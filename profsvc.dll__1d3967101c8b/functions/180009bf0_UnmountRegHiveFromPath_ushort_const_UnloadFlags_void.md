# UnmountRegHiveFromPath(ushort const *,UnloadFlags,void * *)

- ea: `0x180009bf0`
- end: `0x18000a23b`
- name: `?UnmountRegHiveFromPath@@YAJPEBGW4UnloadFlags@@PEAPEAX@Z`
- size: `1611`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `26`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180008ef4`
- `0x180009320`
- `0x1800140c0`

## callees

- `0x180008c7c`
- `0x180009bf0`
- `0x18000a244`
- `0x18000a2e8`
- `0x18000a37c`
- `0x18000a4a0`
- `0x18000a9b8`
- `0x18000a9e0`
- `0x18000aa5c`
- `0x18000aab8`
- `0x180015458`
- `0x180022780`
- `0x18002356c`
- `0x180024e58`
- `0x1800281a8`
- `0x18002aef0`
- `0x18002d2d8`
- `0x180035f88`
- `0x1800360b8`
- `0x18003a730`
- `0x180040e94`
- `0x180047cbc`
- `0x180049ae4`
- `0x180049b80`
- `0x180049bcc`
- `0x180049c1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009f57`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009f57`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009d70`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009d70`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009d57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009d57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009f62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009f70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a17d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a188`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009f62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009f70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a17d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a188`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009ffc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a10e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009ffc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a10e`
- `ntdll!NtUnloadKey2` at `0x180009f14`
- `ntdll!NtUnloadKey2` at `0x180009f14`
- `ntdll!NtUnloadKeyEx` at `0x180009fa1`
- `ntdll!NtUnloadKeyEx` at `0x180009fa1`
- `ntdll!NtOpenKey` at `0x180009e30`
- `ntdll!NtOpenKey` at `0x180009e30`
- `ntdll!NtUnloadKey` at `0x180009e0c`
- `ntdll!NtUnloadKey` at `0x180009e0c`
- `ntdll!RtlInitUnicodeString` at `0x180009d14`
- `ntdll!RtlInitUnicodeString` at `0x180009d14`
- `ntdll!RtlAdjustPrivilege` at `0x18000a1a4`
- `ntdll!RtlAdjustPrivilege` at `0x18000a1a4`
- `ntdll!RtlNtStatusToDosError` at `0x180009e38`
- `ntdll!RtlNtStatusToDosError` at `0x180009f7d`
- `ntdll!RtlNtStatusToDosError` at `0x180009fbc`
- `ntdll!RtlNtStatusToDosError` at `0x18000a0ce`
- `ntdll!RtlNtStatusToDosError` at `0x180009e38`
- `ntdll!RtlNtStatusToDosError` at `0x180009f7d`
- `ntdll!RtlNtStatusToDosError` at `0x180009fbc`
- `ntdll!RtlNtStatusToDosError` at `0x18000a0ce`

## string_xrefs

- `0x180009da4`: `onecore\ds\security\gina\profile\profsvc\profreg.cpp`
- `0x18000a01d`: `onecore\ds\security\gina\profile\profsvc\profreg.cpp`
- `0x18000a075`: `onecore\ds\security\gina\profile\profsvc\profreg.cpp`
- `0x18000a12f`: `onecore\ds\security\gina\profile\profsvc\profreg.cpp`
- `0x180009c45`: `UnmountRegHiveFromPath`
- `0x18000a1b4`: `Failed to remove RESTORE privilege.`
- `0x18000a1c0`: `onecore\ds\security\gina\profile\profsvc\util.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UnmountRegHiveFromPath(const unsigned __int16 *a1, char a2, HANDLE *a3)
{
  char v6; // r14
  HANDLE CurrentThread; // rax
  int v8; // eax
  unsigned int v9; // ebx
  int v11; // ebx
  NTSTATUS v12; // eax
  int v13; // eax
  unsigned int v14; // ebx
  int v15; // eax
  unsigned int v16; // esi
  ULONG v17; // eax
  CErrorText *v18; // rax
  const wchar_t *v19; // r8
  unsigned int v20; // ebx
  unsigned int v21; // ebx
  ULONG v22; // eax
  CErrorText *v23; // rax
  const wchar_t *v24; // r8
  unsigned int v25; // ebx
  unsigned int v26; // eax
  char v27; // bl
  int v28; // eax
  __int64 v29; // rdx
  int v30; // [rsp+20h] [rbp-E0h]
  char *v31; // [rsp+28h] [rbp-D8h]
  __int64 Privilege; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-C0h] BYREF
  PSRWLOCK SRWLock; // [rsp+48h] [rbp-B8h] BYREF
  struct _OBJECT_ATTRIBUTES KeyObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  void **v38; // [rsp+90h] [rbp-70h] BYREF
  int v39; // [rsp+98h] [rbp-68h] BYREF
  char v40; // [rsp+9Ch] [rbp-64h]
  int v41; // [rsp+C0h] [rbp-40h] BYREF
  const char *v42; // [rsp+C8h] [rbp-38h]
  __int64 v43; // [rsp+D0h] [rbp-30h]
  char v44; // [rsp+D8h] [rbp-28h]
  int v45; // [rsp+E0h] [rbp-20h]
  __int128 v46; // [rsp+E8h] [rbp-18h]
  __int128 v47; // [rsp+F8h] [rbp-8h]
  __int128 v48; // [rsp+108h] [rbp+8h]
  __int128 v49; // [rsp+118h] [rbp+18h]
  __int128 v50; // [rsp+128h] [rbp+28h]
  __int128 v51; // [rsp+138h] [rbp+38h]
  __int128 v52; // [rsp+148h] [rbp+48h]
  __int128 v53; // [rsp+158h] [rbp+58h]
  __int128 v54; // [rsp+168h] [rbp+68h]
  __int64 v55; // [rsp+178h] [rbp+78h]
  __int128 v56; // [rsp+180h] [rbp+80h]
  int v57; // [rsp+190h] [rbp+90h]
  __int64 v58; // [rsp+198h] [rbp+98h]
  int *v59; // [rsp+1A0h] [rbp+A0h]
  _DWORD *v60; // [rsp+1A8h] [rbp+A8h] BYREF
  _QWORD v61[3]; // [rsp+1B0h] [rbp+B0h] BYREF
  int v62; // [rsp+1C8h] [rbp+C8h]
  int *v63; // [rsp+1D0h] [rbp+D0h]
  char v64; // [rsp+1D8h] [rbp+D8h]
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  v6 = 0;
  LODWORD(KeyHandle) = 0;
  v39 = 0;
  v40 = 0;
  v44 = 0;
  v41 = 0;
  v42 = "UnmountRegHiveFromPath";
  v43 = 0;
  v45 = 0;
  v56 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v57 = 1;
  v58 = 0;
  v59 = &v39;
  v60 = 0;
  v61[0] = 0;
  v61[1] = &v38;
  v61[2] = 0;
  v62 = 0;
  v63 = &v41;
  v64 = 0;
  v38 = &ProfileTelemetry::UnmountRegHiveFromPath::`vftable';
  ProfileTelemetry::UnmountRegHiveFromPath::StartActivity((ProfileTelemetry::UnmountRegHiveFromPath *)&v38, a1);
  if ( a3 )
  {
    CloseHandle(*a3);
    *a3 = 0;
  }
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, a1);
  *(_QWORD *)&KeyObjectAttributes.Length = 48;
  *(_QWORD *)&KeyObjectAttributes.Attributes = 64;
  KeyObjectAttributes.RootDirectory = 0;
  KeyObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&KeyObjectAttributes.SecurityDescriptor = 0;
  LODWORD(Privilege) = 18;
  WORD2(Privilege) = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle)
    || (((unsigned __int64)TokenHandle + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v8 = PrivilegeAdjuster::AdjustPrivilegeIfNecessary((PrivilegeAdjuster *)&Privilege);
    v9 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19A,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profreg.cpp",
        (const char *)(unsigned int)v8,
        v30);
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(TokenHandle);
      PrivilegeAdjuster::~PrivilegeAdjuster((PrivilegeAdjuster *)&Privilege);
      v38 = &ProfileTelemetry::UnmountRegHiveFromPath::`vftable';
      wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v38);
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v61);
      wil::details::shared_object<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&v60);
      wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>(&v39);
      return v9;
    }
  }
  v11 = NtUnloadKey(&KeyObjectAttributes);
  if ( v11 >= 0 )
  {
    ProfileTelemetry::UnmountRegHiveFromPath::UnloadedKeyFirstTry((ProfileTelemetry::UnmountRegHiveFromPath *)&v38);
LABEL_14:
    wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(&v38);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    if ( BYTE5(Privilege) )
    {
      v26 = RtlAdjustPrivilege(Privilege, BYTE4(Privilege), 0, (PBOOLEAN)&Privilege + 4);
      wil::details::in1diag3::Log_IfNtStatusFailedMsg(
        retaddr,
        (void *)0x33,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.h",
        (const char *)v26,
        (int)"Failed to remove RESTORE privilege.",
        v31);
    }
    v38 = &ProfileTelemetry::UnmountRegHiveFromPath::`vftable';
    if ( !v60 )
      goto LABEL_19;
    wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      &v38,
      &SRWLock);
    if ( !v60 || (v27 = 1, *v60 != 1) )
    {
      v27 = 0;
      wil::details::shared_object<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&v60);
    }
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    if ( v27 )
    {
LABEL_19:
      if ( *v59 == 1 )
      {
        v28 = v59[22];
        LODWORD(KeyHandle) = v28;
        v29 = 2147942974LL;
        if ( v28 < 0 )
          v29 = (unsigned int)v28;
        wil::ActivityBase<ProfileServiceLogging,1,35184372088832,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileServiceLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
          v59,
          v29,
          &KeyHandle);
        wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
          &v38,
          (unsigned int)KeyHandle);
      }
    }
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v61);
    wil::details::shared_object<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&v60);
    wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>(&v39);
    return 0;
  }
  KeyHandle = 0;
  v12 = NtOpenKey(&KeyHandle, 0x20019u, &KeyObjectAttributes);
  if ( RtlNtStatusToDosError(v12) == 2 )
  {
    ProfileTelemetry::UnmountRegHiveFromPath::SubkeyDoesntExist((ProfileTelemetry::UnmountRegHiveFromPath *)&v38);
    goto LABEL_12;
  }
  if ( (a2 & 2) == 0 && RtlNtStatusToDosError(v11) == 5 )
  {
    ProfileTelemetry::UnmountRegHiveFromPath::HiveLeakDetected((ProfileTelemetry::UnmountRegHiveFromPath *)&v38);
    HiveLeakBreak();
  }
  if ( (a2 & 1) != 0 )
  {
    v15 = NtUnloadKeyEx(&KeyObjectAttributes, 0);
    v16 = v15;
    if ( v15 >= 0 )
    {
      v21 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x1C8,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profreg.cpp",
              (const char *)(unsigned int)v11,
              v30);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&KeyHandle);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      PrivilegeAdjuster::~PrivilegeAdjuster((PrivilegeAdjuster *)&Privilege);
      v38 = &ProfileTelemetry::UnmountRegHiveFromPath::`vftable';
      wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v38);
      wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(&v38);
      return v21;
    }
    else
    {
      if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 1) != 0 )
      {
        v17 = RtlNtStatusToDosError(v15);
        v18 = CErrorText::CErrorText((LPWSTR)&SRWLock, v17);
        v19 = L"???";
        if ( *(_QWORD *)v18 )
          v19 = *(const wchar_t **)v18;
        McTemplateU0z_EtwEventWriteTransfer(*(_QWORD *)v18, EVENT_FAILED_HIVE_UNLOAD, v19);
        v6 = 1;
      }
      if ( (v6 & 1) != 0 )
        LocalFree(SRWLock);
      v20 = wil::details::in1diag3::Return_NtStatusMsg(
              retaddr,
              (void *)0x1C3,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profreg.cpp",
              (const char *)v16,
              (int)"Delay unload failed for <%ws>.",
              (const char *)a1,
              Privilege);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&KeyHandle);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      PrivilegeAdjuster::~PrivilegeAdjuster((PrivilegeAdjuster *)&Privilege);
      v38 = &ProfileTelemetry::UnmountRegHiveFromPath::`vftable';
      wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v38);
      wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(&v38);
      return v20;
    }
  }
  else
  {
    v13 = NtUnloadKey2(&KeyObjectAttributes, 1u);
    v14 = v13;
    if ( v13 >= 0 )
    {
      ProfileTelemetry::UnmountRegHiveFromPath::SubkeyForceUnloaded((ProfileTelemetry::UnmountRegHiveFromPath *)&v38);
LABEL_12:
      if ( (char *)KeyHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(KeyHandle);
      goto LABEL_14;
    }
    if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 1) != 0 )
    {
      v22 = RtlNtStatusToDosError(v13);
      v23 = CErrorText::CErrorText((LPWSTR)&SRWLock, v22);
      v24 = L"???";
      if ( *(_QWORD *)v23 )
        v24 = *(const wchar_t **)v23;
      McTemplateU0z_EtwEventWriteTransfer(*(_QWORD *)v23, EVENT_FAILED_HIVE_UNLOAD, v24);
      v6 = 2;
    }
    if ( (v6 & 2) != 0 )
      LocalFree(SRWLock);
    v25 = wil::details::in1diag3::Return_NtStatusMsg(
            retaddr,
            (void *)0x1D1,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profreg.cpp",
            (const char *)v14,
            (int)"Force unload failed for key <%ws>.",
            (const char *)a1,
            Privilege);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&KeyHandle);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    PrivilegeAdjuster::~PrivilegeAdjuster((PrivilegeAdjuster *)&Privilege);
    v38 = &ProfileTelemetry::UnmountRegHiveFromPath::`vftable';
    wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v38);
    wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(&v38);
    return v25;
  }
}

```

## disassembly

```asm
0x180009bf0  mov     [rsp-8+arg_8], rbx
0x180009bf5  mov     [rsp-8+arg_18], rsi
0x180009bfa  push    rbp
0x180009bfb  push    rdi
0x180009bfc  push    r12
0x180009bfe  push    r14
0x180009c00  push    r15
0x180009c02  lea     rbp, [rsp-0F0h]
0x180009c0a  sub     rsp, 1F0h
0x180009c11  mov     rax, cs:__security_cookie
0x180009c18  xor     rax, rsp
0x180009c1b  mov     [rbp+110h+var_30], rax
0x180009c22  mov     rbx, r8
0x180009c25  mov     esi, edx
0x180009c27  mov     rdi, rcx
0x180009c2a  xor     r15d, r15d
0x180009c2d  mov     r14d, r15d
0x180009c30  mov     dword ptr [rsp+210h+KeyHandle], r15d
0x180009c35  mov     [rbp+110h+var_178], r15d
0x180009c39  mov     [rbp+110h+var_174], r15b
0x180009c3d  mov     [rbp+110h+var_138], r15b
0x180009c41  mov     [rbp+110h+var_150], r15d
0x180009c45  lea     rax, aUnmountreghive_0; "UnmountRegHiveFromPath"
0x180009c4c  mov     [rbp+110h+var_148], rax
0x180009c50  mov     [rbp+110h+var_140], r15
0x180009c54  mov     [rbp+110h+var_130], r15d
0x180009c58  xorps   xmm0, xmm0
0x180009c5b  movdqa  [rbp+110h+var_90], xmm0
0x180009c63  xorps   xmm1, xmm1
0x180009c66  xor     eax, eax
0x180009c68  movups  [rbp+110h+var_128], xmm1
0x180009c6c  movups  [rbp+110h+var_118], xmm1
0x180009c70  movups  [rbp+110h+var_108], xmm1
0x180009c74  movups  [rbp+110h+var_F8], xmm1
0x180009c78  movups  [rbp+110h+var_E8], xmm1
0x180009c7c  movups  [rbp+110h+var_D8], xmm1
0x180009c80  movups  [rbp+110h+var_C8], xmm1
0x180009c84  movups  [rbp+110h+var_B8], xmm1
0x180009c88  movups  [rbp+110h+var_A8], xmm1
0x180009c8c  mov     [rbp+110h+var_98], rax
0x180009c90  mov     [rbp+110h+var_80], 1
0x180009c9a  mov     [rbp+110h+var_78], rax
0x180009ca1  lea     rax, [rbp+110h+var_178]
0x180009ca5  mov     [rbp+110h+var_70], rax
0x180009cac  mov     [rbp+110h+var_68], r15
0x180009cb3  mov     [rbp+110h+var_60], r15
0x180009cba  lea     rax, [rbp+110h+var_180]
0x180009cbe  mov     [rbp+110h+var_58], rax
0x180009cc5  mov     [rbp+110h+var_50], r15
0x180009ccc  mov     [rbp+110h+var_48], r15d
0x180009cd3  lea     rax, [rbp+110h+var_150]
0x180009cd7  mov     [rbp+110h+var_40], rax
0x180009cde  mov     [rbp+110h+var_38], r15b
0x180009ce5  lea     r12, ??_7UnmountRegHiveFromPath@ProfileTelemetry@@6B@; const ProfileTelemetry::UnmountRegHiveFromPath::`vftable'
0x180009cec  mov     [rbp+110h+var_180], r12
0x180009cf0  mov     rdx, rcx; unsigned __int16 *
0x180009cf3  lea     rcx, [rbp+110h+var_180]; this
0x180009cf7  call    ?StartActivity@UnmountRegHiveFromPath@ProfileTelemetry@@QEAAXPEBG@Z; ProfileTelemetry::UnmountRegHiveFromPath::StartActivity(ushort const *)
0x180009cfc  nop
0x180009cfd  test    rbx, rbx
0x180009d00  jnz     loc_180009F5F
0x180009d06  xorps   xmm0, xmm0
0x180009d09  movups  xmmword ptr [rbp+110h+DestinationString.Length], xmm0
0x180009d0d  mov     rdx, rdi; SourceString
0x180009d10  lea     rcx, [rbp+110h+DestinationString]; DestinationString
0x180009d14  call    cs:__imp_RtlInitUnicodeString
0x180009d1a  mov     qword ptr [rsp+210h+KeyObjectAttributes.Length], 30h ; '0'
0x180009d23  mov     qword ptr [rsp+210h+KeyObjectAttributes.Attributes], 40h ; '@'
0x180009d2c  mov     [rsp+210h+KeyObjectAttributes.RootDirectory], r15
0x180009d31  lea     rax, [rbp+110h+DestinationString]
0x180009d35  mov     [rsp+210h+KeyObjectAttributes.ObjectName], rax
0x180009d3a  xorps   xmm0, xmm0
0x180009d3d  movdqu  xmmword ptr [rsp+210h+KeyObjectAttributes.SecurityDescriptor], xmm0
0x180009d43  mov     [rsp+210h+Privilege], 12h
0x180009d4b  mov     word ptr [rsp+210h+OldValue], 0
0x180009d52  mov     [rsp+210h+TokenHandle], r15
0x180009d57  call    cs:__imp_GetCurrentThread
0x180009d5d  lea     r9, [rsp+210h+TokenHandle]; TokenHandle
0x180009d62  mov     edx, 20008h; DesiredAccess
0x180009d67  mov     r8d, 1; OpenAsSelf
0x180009d6d  mov     rcx, rax; ThreadHandle
0x180009d70  call    cs:__imp_OpenThreadToken
0x180009d76  test    eax, eax
0x180009d78  jz      short loc_180009D8A
0x180009d7a  mov     rax, [rsp+210h+TokenHandle]
0x180009d7f  inc     rax
0x180009d82  test    rax, 0FFFFFFFFFFFFFFFEh
0x180009d88  jnz     short loc_180009E07
0x180009d8a  lea     rcx, [rsp+210h+Privilege]; this
0x180009d8f  call    ?AdjustPrivilegeIfNecessary@PrivilegeAdjuster@@QEAAJXZ; PrivilegeAdjuster::AdjustPrivilegeIfNecessary(void)
0x180009d94  mov     ebx, eax
0x180009d96  test    eax, eax
0x180009d98  jns     short loc_180009E07
0x180009d9a  mov     rcx, [rbp+118h]; this
0x180009da1  mov     r9d, eax; char *
0x180009da4  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x180009dab  mov     edx, 19Ah; void *
0x180009db0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009db5  mov     rcx, [rsp+210h+TokenHandle]; hObject
0x180009dba  lea     rdx, [rcx-1]
0x180009dbe  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180009dc2  jbe     loc_180009F70
0x180009dc8  lea     rcx, [rsp+210h+Privilege]; this
0x180009dcd  call    ??1PrivilegeAdjuster@@QEAA@XZ; PrivilegeAdjuster::~PrivilegeAdjuster(void)
0x180009dd2  mov     [rbp+110h+var_180], r12
0x180009dd6  lea     rcx, [rbp+110h+var_180]
0x180009dda  call    ?Destroy@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180009ddf  lea     rcx, [rbp+110h+var_60]; this
0x180009de6  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180009deb  lea     rcx, [rbp+110h+var_68]
0x180009df2  call    ?reset@?$shared_object@V?$ActivityData@VProfileLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x180009df7  lea     rcx, [rbp+110h+var_178]
0x180009dfb  call    ??1?$ActivityData@VProfileLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x180009e00  mov     eax, ebx
0x180009e02  jmp     loc_180009ECF
0x180009e07  lea     rcx, [rsp+210h+KeyObjectAttributes]; KeyObjectAttributes
0x180009e0c  call    cs:__imp_NtUnloadKey
0x180009e12  mov     ebx, eax
0x180009e14  test    eax, eax
0x180009e16  jns     loc_180009F32
0x180009e1c  mov     [rsp+210h+KeyHandle], r15
0x180009e21  lea     r8, [rsp+210h+KeyObjectAttributes]; ObjectAttributes
0x180009e26  mov     edx, 20019h; DesiredAccess
0x180009e2b  lea     rcx, [rsp+210h+KeyHandle]; KeyHandle
0x180009e30  call    cs:__imp_NtOpenKey
0x180009e36  mov     ecx, eax; Status
0x180009e38  call    cs:__imp_RtlNtStatusToDosError
0x180009e3e  cmp     eax, 2
0x180009e41  jnz     loc_180009EFA
0x180009e47  lea     rcx, [rbp+110h+var_180]; this
0x180009e4b  call    ?SubkeyDoesntExist@UnmountRegHiveFromPath@ProfileTelemetry@@QEAAXXZ; ProfileTelemetry::UnmountRegHiveFromPath::SubkeyDoesntExist(void)
0x180009e50  mov     rcx, [rsp+210h+KeyHandle]; hObject
0x180009e55  lea     rax, [rcx-1]
0x180009e59  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180009e5d  jbe     loc_18000A17D
0x180009e63  lea     rcx, [rbp+110h+var_180]
0x180009e67  call    ?Stop@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180009e6c  mov     rcx, [rsp+210h+TokenHandle]; hObject
0x180009e71  lea     rax, [rcx-1]
0x180009e75  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180009e79  jbe     loc_18000A188
0x180009e7f  cmp     [rsp+210h+OldValue+1], 0
0x180009e84  jnz     loc_18000A193
0x180009e8a  mov     [rbp+110h+var_180], r12
0x180009e8e  cmp     [rbp+110h+var_68], 0
0x180009e96  jnz     loc_18000A1D6
0x180009e9c  mov     rcx, [rbp+110h+var_70]
0x180009ea3  cmp     dword ptr [rcx], 1
0x180009ea6  jz      loc_18000A20E
0x180009eac  lea     rcx, [rbp+110h+var_60]; this
0x180009eb3  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180009eb8  lea     rcx, [rbp+110h+var_68]
0x180009ebf  call    ?reset@?$shared_object@V?$ActivityData@VProfileLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x180009ec4  lea     rcx, [rbp+110h+var_178]
0x180009ec8  call    ??1?$ActivityData@VProfileLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x180009ecd  xor     eax, eax
0x180009ecf  mov     rcx, [rbp+110h+var_30]
0x180009ed6  xor     rcx, rsp; StackCookie
0x180009ed9  call    __security_check_cookie
0x180009ede  lea     r11, [rsp+210h+var_20]
0x180009ee6  mov     rbx, [r11+38h]
0x180009eea  mov     rsi, [r11+48h]
0x180009eee  mov     rsp, r11
0x180009ef1  pop     r15
0x180009ef3  pop     r14
0x180009ef5  pop     r12
0x180009ef7  pop     rdi
0x180009ef8  pop     rbp
0x180009ef9  retn
0x180009efa  test    sil, 2
0x180009efe  jz      short loc_180009F7B
0x180009f00  lea     rcx, [rsp+210h+KeyObjectAttributes]; TargetKey
0x180009f05  test    sil, 1
0x180009f09  jnz     loc_180009F9F
0x180009f0f  mov     edx, 1; Flags
0x180009f14  call    cs:__imp_NtUnloadKey2
0x180009f1a  mov     ebx, eax
0x180009f1c  test    eax, eax
0x180009f1e  js      loc_18000A0C3
0x180009f24  lea     rcx, [rbp+110h+var_180]; this
0x180009f28  call    ?SubkeyForceUnloaded@UnmountRegHiveFromPath@ProfileTelemetry@@QEAAXXZ; ProfileTelemetry::UnmountRegHiveFromPath::SubkeyForceUnloaded(void)
0x180009f2d  jmp     loc_180009E50
0x180009f32  lea     rcx, [rbp+110h+var_180]; this
0x180009f36  call    ?UnloadedKeyFirstTry@UnmountRegHiveFromPath@ProfileTelemetry@@QEAAXXZ; ProfileTelemetry::UnmountRegHiveFromPath::UnloadedKeyFirstTry(void)
0x180009f3b  jmp     loc_180009E63
0x180009f40  test    bl, bl
0x180009f42  jnz     loc_180009E9C
0x180009f48  jmp     loc_180009EAC
0x180009f4d  mov     rcx, [rsp+210h+SRWLock]; SRWLock
0x180009f52  test    rcx, rcx
0x180009f55  jz      short loc_180009F40
0x180009f57  call    cs:__imp_ReleaseSRWLockExclusive
0x180009f5d  jmp     short loc_180009F40
0x180009f5f  mov     rcx, [rbx]; hObject
0x180009f62  call    cs:__imp_CloseHandle
0x180009f68  mov     [rbx], r15
0x180009f6b  jmp     loc_180009D06
0x180009f70  call    cs:__imp_CloseHandle
0x180009f76  jmp     loc_180009DC8
0x180009f7b  mov     ecx, ebx; Status
0x180009f7d  call    cs:__imp_RtlNtStatusToDosError
0x180009f83  cmp     eax, 5
0x180009f86  jnz     loc_180009F00
0x180009f8c  lea     rcx, [rbp+110h+var_180]; this
0x180009f90  call    ?HiveLeakDetected@UnmountRegHiveFromPath@ProfileTelemetry@@QEAAXXZ; ProfileTelemetry::UnmountRegHiveFromPath::HiveLeakDetected(void)
0x180009f95  call    ?HiveLeakBreak@@YAXXZ; HiveLeakBreak(void)
0x180009f9a  jmp     loc_180009F00
0x180009f9f  xor     edx, edx; Event
0x180009fa1  call    cs:__imp_NtUnloadKeyEx
0x180009fa7  mov     esi, eax
0x180009fa9  test    eax, eax
0x180009fab  jns     loc_18000A06B
0x180009fb1  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 1
0x180009fb8  jz      short loc_180009FF1
0x180009fba  mov     ecx, eax; Status
0x180009fbc  call    cs:__imp_RtlNtStatusToDosError
0x180009fc2  mov     edx, eax; dwMessageId
0x180009fc4  lea     rcx, [rsp+210h+SRWLock]; lpBuffer
0x180009fc9  call    ??0CErrorText@@QEAA@J@Z; CErrorText::CErrorText(long)
0x180009fce  mov     rcx, [rax]
0x180009fd1  lea     r8, asc_180060EA8; "???"
0x180009fd8  test    rcx, rcx
0x180009fdb  cmovnz  r8, rcx
0x180009fdf  lea     rdx, EVENT_FAILED_HIVE_UNLOAD
0x180009fe6  call    McTemplateU0z_EtwEventWriteTransfer
0x180009feb  mov     r14d, 1
0x180009ff1  test    r14b, 1
0x180009ff5  jz      short loc_18000A002
0x180009ff7  mov     rcx, [rsp+210h+SRWLock]; hMem
0x180009ffc  call    cs:__imp_LocalFree
0x18000a002  mov     rcx, [rbp+118h]; this
0x18000a009  mov     [rsp+210h+var_1E8], rdi; char *
0x18000a00e  lea     rax, aDelayUnloadFai; "Delay unload failed for <%ws>."
0x18000a015  mov     qword ptr [rsp+210h+var_1F0], rax; int
0x18000a01a  mov     r9d, esi; char *
0x18000a01d  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000a024  mov     edx, 1C3h; void *
0x18000a029  call    ?Return_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x18000a02e  mov     ebx, eax
0x18000a030  lea     rcx, [rsp+210h+KeyHandle]
0x18000a035  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000a03a  lea     rcx, [rsp+210h+TokenHandle]
0x18000a03f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000a044  lea     rcx, [rsp+210h+Privilege]; this
0x18000a049  call    ??1PrivilegeAdjuster@@QEAA@XZ; PrivilegeAdjuster::~PrivilegeAdjuster(void)
0x18000a04e  mov     [rbp+110h+var_180], r12
0x18000a052  lea     rcx, [rbp+110h+var_180]
0x18000a056  call    ?Destroy@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000a05b  lea     rcx, [rbp+110h+var_180]
0x18000a05f  call    ??1?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000a064  mov     eax, ebx
0x18000a066  jmp     loc_180009ECF
0x18000a06b  mov     rcx, [rbp+118h]; this
0x18000a072  mov     r9d, ebx; char *
0x18000a075  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000a07c  mov     edx, 1C8h; void *
0x18000a081  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18000a086  mov     ebx, eax
0x18000a088  lea     rcx, [rsp+210h+KeyHandle]
0x18000a08d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000a092  lea     rcx, [rsp+210h+TokenHandle]
0x18000a097  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000a09c  lea     rcx, [rsp+210h+Privilege]; this
0x18000a0a1  call    ??1PrivilegeAdjuster@@QEAA@XZ; PrivilegeAdjuster::~PrivilegeAdjuster(void)
0x18000a0a6  mov     [rbp+110h+var_180], r12
0x18000a0aa  lea     rcx, [rbp+110h+var_180]
0x18000a0ae  call    ?Destroy@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000a0b3  lea     rcx, [rbp+110h+var_180]
0x18000a0b7  call    ??1?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000a0bc  mov     eax, ebx
0x18000a0be  jmp     loc_180009ECF
0x18000a0c3  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 1
0x18000a0ca  jz      short loc_18000A103
0x18000a0cc  mov     ecx, ebx; Status
0x18000a0ce  call    cs:__imp_RtlNtStatusToDosError
0x18000a0d4  mov     edx, eax; dwMessageId
0x18000a0d6  lea     rcx, [rsp+210h+SRWLock]; lpBuffer
0x18000a0db  call    ??0CErrorText@@QEAA@J@Z; CErrorText::CErrorText(long)
0x18000a0e0  mov     rcx, [rax]
0x18000a0e3  lea     r8, asc_180060EA8; "???"
0x18000a0ea  test    rcx, rcx
0x18000a0ed  cmovnz  r8, rcx
0x18000a0f1  lea     rdx, EVENT_FAILED_HIVE_UNLOAD
0x18000a0f8  call    McTemplateU0z_EtwEventWriteTransfer
0x18000a0fd  mov     r14d, 2
0x18000a103  test    r14b, 2
0x18000a107  jz      short loc_18000A114
0x18000a109  mov     rcx, [rsp+210h+SRWLock]; hMem
0x18000a10e  call    cs:__imp_LocalFree
0x18000a114  mov     rcx, [rbp+118h]; this
0x18000a11b  mov     [rsp+210h+var_1E8], rdi; char *
0x18000a120  lea     rax, aForceUnloadFai; "Force unload failed for key <%ws>."
0x18000a127  mov     qword ptr [rsp+210h+var_1F0], rax; int
0x18000a12c  mov     r9d, ebx; char *
0x18000a12f  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000a136  mov     edx, 1D1h; void *
0x18000a13b  call    ?Return_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x18000a140  mov     ebx, eax
0x18000a142  lea     rcx, [rsp+210h+KeyHandle]
0x18000a147  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
  ... truncated ...
```
