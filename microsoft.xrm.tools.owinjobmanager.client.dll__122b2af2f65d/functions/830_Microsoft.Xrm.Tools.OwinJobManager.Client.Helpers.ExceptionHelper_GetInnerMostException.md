# Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.ExceptionHelper::GetInnerMostException

- ea: `0x830`
- end: `0x844`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.ExceptionHelper::GetInnerMostException`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x810`

## callees

- `0x830`

## pseudocode

```c

```

## disassembly

```asm
0x830  br.s     loc_83A
0x832  ldarg.0
0x833  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x838  starg.s  0
0x83a  ldarg.0
0x83b  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x840  brtrue.s loc_832
0x842  ldarg.0
0x843  ret
```
