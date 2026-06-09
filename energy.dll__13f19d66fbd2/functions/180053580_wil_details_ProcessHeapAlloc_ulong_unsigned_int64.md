# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180053580`
- end: `0x180053616`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18003e024`
- `0x1800530a0`
- `0x1800531c4`
- `0x1800542e0`
- `0x180054764`

## callees

- `0x18005044c`
- `0x180053580`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800535c9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800535c9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800535a5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800535a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180053594`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180053594`

## string_xrefs

- `0x1800535c2`: `ntdll.dll`

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
0x180053580  mov     [rsp+arg_0], rbx
0x180053585  mov     [rsp+arg_8], rsi
0x18005358a  push    rdi
0x18005358b  sub     rsp, 20h
0x18005358f  mov     rbx, rdx
0x180053592  mov     edi, ecx
0x180053594  call    cs:__imp_GetProcessHeap
0x18005359a  mov     rsi, rax
0x18005359d  mov     r8, rbx; dwBytes
0x1800535a0  mov     edx, edi; dwFlags
0x1800535a2  mov     rcx, rax; hHeap
0x1800535a5  call    cs:__imp_HeapAlloc
0x1800535ab  mov     rbx, rax
0x1800535ae  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800535b5  test    rax, rax
0x1800535b8  jnz     short loc_1800535F8
0x1800535ba  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800535c0  jnz     short loc_180053603
0x1800535c2  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x1800535c9  call    cs:__imp_GetModuleHandleW
0x1800535cf  test    rax, rax
0x1800535d2  jz      short loc_1800535E5
0x1800535d4  mov     rcx, rax
0x1800535d7  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x1800535dc  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800535e3  jmp     short loc_1800535EC
0x1800535e5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800535ec  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800535f3  test    rax, rax
0x1800535f6  jz      short loc_180053603
0x1800535f8  mov     rdx, rbx
0x1800535fb  mov     rcx, rsi
0x1800535fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053603  mov     rax, rbx
0x180053606  mov     rbx, [rsp+28h+arg_0]
0x18005360b  mov     rsi, [rsp+28h+arg_8]
0x180053610  add     rsp, 20h
0x180053614  pop     rdi
0x180053615  retn
```
