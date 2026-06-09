# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180039984`
- end: `0x180039a1a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180038fb0`
- `0x180039820`
- `0x180039a20`
- `0x18004ba00`
- `0x1800568e8`

## callees

- `0x180039984`
- `0x18004f30c`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039998`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039998`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800399a9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800399a9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800399cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800399cd`

## string_xrefs

- `0x1800399c6`: `ntdll.dll`

## pseudocode

```c
LPVOID __fastcall wil::details::ProcessHeapAlloc(DWORD dwFlags, SIZE_T dwBytes)
{
  HANDLE ProcessHeap; // rsi
  LPVOID v5; // rbx
  void (__fastcall *ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z)(HANDLE, LPVOID); // rax
  HMODULE ModuleHandleW; // rax

  ProcessHeap = GetProcessHeap();
  v5 = HeapAlloc(ProcessHeap, dwFlags, dwBytes);
  ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z = (void (__fastcall *)(HANDLE, LPVOID))`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation;
  if ( `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation
    || !`wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation
    && ((ModuleHandleW = GetModuleHandleW(L"ntdll.dll")) == 0
      ? (ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z = (void (__fastcall *)(HANDLE, LPVOID))`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation)
      : (void (__fastcall *)(HANDLE, LPVOID))(ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z = (void (__fastcall *)(HANDLE, LPVOID))___GetProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z(ModuleHandleW),
                                              `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation = (__int64)ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z),
        `wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation = 1,
        ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z) )
  {
    ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z(ProcessHeap, v5);
  }
  return v5;
}

```

## disassembly

```asm
0x180039984  mov     [rsp+arg_0], rbx
0x180039989  mov     [rsp+arg_8], rsi
0x18003998e  push    rdi
0x18003998f  sub     rsp, 20h
0x180039993  mov     rbx, rdx
0x180039996  mov     edi, ecx
0x180039998  call    cs:__imp_GetProcessHeap
0x18003999e  mov     r8, rbx; dwBytes
0x1800399a1  mov     edx, edi; dwFlags
0x1800399a3  mov     rcx, rax; hHeap
0x1800399a6  mov     rsi, rax
0x1800399a9  call    cs:__imp_HeapAlloc
0x1800399af  mov     rbx, rax
0x1800399b2  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800399b9  test    rax, rax
0x1800399bc  jnz     short loc_1800399FC
0x1800399be  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800399c4  jnz     short loc_180039A07
0x1800399c6  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800399cd  call    cs:__imp_GetModuleHandleW
0x1800399d3  test    rax, rax
0x1800399d6  jz      short loc_1800399E9
0x1800399d8  mov     rcx, rax
0x1800399db  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x1800399e0  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800399e7  jmp     short loc_1800399F0
0x1800399e9  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800399f0  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800399f7  test    rax, rax
0x1800399fa  jz      short loc_180039A07
0x1800399fc  mov     rdx, rbx
0x1800399ff  mov     rcx, rsi
0x180039a02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039a07  mov     rsi, [rsp+28h+arg_8]
0x180039a0c  mov     rax, rbx
0x180039a0f  mov     rbx, [rsp+28h+arg_0]
0x180039a14  add     rsp, 20h
0x180039a18  pop     rdi
0x180039a19  retn
```
