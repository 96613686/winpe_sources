# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800054fc`
- end: `0x18000559a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800045dc`
- `0x18000509c`
- `0x180005afc`
- `0x180005e98`

## callees

- `0x1800054fc`
- `0x18001c010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180005545`
- `KERNEL32!GetModuleHandleW` at `0x180005545`
- `KERNEL32!GetProcessHeap` at `0x180005510`
- `KERNEL32!GetProcessHeap` at `0x180005510`
- `KERNEL32!GetProcAddress` at `0x18000555a`
- `KERNEL32!GetProcAddress` at `0x18000555a`
- `KERNEL32!HeapAlloc` at `0x180005521`
- `KERNEL32!HeapAlloc` at `0x180005521`

## string_xrefs

- `0x18000553e`: `ntdll.dll`

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
0x1800054fc  mov     [rsp+arg_0], rbx
0x180005501  mov     [rsp+arg_8], rsi
0x180005506  push    rdi
0x180005507  sub     rsp, 20h
0x18000550b  mov     rbx, rdx
0x18000550e  mov     edi, ecx
0x180005510  call    cs:__imp_GetProcessHeap
0x180005516  mov     r8, rbx; dwBytes
0x180005519  mov     edx, edi; dwFlags
0x18000551b  mov     rcx, rax; hHeap
0x18000551e  mov     rsi, rax
0x180005521  call    cs:__imp_HeapAlloc
0x180005527  mov     rbx, rax
0x18000552a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005531  test    rax, rax
0x180005534  jnz     short loc_18000557C
0x180005536  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000553c  jnz     short loc_180005587
0x18000553e  lea     rcx, ModuleName; "ntdll.dll"
0x180005545  call    cs:__imp_GetModuleHandleW
0x18000554b  test    rax, rax
0x18000554e  jz      short loc_180005569
0x180005550  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x180005557  mov     rcx, rax; hModule
0x18000555a  call    cs:__imp_GetProcAddress
0x180005560  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005567  jmp     short loc_180005570
0x180005569  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005570  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005577  test    rax, rax
0x18000557a  jz      short loc_180005587
0x18000557c  mov     rdx, rbx
0x18000557f  mov     rcx, rsi
0x180005582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005587  mov     rsi, [rsp+28h+arg_8]
0x18000558c  mov     rax, rbx
0x18000558f  mov     rbx, [rsp+28h+arg_0]
0x180005594  add     rsp, 20h
0x180005598  pop     rdi
0x180005599  retn
```
