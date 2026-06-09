# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180007b60`
- end: `0x180007bfe`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005a88`
- `0x1800063a0`
- `0x180006970`
- `0x180008410`

## callees

- `0x180007b60`
- `0x18000b010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180007b85`
- `KERNEL32!HeapAlloc` at `0x180007b85`
- `KERNEL32!GetProcAddress` at `0x180007bbe`
- `KERNEL32!GetProcAddress` at `0x180007bbe`
- `KERNEL32!GetProcessHeap` at `0x180007b74`
- `KERNEL32!GetProcessHeap` at `0x180007b74`
- `KERNEL32!GetModuleHandleW` at `0x180007ba9`
- `KERNEL32!GetModuleHandleW` at `0x180007ba9`

## string_xrefs

- `0x180007ba2`: `ntdll.dll`

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
0x180007b60  mov     [rsp+arg_0], rbx
0x180007b65  mov     [rsp+arg_8], rsi
0x180007b6a  push    rdi
0x180007b6b  sub     rsp, 20h
0x180007b6f  mov     rbx, rdx
0x180007b72  mov     edi, ecx
0x180007b74  call    cs:__imp_GetProcessHeap
0x180007b7a  mov     rsi, rax
0x180007b7d  mov     r8, rbx; dwBytes
0x180007b80  mov     edx, edi; dwFlags
0x180007b82  mov     rcx, rax; hHeap
0x180007b85  call    cs:__imp_HeapAlloc
0x180007b8b  mov     rbx, rax
0x180007b8e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007b95  test    rax, rax
0x180007b98  jnz     short loc_180007BE0
0x180007b9a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007ba0  jnz     short loc_180007BEB
0x180007ba2  lea     rcx, ModuleName; "ntdll.dll"
0x180007ba9  call    cs:__imp_GetModuleHandleW
0x180007baf  test    rax, rax
0x180007bb2  jz      short loc_180007BCD
0x180007bb4  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180007bbb  mov     rcx, rax; hModule
0x180007bbe  call    cs:__imp_GetProcAddress
0x180007bc4  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180007bcb  jmp     short loc_180007BD4
0x180007bcd  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180007bd4  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180007bdb  test    rax, rax
0x180007bde  jz      short loc_180007BEB
0x180007be0  mov     rdx, rbx
0x180007be3  mov     rcx, rsi
0x180007be6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007beb  mov     rax, rbx
0x180007bee  mov     rbx, [rsp+28h+arg_0]
0x180007bf3  mov     rsi, [rsp+28h+arg_8]
0x180007bf8  add     rsp, 20h
0x180007bfc  pop     rdi
0x180007bfd  retn
```
