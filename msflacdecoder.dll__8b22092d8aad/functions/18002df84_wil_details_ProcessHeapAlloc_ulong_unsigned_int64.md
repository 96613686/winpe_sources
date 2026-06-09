# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18002df84`
- end: `0x18002e022`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002d158`
- `0x18002e4fc`
- `0x18002eb14`

## callees

- `0x18002df84`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002dfcd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002dfcd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002dfe2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002dfe2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002df98`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002df98`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002dfa9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002dfa9`

## string_xrefs

- `0x18002dfc6`: `ntdll.dll`

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
0x18002df84  mov     [rsp+arg_0], rbx
0x18002df89  mov     [rsp+arg_8], rsi
0x18002df8e  push    rdi
0x18002df8f  sub     rsp, 20h
0x18002df93  mov     rbx, rdx
0x18002df96  mov     edi, ecx
0x18002df98  call    cs:__imp_GetProcessHeap
0x18002df9e  mov     rsi, rax
0x18002dfa1  mov     r8, rbx; dwBytes
0x18002dfa4  mov     edx, edi; dwFlags
0x18002dfa6  mov     rcx, rax; hHeap
0x18002dfa9  call    cs:__imp_HeapAlloc
0x18002dfaf  mov     rbx, rax
0x18002dfb2  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18002dfb9  test    rax, rax
0x18002dfbc  jnz     short loc_18002E004
0x18002dfbe  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18002dfc4  jnz     short loc_18002E00F
0x18002dfc6  lea     rcx, aNtdllDll; "ntdll.dll"
0x18002dfcd  call    cs:__imp_GetModuleHandleW
0x18002dfd3  test    rax, rax
0x18002dfd6  jz      short loc_18002DFF1
0x18002dfd8  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18002dfdf  mov     rcx, rax; hModule
0x18002dfe2  call    cs:__imp_GetProcAddress
0x18002dfe8  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18002dfef  jmp     short loc_18002DFF8
0x18002dff1  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18002dff8  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18002dfff  test    rax, rax
0x18002e002  jz      short loc_18002E00F
0x18002e004  mov     rdx, rbx
0x18002e007  mov     rcx, rsi
0x18002e00a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e00f  mov     rax, rbx
0x18002e012  mov     rbx, [rsp+28h+arg_0]
0x18002e017  mov     rsi, [rsp+28h+arg_8]
0x18002e01c  add     rsp, 20h
0x18002e020  pop     rdi
0x18002e021  retn
```
