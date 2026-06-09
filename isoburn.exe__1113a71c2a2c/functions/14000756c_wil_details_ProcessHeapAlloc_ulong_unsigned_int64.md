# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x14000756c`
- end: `0x14000760a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140003ecc`
- `0x140004dd0`
- `0x140005714`
- `0x140007de0`

## callees

- `0x14000756c`
- `0x140010010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1400075ca`
- `KERNEL32!GetProcAddress` at `0x1400075ca`
- `KERNEL32!GetProcessHeap` at `0x140007580`
- `KERNEL32!GetProcessHeap` at `0x140007580`
- `KERNEL32!HeapAlloc` at `0x140007591`
- `KERNEL32!HeapAlloc` at `0x140007591`
- `KERNEL32!GetModuleHandleW` at `0x1400075b5`
- `KERNEL32!GetModuleHandleW` at `0x1400075b5`

## string_xrefs

- `0x1400075ae`: `ntdll.dll`

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
0x14000756c  mov     [rsp+arg_0], rbx
0x140007571  mov     [rsp+arg_8], rsi
0x140007576  push    rdi
0x140007577  sub     rsp, 20h
0x14000757b  mov     rbx, rdx
0x14000757e  mov     edi, ecx
0x140007580  call    cs:__imp_GetProcessHeap
0x140007586  mov     r8, rbx; dwBytes
0x140007589  mov     edx, edi; dwFlags
0x14000758b  mov     rcx, rax; hHeap
0x14000758e  mov     rsi, rax
0x140007591  call    cs:__imp_HeapAlloc
0x140007597  mov     rbx, rax
0x14000759a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400075a1  test    rax, rax
0x1400075a4  jnz     short loc_1400075EC
0x1400075a6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400075ac  jnz     short loc_1400075F7
0x1400075ae  lea     rcx, aNtdllDll; "ntdll.dll"
0x1400075b5  call    cs:__imp_GetModuleHandleW
0x1400075bb  test    rax, rax
0x1400075be  jz      short loc_1400075D9
0x1400075c0  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1400075c7  mov     rcx, rax; hModule
0x1400075ca  call    cs:__imp_GetProcAddress
0x1400075d0  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1400075d7  jmp     short loc_1400075E0
0x1400075d9  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400075e0  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400075e7  test    rax, rax
0x1400075ea  jz      short loc_1400075F7
0x1400075ec  mov     rdx, rbx
0x1400075ef  mov     rcx, rsi
0x1400075f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400075f7  mov     rsi, [rsp+28h+arg_8]
0x1400075fc  mov     rax, rbx
0x1400075ff  mov     rbx, [rsp+28h+arg_0]
0x140007604  add     rsp, 20h
0x140007608  pop     rdi
0x140007609  retn
```
