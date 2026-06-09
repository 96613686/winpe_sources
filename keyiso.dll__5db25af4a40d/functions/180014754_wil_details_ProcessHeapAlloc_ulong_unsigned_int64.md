# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180014754`
- end: `0x1800147f3`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `159`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a9ec`
- `0x18001420c`
- `0x180014338`
- `0x180015440`
- `0x1800158c4`

## callees

- `0x180014754`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800147b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800147b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001479d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001479d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014768`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014768`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014779`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014779`

## string_xrefs

- `0x180014796`: `ntdll.dll`

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
0x180014754  mov     [rsp+arg_0], rbx
0x180014759  mov     [rsp+arg_8], rsi
0x18001475e  push    rdi
0x18001475f  sub     rsp, 20h
0x180014763  mov     rbx, rdx
0x180014766  mov     edi, ecx
0x180014768  call    cs:__imp_GetProcessHeap
0x18001476e  mov     rsi, rax
0x180014771  mov     r8, rbx; dwBytes
0x180014774  mov     edx, edi; dwFlags
0x180014776  mov     rcx, rax; hHeap
0x180014779  call    cs:__imp_HeapAlloc
0x18001477f  mov     rbx, rax
0x180014782  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180014789  test    rax, rax
0x18001478c  jnz     short loc_1800147D5
0x18001478e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180014794  jnz     short loc_1800147E0
0x180014796  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18001479d  call    cs:__imp_GetModuleHandleW
0x1800147a3  test    rax, rax
0x1800147a6  jz      short loc_1800147C2
0x1800147a8  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800147af  mov     rcx, rax; hModule
0x1800147b2  call    cs:__imp_GetProcAddress
0x1800147b8  nop
0x1800147b9  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800147c0  jmp     short loc_1800147C9
0x1800147c2  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800147c9  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800147d0  test    rax, rax
0x1800147d3  jz      short loc_1800147E0
0x1800147d5  mov     rdx, rbx
0x1800147d8  mov     rcx, rsi
0x1800147db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147e0  mov     rax, rbx
0x1800147e3  mov     rbx, [rsp+28h+arg_0]
0x1800147e8  mov     rsi, [rsp+28h+arg_8]
0x1800147ed  add     rsp, 20h
0x1800147f1  pop     rdi
0x1800147f2  retn
```
