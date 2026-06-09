# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180006658`
- end: `0x1800066f6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800064b4`
- `0x180006b20`
- `0x180006eb8`

## callees

- `0x180006658`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800066a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800066a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800066b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800066b6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000667d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000667d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000666c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000666c`

## string_xrefs

- `0x18000669a`: `ntdll.dll`

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
0x180006658  mov     [rsp+arg_0], rbx
0x18000665d  mov     [rsp+arg_8], rsi
0x180006662  push    rdi
0x180006663  sub     rsp, 20h
0x180006667  mov     rbx, rdx
0x18000666a  mov     edi, ecx
0x18000666c  call    cs:__imp_GetProcessHeap
0x180006672  mov     rsi, rax
0x180006675  mov     r8, rbx; dwBytes
0x180006678  mov     edx, edi; dwFlags
0x18000667a  mov     rcx, rax; hHeap
0x18000667d  call    cs:__imp_HeapAlloc
0x180006683  mov     rbx, rax
0x180006686  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000668d  test    rax, rax
0x180006690  jnz     short loc_1800066D8
0x180006692  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006698  jnz     short loc_1800066E3
0x18000669a  lea     rcx, ModuleName; "ntdll.dll"
0x1800066a1  call    cs:__imp_GetModuleHandleW
0x1800066a7  test    rax, rax
0x1800066aa  jz      short loc_1800066C5
0x1800066ac  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x1800066b3  mov     rcx, rax; hModule
0x1800066b6  call    cs:__imp_GetProcAddress
0x1800066bc  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800066c3  jmp     short loc_1800066CC
0x1800066c5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800066cc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800066d3  test    rax, rax
0x1800066d6  jz      short loc_1800066E3
0x1800066d8  mov     rdx, rbx
0x1800066db  mov     rcx, rsi
0x1800066de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066e3  mov     rax, rbx
0x1800066e6  mov     rbx, [rsp+28h+arg_0]
0x1800066eb  mov     rsi, [rsp+28h+arg_8]
0x1800066f0  add     rsp, 20h
0x1800066f4  pop     rdi
0x1800066f5  retn
```
