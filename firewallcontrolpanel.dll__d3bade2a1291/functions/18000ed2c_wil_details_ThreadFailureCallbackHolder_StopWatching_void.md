# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x18000ed2c`
- end: `0x18000ed93`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c3ec`
- `0x18000cc84`
- `0x180016a30`

## callees

- `0x18000ed2c`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ed35`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ed35`

## string_xrefs

- `0x18000ed51`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x18000ed2c  push    rbx
0x18000ed2e  sub     rsp, 20h
0x18000ed32  mov     rbx, rcx
0x18000ed35  call    cs:__imp_GetCurrentThreadId
0x18000ed3b  cmp     [rbx+18h], eax
0x18000ed3e  jz      short loc_18000ED5D
0x18000ed40  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000ed47  test    rax, rax
0x18000ed4a  jz      short loc_18000ED5D
0x18000ed4c  mov     rdx, [rsp+28h]
0x18000ed51  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000ed58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed5d  mov     rcx, [rbx]
0x18000ed60  mov     dword ptr [rbx+18h], 0
0x18000ed67  jmp     short loc_18000ED75
0x18000ed69  cmp     rax, rbx
0x18000ed6c  jz      short loc_18000ED7F
0x18000ed6e  lea     rcx, [rax+10h]
0x18000ed72  mov     [rbx], rcx
0x18000ed75  mov     rax, [rcx]
0x18000ed78  test    rax, rax
0x18000ed7b  jnz     short loc_18000ED69
0x18000ed7d  jmp     short loc_18000ED86
0x18000ed7f  mov     rax, [rbx+10h]
0x18000ed83  mov     [rcx], rax
0x18000ed86  mov     qword ptr [rbx], 0
0x18000ed8d  add     rsp, 20h
0x18000ed91  pop     rbx
0x18000ed92  retn
```
