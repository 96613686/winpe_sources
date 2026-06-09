# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180012ef4`
- end: `0x180012f92`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000dc48`
- `0x1800129bc`
- `0x180012ae0`
- `0x180013d54`
- `0x180013fb8`

## callees

- `0x180012ef4`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012f19`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012f19`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012f08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012f08`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012f52`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012f52`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012f3d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012f3d`

## string_xrefs

- `0x180012f36`: `ntdll.dll`

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
0x180012ef4  mov     [rsp+arg_0], rbx
0x180012ef9  mov     [rsp+arg_8], rsi
0x180012efe  push    rdi
0x180012eff  sub     rsp, 20h
0x180012f03  mov     rbx, rdx
0x180012f06  mov     edi, ecx
0x180012f08  call    cs:__imp_GetProcessHeap
0x180012f0e  mov     r8, rbx; dwBytes
0x180012f11  mov     edx, edi; dwFlags
0x180012f13  mov     rcx, rax; hHeap
0x180012f16  mov     rsi, rax
0x180012f19  call    cs:__imp_HeapAlloc
0x180012f1f  mov     rbx, rax
0x180012f22  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180012f29  test    rax, rax
0x180012f2c  jnz     short loc_180012F74
0x180012f2e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180012f34  jnz     short loc_180012F7F
0x180012f36  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180012f3d  call    cs:__imp_GetModuleHandleW
0x180012f43  test    rax, rax
0x180012f46  jz      short loc_180012F61
0x180012f48  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x180012f4f  mov     rcx, rax; hModule
0x180012f52  call    cs:__imp_GetProcAddress
0x180012f58  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180012f5f  jmp     short loc_180012F68
0x180012f61  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180012f68  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180012f6f  test    rax, rax
0x180012f72  jz      short loc_180012F7F
0x180012f74  mov     rdx, rbx
0x180012f77  mov     rcx, rsi
0x180012f7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f7f  mov     rsi, [rsp+28h+arg_8]
0x180012f84  mov     rax, rbx
0x180012f87  mov     rbx, [rsp+28h+arg_0]
0x180012f8c  add     rsp, 20h
0x180012f90  pop     rdi
0x180012f91  retn
```
