# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x140003c28`
- end: `0x140003ca0`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140003720`

## callees

- `0x140003c28`
- `0x140010010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140003c3e`
- `KERNEL32!GetCurrentThreadId` at `0x140003c3e`

## string_xrefs

- `0x140003c59`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
    v3 = *(wil::details::ThreadFailureCallbackHolder ***)this;
    *((_DWORD *)this + 6) = 0;
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
0x140003c28  mov     [rsp+arg_0], rbx
0x140003c2d  push    rdi
0x140003c2e  sub     rsp, 20h
0x140003c32  cmp     dword ptr [rcx+18h], 0
0x140003c36  mov     rdi, rcx
0x140003c39  jz      short loc_140003C95
0x140003c3b  mov     ebx, [rcx+18h]
0x140003c3e  call    cs:__imp_GetCurrentThreadId
0x140003c44  cmp     ebx, eax
0x140003c46  jz      short loc_140003C65
0x140003c48  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x140003c4f  test    rax, rax
0x140003c52  jz      short loc_140003C65
0x140003c54  mov     rdx, [rsp+28h]
0x140003c59  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x140003c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003c65  mov     rcx, [rdi]
0x140003c68  mov     dword ptr [rdi+18h], 0
0x140003c6f  jmp     short loc_140003C7D
0x140003c71  cmp     rax, rdi
0x140003c74  jz      short loc_140003C87
0x140003c76  lea     rcx, [rax+10h]
0x140003c7a  mov     [rdi], rcx
0x140003c7d  mov     rax, [rcx]
0x140003c80  test    rax, rax
0x140003c83  jnz     short loc_140003C71
0x140003c85  jmp     short loc_140003C8E
0x140003c87  mov     rax, [rdi+10h]
0x140003c8b  mov     [rcx], rax
0x140003c8e  mov     qword ptr [rdi], 0
0x140003c95  mov     rbx, [rsp+28h+arg_0]
0x140003c9a  add     rsp, 20h
0x140003c9e  pop     rdi
0x140003c9f  retn
```
