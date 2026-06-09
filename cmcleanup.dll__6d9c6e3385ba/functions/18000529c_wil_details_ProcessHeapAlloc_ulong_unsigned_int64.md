# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000529c`
- end: `0x18000533a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003518`
- `0x1800040c0`
- `0x180006960`

## callees

- `0x18000529c`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800052fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800052fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800052e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800052e5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800052c1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800052c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800052b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800052b0`

## string_xrefs

- `0x1800052de`: `ntdll.dll`

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
0x18000529c  mov     [rsp+arg_0], rbx
0x1800052a1  mov     [rsp+arg_8], rsi
0x1800052a6  push    rdi
0x1800052a7  sub     rsp, 20h
0x1800052ab  mov     rbx, rdx
0x1800052ae  mov     edi, ecx
0x1800052b0  call    cs:__imp_GetProcessHeap
0x1800052b6  mov     rsi, rax
0x1800052b9  mov     r8, rbx; dwBytes
0x1800052bc  mov     edx, edi; dwFlags
0x1800052be  mov     rcx, rax; hHeap
0x1800052c1  call    cs:__imp_HeapAlloc
0x1800052c7  mov     rbx, rax
0x1800052ca  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800052d1  test    rax, rax
0x1800052d4  jnz     short loc_18000531C
0x1800052d6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800052dc  jnz     short loc_180005327
0x1800052de  lea     rcx, ModuleName; "ntdll.dll"
0x1800052e5  call    cs:__imp_GetModuleHandleW
0x1800052eb  test    rax, rax
0x1800052ee  jz      short loc_180005309
0x1800052f0  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800052f7  mov     rcx, rax; hModule
0x1800052fa  call    cs:__imp_GetProcAddress
0x180005300  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005307  jmp     short loc_180005310
0x180005309  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005310  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005317  test    rax, rax
0x18000531a  jz      short loc_180005327
0x18000531c  mov     rdx, rbx
0x18000531f  mov     rcx, rsi
0x180005322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005327  mov     rax, rbx
0x18000532a  mov     rbx, [rsp+28h+arg_0]
0x18000532f  mov     rsi, [rsp+28h+arg_8]
0x180005334  add     rsp, 20h
0x180005338  pop     rdi
0x180005339  retn
```
