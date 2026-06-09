# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000816c`
- end: `0x180008202`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180003098`
- `0x180007c9c`
- `0x180007df0`
- `0x180008ca0`
- `0x180009124`

## callees

- `0x180004efc`
- `0x18000816c`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800081b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800081b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008180`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008180`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008191`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008191`

## string_xrefs

- `0x1800081ae`: `ntdll.dll`

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
0x18000816c  mov     [rsp+arg_0], rbx
0x180008171  mov     [rsp+arg_8], rsi
0x180008176  push    rdi
0x180008177  sub     rsp, 20h
0x18000817b  mov     rbx, rdx
0x18000817e  mov     edi, ecx
0x180008180  call    cs:__imp_GetProcessHeap
0x180008186  mov     rsi, rax
0x180008189  mov     r8, rbx; dwBytes
0x18000818c  mov     edx, edi; dwFlags
0x18000818e  mov     rcx, rax; hHeap
0x180008191  call    cs:__imp_HeapAlloc
0x180008197  mov     rbx, rax
0x18000819a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800081a1  test    rax, rax
0x1800081a4  jnz     short loc_1800081E4
0x1800081a6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800081ac  jnz     short loc_1800081EF
0x1800081ae  lea     rcx, ModuleName; "ntdll.dll"
0x1800081b5  call    cs:__imp_GetModuleHandleW
0x1800081bb  test    rax, rax
0x1800081be  jz      short loc_1800081D1
0x1800081c0  mov     rcx, rax
0x1800081c3  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x1800081c8  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800081cf  jmp     short loc_1800081D8
0x1800081d1  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800081d8  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800081df  test    rax, rax
0x1800081e2  jz      short loc_1800081EF
0x1800081e4  mov     rdx, rbx
0x1800081e7  mov     rcx, rsi
0x1800081ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081ef  mov     rax, rbx
0x1800081f2  mov     rbx, [rsp+28h+arg_0]
0x1800081f7  mov     rsi, [rsp+28h+arg_8]
0x1800081fc  add     rsp, 20h
0x180008200  pop     rdi
0x180008201  retn
```
