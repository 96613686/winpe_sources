# Microsoft.Crm.Common.Application.Commands.ApplicationCommand::ConvertActivityToCase

- ea: `0x21c0`
- end: `0x2340`
- name: `Microsoft.Crm.Common.Application.Commands.ApplicationCommand::ConvertActivityToCase`
- size: `384`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x21c0`

## pseudocode

```c

```

## disassembly

```asm
0x21c0  ldarg.s  7
0x21c2  brfalse.s loc_21C8
0x21c4  ldarg.s  7
0x21c6  br.s     loc_21D1
0x21c8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x21cd  stloc.s  0xB
0x21cf  ldloc.s  0xB
0x21d1  stloc.0
0x21d2  ldarg.s  7
0x21d4  isinst   [Microsoft.Crm]Microsoft.Crm.IClientOrganizationInfo
0x21d9  stloc.1
0x21da  ldloc.1
0x21db  brfalse.s loc_21E5
0x21dd  ldloc.1
0x21de  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx::get_UserId()
0x21e3  br.s     loc_21EF
0x21e5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x21ea  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0x21ef  stloc.2
0x21f0  ldarg.3
0x21f1  brfalse.s loc_21FF
0x21f3  ldarg.3
0x21f4  callvirt instance int32 [mscorlib]System.String::get_Length()
0x21f9  brfalse.s loc_21FF
0x21fb  ldarg.s  4
0x21fd  brtrue.s loc_2205
0x21ff  ldsfld   string [mscorlib]System.String::Empty
0x2204  ret
0x2205  ldsfld   string [mscorlib]System.String::Empty
0x220a  stloc.3
0x220b  ldarg.2
0x220c  brfalse.s loc_2216
0x220e  ldarg.2
0x220f  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2214  brtrue.s loc_221E
0x2216  ldsfld   string [mscorlib]System.String::Empty
0x221b  stloc.3
0x221c  br.s     loc_2220
0x221e  ldarg.2
0x221f  stloc.3
0x2220  ldstr    aIncident// "incident"
0x2225  ldloc.0
0x2226  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x222b  stloc.s  4
0x222d  ldloc.s  4
0x222f  ldstr    aTitle// "title"
0x2234  ldloc.3
0x2235  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x223a  ldloc.0
0x223b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2240  ldarg.s  4
0x2242  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x2247  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x224c  stloc.s  5
0x224e  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::.ctor()
0x2253  stloc.s  6
0x2255  ldloc.s  6
0x2257  ldarg.3
0x2258  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::set_ID(string)
0x225d  ldloc.s  6
0x225f  ldloc.s  5
0x2261  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::set_Type(int32)
0x2266  ldloc.s  4
0x2268  ldstr    aCustomerid// "customerid"
0x226d  ldloc.s  6
0x226f  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x2274  ldarg.s  6
0x2276  ldc.i4   0x81
0x227b  bne.un.s loc_2299
0x227d  ldarg.s  5
0x227f  brfalse.s loc_2299
0x2281  ldarg.s  5
0x2283  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2288  ldc.i4.0
0x2289  ble.s    loc_2299
0x228b  ldloc.s  4
0x228d  ldstr    aSubjectid// "subjectid"
0x2292  ldarg.s  5
0x2294  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x2299  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::.ctor()
0x229e  stloc.s  7
0x22a0  ldloc.s  7
0x22a2  ldc.i4.8
0x22a3  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::set_Type(int32)
0x22a8  ldloc.s  7
0x22aa  ldloc.2
0x22ab  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0x22b0  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::set_ID(string)
0x22b5  ldloc.s  4
0x22b7  ldstr    aOwnerid// "ownerid"
0x22bc  ldloc.s  7
0x22be  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x22c3  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x22c8  stloc.s  8
0x22ca  ldloc.s  4
0x22cc  ldloc.s  8
0x22ce  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Create(valuetype [mscorlib]System.Guid)
0x22d3  ldloc.0
0x22d4  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x22d9  ldarg.1
0x22da  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x22df  ldloca.s 9
0x22e1  ldarg.0
0x22e2  call     instance void [mscorlib]System.Guid::.ctor(string)
0x22e7  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x22ec  ldloc.0
0x22ed  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x22f2  dup
0x22f3  ldstr    aActivityid// "activityid"
0x22f8  ldloc.s  9
0x22fa  box      [mscorlib]System.Guid
0x22ff  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x2304  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::.ctor()
0x2309  stloc.s  0xA
0x230b  ldloc.s  0xA
0x230d  ldloc.s  4
0x230f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x2314  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::set_ID(string)
0x2319  ldloc.s  0xA
0x231b  ldc.i4.s 0x70
0x231d  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::set_Type(int32)
0x2322  dup
0x2323  ldstr    aRegardingobjec// "regardingobjectid"
0x2328  ldloc.s  0xA
0x232a  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x232f  ldc.i4.0
0x2330  ldloc.s  8
0x2332  ldloc.0
0x2333  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Update(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy, bool, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2338  ldloc.s  4
0x233a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x233f  ret
```
