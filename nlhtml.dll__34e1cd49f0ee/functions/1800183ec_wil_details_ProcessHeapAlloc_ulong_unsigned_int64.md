# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800183ec`
- end: `0x180018482`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180017ed0`
- `0x180018030`
- `0x1800194e0`
- `0x180019968`
- `0x18001a8c4`

## callees

- `0x18001534c`
- `0x1800183ec`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180018435`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180018435`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018411`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018411`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018400`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018400`

## string_xrefs

- `0x18001842e`: `ntdll.dll`

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
0x1800183ec  mov     [rsp+arg_0], rbx
0x1800183f1  mov     [rsp+arg_8], rsi
0x1800183f6  push    rdi
0x1800183f7  sub     rsp, 20h
0x1800183fb  mov     rbx, rdx
0x1800183fe  mov     edi, ecx
0x180018400  call    cs:__imp_GetProcessHeap
0x180018406  mov     rsi, rax
0x180018409  mov     r8, rbx; dwBytes
0x18001840c  mov     edx, edi; dwFlags
0x18001840e  mov     rcx, rax; hHeap
0x180018411  call    cs:__imp_HeapAlloc
0x180018417  mov     rbx, rax
0x18001841a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180018421  test    rax, rax
0x180018424  jnz     short loc_180018464
0x180018426  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001842c  jnz     short loc_18001846F
0x18001842e  lea     rcx, aNtdllDll; "ntdll.dll"
0x180018435  call    cs:__imp_GetModuleHandleW
0x18001843b  test    rax, rax
0x18001843e  jz      short loc_180018451
0x180018440  mov     rcx, rax
0x180018443  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180018448  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18001844f  jmp     short loc_180018458
0x180018451  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180018458  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001845f  test    rax, rax
0x180018462  jz      short loc_18001846F
0x180018464  mov     rdx, rbx
0x180018467  mov     rcx, rsi
0x18001846a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001846f  mov     rax, rbx
0x180018472  mov     rbx, [rsp+28h+arg_0]
0x180018477  mov     rsi, [rsp+28h+arg_8]
0x18001847c  add     rsp, 20h
0x180018480  pop     rdi
0x180018481  retn
```
