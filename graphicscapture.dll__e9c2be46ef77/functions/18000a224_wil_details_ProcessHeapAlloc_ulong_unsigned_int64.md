# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000a224`
- end: `0x18000a2ba`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180009bd0`
- `0x180009d34`
- `0x18000b230`
- `0x18000b6b4`
- `0x18000c990`

## callees

- `0x180006c04`
- `0x18000a224`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a26d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a26d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a249`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a249`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a238`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a238`

## string_xrefs

- `0x18000a266`: `ntdll.dll`

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
0x18000a224  mov     [rsp+arg_0], rbx
0x18000a229  mov     [rsp+arg_8], rsi
0x18000a22e  push    rdi
0x18000a22f  sub     rsp, 20h
0x18000a233  mov     rbx, rdx
0x18000a236  mov     edi, ecx
0x18000a238  call    cs:__imp_GetProcessHeap
0x18000a23e  mov     rsi, rax
0x18000a241  mov     r8, rbx; dwBytes
0x18000a244  mov     edx, edi; dwFlags
0x18000a246  mov     rcx, rax; hHeap
0x18000a249  call    cs:__imp_HeapAlloc
0x18000a24f  mov     rbx, rax
0x18000a252  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000a259  test    rax, rax
0x18000a25c  jnz     short loc_18000A29C
0x18000a25e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000a264  jnz     short loc_18000A2A7
0x18000a266  lea     rcx, ModuleName; "ntdll.dll"
0x18000a26d  call    cs:__imp_GetModuleHandleW
0x18000a273  test    rax, rax
0x18000a276  jz      short loc_18000A289
0x18000a278  mov     rcx, rax
0x18000a27b  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x18000a280  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000a287  jmp     short loc_18000A290
0x18000a289  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000a290  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000a297  test    rax, rax
0x18000a29a  jz      short loc_18000A2A7
0x18000a29c  mov     rdx, rbx
0x18000a29f  mov     rcx, rsi
0x18000a2a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2a7  mov     rax, rbx
0x18000a2aa  mov     rbx, [rsp+28h+arg_0]
0x18000a2af  mov     rsi, [rsp+28h+arg_8]
0x18000a2b4  add     rsp, 20h
0x18000a2b8  pop     rdi
0x18000a2b9  retn
```
