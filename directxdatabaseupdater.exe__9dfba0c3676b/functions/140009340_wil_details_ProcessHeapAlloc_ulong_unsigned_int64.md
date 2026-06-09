# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140009340`
- end: `0x1400093de`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000757c`
- `0x140008a14`
- `0x140008b78`
- `0x14000a590`
- `0x14000aa14`
- `0x14000e538`

## callees

- `0x140009340`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140009389`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140009389`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000939e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000939e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009354`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009354`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140009365`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140009365`

## string_xrefs

- `0x140009382`: `ntdll.dll`

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
0x140009340  mov     [rsp+arg_0], rbx
0x140009345  mov     [rsp+arg_8], rsi
0x14000934a  push    rdi
0x14000934b  sub     rsp, 20h
0x14000934f  mov     rbx, rdx
0x140009352  mov     edi, ecx
0x140009354  call    cs:__imp_GetProcessHeap
0x14000935a  mov     rsi, rax
0x14000935d  mov     r8, rbx; dwBytes
0x140009360  mov     edx, edi; dwFlags
0x140009362  mov     rcx, rax; hHeap
0x140009365  call    cs:__imp_HeapAlloc
0x14000936b  mov     rbx, rax
0x14000936e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140009375  test    rax, rax
0x140009378  jnz     short loc_1400093C0
0x14000937a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140009380  jnz     short loc_1400093CB
0x140009382  lea     rcx, ModuleName; "ntdll.dll"
0x140009389  call    cs:__imp_GetModuleHandleW
0x14000938f  test    rax, rax
0x140009392  jz      short loc_1400093AD
0x140009394  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x14000939b  mov     rcx, rax; hModule
0x14000939e  call    cs:__imp_GetProcAddress
0x1400093a4  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1400093ab  jmp     short loc_1400093B4
0x1400093ad  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400093b4  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400093bb  test    rax, rax
0x1400093be  jz      short loc_1400093CB
0x1400093c0  mov     rdx, rbx
0x1400093c3  mov     rcx, rsi
0x1400093c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400093cb  mov     rax, rbx
0x1400093ce  mov     rbx, [rsp+28h+arg_0]
0x1400093d3  mov     rsi, [rsp+28h+arg_8]
0x1400093d8  add     rsp, 20h
0x1400093dc  pop     rdi
0x1400093dd  retn
```
