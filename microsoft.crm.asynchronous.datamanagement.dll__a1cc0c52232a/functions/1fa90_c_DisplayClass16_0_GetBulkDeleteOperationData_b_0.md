# <>c__DisplayClass16_0::<GetBulkDeleteOperationData>b__0

- ea: `0x1fa90`
- end: `0x1fb36`
- name: `<>c__DisplayClass16_0::<GetBulkDeleteOperationData>b__0`
- size: `166`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x1fa90`

## string_xrefs

- `0x1fafe`: `Error in Bulk Delete handler | {0}`
- `0x1fa9f`: `BulkDeleteOperation.GetBulkDeleteOperationData did not get asyncEvent data.`

## pseudocode

```c

```

## disassembly

```asm
0x1fa90  ldarg.0
0x1fa91  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent <>c__DisplayClass16_0::asyncEvent
0x1fa96  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_Data()
0x1fa9b  stloc.0
0x1fa9c  ldloc.0
0x1fa9d  brtrue.s loc_1FAC6
0x1fa9f  ldstr    aBulkdeleteoper_0// "BulkDeleteOperation.GetBulkDeleteOperat"...
0x1faa4  stloc.2
0x1faa5  ldnull
0x1faa6  ldarg.0
0x1faa7  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass16_0::<>4__this
0x1faac  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BulkDeleteOperation::_organizationId
0x1fab1  ldc.i4.s 0x15
0x1fab3  ldloc.2
0x1fab4  ldc.i4.0
0x1fab5  newarr   [mscorlib]System.Object
0x1faba  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1fabf  ldloc.2
0x1fac0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentNullException::.ctor(string)
0x1fac5  throw
0x1fac6  ldtoken  [Microsoft.Crm]Microsoft.Crm.BulkDeleteData
0x1facb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1fad0  newobj   instance void [System.Xml]System.Xml.Serialization.XmlSerializer::.ctor(class [mscorlib]System.Type)
0x1fad5  stloc.1
0x1fad6  ldloc.0
0x1fad7  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x1fadc  stloc.3
0x1fadd  ldloc.1
0x1fade  ldloc.3
0x1fadf  callvirt instance object [System.Xml]System.Xml.Serialization.XmlSerializer::Deserialize(class [mscorlib]System.IO.TextReader)
0x1fae4  castclass [Microsoft.Crm]Microsoft.Crm.BulkDeleteData
0x1fae9  stloc.s  4
0x1faeb  leave.s  loc_1FB33
0x1faed  stloc.s  5
0x1faef  ldloc.s  5
0x1faf1  ldarg.0
0x1faf2  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent <>c__DisplayClass16_0::asyncEvent
0x1faf7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x1fafc  ldc.i4.s 0x15
0x1fafe  ldstr    aErrorInBulkDel_0// "Error in Bulk Delete handler | {0}"
0x1fb03  ldc.i4.1
0x1fb04  newarr   [mscorlib]System.Object
0x1fb09  dup
0x1fb0a  ldc.i4.0
0x1fb0b  ldloc.s  5
0x1fb0d  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x1fb12  stelem.ref
0x1fb13  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1fb18  ldc.i4   0x80040356
0x1fb1d  ldc.i4.0
0x1fb1e  newarr   [mscorlib]System.Object
0x1fb23  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x1fb28  throw
0x1fb29  ldloc.3
0x1fb2a  brfalse.s loc_1FB32
0x1fb2c  ldloc.3
0x1fb2d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1fb32  endfinally
0x1fb33  ldloc.s  4
0x1fb35  ret
```
