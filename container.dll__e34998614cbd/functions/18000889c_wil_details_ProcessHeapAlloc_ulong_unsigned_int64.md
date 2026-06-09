# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000889c`
- end: `0x180008953`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005c6c`
- `0x180006018`
- `0x180007490`
- `0x18000a94c`
- `0x18000c008`

## callees

- `0x18000889c`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800088f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800088f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000890c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000890c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800088b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800088b0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800088c7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800088c7`

## string_xrefs

- `0x1800088ea`: `ntdll.dll`

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
0x18000889c  mov     [rsp+arg_0], rbx
0x1800088a1  mov     [rsp+arg_8], rsi
0x1800088a6  push    rdi
0x1800088a7  sub     rsp, 20h
0x1800088ab  mov     rbx, rdx
0x1800088ae  mov     edi, ecx
0x1800088b0  call    cs:__imp_GetProcessHeap
0x1800088b7  nop     dword ptr [rax+rax+00h]
0x1800088bc  mov     rsi, rax
0x1800088bf  mov     r8, rbx; dwBytes
0x1800088c2  mov     edx, edi; dwFlags
0x1800088c4  mov     rcx, rax; hHeap
0x1800088c7  call    cs:__imp_HeapAlloc
0x1800088ce  nop     dword ptr [rax+rax+00h]
0x1800088d3  mov     rbx, rax
0x1800088d6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800088dd  test    rax, rax
0x1800088e0  jnz     short loc_180008934
0x1800088e2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800088e8  jnz     short loc_18000893F
0x1800088ea  lea     rcx, ModuleName; "ntdll.dll"
0x1800088f1  call    cs:__imp_GetModuleHandleW
0x1800088f8  nop     dword ptr [rax+rax+00h]
0x1800088fd  test    rax, rax
0x180008900  jz      short loc_180008921
0x180008902  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180008909  mov     rcx, rax; hModule
0x18000890c  call    cs:__imp_GetProcAddress
0x180008913  nop     dword ptr [rax+rax+00h]
0x180008918  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000891f  jmp     short loc_180008928
0x180008921  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008928  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000892f  test    rax, rax
0x180008932  jz      short loc_18000893F
0x180008934  mov     rdx, rbx
0x180008937  mov     rcx, rsi
0x18000893a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000893f  mov     rax, rbx
0x180008942  mov     rbx, [rsp+28h+arg_0]
0x180008947  mov     rsi, [rsp+28h+arg_8]
0x18000894c  add     rsp, 20h
0x180008950  pop     rdi
0x180008951  retn
```
