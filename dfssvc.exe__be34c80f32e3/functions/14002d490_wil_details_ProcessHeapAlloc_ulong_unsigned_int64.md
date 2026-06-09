# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x14002d490`
- end: `0x14002d547`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14002ca60`
- `0x14002cb90`
- `0x14002f40c`
- `0x14002fab0`
- `0x140031de4`

## callees

- `0x14002d490`
- `0x14005e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14002d4bb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14002d4bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002d4a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002d4a4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14002d4e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14002d4e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14002d500`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14002d500`

## string_xrefs

- `0x14002d4de`: `ntdll.dll`

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
0x14002d490  mov     [rsp+arg_0], rbx
0x14002d495  mov     [rsp+arg_8], rsi
0x14002d49a  push    rdi
0x14002d49b  sub     rsp, 20h
0x14002d49f  mov     rbx, rdx
0x14002d4a2  mov     edi, ecx
0x14002d4a4  call    cs:__imp_GetProcessHeap
0x14002d4ab  nop     dword ptr [rax+rax+00h]
0x14002d4b0  mov     r8, rbx; dwBytes
0x14002d4b3  mov     edx, edi; dwFlags
0x14002d4b5  mov     rcx, rax; hHeap
0x14002d4b8  mov     rsi, rax
0x14002d4bb  call    cs:__imp_HeapAlloc
0x14002d4c2  nop     dword ptr [rax+rax+00h]
0x14002d4c7  mov     rbx, rax
0x14002d4ca  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14002d4d1  test    rax, rax
0x14002d4d4  jnz     short loc_14002D528
0x14002d4d6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14002d4dc  jnz     short loc_14002D533
0x14002d4de  lea     rcx, ModuleName; "ntdll.dll"
0x14002d4e5  call    cs:__imp_GetModuleHandleW
0x14002d4ec  nop     dword ptr [rax+rax+00h]
0x14002d4f1  test    rax, rax
0x14002d4f4  jz      short loc_14002D515
0x14002d4f6  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x14002d4fd  mov     rcx, rax; hModule
0x14002d500  call    cs:__imp_GetProcAddress
0x14002d507  nop     dword ptr [rax+rax+00h]
0x14002d50c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x14002d513  jmp     short loc_14002D51C
0x14002d515  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14002d51c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14002d523  test    rax, rax
0x14002d526  jz      short loc_14002D533
0x14002d528  mov     rdx, rbx
0x14002d52b  mov     rcx, rsi
0x14002d52e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d533  mov     rsi, [rsp+28h+arg_8]
0x14002d538  mov     rax, rbx
0x14002d53b  mov     rbx, [rsp+28h+arg_0]
0x14002d540  add     rsp, 20h
0x14002d544  pop     rdi
0x14002d545  retn
```
