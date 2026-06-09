# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180078888`
- end: `0x180078926`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800783a8`
- `0x1800784d0`
- `0x180079d94`
- `0x180079fc0`
- `0x18007b11c`

## callees

- `0x180078888`
- `0x180092010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800788e6`
- `KERNEL32!GetProcAddress` at `0x1800788e6`
- `KERNEL32!GetProcessHeap` at `0x18007889c`
- `KERNEL32!GetProcessHeap` at `0x18007889c`
- `KERNEL32!HeapAlloc` at `0x1800788ad`
- `KERNEL32!HeapAlloc` at `0x1800788ad`
- `KERNEL32!GetModuleHandleW` at `0x1800788d1`
- `KERNEL32!GetModuleHandleW` at `0x1800788d1`

## string_xrefs

- `0x1800788ca`: `ntdll.dll`

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
0x180078888  mov     [rsp+arg_0], rbx
0x18007888d  mov     [rsp+arg_8], rsi
0x180078892  push    rdi
0x180078893  sub     rsp, 20h
0x180078897  mov     rbx, rdx
0x18007889a  mov     edi, ecx
0x18007889c  call    cs:__imp_GetProcessHeap
0x1800788a2  mov     r8, rbx; dwBytes
0x1800788a5  mov     edx, edi; dwFlags
0x1800788a7  mov     rcx, rax; hHeap
0x1800788aa  mov     rsi, rax
0x1800788ad  call    cs:__imp_HeapAlloc
0x1800788b3  mov     rbx, rax
0x1800788b6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800788bd  test    rax, rax
0x1800788c0  jnz     short loc_180078908
0x1800788c2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800788c8  jnz     short loc_180078913
0x1800788ca  lea     rcx, ModuleName; "ntdll.dll"
0x1800788d1  call    cs:__imp_GetModuleHandleW
0x1800788d7  test    rax, rax
0x1800788da  jz      short loc_1800788F5
0x1800788dc  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800788e3  mov     rcx, rax; hModule
0x1800788e6  call    cs:__imp_GetProcAddress
0x1800788ec  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800788f3  jmp     short loc_1800788FC
0x1800788f5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800788fc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180078903  test    rax, rax
0x180078906  jz      short loc_180078913
0x180078908  mov     rdx, rbx
0x18007890b  mov     rcx, rsi
0x18007890e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078913  mov     rsi, [rsp+28h+arg_8]
0x180078918  mov     rax, rbx
0x18007891b  mov     rbx, [rsp+28h+arg_0]
0x180078920  add     rsp, 20h
0x180078924  pop     rdi
0x180078925  retn
```
