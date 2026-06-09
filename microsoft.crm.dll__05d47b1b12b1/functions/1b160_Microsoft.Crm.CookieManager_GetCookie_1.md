# Microsoft.Crm.CookieManager::GetCookie_1

- ea: `0x1b160`
- end: `0x1b1c4`
- name: `Microsoft.Crm.CookieManager::GetCookie_1`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1b070`
- `0x1b0c0`

## callees

- `0x1b160`

## string_xrefs

- `0x1b161`: `targetUri`

## pseudocode

```c

```

## disassembly

```asm
0x1b160  ldarg.0
0x1b161  ldstr    aTargeturi// "targetUri"
0x1b166  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1b16b  ldc.i4   0x400
0x1b170  stloc.0
0x1b171  ldloc.0
0x1b172  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x1b177  stloc.1
0x1b178  ldarg.0
0x1b179  callvirt instance string [mscorlib]System.Object::ToString()
0x1b17e  ldstr    aMscrmsession// "MSCRMSession"
0x1b183  ldloc.1
0x1b184  ldloca.s 0
0x1b186  call     bool [Microsoft.Crm.Core]Microsoft.Crm.NativeMethods::InternetGetCookie(string, string, class [mscorlib]System.Text.StringBuilder, int32&)
0x1b18b  stloc.2
0x1b18c  ldloc.2
0x1b18d  brtrue.s loc_1B1B4
0x1b18f  ldc.i4   0x400
0x1b194  ldloc.0
0x1b195  bge.s    loc_1B1B4
0x1b197  ldloc.0
0x1b198  ldc.i4.1
0x1b199  add
0x1b19a  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x1b19f  stloc.1
0x1b1a0  ldarg.0
0x1b1a1  callvirt instance string [mscorlib]System.Object::ToString()
0x1b1a6  ldstr    aMscrmsession// "MSCRMSession"
0x1b1ab  ldloc.1
0x1b1ac  ldloca.s 0
0x1b1ae  call     bool [Microsoft.Crm.Core]Microsoft.Crm.NativeMethods::InternetGetCookie(string, string, class [mscorlib]System.Text.StringBuilder, int32&)
0x1b1b3  stloc.2
0x1b1b4  ldloc.2
0x1b1b5  brtrue.s loc_1B1BD
0x1b1b7  ldsfld   string [mscorlib]System.String::Empty
0x1b1bc  ret
0x1b1bd  ldloc.1
0x1b1be  callvirt instance string [mscorlib]System.Object::ToString()
0x1b1c3  ret
```
