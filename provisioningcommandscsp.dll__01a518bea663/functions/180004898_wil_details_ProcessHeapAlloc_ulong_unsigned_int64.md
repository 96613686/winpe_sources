# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180004898`
- end: `0x180004936`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003140`
- `0x180005234`

## callees

- `0x180004898`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800048e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800048e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800048f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800048f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800048ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800048ac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800048bd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800048bd`

## string_xrefs

- `0x1800048da`: `ntdll.dll`

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
0x180004898  mov     [rsp+arg_0], rbx
0x18000489d  mov     [rsp+arg_8], rsi
0x1800048a2  push    rdi
0x1800048a3  sub     rsp, 20h
0x1800048a7  mov     rbx, rdx
0x1800048aa  mov     edi, ecx
0x1800048ac  call    cs:__imp_GetProcessHeap
0x1800048b2  mov     rsi, rax
0x1800048b5  mov     r8, rbx; dwBytes
0x1800048b8  mov     edx, edi; dwFlags
0x1800048ba  mov     rcx, rax; hHeap
0x1800048bd  call    cs:__imp_HeapAlloc
0x1800048c3  mov     rbx, rax
0x1800048c6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800048cd  test    rax, rax
0x1800048d0  jnz     short loc_180004918
0x1800048d2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800048d8  jnz     short loc_180004923
0x1800048da  lea     rcx, ModuleName; "ntdll.dll"
0x1800048e1  call    cs:__imp_GetModuleHandleW
0x1800048e7  test    rax, rax
0x1800048ea  jz      short loc_180004905
0x1800048ec  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x1800048f3  mov     rcx, rax; hModule
0x1800048f6  call    cs:__imp_GetProcAddress
0x1800048fc  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180004903  jmp     short loc_18000490C
0x180004905  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000490c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180004913  test    rax, rax
0x180004916  jz      short loc_180004923
0x180004918  mov     rdx, rbx
0x18000491b  mov     rcx, rsi
0x18000491e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004923  mov     rax, rbx
0x180004926  mov     rbx, [rsp+28h+arg_0]
0x18000492b  mov     rsi, [rsp+28h+arg_8]
0x180004930  add     rsp, 20h
0x180004934  pop     rdi
0x180004935  retn
```
