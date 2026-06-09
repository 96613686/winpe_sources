# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000ef40`
- end: `0x18000efd6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000e694`
- `0x18000e7f4`
- `0x180011398`
- `0x1800115f8`
- `0x180012ffc`

## callees

- `0x1800091d4`
- `0x18000ef40`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ef89`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ef89`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ef65`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ef65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ef54`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ef54`

## string_xrefs

- `0x18000ef82`: `ntdll.dll`

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
0x18000ef40  mov     [rsp+arg_0], rbx
0x18000ef45  mov     [rsp+arg_8], rsi
0x18000ef4a  push    rdi
0x18000ef4b  sub     rsp, 20h
0x18000ef4f  mov     rbx, rdx
0x18000ef52  mov     edi, ecx
0x18000ef54  call    cs:__imp_GetProcessHeap
0x18000ef5a  mov     rsi, rax
0x18000ef5d  mov     r8, rbx; dwBytes
0x18000ef60  mov     edx, edi; dwFlags
0x18000ef62  mov     rcx, rax; hHeap
0x18000ef65  call    cs:__imp_HeapAlloc
0x18000ef6b  mov     rbx, rax
0x18000ef6e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000ef75  test    rax, rax
0x18000ef78  jnz     short loc_18000EFB8
0x18000ef7a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000ef80  jnz     short loc_18000EFC3
0x18000ef82  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18000ef89  call    cs:__imp_GetModuleHandleW
0x18000ef8f  test    rax, rax
0x18000ef92  jz      short loc_18000EFA5
0x18000ef94  mov     rcx, rax
0x18000ef97  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x18000ef9c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000efa3  jmp     short loc_18000EFAC
0x18000efa5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000efac  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000efb3  test    rax, rax
0x18000efb6  jz      short loc_18000EFC3
0x18000efb8  mov     rdx, rbx
0x18000efbb  mov     rcx, rsi
0x18000efbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efc3  mov     rax, rbx
0x18000efc6  mov     rbx, [rsp+28h+arg_0]
0x18000efcb  mov     rsi, [rsp+28h+arg_8]
0x18000efd0  add     rsp, 20h
0x18000efd4  pop     rdi
0x18000efd5  retn
```
