# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180023520`
- end: `0x1800235d7`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001c684`
- `0x18001ca7c`
- `0x180025090`
- `0x180025424`
- `0x1800264ec`

## callees

- `0x180023520`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023590`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023590`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180023575`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180023575`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002354b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002354b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023534`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023534`

## string_xrefs

- `0x18002356e`: `ntdll.dll`

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
0x180023520  mov     [rsp+arg_0], rbx
0x180023525  mov     [rsp+arg_8], rsi
0x18002352a  push    rdi
0x18002352b  sub     rsp, 20h
0x18002352f  mov     rbx, rdx
0x180023532  mov     edi, ecx
0x180023534  call    cs:__imp_GetProcessHeap
0x18002353b  nop     dword ptr [rax+rax+00h]
0x180023540  mov     r8, rbx; dwBytes
0x180023543  mov     edx, edi; dwFlags
0x180023545  mov     rcx, rax; hHeap
0x180023548  mov     rsi, rax
0x18002354b  call    cs:__imp_HeapAlloc
0x180023552  nop     dword ptr [rax+rax+00h]
0x180023557  mov     rbx, rax
0x18002355a  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x180023561  test    rax, rax
0x180023564  jnz     short loc_1800235B8
0x180023566  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18002356c  jnz     short loc_1800235C3
0x18002356e  lea     rcx, ModuleName; "ntdll.dll"
0x180023575  call    cs:__imp_GetModuleHandleW
0x18002357c  nop     dword ptr [rax+rax+00h]
0x180023581  test    rax, rax
0x180023584  jz      short loc_1800235A5
0x180023586  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x18002358d  mov     rcx, rax; hModule
0x180023590  call    cs:__imp_GetProcAddress
0x180023597  nop     dword ptr [rax+rax+00h]
0x18002359c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800235a3  jmp     short loc_1800235AC
0x1800235a5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800235ac  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800235b3  test    rax, rax
0x1800235b6  jz      short loc_1800235C3
0x1800235b8  mov     rdx, rbx
0x1800235bb  mov     rcx, rsi
0x1800235be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800235c3  mov     rsi, [rsp+28h+arg_8]
0x1800235c8  mov     rax, rbx
0x1800235cb  mov     rbx, [rsp+28h+arg_0]
0x1800235d0  add     rsp, 20h
0x1800235d4  pop     rdi
0x1800235d5  retn
```
