# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18001aeb4`
- end: `0x18001af4a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001a898`
- `0x18001aa2c`
- `0x18001bc80`
- `0x18001c104`
- `0x18001d614`

## callees

- `0x180015a80`
- `0x18001aeb4`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001aefd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001aefd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001aed9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001aed9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001aec8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001aec8`

## string_xrefs

- `0x18001aef6`: `ntdll.dll`

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
0x18001aeb4  mov     [rsp+arg_0], rbx
0x18001aeb9  mov     [rsp+arg_8], rsi
0x18001aebe  push    rdi
0x18001aebf  sub     rsp, 20h
0x18001aec3  mov     rbx, rdx
0x18001aec6  mov     edi, ecx
0x18001aec8  call    cs:__imp_GetProcessHeap
0x18001aece  mov     rsi, rax
0x18001aed1  mov     r8, rbx; dwBytes
0x18001aed4  mov     edx, edi; dwFlags
0x18001aed6  mov     rcx, rax; hHeap
0x18001aed9  call    cs:__imp_HeapAlloc
0x18001aedf  mov     rbx, rax
0x18001aee2  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18001aee9  test    rax, rax
0x18001aeec  jnz     short loc_18001AF2C
0x18001aeee  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001aef4  jnz     short loc_18001AF37
0x18001aef6  lea     rcx, ModuleName; "ntdll.dll"
0x18001aefd  call    cs:__imp_GetModuleHandleW
0x18001af03  test    rax, rax
0x18001af06  jz      short loc_18001AF19
0x18001af08  mov     rcx, rax
0x18001af0b  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x18001af10  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18001af17  jmp     short loc_18001AF20
0x18001af19  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18001af20  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001af27  test    rax, rax
0x18001af2a  jz      short loc_18001AF37
0x18001af2c  mov     rdx, rbx
0x18001af2f  mov     rcx, rsi
0x18001af32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af37  mov     rax, rbx
0x18001af3a  mov     rbx, [rsp+28h+arg_0]
0x18001af3f  mov     rsi, [rsp+28h+arg_8]
0x18001af44  add     rsp, 20h
0x18001af48  pop     rdi
0x18001af49  retn
```
