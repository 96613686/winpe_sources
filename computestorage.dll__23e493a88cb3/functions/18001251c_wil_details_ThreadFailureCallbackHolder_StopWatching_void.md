# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x18001251c`
- end: `0x18001258a`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `110`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `17`
- callee_count: `2`
- tags: ``

## callers

- `0x180008ce8`
- `0x18000ffd4`
- `0x180010120`
- `0x180010420`
- `0x180010720`
- `0x180010a20`
- `0x180010d20`
- `0x180011020`
- `0x180011320`
- `0x180011620`
- `0x180011920`
- `0x180011c20`
- `0x180011f20`
- `0x180012220`
- `0x18001ba88`
- `0x1800203a8`
- `0x180020500`

## callees

- `0x18001251c`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012525`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012525`

## string_xrefs

- `0x180012547`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x18001251c  push    rbx
0x18001251e  sub     rsp, 20h
0x180012522  mov     rbx, rcx
0x180012525  call    cs:__imp_GetCurrentThreadId
0x18001252c  nop     dword ptr [rax+rax+00h]
0x180012531  cmp     [rbx+18h], eax
0x180012534  jz      short loc_180012553
0x180012536  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18001253d  test    rax, rax
0x180012540  jz      short loc_180012553
0x180012542  mov     rdx, [rsp+28h]
0x180012547  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18001254e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012553  mov     rcx, [rbx]
0x180012556  mov     dword ptr [rbx+18h], 0
0x18001255d  jmp     short loc_18001256B
0x18001255f  cmp     rax, rbx
0x180012562  jz      short loc_180012575
0x180012564  lea     rcx, [rax+10h]
0x180012568  mov     [rbx], rcx
0x18001256b  mov     rax, [rcx]
0x18001256e  test    rax, rax
0x180012571  jnz     short loc_18001255F
0x180012573  jmp     short loc_18001257C
0x180012575  mov     rax, [rbx+10h]
0x180012579  mov     [rcx], rax
0x18001257c  mov     qword ptr [rbx], 0
0x180012583  add     rsp, 20h
0x180012587  pop     rbx
0x180012588  retn
```
