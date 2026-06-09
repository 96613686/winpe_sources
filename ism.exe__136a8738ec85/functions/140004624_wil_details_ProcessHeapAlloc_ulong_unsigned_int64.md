# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140004624`
- end: `0x1400046c2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140002e78`
- `0x140003530`
- `0x140004a04`

## callees

- `0x140004624`
- `0x140006010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140004649`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140004649`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004638`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004638`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004682`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004682`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000466d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000466d`

## string_xrefs

- `0x140004666`: `ntdll.dll`

## pseudocode

```c
LPVOID __fastcall wil::details::ProcessHeapAlloc(DWORD dwFlags, SIZE_T dwBytes)
{
  HANDLE ProcessHeap; // rsi
  LPVOID v5; // rbx
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax

  ProcessHeap = GetProcessHeap();
  v5 = HeapAlloc(ProcessHeap, dwFlags, dwBytes);
  ProcAddress = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation;
  if ( `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation
    || !`wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation
    && ((ModuleHandleW = GetModuleHandleW(L"ntdll.dll")) == 0
      ? (ProcAddress = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation)
      : (FARPROC)(ProcAddress = GetProcAddress(ModuleHandleW, "RtlDisownModuleHeapAllocation"),
                  `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation = (__int64)ProcAddress),
        `wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation = 1,
        ProcAddress) )
  {
    ((void (__fastcall *)(HANDLE, LPVOID))ProcAddress)(ProcessHeap, v5);
  }
  return v5;
}

```

## disassembly

```asm
0x140004624  mov     [rsp+arg_0], rbx
0x140004629  mov     [rsp+arg_8], rsi
0x14000462e  push    rdi
0x14000462f  sub     rsp, 20h
0x140004633  mov     rbx, rdx
0x140004636  mov     edi, ecx
0x140004638  call    cs:__imp_GetProcessHeap
0x14000463e  mov     rsi, rax
0x140004641  mov     r8, rbx; dwBytes
0x140004644  mov     edx, edi; dwFlags
0x140004646  mov     rcx, rax; hHeap
0x140004649  call    cs:__imp_HeapAlloc
0x14000464f  mov     rbx, rax
0x140004652  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140004659  test    rax, rax
0x14000465c  jnz     short loc_1400046A4
0x14000465e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140004664  jnz     short loc_1400046AF
0x140004666  lea     rcx, ModuleName; "ntdll.dll"
0x14000466d  call    cs:__imp_GetModuleHandleW
0x140004673  test    rax, rax
0x140004676  jz      short loc_140004691
0x140004678  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x14000467f  mov     rcx, rax; hModule
0x140004682  call    cs:__imp_GetProcAddress
0x140004688  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x14000468f  jmp     short loc_140004698
0x140004691  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140004698  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000469f  test    rax, rax
0x1400046a2  jz      short loc_1400046AF
0x1400046a4  mov     rdx, rbx
0x1400046a7  mov     rcx, rsi
0x1400046aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400046af  mov     rax, rbx
0x1400046b2  mov     rbx, [rsp+28h+arg_0]
0x1400046b7  mov     rsi, [rsp+28h+arg_8]
0x1400046bc  add     rsp, 20h
0x1400046c0  pop     rdi
0x1400046c1  retn
```
