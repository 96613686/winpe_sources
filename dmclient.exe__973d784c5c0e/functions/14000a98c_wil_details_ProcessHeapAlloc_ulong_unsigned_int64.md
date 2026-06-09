# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x14000a98c`
- end: `0x14000aa43`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140004ce4`
- `0x14000b5b4`
- `0x140015fb4`
- `0x14001898c`

## callees

- `0x14000a98c`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000a9fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000a9fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000a9e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000a9e1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000a9b7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000a9b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a9a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a9a0`

## string_xrefs

- `0x14000a9da`: `ntdll.dll`

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
0x14000a98c  mov     [rsp+arg_0], rbx
0x14000a991  mov     [rsp+arg_8], rsi
0x14000a996  push    rdi
0x14000a997  sub     rsp, 20h
0x14000a99b  mov     rbx, rdx
0x14000a99e  mov     edi, ecx
0x14000a9a0  call    cs:__imp_GetProcessHeap
0x14000a9a7  nop     dword ptr [rax+rax+00h]
0x14000a9ac  mov     rsi, rax
0x14000a9af  mov     r8, rbx; dwBytes
0x14000a9b2  mov     edx, edi; dwFlags
0x14000a9b4  mov     rcx, rax; hHeap
0x14000a9b7  call    cs:__imp_HeapAlloc
0x14000a9be  nop     dword ptr [rax+rax+00h]
0x14000a9c3  mov     rbx, rax
0x14000a9c6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000a9cd  test    rax, rax
0x14000a9d0  jnz     short loc_14000AA24
0x14000a9d2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000a9d8  jnz     short loc_14000AA2F
0x14000a9da  lea     rcx, ModuleName; "ntdll.dll"
0x14000a9e1  call    cs:__imp_GetModuleHandleW
0x14000a9e8  nop     dword ptr [rax+rax+00h]
0x14000a9ed  test    rax, rax
0x14000a9f0  jz      short loc_14000AA11
0x14000a9f2  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x14000a9f9  mov     rcx, rax; hModule
0x14000a9fc  call    cs:__imp_GetProcAddress
0x14000aa03  nop     dword ptr [rax+rax+00h]
0x14000aa08  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x14000aa0f  jmp     short loc_14000AA18
0x14000aa11  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000aa18  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000aa1f  test    rax, rax
0x14000aa22  jz      short loc_14000AA2F
0x14000aa24  mov     rdx, rbx
0x14000aa27  mov     rcx, rsi
0x14000aa2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aa2f  mov     rax, rbx
0x14000aa32  mov     rbx, [rsp+28h+arg_0]
0x14000aa37  mov     rsi, [rsp+28h+arg_8]
0x14000aa3c  add     rsp, 20h
0x14000aa40  pop     rdi
0x14000aa41  retn
```
