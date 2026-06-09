# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x18000b8f0`
- end: `0x18000ba77`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `391`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `7`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b7c0`
- `0x18000b800`
- `0x180013080`
- `0x18001f14c`
- `0x18001f418`
- `0x1800210ec`
- `0x1800394e0`

## callees

- `0x18000b8f0`
- `0x18002af50`
- `0x18002ebb0`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ba5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ba5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b995`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b995`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b971`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b971`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b95d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b95d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b91d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ba01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b91d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ba01`

## string_xrefs

- `0x18000b98e`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ThreadFailureCallbackHolder::StartWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  __int64 v2; // rsi
  unsigned __int64 CurrentThreadId; // r14
  unsigned __int64 v4; // r15
  __int64 i; // rcx
  HANDLE ProcessHeap; // rbp
  char *v7; // rdi
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  _QWORD *v10; // rcx
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
    v4 = 8 * ((CurrentThreadId >> 2) % 0xA);
    for ( i = *(_QWORD *)(v4 + v2); i; i = *(_QWORD *)(i + 8) )
    {
      if ( *(_DWORD *)i == (_DWORD)CurrentThreadId )
      {
        v10 = (_QWORD *)(i + 16);
        goto LABEL_14;
      }
    }
    ProcessHeap = GetProcessHeap();
    v7 = (char *)HeapAlloc(ProcessHeap, 0, 0x18u);
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
      ((void (__fastcall *)(HANDLE, char *))ProcAddress)(ProcessHeap, v7);
    }
    if ( v7 )
    {
      *(_DWORD *)v7 = CurrentThreadId;
      *((_DWORD *)v7 + 1) = 0;
      *((_QWORD *)v7 + 1) = 0;
      v10 = v7 + 16;
      *((_QWORD *)v7 + 2) = 0;
      do
      {
        v11 = *(_QWORD *)(v4 + v2);
        *((_QWORD *)v7 + 1) = v11;
      }
      while ( v11 != _InterlockedCompareExchange64((volatile signed __int64 *)(v4 + v2), (signed __int64)v7, v11) );
    }
    else
    {
      v10 = 0;
    }
LABEL_14:
    *(_QWORD *)this = v10;
    if ( v10 )
    {
      *((_QWORD *)this + 2) = *v10;
      *v10 = this;
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
0x18000b8f0  push    rbx
0x18000b8f2  push    rbp
0x18000b8f3  push    rsi
0x18000b8f4  push    rdi
0x18000b8f5  push    r14
0x18000b8f7  push    r15
0x18000b8f9  sub     rsp, 0C8h
0x18000b900  mov     rbx, rcx
0x18000b903  cmp     dword ptr [rcx+18h], 0
0x18000b907  jnz     loc_18000BA37
0x18000b90d  mov     rsi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000b914  test    rsi, rsi
0x18000b917  jz      loc_18000BA28
0x18000b91d  call    cs:__imp_GetCurrentThreadId
0x18000b923  mov     r14d, eax
0x18000b926  mov     r8d, eax
0x18000b929  shr     r8, 2
0x18000b92d  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000b937  mul     r8
0x18000b93a  shr     rdx, 3
0x18000b93e  lea     rcx, [rdx+rdx*4]
0x18000b942  add     rcx, rcx
0x18000b945  sub     r8, rcx
0x18000b948  lea     r15, ds:0[r8*8]
0x18000b950  mov     rcx, [r15+rsi]
0x18000b954  test    rcx, rcx
0x18000b957  jnz     loc_18000BA1A
0x18000b95d  call    cs:__imp_GetProcessHeap
0x18000b963  mov     rbp, rax
0x18000b966  xor     edx, edx; dwFlags
0x18000b968  mov     r8d, 18h; dwBytes
0x18000b96e  mov     rcx, rax; hHeap
0x18000b971  call    cs:__imp_HeapAlloc
0x18000b977  mov     rdi, rax
0x18000b97a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000b981  test    rax, rax
0x18000b984  jnz     short loc_18000B9B7
0x18000b986  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000b98c  jnz     short loc_18000B9C3
0x18000b98e  lea     rcx, ModuleName; "ntdll.dll"
0x18000b995  call    cs:__imp_GetModuleHandleW
0x18000b99b  test    rax, rax
0x18000b99e  jnz     loc_18000BA54
0x18000b9a4  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000b9ab  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000b9b2  test    rax, rax
0x18000b9b5  jz      short loc_18000B9C3
0x18000b9b7  mov     rdx, rdi
0x18000b9ba  mov     rcx, rbp
0x18000b9bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9c2  nop
0x18000b9c3  test    rdi, rdi
0x18000b9c6  jz      loc_18000BA70
0x18000b9cc  mov     [rdi], r14d
0x18000b9cf  xor     eax, eax
0x18000b9d1  mov     [rdi+4], eax
0x18000b9d4  mov     [rdi+8], rax
0x18000b9d8  lea     rcx, [rdi+10h]
0x18000b9dc  mov     [rcx], rax
0x18000b9df  mov     rax, [r15+rsi]
0x18000b9e3  mov     [rdi+8], rax
0x18000b9e7  lock cmpxchg [r15+rsi], rdi
0x18000b9ed  jnz     short loc_18000B9DF
0x18000b9ef  mov     [rbx], rcx
0x18000b9f2  test    rcx, rcx
0x18000b9f5  jz      short loc_18000BA0A
0x18000b9f7  mov     rax, [rcx]
0x18000b9fa  mov     [rbx+10h], rax
0x18000b9fe  mov     [rcx], rbx
0x18000ba01  call    cs:__imp_GetCurrentThreadId
0x18000ba07  mov     [rbx+18h], eax
0x18000ba0a  add     rsp, 0C8h
0x18000ba11  pop     r15
0x18000ba13  pop     r14
0x18000ba15  pop     rdi
0x18000ba16  pop     rsi
0x18000ba17  pop     rbp
0x18000ba18  pop     rbx
0x18000ba19  retn
0x18000ba1a  cmp     [rcx], r14d
0x18000ba1d  jz      short loc_18000BA31
0x18000ba1f  mov     rcx, [rcx+8]
0x18000ba23  jmp     loc_18000B954
0x18000ba28  mov     qword ptr [rcx], 0
0x18000ba2f  jmp     short loc_18000BA0A
0x18000ba31  add     rcx, 10h
0x18000ba35  jmp     short loc_18000B9EF
0x18000ba37  xor     edx, edx; Val
0x18000ba39  mov     r8d, 98h; Size
0x18000ba3f  lea     rcx, [rsp+0F8h+var_D8]; void *
0x18000ba44  call    memset_0
0x18000ba49  lea     rcx, [rsp+0F8h+var_D8]; this
0x18000ba4e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000ba54  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x18000ba5b  mov     rcx, rax; hModule
0x18000ba5e  call    cs:__imp_GetProcAddress
0x18000ba64  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000ba6b  jmp     loc_18000B9AB
0x18000ba70  xor     ecx, ecx
0x18000ba72  jmp     loc_18000B9EF
```
