# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18001fca0`
- end: `0x18001fdbd`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003cf2c`

## callees

- `0x18001fca0`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001fd71`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001fd71`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001fd5c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001fd5c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001fd22`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001fd22`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fd0e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fd0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001fcb5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001fcb5`

## string_xrefs

- `0x18001fd55`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char *__fastcall wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
        __int64 a1,
        char a2)
{
  __int64 v3; // rbp
  unsigned __int64 CurrentThreadId; // rbx
  unsigned __int64 v5; // r14
  __int64 i; // rax
  HANDLE ProcessHeap; // rsi
  _DWORD *v9; // rdi
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  signed __int64 v12; // rax

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
  v9 = HeapAlloc(ProcessHeap, 0, 0x18u);
  ProcAddress = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation;
  if ( `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation
    || !`wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation
    && ((ModuleHandleW = GetModuleHandleW(L"ntdll.dll")) == 0
      ? (ProcAddress = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation)
      : (FARPROC)(ProcAddress = GetProcAddress(ModuleHandleW, "RtlDisownModuleHeapAllocation"),
                  `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation = (__int64)ProcAddress),
        `wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation = 1,
        ProcAddress) )
  {
    ((void (__fastcall *)(HANDLE, _DWORD *))ProcAddress)(ProcessHeap, v9);
  }
  if ( !v9 )
    return 0;
  *v9 = CurrentThreadId;
  v9[1] = 0;
  *((_QWORD *)v9 + 1) = 0;
  *((_QWORD *)v9 + 2) = 0;
  do
  {
    v12 = *(_QWORD *)(v5 + v3);
    *((_QWORD *)v9 + 1) = v12;
  }
  while ( v12 != _InterlockedCompareExchange64((volatile signed __int64 *)(v5 + v3), (signed __int64)v9, v12) );
  return (char *)(v9 + 4);
}

```

## disassembly

```asm
0x18001fca0  push    rbx
0x18001fca2  push    rbp
0x18001fca3  push    rsi
0x18001fca4  push    rdi
0x18001fca5  push    r14
0x18001fca7  sub     rsp, 20h
0x18001fcab  movzx   edi, dl
0x18001fcae  mov     rbp, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001fcb5  call    cs:__imp_GetCurrentThreadId
0x18001fcbb  mov     ebx, eax
0x18001fcbd  mov     r8d, eax
0x18001fcc0  shr     r8, 2
0x18001fcc4  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001fcce  mul     r8
0x18001fcd1  shr     rdx, 3
0x18001fcd5  lea     rcx, [rdx+rdx*4]
0x18001fcd9  add     rcx, rcx
0x18001fcdc  sub     r8, rcx
0x18001fcdf  lea     r14, ds:0[r8*8]
0x18001fce7  mov     rax, [r14+rbp]
0x18001fceb  test    rax, rax
0x18001fcee  jz      short loc_18001FD09
0x18001fcf0  cmp     [rax], ebx
0x18001fcf2  jnz     short loc_18001FD03
0x18001fcf4  add     rax, 10h
0x18001fcf8  add     rsp, 20h
0x18001fcfc  pop     r14
0x18001fcfe  pop     rdi
0x18001fcff  pop     rsi
0x18001fd00  pop     rbp
0x18001fd01  pop     rbx
0x18001fd02  retn
0x18001fd03  mov     rax, [rax+8]
0x18001fd07  jmp     short loc_18001FCEB
0x18001fd09  test    dil, dil
0x18001fd0c  jz      short loc_18001FD48
0x18001fd0e  call    cs:__imp_GetProcessHeap
0x18001fd14  mov     rsi, rax
0x18001fd17  xor     edx, edx; dwFlags
0x18001fd19  mov     r8d, 18h; dwBytes
0x18001fd1f  mov     rcx, rax; hHeap
0x18001fd22  call    cs:__imp_HeapAlloc
0x18001fd28  mov     rdi, rax
0x18001fd2b  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18001fd32  test    rax, rax
0x18001fd35  jz      short loc_18001FD4C
0x18001fd37  mov     rdx, rdi
0x18001fd3a  mov     rcx, rsi
0x18001fd3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd42  nop
0x18001fd43  test    rdi, rdi
0x18001fd46  jnz     short loc_18001FD95
0x18001fd48  xor     eax, eax
0x18001fd4a  jmp     short loc_18001FCF8
0x18001fd4c  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 0; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001fd53  jnz     short loc_18001FD43
0x18001fd55  lea     rcx, LibFileName; "ntdll.dll"
0x18001fd5c  call    cs:__imp_GetModuleHandleW
0x18001fd62  test    rax, rax
0x18001fd65  jz      short loc_18001FD80
0x18001fd67  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18001fd6e  mov     rcx, rax; hModule
0x18001fd71  call    cs:__imp_GetProcAddress
0x18001fd77  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18001fd7e  jmp     short loc_18001FD87
0x18001fd80  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18001fd87  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001fd8e  test    rax, rax
0x18001fd91  jz      short loc_18001FD43
0x18001fd93  jmp     short loc_18001FD37
0x18001fd95  mov     [rdi], ebx
0x18001fd97  xor     eax, eax
0x18001fd99  mov     [rdi+4], eax
0x18001fd9c  mov     [rdi+8], rax
0x18001fda0  mov     [rdi+10h], rax
0x18001fda4  mov     rax, [r14+rbp]
0x18001fda8  mov     [rdi+8], rax
0x18001fdac  lock cmpxchg [r14+rbp], rdi
0x18001fdb2  jnz     short loc_18001FDA4
0x18001fdb4  lea     rax, [rdi+10h]
0x18001fdb8  jmp     loc_18001FCF8
```
