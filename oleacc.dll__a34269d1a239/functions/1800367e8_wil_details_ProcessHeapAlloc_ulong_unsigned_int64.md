# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800367e8`
- end: `0x180036886`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180036304`
- `0x18003642c`
- `0x180037980`
- `0x180037e08`
- `0x18003af94`

## callees

- `0x1800367e8`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180036846`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180036846`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180036831`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180036831`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800367fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800367fc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003680d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003680d`

## string_xrefs

- `0x18003682a`: `ntdll.dll`

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
0x1800367e8  mov     [rsp+arg_0], rbx
0x1800367ed  mov     [rsp+arg_8], rsi
0x1800367f2  push    rdi
0x1800367f3  sub     rsp, 20h
0x1800367f7  mov     rbx, rdx
0x1800367fa  mov     edi, ecx
0x1800367fc  call    cs:__imp_GetProcessHeap
0x180036802  mov     rsi, rax
0x180036805  mov     r8, rbx; dwBytes
0x180036808  mov     edx, edi; dwFlags
0x18003680a  mov     rcx, rax; hHeap
0x18003680d  call    cs:__imp_HeapAlloc
0x180036813  mov     rbx, rax
0x180036816  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18003681d  test    rax, rax
0x180036820  jnz     short loc_180036868
0x180036822  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180036828  jnz     short loc_180036873
0x18003682a  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180036831  call    cs:__imp_GetModuleHandleW
0x180036837  test    rax, rax
0x18003683a  jz      short loc_180036855
0x18003683c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180036843  mov     rcx, rax; hModule
0x180036846  call    cs:__imp_GetProcAddress
0x18003684c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180036853  jmp     short loc_18003685C
0x180036855  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18003685c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180036863  test    rax, rax
0x180036866  jz      short loc_180036873
0x180036868  mov     rdx, rbx
0x18003686b  mov     rcx, rsi
0x18003686e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036873  mov     rax, rbx
0x180036876  mov     rbx, [rsp+28h+arg_0]
0x18003687b  mov     rsi, [rsp+28h+arg_8]
0x180036880  add     rsp, 20h
0x180036884  pop     rdi
0x180036885  retn
```
