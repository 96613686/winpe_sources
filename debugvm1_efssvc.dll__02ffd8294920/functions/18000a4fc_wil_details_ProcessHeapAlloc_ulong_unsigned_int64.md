# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000a4fc`
- end: `0x18000a59a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008fc8`
- `0x1800096c0`
- `0x18000ab54`

## callees

- `0x18000a4fc`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a545`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a545`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a55a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a55a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a521`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a521`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a510`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a510`

## string_xrefs

- `0x18000a53e`: `ntdll.dll`

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
0x18000a4fc  mov     [rsp+arg_0], rbx
0x18000a501  mov     [rsp+arg_8], rsi
0x18000a506  push    rdi
0x18000a507  sub     rsp, 20h
0x18000a50b  mov     rbx, rdx
0x18000a50e  mov     edi, ecx
0x18000a510  call    cs:__imp_GetProcessHeap
0x18000a516  mov     r8, rbx; dwBytes
0x18000a519  mov     edx, edi; dwFlags
0x18000a51b  mov     rcx, rax; hHeap
0x18000a51e  mov     rsi, rax
0x18000a521  call    cs:__imp_HeapAlloc
0x18000a527  mov     rbx, rax
0x18000a52a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000a531  test    rax, rax
0x18000a534  jnz     short loc_18000A57C
0x18000a536  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000a53c  jnz     short loc_18000A587
0x18000a53e  lea     rcx, ModuleName; "ntdll.dll"
0x18000a545  call    cs:__imp_GetModuleHandleW
0x18000a54b  test    rax, rax
0x18000a54e  jz      short loc_18000A569
0x18000a550  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000a557  mov     rcx, rax; hModule
0x18000a55a  call    cs:__imp_GetProcAddress
0x18000a560  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000a567  jmp     short loc_18000A570
0x18000a569  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000a570  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000a577  test    rax, rax
0x18000a57a  jz      short loc_18000A587
0x18000a57c  mov     rdx, rbx
0x18000a57f  mov     rcx, rsi
0x18000a582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a587  mov     rsi, [rsp+28h+arg_8]
0x18000a58c  mov     rax, rbx
0x18000a58f  mov     rbx, [rsp+28h+arg_0]
0x18000a594  add     rsp, 20h
0x18000a598  pop     rdi
0x18000a599  retn
```
