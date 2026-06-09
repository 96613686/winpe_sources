# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180028114`
- end: `0x1800281aa`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001a554`
- `0x18001a6a8`
- `0x180028e04`
- `0x180029068`
- `0x180029e4c`

## callees

- `0x180025af4`
- `0x180028114`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002815d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002815d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028128`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028128`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180028139`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180028139`

## string_xrefs

- `0x180028156`: `ntdll.dll`

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
0x180028114  mov     [rsp+arg_0], rbx
0x180028119  mov     [rsp+arg_8], rsi
0x18002811e  push    rdi
0x18002811f  sub     rsp, 20h
0x180028123  mov     rbx, rdx
0x180028126  mov     edi, ecx
0x180028128  call    cs:__imp_GetProcessHeap
0x18002812e  mov     r8, rbx; dwBytes
0x180028131  mov     edx, edi; dwFlags
0x180028133  mov     rcx, rax; hHeap
0x180028136  mov     rsi, rax
0x180028139  call    cs:__imp_HeapAlloc
0x18002813f  mov     rbx, rax
0x180028142  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180028149  test    rax, rax
0x18002814c  jnz     short loc_18002818C
0x18002814e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180028154  jnz     short loc_180028197
0x180028156  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18002815d  call    cs:__imp_GetModuleHandleW
0x180028163  test    rax, rax
0x180028166  jz      short loc_180028179
0x180028168  mov     rcx, rax
0x18002816b  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180028170  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180028177  jmp     short loc_180028180
0x180028179  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180028180  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180028187  test    rax, rax
0x18002818a  jz      short loc_180028197
0x18002818c  mov     rdx, rbx
0x18002818f  mov     rcx, rsi
0x180028192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028197  mov     rsi, [rsp+28h+arg_8]
0x18002819c  mov     rax, rbx
0x18002819f  mov     rbx, [rsp+28h+arg_0]
0x1800281a4  add     rsp, 20h
0x1800281a8  pop     rdi
0x1800281a9  retn
```
