# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800051fc`
- end: `0x18000529a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003bf8`
- `0x180004390`
- `0x180005a70`
- `0x180006318`
- `0x18000cf30`

## callees

- `0x1800051fc`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000525a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000525a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005245`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005245`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005210`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005210`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005221`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005221`

## string_xrefs

- `0x18000523e`: `ntdll.dll`

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
0x1800051fc  mov     [rsp+arg_0], rbx
0x180005201  mov     [rsp+arg_8], rsi
0x180005206  push    rdi
0x180005207  sub     rsp, 20h
0x18000520b  mov     rbx, rdx
0x18000520e  mov     edi, ecx
0x180005210  call    cs:__imp_GetProcessHeap
0x180005216  mov     r8, rbx; dwBytes
0x180005219  mov     edx, edi; dwFlags
0x18000521b  mov     rcx, rax; hHeap
0x18000521e  mov     rsi, rax
0x180005221  call    cs:__imp_HeapAlloc
0x180005227  mov     rbx, rax
0x18000522a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005231  test    rax, rax
0x180005234  jnz     short loc_18000527C
0x180005236  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000523c  jnz     short loc_180005287
0x18000523e  lea     rcx, ModuleName; "ntdll.dll"
0x180005245  call    cs:__imp_GetModuleHandleW
0x18000524b  test    rax, rax
0x18000524e  jz      short loc_180005269
0x180005250  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180005257  mov     rcx, rax; hModule
0x18000525a  call    cs:__imp_GetProcAddress
0x180005260  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005267  jmp     short loc_180005270
0x180005269  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005270  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005277  test    rax, rax
0x18000527a  jz      short loc_180005287
0x18000527c  mov     rdx, rbx
0x18000527f  mov     rcx, rsi
0x180005282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005287  mov     rsi, [rsp+28h+arg_8]
0x18000528c  mov     rax, rbx
0x18000528f  mov     rbx, [rsp+28h+arg_0]
0x180005294  add     rsp, 20h
0x180005298  pop     rdi
0x180005299  retn
```
