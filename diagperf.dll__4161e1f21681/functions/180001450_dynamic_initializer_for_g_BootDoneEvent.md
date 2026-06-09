# _dynamic_initializer_for__g_BootDoneEvent__

- ea: `0x180001450`
- end: `0x18000147d`
- name: `_dynamic_initializer_for__g_BootDoneEvent__`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18005754c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180001460`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180001460`

## pseudocode

```c
int dynamic_initializer_for__g_BootDoneEvent__()
{
  g_BootDoneEvent = (__int64)CreateEventW(0, 1, 0, 0);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__g_BootDoneEvent__);
}

```

## disassembly

```asm
0x180001450  sub     rsp, 28h
0x180001454  xor     r9d, r9d; lpName
0x180001457  xor     r8d, r8d; bInitialState
0x18000145a  xor     ecx, ecx; lpEventAttributes
0x18000145c  lea     edx, [r9+1]; bManualReset
0x180001460  call    cs:__imp_CreateEventW
0x180001466  lea     rcx, _dynamic_atexit_destructor_for__g_BootDoneEvent__
0x18000146d  mov     cs:?g_BootDoneEvent@@3VCEvent@PerfDiagDm@@A, rax; PerfDiagDm::CEvent g_BootDoneEvent
0x180001474  add     rsp, 28h
0x180001478  jmp     atexit
```
