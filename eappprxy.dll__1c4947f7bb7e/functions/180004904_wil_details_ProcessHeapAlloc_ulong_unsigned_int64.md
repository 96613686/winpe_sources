# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180004904`
- end: `0x1800049bb`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800045a0`
- `0x180005138`

## callees

- `0x180004904`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004918`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004918`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000492f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000492f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004974`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004974`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004959`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004959`

## string_xrefs

- `0x180004952`: `ntdll.dll`

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
0x180004904  mov     [rsp+arg_0], rbx
0x180004909  mov     [rsp+arg_8], rsi
0x18000490e  push    rdi
0x18000490f  sub     rsp, 20h
0x180004913  mov     rbx, rdx
0x180004916  mov     edi, ecx
0x180004918  call    cs:__imp_GetProcessHeap
0x18000491f  nop     dword ptr [rax+rax+00h]
0x180004924  mov     rsi, rax
0x180004927  mov     r8, rbx; dwBytes
0x18000492a  mov     edx, edi; dwFlags
0x18000492c  mov     rcx, rax; hHeap
0x18000492f  call    cs:__imp_HeapAlloc
0x180004936  nop     dword ptr [rax+rax+00h]
0x18000493b  mov     rbx, rax
0x18000493e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180004945  test    rax, rax
0x180004948  jnz     short loc_18000499C
0x18000494a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004950  jnz     short loc_1800049A7
0x180004952  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180004959  call    cs:__imp_GetModuleHandleW
0x180004960  nop     dword ptr [rax+rax+00h]
0x180004965  test    rax, rax
0x180004968  jz      short loc_180004989
0x18000496a  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180004971  mov     rcx, rax; hModule
0x180004974  call    cs:__imp_GetProcAddress
0x18000497b  nop     dword ptr [rax+rax+00h]
0x180004980  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180004987  jmp     short loc_180004990
0x180004989  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180004990  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004997  test    rax, rax
0x18000499a  jz      short loc_1800049A7
0x18000499c  mov     rdx, rbx
0x18000499f  mov     rcx, rsi
0x1800049a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049a7  mov     rax, rbx
0x1800049aa  mov     rbx, [rsp+28h+arg_0]
0x1800049af  mov     rsi, [rsp+28h+arg_8]
0x1800049b4  add     rsp, 20h
0x1800049b8  pop     rdi
0x1800049b9  retn
```
