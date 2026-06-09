# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x18000de0c`
- end: `0x18000de73`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180008fbc`
- `0x18000b044`

## callees

- `0x18000de0c`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000de15`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000de15`

## string_xrefs

- `0x18000de31`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x18000de0c  push    rbx
0x18000de0e  sub     rsp, 20h
0x18000de12  mov     rbx, rcx
0x18000de15  call    cs:__imp_GetCurrentThreadId
0x18000de1b  cmp     [rbx+18h], eax
0x18000de1e  jz      short loc_18000DE3D
0x18000de20  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000de27  test    rax, rax
0x18000de2a  jz      short loc_18000DE3D
0x18000de2c  mov     rdx, [rsp+28h]
0x18000de31  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000de38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de3d  mov     rcx, [rbx]
0x18000de40  mov     dword ptr [rbx+18h], 0
0x18000de47  jmp     short loc_18000DE55
0x18000de49  cmp     rax, rbx
0x18000de4c  jz      short loc_18000DE5F
0x18000de4e  lea     rcx, [rax+10h]
0x18000de52  mov     [rbx], rcx
0x18000de55  mov     rax, [rcx]
0x18000de58  test    rax, rax
0x18000de5b  jnz     short loc_18000DE49
0x18000de5d  jmp     short loc_18000DE66
0x18000de5f  mov     rax, [rbx+10h]
0x18000de63  mov     [rcx], rax
0x18000de66  mov     qword ptr [rbx], 0
0x18000de6d  add     rsp, 20h
0x18000de71  pop     rbx
0x18000de72  retn
```
