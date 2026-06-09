# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800063d8`
- end: `0x180006476`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004b38`
- `0x1800052e0`
- `0x1800058b0`
- `0x1800068b4`
- `0x1800095cc`
- `0x18000fc94`

## callees

- `0x1800063d8`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006421`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006421`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006436`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006436`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800063ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800063ec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800063fd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800063fd`

## string_xrefs

- `0x18000641a`: `ntdll.dll`

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
0x1800063d8  mov     [rsp+arg_0], rbx
0x1800063dd  mov     [rsp+arg_8], rsi
0x1800063e2  push    rdi
0x1800063e3  sub     rsp, 20h
0x1800063e7  mov     rbx, rdx
0x1800063ea  mov     edi, ecx
0x1800063ec  call    cs:__imp_GetProcessHeap
0x1800063f2  mov     rsi, rax
0x1800063f5  mov     r8, rbx; dwBytes
0x1800063f8  mov     edx, edi; dwFlags
0x1800063fa  mov     rcx, rax; hHeap
0x1800063fd  call    cs:__imp_HeapAlloc
0x180006403  mov     rbx, rax
0x180006406  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000640d  test    rax, rax
0x180006410  jnz     short loc_180006458
0x180006412  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006418  jnz     short loc_180006463
0x18000641a  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180006421  call    cs:__imp_GetModuleHandleW
0x180006427  test    rax, rax
0x18000642a  jz      short loc_180006445
0x18000642c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180006433  mov     rcx, rax; hModule
0x180006436  call    cs:__imp_GetProcAddress
0x18000643c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180006443  jmp     short loc_18000644C
0x180006445  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000644c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006453  test    rax, rax
0x180006456  jz      short loc_180006463
0x180006458  mov     rdx, rbx
0x18000645b  mov     rcx, rsi
0x18000645e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006463  mov     rax, rbx
0x180006466  mov     rbx, [rsp+28h+arg_0]
0x18000646b  mov     rsi, [rsp+28h+arg_8]
0x180006470  add     rsp, 20h
0x180006474  pop     rdi
0x180006475  retn
```
