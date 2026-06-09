# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x18000872c`
- end: `0x1800087a4`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180007d5c`
- `0x180015010`

## callees

- `0x18000872c`
- `0x180023010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180008742`
- `KERNEL32!GetCurrentThreadId` at `0x180008742`

## string_xrefs

- `0x18000875d`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x18000872c  mov     [rsp+arg_0], rbx
0x180008731  push    rdi
0x180008732  sub     rsp, 20h
0x180008736  mov     rdi, rcx
0x180008739  cmp     dword ptr [rcx+18h], 0
0x18000873d  jz      short loc_180008799
0x18000873f  mov     ebx, [rcx+18h]
0x180008742  call    cs:__imp_GetCurrentThreadId
0x180008748  cmp     ebx, eax
0x18000874a  jz      short loc_180008769
0x18000874c  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180008753  test    rax, rax
0x180008756  jz      short loc_180008769
0x180008758  mov     rdx, [rsp+28h]
0x18000875d  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180008764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008769  mov     dword ptr [rdi+18h], 0
0x180008770  mov     rcx, [rdi]
0x180008773  jmp     short loc_180008781
0x180008775  cmp     rax, rdi
0x180008778  jz      short loc_18000878B
0x18000877a  lea     rcx, [rax+10h]
0x18000877e  mov     [rdi], rcx
0x180008781  mov     rax, [rcx]
0x180008784  test    rax, rax
0x180008787  jnz     short loc_180008775
0x180008789  jmp     short loc_180008792
0x18000878b  mov     rax, [rdi+10h]
0x18000878f  mov     [rcx], rax
0x180008792  mov     qword ptr [rdi], 0
0x180008799  mov     rbx, [rsp+28h+arg_0]
0x18000879e  add     rsp, 20h
0x1800087a2  pop     rdi
0x1800087a3  retn
```
