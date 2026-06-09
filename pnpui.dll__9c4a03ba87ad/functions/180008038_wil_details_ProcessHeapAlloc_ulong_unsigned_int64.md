# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180008038`
- end: `0x1800080d6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004d1c`
- `0x1800050c0`
- `0x1800061f0`
- `0x180009648`
- `0x18000a5e4`

## callees

- `0x180008038`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008096`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008096`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008081`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008081`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000804c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000804c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000805d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000805d`

## string_xrefs

- `0x18000807a`: `ntdll.dll`

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
0x180008038  mov     [rsp+arg_0], rbx
0x18000803d  mov     [rsp+arg_8], rsi
0x180008042  push    rdi
0x180008043  sub     rsp, 20h
0x180008047  mov     rbx, rdx
0x18000804a  mov     edi, ecx
0x18000804c  call    cs:__imp_GetProcessHeap
0x180008052  mov     r8, rbx; dwBytes
0x180008055  mov     edx, edi; dwFlags
0x180008057  mov     rcx, rax; hHeap
0x18000805a  mov     rsi, rax
0x18000805d  call    cs:__imp_HeapAlloc
0x180008063  mov     rbx, rax
0x180008066  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000806d  test    rax, rax
0x180008070  jnz     short loc_1800080B8
0x180008072  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180008078  jnz     short loc_1800080C3
0x18000807a  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180008081  call    cs:__imp_GetModuleHandleW
0x180008087  test    rax, rax
0x18000808a  jz      short loc_1800080A5
0x18000808c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180008093  mov     rcx, rax; hModule
0x180008096  call    cs:__imp_GetProcAddress
0x18000809c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x1800080a3  jmp     short loc_1800080AC
0x1800080a5  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x1800080ac  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1800080b3  test    rax, rax
0x1800080b6  jz      short loc_1800080C3
0x1800080b8  mov     rdx, rbx
0x1800080bb  mov     rcx, rsi
0x1800080be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080c3  mov     rsi, [rsp+28h+arg_8]
0x1800080c8  mov     rax, rbx
0x1800080cb  mov     rbx, [rsp+28h+arg_0]
0x1800080d0  add     rsp, 20h
0x1800080d4  pop     rdi
0x1800080d5  retn
```
