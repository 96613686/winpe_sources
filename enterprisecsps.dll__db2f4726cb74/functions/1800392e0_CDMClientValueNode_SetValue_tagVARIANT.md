# CDMClientValueNode::SetValue(tagVARIANT)

- ea: `0x1800392e0`
- end: `0x180039725`
- name: `?SetValue@CDMClientValueNode@@UEAAJUtagVARIANT@@@Z`
- size: `1093`
- prototype: `__int64 __fastcall(CDMClientValueNode *__hidden this, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180008de0`
- `0x180009dac`
- `0x18000d4d4`
- `0x180021944`
- `0x18002b310`
- `0x18002b508`
- `0x18002b6f4`
- `0x18002bb44`
- `0x18002bc48`
- `0x18002c064`
- `0x18002c454`
- `0x180036b00`
- `0x1800387e4`
- `0x1800392e0`
- `0x18003972c`
- `0x1800397e0`
- `0x18003a274`
- `0x1800d11a4`
- `0x1800d1778`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800393e6`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180039404`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800393e6`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180039404`
- `OLEAUT32!__imp_SysFreeString` at `0x1800396f5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800396f5`
- `RPCRT4!UuidFromStringW` at `0x1800393ad`
- `RPCRT4!UuidFromStringW` at `0x1800393c4`
- `RPCRT4!UuidFromStringW` at `0x1800394a8`
- `RPCRT4!UuidFromStringW` at `0x180039646`
- `RPCRT4!UuidFromStringW` at `0x1800396ac`
- `RPCRT4!UuidFromStringW` at `0x1800393ad`
- `RPCRT4!UuidFromStringW` at `0x1800393c4`
- `RPCRT4!UuidFromStringW` at `0x1800394a8`
- `RPCRT4!UuidFromStringW` at `0x180039646`
- `RPCRT4!UuidFromStringW` at `0x1800396ac`
- `dmEnrollEngine!SetEnrollmentForceAadToken` at `0x180039671`
- `dmEnrollEngine!SetEnrollmentForceAadToken` at `0x180039671`
- `dmEnrollEngine!__imp_SetEnrollmentAadResourceUrl` at `0x1800394cd`
- `dmEnrollEngine!__imp_SetEnrollmentAadResourceUrl` at `0x1800394cd`
- `dmEnrollEngine!__imp_SetEnrollmentUPN` at `0x18003942a`
- `dmEnrollEngine!__imp_SetEnrollmentUPN` at `0x18003942a`
- `dmEnrollEngine!__imp_SetEnrollmentAadSendDeviceToken` at `0x1800396d1`
- `dmEnrollEngine!__imp_SetEnrollmentAadSendDeviceToken` at `0x1800396d1`

## pseudocode

```c
__int64 __fastcall CDMClientValueNode::SetValue(CDMClientValueNode *this, struct tagVARIANT *a2)
{
  unsigned __int16 *EnrollmentId2; // rax
  const unsigned __int16 *v5; // r8
  const unsigned __int16 *v6; // r9
  unsigned int v7; // eax
  DMClient *v8; // rbx
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  bool v12; // zf
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned __int16 *v16; // rcx
  signed int v17; // edi
  LONGLONG llVal; // rdx
  int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned __int16 *v24; // rcx
  LONGLONG v25; // rdx
  const wchar_t *bstrVal; // rdi
  __int64 v27; // rdx
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  CEnrollmentLogger *Logger; // rax
  const unsigned __int16 *v32; // r8
  IRecordInfo *pRecInfo; // xmm1_8
  const unsigned __int16 *v34; // rdx
  IRecordInfo *v35; // xmm1_8
  unsigned __int16 *v36; // rcx
  unsigned __int16 *v37; // rcx
  __int64 iVal; // rdx
  struct tagVARIANT *v40; // [rsp+20h] [rbp-50h] BYREF
  struct tagVARIANT v41; // [rsp+30h] [rbp-40h] BYREF
  RPC_WSTR StringUuid[2]; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  StringUuid[0] = 0;
  EnrollmentId2 = GetEnrollmentId2(*((struct CConfigServiceProvider2Impl **)this + 17));
  ATL::CComBSTR::operator=(StringUuid, EnrollmentId2);
  v7 = *((_DWORD *)this + 11);
  v8 = (DMClient *)StringUuid[0];
  if ( v7 <= 0x2F )
  {
    if ( v7 == 47 )
    {
      v19 = DMClient::SetExpiryTime((DMClient *)StringUuid[0], (const unsigned __int16 *)a2->cyVal.Lo, (unsigned int)v5);
      goto LABEL_63;
    }
    if ( v7 <= 0x1A )
    {
      if ( v7 == 26 )
        goto LABEL_50;
      if ( v7 <= 7 )
      {
        if ( v7 != 7 )
        {
          v9 = v7 - 2;
          if ( v9 )
          {
            v10 = v9 - 1;
            if ( v10 )
            {
              v11 = v10 - 1;
              if ( v11 )
              {
                v13 = v11 - 1;
                v12 = v13 == 0;
LABEL_14:
                if ( !v12 && v13 != 1 )
                  goto LABEL_56;
                goto LABEL_50;
              }
              goto LABEL_49;
            }
LABEL_50:
            v32 = (const unsigned __int16 *)*((_QWORD *)this + 4);
            pRecInfo = a2->pRecInfo;
            v34 = (const unsigned __int16 *)*((_QWORD *)this + 16);
            *(_OWORD *)&v41.vt = *(_OWORD *)&a2->vt;
            v41.pRecInfo = pRecInfo;
            v19 = DMClient::SetProviderPolicyValue(v8, v34, v32, &v41.vt, v40);
            goto LABEL_63;
          }
        }
        goto LABEL_30;
      }
      v14 = v7 - 8;
      if ( !v14 )
      {
        v19 = DMClient::SetManagementServiceAddressList(
                (DMClient *)StringUuid[0],
                *((const unsigned __int16 **)this + 16),
                a2->bstrVal,
                v6);
        goto LABEL_63;
      }
      v15 = v14 - 13;
      if ( v15 )
      {
        v13 = v15 - 3;
        v12 = v13 == 0;
        goto LABEL_14;
      }
      v16 = StringUuid[0];
      *(_OWORD *)StringUuid = 0;
      if ( UuidFromStringW(v16, (UUID *)StringUuid) )
        goto LABEL_18;
      if ( wcschr(a2->bstrVal, 0x40u) && wcschr(a2->bstrVal, 0x2Eu) )
      {
        llVal = a2->llVal;
        *(_OWORD *)&v41.vt = *(_OWORD *)StringUuid;
        v19 = SetEnrollmentUPN(&v41, llVal);
LABEL_63:
        v17 = v19;
        goto LABEL_64;
      }
LABEL_42:
      v17 = -2147024809;
      goto LABEL_64;
    }
    if ( v7 > 0x25 )
    {
      v28 = v7 - 38;
      if ( !v28 )
        goto LABEL_30;
      v29 = v28 - 1;
      if ( !v29 )
      {
        v19 = DMClient::SetManagementServerAddressList((DMClient *)StringUuid[0], a2->bstrVal, v5);
        goto LABEL_63;
      }
      v30 = v29 - 1;
      if ( !v30 )
      {
        v35 = a2->pRecInfo;
        *(_OWORD *)&v41.vt = *(_OWORD *)&a2->vt;
        v41.pRecInfo = v35;
        v19 = SetCommercialID(&v41);
        goto LABEL_63;
      }
      if ( v30 == 1 )
      {
        v17 = VerifyScopeForConfigSource(*((_QWORD *)this + 17));
        if ( v17 >= 0 )
        {
LABEL_49:
          Logger = CEnrollmentLogger::GetLogger();
          CEnrollmentLogger::LogSetEntDMID(Logger, a2->bstrVal);
          goto LABEL_50;
        }
LABEL_64:
        DmClientLogging::Write(L"CDMClientValueNode::SetValue", *((_DWORD *)this + 11), v17, (int)v6);
        goto LABEL_65;
      }
      goto LABEL_56;
    }
    if ( v7 == 37 )
      goto LABEL_30;
    v20 = v7 - 29;
    if ( !v20 )
    {
      v19 = DMClient::SetSignatureRequired(
              (DMClient *)StringUuid[0],
              (const unsigned __int16 *)(unsigned int)a2->iVal,
              (unsigned int)v5);
      goto LABEL_63;
    }
    v21 = v20 - 1;
    if ( !v21 )
    {
      if ( a2->vt == 8 )
      {
        bstrVal = a2->bstrVal;
        if ( bstrVal )
        {
          if ( *bstrVal )
          {
            LOWORD(v40) = 0;
            WORD2(v40) = 0;
            if ( swscanf(bstrVal, L"%hu.%hu", &v40, (char *)&v40 + 4) == 2 )
            {
              LOBYTE(v27) = 1;
              wil::details::FeatureImpl<__WilFeatureTraits_Feature_WVD_MultiSession_User_Configuration>::ReportUsage(
                `wil::Feature<__WilFeatureTraits_Feature_WVD_MultiSession_User_Configuration>::GetImpl'::`2'::impl,
                v27);
              if ( (unsigned __int16)v40 <= 5u && ((_WORD)v40 != 5 || WORD2(v40) <= 1u) )
              {
                v19 = DMClient::SetAcctString(v8, bstrVal, 43);
                goto LABEL_63;
              }
            }
          }
        }
      }
      goto LABEL_42;
    }
    v22 = v21 - 3;
    if ( v22 )
    {
      v23 = v22 - 2;
      if ( !v23 )
      {
        v19 = DMClient::SetEnableOmaDmKeepAliveMessage(
                (DMClient *)StringUuid[0],
                (const unsigned __int16 *)(unsigned int)a2->iVal,
                (int)v5);
        goto LABEL_63;
      }
      if ( v23 == 1 )
      {
LABEL_30:
        v17 = -2046820335;
        goto LABEL_64;
      }
LABEL_56:
      v17 = -2147418113;
      goto LABEL_64;
    }
    v24 = StringUuid[0];
    *(_OWORD *)StringUuid = 0;
    if ( !UuidFromStringW(v24, (UUID *)StringUuid) )
    {
      v25 = a2->llVal;
      *(_OWORD *)&v41.vt = *(_OWORD *)StringUuid;
      v19 = SetEnrollmentAadResourceUrl(&v41, v25);
      goto LABEL_63;
    }
    goto LABEL_18;
  }
  if ( v7 == 69 )
  {
    v37 = StringUuid[0];
    *(_OWORD *)StringUuid = 0;
    if ( !UuidFromStringW(v37, (UUID *)StringUuid) )
    {
      iVal = (unsigned int)a2->iVal;
      *(_OWORD *)&v41.vt = *(_OWORD *)StringUuid;
      v19 = SetEnrollmentAadSendDeviceToken(&v41, iVal);
      goto LABEL_63;
    }
    goto LABEL_18;
  }
  if ( v7 != 85 )
    goto LABEL_56;
  v36 = StringUuid[0];
  *(_OWORD *)StringUuid = 0;
  if ( UuidFromStringW(v36, (UUID *)StringUuid) )
  {
LABEL_18:
    v17 = UuidFromStringW((RPC_WSTR)v8, (UUID *)StringUuid) | 0x80010000;
    goto LABEL_64;
  }
  if ( a2->lVal <= 8u )
  {
    *(_OWORD *)&v41.vt = *(_OWORD *)StringUuid;
    v19 = SetEnrollmentForceAadToken(&v41);
    goto LABEL_63;
  }
  v17 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x937,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmclient\\dmclientnode.cpp",
    (const char *)0x80070057LL,
    (int)v40);
LABEL_65:
  SysFreeString((BSTR)v8);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1800392e0  mov     [rsp-18h+arg_10], rbx
0x1800392e5  mov     [rsp-18h+arg_18], rsi
0x1800392ea  push    rbp
0x1800392eb  push    rdi
0x1800392ec  push    r14
0x1800392ee  mov     rbp, rsp
0x1800392f1  sub     rsp, 70h
0x1800392f5  mov     rax, cs:__security_cookie
0x1800392fc  xor     rax, rsp
0x1800392ff  mov     [rbp+var_10], rax
0x180039303  mov     r14, rcx
0x180039306  mov     [rbp+StringUuid], 0
0x18003930e  mov     rcx, [rcx+88h]; struct CConfigServiceProvider2Impl *
0x180039315  mov     rsi, rdx
0x180039318  call    ?GetEnrollmentId2@@YAPEAGPEAVCConfigServiceProvider2Impl@@@Z; GetEnrollmentId2(CConfigServiceProvider2Impl *)
0x18003931d  mov     rdx, rax
0x180039320  lea     rcx, [rbp+StringUuid]
0x180039324  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180039329  mov     eax, [r14+2Ch]
0x18003932d  mov     rbx, [rbp+StringUuid]
0x180039331  cmp     eax, 2Fh ; '/'
0x180039334  ja      loc_180039624
0x18003933a  jz      loc_180039614
0x180039340  cmp     eax, 1Ah
0x180039343  ja      loc_180039453
0x180039349  jz      loc_1800395B7
0x18003934f  cmp     eax, 7
0x180039352  ja      short loc_18003937A
0x180039354  jz      loc_18003947F
0x18003935a  sub     eax, 2
0x18003935d  jz      loc_18003947F
0x180039363  sub     eax, 1
0x180039366  jz      loc_1800395B7
0x18003936c  sub     eax, 1
0x18003936f  jz      loc_1800395A6
0x180039375  sub     eax, 1
0x180039378  jmp     short loc_18003938B
0x18003937a  sub     eax, 8
0x18003937d  jz      loc_18003943B
0x180039383  sub     eax, 0Dh
0x180039386  jz      short loc_18003939F
0x180039388  sub     eax, 3
0x18003938b  jz      loc_1800395B7
0x180039391  cmp     eax, 1
0x180039394  jz      loc_1800395B7
0x18003939a  jmp     loc_18003962E
0x18003939f  xorps   xmm0, xmm0
0x1800393a2  lea     rdx, [rbp+StringUuid]; Uuid
0x1800393a6  mov     rcx, rbx; StringUuid
0x1800393a9  movups  xmmword ptr [rbp+StringUuid], xmm0
0x1800393ad  call    cs:__imp_UuidFromStringW
0x1800393b4  nop     dword ptr [rax+rax+00h]
0x1800393b9  test    eax, eax
0x1800393bb  jz      short loc_1800393DD
0x1800393bd  lea     rdx, [rbp+StringUuid]; Uuid
0x1800393c1  mov     rcx, rbx; StringUuid
0x1800393c4  call    cs:__imp_UuidFromStringW
0x1800393cb  nop     dword ptr [rax+rax+00h]
0x1800393d0  mov     edi, eax
0x1800393d2  or      edi, 80010000h
0x1800393d8  jmp     loc_1800396DF
0x1800393dd  mov     rcx, [rsi+8]; Str
0x1800393e1  mov     edx, 40h ; '@'; Ch
0x1800393e6  call    cs:__imp_wcschr
0x1800393ed  nop     dword ptr [rax+rax+00h]
0x1800393f2  test    rax, rax
0x1800393f5  jz      loc_180039555
0x1800393fb  mov     rcx, [rsi+8]; Str
0x1800393ff  mov     edx, 2Eh ; '.'; Ch
0x180039404  call    cs:__imp_wcschr
0x18003940b  nop     dword ptr [rax+rax+00h]
0x180039410  test    rax, rax
0x180039413  jz      loc_180039555
0x180039419  movaps  xmm0, xmmword ptr [rbp+StringUuid]
0x18003941d  lea     rcx, [rbp+var_40]
0x180039421  mov     rdx, [rsi+8]
0x180039425  movdqa  xmmword ptr [rbp+var_40], xmm0
0x18003942a  call    cs:__imp_SetEnrollmentUPN
0x180039431  nop     dword ptr [rax+rax+00h]
0x180039436  jmp     loc_1800396DD
0x18003943b  mov     r8, [rsi+8]; unsigned __int16 *
0x18003943f  mov     rcx, rbx; this
0x180039442  mov     rdx, [r14+80h]; unsigned __int16 *
0x180039449  call    ?SetManagementServiceAddressList@DMClient@@YAJPEBG00@Z; DMClient::SetManagementServiceAddressList(ushort const *,ushort const *,ushort const *)
0x18003944e  jmp     loc_1800396DD
0x180039453  cmp     eax, 25h ; '%'
0x180039456  ja      loc_180039570
0x18003945c  jz      short loc_18003947F
0x18003945e  sub     eax, 1Dh
0x180039461  jz      loc_18003955F
0x180039467  sub     eax, 1
0x18003946a  jz      short loc_1800394DE
0x18003946c  sub     eax, 3
0x18003946f  jz      short loc_18003949A
0x180039471  sub     eax, 2
0x180039474  jz      short loc_180039489
0x180039476  cmp     eax, 1
0x180039479  jnz     loc_18003962E
0x18003947f  mov     edi, 86000011h
0x180039484  jmp     loc_1800396DF
0x180039489  movsx   edx, word ptr [rsi+8]; unsigned __int16 *
0x18003948d  mov     rcx, rbx; this
0x180039490  call    ?SetEnableOmaDmKeepAliveMessage@DMClient@@YAJPEBGH@Z; DMClient::SetEnableOmaDmKeepAliveMessage(ushort const *,int)
0x180039495  jmp     loc_1800396DD
0x18003949a  xorps   xmm0, xmm0
0x18003949d  lea     rdx, [rbp+StringUuid]; Uuid
0x1800394a1  mov     rcx, rbx; StringUuid
0x1800394a4  movups  xmmword ptr [rbp+StringUuid], xmm0
0x1800394a8  call    cs:__imp_UuidFromStringW
0x1800394af  nop     dword ptr [rax+rax+00h]
0x1800394b4  test    eax, eax
0x1800394b6  jnz     loc_1800393BD
0x1800394bc  movaps  xmm0, xmmword ptr [rbp+StringUuid]
0x1800394c0  lea     rcx, [rbp+var_40]
0x1800394c4  mov     rdx, [rsi+8]
0x1800394c8  movdqa  xmmword ptr [rbp+var_40], xmm0
0x1800394cd  call    cs:__imp_SetEnrollmentAadResourceUrl
0x1800394d4  nop     dword ptr [rax+rax+00h]
0x1800394d9  jmp     loc_1800396DD
0x1800394de  mov     ecx, 8
0x1800394e3  cmp     cx, [rsi]
0x1800394e6  jnz     short loc_180039555
0x1800394e8  mov     rdi, [rsi+8]
0x1800394ec  test    rdi, rdi
0x1800394ef  jz      short loc_180039555
0x1800394f1  xor     eax, eax
0x1800394f3  cmp     ax, [rdi]
0x1800394f6  jz      short loc_180039555
0x1800394f8  lea     r9, [rbp+var_4C]
0x1800394fc  mov     [rbp+var_50], ax
0x180039500  lea     r8, [rbp+var_50]
0x180039504  mov     [rbp+var_4C], ax
0x180039508  lea     rdx, aHuHu; "%hu.%hu"
0x18003950f  mov     rcx, rdi; Buffer
0x180039512  call    swscanf
0x180039517  cmp     eax, 2
0x18003951a  jnz     short loc_180039555
0x18003951c  lea     esi, [rax-1]
0x18003951f  mov     dl, sil
0x180039522  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WVD_MultiSession_User_Configuration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WVD_MultiSession_User_Configuration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WVD_MultiSession_User_Configuration> `wil::Feature<__WilFeatureTraits_Feature_WVD_MultiSession_User_Configuration>::GetImpl(void)'::`2'::impl
0x180039529  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_WVD_MultiSession_User_Configuration@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WVD_MultiSession_User_Configuration>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18003952e  lea     eax, [rsi+4]
0x180039531  cmp     ax, [rbp+var_50]
0x180039535  jb      short loc_180039555
0x180039537  jnz     short loc_18003953F
0x180039539  cmp     si, [rbp+var_4C]
0x18003953d  jb      short loc_180039555
0x18003953f  mov     r8d, 2Bh ; '+'
0x180039545  mov     rdx, rdi
0x180039548  mov     rcx, rbx
0x18003954b  call    ?SetAcctString@DMClient@@YAJPEBG0W4tagOMADM_ACCT_MEMBER_TYPE@@@Z; DMClient::SetAcctString(ushort const *,ushort const *,tagOMADM_ACCT_MEMBER_TYPE)
0x180039550  jmp     loc_1800396DD
0x180039555  mov     edi, 80070057h
0x18003955a  jmp     loc_1800396DF
0x18003955f  movsx   edx, word ptr [rsi+8]; unsigned __int16 *
0x180039563  mov     rcx, rbx; this
0x180039566  call    ?SetSignatureRequired@DMClient@@YAJPEBGK@Z; DMClient::SetSignatureRequired(ushort const *,ulong)
0x18003956b  jmp     loc_1800396DD
0x180039570  sub     eax, 26h ; '&'
0x180039573  jz      loc_18003947F
0x180039579  sub     eax, 1
0x18003957c  jz      loc_180039603
0x180039582  sub     eax, 1
0x180039585  jz      short loc_1800395E4
0x180039587  cmp     eax, 1
0x18003958a  jnz     loc_18003962E
0x180039590  mov     rcx, [r14+88h]
0x180039597  call    ?VerifyScopeForConfigSource@@YAJPEAVCConfigServiceProvider2Impl@@W4EnrollmentEnrollType@@@Z; VerifyScopeForConfigSource(CConfigServiceProvider2Impl *,EnrollmentEnrollType)
0x18003959c  mov     edi, eax
0x18003959e  test    eax, eax
0x1800395a0  js      loc_1800396DF
0x1800395a6  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1800395ab  mov     rdx, [rsi+8]; unsigned __int16 *
0x1800395af  mov     rcx, rax; this
0x1800395b2  call    ?LogSetEntDMID@CEnrollmentLogger@@QEAAXPEBG@Z; CEnrollmentLogger::LogSetEntDMID(ushort const *)
0x1800395b7  movups  xmm0, xmmword ptr [rsi]
0x1800395ba  lea     r9, [rbp+var_40]; unsigned __int16 *
0x1800395be  mov     r8, [r14+20h]; unsigned __int16 *
0x1800395c2  movsd   xmm1, qword ptr [rsi+10h]
0x1800395c7  mov     rcx, rbx; this
0x1800395ca  mov     rdx, [r14+80h]; unsigned __int16 *
0x1800395d1  movaps  xmmword ptr [rbp+var_40], xmm0
0x1800395d5  movsd   qword ptr [rbp+var_40+10h], xmm1
0x1800395da  call    ?SetProviderPolicyValue@DMClient@@YAJPEBG00UtagVARIANT@@@Z; DMClient::SetProviderPolicyValue(ushort const *,ushort const *,ushort const *,tagVARIANT)
0x1800395df  jmp     loc_1800396DD
0x1800395e4  movups  xmm0, xmmword ptr [rsi]
0x1800395e7  lea     rcx, [rbp+var_40]; struct tagVARIANT
0x1800395eb  movsd   xmm1, qword ptr [rsi+10h]
0x1800395f0  movaps  xmmword ptr [rbp+var_40], xmm0
0x1800395f4  movsd   qword ptr [rbp+var_40+10h], xmm1
0x1800395f9  call    ?SetCommercialID@@YAJUtagVARIANT@@@Z; SetCommercialID(tagVARIANT)
0x1800395fe  jmp     loc_1800396DD
0x180039603  mov     rdx, [rsi+8]; unsigned __int16 *
0x180039607  mov     rcx, rbx; this
0x18003960a  call    ?SetManagementServerAddressList@DMClient@@YAJPEBG0@Z; DMClient::SetManagementServerAddressList(ushort const *,ushort const *)
0x18003960f  jmp     loc_1800396DD
0x180039614  mov     edx, [rsi+8]; unsigned __int16 *
0x180039617  mov     rcx, rbx; this
0x18003961a  call    ?SetExpiryTime@DMClient@@YAJPEBGK@Z; DMClient::SetExpiryTime(ushort const *,ulong)
0x18003961f  jmp     loc_1800396DD
0x180039624  cmp     eax, 45h ; 'E'
0x180039627  jz      short loc_18003969E
0x180039629  cmp     eax, 55h ; 'U'
0x18003962c  jz      short loc_180039638
0x18003962e  mov     edi, 8000FFFFh
0x180039633  jmp     loc_1800396DF
0x180039638  xorps   xmm0, xmm0
0x18003963b  lea     rdx, [rbp+StringUuid]; Uuid
0x18003963f  mov     rcx, rbx; StringUuid
0x180039642  movups  xmmword ptr [rbp+StringUuid], xmm0
0x180039646  call    cs:__imp_UuidFromStringW
0x18003964d  nop     dword ptr [rax+rax+00h]
0x180039652  test    eax, eax
0x180039654  jnz     loc_1800393BD
0x18003965a  mov     edx, [rsi+8]
0x18003965d  lea     ecx, [rax+8]
0x180039660  cmp     edx, ecx
0x180039662  ja      short loc_18003967F
0x180039664  movaps  xmm0, xmmword ptr [rbp+StringUuid]
0x180039668  lea     rcx, [rbp+var_40]
0x18003966c  movdqa  xmmword ptr [rbp+var_40], xmm0
0x180039671  call    cs:__imp_SetEnrollmentForceAadToken
0x180039678  nop     dword ptr [rax+rax+00h]
0x18003967d  jmp     short loc_1800396DD
0x18003967f  mov     rcx, [rbp+18h]; this
0x180039683  lea     r8, aOnecoreuapAdmi_63; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18003968a  mov     edi, 80070057h
0x18003968f  mov     edx, 937h; void *
0x180039694  mov     r9d, edi; char *
0x180039697  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003969c  jmp     short loc_1800396F2
0x18003969e  xorps   xmm0, xmm0
0x1800396a1  lea     rdx, [rbp+StringUuid]; Uuid
0x1800396a5  mov     rcx, rbx; StringUuid
0x1800396a8  movups  xmmword ptr [rbp+StringUuid], xmm0
0x1800396ac  call    cs:__imp_UuidFromStringW
0x1800396b3  nop     dword ptr [rax+rax+00h]
0x1800396b8  test    eax, eax
0x1800396ba  jnz     loc_1800393BD
0x1800396c0  movaps  xmm0, xmmword ptr [rbp+StringUuid]
0x1800396c4  lea     rcx, [rbp+var_40]
0x1800396c8  movsx   edx, word ptr [rsi+8]
0x1800396cc  movdqa  xmmword ptr [rbp+var_40], xmm0
0x1800396d1  call    cs:__imp_SetEnrollmentAadSendDeviceToken
0x1800396d8  nop     dword ptr [rax+rax+00h]
0x1800396dd  mov     edi, eax
0x1800396df  mov     edx, [r14+2Ch]; unsigned int
0x1800396e3  lea     rcx, aCdmclientvalue_1; "CDMClientValueNode::SetValue"
0x1800396ea  mov     r8d, edi; int
0x1800396ed  call    ?Write@DmClientLogging@@SAXPEBGKJH@Z; DmClientLogging::Write(ushort const *,ulong,long,int)
0x1800396f2  mov     rcx, rbx; bstrString
0x1800396f5  call    cs:__imp_SysFreeString
0x1800396fc  nop     dword ptr [rax+rax+00h]
0x180039701  mov     eax, edi
0x180039703  mov     rcx, [rbp+var_10]
0x180039707  xor     rcx, rsp; StackCookie
0x18003970a  call    __security_check_cookie
0x18003970f  lea     r11, [rsp+70h+var_s0]
0x180039714  mov     rbx, [r11+30h]
0x180039718  mov     rsi, [r11+38h]
0x18003971c  mov     rsp, r11
0x18003971f  pop     r14
0x180039721  pop     rdi
0x180039722  pop     rbp
0x180039723  retn
```
