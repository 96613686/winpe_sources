# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x18000d764`
- end: `0x18000d7cb`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180008d8c`
- `0x180009328`

## callees

- `0x18000d764`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d76d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d76d`

## string_xrefs

- `0x18000d789`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x18000d764  push    rbx
0x18000d766  sub     rsp, 20h
0x18000d76a  mov     rbx, rcx
0x18000d76d  call    cs:__imp_GetCurrentThreadId
0x18000d773  cmp     [rbx+18h], eax
0x18000d776  jz      short loc_18000D795
0x18000d778  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000d77f  test    rax, rax
0x18000d782  jz      short loc_18000D795
0x18000d784  mov     rdx, [rsp+28h]
0x18000d789  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000d790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d795  mov     rcx, [rbx]
0x18000d798  mov     dword ptr [rbx+18h], 0
0x18000d79f  jmp     short loc_18000D7AD
0x18000d7a1  cmp     rax, rbx
0x18000d7a4  jz      short loc_18000D7B7
0x18000d7a6  lea     rcx, [rax+10h]
0x18000d7aa  mov     [rbx], rcx
0x18000d7ad  mov     rax, [rcx]
0x18000d7b0  test    rax, rax
0x18000d7b3  jnz     short loc_18000D7A1
0x18000d7b5  jmp     short loc_18000D7BE
0x18000d7b7  mov     rax, [rbx+10h]
0x18000d7bb  mov     [rcx], rax
0x18000d7be  mov     qword ptr [rbx], 0
0x18000d7c5  add     rsp, 20h
0x18000d7c9  pop     rbx
0x18000d7ca  retn
```
