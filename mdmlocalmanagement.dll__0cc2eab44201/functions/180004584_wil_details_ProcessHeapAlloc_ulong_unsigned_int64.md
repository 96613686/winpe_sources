# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180004584`
- end: `0x18000463b`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004210`
- `0x180004db8`

## callees

- `0x180004584`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800045f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800045f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800045d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800045d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004598`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004598`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800045af`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800045af`

## string_xrefs

- `0x1800045d2`: `ntdll.dll`

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
0x180004584  mov     [rsp+arg_0], rbx
0x180004589  mov     [rsp+arg_8], rsi
0x18000458e  push    rdi
0x18000458f  sub     rsp, 20h
0x180004593  mov     rbx, rdx
0x180004596  mov     edi, ecx
0x180004598  call    cs:__imp_GetProcessHeap
0x18000459f  nop     dword ptr [rax+rax+00h]
0x1800045a4  mov     rsi, rax
0x1800045a7  mov     r8, rbx; dwBytes
0x1800045aa  mov     edx, edi; dwFlags
0x1800045ac  mov     rcx, rax; hHeap
0x1800045af  call    cs:__imp_HeapAlloc
0x1800045b6  nop     dword ptr [rax+rax+00h]
0x1800045bb  mov     rbx, rax
0x1800045be  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800045c5  test    rax, rax
0x1800045c8  jnz     short loc_18000461C
0x1800045ca  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800045d0  jnz     short loc_180004627
0x1800045d2  lea     rcx, ModuleName; "ntdll.dll"
0x1800045d9  call    cs:__imp_GetModuleHandleW
0x1800045e0  nop     dword ptr [rax+rax+00h]
0x1800045e5  test    rax, rax
0x1800045e8  jz      short loc_180004609
0x1800045ea  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800045f1  mov     rcx, rax; hModule
0x1800045f4  call    cs:__imp_GetProcAddress
0x1800045fb  nop     dword ptr [rax+rax+00h]
0x180004600  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180004607  jmp     short loc_180004610
0x180004609  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180004610  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004617  test    rax, rax
0x18000461a  jz      short loc_180004627
0x18000461c  mov     rdx, rbx
0x18000461f  mov     rcx, rsi
0x180004622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004627  mov     rax, rbx
0x18000462a  mov     rbx, [rsp+28h+arg_0]
0x18000462f  mov     rsi, [rsp+28h+arg_8]
0x180004634  add     rsp, 20h
0x180004638  pop     rdi
0x180004639  retn
```
