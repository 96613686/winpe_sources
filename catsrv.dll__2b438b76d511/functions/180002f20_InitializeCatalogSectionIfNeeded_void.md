# InitializeCatalogSectionIfNeeded(void)

- ea: `0x180002f20`
- end: `0x180002faf`
- name: `?InitializeCatalogSectionIfNeeded@@YAJXZ`
- size: `143`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800029c8`

## callees

- `0x180002f20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f92`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180002f80`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180002f80`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180002f3e`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180002f3e`

## string_xrefs

- `0x180002f32`: `Global\__ComCatalogCache__`

## pseudocode

```c
signed int InitializeCatalogSectionIfNeeded(void)
{
  HANDLE v0; // rax
  signed int result; // eax
  signed int v2; // ebx
  signed int LastError; // eax

  v0 = hObject;
  if ( hObject || (v0 = OpenFileMappingW(4u, 0, L"Global\\__ComCatalogCache__"), (hObject = v0) != 0) )
  {
    v2 = 0;
    if ( !lpBaseAddress )
    {
      lpBaseAddress = MapViewOfFile(v0, 4u, 0, 0, 0);
      if ( !lpBaseAddress )
      {
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError > 0 )
          return (unsigned __int16)LastError | 0x80070000;
      }
    }
    return v2;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180002f20  push    rbx
0x180002f22  sub     rsp, 30h
0x180002f26  mov     rax, cs:hObject
0x180002f2d  test    rax, rax
0x180002f30  jnz     short loc_180002F64
0x180002f32  lea     r8, Name; "Global\\__ComCatalogCache__"
0x180002f39  xor     edx, edx; bInheritHandle
0x180002f3b  lea     ecx, [rax+4]; dwDesiredAccess
0x180002f3e  call    cs:__imp_OpenFileMappingW
0x180002f44  mov     cs:hObject, rax
0x180002f4b  test    rax, rax
0x180002f4e  jnz     short loc_180002F64
0x180002f50  call    cs:__imp_GetLastError
0x180002f56  test    eax, eax
0x180002f58  jle     short loc_180002FA9
0x180002f5a  movzx   eax, ax
0x180002f5d  or      eax, 80070000h
0x180002f62  jmp     short loc_180002FA9
0x180002f64  xor     ebx, ebx
0x180002f66  cmp     cs:lpBaseAddress, rbx
0x180002f6d  jnz     short loc_180002FA7
0x180002f6f  xor     r9d, r9d; dwFileOffsetLow
0x180002f72  mov     [rsp+38h+dwNumberOfBytesToMap], rbx; dwNumberOfBytesToMap
0x180002f77  xor     r8d, r8d; dwFileOffsetHigh
0x180002f7a  lea     edx, [rbx+4]; dwDesiredAccess
0x180002f7d  mov     rcx, rax; hFileMappingObject
0x180002f80  call    cs:__imp_MapViewOfFile
0x180002f86  mov     cs:lpBaseAddress, rax
0x180002f8d  test    rax, rax
0x180002f90  jnz     short loc_180002FA7
0x180002f92  call    cs:__imp_GetLastError
0x180002f98  mov     ebx, eax
0x180002f9a  test    eax, eax
0x180002f9c  jle     short loc_180002FA7
0x180002f9e  movzx   ebx, ax
0x180002fa1  or      ebx, 80070000h
0x180002fa7  mov     eax, ebx
0x180002fa9  add     rsp, 30h
0x180002fad  pop     rbx
0x180002fae  retn
```
