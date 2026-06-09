# CMsiPath::TempFolderOrFile(Bool,ushort const *,ushort const *,Bool,_SECURITY_ATTRIBUTES *,IMsiString const * &)

- ea: `0x1800fa4d0`
- end: `0x1800facc9`
- name: `?TempFolderOrFile@CMsiPath@@IEAAPEAVIMsiRecord@@W4Bool@@PEBG10PEAU_SECURITY_ATTRIBUTES@@AEAPEBVIMsiString@@@Z`
- size: `2041`
- prototype: `struct IMsiRecord *__high(enum Bool, const unsigned __int16 *, const unsigned __int16 *, enum Bool, struct _SECURITY_ATTRIBUTES *, const struct IMsiString **)`
- caller_count: `2`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800fa480`
- `0x180220050`

## callees

- `0x18000c4bc`
- `0x180010ac0`
- `0x180013fe4`
- `0x1800141e0`
- `0x180014528`
- `0x18005a250`
- `0x180067fec`
- `0x18007adb4`
- `0x18007ced0`
- `0x18007f4c8`
- `0x18008c93c`
- `0x180095874`
- `0x180097c78`
- `0x18009cdb8`
- `0x18009d06c`
- `0x1800fa4d0`
- `0x18013fa30`
- `0x180153524`
- `0x180153e68`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `ADVAPI32!SetFileSecurityW` at `0x1800fa668`
- `ADVAPI32!SetFileSecurityW` at `0x1800fa668`
- `KERNEL32!CloseHandle` at `0x1800fa6d5`
- `KERNEL32!CloseHandle` at `0x1800fa740`
- `KERNEL32!CloseHandle` at `0x1800faaaa`
- `KERNEL32!CloseHandle` at `0x1800fab0a`
- `KERNEL32!CloseHandle` at `0x1800fa6d5`
- `KERNEL32!CloseHandle` at `0x1800fa740`
- `KERNEL32!CloseHandle` at `0x1800faaaa`
- `KERNEL32!CloseHandle` at `0x1800fab0a`
- `KERNEL32!GetTickCount` at `0x1800fa889`
- `KERNEL32!GetTickCount` at `0x1800fa889`
- `KERNEL32!GetLastError` at `0x1800fa5d3`
- `KERNEL32!GetLastError` at `0x1800fa761`
- `KERNEL32!GetLastError` at `0x1800fab27`
- `KERNEL32!GetLastError` at `0x1800fa5d3`
- `KERNEL32!GetLastError` at `0x1800fa761`
- `KERNEL32!GetLastError` at `0x1800fab27`
- `KERNEL32!SetLastError` at `0x1800fa751`
- `KERNEL32!SetLastError` at `0x1800fab1b`
- `KERNEL32!SetLastError` at `0x1800fa751`
- `KERNEL32!SetLastError` at `0x1800fab1b`
- `KERNEL32!lstrlenW` at `0x1800fa54f`
- `KERNEL32!lstrlenW` at `0x1800fa54f`
- `KERNEL32!CreateFileW` at `0x1800fa6a3`
- `KERNEL32!CreateFileW` at `0x1800faa78`
- `KERNEL32!CreateFileW` at `0x1800fa6a3`
- `KERNEL32!CreateFileW` at `0x1800faa78`
- `KERNEL32!CreateDirectoryW` at `0x1800faa23`
- `KERNEL32!CreateDirectoryW` at `0x1800faa23`
- `KERNEL32!GetFileType` at `0x1800fa6bf`
- `KERNEL32!GetFileType` at `0x1800faa94`
- `KERNEL32!GetFileType` at `0x1800fa6bf`
- `KERNEL32!GetFileType` at `0x1800faa94`
- `KERNEL32!GetTempFileNameW` at `0x1800fa5c0`
- `KERNEL32!GetTempFileNameW` at `0x1800fa5c0`

## string_xrefs

- `0x1800fa70c`: `Error: This is not a valid file, hence failing to create: %s`
- `0x1800faacd`: `Error: This is not a valid file, hence failing to create: %s`

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
  bool v20; // di
  const WCHAR *v21; // rdx
  int v22; // esi
  int v23; // eax
  bool v24; // cl
  LPSECURITY_ATTRIBUTES v25; // r13
  __int64 v26; // r8
  void *lpSecurityDescriptor; // rdi
  SECURITY_INFORMATION SecurityInformation; // eax
  HANDLE v29; // rax
  void *v30; // rdi
  BOOL v31; // edi
  __int64 v32; // rax
  _WORD *v33; // rcx
  signed int v34; // edi
  const unsigned __int16 *v35; // rax
  int v36; // edx
  struct IMsiRecord *v37; // rdi
  int v39; // r10d
  DWORD TickCount; // eax
  unsigned int v41; // r15d
  unsigned int v42; // eax
  unsigned int i; // ecx
  __int64 v44; // rdi
  _WORD *v45; // rax
  _WORD *v46; // rcx
  bool v48; // cl
  HANDLE FileW; // rax
  void *v50; // rdi
  const struct IMsiString **v51; // rax
  __int64 v52; // rdi
  void *v53; // rcx
  int v54; // [rsp+60h] [rbp-A0h]
  int v55; // [rsp+64h] [rbp-9Ch] BYREF
  void *v56; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v57; // [rsp+70h] [rbp-90h]
  unsigned int v58; // [rsp+74h] [rbp-8Ch]
  int v59; // [rsp+78h] [rbp-88h]
  _QWORD *v60; // [rsp+80h] [rbp-80h]
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+88h] [rbp-78h] BYREF
  int v62; // [rsp+90h] [rbp-70h]
  unsigned __int16 *v63; // [rsp+98h] [rbp-68h] BYREF
  _QWORD *v64; // [rsp+A0h] [rbp-60h]
  unsigned __int16 v65; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v66[2]; // [rsp+AAh] [rbp-56h] BYREF
  __int16 v67; // [rsp+BAh] [rbp-46h]
  unsigned __int16 v68[16]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR TempFileName[264]; // [rsp+E0h] [rbp-20h] BYREF

  lpSecurityAttributes = a6;
  v64 = a7;
  v10 = a1;
  v11 = *a1;
  v63 = a3;
  v62 = a2;
  v60 = a1;
  v13 = (*(__int64 (__fastcall **)(_QWORD *))(v11 + 56))(a1);
  v59 = 0;
  LastError = 0;
  if ( a3 )
    v17 = lstrlenW(a3);
  else
    v17 = 0;
  if ( a2 || v17 >= 4 || a4 && *a4 )
  {
    v65 = 46;
    v66[0] = 0x70006D0074LL;
    v66[1] = 0;
    v67 = 0;
    if ( a4 && *a4 )
    {
      v32 = 3;
      v14 = 9;
      v15 = v66;
      do
      {
        if ( !v32 )
          break;
        if ( !*a4 )
          break;
        *v15++ = *a4++;
        --v32;
        --v14;
      }
      while ( v14 );
      v33 = v15 - 1;
      v34 = v14 == 0 ? 0x8007007A : 0;
      if ( v14 )
        v33 = v15;
      *v33 = 0;
      if ( !v14 )
      {
LABEL_45:
        v35 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 80LL))(v13);
        v36 = v34;
        goto LABEL_46;
      }
    }
    v54 = 0;
    if ( v17 > 8 )
      v17 = 8;
    v39 = 8 - v17;
    v55 = 8 - v17;
    if ( byte_1803147FA )
    {
      v41 = dword_180315398;
    }
    else
    {
      TickCount = GetTickCount();
      v39 = v55;
      v41 = TickCount;
      byte_1803147FA = 1;
    }
    dword_180315398 = v41 + 1;
    if ( v17 )
      v41 &= (1 << (4 * v39)) - 1;
    if ( v39 == 8 )
      v42 = -1;
    else
      v42 = (1 << (4 * v39)) - 1;
    v57 = v42;
    for ( i = 0; ; i = v58 + 1 )
    {
      v58 = i;
      if ( i > v42 )
      {
        v31 = v54;
        goto LABEL_100;
      }
      if ( v63 )
      {
        v34 = StringCchCopyNW(v68, 9u, v63, v17);
        if ( v34 < 0 )
          goto LABEL_45;
      }
      if ( v39 )
      {
        v34 = StringCchPrintfW(&v68[v17], 9LL - v17, L"%x", v41);
        if ( v34 < 0 )
          goto LABEL_45;
      }
      v44 = 2147483646;
      v45 = (_WORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 80LL))(v13);
      v14 = (__int64)TempFileName;
      v12 = 260;
      v15 = 0;
      do
      {
        if ( !v44 )
          break;
        if ( !*v45 )
          break;
        *(_WORD *)v14 = *v45++;
        v14 += 2;
        --v44;
        --v12;
      }
      while ( v12 );
      v46 = (_WORD *)(v14 - 2);
      if ( v12 )
        v46 = (_WORD *)v14;
      *v46 = 0;
      if ( !v12
        || (int)StringCchCatW(TempFileName, 0x104u, v68) < 0
        || (int)StringCchCatW(TempFileName, 0x104u, &v65) < 0 )
      {
        goto LABEL_98;
      }
      if ( !(v62
           ? CMsiPath::FFolderExists(v60, TempFileName)
           : (unsigned int)FFileExists(TempFileName, v12, *((unsigned int *)v60 + 12))) )
        break;
LABEL_94:
      ++dword_180315398;
      v42 = v57;
      if ( v41 == v57 )
        v41 = 0;
      else
        ++v41;
      v39 = v55;
    }
    if ( *((_DWORD *)v60 + 12) )
      StartImpersonating();
    if ( v62 )
    {
      if ( CreateDirectoryW(TempFileName, lpSecurityAttributes) )
      {
LABEL_80:
        LastError = 0;
        v54 = 1;
        v31 = 1;
        goto LABEL_89;
      }
    }
    else
    {
      FileW = CreateFileW(TempFileName, 0x40000000u, 1u, lpSecurityAttributes, 1u, 0x100080u, 0);
      v50 = FileW;
      if ( FileW != (HANDLE)-1LL )
      {
        if ( GetFileType(FileW) - 2 > 1 )
        {
          CloseHandle(v50);
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
        CloseHandle(v50);
        SetLastError(0x6Eu);
      }
    }
    v31 = v54;
    LastError = GetLastError();
LABEL_89:
    if ( *((_DWORD *)v60 + 12) )
      StopImpersonating(v48);
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
    LOBYTE(v26) = v20;
    CRefCountedTokenPrivileges::CRefCountedTokenPrivileges(&v55, 1, v26);
    lpSecurityDescriptor = v25->lpSecurityDescriptor;
    SecurityInformation = GetSecurityInformation(lpSecurityDescriptor);
    if ( SetFileSecurityW(TempFileName, SecurityInformation, lpSecurityDescriptor) )
    {
      v29 = CreateFileW(TempFileName, 0x40000000u, 0, 0, 5u, 0x100000u, 0);
      v30 = v29;
      if ( v29 != (HANDLE)-1LL )
      {
        if ( GetFileType(v29) - 2 > 1 )
        {
          CloseHandle(v30);
          v22 = 0;
LABEL_31:
          CRefCountedTokenPrivileges::~CRefCountedTokenPrivileges((CRefCountedTokenPrivileges *)&v55);
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
          v10 = v60;
        }
        CloseHandle(v30);
        SetLastError(0x6Eu);
      }
      v59 = 1;
    }
    LastError = GetLastError();
    goto LABEL_31;
  }
  PostError(1501);
  LastError = 5;
LABEL_33:
  if ( *((_DWORD *)v10 + 12) )
    StopImpersonating(v24);
  v31 = v22 == 0;
LABEL_100:
  if ( !v31 )
  {
    if ( !LastError )
      LastError = 80;
    if ( v59 && LastError == 5 )
    {
      v51 = (const struct IMsiString **)MsiString::MsiString((MsiString *)&v63, TempFileName);
      v37 = PostError(1304, *v51);
      (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v63 + 16LL))(v63);
      goto LABEL_47;
    }
LABEL_98:
    v35 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64, __int64, __int64, _WORD *))(*(_QWORD *)v13 + 80LL))(
                                      v13,
                                      v12,
                                      v14,
                                      v15);
    v36 = LastError;
LABEL_46:
    v37 = PostError(1336, v36, v35);
LABEL_47:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    return v37;
  }
  v56 = &MsiString::s_NullString;
  (*(void (__fastcall **)(void *, WCHAR *, void **))(MsiString::s_NullString + 96LL))(
    &MsiString::s_NullString,
    TempFileName,
    &v56);
  if ( a5 )
  {
    v52 = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)v56 + 176LL))(v56, 6, 92);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v56 + 16LL))(v56);
    v56 = (void *)v52;
  }
  else
  {
    v52 = (__int64)v56;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 8LL))(v52);
  v53 = v56;
  *v64 = v56;
  (*(void (__fastcall **)(void *))(*(_QWORD *)v53 + 16LL))(v53);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  return 0;
}

```

## disassembly

```asm
0x1800fa4d0  mov     [rsp-8+arg_8], rbx
0x1800fa4d5  push    rbp
0x1800fa4d6  push    rsi
0x1800fa4d7  push    rdi
0x1800fa4d8  push    r12
0x1800fa4da  push    r13
0x1800fa4dc  push    r14
0x1800fa4de  push    r15
0x1800fa4e0  lea     rbp, [rsp-200h]
0x1800fa4e8  sub     rsp, 300h
0x1800fa4ef  mov     rax, cs:__security_cookie
0x1800fa4f6  xor     rax, rsp
0x1800fa4f9  mov     [rbp+230h+var_40], rax
0x1800fa500  mov     rax, [rbp+230h+arg_28]
0x1800fa507  mov     rdi, r9
0x1800fa50a  mov     [rbp+230h+lpSecurityAttributes], rax
0x1800fa50e  mov     rsi, r8
0x1800fa511  mov     rax, [rbp+230h+arg_30]
0x1800fa518  mov     r15d, edx
0x1800fa51b  mov     [rbp+230h+var_290], rax
0x1800fa51f  mov     r12, rcx
0x1800fa522  mov     rax, [rcx]
0x1800fa525  mov     [rbp+230h+var_298], r8
0x1800fa529  mov     [rbp+230h+var_2A0], edx
0x1800fa52c  mov     [rbp+230h+var_2B0], rcx
0x1800fa530  mov     rax, [rax+38h]
0x1800fa534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa539  xor     r11d, r11d
0x1800fa53c  mov     rbx, rax
0x1800fa53f  mov     [rsp+330h+var_2B8], r11d
0x1800fa544  mov     r14d, r11d
0x1800fa547  test    rsi, rsi
0x1800fa54a  jz      short loc_1800FA563
0x1800fa54c  mov     rcx, rsi; lpString
0x1800fa54f  call    cs:__imp_lstrlenW
0x1800fa556  nop     dword ptr [rax+rax+00h]
0x1800fa55b  mov     r13d, eax
0x1800fa55e  xor     r11d, r11d
0x1800fa561  jmp     short loc_1800FA566
0x1800fa563  mov     r13d, r11d
0x1800fa566  test    r15d, r15d
0x1800fa569  jnz     loc_1800FA7A8
0x1800fa56f  cmp     r13d, 4
0x1800fa573  jge     loc_1800FA7A8
0x1800fa579  test    rdi, rdi
0x1800fa57c  jz      short loc_1800FA588
0x1800fa57e  cmp     [rdi], r11w
0x1800fa582  jnz     loc_1800FA7A8
0x1800fa588  mov     r15d, r11d
0x1800fa58b  cmp     [r12+30h], r11d
0x1800fa590  jz      short loc_1800FA597
0x1800fa592  call    ?StartImpersonating@@YA_NXZ; StartImpersonating(void)
0x1800fa597  mov     rax, [rbx]
0x1800fa59a  mov     rcx, rbx
0x1800fa59d  mov     rax, [rax+50h]
0x1800fa5a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa5a6  xor     edi, edi
0x1800fa5a8  lea     rdx, Default
0x1800fa5af  test    rsi, rsi
0x1800fa5b2  lea     r9, [rbp+230h+TempFileName]; lpTempFileName
0x1800fa5b6  mov     rcx, rax; lpPathName
0x1800fa5b9  cmovnz  rdx, rsi; lpPrefixString
0x1800fa5bd  xor     r8d, r8d; uUnique
0x1800fa5c0  call    cs:__imp_GetTempFileNameW
0x1800fa5c7  nop     dword ptr [rax+rax+00h]
0x1800fa5cc  lea     esi, [rdi+1]
0x1800fa5cf  test    eax, eax
0x1800fa5d1  jnz     short loc_1800FA5E5
0x1800fa5d3  call    cs:__imp_GetLastError
0x1800fa5da  nop     dword ptr [rax+rax+00h]
0x1800fa5df  mov     r14d, eax
0x1800fa5e2  mov     r15d, esi
0x1800fa5e5  call    ?RunningAsLocalSystem@@YA?AW4TRI@@XZ; RunningAsLocalSystem(void)
0x1800fa5ea  cmp     eax, 0FFFFFFFFh
0x1800fa5ed  jnz     short loc_1800FA607
0x1800fa5ef  mov     ecx, 5DDh; int
0x1800fa5f4  call    ?PostError@@YAPEAVIMsiRecord@@H@Z; PostError(int)
0x1800fa5f9  mov     r14d, 5
0x1800fa5ff  xor     r11d, r11d
0x1800fa602  jmp     loc_1800FA78B
0x1800fa607  xor     r11d, r11d
0x1800fa60a  test    r15d, r15d
0x1800fa60d  jnz     loc_1800FA788
0x1800fa613  mov     r13, [rbp+230h+lpSecurityAttributes]
0x1800fa617  test    r13, r13
0x1800fa61a  jz      loc_1800FA788
0x1800fa620  cmp     [r13+8], r11
0x1800fa624  jz      loc_1800FA788
0x1800fa62a  cmp     eax, esi
0x1800fa62c  jnz     short loc_1800FA638
0x1800fa62e  cmp     [r12+30h], r11d
0x1800fa633  jnz     short loc_1800FA638
0x1800fa635  mov     dil, sil
0x1800fa638  mov     dl, dil; bool
0x1800fa63b  lea     rcx, [rbp+230h+lpSecurityAttributes]; this
0x1800fa63f  call    ??0CElevate@@QEAA@_N@Z; CElevate::CElevate(bool)
0x1800fa644  mov     r8b, dil
0x1800fa647  lea     rcx, [rsp+330h+var_2CC]
0x1800fa64c  mov     edx, esi
0x1800fa64e  call    ??0CRefCountedTokenPrivileges@@QEAA@W4itkpEnum@@_N@Z; CRefCountedTokenPrivileges::CRefCountedTokenPrivileges(itkpEnum,bool)
0x1800fa653  mov     rdi, [r13+8]
0x1800fa657  mov     rcx, rdi; pSecurityDescriptor
0x1800fa65a  call    ?GetSecurityInformation@@YAKPEAX@Z; GetSecurityInformation(void *)
0x1800fa65f  mov     r8, rdi; pSecurityDescriptor
0x1800fa662  lea     rcx, [rbp+230h+TempFileName]; lpFileName
0x1800fa666  mov     edx, eax; SecurityInformation
0x1800fa668  call    cs:__imp_SetFileSecurityW
0x1800fa66f  nop     dword ptr [rax+rax+00h]
0x1800fa674  xor     r13d, r13d
0x1800fa677  test    eax, eax
0x1800fa679  jz      loc_1800FA761
0x1800fa67f  mov     [rsp+330h+hTemplateFile], r13; hTemplateFile
0x1800fa684  lea     rcx, [rbp+230h+TempFileName]; lpFileName
0x1800fa688  mov     [rsp+330h+dwFlagsAndAttributes], 100000h; dwFlagsAndAttributes
0x1800fa690  xor     r9d, r9d; lpSecurityAttributes
0x1800fa693  xor     r8d, r8d; dwShareMode
0x1800fa696  mov     [rsp+330h+dwCreationDisposition], 5; dwCreationDisposition
0x1800fa69e  mov     edx, 40000000h; dwDesiredAccess
0x1800fa6a3  call    cs:__imp_CreateFileW
0x1800fa6aa  nop     dword ptr [rax+rax+00h]
0x1800fa6af  mov     rdi, rax
0x1800fa6b2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800fa6b6  jz      loc_1800FA75D
0x1800fa6bc  mov     rcx, rax; hFile
0x1800fa6bf  call    cs:__imp_GetFileType
0x1800fa6c6  nop     dword ptr [rax+rax+00h]
0x1800fa6cb  add     eax, 0FFFFFFFEh
0x1800fa6ce  cmp     eax, esi
0x1800fa6d0  jbe     short loc_1800FA6E9
0x1800fa6d2  mov     rcx, rdi; hObject
0x1800fa6d5  call    cs:__imp_CloseHandle
0x1800fa6dc  nop     dword ptr [rax+rax+00h]
0x1800fa6e1  mov     esi, r15d
0x1800fa6e4  jmp     loc_1800FA770
0x1800fa6e9  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x1800fa6f0  jz      short loc_1800FA73D
0x1800fa6f2  mov     [rsp+330h+var_2D8], r13; void *
0x1800fa6f7  lea     r12, aNull; "(NULL)"
0x1800fa6fe  mov     [rsp+330h+var_2E0], r13d; unsigned int
0x1800fa703  lea     rax, [rbp+230h+TempFileName]
0x1800fa707  mov     [rsp+330h+var_2E8], r12; unsigned __int16 *
0x1800fa70c  lea     r9, aErrorThisIsNot; "Error: This is not a valid file, hence "...
0x1800fa713  mov     [rsp+330h+var_2F0], r12; unsigned __int16 *
0x1800fa718  xor     edx, edx; unsigned __int16
0x1800fa71a  mov     [rsp+330h+var_2F8], r12; unsigned __int16 *
0x1800fa71f  xor     r8d, r8d; int
0x1800fa722  mov     [rsp+330h+hTemplateFile], r12; unsigned __int16 *
0x1800fa727  mov     qword ptr [rsp+330h+dwFlagsAndAttributes], r12; unsigned __int16 *
0x1800fa72c  lea     ecx, [rdx+9]; int
0x1800fa72f  mov     qword ptr [rsp+330h+dwCreationDisposition], rax; unsigned __int16 *
0x1800fa734  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800fa739  mov     r12, [rbp+230h+var_2B0]
0x1800fa73d  mov     rcx, rdi; hObject
0x1800fa740  call    cs:__imp_CloseHandle
0x1800fa747  nop     dword ptr [rax+rax+00h]
0x1800fa74c  mov     ecx, 6Eh ; 'n'; dwErrCode
0x1800fa751  call    cs:__imp_SetLastError
0x1800fa758  nop     dword ptr [rax+rax+00h]
0x1800fa75d  mov     [rsp+330h+var_2B8], esi
0x1800fa761  call    cs:__imp_GetLastError
0x1800fa768  nop     dword ptr [rax+rax+00h]
0x1800fa76d  mov     r14d, eax
0x1800fa770  lea     rcx, [rsp+330h+var_2CC]; this
0x1800fa775  call    ??1CRefCountedTokenPrivileges@@QEAA@XZ; CRefCountedTokenPrivileges::~CRefCountedTokenPrivileges(void)
0x1800fa77a  lea     rcx, [rbp+230h+lpSecurityAttributes]; this
0x1800fa77e  call    ??1CElevate@@QEAA@XZ; CElevate::~CElevate(void)
0x1800fa783  jmp     loc_1800FA5FF
0x1800fa788  mov     esi, r15d
0x1800fa78b  cmp     [r12+30h], r11d
0x1800fa790  jz      short loc_1800FA79A
0x1800fa792  call    ?StopImpersonating@@YAX_N@Z; StopImpersonating(bool)
0x1800fa797  xor     r11d, r11d
0x1800fa79a  test    esi, esi
0x1800fa79c  mov     edi, r11d
0x1800fa79f  setz    dil
0x1800fa7a3  jmp     loc_1800FABAC
0x1800fa7a8  mov     eax, 2Eh ; '.'
0x1800fa7ad  mov     [rbp+230h+var_288], ax
0x1800fa7b1  mov     rax, 70006D0074h
0x1800fa7bb  mov     [rbp+230h+var_286], rax
0x1800fa7bf  xor     eax, eax
0x1800fa7c1  mov     [rbp+230h+var_27E], rax
0x1800fa7c5  mov     [rbp+230h+var_276], ax
0x1800fa7c9  lea     esi, [rax+1]
0x1800fa7cc  test    rdi, rdi
0x1800fa7cf  jz      loc_1800FA864
0x1800fa7d5  cmp     [rdi], r11w
0x1800fa7d9  jz      loc_1800FA864
0x1800fa7df  lea     eax, [rsi+2]
0x1800fa7e2  lea     r8d, [rsi+8]
0x1800fa7e6  lea     r9, [rbp+230h+var_286]
0x1800fa7ea  test    rax, rax
0x1800fa7ed  jz      short loc_1800FA80B
0x1800fa7ef  movzx   ecx, word ptr [rdi]
0x1800fa7f2  test    cx, cx
0x1800fa7f5  jz      short loc_1800FA80B
0x1800fa7f7  mov     [r9], cx
0x1800fa7fb  add     rdi, 2
0x1800fa7ff  add     r9, 2
0x1800fa803  sub     rax, rsi
0x1800fa806  sub     r8, rsi
0x1800fa809  jnz     short loc_1800FA7EA
0x1800fa80b  mov     rax, r8
0x1800fa80e  lea     rcx, [r9-2]
0x1800fa812  neg     rax
0x1800fa815  sbb     edi, edi
0x1800fa817  not     edi
0x1800fa819  and     edi, 8007007Ah
0x1800fa81f  test    r8, r8
0x1800fa822  cmovnz  rcx, r9
0x1800fa826  mov     [rcx], r11w
0x1800fa82a  jnz     short loc_1800FA864
0x1800fa82c  mov     rax, [rbx]
0x1800fa82f  mov     rcx, rbx
0x1800fa832  mov     rax, [rax+50h]
0x1800fa836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa83b  mov     edx, edi; int
0x1800fa83d  mov     r8, rax; unsigned __int16 *
0x1800fa840  mov     ecx, 538h; int
0x1800fa845  call    ?PostError@@YAPEAVIMsiRecord@@HHPEBG@Z; PostError(int,int,ushort const *)
0x1800fa84a  mov     rdi, rax
0x1800fa84d  mov     rcx, [rbx]
0x1800fa850  mov     rax, [rcx+10h]
0x1800fa854  mov     rcx, rbx
0x1800fa857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa85c  mov     rax, rdi
0x1800fa85f  jmp     loc_1800FAC9E
0x1800fa864  mov     edi, 8
0x1800fa869  mov     [rsp+330h+var_2D0], r11d
0x1800fa86e  cmp     r13d, edi
0x1800fa871  mov     r10d, edi
0x1800fa874  cmovg   r13d, edi
0x1800fa878  sub     r10d, r13d
0x1800fa87b  cmp     cs:byte_1803147FA, r11b
0x1800fa882  mov     [rsp+330h+var_2CC], r10d
0x1800fa887  jnz     short loc_1800FA8A9
0x1800fa889  call    cs:__imp_GetTickCount
0x1800fa890  nop     dword ptr [rax+rax+00h]
0x1800fa895  mov     r10d, [rsp+330h+var_2CC]
0x1800fa89a  xor     r11d, r11d
0x1800fa89d  mov     r15d, eax
0x1800fa8a0  mov     cs:byte_1803147FA, sil
0x1800fa8a7  jmp     short loc_1800FA8B0
0x1800fa8a9  mov     r15d, cs:dword_180315398
0x1800fa8b0  lea     eax, [r15+1]
0x1800fa8b4  mov     cs:dword_180315398, eax
0x1800fa8ba  test    r13d, r13d
0x1800fa8bd  jz      short loc_1800FA8D0
0x1800fa8bf  lea     ecx, ds:0[r10*4]
0x1800fa8c7  mov     eax, esi
0x1800fa8c9  shl     eax, cl
0x1800fa8cb  sub     eax, esi
0x1800fa8cd  and     r15d, eax
0x1800fa8d0  cmp     r10d, edi
0x1800fa8d3  jnz     short loc_1800FA8DA
0x1800fa8d5  or      eax, 0FFFFFFFFh
0x1800fa8d8  jmp     short loc_1800FA8E8
0x1800fa8da  lea     ecx, ds:0[r10*4]
0x1800fa8e2  mov     eax, esi
0x1800fa8e4  shl     eax, cl
0x1800fa8e6  sub     eax, esi
0x1800fa8e8  mov     [rsp+330h+var_2C0], eax
0x1800fa8ec  lea     r12, aNull; "(NULL)"
0x1800fa8f3  mov     ecx, r11d
0x1800fa8f6  mov     [rsp+330h+var_2BC], ecx
0x1800fa8fa  cmp     ecx, eax
0x1800fa8fc  ja      loc_1800FABA8
0x1800fa902  mov     rax, [rbp+230h+var_298]
0x1800fa906  test    rax, rax
0x1800fa909  jz      short loc_1800FA929
0x1800fa90b  movsxd  r9, r13d; unsigned __int64
0x1800fa90e  lea     rcx, [rbp+230h+var_270]; unsigned __int16 *
0x1800fa912  mov     r8, rax; unsigned __int16 *
0x1800fa915  mov     edx, 9; unsigned __int64
0x1800fa91a  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800fa91f  mov     edi, eax
0x1800fa921  test    eax, eax
0x1800fa923  js      loc_1800FA82C
0x1800fa929  test    r10d, r10d
0x1800fa92c  jz      short loc_1800FA95A
0x1800fa92e  movsxd  rax, r13d
0x1800fa931  lea     rcx, [rbp+230h+var_270]
0x1800fa935  mov     edx, 9
0x1800fa93a  lea     r8, asc_18028E88C; "%x"
0x1800fa941  sub     rdx, rax; unsigned __int64
0x1800fa944  mov     r9d, r15d
0x1800fa947  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x1800fa94b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800fa950  mov     edi, eax
0x1800fa952  test    eax, eax
0x1800fa954  js      loc_1800FA82C
0x1800fa95a  mov     rax, [rbx]
0x1800fa95d  mov     rcx, rbx
0x1800fa960  mov     edi, 7FFFFFFEh
0x1800fa965  mov     rax, [rax+50h]
0x1800fa969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa96e  mov     r10d, 104h
0x1800fa974  lea     r8, [rbp+230h+TempFileName]
0x1800fa978  mov     edx, r10d
0x1800fa97b  xor     r9d, r9d
  ... truncated ...
```
