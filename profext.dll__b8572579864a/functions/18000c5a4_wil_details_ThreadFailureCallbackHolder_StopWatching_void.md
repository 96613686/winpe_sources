# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x18000c5a4`
- end: `0x18000c612`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `110`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c588`

## callees

- `0x18000c5a4`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c5ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c5ad`

## string_xrefs

- `0x18000c5cf`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x18000c5a4  push    rbx
0x18000c5a6  sub     rsp, 20h
0x18000c5aa  mov     rbx, rcx
0x18000c5ad  call    cs:__imp_GetCurrentThreadId
0x18000c5b4  nop     dword ptr [rax+rax+00h]
0x18000c5b9  cmp     [rbx+18h], eax
0x18000c5bc  jz      short loc_18000C5DB
0x18000c5be  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000c5c5  test    rax, rax
0x18000c5c8  jz      short loc_18000C5DB
0x18000c5ca  mov     rdx, [rsp+28h]
0x18000c5cf  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000c5d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5db  mov     rcx, [rbx]
0x18000c5de  mov     dword ptr [rbx+18h], 0
0x18000c5e5  jmp     short loc_18000C5F3
0x18000c5e7  cmp     rax, rbx
0x18000c5ea  jz      short loc_18000C5FD
0x18000c5ec  lea     rcx, [rax+10h]
0x18000c5f0  mov     [rbx], rcx
0x18000c5f3  mov     rax, [rcx]
0x18000c5f6  test    rax, rax
0x18000c5f9  jnz     short loc_18000C5E7
0x18000c5fb  jmp     short loc_18000C604
0x18000c5fd  mov     rax, [rbx+10h]
0x18000c601  mov     [rcx], rax
0x18000c604  mov     qword ptr [rbx], 0
0x18000c60b  add     rsp, 20h
0x18000c60f  pop     rbx
0x18000c610  retn
```
