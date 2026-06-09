# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180005ec8`
- end: `0x180005f66`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004528`
- `0x180004e00`
- `0x1800065a4`

## callees

- `0x180005ec8`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005f26`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005f26`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005f11`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005f11`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005eed`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005eed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005edc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005edc`

## string_xrefs

- `0x180005f0a`: `ntdll.dll`

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
0x180005ec8  mov     [rsp+arg_0], rbx
0x180005ecd  mov     [rsp+arg_8], rsi
0x180005ed2  push    rdi
0x180005ed3  sub     rsp, 20h
0x180005ed7  mov     rbx, rdx
0x180005eda  mov     edi, ecx
0x180005edc  call    cs:__imp_GetProcessHeap
0x180005ee2  mov     rsi, rax
0x180005ee5  mov     r8, rbx; dwBytes
0x180005ee8  mov     edx, edi; dwFlags
0x180005eea  mov     rcx, rax; hHeap
0x180005eed  call    cs:__imp_HeapAlloc
0x180005ef3  mov     rbx, rax
0x180005ef6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005efd  test    rax, rax
0x180005f00  jnz     short loc_180005F48
0x180005f02  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005f08  jnz     short loc_180005F53
0x180005f0a  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180005f11  call    cs:__imp_GetModuleHandleW
0x180005f17  test    rax, rax
0x180005f1a  jz      short loc_180005F35
0x180005f1c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180005f23  mov     rcx, rax; hModule
0x180005f26  call    cs:__imp_GetProcAddress
0x180005f2c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005f33  jmp     short loc_180005F3C
0x180005f35  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005f3c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005f43  test    rax, rax
0x180005f46  jz      short loc_180005F53
0x180005f48  mov     rdx, rbx
0x180005f4b  mov     rcx, rsi
0x180005f4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f53  mov     rax, rbx
0x180005f56  mov     rbx, [rsp+28h+arg_0]
0x180005f5b  mov     rsi, [rsp+28h+arg_8]
0x180005f60  add     rsp, 20h
0x180005f64  pop     rdi
0x180005f65  retn
```
