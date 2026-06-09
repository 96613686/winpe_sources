# Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::StopWindowsServices

- ea: `0x2310`
- end: `0x2393`
- name: `Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::StopWindowsServices`
- size: `131`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x2310`
- `0x23a0`
- `0x2460`
- `0x24b0`

## string_xrefs

- `0x233c`: `Stopping service {0} and dependent services {1}`

## pseudocode

```c

```

## disassembly

```asm
0x2310  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x2315  stloc.0
0x2316  ldarg.1
0x2317  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x231c  stloc.1
0x231d  br.s     loc_2373
0x231f  ldloc.1
0x2320  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2325  castclass [mscorlib]System.String
0x232a  stloc.2
0x232b  ldarg.0
0x232c  ldloc.2
0x232d  call     instance bool Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::IsWindowsServiceStopped(string serviceName)
0x2332  brtrue.s loc_2373
0x2334  ldarg.0
0x2335  ldloc.2
0x2336  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::EnumerateRunningDependentServices(string serviceName)
0x233b  stloc.3
0x233c  ldstr    aStoppingServic// "Stopping service {0} and dependent serv"...
0x2341  ldc.i4.2
0x2342  newarr   [mscorlib]System.Object
0x2347  dup
0x2348  ldc.i4.0
0x2349  ldloc.2
0x234a  stelem.ref
0x234b  dup
0x234c  ldc.i4.1
0x234d  ldstr    asc_19276// ", "
0x2352  ldloc.3
0x2353  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x2358  stelem.ref
0x2359  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x235e  ldarg.0
0x235f  ldloc.2
0x2360  call     instance void Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::StopWindowsService(string serviceName)
0x2365  ldloc.0
0x2366  ldloc.2
0x2367  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x236c  ldloc.0
0x236d  ldloc.3
0x236e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x2373  ldloc.1
0x2374  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2379  brtrue.s loc_231F
0x237b  leave.s  loc_2391
0x237d  ldloc.1
0x237e  isinst   [mscorlib]System.IDisposable
0x2383  stloc.s  4
0x2385  ldloc.s  4
0x2387  brfalse.s loc_2390
0x2389  ldloc.s  4
0x238b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2390  endfinally
0x2391  ldloc.0
0x2392  ret
```
