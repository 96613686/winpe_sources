# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180005ad8`
- end: `0x180005b6e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180004efc`
- `0x1800058d8`
- `0x180005d70`
- `0x180006108`
- `0x180019f54`
- `0x18001d5d4`

## callees

- `0x1800039dc`
- `0x180005ad8`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005b21`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005b21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005aec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005aec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005afd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005afd`

## string_xrefs

- `0x180005b1a`: `ntdll.dll`

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
0x180005ad8  mov     [rsp+arg_0], rbx
0x180005add  mov     [rsp+arg_8], rsi
0x180005ae2  push    rdi
0x180005ae3  sub     rsp, 20h
0x180005ae7  mov     rbx, rdx
0x180005aea  mov     edi, ecx
0x180005aec  call    cs:__imp_GetProcessHeap
0x180005af2  mov     rsi, rax
0x180005af5  mov     r8, rbx; dwBytes
0x180005af8  mov     edx, edi; dwFlags
0x180005afa  mov     rcx, rax; hHeap
0x180005afd  call    cs:__imp_HeapAlloc
0x180005b03  mov     rbx, rax
0x180005b06  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005b0d  test    rax, rax
0x180005b10  jnz     short loc_180005B50
0x180005b12  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005b18  jnz     short loc_180005B5B
0x180005b1a  lea     rcx, ModuleName; "ntdll.dll"
0x180005b21  call    cs:__imp_GetModuleHandleW
0x180005b27  test    rax, rax
0x180005b2a  jz      short loc_180005B3D
0x180005b2c  mov     rcx, rax
0x180005b2f  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180005b34  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005b3b  jmp     short loc_180005B44
0x180005b3d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005b44  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005b4b  test    rax, rax
0x180005b4e  jz      short loc_180005B5B
0x180005b50  mov     rdx, rbx
0x180005b53  mov     rcx, rsi
0x180005b56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b5b  mov     rax, rbx
0x180005b5e  mov     rbx, [rsp+28h+arg_0]
0x180005b63  mov     rsi, [rsp+28h+arg_8]
0x180005b68  add     rsp, 20h
0x180005b6c  pop     rdi
0x180005b6d  retn
```
