# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180021260`
- end: `0x1800212ff`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `159`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800117f8`
- `0x180020d6c`
- `0x180020e98`
- `0x180021c20`
- `0x1800220a4`

## callees

- `0x180021260`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800212a9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800212a9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800212be`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800212be`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180021285`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180021285`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021274`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021274`

## string_xrefs

- `0x1800212a2`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180021260  mov     [rsp+arg_0], rbx
0x180021265  mov     [rsp+arg_8], rsi
0x18002126a  push    rdi
0x18002126b  sub     rsp, 20h
0x18002126f  mov     rbx, rdx
0x180021272  mov     edi, ecx
0x180021274  call    cs:__imp_GetProcessHeap
0x18002127a  mov     rsi, rax
0x18002127d  mov     r8, rbx; dwBytes
0x180021280  mov     edx, edi; dwFlags
0x180021282  mov     rcx, rax; hHeap
0x180021285  call    cs:__imp_HeapAlloc
0x18002128b  mov     rbx, rax
0x18002128e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180021295  test    rax, rax
0x180021298  jnz     short loc_1800212E1
0x18002129a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800212a0  jnz     short loc_1800212EC
0x1800212a2  lea     rcx, ModuleName; "ntdll.dll"
0x1800212a9  call    cs:__imp_GetModuleHandleW
0x1800212af  test    rax, rax
0x1800212b2  jz      short loc_1800212CE
0x1800212b4  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x1800212bb  mov     rcx, rax; hModule
0x1800212be  call    cs:__imp_GetProcAddress
0x1800212c4  nop
0x1800212c5  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800212cc  jmp     short loc_1800212D5
0x1800212ce  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800212d5  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800212dc  test    rax, rax
0x1800212df  jz      short loc_1800212EC
0x1800212e1  mov     rdx, rbx
0x1800212e4  mov     rcx, rsi
0x1800212e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212ec  mov     rax, rbx
0x1800212ef  mov     rbx, [rsp+28h+arg_0]
0x1800212f4  mov     rsi, [rsp+28h+arg_8]
0x1800212f9  add     rsp, 20h
0x1800212fd  pop     rdi
0x1800212fe  retn
```
