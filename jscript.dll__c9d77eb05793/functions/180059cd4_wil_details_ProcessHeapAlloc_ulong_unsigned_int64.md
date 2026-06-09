# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180059cd4`
- end: `0x180059d72`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `11`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18005119c`
- `0x180052c44`
- `0x180052d98`
- `0x18005a144`
- `0x18005a2bc`
- `0x180078ab0`
- `0x180078ec0`
- `0x180079270`
- `0x180079620`
- `0x180079950`
- `0x18007cef0`

## callees

- `0x180059cd4`
- `0x180096010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180059cf9`
- `KERNEL32!HeapAlloc` at `0x180059cf9`
- `KERNEL32!GetProcAddress` at `0x180059d32`
- `KERNEL32!GetProcAddress` at `0x180059d32`
- `KERNEL32!GetProcessHeap` at `0x180059ce8`
- `KERNEL32!GetProcessHeap` at `0x180059ce8`
- `KERNEL32!GetModuleHandleW` at `0x180059d1d`
- `KERNEL32!GetModuleHandleW` at `0x180059d1d`

## string_xrefs

- `0x180059d16`: `ntdll.dll`

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
0x180059cd4  mov     [rsp+arg_0], rbx
0x180059cd9  mov     [rsp+arg_8], rsi
0x180059cde  push    rdi
0x180059cdf  sub     rsp, 20h
0x180059ce3  mov     rbx, rdx
0x180059ce6  mov     edi, ecx
0x180059ce8  call    cs:__imp_GetProcessHeap
0x180059cee  mov     r8, rbx; dwBytes
0x180059cf1  mov     edx, edi; dwFlags
0x180059cf3  mov     rcx, rax; hHeap
0x180059cf6  mov     rsi, rax
0x180059cf9  call    cs:__imp_HeapAlloc
0x180059cff  mov     rbx, rax
0x180059d02  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180059d09  test    rax, rax
0x180059d0c  jnz     short loc_180059D54
0x180059d0e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180059d14  jnz     short loc_180059D5F
0x180059d16  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180059d1d  call    cs:__imp_GetModuleHandleW
0x180059d23  test    rax, rax
0x180059d26  jz      short loc_180059D41
0x180059d28  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180059d2f  mov     rcx, rax; hModule
0x180059d32  call    cs:__imp_GetProcAddress
0x180059d38  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180059d3f  jmp     short loc_180059D48
0x180059d41  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180059d48  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180059d4f  test    rax, rax
0x180059d52  jz      short loc_180059D5F
0x180059d54  mov     rdx, rbx
0x180059d57  mov     rcx, rsi
0x180059d5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059d5f  mov     rsi, [rsp+28h+arg_8]
0x180059d64  mov     rax, rbx
0x180059d67  mov     rbx, [rsp+28h+arg_0]
0x180059d6c  add     rsp, 20h
0x180059d70  pop     rdi
0x180059d71  retn
```
