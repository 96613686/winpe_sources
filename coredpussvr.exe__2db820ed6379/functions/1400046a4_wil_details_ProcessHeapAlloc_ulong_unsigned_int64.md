# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1400046a4`
- end: `0x14000475b`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140004340`
- `0x140004ed8`

## callees

- `0x1400046a4`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400046f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400046f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004714`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004714`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400046cf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400046cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400046b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400046b8`

## string_xrefs

- `0x1400046f2`: `ntdll.dll`

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
0x1400046a4  mov     [rsp+arg_0], rbx
0x1400046a9  mov     [rsp+arg_8], rsi
0x1400046ae  push    rdi
0x1400046af  sub     rsp, 20h
0x1400046b3  mov     rbx, rdx
0x1400046b6  mov     edi, ecx
0x1400046b8  call    cs:__imp_GetProcessHeap
0x1400046bf  nop     dword ptr [rax+rax+00h]
0x1400046c4  mov     rsi, rax
0x1400046c7  mov     r8, rbx; dwBytes
0x1400046ca  mov     edx, edi; dwFlags
0x1400046cc  mov     rcx, rax; hHeap
0x1400046cf  call    cs:__imp_HeapAlloc
0x1400046d6  nop     dword ptr [rax+rax+00h]
0x1400046db  mov     rbx, rax
0x1400046de  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400046e5  test    rax, rax
0x1400046e8  jnz     short loc_14000473C
0x1400046ea  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400046f0  jnz     short loc_140004747
0x1400046f2  lea     rcx, ModuleName; "ntdll.dll"
0x1400046f9  call    cs:__imp_GetModuleHandleW
0x140004700  nop     dword ptr [rax+rax+00h]
0x140004705  test    rax, rax
0x140004708  jz      short loc_140004729
0x14000470a  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x140004711  mov     rcx, rax; hModule
0x140004714  call    cs:__imp_GetProcAddress
0x14000471b  nop     dword ptr [rax+rax+00h]
0x140004720  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x140004727  jmp     short loc_140004730
0x140004729  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x140004730  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140004737  test    rax, rax
0x14000473a  jz      short loc_140004747
0x14000473c  mov     rdx, rbx
0x14000473f  mov     rcx, rsi
0x140004742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004747  mov     rax, rbx
0x14000474a  mov     rbx, [rsp+28h+arg_0]
0x14000474f  mov     rsi, [rsp+28h+arg_8]
0x140004754  add     rsp, 20h
0x140004758  pop     rdi
0x140004759  retn
```
