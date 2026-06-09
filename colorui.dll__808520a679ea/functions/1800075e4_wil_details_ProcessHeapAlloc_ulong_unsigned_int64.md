# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800075e4`
- end: `0x180007682`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003828`
- `0x180003bf8`
- `0x180005a20`
- `0x180009ae8`
- `0x18000b464`

## callees

- `0x1800075e4`
- `0x180019010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180007609`
- `KERNEL32!HeapAlloc` at `0x180007609`
- `KERNEL32!GetProcAddress` at `0x180007642`
- `KERNEL32!GetProcAddress` at `0x180007642`
- `KERNEL32!GetProcessHeap` at `0x1800075f8`
- `KERNEL32!GetProcessHeap` at `0x1800075f8`
- `KERNEL32!GetModuleHandleW` at `0x18000762d`
- `KERNEL32!GetModuleHandleW` at `0x18000762d`

## string_xrefs

- `0x180007626`: `ntdll.dll`

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
0x1800075e4  mov     [rsp+arg_0], rbx
0x1800075e9  mov     [rsp+arg_8], rsi
0x1800075ee  push    rdi
0x1800075ef  sub     rsp, 20h
0x1800075f3  mov     rbx, rdx
0x1800075f6  mov     edi, ecx
0x1800075f8  call    cs:__imp_GetProcessHeap
0x1800075fe  mov     r8, rbx; dwBytes
0x180007601  mov     edx, edi; dwFlags
0x180007603  mov     rcx, rax; hHeap
0x180007606  mov     rsi, rax
0x180007609  call    cs:__imp_HeapAlloc
0x18000760f  mov     rbx, rax
0x180007612  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007619  test    rax, rax
0x18000761c  jnz     short loc_180007664
0x18000761e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007624  jnz     short loc_18000766F
0x180007626  lea     rcx, ModuleName; "ntdll.dll"
0x18000762d  call    cs:__imp_GetModuleHandleW
0x180007633  test    rax, rax
0x180007636  jz      short loc_180007651
0x180007638  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000763f  mov     rcx, rax; hModule
0x180007642  call    cs:__imp_GetProcAddress
0x180007648  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000764f  jmp     short loc_180007658
0x180007651  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007658  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000765f  test    rax, rax
0x180007662  jz      short loc_18000766F
0x180007664  mov     rdx, rbx
0x180007667  mov     rcx, rsi
0x18000766a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000766f  mov     rsi, [rsp+28h+arg_8]
0x180007674  mov     rax, rbx
0x180007677  mov     rbx, [rsp+28h+arg_0]
0x18000767c  add     rsp, 20h
0x180007680  pop     rdi
0x180007681  retn
```
