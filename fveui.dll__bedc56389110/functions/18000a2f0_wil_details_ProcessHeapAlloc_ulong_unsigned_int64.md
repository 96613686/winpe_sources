# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000a2f0`
- end: `0x18000a38e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009e0c`
- `0x180009f30`
- `0x18000b300`
- `0x18000b784`
- `0x18000d98c`

## callees

- `0x18000a2f0`
- `0x18002d010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000a34e`
- `KERNEL32!GetProcAddress` at `0x18000a34e`
- `KERNEL32!GetModuleHandleW` at `0x18000a339`
- `KERNEL32!GetModuleHandleW` at `0x18000a339`
- `KERNEL32!HeapAlloc` at `0x18000a315`
- `KERNEL32!HeapAlloc` at `0x18000a315`
- `KERNEL32!GetProcessHeap` at `0x18000a304`
- `KERNEL32!GetProcessHeap` at `0x18000a304`

## string_xrefs

- `0x18000a332`: `ntdll.dll`

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
0x18000a2f0  mov     [rsp+arg_0], rbx
0x18000a2f5  mov     [rsp+arg_8], rsi
0x18000a2fa  push    rdi
0x18000a2fb  sub     rsp, 20h
0x18000a2ff  mov     rbx, rdx
0x18000a302  mov     edi, ecx
0x18000a304  call    cs:__imp_GetProcessHeap
0x18000a30a  mov     rsi, rax
0x18000a30d  mov     r8, rbx; dwBytes
0x18000a310  mov     edx, edi; dwFlags
0x18000a312  mov     rcx, rax; hHeap
0x18000a315  call    cs:__imp_HeapAlloc
0x18000a31b  mov     rbx, rax
0x18000a31e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000a325  test    rax, rax
0x18000a328  jnz     short loc_18000A370
0x18000a32a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000a330  jnz     short loc_18000A37B
0x18000a332  lea     rcx, ModuleName; "ntdll.dll"
0x18000a339  call    cs:__imp_GetModuleHandleW
0x18000a33f  test    rax, rax
0x18000a342  jz      short loc_18000A35D
0x18000a344  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x18000a34b  mov     rcx, rax; hModule
0x18000a34e  call    cs:__imp_GetProcAddress
0x18000a354  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000a35b  jmp     short loc_18000A364
0x18000a35d  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000a364  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000a36b  test    rax, rax
0x18000a36e  jz      short loc_18000A37B
0x18000a370  mov     rdx, rbx
0x18000a373  mov     rcx, rsi
0x18000a376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a37b  mov     rax, rbx
0x18000a37e  mov     rbx, [rsp+28h+arg_0]
0x18000a383  mov     rsi, [rsp+28h+arg_8]
0x18000a388  add     rsp, 20h
0x18000a38c  pop     rdi
0x18000a38d  retn
```
