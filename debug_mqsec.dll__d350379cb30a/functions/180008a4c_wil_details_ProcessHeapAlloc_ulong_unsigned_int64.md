# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180008a4c`
- end: `0x180008aeb`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `159`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000862c`
- `0x18000875c`
- `0x180009940`
- `0x180009e08`
- `0x18000aec8`

## callees

- `0x180008a4c`
- `0x180031010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180008a95`
- `KERNEL32!GetModuleHandleW` at `0x180008a95`
- `KERNEL32!HeapAlloc` at `0x180008a71`
- `KERNEL32!HeapAlloc` at `0x180008a71`
- `KERNEL32!GetProcAddress` at `0x180008aaa`
- `KERNEL32!GetProcAddress` at `0x180008aaa`
- `KERNEL32!GetProcessHeap` at `0x180008a60`
- `KERNEL32!GetProcessHeap` at `0x180008a60`

## string_xrefs

- `0x180008a8e`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180008a4c  mov     [rsp+arg_0], rbx
0x180008a51  mov     [rsp+arg_8], rsi
0x180008a56  push    rdi
0x180008a57  sub     rsp, 20h
0x180008a5b  mov     rbx, rdx
0x180008a5e  mov     edi, ecx
0x180008a60  call    cs:__imp_GetProcessHeap
0x180008a66  mov     rsi, rax
0x180008a69  mov     r8, rbx; dwBytes
0x180008a6c  mov     edx, edi; dwFlags
0x180008a6e  mov     rcx, rax; hHeap
0x180008a71  call    cs:__imp_HeapAlloc
0x180008a77  mov     rbx, rax
0x180008a7a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008a81  test    rax, rax
0x180008a84  jnz     short loc_180008ACD
0x180008a86  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008a8c  jnz     short loc_180008AD8
0x180008a8e  lea     rcx, ModuleName; "ntdll.dll"
0x180008a95  call    cs:__imp_GetModuleHandleW
0x180008a9b  test    rax, rax
0x180008a9e  jz      short loc_180008ABA
0x180008aa0  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x180008aa7  mov     rcx, rax; hModule
0x180008aaa  call    cs:__imp_GetProcAddress
0x180008ab0  nop
0x180008ab1  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180008ab8  jmp     short loc_180008AC1
0x180008aba  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180008ac1  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008ac8  test    rax, rax
0x180008acb  jz      short loc_180008AD8
0x180008acd  mov     rdx, rbx
0x180008ad0  mov     rcx, rsi
0x180008ad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ad8  mov     rax, rbx
0x180008adb  mov     rbx, [rsp+28h+arg_0]
0x180008ae0  mov     rsi, [rsp+28h+arg_8]
0x180008ae5  add     rsp, 20h
0x180008ae9  pop     rdi
0x180008aea  retn
```
