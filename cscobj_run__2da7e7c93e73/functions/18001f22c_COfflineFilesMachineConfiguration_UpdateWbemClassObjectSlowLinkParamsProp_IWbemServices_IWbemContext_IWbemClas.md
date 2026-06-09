# COfflineFilesMachineConfiguration::UpdateWbemClassObjectSlowLinkParamsProp(IWbemServices *,IWbemContext *,IWbemClassObject *)

- ea: `0x18001f22c`
- end: `0x18001f77c`
- name: `?UpdateWbemClassObjectSlowLinkParamsProp@COfflineFilesMachineConfiguration@@CAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemClassObject@@@Z`
- size: `1360`
- prototype: `__int64 __fastcall(struct IWbemServices *, struct IWbemContext *, struct IWbemClassObject *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180021b60`

## callees

- `0x18000b7c0`
- `0x18000c174`
- `0x18000f5a4`
- `0x18000f5cc`
- `0x1800140c8`
- `0x1800157b0`
- `0x18001886c`
- `0x18001c868`
- `0x18001ca10`
- `0x18001cb40`
- `0x18001cbf0`
- `0x18001cc7c`
- `0x18001ce64`
- `0x18001d74c`
- `0x18001d78c`
- `0x18001d8e4`
- `0x18001d954`
- `0x18001d9d8`
- `0x18001f22c`
- `0x180028678`
- `0x1800296a0`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18001f4c5`
- `OLEAUT32!__imp_SysStringLen` at `0x18001f4c5`
- `OLEAUT32!__imp_VariantInit` at `0x18001f26b`
- `OLEAUT32!__imp_VariantInit` at `0x18001f26b`
- `OLEAUT32!__imp_VariantClear` at `0x18001f2ec`
- `OLEAUT32!__imp_VariantClear` at `0x18001f5cf`
- `OLEAUT32!__imp_VariantClear` at `0x18001f2ec`
- `OLEAUT32!__imp_VariantClear` at `0x18001f5cf`

## string_xrefs

- `0x18001f27f`: `SlowLinkParams`
- `0x18001f6f2`: `SlowLinkParams`
- `0x18001f723`: `SlowLinkParams`

## pseudocode

```c
__int64 __fastcall COfflineFilesMachineConfiguration::UpdateWbemClassObjectSlowLinkParamsProp(
        struct IWbemServices *a1,
        struct IWbemContext *a2,
        struct IWbemClassObject *a3)
{
  int PropertyWMISettingDescriptor; // ebx
  int i; // ebx
  int LowerBound; // edi
  int v7; // edi
  int v8; // edi
  int v9; // eax
  __int64 v10; // rdi
  int v11; // eax
  __int64 v12; // rdi
  int v13; // edi
  __int64 v14; // rsi
  int v15; // eax
  __int64 v16; // rdi
  __int64 v17; // rcx
  __int64 v18; // rdx
  int v19; // edi
  ATL::CComVariant *v20; // rax
  __int64 v22; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  struct tagSAFEARRAY *v24; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v25[4]; // [rsp+48h] [rbp-B8h] BYREF
  int v26; // [rsp+4Ch] [rbp-B4h]
  VARIANTARG pvarg; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v28; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 v29[520]; // [rsp+70h] [rbp-90h] BYREF

  v23 = 0;
  VariantInit(&pvarg);
  v24 = 0;
  PropertyWMISettingDescriptor = FindPropertyWMISettingDescriptor(
                                   L"SlowLinkParams",
                                   (const struct USERSTATE_SETTING_DESCRIPTOR **)&v24);
  if ( PropertyWMISettingDescriptor >= 0 )
  {
    CSCWmiConfig::AddSettingAuthorityFlag(2);
    PropertyWMISettingDescriptor = GetUserStateSetting(3, v24, &pvarg);
    if ( PropertyWMISettingDescriptor < 0 || pvarg.vt != 8204 )
    {
      VariantClear(&pvarg);
      PropertyWMISettingDescriptor = 0;
      goto LABEL_54;
    }
    ATL::CComSafeArray<tagVARIANT,12>::operator=(&v23, pvarg.llVal);
  }
  VariantClear(&pvarg);
  if ( PropertyWMISettingDescriptor >= 0 )
  {
    ATL::CComSafeArrayBound::`default constructor closure'((ATL::CComSafeArrayBound *)v25);
    v26 = 0;
    ATL::CComSafeArray<unsigned short *,8>::CComSafeArray<unsigned short *,8>(&v24, v25);
    for ( i = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&v23);
          i < (unsigned int)ATL::CComSafeArray<unsigned short *,8>::GetCount(&v23);
          ++i )
    {
      v22 = 0;
      if ( !v23 )
        goto LABEL_49;
      LowerBound = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&v23);
      if ( i < LowerBound || i > (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&v23) )
        goto LABEL_48;
      if ( *(_WORD *)(*(_QWORD *)(v23 + 16) + 24LL * (i - LowerBound)) != 8204 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
        {
          v19 = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&v23);
          if ( i < v19 || i > (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&v23) )
LABEL_48:
            ATL::AtlThrowImpl(-2147024809);
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            104,
            WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
            *(unsigned __int16 *)(*(_QWORD *)(v23 + 16) + 24LL * (i - v19)));
        }
        goto LABEL_47;
      }
      v7 = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&v23);
      if ( i < v7 || i > (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&v23) )
        goto LABEL_48;
      ATL::CComSafeArray<tagVARIANT,12>::operator=(&v22, *(_QWORD *)(*(_QWORD *)(v23 + 16) + 24LL * (i - v7) + 8));
      if ( (unsigned int)ATL::CComSafeArray<unsigned short *,8>::GetCount(&v22) < 2 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
        {
          v18 = 105;
LABEL_41:
          WPP_SF_(*(_QWORD *)(v17 + 16), v18, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids);
        }
LABEL_47:
        ATL::CComSafeArray<unsigned short *,8>::Destroy(&v22);
        ATL::CComSafeArray<unsigned short *,8>::Destroy(&v24);
        PropertyWMISettingDescriptor = -2147024809;
        goto LABEL_54;
      }
      if ( !v22 )
        goto LABEL_49;
      v8 = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&v22);
      if ( v8 > 1 || (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&v22) < 1 )
        goto LABEL_48;
      if ( *(_WORD *)(*(_QWORD *)(v22 + 16) + 24LL * (1 - v8)) != 8 )
        goto LABEL_35;
      v9 = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&v22);
      v10 = v9;
      if ( v9 > 0 || (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&v22) < 0 )
        goto LABEL_48;
      if ( *(_WORD *)(*(_QWORD *)(v22 + 16) - 24 * v10) != 8 )
        goto LABEL_35;
      v11 = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&v22);
      v12 = v11;
      if ( v11 > 0 || (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&v22) < 0 )
        goto LABEL_48;
      if ( !SysStringLen(*(BSTR *)(*(_QWORD *)(v22 + 16) - 24 * v12 + 8)) )
      {
LABEL_35:
        v17 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
        {
          v18 = 106;
          goto LABEL_41;
        }
        goto LABEL_47;
      }
      memset_0(v29, 0, sizeof(v29));
      if ( !v22 )
        goto LABEL_49;
      v13 = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&v22);
      if ( v13 > 1 || (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&v22) < 1 )
        goto LABEL_48;
      if ( !v22 )
LABEL_49:
        ATL::AtlThrowImpl(-2147467259);
      v14 = *(_QWORD *)(*(_QWORD *)(v22 + 16) + 24LL * (1 - v13) + 8);
      v15 = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&v22);
      v16 = v15;
      if ( v15 > 0 || (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&v22) < 0 )
        goto LABEL_48;
      if ( (int)StringCchPrintfW(v29, 0x208u, L"%ls;%ls", *(_QWORD *)(*(_QWORD *)(v22 + 16) - 24 * v16 + 8), v14) >= 0 )
      {
        v28 = v29;
        ATL::CComSafeArray<unsigned short *,8>::Add(&v24, &v28);
      }
      ATL::CComSafeArray<unsigned short *,8>::Destroy(&v22);
    }
    v20 = ATL::CComVariant::CComVariant((ATL::CComVariant *)&pvarg, v24);
    PropertyWMISettingDescriptor = WmiProp_SetProperty(a3, L"SlowLinkParams", v20);
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
    {
      WPP_SF_SD(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        107,
        (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
        (unsigned int)L"SlowLinkParams",
        PropertyWMISettingDescriptor);
    }
    ATL::CComSafeArray<unsigned short *,8>::Destroy(&v24);
  }
LABEL_54:
  ATL::CComSafeArray<unsigned short *,8>::Destroy(&v23);
  return (unsigned int)PropertyWMISettingDescriptor;
}

```

## disassembly

```asm
0x18001f22c  mov     [rsp-8+arg_0], rbx
0x18001f231  mov     [rsp-8+arg_8], rsi
0x18001f236  push    rbp
0x18001f237  push    rdi
0x18001f238  push    r14
0x18001f23a  lea     rbp, [rsp-390h]
0x18001f242  sub     rsp, 490h
0x18001f249  mov     rax, cs:__security_cookie
0x18001f250  xor     rax, rsp
0x18001f253  mov     [rbp+3A0h+var_20], rax
0x18001f25a  lea     rcx, [rsp+4A0h+pvarg]; pvarg
0x18001f25f  mov     [rsp+4A0h+var_468], 0
0x18001f268  mov     r14, r8
0x18001f26b  call    cs:__imp_VariantInit
0x18001f271  lea     rdx, [rsp+4A0h+var_460]; struct USERSTATE_SETTING_DESCRIPTOR **
0x18001f276  mov     [rsp+4A0h+var_460], 0
0x18001f27f  lea     rcx, CSCWMI_STR_PROP_SLOWLINKPARAMS; "SlowLinkParams"
0x18001f286  call    ?FindPropertyWMISettingDescriptor@@YAJPEBGPEAPEBUUSERSTATE_SETTING_DESCRIPTOR@@@Z; FindPropertyWMISettingDescriptor(ushort const *,USERSTATE_SETTING_DESCRIPTOR const * *)
0x18001f28b  mov     ebx, eax
0x18001f28d  mov     esi, 200Ch
0x18001f292  test    eax, eax
0x18001f294  js      short loc_18001F2E7
0x18001f296  mov     ecx, 2
0x18001f29b  call    ?AddSettingAuthorityFlag@CSCWmiConfig@@YA?AW4USERSTATE_SETTING_SOURCES@@W42@@Z; CSCWmiConfig::AddSettingAuthorityFlag(USERSTATE_SETTING_SOURCES)
0x18001f2a0  mov     rdx, [rsp+4A0h+var_460]
0x18001f2a5  lea     r8, [rsp+4A0h+pvarg]
0x18001f2aa  xor     r9d, r9d
0x18001f2ad  mov     [rsp+4A0h+var_478], 0
0x18001f2b6  mov     dword ptr [rsp+4A0h+var_480], eax
0x18001f2ba  lea     ecx, [r9+3]
0x18001f2be  call    ?GetUserStateSetting@@YAJW4UST_COMPONENT_ID@@PEBUUSERSTATE_SETTING_DESCRIPTOR@@AEAVCComVariant@ATL@@PEAXW4USERSTATE_SETTING_SOURCES@@PEBG@Z; GetUserStateSetting(UST_COMPONENT_ID,USERSTATE_SETTING_DESCRIPTOR const *,ATL::CComVariant &,void *,USERSTATE_SETTING_SOURCES,ushort const *)
0x18001f2c3  mov     ebx, eax
0x18001f2c5  test    eax, eax
0x18001f2c7  js      loc_18001F5CA
0x18001f2cd  cmp     word ptr [rsp+4A0h+pvarg], si
0x18001f2d2  jnz     loc_18001F5CA
0x18001f2d8  mov     rdx, qword ptr [rsp+4A0h+pvarg+8]
0x18001f2dd  lea     rcx, [rsp+4A0h+var_468]
0x18001f2e2  call    ??4?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAAEAV01@PEBUtagSAFEARRAY@@@Z; ATL::CComSafeArray<tagVARIANT,12>::operator=(tagSAFEARRAY const *)
0x18001f2e7  lea     rcx, [rsp+4A0h+pvarg]; pvarg
0x18001f2ec  call    cs:__imp_VariantClear
0x18001f2f2  test    ebx, ebx
0x18001f2f4  js      loc_18001F749
0x18001f2fa  lea     rcx, [rsp+4A0h+var_458]; this
0x18001f2ff  call    ??_FCComSafeArrayBound@ATL@@QEAAXXZ; ATL::CComSafeArrayBound::`default constructor closure'(void)
0x18001f304  lea     rdx, [rsp+4A0h+var_458]
0x18001f309  mov     [rsp+4A0h+var_454], 0
0x18001f311  lea     rcx, [rsp+4A0h+var_460]
0x18001f316  call    ??0?$CComSafeArray@PEAG$07@ATL@@QEAA@PEBUtagSAFEARRAYBOUND@@I@Z; ATL::CComSafeArray<ushort *,8>::CComSafeArray<ushort *,8>(tagSAFEARRAYBOUND const *,uint)
0x18001f31b  lea     rcx, [rsp+4A0h+var_468]
0x18001f320  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x18001f325  mov     ebx, eax
0x18001f327  lea     rcx, [rsp+4A0h+var_468]
0x18001f32c  call    ?GetCount@?$CComSafeArray@PEAG$07@ATL@@QEBAKI@Z; ATL::CComSafeArray<ushort *,8>::GetCount(uint)
0x18001f331  cmp     ebx, eax
0x18001f333  jnb     loc_18001F6E0
0x18001f339  cmp     [rsp+4A0h+var_468], 0
0x18001f33f  mov     [rsp+4A0h+var_470], 0
0x18001f348  jz      loc_18001F6D5
0x18001f34e  lea     rcx, [rsp+4A0h+var_468]
0x18001f353  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x18001f358  mov     edi, eax
0x18001f35a  cmp     ebx, eax
0x18001f35c  jl      loc_18001F6CA
0x18001f362  lea     rcx, [rsp+4A0h+var_468]
0x18001f367  call    ?GetUpperBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetUpperBound(uint)
0x18001f36c  cmp     ebx, eax
0x18001f36e  jg      loc_18001F6CA
0x18001f374  mov     eax, ebx
0x18001f376  sub     eax, edi
0x18001f378  cdqe
0x18001f37a  lea     rdx, [rax+rax*2]
0x18001f37e  mov     rax, [rsp+4A0h+var_468]
0x18001f383  mov     rcx, [rax+10h]
0x18001f387  cmp     [rcx+rdx*8], si
0x18001f38b  jnz     loc_18001F642
0x18001f391  lea     rcx, [rsp+4A0h+var_468]
0x18001f396  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x18001f39b  mov     edi, eax
0x18001f39d  cmp     ebx, eax
0x18001f39f  jl      loc_18001F6CA
0x18001f3a5  lea     rcx, [rsp+4A0h+var_468]
0x18001f3aa  call    ?GetUpperBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetUpperBound(uint)
0x18001f3af  cmp     ebx, eax
0x18001f3b1  jg      loc_18001F6CA
0x18001f3b7  mov     eax, ebx
0x18001f3b9  sub     eax, edi
0x18001f3bb  cdqe
0x18001f3bd  lea     rcx, [rax+rax*2]
0x18001f3c1  mov     rax, [rsp+4A0h+var_468]
0x18001f3c6  mov     rdx, [rax+10h]
0x18001f3ca  mov     rdx, [rdx+rcx*8+8]
0x18001f3cf  lea     rcx, [rsp+4A0h+var_470]
0x18001f3d4  call    ??4?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAAEAV01@PEBUtagSAFEARRAY@@@Z; ATL::CComSafeArray<tagVARIANT,12>::operator=(tagSAFEARRAY const *)
0x18001f3d9  lea     rcx, [rsp+4A0h+var_470]
0x18001f3de  call    ?GetCount@?$CComSafeArray@PEAG$07@ATL@@QEBAKI@Z; ATL::CComSafeArray<ushort *,8>::GetCount(uint)
0x18001f3e3  cmp     eax, 2
0x18001f3e6  jb      loc_18001F607
0x18001f3ec  cmp     [rsp+4A0h+var_470], 0
0x18001f3f2  jz      loc_18001F6D5
0x18001f3f8  lea     rcx, [rsp+4A0h+var_470]
0x18001f3fd  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x18001f402  mov     edi, eax
0x18001f404  cmp     eax, 1
0x18001f407  jg      loc_18001F6CA
0x18001f40d  lea     rcx, [rsp+4A0h+var_470]
0x18001f412  call    ?GetUpperBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetUpperBound(uint)
0x18001f417  cmp     eax, 1
0x18001f41a  jl      loc_18001F6CA
0x18001f420  mov     eax, 1
0x18001f425  sub     eax, edi
0x18001f427  cdqe
0x18001f429  lea     rdx, [rax+rax*2]
0x18001f42d  mov     rax, [rsp+4A0h+var_470]
0x18001f432  mov     rcx, [rax+10h]
0x18001f436  cmp     word ptr [rcx+rdx*8], 8
0x18001f43b  jnz     loc_18001F5DC
0x18001f441  lea     rcx, [rsp+4A0h+var_470]
0x18001f446  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x18001f44b  movsxd  rdi, eax
0x18001f44e  test    eax, eax
0x18001f450  jg      loc_18001F6CA
0x18001f456  lea     rcx, [rsp+4A0h+var_470]
0x18001f45b  call    ?GetUpperBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetUpperBound(uint)
0x18001f460  test    eax, eax
0x18001f462  js      loc_18001F6CA
0x18001f468  mov     rax, [rsp+4A0h+var_470]
0x18001f46d  lea     rdx, [rdi+rdi*2]
0x18001f471  shl     rdx, 3
0x18001f475  mov     rcx, [rax+10h]
0x18001f479  sub     rcx, rdx
0x18001f47c  cmp     word ptr [rcx], 8
0x18001f480  jnz     loc_18001F5DC
0x18001f486  lea     rcx, [rsp+4A0h+var_470]
0x18001f48b  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x18001f490  movsxd  rdi, eax
0x18001f493  test    eax, eax
0x18001f495  jg      loc_18001F6CA
0x18001f49b  lea     rcx, [rsp+4A0h+var_470]
0x18001f4a0  call    ?GetUpperBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetUpperBound(uint)
0x18001f4a5  test    eax, eax
0x18001f4a7  js      loc_18001F6CA
0x18001f4ad  mov     rax, [rsp+4A0h+var_470]
0x18001f4b2  lea     rdx, [rdi+rdi*2]
0x18001f4b6  shl     rdx, 3
0x18001f4ba  mov     rcx, [rax+10h]
0x18001f4be  sub     rcx, rdx
0x18001f4c1  mov     rcx, [rcx+8]; pbstr
0x18001f4c5  call    cs:__imp_SysStringLen
0x18001f4cb  test    eax, eax
0x18001f4cd  jz      loc_18001F5DC
0x18001f4d3  xor     edx, edx; Val
0x18001f4d5  lea     rcx, [rsp+4A0h+var_430]; void *
0x18001f4da  mov     r8d, 410h; Size
0x18001f4e0  call    memset_0
0x18001f4e5  cmp     [rsp+4A0h+var_470], 0
0x18001f4eb  jz      loc_18001F6D5
0x18001f4f1  lea     rcx, [rsp+4A0h+var_470]
0x18001f4f6  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x18001f4fb  mov     edi, eax
0x18001f4fd  cmp     eax, 1
0x18001f500  jg      loc_18001F6CA
0x18001f506  lea     rcx, [rsp+4A0h+var_470]
0x18001f50b  call    ?GetUpperBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetUpperBound(uint)
0x18001f510  cmp     eax, 1
0x18001f513  jl      loc_18001F6CA
0x18001f519  mov     rcx, [rsp+4A0h+var_470]
0x18001f51e  test    rcx, rcx
0x18001f521  jz      loc_18001F6D5
0x18001f527  mov     eax, 1
0x18001f52c  sub     eax, edi
0x18001f52e  cdqe
0x18001f530  lea     rdx, [rax+rax*2]
0x18001f534  mov     rax, [rcx+10h]
0x18001f538  lea     rcx, [rsp+4A0h+var_470]
0x18001f53d  mov     rsi, [rax+rdx*8+8]
0x18001f542  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x18001f547  movsxd  rdi, eax
0x18001f54a  test    eax, eax
0x18001f54c  jg      loc_18001F6CA
0x18001f552  lea     rcx, [rsp+4A0h+var_470]
0x18001f557  call    ?GetUpperBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetUpperBound(uint)
0x18001f55c  test    eax, eax
0x18001f55e  js      loc_18001F6CA
0x18001f564  mov     rax, [rsp+4A0h+var_470]
0x18001f569  lea     rcx, [rdi+rdi*2]
0x18001f56d  shl     rcx, 3
0x18001f571  lea     r8, aLsLs; "%ls;%ls"
0x18001f578  mov     edx, 208h; unsigned __int64
0x18001f57d  mov     [rsp+4A0h+var_480], rsi
0x18001f582  mov     r9, [rax+10h]
0x18001f586  sub     r9, rcx
0x18001f589  lea     rcx, [rsp+4A0h+var_430]; unsigned __int16 *
0x18001f58e  mov     r9, [r9+8]
0x18001f592  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001f597  test    eax, eax
0x18001f599  js      short loc_18001F5B4
0x18001f59b  lea     rax, [rsp+4A0h+var_430]
0x18001f5a0  lea     rdx, [rsp+4A0h+var_438]
0x18001f5a5  mov     [rsp+4A0h+var_438], rax
0x18001f5aa  lea     rcx, [rsp+4A0h+var_460]
0x18001f5af  call    ?Add@?$CComSafeArray@PEAG$07@ATL@@QEAAJAEBQEAGH@Z; ATL::CComSafeArray<ushort *,8>::Add(ushort * const &,int)
0x18001f5b4  lea     rcx, [rsp+4A0h+var_470]
0x18001f5b9  call    ?Destroy@?$CComSafeArray@PEAG$07@ATL@@QEAAJXZ; ATL::CComSafeArray<ushort *,8>::Destroy(void)
0x18001f5be  inc     ebx
0x18001f5c0  mov     esi, 200Ch
0x18001f5c5  jmp     loc_18001F327
0x18001f5ca  lea     rcx, [rsp+4A0h+pvarg]; pvarg
0x18001f5cf  call    cs:__imp_VariantClear
0x18001f5d5  xor     ebx, ebx
0x18001f5d7  jmp     loc_18001F749
0x18001f5dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f5e3  lea     rax, WPP_GLOBAL_Control
0x18001f5ea  cmp     rcx, rax
0x18001f5ed  jz      loc_18001F6AF
0x18001f5f3  test    dword ptr [rcx+1Ch], 4000000h
0x18001f5fa  jz      loc_18001F6AF
0x18001f600  mov     edx, 6Ah ; 'j'
0x18001f605  jmp     short loc_18001F630
0x18001f607  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f60e  lea     rax, WPP_GLOBAL_Control
0x18001f615  cmp     rcx, rax
0x18001f618  jz      loc_18001F6AF
0x18001f61e  test    dword ptr [rcx+1Ch], 4000000h
0x18001f625  jz      loc_18001F6AF
0x18001f62b  mov     edx, 69h ; 'i'
0x18001f630  mov     rcx, [rcx+10h]
0x18001f634  lea     r8, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x18001f63b  call    WPP_SF_
0x18001f640  jmp     short loc_18001F6AF
0x18001f642  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f649  lea     rax, WPP_GLOBAL_Control
0x18001f650  cmp     rcx, rax
0x18001f653  jz      short loc_18001F6AF
0x18001f655  test    dword ptr [rcx+1Ch], 4000000h
0x18001f65c  jz      short loc_18001F6AF
0x18001f65e  lea     rcx, [rsp+4A0h+var_468]
0x18001f663  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x18001f668  mov     edi, eax
0x18001f66a  cmp     ebx, eax
0x18001f66c  jl      short loc_18001F6CA
0x18001f66e  lea     rcx, [rsp+4A0h+var_468]
0x18001f673  call    ?GetUpperBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetUpperBound(uint)
0x18001f678  cmp     ebx, eax
0x18001f67a  jg      short loc_18001F6CA
0x18001f67c  sub     ebx, edi
0x18001f67e  lea     r8, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x18001f685  movsxd  rax, ebx
0x18001f688  lea     rdx, [rax+rax*2]
0x18001f68c  mov     rax, [rsp+4A0h+var_468]
0x18001f691  mov     rcx, [rax+10h]
0x18001f695  movzx   r9d, word ptr [rcx+rdx*8]
0x18001f69a  mov     edx, 68h ; 'h'
0x18001f69f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f6a6  mov     rcx, [rcx+10h]
0x18001f6aa  call    WPP_SF_d
0x18001f6af  lea     rcx, [rsp+4A0h+var_470]
0x18001f6b4  call    ?Destroy@?$CComSafeArray@PEAG$07@ATL@@QEAAJXZ; ATL::CComSafeArray<ushort *,8>::Destroy(void)
0x18001f6b9  lea     rcx, [rsp+4A0h+var_460]
0x18001f6be  call    ?Destroy@?$CComSafeArray@PEAG$07@ATL@@QEAAJXZ; ATL::CComSafeArray<ushort *,8>::Destroy(void)
0x18001f6c3  mov     ebx, 80070057h
0x18001f6c8  jmp     short loc_18001F749
0x18001f6ca  mov     ecx, 80070057h; int
0x18001f6cf  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001f6d5  mov     ecx, 80004005h; int
0x18001f6da  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001f6e0  mov     rdx, [rsp+4A0h+var_460]; struct tagSAFEARRAY *
0x18001f6e5  lea     rcx, [rsp+4A0h+pvarg]; this
0x18001f6ea  call    ??0CComVariant@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z; ATL::CComVariant::CComVariant(tagSAFEARRAY const *)
0x18001f6ef  mov     r8, rax
0x18001f6f2  lea     rdx, CSCWMI_STR_PROP_SLOWLINKPARAMS; "SlowLinkParams"
0x18001f6f9  mov     rcx, r14
0x18001f6fc  call    ?WmiProp_SetProperty@@YAJPEAUIWbemClassObject@@PEBGVCComVariant@ATL@@@Z; WmiProp_SetProperty(IWbemClassObject *,ushort const *,ATL::CComVariant)
0x18001f701  mov     ebx, eax
0x18001f703  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f70a  lea     rax, WPP_GLOBAL_Control
0x18001f711  cmp     rcx, rax
0x18001f714  jz      short loc_18001F73F
0x18001f716  test    dword ptr [rcx+1Ch], 4000000h
0x18001f71d  jz      short loc_18001F73F
0x18001f71f  mov     rcx, [rcx+10h]
0x18001f723  lea     r9, CSCWMI_STR_PROP_SLOWLINKPARAMS; "SlowLinkParams"
0x18001f72a  mov     edx, 6Bh ; 'k'
0x18001f72f  mov     dword ptr [rsp+4A0h+var_480], ebx
0x18001f733  lea     r8, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x18001f73a  call    WPP_SF_SD
0x18001f73f  lea     rcx, [rsp+4A0h+var_460]
0x18001f744  call    ?Destroy@?$CComSafeArray@PEAG$07@ATL@@QEAAJXZ; ATL::CComSafeArray<ushort *,8>::Destroy(void)
0x18001f749  lea     rcx, [rsp+4A0h+var_468]
0x18001f74e  call    ?Destroy@?$CComSafeArray@PEAG$07@ATL@@QEAAJXZ; ATL::CComSafeArray<ushort *,8>::Destroy(void)
0x18001f753  mov     eax, ebx
0x18001f755  mov     rcx, [rbp+3A0h+var_20]
0x18001f75c  xor     rcx, rsp; StackCookie
0x18001f75f  call    __security_check_cookie
0x18001f764  lea     r11, [rsp+4A0h+var_10]
0x18001f76c  mov     rbx, [r11+20h]
0x18001f770  mov     rsi, [r11+28h]
0x18001f774  mov     rsp, r11
0x18001f777  pop     r14
0x18001f779  pop     rdi
  ... truncated ...
```
