# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x14000fafc`
- end: `0x14000fbb3`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000e910`
- `0x14000f768`
- `0x14000fe74`

## callees

- `0x14000fafc`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000fb6c`
- `KERNEL32!GetProcAddress` at `0x14000fb6c`
- `KERNEL32!GetModuleHandleW` at `0x14000fb51`
- `KERNEL32!GetModuleHandleW` at `0x14000fb51`
- `KERNEL32!GetProcessHeap` at `0x14000fb10`
- `KERNEL32!GetProcessHeap` at `0x14000fb10`
- `KERNEL32!HeapAlloc` at `0x14000fb27`
- `KERNEL32!HeapAlloc` at `0x14000fb27`

## string_xrefs

- `0x14000fb4a`: `ntdll.dll`

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
0x14000fafc  mov     [rsp+arg_0], rbx
0x14000fb01  mov     [rsp+arg_8], rsi
0x14000fb06  push    rdi
0x14000fb07  sub     rsp, 20h
0x14000fb0b  mov     rbx, rdx
0x14000fb0e  mov     edi, ecx
0x14000fb10  call    cs:__imp_GetProcessHeap
0x14000fb17  nop     dword ptr [rax+rax+00h]
0x14000fb1c  mov     r8, rbx; dwBytes
0x14000fb1f  mov     edx, edi; dwFlags
0x14000fb21  mov     rcx, rax; hHeap
0x14000fb24  mov     rsi, rax
0x14000fb27  call    cs:__imp_HeapAlloc
0x14000fb2e  nop     dword ptr [rax+rax+00h]
0x14000fb33  mov     rbx, rax
0x14000fb36  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000fb3d  test    rax, rax
0x14000fb40  jnz     short loc_14000FB94
0x14000fb42  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000fb48  jnz     short loc_14000FB9F
0x14000fb4a  lea     rcx, ModuleName; "ntdll.dll"
0x14000fb51  call    cs:__imp_GetModuleHandleW
0x14000fb58  nop     dword ptr [rax+rax+00h]
0x14000fb5d  test    rax, rax
0x14000fb60  jz      short loc_14000FB81
0x14000fb62  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x14000fb69  mov     rcx, rax; hModule
0x14000fb6c  call    cs:__imp_GetProcAddress
0x14000fb73  nop     dword ptr [rax+rax+00h]
0x14000fb78  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x14000fb7f  jmp     short loc_14000FB88
0x14000fb81  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000fb88  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14000fb8f  test    rax, rax
0x14000fb92  jz      short loc_14000FB9F
0x14000fb94  mov     rdx, rbx
0x14000fb97  mov     rcx, rsi
0x14000fb9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fb9f  mov     rsi, [rsp+28h+arg_8]
0x14000fba4  mov     rax, rbx
0x14000fba7  mov     rbx, [rsp+28h+arg_0]
0x14000fbac  add     rsp, 20h
0x14000fbb0  pop     rdi
0x14000fbb1  retn
```
