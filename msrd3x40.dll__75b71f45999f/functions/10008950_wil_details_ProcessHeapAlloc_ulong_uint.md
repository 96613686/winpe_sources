# wil::details::ProcessHeapAlloc(ulong,uint)

- ea: `0x10008950`
- end: `0x100089f7`
- name: `?ProcessHeapAlloc@details@wil@@YGPAXKI@Z`
- size: `167`
- prototype: `void *__usercall@<eax>(wil::details *__hidden this, unsigned int, unsigned int)`
- caller_count: `5`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1000a370`
- `0x1000a6c0`
- `0x1000a900`
- `0x1000f290`
- `0x1000f4b0`

## callees

- `0x10008950`
- `0x1000eb60`
- `0x1005e3b0`
- `0x1005f064`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x100089b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x100089b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x100089a6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x100089a6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x10008986`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x10008986`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1000897b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1000897b`

## string_xrefs

- `0x100089a1`: `ntdll.dll`

## pseudocode

```c
LPVOID __fastcall wil::details::ProcessHeapAlloc(DWORD a1, SIZE_T a2)
{
  HANDLE ProcessHeap; // ebx
  LPVOID result; // eax
  FARPROC RtlDisownModuleHeapAllocation; // esi
  void *v7; // edi
  HMODULE ModuleHandleW; // eax

  ProcessHeap = GetProcessHeap();
  result = HeapAlloc(ProcessHeap, a1, a2);
  RtlDisownModuleHeapAllocation = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation;
  v7 = result;
  if ( `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation )
    goto LABEL_7;
  if ( `wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation )
    return result;
  ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
  if ( ModuleHandleW )
  {
    RtlDisownModuleHeapAllocation = GetProcAddress(ModuleHandleW, "RtlDisownModuleHeapAllocation");
    `wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation = (int)RtlDisownModuleHeapAllocation;
  }
  else
  {
    RtlDisownModuleHeapAllocation = (FARPROC)`wil::details::ProcessHeapAlloc'::`2'::pfnRtlDisownModuleHeapAllocation;
  }
  `wil::details::ProcessHeapAlloc'::`2'::fetchedRtlDisownModuleHeapAllocation = 1;
  if ( RtlDisownModuleHeapAllocation )
LABEL_7:
    ((void (__thiscall *)(FARPROC, HANDLE, void *))RtlDisownModuleHeapAllocation)(
      RtlDisownModuleHeapAllocation,
      ProcessHeap,
      v7);
  return v7;
}

```

## disassembly

```asm
0x10008950  mov     edi, edi
0x10008952  push    ebp
0x10008953  mov     ebp, esp
0x10008955  push    0FFFFFFFFh
0x10008957  push    offset ??1CWin32FindDataInOut@@QAE@XZ_SEH
0x1000895c  mov     eax, large fs:0
0x10008962  push    eax
0x10008963  push    ebx
0x10008964  push    esi
0x10008965  push    edi
0x10008966  mov     eax, ___security_cookie
0x1000896b  xor     eax, ebp
0x1000896d  push    eax
0x1000896e  lea     eax, [ebp+var_C]
0x10008971  mov     large fs:0, eax
0x10008977  mov     esi, edx
0x10008979  mov     edi, ecx
0x1000897b  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x10008981  push    esi; dwBytes
0x10008982  mov     ebx, eax
0x10008984  push    edi; dwFlags
0x10008985  push    ebx; hHeap
0x10008986  call    ds:__imp__HeapAlloc@12; HeapAlloc(x,x,x)
0x1000898c  mov     esi, ?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YGPAXKI@Z@4P6GJPAX0@_EA
0x10008992  mov     edi, eax
0x10008994  test    esi, esi
0x10008996  jnz     short loc_100089D7
0x10008998  cmp     ?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YGPAXKI@Z@4_NA, 0; bool `wil::details::ProcessHeapAlloc(ulong,uint)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x1000899f  jnz     short loc_100089E5
0x100089a1  push    offset ModuleName; "ntdll.dll"
0x100089a6  call    ds:__imp__GetModuleHandleW@4; GetModuleHandleW(x)
0x100089ac  test    eax, eax
0x100089ae  jz      short loc_100089C6
0x100089b0  push    offset ProcName; "RtlDisownModuleHeapAllocation"
0x100089b5  push    eax; hModule
0x100089b6  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x100089bc  mov     esi, eax
0x100089be  mov     ?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YGPAXKI@Z@4P6GJPAX0@_EA, esi
0x100089c4  jmp     short loc_100089CC
0x100089c6  mov     esi, ?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YGPAXKI@Z@4P6GJPAX0@_EA
0x100089cc  mov     ?fetchedRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YGPAXKI@Z@4_NA, 1; bool `wil::details::ProcessHeapAlloc(ulong,uint)'::`2'::fetchedRtlDisownModuleHeapAllocation
0x100089d3  test    esi, esi
0x100089d5  jz      short loc_100089E3
0x100089d7  push    edi; unsigned int
0x100089d8  push    ebx; void *
0x100089d9  mov     ecx, esi
0x100089db  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100089e1  call    esi ; ?pfnRtlDisownModuleHeapAllocation@?1??ProcessHeapAlloc@details@wil@@YGPAXKI@Z@4P6GJPAX0@_EA
0x100089e3  mov     eax, edi
0x100089e5  mov     ecx, [ebp+var_C]
0x100089e8  mov     large fs:0, ecx
0x100089ef  pop     ecx
0x100089f0  pop     edi
0x100089f1  pop     esi
0x100089f2  pop     ebx
0x100089f3  mov     esp, ebp
0x100089f5  pop     ebp
0x100089f6  retn
0x1005f510  nop
0x1005f511  nop
0x1005f512  mov     edx, [esp-4+arg_4]
0x1005f516  lea     eax, [edx+0Ch]
0x1005f519  mov     ecx, [edx-10h]
0x1005f51c  xor     ecx, eax; StackCookie
0x1005f51e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1005f523  mov     eax, offset stru_10062AB0
0x1005f528  jmp     ___CxxFrameHandler3
```
