# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18005ad2c`
- end: `0x18005ade3`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `11`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180051e90`
- `0x180053a9c`
- `0x180053bf4`
- `0x18005b1e8`
- `0x18005b374`
- `0x18007a0f0`
- `0x18007a550`
- `0x18007a940`
- `0x18007ad30`
- `0x18007b0a0`
- `0x18007e770`

## callees

- `0x18005ad2c`
- `0x180098010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18005ad57`
- `KERNEL32!HeapAlloc` at `0x18005ad57`
- `KERNEL32!GetProcAddress` at `0x18005ad9c`
- `KERNEL32!GetProcAddress` at `0x18005ad9c`
- `KERNEL32!GetProcessHeap` at `0x18005ad40`
- `KERNEL32!GetProcessHeap` at `0x18005ad40`
- `KERNEL32!GetModuleHandleW` at `0x18005ad81`
- `KERNEL32!GetModuleHandleW` at `0x18005ad81`

## string_xrefs

- `0x18005ad7a`: `ntdll.dll`

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
0x18005ad2c  mov     [rsp+arg_0], rbx
0x18005ad31  mov     [rsp+arg_8], rsi
0x18005ad36  push    rdi
0x18005ad37  sub     rsp, 20h
0x18005ad3b  mov     rbx, rdx
0x18005ad3e  mov     edi, ecx
0x18005ad40  call    cs:__imp_GetProcessHeap
0x18005ad47  nop     dword ptr [rax+rax+00h]
0x18005ad4c  mov     r8, rbx; dwBytes
0x18005ad4f  mov     edx, edi; dwFlags
0x18005ad51  mov     rcx, rax; hHeap
0x18005ad54  mov     rsi, rax
0x18005ad57  call    cs:__imp_HeapAlloc
0x18005ad5e  nop     dword ptr [rax+rax+00h]
0x18005ad63  mov     rbx, rax
0x18005ad66  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18005ad6d  test    rax, rax
0x18005ad70  jnz     short loc_18005ADC4
0x18005ad72  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18005ad78  jnz     short loc_18005ADCF
0x18005ad7a  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18005ad81  call    cs:__imp_GetModuleHandleW
0x18005ad88  nop     dword ptr [rax+rax+00h]
0x18005ad8d  test    rax, rax
0x18005ad90  jz      short loc_18005ADB1
0x18005ad92  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18005ad99  mov     rcx, rax; hModule
0x18005ad9c  call    cs:__imp_GetProcAddress
0x18005ada3  nop     dword ptr [rax+rax+00h]
0x18005ada8  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18005adaf  jmp     short loc_18005ADB8
0x18005adb1  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18005adb8  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18005adbf  test    rax, rax
0x18005adc2  jz      short loc_18005ADCF
0x18005adc4  mov     rdx, rbx
0x18005adc7  mov     rcx, rsi
0x18005adca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005adcf  mov     rsi, [rsp+28h+arg_8]
0x18005add4  mov     rax, rbx
0x18005add7  mov     rbx, [rsp+28h+arg_0]
0x18005addc  add     rsp, 20h
0x18005ade0  pop     rdi
0x18005ade1  retn
```
