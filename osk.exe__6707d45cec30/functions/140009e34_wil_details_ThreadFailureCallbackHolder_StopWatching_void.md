# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x140009e34`
- end: `0x140009e9b`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400053e4`

## callees

- `0x140009e34`
- `0x140027010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140009e3d`
- `KERNEL32!GetCurrentThreadId` at `0x140009e3d`

## string_xrefs

- `0x140009e59`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x140009e34  push    rbx
0x140009e36  sub     rsp, 20h
0x140009e3a  mov     rbx, rcx
0x140009e3d  call    cs:__imp_GetCurrentThreadId
0x140009e43  cmp     [rbx+18h], eax
0x140009e46  jz      short loc_140009E65
0x140009e48  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x140009e4f  test    rax, rax
0x140009e52  jz      short loc_140009E65
0x140009e54  mov     rdx, [rsp+28h]
0x140009e59  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x140009e60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009e65  mov     rcx, [rbx]
0x140009e68  mov     dword ptr [rbx+18h], 0
0x140009e6f  jmp     short loc_140009E7D
0x140009e71  cmp     rax, rbx
0x140009e74  jz      short loc_140009E87
0x140009e76  lea     rcx, [rax+10h]
0x140009e7a  mov     [rbx], rcx
0x140009e7d  mov     rax, [rcx]
0x140009e80  test    rax, rax
0x140009e83  jnz     short loc_140009E71
0x140009e85  jmp     short loc_140009E8E
0x140009e87  mov     rax, [rbx+10h]
0x140009e8b  mov     [rcx], rax
0x140009e8e  mov     qword ptr [rbx], 0
0x140009e95  add     rsp, 20h
0x140009e99  pop     rbx
0x140009e9a  retn
```
