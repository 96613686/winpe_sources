# <ExecuteRequestMessagesAsyncImplementation>d__18::MoveNext

- ea: `0x32a90`
- end: `0x32d5e`
- name: `<ExecuteRequestMessagesAsyncImplementation>d__18::MoveNext`
- size: `718`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x17c40`
- `0x17ca0`
- `0x17cd0`
- `0x17d50`
- `0x17e40`
- `0x32a90`

## pseudocode

```c

```

## disassembly

```asm
0x32a90  ldarg.0
0x32a91  ldfld    int32 <ExecuteRequestMessagesAsyncImplementation>d__18::<>1__state
0x32a96  stloc.0
0x32a97  ldarg.0
0x32a98  ldfld    class Microsoft.Crm.Extensibility.OData.CrmODataBatchHandler <ExecuteRequestMessagesAsyncImplementation>d__18::<>4__this
0x32a9d  stloc.1
0x32a9e  ldloc.0
0x32a9f  ldc.i4.1
0x32aa0  ble.un.s loc_32AD9
0x32aa2  ldarg.0
0x32aa3  ldnull
0x32aa4  stfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Etm.RequestToken <ExecuteRequestMessagesAsyncImplementation>d__18::<requestToken>5__2
0x32aa9  ldarg.0
0x32aaa  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchRequestItem> <ExecuteRequestMessagesAsyncImplementation>d__18::requests
0x32aaf  brtrue.s loc_32AB7
0x32ab1  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor()
0x32ab6  throw
0x32ab7  ldloc.1
0x32ab8  call     instance void Microsoft.Crm.Extensibility.OData.CrmODataBatchHandler::SetMaxBatchSize()
0x32abd  ldarg.0
0x32abe  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchResponseItem>::.ctor()
0x32ac3  stfld    class [mscorlib]System.Collections.Generic.IList`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchResponseItem> <ExecuteRequestMessagesAsyncImplementation>d__18::<responses>5__3
0x32ac8  ldloc.1
0x32ac9  ldarg.0
0x32aca  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchRequestItem> <ExecuteRequestMessagesAsyncImplementation>d__18::requests
0x32acf  call     instance bool Microsoft.Crm.Extensibility.OData.CrmODataBatchHandler::ValidateBatchSize(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchRequestItem> requests)
0x32ad4  brfalse  loc_32D27
0x32ad9  nop
0x32ada  ldloc.0
0x32adb  ldc.i4.1
0x32adc  ble.un.s loc_32B2E
0x32ade  ldarg.0
0x32adf  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchRequestItem> <ExecuteRequestMessagesAsyncImplementation>d__18::requests
0x32ae4  call     T0x2B000129
0x32ae9  brfalse.s loc_32B0C
0x32aeb  ldarg.0
0x32aec  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchRequestItem> <ExecuteRequestMessagesAsyncImplementation>d__18::requests
0x32af1  call     T0x2B00012A
0x32af6  ldc.i4.s 0xA
0x32af8  bgt.s    loc_32B0C
0x32afa  ldarg.0
0x32afb  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchRequestItem> <ExecuteRequestMessagesAsyncImplementation>d__18::requests
0x32b00  call     T0x2B00012B
0x32b05  isinst   [System.Web.OData]System.Web.OData.Batch.OperationRequestItem
0x32b0a  brtrue.s loc_32B1D
0x32b0c  ldloc.1
0x32b0d  ldarg.0
0x32b0e  ldflda   class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Etm.RequestToken <ExecuteRequestMessagesAsyncImplementation>d__18::<requestToken>5__2
0x32b13  call     instance bool Microsoft.Crm.Extensibility.OData.CrmODataBatchHandler::ValidateExecuteMultipleThrottleSettings([out] class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Etm.RequestToken& requestToken)
0x32b18  brfalse  loc_32CB4
0x32b1d  ldarg.0
0x32b1e  ldarg.0
0x32b1f  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchRequestItem> <ExecuteRequestMessagesAsyncImplementation>d__18::requests
0x32b24  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchRequestItem>::GetEnumerator()
0x32b29  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchRequestItem> <ExecuteRequestMessagesAsyncImplementation>d__18::<>7__wrap3
0x32b2e  nop
0x32b2f  ldloc.0
0x32b30  brfalse.s loc_32BAC
0x32b32  ldloc.0
0x32b33  ldc.i4.1
0x32b34  beq      loc_32C55
0x32b39  br       loc_32C83
0x32b3e  ldarg.0
0x32b3f  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchRequestItem> <ExecuteRequestMessagesAsyncImplementation>d__18::<>7__wrap3
0x32b44  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchRequestItem>::get_Current()
0x32b49  stloc.3
0x32b4a  ldloc.3
0x32b4b  isinst   [System.Web.OData]System.Web.OData.Batch.OperationRequestItem
0x32b50  brfalse  loc_32C09
0x32b55  ldloc.1
0x32b56  ldloc.3
0x32b57  castclass [System.Web.OData]System.Web.OData.Batch.OperationRequestItem
0x32b5c  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.OData]System.Web.OData.Batch.OperationRequestItem::get_Request()
0x32b61  call     instance void Microsoft.Crm.Extensibility.OData.CrmODataBatchHandler::AddRequestInfoToTelemetryWithCounter(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x32b66  ldloc.3
0x32b67  ldloc.1
0x32b68  call     instance class [System.Net.Http]System.Net.Http.HttpMessageInvoker [System.Web.Http]System.Web.Http.Batch.HttpBatchHandler::get_Invoker()
0x32b6d  ldarg.0
0x32b6e  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <ExecuteRequestMessagesAsyncImplementation>d__18::cancellationToken
0x32b73  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchResponseItem> [System.Web.OData]System.Web.OData.Batch.ODataBatchRequestItem::SendRequestAsync(class [System.Net.Http]System.Net.Http.HttpMessageInvoker, valuetype [mscorlib]System.Threading.CancellationToken)
0x32b78  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchResponseItem>::GetAwaiter()
0x32b7d  stloc.s  5
0x32b7f  ldloca.s 5
0x32b81  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchResponseItem>::get_IsCompleted()
0x32b86  brtrue.s loc_32BC9
0x32b88  ldarg.0
0x32b89  ldc.i4.0
0x32b8a  dup
0x32b8b  stloc.0
0x32b8c  stfld    int32 <ExecuteRequestMessagesAsyncImplementation>d__18::<>1__state
0x32b91  ldarg.0
0x32b92  ldloc.s  5
0x32b94  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchResponseItem> <ExecuteRequestMessagesAsyncImplementation>d__18::<>u__1
0x32b99  ldarg.0
0x32b9a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IList`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchResponseItem>> <ExecuteRequestMessagesAsyncImplementation>d__18::<>t__builder
0x32b9f  ldloca.s 5
0x32ba1  ldarg.0
0x32ba2  call     T0x2B00012C
0x32ba7  leave    loc_32D5D
0x32bac  ldarg.0
0x32bad  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchResponseItem> <ExecuteRequestMessagesAsyncImplementation>d__18::<>u__1
0x32bb2  stloc.s  5
0x32bb4  ldarg.0
0x32bb5  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchResponseItem> <ExecuteRequestMessagesAsyncImplementation>d__18::<>u__1
0x32bba  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchResponseItem>
0x32bc0  ldarg.0
0x32bc1  ldc.i4.m1
0x32bc2  dup
0x32bc3  stloc.0
0x32bc4  stfld    int32 <ExecuteRequestMessagesAsyncImplementation>d__18::<>1__state
0x32bc9  ldloca.s 5
0x32bcb  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchResponseItem>::GetResult()
0x32bd0  stloc.s  4
0x32bd2  ldarg.0
0x32bd3  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchResponseItem> <ExecuteRequestMessagesAsyncImplementation>d__18::<responses>5__3
0x32bd8  ldloc.s  4
0x32bda  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchResponseItem>::Add(var<u1>)
0x32bdf  ldloc.1
0x32be0  ldfld    bool Microsoft.Crm.Extensibility.OData.CrmODataBatchHandler::ContinueOnError
0x32be5  brtrue   loc_32C83
0x32bea  ldloc.s  4
0x32bec  brfalse  loc_32C83
0x32bf1  ldloc.s  4
0x32bf3  castclass [System.Web.OData]System.Web.OData.Batch.OperationResponseItem
0x32bf8  callvirt instance class [System.Net.Http]System.Net.Http.HttpResponseMessage [System.Web.OData]System.Web.OData.Batch.OperationResponseItem::get_Response()
0x32bfd  callvirt instance bool [System.Net.Http]System.Net.Http.HttpResponseMessage::get_IsSuccessStatusCode()
0x32c02  brtrue.s loc_32C83
0x32c04  br       loc_32C93
0x32c09  ldloc.1
0x32c0a  ldloc.3
0x32c0b  castclass [System.Web.OData]System.Web.OData.Batch.ChangeSetRequestItem
0x32c10  ldarg.0
0x32c11  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchResponseItem> <ExecuteRequestMessagesAsyncImplementation>d__18::<responses>5__3
0x32c16  ldarg.0
0x32c17  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <ExecuteRequestMessagesAsyncImplementation>d__18::cancellationToken
0x32c1c  call     instance class [mscorlib]System.Threading.Tasks.Task`1<bool> Microsoft.Crm.Extensibility.OData.CrmODataBatchHandler::ExecuteChangeSet(class [System.Web.OData]System.Web.OData.Batch.ChangeSetRequestItem changeSet, class [mscorlib]System.Collections.Generic.IList`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchResponseItem> responses, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x32c21  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::GetAwaiter()
0x32c26  stloc.s  6
0x32c28  ldloca.s 6
0x32c2a  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::get_IsCompleted()
0x32c2f  brtrue.s loc_32C72
0x32c31  ldarg.0
0x32c32  ldc.i4.1
0x32c33  dup
0x32c34  stloc.0
0x32c35  stfld    int32 <ExecuteRequestMessagesAsyncImplementation>d__18::<>1__state
0x32c3a  ldarg.0
0x32c3b  ldloc.s  6
0x32c3d  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <ExecuteRequestMessagesAsyncImplementation>d__18::<>u__2
0x32c42  ldarg.0
0x32c43  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IList`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchResponseItem>> <ExecuteRequestMessagesAsyncImplementation>d__18::<>t__builder
0x32c48  ldloca.s 6
0x32c4a  ldarg.0
0x32c4b  call     T0x2B00012D
0x32c50  leave    loc_32D5D
0x32c55  ldarg.0
0x32c56  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <ExecuteRequestMessagesAsyncImplementation>d__18::<>u__2
0x32c5b  stloc.s  6
0x32c5d  ldarg.0
0x32c5e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <ExecuteRequestMessagesAsyncImplementation>d__18::<>u__2
0x32c63  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>
0x32c69  ldarg.0
0x32c6a  ldc.i4.m1
0x32c6b  dup
0x32c6c  stloc.0
0x32c6d  stfld    int32 <ExecuteRequestMessagesAsyncImplementation>d__18::<>1__state
0x32c72  ldloca.s 6
0x32c74  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::GetResult()
0x32c79  brtrue.s loc_32C83
0x32c7b  ldloc.1
0x32c7c  ldfld    bool Microsoft.Crm.Extensibility.OData.CrmODataBatchHandler::ContinueOnError
0x32c81  brfalse.s loc_32C93
0x32c83  ldarg.0
0x32c84  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchRequestItem> <ExecuteRequestMessagesAsyncImplementation>d__18::<>7__wrap3
0x32c89  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x32c8e  brtrue   loc_32B3E
0x32c93  leave.s  loc_32CAD
0x32c95  ldloc.0
0x32c96  ldc.i4.0
0x32c97  bge.s    loc_32CAC
0x32c99  ldarg.0
0x32c9a  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchRequestItem> <ExecuteRequestMessagesAsyncImplementation>d__18::<>7__wrap3
0x32c9f  brfalse.s loc_32CAC
0x32ca1  ldarg.0
0x32ca2  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchRequestItem> <ExecuteRequestMessagesAsyncImplementation>d__18::<>7__wrap3
0x32ca7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x32cac  endfinally
0x32cad  ldarg.0
0x32cae  ldnull
0x32caf  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchRequestItem> <ExecuteRequestMessagesAsyncImplementation>d__18::<>7__wrap3
0x32cb4  ldarg.0
0x32cb5  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Etm.RequestToken <ExecuteRequestMessagesAsyncImplementation>d__18::<requestToken>5__2
0x32cba  brfalse.s loc_32CCC
0x32cbc  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Etm.RequestGovernor [Microsoft.Crm.Platform.Server]Microsoft.Crm.Etm.RequestGovernor::get_Instance()
0x32cc1  ldarg.0
0x32cc2  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Etm.RequestToken <ExecuteRequestMessagesAsyncImplementation>d__18::<requestToken>5__2
0x32cc7  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Etm.RequestGovernor::OnEndRequest(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Etm.RequestToken)
0x32ccc  leave.s  loc_32D27
0x32cce  pop
0x32ccf  ldarg.0
0x32cd0  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchResponseItem> <ExecuteRequestMessagesAsyncImplementation>d__18::<responses>5__3
0x32cd5  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchResponseItem>::GetEnumerator()
0x32cda  stloc.s  7
0x32cdc  br.s     loc_32CF2
0x32cde  ldloc.s  7
0x32ce0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchResponseItem>::get_Current()
0x32ce5  stloc.s  8
0x32ce7  ldloc.s  8
0x32ce9  brfalse.s loc_32CF2
0x32ceb  ldloc.s  8
0x32ced  callvirt instance void [System.Web.OData]System.Web.OData.Batch.ODataBatchResponseItem::Dispose()
0x32cf2  ldloc.s  7
0x32cf4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x32cf9  brtrue.s loc_32CDE
0x32cfb  leave.s  loc_32D0D
0x32cfd  ldloc.0
0x32cfe  ldc.i4.0
0x32cff  bge.s    loc_32D0C
0x32d01  ldloc.s  7
0x32d03  brfalse.s loc_32D0C
0x32d05  ldloc.s  7
0x32d07  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x32d0c  endfinally
0x32d0d  ldarg.0
0x32d0e  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Etm.RequestToken <ExecuteRequestMessagesAsyncImplementation>d__18::<requestToken>5__2
0x32d13  brfalse.s loc_32D25
0x32d15  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Etm.RequestGovernor [Microsoft.Crm.Platform.Server]Microsoft.Crm.Etm.RequestGovernor::get_Instance()
0x32d1a  ldarg.0
0x32d1b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Etm.RequestToken <ExecuteRequestMessagesAsyncImplementation>d__18::<requestToken>5__2
0x32d20  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Etm.RequestGovernor::OnErrorRequest(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Etm.RequestToken)
0x32d25  rethrow
0x32d27  ldarg.0
0x32d28  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchResponseItem> <ExecuteRequestMessagesAsyncImplementation>d__18::<responses>5__3
0x32d2d  stloc.2
0x32d2e  leave.s  loc_32D49
0x32d30  stloc.s  9
0x32d32  ldarg.0
0x32d33  ldc.i4.s 0xFE
0x32d35  stfld    int32 <ExecuteRequestMessagesAsyncImplementation>d__18::<>1__state
0x32d3a  ldarg.0
0x32d3b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IList`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchResponseItem>> <ExecuteRequestMessagesAsyncImplementation>d__18::<>t__builder
0x32d40  ldloc.s  9
0x32d42  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IList`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchResponseItem>>::SetException(class [mscorlib]System.Exception)
0x32d47  leave.s  loc_32D5D
0x32d49  ldarg.0
0x32d4a  ldc.i4.s 0xFE
0x32d4c  stfld    int32 <ExecuteRequestMessagesAsyncImplementation>d__18::<>1__state
0x32d51  ldarg.0
0x32d52  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IList`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchResponseItem>> <ExecuteRequestMessagesAsyncImplementation>d__18::<>t__builder
0x32d57  ldloc.2
0x32d58  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IList`1<class [System.Web.OData]System.Web.OData.Batch.ODataBatchResponseItem>>::SetResult(var<u1>)
0x32d5d  ret
```
