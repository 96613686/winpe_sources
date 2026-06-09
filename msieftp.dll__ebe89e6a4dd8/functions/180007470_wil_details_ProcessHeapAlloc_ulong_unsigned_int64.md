# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180007470`
- end: `0x18000750e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000443c`
- `0x1800047e0`
- `0x180005e40`
- `0x180009268`
- `0x18000a570`

## callees

- `0x180007470`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800074b9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800074b9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800074ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800074ce`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007495`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007495`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007484`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007484`

## string_xrefs

- `0x1800074b2`: `ntdll.dll`

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
0x180007470  mov     [rsp+arg_0], rbx
0x180007475  mov     [rsp+arg_8], rsi
0x18000747a  push    rdi
0x18000747b  sub     rsp, 20h
0x18000747f  mov     rbx, rdx
0x180007482  mov     edi, ecx
0x180007484  call    cs:__imp_GetProcessHeap
0x18000748a  mov     r8, rbx; dwBytes
0x18000748d  mov     edx, edi; dwFlags
0x18000748f  mov     rcx, rax; hHeap
0x180007492  mov     rsi, rax
0x180007495  call    cs:__imp_HeapAlloc
0x18000749b  mov     rbx, rax
0x18000749e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800074a5  test    rax, rax
0x1800074a8  jnz     short loc_1800074F0
0x1800074aa  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800074b0  jnz     short loc_1800074FB
0x1800074b2  lea     rcx, ModuleName; "ntdll.dll"
0x1800074b9  call    cs:__imp_GetModuleHandleW
0x1800074bf  test    rax, rax
0x1800074c2  jz      short loc_1800074DD
0x1800074c4  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800074cb  mov     rcx, rax; hModule
0x1800074ce  call    cs:__imp_GetProcAddress
0x1800074d4  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800074db  jmp     short loc_1800074E4
0x1800074dd  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800074e4  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800074eb  test    rax, rax
0x1800074ee  jz      short loc_1800074FB
0x1800074f0  mov     rdx, rbx
0x1800074f3  mov     rcx, rsi
0x1800074f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074fb  mov     rsi, [rsp+28h+arg_8]
0x180007500  mov     rax, rbx
0x180007503  mov     rbx, [rsp+28h+arg_0]
0x180007508  add     rsp, 20h
0x18000750c  pop     rdi
0x18000750d  retn
```
