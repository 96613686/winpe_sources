# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180003bb8`
- end: `0x180003c56`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800024d4`
- `0x180002b70`
- `0x180003f00`

## callees

- `0x180003bb8`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003c16`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003c16`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003c01`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003c01`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003bcc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003bcc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003bdd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003bdd`

## string_xrefs

- `0x180003bfa`: `ntdll.dll`

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
0x180003bb8  mov     [rsp+arg_0], rbx
0x180003bbd  mov     [rsp+arg_8], rsi
0x180003bc2  push    rdi
0x180003bc3  sub     rsp, 20h
0x180003bc7  mov     rbx, rdx
0x180003bca  mov     edi, ecx
0x180003bcc  call    cs:__imp_GetProcessHeap
0x180003bd2  mov     r8, rbx; dwBytes
0x180003bd5  mov     edx, edi; dwFlags
0x180003bd7  mov     rcx, rax; hHeap
0x180003bda  mov     rsi, rax
0x180003bdd  call    cs:__imp_HeapAlloc
0x180003be3  mov     rbx, rax
0x180003be6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180003bed  test    rax, rax
0x180003bf0  jnz     short loc_180003C38
0x180003bf2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180003bf8  jnz     short loc_180003C43
0x180003bfa  lea     rcx, ModuleName; "ntdll.dll"
0x180003c01  call    cs:__imp_GetModuleHandleW
0x180003c07  test    rax, rax
0x180003c0a  jz      short loc_180003C25
0x180003c0c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180003c13  mov     rcx, rax; hModule
0x180003c16  call    cs:__imp_GetProcAddress
0x180003c1c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180003c23  jmp     short loc_180003C2C
0x180003c25  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180003c2c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180003c33  test    rax, rax
0x180003c36  jz      short loc_180003C43
0x180003c38  mov     rdx, rbx
0x180003c3b  mov     rcx, rsi
0x180003c3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c43  mov     rsi, [rsp+28h+arg_8]
0x180003c48  mov     rax, rbx
0x180003c4b  mov     rbx, [rsp+28h+arg_0]
0x180003c50  add     rsp, 20h
0x180003c54  pop     rdi
0x180003c55  retn
```
