# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180005910`
- end: `0x1800059c7`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800037f4`
- `0x180003ba0`
- `0x1800046d0`
- `0x180006db8`
- `0x180007f3c`

## callees

- `0x180005910`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000593b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000593b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005924`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005924`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005980`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005980`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005965`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005965`

## string_xrefs

- `0x18000595e`: `ntdll.dll`

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
0x180005910  mov     [rsp+arg_0], rbx
0x180005915  mov     [rsp+arg_8], rsi
0x18000591a  push    rdi
0x18000591b  sub     rsp, 20h
0x18000591f  mov     rbx, rdx
0x180005922  mov     edi, ecx
0x180005924  call    cs:__imp_GetProcessHeap
0x18000592b  nop     dword ptr [rax+rax+00h]
0x180005930  mov     r8, rbx; dwBytes
0x180005933  mov     edx, edi; dwFlags
0x180005935  mov     rcx, rax; hHeap
0x180005938  mov     rsi, rax
0x18000593b  call    cs:__imp_HeapAlloc
0x180005942  nop     dword ptr [rax+rax+00h]
0x180005947  mov     rbx, rax
0x18000594a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005951  test    rax, rax
0x180005954  jnz     short loc_1800059A8
0x180005956  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000595c  jnz     short loc_1800059B3
0x18000595e  lea     rcx, ModuleName; "ntdll.dll"
0x180005965  call    cs:__imp_GetModuleHandleW
0x18000596c  nop     dword ptr [rax+rax+00h]
0x180005971  test    rax, rax
0x180005974  jz      short loc_180005995
0x180005976  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000597d  mov     rcx, rax; hModule
0x180005980  call    cs:__imp_GetProcAddress
0x180005987  nop     dword ptr [rax+rax+00h]
0x18000598c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005993  jmp     short loc_18000599C
0x180005995  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000599c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800059a3  test    rax, rax
0x1800059a6  jz      short loc_1800059B3
0x1800059a8  mov     rdx, rbx
0x1800059ab  mov     rcx, rsi
0x1800059ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059b3  mov     rsi, [rsp+28h+arg_8]
0x1800059b8  mov     rax, rbx
0x1800059bb  mov     rbx, [rsp+28h+arg_0]
0x1800059c0  add     rsp, 20h
0x1800059c4  pop     rdi
0x1800059c5  retn
```
