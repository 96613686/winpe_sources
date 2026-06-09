# DeleteProfileP(ushort const *,ushort const *)

- ea: `0x180030624`
- end: `0x180030a4c`
- name: `?DeleteProfileP@@YAJPEBG0@Z`
- size: `1064`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000b540`
- `0x18002c630`
- `0x180038a30`

## callees

- `0x1800069d0`
- `0x18000f1b0`
- `0x1800111a0`
- `0x1800128b0`
- `0x1800164e0`
- `0x18001e070`
- `0x180022140`
- `0x180023a80`
- `0x18002d2d8`
- `0x18002f89c`
- `0x18002fb04`
- `0x180030624`
- `0x180030a54`
- `0x180030b10`
- `0x180030c24`
- `0x180031754`
- `0x180031844`
- `0x18003a730`
- `0x18003f42c`
- `0x180041df4`
- `0x18004d49c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180030967`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180030967`

## string_xrefs

- `0x180030811`: `ProfileImagePath`
- `0x1800308ba`: `System\CurrentControlset\Services\ProfSvc\Parameters`
- `0x1800308f8`: `System\CurrentControlset\Services\ProfSvc\Parameters`
- `0x1800308f1`: `DeleteRetryAttempts`
- `0x1800308b3`: `DeleteRetryWait`
- `0x1800306e0`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`
- `0x18003076f`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`
- `0x1800307f6`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`
- `0x18003087e`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`
- `0x1800308d7`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`
- `0x180030915`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`
- `0x1800309e4`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`

## pseudocode

```c
__int64 __fastcall DeleteProfileP(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  unsigned int ProfileTypeFromState; // r13d
  unsigned int v5; // ebx
  int ProfileListKeyNameFromSid; // eax
  __int64 v7; // rdx
  __int64 v8; // r9
  unsigned __int16 *v9; // r14
  int DWORD; // eax
  unsigned int v11; // esi
  int v12; // eax
  __int64 v13; // rdx
  unsigned __int16 *v14; // r14
  int v15; // eax
  int v16; // eax
  void *v17; // rdx
  unsigned int v18; // r8d
  int v19; // eax
  int v20; // eax
  int v21; // ecx
  unsigned int v22; // r9d
  int v23; // eax
  int v25; // [rsp+20h] [rbp-E0h]
  int v26; // [rsp+20h] [rbp-E0h]
  bool v27; // [rsp+30h] [rbp-D0h]
  unsigned int v28; // [rsp+34h] [rbp-CCh] BYREF
  DWORD dwMilliseconds; // [rsp+38h] [rbp-C8h] BYREF
  int v30; // [rsp+3Ch] [rbp-C4h] BYREF
  unsigned int v31; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v32; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int16 *v33; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v34; // [rsp+50h] [rbp-B0h]
  __int64 v35; // [rsp+58h] [rbp-A8h]
  unsigned __int16 *v36; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v37; // [rsp+68h] [rbp-98h]
  __int64 v38; // [rsp+70h] [rbp-90h]
  _QWORD v39[3]; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v40; // [rsp+90h] [rbp-70h]
  int v41; // [rsp+94h] [rbp-6Ch]
  _QWORD v42[42]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  wil::ActivityBase<ProfileLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v42);
  v42[0] = &ProfileTelemetry::DeleteUserProfile::`vftable';
  ProfileTelemetry::DeleteUserProfile::StartActivity((ProfileTelemetry::DeleteUserProfile *)v42);
  ProfileTypeFromState = 0;
  if ( !(unsigned int)IsProfileInUse(a1) )
  {
    v33 = 0;
    v34 = 0;
    v35 = 0;
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v33);
    v34 = -1;
    v35 = -1;
    ProfileListKeyNameFromSid = GetProfileListKeyNameFromSid(a1, &v33, 0);
    v5 = ProfileListKeyNameFromSid;
    if ( ProfileListKeyNameFromSid < 0 )
    {
      v7 = 312;
LABEL_5:
      v8 = (unsigned int)ProfileListKeyNameFromSid;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\delete.cpp",
        (const char *)v8,
        v25);
LABEL_44:
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v33);
      goto LABEL_45;
    }
    v31 = 0;
    v9 = v33;
    ProfileListKeyNameFromSid = SHRegGetDWORD(HKEY_LOCAL_MACHINE, v33, L"Flags", &v31);
    v5 = ProfileListKeyNameFromSid;
    if ( ProfileListKeyNameFromSid < 0 )
    {
      v7 = 316;
      goto LABEL_5;
    }
    if ( (v31 & 8) != 0 )
    {
      v5 = -2147024891;
      v8 = 2147942405LL;
      v7 = 317;
      goto LABEL_6;
    }
    v32 = 0;
    DWORD = SHRegGetDWORD(HKEY_LOCAL_MACHINE, v9, L"State", &v32);
    if ( DWORD >= 0 )
    {
      v11 = (v32 >> 13) & 4;
      ProfileTypeFromState = GetProfileTypeFromState(v32);
      v27 = (ProfileTypeFromState & 2) != 0;
    }
    else
    {
      LOBYTE(v11) = 0;
      v27 = 0;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x144,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\delete.cpp",
        (const char *)(unsigned int)DWORD,
        v25);
    }
    v36 = 0;
    v37 = 0;
    v38 = 0;
    if ( a2 )
    {
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v36);
      v37 = -1;
      v38 = -1;
      v12 = ExpandEnvStringAlloc(0, a2, &v36);
      v5 = v12;
      if ( v12 < 0 )
      {
        v13 = 335;
LABEL_17:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v13,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\delete.cpp",
          (const char *)(unsigned int)v12,
          v25);
LABEL_43:
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v36);
        goto LABEL_44;
      }
    }
    else
    {
      v12 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::Initialize(
              &v36,
              -2147483646,
              v9,
              L"ProfileImagePath");
      v5 = v12;
      if ( v12 < 0 )
      {
        v13 = 339;
        goto LABEL_17;
      }
    }
    v5 = 0;
    v39[2] = 0;
    v41 = 0;
    v39[0] = a1;
    v14 = v36;
    v39[1] = v36;
    v40 = ProfileTypeFromState;
    v15 = SendNotification(2, v39, 0xFFFFFFFFLL, 0);
    if ( v15 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x15C,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\delete.cpp",
        (const char *)(unsigned int)v15,
        v25);
    v16 = LsaProfileDeletedHelper(a1);
    if ( v16 < 0 )
      wil::details::in1diag3::_Log_NtStatus(retaddr, v17, v18, (const char *)(unsigned int)v16, v25);
    dwMilliseconds = 0;
    v19 = SHRegGetDWORD(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlset\\Services\\ProfSvc\\Parameters",
            L"DeleteRetryWait",
            &dwMilliseconds);
    if ( v19 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x163,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\delete.cpp",
        (const char *)(unsigned int)v19,
        v25);
    v28 = 0;
    v20 = SHRegGetDWORD(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlset\\Services\\ProfSvc\\Parameters",
            L"DeleteRetryAttempts",
            &v28);
    if ( v20 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x166,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\delete.cpp",
        (const char *)(unsigned int)v20,
        v25);
    if ( v28 && dwMilliseconds )
      LOBYTE(v11) = v11 | 8;
    v21 = DeleteProfileLite(a1, v14, v11, 0);
    if ( v21 < 0 && v28 )
    {
      do
      {
        if ( v21 != -2147024864 && v21 != -2147024751 )
          break;
        Sleep(dwMilliseconds);
        if ( v28 == 1 )
          LOBYTE(v11) = v11 & 0xF7;
        v21 = DeleteProfileLite(0, v14, v11, 0);
        --v28;
      }
      while ( v28 );
      v5 = 0;
    }
    if ( (v11 & 4) == 0 )
    {
      v30 = 0;
      SHRegGetBOOLWithREGSAM(
        HKEY_LOCAL_MACHINE,
        L"Software\\Policies\\Microsoft\\Windows\\System",
        L"LeaveAppMgmtData",
        v22,
        &v30);
      v23 = DeleteOtherPerUserSetting(a1, v27, v30 != 0);
      if ( v23 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x183,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\delete.cpp",
          (const char *)(unsigned int)v23,
          v26);
    }
    wil::ActivityBase<ProfileLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v42);
    goto LABEL_43;
  }
  v5 = -2147024864;
LABEL_45:
  ProfileTelemetry::DeleteUserProfile::~DeleteUserProfile((ProfileTelemetry::DeleteUserProfile *)v42);
  return v5;
}

```

## disassembly

```asm
0x180030624  mov     [rsp-8+arg_10], rbx
0x180030629  mov     [rsp-8+arg_18], rsi
0x18003062e  push    rbp
0x18003062f  push    r12
0x180030631  push    r13
0x180030633  push    r14
0x180030635  push    r15
0x180030637  lea     rbp, [rsp-100h]
0x18003063f  sub     rsp, 200h
0x180030646  mov     rax, cs:__security_cookie
0x18003064d  xor     rax, rsp
0x180030650  mov     [rbp+120h+var_30], rax
0x180030657  mov     r12, rdx
0x18003065a  mov     r15, rcx
0x18003065d  lea     rcx, [rbp+120h+var_180]; struct wil::details::IFailureCallback *
0x180030661  call    ??0?$ActivityBase@VProfileLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ProfileLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180030666  lea     rax, ??_7DeleteUserProfile@ProfileTelemetry@@6B@; const ProfileTelemetry::DeleteUserProfile::`vftable'
0x18003066d  mov     [rbp+120h+var_180], rax
0x180030671  lea     rcx, [rbp+120h+var_180]; this
0x180030675  call    ?StartActivity@DeleteUserProfile@ProfileTelemetry@@QEAAXXZ; ProfileTelemetry::DeleteUserProfile::StartActivity(void)
0x18003067a  nop
0x18003067b  mov     rcx, r15; unsigned __int16 *
0x18003067e  call    ?IsProfileInUse@@YAHPEBG@Z; IsProfileInUse(ushort const *)
0x180030683  xor     r13d, r13d
0x180030686  test    eax, eax
0x180030688  jz      short loc_180030694
0x18003068a  mov     ebx, 80070020h
0x18003068f  jmp     loc_180030A15
0x180030694  mov     [rsp+220h+var_1D8], r13
0x180030699  mov     [rsp+220h+var_1D0], r13
0x18003069e  mov     [rsp+220h+var_1C8], r13
0x1800306a3  lea     rcx, [rsp+220h+var_1D8]
0x1800306a8  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800306ad  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800306b1  mov     [rsp+220h+var_1D0], rax
0x1800306b6  mov     [rsp+220h+var_1C8], rax
0x1800306bb  xor     r8d, r8d; int *
0x1800306be  lea     rdx, [rsp+220h+var_1D8]; unsigned __int16 **
0x1800306c3  mov     rcx, r15; lpString1
0x1800306c6  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x1800306cb  mov     ebx, eax
0x1800306cd  test    eax, eax
0x1800306cf  jns     short loc_1800306F1
0x1800306d1  mov     edx, 138h; void *
0x1800306d6  mov     r9d, eax; char *
0x1800306d9  mov     rcx, [rbp+128h]; this
0x1800306e0  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800306e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800306ec  jmp     loc_180030A0A
0x1800306f1  mov     [rsp+220h+var_1E0], r13d
0x1800306f6  lea     r9, [rsp+220h+var_1E0]; unsigned int *
0x1800306fb  lea     r8, aFlags; "Flags"
0x180030702  mov     r14, [rsp+220h+var_1D8]
0x180030707  mov     rdx, r14; unsigned __int16 *
0x18003070a  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180030711  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180030716  mov     ebx, eax
0x180030718  test    eax, eax
0x18003071a  jns     short loc_180030723
0x18003071c  mov     edx, 13Ch
0x180030721  jmp     short loc_1800306D6
0x180030723  test    byte ptr [rsp+220h+var_1E0], 8
0x180030728  jz      short loc_180030739
0x18003072a  mov     ebx, 80070005h
0x18003072f  mov     r9d, ebx
0x180030732  mov     edx, 13Dh
0x180030737  jmp     short loc_1800306D9
0x180030739  mov     [rsp+220h+var_1DC], r13d
0x18003073e  lea     r9, [rsp+220h+var_1DC]; unsigned int *
0x180030743  lea     r8, aState; "State"
0x18003074a  mov     rdx, r14; unsigned __int16 *
0x18003074d  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180030754  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180030759  mov     rcx, [rbp+128h]; this
0x180030760  test    eax, eax
0x180030762  jns     short loc_180030782
0x180030764  mov     esi, r13d
0x180030767  mov     [rsp+220h+var_1F0], r13b
0x18003076c  mov     r9d, eax; char *
0x18003076f  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x180030776  mov     edx, 144h; void *
0x18003077b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180030780  jmp     short loc_1800307A4
0x180030782  mov     ecx, [rsp+220h+var_1DC]; unsigned int
0x180030786  mov     esi, ecx
0x180030788  shr     esi, 0Dh
0x18003078b  and     esi, 4
0x18003078e  call    ?GetProfileTypeFromState@@YAKK@Z; GetProfileTypeFromState(ulong)
0x180030793  mov     r13d, eax
0x180030796  test    al, 2
0x180030798  mov     [rsp+220h+var_1F0], 1
0x18003079d  jnz     short loc_1800307A4
0x18003079f  mov     [rsp+220h+var_1F0], 0
0x1800307a4  mov     [rsp+220h+var_1C0], 0
0x1800307ad  mov     [rsp+220h+var_1B8], 0
0x1800307b6  mov     [rsp+220h+var_1B0], 0
0x1800307bf  lea     rcx, [rsp+220h+var_1C0]
0x1800307c4  test    r12, r12
0x1800307c7  jz      short loc_180030811
0x1800307c9  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800307ce  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800307d2  mov     [rsp+220h+var_1B8], rax
0x1800307d7  mov     [rsp+220h+var_1B0], rax
0x1800307dc  lea     r8, [rsp+220h+var_1C0]; unsigned __int16 **
0x1800307e1  mov     rdx, r12; unsigned __int16 *
0x1800307e4  xor     ecx, ecx; void *
0x1800307e6  call    ?ExpandEnvStringAlloc@@YAJQEAXPEBGPEAPEAG@Z; ExpandEnvStringAlloc(void * const,ushort const *,ushort * *)
0x1800307eb  mov     ebx, eax
0x1800307ed  test    eax, eax
0x1800307ef  jns     short loc_180030837
0x1800307f1  mov     edx, 14Fh; void *
0x1800307f6  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800307fd  mov     r9d, eax; char *
0x180030800  mov     rcx, [rbp+128h]; this
0x180030807  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003080c  jmp     loc_1800309FF
0x180030811  lea     r9, aProfileimagepa; "ProfileImagePath"
0x180030818  mov     r8, r14
0x18003081b  mov     r12, 0FFFFFFFF80000002h
0x180030822  mov     rdx, r12
0x180030825  call    ?Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *,ushort const *)
0x18003082a  mov     ebx, eax
0x18003082c  test    eax, eax
0x18003082e  jns     short loc_18003083E
0x180030830  mov     edx, 153h
0x180030835  jmp     short loc_1800307F6
0x180030837  mov     r12, 0FFFFFFFF80000002h
0x18003083e  xor     ebx, ebx
0x180030840  mov     [rbp+120h+var_198], rbx
0x180030844  mov     [rbp+120h+var_18C], ebx
0x180030847  mov     [rsp+220h+var_1A8], r15
0x18003084c  mov     r14, [rsp+220h+var_1C0]
0x180030851  mov     [rbp+120h+var_1A0], r14
0x180030855  mov     [rbp+120h+var_190], r13d
0x180030859  xor     r9d, r9d
0x18003085c  or      r13d, 0FFFFFFFFh
0x180030860  mov     r8d, r13d
0x180030863  lea     rdx, [rsp+220h+var_1A8]
0x180030868  lea     ecx, [rbx+2]
0x18003086b  call    ?SendNotification@@YAJW4PROF_NOTIFY_EVENT_FLAGS@@PEAUPROF_NOTIFY_PARAM@@KPEAX@Z; SendNotification(PROF_NOTIFY_EVENT_FLAGS,PROF_NOTIFY_PARAM *,ulong,void *)
0x180030870  mov     rcx, [rbp+128h]; this
0x180030877  test    eax, eax
0x180030879  jns     short loc_18003088F
0x18003087b  mov     r9d, eax; char *
0x18003087e  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x180030885  mov     edx, 15Ch; void *
0x18003088a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003088f  mov     rcx, r15; unsigned __int16 *
0x180030892  call    ?LsaProfileDeletedHelper@@YAJPEBG@Z; LsaProfileDeletedHelper(ushort const *)
0x180030897  mov     rcx, [rbp+128h]; this
0x18003089e  test    eax, eax
0x1800308a0  jns     short loc_1800308AA
0x1800308a2  mov     r9d, eax; char *
0x1800308a5  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x1800308aa  mov     [rsp+220h+dwMilliseconds], ebx
0x1800308ae  lea     r9, [rsp+220h+dwMilliseconds]; unsigned int *
0x1800308b3  lea     r8, aDeleteretrywai; "DeleteRetryWait"
0x1800308ba  lea     rdx, aSystemCurrentc_3; "System\\CurrentControlset\\Services\\Pr"...
0x1800308c1  mov     rcx, r12; HKEY
0x1800308c4  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800308c9  mov     rcx, [rbp+128h]; this
0x1800308d0  test    eax, eax
0x1800308d2  jns     short loc_1800308E8
0x1800308d4  mov     r9d, eax; char *
0x1800308d7  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800308de  mov     edx, 163h; void *
0x1800308e3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800308e8  mov     [rsp+220h+var_1EC], ebx
0x1800308ec  lea     r9, [rsp+220h+var_1EC]; unsigned int *
0x1800308f1  lea     r8, aDeleteretryatt; "DeleteRetryAttempts"
0x1800308f8  lea     rdx, aSystemCurrentc_3; "System\\CurrentControlset\\Services\\Pr"...
0x1800308ff  mov     rcx, r12; HKEY
0x180030902  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180030907  mov     rcx, [rbp+128h]; this
0x18003090e  test    eax, eax
0x180030910  jns     short loc_180030926
0x180030912  mov     r9d, eax; char *
0x180030915  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x18003091c  mov     edx, 166h; void *
0x180030921  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180030926  cmp     [rsp+220h+var_1EC], ebx
0x18003092a  jbe     short loc_180030935
0x18003092c  cmp     [rsp+220h+dwMilliseconds], ebx
0x180030930  jbe     short loc_180030935
0x180030932  or      esi, 8
0x180030935  xor     r9d, r9d
0x180030938  mov     r8d, esi
0x18003093b  mov     rdx, r14
0x18003093e  mov     rcx, r15
0x180030941  call    ?DeleteProfileLite@@YAJPEBG0W4DeleteProfileFlags@@PEAX@Z; DeleteProfileLite(ushort const *,ushort const *,DeleteProfileFlags,void *)
0x180030946  mov     ecx, eax
0x180030948  test    eax, eax
0x18003094a  jns     short loc_180030998
0x18003094c  cmp     [rsp+220h+var_1EC], ebx
0x180030950  jbe     short loc_180030998
0x180030952  mov     ebx, 80070020h
0x180030957  cmp     ecx, ebx
0x180030959  jz      short loc_180030963
0x18003095b  cmp     ecx, 80070091h
0x180030961  jnz     short loc_180030996
0x180030963  mov     ecx, [rsp+220h+dwMilliseconds]; dwMilliseconds
0x180030967  call    cs:__imp_Sleep
0x18003096d  cmp     [rsp+220h+var_1EC], 1
0x180030972  jnz     short loc_180030977
0x180030974  and     esi, 0FFFFFFF7h
0x180030977  xor     r9d, r9d
0x18003097a  mov     r8d, esi
0x18003097d  mov     rdx, r14
0x180030980  xor     ecx, ecx
0x180030982  call    ?DeleteProfileLite@@YAJPEBG0W4DeleteProfileFlags@@PEAX@Z; DeleteProfileLite(ushort const *,ushort const *,DeleteProfileFlags,void *)
0x180030987  mov     ecx, eax
0x180030989  mov     eax, [rsp+220h+var_1EC]
0x18003098d  add     eax, r13d
0x180030990  mov     [rsp+220h+var_1EC], eax
0x180030994  jnz     short loc_180030957
0x180030996  xor     ebx, ebx
0x180030998  test    sil, 4
0x18003099c  jnz     short loc_1800309F5
0x18003099e  mov     [rsp+220h+var_1E4], ebx
0x1800309a2  lea     rax, [rsp+220h+var_1E4]
0x1800309a7  mov     qword ptr [rsp+220h+var_200], rax; int
0x1800309ac  lea     r8, aLeaveappmgmtda; "LeaveAppMgmtData"
0x1800309b3  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x1800309ba  mov     rcx, r12; HKEY
0x1800309bd  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x1800309c2  cmp     [rsp+220h+var_1E4], ebx
0x1800309c6  setnz   r8b; bool
0x1800309ca  mov     dl, [rsp+220h+var_1F0]; bool
0x1800309ce  mov     rcx, r15; unsigned __int16 *
0x1800309d1  call    ?DeleteOtherPerUserSetting@@YAJPEBG_N1@Z; DeleteOtherPerUserSetting(ushort const *,bool,bool)
0x1800309d6  mov     rcx, [rbp+128h]; this
0x1800309dd  test    eax, eax
0x1800309df  jns     short loc_1800309F5
0x1800309e1  mov     r9d, eax; char *
0x1800309e4  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800309eb  mov     edx, 183h; void *
0x1800309f0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800309f5  lea     rcx, [rbp+120h+var_180]
0x1800309f9  call    ?Stop@?$ActivityBase@VProfileLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ProfileLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800309fe  nop
0x1800309ff  lea     rcx, [rsp+220h+var_1C0]
0x180030a04  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180030a09  nop
0x180030a0a  lea     rcx, [rsp+220h+var_1D8]
0x180030a0f  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180030a14  nop
0x180030a15  lea     rcx, [rbp+120h+var_180]; this
0x180030a19  call    ??1DeleteUserProfile@ProfileTelemetry@@QEAA@XZ; ProfileTelemetry::DeleteUserProfile::~DeleteUserProfile(void)
0x180030a1e  mov     eax, ebx
0x180030a20  mov     rcx, [rbp+120h+var_30]
0x180030a27  xor     rcx, rsp; StackCookie
0x180030a2a  call    __security_check_cookie
0x180030a2f  lea     r11, [rsp+220h+var_20]
0x180030a37  mov     rbx, [r11+40h]
0x180030a3b  mov     rsi, [r11+48h]
0x180030a3f  mov     rsp, r11
0x180030a42  pop     r15
0x180030a44  pop     r14
0x180030a46  pop     r13
0x180030a48  pop     r12
0x180030a4a  pop     rbp
0x180030a4b  retn
```
