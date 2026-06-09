# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x18000b610`
- end: `0x18000b68f`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `127`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b470`

## callees

- `0x18000b610`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b626`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b626`

## string_xrefs

- `0x18000b647`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(
        wil::details::ThreadFailureCallbackHolder *this)
{
  int v2; // ebx
  wil::details::ThreadFailureCallbackHolder **v3; // rcx
  wil::details::ThreadFailureCallbackHolder *v4; // rax
  void *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_DWORD *)this + 6) )
  {
    v2 = *((_DWORD *)this + 6);
    if ( v2 != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    *((_DWORD *)this + 6) = 0;
    v3 = *(wil::details::ThreadFailureCallbackHolder ***)this;
    while ( 1 )
    {
      v4 = *v3;
      if ( !*v3 )
        break;
      if ( v4 == this )
      {
        *v3 = (wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)this + 2);
        break;
      }
      v3 = (wil::details::ThreadFailureCallbackHolder **)((char *)v4 + 16);
      *(_QWORD *)this = (char *)v4 + 16;
    }
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x18000b610  mov     [rsp+arg_0], rbx
0x18000b615  push    rdi
0x18000b616  sub     rsp, 20h
0x18000b61a  mov     rdi, rcx
0x18000b61d  cmp     dword ptr [rcx+18h], 0
0x18000b621  jz      short loc_18000B683
0x18000b623  mov     ebx, [rcx+18h]
0x18000b626  call    cs:__imp_GetCurrentThreadId
0x18000b62d  nop     dword ptr [rax+rax+00h]
0x18000b632  cmp     ebx, eax
0x18000b634  jz      short loc_18000B653
0x18000b636  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA; __annotation("Debug", "TelemetryAssert", "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread")
0x18000b63d  test    rax, rax
0x18000b640  jz      short loc_18000B653
0x18000b642  mov     rdx, [rsp+28h]
0x18000b647  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000b64e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b653  mov     dword ptr [rdi+18h], 0
0x18000b65a  mov     rcx, [rdi]
0x18000b65d  jmp     short loc_18000B66B
0x18000b65f  cmp     rax, rdi
0x18000b662  jz      short loc_18000B675
0x18000b664  lea     rcx, [rax+10h]
0x18000b668  mov     [rdi], rcx
0x18000b66b  mov     rax, [rcx]
0x18000b66e  test    rax, rax
0x18000b671  jnz     short loc_18000B65F
0x18000b673  jmp     short loc_18000B67C
0x18000b675  mov     rax, [rdi+10h]
0x18000b679  mov     [rcx], rax
0x18000b67c  mov     qword ptr [rdi], 0
0x18000b683  mov     rbx, [rsp+28h+arg_0]
0x18000b688  add     rsp, 20h
0x18000b68c  pop     rdi
0x18000b68d  retn
```
