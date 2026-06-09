# Microsoft.Crm.StorageNotificationUtility::RetrieveOrganizationDetail

- ea: `0x251f0`
- end: `0x2525e`
- name: `Microsoft.Crm.StorageNotificationUtility::RetrieveOrganizationDetail`
- size: `110`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x24690`
- `0x24d70`
- `0x25020`

## callees

- `0x251f0`

## string_xrefs

- `0x25229`: `Org not found in organization table, assuming deleted.`

## pseudocode

```c

```

## disassembly

```asm
0x251f0  ldnull
0x251f1  stloc.0
0x251f2  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x251f7  stloc.1
0x251f8  ldloc.1
0x251f9  ldstr    aOrganization// "Organization"
0x251fe  ldarg.0
0x251ff  box      [mscorlib]System.Guid
0x25204  ldc.i4.1
0x25205  newarr   [mscorlib]System.String
0x2520a  dup
0x2520b  ldc.i4.0
0x2520c  ldarg.1
0x2520d  stelem.ref
0x2520e  ldc.i4   0x2AE
0x25213  ldstr    aRetrieveorgani_1// "RetrieveOrganizationDetail"
0x25218  ldstr    aDA1SSrcSharedS_4// "D:\\a\\1\\s\\src\\Shared\\Server\\Utils"...
0x2521d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveById(string, object, string[], int32, string, string)
0x25222  stloc.2
0x25223  ldloc.2
0x25224  brtrue.s loc_2523D
0x25226  ldarg.0
0x25227  ldc.i4.s 0x14
0x25229  ldstr    aOrgNotFoundInO// "Org not found in organization table, as"...
0x2522e  ldc.i4.0
0x2522f  newarr   [mscorlib]System.Object
0x25234  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x25239  ldloc.0
0x2523a  stloc.3
0x2523b  leave.s  loc_2525C
0x2523d  ldloc.2
0x2523e  ldarg.1
0x2523f  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0x25244  brfalse.s loc_2524E
0x25246  ldloc.2
0x25247  ldarg.1
0x25248  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x2524d  stloc.0
0x2524e  leave.s  loc_2525A
0x25250  ldloc.1
0x25251  brfalse.s loc_25259
0x25253  ldloc.1
0x25254  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x25259  endfinally
0x2525a  ldloc.0
0x2525b  ret
0x2525c  ldloc.3
0x2525d  ret
```
