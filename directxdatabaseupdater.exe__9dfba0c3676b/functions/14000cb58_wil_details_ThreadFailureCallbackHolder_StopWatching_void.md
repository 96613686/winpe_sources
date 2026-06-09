# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x14000cb58`
- end: `0x14000cbbf`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140006190`
- `0x1400082c0`

## callees

- `0x14000cb58`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000cb61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000cb61`

## string_xrefs

- `0x14000cb7d`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x14000cb58  push    rbx
0x14000cb5a  sub     rsp, 20h
0x14000cb5e  mov     rbx, rcx
0x14000cb61  call    cs:__imp_GetCurrentThreadId
0x14000cb67  cmp     [rbx+18h], eax
0x14000cb6a  jz      short loc_14000CB89
0x14000cb6c  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x14000cb73  test    rax, rax
0x14000cb76  jz      short loc_14000CB89
0x14000cb78  mov     rdx, [rsp+28h]
0x14000cb7d  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x14000cb84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cb89  mov     rcx, [rbx]
0x14000cb8c  mov     dword ptr [rbx+18h], 0
0x14000cb93  jmp     short loc_14000CBA1
0x14000cb95  cmp     rax, rbx
0x14000cb98  jz      short loc_14000CBAB
0x14000cb9a  lea     rcx, [rax+10h]
0x14000cb9e  mov     [rbx], rcx
0x14000cba1  mov     rax, [rcx]
0x14000cba4  test    rax, rax
0x14000cba7  jnz     short loc_14000CB95
0x14000cba9  jmp     short loc_14000CBB2
0x14000cbab  mov     rax, [rbx+10h]
0x14000cbaf  mov     [rcx], rax
0x14000cbb2  mov     qword ptr [rbx], 0
0x14000cbb9  add     rsp, 20h
0x14000cbbd  pop     rbx
0x14000cbbe  retn
```
