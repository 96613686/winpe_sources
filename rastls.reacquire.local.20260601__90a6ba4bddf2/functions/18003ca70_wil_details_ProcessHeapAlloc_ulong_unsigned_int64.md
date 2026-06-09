# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18003ca70`
- end: `0x18003cb27`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002c634`
- `0x18003c564`
- `0x18003c698`
- `0x18003d4a4`
- `0x18003d950`

## callees

- `0x18003ca70`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003cac5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003cac5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003cae0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003cae0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ca84`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ca84`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003ca9b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003ca9b`

## string_xrefs

- `0x18003cabe`: `ntdll.dll`

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
0x18003ca70  mov     [rsp+arg_0], rbx
0x18003ca75  mov     [rsp+arg_8], rsi
0x18003ca7a  push    rdi
0x18003ca7b  sub     rsp, 20h
0x18003ca7f  mov     rbx, rdx
0x18003ca82  mov     edi, ecx
0x18003ca84  call    cs:__imp_GetProcessHeap
0x18003ca8b  nop     dword ptr [rax+rax+00h]
0x18003ca90  mov     rsi, rax
0x18003ca93  mov     r8, rbx; dwBytes
0x18003ca96  mov     edx, edi; dwFlags
0x18003ca98  mov     rcx, rax; hHeap
0x18003ca9b  call    cs:__imp_HeapAlloc
0x18003caa2  nop     dword ptr [rax+rax+00h]
0x18003caa7  mov     rbx, rax
0x18003caaa  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18003cab1  test    rax, rax
0x18003cab4  jnz     short loc_18003CB08
0x18003cab6  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18003cabc  jnz     short loc_18003CB13
0x18003cabe  lea     rcx, ModuleName; "ntdll.dll"
0x18003cac5  call    cs:__imp_GetModuleHandleW
0x18003cacc  nop     dword ptr [rax+rax+00h]
0x18003cad1  test    rax, rax
0x18003cad4  jz      short loc_18003CAF5
0x18003cad6  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18003cadd  mov     rcx, rax; hModule
0x18003cae0  call    cs:__imp_GetProcAddress
0x18003cae7  nop     dword ptr [rax+rax+00h]
0x18003caec  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18003caf3  jmp     short loc_18003CAFC
0x18003caf5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18003cafc  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18003cb03  test    rax, rax
0x18003cb06  jz      short loc_18003CB13
0x18003cb08  mov     rdx, rbx
0x18003cb0b  mov     rcx, rsi
0x18003cb0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cb13  mov     rax, rbx
0x18003cb16  mov     rbx, [rsp+28h+arg_0]
0x18003cb1b  mov     rsi, [rsp+28h+arg_8]
0x18003cb20  add     rsp, 20h
0x18003cb24  pop     rdi
0x18003cb25  retn
```
