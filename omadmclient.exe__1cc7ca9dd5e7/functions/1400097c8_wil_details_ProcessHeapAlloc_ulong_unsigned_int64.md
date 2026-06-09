# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1400097c8`
- end: `0x14000987f`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000714c`
- `0x140007528`
- `0x14000b84c`
- `0x14000d0ac`

## callees

- `0x1400097c8`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009838`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009838`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000981d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000981d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400097dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400097dc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400097f3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400097f3`

## string_xrefs

- `0x140009816`: `ntdll.dll`

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
0x1400097c8  mov     [rsp+arg_0], rbx
0x1400097cd  mov     [rsp+arg_8], rsi
0x1400097d2  push    rdi
0x1400097d3  sub     rsp, 20h
0x1400097d7  mov     rbx, rdx
0x1400097da  mov     edi, ecx
0x1400097dc  call    cs:__imp_GetProcessHeap
0x1400097e3  nop     dword ptr [rax+rax+00h]
0x1400097e8  mov     rsi, rax
0x1400097eb  mov     r8, rbx; dwBytes
0x1400097ee  mov     edx, edi; dwFlags
0x1400097f0  mov     rcx, rax; hHeap
0x1400097f3  call    cs:__imp_HeapAlloc
0x1400097fa  nop     dword ptr [rax+rax+00h]
0x1400097ff  mov     rbx, rax
0x140009802  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140009809  test    rax, rax
0x14000980c  jnz     short loc_140009860
0x14000980e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140009814  jnz     short loc_14000986B
0x140009816  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x14000981d  call    cs:__imp_GetModuleHandleW
0x140009824  nop     dword ptr [rax+rax+00h]
0x140009829  test    rax, rax
0x14000982c  jz      short loc_14000984D
0x14000982e  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x140009835  mov     rcx, rax; hModule
0x140009838  call    cs:__imp_GetProcAddress
0x14000983f  nop     dword ptr [rax+rax+00h]
0x140009844  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x14000984b  jmp     short loc_140009854
0x14000984d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140009854  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000985b  test    rax, rax
0x14000985e  jz      short loc_14000986B
0x140009860  mov     rdx, rbx
0x140009863  mov     rcx, rsi
0x140009866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000986b  mov     rax, rbx
0x14000986e  mov     rbx, [rsp+28h+arg_0]
0x140009873  mov     rsi, [rsp+28h+arg_8]
0x140009878  add     rsp, 20h
0x14000987c  pop     rdi
0x14000987d  retn
```
