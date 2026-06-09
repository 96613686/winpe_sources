# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140006e88`
- end: `0x140006f26`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140004668`
- `0x140004a0c`
- `0x140005ae0`
- `0x1400089e4`
- `0x14000a3ac`

## callees

- `0x140006e88`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006ed1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006ed1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006ee6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006ee6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006e9c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006e9c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140006ead`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140006ead`

## string_xrefs

- `0x140006eca`: `ntdll.dll`

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
0x140006e88  mov     [rsp+arg_0], rbx
0x140006e8d  mov     [rsp+arg_8], rsi
0x140006e92  push    rdi
0x140006e93  sub     rsp, 20h
0x140006e97  mov     rbx, rdx
0x140006e9a  mov     edi, ecx
0x140006e9c  call    cs:__imp_GetProcessHeap
0x140006ea2  mov     rsi, rax
0x140006ea5  mov     r8, rbx; dwBytes
0x140006ea8  mov     edx, edi; dwFlags
0x140006eaa  mov     rcx, rax; hHeap
0x140006ead  call    cs:__imp_HeapAlloc
0x140006eb3  mov     rbx, rax
0x140006eb6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140006ebd  test    rax, rax
0x140006ec0  jnz     short loc_140006F08
0x140006ec2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140006ec8  jnz     short loc_140006F13
0x140006eca  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x140006ed1  call    cs:__imp_GetModuleHandleW
0x140006ed7  test    rax, rax
0x140006eda  jz      short loc_140006EF5
0x140006edc  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x140006ee3  mov     rcx, rax; hModule
0x140006ee6  call    cs:__imp_GetProcAddress
0x140006eec  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140006ef3  jmp     short loc_140006EFC
0x140006ef5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140006efc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140006f03  test    rax, rax
0x140006f06  jz      short loc_140006F13
0x140006f08  mov     rdx, rbx
0x140006f0b  mov     rcx, rsi
0x140006f0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006f13  mov     rax, rbx
0x140006f16  mov     rbx, [rsp+28h+arg_0]
0x140006f1b  mov     rsi, [rsp+28h+arg_8]
0x140006f20  add     rsp, 20h
0x140006f24  pop     rdi
0x140006f25  retn
```
