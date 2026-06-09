# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000550c`
- end: `0x1800055aa`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800037d4`
- `0x1800042e0`
- `0x180005d60`

## callees

- `0x18000550c`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000556a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000556a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005555`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005555`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005531`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005531`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005520`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005520`

## string_xrefs

- `0x18000554e`: `ntdll.dll`

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
0x18000550c  mov     [rsp+arg_0], rbx
0x180005511  mov     [rsp+arg_8], rsi
0x180005516  push    rdi
0x180005517  sub     rsp, 20h
0x18000551b  mov     rbx, rdx
0x18000551e  mov     edi, ecx
0x180005520  call    cs:__imp_GetProcessHeap
0x180005526  mov     rsi, rax
0x180005529  mov     r8, rbx; dwBytes
0x18000552c  mov     edx, edi; dwFlags
0x18000552e  mov     rcx, rax; hHeap
0x180005531  call    cs:__imp_HeapAlloc
0x180005537  mov     rbx, rax
0x18000553a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005541  test    rax, rax
0x180005544  jnz     short loc_18000558C
0x180005546  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000554c  jnz     short loc_180005597
0x18000554e  lea     rcx, ModuleName; "ntdll.dll"
0x180005555  call    cs:__imp_GetModuleHandleW
0x18000555b  test    rax, rax
0x18000555e  jz      short loc_180005579
0x180005560  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180005567  mov     rcx, rax; hModule
0x18000556a  call    cs:__imp_GetProcAddress
0x180005570  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005577  jmp     short loc_180005580
0x180005579  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005580  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005587  test    rax, rax
0x18000558a  jz      short loc_180005597
0x18000558c  mov     rdx, rbx
0x18000558f  mov     rcx, rsi
0x180005592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005597  mov     rax, rbx
0x18000559a  mov     rbx, [rsp+28h+arg_0]
0x18000559f  mov     rsi, [rsp+28h+arg_8]
0x1800055a4  add     rsp, 20h
0x1800055a8  pop     rdi
0x1800055a9  retn
```
