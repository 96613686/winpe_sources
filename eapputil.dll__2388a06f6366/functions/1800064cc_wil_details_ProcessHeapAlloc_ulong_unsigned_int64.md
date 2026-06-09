# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800064cc`
- end: `0x18000656a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004998`
- `0x180005330`
- `0x180006c94`
- `0x180009954`
- `0x18000c544`

## callees

- `0x1800064cc`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006515`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006515`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000652a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000652a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800064e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800064e0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800064f1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800064f1`

## string_xrefs

- `0x18000650e`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x1800064cc  mov     [rsp+arg_0], rbx
0x1800064d1  mov     [rsp+arg_8], rsi
0x1800064d6  push    rdi
0x1800064d7  sub     rsp, 20h
0x1800064db  mov     rbx, rdx
0x1800064de  mov     edi, ecx
0x1800064e0  call    cs:__imp_GetProcessHeap
0x1800064e6  mov     rsi, rax
0x1800064e9  mov     r8, rbx; dwBytes
0x1800064ec  mov     edx, edi; dwFlags
0x1800064ee  mov     rcx, rax; hHeap
0x1800064f1  call    cs:__imp_HeapAlloc
0x1800064f7  mov     rbx, rax
0x1800064fa  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180006501  test    rax, rax
0x180006504  jnz     short loc_18000654C
0x180006506  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000650c  jnz     short loc_180006557
0x18000650e  lea     rcx, ModuleName; "ntdll.dll"
0x180006515  call    cs:__imp_GetModuleHandleW
0x18000651b  test    rax, rax
0x18000651e  jz      short loc_180006539
0x180006520  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180006527  mov     rcx, rax; hModule
0x18000652a  call    cs:__imp_GetProcAddress
0x180006530  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180006537  jmp     short loc_180006540
0x180006539  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180006540  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006547  test    rax, rax
0x18000654a  jz      short loc_180006557
0x18000654c  mov     rdx, rbx
0x18000654f  mov     rcx, rsi
0x180006552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006557  mov     rax, rbx
0x18000655a  mov     rbx, [rsp+28h+arg_0]
0x18000655f  mov     rsi, [rsp+28h+arg_8]
0x180006564  add     rsp, 20h
0x180006568  pop     rdi
0x180006569  retn
```
