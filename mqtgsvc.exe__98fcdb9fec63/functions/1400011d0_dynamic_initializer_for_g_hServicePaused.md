# _dynamic_initializer_for__g_hServicePaused__

- ea: `0x1400011d0`
- end: `0x1400011fd`
- name: `_dynamic_initializer_for__g_hServicePaused__`
- size: `45`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140001aac`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x1400011e0`
- `KERNEL32!CreateEventW` at `0x1400011e0`

## pseudocode

```c
int dynamic_initializer_for__g_hServicePaused__()
{
  g_hServicePaused = CreateEventW(0, 1, 1, 0);
  return atexit(dynamic_atexit_destructor_for__g_hServicePaused__);
}

```

## disassembly

```asm
0x1400011d0  sub     rsp, 28h
0x1400011d4  xor     r9d, r9d; lpName
0x1400011d7  xor     ecx, ecx; lpEventAttributes
0x1400011d9  lea     edx, [r9+1]; bManualReset
0x1400011dd  mov     r8d, edx; bInitialState
0x1400011e0  call    cs:__imp_CreateEventW
0x1400011e6  lea     rcx, _dynamic_atexit_destructor_for__g_hServicePaused__
0x1400011ed  mov     cs:?g_hServicePaused@@3VCHandle@@A, rax; CHandle g_hServicePaused
0x1400011f4  add     rsp, 28h
0x1400011f8  jmp     atexit
```
