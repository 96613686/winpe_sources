# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18003cb48`
- end: `0x18003cbe6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180021768`
- `0x18003c944`
- `0x18003d2fc`
- `0x18003d438`

## callees

- `0x18003cb48`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003cba6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003cba6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003cb91`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003cb91`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003cb6d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003cb6d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003cb5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003cb5c`

## string_xrefs

- `0x18003cb8a`: `ntdll.dll`

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
0x18003cb48  mov     [rsp+arg_0], rbx
0x18003cb4d  mov     [rsp+arg_8], rsi
0x18003cb52  push    rdi
0x18003cb53  sub     rsp, 20h
0x18003cb57  mov     rbx, rdx
0x18003cb5a  mov     edi, ecx
0x18003cb5c  call    cs:__imp_GetProcessHeap
0x18003cb62  mov     r8, rbx; dwBytes
0x18003cb65  mov     edx, edi; dwFlags
0x18003cb67  mov     rcx, rax; hHeap
0x18003cb6a  mov     rsi, rax
0x18003cb6d  call    cs:__imp_HeapAlloc
0x18003cb73  mov     rbx, rax
0x18003cb76  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18003cb7d  test    rax, rax
0x18003cb80  jnz     short loc_18003CBC8
0x18003cb82  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18003cb88  jnz     short loc_18003CBD3
0x18003cb8a  lea     rcx, ModuleName; "ntdll.dll"
0x18003cb91  call    cs:__imp_GetModuleHandleW
0x18003cb97  test    rax, rax
0x18003cb9a  jz      short loc_18003CBB5
0x18003cb9c  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x18003cba3  mov     rcx, rax; hModule
0x18003cba6  call    cs:__imp_GetProcAddress
0x18003cbac  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18003cbb3  jmp     short loc_18003CBBC
0x18003cbb5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18003cbbc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18003cbc3  test    rax, rax
0x18003cbc6  jz      short loc_18003CBD3
0x18003cbc8  mov     rdx, rbx
0x18003cbcb  mov     rcx, rsi
0x18003cbce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cbd3  mov     rsi, [rsp+28h+arg_8]
0x18003cbd8  mov     rax, rbx
0x18003cbdb  mov     rbx, [rsp+28h+arg_0]
0x18003cbe0  add     rsp, 20h
0x18003cbe4  pop     rdi
0x18003cbe5  retn
```
