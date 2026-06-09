# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140004198`
- end: `0x140004236`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140002ab8`
- `0x140003150`
- `0x1400044e0`

## callees

- `0x140004198`
- `0x140005010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1400041f6`
- `KERNEL32!GetProcAddress` at `0x1400041f6`
- `KERNEL32!GetModuleHandleW` at `0x1400041e1`
- `KERNEL32!GetModuleHandleW` at `0x1400041e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400041ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400041ac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400041bd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400041bd`

## string_xrefs

- `0x1400041da`: `ntdll.dll`

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
0x140004198  mov     [rsp+arg_0], rbx
0x14000419d  mov     [rsp+arg_8], rsi
0x1400041a2  push    rdi
0x1400041a3  sub     rsp, 20h
0x1400041a7  mov     rbx, rdx
0x1400041aa  mov     edi, ecx
0x1400041ac  call    cs:__imp_GetProcessHeap
0x1400041b2  mov     r8, rbx; dwBytes
0x1400041b5  mov     edx, edi; dwFlags
0x1400041b7  mov     rcx, rax; hHeap
0x1400041ba  mov     rsi, rax
0x1400041bd  call    cs:__imp_HeapAlloc
0x1400041c3  mov     rbx, rax
0x1400041c6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400041cd  test    rax, rax
0x1400041d0  jnz     short loc_140004218
0x1400041d2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400041d8  jnz     short loc_140004223
0x1400041da  lea     rcx, ModuleName; "ntdll.dll"
0x1400041e1  call    cs:__imp_GetModuleHandleW
0x1400041e7  test    rax, rax
0x1400041ea  jz      short loc_140004205
0x1400041ec  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1400041f3  mov     rcx, rax; hModule
0x1400041f6  call    cs:__imp_GetProcAddress
0x1400041fc  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140004203  jmp     short loc_14000420C
0x140004205  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000420c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140004213  test    rax, rax
0x140004216  jz      short loc_140004223
0x140004218  mov     rdx, rbx
0x14000421b  mov     rcx, rsi
0x14000421e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004223  mov     rsi, [rsp+28h+arg_8]
0x140004228  mov     rax, rbx
0x14000422b  mov     rbx, [rsp+28h+arg_0]
0x140004230  add     rsp, 20h
0x140004234  pop     rdi
0x140004235  retn
```
