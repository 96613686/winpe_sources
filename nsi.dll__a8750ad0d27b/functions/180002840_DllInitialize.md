# _DllInitialize

- ea: `0x180002840`
- end: `0x1800028aa`
- name: `_DllInitialize`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180002800`

## callees

- `0x180002840`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000284d`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000284d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002884`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002897`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002884`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002897`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002853`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002853`

## pseudocode

```c
__int64 __fastcall DllInitialize(HMODULE a1, int a2)
{
  if ( a2 )
  {
    if ( a2 == 1 )
    {
      DisableThreadLibraryCalls(a1);
      g_NsiHeap = GetProcessHeap();
    }
  }
  else
  {
    if ( g_NsiDeviceHandle != (HANDLE)-1LL )
    {
      CloseHandle(g_NsiDeviceHandle);
      g_NsiDeviceHandle = (HANDLE)-1LL;
    }
    if ( g_NsiAsyncDeviceHandle != (HANDLE)-1LL )
    {
      CloseHandle(g_NsiAsyncDeviceHandle);
      g_NsiAsyncDeviceHandle = (HANDLE)-1LL;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180002840  sub     rsp, 28h
0x180002844  test    edx, edx
0x180002846  jz      short loc_18000286A
0x180002848  cmp     edx, 1
0x18000284b  jnz     short loc_180002860
0x18000284d  call    cs:__imp_DisableThreadLibraryCalls
0x180002853  call    cs:__imp_GetProcessHeap
0x180002859  mov     cs:g_NsiHeap, rax
0x180002860  mov     eax, 1
0x180002865  add     rsp, 28h
0x180002869  retn
0x18000286a  mov     rcx, cs:g_NsiDeviceHandle; hObject
0x180002871  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180002875  jnz     short loc_180002897
0x180002877  mov     rcx, cs:g_NsiAsyncDeviceHandle; hObject
0x18000287e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180002882  jz      short loc_180002860
0x180002884  call    cs:__imp_CloseHandle
0x18000288a  mov     cs:g_NsiAsyncDeviceHandle, 0FFFFFFFFFFFFFFFFh
0x180002895  jmp     short loc_180002860
0x180002897  call    cs:__imp_CloseHandle
0x18000289d  mov     cs:g_NsiDeviceHandle, 0FFFFFFFFFFFFFFFFh
0x1800028a8  jmp     short loc_180002877
```
