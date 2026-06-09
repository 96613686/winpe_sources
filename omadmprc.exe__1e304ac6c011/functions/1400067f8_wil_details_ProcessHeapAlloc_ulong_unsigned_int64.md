# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1400067f8`
- end: `0x1400068af`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400042a4`
- `0x140004680`
- `0x140008b50`
- `0x14000a33c`

## callees

- `0x1400067f8`
- `0x140017010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140006823`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140006823`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000680c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000680c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000684d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000684d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006868`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006868`

## string_xrefs

- `0x140006846`: `ntdll.dll`

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
0x1400067f8  mov     [rsp+arg_0], rbx
0x1400067fd  mov     [rsp+arg_8], rsi
0x140006802  push    rdi
0x140006803  sub     rsp, 20h
0x140006807  mov     rbx, rdx
0x14000680a  mov     edi, ecx
0x14000680c  call    cs:__imp_GetProcessHeap
0x140006813  nop     dword ptr [rax+rax+00h]
0x140006818  mov     rsi, rax
0x14000681b  mov     r8, rbx; dwBytes
0x14000681e  mov     edx, edi; dwFlags
0x140006820  mov     rcx, rax; hHeap
0x140006823  call    cs:__imp_HeapAlloc
0x14000682a  nop     dword ptr [rax+rax+00h]
0x14000682f  mov     rbx, rax
0x140006832  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140006839  test    rax, rax
0x14000683c  jnz     short loc_140006890
0x14000683e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140006844  jnz     short loc_14000689B
0x140006846  lea     rcx, ModuleName; "ntdll.dll"
0x14000684d  call    cs:__imp_GetModuleHandleW
0x140006854  nop     dword ptr [rax+rax+00h]
0x140006859  test    rax, rax
0x14000685c  jz      short loc_14000687D
0x14000685e  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x140006865  mov     rcx, rax; hModule
0x140006868  call    cs:__imp_GetProcAddress
0x14000686f  nop     dword ptr [rax+rax+00h]
0x140006874  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x14000687b  jmp     short loc_140006884
0x14000687d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140006884  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000688b  test    rax, rax
0x14000688e  jz      short loc_14000689B
0x140006890  mov     rdx, rbx
0x140006893  mov     rcx, rsi
0x140006896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000689b  mov     rax, rbx
0x14000689e  mov     rbx, [rsp+28h+arg_0]
0x1400068a3  mov     rsi, [rsp+28h+arg_8]
0x1400068a8  add     rsp, 20h
0x1400068ac  pop     rdi
0x1400068ad  retn
```
