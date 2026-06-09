# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1400054b0`
- end: `0x140005558`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `168`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140005280`
- `0x14000577c`
- `0x140005b14`
- `0x14000f180`
- `0x140010870`

## callees

- `0x1400054b0`
- `0x14002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x140005503`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x140005503`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140005518`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140005518`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400054ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400054ce`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400054df`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400054df`

## string_xrefs

- `0x1400054fc`: `ntdll.dll`

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
0x1400054b0  push    rdi
0x1400054b2  sub     rsp, 30h
0x1400054b6  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1400054bf  mov     [rsp+38h+arg_0], rbx
0x1400054c4  mov     [rsp+38h+arg_8], rsi
0x1400054c9  mov     rbx, rdx
0x1400054cc  mov     edi, ecx
0x1400054ce  call    cs:__imp_GetProcessHeap
0x1400054d4  mov     rsi, rax
0x1400054d7  mov     r8, rbx; dwBytes
0x1400054da  mov     edx, edi; dwFlags
0x1400054dc  mov     rcx, rax; hHeap
0x1400054df  call    cs:__imp_HeapAlloc
0x1400054e5  mov     rbx, rax
0x1400054e8  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400054ef  test    rax, rax
0x1400054f2  jnz     short loc_14000553A
0x1400054f4  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400054fa  jnz     short loc_140005545
0x1400054fc  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x140005503  call    cs:__imp_GetModuleHandleW
0x140005509  test    rax, rax
0x14000550c  jz      short loc_140005527
0x14000550e  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x140005515  mov     rcx, rax; hModule
0x140005518  call    cs:__imp_GetProcAddress
0x14000551e  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140005525  jmp     short loc_14000552E
0x140005527  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000552e  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140005535  test    rax, rax
0x140005538  jz      short loc_140005545
0x14000553a  mov     rdx, rbx
0x14000553d  mov     rcx, rsi
0x140005540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005545  mov     rax, rbx
0x140005548  mov     rbx, [rsp+38h+arg_0]
0x14000554d  mov     rsi, [rsp+38h+arg_8]
0x140005552  add     rsp, 30h
0x140005556  pop     rdi
0x140005557  retn
```
