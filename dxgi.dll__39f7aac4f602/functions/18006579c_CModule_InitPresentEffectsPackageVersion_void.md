# CModule::InitPresentEffectsPackageVersion(void)

- ea: `0x18006579c`
- end: `0x180065c3b`
- name: `?InitPresentEffectsPackageVersion@CModule@@QEAAXXZ`
- size: `1183`
- prototype: `void __fastcall(CModule *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180066040`

## callees

- `0x18000c6b0`
- `0x1800306f4`
- `0x18004c6d4`
- `0x18005ed10`
- `0x180064fe4`
- `0x18006579c`
- `0x18006903c`
- `0x180075fa0`
- `0x180076f14`
- `0x180088468`
- `0x1800892d0`
- `0x18008a478`
- `0x18008bf40`
- `0x18008c094`
- `0x18008d8c4`
- `0x18008ef20`
- `0x18008f200`
- `0x180091e70`
- `0x1800921e8`
- `0x180092224`

## import_xrefs

- `ext-ms-win-dx-dxdbhelper-l1-1-0!__imp_QueryUserGlobalSettings` at `0x1800657fb`
- `ext-ms-win-dx-dxdbhelper-l1-1-0!__imp_QueryUserGlobalSettings` at `0x1800657fb`

## string_xrefs

- `0x180065aaf`: `SuperResExt.dll`
- `0x180065ac9`: `SuperResExt.dll`
- `0x180065bc6`: `SuperResExt.dll`
- `0x180065be0`: `SuperResExt.dll`
- `0x1800658e8`: `onecoreuap\windows\directx\dxg\dxgi\dll\dxgi.cpp`
- `0x180065955`: `onecoreuap\windows\directx\dxg\dxgi\dll\dxgi.cpp`
- `0x180065b0d`: `onecoreuap\windows\directx\dxg\dxgi\dll\dxgi.cpp`
- `0x180065805`: `Failed to query effects config`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CModule::InitPresentEffectsPackageVersion(CModule *this)
{
  int UserGlobalSettings; // eax
  CModule *v3; // rcx
  bool IsSelfhostModeEnabled; // bl
  bool *v5; // r9
  int AutoSRPackageInfo; // eax
  char IsEnabled; // al
  bool *v8; // r9
  struct PACKAGE_VERSION *v9; // r8
  int v10; // eax
  wil::details::in1diag3 *v11; // rcx
  __int64 v12; // rdx
  __int16 v13; // bx
  CModule *v14; // rcx
  __int64 v15; // rcx
  _QWORD *v16; // rax
  __int64 v17; // rcx
  _QWORD *v18; // rbx
  _BYTE *v19; // rbx
  const char *v20; // rcx
  int ExtensionProperties; // eax
  __int64 v22; // rcx
  _QWORD *v23; // rax
  __int64 v24; // rcx
  _QWORD *v25; // rbx
  _BYTE *v26; // rbx
  int Size; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v28[2]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD Src[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v30; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v31; // [rsp+58h] [rbp-A8h]
  char v32[272]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_SelfhostMode>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_SelfhostMode>::GetImpl'::`2'::impl)
    && !*((_BYTE *)this + 716) )
  {
    LODWORD(v28[0]) = 0;
    UserGlobalSettings = QueryUserGlobalSettings(19, 0, v28);
    if ( UserGlobalSettings < 0 )
      CModule::RecordJournalImpl(v3, UserGlobalSettings, "Failed to query effects config");
    HIDWORD(v28[0]) = v28[0];
    *((_BYTE *)this + 716) = 1;
    *(_DWORD *)((char *)this + 717) = *(_DWORD *)((char *)v28 + 1);
    *(_WORD *)((char *)this + 721) = *(_WORD *)((char *)v28 + 5);
    *((_BYTE *)this + 723) = HIBYTE(v28[0]);
  }
  if ( !*((_BYTE *)this + 700) )
  {
    if ( CModule::IsPresentEffectsBlocked(this) )
    {
      *((_BYTE *)this + 700) = 1;
      *((_QWORD *)this + 88) = 0;
      return;
    }
    CModule::InitPresentEffectsDeviceApplicability(this);
    if ( !(unsigned __int8)CModule::IsPresentEffectsDeviceApplicable(this) )
      goto LABEL_60;
    v28[0] = 260;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl'::`2'::impl) )
    {
      if ( (int)FindPackagePathAndInfo(
                  L"Microsoft.AutoSuperResolution_8wekyb3d8bbwe",
                  0,
                  0,
                  (struct PACKAGE_VERSION *)this + 88) < 0 )
        FindPackagePathAndInfo(
          L"Microsoft.TestIntegration-43457064_p8ycr9r4f0wh0",
          0,
          0,
          (struct PACKAGE_VERSION *)this + 88);
      goto LABEL_30;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_2604>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_2604>::GetImpl'::`2'::impl) )
    {
      IsSelfhostModeEnabled = CModule::IsSelfhostModeEnabled(this);
      AutoSRPackageInfo = FindAutoSRPackageInfo(v32, v28, (struct PACKAGE_VERSION *)this + 88, v5);
      if ( AutoSRPackageInfo < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xC6E,
          (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\dll\\dxgi.cpp",
          (const char *)(unsigned int)AutoSRPackageInfo,
          Size);
      *((_BYTE *)this + 712) = IsSelfhostModeEnabled;
    }
    else
    {
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_2603>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_2603>::GetImpl'::`2'::impl);
      v9 = (struct PACKAGE_VERSION *)((char *)this + 704);
      if ( IsEnabled )
      {
        v10 = FindAutoSRPackageInfo(v32, v28, v9, v8);
        v11 = retaddr;
        if ( v10 >= 0 )
          goto LABEL_21;
        v12 = 3188;
      }
      else
      {
        v10 = FindAutoSRPackageInfo(0, 0, v9, v8);
        v11 = retaddr;
        if ( v10 >= 0 )
          goto LABEL_21;
        v12 = 3192;
      }
      wil::details::in1diag3::_Log_Hr(
        v11,
        (void *)v12,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\dll\\dxgi.cpp",
        (const char *)(unsigned int)v10,
        Size);
    }
LABEL_21:
    v13 = *((_WORD *)this + 355);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_SelfhostMode>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_SelfhostMode>::GetImpl'::`2'::impl) )
    {
      if ( !CModule::IsSelfhostModeEnabled(this) && !v13 )
      {
LABEL_27:
        *((_QWORD *)this + 88) = 0;
        CModule::RecordJournalImpl(v14, 0, "Package version < 1.0 blocked");
      }
    }
    else if ( !v13 && (*((_BYTE *)this + 720) & 0x10) == 0 )
    {
      goto LABEL_27;
    }
LABEL_30:
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_2603>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_2603>::GetImpl'::`2'::impl) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_2604>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_2604>::GetImpl'::`2'::impl) )
      {
        std::string::string(Src, v32);
        v22 = v30;
        if ( v31 == v30 )
        {
          std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(
            Src,
            1u);
        }
        else
        {
          ++v30;
          v23 = Src;
          if ( v31 > 0xF )
            v23 = (_QWORD *)Src[0];
          *(_WORD *)((char *)v23 + v22) = 92;
        }
        v24 = v30;
        if ( v31 - v30 < 0xF )
        {
          std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(
            Src,
            0xFu);
        }
        else
        {
          v30 += 15;
          v25 = Src;
          if ( v31 > 0xF )
            v25 = (_QWORD *)Src[0];
          v26 = (char *)v25 + v24;
          memmove_0(v26, "SuperResExt.dll", 0xFu);
          v26[15] = 0;
        }
        std::string::operator=((char *)this + 728, Src);
        goto LABEL_59;
      }
      if ( !*((_BYTE *)this + 760) )
      {
        std::string::string(Src, v32);
        v15 = v30;
        if ( v31 == v30 )
        {
          std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(
            Src,
            1u);
        }
        else
        {
          ++v30;
          v16 = Src;
          if ( v31 > 0xF )
            v16 = (_QWORD *)Src[0];
          *(_WORD *)((char *)v16 + v15) = 92;
        }
        v17 = v30;
        if ( v31 - v30 < 0xF )
        {
          std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(
            Src,
            0xFu);
        }
        else
        {
          v30 += 15;
          v18 = Src;
          if ( v31 > 0xF )
            v18 = (_QWORD *)Src[0];
          v19 = (char *)v18 + v17;
          memmove_0(v19, "SuperResExt.dll", 0xFu);
          v19[15] = 0;
        }
        LODWORD(v28[0]) = 0;
        v20 = (const char *)Src;
        if ( v31 > 0xF )
          v20 = (const char *)Src[0];
        ExtensionProperties = GetExtensionProperties(v20, (struct DIRECTSR_EXT_PROPS *)v28);
        if ( ExtensionProperties < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xCAC,
            (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\dll\\dxgi.cpp",
            (const char *)(unsigned int)ExtensionProperties,
            Size);
        *((_DWORD *)this + 191) = v28[0];
        *((_BYTE *)this + 760) = 1;
LABEL_59:
        std::string::~string(Src);
      }
    }
LABEL_60:
    *((_BYTE *)this + 700) = 1;
  }
}

```

## disassembly

```asm
0x18006579c  mov     [rsp-8+arg_8], rbx
0x1800657a1  mov     [rsp-8+arg_10], rsi
0x1800657a6  push    rbp
0x1800657a7  push    rdi
0x1800657a8  push    r15
0x1800657aa  lea     rbp, [rsp-80h]
0x1800657af  sub     rsp, 180h
0x1800657b6  mov     rax, cs:__security_cookie
0x1800657bd  xor     rax, rsp
0x1800657c0  mov     [rbp+90h+var_20], rax
0x1800657c4  mov     rdi, rcx
0x1800657c7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoSR_SelfhostMode@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_SelfhostMode@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_SelfhostMode> `wil::Feature<__WilFeatureTraits_Feature_AutoSR_SelfhostMode>::GetImpl(void)'::`2'::impl
0x1800657ce  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_SelfhostMode@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_SelfhostMode>::__private_IsEnabled(void)
0x1800657d3  mov     r15d, 1
0x1800657d9  test    al, al
0x1800657db  jnz     short loc_180065842
0x1800657dd  cmp     [rdi+2CCh], al
0x1800657e3  jnz     short loc_180065842
0x1800657e5  mov     dword ptr [rsp+190h+var_160], 0
0x1800657ed  lea     r9d, [r15+3]
0x1800657f1  lea     r8, [rsp+190h+var_160]
0x1800657f6  xor     edx, edx
0x1800657f8  lea     ecx, [rdx+13h]
0x1800657fb  call    cs:__imp_QueryUserGlobalSettings
0x180065801  test    eax, eax
0x180065803  jns     short loc_180065813
0x180065805  lea     r8, aFailedToQueryE; "Failed to query effects config"
0x18006580c  mov     edx, eax; unsigned int
0x18006580e  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x180065813  mov     eax, dword ptr [rsp+190h+var_160]
0x180065817  mov     dword ptr [rsp+190h+var_160+4], eax
0x18006581b  mov     [rdi+2CCh], r15b
0x180065822  mov     eax, dword ptr [rsp+190h+var_160+1]
0x180065826  mov     [rdi+2CDh], eax
0x18006582c  movzx   eax, word ptr [rsp+190h+var_160+5]
0x180065831  mov     [rdi+2D1h], ax
0x180065838  mov     al, byte ptr [rsp+190h+var_160+7]
0x18006583c  mov     [rdi+2D3h], al
0x180065842  cmp     byte ptr [rdi+2BCh], 0
0x180065849  jnz     loc_180065C17
0x18006584f  mov     rcx, rdi; this
0x180065852  call    ?IsPresentEffectsBlocked@CModule@@QEAA_NXZ; CModule::IsPresentEffectsBlocked(void)
0x180065857  test    al, al
0x180065859  jz      short loc_180065870
0x18006585b  mov     [rdi+2BCh], r15b
0x180065862  xor     eax, eax
0x180065864  mov     [rdi+2C0h], rax
0x18006586b  jmp     loc_180065C17
0x180065870  mov     rcx, rdi; this
0x180065873  call    ?InitPresentEffectsDeviceApplicability@CModule@@QEAAXXZ; CModule::InitPresentEffectsDeviceApplicability(void)
0x180065878  mov     edx, 2
0x18006587d  mov     rcx, rdi
0x180065880  call    ?IsPresentEffectsDeviceApplicable@CModule@@QEAA_NW4DXGI_EFFECT_TYPE@@@Z; CModule::IsPresentEffectsDeviceApplicable(DXGI_EFFECT_TYPE)
0x180065885  test    al, al
0x180065887  jz      loc_180065C10
0x18006588d  mov     [rsp+190h+var_160], 104h
0x180065896  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoSR_v2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_v2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2> `wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl(void)'::`2'::impl
0x18006589d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_v2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(void)
0x1800658a2  test    al, al
0x1800658a4  jz      loc_1800659B6
0x1800658aa  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoSR_2604@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_2604@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_2604> `wil::Feature<__WilFeatureTraits_Feature_AutoSR_2604>::GetImpl(void)'::`2'::impl
0x1800658b1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_2604@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_2604>::__private_IsEnabled(void)
0x1800658b6  test    al, al
0x1800658b8  jz      short loc_180065901
0x1800658ba  mov     rcx, rdi; this
0x1800658bd  call    ?IsSelfhostModeEnabled@CModule@@QEAA_NXZ; CModule::IsSelfhostModeEnabled(void)
0x1800658c2  mov     bl, al
0x1800658c4  lea     r8, [rdi+2C0h]; struct PACKAGE_VERSION *
0x1800658cb  lea     rdx, [rsp+190h+var_160]; unsigned __int64 *
0x1800658d0  lea     rcx, [rsp+190h+var_130]; char *
0x1800658d5  call    ?FindAutoSRPackageInfo@@YAJPEADPEA_KPEAUPACKAGE_VERSION@@PEA_N@Z; FindAutoSRPackageInfo(char *,unsigned __int64 *,PACKAGE_VERSION *,bool *)
0x1800658da  mov     rcx, [rbp+98h]; this
0x1800658e1  test    eax, eax
0x1800658e3  jns     short loc_1800658F9
0x1800658e5  mov     r9d, eax; char *
0x1800658e8  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x1800658ef  mov     edx, 0C6Eh; void *
0x1800658f4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800658f9  mov     [rdi+2C8h], bl
0x1800658ff  jmp     short loc_180065961
0x180065901  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoSR_2603@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_2603@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_2603> `wil::Feature<__WilFeatureTraits_Feature_AutoSR_2603>::GetImpl(void)'::`2'::impl
0x180065908  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_2603@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_2603>::__private_IsEnabled(void)
0x18006590d  lea     r8, [rdi+2C0h]; struct PACKAGE_VERSION *
0x180065914  test    al, al
0x180065916  jz      short loc_180065939
0x180065918  lea     rdx, [rsp+190h+var_160]; unsigned __int64 *
0x18006591d  lea     rcx, [rsp+190h+var_130]; char *
0x180065922  call    ?FindAutoSRPackageInfo@@YAJPEADPEA_KPEAUPACKAGE_VERSION@@PEA_N@Z; FindAutoSRPackageInfo(char *,unsigned __int64 *,PACKAGE_VERSION *,bool *)
0x180065927  mov     rcx, [rbp+98h]
0x18006592e  test    eax, eax
0x180065930  jns     short loc_180065961
0x180065932  mov     edx, 0C74h
0x180065937  jmp     short loc_180065952
0x180065939  xor     edx, edx; unsigned __int64 *
0x18006593b  xor     ecx, ecx; char *
0x18006593d  call    ?FindAutoSRPackageInfo@@YAJPEADPEA_KPEAUPACKAGE_VERSION@@PEA_N@Z; FindAutoSRPackageInfo(char *,unsigned __int64 *,PACKAGE_VERSION *,bool *)
0x180065942  mov     rcx, [rbp+98h]; this
0x180065949  test    eax, eax
0x18006594b  jns     short loc_180065961
0x18006594d  mov     edx, 0C78h; void *
0x180065952  mov     r9d, eax; char *
0x180065955  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x18006595c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180065961  movzx   ebx, word ptr [rdi+2C6h]
0x180065968  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoSR_SelfhostMode@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_SelfhostMode@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_SelfhostMode> `wil::Feature<__WilFeatureTraits_Feature_AutoSR_SelfhostMode>::GetImpl(void)'::`2'::impl
0x18006596f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_SelfhostMode@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_SelfhostMode>::__private_IsEnabled(void)
0x180065974  test    al, al
0x180065976  jz      short loc_18006598C
0x180065978  mov     rcx, rdi; this
0x18006597b  call    ?IsSelfhostModeEnabled@CModule@@QEAA_NXZ; CModule::IsSelfhostModeEnabled(void)
0x180065980  test    al, al
0x180065982  jnz     short loc_1800659E9
0x180065984  cmp     bx, r15w
0x180065988  jnb     short loc_1800659E9
0x18006598a  jmp     short loc_18006599B
0x18006598c  cmp     bx, r15w
0x180065990  jnb     short loc_1800659E9
0x180065992  test    byte ptr [rdi+2D0h], 10h
0x180065999  jnz     short loc_1800659E9
0x18006599b  mov     qword ptr [rdi+2C0h], 0
0x1800659a6  lea     r8, aPackageVersion; "Package version < 1.0 blocked"
0x1800659ad  xor     edx, edx; unsigned int
0x1800659af  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x1800659b4  jmp     short loc_1800659E9
0x1800659b6  lea     rbx, [rdi+2C0h]
0x1800659bd  mov     r9, rbx; struct PACKAGE_VERSION *
0x1800659c0  xor     r8d, r8d; unsigned __int64 *
0x1800659c3  xor     edx, edx; char *
0x1800659c5  lea     rcx, packageFamilyName; "Microsoft.AutoSuperResolution_8wekyb3d8"...
0x1800659cc  call    ?FindPackagePathAndInfo@@YAJPEBGPEADPEA_KPEAUPACKAGE_VERSION@@@Z; FindPackagePathAndInfo(ushort const *,char *,unsigned __int64 *,PACKAGE_VERSION *)
0x1800659d1  test    eax, eax
0x1800659d3  jns     short loc_1800659E9
0x1800659d5  mov     r9, rbx; struct PACKAGE_VERSION *
0x1800659d8  xor     r8d, r8d; unsigned __int64 *
0x1800659db  xor     edx, edx; char *
0x1800659dd  lea     rcx, aMicrosoftTesti; "Microsoft.TestIntegration-43457064_p8yc"...
0x1800659e4  call    ?FindPackagePathAndInfo@@YAJPEBGPEADPEA_KPEAUPACKAGE_VERSION@@@Z; FindPackagePathAndInfo(ushort const *,char *,unsigned __int64 *,PACKAGE_VERSION *)
0x1800659e9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoSR_2603@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_2603@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_2603> `wil::Feature<__WilFeatureTraits_Feature_AutoSR_2603>::GetImpl(void)'::`2'::impl
0x1800659f0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_2603@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_2603>::__private_IsEnabled(void)
0x1800659f5  test    al, al
0x1800659f7  jz      loc_180065C10
0x1800659fd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoSR_2604@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_2604@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_2604> `wil::Feature<__WilFeatureTraits_Feature_AutoSR_2604>::GetImpl(void)'::`2'::impl
0x180065a04  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_2604@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_2604>::__private_IsEnabled(void)
0x180065a09  test    al, al
0x180065a0b  jnz     loc_180065B34
0x180065a11  cmp     [rdi+2F8h], al
0x180065a17  jnz     loc_180065C10
0x180065a1d  lea     rdx, [rsp+190h+var_130]
0x180065a22  lea     rcx, [rsp+190h+Src]
0x180065a27  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180065a2c  nop
0x180065a2d  mov     rcx, [rsp+190h+var_140]
0x180065a32  mov     rax, [rsp+190h+var_138]
0x180065a37  sub     rax, rcx
0x180065a3a  mov     esi, 0Fh
0x180065a3f  cmp     rax, r15
0x180065a42  jb      short loc_180065A65
0x180065a44  lea     rax, [rcx+1]
0x180065a48  mov     [rsp+190h+var_140], rax
0x180065a4d  lea     rax, [rsp+190h+Src]
0x180065a52  cmp     [rsp+190h+var_138], rsi
0x180065a57  cmova   rax, [rsp+190h+Src]
0x180065a5d  mov     word ptr [rax+rcx], 5Ch ; '\'
0x180065a63  jmp     short loc_180065A7E
0x180065a65  mov     qword ptr [rsp+190h+Size], r15; Size
0x180065a6a  lea     r9, asc_1800DD008; "\\"
0x180065a71  mov     rdx, r15
0x180065a74  lea     rcx, [rsp+190h+Src]; Src
0x180065a79  call    ??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)
0x180065a7e  mov     rcx, [rsp+190h+var_140]
0x180065a83  mov     rax, [rsp+190h+var_138]
0x180065a88  sub     rax, rcx
0x180065a8b  cmp     rax, rsi
0x180065a8e  jb      short loc_180065AC4
0x180065a90  lea     rax, [rcx+0Fh]
0x180065a94  mov     [rsp+190h+var_140], rax
0x180065a99  lea     rbx, [rsp+190h+Src]
0x180065a9e  cmp     [rsp+190h+var_138], rsi
0x180065aa3  cmova   rbx, [rsp+190h+Src]
0x180065aa9  add     rbx, rcx
0x180065aac  mov     r8, rsi; Size
0x180065aaf  lea     rdx, aSuperresextDll; "SuperResExt.dll"
0x180065ab6  mov     rcx, rbx; void *
0x180065ab9  call    memmove_0
0x180065abe  mov     byte ptr [rbx+0Fh], 0
0x180065ac2  jmp     short loc_180065ADD
0x180065ac4  mov     qword ptr [rsp+190h+Size], rsi; int
0x180065ac9  lea     r9, aSuperresextDll; "SuperResExt.dll"
0x180065ad0  mov     rdx, rsi
0x180065ad3  lea     rcx, [rsp+190h+Src]; Src
0x180065ad8  call    ??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)
0x180065add  mov     dword ptr [rsp+190h+var_160], 0
0x180065ae5  lea     rcx, [rsp+190h+Src]
0x180065aea  cmp     [rsp+190h+var_138], rsi
0x180065aef  cmova   rcx, [rsp+190h+Src]; char *
0x180065af5  lea     rdx, [rsp+190h+var_160]; struct DIRECTSR_EXT_PROPS *
0x180065afa  call    ?GetExtensionProperties@@YAJPEBDPEAUDIRECTSR_EXT_PROPS@@@Z; GetExtensionProperties(char const *,DIRECTSR_EXT_PROPS *)
0x180065aff  mov     rcx, [rbp+98h]; this
0x180065b06  test    eax, eax
0x180065b08  jns     short loc_180065B1E
0x180065b0a  mov     r9d, eax; char *
0x180065b0d  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x180065b14  mov     edx, 0CACh; void *
0x180065b19  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180065b1e  mov     eax, dword ptr [rsp+190h+var_160]
0x180065b22  mov     [rdi+2FCh], eax
0x180065b28  mov     [rdi+2F8h], r15b
0x180065b2f  jmp     loc_180065C06
0x180065b34  lea     rdx, [rsp+190h+var_130]
0x180065b39  lea     rcx, [rsp+190h+Src]
0x180065b3e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180065b43  nop
0x180065b44  mov     rcx, [rsp+190h+var_140]
0x180065b49  mov     rax, [rsp+190h+var_138]
0x180065b4e  sub     rax, rcx
0x180065b51  mov     esi, 0Fh
0x180065b56  cmp     rax, r15
0x180065b59  jb      short loc_180065B7C
0x180065b5b  lea     rax, [rcx+1]
0x180065b5f  mov     [rsp+190h+var_140], rax
0x180065b64  lea     rax, [rsp+190h+Src]
0x180065b69  cmp     [rsp+190h+var_138], rsi
0x180065b6e  cmova   rax, [rsp+190h+Src]
0x180065b74  mov     word ptr [rax+rcx], 5Ch ; '\'
0x180065b7a  jmp     short loc_180065B95
0x180065b7c  mov     qword ptr [rsp+190h+Size], r15; Size
0x180065b81  lea     r9, asc_1800DD008; "\\"
0x180065b88  mov     rdx, r15
0x180065b8b  lea     rcx, [rsp+190h+Src]; Src
0x180065b90  call    ??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)
0x180065b95  mov     rcx, [rsp+190h+var_140]
0x180065b9a  mov     rax, [rsp+190h+var_138]
0x180065b9f  sub     rax, rcx
0x180065ba2  cmp     rax, rsi
0x180065ba5  jb      short loc_180065BDB
0x180065ba7  lea     rax, [rcx+0Fh]
0x180065bab  mov     [rsp+190h+var_140], rax
0x180065bb0  lea     rbx, [rsp+190h+Src]
0x180065bb5  cmp     [rsp+190h+var_138], rsi
0x180065bba  cmova   rbx, [rsp+190h+Src]
0x180065bc0  add     rbx, rcx
0x180065bc3  mov     r8, rsi; Size
0x180065bc6  lea     rdx, aSuperresextDll; "SuperResExt.dll"
0x180065bcd  mov     rcx, rbx; void *
0x180065bd0  call    memmove_0
0x180065bd5  mov     byte ptr [rbx+0Fh], 0
0x180065bd9  jmp     short loc_180065BF4
0x180065bdb  mov     qword ptr [rsp+190h+Size], rsi; Size
0x180065be0  lea     r9, aSuperresextDll; "SuperResExt.dll"
0x180065be7  mov     rdx, rsi
0x180065bea  lea     rcx, [rsp+190h+Src]; Src
0x180065bef  call    ??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)
0x180065bf4  lea     rcx, [rdi+2D8h]
0x180065bfb  lea     rdx, [rsp+190h+Src]
0x180065c00  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180065c05  nop
0x180065c06  lea     rcx, [rsp+190h+Src]
0x180065c0b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180065c10  mov     [rdi+2BCh], r15b
0x180065c17  mov     rcx, [rbp+90h+var_20]
0x180065c1b  xor     rcx, rsp; StackCookie
0x180065c1e  call    __security_check_cookie
0x180065c23  lea     r11, [rsp+190h+var_10]
0x180065c2b  mov     rbx, [r11+28h]
0x180065c2f  mov     rsi, [r11+30h]
0x180065c33  mov     rsp, r11
0x180065c36  pop     r15
0x180065c38  pop     rdi
0x180065c39  pop     rbp
0x180065c3a  retn
```
