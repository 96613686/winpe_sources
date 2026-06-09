# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180026280`
- end: `0x18002631e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001f4f4`
- `0x180026068`
- `0x180026550`
- `0x1800268e8`
- `0x1800283dc`

## callees

- `0x180026280`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800262c9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800262c9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800262de`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800262de`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800262a5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800262a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026294`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026294`

## string_xrefs

- `0x1800262c2`: `ntdll.dll`

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
0x180026280  mov     [rsp+arg_0], rbx
0x180026285  mov     [rsp+arg_8], rsi
0x18002628a  push    rdi
0x18002628b  sub     rsp, 20h
0x18002628f  mov     rbx, rdx
0x180026292  mov     edi, ecx
0x180026294  call    cs:__imp_GetProcessHeap
0x18002629a  mov     rsi, rax
0x18002629d  mov     r8, rbx; dwBytes
0x1800262a0  mov     edx, edi; dwFlags
0x1800262a2  mov     rcx, rax; hHeap
0x1800262a5  call    cs:__imp_HeapAlloc
0x1800262ab  mov     rbx, rax
0x1800262ae  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800262b5  test    rax, rax
0x1800262b8  jnz     short loc_180026300
0x1800262ba  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800262c0  jnz     short loc_18002630B
0x1800262c2  lea     rcx, ModuleName; "ntdll.dll"
0x1800262c9  call    cs:__imp_GetModuleHandleW
0x1800262cf  test    rax, rax
0x1800262d2  jz      short loc_1800262ED
0x1800262d4  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x1800262db  mov     rcx, rax; hModule
0x1800262de  call    cs:__imp_GetProcAddress
0x1800262e4  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800262eb  jmp     short loc_1800262F4
0x1800262ed  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800262f4  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800262fb  test    rax, rax
0x1800262fe  jz      short loc_18002630B
0x180026300  mov     rdx, rbx
0x180026303  mov     rcx, rsi
0x180026306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002630b  mov     rax, rbx
0x18002630e  mov     rbx, [rsp+28h+arg_0]
0x180026313  mov     rsi, [rsp+28h+arg_8]
0x180026318  add     rsp, 20h
0x18002631c  pop     rdi
0x18002631d  retn
```
