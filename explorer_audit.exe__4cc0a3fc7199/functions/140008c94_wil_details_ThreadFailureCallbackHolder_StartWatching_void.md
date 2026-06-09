# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x140008c94`
- end: `0x140008dfe`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `362`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `11`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140008290`
- `0x140008bc0`
- `0x140008c70`
- `0x140085e74`
- `0x14008f81c`
- `0x1400aabd0`
- `0x1400f16a0`
- `0x140120e50`
- `0x140120fb8`
- `0x140190be0`
- `0x1401b5cc4`

## callees

- `0x140008c94`
- `0x1400740a4`
- `0x140104ce0`
- `0x1401db010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008de8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008de8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140008d69`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140008d69`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008d33`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008d33`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140008d45`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140008d45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140008cbd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140008d11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140008cbd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140008d11`

## string_xrefs

- `0x140008d62`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ThreadFailureCallbackHolder::StartWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  __int64 v2; // rsi
  unsigned __int64 CurrentThreadId; // r15
  unsigned __int64 v4; // rbp
  __int64 i; // rcx
  _QWORD *v6; // rcx
  HANDLE ProcessHeap; // r14
  char *v8; // rdi
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  signed __int64 v11; // rax
  const struct wil::FailureInfo *v12; // rdx
  _BYTE v13[216]; // [rsp+20h] [rbp-D8h] BYREF

  if ( *((_DWORD *)this + 6) )
  {
    memset_0(v13, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v13, v12);
  }
  v2 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    v4 = (CurrentThreadId >> 2) % 0xA;
    for ( i = *(_QWORD *)(v2 + 8 * v4); i; i = *(_QWORD *)(i + 8) )
    {
      if ( *(_DWORD *)i == (_DWORD)CurrentThreadId )
      {
        v6 = (_QWORD *)(i + 16);
        goto LABEL_8;
      }
    }
    ProcessHeap = GetProcessHeap();
    v8 = (char *)HeapAlloc(ProcessHeap, 0, 0x18u);
    ProcAddress = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation;
    if ( `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation
      || !`wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation
      && ((ModuleHandleW = GetModuleHandleW(L"ntdll.dll")) != 0
        ? (FARPROC)(ProcAddress = GetProcAddress(ModuleHandleW, "RtlDisownModuleHeapAllocation"),
                    `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation = (__int64)ProcAddress)
        : (ProcAddress = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation),
          `wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation = 1,
          ProcAddress) )
    {
      ((void (__fastcall *)(HANDLE, char *))ProcAddress)(ProcessHeap, v8);
    }
    if ( v8 )
    {
      *(_DWORD *)v8 = CurrentThreadId;
      *((_DWORD *)v8 + 1) = 0;
      *((_QWORD *)v8 + 1) = 0;
      v6 = v8 + 16;
      *((_QWORD *)v8 + 2) = 0;
      do
      {
        v11 = *(_QWORD *)(v2 + 8 * v4);
        *((_QWORD *)v8 + 1) = v11;
      }
      while ( v11 != _InterlockedCompareExchange64((volatile signed __int64 *)(v2 + 8 * v4), (signed __int64)v8, v11) );
    }
    else
    {
      v6 = 0;
    }
LABEL_8:
    *(_QWORD *)this = v6;
    if ( v6 )
    {
      *((_QWORD *)this + 2) = *v6;
      *v6 = this;
      *((_DWORD *)this + 6) = GetCurrentThreadId();
    }
  }
  else
  {
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x140008c94  push    rbx
0x140008c96  push    rbp
0x140008c97  push    rsi
0x140008c98  push    rdi
0x140008c99  push    r14
0x140008c9b  push    r15
0x140008c9d  sub     rsp, 0C8h
0x140008ca4  mov     rbx, rcx
0x140008ca7  cmp     dword ptr [rcx+18h], 0
0x140008cab  jnz     loc_140008DC1
0x140008cb1  mov     rsi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140008cb8  test    rsi, rsi
0x140008cbb  jz      short loc_140008D2A
0x140008cbd  call    cs:__imp_GetCurrentThreadId
0x140008cc3  mov     r15d, eax
0x140008cc6  mov     ebp, eax
0x140008cc8  shr     rbp, 2
0x140008ccc  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140008cd6  mul     rbp
0x140008cd9  shr     rdx, 3
0x140008cdd  lea     rcx, [rdx+rdx*4]
0x140008ce1  add     rcx, rcx
0x140008ce4  sub     rbp, rcx
0x140008ce7  mov     rcx, [rsi+rbp*8]
0x140008ceb  test    rcx, rcx
0x140008cee  jz      short loc_140008D33
0x140008cf0  cmp     [rcx], r15d
0x140008cf3  jz      short loc_140008CFB
0x140008cf5  mov     rcx, [rcx+8]
0x140008cf9  jmp     short loc_140008CEB
0x140008cfb  add     rcx, 10h
0x140008cff  mov     [rbx], rcx
0x140008d02  test    rcx, rcx
0x140008d05  jz      short loc_140008D1A
0x140008d07  mov     rax, [rcx]
0x140008d0a  mov     [rbx+10h], rax
0x140008d0e  mov     [rcx], rbx
0x140008d11  call    cs:__imp_GetCurrentThreadId
0x140008d17  mov     [rbx+18h], eax
0x140008d1a  add     rsp, 0C8h
0x140008d21  pop     r15
0x140008d23  pop     r14
0x140008d25  pop     rdi
0x140008d26  pop     rsi
0x140008d27  pop     rbp
0x140008d28  pop     rbx
0x140008d29  retn
0x140008d2a  mov     qword ptr [rcx], 0
0x140008d31  jmp     short loc_140008D1A
0x140008d33  call    cs:__imp_GetProcessHeap
0x140008d39  mov     r14, rax
0x140008d3c  xor     edx, edx; dwFlags
0x140008d3e  lea     r8d, [rdx+18h]; dwBytes
0x140008d42  mov     rcx, rax; hHeap
0x140008d45  call    cs:__imp_HeapAlloc
0x140008d4b  mov     rdi, rax
0x140008d4e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140008d55  test    rax, rax
0x140008d58  jnz     short loc_140008D87
0x140008d5a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140008d60  jnz     short loc_140008D93
0x140008d62  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x140008d69  call    cs:__imp_GetModuleHandleW
0x140008d6f  test    rax, rax
0x140008d72  jnz     short loc_140008DDE
0x140008d74  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140008d7b  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140008d82  test    rax, rax
0x140008d85  jz      short loc_140008D93
0x140008d87  mov     rdx, rdi
0x140008d8a  mov     rcx, r14
0x140008d8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008d92  nop
0x140008d93  test    rdi, rdi
0x140008d96  jz      short loc_140008DF7
0x140008d98  mov     [rdi], r15d
0x140008d9b  xor     eax, eax
0x140008d9d  mov     [rdi+4], eax
0x140008da0  mov     [rdi+8], rax
0x140008da4  lea     rcx, [rdi+10h]
0x140008da8  mov     [rcx], rax
0x140008dab  mov     rax, [rsi+rbp*8]
0x140008daf  mov     [rdi+8], rax
0x140008db3  lock cmpxchg [rsi+rbp*8], rdi
0x140008db9  jz      loc_140008CFF
0x140008dbf  jmp     short loc_140008DAB
0x140008dc1  xor     edx, edx; Val
0x140008dc3  mov     r8d, 98h; Size
0x140008dc9  lea     rcx, [rsp+0F8h+var_D8]; void *
0x140008dce  call    memset_0
0x140008dd3  lea     rcx, [rsp+0F8h+var_D8]; this
0x140008dd8  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140008dde  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x140008de5  mov     rcx, rax; hModule
0x140008de8  call    cs:__imp_GetProcAddress
0x140008dee  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140008df5  jmp     short loc_140008D7B
0x140008df7  xor     ecx, ecx
0x140008df9  jmp     loc_140008CFF
```
