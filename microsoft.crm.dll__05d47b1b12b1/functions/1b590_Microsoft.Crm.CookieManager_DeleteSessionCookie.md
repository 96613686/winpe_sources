# Microsoft.Crm.CookieManager::DeleteSessionCookie

- ea: `0x1b590`
- end: `0x1b5b2`
- name: `Microsoft.Crm.CookieManager::DeleteSessionCookie`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x1b591`: `targetUri`

## pseudocode

```c

```

## disassembly

```asm
0x1b590  ldarg.0
0x1b591  ldstr    aTargeturi// "targetUri"
0x1b596  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1b59b  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x1b5a0  stloc.0
0x1b5a1  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x1b5a6  ldc.i4.s 0x2A
0x1b5a8  ldloca.s 0
0x1b5aa  ldc.i4.0
0x1b5ab  call     bool [Microsoft.Crm.Core]Microsoft.Crm.NativeMethods::InternetSetOption(native int, int32, native int&, int32)
0x1b5b0  pop
0x1b5b1  ret
```
