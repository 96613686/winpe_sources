# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180007f04`
- end: `0x180007fa2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003354`
- `0x1800075a8`
- `0x1800076cc`
- `0x1800088a0`
- `0x180008d24`

## callees

- `0x180007f04`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007f29`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007f29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007f18`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007f18`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007f62`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007f62`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007f4d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007f4d`

## string_xrefs

- `0x180007f46`: `ntdll.dll`

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
0x180007f04  mov     [rsp+arg_0], rbx
0x180007f09  mov     [rsp+arg_8], rsi
0x180007f0e  push    rdi
0x180007f0f  sub     rsp, 20h
0x180007f13  mov     rbx, rdx
0x180007f16  mov     edi, ecx
0x180007f18  call    cs:__imp_GetProcessHeap
0x180007f1e  mov     rsi, rax
0x180007f21  mov     r8, rbx; dwBytes
0x180007f24  mov     edx, edi; dwFlags
0x180007f26  mov     rcx, rax; hHeap
0x180007f29  call    cs:__imp_HeapAlloc
0x180007f2f  mov     rbx, rax
0x180007f32  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007f39  test    rax, rax
0x180007f3c  jnz     short loc_180007F84
0x180007f3e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007f44  jnz     short loc_180007F8F
0x180007f46  lea     rcx, ModuleName; "ntdll.dll"
0x180007f4d  call    cs:__imp_GetModuleHandleW
0x180007f53  test    rax, rax
0x180007f56  jz      short loc_180007F71
0x180007f58  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x180007f5f  mov     rcx, rax; hModule
0x180007f62  call    cs:__imp_GetProcAddress
0x180007f68  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180007f6f  jmp     short loc_180007F78
0x180007f71  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007f78  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007f7f  test    rax, rax
0x180007f82  jz      short loc_180007F8F
0x180007f84  mov     rdx, rbx
0x180007f87  mov     rcx, rsi
0x180007f8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f8f  mov     rax, rbx
0x180007f92  mov     rbx, [rsp+28h+arg_0]
0x180007f97  mov     rsi, [rsp+28h+arg_8]
0x180007f9c  add     rsp, 20h
0x180007fa0  pop     rdi
0x180007fa1  retn
```
