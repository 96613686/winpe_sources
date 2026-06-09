# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x18002706c`
- end: `0x1800270e4`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180026e44`

## callees

- `0x18002706c`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027082`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027082`

## string_xrefs

- `0x18002709d`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x18002706c  mov     [rsp+arg_0], rbx
0x180027071  push    rdi
0x180027072  sub     rsp, 20h
0x180027076  mov     rdi, rcx
0x180027079  cmp     dword ptr [rcx+18h], 0
0x18002707d  jz      short loc_1800270D9
0x18002707f  mov     ebx, [rcx+18h]
0x180027082  call    cs:__imp_GetCurrentThreadId
0x180027088  cmp     ebx, eax
0x18002708a  jz      short loc_1800270A9
0x18002708c  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA; __annotation("Debug", "TelemetryAssert", "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread")
0x180027093  test    rax, rax
0x180027096  jz      short loc_1800270A9
0x180027098  mov     rdx, [rsp+28h]
0x18002709d  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800270a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800270a9  mov     dword ptr [rdi+18h], 0
0x1800270b0  mov     rcx, [rdi]
0x1800270b3  jmp     short loc_1800270C1
0x1800270b5  cmp     rax, rdi
0x1800270b8  jz      short loc_1800270CB
0x1800270ba  lea     rcx, [rax+10h]
0x1800270be  mov     [rdi], rcx
0x1800270c1  mov     rax, [rcx]
0x1800270c4  test    rax, rax
0x1800270c7  jnz     short loc_1800270B5
0x1800270c9  jmp     short loc_1800270D2
0x1800270cb  mov     rax, [rdi+10h]
0x1800270cf  mov     [rcx], rax
0x1800270d2  mov     qword ptr [rdi], 0
0x1800270d9  mov     rbx, [rsp+28h+arg_0]
0x1800270de  add     rsp, 20h
0x1800270e2  pop     rdi
0x1800270e3  retn
```
