# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180005d40`
- end: `0x180005dde`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005850`
- `0x180005974`
- `0x180007060`
- `0x1800074e4`
- `0x180008d84`

## callees

- `0x180005d40`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180005d54`
- `KERNEL32!GetProcessHeap` at `0x180005d54`
- `KERNEL32!HeapAlloc` at `0x180005d65`
- `KERNEL32!HeapAlloc` at `0x180005d65`
- `KERNEL32!GetModuleHandleW` at `0x180005d89`
- `KERNEL32!GetModuleHandleW` at `0x180005d89`
- `KERNEL32!GetProcAddress` at `0x180005d9e`
- `KERNEL32!GetProcAddress` at `0x180005d9e`

## string_xrefs

- `0x180005d82`: `ntdll.dll`

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
0x180005d40  mov     [rsp+arg_0], rbx
0x180005d45  mov     [rsp+arg_8], rsi
0x180005d4a  push    rdi
0x180005d4b  sub     rsp, 20h
0x180005d4f  mov     rbx, rdx
0x180005d52  mov     edi, ecx
0x180005d54  call    cs:__imp_GetProcessHeap
0x180005d5a  mov     rsi, rax
0x180005d5d  mov     r8, rbx; dwBytes
0x180005d60  mov     edx, edi; dwFlags
0x180005d62  mov     rcx, rax; hHeap
0x180005d65  call    cs:__imp_HeapAlloc
0x180005d6b  mov     rbx, rax
0x180005d6e  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005d75  test    rax, rax
0x180005d78  jnz     short loc_180005DC0
0x180005d7a  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005d80  jnz     short loc_180005DCB
0x180005d82  lea     rcx, ModuleName; "ntdll.dll"
0x180005d89  call    cs:__imp_GetModuleHandleW
0x180005d8f  test    rax, rax
0x180005d92  jz      short loc_180005DAD
0x180005d94  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x180005d9b  mov     rcx, rax; hModule
0x180005d9e  call    cs:__imp_GetProcAddress
0x180005da4  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005dab  jmp     short loc_180005DB4
0x180005dad  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180005db4  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005dbb  test    rax, rax
0x180005dbe  jz      short loc_180005DCB
0x180005dc0  mov     rdx, rbx
0x180005dc3  mov     rcx, rsi
0x180005dc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dcb  mov     rax, rbx
0x180005dce  mov     rbx, [rsp+28h+arg_0]
0x180005dd3  mov     rsi, [rsp+28h+arg_8]
0x180005dd8  add     rsp, 20h
0x180005ddc  pop     rdi
0x180005ddd  retn
```
