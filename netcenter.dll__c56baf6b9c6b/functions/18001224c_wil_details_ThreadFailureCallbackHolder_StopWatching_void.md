# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x18001224c`
- end: `0x1800122b3`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180008598`
- `0x18000bcd8`

## callees

- `0x18001224c`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012255`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012255`

## string_xrefs

- `0x180012271`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x18001224c  push    rbx
0x18001224e  sub     rsp, 20h
0x180012252  mov     rbx, rcx
0x180012255  call    cs:__imp_GetCurrentThreadId
0x18001225b  cmp     [rbx+18h], eax
0x18001225e  jz      short loc_18001227D
0x180012260  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180012267  test    rax, rax
0x18001226a  jz      short loc_18001227D
0x18001226c  mov     rdx, [rsp+28h]
0x180012271  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180012278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001227d  mov     rcx, [rbx]
0x180012280  mov     dword ptr [rbx+18h], 0
0x180012287  jmp     short loc_180012295
0x180012289  cmp     rax, rbx
0x18001228c  jz      short loc_18001229F
0x18001228e  lea     rcx, [rax+10h]
0x180012292  mov     [rbx], rcx
0x180012295  mov     rax, [rcx]
0x180012298  test    rax, rax
0x18001229b  jnz     short loc_180012289
0x18001229d  jmp     short loc_1800122A6
0x18001229f  mov     rax, [rbx+10h]
0x1800122a3  mov     [rcx], rax
0x1800122a6  mov     qword ptr [rbx], 0
0x1800122ad  add     rsp, 20h
0x1800122b1  pop     rbx
0x1800122b2  retn
```
