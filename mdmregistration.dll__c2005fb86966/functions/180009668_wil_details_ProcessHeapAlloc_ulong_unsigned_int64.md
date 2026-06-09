# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180009668`
- end: `0x18000971f`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000717c`
- `0x180007558`
- `0x18000b9ac`
- `0x18000ce0c`

## callees

- `0x180009668`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800096bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800096bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800096d8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800096d8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009693`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009693`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000967c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000967c`

## string_xrefs

- `0x1800096b6`: `ntdll.dll`

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
0x180009668  mov     [rsp+arg_0], rbx
0x18000966d  mov     [rsp+arg_8], rsi
0x180009672  push    rdi
0x180009673  sub     rsp, 20h
0x180009677  mov     rbx, rdx
0x18000967a  mov     edi, ecx
0x18000967c  call    cs:__imp_GetProcessHeap
0x180009683  nop     dword ptr [rax+rax+00h]
0x180009688  mov     rsi, rax
0x18000968b  mov     r8, rbx; dwBytes
0x18000968e  mov     edx, edi; dwFlags
0x180009690  mov     rcx, rax; hHeap
0x180009693  call    cs:__imp_HeapAlloc
0x18000969a  nop     dword ptr [rax+rax+00h]
0x18000969f  mov     rbx, rax
0x1800096a2  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800096a9  test    rax, rax
0x1800096ac  jnz     short loc_180009700
0x1800096ae  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800096b4  jnz     short loc_18000970B
0x1800096b6  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x1800096bd  call    cs:__imp_GetModuleHandleW
0x1800096c4  nop     dword ptr [rax+rax+00h]
0x1800096c9  test    rax, rax
0x1800096cc  jz      short loc_1800096ED
0x1800096ce  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800096d5  mov     rcx, rax; hModule
0x1800096d8  call    cs:__imp_GetProcAddress
0x1800096df  nop     dword ptr [rax+rax+00h]
0x1800096e4  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800096eb  jmp     short loc_1800096F4
0x1800096ed  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800096f4  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800096fb  test    rax, rax
0x1800096fe  jz      short loc_18000970B
0x180009700  mov     rdx, rbx
0x180009703  mov     rcx, rsi
0x180009706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000970b  mov     rax, rbx
0x18000970e  mov     rbx, [rsp+28h+arg_0]
0x180009713  mov     rsi, [rsp+28h+arg_8]
0x180009718  add     rsp, 20h
0x18000971c  pop     rdi
0x18000971d  retn
```
