# Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2::AddJob

- ea: `0xd0`
- end: `0x1a0`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2::AddJob`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xd0`
- `0xa30`
- `0xb10`

## string_xrefs

- `0x11d`: `removeIfCompleted`

## pseudocode

```c

```

## disassembly

```asm
0xd0  newobj   instance void class <>c__DisplayClass5_0<var<u1>, !!T0>::.ctor()
0xd5  stloc.0
0xd6  ldarg.2
0xd7  ldarg.0
0xd8  ldfld    int32 class Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2<var<u1>, !!T0>::httpClientTimeoutInMilliseconds
0xdd  ble.s    loc_105
0xdf  ldstr    aThreshold0Cann// "Threshold {0} cannot be bigger than htt"...
0xe4  ldarg.2
0xe5  box      [mscorlib]System.Int32
0xea  ldarg.0
0xeb  ldfld    int32 class Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2<var<u1>, !!T0>::httpClientTimeoutInMilliseconds
0xf0  box      [mscorlib]System.Int32
0xf5  call     string [mscorlib]System.String::Format(string, object, object)
0xfa  ldstr    aSyncwaittimems// "syncWaitTimeMs"
0xff  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x104  throw
0x105  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x10a  dup
0x10b  ldstr    aSyncwaittimems// "syncWaitTimeMs"
0x110  ldarga.s 2
0x112  call     instance string [mscorlib]System.Int32::ToString()
0x117  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x11c  dup
0x11d  ldstr    aRemoveifcomple// "removeIfCompleted"
0x122  ldarga.s 3
0x124  call     instance string [mscorlib]System.Boolean::ToString()
0x129  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x12e  call     string Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.HttpQueryStringHelper::ConvertTo(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> hashtable)
0x133  stloc.1
0x134  ldloc.0
0x135  ldnull
0x136  stfld    string class <>c__DisplayClass5_0<var<u1>, !!T0>::extra
0x13b  ldarg.0
0x13c  ldfld    class [System.Net.Http]System.Net.Http.HttpClient class Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2<var<u1>, !!T0>::client
0x141  ldstr    a01// "{0}?{1}"
0x146  ldarg.0
0x147  ldfld    string class Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2<var<u1>, !!T0>::baseUri
0x14c  ldloc.1
0x14d  call     string [mscorlib]System.String::Format(string, object, object)
0x152  ldarg.1
0x153  ldc.i4.s 0xA
0x155  ldc.i4   0xBB8
0x15a  call     T0x2B000002
0x15f  stloc.2
0x160  leave.s  loc_19E
0x162  isinst   [System.Net.Http]System.Net.Http.HttpRequestException
0x167  dup
0x168  brtrue.s loc_16E
0x16a  pop
0x16b  ldc.i4.0
0x16c  br.s     loc_184
0x16e  stloc.3
0x16f  ldloc.3
0x170  ldloc.0
0x171  ldftn    instance bool class <>c__DisplayClass5_0<var<u1>, !!T0>::<AddJob>b__0(class [System]System.Net.Sockets.SocketException)
0x177  newobj   instance void class [mscorlib]System.Func`2<class [System]System.Net.Sockets.SocketException, bool>::.ctor(object, native int)
0x17c  call     T0x2B000003
0x181  ldc.i4.0
0x182  cgt.un
0x184  endfilter
0x186  pop
0x187  ldstr    aFailedToAddANe// "Failed to add a new job; extra info: {0"...
0x18c  ldloc.0
0x18d  ldfld    string class <>c__DisplayClass5_0<var<u1>, !!T0>::extra
0x192  call     string [mscorlib]System.String::Format(string, object)
0x197  ldloc.3
0x198  newobj   instance void Microsoft.Xrm.Tools.OwinJobManager.Client.Exceptions.JobCreationException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x19d  throw
0x19e  ldloc.2
0x19f  ret
```
