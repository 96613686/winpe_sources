# NlmDomain::AuthenticateForInterface(_GUID const &)

- ea: `0x18009c04c`
- end: `0x18009c6dd`
- name: `?AuthenticateForInterface@NlmDomain@@AEAAJAEBU_GUID@@@Z`
- size: `1681`
- prototype: `int(NlmDomain *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18009c004`

## callees

- `0x180009990`
- `0x18000abbc`
- `0x18000e190`
- `0x180018968`
- `0x18001c800`
- `0x180026e4c`
- `0x18004a868`
- `0x18004c208`
- `0x18004ccc8`
- `0x18004e0a8`
- `0x18007ec80`
- `0x18008791c`
- `0x18009c04c`
- `0x1800a88a0`
- `0x1800c6748`
- `0x18012c220`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18009c571`
- `ntdll!RtlFreeUnicodeString` at `0x18009c698`
- `ntdll!RtlFreeUnicodeString` at `0x18009c571`
- `ntdll!RtlFreeUnicodeString` at `0x18009c698`
- `ntdll!RtlStringFromGUID` at `0x18009c0e7`
- `ntdll!RtlStringFromGUID` at `0x18009c0e7`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18009c14d`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18009c14d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009c562`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009c689`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009c562`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009c689`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009c35f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009c35f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c15f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c3e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c15f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c3e7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18009c21f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18009c300`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18009c21f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18009c300`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18009c270`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18009c270`

## string_xrefs

- `0x18009c0fc`: `onecore\net\netprofiles\service\src\domain\lib\authentication.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall NlmDomain::AuthenticateForInterface(
        NlmDomain *this,
        struct _RTL_CRITICAL_SECTION *a2,
        int a3,
        int a4)
{
  LPCRITICAL_SECTION v4; // r15
  NlmDomain *v5; // r13
  NlmDomain *v6; // r12
  NTSTATUS v7; // eax
  int v8; // r9d
  int v9; // ecx
  HANDLE Event; // rax
  void *v11; // rdx
  unsigned int v12; // r8d
  const char *v13; // r9
  HANDLE v14; // rbx
  __int64 v15; // rcx
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  ULONGLONG TickCount64; // rdi
  DWORD v20; // r9d
  void *v21; // rdx
  int v22; // ecx
  DWORD v23; // ebx
  __int64 v24; // r8
  __int64 v25; // r9
  signed int v26; // esi
  int *v27; // rdx
  char *v28; // rdx
  unsigned __int64 v29; // rax
  int v30; // r8d
  int v31; // r9d
  DWORD v32; // ebx
  signed int LastError; // eax
  __int64 v34; // rcx
  wil::details *v35; // rcx
  wil *v36; // rcx
  const char *v37; // r9
  char v38; // al
  char v39; // al
  char v40; // al
  int v41; // ecx
  int v42; // r8d
  int v43; // r9d
  unsigned __int8 v45; // r12
  NlmDomain *v46; // rdi
  __int64 *v47; // rbx
  int v48; // eax
  int v49; // r8d
  int v50; // [rsp+20h] [rbp-108h]
  int v51; // [rsp+40h] [rbp-E8h] BYREF
  int v52[2]; // [rsp+48h] [rbp-E0h] BYREF
  NlmDomain *v53; // [rsp+50h] [rbp-D8h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+58h] [rbp-D0h] BYREF
  std::_Ref_count_base *v55[2]; // [rsp+60h] [rbp-C8h] BYREF
  NlmDomain *v56; // [rsp+70h] [rbp-B8h]
  NlmDomain *v57; // [rsp+78h] [rbp-B0h] BYREF
  GUID v58; // [rsp+80h] [rbp-A8h]
  _QWORD v59[3]; // [rsp+90h] [rbp-98h] BYREF
  char v60; // [rsp+A8h] [rbp-80h]
  __int128 *v61; // [rsp+B0h] [rbp-78h]
  char v62; // [rsp+B8h] [rbp-70h]
  struct _UNICODE_STRING GuidString; // [rsp+C0h] [rbp-68h] BYREF
  HANDLE Handles[2]; // [rsp+D0h] [rbp-58h] BYREF
  __int128 v65; // [rsp+E0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v4 = a2;
  v5 = this;
  v53 = this;
  v6 = this;
  v56 = this;
  lpCriticalSection = a2;
  if ( (unsigned int)dword_1801BD288 > 5 )
  {
    *(_QWORD *)v52 = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(
      (_DWORD)this,
      (unsigned int)byte_18019B5F9,
      a3,
      a4,
      (__int64)v52);
  }
  GuidString = 0;
  v59[2] = &GuidString;
  v60 = 1;
  if ( (Microsoft_Windows_NlaSvcEnableBits & 0x80u) != 0 )
  {
    v7 = RtlStringFromGUID((const GUID *const)v4, &GuidString);
    v9 = (int)retaddr;
    if ( v7 < 0 )
      wil::details::in1diag3::_Log_NtStatus(
        retaddr,
        (void *)0x1C2,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\domain\\lib\\authentication.cpp",
        (const char *)(unsigned int)v7,
        v50);
    if ( (Microsoft_Windows_NlaSvcEnableBits & 0x80u) != 0 )
      McTemplateU0zzqq_EventWriteTransfer(v9, (unsigned int)StartLdapAuth, GuidString.Buffer, v8, v50, 0);
  }
  v65 = 0;
  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  try
  {
    try
    {
      v14 = Event;
      if ( !Event )
        wil::details::in1diag3::Throw_GetLastError(retaddr, v11, v12, v13);
      GetLastError();
      _reset___shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEAAXPEAX_Z(
        &v65,
        v14);
      v61 = &v65;
      v62 = 1;
      *(_OWORD *)v55 = 0;
      v57 = v5;
      v58 = *(GUID *)&v4->DebugInfo;
      v15 = *((_QWORD *)&v65 + 1);
      if ( *((_QWORD *)&v65 + 1) )
      {
        _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v65 + 1) + 8LL));
        v15 = *((_QWORD *)&v65 + 1);
      }
      v59[0] = v65;
      v59[1] = v15;
      WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_long__NlmDomain::AuthenticateForInterface_::_12_::_lambda_3___(
        v5,
        v55,
        &v57);
      std::shared_ptr<Concurrency::details::_ExceptionHolder>::~shared_ptr<Concurrency::details::_ExceptionHolder>(v59);
      if ( (unsigned int)dword_1801BD288 > 4 )
      {
        *(_QWORD *)v52 = v4;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(
          v16,
          (unsigned int)&word_18019B6F6,
          v17,
          v18,
          (__int64)v52);
      }
      TickCount64 = GetTickCount64();
      Handles[0] = *((HANDLE *)v55[0] + 9);
      Handles[1] = *((HANDLE *)v5 + 98);
      if ( NlmDomain::s_alwaysExpectDomainController )
        v20 = -1;
      else
        v20 = NlmDomain::s_ldapAsyncTimeoutInMs;
      v23 = WaitForMultipleObjects(2u, Handles, 0, v20);
      if ( v23 )
      {
        if ( v23 == 1 )
        {
          v26 = -1610087225;
          if ( (unsigned int)dword_1801BD288 > 4 )
          {
            *(_QWORD *)v52 = v4;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(
              v22,
              (unsigned int)&dword_18019B444,
              v24,
              v25,
              (__int64)v52);
          }
          v29 = GetTickCount64() - TickCount64;
          if ( v29 >= 0x3E8 )
            goto LABEL_47;
          v32 = 1000 - v29;
          if ( (unsigned int)dword_1801BD288 > 4 )
          {
            v51 = 1000 - v29;
            *(_QWORD *)v52 = v4;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_1801BD288,
              (unsigned int)byte_18019B3D3,
              v30,
              v31,
              (__int64)v52,
              (__int64)&v51);
          }
          if ( WaitForSingleObject(*((HANDLE *)v55[0] + 9), v32) )
            goto LABEL_47;
          v26 = *((_DWORD *)v55[0] + 22);
          if ( v26 >= 0 )
          {
            if ( (unsigned int)dword_1801BD288 <= 4 )
              goto LABEL_47;
            v27 = (int *)byte_18019B379;
            goto LABEL_21;
          }
          if ( (unsigned int)dword_1801BD288 <= 4 )
            goto LABEL_47;
          v28 = byte_18019B31D;
        }
        else
        {
          if ( v23 == 258 )
          {
            v26 = -2147023436;
            if ( (unsigned int)dword_1801BD288 <= 4 )
              goto LABEL_47;
            v51 = -2147023436;
            v28 = byte_18019B59B;
LABEL_46:
            *(_QWORD *)v52 = v4;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_1801BD288,
              (_DWORD)v28,
              v24,
              v25,
              (__int64)v52,
              (__int64)&v51);
            goto LABEL_47;
          }
          LastError = GetLastError();
          v26 = LastError;
          if ( LastError > 0 )
            v26 = (unsigned __int16)LastError | 0x80070000;
          if ( v23 != -1 )
            MicrosoftTelemetryAssertTriggeredNoArgs(v34, v21, v24, v25);
          if ( (unsigned int)dword_1801BD288 <= 2 )
            goto LABEL_47;
          v28 = (char *)word_18019B54A;
        }
      }
      else
      {
        v26 = *((_DWORD *)v55[0] + 22);
        if ( v26 >= 0 )
        {
          if ( (unsigned int)dword_1801BD288 <= 4 )
          {
LABEL_47:
            if ( v55[1] )
              std::_Ref_count_base::_Decref(v55[1]);
            if ( (_QWORD)v65 )
              v35 = *(wil::details **)v65;
            else
              v35 = 0;
            wil::details::SetEvent(v35, v21);
            std::shared_ptr<Concurrency::details::_ExceptionHolder>::~shared_ptr<Concurrency::details::_ExceptionHolder>(&v65);
            goto LABEL_91;
          }
          v27 = &dword_18019B69C;
LABEL_21:
          *(_QWORD *)v52 = v4;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(
            v22,
            (_DWORD)v27,
            v24,
            v25,
            (__int64)v52);
          goto LABEL_47;
        }
        if ( (unsigned int)dword_1801BD288 <= 2 )
          goto LABEL_47;
        v28 = (char *)&unk_18019B640;
      }
      v51 = v26;
      goto LABEL_46;
    }
    catch ( ... )
    {
      v48 = wil::ResultFromCaughtException(v36);
      v52[0] = v48;
      LODWORD(v36) = dword_1801BD288;
      if ( (unsigned int)dword_1801BD288 > 2 )
      {
        v51 = v48;
        *(_QWORD *)&v65 = lpCriticalSection;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1801BD288,
          (unsigned int)&word_18019B4F6,
          v49,
          (_DWORD)v37,
          (__int64)&v65,
          (__int64)&v51);
      }
      v26 = v52[0];
      v5 = v53;
      v4 = lpCriticalSection;
      v6 = v53;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x27A,
                           (unsigned int)"onecore\\net\\netprofiles\\service\\src\\domain\\lib\\authentication.cpp",
                           v37);
  }
LABEL_91:
  v38 = Microsoft_Windows_NlaSvcEnableBits;
  if ( (Microsoft_Windows_NlaSvcEnableBits & 0x80u) != 0 )
  {
    if ( v26 < 0 && (Microsoft_Windows_NlaSvcEnableBits & 0x200) != 0 )
    {
      v39 = v26;
      if ( (v26 & 0x1FFF0000) != 0x70000 )
        v39 = v26;
      McTemplateU0zzqq_EventWriteTransfer(
        (_DWORD)v36,
        (unsigned int)FailedLdapAuth,
        GuidString.Buffer,
        (_DWORD)v37,
        v50,
        v39);
      v38 = Microsoft_Windows_NlaSvcEnableBits;
    }
    if ( v38 < 0 )
    {
      v40 = v26;
      if ( (v26 & 0x1FFF0000) != 0x70000 )
        v40 = v26;
      McTemplateU0zzqq_EventWriteTransfer(
        (_DWORD)v36,
        (unsigned int)StopLdapAuth,
        GuidString.Buffer,
        (_DWORD)v37,
        v50,
        v40);
    }
  }
  lpCriticalSection = 0;
  wil::EnterCriticalSection(&lpCriticalSection, (char *)v5 + 792);
  if ( *((_BYTE *)v6 + 1056) )
  {
    if ( (unsigned int)dword_1801BD288 > 5 )
    {
      v53 = (NlmDomain *)v4;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(
        v41,
        (unsigned int)word_18019B4A2,
        v42,
        v43,
        (__int64)&v53);
    }
    *((_BYTE *)v6 + 1057) = 1;
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    RtlFreeUnicodeString(&GuidString);
    return 2684880071LL;
  }
  if ( v26 == -1610087225 )
  {
    if ( (unsigned int)dword_1801BD288 > 5 )
    {
      v53 = (NlmDomain *)v4;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(
        v41,
        (unsigned int)&word_18019B056,
        v42,
        v43,
        (__int64)&v53);
    }
    goto LABEL_82;
  }
  if ( v26 >= 0 )
  {
    v45 = 1;
    goto LABEL_73;
  }
  v45 = 0;
  if ( v26 != -2147023674 )
  {
LABEL_73:
    v46 = v56;
    v47 = std::_Tree<std::_Tmap_traits<_GUID,std::unique_ptr<PerInterfaceData>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::unique_ptr<PerInterfaceData>>>,0>>::_Find<_GUID>(
            (__int64 *)v56 + 123,
            v4);
    if ( v47 != *((__int64 **)v46 + 123) )
    {
      if ( (unsigned int)dword_1801BD288 > 5 )
      {
        v52[0] = v45;
        v53 = (NlmDomain *)v4;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1801BD288,
          (unsigned int)&byte_18019B0FF,
          v42,
          v43,
          (__int64)&v53,
          (__int64)v52);
      }
      *((_BYTE *)v47 + 90) = v45;
      *((_BYTE *)v47 + 91) = 1;
      if ( v45 )
        *((_BYTE *)v47 + 92) = 1;
    }
  }
  if ( (unsigned int)dword_1801BD288 > 5 )
  {
    v52[0] = v26;
    v51 = v45;
    v53 = (NlmDomain *)v4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v41,
      (unsigned int)&dword_18019B0A4,
      v42,
      v43,
      (__int64)&v53,
      (__int64)&v51,
      (__int64)v52);
  }
LABEL_82:
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  RtlFreeUnicodeString(&GuidString);
  return (unsigned int)v26;
}

```

## disassembly

```asm
0x18009c04c  mov     [rsp+arg_10], rbx
0x18009c051  push    rsi
0x18009c052  push    rdi
0x18009c053  push    r12
0x18009c055  push    r13
0x18009c057  push    r15
0x18009c059  sub     rsp, 100h
0x18009c060  mov     rax, cs:__security_cookie
0x18009c067  xor     rax, rsp
0x18009c06a  mov     [rsp+128h+var_38], rax
0x18009c072  mov     r15, rdx
0x18009c075  mov     r13, rcx
0x18009c078  mov     [rsp+128h+var_D8], rcx
0x18009c07d  mov     r12, rcx
0x18009c080  mov     [rsp+128h+var_B8], rcx
0x18009c085  mov     [rsp+128h+lpCriticalSection], rdx
0x18009c08a  mov     eax, cs:dword_1801BD288
0x18009c090  cmp     eax, 5
0x18009c093  jbe     short loc_18009C0B0
0x18009c095  mov     qword ptr [rsp+128h+var_E0], rdx
0x18009c09a  lea     rax, [rsp+128h+var_E0]
0x18009c09f  mov     qword ptr [rsp+128h+var_108], rax; int
0x18009c0a4  lea     rdx, byte_18019B5F9
0x18009c0ab  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &)
0x18009c0b0  xorps   xmm0, xmm0
0x18009c0b3  movups  xmmword ptr [rsp+128h+GuidString.Length], xmm0
0x18009c0bb  lea     rax, [rsp+128h+GuidString]
0x18009c0c3  mov     [rsp+128h+var_88], rax
0x18009c0cb  mov     [rsp+128h+var_80], 1
0x18009c0d3  cmp     byte ptr cs:Microsoft_Windows_NlaSvcEnableBits, 0
0x18009c0da  jge     short loc_18009C133
0x18009c0dc  lea     rdx, [rsp+128h+GuidString]; GuidString
0x18009c0e4  mov     rcx, r15; Guid
0x18009c0e7  call    cs:__imp_RtlStringFromGUID
0x18009c0ed  mov     rcx, [rsp+128h]; this
0x18009c0f5  test    eax, eax
0x18009c0f7  jns     short loc_18009C10D
0x18009c0f9  mov     r9d, eax; char *
0x18009c0fc  lea     r8, aOnecoreNetNetp_59; "onecore\\net\\netprofiles\\service\\src"...
0x18009c103  mov     edx, 1C2h; void *
0x18009c108  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x18009c10d  cmp     byte ptr cs:Microsoft_Windows_NlaSvcEnableBits, 0
0x18009c114  jge     short loc_18009C133
0x18009c116  mov     dword ptr [rsp+128h+var_100], 0
0x18009c11e  mov     r8, [rsp+128h+GuidString.Buffer]
0x18009c126  lea     rdx, StartLdapAuth
0x18009c12d  call    McTemplateU0zzqq_EventWriteTransfer
0x18009c132  nop
0x18009c133  xorps   xmm1, xmm1
0x18009c136  movdqu  [rsp+128h+var_48], xmm1
0x18009c13f  xor     edx, edx; lpName
0x18009c141  xor     ecx, ecx; lpEventAttributes
0x18009c143  mov     r9d, 1F0003h; dwDesiredAccess
0x18009c149  lea     r8d, [rdx+1]; dwFlags
0x18009c14d  call    cs:__imp_CreateEventExW
0x18009c153  mov     rbx, rax
0x18009c156  test    rax, rax
0x18009c159  jz      loc_18009C6CE
0x18009c15f  call    cs:__imp_GetLastError
0x18009c165  mov     rdx, rbx
0x18009c168  lea     rcx, [rsp+128h+var_48]
0x18009c170  call    ?reset@?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEAAXPEAX@Z
0x18009c175  nop
0x18009c176  lea     rax, [rsp+128h+var_48]
0x18009c17e  mov     [rsp+128h+var_78], rax
0x18009c186  mov     [rsp+128h+var_70], 1
0x18009c18e  xorps   xmm0, xmm0
0x18009c191  movups  xmmword ptr [rsp+128h+var_C8], xmm0
0x18009c196  mov     [rsp+128h+var_B0], r13
0x18009c19b  movups  xmm1, xmmword ptr [r15]
0x18009c19f  movdqu  [rsp+128h+var_A8], xmm1
0x18009c1a8  mov     rcx, qword ptr [rsp+128h+var_48+8]
0x18009c1b0  test    rcx, rcx
0x18009c1b3  jz      short loc_18009C1C1
0x18009c1b5  lock inc dword ptr [rcx+8]
0x18009c1b9  mov     rcx, qword ptr [rsp+128h+var_48+8]
0x18009c1c1  mov     rax, qword ptr [rsp+128h+var_48]
0x18009c1c9  mov     [rsp+128h+var_98], rax
0x18009c1d1  mov     [rsp+128h+var_90], rcx
0x18009c1d9  lea     r8, [rsp+128h+var_B0]
0x18009c1de  lea     rdx, [rsp+128h+var_C8]
0x18009c1e3  mov     rcx, r13
0x18009c1e6  call    WcmCommon__ThreadPoolWorkQueue__SubmitWorkWithResults_long__NlmDomain__AuthenticateForInterface____12____lambda_3___
0x18009c1eb  nop
0x18009c1ec  lea     rcx, [rsp+128h+var_98]
0x18009c1f4  call    ??1?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@QEAA@XZ; std::shared_ptr<Concurrency::details::_ExceptionHolder>::~shared_ptr<Concurrency::details::_ExceptionHolder>(void)
0x18009c1f9  mov     eax, cs:dword_1801BD288
0x18009c1ff  cmp     eax, 4
0x18009c202  jbe     short loc_18009C21F
0x18009c204  mov     qword ptr [rsp+128h+var_E0], r15
0x18009c209  lea     rax, [rsp+128h+var_E0]
0x18009c20e  mov     qword ptr [rsp+128h+var_108], rax
0x18009c213  lea     rdx, word_18019B6F6
0x18009c21a  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &)
0x18009c21f  call    cs:__imp_GetTickCount64
0x18009c225  mov     rdi, rax
0x18009c228  mov     rcx, [rsp+128h+var_C8]
0x18009c22d  mov     rdx, [rcx+48h]
0x18009c231  mov     [rsp+128h+Handles], rdx
0x18009c239  mov     rcx, [r13+310h]
0x18009c240  mov     [rsp+128h+var_50], rcx
0x18009c248  mov     cl, cs:?s_alwaysExpectDomainController@NlmDomain@@0U?$atomic@_N@std@@A; std::atomic<bool> NlmDomain::s_alwaysExpectDomainController
0x18009c24e  nop
0x18009c24f  test    cl, cl
0x18009c251  jz      short loc_18009C259
0x18009c253  or      r9d, 0FFFFFFFFh
0x18009c257  jmp     short loc_18009C261
0x18009c259  mov     r9d, cs:?s_ldapAsyncTimeoutInMs@NlmDomain@@0U?$atomic@K@std@@A; dwMilliseconds
0x18009c260  nop
0x18009c261  xor     r8d, r8d; bWaitAll
0x18009c264  lea     rdx, [rsp+128h+Handles]; lpHandles
0x18009c26c  lea     ecx, [r8+2]; nCount
0x18009c270  call    cs:__imp_WaitForMultipleObjects
0x18009c276  mov     ebx, eax
0x18009c278  test    eax, eax
0x18009c27a  jnz     short loc_18009C2CC
0x18009c27c  mov     rax, [rsp+128h+var_C8]
0x18009c281  mov     esi, [rax+58h]
0x18009c284  mov     eax, cs:dword_1801BD288
0x18009c28a  test    esi, esi
0x18009c28c  js      short loc_18009C2B7
0x18009c28e  cmp     eax, 4
0x18009c291  jbe     loc_18009C442
0x18009c297  lea     rdx, dword_18019B69C
0x18009c29e  lea     rax, [rsp+128h+var_E0]
0x18009c2a3  mov     qword ptr [rsp+128h+var_108], rax
0x18009c2a8  mov     qword ptr [rsp+128h+var_E0], r15
0x18009c2ad  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &)
0x18009c2b2  jmp     loc_18009C442
0x18009c2b7  cmp     eax, 2
0x18009c2ba  jbe     loc_18009C442
0x18009c2c0  lea     rdx, unk_18019B640
0x18009c2c7  jmp     loc_18009C418
0x18009c2cc  cmp     ebx, 1
0x18009c2cf  jnz     loc_18009C3A6
0x18009c2d5  mov     esi, 0A00804C7h
0x18009c2da  mov     eax, cs:dword_1801BD288
0x18009c2e0  cmp     eax, 4
0x18009c2e3  jbe     short loc_18009C300
0x18009c2e5  mov     qword ptr [rsp+128h+var_E0], r15
0x18009c2ea  lea     rax, [rsp+128h+var_E0]
0x18009c2ef  mov     qword ptr [rsp+128h+var_108], rax
0x18009c2f4  lea     rdx, dword_18019B444
0x18009c2fb  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &)
0x18009c300  call    cs:__imp_GetTickCount64
0x18009c306  sub     rax, rdi
0x18009c309  mov     ebx, 3E8h
0x18009c30e  cmp     rax, rbx
0x18009c311  jnb     loc_18009C442
0x18009c317  sub     ebx, eax
0x18009c319  mov     eax, cs:dword_1801BD288
0x18009c31f  cmp     eax, 4
0x18009c322  jbe     short loc_18009C354
0x18009c324  mov     [rsp+128h+var_E8], ebx
0x18009c328  mov     qword ptr [rsp+128h+var_E0], r15
0x18009c32d  lea     rax, [rsp+128h+var_E8]
0x18009c332  mov     [rsp+128h+var_100], rax
0x18009c337  lea     rax, [rsp+128h+var_E0]
0x18009c33c  mov     qword ptr [rsp+128h+var_108], rax
0x18009c341  lea     rdx, byte_18019B3D3
0x18009c348  lea     rcx, dword_1801BD288
0x18009c34f  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18009c354  mov     edx, ebx; dwMilliseconds
0x18009c356  mov     rcx, [rsp+128h+var_C8]
0x18009c35b  mov     rcx, [rcx+48h]; hHandle
0x18009c35f  call    cs:__imp_WaitForSingleObject
0x18009c365  test    eax, eax
0x18009c367  jnz     loc_18009C442
0x18009c36d  mov     rax, [rsp+128h+var_C8]
0x18009c372  mov     esi, [rax+58h]
0x18009c375  mov     eax, cs:dword_1801BD288
0x18009c37b  test    esi, esi
0x18009c37d  js      short loc_18009C394
0x18009c37f  cmp     eax, 4
0x18009c382  jbe     loc_18009C442
0x18009c388  lea     rdx, byte_18019B379
0x18009c38f  jmp     loc_18009C29E
0x18009c394  cmp     eax, 4
0x18009c397  jbe     loc_18009C442
0x18009c39d  lea     rdx, byte_18019B31D
0x18009c3a4  jmp     short loc_18009C418
0x18009c3a6  cmp     ebx, 102h
0x18009c3ac  jnz     short loc_18009C3E7
0x18009c3ae  mov     esi, 800705B4h
0x18009c3b3  mov     eax, cs:dword_1801BD288
0x18009c3b9  cmp     eax, 4
0x18009c3bc  jbe     loc_18009C442
0x18009c3c2  mov     [rsp+128h+var_E8], 800705B4h
0x18009c3ca  lea     rax, [rsp+128h+var_E8]
0x18009c3cf  mov     [rsp+128h+var_100], rax
0x18009c3d4  lea     rax, [rsp+128h+var_E0]
0x18009c3d9  mov     qword ptr [rsp+128h+var_108], rax
0x18009c3de  lea     rdx, byte_18019B59B
0x18009c3e5  jmp     short loc_18009C430
0x18009c3e7  call    cs:__imp_GetLastError
0x18009c3ed  mov     esi, eax
0x18009c3ef  test    eax, eax
0x18009c3f1  jle     short loc_18009C3FC
0x18009c3f3  movzx   esi, ax
0x18009c3f6  or      esi, 80070000h
0x18009c3fc  cmp     ebx, 0FFFFFFFFh
0x18009c3ff  jz      short loc_18009C406
0x18009c401  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009c406  mov     eax, cs:dword_1801BD288
0x18009c40c  cmp     eax, 2
0x18009c40f  jbe     short loc_18009C442
0x18009c411  lea     rdx, word_18019B54A
0x18009c418  lea     rax, [rsp+128h+var_E8]
0x18009c41d  mov     [rsp+128h+var_100], rax
0x18009c422  lea     rax, [rsp+128h+var_E0]
0x18009c427  mov     qword ptr [rsp+128h+var_108], rax
0x18009c42c  mov     [rsp+128h+var_E8], esi
0x18009c430  mov     qword ptr [rsp+128h+var_E0], r15
0x18009c435  lea     rcx, dword_1801BD288
0x18009c43c  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18009c441  nop
0x18009c442  mov     rcx, [rsp+128h+var_C8+8]; this
0x18009c447  test    rcx, rcx
0x18009c44a  jz      short loc_18009C452
0x18009c44c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18009c451  nop
0x18009c452  mov     rax, qword ptr [rsp+128h+var_48]
0x18009c45a  test    rax, rax
0x18009c45d  jz      short loc_18009C464
0x18009c45f  mov     rcx, [rax]
0x18009c462  jmp     short loc_18009C466
0x18009c464  xor     ecx, ecx; this
0x18009c466  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18009c46b  nop
0x18009c46c  lea     rcx, [rsp+128h+var_48]
0x18009c474  call    ??1?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@QEAA@XZ; std::shared_ptr<Concurrency::details::_ExceptionHolder>::~shared_ptr<Concurrency::details::_ExceptionHolder>(void)
0x18009c479  nop
0x18009c47a  jmp     short loc_18009C48D
0x18009c47c  mov     esi, [rsp+128h+var_E0]
0x18009c480  mov     r13, [rsp+128h+var_D8]
0x18009c485  mov     r15, [rsp+128h+lpCriticalSection]
0x18009c48a  mov     r12, r13
0x18009c48d  mov     eax, cs:Microsoft_Windows_NlaSvcEnableBits
0x18009c493  test    al, al
0x18009c495  jns     short loc_18009C504
0x18009c497  test    esi, esi
0x18009c499  jns     short loc_18009C4D5
0x18009c49b  test    byte ptr cs:Microsoft_Windows_NlaSvcEnableBits+1, 2
0x18009c4a2  jz      short loc_18009C4D5
0x18009c4a4  mov     eax, esi
0x18009c4a6  and     eax, 1FFF0000h
0x18009c4ab  cmp     eax, 70000h
0x18009c4b0  movzx   eax, si
0x18009c4b3  jz      short loc_18009C4B7
0x18009c4b5  mov     eax, esi
0x18009c4b7  mov     dword ptr [rsp+128h+var_100], eax
0x18009c4bb  mov     r8, [rsp+128h+GuidString.Buffer]
0x18009c4c3  lea     rdx, FailedLdapAuth
0x18009c4ca  call    McTemplateU0zzqq_EventWriteTransfer
0x18009c4cf  mov     eax, cs:Microsoft_Windows_NlaSvcEnableBits
0x18009c4d5  test    al, al
0x18009c4d7  jns     short loc_18009C504
0x18009c4d9  mov     eax, esi
0x18009c4db  and     eax, 1FFF0000h
0x18009c4e0  cmp     eax, 70000h
0x18009c4e5  movzx   eax, si
0x18009c4e8  jz      short loc_18009C4EC
0x18009c4ea  mov     eax, esi
0x18009c4ec  mov     dword ptr [rsp+128h+var_100], eax
0x18009c4f0  mov     r8, [rsp+128h+GuidString.Buffer]
0x18009c4f8  lea     rdx, StopLdapAuth
0x18009c4ff  call    McTemplateU0zzqq_EventWriteTransfer
0x18009c504  mov     [rsp+128h+lpCriticalSection], 0
0x18009c50d  lea     rdx, [r13+318h]
0x18009c514  lea     rcx, [rsp+128h+lpCriticalSection]
0x18009c519  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18009c51e  cmp     byte ptr [r12+420h], 0
0x18009c527  jz      short loc_18009C581
0x18009c529  mov     eax, cs:dword_1801BD288
0x18009c52f  cmp     eax, 5
0x18009c532  jbe     short loc_18009C54F
0x18009c534  mov     [rsp+128h+var_D8], r15
0x18009c539  lea     rax, [rsp+128h+var_D8]
0x18009c53e  mov     qword ptr [rsp+128h+var_108], rax
0x18009c543  lea     rdx, word_18019B4A2
0x18009c54a  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &)
0x18009c54f  mov     byte ptr [r12+421h], 1
0x18009c558  mov     rcx, [rsp+128h+lpCriticalSection]; lpCriticalSection
0x18009c55d  test    rcx, rcx
0x18009c560  jz      short loc_18009C569
0x18009c562  call    cs:__imp_LeaveCriticalSection
0x18009c568  nop
0x18009c569  lea     rcx, [rsp+128h+GuidString]; UnicodeString
0x18009c571  call    cs:__imp_RtlFreeUnicodeString
0x18009c577  mov     eax, 0A00804C7h
0x18009c57c  jmp     loc_18009C6A6
0x18009c581  cmp     esi, 0A00804C7h
0x18009c587  jz      loc_18009C659
0x18009c58d  test    esi, esi
0x18009c58f  js      short loc_18009C596
0x18009c591  mov     r12b, 1
0x18009c594  jmp     short loc_18009C5A1
0x18009c596  xor     r12b, r12b
0x18009c599  cmp     esi, 800704C6h
0x18009c59f  jz      short loc_18009C611
  ... truncated ...
```
