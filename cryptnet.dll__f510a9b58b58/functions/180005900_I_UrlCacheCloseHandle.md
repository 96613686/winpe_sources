# I_UrlCacheCloseHandle

- ea: `0x180005900`
- end: `0x180005936`
- name: `I_UrlCacheCloseHandle`
- size: `54`
- prototype: `void __fastcall(HANDLE hObject)`
- caller_count: `12`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001154`
- `0x180001460`
- `0x1800015bc`
- `0x180001798`
- `0x180001878`
- `0x180002460`
- `0x180003274`
- `0x180004b40`
- `0x1800052d0`
- `0x180019334`
- `0x18001f054`
- `0x18001f480`

## callees

- `0x180005900`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005925`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005925`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005912`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005912`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000591d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000591d`

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
0x180005900  test    rcx, rcx
0x180005903  jz      short locret_180005935
0x180005905  push    rbx
0x180005906  sub     rsp, 20h
0x18000590a  mov     rbx, rcx
0x18000590d  mov     [rsp+28h+arg_0], rdi
0x180005912  call    cs:__imp_GetLastError
0x180005918  mov     rcx, rbx; hObject
0x18000591b  mov     edi, eax
0x18000591d  call    cs:__imp_CloseHandle
0x180005923  mov     ecx, edi; dwErrCode
0x180005925  call    cs:__imp_SetLastError
0x18000592b  mov     rdi, [rsp+28h+arg_0]
0x180005930  add     rsp, 20h
0x180005934  pop     rbx
0x180005935  retn
```
