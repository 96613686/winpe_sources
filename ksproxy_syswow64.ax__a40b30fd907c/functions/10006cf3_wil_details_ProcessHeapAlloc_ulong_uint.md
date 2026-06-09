# wil::details::ProcessHeapAlloc(ulong,uint)

- ea: `0x10006cf3`
- end: `0x10006d6a`
- name: `?ProcessHeapAlloc@details@wil@@YGPAXKI@Z`
- size: `119`
- prototype: `LPVOID __fastcall(DWORD, SIZE_T)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x10007bcd`
- `0x10007d55`
- `0x1000fcc8`

## callees

- `0x10006cf3`
- `0x1002d510`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x10006d07`
- `KERNEL32!HeapAlloc` at `0x10006d07`
- `KERNEL32!GetProcAddress` at `0x10006d37`
- `KERNEL32!GetProcAddress` at `0x10006d37`
- `KERNEL32!GetProcessHeap` at `0x10006cfc`
- `KERNEL32!GetProcessHeap` at `0x10006cfc`
- `KERNEL32!GetModuleHandleW` at `0x10006d27`
- `KERNEL32!GetModuleHandleW` at `0x10006d27`

## string_xrefs

- `0x10006d22`: `ntdll.dll`

## pseudocode

```c
LPVOID __fastcall wil::details::ProcessHeapAlloc(DWORD a1, SIZE_T a2)
{
  HANDLE ProcessHeap; // ebx
  LPVOID v5; // eax
  FARPROC RtlDisownModuleHeapAllocation; // esi
  LPVOID v7; // edi
  HMODULE ModuleHandleW; // eax

  ProcessHeap = GetProcessHeap();
  v5 = HeapAlloc(ProcessHeap, a1, a2);
  RtlDisownModuleHeapAllocation = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation;
  v7 = v5;
  if ( `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation
    || !`wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation
    && ((ModuleHandleW = GetModuleHandleW(L"ntdll.dll")) == 0
      ? (RtlDisownModuleHeapAllocation = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation)
      : (FARPROC)(RtlDisownModuleHeapAllocation = GetProcAddress(ModuleHandleW, "RtlDisownModuleHeapAllocation"),
                  `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation = (CD3DSurfaceAllocator *)RtlDisownModuleHeapAllocation),
        `wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation = 1,
        RtlDisownModuleHeapAllocation) )
  {
    ((void (__thiscall *)(FARPROC, HANDLE, LPVOID))RtlDisownModuleHeapAllocation)(
      RtlDisownModuleHeapAllocation,
      ProcessHeap,
      v7);
  }
  return v7;
}

```

## disassembly

```asm
0x10006cf3  mov     edi, edi
0x10006cf5  push    ebx
0x10006cf6  push    esi
0x10006cf7  push    edi
0x10006cf8  mov     esi, edx
0x10006cfa  mov     edi, ecx
0x10006cfc  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x10006d02  push    esi; dwBytes
0x10006d03  mov     ebx, eax
0x10006d05  push    edi; dwFlags
0x10006d06  push    ebx; hHeap
0x10006d07  call    ds:__imp__HeapAlloc@12; HeapAlloc(x,x,x)
0x10006d0d  mov     esi, ?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YGPAXKI@Z@4P6GJPAX0@_EA
0x10006d13  mov     edi, eax
0x10006d15  test    esi, esi
0x10006d17  jnz     short loc_10006D58
0x10006d19  cmp     ?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YGPAXKI@Z@4_NA, 0; bool `wil::details::ProcessHeapAlloc(ulong,uint)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x10006d20  jnz     short loc_10006D64
0x10006d22  push    offset ModuleName; "ntdll.dll"
0x10006d27  call    ds:__imp__GetModuleHandleW@4; GetModuleHandleW(x)
0x10006d2d  test    eax, eax
0x10006d2f  jz      short loc_10006D47
0x10006d31  push    offset ProcName; "RtlDisownModuleHeapAllocation"
0x10006d36  push    eax; hModule
0x10006d37  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x10006d3d  mov     esi, eax
0x10006d3f  mov     ?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YGPAXKI@Z@4P6GJPAX0@_EA, esi
0x10006d45  jmp     short loc_10006D4D
0x10006d47  mov     esi, ?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YGPAXKI@Z@4P6GJPAX0@_EA
0x10006d4d  mov     ?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YGPAXKI@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,uint)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x10006d54  test    esi, esi
0x10006d56  jz      short loc_10006D64
0x10006d58  push    edi
0x10006d59  push    ebx
0x10006d5a  mov     ecx, esi; this
0x10006d5c  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10006d62  call    esi ; ?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YGPAXKI@Z@4P6GJPAX0@_EA
0x10006d64  mov     eax, edi
0x10006d66  pop     edi
0x10006d67  pop     esi
0x10006d68  pop     ebx
0x10006d69  retn
```
