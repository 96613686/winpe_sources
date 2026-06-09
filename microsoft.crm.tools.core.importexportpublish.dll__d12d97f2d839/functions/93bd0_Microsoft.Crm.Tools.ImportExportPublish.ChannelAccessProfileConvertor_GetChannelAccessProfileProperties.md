# Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfileConvertor::GetChannelAccessProfileProperties

- ea: `0x93bd0`
- end: `0x93d9d`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfileConvertor::GetChannelAccessProfileProperties`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x93a20`

## callees

- `0x93bd0`
- `0x93e90`

## string_xrefs

- `0x93bec`: `EmailAccess`
- `0x93bf1`: `emailaccess`
- `0x93c10`: `FacebookAccess`
- `0x93c15`: `facebookaccess`
- `0x93c34`: `PhoneAccess`
- `0x93c39`: `phoneaccess`
- `0x93c58`: `TwitterAccess`
- `0x93c5d`: `twitteraccess`
- `0x93c7c`: `WebAccess`
- `0x93c81`: `webaccess`

## pseudocode

```c

```

## disassembly

```asm
0x93bd0  ldarg.0
0x93bd1  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap> Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfileConvertor::_channelAccessProfileProperties
0x93bd6  brtrue   loc_93D96
0x93bdb  ldarg.0
0x93bdc  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap>::.ctor()
0x93be1  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap> Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfileConvertor::_channelAccessProfileProperties
0x93be6  ldarg.0
0x93be7  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap> Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfileConvertor::_channelAccessProfileProperties
0x93bec  ldstr    aEmailaccess// "EmailAccess"
0x93bf1  ldstr    aEmailaccess_0// "emailaccess"
0x93bf6  ldtoken  [mscorlib]System.Boolean
0x93bfb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x93c00  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x93c05  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap>::Add(var<u1>)
0x93c0a  ldarg.0
0x93c0b  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap> Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfileConvertor::_channelAccessProfileProperties
0x93c10  ldstr    aFacebookaccess// "FacebookAccess"
0x93c15  ldstr    aFacebookaccess_0// "facebookaccess"
0x93c1a  ldtoken  [mscorlib]System.Boolean
0x93c1f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x93c24  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x93c29  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap>::Add(var<u1>)
0x93c2e  ldarg.0
0x93c2f  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap> Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfileConvertor::_channelAccessProfileProperties
0x93c34  ldstr    aPhoneaccess// "PhoneAccess"
0x93c39  ldstr    aPhoneaccess_0// "phoneaccess"
0x93c3e  ldtoken  [mscorlib]System.Boolean
0x93c43  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x93c48  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x93c4d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap>::Add(var<u1>)
0x93c52  ldarg.0
0x93c53  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap> Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfileConvertor::_channelAccessProfileProperties
0x93c58  ldstr    aTwitteraccess// "TwitterAccess"
0x93c5d  ldstr    aTwitteraccess_0// "twitteraccess"
0x93c62  ldtoken  [mscorlib]System.Boolean
0x93c67  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x93c6c  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x93c71  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap>::Add(var<u1>)
0x93c76  ldarg.0
0x93c77  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap> Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfileConvertor::_channelAccessProfileProperties
0x93c7c  ldstr    aWebaccess// "WebAccess"
0x93c81  ldstr    aWebaccess_0// "webaccess"
0x93c86  ldtoken  [mscorlib]System.Boolean
0x93c8b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x93c90  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x93c95  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap>::Add(var<u1>)
0x93c9a  ldarg.0
0x93c9b  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap> Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfileConvertor::_channelAccessProfileProperties
0x93ca0  ldstr    aViewknowledgea// "ViewKnowledgeArticles"
0x93ca5  ldstr    aViewknowledgea_0// "viewknowledgearticles"
0x93caa  ldtoken  [mscorlib]System.Boolean
0x93caf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x93cb4  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x93cb9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap>::Add(var<u1>)
0x93cbe  ldarg.0
0x93cbf  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap> Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfileConvertor::_channelAccessProfileProperties
0x93cc4  ldstr    aViewarticlerat// "ViewArticleRating"
0x93cc9  ldstr    aViewarticlerat_0// "viewarticlerating"
0x93cce  ldtoken  [mscorlib]System.Boolean
0x93cd3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x93cd8  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x93cdd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap>::Add(var<u1>)
0x93ce2  ldarg.0
0x93ce3  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap> Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfileConvertor::_channelAccessProfileProperties
0x93ce8  ldstr    aRateknowledgea// "RateKnowledgeArticles"
0x93ced  ldstr    aRateknowledgea_0// "rateknowledgearticles"
0x93cf2  ldtoken  [mscorlib]System.Boolean
0x93cf7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x93cfc  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x93d01  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap>::Add(var<u1>)
0x93d06  ldarg.0
0x93d07  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap> Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfileConvertor::_channelAccessProfileProperties
0x93d0c  ldstr    aSubmitfeedback// "SubmitFeedback"
0x93d11  ldstr    aSubmitfeedback_0// "submitfeedback"
0x93d16  ldtoken  [mscorlib]System.Boolean
0x93d1b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x93d20  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x93d25  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap>::Add(var<u1>)
0x93d2a  ldarg.0
0x93d2b  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap> Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfileConvertor::_channelAccessProfileProperties
0x93d30  ldstr    aStatecode_0// "StateCode"
0x93d35  ldstr    aStatecode// "statecode"
0x93d3a  ldtoken  [mscorlib]System.Int32
0x93d3f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x93d44  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x93d49  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap>::Add(var<u1>)
0x93d4e  ldarg.0
0x93d4f  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap> Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfileConvertor::_channelAccessProfileProperties
0x93d54  ldstr    aStatuscode_0// "StatusCode"
0x93d59  ldstr    aStatuscode// "statuscode"
0x93d5e  ldtoken  [mscorlib]System.Int32
0x93d63  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x93d68  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x93d6d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap>::Add(var<u1>)
0x93d72  ldarg.0
0x93d73  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap> Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfileConvertor::_channelAccessProfileProperties
0x93d78  ldstr    aIsguestprofile// "IsGuestProfile"
0x93d7d  ldstr    aIsguestprofile_0// "isguestprofile"
0x93d82  ldtoken  [mscorlib]System.Boolean
0x93d87  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x93d8c  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x93d91  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap>::Add(var<u1>)
0x93d96  ldarg.0
0x93d97  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfilePropertyMap> Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfileConvertor::_channelAccessProfileProperties
0x93d9c  ret
```
