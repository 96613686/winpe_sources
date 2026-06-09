# RegistrationStoreData::PrivilegedAction__lambda_f2ff2e5a25860d24441cf2362c502800___

- ea: `0x1801a368c`
- end: `0x1801a3898`
- name: `RegistrationStoreData::PrivilegedAction__lambda_f2ff2e5a25860d24441cf2362c502800___`
- size: `524`
- prototype: `__int64 __fastcall(const RegistrationStoreData::PrivateHive::Unload::__l2::<lambda_f2ff2e5a25860d24441cf2362c502800> *lambda)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1801a4a44`

## callees

- `0x18005cde8`
- `0x18005ce60`
- `0x180086714`
- `0x18008db2c`
- `0x1801a368c`
- `0x1801a3ff0`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x1801a36e1`
- `ntdll!RtlAdjustPrivilege` at `0x1801a3782`
- `ntdll!RtlAdjustPrivilege` at `0x1801a36e1`
- `ntdll!RtlAdjustPrivilege` at `0x1801a3782`
- `ntdll!RtlNtStatusToDosError` at `0x1801a36e9`
- `ntdll!RtlNtStatusToDosError` at `0x1801a378a`
- `ntdll!RtlNtStatusToDosError` at `0x1801a36e9`
- `ntdll!RtlNtStatusToDosError` at `0x1801a378a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a3813`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a3813`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1801a36b9`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1801a36b9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801a380b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801a380b`

## string_xrefs

- `0x1801a375c`: `onecore\com\combase\registrationstore\privateuserhive.cpp`
- `0x1801a37ef`: `onecore\com\combase\registrationstore\privateuserhive.cpp`
- `0x1801a3868`: `onecore\com\combase\registrationstore\privateuserhive.cpp`
- `0x1801a374a`: `RegistrationStoreData::PrivilegedAction`
- `0x1801a37dd`: `RegistrationStoreData::PrivilegedAction`
- `0x1801a385f`: `RegistrationStoreData::PrivilegedAction`

## pseudocode

```c
__int64 __fastcall RegistrationStoreData::PrivilegedAction__lambda_f2ff2e5a25860d24441cf2362c502800___(
        const RegistrationStoreData::PrivateHive::Unload::__l2::<lambda_f2ff2e5a25860d24441cf2362c502800> *lambda)
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
            v1 = lambda_f2ff2e5a25860d24441cf2362c502800_::operator()();
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
0x1801a368c  push    rbx
0x1801a368e  push    rbp
0x1801a368f  push    rsi
0x1801a3690  sub     rsp, 30h
0x1801a3694  mov     rbp, lambda
0x1801a3697  mov     [rsp+48h+impersonationToken], 0
0x1801a36a0  lea     lambda, [rsp+48h+impersonationToken]; pHandle
0x1801a36a5  call    ?SuspendImpersonate@@YAJPEAPEAX@Z; SuspendImpersonate(void * *)
0x1801a36aa  mov     ebx, eax
0x1801a36ac  test    eax, eax
0x1801a36ae  js      loc_1801A387E
0x1801a36b4  mov     ecx, 2; ImpersonationLevel
0x1801a36b9  call    cs:__imp_ImpersonateSelf
0x1801a36bf  test    eax, eax
0x1801a36c1  jz      loc_1801A3813
0x1801a36c7  mov     r8b, 1; ForThread
0x1801a36ca  mov     [rsp+48h+backupWasEnabled], 0
0x1801a36cf  mov     dl, r8b; NewValue
0x1801a36d2  mov     [rsp+48h+restoreWasEnabled], 0
0x1801a36d7  lea     r9, [rsp+48h+backupWasEnabled]; OldValue
0x1801a36dc  mov     ecx, 11h; Privilege
0x1801a36e1  call    cs:__imp_RtlAdjustPrivilege
0x1801a36e7  mov     ecx, eax; Status
0x1801a36e9  call    cs:__imp_RtlNtStatusToDosError
0x1801a36ef  mov     ebx, eax
0x1801a36f1  test    eax, eax
0x1801a36f3  jle     short loc_1801A36FE
0x1801a36f5  movzx   ebx, ax
0x1801a36f8  or      ebx, 80070000h
0x1801a36fe  lea     rsi, aHrHresult; "hr:%!HRESULT!"
0x1801a3705  test    ebx, ebx
0x1801a3707  jns     short loc_1801A372F
0x1801a3709  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x1801a370f  test    eax, eax
0x1801a3711  jnz     short loc_1801A3746
0x1801a3713  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1801a3719  jz      loc_1801A380B
0x1801a371f  xor     ecx, ecx; level
0x1801a3721  call    IsWppLevelEnabled
0x1801a3726  test    al, al
0x1801a3728  jnz     short loc_1801A3746
0x1801a372a  jmp     loc_1801A380B
0x1801a372f  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x1801a3736  jz      short loc_1801A3772
0x1801a3738  mov     ecx, 3; level
0x1801a373d  call    IsWppLevelEnabled
0x1801a3742  test    al, al
0x1801a3744  jz      short loc_1801A3772
0x1801a3746  mov     dword ptr [rsp+48h+var_20], ebx
0x1801a374a  lea     r8, aRegistrationst_18; "RegistrationStoreData::PrivilegedAction"
0x1801a3751  mov     r9d, 30Ah; line
0x1801a3757  mov     [rsp+48h+format], rsi; format
0x1801a375c  lea     rdx, aOnecoreComComb_71; "onecore\\com\\combase\\registrationstor"...
0x1801a3763  mov     ecx, ebx; hr
0x1801a3765  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x1801a376a  test    ebx, ebx
0x1801a376c  js      loc_1801A380B
0x1801a3772  mov     r8b, 1; ForThread
0x1801a3775  lea     r9, [rsp+48h+restoreWasEnabled]; OldValue
0x1801a377a  mov     dl, r8b; NewValue
0x1801a377d  mov     ecx, 12h; Privilege
0x1801a3782  call    cs:__imp_RtlAdjustPrivilege
0x1801a3788  mov     ecx, eax; Status
0x1801a378a  call    cs:__imp_RtlNtStatusToDosError
0x1801a3790  mov     ebx, eax
0x1801a3792  test    eax, eax
0x1801a3794  jle     short loc_1801A379F
0x1801a3796  movzx   ebx, ax
0x1801a3799  or      ebx, 80070000h
0x1801a379f  test    ebx, ebx
0x1801a37a1  jns     short loc_1801A37C2
0x1801a37a3  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x1801a37a9  test    eax, eax
0x1801a37ab  jnz     short loc_1801A37D9
0x1801a37ad  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1801a37b3  jz      short loc_1801A380B
0x1801a37b5  xor     ecx, ecx; level
0x1801a37b7  call    IsWppLevelEnabled
0x1801a37bc  test    al, al
0x1801a37be  jnz     short loc_1801A37D9
0x1801a37c0  jmp     short loc_1801A380B
0x1801a37c2  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x1801a37c9  jz      short loc_1801A3801
0x1801a37cb  mov     ecx, 3; level
0x1801a37d0  call    IsWppLevelEnabled
0x1801a37d5  test    al, al
0x1801a37d7  jz      short loc_1801A3801
0x1801a37d9  mov     dword ptr [rsp+48h+var_20], ebx
0x1801a37dd  lea     r8, aRegistrationst_18; "RegistrationStoreData::PrivilegedAction"
0x1801a37e4  mov     r9d, 30Fh; line
0x1801a37ea  mov     [rsp+48h+format], rsi; format
0x1801a37ef  lea     rdx, aOnecoreComComb_71; "onecore\\com\\combase\\registrationstor"...
0x1801a37f6  mov     ecx, ebx; hr
0x1801a37f8  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x1801a37fd  test    ebx, ebx
0x1801a37ff  js      short loc_1801A380B
0x1801a3801  mov     lambda, rbp
0x1801a3804  call    _lambda_f2ff2e5a25860d24441cf2362c502800___operator__
0x1801a3809  mov     ebx, eax
0x1801a380b  call    cs:__imp_RevertToSelf
0x1801a3811  jmp     short loc_1801A3874
0x1801a3813  call    cs:__imp_GetLastError
0x1801a3819  mov     ebx, eax
0x1801a381b  test    eax, eax
0x1801a381d  jle     short loc_1801A3828
0x1801a381f  movzx   ebx, ax
0x1801a3822  or      ebx, 80070000h
0x1801a3828  test    ebx, ebx
0x1801a382a  jns     short loc_1801A3888
0x1801a382c  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x1801a3832  test    eax, eax
0x1801a3834  jnz     short loc_1801A3849
0x1801a3836  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1801a383c  jz      short loc_1801A3874
0x1801a383e  xor     ecx, ecx; level
0x1801a3840  call    IsWppLevelEnabled
0x1801a3845  test    al, al
0x1801a3847  jz      short loc_1801A3874
0x1801a3849  lea     rsi, aHrHresult; "hr:%!HRESULT!"
0x1801a3850  mov     dword ptr [rsp+48h+var_20], ebx
0x1801a3854  mov     r9d, 31Bh; line
0x1801a385a  mov     [rsp+48h+format], rsi; format
0x1801a385f  lea     r8, aRegistrationst_18; "RegistrationStoreData::PrivilegedAction"
0x1801a3866  mov     ecx, ebx; hr
0x1801a3868  lea     rdx, aOnecoreComComb_71; "onecore\\com\\combase\\registrationstor"...
0x1801a386f  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x1801a3874  mov     lambda, [rsp+48h+impersonationToken]; hToken
0x1801a3879  call    ?ResumeImpersonate@@YAXPEAX@Z; ResumeImpersonate(void *)
0x1801a387e  mov     eax, ebx
0x1801a3880  add     rsp, 30h
0x1801a3884  pop     rsi
0x1801a3885  pop     rbp
0x1801a3886  pop     rbx
0x1801a3887  retn
0x1801a3888  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x1801a388f  jz      short loc_1801A3874
0x1801a3891  mov     ecx, 3
0x1801a3896  jmp     short loc_1801A3840
```
