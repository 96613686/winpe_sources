# notification_function

- ea: `0x18002b1f0`
- end: `0x18002b5b5`
- name: `notification_function`
- size: `965`
- prototype: `INT_PTR __cdecl(FDINOTIFICATIONTYPE fdint, PFDINOTIFICATION pfdin)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x18001ec1c`
- `0x18002a790`
- `0x18002ab00`
- `0x18002b1f0`
- `0x180055550`
- `0x180055610`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002b477`
- `msvcrt!_wcsicmp` at `0x18002b477`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b3ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b3ad`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002b51a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002b568`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002b51a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002b568`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002b268`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002b2c1`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002b3fe`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002b453`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002b268`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002b2c1`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002b3fe`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002b453`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18002b2d3`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18002b31e`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18002b489`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18002b4d4`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18002b2d3`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18002b31e`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18002b489`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18002b4d4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002b369`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002b369`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002b3ba`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002b3ba`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18002b3a4`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18002b3a4`
- `KERNEL32!DosDateTimeToFileTime` at `0x18002b38b`
- `KERNEL32!DosDateTimeToFileTime` at `0x18002b38b`

## pseudocode

```c
INT_PTR __fastcall notification_function(FDINOTIFICATIONTYPE fdint, PFDINOTIFICATION pfdin)
{
  int v3; // ecx
  int v4; // ecx
  int cchWideChar; // eax
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // rcx
  void *v8; // rsp
  void *v9; // rsp
  DWORD v10; // ecx
  __int64 v11; // rax
  signed int v12; // ecx
  unsigned __int64 v13; // r14
  unsigned __int64 v14; // rax
  __int64 v15; // rdx
  unsigned __int64 v16; // rdx
  void *v17; // rsp
  void *v18; // rsp
  HANDLE FileW; // r14
  USHORT time; // dx
  USHORT date; // cx
  int *v23; // r14
  char *psz1; // r8
  UINT v25; // r15d
  int v26; // eax
  int v27; // edx
  unsigned __int64 v28; // rcx
  unsigned __int64 v29; // rcx
  void *v30; // rsp
  void *v31; // rsp
  __int64 v32; // rdi
  DWORD TempPathW; // ecx
  __int64 v34; // rax
  signed int v35; // ecx
  unsigned __int64 v36; // r15
  unsigned __int64 v37; // rax
  __int64 v38; // rdx
  unsigned __int64 v39; // rdx
  void *v40; // rsp
  void *v41; // rsp
  int v42; // eax
  unsigned __int64 v43; // rcx
  unsigned __int64 v44; // rcx
  void *v45; // rsp
  void *v46; // rsp
  int err[2]; // [rsp+40h] [rbp+0h] BYREF
  struct _FILETIME FileTime; // [rsp+48h] [rbp+8h] BYREF

  if ( fdint == fdintCABINET_INFO )
    return 0;
  v3 = fdint - 1;
  if ( !v3 )
    return 0;
  v4 = v3 - 1;
  if ( !v4 )
  {
    v23 = 0;
    psz1 = pfdin->psz1;
    v25 = CodePage;
    CodePage = SLOBYTE(pfdin->attribs) < 0 ? 0xFDE9 : 0;
    v26 = MultiByteToWideChar(CodePage, 0, psz1, -1, 0, 0);
    v27 = v26;
    if ( v26 )
    {
      v28 = 2LL * v26 + 15;
      if ( v28 <= 2LL * v26 )
        v28 = 0xFFFFFFFFFFFFFF0LL;
      v29 = v28 & 0xFFFFFFFFFFFFFFF0uLL;
      v30 = alloca(v29);
      v31 = alloca(v29);
      v23 = err;
      v27 = MultiByteToWideChar(CodePage, 0, pfdin->psz1, -1, (LPWSTR)err, v26);
    }
    CodePage = v25;
    if ( !v27 )
      return -1;
    v32 = 0;
    if ( !_wcsicmp((const wchar_t *)v23, &word_180073340) )
    {
      TempPathW = GetTempPathW(0, 0);
      if ( !TempPathW )
        return -1;
      v34 = -1;
      do
        ++v34;
      while ( *((_WORD *)v23 + v34) );
      v35 = v34 + 1 + TempPathW;
      v36 = v35;
      v37 = 2LL * v35;
      v38 = v37 + 15;
      if ( v37 + 15 < v37 )
        v38 = 0xFFFFFFFFFFFFFF0LL;
      v39 = v38 & 0xFFFFFFFFFFFFFFF0uLL;
      v40 = alloca(v39);
      v41 = alloca(v39);
      if ( !GetTempPathW(v35, (LPWSTR)err) )
        return -1;
      if ( (int)StringCchCatW((unsigned __int16 *)err, v36, (const unsigned __int16 *)v23) < 0 )
        return -1;
      v42 = WideCharToMultiByte(CodePage, 0, (LPCWCH)err, -1, 0, 0, 0, 0);
      if ( !v42 )
        return -1;
      v43 = v42 + 15LL;
      if ( v43 < v42 )
        v43 = 0xFFFFFFFFFFFFFF0LL;
      v44 = v43 & 0xFFFFFFFFFFFFFFF0uLL;
      v45 = alloca(v44);
      v46 = alloca(v44);
      if ( !WideCharToMultiByte(CodePage, 0, (LPCWCH)err, -1, (LPSTR)err, v42, 0, 0) )
        return -1;
      return fcicb_Open((LPSTR)err, 33057, 0, err, 0);
    }
    return v32;
  }
  if ( v4 != 1 )
    return 0;
  fcicb_Close(pfdin->hf, err, 0);
  cchWideChar = MultiByteToWideChar(CodePage, 0, pfdin->psz1, -1, 0, 0);
  if ( !cchWideChar )
    return -1;
  v6 = 2LL * cchWideChar + 15;
  if ( v6 <= 2LL * cchWideChar )
    v6 = 0xFFFFFFFFFFFFFF0LL;
  v7 = v6 & 0xFFFFFFFFFFFFFFF0uLL;
  v8 = alloca(v7);
  v9 = alloca(v7);
  if ( !MultiByteToWideChar(CodePage, 0, pfdin->psz1, -1, (LPWSTR)err, cchWideChar) )
    return -1;
  v10 = GetTempPathW(0, 0);
  if ( !v10 )
    return -1;
  v11 = -1;
  do
    ++v11;
  while ( *((_WORD *)err + v11) );
  v12 = v11 + v10 + 1;
  v13 = v12;
  v14 = 2LL * v12;
  v15 = v14 + 15;
  if ( v14 + 15 < v14 )
    v15 = 0xFFFFFFFFFFFFFF0LL;
  v16 = v15 & 0xFFFFFFFFFFFFFFF0uLL;
  v17 = alloca(v16);
  v18 = alloca(v16);
  if ( !GetTempPathW(v12, (LPWSTR)err)
    || (int)StringCchCatW((unsigned __int16 *)err, v13, (const unsigned __int16 *)err) < 0 )
  {
    return -1;
  }
  FileW = CreateFileW((LPCWSTR)err, 0xC0000000, 1u, 0, 3u, 0x80u, 0);
  if ( FileW != (HANDLE)-1LL )
  {
    time = pfdin->time;
    date = pfdin->date;
    FileTime = 0;
    *(_QWORD *)err = 0;
    if ( DosDateTimeToFileTime(date, time, &FileTime) )
      SetFileTime(FileW, (const FILETIME *)err, 0, (const FILETIME *)err);
    CloseHandle(FileW);
  }
  SetFileAttributesW((LPCWSTR)err, pfdin->attribs);
  return 1;
}

```

## disassembly

```asm
0x18002b1f0  push    rbp
0x18002b1f2  push    rbx
0x18002b1f3  push    rsi
0x18002b1f4  push    rdi
0x18002b1f5  push    r12
0x18002b1f7  push    r14
0x18002b1f9  push    r15
0x18002b1fb  sub     rsp, 60h
0x18002b1ff  lea     rbp, [rsp+40h]
0x18002b204  mov     rax, cs:__security_cookie
0x18002b20b  xor     rax, rbp
0x18002b20e  mov     [rbp+50h+var_40], rax
0x18002b212  xor     r12d, r12d
0x18002b215  mov     rdi, rdx
0x18002b218  test    ecx, ecx
0x18002b21a  jz      loc_18002B598
0x18002b220  sub     ecx, 1
0x18002b223  jz      loc_18002B598
0x18002b229  sub     ecx, 1
0x18002b22c  jz      loc_18002B3C8
0x18002b232  cmp     ecx, 1
0x18002b235  jnz     loc_18002B598
0x18002b23b  mov     rcx, [rdi+28h]; hf
0x18002b23f  lea     rdx, [rbp+50h+err]; err
0x18002b243  xor     r8d, r8d; pv
0x18002b246  call    fcicb_Close
0x18002b24b  mov     r8, [rdi+8]; lpMultiByteStr
0x18002b24f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002b253  mov     ecx, cs:CodePage; CodePage
0x18002b259  mov     r9d, ebx; cbMultiByte
0x18002b25c  mov     [rsp+90h+cchWideChar], r12d; cchWideChar
0x18002b261  xor     edx, edx; dwFlags
0x18002b263  mov     [rsp+90h+lpWideCharStr], r12; lpWideCharStr
0x18002b268  call    cs:__imp_MultiByteToWideChar
0x18002b26e  movsxd  rdx, eax
0x18002b271  test    eax, eax
0x18002b273  jz      loc_18002B593
0x18002b279  mov     rax, rdx
0x18002b27c  mov     rsi, 0FFFFFFFFFFFFFF0h
0x18002b286  add     rax, rax
0x18002b289  lea     rcx, [rax+0Fh]
0x18002b28d  cmp     rcx, rax
0x18002b290  ja      short loc_18002B295
0x18002b292  mov     rcx, rsi
0x18002b295  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18002b299  mov     rax, rcx
0x18002b29c  call    _alloca_probe
0x18002b2a1  mov     r8, [rdi+8]; lpMultiByteStr
0x18002b2a5  sub     rsp, rcx
0x18002b2a8  mov     ecx, cs:CodePage; CodePage
0x18002b2ae  mov     r9d, ebx; cbMultiByte
0x18002b2b1  mov     [rsp+90h+cchWideChar], edx; cchWideChar
0x18002b2b5  lea     r15, [rsp+90h+err]
0x18002b2ba  xor     edx, edx; dwFlags
0x18002b2bc  mov     [rsp+90h+lpWideCharStr], r15; lpWideCharStr
0x18002b2c1  call    cs:__imp_MultiByteToWideChar
0x18002b2c7  test    eax, eax
0x18002b2c9  jz      loc_18002B593
0x18002b2cf  xor     edx, edx; lpBuffer
0x18002b2d1  xor     ecx, ecx; nBufferLength
0x18002b2d3  call    cs:__imp_GetTempPathW
0x18002b2d9  mov     ecx, eax
0x18002b2db  test    eax, eax
0x18002b2dd  jz      loc_18002B593
0x18002b2e3  mov     rax, rbx
0x18002b2e6  inc     rax
0x18002b2e9  cmp     [r15+rax*2], r12w
0x18002b2ee  jnz     short loc_18002B2E6
0x18002b2f0  inc     ecx
0x18002b2f2  add     ecx, eax
0x18002b2f4  movsxd  r14, ecx
0x18002b2f7  lea     rax, [r14+r14]
0x18002b2fb  lea     rdx, [rax+0Fh]
0x18002b2ff  cmp     rdx, rax
0x18002b302  ja      short loc_18002B307
0x18002b304  mov     rdx, rsi
0x18002b307  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18002b30b  mov     rax, rdx
0x18002b30e  call    _alloca_probe
0x18002b313  sub     rsp, rdx
0x18002b316  lea     rsi, [rsp+90h+err]
0x18002b31b  mov     rdx, rsi; lpBuffer
0x18002b31e  call    cs:__imp_GetTempPathW
0x18002b324  test    eax, eax
0x18002b326  jz      loc_18002B593
0x18002b32c  mov     r8, r15; unsigned __int16 *
0x18002b32f  mov     rdx, r14; unsigned __int64
0x18002b332  mov     rcx, rsi; unsigned __int16 *
0x18002b335  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002b33a  test    eax, eax
0x18002b33c  js      loc_18002B593
0x18002b342  xor     r9d, r9d; lpSecurityAttributes
0x18002b345  mov     [rsp+90h+hTemplateFile], r12; hTemplateFile
0x18002b34a  mov     [rsp+90h+cchWideChar], 80h; dwFlagsAndAttributes
0x18002b352  mov     edx, 0C0000000h; dwDesiredAccess
0x18002b357  mov     rcx, rsi; lpFileName
0x18002b35a  mov     dword ptr [rsp+90h+lpWideCharStr], 3; dwCreationDisposition
0x18002b362  lea     r15d, [r9+1]
0x18002b366  mov     r8d, r15d; dwShareMode
0x18002b369  call    cs:__imp_CreateFileW
0x18002b36f  mov     r14, rax
0x18002b372  cmp     rax, rbx
0x18002b375  jz      short loc_18002B3B3
0x18002b377  movzx   edx, word ptr [rdi+32h]; wFatTime
0x18002b37b  lea     r8, [rbp+50h+FileTime]; lpFileTime
0x18002b37f  movzx   ecx, word ptr [rdi+30h]; wFatDate
0x18002b383  mov     qword ptr [rbp+50h+FileTime.dwLowDateTime], r12
0x18002b387  mov     qword ptr [rbp+50h+err], r12
0x18002b38b  call    cs:__imp_DosDateTimeToFileTime
0x18002b391  cmp     eax, r15d
0x18002b394  jnz     short loc_18002B3AA
0x18002b396  lea     r9, [rbp+50h+err]; lpLastWriteTime
0x18002b39a  xor     r8d, r8d; lpLastAccessTime
0x18002b39d  lea     rdx, [rbp+50h+err]; lpCreationTime
0x18002b3a1  mov     rcx, r14; hFile
0x18002b3a4  call    cs:__imp_SetFileTime
0x18002b3aa  mov     rcx, r14; hObject
0x18002b3ad  call    cs:__imp_CloseHandle
0x18002b3b3  movzx   edx, word ptr [rdi+34h]; dwFileAttributes
0x18002b3b7  mov     rcx, rsi; lpFileName
0x18002b3ba  call    cs:__imp_SetFileAttributesW
0x18002b3c0  mov     rax, r15
0x18002b3c3  jmp     loc_18002B59A
0x18002b3c8  mov     al, [rdx+34h]
0x18002b3cb  mov     r14, r12
0x18002b3ce  mov     r8, [rdx+8]; lpMultiByteStr
0x18002b3d2  and     al, 80h
0x18002b3d4  mov     r15d, cs:CodePage
0x18002b3db  neg     al
0x18002b3dd  mov     [rsp+90h+cchWideChar], r12d; cchWideChar
0x18002b3e2  sbb     ecx, ecx
0x18002b3e4  mov     [rsp+90h+lpWideCharStr], r12; lpWideCharStr
0x18002b3e9  and     ecx, 0FDE9h; CodePage
0x18002b3ef  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002b3f3  mov     r9d, ebx; cbMultiByte
0x18002b3f6  mov     cs:CodePage, ecx
0x18002b3fc  xor     edx, edx; dwFlags
0x18002b3fe  call    cs:__imp_MultiByteToWideChar
0x18002b404  movsxd  rdx, eax
0x18002b407  mov     rsi, 0FFFFFFFFFFFFFF0h
0x18002b411  test    eax, eax
0x18002b413  jz      short loc_18002B45B
0x18002b415  mov     rax, rdx
0x18002b418  add     rax, rax
0x18002b41b  lea     rcx, [rax+0Fh]
0x18002b41f  cmp     rcx, rax
0x18002b422  ja      short loc_18002B427
0x18002b424  mov     rcx, rsi
0x18002b427  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18002b42b  mov     rax, rcx
0x18002b42e  call    _alloca_probe
0x18002b433  mov     r8, [rdi+8]; lpMultiByteStr
0x18002b437  sub     rsp, rcx
0x18002b43a  mov     ecx, cs:CodePage; CodePage
0x18002b440  mov     r9d, ebx; cbMultiByte
0x18002b443  mov     [rsp+90h+cchWideChar], edx; cchWideChar
0x18002b447  lea     r14, [rsp+90h+err]
0x18002b44c  xor     edx, edx; dwFlags
0x18002b44e  mov     [rsp+90h+lpWideCharStr], r14; lpWideCharStr
0x18002b453  call    cs:__imp_MultiByteToWideChar
0x18002b459  mov     edx, eax
0x18002b45b  mov     cs:CodePage, r15d
0x18002b462  test    edx, edx
0x18002b464  jz      loc_18002B593
0x18002b46a  lea     rdx, word_180073340; String2
0x18002b471  mov     rcx, r14; String1
0x18002b474  mov     rdi, r12
0x18002b477  call    cs:__imp__wcsicmp
0x18002b47d  test    eax, eax
0x18002b47f  jnz     loc_18002B58E
0x18002b485  xor     edx, edx; lpBuffer
0x18002b487  xor     ecx, ecx; nBufferLength
0x18002b489  call    cs:__imp_GetTempPathW
0x18002b48f  mov     ecx, eax
0x18002b491  test    eax, eax
0x18002b493  jz      loc_18002B593
0x18002b499  mov     rax, rbx
0x18002b49c  inc     rax
0x18002b49f  cmp     [r14+rax*2], r12w
0x18002b4a4  jnz     short loc_18002B49C
0x18002b4a6  inc     eax
0x18002b4a8  add     ecx, eax
0x18002b4aa  movsxd  r15, ecx
0x18002b4ad  lea     rax, [r15+r15]
0x18002b4b1  lea     rdx, [rax+0Fh]
0x18002b4b5  cmp     rdx, rax
0x18002b4b8  ja      short loc_18002B4BD
0x18002b4ba  mov     rdx, rsi
0x18002b4bd  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18002b4c1  mov     rax, rdx
0x18002b4c4  call    _alloca_probe
0x18002b4c9  sub     rsp, rdx
0x18002b4cc  lea     rdi, [rsp+90h+err]
0x18002b4d1  mov     rdx, rdi; lpBuffer
0x18002b4d4  call    cs:__imp_GetTempPathW
0x18002b4da  test    eax, eax
0x18002b4dc  jz      loc_18002B593
0x18002b4e2  mov     r8, r14; unsigned __int16 *
0x18002b4e5  mov     rdx, r15; unsigned __int64
0x18002b4e8  mov     rcx, rdi; unsigned __int16 *
0x18002b4eb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002b4f0  test    eax, eax
0x18002b4f2  js      loc_18002B593
0x18002b4f8  mov     ecx, cs:CodePage; CodePage
0x18002b4fe  mov     r9d, ebx; cchWideChar
0x18002b501  mov     [rsp+90h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x18002b506  mov     r8, rdi; lpWideCharStr
0x18002b509  mov     [rsp+90h+hTemplateFile], r12; lpDefaultChar
0x18002b50e  xor     edx, edx; dwFlags
0x18002b510  mov     [rsp+90h+cchWideChar], r12d; cbMultiByte
0x18002b515  mov     [rsp+90h+lpWideCharStr], r12; lpMultiByteStr
0x18002b51a  call    cs:__imp_WideCharToMultiByte
0x18002b520  movsxd  rdx, eax
0x18002b523  test    eax, eax
0x18002b525  jz      short loc_18002B593
0x18002b527  lea     rcx, [rdx+0Fh]
0x18002b52b  cmp     rcx, rdx
0x18002b52e  ja      short loc_18002B533
0x18002b530  mov     rcx, rsi
0x18002b533  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18002b537  mov     rax, rcx
0x18002b53a  call    _alloca_probe
0x18002b53f  sub     rsp, rcx
0x18002b542  mov     r9d, ebx; cchWideChar
0x18002b545  mov     ecx, cs:CodePage; CodePage
0x18002b54b  mov     r8, rdi; lpWideCharStr
0x18002b54e  mov     [rsp+90h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x18002b553  lea     rsi, [rsp+90h+err]
0x18002b558  mov     [rsp+90h+hTemplateFile], r12; lpDefaultChar
0x18002b55d  mov     [rsp+90h+cchWideChar], edx; cbMultiByte
0x18002b561  xor     edx, edx; dwFlags
0x18002b563  mov     [rsp+90h+lpWideCharStr], rsi; lpMultiByteStr
0x18002b568  call    cs:__imp_WideCharToMultiByte
0x18002b56e  test    eax, eax
0x18002b570  jz      short loc_18002B593
0x18002b572  lea     r9, [rbp+50h+err]; err
0x18002b576  mov     [rsp+90h+lpWideCharStr], r12; pv
0x18002b57b  xor     r8d, r8d; pmode
0x18002b57e  mov     edx, 8121h; oflag
0x18002b583  mov     rcx, rsi; pszFile
0x18002b586  call    fcicb_Open
0x18002b58b  mov     rdi, rax
0x18002b58e  mov     rax, rdi
0x18002b591  jmp     short loc_18002B59A
0x18002b593  mov     rax, rbx
0x18002b596  jmp     short loc_18002B59A
0x18002b598  xor     eax, eax
0x18002b59a  mov     rcx, [rbp+50h+var_40]
0x18002b59e  xor     rcx, rbp; StackCookie
0x18002b5a1  call    __security_check_cookie
0x18002b5a6  lea     rsp, [rbp+20h]
0x18002b5aa  pop     r15
0x18002b5ac  pop     r14
0x18002b5ae  pop     r12
0x18002b5b0  pop     rdi
0x18002b5b1  pop     rsi
0x18002b5b2  pop     rbx
0x18002b5b3  pop     rbp
0x18002b5b4  retn
```
