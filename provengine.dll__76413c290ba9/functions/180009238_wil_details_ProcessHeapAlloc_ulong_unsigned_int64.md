# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180009238`
- end: `0x1800092d6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800075e8`
- `0x180009dbc`
- `0x180011efc`
- `0x180022284`

## callees

- `0x180009238`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009296`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009296`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009281`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009281`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000924c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000924c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000925d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000925d`

## string_xrefs

- `0x18000927a`: `ntdll.dll`

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
0x180009238  mov     [rsp+arg_0], rbx
0x18000923d  mov     [rsp+arg_8], rsi
0x180009242  push    rdi
0x180009243  sub     rsp, 20h
0x180009247  mov     rbx, rdx
0x18000924a  mov     edi, ecx
0x18000924c  call    cs:__imp_GetProcessHeap
0x180009252  mov     rsi, rax
0x180009255  mov     r8, rbx; dwBytes
0x180009258  mov     edx, edi; dwFlags
0x18000925a  mov     rcx, rax; hHeap
0x18000925d  call    cs:__imp_HeapAlloc
0x180009263  mov     rbx, rax
0x180009266  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000926d  test    rax, rax
0x180009270  jnz     short loc_1800092B8
0x180009272  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180009278  jnz     short loc_1800092C3
0x18000927a  lea     rcx, ModuleName; "ntdll.dll"
0x180009281  call    cs:__imp_GetModuleHandleW
0x180009287  test    rax, rax
0x18000928a  jz      short loc_1800092A5
0x18000928c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180009293  mov     rcx, rax; hModule
0x180009296  call    cs:__imp_GetProcAddress
0x18000929c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800092a3  jmp     short loc_1800092AC
0x1800092a5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800092ac  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800092b3  test    rax, rax
0x1800092b6  jz      short loc_1800092C3
0x1800092b8  mov     rdx, rbx
0x1800092bb  mov     rcx, rsi
0x1800092be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092c3  mov     rax, rbx
0x1800092c6  mov     rbx, [rsp+28h+arg_0]
0x1800092cb  mov     rsi, [rsp+28h+arg_8]
0x1800092d0  add     rsp, 20h
0x1800092d4  pop     rdi
0x1800092d5  retn
```
