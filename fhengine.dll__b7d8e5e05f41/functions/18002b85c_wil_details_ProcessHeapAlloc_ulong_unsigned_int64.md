# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18002b85c`
- end: `0x18002b8fa`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002b2b0`
- `0x18002b3dc`
- `0x18002cfa0`
- `0x18002d428`
- `0x18002e5f0`

## callees

- `0x18002b85c`
- `0x180034010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002b8ba`
- `KERNEL32!GetProcAddress` at `0x18002b8ba`
- `KERNEL32!GetModuleHandleW` at `0x18002b8a5`
- `KERNEL32!GetModuleHandleW` at `0x18002b8a5`
- `KERNEL32!HeapAlloc` at `0x18002b881`
- `KERNEL32!HeapAlloc` at `0x18002b881`
- `KERNEL32!GetProcessHeap` at `0x18002b870`
- `KERNEL32!GetProcessHeap` at `0x18002b870`

## string_xrefs

- `0x18002b89e`: `ntdll.dll`

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
0x18002b85c  mov     [rsp+arg_0], rbx
0x18002b861  mov     [rsp+arg_8], rsi
0x18002b866  push    rdi
0x18002b867  sub     rsp, 20h
0x18002b86b  mov     rbx, rdx
0x18002b86e  mov     edi, ecx
0x18002b870  call    cs:__imp_GetProcessHeap
0x18002b876  mov     rsi, rax
0x18002b879  mov     r8, rbx; dwBytes
0x18002b87c  mov     edx, edi; dwFlags
0x18002b87e  mov     rcx, rax; hHeap
0x18002b881  call    cs:__imp_HeapAlloc
0x18002b887  mov     rbx, rax
0x18002b88a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18002b891  test    rax, rax
0x18002b894  jnz     short loc_18002B8DC
0x18002b896  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18002b89c  jnz     short loc_18002B8E7
0x18002b89e  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18002b8a5  call    cs:__imp_GetModuleHandleW
0x18002b8ab  test    rax, rax
0x18002b8ae  jz      short loc_18002B8C9
0x18002b8b0  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18002b8b7  mov     rcx, rax; hModule
0x18002b8ba  call    cs:__imp_GetProcAddress
0x18002b8c0  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18002b8c7  jmp     short loc_18002B8D0
0x18002b8c9  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18002b8d0  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18002b8d7  test    rax, rax
0x18002b8da  jz      short loc_18002B8E7
0x18002b8dc  mov     rdx, rbx
0x18002b8df  mov     rcx, rsi
0x18002b8e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8e7  mov     rax, rbx
0x18002b8ea  mov     rbx, [rsp+28h+arg_0]
0x18002b8ef  mov     rsi, [rsp+28h+arg_8]
0x18002b8f4  add     rsp, 20h
0x18002b8f8  pop     rdi
0x18002b8f9  retn
```
