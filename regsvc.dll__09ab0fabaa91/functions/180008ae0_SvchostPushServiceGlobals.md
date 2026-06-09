# SvchostPushServiceGlobals

- ea: `0x180008ae0`
- end: `0x180008ae8`
- name: `SvchostPushServiceGlobals`
- size: `8`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
void __fastcall SvchostPushServiceGlobals(__int64 a1)
{
  g_svcsGlobalData = a1;
}

```

## disassembly

```asm
0x180008ae0  mov     cs:g_svcsGlobalData, rcx
0x180008ae7  retn
```
