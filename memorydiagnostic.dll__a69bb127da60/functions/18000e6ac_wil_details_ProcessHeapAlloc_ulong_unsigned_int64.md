# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000e6ac`
- end: `0x18000e74a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008cc8`
- `0x180009098`
- `0x18000c7b0`
- `0x18000d0d0`
- `0x180010c4c`
- `0x180015d60`

## callees

- `0x18000e6ac`
- `0x180023010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000e6f5`
- `KERNEL32!GetModuleHandleW` at `0x18000e6f5`
- `KERNEL32!GetProcessHeap` at `0x18000e6c0`
- `KERNEL32!GetProcessHeap` at `0x18000e6c0`
- `KERNEL32!GetProcAddress` at `0x18000e70a`
- `KERNEL32!GetProcAddress` at `0x18000e70a`
- `KERNEL32!HeapAlloc` at `0x18000e6d1`
- `KERNEL32!HeapAlloc` at `0x18000e6d1`

## string_xrefs

- `0x18000e6ee`: `ntdll.dll`

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
0x18000e6ac  mov     [rsp+arg_0], rbx
0x18000e6b1  mov     [rsp+arg_8], rsi
0x18000e6b6  push    rdi
0x18000e6b7  sub     rsp, 20h
0x18000e6bb  mov     rbx, rdx
0x18000e6be  mov     edi, ecx
0x18000e6c0  call    cs:__imp_GetProcessHeap
0x18000e6c6  mov     rsi, rax
0x18000e6c9  mov     r8, rbx; dwBytes
0x18000e6cc  mov     edx, edi; dwFlags
0x18000e6ce  mov     rcx, rax; hHeap
0x18000e6d1  call    cs:__imp_HeapAlloc
0x18000e6d7  mov     rbx, rax
0x18000e6da  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000e6e1  test    rax, rax
0x18000e6e4  jnz     short loc_18000E72C
0x18000e6e6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000e6ec  jnz     short loc_18000E737
0x18000e6ee  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18000e6f5  call    cs:__imp_GetModuleHandleW
0x18000e6fb  test    rax, rax
0x18000e6fe  jz      short loc_18000E719
0x18000e700  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000e707  mov     rcx, rax; hModule
0x18000e70a  call    cs:__imp_GetProcAddress
0x18000e710  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000e717  jmp     short loc_18000E720
0x18000e719  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000e720  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000e727  test    rax, rax
0x18000e72a  jz      short loc_18000E737
0x18000e72c  mov     rdx, rbx
0x18000e72f  mov     rcx, rsi
0x18000e732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e737  mov     rax, rbx
0x18000e73a  mov     rbx, [rsp+28h+arg_0]
0x18000e73f  mov     rsi, [rsp+28h+arg_8]
0x18000e744  add     rsp, 20h
0x18000e748  pop     rdi
0x18000e749  retn
```
