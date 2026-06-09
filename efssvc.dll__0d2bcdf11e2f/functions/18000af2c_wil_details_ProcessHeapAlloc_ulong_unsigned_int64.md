# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000af2c`
- end: `0x18000afe3`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009e20`
- `0x18000ac68`
- `0x18000b648`

## callees

- `0x18000af2c`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000af81`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000af81`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000af9c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000af9c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000af57`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000af57`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000af40`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000af40`

## string_xrefs

- `0x18000af7a`: `ntdll.dll`

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
0x18000af2c  mov     [rsp+arg_0], rbx
0x18000af31  mov     [rsp+arg_8], rsi
0x18000af36  push    rdi
0x18000af37  sub     rsp, 20h
0x18000af3b  mov     rbx, rdx
0x18000af3e  mov     edi, ecx
0x18000af40  call    cs:__imp_GetProcessHeap
0x18000af47  nop     dword ptr [rax+rax+00h]
0x18000af4c  mov     r8, rbx; dwBytes
0x18000af4f  mov     edx, edi; dwFlags
0x18000af51  mov     rcx, rax; hHeap
0x18000af54  mov     rsi, rax
0x18000af57  call    cs:__imp_HeapAlloc
0x18000af5e  nop     dword ptr [rax+rax+00h]
0x18000af63  mov     rbx, rax
0x18000af66  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000af6d  test    rax, rax
0x18000af70  jnz     short loc_18000AFC4
0x18000af72  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000af78  jnz     short loc_18000AFCF
0x18000af7a  lea     rcx, ModuleName; "ntdll.dll"
0x18000af81  call    cs:__imp_GetModuleHandleW
0x18000af88  nop     dword ptr [rax+rax+00h]
0x18000af8d  test    rax, rax
0x18000af90  jz      short loc_18000AFB1
0x18000af92  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18000af99  mov     rcx, rax; hModule
0x18000af9c  call    cs:__imp_GetProcAddress
0x18000afa3  nop     dword ptr [rax+rax+00h]
0x18000afa8  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18000afaf  jmp     short loc_18000AFB8
0x18000afb1  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000afb8  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18000afbf  test    rax, rax
0x18000afc2  jz      short loc_18000AFCF
0x18000afc4  mov     rdx, rbx
0x18000afc7  mov     rcx, rsi
0x18000afca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afcf  mov     rsi, [rsp+28h+arg_8]
0x18000afd4  mov     rax, rbx
0x18000afd7  mov     rbx, [rsp+28h+arg_0]
0x18000afdc  add     rsp, 20h
0x18000afe0  pop     rdi
0x18000afe1  retn
```
