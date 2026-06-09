# pplx::details::event_impl::event_impl(void)

- ea: `0x18001adf0`
- end: `0x18001ae26`
- name: `??0event_impl@details@pplx@@QEAA@XZ`
- size: `54`
- prototype: `__int64 __fastcall(pplx::details::event_impl *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180046860`
- `0x18005a830`
- `0x18005a960`
- `0x18005ec30`
- `0x180076570`

## callees

- `0x18001adf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001ae17`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001ae17`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001ae06`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001ae06`

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
0x18001adf0  push    rbx
0x18001adf2  sub     rsp, 20h
0x18001adf6  mov     rbx, rcx
0x18001adf9  xor     r9d, r9d; lpName
0x18001adfc  xor     ecx, ecx; lpEventAttributes
0x18001adfe  xor     r8d, r8d; bInitialState
0x18001ae01  mov     edx, 1; bManualReset
0x18001ae06  call    cs:__imp_CreateEventW
0x18001ae0c  mov     [rbx], rax
0x18001ae0f  test    rax, rax
0x18001ae12  jz      short loc_18001AE1D
0x18001ae14  mov     rcx, rax; hEvent
0x18001ae17  call    cs:__imp_ResetEvent
0x18001ae1d  mov     rax, rbx
0x18001ae20  add     rsp, 20h
0x18001ae24  pop     rbx
0x18001ae25  retn
```
