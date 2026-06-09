# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x14000c07c`
- end: `0x14000c11a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000bee0`
- `0x14000cadc`

## callees

- `0x14000c07c`
- `0x140017010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14000c0a1`
- `KERNEL32!HeapAlloc` at `0x14000c0a1`
- `KERNEL32!GetProcAddress` at `0x14000c0da`
- `KERNEL32!GetProcAddress` at `0x14000c0da`
- `KERNEL32!GetModuleHandleW` at `0x14000c0c5`
- `KERNEL32!GetModuleHandleW` at `0x14000c0c5`
- `KERNEL32!GetProcessHeap` at `0x14000c090`
- `KERNEL32!GetProcessHeap` at `0x14000c090`

## string_xrefs

- `0x14000c0be`: `ntdll.dll`

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
0x14000c07c  mov     [rsp+arg_0], rbx
0x14000c081  mov     [rsp+arg_8], rsi
0x14000c086  push    rdi
0x14000c087  sub     rsp, 20h
0x14000c08b  mov     rbx, rdx
0x14000c08e  mov     edi, ecx
0x14000c090  call    cs:__imp_GetProcessHeap
0x14000c096  mov     r8, rbx; dwBytes
0x14000c099  mov     edx, edi; dwFlags
0x14000c09b  mov     rcx, rax; hHeap
0x14000c09e  mov     rsi, rax
0x14000c0a1  call    cs:__imp_HeapAlloc
0x14000c0a7  mov     rbx, rax
0x14000c0aa  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000c0b1  test    rax, rax
0x14000c0b4  jnz     short loc_14000C0FC
0x14000c0b6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000c0bc  jnz     short loc_14000C107
0x14000c0be  lea     rcx, ModuleName; "ntdll.dll"
0x14000c0c5  call    cs:__imp_GetModuleHandleW
0x14000c0cb  test    rax, rax
0x14000c0ce  jz      short loc_14000C0E9
0x14000c0d0  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x14000c0d7  mov     rcx, rax; hModule
0x14000c0da  call    cs:__imp_GetProcAddress
0x14000c0e0  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x14000c0e7  jmp     short loc_14000C0F0
0x14000c0e9  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000c0f0  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000c0f7  test    rax, rax
0x14000c0fa  jz      short loc_14000C107
0x14000c0fc  mov     rdx, rbx
0x14000c0ff  mov     rcx, rsi
0x14000c102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c107  mov     rsi, [rsp+28h+arg_8]
0x14000c10c  mov     rax, rbx
0x14000c10f  mov     rbx, [rsp+28h+arg_0]
0x14000c114  add     rsp, 20h
0x14000c118  pop     rdi
0x14000c119  retn
```
