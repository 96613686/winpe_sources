# CMsiPath::TempFolderOrFile(Bool,ushort const *,ushort const *,Bool,_SECURITY_ATTRIBUTES *,IMsiString const * &)

- ea: `0x1800f11e0`
- end: `0x1800f1962`
- name: `?TempFolderOrFile@CMsiPath@@IEAAPEAVIMsiRecord@@W4Bool@@PEBG10PEAU_SECURITY_ATTRIBUTES@@AEAPEBVIMsiString@@@Z`
- size: `1922`
- prototype: `struct IMsiRecord *__high(enum Bool, const unsigned __int16 *, const unsigned __int16 *, enum Bool, struct _SECURITY_ATTRIBUTES *, const struct IMsiString **)`
- caller_count: `2`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800f1190`
- `0x1802165e0`

## callees

- `0x180022120`
- `0x180024f9c`
- `0x1800255e0`
- `0x180025904`
- `0x180025a18`
- `0x180027b54`
- `0x18004295c`
- `0x180046220`
- `0x180068680`
- `0x18006f870`
- `0x18007b810`
- `0x18007ccec`
- `0x180083178`
- `0x1800833ec`
- `0x1800f11e0`
- `0x18011d2c4`
- `0x18013a830`
- `0x18014ddf8`
- `0x18014e4d4`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!SetFileSecurityW` at `0x1800f1366`
- `ADVAPI32!SetFileSecurityW` at `0x1800f1366`
- `KERNEL32!CloseHandle` at `0x1800f13c1`
- `KERNEL32!CloseHandle` at `0x1800f1423`
- `KERNEL32!CloseHandle` at `0x1800f175f`
- `KERNEL32!CloseHandle` at `0x1800f17b6`
- `KERNEL32!CloseHandle` at `0x1800f13c1`
- `KERNEL32!CloseHandle` at `0x1800f1423`
- `KERNEL32!CloseHandle` at `0x1800f175f`
- `KERNEL32!CloseHandle` at `0x1800f17b6`
- `KERNEL32!GetTickCount` at `0x1800f155a`
- `KERNEL32!GetTickCount` at `0x1800f155a`
- `KERNEL32!GetLastError` at `0x1800f12d7`
- `KERNEL32!GetLastError` at `0x1800f1438`
- `KERNEL32!GetLastError` at `0x1800f17c7`
- `KERNEL32!GetLastError` at `0x1800f12d7`
- `KERNEL32!GetLastError` at `0x1800f1438`
- `KERNEL32!GetLastError` at `0x1800f17c7`
- `KERNEL32!SetLastError` at `0x1800f142e`
- `KERNEL32!SetLastError` at `0x1800f17c1`
- `KERNEL32!SetLastError` at `0x1800f142e`
- `KERNEL32!SetLastError` at `0x1800f17c1`
- `KERNEL32!lstrlenW` at `0x1800f125f`
- `KERNEL32!lstrlenW` at `0x1800f125f`
- `KERNEL32!CreateFileW` at `0x1800f139b`
- `KERNEL32!CreateFileW` at `0x1800f173d`
- `KERNEL32!CreateFileW` at `0x1800f139b`
- `KERNEL32!CreateFileW` at `0x1800f173d`
- `KERNEL32!CreateDirectoryW` at `0x1800f16ee`
- `KERNEL32!CreateDirectoryW` at `0x1800f16ee`
- `KERNEL32!GetFileType` at `0x1800f13b1`
- `KERNEL32!GetFileType` at `0x1800f174f`
- `KERNEL32!GetFileType` at `0x1800f13b1`
- `KERNEL32!GetFileType` at `0x1800f174f`
- `KERNEL32!GetTempFileNameW` at `0x1800f12ca`
- `KERNEL32!GetTempFileNameW` at `0x1800f12ca`

## string_xrefs

- `0x1800f13ef`: `Error: This is not a valid file, hence failing to create: %s`
- `0x1800f1779`: `Error: This is not a valid file, hence failing to create: %s`

## pseudocode

```c
struct IMsiRecord *__fastcall CMsiPath::TempFolderOrFile(
        _QWORD *a1,
        int a2,
        unsigned __int16 *a3,
        _WORD *a4,
        int a5,
        struct _SECURITY_ATTRIBUTES *a6,
        _QWORD *a7)
{
  _QWORD *v10; // r12
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rbx
  __int64 v14; // r8
  _WORD *v15; // r9
  DWORD LastError; // r14d
  int v17; // r13d
  int v18; // r15d
  const WCHAR *v19; // rax
  char v20; // di
  const WCHAR *v21; // rdx
  int v22; // esi
  int v23; // eax
  bool v24; // cl
  LPSECURITY_ATTRIBUTES v25; // r13
  void *lpSecurityDescriptor; // rdi
  SECURITY_INFORMATION SecurityInformation; // eax
  HANDLE v28; // rax
  void *v29; // rdi
  BOOL v30; // edi
  __int64 v31; // rax
  _WORD *v32; // rcx
  signed int v33; // edi
  const unsigned __int16 *v34; // rax
  int v35; // edx
  struct IMsiRecord *v36; // rdi
  int v38; // r10d
  DWORD TickCount; // eax
  unsigned int v40; // r15d
  unsigned int v41; // eax
  unsigned int i; // ecx
  __int64 v43; // rdi
  _WORD *v44; // rax
  _WORD *v45; // rcx
  bool v47; // cl
  HANDLE FileW; // rax
  void *v49; // rdi
  const struct IMsiString **v50; // rax
  __int64 v51; // rdi
  void *v52; // rcx
  int v53; // [rsp+60h] [rbp-A0h]
  int v54; // [rsp+64h] [rbp-9Ch] BYREF
  void *v55; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v56; // [rsp+70h] [rbp-90h]
  unsigned int v57; // [rsp+74h] [rbp-8Ch]
  int v58; // [rsp+78h] [rbp-88h]
  _QWORD *v59; // [rsp+80h] [rbp-80h]
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+88h] [rbp-78h] BYREF
  int v61; // [rsp+90h] [rbp-70h]
  unsigned __int16 *v62; // [rsp+98h] [rbp-68h] BYREF
  _QWORD *v63; // [rsp+A0h] [rbp-60h]
  unsigned __int16 v64; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v65[2]; // [rsp+AAh] [rbp-56h] BYREF
  __int16 v66; // [rsp+BAh] [rbp-46h]
  unsigned __int16 v67[16]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR TempFileName[264]; // [rsp+E0h] [rbp-20h] BYREF

  lpSecurityAttributes = a6;
  v63 = a7;
  v10 = a1;
  v11 = *a1;
  v62 = a3;
  v61 = a2;
  v59 = a1;
  v13 = (*(__int64 (__fastcall **)(_QWORD *))(v11 + 56))(a1);
  v58 = 0;
  LastError = 0;
  if ( a3 )
    v17 = lstrlenW(a3);
  else
    v17 = 0;
  if ( a2 || v17 >= 4 || a4 && *a4 )
  {
    v64 = 46;
    v65[0] = 0x70006D0074LL;
    v65[1] = 0;
    v66 = 0;
    if ( a4 && *a4 )
    {
      v31 = 3;
      v14 = 9;
      v15 = v65;
      do
      {
        if ( !v31 )
          break;
        if ( !*a4 )
          break;
        *v15++ = *a4++;
        --v31;
        --v14;
      }
      while ( v14 );
      v32 = v15 - 1;
      v33 = v14 == 0 ? 0x8007007A : 0;
      if ( v14 )
        v32 = v15;
      *v32 = 0;
      if ( !v14 )
      {
LABEL_45:
        v34 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 80LL))(v13);
        v35 = v33;
        goto LABEL_46;
      }
    }
    v53 = 0;
    if ( v17 > 8 )
      v17 = 8;
    v38 = 8 - v17;
    v54 = 8 - v17;
    if ( byte_18030A82A )
    {
      v40 = dword_18030B3C8;
    }
    else
    {
      TickCount = GetTickCount();
      v38 = v54;
      v40 = TickCount;
      byte_18030A82A = 1;
    }
    dword_18030B3C8 = v40 + 1;
    if ( v17 )
      v40 &= (1 << (4 * v38)) - 1;
    if ( v38 == 8 )
      v41 = -1;
    else
      v41 = (1 << (4 * v38)) - 1;
    v56 = v41;
    for ( i = 0; ; i = v57 + 1 )
    {
      v57 = i;
      if ( i > v41 )
      {
        v30 = v53;
        goto LABEL_100;
      }
      if ( v62 )
      {
        v33 = StringCchCopyNW(v67, 9u, v62, v17);
        if ( v33 < 0 )
          goto LABEL_45;
      }
      if ( v38 )
      {
        v33 = StringCchPrintfW(&v67[v17], 9LL - v17, L"%x", v40);
        if ( v33 < 0 )
          goto LABEL_45;
      }
      v43 = 2147483646;
      v44 = (_WORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 80LL))(v13);
      v14 = (__int64)TempFileName;
      v12 = 260;
      v15 = 0;
      do
      {
        if ( !v43 )
          break;
        if ( !*v44 )
          break;
        *(_WORD *)v14 = *v44++;
        v14 += 2;
        --v43;
        --v12;
      }
      while ( v12 );
      v45 = (_WORD *)(v14 - 2);
      if ( v12 )
        v45 = (_WORD *)v14;
      *v45 = 0;
      if ( !v12
        || (int)StringCchCatW(TempFileName, 0x104u, v67) < 0
        || (int)StringCchCatW(TempFileName, 0x104u, &v64) < 0 )
      {
        goto LABEL_98;
      }
      if ( !(v61
           ? CMsiPath::FFolderExists(v59, TempFileName)
           : (unsigned int)FFileExists(TempFileName, v12, *((unsigned int *)v59 + 12))) )
        break;
LABEL_94:
      ++dword_18030B3C8;
      v41 = v56;
      if ( v40 == v56 )
        v40 = 0;
      else
        ++v40;
      v38 = v54;
    }
    if ( *((_DWORD *)v59 + 12) )
      StartImpersonating();
    if ( v61 )
    {
      if ( CreateDirectoryW(TempFileName, lpSecurityAttributes) )
      {
LABEL_80:
        LastError = 0;
        v53 = 1;
        v30 = 1;
        goto LABEL_89;
      }
    }
    else
    {
      FileW = CreateFileW(TempFileName, 0x40000000u, 1u, lpSecurityAttributes, 1u, 0x100080u, 0);
      v49 = FileW;
      if ( FileW != (HANDLE)-1LL )
      {
        if ( GetFileType(FileW) - 2 > 1 )
        {
          CloseHandle(v49);
          goto LABEL_80;
        }
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"Error: This is not a valid file, hence failing to create: %s",
            TempFileName,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        CloseHandle(v49);
        SetLastError(0x6Eu);
      }
    }
    v30 = v53;
    LastError = GetLastError();
LABEL_89:
    if ( *((_DWORD *)v59 + 12) )
      StopImpersonating(v47);
    if ( LastError == 183 )
    {
      LastError = 80;
    }
    else if ( LastError != 80 )
    {
      goto LABEL_100;
    }
    goto LABEL_94;
  }
  v18 = 0;
  if ( *((_DWORD *)v10 + 12) )
    StartImpersonating();
  v19 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 80LL))(v13);
  v20 = 0;
  v21 = &Default;
  if ( a3 )
    v21 = a3;
  v22 = 1;
  if ( !GetTempFileNameW(v19, v21, 0, TempFileName) )
  {
    LastError = GetLastError();
    v18 = 1;
  }
  v23 = RunningAsLocalSystem();
  if ( v23 != -1 )
  {
    if ( v18 || (v25 = lpSecurityAttributes) == 0 || !lpSecurityAttributes->lpSecurityDescriptor )
    {
      v22 = v18;
      goto LABEL_33;
    }
    if ( v23 == 1 && !*((_DWORD *)v10 + 12) )
      v20 = 1;
    CElevate::CElevate((CElevate *)&lpSecurityAttributes, v20);
    CRefCountedTokenPrivileges::CRefCountedTokenPrivileges((__int64)&v54);
    lpSecurityDescriptor = v25->lpSecurityDescriptor;
    SecurityInformation = GetSecurityInformation(lpSecurityDescriptor);
    if ( SetFileSecurityW(TempFileName, SecurityInformation, lpSecurityDescriptor) )
    {
      v28 = CreateFileW(TempFileName, 0x40000000u, 0, 0, 5u, 0x100000u, 0);
      v29 = v28;
      if ( v28 != (HANDLE)-1LL )
      {
        if ( GetFileType(v28) - 2 > 1 )
        {
          CloseHandle(v29);
          v22 = 0;
LABEL_31:
          CRefCountedTokenPrivileges::~CRefCountedTokenPrivileges((CRefCountedTokenPrivileges *)&v54);
          CElevate::~CElevate((CElevate *)&lpSecurityAttributes);
          goto LABEL_33;
        }
        if ( g_dmDiagnosticMode )
        {
          DebugString(
            9,
            0,
            0,
            L"Error: This is not a valid file, hence failing to create: %s",
            TempFileName,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
          v10 = v59;
        }
        CloseHandle(v29);
        SetLastError(0x6Eu);
      }
      v58 = 1;
    }
    LastError = GetLastError();
    goto LABEL_31;
  }
  PostError(1501);
  LastError = 5;
LABEL_33:
  if ( *((_DWORD *)v10 + 12) )
    StopImpersonating(v24);
  v30 = v22 == 0;
LABEL_100:
  if ( !v30 )
  {
    if ( !LastError )
      LastError = 80;
    if ( v58 && LastError == 5 )
    {
      v50 = (const struct IMsiString **)MsiString::MsiString((MsiString *)&v62, TempFileName);
      v36 = PostError(1304, *v50);
      (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v62 + 16LL))(v62);
      goto LABEL_47;
    }
LABEL_98:
    v34 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64, __int64, __int64, _WORD *))(*(_QWORD *)v13 + 80LL))(
                                      v13,
                                      v12,
                                      v14,
                                      v15);
    v35 = LastError;
LABEL_46:
    v36 = PostError(1336, v35, v34);
LABEL_47:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    return v36;
  }
  v55 = &MsiString::s_NullString;
  (*(void (__fastcall **)(void *, WCHAR *, void **))(MsiString::s_NullString + 96LL))(
    &MsiString::s_NullString,
    TempFileName,
    &v55);
  if ( a5 )
  {
    v51 = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)v55 + 176LL))(v55, 6, 92);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v55 + 16LL))(v55);
    v55 = (void *)v51;
  }
  else
  {
    v51 = (__int64)v55;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 8LL))(v51);
  v52 = v55;
  *v63 = v55;
  (*(void (__fastcall **)(void *))(*(_QWORD *)v52 + 16LL))(v52);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  return 0;
}

```

## disassembly

```asm
0x1800f11e0  mov     [rsp-8+arg_8], rbx
0x1800f11e5  push    rbp
0x1800f11e6  push    rsi
0x1800f11e7  push    rdi
0x1800f11e8  push    r12
0x1800f11ea  push    r13
0x1800f11ec  push    r14
0x1800f11ee  push    r15
0x1800f11f0  lea     rbp, [rsp-200h]
0x1800f11f8  sub     rsp, 300h
0x1800f11ff  mov     rax, cs:__security_cookie
0x1800f1206  xor     rax, rsp
0x1800f1209  mov     [rbp+230h+var_40], rax
0x1800f1210  mov     rax, [rbp+230h+arg_28]
0x1800f1217  mov     rdi, r9
0x1800f121a  mov     [rbp+230h+lpSecurityAttributes], rax
0x1800f121e  mov     rsi, r8
0x1800f1221  mov     rax, [rbp+230h+arg_30]
0x1800f1228  mov     r15d, edx
0x1800f122b  mov     [rbp+230h+var_290], rax
0x1800f122f  mov     r12, rcx
0x1800f1232  mov     rax, [rcx]
0x1800f1235  mov     [rbp+230h+var_298], r8
0x1800f1239  mov     [rbp+230h+var_2A0], edx
0x1800f123c  mov     [rbp+230h+var_2B0], rcx
0x1800f1240  mov     rax, [rax+38h]
0x1800f1244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1249  xor     r11d, r11d
0x1800f124c  mov     rbx, rax
0x1800f124f  mov     [rsp+330h+var_2B8], r11d
0x1800f1254  mov     r14d, r11d
0x1800f1257  test    rsi, rsi
0x1800f125a  jz      short loc_1800F126D
0x1800f125c  mov     rcx, rsi; lpString
0x1800f125f  call    cs:__imp_lstrlenW
0x1800f1265  mov     r13d, eax
0x1800f1268  xor     r11d, r11d
0x1800f126b  jmp     short loc_1800F1270
0x1800f126d  mov     r13d, r11d
0x1800f1270  test    r15d, r15d
0x1800f1273  jnz     loc_1800F1479
0x1800f1279  cmp     r13d, 4
0x1800f127d  jge     loc_1800F1479
0x1800f1283  test    rdi, rdi
0x1800f1286  jz      short loc_1800F1292
0x1800f1288  cmp     [rdi], r11w
0x1800f128c  jnz     loc_1800F1479
0x1800f1292  mov     r15d, r11d
0x1800f1295  cmp     [r12+30h], r11d
0x1800f129a  jz      short loc_1800F12A1
0x1800f129c  call    ?StartImpersonating@@YA_NXZ; StartImpersonating(void)
0x1800f12a1  mov     rax, [rbx]
0x1800f12a4  mov     rcx, rbx
0x1800f12a7  mov     rax, [rax+50h]
0x1800f12ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f12b0  xor     edi, edi
0x1800f12b2  lea     rdx, Default
0x1800f12b9  test    rsi, rsi
0x1800f12bc  lea     r9, [rbp+230h+TempFileName]; lpTempFileName
0x1800f12c0  mov     rcx, rax; lpPathName
0x1800f12c3  cmovnz  rdx, rsi; lpPrefixString
0x1800f12c7  xor     r8d, r8d; uUnique
0x1800f12ca  call    cs:__imp_GetTempFileNameW
0x1800f12d0  lea     esi, [rdi+1]
0x1800f12d3  test    eax, eax
0x1800f12d5  jnz     short loc_1800F12E3
0x1800f12d7  call    cs:__imp_GetLastError
0x1800f12dd  mov     r14d, eax
0x1800f12e0  mov     r15d, esi
0x1800f12e3  call    ?RunningAsLocalSystem@@YA?AW4TRI@@XZ; RunningAsLocalSystem(void)
0x1800f12e8  cmp     eax, 0FFFFFFFFh
0x1800f12eb  jnz     short loc_1800F1305
0x1800f12ed  mov     ecx, 5DDh; int
0x1800f12f2  call    ?PostError@@YAPEAVIMsiRecord@@H@Z; PostError(int)
0x1800f12f7  mov     r14d, 5
0x1800f12fd  xor     r11d, r11d
0x1800f1300  jmp     loc_1800F145C
0x1800f1305  xor     r11d, r11d
0x1800f1308  test    r15d, r15d
0x1800f130b  jnz     loc_1800F1459
0x1800f1311  mov     r13, [rbp+230h+lpSecurityAttributes]
0x1800f1315  test    r13, r13
0x1800f1318  jz      loc_1800F1459
0x1800f131e  cmp     [r13+8], r11
0x1800f1322  jz      loc_1800F1459
0x1800f1328  cmp     eax, esi
0x1800f132a  jnz     short loc_1800F1336
0x1800f132c  cmp     [r12+30h], r11d
0x1800f1331  jnz     short loc_1800F1336
0x1800f1333  mov     dil, sil
0x1800f1336  mov     dl, dil; bool
0x1800f1339  lea     rcx, [rbp+230h+lpSecurityAttributes]; this
0x1800f133d  call    ??0CElevate@@QEAA@_N@Z; CElevate::CElevate(bool)
0x1800f1342  mov     r8b, dil
0x1800f1345  lea     rcx, [rsp+330h+var_2CC]
0x1800f134a  mov     edx, esi
0x1800f134c  call    ??0CRefCountedTokenPrivileges@@QEAA@W4itkpEnum@@_N@Z; CRefCountedTokenPrivileges::CRefCountedTokenPrivileges(itkpEnum,bool)
0x1800f1351  mov     rdi, [r13+8]
0x1800f1355  mov     rcx, rdi; pSecurityDescriptor
0x1800f1358  call    ?GetSecurityInformation@@YAKPEAX@Z; GetSecurityInformation(void *)
0x1800f135d  mov     r8, rdi; pSecurityDescriptor
0x1800f1360  lea     rcx, [rbp+230h+TempFileName]; lpFileName
0x1800f1364  mov     edx, eax; SecurityInformation
0x1800f1366  call    cs:__imp_SetFileSecurityW
0x1800f136c  xor     r13d, r13d
0x1800f136f  test    eax, eax
0x1800f1371  jz      loc_1800F1438
0x1800f1377  mov     [rsp+330h+hTemplateFile], r13; hTemplateFile
0x1800f137c  lea     rcx, [rbp+230h+TempFileName]; lpFileName
0x1800f1380  mov     [rsp+330h+dwFlagsAndAttributes], 100000h; dwFlagsAndAttributes
0x1800f1388  xor     r9d, r9d; lpSecurityAttributes
0x1800f138b  xor     r8d, r8d; dwShareMode
0x1800f138e  mov     [rsp+330h+dwCreationDisposition], 5; dwCreationDisposition
0x1800f1396  mov     edx, 40000000h; dwDesiredAccess
0x1800f139b  call    cs:__imp_CreateFileW
0x1800f13a1  mov     rdi, rax
0x1800f13a4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800f13a8  jz      loc_1800F1434
0x1800f13ae  mov     rcx, rax; hFile
0x1800f13b1  call    cs:__imp_GetFileType
0x1800f13b7  add     eax, 0FFFFFFFEh
0x1800f13ba  cmp     eax, esi
0x1800f13bc  jbe     short loc_1800F13CC
0x1800f13be  mov     rcx, rdi; hObject
0x1800f13c1  call    cs:__imp_CloseHandle
0x1800f13c7  mov     esi, r15d
0x1800f13ca  jmp     short loc_1800F1441
0x1800f13cc  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x1800f13d3  jz      short loc_1800F1420
0x1800f13d5  mov     [rsp+330h+var_2D8], r13; void *
0x1800f13da  lea     r12, aNull; "(NULL)"
0x1800f13e1  mov     [rsp+330h+var_2E0], r13d; unsigned int
0x1800f13e6  lea     rax, [rbp+230h+TempFileName]
0x1800f13ea  mov     [rsp+330h+var_2E8], r12; unsigned __int16 *
0x1800f13ef  lea     r9, aErrorThisIsNot; "Error: This is not a valid file, hence "...
0x1800f13f6  mov     [rsp+330h+var_2F0], r12; unsigned __int16 *
0x1800f13fb  xor     edx, edx; unsigned __int16
0x1800f13fd  mov     [rsp+330h+var_2F8], r12; unsigned __int16 *
0x1800f1402  xor     r8d, r8d; int
0x1800f1405  mov     [rsp+330h+hTemplateFile], r12; unsigned __int16 *
0x1800f140a  mov     qword ptr [rsp+330h+dwFlagsAndAttributes], r12; unsigned __int16 *
0x1800f140f  lea     ecx, [rdx+9]; int
0x1800f1412  mov     qword ptr [rsp+330h+dwCreationDisposition], rax; unsigned __int16 *
0x1800f1417  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800f141c  mov     r12, [rbp+230h+var_2B0]
0x1800f1420  mov     rcx, rdi; hObject
0x1800f1423  call    cs:__imp_CloseHandle
0x1800f1429  mov     ecx, 6Eh ; 'n'; dwErrCode
0x1800f142e  call    cs:__imp_SetLastError
0x1800f1434  mov     [rsp+330h+var_2B8], esi
0x1800f1438  call    cs:__imp_GetLastError
0x1800f143e  mov     r14d, eax
0x1800f1441  lea     rcx, [rsp+330h+var_2CC]; this
0x1800f1446  call    ??1CRefCountedTokenPrivileges@@QEAA@XZ; CRefCountedTokenPrivileges::~CRefCountedTokenPrivileges(void)
0x1800f144b  lea     rcx, [rbp+230h+lpSecurityAttributes]; this
0x1800f144f  call    ??1CElevate@@QEAA@XZ; CElevate::~CElevate(void)
0x1800f1454  jmp     loc_1800F12FD
0x1800f1459  mov     esi, r15d
0x1800f145c  cmp     [r12+30h], r11d
0x1800f1461  jz      short loc_1800F146B
0x1800f1463  call    ?StopImpersonating@@YAX_N@Z; StopImpersonating(bool)
0x1800f1468  xor     r11d, r11d
0x1800f146b  test    esi, esi
0x1800f146d  mov     edi, r11d
0x1800f1470  setz    dil
0x1800f1474  jmp     loc_1800F1846
0x1800f1479  mov     eax, 2Eh ; '.'
0x1800f147e  mov     [rbp+230h+var_288], ax
0x1800f1482  mov     rax, 70006D0074h
0x1800f148c  mov     [rbp+230h+var_286], rax
0x1800f1490  xor     eax, eax
0x1800f1492  mov     [rbp+230h+var_27E], rax
0x1800f1496  mov     [rbp+230h+var_276], ax
0x1800f149a  lea     esi, [rax+1]
0x1800f149d  test    rdi, rdi
0x1800f14a0  jz      loc_1800F1535
0x1800f14a6  cmp     [rdi], r11w
0x1800f14aa  jz      loc_1800F1535
0x1800f14b0  lea     eax, [rsi+2]
0x1800f14b3  lea     r8d, [rsi+8]
0x1800f14b7  lea     r9, [rbp+230h+var_286]
0x1800f14bb  test    rax, rax
0x1800f14be  jz      short loc_1800F14DC
0x1800f14c0  movzx   ecx, word ptr [rdi]
0x1800f14c3  test    cx, cx
0x1800f14c6  jz      short loc_1800F14DC
0x1800f14c8  mov     [r9], cx
0x1800f14cc  add     rdi, 2
0x1800f14d0  add     r9, 2
0x1800f14d4  sub     rax, rsi
0x1800f14d7  sub     r8, rsi
0x1800f14da  jnz     short loc_1800F14BB
0x1800f14dc  mov     rax, r8
0x1800f14df  lea     rcx, [r9-2]
0x1800f14e3  neg     rax
0x1800f14e6  sbb     edi, edi
0x1800f14e8  not     edi
0x1800f14ea  and     edi, 8007007Ah
0x1800f14f0  test    r8, r8
0x1800f14f3  cmovnz  rcx, r9
0x1800f14f7  mov     [rcx], r11w
0x1800f14fb  jnz     short loc_1800F1535
0x1800f14fd  mov     rax, [rbx]
0x1800f1500  mov     rcx, rbx
0x1800f1503  mov     rax, [rax+50h]
0x1800f1507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f150c  mov     edx, edi; int
0x1800f150e  mov     r8, rax; unsigned __int16 *
0x1800f1511  mov     ecx, 538h; int
0x1800f1516  call    ?PostError@@YAPEAVIMsiRecord@@HHPEBG@Z; PostError(int,int,ushort const *)
0x1800f151b  mov     rdi, rax
0x1800f151e  mov     rcx, [rbx]
0x1800f1521  mov     rax, [rcx+10h]
0x1800f1525  mov     rcx, rbx
0x1800f1528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f152d  mov     rax, rdi
0x1800f1530  jmp     loc_1800F1938
0x1800f1535  mov     edi, 8
0x1800f153a  mov     [rsp+330h+var_2D0], r11d
0x1800f153f  cmp     r13d, edi
0x1800f1542  mov     r10d, edi
0x1800f1545  cmovg   r13d, edi
0x1800f1549  sub     r10d, r13d
0x1800f154c  cmp     cs:byte_18030A82A, r11b
0x1800f1553  mov     [rsp+330h+var_2CC], r10d
0x1800f1558  jnz     short loc_1800F1574
0x1800f155a  call    cs:__imp_GetTickCount
0x1800f1560  mov     r10d, [rsp+330h+var_2CC]
0x1800f1565  xor     r11d, r11d
0x1800f1568  mov     r15d, eax
0x1800f156b  mov     cs:byte_18030A82A, sil
0x1800f1572  jmp     short loc_1800F157B
0x1800f1574  mov     r15d, cs:dword_18030B3C8
0x1800f157b  lea     eax, [r15+1]
0x1800f157f  mov     cs:dword_18030B3C8, eax
0x1800f1585  test    r13d, r13d
0x1800f1588  jz      short loc_1800F159B
0x1800f158a  lea     ecx, ds:0[r10*4]
0x1800f1592  mov     eax, esi
0x1800f1594  shl     eax, cl
0x1800f1596  sub     eax, esi
0x1800f1598  and     r15d, eax
0x1800f159b  cmp     r10d, edi
0x1800f159e  jnz     short loc_1800F15A5
0x1800f15a0  or      eax, 0FFFFFFFFh
0x1800f15a3  jmp     short loc_1800F15B3
0x1800f15a5  lea     ecx, ds:0[r10*4]
0x1800f15ad  mov     eax, esi
0x1800f15af  shl     eax, cl
0x1800f15b1  sub     eax, esi
0x1800f15b3  mov     [rsp+330h+var_2C0], eax
0x1800f15b7  lea     r12, aNull; "(NULL)"
0x1800f15be  mov     ecx, r11d
0x1800f15c1  mov     [rsp+330h+var_2BC], ecx
0x1800f15c5  cmp     ecx, eax
0x1800f15c7  ja      loc_1800F1842
0x1800f15cd  mov     rax, [rbp+230h+var_298]
0x1800f15d1  test    rax, rax
0x1800f15d4  jz      short loc_1800F15F4
0x1800f15d6  movsxd  r9, r13d; unsigned __int64
0x1800f15d9  lea     rcx, [rbp+230h+var_270]; unsigned __int16 *
0x1800f15dd  mov     r8, rax; unsigned __int16 *
0x1800f15e0  mov     edx, 9; unsigned __int64
0x1800f15e5  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800f15ea  mov     edi, eax
0x1800f15ec  test    eax, eax
0x1800f15ee  js      loc_1800F14FD
0x1800f15f4  test    r10d, r10d
0x1800f15f7  jz      short loc_1800F1625
0x1800f15f9  movsxd  rax, r13d
0x1800f15fc  lea     rcx, [rbp+230h+var_270]
0x1800f1600  mov     edx, 9
0x1800f1605  lea     r8, asc_180284574; "%x"
0x1800f160c  sub     rdx, rax; unsigned __int64
0x1800f160f  mov     r9d, r15d
0x1800f1612  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x1800f1616  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800f161b  mov     edi, eax
0x1800f161d  test    eax, eax
0x1800f161f  js      loc_1800F14FD
0x1800f1625  mov     rax, [rbx]
0x1800f1628  mov     rcx, rbx
0x1800f162b  mov     edi, 7FFFFFFEh
0x1800f1630  mov     rax, [rax+50h]
0x1800f1634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1639  mov     r10d, 104h
0x1800f163f  lea     r8, [rbp+230h+TempFileName]
0x1800f1643  mov     edx, r10d
0x1800f1646  xor     r9d, r9d
0x1800f1649  test    rdi, rdi
0x1800f164c  jz      short loc_1800F166A
0x1800f164e  movzx   ecx, word ptr [rax]
0x1800f1651  test    cx, cx
0x1800f1654  jz      short loc_1800F166A
0x1800f1656  mov     [r8], cx
0x1800f165a  add     rax, 2
0x1800f165e  add     r8, 2
0x1800f1662  sub     rdi, rsi
0x1800f1665  sub     rdx, rsi
0x1800f1668  jnz     short loc_1800F1649
  ... truncated ...
```
