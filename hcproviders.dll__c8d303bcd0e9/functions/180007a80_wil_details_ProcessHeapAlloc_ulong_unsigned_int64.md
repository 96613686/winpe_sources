# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180007a80`
- end: `0x180007b29`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `169`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800077f0`
- `0x180007cb0`
- `0x180007e3c`

## callees

- `0x180005c94`
- `0x180007a80`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007ad5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007ad5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a94`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a94`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007aab`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007aab`

## string_xrefs

- `0x180007ace`: `ntdll.dll`

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
0x180007a80  mov     [rsp+arg_0], rbx
0x180007a85  mov     [rsp+arg_8], rsi
0x180007a8a  push    rdi
0x180007a8b  sub     rsp, 20h
0x180007a8f  mov     rbx, rdx
0x180007a92  mov     edi, ecx
0x180007a94  call    cs:__imp_GetProcessHeap
0x180007a9b  nop     dword ptr [rax+rax+00h]
0x180007aa0  mov     r8, rbx; dwBytes
0x180007aa3  mov     edx, edi; dwFlags
0x180007aa5  mov     rcx, rax; hHeap
0x180007aa8  mov     rsi, rax
0x180007aab  call    cs:__imp_HeapAlloc
0x180007ab2  nop     dword ptr [rax+rax+00h]
0x180007ab7  mov     rbx, rax
0x180007aba  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007ac1  test    rax, rax
0x180007ac4  jnz     short loc_180007B0A
0x180007ac6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007acc  jnz     short loc_180007B15
0x180007ace  lea     rcx, ModuleName; "ntdll.dll"
0x180007ad5  call    cs:__imp_GetModuleHandleW
0x180007adc  nop     dword ptr [rax+rax+00h]
0x180007ae1  test    rax, rax
0x180007ae4  jz      short loc_180007AF7
0x180007ae6  mov     rcx, rax
0x180007ae9  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180007aee  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180007af5  jmp     short loc_180007AFE
0x180007af7  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007afe  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007b05  test    rax, rax
0x180007b08  jz      short loc_180007B15
0x180007b0a  mov     rdx, rbx
0x180007b0d  mov     rcx, rsi
0x180007b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b15  mov     rsi, [rsp+28h+arg_8]
0x180007b1a  mov     rax, rbx
0x180007b1d  mov     rbx, [rsp+28h+arg_0]
0x180007b22  add     rsp, 20h
0x180007b26  pop     rdi
0x180007b27  retn
```
