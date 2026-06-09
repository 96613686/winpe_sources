# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180006588`
- end: `0x180006626`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800044f8`
- `0x180004bf0`
- `0x180006ae0`

## callees

- `0x180006588`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800065d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800065d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800065e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800065e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000659c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000659c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800065ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800065ad`

## string_xrefs

- `0x1800065ca`: `ntdll.dll`

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
0x180006588  mov     [rsp+arg_0], rbx
0x18000658d  mov     [rsp+arg_8], rsi
0x180006592  push    rdi
0x180006593  sub     rsp, 20h
0x180006597  mov     rbx, rdx
0x18000659a  mov     edi, ecx
0x18000659c  call    cs:__imp_GetProcessHeap
0x1800065a2  mov     rsi, rax
0x1800065a5  mov     r8, rbx; dwBytes
0x1800065a8  mov     edx, edi; dwFlags
0x1800065aa  mov     rcx, rax; hHeap
0x1800065ad  call    cs:__imp_HeapAlloc
0x1800065b3  mov     rbx, rax
0x1800065b6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800065bd  test    rax, rax
0x1800065c0  jnz     short loc_180006608
0x1800065c2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800065c8  jnz     short loc_180006613
0x1800065ca  lea     rcx, ModuleName; "ntdll.dll"
0x1800065d1  call    cs:__imp_GetModuleHandleW
0x1800065d7  test    rax, rax
0x1800065da  jz      short loc_1800065F5
0x1800065dc  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800065e3  mov     rcx, rax; hModule
0x1800065e6  call    cs:__imp_GetProcAddress
0x1800065ec  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800065f3  jmp     short loc_1800065FC
0x1800065f5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800065fc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006603  test    rax, rax
0x180006606  jz      short loc_180006613
0x180006608  mov     rdx, rbx
0x18000660b  mov     rcx, rsi
0x18000660e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006613  mov     rax, rbx
0x180006616  mov     rbx, [rsp+28h+arg_0]
0x18000661b  mov     rsi, [rsp+28h+arg_8]
0x180006620  add     rsp, 20h
0x180006624  pop     rdi
0x180006625  retn
```
