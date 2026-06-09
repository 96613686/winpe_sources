# Microsoft.Crm.AutoReimpersonator::DoImpersonate

- ea: `0x35320`
- end: `0x353dc`
- name: `Microsoft.Crm.AutoReimpersonator::DoImpersonate`
- size: `188`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x352e0`
- `0x35300`

## callees

- `0x2e280`
- `0x2e290`
- `0x2e2a0`
- `0x2e2f0`
- `0x352a0`
- `0x35320`

## string_xrefs

- `0x35339`: `Invalid Thread Id returned by GetCurrentThread. thread == IntPtr.Zero`
- `0x3536a`: `OpenThreadToken failed with hr = `
- `0x35391`: `SetThreadToken(null, null) failed with hr =`
- `0x353ba`: `ImpersonateSelf(2) failed with hr =`

## pseudocode

```c

```

## disassembly

```asm
0x35320  ldarg.0
0x35321  ldarg.1
0x35322  stfld    bool Microsoft.Crm.AutoReimpersonator::forceImpersonate
0x35327  call     native int Microsoft.Crm.NativeMethods::GetCurrentThread()
0x3532c  dup
0x3532d  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x35332  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x35337  brfalse.s loc_35344
0x35339  ldstr    aInvalidThreadI// "Invalid Thread Id returned by GetCurren"...
0x3533e  newobj   instance void Microsoft.Crm.CrmImpersonationException::.ctor(string message)
0x35343  throw
0x35344  ldc.i4.4
0x35345  ldc.i4.1
0x35346  ldarg.0
0x35347  ldflda   native int Microsoft.Crm.AutoReimpersonator::token
0x3534c  call     bool Microsoft.Crm.NativeMethods::OpenThreadToken([hasfieldmarshal] native int, unsigned int32 thread, bool desiredAccess, [hasfieldmarshal] native int& openAsSelf)
0x35351  brtrue.s loc_35380
0x35353  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x35358  stloc.0
0x35359  ldloc.0
0x3535a  ldc.i4   0x3F0
0x3535f  bne.un.s loc_3536A
0x35361  ldarg.0
0x35362  ldfld    bool Microsoft.Crm.AutoReimpersonator::forceImpersonate
0x35367  brtrue.s loc_35380
0x35369  ret
0x3536a  ldstr    aOpenthreadtoke// "OpenThreadToken failed with hr = "
0x3536f  ldloc.0
0x35370  box      [mscorlib]System.Int32
0x35375  call     string [mscorlib]System.String::Concat(object, object)
0x3537a  newobj   instance void Microsoft.Crm.CrmImpersonationException::.ctor(string message)
0x3537f  throw
0x35380  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x35385  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3538a  call     bool Microsoft.Crm.NativeMethods::SetThreadToken([hasfieldmarshal] native int, native int thread)
0x3538f  brtrue.s loc_353AB
0x35391  ldstr    aSetthreadtoken// "SetThreadToken(null, null) failed with "...
0x35396  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x3539b  box      [mscorlib]System.Int32
0x353a0  call     string [mscorlib]System.String::Concat(object, object)
0x353a5  newobj   instance void Microsoft.Crm.CrmImpersonationException::.ctor(string message)
0x353aa  throw
0x353ab  ldarg.0
0x353ac  ldc.i4.1
0x353ad  stfld    bool Microsoft.Crm.AutoReimpersonator::threadTokenCleared
0x353b2  ldc.i4.2
0x353b3  call     bool Microsoft.Crm.NativeMethods::ImpersonateSelf([hasfieldmarshal] int32)
0x353b8  brtrue.s loc_353D4
0x353ba  ldstr    aImpersonatesel// "ImpersonateSelf(2) failed with hr ="
0x353bf  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x353c4  box      [mscorlib]System.Int32
0x353c9  call     string [mscorlib]System.String::Concat(object, object)
0x353ce  newobj   instance void Microsoft.Crm.CrmImpersonationException::.ctor(string message)
0x353d3  throw
0x353d4  ldarg.0
0x353d5  ldc.i4.1
0x353d6  stfld    bool Microsoft.Crm.AutoReimpersonator::impersonate
0x353db  ret
```
