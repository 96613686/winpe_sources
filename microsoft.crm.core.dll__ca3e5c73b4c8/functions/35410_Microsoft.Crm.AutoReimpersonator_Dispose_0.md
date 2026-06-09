# Microsoft.Crm.AutoReimpersonator::Dispose_0

- ea: `0x35410`
- end: `0x35524`
- name: `Microsoft.Crm.AutoReimpersonator::Dispose_0`
- size: `276`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x353e0`
- `0x35400`

## callees

- `0x1b8d0`
- `0x2e2a0`
- `0x2e2b0`
- `0x2e300`
- `0x352a0`
- `0x35410`

## string_xrefs

- `0x35418`: `AutoReimpersonator`
- `0x3541d`: `AutoReimpersonator - Encountered disposed AutoReimpersonator when it should not be disposed`
- `0x3543d`: `RevertToSelf for reverting to impersonation failed with hr = `
- `0x35480`: `Handle to thread token should be non zero`
- `0x354a2`: `SetThreadToken for reverting to impersonation failed with hr = `

## pseudocode

```c

```

## disassembly

```asm
0x35410  ldarg.0
0x35411  ldfld    bool Microsoft.Crm.AutoReimpersonator::disposed
0x35416  brfalse.s loc_35428
0x35418  ldstr    aAutoreimperson// "AutoReimpersonator"
0x3541d  ldstr    aAutoreimperson_0// "AutoReimpersonator - Encountered dispos"...
0x35422  newobj   instance void Microsoft.Crm.CrmObjectDisposedException::.ctor(string objectName, string message)
0x35427  throw
0x35428  ldarg.0
0x35429  ldfld    bool Microsoft.Crm.AutoReimpersonator::impersonate
0x3542e  brfalse.s loc_3545A
0x35430  call     bool Microsoft.Crm.NativeMethods::RevertToSelf()
0x35435  brtrue.s loc_35453
0x35437  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x3543c  stloc.0
0x3543d  ldstr    aReverttoselfFo// "RevertToSelf for reverting to impersona"...
0x35442  ldloc.0
0x35443  box      [mscorlib]System.Int32
0x35448  call     string [mscorlib]System.String::Concat(object, object)
0x3544d  newobj   instance void Microsoft.Crm.CrmImpersonationException::.ctor(string message)
0x35452  throw
0x35453  ldarg.0
0x35454  ldc.i4.0
0x35455  stfld    bool Microsoft.Crm.AutoReimpersonator::impersonate
0x3545a  ldarg.0
0x3545b  ldfld    bool Microsoft.Crm.AutoReimpersonator::threadTokenCleared
0x35460  brfalse  loc_3550D
0x35465  ldarg.0
0x35466  ldfld    bool Microsoft.Crm.AutoReimpersonator::forceImpersonate
0x3546b  brtrue.s loc_3547F
0x3546d  ldarg.0
0x3546e  ldfld    native int Microsoft.Crm.AutoReimpersonator::token
0x35473  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x35478  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x3547d  br.s     loc_35480
0x3547f  ldc.i4.1
0x35480  ldstr    aHandleToThread// "Handle to thread token should be non ze"...
0x35485  call     void [System]System.Diagnostics.Trace::Assert(bool, string)
0x3548a  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3548f  ldarg.0
0x35490  ldfld    native int Microsoft.Crm.AutoReimpersonator::token
0x35495  call     bool Microsoft.Crm.NativeMethods::SetThreadToken([hasfieldmarshal] native int, native int thread)
0x3549a  brtrue.s loc_354B8
0x3549c  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x354a1  stloc.1
0x354a2  ldstr    aSetthreadtoken_0// "SetThreadToken for reverting to imperso"...
0x354a7  ldloc.1
0x354a8  box      [mscorlib]System.Int32
0x354ad  call     string [mscorlib]System.String::Concat(object, object)
0x354b2  newobj   instance void Microsoft.Crm.CrmImpersonationException::.ctor(string message)
0x354b7  throw
0x354b8  ldarg.0
0x354b9  ldfld    bool Microsoft.Crm.AutoReimpersonator::forceImpersonate
0x354be  brfalse.s loc_354D2
0x354c0  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x354c5  ldarg.0
0x354c6  ldfld    native int Microsoft.Crm.AutoReimpersonator::token
0x354cb  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x354d0  brfalse.s loc_354FB
0x354d2  ldarg.0
0x354d3  ldfld    native int Microsoft.Crm.AutoReimpersonator::token
0x354d8  call     bool Microsoft.Crm.NativeMethods::CloseHandle([hasfieldmarshal] native int)
0x354dd  brtrue.s loc_354FB
0x354df  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x354e4  stloc.2
0x354e5  ldstr    aClosehandleFai// "CloseHandle failed with hr = "
0x354ea  ldloc.2
0x354eb  box      [mscorlib]System.Int32
0x354f0  call     string [mscorlib]System.String::Concat(object, object)
0x354f5  newobj   instance void Microsoft.Crm.CrmImpersonationException::.ctor(string message)
0x354fa  throw
0x354fb  ldarg.0
0x354fc  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x35501  stfld    native int Microsoft.Crm.AutoReimpersonator::token
0x35506  ldarg.0
0x35507  ldc.i4.0
0x35508  stfld    bool Microsoft.Crm.AutoReimpersonator::threadTokenCleared
0x3550d  ldarg.0
0x3550e  ldc.i4.1
0x3550f  stfld    bool Microsoft.Crm.AutoReimpersonator::disposed
0x35514  ldarg.1
0x35515  brfalse.s loc_3551D
0x35517  ldarg.0
0x35518  call     void [mscorlib]System.GC::SuppressFinalize(object)
0x3551d  ldarg.0
0x3551e  call     void [mscorlib]System.GC::KeepAlive(object)
0x35523  ret
```
