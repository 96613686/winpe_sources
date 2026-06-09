# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x14000f32c`
- end: `0x14000f3c2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000d7c0`
- `0x14000ec00`
- `0x140012700`
- `0x140013070`
- `0x140013408`
- `0x140016968`

## callees

- `0x14000f32c`
- `0x140010fcc`
- `0x14001f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000f375`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000f375`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000f351`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000f351`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f340`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f340`

## string_xrefs

- `0x14000f36e`: `ntdll.dll`

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
0x14000f32c  mov     [rsp+arg_0], rbx
0x14000f331  mov     [rsp+arg_8], rsi
0x14000f336  push    rdi
0x14000f337  sub     rsp, 20h
0x14000f33b  mov     rbx, rdx
0x14000f33e  mov     edi, ecx
0x14000f340  call    cs:__imp_GetProcessHeap
0x14000f346  mov     rsi, rax
0x14000f349  mov     r8, rbx; dwBytes
0x14000f34c  mov     edx, edi; dwFlags
0x14000f34e  mov     rcx, rax; hHeap
0x14000f351  call    cs:__imp_HeapAlloc
0x14000f357  mov     rbx, rax
0x14000f35a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000f361  test    rax, rax
0x14000f364  jnz     short loc_14000F3A4
0x14000f366  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000f36c  jnz     short loc_14000F3AF
0x14000f36e  lea     rcx, ModuleName; "ntdll.dll"
0x14000f375  call    cs:__imp_GetModuleHandleW
0x14000f37b  test    rax, rax
0x14000f37e  jz      short loc_14000F391
0x14000f380  mov     rcx, rax
0x14000f383  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x14000f388  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x14000f38f  jmp     short loc_14000F398
0x14000f391  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000f398  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000f39f  test    rax, rax
0x14000f3a2  jz      short loc_14000F3AF
0x14000f3a4  mov     rdx, rbx
0x14000f3a7  mov     rcx, rsi
0x14000f3aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f3af  mov     rax, rbx
0x14000f3b2  mov     rbx, [rsp+28h+arg_0]
0x14000f3b7  mov     rsi, [rsp+28h+arg_8]
0x14000f3bc  add     rsp, 20h
0x14000f3c0  pop     rdi
0x14000f3c1  retn
```
