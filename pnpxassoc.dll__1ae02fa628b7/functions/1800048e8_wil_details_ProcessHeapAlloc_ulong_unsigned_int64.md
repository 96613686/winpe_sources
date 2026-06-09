# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800048e8`
- end: `0x180004986`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000314c`
- `0x1800038a0`
- `0x180004c28`
- `0x18001085c`
- `0x1800129e4`

## callees

- `0x1800048e8`
- `0x180014010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000490d`
- `KERNEL32!HeapAlloc` at `0x18000490d`
- `KERNEL32!GetProcAddress` at `0x180004946`
- `KERNEL32!GetProcAddress` at `0x180004946`
- `KERNEL32!GetProcessHeap` at `0x1800048fc`
- `KERNEL32!GetProcessHeap` at `0x1800048fc`
- `KERNEL32!GetModuleHandleW` at `0x180004931`
- `KERNEL32!GetModuleHandleW` at `0x180004931`

## string_xrefs

- `0x18000492a`: `ntdll.dll`

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
0x1800048e8  mov     [rsp+arg_0], rbx
0x1800048ed  mov     [rsp+arg_8], rsi
0x1800048f2  push    rdi
0x1800048f3  sub     rsp, 20h
0x1800048f7  mov     rbx, rdx
0x1800048fa  mov     edi, ecx
0x1800048fc  call    cs:__imp_GetProcessHeap
0x180004902  mov     r8, rbx; dwBytes
0x180004905  mov     edx, edi; dwFlags
0x180004907  mov     rcx, rax; hHeap
0x18000490a  mov     rsi, rax
0x18000490d  call    cs:__imp_HeapAlloc
0x180004913  mov     rbx, rax
0x180004916  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000491d  test    rax, rax
0x180004920  jnz     short loc_180004968
0x180004922  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004928  jnz     short loc_180004973
0x18000492a  lea     rcx, ModuleName; "ntdll.dll"
0x180004931  call    cs:__imp_GetModuleHandleW
0x180004937  test    rax, rax
0x18000493a  jz      short loc_180004955
0x18000493c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180004943  mov     rcx, rax; hModule
0x180004946  call    cs:__imp_GetProcAddress
0x18000494c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180004953  jmp     short loc_18000495C
0x180004955  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000495c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004963  test    rax, rax
0x180004966  jz      short loc_180004973
0x180004968  mov     rdx, rbx
0x18000496b  mov     rcx, rsi
0x18000496e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004973  mov     rsi, [rsp+28h+arg_8]
0x180004978  mov     rax, rbx
0x18000497b  mov     rbx, [rsp+28h+arg_0]
0x180004980  add     rsp, 20h
0x180004984  pop     rdi
0x180004985  retn
```
