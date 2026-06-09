# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180024f90`
- end: `0x18002502e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180024bb4`
- `0x180024d4c`
- `0x180025cfc`
- `0x180025f28`
- `0x180026b84`

## callees

- `0x180024f90`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180024fee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180024fee`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180024fd9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180024fd9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024fa4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024fa4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024fb5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024fb5`

## string_xrefs

- `0x180024fd2`: `ntdll.dll`

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
0x180024f90  mov     [rsp+arg_0], rbx
0x180024f95  mov     [rsp+arg_8], rsi
0x180024f9a  push    rdi
0x180024f9b  sub     rsp, 20h
0x180024f9f  mov     rbx, rdx
0x180024fa2  mov     edi, ecx
0x180024fa4  call    cs:__imp_GetProcessHeap
0x180024faa  mov     rsi, rax
0x180024fad  mov     r8, rbx; dwBytes
0x180024fb0  mov     edx, edi; dwFlags
0x180024fb2  mov     rcx, rax; hHeap
0x180024fb5  call    cs:__imp_HeapAlloc
0x180024fbb  mov     rbx, rax
0x180024fbe  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180024fc5  test    rax, rax
0x180024fc8  jnz     short loc_180025010
0x180024fca  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180024fd0  jnz     short loc_18002501B
0x180024fd2  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180024fd9  call    cs:__imp_GetModuleHandleW
0x180024fdf  test    rax, rax
0x180024fe2  jz      short loc_180024FFD
0x180024fe4  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180024feb  mov     rcx, rax; hModule
0x180024fee  call    cs:__imp_GetProcAddress
0x180024ff4  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180024ffb  jmp     short loc_180025004
0x180024ffd  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180025004  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18002500b  test    rax, rax
0x18002500e  jz      short loc_18002501B
0x180025010  mov     rdx, rbx
0x180025013  mov     rcx, rsi
0x180025016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002501b  mov     rax, rbx
0x18002501e  mov     rbx, [rsp+28h+arg_0]
0x180025023  mov     rsi, [rsp+28h+arg_8]
0x180025028  add     rsp, 20h
0x18002502c  pop     rdi
0x18002502d  retn
```
