# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x1800175cc`
- end: `0x180017633`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180014898`
- `0x180015a00`

## callees

- `0x1800175cc`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800175d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800175d5`

## string_xrefs

- `0x1800175f1`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x1800175cc  push    rbx
0x1800175ce  sub     rsp, 20h
0x1800175d2  mov     rbx, rcx
0x1800175d5  call    cs:__imp_GetCurrentThreadId
0x1800175db  cmp     [rbx+18h], eax
0x1800175de  jz      short loc_1800175FD
0x1800175e0  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x1800175e7  test    rax, rax
0x1800175ea  jz      short loc_1800175FD
0x1800175ec  mov     rdx, [rsp+28h]
0x1800175f1  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800175f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175fd  mov     rcx, [rbx]
0x180017600  mov     dword ptr [rbx+18h], 0
0x180017607  jmp     short loc_180017615
0x180017609  cmp     rax, rbx
0x18001760c  jz      short loc_18001761F
0x18001760e  lea     rcx, [rax+10h]
0x180017612  mov     [rbx], rcx
0x180017615  mov     rax, [rcx]
0x180017618  test    rax, rax
0x18001761b  jnz     short loc_180017609
0x18001761d  jmp     short loc_180017626
0x18001761f  mov     rax, [rbx+10h]
0x180017623  mov     [rcx], rax
0x180017626  mov     qword ptr [rbx], 0
0x18001762d  add     rsp, 20h
0x180017631  pop     rbx
0x180017632  retn
```
