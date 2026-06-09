# CDRMReader::CreateLicenseCache(uint,int)

- ea: `0x180022c8c`
- end: `0x180023255`
- name: `?CreateLicenseCache@CDRMReader@@AEAAJIH@Z`
- size: `1481`
- prototype: `__int64 __fastcall(CDRMReader *__hidden this, unsigned int, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180023518`

## callees

- `0x180001244`
- `0x180001284`
- `0x180004654`
- `0x18001ee4c`
- `0x18001f610`
- `0x180022c8c`
- `0x180023400`
- `0x18002348c`
- `0x180036b9c`
- `0x180039768`
- `0x18005bd72`
- `0x18005bdc0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002313a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180023180`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800231a5`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002313a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180023180`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800231a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022d29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023239`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022d29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023239`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180022d1f`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180023124`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18002316a`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180022d1f`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180023124`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18002316a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180022cdd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180022cdd`

## pseudocode

```c
__int64 __fastcall CDRMReader::CreateLicenseCache(CDRMReader *this, char a2)
{
  void *v4; // r15
  int v5; // edi
  __int64 v6; // rdx
  signed int LastError; // ebx
  int v8; // eax
  int v9; // eax
  CDRMCBase *v10; // rcx
  unsigned int *v11; // r14
  __int64 *v12; // r13
  CDRMCBase *v13; // rcx
  __int64 *v14; // r12
  void *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // r12
  unsigned int v19; // r14d
  int PersistedLicense; // eax
  CDRMCBase *v21; // rcx
  unsigned int v22; // r13d
  CDRMCBase *v23; // rcx
  unsigned int v24; // eax
  void *v25; // rax
  int v26; // edi
  unsigned int v27; // edi
  __int64 v29; // rcx
  unsigned int v30; // eax
  __int64 v31; // r14
  unsigned __int16 *v32; // rcx
  void *v33; // rcx
  unsigned __int16 *v34; // rcx
  unsigned __int64 v35; // rdx
  unsigned __int64 v36; // rax
  DWORD v37; // eax
  CDRMCBase *v38; // [rsp+40h] [rbp-99h] BYREF
  unsigned int v39; // [rsp+48h] [rbp-91h]
  unsigned int v40; // [rsp+4Ch] [rbp-8Dh] BYREF
  void *Block; // [rsp+50h] [rbp-89h] BYREF
  unsigned __int16 **v42; // [rsp+58h] [rbp-81h] BYREF
  unsigned __int16 **v43; // [rsp+60h] [rbp-79h] BYREF
  unsigned int v44; // [rsp+68h] [rbp-71h] BYREF
  struct _FILETIME FileTime; // [rsp+70h] [rbp-69h] BYREF
  FILETIME FileTime2; // [rsp+78h] [rbp-61h] BYREF
  FILETIME FileTime1; // [rsp+80h] [rbp-59h] BYREF
  __int64 v48; // [rsp+88h] [rbp-51h]
  unsigned __int16 **v49; // [rsp+90h] [rbp-49h] BYREF
  unsigned __int16 **v50; // [rsp+98h] [rbp-41h] BYREF
  _QWORD v51[2]; // [rsp+A0h] [rbp-39h] BYREF
  unsigned __int16 **v52; // [rsp+B0h] [rbp-29h] BYREF
  SYSTEMTIME v53; // [rsp+B8h] [rbp-21h] BYREF
  SYSTEMTIME v54; // [rsp+C8h] [rbp-11h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+D8h] [rbp-1h] BYREF

  FileTime1 = 0;
  FileTime2 = 0;
  FileTime = 0;
  v53 = 0;
  v54 = 0;
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  Block = 0;
  v39 = 0;
  v38 = 0;
  v4 = 0;
  v49 = 0;
  v5 = a2 & 0x60;
  v50 = 0;
  v44 = 0;
  v52 = 0;
  v42 = 0;
  v43 = 0;
  if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
  {
    LastError = GetLastError();
    goto LABEL_3;
  }
  v51[0] = *((_QWORD *)this + 22);
  v51[1] = *((_QWORD *)this + 23);
  if ( v5 )
  {
    PersistedLicense = GetPersistedLicenseEx(2, v6, 2, v51, 0, (char *)&v38 + 4, &v49, &v50);
    LastError = PersistedLicense;
    if ( PersistedLicense == -2147168454 )
    {
      LastError = 0;
      goto LABEL_32;
    }
    if ( PersistedLicense < 0 )
      goto LABEL_31;
    v22 = HIDWORD(v38);
    v40 = *((_DWORD *)this + 64);
    LastError = CDRMCBase::AddArrayToArrayOfStrings(v21, HIDWORD(v38), &v49, &v40, (unsigned __int16 ***)this + 33);
    if ( LastError < 0 )
      goto LABEL_31;
    LODWORD(v38) = *((_DWORD *)this + 64);
    LastError = CDRMCBase::AddArrayToArrayOfStrings(
                  v23,
                  v22,
                  &v50,
                  (unsigned int *)&v38,
                  (unsigned __int16 ***)this + 31);
    if ( LastError < 0 )
      goto LABEL_31;
    v24 = (unsigned int)v38;
    if ( v40 != (_DWORD)v38 )
    {
LABEL_14:
      LastError = 0;
      goto LABEL_32;
    }
    *((_DWORD *)this + 64) = (_DWORD)v38;
    v25 = operator new(saturated_mul(v24, 4u));
    *((_QWORD *)this + 34) = v25;
    if ( !v25 )
    {
      LastError = -2147024882;
      goto LABEL_31;
    }
    memset_0(v25, 0, 4LL * *((unsigned int *)this + 64));
    v16 = *((_QWORD *)this + 31);
    v17 = *((_QWORD *)this + 33);
    v19 = *((_DWORD *)this + 64);
    v18 = *((_QWORD *)this + 34);
    goto LABEL_34;
  }
  v9 = GetPersistedLicenseEx(4, v6, 0, 0, 0, &v38, &v43, &v42);
  v10 = (CDRMCBase *)(unsigned int)v38;
  LastError = v9;
  v39 = (unsigned int)v38;
  if ( v9 == -2147168454 || !(_DWORD)v38 )
  {
    LastError = 0;
    v12 = (__int64 *)((char *)this + 280);
    v11 = (unsigned int *)((char *)this + 288);
    v14 = (__int64 *)((char *)this + 296);
  }
  else
  {
    if ( v9 < 0 )
      goto LABEL_6;
    v11 = (unsigned int *)((char *)this + 288);
    v12 = (__int64 *)((char *)this + 280);
    LODWORD(v38) = *((_DWORD *)this + 72);
    LastError = CDRMCBase::AddArrayToArrayOfStrings(
                  v10,
                  (unsigned int)v10,
                  &v42,
                  (unsigned int *)&v38,
                  (unsigned __int16 ***)this + 35);
    if ( LastError < 0 )
      goto LABEL_6;
    v14 = (__int64 *)((char *)this + 296);
    LastError = CDRMCBase::AddArrayToArrayOfStrings(
                  v13,
                  v39,
                  &v43,
                  (unsigned int *)this + 72,
                  (unsigned __int16 ***)this + 37);
    if ( LastError < 0 )
      goto LABEL_6;
    if ( (_DWORD)v38 != *v11 )
      goto LABEL_14;
    LODWORD(v38) = v39;
    LastError = CDRMCBase::DeleteArrayofString(&v42, (unsigned int *)&v38);
    if ( LastError < 0 )
      goto LABEL_6;
    LODWORD(v38) = v39;
    LastError = CDRMCBase::DeleteArrayofString(&v43, (unsigned int *)&v38);
    if ( LastError < 0 )
      goto LABEL_6;
    v39 = 0;
  }
  if ( *v11 )
  {
    v15 = operator new(saturated_mul(*v11, 4u));
    *((_QWORD *)this + 38) = v15;
    if ( !v15 )
    {
      LastError = -2147024882;
      goto LABEL_6;
    }
    memset_0(v15, 0, 4LL * *v11);
    v16 = *v12;
    v17 = *v14;
    v18 = *((_QWORD *)this + 38);
    v19 = *v11;
LABEL_34:
    LODWORD(v38) = v19;
    v51[0] = v17;
    v48 = v16;
    if ( v16 )
    {
      v29 = 0;
      v40 = 0;
      if ( v19 )
      {
        v30 = v19;
        do
        {
          v31 = (unsigned int)v29;
          v53 = 0;
          v54 = 0;
          v32 = *(unsigned __int16 **)(v16 + 8 * v29);
          if ( v32 )
          {
            v4 = 0;
            LastError = GetLicenseValidityTimeAndLicenseId(v32, &v53, &v54, (unsigned __int16 **)&Block, 0, 0);
            v8 = v5;
            if ( LastError < 0 )
            {
              v4 = Block;
LABEL_5:
              if ( !v8 )
              {
LABEL_6:
                CDRMReader::DeleteRevocationListCache(this);
                goto LABEL_32;
              }
LABEL_31:
              CDRMReader::DeleteEULCache(this);
              goto LABEL_32;
            }
            if ( !v53.wYear )
              goto LABEL_43;
            if ( !SystemTimeToFileTime(&v53, &FileTime1) )
              goto LABEL_63;
            if ( CompareFileTime(&FileTime1, &FileTime) == 1 )
            {
              v33 = Block;
              *(_DWORD *)(v18 + 4 * v31) = -1;
              operator delete(v33);
            }
            else
            {
LABEL_43:
              if ( v54.wYear )
              {
                if ( !SystemTimeToFileTime(&v54, &FileTime2) )
                {
LABEL_63:
                  v37 = GetLastError();
                  v4 = Block;
                  LastError = v37;
                  break;
                }
                if ( CompareFileTime(&FileTime, &FileTime2) == 1 )
                  *(_DWORD *)(v18 + 4 * v31) = 1;
              }
              if ( v53.wYear && v54.wYear && CompareFileTime(&FileTime1, &FileTime2) == 1 )
                *(_DWORD *)(v18 + 4 * v31) = -1;
              v4 = Block;
              if ( *(_DWORD *)(v18 + 4 * v31) != -1 )
              {
                v34 = *(unsigned __int16 **)(v51[0] + 8 * v31);
                if ( v34 )
                {
                  v35 = -1;
                  do
                    ++v35;
                  while ( v34[v35] );
                  v36 = -1;
                  do
                    ++v36;
                  while ( *((_WORD *)Block + v36) );
                  if ( v35 >= v36 )
                  {
                    LastError = StringCchCopyW(v34, v35 + 1, (const unsigned __int16 *)Block);
                    v8 = v5;
                    if ( LastError < 0 )
                      goto LABEL_5;
                  }
                }
              }
              operator delete(v4);
              v4 = 0;
            }
            v16 = v48;
            v30 = (unsigned int)v38;
            Block = 0;
          }
          v29 = v40 + 1;
          v40 = v29;
        }
        while ( (unsigned int)v29 < v30 );
      }
    }
  }
LABEL_3:
  if ( LastError < 0 )
  {
    v8 = v5;
    goto LABEL_5;
  }
LABEL_32:
  v26 = HIDWORD(v38);
  CDRMCBase::DeleteArrayofString(&v49, (unsigned int *)&v38 + 1);
  HIDWORD(v38) = v26;
  CDRMCBase::DeleteArrayofString(&v50, (unsigned int *)&v38 + 1);
  operator delete(v4);
  operator delete(0);
  CDRMCBase::DeleteArrayofString(&v52, &v44);
  v27 = v39;
  HIDWORD(v38) = v39;
  CDRMCBase::DeleteArrayofString(&v42, (unsigned int *)&v38 + 1);
  HIDWORD(v38) = v27;
  CDRMCBase::DeleteArrayofString(&v43, (unsigned int *)&v38 + 1);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180022c8c  push    rbp
0x180022c8e  push    rbx
0x180022c8f  push    rsi
0x180022c90  push    rdi
0x180022c91  push    r12
0x180022c93  push    r13
0x180022c95  push    r14
0x180022c97  push    r15
0x180022c99  lea     rbp, [rsp-1Fh]
0x180022c9e  sub     rsp, 0F8h
0x180022ca5  mov     rax, cs:__security_cookie
0x180022cac  xor     rax, rsp
0x180022caf  mov     [rbp+57h+var_48], rax
0x180022cb3  xorps   xmm0, xmm0
0x180022cb6  xor     r14d, r14d
0x180022cb9  mov     rsi, rcx
0x180022cbc  mov     qword ptr [rbp+57h+FileTime1.dwLowDateTime], r14
0x180022cc0  xorps   xmm1, xmm1
0x180022cc3  mov     qword ptr [rbp+57h+FileTime2.dwLowDateTime], r14
0x180022cc7  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180022ccb  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], r14
0x180022ccf  movups  xmmword ptr [rbp+57h+var_78.wYear], xmm0
0x180022cd3  mov     edi, edx
0x180022cd5  movups  xmmword ptr [rbp+57h+var_68.wYear], xmm1
0x180022cd9  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180022cdd  call    cs:__imp_GetSystemTime
0x180022ce3  mov     eax, r14d
0x180022ce6  mov     [rsp+130h+Block], r14
0x180022ceb  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x180022cef  mov     [rsp+130h+var_E8], eax
0x180022cf3  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180022cf7  mov     dword ptr [rsp+130h+var_F0], eax
0x180022cfb  mov     r15d, r14d
0x180022cfe  mov     dword ptr [rsp+130h+var_F0+4], r14d
0x180022d03  mov     [rbp+57h+var_A0], r14
0x180022d07  and     edi, 60h
0x180022d0a  mov     [rbp+57h+var_98], r14
0x180022d0e  mov     [rbp+57h+var_C8], r14d
0x180022d12  mov     [rbp+57h+var_80], r14
0x180022d16  mov     [rsp+130h+var_D8], r14
0x180022d1b  mov     [rbp+57h+var_D0], r14
0x180022d1f  call    cs:__imp_SystemTimeToFileTime
0x180022d25  test    eax, eax
0x180022d27  jnz     short loc_180022D50
0x180022d29  call    cs:__imp_GetLastError
0x180022d2f  mov     ebx, eax
0x180022d31  test    ebx, ebx
0x180022d33  jns     loc_180022FEB
0x180022d39  mov     eax, edi
0x180022d3b  test    eax, eax
0x180022d3d  jnz     loc_180022FE3
0x180022d43  mov     rcx, rsi; this
0x180022d46  call    ?DeleteRevocationListCache@CDRMReader@@QEAAJXZ; CDRMReader::DeleteRevocationListCache(void)
0x180022d4b  jmp     loc_180022FEB
0x180022d50  mov     rax, [rsi+0B0h]
0x180022d57  mov     [rbp+57h+var_90], rax
0x180022d5b  mov     rax, [rsi+0B8h]
0x180022d62  mov     [rbp+57h+var_88], rax
0x180022d66  test    edi, edi
0x180022d68  jnz     loc_180022EF3
0x180022d6e  lea     rax, [rsp+130h+var_D8]
0x180022d73  xor     r9d, r9d
0x180022d76  mov     [rsp+130h+var_F8], rax
0x180022d7b  lea     ecx, [rdi+4]
0x180022d7e  lea     rax, [rbp+57h+var_D0]
0x180022d82  xor     r8d, r8d
0x180022d85  mov     [rsp+130h+var_100], rax
0x180022d8a  lea     rax, [rsp+130h+var_F0]
0x180022d8f  mov     [rsp+130h+var_108], rax
0x180022d94  mov     dword ptr [rsp+130h+var_110], r14d
0x180022d99  call    ?GetPersistedLicenseEx@@YAJW4DRM_LICENSE_TYPE@@HIPEAPEAGIPEAIPEAPEAPEAG3@Z; GetPersistedLicenseEx(DRM_LICENSE_TYPE,int,uint,ushort * *,uint,uint *,ushort * * *,ushort * * *)
0x180022d9e  mov     ecx, dword ptr [rsp+130h+var_F0]; this
0x180022da2  mov     ebx, eax
0x180022da4  mov     [rsp+130h+var_E8], ecx
0x180022da8  cmp     eax, 8004CF3Ah
0x180022dad  jz      loc_180022E72
0x180022db3  test    ecx, ecx
0x180022db5  jz      loc_180022E72
0x180022dbb  test    eax, eax
0x180022dbd  js      short loc_180022D43
0x180022dbf  lea     r14, [rsi+120h]
0x180022dc6  mov     edx, ecx; unsigned int
0x180022dc8  mov     eax, [r14]
0x180022dcb  lea     r13, [rsi+118h]
0x180022dd2  lea     r9, [rsp+130h+var_F0]; unsigned int *
0x180022dd7  mov     dword ptr [rsp+130h+var_F0], eax
0x180022ddb  lea     r8, [rsp+130h+var_D8]; unsigned __int16 ***
0x180022de0  mov     [rsp+130h+var_110], r13; unsigned __int16 ***
0x180022de5  call    ?AddArrayToArrayOfStrings@CDRMCBase@@QEAAJIPEAPEAPEAGPEAI0@Z; CDRMCBase::AddArrayToArrayOfStrings(uint,ushort * * *,uint *,ushort * * *)
0x180022dea  mov     ebx, eax
0x180022dec  test    eax, eax
0x180022dee  js      loc_180022D43
0x180022df4  mov     edx, [rsp+130h+var_E8]; unsigned int
0x180022df8  lea     r12, [rsi+128h]
0x180022dff  mov     r9, r14; unsigned int *
0x180022e02  mov     [rsp+130h+var_110], r12; unsigned __int16 ***
0x180022e07  lea     r8, [rbp+57h+var_D0]; unsigned __int16 ***
0x180022e0b  call    ?AddArrayToArrayOfStrings@CDRMCBase@@QEAAJIPEAPEAPEAGPEAI0@Z; CDRMCBase::AddArrayToArrayOfStrings(uint,ushort * * *,uint *,ushort * * *)
0x180022e10  mov     ebx, eax
0x180022e12  test    eax, eax
0x180022e14  js      loc_180022D43
0x180022e1a  mov     eax, [r14]
0x180022e1d  cmp     dword ptr [rsp+130h+var_F0], eax
0x180022e21  jz      short loc_180022E2A
0x180022e23  xor     ebx, ebx
0x180022e25  jmp     loc_180022FEB
0x180022e2a  mov     eax, [rsp+130h+var_E8]
0x180022e2e  lea     rdx, [rsp+130h+var_F0]; unsigned int *
0x180022e33  lea     rcx, [rsp+130h+var_D8]; unsigned __int16 ***
0x180022e38  mov     dword ptr [rsp+130h+var_F0], eax
0x180022e3c  call    ?DeleteArrayofString@CDRMCBase@@SAJPEAPEAPEAGPEAI@Z; CDRMCBase::DeleteArrayofString(ushort * * *,uint *)
0x180022e41  mov     ebx, eax
0x180022e43  test    eax, eax
0x180022e45  js      loc_180022D43
0x180022e4b  mov     eax, [rsp+130h+var_E8]
0x180022e4f  lea     rdx, [rsp+130h+var_F0]; unsigned int *
0x180022e54  lea     rcx, [rbp+57h+var_D0]; unsigned __int16 ***
0x180022e58  mov     dword ptr [rsp+130h+var_F0], eax
0x180022e5c  call    ?DeleteArrayofString@CDRMCBase@@SAJPEAPEAPEAGPEAI@Z; CDRMCBase::DeleteArrayofString(ushort * * *,uint *)
0x180022e61  mov     ebx, eax
0x180022e63  test    eax, eax
0x180022e65  js      loc_180022D43
0x180022e6b  mov     [rsp+130h+var_E8], r15d
0x180022e70  jmp     short loc_180022E8A
0x180022e72  mov     ebx, r14d
0x180022e75  lea     r13, [rsi+118h]
0x180022e7c  lea     r14, [rsi+120h]
0x180022e83  lea     r12, [rsi+128h]
0x180022e8a  cmp     [r14], r15d
0x180022e8d  jz      loc_180022D31
0x180022e93  mov     ecx, [r14]
0x180022e96  mov     eax, 4
0x180022e9b  mul     rcx
0x180022e9e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180022ea5  cmovb   rax, rcx
0x180022ea9  mov     rcx, rax; Size
0x180022eac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022eb1  mov     [rsi+130h], rax
0x180022eb8  test    rax, rax
0x180022ebb  jnz     short loc_180022EC7
0x180022ebd  mov     ebx, 8007000Eh
0x180022ec2  jmp     loc_180022D43
0x180022ec7  mov     r8d, [r14]
0x180022eca  xor     edx, edx; Val
0x180022ecc  shl     r8, 2; Size
0x180022ed0  mov     rcx, rax; void *
0x180022ed3  call    memset_0
0x180022ed8  mov     rdx, [r13+0]
0x180022edc  or      r13, 0FFFFFFFFFFFFFFFFh
0x180022ee0  mov     rax, [r12]
0x180022ee4  mov     r12, [rsi+130h]
0x180022eeb  mov     r14d, [r14]
0x180022eee  jmp     loc_1800230A4
0x180022ef3  lea     rax, [rbp+57h+var_98]
0x180022ef7  mov     ecx, 2
0x180022efc  mov     [rsp+130h+var_F8], rax
0x180022f01  lea     r9, [rbp+57h+var_90]
0x180022f05  lea     rax, [rbp+57h+var_A0]
0x180022f09  mov     r8d, ecx
0x180022f0c  mov     [rsp+130h+var_100], rax
0x180022f11  lea     rax, [rsp+130h+var_F0+4]
0x180022f16  mov     [rsp+130h+var_108], rax
0x180022f1b  mov     dword ptr [rsp+130h+var_110], r14d
0x180022f20  call    ?GetPersistedLicenseEx@@YAJW4DRM_LICENSE_TYPE@@HIPEAPEAGIPEAIPEAPEAPEAG3@Z; GetPersistedLicenseEx(DRM_LICENSE_TYPE,int,uint,ushort * *,uint,uint *,ushort * * *,ushort * * *)
0x180022f25  mov     ebx, eax
0x180022f27  cmp     eax, 8004CF3Ah
0x180022f2c  jnz     short loc_180022F36
0x180022f2e  mov     ebx, r14d
0x180022f31  jmp     loc_180022FEB
0x180022f36  test    eax, eax
0x180022f38  js      loc_180022FE3
0x180022f3e  mov     eax, [rsi+100h]
0x180022f44  lea     r14, [rsi+108h]
0x180022f4b  mov     r13d, dword ptr [rsp+130h+var_F0+4]
0x180022f50  lea     r9, [rsp+130h+var_E4]; unsigned int *
0x180022f55  mov     edx, r13d; unsigned int
0x180022f58  mov     [rsp+130h+var_110], r14; unsigned __int16 ***
0x180022f5d  lea     r8, [rbp+57h+var_A0]; unsigned __int16 ***
0x180022f61  mov     [rsp+130h+var_E4], eax
0x180022f65  call    ?AddArrayToArrayOfStrings@CDRMCBase@@QEAAJIPEAPEAPEAGPEAI0@Z; CDRMCBase::AddArrayToArrayOfStrings(uint,ushort * * *,uint *,ushort * * *)
0x180022f6a  mov     ebx, eax
0x180022f6c  test    eax, eax
0x180022f6e  js      short loc_180022FE3
0x180022f70  mov     eax, [rsi+100h]
0x180022f76  lea     r12, [rsi+0F8h]
0x180022f7d  lea     r9, [rsp+130h+var_F0]; unsigned int *
0x180022f82  mov     [rsp+130h+var_110], r12; unsigned __int16 ***
0x180022f87  lea     r8, [rbp+57h+var_98]; unsigned __int16 ***
0x180022f8b  mov     dword ptr [rsp+130h+var_F0], eax
0x180022f8f  mov     edx, r13d; unsigned int
0x180022f92  call    ?AddArrayToArrayOfStrings@CDRMCBase@@QEAAJIPEAPEAPEAGPEAI0@Z; CDRMCBase::AddArrayToArrayOfStrings(uint,ushort * * *,uint *,ushort * * *)
0x180022f97  mov     ebx, eax
0x180022f99  test    eax, eax
0x180022f9b  js      short loc_180022FE3
0x180022f9d  mov     eax, dword ptr [rsp+130h+var_F0]
0x180022fa1  cmp     [rsp+130h+var_E4], eax
0x180022fa5  jnz     loc_180022E23
0x180022fab  mov     ecx, eax
0x180022fad  mov     r13, 0FFFFFFFFFFFFFFFFh
0x180022fb4  mov     [rsi+100h], ecx
0x180022fba  mov     eax, 4
0x180022fbf  mul     rcx
0x180022fc2  cmovb   rax, r13
0x180022fc6  mov     rcx, rax; Size
0x180022fc9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022fce  mov     [rsi+110h], rax
0x180022fd5  test    rax, rax
0x180022fd8  jnz     loc_18002307A
0x180022fde  mov     ebx, 8007000Eh
0x180022fe3  mov     rcx, rsi; this
0x180022fe6  call    ?DeleteEULCache@CDRMReader@@QEAAJXZ; CDRMReader::DeleteEULCache(void)
0x180022feb  mov     edi, dword ptr [rsp+130h+var_F0+4]
0x180022fef  lea     rdx, [rsp+130h+var_F0+4]; unsigned int *
0x180022ff4  lea     rcx, [rbp+57h+var_A0]; unsigned __int16 ***
0x180022ff8  mov     dword ptr [rsp+130h+var_F0+4], edi
0x180022ffc  call    ?DeleteArrayofString@CDRMCBase@@SAJPEAPEAPEAGPEAI@Z; CDRMCBase::DeleteArrayofString(ushort * * *,uint *)
0x180023001  lea     rdx, [rsp+130h+var_F0+4]; unsigned int *
0x180023006  mov     dword ptr [rsp+130h+var_F0+4], edi
0x18002300a  lea     rcx, [rbp+57h+var_98]; unsigned __int16 ***
0x18002300e  call    ?DeleteArrayofString@CDRMCBase@@SAJPEAPEAPEAGPEAI@Z; CDRMCBase::DeleteArrayofString(ushort * * *,uint *)
0x180023013  mov     rcx, r15; Block
0x180023016  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002301b  xor     ecx, ecx; Block
0x18002301d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023022  lea     rdx, [rbp+57h+var_C8]; unsigned int *
0x180023026  lea     rcx, [rbp+57h+var_80]; unsigned __int16 ***
0x18002302a  call    ?DeleteArrayofString@CDRMCBase@@SAJPEAPEAPEAGPEAI@Z; CDRMCBase::DeleteArrayofString(ushort * * *,uint *)
0x18002302f  mov     edi, [rsp+130h+var_E8]
0x180023033  lea     rdx, [rsp+130h+var_F0+4]; unsigned int *
0x180023038  lea     rcx, [rsp+130h+var_D8]; unsigned __int16 ***
0x18002303d  mov     dword ptr [rsp+130h+var_F0+4], edi
0x180023041  call    ?DeleteArrayofString@CDRMCBase@@SAJPEAPEAPEAGPEAI@Z; CDRMCBase::DeleteArrayofString(ushort * * *,uint *)
0x180023046  lea     rdx, [rsp+130h+var_F0+4]; unsigned int *
0x18002304b  mov     dword ptr [rsp+130h+var_F0+4], edi
0x18002304f  lea     rcx, [rbp+57h+var_D0]; unsigned __int16 ***
0x180023053  call    ?DeleteArrayofString@CDRMCBase@@SAJPEAPEAPEAGPEAI@Z; CDRMCBase::DeleteArrayofString(ushort * * *,uint *)
0x180023058  mov     eax, ebx
0x18002305a  mov     rcx, [rbp+57h+var_48]
0x18002305e  xor     rcx, rsp; StackCookie
0x180023061  call    __security_check_cookie
0x180023066  add     rsp, 0F8h
0x18002306d  pop     r15
0x18002306f  pop     r14
0x180023071  pop     r13
0x180023073  pop     r12
0x180023075  pop     rdi
0x180023076  pop     rsi
0x180023077  pop     rbx
0x180023078  pop     rbp
0x180023079  retn
0x18002307a  mov     r8d, [rsi+100h]
0x180023081  xor     edx, edx; Val
0x180023083  shl     r8, 2; Size
0x180023087  mov     rcx, rax; void *
0x18002308a  call    memset_0
0x18002308f  mov     rdx, [r12]
0x180023093  mov     rax, [r14]
0x180023096  mov     r14d, [rsi+100h]
0x18002309d  mov     r12, [rsi+110h]
0x1800230a4  mov     dword ptr [rsp+130h+var_F0], r14d
0x1800230a9  mov     [rbp+57h+var_90], rax
0x1800230ad  mov     [rbp+57h+var_A8], rdx
0x1800230b1  test    rdx, rdx
0x1800230b4  jz      loc_180022D31
0x1800230ba  xor     ecx, ecx
0x1800230bc  mov     [rsp+130h+var_E4], ecx
0x1800230c0  test    r14d, r14d
0x1800230c3  jz      loc_180022D31
0x1800230c9  mov     eax, r14d
0x1800230cc  xorps   xmm0, xmm0
0x1800230cf  mov     r14d, ecx
0x1800230d2  xorps   xmm1, xmm1
0x1800230d5  movups  xmmword ptr [rbp+57h+var_78.wYear], xmm0
0x1800230d9  movups  xmmword ptr [rbp+57h+var_68.wYear], xmm1
0x1800230dd  mov     rcx, [rdx+rcx*8]; unsigned __int16 *
0x1800230e1  test    rcx, rcx
0x1800230e4  jz      loc_180023222
0x1800230ea  xor     r15d, r15d
0x1800230ed  lea     r9, [rsp+130h+Block]; unsigned __int16 **
0x1800230f2  mov     [rsp+130h+var_108], r15; unsigned __int16 **
0x1800230f7  lea     r8, [rbp+57h+var_68]; struct _SYSTEMTIME *
0x1800230fb  lea     rdx, [rbp+57h+var_78]; struct _SYSTEMTIME *
0x1800230ff  mov     [rsp+130h+var_110], r15; unsigned __int16 **
0x180023104  call    ?GetLicenseValidityTimeAndLicenseId@@YAJPEAGPEAU_SYSTEMTIME@@1PEAPEAG22@Z; GetLicenseValidityTimeAndLicenseId(ushort *,_SYSTEMTIME *,_SYSTEMTIME *,ushort * *,ushort * *,ushort * *)
0x180023109  mov     ebx, eax
0x18002310b  mov     eax, edi
0x18002310d  test    ebx, ebx
0x18002310f  js      loc_18002324B
0x180023115  cmp     [rbp+57h+var_78.wYear], r15w
0x18002311a  jbe     short loc_18002315B
0x18002311c  lea     rdx, [rbp+57h+FileTime1]; lpFileTime
0x180023120  lea     rcx, [rbp+57h+var_78]; lpSystemTime
0x180023124  call    cs:__imp_SystemTimeToFileTime
0x18002312a  test    eax, eax
0x18002312c  jz      loc_180023239
0x180023132  lea     rdx, [rbp+57h+FileTime]; lpFileTime2
0x180023136  lea     rcx, [rbp+57h+FileTime1]; lpFileTime1
0x18002313a  call    cs:__imp_CompareFileTime
0x180023140  cmp     eax, 1
0x180023143  jnz     short loc_18002315B
  ... truncated ...
```
