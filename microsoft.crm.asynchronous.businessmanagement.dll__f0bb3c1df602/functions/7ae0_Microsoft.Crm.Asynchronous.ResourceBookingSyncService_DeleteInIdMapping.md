# Microsoft.Crm.Asynchronous.ResourceBookingSyncService::DeleteInIdMapping

- ea: `0x7ae0`
- end: `0x7c0a`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncService::DeleteInIdMapping`
- size: `298`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x74e0`

## callees

- `0x7ae0`
- `0x8840`
- `0x16390`
- `0x163e0`

## string_xrefs

- `0x7b31`: `DELETE FROM BookableResourceBookingExchangeSyncIdMappingBase`
- `0x7ae6`: `MethodDeleteInIdMapping`
- `0x7bff`: `MethodDeleteInIdMapping`

## pseudocode

```c

```

## disassembly

```asm
0x7ae0  ldarg.0
0x7ae1  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x7ae6  ldstr    aMethoddeletein_3// "MethodDeleteInIdMapping"
0x7aeb  callvirt instance void Metrics::StartTimer(string name)
0x7af0  ldarg.2
0x7af1  brfalse  loc_7BF9
0x7af6  ldarg.2
0x7af7  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<valuetype [mscorlib]System.Guid>::get_Count()
0x7afc  ldc.i4.0
0x7afd  ble      loc_7BF9
0x7b02  ldc.i4.7
0x7b03  stloc.0
0x7b04  ldnull
0x7b05  stloc.1
0x7b06  ldc.i4.1
0x7b07  stloc.2
0x7b08  ldc.i4   0x1F4
0x7b0d  stloc.3
0x7b0e  ldc.i4.0
0x7b0f  stloc.s  4
0x7b11  ldarg.2
0x7b12  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x7b17  stloc.s  5
0x7b19  br       loc_7BDF
0x7b1e  ldloc.s  5
0x7b20  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Guid>::get_Current()
0x7b25  stloc.s  6
0x7b27  ldloc.2
0x7b28  brfalse.s loc_7B4A
0x7b2a  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x7b2f  stloc.1
0x7b30  ldloc.1
0x7b31  ldstr    aDeleteFromBook// "DELETE FROM BookableResourceBookingExch"...
0x7b36  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x7b3b  pop
0x7b3c  ldloc.1
0x7b3d  ldstr    aWhereBookabler_2// "WHERE BookableResourceBookingExchangeSy"...
0x7b42  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x7b47  pop
0x7b48  ldc.i4.0
0x7b49  stloc.2
0x7b4a  ldloc.s  4
0x7b4c  ldc.i4.1
0x7b4d  add
0x7b4e  stloc.s  4
0x7b50  ldloc.1
0x7b51  ldstr    a01_1// "'{0}'{1}"
0x7b56  ldloca.s 6
0x7b58  constrained. [mscorlib]System.Guid
0x7b5e  callvirt instance string [mscorlib]System.Object::ToString()
0x7b63  ldloc.s  4
0x7b65  ldarg.2
0x7b66  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<valuetype [mscorlib]System.Guid>::get_Count()
0x7b6b  bge.s    loc_7B73
0x7b6d  ldloc.s  4
0x7b6f  ldloc.3
0x7b70  rem
0x7b71  brtrue.s loc_7B7A
0x7b73  ldstr    asc_1BAE8// ")"
0x7b78  br.s     loc_7B7F
0x7b7a  ldstr    asc_20444// ", "
0x7b7f  call     string [mscorlib]System.String::Format(string, object, object)
0x7b84  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x7b89  pop
0x7b8a  ldloc.s  4
0x7b8c  ldloc.3
0x7b8d  rem
0x7b8e  brfalse.s loc_7B9A
0x7b90  ldloc.s  4
0x7b92  ldarg.2
0x7b93  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<valuetype [mscorlib]System.Guid>::get_Count()
0x7b98  blt.s    loc_7BDF
0x7b9a  ldarg.1
0x7b9b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection)
0x7ba0  stloc.s  7
0x7ba2  ldarg.1
0x7ba3  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x7ba8  stloc.s  8
0x7baa  ldloc.s  8
0x7bac  ldloc.1
0x7bad  callvirt instance string [mscorlib]System.Object::ToString()
0x7bb2  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x7bb7  ldarg.0
0x7bb8  ldloc.s  7
0x7bba  ldloc.s  8
0x7bbc  ldloc.0
0x7bbd  call     instance int32 Microsoft.Crm.Asynchronous.ResourceBookingSyncService::ExecuteTransaction(class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction transaction, class [System.Data]System.Data.IDbCommand command, valuetype DatabaseTransactionType databaseTransactionType)
0x7bc2  pop
0x7bc3  leave.s  loc_7BDD
0x7bc5  ldloc.s  8
0x7bc7  brfalse.s loc_7BD0
0x7bc9  ldloc.s  8
0x7bcb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7bd0  endfinally
0x7bd1  ldloc.s  7
0x7bd3  brfalse.s loc_7BDC
0x7bd5  ldloc.s  7
0x7bd7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7bdc  endfinally
0x7bdd  ldc.i4.1
0x7bde  stloc.2
0x7bdf  ldloc.s  5
0x7be1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7be6  brtrue   loc_7B1E
0x7beb  leave.s  loc_7BF9
0x7bed  ldloc.s  5
0x7bef  brfalse.s loc_7BF8
0x7bf1  ldloc.s  5
0x7bf3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7bf8  endfinally
0x7bf9  ldarg.0
0x7bfa  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x7bff  ldstr    aMethoddeletein_3// "MethodDeleteInIdMapping"
0x7c04  callvirt instance void Metrics::StopTimer(string name)
0x7c09  ret
```
