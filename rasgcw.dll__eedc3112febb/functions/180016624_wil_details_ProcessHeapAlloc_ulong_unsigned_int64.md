# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180016624`
- end: `0x1800166c2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800153bc`
- `0x180015e40`
- `0x180016c3c`
- `0x180016fd4`

## callees

- `0x180016624`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016682`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016682`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001666d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001666d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016649`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016649`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016638`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016638`

## string_xrefs

- `0x180016666`: `ntdll.dll`

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
0x180016624  mov     [rsp+arg_0], rbx
0x180016629  mov     [rsp+arg_8], rsi
0x18001662e  push    rdi
0x18001662f  sub     rsp, 20h
0x180016633  mov     rbx, rdx
0x180016636  mov     edi, ecx
0x180016638  call    cs:__imp_GetProcessHeap
0x18001663e  mov     rsi, rax
0x180016641  mov     r8, rbx; dwBytes
0x180016644  mov     edx, edi; dwFlags
0x180016646  mov     rcx, rax; hHeap
0x180016649  call    cs:__imp_HeapAlloc
0x18001664f  mov     rbx, rax
0x180016652  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180016659  test    rax, rax
0x18001665c  jnz     short loc_1800166A4
0x18001665e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180016664  jnz     short loc_1800166AF
0x180016666  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18001666d  call    cs:__imp_GetModuleHandleW
0x180016673  test    rax, rax
0x180016676  jz      short loc_180016691
0x180016678  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18001667f  mov     rcx, rax; hModule
0x180016682  call    cs:__imp_GetProcAddress
0x180016688  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18001668f  jmp     short loc_180016698
0x180016691  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180016698  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001669f  test    rax, rax
0x1800166a2  jz      short loc_1800166AF
0x1800166a4  mov     rdx, rbx
0x1800166a7  mov     rcx, rsi
0x1800166aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166af  mov     rax, rbx
0x1800166b2  mov     rbx, [rsp+28h+arg_0]
0x1800166b7  mov     rsi, [rsp+28h+arg_8]
0x1800166bc  add     rsp, 20h
0x1800166c0  pop     rdi
0x1800166c1  retn
```
