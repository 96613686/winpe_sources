# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000a7f8`
- end: `0x18000a896`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000870c`
- `0x180008ab0`
- `0x180009690`
- `0x18000bb88`
- `0x18000cacc`

## callees

- `0x18000a7f8`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a841`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a841`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a856`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a856`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a81d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a81d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a80c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a80c`

## string_xrefs

- `0x18000a83a`: `ntdll.dll`

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
0x18000a7f8  mov     [rsp+arg_0], rbx
0x18000a7fd  mov     [rsp+arg_8], rsi
0x18000a802  push    rdi
0x18000a803  sub     rsp, 20h
0x18000a807  mov     rbx, rdx
0x18000a80a  mov     edi, ecx
0x18000a80c  call    cs:__imp_GetProcessHeap
0x18000a812  mov     r8, rbx; dwBytes
0x18000a815  mov     edx, edi; dwFlags
0x18000a817  mov     rcx, rax; hHeap
0x18000a81a  mov     rsi, rax
0x18000a81d  call    cs:__imp_HeapAlloc
0x18000a823  mov     rbx, rax
0x18000a826  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000a82d  test    rax, rax
0x18000a830  jnz     short loc_18000A878
0x18000a832  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000a838  jnz     short loc_18000A883
0x18000a83a  lea     rcx, ModuleName; "ntdll.dll"
0x18000a841  call    cs:__imp_GetModuleHandleW
0x18000a847  test    rax, rax
0x18000a84a  jz      short loc_18000A865
0x18000a84c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000a853  mov     rcx, rax; hModule
0x18000a856  call    cs:__imp_GetProcAddress
0x18000a85c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000a863  jmp     short loc_18000A86C
0x18000a865  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000a86c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000a873  test    rax, rax
0x18000a876  jz      short loc_18000A883
0x18000a878  mov     rdx, rbx
0x18000a87b  mov     rcx, rsi
0x18000a87e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a883  mov     rsi, [rsp+28h+arg_8]
0x18000a888  mov     rax, rbx
0x18000a88b  mov     rbx, [rsp+28h+arg_0]
0x18000a890  add     rsp, 20h
0x18000a894  pop     rdi
0x18000a895  retn
```
