# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1400083f8`
- end: `0x140008496`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140005738`
- `0x140005b08`
- `0x140006e70`
- `0x140007440`
- `0x140009854`
- `0x14000bb1c`

## callees

- `0x1400083f8`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140008441`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140008441`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008456`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008456`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000840c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000840c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000841d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000841d`

## string_xrefs

- `0x14000843a`: `ntdll.dll`

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
0x1400083f8  mov     [rsp+arg_0], rbx
0x1400083fd  mov     [rsp+arg_8], rsi
0x140008402  push    rdi
0x140008403  sub     rsp, 20h
0x140008407  mov     rbx, rdx
0x14000840a  mov     edi, ecx
0x14000840c  call    cs:__imp_GetProcessHeap
0x140008412  mov     rsi, rax
0x140008415  mov     r8, rbx; dwBytes
0x140008418  mov     edx, edi; dwFlags
0x14000841a  mov     rcx, rax; hHeap
0x14000841d  call    cs:__imp_HeapAlloc
0x140008423  mov     rbx, rax
0x140008426  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000842d  test    rax, rax
0x140008430  jnz     short loc_140008478
0x140008432  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140008438  jnz     short loc_140008483
0x14000843a  lea     rcx, ModuleName; "ntdll.dll"
0x140008441  call    cs:__imp_GetModuleHandleW
0x140008447  test    rax, rax
0x14000844a  jz      short loc_140008465
0x14000844c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x140008453  mov     rcx, rax; hModule
0x140008456  call    cs:__imp_GetProcAddress
0x14000845c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140008463  jmp     short loc_14000846C
0x140008465  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000846c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140008473  test    rax, rax
0x140008476  jz      short loc_140008483
0x140008478  mov     rdx, rbx
0x14000847b  mov     rcx, rsi
0x14000847e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008483  mov     rax, rbx
0x140008486  mov     rbx, [rsp+28h+arg_0]
0x14000848b  mov     rsi, [rsp+28h+arg_8]
0x140008490  add     rsp, 20h
0x140008494  pop     rdi
0x140008495  retn
```
