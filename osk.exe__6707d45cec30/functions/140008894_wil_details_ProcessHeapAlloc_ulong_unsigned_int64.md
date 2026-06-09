# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140008894`
- end: `0x14000892a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000690c`
- `0x1400077fc`
- `0x140007960`
- `0x140009710`
- `0x140009bc8`
- `0x14000c7e0`

## callees

- `0x140003904`
- `0x140008894`
- `0x140027010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1400088b9`
- `KERNEL32!HeapAlloc` at `0x1400088b9`
- `KERNEL32!GetProcessHeap` at `0x1400088a8`
- `KERNEL32!GetProcessHeap` at `0x1400088a8`
- `KERNEL32!GetModuleHandleW` at `0x1400088dd`
- `KERNEL32!GetModuleHandleW` at `0x1400088dd`

## string_xrefs

- `0x1400088d6`: `ntdll.dll`

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
0x140008894  mov     [rsp+arg_0], rbx
0x140008899  mov     [rsp+arg_8], rsi
0x14000889e  push    rdi
0x14000889f  sub     rsp, 20h
0x1400088a3  mov     rbx, rdx
0x1400088a6  mov     edi, ecx
0x1400088a8  call    cs:__imp_GetProcessHeap
0x1400088ae  mov     rsi, rax
0x1400088b1  mov     r8, rbx; dwBytes
0x1400088b4  mov     edx, edi; dwFlags
0x1400088b6  mov     rcx, rax; hHeap
0x1400088b9  call    cs:__imp_HeapAlloc
0x1400088bf  mov     rbx, rax
0x1400088c2  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400088c9  test    rax, rax
0x1400088cc  jnz     short loc_14000890C
0x1400088ce  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400088d4  jnz     short loc_140008917
0x1400088d6  lea     rcx, ModuleName; "ntdll.dll"
0x1400088dd  call    cs:__imp_GetModuleHandleW
0x1400088e3  test    rax, rax
0x1400088e6  jz      short loc_1400088F9
0x1400088e8  mov     rcx, rax
0x1400088eb  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x1400088f0  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1400088f7  jmp     short loc_140008900
0x1400088f9  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140008900  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140008907  test    rax, rax
0x14000890a  jz      short loc_140008917
0x14000890c  mov     rdx, rbx
0x14000890f  mov     rcx, rsi
0x140008912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008917  mov     rax, rbx
0x14000891a  mov     rbx, [rsp+28h+arg_0]
0x14000891f  mov     rsi, [rsp+28h+arg_8]
0x140008924  add     rsp, 20h
0x140008928  pop     rdi
0x140008929  retn
```
