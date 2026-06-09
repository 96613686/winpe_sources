# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140005530`
- end: `0x1400055ce`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140003d68`
- `0x140004430`
- `0x140005ab4`

## callees

- `0x140005530`
- `0x140008010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005579`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005579`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000558e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000558e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005544`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005544`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140005555`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140005555`

## string_xrefs

- `0x140005572`: `ntdll.dll`

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
0x140005530  mov     [rsp+arg_0], rbx
0x140005535  mov     [rsp+arg_8], rsi
0x14000553a  push    rdi
0x14000553b  sub     rsp, 20h
0x14000553f  mov     rbx, rdx
0x140005542  mov     edi, ecx
0x140005544  call    cs:__imp_GetProcessHeap
0x14000554a  mov     rsi, rax
0x14000554d  mov     r8, rbx; dwBytes
0x140005550  mov     edx, edi; dwFlags
0x140005552  mov     rcx, rax; hHeap
0x140005555  call    cs:__imp_HeapAlloc
0x14000555b  mov     rbx, rax
0x14000555e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140005565  test    rax, rax
0x140005568  jnz     short loc_1400055B0
0x14000556a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140005570  jnz     short loc_1400055BB
0x140005572  lea     rcx, ModuleName; "ntdll.dll"
0x140005579  call    cs:__imp_GetModuleHandleW
0x14000557f  test    rax, rax
0x140005582  jz      short loc_14000559D
0x140005584  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x14000558b  mov     rcx, rax; hModule
0x14000558e  call    cs:__imp_GetProcAddress
0x140005594  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x14000559b  jmp     short loc_1400055A4
0x14000559d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400055a4  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400055ab  test    rax, rax
0x1400055ae  jz      short loc_1400055BB
0x1400055b0  mov     rdx, rbx
0x1400055b3  mov     rcx, rsi
0x1400055b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400055bb  mov     rax, rbx
0x1400055be  mov     rbx, [rsp+28h+arg_0]
0x1400055c3  mov     rsi, [rsp+28h+arg_8]
0x1400055c8  add     rsp, 20h
0x1400055cc  pop     rdi
0x1400055cd  retn
```
