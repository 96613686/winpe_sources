# Microsoft.Crm.CrmLive.Provisioning.AddInitialUserToConfigDBAction::RetrieveDirectoryObjectIdLegacy

- ea: `0x2a90`
- end: `0x2b14`
- name: `Microsoft.Crm.CrmLive.Provisioning.AddInitialUserToConfigDBAction::RetrieveDirectoryObjectIdLegacy`
- size: `132`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x2a30`

## callees

- `0x2a90`

## string_xrefs

- `0x2ad0`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\AddInitialUserToConfigDBAction.cs`
- `0x2aa9`: `DirectoryObjectState`
- `0x2acb`: `RetrieveDirectoryObjectIdLegacy`

## pseudocode

```c

```

## disassembly

```asm
0x2a90  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x2a95  stloc.0
0x2a96  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x2a9b  stloc.1
0x2a9c  ldloc.1
0x2a9d  ldstr    aUserprincipaln// "UserPrincipalName"
0x2aa2  ldarg.0
0x2aa3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2aa8  ldloc.0
0x2aa9  ldstr    aDirectoryobjec_0// "DirectoryObjectState"
0x2aae  ldc.i4.1
0x2aaf  newarr   [mscorlib]System.String
0x2ab4  dup
0x2ab5  ldc.i4.0
0x2ab6  ldstr    aObjectid_1// "ObjectId"
0x2abb  stelem.ref
0x2abc  ldc.i4.1
0x2abd  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x2ac2  dup
0x2ac3  ldc.i4.0
0x2ac4  ldloc.1
0x2ac5  stelem.ref
0x2ac6  ldc.i4   0xDE
0x2acb  ldstr    aRetrievedirect// "RetrieveDirectoryObjectIdLegacy"
0x2ad0  ldstr    aDDbsShDccm2110_1// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x2ad5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x2ada  stloc.2
0x2adb  ldloc.2
0x2adc  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0x2ae1  brfalse.s loc_2AEB
0x2ae3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2ae8  stloc.3
0x2ae9  leave.s  loc_2B12
0x2aeb  ldloc.2
0x2aec  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x2af1  call     T0x2B000017
0x2af6  ldstr    aObjectid_1// "ObjectId"
0x2afb  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x2b00  unbox.any [mscorlib]System.Guid
0x2b05  stloc.3
0x2b06  leave.s  loc_2B12
0x2b08  ldloc.0
0x2b09  brfalse.s loc_2B11
0x2b0b  ldloc.0
0x2b0c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2b11  endfinally
0x2b12  ldloc.3
0x2b13  ret
```
