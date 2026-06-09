# COfflineFilesMachineConfiguration::UpdateOrRemoveWMISlowLinkParamsProperty(IWbemClassObject *,IWbemServices *)

- ea: `0x18001e9b8`
- end: `0x18001ec27`
- name: `?UpdateOrRemoveWMISlowLinkParamsProperty@COfflineFilesMachineConfiguration@@CAJPEAUIWbemClassObject@@PEAUIWbemServices@@@Z`
- size: `623`
- prototype: `__int64 __fastcall(struct IWbemClassObject *, struct IWbemServices *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001f820`

## callees

- `0x18000a084`
- `0x18000f60c`
- `0x1800140c8`
- `0x18001886c`
- `0x18001c7bc`
- `0x18001c8c8`
- `0x18001ca10`
- `0x18001cbf0`
- `0x18001cda0`
- `0x18001d74c`
- `0x18001d78c`
- `0x18001d8e4`
- `0x18001d954`
- `0x18001d9d8`
- `0x18001da18`
- `0x18001dc18`
- `0x18001e9b8`
- `0x18002c010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001e9d6`
- `OLEAUT32!__imp_VariantInit` at `0x18001ea75`
- `OLEAUT32!__imp_VariantInit` at `0x18001eade`
- `OLEAUT32!__imp_VariantInit` at `0x18001e9d6`
- `OLEAUT32!__imp_VariantInit` at `0x18001ea75`
- `OLEAUT32!__imp_VariantInit` at `0x18001eade`
- `OLEAUT32!__imp_VariantClear` at `0x18001eb78`
- `OLEAUT32!__imp_VariantClear` at `0x18001eb89`
- `OLEAUT32!__imp_VariantClear` at `0x18001ebde`
- `OLEAUT32!__imp_VariantClear` at `0x18001ebe8`
- `OLEAUT32!__imp_VariantClear` at `0x18001ebfb`
- `OLEAUT32!__imp_VariantClear` at `0x18001eb78`
- `OLEAUT32!__imp_VariantClear` at `0x18001eb89`
- `OLEAUT32!__imp_VariantClear` at `0x18001ebde`
- `OLEAUT32!__imp_VariantClear` at `0x18001ebe8`
- `OLEAUT32!__imp_VariantClear` at `0x18001ebfb`

## string_xrefs

- `0x18001ea88`: `SlowLinkEnabled`
- `0x18001e9e5`: `SlowLinkParams`
- `0x18001ea2a`: `SlowLinkParams`
- `0x18001eba4`: `SlowLinkParams`

## pseudocode

```c
__int64 __fastcall COfflineFilesMachineConfiguration::UpdateOrRemoveWMISlowLinkParamsProperty(
        struct IWbemClassObject *a1,
        SAFEARRAY *a2)
{
  int v3; // eax
  int PropertyWMISettingDescriptor; // ebx
  int i; // edi
  int LowerBound; // ebx
  int v7; // eax
  VARIANTARG *v8; // rax
  char v10; // [rsp+20h] [rbp-39h]
  VARIANTARG v11; // [rsp+40h] [rbp-19h] BYREF
  VARIANTARG v12; // [rsp+58h] [rbp-1h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp+17h] BYREF
  struct tagSAFEARRAY *v14; // [rsp+C0h] [rbp+67h] BYREF
  SAFEARRAY *ppsaOut; // [rsp+C8h] [rbp+6Fh] BYREF
  char v16; // [rsp+D0h] [rbp+77h] BYREF
  int v17; // [rsp+D4h] [rbp+7Bh]

  ppsaOut = a2;
  VariantInit(&pvarg);
  v10 = 0;
  v3 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const WCHAR *, _QWORD, VARIANTARG *))a1->lpVtbl->Get)(
         a1,
         L"SlowLinkParams",
         0,
         &pvarg);
  PropertyWMISettingDescriptor = v3;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_SD(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      102,
      (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
      (unsigned int)L"SlowLinkParams",
      v3);
  }
  if ( PropertyWMISettingDescriptor >= 0 && pvarg.vt == 8200 )
  {
    ATL::CComSafeArrayBound::`default constructor closure'((ATL::CComSafeArrayBound *)&v16);
    v17 = 0;
    ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(&v14, &v16);
    VariantInit(&v12);
    if ( (int)CSCWmiConfig::GetUserStateSettingForWbemClassObject(L"SlowLinkEnabled", &v12, 0, 34) < 0
      || v12.vt != 11
      || !v12.iVal )
    {
      goto LABEL_21;
    }
    ATL::CComSafeArray<unsigned short *,8>::CComSafeArray<unsigned short *,8>(&ppsaOut, pvarg.parray);
    for ( i = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&ppsaOut);
          i < (unsigned int)ATL::CComSafeArray<unsigned short *,8>::GetCount(&ppsaOut);
          ++i )
    {
      VariantInit(&v11);
      if ( !ppsaOut )
        ATL::AtlThrowImpl(-2147467259);
      LowerBound = ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(&ppsaOut);
      if ( i < LowerBound || i > (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(&ppsaOut) )
        ATL::AtlThrowImpl(-2147024809);
      PropertyWMISettingDescriptor = COfflineFilesMachineConfiguration::ParseSlowLinkParamsString(
                                       *((const unsigned __int16 **)ppsaOut->pvData + i - LowerBound),
                                       (struct ATL::CComVariant *)&v11);
      if ( PropertyWMISettingDescriptor < 0 )
      {
        VariantClear(&v11);
        break;
      }
      v7 = ATL::CComSafeArray<tagVARIANT,12>::Add(&v14, &v11);
      PropertyWMISettingDescriptor = v7;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
      {
        WPP_SF_dd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          103,
          WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
          (unsigned int)i,
          v7);
      }
      VariantClear(&v11);
    }
    ATL::CComSafeArray<unsigned short *,8>::Destroy(&ppsaOut);
    if ( PropertyWMISettingDescriptor >= 0 )
    {
LABEL_21:
      ppsaOut = 0;
      PropertyWMISettingDescriptor = FindPropertyWMISettingDescriptor(
                                       L"SlowLinkParams",
                                       (const struct USERSTATE_SETTING_DESCRIPTOR **)&ppsaOut);
      if ( PropertyWMISettingDescriptor >= 0 )
      {
        v8 = (VARIANTARG *)ATL::CComVariant::CComVariant((ATL::CComVariant *)&v11, v14);
        PropertyWMISettingDescriptor = SetUserStateSetting((__int64)ppsaOut, v8, 0, 0x22u, v10);
        VariantClear(&v11);
      }
    }
    VariantClear(&v12);
    ATL::CComSafeArray<unsigned short *,8>::Destroy(&v14);
  }
  VariantClear(&pvarg);
  return (unsigned int)PropertyWMISettingDescriptor;
}

```

## disassembly

```asm
0x18001e9b8  mov     [rsp-8+ppsaOut], rdx
0x18001e9bd  push    rbp
0x18001e9be  push    rbx
0x18001e9bf  push    rsi
0x18001e9c0  push    rdi
0x18001e9c1  push    r13
0x18001e9c3  lea     rbp, [rsp-37h]
0x18001e9c8  sub     rsp, 90h
0x18001e9cf  mov     rbx, rcx
0x18001e9d2  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001e9d6  call    cs:__imp_VariantInit
0x18001e9dc  mov     rax, [rbx]
0x18001e9df  lea     r9, [rbp+57h+pvarg]
0x18001e9e3  xor     esi, esi
0x18001e9e5  lea     rdx, CSCWMI_STR_PROP_SLOWLINKPARAMS; "SlowLinkParams"
0x18001e9ec  mov     [rsp+0B0h+var_88], rsi
0x18001e9f1  xor     r8d, r8d
0x18001e9f4  mov     rcx, rbx
0x18001e9f7  mov     [rsp+0B0h+var_90], rsi
0x18001e9fc  mov     rax, [rax+20h]
0x18001ea00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea05  mov     ebx, eax
0x18001ea07  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ea0e  lea     r13, WPP_GLOBAL_Control
0x18001ea15  cmp     rcx, r13
0x18001ea18  jz      short loc_18001EA41
0x18001ea1a  test    dword ptr [rcx+1Ch], 4000000h
0x18001ea21  jz      short loc_18001EA41
0x18001ea23  mov     rcx, [rcx+10h]
0x18001ea27  lea     edx, [rsi+66h]
0x18001ea2a  lea     r9, CSCWMI_STR_PROP_SLOWLINKPARAMS; "SlowLinkParams"
0x18001ea31  mov     dword ptr [rsp+0B0h+var_90], eax
0x18001ea35  lea     r8, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x18001ea3c  call    WPP_SF_SD
0x18001ea41  test    ebx, ebx
0x18001ea43  js      loc_18001EBF7
0x18001ea49  mov     eax, 2008h
0x18001ea4e  cmp     word ptr [rbp+57h+pvarg], ax
0x18001ea52  jnz     loc_18001EBF7
0x18001ea58  lea     rcx, [rbp+57h+arg_10]; this
0x18001ea5c  call    ??_FCComSafeArrayBound@ATL@@QEAAXXZ; ATL::CComSafeArrayBound::`default constructor closure'(void)
0x18001ea61  lea     rdx, [rbp+57h+arg_10]
0x18001ea65  mov     [rbp+57h+arg_14], esi
0x18001ea68  lea     rcx, [rbp+57h+arg_0]
0x18001ea6c  call    ??0?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAA@PEBUtagSAFEARRAYBOUND@@I@Z; ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(tagSAFEARRAYBOUND const *,uint)
0x18001ea71  lea     rcx, [rbp+57h+var_58]; pvarg
0x18001ea75  call    cs:__imp_VariantInit
0x18001ea7b  mov     r9d, 22h ; '"'
0x18001ea81  lea     rdx, [rbp+57h+var_58]
0x18001ea85  xor     r8d, r8d
0x18001ea88  lea     rcx, CSCWMI_STR_PROP_SLOWLINKENABLED; "SlowLinkEnabled"
0x18001ea8f  call    ?GetUserStateSettingForWbemClassObject@CSCWmiConfig@@YAJPEBGAEAVCComVariant@ATL@@PEAXW4USERSTATE_SETTING_SOURCES@@@Z; CSCWmiConfig::GetUserStateSettingForWbemClassObject(ushort const *,ATL::CComVariant &,void *,USERSTATE_SETTING_SOURCES)
0x18001ea94  test    eax, eax
0x18001ea96  js      loc_18001EB9C
0x18001ea9c  cmp     word ptr [rbp+57h+var_58], 0Bh
0x18001eaa1  jnz     loc_18001EB9C
0x18001eaa7  cmp     word ptr [rbp+57h+var_58+8], si
0x18001eaab  jz      loc_18001EB9C
0x18001eab1  mov     rdx, qword ptr [rbp+57h+pvarg+8]; struct tagSAFEARRAY *
0x18001eab5  lea     rcx, [rbp+57h+ppsaOut]; ppsaOut
0x18001eab9  call    ??0?$CComSafeArray@PEAG$07@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z; ATL::CComSafeArray<ushort *,8>::CComSafeArray<ushort *,8>(tagSAFEARRAY const *)
0x18001eabe  lea     rcx, [rbp+57h+ppsaOut]
0x18001eac2  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x18001eac7  mov     edi, eax
0x18001eac9  lea     rcx, [rbp+57h+ppsaOut]
0x18001eacd  call    ?GetCount@?$CComSafeArray@PEAG$07@ATL@@QEBAKI@Z; ATL::CComSafeArray<ushort *,8>::GetCount(uint)
0x18001ead2  cmp     edi, eax
0x18001ead4  jnb     loc_18001EB8F
0x18001eada  lea     rcx, [rbp+57h+var_70]; pvarg
0x18001eade  call    cs:__imp_VariantInit
0x18001eae4  cmp     [rbp+57h+ppsaOut], rsi
0x18001eae8  jz      loc_18001EC1C
0x18001eaee  lea     rcx, [rbp+57h+ppsaOut]
0x18001eaf2  call    ?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z; ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)
0x18001eaf7  mov     ebx, eax
0x18001eaf9  cmp     edi, eax
0x18001eafb  jl      loc_18001EC11
0x18001eb01  lea     rcx, [rbp+57h+ppsaOut]
0x18001eb05  call    ?GetUpperBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetUpperBound(uint)
0x18001eb0a  cmp     edi, eax
0x18001eb0c  jg      loc_18001EC11
0x18001eb12  mov     rax, [rbp+57h+ppsaOut]
0x18001eb16  lea     rdx, [rbp+57h+var_70]; struct ATL::CComVariant *
0x18001eb1a  mov     ecx, edi
0x18001eb1c  sub     ecx, ebx
0x18001eb1e  movsxd  r8, ecx
0x18001eb21  mov     rcx, [rax+10h]
0x18001eb25  mov     rcx, [rcx+r8*8]; unsigned __int16 *
0x18001eb29  call    ?ParseSlowLinkParamsString@COfflineFilesMachineConfiguration@@CAJPEBGAEAVCComVariant@ATL@@@Z; COfflineFilesMachineConfiguration::ParseSlowLinkParamsString(ushort const *,ATL::CComVariant &)
0x18001eb2e  mov     ebx, eax
0x18001eb30  test    eax, eax
0x18001eb32  js      short loc_18001EB85
0x18001eb34  lea     rdx, [rbp+57h+var_70]
0x18001eb38  lea     rcx, [rbp+57h+arg_0]
0x18001eb3c  call    ?Add@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJAEBUtagVARIANT@@H@Z; ATL::CComSafeArray<tagVARIANT,12>::Add(tagVARIANT const &,int)
0x18001eb41  mov     ebx, eax
0x18001eb43  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eb4a  cmp     rcx, r13
0x18001eb4d  jz      short loc_18001EB74
0x18001eb4f  test    dword ptr [rcx+1Ch], 4000000h
0x18001eb56  jz      short loc_18001EB74
0x18001eb58  mov     rcx, [rcx+10h]
0x18001eb5c  lea     r8, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x18001eb63  mov     edx, 67h ; 'g'
0x18001eb68  mov     dword ptr [rsp+0B0h+var_90], eax
0x18001eb6c  mov     r9d, edi
0x18001eb6f  call    WPP_SF_dd
0x18001eb74  lea     rcx, [rbp+57h+var_70]; pvarg
0x18001eb78  call    cs:__imp_VariantClear
0x18001eb7e  inc     edi
0x18001eb80  jmp     loc_18001EAC9
0x18001eb85  lea     rcx, [rbp+57h+var_70]; pvarg
0x18001eb89  call    cs:__imp_VariantClear
0x18001eb8f  lea     rcx, [rbp+57h+ppsaOut]
0x18001eb93  call    ?Destroy@?$CComSafeArray@PEAG$07@ATL@@QEAAJXZ; ATL::CComSafeArray<ushort *,8>::Destroy(void)
0x18001eb98  test    ebx, ebx
0x18001eb9a  js      short loc_18001EBE4
0x18001eb9c  lea     rdx, [rbp+57h+ppsaOut]; struct USERSTATE_SETTING_DESCRIPTOR **
0x18001eba0  mov     [rbp+57h+ppsaOut], rsi
0x18001eba4  lea     rcx, CSCWMI_STR_PROP_SLOWLINKPARAMS; "SlowLinkParams"
0x18001ebab  call    ?FindPropertyWMISettingDescriptor@@YAJPEBGPEAPEBUUSERSTATE_SETTING_DESCRIPTOR@@@Z; FindPropertyWMISettingDescriptor(ushort const *,USERSTATE_SETTING_DESCRIPTOR const * *)
0x18001ebb0  mov     ebx, eax
0x18001ebb2  test    eax, eax
0x18001ebb4  js      short loc_18001EBE4
0x18001ebb6  mov     rdx, [rbp+57h+arg_0]; struct tagSAFEARRAY *
0x18001ebba  lea     rcx, [rbp+57h+var_70]; this
0x18001ebbe  call    ??0CComVariant@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z; ATL::CComVariant::CComVariant(tagSAFEARRAY const *)
0x18001ebc3  mov     rcx, [rbp+57h+ppsaOut]
0x18001ebc7  mov     r9d, 22h ; '"'
0x18001ebcd  xor     r8d, r8d
0x18001ebd0  mov     rdx, rax
0x18001ebd3  call    ?SetUserStateSetting@@YAJPEBUUSERSTATE_SETTING_DESCRIPTOR@@AEBVCComVariant@ATL@@PEAXW4USERSTATE_SETTING_SOURCES@@PEBG@Z; SetUserStateSetting(USERSTATE_SETTING_DESCRIPTOR const *,ATL::CComVariant const &,void *,USERSTATE_SETTING_SOURCES,ushort const *)
0x18001ebd8  lea     rcx, [rbp+57h+var_70]; pvarg
0x18001ebdc  mov     ebx, eax
0x18001ebde  call    cs:__imp_VariantClear
0x18001ebe4  lea     rcx, [rbp+57h+var_58]; pvarg
0x18001ebe8  call    cs:__imp_VariantClear
0x18001ebee  lea     rcx, [rbp+57h+arg_0]
0x18001ebf2  call    ?Destroy@?$CComSafeArray@PEAG$07@ATL@@QEAAJXZ; ATL::CComSafeArray<ushort *,8>::Destroy(void)
0x18001ebf7  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001ebfb  call    cs:__imp_VariantClear
0x18001ec01  mov     eax, ebx
0x18001ec03  add     rsp, 90h
0x18001ec0a  pop     r13
0x18001ec0c  pop     rdi
0x18001ec0d  pop     rsi
0x18001ec0e  pop     rbx
0x18001ec0f  pop     rbp
0x18001ec10  retn
0x18001ec11  mov     ecx, 80070057h; int
0x18001ec16  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001ec1c  mov     ecx, 80004005h; int
0x18001ec21  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
