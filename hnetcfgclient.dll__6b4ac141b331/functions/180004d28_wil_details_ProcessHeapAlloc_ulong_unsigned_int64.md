# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180004d28`
- end: `0x180004dc6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004ab4`
- `0x1800051ac`
- `0x180005544`

## callees

- `0x180004d28`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004d71`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004d71`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004d86`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004d86`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004d4d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004d4d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004d3c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004d3c`

## string_xrefs

- `0x180004d6a`: `ntdll.dll`

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
0x180004d28  mov     [rsp+arg_0], rbx
0x180004d2d  mov     [rsp+arg_8], rsi
0x180004d32  push    rdi
0x180004d33  sub     rsp, 20h
0x180004d37  mov     rbx, rdx
0x180004d3a  mov     edi, ecx
0x180004d3c  call    cs:__imp_GetProcessHeap
0x180004d42  mov     rsi, rax
0x180004d45  mov     r8, rbx; dwBytes
0x180004d48  mov     edx, edi; dwFlags
0x180004d4a  mov     rcx, rax; hHeap
0x180004d4d  call    cs:__imp_HeapAlloc
0x180004d53  mov     rbx, rax
0x180004d56  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180004d5d  test    rax, rax
0x180004d60  jnz     short loc_180004DA8
0x180004d62  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004d68  jnz     short loc_180004DB3
0x180004d6a  lea     rcx, ModuleName; "ntdll.dll"
0x180004d71  call    cs:__imp_GetModuleHandleW
0x180004d77  test    rax, rax
0x180004d7a  jz      short loc_180004D95
0x180004d7c  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x180004d83  mov     rcx, rax; hModule
0x180004d86  call    cs:__imp_GetProcAddress
0x180004d8c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180004d93  jmp     short loc_180004D9C
0x180004d95  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180004d9c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004da3  test    rax, rax
0x180004da6  jz      short loc_180004DB3
0x180004da8  mov     rdx, rbx
0x180004dab  mov     rcx, rsi
0x180004dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004db3  mov     rax, rbx
0x180004db6  mov     rbx, [rsp+28h+arg_0]
0x180004dbb  mov     rsi, [rsp+28h+arg_8]
0x180004dc0  add     rsp, 20h
0x180004dc4  pop     rdi
0x180004dc5  retn
```
