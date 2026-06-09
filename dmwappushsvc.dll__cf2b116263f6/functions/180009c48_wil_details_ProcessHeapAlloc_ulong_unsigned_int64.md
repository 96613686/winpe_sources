# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180009c48`
- end: `0x180009ce6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800097dc`
- `0x18000990c`
- `0x18000afc0`
- `0x18000b1e8`
- `0x18000caa4`

## callees

- `0x180009c48`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009c5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009c5c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009c6d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009c6d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009ca6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009ca6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009c91`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009c91`

## string_xrefs

- `0x180009c8a`: `ntdll.dll`

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
0x180009c48  mov     [rsp+arg_0], rbx
0x180009c4d  mov     [rsp+arg_8], rsi
0x180009c52  push    rdi
0x180009c53  sub     rsp, 20h
0x180009c57  mov     rbx, rdx
0x180009c5a  mov     edi, ecx
0x180009c5c  call    cs:__imp_GetProcessHeap
0x180009c62  mov     rsi, rax
0x180009c65  mov     r8, rbx; dwBytes
0x180009c68  mov     edx, edi; dwFlags
0x180009c6a  mov     rcx, rax; hHeap
0x180009c6d  call    cs:__imp_HeapAlloc
0x180009c73  mov     rbx, rax
0x180009c76  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180009c7d  test    rax, rax
0x180009c80  jnz     short loc_180009CC8
0x180009c82  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180009c88  jnz     short loc_180009CD3
0x180009c8a  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180009c91  call    cs:__imp_GetModuleHandleW
0x180009c97  test    rax, rax
0x180009c9a  jz      short loc_180009CB5
0x180009c9c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180009ca3  mov     rcx, rax; hModule
0x180009ca6  call    cs:__imp_GetProcAddress
0x180009cac  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180009cb3  jmp     short loc_180009CBC
0x180009cb5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180009cbc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180009cc3  test    rax, rax
0x180009cc6  jz      short loc_180009CD3
0x180009cc8  mov     rdx, rbx
0x180009ccb  mov     rcx, rsi
0x180009cce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cd3  mov     rax, rbx
0x180009cd6  mov     rbx, [rsp+28h+arg_0]
0x180009cdb  mov     rsi, [rsp+28h+arg_8]
0x180009ce0  add     rsp, 20h
0x180009ce4  pop     rdi
0x180009ce5  retn
```
