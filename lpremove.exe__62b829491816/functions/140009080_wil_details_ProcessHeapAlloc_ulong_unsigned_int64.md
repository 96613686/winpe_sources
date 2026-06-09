# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140009080`
- end: `0x14000911e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140005ce8`
- `0x1400060b8`
- `0x140007190`
- `0x140007760`
- `0x14000aa04`
- `0x14000d04c`

## callees

- `0x140009080`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1400090c9`
- `KERNEL32!GetModuleHandleW` at `0x1400090c9`
- `KERNEL32!GetProcAddress` at `0x1400090de`
- `KERNEL32!GetProcAddress` at `0x1400090de`
- `KERNEL32!GetProcessHeap` at `0x140009094`
- `KERNEL32!GetProcessHeap` at `0x140009094`
- `KERNEL32!HeapAlloc` at `0x1400090a5`
- `KERNEL32!HeapAlloc` at `0x1400090a5`

## string_xrefs

- `0x1400090c2`: `ntdll.dll`

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
0x140009080  mov     [rsp+arg_0], rbx
0x140009085  mov     [rsp+arg_8], rsi
0x14000908a  push    rdi
0x14000908b  sub     rsp, 20h
0x14000908f  mov     rbx, rdx
0x140009092  mov     edi, ecx
0x140009094  call    cs:__imp_GetProcessHeap
0x14000909a  mov     rsi, rax
0x14000909d  mov     r8, rbx; dwBytes
0x1400090a0  mov     edx, edi; dwFlags
0x1400090a2  mov     rcx, rax; hHeap
0x1400090a5  call    cs:__imp_HeapAlloc
0x1400090ab  mov     rbx, rax
0x1400090ae  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400090b5  test    rax, rax
0x1400090b8  jnz     short loc_140009100
0x1400090ba  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400090c0  jnz     short loc_14000910B
0x1400090c2  lea     rcx, ModuleName; "ntdll.dll"
0x1400090c9  call    cs:__imp_GetModuleHandleW
0x1400090cf  test    rax, rax
0x1400090d2  jz      short loc_1400090ED
0x1400090d4  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1400090db  mov     rcx, rax; hModule
0x1400090de  call    cs:__imp_GetProcAddress
0x1400090e4  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1400090eb  jmp     short loc_1400090F4
0x1400090ed  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400090f4  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400090fb  test    rax, rax
0x1400090fe  jz      short loc_14000910B
0x140009100  mov     rdx, rbx
0x140009103  mov     rcx, rsi
0x140009106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000910b  mov     rax, rbx
0x14000910e  mov     rbx, [rsp+28h+arg_0]
0x140009113  mov     rsi, [rsp+28h+arg_8]
0x140009118  add     rsp, 20h
0x14000911c  pop     rdi
0x14000911d  retn
```
