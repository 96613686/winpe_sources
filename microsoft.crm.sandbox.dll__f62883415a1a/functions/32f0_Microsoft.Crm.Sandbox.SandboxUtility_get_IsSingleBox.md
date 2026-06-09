# Microsoft.Crm.Sandbox.SandboxUtility::get_IsSingleBox

- ea: `0x32f0`
- end: `0x33f3`
- name: `Microsoft.Crm.Sandbox.SandboxUtility::get_IsSingleBox`
- size: `259`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x14a0`
- `0x14d0`
- `0x32f0`

## string_xrefs

- `0x331e`: `MSCRMSandboxService`
- `0x3311`: `SYSTEM\CurrentControlSet\Services\{0}`

## pseudocode

```c

```

## disassembly

```asm
0x32f0  ldsflda  valuetype [mscorlib]System.Nullable`1<bool> Microsoft.Crm.Sandbox.SandboxUtility::_singleBox
0x32f5  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x32fa  brfalse.s loc_3307
0x32fc  ldsflda  valuetype [mscorlib]System.Nullable`1<bool> Microsoft.Crm.Sandbox.SandboxUtility::_singleBox
0x3301  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x3306  ret
0x3307  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x330c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3311  ldstr    aSystemCurrentc// "SYSTEM\\CurrentControlSet\\Services\\{0"...
0x3316  ldc.i4.1
0x3317  newarr   [mscorlib]System.Object
0x331c  dup
0x331d  ldc.i4.0
0x331e  ldstr    aMscrmsandboxse// "MSCRMSandboxService"
0x3323  stelem.ref
0x3324  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3329  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x332e  stloc.1
0x332f  ldloc.1
0x3330  brfalse.s loc_3353
0x3332  ldloc.1
0x3333  ldstr    aSinglebox// "SingleBox"
0x3338  ldc.i4.0
0x3339  box      [mscorlib]System.Int32
0x333e  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string, object)
0x3343  unbox.any [mscorlib]System.Int32
0x3348  ldc.i4.0
0x3349  cgt.un
0x334b  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x3350  stloc.0
0x3351  leave.s  loc_3366
0x3353  ldc.i4.0
0x3354  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x3359  stloc.0
0x335a  leave.s  loc_3366
0x335c  ldloc.1
0x335d  brfalse.s loc_3365
0x335f  ldloc.1
0x3360  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3365  endfinally
0x3366  ldc.i4.0
0x3367  ldc.i4.0
0x3368  call     T0x2B000008
0x336d  ldc.i4.0
0x336e  cgt
0x3370  brfalse.s loc_3391
0x3372  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3377  ldc.i4.s 0x26
0x3379  ldstr    aSandboxutility_0// "SandboxUtility.IsSingleBox: WARNING: fo"...
0x337e  ldc.i4.0
0x337f  newarr   [mscorlib]System.Object
0x3384  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x3389  ldloca.s 0
0x338b  ldc.i4.1
0x338c  call     instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x3391  ldc.i4.1
0x3392  ldc.i4.0
0x3393  call     T0x2B000008
0x3398  ldc.i4.0
0x3399  cgt
0x339b  brfalse.s loc_33BC
0x339d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x33a2  ldc.i4.s 0x26
0x33a4  ldstr    aSandboxutility_1// "SandboxUtility.IsSingleBox: WARNING: fo"...
0x33a9  ldc.i4.0
0x33aa  newarr   [mscorlib]System.Object
0x33af  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x33b4  ldloca.s 0
0x33b6  ldc.i4.0
0x33b7  call     instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x33bc  ldloc.0
0x33bd  stsfld   valuetype [mscorlib]System.Nullable`1<bool> Microsoft.Crm.Sandbox.SandboxUtility::_singleBox
0x33c2  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x33c7  ldc.i4.s 0x26
0x33c9  ldstr    aSandboxutility_2// "SandboxUtility.IsSingleBox: _singleBox:"...
0x33ce  ldsfld   valuetype [mscorlib]System.Nullable`1<bool> Microsoft.Crm.Sandbox.SandboxUtility::_singleBox
0x33d3  box      valuetype [mscorlib]System.Nullable`1<bool>
0x33d8  call     string [mscorlib]System.String::Concat(object, object)
0x33dd  ldc.i4.0
0x33de  newarr   [mscorlib]System.Object
0x33e3  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x33e8  ldsflda  valuetype [mscorlib]System.Nullable`1<bool> Microsoft.Crm.Sandbox.SandboxUtility::_singleBox
0x33ed  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x33f2  ret
```
