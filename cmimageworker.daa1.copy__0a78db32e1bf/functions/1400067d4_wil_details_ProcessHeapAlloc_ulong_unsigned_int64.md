# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1400067d4`
- end: `0x14000688b`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000418c`
- `0x140004ed0`
- `0x140007500`
- `0x140016494`
- `0x140020274`

## callees

- `0x1400067d4`
- `0x140034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006844`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006844`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006829`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006829`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400067e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400067e8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400067ff`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400067ff`

## string_xrefs

- `0x140006822`: `ntdll.dll`

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
0x1400067d4  mov     [rsp+arg_0], rbx
0x1400067d9  mov     [rsp+arg_8], rsi
0x1400067de  push    rdi
0x1400067df  sub     rsp, 20h
0x1400067e3  mov     rbx, rdx
0x1400067e6  mov     edi, ecx
0x1400067e8  call    cs:__imp_GetProcessHeap
0x1400067ef  nop     dword ptr [rax+rax+00h]
0x1400067f4  mov     rsi, rax
0x1400067f7  mov     r8, rbx; dwBytes
0x1400067fa  mov     edx, edi; dwFlags
0x1400067fc  mov     rcx, rax; hHeap
0x1400067ff  call    cs:__imp_HeapAlloc
0x140006806  nop     dword ptr [rax+rax+00h]
0x14000680b  mov     rbx, rax
0x14000680e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140006815  test    rax, rax
0x140006818  jnz     short loc_14000686C
0x14000681a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140006820  jnz     short loc_140006877
0x140006822  lea     rcx, ModuleName; "ntdll.dll"
0x140006829  call    cs:__imp_GetModuleHandleW
0x140006830  nop     dword ptr [rax+rax+00h]
0x140006835  test    rax, rax
0x140006838  jz      short loc_140006859
0x14000683a  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x140006841  mov     rcx, rax; hModule
0x140006844  call    cs:__imp_GetProcAddress
0x14000684b  nop     dword ptr [rax+rax+00h]
0x140006850  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140006857  jmp     short loc_140006860
0x140006859  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140006860  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140006867  test    rax, rax
0x14000686a  jz      short loc_140006877
0x14000686c  mov     rdx, rbx
0x14000686f  mov     rcx, rsi
0x140006872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006877  mov     rax, rbx
0x14000687a  mov     rbx, [rsp+28h+arg_0]
0x14000687f  mov     rsi, [rsp+28h+arg_8]
0x140006884  add     rsp, 20h
0x140006888  pop     rdi
0x140006889  retn
```
