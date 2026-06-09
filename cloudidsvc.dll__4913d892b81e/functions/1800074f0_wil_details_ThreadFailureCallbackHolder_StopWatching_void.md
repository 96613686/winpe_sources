# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x1800074f0`
- end: `0x180007557`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004724`

## callees

- `0x1800074f0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800074f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800074f9`

## string_xrefs

- `0x180007515`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x1800074f0  push    rbx
0x1800074f2  sub     rsp, 20h
0x1800074f6  mov     rbx, rcx
0x1800074f9  call    cs:__imp_GetCurrentThreadId
0x1800074ff  cmp     [rbx+18h], eax
0x180007502  jz      short loc_180007521
0x180007504  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000750b  test    rax, rax
0x18000750e  jz      short loc_180007521
0x180007510  mov     rdx, [rsp+28h]
0x180007515  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000751c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007521  mov     rcx, [rbx]
0x180007524  mov     dword ptr [rbx+18h], 0
0x18000752b  jmp     short loc_180007539
0x18000752d  cmp     rax, rbx
0x180007530  jz      short loc_180007543
0x180007532  lea     rcx, [rax+10h]
0x180007536  mov     [rbx], rcx
0x180007539  mov     rax, [rcx]
0x18000753c  test    rax, rax
0x18000753f  jnz     short loc_18000752D
0x180007541  jmp     short loc_18000754A
0x180007543  mov     rax, [rbx+10h]
0x180007547  mov     [rcx], rax
0x18000754a  mov     qword ptr [rbx], 0
0x180007551  add     rsp, 20h
0x180007555  pop     rbx
0x180007556  retn
```
