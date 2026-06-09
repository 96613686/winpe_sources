# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x18000eff8`
- end: `0x18000f05f`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c988`
- `0x18000dd94`

## callees

- `0x18000eff8`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f001`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f001`

## string_xrefs

- `0x18000f01d`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x18000eff8  push    rbx
0x18000effa  sub     rsp, 20h
0x18000effe  mov     rbx, rcx
0x18000f001  call    cs:__imp_GetCurrentThreadId
0x18000f007  cmp     [rbx+18h], eax
0x18000f00a  jz      short loc_18000F029
0x18000f00c  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000f013  test    rax, rax
0x18000f016  jz      short loc_18000F029
0x18000f018  mov     rdx, [rsp+28h]
0x18000f01d  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000f024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f029  mov     rcx, [rbx]
0x18000f02c  mov     dword ptr [rbx+18h], 0
0x18000f033  jmp     short loc_18000F041
0x18000f035  cmp     rax, rbx
0x18000f038  jz      short loc_18000F04B
0x18000f03a  lea     rcx, [rax+10h]
0x18000f03e  mov     [rbx], rcx
0x18000f041  mov     rax, [rcx]
0x18000f044  test    rax, rax
0x18000f047  jnz     short loc_18000F035
0x18000f049  jmp     short loc_18000F052
0x18000f04b  mov     rax, [rbx+10h]
0x18000f04f  mov     [rcx], rax
0x18000f052  mov     qword ptr [rbx], 0
0x18000f059  add     rsp, 20h
0x18000f05d  pop     rbx
0x18000f05e  retn
```
