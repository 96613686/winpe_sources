# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180006764`
- end: `0x18000681b`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800043ec`
- `0x1800047e4`
- `0x1800080e0`
- `0x18000894c`
- `0x180009b60`

## callees

- `0x180006764`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800067b9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800067b9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800067d4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800067d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006778`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006778`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000678f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000678f`

## string_xrefs

- `0x1800067b2`: `ntdll.dll`

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
0x180006764  mov     [rsp+arg_0], rbx
0x180006769  mov     [rsp+arg_8], rsi
0x18000676e  push    rdi
0x18000676f  sub     rsp, 20h
0x180006773  mov     rbx, rdx
0x180006776  mov     edi, ecx
0x180006778  call    cs:__imp_GetProcessHeap
0x18000677f  nop     dword ptr [rax+rax+00h]
0x180006784  mov     rsi, rax
0x180006787  mov     r8, rbx; dwBytes
0x18000678a  mov     edx, edi; dwFlags
0x18000678c  mov     rcx, rax; hHeap
0x18000678f  call    cs:__imp_HeapAlloc
0x180006796  nop     dword ptr [rax+rax+00h]
0x18000679b  mov     rbx, rax
0x18000679e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800067a5  test    rax, rax
0x1800067a8  jnz     short loc_1800067FC
0x1800067aa  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800067b0  jnz     short loc_180006807
0x1800067b2  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x1800067b9  call    cs:__imp_GetModuleHandleW
0x1800067c0  nop     dword ptr [rax+rax+00h]
0x1800067c5  test    rax, rax
0x1800067c8  jz      short loc_1800067E9
0x1800067ca  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800067d1  mov     rcx, rax; hModule
0x1800067d4  call    cs:__imp_GetProcAddress
0x1800067db  nop     dword ptr [rax+rax+00h]
0x1800067e0  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800067e7  jmp     short loc_1800067F0
0x1800067e9  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800067f0  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800067f7  test    rax, rax
0x1800067fa  jz      short loc_180006807
0x1800067fc  mov     rdx, rbx
0x1800067ff  mov     rcx, rsi
0x180006802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006807  mov     rax, rbx
0x18000680a  mov     rbx, [rsp+28h+arg_0]
0x18000680f  mov     rsi, [rsp+28h+arg_8]
0x180006814  add     rsp, 20h
0x180006818  pop     rdi
0x180006819  retn
```
