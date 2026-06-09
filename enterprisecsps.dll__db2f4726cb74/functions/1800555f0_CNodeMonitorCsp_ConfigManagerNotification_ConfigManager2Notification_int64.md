# CNodeMonitorCsp::ConfigManagerNotification(ConfigManager2Notification,__int64)

- ea: `0x1800555f0`
- end: `0x180055b1a`
- name: `?ConfigManagerNotification@CNodeMonitorCsp@@UEAAJW4ConfigManager2Notification@@_J@Z`
- size: `1322`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180008de0`
- `0x180009cc4`
- `0x18000caf4`
- `0x18000d4d4`
- `0x18000db4c`
- `0x180025a78`
- `0x180025a9c`
- `0x180025d20`
- `0x180041f2c`
- `0x1800552dc`
- `0x180055358`
- `0x1800553cc`
- `0x18005558c`
- `0x1800555f0`
- `0x180055e74`
- `0x180056448`
- `0x180056580`
- `0x180056ddc`
- `0x180056e10`
- `0x180107010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180055865`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180055894`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180055865`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180055894`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800558cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800558cd`
- `OLEAUT32!__imp_SysAllocString` at `0x18005571f`
- `OLEAUT32!__imp_SysAllocString` at `0x18005571f`
- `OLEAUT32!__imp_VariantInit` at `0x180055700`
- `OLEAUT32!__imp_VariantInit` at `0x1800557cb`
- `OLEAUT32!__imp_VariantInit` at `0x180055a0b`
- `OLEAUT32!__imp_VariantInit` at `0x180055700`
- `OLEAUT32!__imp_VariantInit` at `0x1800557cb`
- `OLEAUT32!__imp_VariantInit` at `0x180055a0b`
- `OLEAUT32!__imp_VariantClear` at `0x18005573a`
- `OLEAUT32!__imp_VariantClear` at `0x18005599e`
- `OLEAUT32!__imp_VariantClear` at `0x180055a7b`
- `OLEAUT32!__imp_VariantClear` at `0x180055a8c`
- `OLEAUT32!__imp_VariantClear` at `0x180055abc`
- `OLEAUT32!__imp_VariantClear` at `0x180055acd`
- `OLEAUT32!__imp_VariantClear` at `0x18005573a`
- `OLEAUT32!__imp_VariantClear` at `0x18005599e`
- `OLEAUT32!__imp_VariantClear` at `0x180055a7b`
- `OLEAUT32!__imp_VariantClear` at `0x180055a8c`
- `OLEAUT32!__imp_VariantClear` at `0x180055abc`
- `OLEAUT32!__imp_VariantClear` at `0x180055acd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18005594c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18005594c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800558b9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800558b9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800556df`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800556df`

## string_xrefs

- `0x18005562c`: `ConfigManagerNotificationActivity`
- `0x1800556ad`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodemoncsp.cpp`
- `0x18005578e`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodemoncsp.cpp`
- `0x180055928`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodemoncsp.cpp`
- `0x180055968`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodemoncsp.cpp`
- `0x1800559c6`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodemoncsp.cpp`
- `0x180055a62`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodemoncsp.cpp`
- `0x18005575d`: `pdcustomtaskname`
- `0x180055712`: `configmanager2_nodecache`
- `0x180055905`: `%sSoftware\Microsoft\Provisioning\NodeCache\CSP\%s`

## pseudocode

```c
__int64 __fastcall CNodeMonitorCsp::ConfigManagerNotification(__int64 a1, int a2, __int64 a3)
{
  __int64 **v5; // r15
  unsigned int v6; // edi
  __int64 v7; // rdx
  unsigned __int64 v8; // r9
  HRESULT Instance; // eax
  __int64 *v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  PSID *i; // r14
  PSID v14; // r12
  __int64 v15; // rbx
  int v16; // eax
  __int64 *v17; // rcx
  __int64 v18; // rax
  int v19; // eax
  const WCHAR *bstrVal; // rbx
  const unsigned __int16 *v21; // rax
  int v22; // eax
  unsigned int v23; // eax
  __int64 v24; // rdx
  unsigned __int64 v25; // r9
  VARIANTARG *v26; // rcx
  __int64 *v27; // rcx
  __int64 v28; // rax
  __int64 (__fastcall *v29)(__int64 *, const wchar_t *, VARIANTARG *); // rax
  int v30; // eax
  int ppv; // [rsp+20h] [rbp-E0h]
  __int64 v33; // [rsp+30h] [rbp-D0h] BYREF
  PSID Sid; // [rsp+38h] [rbp-C8h] BYREF
  VARIANTARG v35; // [rsp+40h] [rbp-C0h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG v37; // [rsp+78h] [rbp-88h] BYREF
  VARIANTARG v38; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v39[42]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR SubKey[264]; // [rsp+200h] [rbp+100h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+468h] [rbp+368h]

  if ( a2 == 4 )
  {
    wil::ActivityBase<NodeCacheProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NodeCacheProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v39);
    v39[0] = &NodeMonCspProvider::ConfigManagerNotificationActivity::`vftable';
    NodeMonCspProvider::ConfigManagerNotificationActivity::StartActivity((NodeMonCspProvider::ConfigManagerNotificationActivity *)v39);
    v5 = (__int64 **)(a1 + 80);
    if ( *(_QWORD *)(a1 + 80) )
    {
      v6 = -2147467259;
      v7 = 248;
LABEL_8:
      v8 = v6;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodemoncsp.cpp",
        (const char *)v8,
        ppv);
LABEL_44:
      NodeMonCspProvider::ConfigManagerNotificationActivity::~ConfigManagerNotificationActivity((NodeMonCspProvider::ConfigManagerNotificationActivity *)v39);
      return v6;
    }
    if ( *(_QWORD *)(a1 + 72) != a3 )
    {
      v33 = a3;
      Microsoft::WRL::ComPtr<IConfigNode>::InternalAddRef(&v33);
      v33 = *(_QWORD *)(a1 + 72);
      *(_QWORD *)(a1 + 72) = a3;
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v33);
    }
    if ( !*(_QWORD *)(a1 + 72) )
    {
      v6 = -2147024809;
      v7 = 252;
      goto LABEL_8;
    }
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(a1 + 80);
    Instance = CoCreateInstance(
                 &GUID_66d0db14_5638_475f_a386_629522d8c461,
                 0,
                 1u,
                 &GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0,
                 (LPVOID *)(a1 + 80));
    v6 = Instance;
    if ( Instance < 0 )
    {
      v8 = (unsigned int)Instance;
      v7 = 255;
      goto LABEL_9;
    }
    VariantInit(&pvarg);
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)SysAllocString(L"configmanager2_nodecache");
    if ( !pvarg.llVal )
    {
      VariantClear(&pvarg);
      v6 = -2147024882;
      goto LABEL_44;
    }
    v10 = *v5;
    v11 = **v5;
    v35 = pvarg;
    v12 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v11 + 104))(
            v10,
            L"pdcustomtaskname",
            &v35);
    v6 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10B,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodemoncsp.cpp",
        (const char *)(unsigned int)v12,
        ppv);
LABEL_43:
      VariantClear(&pvarg);
      goto LABEL_44;
    }
    for ( i = (PSID *)&g_omaDmSessionVariableNames; i != (PSID *)&dword_180155958; ++i )
    {
      Sid = *i;
      v14 = Sid;
      VariantInit(&v35);
      wil::make_bstr_nothrow(&v33, v14);
      v15 = v33;
      if ( !v33 )
      {
        v6 = -2147024882;
        v24 = 274;
        goto LABEL_35;
      }
      v16 = (*(__int64 (__fastcall **)(_QWORD, __int64, VARIANTARG *))(**(_QWORD **)(a1 + 72) + 32LL))(
              *(_QWORD *)(a1 + 72),
              v33,
              &v35);
      v6 = v16;
      if ( v16 < 0 )
      {
        if ( v16 != -2147023728 )
        {
          v25 = (unsigned int)v16;
          v24 = 321;
LABEL_36:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v24,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodemoncsp.cpp",
            (const char *)v25,
            ppv);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
          v26 = &v35;
LABEL_42:
          VariantClear(v26);
          goto LABEL_43;
        }
      }
      else
      {
        v17 = *v5;
        v18 = **v5;
        v38 = v35;
        v19 = (*(__int64 (__fastcall **)(__int64 *, __int64, VARIANTARG *))(v18 + 104))(v17, v15, &v38);
        v6 = v19;
        if ( v19 < 0 )
        {
          v25 = (unsigned int)v19;
          v24 = 280;
          goto LABEL_36;
        }
        NodeMonCspProvider::ConfigManagerNotificationActivity::SessionVariableSet<unsigned short const * &,unsigned short * &>(
          v39,
          &Sid,
          &v35.decVal.Lo32);
        if ( !(unsigned int)_o__wcsicmp(v14, L"OMADM::ServerID") )
        {
          if ( v35.vt != 8 )
          {
            v6 = -2046820351;
            v24 = 287;
LABEL_35:
            v25 = v6;
            goto LABEL_36;
          }
          bstrVal = v35.bstrVal;
          if ( (unsigned int)_o__wcsicmp(L"Device", v35.llVal) )
          {
            Sid = 0;
            if ( !ConvertStringSidToSidW(bstrVal, &Sid) && GetLastError() == 1337 )
            {
              memset_0(SubKey, 0, 0x208u);
              v21 = DMGetNonVolatileRegPrefix();
              ppv = (int)bstrVal;
              v22 = StringCchPrintfW(SubKey, 0x104u, L"%sSoftware\\Microsoft\\Provisioning\\NodeCache\\CSP\\%s", v21);
              if ( v22 >= 0 )
              {
                v23 = RegDeleteTreeW(HKEY_LOCAL_MACHINE, SubKey);
                if ( v23 != 2 )
                {
                  if ( v23 )
                    wil::details::in1diag3::_Log_Win32(
                      retaddr,
                      (void *)0x134,
                      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodemoncsp.cpp",
                      (const char *)v23,
                      (unsigned int)bstrVal);
                }
              }
              else
              {
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x12E,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodemoncsp.cpp",
                  (const char *)(unsigned int)v22,
                  (int)bstrVal);
              }
            }
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
          }
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
      VariantClear(&v35);
    }
    VariantInit(&v37);
    v27 = *v5;
    v37.lVal = 0;
    v37.vt = 19;
    v28 = *v27;
    v38.pRecInfo = v37.pRecInfo;
    v29 = *(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v28 + 104);
    *(_OWORD *)&v38.vt = *(_OWORD *)&v37.vt;
    v30 = v29(v27, L"OMADM::TelemetryLevel", &v38);
    v6 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14B,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodemoncsp.cpp",
        (const char *)(unsigned int)v30,
        ppv);
      v26 = &v37;
      goto LABEL_42;
    }
    NodeMonCspProvider::ConfigManagerNotificationActivity::SessionVariableSet<unsigned short const (&)[22],unsigned short const (&)[2]>(v39);
    wil::ActivityBase<NodeCacheProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v39);
    VariantClear(&v37);
    VariantClear(&pvarg);
    NodeMonCspProvider::ConfigManagerNotificationActivity::~ConfigManagerNotificationActivity((NodeMonCspProvider::ConfigManagerNotificationActivity *)v39);
  }
  else if ( !a2 && a3 )
  {
    *(_DWORD *)(a1 + 68) = *(_DWORD *)(a3 + 4);
  }
  return 0;
}

```

## disassembly

```asm
0x1800555f0  push    rbp
0x1800555f2  push    rbx
0x1800555f3  push    rsi
0x1800555f4  push    rdi
0x1800555f5  push    r12
0x1800555f7  push    r13
0x1800555f9  push    r14
0x1800555fb  push    r15
0x1800555fd  lea     rbp, [rsp-328h]
0x180055605  sub     rsp, 428h
0x18005560c  mov     rax, cs:__security_cookie
0x180055613  xor     rax, rsp
0x180055616  mov     [rbp+360h+var_50], rax
0x18005561d  mov     rbx, r8
0x180055620  mov     rsi, rcx
0x180055623  cmp     edx, 4
0x180055626  jnz     loc_180055AE4
0x18005562c  lea     rdx, aConfigmanagern; "ConfigManagerNotificationActivity"
0x180055633  lea     rcx, [rbp+360h+var_3B0]; struct wil::details::IFailureCallback *
0x180055637  call    ??0?$ActivityBase@VNodeCacheProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<NodeCacheProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NodeCacheProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18005563c  lea     rax, ??_7ConfigManagerNotificationActivity@NodeMonCspProvider@@6B@; const NodeMonCspProvider::ConfigManagerNotificationActivity::`vftable'
0x180055643  lea     rcx, [rbp+360h+var_3B0]; this
0x180055647  mov     [rbp+360h+var_3B0], rax
0x18005564b  call    ?StartActivity@ConfigManagerNotificationActivity@NodeMonCspProvider@@QEAAXXZ; NodeMonCspProvider::ConfigManagerNotificationActivity::StartActivity(void)
0x180055650  lea     r15, [rsi+50h]
0x180055654  cmp     qword ptr [r15], 0
0x180055658  jz      short loc_180055666
0x18005565a  mov     edi, 80004005h
0x18005565f  mov     edx, 0F8h
0x180055664  jmp     short loc_1800556A3
0x180055666  cmp     [rsi+48h], rbx
0x18005566a  jz      short loc_180055692
0x18005566c  lea     rcx, [rsp+460h+var_430]
0x180055671  mov     [rsp+460h+var_430], rbx
0x180055676  call    ?InternalAddRef@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IConfigNode>::InternalAddRef(void)
0x18005567b  mov     rax, [rsi+48h]
0x18005567f  lea     rcx, [rsp+460h+var_430]
0x180055684  mov     [rsp+460h+var_430], rax
0x180055689  mov     [rsi+48h], rbx
0x18005568d  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180055692  cmp     qword ptr [rsi+48h], 0
0x180055697  jnz     short loc_1800556BE
0x180055699  mov     edi, 80070057h
0x18005569e  mov     edx, 0FCh; void *
0x1800556a3  mov     r9d, edi; char *
0x1800556a6  mov     rcx, [rbp+368h]; this
0x1800556ad  lea     r8, aOnecoreuapAdmi_73; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800556b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800556b9  jmp     loc_180055A98
0x1800556be  mov     rcx, r15
0x1800556c1  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800556c6  xor     edx, edx; pUnkOuter
0x1800556c8  mov     qword ptr [rsp+460h+ppv], r15; int
0x1800556cd  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x1800556d4  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x1800556db  lea     r8d, [rdx+1]; dwClsContext
0x1800556df  call    cs:__imp_CoCreateInstance
0x1800556e6  nop     dword ptr [rax+rax+00h]
0x1800556eb  mov     edi, eax
0x1800556ed  test    eax, eax
0x1800556ef  jns     short loc_1800556FB
0x1800556f1  mov     r9d, eax
0x1800556f4  mov     edx, 0FFh
0x1800556f9  jmp     short loc_1800556A6
0x1800556fb  lea     rcx, [rsp+460h+pvarg]; pvarg
0x180055700  call    cs:__imp_VariantInit
0x180055707  nop     dword ptr [rax+rax+00h]
0x18005570c  mov     r13d, 8
0x180055712  lea     rcx, aConfigmanager2; "configmanager2_nodecache"
0x180055719  mov     word ptr [rsp+460h+pvarg], r13w
0x18005571f  call    cs:__imp_SysAllocString
0x180055726  nop     dword ptr [rax+rax+00h]
0x18005572b  mov     qword ptr [rsp+460h+pvarg+8], rax
0x180055730  test    rax, rax
0x180055733  jnz     short loc_180055750
0x180055735  lea     rcx, [rsp+460h+pvarg]; pvarg
0x18005573a  call    cs:__imp_VariantClear
0x180055741  nop     dword ptr [rax+rax+00h]
0x180055746  mov     edi, 8007000Eh
0x18005574b  jmp     loc_180055A98
0x180055750  mov     rcx, [r15]
0x180055753  lea     r8, [rsp+460h+var_420]
0x180055758  movups  xmm0, xmmword ptr [rsp+460h+pvarg]
0x18005575d  lea     rdx, aPdcustomtaskna; "pdcustomtaskname"
0x180055764  movsd   xmm1, qword ptr [rsp+460h+pvarg+10h]
0x18005576a  mov     rax, [rcx]
0x18005576d  movaps  xmmword ptr [rsp+460h+var_420], xmm0
0x180055772  movsd   qword ptr [rsp+460h+var_420+10h], xmm1
0x180055778  mov     rax, [rax+68h]
0x18005577c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055781  mov     edi, eax
0x180055783  test    eax, eax
0x180055785  jns     short loc_1800557A7
0x180055787  mov     rcx, [rbp+368h]; this
0x18005578e  lea     r8, aOnecoreuapAdmi_73; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180055795  mov     r9d, eax; char *
0x180055798  mov     edx, 10Bh; void *
0x18005579d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800557a2  jmp     loc_180055A87
0x1800557a7  lea     r14, ?g_omaDmSessionVariableNames@@3PAPEBGA; ushort const * near * g_omaDmSessionVariableNames
0x1800557ae  lea     rax, dword_180155958
0x1800557b5  cmp     r14, rax
0x1800557b8  jz      loc_180055A06
0x1800557be  mov     r12, [r14]
0x1800557c1  lea     rcx, [rsp+460h+var_420]; pvarg
0x1800557c6  mov     [rsp+460h+Sid], r12
0x1800557cb  call    cs:__imp_VariantInit
0x1800557d2  nop     dword ptr [rax+rax+00h]
0x1800557d7  mov     rdx, r12
0x1800557da  lea     rcx, [rsp+460h+var_430]
0x1800557df  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x1800557e4  mov     rbx, [rsp+460h+var_430]
0x1800557e9  test    rbx, rbx
0x1800557ec  jz      loc_1800559FA
0x1800557f2  mov     rcx, [rsi+48h]
0x1800557f6  lea     r8, [rsp+460h+var_420]
0x1800557fb  mov     rdx, rbx
0x1800557fe  mov     rax, [rcx]
0x180055801  mov     rax, [rax+20h]
0x180055805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005580a  mov     edi, eax
0x18005580c  test    eax, eax
0x18005580e  js      loc_180055988
0x180055814  mov     rcx, [r15]
0x180055817  lea     r8, [rbp+360h+var_3D0]
0x18005581b  movups  xmm0, xmmword ptr [rsp+460h+var_420]
0x180055820  mov     rdx, rbx
0x180055823  movsd   xmm1, qword ptr [rsp+460h+var_420+10h]
0x180055829  mov     rax, [rcx]
0x18005582c  movaps  [rbp+360h+var_3D0], xmm0
0x180055830  movsd   [rbp+360h+var_3C0], xmm1
0x180055835  mov     rax, [rax+68h]
0x180055839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005583e  mov     edi, eax
0x180055840  test    eax, eax
0x180055842  js      loc_1800559E6
0x180055848  lea     r8, [rsp+460h+var_420+8]
0x18005584d  lea     rdx, [rsp+460h+Sid]
0x180055852  lea     rcx, [rbp+360h+var_3B0]
0x180055856  call    ??$SessionVariableSet@AEAPEBGAEAPEAG@ConfigManagerNotificationActivity@NodeMonCspProvider@@QEAAXAEAPEBGAEAPEAG@Z; NodeMonCspProvider::ConfigManagerNotificationActivity::SessionVariableSet<ushort const * &,ushort * &>(ushort const * &,ushort * &)
0x18005585b  lea     rdx, aOmadmServerid; "OMADM::ServerID"
0x180055862  mov     rcx, r12
0x180055865  call    cs:__imp__o__wcsicmp
0x18005586c  nop     dword ptr [rax+rax+00h]
0x180055871  test    eax, eax
0x180055873  jnz     loc_18005598F
0x180055879  cmp     r13w, word ptr [rsp+460h+var_420]
0x18005587f  jnz     loc_1800559B2
0x180055885  mov     rbx, qword ptr [rsp+460h+var_420+8]
0x18005588a  lea     rcx, aDevice_1; "Device"
0x180055891  mov     rdx, rbx
0x180055894  call    cs:__imp__o__wcsicmp
0x18005589b  nop     dword ptr [rax+rax+00h]
0x1800558a0  test    eax, eax
0x1800558a2  jz      loc_18005598F
0x1800558a8  lea     rdx, [rsp+460h+Sid]; Sid
0x1800558ad  mov     [rsp+460h+Sid], 0
0x1800558b6  mov     rcx, rbx; StringSid
0x1800558b9  call    cs:__imp_ConvertStringSidToSidW
0x1800558c0  nop     dword ptr [rax+rax+00h]
0x1800558c5  test    eax, eax
0x1800558c7  jnz     loc_18005597C
0x1800558cd  call    cs:__imp_GetLastError
0x1800558d4  nop     dword ptr [rax+rax+00h]
0x1800558d9  cmp     eax, 539h
0x1800558de  jnz     loc_18005597C
0x1800558e4  xor     edx, edx; Val
0x1800558e6  lea     rcx, [rbp+360h+SubKey]; void *
0x1800558ed  mov     r8d, 208h; Size
0x1800558f3  call    memset_0
0x1800558f8  call    ?DMGetNonVolatileRegPrefix@@YAPEBGXZ; DMGetNonVolatileRegPrefix(void)
0x1800558fd  mov     r9, rax
0x180055900  mov     qword ptr [rsp+460h+ppv], rbx; unsigned int
0x180055905  lea     r8, aSsoftwareMicro_0; "%sSoftware\\Microsoft\\Provisioning\\No"...
0x18005590c  mov     edx, 104h; unsigned __int64
0x180055911  lea     rcx, [rbp+360h+SubKey]; unsigned __int16 *
0x180055918  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005591d  test    eax, eax
0x18005591f  jns     short loc_18005593E
0x180055921  mov     rcx, [rbp+368h]; this
0x180055928  lea     r8, aOnecoreuapAdmi_73; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18005592f  mov     r9d, eax; char *
0x180055932  mov     edx, 12Eh; void *
0x180055937  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005593c  jmp     short loc_18005597C
0x18005593e  lea     rdx, [rbp+360h+SubKey]; lpSubKey
0x180055945  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005594c  call    cs:__imp_RegDeleteTreeW
0x180055953  nop     dword ptr [rax+rax+00h]
0x180055958  cmp     eax, 2
0x18005595b  jz      short loc_18005597C
0x18005595d  test    eax, eax
0x18005595f  jz      short loc_18005597C
0x180055961  mov     rcx, [rbp+368h]; this
0x180055968  lea     r8, aOnecoreuapAdmi_73; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18005596f  mov     r9d, eax; char *
0x180055972  mov     edx, 134h; void *
0x180055977  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18005597c  lea     rcx, [rsp+460h+Sid]
0x180055981  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180055986  jmp     short loc_18005598F
0x180055988  cmp     eax, 80070490h
0x18005598d  jnz     short loc_1800559F0
0x18005598f  lea     rcx, [rsp+460h+var_430]
0x180055994  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180055999  lea     rcx, [rsp+460h+var_420]; pvarg
0x18005599e  call    cs:__imp_VariantClear
0x1800559a5  nop     dword ptr [rax+rax+00h]
0x1800559aa  add     r14, r13
0x1800559ad  jmp     loc_1800557AE
0x1800559b2  mov     edi, 86000001h
0x1800559b7  mov     edx, 11Fh; void *
0x1800559bc  mov     r9d, edi; char *
0x1800559bf  mov     rcx, [rbp+368h]; this
0x1800559c6  lea     r8, aOnecoreuapAdmi_73; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800559cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800559d2  lea     rcx, [rsp+460h+var_430]
0x1800559d7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800559dc  lea     rcx, [rsp+460h+var_420]
0x1800559e1  jmp     loc_180055A7B
0x1800559e6  mov     r9d, eax
0x1800559e9  mov     edx, 118h
0x1800559ee  jmp     short loc_1800559BF
0x1800559f0  mov     r9d, eax
0x1800559f3  mov     edx, 141h
0x1800559f8  jmp     short loc_1800559BF
0x1800559fa  mov     edi, 8007000Eh
0x1800559ff  mov     edx, 112h
0x180055a04  jmp     short loc_1800559BC
0x180055a06  lea     rcx, [rsp+460h+var_3E8]; pvarg
0x180055a0b  call    cs:__imp_VariantInit
0x180055a12  nop     dword ptr [rax+rax+00h]
0x180055a17  mov     rcx, [r15]
0x180055a1a  lea     r8, [rbp+360h+var_3D0]
0x180055a1e  movsd   xmm1, qword ptr [rbp+360h+var_3E8+10h]
0x180055a23  lea     rdx, aOmadmTelemetry; "OMADM::TelemetryLevel"
0x180055a2a  mov     dword ptr [rbp+360h+var_3E8+8], 0
0x180055a31  mov     eax, 13h
0x180055a36  mov     word ptr [rsp+460h+var_3E8], ax
0x180055a3b  mov     rax, [rcx]
0x180055a3e  movups  xmm0, xmmword ptr [rsp+460h+var_3E8]
0x180055a43  movsd   [rbp+360h+var_3C0], xmm1
0x180055a48  mov     rax, [rax+68h]
0x180055a4c  movaps  [rbp+360h+var_3D0], xmm0
0x180055a50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055a55  mov     edi, eax
0x180055a57  test    eax, eax
0x180055a59  jns     short loc_180055AA5
0x180055a5b  mov     rcx, [rbp+368h]; this
0x180055a62  lea     r8, aOnecoreuapAdmi_73; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180055a69  mov     r9d, eax; char *
0x180055a6c  mov     edx, 14Bh; void *
0x180055a71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055a76  lea     rcx, [rsp+460h+var_3E8]; pvarg
0x180055a7b  call    cs:__imp_VariantClear
0x180055a82  nop     dword ptr [rax+rax+00h]
0x180055a87  lea     rcx, [rsp+460h+pvarg]; pvarg
0x180055a8c  call    cs:__imp_VariantClear
0x180055a93  nop     dword ptr [rax+rax+00h]
0x180055a98  lea     rcx, [rbp+360h+var_3B0]; this
0x180055a9c  call    ??1ConfigManagerNotificationActivity@NodeMonCspProvider@@QEAA@XZ; NodeMonCspProvider::ConfigManagerNotificationActivity::~ConfigManagerNotificationActivity(void)
0x180055aa1  mov     eax, edi
0x180055aa3  jmp     short loc_180055AF6
0x180055aa5  lea     rcx, [rbp+360h+var_3B0]
0x180055aa9  call    ??$SessionVariableSet@AEAY0BG@$$CBGAEAY01$$CBG@ConfigManagerNotificationActivity@NodeMonCspProvider@@QEAAXAEAY0BG@$$CBGAEAY01$$CBG@Z; NodeMonCspProvider::ConfigManagerNotificationActivity::SessionVariableSet<ushort const (&)[22],ushort const (&)[2]>(ushort const (&)[22],ushort const (&)[2])
0x180055aae  lea     rcx, [rbp+360h+var_3B0]
0x180055ab2  call    ?Stop@?$ActivityBase@VNodeCacheProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<NodeCacheProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180055ab7  lea     rcx, [rsp+460h+var_3E8]; pvarg
0x180055abc  call    cs:__imp_VariantClear
0x180055ac3  nop     dword ptr [rax+rax+00h]
0x180055ac8  lea     rcx, [rsp+460h+pvarg]; pvarg
0x180055acd  call    cs:__imp_VariantClear
0x180055ad4  nop     dword ptr [rax+rax+00h]
0x180055ad9  lea     rcx, [rbp+360h+var_3B0]; this
0x180055add  call    ??1ConfigManagerNotificationActivity@NodeMonCspProvider@@QEAA@XZ; NodeMonCspProvider::ConfigManagerNotificationActivity::~ConfigManagerNotificationActivity(void)
0x180055ae2  jmp     short loc_180055AF4
0x180055ae4  test    edx, edx
0x180055ae6  jnz     short loc_180055AF4
0x180055ae8  test    rbx, rbx
0x180055aeb  jz      short loc_180055AF4
0x180055aed  mov     eax, [r8+4]
0x180055af1  mov     [rcx+44h], eax
0x180055af4  xor     eax, eax
0x180055af6  mov     rcx, [rbp+360h+var_50]
0x180055afd  xor     rcx, rsp; StackCookie
0x180055b00  call    __security_check_cookie
0x180055b05  add     rsp, 428h
0x180055b0c  pop     r15
0x180055b0e  pop     r14
0x180055b10  pop     r13
0x180055b12  pop     r12
0x180055b14  pop     rdi
0x180055b15  pop     rsi
0x180055b16  pop     rbx
0x180055b17  pop     rbp
0x180055b18  retn
```
