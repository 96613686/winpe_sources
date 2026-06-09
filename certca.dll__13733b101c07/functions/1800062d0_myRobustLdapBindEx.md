# myRobustLdapBindEx

- ea: `0x1800062d0`
- end: `0x180006987`
- name: `myRobustLdapBindEx`
- size: `1719`
- prototype: `__int64 __fastcall(char, const unsigned __int16 *, const unsigned __int16 *, const WCHAR *, LDAP **, unsigned __int16 **)`
- caller_count: `12`
- callee_count: `10`
- tags: ``

## callers

- `0x18000a630`
- `0x18000a920`
- `0x180012680`
- `0x180029750`
- `0x18002ef70`
- `0x18002fc24`
- `0x180030224`
- `0x180033f70`
- `0x1800356b8`
- `0x180035bd0`
- `0x180035da8`
- `0x1800365a4`

## callees

- `0x1800062d0`
- `0x180006990`
- `0x180008610`
- `0x18000a3b0`
- `0x18000dce0`
- `0x18000eac0`
- `0x1800115cc`
- `0x180011600`
- `0x180017990`
- `0x180029630`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006959`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006959`
- `WLDAP32!__imp_ldap_get_optionW` at `0x18000673b`
- `WLDAP32!__imp_ldap_get_optionW` at `0x18000676b`
- `WLDAP32!__imp_ldap_get_optionW` at `0x180006828`
- `WLDAP32!__imp_ldap_get_optionW` at `0x18000673b`
- `WLDAP32!__imp_ldap_get_optionW` at `0x18000676b`
- `WLDAP32!__imp_ldap_get_optionW` at `0x180006828`
- `WLDAP32!__imp_ldap_unbind` at `0x180006444`
- `WLDAP32!__imp_ldap_unbind` at `0x180006967`
- `WLDAP32!__imp_ldap_unbind` at `0x180006444`
- `WLDAP32!__imp_ldap_unbind` at `0x180006967`
- `WLDAP32!__imp_ldap_set_optionW` at `0x1800064d0`
- `WLDAP32!__imp_ldap_set_optionW` at `0x180006512`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18000655f`
- `WLDAP32!__imp_ldap_set_optionW` at `0x1800065a9`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18000664c`
- `WLDAP32!__imp_ldap_set_optionW` at `0x180006690`
- `WLDAP32!__imp_ldap_set_optionW` at `0x1800066d2`
- `WLDAP32!__imp_ldap_set_optionW` at `0x1800064d0`
- `WLDAP32!__imp_ldap_set_optionW` at `0x180006512`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18000655f`
- `WLDAP32!__imp_ldap_set_optionW` at `0x1800065a9`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18000664c`
- `WLDAP32!__imp_ldap_set_optionW` at `0x180006690`
- `WLDAP32!__imp_ldap_set_optionW` at `0x1800066d2`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180006789`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180006789`
- `WLDAP32!__imp_ldap_bind_sW` at `0x180006710`
- `WLDAP32!__imp_ldap_bind_sW` at `0x180006710`
- `WLDAP32!__imp_ldap_initW` at `0x18000647a`
- `WLDAP32!__imp_ldap_initW` at `0x18000647a`
- `WLDAP32!__imp_ldap_memfreeW` at `0x1800067e6`
- `WLDAP32!__imp_ldap_memfreeW` at `0x1800067e6`

## pseudocode

```c
__int64 __fastcall myRobustLdapBindEx(
        char a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const WCHAR *a4,
        LDAP **a5,
        unsigned __int16 **a6)
{
  int v8; // edi
  int CertRegDWValue; // eax
  int v10; // ecx
  LDAP *v11; // rsi
  int v12; // eax
  unsigned int v13; // r14d
  int v14; // edi
  int v15; // eax
  unsigned int v16; // ebx
  int TargetMachineDomainDnsName; // eax
  WCHAR *v18; // rax
  char v19; // bl
  int v20; // r13d
  ULONG v21; // edx
  LDAP *v22; // rax
  unsigned __int16 **v23; // rdx
  int Error; // eax
  int v25; // r8d
  unsigned int v26; // edx
  int v27; // r9d
  ULONG v28; // eax
  unsigned int v29; // edx
  unsigned int v30; // ecx
  unsigned int v31; // r9d
  ULONG v32; // eax
  unsigned int v33; // r9d
  int v34; // eax
  ULONG v35; // eax
  unsigned int v36; // r9d
  ULONG v37; // eax
  unsigned int v38; // r9d
  int v39; // eax
  ULONG v40; // eax
  unsigned int v41; // r9d
  ULONG v42; // eax
  unsigned int v43; // r9d
  ULONG v44; // eax
  unsigned int v45; // r9d
  ULONG v46; // ebx
  ULONG optionW; // eax
  ULONG v48; // eax
  ULONG v49; // eax
  ULONG v50; // eax
  unsigned int v51; // r9d
  int v52; // eax
  unsigned __int16 **v54; // [rsp+20h] [rbp-50h]
  ULONG v55; // [rsp+30h] [rbp-40h] BYREF
  int v56; // [rsp+34h] [rbp-3Ch]
  WCHAR *v57; // [rsp+38h] [rbp-38h]
  int invalue; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int16 *outvalue; // [rsp+48h] [rbp-28h] BYREF
  int v60; // [rsp+50h] [rbp-20h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-18h] BYREF
  unsigned __int16 **v62; // [rsp+60h] [rbp-10h]
  LDAP **v63; // [rsp+68h] [rbp-8h]

  v63 = a5;
  v62 = a6;
  v57 = (WCHAR *)a4;
  v8 = (int)a2;
  v60 = (int)a3;
  invalue = 0;
  v55 = 0;
  CertRegDWValue = myGetCertRegDWValue(0, a2, a3, L"LDAPFlags", &v55);
  if ( CertRegDWValue )
  {
    CSPrintErrorLineFileData2(L"LDAPFlags", 0xCF01ADu, CertRegDWValue, -2147024894);
    v56 = 0;
  }
  else
  {
    v56 = v55;
  }
  hMem = 0;
  v10 = v8 | 2;
  v11 = 0;
  v12 = 0x40000000;
  invalue = 0x40000000;
  if ( (a1 & 1) == 0 )
    v10 = v8;
  v13 = v10 | 4;
  if ( (v10 & 1) == 0 )
    v13 = v10;
  v14 = (v13 >> 2) & 1;
  if ( (v13 & 2) != 0 )
  {
    v12 = 1073741888;
    invalue = 1073741888;
  }
  if ( (v13 & 0x40) != 0 )
    invalue = v12 | 0x1000;
  if ( (v13 & 0x100) == 0 )
  {
    if ( (v13 & 0x80u) != 0 || !a4 )
    {
      TargetMachineDomainDnsName = myGetTargetMachineDomainDnsName(a4, 0, (unsigned __int16 **)&hMem, 0);
      v16 = TargetMachineDomainDnsName;
      if ( TargetMachineDomainDnsName )
      {
        CSPrintErrorLineFileData2(0, 0x124032Cu, TargetMachineDomainDnsName, 0);
        goto LABEL_107;
      }
      v18 = (WCHAR *)a4;
      if ( !a4 )
      {
        if ( (v13 & 2) == 0 )
          v18 = (WCHAR *)hMem;
        v57 = v18;
      }
      goto LABEL_24;
    }
    v15 = myDupString(a4, (unsigned __int16 **)&hMem);
    v16 = v15;
    if ( v15 )
    {
      CSPrintErrorLineFileData2(0, 0x11C032Cu, v15, 0);
      goto LABEL_107;
    }
  }
  v18 = (WCHAR *)a4;
LABEL_24:
  v19 = v56;
  v20 = v56 & 1;
  while ( 1 )
  {
    if ( v11 )
    {
      ldap_unbind(v11);
      v18 = v57;
    }
    if ( v20 )
    {
      v21 = 3269;
      if ( (v13 & 2) == 0 )
        v21 = 636;
    }
    else
    {
      v21 = 389;
      if ( (v13 & 2) != 0 )
        v21 = 3268;
    }
    v22 = ldap_initW(v18, v21);
    v11 = v22;
    if ( !v22 )
    {
      Error = myHLdapLastError(0, v23);
      v16 = Error;
      v25 = Error;
      if ( v14 )
      {
        CSPrintErrorLineFileData2(0, 0x148032Cu, Error, 0);
        goto LABEL_107;
      }
      v26 = 21234476;
LABEL_36:
      v27 = Error;
      goto LABEL_37;
    }
    if ( v14 )
      invalue |= 1u;
    v28 = ldap_set_optionW(v22, 61, &invalue);
    if ( v28 )
    {
      Error = myHLdapError3(v11, v28, 0, v31, v54);
      v16 = Error;
      v25 = Error;
      if ( v14 )
      {
        CSPrintErrorLineFileData2(0, 0x15C032Cu, Error, 0);
        goto LABEL_107;
      }
      v26 = 22545196;
      goto LABEL_36;
    }
    if ( v60 )
    {
      if ( v60 == 2 )
        goto LABEL_52;
    }
    else
    {
      v32 = ldap_set_optionW(v11, 64, (const void *)1);
      if ( v32 )
      {
        v34 = myHLdapError3(v11, v32, 0, v33, v54);
        v16 = v34;
        v27 = v34;
        v25 = v34;
        if ( v14 )
        {
          CSPrintErrorLineFileData2(0, 0x16D032Cu, v34, v34);
          goto LABEL_107;
        }
        v26 = 23659308;
        goto LABEL_37;
      }
      v60 = 3;
    }
    v35 = ldap_set_optionW(v11, 17, &v60);
    if ( v35 )
    {
      Error = myHLdapError3(v11, v35, 0, v36, v54);
      v16 = Error;
      v25 = Error;
      if ( v14 )
      {
        CSPrintErrorLineFileData2(0, 0x185032Cu, Error, 0);
        goto LABEL_107;
      }
      v26 = 25232172;
      goto LABEL_36;
    }
LABEL_52:
    if ( (v13 & 0x80u) != 0 )
    {
      if ( v57 )
      {
        v37 = ldap_set_optionW(v11, 152, (const void *)1);
        if ( v37 )
        {
          Error = myHLdapError3(v11, v37, 0, v38, v54);
          v16 = Error;
          v25 = Error;
          if ( v14 )
          {
            CSPrintErrorLineFileData2(0, 0x196032Cu, Error, 0);
            goto LABEL_107;
          }
          v26 = 26346284;
          goto LABEL_36;
        }
      }
    }
    if ( (v19 & 2) == 0 && _IsWinXXOrNewer(v30, v29) )
    {
      v55 = 1;
      if ( (v13 & 0x10) == 0 )
        goto LABEL_65;
      v39 = DCSupportsSigning(v11, (int *)&v55);
      v16 = v39;
      if ( v39 )
      {
        CSPrintErrorLineFileData2(0, 0x1A3032Cu, v39, 0);
        goto LABEL_107;
      }
      if ( v55 )
      {
LABEL_65:
        v40 = ldap_set_optionW(v11, 149, (const void *)1);
        if ( v40 )
        {
          Error = myHLdapError3(v11, v40, 0x59u, v41, v54);
          v16 = Error;
          v25 = Error;
          if ( v14 )
          {
            CSPrintErrorLineFileData2(0, 0x1B1032Cu, Error, 0);
            goto LABEL_107;
          }
          v26 = 28115756;
          goto LABEL_36;
        }
      }
      else if ( !v20 && (v13 & 8) != 0 )
      {
        v16 = -2146877421;
        CSPrintErrorLineFileData2(0, 0x1B9032Cu, -2146877421, 0);
        goto LABEL_107;
      }
    }
    if ( (v13 & 0x100) == 0 )
    {
      v42 = ldap_set_optionW(v11, 59, &hMem);
      if ( v42 )
      {
        Error = myHLdapError3(v11, v42, 0, v43, v54);
        v16 = Error;
        v25 = Error;
        if ( v14 )
        {
          CSPrintErrorLineFileData2(0, 0x1CC032Cu, Error, 0);
          goto LABEL_107;
        }
        v26 = 29885228;
        goto LABEL_36;
      }
    }
    if ( (v13 & 0x200) != 0 )
    {
      v44 = ldap_set_optionW(v11, 145, 0);
      if ( v44 )
      {
        Error = myHLdapError3(v11, v44, 0, v45, v54);
        v16 = Error;
        v25 = Error;
        if ( v14 )
        {
          CSPrintErrorLineFileData2(0, 0x1E0032Cu, Error, 0);
          goto LABEL_107;
        }
        v26 = 31195948;
        goto LABEL_36;
      }
    }
    v46 = ldap_bind_sW(v11, 0, 0, 0x486u);
    if ( !v46 )
      break;
    v55 = 0;
    outvalue = 0;
    optionW = ldap_get_optionW(v11, 51, &outvalue);
    if ( optionW )
    {
      CSPrintErrorLineFileData2(0, 0xAB501ADu, optionW, 0);
      outvalue = 0;
    }
    v48 = ldap_get_optionW(v11, 52, &v55);
    if ( v48 )
    {
      CSPrintErrorLineFileData2(0, 0xABF01ADu, v48, v48);
      v49 = LdapMapErrorToWin32(v46);
      v55 = v49;
    }
    else
    {
      v49 = v55;
      if ( !v55 )
      {
        v55 = -2147016555;
        CSPrintErrorLineFileData2(L"LDAP_OPT_SERVER_EXT_ERROR", 0xACA01ADu, -2147016555, 0);
        v49 = v55;
      }
    }
    v55 = myHError(v49);
    CSPrintErrorLineFileData2(outvalue, 0xADA01ADu, v46, 0);
    if ( outvalue )
      ldap_memfreeW(outvalue);
    v16 = v55;
    v25 = v55;
    if ( v14 )
    {
      CSPrintErrorLineFileData2(0, 0x1EE032Cu, v55, 0);
      goto LABEL_107;
    }
    v27 = v55;
    v26 = 32113452;
LABEL_37:
    CSPrintErrorLineFileData2(0, v26, v25, v27);
    v18 = v57;
    v14 = 1;
    v19 = v56;
  }
  if ( !v62 )
    goto LABEL_106;
  outvalue = 0;
  v50 = ldap_get_optionW(v11, 48, &outvalue);
  if ( v50 )
    outvalue = 0;
  Error = myHLdapError3(v11, v50, 0, v51, v54);
  v16 = Error;
  if ( Error )
  {
    v25 = Error;
    if ( v14 )
    {
      CSPrintErrorLineFileData2(0, 0x1FE032Cu, Error, 0);
      goto LABEL_107;
    }
    v26 = 33162028;
    goto LABEL_36;
  }
  v52 = myDupString(outvalue, v62);
  v16 = v52;
  if ( v52 )
  {
    CSPrintErrorLineFileData2(0, 0x201032Cu, v52, 0);
    goto LABEL_107;
  }
LABEL_106:
  *v63 = v11;
  v11 = 0;
  v16 = 0;
LABEL_107:
  if ( hMem )
    LocalFree(hMem);
  if ( v11 )
    ldap_unbind(v11);
  return v16;
}

```

## disassembly

```asm
0x1800062d0  mov     [rsp-38h+arg_0], rbx
0x1800062d5  push    rbp
0x1800062d6  push    rsi
0x1800062d7  push    rdi
0x1800062d8  push    r12
0x1800062da  push    r13
0x1800062dc  push    r14
0x1800062de  push    r15
0x1800062e0  mov     rbp, rsp
0x1800062e3  sub     rsp, 70h
0x1800062e7  mov     rax, [rbp+arg_20]
0x1800062eb  mov     r13, r9
0x1800062ee  mov     [rbp+var_8], rax
0x1800062f2  mov     ebx, ecx
0x1800062f4  mov     rax, [rbp+arg_28]
0x1800062f8  xor     r14d, r14d
0x1800062fb  mov     [rbp+var_10], rax
0x1800062ff  xor     ecx, ecx; unsigned __int16 *
0x180006301  lea     rax, [rbp+var_40]
0x180006305  mov     [rbp+var_38], r9
0x180006309  lea     r9, aLdapflags; "LDAPFlags"
0x180006310  mov     [rsp+70h+var_50], rax; unsigned __int16 **
0x180006315  mov     edi, edx
0x180006317  mov     [rbp+var_20], r8d
0x18000631b  mov     [rbp+invalue], r14d
0x18000631f  mov     dword ptr [rbp+var_40], r14d
0x180006323  call    ?myGetCertRegDWValue@@YAJPEBG000PEAK@Z; myGetCertRegDWValue(ushort const *,ushort const *,ushort const *,ushort const *,ulong *)
0x180006328  test    eax, eax
0x18000632a  jz      short loc_18000634C
0x18000632c  mov     r9d, 80070002h; int
0x180006332  lea     rcx, aLdapflags; "LDAPFlags"
0x180006339  mov     r8d, eax; int
0x18000633c  mov     edx, 0CF01ADh; unsigned int
0x180006341  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180006346  mov     dword ptr [rbp+var_40+4], r14d
0x18000634a  jmp     short loc_180006352
0x18000634c  mov     eax, dword ptr [rbp+var_40]
0x18000634f  mov     dword ptr [rbp+var_40+4], eax
0x180006352  mov     ecx, edi
0x180006354  mov     [rbp+hMem], r14
0x180006358  or      ecx, 2
0x18000635b  mov     rsi, r14
0x18000635e  test    bl, 1
0x180006361  mov     eax, 40000000h
0x180006366  mov     [rbp+invalue], eax
0x180006369  cmovz   ecx, edi
0x18000636c  mov     r14d, ecx
0x18000636f  or      r14d, 4
0x180006373  test    cl, 1
0x180006376  cmovz   r14d, ecx
0x18000637a  mov     edi, r14d
0x18000637d  mov     r12d, r14d
0x180006380  shr     edi, 2
0x180006383  and     edi, 1
0x180006386  and     r12d, 2
0x18000638a  jz      short loc_180006394
0x18000638c  mov     eax, 40000040h
0x180006391  mov     [rbp+invalue], eax
0x180006394  test    r14b, 40h
0x180006398  jz      short loc_1800063A1
0x18000639a  bts     eax, 0Ch
0x18000639e  mov     [rbp+invalue], eax
0x1800063a1  mov     r15d, r14d
0x1800063a4  and     r15d, 100h
0x1800063ab  jnz     short loc_180006424
0x1800063ad  test    r14b, r14b
0x1800063b0  js      short loc_1800063E0
0x1800063b2  test    r13, r13
0x1800063b5  jz      short loc_1800063E0
0x1800063b7  lea     rdx, [rbp+hMem]; unsigned __int16 **
0x1800063bb  mov     rcx, r13; Src
0x1800063be  call    ?myDupString@@YAJPEBGPEAPEAG@Z; myDupString(ushort const *,ushort * *)
0x1800063c3  mov     ebx, eax
0x1800063c5  test    eax, eax
0x1800063c7  jz      short loc_180006424
0x1800063c9  xor     r9d, r9d; int
0x1800063cc  mov     r8d, eax; int
0x1800063cf  mov     edx, 11C032Ch; unsigned int
0x1800063d4  xor     ecx, ecx; unsigned __int16 *
0x1800063d6  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x1800063db  jmp     loc_180006950
0x1800063e0  xor     r9d, r9d; unsigned __int16 **
0x1800063e3  lea     r8, [rbp+hMem]; unsigned __int16 **
0x1800063e7  xor     edx, edx; unsigned __int16 **
0x1800063e9  mov     rcx, r13; lpString
0x1800063ec  call    ?myGetTargetMachineDomainDnsName@@YAJPEBGPEAPEAG11@Z; myGetTargetMachineDomainDnsName(ushort const *,ushort * *,ushort * *,ushort * *)
0x1800063f1  mov     ebx, eax
0x1800063f3  test    eax, eax
0x1800063f5  jz      short loc_18000640E
0x1800063f7  xor     r9d, r9d; int
0x1800063fa  mov     r8d, eax; int
0x1800063fd  mov     edx, 124032Ch; unsigned int
0x180006402  xor     ecx, ecx; unsigned __int16 *
0x180006404  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180006409  jmp     loc_180006950
0x18000640e  mov     rax, r13
0x180006411  test    rax, rax
0x180006414  jnz     short loc_180006427
0x180006416  test    r12d, r12d
0x180006419  cmovz   rax, [rbp+hMem]
0x18000641e  mov     [rbp+var_38], rax
0x180006422  jmp     short loc_180006427
0x180006424  mov     rax, r13
0x180006427  mov     ebx, dword ptr [rbp+var_40+4]
0x18000642a  mov     r13d, ebx
0x18000642d  and     r13d, 1
0x180006431  mov     ecx, 27Ch
0x180006436  mov     r8d, 0CC4h
0x18000643c  test    rsi, rsi
0x18000643f  jz      short loc_180006459
0x180006441  mov     rcx, rsi; ld
0x180006444  call    cs:__imp_ldap_unbind
0x18000644a  mov     rax, [rbp+var_38]
0x18000644e  mov     ecx, 27Ch
0x180006453  mov     r8d, 0CC4h
0x180006459  test    r13d, r13d
0x18000645c  jz      short loc_18000646B
0x18000645e  test    r12d, r12d
0x180006461  mov     edx, 0CC5h
0x180006466  cmovz   edx, ecx
0x180006469  jmp     short loc_180006477
0x18000646b  test    r12d, r12d
0x18000646e  mov     edx, 185h
0x180006473  cmovnz  edx, r8d; PortNumber
0x180006477  mov     rcx, rax; HostName
0x18000647a  call    cs:__imp_ldap_initW
0x180006480  mov     rsi, rax
0x180006483  test    rax, rax
0x180006486  jnz     short loc_1800064BC
0x180006488  xor     ecx, ecx; struct ldap *
0x18000648a  call    ?myHLdapLastError@@YAJPEAUldap@@PEAPEAG@Z; myHLdapLastError(ldap *,ushort * *)
0x18000648f  xor     ecx, ecx; unsigned __int16 *
0x180006491  mov     ebx, eax
0x180006493  mov     r8d, eax; int
0x180006496  test    edi, edi
0x180006498  jnz     loc_180006868
0x18000649e  mov     edx, 144032Ch; unsigned int
0x1800064a3  mov     r9d, eax; int
0x1800064a6  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x1800064ab  mov     rax, [rbp+var_38]
0x1800064af  mov     edi, 1
0x1800064b4  mov     ebx, dword ptr [rbp+var_40+4]
0x1800064b7  jmp     loc_180006431
0x1800064bc  test    edi, edi
0x1800064be  jz      short loc_1800064C4
0x1800064c0  or      [rbp+invalue], 1
0x1800064c4  lea     r8, [rbp+invalue]; invalue
0x1800064c8  mov     edx, 3Dh ; '='; option
0x1800064cd  mov     rcx, rsi; ld
0x1800064d0  call    cs:__imp_ldap_set_optionW
0x1800064d6  test    eax, eax
0x1800064d8  jz      short loc_1800064FD
0x1800064da  xor     r8d, r8d; unsigned int
0x1800064dd  mov     edx, eax; unsigned int
0x1800064df  mov     rcx, rsi; ld
0x1800064e2  call    ?myHLdapError3@@YAJPEAUldap@@KKKPEAPEAG@Z; myHLdapError3(ldap *,ulong,ulong,ulong,ushort * *)
0x1800064e7  xor     ecx, ecx; unsigned __int16 *
0x1800064e9  mov     ebx, eax
0x1800064eb  mov     r8d, eax; int
0x1800064ee  test    edi, edi
0x1800064f0  jnz     loc_18000687A
0x1800064f6  mov     edx, 158032Ch
0x1800064fb  jmp     short loc_1800064A3
0x1800064fd  mov     eax, [rbp+var_20]
0x180006500  test    eax, eax
0x180006502  jnz     short loc_18000654E
0x180006504  mov     edx, 40h ; '@'; option
0x180006509  mov     r8d, 1; invalue
0x18000650f  mov     rcx, rsi; ld
0x180006512  call    cs:__imp_ldap_set_optionW
0x180006518  test    eax, eax
0x18000651a  jz      short loc_180006545
0x18000651c  xor     r8d, r8d; unsigned int
0x18000651f  mov     edx, eax; unsigned int
0x180006521  mov     rcx, rsi; ld
0x180006524  call    ?myHLdapError3@@YAJPEAUldap@@KKKPEAPEAG@Z; myHLdapError3(ldap *,ulong,ulong,ulong,ushort * *)
0x180006529  xor     ecx, ecx; unsigned __int16 *
0x18000652b  mov     ebx, eax
0x18000652d  mov     r9d, eax; int
0x180006530  mov     r8d, eax; int
0x180006533  test    edi, edi
0x180006535  jnz     loc_18000688C
0x18000653b  mov     edx, 169032Ch
0x180006540  jmp     loc_1800064A6
0x180006545  mov     [rbp+var_20], 3
0x18000654c  jmp     short loc_180006553
0x18000654e  cmp     eax, 2
0x180006551  jz      short loc_18000658F
0x180006553  lea     r8, [rbp+var_20]; invalue
0x180006557  mov     edx, 11h; option
0x18000655c  mov     rcx, rsi; ld
0x18000655f  call    cs:__imp_ldap_set_optionW
0x180006565  test    eax, eax
0x180006567  jz      short loc_18000658F
0x180006569  xor     r8d, r8d; unsigned int
0x18000656c  mov     edx, eax; unsigned int
0x18000656e  mov     rcx, rsi; ld
0x180006571  call    ?myHLdapError3@@YAJPEAUldap@@KKKPEAPEAG@Z; myHLdapError3(ldap *,ulong,ulong,ulong,ushort * *)
0x180006576  xor     ecx, ecx; unsigned __int16 *
0x180006578  mov     ebx, eax
0x18000657a  mov     r8d, eax; int
0x18000657d  test    edi, edi
0x18000657f  jnz     loc_18000689B
0x180006585  mov     edx, 181032Ch
0x18000658a  jmp     loc_1800064A3
0x18000658f  test    r14b, r14b
0x180006592  jns     short loc_1800065D9
0x180006594  cmp     [rbp+var_38], 0
0x180006599  jz      short loc_1800065D9
0x18000659b  mov     edx, 98h; option
0x1800065a0  mov     r8d, 1; invalue
0x1800065a6  mov     rcx, rsi; ld
0x1800065a9  call    cs:__imp_ldap_set_optionW
0x1800065af  test    eax, eax
0x1800065b1  jz      short loc_1800065D9
0x1800065b3  xor     r8d, r8d; unsigned int
0x1800065b6  mov     edx, eax; unsigned int
0x1800065b8  mov     rcx, rsi; ld
0x1800065bb  call    ?myHLdapError3@@YAJPEAUldap@@KKKPEAPEAG@Z; myHLdapError3(ldap *,ulong,ulong,ulong,ushort * *)
0x1800065c0  xor     ecx, ecx; unsigned __int16 *
0x1800065c2  mov     ebx, eax
0x1800065c4  mov     r8d, eax; int
0x1800065c7  test    edi, edi
0x1800065c9  jnz     loc_1800068AD
0x1800065cf  mov     edx, 192032Ch
0x1800065d4  jmp     loc_1800064A3
0x1800065d9  test    bl, 2
0x1800065dc  jnz     loc_18000667F
0x1800065e2  call    ?_IsWinXXOrNewer@@YA_NKK@Z; _IsWinXXOrNewer(ulong,ulong)
0x1800065e7  test    al, al
0x1800065e9  jz      loc_18000667F
0x1800065ef  mov     dword ptr [rbp+var_40], 1
0x1800065f6  test    r14b, 10h
0x1800065fa  jz      short loc_18000663E
0x1800065fc  lea     rdx, [rbp+var_40]; int *
0x180006600  mov     rcx, rsi; ld
0x180006603  call    ?DCSupportsSigning@@YAJPEAUldap@@PEAH@Z; DCSupportsSigning(ldap *,int *)
0x180006608  mov     ebx, eax
0x18000660a  test    eax, eax
0x18000660c  jnz     loc_1800068BF
0x180006612  cmp     dword ptr [rbp+var_40], eax
0x180006615  jnz     short loc_18000663E
0x180006617  test    r13d, r13d
0x18000661a  jnz     short loc_18000667F
0x18000661c  test    r14b, 8
0x180006620  jz      short loc_18000667F
0x180006622  mov     ebx, 80094013h
0x180006627  xor     r9d, r9d; int
0x18000662a  mov     r8d, ebx; int
0x18000662d  mov     edx, 1B9032Ch; unsigned int
0x180006632  xor     ecx, ecx; unsigned __int16 *
0x180006634  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180006639  jmp     loc_180006950
0x18000663e  mov     edx, 95h; option
0x180006643  mov     r8d, 1; invalue
0x180006649  mov     rcx, rsi; ld
0x18000664c  call    cs:__imp_ldap_set_optionW
0x180006652  test    eax, eax
0x180006654  jz      short loc_18000667F
0x180006656  mov     r8d, 59h ; 'Y'; unsigned int
0x18000665c  mov     edx, eax; unsigned int
0x18000665e  mov     rcx, rsi; ld
0x180006661  call    ?myHLdapError3@@YAJPEAUldap@@KKKPEAPEAG@Z; myHLdapError3(ldap *,ulong,ulong,ulong,ushort * *)
0x180006666  xor     ecx, ecx; unsigned __int16 *
0x180006668  mov     ebx, eax
0x18000666a  mov     r8d, eax; int
0x18000666d  test    edi, edi
0x18000666f  jnz     loc_1800068D3
0x180006675  mov     edx, 1AD032Ch
0x18000667a  jmp     loc_1800064A3
0x18000667f  test    r15d, r15d
0x180006682  jnz     short loc_1800066C0
0x180006684  lea     r8, [rbp+hMem]; invalue
0x180006688  mov     edx, 3Bh ; ';'; option
0x18000668d  mov     rcx, rsi; ld
0x180006690  call    cs:__imp_ldap_set_optionW
0x180006696  test    eax, eax
0x180006698  jz      short loc_1800066C0
0x18000669a  xor     r8d, r8d; unsigned int
0x18000669d  mov     edx, eax; unsigned int
0x18000669f  mov     rcx, rsi; ld
0x1800066a2  call    ?myHLdapError3@@YAJPEAUldap@@KKKPEAPEAG@Z; myHLdapError3(ldap *,ulong,ulong,ulong,ushort * *)
0x1800066a7  xor     ecx, ecx; unsigned __int16 *
0x1800066a9  mov     ebx, eax
0x1800066ab  mov     r8d, eax; int
0x1800066ae  test    edi, edi
0x1800066b0  jnz     loc_1800068E2
0x1800066b6  mov     edx, 1C8032Ch
0x1800066bb  jmp     loc_1800064A3
0x1800066c0  bt      r14d, 9
0x1800066c5  jnb     short loc_180006702
0x1800066c7  xor     r8d, r8d; invalue
0x1800066ca  mov     edx, 91h; option
0x1800066cf  mov     rcx, rsi; ld
0x1800066d2  call    cs:__imp_ldap_set_optionW
0x1800066d8  test    eax, eax
0x1800066da  jz      short loc_180006702
0x1800066dc  xor     r8d, r8d; unsigned int
0x1800066df  mov     edx, eax; unsigned int
0x1800066e1  mov     rcx, rsi; ld
  ... truncated ...
```
