# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x180011a3c`
- end: `0x180011aa3`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000fb34`
- `0x180010410`

## callees

- `0x180011a3c`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011a45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011a45`

## string_xrefs

- `0x180011a61`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x180011a3c  push    rbx
0x180011a3e  sub     rsp, 20h
0x180011a42  mov     rbx, rcx
0x180011a45  call    cs:__imp_GetCurrentThreadId
0x180011a4b  cmp     [rbx+18h], eax
0x180011a4e  jz      short loc_180011A6D
0x180011a50  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180011a57  test    rax, rax
0x180011a5a  jz      short loc_180011A6D
0x180011a5c  mov     rdx, [rsp+28h]
0x180011a61  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180011a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a6d  mov     rcx, [rbx]
0x180011a70  mov     dword ptr [rbx+18h], 0
0x180011a77  jmp     short loc_180011A85
0x180011a79  cmp     rax, rbx
0x180011a7c  jz      short loc_180011A8F
0x180011a7e  lea     rcx, [rax+10h]
0x180011a82  mov     [rbx], rcx
0x180011a85  mov     rax, [rcx]
0x180011a88  test    rax, rax
0x180011a8b  jnz     short loc_180011A79
0x180011a8d  jmp     short loc_180011A96
0x180011a8f  mov     rax, [rbx+10h]
0x180011a93  mov     [rcx], rax
0x180011a96  mov     qword ptr [rbx], 0
0x180011a9d  add     rsp, 20h
0x180011aa1  pop     rbx
0x180011aa2  retn
```
