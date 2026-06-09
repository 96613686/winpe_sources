# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18001adc0`
- end: `0x18001ae69`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `169`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180011f78`
- `0x18001a834`
- `0x18001a968`
- `0x18001bcf4`
- `0x18001c1fc`

## callees

- `0x180016a90`
- `0x18001adc0`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001ae15`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001ae15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001add4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001add4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001adeb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001adeb`

## string_xrefs

- `0x18001ae0e`: `ntdll.dll`

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
0x18001adc0  mov     [rsp+arg_0], rbx
0x18001adc5  mov     [rsp+arg_8], rsi
0x18001adca  push    rdi
0x18001adcb  sub     rsp, 20h
0x18001adcf  mov     rbx, rdx
0x18001add2  mov     edi, ecx
0x18001add4  call    cs:__imp_GetProcessHeap
0x18001addb  nop     dword ptr [rax+rax+00h]
0x18001ade0  mov     rsi, rax
0x18001ade3  mov     r8, rbx; dwBytes
0x18001ade6  mov     edx, edi; dwFlags
0x18001ade8  mov     rcx, rax; hHeap
0x18001adeb  call    cs:__imp_HeapAlloc
0x18001adf2  nop     dword ptr [rax+rax+00h]
0x18001adf7  mov     rbx, rax
0x18001adfa  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18001ae01  test    rax, rax
0x18001ae04  jnz     short loc_18001AE4A
0x18001ae06  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001ae0c  jnz     short loc_18001AE55
0x18001ae0e  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18001ae15  call    cs:__imp_GetModuleHandleW
0x18001ae1c  nop     dword ptr [rax+rax+00h]
0x18001ae21  test    rax, rax
0x18001ae24  jz      short loc_18001AE37
0x18001ae26  mov     rcx, rax
0x18001ae29  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x18001ae2e  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18001ae35  jmp     short loc_18001AE3E
0x18001ae37  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18001ae3e  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001ae45  test    rax, rax
0x18001ae48  jz      short loc_18001AE55
0x18001ae4a  mov     rdx, rbx
0x18001ae4d  mov     rcx, rsi
0x18001ae50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae55  mov     rax, rbx
0x18001ae58  mov     rbx, [rsp+28h+arg_0]
0x18001ae5d  mov     rsi, [rsp+28h+arg_8]
0x18001ae62  add     rsp, 20h
0x18001ae66  pop     rdi
0x18001ae67  retn
```
