# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180007688`
- end: `0x18000771e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800070cc`
- `0x180007230`
- `0x180008590`
- `0x180008a14`
- `0x180009d24`

## callees

- `0x180004258`
- `0x180007688`
- `0x180040010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800076d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800076d1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800076ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800076ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000769c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000769c`

## string_xrefs

- `0x1800076ca`: `ntdll.dll`

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
0x180007688  mov     [rsp+arg_0], rbx
0x18000768d  mov     [rsp+arg_8], rsi
0x180007692  push    rdi
0x180007693  sub     rsp, 20h
0x180007697  mov     rbx, rdx
0x18000769a  mov     edi, ecx
0x18000769c  call    cs:__imp_GetProcessHeap
0x1800076a2  mov     rsi, rax
0x1800076a5  mov     r8, rbx; dwBytes
0x1800076a8  mov     edx, edi; dwFlags
0x1800076aa  mov     rcx, rax; hHeap
0x1800076ad  call    cs:__imp_HeapAlloc
0x1800076b3  mov     rbx, rax
0x1800076b6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800076bd  test    rax, rax
0x1800076c0  jnz     short loc_180007700
0x1800076c2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800076c8  jnz     short loc_18000770B
0x1800076ca  lea     rcx, ModuleName; "ntdll.dll"
0x1800076d1  call    cs:__imp_GetModuleHandleW
0x1800076d7  test    rax, rax
0x1800076da  jz      short loc_1800076ED
0x1800076dc  mov     rcx, rax
0x1800076df  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x1800076e4  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800076eb  jmp     short loc_1800076F4
0x1800076ed  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800076f4  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800076fb  test    rax, rax
0x1800076fe  jz      short loc_18000770B
0x180007700  mov     rdx, rbx
0x180007703  mov     rcx, rsi
0x180007706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000770b  mov     rax, rbx
0x18000770e  mov     rbx, [rsp+28h+arg_0]
0x180007713  mov     rsi, [rsp+28h+arg_8]
0x180007718  add     rsp, 20h
0x18000771c  pop     rdi
0x18000771d  retn
```
