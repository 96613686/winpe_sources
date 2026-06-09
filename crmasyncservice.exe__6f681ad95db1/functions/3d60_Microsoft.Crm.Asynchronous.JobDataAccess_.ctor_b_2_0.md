# Microsoft.Crm.Asynchronous.JobDataAccess::<.ctor>b__2_0

- ea: `0x3d60`
- end: `0x3d77`
- name: `Microsoft.Crm.Asynchronous.JobDataAccess::<.ctor>b__2_0`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x3850`
- `0x3e10`
- `0x4a10`

## pseudocode

```c

```

## disassembly

```asm
0x3d60  ldarg.0
0x3d61  ldarg.0
0x3d62  ldfld    class Microsoft.Crm.Asynchronous.JobManager Microsoft.Crm.Asynchronous.JobDataAccess::_jobManager
0x3d67  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.JobManager::get_ScaleGroupId()
0x3d6c  call     class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.JobDataAccessUtility::GetOrganizationsAvailableForMaintenance(valuetype [mscorlib]System.Guid scaleGroupId)
0x3d71  call     instance string Microsoft.Crm.Asynchronous.JobDataAccess::GetInClause(class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Guid> list)
0x3d76  ret
```
