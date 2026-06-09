# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180007e78`
- end: `0x180007f16`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800048f8`
- `0x180004c9c`
- `0x180006310`
- `0x18000a940`
- `0x18000c80c`

## callees

- `0x180007e78`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007ec1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007ec1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007ed6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007ed6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007e9d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007e9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007e8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007e8c`

## string_xrefs

- `0x180007eba`: `ntdll.dll`

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
0x180007e78  mov     [rsp+arg_0], rbx
0x180007e7d  mov     [rsp+arg_8], rsi
0x180007e82  push    rdi
0x180007e83  sub     rsp, 20h
0x180007e87  mov     rbx, rdx
0x180007e8a  mov     edi, ecx
0x180007e8c  call    cs:__imp_GetProcessHeap
0x180007e92  mov     rsi, rax
0x180007e95  mov     r8, rbx; dwBytes
0x180007e98  mov     edx, edi; dwFlags
0x180007e9a  mov     rcx, rax; hHeap
0x180007e9d  call    cs:__imp_HeapAlloc
0x180007ea3  mov     rbx, rax
0x180007ea6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007ead  test    rax, rax
0x180007eb0  jnz     short loc_180007EF8
0x180007eb2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007eb8  jnz     short loc_180007F03
0x180007eba  lea     rcx, ModuleName; "ntdll.dll"
0x180007ec1  call    cs:__imp_GetModuleHandleW
0x180007ec7  test    rax, rax
0x180007eca  jz      short loc_180007EE5
0x180007ecc  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180007ed3  mov     rcx, rax; hModule
0x180007ed6  call    cs:__imp_GetProcAddress
0x180007edc  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180007ee3  jmp     short loc_180007EEC
0x180007ee5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007eec  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007ef3  test    rax, rax
0x180007ef6  jz      short loc_180007F03
0x180007ef8  mov     rdx, rbx
0x180007efb  mov     rcx, rsi
0x180007efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f03  mov     rax, rbx
0x180007f06  mov     rbx, [rsp+28h+arg_0]
0x180007f0b  mov     rsi, [rsp+28h+arg_8]
0x180007f10  add     rsp, 20h
0x180007f14  pop     rdi
0x180007f15  retn
```
