<p class="class_title"><strong class="class_title">AppotaPayment</strong></p>
<p>Inherits from: NSObject<br />
Declared in: <a href="AppotaPaymentHeader.html">AppotaPayment.h</a></p>
<p class="auto-style8"><strong>General</strong></p>
<p>AppotaPayment is the class that implements all main features of Payment SDK. 
This class provides functions calling to payment interfaces for each various 
methods.</p>
<p class="auto-style8"><strong>Properties</strong></p>
<table border="0" style="border-width: 0px">
	<tr>
		<td style="width: 154px" class="auto-style7">BOOL 
		isSandBoxMode</td>
		<td>Select turn on/off sandbox mode for application</td>
	</tr>
	<tr>
		<td style="width: 154px" class="auto-style7">NSString *clientID</td>
		<td>ClientID code for application provided by Appota system</td>
	</tr>
	<tr>
		<td style="width: 154px" class="auto-style7">NSString *clientSecret</td>
		<td>Series of clientSecret for application provided by Appota system</td>
	</tr>
	<tr>
		<td style="width: 154px" class="auto-style7">NSString *sandboxKey</td>
		<td>Series of sandboxKey for application provided by Appota system</td>
	</tr>
	<tr>
		<td style="width: 154px" class="auto-style7">NSString *inappKey</td>
		<td>Series of inappKey for application provided by Appota system</td>
	</tr>
	<tr>
		<td style="width: 154px" class="auto-style7">BOOL 
		debugMode</td>
		<td>Select turn on/off debug mode</td>
	</tr>
</table>

<p class="auto-style8"><strong>Definition Type</strong></p>
<p><strong><a name="AppotaPaymentHandler">AppotaPaymentHandler</a></strong></p>
<p>Conveyed when calling payment methods to receive data after constructing 
process of a transaction ends.</p>

<pre><code data-language="C">typedef void(^AppotaPaymentHandler)(NSDictionary *apiDict, AppotaPaymentState status, NSError *error);</code></pre>

<p><strong><a name="AppotaPaymentState">AppotaPaymentState</a></strong></p>
<p>Values of transaction status returned when constructing process of a 
transaction ends.</p>
<pre><code data-language="C">typedef enum {
&nbsp;&nbsp;&nbsp; AppotaPaymentSucceed = 1,
&nbsp;&nbsp;&nbsp; AppotaPaymentFailed = 0,
&nbsp;&nbsp;&nbsp; AppotaPaymentSMSPending = 2,
&nbsp;&nbsp;&nbsp; AppotaPaymentSMSCanceled = 3,
&nbsp;&nbsp;&nbsp; AppotaPaymentSMSInValidAmount = 4,
&nbsp;&nbsp;&nbsp; AppotaPaymentClosed = 5,
&nbsp;&nbsp;&nbsp; AppotaPaymentCardInvalid = 6,
&nbsp;&nbsp;&nbsp; AppotaPaymentInvalidAmount = 7,
&nbsp;&nbsp;&nbsp; AppotaGetListSMSError = 11,
&nbsp;&nbsp;&nbsp; AppotaPaymentWrongFormatResponse = 12,
} AppotaPaymentState;</code></pre>

<p class="auto-style8"><strong>Methods</strong></p>
<table border="1" class="gridtable">
	<tr>
		<td style="width: 122px">void</td>
		<td><a href="#makeSMSPaymentWithAmount">makeSMSPaymentWithAmount:(int) 
		amount withState:(NSString*) state withTarget:(NSString*) target 
		withNoticeUrl:(NSString*) noticeUrl 
		withCompletionHandler:(AppotaPaymentHandler) handler</a><br />
		<em>Display payment interface using SMS method with a given price.</em></td>
	</tr>
	<tr>
		<td style="width: 122px">void</td>
		<td><a href="#makeSMSPaymentWithListAmount">
		makeSMSPaymentWithListAmount:(NSArray*) listAmount withState:(NSString*) 
		state withTarget:(NSString*) target withNoticeUrl:(NSString*) noticeUrl 
		withDescription:(NSString*) description 
		withCompletionHandler:(AppotaPaymentHandler) handler</a><br />
		<em>Display payment interface using SMS method with a list of given 
		prices.</em></td>
	</tr>
	<tr>
		<td style="width: 122px">void</td>
		<td><a href="#makeSMSPaymentWithState">
		makeSMSPaymentWithState:(NSString*) state withTarget:(NSString*) target 
		withNoticeUrl:(NSString*) noticeUrl withDescription:(NSString*) 
		description withCompletionHandler:(AppotaPaymentHandler) handler</a><br />
		<em>Get SMS structures from system (for those applications design 
		payment interface themselves, do not use displayed interface of Appota 
		SDK).</em></td>
	</tr>
	<tr>
		<td style="width: 122px">void</td>
		<td><a href="#makePaypalPaymentWithAmount">
		makePaypalPaymentWithAmount:(float) amount withState:(NSString*) state 
		withTarget:(NSString*) target withNoticeUrl:(NSString*) noticeUrl 
		withCompletionHandler:(AppotaPaymentHandler) handler</a><br />
		<em>Display payment interface using Paypal method with a given price.</em></td>
	</tr>
	<tr>
		<td style="width: 122px">void</td>
		<td><a href="#makePaypalPaymentWithListAmount">
		makePaypalPaymentWithListAmount:(NSArray*) listAmount 
		withState:(NSString*) state withTarget:(NSString*) target 
		withNoticeUrl:(NSString*) noticeUrl withDescription:(NSString*) 
		description withCompletionHandler:(AppotaPaymentHandler) handler</a><br />
		<em>Display payment interface using Paypal method with a list of given 
		prices.</em></td>
	</tr>
	<tr>
		<td style="width: 122px">void</td>
		<td><a href="#makePaypalPaymentWithState">
		makePaypalPaymentWithState:(NSString*) state withTarget:(NSString*) 
		target withNoticeUrl:(NSString*) noticeUrl withDescription:(NSString*) 
		description withCompletionHandler:(AppotaPaymentHandler) handler</a><br />
		<em>Display payment interface using Paypal method that allows user to 
		add the amount of money.</em></td>
	</tr>
	<tr>
		<td style="width: 122px">void</td>
		<td><a href="#makeCardPaymentWithCardCode">
		makeCardPaymentWithCardCode:(NSString *)cardCode 
		withCardSerial:(NSString *)cardSerial withCardVendor:(NSString 
		*)cardVendor withState:(NSString*) state withTarget:(NSString*) target 
		withNoticeUrl:(NSString*) noticeUrl 
		withCompletionHandler:(AppotaPaymentHandler) handler</a><br />
		<em>Payment by direct Card (for those applications design payment 
		interface themselves, do not use displayed interface of Appota SDK).</em></td>
	</tr>
	<tr>
		<td style="width: 122px">void</td>
		<td><a href="#makeCardPaymentWithState">
		makeCardPaymentWithState:(NSString*) state withTarget:(NSString*) target 
		withNoticeUrl:(NSString*) noticeUrl withDescription:(NSString*) 
		description withCompletionHandler:(AppotaPaymentHandler) handler</a><br />
		<em>Display payment interface using Card method.</em></td>
	</tr>
	<tr>
		<td style="width: 122px">void</td>
		<td><a href="#makeBankPaymentWithAmount">
		makeBankPaymentWithAmount:(float) amount withState:(NSString*) state 
		withTarget:(NSString*) target withNoticeUrl:(NSString*) noticeUrl 
		withCompletionHandler:(AppotaPaymentHandler) handler</a><br />
		<em>Display payment interface using Internet Banking with a given price.</em></td>
	</tr>
	<tr>
		<td style="width: 122px">void</td>
		<td><a href="#makePaypalPaymentWithListAmount">
		makeBankPaymentWithListAmount:(NSArray*) listAmount 
		withState:(NSString*) state withTarget:(NSString*) target 
		withNoticeUrl:(NSString*) noticeUrl withDescription:(NSString*) 
		description withCompletionHandler:(AppotaPaymentHandler) handler</a><br />
		<em>Display payment interface using Internet Banking with a list of 
		given prices.</em></td>
	</tr>
	<tr>
		<td style="width: 122px">void</td>
		<td><a href="#makePaypalPaymentWithState">
		makeBankPaymentWithState:(NSString*) state withTarget:(NSString*) target 
		withNoticeUrl:(NSString*) noticeUrl withDescription:(NSString*) 
		description withCompletionHandler:(AppotaPaymentHandler) handler</a><br />
		<em>Display payment interface using Internet Banking that allows users 
		to add the amount of money.</em></td>
	</tr>
	<tr>
		<td style="width: 122px">void</td>
		<td><a href="#makeApplePaymentWithItem">
		makeApplePaymentWithItem:(AppotaAppleIAPItem*) item 
		withState:(NSString*) state withTarget:(NSString*) target 
		withNoticeUrl:(NSString*) noticeUrl withDescription:(NSString*) 
		description withCompletionHandler:(AppotaPaymentHandler) handler</a><br />
		<em>Display payment interface using Apple Payment method with a given 
		IAP item.</em></td>
	</tr>
	<tr>
		<td style="width: 122px">void</td>
		<td><a href="#makeApplePaymentWithListItem">
		makeApplePaymentWithListItem:(NSArray*) lisItem withState:(NSString*) 
		state withTarget:(NSString*) target withNoticeUrl:(NSString*) noticeUrl 
		withDescription:(NSString*) description 
		withCompletionHandler:(AppotaPaymentHandler) handler</a><br />
		<em>Display payment interface using Apple Payment method with a list of 
		given IAP items.</em></td>
	</tr>
	<tr>
		<td style="width: 122px">void</td>
		<td>checkTransactionInAppWithID:(NSString *)inApp_id 
		withCompletionHandler:(AppotaResultHandler) handler</td>
	</tr>
	<tr>
		<td style="width: 122px">void</td>
		<td>checkUpdate</td>
	</tr>
</table>

<p>&nbsp;</p>
<hr/><strong><p class="method_detail">(void) <a name="makeSMSPaymentWithAmount">
makeSMSPaymentWithAmount</a>:(int) amount withState:(NSString*) state 
withTarget:(NSString*) target withNoticeUrl:(NSString*) noticeUrl 
withCompletionHandler:(<a href="#AppotaPaymentHandler">AppotaPaymentHandler</a>) handler</p></strong>
<p>Display payment interface using SMS method with a given price.</p>
<p><strong>Parameters:</strong></p>
<p>- amount: value of each SMS<br />
- state: A seri of customized states for dev to send to<br />
- target: A seri of customized targets for dev to send to<br />
- noticeUrl: URL called when transaction ends<br />
- handler: Handler called when constructing transaction ends</p>
<hr/><strong><p class="method_detail">(void) <a name="makeSMSPaymentWithListAmount">
makeSMSPaymentWithListAmount</a>:(NSArray*) listAmount withState:(NSString*) 
state withTarget:(NSString*) target withNoticeUrl:(NSString*) noticeUrl 
withDescription:(NSString*) description 
withCompletionHandler:(<a href="#AppotaPaymentHandler">AppotaPaymentHandler</a>) handler</p></strong>
<p>Display payment interface using SMS method with a list of given prices.</p>
<p><strong>Parameters:</strong></p>
<p>- listAmount: A list of SMS value <br />
- state: A seri of customized states for dev to send to<br />
- target: A seri of customized targets for dev to send to<br />
- noticeUrl: URL called when transaction ends<br />
- description: Decribe payment specifically <br />
- handler: Handler called when constructing transaction ends</p>
<hr/><strong><p class="method_detail">(void) <a name="makeSMSPaymentWithState">
makeSMSPaymentWithState</a>:(NSString*) state withTarget:(NSString*) target 
withNoticeUrl:(NSString*) noticeUrl withDescription:(NSString*) description 
withCompletionHandler:(<a href="#AppotaPaymentHandler">AppotaPaymentHandler</a>) handler</p></strong>
<p>Get SMS structures from system (for those applications design payment 
interface themselves, do not use displayed interface of Appota SDK).</p>
<p><strong>Parameters:</strong></p>
<p>- state: A seri of customized states for dev to send to<br />
- target: A seri of customized targets for dev to send to<br />
- noticeUrl: URL called when transaction ends<br />
- description: Decribe payment specifically <br />
- handler: Handler called when constructing transaction ends</p>
<hr/><strong><p class="method_detail">(void) <a name="makePaypalPaymentWithAmount">
makePaypalPaymentWithAmount</a>:(float) amount withState:(NSString*) state 
withTarget:(NSString*) target withNoticeUrl:(NSString*) noticeUrl 
withCompletionHandler:(<a href="#AppotaPaymentHandler">AppotaPaymentHandler</a>) handler</p></strong>
<p>Display payment interface using Paypal method with a given price.</p>
<p><strong>Parameters:</strong></p>
<p>- amount: value of each SMS<br />
- state: A seri of customized states for dev to send to<br />
- target: A seri of customized targets for dev to send to<br />
- noticeUrl: URL called when transaction ends<br />
- handler: Handler called when constructing transaction ends</p>
<hr/><strong><p class="method_detail">(void) <a name="makePaypalPaymentWithListAmount">
makePaypalPaymentWithListAmount</a>:(NSArray*) listAmount withState:(NSString*) 
state withTarget:(NSString*) target withNoticeUrl:(NSString*) noticeUrl 
withDescription:(NSString*) description 
withCompletionHandler:(<a href="#AppotaPaymentHandler">AppotaPaymentHandler</a>) handler</p></strong>
<p>Display payment interface using Paypal method with a list of given prices.</p>
<p><strong>Parameters:</strong></p>
<p>- listAmount: List of value to charge<br />
- state: A seri of customized states for dev to send to<br />
- target: A seri of customized targets for dev to send to<br />
- noticeUrl: URL called when transaction ends<br />
- description: Decribe payment specifically<br />
- handler: Handler called when constructing transaction ends</p>
<hr/><strong><p class="method_detail">(void) <a name="makePaypalPaymentWithState">
makePaypalPaymentWithState</a>:(NSString*) state withTarget:(NSString*) target 
withNoticeUrl:(NSString*) noticeUrl withDescription:(NSString*) description 
withCompletionHandler:(<a href="#AppotaPaymentHandler">AppotaPaymentHandler</a>) handler</p></strong>
<p>Display payment interface using Paypal method that allows user to add the 
amount of money.</p>
<p><strong>Parameters:</strong></p>
<p>- state: A seri of customized states for dev to send to<br />
- target: A seri of customized targets for dev to send to<br />
- noticeUrl: URL called when transaction ends<br />
- description: Decribe payment specifically<br />
- handler: Handler called when constructing transaction ends</p>
<hr/><strong><p class="method_detail">(void) <a name="makeCardPaymentWithCardCode">
makeCardPaymentWithCardCode</a>:(NSString *)cardCode withCardSerial:(NSString 
*)cardSerial withCardVendor:(NSString *)cardVendor withState:(NSString*) state 
withTarget:(NSString*) target withNoticeUrl:(NSString*) noticeUrl 
withCompletionHandler:(<a href="#AppotaPaymentHandler">AppotaPaymentHandler</a>) handler</p></strong>
<p>Payment by direct Card (for those applications design payment interface 
themselves, do not use displayed interface of Appota SDK).</p>
<p><strong>Parameters:</strong></p>
<p>- cardCode: Card Code Number<br />
- cardSerial: Serial Number<br />
- cardVendor: Vendors. Now supporting: <br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <span class="auto-style2">vinaphone</span>: 
Vinaphone Card<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <span class="auto-style2">mobifone</span>:&nbsp; 
Mobifone Card<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <span class="auto-style2">viettel</span>:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Viettel 
Card<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <span class="auto-style2">fpt</span>:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; FPT Gate 
Card<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <span class="auto-style2">mega</span>:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; MegaCard&nbsp;&nbsp; <br />
- state: A seri of customized states for dev to send to<br />
- target: A seri of customized targets for dev to send to<br />
- noticeUrl: URL called when transaction ends<br />
- handler: Handler called when constructing transaction ends</p>
<hr/><strong><p class="method_detail">(void) <a name="makeCardPaymentWithState">
makeCardPaymentWithState</a>:(NSString*) state withTarget:(NSString*) target 
withNoticeUrl:(NSString*) noticeUrl withDescription:(NSString*) description 
withCompletionHandler:(<a href="#AppotaPaymentHandler">AppotaPaymentHandler</a>) handler</p></strong>
<p>Display payment interface using Card method.</p>
<p><strong>Parameters:</strong></p>
<p>- state: A seri of customized states for dev to send to<br />
- target: A seri of customized targets for dev to send to<br />
- noticeUrl: URL called when transaction ends<br />
- description: Decribe payment specifically<br />
- handler: Handler called when constructing transaction ends</p>
<hr/><strong><p class="method_detail">(void) <a name="makeBankPaymentWithAmount">
makeBankPaymentWithAmount</a>:(float) amount withState:(NSString*) state 
withTarget:(NSString*) target withNoticeUrl:(NSString*) noticeUrl 
withCompletionHandler:(<a href="#AppotaPaymentHandler">AppotaPaymentHandler</a>) handler</p></strong>
<p>Display payment interface using Internet Banking with a given price.</p>
<p><strong>Parameters:</strong></p>
<p>- amount: Value to charge<br />
- state: A seri of customized states for dev to send to<br />
- target: A seri of customized targets for dev to send to<br />
- noticeUrl: URL called when transaction ends<br />
- handler: Handler called when constructing transaction ends</p>
<hr/><strong><p class="method_detail">(void) <a name="makeBankPaymentWithListAmount">
makeBankPaymentWithListAmount</a>:(NSArray*) listAmount withState:(NSString*) 
state withTarget:(NSString*) target withNoticeUrl:(NSString*) noticeUrl 
withDescription:(NSString*) description 
withCompletionHandler:(<a href="#AppotaPaymentHandler">AppotaPaymentHandler</a>) handler</p></strong>
<p>Display payment interface using Internet Banking with a list of given prices.</p>
<p><strong>Parameters:</strong></p>
<p>- listAmount: A list of value to charge<br />
- state: A seri of customized states for dev to send to<br />
- target: A seri of customized targets for dev to send to<br />
- noticeUrl: URL called when transaction ends<br />
- description: Decribe payment specifically<br />
- handler: Handler called when constructing transaction ends</p>
<hr/><strong><p class="method_detail">(void) <a name="makeBankPaymentWithState">
makeBankPaymentWithState</a>:(NSString*) state withTarget:(NSString*) target 
withNoticeUrl:(NSString*) noticeUrl withDescription:(NSString*) description 
withCompletionHandler:(<a href="#AppotaPaymentHandler">AppotaPaymentHandler</a>) handler</p></strong>
<p>Display payment interface using Internet Banking that allows users to add the 
amount of money.</p>
<p><strong>Parameters:</strong></p>
<p>- state: A seri of customized states for dev to send to<br />
- target: A seri of customized targets for dev to send to<br />
- noticeUrl: URL called when transaction ends<br />
- description: Decribe payment specifically<br />
- handler: Handler called when constructing transaction ends</p>
<hr/><strong><p class="method_detail">(void) <a name="makeApplePaymentWithItem">
makeApplePaymentWithItem</a>:(AppotaAppleIAPItem*) item withState:(NSString*) 
state withTarget:(NSString*) target withNoticeUrl:(NSString*) noticeUrl 
withDescription:(NSString*) description 
withCompletionHandler:(<a href="#AppotaPaymentHandler">AppotaPaymentHandler</a>) handler</p></strong>
<p>Display payment interface using Apple Payment method with a given IAP item.</p>
<p><strong>Parameters:</strong></p>
<p>- items: IAP Item<br />
- state: A seri of customized states for dev to send to<br />
- target: A seri of customized targets for dev to send to<br />
- noticeUrl: URL called when transaction ends<br />
- description: Decribe payment specifically<br />
- handler: Handler called when constructing transaction ends</p>
<hr/><strong><p class="method_detail">(void) <a name="makeApplePaymentWithListItem">
makeApplePaymentWithListItem</a>:(NSArray*) lisItem withState:(NSString*) state 
withTarget:(NSString*) target withNoticeUrl:(NSString*) noticeUrl 
withDescription:(NSString*) description 
withCompletionHandler:(<a href="#AppotaPaymentHandler">AppotaPaymentHandler</a>) handler</p></strong>
<p>Display payment interface using Apple Payment method with a list of given IAP 
items.</p>
<p><strong>Parameters:</strong></p>
<p>- item: List of IAP items<br />
- state: A seri of customized states for dev to send to<br />
- target: A seri of customized targets for dev to send to<br />
- noticeUrl: URL called when transaction ends<br />
- description: Decribe payment specifically<br />
- handler: Handler called when constructing transaction ends</p>
<p>&nbsp;</p>

</body>

</html>
