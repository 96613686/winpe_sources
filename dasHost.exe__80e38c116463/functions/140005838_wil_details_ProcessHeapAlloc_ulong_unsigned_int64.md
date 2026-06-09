# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140005838`
- end: `0x1400058d6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400039d8`
- `0x140003da8`
- `0x1400049c0`
- `0x140006dd4`
- `0x1400084fc`

## callees

- `0x140005838`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005881`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005881`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005896`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005896`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000585d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000585d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000584c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000584c`

## string_xrefs

- `0x14000587a`: `ntdll.dll`

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
0x140005838  mov     [rsp+arg_0], rbx
0x14000583d  mov     [rsp+arg_8], rsi
0x140005842  push    rdi
0x140005843  sub     rsp, 20h
0x140005847  mov     rbx, rdx
0x14000584a  mov     edi, ecx
0x14000584c  call    cs:__imp_GetProcessHeap
0x140005852  mov     rsi, rax
0x140005855  mov     r8, rbx; dwBytes
0x140005858  mov     edx, edi; dwFlags
0x14000585a  mov     rcx, rax; hHeap
0x14000585d  call    cs:__imp_HeapAlloc
0x140005863  mov     rbx, rax
0x140005866  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x14000586d  test    rax, rax
0x140005870  jnz     short loc_1400058B8
0x140005872  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x140005878  jnz     short loc_1400058C3
0x14000587a  lea     rcx, ModuleName; "ntdll.dll"
0x140005881  call    cs:__imp_GetModuleHandleW
0x140005887  test    rax, rax
0x14000588a  jz      short loc_1400058A5
0x14000588c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x140005893  mov     rcx, rax; hModule
0x140005896  call    cs:__imp_GetProcAddress
0x14000589c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1400058a3  jmp     short loc_1400058AC
0x1400058a5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1400058ac  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1400058b3  test    rax, rax
0x1400058b6  jz      short loc_1400058C3
0x1400058b8  mov     rdx, rbx
0x1400058bb  mov     rcx, rsi
0x1400058be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400058c3  mov     rax, rbx
0x1400058c6  mov     rbx, [rsp+28h+arg_0]
0x1400058cb  mov     rsi, [rsp+28h+arg_8]
0x1400058d0  add     rsp, 20h
0x1400058d4  pop     rdi
0x1400058d5  retn
```
