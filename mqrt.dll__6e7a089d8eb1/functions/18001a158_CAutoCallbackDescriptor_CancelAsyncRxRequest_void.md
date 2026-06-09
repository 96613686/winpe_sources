# CAutoCallbackDescriptor::CancelAsyncRxRequest(void)

- ea: `0x18001a158`
- end: `0x18001a1b0`
- name: `?CancelAsyncRxRequest@CAutoCallbackDescriptor@@AEAAXXZ`
- size: `88`
- prototype: `void __fastcall(CAutoCallbackDescriptor *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a55c`

## callees

- `0x180013bbc`
- `0x18001a158`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18001a192`
- `KERNEL32!SetEvent` at `0x18001a192`
- `KERNEL32!LeaveCriticalSection` at `0x18001a19c`
- `KERNEL32!LeaveCriticalSection` at `0x18001a19c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CAutoCallbackDescriptor::CancelAsyncRxRequest(CAutoCallbackDescriptor *this)
{
  _BYTE *v1; // rbx

  v1 = *(_BYTE **)this;
  *(_QWORD *)this = 0;
  try
  {
    CCriticalSection::Lock((CCriticalSection *)&g_AsyncRxThread);
    *v1 = 1;
    byte_18003D8C0 = 1;
    SetEvent(hEvent);
    LeaveCriticalSection(&g_AsyncRxThread);
  }
  catch ( std::bad_alloc )
  {
  }
}

```

## disassembly

```asm
0x18001a158  mov     [rsp+arg_8], rbx
0x18001a15d  push    rdi
0x18001a15e  sub     rsp, 20h
0x18001a162  mov     rbx, [rcx]
0x18001a165  mov     qword ptr [rcx], 0
0x18001a16c  lea     rdi, ?g_AsyncRxThread@@3VCAsyncRxThread@@A; CAsyncRxThread g_AsyncRxThread
0x18001a173  mov     [rsp+28h+arg_0], rdi
0x18001a178  mov     rcx, rdi; this
0x18001a17b  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x18001a180  nop
0x18001a181  mov     byte ptr [rbx], 1
0x18001a184  mov     cs:byte_18003D8C0, 1
0x18001a18b  mov     rcx, cs:hEvent; hEvent
0x18001a192  call    cs:__imp_SetEvent
0x18001a198  nop
0x18001a199  mov     rcx, rdi; lpCriticalSection
0x18001a19c  call    cs:__imp_LeaveCriticalSection
0x18001a1a2  nop
0x18001a1a3  jmp     short $+2
0x18001a1a5  mov     rbx, [rsp+28h+arg_8]
0x18001a1aa  add     rsp, 20h
0x18001a1ae  pop     rdi
0x18001a1af  retn
```
