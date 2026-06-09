# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000c0e0`
- end: `0x18000c176`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000be40`
- `0x18000c510`
- `0x18000c8a8`
- `0x1800109a4`
- `0x1800136a4`

## callees

- `0x180009e90`
- `0x18000c0e0`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c129`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c129`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c105`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c105`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c0f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c0f4`

## string_xrefs

- `0x18000c122`: `ntdll.dll`

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
0x18000c0e0  mov     [rsp+arg_0], rbx
0x18000c0e5  mov     [rsp+arg_8], rsi
0x18000c0ea  push    rdi
0x18000c0eb  sub     rsp, 20h
0x18000c0ef  mov     rbx, rdx
0x18000c0f2  mov     edi, ecx
0x18000c0f4  call    cs:__imp_GetProcessHeap
0x18000c0fa  mov     rsi, rax
0x18000c0fd  mov     r8, rbx; dwBytes
0x18000c100  mov     edx, edi; dwFlags
0x18000c102  mov     rcx, rax; hHeap
0x18000c105  call    cs:__imp_HeapAlloc
0x18000c10b  mov     rbx, rax
0x18000c10e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000c115  test    rax, rax
0x18000c118  jnz     short loc_18000C158
0x18000c11a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000c120  jnz     short loc_18000C163
0x18000c122  lea     rcx, ModuleName; "ntdll.dll"
0x18000c129  call    cs:__imp_GetModuleHandleW
0x18000c12f  test    rax, rax
0x18000c132  jz      short loc_18000C145
0x18000c134  mov     rcx, rax
0x18000c137  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x18000c13c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000c143  jmp     short loc_18000C14C
0x18000c145  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000c14c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000c153  test    rax, rax
0x18000c156  jz      short loc_18000C163
0x18000c158  mov     rdx, rbx
0x18000c15b  mov     rcx, rsi
0x18000c15e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c163  mov     rax, rbx
0x18000c166  mov     rbx, [rsp+28h+arg_0]
0x18000c16b  mov     rsi, [rsp+28h+arg_8]
0x18000c170  add     rsp, 20h
0x18000c174  pop     rdi
0x18000c175  retn
```
