# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000a240`
- end: `0x18000a2d6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180009b7c`
- `0x180009d44`
- `0x18000b1a0`
- `0x18000b630`
- `0x18000c874`

## callees

- `0x18000684c`
- `0x18000a240`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a289`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a289`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a265`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a265`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a254`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a254`

## string_xrefs

- `0x18000a282`: `ntdll.dll`

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
0x18000a240  mov     [rsp+arg_0], rbx
0x18000a245  mov     [rsp+arg_8], rsi
0x18000a24a  push    rdi
0x18000a24b  sub     rsp, 20h
0x18000a24f  mov     rbx, rdx
0x18000a252  mov     edi, ecx
0x18000a254  call    cs:__imp_GetProcessHeap
0x18000a25a  mov     rsi, rax
0x18000a25d  mov     r8, rbx; dwBytes
0x18000a260  mov     edx, edi; dwFlags
0x18000a262  mov     rcx, rax; hHeap
0x18000a265  call    cs:__imp_HeapAlloc
0x18000a26b  mov     rbx, rax
0x18000a26e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000a275  test    rax, rax
0x18000a278  jnz     short loc_18000A2B8
0x18000a27a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000a280  jnz     short loc_18000A2C3
0x18000a282  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000a289  call    cs:__imp_GetModuleHandleW
0x18000a28f  test    rax, rax
0x18000a292  jz      short loc_18000A2A5
0x18000a294  mov     rcx, rax
0x18000a297  call    ??$GetProcAddress@P6AJPEAX0@_E@details@wil@@YAP6AJPEAX0@_EPEAUHINSTANCE__@@PEBD@Z
0x18000a29c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000a2a3  jmp     short loc_18000A2AC
0x18000a2a5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000a2ac  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000a2b3  test    rax, rax
0x18000a2b6  jz      short loc_18000A2C3
0x18000a2b8  mov     rdx, rbx
0x18000a2bb  mov     rcx, rsi
0x18000a2be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2c3  mov     rax, rbx
0x18000a2c6  mov     rbx, [rsp+28h+arg_0]
0x18000a2cb  mov     rsi, [rsp+28h+arg_8]
0x18000a2d0  add     rsp, 20h
0x18000a2d4  pop     rdi
0x18000a2d5  retn
```
