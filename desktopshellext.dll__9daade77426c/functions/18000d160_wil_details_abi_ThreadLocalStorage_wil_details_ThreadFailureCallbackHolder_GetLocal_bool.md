# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000d160`
- end: `0x18000d28e`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002d8cc`

## callees

- `0x18000d160`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d27b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d27b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d1f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d1f4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d1d0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d1d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d1bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d1bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d175`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d175`

## string_xrefs

- `0x18000d1ed`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char *__fastcall wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
        __int64 a1,
        char a2)
{
  __int64 v3; // rbp
  unsigned __int64 CurrentThreadId; // rsi
  unsigned __int64 v5; // r14
  __int64 i; // rax
  HANDLE ProcessHeap; // rdi
  _DWORD *v8; // rbx
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  signed __int64 v11; // rax

  v3 = wil::details::g_pThreadFailureCallbacks;
  CurrentThreadId = GetCurrentThreadId();
  v5 = 8 * ((CurrentThreadId >> 2) % 0xA);
  for ( i = *(_QWORD *)(v5 + v3); i; i = *(_QWORD *)(i + 8) )
  {
    if ( *(_DWORD *)i == (_DWORD)CurrentThreadId )
      return (char *)(i + 16);
  }
  if ( !a2 )
    return 0;
  ProcessHeap = GetProcessHeap();
  v8 = HeapAlloc(ProcessHeap, 0, 0x18u);
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
    ((void (__fastcall *)(HANDLE, _DWORD *))ProcAddress)(ProcessHeap, v8);
  }
  if ( !v8 )
    return 0;
  *v8 = CurrentThreadId;
  v8[1] = 0;
  *((_QWORD *)v8 + 1) = 0;
  *((_QWORD *)v8 + 2) = 0;
  do
  {
    v11 = *(_QWORD *)(v5 + v3);
    *((_QWORD *)v8 + 1) = v11;
  }
  while ( v11 != _InterlockedCompareExchange64((volatile signed __int64 *)(v5 + v3), (signed __int64)v8, v11) );
  return (char *)(v8 + 4);
}

```

## disassembly

```asm
0x18000d160  push    rbx
0x18000d162  push    rbp
0x18000d163  push    rsi
0x18000d164  push    rdi
0x18000d165  push    r14
0x18000d167  sub     rsp, 20h
0x18000d16b  movzx   ebx, dl
0x18000d16e  mov     rbp, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000d175  call    cs:__imp_GetCurrentThreadId
0x18000d17b  mov     esi, eax
0x18000d17d  mov     r8d, eax
0x18000d180  shr     r8, 2
0x18000d184  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000d18e  mul     r8
0x18000d191  shr     rdx, 3
0x18000d195  lea     rcx, [rdx+rdx*4]
0x18000d199  add     rcx, rcx
0x18000d19c  sub     r8, rcx
0x18000d19f  lea     r14, ds:0[r8*8]
0x18000d1a7  mov     rax, [r14+rbp]
0x18000d1ab  test    rax, rax
0x18000d1ae  jnz     loc_18000D251
0x18000d1b4  test    bl, bl
0x18000d1b6  jz      loc_18000D25E
0x18000d1bc  call    cs:__imp_GetProcessHeap
0x18000d1c2  mov     rdi, rax
0x18000d1c5  xor     edx, edx; dwFlags
0x18000d1c7  mov     r8d, 18h; dwBytes
0x18000d1cd  mov     rcx, rax; hHeap
0x18000d1d0  call    cs:__imp_HeapAlloc
0x18000d1d6  mov     rbx, rax
0x18000d1d9  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000d1e0  test    rax, rax
0x18000d1e3  jnz     short loc_18000D212
0x18000d1e5  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000d1eb  jnz     short loc_18000D21E
0x18000d1ed  lea     rcx, ModuleName; "ntdll.dll"
0x18000d1f4  call    cs:__imp_GetModuleHandleW
0x18000d1fa  test    rax, rax
0x18000d1fd  jnz     short loc_18000D271
0x18000d1ff  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000d206  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000d20d  test    rax, rax
0x18000d210  jz      short loc_18000D21E
0x18000d212  mov     rdx, rbx
0x18000d215  mov     rcx, rdi
0x18000d218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d21d  nop
0x18000d21e  test    rbx, rbx
0x18000d221  jz      short loc_18000D25E
0x18000d223  mov     [rbx], esi
0x18000d225  xor     eax, eax
0x18000d227  mov     [rbx+4], eax
0x18000d22a  mov     [rbx+8], rax
0x18000d22e  mov     [rbx+10h], rax
0x18000d232  mov     rax, [r14+rbp]
0x18000d236  mov     [rbx+8], rax
0x18000d23a  lock cmpxchg [r14+rbp], rbx
0x18000d240  jnz     short loc_18000D232
0x18000d242  lea     rax, [rbx+10h]
0x18000d246  add     rsp, 20h
0x18000d24a  pop     r14
0x18000d24c  pop     rdi
0x18000d24d  pop     rsi
0x18000d24e  pop     rbp
0x18000d24f  pop     rbx
0x18000d250  retn
0x18000d251  cmp     [rax], esi
0x18000d253  jz      short loc_18000D262
0x18000d255  mov     rax, [rax+8]
0x18000d259  jmp     loc_18000D1AB
0x18000d25e  xor     eax, eax
0x18000d260  jmp     short loc_18000D246
0x18000d262  add     rax, 10h
0x18000d266  add     rsp, 20h
0x18000d26a  pop     r14
0x18000d26c  pop     rdi
0x18000d26d  pop     rsi
0x18000d26e  pop     rbp
0x18000d26f  pop     rbx
0x18000d270  retn
0x18000d271  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x18000d278  mov     rcx, rax; hModule
0x18000d27b  call    cs:__imp_GetProcAddress
0x18000d281  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000d288  jmp     loc_18000D206
```
