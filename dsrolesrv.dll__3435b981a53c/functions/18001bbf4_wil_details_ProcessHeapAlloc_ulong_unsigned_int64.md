# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18001bbf4`
- end: `0x18001bc92`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001b69c`
- `0x18001b7f0`
- `0x18001c964`
- `0x18001cbc8`
- `0x18001dde0`

## callees

- `0x18001bbf4`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001bc52`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001bc52`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001bc3d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001bc3d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001bc19`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001bc19`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bc08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bc08`

## string_xrefs

- `0x18001bc36`: `ntdll.dll`

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
0x18001bbf4  mov     [rsp+arg_0], rbx
0x18001bbf9  mov     [rsp+arg_8], rsi
0x18001bbfe  push    rdi
0x18001bbff  sub     rsp, 20h
0x18001bc03  mov     rbx, rdx
0x18001bc06  mov     edi, ecx
0x18001bc08  call    cs:__imp_GetProcessHeap
0x18001bc0e  mov     r8, rbx; dwBytes
0x18001bc11  mov     edx, edi; dwFlags
0x18001bc13  mov     rcx, rax; hHeap
0x18001bc16  mov     rsi, rax
0x18001bc19  call    cs:__imp_HeapAlloc
0x18001bc1f  mov     rbx, rax
0x18001bc22  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18001bc29  test    rax, rax
0x18001bc2c  jnz     short loc_18001BC74
0x18001bc2e  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001bc34  jnz     short loc_18001BC7F
0x18001bc36  lea     rcx, ModuleName; "ntdll.dll"
0x18001bc3d  call    cs:__imp_GetModuleHandleW
0x18001bc43  test    rax, rax
0x18001bc46  jz      short loc_18001BC61
0x18001bc48  lea     rdx, ProcName; "RtlDisownModuleHeapAllocation"
0x18001bc4f  mov     rcx, rax; hModule
0x18001bc52  call    cs:__imp_GetProcAddress
0x18001bc58  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x18001bc5f  jmp     short loc_18001BC68
0x18001bc61  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18001bc68  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x18001bc6f  test    rax, rax
0x18001bc72  jz      short loc_18001BC7F
0x18001bc74  mov     rdx, rbx
0x18001bc77  mov     rcx, rsi
0x18001bc7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc7f  mov     rsi, [rsp+28h+arg_8]
0x18001bc84  mov     rax, rbx
0x18001bc87  mov     rbx, [rsp+28h+arg_0]
0x18001bc8c  add     rsp, 20h
0x18001bc90  pop     rdi
0x18001bc91  retn
```
