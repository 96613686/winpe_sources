# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000fd80`
- end: `0x18000fe28`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `168`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000af70`
- `0x18000b0d0`
- `0x180010cf8`
- `0x18001117c`
- `0x18001207c`

## callees

- `0x18000fd80`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fdd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fdd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fde8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fde8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fd9e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fd9e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fdaf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000fdaf`

## string_xrefs

- `0x18000fdcc`: `ntdll.dll`

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
0x18000fd80  push    rdi
0x18000fd82  sub     rsp, 30h
0x18000fd86  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000fd8f  mov     [rsp+38h+arg_0], rbx
0x18000fd94  mov     [rsp+38h+arg_8], rsi
0x18000fd99  mov     rbx, rdx
0x18000fd9c  mov     edi, ecx
0x18000fd9e  call    cs:__imp_GetProcessHeap
0x18000fda4  mov     rsi, rax
0x18000fda7  mov     r8, rbx; dwBytes
0x18000fdaa  mov     edx, edi; dwFlags
0x18000fdac  mov     rcx, rax; hHeap
0x18000fdaf  call    cs:__imp_HeapAlloc
0x18000fdb5  mov     rbx, rax
0x18000fdb8  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000fdbf  test    rax, rax
0x18000fdc2  jnz     short loc_18000FE0A
0x18000fdc4  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000fdca  jnz     short loc_18000FE15
0x18000fdcc  lea     rcx, ModuleName; "ntdll.dll"
0x18000fdd3  call    cs:__imp_GetModuleHandleW
0x18000fdd9  test    rax, rax
0x18000fddc  jz      short loc_18000FDF7
0x18000fdde  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000fde5  mov     rcx, rax; hModule
0x18000fde8  call    cs:__imp_GetProcAddress
0x18000fdee  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000fdf5  jmp     short loc_18000FDFE
0x18000fdf7  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000fdfe  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000fe05  test    rax, rax
0x18000fe08  jz      short loc_18000FE15
0x18000fe0a  mov     rdx, rbx
0x18000fe0d  mov     rcx, rsi
0x18000fe10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe15  mov     rax, rbx
0x18000fe18  mov     rbx, [rsp+38h+arg_0]
0x18000fe1d  mov     rsi, [rsp+38h+arg_8]
0x18000fe22  add     rsp, 30h
0x18000fe26  pop     rdi
0x18000fe27  retn
```
