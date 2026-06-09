# _waccess_s

- ea: `0x180008e90`
- end: `0x180008f29`
- name: `_waccess_s`
- size: `153`
- prototype: `errno_t __cdecl(const wchar_t *FileName, int AccessMode)`
- caller_count: `9`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180008e70`
- `0x18001a300`
- `0x18001ad60`
- `0x18001b370`
- `0x180022674`
- `0x180031940`
- `0x18004f410`
- `0x18004fe20`
- `0x18005011c`

## callees

- `0x180007e80`
- `0x180007ea8`
- `0x180007f00`
- `0x180008e90`
- `0x18002f050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ee3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ee3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180008ed8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180008ed8`

## pseudocode

```c
errno_t __cdecl waccess_s(const wchar_t *FileName, int AccessMode)
{
  char v2; // bl
  DWORD FileAttributesW; // eax
  DWORD LastError; // eax

  v2 = AccessMode;
  if ( !FileName || (AccessMode & 0xFFFFFFF0) != 0 )
  {
    *_doserrno() = 0;
    *errno() = 22;
    invalid_parameter(0, 0, 0, 0, 0);
  }
  FileAttributesW = GetFileAttributesW(FileName);
  if ( FileAttributesW == -1 )
  {
    LastError = GetLastError();
    dosmaperr(LastError);
    return *errno();
  }
  else if ( (FileAttributesW & 0x10) == 0 && (FileAttributesW & 1) != 0 && (v2 & 2) != 0 )
  {
    *_doserrno() = 5;
    *errno() = 13;
    return 13;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180008e90  push    rbx
0x180008e92  sub     rsp, 30h
0x180008e96  mov     ebx, edx
0x180008e98  test    rcx, rcx
0x180008e9b  jnz     short loc_180008ED0
0x180008e9d  call    __doserrno
0x180008ea2  mov     dword ptr [rax], 0
0x180008ea8  call    _errno
0x180008ead  mov     ebx, 16h
0x180008eb2  mov     [rsp+38h+Reserved], 0; Reserved
0x180008ebb  xor     r9d, r9d; LineNo
0x180008ebe  xor     r8d, r8d; FileName
0x180008ec1  xor     edx, edx; FunctionName
0x180008ec3  xor     ecx, ecx; Expression
0x180008ec5  mov     [rax], ebx
0x180008ec7  call    _invalid_parameter
0x180008ecc  mov     eax, ebx
0x180008ece  jmp     short loc_180008F23
0x180008ed0  test    ebx, 0FFFFFFF0h
0x180008ed6  jnz     short loc_180008E9D
0x180008ed8  call    cs:__imp_GetFileAttributesW
0x180008ede  cmp     eax, 0FFFFFFFFh
0x180008ee1  jnz     short loc_180008EF9
0x180008ee3  call    cs:__imp_GetLastError
0x180008ee9  mov     ecx, eax
0x180008eeb  call    _dosmaperr
0x180008ef0  call    _errno
0x180008ef5  mov     eax, [rax]
0x180008ef7  jmp     short loc_180008F23
0x180008ef9  test    al, 10h
0x180008efb  jnz     short loc_180008F21
0x180008efd  test    al, 1
0x180008eff  jz      short loc_180008F21
0x180008f01  test    bl, 2
0x180008f04  jz      short loc_180008F21
0x180008f06  call    __doserrno
0x180008f0b  mov     dword ptr [rax], 5
0x180008f11  call    _errno
0x180008f16  mov     ecx, 0Dh
0x180008f1b  mov     [rax], ecx
0x180008f1d  mov     eax, ecx
0x180008f1f  jmp     short loc_180008F23
0x180008f21  xor     eax, eax
0x180008f23  add     rsp, 30h
0x180008f27  pop     rbx
0x180008f28  retn
```
