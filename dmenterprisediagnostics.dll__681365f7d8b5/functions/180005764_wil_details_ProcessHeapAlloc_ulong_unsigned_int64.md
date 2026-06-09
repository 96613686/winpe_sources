# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180005764`
- end: `0x18000580d`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `169`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000548c`
- `0x180005cac`
- `0x180006060`

## callees

- `0x180002a08`
- `0x180005764`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800057b9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800057b9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000578f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000578f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005778`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005778`

## string_xrefs

- `0x1800057b2`: `ntdll.dll`

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
0x180005764  mov     [rsp+arg_0], rbx
0x180005769  mov     [rsp+arg_8], rsi
0x18000576e  push    rdi
0x18000576f  sub     rsp, 20h
0x180005773  mov     rbx, rdx
0x180005776  mov     edi, ecx
0x180005778  call    cs:__imp_GetProcessHeap
0x18000577f  nop     dword ptr [rax+rax+00h]
0x180005784  mov     rsi, rax
0x180005787  mov     r8, rbx; dwBytes
0x18000578a  mov     edx, edi; dwFlags
0x18000578c  mov     rcx, rax; hHeap
0x18000578f  call    cs:__imp_HeapAlloc
0x180005796  nop     dword ptr [rax+rax+00h]
0x18000579b  mov     rbx, rax
0x18000579e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800057a5  test    rax, rax
0x1800057a8  jnz     short loc_1800057EE
0x1800057aa  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800057b0  jnz     short loc_1800057F9
0x1800057b2  lea     rcx, LibFileName; "ntdll.dll"
0x1800057b9  call    cs:__imp_GetModuleHandleW
0x1800057c0  nop     dword ptr [rax+rax+00h]
0x1800057c5  test    rax, rax
0x1800057c8  jz      short loc_1800057DB
0x1800057ca  mov     rcx, rax
0x1800057cd  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x1800057d2  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800057d9  jmp     short loc_1800057E2
0x1800057db  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800057e2  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800057e9  test    rax, rax
0x1800057ec  jz      short loc_1800057F9
0x1800057ee  mov     rdx, rbx
0x1800057f1  mov     rcx, rsi
0x1800057f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057f9  mov     rax, rbx
0x1800057fc  mov     rbx, [rsp+28h+arg_0]
0x180005801  mov     rsi, [rsp+28h+arg_8]
0x180005806  add     rsp, 20h
0x18000580a  pop     rdi
0x18000580b  retn
```
