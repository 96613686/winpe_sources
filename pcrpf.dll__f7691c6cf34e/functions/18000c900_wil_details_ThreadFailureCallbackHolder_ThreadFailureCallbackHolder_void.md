# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x18000c900`
- end: `0x18000c97f`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `127`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c5cc`

## callees

- `0x18000c900`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c916`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c916`

## string_xrefs

- `0x18000c937`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
0x18000c900  mov     [rsp+arg_0], rbx
0x18000c905  push    rdi
0x18000c906  sub     rsp, 20h
0x18000c90a  mov     rdi, rcx
0x18000c90d  cmp     dword ptr [rcx+18h], 0
0x18000c911  jz      short loc_18000C973
0x18000c913  mov     ebx, [rcx+18h]
0x18000c916  call    cs:__imp_GetCurrentThreadId
0x18000c91d  nop     dword ptr [rax+rax+00h]
0x18000c922  cmp     ebx, eax
0x18000c924  jz      short loc_18000C943
0x18000c926  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000c92d  test    rax, rax
0x18000c930  jz      short loc_18000C943
0x18000c932  mov     rdx, [rsp+28h]
0x18000c937  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000c93e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c943  mov     dword ptr [rdi+18h], 0
0x18000c94a  mov     rcx, [rdi]
0x18000c94d  jmp     short loc_18000C95B
0x18000c94f  cmp     rax, rdi
0x18000c952  jz      short loc_18000C965
0x18000c954  lea     rcx, [rax+10h]
0x18000c958  mov     [rdi], rcx
0x18000c95b  mov     rax, [rcx]
0x18000c95e  test    rax, rax
0x18000c961  jnz     short loc_18000C94F
0x18000c963  jmp     short loc_18000C96C
0x18000c965  mov     rax, [rdi+10h]
0x18000c969  mov     [rcx], rax
0x18000c96c  mov     qword ptr [rdi], 0
0x18000c973  mov     rbx, [rsp+28h+arg_0]
0x18000c978  add     rsp, 20h
0x18000c97c  pop     rdi
0x18000c97d  retn
```
