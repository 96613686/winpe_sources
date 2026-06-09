# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800047a8`
- end: `0x180004846`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800030c8`
- `0x180003760`
- `0x180004b10`

## callees

- `0x1800047a8`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004806`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004806`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800047f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800047f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800047bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800047bc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800047cd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800047cd`

## string_xrefs

- `0x1800047ea`: `ntdll.dll`

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
0x1800047a8  mov     [rsp+arg_0], rbx
0x1800047ad  mov     [rsp+arg_8], rsi
0x1800047b2  push    rdi
0x1800047b3  sub     rsp, 20h
0x1800047b7  mov     rbx, rdx
0x1800047ba  mov     edi, ecx
0x1800047bc  call    cs:__imp_GetProcessHeap
0x1800047c2  mov     rsi, rax
0x1800047c5  mov     r8, rbx; dwBytes
0x1800047c8  mov     edx, edi; dwFlags
0x1800047ca  mov     rcx, rax; hHeap
0x1800047cd  call    cs:__imp_HeapAlloc
0x1800047d3  mov     rbx, rax
0x1800047d6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800047dd  test    rax, rax
0x1800047e0  jnz     short loc_180004828
0x1800047e2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800047e8  jnz     short loc_180004833
0x1800047ea  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800047f1  call    cs:__imp_GetModuleHandleW
0x1800047f7  test    rax, rax
0x1800047fa  jz      short loc_180004815
0x1800047fc  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180004803  mov     rcx, rax; hModule
0x180004806  call    cs:__imp_GetProcAddress
0x18000480c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180004813  jmp     short loc_18000481C
0x180004815  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000481c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004823  test    rax, rax
0x180004826  jz      short loc_180004833
0x180004828  mov     rdx, rbx
0x18000482b  mov     rcx, rsi
0x18000482e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004833  mov     rax, rbx
0x180004836  mov     rbx, [rsp+28h+arg_0]
0x18000483b  mov     rsi, [rsp+28h+arg_8]
0x180004840  add     rsp, 20h
0x180004844  pop     rdi
0x180004845  retn
```
