# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800053f8`
- end: `0x180005496`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003114`
- `0x1800034b8`
- `0x180004270`
- `0x1800068d8`
- `0x1800078bc`

## callees

- `0x1800053f8`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005441`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005441`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005456`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005456`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000541d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000541d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000540c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000540c`

## string_xrefs

- `0x18000543a`: `ntdll.dll`

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
0x1800053f8  mov     [rsp+arg_0], rbx
0x1800053fd  mov     [rsp+arg_8], rsi
0x180005402  push    rdi
0x180005403  sub     rsp, 20h
0x180005407  mov     rbx, rdx
0x18000540a  mov     edi, ecx
0x18000540c  call    cs:__imp_GetProcessHeap
0x180005412  mov     r8, rbx; dwBytes
0x180005415  mov     edx, edi; dwFlags
0x180005417  mov     rcx, rax; hHeap
0x18000541a  mov     rsi, rax
0x18000541d  call    cs:__imp_HeapAlloc
0x180005423  mov     rbx, rax
0x180005426  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000542d  test    rax, rax
0x180005430  jnz     short loc_180005478
0x180005432  cmp     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, al; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005438  jnz     short loc_180005483
0x18000543a  lea     rcx, ModuleName; "ntdll.dll"
0x180005441  call    cs:__imp_GetModuleHandleW
0x180005447  test    rax, rax
0x18000544a  jz      short loc_180005465
0x18000544c  lea     rdx, aRtldisownmodul; "RtlDisownModuleHeapAllocation"
0x180005453  mov     rcx, rax; hModule
0x180005456  call    cs:__imp_GetProcAddress
0x18000545c  mov     cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA, rax
0x180005463  jmp     short loc_18000546C
0x180005465  mov     rax, cs:?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4P6AJPEAX1@_EEA
0x18000546c  mov     cs:?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,unsigned __int64)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x180005473  test    rax, rax
0x180005476  jz      short loc_180005483
0x180005478  mov     rdx, rbx
0x18000547b  mov     rcx, rsi
0x18000547e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005483  mov     rsi, [rsp+28h+arg_8]
0x180005488  mov     rax, rbx
0x18000548b  mov     rbx, [rsp+28h+arg_0]
0x180005490  add     rsp, 20h
0x180005494  pop     rdi
0x180005495  retn
```
