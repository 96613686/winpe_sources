# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180008378`
- end: `0x18000840e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180008104`
- `0x1800087fc`
- `0x180008b94`

## callees

- `0x1800062e8`
- `0x180008378`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800083c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800083c1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000839d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000839d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000838c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000838c`

## string_xrefs

- `0x1800083ba`: `ntdll.dll`

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
0x180008378  mov     [rsp+arg_0], rbx
0x18000837d  mov     [rsp+arg_8], rsi
0x180008382  push    rdi
0x180008383  sub     rsp, 20h
0x180008387  mov     rbx, rdx
0x18000838a  mov     edi, ecx
0x18000838c  call    cs:__imp_GetProcessHeap
0x180008392  mov     rsi, rax
0x180008395  mov     r8, rbx; dwBytes
0x180008398  mov     edx, edi; dwFlags
0x18000839a  mov     rcx, rax; hHeap
0x18000839d  call    cs:__imp_HeapAlloc
0x1800083a3  mov     rbx, rax
0x1800083a6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800083ad  test    rax, rax
0x1800083b0  jnz     short loc_1800083F0
0x1800083b2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800083b8  jnz     short loc_1800083FB
0x1800083ba  lea     rcx, ModuleName; "ntdll.dll"
0x1800083c1  call    cs:__imp_GetModuleHandleW
0x1800083c7  test    rax, rax
0x1800083ca  jz      short loc_1800083DD
0x1800083cc  mov     rcx, rax
0x1800083cf  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x1800083d4  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800083db  jmp     short loc_1800083E4
0x1800083dd  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800083e4  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800083eb  test    rax, rax
0x1800083ee  jz      short loc_1800083FB
0x1800083f0  mov     rdx, rbx
0x1800083f3  mov     rcx, rsi
0x1800083f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083fb  mov     rax, rbx
0x1800083fe  mov     rbx, [rsp+28h+arg_0]
0x180008403  mov     rsi, [rsp+28h+arg_8]
0x180008408  add     rsp, 20h
0x18000840c  pop     rdi
0x18000840d  retn
```
