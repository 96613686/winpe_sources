# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000a908`
- end: `0x18000a9a6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008828`
- `0x180008bcc`
- `0x18000c1cc`
- `0x18000d020`

## callees

- `0x18000a908`
- `0x180017010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000a92d`
- `KERNEL32!HeapAlloc` at `0x18000a92d`
- `KERNEL32!GetProcessHeap` at `0x18000a91c`
- `KERNEL32!GetProcessHeap` at `0x18000a91c`
- `KERNEL32!GetModuleHandleW` at `0x18000a951`
- `KERNEL32!GetModuleHandleW` at `0x18000a951`
- `KERNEL32!GetProcAddress` at `0x18000a966`
- `KERNEL32!GetProcAddress` at `0x18000a966`

## string_xrefs

- `0x18000a94a`: `ntdll.dll`

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
0x18000a908  mov     [rsp+arg_0], rbx
0x18000a90d  mov     [rsp+arg_8], rsi
0x18000a912  push    rdi
0x18000a913  sub     rsp, 20h
0x18000a917  mov     rbx, rdx
0x18000a91a  mov     edi, ecx
0x18000a91c  call    cs:__imp_GetProcessHeap
0x18000a922  mov     rsi, rax
0x18000a925  mov     r8, rbx; dwBytes
0x18000a928  mov     edx, edi; dwFlags
0x18000a92a  mov     rcx, rax; hHeap
0x18000a92d  call    cs:__imp_HeapAlloc
0x18000a933  mov     rbx, rax
0x18000a936  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000a93d  test    rax, rax
0x18000a940  jnz     short loc_18000A988
0x18000a942  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000a948  jnz     short loc_18000A993
0x18000a94a  lea     rcx, aNtdllDll; "ntdll.dll"
0x18000a951  call    cs:__imp_GetModuleHandleW
0x18000a957  test    rax, rax
0x18000a95a  jz      short loc_18000A975
0x18000a95c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000a963  mov     rcx, rax; hModule
0x18000a966  call    cs:__imp_GetProcAddress
0x18000a96c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000a973  jmp     short loc_18000A97C
0x18000a975  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000a97c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000a983  test    rax, rax
0x18000a986  jz      short loc_18000A993
0x18000a988  mov     rdx, rbx
0x18000a98b  mov     rcx, rsi
0x18000a98e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a993  mov     rax, rbx
0x18000a996  mov     rbx, [rsp+28h+arg_0]
0x18000a99b  mov     rsi, [rsp+28h+arg_8]
0x18000a9a0  add     rsp, 20h
0x18000a9a4  pop     rdi
0x18000a9a5  retn
```
