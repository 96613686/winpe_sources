# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x140006c50`
- end: `0x140006cc8`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140005f4c`

## callees

- `0x140006c50`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006c66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006c66`

## string_xrefs

- `0x140006c81`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x140006c50  mov     [rsp+arg_0], rbx
0x140006c55  push    rdi
0x140006c56  sub     rsp, 20h
0x140006c5a  mov     rdi, rcx
0x140006c5d  cmp     dword ptr [rcx+18h], 0
0x140006c61  jz      short loc_140006CBD
0x140006c63  mov     ebx, [rcx+18h]
0x140006c66  call    cs:__imp_GetCurrentThreadId
0x140006c6c  cmp     ebx, eax
0x140006c6e  jz      short loc_140006C8D
0x140006c70  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x140006c77  test    rax, rax
0x140006c7a  jz      short loc_140006C8D
0x140006c7c  mov     rdx, [rsp+28h]
0x140006c81  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x140006c88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c8d  mov     dword ptr [rdi+18h], 0
0x140006c94  mov     rcx, [rdi]
0x140006c97  jmp     short loc_140006CA5
0x140006c99  cmp     rax, rdi
0x140006c9c  jz      short loc_140006CAF
0x140006c9e  lea     rcx, [rax+10h]
0x140006ca2  mov     [rdi], rcx
0x140006ca5  mov     rax, [rcx]
0x140006ca8  test    rax, rax
0x140006cab  jnz     short loc_140006C99
0x140006cad  jmp     short loc_140006CB6
0x140006caf  mov     rax, [rdi+10h]
0x140006cb3  mov     [rcx], rax
0x140006cb6  mov     qword ptr [rdi], 0
0x140006cbd  mov     rbx, [rsp+28h+arg_0]
0x140006cc2  add     rsp, 20h
0x140006cc6  pop     rdi
0x140006cc7  retn
```
