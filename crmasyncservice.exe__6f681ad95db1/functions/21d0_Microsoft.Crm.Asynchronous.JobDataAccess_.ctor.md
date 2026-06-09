# Microsoft.Crm.Asynchronous.JobDataAccess::.ctor

- ea: `0x21d0`
- end: `0x2201`
- name: `Microsoft.Crm.Asynchronous.JobDataAccess::.ctor`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x21a0`

## pseudocode

```c

```

## disassembly

```asm
0x21d0  ldarg.0
0x21d1  ldnull
0x21d2  call     instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration)
0x21d7  ldarg.0
0x21d8  ldarg.1
0x21d9  stfld    class Microsoft.Crm.Asynchronous.JobManager Microsoft.Crm.Asynchronous.JobDataAccess::_jobManager
0x21de  ldarg.0
0x21df  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x21e4  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::set_OrganizationId(valuetype [mscorlib]System.Guid)
0x21e9  ldarg.0
0x21ea  ldarg.0
0x21eb  ldftn    instance string Microsoft.Crm.Asynchronous.JobDataAccess::<.ctor>b__2_0()
0x21f1  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0x21f6  newobj   instance void class [mscorlib]System.Lazy`1<string>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x21fb  stfld    class [mscorlib]System.Lazy`1<string> Microsoft.Crm.Asynchronous.JobDataAccess::validOrgIdsInClause
0x2200  ret
```
