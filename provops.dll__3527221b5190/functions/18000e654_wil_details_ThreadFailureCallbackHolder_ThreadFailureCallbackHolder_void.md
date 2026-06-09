# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x18000e654`
- end: `0x18000e6cc`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d0fc`
- `0x18000d170`
- `0x18000d1e4`

## callees

- `0x18000e654`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e66a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e66a`

## string_xrefs

- `0x18000e685`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x18000e654  mov     [rsp+arg_0], rbx
0x18000e659  push    rdi
0x18000e65a  sub     rsp, 20h
0x18000e65e  mov     rdi, rcx
0x18000e661  cmp     dword ptr [rcx+18h], 0
0x18000e665  jz      short loc_18000E6C1
0x18000e667  mov     ebx, [rcx+18h]
0x18000e66a  call    cs:__imp_GetCurrentThreadId
0x18000e670  cmp     ebx, eax
0x18000e672  jz      short loc_18000E691
0x18000e674  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000e67b  test    rax, rax
0x18000e67e  jz      short loc_18000E691
0x18000e680  mov     rdx, [rsp+28h]
0x18000e685  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000e68c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e691  mov     dword ptr [rdi+18h], 0
0x18000e698  mov     rcx, [rdi]
0x18000e69b  jmp     short loc_18000E6A9
0x18000e69d  cmp     rax, rdi
0x18000e6a0  jz      short loc_18000E6B3
0x18000e6a2  lea     rcx, [rax+10h]
0x18000e6a6  mov     [rdi], rcx
0x18000e6a9  mov     rax, [rcx]
0x18000e6ac  test    rax, rax
0x18000e6af  jnz     short loc_18000E69D
0x18000e6b1  jmp     short loc_18000E6BA
0x18000e6b3  mov     rax, [rdi+10h]
0x18000e6b7  mov     [rcx], rax
0x18000e6ba  mov     qword ptr [rdi], 0
0x18000e6c1  mov     rbx, [rsp+28h+arg_0]
0x18000e6c6  add     rsp, 20h
0x18000e6ca  pop     rdi
0x18000e6cb  retn
```
