# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180005ba8`
- end: `0x180005c46`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004efc`
- `0x180005924`
- `0x180006070`
- `0x180006408`

## callees

- `0x180005ba8`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005c06`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005c06`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005bf1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005bf1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005bbc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005bbc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005bcd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005bcd`

## string_xrefs

- `0x180005bea`: `ntdll.dll`

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
0x180005ba8  mov     [rsp+arg_0], rbx
0x180005bad  mov     [rsp+arg_8], rsi
0x180005bb2  push    rdi
0x180005bb3  sub     rsp, 20h
0x180005bb7  mov     rbx, rdx
0x180005bba  mov     edi, ecx
0x180005bbc  call    cs:__imp_GetProcessHeap
0x180005bc2  mov     rsi, rax
0x180005bc5  mov     r8, rbx; dwBytes
0x180005bc8  mov     edx, edi; dwFlags
0x180005bca  mov     rcx, rax; hHeap
0x180005bcd  call    cs:__imp_HeapAlloc
0x180005bd3  mov     rbx, rax
0x180005bd6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005bdd  test    rax, rax
0x180005be0  jnz     short loc_180005C28
0x180005be2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005be8  jnz     short loc_180005C33
0x180005bea  lea     rcx, ModuleName; "ntdll.dll"
0x180005bf1  call    cs:__imp_GetModuleHandleW
0x180005bf7  test    rax, rax
0x180005bfa  jz      short loc_180005C15
0x180005bfc  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x180005c03  mov     rcx, rax; hModule
0x180005c06  call    cs:__imp_GetProcAddress
0x180005c0c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005c13  jmp     short loc_180005C1C
0x180005c15  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005c1c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005c23  test    rax, rax
0x180005c26  jz      short loc_180005C33
0x180005c28  mov     rdx, rbx
0x180005c2b  mov     rcx, rsi
0x180005c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c33  mov     rax, rbx
0x180005c36  mov     rbx, [rsp+28h+arg_0]
0x180005c3b  mov     rsi, [rsp+28h+arg_8]
0x180005c40  add     rsp, 20h
0x180005c44  pop     rdi
0x180005c45  retn
```
