# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000dc6c`
- end: `0x18000dd02`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000d960`
- `0x18000e370`
- `0x18000e708`
- `0x180013ecc`
- `0x18001740c`

## callees

- `0x18000bc9c`
- `0x18000dc6c`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000dcb5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000dcb5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dc80`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dc80`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000dc91`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000dc91`

## string_xrefs

- `0x18000dcae`: `ntdll.dll`

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
0x18000dc6c  mov     [rsp+arg_0], rbx
0x18000dc71  mov     [rsp+arg_8], rsi
0x18000dc76  push    rdi
0x18000dc77  sub     rsp, 20h
0x18000dc7b  mov     rbx, rdx
0x18000dc7e  mov     edi, ecx
0x18000dc80  call    cs:__imp_GetProcessHeap
0x18000dc86  mov     rsi, rax
0x18000dc89  mov     r8, rbx; dwBytes
0x18000dc8c  mov     edx, edi; dwFlags
0x18000dc8e  mov     rcx, rax; hHeap
0x18000dc91  call    cs:__imp_HeapAlloc
0x18000dc97  mov     rbx, rax
0x18000dc9a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000dca1  test    rax, rax
0x18000dca4  jnz     short loc_18000DCE4
0x18000dca6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000dcac  jnz     short loc_18000DCEF
0x18000dcae  lea     rcx, ModuleName; "ntdll.dll"
0x18000dcb5  call    cs:__imp_GetModuleHandleW
0x18000dcbb  test    rax, rax
0x18000dcbe  jz      short loc_18000DCD1
0x18000dcc0  mov     rcx, rax
0x18000dcc3  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x18000dcc8  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000dccf  jmp     short loc_18000DCD8
0x18000dcd1  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000dcd8  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000dcdf  test    rax, rax
0x18000dce2  jz      short loc_18000DCEF
0x18000dce4  mov     rdx, rbx
0x18000dce7  mov     rcx, rsi
0x18000dcea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcef  mov     rax, rbx
0x18000dcf2  mov     rbx, [rsp+28h+arg_0]
0x18000dcf7  mov     rsi, [rsp+28h+arg_8]
0x18000dcfc  add     rsp, 20h
0x18000dd00  pop     rdi
0x18000dd01  retn
```
