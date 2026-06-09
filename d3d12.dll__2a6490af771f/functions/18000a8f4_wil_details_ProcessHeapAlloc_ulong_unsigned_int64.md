# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000a8f4`
- end: `0x18000a992`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a9b8`
- `0x18000d32c`
- `0x18000d450`
- `0x18000d8e0`
- `0x18000dc78`

## callees

- `0x18000a8f4`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a93d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a93d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a952`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a952`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a919`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a919`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a908`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a908`

## string_xrefs

- `0x18000a936`: `ntdll.dll`

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
0x18000a8f4  mov     [rsp+arg_0], rbx
0x18000a8f9  mov     [rsp+arg_8], rsi
0x18000a8fe  push    rdi
0x18000a8ff  sub     rsp, 20h
0x18000a903  mov     rbx, rdx
0x18000a906  mov     edi, ecx
0x18000a908  call    cs:__imp_GetProcessHeap
0x18000a90e  mov     rsi, rax
0x18000a911  mov     r8, rbx; dwBytes
0x18000a914  mov     edx, edi; dwFlags
0x18000a916  mov     rcx, rax; hHeap
0x18000a919  call    cs:__imp_HeapAlloc
0x18000a91f  mov     rbx, rax
0x18000a922  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000a929  test    rax, rax
0x18000a92c  jnz     short loc_18000A974
0x18000a92e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000a934  jnz     short loc_18000A97F
0x18000a936  lea     rcx, ModuleName; "ntdll.dll"
0x18000a93d  call    cs:__imp_GetModuleHandleW
0x18000a943  test    rax, rax
0x18000a946  jz      short loc_18000A961
0x18000a948  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000a94f  mov     rcx, rax; hModule
0x18000a952  call    cs:__imp_GetProcAddress
0x18000a958  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000a95f  jmp     short loc_18000A968
0x18000a961  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000a968  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000a96f  test    rax, rax
0x18000a972  jz      short loc_18000A97F
0x18000a974  mov     rdx, rbx
0x18000a977  mov     rcx, rsi
0x18000a97a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a97f  mov     rax, rbx
0x18000a982  mov     rbx, [rsp+28h+arg_0]
0x18000a987  mov     rsi, [rsp+28h+arg_8]
0x18000a98c  add     rsp, 20h
0x18000a990  pop     rdi
0x18000a991  retn
```
