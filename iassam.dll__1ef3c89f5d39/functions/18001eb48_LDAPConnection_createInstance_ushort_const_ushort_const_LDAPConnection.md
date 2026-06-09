# LDAPConnection::createInstance(ushort const *,ushort const *,LDAPConnection * *)

- ea: `0x18001eb48`
- end: `0x18001f195`
- name: `?createInstance@LDAPConnection@@SAKPEBG0PEAPEAV1@@Z`
- size: `1613`
- prototype: `static unsigned int(const unsigned __int16 *, const unsigned __int16 *, struct LDAPConnection **)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18001fb74`

## callees

- `0x180001c88`
- `0x18000342c`
- `0x18000a760`
- `0x18000c500`
- `0x18000d49c`
- `0x18000e754`
- `0x18001db68`
- `0x18001e11c`
- `0x18001e1ac`
- `0x18001e3fc`
- `0x18001e854`
- `0x18001eb48`
- `0x18001f240`
- `0x1800254a0`
- `0x18002b4a0`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18001eea8`
- `msvcrt!wcscat_s` at `0x18001eea8`
- `KERNEL32!GetLastError` at `0x18001edff`
- `KERNEL32!GetLastError` at `0x18001edff`
- `KERNEL32!InitializeCriticalSection` at `0x18001f044`
- `KERNEL32!InitializeCriticalSection` at `0x18001f044`
- `KERNEL32!GetComputerNameW` at `0x18001edee`
- `KERNEL32!GetComputerNameW` at `0x18001edee`
- `WLDAP32!__imp_ldap_get_optionW` at `0x18001ebef`
- `WLDAP32!__imp_ldap_get_optionW` at `0x18001ed45`
- `WLDAP32!__imp_ldap_get_optionW` at `0x18001ef65`
- `WLDAP32!__imp_ldap_get_optionW` at `0x18001f0ae`
- `WLDAP32!__imp_ldap_get_optionW` at `0x18001ebef`
- `WLDAP32!__imp_ldap_get_optionW` at `0x18001ed45`
- `WLDAP32!__imp_ldap_get_optionW` at `0x18001ef65`
- `WLDAP32!__imp_ldap_get_optionW` at `0x18001f0ae`
- `WLDAP32!__imp_ldap_unbind` at `0x18001ee84`
- `WLDAP32!__imp_ldap_unbind` at `0x18001f15b`
- `WLDAP32!__imp_ldap_unbind` at `0x18001ee84`
- `WLDAP32!__imp_ldap_unbind` at `0x18001f15b`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18001ebcc`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18001ed20`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18001eff4`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18001f00b`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18001f027`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18001ebcc`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18001ed20`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18001eff4`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18001f00b`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18001f027`
- `WLDAP32!__imp_LdapGetLastError` at `0x18001ebaa`
- `WLDAP32!__imp_LdapGetLastError` at `0x18001ebaa`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001f164`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18001f164`
- `WLDAP32!__imp_ldap_bind_sW` at `0x18001ef40`
- `WLDAP32!__imp_ldap_bind_sW` at `0x18001ef40`
- `WLDAP32!__imp_ldap_connect` at `0x18001edcc`
- `WLDAP32!__imp_ldap_connect` at `0x18001edcc`
- `WLDAP32!__imp_ldap_initW` at `0x18001eb9c`
- `WLDAP32!__imp_ldap_initW` at `0x18001eb9c`
- `WLDAP32!__imp_ldap_memfreeW` at `0x18001f152`
- `WLDAP32!__imp_ldap_memfreeW` at `0x18001f152`

## string_xrefs

- `0x18001ee4f`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s`
- `0x18001ec60`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ LDAP ERROR in %s. Code = 0x%X \nExtended error info: %S`
- `0x18001edac`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ LDAP ERROR in %s. Code = 0x%X \nExtended error info: %S`
- `0x18001efcc`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ LDAP ERROR in %s. Code = 0x%X \nExtended error info: %S`
- `0x18001f109`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ LDAP ERROR in %s. Code = 0x%X \nExtended error info: %S`
- `0x18001ee3e`: `GetComputerNameW`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ULONG __fastcall LDAPConnection::createInstance(
        const unsigned __int16 *a1,
        WCHAR *a2,
        struct _RTL_CRITICAL_SECTION **a3)
{
  LDAP *v5; // rax
  LDAP *v6; // rbx
  ULONG LastError; // ecx
  ULONG v8; // r14d
  WCHAR *v9; // rcx
  const wchar_t *v10; // rdi
  const char *v11; // rsi
  DWORD v12; // r14d
  unsigned int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rax
  int v16; // r9d
  PWCHAR v17; // rdi
  const char *v18; // rsi
  const struct std::nothrow_t *v19; // rdx
  struct _RTL_CRITICAL_SECTION *v20; // rax
  struct _RTL_CRITICAL_SECTION *v21; // rdi
  unsigned int RootDSE; // ebx
  BOOL invalue; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR *outvalue; // [rsp+48h] [rbp-B8h] BYREF
  PWCHAR Block; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR cred[4]; // [rsp+58h] [rbp-A8h] BYREF
  int v27; // [rsp+60h] [rbp-A0h]
  __int128 v28; // [rsp+64h] [rbp-9Ch]
  __int128 v29; // [rsp+74h] [rbp-8Ch]
  int v30; // [rsp+84h] [rbp-7Ch]
  wchar_t Buffer[20]; // [rsp+88h] [rbp-78h] BYREF
  char v32[256]; // [rsp+B0h] [rbp-50h] BYREF

  invalue = 0;
  if ( !a3 )
    return 87;
  v5 = ldap_initW(a2, 0x185u);
  v6 = v5;
  if ( !v5 )
  {
    LastError = LdapGetLastError();
    return LdapMapErrorToWin32(LastError);
  }
  invalue = 1;
  v8 = ldap_set_optionW(v5, 152, &invalue);
  if ( v8 )
  {
    outvalue = 0;
    if ( ldap_get_optionW(v6, 51, &outvalue) )
    {
      v9 = 0;
      outvalue = 0;
    }
    else
    {
      v9 = outvalue;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v10 = L"Failed to get extended error info";
      v11 = "ldap_set_optionW(LDAP_OPT_AREC_EXCLUSIVE)";
      WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ LDAP ERROR in %s. Co"
                  "de = 0x%X \n"
                  "Extended error info: %S");
LABEL_13:
      if ( outvalue )
        v10 = outvalue;
      WPP_SF_ssDS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v11, v8, (__int64)v10);
      v9 = outvalue;
      goto LABEL_67;
    }
    goto LABEL_67;
  }
  invalue = LDAPConnection::IsEncryptionDisabled() == 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("Trying to set LDAP encryption = %ld");
    WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_5e533440ec7237f17173738acd6b67e7_Traceguids);
  }
  v8 = ldap_set_optionW(v6, 150, &invalue);
  if ( v8 )
  {
    outvalue = 0;
    if ( ldap_get_optionW(v6, 51, &outvalue) )
    {
      v9 = 0;
      outvalue = 0;
    }
    else
    {
      v9 = outvalue;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v10 = L"Failed to get extended error info";
      v11 = "ldap_set_optionW(LDAP_OPT_ENCRYPT)";
      WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ LDAP ERROR in %s. Co"
                  "de = 0x%X \n"
                  "Extended error info: %S");
      goto LABEL_13;
    }
LABEL_67:
    if ( v9 )
      ldap_memfreeW(v9);
    ldap_unbind(v6);
    LastError = v8;
    return LdapMapErrorToWin32(LastError);
  }
  v8 = ldap_connect(v6, &timeout);
  if ( v8 )
  {
    Block = 0;
    if ( ldap_get_optionW(v6, 51, &Block) )
    {
      v9 = 0;
      Block = 0;
    }
    else
    {
      v9 = Block;
    }
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_67;
    }
    v17 = L"Failed to get extended error info";
    v18 = "ldap_connect";
    WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ LDAP ERROR in %s. Code"
                " = 0x%X \n"
                "Extended error info: %S");
    goto LABEL_64;
  }
  LODWORD(outvalue) = 19;
  if ( !GetComputerNameW(Buffer, (LPDWORD)&outvalue) )
  {
    v12 = GetLastError();
    v13 = IASFormatSysErr(v12, v32);
    if ( v13 >= 0x100uLL )
      _report_rangecheckfailure(v14);
    v32[v13] = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s");
      WPP_SF_sss(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"GetComputerNameW", (__int64)v32);
    }
    goto LABEL_35;
  }
  wcscat_s(Buffer, 0x13u, L"$");
  v28 = 0;
  v29 = 0;
  *(_QWORD *)cred = Buffer;
  v15 = -1;
  do
    ++v15;
  while ( Buffer[v15] );
  v27 = v15;
  v30 = 2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("Setting localServerName.User to %S");
    WPP_SF_sS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      (unsigned int)WPP_5e533440ec7237f17173738acd6b67e7_Traceguids,
      v16,
      *(__int64 *)cred);
  }
  v8 = ldap_bind_sW(v6, 0, cred, 0x486u);
  if ( v8 )
  {
    Block = 0;
    if ( ldap_get_optionW(v6, 51, &Block) )
    {
      v9 = 0;
      Block = 0;
    }
    else
    {
      v9 = Block;
    }
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_67;
    }
    v17 = L"Failed to get extended error info";
    v18 = "ldap_bind_s";
    WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ LDAP ERROR in %s. Code"
                " = 0x%X \n"
                "Extended error info: %S");
LABEL_64:
    if ( Block )
      v17 = Block;
    WPP_SF_ssDS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v18, v8, (__int64)v17);
    v9 = Block;
    goto LABEL_67;
  }
  invalue = 0;
  v12 = 8;
  ldap_set_optionW(v6, 8, &invalue);
  invalue = 0;
  ldap_set_optionW(v6, 145, &invalue);
  invalue = 1;
  ldap_set_optionW(v6, 148, &invalue);
  v20 = (struct _RTL_CRITICAL_SECTION *)operator new[](0x70u, v19);
  v21 = v20;
  if ( !v20 )
  {
LABEL_35:
    ldap_unbind(v6);
    return v12;
  }
  InitializeCriticalSection(v20);
  v21[1].DebugInfo = 0;
  *(_QWORD *)&v21[1].LockCount = 0;
  std::basic_string<unsigned short,std::char_traits<unsigned short>,StdAllocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,StdAllocator<unsigned short>>(&v21[1].OwningThread);
  *(_QWORD *)&v21[2].LockCount = v6;
  LODWORD(v21[2].OwningThread) = 1;
  v21[2].LockSemaphore = 0;
  RootDSE = LDAPConnection::readRootDSE((LDAPConnection *)v21);
  if ( RootDSE || (RootDSE = LDAPConnection::checkAccess((LDAPConnection *)v21)) != 0 )
    LDAPConnection::Release((LDAPConnection *)v21);
  else
    *a3 = v21;
  return RootDSE;
}

```

## disassembly

```asm
0x18001eb48  mov     [rsp-8+arg_0], rbx
0x18001eb4d  push    rbp
0x18001eb4e  push    rsi
0x18001eb4f  push    rdi
0x18001eb50  push    r12
0x18001eb52  push    r13
0x18001eb54  push    r14
0x18001eb56  push    r15
0x18001eb58  lea     rbp, [rsp-0C0h]
0x18001eb60  sub     rsp, 1C0h
0x18001eb67  mov     rax, cs:__security_cookie
0x18001eb6e  xor     rax, rsp
0x18001eb71  mov     [rbp+0F0h+var_40], rax
0x18001eb78  mov     r15, r8
0x18001eb7b  mov     r13, rdx
0x18001eb7e  xor     r12d, r12d
0x18001eb81  mov     [rsp+1F0h+invalue], r12d
0x18001eb86  test    r8, r8
0x18001eb89  jnz     short loc_18001EB94
0x18001eb8b  lea     eax, [r8+57h]
0x18001eb8f  jmp     loc_18001F16B
0x18001eb94  mov     edx, 185h; PortNumber
0x18001eb99  mov     rcx, r13; HostName
0x18001eb9c  call    cs:__imp_ldap_initW
0x18001eba2  mov     rbx, rax
0x18001eba5  test    rax, rax
0x18001eba8  jnz     short loc_18001EBB7
0x18001ebaa  call    cs:__imp_LdapGetLastError
0x18001ebb0  mov     ecx, eax
0x18001ebb2  jmp     loc_18001F164
0x18001ebb7  mov     [rsp+1F0h+invalue], 1
0x18001ebbf  lea     r8, [rsp+1F0h+invalue]; invalue
0x18001ebc4  mov     edx, 98h; option
0x18001ebc9  mov     rcx, rbx; ld
0x18001ebcc  call    cs:__imp_ldap_set_optionW
0x18001ebd2  mov     r14d, eax
0x18001ebd5  test    eax, eax
0x18001ebd7  jz      loc_18001ECAD
0x18001ebdd  mov     [rsp+1F0h+outvalue], r12
0x18001ebe2  lea     r8, [rsp+1F0h+outvalue]; outvalue
0x18001ebe7  mov     edx, 33h ; '3'; option
0x18001ebec  mov     rcx, rbx; ld
0x18001ebef  call    cs:__imp_ldap_get_optionW
0x18001ebf5  test    eax, eax
0x18001ebf7  jz      short loc_18001EC03
0x18001ebf9  mov     rcx, r12
0x18001ebfc  mov     [rsp+1F0h+outvalue], rcx
0x18001ec01  jmp     short loc_18001EC08
0x18001ec03  mov     rcx, [rsp+1F0h+outvalue]
0x18001ec08  lea     rsi, WPP_GLOBAL_Control
0x18001ec0f  mov     rax, cs:WPP_GLOBAL_Control
0x18001ec16  cmp     rax, rsi
0x18001ec19  jz      loc_18001F14D
0x18001ec1f  cmp     byte ptr [rax+19h], 2
0x18001ec23  jb      loc_18001F14D
0x18001ec29  mov     dil, 4
0x18001ec2c  test    [rax+1Ch], dil
0x18001ec30  jz      loc_18001F14D
0x18001ec36  lea     rdi, aFailedToGetExt; "Failed to get extended error info"
0x18001ec3d  mov     rax, rdi
0x18001ec40  test    rcx, rcx
0x18001ec43  cmovnz  rax, rcx
0x18001ec47  mov     [rsp+1F0h+var_1D0], rax
0x18001ec4c  mov     r9d, r14d
0x18001ec4f  lea     rsi, aLdapSetOptionw_0; "ldap_set_optionW(LDAP_OPT_AREC_EXCLUSIV"...
0x18001ec56  mov     r8, rsi
0x18001ec59  lea     rdx, aNpssvc; "NPSSVC"
0x18001ec60  lea     rcx, aCpuPidTidNowSL_1; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x18001ec67  call    WppDbgPrint
0x18001ec6c  mov     edx, 0Ah
0x18001ec71  lea     r8, WPP_5e533440ec7237f17173738acd6b67e7_Traceguids
0x18001ec78  mov     rax, [rsp+1F0h+outvalue]
0x18001ec7d  test    rax, rax
0x18001ec80  cmovnz  rdi, rax
0x18001ec84  mov     [rsp+1F0h+var_1C0], rdi; __int64
0x18001ec89  mov     dword ptr [rsp+1F0h+var_1C8], r14d; char
0x18001ec8e  mov     [rsp+1F0h+var_1D0], rsi; __int64
0x18001ec93  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ec9a  mov     rcx, [rcx+10h]; LoggerHandle
0x18001ec9e  call    WPP_SF_ssDS
0x18001eca3  mov     rcx, [rsp+1F0h+outvalue]
0x18001eca8  jmp     loc_18001F14D
0x18001ecad  call    ?IsEncryptionDisabled@LDAPConnection@@KAHXZ; LDAPConnection::IsEncryptionDisabled(void)
0x18001ecb2  mov     edx, r12d
0x18001ecb5  test    eax, eax
0x18001ecb7  setz    dl
0x18001ecba  mov     [rsp+1F0h+invalue], edx
0x18001ecbe  lea     rsi, WPP_GLOBAL_Control
0x18001ecc5  lea     r12, WPP_5e533440ec7237f17173738acd6b67e7_Traceguids
0x18001eccc  mov     dil, 4
0x18001eccf  mov     rax, cs:WPP_GLOBAL_Control
0x18001ecd6  cmp     rax, rsi
0x18001ecd9  jz      short loc_18001ED13
0x18001ecdb  cmp     [rax+19h], dil
0x18001ecdf  jb      short loc_18001ED13
0x18001ece1  test    [rax+1Ch], dil
0x18001ece5  jz      short loc_18001ED13
0x18001ece7  lea     rcx, aTryingToSetLda; "Trying to set LDAP encryption = %ld"
0x18001ecee  call    WppDbgPrint
0x18001ecf3  mov     edx, 0Bh
0x18001ecf8  mov     eax, [rsp+1F0h+invalue]
0x18001ecfc  mov     dword ptr [rsp+1F0h+var_1D0], eax
0x18001ed00  mov     r8, r12
0x18001ed03  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ed0a  mov     rcx, [rcx+10h]
0x18001ed0e  call    WPP_SF_sd
0x18001ed13  lea     r8, [rsp+1F0h+invalue]; invalue
0x18001ed18  mov     edx, 96h; option
0x18001ed1d  mov     rcx, rbx; ld
0x18001ed20  call    cs:__imp_ldap_set_optionW
0x18001ed26  mov     r14d, eax
0x18001ed29  mov     rcx, rbx; ld
0x18001ed2c  test    eax, eax
0x18001ed2e  jz      loc_18001EDC5
0x18001ed34  xor     r15d, r15d
0x18001ed37  mov     [rsp+1F0h+outvalue], r15
0x18001ed3c  lea     r8, [rsp+1F0h+outvalue]; outvalue
0x18001ed41  lea     edx, [r15+33h]; option
0x18001ed45  call    cs:__imp_ldap_get_optionW
0x18001ed4b  test    eax, eax
0x18001ed4d  jz      short loc_18001ED59
0x18001ed4f  mov     ecx, r15d
0x18001ed52  mov     [rsp+1F0h+outvalue], rcx
0x18001ed57  jmp     short loc_18001ED5E
0x18001ed59  mov     rcx, [rsp+1F0h+outvalue]
0x18001ed5e  mov     rax, cs:WPP_GLOBAL_Control
0x18001ed65  cmp     rax, rsi
0x18001ed68  jz      loc_18001F14D
0x18001ed6e  cmp     byte ptr [rax+19h], 2
0x18001ed72  jb      loc_18001F14D
0x18001ed78  test    [rax+1Ch], dil
0x18001ed7c  jz      loc_18001F14D
0x18001ed82  lea     rdi, aFailedToGetExt; "Failed to get extended error info"
0x18001ed89  mov     rax, rdi
0x18001ed8c  test    rcx, rcx
0x18001ed8f  cmovnz  rax, rcx
0x18001ed93  mov     [rsp+1F0h+var_1D0], rax
0x18001ed98  mov     r9d, r14d
0x18001ed9b  lea     rsi, aLdapSetOptionw; "ldap_set_optionW(LDAP_OPT_ENCRYPT)"
0x18001eda2  mov     r8, rsi
0x18001eda5  lea     rdx, aNpssvc; "NPSSVC"
0x18001edac  lea     rcx, aCpuPidTidNowSL_1; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x18001edb3  call    WppDbgPrint
0x18001edb8  mov     edx, 0Ch
0x18001edbd  mov     r8, r12
0x18001edc0  jmp     loc_18001EC78
0x18001edc5  lea     rdx, timeout; timeout
0x18001edcc  call    cs:__imp_ldap_connect
0x18001edd2  mov     r14d, eax
0x18001edd5  test    eax, eax
0x18001edd7  jnz     loc_18001F09A
0x18001eddd  mov     dword ptr [rsp+1F0h+outvalue], 13h
0x18001ede5  lea     rdx, [rsp+1F0h+outvalue]; nSize
0x18001edea  lea     rcx, [rbp+0F0h+Buffer]; lpBuffer
0x18001edee  call    cs:__imp_GetComputerNameW
0x18001edf4  xor     r14d, r14d
0x18001edf7  test    eax, eax
0x18001edf9  jnz     loc_18001EE98
0x18001edff  call    cs:__imp_GetLastError
0x18001ee05  mov     r14d, eax
0x18001ee08  lea     rdx, [rbp+0F0h+var_140]; Buffer
0x18001ee0c  mov     ecx, eax; dwMessageId
0x18001ee0e  call    IASFormatSysErr
0x18001ee13  mov     eax, eax
0x18001ee15  cmp     rax, 100h
0x18001ee1b  jnb     short loc_18001EE92
0x18001ee1d  mov     [rbp+rax+0F0h+var_140], 0
0x18001ee22  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ee29  cmp     rcx, rsi
0x18001ee2c  jz      short loc_18001EE81
0x18001ee2e  cmp     byte ptr [rcx+19h], 2
0x18001ee32  jb      short loc_18001EE81
0x18001ee34  test    [rcx+1Ch], dil
0x18001ee38  jz      short loc_18001EE81
0x18001ee3a  lea     r9, [rbp+0F0h+var_140]
0x18001ee3e  lea     rdi, aGetcomputernam; "GetComputerNameW"
0x18001ee45  mov     r8, rdi
0x18001ee48  lea     rdx, aNpssvc; "NPSSVC"
0x18001ee4f  lea     rcx, aCpuPidTidNowSL; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x18001ee56  call    WppDbgPrint
0x18001ee5b  mov     edx, 0Dh
0x18001ee60  lea     rax, [rbp+0F0h+var_140]
0x18001ee64  mov     qword ptr [rsp+1F0h+var_1C8], rax; __int64
0x18001ee69  mov     [rsp+1F0h+var_1D0], rdi; __int64
0x18001ee6e  mov     r8, r12
0x18001ee71  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ee78  mov     rcx, [rcx+10h]; LoggerHandle
0x18001ee7c  call    WPP_SF_sss
0x18001ee81  mov     rcx, rbx; ld
0x18001ee84  call    cs:__imp_ldap_unbind
0x18001ee8a  mov     eax, r14d
0x18001ee8d  jmp     loc_18001F16B
0x18001ee92  call    __report_rangecheckfailure
0x18001ee98  lea     r8, asc_180036354; "$"
0x18001ee9f  mov     edx, 13h; SizeInWords
0x18001eea4  lea     rcx, [rbp+0F0h+Buffer]; Destination
0x18001eea8  call    cs:__imp_wcscat_s
0x18001eeae  xorps   xmm0, xmm0
0x18001eeb1  movdqu  [rsp+1F0h+var_18C], xmm0
0x18001eeb7  xorps   xmm1, xmm1
0x18001eeba  movdqu  [rsp+1F0h+var_17C], xmm1
0x18001eec0  lea     rax, [rbp+0F0h+Buffer]
0x18001eec4  mov     qword ptr [rsp+1F0h+cred], rax
0x18001eec9  lea     rcx, [rbp+0F0h+Buffer]
0x18001eecd  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001eed1  inc     rax
0x18001eed4  cmp     [rcx+rax*2], r14w
0x18001eed9  jnz     short loc_18001EED1
0x18001eedb  mov     [rsp+1F0h+var_190], eax
0x18001eedf  mov     [rbp+0F0h+var_16C], 2
0x18001eee6  mov     rax, cs:WPP_GLOBAL_Control
0x18001eeed  cmp     rax, rsi
0x18001eef0  jz      short loc_18001EF30
0x18001eef2  cmp     [rax+19h], dil
0x18001eef6  jb      short loc_18001EF30
0x18001eef8  test    [rax+1Ch], dil
0x18001eefc  jz      short loc_18001EF30
0x18001eefe  lea     rdx, [rbp+0F0h+Buffer]
0x18001ef02  lea     rcx, aSettingLocalse; "Setting localServerName.User to %S"
0x18001ef09  call    WppDbgPrint
0x18001ef0e  mov     edx, 0Eh
0x18001ef13  mov     rax, qword ptr [rsp+1F0h+cred]
0x18001ef18  mov     [rsp+1F0h+var_1D0], rax
0x18001ef1d  mov     r8, r12
0x18001ef20  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ef27  mov     rcx, [rcx+10h]
0x18001ef2b  call    WPP_SF_sS
0x18001ef30  mov     r9d, 486h; method
0x18001ef36  lea     r8, [rsp+1F0h+cred]; cred
0x18001ef3b  xor     edx, edx; dn
0x18001ef3d  mov     rcx, rbx; ld
0x18001ef40  call    cs:__imp_ldap_bind_sW
0x18001ef46  mov     r14d, eax
0x18001ef49  mov     rcx, rbx; ld
0x18001ef4c  test    eax, eax
0x18001ef4e  jz      loc_18001EFE2
0x18001ef54  xor     r15d, r15d
0x18001ef57  mov     [rsp+1F0h+Block], r15
0x18001ef5c  lea     r8, [rsp+1F0h+Block]; outvalue
0x18001ef61  lea     edx, [r15+33h]; option
0x18001ef65  call    cs:__imp_ldap_get_optionW
0x18001ef6b  test    eax, eax
0x18001ef6d  jz      short loc_18001EF79
0x18001ef6f  mov     ecx, r15d
0x18001ef72  mov     [rsp+1F0h+Block], rcx
0x18001ef77  jmp     short loc_18001EF7E
0x18001ef79  mov     rcx, [rsp+1F0h+Block]
0x18001ef7e  mov     rax, cs:WPP_GLOBAL_Control
0x18001ef85  cmp     rax, rsi
0x18001ef88  jz      loc_18001F14D
0x18001ef8e  cmp     byte ptr [rax+19h], 2
0x18001ef92  jb      loc_18001F14D
0x18001ef98  test    [rax+1Ch], dil
0x18001ef9c  jz      loc_18001F14D
0x18001efa2  lea     rdi, aFailedToGetExt; "Failed to get extended error info"
0x18001efa9  mov     rax, rdi
0x18001efac  test    rcx, rcx
0x18001efaf  cmovnz  rax, rcx
0x18001efb3  mov     [rsp+1F0h+var_1D0], rax
0x18001efb8  mov     r9d, r14d
0x18001efbb  lea     rsi, aLdapBindS; "ldap_bind_s"
0x18001efc2  mov     r8, rsi
0x18001efc5  lea     rdx, aNpssvc; "NPSSVC"
0x18001efcc  lea     rcx, aCpuPidTidNowSL_1; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x18001efd3  call    WppDbgPrint
0x18001efd8  mov     edx, 0Fh
0x18001efdd  jmp     loc_18001F11A
0x18001efe2  xor     esi, esi
0x18001efe4  mov     [rsp+1F0h+invalue], esi
0x18001efe8  lea     r8, [rsp+1F0h+invalue]; invalue
0x18001efed  lea     r14d, [rsi+8]
0x18001eff1  mov     edx, r14d; option
0x18001eff4  call    cs:__imp_ldap_set_optionW
0x18001effa  mov     [rsp+1F0h+invalue], esi
0x18001effe  lea     r8, [rsp+1F0h+invalue]; invalue
0x18001f003  mov     edx, 91h; option
0x18001f008  mov     rcx, rbx; ld
0x18001f00b  call    cs:__imp_ldap_set_optionW
0x18001f011  lea     r12d, [rsi+1]
0x18001f015  mov     [rsp+1F0h+invalue], r12d
0x18001f01a  lea     r8, [rsp+1F0h+invalue]; invalue
0x18001f01f  mov     edx, 94h; option
0x18001f024  mov     rcx, rbx; ld
0x18001f027  call    cs:__imp_ldap_set_optionW
0x18001f02d  lea     ecx, [rsi+70h]; Size
0x18001f030  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001f035  mov     rdi, rax
0x18001f038  test    rax, rax
0x18001f03b  jz      loc_18001EE81
0x18001f041  mov     rcx, rax; lpCriticalSection
0x18001f044  call    cs:__imp_InitializeCriticalSection
0x18001f04a  mov     [rdi+28h], rsi
0x18001f04e  mov     [rdi+30h], rsi
0x18001f052  lea     rcx, [rdi+38h]; void *
0x18001f056  mov     rdx, r13
0x18001f059  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$StdAllocator@G@@@std@@QEAA@PEBG@Z; std::basic_string<ushort,std::char_traits<ushort>,StdAllocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,StdAllocator<ushort>>(ushort const *)
0x18001f05e  mov     [rdi+58h], rbx
0x18001f062  mov     [rdi+60h], r12d
0x18001f066  mov     [rdi+68h], rsi
0x18001f06a  mov     rcx, rdi; this
  ... truncated ...
```
