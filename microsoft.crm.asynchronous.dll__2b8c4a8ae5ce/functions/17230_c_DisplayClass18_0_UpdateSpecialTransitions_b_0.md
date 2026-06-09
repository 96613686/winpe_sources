# <>c__DisplayClass18_0::<UpdateSpecialTransitions>b__0

- ea: `0x17230`
- end: `0x17272`
- name: `<>c__DisplayClass18_0::<UpdateSpecialTransitions>b__0`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0xd5a0`
- `0xd780`
- `0x17230`
- `0x17b70`

## pseudocode

```c

```

## disassembly

```asm
0x17230  ldarg.0
0x17231  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess <>c__DisplayClass18_0::<>4__this
0x17236  ldarg.0
0x17237  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass18_0::selectCommand
0x1723c  ldarg.0
0x1723d  ldfld    class RecordProcessor <>c__DisplayClass18_0::<>9__1
0x17242  dup
0x17243  brtrue.s loc_1725B
0x17245  pop
0x17246  ldarg.0
0x17247  ldarg.0
0x17248  ldftn    instance void <>c__DisplayClass18_0::<UpdateSpecialTransitions>b__1(object[] values)
0x1724e  newobj   instance void RecordProcessor::.ctor(object object, native int method)
0x17253  dup
0x17254  stloc.0
0x17255  stfld    class RecordProcessor <>c__DisplayClass18_0::<>9__1
0x1725a  ldloc.0
0x1725b  ldarg.0
0x1725c  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess <>c__DisplayClass18_0::<>4__this
0x17261  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x17266  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x1726b  call     instance int32 Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo command, class RecordProcessor recordProcessor, valuetype [mscorlib]System.Guid inputOrganizationId)
0x17270  pop
0x17271  ret
```
