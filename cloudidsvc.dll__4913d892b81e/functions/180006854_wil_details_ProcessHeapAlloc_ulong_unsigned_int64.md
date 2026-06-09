# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180006854`
- end: `0x1800068f2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800059fc`
- `0x1800065a0`
- `0x180007038`
- `0x1800073d0`

## callees

- `0x180006854`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800068b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800068b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000689d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000689d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006879`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006879`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006868`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006868`

## string_xrefs

- `0x180006896`: `ntdll.dll`

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
0x180006854  mov     [rsp+arg_0], rbx
0x180006859  mov     [rsp+arg_8], rsi
0x18000685e  push    rdi
0x18000685f  sub     rsp, 20h
0x180006863  mov     rbx, rdx
0x180006866  mov     edi, ecx
0x180006868  call    cs:__imp_GetProcessHeap
0x18000686e  mov     rsi, rax
0x180006871  mov     r8, rbx; dwBytes
0x180006874  mov     edx, edi; dwFlags
0x180006876  mov     rcx, rax; hHeap
0x180006879  call    cs:__imp_HeapAlloc
0x18000687f  mov     rbx, rax
0x180006882  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180006889  test    rax, rax
0x18000688c  jnz     short loc_1800068D4
0x18000688e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006894  jnz     short loc_1800068DF
0x180006896  lea     rcx, ModuleName; "ntdll.dll"
0x18000689d  call    cs:__imp_GetModuleHandleW
0x1800068a3  test    rax, rax
0x1800068a6  jz      short loc_1800068C1
0x1800068a8  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x1800068af  mov     rcx, rax; hModule
0x1800068b2  call    cs:__imp_GetProcAddress
0x1800068b8  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800068bf  jmp     short loc_1800068C8
0x1800068c1  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800068c8  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800068cf  test    rax, rax
0x1800068d2  jz      short loc_1800068DF
0x1800068d4  mov     rdx, rbx
0x1800068d7  mov     rcx, rsi
0x1800068da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068df  mov     rax, rbx
0x1800068e2  mov     rbx, [rsp+28h+arg_0]
0x1800068e7  mov     rsi, [rsp+28h+arg_8]
0x1800068ec  add     rsp, 20h
0x1800068f0  pop     rdi
0x1800068f1  retn
```
