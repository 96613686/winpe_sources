# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180004e28`
- end: `0x180004ec6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003734`
- `0x180003de0`
- `0x180005320`

## callees

- `0x180004e28`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004e86`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004e86`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004e71`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004e71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004e3c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004e3c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004e4d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004e4d`

## string_xrefs

- `0x180004e6a`: `ntdll.dll`

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
0x180004e28  mov     [rsp+arg_0], rbx
0x180004e2d  mov     [rsp+arg_8], rsi
0x180004e32  push    rdi
0x180004e33  sub     rsp, 20h
0x180004e37  mov     rbx, rdx
0x180004e3a  mov     edi, ecx
0x180004e3c  call    cs:__imp_GetProcessHeap
0x180004e42  mov     rsi, rax
0x180004e45  mov     r8, rbx; dwBytes
0x180004e48  mov     edx, edi; dwFlags
0x180004e4a  mov     rcx, rax; hHeap
0x180004e4d  call    cs:__imp_HeapAlloc
0x180004e53  mov     rbx, rax
0x180004e56  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180004e5d  test    rax, rax
0x180004e60  jnz     short loc_180004EA8
0x180004e62  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004e68  jnz     short loc_180004EB3
0x180004e6a  lea     rcx, ModuleName; "ntdll.dll"
0x180004e71  call    cs:__imp_GetModuleHandleW
0x180004e77  test    rax, rax
0x180004e7a  jz      short loc_180004E95
0x180004e7c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180004e83  mov     rcx, rax; hModule
0x180004e86  call    cs:__imp_GetProcAddress
0x180004e8c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180004e93  jmp     short loc_180004E9C
0x180004e95  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180004e9c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004ea3  test    rax, rax
0x180004ea6  jz      short loc_180004EB3
0x180004ea8  mov     rdx, rbx
0x180004eab  mov     rcx, rsi
0x180004eae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004eb3  mov     rax, rbx
0x180004eb6  mov     rbx, [rsp+28h+arg_0]
0x180004ebb  mov     rsi, [rsp+28h+arg_8]
0x180004ec0  add     rsp, 20h
0x180004ec4  pop     rdi
0x180004ec5  retn
```
