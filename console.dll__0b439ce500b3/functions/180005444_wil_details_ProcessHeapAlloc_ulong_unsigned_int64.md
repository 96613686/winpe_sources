# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180005444`
- end: `0x1800054ed`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `169`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180005178`
- `0x180005954`
- `0x180005d08`

## callees

- `0x180003110`
- `0x180005444`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005499`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005499`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000546f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000546f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005458`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005458`

## string_xrefs

- `0x180005492`: `ntdll.dll`

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
0x180005444  mov     [rsp+arg_0], rbx
0x180005449  mov     [rsp+arg_8], rsi
0x18000544e  push    rdi
0x18000544f  sub     rsp, 20h
0x180005453  mov     rbx, rdx
0x180005456  mov     edi, ecx
0x180005458  call    cs:__imp_GetProcessHeap
0x18000545f  nop     dword ptr [rax+rax+00h]
0x180005464  mov     rsi, rax
0x180005467  mov     r8, rbx; dwBytes
0x18000546a  mov     edx, edi; dwFlags
0x18000546c  mov     rcx, rax; hHeap
0x18000546f  call    cs:__imp_HeapAlloc
0x180005476  nop     dword ptr [rax+rax+00h]
0x18000547b  mov     rbx, rax
0x18000547e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005485  test    rax, rax
0x180005488  jnz     short loc_1800054CE
0x18000548a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005490  jnz     short loc_1800054D9
0x180005492  lea     rcx, aNtdllDll; "ntdll.dll"
0x180005499  call    cs:__imp_GetModuleHandleW
0x1800054a0  nop     dword ptr [rax+rax+00h]
0x1800054a5  test    rax, rax
0x1800054a8  jz      short loc_1800054BB
0x1800054aa  mov     rcx, rax
0x1800054ad  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x1800054b2  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800054b9  jmp     short loc_1800054C2
0x1800054bb  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800054c2  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800054c9  test    rax, rax
0x1800054cc  jz      short loc_1800054D9
0x1800054ce  mov     rdx, rbx
0x1800054d1  mov     rcx, rsi
0x1800054d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054d9  mov     rax, rbx
0x1800054dc  mov     rbx, [rsp+28h+arg_0]
0x1800054e1  mov     rsi, [rsp+28h+arg_8]
0x1800054e6  add     rsp, 20h
0x1800054ea  pop     rdi
0x1800054eb  retn
```
