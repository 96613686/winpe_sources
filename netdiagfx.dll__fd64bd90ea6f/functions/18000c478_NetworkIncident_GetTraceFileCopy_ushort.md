# NetworkIncident::GetTraceFileCopy(ushort * *)

- ea: `0x18000c478`
- end: `0x18000cac7`
- name: `?GetTraceFileCopy@NetworkIncident@@QEAAJPEAPEAG@Z`
- size: `1615`
- prototype: `__int64 __fastcall(NetworkIncident *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001b094`

## callees

- `0x18000579c`
- `0x180006d58`
- `0x180006fa0`
- `0x180007014`
- `0x180007ce8`
- `0x180008754`
- `0x180008e6c`
- `0x180008efc`
- `0x1800095a4`
- `0x180009df0`
- `0x18000bca0`
- `0x18000bcd0`
- `0x18000c18c`
- `0x18000c454`
- `0x18000c478`
- `0x1800237a4`
- `0x180023880`
- `0x180023ac8`
- `0x18002c802`
- `0x18002c840`
- `0x18002f010`

## import_xrefs

- `msvcrt!_localtime64_s` at `0x18000c8d5`
- `msvcrt!_localtime64_s` at `0x18000c8d5`
- `KERNEL32!GetLastError` at `0x18000c54b`
- `KERNEL32!GetLastError` at `0x18000c5bd`
- `KERNEL32!GetLastError` at `0x18000c643`
- `KERNEL32!GetLastError` at `0x18000c7dc`
- `KERNEL32!GetLastError` at `0x18000c989`
- `KERNEL32!GetLastError` at `0x18000c54b`
- `KERNEL32!GetLastError` at `0x18000c5bd`
- `KERNEL32!GetLastError` at `0x18000c643`
- `KERNEL32!GetLastError` at `0x18000c7dc`
- `KERNEL32!GetLastError` at `0x18000c989`
- `KERNEL32!GetCurrentThread` at `0x18000c504`
- `KERNEL32!GetCurrentThread` at `0x18000c504`
- `KERNEL32!DeleteFileW` at `0x18000c747`
- `KERNEL32!DeleteFileW` at `0x18000c973`
- `KERNEL32!DeleteFileW` at `0x18000c747`
- `KERNEL32!DeleteFileW` at `0x18000c973`
- `KERNEL32!MoveFileW` at `0x18000c97f`
- `KERNEL32!MoveFileW` at `0x18000c97f`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x18000c83b`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x18000c9cd`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x18000c83b`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x18000c9cd`
- `ADVAPI32!OpenThreadToken` at `0x18000c522`
- `ADVAPI32!OpenThreadToken` at `0x18000c522`
- `ADVAPI32!CheckTokenMembership` at `0x18000c5a4`
- `ADVAPI32!CheckTokenMembership` at `0x18000c5a4`
- `SHLWAPI!PathFileExistsW` at `0x18000c8f4`
- `SHLWAPI!PathFileExistsW` at `0x18000c8f4`
- `SHELL32!SHGetFolderPathAndSubDirW` at `0x18000c6ac`
- `SHELL32!SHGetFolderPathAndSubDirW` at `0x18000c6ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ca21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ca21`

## pseudocode

```c
__int64 __fastcall NetworkIncident::GetTraceFileCopy(NetworkIncident *this, unsigned __int16 **a2)
{
  unsigned __int16 **v2; // r12
  NetworkIncident *v3; // r13
  int v4; // edi
  bool v5; // r14
  HANDLE CurrentThread; // rax
  signed int v7; // eax
  BOOL v8; // ebx
  signed int LastError; // eax
  signed int v10; // eax
  unsigned int v11; // r8d
  unsigned __int8 v12; // r9
  _QWORD *v13; // r14
  WCHAR *v14; // rbx
  int v15; // r15d
  const WCHAR *v16; // rax
  signed int v17; // eax
  struct _ACL *PACL; // rax
  signed int v19; // eax
  __time64_t *TickCount; // rax
  const __time64_t *v21; // rax
  int tm_sec; // edi
  int v23; // r15d
  WCHAR *v24; // r14
  signed int v25; // eax
  bool v26; // zf
  unsigned __int64 v27; // rdi
  unsigned __int16 *v28; // rax
  LPCWSTR pszSubDir; // [rsp+20h] [rbp-448h]
  WINBOOL IsMember[2]; // [rsp+48h] [rbp-420h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-418h] BYREF
  unsigned __int64 v33; // [rsp+58h] [rbp-410h] BYREF
  LPWSTR pObjectName; // [rsp+60h] [rbp-408h] BYREF
  NetworkIncident *v35; // [rsp+68h] [rbp-400h]
  void **v36; // [rsp+70h] [rbp-3F8h] BYREF
  HANDLE v37[2]; // [rsp+78h] [rbp-3F0h]
  __int64 v38; // [rsp+88h] [rbp-3E0h]
  _QWORD v39[2]; // [rsp+90h] [rbp-3D8h] BYREF
  char v40; // [rsp+A0h] [rbp-3C8h]
  int v41; // [rsp+A4h] [rbp-3C4h]
  __int128 v42; // [rsp+A8h] [rbp-3C0h]
  __int64 v43; // [rsp+B8h] [rbp-3B0h]
  int v44; // [rsp+C0h] [rbp-3A8h]
  WINBOOL *v45; // [rsp+C8h] [rbp-3A0h] BYREF
  WINBOOL *v46; // [rsp+D0h] [rbp-398h] BYREF
  _BYTE v47[8]; // [rsp+D8h] [rbp-390h] BYREF
  _BYTE v48[8]; // [rsp+E0h] [rbp-388h] BYREF
  WINBOOL *v49; // [rsp+E8h] [rbp-380h] BYREF
  struct tm Tm; // [rsp+F0h] [rbp-378h] BYREF
  void **v51; // [rsp+120h] [rbp-348h] BYREF
  _BYTE psidOwner[72]; // [rsp+128h] [rbp-340h] BYREF
  int v53; // [rsp+170h] [rbp-2F8h]
  _BYTE v54[8]; // [rsp+178h] [rbp-2F0h] BYREF
  _BYTE v55[8]; // [rsp+180h] [rbp-2E8h] BYREF
  _BYTE v56[8]; // [rsp+188h] [rbp-2E0h] BYREF
  _BYTE v57[16]; // [rsp+190h] [rbp-2D8h] BYREF
  _BYTE v58[8]; // [rsp+1A0h] [rbp-2C8h] BYREF
  _BYTE SidToCheck[120]; // [rsp+1A8h] [rbp-2C0h] BYREF
  WCHAR pszPath[264]; // [rsp+220h] [rbp-248h] BYREF

  v2 = a2;
  v3 = this;
  v35 = this;
  v33 = (unsigned __int64)a2;
  if ( a2 )
  {
    v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 56LL))(*((_QWORD *)this + 10));
    v5 = v4 == 0;
  }
  else
  {
    v4 = -2147024809;
    v5 = 0;
  }
  v36 = &ATL::CAccessToken::`vftable';
  *(_OWORD *)v37 = 0;
  v38 = 0;
  if ( v4 )
    goto LABEL_13;
  CurrentThread = GetCurrentThread();
  TokenHandle = 0;
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    ((void (__fastcall *)(void ***))v36[1])(&v36);
    v37[0] = TokenHandle;
LABEL_10:
    ATL::CSid::CSid((ATL::CSid *)v58, (PSID_IDENTIFIER_AUTHORITY)&ATL::Sids::SecurityNTAuthority, 2u);
    IsMember[0] = 0;
    v8 = CheckTokenMembership(v37[0], SidToCheck, IsMember);
    ATL::CSid::~CSid((ATL::CSid *)v58);
    if ( !v8 )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
    }
    goto LABEL_13;
  }
  v7 = GetLastError();
  v4 = v7;
  if ( v7 > 0 )
    v4 = (unsigned __int16)v7 | 0x80070000;
  if ( !v4 )
    goto LABEL_10;
LABEL_13:
  v51 = &ATL::CSid::`vftable';
  psidOwner[68] = 0;
  v53 = 7;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v54);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v55);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v56);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v57);
  if ( !v4 )
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      if ( !(unsigned __int8)ATL::CAccessToken::GetInfoConvert<ATL::CSid,_TOKEN_USER>(&v36, &v51) )
      {
        v10 = GetLastError();
        v4 = v10;
        if ( v10 > 0 )
          v4 = (unsigned __int16)v10 | 0x80070000;
      }
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', (const ATL::CAtlException **)&v45) )
      {
        IsMember[0] = *v45;
        v4 = IsMember[0];
        v3 = v35;
        v2 = (unsigned __int16 **)v33;
        __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18000C65A);
      }
    }
  }
  memset_0(pszPath, 0, 0x20Au);
  if ( !v4 )
    v4 = SHGetFolderPathAndSubDirW(0, 32796, 0, 0, L"Microsoft\\NetTraces", pszPath);
  if ( v5 )
    v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v3 + 10) + 64LL))(*((_QWORD *)v3 + 10));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&pObjectName);
  if ( v4
    || (v13 = (_QWORD *)((char *)v3 + 128),
        (v4 = CTraceController::GenerateTraceFilePath((_DWORD *)v3 + 32, (__int64)L"temp", (__int64)&pObjectName)) != 0) )
  {
    v14 = pObjectName;
  }
  else
  {
    v14 = pObjectName;
    v4 = CTraceController::CopyTraceFile((NetworkIncident *)((char *)v3 + 128), pObjectName);
    if ( !v4 )
    {
      v4 = *((_DWORD *)v3 + 38);
      if ( !v4 )
      {
        v15 = CTraceController::Stop((NetworkIncident *)((char *)v3 + 128));
        if ( v15 == 1 || (v4 = v15) == 0 )
        {
          v16 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v13 + 56LL))(*v13);
          DeleteFileW(v16);
          if ( !v15 )
            v4 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v13 + 96LL))(*v13);
        }
      }
    }
  }
  v39[1] = 0;
  v40 = 0;
  v41 = 2;
  v39[0] = &ATL::CDacl::`vftable';
  v42 = 0;
  v43 = 0;
  v44 = 0;
  if ( !v4 )
  {
    if ( __eh34_try(-1, 2) )
    {
      __eh34_scope_strut(2);
      if ( !ATL::CDacl::AddAllowedAce((ATL::CDacl *)v39, (const struct ATL::CSid *)&v51, v11, v12) )
      {
        v17 = GetLastError();
        v4 = v17;
        if ( v17 > 0 )
          v4 = (unsigned __int16)v17 | 0x80070000;
      }
    }
    if ( __eh34_catch(2) )
    {
      if ( __eh34_catch_type(2, &ATL::CAtlException `RTTI Type Descriptor', (const ATL::CAtlException **)&v46) )
      {
        IsMember[0] = *v46;
        v4 = IsMember[0];
        v14 = pObjectName;
        v3 = v35;
        v2 = (unsigned __int16 **)v33;
        __eh34_try_continuation(2, &ATL::CAtlException `RTTI Type Descriptor', &loc_18000C7F3);
      }
    }
    if ( !v4 )
    {
      PACL = (struct _ACL *)ATL::CAcl::GetPACL((ATL::CAcl *)v39);
      v19 = SetNamedSecurityInfoW(v14, SE_FILE_OBJECT, 4u, 0, 0, PACL, 0);
      if ( v19 )
      {
        if ( v19 > 0 )
          v4 = (unsigned __int16)v19 | 0x80070000;
        else
          v4 = v19;
      }
    }
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&TokenHandle);
  if ( v4 )
    goto LABEL_67;
  TickCount = (__time64_t *)ATL::CTime::GetTickCount(v47);
  if ( __eh34_try(-1, 4) )
  {
    __eh34_scope_strut(4);
    ATL::CTime::Format(TickCount);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      &TokenHandle,
      L"%s\\NdfSession-%s.etl",
      pszPath,
      *(_QWORD *)IsMember);
    v21 = (const __time64_t *)ATL::CTime::GetTickCount(v48);
    memset(&Tm, 0, sizeof(Tm));
    tm_sec = -1;
    if ( !_localtime64_s(&Tm, v21) )
      tm_sec = Tm.tm_sec;
    v23 = tm_sec + 100;
    while ( 1 )
    {
      v24 = (WCHAR *)TokenHandle;
      if ( !PathFileExistsW((LPCWSTR)TokenHandle) || tm_sec >= v23 )
        break;
      LODWORD(pszSubDir) = tm_sec;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &TokenHandle,
        L"%s\\NdfSession-%s-%d.etl",
        pszPath,
        *(_QWORD *)IsMember,
        pszSubDir);
      ++tm_sec;
    }
    ATL::CStringData::Release((ATL::CStringData *)(*(_QWORD *)IsMember - 24LL));
  }
  if ( __eh34_catch(4) )
  {
    if ( __eh34_catch_type(4, &ATL::CAtlException `RTTI Type Descriptor', (const ATL::CAtlException **)&v49) )
    {
      IsMember[0] = *v49;
      __eh34_try_continuation(4, &ATL::CAtlException `RTTI Type Descriptor', &loc_18000C93A);
      v4 = IsMember[0];
      v14 = pObjectName;
      v3 = v35;
      v2 = (unsigned __int16 **)v33;
      if ( !IsMember[0] )
      {
        v24 = (WCHAR *)TokenHandle;
        goto LABEL_52;
      }
LABEL_67:
      v24 = (WCHAR *)TokenHandle;
      goto LABEL_68;
    }
  }
LABEL_52:
  v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v3 + 10) + 56LL))(*((_QWORD *)v3 + 10));
  if ( !v4 )
  {
    DeleteFileW(v24);
    if ( MoveFileW(v14, v24) )
      goto LABEL_57;
    v25 = GetLastError();
    v26 = v25 == 0;
    if ( v25 > 0 )
      v26 = 0;
    if ( v26 )
LABEL_57:
      SetNamedSecurityInfoW(v24, SE_FILE_OBJECT, 1u, psidOwner, 0, 0, 0);
    v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v3 + 10) + 64LL))(*((_QWORD *)v3 + 10));
  }
  if ( !v4 )
  {
    if ( v2 && v24 )
    {
      v33 = 0;
      v4 = StringCchLengthW(v24, 0xFFFEu, &v33);
      if ( v4 >= 0 )
      {
        v27 = v33;
        v28 = (unsigned __int16 *)CoTaskMemAlloc(2 * v33 + 2);
        *v2 = v28;
        if ( v28 )
          v4 = StringCchCopyW(v28, v27 + 1, v24);
        else
          v4 = -2147024882;
      }
    }
    else
    {
      v4 = -2147024809;
    }
  }
LABEL_68:
  ATL::CStringData::Release((ATL::CStringData *)(v24 - 12));
  ATL::CDacl::~CDacl((ATL::CDacl *)v39);
  ATL::CStringData::Release((ATL::CStringData *)(v14 - 12));
  ATL::CSid::~CSid((ATL::CSid *)&v51);
  v36 = &ATL::CAccessToken::`vftable';
  ATL::CAccessToken::Clear((ATL::CAccessToken *)&v36);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000c478  mov     [rsp+arg_10], rbx
0x18000c47d  push    rdi
0x18000c47e  push    r12
0x18000c480  push    r13
0x18000c482  push    r14
0x18000c484  push    r15
0x18000c486  sub     rsp, 440h
0x18000c48d  mov     rax, cs:__security_cookie
0x18000c494  xor     rax, rsp
0x18000c497  mov     [rsp+468h+var_38], rax
0x18000c49f  mov     r12, rdx
0x18000c4a2  mov     r13, rcx
0x18000c4a5  mov     [rsp+468h+var_400], rcx
0x18000c4aa  mov     [rsp+468h+var_410], rdx
0x18000c4af  test    rdx, rdx
0x18000c4b2  jnz     short loc_18000C4BE
0x18000c4b4  mov     edi, 80070057h
0x18000c4b9  xor     r14b, r14b
0x18000c4bc  jmp     short loc_18000C4D6
0x18000c4be  mov     rcx, [rcx+50h]
0x18000c4c2  mov     rax, [rcx]
0x18000c4c5  mov     rax, [rax+38h]
0x18000c4c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4ce  mov     edi, eax
0x18000c4d0  test    eax, eax
0x18000c4d2  setz    r14b
0x18000c4d6  mov     [rsp+468h+var_428], r14b
0x18000c4db  lea     rbx, ??_7CAccessToken@ATL@@6B@; const ATL::CAccessToken::`vftable'
0x18000c4e2  mov     [rsp+468h+var_3F8], rbx
0x18000c4e7  xorps   xmm0, xmm0
0x18000c4ea  movdqu  xmmword ptr [rsp+468h+var_3F0], xmm0
0x18000c4f0  mov     [rsp+468h+var_3E0], 0
0x18000c4fc  test    edi, edi
0x18000c4fe  jnz     loc_18000C5D2
0x18000c504  call    cs:__imp_GetCurrentThread
0x18000c50a  mov     [rsp+468h+TokenHandle], 0
0x18000c513  lea     r9, [rsp+468h+TokenHandle]; TokenHandle
0x18000c518  lea     edx, [rdi+8]; DesiredAccess
0x18000c51b  lea     r8d, [rdi+1]; OpenAsSelf
0x18000c51f  mov     rcx, rax; ThreadHandle
0x18000c522  call    cs:__imp_OpenThreadToken
0x18000c528  test    eax, eax
0x18000c52a  jz      short loc_18000C54B
0x18000c52c  mov     rax, [rsp+468h+var_3F8]
0x18000c531  lea     rcx, [rsp+468h+var_3F8]
0x18000c536  mov     rax, [rax+8]
0x18000c53a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c53f  mov     rax, [rsp+468h+TokenHandle]
0x18000c544  mov     [rsp+468h+var_3F0], rax
0x18000c549  jmp     short loc_18000C564
0x18000c54b  call    cs:__imp_GetLastError
0x18000c551  mov     edi, eax
0x18000c553  test    eax, eax
0x18000c555  jle     short loc_18000C560
0x18000c557  movzx   edi, ax
0x18000c55a  or      edi, 80070000h
0x18000c560  test    edi, edi
0x18000c562  jnz     short loc_18000C5D2
0x18000c564  mov     dword ptr [rsp+468h+pszSubDir], 220h
0x18000c56c  mov     r9d, 20h ; ' '
0x18000c572  lea     r8d, [r9-1Eh]; unsigned __int8
0x18000c576  lea     rdx, ?SecurityNTAuthority@Sids@ATL@@3U_SID_IDENTIFIER_AUTHORITY@@B; pIdentifierAuthority
0x18000c57d  lea     rcx, [rsp+468h+var_2C8]; this
0x18000c585  call    ??0CSid@ATL@@QEAA@AEBU_SID_IDENTIFIER_AUTHORITY@@EZZ; ATL::CSid::CSid(_SID_IDENTIFIER_AUTHORITY const &,uchar,...)
0x18000c58a  mov     [rsp+468h+IsMember], 0
0x18000c592  lea     r8, [rsp+468h+IsMember]; IsMember
0x18000c597  lea     rdx, [rsp+468h+SidToCheck]; SidToCheck
0x18000c59f  mov     rcx, [rsp+468h+var_3F0]; TokenHandle
0x18000c5a4  call    cs:__imp_CheckTokenMembership
0x18000c5aa  mov     ebx, eax
0x18000c5ac  lea     rcx, [rsp+468h+var_2C8]; this
0x18000c5b4  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x18000c5b9  test    ebx, ebx
0x18000c5bb  jnz     short loc_18000C5D2
0x18000c5bd  call    cs:__imp_GetLastError
0x18000c5c3  mov     edi, eax
0x18000c5c5  test    eax, eax
0x18000c5c7  jle     short loc_18000C5D2
0x18000c5c9  movzx   edi, ax
0x18000c5cc  or      edi, 80070000h
0x18000c5d2  lea     rax, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x18000c5d9  mov     [rsp+468h+var_348], rax
0x18000c5e1  mov     [rsp+468h+var_2FC], 0
0x18000c5e9  mov     [rsp+468h+var_2F8], 7
0x18000c5f4  lea     rcx, [rsp+468h+var_2F0]
0x18000c5fc  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000c601  lea     rcx, [rsp+468h+var_2E8]
0x18000c609  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000c60e  lea     rcx, [rsp+468h+var_2E0]
0x18000c616  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000c61b  lea     rcx, [rsp+468h+var_2D8]
0x18000c623  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000c628  nop
0x18000c629  test    edi, edi
0x18000c62b  jnz     short loc_18000C66D
0x18000c62d  lea     rdx, [rsp+468h+var_348]
0x18000c635  lea     rcx, [rsp+468h+var_3F8]
0x18000c63a  call    ??$GetInfoConvert@VCSid@ATL@@U_TOKEN_USER@@@CAccessToken@ATL@@IEBA_NPEAVCSid@1@W4_TOKEN_INFORMATION_CLASS@@PEAU_TOKEN_USER@@@Z; ATL::CAccessToken::GetInfoConvert<ATL::CSid,_TOKEN_USER>(ATL::CSid *,_TOKEN_INFORMATION_CLASS,_TOKEN_USER *)
0x18000c63f  test    al, al
0x18000c641  jnz     short loc_18000C658
0x18000c643  call    cs:__imp_GetLastError
0x18000c649  mov     edi, eax
0x18000c64b  test    eax, eax
0x18000c64d  jle     short loc_18000C658
0x18000c64f  movzx   edi, ax
0x18000c652  or      edi, 80070000h
0x18000c658  jmp     short loc_18000C66D
0x18000c65a  mov     edi, [rsp+468h+IsMember]
0x18000c65e  mov     r14b, [rsp+468h+var_428]
0x18000c663  mov     r13, [rsp+468h+var_400]
0x18000c668  mov     r12, [rsp+468h+var_410]
0x18000c66d  xor     edx, edx; Val
0x18000c66f  mov     r8d, 20Ah; Size
0x18000c675  lea     rcx, [rsp+468h+var_248]; void *
0x18000c67d  call    memset_0
0x18000c682  test    edi, edi
0x18000c684  jnz     short loc_18000C6B4
0x18000c686  lea     rax, [rsp+468h+var_248]
0x18000c68e  mov     [rsp+468h+pszPath], rax; pszPath
0x18000c693  lea     rax, pszSubDir; "Microsoft\\NetTraces"
0x18000c69a  mov     [rsp+468h+pszSubDir], rax; pszSubDir
0x18000c69f  xor     r9d, r9d; dwFlags
0x18000c6a2  xor     r8d, r8d; hToken
0x18000c6a5  mov     edx, 801Ch; csidl
0x18000c6aa  xor     ecx, ecx; hwnd
0x18000c6ac  call    cs:__imp_SHGetFolderPathAndSubDirW
0x18000c6b2  mov     edi, eax
0x18000c6b4  test    r14b, r14b
0x18000c6b7  jz      short loc_18000C6CB
0x18000c6b9  mov     rcx, [r13+50h]
0x18000c6bd  mov     rax, [rcx]
0x18000c6c0  mov     rax, [rax+40h]
0x18000c6c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6c9  mov     edi, eax
0x18000c6cb  lea     rcx, [rsp+468h+pObjectName]
0x18000c6d0  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000c6d5  nop
0x18000c6d6  test    edi, edi
0x18000c6d8  jnz     loc_18000C765
0x18000c6de  lea     r14, [r13+80h]
0x18000c6e5  lea     r8, [rsp+468h+pObjectName]
0x18000c6ea  lea     rdx, aTemp; "temp"
0x18000c6f1  mov     rcx, r14
0x18000c6f4  call    ?GenerateTraceFilePath@CTraceController@@QEAAJPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CTraceController::GenerateTraceFilePath(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18000c6f9  mov     edi, eax
0x18000c6fb  test    eax, eax
0x18000c6fd  jnz     short loc_18000C765
0x18000c6ff  mov     rbx, [rsp+468h+pObjectName]
0x18000c704  mov     rdx, rbx; lpNewFileName
0x18000c707  mov     rcx, r14; this
0x18000c70a  call    ?CopyTraceFile@CTraceController@@QEAAJPEBG@Z; CTraceController::CopyTraceFile(ushort const *)
0x18000c70f  mov     edi, eax
0x18000c711  test    eax, eax
0x18000c713  jnz     short loc_18000C76A
0x18000c715  mov     edi, [r14+18h]
0x18000c719  test    edi, edi
0x18000c71b  jnz     short loc_18000C76A
0x18000c71d  mov     rcx, r14; this
0x18000c720  call    ?Stop@CTraceController@@QEAAJXZ; CTraceController::Stop(void)
0x18000c725  mov     r15d, eax
0x18000c728  cmp     eax, 1
0x18000c72b  jz      short loc_18000C735
0x18000c72d  mov     edi, r15d
0x18000c730  test    r15d, r15d
0x18000c733  jnz     short loc_18000C76A
0x18000c735  mov     rcx, [r14]
0x18000c738  mov     rax, [rcx]
0x18000c73b  mov     rax, [rax+38h]
0x18000c73f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c744  mov     rcx, rax; lpFileName
0x18000c747  call    cs:__imp_DeleteFileW
0x18000c74d  test    r15d, r15d
0x18000c750  jnz     short loc_18000C76A
0x18000c752  mov     rcx, [r14]
0x18000c755  mov     rax, [rcx]
0x18000c758  mov     rax, [rax+60h]
0x18000c75c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c761  mov     edi, eax
0x18000c763  jmp     short loc_18000C76A
0x18000c765  mov     rbx, [rsp+468h+pObjectName]
0x18000c76a  mov     [rsp+468h+var_3D0], 0
0x18000c776  mov     [rsp+468h+var_3C8], 0
0x18000c77e  mov     [rsp+468h+var_3C4], 2
0x18000c789  lea     rax, ??_7CDacl@ATL@@6B@; const ATL::CDacl::`vftable'
0x18000c790  mov     [rsp+468h+var_3D8], rax
0x18000c798  xorps   xmm0, xmm0
0x18000c79b  movdqu  [rsp+468h+var_3C0], xmm0
0x18000c7a4  mov     [rsp+468h+var_3B0], 0
0x18000c7b0  mov     [rsp+468h+var_3A8], 0
0x18000c7bb  test    edi, edi
0x18000c7bd  jnz     loc_18000C854
0x18000c7c3  lea     rdx, [rsp+468h+var_348]; struct ATL::CSid *
0x18000c7cb  lea     rcx, [rsp+468h+var_3D8]; this
0x18000c7d3  call    ?AddAllowedAce@CDacl@ATL@@QEAA_NAEBVCSid@2@KE@Z; ATL::CDacl::AddAllowedAce(ATL::CSid const &,ulong,uchar)
0x18000c7d8  test    al, al
0x18000c7da  jnz     short loc_18000C7F1
0x18000c7dc  call    cs:__imp_GetLastError
0x18000c7e2  mov     edi, eax
0x18000c7e4  test    eax, eax
0x18000c7e6  jle     short loc_18000C7F1
0x18000c7e8  movzx   edi, ax
0x18000c7eb  or      edi, 80070000h
0x18000c7f1  jmp     short loc_18000C806
0x18000c7f3  mov     edi, [rsp+468h+IsMember]
0x18000c7f7  mov     rbx, [rsp+468h+pObjectName]
0x18000c7fc  mov     r13, [rsp+468h+var_400]
0x18000c801  mov     r12, [rsp+468h+var_410]
0x18000c806  test    edi, edi
0x18000c808  jnz     short loc_18000C854
0x18000c80a  lea     rcx, [rsp+468h+var_3D8]; this
0x18000c812  call    ?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ; ATL::CAcl::GetPACL(void)
0x18000c817  mov     [rsp+468h+pSacl], 0; pSacl
0x18000c820  mov     [rsp+468h+pszPath], rax; pDacl
0x18000c825  mov     [rsp+468h+pszSubDir], 0; psidGroup
0x18000c82e  xor     r9d, r9d; psidOwner
0x18000c831  lea     edx, [rdi+1]; ObjectType
0x18000c834  lea     r8d, [rdi+4]; SecurityInfo
0x18000c838  mov     rcx, rbx; pObjectName
0x18000c83b  call    cs:__imp_SetNamedSecurityInfoW
0x18000c841  test    eax, eax
0x18000c843  jz      short loc_18000C854
0x18000c845  jg      short loc_18000C84B
0x18000c847  mov     edi, eax
0x18000c849  jmp     short loc_18000C854
0x18000c84b  movzx   edi, ax
0x18000c84e  or      edi, 80070000h
0x18000c854  lea     rcx, [rsp+468h+TokenHandle]
0x18000c859  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000c85e  nop
0x18000c85f  test    edi, edi
0x18000c861  jnz     loc_18000CA51
0x18000c867  lea     rcx, [rsp+468h+var_390]
0x18000c86f  call    ?GetTickCount@CTime@ATL@@SA?AV12@XZ; ATL::CTime::GetTickCount(void)
0x18000c874  lea     rdx, [rsp+468h+IsMember]
0x18000c879  mov     rcx, rax; Time
0x18000c87c  call    ?Format@CTime@ATL@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@PEBG@Z; ATL::CTime::Format(ushort const *)
0x18000c881  nop
0x18000c882  mov     r9, qword ptr [rsp+468h+IsMember]
0x18000c887  lea     r8, [rsp+468h+var_248]
0x18000c88f  lea     rdx, aSNdfsessionSEt; "%s\\NdfSession-%s.etl"
0x18000c896  lea     rcx, [rsp+468h+TokenHandle]
0x18000c89b  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18000c8a0  lea     rcx, [rsp+468h+var_388]
0x18000c8a8  call    ?GetTickCount@CTime@ATL@@SA?AV12@XZ; ATL::CTime::GetTickCount(void)
0x18000c8ad  nop
0x18000c8ae  xorps   xmm0, xmm0
0x18000c8b1  xor     ecx, ecx
0x18000c8b3  movups  xmmword ptr [rsp+468h+Tm.tm_sec], xmm0
0x18000c8bb  movups  xmmword ptr [rsp+468h+Tm.tm_mon], xmm0
0x18000c8c3  mov     [rsp+468h+Tm.tm_isdst], ecx
0x18000c8ca  mov     rdx, rax; Time
0x18000c8cd  lea     rcx, [rsp+468h+Tm]; Tm
0x18000c8d5  call    cs:__imp__localtime64_s
0x18000c8db  or      edi, 0FFFFFFFFh
0x18000c8de  test    eax, eax
0x18000c8e0  cmovz   edi, [rsp+468h+Tm.tm_sec]
0x18000c8e8  lea     r15d, [rdi+64h]
0x18000c8ec  mov     r14, [rsp+468h+TokenHandle]
0x18000c8f1  mov     rcx, r14; pszPath
0x18000c8f4  call    cs:__imp_PathFileExistsW
0x18000c8fa  test    eax, eax
0x18000c8fc  jz      short loc_18000C929
0x18000c8fe  cmp     edi, r15d
0x18000c901  jge     short loc_18000C929
0x18000c903  mov     dword ptr [rsp+468h+pszSubDir], edi
0x18000c907  mov     r9, qword ptr [rsp+468h+IsMember]
0x18000c90c  lea     r8, [rsp+468h+var_248]
0x18000c914  lea     rdx, aSNdfsessionSDE; "%s\\NdfSession-%s-%d.etl"
0x18000c91b  lea     rcx, [rsp+468h+TokenHandle]
0x18000c920  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18000c925  inc     edi
0x18000c927  jmp     short loc_18000C8EC
0x18000c929  mov     rcx, qword ptr [rsp+468h+IsMember]
0x18000c92e  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000c932  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000c937  nop
0x18000c938  jmp     short loc_18000C95A
0x18000c93a  mov     edi, [rsp+468h+IsMember]
0x18000c93e  mov     rbx, [rsp+468h+pObjectName]
0x18000c943  mov     r13, [rsp+468h+var_400]
0x18000c948  mov     r12, [rsp+468h+var_410]
0x18000c94d  test    edi, edi
0x18000c94f  jnz     loc_18000CA51
0x18000c955  mov     r14, [rsp+468h+TokenHandle]
0x18000c95a  mov     rcx, [r13+50h]
0x18000c95e  mov     rax, [rcx]
0x18000c961  mov     rax, [rax+38h]
0x18000c965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c96a  mov     edi, eax
0x18000c96c  test    eax, eax
0x18000c96e  jnz     short loc_18000C9E5
0x18000c970  mov     rcx, r14; lpFileName
0x18000c973  call    cs:__imp_DeleteFileW
0x18000c979  mov     rdx, r14; lpNewFileName
0x18000c97c  mov     rcx, rbx; lpExistingFileName
0x18000c97f  call    cs:__imp_MoveFileW
0x18000c985  test    eax, eax
0x18000c987  jnz     short loc_18000C99F
0x18000c989  call    cs:__imp_GetLastError
0x18000c98f  test    eax, eax
  ... truncated ...
```
