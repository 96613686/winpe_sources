# CopyPrinterDriverFilesToTempDirectory(_DRIVER_INFO_6W *,HWND__ *,unsigned __int64 *,_DRIVER_INFO_6W * *,ushort * *)

- ea: `0x18002e630`
- end: `0x18002ead3`
- name: `?CopyPrinterDriverFilesToTempDirectory@@YAJPEAU_DRIVER_INFO_6W@@PEAUHWND__@@PEA_KPEAPEAU1@PEAPEAG@Z`
- size: `1187`
- prototype: `__int64 __fastcall(struct _DRIVER_INFO_6W *, HWND, unsigned __int64 *, struct _DRIVER_INFO_6W **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002f364`

## callees

- `0x180002300`
- `0x180002f48`
- `0x18000b200`
- `0x18000d290`
- `0x18001bc44`
- `0x18002e630`
- `0x18002eadc`
- `0x18002f958`
- `0x18002fd3c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002e702`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002e702`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ea8b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ea8b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e828`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e828`
- `ADVAPI32!DecryptFileW` at `0x18002e721`
- `ADVAPI32!DecryptFileW` at `0x18002e721`
- `SETUPAPI!SetupInitDefaultQueueCallbackEx` at `0x18002e974`
- `SETUPAPI!SetupInitDefaultQueueCallbackEx` at `0x18002e974`
- `SETUPAPI!SetupOpenFileQueue` at `0x18002e8a0`
- `SETUPAPI!SetupOpenFileQueue` at `0x18002e8a0`
- `SETUPAPI!SetupTermDefaultQueueCallback` at `0x18002ea4e`
- `SETUPAPI!SetupTermDefaultQueueCallback` at `0x18002ea4e`
- `SETUPAPI!SetupCommitFileQueueW` at `0x18002e9a0`
- `SETUPAPI!SetupCommitFileQueueW` at `0x18002e9a0`
- `SETUPAPI!SetupCloseFileQueue` at `0x18002ea9a`
- `SETUPAPI!SetupCloseFileQueue` at `0x18002ea9a`

## pseudocode

```c
__int64 __fastcall CopyPrinterDriverFilesToTempDirectory(
        struct _DRIVER_INFO_6W *a1,
        HWND a2,
        unsigned __int64 *a3,
        struct _DRIVER_INFO_6W **a4,
        unsigned __int16 **a5)
{
  int UniqueTempDirInUserTempDir; // ebx
  NCoreLibrary *v9; // rcx
  NCoreLibrary *v10; // rcx
  int LastErrorAsFailHR; // eax
  unsigned __int64 v12; // r14
  unsigned int v13; // esi
  unsigned __int16 *v14; // rdi
  int v15; // ecx
  unsigned __int64 v16; // r15
  int StringSizeAndIncrementTotalSize; // eax
  unsigned __int16 *v18; // rax
  struct _DRIVER_INFO_6W *v19; // rdi
  __int128 v20; // xmm0
  unsigned __int16 *v21; // rsi
  NCoreLibrary *v22; // rcx
  HSPFILEQ v23; // r12
  unsigned int v24; // r14d
  __int16 v25; // r11
  __int64 v26; // rcx
  wchar_t *v27; // r15
  unsigned __int16 **v28; // r8
  int v29; // ecx
  unsigned __int16 *v30; // rax
  __int64 v31; // r9
  unsigned __int64 v32; // r14
  NCoreLibrary *v33; // rcx
  PVOID inited; // rsi
  NCoreLibrary *v35; // rcx
  unsigned __int16 *v36; // rsi
  __int64 v37; // rax
  unsigned __int16 *v39; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v40; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v41; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v42; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v43; // [rsp+50h] [rbp-B0h]
  __int64 v44; // [rsp+58h] [rbp-A8h]
  HWND OwnerWindow; // [rsp+60h] [rbp-A0h]
  unsigned __int16 **v46; // [rsp+68h] [rbp-98h]
  struct _DRIVER_INFO_6W **v47; // [rsp+70h] [rbp-90h]
  unsigned __int64 *v48; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v49; // [rsp+80h] [rbp-80h] BYREF
  WCHAR PathName[264]; // [rsp+90h] [rbp-70h] BYREF

  OwnerWindow = a2;
  v48 = a3;
  v46 = a5;
  v47 = a4;
  memset_0(PathName, 0, 0x208u);
  v39 = 0;
  v41 = 0;
  if ( !a1 || !a3 || !a4 || !a5 )
    return (unsigned int)-2147024809;
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  UniqueTempDirInUserTempDir = GetUniqueTempDirInUserTempDir(PathName);
  if ( UniqueTempDirInUserTempDir >= 0 )
  {
    UniqueTempDirInUserTempDir = StringCchLengthW(PathName, 0x7FFFFFFFu, (unsigned __int64 *)&v39);
    if ( UniqueTempDirInUserTempDir >= 0 )
    {
      if ( CreateDirectoryW(PathName, 0)
        || (UniqueTempDirInUserTempDir = NCoreLibrary::GetLastErrorAsFailHR(v9), UniqueTempDirInUserTempDir >= 0) )
      {
        if ( DecryptFileW(PathName, 0)
          || (LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v10),
              UniqueTempDirInUserTempDir = LastErrorAsFailHR,
              LastErrorAsFailHR == -2147018881) )
        {
          UniqueTempDirInUserTempDir = 0;
        }
        else if ( LastErrorAsFailHR < 0 )
        {
          return (unsigned int)UniqueTempDirInUserTempDir;
        }
        v12 = 0;
        v40 = 0;
        v13 = 0;
        do
        {
          if ( v13 >= 0xE )
            break;
          v14 = *(unsigned __int16 **)((char *)&a1->cVersion + *(unsigned int *)&DriverInfo6Strings[4 * v13]);
          if ( v14 )
          {
            v15 = *(_DWORD *)&DriverInfo6Strings[4 * v13 + 2];
            v16 = (unsigned __int64)v39 & -(__int64)((v15 & 4) != 0);
            if ( (v15 & 1) != 0 )
            {
              StringSizeAndIncrementTotalSize = GetStringSizeAndIncrementTotalSize(
                                                  v14,
                                                  &v40,
                                                  (unsigned __int64)v39 & -(__int64)((v15 & 4) != 0));
              v12 = v40;
              UniqueTempDirInUserTempDir = StringSizeAndIncrementTotalSize;
            }
            else if ( (v15 & 2) != 0 )
            {
              if ( UniqueTempDirInUserTempDir >= 0 )
              {
                while ( *v14 )
                {
                  UniqueTempDirInUserTempDir = GetStringSizeAndIncrementTotalSize(v14, &v40, v16);
                  if ( UniqueTempDirInUserTempDir < 0 )
                    break;
                  UniqueTempDirInUserTempDir = StringCchLengthW(v14, 0x7FFFFFFFu, &v41);
                  if ( UniqueTempDirInUserTempDir < 0 )
                    break;
                  v14 += v41 + 1;
                }
                v12 = v40;
              }
              v40 = ++v12;
            }
          }
          ++v13;
        }
        while ( UniqueTempDirInUserTempDir >= 0 );
        if ( UniqueTempDirInUserTempDir >= 0 )
        {
          v18 = (unsigned __int16 *)LocalAlloc(0x40u, (unsigned int)(2 * v12 + 136));
          v19 = (struct _DRIVER_INFO_6W *)v18;
          if ( !v18 )
            return (unsigned int)-2147024882;
          v20 = *(_OWORD *)&a1->cVersion;
          v21 = v18 + 68;
          v42 = v12;
          v39 = v18 + 68;
          *(_OWORD *)v18 = v20;
          *((_OWORD *)v18 + 1) = *(_OWORD *)&a1->pEnvironment;
          *((_OWORD *)v18 + 2) = *(_OWORD *)&a1->pDataFile;
          *((_OWORD *)v18 + 3) = *(_OWORD *)&a1->pHelpFile;
          *((_OWORD *)v18 + 4) = *(_OWORD *)&a1->pMonitorName;
          *((_OWORD *)v18 + 5) = *(_OWORD *)&a1->pszzPreviousNames;
          *((_OWORD *)v18 + 6) = *(_OWORD *)&a1->dwlDriverVersion;
          *((_OWORD *)v18 + 7) = *(_OWORD *)&a1->pszOEMUrl;
          *((_QWORD *)v18 + 16) = a1->pszProvider;
          v23 = SetupOpenFileQueue();
          if ( v23 == (HSPFILEQ)-1LL )
          {
            UniqueTempDirInUserTempDir = NCoreLibrary::GetLastErrorAsFailHR(v22);
            if ( UniqueTempDirInUserTempDir < 0 )
              goto LABEL_58;
          }
          else
          {
            UniqueTempDirInUserTempDir = 0;
          }
          v24 = 0;
          do
          {
            if ( v24 >= 0xE )
              break;
            v25 = 0;
            v26 = *(unsigned int *)&DriverInfo6Strings[4 * v24];
            v27 = *(wchar_t **)((char *)&a1->cVersion + v26);
            if ( v27 )
            {
              v28 = (unsigned __int16 **)((char *)v19 + v26);
              v29 = *(_DWORD *)&DriverInfo6Strings[4 * v24 + 2];
              v30 = (unsigned __int16 *)((unsigned __int64)PathName & -(__int64)((v29 & 4) != 0));
              v31 = -1;
              v43 = v30;
              if ( (v29 & 4) != 0 )
                v31 = (__int64)v23;
              v44 = v31;
              if ( (v29 & 1) != 0 )
              {
                UniqueTempDirInUserTempDir = CopyStringAndAddToFileQueueForCopy(v27, &v39, &v42, v28, v30, (void *)v31);
LABEL_39:
                v21 = v39;
              }
              else if ( (v29 & 2) != 0 )
              {
                *v28 = v21;
                while ( *v27 != v25 )
                {
                  UniqueTempDirInUserTempDir = CopyStringAndAddToFileQueueForCopy(
                                                 v27,
                                                 &v39,
                                                 &v42,
                                                 &v49,
                                                 v30,
                                                 (void *)v31);
                  if ( UniqueTempDirInUserTempDir < 0 )
                    goto LABEL_39;
                  UniqueTempDirInUserTempDir = StringCchLengthW(v27, 0x7FFFFFFFu, &v41);
                  if ( UniqueTempDirInUserTempDir < 0 )
                    goto LABEL_39;
                  v31 = v44;
                  v30 = v43;
                  v27 += v41 + 1;
                }
                v36 = v39;
                *v39 = 0;
                v21 = v36 + 1;
                v39 = v21;
              }
            }
            ++v24;
          }
          while ( UniqueTempDirInUserTempDir >= 0 );
          v32 = v40;
          if ( UniqueTempDirInUserTempDir >= 0 )
          {
            inited = SetupInitDefaultQueueCallbackEx(OwnerWindow, 0, 0, 0, 0);
            if ( inited
              || (UniqueTempDirInUserTempDir = NCoreLibrary::GetLastErrorAsFailHR(v33), UniqueTempDirInUserTempDir >= 0) )
            {
              if ( SetupCommitFileQueueW(0, v23, QueueCallback, inited) )
                UniqueTempDirInUserTempDir = 0;
              else
                UniqueTempDirInUserTempDir = NCoreLibrary::GetLastErrorAsFailHR(v35);
            }
            SetupTermDefaultQueueCallback(inited);
            if ( UniqueTempDirInUserTempDir >= 0 )
            {
              v37 = AllocStr(PathName);
              *v46 = (unsigned __int16 *)v37;
              if ( v37 )
              {
                UniqueTempDirInUserTempDir = 0;
                *v47 = v19;
                *v48 = v32;
                goto LABEL_59;
              }
              UniqueTempDirInUserTempDir = -2147024882;
            }
          }
LABEL_58:
          LocalFree(v19);
LABEL_59:
          if ( v23 != (HSPFILEQ)-1LL )
            SetupCloseFileQueue(v23);
        }
      }
    }
  }
  return (unsigned int)UniqueTempDirInUserTempDir;
}

```

## disassembly

```asm
0x18002e630  push    rbp
0x18002e632  push    rbx
0x18002e633  push    rsi
0x18002e634  push    rdi
0x18002e635  push    r12
0x18002e637  push    r13
0x18002e639  push    r14
0x18002e63b  push    r15
0x18002e63d  lea     rbp, [rsp-1B8h]
0x18002e645  sub     rsp, 2B8h
0x18002e64c  mov     rax, cs:__security_cookie
0x18002e653  xor     rax, rsp
0x18002e656  mov     [rbp+1F0h+var_50], rax
0x18002e65d  mov     rsi, [rbp+1F0h+arg_20]
0x18002e664  mov     rbx, r8
0x18002e667  mov     [rsp+2F0h+OwnerWindow], rdx
0x18002e66c  mov     r13, rcx
0x18002e66f  xor     edx, edx; Val
0x18002e671  mov     [rsp+2F0h+var_278], rbx
0x18002e676  mov     r8d, 208h; Size
0x18002e67c  mov     [rsp+2F0h+var_288], rsi
0x18002e681  lea     rcx, [rbp+1F0h+PathName]; void *
0x18002e685  mov     [rsp+2F0h+var_280], r9
0x18002e68a  mov     rdi, r9
0x18002e68d  call    memset_0
0x18002e692  xor     r15d, r15d
0x18002e695  mov     [rsp+2F0h+var_2C0], r15
0x18002e69a  mov     [rsp+2F0h+var_2B0], r15
0x18002e69f  test    r13, r13
0x18002e6a2  jz      loc_18002EAA9
0x18002e6a8  test    rbx, rbx
0x18002e6ab  jz      loc_18002EAA9
0x18002e6b1  test    rdi, rdi
0x18002e6b4  jz      loc_18002EAA9
0x18002e6ba  test    rsi, rsi
0x18002e6bd  jz      loc_18002EAA9
0x18002e6c3  mov     [rbx], r15
0x18002e6c6  lea     rcx, [rbp+1F0h+PathName]; lpPathName
0x18002e6ca  mov     [rdi], r15
0x18002e6cd  mov     [rsi], r15
0x18002e6d0  call    GetUniqueTempDirInUserTempDir
0x18002e6d5  mov     ebx, eax
0x18002e6d7  test    eax, eax
0x18002e6d9  js      loc_18002EAAE
0x18002e6df  lea     r8, [rsp+2F0h+var_2C0]; unsigned __int64 *
0x18002e6e4  mov     edx, 7FFFFFFFh; unsigned __int64
0x18002e6e9  lea     rcx, [rbp+1F0h+PathName]; unsigned __int16 *
0x18002e6ed  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002e6f2  mov     ebx, eax
0x18002e6f4  test    eax, eax
0x18002e6f6  js      loc_18002EAAE
0x18002e6fc  xor     edx, edx; lpSecurityAttributes
0x18002e6fe  lea     rcx, [rbp+1F0h+PathName]; lpPathName
0x18002e702  call    cs:__imp_CreateDirectoryW
0x18002e708  test    eax, eax
0x18002e70a  jnz     short loc_18002E71B
0x18002e70c  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002e711  mov     ebx, eax
0x18002e713  test    eax, eax
0x18002e715  js      loc_18002EAAE
0x18002e71b  xor     edx, edx; dwReserved
0x18002e71d  lea     rcx, [rbp+1F0h+PathName]; lpFileName
0x18002e721  call    cs:__imp_DecryptFileW
0x18002e727  test    eax, eax
0x18002e729  jz      short loc_18002E730
0x18002e72b  mov     ebx, r15d
0x18002e72e  jmp     short loc_18002E746
0x18002e730  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002e735  mov     ebx, eax
0x18002e737  cmp     eax, 8007177Fh
0x18002e73c  jz      short loc_18002E72B
0x18002e73e  test    eax, eax
0x18002e740  js      loc_18002EAAE
0x18002e746  mov     r14, r15
0x18002e749  mov     [rsp+2F0h+var_2B8], r15
0x18002e74e  mov     esi, r15d
0x18002e751  lea     rdx, DriverInfo6Strings; "\b"
0x18002e758  cmp     esi, 0Eh
0x18002e75b  jnb     loc_18002E813
0x18002e761  mov     ecx, esi
0x18002e763  mov     eax, [rdx+rcx*8]
0x18002e766  mov     rdi, [rax+r13]
0x18002e76a  test    rdi, rdi
0x18002e76d  jz      loc_18002E802
0x18002e773  mov     ecx, [rdx+rcx*8+4]
0x18002e777  mov     al, cl
0x18002e779  and     al, 4
0x18002e77b  neg     al
0x18002e77d  sbb     r15, r15
0x18002e780  and     r15, [rsp+2F0h+var_2C0]
0x18002e785  test    cl, 1
0x18002e788  jz      short loc_18002E7A3
0x18002e78a  mov     r8, r15; unsigned __int64
0x18002e78d  lea     rdx, [rsp+2F0h+var_2B8]; unsigned __int64 *
0x18002e792  mov     rcx, rdi; unsigned __int16 *
0x18002e795  call    ?GetStringSizeAndIncrementTotalSize@@YAJPEAGPEA_K_K@Z; GetStringSizeAndIncrementTotalSize(ushort *,unsigned __int64 *,unsigned __int64)
0x18002e79a  mov     r14, [rsp+2F0h+var_2B8]
0x18002e79f  mov     ebx, eax
0x18002e7a1  jmp     short loc_18002E7FF
0x18002e7a3  test    cl, 2
0x18002e7a6  jz      short loc_18002E7FF
0x18002e7a8  xor     r12d, r12d
0x18002e7ab  test    ebx, ebx
0x18002e7ad  js      short loc_18002E7F7
0x18002e7af  cmp     [rdi], r12w
0x18002e7b3  jz      short loc_18002E7F2
0x18002e7b5  mov     r8, r15; unsigned __int64
0x18002e7b8  lea     rdx, [rsp+2F0h+var_2B8]; unsigned __int64 *
0x18002e7bd  mov     rcx, rdi; unsigned __int16 *
0x18002e7c0  call    ?GetStringSizeAndIncrementTotalSize@@YAJPEAGPEA_K_K@Z; GetStringSizeAndIncrementTotalSize(ushort *,unsigned __int64 *,unsigned __int64)
0x18002e7c5  mov     ebx, eax
0x18002e7c7  test    eax, eax
0x18002e7c9  js      short loc_18002E7F2
0x18002e7cb  lea     r8, [rsp+2F0h+var_2B0]; unsigned __int64 *
0x18002e7d0  mov     edx, 7FFFFFFFh; unsigned __int64
0x18002e7d5  mov     rcx, rdi; unsigned __int16 *
0x18002e7d8  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002e7dd  mov     ebx, eax
0x18002e7df  test    eax, eax
0x18002e7e1  js      short loc_18002E7F2
0x18002e7e3  mov     rax, [rsp+2F0h+var_2B0]
0x18002e7e8  lea     rdi, [rdi+rax*2]
0x18002e7ec  add     rdi, 2
0x18002e7f0  jmp     short loc_18002E7AF
0x18002e7f2  mov     r14, [rsp+2F0h+var_2B8]
0x18002e7f7  inc     r14
0x18002e7fa  mov     [rsp+2F0h+var_2B8], r14
0x18002e7ff  xor     r15d, r15d
0x18002e802  inc     esi
0x18002e804  lea     rdx, DriverInfo6Strings; "\b"
0x18002e80b  test    ebx, ebx
0x18002e80d  jns     loc_18002E758
0x18002e813  test    ebx, ebx
0x18002e815  js      loc_18002EAAE
0x18002e81b  lea     edx, ds:88h[r14*2]; uBytes
0x18002e823  mov     ecx, 40h ; '@'; uFlags
0x18002e828  call    cs:__imp_LocalAlloc
0x18002e82e  mov     rdi, rax
0x18002e831  test    rax, rax
0x18002e834  jz      loc_18002EAA2
0x18002e83a  movups  xmm0, xmmword ptr [r13+0]
0x18002e83f  lea     rsi, [rdi+88h]
0x18002e846  mov     [rsp+2F0h+var_2A8], r14
0x18002e84b  mov     [rsp+2F0h+var_2C0], rsi
0x18002e850  movups  xmmword ptr [rax], xmm0
0x18002e853  movups  xmm1, xmmword ptr [r13+10h]
0x18002e858  movups  xmmword ptr [rax+10h], xmm1
0x18002e85c  movups  xmm0, xmmword ptr [r13+20h]
0x18002e861  movups  xmmword ptr [rax+20h], xmm0
0x18002e865  movups  xmm1, xmmword ptr [r13+30h]
0x18002e86a  movups  xmmword ptr [rax+30h], xmm1
0x18002e86e  movups  xmm0, xmmword ptr [r13+40h]
0x18002e873  movups  xmmword ptr [rax+40h], xmm0
0x18002e877  movups  xmm1, xmmword ptr [r13+50h]
0x18002e87c  movups  xmmword ptr [rax+50h], xmm1
0x18002e880  movups  xmm0, xmmword ptr [r13+60h]
0x18002e885  movups  xmmword ptr [rax+60h], xmm0
0x18002e889  movups  xmm1, xmmword ptr [r13+70h]
0x18002e88e  movups  xmmword ptr [rax+70h], xmm1
0x18002e892  mov     rax, [r13+80h]
0x18002e899  mov     [rdi+80h], rax
0x18002e8a0  call    cs:__imp_SetupOpenFileQueue
0x18002e8a6  mov     r12, rax
0x18002e8a9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002e8ad  jz      short loc_18002E8B4
0x18002e8af  mov     ebx, r15d
0x18002e8b2  jmp     short loc_18002E8C3
0x18002e8b4  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002e8b9  mov     ebx, eax
0x18002e8bb  test    eax, eax
0x18002e8bd  js      loc_18002EA88
0x18002e8c3  mov     r14d, r15d
0x18002e8c6  cmp     r14d, 0Eh
0x18002e8ca  jnb     loc_18002E955
0x18002e8d0  mov     eax, r14d
0x18002e8d3  lea     rdx, DriverInfo6Strings; "\b"
0x18002e8da  xor     r11d, r11d
0x18002e8dd  mov     ecx, [rdx+rax*8]
0x18002e8e0  mov     r15, [rcx+r13]
0x18002e8e4  test    r15, r15
0x18002e8e7  jz      short loc_18002E947
0x18002e8e9  lea     r9, [rbp+1F0h+PathName]
0x18002e8ed  lea     r8, [rcx+rdi]
0x18002e8f1  mov     ecx, [rdx+rax*8+4]
0x18002e8f5  mov     edx, ecx
0x18002e8f7  and     edx, 4
0x18002e8fa  mov     eax, edx
0x18002e8fc  neg     eax
0x18002e8fe  sbb     rax, rax
0x18002e901  and     rax, r9
0x18002e904  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002e908  test    edx, edx
0x18002e90a  mov     [rsp+2F0h+var_2A0], rax
0x18002e90f  cmovnz  r9, r12
0x18002e913  mov     [rsp+2F0h+var_298], r9
0x18002e918  test    cl, 1
0x18002e91b  jz      loc_18002E9B6
0x18002e921  mov     [rsp+2F0h+var_2C8], r9; void *
0x18002e926  lea     rdx, [rsp+2F0h+var_2C0]; unsigned __int16 **
0x18002e92b  mov     r9, r8; unsigned __int16 **
0x18002e92e  mov     [rsp+2F0h+Reserved2], rax; unsigned __int16 *
0x18002e933  lea     r8, [rsp+2F0h+var_2A8]; unsigned __int64 *
0x18002e938  mov     rcx, r15; Str
0x18002e93b  call    ?CopyStringAndAddToFileQueueForCopy@@YAJPEAGPEAPEAGPEA_K10PEAX@Z; CopyStringAndAddToFileQueueForCopy(ushort *,ushort * *,unsigned __int64 *,ushort * *,ushort *,void *)
0x18002e940  mov     ebx, eax
0x18002e942  mov     rsi, [rsp+2F0h+var_2C0]
0x18002e947  xor     r15d, r15d
0x18002e94a  inc     r14d
0x18002e94d  test    ebx, ebx
0x18002e94f  jns     loc_18002E8C6
0x18002e955  mov     r14, [rsp+2F0h+var_2B8]
0x18002e95a  test    ebx, ebx
0x18002e95c  js      loc_18002EA88
0x18002e962  mov     rcx, [rsp+2F0h+OwnerWindow]; OwnerWindow
0x18002e967  xor     r9d, r9d; Reserved1
0x18002e96a  xor     r8d, r8d; ProgressMessage
0x18002e96d  mov     [rsp+2F0h+Reserved2], r15; Reserved2
0x18002e972  xor     edx, edx; AlternateProgressWindow
0x18002e974  call    cs:__imp_SetupInitDefaultQueueCallbackEx
0x18002e97a  mov     rsi, rax
0x18002e97d  test    rax, rax
0x18002e980  jnz     short loc_18002E991
0x18002e982  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002e987  mov     ebx, eax
0x18002e989  test    eax, eax
0x18002e98b  js      loc_18002EA4B
0x18002e991  mov     r9, rsi; Context
0x18002e994  lea     r8, QueueCallback; MsgHandler
0x18002e99b  mov     rdx, r12; QueueHandle
0x18002e99e  xor     ecx, ecx; Owner
0x18002e9a0  call    cs:__imp_SetupCommitFileQueueW
0x18002e9a6  test    eax, eax
0x18002e9a8  jz      loc_18002EA44
0x18002e9ae  mov     ebx, r15d
0x18002e9b1  jmp     loc_18002EA4B
0x18002e9b6  test    cl, 2
0x18002e9b9  jz      short loc_18002E947
0x18002e9bb  mov     [r8], rsi
0x18002e9be  test    ebx, ebx
0x18002e9c0  js      short loc_18002E947
0x18002e9c2  cmp     [r15], r11w
0x18002e9c6  jz      short loc_18002EA2A
0x18002e9c8  mov     [rsp+2F0h+var_2C8], r9; void *
0x18002e9cd  lea     r8, [rsp+2F0h+var_2A8]; unsigned __int64 *
0x18002e9d2  lea     r9, [rbp+1F0h+var_270]; unsigned __int16 **
0x18002e9d6  mov     [rsp+2F0h+Reserved2], rax; unsigned __int16 *
0x18002e9db  lea     rdx, [rsp+2F0h+var_2C0]; unsigned __int16 **
0x18002e9e0  mov     rcx, r15; Str
0x18002e9e3  call    ?CopyStringAndAddToFileQueueForCopy@@YAJPEAGPEAPEAGPEA_K10PEAX@Z; CopyStringAndAddToFileQueueForCopy(ushort *,ushort * *,unsigned __int64 *,ushort * *,ushort *,void *)
0x18002e9e8  xor     r11d, r11d
0x18002e9eb  mov     ebx, eax
0x18002e9ed  test    eax, eax
0x18002e9ef  js      loc_18002E942
0x18002e9f5  lea     r8, [rsp+2F0h+var_2B0]; unsigned __int64 *
0x18002e9fa  mov     edx, 7FFFFFFFh; unsigned __int64
0x18002e9ff  mov     rcx, r15; unsigned __int16 *
0x18002ea02  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002ea07  mov     ebx, eax
0x18002ea09  test    eax, eax
0x18002ea0b  js      loc_18002E942
0x18002ea11  mov     rax, [rsp+2F0h+var_2B0]
0x18002ea16  mov     r9, [rsp+2F0h+var_298]
0x18002ea1b  lea     r15, [r15+rax*2]
0x18002ea1f  mov     rax, [rsp+2F0h+var_2A0]
0x18002ea24  add     r15, 2
0x18002ea28  jmp     short loc_18002E9C2
0x18002ea2a  mov     rsi, [rsp+2F0h+var_2C0]
0x18002ea2f  xor     r15d, r15d
0x18002ea32  mov     [rsi], r15w
0x18002ea36  add     rsi, 2
0x18002ea3a  mov     [rsp+2F0h+var_2C0], rsi
0x18002ea3f  jmp     loc_18002E94A
0x18002ea44  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002ea49  mov     ebx, eax
0x18002ea4b  mov     rcx, rsi; Context
0x18002ea4e  call    cs:__imp_SetupTermDefaultQueueCallback
0x18002ea54  test    ebx, ebx
0x18002ea56  js      short loc_18002EA88
0x18002ea58  lea     rcx, [rbp+1F0h+PathName]; unsigned __int16 *
0x18002ea5c  call    AllocStr
0x18002ea61  mov     rcx, [rsp+2F0h+var_288]
0x18002ea66  mov     [rcx], rax
0x18002ea69  test    rax, rax
0x18002ea6c  jz      short loc_18002EA83
0x18002ea6e  mov     rax, [rsp+2F0h+var_280]
0x18002ea73  mov     ebx, r15d
0x18002ea76  mov     [rax], rdi
0x18002ea79  mov     rax, [rsp+2F0h+var_278]
0x18002ea7e  mov     [rax], r14
0x18002ea81  jmp     short loc_18002EA91
0x18002ea83  mov     ebx, 8007000Eh
0x18002ea88  mov     rcx, rdi; hMem
0x18002ea8b  call    cs:__imp_LocalFree
0x18002ea91  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x18002ea95  jz      short loc_18002EAAE
0x18002ea97  mov     rcx, r12; QueueHandle
0x18002ea9a  call    cs:__imp_SetupCloseFileQueue
0x18002eaa0  jmp     short loc_18002EAAE
0x18002eaa2  mov     ebx, 8007000Eh
0x18002eaa7  jmp     short loc_18002EAAE
  ... truncated ...
```
