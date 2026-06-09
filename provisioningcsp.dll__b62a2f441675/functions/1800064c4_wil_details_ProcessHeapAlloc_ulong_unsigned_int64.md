# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800064c4`
- end: `0x18000657b`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004bb0`
- `0x1800058d0`
- `0x180006ea4`
- `0x180014454`
- `0x180022984`

## callees

- `0x1800064c4`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006534`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006534`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006519`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006519`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800064ef`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800064ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800064d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800064d8`

## string_xrefs

- `0x180006512`: `ntdll.dll`

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
0x1800064c4  mov     [rsp+arg_0], rbx
0x1800064c9  mov     [rsp+arg_8], rsi
0x1800064ce  push    rdi
0x1800064cf  sub     rsp, 20h
0x1800064d3  mov     rbx, rdx
0x1800064d6  mov     edi, ecx
0x1800064d8  call    cs:__imp_GetProcessHeap
0x1800064df  nop     dword ptr [rax+rax+00h]
0x1800064e4  mov     rsi, rax
0x1800064e7  mov     r8, rbx; dwBytes
0x1800064ea  mov     edx, edi; dwFlags
0x1800064ec  mov     rcx, rax; hHeap
0x1800064ef  call    cs:__imp_HeapAlloc
0x1800064f6  nop     dword ptr [rax+rax+00h]
0x1800064fb  mov     rbx, rax
0x1800064fe  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180006505  test    rax, rax
0x180006508  jnz     short loc_18000655C
0x18000650a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006510  jnz     short loc_180006567
0x180006512  lea     rcx, ModuleName; "ntdll.dll"
0x180006519  call    cs:__imp_GetModuleHandleW
0x180006520  nop     dword ptr [rax+rax+00h]
0x180006525  test    rax, rax
0x180006528  jz      short loc_180006549
0x18000652a  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180006531  mov     rcx, rax; hModule
0x180006534  call    cs:__imp_GetProcAddress
0x18000653b  nop     dword ptr [rax+rax+00h]
0x180006540  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180006547  jmp     short loc_180006550
0x180006549  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180006550  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006557  test    rax, rax
0x18000655a  jz      short loc_180006567
0x18000655c  mov     rdx, rbx
0x18000655f  mov     rcx, rsi
0x180006562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006567  mov     rax, rbx
0x18000656a  mov     rbx, [rsp+28h+arg_0]
0x18000656f  mov     rsi, [rsp+28h+arg_8]
0x180006574  add     rsp, 20h
0x180006578  pop     rdi
0x180006579  retn
```
