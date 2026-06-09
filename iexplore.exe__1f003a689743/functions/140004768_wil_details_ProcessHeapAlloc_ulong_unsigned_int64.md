# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140004768`
- end: `0x1400047fe`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140004594`
- `0x140004a9c`
- `0x140004c14`

## callees

- `0x140002354`
- `0x140004768`
- `0x140006010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14000478d`
- `KERNEL32!HeapAlloc` at `0x14000478d`
- `KERNEL32!GetModuleHandleW` at `0x1400047b1`
- `KERNEL32!GetModuleHandleW` at `0x1400047b1`
- `KERNEL32!GetProcessHeap` at `0x14000477c`
- `KERNEL32!GetProcessHeap` at `0x14000477c`

## string_xrefs

- `0x1400047aa`: `ntdll.dll`

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
0x140004768  mov     [rsp+arg_0], rbx
0x14000476d  mov     [rsp+arg_8], rsi
0x140004772  push    rdi
0x140004773  sub     rsp, 20h
0x140004777  mov     rbx, rdx
0x14000477a  mov     edi, ecx
0x14000477c  call    cs:__imp_GetProcessHeap
0x140004782  mov     r8, rbx; dwBytes
0x140004785  mov     edx, edi; dwFlags
0x140004787  mov     rcx, rax; hHeap
0x14000478a  mov     rsi, rax
0x14000478d  call    cs:__imp_HeapAlloc
0x140004793  mov     rbx, rax
0x140004796  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000479d  test    rax, rax
0x1400047a0  jnz     short loc_1400047E0
0x1400047a2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400047a8  jnz     short loc_1400047EB
0x1400047aa  lea     rcx, aNtdllDll; "ntdll.dll"
0x1400047b1  call    cs:__imp_GetModuleHandleW
0x1400047b7  test    rax, rax
0x1400047ba  jz      short loc_1400047CD
0x1400047bc  mov     rcx, rax
0x1400047bf  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x1400047c4  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1400047cb  jmp     short loc_1400047D4
0x1400047cd  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400047d4  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400047db  test    rax, rax
0x1400047de  jz      short loc_1400047EB
0x1400047e0  mov     rdx, rbx
0x1400047e3  mov     rcx, rsi
0x1400047e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400047eb  mov     rsi, [rsp+28h+arg_8]
0x1400047f0  mov     rax, rbx
0x1400047f3  mov     rbx, [rsp+28h+arg_0]
0x1400047f8  add     rsp, 20h
0x1400047fc  pop     rdi
0x1400047fd  retn
```
