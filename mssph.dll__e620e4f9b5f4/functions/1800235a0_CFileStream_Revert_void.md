# CFileStream::Revert(void)

- ea: `0x1800235a0`
- end: `0x1800235c1`
- name: `?Revert@CFileStream@@UEAAJXZ`
- size: `33`
- prototype: `__int64 __fastcall(LPCWSTR *this)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800235a0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800235b1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800235b1`

## pseudocode

```c
__int64 __fastcall CFileStream::Revert(LPCWSTR *this)
{
  if ( *((_DWORD *)this + 49) )
    DeleteFileW(this[5]);
  return 1;
}

```

## disassembly

```asm
0x1800235a0  sub     rsp, 28h
0x1800235a4  cmp     dword ptr [rcx+0C4h], 0
0x1800235ab  jz      short loc_1800235B7
0x1800235ad  mov     rcx, [rcx+28h]; lpFileName
0x1800235b1  call    cs:__imp_DeleteFileW
0x1800235b7  mov     eax, 1
0x1800235bc  add     rsp, 28h
0x1800235c0  retn
```
