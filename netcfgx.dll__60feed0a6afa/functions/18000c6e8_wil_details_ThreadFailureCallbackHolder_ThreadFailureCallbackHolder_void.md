# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x18000c6e8`
- end: `0x18000c760`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c204`

## callees

- `0x18000c6e8`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c6fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c6fe`

## string_xrefs

- `0x18000c719`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x18000c6e8  mov     [rsp+arg_0], rbx
0x18000c6ed  push    rdi
0x18000c6ee  sub     rsp, 20h
0x18000c6f2  mov     rdi, rcx
0x18000c6f5  cmp     dword ptr [rcx+18h], 0
0x18000c6f9  jz      short loc_18000C755
0x18000c6fb  mov     ebx, [rcx+18h]
0x18000c6fe  call    cs:__imp_GetCurrentThreadId
0x18000c704  cmp     ebx, eax
0x18000c706  jz      short loc_18000C725
0x18000c708  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000c70f  test    rax, rax
0x18000c712  jz      short loc_18000C725
0x18000c714  mov     rdx, [rsp+28h]
0x18000c719  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000c720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c725  mov     dword ptr [rdi+18h], 0
0x18000c72c  mov     rcx, [rdi]
0x18000c72f  jmp     short loc_18000C73D
0x18000c731  cmp     rax, rdi
0x18000c734  jz      short loc_18000C747
0x18000c736  lea     rcx, [rax+10h]
0x18000c73a  mov     [rdi], rcx
0x18000c73d  mov     rax, [rcx]
0x18000c740  test    rax, rax
0x18000c743  jnz     short loc_18000C731
0x18000c745  jmp     short loc_18000C74E
0x18000c747  mov     rax, [rdi+10h]
0x18000c74b  mov     [rcx], rax
0x18000c74e  mov     qword ptr [rdi], 0
0x18000c755  mov     rbx, [rsp+28h+arg_0]
0x18000c75a  add     rsp, 20h
0x18000c75e  pop     rdi
0x18000c75f  retn
```
