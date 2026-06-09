# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180005e98`
- end: `0x180005f36`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000527c`
- `0x180005c98`
- `0x180006124`
- `0x180006260`
- `0x180010f04`
- `0x1800125d4`

## callees

- `0x180005e98`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005ef6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005ef6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005ee1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005ee1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005ebd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005ebd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005eac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005eac`

## string_xrefs

- `0x180005eda`: `ntdll.dll`

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
0x180005e98  mov     [rsp+arg_0], rbx
0x180005e9d  mov     [rsp+arg_8], rsi
0x180005ea2  push    rdi
0x180005ea3  sub     rsp, 20h
0x180005ea7  mov     rbx, rdx
0x180005eaa  mov     edi, ecx
0x180005eac  call    cs:__imp_GetProcessHeap
0x180005eb2  mov     r8, rbx; dwBytes
0x180005eb5  mov     edx, edi; dwFlags
0x180005eb7  mov     rcx, rax; hHeap
0x180005eba  mov     rsi, rax
0x180005ebd  call    cs:__imp_HeapAlloc
0x180005ec3  mov     rbx, rax
0x180005ec6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005ecd  test    rax, rax
0x180005ed0  jnz     short loc_180005F18
0x180005ed2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005ed8  jnz     short loc_180005F23
0x180005eda  lea     rcx, ModuleName; "ntdll.dll"
0x180005ee1  call    cs:__imp_GetModuleHandleW
0x180005ee7  test    rax, rax
0x180005eea  jz      short loc_180005F05
0x180005eec  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x180005ef3  mov     rcx, rax; hModule
0x180005ef6  call    cs:__imp_GetProcAddress
0x180005efc  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005f03  jmp     short loc_180005F0C
0x180005f05  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005f0c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005f13  test    rax, rax
0x180005f16  jz      short loc_180005F23
0x180005f18  mov     rdx, rbx
0x180005f1b  mov     rcx, rsi
0x180005f1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f23  mov     rsi, [rsp+28h+arg_8]
0x180005f28  mov     rax, rbx
0x180005f2b  mov     rbx, [rsp+28h+arg_0]
0x180005f30  add     rsp, 20h
0x180005f34  pop     rdi
0x180005f35  retn
```
