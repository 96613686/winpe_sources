# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x1800094d4`
- end: `0x18000953b`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000875c`
- `0x180008898`

## callees

- `0x1800094d4`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800094dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800094dd`

## string_xrefs

- `0x1800094f9`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x1800094d4  push    rbx
0x1800094d6  sub     rsp, 20h
0x1800094da  mov     rbx, rcx
0x1800094dd  call    cs:__imp_GetCurrentThreadId
0x1800094e3  cmp     [rbx+18h], eax
0x1800094e6  jz      short loc_180009505
0x1800094e8  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x1800094ef  test    rax, rax
0x1800094f2  jz      short loc_180009505
0x1800094f4  mov     rdx, [rsp+28h]
0x1800094f9  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180009500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009505  mov     rcx, [rbx]
0x180009508  mov     dword ptr [rbx+18h], 0
0x18000950f  jmp     short loc_18000951D
0x180009511  cmp     rax, rbx
0x180009514  jz      short loc_180009527
0x180009516  lea     rcx, [rax+10h]
0x18000951a  mov     [rbx], rcx
0x18000951d  mov     rax, [rcx]
0x180009520  test    rax, rax
0x180009523  jnz     short loc_180009511
0x180009525  jmp     short loc_18000952E
0x180009527  mov     rax, [rbx+10h]
0x18000952b  mov     [rcx], rax
0x18000952e  mov     qword ptr [rbx], 0
0x180009535  add     rsp, 20h
0x180009539  pop     rbx
0x18000953a  retn
```
