# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180007828`
- end: `0x1800078c6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800060c8`
- `0x1800067b0`
- `0x180007b90`

## callees

- `0x180007828`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007886`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007886`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007871`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007871`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000783c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000783c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000784d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000784d`

## string_xrefs

- `0x18000786a`: `ntdll.dll`

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
0x180007828  mov     [rsp+arg_0], rbx
0x18000782d  mov     [rsp+arg_8], rsi
0x180007832  push    rdi
0x180007833  sub     rsp, 20h
0x180007837  mov     rbx, rdx
0x18000783a  mov     edi, ecx
0x18000783c  call    cs:__imp_GetProcessHeap
0x180007842  mov     rsi, rax
0x180007845  mov     r8, rbx; dwBytes
0x180007848  mov     edx, edi; dwFlags
0x18000784a  mov     rcx, rax; hHeap
0x18000784d  call    cs:__imp_HeapAlloc
0x180007853  mov     rbx, rax
0x180007856  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000785d  test    rax, rax
0x180007860  jnz     short loc_1800078A8
0x180007862  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007868  jnz     short loc_1800078B3
0x18000786a  lea     rcx, ModuleName; "ntdll.dll"
0x180007871  call    cs:__imp_GetModuleHandleW
0x180007877  test    rax, rax
0x18000787a  jz      short loc_180007895
0x18000787c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180007883  mov     rcx, rax; hModule
0x180007886  call    cs:__imp_GetProcAddress
0x18000788c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180007893  jmp     short loc_18000789C
0x180007895  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000789c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800078a3  test    rax, rax
0x1800078a6  jz      short loc_1800078B3
0x1800078a8  mov     rdx, rbx
0x1800078ab  mov     rcx, rsi
0x1800078ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078b3  mov     rax, rbx
0x1800078b6  mov     rbx, [rsp+28h+arg_0]
0x1800078bb  mov     rsi, [rsp+28h+arg_8]
0x1800078c0  add     rsp, 20h
0x1800078c4  pop     rdi
0x1800078c5  retn
```
