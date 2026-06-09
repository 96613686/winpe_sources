# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140007288`
- end: `0x140007326`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140003de0`
- `0x140007df8`

## callees

- `0x140007288`
- `0x140010010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400072d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400072d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400072e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400072e6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400072ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400072ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000729c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000729c`

## string_xrefs

- `0x1400072ca`: `ntdll.dll`

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
0x140007288  mov     [rsp+arg_0], rbx
0x14000728d  mov     [rsp+arg_8], rsi
0x140007292  push    rdi
0x140007293  sub     rsp, 20h
0x140007297  mov     rbx, rdx
0x14000729a  mov     edi, ecx
0x14000729c  call    cs:__imp_GetProcessHeap
0x1400072a2  mov     rsi, rax
0x1400072a5  mov     r8, rbx; dwBytes
0x1400072a8  mov     edx, edi; dwFlags
0x1400072aa  mov     rcx, rax; hHeap
0x1400072ad  call    cs:__imp_HeapAlloc
0x1400072b3  mov     rbx, rax
0x1400072b6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400072bd  test    rax, rax
0x1400072c0  jnz     short loc_140007308
0x1400072c2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400072c8  jnz     short loc_140007313
0x1400072ca  lea     rcx, ModuleName; "ntdll.dll"
0x1400072d1  call    cs:__imp_GetModuleHandleW
0x1400072d7  test    rax, rax
0x1400072da  jz      short loc_1400072F5
0x1400072dc  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1400072e3  mov     rcx, rax; hModule
0x1400072e6  call    cs:__imp_GetProcAddress
0x1400072ec  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1400072f3  jmp     short loc_1400072FC
0x1400072f5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400072fc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140007303  test    rax, rax
0x140007306  jz      short loc_140007313
0x140007308  mov     rdx, rbx
0x14000730b  mov     rcx, rsi
0x14000730e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007313  mov     rax, rbx
0x140007316  mov     rbx, [rsp+28h+arg_0]
0x14000731b  mov     rsi, [rsp+28h+arg_8]
0x140007320  add     rsp, 20h
0x140007324  pop     rdi
0x140007325  retn
```
