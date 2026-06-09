# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180032158`
- end: `0x1800321ed`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `149`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000bde0`
- `0x180032550`
- `0x1800326b8`

## callees

- `0x18001273a`
- `0x180030a3c`
- `0x180032158`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003216c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003216c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003217d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003217d`

## string_xrefs

- `0x18003219a`: `ntdll.dll`

## pseudocode

```c
LPVOID __fastcall wil::details::ProcessHeapAlloc(DWORD dwFlags, SIZE_T dwBytes)
{
  HANDLE ProcessHeap; // rsi
  LPVOID v5; // rbx
  void (__fastcall *ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z)(HANDLE, LPVOID); // rax
  HMODULE ModuleHandleW_0; // rax

  ProcessHeap = GetProcessHeap();
  v5 = HeapAlloc(ProcessHeap, dwFlags, dwBytes);
  ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z = (void (__fastcall *)(HANDLE, LPVOID))`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation;
  if ( `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation
    || !`wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation
    && ((ModuleHandleW_0 = GetModuleHandleW_0(L"ntdll.dll")) == 0
      ? (ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z = (void (__fastcall *)(HANDLE, LPVOID))`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation)
      : (void (__fastcall *)(HANDLE, LPVOID))(ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z = (void (__fastcall *)(HANDLE, LPVOID))___GetProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z(ModuleHandleW_0),
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
0x180032158  mov     [rsp+arg_0], rbx
0x18003215d  mov     [rsp+arg_8], rsi
0x180032162  push    rdi
0x180032163  sub     rsp, 20h
0x180032167  mov     rbx, rdx
0x18003216a  mov     edi, ecx
0x18003216c  call    cs:__imp_GetProcessHeap
0x180032172  mov     r8, rbx; dwBytes
0x180032175  mov     edx, edi; dwFlags
0x180032177  mov     rcx, rax; hHeap
0x18003217a  mov     rsi, rax
0x18003217d  call    cs:__imp_HeapAlloc
0x180032183  mov     rbx, rax
0x180032186  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18003218d  test    rax, rax
0x180032190  jnz     short loc_1800321CF
0x180032192  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180032198  jnz     short loc_1800321DA
0x18003219a  lea     rcx, aNtdllDll; "ntdll.dll"
0x1800321a1  call    GetModuleHandleW_0
0x1800321a6  test    rax, rax
0x1800321a9  jz      short loc_1800321BC
0x1800321ab  mov     rcx, rax
0x1800321ae  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x1800321b3  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800321ba  jmp     short loc_1800321C3
0x1800321bc  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800321c3  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800321ca  test    rax, rax
0x1800321cd  jz      short loc_1800321DA
0x1800321cf  mov     rdx, rbx
0x1800321d2  mov     rcx, rsi
0x1800321d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800321da  mov     rsi, [rsp+28h+arg_8]
0x1800321df  mov     rax, rbx
0x1800321e2  mov     rbx, [rsp+28h+arg_0]
0x1800321e7  add     rsp, 20h
0x1800321eb  pop     rdi
0x1800321ec  retn
```
