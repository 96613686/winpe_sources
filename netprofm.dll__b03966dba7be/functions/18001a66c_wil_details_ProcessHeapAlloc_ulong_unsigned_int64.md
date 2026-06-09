# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18001a66c`
- end: `0x18001a702`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180019fbc`
- `0x18001a128`
- `0x18001c078`
- `0x18001c500`
- `0x18001d5f0`

## callees

- `0x180014210`
- `0x18001a66c`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001a6b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001a6b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a680`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a680`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a691`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a691`

## string_xrefs

- `0x18001a6ae`: `ntdll.dll`

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
0x18001a66c  mov     [rsp+arg_0], rbx
0x18001a671  mov     [rsp+arg_8], rsi
0x18001a676  push    rdi
0x18001a677  sub     rsp, 20h
0x18001a67b  mov     rbx, rdx
0x18001a67e  mov     edi, ecx
0x18001a680  call    cs:__imp_GetProcessHeap
0x18001a686  mov     rsi, rax
0x18001a689  mov     r8, rbx; dwBytes
0x18001a68c  mov     edx, edi; dwFlags
0x18001a68e  mov     rcx, rax; hHeap
0x18001a691  call    cs:__imp_HeapAlloc
0x18001a697  mov     rbx, rax
0x18001a69a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18001a6a1  test    rax, rax
0x18001a6a4  jnz     short loc_18001A6E4
0x18001a6a6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001a6ac  jnz     short loc_18001A6EF
0x18001a6ae  lea     rcx, ModuleName; "ntdll.dll"
0x18001a6b5  call    cs:__imp_GetModuleHandleW
0x18001a6bb  test    rax, rax
0x18001a6be  jz      short loc_18001A6D1
0x18001a6c0  mov     rcx, rax
0x18001a6c3  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x18001a6c8  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18001a6cf  jmp     short loc_18001A6D8
0x18001a6d1  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18001a6d8  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001a6df  test    rax, rax
0x18001a6e2  jz      short loc_18001A6EF
0x18001a6e4  mov     rdx, rbx
0x18001a6e7  mov     rcx, rsi
0x18001a6ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a6ef  mov     rax, rbx
0x18001a6f2  mov     rbx, [rsp+28h+arg_0]
0x18001a6f7  mov     rsi, [rsp+28h+arg_8]
0x18001a6fc  add     rsp, 20h
0x18001a700  pop     rdi
0x18001a701  retn
```
