# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1400056d8`
- end: `0x140005776`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140004aec`
- `0x1400054dc`
- `0x140005ab4`
- `0x140005e4c`
- `0x140007dd0`
- `0x14000a7cc`

## callees

- `0x1400056d8`
- `0x140018010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400056ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400056ec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400056fd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400056fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005721`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005721`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005736`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005736`

## string_xrefs

- `0x14000571a`: `ntdll.dll`

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
0x1400056d8  mov     [rsp+arg_0], rbx
0x1400056dd  mov     [rsp+arg_8], rsi
0x1400056e2  push    rdi
0x1400056e3  sub     rsp, 20h
0x1400056e7  mov     rbx, rdx
0x1400056ea  mov     edi, ecx
0x1400056ec  call    cs:__imp_GetProcessHeap
0x1400056f2  mov     rsi, rax
0x1400056f5  mov     r8, rbx; dwBytes
0x1400056f8  mov     edx, edi; dwFlags
0x1400056fa  mov     rcx, rax; hHeap
0x1400056fd  call    cs:__imp_HeapAlloc
0x140005703  mov     rbx, rax
0x140005706  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000570d  test    rax, rax
0x140005710  jnz     short loc_140005758
0x140005712  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140005718  jnz     short loc_140005763
0x14000571a  lea     rcx, ModuleName; "ntdll.dll"
0x140005721  call    cs:__imp_GetModuleHandleW
0x140005727  test    rax, rax
0x14000572a  jz      short loc_140005745
0x14000572c  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x140005733  mov     rcx, rax; hModule
0x140005736  call    cs:__imp_GetProcAddress
0x14000573c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140005743  jmp     short loc_14000574C
0x140005745  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000574c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140005753  test    rax, rax
0x140005756  jz      short loc_140005763
0x140005758  mov     rdx, rbx
0x14000575b  mov     rcx, rsi
0x14000575e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005763  mov     rax, rbx
0x140005766  mov     rbx, [rsp+28h+arg_0]
0x14000576b  mov     rsi, [rsp+28h+arg_8]
0x140005770  add     rsp, 20h
0x140005774  pop     rdi
0x140005775  retn
```
