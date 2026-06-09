# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000f700`
- end: `0x18000f79e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000ac74`
- `0x18000cd18`
- `0x180011000`
- `0x1800115c0`

## callees

- `0x18000f700`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f75e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f75e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f749`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f749`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f725`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f725`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f714`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f714`

## string_xrefs

- `0x18000f742`: `ntdll.dll`

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
0x18000f700  mov     [rsp+arg_0], rbx
0x18000f705  mov     [rsp+arg_8], rsi
0x18000f70a  push    rdi
0x18000f70b  sub     rsp, 20h
0x18000f70f  mov     rbx, rdx
0x18000f712  mov     edi, ecx
0x18000f714  call    cs:__imp_GetProcessHeap
0x18000f71a  mov     rsi, rax
0x18000f71d  mov     r8, rbx; dwBytes
0x18000f720  mov     edx, edi; dwFlags
0x18000f722  mov     rcx, rax; hHeap
0x18000f725  call    cs:__imp_HeapAlloc
0x18000f72b  mov     rbx, rax
0x18000f72e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000f735  test    rax, rax
0x18000f738  jnz     short loc_18000F780
0x18000f73a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000f740  jnz     short loc_18000F78B
0x18000f742  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000f749  call    cs:__imp_GetModuleHandleW
0x18000f74f  test    rax, rax
0x18000f752  jz      short loc_18000F76D
0x18000f754  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000f75b  mov     rcx, rax; hModule
0x18000f75e  call    cs:__imp_GetProcAddress
0x18000f764  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000f76b  jmp     short loc_18000F774
0x18000f76d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000f774  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000f77b  test    rax, rax
0x18000f77e  jz      short loc_18000F78B
0x18000f780  mov     rdx, rbx
0x18000f783  mov     rcx, rsi
0x18000f786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f78b  mov     rax, rbx
0x18000f78e  mov     rbx, [rsp+28h+arg_0]
0x18000f793  mov     rsi, [rsp+28h+arg_8]
0x18000f798  add     rsp, 20h
0x18000f79c  pop     rdi
0x18000f79d  retn
```
