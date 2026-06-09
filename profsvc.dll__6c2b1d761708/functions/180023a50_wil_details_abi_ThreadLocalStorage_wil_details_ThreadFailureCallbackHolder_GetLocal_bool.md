# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180023a50`
- end: `0x180023b8c`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `316`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003e4d4`

## callees

- `0x180023a50`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023b3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023b3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180023b1f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180023b1f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023adf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023adf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023ac5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023ac5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023a65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023a65`

## string_xrefs

- `0x180023b18`: `ntdll.dll`

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
0x180023a50  push    rbx
0x180023a52  push    rbp
0x180023a53  push    rsi
0x180023a54  push    rdi
0x180023a55  push    r14
0x180023a57  sub     rsp, 20h
0x180023a5b  movzx   edi, dl
0x180023a5e  mov     rbp, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180023a65  call    cs:__imp_GetCurrentThreadId
0x180023a6c  nop     dword ptr [rax+rax+00h]
0x180023a71  mov     ebx, eax
0x180023a73  mov     r8d, eax
0x180023a76  shr     r8, 2
0x180023a7a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180023a84  mul     r8
0x180023a87  shr     rdx, 3
0x180023a8b  lea     rcx, [rdx+rdx*4]
0x180023a8f  add     rcx, rcx
0x180023a92  sub     r8, rcx
0x180023a95  lea     r14, ds:0[r8*8]
0x180023a9d  mov     rax, [r14+rbp]
0x180023aa1  test    rax, rax
0x180023aa4  jz      short loc_180023AC0
0x180023aa6  cmp     [rax], ebx
0x180023aa8  jnz     short loc_180023ABA
0x180023aaa  add     rax, 10h
0x180023aae  add     rsp, 20h
0x180023ab2  pop     r14
0x180023ab4  pop     rdi
0x180023ab5  pop     rsi
0x180023ab6  pop     rbp
0x180023ab7  pop     rbx
0x180023ab8  retn
0x180023aba  mov     rax, [rax+8]
0x180023abe  jmp     short loc_180023AA1
0x180023ac0  test    dil, dil
0x180023ac3  jz      short loc_180023B0B
0x180023ac5  call    cs:__imp_GetProcessHeap
0x180023acc  nop     dword ptr [rax+rax+00h]
0x180023ad1  mov     rsi, rax
0x180023ad4  xor     edx, edx; dwFlags
0x180023ad6  mov     r8d, 18h; dwBytes
0x180023adc  mov     rcx, rax; hHeap
0x180023adf  call    cs:__imp_HeapAlloc
0x180023ae6  nop     dword ptr [rax+rax+00h]
0x180023aeb  mov     rdi, rax
0x180023aee  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180023af5  test    rax, rax
0x180023af8  jz      short loc_180023B0F
0x180023afa  mov     rdx, rdi
0x180023afd  mov     rcx, rsi
0x180023b00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b05  nop
0x180023b06  test    rdi, rdi
0x180023b09  jnz     short loc_180023B64
0x180023b0b  xor     eax, eax
0x180023b0d  jmp     short loc_180023AAE
0x180023b0f  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 0; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180023b16  jnz     short loc_180023B06
0x180023b18  lea     rcx, LibFileName; "ntdll.dll"
0x180023b1f  call    cs:__imp_GetModuleHandleW
0x180023b26  nop     dword ptr [rax+rax+00h]
0x180023b2b  test    rax, rax
0x180023b2e  jz      short loc_180023B4F
0x180023b30  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180023b37  mov     rcx, rax; hModule
0x180023b3a  call    cs:__imp_GetProcAddress
0x180023b41  nop     dword ptr [rax+rax+00h]
0x180023b46  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180023b4d  jmp     short loc_180023B56
0x180023b4f  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180023b56  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180023b5d  test    rax, rax
0x180023b60  jz      short loc_180023B06
0x180023b62  jmp     short loc_180023AFA
0x180023b64  mov     [rdi], ebx
0x180023b66  xor     eax, eax
0x180023b68  mov     [rdi+4], eax
0x180023b6b  mov     [rdi+8], rax
0x180023b6f  mov     [rdi+10h], rax
0x180023b73  mov     rax, [r14+rbp]
0x180023b77  mov     [rdi+8], rax
0x180023b7b  lock cmpxchg [r14+rbp], rdi
0x180023b81  jnz     short loc_180023B73
0x180023b83  lea     rax, [rdi+10h]
0x180023b87  jmp     loc_180023AAE
```
