# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140019514`
- end: `0x1400195b3`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `159`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400190b0`
- `0x1400191dc`
- `0x14001a460`
- `0x14001a924`
- `0x14001bcc0`

## callees

- `0x140019514`
- `0x140020010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140019572`
- `KERNEL32!GetProcAddress` at `0x140019572`
- `KERNEL32!HeapAlloc` at `0x140019539`
- `KERNEL32!HeapAlloc` at `0x140019539`
- `KERNEL32!GetProcessHeap` at `0x140019528`
- `KERNEL32!GetProcessHeap` at `0x140019528`
- `KERNEL32!GetModuleHandleW` at `0x14001955d`
- `KERNEL32!GetModuleHandleW` at `0x14001955d`

## string_xrefs

- `0x140019556`: `ntdll.dll`

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
0x140019514  mov     [rsp+arg_0], rbx
0x140019519  mov     [rsp+arg_8], rsi
0x14001951e  push    rdi
0x14001951f  sub     rsp, 20h
0x140019523  mov     rbx, rdx
0x140019526  mov     edi, ecx
0x140019528  call    cs:__imp_GetProcessHeap
0x14001952e  mov     rsi, rax
0x140019531  mov     r8, rbx; dwBytes
0x140019534  mov     edx, edi; dwFlags
0x140019536  mov     rcx, rax; hHeap
0x140019539  call    cs:__imp_HeapAlloc
0x14001953f  mov     rbx, rax
0x140019542  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140019549  test    rax, rax
0x14001954c  jnz     short loc_140019595
0x14001954e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140019554  jnz     short loc_1400195A0
0x140019556  lea     rcx, ModuleName; "ntdll.dll"
0x14001955d  call    cs:__imp_GetModuleHandleW
0x140019563  test    rax, rax
0x140019566  jz      short loc_140019582
0x140019568  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x14001956f  mov     rcx, rax; hModule
0x140019572  call    cs:__imp_GetProcAddress
0x140019578  nop
0x140019579  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140019580  jmp     short loc_140019589
0x140019582  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140019589  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140019590  test    rax, rax
0x140019593  jz      short loc_1400195A0
0x140019595  mov     rdx, rbx
0x140019598  mov     rcx, rsi
0x14001959b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400195a0  mov     rax, rbx
0x1400195a3  mov     rbx, [rsp+28h+arg_0]
0x1400195a8  mov     rsi, [rsp+28h+arg_8]
0x1400195ad  add     rsp, 20h
0x1400195b1  pop     rdi
0x1400195b2  retn
```
