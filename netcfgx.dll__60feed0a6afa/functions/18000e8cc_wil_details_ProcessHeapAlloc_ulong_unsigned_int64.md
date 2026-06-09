# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000e8cc`
- end: `0x18000e96a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000c8ec`
- `0x18000cfa0`
- `0x18000d570`
- `0x18000efc0`

## callees

- `0x18000e8cc`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e8f1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e8f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e8e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e8e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e915`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e915`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e92a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e92a`

## string_xrefs

- `0x18000e90e`: `ntdll.dll`

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
0x18000e8cc  mov     [rsp+arg_0], rbx
0x18000e8d1  mov     [rsp+arg_8], rsi
0x18000e8d6  push    rdi
0x18000e8d7  sub     rsp, 20h
0x18000e8db  mov     rbx, rdx
0x18000e8de  mov     edi, ecx
0x18000e8e0  call    cs:__imp_GetProcessHeap
0x18000e8e6  mov     rsi, rax
0x18000e8e9  mov     r8, rbx; dwBytes
0x18000e8ec  mov     edx, edi; dwFlags
0x18000e8ee  mov     rcx, rax; hHeap
0x18000e8f1  call    cs:__imp_HeapAlloc
0x18000e8f7  mov     rbx, rax
0x18000e8fa  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000e901  test    rax, rax
0x18000e904  jnz     short loc_18000E94C
0x18000e906  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000e90c  jnz     short loc_18000E957
0x18000e90e  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000e915  call    cs:__imp_GetModuleHandleW
0x18000e91b  test    rax, rax
0x18000e91e  jz      short loc_18000E939
0x18000e920  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000e927  mov     rcx, rax; hModule
0x18000e92a  call    cs:__imp_GetProcAddress
0x18000e930  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000e937  jmp     short loc_18000E940
0x18000e939  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000e940  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000e947  test    rax, rax
0x18000e94a  jz      short loc_18000E957
0x18000e94c  mov     rdx, rbx
0x18000e94f  mov     rcx, rsi
0x18000e952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e957  mov     rax, rbx
0x18000e95a  mov     rbx, [rsp+28h+arg_0]
0x18000e95f  mov     rsi, [rsp+28h+arg_8]
0x18000e964  add     rsp, 20h
0x18000e968  pop     rdi
0x18000e969  retn
```
