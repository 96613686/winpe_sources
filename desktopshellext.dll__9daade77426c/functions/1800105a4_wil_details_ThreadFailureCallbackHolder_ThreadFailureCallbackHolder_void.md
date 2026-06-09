# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x1800105a4`
- end: `0x18001061a`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `118`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180035f50`
- `0x1800558a8`

## callees

- `0x1800105a4`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800105ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800105ba`

## string_xrefs

- `0x1800105d5`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(
        wil::details::ThreadFailureCallbackHolder *this)
{
  int v2; // ebx
  wil::details::ThreadFailureCallbackHolder *v3; // rax
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
    while ( 1 )
    {
      v3 = **(wil::details::ThreadFailureCallbackHolder ***)this;
      if ( !v3 )
        break;
      if ( v3 == this )
      {
        **(_QWORD **)this = *((_QWORD *)this + 2);
        break;
      }
      *(_QWORD *)this = (char *)v3 + 16;
    }
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x1800105a4  mov     [rsp+arg_0], rbx
0x1800105a9  push    rdi
0x1800105aa  sub     rsp, 20h
0x1800105ae  mov     rdi, rcx
0x1800105b1  cmp     dword ptr [rcx+18h], 0
0x1800105b5  jz      short loc_18001060F
0x1800105b7  mov     ebx, [rcx+18h]
0x1800105ba  call    cs:__imp_GetCurrentThreadId
0x1800105c0  cmp     ebx, eax
0x1800105c2  jz      short loc_1800105E1
0x1800105c4  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x1800105cb  test    rax, rax
0x1800105ce  jz      short loc_1800105E1
0x1800105d0  mov     rdx, [rsp+28h]
0x1800105d5  lea     rcx, aMemoryCorrupti
0x1800105dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105e1  mov     dword ptr [rdi+18h], 0
0x1800105e8  mov     rcx, [rdi]
0x1800105eb  mov     rax, [rcx]
0x1800105ee  test    rax, rax
0x1800105f1  jz      short loc_180010608
0x1800105f3  cmp     rax, rdi
0x1800105f6  jz      short loc_180010601
0x1800105f8  add     rax, 10h
0x1800105fc  mov     [rdi], rax
0x1800105ff  jmp     short loc_1800105E8
0x180010601  mov     rax, [rdi+10h]
0x180010605  mov     [rcx], rax
0x180010608  mov     qword ptr [rdi], 0
0x18001060f  mov     rbx, [rsp+28h+arg_0]
0x180010614  add     rsp, 20h
0x180010618  pop     rdi
0x180010619  retn
```
