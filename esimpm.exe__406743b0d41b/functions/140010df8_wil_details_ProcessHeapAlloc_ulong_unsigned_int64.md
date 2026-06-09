# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140010df8`
- end: `0x140010e96`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000eb58`
- `0x14000eefc`
- `0x14000fba0`
- `0x140012644`
- `0x140013f7c`

## callees

- `0x140010df8`
- `0x14003e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140010e56`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140010e56`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140010e41`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140010e41`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140010e1d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140010e1d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010e0c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010e0c`

## string_xrefs

- `0x140010e3a`: `ntdll.dll`

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
0x140010df8  mov     [rsp+arg_0], rbx
0x140010dfd  mov     [rsp+arg_8], rsi
0x140010e02  push    rdi
0x140010e03  sub     rsp, 20h
0x140010e07  mov     rbx, rdx
0x140010e0a  mov     edi, ecx
0x140010e0c  call    cs:__imp_GetProcessHeap
0x140010e12  mov     rsi, rax
0x140010e15  mov     r8, rbx; dwBytes
0x140010e18  mov     edx, edi; dwFlags
0x140010e1a  mov     rcx, rax; hHeap
0x140010e1d  call    cs:__imp_HeapAlloc
0x140010e23  mov     rbx, rax
0x140010e26  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140010e2d  test    rax, rax
0x140010e30  jnz     short loc_140010E78
0x140010e32  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140010e38  jnz     short loc_140010E83
0x140010e3a  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x140010e41  call    cs:__imp_GetModuleHandleW
0x140010e47  test    rax, rax
0x140010e4a  jz      short loc_140010E65
0x140010e4c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x140010e53  mov     rcx, rax; hModule
0x140010e56  call    cs:__imp_GetProcAddress
0x140010e5c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140010e63  jmp     short loc_140010E6C
0x140010e65  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140010e6c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140010e73  test    rax, rax
0x140010e76  jz      short loc_140010E83
0x140010e78  mov     rdx, rbx
0x140010e7b  mov     rcx, rsi
0x140010e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010e83  mov     rax, rbx
0x140010e86  mov     rbx, [rsp+28h+arg_0]
0x140010e8b  mov     rsi, [rsp+28h+arg_8]
0x140010e90  add     rsp, 20h
0x140010e94  pop     rdi
0x140010e95  retn
```
