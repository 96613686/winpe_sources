# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18005c850`
- end: `0x18005c8ee`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800512b4`
- `0x18005c36c`
- `0x18005c490`
- `0x18005d254`
- `0x18005d4b8`

## callees

- `0x18005c850`
- `0x180107010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005c8ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005c8ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005c899`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005c899`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005c875`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005c875`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005c864`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005c864`

## string_xrefs

- `0x18005c892`: `ntdll.dll`

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
0x18005c850  mov     [rsp+arg_0], rbx
0x18005c855  mov     [rsp+arg_8], rsi
0x18005c85a  push    rdi
0x18005c85b  sub     rsp, 20h
0x18005c85f  mov     rbx, rdx
0x18005c862  mov     edi, ecx
0x18005c864  call    cs:__imp_GetProcessHeap
0x18005c86a  mov     r8, rbx; dwBytes
0x18005c86d  mov     edx, edi; dwFlags
0x18005c86f  mov     rcx, rax; hHeap
0x18005c872  mov     rsi, rax
0x18005c875  call    cs:__imp_HeapAlloc
0x18005c87b  mov     rbx, rax
0x18005c87e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18005c885  test    rax, rax
0x18005c888  jnz     short loc_18005C8D0
0x18005c88a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18005c890  jnz     short loc_18005C8DB
0x18005c892  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18005c899  call    cs:__imp_GetModuleHandleW
0x18005c89f  test    rax, rax
0x18005c8a2  jz      short loc_18005C8BD
0x18005c8a4  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18005c8ab  mov     rcx, rax; hModule
0x18005c8ae  call    cs:__imp_GetProcAddress
0x18005c8b4  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18005c8bb  jmp     short loc_18005C8C4
0x18005c8bd  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18005c8c4  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18005c8cb  test    rax, rax
0x18005c8ce  jz      short loc_18005C8DB
0x18005c8d0  mov     rdx, rbx
0x18005c8d3  mov     rcx, rsi
0x18005c8d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c8db  mov     rsi, [rsp+28h+arg_8]
0x18005c8e0  mov     rax, rbx
0x18005c8e3  mov     rbx, [rsp+28h+arg_0]
0x18005c8e8  add     rsp, 20h
0x18005c8ec  pop     rdi
0x18005c8ed  retn
```
