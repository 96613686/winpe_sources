# Microsoft.Crm.Asynchronous.EntityKeyIndexCreateOperation::HasJobBeenAbortedOrPaused

- ea: `0x2780`
- end: `0x2891`
- name: `Microsoft.Crm.Asynchronous.EntityKeyIndexCreateOperation::HasJobBeenAbortedOrPaused`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x2600`

## callees

- `0x2780`
- `0x28a0`
- `0x28c0`

## pseudocode

```c

```

## disassembly

```asm
0x2780  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSucceededResult::.ctor()
0x2785  stloc.0
0x2786  ldarg.2
0x2787  callvirt instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::QueryForEarlyExitRequest()
0x278c  stloc.1
0x278d  ldloc.1
0x278e  switch   loc_27A4, loc_27F7, loc_2844
0x279f  br       loc_288F
0x27a4  ldarg.0
0x27a5  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x27aa  dup
0x27ab  ldstr    aEntitykeyindex// "EntityKeyIndexStatus"
0x27b0  ldc.i4.2
0x27b1  box      [mscorlib]System.Int32
0x27b6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x27bb  dup
0x27bc  ldstr    aIndexid// "IndexId"
0x27c1  ldarg.1
0x27c2  box      [mscorlib]System.Guid
0x27c7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x27cc  dup
0x27cd  ldstr    aAsyncjobid// "AsyncJobId"
0x27d2  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x27d7  box      [mscorlib]System.Guid
0x27dc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x27e1  ldarg.2
0x27e2  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_Data()
0x27e7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x27ec  ldarg.3
0x27ed  call     instance void Microsoft.Crm.Asynchronous.EntityKeyIndexCreateOperation::UpdateEntityKey(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> columnValues, valuetype [mscorlib]System.Guid entityKeyId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x27f2  br       loc_288F
0x27f7  ldarg.0
0x27f8  ldarg.1
0x27f9  ldarg.3
0x27fa  call     instance void Microsoft.Crm.Asynchronous.EntityKeyIndexCreateOperation::DeleteIndex(valuetype [mscorlib]System.Guid indexId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x27ff  ldarg.0
0x2800  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x2805  dup
0x2806  ldstr    aEntitykeyindex// "EntityKeyIndexStatus"
0x280b  ldc.i4.0
0x280c  box      [mscorlib]System.Int32
0x2811  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2816  dup
0x2817  ldstr    aIndexid// "IndexId"
0x281c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2821  box      [mscorlib]System.Guid
0x2826  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x282b  ldarg.2
0x282c  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_Data()
0x2831  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x2836  ldarg.3
0x2837  call     instance void Microsoft.Crm.Asynchronous.EntityKeyIndexCreateOperation::UpdateEntityKey(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> columnValues, valuetype [mscorlib]System.Guid entityKeyId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x283c  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncPausedResult::.ctor()
0x2841  stloc.0
0x2842  br.s     loc_288F
0x2844  ldarg.0
0x2845  ldarg.1
0x2846  ldarg.3
0x2847  call     instance void Microsoft.Crm.Asynchronous.EntityKeyIndexCreateOperation::DeleteIndex(valuetype [mscorlib]System.Guid indexId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x284c  ldarg.0
0x284d  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x2852  dup
0x2853  ldstr    aEntitykeyindex// "EntityKeyIndexStatus"
0x2858  ldc.i4.3
0x2859  box      [mscorlib]System.Int32
0x285e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2863  dup
0x2864  ldstr    aIndexid// "IndexId"
0x2869  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x286e  box      [mscorlib]System.Guid
0x2873  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2878  ldarg.2
0x2879  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_Data()
0x287e  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x2883  ldarg.3
0x2884  call     instance void Microsoft.Crm.Asynchronous.EntityKeyIndexCreateOperation::UpdateEntityKey(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> columnValues, valuetype [mscorlib]System.Guid entityKeyId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2889  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncCanceledResult::.ctor()
0x288e  stloc.0
0x288f  ldloc.0
0x2890  ret
```
