# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180012bf0`
- end: `0x180012ca8`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `184`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b1b0`
- `0x18000e640`
- `0x180013eb0`

## callees

- `0x180012bf0`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012c45`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012c45`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012c60`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012c60`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012c04`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012c04`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012c1b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012c1b`

## string_xrefs

- `0x180012c3e`: `ntdll.dll`

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
0x180012bf0  mov     [rsp+arg_0], rbx
0x180012bf5  mov     [rsp+arg_8], rsi
0x180012bfa  push    rdi
0x180012bfb  sub     rsp, 20h
0x180012bff  mov     rbx, rdx
0x180012c02  mov     edi, ecx
0x180012c04  call    cs:__imp_GetProcessHeap
0x180012c0b  nop     dword ptr [rax+rax+00h]
0x180012c10  mov     rsi, rax
0x180012c13  mov     r8, rbx; dwBytes
0x180012c16  mov     edx, edi; dwFlags
0x180012c18  mov     rcx, rax; hHeap
0x180012c1b  call    cs:__imp_HeapAlloc
0x180012c22  nop     dword ptr [rax+rax+00h]
0x180012c27  mov     rbx, rax
0x180012c2a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180012c31  test    rax, rax
0x180012c34  jnz     short loc_180012C88
0x180012c36  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180012c3c  jnz     short loc_180012C94
0x180012c3e  lea     rcx, ModuleName; "ntdll.dll"
0x180012c45  call    cs:__imp_GetModuleHandleW
0x180012c4c  nop     dword ptr [rax+rax+00h]
0x180012c51  test    rax, rax
0x180012c54  jz      short loc_180012C75
0x180012c56  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180012c5d  mov     rcx, rax; hModule
0x180012c60  call    cs:__imp_GetProcAddress
0x180012c67  nop     dword ptr [rax+rax+00h]
0x180012c6c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180012c73  jmp     short loc_180012C7C
0x180012c75  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180012c7c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180012c83  test    rax, rax
0x180012c86  jz      short loc_180012C94
0x180012c88  mov     rdx, rbx
0x180012c8b  mov     rcx, rsi
0x180012c8e  call    cs:__guard_dispatch_icall_fptr
0x180012c94  mov     rax, rbx
0x180012c97  mov     rbx, [rsp+28h+arg_0]
0x180012c9c  mov     rsi, [rsp+28h+arg_8]
0x180012ca1  add     rsp, 20h
0x180012ca5  pop     rdi
0x180012ca6  retn
```
