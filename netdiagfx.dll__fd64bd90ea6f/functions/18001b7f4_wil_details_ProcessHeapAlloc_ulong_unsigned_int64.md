# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18001b7f4`
- end: `0x18001b892`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001b47c`
- `0x18001c71c`
- `0x18001c858`

## callees

- `0x18001b7f4`
- `0x18002f010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18001b819`
- `KERNEL32!HeapAlloc` at `0x18001b819`
- `KERNEL32!GetProcAddress` at `0x18001b852`
- `KERNEL32!GetProcAddress` at `0x18001b852`
- `KERNEL32!GetProcessHeap` at `0x18001b808`
- `KERNEL32!GetProcessHeap` at `0x18001b808`
- `KERNEL32!GetModuleHandleW` at `0x18001b83d`
- `KERNEL32!GetModuleHandleW` at `0x18001b83d`

## string_xrefs

- `0x18001b836`: `ntdll.dll`

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
0x18001b7f4  mov     [rsp+arg_0], rbx
0x18001b7f9  mov     [rsp+arg_8], rsi
0x18001b7fe  push    rdi
0x18001b7ff  sub     rsp, 20h
0x18001b803  mov     rbx, rdx
0x18001b806  mov     edi, ecx
0x18001b808  call    cs:__imp_GetProcessHeap
0x18001b80e  mov     rsi, rax
0x18001b811  mov     r8, rbx; dwBytes
0x18001b814  mov     edx, edi; dwFlags
0x18001b816  mov     rcx, rax; hHeap
0x18001b819  call    cs:__imp_HeapAlloc
0x18001b81f  mov     rbx, rax
0x18001b822  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18001b829  test    rax, rax
0x18001b82c  jnz     short loc_18001B874
0x18001b82e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001b834  jnz     short loc_18001B87F
0x18001b836  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18001b83d  call    cs:__imp_GetModuleHandleW
0x18001b843  test    rax, rax
0x18001b846  jz      short loc_18001B861
0x18001b848  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18001b84f  mov     rcx, rax; hModule
0x18001b852  call    cs:__imp_GetProcAddress
0x18001b858  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18001b85f  jmp     short loc_18001B868
0x18001b861  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18001b868  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001b86f  test    rax, rax
0x18001b872  jz      short loc_18001B87F
0x18001b874  mov     rdx, rbx
0x18001b877  mov     rcx, rsi
0x18001b87a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b87f  mov     rax, rbx
0x18001b882  mov     rbx, [rsp+28h+arg_0]
0x18001b887  mov     rsi, [rsp+28h+arg_8]
0x18001b88c  add     rsp, 20h
0x18001b890  pop     rdi
0x18001b891  retn
```
