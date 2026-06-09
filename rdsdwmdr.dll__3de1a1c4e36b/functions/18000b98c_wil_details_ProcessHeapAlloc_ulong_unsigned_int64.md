# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000b98c`
- end: `0x18000ba2a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a7c8`
- `0x18000c234`
- `0x18000c3ac`

## callees

- `0x18000b98c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b9a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b9a0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b9b1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b9b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b9ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b9ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b9d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b9d5`

## string_xrefs

- `0x18000b9ce`: `ntdll.dll`

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
0x18000b98c  mov     [rsp+arg_0], rbx
0x18000b991  mov     [rsp+arg_8], rsi
0x18000b996  push    rdi
0x18000b997  sub     rsp, 20h
0x18000b99b  mov     rbx, rdx
0x18000b99e  mov     edi, ecx
0x18000b9a0  call    cs:__imp_GetProcessHeap
0x18000b9a6  mov     r8, rbx; dwBytes
0x18000b9a9  mov     edx, edi; dwFlags
0x18000b9ab  mov     rcx, rax; hHeap
0x18000b9ae  mov     rsi, rax
0x18000b9b1  call    cs:__imp_HeapAlloc
0x18000b9b7  mov     rbx, rax
0x18000b9ba  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000b9c1  test    rax, rax
0x18000b9c4  jnz     short loc_18000BA0C
0x18000b9c6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000b9cc  jnz     short loc_18000BA17
0x18000b9ce  lea     rcx, ModuleName; "ntdll.dll"
0x18000b9d5  call    cs:__imp_GetModuleHandleW
0x18000b9db  test    rax, rax
0x18000b9de  jz      short loc_18000B9F9
0x18000b9e0  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x18000b9e7  mov     rcx, rax; hModule
0x18000b9ea  call    cs:__imp_GetProcAddress
0x18000b9f0  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000b9f7  jmp     short loc_18000BA00
0x18000b9f9  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000ba00  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000ba07  test    rax, rax
0x18000ba0a  jz      short loc_18000BA17
0x18000ba0c  mov     rdx, rbx
0x18000ba0f  mov     rcx, rsi
0x18000ba12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba17  mov     rsi, [rsp+28h+arg_8]
0x18000ba1c  mov     rax, rbx
0x18000ba1f  mov     rbx, [rsp+28h+arg_0]
0x18000ba24  add     rsp, 20h
0x18000ba28  pop     rdi
0x18000ba29  retn
```
