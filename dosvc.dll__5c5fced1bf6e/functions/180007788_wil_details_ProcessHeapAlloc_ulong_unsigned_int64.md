# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180007788`
- end: `0x180007826`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180007534`
- `0x180007a4c`
- `0x180007de4`

## callees

- `0x180007788`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800077e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800077e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800077d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800077d1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800077ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800077ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000779c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000779c`

## string_xrefs

- `0x1800077ca`: `ntdll.dll`

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
0x180007788  mov     [rsp+arg_0], rbx
0x18000778d  mov     [rsp+arg_8], rsi
0x180007792  push    rdi
0x180007793  sub     rsp, 20h
0x180007797  mov     rbx, rdx
0x18000779a  mov     edi, ecx
0x18000779c  call    cs:__imp_GetProcessHeap
0x1800077a2  mov     rsi, rax
0x1800077a5  mov     r8, rbx; dwBytes
0x1800077a8  mov     edx, edi; dwFlags
0x1800077aa  mov     rcx, rax; hHeap
0x1800077ad  call    cs:__imp_HeapAlloc
0x1800077b3  mov     rbx, rax
0x1800077b6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800077bd  test    rax, rax
0x1800077c0  jnz     short loc_180007808
0x1800077c2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800077c8  jnz     short loc_180007813
0x1800077ca  lea     rcx, LibFileName; "ntdll.dll"
0x1800077d1  call    cs:__imp_GetModuleHandleW
0x1800077d7  test    rax, rax
0x1800077da  jz      short loc_1800077F5
0x1800077dc  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800077e3  mov     rcx, rax; hModule
0x1800077e6  call    cs:__imp_GetProcAddress
0x1800077ec  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800077f3  jmp     short loc_1800077FC
0x1800077f5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800077fc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007803  test    rax, rax
0x180007806  jz      short loc_180007813
0x180007808  mov     rdx, rbx
0x18000780b  mov     rcx, rsi
0x18000780e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007813  mov     rax, rbx
0x180007816  mov     rbx, [rsp+28h+arg_0]
0x18000781b  mov     rsi, [rsp+28h+arg_8]
0x180007820  add     rsp, 20h
0x180007824  pop     rdi
0x180007825  retn
```
