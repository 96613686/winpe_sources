# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180005108`
- end: `0x18000519e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180004e4c`
- `0x18000558c`
- `0x180005924`

## callees

- `0x180002e18`
- `0x180005108`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005151`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005151`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000511c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000511c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000512d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000512d`

## string_xrefs

- `0x18000514a`: `ntdll.dll`

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
0x180005108  mov     [rsp+arg_0], rbx
0x18000510d  mov     [rsp+arg_8], rsi
0x180005112  push    rdi
0x180005113  sub     rsp, 20h
0x180005117  mov     rbx, rdx
0x18000511a  mov     edi, ecx
0x18000511c  call    cs:__imp_GetProcessHeap
0x180005122  mov     rsi, rax
0x180005125  mov     r8, rbx; dwBytes
0x180005128  mov     edx, edi; dwFlags
0x18000512a  mov     rcx, rax; hHeap
0x18000512d  call    cs:__imp_HeapAlloc
0x180005133  mov     rbx, rax
0x180005136  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000513d  test    rax, rax
0x180005140  jnz     short loc_180005180
0x180005142  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005148  jnz     short loc_18000518B
0x18000514a  lea     rcx, aNtdllDll; "ntdll.dll"
0x180005151  call    cs:__imp_GetModuleHandleW
0x180005157  test    rax, rax
0x18000515a  jz      short loc_18000516D
0x18000515c  mov     rcx, rax
0x18000515f  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180005164  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000516b  jmp     short loc_180005174
0x18000516d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005174  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000517b  test    rax, rax
0x18000517e  jz      short loc_18000518B
0x180005180  mov     rdx, rbx
0x180005183  mov     rcx, rsi
0x180005186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000518b  mov     rax, rbx
0x18000518e  mov     rbx, [rsp+28h+arg_0]
0x180005193  mov     rsi, [rsp+28h+arg_8]
0x180005198  add     rsp, 20h
0x18000519c  pop     rdi
0x18000519d  retn
```
