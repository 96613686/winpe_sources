# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailRecipientActivityControl::GenerateClientStrings

- ea: `0x27e90`
- end: `0x2823e`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailRecipientActivityControl::GenerateClientStrings`
- size: `942`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x27ab0`

## string_xrefs

- `0x281ac`: `CustomControl_EmailEngagment_Opened`
- `0x27e96`: `EmailEngagment_OpenedBy`
- `0x27ea0`: `EmailEngagment_OpenedBy`
- `0x27ee4`: `EmailEngagment_LinksViewed`
- `0x27eee`: `EmailEngagment_LinksViewed`
- `0x28084`: `EmailEngagment_OpenActivity`
- `0x2808e`: `Email_Engagement_Recipient_Activity_Stats_Section_OpenActivity`
- `0x280d2`: `EmailEngagment_LinkActivity`
- `0x280dc`: `Email_Engagement_Recipient_Activity_Stats_Section_LinkActivity`
- `0x280ec`: `EmailEngagment_Link_Preview`
- `0x280f6`: `Email_Engagement_Recipient_Interaction_Details_Section_Link_Preview`
- `0x281a2`: `EmailEngagement_Opened`
- `0x28224`: `EMAILENGAGMENT_OPENEDBY_WITHOUT_LOCATION`
- `0x2822e`: `EmailEngagment_OpenedBy_Without_Location`

## pseudocode

```c

```

## disassembly

```asm
0x27e90  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x27e95  dup
0x27e96  ldstr    aEmailengagment_2// "EmailEngagment_OpenedBy"
0x27e9b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x27ea0  ldstr    aEmailengagment_2// "EmailEngagment_OpenedBy"
0x27ea5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x27eaa  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x27eaf  dup
0x27eb0  ldstr    aEmailengagment_3// "EmailEngagment_AttachmentViewed"
0x27eb5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x27eba  ldstr    aEmailengagment_3// "EmailEngagment_AttachmentViewed"
0x27ebf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x27ec4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x27ec9  dup
0x27eca  ldstr    aEmailengagment_4// "EmailEngagment_NearLocation"
0x27ecf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x27ed4  ldstr    aEmailengagment_5// "EmailEngagment_Near_Location"
0x27ed9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x27ede  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x27ee3  dup
0x27ee4  ldstr    aEmailengagment_6// "EmailEngagment_LinksViewed"
0x27ee9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x27eee  ldstr    aEmailengagment_6// "EmailEngagment_LinksViewed"
0x27ef3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x27ef8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x27efd  dup
0x27efe  ldstr    aEmailengagment_7// "EmailEngagment_RepliedBy"
0x27f03  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x27f08  ldstr    aEmailengagment_7// "EmailEngagment_RepliedBy"
0x27f0d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x27f12  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x27f17  dup
0x27f18  ldstr    aEmailengagment_8// "EmailEngagment_Year_Text"
0x27f1d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x27f22  ldstr    aEmailengagment_8// "EmailEngagment_Year_Text"
0x27f27  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x27f2c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x27f31  dup
0x27f32  ldstr    aEmailengagment_9// "EmailEngagment_Month_Text"
0x27f37  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x27f3c  ldstr    aEmailengagment_9// "EmailEngagment_Month_Text"
0x27f41  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x27f46  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x27f4b  dup
0x27f4c  ldstr    aEmailengagment_10// "EmailEngagment_Week_Text"
0x27f51  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x27f56  ldstr    aEmailengagment_10// "EmailEngagment_Week_Text"
0x27f5b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x27f60  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x27f65  dup
0x27f66  ldstr    aEmailengagment_11// "EmailEngagment_Day_Text"
0x27f6b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x27f70  ldstr    aEmailengagment_11// "EmailEngagment_Day_Text"
0x27f75  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x27f7a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x27f7f  dup
0x27f80  ldstr    aEmailengagment_12// "EmailEngagment_Hour_Text"
0x27f85  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x27f8a  ldstr    aEmailengagment_12// "EmailEngagment_Hour_Text"
0x27f8f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x27f94  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x27f99  dup
0x27f9a  ldstr    aEmailengagment_13// "EmailEngagment_Minute_Text"
0x27f9f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x27fa4  ldstr    aEmailengagment_13// "EmailEngagment_Minute_Text"
0x27fa9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x27fae  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x27fb3  dup
0x27fb4  ldstr    aEmailengagment_14// "EmailEngagment_JustNow_Text"
0x27fb9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x27fbe  ldstr    aEmailengagment_14// "EmailEngagment_JustNow_Text"
0x27fc3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x27fc8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x27fcd  dup
0x27fce  ldstr    aCustomcontrolE_0// "CustomControl_EmailEngagment_ViewReply"
0x27fd3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x27fd8  ldstr    aCustomcontrolE_0// "CustomControl_EmailEngagment_ViewReply"
0x27fdd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x27fe2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x27fe7  dup
0x27fe8  ldstr    aCustomcontrolJ// "CustomControl_Justnow_Text"
0x27fed  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x27ff2  ldstr    aCustomcontrolJ// "CustomControl_Justnow_Text"
0x27ff7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x27ffc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x28001  dup
0x28002  ldstr    aCustomcontrolH// "CustomControl_Hour_Text"
0x28007  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x2800c  ldstr    aCustomcontrolH// "CustomControl_Hour_Text"
0x28011  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x28016  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x2801b  dup
0x2801c  ldstr    aCustomcontrolH_0// "CustomControl_Hours_Text"
0x28021  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x28026  ldstr    aCustomcontrolH_0// "CustomControl_Hours_Text"
0x2802b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x28030  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x28035  dup
0x28036  ldstr    aCustomcontrolT// "CustomControl_Today_Text"
0x2803b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x28040  ldstr    aCustomcontrolT// "CustomControl_Today_Text"
0x28045  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2804a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x2804f  dup
0x28050  ldstr    aCustomcontrolY// "CustomControl_Yesterday_Text"
0x28055  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x2805a  ldstr    aCustomcontrolY// "CustomControl_Yesterday_Text"
0x2805f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x28064  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x28069  dup
0x2806a  ldstr    aEmailengagment_15// "EmailEngagment_HEADER"
0x2806f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x28074  ldstr    aEmailEngagemen_66// "Email_Engagement_Recipient_Activity_Sta"...
0x28079  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2807e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x28083  dup
0x28084  ldstr    aEmailengagment_16// "EmailEngagment_OpenActivity"
0x28089  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x2808e  ldstr    aEmailEngagemen_67// "Email_Engagement_Recipient_Activity_Sta"...
0x28093  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x28098  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x2809d  dup
0x2809e  ldstr    aEmailengagment_17// "EmailEngagment_AttachementActivity"
0x280a3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x280a8  ldstr    aEmailEngagemen_68// "Email_Engagement_Recipient_Activity_Sta"...
0x280ad  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x280b2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x280b7  dup
0x280b8  ldstr    aEmailengagment_18// "EmailEngagment_ReplyActivity"
0x280bd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x280c2  ldstr    aEmailEngagemen_69// "Email_Engagement_Recipient_Activity_Sta"...
0x280c7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x280cc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x280d1  dup
0x280d2  ldstr    aEmailengagment_19// "EmailEngagment_LinkActivity"
0x280d7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x280dc  ldstr    aEmailEngagemen_70// "Email_Engagement_Recipient_Activity_Sta"...
0x280e1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x280e6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x280eb  dup
0x280ec  ldstr    aEmailengagment_20// "EmailEngagment_Link_Preview"
0x280f1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x280f6  ldstr    aEmailEngagemen_71// "Email_Engagement_Recipient_Interaction_"...
0x280fb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x28100  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x28105  dup
0x28106  ldstr    aEmailengagment_21// "EmailEngagment_Map_Preview"
0x2810b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x28110  ldstr    aEmailEngagemen_72// "Email_Engagement_Recipient_Interaction_"...
0x28115  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2811a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x2811f  dup
0x28120  ldstr    aEmailengagment_22// "EmailEngagment_Clicked_Near_Title"
0x28125  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x2812a  ldstr    aEmailengagment_22// "EmailEngagment_Clicked_Near_Title"
0x2812f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x28134  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x28139  dup
0x2813a  ldstr    aEmailengagemen_2// "EmailEngagement_Viewed_Near_Title"
0x2813f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x28144  ldstr    aEmailengagemen_2// "EmailEngagement_Viewed_Near_Title"
0x28149  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2814e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x28153  dup
0x28154  ldstr    aEmailengagemen_3// "EmailEngagement_Location"
0x28159  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x2815e  ldstr    aEmailengagemen_3// "EmailEngagement_Location"
0x28163  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x28168  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x2816d  dup
0x2816e  ldstr    aEmailengagemen_4// "EmailEngagement_Close_Map"
0x28173  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x28178  ldstr    aEmailengagemen_4// "EmailEngagement_Close_Map"
0x2817d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x28182  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x28187  dup
0x28188  ldstr    aEmailengagemen_5// "EmailEngagement_Popout_Map"
0x2818d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x28192  ldstr    aEmailengagemen_5// "EmailEngagement_Popout_Map"
0x28197  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2819c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x281a1  dup
0x281a2  ldstr    aEmailengagemen_6// "EmailEngagement_Opened"
0x281a7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x281ac  ldstr    aCustomcontrolE// "CustomControl_EmailEngagment_Opened"
0x281b1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x281b6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x281bb  dup
0x281bc  ldstr    aEmailengagemen_7// "EMAILENGAGEMENT_RECIPIENTACTIVITY_TITLE"
0x281c1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x281c6  ldstr    aEmailengagemen_8// "EmailEngagement_RecipientActivity_Title"
0x281cb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x281d0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x281d5  dup
0x281d6  ldstr    aEmailengagemen_9// "EMAILENGAGEMENT_RECIPIENTACTIVITY_NONAM"...
0x281db  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x281e0  ldstr    aInlineeditcont_17// "InlineEditControls.InlineLookup.NoName"
0x281e5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x281ea  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x281ef  dup
0x281f0  ldstr    aEmailengagemen_10// "EMAILENGAGEMENT_RECIPIENTACTIVITY_UNKNO"...
0x281f5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x281fa  ldstr    aEmailengagemen_11// "EmailEngagement_Interaction_Unknown_Loc"...
0x281ff  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x28204  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x28209  dup
0x2820a  ldstr    aEmailengagemen_12// "EMAILENGAGEMENT_RECIPIENTACTIVITY_INTER"...
0x2820f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x28214  ldstr    aEmailengagemen_13// "EmailEngagement_Interaction_Load_Failed"
0x28219  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2821e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x28223  dup
0x28224  ldstr    aEmailengagment_23// "EMAILENGAGMENT_OPENEDBY_WITHOUT_LOCATIO"...
0x28229  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x2822e  ldstr    aEmailengagment_24// "EmailEngagment_OpenedBy_Without_Locatio"...
0x28233  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x28238  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x2823d  ret
```
