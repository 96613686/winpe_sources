# pplx::details::event_impl::event_impl(void)

- ea: `0x18001ad60`
- end: `0x18001ad96`
- name: `??0event_impl@details@pplx@@QEAA@XZ`
- size: `54`
- prototype: `__int64 __fastcall(pplx::details::event_impl *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180046740`
- `0x18005a6e0`
- `0x18005a810`
- `0x18005eac0`
- `0x180076400`

## callees

- `0x18001ad60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001ad87`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001ad87`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001ad76`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001ad76`

## pseudocode

```c
pplx::details::event_impl *__fastcall pplx::details::event_impl::event_impl(pplx::details::event_impl *this)
{
  HANDLE EventW; // rax

  EventW = CreateEventW(0, 1, 0, 0);
  *(_QWORD *)this = EventW;
  if ( EventW )
    ResetEvent(EventW);
  return this;
}

```

## disassembly

```asm
0x18001ad60  push    rbx
0x18001ad62  sub     rsp, 20h
0x18001ad66  mov     rbx, rcx
0x18001ad69  xor     r9d, r9d; lpName
0x18001ad6c  xor     ecx, ecx; lpEventAttributes
0x18001ad6e  xor     r8d, r8d; bInitialState
0x18001ad71  mov     edx, 1; bManualReset
0x18001ad76  call    cs:__imp_CreateEventW
0x18001ad7c  mov     [rbx], rax
0x18001ad7f  test    rax, rax
0x18001ad82  jz      short loc_18001AD8D
0x18001ad84  mov     rcx, rax; hEvent
0x18001ad87  call    cs:__imp_ResetEvent
0x18001ad8d  mov     rax, rbx
0x18001ad90  add     rsp, 20h
0x18001ad94  pop     rbx
0x18001ad95  retn
```
