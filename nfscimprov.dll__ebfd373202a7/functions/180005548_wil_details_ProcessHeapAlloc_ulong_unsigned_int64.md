# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180005548`
- end: `0x1800055e6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005144`
- `0x18000526c`
- `0x1800063b0`
- `0x180006838`
- `0x180007e94`

## callees

- `0x180005548`
- `0x180037010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000556d`
- `KERNEL32!HeapAlloc` at `0x18000556d`
- `KERNEL32!GetProcAddress` at `0x1800055a6`
- `KERNEL32!GetProcAddress` at `0x1800055a6`
- `KERNEL32!GetProcessHeap` at `0x18000555c`
- `KERNEL32!GetProcessHeap` at `0x18000555c`
- `KERNEL32!GetModuleHandleW` at `0x180005591`
- `KERNEL32!GetModuleHandleW` at `0x180005591`

## string_xrefs

- `0x18000558a`: `ntdll.dll`

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
0x180005548  mov     [rsp+arg_0], rbx
0x18000554d  mov     [rsp+arg_8], rsi
0x180005552  push    rdi
0x180005553  sub     rsp, 20h
0x180005557  mov     rbx, rdx
0x18000555a  mov     edi, ecx
0x18000555c  call    cs:__imp_GetProcessHeap
0x180005562  mov     rsi, rax
0x180005565  mov     r8, rbx; dwBytes
0x180005568  mov     edx, edi; dwFlags
0x18000556a  mov     rcx, rax; hHeap
0x18000556d  call    cs:__imp_HeapAlloc
0x180005573  mov     rbx, rax
0x180005576  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000557d  test    rax, rax
0x180005580  jnz     short loc_1800055C8
0x180005582  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005588  jnz     short loc_1800055D3
0x18000558a  lea     rcx, ModuleName; "ntdll.dll"
0x180005591  call    cs:__imp_GetModuleHandleW
0x180005597  test    rax, rax
0x18000559a  jz      short loc_1800055B5
0x18000559c  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x1800055a3  mov     rcx, rax; hModule
0x1800055a6  call    cs:__imp_GetProcAddress
0x1800055ac  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800055b3  jmp     short loc_1800055BC
0x1800055b5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800055bc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800055c3  test    rax, rax
0x1800055c6  jz      short loc_1800055D3
0x1800055c8  mov     rdx, rbx
0x1800055cb  mov     rcx, rsi
0x1800055ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055d3  mov     rax, rbx
0x1800055d6  mov     rbx, [rsp+28h+arg_0]
0x1800055db  mov     rsi, [rsp+28h+arg_8]
0x1800055e0  add     rsp, 20h
0x1800055e4  pop     rdi
0x1800055e5  retn
```
