# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800115ac`
- end: `0x18001164a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a3f8`
- `0x18001316c`
- `0x1800133b8`

## callees

- `0x1800115ac`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800115f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800115f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001160a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001160a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800115d1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800115d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800115c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800115c0`

## string_xrefs

- `0x1800115ee`: `ntdll.dll`

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
0x1800115ac  mov     [rsp+arg_0], rbx
0x1800115b1  mov     [rsp+arg_8], rsi
0x1800115b6  push    rdi
0x1800115b7  sub     rsp, 20h
0x1800115bb  mov     rbx, rdx
0x1800115be  mov     edi, ecx
0x1800115c0  call    cs:__imp_GetProcessHeap
0x1800115c6  mov     r8, rbx; dwBytes
0x1800115c9  mov     edx, edi; dwFlags
0x1800115cb  mov     rcx, rax; hHeap
0x1800115ce  mov     rsi, rax
0x1800115d1  call    cs:__imp_HeapAlloc
0x1800115d7  mov     rbx, rax
0x1800115da  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800115e1  test    rax, rax
0x1800115e4  jnz     short loc_18001162C
0x1800115e6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800115ec  jnz     short loc_180011637
0x1800115ee  lea     rcx, ModuleName; "ntdll.dll"
0x1800115f5  call    cs:__imp_GetModuleHandleW
0x1800115fb  test    rax, rax
0x1800115fe  jz      short loc_180011619
0x180011600  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180011607  mov     rcx, rax; hModule
0x18001160a  call    cs:__imp_GetProcAddress
0x180011610  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180011617  jmp     short loc_180011620
0x180011619  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180011620  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180011627  test    rax, rax
0x18001162a  jz      short loc_180011637
0x18001162c  mov     rdx, rbx
0x18001162f  mov     rcx, rsi
0x180011632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011637  mov     rsi, [rsp+28h+arg_8]
0x18001163c  mov     rax, rbx
0x18001163f  mov     rbx, [rsp+28h+arg_0]
0x180011644  add     rsp, 20h
0x180011648  pop     rdi
0x180011649  retn
```
