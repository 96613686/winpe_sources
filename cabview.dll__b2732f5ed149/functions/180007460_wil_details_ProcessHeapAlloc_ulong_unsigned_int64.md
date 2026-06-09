# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180007460`
- end: `0x1800074f6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180005fec`
- `0x180006e60`
- `0x180006fd0`
- `0x180008594`
- `0x1800087bc`
- `0x180009eec`

## callees

- `0x1800032a4`
- `0x180007460`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007485`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007485`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007474`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007474`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800074a9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800074a9`

## string_xrefs

- `0x1800074a2`: `ntdll.dll`

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
0x180007460  mov     [rsp+arg_0], rbx
0x180007465  mov     [rsp+arg_8], rsi
0x18000746a  push    rdi
0x18000746b  sub     rsp, 20h
0x18000746f  mov     rbx, rdx
0x180007472  mov     edi, ecx
0x180007474  call    cs:__imp_GetProcessHeap
0x18000747a  mov     r8, rbx; dwBytes
0x18000747d  mov     edx, edi; dwFlags
0x18000747f  mov     rcx, rax; hHeap
0x180007482  mov     rsi, rax
0x180007485  call    cs:__imp_HeapAlloc
0x18000748b  mov     rbx, rax
0x18000748e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007495  test    rax, rax
0x180007498  jnz     short loc_1800074D8
0x18000749a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800074a0  jnz     short loc_1800074E3
0x1800074a2  lea     rcx, ModuleName; "ntdll.dll"
0x1800074a9  call    cs:__imp_GetModuleHandleW
0x1800074af  test    rax, rax
0x1800074b2  jz      short loc_1800074C5
0x1800074b4  mov     rcx, rax
0x1800074b7  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x1800074bc  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800074c3  jmp     short loc_1800074CC
0x1800074c5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800074cc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800074d3  test    rax, rax
0x1800074d6  jz      short loc_1800074E3
0x1800074d8  mov     rdx, rbx
0x1800074db  mov     rcx, rsi
0x1800074de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074e3  mov     rsi, [rsp+28h+arg_8]
0x1800074e8  mov     rax, rbx
0x1800074eb  mov     rbx, [rsp+28h+arg_0]
0x1800074f0  add     rsp, 20h
0x1800074f4  pop     rdi
0x1800074f5  retn
```
