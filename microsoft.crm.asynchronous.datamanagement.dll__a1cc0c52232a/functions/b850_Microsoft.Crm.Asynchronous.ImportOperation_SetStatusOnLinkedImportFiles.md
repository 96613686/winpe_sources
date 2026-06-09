# Microsoft.Crm.Asynchronous.ImportOperation::SetStatusOnLinkedImportFiles

- ea: `0xb850`
- end: `0xb8c1`
- name: `Microsoft.Crm.Asynchronous.ImportOperation::SetStatusOnLinkedImportFiles`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0xb0e0`

## callees

- `0x3d00`
- `0xb850`
- `0xb8d0`

## pseudocode

```c

```

## disassembly

```asm
0xb850  ldarg.0
0xb851  ldarg.1
0xb852  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection Microsoft.Crm.Asynchronous.ImportOperation::RetrieveNotCompletedImportFiles(valuetype [mscorlib]System.Guid importId)
0xb857  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0xb85c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0xb861  stloc.0
0xb862  br.s     loc_B8AC
0xb864  ldloc.0
0xb865  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0xb86a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0xb86f  stloc.1
0xb870  ldarg.0
0xb871  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ImportOperation::_asyncEvent
0xb876  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xb87b  ldc.i4.s 0x18
0xb87d  ldstr    aUpdatingTheSta// "Updating the status of importfile {0} t"...
0xb882  ldc.i4.2
0xb883  newarr   [mscorlib]System.Object
0xb888  dup
0xb889  ldc.i4.0
0xb88a  ldloc.1
0xb88b  box      [mscorlib]System.Guid
0xb890  stelem.ref
0xb891  dup
0xb892  ldc.i4.1
0xb893  ldarg.2
0xb894  box      [mscorlib]System.Int32
0xb899  stelem.ref
0xb89a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xb89f  ldarg.0
0xb8a0  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0xb8a5  ldloc.1
0xb8a6  ldarg.2
0xb8a7  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::SetImportFileStatusToComplete(valuetype [mscorlib]System.Guid importFileId, int32 status)
0xb8ac  ldloc.0
0xb8ad  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xb8b2  brtrue.s loc_B864
0xb8b4  leave.s  loc_B8C0
0xb8b6  ldloc.0
0xb8b7  brfalse.s loc_B8BF
0xb8b9  ldloc.0
0xb8ba  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb8bf  endfinally
0xb8c0  ret
```
