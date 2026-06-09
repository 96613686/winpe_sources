# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800080d8`
- end: `0x18000818f`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005a1c`
- `0x180005df8`
- `0x1800070e0`
- `0x18000a29c`
- `0x18000b7a8`

## callees

- `0x1800080d8`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008148`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008148`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000812d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000812d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008103`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008103`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800080ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800080ec`

## string_xrefs

- `0x180008126`: `ntdll.dll`

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
0x1800080d8  mov     [rsp+arg_0], rbx
0x1800080dd  mov     [rsp+arg_8], rsi
0x1800080e2  push    rdi
0x1800080e3  sub     rsp, 20h
0x1800080e7  mov     rbx, rdx
0x1800080ea  mov     edi, ecx
0x1800080ec  call    cs:__imp_GetProcessHeap
0x1800080f3  nop     dword ptr [rax+rax+00h]
0x1800080f8  mov     rsi, rax
0x1800080fb  mov     r8, rbx; dwBytes
0x1800080fe  mov     edx, edi; dwFlags
0x180008100  mov     rcx, rax; hHeap
0x180008103  call    cs:__imp_HeapAlloc
0x18000810a  nop     dword ptr [rax+rax+00h]
0x18000810f  mov     rbx, rax
0x180008112  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008119  test    rax, rax
0x18000811c  jnz     short loc_180008170
0x18000811e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008124  jnz     short loc_18000817B
0x180008126  lea     rcx, ModuleName; "ntdll.dll"
0x18000812d  call    cs:__imp_GetModuleHandleW
0x180008134  nop     dword ptr [rax+rax+00h]
0x180008139  test    rax, rax
0x18000813c  jz      short loc_18000815D
0x18000813e  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180008145  mov     rcx, rax; hModule
0x180008148  call    cs:__imp_GetProcAddress
0x18000814f  nop     dword ptr [rax+rax+00h]
0x180008154  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000815b  jmp     short loc_180008164
0x18000815d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008164  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000816b  test    rax, rax
0x18000816e  jz      short loc_18000817B
0x180008170  mov     rdx, rbx
0x180008173  mov     rcx, rsi
0x180008176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000817b  mov     rax, rbx
0x18000817e  mov     rbx, [rsp+28h+arg_0]
0x180008183  mov     rsi, [rsp+28h+arg_8]
0x180008188  add     rsp, 20h
0x18000818c  pop     rdi
0x18000818d  retn
```
