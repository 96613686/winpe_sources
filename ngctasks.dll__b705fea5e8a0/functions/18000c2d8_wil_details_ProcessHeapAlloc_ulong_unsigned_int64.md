# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000c2d8`
- end: `0x18000c376`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a784`
- `0x18000b7d4`
- `0x18000cd54`
- `0x18000d0ec`
- `0x180018e10`
- `0x18001aca4`

## callees

- `0x18000c2d8`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c336`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c336`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c321`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c321`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c2ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c2ec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c2fd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c2fd`

## string_xrefs

- `0x18000c31a`: `ntdll.dll`

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
0x18000c2d8  mov     [rsp+arg_0], rbx
0x18000c2dd  mov     [rsp+arg_8], rsi
0x18000c2e2  push    rdi
0x18000c2e3  sub     rsp, 20h
0x18000c2e7  mov     rbx, rdx
0x18000c2ea  mov     edi, ecx
0x18000c2ec  call    cs:__imp_GetProcessHeap
0x18000c2f2  mov     rsi, rax
0x18000c2f5  mov     r8, rbx; dwBytes
0x18000c2f8  mov     edx, edi; dwFlags
0x18000c2fa  mov     rcx, rax; hHeap
0x18000c2fd  call    cs:__imp_HeapAlloc
0x18000c303  mov     rbx, rax
0x18000c306  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000c30d  test    rax, rax
0x18000c310  jnz     short loc_18000C358
0x18000c312  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000c318  jnz     short loc_18000C363
0x18000c31a  lea     rcx, ModuleName; "ntdll.dll"
0x18000c321  call    cs:__imp_GetModuleHandleW
0x18000c327  test    rax, rax
0x18000c32a  jz      short loc_18000C345
0x18000c32c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000c333  mov     rcx, rax; hModule
0x18000c336  call    cs:__imp_GetProcAddress
0x18000c33c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000c343  jmp     short loc_18000C34C
0x18000c345  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000c34c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000c353  test    rax, rax
0x18000c356  jz      short loc_18000C363
0x18000c358  mov     rdx, rbx
0x18000c35b  mov     rcx, rsi
0x18000c35e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c363  mov     rax, rbx
0x18000c366  mov     rbx, [rsp+28h+arg_0]
0x18000c36b  mov     rsi, [rsp+28h+arg_8]
0x18000c370  add     rsp, 20h
0x18000c374  pop     rdi
0x18000c375  retn
```
