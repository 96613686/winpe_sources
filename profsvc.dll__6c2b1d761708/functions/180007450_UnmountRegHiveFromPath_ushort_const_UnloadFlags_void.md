# UnmountRegHiveFromPath(ushort const *,UnloadFlags,void * *)

- ea: `0x180007450`
- end: `0x180007aa9`
- name: `?UnmountRegHiveFromPath@@YAJPEBGW4UnloadFlags@@PEAPEAX@Z`
- size: `1625`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `28`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180006498`
- `0x1800066cc`
- `0x18000f330`

## callees

- `0x18000621c`
- `0x180007450`
- `0x180007ab0`
- `0x180007bc0`
- `0x180007c2c`
- `0x180007d40`
- `0x1800080d0`
- `0x180008154`
- `0x1800081b0`
- `0x1800081f0`
- `0x180008250`
- `0x1800084bc`
- `0x180017fdc`
- `0x180025570`
- `0x180025e54`
- `0x180027988`
- `0x18002a120`
- `0x180030ad0`
- `0x1800364c8`
- `0x18003651c`
- `0x1800366ec`
- `0x18003bc70`
- `0x180042880`
- `0x180049e10`
- `0x18004bff4`
- `0x18004c090`
- `0x18004c0dc`
- `0x18004c12c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800077e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800077e3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800075dc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800075dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800075bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800075bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800077f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007808`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800079d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800079ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800077f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007808`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800079d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800079ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800078ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007986`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800078ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007986`
- `ntdll!NtUnloadKey2` at `0x18000779a`
- `ntdll!NtUnloadKey2` at `0x18000779a`
- `ntdll!NtUnloadKeyEx` at `0x180007845`
- `ntdll!NtUnloadKeyEx` at `0x180007845`
- `ntdll!NtOpenKey` at `0x180007690`
- `ntdll!NtOpenKey` at `0x180007690`
- `ntdll!NtUnloadKey` at `0x180007666`
- `ntdll!NtUnloadKey` at `0x180007666`
- `ntdll!RtlInitUnicodeString` at `0x180007574`
- `ntdll!RtlInitUnicodeString` at `0x180007574`
- `ntdll!RtlAdjustPrivilege` at `0x180007a0c`
- `ntdll!RtlAdjustPrivilege` at `0x180007a0c`
- `ntdll!RtlNtStatusToDosError` at `0x18000769e`
- `ntdll!RtlNtStatusToDosError` at `0x18000781b`
- `ntdll!RtlNtStatusToDosError` at `0x180007866`
- `ntdll!RtlNtStatusToDosError` at `0x180007940`
- `ntdll!RtlNtStatusToDosError` at `0x18000769e`
- `ntdll!RtlNtStatusToDosError` at `0x18000781b`
- `ntdll!RtlNtStatusToDosError` at `0x180007866`
- `ntdll!RtlNtStatusToDosError` at `0x180007940`

## string_xrefs

- `0x1800074a5`: `UnmountRegHiveFromPath`
- `0x180007616`: `onecore\ds\security\gina\profile\profsvc\profreg.cpp`
- `0x1800078d3`: `onecore\ds\security\gina\profile\profsvc\profreg.cpp`
- `0x180007909`: `onecore\ds\security\gina\profile\profsvc\profreg.cpp`
- `0x1800079ad`: `onecore\ds\security\gina\profile\profsvc\profreg.cpp`
- `0x180007a22`: `Failed to remove RESTORE privilege.`
- `0x180007a2e`: `onecore\ds\security\gina\profile\profsvc\util.h`

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
  ULONG v20; // eax
  CErrorText *v21; // rax
  const wchar_t *v22; // r8
  unsigned int v23; // eax
  char v24; // bl
  int v25; // eax
  __int64 v26; // rdx
  int v27; // [rsp+20h] [rbp-E0h]
  char *v28; // [rsp+28h] [rbp-D8h]
  __int64 Privilege; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-C0h] BYREF
  PSRWLOCK SRWLock; // [rsp+48h] [rbp-B8h] BYREF
  _OBJECT_ATTRIBUTES KeyObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  void **v35; // [rsp+90h] [rbp-70h] BYREF
  int v36; // [rsp+98h] [rbp-68h] BYREF
  char v37; // [rsp+9Ch] [rbp-64h]
  int v38; // [rsp+C0h] [rbp-40h] BYREF
  const char *v39; // [rsp+C8h] [rbp-38h]
  __int64 v40; // [rsp+D0h] [rbp-30h]
  char v41; // [rsp+D8h] [rbp-28h]
  int v42; // [rsp+E0h] [rbp-20h]
  __int128 v43; // [rsp+E8h] [rbp-18h]
  __int128 v44; // [rsp+F8h] [rbp-8h]
  __int128 v45; // [rsp+108h] [rbp+8h]
  __int128 v46; // [rsp+118h] [rbp+18h]
  __int128 v47; // [rsp+128h] [rbp+28h]
  __int128 v48; // [rsp+138h] [rbp+38h]
  __int128 v49; // [rsp+148h] [rbp+48h]
  __int128 v50; // [rsp+158h] [rbp+58h]
  __int128 v51; // [rsp+168h] [rbp+68h]
  __int64 v52; // [rsp+178h] [rbp+78h]
  __int128 v53; // [rsp+180h] [rbp+80h] BYREF
  int v54; // [rsp+190h] [rbp+90h]
  __int64 v55; // [rsp+198h] [rbp+98h]
  int *v56; // [rsp+1A0h] [rbp+A0h]
  _DWORD *v57; // [rsp+1A8h] [rbp+A8h] BYREF
  _QWORD v58[3]; // [rsp+1B0h] [rbp+B0h] BYREF
  int v59; // [rsp+1C8h] [rbp+C8h]
  int *v60; // [rsp+1D0h] [rbp+D0h]
  char v61; // [rsp+1D8h] [rbp+D8h]
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  v6 = 0;
  LODWORD(KeyHandle) = 0;
  v36 = 0;
  v37 = 0;
  v41 = 0;
  v38 = 0;
  v39 = "UnmountRegHiveFromPath";
  v40 = 0;
  v42 = 0;
  v53 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v54 = 1;
  v55 = 0;
  v56 = &v36;
  v57 = 0;
  v58[0] = 0;
  v58[1] = &v35;
  v58[2] = 0;
  v59 = 0;
  v60 = &v38;
  v61 = 0;
  v35 = &ProfileTelemetry::UnmountRegHiveFromPath::`vftable';
  ProfileTelemetry::UnmountRegHiveFromPath::StartActivity((ProfileTelemetry::UnmountRegHiveFromPath *)&v35, a1);
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
        v27);
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(TokenHandle);
LABEL_8:
      PrivilegeAdjuster::~PrivilegeAdjuster((PrivilegeAdjuster *)&Privilege);
      v35 = &ProfileTelemetry::UnmountRegHiveFromPath::`vftable';
      wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v35);
      wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(&v35);
      return v9;
    }
  }
  v11 = NtUnloadKey(&KeyObjectAttributes);
  if ( v11 >= 0 )
  {
    ProfileTelemetry::UnmountRegHiveFromPath::UnloadedKeyFirstTry((ProfileTelemetry::UnmountRegHiveFromPath *)&v35);
  }
  else
  {
    KeyHandle = 0;
    v12 = NtOpenKey(&KeyHandle, 0x20019u, &KeyObjectAttributes);
    if ( RtlNtStatusToDosError(v12) == 2 )
    {
      ProfileTelemetry::UnmountRegHiveFromPath::SubkeyDoesntExist((ProfileTelemetry::UnmountRegHiveFromPath *)&v35);
    }
    else
    {
      if ( (a2 & 2) == 0 && RtlNtStatusToDosError(v11) == 5 )
      {
        ProfileTelemetry::UnmountRegHiveFromPath::HiveLeakDetected((ProfileTelemetry::UnmountRegHiveFromPath *)&v35);
        HiveLeakBreak();
      }
      if ( (a2 & 1) != 0 )
      {
        v15 = NtUnloadKeyEx(&KeyObjectAttributes, 0);
        v16 = v15;
        if ( v15 >= 0 )
        {
          v9 = wil::details::in1diag3::Return_NtStatus(
                 retaddr,
                 (void *)0x1C8,
                 (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profreg.cpp",
                 (const char *)(unsigned int)v11,
                 v27);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&KeyHandle);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
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
          v9 = wil::details::in1diag3::Return_NtStatusMsg(
                 retaddr,
                 (void *)0x1C3,
                 (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profreg.cpp",
                 (const char *)v16,
                 (int)"Delay unload failed for <%ws>.",
                 (const char *)a1,
                 Privilege);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&KeyHandle);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        }
        goto LABEL_8;
      }
      v13 = NtUnloadKey2(&KeyObjectAttributes, 1u);
      v14 = v13;
      if ( v13 < 0 )
      {
        if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 1) != 0 )
        {
          v20 = RtlNtStatusToDosError(v13);
          v21 = CErrorText::CErrorText((LPWSTR)&SRWLock, v20);
          v22 = L"???";
          if ( *(_QWORD *)v21 )
            v22 = *(const wchar_t **)v21;
          McTemplateU0z_EtwEventWriteTransfer(*(_QWORD *)v21, EVENT_FAILED_HIVE_UNLOAD, v22);
          v6 = 2;
        }
        if ( (v6 & 2) != 0 )
          LocalFree(SRWLock);
        v9 = wil::details::in1diag3::Return_NtStatusMsg(
               retaddr,
               (void *)0x1D1,
               (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profreg.cpp",
               (const char *)v14,
               (int)"Force unload failed for key <%ws>.",
               (const char *)a1,
               Privilege);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&KeyHandle);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        goto LABEL_8;
      }
      ProfileTelemetry::UnmountRegHiveFromPath::SubkeyForceUnloaded((ProfileTelemetry::UnmountRegHiveFromPath *)&v35);
    }
    if ( (char *)KeyHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(KeyHandle);
  }
  wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(&v35);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  if ( BYTE5(Privilege) )
  {
    v23 = RtlAdjustPrivilege(Privilege, BYTE4(Privilege), 0, (PBOOLEAN)&Privilege + 4);
    wil::details::in1diag3::Log_IfNtStatusFailedMsg(
      retaddr,
      (void *)0x33,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.h",
      (const char *)v23,
      (int)"Failed to remove RESTORE privilege.",
      v28);
  }
  v35 = &ProfileTelemetry::UnmountRegHiveFromPath::`vftable';
  if ( !v57 )
    goto LABEL_19;
  wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(&v35, &SRWLock);
  if ( !v57 || (v24 = 1, *v57 != 1) )
  {
    v24 = 0;
    wil::details::shared_object<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&v57);
  }
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v24 )
  {
LABEL_19:
    if ( *v56 == 1 )
    {
      v25 = v56[22];
      LODWORD(KeyHandle) = v25;
      v26 = 2147942974LL;
      if ( v25 < 0 )
        v26 = (unsigned int)v25;
      wil::ActivityBase<ProfileServiceLogging,1,35184372088832,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileServiceLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
        v56,
        v26,
        &KeyHandle);
      wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
        &v35,
        (unsigned int)KeyHandle);
    }
  }
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v58);
  wil::details::shared_object<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(&v57);
  wil::details::shared_buffer::reset((wil::details::shared_buffer *)&v53);
  wil::details::StoredCallContextInfo::ClearMessage((wil::details::StoredCallContextInfo *)&v38);
  _TlgActivityBase<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>,0,4>::~_TlgActivityBase<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>,0,4>(&v36);
  return 0;
}

```

## disassembly

```asm
0x180007450  mov     [rsp-8+arg_8], rbx
0x180007455  mov     [rsp-8+arg_18], rsi
0x18000745a  push    rbp
0x18000745b  push    rdi
0x18000745c  push    r12
0x18000745e  push    r14
0x180007460  push    r15
0x180007462  lea     rbp, [rsp-0F0h]
0x18000746a  sub     rsp, 1F0h
0x180007471  mov     rax, cs:__security_cookie
0x180007478  xor     rax, rsp
0x18000747b  mov     [rbp+110h+var_30], rax
0x180007482  mov     rbx, r8
0x180007485  mov     esi, edx
0x180007487  mov     rdi, rcx
0x18000748a  xor     r15d, r15d
0x18000748d  mov     r14d, r15d
0x180007490  mov     dword ptr [rsp+210h+KeyHandle], r15d
0x180007495  mov     [rbp+110h+var_178], r15d
0x180007499  mov     [rbp+110h+var_174], r15b
0x18000749d  mov     [rbp+110h+var_138], r15b
0x1800074a1  mov     [rbp+110h+var_150], r15d
0x1800074a5  lea     rax, aUnmountreghive_0; "UnmountRegHiveFromPath"
0x1800074ac  mov     [rbp+110h+var_148], rax
0x1800074b0  mov     [rbp+110h+var_140], r15
0x1800074b4  mov     [rbp+110h+var_130], r15d
0x1800074b8  xorps   xmm0, xmm0
0x1800074bb  movdqa  [rbp+110h+var_90], xmm0
0x1800074c3  xorps   xmm1, xmm1
0x1800074c6  xor     eax, eax
0x1800074c8  movups  [rbp+110h+var_128], xmm1
0x1800074cc  movups  [rbp+110h+var_118], xmm1
0x1800074d0  movups  [rbp+110h+var_108], xmm1
0x1800074d4  movups  [rbp+110h+var_F8], xmm1
0x1800074d8  movups  [rbp+110h+var_E8], xmm1
0x1800074dc  movups  [rbp+110h+var_D8], xmm1
0x1800074e0  movups  [rbp+110h+var_C8], xmm1
0x1800074e4  movups  [rbp+110h+var_B8], xmm1
0x1800074e8  movups  [rbp+110h+var_A8], xmm1
0x1800074ec  mov     [rbp+110h+var_98], rax
0x1800074f0  mov     [rbp+110h+var_80], 1
0x1800074fa  mov     [rbp+110h+var_78], rax
0x180007501  lea     rax, [rbp+110h+var_178]
0x180007505  mov     [rbp+110h+var_70], rax
0x18000750c  mov     [rbp+110h+var_68], r15
0x180007513  mov     [rbp+110h+var_60], r15
0x18000751a  lea     rax, [rbp+110h+var_180]
0x18000751e  mov     [rbp+110h+var_58], rax
0x180007525  mov     [rbp+110h+var_50], r15
0x18000752c  mov     [rbp+110h+var_48], r15d
0x180007533  lea     rax, [rbp+110h+var_150]
0x180007537  mov     [rbp+110h+var_40], rax
0x18000753e  mov     [rbp+110h+var_38], r15b
0x180007545  lea     r12, ??_7UnmountRegHiveFromPath@ProfileTelemetry@@6B@; const ProfileTelemetry::UnmountRegHiveFromPath::`vftable'
0x18000754c  mov     [rbp+110h+var_180], r12
0x180007550  mov     rdx, rcx; unsigned __int16 *
0x180007553  lea     rcx, [rbp+110h+var_180]; this
0x180007557  call    ?StartActivity@UnmountRegHiveFromPath@ProfileTelemetry@@QEAAXPEBG@Z; ProfileTelemetry::UnmountRegHiveFromPath::StartActivity(ushort const *)
0x18000755c  nop
0x18000755d  test    rbx, rbx
0x180007560  jnz     loc_1800077F1
0x180007566  xorps   xmm0, xmm0
0x180007569  movups  xmmword ptr [rbp+110h+DestinationString.Length], xmm0
0x18000756d  mov     rdx, rdi; SourceString
0x180007570  lea     rcx, [rbp+110h+DestinationString]; DestinationString
0x180007574  call    cs:__imp_RtlInitUnicodeString
0x18000757b  nop     dword ptr [rax+rax+00h]
0x180007580  mov     qword ptr [rsp+210h+KeyObjectAttributes.Length], 30h ; '0'
0x180007589  mov     qword ptr [rsp+210h+KeyObjectAttributes.Attributes], 40h ; '@'
0x180007592  mov     [rsp+210h+KeyObjectAttributes.RootDirectory], r15
0x180007597  lea     rax, [rbp+110h+DestinationString]
0x18000759b  mov     [rsp+210h+KeyObjectAttributes.ObjectName], rax
0x1800075a0  xorps   xmm0, xmm0
0x1800075a3  movdqu  xmmword ptr [rsp+210h+KeyObjectAttributes.SecurityDescriptor], xmm0
0x1800075a9  mov     [rsp+210h+Privilege], 12h
0x1800075b1  mov     word ptr [rsp+210h+OldValue], 0
0x1800075b8  mov     [rsp+210h+TokenHandle], r15
0x1800075bd  call    cs:__imp_GetCurrentThread
0x1800075c4  nop     dword ptr [rax+rax+00h]
0x1800075c9  lea     r9, [rsp+210h+TokenHandle]; TokenHandle
0x1800075ce  mov     edx, 20008h; DesiredAccess
0x1800075d3  mov     r8d, 1; OpenAsSelf
0x1800075d9  mov     rcx, rax; ThreadHandle
0x1800075dc  call    cs:__imp_OpenThreadToken
0x1800075e3  nop     dword ptr [rax+rax+00h]
0x1800075e8  test    eax, eax
0x1800075ea  jz      short loc_1800075FC
0x1800075ec  mov     rax, [rsp+210h+TokenHandle]
0x1800075f1  inc     rax
0x1800075f4  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800075fa  jnz     short loc_180007661
0x1800075fc  lea     rcx, [rsp+210h+Privilege]; this
0x180007601  call    ?AdjustPrivilegeIfNecessary@PrivilegeAdjuster@@QEAAJXZ; PrivilegeAdjuster::AdjustPrivilegeIfNecessary(void)
0x180007606  mov     ebx, eax
0x180007608  test    eax, eax
0x18000760a  jns     short loc_180007661
0x18000760c  mov     rcx, [rbp+118h]; this
0x180007613  mov     r9d, eax; char *
0x180007616  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000761d  mov     edx, 19Ah; void *
0x180007622  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007627  mov     rcx, [rsp+210h+TokenHandle]; hObject
0x18000762c  lea     rdx, [rcx-1]
0x180007630  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180007634  jbe     loc_180007808
0x18000763a  lea     rcx, [rsp+210h+Privilege]; this
0x18000763f  call    ??1PrivilegeAdjuster@@QEAA@XZ; PrivilegeAdjuster::~PrivilegeAdjuster(void)
0x180007644  mov     [rbp+110h+var_180], r12
0x180007648  lea     rcx, [rbp+110h+var_180]
0x18000764c  call    ?Destroy@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180007651  lea     rcx, [rbp+110h+var_180]
0x180007655  call    ??1?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000765a  mov     eax, ebx
0x18000765c  jmp     loc_180007750
0x180007661  lea     rcx, [rsp+210h+KeyObjectAttributes]; KeyObjectAttributes
0x180007666  call    cs:__imp_NtUnloadKey
0x18000766d  nop     dword ptr [rax+rax+00h]
0x180007672  mov     ebx, eax
0x180007674  test    eax, eax
0x180007676  jns     loc_1800077BE
0x18000767c  mov     [rsp+210h+KeyHandle], r15
0x180007681  lea     r8, [rsp+210h+KeyObjectAttributes]; ObjectAttributes
0x180007686  mov     edx, 20019h; DesiredAccess
0x18000768b  lea     rcx, [rsp+210h+KeyHandle]; KeyHandle
0x180007690  call    cs:__imp_NtOpenKey
0x180007697  nop     dword ptr [rax+rax+00h]
0x18000769c  mov     ecx, eax; Status
0x18000769e  call    cs:__imp_RtlNtStatusToDosError
0x1800076a5  nop     dword ptr [rax+rax+00h]
0x1800076aa  cmp     eax, 2
0x1800076ad  jnz     loc_18000777C
0x1800076b3  lea     rcx, [rbp+110h+var_180]; this
0x1800076b7  call    ?SubkeyDoesntExist@UnmountRegHiveFromPath@ProfileTelemetry@@QEAAXXZ; ProfileTelemetry::UnmountRegHiveFromPath::SubkeyDoesntExist(void)
0x1800076bc  mov     rcx, [rsp+210h+KeyHandle]; hObject
0x1800076c1  lea     rax, [rcx-1]
0x1800076c5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800076c9  jbe     loc_1800079D9
0x1800076cf  lea     rcx, [rbp+110h+var_180]
0x1800076d3  call    ?Stop@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800076d8  mov     rcx, [rsp+210h+TokenHandle]; hObject
0x1800076dd  lea     rax, [rcx-1]
0x1800076e1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800076e5  jbe     loc_1800079EA
0x1800076eb  cmp     [rsp+210h+OldValue+1], 0
0x1800076f0  jnz     loc_1800079FB
0x1800076f6  mov     [rbp+110h+var_180], r12
0x1800076fa  cmp     [rbp+110h+var_68], 0
0x180007702  jnz     loc_180007A44
0x180007708  mov     rcx, [rbp+110h+var_70]
0x18000770f  cmp     dword ptr [rcx], 1
0x180007712  jz      loc_180007A7C
0x180007718  lea     rcx, [rbp+110h+var_60]; this
0x18000771f  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180007724  lea     rcx, [rbp+110h+var_68]
0x18000772b  call    ?reset@?$shared_object@V?$ActivityData@VProfileLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x180007730  lea     rcx, [rbp+110h+var_90]; this
0x180007737  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x18000773c  lea     rcx, [rbp+110h+var_150]; this
0x180007740  call    ?ClearMessage@StoredCallContextInfo@details@wil@@QEAAXXZ; wil::details::StoredCallContextInfo::ClearMessage(void)
0x180007745  lea     rcx, [rbp+110h+var_178]
0x180007749  call    ??1?$_TlgActivityBase@V?$ActivityData@VProfileLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VProfileLogging@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@$0A@$03@@IEAA@XZ; _TlgActivityBase<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>,0,4>::~_TlgActivityBase<wil::ActivityBase<ProfileLogging,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ProfileLogging,_TlgReflectorTag_Param0IsProviderType>,0,4>(void)
0x18000774e  xor     eax, eax
0x180007750  mov     rcx, [rbp+110h+var_30]
0x180007757  xor     rcx, rsp; StackCookie
0x18000775a  call    __security_check_cookie
0x18000775f  lea     r11, [rsp+210h+var_20]
0x180007767  mov     rbx, [r11+38h]
0x18000776b  mov     rsi, [r11+48h]
0x18000776f  mov     rsp, r11
0x180007772  pop     r15
0x180007774  pop     r14
0x180007776  pop     r12
0x180007778  pop     rdi
0x180007779  pop     rbp
0x18000777a  retn
0x18000777c  test    sil, 2
0x180007780  jz      loc_180007819
0x180007786  lea     rcx, [rsp+210h+KeyObjectAttributes]; TargetKey
0x18000778b  test    sil, 1
0x18000778f  jnz     loc_180007843
0x180007795  mov     edx, 1; Flags
0x18000779a  call    cs:__imp_NtUnloadKey2
0x1800077a1  nop     dword ptr [rax+rax+00h]
0x1800077a6  mov     ebx, eax
0x1800077a8  test    eax, eax
0x1800077aa  js      loc_180007935
0x1800077b0  lea     rcx, [rbp+110h+var_180]; this
0x1800077b4  call    ?SubkeyForceUnloaded@UnmountRegHiveFromPath@ProfileTelemetry@@QEAAXXZ; ProfileTelemetry::UnmountRegHiveFromPath::SubkeyForceUnloaded(void)
0x1800077b9  jmp     loc_1800076BC
0x1800077be  lea     rcx, [rbp+110h+var_180]; this
0x1800077c2  call    ?UnloadedKeyFirstTry@UnmountRegHiveFromPath@ProfileTelemetry@@QEAAXXZ; ProfileTelemetry::UnmountRegHiveFromPath::UnloadedKeyFirstTry(void)
0x1800077c7  jmp     loc_1800076CF
0x1800077cc  test    bl, bl
0x1800077ce  jnz     loc_180007708
0x1800077d4  jmp     loc_180007718
0x1800077d9  mov     rcx, [rsp+210h+SRWLock]; SRWLock
0x1800077de  test    rcx, rcx
0x1800077e1  jz      short loc_1800077CC
0x1800077e3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800077ea  nop     dword ptr [rax+rax+00h]
0x1800077ef  jmp     short loc_1800077CC
0x1800077f1  mov     rcx, [rbx]; hObject
0x1800077f4  call    cs:__imp_CloseHandle
0x1800077fb  nop     dword ptr [rax+rax+00h]
0x180007800  mov     [rbx], r15
0x180007803  jmp     loc_180007566
0x180007808  call    cs:__imp_CloseHandle
0x18000780f  nop     dword ptr [rax+rax+00h]
0x180007814  jmp     loc_18000763A
0x180007819  mov     ecx, ebx; Status
0x18000781b  call    cs:__imp_RtlNtStatusToDosError
0x180007822  nop     dword ptr [rax+rax+00h]
0x180007827  cmp     eax, 5
0x18000782a  jnz     loc_180007786
0x180007830  lea     rcx, [rbp+110h+var_180]; this
0x180007834  call    ?HiveLeakDetected@UnmountRegHiveFromPath@ProfileTelemetry@@QEAAXXZ; ProfileTelemetry::UnmountRegHiveFromPath::HiveLeakDetected(void)
0x180007839  call    ?HiveLeakBreak@@YAXXZ; HiveLeakBreak(void)
0x18000783e  jmp     loc_180007786
0x180007843  xor     edx, edx; Event
0x180007845  call    cs:__imp_NtUnloadKeyEx
0x18000784c  nop     dword ptr [rax+rax+00h]
0x180007851  mov     esi, eax
0x180007853  test    eax, eax
0x180007855  jns     loc_1800078FF
0x18000785b  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 1
0x180007862  jz      short loc_1800078A1
0x180007864  mov     ecx, eax; Status
0x180007866  call    cs:__imp_RtlNtStatusToDosError
0x18000786d  nop     dword ptr [rax+rax+00h]
0x180007872  mov     edx, eax; dwMessageId
0x180007874  lea     rcx, [rsp+210h+SRWLock]; lpBuffer
0x180007879  call    ??0CErrorText@@QEAA@J@Z; CErrorText::CErrorText(long)
0x18000787e  mov     rcx, [rax]
0x180007881  lea     r8, asc_180063710; "???"
0x180007888  test    rcx, rcx
0x18000788b  cmovnz  r8, rcx
0x18000788f  lea     rdx, EVENT_FAILED_HIVE_UNLOAD
0x180007896  call    McTemplateU0z_EtwEventWriteTransfer
0x18000789b  mov     r14d, 1
0x1800078a1  test    r14b, 1
0x1800078a5  jz      short loc_1800078B8
0x1800078a7  mov     rcx, [rsp+210h+SRWLock]; hMem
0x1800078ac  call    cs:__imp_LocalFree
0x1800078b3  nop     dword ptr [rax+rax+00h]
0x1800078b8  mov     rcx, [rbp+118h]; this
0x1800078bf  mov     [rsp+210h+var_1E8], rdi; char *
0x1800078c4  lea     rax, aDelayUnloadFai; "Delay unload failed for <%ws>."
0x1800078cb  mov     qword ptr [rsp+210h+var_1F0], rax; int
0x1800078d0  mov     r9d, esi; char *
0x1800078d3  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800078da  mov     edx, 1C3h; void *
0x1800078df  call    ?Return_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x1800078e4  mov     ebx, eax
0x1800078e6  lea     rcx, [rsp+210h+KeyHandle]
0x1800078eb  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800078f0  lea     rcx, [rsp+210h+TokenHandle]
0x1800078f5  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800078fa  jmp     loc_18000763A
0x1800078ff  mov     rcx, [rbp+118h]; this
0x180007906  mov     r9d, ebx; char *
0x180007909  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x180007910  mov     edx, 1C8h; void *
0x180007915  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18000791a  mov     ebx, eax
0x18000791c  lea     rcx, [rsp+210h+KeyHandle]
0x180007921  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180007926  lea     rcx, [rsp+210h+TokenHandle]
0x18000792b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180007930  jmp     loc_18000763A
0x180007935  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 1
0x18000793c  jz      short loc_18000797B
0x18000793e  mov     ecx, ebx; Status
0x180007940  call    cs:__imp_RtlNtStatusToDosError
0x180007947  nop     dword ptr [rax+rax+00h]
0x18000794c  mov     edx, eax; dwMessageId
0x18000794e  lea     rcx, [rsp+210h+SRWLock]; lpBuffer
0x180007953  call    ??0CErrorText@@QEAA@J@Z; CErrorText::CErrorText(long)
0x180007958  mov     rcx, [rax]
0x18000795b  lea     r8, asc_180063710; "???"
0x180007962  test    rcx, rcx
0x180007965  cmovnz  r8, rcx
0x180007969  lea     rdx, EVENT_FAILED_HIVE_UNLOAD
0x180007970  call    McTemplateU0z_EtwEventWriteTransfer
0x180007975  mov     r14d, 2
0x18000797b  test    r14b, 2
0x18000797f  jz      short loc_180007992
0x180007981  mov     rcx, [rsp+210h+SRWLock]; hMem
0x180007986  call    cs:__imp_LocalFree
0x18000798d  nop     dword ptr [rax+rax+00h]
0x180007992  mov     rcx, [rbp+118h]; this
0x180007999  mov     [rsp+210h+var_1E8], rdi; char *
0x18000799e  lea     rax, aForceUnloadFai; "Force unload failed for key <%ws>."
0x1800079a5  mov     qword ptr [rsp+210h+var_1F0], rax; int
0x1800079aa  mov     r9d, ebx; char *
0x1800079ad  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800079b4  mov     edx, 1D1h; void *
0x1800079b9  call    ?Return_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x1800079be  mov     ebx, eax
0x1800079c0  lea     rcx, [rsp+210h+KeyHandle]
0x1800079c5  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
  ... truncated ...
```
