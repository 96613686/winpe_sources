# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18001498c`
- end: `0x180014a2a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000d320`
- `0x180013f58`
- `0x18001407c`
- `0x180016084`
- `0x1800162e8`

## callees

- `0x18001498c`
- `0x180023010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800149d5`
- `KERNEL32!GetModuleHandleW` at `0x1800149d5`
- `KERNEL32!GetProcAddress` at `0x1800149ea`
- `KERNEL32!GetProcAddress` at `0x1800149ea`
- `KERNEL32!GetProcessHeap` at `0x1800149a0`
- `KERNEL32!GetProcessHeap` at `0x1800149a0`
- `KERNEL32!HeapAlloc` at `0x1800149b1`
- `KERNEL32!HeapAlloc` at `0x1800149b1`

## string_xrefs

- `0x1800149ce`: `ntdll.dll`

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
0x18001498c  mov     [rsp+arg_0], rbx
0x180014991  mov     [rsp+arg_8], rsi
0x180014996  push    rdi
0x180014997  sub     rsp, 20h
0x18001499b  mov     rbx, rdx
0x18001499e  mov     edi, ecx
0x1800149a0  call    cs:__imp_GetProcessHeap
0x1800149a6  mov     r8, rbx; dwBytes
0x1800149a9  mov     edx, edi; dwFlags
0x1800149ab  mov     rcx, rax; hHeap
0x1800149ae  mov     rsi, rax
0x1800149b1  call    cs:__imp_HeapAlloc
0x1800149b7  mov     rbx, rax
0x1800149ba  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800149c1  test    rax, rax
0x1800149c4  jnz     short loc_180014A0C
0x1800149c6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800149cc  jnz     short loc_180014A17
0x1800149ce  lea     rcx, aNtdllDll; "ntdll.dll"
0x1800149d5  call    cs:__imp_GetModuleHandleW
0x1800149db  test    rax, rax
0x1800149de  jz      short loc_1800149F9
0x1800149e0  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800149e7  mov     rcx, rax; hModule
0x1800149ea  call    cs:__imp_GetProcAddress
0x1800149f0  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800149f7  jmp     short loc_180014A00
0x1800149f9  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180014a00  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180014a07  test    rax, rax
0x180014a0a  jz      short loc_180014A17
0x180014a0c  mov     rdx, rbx
0x180014a0f  mov     rcx, rsi
0x180014a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a17  mov     rsi, [rsp+28h+arg_8]
0x180014a1c  mov     rax, rbx
0x180014a1f  mov     rbx, [rsp+28h+arg_0]
0x180014a24  add     rsp, 20h
0x180014a28  pop     rdi
0x180014a29  retn
```
