# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x140003ef8`
- end: `0x140003f77`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `127`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140003b30`

## callees

- `0x140003ef8`
- `0x140034010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003f0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003f0e`

## string_xrefs

- `0x140003f2f`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x140003ef8  mov     [rsp+arg_0], rbx
0x140003efd  push    rdi
0x140003efe  sub     rsp, 20h
0x140003f02  mov     rdi, rcx
0x140003f05  cmp     dword ptr [rcx+18h], 0
0x140003f09  jz      short loc_140003F6B
0x140003f0b  mov     ebx, [rcx+18h]
0x140003f0e  call    cs:__imp_GetCurrentThreadId
0x140003f15  nop     dword ptr [rax+rax+00h]
0x140003f1a  cmp     ebx, eax
0x140003f1c  jz      short loc_140003F3B
0x140003f1e  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x140003f25  test    rax, rax
0x140003f28  jz      short loc_140003F3B
0x140003f2a  mov     rdx, [rsp+28h]
0x140003f2f  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x140003f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f3b  mov     dword ptr [rdi+18h], 0
0x140003f42  mov     rcx, [rdi]
0x140003f45  jmp     short loc_140003F53
0x140003f47  cmp     rax, rdi
0x140003f4a  jz      short loc_140003F5D
0x140003f4c  lea     rcx, [rax+10h]
0x140003f50  mov     [rdi], rcx
0x140003f53  mov     rax, [rcx]
0x140003f56  test    rax, rax
0x140003f59  jnz     short loc_140003F47
0x140003f5b  jmp     short loc_140003F64
0x140003f5d  mov     rax, [rdi+10h]
0x140003f61  mov     [rcx], rax
0x140003f64  mov     qword ptr [rdi], 0
0x140003f6b  mov     rbx, [rsp+28h+arg_0]
0x140003f70  add     rsp, 20h
0x140003f74  pop     rdi
0x140003f75  retn
```
