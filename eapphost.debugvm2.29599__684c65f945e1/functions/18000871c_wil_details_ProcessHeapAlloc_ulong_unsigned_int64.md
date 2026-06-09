# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000871c`
- end: `0x1800087ba`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008448`
- `0x180008b50`
- `0x180008ee8`
- `0x18000bb04`
- `0x18000d6a0`

## callees

- `0x18000871c`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008730`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008730`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008741`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008741`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008765`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008765`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000877a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000877a`

## string_xrefs

- `0x18000875e`: `ntdll.dll`

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
0x18000871c  mov     [rsp+arg_0], rbx
0x180008721  mov     [rsp+arg_8], rsi
0x180008726  push    rdi
0x180008727  sub     rsp, 20h
0x18000872b  mov     rbx, rdx
0x18000872e  mov     edi, ecx
0x180008730  call    cs:__imp_GetProcessHeap
0x180008736  mov     rsi, rax
0x180008739  mov     r8, rbx; dwBytes
0x18000873c  mov     edx, edi; dwFlags
0x18000873e  mov     rcx, rax; hHeap
0x180008741  call    cs:__imp_HeapAlloc
0x180008747  mov     rbx, rax
0x18000874a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008751  test    rax, rax
0x180008754  jnz     short loc_18000879C
0x180008756  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000875c  jnz     short loc_1800087A7
0x18000875e  lea     rcx, ModuleName; "ntdll.dll"
0x180008765  call    cs:__imp_GetModuleHandleW
0x18000876b  test    rax, rax
0x18000876e  jz      short loc_180008789
0x180008770  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x180008777  mov     rcx, rax; hModule
0x18000877a  call    cs:__imp_GetProcAddress
0x180008780  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180008787  jmp     short loc_180008790
0x180008789  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008790  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008797  test    rax, rax
0x18000879a  jz      short loc_1800087A7
0x18000879c  mov     rdx, rbx
0x18000879f  mov     rcx, rsi
0x1800087a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087a7  mov     rax, rbx
0x1800087aa  mov     rbx, [rsp+28h+arg_0]
0x1800087af  mov     rsi, [rsp+28h+arg_8]
0x1800087b4  add     rsp, 20h
0x1800087b8  pop     rdi
0x1800087b9  retn
```
