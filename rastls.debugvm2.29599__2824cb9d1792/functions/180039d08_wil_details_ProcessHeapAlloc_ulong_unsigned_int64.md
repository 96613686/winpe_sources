# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180039d08`
- end: `0x180039da6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002a164`
- `0x18003980c`
- `0x18003993c`
- `0x18003a6c0`
- `0x18003ab50`

## callees

- `0x180039d08`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180039d51`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180039d51`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180039d66`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180039d66`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039d1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039d1c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039d2d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039d2d`

## string_xrefs

- `0x180039d4a`: `ntdll.dll`

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
0x180039d08  mov     [rsp+arg_0], rbx
0x180039d0d  mov     [rsp+arg_8], rsi
0x180039d12  push    rdi
0x180039d13  sub     rsp, 20h
0x180039d17  mov     rbx, rdx
0x180039d1a  mov     edi, ecx
0x180039d1c  call    cs:__imp_GetProcessHeap
0x180039d22  mov     rsi, rax
0x180039d25  mov     r8, rbx; dwBytes
0x180039d28  mov     edx, edi; dwFlags
0x180039d2a  mov     rcx, rax; hHeap
0x180039d2d  call    cs:__imp_HeapAlloc
0x180039d33  mov     rbx, rax
0x180039d36  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180039d3d  test    rax, rax
0x180039d40  jnz     short loc_180039D88
0x180039d42  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180039d48  jnz     short loc_180039D93
0x180039d4a  lea     rcx, ModuleName; "ntdll.dll"
0x180039d51  call    cs:__imp_GetModuleHandleW
0x180039d57  test    rax, rax
0x180039d5a  jz      short loc_180039D75
0x180039d5c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180039d63  mov     rcx, rax; hModule
0x180039d66  call    cs:__imp_GetProcAddress
0x180039d6c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180039d73  jmp     short loc_180039D7C
0x180039d75  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180039d7c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180039d83  test    rax, rax
0x180039d86  jz      short loc_180039D93
0x180039d88  mov     rdx, rbx
0x180039d8b  mov     rcx, rsi
0x180039d8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039d93  mov     rax, rbx
0x180039d96  mov     rbx, [rsp+28h+arg_0]
0x180039d9b  mov     rsi, [rsp+28h+arg_8]
0x180039da0  add     rsp, 20h
0x180039da4  pop     rdi
0x180039da5  retn
```
