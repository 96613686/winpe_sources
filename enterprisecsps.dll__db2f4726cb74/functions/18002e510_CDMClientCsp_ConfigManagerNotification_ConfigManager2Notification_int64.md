# CDMClientCsp::ConfigManagerNotification(ConfigManager2Notification,__int64)

- ea: `0x18002e510`
- end: `0x18002e9fe`
- name: `?ConfigManagerNotification@CDMClientCsp@@UEAAJW4ConfigManager2Notification@@_J@Z`
- size: `1262`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180008de0`
- `0x18000d4d4`
- `0x18001a114`
- `0x180025a78`
- `0x1800297ec`
- `0x18002e4b0`
- `0x18002e510`
- `0x180036b00`
- `0x180036ce8`
- `0x1800d11a4`
- `0x1800d15fc`
- `0x1800d6950`
- `0x1800dcc0c`
- `0x1800de394`
- `0x1800de864`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002e66d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002e66d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002e5d5`
- `OLEAUT32!__imp_SysFreeString` at `0x18002e953`
- `OLEAUT32!__imp_SysFreeString` at `0x18002e962`
- `OLEAUT32!__imp_SysFreeString` at `0x18002e9aa`
- `OLEAUT32!__imp_SysFreeString` at `0x18002e5d5`
- `OLEAUT32!__imp_SysFreeString` at `0x18002e953`
- `OLEAUT32!__imp_SysFreeString` at `0x18002e962`
- `OLEAUT32!__imp_SysFreeString` at `0x18002e9aa`
- `OLEAUT32!__imp_VariantInit` at `0x18002e6ac`
- `OLEAUT32!__imp_VariantInit` at `0x18002e7f1`
- `OLEAUT32!__imp_VariantInit` at `0x18002e6ac`
- `OLEAUT32!__imp_VariantInit` at `0x18002e7f1`
- `RPCRT4!UuidFromStringW` at `0x18002e58f`
- `RPCRT4!UuidFromStringW` at `0x18002e5a6`
- `RPCRT4!UuidFromStringW` at `0x18002e58f`
- `RPCRT4!UuidFromStringW` at `0x18002e5a6`
- `DMCmnUtils!DmDeleteTask` at `0x18002e738`
- `DMCmnUtils!DmDeleteTask` at `0x18002e776`
- `DMCmnUtils!DmDeleteTask` at `0x18002e880`
- `DMCmnUtils!DmDeleteTask` at `0x18002e8be`
- `DMCmnUtils!DmDeleteTask` at `0x18002e738`
- `DMCmnUtils!DmDeleteTask` at `0x18002e776`
- `DMCmnUtils!DmDeleteTask` at `0x18002e880`
- `DMCmnUtils!DmDeleteTask` at `0x18002e8be`
- `DMCmnUtils!BigStrcat` at `0x18002e71b`
- `DMCmnUtils!BigStrcat` at `0x18002e863`
- `DMCmnUtils!BigStrcat` at `0x18002e71b`
- `DMCmnUtils!BigStrcat` at `0x18002e863`
- `dmEnrollEngine!GetEnrollmentSID` at `0x18002e656`
- `dmEnrollEngine!GetEnrollmentSID` at `0x18002e656`
- `dmEnrollEngine!GetEnrollmentType` at `0x18002e600`
- `dmEnrollEngine!GetEnrollmentType` at `0x18002e600`

## string_xrefs

- `0x18002e727`: `Login Schedule created by enrollment client`
- `0x18002e765`: `Login Schedule created by enrollment client`
- `0x18002e7b2`: `Login Schedule created by enrollment client`
- `0x18002e86f`: `First Login Schedule created by enrollment client`
- `0x18002e8ad`: `First Login Schedule created by enrollment client`
- `0x18002e8fa`: `First Login Schedule created by enrollment client`

## pseudocode

```c
__int64 __fastcall CDMClientCsp::ConfigManagerNotification(
        struct CConfigServiceProvider2Impl *a1,
        unsigned int a2,
        __int64 a3)
{
  BSTR v3; // rdi
  unsigned int v4; // r15d
  unsigned int v6; // r14d
  unsigned int v7; // esi
  const unsigned __int16 *EnrollmentId2; // rax
  unsigned __int16 *v9; // rbx
  unsigned int v10; // edi
  const unsigned __int16 *SID; // rax
  const unsigned __int16 *v13; // r12
  OLECHAR *v14; // rdi
  unsigned __int8 v15; // r15
  struct tagVARIANT *v16; // r9
  int v17; // esi
  int v18; // r15d
  int v19; // eax
  CEnrollmentLogger *v20; // rax
  struct tagVARIANT *v21; // r9
  int PollValue; // esi
  int v23; // r15d
  int v24; // eax
  CEnrollmentLogger *Logger; // rax
  const unsigned __int16 *v26; // rax
  OLECHAR *v27; // rbx
  int v28; // [rsp+20h] [rbp-79h]
  char v29; // [rsp+40h] [rbp-59h]
  unsigned int v30; // [rsp+44h] [rbp-55h] BYREF
  __int64 v31; // [rsp+48h] [rbp-51h] BYREF
  unsigned int v32; // [rsp+50h] [rbp-49h]
  RPC_WSTR StringUuid[2]; // [rsp+60h] [rbp-39h] BYREF
  unsigned int v34; // [rsp+70h] [rbp-29h]
  BSTR bstrString; // [rsp+78h] [rbp-21h] BYREF
  VARIANTARG pvarg; // [rsp+80h] [rbp-19h] BYREF
  UUID Uuid; // [rsp+A0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  bstrString = (BSTR)a3;
  v3 = (BSTR)a3;
  v34 = a2;
  v4 = a2;
  if ( a2 != 3 )
  {
    if ( !a2 && a3 )
      *((_DWORD *)a1 + 26) = *(_DWORD *)(a3 + 4);
    return CConfigServiceProvider2Impl::ConfigManagerNotification(a1, v4, v3);
  }
  v6 = DMClient::g_PollValueChanged;
  v7 = DMClient::g_MultipleSessionValueChanged;
  v32 = DMClient::g_MultipleSessionValueChanged;
  if ( DMClient::g_PollValueChanged )
  {
    EnrollmentId2 = GetEnrollmentId2(a1);
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)StringUuid, EnrollmentId2);
    v9 = StringUuid[0];
    Uuid = 0;
    if ( UuidFromStringW(StringUuid[0], &Uuid) )
    {
      v10 = UuidFromStringW(v9, &Uuid) | 0x80010000;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA6,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmclient\\dmclientcsp.cpp",
        (const char *)v10,
        v28);
      SysFreeString(v9);
      return v10;
    }
    *(UUID *)StringUuid = Uuid;
    v30 = 63;
    GetEnrollmentType(StringUuid, &v30);
    SID = GetSID(a1);
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)StringUuid, SID);
    v13 = 0;
    v14 = StringUuid[0];
    v31 = 0;
    if ( ((1LL << v30) & 0x9402021) != 0 )
    {
      v15 = 1;
      *(UUID *)StringUuid = Uuid;
      v29 = 1;
      if ( (int)GetEnrollmentSID(StringUuid, &v31) >= 0 && !(unsigned int)_o__wcsicmp(v14, v31) )
        v13 = v14;
    }
    else
    {
      v15 = 0;
      v29 = 0;
    }
    if ( !v9 )
      goto LABEL_57;
    memset(&pvarg, 0, sizeof(pvarg));
    if ( (v6 & 0x40) == 0 )
    {
LABEL_33:
      if ( (v6 & 0x80u) == 0 )
      {
LABEL_54:
        if ( v6 )
          SyncPollingOptions(v9);
        v7 = v32;
LABEL_57:
        DMClient::g_PollValueChanged &= ~v6;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v31);
        SysFreeString(v14);
        SysFreeString(v9);
        v3 = bstrString;
        v4 = v34;
        goto LABEL_58;
      }
      VariantInit(&pvarg);
      PollValue = DMClient::GetPollValue((DMClient *)v9, L"AllUsersPollOnFirstLogin", &pvarg.vt, v21);
      if ( PollValue < 0 )
      {
LABEL_53:
        Logger = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogLoginTaskScheduled(
          Logger,
          L"First Login Schedule created by enrollment client",
          v30,
          pvarg.cyVal.Lo,
          v15,
          v13 != 0,
          PollValue);
        v6 &= ~0x80u;
        goto LABEL_54;
      }
      if ( pvarg.lVal == 1 )
      {
        if ( !v15 || v13 )
          PollValue = ScheduleOneOmaDmSessionOnLogin(v9, v13, 1);
        else
          PollValue = -2102788088;
        goto LABEL_53;
      }
      v23 = 0;
      if ( v31 )
      {
        StringUuid[0] = BigStrcat(2u, v31, L"\\EnterpriseMgmt");
        v24 = DmDeleteTask(StringUuid[0], v9, L"First Login Schedule created by enrollment client");
        v23 = v24;
        if ( (unsigned int)(v24 + 2147024894) <= 1 || v24 == -2147023728 )
          v23 = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(StringUuid);
      }
      PollValue = DmDeleteTask(
                    L"\\Microsoft\\Windows\\EnterpriseMgmt",
                    v9,
                    L"First Login Schedule created by enrollment client");
      if ( (unsigned int)(PollValue + 2147024894) <= 1 || PollValue == -2147023728 )
      {
        PollValue = 0;
      }
      else if ( PollValue )
      {
LABEL_52:
        v15 = v29;
        goto LABEL_53;
      }
      if ( v23 )
        PollValue = v23;
      goto LABEL_52;
    }
    VariantInit(&pvarg);
    v17 = DMClient::GetPollValue((DMClient *)v9, L"PollOnLogin", &pvarg.vt, v16);
    if ( v17 < 0 )
    {
LABEL_32:
      v20 = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogLoginTaskScheduled(
        v20,
        L"Login Schedule created by enrollment client",
        v30,
        pvarg.cyVal.Lo,
        v15,
        v13 != 0,
        v17);
      v6 &= ~0x40u;
      goto LABEL_33;
    }
    if ( pvarg.lVal == 1 )
    {
      if ( !v15 || v13 )
        v17 = ScheduleOneOmaDmSessionOnLogin(v9, v13, 0);
      else
        v17 = -2102788088;
      goto LABEL_32;
    }
    v18 = 0;
    if ( v31 )
    {
      StringUuid[0] = BigStrcat(2u, v31, L"\\EnterpriseMgmt");
      v19 = DmDeleteTask(StringUuid[0], v9, L"Login Schedule created by enrollment client");
      v18 = v19;
      if ( (unsigned int)(v19 + 2147024894) <= 1 || v19 == -2147023728 )
        v18 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(StringUuid);
    }
    v17 = DmDeleteTask(L"\\Microsoft\\Windows\\EnterpriseMgmt", v9, L"Login Schedule created by enrollment client");
    if ( (unsigned int)(v17 + 2147024894) <= 1 || v17 == -2147023728 )
    {
      v17 = 0;
    }
    else if ( v17 )
    {
LABEL_31:
      v15 = v29;
      goto LABEL_32;
    }
    if ( v18 )
      v17 = v18;
    goto LABEL_31;
  }
LABEL_58:
  if ( v7 )
  {
    v26 = GetEnrollmentId2(a1);
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, v26);
    v27 = bstrString;
    if ( bstrString )
      SyncPollingOptionsForMultipleSession(bstrString);
    DMClient::g_MultipleSessionValueChanged &= ~v7;
    SysFreeString(v27);
  }
  return CConfigServiceProvider2Impl::ConfigManagerNotification(a1, v4, v3);
}

```

## disassembly

```asm
0x18002e510  mov     [rsp-8+arg_8], rbx
0x18002e515  push    rbp
0x18002e516  push    rsi
0x18002e517  push    rdi
0x18002e518  push    r12
0x18002e51a  push    r13
0x18002e51c  push    r14
0x18002e51e  push    r15
0x18002e520  lea     rbp, [rsp-27h]
0x18002e525  sub     rsp, 0C0h
0x18002e52c  mov     rax, cs:__security_cookie
0x18002e533  xor     rax, rsp
0x18002e536  mov     [rbp+57h+var_40], rax
0x18002e53a  mov     [rbp+57h+bstrString], r8
0x18002e53e  mov     rdi, r8
0x18002e541  mov     [rbp+57h+var_80], edx
0x18002e544  mov     r15d, edx
0x18002e547  mov     r13, rcx
0x18002e54a  cmp     edx, 3
0x18002e54d  jnz     loc_18002E9B8
0x18002e553  mov     r14d, cs:?g_PollValueChanged@DMClient@@3KA; ulong DMClient::g_PollValueChanged
0x18002e55a  mov     esi, cs:?g_MultipleSessionValueChanged@DMClient@@3KA; ulong DMClient::g_MultipleSessionValueChanged
0x18002e560  mov     [rbp+57h+var_A0], esi
0x18002e563  test    r14d, r14d
0x18002e566  jz      loc_18002E976
0x18002e56c  call    ?GetEnrollmentId2@@YAPEAGPEAVCConfigServiceProvider2Impl@@@Z; GetEnrollmentId2(CConfigServiceProvider2Impl *)
0x18002e571  mov     rdx, rax; unsigned __int16 *
0x18002e574  lea     rcx, [rbp+57h+StringUuid]; this
0x18002e578  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18002e57d  mov     rbx, [rbp+57h+StringUuid]
0x18002e581  lea     rdx, [rbp+57h+Uuid]; Uuid
0x18002e585  xorps   xmm0, xmm0
0x18002e588  mov     rcx, rbx; StringUuid
0x18002e58b  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x18002e58f  call    cs:__imp_UuidFromStringW
0x18002e596  nop     dword ptr [rax+rax+00h]
0x18002e59b  test    eax, eax
0x18002e59d  jz      short loc_18002E5E8
0x18002e59f  lea     rdx, [rbp+57h+Uuid]; Uuid
0x18002e5a3  mov     rcx, rbx; StringUuid
0x18002e5a6  call    cs:__imp_UuidFromStringW
0x18002e5ad  nop     dword ptr [rax+rax+00h]
0x18002e5b2  mov     rcx, [rbp+5Fh]; this
0x18002e5b6  lea     r8, aOnecoreuapAdmi_70; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18002e5bd  mov     edi, eax
0x18002e5bf  mov     edx, 0A6h; void *
0x18002e5c4  or      edi, 80010000h
0x18002e5ca  mov     r9d, edi; char *
0x18002e5cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e5d2  mov     rcx, rbx; bstrString
0x18002e5d5  call    cs:__imp_SysFreeString
0x18002e5dc  nop     dword ptr [rax+rax+00h]
0x18002e5e1  mov     eax, edi
0x18002e5e3  jmp     loc_18002E9D6
0x18002e5e8  movaps  xmm0, xmmword ptr [rbp+57h+Uuid.Data1]
0x18002e5ec  lea     rdx, [rbp+57h+var_AC]
0x18002e5f0  lea     rcx, [rbp+57h+StringUuid]
0x18002e5f4  movdqa  xmmword ptr [rbp+57h+StringUuid], xmm0
0x18002e5f9  mov     [rbp+57h+var_AC], 3Fh ; '?'
0x18002e600  call    cs:__imp_GetEnrollmentType
0x18002e607  nop     dword ptr [rax+rax+00h]
0x18002e60c  mov     rcx, r13; struct CConfigServiceProvider2Impl *
0x18002e60f  call    ?GetSID@@YAPEAGPEAVCConfigServiceProvider2Impl@@@Z; GetSID(CConfigServiceProvider2Impl *)
0x18002e614  mov     rdx, rax; unsigned __int16 *
0x18002e617  lea     rcx, [rbp+57h+StringUuid]; this
0x18002e61b  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18002e620  mov     ecx, [rbp+57h+var_AC]
0x18002e623  xor     r12d, r12d
0x18002e626  mov     rdi, [rbp+57h+StringUuid]
0x18002e62a  mov     [rbp+57h+var_A8], r12
0x18002e62e  lea     eax, [r12+1]
0x18002e633  shl     rax, cl
0x18002e636  test    rax, 9402021h
0x18002e63c  jz      short loc_18002E681
0x18002e63e  movaps  xmm0, xmmword ptr [rbp+57h+Uuid.Data1]
0x18002e642  lea     rdx, [rbp+57h+var_A8]
0x18002e646  mov     r15b, 1
0x18002e649  movdqa  xmmword ptr [rbp+57h+StringUuid], xmm0
0x18002e64e  lea     rcx, [rbp+57h+StringUuid]
0x18002e652  mov     [rbp+57h+var_B0], r15b
0x18002e656  call    cs:__imp_GetEnrollmentSID
0x18002e65d  nop     dword ptr [rax+rax+00h]
0x18002e662  test    eax, eax
0x18002e664  js      short loc_18002E688
0x18002e666  mov     rdx, [rbp+57h+var_A8]
0x18002e66a  mov     rcx, rdi
0x18002e66d  call    cs:__imp__o__wcsicmp
0x18002e674  nop     dword ptr [rax+rax+00h]
0x18002e679  test    eax, eax
0x18002e67b  cmovz   r12, rdi
0x18002e67f  jmp     short loc_18002E688
0x18002e681  xor     r15b, r15b
0x18002e684  mov     [rbp+57h+var_B0], r15b
0x18002e688  test    rbx, rbx
0x18002e68b  jz      loc_18002E93D
0x18002e691  xor     eax, eax
0x18002e693  xorps   xmm0, xmm0
0x18002e696  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18002e69a  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18002e69e  test    r14b, 40h
0x18002e6a2  jz      loc_18002E7E4
0x18002e6a8  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002e6ac  call    cs:__imp_VariantInit
0x18002e6b3  nop     dword ptr [rax+rax+00h]
0x18002e6b8  lea     r8, [rbp+57h+pvarg]; unsigned __int16 *
0x18002e6bc  mov     rcx, rbx; this
0x18002e6bf  lea     rdx, aPollonlogin; "PollOnLogin"
0x18002e6c6  call    ?GetPollValue@DMClient@@YAJPEBG0PEAUtagVARIANT@@@Z; DMClient::GetPollValue(ushort const *,ushort const *,tagVARIANT *)
0x18002e6cb  mov     esi, eax
0x18002e6cd  test    eax, eax
0x18002e6cf  js      loc_18002E7A9
0x18002e6d5  cmp     dword ptr [rbp+57h+pvarg+8], 1
0x18002e6d9  jnz     short loc_18002E704
0x18002e6db  test    r15b, r15b
0x18002e6de  jz      short loc_18002E6EF
0x18002e6e0  test    r12, r12
0x18002e6e3  jnz     short loc_18002E6EF
0x18002e6e5  mov     esi, 82AA0008h
0x18002e6ea  jmp     loc_18002E7A9
0x18002e6ef  xor     r8d, r8d; int
0x18002e6f2  mov     rdx, r12; unsigned __int16 *
0x18002e6f5  mov     rcx, rbx; unsigned __int16 *
0x18002e6f8  call    ?ScheduleOneOmaDmSessionOnLogin@@YAJPEBG0H@Z; ScheduleOneOmaDmSessionOnLogin(ushort const *,ushort const *,int)
0x18002e6fd  mov     esi, eax
0x18002e6ff  jmp     loc_18002E7A9
0x18002e704  mov     rdx, [rbp+57h+var_A8]
0x18002e708  xor     r15d, r15d
0x18002e70b  test    rdx, rdx
0x18002e70e  jz      short loc_18002E765
0x18002e710  lea     r8, aEnterprisemgmt_0; "\\EnterpriseMgmt"
0x18002e717  lea     ecx, [r15+2]
0x18002e71b  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x18002e722  nop     dword ptr [rax+rax+00h]
0x18002e727  lea     r8, aLoginScheduleC; "Login Schedule created by enrollment cl"...
0x18002e72e  mov     rdx, rbx
0x18002e731  mov     rcx, rax
0x18002e734  mov     [rbp+57h+StringUuid], rax
0x18002e738  call    cs:__imp_?DmDeleteTask@@YAJPEBG00@Z; DmDeleteTask(ushort const *,ushort const *,ushort const *)
0x18002e73f  nop     dword ptr [rax+rax+00h]
0x18002e744  mov     r15d, eax
0x18002e747  lea     ecx, [rax+7FF8FFFEh]
0x18002e74d  cmp     ecx, 1
0x18002e750  jbe     short loc_18002E759
0x18002e752  cmp     eax, 80070490h
0x18002e757  jnz     short loc_18002E75C
0x18002e759  xor     r15d, r15d
0x18002e75c  lea     rcx, [rbp+57h+StringUuid]
0x18002e760  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002e765  lea     r8, aLoginScheduleC; "Login Schedule created by enrollment cl"...
0x18002e76c  mov     rdx, rbx
0x18002e76f  lea     rcx, aMicrosoftWindo_3; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x18002e776  call    cs:__imp_?DmDeleteTask@@YAJPEBG00@Z; DmDeleteTask(ushort const *,ushort const *,ushort const *)
0x18002e77d  nop     dword ptr [rax+rax+00h]
0x18002e782  mov     esi, eax
0x18002e784  add     eax, 7FF8FFFEh
0x18002e789  cmp     eax, 1
0x18002e78c  jbe     short loc_18002E79C
0x18002e78e  cmp     esi, 80070490h
0x18002e794  jz      short loc_18002E79C
0x18002e796  test    esi, esi
0x18002e798  jnz     short loc_18002E7A5
0x18002e79a  jmp     short loc_18002E79E
0x18002e79c  xor     esi, esi
0x18002e79e  test    r15d, r15d
0x18002e7a1  cmovnz  esi, r15d
0x18002e7a5  mov     r15b, [rbp+57h+var_B0]
0x18002e7a9  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18002e7ae  mov     r9d, dword ptr [rbp+57h+pvarg+8]; unsigned int
0x18002e7b2  lea     rdx, aLoginScheduleC; "Login Schedule created by enrollment cl"...
0x18002e7b9  xor     r8d, r8d
0x18002e7bc  movzx   ecx, r15b
0x18002e7c0  mov     [rsp+0F0h+var_C0], esi; int
0x18002e7c4  test    r12, r12
0x18002e7c7  setnz   r8b
0x18002e7cb  mov     [rsp+0F0h+var_C8], r8d; int
0x18002e7d0  mov     r8d, [rbp+57h+var_AC]; unsigned int
0x18002e7d4  mov     [rsp+0F0h+var_D0], ecx; int
0x18002e7d8  mov     rcx, rax; this
0x18002e7db  call    ?LogLoginTaskScheduled@CEnrollmentLogger@@QEAAXPEBGIKHHJ@Z; CEnrollmentLogger::LogLoginTaskScheduled(ushort const *,uint,ulong,int,int,long)
0x18002e7e0  and     r14d, 0FFFFFFBFh
0x18002e7e4  test    r14b, r14b
0x18002e7e7  jns     loc_18002E92D
0x18002e7ed  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002e7f1  call    cs:__imp_VariantInit
0x18002e7f8  nop     dword ptr [rax+rax+00h]
0x18002e7fd  lea     r8, [rbp+57h+pvarg]; unsigned __int16 *
0x18002e801  mov     rcx, rbx; this
0x18002e804  lea     rdx, aAlluserspollon; "AllUsersPollOnFirstLogin"
0x18002e80b  call    ?GetPollValue@DMClient@@YAJPEBG0PEAUtagVARIANT@@@Z; DMClient::GetPollValue(ushort const *,ushort const *,tagVARIANT *)
0x18002e810  mov     esi, eax
0x18002e812  test    eax, eax
0x18002e814  js      loc_18002E8F1
0x18002e81a  cmp     dword ptr [rbp+57h+pvarg+8], 1
0x18002e81e  jnz     short loc_18002E84C
0x18002e820  test    r15b, r15b
0x18002e823  jz      short loc_18002E834
0x18002e825  test    r12, r12
0x18002e828  jnz     short loc_18002E834
0x18002e82a  mov     esi, 82AA0008h
0x18002e82f  jmp     loc_18002E8F1
0x18002e834  mov     r8d, 1; int
0x18002e83a  mov     rdx, r12; unsigned __int16 *
0x18002e83d  mov     rcx, rbx; unsigned __int16 *
0x18002e840  call    ?ScheduleOneOmaDmSessionOnLogin@@YAJPEBG0H@Z; ScheduleOneOmaDmSessionOnLogin(ushort const *,ushort const *,int)
0x18002e845  mov     esi, eax
0x18002e847  jmp     loc_18002E8F1
0x18002e84c  mov     rdx, [rbp+57h+var_A8]
0x18002e850  xor     r15d, r15d
0x18002e853  test    rdx, rdx
0x18002e856  jz      short loc_18002E8AD
0x18002e858  lea     r8, aEnterprisemgmt_0; "\\EnterpriseMgmt"
0x18002e85f  lea     ecx, [r15+2]
0x18002e863  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x18002e86a  nop     dword ptr [rax+rax+00h]
0x18002e86f  lea     r8, aFirstLoginSche; "First Login Schedule created by enrollm"...
0x18002e876  mov     rdx, rbx
0x18002e879  mov     rcx, rax
0x18002e87c  mov     [rbp+57h+StringUuid], rax
0x18002e880  call    cs:__imp_?DmDeleteTask@@YAJPEBG00@Z; DmDeleteTask(ushort const *,ushort const *,ushort const *)
0x18002e887  nop     dword ptr [rax+rax+00h]
0x18002e88c  mov     r15d, eax
0x18002e88f  lea     ecx, [rax+7FF8FFFEh]
0x18002e895  cmp     ecx, 1
0x18002e898  jbe     short loc_18002E8A1
0x18002e89a  cmp     eax, 80070490h
0x18002e89f  jnz     short loc_18002E8A4
0x18002e8a1  xor     r15d, r15d
0x18002e8a4  lea     rcx, [rbp+57h+StringUuid]
0x18002e8a8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002e8ad  lea     r8, aFirstLoginSche; "First Login Schedule created by enrollm"...
0x18002e8b4  mov     rdx, rbx
0x18002e8b7  lea     rcx, aMicrosoftWindo_3; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x18002e8be  call    cs:__imp_?DmDeleteTask@@YAJPEBG00@Z; DmDeleteTask(ushort const *,ushort const *,ushort const *)
0x18002e8c5  nop     dword ptr [rax+rax+00h]
0x18002e8ca  mov     esi, eax
0x18002e8cc  add     eax, 7FF8FFFEh
0x18002e8d1  cmp     eax, 1
0x18002e8d4  jbe     short loc_18002E8E4
0x18002e8d6  cmp     esi, 80070490h
0x18002e8dc  jz      short loc_18002E8E4
0x18002e8de  test    esi, esi
0x18002e8e0  jnz     short loc_18002E8ED
0x18002e8e2  jmp     short loc_18002E8E6
0x18002e8e4  xor     esi, esi
0x18002e8e6  test    r15d, r15d
0x18002e8e9  cmovnz  esi, r15d
0x18002e8ed  mov     r15b, [rbp+57h+var_B0]
0x18002e8f1  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18002e8f6  mov     r9d, dword ptr [rbp+57h+pvarg+8]; unsigned int
0x18002e8fa  lea     rdx, aFirstLoginSche; "First Login Schedule created by enrollm"...
0x18002e901  xor     r8d, r8d
0x18002e904  movzx   ecx, r15b
0x18002e908  mov     [rsp+0F0h+var_C0], esi; int
0x18002e90c  test    r12, r12
0x18002e90f  setnz   r8b
0x18002e913  mov     [rsp+0F0h+var_C8], r8d; int
0x18002e918  mov     r8d, [rbp+57h+var_AC]; unsigned int
0x18002e91c  mov     [rsp+0F0h+var_D0], ecx; int
0x18002e920  mov     rcx, rax; this
0x18002e923  call    ?LogLoginTaskScheduled@CEnrollmentLogger@@QEAAXPEBGIKHHJ@Z; CEnrollmentLogger::LogLoginTaskScheduled(ushort const *,uint,ulong,int,int,long)
0x18002e928  btr     r14d, 7
0x18002e92d  test    r14d, r14d
0x18002e930  jz      short loc_18002E93A
0x18002e932  mov     rcx, rbx
0x18002e935  call    ?SyncPollingOptions@@YAJPEBG0_NW4EnrollmentEnrollType@@1@Z; SyncPollingOptions(ushort const *,ushort const *,bool,EnrollmentEnrollType,bool)
0x18002e93a  mov     esi, [rbp+57h+var_A0]
0x18002e93d  not     r14d
0x18002e940  lea     rcx, [rbp+57h+var_A8]
0x18002e944  and     cs:?g_PollValueChanged@DMClient@@3KA, r14d; ulong DMClient::g_PollValueChanged
0x18002e94b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002e950  mov     rcx, rdi; bstrString
0x18002e953  call    cs:__imp_SysFreeString
0x18002e95a  nop     dword ptr [rax+rax+00h]
0x18002e95f  mov     rcx, rbx; bstrString
0x18002e962  call    cs:__imp_SysFreeString
0x18002e969  nop     dword ptr [rax+rax+00h]
0x18002e96e  mov     rdi, [rbp+57h+bstrString]
0x18002e972  mov     r15d, [rbp+57h+var_80]
0x18002e976  test    esi, esi
0x18002e978  jz      short loc_18002E9C8
0x18002e97a  mov     rcx, r13; struct CConfigServiceProvider2Impl *
0x18002e97d  call    ?GetEnrollmentId2@@YAPEAGPEAVCConfigServiceProvider2Impl@@@Z; GetEnrollmentId2(CConfigServiceProvider2Impl *)
0x18002e982  mov     rdx, rax; unsigned __int16 *
0x18002e985  lea     rcx, [rbp+57h+bstrString]; this
0x18002e989  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18002e98e  mov     rbx, [rbp+57h+bstrString]
0x18002e992  test    rbx, rbx
0x18002e995  jz      short loc_18002E99F
0x18002e997  mov     rcx, rbx; pszMore
0x18002e99a  call    ?SyncPollingOptionsForMultipleSession@@YAJPEBG@Z; SyncPollingOptionsForMultipleSession(ushort const *)
0x18002e99f  not     esi
0x18002e9a1  mov     rcx, rbx; bstrString
0x18002e9a4  and     cs:?g_MultipleSessionValueChanged@DMClient@@3KA, esi; ulong DMClient::g_MultipleSessionValueChanged
0x18002e9aa  call    cs:__imp_SysFreeString
0x18002e9b1  nop     dword ptr [rax+rax+00h]
0x18002e9b6  jmp     short loc_18002E9C8
0x18002e9b8  test    edx, edx
0x18002e9ba  jnz     short loc_18002E9C8
0x18002e9bc  test    r8, r8
0x18002e9bf  jz      short loc_18002E9C8
  ... truncated ...
```
