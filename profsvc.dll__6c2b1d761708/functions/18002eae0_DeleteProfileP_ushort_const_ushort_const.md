# DeleteProfileP(ushort const *,ushort const *)

- ea: `0x18002eae0`
- end: `0x18002ef0f`
- name: `?DeleteProfileP@@YAJPEBG0@Z`
- size: `1071`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180008fa0`
- `0x180037bbc`
- `0x18004e3d0`

## callees

- `0x18000d2c0`
- `0x18000e1a0`
- `0x180010b10`
- `0x180014e90`
- `0x180022130`
- `0x180022440`
- `0x180025200`
- `0x180026390`
- `0x18002d508`
- `0x18002e0c4`
- `0x18002e0f0`
- `0x18002e908`
- `0x18002ea20`
- `0x18002eae0`
- `0x18002f6e8`
- `0x180030008`
- `0x180030ad0`
- `0x18003bc70`
- `0x180040bcc`
- `0x1800437d8`
- `0x1800507b0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002ee23`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002ee23`

## string_xrefs

- `0x18002eccd`: `ProfileImagePath`
- `0x18002eb9c`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`
- `0x18002ec2b`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`
- `0x18002ecb2`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`
- `0x18002ed3a`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`
- `0x18002ed93`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`
- `0x18002edd1`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`
- `0x18002eea6`: `onecore\ds\security\gina\profile\profsvc\delete.cpp`
- `0x18002ed76`: `System\CurrentControlset\Services\ProfSvc\Parameters`
- `0x18002edb4`: `System\CurrentControlset\Services\ProfSvc\Parameters`
- `0x18002edad`: `DeleteRetryAttempts`
- `0x18002ed6f`: `DeleteRetryWait`

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
    v15 = SendNotification(2, v39, 0xFFFFFFFFLL);
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
0x18002eae0  mov     [rsp-8+arg_10], rbx
0x18002eae5  mov     [rsp-8+arg_18], rsi
0x18002eaea  push    rbp
0x18002eaeb  push    r12
0x18002eaed  push    r13
0x18002eaef  push    r14
0x18002eaf1  push    r15
0x18002eaf3  lea     rbp, [rsp-100h]
0x18002eafb  sub     rsp, 200h
0x18002eb02  mov     rax, cs:__security_cookie
0x18002eb09  xor     rax, rsp
0x18002eb0c  mov     [rbp+120h+var_30], rax
0x18002eb13  mov     r12, rdx
0x18002eb16  mov     r15, rcx
0x18002eb19  lea     rcx, [rbp+120h+var_180]; struct wil::details::IFailureCallback *
0x18002eb1d  call    ??0?$ActivityBase@VProfileLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ProfileLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ProfileLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18002eb22  lea     rax, ??_7DeleteUserProfile@ProfileTelemetry@@6B@; const ProfileTelemetry::DeleteUserProfile::`vftable'
0x18002eb29  mov     [rbp+120h+var_180], rax
0x18002eb2d  lea     rcx, [rbp+120h+var_180]; this
0x18002eb31  call    ?StartActivity@DeleteUserProfile@ProfileTelemetry@@QEAAXXZ; ProfileTelemetry::DeleteUserProfile::StartActivity(void)
0x18002eb36  nop
0x18002eb37  mov     rcx, r15; unsigned __int16 *
0x18002eb3a  call    ?IsProfileInUse@@YAHPEBG@Z; IsProfileInUse(ushort const *)
0x18002eb3f  xor     r13d, r13d
0x18002eb42  test    eax, eax
0x18002eb44  jz      short loc_18002EB50
0x18002eb46  mov     ebx, 80070020h
0x18002eb4b  jmp     loc_18002EED7
0x18002eb50  mov     [rsp+220h+var_1D8], r13
0x18002eb55  mov     [rsp+220h+var_1D0], r13
0x18002eb5a  mov     [rsp+220h+var_1C8], r13
0x18002eb5f  lea     rcx, [rsp+220h+var_1D8]
0x18002eb64  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002eb69  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002eb6d  mov     [rsp+220h+var_1D0], rax
0x18002eb72  mov     [rsp+220h+var_1C8], rax
0x18002eb77  xor     r8d, r8d; int *
0x18002eb7a  lea     rdx, [rsp+220h+var_1D8]; unsigned __int16 **
0x18002eb7f  mov     rcx, r15; lpString1
0x18002eb82  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x18002eb87  mov     ebx, eax
0x18002eb89  test    eax, eax
0x18002eb8b  jns     short loc_18002EBAD
0x18002eb8d  mov     edx, 138h; void *
0x18002eb92  mov     r9d, eax; char *
0x18002eb95  mov     rcx, [rbp+128h]; this
0x18002eb9c  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002eba3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002eba8  jmp     loc_18002EECC
0x18002ebad  mov     [rsp+220h+var_1E0], r13d
0x18002ebb2  lea     r9, [rsp+220h+var_1E0]; unsigned int *
0x18002ebb7  lea     r8, Value; "Flags"
0x18002ebbe  mov     r14, [rsp+220h+var_1D8]
0x18002ebc3  mov     rdx, r14; unsigned __int16 *
0x18002ebc6  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18002ebcd  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18002ebd2  mov     ebx, eax
0x18002ebd4  test    eax, eax
0x18002ebd6  jns     short loc_18002EBDF
0x18002ebd8  mov     edx, 13Ch
0x18002ebdd  jmp     short loc_18002EB92
0x18002ebdf  test    byte ptr [rsp+220h+var_1E0], 8
0x18002ebe4  jz      short loc_18002EBF5
0x18002ebe6  mov     ebx, 80070005h
0x18002ebeb  mov     r9d, ebx
0x18002ebee  mov     edx, 13Dh
0x18002ebf3  jmp     short loc_18002EB95
0x18002ebf5  mov     [rsp+220h+var_1DC], r13d
0x18002ebfa  lea     r9, [rsp+220h+var_1DC]; unsigned int *
0x18002ebff  lea     r8, aState; "State"
0x18002ec06  mov     rdx, r14; unsigned __int16 *
0x18002ec09  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18002ec10  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18002ec15  mov     rcx, [rbp+128h]; this
0x18002ec1c  test    eax, eax
0x18002ec1e  jns     short loc_18002EC3E
0x18002ec20  mov     esi, r13d
0x18002ec23  mov     [rsp+220h+var_1F0], r13b
0x18002ec28  mov     r9d, eax; char *
0x18002ec2b  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002ec32  mov     edx, 144h; void *
0x18002ec37  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002ec3c  jmp     short loc_18002EC60
0x18002ec3e  mov     ecx, [rsp+220h+var_1DC]; unsigned int
0x18002ec42  mov     esi, ecx
0x18002ec44  shr     esi, 0Dh
0x18002ec47  and     esi, 4
0x18002ec4a  call    ?GetProfileTypeFromState@@YAKK@Z; GetProfileTypeFromState(ulong)
0x18002ec4f  mov     r13d, eax
0x18002ec52  test    al, 2
0x18002ec54  mov     [rsp+220h+var_1F0], 1
0x18002ec59  jnz     short loc_18002EC60
0x18002ec5b  mov     [rsp+220h+var_1F0], 0
0x18002ec60  mov     [rsp+220h+var_1C0], 0
0x18002ec69  mov     [rsp+220h+var_1B8], 0
0x18002ec72  mov     [rsp+220h+var_1B0], 0
0x18002ec7b  lea     rcx, [rsp+220h+var_1C0]
0x18002ec80  test    r12, r12
0x18002ec83  jz      short loc_18002ECCD
0x18002ec85  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002ec8a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002ec8e  mov     [rsp+220h+var_1B8], rax
0x18002ec93  mov     [rsp+220h+var_1B0], rax
0x18002ec98  lea     r8, [rsp+220h+var_1C0]; unsigned __int16 **
0x18002ec9d  mov     rdx, r12; unsigned __int16 *
0x18002eca0  xor     ecx, ecx; void *
0x18002eca2  call    ?ExpandEnvStringAlloc@@YAJQEAXPEBGPEAPEAG@Z; ExpandEnvStringAlloc(void * const,ushort const *,ushort * *)
0x18002eca7  mov     ebx, eax
0x18002eca9  test    eax, eax
0x18002ecab  jns     short loc_18002ECF3
0x18002ecad  mov     edx, 14Fh; void *
0x18002ecb2  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002ecb9  mov     r9d, eax; char *
0x18002ecbc  mov     rcx, [rbp+128h]; this
0x18002ecc3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ecc8  jmp     loc_18002EEC1
0x18002eccd  lea     r9, aProfileimagepa; "ProfileImagePath"
0x18002ecd4  mov     r8, r14
0x18002ecd7  mov     r12, 0FFFFFFFF80000002h
0x18002ecde  mov     rdx, r12
0x18002ece1  call    ?Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *,ushort const *)
0x18002ece6  mov     ebx, eax
0x18002ece8  test    eax, eax
0x18002ecea  jns     short loc_18002ECFA
0x18002ecec  mov     edx, 153h
0x18002ecf1  jmp     short loc_18002ECB2
0x18002ecf3  mov     r12, 0FFFFFFFF80000002h
0x18002ecfa  xor     ebx, ebx
0x18002ecfc  mov     [rbp+120h+var_198], rbx
0x18002ed00  mov     [rbp+120h+var_18C], ebx
0x18002ed03  mov     [rsp+220h+var_1A8], r15
0x18002ed08  mov     r14, [rsp+220h+var_1C0]
0x18002ed0d  mov     [rbp+120h+var_1A0], r14
0x18002ed11  mov     [rbp+120h+var_190], r13d
0x18002ed15  xor     r9d, r9d
0x18002ed18  or      r13d, 0FFFFFFFFh
0x18002ed1c  mov     r8d, r13d
0x18002ed1f  lea     rdx, [rsp+220h+var_1A8]
0x18002ed24  lea     ecx, [rbx+2]
0x18002ed27  call    ?SendNotification@@YAJW4PROF_NOTIFY_EVENT_FLAGS@@PEAUPROF_NOTIFY_PARAM@@KPEAX@Z; SendNotification(PROF_NOTIFY_EVENT_FLAGS,PROF_NOTIFY_PARAM *,ulong,void *)
0x18002ed2c  mov     rcx, [rbp+128h]; this
0x18002ed33  test    eax, eax
0x18002ed35  jns     short loc_18002ED4B
0x18002ed37  mov     r9d, eax; char *
0x18002ed3a  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002ed41  mov     edx, 15Ch; void *
0x18002ed46  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002ed4b  mov     rcx, r15; unsigned __int16 *
0x18002ed4e  call    ?LsaProfileDeletedHelper@@YAJPEBG@Z; LsaProfileDeletedHelper(ushort const *)
0x18002ed53  mov     rcx, [rbp+128h]; this
0x18002ed5a  test    eax, eax
0x18002ed5c  jns     short loc_18002ED66
0x18002ed5e  mov     r9d, eax; char *
0x18002ed61  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x18002ed66  mov     [rsp+220h+dwMilliseconds], ebx
0x18002ed6a  lea     r9, [rsp+220h+dwMilliseconds]; unsigned int *
0x18002ed6f  lea     r8, aDeleteretrywai; "DeleteRetryWait"
0x18002ed76  lea     rdx, aSystemCurrentc_3; "System\\CurrentControlset\\Services\\Pr"...
0x18002ed7d  mov     rcx, r12; HKEY
0x18002ed80  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18002ed85  mov     rcx, [rbp+128h]; this
0x18002ed8c  test    eax, eax
0x18002ed8e  jns     short loc_18002EDA4
0x18002ed90  mov     r9d, eax; char *
0x18002ed93  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002ed9a  mov     edx, 163h; void *
0x18002ed9f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002eda4  mov     [rsp+220h+var_1EC], ebx
0x18002eda8  lea     r9, [rsp+220h+var_1EC]; unsigned int *
0x18002edad  lea     r8, aDeleteretryatt; "DeleteRetryAttempts"
0x18002edb4  lea     rdx, aSystemCurrentc_3; "System\\CurrentControlset\\Services\\Pr"...
0x18002edbb  mov     rcx, r12; HKEY
0x18002edbe  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18002edc3  mov     rcx, [rbp+128h]; this
0x18002edca  test    eax, eax
0x18002edcc  jns     short loc_18002EDE2
0x18002edce  mov     r9d, eax; char *
0x18002edd1  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002edd8  mov     edx, 166h; void *
0x18002eddd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002ede2  cmp     [rsp+220h+var_1EC], ebx
0x18002ede6  jbe     short loc_18002EDF1
0x18002ede8  cmp     [rsp+220h+dwMilliseconds], ebx
0x18002edec  jbe     short loc_18002EDF1
0x18002edee  or      esi, 8
0x18002edf1  xor     r9d, r9d
0x18002edf4  mov     r8d, esi
0x18002edf7  mov     rdx, r14
0x18002edfa  mov     rcx, r15
0x18002edfd  call    ?DeleteProfileLite@@YAJPEBG0W4DeleteProfileFlags@@PEAX@Z; DeleteProfileLite(ushort const *,ushort const *,DeleteProfileFlags,void *)
0x18002ee02  mov     ecx, eax
0x18002ee04  test    eax, eax
0x18002ee06  jns     short loc_18002EE5A
0x18002ee08  cmp     [rsp+220h+var_1EC], ebx
0x18002ee0c  jbe     short loc_18002EE5A
0x18002ee0e  mov     ebx, 80070020h
0x18002ee13  cmp     ecx, ebx
0x18002ee15  jz      short loc_18002EE1F
0x18002ee17  cmp     ecx, 80070091h
0x18002ee1d  jnz     short loc_18002EE58
0x18002ee1f  mov     ecx, [rsp+220h+dwMilliseconds]; dwMilliseconds
0x18002ee23  call    cs:__imp_Sleep
0x18002ee2a  nop     dword ptr [rax+rax+00h]
0x18002ee2f  cmp     [rsp+220h+var_1EC], 1
0x18002ee34  jnz     short loc_18002EE39
0x18002ee36  and     esi, 0FFFFFFF7h
0x18002ee39  xor     r9d, r9d
0x18002ee3c  mov     r8d, esi
0x18002ee3f  mov     rdx, r14
0x18002ee42  xor     ecx, ecx
0x18002ee44  call    ?DeleteProfileLite@@YAJPEBG0W4DeleteProfileFlags@@PEAX@Z; DeleteProfileLite(ushort const *,ushort const *,DeleteProfileFlags,void *)
0x18002ee49  mov     ecx, eax
0x18002ee4b  mov     eax, [rsp+220h+var_1EC]
0x18002ee4f  add     eax, r13d
0x18002ee52  mov     [rsp+220h+var_1EC], eax
0x18002ee56  jnz     short loc_18002EE13
0x18002ee58  xor     ebx, ebx
0x18002ee5a  test    sil, 4
0x18002ee5e  jnz     short loc_18002EEB7
0x18002ee60  mov     [rsp+220h+var_1E4], ebx
0x18002ee64  lea     rax, [rsp+220h+var_1E4]
0x18002ee69  mov     qword ptr [rsp+220h+var_200], rax; int
0x18002ee6e  lea     r8, aLeaveappmgmtda; "LeaveAppMgmtData"
0x18002ee75  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x18002ee7c  mov     rcx, r12; HKEY
0x18002ee7f  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x18002ee84  cmp     [rsp+220h+var_1E4], ebx
0x18002ee88  setnz   r8b; bool
0x18002ee8c  mov     dl, [rsp+220h+var_1F0]; bool
0x18002ee90  mov     rcx, r15; unsigned __int16 *
0x18002ee93  call    ?DeleteOtherPerUserSetting@@YAJPEBG_N1@Z; DeleteOtherPerUserSetting(ushort const *,bool,bool)
0x18002ee98  mov     rcx, [rbp+128h]; this
0x18002ee9f  test    eax, eax
0x18002eea1  jns     short loc_18002EEB7
0x18002eea3  mov     r9d, eax; char *
0x18002eea6  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002eead  mov     edx, 183h; void *
0x18002eeb2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002eeb7  lea     rcx, [rbp+120h+var_180]
0x18002eebb  call    ?Stop@?$ActivityBase@VProfileLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ProfileLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002eec0  nop
0x18002eec1  lea     rcx, [rsp+220h+var_1C0]
0x18002eec6  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002eecb  nop
0x18002eecc  lea     rcx, [rsp+220h+var_1D8]
0x18002eed1  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002eed6  nop
0x18002eed7  lea     rcx, [rbp+120h+var_180]; this
0x18002eedb  call    ??1DeleteUserProfile@ProfileTelemetry@@QEAA@XZ; ProfileTelemetry::DeleteUserProfile::~DeleteUserProfile(void)
0x18002eee0  mov     eax, ebx
0x18002eee2  mov     rcx, [rbp+120h+var_30]
0x18002eee9  xor     rcx, rsp; StackCookie
0x18002eeec  call    __security_check_cookie
0x18002eef1  lea     r11, [rsp+220h+var_20]
0x18002eef9  mov     rbx, [r11+40h]
0x18002eefd  mov     rsi, [r11+48h]
0x18002ef01  mov     rsp, r11
0x18002ef04  pop     r15
0x18002ef06  pop     r14
0x18002ef08  pop     r13
0x18002ef0a  pop     r12
0x18002ef0c  pop     rbp
0x18002ef0d  retn
```
