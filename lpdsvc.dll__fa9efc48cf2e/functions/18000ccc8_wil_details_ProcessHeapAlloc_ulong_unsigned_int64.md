# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000ccc8`
- end: `0x18000cd66`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b59c`
- `0x18000bc80`
- `0x18000d010`

## callees

- `0x18000ccc8`
- `0x18000e010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000cd26`
- `KERNEL32!GetProcAddress` at `0x18000cd26`
- `KERNEL32!GetModuleHandleW` at `0x18000cd11`
- `KERNEL32!GetModuleHandleW` at `0x18000cd11`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cced`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cced`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ccdc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ccdc`

## string_xrefs

- `0x18000cd0a`: `ntdll.dll`

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
0x18000ccc8  mov     [rsp+arg_0], rbx
0x18000cccd  mov     [rsp+arg_8], rsi
0x18000ccd2  push    rdi
0x18000ccd3  sub     rsp, 20h
0x18000ccd7  mov     rbx, rdx
0x18000ccda  mov     edi, ecx
0x18000ccdc  call    cs:__imp_GetProcessHeap
0x18000cce2  mov     r8, rbx; dwBytes
0x18000cce5  mov     edx, edi; dwFlags
0x18000cce7  mov     rcx, rax; hHeap
0x18000ccea  mov     rsi, rax
0x18000cced  call    cs:__imp_HeapAlloc
0x18000ccf3  mov     rbx, rax
0x18000ccf6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000ccfd  test    rax, rax
0x18000cd00  jnz     short loc_18000CD48
0x18000cd02  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000cd08  jnz     short loc_18000CD53
0x18000cd0a  lea     rcx, ModuleName; "ntdll.dll"
0x18000cd11  call    cs:__imp_GetModuleHandleW
0x18000cd17  test    rax, rax
0x18000cd1a  jz      short loc_18000CD35
0x18000cd1c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000cd23  mov     rcx, rax; hModule
0x18000cd26  call    cs:__imp_GetProcAddress
0x18000cd2c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000cd33  jmp     short loc_18000CD3C
0x18000cd35  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000cd3c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000cd43  test    rax, rax
0x18000cd46  jz      short loc_18000CD53
0x18000cd48  mov     rdx, rbx
0x18000cd4b  mov     rcx, rsi
0x18000cd4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd53  mov     rsi, [rsp+28h+arg_8]
0x18000cd58  mov     rax, rbx
0x18000cd5b  mov     rbx, [rsp+28h+arg_0]
0x18000cd60  add     rsp, 20h
0x18000cd64  pop     rdi
0x18000cd65  retn
```
