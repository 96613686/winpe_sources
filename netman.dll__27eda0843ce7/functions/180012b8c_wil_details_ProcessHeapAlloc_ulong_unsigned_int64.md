# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180012b8c`
- end: `0x180012c2a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180011f60`
- `0x180012090`
- `0x180016ea8`
- `0x1800170d4`
- `0x180018e64`

## callees

- `0x180012b8c`
- `0x180036010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180012bd5`
- `KERNEL32!GetModuleHandleW` at `0x180012bd5`
- `KERNEL32!GetProcessHeap` at `0x180012ba0`
- `KERNEL32!GetProcessHeap` at `0x180012ba0`
- `KERNEL32!GetProcAddress` at `0x180012bea`
- `KERNEL32!GetProcAddress` at `0x180012bea`
- `KERNEL32!HeapAlloc` at `0x180012bb1`
- `KERNEL32!HeapAlloc` at `0x180012bb1`

## string_xrefs

- `0x180012bce`: `ntdll.dll`

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
0x180012b8c  mov     [rsp+arg_0], rbx
0x180012b91  mov     [rsp+arg_8], rsi
0x180012b96  push    rdi
0x180012b97  sub     rsp, 20h
0x180012b9b  mov     rbx, rdx
0x180012b9e  mov     edi, ecx
0x180012ba0  call    cs:__imp_GetProcessHeap
0x180012ba6  mov     rsi, rax
0x180012ba9  mov     r8, rbx; dwBytes
0x180012bac  mov     edx, edi; dwFlags
0x180012bae  mov     rcx, rax; hHeap
0x180012bb1  call    cs:__imp_HeapAlloc
0x180012bb7  mov     rbx, rax
0x180012bba  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180012bc1  test    rax, rax
0x180012bc4  jnz     short loc_180012C0C
0x180012bc6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180012bcc  jnz     short loc_180012C17
0x180012bce  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180012bd5  call    cs:__imp_GetModuleHandleW
0x180012bdb  test    rax, rax
0x180012bde  jz      short loc_180012BF9
0x180012be0  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180012be7  mov     rcx, rax; hModule
0x180012bea  call    cs:__imp_GetProcAddress
0x180012bf0  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180012bf7  jmp     short loc_180012C00
0x180012bf9  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180012c00  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180012c07  test    rax, rax
0x180012c0a  jz      short loc_180012C17
0x180012c0c  mov     rdx, rbx
0x180012c0f  mov     rcx, rsi
0x180012c12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c17  mov     rax, rbx
0x180012c1a  mov     rbx, [rsp+28h+arg_0]
0x180012c1f  mov     rsi, [rsp+28h+arg_8]
0x180012c24  add     rsp, 20h
0x180012c28  pop     rdi
0x180012c29  retn
```
