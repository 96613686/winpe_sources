# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140015488`
- end: `0x140015526`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14001339c`
- `0x140013740`
- `0x140014320`
- `0x140016818`
- `0x140017744`

## callees

- `0x140015488`
- `0x140019010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x14001549c`
- `KERNEL32!GetProcessHeap` at `0x14001549c`
- `KERNEL32!HeapAlloc` at `0x1400154ad`
- `KERNEL32!HeapAlloc` at `0x1400154ad`
- `KERNEL32!GetProcAddress` at `0x1400154e6`
- `KERNEL32!GetProcAddress` at `0x1400154e6`
- `KERNEL32!GetModuleHandleW` at `0x1400154d1`
- `KERNEL32!GetModuleHandleW` at `0x1400154d1`

## string_xrefs

- `0x1400154ca`: `ntdll.dll`

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
0x140015488  mov     [rsp+arg_0], rbx
0x14001548d  mov     [rsp+arg_8], rsi
0x140015492  push    rdi
0x140015493  sub     rsp, 20h
0x140015497  mov     rbx, rdx
0x14001549a  mov     edi, ecx
0x14001549c  call    cs:__imp_GetProcessHeap
0x1400154a2  mov     r8, rbx; dwBytes
0x1400154a5  mov     edx, edi; dwFlags
0x1400154a7  mov     rcx, rax; hHeap
0x1400154aa  mov     rsi, rax
0x1400154ad  call    cs:__imp_HeapAlloc
0x1400154b3  mov     rbx, rax
0x1400154b6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400154bd  test    rax, rax
0x1400154c0  jnz     short loc_140015508
0x1400154c2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400154c8  jnz     short loc_140015513
0x1400154ca  lea     rcx, ModuleName; "ntdll.dll"
0x1400154d1  call    cs:__imp_GetModuleHandleW
0x1400154d7  test    rax, rax
0x1400154da  jz      short loc_1400154F5
0x1400154dc  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1400154e3  mov     rcx, rax; hModule
0x1400154e6  call    cs:__imp_GetProcAddress
0x1400154ec  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1400154f3  jmp     short loc_1400154FC
0x1400154f5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400154fc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140015503  test    rax, rax
0x140015506  jz      short loc_140015513
0x140015508  mov     rdx, rbx
0x14001550b  mov     rcx, rsi
0x14001550e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015513  mov     rsi, [rsp+28h+arg_8]
0x140015518  mov     rax, rbx
0x14001551b  mov     rbx, [rsp+28h+arg_0]
0x140015520  add     rsp, 20h
0x140015524  pop     rdi
0x140015525  retn
```
