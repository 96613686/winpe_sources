# Microsoft.Crm.Asynchronous.YammerPostOperation::GetYammerActivityFromRecord

- ea: `0x9d90`
- end: `0x9fa2`
- name: `Microsoft.Crm.Asynchronous.YammerPostOperation::GetYammerActivityFromRecord`
- size: `530`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x9ae0`

## callees

- `0x9d90`

## string_xrefs

- `0x9d9c`: `reader`

## pseudocode

```c

```

## disassembly

```asm
0x9d90  ldarg.2
0x9d91  ldstr    aFollowertable// "followerTable"
0x9d96  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x9d9b  ldarg.1
0x9d9c  ldstr    aReader// "reader"
0x9da1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x9da6  ldarg.1
0x9da7  ldstr    aPostid// "postid"
0x9dac  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x9db1  unbox.any [mscorlib]System.Guid
0x9db6  stloc.0
0x9db7  ldarg.1
0x9db8  ldstr    aOwninguseremai// "owninguseremail"
0x9dbd  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x9dc2  isinst   [mscorlib]System.String
0x9dc7  stloc.1
0x9dc8  ldloc.1
0x9dc9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9dce  ldc.i4.0
0x9dcf  ceq
0x9dd1  ldstr    aOwninguseremai_0// "owningUserEmail must have value"
0x9dd6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x9ddb  ldarg.1
0x9ddc  ldstr    aRegardingobjec// "regardingobjectid"
0x9de1  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x9de6  unbox.any [mscorlib]System.Guid
0x9deb  stloc.2
0x9dec  ldarg.1
0x9ded  ldstr    aRegardingobjec_1// "regardingobjectidname"
0x9df2  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x9df7  isinst   [mscorlib]System.String
0x9dfc  stloc.3
0x9dfd  ldarg.1
0x9dfe  ldstr    aRegardingobjec_0// "regardingobjecttypecode"
0x9e03  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x9e08  unbox.any [mscorlib]System.Int32
0x9e0d  stloc.s  4
0x9e0f  ldarg.1
0x9e10  ldstr    aIspostfollow// "ispostfollow"
0x9e15  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x9e1a  unbox.any [mscorlib]System.Int32
0x9e1f  stloc.s  5
0x9e21  ldarg.1
0x9e22  ldstr    aOwninguserid// "owninguserid"
0x9e27  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x9e2c  isinst   [mscorlib]System.String
0x9e31  stloc.s  6
0x9e33  ldarg.1
0x9e34  ldstr    aModifiedon// "modifiedon"
0x9e39  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x9e3e  unbox.any [mscorlib]System.DateTime
0x9e43  stloc.s  7
0x9e45  ldloc.s  6
0x9e47  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9e4c  ldc.i4.0
0x9e4d  ceq
0x9e4f  ldstr    aOwninguseridMu// "owningUserId must have value"
0x9e54  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x9e59  ldnull
0x9e5a  stloc.s  8
0x9e5c  ldnull
0x9e5d  stloc.s  9
0x9e5f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9e64  ldstr    a01_3// "{0},{1}"
0x9e69  ldc.i4.2
0x9e6a  newarr   [mscorlib]System.Object
0x9e6f  dup
0x9e70  ldc.i4.0
0x9e71  ldloc.s  4
0x9e73  box      [mscorlib]System.Int32
0x9e78  stelem.ref
0x9e79  dup
0x9e7a  ldc.i4.1
0x9e7b  ldloc.2
0x9e7c  box      [mscorlib]System.Guid
0x9e81  stelem.ref
0x9e82  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9e87  stloc.s  0xA
0x9e89  ldarg.3
0x9e8a  brfalse.s loc_9EA0
0x9e8c  ldarg.2
0x9e8d  ldloc.s  0xA
0x9e8f  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>>::ContainsKey(var<u1>)
0x9e94  brfalse.s loc_9EA0
0x9e96  ldarg.2
0x9e97  ldloc.s  0xA
0x9e99  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>>::get_Item(void)
0x9e9e  stloc.s  9
0x9ea0  ldarg.0
0x9ea1  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Asynchronous.YammerPostOperation::_organizationContext
0x9ea6  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9eab  ldloc.s  4
0x9ead  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x9eb2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x9eb7  ldloc.2
0x9eb8  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x9ebd  stloc.s  0xB
0x9ebf  ldloc.s  0xB
0x9ec1  ldloc.3
0x9ec2  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::set_Name(string)
0x9ec7  ldloc.s  5
0x9ec9  brfalse.s loc_9EED
0x9ecb  ldloc.s  5
0x9ecd  ldc.i4.1
0x9ece  bne.un   loc_9F60
0x9ed3  call     class [Microsoft.Crm.Yammer]Microsoft.Crm.Yammer.YammerActivityFactory [Microsoft.Crm.Yammer]Microsoft.Crm.Yammer.YammerActivityFactory::get_Instance()
0x9ed8  ldarg.0
0x9ed9  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Asynchronous.YammerPostOperation::_organizationContext
0x9ede  ldloc.1
0x9edf  ldloc.s  9
0x9ee1  ldloc.s  0xB
0x9ee3  ldarg.3
0x9ee4  callvirt instance class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.YammerActivity [Microsoft.Crm.Yammer]Microsoft.Crm.Yammer.YammerActivityFactory::GetYammerActivityForFollow(class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference, bool)
0x9ee9  stloc.s  8
0x9eeb  br.s     loc_9F6B
0x9eed  ldarg.1
0x9eee  ldstr    aText// "text"
0x9ef3  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x9ef8  isinst   [mscorlib]System.String
0x9efd  stloc.s  0xC
0x9eff  ldloc.s  0xC
0x9f01  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9f06  brfalse.s loc_9F0A
0x9f08  ldnull
0x9f09  ret
0x9f0a  ldloc.s  0xC
0x9f0c  ldarg.0
0x9f0d  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.YammerPostOperation::_organizationId
0x9f12  call     class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.AutoPostText [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.PostUtility::DeserializeAutoPost(string, valuetype [mscorlib]System.Guid)
0x9f17  stloc.s  0xD
0x9f19  ldloc.s  0xD
0x9f1b  brtrue.s loc_9F3F
0x9f1d  ldarg.0
0x9f1e  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.YammerPostOperation::_organizationId
0x9f23  ldc.i4.s 0x14
0x9f25  ldstr    a0_1// "{0}"
0x9f2a  ldc.i4.1
0x9f2b  newarr   [mscorlib]System.Object
0x9f30  dup
0x9f31  ldc.i4.0
0x9f32  ldstr    aDroppingAutopo_1// "Dropping Autopost to Yammer. Reason:The"...
0x9f37  stelem.ref
0x9f38  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9f3d  ldnull
0x9f3e  ret
0x9f3f  call     class [Microsoft.Crm.Yammer]Microsoft.Crm.Yammer.YammerActivityFactory [Microsoft.Crm.Yammer]Microsoft.Crm.Yammer.YammerActivityFactory::get_Instance()
0x9f44  ldarg.0
0x9f45  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Asynchronous.YammerPostOperation::_organizationContext
0x9f4a  ldloc.s  0xD
0x9f4c  callvirt instance string [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.AutoPostText::get_Id()
0x9f51  ldloc.1
0x9f52  ldloc.s  9
0x9f54  ldloc.s  0xB
0x9f56  ldarg.3
0x9f57  callvirt instance class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.YammerActivity [Microsoft.Crm.Yammer]Microsoft.Crm.Yammer.YammerActivityFactory::GetYammerActivityForPost(class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext, string, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference, bool)
0x9f5c  stloc.s  8
0x9f5e  br.s     loc_9F6B
0x9f60  ldstr    aUnknownValueRe// "Unknown value returned from the p_Retri"...
0x9f65  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x9f6a  throw
0x9f6b  ldloc.s  8
0x9f6d  brfalse.s loc_9F9F
0x9f6f  ldloc.s  8
0x9f71  ldloc.0
0x9f72  callvirt instance void [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.YammerActivity::set_Id(valuetype [mscorlib]System.Guid)
0x9f77  ldloc.s  8
0x9f79  ldloc.2
0x9f7a  callvirt instance void [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.YammerActivity::set_RegardingObjectId(valuetype [mscorlib]System.Guid)
0x9f7f  ldloc.s  8
0x9f81  ldloc.s  4
0x9f83  callvirt instance void [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.YammerActivity::set_RegardingObjectTypeCode(int32)
0x9f88  ldloc.s  8
0x9f8a  callvirt instance class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.YammerUser [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.YammerActivity::get_Actor()
0x9f8f  ldloc.s  6
0x9f91  callvirt instance void [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.YammerUser::set_UserId(string)
0x9f96  ldloc.s  8
0x9f98  ldloc.s  7
0x9f9a  callvirt instance void [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.YammerActivity::set_ModifiedOn(valuetype [mscorlib]System.DateTime)
0x9f9f  ldloc.s  8
0x9fa1  ret
```
