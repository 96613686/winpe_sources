# UpdatePreFetchJobCacheFile(_CUCS_PRE_FETCH_JOB_ENTRY *)

- ea: `0x180004c90`
- end: `0x180005457`
- name: `?UpdatePreFetchJobCacheFile@@YAHPEAU_CUCS_PRE_FETCH_JOB_ENTRY@@@Z`
- size: `1991`
- prototype: `__int64 __fastcall(struct _CUCS_PRE_FETCH_JOB_ENTRY *, __int64)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180003a44`
- `0x180003c90`

## callees

- `0x180003f00`
- `0x180004180`
- `0x1800042e0`
- `0x180004c90`
- `0x1800068b0`
- `0x1800070d0`
- `0x180007980`
- `0x180007af0`
- `0x180009030`
- `0x18000b4a4`
- `0x18000e2f0`
- `0x1800174fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004fc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000535f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004fc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000535f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004fd8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005367`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800053e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005432`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004fd8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005367`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800053e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005432`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800050b3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800050b3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800050d8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800050d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000509d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000509d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004fd0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004fd0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004dc3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004f93`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004dc3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004f93`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180004ecf`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180004ecf`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180004ea7`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800051b7`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180004ea7`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800051b7`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180004ee0`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180004ee0`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180004e1a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180004e1a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800053c9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180005416`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800053c9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180005416`

## pseudocode

```c
__int64 __fastcall UpdatePreFetchJobCacheFile(struct _CUCS_PRE_FETCH_JOB_ENTRY *a1, __int64 a2)
{
  void **v2; // rax
  DWORD v3; // r13d
  __int64 FileW; // r15
  DWORD v6; // r12d
  FILETIME *v7; // rbp
  HANDLE CacheFile; // rdi
  __int64 v9; // rbx
  __int16 v10; // cx
  __int64 v11; // rax
  unsigned int j; // ebx
  const FILETIME *v13; // rax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  __int128 v17; // xmm6
  __int128 v18; // xmm7
  __int128 v19; // xmm8
  __int128 v20; // xmm9
  __int16 v21; // cx
  __int64 v22; // rax
  unsigned int i; // ebx
  DWORD v24; // ebx
  void *v26; // rbx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  __int64 v29; // rax
  void *v30; // rdi
  __int64 v31; // rcx
  _WORD *v32; // rsi
  __int64 v33; // rbx
  __int64 v34; // r13
  char *v35; // r12
  size_t v36; // rdi
  __int64 v37; // r13
  char *v38; // r12
  DWORD v39; // eax
  DWORD v40; // eax
  DWORD dwFlagsAndAttributes; // [rsp+28h] [rbp-110h]
  DWORD NumberOfBytesWritten[2]; // [rsp+40h] [rbp-F8h] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+48h] [rbp-F0h]
  int v44; // [rsp+4Ch] [rbp-ECh]
  void *TokenHandle; // [rsp+50h] [rbp-E8h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp-E0h]
  void *Src; // [rsp+60h] [rbp-D8h]
  __int64 v48; // [rsp+68h] [rbp-D0h]
  _OWORD v49[4]; // [rsp+70h] [rbp-C8h] BYREF
  __int16 v50; // [rsp+B0h] [rbp-88h]

  v2 = (void **)*((_QWORD *)a1 + 16);
  v3 = 1;
  FileW = 0;
  v44 = 0;
  v6 = 0;
  nNumberOfBytesToWrite = 0;
  v7 = 0;
  if ( v2 )
  {
    v26 = *v2;
    TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle)
      || (LastError = GetLastError(), TokenHandle = 0, LastError == 1008) )
    {
      if ( SetThreadToken(0, v26) )
      {
        hObject = TokenHandle;
        v44 = 1;
        goto LABEL_3;
      }
      LastError = GetLastError();
    }
    SetLastError(LastError);
    hObject = TokenHandle;
    if ( TokenHandle )
    {
      I_UrlCacheCloseHandle(TokenHandle);
      hObject = 0;
      TokenHandle = 0;
    }
  }
  else
  {
    hObject = 0;
  }
LABEL_3:
  if ( *((_DWORD *)a1 + 30) || !*((_QWORD *)a1 + 27) )
  {
    CacheFile = I_UrlCacheCreateCacheFile(
                  *(_WORD **)(*((_QWORD *)a1 + 6) + 32LL),
                  a2,
                  *((_WORD **)a1 + 10),
                  *((_QWORD *)a1 + 9),
                  1);
    if ( !CacheFile )
      goto LABEL_30;
  }
  else
  {
    v29 = *((_QWORD *)a1 + 6);
    v30 = (void *)*((_QWORD *)a1 + 10);
    v31 = *((_QWORD *)a1 + 9);
    Src = v30;
    v32 = *(_WORD **)(v29 + 32);
    I_UrlCacheGetUrlFileName(v31, v49);
    if ( v32 )
    {
      v33 = -1;
      do
        ++v33;
      while ( v32[v33] );
    }
    else
    {
      LODWORD(v33) = 0;
    }
    if ( v30 )
    {
      v34 = -1;
      do
        ++v34;
      while ( *((_WORD *)v30 + v34) );
    }
    else
    {
      LODWORD(v34) = 0;
    }
    v35 = (char *)PkiNonzeroAlloc(2LL * (unsigned int)(v33 + v34 + 42));
    if ( !v35 )
    {
      PkiFree(0);
      CacheFile = 0;
      goto LABEL_30;
    }
    *(_QWORD *)NumberOfBytesWritten = (unsigned int)v33;
    v36 = 2LL * (unsigned int)v33;
    memcpy_0(v35, v32, v36);
    *(_OWORD *)&v35[v36] = *(_OWORD *)L"MetaData";
    *(_WORD *)&v35[v36 + 16] = aMetadata[8];
    if ( !(unsigned int)I_CryptRecursiveCreateLowIntegrityDirectory((LPCWSTR)v35) )
    {
      PkiFree(v35);
      PkiFree(0);
      CacheFile = 0;
      goto LABEL_30;
    }
    *(_WORD *)&v35[2 * (unsigned int)(v33 + 8)] = 92;
    if ( (_DWORD)v34 )
      memcpy_0(&v35[2 * *(_QWORD *)NumberOfBytesWritten + 18], Src, 2LL * (unsigned int)v34);
    v17 = v49[0];
    v18 = v49[1];
    v19 = v49[2];
    v20 = v49[3];
    v21 = v50;
    v22 = *(_QWORD *)NumberOfBytesWritten + (unsigned int)v34;
    *(_OWORD *)&v35[2 * v22 + 18] = v49[0];
    *(_OWORD *)&v35[2 * v22 + 34] = v18;
    *(_OWORD *)&v35[2 * v22 + 50] = v19;
    *(_OWORD *)&v35[2 * v22 + 66] = v20;
    *(_WORD *)&v35[2 * v22 + 82] = v21;
    NumberOfBytesWritten[0] = 1;
    for ( i = 0; ; ++i )
    {
      CacheFile = CreateFileW((LPCWSTR)v35, 0xC0000000, 0, 0, 4u, 4u, 0);
      if ( CacheFile != (HANDLE)-1LL )
        break;
      v39 = GetLastError();
      if ( v39 == 32 )
      {
        if ( i >= 6 )
          goto LABEL_88;
      }
      else
      {
        if ( v39 != 5 )
        {
          if ( v39 == 3 )
            v39 = 2;
LABEL_88:
          SetLastError(v39);
          CacheFile = 0;
          break;
        }
        if ( i )
          goto LABEL_88;
      }
      Sleep(*((_DWORD *)qword_18001B4D0 + i));
    }
    PkiFree(v35);
    if ( !CacheFile )
    {
LABEL_30:
      v3 = 0;
      if ( !v7 )
        goto LABEL_32;
      goto LABEL_31;
    }
    v37 = -1;
    if ( v32 )
    {
      FileW = -1;
      do
        ++FileW;
      while ( v32[FileW] );
    }
    if ( Src )
    {
      do
        ++v37;
      while ( *((_WORD *)Src + v37) );
    }
    else
    {
      LODWORD(v37) = 0;
    }
    v38 = (char *)PkiNonzeroAlloc(2LL * (unsigned int)(FileW + v37 + 41));
    if ( !v38 )
      goto LABEL_70;
    v48 = (unsigned int)FileW;
    memcpy_0(v38, v32, 2LL * (unsigned int)FileW);
    *(_OWORD *)&v38[2 * (unsigned int)FileW] = *(_OWORD *)L"Content";
    if ( !(unsigned int)I_CryptRecursiveCreateLowIntegrityDirectory((LPCWSTR)v38) )
    {
      PkiFree(v38);
      v38 = 0;
LABEL_70:
      PkiFree(v38);
      FileW = 0;
LABEL_71:
      I_UrlCacheCloseHandle(CacheFile);
      CacheFile = 0;
      goto LABEL_30;
    }
    v9 = v48;
    *(_WORD *)&v38[2 * (unsigned int)(FileW + 7)] = 92;
    if ( (_DWORD)v37 )
      memcpy_0(&v38[2 * v9 + 16], Src, 2LL * (unsigned int)v37);
    v10 = v50;
    v11 = v9 + (unsigned int)v37;
    *(_OWORD *)&v38[2 * v11 + 16] = v17;
    *(_OWORD *)&v38[2 * v11 + 32] = v18;
    *(_OWORD *)&v38[2 * v11 + 48] = v19;
    *(_OWORD *)&v38[2 * v11 + 64] = v20;
    *(_WORD *)&v38[2 * v11 + 80] = v10;
    for ( j = 0; ; ++j )
    {
      FileW = (__int64)CreateFileW((LPCWSTR)v38, 0xC0000000, 0, 0, 4u, 4u, 0);
      if ( FileW != -1 )
        break;
      v40 = GetLastError();
      if ( v40 == 32 )
      {
        if ( j >= 6 )
          goto LABEL_97;
      }
      else
      {
        if ( v40 != 5 )
        {
          if ( v40 == 3 )
            v40 = 2;
LABEL_97:
          SetLastError(v40);
          FileW = 0;
          break;
        }
        if ( j )
          goto LABEL_97;
      }
      Sleep(*((_DWORD *)qword_18001B4D0 + j));
    }
    PkiFree(v38);
    if ( !FileW )
      goto LABEL_71;
    v6 = NumberOfBytesWritten[0];
    v3 = NumberOfBytesWritten[0];
  }
  v13 = (const FILETIME *)I_UrlCacheReadAndValidateMetaDataFile(CacheFile, 0);
  v7 = (FILETIME *)v13;
  if ( !v13 )
    goto LABEL_30;
  if ( !CompareFileTime(v13 + 2, (const FILETIME *)((char *)a1 + 60)) )
  {
    if ( v6 )
    {
      v7[9] = *(FILETIME *)((char *)a1 + 240);
      if ( SetFilePointer(CacheFile, 0, 0, 0) == -1
        || !(unsigned int)I_UrlCacheWriteCryptBlobArray2(
                            *((LPCVOID *)a1 + 9),
                            CacheFile,
                            (HANDLE)FileW,
                            (__int64)&v7[8],
                            dwFlagsAndAttributes,
                            *((_QWORD *)a1 + 28)) )
      {
        goto LABEL_30;
      }
    }
    else
    {
      v7[4].dwLowDateTime = *((_DWORD *)a1 + 30);
      v14 = *((_DWORD *)a1 + 30);
      if ( !v14 || v14 == 50 || v14 == 4350 )
        v7[2] = *(FILETIME *)((char *)a1 + 232);
      v15 = *((_DWORD *)a1 + 30);
      if ( v15 && v15 != 4350 )
      {
        LOWORD(v7[10].dwHighDateTime) = 0;
        HIWORD(v7[10].dwHighDateTime) &= ~0x8000u;
      }
      v16 = *((_DWORD *)a1 + 35);
      if ( (v16 == 7 || (unsigned int)(v16 - 5) <= 1) && !*((_DWORD *)a1 + 30) && !*((_DWORD *)a1 + 44) )
      {
        *(_OWORD *)&v7[3].dwLowDateTime = 0;
        *(_OWORD *)&v7[5].dwLowDateTime = 0;
        v7[7] = 0;
        v7[3].dwLowDateTime = 40;
      }
      NumberOfBytesWritten[0] = 0;
      if ( SetFilePointer(CacheFile, 0, 0, 0) == -1
        || !WriteFile(CacheFile, v7, nNumberOfBytesToWrite, NumberOfBytesWritten, 0) )
      {
        goto LABEL_30;
      }
      SetEndOfFile(CacheFile);
      *(FILETIME *)((char *)a1 + 60) = v7[2];
    }
  }
LABEL_31:
  v24 = GetLastError();
  LocalFree(v7);
  SetLastError(v24);
LABEL_32:
  if ( FileW )
    I_UrlCacheCloseHandle((HANDLE)FileW);
  if ( CacheFile )
    I_UrlCacheCloseHandle(CacheFile);
  if ( v44 )
    RestoreToken(hObject);
  return v3;
}

```

## disassembly

```asm
0x180004c90  mov     r11, rsp
0x180004c93  push    r13
0x180004c95  sub     rsp, 130h
0x180004c9c  mov     rax, cs:__security_cookie
0x180004ca3  xor     rax, rsp
0x180004ca6  mov     [rsp+138h+var_78], rax
0x180004cae  mov     rax, [rcx+80h]
0x180004cb5  mov     r13d, 1
0x180004cbb  mov     [r11+10h], rbx
0x180004cbf  mov     [r11+18h], rbp
0x180004cc3  mov     [r11-10h], rdi
0x180004cc7  mov     [r11-18h], r12
0x180004ccb  mov     [r11-20h], r14
0x180004ccf  mov     r14, rcx
0x180004cd2  mov     [r11-28h], r15
0x180004cd6  xor     r15d, r15d
0x180004cd9  mov     [rsp+138h+var_EC], r15d
0x180004cde  mov     r12d, r15d
0x180004ce1  mov     [rsp+138h+nNumberOfBytesToWrite], r15d
0x180004ce6  mov     ebp, r15d
0x180004ce9  test    rax, rax
0x180004cec  jnz     loc_180005095
0x180004cf2  mov     [rsp+138h+hObject], r15
0x180004cf7  mov     [rsp+138h+arg_18], rsi
0x180004cff  movaps  [rsp+138h+var_38], xmm6
0x180004d07  movaps  [rsp+138h+var_48], xmm7
0x180004d0f  movaps  [rsp+138h+var_58], xmm8
0x180004d18  movaps  [rsp+138h+var_68], xmm9
0x180004d21  cmp     [r14+78h], ebp
0x180004d25  jz      loc_1800050FA
0x180004d2b  mov     rcx, [r14+30h]
0x180004d2f  mov     r9, [r14+48h]
0x180004d33  mov     r8, [r14+50h]
0x180004d37  mov     [rsp+138h+dwCreationDisposition], r13d; int
0x180004d3c  mov     rcx, [rcx+20h]; Src
0x180004d40  call    I_UrlCacheCreateCacheFile
0x180004d45  mov     rdi, rax
0x180004d48  test    rax, rax
0x180004d4b  jz      loc_180004FBD
0x180004d51  jmp     loc_180004DEF
0x180004d56  mov     rbx, [rsp+138h+var_D0]
0x180004d5b  lea     eax, [r15+7]
0x180004d5f  mov     word ptr [r12+rax*2], 5Ch ; '\'
0x180004d66  test    r13d, r13d
0x180004d69  jnz     loc_180005280
0x180004d6f  movzx   ecx, [rsp+138h+var_88]
0x180004d77  mov     eax, r13d
0x180004d7a  add     rax, rbx
0x180004d7d  movups  xmmword ptr [r12+rax*2+10h], xmm6
0x180004d83  movups  xmmword ptr [r12+rax*2+20h], xmm7
0x180004d89  movups  xmmword ptr [r12+rax*2+30h], xmm8
0x180004d8f  movups  xmmword ptr [r12+rax*2+40h], xmm9
0x180004d95  mov     [r12+rax*2+50h], cx
0x180004d9b  xor     eax, eax
0x180004d9d  mov     ebx, eax
0x180004d9f  nop
0x180004da0  mov     [rsp+138h+hTemplateFile], rax; hTemplateFile
0x180004da5  xor     r9d, r9d; lpSecurityAttributes
0x180004da8  mov     [rsp+138h+dwFlagsAndAttributes], 4; int
0x180004db0  xor     r8d, r8d; dwShareMode
0x180004db3  mov     edx, 0C0000000h; dwDesiredAccess
0x180004db8  mov     [rsp+138h+dwCreationDisposition], 4; dwCreationDisposition
0x180004dc0  mov     rcx, r12; lpFileName
0x180004dc3  call    cs:__imp_CreateFileW
0x180004dc9  mov     r15, rax
0x180004dcc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180004dd0  jz      loc_1800053EE
0x180004dd6  mov     rcx, r12; hMem
0x180004dd9  call    PkiFree
0x180004dde  test    r15, r15
0x180004de1  jz      loc_1800052F9
0x180004de7  mov     r12d, [rsp+138h+NumberOfBytesWritten]
0x180004dec  mov     r13d, r12d
0x180004def  lea     r9, [rsp+138h+nNumberOfBytesToWrite]
0x180004df4  mov     qword ptr [rsp+138h+dwCreationDisposition], rbp; __int64
0x180004df9  xor     r8d, r8d
0x180004dfc  xor     edx, edx
0x180004dfe  mov     rcx, rdi; hFile
0x180004e01  call    I_UrlCacheReadAndValidateMetaDataFile
0x180004e06  mov     rbp, rax
0x180004e09  test    rax, rax
0x180004e0c  jz      loc_180004FBD
0x180004e12  lea     rdx, [r14+3Ch]; lpFileTime2
0x180004e16  lea     rcx, [rax+10h]; lpFileTime1
0x180004e1a  call    cs:__imp_CompareFileTime
0x180004e20  test    eax, eax
0x180004e22  jnz     loc_180004FC5
0x180004e28  test    r12d, r12d
0x180004e2b  jnz     loc_18000519D
0x180004e31  mov     eax, [r14+78h]
0x180004e35  mov     [rbp+20h], eax
0x180004e38  mov     eax, [r14+78h]
0x180004e3c  test    eax, eax
0x180004e3e  jnz     loc_18000507C
0x180004e44  mov     rax, [r14+0E8h]
0x180004e4b  mov     [rbp+10h], rax
0x180004e4f  mov     eax, [r14+78h]
0x180004e53  test    eax, eax
0x180004e55  jnz     loc_18000517E
0x180004e5b  mov     eax, [r14+8Ch]
0x180004e62  cmp     eax, 7
0x180004e65  jnz     loc_180005440
0x180004e6b  cmp     dword ptr [r14+78h], 0
0x180004e70  jnz     short loc_180004E94
0x180004e72  cmp     dword ptr [r14+0B0h], 0
0x180004e7a  jnz     short loc_180004E94
0x180004e7c  xorps   xmm0, xmm0
0x180004e7f  xor     eax, eax
0x180004e81  movups  xmmword ptr [rbp+18h], xmm0
0x180004e85  movups  xmmword ptr [rbp+28h], xmm0
0x180004e89  mov     [rbp+38h], rax
0x180004e8d  mov     dword ptr [rbp+18h], 28h ; '('
0x180004e94  xor     r9d, r9d; dwMoveMethod
0x180004e97  mov     [rsp+138h+NumberOfBytesWritten], 0
0x180004e9f  xor     r8d, r8d; lpDistanceToMoveHigh
0x180004ea2  xor     edx, edx; lDistanceToMove
0x180004ea4  mov     rcx, rdi; hFile
0x180004ea7  call    cs:__imp_SetFilePointer
0x180004ead  cmp     eax, 0FFFFFFFFh
0x180004eb0  jz      loc_180004FBD
0x180004eb6  mov     r8d, [rsp+138h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x180004ebb  lea     r9, [rsp+138h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180004ec0  mov     rdx, rbp; lpBuffer
0x180004ec3  mov     qword ptr [rsp+138h+dwCreationDisposition], 0; lpOverlapped
0x180004ecc  mov     rcx, rdi; hFile
0x180004ecf  call    cs:__imp_WriteFile
0x180004ed5  test    eax, eax
0x180004ed7  jz      loc_180004FBD
0x180004edd  mov     rcx, rdi; hFile
0x180004ee0  call    cs:__imp_SetEndOfFile
0x180004ee6  mov     rax, [rbp+10h]
0x180004eea  mov     [r14+3Ch], rax
0x180004eee  jmp     loc_180004FC5
0x180004ef3  add     ebx, 8
0x180004ef6  mov     word ptr [r12+rbx*2], 5Ch ; '\'
0x180004efd  mov     rbx, qword ptr [rsp+138h+NumberOfBytesWritten]
0x180004f02  test    r13d, r13d
0x180004f05  jnz     loc_180005263
0x180004f0b  movaps  xmm6, [rsp+138h+var_C8]
0x180004f10  movaps  xmm7, [rsp+138h+var_B8]
0x180004f18  movaps  xmm8, [rsp+138h+var_A8]
0x180004f21  movaps  xmm9, [rsp+138h+var_98]
0x180004f2a  movzx   ecx, [rsp+138h+var_88]
0x180004f32  mov     eax, r13d
0x180004f35  add     rax, rbx
0x180004f38  movups  xmmword ptr [r12+rax*2+12h], xmm6
0x180004f3e  movups  xmmword ptr [r12+rax*2+22h], xmm7
0x180004f44  movups  xmmword ptr [r12+rax*2+32h], xmm8
0x180004f4a  movups  xmmword ptr [r12+rax*2+42h], xmm9
0x180004f50  mov     [r12+rax*2+52h], cx
0x180004f56  xor     eax, eax
0x180004f58  mov     [rsp+138h+NumberOfBytesWritten], 1
0x180004f60  mov     ebx, eax
0x180004f62  nop     dword ptr [rax+00h]
0x180004f66  nop     word ptr [rax+rax+00000000h]
0x180004f70  mov     [rsp+138h+hTemplateFile], rax; hTemplateFile
0x180004f75  xor     r9d, r9d; lpSecurityAttributes
0x180004f78  mov     [rsp+138h+dwFlagsAndAttributes], 4; dwFlagsAndAttributes
0x180004f80  xor     r8d, r8d; dwShareMode
0x180004f83  mov     edx, 0C0000000h; dwDesiredAccess
0x180004f88  mov     [rsp+138h+dwCreationDisposition], 4; dwCreationDisposition
0x180004f90  mov     rcx, r12; lpFileName
0x180004f93  call    cs:__imp_CreateFileW
0x180004f99  mov     rdi, rax
0x180004f9c  mov     r13d, 2
0x180004fa2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180004fa6  jz      loc_1800053A1
0x180004fac  mov     rcx, r12; hMem
0x180004faf  call    PkiFree
0x180004fb4  test    rdi, rdi
0x180004fb7  jnz     loc_1800052AF
0x180004fbd  xor     r13d, r13d
0x180004fc0  test    rbp, rbp
0x180004fc3  jz      short loc_180004FDE
0x180004fc5  call    cs:__imp_GetLastError
0x180004fcb  mov     rcx, rbp; hMem
0x180004fce  mov     ebx, eax
0x180004fd0  call    cs:__imp_LocalFree
0x180004fd6  mov     ecx, ebx; dwErrCode
0x180004fd8  call    cs:__imp_SetLastError
0x180004fde  movaps  xmm9, [rsp+138h+var_68]
0x180004fe7  movaps  xmm8, [rsp+138h+var_58]
0x180004ff0  movaps  xmm7, [rsp+138h+var_48]
0x180004ff8  movaps  xmm6, [rsp+138h+var_38]
0x180005000  mov     r14, [rsp+138h+var_20]
0x180005008  mov     r12, [rsp+138h+var_18]
0x180005010  mov     rsi, [rsp+138h+arg_18]
0x180005018  mov     rbp, [rsp+138h+arg_10]
0x180005020  mov     rbx, [rsp+138h+arg_8]
0x180005028  test    r15, r15
0x18000502b  jnz     loc_180005256
0x180005031  mov     r15, [rsp+138h+var_28]
0x180005039  test    rdi, rdi
0x18000503c  jz      short loc_180005046
0x18000503e  mov     rcx, rdi; hObject
0x180005041  call    I_UrlCacheCloseHandle
0x180005046  cmp     [rsp+138h+var_EC], 0
0x18000504b  mov     rdi, [rsp+138h+var_10]
0x180005053  jz      short loc_18000505F
0x180005055  mov     rcx, [rsp+138h+hObject]; hObject
0x18000505a  call    ?RestoreToken@@YAXPEAX@Z; RestoreToken(void *)
0x18000505f  mov     eax, r13d
0x180005062  mov     rcx, [rsp+138h+var_78]
0x18000506a  xor     rcx, rsp; StackCookie
0x18000506d  call    __security_check_cookie
0x180005072  add     rsp, 130h
0x180005079  pop     r13
0x18000507b  retn
0x18000507c  cmp     eax, 32h ; '2'
0x18000507f  jz      loc_180004E44
0x180005085  cmp     eax, 10FEh
0x18000508a  jnz     loc_180004E4F
0x180005090  jmp     loc_180004E44
0x180005095  mov     rbx, [rax]
0x180005098  mov     [rsp+138h+TokenHandle], r15
0x18000509d  call    cs:__imp_GetCurrentThread
0x1800050a3  lea     r9, [rsp+138h+TokenHandle]; TokenHandle
0x1800050a8  mov     r8d, r13d; OpenAsSelf
0x1800050ab  mov     rcx, rax; ThreadHandle
0x1800050ae  mov     edx, 0Ch; DesiredAccess
0x1800050b3  call    cs:__imp_OpenThreadToken
0x1800050b9  test    eax, eax
0x1800050bb  jnz     short loc_1800050D3
0x1800050bd  call    cs:__imp_GetLastError
0x1800050c3  mov     [rsp+138h+TokenHandle], r15
0x1800050c8  cmp     eax, 3F0h
0x1800050cd  jnz     loc_180005365
0x1800050d3  mov     rdx, rbx; Token
0x1800050d6  xor     ecx, ecx; Thread
0x1800050d8  call    cs:__imp_SetThreadToken
0x1800050de  test    eax, eax
0x1800050e0  jz      loc_18000535F
0x1800050e6  mov     rax, [rsp+138h+TokenHandle]
0x1800050eb  mov     [rsp+138h+hObject], rax
0x1800050f0  mov     [rsp+138h+var_EC], r13d
0x1800050f5  jmp     loc_180004CF7
0x1800050fa  cmp     [r14+0D8h], rbp
0x180005101  jz      loc_180004D2B
0x180005107  mov     rax, [r14+30h]
0x18000510b  lea     rdx, [rsp+138h+var_C8]
0x180005110  mov     rdi, [r14+50h]
0x180005114  mov     rcx, [r14+48h]
0x180005118  mov     [rsp+138h+Src], rdi
0x18000511d  mov     rsi, [rax+20h]
0x180005121  call    I_UrlCacheGetUrlFileName
0x180005126  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000512d  test    rsi, rsi
0x180005130  jz      loc_18000539A
0x180005136  mov     rbx, rax
0x180005139  nop     dword ptr [rax+00000000h]
0x180005140  inc     rbx
0x180005143  cmp     [rsi+rbx*2], bp
0x180005147  jnz     short loc_180005140
0x180005149  test    rdi, rdi
0x18000514c  jnz     loc_18000529D
0x180005152  xor     r13d, r13d
0x180005155  lea     ecx, [r13+2Ah]
0x180005159  add     ecx, ebx
0x18000515b  add     rcx, rcx; uBytes
0x18000515e  call    PkiNonzeroAlloc
0x180005163  mov     r12, rax
0x180005166  test    rax, rax
0x180005169  jnz     loc_1800051FA
0x18000516f  mov     rcx, rax; hMem
0x180005172  call    PkiFree
0x180005177  xor     edi, edi
0x180005179  jmp     loc_180004FBD
0x18000517e  cmp     eax, 10FEh
0x180005183  jz      loc_180004E5B
0x180005189  xor     eax, eax
0x18000518b  mov     [rbp+54h], ax
0x18000518f  mov     eax, 7FFFh
0x180005194  and     [rbp+56h], ax
0x180005198  jmp     loc_180004E5B
0x18000519d  mov     rax, [r14+0F0h]
0x1800051a4  lea     rbx, [rbp+40h]
0x1800051a8  xor     r9d, r9d; dwMoveMethod
0x1800051ab  mov     [rbx+8], rax
0x1800051af  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800051b2  xor     edx, edx; lDistanceToMove
0x1800051b4  mov     rcx, rdi; hFile
0x1800051b7  call    cs:__imp_SetFilePointer
0x1800051bd  cmp     eax, 0FFFFFFFFh
0x1800051c0  jz      loc_180004FBD
0x1800051c6  mov     rax, [r14+0E0h]
0x1800051cd  mov     r8, r15; HANDLE
0x1800051d0  mov     r9, [r14+0D8h]
0x1800051d7  mov     rdx, rdi; hFile
0x1800051da  mov     rcx, [r14+48h]; lpBuffer
0x1800051de  mov     [rsp+138h+hTemplateFile], rax; __int64
0x1800051e3  mov     qword ptr [rsp+138h+dwCreationDisposition], rbx; __int64
0x1800051e8  call    I_UrlCacheWriteCryptBlobArray2
0x1800051ed  test    eax, eax
0x1800051ef  jnz     loc_180004FC5
0x1800051f5  jmp     loc_180004FBD
0x1800051fa  mov     eax, ebx
0x1800051fc  mov     rdx, rsi; Src
0x1800051ff  mov     rcx, r12; void *
0x180005202  mov     qword ptr [rsp+138h+NumberOfBytesWritten], rax
0x180005207  lea     rdi, [rax+rax]
  ... truncated ...
```
