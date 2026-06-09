# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000603c`
- end: `0x1800060da`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003ac8`
- `0x180003e98`
- `0x180004b90`
- `0x180007774`
- `0x18000900c`

## callees

- `0x18000603c`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006085`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006085`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000609a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000609a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006061`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006061`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006050`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006050`

## string_xrefs

- `0x18000607e`: `ntdll.dll`

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
0x18000603c  mov     [rsp+arg_0], rbx
0x180006041  mov     [rsp+arg_8], rsi
0x180006046  push    rdi
0x180006047  sub     rsp, 20h
0x18000604b  mov     rbx, rdx
0x18000604e  mov     edi, ecx
0x180006050  call    cs:__imp_GetProcessHeap
0x180006056  mov     rsi, rax
0x180006059  mov     r8, rbx; dwBytes
0x18000605c  mov     edx, edi; dwFlags
0x18000605e  mov     rcx, rax; hHeap
0x180006061  call    cs:__imp_HeapAlloc
0x180006067  mov     rbx, rax
0x18000606a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180006071  test    rax, rax
0x180006074  jnz     short loc_1800060BC
0x180006076  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000607c  jnz     short loc_1800060C7
0x18000607e  lea     rcx, ModuleName; "ntdll.dll"
0x180006085  call    cs:__imp_GetModuleHandleW
0x18000608b  test    rax, rax
0x18000608e  jz      short loc_1800060A9
0x180006090  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180006097  mov     rcx, rax; hModule
0x18000609a  call    cs:__imp_GetProcAddress
0x1800060a0  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800060a7  jmp     short loc_1800060B0
0x1800060a9  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800060b0  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800060b7  test    rax, rax
0x1800060ba  jz      short loc_1800060C7
0x1800060bc  mov     rdx, rbx
0x1800060bf  mov     rcx, rsi
0x1800060c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060c7  mov     rax, rbx
0x1800060ca  mov     rbx, [rsp+28h+arg_0]
0x1800060cf  mov     rsi, [rsp+28h+arg_8]
0x1800060d4  add     rsp, 20h
0x1800060d8  pop     rdi
0x1800060d9  retn
```
