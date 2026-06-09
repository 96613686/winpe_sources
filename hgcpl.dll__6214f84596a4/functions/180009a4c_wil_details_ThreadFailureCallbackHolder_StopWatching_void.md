# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x180009a4c`
- end: `0x180009ab3`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000725c`
- `0x180007698`

## callees

- `0x180009a4c`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009a55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009a55`

## string_xrefs

- `0x180009a71`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StopWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  wil::details::ThreadFailureCallbackHolder **v2; // rcx
  wil::details::ThreadFailureCallbackHolder *v3; // rax
  void *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_DWORD *)this + 6) != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
    wil::details::g_pfnReportFatalUsageError(
      "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
      retaddr);
  v2 = *(wil::details::ThreadFailureCallbackHolder ***)this;
  *((_DWORD *)this + 6) = 0;
  while ( 1 )
  {
    v3 = *v2;
    if ( !*v2 )
      break;
    if ( v3 == this )
    {
      *v2 = (wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)this + 2);
      break;
    }
    v2 = (wil::details::ThreadFailureCallbackHolder **)((char *)v3 + 16);
    *(_QWORD *)this = (char *)v3 + 16;
  }
  *(_QWORD *)this = 0;
}

```

## disassembly

```asm
0x180009a4c  push    rbx
0x180009a4e  sub     rsp, 20h
0x180009a52  mov     rbx, rcx
0x180009a55  call    cs:__imp_GetCurrentThreadId
0x180009a5b  cmp     [rbx+18h], eax
0x180009a5e  jz      short loc_180009A7D
0x180009a60  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA; __annotation("Debug", "TelemetryAssert", "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread")
0x180009a67  test    rax, rax
0x180009a6a  jz      short loc_180009A7D
0x180009a6c  mov     rdx, [rsp+28h]
0x180009a71  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180009a78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a7d  mov     rcx, [rbx]
0x180009a80  mov     dword ptr [rbx+18h], 0
0x180009a87  jmp     short loc_180009A95
0x180009a89  cmp     rax, rbx
0x180009a8c  jz      short loc_180009A9F
0x180009a8e  lea     rcx, [rax+10h]
0x180009a92  mov     [rbx], rcx
0x180009a95  mov     rax, [rcx]
0x180009a98  test    rax, rax
0x180009a9b  jnz     short loc_180009A89
0x180009a9d  jmp     short loc_180009AA6
0x180009a9f  mov     rax, [rbx+10h]
0x180009aa3  mov     [rcx], rax
0x180009aa6  mov     qword ptr [rbx], 0
0x180009aad  add     rsp, 20h
0x180009ab1  pop     rbx
0x180009ab2  retn
```
