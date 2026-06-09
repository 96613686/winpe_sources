# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x180006a54`
- end: `0x180006abb`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003b9c`
- `0x180004c64`

## callees

- `0x180006a54`
- `0x18001c010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180006a5d`
- `KERNEL32!GetCurrentThreadId` at `0x180006a5d`

## string_xrefs

- `0x180006a79`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x180006a54  push    rbx
0x180006a56  sub     rsp, 20h
0x180006a5a  mov     rbx, rcx
0x180006a5d  call    cs:__imp_GetCurrentThreadId
0x180006a63  cmp     [rbx+18h], eax
0x180006a66  jz      short loc_180006A85
0x180006a68  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180006a6f  test    rax, rax
0x180006a72  jz      short loc_180006A85
0x180006a74  mov     rdx, [rsp+28h]
0x180006a79  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180006a80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a85  mov     rcx, [rbx]
0x180006a88  mov     dword ptr [rbx+18h], 0
0x180006a8f  jmp     short loc_180006A9D
0x180006a91  cmp     rax, rbx
0x180006a94  jz      short loc_180006AA7
0x180006a96  lea     rcx, [rax+10h]
0x180006a9a  mov     [rbx], rcx
0x180006a9d  mov     rax, [rcx]
0x180006aa0  test    rax, rax
0x180006aa3  jnz     short loc_180006A91
0x180006aa5  jmp     short loc_180006AAE
0x180006aa7  mov     rax, [rbx+10h]
0x180006aab  mov     [rcx], rax
0x180006aae  mov     qword ptr [rbx], 0
0x180006ab5  add     rsp, 20h
0x180006ab9  pop     rbx
0x180006aba  retn
```
