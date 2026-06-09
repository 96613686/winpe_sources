# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18007abe0`
- end: `0x18007ac97`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18007a6cc`
- `0x18007a7f4`
- `0x18007c1b8`
- `0x18007c3f4`
- `0x18007d44c`

## callees

- `0x18007abe0`
- `0x180095010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18007ac50`
- `KERNEL32!GetProcAddress` at `0x18007ac50`
- `KERNEL32!GetProcessHeap` at `0x18007abf4`
- `KERNEL32!GetProcessHeap` at `0x18007abf4`
- `KERNEL32!HeapAlloc` at `0x18007ac0b`
- `KERNEL32!HeapAlloc` at `0x18007ac0b`
- `KERNEL32!GetModuleHandleW` at `0x18007ac35`
- `KERNEL32!GetModuleHandleW` at `0x18007ac35`

## string_xrefs

- `0x18007ac2e`: `ntdll.dll`

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
0x18007abe0  mov     [rsp+arg_0], rbx
0x18007abe5  mov     [rsp+arg_8], rsi
0x18007abea  push    rdi
0x18007abeb  sub     rsp, 20h
0x18007abef  mov     rbx, rdx
0x18007abf2  mov     edi, ecx
0x18007abf4  call    cs:__imp_GetProcessHeap
0x18007abfb  nop     dword ptr [rax+rax+00h]
0x18007ac00  mov     r8, rbx; dwBytes
0x18007ac03  mov     edx, edi; dwFlags
0x18007ac05  mov     rcx, rax; hHeap
0x18007ac08  mov     rsi, rax
0x18007ac0b  call    cs:__imp_HeapAlloc
0x18007ac12  nop     dword ptr [rax+rax+00h]
0x18007ac17  mov     rbx, rax
0x18007ac1a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18007ac21  test    rax, rax
0x18007ac24  jnz     short loc_18007AC78
0x18007ac26  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18007ac2c  jnz     short loc_18007AC83
0x18007ac2e  lea     rcx, ModuleName; "ntdll.dll"
0x18007ac35  call    cs:__imp_GetModuleHandleW
0x18007ac3c  nop     dword ptr [rax+rax+00h]
0x18007ac41  test    rax, rax
0x18007ac44  jz      short loc_18007AC65
0x18007ac46  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18007ac4d  mov     rcx, rax; hModule
0x18007ac50  call    cs:__imp_GetProcAddress
0x18007ac57  nop     dword ptr [rax+rax+00h]
0x18007ac5c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18007ac63  jmp     short loc_18007AC6C
0x18007ac65  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18007ac6c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18007ac73  test    rax, rax
0x18007ac76  jz      short loc_18007AC83
0x18007ac78  mov     rdx, rbx
0x18007ac7b  mov     rcx, rsi
0x18007ac7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ac83  mov     rsi, [rsp+28h+arg_8]
0x18007ac88  mov     rax, rbx
0x18007ac8b  mov     rbx, [rsp+28h+arg_0]
0x18007ac90  add     rsp, 20h
0x18007ac94  pop     rdi
0x18007ac95  retn
```
