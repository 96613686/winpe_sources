# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800055a8`
- end: `0x18000563e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800052ec`
- `0x180005a9c`
- `0x180005e34`

## callees

- `0x1800029dc`
- `0x1800055a8`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800055f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800055f1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800055cd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800055cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800055bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800055bc`

## string_xrefs

- `0x1800055ea`: `ntdll.dll`

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
0x1800055a8  mov     [rsp+arg_0], rbx
0x1800055ad  mov     [rsp+arg_8], rsi
0x1800055b2  push    rdi
0x1800055b3  sub     rsp, 20h
0x1800055b7  mov     rbx, rdx
0x1800055ba  mov     edi, ecx
0x1800055bc  call    cs:__imp_GetProcessHeap
0x1800055c2  mov     rsi, rax
0x1800055c5  mov     r8, rbx; dwBytes
0x1800055c8  mov     edx, edi; dwFlags
0x1800055ca  mov     rcx, rax; hHeap
0x1800055cd  call    cs:__imp_HeapAlloc
0x1800055d3  mov     rbx, rax
0x1800055d6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800055dd  test    rax, rax
0x1800055e0  jnz     short loc_180005620
0x1800055e2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800055e8  jnz     short loc_18000562B
0x1800055ea  lea     rcx, LibFileName; "ntdll.dll"
0x1800055f1  call    cs:__imp_GetModuleHandleW
0x1800055f7  test    rax, rax
0x1800055fa  jz      short loc_18000560D
0x1800055fc  mov     rcx, rax
0x1800055ff  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180005604  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000560b  jmp     short loc_180005614
0x18000560d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005614  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000561b  test    rax, rax
0x18000561e  jz      short loc_18000562B
0x180005620  mov     rdx, rbx
0x180005623  mov     rcx, rsi
0x180005626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000562b  mov     rax, rbx
0x18000562e  mov     rbx, [rsp+28h+arg_0]
0x180005633  mov     rsi, [rsp+28h+arg_8]
0x180005638  add     rsp, 20h
0x18000563c  pop     rdi
0x18000563d  retn
```
