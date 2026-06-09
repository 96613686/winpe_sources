# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180005468`
- end: `0x180005506`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003d40`
- `0x180005bb8`
- `0x180007e80`
- `0x1800124ac`

## callees

- `0x180005468`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800054b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800054b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800054c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800054c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000547c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000547c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000548d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000548d`

## string_xrefs

- `0x1800054aa`: `ntdll.dll`

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
0x180005468  mov     [rsp+arg_0], rbx
0x18000546d  mov     [rsp+arg_8], rsi
0x180005472  push    rdi
0x180005473  sub     rsp, 20h
0x180005477  mov     rbx, rdx
0x18000547a  mov     edi, ecx
0x18000547c  call    cs:__imp_GetProcessHeap
0x180005482  mov     rsi, rax
0x180005485  mov     r8, rbx; dwBytes
0x180005488  mov     edx, edi; dwFlags
0x18000548a  mov     rcx, rax; hHeap
0x18000548d  call    cs:__imp_HeapAlloc
0x180005493  mov     rbx, rax
0x180005496  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000549d  test    rax, rax
0x1800054a0  jnz     short loc_1800054E8
0x1800054a2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800054a8  jnz     short loc_1800054F3
0x1800054aa  lea     rcx, ModuleName; "ntdll.dll"
0x1800054b1  call    cs:__imp_GetModuleHandleW
0x1800054b7  test    rax, rax
0x1800054ba  jz      short loc_1800054D5
0x1800054bc  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800054c3  mov     rcx, rax; hModule
0x1800054c6  call    cs:__imp_GetProcAddress
0x1800054cc  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800054d3  jmp     short loc_1800054DC
0x1800054d5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800054dc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800054e3  test    rax, rax
0x1800054e6  jz      short loc_1800054F3
0x1800054e8  mov     rdx, rbx
0x1800054eb  mov     rcx, rsi
0x1800054ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054f3  mov     rax, rbx
0x1800054f6  mov     rbx, [rsp+28h+arg_0]
0x1800054fb  mov     rsi, [rsp+28h+arg_8]
0x180005500  add     rsp, 20h
0x180005504  pop     rdi
0x180005505  retn
```
