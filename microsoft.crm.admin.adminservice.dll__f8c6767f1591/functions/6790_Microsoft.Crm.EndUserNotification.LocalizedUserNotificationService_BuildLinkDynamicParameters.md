# Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::BuildLinkDynamicParameters

- ea: `0x6790`
- end: `0x6881`
- name: `Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::BuildLinkDynamicParameters`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x5df0`

## callees

- `0x6790`
- `0x6ed0`

## string_xrefs

- `0x679a`: `LEGAL_LINK`
- `0x67e8`: `LEGAL_LINK`
- `0x67c0`: `PRIVACY_LINK`
- `0x680e`: `PRIVACY_LINK`
- `0x67f8`: `LegalLinkURL`
- `0x681e`: `PrivacyLinkURL`
- `0x6834`: `CONTACTUS_LINK`
- `0x6844`: `ContactUsLinkURL`
- `0x685a`: `LEARN_MORE_LINK`
- `0x686a`: `LearnMoreLinkURL`

## pseudocode

```c

```

## disassembly

```asm
0x6790  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::.ctor()
0x6795  stloc.0
0x6796  ldarg.1
0x6797  brfalse.s loc_67E7
0x6799  ldloc.0
0x679a  ldstr    aLegalLink// "LEGAL_LINK"
0x679f  ldarg.0
0x67a0  ldfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::_context
0x67a5  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetContextInstance(valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext)
0x67aa  ldstr    aMsonlinelegalu// "MSOnlineLegalUrl"
0x67af  ldc.i4.0
0x67b0  callvirt T0x2B000014
0x67b5  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::BuildParamPropertyBag(string name, string value)
0x67ba  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::Add(var<u1>)
0x67bf  ldloc.0
0x67c0  ldstr    aPrivacyLink// "PRIVACY_LINK"
0x67c5  ldarg.0
0x67c6  ldfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::_context
0x67cb  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetContextInstance(valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext)
0x67d0  ldstr    aMsonlineprivac// "MSOnlinePrivacyUrl"
0x67d5  ldc.i4.0
0x67d6  callvirt T0x2B000014
0x67db  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::BuildParamPropertyBag(string name, string value)
0x67e0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::Add(var<u1>)
0x67e5  br.s     loc_6833
0x67e7  ldloc.0
0x67e8  ldstr    aLegalLink// "LEGAL_LINK"
0x67ed  ldarg.0
0x67ee  ldfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::_context
0x67f3  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetContextInstance(valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext)
0x67f8  ldstr    aLegallinkurl// "LegalLinkURL"
0x67fd  ldc.i4.0
0x67fe  callvirt T0x2B000014
0x6803  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::BuildParamPropertyBag(string name, string value)
0x6808  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::Add(var<u1>)
0x680d  ldloc.0
0x680e  ldstr    aPrivacyLink// "PRIVACY_LINK"
0x6813  ldarg.0
0x6814  ldfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::_context
0x6819  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetContextInstance(valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext)
0x681e  ldstr    aPrivacylinkurl// "PrivacyLinkURL"
0x6823  ldc.i4.0
0x6824  callvirt T0x2B000014
0x6829  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::BuildParamPropertyBag(string name, string value)
0x682e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::Add(var<u1>)
0x6833  ldloc.0
0x6834  ldstr    aContactusLink// "CONTACTUS_LINK"
0x6839  ldarg.0
0x683a  ldfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::_context
0x683f  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetContextInstance(valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext)
0x6844  ldstr    aContactuslinku// "ContactUsLinkURL"
0x6849  ldc.i4.0
0x684a  callvirt T0x2B000014
0x684f  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::BuildParamPropertyBag(string name, string value)
0x6854  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::Add(var<u1>)
0x6859  ldloc.0
0x685a  ldstr    aLearnMoreLink// "LEARN_MORE_LINK"
0x685f  ldarg.0
0x6860  ldfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::_context
0x6865  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetContextInstance(valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext)
0x686a  ldstr    aLearnmorelinku// "LearnMoreLinkURL"
0x686f  ldc.i4.0
0x6870  callvirt T0x2B000014
0x6875  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::BuildParamPropertyBag(string name, string value)
0x687a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::Add(var<u1>)
0x687f  ldloc.0
0x6880  ret
```
