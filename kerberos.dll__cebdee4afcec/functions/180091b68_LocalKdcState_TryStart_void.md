# LocalKdcState::TryStart(void)

- ea: `0x180091b68`
- end: `0x18009207e`
- name: `?TryStart@LocalKdcState@@YAJXZ`
- size: `1302`
- prototype: `__int64 __fastcall(LocalKdcState *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180077bf0`
- `0x1800d0330`

## callees

- `0x180033c68`
- `0x180066628`
- `0x180070a30`
- `0x180074230`
- `0x180074298`
- `0x180075444`
- `0x18008ae1c`
- `0x18008b70c`
- `0x180091a48`
- `0x180091a68`
- `0x180091b68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180091ce5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180091ce5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180091f78`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180092025`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180091f78`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180092025`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180091bb2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180091bb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091d14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091d61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091da9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091e90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091fa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091fb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091d14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091d61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091da9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091e90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091fa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091fb1`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180091bfe`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180091cce`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180091e68`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180091ef6`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180091f6e`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180092017`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180091bfe`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180091cce`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180091e68`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180091ef6`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180091f6e`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180092017`
- `ntdll!NtOpenEvent` at `0x180091c7c`
- `ntdll!NtOpenEvent` at `0x180091c7c`
- `ntdll!NtCreateEvent` at `0x180091c5c`
- `ntdll!NtCreateEvent` at `0x180091c5c`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180091d4f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180091d4f`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180091f98`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180091f98`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180091d05`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180091d05`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180091d9f`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180091e86`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180091d9f`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180091e86`

## string_xrefs

- `0x180092036`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x180091c16`: `\SAM_SERVICE_STARTED`
- `0x180091c8c`: `Failed to open or create event with status 0x0x%x`
- `0x180091d1e`: `OpenSCManager failed: 0x%x`
- `0x180091d6b`: `OpenService failed: 0x%x`
- `0x180091dba`: `QueryServiceConfig failed: 0x%0x`
- `0x180091e9a`: `QueryServiceConfig failed again: 0x%x`
- `0x180091f10`: `LocalKDC service is disabled`
- `0x180091fbb`: `StartService failed: 0x%0x`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall LocalKdcState::TryStart(LocalKdcState *this)
{
  LocalKdcState *v1; // rcx
  int v2; // edi
  NTSTATUS v3; // eax
  DWORD v4; // eax
  const char *v5; // r9
  SC_HANDLE v6; // rax
  DWORD LastError; // eax
  SC_HANDLE v8; // rax
  SC_HANDLE v9; // rbx
  DWORD v10; // eax
  DWORD v11; // eax
  struct _QUERY_SERVICE_CONFIGW **v12; // rax
  struct _QUERY_SERVICE_CONFIGW *v13; // rdi
  DWORD v14; // eax
  __int64 InitialState; // [rsp+20h] [rbp-49h]
  struct _QUERY_SERVICE_CONFIGW *v17; // [rsp+30h] [rbp-39h] BYREF
  SC_HANDLE v18; // [rsp+38h] [rbp-31h] BYREF
  _BYTE v19[8]; // [rsp+40h] [rbp-29h] BYREF
  RTL_SRWLOCK *v20; // [rsp+48h] [rbp-21h]
  _QWORD v21[2]; // [rsp+50h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  DWORD pcbBytesNeeded; // [rsp+D8h] [rbp+6Fh] BYREF
  void *EventHandle; // [rsp+E0h] [rbp+77h] BYREF
  SC_HANDLE v26; // [rsp+E8h] [rbp+7Fh] BYREF

  if ( dword_180148BE8 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180148BE8);
    if ( dword_180148BE8 == -1 )
    {
      atexit(LocalKdcState::TryStart_::_2_::_dynamic_atexit_destructor_for__s_localkdcAutoStartMutex__);
      Init_thread_footer(&dword_180148BE8);
    }
  }
  v20 = &stru_180146700;
  AcquireSRWLockExclusive(&stru_180146700);
  if ( byte_180146708 || dword_18014670C )
    goto LABEL_41;
  if ( LocalKdcState::IsLocalKdcSupported(v1) )
  {
    v21[0] = 2752552;
    v21[1] = L"\\SAM_SERVICE_STARTED";
    *(_QWORD *)&ObjectAttributes.Length = 48;
    memset(&ObjectAttributes.Attributes, 0, 24);
    EventHandle = 0;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)v21;
    v3 = NtCreateEvent(&EventHandle, 0x100000u, &ObjectAttributes, NotificationEvent, 0);
    v2 = v3;
    if ( v3 == 0x40000000 || v3 == -1073741771 )
      v2 = NtOpenEvent(&EventHandle, 0x100000u, &ObjectAttributes);
    if ( v2 < 0 )
    {
      KerbTracerT::Log(1, "LocalKdcState::TryStart", 161, "Failed to open or create event with status 0x0x%x", v2);
LABEL_13:
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&EventHandle);
      if ( !byte_180146708 )
      {
        dword_18014670C = 1;
        WakeByAddressAll(&dword_18014670C);
      }
      goto LABEL_49;
    }
    v4 = WaitForSingleObjectEx(EventHandle, 0x7530u, 0);
    if ( v4 == 258 )
    {
      KerbTracerT::Log(1, "LocalKdcState::TryStart", 168, "Timed out waiting for SAM database signal");
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&EventHandle);
      if ( !byte_180146708 )
      {
        dword_18014670C = 1;
        WakeByAddressAll(&dword_18014670C);
      }
      v2 = -1073741595;
      goto LABEL_49;
    }
    if ( v4 )
      wil::details::in1diag3::FailFast_Unexpected(
        retaddr,
        (void *)0xB0F,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v5);
    v6 = OpenSCManagerW(0, 0, 1u);
    v26 = v6;
    if ( !v6 )
    {
      LastError = GetLastError();
      KerbTracerT::Log(1, "LocalKdcState::TryStart", 177, "OpenSCManager failed: 0x%x", LastError);
LABEL_34:
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v26);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&EventHandle);
      if ( !byte_180146708 )
      {
        dword_18014670C = 1;
        WakeByAddressAll(&dword_18014670C);
      }
      v2 = -1073741422;
      goto LABEL_49;
    }
    v8 = OpenServiceW(v6, L"LOCALKDC", 0x15u);
    v9 = v8;
    v18 = v8;
    if ( !v8 )
    {
      v10 = GetLastError();
      KerbTracerT::Log(1, "LocalKdcState::TryStart", 185, "OpenService failed: 0x%x", v10);
LABEL_33:
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v18);
      goto LABEL_34;
    }
    v17 = 0;
    pcbBytesNeeded = 0;
    if ( !QueryServiceConfigW(v8, 0, 0, &pcbBytesNeeded) )
    {
      v11 = GetLastError();
      v2 = v11;
      if ( v11 != 122 )
      {
        LODWORD(InitialState) = v11;
        KerbTracerT::Log(1, "LocalKdcState::TryStart", 199, "QueryServiceConfig failed: 0x%0x", InitialState);
LABEL_24:
        if ( v2 > 0 )
          v2 = (unsigned __int16)v2 | 0xC0070000;
        utl::unique_ptr<unsigned short * [0],utl::default_delete<unsigned short * [0]>>::~unique_ptr<unsigned short * [0],utl::default_delete<unsigned short * [0]>>(&v17);
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v18);
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v26);
        goto LABEL_13;
      }
    }
    v12 = (struct _QUERY_SERVICE_CONFIGW **)utl::make_unique<unsigned char [0],0>(v19, pcbBytesNeeded);
    v13 = *v12;
    *v12 = 0;
    v17 = v13;
    utl::unique_ptr<unsigned short * [0],utl::default_delete<unsigned short * [0]>>::~unique_ptr<unsigned short * [0],utl::default_delete<unsigned short * [0]>>(v19);
    if ( !v13 )
    {
      utl::unique_ptr<unsigned short * [0],utl::default_delete<unsigned short * [0]>>::~unique_ptr<unsigned short * [0],utl::default_delete<unsigned short * [0]>>(&v17);
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v18);
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v26);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&EventHandle);
      if ( !byte_180146708 )
      {
        dword_18014670C = 1;
        WakeByAddressAll(&dword_18014670C);
      }
      v2 = -1073741801;
      goto LABEL_49;
    }
    if ( !QueryServiceConfigW(v9, v13, pcbBytesNeeded, &pcbBytesNeeded) )
    {
      v14 = GetLastError();
      KerbTracerT::Log(1, "LocalKdcState::TryStart", 213, "QueryServiceConfig failed again: 0x%x", v14);
      utl::unique_ptr<unsigned short * [0],utl::default_delete<unsigned short * [0]>>::~unique_ptr<unsigned short * [0],utl::default_delete<unsigned short * [0]>>(&v17);
      goto LABEL_33;
    }
    if ( v13->dwStartType == 4 )
    {
      KerbTracerT::Log(3, "LocalKdcState::TryStart", 222, "LocalKDC service is disabled");
    }
    else
    {
      if ( !StartServiceW(v9, 0, 0) )
      {
        v2 = GetLastError();
        if ( v2 != 1056 )
        {
          LODWORD(InitialState) = GetLastError();
          KerbTracerT::Log(1, "LocalKdcState::TryStart", 232, "StartService failed: 0x%0x", InitialState);
          goto LABEL_24;
        }
      }
      byte_180146708 = 1;
    }
    utl::unique_ptr<unsigned short * [0],utl::default_delete<unsigned short * [0]>>::~unique_ptr<unsigned short * [0],utl::default_delete<unsigned short * [0]>>(&v17);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v18);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v26);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&EventHandle);
    if ( !byte_180146708 )
    {
      dword_18014670C = 1;
      WakeByAddressAll(&dword_18014670C);
    }
LABEL_41:
    ReleaseSRWLockExclusive(&stru_180146700);
    return 0;
  }
  if ( !byte_180146708 )
  {
    dword_18014670C = 1;
    WakeByAddressAll(&dword_18014670C);
  }
  v2 = -1073741637;
LABEL_49:
  ReleaseSRWLockExclusive(&stru_180146700);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180091b68  push    rbp
0x180091b6a  push    rbx
0x180091b6b  push    rsi
0x180091b6c  push    rdi
0x180091b6d  push    r14
0x180091b6f  push    r15
0x180091b71  lea     rbp, [rsp-2Fh]
0x180091b76  sub     rsp, 98h
0x180091b7d  mov     ecx, cs:_tls_index
0x180091b83  mov     rax, gs:58h
0x180091b8c  mov     edx, 4
0x180091b91  mov     rax, [rax+rcx*8]
0x180091b95  mov     eax, [rdx+rax]
0x180091b98  cmp     cs:dword_180148BE8, eax
0x180091b9e  jg      loc_180092048
0x180091ba4  lea     r15, stru_180146700
0x180091bab  mov     [rbp+57h+var_78], r15
0x180091baf  mov     rcx, r15; SRWLock
0x180091bb2  call    cs:__imp_AcquireSRWLockExclusive
0x180091bb8  nop
0x180091bb9  xor     esi, esi
0x180091bbb  cmp     cs:byte_180146708, sil
0x180091bc2  jnz     loc_180091F75
0x180091bc8  mov     eax, cs:dword_18014670C
0x180091bce  test    eax, eax
0x180091bd0  jnz     loc_180091F75
0x180091bd6  lea     r14d, [rsi+1]
0x180091bda  mov     [rbp+57h+arg_1], r14b
0x180091bde  call    ?IsLocalKdcSupported@LocalKdcState@@YA_NXZ; LocalKdcState::IsLocalKdcSupported(void)
0x180091be3  test    al, al
0x180091be5  jnz     short loc_180091C0E
0x180091be7  cmp     cs:byte_180146708, sil
0x180091bee  jnz     short loc_180091C04
0x180091bf0  mov     cs:dword_18014670C, r14d
0x180091bf7  lea     rcx, dword_18014670C; Address
0x180091bfe  call    cs:__imp_WakeByAddressAll
0x180091c04  mov     edi, 0C00000BBh
0x180091c09  jmp     loc_180092022
0x180091c0e  mov     [rbp+57h+var_70], 2A0028h
0x180091c16  lea     rax, aSamServiceStar; "\\SAM_SERVICE_STARTED"
0x180091c1d  mov     [rbp+57h+var_68], rax
0x180091c21  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180091c29  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], rsi
0x180091c2d  mov     [rbp+57h+EventHandle], rsi
0x180091c31  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x180091c35  lea     rax, [rbp+57h+var_70]
0x180091c39  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180091c3d  xorps   xmm0, xmm0
0x180091c40  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180091c45  mov     [rsp+0C0h+InitialState], sil; InitialState
0x180091c4a  xor     r9d, r9d; EventType
0x180091c4d  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180091c51  mov     ebx, 100000h
0x180091c56  mov     edx, ebx; DesiredAccess
0x180091c58  lea     rcx, [rbp+57h+EventHandle]; EventHandle
0x180091c5c  call    cs:__imp_NtCreateEvent
0x180091c62  mov     edi, eax
0x180091c64  cmp     eax, 40000000h
0x180091c69  jz      short loc_180091C72
0x180091c6b  cmp     eax, 0C0000035h
0x180091c70  jnz     short loc_180091C84
0x180091c72  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180091c76  mov     edx, ebx; DesiredAccess
0x180091c78  lea     rcx, [rbp+57h+EventHandle]; EventHandle
0x180091c7c  call    cs:__imp_NtOpenEvent
0x180091c82  mov     edi, eax
0x180091c84  test    edi, edi
0x180091c86  jns     short loc_180091CD9
0x180091c88  mov     dword ptr [rsp+0C0h+InitialState], edi
0x180091c8c  lea     r9, aFailedToOpenOr; "Failed to open or create event with sta"...
0x180091c93  mov     r8d, 0A1h
0x180091c99  lea     rdx, aLocalkdcstateT; "LocalKdcState::TryStart"
0x180091ca0  mov     ecx, r14d
0x180091ca3  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180091ca8  nop
0x180091ca9  lea     rcx, [rbp+57h+EventHandle]
0x180091cad  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180091cb2  nop
0x180091cb3  cmp     cs:byte_180146708, sil
0x180091cba  jnz     loc_180092022
0x180091cc0  mov     cs:dword_18014670C, r14d
0x180091cc7  lea     rcx, dword_18014670C; Address
0x180091cce  call    cs:__imp_WakeByAddressAll
0x180091cd4  jmp     loc_180092022
0x180091cd9  xor     r8d, r8d; bAlertable
0x180091cdc  mov     edx, 7530h; dwMilliseconds
0x180091ce1  mov     rcx, [rbp+57h+EventHandle]; hHandle
0x180091ce5  call    cs:__imp_WaitForSingleObjectEx
0x180091ceb  cmp     eax, 102h
0x180091cf0  jz      loc_180091FD9
0x180091cf6  test    eax, eax
0x180091cf8  jnz     loc_180092032
0x180091cfe  mov     r8d, r14d; dwDesiredAccess
0x180091d01  xor     edx, edx; lpDatabaseName
0x180091d03  xor     ecx, ecx; lpMachineName
0x180091d05  call    cs:__imp_OpenSCManagerW
0x180091d0b  mov     [rbp+57h+arg_18], rax
0x180091d0f  test    rax, rax
0x180091d12  jnz     short loc_180091D3F
0x180091d14  call    cs:__imp_GetLastError
0x180091d1a  mov     dword ptr [rsp+0C0h+InitialState], eax
0x180091d1e  lea     r9, aOpenscmanagerF; "OpenSCManager failed: 0x%x"
0x180091d25  mov     r8d, 0B1h
0x180091d2b  lea     rdx, aLocalkdcstateT; "LocalKdcState::TryStart"
0x180091d32  mov     ecx, r14d
0x180091d35  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180091d3a  jmp     loc_180091ECB
0x180091d3f  mov     r8d, 15h; dwDesiredAccess
0x180091d45  lea     rdx, aLocalkdc; "LOCALKDC"
0x180091d4c  mov     rcx, rax; hSCManager
0x180091d4f  call    cs:__imp_OpenServiceW
0x180091d55  mov     rbx, rax
0x180091d58  mov     [rbp+57h+var_88], rax
0x180091d5c  test    rax, rax
0x180091d5f  jnz     short loc_180091D8C
0x180091d61  call    cs:__imp_GetLastError
0x180091d67  mov     dword ptr [rsp+0C0h+InitialState], eax
0x180091d6b  lea     r9, aOpenserviceFai; "OpenService failed: 0x%x"
0x180091d72  mov     r8d, 0B9h
0x180091d78  lea     rdx, aLocalkdcstateT; "LocalKdcState::TryStart"
0x180091d7f  mov     ecx, r14d
0x180091d82  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180091d87  jmp     loc_180091EC1
0x180091d8c  mov     [rbp+57h+var_90], rsi
0x180091d90  mov     [rbp+57h+pcbBytesNeeded], esi
0x180091d93  lea     r9, [rbp+57h+pcbBytesNeeded]; pcbBytesNeeded
0x180091d97  xor     r8d, r8d; cbBufSize
0x180091d9a  xor     edx, edx; lpServiceConfig
0x180091d9c  mov     rcx, rbx; hService
0x180091d9f  call    cs:__imp_QueryServiceConfigW
0x180091da5  test    eax, eax
0x180091da7  jnz     short loc_180091E05
0x180091da9  call    cs:__imp_GetLastError
0x180091daf  mov     edi, eax
0x180091db1  cmp     eax, 7Ah ; 'z'
0x180091db4  jz      short loc_180091E05
0x180091db6  mov     dword ptr [rsp+0C0h+InitialState], eax
0x180091dba  lea     r9, aQueryserviceco_0; "QueryServiceConfig failed: 0x%0x"
0x180091dc1  mov     r8d, 0C7h
0x180091dc7  lea     rdx, aLocalkdcstateT; "LocalKdcState::TryStart"
0x180091dce  mov     ecx, r14d
0x180091dd1  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180091dd6  test    edi, edi
0x180091dd8  jle     short loc_180091DE3
0x180091dda  movzx   edi, di
0x180091ddd  or      edi, 0C0070000h
0x180091de3  lea     rcx, [rbp+57h+var_90]
0x180091de7  call    ??1?$unique_ptr@$$BY0A@PEAGU?$default_delete@$$BY0A@PEAG@utl@@@utl@@QEAA@XZ; utl::unique_ptr<ushort * [0],utl::default_delete<ushort * [0]>>::~unique_ptr<ushort * [0],utl::default_delete<ushort * [0]>>(void)
0x180091dec  nop
0x180091ded  lea     rcx, [rbp+57h+var_88]
0x180091df1  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180091df6  nop
0x180091df7  lea     rcx, [rbp+57h+arg_18]
0x180091dfb  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180091e00  jmp     loc_180091CA9
0x180091e05  mov     edx, [rbp+57h+pcbBytesNeeded]
0x180091e08  lea     rcx, [rbp+57h+var_80]
0x180091e0c  call    ??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z; utl::make_unique<uchar [0],0>(unsigned __int64)
0x180091e11  mov     rdi, [rax]
0x180091e14  mov     [rax], rsi
0x180091e17  mov     [rbp+57h+var_90], rdi
0x180091e1b  lea     rcx, [rbp+57h+var_80]
0x180091e1f  call    ??1?$unique_ptr@$$BY0A@PEAGU?$default_delete@$$BY0A@PEAG@utl@@@utl@@QEAA@XZ; utl::unique_ptr<ushort * [0],utl::default_delete<ushort * [0]>>::~unique_ptr<ushort * [0],utl::default_delete<ushort * [0]>>(void)
0x180091e24  test    rdi, rdi
0x180091e27  jnz     short loc_180091E78
0x180091e29  lea     rcx, [rbp+57h+var_90]
0x180091e2d  call    ??1?$unique_ptr@$$BY0A@PEAGU?$default_delete@$$BY0A@PEAG@utl@@@utl@@QEAA@XZ; utl::unique_ptr<ushort * [0],utl::default_delete<ushort * [0]>>::~unique_ptr<ushort * [0],utl::default_delete<ushort * [0]>>(void)
0x180091e32  nop
0x180091e33  lea     rcx, [rbp+57h+var_88]
0x180091e37  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180091e3c  nop
0x180091e3d  lea     rcx, [rbp+57h+arg_18]
0x180091e41  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180091e46  nop
0x180091e47  lea     rcx, [rbp+57h+EventHandle]
0x180091e4b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180091e50  nop
0x180091e51  cmp     cs:byte_180146708, sil
0x180091e58  jnz     short loc_180091E6E
0x180091e5a  mov     cs:dword_18014670C, r14d
0x180091e61  lea     rcx, dword_18014670C; Address
0x180091e68  call    cs:__imp_WakeByAddressAll
0x180091e6e  mov     edi, 0C0000017h
0x180091e73  jmp     loc_180092022
0x180091e78  lea     r9, [rbp+57h+pcbBytesNeeded]; pcbBytesNeeded
0x180091e7c  mov     r8d, [rbp+57h+pcbBytesNeeded]; cbBufSize
0x180091e80  mov     rdx, rdi; lpServiceConfig
0x180091e83  mov     rcx, rbx; hService
0x180091e86  call    cs:__imp_QueryServiceConfigW
0x180091e8c  test    eax, eax
0x180091e8e  jnz     short loc_180091F06
0x180091e90  call    cs:__imp_GetLastError
0x180091e96  mov     dword ptr [rsp+0C0h+InitialState], eax
0x180091e9a  lea     r9, aQueryserviceco_1; "QueryServiceConfig failed again: 0x%x"
0x180091ea1  mov     r8d, 0D5h
0x180091ea7  lea     rdx, aLocalkdcstateT; "LocalKdcState::TryStart"
0x180091eae  mov     ecx, r14d
0x180091eb1  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180091eb6  nop
0x180091eb7  lea     rcx, [rbp+57h+var_90]
0x180091ebb  call    ??1?$unique_ptr@$$BY0A@PEAGU?$default_delete@$$BY0A@PEAG@utl@@@utl@@QEAA@XZ; utl::unique_ptr<ushort * [0],utl::default_delete<ushort * [0]>>::~unique_ptr<ushort * [0],utl::default_delete<ushort * [0]>>(void)
0x180091ec0  nop
0x180091ec1  lea     rcx, [rbp+57h+var_88]
0x180091ec5  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180091eca  nop
0x180091ecb  lea     rcx, [rbp+57h+arg_18]
0x180091ecf  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180091ed4  nop
0x180091ed5  lea     rcx, [rbp+57h+EventHandle]
0x180091ed9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180091ede  nop
0x180091edf  cmp     cs:byte_180146708, sil
0x180091ee6  jnz     short loc_180091EFC
0x180091ee8  mov     cs:dword_18014670C, r14d
0x180091eef  lea     rcx, dword_18014670C; Address
0x180091ef6  call    cs:__imp_WakeByAddressAll
0x180091efc  mov     edi, 0C0000192h
0x180091f01  jmp     loc_180092022
0x180091f06  cmp     dword ptr [rdi+4], 4
0x180091f0a  jnz     loc_180091F90
0x180091f10  lea     r9, aLocalkdcServic; "LocalKDC service is disabled"
0x180091f17  mov     r8d, 0DEh
0x180091f1d  lea     rdx, aLocalkdcstateT; "LocalKdcState::TryStart"
0x180091f24  mov     ecx, 3
0x180091f29  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180091f2e  nop
0x180091f2f  lea     rcx, [rbp+57h+var_90]
0x180091f33  call    ??1?$unique_ptr@$$BY0A@PEAGU?$default_delete@$$BY0A@PEAG@utl@@@utl@@QEAA@XZ; utl::unique_ptr<ushort * [0],utl::default_delete<ushort * [0]>>::~unique_ptr<ushort * [0],utl::default_delete<ushort * [0]>>(void)
0x180091f38  nop
0x180091f39  lea     rcx, [rbp+57h+var_88]
0x180091f3d  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180091f42  nop
0x180091f43  lea     rcx, [rbp+57h+arg_18]
0x180091f47  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180091f4c  nop
0x180091f4d  lea     rcx, [rbp+57h+EventHandle]
0x180091f51  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180091f56  nop
0x180091f57  cmp     cs:byte_180146708, sil
0x180091f5e  jnz     short loc_180091F75
0x180091f60  mov     cs:dword_18014670C, r14d
0x180091f67  lea     rcx, dword_18014670C; Address
0x180091f6e  call    cs:__imp_WakeByAddressAll
0x180091f74  nop
0x180091f75  mov     rcx, r15; SRWLock
0x180091f78  call    cs:__imp_ReleaseSRWLockExclusive
0x180091f7e  xor     eax, eax
0x180091f80  add     rsp, 98h
0x180091f87  pop     r15
0x180091f89  pop     r14
0x180091f8b  pop     rdi
0x180091f8c  pop     rsi
0x180091f8d  pop     rbx
0x180091f8e  pop     rbp
0x180091f8f  retn
0x180091f90  xor     r8d, r8d; lpServiceArgVectors
0x180091f93  xor     edx, edx; dwNumServiceArgs
0x180091f95  mov     rcx, rbx; hService
0x180091f98  call    cs:__imp_StartServiceW
0x180091f9e  test    eax, eax
0x180091fa0  jnz     short loc_180091FCD
0x180091fa2  call    cs:__imp_GetLastError
0x180091fa8  mov     edi, eax
0x180091faa  cmp     eax, 420h
0x180091faf  jz      short loc_180091FCD
0x180091fb1  call    cs:__imp_GetLastError
0x180091fb7  mov     dword ptr [rsp+0C0h+InitialState], eax
0x180091fbb  lea     r9, aStartserviceFa; "StartService failed: 0x%0x"
0x180091fc2  mov     r8d, 0E8h
0x180091fc8  jmp     loc_180091DC7
0x180091fcd  mov     cs:byte_180146708, r14b
0x180091fd4  jmp     loc_180091F2F
0x180091fd9  lea     r9, aTimedOutWaitin; "Timed out waiting for SAM database sign"...
0x180091fe0  mov     r8d, 0A8h
0x180091fe6  lea     rdx, aLocalkdcstateT; "LocalKdcState::TryStart"
0x180091fed  mov     ecx, r14d
0x180091ff0  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180091ff5  nop
0x180091ff6  lea     rcx, [rbp+57h+EventHandle]
0x180091ffa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180091fff  nop
0x180092000  cmp     cs:byte_180146708, sil
0x180092007  jnz     short loc_18009201D
0x180092009  mov     cs:dword_18014670C, r14d
0x180092010  lea     rcx, dword_18014670C; Address
0x180092017  call    cs:__imp_WakeByAddressAll
0x18009201d  mov     edi, 0C00000E5h
0x180092022  mov     rcx, r15; SRWLock
0x180092025  call    cs:__imp_ReleaseSRWLockExclusive
0x18009202b  mov     eax, edi
0x18009202d  jmp     loc_180091F80
0x180092032  mov     rcx, [rbp+5Fh]; this
0x180092036  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18009203d  mov     edx, 0B0Fh; void *
0x180092042  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180092048  lea     rcx, dword_180148BE8
0x18009204f  call    _Init_thread_header
0x180092054  cmp     cs:dword_180148BE8, 0FFFFFFFFh
0x18009205b  jnz     loc_180091BA4
0x180092061  lea     rcx, _LocalKdcState__TryStart____2____dynamic_atexit_destructor_for__s_localkdcAutoStartMutex__; void (__cdecl *)()
  ... truncated ...
```
