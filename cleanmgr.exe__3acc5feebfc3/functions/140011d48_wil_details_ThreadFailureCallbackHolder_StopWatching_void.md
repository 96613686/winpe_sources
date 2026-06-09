# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x140011d48`
- end: `0x140011daf`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f930`
- `0x14000fc6c`

## callees

- `0x140011d48`
- `0x140018010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140011d51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140011d51`

## string_xrefs

- `0x140011d6d`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x140011d48  push    rbx
0x140011d4a  sub     rsp, 20h
0x140011d4e  mov     rbx, rcx
0x140011d51  call    cs:__imp_GetCurrentThreadId
0x140011d57  cmp     [rbx+18h], eax
0x140011d5a  jz      short loc_140011D79
0x140011d5c  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x140011d63  test    rax, rax
0x140011d66  jz      short loc_140011D79
0x140011d68  mov     rdx, [rsp+28h]
0x140011d6d  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x140011d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011d79  mov     rcx, [rbx]
0x140011d7c  mov     dword ptr [rbx+18h], 0
0x140011d83  jmp     short loc_140011D91
0x140011d85  cmp     rax, rbx
0x140011d88  jz      short loc_140011D9B
0x140011d8a  lea     rcx, [rax+10h]
0x140011d8e  mov     [rbx], rcx
0x140011d91  mov     rax, [rcx]
0x140011d94  test    rax, rax
0x140011d97  jnz     short loc_140011D85
0x140011d99  jmp     short loc_140011DA2
0x140011d9b  mov     rax, [rbx+10h]
0x140011d9f  mov     [rcx], rax
0x140011da2  mov     qword ptr [rbx], 0
0x140011da9  add     rsp, 20h
0x140011dad  pop     rbx
0x140011dae  retn
```
