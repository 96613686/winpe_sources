# Microsoft.Crm.Metadata.Generators.AppModuleGenerator::HandleDescriptorMetadataRequest

- ea: `0x3d9a0`
- end: `0x3dd2b`
- name: `Microsoft.Crm.Metadata.Generators.AppModuleGenerator::HandleDescriptorMetadataRequest`
- size: `907`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x3d910`

## callees

- `0x383b0`
- `0x3d9a0`
- `0x3de10`
- `0x45510`

## string_xrefs

- `0x3db32`: `componentstate`
- `0x3db8a`: `componentstate`
- `0x3dc09`: `componentstate`
- `0x3dc88`: `componentstate`
- `0x3db99`: `descriptor`
- `0x3dbb6`: `descriptor`
- `0x3dc18`: `descriptor`
- `0x3dc35`: `descriptor`
- `0x3dc97`: `descriptor`
- `0x3da2c`: `AppModuleGenerator.HandleDescriptorMetadataRequest(): [appModuleKey:{0}],[descriptor:{1}]`
- `0x3da5f`: `AppModuleGenerator.HandleDescriptorMetadataRequest(): Empty descriptor found for Legacy AppModule.`
- `0x3daa6`: `AppModuleGenerator.HandleDescriptorMetadataRequest(): Request not current Origanization [organizationid:{0}],[generatorkey:{1}].`
- `0x3daf4`: `AppModuleGenerator.HandleDescriptorMetadataRequest(): Error while generating clientMetaData for default app. Exception:{0}`
- `0x3db73`: `AppModuleGenerator.HandleDescriptorMetadataRequest(): [appModuleKey:{0}],[componentstate:{1}],[descriptor:{2}]`
- `0x3dbf2`: `AppModuleGenerator.HandleDescriptorMetadataRequest(): [appModuleKey:{0}],[componentstate:{1}],[descriptor:{2}]`
- `0x3dc5b`: `AppModuleGenerator.HandleDescriptorMetadataRequest(): Error while generating clientMetaData for appmodule with [appmoduleid:{0}][appmoduleidunique:{1}][componentstate:{2}][descriptor:{3}]. Exception:{4}`
- `0x3dcbc`: `AppModuleGenerator.HandleDescriptorMetadataRequest(): UnKnown Generator Data type: {0}`
- `0x3dcf0`: `AppModuleGenerator.HandleDescriptorMetadataRequest(): Exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x3d9a0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3d9a5  ldstr    aAppmodulegener_0// "AppModuleGenerator_Online_BEGIN_{0}.Gen"...
0x3d9aa  ldc.i4.1
0x3d9ab  newarr   [mscorlib]System.Object
0x3d9b0  dup
0x3d9b1  ldc.i4.0
0x3d9b2  ldarg.0
0x3d9b3  stelem.ref
0x3d9b4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3d9b9  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x3d9be  ldarg.1
0x3d9bf  callvirt instance object Microsoft.Crm.Metadata.Generators.CandidateItem::get_Data()
0x3d9c4  isinst   Microsoft.Crm.Metadata.OtherItem
0x3d9c9  brfalse  loc_3DB13
0x3d9ce  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3d9d3  stloc.0
0x3d9d4  ldarg.1
0x3d9d5  callvirt instance object Microsoft.Crm.Metadata.Generators.CandidateItem::get_Data()
0x3d9da  castclass Microsoft.Crm.Metadata.OtherItem
0x3d9df  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Metadata.OtherItem::get_CandidateIds()
0x3d9e4  ldc.i4.0
0x3d9e5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Item(!!T0)
0x3d9ea  stloc.0
0x3d9eb  ldarg.s  4
0x3d9ed  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3d9f2  ldloc.0
0x3d9f3  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3d9f8  brfalse  loc_3DA9D
0x3d9fd  ldarg.s  4
0x3d9ff  call     string Microsoft.Crm.Metadata.Generators.AppModuleGenerator::GetAppModuleDescriptor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3da04  stloc.1
0x3da05  ldloc.1
0x3da06  brfalse.s loc_3DA56
0x3da08  ldstr    aLegacyappmodul// "LegacyAppModule"
0x3da0d  stloc.2
0x3da0e  ldarg.2
0x3da0f  ldloc.2
0x3da10  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>>::ContainsKey(var<u1>)
0x3da15  brtrue.s loc_3DA23
0x3da17  ldarg.2
0x3da18  ldloc.2
0x3da19  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x3da1e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>>::set_Item(var<u1>, !!T0)
0x3da23  ldarg.s  4
0x3da25  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3da2a  ldc.i4.s 0x47
0x3da2c  ldstr    aAppmodulegener_1// "AppModuleGenerator.HandleDescriptorMeta"...
0x3da31  ldc.i4.2
0x3da32  newarr   [mscorlib]System.Object
0x3da37  dup
0x3da38  ldc.i4.0
0x3da39  ldloc.2
0x3da3a  stelem.ref
0x3da3b  dup
0x3da3c  ldc.i4.1
0x3da3d  ldloc.1
0x3da3e  stelem.ref
0x3da3f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3da44  ldarg.2
0x3da45  ldloc.2
0x3da46  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>>::get_Item(void)
0x3da4b  ldloc.1
0x3da4c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3da51  br       loc_3DAE2
0x3da56  ldarg.s  4
0x3da58  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3da5d  ldc.i4.s 0x47
0x3da5f  ldstr    aAppmodulegener_2// "AppModuleGenerator.HandleDescriptorMeta"...
0x3da64  ldc.i4.2
0x3da65  newarr   [mscorlib]System.Object
0x3da6a  dup
0x3da6b  ldc.i4.0
0x3da6c  ldarg.s  4
0x3da6e  brtrue.s loc_3DA7B
0x3da70  ldloca.s 3
0x3da72  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x3da78  ldloc.3
0x3da79  br.s     loc_3DA87
0x3da7b  ldarg.s  4
0x3da7d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3da82  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x3da87  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x3da8c  stelem.ref
0x3da8d  dup
0x3da8e  ldc.i4.1
0x3da8f  ldloc.0
0x3da90  box      [mscorlib]System.Guid
0x3da95  stelem.ref
0x3da96  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3da9b  br.s     loc_3DAE2
0x3da9d  ldarg.s  4
0x3da9f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3daa4  ldc.i4.s 0x47
0x3daa6  ldstr    aAppmodulegener_3// "AppModuleGenerator.HandleDescriptorMeta"...
0x3daab  ldc.i4.2
0x3daac  newarr   [mscorlib]System.Object
0x3dab1  dup
0x3dab2  ldc.i4.0
0x3dab3  ldarg.s  4
0x3dab5  brtrue.s loc_3DAC2
0x3dab7  ldloca.s 3
0x3dab9  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x3dabf  ldloc.3
0x3dac0  br.s     loc_3DACE
0x3dac2  ldarg.s  4
0x3dac4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3dac9  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x3dace  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x3dad3  stelem.ref
0x3dad4  dup
0x3dad5  ldc.i4.1
0x3dad6  ldloc.0
0x3dad7  box      [mscorlib]System.Guid
0x3dadc  stelem.ref
0x3dadd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3dae2  leave    loc_3DCE1
0x3dae7  stloc.s  4
0x3dae9  ldloc.s  4
0x3daeb  ldarg.s  4
0x3daed  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3daf2  ldc.i4.s 0x47
0x3daf4  ldstr    aAppmodulegener_4// "AppModuleGenerator.HandleDescriptorMeta"...
0x3daf9  ldc.i4.1
0x3dafa  newarr   [mscorlib]System.Object
0x3daff  dup
0x3db00  ldc.i4.0
0x3db01  ldloc.s  4
0x3db03  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3db08  stelem.ref
0x3db09  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3db0e  leave    loc_3DCE1
0x3db13  ldarg.1
0x3db14  callvirt instance object Microsoft.Crm.Metadata.Generators.CandidateItem::get_Data()
0x3db19  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x3db1e  brfalse  loc_3DCB3
0x3db23  ldarg.1
0x3db24  callvirt instance object Microsoft.Crm.Metadata.Generators.CandidateItem::get_Data()
0x3db29  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x3db2e  stloc.s  5
0x3db30  ldloc.s  5
0x3db32  ldstr    aComponentstate_0// "componentstate"
0x3db37  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3db3c  callvirt instance string [mscorlib]System.Object::ToString()
0x3db41  ldstr    a1// "1"
0x3db46  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3db4b  brfalse.s loc_3DBCC
0x3db4d  ldarg.2
0x3db4e  ldsfld   string Microsoft.Crm.Metadata.Generators.AppModuleGenerator::appModuleUnpublishedKey
0x3db53  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>>::ContainsKey(var<u1>)
0x3db58  brtrue.s loc_3DB6A
0x3db5a  ldarg.2
0x3db5b  ldsfld   string Microsoft.Crm.Metadata.Generators.AppModuleGenerator::appModuleUnpublishedKey
0x3db60  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x3db65  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>>::set_Item(var<u1>, !!T0)
0x3db6a  ldarg.s  4
0x3db6c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3db71  ldc.i4.s 0x47
0x3db73  ldstr    aAppmodulegener_5// "AppModuleGenerator.HandleDescriptorMeta"...
0x3db78  ldc.i4.3
0x3db79  newarr   [mscorlib]System.Object
0x3db7e  dup
0x3db7f  ldc.i4.0
0x3db80  ldsfld   string Microsoft.Crm.Metadata.Generators.AppModuleGenerator::appModuleUnpublishedKey
0x3db85  stelem.ref
0x3db86  dup
0x3db87  ldc.i4.1
0x3db88  ldloc.s  5
0x3db8a  ldstr    aComponentstate_0// "componentstate"
0x3db8f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3db94  stelem.ref
0x3db95  dup
0x3db96  ldc.i4.2
0x3db97  ldloc.s  5
0x3db99  ldstr    aDescriptor// "descriptor"
0x3db9e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3dba3  stelem.ref
0x3dba4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3dba9  ldarg.2
0x3dbaa  ldsfld   string Microsoft.Crm.Metadata.Generators.AppModuleGenerator::appModuleUnpublishedKey
0x3dbaf  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>>::get_Item(void)
0x3dbb4  ldloc.s  5
0x3dbb6  ldstr    aDescriptor// "descriptor"
0x3dbbb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3dbc0  callvirt instance string [mscorlib]System.Object::ToString()
0x3dbc5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3dbca  br.s     loc_3DC49
0x3dbcc  ldarg.2
0x3dbcd  ldsfld   string Microsoft.Crm.Metadata.Generators.AppModuleGenerator::appModulePublishedKey
0x3dbd2  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>>::ContainsKey(var<u1>)
0x3dbd7  brtrue.s loc_3DBE9
0x3dbd9  ldarg.2
0x3dbda  ldsfld   string Microsoft.Crm.Metadata.Generators.AppModuleGenerator::appModulePublishedKey
0x3dbdf  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x3dbe4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>>::set_Item(var<u1>, !!T0)
0x3dbe9  ldarg.s  4
0x3dbeb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3dbf0  ldc.i4.s 0x47
0x3dbf2  ldstr    aAppmodulegener_5// "AppModuleGenerator.HandleDescriptorMeta"...
0x3dbf7  ldc.i4.3
0x3dbf8  newarr   [mscorlib]System.Object
0x3dbfd  dup
0x3dbfe  ldc.i4.0
0x3dbff  ldsfld   string Microsoft.Crm.Metadata.Generators.AppModuleGenerator::appModuleUnpublishedKey
0x3dc04  stelem.ref
0x3dc05  dup
0x3dc06  ldc.i4.1
0x3dc07  ldloc.s  5
0x3dc09  ldstr    aComponentstate_0// "componentstate"
0x3dc0e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3dc13  stelem.ref
0x3dc14  dup
0x3dc15  ldc.i4.2
0x3dc16  ldloc.s  5
0x3dc18  ldstr    aDescriptor// "descriptor"
0x3dc1d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3dc22  stelem.ref
0x3dc23  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3dc28  ldarg.2
0x3dc29  ldsfld   string Microsoft.Crm.Metadata.Generators.AppModuleGenerator::appModulePublishedKey
0x3dc2e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>>::get_Item(void)
0x3dc33  ldloc.s  5
0x3dc35  ldstr    aDescriptor// "descriptor"
0x3dc3a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3dc3f  callvirt instance string [mscorlib]System.Object::ToString()
0x3dc44  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3dc49  leave    loc_3DCE1
0x3dc4e  stloc.s  6
0x3dc50  ldloc.s  6
0x3dc52  ldarg.s  4
0x3dc54  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3dc59  ldc.i4.s 0x47
0x3dc5b  ldstr    aAppmodulegener_6// "AppModuleGenerator.HandleDescriptorMeta"...
0x3dc60  ldc.i4.5
0x3dc61  newarr   [mscorlib]System.Object
0x3dc66  dup
0x3dc67  ldc.i4.0
0x3dc68  ldloc.s  5
0x3dc6a  ldstr    aAppmoduleid// "appmoduleid"
0x3dc6f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3dc74  stelem.ref
0x3dc75  dup
0x3dc76  ldc.i4.1
0x3dc77  ldloc.s  5
0x3dc79  ldstr    aAppmoduleiduni// "appmoduleidunique"
0x3dc7e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3dc83  stelem.ref
0x3dc84  dup
0x3dc85  ldc.i4.2
0x3dc86  ldloc.s  5
0x3dc88  ldstr    aComponentstate_0// "componentstate"
0x3dc8d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3dc92  stelem.ref
0x3dc93  dup
0x3dc94  ldc.i4.3
0x3dc95  ldloc.s  5
0x3dc97  ldstr    aDescriptor// "descriptor"
0x3dc9c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3dca1  stelem.ref
0x3dca2  dup
0x3dca3  ldc.i4.4
0x3dca4  ldloc.s  6
0x3dca6  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3dcab  stelem.ref
0x3dcac  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3dcb1  leave.s  loc_3DCE1
0x3dcb3  ldarg.s  4
0x3dcb5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3dcba  ldc.i4.s 0x47
0x3dcbc  ldstr    aAppmodulegener_7// "AppModuleGenerator.HandleDescriptorMeta"...
0x3dcc1  ldc.i4.1
0x3dcc2  newarr   [mscorlib]System.Object
0x3dcc7  dup
0x3dcc8  ldc.i4.0
0x3dcc9  ldarg.1
0x3dcca  callvirt instance object Microsoft.Crm.Metadata.Generators.CandidateItem::get_Data()
0x3dccf  dup
0x3dcd0  brtrue.s loc_3DCD6
0x3dcd2  pop
0x3dcd3  ldnull
0x3dcd4  br.s     loc_3DCDB
0x3dcd6  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3dcdb  stelem.ref
0x3dcdc  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3dce1  leave.s  loc_3DD0C
0x3dce3  stloc.s  7
0x3dce5  ldloc.s  7
0x3dce7  ldarg.s  4
0x3dce9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3dcee  ldc.i4.s 0x47
0x3dcf0  ldstr    aAppmodulegener_8// "AppModuleGenerator.HandleDescriptorMeta"...
0x3dcf5  ldc.i4.1
0x3dcf6  newarr   [mscorlib]System.Object
0x3dcfb  dup
0x3dcfc  ldc.i4.0
0x3dcfd  ldloc.s  7
0x3dcff  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3dd04  stelem.ref
0x3dd05  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3dd0a  leave.s  loc_3DD0C
0x3dd0c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
  ... truncated ...
```
