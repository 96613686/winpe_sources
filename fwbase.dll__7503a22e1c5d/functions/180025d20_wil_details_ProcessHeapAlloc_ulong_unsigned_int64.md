# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180025d20`
- end: `0x180025dbe`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180022d20`
- `0x180023100`
- `0x1800242b0`
- `0x180027b60`
- `0x180029710`

## callees

- `0x180025d20`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025d7e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025d7e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025d69`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025d69`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025d45`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025d45`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025d34`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025d34`

## string_xrefs

- `0x180025d62`: `ntdll.dll`

## pseudocode

```c
LPVOID __fastcall wil::details::ProcessHeapAlloc(DWORD dwFlags, SIZE_T dwBytes)
{
  HANDLE ProcessHeap; // rsi
  LPVOID v5; // rbx
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax

  ProcessHeap = GetProcessHeap();
  v5 = HeapAlloc(ProcessHeap, dwFlags, dwBytes);
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
    ((void (__fastcall *)(HANDLE, LPVOID))ProcAddress)(ProcessHeap, v5);
  }
  return v5;
}

```

## disassembly

```asm
0x180025d20  mov     [rsp+arg_0], rbx
0x180025d25  mov     [rsp+arg_8], rsi
0x180025d2a  push    rdi
0x180025d2b  sub     rsp, 20h
0x180025d2f  mov     rbx, rdx
0x180025d32  mov     edi, ecx
0x180025d34  call    cs:__imp_GetProcessHeap
0x180025d3a  mov     rsi, rax
0x180025d3d  mov     r8, rbx; dwBytes
0x180025d40  mov     edx, edi; dwFlags
0x180025d42  mov     rcx, rax; hHeap
0x180025d45  call    cs:__imp_HeapAlloc
0x180025d4b  mov     rbx, rax
0x180025d4e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180025d55  test    rax, rax
0x180025d58  jnz     short loc_180025DA0
0x180025d5a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180025d60  jnz     short loc_180025DAB
0x180025d62  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180025d69  call    cs:__imp_GetModuleHandleW
0x180025d6f  test    rax, rax
0x180025d72  jz      short loc_180025D8D
0x180025d74  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180025d7b  mov     rcx, rax; hModule
0x180025d7e  call    cs:__imp_GetProcAddress
0x180025d84  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180025d8b  jmp     short loc_180025D94
0x180025d8d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180025d94  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180025d9b  test    rax, rax
0x180025d9e  jz      short loc_180025DAB
0x180025da0  mov     rdx, rbx
0x180025da3  mov     rcx, rsi
0x180025da6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025dab  mov     rax, rbx
0x180025dae  mov     rbx, [rsp+28h+arg_0]
0x180025db3  mov     rsi, [rsp+28h+arg_8]
0x180025db8  add     rsp, 20h
0x180025dbc  pop     rdi
0x180025dbd  retn
```
