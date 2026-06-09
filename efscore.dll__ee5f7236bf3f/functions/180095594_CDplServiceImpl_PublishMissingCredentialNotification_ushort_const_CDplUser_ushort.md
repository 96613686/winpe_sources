# CDplServiceImpl::PublishMissingCredentialNotification(ushort const *,CDplUser *,ushort *)

- ea: `0x180095594`
- end: `0x180095d44`
- name: `?PublishMissingCredentialNotification@CDplServiceImpl@@AEAAXPEBGPEAVCDplUser@@PEAG@Z`
- size: `1968`
- prototype: `void __fastcall(CDplServiceImpl *__hidden this, const unsigned __int16 *, struct CDplUser *, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180092240`
- `0x180092e48`
- `0x1800b2174`

## callees

- `0x180001a7c`
- `0x180001b48`
- `0x180001ba8`
- `0x180001d84`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x1800841d0`
- `0x1800861ec`
- `0x180095594`
- `0x1800964ac`
- `0x18009652c`
- `0x180096cc0`
- `0x18009cd9c`
- `0x1800baeb0`
- `0x1800d5af8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095ce0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095ce0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800957e0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800958e2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180095a9a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800957e0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800958e2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180095a9a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180095798`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180095798`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180095b60`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180095b60`
- `ntdll!RtlPublishWnfStateData` at `0x180095be3`
- `ntdll!RtlPublishWnfStateData` at `0x180095be3`
- `ntdll!RtlNtStatusToDosError` at `0x180095bf1`
- `ntdll!RtlNtStatusToDosError` at `0x180095bf1`
- `ntdll!RtlDllShutdownInProgress` at `0x180095c67`
- `ntdll!RtlDllShutdownInProgress` at `0x180095c67`

## string_xrefs

- `0x180095921`: `Missing credential notification is temporarily supressed. Seconds remaining: `
- `0x1800959c6`: `RetrieveCredentialsFromAad in CDplServiceImpl::PublishMissingCredentialNotification`

## pseudocode

```c
void __fastcall CDplServiceImpl::PublishMissingCredentialNotification(
        CDplServiceImpl *this,
        const unsigned __int16 *a2,
        struct CDplUser *a3,
        unsigned __int16 *a4)
{
  unsigned __int16 *v4; // r15
  int v8; // ecx
  int CurrentActiveUserSid; // edi
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  __int64 *v13; // rdx
  int v14; // r8d
  int v15; // eax
  int v16; // ecx
  int v17; // ecx
  LSTATUS ValueW; // eax
  unsigned __int16 *v19; // rbx
  char *v20; // rdx
  int v21; // eax
  CDplServiceImpl *v22; // rcx
  NTSTATUS v23; // eax
  NTSTATUS v24; // ebx
  signed int v25; // eax
  int v26; // ecx
  int v27; // r8d
  char pdwType; // [rsp+20h] [rbp-49h]
  int v29; // [rsp+40h] [rbp-29h] BYREF
  __int64 Data; // [rsp+48h] [rbp-21h] BYREF
  unsigned __int16 *v31; // [rsp+50h] [rbp-19h] BYREF
  HKEY hkey; // [rsp+58h] [rbp-11h] BYREF
  int v33; // [rsp+60h] [rbp-9h] BYREF
  unsigned int pvData; // [rsp+64h] [rbp-5h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+68h] [rbp-1h] BYREF
  void *v36; // [rsp+70h] [rbp+7h] BYREF
  __int64 v37; // [rsp+78h] [rbp+Fh] BYREF
  DWORD pcbData; // [rsp+D8h] [rbp+6Fh] BYREF
  int v39; // [rsp+DCh] [rbp+73h]

  v39 = HIDWORD(a2);
  v4 = 0;
  v36 = 0;
  hkey = 0;
  Data = 0;
  pcbData = 0;
  SystemTimeAsFileTime = 0;
  v29 = 1;
  pvData = 0;
  v31 = 0;
  v33 = 0;
  fnEfsLogTrace1Strings((_DWORD)this, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 37, 82);
  fnEfsLogTrace1Strings(v8, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 91);
  CurrentActiveUserSid = EdpCredSvcShouldCheckCaller(&v29);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              CurrentActiveUserSid,
              37,
              91) < 0 )
    goto LABEL_42;
  if ( !v29 )
  {
    pdwType = 99;
LABEL_4:
    CurrentActiveUserSid = 1;
    v13 = EFS_TRACE_STATUS;
    v14 = 1;
LABEL_41:
    fnEfsLogTrace1(g_hPublisher, (_DWORD)v13, v14, 37, pdwType);
    goto LABEL_42;
  }
  fnEfsLogTrace1Strings(v10, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 108);
  CurrentActiveUserSid = CEdpCredSvcUserState::GetCurrentActiveUserSid(&v31);
  v15 = fnEfsLogTrace1String1Dword(
          g_hPublisher,
          (unsigned int)EFS_TRACE_COMPLETE_EVENT,
          (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
          (unsigned int)&sourceString,
          CurrentActiveUserSid,
          37,
          108);
  v4 = v31;
  if ( v15 < 0 )
    goto LABEL_42;
  if ( !v31 )
  {
    pdwType = 112;
    goto LABEL_4;
  }
  CDplServiceImpl::RevertToSelf(this, &v36);
  fnEfsLogTrace1Strings(v16, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 130);
  CurrentActiveUserSid = EdpCredSvcOpenUserCredStore(v4, 0xF003Fu, &hkey);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              CurrentActiveUserSid,
              37,
              130) < 0 )
  {
LABEL_32:
    fnEfsLogTrace1Strings(v17, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 11);
    CurrentActiveUserSid = CDplServiceImpl::ShouldPublishMissingCredentialNotification(v22, v4);
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                CurrentActiveUserSid,
                37,
                11) >= 0
      && !CurrentActiveUserSid )
    {
      v23 = RtlPublishWnfStateData(WNF_EDP_MISSING_CREDENTIALS, 0, 0, 0, 0);
      v24 = v23;
      if ( v23 < 0 )
      {
        v25 = RtlNtStatusToDosError(v23);
        CurrentActiveUserSid = v25;
        if ( !v25 || v25 == 317 )
        {
          CurrentActiveUserSid = v24 | 0x10000000;
        }
        else if ( v25 > 0 )
        {
          CurrentActiveUserSid = (unsigned __int16)v25 | 0x80070000;
        }
        pdwType = 32;
        v13 = EFS_TRACE_ERROR;
        v14 = CurrentActiveUserSid;
        goto LABEL_41;
      }
    }
    goto LABEL_42;
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v31 = (unsigned __int16 *)SystemTimeAsFileTime;
  pcbData = 8;
  ValueW = RegGetValueW(hkey, 0, L"NoMissingCredsPromptUntil", 0x20000040u, 0, &Data, &pcbData);
  v19 = v31;
  if ( !ValueW && (__int64)v31 < Data )
  {
    fnEfsLogTrace1String1Dword(
      g_hPublisher,
      (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
      (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
      (unsigned int)L"Missing credential notification is throttled. Seconds remaining: ",
      (Data - (__int64)v31) / 0x989680uLL,
      37,
      155);
    if ( (unsigned int)dword_180114250 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180114250, 0x400000000000LL) )
    {
      v29 = (Data - (__int64)v19) / 0x989680uLL;
      v20 = byte_180102F5D;
LABEL_14:
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_180114250,
        (_DWORD)v20,
        v11,
        v12,
        (__int64)&v29);
      goto LABEL_42;
    }
    goto LABEL_42;
  }
  pcbData = 8;
  if ( RegGetValueW(hkey, L"Volatile", L"NoMissingCredsPromptUntil", 0x20000040u, 0, &Data, &pcbData)
    || (__int64)v19 >= Data )
  {
    if ( a3 )
    {
      if ( a4 )
      {
        v21 = CDplUser::RetrieveCredentialsFromAad(a3, a4, &v33);
        fnEfsLogTrace1String1Dword(
          g_hPublisher,
          (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
          (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
          (unsigned int)L"RetrieveCredentialsFromAad in CDplServiceImpl::PublishMissingCredentialNotification",
          v21,
          37,
          206);
        if ( v33 )
        {
          fnEfsLogTrace1String1Dword(
            g_hPublisher,
            (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
            (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
            (unsigned int)L"Missing credential was retrieved from cloud.",
            0,
            37,
            211);
          if ( (unsigned int)dword_180114250 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180114250, 0x400000000000LL) )
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
              &dword_180114250,
              byte_180102CDD,
              0,
              0);
          goto LABEL_42;
        }
      }
    }
    pcbData = 4;
    if ( !RegGetValueW(hkey, 0, L"MissingCredsIgnoreCounter", 0x20000010u, 0, &pvData, &pcbData) && pvData >= 3 )
    {
      fnEfsLogTrace1String1Dword(
        g_hPublisher,
        (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
        (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
        (unsigned int)L"Missing credential notification is permanently supressed.",
        0,
        37,
        235);
      if ( (unsigned int)dword_180114250 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180114250, 0x400000000000LL) )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          &dword_180114250,
          qword_180102DA8,
          0,
          0);
      goto LABEL_42;
    }
    Data = *(_QWORD *)&SystemTimeAsFileTime + 36000000000LL;
    RegSetKeyValueW(hkey, 0, L"NoMissingCredsPromptUntil", 0xBu, &Data, 8u);
    goto LABEL_32;
  }
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
    (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
    (unsigned int)L"Missing credential notification is temporarily supressed. Seconds remaining: ",
    (Data - (__int64)v19) / 0x989680uLL,
    37,
    181);
  if ( (unsigned int)dword_180114250 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180114250, 0x400000000000LL) )
  {
    v29 = (Data - (__int64)v19) / 0x989680uLL;
    v20 = (char *)&unk_180102E48;
    goto LABEL_14;
  }
LABEL_42:
  if ( (unsigned int)dword_180114250 > 5 )
  {
    v29 = CurrentActiveUserSid;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180114250,
      (unsigned int)&dword_180102EB4,
      v11,
      v12,
      (__int64)&v29);
  }
  if ( !RtlDllShutdownInProgress()
    && (unsigned int)dword_180114218 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_180114218, 0x400000000000LL) )
  {
    v31 = (unsigned __int16 *)0x1000000;
    v29 = CurrentActiveUserSid;
    v37 = 1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v26,
      (unsigned int)byte_180102D35,
      v27,
      (unsigned int)&v37,
      (__int64)&v29,
      (__int64)&v31);
  }
  CDplServiceImpl::RestoreImpersonation(this, &v36);
  if ( hkey )
  {
    RegCloseKey(hkey);
    hkey = 0;
  }
  if ( v4 )
    DplibMemFree(v4);
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    CurrentActiveUserSid,
    37,
    56);
}

```

## disassembly

```asm
0x180095594  mov     qword ptr [rsp-8+arg_8], rdx
0x180095599  push    rbp
0x18009559a  push    rbx
0x18009559b  push    rsi
0x18009559c  push    rdi
0x18009559d  push    r12
0x18009559f  push    r13
0x1800955a1  push    r14
0x1800955a3  push    r15
0x1800955a5  lea     rbp, [rsp-1Fh]
0x1800955aa  sub     rsp, 88h
0x1800955b1  xor     r15d, r15d
0x1800955b4  mov     [rbp+57h+var_50], 0
0x1800955bc  mov     r14, r9
0x1800955bf  mov     [rbp+57h+hkey], 0
0x1800955c7  mov     r12, r8
0x1800955ca  mov     [rbp+57h+Data], 0
0x1800955d2  lea     r8, sourceString
0x1800955d9  mov     [rbp+57h+arg_8], 0
0x1800955e0  lea     esi, [r15+1]
0x1800955e4  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800955ec  lea     r9d, [r15+25h]
0x1800955f0  mov     [rbp+57h+var_80], esi
0x1800955f3  lea     rdx, EFS_TRACE_ENTER_EVENT
0x1800955fa  mov     [rbp+57h+var_5C], 0
0x180095601  mov     r13, rcx
0x180095604  mov     [rbp+57h+var_70], r15
0x180095608  mov     [rbp+57h+var_60], r15d
0x18009560c  mov     dword ptr [rsp+0C0h+pdwType], 1E52h
0x180095614  call    fnEfsLogTrace1Strings
0x180095619  mov     ebx, 1E5Bh
0x18009561e  lea     r9d, [r15+25h]
0x180095622  lea     r8, sourceString
0x180095629  mov     dword ptr [rsp+0C0h+pdwType], ebx
0x18009562d  lea     rdx, EFS_TRACE_START_EVENT
0x180095634  call    fnEfsLogTrace1Strings
0x180095639  lea     rcx, [rbp+57h+var_80]; int *
0x18009563d  call    ?EdpCredSvcShouldCheckCaller@@YAJPEAH@Z; EdpCredSvcShouldCheckCaller(int *)
0x180095642  mov     rcx, cs:g_hPublisher
0x180095649  lea     r9, sourceString
0x180095650  mov     dword ptr [rsp+0C0h+pcbData], ebx
0x180095654  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x18009565b  mov     dword ptr [rsp+0C0h+pvData], 25h ; '%'
0x180095663  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x18009566a  mov     dword ptr [rsp+0C0h+pdwType], eax
0x18009566e  mov     edi, eax
0x180095670  call    fnEfsLogTrace1String1Dword
0x180095675  test    eax, eax
0x180095677  js      loc_180095C3D
0x18009567d  lea     r9d, [r15+25h]
0x180095681  cmp     [rbp+57h+var_80], r15d
0x180095685  jnz     short loc_1800956A0
0x180095687  mov     dword ptr [rsp+0C0h+pdwType], 1E63h
0x18009568f  mov     edi, esi
0x180095691  lea     rdx, EFS_TRACE_STATUS
0x180095698  mov     r8d, esi
0x18009569b  jmp     loc_180095C31
0x1800956a0  mov     ebx, 1E6Ch
0x1800956a5  lea     r8, sourceString
0x1800956ac  lea     rdx, EFS_TRACE_START_EVENT
0x1800956b3  mov     dword ptr [rsp+0C0h+pdwType], ebx
0x1800956b7  call    fnEfsLogTrace1Strings
0x1800956bc  lea     rcx, [rbp+57h+var_70]; unsigned __int16 **
0x1800956c0  call    ?GetCurrentActiveUserSid@CEdpCredSvcUserState@@SAJPEAPEAG@Z; CEdpCredSvcUserState::GetCurrentActiveUserSid(ushort * *)
0x1800956c5  mov     rcx, cs:g_hPublisher
0x1800956cc  lea     r9, sourceString
0x1800956d3  mov     dword ptr [rsp+0C0h+pcbData], ebx
0x1800956d7  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800956de  mov     dword ptr [rsp+0C0h+pvData], 25h ; '%'
0x1800956e6  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800956ed  mov     dword ptr [rsp+0C0h+pdwType], eax
0x1800956f1  mov     edi, eax
0x1800956f3  call    fnEfsLogTrace1String1Dword
0x1800956f8  mov     r15, [rbp+57h+var_70]
0x1800956fc  test    eax, eax
0x1800956fe  js      loc_180095C3D
0x180095704  test    r15, r15
0x180095707  jnz     short loc_18009571A
0x180095709  mov     dword ptr [rsp+0C0h+pdwType], 1E70h
0x180095711  lea     r9d, [r15+25h]
0x180095715  jmp     loc_18009568F
0x18009571a  lea     rdx, [rbp+57h+var_50]; void **
0x18009571e  mov     rcx, r13; this
0x180095721  call    ?RevertToSelf@CDplServiceImpl@@AEAAJPEAPEAX@Z; CDplServiceImpl::RevertToSelf(void * *)
0x180095726  mov     ebx, 1E82h
0x18009572b  lea     r8, sourceString
0x180095732  mov     r9d, 25h ; '%'
0x180095738  mov     dword ptr [rsp+0C0h+pdwType], ebx
0x18009573c  lea     rdx, EFS_TRACE_START_EVENT
0x180095743  call    fnEfsLogTrace1Strings
0x180095748  lea     r8, [rbp+57h+hkey]; phkResult
0x18009574c  mov     edx, 0F003Fh; samDesired
0x180095751  mov     rcx, r15; unsigned __int16 *
0x180095754  call    ?EdpCredSvcOpenUserCredStore@@YAJPEBGKPEAPEAUHKEY__@@@Z; EdpCredSvcOpenUserCredStore(ushort const *,ulong,HKEY__ * *)
0x180095759  mov     rcx, cs:g_hPublisher
0x180095760  lea     r9, sourceString
0x180095767  mov     dword ptr [rsp+0C0h+pcbData], ebx
0x18009576b  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180095772  mov     dword ptr [rsp+0C0h+pvData], 25h ; '%'
0x18009577a  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180095781  mov     dword ptr [rsp+0C0h+pdwType], eax
0x180095785  mov     edi, eax
0x180095787  call    fnEfsLogTrace1String1Dword
0x18009578c  test    eax, eax
0x18009578e  js      loc_180095B66
0x180095794  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180095798  call    cs:__imp_GetSystemTimeAsFileTime
0x18009579e  mov     eax, [rbp+57h+SystemTimeAsFileTime.dwHighDateTime]
0x1800957a1  lea     r8, aNomissingcreds; "NoMissingCredsPromptUntil"
0x1800957a8  mov     rcx, [rbp+57h+hkey]; hkey
0x1800957ac  mov     esi, 8
0x1800957b1  mov     dword ptr [rbp+57h+var_70+4], eax
0x1800957b4  mov     r9d, 20000040h; dwFlags
0x1800957ba  mov     eax, [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x1800957bd  xor     edx, edx; lpSubKey
0x1800957bf  mov     dword ptr [rbp+57h+var_70], eax
0x1800957c2  lea     rax, [rbp+57h+arg_8]
0x1800957c6  mov     [rsp+0C0h+pcbData], rax; pcbData
0x1800957cb  lea     rax, [rbp+57h+Data]
0x1800957cf  mov     [rsp+0C0h+pvData], rax; pvData
0x1800957d4  mov     [rsp+0C0h+pdwType], 0; pdwType
0x1800957dd  mov     [rbp+57h+arg_8], esi
0x1800957e0  call    cs:__imp_RegGetValueW
0x1800957e6  mov     rbx, [rbp+57h+var_70]
0x1800957ea  test    eax, eax
0x1800957ec  jnz     loc_1800958AC
0x1800957f2  mov     rcx, [rbp+57h+Data]
0x1800957f6  cmp     rbx, rcx
0x1800957f9  jge     loc_1800958AC
0x1800957ff  sub     rcx, rbx
0x180095802  mov     dword ptr [rsp+0C0h+pcbData], 1E9Bh
0x18009580a  lea     rsi, EFS_TRACE_MSG_DWORD_EVENT
0x180095811  mov     dword ptr [rsp+0C0h+pvData], 25h ; '%'
0x180095819  mov     r14, 0D6BF94D5E57A42BDh
0x180095823  lea     r9, aMissingCredent_0; "Missing credential notification is thro"...
0x18009582a  mov     rax, r14
0x18009582d  mov     r8, rsi
0x180095830  mul     rcx
0x180095833  mov     rcx, cs:g_hPublisher
0x18009583a  shr     rdx, 17h
0x18009583e  mov     dword ptr [rsp+0C0h+pdwType], edx
0x180095842  mov     rdx, rsi
0x180095845  call    fnEfsLogTrace1String1Dword
0x18009584a  mov     ecx, cs:dword_180114250
0x180095850  cmp     ecx, 5
0x180095853  jbe     loc_180095C3D
0x180095859  mov     rdx, 400000000000h
0x180095863  lea     rcx, dword_180114250
0x18009586a  call    _tlgKeywordOn
0x18009586f  test    al, al
0x180095871  jz      loc_180095C3D
0x180095877  mov     rcx, [rbp+57h+Data]
0x18009587b  mov     rax, r14
0x18009587e  sub     rcx, rbx
0x180095881  mul     rcx
0x180095884  shr     rdx, 17h
0x180095888  mov     [rbp+57h+var_80], edx
0x18009588b  lea     rdx, byte_180102F5D
0x180095892  lea     rax, [rbp+57h+var_80]
0x180095896  lea     rcx, dword_180114250
0x18009589d  mov     [rsp+0C0h+pdwType], rax
0x1800958a2  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800958a7  jmp     loc_180095C3D
0x1800958ac  mov     rcx, [rbp+57h+hkey]; hkey
0x1800958b0  lea     rax, [rbp+57h+arg_8]
0x1800958b4  mov     [rsp+0C0h+pcbData], rax; pcbData
0x1800958b9  lea     r8, aNomissingcreds; "NoMissingCredsPromptUntil"
0x1800958c0  lea     rax, [rbp+57h+Data]
0x1800958c4  mov     [rbp+57h+arg_8], esi
0x1800958c7  mov     [rsp+0C0h+pvData], rax; pvData
0x1800958cc  lea     rdx, aVolatile; "Volatile"
0x1800958d3  mov     r9d, 20000040h; dwFlags
0x1800958d9  mov     [rsp+0C0h+pdwType], 0; pdwType
0x1800958e2  call    cs:__imp_RegGetValueW
0x1800958e8  test    eax, eax
0x1800958ea  jnz     loc_180095995
0x1800958f0  mov     rcx, [rbp+57h+Data]
0x1800958f4  cmp     rbx, rcx
0x1800958f7  jge     loc_180095995
0x1800958fd  sub     rcx, rbx
0x180095900  mov     dword ptr [rsp+0C0h+pcbData], 1EB5h
0x180095908  lea     rsi, EFS_TRACE_MSG_DWORD_EVENT
0x18009590f  mov     dword ptr [rsp+0C0h+pvData], 25h ; '%'
0x180095917  mov     r14, 0D6BF94D5E57A42BDh
0x180095921  lea     r9, aMissingCredent_2; "Missing credential notification is temp"...
0x180095928  mov     rax, r14
0x18009592b  mov     r8, rsi
0x18009592e  mul     rcx
0x180095931  mov     rcx, cs:g_hPublisher
0x180095938  shr     rdx, 17h
0x18009593c  mov     dword ptr [rsp+0C0h+pdwType], edx
0x180095940  mov     rdx, rsi
0x180095943  call    fnEfsLogTrace1String1Dword
0x180095948  mov     eax, cs:dword_180114250
0x18009594e  cmp     eax, 5
0x180095951  jbe     loc_180095C3D
0x180095957  mov     rdx, 400000000000h
0x180095961  lea     rcx, dword_180114250
0x180095968  call    _tlgKeywordOn
0x18009596d  test    al, al
0x18009596f  jz      loc_180095C3D
0x180095975  mov     rcx, [rbp+57h+Data]
0x180095979  mov     rax, r14
0x18009597c  sub     rcx, rbx
0x18009597f  mul     rcx
0x180095982  shr     rdx, 17h
0x180095986  mov     [rbp+57h+var_80], edx
0x180095989  lea     rdx, unk_180102E48
0x180095990  jmp     loc_180095892
0x180095995  xor     ebx, ebx
0x180095997  lea     rsi, EFS_TRACE_MSG_DWORD_EVENT
0x18009599e  test    r12, r12
0x1800959a1  jz      loc_180095A69
0x1800959a7  test    r14, r14
0x1800959aa  jz      loc_180095A69
0x1800959b0  lea     r8, [rbp+57h+var_60]; int *
0x1800959b4  mov     rdx, r14; StringUuid
0x1800959b7  mov     rcx, r12; this
0x1800959ba  call    ?RetrieveCredentialsFromAad@CDplUser@@AEAAJPEAGPEAH@Z; CDplUser::RetrieveCredentialsFromAad(ushort *,int *)
0x1800959bf  mov     rcx, cs:g_hPublisher
0x1800959c6  lea     r9, aRetrievecreden_0; "RetrieveCredentialsFromAad in CDplServi"...
0x1800959cd  mov     dword ptr [rsp+0C0h+pcbData], 1ECEh
0x1800959d5  mov     r8, rsi
0x1800959d8  mov     dword ptr [rsp+0C0h+pvData], 25h ; '%'
0x1800959e0  mov     rdx, rsi
0x1800959e3  mov     dword ptr [rsp+0C0h+pdwType], eax
0x1800959e7  call    fnEfsLogTrace1String1Dword
0x1800959ec  cmp     [rbp+57h+var_60], ebx
0x1800959ef  jz      short loc_180095A69
0x1800959f1  mov     rcx, cs:g_hPublisher
0x1800959f8  lea     r9, aMissingCredent; "Missing credential was retrieved from c"...
0x1800959ff  mov     dword ptr [rsp+0C0h+pcbData], 1ED3h
0x180095a07  mov     r8, rsi
0x180095a0a  mov     dword ptr [rsp+0C0h+pvData], 25h ; '%'
0x180095a12  mov     rdx, rsi
0x180095a15  mov     dword ptr [rsp+0C0h+pdwType], ebx
0x180095a19  call    fnEfsLogTrace1String1Dword
0x180095a1e  mov     eax, cs:dword_180114250
0x180095a24  cmp     eax, 5
0x180095a27  jbe     loc_180095C3D
0x180095a2d  mov     rdx, 400000000000h
0x180095a37  lea     rcx, dword_180114250
0x180095a3e  call    _tlgKeywordOn
0x180095a43  test    al, al
0x180095a45  jz      loc_180095C3D
0x180095a4b  xor     r9d, r9d
0x180095a4e  lea     rdx, byte_180102CDD
0x180095a55  xor     r8d, r8d
0x180095a58  lea     rcx, dword_180114250
0x180095a5f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180095a64  jmp     loc_180095C3D
0x180095a69  mov     rcx, [rbp+57h+hkey]; hkey
0x180095a6d  lea     rax, [rbp+57h+arg_8]
0x180095a71  mov     [rsp+0C0h+pcbData], rax; pcbData
0x180095a76  lea     r8, aMissingcredsig; "MissingCredsIgnoreCounter"
0x180095a7d  lea     rax, [rbp+57h+var_5C]
0x180095a81  mov     [rbp+57h+arg_8], 4
0x180095a88  mov     [rsp+0C0h+pvData], rax; pvData
0x180095a8d  mov     r9d, 20000010h; dwFlags
0x180095a93  xor     edx, edx; lpSubKey
0x180095a95  mov     [rsp+0C0h+pdwType], rbx; pdwType
0x180095a9a  call    cs:__imp_RegGetValueW
0x180095aa0  test    eax, eax
0x180095aa2  jnz     short loc_180095B22
0x180095aa4  cmp     [rbp+57h+var_5C], 3
0x180095aa8  jb      short loc_180095B22
0x180095aaa  mov     rcx, cs:g_hPublisher
0x180095ab1  lea     r9, aMissingCredent_1; "Missing credential notification is perm"...
0x180095ab8  mov     dword ptr [rsp+0C0h+pcbData], 1EEBh
0x180095ac0  mov     r8, rsi
0x180095ac3  mov     dword ptr [rsp+0C0h+pvData], 25h ; '%'
0x180095acb  mov     rdx, rsi
0x180095ace  mov     dword ptr [rsp+0C0h+pdwType], ebx
0x180095ad2  call    fnEfsLogTrace1String1Dword
0x180095ad7  mov     eax, cs:dword_180114250
0x180095add  cmp     eax, 5
0x180095ae0  jbe     loc_180095C3D
0x180095ae6  mov     rdx, 400000000000h
0x180095af0  lea     rcx, dword_180114250
0x180095af7  call    _tlgKeywordOn
0x180095afc  test    al, al
0x180095afe  jz      loc_180095C3D
0x180095b04  xor     r9d, r9d
0x180095b07  lea     rdx, qword_180102DA8
0x180095b0e  xor     r8d, r8d
0x180095b11  lea     rcx, dword_180114250
0x180095b18  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180095b1d  jmp     loc_180095C3D
0x180095b22  mov     eax, [rbp+57h+SystemTimeAsFileTime.dwHighDateTime]
0x180095b25  lea     r8, aNomissingcreds; "NoMissingCredsPromptUntil"
0x180095b2c  mov     rcx, [rbp+57h+hkey]; hKey
0x180095b30  mov     r9d, 0Bh; dwType
0x180095b36  mov     dword ptr [rbp+57h+Data+4], eax
0x180095b39  xor     edx, edx; lpSubKey
0x180095b3b  mov     eax, [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x180095b3e  mov     dword ptr [rbp+57h+Data], eax
0x180095b41  mov     rax, 861C46800h
0x180095b4b  add     [rbp+57h+Data], rax
0x180095b4f  lea     rax, [rbp+57h+Data]
0x180095b53  mov     dword ptr [rsp+0C0h+pvData], 8; cbData
  ... truncated ...
```
