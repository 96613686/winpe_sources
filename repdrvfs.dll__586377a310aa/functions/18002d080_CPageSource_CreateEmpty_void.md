# CPageSource::CreateEmpty(void)

- ea: `0x18002d080`
- end: `0x18002d4eb`
- name: `?CreateEmpty@CPageSource@@AEAAKXZ`
- size: `1131`
- prototype: `__int64 __fastcall(CPageSource *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002fd70`

## callees

- `0x1800216c8`
- `0x180029fbc`
- `0x18002cab8`
- `0x18002ce70`
- `0x18002cf00`
- `0x18002cf48`
- `0x18002cf70`
- `0x18002d080`
- `0x18002fb0c`
- `0x180037974`
- `0x18003c16c`
- `0x180044420`

## import_xrefs

- `wbemcomn!??0WString@@QEAA@AEBV0@@Z` at `0x18002d0fc`
- `wbemcomn!??0WString@@QEAA@AEBV0@@Z` at `0x18002d111`
- `wbemcomn!??0WString@@QEAA@AEBV0@@Z` at `0x18002d126`
- `wbemcomn!??0WString@@QEAA@AEBV0@@Z` at `0x18002d14a`
- `wbemcomn!??0WString@@QEAA@AEBV0@@Z` at `0x18002d248`
- `wbemcomn!??0WString@@QEAA@AEBV0@@Z` at `0x18002d2e8`
- `wbemcomn!??0WString@@QEAA@AEBV0@@Z` at `0x18002d0fc`
- `wbemcomn!??0WString@@QEAA@AEBV0@@Z` at `0x18002d111`
- `wbemcomn!??0WString@@QEAA@AEBV0@@Z` at `0x18002d126`
- `wbemcomn!??0WString@@QEAA@AEBV0@@Z` at `0x18002d14a`
- `wbemcomn!??0WString@@QEAA@AEBV0@@Z` at `0x18002d248`
- `wbemcomn!??0WString@@QEAA@AEBV0@@Z` at `0x18002d2e8`
- `wbemcomn!??1WString@@QEAA@XZ` at `0x18002d154`
- `wbemcomn!??1WString@@QEAA@XZ` at `0x18002d15e`
- `wbemcomn!??1WString@@QEAA@XZ` at `0x18002d168`
- `wbemcomn!??1WString@@QEAA@XZ` at `0x18002d154`
- `wbemcomn!??1WString@@QEAA@XZ` at `0x18002d15e`
- `wbemcomn!??1WString@@QEAA@XZ` at `0x18002d168`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x18002d182`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x18002d201`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x18002d282`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x18002d182`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x18002d201`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x18002d282`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002d1cf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002d231`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002d2b0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002d1cf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002d231`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002d2b0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002d251`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002d2f1`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18002d3b7`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18002d3b7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002d3a3`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002d3a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d1ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d2bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d3c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d1ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d2bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d3c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d262`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPageSource::CreateEmpty(CPageSource *this)
{
  char *v2; // r15
  const struct WString *v3; // rsi
  const struct WString *v4; // rdi
  const struct WString *v5; // rbx
  int i; // ebx
  const unsigned __int16 *v7; // rax
  signed int LastError; // eax
  HANDLE FileW; // rax
  DWORD v10; // ebx
  const WCHAR *v11; // rax
  HANDLE v12; // rbx
  WString *v13; // rax
  const struct WString *v14; // rsi
  const WCHAR *v15; // rax
  HANDLE v16; // r14
  WString *v17; // rax
  int j; // ebx
  unsigned int v19; // esi
  HANDLE v20; // rdi
  DWORD v21; // edi
  _BYTE v23[8]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+48h] [rbp-B8h] BYREF
  int Buffer; // [rsp+50h] [rbp-B0h] BYREF
  const struct WString *v26; // [rsp+58h] [rbp-A8h]
  _BYTE v27[8]; // [rsp+60h] [rbp-A0h] BYREF
  BOOL (__stdcall *v28)(HANDLE); // [rsp+68h] [rbp-98h]
  HANDLE v29; // [rsp+70h] [rbp-90h]
  _BYTE v30[8]; // [rsp+78h] [rbp-88h] BYREF
  BOOL (__stdcall *v31)(HANDLE); // [rsp+80h] [rbp-80h]
  HANDLE v32; // [rsp+88h] [rbp-78h]
  _BYTE v33[24]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v34[24]; // [rsp+A8h] [rbp-58h] BYREF
  char v35[8]; // [rsp+C0h] [rbp-40h] BYREF
  void (__fastcall *v36)(const unsigned __int16 *); // [rsp+C8h] [rbp-38h]
  _BYTE v37[8]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v38[8]; // [rsp+D8h] [rbp-28h] BYREF
  void (__fastcall *v39)(void **, int); // [rsp+E0h] [rbp-20h]
  HANDLE *v40; // [rsp+E8h] [rbp-18h]
  int v41; // [rsp+F0h] [rbp-10h]
  const struct WString *v42; // [rsp+F8h] [rbp-8h]
  const struct WString *v43; // [rsp+100h] [rbp+0h]
  _BYTE v44[96]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v45[96]; // [rsp+170h] [rbp+70h] BYREF
  HANDLE hFile[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  HANDLE v47; // [rsp+1E0h] [rbp+E0h]
  WCHAR FileName[264]; // [rsp+1F0h] [rbp+F0h] BYREF

  *(__m128i *)hFile = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v47 = hFile[0];
  v38[0] = 0;
  v39 = CloseHandleArray;
  v40 = hFile;
  v41 = 3;
  v2 = (char *)this + 960;
  v3 = WString::WString((WString *)&Buffer, (CPageSource *)((char *)this + 960));
  v42 = v3;
  v4 = WString::WString((WString *)&NumberOfBytesWritten, v3);
  v43 = v4;
  v5 = WString::WString((WString *)v23, v4);
  v26 = v5;
  v35[0] = 0;
  v36 = DeleteMaps;
  WString::WString((WString *)v37, v5);
  WString::~WString(v5);
  WString::~WString(v4);
  WString::~WString(v3);
  for ( i = 0; i < 3; ++i )
  {
    v7 = (const unsigned __int16 *)WString::operator unsigned short *(v2);
    LastError = StringCchPrintfW(FileName, 0x105u, v7, (unsigned int)(i + 1));
    if ( LastError < 0 )
      goto LABEL_7;
    FileW = CreateFileW(FileName, 0x40000000u, 1u, &g_SA, 2u, 0x80000080, 0);
    hFile[i] = FileW;
    if ( FileW == (HANDLE)-1LL )
      goto LABEL_6;
  }
  v11 = (const WCHAR *)WString::operator unsigned short *((char *)this + 952);
  v12 = CreateFileW(v11, 0x40000000u, 1u, &g_SA, 2u, 0x80000080, 0);
  if ( v12 == (HANDLE)-1LL )
  {
LABEL_6:
    LastError = GetLastError();
LABEL_7:
    v10 = LastError;
    goto LABEL_23;
  }
  v13 = WString::WString((WString *)v23, (CPageSource *)((char *)this + 952));
  MakeGuard<int (*)(unsigned short const *),WString>(v33, DeleteFileW, v13);
  v27[0] = 0;
  v28 = CloseHandle;
  v29 = v12;
  v14 = (CPageSource *)((char *)this + 944);
  v15 = (const WCHAR *)WString::operator unsigned short *((char *)this + 944);
  v16 = CreateFileW(v15, 0x40000000u, 1u, &g_SA, 2u, 0x80000080, 0);
  if ( v16 == (HANDLE)-1LL )
  {
    v10 = GetLastError();
    ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v27);
    ScopeGuardImpl1<void (*)(unsigned short const *),WString>::~ScopeGuardImpl1<void (*)(unsigned short const *),WString>(v33);
  }
  else
  {
    v17 = WString::WString((WString *)v23, v14);
    MakeGuard<int (*)(unsigned short const *),WString>(v34, DeleteFileW, v17);
    v30[0] = 0;
    v31 = CloseHandle;
    v32 = v16;
    CPageMap::CPageMap((CPageMap *)v45, 0);
    CPageMap::CPageMap((CPageMap *)v44, 1);
    CreateIndexAdminPage((struct CPageMap *)v44, v12);
    for ( j = 0; j < 3; ++j )
    {
      v19 = CPageMap::Save((CPageMap *)v45, hFile[j]);
      if ( v19 || (v19 = CPageMap::Save((CPageMap *)v44, hFile[j])) != 0 )
      {
        CPageMap::~CPageMap((CPageMap *)v44);
        CPageMap::~CPageMap((CPageMap *)v45);
        ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v30);
        ScopeGuardImpl1<void (*)(unsigned short const *),WString>::~ScopeGuardImpl1<void (*)(unsigned short const *),WString>(v34);
        ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v27);
        ScopeGuardImpl1<void (*)(unsigned short const *),WString>::~ScopeGuardImpl1<void (*)(unsigned short const *),WString>(v33);
        v10 = v19;
        goto LABEL_23;
      }
      v20 = hFile[j];
      NumberOfBytesWritten = 0;
      Buffer = 1;
      if ( !WriteFile(v20, &Buffer, 4u, &NumberOfBytesWritten, 0) || NumberOfBytesWritten != 4 || !SetEndOfFile(v20) )
      {
        v21 = GetLastError();
        if ( v21 )
        {
          CPageMap::~CPageMap((CPageMap *)v44);
          CPageMap::~CPageMap((CPageMap *)v45);
          ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v30);
          ScopeGuardImpl1<void (*)(unsigned short const *),WString>::~ScopeGuardImpl1<void (*)(unsigned short const *),WString>(v34);
          ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v27);
          ScopeGuardImpl1<void (*)(unsigned short const *),WString>::~ScopeGuardImpl1<void (*)(unsigned short const *),WString>(v33);
          v10 = v21;
          goto LABEL_23;
        }
      }
    }
    v35[0] = 1;
    v33[0] = 1;
    v34[0] = 1;
    ReportFutureCorruption();
    CPageMap::~CPageMap((CPageMap *)v44);
    CPageMap::~CPageMap((CPageMap *)v45);
    ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v30);
    ScopeGuardImpl1<void (*)(unsigned short const *),WString>::~ScopeGuardImpl1<void (*)(unsigned short const *),WString>(v34);
    ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>((__int64)v27);
    ScopeGuardImpl1<void (*)(unsigned short const *),WString>::~ScopeGuardImpl1<void (*)(unsigned short const *),WString>(v33);
    v10 = 0;
  }
LABEL_23:
  ScopeGuardImpl1<void (*)(unsigned short const *),WString>::~ScopeGuardImpl1<void (*)(unsigned short const *),WString>(v35);
  ScopeGuardImpl2<void (*)(void * *,int),void * *,int>::~ScopeGuardImpl2<void (*)(void * *,int),void * *,int>(v38);
  return v10;
}

```

## disassembly

```asm
0x18002d080  mov     [rsp-8+arg_8], rbx
0x18002d085  mov     [rsp-8+arg_10], rsi
0x18002d08a  push    rbp
0x18002d08b  push    rdi
0x18002d08c  push    r13
0x18002d08e  push    r14
0x18002d090  push    r15
0x18002d092  lea     rbp, [rsp-310h]
0x18002d09a  sub     rsp, 410h
0x18002d0a1  mov     rax, cs:__security_cookie
0x18002d0a8  xor     rax, rsp
0x18002d0ab  mov     [rbp+330h+var_30], rax
0x18002d0b2  mov     r14, rcx
0x18002d0b5  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18002d0bd  movups  xmmword ptr [rbp+330h+hFile], xmm0
0x18002d0c4  movq    [rbp+330h+var_250], xmm0
0x18002d0cc  mov     [rbp+330h+var_358], 0
0x18002d0d0  lea     rax, ?CloseHandleArray@@YAXPEAPEAXH@Z; CloseHandleArray(void * *,int)
0x18002d0d7  mov     [rbp+330h+var_350], rax
0x18002d0db  lea     rax, [rbp+330h+hFile]
0x18002d0e2  mov     [rbp+330h+var_348], rax
0x18002d0e6  mov     [rbp+330h+var_340], 3
0x18002d0ed  lea     r15, [rcx+3C0h]
0x18002d0f4  mov     rdx, r15
0x18002d0f7  lea     rcx, [rsp+430h+Buffer]
0x18002d0fc  call    cs:__imp_??0WString@@QEAA@AEBV0@@Z; WString::WString(WString const &)
0x18002d102  mov     rsi, rax
0x18002d105  mov     [rbp+330h+var_338], rax
0x18002d109  mov     rdx, rax
0x18002d10c  lea     rcx, [rsp+430h+NumberOfBytesWritten]
0x18002d111  call    cs:__imp_??0WString@@QEAA@AEBV0@@Z; WString::WString(WString const &)
0x18002d117  mov     rdi, rax
0x18002d11a  mov     [rbp+330h+var_330], rax
0x18002d11e  mov     rdx, rax
0x18002d121  lea     rcx, [rsp+430h+var_3F0]
0x18002d126  call    cs:__imp_??0WString@@QEAA@AEBV0@@Z; WString::WString(WString const &)
0x18002d12c  mov     rbx, rax
0x18002d12f  mov     [rsp+430h+var_3D8], rax
0x18002d134  mov     [rbp+330h+var_370], 0
0x18002d138  lea     rax, ?DeleteMaps@@YAXPEBG@Z; DeleteMaps(ushort const *)
0x18002d13f  mov     [rbp+330h+var_368], rax
0x18002d143  mov     rdx, rbx
0x18002d146  lea     rcx, [rbp+330h+var_360]
0x18002d14a  call    cs:__imp_??0WString@@QEAA@AEBV0@@Z; WString::WString(WString const &)
0x18002d150  nop
0x18002d151  mov     rcx, rbx
0x18002d154  call    cs:__imp_??1WString@@QEAA@XZ; WString::~WString(void)
0x18002d15a  nop
0x18002d15b  mov     rcx, rdi
0x18002d15e  call    cs:__imp_??1WString@@QEAA@XZ; WString::~WString(void)
0x18002d164  nop
0x18002d165  mov     rcx, rsi
0x18002d168  call    cs:__imp_??1WString@@QEAA@XZ; WString::~WString(void)
0x18002d16e  nop
0x18002d16f  xor     ebx, ebx
0x18002d171  mov     esi, 80000080h
0x18002d176  lea     r13d, [rbx+1]
0x18002d17a  cmp     ebx, 3
0x18002d17d  jge     short loc_18002D1F7
0x18002d17f  mov     rcx, r15
0x18002d182  call    cs:__imp_??BWString@@QEAAPEAGXZ; WString::operator ushort *(void)
0x18002d188  mov     r8, rax; unsigned __int16 *
0x18002d18b  lea     r9d, [rbx+1]
0x18002d18f  mov     edx, 105h; unsigned __int64
0x18002d194  lea     rcx, [rbp+330h+FileName]; unsigned __int16 *
0x18002d19b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002d1a0  test    eax, eax
0x18002d1a2  js      short loc_18002D1F0
0x18002d1a4  mov     [rsp+430h+hTemplateFile], 0; hTemplateFile
0x18002d1ad  mov     [rsp+430h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x18002d1b1  mov     [rsp+430h+dwCreationDisposition], 2; dwCreationDisposition
0x18002d1b9  lea     r9, ?g_SA@@3U_SECURITY_ATTRIBUTES@@A; lpSecurityAttributes
0x18002d1c0  mov     r8d, r13d; dwShareMode
0x18002d1c3  mov     edx, 40000000h; dwDesiredAccess
0x18002d1c8  lea     rcx, [rbp+330h+FileName]; lpFileName
0x18002d1cf  call    cs:__imp_CreateFileW
0x18002d1d5  movsxd  rcx, ebx
0x18002d1d8  mov     [rbp+rcx*8+330h+hFile], rax
0x18002d1e0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002d1e4  jz      short loc_18002D1EA
0x18002d1e6  inc     ebx
0x18002d1e8  jmp     short loc_18002D17A
0x18002d1ea  call    cs:__imp_GetLastError
0x18002d1f0  mov     ebx, eax
0x18002d1f2  jmp     loc_18002D4AB
0x18002d1f7  lea     rdi, [r14+3B8h]
0x18002d1fe  mov     rcx, rdi
0x18002d201  call    cs:__imp_??BWString@@QEAAPEAGXZ; WString::operator ushort *(void)
0x18002d207  mov     rcx, rax; lpFileName
0x18002d20a  mov     [rsp+430h+hTemplateFile], 0; hTemplateFile
0x18002d213  mov     [rsp+430h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x18002d217  mov     r15d, 2
0x18002d21d  mov     [rsp+430h+dwCreationDisposition], r15d; dwCreationDisposition
0x18002d222  lea     r9, ?g_SA@@3U_SECURITY_ATTRIBUTES@@A; lpSecurityAttributes
0x18002d229  mov     r8d, r13d; dwShareMode
0x18002d22c  mov     edx, 40000000h; dwDesiredAccess
0x18002d231  call    cs:__imp_CreateFileW
0x18002d237  mov     rbx, rax
0x18002d23a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002d23e  jz      short loc_18002D1EA
0x18002d240  mov     rdx, rdi
0x18002d243  lea     rcx, [rsp+430h+var_3F0]
0x18002d248  call    cs:__imp_??0WString@@QEAA@AEBV0@@Z; WString::WString(WString const &)
0x18002d24e  mov     r8, rax
0x18002d251  mov     rdx, cs:__imp_DeleteFileW
0x18002d258  lea     rcx, [rbp+330h+var_3A0]
0x18002d25c  call    ??$MakeGuard@P6AHPEBG@ZVWString@@@@YA?AV?$ScopeGuardImpl1@P6AHPEBG@ZVWString@@@@P6AHPEBG@ZVWString@@@Z; MakeGuard<int (*)(ushort const *),WString>(int (*)(ushort const *),WString)
0x18002d261  nop
0x18002d262  mov     rdi, cs:__imp_CloseHandle
0x18002d269  mov     [rsp+430h+var_3D0], 0
0x18002d26e  mov     [rsp+430h+var_3C8], rdi
0x18002d273  mov     [rsp+430h+var_3C0], rbx
0x18002d278  lea     rsi, [r14+3B0h]
0x18002d27f  mov     rcx, rsi
0x18002d282  call    cs:__imp_??BWString@@QEAAPEAGXZ; WString::operator ushort *(void)
0x18002d288  mov     rcx, rax; lpFileName
0x18002d28b  mov     [rsp+430h+hTemplateFile], 0; hTemplateFile
0x18002d294  mov     [rsp+430h+dwFlagsAndAttributes], 80000080h; dwFlagsAndAttributes
0x18002d29c  mov     [rsp+430h+dwCreationDisposition], r15d; dwCreationDisposition
0x18002d2a1  lea     r9, ?g_SA@@3U_SECURITY_ATTRIBUTES@@A; lpSecurityAttributes
0x18002d2a8  mov     r8d, r13d; dwShareMode
0x18002d2ab  mov     edx, 40000000h; dwDesiredAccess
0x18002d2b0  call    cs:__imp_CreateFileW
0x18002d2b6  mov     r14, rax
0x18002d2b9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002d2bd  jnz     short loc_18002D2E0
0x18002d2bf  call    cs:__imp_GetLastError
0x18002d2c5  mov     ebx, eax
0x18002d2c7  lea     rcx, [rsp+430h+var_3D0]
0x18002d2cc  call    ??1?$ScopeGuardImpl1@P6AXPEAU_RTL_CRITICAL_SECTION@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>(void)
0x18002d2d1  nop
0x18002d2d2  lea     rcx, [rbp+330h+var_3A0]
0x18002d2d6  call    ??1?$ScopeGuardImpl1@P6AXPEBG@ZVWString@@@@QEAA@XZ; ScopeGuardImpl1<void (*)(ushort const *),WString>::~ScopeGuardImpl1<void (*)(ushort const *),WString>(void)
0x18002d2db  jmp     loc_18002D4AB
0x18002d2e0  mov     rdx, rsi
0x18002d2e3  lea     rcx, [rsp+430h+var_3F0]
0x18002d2e8  call    cs:__imp_??0WString@@QEAA@AEBV0@@Z; WString::WString(WString const &)
0x18002d2ee  mov     r8, rax
0x18002d2f1  mov     rdx, cs:__imp_DeleteFileW
0x18002d2f8  lea     rcx, [rbp+330h+var_388]
0x18002d2fc  call    ??$MakeGuard@P6AHPEBG@ZVWString@@@@YA?AV?$ScopeGuardImpl1@P6AHPEBG@ZVWString@@@@P6AHPEBG@ZVWString@@@Z; MakeGuard<int (*)(ushort const *),WString>(int (*)(ushort const *),WString)
0x18002d301  nop
0x18002d302  mov     [rsp+430h+var_3B8], 0
0x18002d307  mov     [rbp+330h+var_3B0], rdi
0x18002d30b  mov     [rbp+330h+var_3A8], r14
0x18002d30f  xor     edx, edx; int
0x18002d311  lea     rcx, [rbp+330h+var_2C0]; this
0x18002d315  call    ??0CPageMap@@QEAA@H@Z; CPageMap::CPageMap(int)
0x18002d31a  nop
0x18002d31b  mov     edx, r13d; int
0x18002d31e  lea     rcx, [rbp+330h+var_320]; this
0x18002d322  call    ??0CPageMap@@QEAA@H@Z; CPageMap::CPageMap(int)
0x18002d327  nop
0x18002d328  mov     rdx, rbx; void *
0x18002d32b  lea     rcx, [rbp+330h+var_320]; struct CPageMap *
0x18002d32f  call    ?CreateIndexAdminPage@@YAKAEAUCPageMap@@PEAX@Z; CreateIndexAdminPage(CPageMap &,void *)
0x18002d334  xor     ebx, ebx
0x18002d336  cmp     ebx, 3
0x18002d339  jge     loc_18002D45A
0x18002d33f  movsxd  rdi, ebx
0x18002d342  mov     rdx, [rbp+rdi*8+330h+hFile]; void *
0x18002d34a  lea     rcx, [rbp+330h+var_2C0]; this
0x18002d34e  call    ?Save@CPageMap@@QEAAKPEAX@Z; CPageMap::Save(void *)
0x18002d353  mov     esi, eax
0x18002d355  test    eax, eax
0x18002d357  jnz     loc_18002D419
0x18002d35d  mov     rdx, [rbp+rdi*8+330h+hFile]; void *
0x18002d365  lea     rcx, [rbp+330h+var_320]; this
0x18002d369  call    ?Save@CPageMap@@QEAAKPEAX@Z; CPageMap::Save(void *)
0x18002d36e  mov     esi, eax
0x18002d370  test    eax, eax
0x18002d372  jnz     loc_18002D419
0x18002d378  mov     rdi, [rbp+rdi*8+330h+hFile]
0x18002d380  mov     [rsp+430h+NumberOfBytesWritten], eax
0x18002d384  mov     [rsp+430h+Buffer], r13d
0x18002d389  mov     qword ptr [rsp+430h+dwCreationDisposition], 0; lpOverlapped
0x18002d392  lea     r9, [rsp+430h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002d397  lea     r8d, [rax+4]; nNumberOfBytesToWrite
0x18002d39b  lea     rdx, [rsp+430h+Buffer]; lpBuffer
0x18002d3a0  mov     rcx, rdi; hFile
0x18002d3a3  call    cs:__imp_WriteFile
0x18002d3a9  test    eax, eax
0x18002d3ab  jz      short loc_18002D3C1
0x18002d3ad  cmp     [rsp+430h+NumberOfBytesWritten], 4
0x18002d3b2  jnz     short loc_18002D3C1
0x18002d3b4  mov     rcx, rdi; hFile
0x18002d3b7  call    cs:__imp_SetEndOfFile
0x18002d3bd  test    eax, eax
0x18002d3bf  jnz     short loc_18002D3CD
0x18002d3c1  call    cs:__imp_GetLastError
0x18002d3c7  mov     edi, eax
0x18002d3c9  test    eax, eax
0x18002d3cb  jnz     short loc_18002D3D5
0x18002d3cd  add     ebx, r13d
0x18002d3d0  jmp     loc_18002D336
0x18002d3d5  lea     rcx, [rbp+330h+var_320]; this
0x18002d3d9  call    ??1CPageMap@@QEAA@XZ; CPageMap::~CPageMap(void)
0x18002d3de  nop
0x18002d3df  lea     rcx, [rbp+330h+var_2C0]; this
0x18002d3e3  call    ??1CPageMap@@QEAA@XZ; CPageMap::~CPageMap(void)
0x18002d3e8  nop
0x18002d3e9  lea     rcx, [rsp+430h+var_3B8]
0x18002d3ee  call    ??1?$ScopeGuardImpl1@P6AXPEAU_RTL_CRITICAL_SECTION@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>(void)
0x18002d3f3  nop
0x18002d3f4  lea     rcx, [rbp+330h+var_388]
0x18002d3f8  call    ??1?$ScopeGuardImpl1@P6AXPEBG@ZVWString@@@@QEAA@XZ; ScopeGuardImpl1<void (*)(ushort const *),WString>::~ScopeGuardImpl1<void (*)(ushort const *),WString>(void)
0x18002d3fd  nop
0x18002d3fe  lea     rcx, [rsp+430h+var_3D0]
0x18002d403  call    ??1?$ScopeGuardImpl1@P6AXPEAU_RTL_CRITICAL_SECTION@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>(void)
0x18002d408  nop
0x18002d409  lea     rcx, [rbp+330h+var_3A0]
0x18002d40d  call    ??1?$ScopeGuardImpl1@P6AXPEBG@ZVWString@@@@QEAA@XZ; ScopeGuardImpl1<void (*)(ushort const *),WString>::~ScopeGuardImpl1<void (*)(ushort const *),WString>(void)
0x18002d412  mov     ebx, edi
0x18002d414  jmp     loc_18002D4AB
0x18002d419  lea     rcx, [rbp+330h+var_320]; this
0x18002d41d  call    ??1CPageMap@@QEAA@XZ; CPageMap::~CPageMap(void)
0x18002d422  nop
0x18002d423  lea     rcx, [rbp+330h+var_2C0]; this
0x18002d427  call    ??1CPageMap@@QEAA@XZ; CPageMap::~CPageMap(void)
0x18002d42c  nop
0x18002d42d  lea     rcx, [rsp+430h+var_3B8]
0x18002d432  call    ??1?$ScopeGuardImpl1@P6AXPEAU_RTL_CRITICAL_SECTION@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>(void)
0x18002d437  nop
0x18002d438  lea     rcx, [rbp+330h+var_388]
0x18002d43c  call    ??1?$ScopeGuardImpl1@P6AXPEBG@ZVWString@@@@QEAA@XZ; ScopeGuardImpl1<void (*)(ushort const *),WString>::~ScopeGuardImpl1<void (*)(ushort const *),WString>(void)
0x18002d441  nop
0x18002d442  lea     rcx, [rsp+430h+var_3D0]
0x18002d447  call    ??1?$ScopeGuardImpl1@P6AXPEAU_RTL_CRITICAL_SECTION@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>(void)
0x18002d44c  nop
0x18002d44d  lea     rcx, [rbp+330h+var_3A0]
0x18002d451  call    ??1?$ScopeGuardImpl1@P6AXPEBG@ZVWString@@@@QEAA@XZ; ScopeGuardImpl1<void (*)(ushort const *),WString>::~ScopeGuardImpl1<void (*)(ushort const *),WString>(void)
0x18002d456  mov     ebx, esi
0x18002d458  jmp     short loc_18002D4AB
0x18002d45a  mov     [rbp+330h+var_370], r13b
0x18002d45e  mov     [rbp+330h+var_3A0], r13b
0x18002d462  mov     [rbp+330h+var_388], r13b
0x18002d466  call    ?ReportFutureCorruption@@YAJXZ; ReportFutureCorruption(void)
0x18002d46b  nop
0x18002d46c  lea     rcx, [rbp+330h+var_320]; this
0x18002d470  call    ??1CPageMap@@QEAA@XZ; CPageMap::~CPageMap(void)
0x18002d475  nop
0x18002d476  lea     rcx, [rbp+330h+var_2C0]; this
0x18002d47a  call    ??1CPageMap@@QEAA@XZ; CPageMap::~CPageMap(void)
0x18002d47f  nop
0x18002d480  lea     rcx, [rsp+430h+var_3B8]
0x18002d485  call    ??1?$ScopeGuardImpl1@P6AXPEAU_RTL_CRITICAL_SECTION@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>(void)
0x18002d48a  nop
0x18002d48b  lea     rcx, [rbp+330h+var_388]
0x18002d48f  call    ??1?$ScopeGuardImpl1@P6AXPEBG@ZVWString@@@@QEAA@XZ; ScopeGuardImpl1<void (*)(ushort const *),WString>::~ScopeGuardImpl1<void (*)(ushort const *),WString>(void)
0x18002d494  nop
0x18002d495  lea     rcx, [rsp+430h+var_3D0]
0x18002d49a  call    ??1?$ScopeGuardImpl1@P6AXPEAU_RTL_CRITICAL_SECTION@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>(void)
0x18002d49f  nop
0x18002d4a0  lea     rcx, [rbp+330h+var_3A0]
0x18002d4a4  call    ??1?$ScopeGuardImpl1@P6AXPEBG@ZVWString@@@@QEAA@XZ; ScopeGuardImpl1<void (*)(ushort const *),WString>::~ScopeGuardImpl1<void (*)(ushort const *),WString>(void)
0x18002d4a9  xor     ebx, ebx
0x18002d4ab  lea     rcx, [rbp+330h+var_370]
0x18002d4af  call    ??1?$ScopeGuardImpl1@P6AXPEBG@ZVWString@@@@QEAA@XZ; ScopeGuardImpl1<void (*)(ushort const *),WString>::~ScopeGuardImpl1<void (*)(ushort const *),WString>(void)
0x18002d4b4  nop
0x18002d4b5  lea     rcx, [rbp+330h+var_358]
0x18002d4b9  call    ??1?$ScopeGuardImpl2@P6AXPEAPEAXH@ZPEAPEAXH@@QEAA@XZ; ScopeGuardImpl2<void (*)(void * *,int),void * *,int>::~ScopeGuardImpl2<void (*)(void * *,int),void * *,int>(void)
0x18002d4be  mov     eax, ebx
0x18002d4c0  mov     rcx, [rbp+330h+var_30]
0x18002d4c7  xor     rcx, rsp; StackCookie
0x18002d4ca  call    __security_check_cookie
0x18002d4cf  lea     r11, [rsp+430h+var_20]
0x18002d4d7  mov     rbx, [r11+38h]
0x18002d4db  mov     rsi, [r11+40h]
0x18002d4df  mov     rsp, r11
0x18002d4e2  pop     r15
0x18002d4e4  pop     r14
0x18002d4e6  pop     r13
0x18002d4e8  pop     rdi
0x18002d4e9  pop     rbp
0x18002d4ea  retn
```
