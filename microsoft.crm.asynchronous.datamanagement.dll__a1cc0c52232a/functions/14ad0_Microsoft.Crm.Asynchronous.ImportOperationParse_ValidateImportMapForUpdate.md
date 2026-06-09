# Microsoft.Crm.Asynchronous.ImportOperationParse::ValidateImportMapForUpdate

- ea: `0x14ad0`
- end: `0x14bb7`
- name: `Microsoft.Crm.Asynchronous.ImportOperationParse::ValidateImportMapForUpdate`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14370`

## callees

- `0x8f10`
- `0x8f40`
- `0x8f60`
- `0xb0e0`
- `0x14ad0`

## string_xrefs

- `0x14ba4`: `Need to provide a proper import map for update job to start`

## pseudocode

```c

```

## disassembly

```asm
0x14ad0  ldarg.0
0x14ad1  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0x14ad6  callvirt instance int32 Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportMode()
0x14adb  ldc.i4.1
0x14adc  beq.s    loc_14AE0
0x14ade  ldnull
0x14adf  ret
0x14ae0  ldc.i4.0
0x14ae1  stloc.0
0x14ae2  ldarg.0
0x14ae3  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0x14ae8  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportFileIdToImportFileObjectDictionary()
0x14aed  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x14af2  stloc.1
0x14af3  br.s     loc_14B6D
0x14af5  ldloca.s 1
0x14af7  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x14afc  stloc.2
0x14afd  ldloca.s 2
0x14aff  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Value()
0x14b04  stloc.3
0x14b05  ldloc.3
0x14b06  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x14b0b  ldstr    aImportmapid// "importmapid"
0x14b10  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x14b15  brfalse.s loc_14B69
0x14b17  ldloc.3
0x14b18  ldstr    aImportmapid// "importmapid"
0x14b1d  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x14b22  brfalse.s loc_14B69
0x14b24  ldloc.3
0x14b25  ldstr    aImportmapid// "importmapid"
0x14b2a  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x14b2f  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x14b34  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x14b39  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x14b3e  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x14b43  brtrue.s loc_14B69
0x14b45  ldloc.3
0x14b46  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x14b4b  ldstr    aUsesystemmap// "usesystemmap"
0x14b50  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x14b55  brfalse.s loc_14B6D
0x14b57  ldloc.3
0x14b58  ldstr    aUsesystemmap// "usesystemmap"
0x14b5d  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x14b62  unbox.any [mscorlib]System.Boolean
0x14b67  brfalse.s loc_14B6D
0x14b69  ldc.i4.1
0x14b6a  stloc.0
0x14b6b  leave.s  loc_14B89
0x14b6d  ldloca.s 1
0x14b6f  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::MoveNext()
0x14b74  brtrue   loc_14AF5
0x14b79  leave.s  loc_14B89
0x14b7b  ldloca.s 1
0x14b7d  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>
0x14b83  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14b88  endfinally
0x14b89  ldloc.0
0x14b8a  brfalse.s loc_14BB5
0x14b8c  ldarg.0
0x14b8d  ldarg.0
0x14b8e  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0x14b93  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportId()
0x14b98  ldc.i4.5
0x14b99  ldc.i4.1
0x14b9a  call     instance void Microsoft.Crm.Asynchronous.ImportOperation::SetImportStatus(valuetype [mscorlib]System.Guid importId, int32 importStatus, bool cleanupImportFilesContent)
0x14b9f  ldc.i4   0x8004F600
0x14ba4  ldstr    aNeedToProvideA// "Need to provide a proper import map for"...
0x14ba9  ldc.i4.0
0x14baa  newarr   [mscorlib]System.Object
0x14baf  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult::.ctor(int32, string, object[])
0x14bb4  ret
0x14bb5  ldnull
0x14bb6  ret
```
