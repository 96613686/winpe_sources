# RealtimeProtection::DlpEngineUtils::GetUxSettingsFromEngine(ulong *)

- ea: `0x18007bd5c`
- end: `0x18007c09c`
- name: `?GetUxSettingsFromEngine@DlpEngineUtils@RealtimeProtection@@YAJPEAK@Z`
- size: `832`
- prototype: `__int64 __fastcall(RealtimeProtection::DlpEngineUtils *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18007a790`

## callees

- `0x180028a10`
- `0x18003fa60`
- `0x180040290`
- `0x180046d10`
- `0x180079dc0`
- `0x18007bd5c`
- `0x18007cdd4`
- `0x1800809d0`
- `0x1800a7df0`
- `0x18010cb40`

## import_xrefs

- `MpClient!MpConfigGetValue` at `0x18007bea6`
- `MpClient!MpConfigGetValue` at `0x18007bea6`
- `MpClient!MpConfigSetValue` at `0x18007c01e`
- `MpClient!MpConfigSetValue` at `0x18007c01e`
- `MpClient!MpConfigClose` at `0x18007be69`
- `MpClient!MpConfigClose` at `0x18007beca`
- `MpClient!MpConfigClose` at `0x18007bff6`
- `MpClient!MpConfigClose` at `0x18007c060`
- `MpClient!MpConfigClose` at `0x18007c06f`
- `MpClient!MpConfigClose` at `0x18007be69`
- `MpClient!MpConfigClose` at `0x18007beca`
- `MpClient!MpConfigClose` at `0x18007bff6`
- `MpClient!MpConfigClose` at `0x18007c060`
- `MpClient!MpConfigClose` at `0x18007c06f`
- `MpClient!MpConfigOpen` at `0x18007be2c`
- `MpClient!MpConfigOpen` at `0x18007bee3`
- `MpClient!MpConfigOpen` at `0x18007bfb3`
- `MpClient!MpConfigOpen` at `0x18007be2c`
- `MpClient!MpConfigOpen` at `0x18007bee3`
- `MpClient!MpConfigOpen` at `0x18007bfb3`

## string_xrefs

- `0x18007bedc`: `Miscellaneous Configuration`
- `0x18007bdfc`: `No engine to query the settings. Could be by design if early in the service startup.`
- `0x18007bf48`: `DlpShowDialog: overridden by miscconfig, old value: %lu, new value: %lu.`

## pseudocode

```c
__int64 __fastcall RealtimeProtection::DlpEngineUtils::GetUxSettingsFromEngine(
        RealtimeProtection::DlpEngineUtils *this,
        struct RealtimeProtection::DlpCEngine **a2)
{
  __int64 v3; // r14
  unsigned int v4; // edi
  const wchar_t *v5; // rdx
  CommonUtil::CRefObject *v6; // rbx
  int EngineSettings; // eax
  int v8; // eax
  unsigned int v9; // ebx
  CommonUtil::CRefObject *v10; // rcx
  int v12; // eax
  int v13; // ebx
  unsigned int Value; // eax
  int v15; // eax
  int v16; // eax
  wchar_t *v17; // [rsp+30h] [rbp-30h] BYREF
  CommonUtil::CRefObject *v18; // [rsp+38h] [rbp-28h] BYREF
  CommonUtil::CRefObject *v19; // [rsp+40h] [rbp-20h] BYREF
  int v20; // [rsp+48h] [rbp-18h] BYREF
  __int64 v21; // [rsp+50h] [rbp-10h] BYREF

  *(_DWORD *)this = 0;
  v3 = 0;
  v4 = 1;
  LODWORD(v17) = 1;
  v18 = 0;
  RealtimeProtection::DlpPlugin::GetEngine((RealtimeProtection::DlpPlugin *)&v18, a2);
  v6 = v18;
  if ( v18 )
  {
    EngineSettings = RealtimeProtection::DlpCEngine::QueryEngineSettings(v18, L"MpDlpShowDialogs", (unsigned int *)&v17);
    if ( EngineSettings < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        95,
        &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
        (unsigned int)EngineSettings);
    }
    v4 = (unsigned int)v17;
  }
  else
  {
    RealtimeProtection::MpLogMessageImpl(
      (RealtimeProtection *)L"No engine to query the settings. Could be by design if early in the service startup.",
      v5);
  }
  if ( v6 )
    CommonUtil::CRefObject::Release(v6);
  if ( !v4 )
  {
    v18 = 0;
    v8 = MpConfigOpen(L"Features", &v18);
    v9 = v8;
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          96,
          &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
          (unsigned int)v8);
      v10 = v18;
      goto LABEL_16;
    }
    v20 = 0;
    v21 = 0;
    LODWORD(v17) = 8;
    if ( (int)((__int64 (__fastcall *)(CommonUtil::CRefObject *, const wchar_t *, int *, wchar_t **, __int64 *, _QWORD))MpConfigGetValue)(
                v18,
                L"MpCapability",
                &v20,
                &v17,
                &v21,
                0) < 0 )
    {
      v4 = 1;
    }
    else
    {
      v3 = v21;
      v4 = (v21 & 4) == 0;
    }
    if ( v18 )
      MpConfigClose();
  }
  v19 = 0;
  v12 = MpConfigOpen(L"Miscellaneous Configuration", &v19);
  v9 = v12;
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        97,
        &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
        (unsigned int)v12);
LABEL_28:
    v10 = v19;
LABEL_16:
    if ( v10 )
      MpConfigClose();
    return v9;
  }
  LODWORD(v17) = v4;
  if ( (int)MpConfigGetValueDword(v19, L"DlpShowDialogs", &v17, 0) < 0 )
  {
    RealtimeProtection::MpLogMessageImpl(
      (RealtimeProtection *)L"DlpShowDialog: %lu, MpCapability: 0x%I64x.",
      (const wchar_t *)v4,
      v3);
    *(_DWORD *)this = v4;
  }
  else
  {
    v13 = (int)v17;
    RealtimeProtection::MpLogMessageImpl(
      (RealtimeProtection *)L"DlpShowDialog: overridden by miscconfig, old value: %lu, new value: %lu.",
      (const wchar_t *)v4,
      (unsigned int)v17);
    *(_DWORD *)this = v13;
  }
  Value = Dlp::FeatureControl::GetValue(225);
  LODWORD(v17) = Value;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids, Value);
  v18 = 0;
  v15 = MpConfigOpen(L"Features", &v18);
  v9 = v15;
  if ( v15 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        99,
        &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
        (unsigned int)v15);
    if ( v18 )
      MpConfigClose();
    goto LABEL_28;
  }
  v16 = MpConfigSetValue(v18, L"DlpToastButtonFlags", 1, 4, &v17);
  if ( v16 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      100,
      &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
      (unsigned int)v17,
      v16);
  if ( v18 )
    MpConfigClose();
  if ( v19 )
    MpConfigClose();
  return 0;
}

```

## disassembly

```asm
0x18007bd5c  mov     [rsp-28h+arg_8], rbx
0x18007bd61  mov     [rsp-28h+arg_10], rsi
0x18007bd66  push    rbp
0x18007bd67  push    rdi
0x18007bd68  push    r12
0x18007bd6a  push    r13
0x18007bd6c  push    r14
0x18007bd6e  mov     rbp, rsp
0x18007bd71  sub     rsp, 60h
0x18007bd75  mov     rax, cs:__security_cookie
0x18007bd7c  xor     rax, rsp
0x18007bd7f  mov     [rbp+var_8], rax
0x18007bd83  mov     rsi, rcx
0x18007bd86  mov     dword ptr [rcx], 0
0x18007bd8c  xor     r14d, r14d
0x18007bd8f  lea     r12d, [r14+1]
0x18007bd93  mov     edi, r12d
0x18007bd96  mov     dword ptr [rbp+var_30], r12d
0x18007bd9a  mov     [rbp+var_28], r14
0x18007bd9e  lea     rcx, [rbp+var_28]; this
0x18007bda2  call    ?GetEngine@DlpPlugin@RealtimeProtection@@YAXPEAPEAVDlpCEngine@2@@Z; RealtimeProtection::DlpPlugin::GetEngine(RealtimeProtection::DlpCEngine * *)
0x18007bda7  lea     r13, WPP_GLOBAL_Control
0x18007bdae  mov     rbx, [rbp+var_28]
0x18007bdb2  test    rbx, rbx
0x18007bdb5  jz      short loc_18007BDFC
0x18007bdb7  lea     r8, [rbp+var_30]; unsigned int *
0x18007bdbb  lea     rdx, aMpdlpshowdialo; "MpDlpShowDialogs"
0x18007bdc2  mov     rcx, rbx; this
0x18007bdc5  call    ?QueryEngineSettings@DlpCEngine@RealtimeProtection@@AEAAJPEB_WPEAK@Z; RealtimeProtection::DlpCEngine::QueryEngineSettings(wchar_t const *,ulong *)
0x18007bdca  test    eax, eax
0x18007bdcc  jns     short loc_18007BDF7
0x18007bdce  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bdd5  cmp     rcx, r13
0x18007bdd8  jz      short loc_18007BDF7
0x18007bdda  test    [rcx+1Ch], r12b
0x18007bdde  jz      short loc_18007BDF7
0x18007bde0  lea     edx, [r14+5Fh]
0x18007bde4  mov     r9d, eax
0x18007bde7  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18007bdee  mov     rcx, [rcx+10h]
0x18007bdf2  call    WPP_SF_d
0x18007bdf7  mov     edi, dword ptr [rbp+var_30]
0x18007bdfa  jmp     short loc_18007BE08
0x18007bdfc  lea     rcx, aNoEngineToQuer; "No engine to query the settings. Could "...
0x18007be03  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x18007be08  test    rbx, rbx
0x18007be0b  jz      short loc_18007BE15
0x18007be0d  mov     rcx, rbx; this
0x18007be10  call    ?Release@CRefObject@CommonUtil@@QEBAJXZ; CommonUtil::CRefObject::Release(void)
0x18007be15  test    edi, edi
0x18007be17  jnz     loc_18007BED0
0x18007be1d  mov     [rbp+var_28], r14
0x18007be21  lea     rdx, [rbp+var_28]
0x18007be25  lea     rcx, aFeatures_0; "Features"
0x18007be2c  call    cs:__imp_MpConfigOpen
0x18007be32  mov     ebx, eax
0x18007be34  test    eax, eax
0x18007be36  jns     short loc_18007BE76
0x18007be38  mov     rcx, cs:WPP_GLOBAL_Control
0x18007be3f  cmp     rcx, r13
0x18007be42  jz      short loc_18007BE60
0x18007be44  test    [rcx+1Ch], r12b
0x18007be48  jz      short loc_18007BE60
0x18007be4a  lea     edx, [rdi+60h]
0x18007be4d  mov     r9d, eax
0x18007be50  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18007be57  mov     rcx, [rcx+10h]
0x18007be5b  call    WPP_SF_d
0x18007be60  mov     rcx, [rbp+var_28]
0x18007be64  test    rcx, rcx
0x18007be67  jz      short loc_18007BE6F
0x18007be69  call    cs:__imp_MpConfigClose
0x18007be6f  mov     eax, ebx
0x18007be71  jmp     loc_18007C077
0x18007be76  mov     [rbp+var_18], r14d
0x18007be7a  mov     [rbp+var_10], r14
0x18007be7e  mov     dword ptr [rbp+var_30], 8
0x18007be85  mov     [rsp+60h+var_38], r14
0x18007be8a  lea     rax, [rbp+var_10]
0x18007be8e  mov     [rsp+60h+var_40], rax
0x18007be93  lea     r9, [rbp+var_30]
0x18007be97  lea     r8, [rbp+var_18]
0x18007be9b  lea     rdx, aMpcapability; "MpCapability"
0x18007bea2  mov     rcx, [rbp+var_28]
0x18007bea6  call    cs:__imp_MpConfigGetValue
0x18007beac  test    eax, eax
0x18007beae  js      short loc_18007BEBE
0x18007beb0  mov     r14, [rbp+var_10]
0x18007beb4  test    r14b, 4
0x18007beb8  cmovz   edi, r12d
0x18007bebc  jmp     short loc_18007BEC1
0x18007bebe  mov     edi, r12d
0x18007bec1  mov     rcx, [rbp+var_28]
0x18007bec5  test    rcx, rcx
0x18007bec8  jz      short loc_18007BED0
0x18007beca  call    cs:__imp_MpConfigClose
0x18007bed0  mov     [rbp+var_20], 0
0x18007bed8  lea     rdx, [rbp+var_20]
0x18007bedc  lea     rcx, aMiscellaneousC_0; "Miscellaneous Configuration"
0x18007bee3  call    cs:__imp_MpConfigOpen
0x18007bee9  mov     ebx, eax
0x18007beeb  test    eax, eax
0x18007beed  jns     short loc_18007BF22
0x18007beef  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bef6  cmp     rcx, r13
0x18007bef9  jz      short loc_18007BF19
0x18007befb  test    [rcx+1Ch], r12b
0x18007beff  jz      short loc_18007BF19
0x18007bf01  mov     edx, 61h ; 'a'
0x18007bf06  mov     r9d, eax
0x18007bf09  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18007bf10  mov     rcx, [rcx+10h]
0x18007bf14  call    WPP_SF_d
0x18007bf19  mov     rcx, [rbp+var_20]
0x18007bf1d  jmp     loc_18007BE64
0x18007bf22  mov     dword ptr [rbp+var_30], edi
0x18007bf25  xor     r9d, r9d
0x18007bf28  lea     r8, [rbp+var_30]
0x18007bf2c  lea     rdx, aDlpshowdialogs; "DlpShowDialogs"
0x18007bf33  mov     rcx, [rbp+var_20]
0x18007bf37  call    MpConfigGetValueDword
0x18007bf3c  mov     edx, edi; wchar_t *
0x18007bf3e  test    eax, eax
0x18007bf40  js      short loc_18007BF58
0x18007bf42  mov     ebx, dword ptr [rbp+var_30]
0x18007bf45  mov     r8d, ebx
0x18007bf48  lea     rcx, aDlpshowdialogO; "DlpShowDialog: overridden by miscconfig"...
0x18007bf4f  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x18007bf54  mov     [rsi], ebx
0x18007bf56  jmp     short loc_18007BF69
0x18007bf58  mov     r8, r14
0x18007bf5b  lea     rcx, aDlpshowdialogL; "DlpShowDialog: %lu, MpCapability: 0x%I6"...
0x18007bf62  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x18007bf67  mov     [rsi], edi
0x18007bf69  mov     ecx, 0E1h
0x18007bf6e  call    ?GetValue@FeatureControl@Dlp@@YAIW4FeatureControlEnum@@@Z; Dlp::FeatureControl::GetValue(FeatureControlEnum)
0x18007bf73  mov     dword ptr [rbp+var_30], eax
0x18007bf76  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bf7d  cmp     rcx, r13
0x18007bf80  jz      short loc_18007BFA0
0x18007bf82  test    byte ptr [rcx+1Ch], 4
0x18007bf86  jz      short loc_18007BFA0
0x18007bf88  mov     edx, 62h ; 'b'
0x18007bf8d  mov     r9d, eax
0x18007bf90  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18007bf97  mov     rcx, [rcx+10h]
0x18007bf9b  call    WPP_SF_d
0x18007bfa0  mov     [rbp+var_28], 0
0x18007bfa8  lea     rdx, [rbp+var_28]
0x18007bfac  lea     rcx, aFeatures_0; "Features"
0x18007bfb3  call    cs:__imp_MpConfigOpen
0x18007bfb9  mov     ebx, eax
0x18007bfbb  test    eax, eax
0x18007bfbd  jns     short loc_18007C001
0x18007bfbf  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bfc6  cmp     rcx, r13
0x18007bfc9  jz      short loc_18007BFE9
0x18007bfcb  test    [rcx+1Ch], r12b
0x18007bfcf  jz      short loc_18007BFE9
0x18007bfd1  mov     edx, 63h ; 'c'
0x18007bfd6  mov     r9d, eax
0x18007bfd9  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18007bfe0  mov     rcx, [rcx+10h]
0x18007bfe4  call    WPP_SF_d
0x18007bfe9  mov     rcx, [rbp+var_28]
0x18007bfed  test    rcx, rcx
0x18007bff0  jz      loc_18007BF19
0x18007bff6  call    cs:__imp_MpConfigClose
0x18007bffc  jmp     loc_18007BF19
0x18007c001  lea     rax, [rbp+var_30]
0x18007c005  mov     [rsp+60h+var_40], rax
0x18007c00a  mov     r9d, 4
0x18007c010  mov     r8d, r12d
0x18007c013  lea     rdx, aDlptoastbutton; "DlpToastButtonFlags"
0x18007c01a  mov     rcx, [rbp+var_28]
0x18007c01e  call    cs:__imp_MpConfigSetValue
0x18007c024  test    eax, eax
0x18007c026  jns     short loc_18007C057
0x18007c028  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c02f  cmp     rcx, r13
0x18007c032  jz      short loc_18007C057
0x18007c034  test    byte ptr [rcx+1Ch], 2
0x18007c038  jz      short loc_18007C057
0x18007c03a  mov     edx, 64h ; 'd'
0x18007c03f  mov     dword ptr [rsp+60h+var_40], eax
0x18007c043  mov     r9d, dword ptr [rbp+var_30]
0x18007c047  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18007c04e  mov     rcx, [rcx+10h]
0x18007c052  call    WPP_SF_Dd
0x18007c057  mov     rcx, [rbp+var_28]
0x18007c05b  test    rcx, rcx
0x18007c05e  jz      short loc_18007C066
0x18007c060  call    cs:__imp_MpConfigClose
0x18007c066  mov     rcx, [rbp+var_20]
0x18007c06a  test    rcx, rcx
0x18007c06d  jz      short loc_18007C075
0x18007c06f  call    cs:__imp_MpConfigClose
0x18007c075  xor     eax, eax
0x18007c077  mov     rcx, [rbp+var_8]
0x18007c07b  xor     rcx, rsp; StackCookie
0x18007c07e  call    __security_check_cookie
0x18007c083  lea     r11, [rsp+60h+var_s0]
0x18007c088  mov     rbx, [r11+38h]
0x18007c08c  mov     rsi, [r11+40h]
0x18007c090  mov     rsp, r11
0x18007c093  pop     r14
0x18007c095  pop     r13
0x18007c097  pop     r12
0x18007c099  pop     rdi
0x18007c09a  pop     rbp
0x18007c09b  retn
```
