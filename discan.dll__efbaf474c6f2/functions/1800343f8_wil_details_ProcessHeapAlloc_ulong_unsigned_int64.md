# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800343f8`
- end: `0x18003448e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180033f2c`
- `0x180034080`
- `0x1800350a4`
- `0x180035308`
- `0x180036450`

## callees

- `0x180031628`
- `0x1800343f8`
- `0x180039010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18003441d`
- `KERNEL32!HeapAlloc` at `0x18003441d`
- `KERNEL32!GetProcessHeap` at `0x18003440c`
- `KERNEL32!GetProcessHeap` at `0x18003440c`
- `KERNEL32!GetModuleHandleW` at `0x180034441`
- `KERNEL32!GetModuleHandleW` at `0x180034441`

## string_xrefs

- `0x18003443a`: `ntdll.dll`

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
0x1800343f8  mov     [rsp+arg_0], rbx
0x1800343fd  mov     [rsp+arg_8], rsi
0x180034402  push    rdi
0x180034403  sub     rsp, 20h
0x180034407  mov     rbx, rdx
0x18003440a  mov     edi, ecx
0x18003440c  call    cs:__imp_GetProcessHeap
0x180034412  mov     r8, rbx; dwBytes
0x180034415  mov     edx, edi; dwFlags
0x180034417  mov     rcx, rax; hHeap
0x18003441a  mov     rsi, rax
0x18003441d  call    cs:__imp_HeapAlloc
0x180034423  mov     rbx, rax
0x180034426  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18003442d  test    rax, rax
0x180034430  jnz     short loc_180034470
0x180034432  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180034438  jnz     short loc_18003447B
0x18003443a  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180034441  call    cs:__imp_GetModuleHandleW
0x180034447  test    rax, rax
0x18003444a  jz      short loc_18003445D
0x18003444c  mov     rcx, rax
0x18003444f  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180034454  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18003445b  jmp     short loc_180034464
0x18003445d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180034464  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18003446b  test    rax, rax
0x18003446e  jz      short loc_18003447B
0x180034470  mov     rdx, rbx
0x180034473  mov     rcx, rsi
0x180034476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003447b  mov     rsi, [rsp+28h+arg_8]
0x180034480  mov     rax, rbx
0x180034483  mov     rbx, [rsp+28h+arg_0]
0x180034488  add     rsp, 20h
0x18003448c  pop     rdi
0x18003448d  retn
```
