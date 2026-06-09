# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x14000a910`
- end: `0x14000a9ae`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140007368`
- `0x140007738`
- `0x140008e70`
- `0x1400096cc`
- `0x14000ca04`
- `0x140010580`

## callees

- `0x14000a910`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000a96e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000a96e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000a959`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000a959`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a924`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a924`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000a935`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000a935`

## string_xrefs

- `0x14000a952`: `ntdll.dll`

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
0x14000a910  mov     [rsp+arg_0], rbx
0x14000a915  mov     [rsp+arg_8], rsi
0x14000a91a  push    rdi
0x14000a91b  sub     rsp, 20h
0x14000a91f  mov     rbx, rdx
0x14000a922  mov     edi, ecx
0x14000a924  call    cs:__imp_GetProcessHeap
0x14000a92a  mov     rsi, rax
0x14000a92d  mov     r8, rbx; dwBytes
0x14000a930  mov     edx, edi; dwFlags
0x14000a932  mov     rcx, rax; hHeap
0x14000a935  call    cs:__imp_HeapAlloc
0x14000a93b  mov     rbx, rax
0x14000a93e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000a945  test    rax, rax
0x14000a948  jnz     short loc_14000A990
0x14000a94a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000a950  jnz     short loc_14000A99B
0x14000a952  lea     rcx, ModuleName; "ntdll.dll"
0x14000a959  call    cs:__imp_GetModuleHandleW
0x14000a95f  test    rax, rax
0x14000a962  jz      short loc_14000A97D
0x14000a964  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x14000a96b  mov     rcx, rax; hModule
0x14000a96e  call    cs:__imp_GetProcAddress
0x14000a974  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x14000a97b  jmp     short loc_14000A984
0x14000a97d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000a984  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000a98b  test    rax, rax
0x14000a98e  jz      short loc_14000A99B
0x14000a990  mov     rdx, rbx
0x14000a993  mov     rcx, rsi
0x14000a996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a99b  mov     rax, rbx
0x14000a99e  mov     rbx, [rsp+28h+arg_0]
0x14000a9a3  mov     rsi, [rsp+28h+arg_8]
0x14000a9a8  add     rsp, 20h
0x14000a9ac  pop     rdi
0x14000a9ad  retn
```
