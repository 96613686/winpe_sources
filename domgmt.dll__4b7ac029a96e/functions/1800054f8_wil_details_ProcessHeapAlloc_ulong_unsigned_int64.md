# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800054f8`
- end: `0x180005596`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003db8`
- `0x1800044a0`
- `0x1800059f0`

## callees

- `0x1800054f8`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005556`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005556`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005541`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005541`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000550c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000550c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000551d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000551d`

## string_xrefs

- `0x18000553a`: `ntdll.dll`

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
0x1800054f8  mov     [rsp+arg_0], rbx
0x1800054fd  mov     [rsp+arg_8], rsi
0x180005502  push    rdi
0x180005503  sub     rsp, 20h
0x180005507  mov     rbx, rdx
0x18000550a  mov     edi, ecx
0x18000550c  call    cs:__imp_GetProcessHeap
0x180005512  mov     rsi, rax
0x180005515  mov     r8, rbx; dwBytes
0x180005518  mov     edx, edi; dwFlags
0x18000551a  mov     rcx, rax; hHeap
0x18000551d  call    cs:__imp_HeapAlloc
0x180005523  mov     rbx, rax
0x180005526  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000552d  test    rax, rax
0x180005530  jnz     short loc_180005578
0x180005532  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005538  jnz     short loc_180005583
0x18000553a  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180005541  call    cs:__imp_GetModuleHandleW
0x180005547  test    rax, rax
0x18000554a  jz      short loc_180005565
0x18000554c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180005553  mov     rcx, rax; hModule
0x180005556  call    cs:__imp_GetProcAddress
0x18000555c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005563  jmp     short loc_18000556C
0x180005565  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000556c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005573  test    rax, rax
0x180005576  jz      short loc_180005583
0x180005578  mov     rdx, rbx
0x18000557b  mov     rcx, rsi
0x18000557e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005583  mov     rax, rbx
0x180005586  mov     rbx, [rsp+28h+arg_0]
0x18000558b  mov     rsi, [rsp+28h+arg_8]
0x180005590  add     rsp, 20h
0x180005594  pop     rdi
0x180005595  retn
```
