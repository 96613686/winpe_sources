# CDMClientValueNode::GetValue(tagVARIANT *)

- ea: `0x180037b70`
- end: `0x180038252`
- name: `?GetValue@CDMClientValueNode@@UEAAJPEAUtagVARIANT@@@Z`
- size: `1762`
- prototype: `int(CDMClientValueNode *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180008de0`
- `0x180009cc4`
- `0x180021944`
- `0x180025a78`
- `0x18002796c`
- `0x180028994`
- `0x180028b60`
- `0x180028f98`
- `0x1800293f0`
- `0x18002955c`
- `0x180029ab0`
- `0x180029ec8`
- `0x18002dc38`
- `0x180036b00`
- `0x180037b70`
- `0x1800384d0`
- `0x1800387e4`
- `0x18003972c`
- `0x1800397e0`
- `0x18003a120`
- `0x18003f3d4`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180037ce8`
- `OLEAUT32!__imp_SysAllocString` at `0x180037f09`
- `OLEAUT32!__imp_SysAllocString` at `0x180037f54`
- `OLEAUT32!__imp_SysAllocString` at `0x180038125`
- `OLEAUT32!__imp_SysAllocString` at `0x180037ce8`
- `OLEAUT32!__imp_SysAllocString` at `0x180037f09`
- `OLEAUT32!__imp_SysAllocString` at `0x180037f54`
- `OLEAUT32!__imp_SysAllocString` at `0x180038125`
- `OLEAUT32!__imp_SysFreeString` at `0x180037d83`
- `OLEAUT32!__imp_SysFreeString` at `0x180037d83`
- `RPCRT4!UuidFromStringW` at `0x180037c81`
- `RPCRT4!UuidFromStringW` at `0x180037c99`
- `RPCRT4!UuidFromStringW` at `0x180037ec5`
- `RPCRT4!UuidFromStringW` at `0x180038050`
- `RPCRT4!UuidFromStringW` at `0x180038068`
- `RPCRT4!UuidFromStringW` at `0x180038193`
- `RPCRT4!UuidFromStringW` at `0x1800381fc`
- `RPCRT4!UuidFromStringW` at `0x180037c81`
- `RPCRT4!UuidFromStringW` at `0x180037c99`
- `RPCRT4!UuidFromStringW` at `0x180037ec5`
- `RPCRT4!UuidFromStringW` at `0x180038050`
- `RPCRT4!UuidFromStringW` at `0x180038068`
- `RPCRT4!UuidFromStringW` at `0x180038193`
- `RPCRT4!UuidFromStringW` at `0x1800381fc`
- `omadmapi!__imp_OmaDmGetAcctInfo` at `0x180037e3e`
- `omadmapi!__imp_OmaDmGetAcctInfo` at `0x180037e3e`
- `omadmapi!__imp_OmaDmFreeAcctInfo` at `0x180037e84`
- `omadmapi!__imp_OmaDmFreeAcctInfo` at `0x180037e84`
- `omadmapi!__imp_OmaDmIsNodeValuePresent` at `0x180037e5b`
- `omadmapi!__imp_OmaDmIsNodeValuePresent` at `0x180037e5b`
- `omadmapi!__imp_OmaDmSetNodeValuePresence` at `0x180037e1f`
- `omadmapi!__imp_OmaDmSetNodeValuePresence` at `0x180037e1f`
- `dmEnrollEngine!GetEnrollmentUPN` at `0x180037cd1`
- `dmEnrollEngine!GetEnrollmentUPN` at `0x180037cd1`
- `dmEnrollEngine!GetEnrollmentAadSendDeviceToken` at `0x180038229`
- `dmEnrollEngine!GetEnrollmentAadSendDeviceToken` at `0x180038229`
- `dmEnrollEngine!GetEnrollmentType` at `0x18003809e`
- `dmEnrollEngine!GetEnrollmentType` at `0x18003809e`
- `dmEnrollEngine!GetEnrollmentForceAadToken` at `0x1800381c0`
- `dmEnrollEngine!GetEnrollmentForceAadToken` at `0x1800381c0`
- `dmEnrollEngine!GetEnrollmentAadResourceUrl` at `0x180037eee`
- `dmEnrollEngine!GetEnrollmentAadResourceUrl` at `0x180037eee`

## string_xrefs

- `0x180038103`: `Compliance`
- `0x1800380f1`: `MMPCComplete`

## pseudocode

```c
__int64 __fastcall CDMClientValueNode::GetValue(
        CDMClientValueNode *this,
        struct tagVARIANT *a2,
        __int64 a3,
        unsigned __int16 **a4)
{
  signed int EnrollmentAadSendDeviceToken; // ebx
  unsigned __int16 *EnrollmentId2; // rax
  unsigned __int16 **v8; // rdx
  unsigned int *v9; // r8
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  bool v13; // zf
  unsigned int v14; // eax
  int DeviceIDString; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned __int16 *v18; // rbx
  BSTR v19; // rax
  SHORT v20; // si
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  int v26; // r14d
  BSTR v27; // rax
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // eax
  unsigned __int16 **v32; // r8
  const OLECHAR *v33; // rcx
  unsigned __int16 *v34; // rbx
  BSTR v35; // rax
  OLECHAR *psz; // [rsp+20h] [rbp-E0h] BYREF
  RPC_WSTR StringUuid; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int16 v38[8]; // [rsp+30h] [rbp-D0h] BYREF
  UUID v39; // [rsp+40h] [rbp-C0h] BYREF
  UUID Uuid; // [rsp+50h] [rbp-B0h] BYREF
  int v41; // [rsp+60h] [rbp-A0h] BYREF
  char v42[480]; // [rsp+64h] [rbp-9Ch] BYREF
  int v43; // [rsp+244h] [rbp+144h]

  StringUuid = 0;
  *(_QWORD *)v38 = 0;
  if ( !a2 )
  {
    EnrollmentAadSendDeviceToken = -2147024809;
    goto LABEL_33;
  }
  EnrollmentId2 = GetEnrollmentId2(*((struct CConfigServiceProvider2Impl **)this + 17));
  ATL::CComBSTR::operator=(&StringUuid, EnrollmentId2);
  v10 = *((_DWORD *)this + 11);
  if ( v10 > 0x2F )
  {
    if ( v10 == 69 )
    {
      v34 = StringUuid;
      Uuid = 0;
      if ( !UuidFromStringW(StringUuid, &Uuid) )
      {
        v39 = Uuid;
        LODWORD(psz) = 0;
        EnrollmentAadSendDeviceToken = GetEnrollmentAadSendDeviceToken(&v39, &psz);
        if ( EnrollmentAadSendDeviceToken < 0 )
          goto LABEL_33;
        if ( !(_DWORD)psz )
        {
LABEL_30:
          v20 = 0;
LABEL_31:
          a2->iVal = v20;
          goto LABEL_32;
        }
LABEL_102:
        v20 = -1;
        goto LABEL_31;
      }
    }
    else
    {
      if ( v10 != 85 )
        goto LABEL_95;
      v34 = StringUuid;
      Uuid = 0;
      if ( !UuidFromStringW(StringUuid, &Uuid) )
      {
        v39 = Uuid;
        LODWORD(psz) = 0;
        EnrollmentAadSendDeviceToken = GetEnrollmentForceAadToken(&v39, &psz);
        if ( EnrollmentAadSendDeviceToken >= 0 )
        {
          a2->lVal = (int)psz;
          a2->vt = 3;
        }
        goto LABEL_33;
      }
    }
    goto LABEL_71;
  }
  if ( v10 == 47 )
  {
    EnrollmentAadSendDeviceToken = DMClient::GetExpiryTime((DMClient *)StringUuid, &a2->uiVal, v9);
    if ( EnrollmentAadSendDeviceToken >= 0 )
      a2->vt = 19;
    goto LABEL_33;
  }
  if ( v10 <= 0x1D )
  {
    if ( v10 != 29 )
    {
      if ( v10 <= 7 )
      {
        if ( v10 != 7 )
        {
          v11 = v10 - 2;
          if ( v11 )
          {
            v12 = v11 - 1;
            if ( !v12 )
              goto LABEL_65;
            v14 = v12 - 1;
            v13 = v14 == 0;
            goto LABEL_16;
          }
          DeviceIDString = GetDeviceIDString(*((struct CConfigServiceProvider2Impl **)this + 17), &a2->bstrVal);
          goto LABEL_56;
        }
LABEL_95:
        EnrollmentAadSendDeviceToken = -2147418113;
        goto LABEL_33;
      }
      v16 = v10 - 8;
      if ( v16 )
      {
        v17 = v16 - 13;
        if ( v17 )
        {
          v14 = v17 - 3;
          v13 = v14 == 0;
LABEL_16:
          if ( !v13 && v14 - 1 >= 2 )
            goto LABEL_95;
LABEL_65:
          EnrollmentAadSendDeviceToken = DMClient::GetProviderPolicyValue(
                                           (DMClient *)StringUuid,
                                           *((const unsigned __int16 **)this + 16),
                                           *((const unsigned __int16 **)this + 4),
                                           &a2->vt,
                                           (struct tagVARIANT *)psz);
          goto LABEL_33;
        }
        v18 = StringUuid;
        psz = 0;
        Uuid = 0;
        if ( UuidFromStringW(StringUuid, &Uuid) )
          goto LABEL_20;
        v39 = Uuid;
        EnrollmentAadSendDeviceToken = GetEnrollmentUPN(&v39, &psz);
        if ( EnrollmentAadSendDeviceToken < 0 )
          goto LABEL_21;
        v19 = SysAllocString(psz);
        a2->llVal = (LONGLONG)v19;
        if ( v19 )
        {
          a2->vt = 8;
          goto LABEL_21;
        }
        goto LABEL_24;
      }
      EnrollmentAadSendDeviceToken = DMClient::GetManagementServiceAddressesList(
                                       (DMClient *)StringUuid,
                                       *((const unsigned __int16 **)this + 16),
                                       &a2->uiVal,
                                       a4);
      if ( EnrollmentAadSendDeviceToken >= 0 )
        a2->vt = 8;
      goto LABEL_33;
    }
    LODWORD(psz) = 0;
    EnrollmentAadSendDeviceToken = DMClient::GetSignatureRequired(
                                     (DMClient *)StringUuid,
                                     (const unsigned __int16 *)&psz,
                                     v9);
    if ( EnrollmentAadSendDeviceToken < 0 )
      goto LABEL_33;
    if ( !(_DWORD)psz )
      goto LABEL_30;
    goto LABEL_102;
  }
  if ( v10 > 0x24 )
  {
    v28 = v10 - 37;
    if ( v28 )
    {
      v29 = v28 - 1;
      if ( !v29 )
      {
        DeviceIDString = DMClient::GetHardwareDevID((DMClient *)&a2->decVal.8, v8);
        goto LABEL_56;
      }
      v30 = v29 - 1;
      if ( v30 )
      {
        v31 = v30 - 1;
        if ( v31 )
        {
          if ( v31 == 1 )
          {
            EnrollmentAadSendDeviceToken = VerifyScopeForConfigSource(*((_QWORD *)this + 17));
            if ( EnrollmentAadSendDeviceToken < 0 )
              goto LABEL_33;
            goto LABEL_65;
          }
          goto LABEL_95;
        }
        DeviceIDString = GetCommercialID(&a2->bstrVal);
LABEL_56:
        EnrollmentAadSendDeviceToken = DeviceIDString;
        if ( DeviceIDString < 0 )
          goto LABEL_33;
LABEL_57:
        a2->vt = 8;
        goto LABEL_33;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        v38,
        0);
      EnrollmentAadSendDeviceToken = DMClient::GetManagementServerAddressList((DMClient *)StringUuid, v38, v32);
      if ( EnrollmentAadSendDeviceToken < 0 )
        goto LABEL_33;
      v33 = *(const OLECHAR **)v38;
      goto LABEL_89;
    }
    v34 = StringUuid;
    Uuid = 0;
    if ( !UuidFromStringW(StringUuid, &Uuid) )
    {
      v39 = Uuid;
      LODWORD(psz) = 63;
      EnrollmentAadSendDeviceToken = GetEnrollmentType(&v39, &psz);
      if ( EnrollmentAadSendDeviceToken < 0 )
        goto LABEL_33;
      switch ( (_DWORD)psz )
      {
        case 0:
          goto LABEL_88;
        case 5:
          v33 = L"AppManagement";
          break;
        case 6:
          v33 = L"Device";
          break;
        case 0xD:
LABEL_88:
          v33 = L"Full";
          break;
        case 0x16:
          v33 = L"Compliance";
          break;
        case 0x18:
          v33 = L"MMPC";
          break;
        case 0x1A:
          v33 = L"MMPCComplete";
          break;
        case 0x1B:
          v33 = L"MMPCOnPremise";
          break;
        default:
          v33 = L"Local";
          break;
      }
LABEL_89:
      v35 = SysAllocString(v33);
      a2->llVal = (LONGLONG)v35;
      if ( !v35 )
      {
        EnrollmentAadSendDeviceToken = -2147024882;
        goto LABEL_33;
      }
      goto LABEL_57;
    }
LABEL_71:
    EnrollmentAadSendDeviceToken = UuidFromStringW(v34, &Uuid) | 0x80010000;
    goto LABEL_33;
  }
  if ( v10 == 36 )
  {
    DeviceIDString = DMClient::GetAADDeviceID((DMClient *)&a2->decVal.8, v8);
    goto LABEL_56;
  }
  v22 = v10 - 30;
  if ( !v22 )
  {
    DeviceIDString = DMClient::GetManagementServiceVersion((DMClient *)StringUuid, &a2->uiVal, (unsigned __int16 **)v9);
    goto LABEL_56;
  }
  v23 = v22 - 1;
  if ( !v23 )
  {
    EnrollmentAadSendDeviceToken = 0;
    a2->vt = 8;
    LOBYTE(v8) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_WVD_MultiSession_User_Configuration>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_WVD_MultiSession_User_Configuration>::GetImpl'::`2'::impl,
      v8);
    a2->llVal = (LONGLONG)SysAllocString(L"5.1");
    goto LABEL_33;
  }
  v24 = v23 - 1;
  if ( !v24 )
  {
    EnrollmentAadSendDeviceToken = 0;
    goto LABEL_33;
  }
  v25 = v24 - 1;
  if ( !v25 )
  {
    v18 = StringUuid;
    psz = 0;
    Uuid = 0;
    if ( UuidFromStringW(StringUuid, &Uuid) )
    {
LABEL_20:
      EnrollmentAadSendDeviceToken = UuidFromStringW(v18, &Uuid) | 0x80010000;
LABEL_21:
      CTSmartObj<unsigned short *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(&psz);
      goto LABEL_33;
    }
    v39 = Uuid;
    EnrollmentAadSendDeviceToken = GetEnrollmentAadResourceUrl(&v39, &psz);
    if ( EnrollmentAadSendDeviceToken < 0 )
      goto LABEL_21;
    v27 = SysAllocString(psz);
    a2->llVal = (LONGLONG)v27;
    if ( v27 )
    {
      a2->vt = 8;
      goto LABEL_21;
    }
LABEL_24:
    EnrollmentAadSendDeviceToken = -2147024882;
    goto LABEL_21;
  }
  if ( v25 != 2 )
    goto LABEL_95;
  memset_0(v42, 0, 0x1FCu);
  v41 = 512;
  v26 = 0;
  EnrollmentAadSendDeviceToken = OmaDmSetNodeValuePresence(55, &v41, 0xFFFFFFFFLL);
  if ( EnrollmentAadSendDeviceToken >= 0 )
  {
    EnrollmentAadSendDeviceToken = OmaDmGetAcctInfo(StringUuid, 1, &v41);
    if ( EnrollmentAadSendDeviceToken < 0 )
    {
      if ( EnrollmentAadSendDeviceToken == -2147024894 )
        EnrollmentAadSendDeviceToken = 0;
    }
    else if ( (unsigned int)OmaDmIsNodeValuePresent(55, &v41, 0xFFFFFFFFLL) )
    {
      v26 = v43;
    }
  }
  OmaDmFreeAcctInfo(&v41);
  a2->iVal = -(v26 != 0);
  if ( EnrollmentAadSendDeviceToken >= 0 )
LABEL_32:
    a2->vt = 11;
LABEL_33:
  DmClientLogging::Write(L"CDMClientValueNode::GetValue", *((_DWORD *)this + 11), EnrollmentAadSendDeviceToken, (int)a4);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v38);
  SysFreeString(StringUuid);
  return (unsigned int)EnrollmentAadSendDeviceToken;
}

```

## disassembly

```asm
0x180037b70  mov     [rsp-8+arg_10], rbx
0x180037b75  push    rbp
0x180037b76  push    rsi
0x180037b77  push    rdi
0x180037b78  push    r14
0x180037b7a  push    r15
0x180037b7c  lea     rbp, [rsp-170h]
0x180037b84  sub     rsp, 270h
0x180037b8b  mov     rax, cs:__security_cookie
0x180037b92  xor     rax, rsp
0x180037b95  mov     [rbp+190h+var_30], rax
0x180037b9c  mov     [rsp+290h+StringUuid], 0
0x180037ba5  mov     rdi, rdx
0x180037ba8  mov     qword ptr [rsp+290h+var_260], 0
0x180037bb1  mov     r15, rcx
0x180037bb4  test    rdx, rdx
0x180037bb7  jnz     short loc_180037BC3
0x180037bb9  mov     ebx, 80070057h
0x180037bbe  jmp     loc_180037D61
0x180037bc3  mov     rcx, [rcx+88h]; struct CConfigServiceProvider2Impl *
0x180037bca  call    ?GetEnrollmentId2@@YAPEAGPEAVCConfigServiceProvider2Impl@@@Z; GetEnrollmentId2(CConfigServiceProvider2Impl *)
0x180037bcf  mov     rdx, rax
0x180037bd2  lea     rcx, [rsp+290h+StringUuid]
0x180037bd7  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180037bdc  mov     eax, [r15+2Ch]
0x180037be0  cmp     eax, 2Fh ; '/'
0x180037be3  ja      loc_18003816A
0x180037be9  jz      loc_180038148
0x180037bef  cmp     eax, 1Dh
0x180037bf2  ja      loc_180037DB8
0x180037bf8  jz      loc_180037D2E
0x180037bfe  cmp     eax, 7
0x180037c01  ja      short loc_180037C31
0x180037c03  jz      loc_180038174
0x180037c09  sub     eax, 2
0x180037c0c  jz      short loc_180037C1C
0x180037c0e  sub     eax, 1
0x180037c11  jz      loc_180037FD1
0x180037c17  sub     eax, 1
0x180037c1a  jmp     short loc_180037C46
0x180037c1c  mov     rcx, [r15+88h]; struct CConfigServiceProvider2Impl *
0x180037c23  lea     rdx, [rdi+8]; unsigned __int16 **
0x180037c27  call    ?GetDeviceIDString@@YAJPEAVCConfigServiceProvider2Impl@@PEAPEAG@Z; GetDeviceIDString(CConfigServiceProvider2Impl *,ushort * *)
0x180037c2c  jmp     loc_180037F77
0x180037c31  mov     esi, 8
0x180037c36  sub     eax, esi
0x180037c38  jz      loc_180037D0E
0x180037c3e  sub     eax, 0Dh
0x180037c41  jz      short loc_180037C63
0x180037c43  sub     eax, 3
0x180037c46  jz      loc_180037FD1
0x180037c4c  sub     eax, 1
0x180037c4f  jz      loc_180037FD1
0x180037c55  cmp     eax, 1
0x180037c58  jz      loc_180037FD1
0x180037c5e  jmp     loc_180038174
0x180037c63  mov     rbx, [rsp+290h+StringUuid]
0x180037c68  lea     rdx, [rsp+290h+Uuid]; Uuid
0x180037c6d  xorps   xmm0, xmm0
0x180037c70  mov     [rsp+290h+psz], 0
0x180037c79  mov     rcx, rbx; StringUuid
0x180037c7c  movups  xmmword ptr [rsp+290h+Uuid.Data1], xmm0
0x180037c81  call    cs:__imp_UuidFromStringW
0x180037c88  nop     dword ptr [rax+rax+00h]
0x180037c8d  test    eax, eax
0x180037c8f  jz      short loc_180037CBC
0x180037c91  lea     rdx, [rsp+290h+Uuid]; Uuid
0x180037c96  mov     rcx, rbx; StringUuid
0x180037c99  call    cs:__imp_UuidFromStringW
0x180037ca0  nop     dword ptr [rax+rax+00h]
0x180037ca5  mov     ebx, eax
0x180037ca7  or      ebx, 80010000h
0x180037cad  lea     rcx, [rsp+290h+psz]
0x180037cb2  call    ?Release@?$CTSmartObj@PEAGV?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyHeapMem@@@@@@QEAAXXZ; CTSmartObj<ushort *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(void)
0x180037cb7  jmp     loc_180037D61
0x180037cbc  movaps  xmm0, xmmword ptr [rsp+290h+Uuid.Data1]
0x180037cc1  lea     rdx, [rsp+290h+psz]
0x180037cc6  lea     rcx, [rsp+290h+var_250]
0x180037ccb  movdqa  [rsp+290h+var_250], xmm0
0x180037cd1  call    cs:__imp_GetEnrollmentUPN
0x180037cd8  nop     dword ptr [rax+rax+00h]
0x180037cdd  mov     ebx, eax
0x180037cdf  test    eax, eax
0x180037ce1  js      short loc_180037CAD
0x180037ce3  mov     rcx, [rsp+290h+psz]; psz
0x180037ce8  call    cs:__imp_SysAllocString
0x180037cef  nop     dword ptr [rax+rax+00h]
0x180037cf4  mov     [rdi+8], rax
0x180037cf8  lea     rcx, [rsp+290h+psz]
0x180037cfd  test    rax, rax
0x180037d00  jnz     short loc_180037D09
0x180037d02  mov     ebx, 8007000Eh
0x180037d07  jmp     short loc_180037CB2
0x180037d09  mov     [rdi], si
0x180037d0c  jmp     short loc_180037CB2
0x180037d0e  mov     rdx, [r15+80h]; unsigned __int16 *
0x180037d15  lea     r8, [rdi+8]; unsigned __int16 *
0x180037d19  mov     rcx, [rsp+290h+StringUuid]; this
0x180037d1e  call    ?GetManagementServiceAddressesList@DMClient@@YAJPEBG0PEAPEAG@Z; DMClient::GetManagementServiceAddressesList(ushort const *,ushort const *,ushort * *)
0x180037d23  mov     ebx, eax
0x180037d25  test    eax, eax
0x180037d27  js      short loc_180037D61
0x180037d29  mov     [rdi], si
0x180037d2c  jmp     short loc_180037D61
0x180037d2e  mov     rcx, [rsp+290h+StringUuid]; this
0x180037d33  lea     rdx, [rsp+290h+psz]; unsigned __int16 *
0x180037d38  mov     dword ptr [rsp+290h+psz], 0
0x180037d40  call    ?GetSignatureRequired@DMClient@@YAJPEBGPEAK@Z; DMClient::GetSignatureRequired(ushort const *,ulong *)
0x180037d45  mov     ebx, eax
0x180037d47  test    eax, eax
0x180037d49  js      short loc_180037D61
0x180037d4b  cmp     dword ptr [rsp+290h+psz], 0
0x180037d50  ja      loc_18003824A
0x180037d56  xor     esi, esi
0x180037d58  mov     [rdi+8], si
0x180037d5c  mov     word ptr [rdi], 0Bh
0x180037d61  mov     edx, [r15+2Ch]; unsigned int
0x180037d65  lea     rcx, aCdmclientvalue_0; "CDMClientValueNode::GetValue"
0x180037d6c  mov     r8d, ebx; int
0x180037d6f  call    ?Write@DmClientLogging@@SAXPEBGKJH@Z; DmClientLogging::Write(ushort const *,ulong,long,int)
0x180037d74  lea     rcx, [rsp+290h+var_260]
0x180037d79  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180037d7e  mov     rcx, [rsp+290h+StringUuid]; bstrString
0x180037d83  call    cs:__imp_SysFreeString
0x180037d8a  nop     dword ptr [rax+rax+00h]
0x180037d8f  mov     eax, ebx
0x180037d91  mov     rcx, [rbp+190h+var_30]
0x180037d98  xor     rcx, rsp; StackCookie
0x180037d9b  call    __security_check_cookie
0x180037da0  mov     rbx, [rsp+290h+arg_10]
0x180037da8  add     rsp, 270h
0x180037daf  pop     r15
0x180037db1  pop     r14
0x180037db3  pop     rdi
0x180037db4  pop     rsi
0x180037db5  pop     rbp
0x180037db6  retn
0x180037db8  cmp     eax, 24h ; '$'
0x180037dbb  ja      loc_180037F96
0x180037dc1  jz      loc_180037F8B
0x180037dc7  sub     eax, 1Eh
0x180037dca  jz      loc_180037F69
0x180037dd0  sub     eax, 1
0x180037dd3  jz      loc_180037F38
0x180037dd9  sub     eax, 1
0x180037ddc  jz      loc_180037F31
0x180037de2  sub     eax, 1
0x180037de5  jz      loc_180037EA7
0x180037deb  cmp     eax, 2
0x180037dee  jnz     loc_180038174
0x180037df4  xor     edx, edx; Val
0x180037df6  lea     rcx, [rsp+290h+var_22C]; void *
0x180037dfb  mov     r8d, 1FCh; Size
0x180037e01  call    memset_0
0x180037e06  or      esi, 0FFFFFFFFh
0x180037e09  mov     [rsp+290h+var_230], 200h
0x180037e11  mov     r8d, esi
0x180037e14  lea     rdx, [rsp+290h+var_230]
0x180037e19  xor     r14d, r14d
0x180037e1c  lea     ecx, [rsi+38h]
0x180037e1f  call    cs:__imp_OmaDmSetNodeValuePresence
0x180037e26  nop     dword ptr [rax+rax+00h]
0x180037e2b  mov     ebx, eax
0x180037e2d  test    eax, eax
0x180037e2f  js      short loc_180037E7F
0x180037e31  mov     rcx, [rsp+290h+StringUuid]
0x180037e36  lea     r8, [rsp+290h+var_230]
0x180037e3b  lea     edx, [rsi+2]
0x180037e3e  call    cs:__imp_OmaDmGetAcctInfo
0x180037e45  nop     dword ptr [rax+rax+00h]
0x180037e4a  mov     ebx, eax
0x180037e4c  test    eax, eax
0x180037e4e  js      short loc_180037E74
0x180037e50  mov     r8d, esi
0x180037e53  lea     rdx, [rsp+290h+var_230]
0x180037e58  lea     ecx, [rsi+38h]
0x180037e5b  call    cs:__imp_OmaDmIsNodeValuePresent
0x180037e62  nop     dword ptr [rax+rax+00h]
0x180037e67  test    eax, eax
0x180037e69  jz      short loc_180037E7F
0x180037e6b  mov     r14d, [rbp+190h+var_4C]
0x180037e72  jmp     short loc_180037E7F
0x180037e74  xor     eax, eax
0x180037e76  cmp     ebx, 80070002h
0x180037e7c  cmovz   ebx, eax
0x180037e7f  lea     rcx, [rsp+290h+var_230]
0x180037e84  call    cs:__imp_OmaDmFreeAcctInfo
0x180037e8b  nop     dword ptr [rax+rax+00h]
0x180037e90  neg     r14d
0x180037e93  sbb     ax, ax
0x180037e96  mov     [rdi+8], ax
0x180037e9a  test    ebx, ebx
0x180037e9c  js      loc_180037D61
0x180037ea2  jmp     loc_180037D5C
0x180037ea7  mov     rbx, [rsp+290h+StringUuid]
0x180037eac  lea     rdx, [rsp+290h+Uuid]; Uuid
0x180037eb1  xorps   xmm0, xmm0
0x180037eb4  mov     [rsp+290h+psz], 0
0x180037ebd  mov     rcx, rbx; StringUuid
0x180037ec0  movups  xmmword ptr [rsp+290h+Uuid.Data1], xmm0
0x180037ec5  call    cs:__imp_UuidFromStringW
0x180037ecc  nop     dword ptr [rax+rax+00h]
0x180037ed1  test    eax, eax
0x180037ed3  jnz     loc_180037C91
0x180037ed9  movaps  xmm0, xmmword ptr [rsp+290h+Uuid.Data1]
0x180037ede  lea     rdx, [rsp+290h+psz]
0x180037ee3  lea     rcx, [rsp+290h+var_250]
0x180037ee8  movdqa  [rsp+290h+var_250], xmm0
0x180037eee  call    cs:__imp_GetEnrollmentAadResourceUrl
0x180037ef5  nop     dword ptr [rax+rax+00h]
0x180037efa  mov     ebx, eax
0x180037efc  test    eax, eax
0x180037efe  js      loc_180037CAD
0x180037f04  mov     rcx, [rsp+290h+psz]; psz
0x180037f09  call    cs:__imp_SysAllocString
0x180037f10  nop     dword ptr [rax+rax+00h]
0x180037f15  mov     [rdi+8], rax
0x180037f19  lea     rcx, [rsp+290h+psz]
0x180037f1e  test    rax, rax
0x180037f21  jz      loc_180037D02
0x180037f27  mov     word ptr [rdi], 8
0x180037f2c  jmp     loc_180037CB2
0x180037f31  xor     ebx, ebx
0x180037f33  jmp     loc_180037D61
0x180037f38  xor     ebx, ebx
0x180037f3a  mov     word ptr [rdi], 8
0x180037f3f  mov     dl, 1
0x180037f41  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WVD_MultiSession_User_Configuration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WVD_MultiSession_User_Configuration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WVD_MultiSession_User_Configuration> `wil::Feature<__WilFeatureTraits_Feature_WVD_MultiSession_User_Configuration>::GetImpl(void)'::`2'::impl
0x180037f48  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_WVD_MultiSession_User_Configuration@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WVD_MultiSession_User_Configuration>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180037f4d  lea     rcx, a51; "5.1"
0x180037f54  call    cs:__imp_SysAllocString
0x180037f5b  nop     dword ptr [rax+rax+00h]
0x180037f60  mov     [rdi+8], rax
0x180037f64  jmp     loc_180037D61
0x180037f69  mov     rcx, [rsp+290h+StringUuid]; this
0x180037f6e  lea     rdx, [rdi+8]; unsigned __int16 *
0x180037f72  call    ?GetManagementServiceVersion@DMClient@@YAJPEBGPEAPEAG@Z; DMClient::GetManagementServiceVersion(ushort const *,ushort * *)
0x180037f77  mov     ebx, eax
0x180037f79  test    eax, eax
0x180037f7b  js      loc_180037D61
0x180037f81  mov     word ptr [rdi], 8
0x180037f86  jmp     loc_180037D61
0x180037f8b  lea     rcx, [rdi+8]; this
0x180037f8f  call    ?GetAADDeviceID@DMClient@@YAJPEAPEAG@Z; DMClient::GetAADDeviceID(ushort * *)
0x180037f94  jmp     short loc_180037F77
0x180037f96  sub     eax, 25h ; '%'
0x180037f99  jz      loc_18003803B
0x180037f9f  sub     eax, 1
0x180037fa2  jz      loc_18003802D
0x180037fa8  sub     eax, 1
0x180037fab  jz      short loc_180037FFE
0x180037fad  sub     eax, 1
0x180037fb0  jz      short loc_180037FF0
0x180037fb2  cmp     eax, 1
0x180037fb5  jnz     loc_180038174
0x180037fbb  mov     rcx, [r15+88h]
0x180037fc2  call    ?VerifyScopeForConfigSource@@YAJPEAVCConfigServiceProvider2Impl@@W4EnrollmentEnrollType@@@Z; VerifyScopeForConfigSource(CConfigServiceProvider2Impl *,EnrollmentEnrollType)
0x180037fc7  mov     ebx, eax
0x180037fc9  test    eax, eax
0x180037fcb  js      loc_180037D61
0x180037fd1  mov     r8, [r15+20h]; unsigned __int16 *
0x180037fd5  mov     r9, rdi; unsigned __int16 *
0x180037fd8  mov     rdx, [r15+80h]; unsigned __int16 *
0x180037fdf  mov     rcx, [rsp+290h+StringUuid]; this
0x180037fe4  call    ?GetProviderPolicyValue@DMClient@@YAJPEBG00PEAUtagVARIANT@@@Z; DMClient::GetProviderPolicyValue(ushort const *,ushort const *,ushort const *,tagVARIANT *)
0x180037fe9  mov     ebx, eax
0x180037feb  jmp     loc_180037D61
0x180037ff0  lea     rcx, [rdi+8]; unsigned __int16 **
0x180037ff4  call    ?GetCommercialID@@YAJPEAPEAG@Z; GetCommercialID(ushort * *)
0x180037ff9  jmp     loc_180037F77
0x180037ffe  xor     edx, edx
0x180038000  lea     rcx, [rsp+290h+var_260]
0x180038005  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003800a  mov     rcx, [rsp+290h+StringUuid]; this
0x18003800f  lea     rdx, [rsp+290h+var_260]; unsigned __int16 *
0x180038014  call    ?GetManagementServerAddressList@DMClient@@YAJPEBGPEAPEAG@Z; DMClient::GetManagementServerAddressList(ushort const *,ushort * *)
0x180038019  mov     ebx, eax
0x18003801b  test    eax, eax
0x18003801d  js      loc_180037D61
0x180038023  mov     rcx, qword ptr [rsp+290h+var_260]
0x180038028  jmp     loc_180038125
0x18003802d  lea     rcx, [rdi+8]; this
0x180038031  call    ?GetHardwareDevID@DMClient@@YAJPEAPEAG@Z; DMClient::GetHardwareDevID(ushort * *)
0x180038036  jmp     loc_180037F77
0x18003803b  mov     rbx, [rsp+290h+StringUuid]
0x180038040  lea     rdx, [rsp+290h+Uuid]; Uuid
0x180038045  xorps   xmm0, xmm0
0x180038048  mov     rcx, rbx; StringUuid
0x18003804b  movups  xmmword ptr [rsp+290h+Uuid.Data1], xmm0
0x180038050  call    cs:__imp_UuidFromStringW
0x180038057  nop     dword ptr [rax+rax+00h]
0x18003805c  test    eax, eax
0x18003805e  jz      short loc_180038081
0x180038060  lea     rdx, [rsp+290h+Uuid]; Uuid
0x180038065  mov     rcx, rbx; StringUuid
0x180038068  call    cs:__imp_UuidFromStringW
0x18003806f  nop     dword ptr [rax+rax+00h]
0x180038074  mov     ebx, eax
0x180038076  or      ebx, 80010000h
0x18003807c  jmp     loc_180037D61
  ... truncated ...
```
