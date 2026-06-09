# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x1400057c8`
- end: `0x140005840`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140004d8c`

## callees

- `0x1400057c8`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400057de`
- `KERNEL32!GetCurrentThreadId` at `0x1400057de`

## string_xrefs

- `0x1400057f9`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x1400057c8  mov     [rsp+arg_0], rbx
0x1400057cd  push    rdi
0x1400057ce  sub     rsp, 20h
0x1400057d2  mov     rdi, rcx
0x1400057d5  cmp     dword ptr [rcx+18h], 0
0x1400057d9  jz      short loc_140005835
0x1400057db  mov     ebx, [rcx+18h]
0x1400057de  call    cs:__imp_GetCurrentThreadId
0x1400057e4  cmp     ebx, eax
0x1400057e6  jz      short loc_140005805
0x1400057e8  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x1400057ef  test    rax, rax
0x1400057f2  jz      short loc_140005805
0x1400057f4  mov     rdx, [rsp+28h]
0x1400057f9  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x140005800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005805  mov     dword ptr [rdi+18h], 0
0x14000580c  mov     rcx, [rdi]
0x14000580f  jmp     short loc_14000581D
0x140005811  cmp     rax, rdi
0x140005814  jz      short loc_140005827
0x140005816  lea     rcx, [rax+10h]
0x14000581a  mov     [rdi], rcx
0x14000581d  mov     rax, [rcx]
0x140005820  test    rax, rax
0x140005823  jnz     short loc_140005811
0x140005825  jmp     short loc_14000582E
0x140005827  mov     rax, [rdi+10h]
0x14000582b  mov     [rcx], rax
0x14000582e  mov     qword ptr [rdi], 0
0x140005835  mov     rbx, [rsp+28h+arg_0]
0x14000583a  add     rsp, 20h
0x14000583e  pop     rdi
0x14000583f  retn
```
