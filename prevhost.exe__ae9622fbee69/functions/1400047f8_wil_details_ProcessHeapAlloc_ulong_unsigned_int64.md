# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1400047f8`
- end: `0x140004896`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140002b44`
- `0x140003450`
- `0x140004de0`

## callees

- `0x1400047f8`
- `0x140006010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14000481d`
- `KERNEL32!HeapAlloc` at `0x14000481d`
- `KERNEL32!GetProcAddress` at `0x140004856`
- `KERNEL32!GetProcAddress` at `0x140004856`
- `KERNEL32!GetProcessHeap` at `0x14000480c`
- `KERNEL32!GetProcessHeap` at `0x14000480c`
- `KERNEL32!GetModuleHandleW` at `0x140004841`
- `KERNEL32!GetModuleHandleW` at `0x140004841`

## string_xrefs

- `0x14000483a`: `ntdll.dll`

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
0x1400047f8  mov     [rsp+arg_0], rbx
0x1400047fd  mov     [rsp+arg_8], rsi
0x140004802  push    rdi
0x140004803  sub     rsp, 20h
0x140004807  mov     rbx, rdx
0x14000480a  mov     edi, ecx
0x14000480c  call    cs:__imp_GetProcessHeap
0x140004812  mov     r8, rbx; dwBytes
0x140004815  mov     edx, edi; dwFlags
0x140004817  mov     rcx, rax; hHeap
0x14000481a  mov     rsi, rax
0x14000481d  call    cs:__imp_HeapAlloc
0x140004823  mov     rbx, rax
0x140004826  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000482d  test    rax, rax
0x140004830  jnz     short loc_140004878
0x140004832  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140004838  jnz     short loc_140004883
0x14000483a  lea     rcx, ModuleName; "ntdll.dll"
0x140004841  call    cs:__imp_GetModuleHandleW
0x140004847  test    rax, rax
0x14000484a  jz      short loc_140004865
0x14000484c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x140004853  mov     rcx, rax; hModule
0x140004856  call    cs:__imp_GetProcAddress
0x14000485c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140004863  jmp     short loc_14000486C
0x140004865  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000486c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140004873  test    rax, rax
0x140004876  jz      short loc_140004883
0x140004878  mov     rdx, rbx
0x14000487b  mov     rcx, rsi
0x14000487e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004883  mov     rsi, [rsp+28h+arg_8]
0x140004888  mov     rax, rbx
0x14000488b  mov     rbx, [rsp+28h+arg_0]
0x140004890  add     rsp, 20h
0x140004894  pop     rdi
0x140004895  retn
```
