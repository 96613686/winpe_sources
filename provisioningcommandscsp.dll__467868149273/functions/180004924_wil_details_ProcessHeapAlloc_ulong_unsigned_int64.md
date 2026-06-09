# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180004924`
- end: `0x1800049db`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800045a8`
- `0x18000539c`

## callees

- `0x180004924`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004979`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004979`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004994`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004994`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004938`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004938`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000494f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000494f`

## string_xrefs

- `0x180004972`: `ntdll.dll`

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
0x180004924  mov     [rsp+arg_0], rbx
0x180004929  mov     [rsp+arg_8], rsi
0x18000492e  push    rdi
0x18000492f  sub     rsp, 20h
0x180004933  mov     rbx, rdx
0x180004936  mov     edi, ecx
0x180004938  call    cs:__imp_GetProcessHeap
0x18000493f  nop     dword ptr [rax+rax+00h]
0x180004944  mov     rsi, rax
0x180004947  mov     r8, rbx; dwBytes
0x18000494a  mov     edx, edi; dwFlags
0x18000494c  mov     rcx, rax; hHeap
0x18000494f  call    cs:__imp_HeapAlloc
0x180004956  nop     dword ptr [rax+rax+00h]
0x18000495b  mov     rbx, rax
0x18000495e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180004965  test    rax, rax
0x180004968  jnz     short loc_1800049BC
0x18000496a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004970  jnz     short loc_1800049C7
0x180004972  lea     rcx, ModuleName; "ntdll.dll"
0x180004979  call    cs:__imp_GetModuleHandleW
0x180004980  nop     dword ptr [rax+rax+00h]
0x180004985  test    rax, rax
0x180004988  jz      short loc_1800049A9
0x18000498a  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180004991  mov     rcx, rax; hModule
0x180004994  call    cs:__imp_GetProcAddress
0x18000499b  nop     dword ptr [rax+rax+00h]
0x1800049a0  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800049a7  jmp     short loc_1800049B0
0x1800049a9  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800049b0  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800049b7  test    rax, rax
0x1800049ba  jz      short loc_1800049C7
0x1800049bc  mov     rdx, rbx
0x1800049bf  mov     rcx, rsi
0x1800049c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049c7  mov     rax, rbx
0x1800049ca  mov     rbx, [rsp+28h+arg_0]
0x1800049cf  mov     rsi, [rsp+28h+arg_8]
0x1800049d4  add     rsp, 20h
0x1800049d8  pop     rdi
0x1800049d9  retn
```
