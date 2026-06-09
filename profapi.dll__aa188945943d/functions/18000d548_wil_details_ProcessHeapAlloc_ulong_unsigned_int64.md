# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000d548`
- end: `0x18000d5e6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800022cc`
- `0x18000bf10`
- `0x18000d410`
- `0x18000ee5c`
- `0x1800114c0`

## callees

- `0x18000d548`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d591`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d591`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d5a6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d5a6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d56d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d56d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d55c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d55c`

## string_xrefs

- `0x18000d58a`: `ntdll.dll`

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
0x18000d548  mov     [rsp+arg_0], rbx
0x18000d54d  mov     [rsp+arg_8], rsi
0x18000d552  push    rdi
0x18000d553  sub     rsp, 20h
0x18000d557  mov     rbx, rdx
0x18000d55a  mov     edi, ecx
0x18000d55c  call    cs:__imp_GetProcessHeap
0x18000d562  mov     rsi, rax
0x18000d565  mov     r8, rbx; dwBytes
0x18000d568  mov     edx, edi; dwFlags
0x18000d56a  mov     rcx, rax; hHeap
0x18000d56d  call    cs:__imp_HeapAlloc
0x18000d573  mov     rbx, rax
0x18000d576  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000d57d  test    rax, rax
0x18000d580  jnz     short loc_18000D5C8
0x18000d582  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000d588  jnz     short loc_18000D5D3
0x18000d58a  lea     rcx, LibFileName; "ntdll.dll"
0x18000d591  call    cs:__imp_GetModuleHandleW
0x18000d597  test    rax, rax
0x18000d59a  jz      short loc_18000D5B5
0x18000d59c  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x18000d5a3  mov     rcx, rax; hModule
0x18000d5a6  call    cs:__imp_GetProcAddress
0x18000d5ac  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000d5b3  jmp     short loc_18000D5BC
0x18000d5b5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000d5bc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000d5c3  test    rax, rax
0x18000d5c6  jz      short loc_18000D5D3
0x18000d5c8  mov     rdx, rbx
0x18000d5cb  mov     rcx, rsi
0x18000d5ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5d3  mov     rax, rbx
0x18000d5d6  mov     rbx, [rsp+28h+arg_0]
0x18000d5db  mov     rsi, [rsp+28h+arg_8]
0x18000d5e0  add     rsp, 20h
0x18000d5e4  pop     rdi
0x18000d5e5  retn
```
