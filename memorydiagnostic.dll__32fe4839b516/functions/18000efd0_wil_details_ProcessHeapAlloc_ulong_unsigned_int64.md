# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000efd0`
- end: `0x18000f087`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008cc4`
- `0x1800090b8`
- `0x18000d804`
- `0x180011660`
- `0x180011ecc`
- `0x18001864c`

## callees

- `0x18000efd0`
- `0x180024010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000efe4`
- `KERNEL32!GetProcessHeap` at `0x18000efe4`
- `KERNEL32!GetModuleHandleW` at `0x18000f025`
- `KERNEL32!GetModuleHandleW` at `0x18000f025`
- `KERNEL32!GetProcAddress` at `0x18000f040`
- `KERNEL32!GetProcAddress` at `0x18000f040`
- `KERNEL32!HeapAlloc` at `0x18000effb`
- `KERNEL32!HeapAlloc` at `0x18000effb`

## string_xrefs

- `0x18000f01e`: `ntdll.dll`

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
0x18000efd0  mov     [rsp+arg_0], rbx
0x18000efd5  mov     [rsp+arg_8], rsi
0x18000efda  push    rdi
0x18000efdb  sub     rsp, 20h
0x18000efdf  mov     rbx, rdx
0x18000efe2  mov     edi, ecx
0x18000efe4  call    cs:__imp_GetProcessHeap
0x18000efeb  nop     dword ptr [rax+rax+00h]
0x18000eff0  mov     rsi, rax
0x18000eff3  mov     r8, rbx; dwBytes
0x18000eff6  mov     edx, edi; dwFlags
0x18000eff8  mov     rcx, rax; hHeap
0x18000effb  call    cs:__imp_HeapAlloc
0x18000f002  nop     dword ptr [rax+rax+00h]
0x18000f007  mov     rbx, rax
0x18000f00a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000f011  test    rax, rax
0x18000f014  jnz     short loc_18000F068
0x18000f016  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000f01c  jnz     short loc_18000F073
0x18000f01e  lea     rcx, ModuleName; "ntdll.dll"
0x18000f025  call    cs:__imp_GetModuleHandleW
0x18000f02c  nop     dword ptr [rax+rax+00h]
0x18000f031  test    rax, rax
0x18000f034  jz      short loc_18000F055
0x18000f036  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000f03d  mov     rcx, rax; hModule
0x18000f040  call    cs:__imp_GetProcAddress
0x18000f047  nop     dword ptr [rax+rax+00h]
0x18000f04c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000f053  jmp     short loc_18000F05C
0x18000f055  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000f05c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000f063  test    rax, rax
0x18000f066  jz      short loc_18000F073
0x18000f068  mov     rdx, rbx
0x18000f06b  mov     rcx, rsi
0x18000f06e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f073  mov     rax, rbx
0x18000f076  mov     rbx, [rsp+28h+arg_0]
0x18000f07b  mov     rsi, [rsp+28h+arg_8]
0x18000f080  add     rsp, 20h
0x18000f084  pop     rdi
0x18000f085  retn
```
