# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180006840`
- end: `0x1800068de`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004428`
- `0x1800047cc`
- `0x180005560`
- `0x180008364`
- `0x180009ba0`

## callees

- `0x180006840`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000689e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000689e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006889`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006889`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006854`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006854`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006865`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006865`

## string_xrefs

- `0x180006882`: `ntdll.dll`

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
0x180006840  mov     [rsp+arg_0], rbx
0x180006845  mov     [rsp+arg_8], rsi
0x18000684a  push    rdi
0x18000684b  sub     rsp, 20h
0x18000684f  mov     rbx, rdx
0x180006852  mov     edi, ecx
0x180006854  call    cs:__imp_GetProcessHeap
0x18000685a  mov     rsi, rax
0x18000685d  mov     r8, rbx; dwBytes
0x180006860  mov     edx, edi; dwFlags
0x180006862  mov     rcx, rax; hHeap
0x180006865  call    cs:__imp_HeapAlloc
0x18000686b  mov     rbx, rax
0x18000686e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180006875  test    rax, rax
0x180006878  jnz     short loc_1800068C0
0x18000687a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006880  jnz     short loc_1800068CB
0x180006882  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180006889  call    cs:__imp_GetModuleHandleW
0x18000688f  test    rax, rax
0x180006892  jz      short loc_1800068AD
0x180006894  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000689b  mov     rcx, rax; hModule
0x18000689e  call    cs:__imp_GetProcAddress
0x1800068a4  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800068ab  jmp     short loc_1800068B4
0x1800068ad  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800068b4  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800068bb  test    rax, rax
0x1800068be  jz      short loc_1800068CB
0x1800068c0  mov     rdx, rbx
0x1800068c3  mov     rcx, rsi
0x1800068c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068cb  mov     rax, rbx
0x1800068ce  mov     rbx, [rsp+28h+arg_0]
0x1800068d3  mov     rsi, [rsp+28h+arg_8]
0x1800068d8  add     rsp, 20h
0x1800068dc  pop     rdi
0x1800068dd  retn
```
