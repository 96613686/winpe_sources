# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x140011ae4`
- end: `0x140011b5c`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400118a4`

## callees

- `0x140011ae4`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140011afa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140011afa`

## string_xrefs

- `0x140011b15`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x140011ae4  mov     [rsp+arg_0], rbx
0x140011ae9  push    rdi
0x140011aea  sub     rsp, 20h
0x140011aee  mov     rdi, rcx
0x140011af1  cmp     dword ptr [rcx+18h], 0
0x140011af5  jz      short loc_140011B51
0x140011af7  mov     ebx, [rcx+18h]
0x140011afa  call    cs:__imp_GetCurrentThreadId
0x140011b00  cmp     ebx, eax
0x140011b02  jz      short loc_140011B21
0x140011b04  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x140011b0b  test    rax, rax
0x140011b0e  jz      short loc_140011B21
0x140011b10  mov     rdx, [rsp+28h]
0x140011b15  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x140011b1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011b21  mov     dword ptr [rdi+18h], 0
0x140011b28  mov     rcx, [rdi]
0x140011b2b  jmp     short loc_140011B39
0x140011b2d  cmp     rax, rdi
0x140011b30  jz      short loc_140011B43
0x140011b32  lea     rcx, [rax+10h]
0x140011b36  mov     [rdi], rcx
0x140011b39  mov     rax, [rcx]
0x140011b3c  test    rax, rax
0x140011b3f  jnz     short loc_140011B2D
0x140011b41  jmp     short loc_140011B4A
0x140011b43  mov     rax, [rdi+10h]
0x140011b47  mov     [rcx], rax
0x140011b4a  mov     qword ptr [rdi], 0
0x140011b51  mov     rbx, [rsp+28h+arg_0]
0x140011b56  add     rsp, 20h
0x140011b5a  pop     rdi
0x140011b5b  retn
```
