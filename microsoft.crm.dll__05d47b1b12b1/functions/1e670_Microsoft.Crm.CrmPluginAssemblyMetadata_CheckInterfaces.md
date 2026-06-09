# Microsoft.Crm.CrmPluginAssemblyMetadata::CheckInterfaces

- ea: `0x1e670`
- end: `0x1e80d`
- name: `Microsoft.Crm.CrmPluginAssemblyMetadata::CheckInterfaces`
- size: `413`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1e4f0`

## callees

- `0x192d0`
- `0x19330`
- `0x1e140`
- `0x1e670`
- `0x1e810`
- `0x1f270`
- `0x1f2c0`
- `0x1f2f0`

## string_xrefs

- `0x1e77d`: `Microsoft.Crm.Sdk.IPlugin`
- `0x1e7ab`: `CheckInterfaces: IsV4PluginType`
- `0x1e7bf`: `Microsoft.Xrm.Sdk.IPlugin`
- `0x1e7ed`: `CheckInterfaces: IsV5PluginType`

## pseudocode

```c

```

## disassembly

```asm
0x1e670  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1e675  ldc.i4.s 0x14
0x1e677  ldstr    aCheckinterface// "CheckInterfaces: crmType.TypeDef: {0}"
0x1e67c  ldc.i4.1
0x1e67d  newarr   [mscorlib]System.Object
0x1e682  dup
0x1e683  ldc.i4.0
0x1e684  ldarg.0
0x1e685  ldarg.1
0x1e686  callvirt instance unsigned int32 Microsoft.Crm.CrmPluginTypeMetadata::get_TypeDef()
0x1e68b  call     instance string Microsoft.Crm.CrmPluginAssemblyMetadata::Hex(unsigned int32 value)
0x1e690  stelem.ref
0x1e691  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1e696  ldc.i4   0x1000
0x1e69b  newarr   [mscorlib]System.UInt32
0x1e6a0  stloc.0
0x1e6a1  ldc.i4   0x1000
0x1e6a6  stloc.1
0x1e6a7  ldarg.0
0x1e6a8  ldfld    class Microsoft.Crm.IMetaDataImport Microsoft.Crm.CrmPluginAssemblyMetadata::_mdaImport
0x1e6ad  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x1e6b2  stloc.2
0x1e6b3  ldloca.s 2
0x1e6b5  ldarg.1
0x1e6b6  callvirt instance unsigned int32 Microsoft.Crm.CrmPluginTypeMetadata::get_TypeDef()
0x1e6bb  ldloc.0
0x1e6bc  ldloc.1
0x1e6bd  ldloca.s 1
0x1e6bf  callvirt instance void Microsoft.Crm.IMetaDataImport::EnumInterfaceImpls(native int& hcorEnum, unsigned int32 mdTypeDef, [hasfieldmarshal] unsigned int32[] mdInterfaceImpl, unsigned int32 max, [out] unsigned int32& count)
0x1e6c4  ldloc.1
0x1e6c5  ldc.i4.1
0x1e6c6  bge.un.s loc_1E6E8
0x1e6c8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1e6cd  ldc.i4.s 0x14
0x1e6cf  ldstr    a0_0// "{0}"
0x1e6d4  ldc.i4.1
0x1e6d5  newarr   [mscorlib]System.Object
0x1e6da  dup
0x1e6db  ldc.i4.0
0x1e6dc  ldstr    aCheckinterface_0// "CheckInterfaces: no interfaces found"
0x1e6e1  stelem.ref
0x1e6e2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1e6e7  ret
0x1e6e8  ldc.i4.0
0x1e6e9  stloc.3
0x1e6ea  br       loc_1E803
0x1e6ef  ldarg.0
0x1e6f0  ldfld    class Microsoft.Crm.IMetaDataImport Microsoft.Crm.CrmPluginAssemblyMetadata::_mdaImport
0x1e6f5  ldloc.0
0x1e6f6  ldloc.3
0x1e6f7  ldelem.u4
0x1e6f8  ldloca.s 4
0x1e6fa  ldloca.s 5
0x1e6fc  callvirt instance void Microsoft.Crm.IMetaDataImport::GetInterfaceImplProps(unsigned int32 mdTypeDefMethod, [out] unsigned int32& mdTypeDefClass, [out] unsigned int32& mdTypeDefInterface)
0x1e701  ldarg.0
0x1e702  ldloc.s  5
0x1e704  ldloca.s 6
0x1e706  ldloca.s 7
0x1e708  ldloca.s 8
0x1e70a  ldloca.s 8
0x1e70c  call     instance void Microsoft.Crm.CrmPluginAssemblyMetadata::GetTypeProps(unsigned int32 token, [out] string& typeName, [out] unsigned int32& nextToken, [out] bool& isPublic, [out] bool& isAbstract)
0x1e711  ldloc.s  6
0x1e713  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1e718  brfalse.s loc_1E73E
0x1e71a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1e71f  ldc.i4.s 0x14
0x1e721  ldstr    a0_0// "{0}"
0x1e726  ldc.i4.1
0x1e727  newarr   [mscorlib]System.Object
0x1e72c  dup
0x1e72d  ldc.i4.0
0x1e72e  ldstr    aCheckinterface_1// "CheckInterfaces: no interface props fou"...
0x1e733  stelem.ref
0x1e734  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1e739  br       loc_1E7FF
0x1e73e  ldarg.0
0x1e73f  ldloc.s  7
0x1e741  ldloca.s 9
0x1e743  ldloca.s 0xA
0x1e745  ldloca.s 8
0x1e747  ldloca.s 8
0x1e749  call     instance void Microsoft.Crm.CrmPluginAssemblyMetadata::GetTypeProps(unsigned int32 token, [out] string& typeName, [out] unsigned int32& nextToken, [out] bool& isPublic, [out] bool& isAbstract)
0x1e74e  ldloc.s  9
0x1e750  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1e755  brfalse.s loc_1E77B
0x1e757  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1e75c  ldc.i4.s 0x14
0x1e75e  ldstr    a0_0// "{0}"
0x1e763  ldc.i4.1
0x1e764  newarr   [mscorlib]System.Object
0x1e769  dup
0x1e76a  ldc.i4.0
0x1e76b  ldstr    aCheckinterface_2// "CheckInterfaces: no module props found"
0x1e770  stelem.ref
0x1e771  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1e776  br       loc_1E7FF
0x1e77b  ldloc.s  6
0x1e77d  ldstr    aMicrosoftCrmSd// "Microsoft.Crm.Sdk.IPlugin"
0x1e782  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1e787  brfalse.s loc_1E7BD
0x1e789  ldloc.s  9
0x1e78b  ldstr    aMicrosoftCrmSd_0// "Microsoft.Crm.Sdk"
0x1e790  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1e795  brfalse.s loc_1E7BD
0x1e797  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1e79c  ldc.i4.s 0x14
0x1e79e  ldstr    a0_0// "{0}"
0x1e7a3  ldc.i4.1
0x1e7a4  newarr   [mscorlib]System.Object
0x1e7a9  dup
0x1e7aa  ldc.i4.0
0x1e7ab  ldstr    aCheckinterface_3// "CheckInterfaces: IsV4PluginType"
0x1e7b0  stelem.ref
0x1e7b1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1e7b6  ldarg.1
0x1e7b7  ldc.i4.1
0x1e7b8  callvirt instance void Microsoft.Crm.CrmPluginTypeMetadata::set_IsV4PluginType(bool value)
0x1e7bd  ldloc.s  6
0x1e7bf  ldstr    aMicrosoftXrmSd// "Microsoft.Xrm.Sdk.IPlugin"
0x1e7c4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1e7c9  brfalse.s loc_1E7FF
0x1e7cb  ldloc.s  9
0x1e7cd  ldstr    aMicrosoftXrmSd_0// "Microsoft.Xrm.Sdk"
0x1e7d2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1e7d7  brfalse.s loc_1E7FF
0x1e7d9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1e7de  ldc.i4.s 0x14
0x1e7e0  ldstr    a0_0// "{0}"
0x1e7e5  ldc.i4.1
0x1e7e6  newarr   [mscorlib]System.Object
0x1e7eb  dup
0x1e7ec  ldc.i4.0
0x1e7ed  ldstr    aCheckinterface_4// "CheckInterfaces: IsV5PluginType"
0x1e7f2  stelem.ref
0x1e7f3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1e7f8  ldarg.1
0x1e7f9  ldc.i4.1
0x1e7fa  callvirt instance void Microsoft.Crm.CrmPluginTypeMetadata::set_IsV5PluginType(bool value)
0x1e7ff  ldloc.3
0x1e800  ldc.i4.1
0x1e801  add
0x1e802  stloc.3
0x1e803  ldloc.3
0x1e804  conv.i8
0x1e805  ldloc.1
0x1e806  conv.u8
0x1e807  blt      loc_1E6EF
0x1e80c  ret
```
