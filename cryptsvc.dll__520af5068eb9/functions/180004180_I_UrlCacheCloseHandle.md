# I_UrlCacheCloseHandle

- ea: `0x180004180`
- end: `0x1800041b6`
- name: `I_UrlCacheCloseHandle`
- size: `54`
- prototype: `void __fastcall(HANDLE hObject)`
- caller_count: `11`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002820`
- `0x180004c90`
- `0x180005bd0`
- `0x180006aa0`
- `0x180006d00`
- `0x180007980`
- `0x180007dc0`
- `0x180008a10`
- `0x180008df0`
- `0x18000a814`
- `0x18000fbec`

## callees

- `0x180004180`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004192`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004192`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800041a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800041a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000419d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000419d`

## pseudocode

```c
void __fastcall I_UrlCacheCloseHandle(HANDLE hObject)
{
  DWORD LastError; // edi

  if ( hObject )
  {
    LastError = GetLastError();
    CloseHandle(hObject);
    SetLastError(LastError);
  }
}

```

## disassembly

```asm
0x180004180  test    rcx, rcx
0x180004183  jz      short locret_1800041B5
0x180004185  push    rbx
0x180004186  sub     rsp, 20h
0x18000418a  mov     rbx, rcx
0x18000418d  mov     [rsp+28h+arg_0], rdi
0x180004192  call    cs:__imp_GetLastError
0x180004198  mov     rcx, rbx; hObject
0x18000419b  mov     edi, eax
0x18000419d  call    cs:__imp_CloseHandle
0x1800041a3  mov     ecx, edi; dwErrCode
0x1800041a5  call    cs:__imp_SetLastError
0x1800041ab  mov     rdi, [rsp+28h+arg_0]
0x1800041b0  add     rsp, 20h
0x1800041b4  pop     rbx
0x1800041b5  retn
```
