# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x18000efc4`
- end: `0x18000f02b`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000aca4`
- `0x18000d524`

## callees

- `0x18000efc4`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000efcd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000efcd`

## string_xrefs

- `0x18000efe9`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x18000efc4  push    rbx
0x18000efc6  sub     rsp, 20h
0x18000efca  mov     rbx, rcx
0x18000efcd  call    cs:__imp_GetCurrentThreadId
0x18000efd3  cmp     [rbx+18h], eax
0x18000efd6  jz      short loc_18000EFF5
0x18000efd8  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000efdf  test    rax, rax
0x18000efe2  jz      short loc_18000EFF5
0x18000efe4  mov     rdx, [rsp+28h]
0x18000efe9  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000eff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eff5  mov     rcx, [rbx]
0x18000eff8  mov     dword ptr [rbx+18h], 0
0x18000efff  jmp     short loc_18000F00D
0x18000f001  cmp     rax, rbx
0x18000f004  jz      short loc_18000F017
0x18000f006  lea     rcx, [rax+10h]
0x18000f00a  mov     [rbx], rcx
0x18000f00d  mov     rax, [rcx]
0x18000f010  test    rax, rax
0x18000f013  jnz     short loc_18000F001
0x18000f015  jmp     short loc_18000F01E
0x18000f017  mov     rax, [rbx+10h]
0x18000f01b  mov     [rcx], rax
0x18000f01e  mov     qword ptr [rbx], 0
0x18000f025  add     rsp, 20h
0x18000f029  pop     rbx
0x18000f02a  retn
```
