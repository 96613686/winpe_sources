# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800100a8`
- end: `0x18001015f`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a8a4`
- `0x18000ac80`
- `0x1800129d0`
- `0x180013f2c`

## callees

- `0x1800100a8`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800100fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800100fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010118`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010118`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800100d3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800100d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800100bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800100bc`

## string_xrefs

- `0x1800100f6`: `ntdll.dll`

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
0x1800100a8  mov     [rsp+arg_0], rbx
0x1800100ad  mov     [rsp+arg_8], rsi
0x1800100b2  push    rdi
0x1800100b3  sub     rsp, 20h
0x1800100b7  mov     rbx, rdx
0x1800100ba  mov     edi, ecx
0x1800100bc  call    cs:__imp_GetProcessHeap
0x1800100c3  nop     dword ptr [rax+rax+00h]
0x1800100c8  mov     rsi, rax
0x1800100cb  mov     r8, rbx; dwBytes
0x1800100ce  mov     edx, edi; dwFlags
0x1800100d0  mov     rcx, rax; hHeap
0x1800100d3  call    cs:__imp_HeapAlloc
0x1800100da  nop     dword ptr [rax+rax+00h]
0x1800100df  mov     rbx, rax
0x1800100e2  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800100e9  test    rax, rax
0x1800100ec  jnz     short loc_180010140
0x1800100ee  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800100f4  jnz     short loc_18001014B
0x1800100f6  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800100fd  call    cs:__imp_GetModuleHandleW
0x180010104  nop     dword ptr [rax+rax+00h]
0x180010109  test    rax, rax
0x18001010c  jz      short loc_18001012D
0x18001010e  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180010115  mov     rcx, rax; hModule
0x180010118  call    cs:__imp_GetProcAddress
0x18001011f  nop     dword ptr [rax+rax+00h]
0x180010124  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18001012b  jmp     short loc_180010134
0x18001012d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180010134  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001013b  test    rax, rax
0x18001013e  jz      short loc_18001014B
0x180010140  mov     rdx, rbx
0x180010143  mov     rcx, rsi
0x180010146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001014b  mov     rax, rbx
0x18001014e  mov     rbx, [rsp+28h+arg_0]
0x180010153  mov     rsi, [rsp+28h+arg_8]
0x180010158  add     rsp, 20h
0x18001015c  pop     rdi
0x18001015d  retn
```
