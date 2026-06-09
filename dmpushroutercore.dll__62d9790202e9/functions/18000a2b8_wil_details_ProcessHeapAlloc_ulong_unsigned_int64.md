# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000a2b8`
- end: `0x18000a356`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180007ee8`
- `0x1800082b8`
- `0x180008fb0`
- `0x180009580`
- `0x18000bba4`
- `0x18000d58c`

## callees

- `0x18000a2b8`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a2dd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a2dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a2cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a2cc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a301`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a301`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a316`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a316`

## string_xrefs

- `0x18000a2fa`: `ntdll.dll`

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
0x18000a2b8  mov     [rsp+arg_0], rbx
0x18000a2bd  mov     [rsp+arg_8], rsi
0x18000a2c2  push    rdi
0x18000a2c3  sub     rsp, 20h
0x18000a2c7  mov     rbx, rdx
0x18000a2ca  mov     edi, ecx
0x18000a2cc  call    cs:__imp_GetProcessHeap
0x18000a2d2  mov     rsi, rax
0x18000a2d5  mov     r8, rbx; dwBytes
0x18000a2d8  mov     edx, edi; dwFlags
0x18000a2da  mov     rcx, rax; hHeap
0x18000a2dd  call    cs:__imp_HeapAlloc
0x18000a2e3  mov     rbx, rax
0x18000a2e6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000a2ed  test    rax, rax
0x18000a2f0  jnz     short loc_18000A338
0x18000a2f2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000a2f8  jnz     short loc_18000A343
0x18000a2fa  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000a301  call    cs:__imp_GetModuleHandleW
0x18000a307  test    rax, rax
0x18000a30a  jz      short loc_18000A325
0x18000a30c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000a313  mov     rcx, rax; hModule
0x18000a316  call    cs:__imp_GetProcAddress
0x18000a31c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000a323  jmp     short loc_18000A32C
0x18000a325  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000a32c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000a333  test    rax, rax
0x18000a336  jz      short loc_18000A343
0x18000a338  mov     rdx, rbx
0x18000a33b  mov     rcx, rsi
0x18000a33e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a343  mov     rax, rbx
0x18000a346  mov     rbx, [rsp+28h+arg_0]
0x18000a34b  mov     rsi, [rsp+28h+arg_8]
0x18000a350  add     rsp, 20h
0x18000a354  pop     rdi
0x18000a355  retn
```
