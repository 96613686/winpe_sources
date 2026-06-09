# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180006da8`
- end: `0x180006e46`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004d50`
- `0x180007b98`
- `0x180016630`
- `0x180024b74`

## callees

- `0x180006da8`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006df1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006df1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006e06`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006e06`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006dcd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006dcd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006dbc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006dbc`

## string_xrefs

- `0x180006dea`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180006da8  mov     [rsp+arg_0], rbx
0x180006dad  mov     [rsp+arg_8], rsi
0x180006db2  push    rdi
0x180006db3  sub     rsp, 20h
0x180006db7  mov     rbx, rdx
0x180006dba  mov     edi, ecx
0x180006dbc  call    cs:__imp_GetProcessHeap
0x180006dc2  mov     rsi, rax
0x180006dc5  mov     r8, rbx; dwBytes
0x180006dc8  mov     edx, edi; dwFlags
0x180006dca  mov     rcx, rax; hHeap
0x180006dcd  call    cs:__imp_HeapAlloc
0x180006dd3  mov     rbx, rax
0x180006dd6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180006ddd  test    rax, rax
0x180006de0  jnz     short loc_180006E28
0x180006de2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006de8  jnz     short loc_180006E33
0x180006dea  lea     rcx, ModuleName; "ntdll.dll"
0x180006df1  call    cs:__imp_GetModuleHandleW
0x180006df7  test    rax, rax
0x180006dfa  jz      short loc_180006E15
0x180006dfc  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180006e03  mov     rcx, rax; hModule
0x180006e06  call    cs:__imp_GetProcAddress
0x180006e0c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180006e13  jmp     short loc_180006E1C
0x180006e15  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180006e1c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006e23  test    rax, rax
0x180006e26  jz      short loc_180006E33
0x180006e28  mov     rdx, rbx
0x180006e2b  mov     rcx, rsi
0x180006e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e33  mov     rax, rbx
0x180006e36  mov     rbx, [rsp+28h+arg_0]
0x180006e3b  mov     rsi, [rsp+28h+arg_8]
0x180006e40  add     rsp, 20h
0x180006e44  pop     rdi
0x180006e45  retn
```
