# _dynamic_initializer_for__s_hStopEvent__

- ea: `0x140001210`
- end: `0x14000123b`
- name: `_dynamic_initializer_for__s_hStopEvent__`
- size: `43`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140001aac`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x14000121e`
- `KERNEL32!CreateEventW` at `0x14000121e`

## pseudocode

```c
int dynamic_initializer_for__s_hStopEvent__()
{
  s_hStopEvent = CreateEventW(0, 0, 0, 0);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__s_hStopEvent__);
}

```

## disassembly

```asm
0x140001210  sub     rsp, 28h
0x140001214  xor     r9d, r9d; lpName
0x140001217  xor     r8d, r8d; bInitialState
0x14000121a  xor     edx, edx; bManualReset
0x14000121c  xor     ecx, ecx; lpEventAttributes
0x14000121e  call    cs:__imp_CreateEventW
0x140001224  lea     rcx, _dynamic_atexit_destructor_for__s_hStopEvent__
0x14000122b  mov     cs:?s_hStopEvent@@3VCHandle@@A, rax; CHandle s_hStopEvent
0x140001232  add     rsp, 28h
0x140001236  jmp     atexit
```
