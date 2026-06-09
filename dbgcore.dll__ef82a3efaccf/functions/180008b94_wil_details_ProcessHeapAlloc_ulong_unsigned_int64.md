# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180008b94`
- end: `0x180008c3c`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `168`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004c68`
- `0x18000500c`
- `0x180006fd0`
- `0x18000a4e8`
- `0x18000f49c`

## callees

- `0x180008b94`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180008bfc`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180008bfc`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180008be7`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180008be7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008bb2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008bb2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008bc3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008bc3`

## string_xrefs

- `0x180008be0`: `ntdll.dll`

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
0x180008b94  push    rdi
0x180008b96  sub     rsp, 30h
0x180008b9a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180008ba3  mov     [rsp+38h+arg_0], rbx
0x180008ba8  mov     [rsp+38h+arg_8], rsi
0x180008bad  mov     rbx, rdx
0x180008bb0  mov     edi, ecx
0x180008bb2  call    cs:__imp_GetProcessHeap
0x180008bb8  mov     rsi, rax
0x180008bbb  mov     r8, rbx; dwBytes
0x180008bbe  mov     edx, edi; dwFlags
0x180008bc0  mov     rcx, rax; hHeap
0x180008bc3  call    cs:__imp_HeapAlloc
0x180008bc9  mov     rbx, rax
0x180008bcc  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008bd3  test    rax, rax
0x180008bd6  jnz     short loc_180008C1E
0x180008bd8  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008bde  jnz     short loc_180008C29
0x180008be0  lea     rcx, ModuleName; "ntdll.dll"
0x180008be7  call    cs:__imp_GetModuleHandleW
0x180008bed  test    rax, rax
0x180008bf0  jz      short loc_180008C0B
0x180008bf2  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180008bf9  mov     rcx, rax; hModule
0x180008bfc  call    cs:__imp_GetProcAddress
0x180008c02  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180008c09  jmp     short loc_180008C12
0x180008c0b  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008c12  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008c19  test    rax, rax
0x180008c1c  jz      short loc_180008C29
0x180008c1e  mov     rdx, rbx
0x180008c21  mov     rcx, rsi
0x180008c24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c29  mov     rax, rbx
0x180008c2c  mov     rbx, [rsp+38h+arg_0]
0x180008c31  mov     rsi, [rsp+38h+arg_8]
0x180008c36  add     rsp, 30h
0x180008c3a  pop     rdi
0x180008c3b  retn
```
