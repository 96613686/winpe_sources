# CUserProfile::UnloadHives(int *)

- ea: `0x1800066cc`
- end: `0x180006a02`
- name: `?UnloadHives@CUserProfile@@IEAAJPEAH@Z`
- size: `822`
- prototype: `__int64 __fastcall(CUserProfile *__hidden this, int *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008fa0`

## callees

- `0x18000626c`
- `0x1800066cc`
- `0x180006a10`
- `0x180007450`
- `0x180007bc0`
- `0x180007c2c`
- `0x180007d40`
- `0x18000a6e0`
- `0x18000b060`
- `0x18000d030`
- `0x18000e1a0`
- `0x180013144`
- `0x180028ec8`
- `0x180030ad0`
- `0x18003bc70`
- `0x18003c870`
- `0x180040bcc`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180006770`
- `OLEAUT32!__imp_VariantClear` at `0x1800068f8`
- `OLEAUT32!__imp_VariantClear` at `0x180006770`
- `OLEAUT32!__imp_VariantClear` at `0x1800068f8`

## string_xrefs

- `0x18000683a`: `\Registry\User\%ws`
- `0x180006795`: `UnmountRegHive`
- `0x18000696b`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x1800069ba`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x1800069ea`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180006913`: `onecore\ds\security\gina\profile\profsvc\profreg.cpp`
- `0x18000698b`: `onecore\ds\security\gina\profile\profsvc\profreg.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CUserProfile::UnloadHives(CUserProfile *this, int *a2)
{
  bool v4; // si
  const unsigned __int16 *v5; // rbx
  int v6; // eax
  unsigned int v7; // ebx
  char v8; // dl
  __int64 v9; // rsi
  int v10; // eax
  const struct wil::FailureInfo *v11; // rdx
  int v13; // eax
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // [rsp+20h] [rbp-E0h]
  int v17; // [rsp+20h] [rbp-E0h]
  int v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+20h] [rbp-E0h]
  __int64 v20; // [rsp+28h] [rbp-D8h]
  VARIANTARG pvarg; // [rsp+40h] [rbp-C0h] BYREF
  void **v22; // [rsp+60h] [rbp-A0h] BYREF
  int v23; // [rsp+68h] [rbp-98h] BYREF
  char v24; // [rsp+6Ch] [rbp-94h]
  int v25; // [rsp+90h] [rbp-70h] BYREF
  const char *v26; // [rsp+98h] [rbp-68h]
  __int64 v27; // [rsp+A0h] [rbp-60h]
  char v28; // [rsp+A8h] [rbp-58h]
  int v29; // [rsp+B0h] [rbp-50h]
  _BYTE v30[152]; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v31; // [rsp+150h] [rbp+50h]
  int v32; // [rsp+160h] [rbp+60h]
  __int64 v33; // [rsp+168h] [rbp+68h]
  int *v34; // [rsp+170h] [rbp+70h]
  __int64 v35; // [rsp+178h] [rbp+78h]
  __int64 v36; // [rsp+180h] [rbp+80h]
  void ***v37; // [rsp+188h] [rbp+88h]
  __int64 v38; // [rsp+190h] [rbp+90h]
  int v39; // [rsp+198h] [rbp+98h]
  int *v40; // [rsp+1A0h] [rbp+A0h]
  char v41; // [rsp+1A8h] [rbp+A8h]
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  *a2 = 0;
  if ( (*((_BYTE *)this + 8) & 4) == 0 )
  {
    v13 = UnloadUserClasses(*((const unsigned __int16 **)this + 6), (void **)this + 29);
    if ( v13 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x9BE,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)v13,
        v16);
  }
  memset(&pvarg, 0, sizeof(pvarg));
  if ( (int)GetUserStateSetting(2u, (__int64)qword_18007FC90, 0x22u, 8, &pvarg, v20, 0, 0) >= 0 )
  {
    v4 = pvarg.iVal == 0xFFFF;
    if ( pvarg.vt == 4095 )
      pvarg.vt = 8;
    VariantClear(&pvarg);
  }
  else
  {
    if ( pvarg.vt == 4095 )
      pvarg.vt = 8;
    VariantClear(&pvarg);
    v4 = 0;
  }
  v5 = (const unsigned __int16 *)*((_QWORD *)this + 6);
  v23 = 0;
  v24 = 0;
  v28 = 0;
  v25 = 0;
  v26 = "UnmountRegHive";
  v27 = 0;
  v29 = 0;
  v31 = 0;
  memset_0(v30, 0, sizeof(v30));
  v32 = 1;
  v33 = 0;
  v34 = &v23;
  v35 = 0;
  v36 = 0;
  v37 = &v22;
  v38 = 0;
  v39 = 0;
  v40 = &v25;
  v41 = 0;
  v22 = &ProfileTelemetry::UnmountRegHive::`vftable';
  ProfileTelemetry::UnmountRegHive::StartActivity((ProfileTelemetry::UnmountRegHive *)&v22, v5);
  memset(&pvarg, 0, sizeof(pvarg));
  v6 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
         &pvarg,
         L"\\Registry\\User\\%ws",
         v5);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x169,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profreg.cpp",
      (const char *)(unsigned int)v6,
      v17);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&pvarg);
    v22 = &ProfileTelemetry::UnmountRegHive::`vftable';
    wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v22);
    wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(&v22);
  }
  else
  {
    v8 = v4;
    v9 = *(_QWORD *)&pvarg.vt;
    v10 = UnmountRegHiveFromPath(*(const unsigned __int16 **)&pvarg.vt, v8, (HANDLE *)this + 28);
    v7 = v10;
    if ( v10 >= 0 )
    {
      wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop((__int64)&v22, v11);
      if ( v9 )
        Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v9);
      v22 = &ProfileTelemetry::UnmountRegHive::`vftable';
      wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v22);
      wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(&v22);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16B,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profreg.cpp",
      (const char *)(unsigned int)v10,
      v17);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&pvarg);
    ProfileTelemetry::UnmountRegHive::~UnmountRegHive((ProfileTelemetry::UnmountRegHive *)&v22);
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x9C7,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
    (const char *)v7,
    v18);
  v14 = CUserProfile::SaveTempHive(this, a2);
  v15 = v14;
  if ( v14 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x9C9,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
    (const char *)(unsigned int)v14,
    v19);
  return v15;
}

```

## disassembly

```asm
0x1800066cc  mov     [rsp-8+arg_10], rbx
0x1800066d1  mov     [rsp-8+arg_18], rsi
0x1800066d6  push    rbp
0x1800066d7  push    rdi
0x1800066d8  push    r13
0x1800066da  push    r14
0x1800066dc  push    r15
0x1800066de  lea     rbp, [rsp-0C0h]
0x1800066e6  sub     rsp, 1C0h
0x1800066ed  mov     rax, cs:__security_cookie
0x1800066f4  xor     rax, rsp
0x1800066f7  mov     [rbp+0E0h+var_30], rax
0x1800066fe  mov     r14, rdx
0x180006701  mov     rdi, rcx
0x180006704  xor     r15d, r15d
0x180006707  mov     [rdx], r15d
0x18000670a  test    byte ptr [rcx+8], 4
0x18000670e  jz      loc_180006949
0x180006714  xorps   xmm0, xmm0
0x180006717  xor     eax, eax
0x180006719  movups  xmmword ptr [rsp+1E0h+pvarg], xmm0
0x18000671e  mov     qword ptr [rsp+1E0h+pvarg+10h], rax
0x180006723  mov     [rsp+1E0h+var_1A8], r15
0x180006728  mov     [rsp+1E0h+var_1B0], r15d
0x18000672d  lea     rax, [rsp+1E0h+pvarg]
0x180006732  mov     qword ptr [rsp+1E0h+var_1C0], rax; int
0x180006737  mov     ebx, 8
0x18000673c  mov     r9d, ebx
0x18000673f  lea     r8d, [rbx+1Ah]
0x180006743  lea     rdx, qword_18007FC90
0x18000674a  lea     ecx, [rbx-6]
0x18000674d  call    ?GetUserStateSetting@@YAJW4UST_COMPONENT_ID@@QEBUUSERSTATE_SETTING_DESCRIPTOR@@IIAEAVCComVariant@ATL@@PEAXW4USERSTATE_SETTING_SOURCES@@PEBG@Z; GetUserStateSetting(UST_COMPONENT_ID,USERSTATE_SETTING_DESCRIPTOR const * const,uint,uint,ATL::CComVariant &,void *,USERSTATE_SETTING_SOURCES,ushort const *)
0x180006752  test    eax, eax
0x180006754  jns     loc_1800068D3
0x18000675a  mov     eax, 0FFFh
0x18000675f  cmp     word ptr [rsp+1E0h+pvarg], ax
0x180006764  jnz     short loc_18000676B
0x180006766  mov     word ptr [rsp+1E0h+pvarg], bx
0x18000676b  lea     rcx, [rsp+1E0h+pvarg]; pvarg
0x180006770  call    cs:__imp_VariantClear
0x180006777  nop     dword ptr [rax+rax+00h]
0x18000677c  mov     esi, r15d
0x18000677f  mov     rbx, [rdi+30h]
0x180006783  mov     [rsp+1E0h+var_178], r15d
0x180006788  mov     [rsp+1E0h+var_174], r15b
0x18000678d  mov     [rbp+0E0h+var_138], r15b
0x180006791  mov     [rbp+0E0h+var_150], r15d
0x180006795  lea     rax, aUnmountreghive; "UnmountRegHive"
0x18000679c  mov     [rbp+0E0h+var_148], rax
0x1800067a0  mov     [rbp+0E0h+var_140], r15
0x1800067a4  mov     [rbp+0E0h+var_130], r15d
0x1800067a8  xorps   xmm0, xmm0
0x1800067ab  movdqa  [rbp+0E0h+var_90], xmm0
0x1800067b0  xor     edx, edx; Val
0x1800067b2  mov     r8d, 98h; Size
0x1800067b8  lea     rcx, [rbp+0E0h+var_128]; void *
0x1800067bc  call    memset_0
0x1800067c1  mov     [rbp+0E0h+var_80], 1
0x1800067c8  xor     eax, eax
0x1800067ca  mov     [rbp+0E0h+var_78], rax
0x1800067ce  lea     rax, [rsp+1E0h+var_178]
0x1800067d3  mov     [rbp+0E0h+var_70], rax
0x1800067d7  mov     [rbp+0E0h+var_68], r15
0x1800067db  mov     [rbp+0E0h+var_60], r15
0x1800067e2  lea     rax, [rsp+1E0h+var_180]
0x1800067e7  mov     [rbp+0E0h+var_58], rax
0x1800067ee  mov     [rbp+0E0h+var_50], r15
0x1800067f5  mov     [rbp+0E0h+var_48], r15d
0x1800067fc  lea     rax, [rbp+0E0h+var_150]
0x180006800  mov     [rbp+0E0h+var_40], rax
0x180006807  mov     [rbp+0E0h+var_38], r15b
0x18000680e  lea     r13, ??_7UnmountRegHive@ProfileTelemetry@@6B@; const ProfileTelemetry::UnmountRegHive::`vftable'
0x180006815  mov     [rsp+1E0h+var_180], r13
0x18000681a  mov     rdx, rbx; unsigned __int16 *
0x18000681d  lea     rcx, [rsp+1E0h+var_180]; this
0x180006822  call    ?StartActivity@UnmountRegHive@ProfileTelemetry@@QEAAXPEBG@Z; ProfileTelemetry::UnmountRegHive::StartActivity(ushort const *)
0x180006827  nop
0x180006828  mov     qword ptr [rsp+1E0h+pvarg], r15
0x18000682d  mov     qword ptr [rsp+1E0h+pvarg+8], r15
0x180006832  mov     qword ptr [rsp+1E0h+pvarg+10h], r15
0x180006837  mov     r8, rbx
0x18000683a  lea     rdx, aRegistryUserWs; "\\Registry\\User\\%ws"
0x180006841  lea     rcx, [rsp+1E0h+pvarg]
0x180006846  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18000684b  mov     ebx, eax
0x18000684d  test    eax, eax
0x18000684f  js      loc_180006909
0x180006855  lea     r8, [rdi+0E0h]
0x18000685c  mov     edx, esi
0x18000685e  mov     rsi, qword ptr [rsp+1E0h+pvarg]
0x180006863  mov     rcx, rsi
0x180006866  call    ?UnmountRegHiveFromPath@@YAJPEBGW4UnloadFlags@@PEAPEAX@Z; UnmountRegHiveFromPath(ushort const *,UnloadFlags,void * *)
0x18000686b  mov     ebx, eax
0x18000686d  test    eax, eax
0x18000686f  js      loc_180006981
0x180006875  lea     rcx, [rsp+1E0h+var_180]
0x18000687a  call    ?Stop@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000687f  test    rsi, rsi
0x180006882  jz      short loc_18000688C
0x180006884  mov     rcx, rsi
0x180006887  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x18000688c  mov     [rsp+1E0h+var_180], r13
0x180006891  lea     rcx, [rsp+1E0h+var_180]
0x180006896  call    ?Destroy@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000689b  lea     rcx, [rsp+1E0h+var_180]
0x1800068a0  call    ??1?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800068a5  xor     eax, eax
0x1800068a7  mov     rcx, [rbp+0E0h+var_30]
0x1800068ae  xor     rcx, rsp; StackCookie
0x1800068b1  call    __security_check_cookie
0x1800068b6  lea     r11, [rsp+1E0h+var_20]
0x1800068be  mov     rbx, [r11+40h]
0x1800068c2  mov     rsi, [r11+48h]
0x1800068c6  mov     rsp, r11
0x1800068c9  pop     r15
0x1800068cb  pop     r14
0x1800068cd  pop     r13
0x1800068cf  pop     rdi
0x1800068d0  pop     rbp
0x1800068d1  retn
0x1800068d3  mov     esi, r15d
0x1800068d6  or      eax, 0FFFFFFFFh
0x1800068d9  cmp     ax, word ptr [rsp+1E0h+pvarg+8]
0x1800068de  setz    sil
0x1800068e2  mov     eax, 0FFFh
0x1800068e7  cmp     word ptr [rsp+1E0h+pvarg], ax
0x1800068ec  jnz     short loc_1800068F3
0x1800068ee  mov     word ptr [rsp+1E0h+pvarg], bx
0x1800068f3  lea     rcx, [rsp+1E0h+pvarg]; pvarg
0x1800068f8  call    cs:__imp_VariantClear
0x1800068ff  nop     dword ptr [rax+rax+00h]
0x180006904  jmp     loc_18000677F
0x180006909  mov     rcx, [rbp+0E8h]; this
0x180006910  mov     r9d, eax; char *
0x180006913  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000691a  mov     edx, 169h; void *
0x18000691f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006924  lea     rcx, [rsp+1E0h+pvarg]
0x180006929  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18000692e  mov     [rsp+1E0h+var_180], r13
0x180006933  lea     rcx, [rsp+1E0h+var_180]
0x180006938  call    ?Destroy@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000693d  lea     rcx, [rsp+1E0h+var_180]
0x180006942  call    ??1?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180006947  jmp     short loc_1800069B0
0x180006949  lea     rdx, [rcx+0E8h]; void **
0x180006950  mov     rcx, [rcx+30h]; unsigned __int16 *
0x180006954  call    ?UnloadUserClasses@@YAJPEBGPEAPEAX@Z; UnloadUserClasses(ushort const *,void * *)
0x180006959  mov     rcx, [rbp+0E8h]; this
0x180006960  test    eax, eax
0x180006962  jns     loc_180006714
0x180006968  mov     r9d, eax; char *
0x18000696b  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180006972  mov     edx, 9BEh; void *
0x180006977  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000697c  jmp     loc_180006714
0x180006981  mov     rcx, [rbp+0E8h]; this
0x180006988  mov     r9d, eax; char *
0x18000698b  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x180006992  mov     edx, 16Bh; void *
0x180006997  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000699c  lea     rcx, [rsp+1E0h+pvarg]
0x1800069a1  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800069a6  lea     rcx, [rsp+1E0h+var_180]; this
0x1800069ab  call    ??1UnmountRegHive@ProfileTelemetry@@QEAA@XZ; ProfileTelemetry::UnmountRegHive::~UnmountRegHive(void)
0x1800069b0  mov     rcx, [rbp+0E8h]; this
0x1800069b7  mov     r9d, ebx; char *
0x1800069ba  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800069c1  mov     edx, 9C7h; void *
0x1800069c6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800069cb  mov     rdx, r14; int *
0x1800069ce  mov     rcx, rdi; this
0x1800069d1  call    ?SaveTempHive@CUserProfile@@IEAAJPEAH@Z; CUserProfile::SaveTempHive(int *)
0x1800069d6  mov     ebx, eax
0x1800069d8  test    eax, eax
0x1800069da  jns     loc_1800068A5
0x1800069e0  mov     rcx, [rbp+0E8h]; this
0x1800069e7  mov     r9d, eax; char *
0x1800069ea  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800069f1  mov     edx, 9C9h; void *
0x1800069f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800069fb  mov     eax, ebx
0x1800069fd  jmp     loc_1800068A7
```
