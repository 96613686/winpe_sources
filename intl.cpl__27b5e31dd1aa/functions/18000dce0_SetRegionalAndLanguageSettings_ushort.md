# SetRegionalAndLanguageSettings(ushort *)

- ea: `0x18000dce0`
- end: `0x18000e589`
- name: `?SetRegionalAndLanguageSettings@@YAJPEAG@Z`
- size: `2217`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180014c90`

## callees

- `0x18000a860`
- `0x18000aa9c`
- `0x18000ac78`
- `0x18000b2a4`
- `0x18000b6ec`
- `0x18000ba98`
- `0x18000c870`
- `0x18000ce98`
- `0x18000d1bc`
- `0x18000d5d0`
- `0x18000d974`
- `0x18000dce0`
- `0x18000e730`
- `0x18000e844`
- `0x18000f034`
- `0x18000f464`
- `0x18000f4d4`
- `0x1800261f0`
- `0x180026234`
- `0x180026304`
- `0x180026994`
- `0x18002a150`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeResource` at `0x18000dff9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeResource` at `0x18000dff9`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18000df61`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18000df61`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000df2e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000df2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df3c`
- `OLEAUT32!__imp_SysAllocString` at `0x18000df9a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e0a7`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e279`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e2c5`
- `OLEAUT32!__imp_SysAllocString` at `0x18000df9a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e0a7`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e279`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e2c5`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e4f7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e505`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e4f7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e505`
- `OLEAUT32!__imp_VariantInit` at `0x18000dd65`
- `OLEAUT32!__imp_VariantInit` at `0x18000dd6f`
- `OLEAUT32!__imp_VariantInit` at `0x18000dd79`
- `OLEAUT32!__imp_VariantInit` at `0x18000dd83`
- `OLEAUT32!__imp_VariantInit` at `0x18000dd65`
- `OLEAUT32!__imp_VariantInit` at `0x18000dd6f`
- `OLEAUT32!__imp_VariantInit` at `0x18000dd79`
- `OLEAUT32!__imp_VariantInit` at `0x18000dd83`
- `OLEAUT32!__imp_VariantClear` at `0x18000e50f`
- `OLEAUT32!__imp_VariantClear` at `0x18000e519`
- `OLEAUT32!__imp_VariantClear` at `0x18000e523`
- `OLEAUT32!__imp_VariantClear` at `0x18000e52d`
- `OLEAUT32!__imp_VariantClear` at `0x18000e50f`
- `OLEAUT32!__imp_VariantClear` at `0x18000e519`
- `OLEAUT32!__imp_VariantClear` at `0x18000e523`
- `OLEAUT32!__imp_VariantClear` at `0x18000e52d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000e533`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000e533`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000de74`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000e033`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000e116`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000de74`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000e033`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000e116`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x18000df09`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x18000df09`
- `ole32!CoInitialize` at `0x18000de32`
- `ole32!CoInitialize` at `0x18000de32`

## string_xrefs

- `0x18000e2be`: `xmlns:gs='urn:longhornGlobalizationUnattend'`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SetRegionalAndLanguageSettings(unsigned __int16 *a1)
{
  OLECHAR *v2; // r15
  OLECHAR *v3; // r12
  unsigned int v4; // r8d
  __int64 v5; // r8
  unsigned __int16 *v6; // rax
  unsigned int Instance; // ebx
  unsigned __int64 v8; // rsi
  __int64 v9; // r9
  __int64 v10; // rdx
  HRSRC ResourceW; // rax
  HGLOBAL Resource; // rax
  void *v13; // rdi
  signed int LastError; // eax
  const OLECHAR *v15; // rax
  const OLECHAR *v16; // rcx
  const OLECHAR ***v17; // rax
  const OLECHAR *v18; // rcx
  HRESULT (__stdcall *setProperty)(IXMLDOMDocument2 *, BSTR, VARIANT); // rbx
  __int128 v20; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  _bstr_t *v22; // rax
  __int64 v23; // rdx
  int UserList; // eax
  wil::details::in1diag3 *v25; // rcx
  __int64 v26; // rdx
  int v27; // eax
  __int64 v28; // rdx
  int ppv; // [rsp+28h] [rbp-E0h]
  struct IXMLDOMDocument2 *v31; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v32; // [rsp+40h] [rbp-C8h] BYREF
  LPVOID v33; // [rsp+48h] [rbp-C0h] BYREF
  LPVOID v34; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v35; // [rsp+58h] [rbp-B0h] BYREF
  LONGLONG v36; // [rsp+60h] [rbp-A8h] BYREF
  LONGLONG v37; // [rsp+68h] [rbp-A0h] BYREF
  VARIANTARG v38; // [rsp+78h] [rbp-90h] BYREF
  VARIANTARG v39; // [rsp+98h] [rbp-70h] BYREF
  VARIANTARG v40; // [rsp+B0h] [rbp-58h] BYREF
  VARIANTARG pvarg; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG v42; // [rsp+E0h] [rbp-28h] BYREF
  _QWORD v43[42]; // [rsp+F8h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C0h] [rbp+1B8h]

  v31 = 0;
  v33 = 0;
  v34 = 0;
  v2 = 0;
  v3 = 0;
  memset(&v42, 0, sizeof(v42));
  memset(&v40, 0, sizeof(v40));
  memset(&v39, 0, sizeof(v39));
  memset(&pvarg, 0, sizeof(pvarg));
  LOWORD(v32) = -1;
  VariantInit(&pvarg);
  VariantInit(&v39);
  VariantInit(&v42);
  VariantInit(&v40);
  wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v43,
    "SetRegionalAndLanguageSettings");
  v43[0] = &IntlCplTraceLoggingTelemetry::SetRegionalAndLanguageSettings::`vftable';
  IntlCplTraceLoggingTelemetry::SetRegionalAndLanguageSettings::StartActivity((IntlCplTraceLoggingTelemetry::SetRegionalAndLanguageSettings *)v43);
  if ( !a1 || !*a1 )
  {
    v10 = 2467;
    goto LABEL_85;
  }
  v5 = 260;
  v6 = a1;
  do
  {
    if ( !*v6 )
      break;
    ++v6;
    --v5;
  }
  while ( v5 );
  Instance = v5 == 0 ? 0x80070057 : 0;
  v8 = (260 - v5) & ((unsigned __int128)-(__int128)(unsigned __int64)v5 >> 64) & -(__int64)(v5 != 0);
  if ( !(unsigned int)CheckHR(Instance) )
  {
    v9 = Instance;
    v10 = 2475;
LABEL_86:
    wil::details::in1diag3::Log_Hr(retaddr, (void *)v10, v4, (const char *)v9, ppv);
    goto LABEL_87;
  }
  if ( v8 >= 0x104 )
  {
    v10 = 2482;
LABEL_85:
    v9 = 2147942487LL;
    Instance = -2147024809;
    goto LABEL_86;
  }
  Instance = CoInitialize(0);
  if ( !(unsigned int)CheckHR(Instance) )
  {
    v9 = Instance;
    v10 = 2490;
    goto LABEL_86;
  }
  Instance = CoCreateInstance(
               &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
               0,
               1u,
               &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
               &v33);
  if ( !(unsigned int)CheckHR(Instance) )
  {
    v9 = Instance;
    v10 = 2503;
    goto LABEL_86;
  }
  Instance = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v33 + 504LL))(v33, 0);
  if ( !(unsigned int)CheckHR(Instance) )
  {
    v9 = Instance;
    v10 = 2510;
    goto LABEL_86;
  }
  Instance = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v33 + 544LL))(v33, 0);
  if ( !(unsigned int)CheckHR(Instance) )
  {
    v9 = Instance;
    v10 = 2517;
    goto LABEL_86;
  }
  ResourceW = FindResourceW(hInstance, L"IDS_UNATTEND", L"SCHEMAS");
  if ( !ResourceW )
  {
    v10 = 2525;
    v9 = 2147500037LL;
    goto LABEL_86;
  }
  Resource = LoadResource(hInstance, ResourceW);
  v13 = Resource;
  if ( !Resource )
  {
    LastError = GetLastError();
    Instance = LastError;
    if ( LastError > 0 )
      Instance = (unsigned __int16)LastError | 0x80070000;
    v9 = Instance;
    v10 = 2534;
    goto LABEL_86;
  }
  v15 = (const OLECHAR *)LockResource(Resource);
  if ( !v15 )
  {
    v9 = 2147500037LL;
    Instance = -2147467259;
    v10 = 2543;
    goto LABEL_86;
  }
  if ( *v15 == 0xFFFE || (v16 = v15, *v15 == 0xFEFF) )
    v16 = v15 + 1;
  v2 = SysAllocString(v16);
  Instance = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int64 *))(*(_QWORD *)v33 + 520LL))(v33, v2, &v32);
  if ( !(unsigned int)CheckHR(Instance) )
  {
    v9 = Instance;
    v10 = 2559;
    goto LABEL_86;
  }
  if ( (_WORD)v32 != 0xFFFF )
  {
    v9 = 2147500037LL;
    Instance = -2147467259;
    v10 = 2567;
    goto LABEL_86;
  }
  if ( FreeResource(v13) )
  {
    v9 = 2147500037LL;
    Instance = -2147467259;
    v10 = 2575;
    goto LABEL_86;
  }
  Instance = CoCreateInstance(
               &GUID_88d96a07_f192_11d4_a65f_0040963251e5,
               0,
               1u,
               &GUID_373984c8_b845_449b_91e7_45ac83036ade,
               &v34);
  if ( !(unsigned int)CheckHR(Instance) )
  {
    v9 = Instance;
    v10 = 2588;
    goto LABEL_86;
  }
  v36 = 0;
  Instance = (**(__int64 (__fastcall ***)(LPVOID, GUID *, LONGLONG *))v33)(v33, &IID_IDispatch, &v36);
  if ( !(unsigned int)CheckHR(Instance) )
  {
    v9 = Instance;
    v10 = 2597;
    goto LABEL_86;
  }
  pvarg.llVal = v36;
  pvarg.vt = 9;
  v3 = SysAllocString(L"urn:longhornGlobalizationUnattend");
  v38 = pvarg;
  Instance = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, VARIANTARG *))(*(_QWORD *)v34 + 56LL))(v34, v3, &v38);
  if ( !(unsigned int)CheckHR(Instance) )
  {
    v9 = Instance;
    v10 = 2612;
    goto LABEL_86;
  }
  Instance = CoCreateInstance(
               &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
               0,
               1u,
               &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
               (LPVOID *)&v31);
  if ( !(unsigned int)CheckHR(Instance) || !v31 )
  {
    v9 = Instance;
    v10 = 2625;
    goto LABEL_86;
  }
  Instance = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, _QWORD))v31->lpVtbl->put_async)(v31, 0);
  if ( !(unsigned int)CheckHR(Instance) )
  {
    v9 = Instance;
    v10 = 2632;
    goto LABEL_86;
  }
  Instance = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, __int64))v31->lpVtbl->put_validateOnParse)(
               v31,
               0xFFFFFFFFLL);
  if ( !(unsigned int)CheckHR(Instance) )
  {
    v9 = Instance;
    v10 = 2639;
    goto LABEL_86;
  }
  Instance = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, __int64))v31->lpVtbl->put_resolveExternals)(
               v31,
               0xFFFFFFFFLL);
  if ( !(unsigned int)CheckHR(Instance) )
  {
    v9 = Instance;
    v10 = 2646;
    goto LABEL_86;
  }
  v37 = 0;
  Instance = (**(__int64 (__fastcall ***)(LPVOID, GUID *, LONGLONG *))v34)(v34, &IID_IXMLDOMSchemaCollection, &v37);
  if ( !(unsigned int)CheckHR(Instance) )
  {
    v9 = Instance;
    v10 = 2655;
    goto LABEL_86;
  }
  v39.llVal = v37;
  v39.vt = 9;
  v38 = v39;
  Instance = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, VARIANTARG *))v31->lpVtbl->putref_schemas)(v31, &v38);
  if ( !(unsigned int)CheckHR(Instance) )
  {
    v9 = Instance;
    v10 = 2667;
    goto LABEL_86;
  }
  v17 = (const OLECHAR ***)_bstr_t::_bstr_t((_bstr_t *)&v35, a1);
  if ( *v17 )
    v18 = **v17;
  else
    v18 = 0;
  v42.llVal = (LONGLONG)SysAllocString(v18);
  _bstr_t::_Free((_bstr_t *)&v35);
  v42.vt = 8;
  Instance = ParseAndValidateFile(v31, &v42);
  if ( !(unsigned int)CheckHR(Instance) )
  {
    v9 = Instance;
    v10 = 2684;
    goto LABEL_86;
  }
  v40.llVal = (LONGLONG)SysAllocString(L"xmlns:gs='urn:longhornGlobalizationUnattend'");
  v40.vt = 8;
  setProperty = v31->lpVtbl->setProperty;
  v20 = *(_OWORD *)&v40.vt;
  pRecInfo = v40.pRecInfo;
  v22 = _bstr_t::_bstr_t((_bstr_t *)&v35, L"SelectionNamespaces");
  if ( *(_QWORD *)v22 )
    v23 = **(_QWORD **)v22;
  else
    v23 = 0;
  *(_OWORD *)&v38.vt = v20;
  v38.pRecInfo = pRecInfo;
  Instance = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, __int64, VARIANTARG *))setProperty)(v31, v23, &v38);
  _bstr_t::_Free((_bstr_t *)&v35);
  if ( !(unsigned int)CheckHR(Instance) )
  {
    v9 = Instance;
    v10 = 2697;
    goto LABEL_86;
  }
  UserList = GetUserList(v31);
  Instance = UserList;
  v25 = retaddr;
  if ( UserList < 0 )
  {
    v26 = 2710;
LABEL_65:
    wil::details::in1diag3::_Log_Hr(
      v25,
      (void *)v26,
      (unsigned int)"shell\\osshell\\cpls\\intl\\cme.cpp",
      (const char *)(unsigned int)UserList,
      ppv);
    goto LABEL_87;
  }
  UserList = ChangeUserLocaleSection(v31);
  Instance = UserList;
  v25 = retaddr;
  if ( UserList < 0 )
  {
    v26 = 2715;
    goto LABEL_65;
  }
  UserList = ChangeLocationPreferences(v31);
  Instance = UserList;
  v25 = retaddr;
  if ( UserList < 0 )
  {
    v26 = 2720;
    goto LABEL_65;
  }
  UserList = ChangeInputPreferences(v31);
  Instance = UserList;
  v25 = retaddr;
  if ( UserList < 0 )
  {
    v26 = 2725;
    goto LABEL_65;
  }
  UserList = UpdateMUIPreferences(v31);
  Instance = UserList;
  v25 = retaddr;
  if ( UserList < 0 )
  {
    v26 = 2730;
    goto LABEL_65;
  }
  UserList = ChangeSystemLocale(v31);
  Instance = UserList;
  v25 = retaddr;
  if ( UserList < 0 )
  {
    v26 = 2737;
    goto LABEL_65;
  }
  v27 = gCopySettingsToDefaultUserAcct;
  if ( (gCopySettingsToSystemAcct || gCopySettingsToDefaultUserAcct) && g_bAdmin_Privileges )
  {
    if ( gCopySettingsToSystemAcct )
    {
      Intl_SaveSystemAcctSettings(HKEY_CURRENT_USER, 0, 1);
      Intl_SetUILanguageForSystemAccts(HKEY_CURRENT_USER, 0);
      v27 = gCopySettingsToDefaultUserAcct;
    }
    if ( v27 )
    {
      Intl_SaveDefaultUserSettings(HKEY_CURRENT_USER, 0, 1);
      Intl_SaveUISettingsToNtUserFile(HKEY_CURRENT_USER);
    }
  }
LABEL_87:
  if ( v33 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v33 + 16LL))(v33);
    v33 = 0;
  }
  if ( v34 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v34 + 16LL))(v34);
    v34 = 0;
  }
  if ( v31 )
  {
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v31->lpVtbl->Release)(v31);
    v31 = 0;
  }
  if ( v3 )
    SysFreeString(v3);
  if ( v2 )
    SysFreeString(v2);
  VariantClear(&v42);
  VariantClear(&v39);
  VariantClear(&v40);
  VariantClear(&pvarg);
  CoUninitialize();
  if ( (Instance & 0x80000000) == 0 )
    v28 = 0;
  else
    v28 = Instance;
  wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v43, v28);
  IntlCplTraceLoggingTelemetry::SetRegionalAndLanguageSettings::~SetRegionalAndLanguageSettings((IntlCplTraceLoggingTelemetry::SetRegionalAndLanguageSettings *)v43);
  return Instance;
}

```

## disassembly

```asm
0x18000dce0  mov     rax, rsp
0x18000dce3  push    rbp
0x18000dce4  push    rbx
0x18000dce5  push    rsi
0x18000dce6  push    rdi
0x18000dce7  push    r12
0x18000dce9  push    r13
0x18000dceb  push    r14
0x18000dced  push    r15
0x18000dcef  lea     rbp, [rax-1B8h]
0x18000dcf6  sub     rsp, 278h
0x18000dcfd  movaps  xmmword ptr [rax-58h], xmm6
0x18000dd01  movaps  xmmword ptr [rax-68h], xmm7
0x18000dd05  mov     rax, cs:__security_cookie
0x18000dd0c  xor     rax, rsp
0x18000dd0f  mov     [rbp+1B0h+var_70], rax
0x18000dd16  mov     r14, rcx
0x18000dd19  xor     r13d, r13d
0x18000dd1c  mov     [rsp+2B0h+var_280], r13
0x18000dd21  mov     [rsp+2B0h+var_270], r13
0x18000dd26  mov     [rsp+2B0h+var_268], r13
0x18000dd2b  mov     r15d, r13d
0x18000dd2e  mov     r12d, r13d
0x18000dd31  xorps   xmm0, xmm0
0x18000dd34  xor     eax, eax
0x18000dd36  movups  xmmword ptr [rbp+1B0h+var_1D8], xmm0
0x18000dd3a  mov     qword ptr [rbp+1B0h+var_1D8+10h], rax
0x18000dd3e  xorps   xmm1, xmm1
0x18000dd41  movups  xmmword ptr [rbp+1B0h+var_208], xmm1
0x18000dd45  mov     qword ptr [rbp+1B0h+var_208+10h], rax
0x18000dd49  movups  xmmword ptr [rbp+1B0h+var_220], xmm0
0x18000dd4d  mov     qword ptr [rbp+1B0h+var_220+10h], rax
0x18000dd51  movups  xmmword ptr [rbp+1B0h+pvarg], xmm1
0x18000dd55  mov     qword ptr [rbp+1B0h+pvarg+10h], rax
0x18000dd59  or      eax, 0FFFFFFFFh
0x18000dd5c  mov     word ptr [rsp+2B0h+var_278], ax
0x18000dd61  lea     rcx, [rbp+1B0h+pvarg]; pvarg
0x18000dd65  call    cs:__imp_VariantInit
0x18000dd6b  lea     rcx, [rbp+1B0h+var_220]; pvarg
0x18000dd6f  call    cs:__imp_VariantInit
0x18000dd75  lea     rcx, [rbp+1B0h+var_1D8]; pvarg
0x18000dd79  call    cs:__imp_VariantInit
0x18000dd7f  lea     rcx, [rbp+1B0h+var_208]; pvarg
0x18000dd83  call    cs:__imp_VariantInit
0x18000dd89  lea     rdx, aSetregionaland; "SetRegionalAndLanguageSettings"
0x18000dd90  lea     rcx, [rbp+1B0h+var_1C0]
0x18000dd94  call    ??0?$ActivityBase@VIntlCplTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000dd99  lea     rax, ??_7SetRegionalAndLanguageSettings@IntlCplTraceLoggingTelemetry@@6B@; const IntlCplTraceLoggingTelemetry::SetRegionalAndLanguageSettings::`vftable'
0x18000dda0  mov     [rbp+1B0h+var_1C0], rax
0x18000dda4  lea     rcx, [rbp+1B0h+var_1C0]; this
0x18000dda8  call    ?StartActivity@SetRegionalAndLanguageSettings@IntlCplTraceLoggingTelemetry@@QEAAXXZ; IntlCplTraceLoggingTelemetry::SetRegionalAndLanguageSettings::StartActivity(void)
0x18000ddad  nop
0x18000ddae  test    r14, r14
0x18000ddb1  jz      loc_18000E483
0x18000ddb7  cmp     [r14], r13w
0x18000ddbb  jz      loc_18000E483
0x18000ddc1  mov     ecx, 104h
0x18000ddc6  mov     r8d, ecx
0x18000ddc9  mov     rax, r14
0x18000ddcc  cmp     [rax], r13w
0x18000ddd0  jz      short loc_18000DDDC
0x18000ddd2  add     rax, 2
0x18000ddd6  sub     r8, 1
0x18000ddda  jnz     short loc_18000DDCC
0x18000dddc  mov     rax, r8
0x18000dddf  neg     rax
0x18000dde2  sbb     ebx, ebx
0x18000dde4  not     ebx
0x18000dde6  mov     edi, 80070057h
0x18000ddeb  and     ebx, edi
0x18000dded  mov     rax, r8
0x18000ddf0  sub     rcx, r8
0x18000ddf3  neg     rax
0x18000ddf6  sbb     rdx, rdx
0x18000ddf9  and     rdx, rcx
0x18000ddfc  neg     r8
0x18000ddff  sbb     rsi, rsi
0x18000de02  and     rsi, rdx
0x18000de05  mov     ecx, ebx; int
0x18000de07  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000de0c  test    eax, eax
0x18000de0e  jnz     short loc_18000DE1D
0x18000de10  mov     r9d, ebx
0x18000de13  mov     edx, 9ABh
0x18000de18  jmp     loc_18000E492
0x18000de1d  cmp     rsi, 104h
0x18000de24  jb      short loc_18000DE30
0x18000de26  mov     edx, 9B2h
0x18000de2b  jmp     loc_18000E48D
0x18000de30  xor     ecx, ecx; pvReserved
0x18000de32  call    cs:__imp_CoInitialize
0x18000de38  mov     ebx, eax
0x18000de3a  mov     ecx, eax; int
0x18000de3c  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000de41  test    eax, eax
0x18000de43  jnz     short loc_18000DE52
0x18000de45  mov     r9d, ebx
0x18000de48  mov     edx, 9BAh
0x18000de4d  jmp     loc_18000E492
0x18000de52  lea     rax, [rsp+2B0h+var_270]
0x18000de57  mov     qword ptr [rsp+2B0h+ppv], rax; ppv
0x18000de5c  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x18000de63  mov     esi, 1
0x18000de68  mov     r8d, esi; dwClsContext
0x18000de6b  xor     edx, edx; pUnkOuter
0x18000de6d  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x18000de74  call    cs:__imp_CoCreateInstance
0x18000de7a  mov     ebx, eax
0x18000de7c  mov     ecx, eax; int
0x18000de7e  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000de83  test    eax, eax
0x18000de85  jnz     short loc_18000DE94
0x18000de87  mov     r9d, ebx
0x18000de8a  mov     edx, 9C7h
0x18000de8f  jmp     loc_18000E492
0x18000de94  mov     rcx, [rsp+2B0h+var_270]
0x18000de99  mov     rax, [rcx]
0x18000de9c  xor     edx, edx
0x18000de9e  mov     rax, [rax+1F8h]
0x18000dea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000deaa  mov     ebx, eax
0x18000deac  mov     ecx, eax; int
0x18000deae  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000deb3  test    eax, eax
0x18000deb5  jnz     short loc_18000DEC4
0x18000deb7  mov     r9d, ebx
0x18000deba  mov     edx, 9CEh
0x18000debf  jmp     loc_18000E492
0x18000dec4  mov     rcx, [rsp+2B0h+var_270]
0x18000dec9  mov     rax, [rcx]
0x18000decc  xor     edx, edx
0x18000dece  mov     rax, [rax+220h]
0x18000ded5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000deda  mov     ebx, eax
0x18000dedc  mov     ecx, eax; int
0x18000dede  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000dee3  test    eax, eax
0x18000dee5  jnz     short loc_18000DEF4
0x18000dee7  mov     r9d, ebx
0x18000deea  mov     edx, 9D5h
0x18000deef  jmp     loc_18000E492
0x18000def4  lea     r8, Type; "SCHEMAS"
0x18000defb  lea     rdx, Name; "IDS_UNATTEND"
0x18000df02  mov     rcx, cs:?hInstance@@3PEAUHINSTANCE__@@EA; hModule
0x18000df09  call    cs:__imp_FindResourceW
0x18000df0f  test    rax, rax
0x18000df12  jnz     short loc_18000DF24
0x18000df14  mov     edx, 9DDh
0x18000df19  mov     r9d, 80004005h
0x18000df1f  jmp     loc_18000E492
0x18000df24  mov     rdx, rax; hResInfo
0x18000df27  mov     rcx, cs:?hInstance@@3PEAUHINSTANCE__@@EA; hModule
0x18000df2e  call    cs:__imp_LoadResource
0x18000df34  mov     rdi, rax
0x18000df37  test    rax, rax
0x18000df3a  jnz     short loc_18000DF5E
0x18000df3c  call    cs:__imp_GetLastError
0x18000df42  mov     ebx, eax
0x18000df44  test    eax, eax
0x18000df46  jle     short loc_18000DF51
0x18000df48  movzx   ebx, ax
0x18000df4b  or      ebx, 80070000h
0x18000df51  mov     r9d, ebx
0x18000df54  mov     edx, 9E6h
0x18000df59  jmp     loc_18000E492
0x18000df5e  mov     rcx, rdi; hResData
0x18000df61  call    cs:__imp_LockResource
0x18000df67  test    rax, rax
0x18000df6a  jnz     short loc_18000DF7F
0x18000df6c  mov     r9d, 80004005h
0x18000df72  mov     ebx, r9d
0x18000df75  mov     edx, 9EFh
0x18000df7a  jmp     loc_18000E492
0x18000df7f  mov     ecx, 0FFFEh
0x18000df84  cmp     [rax], cx
0x18000df87  jz      short loc_18000DF96
0x18000df89  mov     ecx, 0FEFFh
0x18000df8e  cmp     [rax], cx
0x18000df91  mov     rcx, rax
0x18000df94  jnz     short loc_18000DF9A
0x18000df96  lea     rcx, [rax+2]; psz
0x18000df9a  call    cs:__imp_SysAllocString
0x18000dfa0  mov     r15, rax
0x18000dfa3  mov     rcx, [rsp+2B0h+var_270]
0x18000dfa8  mov     rax, [rcx]
0x18000dfab  lea     r8, [rsp+2B0h+var_278]
0x18000dfb0  mov     rdx, r15
0x18000dfb3  mov     rax, [rax+208h]
0x18000dfba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfbf  mov     ebx, eax
0x18000dfc1  mov     ecx, eax; int
0x18000dfc3  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000dfc8  test    eax, eax
0x18000dfca  jnz     short loc_18000DFD9
0x18000dfcc  mov     r9d, ebx
0x18000dfcf  mov     edx, 9FFh
0x18000dfd4  jmp     loc_18000E492
0x18000dfd9  or      eax, 0FFFFFFFFh
0x18000dfdc  cmp     word ptr [rsp+2B0h+var_278], ax
0x18000dfe1  jz      short loc_18000DFF6
0x18000dfe3  mov     r9d, 80004005h
0x18000dfe9  mov     ebx, r9d
0x18000dfec  mov     edx, 0A07h
0x18000dff1  jmp     loc_18000E492
0x18000dff6  mov     rcx, rdi; hResData
0x18000dff9  call    cs:__imp_FreeResource
0x18000dfff  test    eax, eax
0x18000e001  jz      short loc_18000E016
0x18000e003  mov     r9d, 80004005h
0x18000e009  mov     ebx, r9d
0x18000e00c  mov     edx, 0A0Fh
0x18000e011  jmp     loc_18000E492
0x18000e016  lea     rax, [rsp+2B0h+var_268]
0x18000e01b  mov     qword ptr [rsp+2B0h+ppv], rax; ppv
0x18000e020  lea     r9, _GUID_373984c8_b845_449b_91e7_45ac83036ade; riid
0x18000e027  mov     r8d, esi; dwClsContext
0x18000e02a  xor     edx, edx; pUnkOuter
0x18000e02c  lea     rcx, _GUID_88d96a07_f192_11d4_a65f_0040963251e5; rclsid
0x18000e033  call    cs:__imp_CoCreateInstance
0x18000e039  mov     ebx, eax
0x18000e03b  mov     ecx, eax; int
0x18000e03d  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000e042  test    eax, eax
0x18000e044  jnz     short loc_18000E053
0x18000e046  mov     r9d, ebx
0x18000e049  mov     edx, 0A1Ch
0x18000e04e  jmp     loc_18000E492
0x18000e053  mov     [rsp+2B0h+var_258], r13
0x18000e058  mov     rcx, [rsp+2B0h+var_270]
0x18000e05d  mov     rax, [rcx]
0x18000e060  lea     r8, [rsp+2B0h+var_258]
0x18000e065  lea     rdx, IID_IDispatch
0x18000e06c  mov     rax, [rax]
0x18000e06f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e074  mov     ebx, eax
0x18000e076  mov     ecx, eax; int
0x18000e078  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000e07d  test    eax, eax
0x18000e07f  jnz     short loc_18000E08E
0x18000e081  mov     r9d, ebx
0x18000e084  mov     edx, 0A25h
0x18000e089  jmp     loc_18000E492
0x18000e08e  mov     rax, [rsp+2B0h+var_258]
0x18000e093  mov     qword ptr [rbp+1B0h+pvarg+8], rax
0x18000e097  mov     eax, 9
0x18000e09c  mov     word ptr [rbp+1B0h+pvarg], ax
0x18000e0a0  lea     rcx, psz; "urn:longhornGlobalizationUnattend"
0x18000e0a7  call    cs:__imp_SysAllocString
0x18000e0ad  mov     r12, rax
0x18000e0b0  movups  xmm0, xmmword ptr [rbp+1B0h+pvarg]
0x18000e0b4  movaps  xmmword ptr [rsp+2B0h+var_248+8], xmm0
0x18000e0b9  movsd   xmm1, qword ptr [rbp+1B0h+pvarg+10h]
0x18000e0be  movsd   [rbp+1B0h+var_230], xmm1
0x18000e0c3  mov     r9, [rsp+2B0h+var_268]
0x18000e0c8  mov     rcx, [r9]
0x18000e0cb  mov     rax, [rcx+38h]
0x18000e0cf  lea     r8, [rsp+2B0h+var_248+8]
0x18000e0d4  mov     rdx, r12
0x18000e0d7  mov     rcx, r9
0x18000e0da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0df  mov     ebx, eax
0x18000e0e1  mov     ecx, eax; int
0x18000e0e3  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000e0e8  test    eax, eax
0x18000e0ea  jnz     short loc_18000E0F9
0x18000e0ec  mov     r9d, ebx
0x18000e0ef  mov     edx, 0A34h
0x18000e0f4  jmp     loc_18000E492
0x18000e0f9  lea     rax, [rsp+2B0h+var_280]
0x18000e0fe  mov     qword ptr [rsp+2B0h+ppv], rax; int
0x18000e103  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x18000e10a  mov     r8d, esi; dwClsContext
0x18000e10d  xor     edx, edx; pUnkOuter
0x18000e10f  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x18000e116  call    cs:__imp_CoCreateInstance
0x18000e11c  mov     ebx, eax
0x18000e11e  mov     ecx, eax; int
0x18000e120  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000e125  test    eax, eax
0x18000e127  jz      loc_18000E479
0x18000e12d  mov     rcx, [rsp+2B0h+var_280]
0x18000e132  test    rcx, rcx
0x18000e135  jz      loc_18000E479
0x18000e13b  mov     rax, [rcx]
0x18000e13e  xor     edx, edx
0x18000e140  mov     rax, [rax+1F8h]
0x18000e147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e14c  mov     ebx, eax
0x18000e14e  mov     ecx, eax; int
0x18000e150  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000e155  test    eax, eax
0x18000e157  jnz     short loc_18000E166
0x18000e159  mov     r9d, ebx
0x18000e15c  mov     edx, 0A48h
0x18000e161  jmp     loc_18000E492
0x18000e166  mov     rcx, [rsp+2B0h+var_280]
0x18000e16b  mov     rax, [rcx]
0x18000e16e  or      edi, 0FFFFFFFFh
0x18000e171  mov     edx, edi
0x18000e173  mov     rax, [rax+220h]
  ... truncated ...
```
