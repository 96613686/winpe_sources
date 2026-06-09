# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x14000a74c`
- end: `0x14000a7ea`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140004bd0`
- `0x14000b288`
- `0x140013330`
- `0x140016bbc`

## callees

- `0x14000a74c`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000a7aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000a7aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000a795`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000a795`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000a771`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000a771`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a760`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a760`

## string_xrefs

- `0x14000a78e`: `ntdll.dll`

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
0x14000a74c  mov     [rsp+arg_0], rbx
0x14000a751  mov     [rsp+arg_8], rsi
0x14000a756  push    rdi
0x14000a757  sub     rsp, 20h
0x14000a75b  mov     rbx, rdx
0x14000a75e  mov     edi, ecx
0x14000a760  call    cs:__imp_GetProcessHeap
0x14000a766  mov     rsi, rax
0x14000a769  mov     r8, rbx; dwBytes
0x14000a76c  mov     edx, edi; dwFlags
0x14000a76e  mov     rcx, rax; hHeap
0x14000a771  call    cs:__imp_HeapAlloc
0x14000a777  mov     rbx, rax
0x14000a77a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000a781  test    rax, rax
0x14000a784  jnz     short loc_14000A7CC
0x14000a786  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000a78c  jnz     short loc_14000A7D7
0x14000a78e  lea     rcx, ModuleName; "ntdll.dll"
0x14000a795  call    cs:__imp_GetModuleHandleW
0x14000a79b  test    rax, rax
0x14000a79e  jz      short loc_14000A7B9
0x14000a7a0  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x14000a7a7  mov     rcx, rax; hModule
0x14000a7aa  call    cs:__imp_GetProcAddress
0x14000a7b0  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x14000a7b7  jmp     short loc_14000A7C0
0x14000a7b9  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000a7c0  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000a7c7  test    rax, rax
0x14000a7ca  jz      short loc_14000A7D7
0x14000a7cc  mov     rdx, rbx
0x14000a7cf  mov     rcx, rsi
0x14000a7d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a7d7  mov     rax, rbx
0x14000a7da  mov     rbx, [rsp+28h+arg_0]
0x14000a7df  mov     rsi, [rsp+28h+arg_8]
0x14000a7e4  add     rsp, 20h
0x14000a7e8  pop     rdi
0x14000a7e9  retn
```
