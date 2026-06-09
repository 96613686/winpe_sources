# RegistrationStoreData::PrivilegedAction__lambda_4ad815d377d0a4db042d95d3845689d5___

- ea: `0x1801a3264`
- end: `0x1801a3470`
- name: `RegistrationStoreData::PrivilegedAction__lambda_4ad815d377d0a4db042d95d3845689d5___`
- size: `524`
- prototype: `HRESULT __fastcall(const RegistrationStoreData::PrivateHive::RemoveUserHivePath::__l43::<lambda_4ad815d377d0a4db042d95d3845689d5> *lambda)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1801397a4`

## callees

- `0x18005cde8`
- `0x18005ce60`
- `0x180086714`
- `0x18008db2c`
- `0x1801a3264`
- `0x1801a3934`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x1801a32b9`
- `ntdll!RtlAdjustPrivilege` at `0x1801a335a`
- `ntdll!RtlAdjustPrivilege` at `0x1801a32b9`
- `ntdll!RtlAdjustPrivilege` at `0x1801a335a`
- `ntdll!RtlNtStatusToDosError` at `0x1801a32c1`
- `ntdll!RtlNtStatusToDosError` at `0x1801a3362`
- `ntdll!RtlNtStatusToDosError` at `0x1801a32c1`
- `ntdll!RtlNtStatusToDosError` at `0x1801a3362`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a33eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a33eb`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1801a3291`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1801a3291`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801a33e3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801a33e3`

## string_xrefs

- `0x1801a3334`: `onecore\com\combase\registrationstore\privateuserhive.cpp`
- `0x1801a33c7`: `onecore\com\combase\registrationstore\privateuserhive.cpp`
- `0x1801a3440`: `onecore\com\combase\registrationstore\privateuserhive.cpp`
- `0x1801a3322`: `RegistrationStoreData::PrivilegedAction`
- `0x1801a33b5`: `RegistrationStoreData::PrivilegedAction`
- `0x1801a3437`: `RegistrationStoreData::PrivilegedAction`

## pseudocode

```c
__int64 __fastcall RegistrationStoreData::PrivilegedAction__lambda_4ad815d377d0a4db042d95d3845689d5___(
        RegistrationStoreData::PrivateHive::RemoveUserHivePath::__l43::<lambda_4ad815d377d0a4db042d95d3845689d5> *lambda)
{
  HRESULT v2; // ebx
  NTSTATUS v3; // eax
  signed int v4; // eax
  NTSTATUS v5; // eax
  signed int v6; // eax
  signed int LastError; // eax
  TraceLevel v8; // ecx
  __int64 v10; // [rsp+28h] [rbp-20h]
  unsigned __int8 backupWasEnabled; // [rsp+58h] [rbp+10h] BYREF
  unsigned __int8 restoreWasEnabled; // [rsp+60h] [rbp+18h] BYREF
  void *impersonationToken; // [rsp+68h] [rbp+20h] BYREF

  impersonationToken = 0;
  v2 = SuspendImpersonate(&impersonationToken);
  if ( v2 >= 0 )
  {
    if ( ImpersonateSelf(SecurityImpersonation) )
    {
      backupWasEnabled = 0;
      restoreWasEnabled = 0;
      v3 = RtlAdjustPrivilege(0x11u, 1u, 1u, &backupWasEnabled);
      v4 = RtlNtStatusToDosError(v3);
      v2 = v4;
      if ( v4 > 0 )
        v2 = (unsigned __int16)v4 | 0x80070000;
      if ( v2 >= 0 )
      {
        if ( !gfEnableTracing || !IsWppLevelEnabled(VERBOSE) )
        {
LABEL_13:
          v5 = RtlAdjustPrivilege(0x12u, 1u, 1u, &restoreWasEnabled);
          v6 = RtlNtStatusToDosError(v5);
          v2 = v6;
          if ( v6 > 0 )
            v2 = (unsigned __int16)v6 | 0x80070000;
          if ( v2 >= 0 )
          {
            if ( !gfEnableTracing || !IsWppLevelEnabled(VERBOSE) )
              goto LABEL_23;
          }
          else if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                 && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
          {
            goto LABEL_24;
          }
          LODWORD(v10) = v2;
          ComTraceHr(
            v2,
            "onecore\\com\\combase\\registrationstore\\privateuserhive.cpp",
            "RegistrationStoreData::PrivilegedAction",
            783,
            L"hr:%!HRESULT!",
            v10);
          if ( v2 >= 0 )
LABEL_23:
            v2 = lambda_4ad815d377d0a4db042d95d3845689d5_::operator()((LPCWSTR *)lambda);
LABEL_24:
          RevertToSelf();
LABEL_33:
          ResumeImpersonate(impersonationToken);
          return (unsigned int)v2;
        }
      }
      else if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
      {
        goto LABEL_24;
      }
      ComTraceHr(
        v2,
        "onecore\\com\\combase\\registrationstore\\privateuserhive.cpp",
        "RegistrationStoreData::PrivilegedAction",
        778,
        L"hr:%!HRESULT!",
        v2);
      if ( v2 < 0 )
        goto LABEL_24;
      goto LABEL_13;
    }
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( v2 >= 0 )
    {
      if ( !gfEnableTracing )
        goto LABEL_33;
      v8 = VERBOSE;
    }
    else
    {
      if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 )
        goto LABEL_32;
      if ( !gfEnableTracing )
        goto LABEL_33;
      v8 = ERRORS;
    }
    if ( !IsWppLevelEnabled(v8) )
      goto LABEL_33;
LABEL_32:
    ComTraceHr(
      v2,
      "onecore\\com\\combase\\registrationstore\\privateuserhive.cpp",
      "RegistrationStoreData::PrivilegedAction",
      795,
      L"hr:%!HRESULT!",
      v2);
    goto LABEL_33;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1801a3264  push    rbx
0x1801a3266  push    rbp
0x1801a3267  push    rsi
0x1801a3268  sub     rsp, 30h
0x1801a326c  mov     rbp, lambda
0x1801a326f  mov     [rsp+48h+impersonationToken], 0
0x1801a3278  lea     lambda, [rsp+48h+impersonationToken]; pHandle
0x1801a327d  call    ?SuspendImpersonate@@YAJPEAPEAX@Z; SuspendImpersonate(void * *)
0x1801a3282  mov     ebx, eax
0x1801a3284  test    eax, eax
0x1801a3286  js      loc_1801A3456
0x1801a328c  mov     ecx, 2; ImpersonationLevel
0x1801a3291  call    cs:__imp_ImpersonateSelf
0x1801a3297  test    eax, eax
0x1801a3299  jz      loc_1801A33EB
0x1801a329f  mov     r8b, 1; ForThread
0x1801a32a2  mov     [rsp+48h+backupWasEnabled], 0
0x1801a32a7  mov     dl, r8b; NewValue
0x1801a32aa  mov     [rsp+48h+restoreWasEnabled], 0
0x1801a32af  lea     r9, [rsp+48h+backupWasEnabled]; OldValue
0x1801a32b4  mov     ecx, 11h; Privilege
0x1801a32b9  call    cs:__imp_RtlAdjustPrivilege
0x1801a32bf  mov     ecx, eax; Status
0x1801a32c1  call    cs:__imp_RtlNtStatusToDosError
0x1801a32c7  mov     ebx, eax
0x1801a32c9  test    eax, eax
0x1801a32cb  jle     short loc_1801A32D6
0x1801a32cd  movzx   ebx, ax
0x1801a32d0  or      ebx, 80070000h
0x1801a32d6  lea     rsi, aHrHresult; "hr:%!HRESULT!"
0x1801a32dd  test    ebx, ebx
0x1801a32df  jns     short loc_1801A3307
0x1801a32e1  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x1801a32e7  test    eax, eax
0x1801a32e9  jnz     short loc_1801A331E
0x1801a32eb  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1801a32f1  jz      loc_1801A33E3
0x1801a32f7  xor     ecx, ecx; level
0x1801a32f9  call    IsWppLevelEnabled
0x1801a32fe  test    al, al
0x1801a3300  jnz     short loc_1801A331E
0x1801a3302  jmp     loc_1801A33E3
0x1801a3307  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x1801a330e  jz      short loc_1801A334A
0x1801a3310  mov     ecx, 3; level
0x1801a3315  call    IsWppLevelEnabled
0x1801a331a  test    al, al
0x1801a331c  jz      short loc_1801A334A
0x1801a331e  mov     dword ptr [rsp+48h+var_20], ebx
0x1801a3322  lea     r8, aRegistrationst_18; "RegistrationStoreData::PrivilegedAction"
0x1801a3329  mov     r9d, 30Ah; line
0x1801a332f  mov     [rsp+48h+format], rsi; format
0x1801a3334  lea     rdx, aOnecoreComComb_71; "onecore\\com\\combase\\registrationstor"...
0x1801a333b  mov     ecx, ebx; hr
0x1801a333d  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x1801a3342  test    ebx, ebx
0x1801a3344  js      loc_1801A33E3
0x1801a334a  mov     r8b, 1; ForThread
0x1801a334d  lea     r9, [rsp+48h+restoreWasEnabled]; OldValue
0x1801a3352  mov     dl, r8b; NewValue
0x1801a3355  mov     ecx, 12h; Privilege
0x1801a335a  call    cs:__imp_RtlAdjustPrivilege
0x1801a3360  mov     ecx, eax; Status
0x1801a3362  call    cs:__imp_RtlNtStatusToDosError
0x1801a3368  mov     ebx, eax
0x1801a336a  test    eax, eax
0x1801a336c  jle     short loc_1801A3377
0x1801a336e  movzx   ebx, ax
0x1801a3371  or      ebx, 80070000h
0x1801a3377  test    ebx, ebx
0x1801a3379  jns     short loc_1801A339A
0x1801a337b  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x1801a3381  test    eax, eax
0x1801a3383  jnz     short loc_1801A33B1
0x1801a3385  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1801a338b  jz      short loc_1801A33E3
0x1801a338d  xor     ecx, ecx; level
0x1801a338f  call    IsWppLevelEnabled
0x1801a3394  test    al, al
0x1801a3396  jnz     short loc_1801A33B1
0x1801a3398  jmp     short loc_1801A33E3
0x1801a339a  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x1801a33a1  jz      short loc_1801A33D9
0x1801a33a3  mov     ecx, 3; level
0x1801a33a8  call    IsWppLevelEnabled
0x1801a33ad  test    al, al
0x1801a33af  jz      short loc_1801A33D9
0x1801a33b1  mov     dword ptr [rsp+48h+var_20], ebx
0x1801a33b5  lea     r8, aRegistrationst_18; "RegistrationStoreData::PrivilegedAction"
0x1801a33bc  mov     r9d, 30Fh; line
0x1801a33c2  mov     [rsp+48h+format], rsi; format
0x1801a33c7  lea     rdx, aOnecoreComComb_71; "onecore\\com\\combase\\registrationstor"...
0x1801a33ce  mov     ecx, ebx; hr
0x1801a33d0  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x1801a33d5  test    ebx, ebx
0x1801a33d7  js      short loc_1801A33E3
0x1801a33d9  mov     lambda, rbp
0x1801a33dc  call    _lambda_4ad815d377d0a4db042d95d3845689d5___operator__
0x1801a33e1  mov     ebx, eax
0x1801a33e3  call    cs:__imp_RevertToSelf
0x1801a33e9  jmp     short loc_1801A344C
0x1801a33eb  call    cs:__imp_GetLastError
0x1801a33f1  mov     ebx, eax
0x1801a33f3  test    eax, eax
0x1801a33f5  jle     short loc_1801A3400
0x1801a33f7  movzx   ebx, ax
0x1801a33fa  or      ebx, 80070000h
0x1801a3400  test    ebx, ebx
0x1801a3402  jns     short loc_1801A3460
0x1801a3404  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x1801a340a  test    eax, eax
0x1801a340c  jnz     short loc_1801A3421
0x1801a340e  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1801a3414  jz      short loc_1801A344C
0x1801a3416  xor     ecx, ecx; level
0x1801a3418  call    IsWppLevelEnabled
0x1801a341d  test    al, al
0x1801a341f  jz      short loc_1801A344C
0x1801a3421  lea     rsi, aHrHresult; "hr:%!HRESULT!"
0x1801a3428  mov     dword ptr [rsp+48h+var_20], ebx
0x1801a342c  mov     r9d, 31Bh; line
0x1801a3432  mov     [rsp+48h+format], rsi; format
0x1801a3437  lea     r8, aRegistrationst_18; "RegistrationStoreData::PrivilegedAction"
0x1801a343e  mov     ecx, ebx; hr
0x1801a3440  lea     rdx, aOnecoreComComb_71; "onecore\\com\\combase\\registrationstor"...
0x1801a3447  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x1801a344c  mov     lambda, [rsp+48h+impersonationToken]; hToken
0x1801a3451  call    ?ResumeImpersonate@@YAXPEAX@Z; ResumeImpersonate(void *)
0x1801a3456  mov     eax, ebx
0x1801a3458  add     rsp, 30h
0x1801a345c  pop     rsi
0x1801a345d  pop     rbp
0x1801a345e  pop     rbx
0x1801a345f  retn
0x1801a3460  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x1801a3467  jz      short loc_1801A344C
0x1801a3469  mov     ecx, 3
0x1801a346e  jmp     short loc_1801A3418
```
