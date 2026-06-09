# OpenFilenameStoreProvW(char const *,ulong,unsigned __int64,ulong,void const *,void *,_CERT_STORE_PROV_INFO *)

- ea: `0x18006c670`
- end: `0x18006cb53`
- name: `?OpenFilenameStoreProvW@@YAHPEBDK_KKPEBXPEAXPEAU_CERT_STORE_PROV_INFO@@@Z`
- size: `1251`
- prototype: `__int64 __fastcall(const char *, unsigned int, unsigned __int64, unsigned int, LPCWSTR lpFileName, HCERTSTORE hCertStore, struct _CERT_STORE_PROV_INFO *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18006cb60`

## callees

- `0x180028d60`
- `0x18002cb30`
- `0x18002d430`
- `0x180030e60`
- `0x1800342b0`
- `0x180047f10`
- `0x18006c670`
- `0x180072aa0`
- `0x1800a0230`
- `0x1800bec20`
- `0x1800c4cd0`
- `0x1800c4dc0`
- `0x1800c4f40`
- `0x1800c83b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c929`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cb07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c929`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cb07`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006caf7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006cb1a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006caf7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006cb1a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18006c879`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18006c879`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18006c96d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18006c96d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006c774`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006c8b7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006c774`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006c8b7`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18006c906`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18006c906`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18006c78f`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18006c91b`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18006c78f`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18006c91b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006c7f3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006c820`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006c7f3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006c820`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006cb12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006cb12`

## pseudocode

```c
__int64 __fastcall OpenFilenameStoreProvW(
        const char *a1,
        int a2,
        unsigned __int64 a3,
        int a4,
        LPCWSTR lpFileName,
        HCERTSTORE hCertStore,
        struct _CERT_STORE_PROV_INFO *a7)
{
  unsigned int v7; // r14d
  __int64 FileW; // r15
  int v10; // ebx
  unsigned int v11; // edi
  int v12; // ecx
  int v13; // edx
  DWORD dwCreationDisposition; // ecx
  HANDLE v15; // rax
  unsigned int v16; // r12d
  __int64 v17; // rax
  const WCHAR *v18; // rcx
  const WCHAR *v19; // rbx
  struct _CERT_STORE_PROV_INFO *v20; // rbx
  DWORD FileSize; // eax
  void *v22; // rax
  struct _CERT_STORE_PROV_INFO *v23; // r12
  __int64 v24; // rax
  DWORD v25; // ecx
  int updated; // ebx
  DWORD LastError; // ebx
  int v29; // [rsp+68h] [rbp-79h]
  DWORD dwCertEncodingType; // [rsp+6Ch] [rbp-75h]
  DWORD nNumberOfBytesToRead[4]; // [rsp+70h] [rbp-71h] BYREF
  DWORD NumberOfBytesRead; // [rsp+80h] [rbp-61h] BYREF
  HCERTSTORE phCertStore; // [rsp+88h] [rbp-59h] BYREF
  unsigned __int64 v34; // [rsp+90h] [rbp-51h]
  const char *pvData[2]; // [rsp+98h] [rbp-49h] BYREF
  _OWORD FileInformation[2]; // [rsp+A8h] [rbp-39h] BYREF
  int v37; // [rsp+C8h] [rbp-19h]

  v7 = a4 & 0xFFFFFFDF;
  FileW = -1;
  v34 = a3;
  pvData[0] = a1;
  NumberOfBytesRead = 0;
  phCertStore = 0;
  *(_OWORD *)nNumberOfBytesToRead = 0;
  if ( (a4 & 0xFFFE001C) != 0 )
    goto LABEL_60;
  v10 = a4 & 0x800;
  if ( (a4 & 0x800) != 0 )
    ILS_EnableBackupRestorePrivileges();
  v11 = 1;
  v12 = a2 | 1;
  if ( (_WORD)a2 )
    v12 = a2;
  v13 = v12 | 0x10000;
  if ( (v12 & 0xFFFF0000) != 0 )
    v13 = v12;
  v29 = v7 & 0x10000;
  dwCertEncodingType = v13;
  if ( (v7 & 0x10000) == 0 )
  {
    v37 = 0;
    memset(FileInformation, 0, sizeof(FileInformation));
    if ( !GetFileAttributesExW(lpFileName, GetFileExInfoStandard, FileInformation) )
      goto LABEL_62;
    v16 = 0;
    FileW = (__int64)CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, v10 != 0 ? 33554560 : 128, 0);
    if ( FileW == -1 )
      goto LABEL_62;
    goto LABEL_30;
  }
  if ( (v7 & 0x8000) != 0 )
  {
LABEL_60:
    v25 = -2147024809;
    goto LABEL_61;
  }
  if ( (v7 & 0x2000) != 0 )
    dwCreationDisposition = 1;
  else
    dwCreationDisposition = 4 - ((v7 & 0x4000) != 0);
  v15 = CreateFileW(lpFileName, 0xC0000000, 1u, 0, dwCreationDisposition, v10 != 0 ? 33554560 : 128, 0);
  FileW = (__int64)v15;
  if ( v15 == (HANDLE)-1LL )
    goto LABEL_62;
  v16 = 1;
  if ( !GetFileSize(v15, 0) )
  {
    if ( lpFileName )
    {
      v17 = -1;
      do
        ++v17;
      while ( lpFileName[v17] );
    }
    else
    {
      LODWORD(v17) = 0;
    }
    v18 = &lpFileName[(int)v17];
    while ( v18 > lpFileName )
    {
      v19 = v18--;
      if ( *v18 == 46 )
      {
        if ( CompareStringW(0x409u, 1u, v19, -1, L"p7c", -1) == 2
          || CompareStringW(0x409u, 1u, v19, -1, L"spc", -1) == 2 )
        {
          v16 = 2;
        }
        break;
      }
    }
    v20 = a7;
    goto LABEL_27;
  }
LABEL_30:
  v20 = a7;
  if ( OpenFileStoreProv(pvData[0], dwCertEncodingType, v34, v7, (const void *)FileW, hCertStore, a7) )
    goto LABEL_44;
  if ( SetFilePointer((HANDLE)FileW, 0, 0, 0) )
    goto LABEL_62;
  FileSize = GetFileSize((HANDLE)FileW, 0);
  nNumberOfBytesToRead[0] = FileSize;
  if ( FileSize == -1 )
  {
    if ( GetLastError() )
      goto LABEL_62;
    FileSize = nNumberOfBytesToRead[0];
  }
  if ( !FileSize )
  {
LABEL_41:
    if ( v29 )
    {
LABEL_27:
      v11 = OpenFileForCommit((HANDLE)FileW, 0, 0, hCertStore, dwCertEncodingType, v16, v20);
      goto LABEL_44;
    }
    v23 = a7;
    goto LABEL_43;
  }
  v22 = (void *)PkiNonzeroAlloc(FileSize);
  *(_QWORD *)&nNumberOfBytesToRead[2] = v22;
  if ( !v22 || !ReadFile((HANDLE)FileW, v22, nNumberOfBytesToRead[0], &NumberOfBytesRead, 0) )
    goto LABEL_62;
  v23 = a7;
  if ( (unsigned int)OpenPKCS7StoreProv(pvData[0], dwCertEncodingType, v34, v7, nNumberOfBytesToRead, hCertStore, a7) )
  {
    v16 = 2;
LABEL_40:
    v20 = a7;
    goto LABEL_41;
  }
  if ( !CertAddEncodedCertificateToStore(
          hCertStore,
          dwCertEncodingType,
          *(const BYTE **)&nNumberOfBytesToRead[2],
          nNumberOfBytesToRead[0],
          2u,
          0) )
  {
    if ( !CryptQueryObject(2u, nNumberOfBytesToRead, 0x6102u, 0xEu, 0, 0, 0, 0, &phCertStore, 0, 0) )
    {
      if ( (unsigned int)OpenPKCS12StoreProv(
                           pvData[0],
                           dwCertEncodingType,
                           v34,
                           v7,
                           (struct _CRYPTOAPI_BLOB *)nNumberOfBytesToRead,
                           hCertStore,
                           a7) )
      {
        v16 = 3;
        goto LABEL_40;
      }
      v25 = -2146885629;
      goto LABEL_61;
    }
    updated = I_CertUpdateStore(hCertStore, phCertStore, 0, 0);
    CertCloseStore(phCertStore, 0);
    if ( !updated )
    {
LABEL_62:
      v11 = 0;
      goto LABEL_63;
    }
  }
  if ( v29 )
  {
    v25 = 5;
LABEL_61:
    SetLastError(v25);
    goto LABEL_62;
  }
LABEL_43:
  v23->dwStoreProvFlags |= 4u;
LABEL_44:
  if ( (v7 & 2) != 0 )
  {
    HIDWORD(pvData[0]) = 0;
    pvData[1] = (const char *)lpFileName;
    if ( lpFileName )
    {
      v24 = -1;
      do
        ++v24;
      while ( lpFileName[v24] );
    }
    else
    {
      LODWORD(v24) = 0;
    }
    LODWORD(pvData[0]) = 2 * v24 + 2;
    CertSetStoreProperty(hCertStore, 0x1000u, 0, pvData);
  }
LABEL_63:
  if ( FileW != -1 )
  {
    LastError = GetLastError();
    CloseHandle((HANDLE)FileW);
    SetLastError(LastError);
  }
  if ( *(_QWORD *)&nNumberOfBytesToRead[2] )
    PkiDefaultCryptFree(*(HLOCAL *)&nNumberOfBytesToRead[2]);
  return v11;
}

```

## disassembly

```asm
0x18006c670  push    rbp
0x18006c672  push    rbx
0x18006c673  push    rsi
0x18006c674  push    rdi
0x18006c675  push    r12
0x18006c677  push    r13
0x18006c679  push    r14
0x18006c67b  push    r15
0x18006c67d  lea     rbp, [rsp-7]
0x18006c682  sub     rsp, 0E8h
0x18006c689  mov     rax, cs:__security_cookie
0x18006c690  xor     rax, rsp
0x18006c693  mov     [rbp+3Fh+var_50], rax
0x18006c697  mov     rax, [rbp+3Fh+arg_30]
0x18006c69b  mov     r14d, r9d
0x18006c69e  mov     rsi, [rbp+3Fh+lpFileName]
0x18006c6a2  xor     r9d, r9d
0x18006c6a5  mov     r13, [rbp+3Fh+hCertStore]
0x18006c6a9  and     r14d, 0FFFFFFDFh
0x18006c6ad  or      r15, 0FFFFFFFFFFFFFFFFh
0x18006c6b1  mov     [rbp+3Fh+var_90], r8
0x18006c6b5  mov     [rbp+3Fh+pvData], rcx
0x18006c6b9  xorps   xmm0, xmm0
0x18006c6bc  mov     [rsp+120h+var_C0], rax
0x18006c6c1  mov     r12d, edx
0x18006c6c4  mov     [rbp+3Fh+NumberOfBytesRead], r9d
0x18006c6c8  mov     [rbp+3Fh+var_98], r9
0x18006c6cc  movups  xmmword ptr [rbp+3Fh+nNumberOfBytesToRead], xmm0
0x18006c6d0  test    r14d, 0FFFE003Ch
0x18006c6d7  jnz     loc_18006CAF2
0x18006c6dd  mov     ebx, r14d
0x18006c6e0  and     ebx, 800h
0x18006c6e6  jz      short loc_18006C6F0
0x18006c6e8  call    ?ILS_EnableBackupRestorePrivileges@@YAXXZ; ILS_EnableBackupRestorePrivileges(void)
0x18006c6ed  xor     r9d, r9d
0x18006c6f0  mov     r8d, 10000h
0x18006c6f6  mov     ecx, r12d
0x18006c6f9  mov     edi, 1
0x18006c6fe  mov     eax, r14d
0x18006c701  or      ecx, edi
0x18006c703  test    r12w, r12w
0x18006c707  cmovnz  ecx, r12d
0x18006c70b  mov     edx, ecx
0x18006c70d  or      edx, r8d
0x18006c710  test    ecx, 0FFFF0000h
0x18006c716  cmovnz  edx, ecx
0x18006c719  and     eax, r8d
0x18006c71c  mov     [rbp+3Fh+var_B8], eax
0x18006c71f  mov     [rbp+3Fh+dwCertEncodingType], edx
0x18006c722  jz      loc_18006C860
0x18006c728  bt      r14d, 0Fh
0x18006c72d  jb      loc_18006CAF2
0x18006c733  bt      r14d, 0Dh
0x18006c738  jnb     short loc_18006C73E
0x18006c73a  mov     ecx, edi
0x18006c73c  jmp     short loc_18006C74D
0x18006c73e  mov     eax, r14d
0x18006c741  and     eax, 4000h
0x18006c746  neg     eax
0x18006c748  sbb     ecx, ecx
0x18006c74a  add     ecx, 4
0x18006c74d  mov     [rsp+120h+hTemplateFile], r9; hTemplateFile
0x18006c752  neg     ebx
0x18006c754  mov     r8d, edi; dwShareMode
0x18006c757  mov     edx, 0C0000000h; dwDesiredAccess
0x18006c75c  sbb     eax, eax
0x18006c75e  xor     r9d, r9d; lpSecurityAttributes
0x18006c761  and     eax, 2000000h
0x18006c766  sub     eax, 0FFFFFF80h
0x18006c769  mov     [rsp+120h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x18006c76d  mov     [rsp+120h+dwCreationDisposition], ecx; dwCreationDisposition
0x18006c771  mov     rcx, rsi; lpFileName
0x18006c774  call    cs:__imp_CreateFileW
0x18006c77a  mov     r15, rax
0x18006c77d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006c781  jz      loc_18006CAFD
0x18006c787  xor     edx, edx; lpFileSizeHigh
0x18006c789  mov     rcx, rax; hFile
0x18006c78c  mov     r12d, edi
0x18006c78f  call    cs:__imp_GetFileSize
0x18006c795  xor     ecx, ecx
0x18006c797  test    eax, eax
0x18006c799  jnz     loc_18006C8CA
0x18006c79f  test    rsi, rsi
0x18006c7a2  jz      short loc_18006C7B3
0x18006c7a4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006c7a8  inc     rax
0x18006c7ab  cmp     [rsi+rax*2], cx
0x18006c7af  jnz     short loc_18006C7A8
0x18006c7b1  jmp     short loc_18006C7B5
0x18006c7b3  mov     eax, ecx
0x18006c7b5  cdqe
0x18006c7b7  lea     rcx, [rsi+rax*2]
0x18006c7bb  cmp     rcx, rsi
0x18006c7be  jbe     short loc_18006C831
0x18006c7c0  mov     rbx, rcx
0x18006c7c3  mov     eax, 2Eh ; '.'
0x18006c7c8  sub     rcx, 2
0x18006c7cc  cmp     ax, [rcx]
0x18006c7cf  jnz     short loc_18006C7BB
0x18006c7d1  lea     rax, aP7c; "p7c"
0x18006c7d8  mov     [rsp+120h+dwFlagsAndAttributes], 0FFFFFFFFh; cchCount2
0x18006c7e0  or      r9d, 0FFFFFFFFh; cchCount1
0x18006c7e4  mov     qword ptr [rsp+120h+dwCreationDisposition], rax; lpString2
0x18006c7e9  mov     r8, rbx; lpString1
0x18006c7ec  mov     edx, edi; dwCmpFlags
0x18006c7ee  mov     ecx, 409h; Locale
0x18006c7f3  call    cs:__imp_CompareStringW
0x18006c7f9  cmp     eax, 2
0x18006c7fc  jz      short loc_18006C82B
0x18006c7fe  lea     rax, aSpc_1; "spc"
0x18006c805  mov     [rsp+120h+dwFlagsAndAttributes], 0FFFFFFFFh; cchCount2
0x18006c80d  or      r9d, 0FFFFFFFFh; cchCount1
0x18006c811  mov     qword ptr [rsp+120h+dwCreationDisposition], rax; lpString2
0x18006c816  mov     r8, rbx; lpString1
0x18006c819  mov     edx, edi; dwCmpFlags
0x18006c81b  mov     ecx, 409h; Locale
0x18006c820  call    cs:__imp_CompareStringW
0x18006c826  cmp     eax, 2
0x18006c829  jnz     short loc_18006C831
0x18006c82b  mov     r12d, 2
0x18006c831  mov     rbx, [rsp+120h+var_C0]
0x18006c836  mov     eax, [rbp+3Fh+dwCertEncodingType]
0x18006c839  mov     r9, r13; void *
0x18006c83c  mov     [rsp+120h+hTemplateFile], rbx; struct _CERT_STORE_PROV_INFO *
0x18006c841  xor     r8d, r8d; int
0x18006c844  mov     [rsp+120h+dwFlagsAndAttributes], r12d; unsigned int
0x18006c849  xor     edx, edx; unsigned int
0x18006c84b  mov     rcx, r15; hSourceHandle
0x18006c84e  mov     [rsp+120h+dwCreationDisposition], eax; unsigned int
0x18006c852  call    ?OpenFileForCommit@@YAHPEAXKJ0KKPEAU_CERT_STORE_PROV_INFO@@@Z; OpenFileForCommit(void *,ulong,long,void *,ulong,ulong,_CERT_STORE_PROV_INFO *)
0x18006c857  mov     edi, eax
0x18006c859  xor     ecx, ecx
0x18006c85b  jmp     loc_18006C9CB
0x18006c860  xorps   xmm0, xmm0
0x18006c863  lea     r8, [rbp+3Fh+FileInformation]; lpFileInformation
0x18006c867  xor     eax, eax
0x18006c869  xor     edx, edx; fInfoLevelId
0x18006c86b  mov     rcx, rsi; lpFileName
0x18006c86e  mov     [rbp+3Fh+var_58], eax
0x18006c871  movups  [rbp+3Fh+FileInformation], xmm0
0x18006c875  movups  [rbp+3Fh+var_68], xmm0
0x18006c879  call    cs:__imp_GetFileAttributesExW
0x18006c87f  xor     ecx, ecx
0x18006c881  test    eax, eax
0x18006c883  jz      loc_18006CAFF
0x18006c889  mov     r12d, ecx
0x18006c88c  mov     [rsp+120h+hTemplateFile], rcx; hTemplateFile
0x18006c891  neg     ebx
0x18006c893  mov     r8d, edi; dwShareMode
0x18006c896  mov     edx, 80000000h; dwDesiredAccess
0x18006c89b  sbb     eax, eax
0x18006c89d  mov     rcx, rsi; lpFileName
0x18006c8a0  and     eax, 2000000h
0x18006c8a5  xor     r9d, r9d; lpSecurityAttributes
0x18006c8a8  sub     eax, 0FFFFFF80h
0x18006c8ab  mov     [rsp+120h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x18006c8af  mov     [rsp+120h+dwCreationDisposition], 3; dwCreationDisposition
0x18006c8b7  call    cs:__imp_CreateFileW
0x18006c8bd  mov     r15, rax
0x18006c8c0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006c8c4  jz      loc_18006CAFD
0x18006c8ca  mov     rbx, [rsp+120h+var_C0]
0x18006c8cf  mov     r9d, r14d; unsigned int
0x18006c8d2  mov     r8, [rbp+3Fh+var_90]; unsigned __int64
0x18006c8d6  mov     edx, [rbp+3Fh+dwCertEncodingType]; unsigned int
0x18006c8d9  mov     rcx, [rbp+3Fh+pvData]; char *
0x18006c8dd  mov     [rsp+120h+hTemplateFile], rbx; struct _CERT_STORE_PROV_INFO *
0x18006c8e2  mov     qword ptr [rsp+120h+dwFlagsAndAttributes], r13; void *
0x18006c8e7  mov     qword ptr [rsp+120h+dwCreationDisposition], r15; void *
0x18006c8ec  call    ?OpenFileStoreProv@@YAHPEBDK_KKPEBXPEAXPEAU_CERT_STORE_PROV_INFO@@@Z; OpenFileStoreProv(char const *,ulong,unsigned __int64,ulong,void const *,void *,_CERT_STORE_PROV_INFO *)
0x18006c8f1  xor     ecx, ecx
0x18006c8f3  test    eax, eax
0x18006c8f5  jnz     loc_18006C9CB
0x18006c8fb  xor     r9d, r9d; dwMoveMethod
0x18006c8fe  xor     r8d, r8d; lpDistanceToMoveHigh
0x18006c901  xor     edx, edx; lDistanceToMove
0x18006c903  mov     rcx, r15; hFile
0x18006c906  call    cs:__imp_SetFilePointer
0x18006c90c  xor     ecx, ecx
0x18006c90e  test    eax, eax
0x18006c910  jnz     loc_18006CAFF
0x18006c916  xor     edx, edx; lpFileSizeHigh
0x18006c918  mov     rcx, r15; hFile
0x18006c91b  call    cs:__imp_GetFileSize
0x18006c921  mov     [rbp+3Fh+nNumberOfBytesToRead], eax
0x18006c924  cmp     eax, 0FFFFFFFFh
0x18006c927  jnz     short loc_18006C93E
0x18006c929  call    cs:__imp_GetLastError
0x18006c92f  xor     ecx, ecx
0x18006c931  test    eax, eax
0x18006c933  jnz     loc_18006CAFF
0x18006c939  mov     eax, [rbp+3Fh+nNumberOfBytesToRead]
0x18006c93c  jmp     short loc_18006C940
0x18006c93e  xor     ecx, ecx
0x18006c940  test    eax, eax
0x18006c942  jz      short loc_18006C9B7
0x18006c944  mov     ecx, eax; uBytes
0x18006c946  call    PkiNonzeroAlloc
0x18006c94b  xor     ecx, ecx
0x18006c94d  mov     qword ptr [rbp+3Fh+nNumberOfBytesToRead+8], rax
0x18006c951  test    rax, rax
0x18006c954  jz      loc_18006CAFF
0x18006c95a  mov     r8d, [rbp+3Fh+nNumberOfBytesToRead]; nNumberOfBytesToRead
0x18006c95e  lea     r9, [rbp+3Fh+NumberOfBytesRead]; lpNumberOfBytesRead
0x18006c962  mov     qword ptr [rsp+120h+dwCreationDisposition], rcx; lpOverlapped
0x18006c967  mov     rdx, rax; lpBuffer
0x18006c96a  mov     rcx, r15; hFile
0x18006c96d  call    cs:__imp_ReadFile
0x18006c973  xor     ecx, ecx
0x18006c975  test    eax, eax
0x18006c977  jz      loc_18006CAFF
0x18006c97d  mov     r8, [rbp+3Fh+var_90]; unsigned __int64
0x18006c981  lea     rax, [rbp+3Fh+nNumberOfBytesToRead]
0x18006c985  mov     rcx, [rbp+3Fh+pvData]; char *
0x18006c989  mov     r12, rbx
0x18006c98c  mov     [rsp+120h+hTemplateFile], rbx; struct _CERT_STORE_PROV_INFO *
0x18006c991  mov     r9d, r14d; unsigned int
0x18006c994  mov     ebx, [rbp+3Fh+dwCertEncodingType]
0x18006c997  mov     edx, ebx; unsigned int
0x18006c999  mov     qword ptr [rsp+120h+dwFlagsAndAttributes], r13; void *
0x18006c99e  mov     qword ptr [rsp+120h+dwCreationDisposition], rax; void *
0x18006c9a3  call    ?OpenPKCS7StoreProv@@YAHPEBDK_KKPEBXPEAXPEAU_CERT_STORE_PROV_INFO@@@Z; OpenPKCS7StoreProv(char const *,ulong,unsigned __int64,ulong,void const *,void *,_CERT_STORE_PROV_INFO *)
0x18006c9a8  xor     ecx, ecx
0x18006c9aa  test    eax, eax
0x18006c9ac  jz      short loc_18006C9F7
0x18006c9ae  lea     r12d, [rcx+2]
0x18006c9b2  mov     rbx, [rsp+120h+var_C0]
0x18006c9b7  cmp     [rbp+3Fh+var_B8], ecx
0x18006c9ba  jnz     loc_18006C836
0x18006c9c0  mov     r12, [rsp+120h+var_C0]
0x18006c9c5  or      dword ptr [r12+18h], 4
0x18006c9cb  test    r14b, 2
0x18006c9cf  jz      loc_18006CB01
0x18006c9d5  mov     dword ptr [rbp+3Fh+pvData+4], ecx
0x18006c9d8  mov     [rbp+3Fh+var_80], rsi
0x18006c9dc  test    rsi, rsi
0x18006c9df  jz      loc_18006CAD0
0x18006c9e5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006c9e9  inc     rax
0x18006c9ec  cmp     [rsi+rax*2], cx
0x18006c9f0  jnz     short loc_18006C9E9
0x18006c9f2  jmp     loc_18006CAD2
0x18006c9f7  mov     r9d, [rbp+3Fh+nNumberOfBytesToRead]; cbCertEncoded
0x18006c9fb  mov     edx, ebx; dwCertEncodingType
0x18006c9fd  mov     r8, qword ptr [rbp+3Fh+nNumberOfBytesToRead+8]; pbCertEncoded
0x18006ca01  mov     qword ptr [rsp+120h+dwFlagsAndAttributes], rcx; ppCertContext
0x18006ca06  mov     rcx, r13; hCertStore
0x18006ca09  mov     [rsp+120h+dwCreationDisposition], 2; dwAddDisposition
0x18006ca11  call    CertAddEncodedCertificateToStore
0x18006ca16  xor     ecx, ecx
0x18006ca18  test    eax, eax
0x18006ca1a  jz      short loc_18006CA2B
0x18006ca1c  cmp     [rbp+3Fh+var_B8], ecx
0x18006ca1f  jz      short loc_18006C9C5
0x18006ca21  mov     ecx, 5
0x18006ca26  jmp     loc_18006CAF7
0x18006ca2b  mov     [rsp+120h+ppvContext], rcx; ppvContext
0x18006ca30  lea     rax, [rbp+3Fh+var_98]
0x18006ca34  mov     [rsp+120h+phMsg], rcx; phMsg
0x18006ca39  lea     rdx, [rbp+3Fh+nNumberOfBytesToRead]; pvObject
0x18006ca3d  mov     [rsp+120h+phCertStore], rax; phCertStore
0x18006ca42  mov     r9d, 0Eh; dwExpectedFormatTypeFlags
0x18006ca48  mov     [rsp+120h+pdwFormatType], rcx; pdwFormatType
0x18006ca4d  mov     r8d, 6102h; dwExpectedContentTypeFlags
0x18006ca53  mov     [rsp+120h+hTemplateFile], rcx; pdwContentType
0x18006ca58  mov     qword ptr [rsp+120h+dwFlagsAndAttributes], rcx; pdwMsgAndCertEncodingType
0x18006ca5d  mov     [rsp+120h+dwCreationDisposition], ecx; dwFlags
0x18006ca61  lea     ecx, [r9-0Ch]; dwObjectType
0x18006ca65  call    CryptQueryObject
0x18006ca6a  test    eax, eax
0x18006ca6c  jz      short loc_18006CA95
0x18006ca6e  mov     rdx, [rbp+3Fh+var_98]
0x18006ca72  xor     r9d, r9d
0x18006ca75  xor     r8d, r8d
0x18006ca78  mov     rcx, r13
0x18006ca7b  call    I_CertUpdateStore
0x18006ca80  mov     rcx, [rbp+3Fh+var_98]; hCertStore
0x18006ca84  xor     edx, edx; dwFlags
0x18006ca86  mov     ebx, eax
0x18006ca88  call    CertCloseStore
0x18006ca8d  xor     ecx, ecx
0x18006ca8f  test    ebx, ebx
0x18006ca91  jz      short loc_18006CAFF
0x18006ca93  jmp     short loc_18006CA1C
0x18006ca95  mov     r8, [rbp+3Fh+var_90]; unsigned __int64
0x18006ca99  lea     rax, [rbp+3Fh+nNumberOfBytesToRead]
0x18006ca9d  mov     rcx, [rbp+3Fh+pvData]; char *
0x18006caa1  mov     r9d, r14d; unsigned int
0x18006caa4  mov     [rsp+120h+hTemplateFile], r12; struct _CERT_STORE_PROV_INFO *
0x18006caa9  mov     edx, ebx; unsigned int
0x18006caab  mov     qword ptr [rsp+120h+dwFlagsAndAttributes], r13; hCertStore
0x18006cab0  mov     qword ptr [rsp+120h+dwCreationDisposition], rax; struct _CRYPTOAPI_BLOB *
0x18006cab5  call    ?OpenPKCS12StoreProv@@YAHPEBDK_KKPEBXPEAXPEAU_CERT_STORE_PROV_INFO@@@Z; OpenPKCS12StoreProv(char const *,ulong,unsigned __int64,ulong,void const *,void *,_CERT_STORE_PROV_INFO *)
0x18006caba  xor     ecx, ecx
0x18006cabc  test    eax, eax
0x18006cabe  jz      short loc_18006CAC9
0x18006cac0  lea     r12d, [rcx+3]
0x18006cac4  jmp     loc_18006C9B2
0x18006cac9  mov     ecx, 80092003h
  ... truncated ...
```
