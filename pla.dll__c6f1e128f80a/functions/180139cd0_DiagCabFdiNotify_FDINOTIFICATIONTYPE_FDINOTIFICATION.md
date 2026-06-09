# DiagCabFdiNotify(FDINOTIFICATIONTYPE,FDINOTIFICATION *)

- ea: `0x180139cd0`
- end: `0x180139f69`
- name: `?DiagCabFdiNotify@@YA_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@Z`
- size: `665`
- prototype: `INT_PTR __fastcall(FDINOTIFICATIONTYPE fdint, PFDINOTIFICATION pfdin)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180138858`
- `0x180139cd0`
- `0x18013a9a8`
- `0x18013aeb2`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `msvcrt!_close` at `0x180139e19`
- `msvcrt!_close` at `0x180139e19`
- `msvcrt!_wopen` at `0x180139f3b`
- `msvcrt!_wopen` at `0x180139f3b`
- `msvcrt!_get_osfhandle` at `0x180139d8d`
- `msvcrt!_get_osfhandle` at `0x180139d8d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x180139d68`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x180139d68`
- `api-ms-win-core-file-l1-1-0!LocalFileTimeToFileTime` at `0x180139d80`
- `api-ms-win-core-file-l1-1-0!LocalFileTimeToFileTime` at `0x180139d80`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180139e9e`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180139ec6`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180139e9e`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180139ec6`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180139da5`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180139da5`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180139e10`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180139e10`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180139dd0`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180139e4f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180139dd0`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180139e4f`

## pseudocode

```c
INT_PTR __fastcall DiagCabFdiNotify(FDINOTIFICATIONTYPE fdint, PFDINOTIFICATION pfdin)
{
  void *pv; // r14
  int v4; // ebx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  void *osfhandle; // rax
  signed int FullPathNameW; // eax
  signed int v11; // eax
  size_t v12; // r8
  unsigned __int64 v13; // rax
  struct _FILETIME FileTime; // [rsp+30h] [rbp-D0h] BYREF
  FILETIME LastWriteTime; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR FilePart[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR WideCharStr[264]; // [rsp+260h] [rbp+160h] BYREF
  wchar_t Buffer[264]; // [rsp+470h] [rbp+370h] BYREF
  wchar_t String1[264]; // [rsp+680h] [rbp+580h] BYREF

  pv = pfdin->pv;
  LastWriteTime = 0;
  FileTime = 0;
  FilePart[0] = 0;
  if ( fdint == fdintCABINET_INFO )
    return 0;
  v4 = -1;
  v5 = fdint - 1;
  if ( !v5 )
    return -1;
  v6 = v5 - 1;
  if ( !v6 )
  {
    if ( MultiByteToWideChar(0xFDE9u, 8u, pfdin->psz1, -1, WideCharStr, 260) )
    {
      if ( (int)StringCbPrintfW(FileName, 0x208u, L"%s\\%s", *((_QWORD *)pv + 2), WideCharStr) < 0 )
      {
LABEL_29:
        if ( *(_QWORD *)pv )
          (*(void (__fastcall **)(WCHAR *, _QWORD))pv)(FileName, *((_QWORD *)pv + 1));
        return v4;
      }
      FullPathNameW = GetFullPathNameW(FileName, 0x104u, Buffer, FilePart);
      if ( FullPathNameW )
      {
        if ( FullPathNameW <= 260 )
        {
          v11 = GetFullPathNameW(*((LPCWSTR *)pv + 2), 0x104u, String1, FilePart);
          if ( v11 )
          {
            if ( v11 <= 260 )
            {
              v12 = -1;
              do
                ++v12;
              while ( String1[v12] );
              v13 = -1;
              do
                ++v13;
              while ( Buffer[v13] );
              if ( v12 <= v13 && !wcsncmp_0(String1, Buffer, v12) )
              {
                if ( (int)DiagCreatePath(FileName) >= 0 )
                  v4 = _wopen(FileName, 33025, 0);
                goto LABEL_29;
              }
            }
          }
        }
      }
    }
    return -1;
  }
  v7 = v6 - 1;
  if ( v7 )
  {
    if ( v7 != 1 )
      return 0;
    return -1;
  }
  if ( DosDateTimeToFileTime(pfdin->date, pfdin->time, &FileTime) )
  {
    if ( LocalFileTimeToFileTime(&FileTime, &LastWriteTime) )
    {
      osfhandle = (void *)_get_osfhandle(pfdin->hf);
      if ( osfhandle != (void *)-1LL )
        SetFileTime(osfhandle, 0, 0, &LastWriteTime);
    }
  }
  if ( MultiByteToWideChar(0xFDE9u, 8u, pfdin->psz1, -1, WideCharStr, 260) )
  {
    if ( (int)StringCbPrintfW(FileName, 0x208u, L"%s\\%s", *((_QWORD *)pv + 2), WideCharStr) >= 0 )
      SetFileAttributesW(FileName, pfdin->attribs & 0x27);
  }
  _close(pfdin->hf);
  return 1;
}

```

## disassembly

```asm
0x180139cd0  push    rbp
0x180139cd2  push    rbx
0x180139cd3  push    rsi
0x180139cd4  push    rdi
0x180139cd5  push    r14
0x180139cd7  push    r15
0x180139cd9  lea     rbp, [rsp-7A8h]
0x180139ce1  sub     rsp, 8A8h
0x180139ce8  mov     rax, cs:__security_cookie
0x180139cef  xor     rax, rsp
0x180139cf2  mov     [rbp+7D0h+var_40], rax
0x180139cf9  mov     r14, [rdx+20h]
0x180139cfd  xor     r15d, r15d
0x180139d00  mov     qword ptr [rsp+8D0h+LastWriteTime.dwLowDateTime], r15
0x180139d05  mov     rdi, rdx
0x180139d08  mov     qword ptr [rsp+8D0h+FileTime.dwLowDateTime], r15
0x180139d0d  mov     [rsp+8D0h+FilePart], r15
0x180139d12  test    ecx, ecx
0x180139d14  jz      short loc_180139D3A
0x180139d16  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180139d1a  sub     ecx, 1
0x180139d1d  jz      loc_180139F61
0x180139d23  sub     ecx, 1
0x180139d26  jz      loc_180139E29
0x180139d2c  sub     ecx, 1
0x180139d2f  jz      short loc_180139D5B
0x180139d31  cmp     ecx, 1
0x180139d34  jz      loc_180139F61
0x180139d3a  xor     eax, eax
0x180139d3c  mov     rcx, [rbp+7D0h+var_40]
0x180139d43  xor     rcx, rsp; StackCookie
0x180139d46  call    __security_check_cookie
0x180139d4b  add     rsp, 8A8h
0x180139d52  pop     r15
0x180139d54  pop     r14
0x180139d56  pop     rdi
0x180139d57  pop     rsi
0x180139d58  pop     rbx
0x180139d59  pop     rbp
0x180139d5a  retn
0x180139d5b  movzx   edx, word ptr [rdx+32h]; wFatTime
0x180139d5f  lea     r8, [rsp+8D0h+FileTime]; lpFileTime
0x180139d64  movzx   ecx, word ptr [rdi+30h]; wFatDate
0x180139d68  call    cs:__imp_DosDateTimeToFileTime
0x180139d6e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180139d72  test    eax, eax
0x180139d74  jz      short loc_180139DAB
0x180139d76  lea     rdx, [rsp+8D0h+LastWriteTime]; lpFileTime
0x180139d7b  lea     rcx, [rsp+8D0h+FileTime]; lpLocalFileTime
0x180139d80  call    cs:__imp_LocalFileTimeToFileTime
0x180139d86  test    eax, eax
0x180139d88  jz      short loc_180139DAB
0x180139d8a  mov     ecx, [rdi+28h]; FileHandle
0x180139d8d  call    cs:__imp__get_osfhandle
0x180139d93  cmp     rax, rbx
0x180139d96  jz      short loc_180139DAB
0x180139d98  lea     r9, [rsp+8D0h+LastWriteTime]; lpLastWriteTime
0x180139d9d  xor     r8d, r8d; lpLastAccessTime
0x180139da0  xor     edx, edx; lpCreationTime
0x180139da2  mov     rcx, rax; hFile
0x180139da5  call    cs:__imp_SetFileTime
0x180139dab  mov     r8, [rdi+8]; lpMultiByteStr
0x180139daf  lea     rax, [rbp+7D0h+WideCharStr]
0x180139db6  mov     [rsp+8D0h+cchWideChar], 104h; cchWideChar
0x180139dbe  mov     r9d, ebx; cbMultiByte
0x180139dc1  mov     edx, 8; dwFlags
0x180139dc6  mov     [rsp+8D0h+lpWideCharStr], rax; lpWideCharStr
0x180139dcb  mov     ecx, 0FDE9h; CodePage
0x180139dd0  call    cs:__imp_MultiByteToWideChar
0x180139dd6  test    eax, eax
0x180139dd8  jz      short loc_180139E16
0x180139dda  mov     r9, [r14+10h]
0x180139dde  lea     rax, [rbp+7D0h+WideCharStr]
0x180139de5  lea     r8, aSS_0; "%s\\%s"
0x180139dec  mov     [rsp+8D0h+lpWideCharStr], rax
0x180139df1  mov     edx, 208h; unsigned __int64
0x180139df6  lea     rcx, [rsp+8D0h+FileName]; unsigned __int16 *
0x180139dfb  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180139e00  test    eax, eax
0x180139e02  js      short loc_180139E16
0x180139e04  movzx   edx, word ptr [rdi+34h]
0x180139e08  lea     rcx, [rsp+8D0h+FileName]; lpFileName
0x180139e0d  and     edx, 27h; dwFileAttributes
0x180139e10  call    cs:__imp_SetFileAttributesW
0x180139e16  mov     ecx, [rdi+28h]; FileHandle
0x180139e19  call    cs:__imp__close
0x180139e1f  mov     eax, 1
0x180139e24  jmp     loc_180139D3C
0x180139e29  mov     r8, [rdx+8]; lpMultiByteStr
0x180139e2d  lea     rax, [rbp+7D0h+WideCharStr]
0x180139e34  mov     esi, 104h
0x180139e39  mov     r9d, ebx; cbMultiByte
0x180139e3c  mov     [rsp+8D0h+cchWideChar], esi; cchWideChar
0x180139e40  mov     edx, 8; dwFlags
0x180139e45  mov     ecx, 0FDE9h; CodePage
0x180139e4a  mov     [rsp+8D0h+lpWideCharStr], rax; lpWideCharStr
0x180139e4f  call    cs:__imp_MultiByteToWideChar
0x180139e55  test    eax, eax
0x180139e57  jz      loc_180139F61
0x180139e5d  mov     r9, [r14+10h]
0x180139e61  lea     rax, [rbp+7D0h+WideCharStr]
0x180139e68  lea     r8, aSS_0; "%s\\%s"
0x180139e6f  mov     [rsp+8D0h+lpWideCharStr], rax
0x180139e74  mov     edx, 208h; unsigned __int64
0x180139e79  lea     rcx, [rsp+8D0h+FileName]; unsigned __int16 *
0x180139e7e  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180139e83  test    eax, eax
0x180139e85  js      loc_180139F43
0x180139e8b  lea     r9, [rsp+8D0h+FilePart]; lpFilePart
0x180139e90  mov     edx, esi; nBufferLength
0x180139e92  lea     r8, [rbp+7D0h+Buffer]; lpBuffer
0x180139e99  lea     rcx, [rsp+8D0h+FileName]; lpFileName
0x180139e9e  call    cs:__imp_GetFullPathNameW
0x180139ea4  test    eax, eax
0x180139ea6  jz      loc_180139F61
0x180139eac  cmp     eax, esi
0x180139eae  jg      loc_180139F61
0x180139eb4  mov     rcx, [r14+10h]; lpFileName
0x180139eb8  lea     r9, [rsp+8D0h+FilePart]; lpFilePart
0x180139ebd  lea     r8, [rbp+7D0h+String1]; lpBuffer
0x180139ec4  mov     edx, esi; nBufferLength
0x180139ec6  call    cs:__imp_GetFullPathNameW
0x180139ecc  test    eax, eax
0x180139ece  jz      loc_180139F61
0x180139ed4  cmp     eax, esi
0x180139ed6  jg      loc_180139F61
0x180139edc  lea     rax, [rbp+7D0h+String1]
0x180139ee3  mov     r8, rbx
0x180139ee6  inc     r8; MaxCount
0x180139ee9  cmp     [rax+r8*2], r15w
0x180139eee  jnz     short loc_180139EE6
0x180139ef0  lea     rcx, [rbp+7D0h+Buffer]
0x180139ef7  mov     rax, rbx
0x180139efa  inc     rax
0x180139efd  cmp     [rcx+rax*2], r15w
0x180139f02  jnz     short loc_180139EFA
0x180139f04  cmp     r8, rax
0x180139f07  ja      short loc_180139F61
0x180139f09  lea     rdx, [rbp+7D0h+Buffer]; String2
0x180139f10  lea     rcx, [rbp+7D0h+String1]; String1
0x180139f17  call    wcsncmp_0
0x180139f1c  test    eax, eax
0x180139f1e  jnz     short loc_180139F61
0x180139f20  lea     rcx, [rsp+8D0h+FileName]; lpPathName
0x180139f25  call    ?DiagCreatePath@@YAJPEAG@Z; DiagCreatePath(ushort *)
0x180139f2a  test    eax, eax
0x180139f2c  js      short loc_180139F43
0x180139f2e  xor     r8d, r8d
0x180139f31  lea     rcx, [rsp+8D0h+FileName]; FileName
0x180139f36  mov     edx, 8101h; OpenFlag
0x180139f3b  call    cs:__imp__wopen
0x180139f41  mov     ebx, eax
0x180139f43  mov     rax, [r14]
0x180139f46  test    rax, rax
0x180139f49  jz      short loc_180139F59
0x180139f4b  mov     rdx, [r14+8]
0x180139f4f  lea     rcx, [rsp+8D0h+FileName]
0x180139f54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139f59  movsxd  rax, ebx
0x180139f5c  jmp     loc_180139D3C
0x180139f61  mov     rax, rbx
0x180139f64  jmp     loc_180139D3C
```
