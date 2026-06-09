# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x14006ac38`
- end: `0x14006acd6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400687a8`
- `0x140068b4c`
- `0x14006c638`
- `0x14006d480`

## callees

- `0x14006ac38`
- `0x140085010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14006ac5d`
- `KERNEL32!HeapAlloc` at `0x14006ac5d`
- `KERNEL32!GetProcessHeap` at `0x14006ac4c`
- `KERNEL32!GetProcessHeap` at `0x14006ac4c`
- `KERNEL32!GetProcAddress` at `0x14006ac96`
- `KERNEL32!GetProcAddress` at `0x14006ac96`
- `KERNEL32!GetModuleHandleW` at `0x14006ac81`
- `KERNEL32!GetModuleHandleW` at `0x14006ac81`

## string_xrefs

- `0x14006ac7a`: `ntdll.dll`

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
0x14006ac38  mov     [rsp+arg_0], rbx
0x14006ac3d  mov     [rsp+arg_8], rsi
0x14006ac42  push    rdi
0x14006ac43  sub     rsp, 20h
0x14006ac47  mov     rbx, rdx
0x14006ac4a  mov     edi, ecx
0x14006ac4c  call    cs:__imp_GetProcessHeap
0x14006ac52  mov     rsi, rax
0x14006ac55  mov     r8, rbx; dwBytes
0x14006ac58  mov     edx, edi; dwFlags
0x14006ac5a  mov     rcx, rax; hHeap
0x14006ac5d  call    cs:__imp_HeapAlloc
0x14006ac63  mov     rbx, rax
0x14006ac66  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14006ac6d  test    rax, rax
0x14006ac70  jnz     short loc_14006ACB8
0x14006ac72  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14006ac78  jnz     short loc_14006ACC3
0x14006ac7a  lea     rcx, ModuleName; "ntdll.dll"
0x14006ac81  call    cs:__imp_GetModuleHandleW
0x14006ac87  test    rax, rax
0x14006ac8a  jz      short loc_14006ACA5
0x14006ac8c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x14006ac93  mov     rcx, rax; hModule
0x14006ac96  call    cs:__imp_GetProcAddress
0x14006ac9c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x14006aca3  jmp     short loc_14006ACAC
0x14006aca5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14006acac  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x14006acb3  test    rax, rax
0x14006acb6  jz      short loc_14006ACC3
0x14006acb8  mov     rdx, rbx
0x14006acbb  mov     rcx, rsi
0x14006acbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006acc3  mov     rax, rbx
0x14006acc6  mov     rbx, [rsp+28h+arg_0]
0x14006accb  mov     rsi, [rsp+28h+arg_8]
0x14006acd0  add     rsp, 20h
0x14006acd4  pop     rdi
0x14006acd5  retn
```
