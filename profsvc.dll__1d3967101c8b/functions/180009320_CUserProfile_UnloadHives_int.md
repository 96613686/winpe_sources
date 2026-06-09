# CUserProfile::UnloadHives(int *)

- ea: `0x180009320`
- end: `0x180009682`
- name: `?UnloadHives@CUserProfile@@IEAAJPEAH@Z`
- size: `866`
- prototype: `__int64 __fastcall(CUserProfile *__hidden this, int *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b540`

## callees

- `0x1800053a0`
- `0x180008ccc`
- `0x180009320`
- `0x180009690`
- `0x180009bf0`
- `0x18000a37c`
- `0x18000a4a0`
- `0x18000a9e0`
- `0x18000aa5c`
- `0x18000aab8`
- `0x18000cb80`
- `0x180010f30`
- `0x1800111a0`
- `0x18001a634`
- `0x180026dcc`
- `0x18002d2d8`
- `0x18003a730`
- `0x18003b310`
- `0x18003f42c`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1800093c4`
- `OLEAUT32!__imp_VariantClear` at `0x180009562`
- `OLEAUT32!__imp_VariantClear` at `0x1800093c4`
- `OLEAUT32!__imp_VariantClear` at `0x180009562`

## string_xrefs

- `0x180009577`: `onecore\ds\security\gina\profile\profsvc\profreg.cpp`
- `0x18000960b`: `onecore\ds\security\gina\profile\profsvc\profreg.cpp`
- `0x180009488`: `\Registry\User\%ws`
- `0x1800093e3`: `UnmountRegHive`
- `0x1800095eb`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000963a`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18000966a`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`

## pseudocode

```c
__int64 __fastcall CUserProfile::UnloadHives(CUserProfile *this, int *a2)
{
  BOOL v4; // r14d
  const unsigned __int16 *v5; // rbx
  int v6; // eax
  unsigned int v7; // esi
  __int64 v8; // rbx
  int v9; // eax
  int v11; // eax
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // [rsp+20h] [rbp-E0h]
  int v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+20h] [rbp-E0h]
  VARIANTARG pvarg; // [rsp+40h] [rbp-C0h] BYREF
  void **v18; // [rsp+60h] [rbp-A0h] BYREF
  int v19; // [rsp+68h] [rbp-98h] BYREF
  char v20; // [rsp+6Ch] [rbp-94h]
  int v21; // [rsp+90h] [rbp-70h] BYREF
  const char *v22; // [rsp+98h] [rbp-68h]
  __int64 v23; // [rsp+A0h] [rbp-60h]
  char v24; // [rsp+A8h] [rbp-58h]
  int v25; // [rsp+B0h] [rbp-50h]
  _BYTE v26[152]; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v27; // [rsp+150h] [rbp+50h]
  int v28; // [rsp+160h] [rbp+60h]
  __int64 v29; // [rsp+168h] [rbp+68h]
  int *v30; // [rsp+170h] [rbp+70h]
  __int64 v31; // [rsp+178h] [rbp+78h] BYREF
  _QWORD v32[3]; // [rsp+180h] [rbp+80h] BYREF
  int v33; // [rsp+198h] [rbp+98h]
  int *v34; // [rsp+1A0h] [rbp+A0h]
  char v35; // [rsp+1A8h] [rbp+A8h]
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  *a2 = 0;
  if ( (*((_BYTE *)this + 8) & 4) == 0 )
  {
    v11 = UnloadUserClasses(*((const unsigned __int16 **)this + 6), (void **)this + 29);
    if ( v11 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x9BE,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)v11,
        v14);
  }
  memset(&pvarg, 0, sizeof(pvarg));
  if ( (int)GetUserStateSetting(2, qword_18007CB80, 34, 8) >= 0 )
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
  v19 = 0;
  v20 = 0;
  v24 = 0;
  v21 = 0;
  v22 = "UnmountRegHive";
  v23 = 0;
  v25 = 0;
  v27 = 0;
  memset_0(v26, 0, sizeof(v26));
  v28 = 1;
  v29 = 0;
  v30 = &v19;
  v31 = 0;
  v32[0] = 0;
  v32[1] = &v18;
  v32[2] = 0;
  v33 = 0;
  v34 = &v21;
  v35 = 0;
  v18 = &ProfileTelemetry::UnmountRegHive::`vftable';
  ProfileTelemetry::UnmountRegHive::StartActivity((ProfileTelemetry::UnmountRegHive *)&v18, v5);
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
      (int)&pvarg);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&pvarg);
    v18 = &ProfileTelemetry::UnmountRegHive::`vftable';
    wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v18);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v32);
    wil::details::shared_object<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&v31);
    wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>(&v19);
  }
  else
  {
    v8 = *(_QWORD *)&pvarg.vt;
    v9 = UnmountRegHiveFromPath(*(_QWORD *)&pvarg.vt, v4, (char *)this + 224);
    v7 = v9;
    if ( v9 >= 0 )
    {
      wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(&v18);
      if ( v8 )
        Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v8);
      v18 = &ProfileTelemetry::UnmountRegHive::`vftable';
      wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v18);
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v32);
      wil::details::shared_object<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&v31);
      wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>(&v19);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16B,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profreg.cpp",
      (const char *)(unsigned int)v9,
      (int)&pvarg);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&pvarg);
    ProfileTelemetry::UnmountRegHive::~UnmountRegHive((ProfileTelemetry::UnmountRegHive *)&v18);
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x9C7,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
    (const char *)v7,
    v15);
  v12 = CUserProfile::SaveTempHive(this, a2);
  v13 = v12;
  if ( v12 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x9C9,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
    (const char *)(unsigned int)v12,
    v16);
  return v13;
}

```

## disassembly

```asm
0x180009320  mov     [rsp-8+arg_10], rbx
0x180009325  mov     [rsp-8+arg_18], rsi
0x18000932a  push    rbp
0x18000932b  push    rdi
0x18000932c  push    r12
0x18000932e  push    r14
0x180009330  push    r15
0x180009332  lea     rbp, [rsp-0C0h]
0x18000933a  sub     rsp, 1C0h
0x180009341  mov     rax, cs:__security_cookie
0x180009348  xor     rax, rsp
0x18000934b  mov     [rbp+0E0h+var_30], rax
0x180009352  mov     r15, rdx
0x180009355  mov     rdi, rcx
0x180009358  xor     r12d, r12d
0x18000935b  mov     [rdx], r12d
0x18000935e  test    byte ptr [rcx+8], 4
0x180009362  jz      loc_1800095C9
0x180009368  xorps   xmm0, xmm0
0x18000936b  xor     eax, eax
0x18000936d  movups  xmmword ptr [rsp+1E0h+pvarg], xmm0
0x180009372  mov     qword ptr [rsp+1E0h+pvarg+10h], rax
0x180009377  mov     [rsp+1E0h+var_1A8], r12
0x18000937c  mov     [rsp+1E0h+var_1B0], r12d
0x180009381  lea     rax, [rsp+1E0h+pvarg]
0x180009386  mov     qword ptr [rsp+1E0h+var_1C0], rax; int
0x18000938b  mov     ebx, 8
0x180009390  mov     r9d, ebx
0x180009393  lea     r8d, [rbx+1Ah]
0x180009397  lea     rdx, qword_18007CB80
0x18000939e  lea     ecx, [rbx-6]
0x1800093a1  call    ?GetUserStateSetting@@YAJW4UST_COMPONENT_ID@@QEBUUSERSTATE_SETTING_DESCRIPTOR@@IIAEAVCComVariant@ATL@@PEAXW4USERSTATE_SETTING_SOURCES@@PEBG@Z; GetUserStateSetting(UST_COMPONENT_ID,USERSTATE_SETTING_DESCRIPTOR const * const,uint,uint,ATL::CComVariant &,void *,USERSTATE_SETTING_SOURCES,ushort const *)
0x1800093a6  test    eax, eax
0x1800093a8  jns     loc_18000953D
0x1800093ae  mov     eax, 0FFFh
0x1800093b3  cmp     word ptr [rsp+1E0h+pvarg], ax
0x1800093b8  jnz     short loc_1800093BF
0x1800093ba  mov     word ptr [rsp+1E0h+pvarg], bx
0x1800093bf  lea     rcx, [rsp+1E0h+pvarg]; pvarg
0x1800093c4  call    cs:__imp_VariantClear
0x1800093ca  mov     r14d, r12d
0x1800093cd  mov     rbx, [rdi+30h]
0x1800093d1  mov     [rsp+1E0h+var_178], r12d
0x1800093d6  mov     [rsp+1E0h+var_174], r12b
0x1800093db  mov     [rbp+0E0h+var_138], r12b
0x1800093df  mov     [rbp+0E0h+var_150], r12d
0x1800093e3  lea     rax, aUnmountreghive; "UnmountRegHive"
0x1800093ea  mov     [rbp+0E0h+var_148], rax
0x1800093ee  mov     [rbp+0E0h+var_140], r12
0x1800093f2  mov     [rbp+0E0h+var_130], r12d
0x1800093f6  xorps   xmm0, xmm0
0x1800093f9  movdqa  [rbp+0E0h+var_90], xmm0
0x1800093fe  xor     edx, edx; Val
0x180009400  mov     r8d, 98h; Size
0x180009406  lea     rcx, [rbp+0E0h+var_128]; void *
0x18000940a  call    memset_0
0x18000940f  mov     [rbp+0E0h+var_80], 1
0x180009416  xor     eax, eax
0x180009418  mov     [rbp+0E0h+var_78], rax
0x18000941c  lea     rax, [rsp+1E0h+var_178]
0x180009421  mov     [rbp+0E0h+var_70], rax
0x180009425  mov     [rbp+0E0h+var_68], r12
0x180009429  mov     [rbp+0E0h+var_60], r12
0x180009430  lea     rax, [rsp+1E0h+var_180]
0x180009435  mov     [rbp+0E0h+var_58], rax
0x18000943c  mov     [rbp+0E0h+var_50], r12
0x180009443  mov     [rbp+0E0h+var_48], r12d
0x18000944a  lea     rax, [rbp+0E0h+var_150]
0x18000944e  mov     [rbp+0E0h+var_40], rax
0x180009455  mov     [rbp+0E0h+var_38], r12b
0x18000945c  lea     rax, ??_7UnmountRegHive@ProfileTelemetry@@6B@; const ProfileTelemetry::UnmountRegHive::`vftable'
0x180009463  mov     [rsp+1E0h+var_180], rax
0x180009468  mov     rdx, rbx; unsigned __int16 *
0x18000946b  lea     rcx, [rsp+1E0h+var_180]; this
0x180009470  call    ?StartActivity@UnmountRegHive@ProfileTelemetry@@QEAAXPEBG@Z; ProfileTelemetry::UnmountRegHive::StartActivity(ushort const *)
0x180009475  nop
0x180009476  mov     qword ptr [rsp+1E0h+pvarg], r12
0x18000947b  mov     qword ptr [rsp+1E0h+pvarg+8], r12
0x180009480  mov     qword ptr [rsp+1E0h+pvarg+10h], r12
0x180009485  mov     r8, rbx
0x180009488  lea     rdx, aRegistryUserWs; "\\Registry\\User\\%ws"
0x18000948f  lea     rcx, [rsp+1E0h+pvarg]
0x180009494  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180009499  mov     esi, eax
0x18000949b  test    eax, eax
0x18000949d  js      loc_18000956D
0x1800094a3  lea     r8, [rdi+0E0h]
0x1800094aa  mov     edx, r14d
0x1800094ad  mov     rbx, qword ptr [rsp+1E0h+pvarg]
0x1800094b2  mov     rcx, rbx
0x1800094b5  call    ?UnmountRegHiveFromPath@@YAJPEBGW4UnloadFlags@@PEAPEAX@Z; UnmountRegHiveFromPath(ushort const *,UnloadFlags,void * *)
0x1800094ba  mov     esi, eax
0x1800094bc  test    eax, eax
0x1800094be  js      loc_180009601
0x1800094c4  lea     rcx, [rsp+1E0h+var_180]
0x1800094c9  call    ?Stop@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800094ce  test    rbx, rbx
0x1800094d1  jz      short loc_1800094DB
0x1800094d3  mov     rcx, rbx
0x1800094d6  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x1800094db  lea     rax, ??_7UnmountRegHive@ProfileTelemetry@@6B@; const ProfileTelemetry::UnmountRegHive::`vftable'
0x1800094e2  mov     [rsp+1E0h+var_180], rax
0x1800094e7  lea     rcx, [rsp+1E0h+var_180]
0x1800094ec  call    ?Destroy@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800094f1  lea     rcx, [rbp+0E0h+var_60]; this
0x1800094f8  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800094fd  lea     rcx, [rbp+0E0h+var_68]
0x180009501  call    ?reset@?$shared_object@V?$ActivityData@VProfileLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x180009506  lea     rcx, [rsp+1E0h+var_178]
0x18000950b  call    ??1?$ActivityData@VProfileLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x180009510  xor     eax, eax
0x180009512  mov     rcx, [rbp+0E0h+var_30]
0x180009519  xor     rcx, rsp; StackCookie
0x18000951c  call    __security_check_cookie
0x180009521  lea     r11, [rsp+1E0h+var_20]
0x180009529  mov     rbx, [r11+40h]
0x18000952d  mov     rsi, [r11+48h]
0x180009531  mov     rsp, r11
0x180009534  pop     r15
0x180009536  pop     r14
0x180009538  pop     r12
0x18000953a  pop     rdi
0x18000953b  pop     rbp
0x18000953c  retn
0x18000953d  mov     r14d, r12d
0x180009540  or      eax, 0FFFFFFFFh
0x180009543  cmp     ax, word ptr [rsp+1E0h+pvarg+8]
0x180009548  setz    r14b
0x18000954c  mov     eax, 0FFFh
0x180009551  cmp     word ptr [rsp+1E0h+pvarg], ax
0x180009556  jnz     short loc_18000955D
0x180009558  mov     word ptr [rsp+1E0h+pvarg], bx
0x18000955d  lea     rcx, [rsp+1E0h+pvarg]; pvarg
0x180009562  call    cs:__imp_VariantClear
0x180009568  jmp     loc_1800093CD
0x18000956d  mov     rcx, [rbp+0E8h]; this
0x180009574  mov     r9d, eax; char *
0x180009577  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000957e  mov     edx, 169h; void *
0x180009583  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009588  lea     rcx, [rsp+1E0h+pvarg]
0x18000958d  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180009592  lea     rax, ??_7UnmountRegHive@ProfileTelemetry@@6B@; const ProfileTelemetry::UnmountRegHive::`vftable'
0x180009599  mov     [rsp+1E0h+var_180], rax
0x18000959e  lea     rcx, [rsp+1E0h+var_180]
0x1800095a3  call    ?Destroy@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800095a8  lea     rcx, [rbp+0E0h+var_60]; this
0x1800095af  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800095b4  lea     rcx, [rbp+0E0h+var_68]
0x1800095b8  call    ?reset@?$shared_object@V?$ActivityData@VProfileLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x1800095bd  lea     rcx, [rsp+1E0h+var_178]
0x1800095c2  call    ??1?$ActivityData@VProfileLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800095c7  jmp     short loc_180009630
0x1800095c9  lea     rdx, [rcx+0E8h]; void **
0x1800095d0  mov     rcx, [rcx+30h]; unsigned __int16 *
0x1800095d4  call    ?UnloadUserClasses@@YAJPEBGPEAPEAX@Z; UnloadUserClasses(ushort const *,void * *)
0x1800095d9  mov     rcx, [rbp+0E8h]; this
0x1800095e0  test    eax, eax
0x1800095e2  jns     loc_180009368
0x1800095e8  mov     r9d, eax; char *
0x1800095eb  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800095f2  mov     edx, 9BEh; void *
0x1800095f7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800095fc  jmp     loc_180009368
0x180009601  mov     rcx, [rbp+0E8h]; this
0x180009608  mov     r9d, eax; char *
0x18000960b  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x180009612  mov     edx, 16Bh; void *
0x180009617  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000961c  lea     rcx, [rsp+1E0h+pvarg]
0x180009621  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180009626  lea     rcx, [rsp+1E0h+var_180]; this
0x18000962b  call    ??1UnmountRegHive@ProfileTelemetry@@QEAA@XZ; ProfileTelemetry::UnmountRegHive::~UnmountRegHive(void)
0x180009630  mov     rcx, [rbp+0E8h]; this
0x180009637  mov     r9d, esi; char *
0x18000963a  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180009641  mov     edx, 9C7h; void *
0x180009646  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000964b  mov     rdx, r15; int *
0x18000964e  mov     rcx, rdi; this
0x180009651  call    ?SaveTempHive@CUserProfile@@IEAAJPEAH@Z; CUserProfile::SaveTempHive(int *)
0x180009656  mov     ebx, eax
0x180009658  test    eax, eax
0x18000965a  jns     loc_180009510
0x180009660  mov     rcx, [rbp+0E8h]; this
0x180009667  mov     r9d, eax; char *
0x18000966a  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180009671  mov     edx, 9C9h; void *
0x180009676  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000967b  mov     eax, ebx
0x18000967d  jmp     loc_180009512
```
