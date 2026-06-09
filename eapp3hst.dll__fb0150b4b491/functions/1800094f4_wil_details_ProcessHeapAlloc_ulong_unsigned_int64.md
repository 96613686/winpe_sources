# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800094f4`
- end: `0x18000958a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180008ff4`
- `0x180009148`
- `0x18000a790`
- `0x18000a9b8`
- `0x18000bc20`

## callees

- `0x180005184`
- `0x1800094f4`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000953d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000953d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009508`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009508`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009519`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009519`

## string_xrefs

- `0x180009536`: `ntdll.dll`

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
0x1800094f4  mov     [rsp+arg_0], rbx
0x1800094f9  mov     [rsp+arg_8], rsi
0x1800094fe  push    rdi
0x1800094ff  sub     rsp, 20h
0x180009503  mov     rbx, rdx
0x180009506  mov     edi, ecx
0x180009508  call    cs:__imp_GetProcessHeap
0x18000950e  mov     rsi, rax
0x180009511  mov     r8, rbx; dwBytes
0x180009514  mov     edx, edi; dwFlags
0x180009516  mov     rcx, rax; hHeap
0x180009519  call    cs:__imp_HeapAlloc
0x18000951f  mov     rbx, rax
0x180009522  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180009529  test    rax, rax
0x18000952c  jnz     short loc_18000956C
0x18000952e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180009534  jnz     short loc_180009577
0x180009536  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000953d  call    cs:__imp_GetModuleHandleW
0x180009543  test    rax, rax
0x180009546  jz      short loc_180009559
0x180009548  mov     rcx, rax
0x18000954b  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180009550  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180009557  jmp     short loc_180009560
0x180009559  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180009560  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180009567  test    rax, rax
0x18000956a  jz      short loc_180009577
0x18000956c  mov     rdx, rbx
0x18000956f  mov     rcx, rsi
0x180009572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009577  mov     rax, rbx
0x18000957a  mov     rbx, [rsp+28h+arg_0]
0x18000957f  mov     rsi, [rsp+28h+arg_8]
0x180009584  add     rsp, 20h
0x180009588  pop     rdi
0x180009589  retn
```
