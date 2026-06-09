# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180008c0c`
- end: `0x180008caa`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008010`
- `0x180008600`
- `0x180008e7c`

## callees

- `0x180008c0c`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008c55`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008c55`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008c6a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008c6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008c20`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008c20`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008c31`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008c31`

## string_xrefs

- `0x180008c4e`: `ntdll.dll`

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
0x180008c0c  mov     [rsp+arg_0], rbx
0x180008c11  mov     [rsp+arg_8], rsi
0x180008c16  push    rdi
0x180008c17  sub     rsp, 20h
0x180008c1b  mov     rbx, rdx
0x180008c1e  mov     edi, ecx
0x180008c20  call    cs:__imp_GetProcessHeap
0x180008c26  mov     rsi, rax
0x180008c29  mov     r8, rbx; dwBytes
0x180008c2c  mov     edx, edi; dwFlags
0x180008c2e  mov     rcx, rax; hHeap
0x180008c31  call    cs:__imp_HeapAlloc
0x180008c37  mov     rbx, rax
0x180008c3a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008c41  test    rax, rax
0x180008c44  jnz     short loc_180008C8C
0x180008c46  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008c4c  jnz     short loc_180008C97
0x180008c4e  lea     rcx, ModuleName; "ntdll.dll"
0x180008c55  call    cs:__imp_GetModuleHandleW
0x180008c5b  test    rax, rax
0x180008c5e  jz      short loc_180008C79
0x180008c60  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180008c67  mov     rcx, rax; hModule
0x180008c6a  call    cs:__imp_GetProcAddress
0x180008c70  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180008c77  jmp     short loc_180008C80
0x180008c79  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008c80  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008c87  test    rax, rax
0x180008c8a  jz      short loc_180008C97
0x180008c8c  mov     rdx, rbx
0x180008c8f  mov     rcx, rsi
0x180008c92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c97  mov     rax, rbx
0x180008c9a  mov     rbx, [rsp+28h+arg_0]
0x180008c9f  mov     rsi, [rsp+28h+arg_8]
0x180008ca4  add     rsp, 20h
0x180008ca8  pop     rdi
0x180008ca9  retn
```
