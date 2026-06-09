# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18002a654`
- end: `0x18002a6f2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800141c0`
- `0x18001965c`
- `0x1800198f8`
- `0x180041974`
- `0x180041ab0`
- `0x180042938`
- `0x180043574`

## callees

- `0x18002a654`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a6b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a6b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002a69d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002a69d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a679`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a679`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a668`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a668`

## string_xrefs

- `0x18002a696`: `ntdll.dll`

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
0x18002a654  mov     [rsp+arg_0], rbx
0x18002a659  mov     [rsp+arg_8], rsi
0x18002a65e  push    rdi
0x18002a65f  sub     rsp, 20h
0x18002a663  mov     rbx, rdx
0x18002a666  mov     edi, ecx
0x18002a668  call    cs:__imp_GetProcessHeap
0x18002a66e  mov     rsi, rax
0x18002a671  mov     r8, rbx; dwBytes
0x18002a674  mov     edx, edi; dwFlags
0x18002a676  mov     rcx, rax; hHeap
0x18002a679  call    cs:__imp_HeapAlloc
0x18002a67f  mov     rbx, rax
0x18002a682  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18002a689  test    rax, rax
0x18002a68c  jnz     short loc_18002A6D4
0x18002a68e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18002a694  jnz     short loc_18002A6DF
0x18002a696  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18002a69d  call    cs:__imp_GetModuleHandleW
0x18002a6a3  test    rax, rax
0x18002a6a6  jz      short loc_18002A6C1
0x18002a6a8  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18002a6af  mov     rcx, rax; hModule
0x18002a6b2  call    cs:__imp_GetProcAddress
0x18002a6b8  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18002a6bf  jmp     short loc_18002A6C8
0x18002a6c1  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18002a6c8  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18002a6cf  test    rax, rax
0x18002a6d2  jz      short loc_18002A6DF
0x18002a6d4  mov     rdx, rbx
0x18002a6d7  mov     rcx, rsi
0x18002a6da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a6df  mov     rax, rbx
0x18002a6e2  mov     rbx, [rsp+28h+arg_0]
0x18002a6e7  mov     rsi, [rsp+28h+arg_8]
0x18002a6ec  add     rsp, 20h
0x18002a6f0  pop     rdi
0x18002a6f1  retn
```
