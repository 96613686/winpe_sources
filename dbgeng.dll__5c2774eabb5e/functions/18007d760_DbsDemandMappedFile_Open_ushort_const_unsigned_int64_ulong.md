# DbsDemandMappedFile::Open(ushort const *,unsigned __int64,ulong)

- ea: `0x18007d760`
- end: `0x18007d924`
- name: `?Open@DbsDemandMappedFile@@QEAAJPEBG_KK@Z`
- size: `452`
- prototype: `int(DbsDemandMappedFile *__hidden this, const unsigned __int16 *, unsigned __int64, unsigned int)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18029b670`
- `0x1802c9614`
- `0x1804b07f0`
- `0x1804b0810`

## callees

- `0x18007d760`
- `0x18007daa4`
- `0x1800c9620`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d847`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d847`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18007d7c1`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18007d7c1`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18007d834`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18007d834`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007d804`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007d804`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18007d894`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18007d894`

## pseudocode

```c
__int64 __fastcall DbsDemandMappedFile::Open(
        DbsDemandMappedFile *this,
        const unsigned __int16 *a2,
        char *FileW,
        int a4)
{
  DWORD FileSize; // eax
  __int64 v10; // rdi
  bool v11; // zf
  int Status; // edi
  HANDLE FileMappingW; // rax
  int v14; // ecx
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // rcx
  __int64 v17; // rsi
  DWORD FileSizeHigh; // [rsp+70h] [rbp+8h] BYREF

  if ( !(*(unsigned __int8 (__fastcall **)(DbsDemandMappedFile *))(*(_QWORD *)this + 16LL))(this) && a2 )
  {
    if ( !DbsDynamicString<unsigned short>::CopyStr((char *)this + 24, a2, 0xFFFFFFFFLL) )
      return 2147942414LL;
    if ( FileW )
    {
      if ( SetFilePointer(FileW, 0, 0, 0) == -1 )
        goto LABEL_20;
      *((_QWORD *)this + 15) = FileW;
    }
    else
    {
      FileW = (char *)CreateFileW(a2, 0x80000000, 7u, 0, 3u, 0x80u, 0);
      *((_QWORD *)this + 15) = FileW;
      if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      {
        *((_QWORD *)this + 15) = 0;
        goto LABEL_20;
      }
    }
    FileSizeHigh = 0;
    FileSize = GetFileSize(FileW, &FileSizeHigh);
    v10 = FileSize;
    if ( FileSize != -1 || !GetLastError() )
    {
      v11 = (v10 | ((unsigned __int64)FileSizeHigh << 32)) == 0;
      *((_QWORD *)this + 6) = v10 | ((unsigned __int64)FileSizeHigh << 32);
      if ( v11 )
      {
        Status = -805306082;
LABEL_21:
        (*(void (__fastcall **)(DbsDemandMappedFile *))(*(_QWORD *)this + 8LL))(this);
        return (unsigned int)Status;
      }
      FileMappingW = CreateFileMappingW(*((HANDLE *)this + 15), 0, 2u, 0, 0, 0);
      *((_QWORD *)this + 16) = FileMappingW;
      if ( FileMappingW )
      {
        v14 = *((_DWORD *)this + 4);
        v15 = *((_QWORD *)this + 6);
        *((_QWORD *)this + 7) = v15;
        v16 = (v14 + a4 - 1) & (unsigned int)-v14;
        if ( v15 < v16 )
          LODWORD(v16) = v15;
        v17 = (unsigned int)v16;
        if ( !(_DWORD)v16
          || (Status = (*(__int64 (__fastcall **)(DbsDemandMappedFile *, _QWORD, _QWORD, char *))(*(_QWORD *)this + 32LL))(
                         this,
                         0,
                         (unsigned int)v16,
                         (char *)this + 64),
              Status >= 0) )
        {
          *((_QWORD *)this + 9) = v17;
          return 0;
        }
        goto LABEL_21;
      }
    }
LABEL_20:
    Status = DbsLastStatus();
    goto LABEL_21;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18007d760  push    rbx
0x18007d762  push    rbp
0x18007d763  push    rsi
0x18007d764  push    rdi
0x18007d765  sub     rsp, 48h
0x18007d769  mov     rax, [rcx]
0x18007d76c  mov     ebp, r9d
0x18007d76f  mov     rdi, r8
0x18007d772  mov     rsi, rdx
0x18007d775  mov     rbx, rcx
0x18007d778  mov     rax, [rax+10h]
0x18007d77c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d781  test    al, al
0x18007d783  jnz     loc_18007D915
0x18007d789  test    rsi, rsi
0x18007d78c  jz      loc_18007D915
0x18007d792  lea     rcx, [rbx+18h]
0x18007d796  or      r8d, 0FFFFFFFFh
0x18007d79a  mov     rdx, rsi
0x18007d79d  call    ?CopyStr@?$DbsDynamicString@G@@QEAAPEAGPEBGK@Z; DbsDynamicString<ushort>::CopyStr(ushort const *,ulong)
0x18007d7a2  test    rax, rax
0x18007d7a5  jnz     short loc_18007D7B1
0x18007d7a7  mov     eax, 8007000Eh
0x18007d7ac  jmp     loc_18007D91A
0x18007d7b1  test    rdi, rdi
0x18007d7b4  jz      short loc_18007D7DC
0x18007d7b6  xor     r9d, r9d; dwMoveMethod
0x18007d7b9  xor     r8d, r8d; lpDistanceToMoveHigh
0x18007d7bc  xor     edx, edx; lDistanceToMove
0x18007d7be  mov     rcx, rdi; hFile
0x18007d7c1  call    cs:__imp_SetFilePointer
0x18007d7c8  nop     dword ptr [rax+rax+00h]
0x18007d7cd  cmp     eax, 0FFFFFFFFh
0x18007d7d0  jz      loc_18007D8FB
0x18007d7d6  mov     [rbx+78h], rdi
0x18007d7da  jmp     short loc_18007D824
0x18007d7dc  xor     r9d, r9d; lpSecurityAttributes
0x18007d7df  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18007d7e8  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18007d7f0  mov     edx, 80000000h; dwDesiredAccess
0x18007d7f5  mov     rcx, rsi; lpFileName
0x18007d7f8  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18007d800  lea     r8d, [r9+7]; dwShareMode
0x18007d804  call    cs:__imp_CreateFileW
0x18007d80b  nop     dword ptr [rax+rax+00h]
0x18007d810  mov     rdi, rax
0x18007d813  mov     [rbx+78h], rax
0x18007d817  dec     rax
0x18007d81a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18007d81e  ja      loc_18007D8F3
0x18007d824  lea     rdx, [rsp+68h+FileSizeHigh]; lpFileSizeHigh
0x18007d829  mov     [rsp+68h+FileSizeHigh], 0
0x18007d831  mov     rcx, rdi; hFile
0x18007d834  call    cs:__imp_GetFileSize
0x18007d83b  nop     dword ptr [rax+rax+00h]
0x18007d840  mov     edi, eax
0x18007d842  cmp     eax, 0FFFFFFFFh
0x18007d845  jnz     short loc_18007D85B
0x18007d847  call    cs:__imp_GetLastError
0x18007d84e  nop     dword ptr [rax+rax+00h]
0x18007d853  test    eax, eax
0x18007d855  jnz     loc_18007D8FB
0x18007d85b  mov     ecx, [rsp+68h+FileSizeHigh]
0x18007d85f  shl     rcx, 20h
0x18007d863  or      rcx, rdi
0x18007d866  mov     [rbx+30h], rcx
0x18007d86a  jnz     short loc_18007D876
0x18007d86c  mov     edi, 0D000011Eh
0x18007d871  jmp     loc_18007D902
0x18007d876  mov     rcx, [rbx+78h]; hFile
0x18007d87a  xor     r9d, r9d; dwMaximumSizeHigh
0x18007d87d  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], 0; lpName
0x18007d886  xor     edx, edx; lpFileMappingAttributes
0x18007d888  mov     [rsp+68h+dwCreationDisposition], 0; dwMaximumSizeLow
0x18007d890  lea     r8d, [r9+2]; flProtect
0x18007d894  call    cs:__imp_CreateFileMappingW
0x18007d89b  nop     dword ptr [rax+rax+00h]
0x18007d8a0  mov     [rbx+80h], rax
0x18007d8a7  test    rax, rax
0x18007d8aa  jz      short loc_18007D8FB
0x18007d8ac  mov     ecx, [rbx+10h]
0x18007d8af  lea     eax, [rbp-1]
0x18007d8b2  mov     rdx, [rbx+30h]
0x18007d8b6  add     eax, ecx
0x18007d8b8  neg     ecx
0x18007d8ba  mov     [rbx+38h], rdx
0x18007d8be  and     ecx, eax
0x18007d8c0  cmp     rdx, rcx
0x18007d8c3  jnb     short loc_18007D8C7
0x18007d8c5  mov     ecx, edx
0x18007d8c7  mov     esi, ecx
0x18007d8c9  test    ecx, ecx
0x18007d8cb  jz      short loc_18007D8EB
0x18007d8cd  mov     rax, [rbx]
0x18007d8d0  lea     r9, [rbx+40h]
0x18007d8d4  mov     r8d, esi
0x18007d8d7  xor     edx, edx
0x18007d8d9  mov     rcx, rbx
0x18007d8dc  mov     rax, [rax+20h]
0x18007d8e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d8e5  mov     edi, eax
0x18007d8e7  test    eax, eax
0x18007d8e9  js      short loc_18007D902
0x18007d8eb  mov     [rbx+48h], rsi
0x18007d8ef  xor     eax, eax
0x18007d8f1  jmp     short loc_18007D91A
0x18007d8f3  mov     qword ptr [rbx+78h], 0
0x18007d8fb  call    ?DbsLastStatus@@YAJXZ; DbsLastStatus(void)
0x18007d900  mov     edi, eax
0x18007d902  mov     rax, [rbx]
0x18007d905  mov     rcx, rbx
0x18007d908  mov     rax, [rax+8]
0x18007d90c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d911  mov     eax, edi
0x18007d913  jmp     short loc_18007D91A
0x18007d915  mov     eax, 80070057h
0x18007d91a  add     rsp, 48h
0x18007d91e  pop     rdi
0x18007d91f  pop     rsi
0x18007d920  pop     rbp
0x18007d921  pop     rbx
0x18007d922  retn
```
