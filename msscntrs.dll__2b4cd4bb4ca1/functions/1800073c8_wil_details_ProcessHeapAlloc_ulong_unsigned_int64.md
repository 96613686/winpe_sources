# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800073c8`
- end: `0x180007466`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800050b8`
- `0x180005488`
- `0x180006170`
- `0x180008c84`
- `0x18000a54c`

## callees

- `0x1800073c8`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007426`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007426`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007411`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007411`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800073ed`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800073ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800073dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800073dc`

## string_xrefs

- `0x18000740a`: `ntdll.dll`

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
0x1800073c8  mov     [rsp+arg_0], rbx
0x1800073cd  mov     [rsp+arg_8], rsi
0x1800073d2  push    rdi
0x1800073d3  sub     rsp, 20h
0x1800073d7  mov     rbx, rdx
0x1800073da  mov     edi, ecx
0x1800073dc  call    cs:__imp_GetProcessHeap
0x1800073e2  mov     rsi, rax
0x1800073e5  mov     r8, rbx; dwBytes
0x1800073e8  mov     edx, edi; dwFlags
0x1800073ea  mov     rcx, rax; hHeap
0x1800073ed  call    cs:__imp_HeapAlloc
0x1800073f3  mov     rbx, rax
0x1800073f6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800073fd  test    rax, rax
0x180007400  jnz     short loc_180007448
0x180007402  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007408  jnz     short loc_180007453
0x18000740a  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180007411  call    cs:__imp_GetModuleHandleW
0x180007417  test    rax, rax
0x18000741a  jz      short loc_180007435
0x18000741c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180007423  mov     rcx, rax; hModule
0x180007426  call    cs:__imp_GetProcAddress
0x18000742c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180007433  jmp     short loc_18000743C
0x180007435  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000743c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007443  test    rax, rax
0x180007446  jz      short loc_180007453
0x180007448  mov     rdx, rbx
0x18000744b  mov     rcx, rsi
0x18000744e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007453  mov     rax, rbx
0x180007456  mov     rbx, [rsp+28h+arg_0]
0x18000745b  mov     rsi, [rsp+28h+arg_8]
0x180007460  add     rsp, 20h
0x180007464  pop     rdi
0x180007465  retn
```
