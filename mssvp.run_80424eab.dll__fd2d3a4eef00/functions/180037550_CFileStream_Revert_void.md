# CFileStream::Revert(void)

- ea: `0x180037550`
- end: `0x180037571`
- name: `?Revert@CFileStream@@UEAAJXZ`
- size: `33`
- prototype: `__int64 __fastcall(CFileStream *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180037550`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180037561`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180037561`

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
0x180037550  sub     rsp, 28h
0x180037554  cmp     dword ptr [rcx+0C4h], 0
0x18003755b  jz      short loc_180037567
0x18003755d  mov     rcx, [rcx+28h]; lpFileName
0x180037561  call    cs:__imp_DeleteFileW
0x180037567  mov     eax, 1
0x18003756c  add     rsp, 28h
0x180037570  retn
```
