# pplx::details::event_impl::event_impl(void)

- ea: `0x180014220`
- end: `0x180014256`
- name: `??0event_impl@details@pplx@@QEAA@XZ`
- size: `54`
- prototype: `__int64 __fastcall(pplx::details::event_impl *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800a5eec`
- `0x1800a5fd0`
- `0x1800bd2a8`

## callees

- `0x180014220`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180014236`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180014236`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180014247`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180014247`

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
0x180014220  push    rbx
0x180014222  sub     rsp, 20h
0x180014226  mov     rbx, rcx
0x180014229  xor     r9d, r9d; lpName
0x18001422c  xor     ecx, ecx; lpEventAttributes
0x18001422e  xor     r8d, r8d; bInitialState
0x180014231  mov     edx, 1; bManualReset
0x180014236  call    cs:__imp_CreateEventW
0x18001423c  mov     [rbx], rax
0x18001423f  test    rax, rax
0x180014242  jz      short loc_18001424D
0x180014244  mov     rcx, rax; hEvent
0x180014247  call    cs:__imp_ResetEvent
0x18001424d  mov     rax, rbx
0x180014250  add     rsp, 20h
0x180014254  pop     rbx
0x180014255  retn
```
