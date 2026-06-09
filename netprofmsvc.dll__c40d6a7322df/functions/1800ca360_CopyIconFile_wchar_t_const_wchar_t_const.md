# CopyIconFile(wchar_t const *,wchar_t const *)

- ea: `0x1800ca360`
- end: `0x1800ca3b3`
- name: `?CopyIconFile@@YAKPEB_W0@Z`
- size: `83`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800ca3bc`

## callees

- `0x1800ca360`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca39e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca39e`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800ca396`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800ca396`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800ca37f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800ca37f`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800ca370`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800ca370`

## pseudocode

```c
__int64 __fastcall CopyIconFile(const wchar_t *a1, const wchar_t *a2)
{
  unsigned int v3; // ebx
  DWORD FileAttributesW; // eax

  if ( CopyFileW(a1, a2, 0) )
  {
    v3 = 0;
    FileAttributesW = GetFileAttributesW(a2);
    if ( FileAttributesW != -1 && (FileAttributesW & 1) != 0 )
      SetFileAttributesW(a2, FileAttributesW & 0xFFFFFFFE);
  }
  else
  {
    return GetLastError();
  }
  return v3;
}

```

## disassembly

```asm
0x1800ca360  mov     [rsp+arg_0], rbx
0x1800ca365  push    rdi
0x1800ca366  sub     rsp, 20h
0x1800ca36a  xor     r8d, r8d; bFailIfExists
0x1800ca36d  mov     rdi, rdx
0x1800ca370  call    cs:__imp_CopyFileW
0x1800ca376  test    eax, eax
0x1800ca378  jz      short loc_1800CA39E
0x1800ca37a  mov     rcx, rdi; lpFileName
0x1800ca37d  xor     ebx, ebx
0x1800ca37f  call    cs:__imp_GetFileAttributesW
0x1800ca385  cmp     eax, 0FFFFFFFFh
0x1800ca388  jz      short loc_1800CA3A6
0x1800ca38a  test    al, 1
0x1800ca38c  jz      short loc_1800CA3A6
0x1800ca38e  and     eax, 0FFFFFFFEh
0x1800ca391  mov     rcx, rdi; lpFileName
0x1800ca394  mov     edx, eax; dwFileAttributes
0x1800ca396  call    cs:__imp_SetFileAttributesW
0x1800ca39c  jmp     short loc_1800CA3A6
0x1800ca39e  call    cs:__imp_GetLastError
0x1800ca3a4  mov     ebx, eax
0x1800ca3a6  mov     eax, ebx
0x1800ca3a8  mov     rbx, [rsp+28h+arg_0]
0x1800ca3ad  add     rsp, 20h
0x1800ca3b1  pop     rdi
0x1800ca3b2  retn
```
