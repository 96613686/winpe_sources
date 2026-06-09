# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x1800092e4`
- end: `0x18000935c`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800087f0`
- `0x180008868`
- `0x180010700`
- `0x180011130`

## callees

- `0x1800092e4`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800092fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800092fa`

## string_xrefs

- `0x180009315`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x1800092e4  mov     [rsp+arg_0], rbx
0x1800092e9  push    rdi
0x1800092ea  sub     rsp, 20h
0x1800092ee  mov     rdi, rcx
0x1800092f1  cmp     dword ptr [rcx+18h], 0
0x1800092f5  jz      short loc_180009351
0x1800092f7  mov     ebx, [rcx+18h]
0x1800092fa  call    cs:__imp_GetCurrentThreadId
0x180009300  cmp     ebx, eax
0x180009302  jz      short loc_180009321
0x180009304  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000930b  test    rax, rax
0x18000930e  jz      short loc_180009321
0x180009310  mov     rdx, [rsp+28h]
0x180009315  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000931c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009321  mov     dword ptr [rdi+18h], 0
0x180009328  mov     rcx, [rdi]
0x18000932b  jmp     short loc_180009339
0x18000932d  cmp     rax, rdi
0x180009330  jz      short loc_180009343
0x180009332  lea     rcx, [rax+10h]
0x180009336  mov     [rdi], rcx
0x180009339  mov     rax, [rcx]
0x18000933c  test    rax, rax
0x18000933f  jnz     short loc_18000932D
0x180009341  jmp     short loc_18000934A
0x180009343  mov     rax, [rdi+10h]
0x180009347  mov     [rcx], rax
0x18000934a  mov     qword ptr [rdi], 0
0x180009351  mov     rbx, [rsp+28h+arg_0]
0x180009356  add     rsp, 20h
0x18000935a  pop     rdi
0x18000935b  retn
```
