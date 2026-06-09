# CDMClientConfigRefreshNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)

- ea: `0x180031c40`
- end: `0x180031f05`
- name: `?CreateNodeInstance@CDMClientConfigRefreshNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z`
- size: `709`
- prototype: `__int64 __usercall@<rax>(struct CConfigServiceProvider2Impl *@<rcx>, struct IConfigManager2URI *@<rdx>, const struct CSP_NODE_DATA *@<r8>, int@<r9d>, struct ICSPNode **, unsigned int *)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002fca0`
- `0x180030660`

## callees

- `0x18001a4fc`
- `0x180021944`
- `0x180025ac0`
- `0x180028488`
- `0x18002dcc8`
- `0x180030f00`
- `0x180031c40`
- `0x180036b00`
- `0x1800385a4`
- `0x1800db314`
- `0x1800f7338`
- `0x1800f7a7c`
- `0x1800f7b24`
- `0x180107010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180031eb2`
- `OLEAUT32!__imp_SysFreeString` at `0x180031ed8`
- `OLEAUT32!__imp_SysFreeString` at `0x180031eb2`
- `OLEAUT32!__imp_SysFreeString` at `0x180031ed8`
- `OLEAUT32!__imp_VariantInit` at `0x180031c96`
- `OLEAUT32!__imp_VariantInit` at `0x180031c96`
- `DMCmnUtils!DmDisableTask` at `0x180031e27`
- `DMCmnUtils!DmDisableTask` at `0x180031e27`

## string_xrefs

- `0x180031e16`: `Schedule created by dm client to refresh settings`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDMClientConfigRefreshNode::CreateNodeInstance(
        struct CConfigServiceProvider2Impl *a1,
        struct IConfigManager2URI *a2,
        const struct CSP_NODE_DATA *a3,
        int a4,
        struct ICSPNode **a5,
        unsigned int *a6)
{
  struct IConfigManager2URI *v8; // r14
  OLECHAR *v10; // rdi
  int ConfigRefreshKey; // esi
  unsigned __int16 *EnrollmentId2; // rax
  int v13; // eax
  int v14; // r9d
  int v15; // r9d
  CConfigRefreshLogger *Logger; // rax
  unsigned int v17; // edx
  unsigned int v18; // r8d
  CConfigRefreshLogger *v19; // rax
  struct ICSPNode *v20; // rbx
  int v22; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int16 v23[4]; // [rsp+38h] [rbp-40h] BYREF
  struct ICSPNode *v24; // [rsp+40h] [rbp-38h] BYREF
  DMClient *v25; // [rsp+48h] [rbp-30h] BYREF
  __int64 v26; // [rsp+50h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-20h] BYREF

  v8 = a2;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ConfigRefresh>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ConfigRefresh>::GetImpl'::`2'::impl,
    a2);
  v26 = 0;
  v22 = 0;
  v24 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v10 = 0;
  v25 = 0;
  *(_QWORD *)v23 = 0;
  VariantInit(&pvarg);
  if ( a1 && v8 && a3 && a5 && a6 )
  {
    *a5 = 0;
    *a6 = 0;
    ConfigRefreshKey = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, int *))(*(_QWORD *)v8 + 136LL))(v8, &v22);
    if ( ConfigRefreshKey < 0 )
    {
LABEL_29:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v23);
      SysFreeString(v10);
      ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v24);
      return (unsigned int)ConfigRefreshKey;
    }
    EnrollmentId2 = GetEnrollmentId2(a1);
    ATL::CComBSTR::operator=(&v25, EnrollmentId2);
    v10 = (OLECHAR *)v25;
    if ( *((_DWORD *)a3 + 3) == 90 )
    {
      ConfigRefreshKey = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, __int64 *))(*(_QWORD *)v8 + 88LL))(
                           v8,
                           (unsigned int)(v22 - 2),
                           &v26);
      if ( ConfigRefreshKey < 0 )
        goto LABEL_29;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        v23,
        0);
      ConfigRefreshKey = DMClient::GetConfigRefreshKey((DMClient *)v10, v23, 0, v14);
      if ( (int)(ConfigRefreshKey + 0x80000000) >= 0 && ConfigRefreshKey != -2147024894 )
        goto LABEL_29;
      if ( !a4 )
      {
        if ( ConfigRefreshKey == -2147024894 )
        {
          ConfigRefreshKey = -2046820350;
          goto LABEL_29;
        }
        goto LABEL_22;
      }
      if ( ConfigRefreshKey != -2147024894 )
      {
        ConfigRefreshKey = -2046820335;
        goto LABEL_29;
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        v23,
        0);
      ConfigRefreshKey = DMClient::GetConfigRefreshKey((DMClient *)v10, v23, (HKEY *)1, v15);
      if ( ConfigRefreshKey < 0 )
        goto LABEL_29;
      Logger = CConfigRefreshLogger::GetLogger();
      CConfigRefreshLogger::LogConfigRefreshScheduleCreateStart(Logger);
      ConfigRefreshKey = ScheduleConfigRefresh(v10, v17, v18);
      v19 = CConfigRefreshLogger::GetLogger();
      CConfigRefreshLogger::LogConfigRefreshScheduleCreateEnd(v19, ConfigRefreshKey);
      if ( ConfigRefreshKey < 0 )
        goto LABEL_29;
      v13 = DmDisableTask(
              L"\\Microsoft\\Windows\\EnterpriseMgmtNonCritical",
              v10,
              L"Schedule created by dm client to refresh settings");
    }
    else
    {
      if ( *((_DWORD *)a3 + 3) != 91 && (unsigned int)(*((_DWORD *)a3 + 3) - 92) >= 2 )
      {
        ConfigRefreshKey = -2147418113;
        goto LABEL_29;
      }
      v13 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, __int64 *))(*(_QWORD *)v8 + 88LL))(
              v8,
              (unsigned int)(v22 - 3),
              &v26);
    }
    ConfigRefreshKey = v13;
    if ( v13 < 0 )
      goto LABEL_29;
LABEL_22:
    ConfigRefreshKey = ATL::CComObject<CDMClientConfigRefreshNode>::CreateInstance(&v24);
    if ( ConfigRefreshKey >= 0 )
    {
      v20 = v24;
      if ( v24 )
      {
        ConfigRefreshKey = (*(__int64 (__fastcall **)(struct ICSPNode *, struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *))(*(_QWORD *)v24 + 136LL))(
                             v24,
                             a1,
                             v8,
                             a3);
        if ( ConfigRefreshKey >= 0 )
        {
          (*(void (__fastcall **)(struct ICSPNode *))(*(_QWORD *)v20 + 8LL))(v20);
          *((_QWORD *)v20 + 16) = a1;
          v24 = 0;
          *a5 = v20;
        }
      }
      else
      {
        ConfigRefreshKey = -2147024882;
      }
    }
    goto LABEL_29;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v23);
  SysFreeString(0);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v24);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180031c40  push    rbp
0x180031c42  push    rbx
0x180031c43  push    rsi
0x180031c44  push    rdi
0x180031c45  push    r12
0x180031c47  push    r13
0x180031c49  push    r14
0x180031c4b  push    r15
0x180031c4d  mov     rbp, rsp
0x180031c50  sub     rsp, 78h
0x180031c54  mov     ebx, r9d
0x180031c57  mov     r13, r8
0x180031c5a  mov     r14, rdx
0x180031c5d  mov     r12, rcx
0x180031c60  mov     dl, 1
0x180031c62  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ConfigRefresh@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ConfigRefresh@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ConfigRefresh> `wil::Feature<__WilFeatureTraits_Feature_ConfigRefresh>::GetImpl(void)'::`2'::impl
0x180031c69  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ConfigRefresh@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ConfigRefresh>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180031c6e  xor     esi, esi
0x180031c70  mov     [rbp+var_28], rsi
0x180031c74  mov     [rbp+var_48], esi
0x180031c77  mov     [rbp+var_38], rsi
0x180031c7b  xorps   xmm0, xmm0
0x180031c7e  xor     eax, eax
0x180031c80  movups  xmmword ptr [rbp+pvarg], xmm0
0x180031c84  mov     qword ptr [rbp+pvarg+10h], rax
0x180031c88  mov     edi, esi
0x180031c8a  mov     [rbp+var_30], rsi
0x180031c8e  mov     qword ptr [rbp+var_40], rsi
0x180031c92  lea     rcx, [rbp+pvarg]; pvarg
0x180031c96  call    cs:__imp_VariantInit
0x180031c9d  nop     dword ptr [rax+rax+00h]
0x180031ca2  test    r12, r12
0x180031ca5  jz      loc_180031ECC
0x180031cab  test    r14, r14
0x180031cae  jz      loc_180031ECC
0x180031cb4  test    r13, r13
0x180031cb7  jz      loc_180031ECC
0x180031cbd  mov     r15, [rbp+arg_20]
0x180031cc1  test    r15, r15
0x180031cc4  jz      loc_180031ECC
0x180031cca  mov     rax, [rbp+arg_28]
0x180031cce  test    rax, rax
0x180031cd1  jz      loc_180031ECC
0x180031cd7  mov     [r15], rsi
0x180031cda  mov     [rax], esi
0x180031cdc  mov     rax, [r14]
0x180031cdf  lea     rdx, [rbp+var_48]
0x180031ce3  mov     rcx, r14
0x180031ce6  mov     rax, [rax+88h]
0x180031ced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031cf2  mov     esi, eax
0x180031cf4  test    eax, eax
0x180031cf6  js      loc_180031EA5
0x180031cfc  mov     rcx, r12; struct CConfigServiceProvider2Impl *
0x180031cff  call    ?GetEnrollmentId2@@YAPEAGPEAVCConfigServiceProvider2Impl@@@Z; GetEnrollmentId2(CConfigServiceProvider2Impl *)
0x180031d04  mov     rdx, rax
0x180031d07  lea     rcx, [rbp+var_30]
0x180031d0b  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180031d10  mov     ecx, [r13+0Ch]
0x180031d14  mov     rdi, [rbp+var_30]
0x180031d18  sub     ecx, 5Ah ; 'Z'
0x180031d1b  jz      short loc_180031D54
0x180031d1d  sub     ecx, 1
0x180031d20  jz      short loc_180031D36
0x180031d22  sub     ecx, 1
0x180031d25  jz      short loc_180031D36
0x180031d27  cmp     ecx, 1
0x180031d2a  jz      short loc_180031D36
0x180031d2c  mov     esi, 8000FFFFh
0x180031d31  jmp     loc_180031EA5
0x180031d36  mov     rax, [r14]
0x180031d39  mov     edx, [rbp+var_48]
0x180031d3c  add     edx, 0FFFFFFFDh
0x180031d3f  lea     r8, [rbp+var_28]
0x180031d43  mov     rcx, r14
0x180031d46  mov     rax, [rax+58h]
0x180031d4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031d4f  jmp     loc_180031E33
0x180031d54  mov     rax, [r14]
0x180031d57  mov     edx, [rbp+var_48]
0x180031d5a  add     edx, 0FFFFFFFEh
0x180031d5d  lea     r8, [rbp+var_28]
0x180031d61  mov     rcx, r14
0x180031d64  mov     rax, [rax+58h]
0x180031d68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031d6d  mov     esi, eax
0x180031d6f  test    eax, eax
0x180031d71  js      loc_180031EA5
0x180031d77  xor     edx, edx
0x180031d79  lea     rcx, [rbp+var_40]
0x180031d7d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180031d82  xor     r8d, r8d; HKEY *
0x180031d85  lea     rdx, [rbp+var_40]; unsigned __int16 *
0x180031d89  mov     rcx, rdi; this
0x180031d8c  call    ?GetConfigRefreshKey@DMClient@@YAJPEBGPEAPEAUHKEY__@@H@Z; DMClient::GetConfigRefreshKey(ushort const *,HKEY__ * *,int)
0x180031d91  mov     esi, eax
0x180031d93  mov     ecx, 80000000h
0x180031d98  add     eax, ecx
0x180031d9a  mov     edx, 80070002h
0x180031d9f  test    ecx, eax
0x180031da1  jnz     short loc_180031DAB
0x180031da3  cmp     esi, edx
0x180031da5  jnz     loc_180031EA5
0x180031dab  test    ebx, ebx
0x180031dad  jz      loc_180031E58
0x180031db3  cmp     esi, edx
0x180031db5  jz      short loc_180031DC1
0x180031db7  mov     esi, 86000011h
0x180031dbc  jmp     loc_180031EA5
0x180031dc1  xor     edx, edx
0x180031dc3  lea     rcx, [rbp+var_40]
0x180031dc7  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180031dcc  mov     r8d, 1; HKEY *
0x180031dd2  lea     rdx, [rbp+var_40]; unsigned __int16 *
0x180031dd6  mov     rcx, rdi; this
0x180031dd9  call    ?GetConfigRefreshKey@DMClient@@YAJPEBGPEAPEAUHKEY__@@H@Z; DMClient::GetConfigRefreshKey(ushort const *,HKEY__ * *,int)
0x180031dde  mov     esi, eax
0x180031de0  test    eax, eax
0x180031de2  js      loc_180031EA5
0x180031de8  call    ?GetLogger@CConfigRefreshLogger@@SAPEAV1@XZ; CConfigRefreshLogger::GetLogger(void)
0x180031ded  mov     rcx, rax; this
0x180031df0  call    ?LogConfigRefreshScheduleCreateStart@CConfigRefreshLogger@@QEAAXXZ; CConfigRefreshLogger::LogConfigRefreshScheduleCreateStart(void)
0x180031df5  mov     rcx, rdi; unsigned __int16 *
0x180031df8  call    ?ScheduleConfigRefresh@@YAJPEBGKK@Z; ScheduleConfigRefresh(ushort const *,ulong,ulong)
0x180031dfd  mov     esi, eax
0x180031dff  call    ?GetLogger@CConfigRefreshLogger@@SAPEAV1@XZ; CConfigRefreshLogger::GetLogger(void)
0x180031e04  mov     edx, esi; int
0x180031e06  mov     rcx, rax; this
0x180031e09  call    ?LogConfigRefreshScheduleCreateEnd@CConfigRefreshLogger@@QEAAXJ@Z; CConfigRefreshLogger::LogConfigRefreshScheduleCreateEnd(long)
0x180031e0e  test    esi, esi
0x180031e10  js      loc_180031EA5
0x180031e16  lea     r8, aScheduleCreate; "Schedule created by dm client to refres"...
0x180031e1d  mov     rdx, rdi
0x180031e20  lea     rcx, aMicrosoftWindo_1; "\\Microsoft\\Windows\\EnterpriseMgmtNon"...
0x180031e27  call    cs:__imp_?DmDisableTask@@YAJPEBG00@Z; DmDisableTask(ushort const *,ushort const *,ushort const *)
0x180031e2e  nop     dword ptr [rax+rax+00h]
0x180031e33  mov     esi, eax
0x180031e35  test    eax, eax
0x180031e37  js      short loc_180031EA5
0x180031e39  lea     rcx, [rbp+var_38]
0x180031e3d  call    ?CreateInstance@?$CComObject@VCDMClientConfigRefreshNode@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CDMClientConfigRefreshNode>::CreateInstance(ATL::CComObject<CDMClientConfigRefreshNode> * *)
0x180031e42  mov     esi, eax
0x180031e44  test    eax, eax
0x180031e46  js      short loc_180031EA5
0x180031e48  mov     rbx, [rbp+var_38]
0x180031e4c  test    rbx, rbx
0x180031e4f  jnz     short loc_180031E63
0x180031e51  mov     esi, 8007000Eh
0x180031e56  jmp     short loc_180031EA5
0x180031e58  cmp     esi, edx
0x180031e5a  jnz     short loc_180031E39
0x180031e5c  mov     esi, 86000002h
0x180031e61  jmp     short loc_180031EA5
0x180031e63  mov     rax, [rbx]
0x180031e66  mov     r9, r13
0x180031e69  mov     r8, r14
0x180031e6c  mov     rdx, r12
0x180031e6f  mov     rcx, rbx
0x180031e72  mov     rax, [rax+88h]
0x180031e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031e7e  mov     esi, eax
0x180031e80  test    eax, eax
0x180031e82  js      short loc_180031EA5
0x180031e84  mov     rax, [rbx]
0x180031e87  mov     rcx, rbx
0x180031e8a  mov     rax, [rax+8]
0x180031e8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031e93  mov     [rbx+80h], r12
0x180031e9a  mov     [rbp+var_38], 0
0x180031ea2  mov     [r15], rbx
0x180031ea5  lea     rcx, [rbp+var_40]
0x180031ea9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180031eae  nop
0x180031eaf  mov     rcx, rdi; bstrString
0x180031eb2  call    cs:__imp_SysFreeString
0x180031eb9  nop     dword ptr [rax+rax+00h]
0x180031ebe  nop
0x180031ebf  lea     rcx, [rbp+var_38]
0x180031ec3  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x180031ec8  mov     eax, esi
0x180031eca  jmp     short loc_180031EF3
0x180031ecc  lea     rcx, [rbp+var_40]
0x180031ed0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180031ed5  nop
0x180031ed6  xor     ecx, ecx; bstrString
0x180031ed8  call    cs:__imp_SysFreeString
0x180031edf  nop     dword ptr [rax+rax+00h]
0x180031ee4  nop
0x180031ee5  lea     rcx, [rbp+var_38]
0x180031ee9  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x180031eee  mov     eax, 80070057h
0x180031ef3  add     rsp, 78h
0x180031ef7  pop     r15
0x180031ef9  pop     r14
0x180031efb  pop     r13
0x180031efd  pop     r12
0x180031eff  pop     rdi
0x180031f00  pop     rsi
0x180031f01  pop     rbx
0x180031f02  pop     rbp
0x180031f03  retn
```
