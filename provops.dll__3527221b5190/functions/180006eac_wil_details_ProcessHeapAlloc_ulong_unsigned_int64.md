# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180006eac`
- end: `0x180006f4a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005480`
- `0x180006340`
- `0x180007b68`
- `0x18000f4c8`
- `0x180021370`

## callees

- `0x180006eac`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006ef5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006ef5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006f0a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006f0a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006ed1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006ed1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006ec0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006ec0`

## string_xrefs

- `0x180006eee`: `ntdll.dll`

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
0x180006eac  mov     [rsp+arg_0], rbx
0x180006eb1  mov     [rsp+arg_8], rsi
0x180006eb6  push    rdi
0x180006eb7  sub     rsp, 20h
0x180006ebb  mov     rbx, rdx
0x180006ebe  mov     edi, ecx
0x180006ec0  call    cs:__imp_GetProcessHeap
0x180006ec6  mov     rsi, rax
0x180006ec9  mov     r8, rbx; dwBytes
0x180006ecc  mov     edx, edi; dwFlags
0x180006ece  mov     rcx, rax; hHeap
0x180006ed1  call    cs:__imp_HeapAlloc
0x180006ed7  mov     rbx, rax
0x180006eda  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180006ee1  test    rax, rax
0x180006ee4  jnz     short loc_180006F2C
0x180006ee6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006eec  jnz     short loc_180006F37
0x180006eee  lea     rcx, ModuleName; "ntdll.dll"
0x180006ef5  call    cs:__imp_GetModuleHandleW
0x180006efb  test    rax, rax
0x180006efe  jz      short loc_180006F19
0x180006f00  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180006f07  mov     rcx, rax; hModule
0x180006f0a  call    cs:__imp_GetProcAddress
0x180006f10  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180006f17  jmp     short loc_180006F20
0x180006f19  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180006f20  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180006f27  test    rax, rax
0x180006f2a  jz      short loc_180006F37
0x180006f2c  mov     rdx, rbx
0x180006f2f  mov     rcx, rsi
0x180006f32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f37  mov     rax, rbx
0x180006f3a  mov     rbx, [rsp+28h+arg_0]
0x180006f3f  mov     rsi, [rsp+28h+arg_8]
0x180006f44  add     rsp, 20h
0x180006f48  pop     rdi
0x180006f49  retn
```
