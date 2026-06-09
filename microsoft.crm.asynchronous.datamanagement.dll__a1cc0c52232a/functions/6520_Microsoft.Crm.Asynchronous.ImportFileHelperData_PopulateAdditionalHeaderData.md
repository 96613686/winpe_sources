# Microsoft.Crm.Asynchronous.ImportFileHelperData::PopulateAdditionalHeaderData

- ea: `0x6520`
- end: `0x65c4`
- name: `Microsoft.Crm.Asynchronous.ImportFileHelperData::PopulateAdditionalHeaderData`
- size: `164`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xd1c0`
- `0xe130`
- `0x17670`
- `0x19b90`

## callees

- `0x3b80`
- `0x6520`
- `0x65d0`

## pseudocode

```c

```

## disassembly

```asm
0x6520  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor()
0x6525  stloc.0
0x6526  ldloc.0
0x6527  ldstr    aAdditionalhead// "additionalheaderrow"
0x652c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0x6531  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveRequest::.ctor()
0x6536  stloc.1
0x6537  ldloc.1
0x6538  ldloc.0
0x6539  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveRequest::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x653e  ldloc.1
0x653f  ldstr    aImportfile// "importfile"
0x6544  ldarg.0
0x6545  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportFileHelperData::_importFileId
0x654a  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x654f  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0x6554  ldarg.0
0x6555  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.ImportFileHelperData::_crmService
0x655a  ldloc.1
0x655b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x6560  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveResponse
0x6565  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveResponse::get_Entity()
0x656a  ldstr    aAdditionalhead// "additionalheaderrow"
0x656f  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetStringFromDynamicEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity de, string propertyName)
0x6574  stloc.2
0x6575  ldloc.2
0x6576  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x657b  brfalse.s loc_65AA
0x657d  ldarg.0
0x657e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x6583  stfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Asynchronous.ImportFileHelperData::_additionalHeaderColumns
0x6588  ldarg.0
0x6589  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor()
0x658e  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Asynchronous.ImportFileHelperData::_additionalHeaderColumnToParsedTableColumnIndexDictionary
0x6593  ldarg.0
0x6594  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x6599  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Asynchronous.ImportFileHelperData::_additionalHeaderColumnToParsedTableColumnDictionary
0x659e  ldarg.0
0x659f  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x65a4  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Asynchronous.ImportFileHelperData::_parsedTableColumnToAdditionalHeaderColumnDictionary
0x65a9  ret
0x65aa  ldloc.2
0x65ab  ldc.i4.1
0x65ac  newarr   [mscorlib]System.Char
0x65b1  dup
0x65b2  ldc.i4.0
0x65b3  ldc.i4.s 0x2C
0x65b5  stelem.i2
0x65b6  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x65bb  stloc.3
0x65bc  ldarg.0
0x65bd  ldloc.3
0x65be  call     instance void Microsoft.Crm.Asynchronous.ImportFileHelperData::PopulateAdditionalHeaderData(string[] additionalHeaderColumns)
0x65c3  ret
```
