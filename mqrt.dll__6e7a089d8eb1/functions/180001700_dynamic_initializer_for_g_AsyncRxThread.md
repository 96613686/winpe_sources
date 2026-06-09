# _dynamic_initializer_for__g_AsyncRxThread__

- ea: `0x180001700`
- end: `0x180001740`
- name: `_dynamic_initializer_for__g_AsyncRxThread__`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001f70`
- `0x18001305c`

## pseudocode

```c
int dynamic_initializer_for__g_AsyncRxThread__()
{
  CCriticalSection::CCriticalSection((CCriticalSection *)&g_AsyncRxThread);
  byte_18003D498 = 0;
  *(_OWORD *)&hObject = 0;
  hEvent = 0;
  byte_18003D8C0 = 0;
  return atexit(dynamic_atexit_destructor_for__g_AsyncRxThread__);
}

```

## disassembly

```asm
0x180001700  sub     rsp, 28h
0x180001704  lea     rcx, ?g_AsyncRxThread@@3VCAsyncRxThread@@A; this
0x18000170b  call    ??0CCriticalSection@@QEAA@XZ; CCriticalSection::CCriticalSection(void)
0x180001710  xor     eax, eax
0x180001712  lea     rcx, _dynamic_atexit_destructor_for__g_AsyncRxThread__
0x180001719  xorps   xmm0, xmm0
0x18000171c  mov     cs:byte_18003D498, al
0x180001722  movdqa  cs:hObject, xmm0
0x18000172a  mov     cs:hEvent, rax
0x180001731  mov     cs:byte_18003D8C0, al
0x180001737  add     rsp, 28h
0x18000173b  jmp     atexit
```
