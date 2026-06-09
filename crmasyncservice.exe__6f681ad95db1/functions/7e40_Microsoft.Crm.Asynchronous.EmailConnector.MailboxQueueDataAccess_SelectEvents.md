# Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::SelectEvents

- ea: `0x7e40`
- end: `0x7eb8`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::SelectEvents`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x4e40`
- `0x7e40`
- `0x7ec0`
- `0x8b60`

## pseudocode

```c

```

## disassembly

```asm
0x7e40  ldarg.0
0x7e41  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x7e46  call     bool Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::IsMailboxQueueEnabled(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration orgConfiguration)
0x7e4b  brtrue.s loc_7E53
0x7e4d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager>::.ctor()
0x7e52  ret
0x7e53  ldarg.0
0x7e54  ldarg.1
0x7e55  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.MailBoxEntityWrapper> Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::SelectMailboxes(int32 numberOfMailboxes)
0x7e5a  stloc.0
0x7e5b  ldloc.0
0x7e5c  brfalse.s loc_7E66
0x7e5e  ldloc.0
0x7e5f  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.MailBoxEntityWrapper>::get_Count()
0x7e64  brtrue.s loc_7E6C
0x7e66  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager>::.ctor()
0x7e6b  ret
0x7e6c  ldarg.0
0x7e6d  ldloc.0
0x7e6e  call     instance class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager> Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::GetEvents(class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.MailBoxEntityWrapper> mailBoxEntityWrappers)
0x7e73  stloc.1
0x7e74  ldarg.0
0x7e75  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x7e7a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x7e7f  ldc.i4.s 0x15
0x7e81  ldstr    a0SelectingUpTo// "{0}: Selecting up to {1} operations - {"...
0x7e86  ldc.i4.3
0x7e87  newarr   [mscorlib]System.Object
0x7e8c  dup
0x7e8d  ldc.i4.0
0x7e8e  ldarg.0
0x7e8f  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_queueManager
0x7e94  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x7e99  stelem.ref
0x7e9a  dup
0x7e9b  ldc.i4.1
0x7e9c  ldarg.1
0x7e9d  box      [mscorlib]System.Int32
0x7ea2  stelem.ref
0x7ea3  dup
0x7ea4  ldc.i4.2
0x7ea5  ldloc.1
0x7ea6  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager>::get_Count()
0x7eab  box      [mscorlib]System.Int32
0x7eb0  stelem.ref
0x7eb1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7eb6  ldloc.1
0x7eb7  ret
```
