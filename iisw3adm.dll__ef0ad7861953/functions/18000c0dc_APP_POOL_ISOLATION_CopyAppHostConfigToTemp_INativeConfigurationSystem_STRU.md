# APP_POOL_ISOLATION::CopyAppHostConfigToTemp(INativeConfigurationSystem *,STRU *)

- ea: `0x18000c0dc`
- end: `0x18000c4dc`
- name: `?CopyAppHostConfigToTemp@APP_POOL_ISOLATION@@AEAAJPEAVINativeConfigurationSystem@@PEAVSTRU@@@Z`
- size: `1024`
- prototype: `__int64 __fastcall(APP_POOL_ISOLATION *__hidden this, struct INativeConfigurationSystem *, struct STRU *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000d8a4`

## callees

- `0x18000c0dc`
- `0x18000d78c`
- `0x180061060`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c1fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c209`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c396`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c1fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c209`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c396`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c23c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c23c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000c459`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000c459`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18000c387`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18000c387`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000c4a0`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000c4a0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000c22c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000c22c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c1a8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c1ed`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c1a8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c1ed`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c255`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c260`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c255`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c260`
- `iisutil!PuDbgPrintError` at `0x18000c41f`
- `iisutil!PuDbgPrintError` at `0x18000c41f`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000c115`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000c11f`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000c115`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000c11f`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000c24b`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000c24b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000c2b6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000c3b0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000c2b6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000c3b0`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000c2d2`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000c2ee`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000c320`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000c33a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000c356`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000c2d2`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000c2ee`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000c320`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000c33a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000c356`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000c1c1`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000c1c1`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18000c30e`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18000c30e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000c29c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000c29c`

## string_xrefs

- `0x18000c3f9`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\app_pool_isolation.cxx`
- `0x18000c40f`: `SetFileDacl( %S, %S ) failed.\n`
- `0x18000c3eb`: `APP_POOL_ISOLATION::CopyAppHostConfigToTemp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall APP_POOL_ISOLATION::CopyAppHostConfigToTemp(
        APP_POOL_ISOLATION *this,
        struct INativeConfigurationSystem *a2,
        struct STRU *a3)
{
  _WORD *v6; // rcx
  signed int v7; // ebx
  signed int LastError; // eax
  const WCHAR *v10; // rcx
  signed int v11; // eax
  APP_POOL_ISOLATION *v12; // rcx
  __int64 v13; // r8
  int v14; // r14d
  int v15; // eax
  APP_POOL_ISOLATION *v16; // rcx
  signed int v17; // eax
  DWORD TokenInformationLength; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE TokenHandle; // [rsp+48h] [rbp-B8h] BYREF
  LPWSTR StringSid; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v21[32]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v22; // [rsp+78h] [rbp-88h]
  _QWORD v23[4]; // [rsp+90h] [rbp-70h] BYREF
  LPVOID TokenInformation; // [rsp+B0h] [rbp-50h]
  int v25; // [rsp+B8h] [rbp-48h]
  __int16 v26; // [rsp+BCh] [rbp-44h]
  _BYTE v27[32]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v28; // [rsp+E0h] [rbp-20h]
  WCHAR TempFileName[264]; // [rsp+100h] [rbp+0h] BYREF

  STRU::STRU((STRU *)v21);
  STRU::STRU((STRU *)v27);
  v6 = (_WORD *)*((_QWORD *)a3 + 4);
  TokenInformation = v23;
  TokenHandle = 0;
  StringSid = 0;
  TokenInformationLength = 0;
  v23[0] = 0;
  v25 = 32;
  v26 = 256;
  *v6 = 0;
  *((_DWORD *)a3 + 12) = 0;
  v7 = (*(__int64 (__fastcall **)(struct INativeConfigurationSystem *, HANDLE *))(*(_QWORD *)a2 + 136LL))(
         a2,
         &TokenHandle);
  if ( v7 < 0 )
    goto LABEL_12;
  if ( TokenHandle )
  {
    TokenInformationLength = 0;
    if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
    {
      v7 = -2147418113;
      goto LABEL_12;
    }
    if ( !BUFFER::Resize((BUFFER *)v23, TokenInformationLength) )
    {
      v7 = -2147024882;
      goto LABEL_12;
    }
    if ( !GetTokenInformation(TokenHandle, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength)
      || !ConvertSidToStringSidW(*(PSID *)TokenInformation, &StringSid) )
    {
      if ( GetLastError() )
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v7 = -2147467259;
      }
      goto LABEL_11;
    }
  }
  v7 = STRU::Copy((STRU *)v21, L"D:P");
  if ( v7 < 0 )
    goto LABEL_12;
  v7 = STRU::Append((STRU *)v21, L"(A;;GA;;;SY)");
  if ( v7 < 0 )
    goto LABEL_12;
  v7 = STRU::Append((STRU *)v21, L"(A;;GA;;;BA)");
  if ( v7 < 0 )
    goto LABEL_12;
  if ( StringSid )
  {
    STRU::Copy((STRU *)v27, (const struct STRU *)v21);
    v7 = STRU::Append((STRU *)v21, L"(A;;GWGX;;;");
    if ( v7 < 0 )
      goto LABEL_12;
    v7 = STRU::Append((STRU *)v21, StringSid);
    if ( v7 < 0 )
      goto LABEL_12;
    v7 = STRU::Append((STRU *)v21, L")");
    if ( v7 < 0 )
      goto LABEL_12;
  }
  v10 = (const WCHAR *)*((_QWORD *)this + 16);
  **((_WORD **)a3 + 4) = 0;
  *((_DWORD *)a3 + 12) = 0;
  if ( GetTempFileNameW(v10, L"APCFG", 0, TempFileName) )
  {
    v7 = STRU::Copy(a3, TempFileName);
  }
  else
  {
    v11 = GetLastError();
    v7 = v11;
    if ( v11 > 0 )
      v7 = (unsigned __int16)v11 | 0x80070000;
  }
  if ( v7 < 0 )
    goto LABEL_12;
  v7 = APP_POOL_ISOLATION::SetFileDacl(v12, v22, *((unsigned __int16 **)a3 + 4));
  if ( v7 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_12;
    v13 = 1148;
    goto LABEL_34;
  }
  v14 = 5;
  do
  {
    v15 = (*(__int64 (__fastcall **)(struct INativeConfigurationSystem *, _QWORD))(*(_QWORD *)a2 + 120LL))(
            a2,
            *((_QWORD *)a3 + 4));
    v7 = v15;
    if ( v15 >= 0 )
      break;
    if ( v15 != -2147024864 )
      goto LABEL_12;
    Sleep(0x1F4u);
    --v14;
  }
  while ( v14 );
  if ( !StringSid || (v7 = APP_POOL_ISOLATION::SetFileDacl(v16, v28, *((unsigned __int16 **)a3 + 4)), v7 >= 0) )
  {
    if ( !SetFileAttributesW(*((LPCWSTR *)a3 + 4), 0x2020u) )
    {
      if ( !GetLastError() )
      {
        v7 = -2147467259;
        goto LABEL_12;
      }
      v17 = GetLastError();
      v7 = v17;
      if ( v17 > 0 )
        v7 = (unsigned __int16)v17 | 0x80070000;
    }
LABEL_11:
    if ( v7 >= 0 )
      goto LABEL_14;
    goto LABEL_12;
  }
  if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    v13 = 1188;
LABEL_34:
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool_isolation.cxx",
      v13,
      "APP_POOL_ISOLATION::CopyAppHostConfigToTemp",
      v7,
      "SetFileDacl( %S, %S ) failed.\n",
      v22,
      *((const wchar_t **)a3 + 4));
  }
LABEL_12:
  if ( *((_DWORD *)a3 + 12) )
    DeleteFileW(*((LPCWSTR *)a3 + 4));
LABEL_14:
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v23);
  STRU::~STRU((STRU *)v27);
  STRU::~STRU((STRU *)v21);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000c0dc  push    rbp
0x18000c0de  push    rbx
0x18000c0df  push    rsi
0x18000c0e0  push    rdi
0x18000c0e1  push    r12
0x18000c0e3  push    r14
0x18000c0e5  push    r15
0x18000c0e7  lea     rbp, [rsp-220h]
0x18000c0ef  sub     rsp, 320h
0x18000c0f6  mov     rax, cs:__security_cookie
0x18000c0fd  xor     rax, rsp
0x18000c100  mov     [rbp+250h+var_40], rax
0x18000c107  mov     rsi, rcx
0x18000c10a  mov     rdi, r8
0x18000c10d  lea     rcx, [rsp+350h+var_2F8]
0x18000c112  mov     r15, rdx
0x18000c115  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000c11b  lea     rcx, [rbp+250h+var_290]
0x18000c11f  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000c125  mov     rcx, [rdi+20h]
0x18000c129  lea     rax, [rbp+250h+var_2C0]
0x18000c12d  xor     r12d, r12d
0x18000c130  mov     [rbp+250h+TokenInformation], rax
0x18000c134  mov     [rsp+350h+TokenHandle], r12
0x18000c139  lea     rdx, [rsp+350h+TokenHandle]
0x18000c13e  mov     [rsp+350h+StringSid], r12
0x18000c143  mov     [rsp+350h+TokenInformationLength], r12d
0x18000c148  mov     [rbp+250h+var_2C0], r12
0x18000c14c  lea     r14d, [r12+1]
0x18000c151  mov     [rbp+250h+var_298], 20h ; ' '
0x18000c158  mov     [rbp+250h+var_294], 100h
0x18000c15e  mov     [rcx], r12w
0x18000c162  mov     rcx, r15
0x18000c165  mov     [rdi+30h], r12d
0x18000c169  mov     rax, [r15]
0x18000c16c  mov     rax, [rax+88h]
0x18000c173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c178  mov     ebx, eax
0x18000c17a  test    eax, eax
0x18000c17c  js      loc_18000C222
0x18000c182  mov     rcx, [rsp+350h+TokenHandle]; TokenHandle
0x18000c187  test    rcx, rcx
0x18000c18a  jz      loc_18000C2AA
0x18000c190  lea     rax, [rsp+350h+TokenInformationLength]
0x18000c195  mov     [rsp+350h+TokenInformationLength], r12d
0x18000c19a  xor     r9d, r9d; TokenInformationLength
0x18000c19d  mov     [rsp+350h+ReturnLength], rax; ReturnLength
0x18000c1a2  xor     r8d, r8d; TokenInformation
0x18000c1a5  mov     edx, r14d; TokenInformationClass
0x18000c1a8  call    cs:__imp_GetTokenInformation
0x18000c1ae  test    eax, eax
0x18000c1b0  jz      short loc_18000C1B9
0x18000c1b2  mov     ebx, 8000FFFFh
0x18000c1b7  jmp     short loc_18000C222
0x18000c1b9  mov     edx, [rsp+350h+TokenInformationLength]
0x18000c1bd  lea     rcx, [rbp+250h+var_2C0]
0x18000c1c1  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18000c1c7  test    al, al
0x18000c1c9  jnz     short loc_18000C1D2
0x18000c1cb  mov     ebx, 8007000Eh
0x18000c1d0  jmp     short loc_18000C222
0x18000c1d2  mov     r9d, [rsp+350h+TokenInformationLength]; TokenInformationLength
0x18000c1d7  lea     rax, [rsp+350h+TokenInformationLength]
0x18000c1dc  mov     r8, [rbp+250h+TokenInformation]; TokenInformation
0x18000c1e0  mov     edx, r14d; TokenInformationClass
0x18000c1e3  mov     rcx, [rsp+350h+TokenHandle]; TokenHandle
0x18000c1e8  mov     [rsp+350h+ReturnLength], rax; ReturnLength
0x18000c1ed  call    cs:__imp_GetTokenInformation
0x18000c1f3  test    eax, eax
0x18000c1f5  jnz     loc_18000C290
0x18000c1fb  call    cs:__imp_GetLastError
0x18000c201  test    eax, eax
0x18000c203  jz      loc_18000C289
0x18000c209  call    cs:__imp_GetLastError
0x18000c20f  mov     ebx, eax
0x18000c211  test    eax, eax
0x18000c213  jle     short loc_18000C21E
0x18000c215  movzx   ebx, ax
0x18000c218  or      ebx, 80070000h
0x18000c21e  test    ebx, ebx
0x18000c220  jns     short loc_18000C232
0x18000c222  cmp     [rdi+30h], r12d
0x18000c226  jz      short loc_18000C232
0x18000c228  mov     rcx, [rdi+20h]; lpFileName
0x18000c22c  call    cs:__imp_DeleteFileW
0x18000c232  mov     rcx, [rsp+350h+TokenHandle]; hObject
0x18000c237  test    rcx, rcx
0x18000c23a  jz      short loc_18000C247
0x18000c23c  call    cs:__imp_CloseHandle
0x18000c242  mov     [rsp+350h+TokenHandle], r12
0x18000c247  lea     rcx, [rbp+250h+var_2C0]
0x18000c24b  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000c251  lea     rcx, [rbp+250h+var_290]
0x18000c255  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000c25b  lea     rcx, [rsp+350h+var_2F8]
0x18000c260  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000c266  mov     eax, ebx
0x18000c268  mov     rcx, [rbp+250h+var_40]
0x18000c26f  xor     rcx, rsp; StackCookie
0x18000c272  call    __security_check_cookie
0x18000c277  add     rsp, 320h
0x18000c27e  pop     r15
0x18000c280  pop     r14
0x18000c282  pop     r12
0x18000c284  pop     rdi
0x18000c285  pop     rsi
0x18000c286  pop     rbx
0x18000c287  pop     rbp
0x18000c288  retn
0x18000c289  mov     ebx, 80004005h
0x18000c28e  jmp     short loc_18000C21E
0x18000c290  mov     rcx, [rbp+250h+TokenInformation]
0x18000c294  lea     rdx, [rsp+350h+StringSid]; StringSid
0x18000c299  mov     rcx, [rcx]; Sid
0x18000c29c  call    cs:__imp_ConvertSidToStringSidW
0x18000c2a2  test    eax, eax
0x18000c2a4  jz      loc_18000C1FB
0x18000c2aa  lea     rdx, aDP; "D:P"
0x18000c2b1  lea     rcx, [rsp+350h+var_2F8]
0x18000c2b6  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000c2bc  mov     ebx, eax
0x18000c2be  test    eax, eax
0x18000c2c0  js      loc_18000C222
0x18000c2c6  lea     rdx, aAGaSy; "(A;;GA;;;SY)"
0x18000c2cd  lea     rcx, [rsp+350h+var_2F8]
0x18000c2d2  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000c2d8  mov     ebx, eax
0x18000c2da  test    eax, eax
0x18000c2dc  js      loc_18000C222
0x18000c2e2  lea     rdx, aAGaBa; "(A;;GA;;;BA)"
0x18000c2e9  lea     rcx, [rsp+350h+var_2F8]
0x18000c2ee  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000c2f4  mov     ebx, eax
0x18000c2f6  test    eax, eax
0x18000c2f8  js      loc_18000C222
0x18000c2fe  cmp     [rsp+350h+StringSid], r12
0x18000c303  jz      short loc_18000C366
0x18000c305  lea     rdx, [rsp+350h+var_2F8]
0x18000c30a  lea     rcx, [rbp+250h+var_290]
0x18000c30e  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x18000c314  lea     rdx, aAGwgx; "(A;;GWGX;;;"
0x18000c31b  lea     rcx, [rsp+350h+var_2F8]
0x18000c320  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000c326  mov     ebx, eax
0x18000c328  test    eax, eax
0x18000c32a  js      loc_18000C222
0x18000c330  mov     rdx, [rsp+350h+StringSid]
0x18000c335  lea     rcx, [rsp+350h+var_2F8]
0x18000c33a  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000c340  mov     ebx, eax
0x18000c342  test    eax, eax
0x18000c344  js      loc_18000C222
0x18000c34a  lea     rdx, asc_180067C58; ")"
0x18000c351  lea     rcx, [rsp+350h+var_2F8]
0x18000c356  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000c35c  mov     ebx, eax
0x18000c35e  test    eax, eax
0x18000c360  js      loc_18000C222
0x18000c366  mov     rdx, [rdi+20h]
0x18000c36a  lea     r9, [rbp+250h+TempFileName]; lpTempFileName
0x18000c36e  mov     rcx, [rsi+80h]; lpPathName
0x18000c375  xor     r8d, r8d; uUnique
0x18000c378  mov     [rdx], r12w
0x18000c37c  lea     rdx, PrefixString; "APCFG"
0x18000c383  mov     [rdi+30h], r12d
0x18000c387  call    cs:__imp_GetTempFileNameW
0x18000c38d  mov     esi, 80070000h
0x18000c392  test    eax, eax
0x18000c394  jnz     short loc_18000C3A9
0x18000c396  call    cs:__imp_GetLastError
0x18000c39c  mov     ebx, eax
0x18000c39e  test    eax, eax
0x18000c3a0  jle     short loc_18000C3B8
0x18000c3a2  movzx   ebx, ax
0x18000c3a5  or      ebx, esi
0x18000c3a7  jmp     short loc_18000C3B8
0x18000c3a9  lea     rdx, [rbp+250h+TempFileName]
0x18000c3ad  mov     rcx, rdi
0x18000c3b0  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000c3b6  mov     ebx, eax
0x18000c3b8  test    ebx, ebx
0x18000c3ba  js      loc_18000C222
0x18000c3c0  mov     r8, [rdi+20h]; unsigned __int16 *
0x18000c3c4  mov     rdx, [rsp+350h+var_2D8]; unsigned __int16 *
0x18000c3c9  call    ?SetFileDacl@APP_POOL_ISOLATION@@AEAAJPEAG0@Z; APP_POOL_ISOLATION::SetFileDacl(ushort *,ushort *)
0x18000c3ce  mov     ebx, eax
0x18000c3d0  test    eax, eax
0x18000c3d2  jns     short loc_18000C42A
0x18000c3d4  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000c3db  jz      loc_18000C222
0x18000c3e1  mov     r8d, 47Ch
0x18000c3e7  mov     rax, [rdi+20h]
0x18000c3eb  lea     r9, aAppPoolIsolati_0; "APP_POOL_ISOLATION::CopyAppHostConfigTo"...
0x18000c3f2  mov     rcx, cs:g_pDebug
0x18000c3f9  lea     rdx, aServercommonIn_28; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000c400  mov     [rsp+350h+var_318], rax
0x18000c405  mov     rax, [rsp+350h+var_2D8]
0x18000c40a  mov     [rsp+350h+var_320], rax
0x18000c40f  lea     rax, aSetfiledaclSSF; "SetFileDacl( %S, %S ) failed.\n"
0x18000c416  mov     [rsp+350h+var_328], rax
0x18000c41b  mov     dword ptr [rsp+350h+ReturnLength], ebx
0x18000c41f  call    cs:__imp_PuDbgPrintError
0x18000c425  jmp     loc_18000C222
0x18000c42a  mov     r14d, 5
0x18000c430  mov     rax, [r15]
0x18000c433  mov     rcx, r15
0x18000c436  mov     rdx, [rdi+20h]
0x18000c43a  mov     rax, [rax+78h]
0x18000c43e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c443  mov     ebx, eax
0x18000c445  test    eax, eax
0x18000c447  jns     short loc_18000C465
0x18000c449  cmp     eax, 80070020h
0x18000c44e  jnz     loc_18000C222
0x18000c454  mov     ecx, 1F4h; dwMilliseconds
0x18000c459  call    cs:__imp_Sleep
0x18000c45f  add     r14d, 0FFFFFFFFh
0x18000c463  jnz     short loc_18000C430
0x18000c465  cmp     [rsp+350h+StringSid], r12
0x18000c46a  jz      short loc_18000C497
0x18000c46c  mov     r8, [rdi+20h]; unsigned __int16 *
0x18000c470  mov     rdx, [rbp+250h+var_270]; unsigned __int16 *
0x18000c474  call    ?SetFileDacl@APP_POOL_ISOLATION@@AEAAJPEAG0@Z; APP_POOL_ISOLATION::SetFileDacl(ushort *,ushort *)
0x18000c479  mov     ebx, eax
0x18000c47b  test    eax, eax
0x18000c47d  jns     short loc_18000C497
0x18000c47f  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000c486  jz      loc_18000C222
0x18000c48c  mov     r8d, 4A4h
0x18000c492  jmp     loc_18000C3E7
0x18000c497  mov     rcx, [rdi+20h]; lpFileName
0x18000c49b  mov     edx, 2020h; dwFileAttributes
0x18000c4a0  call    cs:__imp_SetFileAttributesW
0x18000c4a6  test    eax, eax
0x18000c4a8  jnz     loc_18000C21E
0x18000c4ae  call    cs:__imp_GetLastError
0x18000c4b4  test    eax, eax
0x18000c4b6  jz      short loc_18000C4D2
0x18000c4b8  call    cs:__imp_GetLastError
0x18000c4be  mov     ebx, eax
0x18000c4c0  test    eax, eax
0x18000c4c2  jle     loc_18000C21E
0x18000c4c8  movzx   ebx, ax
0x18000c4cb  or      ebx, esi
0x18000c4cd  jmp     loc_18000C21E
0x18000c4d2  mov     ebx, 80004005h
0x18000c4d7  jmp     loc_18000C222
```
