# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180004588`
- end: `0x180004626`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002e48`
- `0x180003530`
- `0x180004a80`

## callees

- `0x180004588`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800045d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800045d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800045e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800045e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000459c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000459c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800045ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800045ad`

## string_xrefs

- `0x1800045ca`: `ntdll.dll`

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
0x180004588  mov     [rsp+arg_0], rbx
0x18000458d  mov     [rsp+arg_8], rsi
0x180004592  push    rdi
0x180004593  sub     rsp, 20h
0x180004597  mov     rbx, rdx
0x18000459a  mov     edi, ecx
0x18000459c  call    cs:__imp_GetProcessHeap
0x1800045a2  mov     rsi, rax
0x1800045a5  mov     r8, rbx; dwBytes
0x1800045a8  mov     edx, edi; dwFlags
0x1800045aa  mov     rcx, rax; hHeap
0x1800045ad  call    cs:__imp_HeapAlloc
0x1800045b3  mov     rbx, rax
0x1800045b6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800045bd  test    rax, rax
0x1800045c0  jnz     short loc_180004608
0x1800045c2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800045c8  jnz     short loc_180004613
0x1800045ca  lea     rcx, ModuleName; "ntdll.dll"
0x1800045d1  call    cs:__imp_GetModuleHandleW
0x1800045d7  test    rax, rax
0x1800045da  jz      short loc_1800045F5
0x1800045dc  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800045e3  mov     rcx, rax; hModule
0x1800045e6  call    cs:__imp_GetProcAddress
0x1800045ec  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800045f3  jmp     short loc_1800045FC
0x1800045f5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800045fc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004603  test    rax, rax
0x180004606  jz      short loc_180004613
0x180004608  mov     rdx, rbx
0x18000460b  mov     rcx, rsi
0x18000460e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004613  mov     rax, rbx
0x180004616  mov     rbx, [rsp+28h+arg_0]
0x18000461b  mov     rsi, [rsp+28h+arg_8]
0x180004620  add     rsp, 20h
0x180004624  pop     rdi
0x180004625  retn
```
