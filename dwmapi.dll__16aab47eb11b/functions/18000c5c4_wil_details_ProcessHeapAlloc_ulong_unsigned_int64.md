# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000c5c4`
- end: `0x18000c662`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006530`
- `0x18000a760`
- `0x18000c35c`
- `0x18000c48c`
- `0x18000c7a4`

## callees

- `0x18000c5c4`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c60d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c60d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c622`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c622`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c5d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c5d8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c5e9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c5e9`

## string_xrefs

- `0x18000c606`: `ntdll.dll`

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
0x18000c5c4  mov     [rsp+arg_0], rbx
0x18000c5c9  mov     [rsp+arg_8], rsi
0x18000c5ce  push    rdi
0x18000c5cf  sub     rsp, 20h
0x18000c5d3  mov     rbx, rdx
0x18000c5d6  mov     edi, ecx
0x18000c5d8  call    cs:__imp_GetProcessHeap
0x18000c5de  mov     r8, rbx; dwBytes
0x18000c5e1  mov     edx, edi; dwFlags
0x18000c5e3  mov     rcx, rax; hHeap
0x18000c5e6  mov     rsi, rax
0x18000c5e9  call    cs:__imp_HeapAlloc
0x18000c5ef  mov     rbx, rax
0x18000c5f2  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000c5f9  test    rax, rax
0x18000c5fc  jnz     short loc_18000C644
0x18000c5fe  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000c604  jnz     short loc_18000C64F
0x18000c606  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000c60d  call    cs:__imp_GetModuleHandleW
0x18000c613  test    rax, rax
0x18000c616  jz      short loc_18000C631
0x18000c618  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000c61f  mov     rcx, rax; hModule
0x18000c622  call    cs:__imp_GetProcAddress
0x18000c628  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000c62f  jmp     short loc_18000C638
0x18000c631  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000c638  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000c63f  test    rax, rax
0x18000c642  jz      short loc_18000C64F
0x18000c644  mov     rdx, rbx
0x18000c647  mov     rcx, rsi
0x18000c64a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c64f  mov     rsi, [rsp+28h+arg_8]
0x18000c654  mov     rax, rbx
0x18000c657  mov     rbx, [rsp+28h+arg_0]
0x18000c65c  add     rsp, 20h
0x18000c660  pop     rdi
0x18000c661  retn
```
