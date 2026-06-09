# CMDCOM::ComMDBackupD(ulong,char *,ulong,ulong,int,char *)

- ea: `0x180015e30`
- end: `0x18001628e`
- name: `?ComMDBackupD@CMDCOM@@QEAAJKPEADKKH0@Z`
- size: `1118`
- prototype: `__int64 __fastcall(CMDCOM *this, unsigned int, char *, unsigned int, unsigned int, int, char *)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180015e00`
- `0x1800162a0`
- `0x1800162d0`

## callees

- `0x1800089c8`
- `0x180009bd0`
- `0x180015e30`
- `0x18001b020`
- `0x18001cca8`
- `0x18001f548`
- `0x18001f638`
- `0x180023548`
- `0x18003099a`
- `0x1800309d0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800160aa`
- `ole32!CoTaskMemFree` at `0x1800160aa`
- `KERNEL32!SetFileTime` at `0x1800161ce`
- `KERNEL32!SetFileTime` at `0x1800161ce`
- `KERNEL32!CreateFileA` at `0x18001619c`
- `KERNEL32!CreateFileA` at `0x18001619c`
- `KERNEL32!CopyFileA` at `0x180016112`
- `KERNEL32!CopyFileA` at `0x180016143`
- `KERNEL32!CopyFileA` at `0x180016112`
- `KERNEL32!CopyFileA` at `0x180016143`
- `KERNEL32!OpenFile` at `0x180015f2c`
- `KERNEL32!OpenFile` at `0x180015f4d`
- `KERNEL32!OpenFile` at `0x180015f2c`
- `KERNEL32!OpenFile` at `0x180015f4d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800161b9`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800161b9`
- `KERNEL32!CloseHandle` at `0x1800161d7`
- `KERNEL32!CloseHandle` at `0x1800161d7`
- `KERNEL32!WaitForSingleObject` at `0x180015f6f`
- `KERNEL32!WaitForSingleObject` at `0x180015f6f`
- `KERNEL32!ReleaseSemaphore` at `0x180016229`
- `KERNEL32!ReleaseSemaphore` at `0x180016229`
- `KERNEL32!GetLastError` at `0x18001614f`
- `KERNEL32!GetLastError` at `0x18001614f`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x180016103`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x180016134`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x1800161ee`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x180016103`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x180016134`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x1800161ee`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x180015e95`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x180015e9f`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x180015e95`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x180015e9f`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x180016251`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x18001625c`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x180016251`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x18001625c`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x180015f17`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x180015f3d`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x18001605e`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x18001606e`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x1800160f3`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x180016124`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x180016173`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x1800161fe`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x180015f17`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x180015f3d`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x18001605e`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x18001606e`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x1800160f3`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x180016124`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x180016173`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x1800161fe`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDBackupD(
        CMDCOM *this,
        unsigned int a2,
        char *a3,
        unsigned int a4,
        unsigned int a5,
        int a6,
        char *a7)
{
  int v9; // ebx
  char v10; // r13
  signed int BackupFileName; // edi
  int v12; // r14d
  const CHAR *Str; // rax
  const CHAR *v14; // rax
  int v15; // r12d
  struct IIS_CRYPTO_STORAGE *v16; // rsi
  struct IIS_CRYPTO_STORAGE *v17; // rax
  int inited; // eax
  struct _IIS_CRYPTO_BLOB *v19; // r14
  unsigned __int16 *v20; // rbx
  unsigned __int16 *v21; // rax
  int v22; // r14d
  const CHAR *v23; // rbx
  const CHAR *v24; // rax
  const CHAR *v25; // rbx
  const CHAR *v26; // rax
  signed int LastError; // eax
  const CHAR *v28; // rax
  HANDLE FileA; // rbx
  unsigned __int16 *v30; // rdi
  char *v31; // rbx
  char *v32; // rax
  unsigned int v33; // edx
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v36; // [rsp+48h] [rbp-B8h]
  int v37; // [rsp+4Ch] [rbp-B4h]
  unsigned __int16 *v38; // [rsp+50h] [rbp-B0h]
  _BYTE v39[128]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v40[128]; // [rsp+E0h] [rbp-20h] BYREF
  _OFSTRUCT ReOpenBuff; // [rsp+160h] [rbp+60h] BYREF

  v38 = (unsigned __int16 *)a3;
  v36 = a2;
  pv = 0;
  memset_0(&ReOpenBuff, 0, sizeof(ReOpenBuff));
  STRAU::STRAU((STRAU *)v39);
  STRAU::STRAU((STRAU *)v40);
  if ( !g_dwInitialized )
  {
    v9 = -2146646016;
LABEL_45:
    BackupFileName = v9;
    goto LABEL_46;
  }
  if ( (a5 & 6) == 4 )
  {
    v9 = -2147024809;
    goto LABEL_45;
  }
  v10 = 2;
  if ( a5 )
    v10 = a5;
  BackupFileName = CreateBackupFileName(a3, a4, a6, (struct STRAU *)v39, (struct STRAU *)v40);
  if ( BackupFileName >= 0 )
  {
    v12 = v10 & 1;
    v37 = v12;
    if ( (v10 & 1) == 0 )
    {
      Str = STRAU::QueryStr((STRAU *)v39, 0);
      if ( OpenFile(Str, &ReOpenBuff, 0x4000u) != -1
        || (v14 = STRAU::QueryStr((STRAU *)v40, 0), OpenFile(v14, &ReOpenBuff, 0x4000u) != -1) )
      {
        BackupFileName = -2147024816;
        goto LABEL_46;
      }
    }
    v15 = 0;
    WaitForSingleObject(g_hReadSaveSemaphore, 0xFFFFFFFF);
    if ( (v10 & 2) == 0 )
    {
      v16 = 0;
      if ( !a7 )
        goto LABEL_30;
    }
    v17 = (struct IIS_CRYPTO_STORAGE *)operator new(0x30u);
    v16 = v17;
    if ( a7 )
    {
      if ( v17 )
      {
        *((_QWORD *)v17 + 1) = 0;
        *((_DWORD *)v17 + 4) = 0;
        *((_QWORD *)v17 + 3) = 0;
        *((_QWORD *)v17 + 4) = 0;
        *((_QWORD *)v17 + 5) = 0;
        *(_QWORD *)v17 = &IIS_CRYPTO_STORAGE2::`vftable';
        inited = InitStorageAndSessionKey2(a7, v17, (struct _IIS_CRYPTO_BLOB **)&pv, 1);
        goto LABEL_18;
      }
    }
    else if ( v17 )
    {
      *((_QWORD *)v17 + 1) = 0;
      *((_DWORD *)v17 + 4) = 0;
      *((_QWORD *)v17 + 3) = 0;
      *((_QWORD *)v17 + 4) = 0;
      *(_QWORD *)v17 = &IIS_CRYPTO_STORAGE::`vftable';
      *((_QWORD *)v17 + 5) = 0;
      inited = InitStorageAndSessionKey(v17, (struct _IIS_CRYPTO_BLOB **)&pv);
LABEL_18:
      BackupFileName = inited;
      if ( inited >= 0 )
      {
        v19 = (struct _IIS_CRYPTO_BLOB *)pv;
        if ( g_dwInitialized )
        {
          if ( a7 )
          {
            v20 = (unsigned __int16 *)STRAU::QueryStr((STRAU *)v40, 1);
            v21 = (unsigned __int16 *)STRAU::QueryStr((STRAU *)v39, 1);
            BackupFileName = SaveAllData(v36, v16, v19, v21, v20, v36, 1, 0);
          }
          else
          {
            BackupFileName = SaveAllData(v36, v16, (struct _IIS_CRYPTO_BLOB *)pv, 0, 0, v36, 1, 0);
          }
        }
        else
        {
          BackupFileName = -2146646016;
        }
        *(_BYTE *)v19 = 88;
        CoTaskMemFree(v19);
        if ( BackupFileName >= 0 )
        {
LABEL_28:
          if ( a7 )
          {
LABEL_34:
            if ( BackupFileName >= 0 )
            {
              v28 = STRAU::QueryStr((STRAU *)v39, 0);
              FileA = CreateFileA(v28, 0xC0000000, 0, 0, 3u, 0x80u, 0);
              if ( FileA != (HANDLE)-1LL )
              {
                pv = 0;
                GetSystemTimeAsFileTime((LPFILETIME)&pv);
                SetFileTime(FileA, 0, (const FILETIME *)&pv, (const FILETIME *)&pv);
                CloseHandle(FileA);
              }
              v30 = v38;
              if ( v38 )
              {
                v31 = STR::QueryStr(g_strRealFileName);
                v32 = STRAU::QueryStr((STRAU *)v39, 0);
                BackupFileName = BackupCertificates(v30, v32, v31);
              }
              else
              {
                BackupFileName = -2147024809;
              }
            }
            goto LABEL_40;
          }
          v12 = v37;
LABEL_30:
          v22 = v12 ^ 1;
          v23 = STRAU::QueryStr((STRAU *)v39, 0);
          v24 = STR::QueryStr(g_strRealFileName);
          if ( !CopyFileA(v24, v23, v22)
            || (v25 = STRAU::QueryStr((STRAU *)v40, 0),
                v26 = STR::QueryStr(g_strSchemaFileName),
                !CopyFileA(v26, v25, v22)) )
          {
            LastError = GetLastError();
            BackupFileName = LastError;
            if ( LastError > 0 )
              BackupFileName = (unsigned __int16)LastError | 0x80070000;
          }
          goto LABEL_34;
        }
      }
LABEL_27:
      v15 = 837641;
      if ( (v10 & 4) == 0 )
      {
LABEL_40:
        ReleaseSemaphore(g_hReadSaveSemaphore, 1, 0);
        v9 = v15;
        if ( BackupFileName )
          v9 = BackupFileName;
        if ( v16 )
          IIS_CRYPTO_STORAGE::`scalar deleting destructor'(v16, v33);
        goto LABEL_45;
      }
      goto LABEL_28;
    }
    v16 = 0;
    BackupFileName = -2147024882;
    goto LABEL_27;
  }
LABEL_46:
  STRAU::~STRAU((STRAU *)v40);
  STRAU::~STRAU((STRAU *)v39);
  return (unsigned int)BackupFileName;
}

```

## disassembly

```asm
0x180015e30  mov     [rsp-8+arg_0], rbx
0x180015e35  push    rbp
0x180015e36  push    rsi
0x180015e37  push    rdi
0x180015e38  push    r12
0x180015e3a  push    r13
0x180015e3c  push    r14
0x180015e3e  push    r15
0x180015e40  lea     rbp, [rsp-100h]
0x180015e48  sub     rsp, 200h
0x180015e4f  mov     rax, cs:__security_cookie
0x180015e56  xor     rax, rsp
0x180015e59  mov     [rbp+130h+var_40], rax
0x180015e60  mov     r15, [rbp+130h+arg_30]
0x180015e67  lea     rcx, [rbp+130h+ReOpenBuff]; void *
0x180015e6b  mov     rdi, r8
0x180015e6e  mov     [rsp+230h+var_1E0], r8
0x180015e73  mov     [rsp+230h+var_1E8], edx
0x180015e77  mov     r8d, 88h; Size
0x180015e7d  xor     edx, edx; Val
0x180015e7f  mov     [rsp+230h+pv], 0
0x180015e88  mov     ebx, r9d
0x180015e8b  call    memset_0
0x180015e90  lea     rcx, [rsp+230h+var_1D0]
0x180015e95  call    cs:__imp_??0STRAU@@QEAA@XZ; STRAU::STRAU(void)
0x180015e9b  lea     rcx, [rbp+130h+var_150]
0x180015e9f  call    cs:__imp_??0STRAU@@QEAA@XZ; STRAU::STRAU(void)
0x180015ea5  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x180015eab  test    eax, eax
0x180015ead  jnz     short loc_180015EB9
0x180015eaf  mov     ebx, 800CC800h
0x180015eb4  jmp     loc_18001624B
0x180015eb9  mov     ecx, [rbp+130h+arg_20]
0x180015ebf  mov     eax, ecx
0x180015ec1  and     al, 6
0x180015ec3  cmp     al, 4
0x180015ec5  jz      loc_180016246
0x180015ecb  mov     r8d, [rbp+130h+arg_28]; int
0x180015ed2  lea     rax, [rbp+130h+var_150]
0x180015ed6  test    ecx, ecx
0x180015ed8  mov     qword ptr [rsp+230h+dwCreationDisposition], rax; struct STRAU *
0x180015edd  mov     r13d, 2
0x180015ee3  lea     r9, [rsp+230h+var_1D0]; struct STRAU *
0x180015ee8  cmovnz  r13d, ecx
0x180015eec  mov     edx, ebx; unsigned int
0x180015eee  mov     rcx, rdi; char *
0x180015ef1  call    ?CreateBackupFileName@@YAJPEADKHPEAVSTRAU@@1@Z; CreateBackupFileName(char *,ulong,int,STRAU *,STRAU *)
0x180015ef6  xor     ebx, ebx
0x180015ef8  mov     edi, eax
0x180015efa  test    eax, eax
0x180015efc  js      loc_18001624D
0x180015f02  mov     r14d, r13d
0x180015f05  and     r14d, 1
0x180015f09  mov     [rsp+230h+var_1E4], r14d
0x180015f0e  jnz     short loc_180015F62
0x180015f10  xor     edx, edx
0x180015f12  lea     rcx, [rsp+230h+var_1D0]
0x180015f17  call    cs:__imp_?QueryStr@STRAU@@QEAAPEADH@Z; STRAU::QueryStr(int)
0x180015f1d  mov     esi, 4000h
0x180015f22  lea     rdx, [rbp+130h+ReOpenBuff]; lpReOpenBuff
0x180015f26  mov     rcx, rax; lpFileName
0x180015f29  mov     r8d, esi; uStyle
0x180015f2c  call    cs:__imp_OpenFile
0x180015f32  cmp     eax, 0FFFFFFFFh
0x180015f35  jnz     short loc_180015F58
0x180015f37  xor     edx, edx
0x180015f39  lea     rcx, [rbp+130h+var_150]
0x180015f3d  call    cs:__imp_?QueryStr@STRAU@@QEAAPEADH@Z; STRAU::QueryStr(int)
0x180015f43  mov     r8d, esi; uStyle
0x180015f46  lea     rdx, [rbp+130h+ReOpenBuff]; lpReOpenBuff
0x180015f4a  mov     rcx, rax; lpFileName
0x180015f4d  call    cs:__imp_OpenFile
0x180015f53  cmp     eax, 0FFFFFFFFh
0x180015f56  jz      short loc_180015F62
0x180015f58  mov     edi, 80070050h
0x180015f5d  jmp     loc_18001624D
0x180015f62  mov     rcx, cs:?g_hReadSaveSemaphore@@3PEAXEA; hHandle
0x180015f69  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180015f6c  mov     r12d, ebx
0x180015f6f  call    cs:__imp_WaitForSingleObject
0x180015f75  test    r13b, 2
0x180015f79  jnz     short loc_180015F87
0x180015f7b  mov     rsi, rbx
0x180015f7e  test    r15, r15
0x180015f81  jz      loc_1800160E8
0x180015f87  mov     ecx, 30h ; '0'; Size
0x180015f8c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015f91  mov     rsi, rax
0x180015f94  test    r15, r15
0x180015f97  jnz     short loc_180015FCE
0x180015f99  test    rax, rax
0x180015f9c  jz      loc_1800160B6
0x180015fa2  mov     [rax+8], rbx
0x180015fa6  lea     rdx, [rsp+230h+pv]; struct _IIS_CRYPTO_BLOB **
0x180015fab  mov     [rax+10h], ebx
0x180015fae  mov     rcx, rsi; this
0x180015fb1  mov     [rax+18h], rbx
0x180015fb5  mov     [rax+20h], rbx
0x180015fb9  lea     rax, ??_7IIS_CRYPTO_STORAGE@@6B@; const IIS_CRYPTO_STORAGE::`vftable'
0x180015fc0  mov     [rsi], rax
0x180015fc3  mov     [rsi+28h], rbx
0x180015fc7  call    ?InitStorageAndSessionKey@@YAJPEAVIIS_CRYPTO_STORAGE@@PEAPEFAU_IIS_CRYPTO_BLOB@@@Z; InitStorageAndSessionKey(IIS_CRYPTO_STORAGE *,_IIS_CRYPTO_BLOB * *)
0x180015fcc  jmp     short loc_18001600A
0x180015fce  test    rax, rax
0x180015fd1  jz      loc_1800160B6
0x180015fd7  mov     [rax+8], rbx
0x180015fdb  lea     r8, [rsp+230h+pv]; struct _IIS_CRYPTO_BLOB **
0x180015fe0  mov     [rax+10h], ebx
0x180015fe3  mov     r9d, 1; int
0x180015fe9  mov     [rax+18h], rbx
0x180015fed  mov     rdx, rsi; this
0x180015ff0  mov     [rax+20h], rbx
0x180015ff4  mov     rcx, r15; char *
0x180015ff7  mov     [rax+28h], rbx
0x180015ffb  lea     rax, ??_7IIS_CRYPTO_STORAGE2@@6B@; const IIS_CRYPTO_STORAGE2::`vftable'
0x180016002  mov     [rsi], rax
0x180016005  call    ?InitStorageAndSessionKey2@@YAJPEADPEAVIIS_CRYPTO_STORAGE@@PEAPEFAU_IIS_CRYPTO_BLOB@@H@Z; InitStorageAndSessionKey2(char *,IIS_CRYPTO_STORAGE *,_IIS_CRYPTO_BLOB * *,int)
0x18001600a  mov     edi, eax
0x18001600c  test    eax, eax
0x18001600e  js      loc_1800160C2
0x180016014  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x18001601a  mov     r14, [rsp+230h+pv]
0x18001601f  test    eax, eax
0x180016021  jz      short loc_18001609E
0x180016023  test    r15, r15
0x180016026  jnz     short loc_180016053
0x180016028  mov     ecx, [rsp+230h+var_1E8]; int
0x18001602c  xor     r9d, r9d; unsigned __int16 *
0x18001602f  mov     [rsp+230h+var_1F8], ebx; int
0x180016033  mov     r8, r14; struct _IIS_CRYPTO_BLOB *
0x180016036  mov     dword ptr [rsp+230h+hTemplateFile], 1; int
0x18001603e  mov     rdx, rsi; struct IIS_CRYPTO_STORAGE *
0x180016041  mov     [rsp+230h+dwFlagsAndAttributes], ecx; unsigned int
0x180016045  mov     qword ptr [rsp+230h+dwCreationDisposition], rbx; unsigned __int16 *
0x18001604a  call    ?SaveAllData@@YAJHPEAVIIS_CRYPTO_STORAGE@@PEFAU_IIS_CRYPTO_BLOB@@PEAG2KHH@Z; SaveAllData(int,IIS_CRYPTO_STORAGE *,_IIS_CRYPTO_BLOB *,ushort *,ushort *,ulong,int,int)
0x18001604f  mov     edi, eax
0x180016051  jmp     short loc_1800160A3
0x180016053  mov     edi, 1
0x180016058  lea     rcx, [rbp+130h+var_150]
0x18001605c  mov     edx, edi
0x18001605e  call    cs:__imp_?QueryStr@STRAU@@QEAAPEADH@Z; STRAU::QueryStr(int)
0x180016064  mov     edx, edi
0x180016066  lea     rcx, [rsp+230h+var_1D0]
0x18001606b  mov     rbx, rax
0x18001606e  call    cs:__imp_?QueryStr@STRAU@@QEAAPEADH@Z; STRAU::QueryStr(int)
0x180016074  mov     ecx, [rsp+230h+var_1E8]; int
0x180016078  mov     r8, r14; struct _IIS_CRYPTO_BLOB *
0x18001607b  mov     [rsp+230h+var_1F8], r12d; int
0x180016080  mov     r9, rax; unsigned __int16 *
0x180016083  mov     dword ptr [rsp+230h+hTemplateFile], edi; int
0x180016087  mov     rdx, rsi; struct IIS_CRYPTO_STORAGE *
0x18001608a  mov     [rsp+230h+dwFlagsAndAttributes], ecx; unsigned int
0x18001608e  mov     qword ptr [rsp+230h+dwCreationDisposition], rbx; unsigned __int16 *
0x180016093  call    ?SaveAllData@@YAJHPEAVIIS_CRYPTO_STORAGE@@PEFAU_IIS_CRYPTO_BLOB@@PEAG2KHH@Z; SaveAllData(int,IIS_CRYPTO_STORAGE *,_IIS_CRYPTO_BLOB *,ushort *,ushort *,ulong,int,int)
0x180016098  mov     edi, eax
0x18001609a  xor     ebx, ebx
0x18001609c  jmp     short loc_1800160A3
0x18001609e  mov     edi, 800CC800h
0x1800160a3  mov     rcx, r14; pv
0x1800160a6  mov     byte ptr [r14], 58h ; 'X'
0x1800160aa  call    cs:__imp_CoTaskMemFree
0x1800160b0  test    edi, edi
0x1800160b2  jns     short loc_1800160DA
0x1800160b4  jmp     short loc_1800160BE
0x1800160b6  mov     rsi, rbx
0x1800160b9  mov     edi, 8007000Eh
0x1800160be  test    edi, edi
0x1800160c0  jns     short loc_1800160D4
0x1800160c2  mov     r12d, 0CC809h
0x1800160c8  test    r13b, 4
0x1800160cc  jz      loc_18001621B
0x1800160d2  jmp     short loc_1800160DA
0x1800160d4  mov     r12d, 0CC809h
0x1800160da  test    r15, r15
0x1800160dd  jnz     loc_180016164
0x1800160e3  mov     r14d, [rsp+230h+var_1E4]
0x1800160e8  xor     edx, edx
0x1800160ea  lea     rcx, [rsp+230h+var_1D0]
0x1800160ef  xor     r14d, 1
0x1800160f3  call    cs:__imp_?QueryStr@STRAU@@QEAAPEADH@Z; STRAU::QueryStr(int)
0x1800160f9  mov     rcx, cs:?g_strRealFileName@@3PEAVSTR@@EA; STR * g_strRealFileName
0x180016100  mov     rbx, rax
0x180016103  call    cs:__imp_?QueryStr@STR@@QEBAPEADXZ; STR::QueryStr(void)
0x180016109  mov     r8d, r14d; bFailIfExists
0x18001610c  mov     rdx, rbx; lpNewFileName
0x18001610f  mov     rcx, rax; lpExistingFileName
0x180016112  call    cs:__imp_CopyFileA
0x180016118  xor     ebx, ebx
0x18001611a  test    eax, eax
0x18001611c  jz      short loc_18001614F
0x18001611e  xor     edx, edx
0x180016120  lea     rcx, [rbp+130h+var_150]
0x180016124  call    cs:__imp_?QueryStr@STRAU@@QEAAPEADH@Z; STRAU::QueryStr(int)
0x18001612a  mov     rcx, cs:?g_strSchemaFileName@@3PEAVSTR@@EA; STR * g_strSchemaFileName
0x180016131  mov     rbx, rax
0x180016134  call    cs:__imp_?QueryStr@STR@@QEBAPEADXZ; STR::QueryStr(void)
0x18001613a  mov     r8d, r14d; bFailIfExists
0x18001613d  mov     rdx, rbx; lpNewFileName
0x180016140  mov     rcx, rax; lpExistingFileName
0x180016143  call    cs:__imp_CopyFileA
0x180016149  xor     ebx, ebx
0x18001614b  test    eax, eax
0x18001614d  jnz     short loc_180016164
0x18001614f  call    cs:__imp_GetLastError
0x180016155  mov     edi, eax
0x180016157  test    eax, eax
0x180016159  jle     short loc_180016164
0x18001615b  movzx   edi, ax
0x18001615e  or      edi, 80070000h
0x180016164  test    edi, edi
0x180016166  js      loc_18001621B
0x18001616c  xor     edx, edx
0x18001616e  lea     rcx, [rsp+230h+var_1D0]
0x180016173  call    cs:__imp_?QueryStr@STRAU@@QEAAPEADH@Z; STRAU::QueryStr(int)
0x180016179  mov     [rsp+230h+hTemplateFile], rbx; hTemplateFile
0x18001617e  xor     r9d, r9d; lpSecurityAttributes
0x180016181  mov     rcx, rax; lpFileName
0x180016184  mov     [rsp+230h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001618c  xor     r8d, r8d; dwShareMode
0x18001618f  mov     [rsp+230h+dwCreationDisposition], 3; dwCreationDisposition
0x180016197  mov     edx, 0C0000000h; dwDesiredAccess
0x18001619c  call    cs:__imp_CreateFileA
0x1800161a2  mov     rbx, rax
0x1800161a5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800161a9  jz      short loc_1800161DD
0x1800161ab  lea     rcx, [rsp+230h+pv]; lpSystemTimeAsFileTime
0x1800161b0  mov     [rsp+230h+pv], 0
0x1800161b9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800161bf  lea     r9, [rsp+230h+pv]; lpLastWriteTime
0x1800161c4  xor     edx, edx; lpCreationTime
0x1800161c6  lea     r8, [rsp+230h+pv]; lpLastAccessTime
0x1800161cb  mov     rcx, rbx; hFile
0x1800161ce  call    cs:__imp_SetFileTime
0x1800161d4  mov     rcx, rbx; hObject
0x1800161d7  call    cs:__imp_CloseHandle
0x1800161dd  mov     rdi, [rsp+230h+var_1E0]
0x1800161e2  test    rdi, rdi
0x1800161e5  jz      short loc_180016216
0x1800161e7  mov     rcx, cs:?g_strRealFileName@@3PEAVSTR@@EA; STR * g_strRealFileName
0x1800161ee  call    cs:__imp_?QueryStr@STR@@QEBAPEADXZ; STR::QueryStr(void)
0x1800161f4  xor     edx, edx
0x1800161f6  lea     rcx, [rsp+230h+var_1D0]
0x1800161fb  mov     rbx, rax
0x1800161fe  call    cs:__imp_?QueryStr@STRAU@@QEAAPEADH@Z; STRAU::QueryStr(int)
0x180016204  mov     r8, rbx; char *
0x180016207  mov     rcx, rdi; unsigned __int16 *
0x18001620a  mov     rdx, rax; char *
0x18001620d  call    ?BackupCertificates@@YAJPEBGPEAD1@Z; BackupCertificates(ushort const *,char *,char *)
0x180016212  mov     edi, eax
0x180016214  jmp     short loc_18001621B
0x180016216  mov     edi, 80070057h
0x18001621b  mov     rcx, cs:?g_hReadSaveSemaphore@@3PEAXEA; hSemaphore
0x180016222  xor     r8d, r8d; lpPreviousCount
0x180016225  lea     edx, [r8+1]; lReleaseCount
0x180016229  call    cs:__imp_ReleaseSemaphore
0x18001622f  test    edi, edi
0x180016231  mov     ebx, r12d
0x180016234  cmovnz  ebx, edi
0x180016237  test    rsi, rsi
0x18001623a  jz      short loc_18001624B
0x18001623c  mov     rcx, rsi; this
0x18001623f  call    ??_GIIS_CRYPTO_STORAGE@@QEAAPEAXI@Z; IIS_CRYPTO_STORAGE::`scalar deleting destructor'(uint)
0x180016244  jmp     short loc_18001624B
0x180016246  mov     ebx, 80070057h
0x18001624b  mov     edi, ebx
0x18001624d  lea     rcx, [rbp+130h+var_150]
0x180016251  call    cs:__imp_??1STRAU@@QEAA@XZ; STRAU::~STRAU(void)
0x180016257  lea     rcx, [rsp+230h+var_1D0]
0x18001625c  call    cs:__imp_??1STRAU@@QEAA@XZ; STRAU::~STRAU(void)
0x180016262  mov     eax, edi
0x180016264  mov     rcx, [rbp+130h+var_40]
0x18001626b  xor     rcx, rsp; StackCookie
0x18001626e  call    __security_check_cookie
0x180016273  mov     rbx, [rsp+230h+arg_0]
0x18001627b  add     rsp, 200h
0x180016282  pop     r15
0x180016284  pop     r14
0x180016286  pop     r13
0x180016288  pop     r12
0x18001628a  pop     rdi
0x18001628b  pop     rsi
0x18001628c  pop     rbp
0x18001628d  retn
```
