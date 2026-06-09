# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180014130`
- end: `0x1800141ce`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000d7a4`
- `0x18000d8f8`
- `0x1800149b4`
- `0x180014c18`
- `0x18001587c`

## callees

- `0x180014130`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180014179`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180014179`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001418e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001418e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014144`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014144`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014155`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014155`

## string_xrefs

- `0x180014172`: `ntdll.dll`

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
0x180014130  mov     [rsp+arg_0], rbx
0x180014135  mov     [rsp+arg_8], rsi
0x18001413a  push    rdi
0x18001413b  sub     rsp, 20h
0x18001413f  mov     rbx, rdx
0x180014142  mov     edi, ecx
0x180014144  call    cs:__imp_GetProcessHeap
0x18001414a  mov     r8, rbx; dwBytes
0x18001414d  mov     edx, edi; dwFlags
0x18001414f  mov     rcx, rax; hHeap
0x180014152  mov     rsi, rax
0x180014155  call    cs:__imp_HeapAlloc
0x18001415b  mov     rbx, rax
0x18001415e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180014165  test    rax, rax
0x180014168  jnz     short loc_1800141B0
0x18001416a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180014170  jnz     short loc_1800141BB
0x180014172  lea     rcx, ModuleName; "ntdll.dll"
0x180014179  call    cs:__imp_GetModuleHandleW
0x18001417f  test    rax, rax
0x180014182  jz      short loc_18001419D
0x180014184  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x18001418b  mov     rcx, rax; hModule
0x18001418e  call    cs:__imp_GetProcAddress
0x180014194  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18001419b  jmp     short loc_1800141A4
0x18001419d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800141a4  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800141ab  test    rax, rax
0x1800141ae  jz      short loc_1800141BB
0x1800141b0  mov     rdx, rbx
0x1800141b3  mov     rcx, rsi
0x1800141b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141bb  mov     rsi, [rsp+28h+arg_8]
0x1800141c0  mov     rax, rbx
0x1800141c3  mov     rbx, [rsp+28h+arg_0]
0x1800141c8  add     rsp, 20h
0x1800141cc  pop     rdi
0x1800141cd  retn
```
