# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x1800057b0`
- end: `0x180005828`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005240`

## callees

- `0x1800057b0`
- `0x18000b010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800057c6`
- `KERNEL32!GetCurrentThreadId` at `0x1800057c6`

## string_xrefs

- `0x1800057e1`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(
        wil::details::ThreadFailureCallbackHolder *this)
{
  int v2; // ebx
  wil::details::ThreadFailureCallbackHolder **v3; // rcx
  wil::details::ThreadFailureCallbackHolder *v4; // rax
  void *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_DWORD *)this + 6) )
  {
    v2 = *((_DWORD *)this + 6);
    if ( v2 != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    *((_DWORD *)this + 6) = 0;
    v3 = *(wil::details::ThreadFailureCallbackHolder ***)this;
    while ( 1 )
    {
      v4 = *v3;
      if ( !*v3 )
        break;
      if ( v4 == this )
      {
        *v3 = (wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)this + 2);
        break;
      }
      v3 = (wil::details::ThreadFailureCallbackHolder **)((char *)v4 + 16);
      *(_QWORD *)this = (char *)v4 + 16;
    }
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x1800057b0  mov     [rsp+arg_0], rbx
0x1800057b5  push    rdi
0x1800057b6  sub     rsp, 20h
0x1800057ba  mov     rdi, rcx
0x1800057bd  cmp     dword ptr [rcx+18h], 0
0x1800057c1  jz      short loc_18000581D
0x1800057c3  mov     ebx, [rcx+18h]
0x1800057c6  call    cs:__imp_GetCurrentThreadId
0x1800057cc  cmp     ebx, eax
0x1800057ce  jz      short loc_1800057ED
0x1800057d0  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x1800057d7  test    rax, rax
0x1800057da  jz      short loc_1800057ED
0x1800057dc  mov     rdx, [rsp+28h]
0x1800057e1  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800057e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057ed  mov     dword ptr [rdi+18h], 0
0x1800057f4  mov     rcx, [rdi]
0x1800057f7  jmp     short loc_180005805
0x1800057f9  cmp     rax, rdi
0x1800057fc  jz      short loc_18000580F
0x1800057fe  lea     rcx, [rax+10h]
0x180005802  mov     [rdi], rcx
0x180005805  mov     rax, [rcx]
0x180005808  test    rax, rax
0x18000580b  jnz     short loc_1800057F9
0x18000580d  jmp     short loc_180005816
0x18000580f  mov     rax, [rdi+10h]
0x180005813  mov     [rcx], rax
0x180005816  mov     qword ptr [rdi], 0
0x18000581d  mov     rbx, [rsp+28h+arg_0]
0x180005822  add     rsp, 20h
0x180005826  pop     rdi
0x180005827  retn
```
