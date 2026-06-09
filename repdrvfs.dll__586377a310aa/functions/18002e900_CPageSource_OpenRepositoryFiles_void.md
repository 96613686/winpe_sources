# CPageSource::OpenRepositoryFiles(void)

- ea: `0x18002e900`
- end: `0x18002ef66`
- name: `?OpenRepositoryFiles@CPageSource@@AEAAKXZ`
- size: `1638`
- prototype: `unsigned int __fastcall(CPageSource *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18002fd70`

## callees

- `0x1800216c8`
- `0x180029fbc`
- `0x18002b1b8`
- `0x18002b2d8`
- `0x18002ce08`
- `0x18002cf48`
- `0x18002e5b8`
- `0x18002e830`
- `0x18002e900`
- `0x18002ef6c`
- `0x180044420`

## import_xrefs

- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x18002e996`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x18002ea2f`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x18002ea8d`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x18002e996`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x18002ea2f`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x18002ea8d`
- `wbemcomn!?IsOffline@CWbemInstallObject@@SA_NXZ` at `0x18002eb49`
- `wbemcomn!?IsOffline@CWbemInstallObject@@SA_NXZ` at `0x18002eb49`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002e9e8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002ea56`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002eab4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002e9e8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002ea56`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002eab4`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002eb86`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002ed38`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002ed98`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002edbf`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002eb86`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002ed38`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002ed98`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002edbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ea09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eac4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ead1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eb94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ee7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ea09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eac4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ead1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eb94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ee7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ea67`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CPageSource::OpenRepositoryFiles(CPageSource *this)
{
  unsigned int v2; // r12d
  DWORD v3; // edi
  int i; // ebx
  const unsigned __int16 *v5; // rax
  signed int LastError; // eax
  HANDLE FileW; // rax
  DWORD v8; // ebx
  const WCHAR *v9; // rax
  HANDLE v10; // rax
  DWORD v11; // ebx
  const WCHAR *v12; // rax
  HANDLE v13; // rax
  DWORD v14; // ebx
  unsigned int j; // edi
  unsigned int v16; // r9d
  char IsOffline; // al
  bool v18; // r8
  signed int k; // r15d
  unsigned int v20; // eax
  HANDLE v21; // rdi
  unsigned __int64 v22; // rsi
  CPageMap *v23; // rbx
  CPageMap *v24; // rax
  unsigned __int8 v25; // bl
  CPageMap *v26; // rcx
  unsigned int ImproperShutdownSignature; // ebx
  char m; // [rsp+40h] [rbp-C0h]
  char v30[8]; // [rsp+48h] [rbp-B8h] BYREF
  BOOL (__stdcall *v31)(HANDLE); // [rsp+50h] [rbp-B0h]
  HANDLE v32; // [rsp+58h] [rbp-A8h]
  char v33[8]; // [rsp+60h] [rbp-A0h] BYREF
  BOOL (__stdcall *v34)(HANDLE); // [rsp+68h] [rbp-98h]
  HANDLE v35; // [rsp+70h] [rbp-90h]
  HANDLE v36; // [rsp+78h] [rbp-88h]
  HANDLE v37; // [rsp+80h] [rbp-80h]
  char v38[8]; // [rsp+88h] [rbp-78h] BYREF
  void (__fastcall *v39)(void **, int); // [rsp+90h] [rbp-70h]
  HANDLE *v40; // [rsp+98h] [rbp-68h]
  int v41; // [rsp+A0h] [rbp-60h]
  _BYTE *v42; // [rsp+A8h] [rbp-58h]
  _BYTE v43[96]; // [rsp+B8h] [rbp-48h] BYREF
  char v44[96]; // [rsp+118h] [rbp+18h] BYREF
  HANDLE hFile[2]; // [rsp+178h] [rbp+78h] BYREF
  HANDLE v46; // [rsp+188h] [rbp+88h]
  _BYTE v47[4]; // [rsp+190h] [rbp+90h] BYREF
  _DWORD v48[71]; // [rsp+194h] [rbp+94h]
  _BYTE v49[288]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR FileName[264]; // [rsp+3D0h] [rbp+2D0h] BYREF

  v2 = 0;
  *((_BYTE *)this + 1) = 0;
  v3 = *(_BYTE *)this != 0 ? 3 : 1;
  *(__m128i *)hFile = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v46 = hFile[0];
  v38[0] = 0;
  v39 = CloseHandleArray;
  v40 = hFile;
  v41 = 3;
  *((_DWORD *)this + 252) = 3;
  for ( i = 0; ; ++i )
  {
    if ( i >= 3 )
      goto LABEL_9;
    v5 = (const unsigned __int16 *)WString::operator unsigned short *((char *)this + 960);
    LastError = StringCchPrintfW(FileName, 0x105u, v5, (unsigned int)(i + 1));
    if ( LastError < 0 )
      goto LABEL_13;
    FileW = CreateFileW(FileName, CPageSource::m_writeBit | 0x80000000, v3, &g_SA, 3u, 0x80u, 0);
    hFile[i] = FileW;
    if ( FileW == (HANDLE)-1LL )
      break;
  }
  if ( i < 2 || GetLastError() != 2 )
    goto LABEL_12;
  *((_DWORD *)this + 252) = i;
LABEL_9:
  v8 = CPageSource::m_writeBit | 0x80000000;
  v9 = (const WCHAR *)WString::operator unsigned short *((char *)this + 944);
  v10 = CreateFileW(v9, v8, v3, &g_SA, 3u, 0x80u, 0);
  v36 = v10;
  if ( v10 == (HANDLE)-1LL )
  {
LABEL_12:
    LastError = GetLastError();
LABEL_13:
    v14 = LastError;
LABEL_49:
    ScopeGuardImpl2<void (*)(void * *,int),void * *,int>::~ScopeGuardImpl2<void (*)(void * *,int),void * *,int>(v38);
    return v14;
  }
  v30[0] = 0;
  v31 = CloseHandle;
  v32 = v10;
  v11 = CPageSource::m_writeBit | 0x80000000;
  v12 = (const WCHAR *)WString::operator unsigned short *((char *)this + 952);
  v13 = CreateFileW(v12, v11, v3, &g_SA, 3u, 0x80u, 0);
  v37 = v13;
  if ( v13 == (HANDLE)-1LL )
  {
    v14 = GetLastError();
LABEL_48:
    ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v30);
    goto LABEL_49;
  }
  v33[0] = 0;
  v34 = CloseHandle;
  v35 = v13;
  `eh vector constructor iterator'(
    v47,
    0x60u,
    3u,
    (void (*)(void *))CPageMap::`default constructor closure',
    (void (*)(void *))CPageMap::~CPageMap);
  `eh vector constructor iterator'(
    v49,
    0x60u,
    3u,
    (void (*)(void *))CPageMap::`default constructor closure',
    (void (*)(void *))CPageMap::~CPageMap);
  for ( j = 0; ; ++j )
  {
    v16 = *((_DWORD *)this + 252);
    if ( j >= v16 )
      break;
    if ( *(_BYTE *)this || (IsOffline = CWbemInstallObject::IsOffline(), v18 = 0, IsOffline) )
      v18 = 1;
    CPageMap::LoadSignature((CPageMap *)&v47[96 * j], hFile[j], v18);
    if ( !SetFilePointerEx(hFile[j], 0, 0, 0) )
    {
      v14 = GetLastError();
      `eh vector destructor iterator'(v49, 0x60u, 3u, (void (*)(void *))CPageMap::~CPageMap);
LABEL_47:
      `eh vector destructor iterator'(v47, 0x60u, 3u, (void (*)(void *))CPageMap::~CPageMap);
      ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v33);
      goto LABEL_48;
    }
  }
  for ( k = 0; k < v16; ++k )
  {
    v20 = v48[24 * ((k + 1) % v16)];
    if ( v20 >= v48[24 * k] )
    {
      if ( v20 > v48[24 * k] && v48[24 * ((k + 1) % v16) + 1] <= v48[24 * k + 1] )
      {
LABEL_26:
        if ( k != -1 )
          goto LABEL_33;
        break;
      }
    }
    else if ( v48[24 * ((k + 1) % v16) + 1] < v48[24 * k + 1] )
    {
      goto LABEL_26;
    }
  }
  if ( v48[0] != 2 )
  {
    `eh vector destructor iterator'(v49, 0x60u, 3u, (void (*)(void *))CPageMap::~CPageMap);
    `eh vector destructor iterator'(v47, 0x60u, 3u, (void (*)(void *))CPageMap::~CPageMap);
    ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v33);
    ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v30);
    v14 = 1358;
    goto LABEL_49;
  }
  k = 0;
LABEL_33:
  for ( m = 0; ; m = 1 )
  {
    if ( v2 >= *((_DWORD *)this + 252) )
      goto LABEL_50;
    v21 = hFile[k];
    v42 = v43;
    v22 = 96LL * k;
    v23 = CPageMap::CPageMap((CPageMap *)v43, (const struct CPageMap *)&v49[v22]);
    v24 = CPageMap::CPageMap((CPageMap *)v44, (const struct CPageMap *)&v47[v22]);
    v25 = CPageSource::OpenMappingFile(this, v24, v23, v21, v36, v37);
    *((_DWORD *)&g_mapValid + k) = (v25 ^ 1) + 1;
    *((_DWORD *)&g_mapWriteID + k) = v48[v22 / 4];
    if ( !SetFilePointerEx(hFile[k], 0, 0, 0) )
      goto LABEL_46;
    if ( v25 )
      break;
    ++v2;
    k = (unsigned int)(k + *((_DWORD *)this + 252) - 1) % *((_DWORD *)this + 252);
  }
  if ( k == -1 )
  {
LABEL_50:
    `eh vector destructor iterator'(v49, 0x60u, 3u, (void (*)(void *))CPageMap::~CPageMap);
    `eh vector destructor iterator'(v47, 0x60u, 3u, (void (*)(void *))CPageMap::~CPageMap);
    ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v33);
    ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v30);
    ScopeGuardImpl2<void (*)(void * *,int),void * *,int>::~ScopeGuardImpl2<void (*)(void * *,int),void * *,int>(v38);
    return 1358;
  }
  if ( m )
    CRepositoryCorruption::m_dwCorruptionType = 0;
  if ( !SetFilePointerEx(hFile[k], (LARGE_INTEGER)-4LL, 0, 2u)
    || (ImproperShutdownSignature = CPageMap::ReadImproperShutdownSignature(v26, hFile[k]),
        !SetFilePointerEx(hFile[k], 0, 0, 0)) )
  {
LABEL_46:
    v14 = GetLastError();
    `eh vector destructor iterator'(v49, 0x60u, 3u, (void (*)(void *))CPageMap::~CPageMap);
    goto LABEL_47;
  }
  if ( ImproperShutdownSignature )
    *((_BYTE *)this + 1) = 1;
  *((_DWORD *)this + 253) = k;
  *(_OWORD *)((char *)this + 968) = *(_OWORD *)hFile;
  *((_QWORD *)this + 123) = v46;
  *((_QWORD *)this + 124) = v36;
  *((_QWORD *)this + 125) = v37;
  v38[0] = 1;
  v33[0] = 1;
  v30[0] = 1;
  `eh vector destructor iterator'(v49, 0x60u, 3u, (void (*)(void *))CPageMap::~CPageMap);
  `eh vector destructor iterator'(v47, 0x60u, 3u, (void (*)(void *))CPageMap::~CPageMap);
  ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v33);
  ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v30);
  ScopeGuardImpl2<void (*)(void * *,int),void * *,int>::~ScopeGuardImpl2<void (*)(void * *,int),void * *,int>(v38);
  return 0;
}

```

## disassembly

```asm
0x18002e900  push    rbp
0x18002e902  push    rbx
0x18002e903  push    rsi
0x18002e904  push    rdi
0x18002e905  push    r12
0x18002e907  push    r13
0x18002e909  push    r14
0x18002e90b  push    r15
0x18002e90d  lea     rbp, [rsp-4F8h]
0x18002e915  sub     rsp, 5F8h
0x18002e91c  mov     rax, cs:__security_cookie
0x18002e923  xor     rax, rsp
0x18002e926  mov     [rbp+530h+var_50], rax
0x18002e92d  mov     r14, rcx
0x18002e930  xor     r12d, r12d
0x18002e933  mov     [rcx+1], r12b
0x18002e937  mov     al, [rcx]
0x18002e939  neg     al
0x18002e93b  sbb     edi, edi
0x18002e93d  and     edi, 2
0x18002e940  inc     edi
0x18002e942  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18002e94a  movups  xmmword ptr [rbp+530h+hFile], xmm0
0x18002e94e  movq    [rbp+530h+var_4A8], xmm0
0x18002e956  mov     [rbp+530h+var_5A8], r12b
0x18002e95a  lea     rax, ?CloseHandleArray@@YAXPEAPEAXH@Z; CloseHandleArray(void * *,int)
0x18002e961  mov     [rbp+530h+var_5A0], rax
0x18002e965  lea     rax, [rbp+530h+hFile]
0x18002e969  mov     [rbp+530h+var_598], rax
0x18002e96d  lea     r13d, [r12+3]
0x18002e972  mov     [rbp+530h+var_590], r13d
0x18002e976  mov     [rcx+3F0h], r13d
0x18002e97d  mov     ebx, r12d
0x18002e980  mov     r15d, 80000000h
0x18002e986  cmp     ebx, r13d
0x18002e989  jge     loc_18002EA1F
0x18002e98f  lea     rcx, [r14+3C0h]
0x18002e996  call    cs:__imp_??BWString@@QEAAPEAGXZ; WString::operator ushort *(void)
0x18002e99c  mov     r8, rax; unsigned __int16 *
0x18002e99f  lea     r9d, [rbx+1]
0x18002e9a3  mov     edx, 105h; unsigned __int64
0x18002e9a8  lea     rcx, [rbp+530h+FileName]; unsigned __int16 *
0x18002e9af  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002e9b4  test    eax, eax
0x18002e9b6  js      loc_18002EAD7
0x18002e9bc  mov     edx, cs:?m_writeBit@CPageSource@@0KA; ulong CPageSource::m_writeBit
0x18002e9c2  or      edx, r15d; dwDesiredAccess
0x18002e9c5  mov     [rsp+630h+hTemplateFile], r12; hTemplateFile
0x18002e9ca  mov     [rsp+630h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002e9d2  mov     [rsp+630h+dwCreationDisposition], r13d; dwCreationDisposition
0x18002e9d7  lea     r9, ?g_SA@@3U_SECURITY_ATTRIBUTES@@A; lpSecurityAttributes
0x18002e9de  mov     r8d, edi; dwShareMode
0x18002e9e1  lea     rcx, [rbp+530h+FileName]; lpFileName
0x18002e9e8  call    cs:__imp_CreateFileW
0x18002e9ee  movsxd  rcx, ebx
0x18002e9f1  mov     [rbp+rcx*8+530h+hFile], rax
0x18002e9f6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002e9fa  jz      short loc_18002EA00
0x18002e9fc  inc     ebx
0x18002e9fe  jmp     short loc_18002E986
0x18002ea00  cmp     ebx, 2
0x18002ea03  jl      loc_18002EAD1
0x18002ea09  call    cs:__imp_GetLastError
0x18002ea0f  cmp     eax, 2
0x18002ea12  jnz     loc_18002EAD1
0x18002ea18  mov     [r14+3F0h], ebx
0x18002ea1f  mov     ebx, cs:?m_writeBit@CPageSource@@0KA; ulong CPageSource::m_writeBit
0x18002ea25  or      ebx, r15d
0x18002ea28  lea     rcx, [r14+3B0h]
0x18002ea2f  call    cs:__imp_??BWString@@QEAAPEAGXZ; WString::operator ushort *(void)
0x18002ea35  mov     [rsp+630h+hTemplateFile], r12; hTemplateFile
0x18002ea3a  mov     [rsp+630h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002ea42  mov     [rsp+630h+dwCreationDisposition], r13d; dwCreationDisposition
0x18002ea47  lea     r9, ?g_SA@@3U_SECURITY_ATTRIBUTES@@A; lpSecurityAttributes
0x18002ea4e  mov     r8d, edi; dwShareMode
0x18002ea51  mov     edx, ebx; dwDesiredAccess
0x18002ea53  mov     rcx, rax; lpFileName
0x18002ea56  call    cs:__imp_CreateFileW
0x18002ea5c  mov     [rsp+630h+var_5B8], rax
0x18002ea61  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002ea65  jz      short loc_18002EAD1
0x18002ea67  mov     rsi, cs:__imp_CloseHandle
0x18002ea6e  mov     [rsp+630h+var_5E8], r12b
0x18002ea73  mov     [rsp+630h+var_5E0], rsi
0x18002ea78  mov     [rsp+630h+var_5D8], rax
0x18002ea7d  mov     ebx, cs:?m_writeBit@CPageSource@@0KA; ulong CPageSource::m_writeBit
0x18002ea83  or      ebx, r15d
0x18002ea86  lea     rcx, [r14+3B8h]
0x18002ea8d  call    cs:__imp_??BWString@@QEAAPEAGXZ; WString::operator ushort *(void)
0x18002ea93  mov     [rsp+630h+hTemplateFile], r12; hTemplateFile
0x18002ea98  mov     [rsp+630h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002eaa0  mov     [rsp+630h+dwCreationDisposition], r13d; dwCreationDisposition
0x18002eaa5  lea     r9, ?g_SA@@3U_SECURITY_ATTRIBUTES@@A; lpSecurityAttributes
0x18002eaac  mov     r8d, edi; dwShareMode
0x18002eaaf  mov     edx, ebx; dwDesiredAccess
0x18002eab1  mov     rcx, rax; lpFileName
0x18002eab4  call    cs:__imp_CreateFileW
0x18002eaba  mov     [rbp+530h+var_5B0], rax
0x18002eabe  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002eac2  jnz     short loc_18002EADE
0x18002eac4  call    cs:__imp_GetLastError
0x18002eaca  mov     ebx, eax
0x18002eacc  jmp     loc_18002EECD
0x18002ead1  call    cs:__imp_GetLastError
0x18002ead7  mov     ebx, eax
0x18002ead9  jmp     loc_18002EED8
0x18002eade  mov     [rsp+630h+var_5D0], r12b
0x18002eae3  mov     [rsp+630h+var_5C8], rsi
0x18002eae8  mov     [rsp+630h+var_5C0], rax
0x18002eaed  lea     rbx, ??1CPageMap@@QEAA@XZ; CPageMap::~CPageMap(void)
0x18002eaf4  mov     qword ptr [rsp+630h+dwCreationDisposition], rbx; void (*)(void *)
0x18002eaf9  lea     r9, ??_FCPageMap@@QEAAXXZ; void (*)(void *)
0x18002eb00  mov     r8, r13; unsigned __int64
0x18002eb03  mov     esi, 60h ; '`'
0x18002eb08  mov     edx, esi; unsigned __int64
0x18002eb0a  lea     rcx, [rbp+530h+var_4A0]; void *
0x18002eb11  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18002eb16  nop
0x18002eb17  mov     qword ptr [rsp+630h+dwCreationDisposition], rbx; void (*)(void *)
0x18002eb1c  lea     r9, ??_FCPageMap@@QEAAXXZ; void (*)(void *)
0x18002eb23  mov     r8, r13; unsigned __int64
0x18002eb26  mov     edx, esi; unsigned __int64
0x18002eb28  lea     rcx, [rbp+530h+var_380]; void *
0x18002eb2f  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18002eb34  nop
0x18002eb35  mov     edi, r12d
0x18002eb38  mov     r9d, [r14+3F0h]
0x18002eb3f  cmp     edi, r9d
0x18002eb42  jnb     short loc_18002EBBE
0x18002eb44  cmp     [r14], r12b
0x18002eb47  jnz     short loc_18002EB56
0x18002eb49  call    cs:__imp_?IsOffline@CWbemInstallObject@@SA_NXZ; CWbemInstallObject::IsOffline(void)
0x18002eb4f  test    al, al
0x18002eb51  mov     r8b, r12b
0x18002eb54  jz      short loc_18002EB59
0x18002eb56  mov     r8b, 1; bool
0x18002eb59  movsxd  rbx, edi
0x18002eb5c  lea     rax, [rbx+rbx*2]
0x18002eb60  shl     rax, 5
0x18002eb64  lea     rcx, [rbp+530h+var_4A0]
0x18002eb6b  add     rcx, rax; this
0x18002eb6e  mov     rdx, [rbp+rbx*8+530h+hFile]; hFile
0x18002eb73  call    ?LoadSignature@CPageMap@@QEAAKPEAX_N@Z; CPageMap::LoadSignature(void *,bool)
0x18002eb78  mov     rdx, r12; liDistanceToMove
0x18002eb7b  xor     r9d, r9d; dwMoveMethod
0x18002eb7e  xor     r8d, r8d; lpNewFilePointer
0x18002eb81  mov     rcx, [rbp+rbx*8+530h+hFile]; hFile
0x18002eb86  call    cs:__imp_SetFilePointerEx
0x18002eb8c  test    eax, eax
0x18002eb8e  jz      short loc_18002EB94
0x18002eb90  inc     edi
0x18002eb92  jmp     short loc_18002EB38
0x18002eb94  call    cs:__imp_GetLastError
0x18002eb9a  mov     ebx, eax
0x18002eb9c  lea     r9, ??1CPageMap@@QEAA@XZ; void (*)(void *)
0x18002eba3  mov     r8, r13; unsigned __int64
0x18002eba6  mov     rdx, rsi; unsigned __int64
0x18002eba9  lea     rcx, [rbp+530h+var_380]; void *
0x18002ebb0  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18002ebb5  nop
0x18002ebb6  mov     r8, r13
0x18002ebb9  jmp     loc_18002EEAB
0x18002ebbe  mov     r15d, r12d
0x18002ebc1  cmp     r15d, r9d
0x18002ebc4  jnb     short loc_18002EC0A
0x18002ebc6  movsxd  rax, r15d
0x18002ebc9  lea     r8, [rax+rax*2]
0x18002ebcd  shl     r8, 5
0x18002ebd1  xor     edx, edx
0x18002ebd3  lea     eax, [r15+1]
0x18002ebd7  div     r9d
0x18002ebda  lea     rdx, [rdx+rdx*2]
0x18002ebde  shl     rdx, 5
0x18002ebe2  mov     eax, [rbp+rdx+530h+var_49C]
0x18002ebe9  cmp     eax, [rbp+r8+530h+var_49C]
0x18002ebf1  jnb     short loc_18002EC66
0x18002ebf3  mov     eax, [rbp+r8+530h+var_498]
0x18002ebfb  cmp     [rbp+rdx+530h+var_498], eax
0x18002ec02  jnb     short loc_18002EC79
0x18002ec04  cmp     r15d, 0FFFFFFFFh
0x18002ec08  jnz     short loc_18002EC84
0x18002ec0a  cmp     [rbp+530h+var_49C], 2
0x18002ec11  jz      short loc_18002EC81
0x18002ec13  lea     r9, ??1CPageMap@@QEAA@XZ; void (*)(void *)
0x18002ec1a  mov     r8, r13; unsigned __int64
0x18002ec1d  mov     rdx, rsi; unsigned __int64
0x18002ec20  lea     rcx, [rbp+530h+var_380]; void *
0x18002ec27  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18002ec2c  nop
0x18002ec2d  lea     r9, ??1CPageMap@@QEAA@XZ; void (*)(void *)
0x18002ec34  mov     r8, r13; unsigned __int64
0x18002ec37  mov     rdx, rsi; unsigned __int64
0x18002ec3a  lea     rcx, [rbp+530h+var_4A0]; void *
0x18002ec41  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18002ec46  nop
0x18002ec47  lea     rcx, [rsp+630h+var_5D0]
0x18002ec4c  call    ??1?$ScopeGuardImpl1@P6AXPEAU_RTL_CRITICAL_SECTION@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>(void)
0x18002ec51  nop
0x18002ec52  lea     rcx, [rsp+630h+var_5E8]
0x18002ec57  call    ??1?$ScopeGuardImpl1@P6AXPEAU_RTL_CRITICAL_SECTION@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>(void)
0x18002ec5c  mov     ebx, 54Eh
0x18002ec61  jmp     loc_18002EED8
0x18002ec66  jbe     short loc_18002EC79
0x18002ec68  mov     eax, [rbp+r8+530h+var_498]
0x18002ec70  cmp     [rbp+rdx+530h+var_498], eax
0x18002ec77  jbe     short loc_18002EC04
0x18002ec79  inc     r15d
0x18002ec7c  jmp     loc_18002EBC1
0x18002ec81  mov     r15d, r12d
0x18002ec84  mov     [rsp+630h+var_5F0], r12b
0x18002ec89  cmp     r12d, [r14+3F0h]
0x18002ec90  jnb     loc_18002EEE5
0x18002ec96  movsxd  r13, r15d
0x18002ec99  mov     rdi, [rbp+r13*8+530h+hFile]
0x18002ec9e  lea     rax, [rbp+530h+var_578]
0x18002eca2  mov     [rbp+530h+var_588], rax
0x18002eca6  lea     rsi, ds:0[r13*2]
0x18002ecae  add     rsi, r13
0x18002ecb1  shl     rsi, 5
0x18002ecb5  lea     rdx, [rbp+530h+var_380]
0x18002ecbc  add     rdx, rsi; struct CPageMap *
0x18002ecbf  lea     rcx, [rbp+530h+var_578]; this
0x18002ecc3  call    ??0CPageMap@@QEAA@AEBU0@@Z; CPageMap::CPageMap(CPageMap const &)
0x18002ecc8  mov     rbx, rax
0x18002eccb  lea     rdx, [rbp+530h+var_4A0]
0x18002ecd2  add     rdx, rsi; struct CPageMap *
0x18002ecd5  lea     rcx, [rbp+530h+var_518]; this
0x18002ecd9  call    ??0CPageMap@@QEAA@AEBU0@@Z; CPageMap::CPageMap(CPageMap const &)
0x18002ecde  nop
0x18002ecdf  mov     rcx, [rbp+530h+var_5B0]
0x18002ece3  mov     qword ptr [rsp+630h+dwFlagsAndAttributes], rcx
0x18002ece8  mov     rcx, [rsp+630h+var_5B8]
0x18002eced  mov     qword ptr [rsp+630h+dwCreationDisposition], rcx
0x18002ecf2  mov     r9, rdi
0x18002ecf5  mov     r8, rbx
0x18002ecf8  mov     rdx, rax
0x18002ecfb  mov     rcx, r14
0x18002ecfe  call    ?OpenMappingFile@CPageSource@@AEAA_NUCPageMap@@0PEAX11@Z; CPageSource::OpenMappingFile(CPageMap,CPageMap,void *,void *,void *)
0x18002ed03  movzx   ebx, al
0x18002ed06  mov     eax, ebx
0x18002ed08  xor     eax, 1
0x18002ed0b  inc     eax
0x18002ed0d  lea     rdi, __ImageBase
0x18002ed14  mov     rva ?g_mapValid@@3PAW4WMIMapValidStatus@@A[rdi+r13*4], eax; WMIMapValidStatus near * g_mapValid ...
0x18002ed1c  mov     eax, [rbp+rsi+530h+var_49C]
0x18002ed23  mov     rva ?g_mapWriteID@@3PAKA[rdi+r13*4], eax; ulong near * g_mapWriteID ...
0x18002ed2b  xor     edx, edx; liDistanceToMove
0x18002ed2d  xor     r9d, r9d; dwMoveMethod
0x18002ed30  xor     r8d, r8d; lpNewFilePointer
0x18002ed33  mov     rcx, [rbp+r13*8+530h+hFile]; hFile
0x18002ed38  call    cs:__imp_SetFilePointerEx
0x18002ed3e  test    eax, eax
0x18002ed40  jz      loc_18002EE7F
0x18002ed46  test    bl, bl
0x18002ed48  jnz     short loc_18002ED6B
0x18002ed4a  mov     [rsp+630h+var_5F0], 1
0x18002ed4f  inc     r12d
0x18002ed52  mov     ecx, [r14+3F0h]
0x18002ed59  lea     eax, [rcx-1]
0x18002ed5c  add     eax, r15d
0x18002ed5f  xor     edx, edx
0x18002ed61  div     ecx
0x18002ed63  mov     r15d, edx
0x18002ed66  jmp     loc_18002EC89
0x18002ed6b  cmp     r15d, 0FFFFFFFFh
0x18002ed6f  jz      loc_18002EEE5
0x18002ed75  cmp     [rsp+630h+var_5F0], 0
0x18002ed7a  jz      short loc_18002ED86
0x18002ed7c  mov     cs:?m_dwCorruptionType@CRepositoryCorruption@@2JA, 0; long CRepositoryCorruption::m_dwCorruptionType
0x18002ed86  mov     r9d, 2; dwMoveMethod
0x18002ed8c  xor     r8d, r8d; lpNewFilePointer
0x18002ed8f  lea     rdx, [r8-4]; liDistanceToMove
0x18002ed93  mov     rcx, [rbp+r13*8+530h+hFile]; hFile
0x18002ed98  call    cs:__imp_SetFilePointerEx
0x18002ed9e  test    eax, eax
0x18002eda0  jz      loc_18002EE7F
0x18002eda6  mov     rdx, [rbp+r13*8+530h+hFile]; void *
0x18002edab  call    ?ReadImproperShutdownSignature@CPageMap@@QEAAKPEAX@Z; CPageMap::ReadImproperShutdownSignature(void *)
0x18002edb0  mov     ebx, eax
0x18002edb2  xor     edx, edx; liDistanceToMove
0x18002edb4  xor     r9d, r9d; dwMoveMethod
0x18002edb7  xor     r8d, r8d; lpNewFilePointer
0x18002edba  mov     rcx, [rbp+r13*8+530h+hFile]; hFile
0x18002edbf  call    cs:__imp_SetFilePointerEx
0x18002edc5  test    eax, eax
0x18002edc7  jz      loc_18002EE7F
0x18002edcd  test    ebx, ebx
0x18002edcf  jz      short loc_18002EDD6
0x18002edd1  mov     byte ptr [r14+1], 1
0x18002edd6  mov     [r14+3F4h], r15d
0x18002eddd  movups  xmm0, xmmword ptr [rbp+530h+hFile]
0x18002ede1  movups  xmmword ptr [r14+3C8h], xmm0
0x18002ede9  movsd   xmm1, [rbp+530h+var_4A8]
0x18002edf1  movsd   qword ptr [r14+3D8h], xmm1
0x18002edfa  mov     rax, [rsp+630h+var_5B8]
0x18002edff  mov     [r14+3E0h], rax
0x18002ee06  mov     rax, [rbp+530h+var_5B0]
0x18002ee0a  mov     [r14+3E8h], rax
0x18002ee11  mov     [rbp+530h+var_5A8], 1
0x18002ee15  mov     [rsp+630h+var_5D0], 1
  ... truncated ...
```
