# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140079c0c`
- end: `0x140079caa`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140074f78`
- `0x1400750cc`
- `0x14007a6b0`
- `0x14007ab34`
- `0x14007b954`

## callees

- `0x140079c0c`
- `0x140098010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x140079c55`
- `KERNEL32!GetModuleHandleW` at `0x140079c55`
- `KERNEL32!GetProcessHeap` at `0x140079c20`
- `KERNEL32!GetProcessHeap` at `0x140079c20`
- `KERNEL32!GetProcAddress` at `0x140079c6a`
- `KERNEL32!GetProcAddress` at `0x140079c6a`
- `KERNEL32!HeapAlloc` at `0x140079c31`
- `KERNEL32!HeapAlloc` at `0x140079c31`

## string_xrefs

- `0x140079c4e`: `ntdll.dll`

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
0x140079c0c  mov     [rsp+arg_0], rbx
0x140079c11  mov     [rsp+arg_8], rsi
0x140079c16  push    rdi
0x140079c17  sub     rsp, 20h
0x140079c1b  mov     rbx, rdx
0x140079c1e  mov     edi, ecx
0x140079c20  call    cs:__imp_GetProcessHeap
0x140079c26  mov     rsi, rax
0x140079c29  mov     r8, rbx; dwBytes
0x140079c2c  mov     edx, edi; dwFlags
0x140079c2e  mov     rcx, rax; hHeap
0x140079c31  call    cs:__imp_HeapAlloc
0x140079c37  mov     rbx, rax
0x140079c3a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140079c41  test    rax, rax
0x140079c44  jnz     short loc_140079C8C
0x140079c46  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140079c4c  jnz     short loc_140079C97
0x140079c4e  lea     rcx, ModuleName; "ntdll.dll"
0x140079c55  call    cs:__imp_GetModuleHandleW
0x140079c5b  test    rax, rax
0x140079c5e  jz      short loc_140079C79
0x140079c60  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x140079c67  mov     rcx, rax; hModule
0x140079c6a  call    cs:__imp_GetProcAddress
0x140079c70  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140079c77  jmp     short loc_140079C80
0x140079c79  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140079c80  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140079c87  test    rax, rax
0x140079c8a  jz      short loc_140079C97
0x140079c8c  mov     rdx, rbx
0x140079c8f  mov     rcx, rsi
0x140079c92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140079c97  mov     rax, rbx
0x140079c9a  mov     rbx, [rsp+28h+arg_0]
0x140079c9f  mov     rsi, [rsp+28h+arg_8]
0x140079ca4  add     rsp, 20h
0x140079ca8  pop     rdi
0x140079ca9  retn
```
