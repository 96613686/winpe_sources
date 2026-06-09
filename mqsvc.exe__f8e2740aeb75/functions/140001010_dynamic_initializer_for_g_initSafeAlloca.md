# _dynamic_initializer_for__g_initSafeAlloca__

- ea: `0x140001010`
- end: `0x140001037`
- name: `_dynamic_initializer_for__g_initSafeAlloca__`
- size: `39`
- prototype: `PIMAGE_NT_HEADERS()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## import_xrefs

- `ntdll!RtlImageNtHeader` at `0x140001021`
- `ntdll!RtlImageNtHeader` at `0x140001021`

## pseudocode

```c
PIMAGE_NT_HEADERS dynamic_initializer_for__g_initSafeAlloca__()
{
  PIMAGE_NT_HEADERS result; // rax

  result = RtlImageNtHeader(NtCurrentPeb()->ImageBaseAddress);
  g_ulAdditionalProbeSize = 0x4000;
  return result;
}

```

## disassembly

```asm
0x140001010  sub     rsp, 28h
0x140001014  mov     rcx, gs:60h
0x14000101d  mov     rcx, [rcx+10h]; BaseAddress
0x140001021  call    cs:__imp_RtlImageNtHeader
0x140001027  mov     cs:g_ulAdditionalProbeSize, 4000h
0x140001032  add     rsp, 28h
0x140001036  retn
```
