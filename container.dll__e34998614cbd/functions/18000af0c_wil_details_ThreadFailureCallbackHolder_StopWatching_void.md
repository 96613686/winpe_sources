# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x18000af0c`
- end: `0x18000af7a`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `110`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `18`
- callee_count: `2`
- tags: ``

## callers

- `0x180005038`
- `0x18000ac60`
- `0x18000d028`
- `0x180010418`
- `0x18001054c`
- `0x1800106b0`
- `0x180010820`
- `0x180010ac0`
- `0x180010d70`
- `0x180011010`
- `0x1800112c0`
- `0x180011560`
- `0x180011810`
- `0x180011ab0`
- `0x180011d50`
- `0x180020dc0`
- `0x18002bd20`
- `0x18002bfc0`

## callees

- `0x18000af0c`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000af15`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000af15`

## string_xrefs

- `0x18000af37`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x18000af0c  push    rbx
0x18000af0e  sub     rsp, 20h
0x18000af12  mov     rbx, rcx
0x18000af15  call    cs:__imp_GetCurrentThreadId
0x18000af1c  nop     dword ptr [rax+rax+00h]
0x18000af21  cmp     [rbx+18h], eax
0x18000af24  jz      short loc_18000AF43
0x18000af26  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000af2d  test    rax, rax
0x18000af30  jz      short loc_18000AF43
0x18000af32  mov     rdx, [rsp+28h]
0x18000af37  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000af3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af43  mov     rcx, [rbx]
0x18000af46  mov     dword ptr [rbx+18h], 0
0x18000af4d  jmp     short loc_18000AF5B
0x18000af4f  cmp     rax, rbx
0x18000af52  jz      short loc_18000AF65
0x18000af54  lea     rcx, [rax+10h]
0x18000af58  mov     [rbx], rcx
0x18000af5b  mov     rax, [rcx]
0x18000af5e  test    rax, rax
0x18000af61  jnz     short loc_18000AF4F
0x18000af63  jmp     short loc_18000AF6C
0x18000af65  mov     rax, [rbx+10h]
0x18000af69  mov     [rcx], rax
0x18000af6c  mov     qword ptr [rbx], 0
0x18000af73  add     rsp, 20h
0x18000af77  pop     rbx
0x18000af78  retn
```
