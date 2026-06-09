# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180005c38`
- end: `0x180005cce`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180005754`
- `0x1800058b0`
- `0x180006900`
- `0x180006dc4`
- `0x180007eb8`

## callees

- `0x180002a20`
- `0x180005c38`
- `0x180026010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180005c4c`
- `KERNEL32!GetProcessHeap` at `0x180005c4c`
- `KERNEL32!HeapAlloc` at `0x180005c5d`
- `KERNEL32!HeapAlloc` at `0x180005c5d`
- `KERNEL32!GetModuleHandleW` at `0x180005c81`
- `KERNEL32!GetModuleHandleW` at `0x180005c81`

## string_xrefs

- `0x180005c7a`: `ntdll.dll`

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
0x180005c38  mov     [rsp+arg_0], rbx
0x180005c3d  mov     [rsp+arg_8], rsi
0x180005c42  push    rdi
0x180005c43  sub     rsp, 20h
0x180005c47  mov     rbx, rdx
0x180005c4a  mov     edi, ecx
0x180005c4c  call    cs:__imp_GetProcessHeap
0x180005c52  mov     rsi, rax
0x180005c55  mov     r8, rbx; dwBytes
0x180005c58  mov     edx, edi; dwFlags
0x180005c5a  mov     rcx, rax; hHeap
0x180005c5d  call    cs:__imp_HeapAlloc
0x180005c63  mov     rbx, rax
0x180005c66  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005c6d  test    rax, rax
0x180005c70  jnz     short loc_180005CB0
0x180005c72  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005c78  jnz     short loc_180005CBB
0x180005c7a  lea     rcx, ModuleName; "ntdll.dll"
0x180005c81  call    cs:__imp_GetModuleHandleW
0x180005c87  test    rax, rax
0x180005c8a  jz      short loc_180005C9D
0x180005c8c  mov     rcx, rax
0x180005c8f  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180005c94  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005c9b  jmp     short loc_180005CA4
0x180005c9d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005ca4  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005cab  test    rax, rax
0x180005cae  jz      short loc_180005CBB
0x180005cb0  mov     rdx, rbx
0x180005cb3  mov     rcx, rsi
0x180005cb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cbb  mov     rax, rbx
0x180005cbe  mov     rbx, [rsp+28h+arg_0]
0x180005cc3  mov     rsi, [rsp+28h+arg_8]
0x180005cc8  add     rsp, 20h
0x180005ccc  pop     rdi
0x180005ccd  retn
```
