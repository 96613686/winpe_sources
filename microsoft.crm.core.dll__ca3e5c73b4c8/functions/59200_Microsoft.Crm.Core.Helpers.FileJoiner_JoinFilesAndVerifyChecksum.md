# Microsoft.Crm.Core.Helpers.FileJoiner::JoinFilesAndVerifyChecksum

- ea: `0x59200`
- end: `0x5940b`
- name: `Microsoft.Crm.Core.Helpers.FileJoiner::JoinFilesAndVerifyChecksum`
- size: `523`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1a8a0`
- `0x1be80`
- `0x1c070`
- `0x1eaa0`
- `0x1f510`
- `0x50cf0`
- `0x50d10`
- `0x59200`
- `0x6d090`
- `0x6d0b0`

## string_xrefs

- `0x5921e`: `fileJoinConfigSettings`
- `0x59233`: `fileJoinConfigSettings.SharedFilesDirectory`
- `0x59257`: `Invalid shared files directory: {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x59200  newobj   instance void <>c__DisplayClass0_0::.ctor()
0x59205  stloc.0
0x59206  ldloc.0
0x59207  ldarg.1
0x59208  stfld    class Microsoft.Crm.Core.Models.FileJoinConfigSettings <>c__DisplayClass0_0::fileJoinConfigSettings
0x5920d  ldarg.0
0x5920e  ldstr    aFilemodels// "fileModels"
0x59213  call     void Microsoft.Crm.Exceptions::ThrowIfNull(object parameter, string name)
0x59218  ldloc.0
0x59219  ldfld    class Microsoft.Crm.Core.Models.FileJoinConfigSettings <>c__DisplayClass0_0::fileJoinConfigSettings
0x5921e  ldstr    aFilejoinconfig// "fileJoinConfigSettings"
0x59223  call     void Microsoft.Crm.Exceptions::ThrowIfNull(object parameter, string name)
0x59228  ldloc.0
0x59229  ldfld    class Microsoft.Crm.Core.Models.FileJoinConfigSettings <>c__DisplayClass0_0::fileJoinConfigSettings
0x5922e  callvirt instance string Microsoft.Crm.Core.Models.FileJoinConfigSettings::get_SharedFilesDirectory()
0x59233  ldstr    aFilejoinconfig_0// "fileJoinConfigSettings.SharedFilesDirec"...
0x59238  call     void Microsoft.Crm.Exceptions::ThrowIfNullOrWhiteSpace(string parameter, string name)
0x5923d  ldloc.0
0x5923e  ldfld    class Microsoft.Crm.Core.Models.FileJoinConfigSettings <>c__DisplayClass0_0::fileJoinConfigSettings
0x59243  callvirt instance string Microsoft.Crm.Core.Models.FileJoinConfigSettings::get_SharedFilesDirectory()
0x59248  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x5924d  brtrue.s loc_5927B
0x5924f  ldnull
0x59250  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x59255  ldc.i4.s 0x12
0x59257  ldstr    aInvalidSharedF// "Invalid shared files directory: {0}."
0x5925c  ldc.i4.1
0x5925d  newarr   [mscorlib]System.Object
0x59262  dup
0x59263  ldc.i4.0
0x59264  ldloc.0
0x59265  ldfld    class Microsoft.Crm.Core.Models.FileJoinConfigSettings <>c__DisplayClass0_0::fileJoinConfigSettings
0x5926a  callvirt instance string Microsoft.Crm.Core.Models.FileJoinConfigSettings::get_SharedFilesDirectory()
0x5926f  stelem.ref
0x59270  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x59275  newobj   instance void class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<string>::.ctor()
0x5927a  ret
0x5927b  ldarg.0
0x5927c  call     T0x2B0000E8
0x59281  brtrue.s loc_592A1
0x59283  ldnull
0x59284  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x59289  ldc.i4.s 0x12
0x5928b  ldstr    aInvalidFileMod// "Invalid file models data."
0x59290  ldc.i4.0
0x59291  newarr   [mscorlib]System.Object
0x59296  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x5929b  newobj   instance void class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<string>::.ctor()
0x592a0  ret
0x592a1  ldloc.0
0x592a2  newobj   instance void [mscorlib]System.Threading.CancellationTokenSource::.ctor()
0x592a7  stfld    class [mscorlib]System.Threading.CancellationTokenSource <>c__DisplayClass0_0::cancelTokenSrc
0x592ac  newobj   instance void <>c__DisplayClass0_1::.ctor()
0x592b1  stloc.1
0x592b2  ldloc.1
0x592b3  ldloc.0
0x592b4  stfld    class <>c__DisplayClass0_0 <>c__DisplayClass0_1::CS$<>8__locals1
0x592b9  ldloc.1
0x592ba  newobj   instance void class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<string>::.ctor()
0x592bf  stfld    class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<string> <>c__DisplayClass0_1::fileLocations
0x592c4  ldarg.0
0x592c5  newobj   instance void [mscorlib]System.Threading.Tasks.ParallelOptions::.ctor()
0x592ca  dup
0x592cb  ldloc.1
0x592cc  ldfld    class <>c__DisplayClass0_0 <>c__DisplayClass0_1::CS$<>8__locals1
0x592d1  ldfld    class Microsoft.Crm.Core.Models.FileJoinConfigSettings <>c__DisplayClass0_0::fileJoinConfigSettings
0x592d6  callvirt instance int32 Microsoft.Crm.Core.Models.FileJoinConfigSettings::get_MaxDegreeOfParallelism()
0x592db  callvirt instance void [mscorlib]System.Threading.Tasks.ParallelOptions::set_MaxDegreeOfParallelism(int32)
0x592e0  dup
0x592e1  ldloc.1
0x592e2  ldfld    class <>c__DisplayClass0_0 <>c__DisplayClass0_1::CS$<>8__locals1
0x592e7  ldfld    class [mscorlib]System.Threading.CancellationTokenSource <>c__DisplayClass0_0::cancelTokenSrc
0x592ec  callvirt instance valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationTokenSource::get_Token()
0x592f1  callvirt instance void [mscorlib]System.Threading.Tasks.ParallelOptions::set_CancellationToken(valuetype [mscorlib]System.Threading.CancellationToken)
0x592f6  ldloc.1
0x592f7  ldftn    instance void <>c__DisplayClass0_1::<JoinFilesAndVerifyChecksum>b__0(class Microsoft.Crm.Core.Models.FileModel FileModel)
0x592fd  newobj   instance void class [mscorlib]System.Action`1<class Microsoft.Crm.Core.Models.FileModel>::.ctor(object, native int)
0x59302  call     T0x2B0000E9
0x59307  pop
0x59308  ldloc.1
0x59309  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<string> <>c__DisplayClass0_1::fileLocations
0x5930e  stloc.2
0x5930f  leave    loc_59409
0x59314  stloc.3
0x59315  ldloc.3
0x59316  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x5931b  ldtoken  [mscorlib]System.AggregateException
0x59320  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x59325  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x5932a  brfalse.s loc_5938A
0x5932c  ldloc.3
0x5932d  castclass [mscorlib]System.AggregateException
0x59332  callvirt instance class [mscorlib]System.AggregateException [mscorlib]System.AggregateException::Flatten()
0x59337  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [mscorlib]System.Exception> [mscorlib]System.AggregateException::get_InnerExceptions()
0x5933c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [mscorlib]System.Exception>::GetEnumerator()
0x59341  stloc.s  4
0x59343  br.s     loc_5936B
0x59345  ldloc.s  4
0x59347  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.Exception>::get_Current()
0x5934c  stloc.s  5
0x5934e  ldloc.3
0x5934f  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x59354  ldc.i4.s 0x12
0x59356  ldstr    aErrorOccurred0// "Error occurred  : {0}."
0x5935b  ldc.i4.1
0x5935c  newarr   [mscorlib]System.Object
0x59361  dup
0x59362  ldc.i4.0
0x59363  ldloc.s  5
0x59365  stelem.ref
0x59366  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x5936b  ldloc.s  4
0x5936d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x59372  brtrue.s loc_59345
0x59374  leave.s  loc_59382
0x59376  ldloc.s  4
0x59378  brfalse.s loc_59381
0x5937a  ldloc.s  4
0x5937c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x59381  endfinally
0x59382  newobj   instance void class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<string>::.ctor()
0x59387  stloc.2
0x59388  leave.s  loc_59409
0x5938a  ldloc.3
0x5938b  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x59390  ldtoken  [mscorlib]System.OperationCanceledException
0x59395  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5939a  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x5939f  brtrue.s loc_593CF
0x593a1  ldloc.3
0x593a2  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x593a7  ldtoken  [mscorlib]System.ArgumentNullException
0x593ac  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x593b1  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x593b6  brtrue.s loc_593CF
0x593b8  ldloc.3
0x593b9  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x593be  ldtoken  [mscorlib]System.ObjectDisposedException
0x593c3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x593c8  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x593cd  brfalse.s loc_593F3
0x593cf  ldloc.3
0x593d0  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x593d5  ldc.i4.s 0x12
0x593d7  ldstr    aErrorOccurred0// "Error occurred  : {0}."
0x593dc  ldc.i4.1
0x593dd  newarr   [mscorlib]System.Object
0x593e2  dup
0x593e3  ldc.i4.0
0x593e4  ldloc.3
0x593e5  stelem.ref
0x593e6  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x593eb  newobj   instance void class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<string>::.ctor()
0x593f0  stloc.2
0x593f1  leave.s  loc_59409
0x593f3  ldstr    aUnexpectedErro_0// "Unexpected error occured while joining "...
0x593f8  ldloc.3
0x593f9  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x593fe  ldc.i4   0x80040216
0x59403  newobj   instance void Microsoft.Crm.CrmException::.ctor(string message, class [mscorlib]System.Exception innerException, int32 errorCode)
0x59408  throw
0x59409  ldloc.2
0x5940a  ret
```
