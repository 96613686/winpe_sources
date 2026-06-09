# SetAttrAndDeleteFile(wil::basic_zstring_view<wchar_t> const &)

- ea: `0x180010c74`
- end: `0x180010cae`
- name: `?SetAttrAndDeleteFile@@YAHAEBV?$basic_zstring_view@_W@wil@@@Z`
- size: `58`
- prototype: `BOOL __fastcall(LPCWSTR *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000d200`

## callees

- `0x180010358`
- `0x180010c74`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180010c9c`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180010c8e`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180010c8e`

## pseudocode

```c
BOOL __fastcall SetAttrAndDeleteFile(LPCWSTR *a1)
{
  if ( (unsigned int)FileDeleteHelper(a1) )
    return 1;
  SetFileAttributesW(*a1, 0x80u);
  return DeleteFileW(*a1);
}

```

## disassembly

```asm
0x180010c74  push    rbx
0x180010c76  sub     rsp, 20h
0x180010c7a  mov     rbx, rcx
0x180010c7d  call    FileDeleteHelper
0x180010c82  test    eax, eax
0x180010c84  jnz     short loc_180010CA3
0x180010c86  mov     rcx, [rbx]; lpFileName
0x180010c89  mov     edx, 80h; dwFileAttributes
0x180010c8e  call    cs:__imp_SetFileAttributesW
0x180010c94  mov     rcx, [rbx]
0x180010c97  add     rsp, 20h
0x180010c9b  pop     rbx
0x180010c9c  jmp     cs:__imp_DeleteFileW
0x180010ca3  mov     eax, 1
0x180010ca8  add     rsp, 20h
0x180010cac  pop     rbx
0x180010cad  retn
```
