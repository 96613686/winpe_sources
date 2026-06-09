# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000524c`
- end: `0x1800052f4`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `168`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003a68`
- `0x180004160`
- `0x180005650`

## callees

- `0x18000524c`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800052b4`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800052b4`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000529f`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000529f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000527b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000527b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000526a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000526a`

## string_xrefs

- `0x180005298`: `ntdll.dll`

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
0x18000524c  push    rdi
0x18000524e  sub     rsp, 30h
0x180005252  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000525b  mov     [rsp+38h+arg_0], rbx
0x180005260  mov     [rsp+38h+arg_8], rsi
0x180005265  mov     rbx, rdx
0x180005268  mov     edi, ecx
0x18000526a  call    cs:__imp_GetProcessHeap
0x180005270  mov     rsi, rax
0x180005273  mov     r8, rbx; dwBytes
0x180005276  mov     edx, edi; dwFlags
0x180005278  mov     rcx, rax; hHeap
0x18000527b  call    cs:__imp_HeapAlloc
0x180005281  mov     rbx, rax
0x180005284  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000528b  test    rax, rax
0x18000528e  jnz     short loc_1800052D6
0x180005290  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005296  jnz     short loc_1800052E1
0x180005298  lea     rcx, LibFileName; "ntdll.dll"
0x18000529f  call    cs:__imp_GetModuleHandleW
0x1800052a5  test    rax, rax
0x1800052a8  jz      short loc_1800052C3
0x1800052aa  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800052b1  mov     rcx, rax; hModule
0x1800052b4  call    cs:__imp_GetProcAddress
0x1800052ba  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800052c1  jmp     short loc_1800052CA
0x1800052c3  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800052ca  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800052d1  test    rax, rax
0x1800052d4  jz      short loc_1800052E1
0x1800052d6  mov     rdx, rbx
0x1800052d9  mov     rcx, rsi
0x1800052dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052e1  mov     rax, rbx
0x1800052e4  mov     rbx, [rsp+38h+arg_0]
0x1800052e9  mov     rsi, [rsp+38h+arg_8]
0x1800052ee  add     rsp, 30h
0x1800052f2  pop     rdi
0x1800052f3  retn
```
