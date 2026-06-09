# CryptSIPRetrieveSubjectGuidForCatalogFile

- ea: `0x1800241f0`
- end: `0x180024488`
- name: `CryptSIPRetrieveSubjectGuidForCatalogFile`
- size: `664`
- prototype: `BOOL __stdcall(LPCWSTR FileName, HANDLE hFileIn, GUID *pgSubject)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18002d430`

## callees

- `0x1800241f0`
- `0x1800248e0`
- `0x180024994`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024432`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024440`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024432`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024440`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002443a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024452`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002447d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002443a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024452`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002447d`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180024254`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180024254`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002440b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002440b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024370`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800243cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024370`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800243cc`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800242cc`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800242cc`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180024362`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180024362`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x180024284`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x180024284`

## pseudocode

```c
BOOL __stdcall CryptSIPRetrieveSubjectGuidForCatalogFile(LPCWSTR FileName, HANDLE hFileIn, GUID *pgSubject)
{
  char *FileW; // rsi
  HANDLE FileMappingA; // r12
  int v6; // r13d
  unsigned __int8 *v7; // r14
  BOOL v8; // r15d
  unsigned int v9; // eax
  DWORD v10; // edi
  DWORD LastError; // ecx
  union _LARGE_INTEGER FileSize; // [rsp+40h] [rbp-58h] BYREF
  unsigned __int8 *v14; // [rsp+48h] [rbp-50h]
  HANDLE v15; // [rsp+50h] [rbp-48h]
  int v16; // [rsp+58h] [rbp-40h]
  int v17; // [rsp+5Ch] [rbp-3Ch]
  int v18; // [rsp+60h] [rbp-38h]
  int v19; // [rsp+64h] [rbp-34h]
  unsigned int v20; // [rsp+B0h] [rbp+18h]

  FileW = (char *)hFileIn;
  FileSize.QuadPart = 0;
  FileMappingA = 0;
  v6 = 0;
  v7 = 0;
  if ( !pgSubject )
    goto LABEL_33;
  *pgSubject = 0;
  if ( (((unsigned __int64)hFileIn + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v8 = 1;
    goto LABEL_4;
  }
  if ( !FileName )
    goto LABEL_33;
  v8 = 1;
  FileW = (char *)CreateFileW(FileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( FileW != (char *)-1LL )
  {
    v6 = 1;
LABEL_4:
    if ( GetFileSizeEx(FileW, &FileSize) )
    {
      if ( FileSize.QuadPart < 4 )
      {
LABEL_24:
        pgSubject->Data1 = -566945214;
        *(_DWORD *)&pgSubject->Data2 = 298880601;
        *(_DWORD *)pgSubject->Data4 = -1073723508;
        *(_DWORD *)&pgSubject->Data4[4] = -292175281;
        v10 = -2147418113;
        goto LABEL_16;
      }
      FileMappingA = CreateFileMappingA(FileW, 0, 2u, 0, 0, 0);
      v15 = FileMappingA;
      if ( FileMappingA )
      {
        v9 = FileSize.QuadPart >= (unsigned int)I_CryptGetMaxHeaderBytesToMapRegValue()
           ? I_CryptGetMaxHeaderBytesToMapRegValue()
           : FileSize.LowPart;
        v20 = v9;
        v7 = (unsigned __int8 *)MapViewOfFile(FileMappingA, 4u, 0, 0, v9);
        v14 = v7;
        if ( v7 )
        {
          if ( *(_WORD *)v7 == 23117 && (unsigned int)_DetermineWhichPE(v7, v20, pgSubject) )
          {
            v10 = -2147418113;
            goto LABEL_16;
          }
          if ( *(_DWORD *)v7 == 1178817357 )
          {
            v16 = -964056390;
            v17 = 298880632;
            v18 = -1073723508;
            v19 = -292175281;
            pgSubject->Data1 = -964056390;
            *(_DWORD *)&pgSubject->Data2 = 298880632;
            *(_DWORD *)pgSubject->Data4 = -1073723508;
            *(_DWORD *)&pgSubject->Data4[4] = -292175281;
            v10 = -2147418113;
            goto LABEL_16;
          }
          goto LABEL_24;
        }
      }
      goto LABEL_31;
    }
LABEL_33:
    LastError = 87;
    goto LABEL_32;
  }
LABEL_31:
  LastError = GetLastError();
LABEL_32:
  SetLastError(LastError);
  v10 = GetLastError();
  v8 = 0;
LABEL_16:
  if ( v7 )
    UnmapViewOfFile(v7);
  if ( FileMappingA )
    CloseHandle(FileMappingA);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL && v6 )
    CloseHandle(FileW);
  if ( !v8 )
    SetLastError(v10);
  return v8;
}

```

## disassembly

```asm
0x1800241f0  mov     [rsp+arg_0], rsi
0x1800241f5  mov     [rsp+arg_8], rdx
0x1800241fa  push    rdi
0x1800241fb  push    r12
0x1800241fd  push    r13
0x1800241ff  push    r14
0x180024201  push    r15
0x180024203  sub     rsp, 70h
0x180024207  mov     rdi, r8
0x18002420a  mov     rsi, rdx
0x18002420d  mov     qword ptr [rsp+98h+FileSize], 0
0x180024216  xor     r12d, r12d
0x180024219  xor     r13d, r13d
0x18002421c  mov     [rsp+98h+arg_18], r13d
0x180024224  xor     r14d, r14d
0x180024227  test    r8, r8
0x18002422a  jz      loc_180024474
0x180024230  xorps   xmm0, xmm0
0x180024233  movups  xmmword ptr [r8], xmm0
0x180024237  lea     rax, [rdx+1]
0x18002423b  test    rax, 0FFFFFFFFFFFFFFFEh
0x180024241  jz      loc_1800243DE
0x180024247  lea     r15d, [r12+1]
0x18002424c  lea     rdx, [rsp+98h+FileSize]; lpFileSize
0x180024251  mov     rcx, rsi; hFile
0x180024254  call    cs:__imp_GetFileSizeEx
0x18002425a  test    eax, eax
0x18002425c  jz      loc_180024474
0x180024262  cmp     qword ptr [rsp+98h+FileSize], 4
0x180024268  jl      loc_1800243A2
0x18002426e  mov     [rsp+98h+lpName], r12; lpName
0x180024273  mov     [rsp+98h+dwMaximumSizeLow], r12d; dwMaximumSizeLow
0x180024278  xor     r9d, r9d; dwMaximumSizeHigh
0x18002427b  xor     edx, edx; lpFileMappingAttributes
0x18002427d  lea     r8d, [r9+2]; flProtect
0x180024281  mov     rcx, rsi; hFile
0x180024284  call    cs:__imp_CreateFileMappingA
0x18002428a  mov     r12, rax
0x18002428d  mov     [rsp+98h+var_48], rax
0x180024292  test    rax, rax
0x180024295  jz      loc_180024432
0x18002429b  call    I_CryptGetMaxHeaderBytesToMapRegValue
0x1800242a0  mov     ecx, eax
0x1800242a2  cmp     qword ptr [rsp+98h+FileSize], rcx
0x1800242a7  jge     loc_1800243D4
0x1800242ad  mov     eax, dword ptr [rsp+98h+FileSize]
0x1800242b1  mov     [rsp+98h+arg_10], eax
0x1800242b8  mov     ecx, eax
0x1800242ba  mov     qword ptr [rsp+98h+dwMaximumSizeLow], rcx; dwNumberOfBytesToMap
0x1800242bf  xor     r9d, r9d; dwFileOffsetLow
0x1800242c2  xor     r8d, r8d; dwFileOffsetHigh
0x1800242c5  lea     edx, [r9+4]; dwDesiredAccess
0x1800242c9  mov     rcx, r12; hFileMappingObject
0x1800242cc  call    cs:__imp_MapViewOfFile
0x1800242d2  mov     r14, rax
0x1800242d5  mov     [rsp+98h+var_50], rax
0x1800242da  test    rax, rax
0x1800242dd  jz      loc_180024432
0x1800242e3  mov     eax, 5A4Dh
0x1800242e8  cmp     [r14], ax
0x1800242ec  jnz     short loc_18002430B
0x1800242ee  mov     r8, rdi; struct _GUID *
0x1800242f1  mov     edx, [rsp+98h+arg_10]; unsigned int
0x1800242f8  mov     rcx, r14; unsigned __int8 *
0x1800242fb  call    ?_DetermineWhichPE@@YAHPEAEKPEAU_GUID@@@Z; _DetermineWhichPE(uchar *,ulong,_GUID *)
0x180024300  test    eax, eax
0x180024302  jz      short loc_18002430B
0x180024304  mov     edi, 8000FFFFh
0x180024309  jmp     short loc_18002435A
0x18002430b  cmp     dword ptr [r14], 4643534Dh
0x180024312  jnz     short loc_180024353
0x180024314  mov     ecx, 0C689AABAh
0x180024319  mov     [rsp+98h+var_40], ecx
0x18002431d  mov     [rsp+98h+var_3C], 11D08E78h
0x180024325  mov     [rsp+98h+var_38], 0C000478Ch
0x18002432d  mov     [rsp+98h+var_34], 0EE95C24Fh
0x180024335  mov     [rdi], ecx
0x180024337  mov     dword ptr [rdi+4], 11D08E78h
0x18002433e  mov     dword ptr [rdi+8], 0C000478Ch
0x180024345  mov     dword ptr [rdi+0Ch], 0EE95C24Fh
0x18002434c  mov     edi, 8000FFFFh
0x180024351  jmp     short loc_18002435A
0x180024353  jmp     short loc_1800243A2
0x180024355  jmp     loc_180024450
0x18002435a  test    r14, r14
0x18002435d  jz      short loc_180024368
0x18002435f  mov     rcx, r14; lpBaseAddress
0x180024362  call    cs:__imp_UnmapViewOfFile
0x180024368  test    r12, r12
0x18002436b  jz      short loc_180024376
0x18002436d  mov     rcx, r12; hObject
0x180024370  call    cs:__imp_CloseHandle
0x180024376  lea     rax, [rsi-1]
0x18002437a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002437e  jbe     short loc_1800243C4
0x180024380  test    r15d, r15d
0x180024383  jz      loc_18002447B
0x180024389  mov     eax, r15d
0x18002438c  mov     rsi, [rsp+98h+arg_0]
0x180024394  add     rsp, 70h
0x180024398  pop     r15
0x18002439a  pop     r14
0x18002439c  pop     r13
0x18002439e  pop     r12
0x1800243a0  pop     rdi
0x1800243a1  retn
0x1800243a2  mov     dword ptr [rdi], 0DE351A42h
0x1800243a8  mov     dword ptr [rdi+4], 11D08E59h
0x1800243af  mov     dword ptr [rdi+8], 0C000478Ch
0x1800243b6  mov     dword ptr [rdi+0Ch], 0EE95C24Fh
0x1800243bd  mov     edi, 8000FFFFh
0x1800243c2  jmp     short loc_18002435A
0x1800243c4  test    r13d, r13d
0x1800243c7  jz      short loc_180024380
0x1800243c9  mov     rcx, rsi; hObject
0x1800243cc  call    cs:__imp_CloseHandle
0x1800243d2  jmp     short loc_180024380
0x1800243d4  call    I_CryptGetMaxHeaderBytesToMapRegValue
0x1800243d9  jmp     loc_1800242B1
0x1800243de  test    rcx, rcx
0x1800243e1  jz      loc_180024474
0x1800243e7  mov     [rsp+98h+hTemplateFile], r12; hTemplateFile
0x1800243ec  mov     dword ptr [rsp+98h+lpName], 80h; dwFlagsAndAttributes
0x1800243f4  mov     [rsp+98h+dwMaximumSizeLow], 3; dwCreationDisposition
0x1800243fc  xor     r9d, r9d; lpSecurityAttributes
0x1800243ff  lea     r15d, [r9+1]
0x180024403  mov     r8d, r15d; dwShareMode
0x180024406  mov     edx, 80000000h; dwDesiredAccess
0x18002440b  call    cs:__imp_CreateFileW
0x180024411  mov     rsi, rax
0x180024414  mov     [rsp+98h+arg_8], rax
0x18002441c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180024420  jz      short loc_180024432
0x180024422  mov     r13d, r15d
0x180024425  mov     [rsp+98h+arg_18], r15d
0x18002442d  jmp     loc_18002424C
0x180024432  call    cs:__imp_GetLastError
0x180024438  mov     ecx, eax; dwErrCode
0x18002443a  call    cs:__imp_SetLastError
0x180024440  call    cs:__imp_GetLastError
0x180024446  mov     edi, eax
0x180024448  xor     r15d, r15d
0x18002444b  jmp     loc_18002435A
0x180024450  mov     ecx, eax; dwErrCode
0x180024452  call    cs:__imp_SetLastError
0x180024458  mov     rsi, [rsp+98h+arg_8]
0x180024460  mov     r14, [rsp+98h+var_50]
0x180024465  mov     r12, [rsp+98h+var_48]
0x18002446a  mov     r13d, [rsp+98h+arg_18]
0x180024472  jmp     short loc_180024440
0x180024474  mov     ecx, 57h ; 'W'
0x180024479  jmp     short loc_18002443A
0x18002447b  mov     ecx, edi; dwErrCode
0x18002447d  call    cs:__imp_SetLastError
0x180024483  jmp     loc_180024389
```
