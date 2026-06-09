# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180023d3c`
- end: `0x180023de5`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `169`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180011530`
- `0x18001eed8`
- `0x180024750`

## callees

- `0x180020144`
- `0x180023d3c`
- `0x180045010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180023d67`
- `KERNEL32!HeapAlloc` at `0x180023d67`
- `KERNEL32!GetProcessHeap` at `0x180023d50`
- `KERNEL32!GetProcessHeap` at `0x180023d50`
- `KERNEL32!GetModuleHandleW` at `0x180023d91`
- `KERNEL32!GetModuleHandleW` at `0x180023d91`

## string_xrefs

- `0x180023d8a`: `ntdll.dll`

## pseudocode

```c
LPVOID __fastcall wil::details::ProcessHeapAlloc(DWORD dwFlags, SIZE_T dwBytes)
{
  HANDLE ProcessHeap; // rsi
  LPVOID v5; // rbx
  FARPROC ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z; // rax
  HMODULE ModuleHandleW; // rax

  ProcessHeap = GetProcessHeap();
  v5 = HeapAlloc(ProcessHeap, dwFlags, dwBytes);
  ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation;
  if ( `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation
    || !`wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation
    && ((ModuleHandleW = GetModuleHandleW(L"ntdll.dll")) == 0
      ? (ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation)
      : (FARPROC)(ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z = ___GetProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z(ModuleHandleW),
                  `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation = (__int64)ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z),
        `wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation = 1,
        ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z) )
  {
    ((void (__fastcall *)(HANDLE, LPVOID))ProcAddress_P6AJPEAX0__E_details_wil__YAP6AJPEAX0__EPEAUHINSTANCE____PEBD_Z)(
      ProcessHeap,
      v5);
  }
  return v5;
}

```

## disassembly

```asm
0x180023d3c  mov     [rsp+arg_0], rbx
0x180023d41  mov     [rsp+arg_8], rsi
0x180023d46  push    rdi
0x180023d47  sub     rsp, 20h
0x180023d4b  mov     rbx, rdx
0x180023d4e  mov     edi, ecx
0x180023d50  call    cs:__imp_GetProcessHeap
0x180023d57  nop     dword ptr [rax+rax+00h]
0x180023d5c  mov     r8, rbx; dwBytes
0x180023d5f  mov     edx, edi; dwFlags
0x180023d61  mov     rcx, rax; hHeap
0x180023d64  mov     rsi, rax
0x180023d67  call    cs:__imp_HeapAlloc
0x180023d6e  nop     dword ptr [rax+rax+00h]
0x180023d73  mov     rbx, rax
0x180023d76  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180023d7d  test    rax, rax
0x180023d80  jnz     short loc_180023DC6
0x180023d82  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180023d88  jnz     short loc_180023DD1
0x180023d8a  lea     rcx, ModuleName; "ntdll.dll"
0x180023d91  call    cs:__imp_GetModuleHandleW
0x180023d98  nop     dword ptr [rax+rax+00h]
0x180023d9d  test    rax, rax
0x180023da0  jz      short loc_180023DB3
0x180023da2  mov     rcx, rax
0x180023da5  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x180023daa  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180023db1  jmp     short loc_180023DBA
0x180023db3  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180023dba  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180023dc1  test    rax, rax
0x180023dc4  jz      short loc_180023DD1
0x180023dc6  mov     rdx, rbx
0x180023dc9  mov     rcx, rsi
0x180023dcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023dd1  mov     rsi, [rsp+28h+arg_8]
0x180023dd6  mov     rax, rbx
0x180023dd9  mov     rbx, [rsp+28h+arg_0]
0x180023dde  add     rsp, 20h
0x180023de2  pop     rdi
0x180023de3  retn
```
