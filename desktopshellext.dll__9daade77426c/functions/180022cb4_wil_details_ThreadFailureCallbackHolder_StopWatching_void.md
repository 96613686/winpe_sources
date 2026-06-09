# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x180022cb4`
- end: `0x180022d19`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `101`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800087e0`
- `0x180009150`
- `0x180010f04`
- `0x18001f14c`
- `0x18001f418`

## callees

- `0x180022cb4`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022cbd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022cbd`

## string_xrefs

- `0x180022cd9`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StopWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  wil::details::ThreadFailureCallbackHolder *v2; // rax
  void *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_DWORD *)this + 6) != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
    wil::details::g_pfnReportFatalUsageError(
      "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
      retaddr);
  *((_DWORD *)this + 6) = 0;
  while ( 1 )
  {
    v2 = **(wil::details::ThreadFailureCallbackHolder ***)this;
    if ( !v2 )
      break;
    if ( v2 == this )
    {
      **(_QWORD **)this = *((_QWORD *)this + 2);
      break;
    }
    *(_QWORD *)this = (char *)v2 + 16;
  }
  *(_QWORD *)this = 0;
}

```

## disassembly

```asm
0x180022cb4  push    rbx
0x180022cb6  sub     rsp, 20h
0x180022cba  mov     rbx, rcx
0x180022cbd  call    cs:__imp_GetCurrentThreadId
0x180022cc3  cmp     [rbx+18h], eax
0x180022cc6  jz      short loc_180022CE5
0x180022cc8  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180022ccf  test    rax, rax
0x180022cd2  jz      short loc_180022CE5
0x180022cd4  mov     rdx, [rsp+28h]
0x180022cd9  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180022ce0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ce5  mov     dword ptr [rbx+18h], 0
0x180022cec  mov     rcx, [rbx]
0x180022cef  mov     rax, [rcx]
0x180022cf2  test    rax, rax
0x180022cf5  jz      short loc_180022D0C
0x180022cf7  cmp     rax, rbx
0x180022cfa  jz      short loc_180022D05
0x180022cfc  add     rax, 10h
0x180022d00  mov     [rbx], rax
0x180022d03  jmp     short loc_180022CEC
0x180022d05  mov     rax, [rbx+10h]
0x180022d09  mov     [rcx], rax
0x180022d0c  mov     qword ptr [rbx], 0
0x180022d13  add     rsp, 20h
0x180022d17  pop     rbx
0x180022d18  retn
```
