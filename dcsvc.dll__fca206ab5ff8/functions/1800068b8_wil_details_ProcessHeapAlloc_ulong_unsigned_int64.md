# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800068b8`
- end: `0x180006956`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004418`
- `0x1800047e8`
- `0x1800054f0`
- `0x1800085d0`
- `0x18000a270`

## callees

- `0x1800068b8`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800068cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800068cc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800068dd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800068dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006916`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006916`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006901`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006901`

## string_xrefs

- `0x1800068fa`: `ntdll.dll`

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
0x1800068b8  mov     [rsp+arg_0], rbx
0x1800068bd  mov     [rsp+arg_8], rsi
0x1800068c2  push    rdi
0x1800068c3  sub     rsp, 20h
0x1800068c7  mov     rbx, rdx
0x1800068ca  mov     edi, ecx
0x1800068cc  call    cs:__imp_GetProcessHeap
0x1800068d2  mov     rsi, rax
0x1800068d5  mov     r8, rbx; dwBytes
0x1800068d8  mov     edx, edi; dwFlags
0x1800068da  mov     rcx, rax; hHeap
0x1800068dd  call    cs:__imp_HeapAlloc
0x1800068e3  mov     rbx, rax
0x1800068e6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800068ed  test    rax, rax
0x1800068f0  jnz     short loc_180006938
0x1800068f2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800068f8  jnz     short loc_180006943
0x1800068fa  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180006901  call    cs:__imp_GetModuleHandleW
0x180006907  test    rax, rax
0x18000690a  jz      short loc_180006925
0x18000690c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180006913  mov     rcx, rax; hModule
0x180006916  call    cs:__imp_GetProcAddress
0x18000691c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180006923  jmp     short loc_18000692C
0x180006925  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000692c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006933  test    rax, rax
0x180006936  jz      short loc_180006943
0x180006938  mov     rdx, rbx
0x18000693b  mov     rcx, rsi
0x18000693e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006943  mov     rax, rbx
0x180006946  mov     rbx, [rsp+28h+arg_0]
0x18000694b  mov     rsi, [rsp+28h+arg_8]
0x180006950  add     rsp, 20h
0x180006954  pop     rdi
0x180006955  retn
```
