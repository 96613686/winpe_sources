# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180008a6c`
- end: `0x180008b23`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000878c`
- `0x180008ee4`
- `0x180009298`
- `0x18000bff4`
- `0x18000dc08`

## callees

- `0x180008a6c`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008a80`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008a80`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008a97`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008a97`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008ac1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008ac1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008adc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008adc`

## string_xrefs

- `0x180008aba`: `ntdll.dll`

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
0x180008a6c  mov     [rsp+arg_0], rbx
0x180008a71  mov     [rsp+arg_8], rsi
0x180008a76  push    rdi
0x180008a77  sub     rsp, 20h
0x180008a7b  mov     rbx, rdx
0x180008a7e  mov     edi, ecx
0x180008a80  call    cs:__imp_GetProcessHeap
0x180008a87  nop     dword ptr [rax+rax+00h]
0x180008a8c  mov     rsi, rax
0x180008a8f  mov     r8, rbx; dwBytes
0x180008a92  mov     edx, edi; dwFlags
0x180008a94  mov     rcx, rax; hHeap
0x180008a97  call    cs:__imp_HeapAlloc
0x180008a9e  nop     dword ptr [rax+rax+00h]
0x180008aa3  mov     rbx, rax
0x180008aa6  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008aad  test    rax, rax
0x180008ab0  jnz     short loc_180008B04
0x180008ab2  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008ab8  jnz     short loc_180008B0F
0x180008aba  lea     rcx, ModuleName; "ntdll.dll"
0x180008ac1  call    cs:__imp_GetModuleHandleW
0x180008ac8  nop     dword ptr [rax+rax+00h]
0x180008acd  test    rax, rax
0x180008ad0  jz      short loc_180008AF1
0x180008ad2  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x180008ad9  mov     rcx, rax; hModule
0x180008adc  call    cs:__imp_GetProcAddress
0x180008ae3  nop     dword ptr [rax+rax+00h]
0x180008ae8  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180008aef  jmp     short loc_180008AF8
0x180008af1  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008af8  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008aff  test    rax, rax
0x180008b02  jz      short loc_180008B0F
0x180008b04  mov     rdx, rbx
0x180008b07  mov     rcx, rsi
0x180008b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b0f  mov     rax, rbx
0x180008b12  mov     rbx, [rsp+28h+arg_0]
0x180008b17  mov     rsi, [rsp+28h+arg_8]
0x180008b1c  add     rsp, 20h
0x180008b20  pop     rdi
0x180008b21  retn
```
