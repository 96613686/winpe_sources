# CflApi::SetupTempUserAccount(uchar * *,ulong *)

- ea: `0x180020a54`
- end: `0x180020ffa`
- name: `?SetupTempUserAccount@CflApi@@YAJPEAPEAEPEAK@Z`
- size: `1446`
- prototype: `__int64 __fastcall(CflApi *__hidden this, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180011dd0`

## callees

- `0x180002ef8`
- `0x1800067c4`
- `0x1800071b4`
- `0x180007228`
- `0x180010700`
- `0x180011130`
- `0x18001332c`
- `0x18001ad08`
- `0x18001afc8`
- `0x18001c500`
- `0x18001d29c`
- `0x18001eef8`
- `0x18001f8e4`
- `0x18001f948`
- `0x180020040`
- `0x180020a54`
- `0x18002222c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020acc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020acc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020ade`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020ade`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180020e05`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180020e05`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180020e9d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180020eda`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180020e9d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180020eda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020e30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020f0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020e30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020f0e`
- `samcli!NetUserGetInfo` at `0x180020b4b`
- `samcli!NetUserGetInfo` at `0x180020b4b`
- `samcli!NetUserAdd` at `0x180020d1d`
- `samcli!NetUserAdd` at `0x180020d1d`
- `netutils!NetApiBufferFree` at `0x180020b76`
- `netutils!NetApiBufferFree` at `0x180020f5c`
- `netutils!NetApiBufferFree` at `0x180020b76`
- `netutils!NetApiBufferFree` at `0x180020f5c`

## string_xrefs

- `0x180020ece`: `CflTempAccountCreated`
- `0x180020a9a`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x180020fcc`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`

## pseudocode

```c
__int64 __fastcall CflApi::SetupTempUserAccount(CflApi *this, unsigned __int8 **a2, unsigned int *a3)
{
  int v4; // eax
  char v5; // r12
  WCHAR *v6; // rbx
  __int64 v7; // r15
  DWORD LastError; // esi
  int v9; // eax
  unsigned int v10; // esi
  int v11; // eax
  unsigned __int16 **v12; // rdx
  unsigned __int16 *v13; // rdi
  int ComplexPassword; // r15d
  LPCWSTR v15; // rsi
  __int64 v16; // rax
  unsigned __int64 v17; // rsi
  int v18; // eax
  WCHAR *v19; // rcx
  unsigned __int64 v20; // rdx
  int v21; // eax
  __int64 v22; // rdx
  DWORD v24; // eax
  int v25; // eax
  unsigned int v26; // eax
  __int64 v27; // rdx
  unsigned int v28; // r14d
  WCHAR *v29; // rcx
  int dwOptions; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-E0h]
  int dwOptionsb; // [rsp+20h] [rbp-E0h]
  const char *samDesired; // [rsp+28h] [rbp-D8h]
  LPCWSTR username; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  BYTE v36[8]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR *v37; // [rsp+68h] [rbp-98h]
  LPCWSTR v38; // [rsp+70h] [rbp-90h]
  LPBYTE *p_bufptr; // [rsp+78h] [rbp-88h] BYREF
  __int64 v40; // [rsp+80h] [rbp-80h] BYREF
  char v41; // [rsp+88h] [rbp-78h]
  BYTE buf[8]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v43; // [rsp+98h] [rbp-68h]
  int v44; // [rsp+A4h] [rbp-5Ch]
  int v45; // [rsp+B8h] [rbp-48h]
  const wchar_t *v46; // [rsp+E0h] [rbp-20h]
  int v47; // [rsp+F8h] [rbp-8h]
  int v48; // [rsp+FCh] [rbp-4h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]
  LPBYTE bufptr; // [rsp+180h] [rbp+80h] BYREF
  int Data; // [rsp+188h] [rbp+88h] BYREF

  if ( !this || !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB8,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)0x80004003LL,
      dwOptions);
    return 2147500035LL;
  }
  *(_QWORD *)this = 0;
  *(_DWORD *)a2 = 0;
  v4 = CflApi::ClearTempUserAccount(this);
  if ( v4 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xBD,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)(unsigned int)v4,
      dwOptions);
  v37 = 0;
  v5 = 0;
  v6 = 0;
  v7 = 1;
  do
  {
    if ( v6 )
    {
      LastError = GetLastError();
      CflFreeBuffer(v6);
      SetLastError(LastError);
    }
    username = 0;
    v9 = CflApiNew::AllocBuffer_unsigned_short_(13, &username);
    v10 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2DF,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
        (const char *)(unsigned int)v9,
        dwOptions);
      v29 = (WCHAR *)username;
      if ( username )
LABEL_71:
        CflFreeBuffer(v29);
LABEL_72:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC0,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
        (const char *)v10,
        dwOptionsb);
      return v10;
    }
    dwOptions = v7;
    v6 = (WCHAR *)username;
    v11 = StringCchPrintfW((unsigned __int16 *)username, 0xDu, L"%s%Iu", L"defaultuser");
    v10 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E5,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
        (const char *)(unsigned int)v11,
        v7);
      goto LABEL_67;
    }
    bufptr = 0;
    if ( NetUserGetInfo(0, v6, 0, &bufptr) == 2221 )
    {
      v5 = 1;
      goto LABEL_13;
    }
    if ( (unsigned __int64)++v7 > 9 )
    {
      v10 = -2147024574;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2F3,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
        (const char *)0x80070142LL,
        dwOptions);
      if ( bufptr )
        NetApiBufferFree(bufptr);
LABEL_67:
      if ( v6 )
      {
        v29 = v6;
        goto LABEL_71;
      }
      goto LABEL_72;
    }
LABEL_13:
    if ( bufptr )
      NetApiBufferFree(bufptr);
  }
  while ( !v5 );
  v37 = v6;
  v13 = 0;
  v38 = 0;
  bufptr = 0;
  p_bufptr = &bufptr;
  v40 = 0;
  v41 = 1;
  ComplexPassword = SystemManagedAccountUtil::GenerateComplexPassword((SystemManagedAccountUtil *)&v40, v12);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::cotaskmem_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::cotaskmem_secure_deleter>>(&p_bufptr);
  if ( ComplexPassword < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x305,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)(unsigned int)ComplexPassword,
      dwOptions);
    goto LABEL_18;
  }
  v16 = -1;
  do
    ++v16;
  while ( *(_WORD *)&bufptr[2 * v16] );
  v17 = v16 + 1;
  username = 0;
  v18 = CflApiNew::AllocBuffer_unsigned_short_(v16 + 1, &username);
  ComplexPassword = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x30A,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)(unsigned int)v18,
      dwOptions);
    v19 = (WCHAR *)username;
    if ( username )
      goto LABEL_23;
    goto LABEL_18;
  }
  v20 = v17;
  v15 = username;
  v21 = StringCchCopyW((unsigned __int16 *)username, v20, (const unsigned __int16 *)bufptr);
  ComplexPassword = v21;
  if ( v21 >= 0 )
  {
    v13 = (unsigned __int16 *)v15;
    v38 = v15;
    ComplexPassword = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x30B,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)(unsigned int)v21,
      dwOptions);
    if ( v15 )
    {
      v19 = (WCHAR *)v15;
LABEL_23:
      CflSecureFreeBuffer(v19);
    }
LABEL_18:
    v15 = 0;
  }
  wistd::unique_ptr<unsigned short [0],wil::cotaskmem_secure_deleter>::~unique_ptr<unsigned short [0],wil::cotaskmem_secure_deleter>(&bufptr);
  if ( ComplexPassword < 0 )
  {
    v22 = 194;
    goto LABEL_30;
  }
  memset_0(buf, 0, 0x98u);
  *(_QWORD *)buf = v6;
  v43 = v13;
  v44 = 1;
  v45 = 513;
  v46 = L"{2D0CB8B4-2469-4C46-A0FC-F09CAF1FF0CD}";
  v47 = -1;
  v48 = -1;
  v24 = NetUserAdd(0, 2u, buf, 0);
  if ( v24 )
  {
    LODWORD(samDesired) = v24;
    ComplexPassword = -2147467259;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x328,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)0x80004005LL,
      (int)"status: %d",
      samDesired);
    v22 = 195;
    goto LABEL_30;
  }
  ComplexPassword = CflApi::HideTempUserAccountFromLogonUI(v6);
  if ( ComplexPassword >= 0 )
  {
    LODWORD(bufptr) = 0;
    username = 0;
    v25 = CflApi::SerializeTempUserAccountCredential(v6, v13);
    ComplexPassword = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCC,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
        (const char *)(unsigned int)v25,
        dwOptions);
      if ( username )
        CflSecureFreeBuffer((HLOCAL)username);
      goto LABEL_31;
    }
    hKey = 0;
    v26 = RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
            0,
            0,
            0,
            2u,
            0,
            &hKey,
            0);
    if ( v26 )
    {
      v27 = 219;
    }
    else
    {
      Data = 1;
      v26 = RegSetValueExW(hKey, L"DefaultAccountAction", 0, 4u, (const BYTE *)&Data, 4u);
      if ( v26 )
      {
        v27 = 229;
      }
      else
      {
        *(_DWORD *)v36 = 1;
        v26 = RegSetValueExW(hKey, L"CflTempAccountCreated", 0, 4u, v36, 4u);
        if ( !v26 )
        {
          *(_QWORD *)this = username;
          *(_DWORD *)a2 = (_DWORD)bufptr;
          if ( hKey )
            RegCloseKey(hKey);
          if ( v15 )
            CflSecureFreeBuffer(v13);
          if ( v6 )
            CflFreeBuffer(v6);
          return 0;
        }
        v27 = 239;
      }
    }
    v28 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v27,
            (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
            (const char *)v26,
            dwOptionsa);
    if ( hKey )
      RegCloseKey(hKey);
    if ( username )
      CflSecureFreeBuffer((HLOCAL)username);
    if ( v15 )
      CflSecureFreeBuffer(v13);
    if ( v6 )
      CflFreeBuffer(v6);
    return v28;
  }
  v22 = 196;
LABEL_30:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v22,
    (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
    (const char *)(unsigned int)ComplexPassword,
    dwOptions);
LABEL_31:
  if ( v15 )
    CflSecureFreeBuffer(v13);
  if ( v6 )
    CflFreeBuffer(v6);
  return (unsigned int)ComplexPassword;
}

```

## disassembly

```asm
0x180020a54  mov     [rsp-8+arg_8], rbx
0x180020a59  mov     [rsp-8+arg_0], rcx
0x180020a5e  push    rbp
0x180020a5f  push    rsi
0x180020a60  push    rdi
0x180020a61  push    r12
0x180020a63  push    r13
0x180020a65  push    r14
0x180020a67  push    r15
0x180020a69  lea     rbp, [rsp-30h]
0x180020a6e  sub     rsp, 130h
0x180020a75  mov     r13, rdx
0x180020a78  xor     esi, esi
0x180020a7a  test    rcx, rcx
0x180020a7d  jz      loc_180020FC0
0x180020a83  test    rdx, rdx
0x180020a86  jz      loc_180020FC0
0x180020a8c  mov     [rcx], rsi
0x180020a8f  mov     [rdx], esi
0x180020a91  call    ?ClearTempUserAccount@CflApi@@YAJXZ; CflApi::ClearTempUserAccount(void)
0x180020a96  mov     rcx, [rbp+68h]; this
0x180020a9a  lea     r14, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x180020aa1  test    eax, eax
0x180020aa3  jns     short loc_180020AB6
0x180020aa5  mov     r9d, eax; char *
0x180020aa8  mov     r8, r14; unsigned int
0x180020aab  mov     edx, 0BDh; void *
0x180020ab0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180020ab5  nop
0x180020ab6  mov     [rsp+160h+var_F8], rsi
0x180020abb  mov     r12b, sil
0x180020abe  mov     rbx, rsi
0x180020ac1  mov     r15d, 1
0x180020ac7  test    rbx, rbx
0x180020aca  jz      short loc_180020AE6
0x180020acc  call    cs:__imp_GetLastError
0x180020ad2  mov     esi, eax
0x180020ad4  mov     rcx, rbx; hMem
0x180020ad7  call    CflFreeBuffer
0x180020adc  mov     ecx, esi; dwErrCode
0x180020ade  call    cs:__imp_SetLastError
0x180020ae4  xor     esi, esi
0x180020ae6  mov     [rsp+160h+username], rsi
0x180020aeb  lea     rdx, [rsp+160h+username]
0x180020af0  mov     ecx, 0Dh
0x180020af5  call    CflApiNew__AllocBuffer_unsigned_short_
0x180020afa  mov     esi, eax
0x180020afc  test    eax, eax
0x180020afe  js      loc_180020F83
0x180020b04  mov     qword ptr [rsp+160h+dwOptions], r15; int
0x180020b09  lea     r9, aDefaultuser; "defaultuser"
0x180020b10  lea     r8, aSIu; "%s%Iu"
0x180020b17  mov     edx, 0Dh; unsigned __int64
0x180020b1c  mov     rbx, [rsp+160h+username]
0x180020b21  mov     rcx, rbx; unsigned __int16 *
0x180020b24  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180020b29  mov     esi, eax
0x180020b2b  test    eax, eax
0x180020b2d  js      loc_180020F6D
0x180020b33  xor     esi, esi
0x180020b35  mov     [rbp+60h+bufptr], rsi
0x180020b3c  lea     r9, [rbp+60h+bufptr]; bufptr
0x180020b43  xor     r8d, r8d; level
0x180020b46  mov     rdx, rbx; username
0x180020b49  xor     ecx, ecx; servername
0x180020b4b  call    cs:__imp_NetUserGetInfo
0x180020b51  cmp     eax, 8ADh
0x180020b56  jnz     short loc_180020B5D
0x180020b58  mov     r12b, 1
0x180020b5b  jmp     short loc_180020B6A
0x180020b5d  inc     r15
0x180020b60  cmp     r15, 9
0x180020b64  ja      loc_180020F37
0x180020b6a  mov     rcx, [rbp+60h+bufptr]; Buffer
0x180020b71  test    rcx, rcx
0x180020b74  jz      short loc_180020B7C
0x180020b76  call    cs:__imp_NetApiBufferFree
0x180020b7c  test    r12b, r12b
0x180020b7f  jz      loc_180020AC7
0x180020b85  mov     [rsp+160h+var_F8], rbx
0x180020b8a  xor     r12d, r12d
0x180020b8d  mov     edi, r12d
0x180020b90  mov     [rsp+160h+var_F0], r12
0x180020b95  mov     [rbp+60h+bufptr], r12
0x180020b9c  lea     rax, [rbp+60h+bufptr]
0x180020ba3  mov     [rsp+160h+var_E8], rax
0x180020ba8  mov     [rbp+60h+var_E0], r12
0x180020bac  mov     [rbp+60h+var_D8], 1
0x180020bb0  lea     rcx, [rbp+60h+var_E0]; this
0x180020bb4  call    ?GenerateComplexPassword@SystemManagedAccountUtil@@YAJPEAPEAG@Z; SystemManagedAccountUtil::GenerateComplexPassword(ushort * *)
0x180020bb9  mov     r15d, eax
0x180020bbc  lea     rcx, [rsp+160h+var_E8]
0x180020bc1  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GUcotaskmem_secure_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::cotaskmem_secure_deleter>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::cotaskmem_secure_deleter>>(void)
0x180020bc6  test    r15d, r15d
0x180020bc9  jns     short loc_180020BE8
0x180020bcb  mov     rcx, [rbp+68h]; this
0x180020bcf  mov     r9d, r15d; char *
0x180020bd2  mov     r8, r14; unsigned int
0x180020bd5  mov     edx, 305h; void *
0x180020bda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020bdf  nop
0x180020be0  mov     rsi, r12
0x180020be3  jmp     loc_180020C8C
0x180020be8  mov     rcx, [rbp+60h+bufptr]
0x180020bef  or      rax, 0FFFFFFFFFFFFFFFFh
0x180020bf3  inc     rax
0x180020bf6  cmp     [rcx+rax*2], r12w
0x180020bfb  jnz     short loc_180020BF3
0x180020bfd  lea     rsi, [rax+1]
0x180020c01  mov     [rsp+160h+username], r12
0x180020c06  lea     rdx, [rsp+160h+username]
0x180020c0b  mov     rcx, rsi
0x180020c0e  call    CflApiNew__AllocBuffer_unsigned_short_
0x180020c13  mov     r15d, eax
0x180020c16  test    eax, eax
0x180020c18  jns     short loc_180020C40
0x180020c1a  mov     rcx, [rbp+68h]; this
0x180020c1e  mov     r9d, eax; char *
0x180020c21  mov     r8, r14; unsigned int
0x180020c24  mov     edx, 30Ah; void *
0x180020c29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020c2e  nop
0x180020c2f  mov     rcx, [rsp+160h+username]; hMem
0x180020c34  test    rcx, rcx
0x180020c37  jz      short loc_180020BE0
0x180020c39  call    CflSecureFreeBuffer
0x180020c3e  jmp     short loc_180020BE0
0x180020c40  mov     r8, [rbp+60h+bufptr]; unsigned __int16 *
0x180020c47  mov     rdx, rsi; unsigned __int64
0x180020c4a  mov     rsi, [rsp+160h+username]
0x180020c4f  mov     rcx, rsi; unsigned __int16 *
0x180020c52  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180020c57  mov     r15d, eax
0x180020c5a  test    eax, eax
0x180020c5c  jns     short loc_180020C81
0x180020c5e  mov     rcx, [rbp+68h]; this
0x180020c62  mov     r9d, eax; char *
0x180020c65  mov     r8, r14; unsigned int
0x180020c68  mov     edx, 30Bh; void *
0x180020c6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020c72  nop
0x180020c73  test    rsi, rsi
0x180020c76  jz      loc_180020BE0
0x180020c7c  mov     rcx, rsi
0x180020c7f  jmp     short loc_180020C39
0x180020c81  mov     rdi, rsi
0x180020c84  mov     [rsp+160h+var_F0], rsi
0x180020c89  mov     r15d, r12d
0x180020c8c  lea     rcx, [rbp+60h+bufptr]
0x180020c93  call    ??1?$unique_ptr@$$BY0A@GUcotaskmem_secure_deleter@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<ushort [0],wil::cotaskmem_secure_deleter>::~unique_ptr<ushort [0],wil::cotaskmem_secure_deleter>(void)
0x180020c98  test    r15d, r15d
0x180020c9b  jns     short loc_180020CD5
0x180020c9d  mov     edx, 0C2h; void *
0x180020ca2  mov     r8, r14; unsigned int
0x180020ca5  mov     r9d, r15d; char *
0x180020ca8  mov     rcx, [rbp+68h]; this
0x180020cac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020cb1  nop
0x180020cb2  test    rsi, rsi
0x180020cb5  jz      short loc_180020CC0
0x180020cb7  mov     rcx, rdi; hMem
0x180020cba  call    CflSecureFreeBuffer
0x180020cbf  nop
0x180020cc0  test    rbx, rbx
0x180020cc3  jz      short loc_180020CCD
0x180020cc5  mov     rcx, rbx; hMem
0x180020cc8  call    CflFreeBuffer
0x180020ccd  mov     eax, r15d
0x180020cd0  jmp     loc_180020FDF
0x180020cd5  xor     edx, edx; Val
0x180020cd7  mov     r8d, 98h; Size
0x180020cdd  lea     rcx, [rbp+60h+buf]; void *
0x180020ce1  call    memset_0
0x180020ce6  mov     qword ptr [rbp+60h+buf], rbx
0x180020cea  mov     [rbp+60h+var_C8], rdi
0x180020cee  mov     [rbp+60h+var_BC], 1
0x180020cf5  mov     [rbp+60h+var_A8], 201h
0x180020cfc  lea     rax, a2d0cb8b424694c; "{2D0CB8B4-2469-4C46-A0FC-F09CAF1FF0CD}"
0x180020d03  mov     [rbp+60h+var_80], rax
0x180020d07  or      eax, 0FFFFFFFFh
0x180020d0a  mov     [rbp+60h+var_68], eax
0x180020d0d  mov     [rbp+60h+var_64], eax
0x180020d10  xor     r9d, r9d; parm_err
0x180020d13  lea     r8, [rbp+60h+buf]; buf
0x180020d17  lea     edx, [r9+2]; level
0x180020d1b  xor     ecx, ecx; servername
0x180020d1d  call    cs:__imp_NetUserAdd
0x180020d23  test    eax, eax
0x180020d25  jz      short loc_180020D5B
0x180020d27  mov     rcx, [rbp+68h]; this
0x180020d2b  mov     dword ptr [rsp+160h+samDesired], eax; char *
0x180020d2f  lea     rax, aStatusD; "status: %d"
0x180020d36  mov     qword ptr [rsp+160h+dwOptions], rax; int
0x180020d3b  mov     r15d, 80004005h
0x180020d41  mov     r9d, r15d; char *
0x180020d44  mov     r8, r14; unsigned int
0x180020d47  mov     edx, 328h; void *
0x180020d4c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180020d51  mov     edx, 0C3h
0x180020d56  jmp     loc_180020CA2
0x180020d5b  mov     rcx, rbx; SourceString
0x180020d5e  call    CflApi__HideTempUserAccountFromLogonUI
0x180020d63  mov     r15d, eax
0x180020d66  test    eax, eax
0x180020d68  jns     short loc_180020D74
0x180020d6a  mov     edx, 0C4h
0x180020d6f  jmp     loc_180020CA2
0x180020d74  mov     dword ptr [rbp+60h+bufptr], r12d
0x180020d7b  mov     [rsp+160h+username], r12
0x180020d80  lea     r9, [rbp+60h+bufptr]
0x180020d87  lea     r8, [rsp+160h+username]
0x180020d8c  mov     rdx, rdi; unsigned __int16 *
0x180020d8f  mov     rcx, rbx; unsigned __int16 *
0x180020d92  call    CflApi__SerializeTempUserAccountCredential
0x180020d97  mov     r15d, eax
0x180020d9a  test    eax, eax
0x180020d9c  jns     short loc_180020DCB
0x180020d9e  mov     rcx, [rbp+68h]; this
0x180020da2  mov     r9d, eax; char *
0x180020da5  mov     r8, r14; unsigned int
0x180020da8  mov     edx, 0CCh; void *
0x180020dad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020db2  nop
0x180020db3  mov     rcx, [rsp+160h+username]; hMem
0x180020db8  test    rcx, rcx
0x180020dbb  jz      loc_180020CB2
0x180020dc1  call    CflSecureFreeBuffer
0x180020dc6  jmp     loc_180020CB2
0x180020dcb  mov     [rsp+160h+hKey], r12
0x180020dd0  mov     [rsp+160h+lpdwDisposition], r12; lpdwDisposition
0x180020dd5  lea     rax, [rsp+160h+hKey]
0x180020dda  mov     [rsp+160h+phkResult], rax; phkResult
0x180020ddf  mov     [rsp+160h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180020de4  mov     dword ptr [rsp+160h+samDesired], 2; samDesired
0x180020dec  mov     [rsp+160h+dwOptions], r12d; unsigned int
0x180020df1  xor     r9d, r9d; lpClass
0x180020df4  xor     r8d, r8d; Reserved
0x180020df7  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180020dfe  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180020e05  call    cs:__imp_RegCreateKeyExW
0x180020e0b  test    eax, eax
0x180020e0d  jz      short loc_180020E6A
0x180020e0f  mov     edx, 0DBh; void *
0x180020e14  mov     r9d, eax; char *
0x180020e17  mov     r8, r14; unsigned int
0x180020e1a  mov     rcx, [rbp+68h]; this
0x180020e1e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180020e23  mov     rcx, [rsp+160h+hKey]; hKey
0x180020e28  mov     r14d, eax
0x180020e2b  test    rcx, rcx
0x180020e2e  jz      short loc_180020E37
0x180020e30  call    cs:__imp_RegCloseKey
0x180020e36  nop
0x180020e37  mov     rcx, [rsp+160h+username]; hMem
0x180020e3c  test    rcx, rcx
0x180020e3f  jz      short loc_180020E47
0x180020e41  call    CflSecureFreeBuffer
0x180020e46  nop
0x180020e47  test    rsi, rsi
0x180020e4a  jz      short loc_180020E55
0x180020e4c  mov     rcx, rdi; hMem
0x180020e4f  call    CflSecureFreeBuffer
0x180020e54  nop
0x180020e55  test    rbx, rbx
0x180020e58  jz      short loc_180020E62
0x180020e5a  mov     rcx, rbx; hMem
0x180020e5d  call    CflFreeBuffer
0x180020e62  mov     eax, r14d
0x180020e65  jmp     loc_180020FDF
0x180020e6a  mov     [rbp+60h+Data], 1
0x180020e74  mov     r15d, 4
0x180020e7a  mov     dword ptr [rsp+160h+samDesired], r15d; cbData
0x180020e7f  lea     rax, [rbp+60h+Data]
0x180020e86  mov     qword ptr [rsp+160h+dwOptions], rax; lpData
0x180020e8b  mov     r9d, r15d; dwType
0x180020e8e  xor     r8d, r8d; Reserved
0x180020e91  lea     rdx, aDefaultaccount; "DefaultAccountAction"
0x180020e98  mov     rcx, [rsp+160h+hKey]; hKey
0x180020e9d  call    cs:__imp_RegSetValueExW
0x180020ea3  test    eax, eax
0x180020ea5  jz      short loc_180020EB1
0x180020ea7  mov     edx, 0E5h
0x180020eac  jmp     loc_180020E14
0x180020eb1  mov     dword ptr [rsp+160h+var_100], 1
0x180020eb9  mov     dword ptr [rsp+160h+samDesired], r15d; cbData
0x180020ebe  lea     rax, [rsp+160h+var_100]
0x180020ec3  mov     qword ptr [rsp+160h+dwOptions], rax; lpData
0x180020ec8  mov     r9d, r15d; dwType
0x180020ecb  xor     r8d, r8d; Reserved
0x180020ece  lea     rdx, aCfltempaccount; "CflTempAccountCreated"
0x180020ed5  mov     rcx, [rsp+160h+hKey]; hKey
0x180020eda  call    cs:__imp_RegSetValueExW
0x180020ee0  test    eax, eax
0x180020ee2  jz      short loc_180020EEE
0x180020ee4  mov     edx, 0EFh
0x180020ee9  jmp     loc_180020E14
0x180020eee  mov     rax, [rsp+160h+username]
0x180020ef3  mov     rcx, [rbp+60h+arg_0]
0x180020ef7  mov     [rcx], rax
0x180020efa  mov     eax, dword ptr [rbp+60h+bufptr]
  ... truncated ...
```
