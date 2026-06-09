# RegistrationStoreData::PrivilegedAction__lambda_b48b12c279374565a5bb5f751ab6a0db___

- ea: `0x1801a3478`
- end: `0x1801a3684`
- name: `RegistrationStoreData::PrivilegedAction__lambda_b48b12c279374565a5bb5f751ab6a0db___`
- size: `524`
- prototype: `HRESULT __fastcall(const RegistrationStoreData::PrivateHive::Create::__l2::<lambda_b48b12c279374565a5bb5f751ab6a0db> *lambda)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180162e50`

## callees

- `0x18005cde8`
- `0x18005ce60`
- `0x180086714`
- `0x18008db2c`
- `0x1801a3478`
- `0x1801a3c1c`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x1801a34cd`
- `ntdll!RtlAdjustPrivilege` at `0x1801a356e`
- `ntdll!RtlAdjustPrivilege` at `0x1801a34cd`
- `ntdll!RtlAdjustPrivilege` at `0x1801a356e`
- `ntdll!RtlNtStatusToDosError` at `0x1801a34d5`
- `ntdll!RtlNtStatusToDosError` at `0x1801a3576`
- `ntdll!RtlNtStatusToDosError` at `0x1801a34d5`
- `ntdll!RtlNtStatusToDosError` at `0x1801a3576`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a35ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a35ff`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1801a34a5`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1801a34a5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801a35f7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801a35f7`

## string_xrefs

- `0x1801a3548`: `onecore\com\combase\registrationstore\privateuserhive.cpp`
- `0x1801a35db`: `onecore\com\combase\registrationstore\privateuserhive.cpp`
- `0x1801a3654`: `onecore\com\combase\registrationstore\privateuserhive.cpp`
- `0x1801a3536`: `RegistrationStoreData::PrivilegedAction`
- `0x1801a35c9`: `RegistrationStoreData::PrivilegedAction`
- `0x1801a364b`: `RegistrationStoreData::PrivilegedAction`

## pseudocode

```c
__int64 __fastcall RegistrationStoreData::PrivilegedAction__lambda_b48b12c279374565a5bb5f751ab6a0db___(
        const RegistrationStoreData::PrivateHive::Create::__l2::<lambda_b48b12c279374565a5bb5f751ab6a0db> *lambda)
{
  HRESULT v1; // ebx
  NTSTATUS v2; // eax
  signed int v3; // eax
  NTSTATUS v4; // eax
  signed int v5; // eax
  signed int LastError; // eax
  TraceLevel v7; // ecx
  __int64 v9; // [rsp+28h] [rbp-20h]
  unsigned __int8 backupWasEnabled; // [rsp+58h] [rbp+10h] BYREF
  unsigned __int8 restoreWasEnabled; // [rsp+60h] [rbp+18h] BYREF
  void *impersonationToken; // [rsp+68h] [rbp+20h] BYREF

  impersonationToken = 0;
  v1 = SuspendImpersonate(&impersonationToken);
  if ( v1 >= 0 )
  {
    if ( ImpersonateSelf(SecurityImpersonation) )
    {
      backupWasEnabled = 0;
      restoreWasEnabled = 0;
      v2 = RtlAdjustPrivilege(0x11u, 1u, 1u, &backupWasEnabled);
      v3 = RtlNtStatusToDosError(v2);
      v1 = v3;
      if ( v3 > 0 )
        v1 = (unsigned __int16)v3 | 0x80070000;
      if ( v1 >= 0 )
      {
        if ( !gfEnableTracing || !IsWppLevelEnabled(VERBOSE) )
        {
LABEL_13:
          v4 = RtlAdjustPrivilege(0x12u, 1u, 1u, &restoreWasEnabled);
          v5 = RtlNtStatusToDosError(v4);
          v1 = v5;
          if ( v5 > 0 )
            v1 = (unsigned __int16)v5 | 0x80070000;
          if ( v1 >= 0 )
          {
            if ( !gfEnableTracing || !IsWppLevelEnabled(VERBOSE) )
              goto LABEL_23;
          }
          else if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
                 && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
          {
            goto LABEL_24;
          }
          LODWORD(v9) = v1;
          ComTraceHr(
            v1,
            "onecore\\com\\combase\\registrationstore\\privateuserhive.cpp",
            "RegistrationStoreData::PrivilegedAction",
            783,
            L"hr:%!HRESULT!",
            v9);
          if ( v1 >= 0 )
LABEL_23:
            v1 = lambda_b48b12c279374565a5bb5f751ab6a0db_::operator()();
LABEL_24:
          RevertToSelf();
LABEL_33:
          ResumeImpersonate(impersonationToken);
          return (unsigned int)v1;
        }
      }
      else if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
      {
        goto LABEL_24;
      }
      ComTraceHr(
        v1,
        "onecore\\com\\combase\\registrationstore\\privateuserhive.cpp",
        "RegistrationStoreData::PrivilegedAction",
        778,
        L"hr:%!HRESULT!",
        v1);
      if ( v1 < 0 )
        goto LABEL_24;
      goto LABEL_13;
    }
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    if ( v1 >= 0 )
    {
      if ( !gfEnableTracing )
        goto LABEL_33;
      v7 = VERBOSE;
    }
    else
    {
      if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 )
        goto LABEL_32;
      if ( !gfEnableTracing )
        goto LABEL_33;
      v7 = ERRORS;
    }
    if ( !IsWppLevelEnabled(v7) )
      goto LABEL_33;
LABEL_32:
    ComTraceHr(
      v1,
      "onecore\\com\\combase\\registrationstore\\privateuserhive.cpp",
      "RegistrationStoreData::PrivilegedAction",
      795,
      L"hr:%!HRESULT!",
      v1);
    goto LABEL_33;
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1801a3478  push    rbx
0x1801a347a  push    rbp
0x1801a347b  push    rsi
0x1801a347c  sub     rsp, 30h
0x1801a3480  mov     rbp, lambda
0x1801a3483  mov     [rsp+48h+impersonationToken], 0
0x1801a348c  lea     lambda, [rsp+48h+impersonationToken]; pHandle
0x1801a3491  call    ?SuspendImpersonate@@YAJPEAPEAX@Z; SuspendImpersonate(void * *)
0x1801a3496  mov     ebx, eax
0x1801a3498  test    eax, eax
0x1801a349a  js      loc_1801A366A
0x1801a34a0  mov     ecx, 2; ImpersonationLevel
0x1801a34a5  call    cs:__imp_ImpersonateSelf
0x1801a34ab  test    eax, eax
0x1801a34ad  jz      loc_1801A35FF
0x1801a34b3  mov     r8b, 1; ForThread
0x1801a34b6  mov     [rsp+48h+backupWasEnabled], 0
0x1801a34bb  mov     dl, r8b; NewValue
0x1801a34be  mov     [rsp+48h+restoreWasEnabled], 0
0x1801a34c3  lea     r9, [rsp+48h+backupWasEnabled]; OldValue
0x1801a34c8  mov     ecx, 11h; Privilege
0x1801a34cd  call    cs:__imp_RtlAdjustPrivilege
0x1801a34d3  mov     ecx, eax; Status
0x1801a34d5  call    cs:__imp_RtlNtStatusToDosError
0x1801a34db  mov     ebx, eax
0x1801a34dd  test    eax, eax
0x1801a34df  jle     short loc_1801A34EA
0x1801a34e1  movzx   ebx, ax
0x1801a34e4  or      ebx, 80070000h
0x1801a34ea  lea     rsi, aHrHresult; "hr:%!HRESULT!"
0x1801a34f1  test    ebx, ebx
0x1801a34f3  jns     short loc_1801A351B
0x1801a34f5  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x1801a34fb  test    eax, eax
0x1801a34fd  jnz     short loc_1801A3532
0x1801a34ff  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1801a3505  jz      loc_1801A35F7
0x1801a350b  xor     ecx, ecx; level
0x1801a350d  call    IsWppLevelEnabled
0x1801a3512  test    al, al
0x1801a3514  jnz     short loc_1801A3532
0x1801a3516  jmp     loc_1801A35F7
0x1801a351b  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x1801a3522  jz      short loc_1801A355E
0x1801a3524  mov     ecx, 3; level
0x1801a3529  call    IsWppLevelEnabled
0x1801a352e  test    al, al
0x1801a3530  jz      short loc_1801A355E
0x1801a3532  mov     dword ptr [rsp+48h+var_20], ebx
0x1801a3536  lea     r8, aRegistrationst_18; "RegistrationStoreData::PrivilegedAction"
0x1801a353d  mov     r9d, 30Ah; line
0x1801a3543  mov     [rsp+48h+format], rsi; format
0x1801a3548  lea     rdx, aOnecoreComComb_71; "onecore\\com\\combase\\registrationstor"...
0x1801a354f  mov     ecx, ebx; hr
0x1801a3551  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x1801a3556  test    ebx, ebx
0x1801a3558  js      loc_1801A35F7
0x1801a355e  mov     r8b, 1; ForThread
0x1801a3561  lea     r9, [rsp+48h+restoreWasEnabled]; OldValue
0x1801a3566  mov     dl, r8b; NewValue
0x1801a3569  mov     ecx, 12h; Privilege
0x1801a356e  call    cs:__imp_RtlAdjustPrivilege
0x1801a3574  mov     ecx, eax; Status
0x1801a3576  call    cs:__imp_RtlNtStatusToDosError
0x1801a357c  mov     ebx, eax
0x1801a357e  test    eax, eax
0x1801a3580  jle     short loc_1801A358B
0x1801a3582  movzx   ebx, ax
0x1801a3585  or      ebx, 80070000h
0x1801a358b  test    ebx, ebx
0x1801a358d  jns     short loc_1801A35AE
0x1801a358f  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x1801a3595  test    eax, eax
0x1801a3597  jnz     short loc_1801A35C5
0x1801a3599  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1801a359f  jz      short loc_1801A35F7
0x1801a35a1  xor     ecx, ecx; level
0x1801a35a3  call    IsWppLevelEnabled
0x1801a35a8  test    al, al
0x1801a35aa  jnz     short loc_1801A35C5
0x1801a35ac  jmp     short loc_1801A35F7
0x1801a35ae  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x1801a35b5  jz      short loc_1801A35ED
0x1801a35b7  mov     ecx, 3; level
0x1801a35bc  call    IsWppLevelEnabled
0x1801a35c1  test    al, al
0x1801a35c3  jz      short loc_1801A35ED
0x1801a35c5  mov     dword ptr [rsp+48h+var_20], ebx
0x1801a35c9  lea     r8, aRegistrationst_18; "RegistrationStoreData::PrivilegedAction"
0x1801a35d0  mov     r9d, 30Fh; line
0x1801a35d6  mov     [rsp+48h+format], rsi; format
0x1801a35db  lea     rdx, aOnecoreComComb_71; "onecore\\com\\combase\\registrationstor"...
0x1801a35e2  mov     ecx, ebx; hr
0x1801a35e4  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x1801a35e9  test    ebx, ebx
0x1801a35eb  js      short loc_1801A35F7
0x1801a35ed  mov     lambda, rbp
0x1801a35f0  call    _lambda_b48b12c279374565a5bb5f751ab6a0db___operator__
0x1801a35f5  mov     ebx, eax
0x1801a35f7  call    cs:__imp_RevertToSelf
0x1801a35fd  jmp     short loc_1801A3660
0x1801a35ff  call    cs:__imp_GetLastError
0x1801a3605  mov     ebx, eax
0x1801a3607  test    eax, eax
0x1801a3609  jle     short loc_1801A3614
0x1801a360b  movzx   ebx, ax
0x1801a360e  or      ebx, 80070000h
0x1801a3614  test    ebx, ebx
0x1801a3616  jns     short loc_1801A3674
0x1801a3618  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x1801a361e  test    eax, eax
0x1801a3620  jnz     short loc_1801A3635
0x1801a3622  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1801a3628  jz      short loc_1801A3660
0x1801a362a  xor     ecx, ecx; level
0x1801a362c  call    IsWppLevelEnabled
0x1801a3631  test    al, al
0x1801a3633  jz      short loc_1801A3660
0x1801a3635  lea     rsi, aHrHresult; "hr:%!HRESULT!"
0x1801a363c  mov     dword ptr [rsp+48h+var_20], ebx
0x1801a3640  mov     r9d, 31Bh; line
0x1801a3646  mov     [rsp+48h+format], rsi; format
0x1801a364b  lea     r8, aRegistrationst_18; "RegistrationStoreData::PrivilegedAction"
0x1801a3652  mov     ecx, ebx; hr
0x1801a3654  lea     rdx, aOnecoreComComb_71; "onecore\\com\\combase\\registrationstor"...
0x1801a365b  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x1801a3660  mov     lambda, [rsp+48h+impersonationToken]; hToken
0x1801a3665  call    ?ResumeImpersonate@@YAXPEAX@Z; ResumeImpersonate(void *)
0x1801a366a  mov     eax, ebx
0x1801a366c  add     rsp, 30h
0x1801a3670  pop     rsi
0x1801a3671  pop     rbp
0x1801a3672  pop     rbx
0x1801a3673  retn
0x1801a3674  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x1801a367b  jz      short loc_1801A3660
0x1801a367d  mov     ecx, 3
0x1801a3682  jmp     short loc_1801A362C
```
