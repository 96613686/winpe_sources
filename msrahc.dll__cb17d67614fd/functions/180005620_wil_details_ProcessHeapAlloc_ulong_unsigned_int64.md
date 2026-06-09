# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180005620`
- end: `0x1800056b6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180005240`
- `0x180005370`
- `0x180006400`
- `0x180006888`
- `0x180007f14`

## callees

- `0x1800026bc`
- `0x180005620`
- `0x18001c010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180005669`
- `KERNEL32!GetModuleHandleW` at `0x180005669`
- `KERNEL32!GetProcessHeap` at `0x180005634`
- `KERNEL32!GetProcessHeap` at `0x180005634`
- `KERNEL32!HeapAlloc` at `0x180005645`
- `KERNEL32!HeapAlloc` at `0x180005645`

## string_xrefs

- `0x180005662`: `ntdll.dll`

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
0x180005620  mov     [rsp+arg_0], rbx
0x180005625  mov     [rsp+arg_8], rsi
0x18000562a  push    rdi
0x18000562b  sub     rsp, 20h
0x18000562f  mov     rbx, rdx
0x180005632  mov     edi, ecx
0x180005634  call    cs:__imp_GetProcessHeap
0x18000563a  mov     rsi, rax
0x18000563d  mov     r8, rbx; dwBytes
0x180005640  mov     edx, edi; dwFlags
0x180005642  mov     rcx, rax; hHeap
0x180005645  call    cs:__imp_HeapAlloc
0x18000564b  mov     rbx, rax
0x18000564e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005655  test    rax, rax
0x180005658  jnz     short loc_180005698
0x18000565a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005660  jnz     short loc_1800056A3
0x180005662  lea     rcx, ModuleName; "ntdll.dll"
0x180005669  call    cs:__imp_GetModuleHandleW
0x18000566f  test    rax, rax
0x180005672  jz      short loc_180005685
0x180005674  mov     rcx, rax
0x180005677  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x18000567c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005683  jmp     short loc_18000568C
0x180005685  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000568c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005693  test    rax, rax
0x180005696  jz      short loc_1800056A3
0x180005698  mov     rdx, rbx
0x18000569b  mov     rcx, rsi
0x18000569e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056a3  mov     rax, rbx
0x1800056a6  mov     rbx, [rsp+28h+arg_0]
0x1800056ab  mov     rsi, [rsp+28h+arg_8]
0x1800056b0  add     rsp, 20h
0x1800056b4  pop     rdi
0x1800056b5  retn
```
