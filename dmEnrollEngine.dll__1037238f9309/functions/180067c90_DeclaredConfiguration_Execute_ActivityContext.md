# DeclaredConfiguration::Execute(ActivityContext *)

- ea: `0x180067c90`
- end: `0x180068074`
- name: `?Execute@DeclaredConfiguration@@UEAAJPEAVActivityContext@@@Z`
- size: `996`
- prototype: `__int64 __fastcall(DeclaredConfiguration *this, struct ActivityContext *)`
- caller_count: `0`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180006950`
- `0x18000de50`
- `0x180010f8c`
- `0x180019e8c`
- `0x18001a86c`
- `0x18001aec8`
- `0x18001f98c`
- `0x180021934`
- `0x18002c3b4`
- `0x18002c648`
- `0x18002c664`
- `0x18002c680`
- `0x18002e1a0`
- `0x180033468`
- `0x18003b068`
- `0x18004e07c`
- `0x180067a90`
- `0x180067ac4`
- `0x180067c90`
- `0x1800681d8`
- `0x18006828c`
- `0x180073560`
- `0x1800763f8`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180067cd8`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180067cd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067dc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067dc9`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180067ef0`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180067ef0`
- `DeclaredConfigurationAPI!DeclaredConfigurationOrchestrator_DeleteAllRequestsForEnrollmentIdSid` at `0x180067e48`
- `DeclaredConfigurationAPI!DeclaredConfigurationOrchestrator_DeleteAllRequestsForEnrollmentIdSid` at `0x180067e48`
- `DeclaredConfigurationAPI!DeclaredConfigurationStore_DeleteEnrollmentIdSid2` at `0x180067f6a`
- `DeclaredConfigurationAPI!DeclaredConfigurationStore_DeleteEnrollmentIdSid2` at `0x180067f6a`
- `DeclaredConfigurationAPI!DeclaredConfigurationStore_GetRootFolderForCDNDownload` at `0x180067e71`
- `DeclaredConfigurationAPI!DeclaredConfigurationStore_GetRootFolderForCDNDownload` at `0x180067e71`
- `DeclaredConfigurationAPI!DeclaredConfigurationStore_WaitForDeletingRequests` at `0x180067d2d`
- `DeclaredConfigurationAPI!DeclaredConfigurationStore_WaitForDeletingRequests` at `0x180067d2d`
- `DeclaredConfiguration!DMOrchestratorDeletePerEnrollmentScenario` at `0x180067d23`
- `DeclaredConfiguration!DMOrchestratorDeletePerEnrollmentScenario` at `0x180067d23`

## string_xrefs

- `0x180067def`: `Acquire DeclaredConfiguration mutex lock failed`
- `0x180067d18`: `MSFTExtensibilityMIProviderConfig`
- `0x180067d3f`: `Global\DeclaredConfigurationMutex`

## pseudocode

```c
// Hidden C++ exception states: #wind=30
__int64 __fastcall DeclaredConfiguration::Execute(DeclaredConfiguration *this, struct ActivityContext *a2)
{
  __int64 v4; // rdx
  signed int KeyAsString; // ebx
  const unsigned __int16 *v6; // rcx
  int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // r8
  const unsigned __int16 *v10; // rcx
  __int64 v11; // r8
  signed int LastError; // eax
  int v13; // ecx
  int RootFolderForCDNDownload; // ebx
  __int64 v15; // rdi
  struct _GUID v16; // xmm6
  unsigned __int16 *v17; // rdx
  __int128 *v18; // rdx
  int v19; // ebx
  CEnrollmentLogger *Logger; // rax
  __int64 v21; // r8
  __int64 v22; // r8
  int v24; // [rsp+38h] [rbp-D0h] BYREF
  int v25; // [rsp+3Ch] [rbp-CCh] BYREF
  __int64 v26; // [rsp+40h] [rbp-C8h] BYREF
  unsigned __int16 *v27; // [rsp+48h] [rbp-C0h] BYREF
  int v28; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v29; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v30; // [rsp+60h] [rbp-A8h] BYREF
  __int128 v31; // [rsp+68h] [rbp-A0h] BYREF
  __m128i si128; // [rsp+78h] [rbp-90h]
  struct _GUID v33; // [rsp+88h] [rbp-80h] BYREF
  char v34; // [rsp+98h] [rbp-70h]
  unsigned __int16 v35[40]; // [rsp+A8h] [rbp-60h] BYREF

  v25 = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v25, 0);
  if ( v25 != 16 )
  {
    LOBYTE(v4) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_Desktop>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_Desktop>::GetImpl'::`2'::impl,
      v4);
  }
  v27 = 0;
  v35[0] = 0;
  KeyAsString = ActivityContext::get_KeyAsString(a2, v35);
  if ( KeyAsString >= 0 )
  {
    DMOrchestratorDeletePerEnrollmentScenario(v35, L"MSFTExtensibilityMIProviderConfig");
    DeclaredConfigurationStore_WaitForDeletingRequests(v35);
    DeclaredConfigurationStore_DeleteScheduledTask(v6, 0);
    v30 = 0;
    v7 = _create___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
           &v30,
           L"Global\\DeclaredConfigurationMutex");
    KeyAsString = v7;
    if ( v7 >= 0 )
    {
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
        McGenEventWrite_EventWriteTransfer(
          MDM_ENTERPRISE_DIAGNOSTICS_Context,
          EnterpriseDiagnosticsDeclaredConfigurationUnenrollExecuteLockCreationSuccess,
          v9,
          1,
          &v33);
      v24 = 0;
      _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
        &v30,
        &v28,
        &v24,
        180000);
      if ( v24 )
      {
        LastError = GetLastError();
        KeyAsString = LastError;
        if ( LastError > 0 )
          KeyAsString = (unsigned __int16)LastError | 0x80070000;
        if ( byte_1800B0341 < 0 )
          McTemplateU0zzd_EventWriteTransfer(
            v13,
            (unsigned int)OrchestratorGenericFailure,
            (unsigned int)&wszURI,
            (unsigned int)L"Acquire DeclaredConfiguration mutex lock failed",
            KeyAsString);
      }
      else
      {
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
          McGenEventWrite_EventWriteTransfer(
            MDM_ENTERPRISE_DIAGNOSTICS_Context,
            EnterpriseDiagnosticsDeclaredConfigurationUnenrollExecuteLock,
            v11,
            1,
            &v33);
        BYTE1(v24) = 1;
        DeclaredConfigurationStore_DeleteScheduledTask(v10, v35);
        DeclaredConfigurationOrchestrator_DeleteAllRequestsForEnrollmentIdSid(v35);
        CDNDownload_DeleteAllRecordsForEnrollmentId((char *)v35);
        v26 = 0;
        *(_QWORD *)&v33.Data1 = &v26;
        *(_QWORD *)v33.Data4 = 0;
        v34 = 1;
        RootFolderForCDNDownload = DeclaredConfigurationStore_GetRootFolderForCDNDownload((unsigned __int16 **)v33.Data4);
        wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&v33);
        v15 = -1;
        if ( RootFolderForCDNDownload >= 0 )
          wil::RemoveDirectoryRecursiveNoThrow(v26, 0, -1);
        v16 = *(struct _GUID *)((char *)a2 + 8);
        LODWORD(v29) = 63;
        v33 = v16;
        KeyAsString = EEDBManager::GetEnrollmentType(&v33, (enum EnrollmentEnrollType *)&v29);
        if ( KeyAsString >= 0 )
        {
          if ( !*((_DWORD *)this + 6) )
          {
            v33 = v16;
            KeyAsString = EEDBManager::GetEnrollmentString(&v33, L"SID", &v27);
            if ( KeyAsString == -2147024894 )
              KeyAsString = DmGetActiveUserSid(&v27);
          }
          if ( KeyAsString >= 0 )
          {
            v31 = 0;
            si128 = _mm_load_si128((const __m128i *)&_xmm);
            LOWORD(v31) = 0;
            if ( *((_DWORD *)this + 6) )
            {
              v17 = L"Device";
              v15 = 6;
            }
            else
            {
              v17 = v27;
              do
                ++v15;
              while ( v27[v15] );
            }
            std::wstring::_Assign<unsigned short>(&v31, v17, v15);
            v18 = &v31;
            if ( si128.m128i_i64[1] > 7uLL )
              v18 = (__int128 *)v31;
            v19 = DeclaredConfigurationStore_DeleteEnrollmentIdSid2(v35, v18, 0, 63);
            if ( (int)(v19 + 0x80000000) >= 0 && v19 != -2147024894 )
            {
              Logger = CEnrollmentLogger::GetLogger();
              v33 = *(struct _GUID *)((char *)a2 + 8);
              CEnrollmentLogger::LogUnenrollDeclaredConfigurationFail(Logger, v19, &v33);
            }
            std::wstring::_Tidy_deallocate(&v31);
            std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v26);
            if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
              McGenEventWrite_EventWriteTransfer(
                MDM_ENTERPRISE_DIAGNOSTICS_Context,
                EnterpriseDiagnosticsDeclaredConfigurationUnenrollExecuteUnlock,
                v21,
                1,
                &v33);
            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v28);
            KeyAsString = 0;
            goto LABEL_38;
          }
        }
        std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v26);
        if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
          McGenEventWrite_EventWriteTransfer(
            MDM_ENTERPRISE_DIAGNOSTICS_Context,
            EnterpriseDiagnosticsDeclaredConfigurationUnenrollExecuteUnlock,
            v22,
            1,
            &v33);
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v28);
    }
    else if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) != 0 )
    {
      McTemplateU0dd_EventWriteTransfer(
        v8,
        EnterpriseDiagnosticsDeclaredConfigurationUnenrollExecuteLockCreationFailure,
        (unsigned int)v7,
        (unsigned int)v7);
    }
LABEL_38:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v30);
  }
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>(&v27);
  return (unsigned int)KeyAsString;
}

```

## disassembly

```asm
0x180067c90  mov     rax, rsp
0x180067c93  mov     [rax+8], rbx
0x180067c97  mov     [rax+18h], rsi
0x180067c9b  push    rbp
0x180067c9c  push    rdi
0x180067c9d  push    r12
0x180067c9f  push    r14
0x180067ca1  push    r15
0x180067ca3  lea     rbp, [rax-38h]
0x180067ca7  sub     rsp, 110h
0x180067cae  movaps  xmmword ptr [rax-38h], xmm6
0x180067cb2  mov     rax, cs:__security_cookie
0x180067cb9  xor     rax, rsp
0x180067cbc  mov     [rbp+30h+var_40], rax
0x180067cc0  mov     rsi, rdx
0x180067cc3  mov     r14, rcx
0x180067cc6  xor     r15d, r15d
0x180067cc9  mov     dword ptr [rsp+130h+var_100+4], r15d
0x180067cce  xor     r8d, r8d
0x180067cd1  lea     rdx, [rsp+130h+var_100+4]
0x180067cd6  xor     ecx, ecx
0x180067cd8  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180067cde  lea     r12d, [r15+1]
0x180067ce2  cmp     dword ptr [rsp+130h+var_100+4], 10h
0x180067ce7  jz      short loc_180067CF8
0x180067ce9  mov     dl, r12b
0x180067cec  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeclaredConfiguration_Desktop@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_Desktop@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_Desktop> `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_Desktop>::GetImpl(void)'::`2'::impl
0x180067cf3  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_Desktop@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_Desktop>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180067cf8  mov     [rsp+130h+var_F0], r15
0x180067cfd  mov     [rbp+30h+var_90], r15w
0x180067d02  lea     rdx, [rbp+30h+var_90]; unsigned __int16 *
0x180067d06  mov     rcx, rsi; this
0x180067d09  call    ?get_KeyAsString@ActivityContext@@QEAAJQEAG@Z; ActivityContext::get_KeyAsString(ushort * const)
0x180067d0e  mov     ebx, eax
0x180067d10  test    eax, eax
0x180067d12  js      loc_18006803B
0x180067d18  lea     rdx, aMsftextensibil; "MSFTExtensibilityMIProviderConfig"
0x180067d1f  lea     rcx, [rbp+30h+var_90]
0x180067d23  call    cs:__imp_DMOrchestratorDeletePerEnrollmentScenario
0x180067d29  lea     rcx, [rbp+30h+var_90]
0x180067d2d  call    cs:__imp_?DeclaredConfigurationStore_WaitForDeletingRequests@@YAJPEBG@Z; DeclaredConfigurationStore_WaitForDeletingRequests(ushort const *)
0x180067d33  xor     edx, edx; unsigned __int16 *
0x180067d35  call    ?DeclaredConfigurationStore_DeleteScheduledTask@@YAJPEBG0@Z; DeclaredConfigurationStore_DeleteScheduledTask(ushort const *,ushort const *)
0x180067d3a  mov     qword ptr [rsp+130h+var_D8], r15
0x180067d3f  lea     rdx, aGlobalDeclared; "Global\\DeclaredConfigurationMutex"
0x180067d46  lea     rcx, [rsp+130h+var_D8]
0x180067d4b  call    ?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180067d50  mov     ebx, eax
0x180067d52  test    eax, eax
0x180067d54  jns     short loc_180067D7A
0x180067d56  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 8
0x180067d5d  jz      loc_180068030
0x180067d63  mov     r9d, eax
0x180067d66  mov     r8d, eax
0x180067d69  lea     rdx, EnterpriseDiagnosticsDeclaredConfigurationUnenrollExecuteLockCreationFailure
0x180067d70  call    McTemplateU0dd_EventWriteTransfer
0x180067d75  jmp     loc_180068030
0x180067d7a  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 4
0x180067d81  jz      short loc_180067DA2
0x180067d83  lea     rax, [rbp+30h+var_B0]
0x180067d87  mov     [rsp+130h+var_110], rax
0x180067d8c  mov     r9d, r12d
0x180067d8f  lea     rdx, EnterpriseDiagnosticsDeclaredConfigurationUnenrollExecuteLockCreationSuccess
0x180067d96  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x180067d9d  call    McGenEventWrite_EventWriteTransfer
0x180067da2  mov     dword ptr [rsp+130h+var_100], r15d
0x180067da7  mov     r9d, 2BF20h
0x180067dad  lea     r8, [rsp+130h+var_100]
0x180067db2  lea     rdx, [rsp+130h+var_E8]
0x180067db7  lea     rcx, [rsp+130h+var_D8]
0x180067dbc  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180067dc1  nop
0x180067dc2  cmp     dword ptr [rsp+130h+var_100], r15d
0x180067dc7  jz      short loc_180067E0E
0x180067dc9  call    cs:__imp_GetLastError
0x180067dcf  mov     ebx, eax
0x180067dd1  test    eax, eax
0x180067dd3  jle     short loc_180067DDE
0x180067dd5  movzx   ebx, ax
0x180067dd8  or      ebx, 80070000h
0x180067dde  cmp     cs:byte_1800B0341, r15b
0x180067de5  jge     loc_180068025
0x180067deb  mov     dword ptr [rsp+130h+var_110], ebx
0x180067def  lea     r9, aAcquireDeclare; "Acquire DeclaredConfiguration mutex loc"...
0x180067df6  lea     r8, wszURI
0x180067dfd  lea     rdx, OrchestratorGenericFailure
0x180067e04  call    McTemplateU0zzd_EventWriteTransfer
0x180067e09  jmp     loc_180068025
0x180067e0e  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 4
0x180067e15  jz      short loc_180067E36
0x180067e17  lea     rax, [rbp+30h+var_B0]
0x180067e1b  mov     [rsp+130h+var_110], rax
0x180067e20  mov     r9d, r12d
0x180067e23  lea     rdx, EnterpriseDiagnosticsDeclaredConfigurationUnenrollExecuteLock
0x180067e2a  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x180067e31  call    McGenEventWrite_EventWriteTransfer
0x180067e36  mov     byte ptr [rsp+130h+var_100+1], r12b
0x180067e3b  lea     rdx, [rbp+30h+var_90]; unsigned __int16 *
0x180067e3f  call    ?DeclaredConfigurationStore_DeleteScheduledTask@@YAJPEBG0@Z; DeclaredConfigurationStore_DeleteScheduledTask(ushort const *,ushort const *)
0x180067e44  lea     rcx, [rbp+30h+var_90]
0x180067e48  call    cs:__imp_?DeclaredConfigurationOrchestrator_DeleteAllRequestsForEnrollmentIdSid@@YAJPEBG@Z; DeclaredConfigurationOrchestrator_DeleteAllRequestsForEnrollmentIdSid(ushort const *)
0x180067e4e  lea     rcx, [rbp+30h+var_90]; unsigned __int16 *
0x180067e52  call    ?CDNDownload_DeleteAllRecordsForEnrollmentId@@YAJPEBG@Z; CDNDownload_DeleteAllRecordsForEnrollmentId(ushort const *)
0x180067e57  mov     [rsp+130h+var_F8], r15
0x180067e5c  lea     rax, [rsp+130h+var_F8]
0x180067e61  mov     qword ptr [rbp+30h+var_B0.Data1], rax
0x180067e65  mov     qword ptr [rbp+30h+var_B0.Data4], r15
0x180067e69  mov     [rbp+30h+var_A0], r12b
0x180067e6d  lea     rcx, [rbp+30h+var_B0.Data4]
0x180067e71  call    cs:__imp_?DeclaredConfigurationStore_GetRootFolderForCDNDownload@@YAJPEAPEAG@Z; DeclaredConfigurationStore_GetRootFolderForCDNDownload(ushort * *)
0x180067e77  mov     ebx, eax
0x180067e79  lea     rcx, [rbp+30h+var_B0]
0x180067e7d  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x180067e82  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180067e86  test    ebx, ebx
0x180067e88  js      short loc_180067E99
0x180067e8a  mov     r8, rdi
0x180067e8d  xor     edx, edx
0x180067e8f  mov     rcx, [rsp+130h+var_F8]
0x180067e94  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x180067e99  movups  xmm6, xmmword ptr [rsi+8]
0x180067e9d  mov     dword ptr [rsp+130h+var_E0], 3Fh ; '?'
0x180067ea5  movdqu  xmmword ptr [rbp+30h+var_B0.Data1], xmm6
0x180067eaa  lea     rdx, [rsp+130h+var_E0]; enum EnrollmentEnrollType *
0x180067eaf  lea     rcx, [rbp+30h+var_B0]; struct _GUID
0x180067eb3  call    ?GetEnrollmentType@EEDBManager@@SAJU_GUID@@PEAW4EnrollmentEnrollType@@@Z; EEDBManager::GetEnrollmentType(_GUID,EnrollmentEnrollType *)
0x180067eb8  mov     ebx, eax
0x180067eba  test    eax, eax
0x180067ebc  js      loc_180067FF1
0x180067ec2  cmp     [r14+18h], r15d
0x180067ec6  jnz     short loc_180067EF8
0x180067ec8  movdqa  xmmword ptr [rbp+30h+var_B0.Data1], xmm6
0x180067ecd  lea     r8, [rsp+130h+var_F0]; unsigned __int16 **
0x180067ed2  lea     rdx, aSid; "SID"
0x180067ed9  lea     rcx, [rbp+30h+var_B0]; struct _GUID
0x180067edd  call    ?GetEnrollmentString@EEDBManager@@CAJU_GUID@@PEBGPEAPEAG@Z; EEDBManager::GetEnrollmentString(_GUID,ushort const *,ushort * *)
0x180067ee2  mov     ebx, eax
0x180067ee4  cmp     eax, 80070002h
0x180067ee9  jnz     short loc_180067EF8
0x180067eeb  lea     rcx, [rsp+130h+var_F0]
0x180067ef0  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x180067ef6  mov     ebx, eax
0x180067ef8  test    ebx, ebx
0x180067efa  js      loc_180067FF1
0x180067f00  xorps   xmm0, xmm0
0x180067f03  movups  [rsp+130h+var_D8+8], xmm0
0x180067f08  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180067f10  movdqu  [rsp+130h+var_C8+8], xmm1
0x180067f16  mov     word ptr [rsp+130h+var_D8+8], r15w
0x180067f1c  cmp     [r14+18h], r15d
0x180067f20  jz      short loc_180067F30
0x180067f22  lea     rdx, aDevice; "Device"
0x180067f29  mov     edi, 6
0x180067f2e  jmp     short loc_180067F3F
0x180067f30  mov     rdx, [rsp+130h+var_F0]
0x180067f35  inc     rdi
0x180067f38  cmp     [rdx+rdi*2], r15w
0x180067f3d  jnz     short loc_180067F35
0x180067f3f  mov     r8, rdi
0x180067f42  lea     rcx, [rsp+130h+var_D8+8]
0x180067f47  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180067f4c  lea     rdx, [rsp+130h+var_D8+8]
0x180067f51  cmp     [rsp+130h+var_B8], 7
0x180067f57  cmova   rdx, qword ptr [rsp+130h+var_D8+8]
0x180067f5d  mov     r9d, 3Fh ; '?'
0x180067f63  xor     r8d, r8d
0x180067f66  lea     rcx, [rbp+30h+var_90]
0x180067f6a  call    cs:__imp_?DeclaredConfigurationStore_DeleteEnrollmentIdSid2@@YAJPEBG0W4_CSP_NAMESPACE_PREFIX@@W4EnrollmentEnrollType@@@Z; DeclaredConfigurationStore_DeleteEnrollmentIdSid2(ushort const *,ushort const *,_CSP_NAMESPACE_PREFIX,EnrollmentEnrollType)
0x180067f70  mov     ebx, eax
0x180067f72  mov     eax, 80000000h
0x180067f77  lea     ecx, [rbx+rax]
0x180067f7a  test    eax, ecx
0x180067f7c  jnz     short loc_180067FA3
0x180067f7e  cmp     ebx, 80070002h
0x180067f84  jz      short loc_180067FA3
0x180067f86  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180067f8b  movups  xmm0, xmmword ptr [rsi+8]
0x180067f8f  movdqu  xmmword ptr [rbp+30h+var_B0.Data1], xmm0
0x180067f94  lea     r8, [rbp+30h+var_B0]; struct _GUID
0x180067f98  mov     edx, ebx; int
0x180067f9a  mov     rcx, rax; this
0x180067f9d  call    ?LogUnenrollDeclaredConfigurationFail@CEnrollmentLogger@@QEAAXJU_GUID@@@Z; CEnrollmentLogger::LogUnenrollDeclaredConfigurationFail(long,_GUID)
0x180067fa2  nop
0x180067fa3  lea     rcx, [rsp+130h+var_D8+8]
0x180067fa8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180067fad  nop
0x180067fae  lea     rcx, [rsp+130h+var_F8]
0x180067fb3  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x180067fb8  nop
0x180067fb9  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 4
0x180067fc0  jz      short loc_180067FE2
0x180067fc2  lea     rax, [rbp+30h+var_B0]
0x180067fc6  mov     [rsp+130h+var_110], rax
0x180067fcb  mov     r9d, r12d
0x180067fce  lea     rdx, EnterpriseDiagnosticsDeclaredConfigurationUnenrollExecuteUnlock
0x180067fd5  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x180067fdc  call    McGenEventWrite_EventWriteTransfer
0x180067fe1  nop
0x180067fe2  lea     rcx, [rsp+130h+var_E8]
0x180067fe7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180067fec  mov     ebx, r15d
0x180067fef  jmp     short loc_180068030
0x180067ff1  lea     rcx, [rsp+130h+var_F8]
0x180067ff6  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x180067ffb  nop
0x180067ffc  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 4
0x180068003  jz      short loc_180068025
0x180068005  lea     rax, [rbp+30h+var_B0]
0x180068009  mov     [rsp+130h+var_110], rax
0x18006800e  mov     r9d, r12d
0x180068011  lea     rdx, EnterpriseDiagnosticsDeclaredConfigurationUnenrollExecuteUnlock
0x180068018  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x18006801f  call    McGenEventWrite_EventWriteTransfer
0x180068024  nop
0x180068025  lea     rcx, [rsp+130h+var_E8]
0x18006802a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18006802f  nop
0x180068030  lea     rcx, [rsp+130h+var_D8]
0x180068035  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18006803a  nop
0x18006803b  lea     rcx, [rsp+130h+var_F0]
0x180068040  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x180068045  mov     eax, ebx
0x180068047  mov     rcx, [rbp+30h+var_40]
0x18006804b  xor     rcx, rsp; StackCookie
0x18006804e  call    __security_check_cookie
0x180068053  lea     r11, [rsp+130h+var_20]
0x18006805b  mov     rbx, [r11+30h]
0x18006805f  mov     rsi, [r11+40h]
0x180068063  movaps  xmm6, xmmword ptr [r11-10h]
0x180068068  mov     rsp, r11
0x18006806b  pop     r15
0x18006806d  pop     r14
0x18006806f  pop     r12
0x180068071  pop     rdi
0x180068072  pop     rbp
0x180068073  retn
```
