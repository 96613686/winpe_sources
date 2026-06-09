# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180039a68`
- end: `0x180039b07`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `159`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002d708`
- `0x180039640`
- `0x18003976c`
- `0x18003a490`
- `0x18003a914`

## callees

- `0x180039a68`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180039ab1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180039ab1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180039ac6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180039ac6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039a8d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039a8d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039a7c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039a7c`

## string_xrefs

- `0x180039aaa`: `ntdll.dll`

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
0x180039a68  mov     [rsp+arg_0], rbx
0x180039a6d  mov     [rsp+arg_8], rsi
0x180039a72  push    rdi
0x180039a73  sub     rsp, 20h
0x180039a77  mov     rbx, rdx
0x180039a7a  mov     edi, ecx
0x180039a7c  call    cs:__imp_GetProcessHeap
0x180039a82  mov     rsi, rax
0x180039a85  mov     r8, rbx; dwBytes
0x180039a88  mov     edx, edi; dwFlags
0x180039a8a  mov     rcx, rax; hHeap
0x180039a8d  call    cs:__imp_HeapAlloc
0x180039a93  mov     rbx, rax
0x180039a96  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180039a9d  test    rax, rax
0x180039aa0  jnz     short loc_180039AE9
0x180039aa2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180039aa8  jnz     short loc_180039AF4
0x180039aaa  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180039ab1  call    cs:__imp_GetModuleHandleW
0x180039ab7  test    rax, rax
0x180039aba  jz      short loc_180039AD6
0x180039abc  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180039ac3  mov     rcx, rax; hModule
0x180039ac6  call    cs:__imp_GetProcAddress
0x180039acc  nop
0x180039acd  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180039ad4  jmp     short loc_180039ADD
0x180039ad6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180039add  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180039ae4  test    rax, rax
0x180039ae7  jz      short loc_180039AF4
0x180039ae9  mov     rdx, rbx
0x180039aec  mov     rcx, rsi
0x180039aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039af4  mov     rax, rbx
0x180039af7  mov     rbx, [rsp+28h+arg_0]
0x180039afc  mov     rsi, [rsp+28h+arg_8]
0x180039b01  add     rsp, 20h
0x180039b05  pop     rdi
0x180039b06  retn
```
