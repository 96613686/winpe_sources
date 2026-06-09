# _lambda_2925410eb9906e38deb70bce9a0dcb53_::operator()

- ea: `0x18009c9bc`
- end: `0x18009d1be`
- name: `_lambda_2925410eb9906e38deb70bce9a0dcb53_::operator()`
- size: `2050`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18009e488`

## callees

- `0x180005c90`
- `0x1800093f0`
- `0x180010e90`
- `0x180014dc0`
- `0x1800190c0`
- `0x1800290c0`
- `0x1800321f8`
- `0x180032964`
- `0x180040fb8`
- `0x18004ed20`
- `0x180057f58`
- `0x180065fa4`
- `0x18006cc70`
- `0x18007a670`
- `0x18008b70c`
- `0x180090040`
- `0x18009c9bc`
- `0x18009fdac`
- `0x1800a024c`
- `0x1800bf420`
- `0x1800dd6d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009cf73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009cf73`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18009d07c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18009d07c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18009d108`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18009d108`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18009cf69`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18009cf69`
- `ntdll!RtlCopyUnicodeString` at `0x18009d03e`
- `ntdll!RtlCopyUnicodeString` at `0x18009d03e`
- `KerbClientShared!KerbClientFreeStoredCred` at `0x18009ce23`
- `KerbClientShared!KerbClientFreeStoredCred` at `0x18009ce36`
- `KerbClientShared!KerbClientFreeStoredCred` at `0x18009ce23`
- `KerbClientShared!KerbClientFreeStoredCred` at `0x18009ce36`

## string_xrefs

- `0x18009ca70`: `KerbBuildFullServiceKdcName failed KerbErr - %x\n`
- `0x18009cd0f`: `Failed to create a cache entry and insert it into the cache for DMSA - %x\n`
- `0x18009d04a`: `RtlCopyUnicodeString failed for DMSA name\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall lambda_2925410eb9906e38deb70bce9a0dcb53_::operator()(struct _UNICODE_STRING **a1)
{
  __int64 v2; // rcx
  int v3; // r8d
  struct _KERB_LOGON_SESSION *v4; // rbx
  int v5; // eax
  struct _KERB_CREDENTIAL *v6; // rdx
  int v7; // r14d
  int v8; // ecx
  int SuppCredArrayForDmsa; // ebx
  int TgtToS4URealm; // eax
  const char *v11; // r9
  __int64 v12; // r8
  int v13; // ebx
  const char *v14; // r9
  __int64 v15; // r8
  __int64 v16; // rcx
  struct _UNICODE_STRING *v17; // rax
  int TicketCacheEntry; // eax
  const char *v19; // r9
  __int64 v20; // r8
  __int64 v21; // r14
  union _LARGE_INTEGER SystemTime; // rax
  __int64 v23; // r10
  __int64 v24; // r11
  struct _UNICODE_STRING *v25; // rax
  __int64 *v26; // r10
  __int64 v27; // rcx
  struct _UNICODE_STRING *v28; // rax
  _WORD *v29; // r15
  void *v30; // rax
  void *v31; // rdx
  PWSTR Buffer; // rcx
  __int64 v33; // rcx
  unsigned int DueTime; // [rsp+20h] [rbp-89h]
  DWORD DueTimea[2]; // [rsp+20h] [rbp-89h]
  DWORD DueTimeb[2]; // [rsp+20h] [rbp-89h]
  DWORD Period; // [rsp+28h] [rbp-81h]
  ULONG Flags; // [rsp+30h] [rbp-79h]
  struct _KERB_LOGON_SESSION *v40; // [rsp+B0h] [rbp+7h] BYREF
  _QWORD v41[9]; // [rsp+B8h] [rbp+Fh] BYREF
  __int64 v42; // [rsp+110h] [rbp+67h] BYREF
  int v43; // [rsp+118h] [rbp+6Fh] BYREF
  char v44; // [rsp+120h] [rbp+77h] BYREF
  __int64 v45; // [rsp+128h] [rbp+7Fh] BYREF

  v2 = *(_QWORD *)&(*a1)->Length;
  if ( v2 && *(_QWORD *)&a1[1]->Length && *(_QWORD *)&a1[2]->Length )
  {
    if ( (*(_BYTE *)(v2 + 528) & 0x20) == 0 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v2);
    v42 = 999;
    KerbLocateLogonSessionUnique(&v40, &v42);
    v4 = v40;
    if ( !v40 )
    {
      KerbTracerT::Log(
        1,
        "KerbGetDmsaTgt::<lambda_2925410eb9906e38deb70bce9a0dcb53>::operator ()",
        3478,
        "Unable to reference the system logon session\n");
LABEL_65:
      SuppCredArrayForDmsa = -1073741595;
      goto LABEL_66;
    }
    v5 = KerbBuildFullServiceKdcNameWithSid(
           *(_QWORD *)&a1[2]->Length,
           (unsigned int)&KerbGlobalKdcServiceName,
           v3,
           2,
           (__int64)a1[3]);
    v7 = v5;
    if ( v5 )
    {
      KerbTracerT::Log(
        1,
        "KerbGetDmsaTgt::<lambda_2925410eb9906e38deb70bce9a0dcb53>::operator ()",
        3491,
        "KerbBuildFullServiceKdcName failed KerbErr - %x\n",
        v5);
      v8 = v7;
LABEL_10:
      SuppCredArrayForDmsa = KerbMapKerbError(v8);
LABEL_66:
      wil::details::unique_storage<wil::details::resource_policy<_KERB_LOGON_SESSION *,void (_KERB_LOGON_SESSION *),&void KerbDereferenceLogonSession(_KERB_LOGON_SESSION *),wistd::integral_constant<unsigned __int64,0>,_KERB_LOGON_SESSION *,_KERB_LOGON_SESSION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_KERB_LOGON_SESSION *,void (_KERB_LOGON_SESSION *),&void KerbDereferenceLogonSession(_KERB_LOGON_SESSION *),wistd::integral_constant<unsigned __int64,0>,_KERB_LOGON_SESSION *,_KERB_LOGON_SESSION *,0,std::nullptr_t>>(&v40);
      return (unsigned int)SuppCredArrayForDmsa;
    }
    TgtToS4URealm = KerbGetTgtToS4URealm(
                      v4,
                      v6,
                      *(struct _UNICODE_STRING **)&a1[2]->Length,
                      (struct _KERB_TICKET_CACHE_ENTRY **)a1[4],
                      DueTime,
                      Period,
                      Flags);
    SuppCredArrayForDmsa = TgtToS4URealm;
    if ( TgtToS4URealm < 0 )
    {
      v11 = "KerbGetTgtToS4URealm cannot get S4U Tgt - %x\n";
      v12 = 3508;
LABEL_13:
      DueTimea[0] = TgtToS4URealm;
      KerbTracerT::Log(
        1,
        "KerbGetDmsaTgt::<lambda_2925410eb9906e38deb70bce9a0dcb53>::operator ()",
        v12,
        v11,
        *(_QWORD *)DueTimea);
      goto LABEL_66;
    }
    v13 = KerbConvertKdcNameToPrincipalName(
            (struct KERB_PRINCIPAL_NAME *)&a1[5]->Buffer,
            *(struct _KERB_INTERNAL_NAME **)&a1[1]->Length);
    if ( v13 )
    {
      v14 = "KerbConvertKdcNameToPrincipalName failed KerbErr - %x\n";
      v15 = 3518;
LABEL_16:
      DueTimea[0] = v13;
      KerbTracerT::Log(
        1,
        "KerbGetDmsaTgt::<lambda_2925410eb9906e38deb70bce9a0dcb53>::operator ()",
        v15,
        v14,
        *(_QWORD *)DueTimea);
      v8 = v13;
      goto LABEL_10;
    }
    a1[5]->Length |= 0x80u;
    v13 = KerbConvertUnicodeStringToRealm((CHAR **)&a1[5][1].Buffer, *(unsigned __int16 **)&a1[2]->Length);
    if ( v13 )
    {
      v14 = "KerbConvertUnicodeStringToRealm failed KerbErr - %x\n";
      v15 = 3527;
      goto LABEL_16;
    }
    a1[5]->Length |= 0x40u;
    LODWORD(v42) = 8;
    v43 = 72;
    a1[5]->Length |= 0x10u;
    *(_DWORD *)&a1[5][3].Length = 32;
    a1[5][3].Buffer = (PWSTR)&v43;
    TgtToS4URealm = KerbGetTgsTicketEx(
                      0,
                      0,
                      0,
                      *(struct _KERB_TICKET_CACHE_ENTRY **)&a1[4]->Length,
                      *(struct _KERB_INTERNAL_NAME **)&a1[3]->Length,
                      0,
                      0,
                      0,
                      0,
                      0,
                      (struct PA_S4U_X509_USER *)a1[5],
                      0,
                      0,
                      0,
                      0,
                      0,
                      (struct KERB_KDC_REPLY **)a1[6],
                      (struct KERB_ENCRYPTED_KDC_REPLY **)a1[7],
                      (unsigned int *)&a1[8]->Length,
                      a1[9],
                      (unsigned int *)&a1[10]->Length,
                      (struct _DMSA_KEY_PACKAGE *)a1[11]);
    SuppCredArrayForDmsa = TgtToS4URealm;
    if ( TgtToS4URealm < 0 )
    {
      v11 = "Failed to get DMSA Tgt - %x\n";
      v12 = 3566;
      goto LABEL_13;
    }
    if ( *(_DWORD *)&a1[8]->Length )
      MicrosoftTelemetryAssertTriggeredNoArgs(v16);
    v17 = a1[11];
    if ( *(__int64 *)&v17[1].Length < 0 || (__int64)v17[1].Buffer < 0 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v16);
      KerbTracerT::Log(
        1,
        "KerbGetDmsaTgt::<lambda_2925410eb9906e38deb70bce9a0dcb53>::operator ()",
        3574,
        "Invalid timestamps for DMSA\n");
      goto LABEL_65;
    }
    wil::RtlEnterCriticalSection(&v44, *(_QWORD *)&(*a1)->Length + 80LL);
    TicketCacheEntry = KerbCreateTicketCacheEntry(
                         *(struct KERB_KDC_REPLY **)&a1[6]->Length,
                         *(struct KERB_ENCRYPTED_KDC_REPLY **)&a1[7]->Length,
                         *(struct KerbCredIsoApi **)(*(_QWORD *)&a1[4]->Length + 168LL),
                         0,
                         0,
                         *(_DWORD *)&a1[10]->Length | 1u,
                         *(_DWORD *)(*(_QWORD *)&a1[4]->Length + 344LL),
                         (struct _KERB_TICKET_CACHE *)(*(_QWORD *)&(*a1)->Length + 360LL),
                         0,
                         a1[9],
                         (struct _UNICODE_STRING *)(*(_QWORD *)&(*a1)->Length + 136LL),
                         0,
                         (struct _KERB_TICKET_CACHE_ENTRY **)a1[12]);
    SuppCredArrayForDmsa = TicketCacheEntry;
    if ( TicketCacheEntry < 0 )
    {
      v19 = "Failed to create a cache entry and insert it into the cache for DMSA - %x\n";
      v20 = 3598;
LABEL_27:
      DueTimeb[0] = TicketCacheEntry;
      KerbTracerT::Log(
        1,
        "KerbGetDmsaTgt::<lambda_2925410eb9906e38deb70bce9a0dcb53>::operator ()",
        v20,
        v19,
        *(_QWORD *)DueTimeb);
LABEL_28:
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,long (*)(_RTL_CRITICAL_SECTION *),&long RtlLeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,2>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,long (*)(_RTL_CRITICAL_SECTION *),&long RtlLeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,2>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v44);
      goto LABEL_66;
    }
    v21 = *(_QWORD *)&(*a1)->Length;
    SystemTime = KerbGetSystemTime();
    v45 = 0;
    v42 = 0;
    v41[0] = 600000000;
    TicketCacheEntry = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))RtlLongLongAdd)(
                         *(_QWORD *)&a1[11][1].Length,
                         (union _LARGE_INTEGER)SystemTime.QuadPart,
                         &v42);
    SuppCredArrayForDmsa = TicketCacheEntry;
    if ( TicketCacheEntry < 0 )
    {
      v19 = "RtlLongLongAdd failed for  ExpirationTime - %x\n";
      v20 = 3613;
      goto LABEL_27;
    }
    TicketCacheEntry = RtlLongLongAdd(*(_QWORD *)(v24 + 24), v23, &v45);
    SuppCredArrayForDmsa = TicketCacheEntry;
    if ( TicketCacheEntry < 0 )
    {
      v19 = "RtlLongLongAdd failed for  ExpirationTime - %x\n";
      v20 = 3620;
      goto LABEL_27;
    }
    v25 = a1[13];
    if ( *(_QWORD *)&v25->Length )
      **(_DWORD **)&v25->Length = 1;
    if ( (unsigned __int8)KerbCheckTimeSkew(v21 + 752, &v42, v41)
      && (unsigned __int8)KerbCheckTimeSkew(v21 + 760, &v45, v41) )
    {
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,long (*)(_RTL_CRITICAL_SECTION *),&long RtlLeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,2>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,long (*)(_RTL_CRITICAL_SECTION *),&long RtlLeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,2>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v44);
      SuppCredArrayForDmsa = 0;
      goto LABEL_66;
    }
    *(_DWORD *)&a1[14]->Length = 1;
    *v26 = v42;
    *(_QWORD *)(v21 + 760) = v45;
    KerbClientFreeStoredCred(*(struct _KERB_STORED_CREDENTIAL **)(*(_QWORD *)&(*a1)->Length + 272LL));
    KerbClientFreeStoredCred(*(struct _KERB_STORED_CREDENTIAL **)(*(_QWORD *)&(*a1)->Length + 264LL));
    *(_QWORD *)(*(_QWORD *)&(*a1)->Length + 264LL) = a1[11]->Buffer;
    *(_QWORD *)(*(_QWORD *)&(*a1)->Length + 272LL) = *(_QWORD *)&a1[11]->Length;
    a1[11]->Buffer = 0;
    *(_QWORD *)&a1[11]->Length = 0;
    if ( (*(_BYTE *)(*(_QWORD *)&(*a1)->Length + 528LL) & 0x40) != 0 )
    {
      SuppCredArrayForDmsa = KerbGetSuppCredArrayForDmsa(
                               (const struct _KERB_PRIMARY_CREDENTIAL *)(*(_QWORD *)&(*a1)->Length + 120LL),
                               (struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **)a1[15]);
      if ( SuppCredArrayForDmsa >= 0 )
      {
        *(_QWORD *)&a1[16]->Length = MIDL_user_allocate(0xE8u);
        v28 = a1[16];
        if ( !*(_QWORD *)&v28->Length )
        {
          KerbTracerT::Log(
            1,
            "KerbGetDmsaTgt::<lambda_2925410eb9906e38deb70bce9a0dcb53>::operator ()",
            3665,
            "Allocation failure\n");
LABEL_43:
          wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,long (*)(_RTL_CRITICAL_SECTION *),&long RtlLeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,2>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,long (*)(_RTL_CRITICAL_SECTION *),&long RtlLeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,2>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v44);
          SuppCredArrayForDmsa = -1073741801;
          goto LABEL_66;
        }
        *(_DWORD *)(*(_QWORD *)&v28->Length + 80LL) |= 0x1004u;
        **(_QWORD **)&a1[16]->Length = *(_QWORD *)(*(_QWORD *)&(*a1)->Length + 64LL);
        *(_QWORD *)(*(_QWORD *)&a1[16]->Length + 200LL) = KerberosPackageId;
        *(_QWORD *)(*(_QWORD *)&a1[16]->Length + 224LL) = *(_QWORD *)&a1[15]->Length;
        if ( QueueUserWorkItem(KerbUpdateDmsaCredsCallback, *(PVOID *)&a1[16]->Length, 0) )
        {
          *(_QWORD *)&a1[15]->Length = 0;
          *(_QWORD *)&a1[16]->Length = 0;
        }
        else
        {
          DueTimeb[0] = GetLastError();
          KerbTracerT::Log(
            1,
            "KerbGetDmsaTgt::<lambda_2925410eb9906e38deb70bce9a0dcb53>::operator ()",
            3678,
            "QueueUserWorkItem failed - %x\n",
            *(_QWORD *)DueTimeb);
        }
      }
      else
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v27);
        DueTimeb[0] = SuppCredArrayForDmsa;
        KerbTracerT::Log(
          1,
          "KerbGetDmsaTgt::<lambda_2925410eb9906e38deb70bce9a0dcb53>::operator ()",
          3658,
          "KerbGetSuppCredArrayForDmsa failed for  DMSA - %x\n",
          *(_QWORD *)DueTimeb);
      }
    }
    *(_QWORD *)(v21 + 744) = *(_QWORD *)(*(_QWORD *)&(*a1)->Length + 64LL);
    if ( !*(_QWORD *)(v21 + 768) )
      KerbDuplicateKdcName((struct _KERB_INTERNAL_NAME **)(v21 + 768), *(struct _KERB_INTERNAL_NAME **)&a1[1]->Length);
    v29 = (_WORD *)(v21 + 776);
    if ( !*(_QWORD *)(v21 + 784) )
    {
      v30 = MIDL_user_allocate(*(unsigned __int16 *)(*(_QWORD *)&a1[2]->Length + 2LL));
      *(_QWORD *)(v21 + 784) = v30;
      if ( !v30 )
      {
        KerbTracerT::Log(
          1,
          "KerbGetDmsaTgt::<lambda_2925410eb9906e38deb70bce9a0dcb53>::operator ()",
          3700,
          "Allocation failed for DMSA name \n");
        goto LABEL_43;
      }
      *v29 = **(_WORD **)&a1[2]->Length;
      *(_WORD *)(v21 + 778) = *(_WORD *)(*(_QWORD *)&a1[2]->Length + 2LL);
      RtlCopyUnicodeString((PUNICODE_STRING)(v21 + 776), *(PCUNICODE_STRING *)&a1[2]->Length);
      if ( !*v29 )
      {
        KerbTracerT::Log(
          1,
          "KerbGetDmsaTgt::<lambda_2925410eb9906e38deb70bce9a0dcb53>::operator ()",
          3711,
          "RtlCopyUnicodeString failed for DMSA name\n");
        goto LABEL_28;
      }
    }
    v31 = *(void **)(v21 + 792);
    if ( v31 )
    {
      DeleteTimerQueueTimer(0, v31, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      *(_QWORD *)(v21 + 792) = 0;
    }
    Buffer = a1[11][1].Buffer;
    if ( (unsigned __int64)((__int64)Buffer / 10000) > 0xFFFFFFFF )
    {
      SuppCredArrayForDmsa = -1073741675;
      DueTimeb[0] = -1073741675;
      KerbTracerT::Log(
        1,
        "KerbGetDmsaTgt::<lambda_2925410eb9906e38deb70bce9a0dcb53>::operator ()",
        3727,
        "RtlLongLongToULong failed for  ExpirationInterval - %x\n",
        *(_QWORD *)DueTimeb);
      goto LABEL_28;
    }
    LODWORD(v42) = (__int64)Buffer / 10000;
    TicketCacheEntry = StaggerTimeForDmsa((unsigned int *)&v42);
    SuppCredArrayForDmsa = TicketCacheEntry;
    if ( TicketCacheEntry >= 0 )
    {
      if ( CreateTimerQueueTimer(
             (PHANDLE)(v21 + 792),
             0,
             KerbGetDmsaTgtCallback,
             (PVOID)(*(_QWORD *)&(*a1)->Length + 64LL),
             v42,
             0,
             0) )
      {
        wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,long (*)(_RTL_CRITICAL_SECTION *),&long RtlLeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,2>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,long (*)(_RTL_CRITICAL_SECTION *),&long RtlLeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,2>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v44);
        wil::details::unique_storage<wil::details::resource_policy<_KERB_LOGON_SESSION *,void (_KERB_LOGON_SESSION *),&void KerbDereferenceLogonSession(_KERB_LOGON_SESSION *),wistd::integral_constant<unsigned __int64,0>,_KERB_LOGON_SESSION *,_KERB_LOGON_SESSION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_KERB_LOGON_SESSION *,void (_KERB_LOGON_SESSION *),&void KerbDereferenceLogonSession(_KERB_LOGON_SESSION *),wistd::integral_constant<unsigned __int64,0>,_KERB_LOGON_SESSION *,_KERB_LOGON_SESSION *,0,std::nullptr_t>>(&v40);
        return 0;
      }
      MicrosoftTelemetryAssertTriggeredNoArgs(v33);
      KerbTracerT::Log(
        1,
        "KerbGetDmsaTgt::<lambda_2925410eb9906e38deb70bce9a0dcb53>::operator ()",
        3747,
        "Failed to schedule ticket renewal for DMSA\n");
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,long (*)(_RTL_CRITICAL_SECTION *),&long RtlLeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,2>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,long (*)(_RTL_CRITICAL_SECTION *),&long RtlLeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,2>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v44);
      goto LABEL_65;
    }
    v19 = "StaggerTimeForDmsa failed - %x\n";
    v20 = 3734;
    goto LABEL_27;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x18009c9bc  push    rbp
0x18009c9be  push    rbx
0x18009c9bf  push    rsi
0x18009c9c0  push    rdi
0x18009c9c1  push    r12
0x18009c9c3  push    r13
0x18009c9c5  push    r14
0x18009c9c7  push    r15
0x18009c9c9  lea     rbp, [rsp-1Fh]
0x18009c9ce  sub     rsp, 0C8h
0x18009c9d5  mov     rdi, rcx
0x18009c9d8  mov     rax, [rcx]
0x18009c9db  mov     rcx, [rax]
0x18009c9de  xor     r12d, r12d
0x18009c9e1  test    rcx, rcx
0x18009c9e4  jz      loc_18009D1A5
0x18009c9ea  mov     rax, [rdi+8]
0x18009c9ee  cmp     [rax], r12
0x18009c9f1  jz      loc_18009D1A5
0x18009c9f7  mov     rax, [rdi+10h]
0x18009c9fb  cmp     [rax], r12
0x18009c9fe  jz      loc_18009D1A5
0x18009ca04  test    byte ptr [rcx+210h], 20h
0x18009ca0b  jnz     short loc_18009CA12
0x18009ca0d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009ca12  mov     [rbp+57h+arg_0], 3E7h
0x18009ca1a  lea     rdx, [rbp+57h+arg_0]
0x18009ca1e  lea     rcx, [rbp+57h+var_50]
0x18009ca22  call    ?KerbLocateLogonSessionUnique@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_KERB_LOGON_SESSION@@$$A6AXPEAU1@@Z$1?KerbDereferenceLogonSession@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBU_LUID@@E@Z; KerbLocateLogonSessionUnique(_LUID const *,uchar)
0x18009ca27  nop
0x18009ca28  mov     rbx, [rbp+57h+var_50]
0x18009ca2c  test    rbx, rbx
0x18009ca2f  jnz     short loc_18009CA43
0x18009ca31  lea     r9, aUnableToRefere; "Unable to reference the system logon se"...
0x18009ca38  mov     r8d, 0D96h
0x18009ca3e  jmp     loc_18009D182
0x18009ca43  mov     rcx, [rdi+10h]
0x18009ca47  mov     rax, [rdi+18h]
0x18009ca4b  mov     qword ptr [rsp+100h+DueTime], rax; unsigned int
0x18009ca50  mov     r9d, 2
0x18009ca56  lea     rdx, ?KerbGlobalKdcServiceName@@3U_UNICODE_STRING@@A; _UNICODE_STRING KerbGlobalKdcServiceName
0x18009ca5d  mov     rcx, [rcx]
0x18009ca60  call    KerbBuildFullServiceKdcNameWithSid
0x18009ca65  mov     r14d, eax
0x18009ca68  test    eax, eax
0x18009ca6a  jz      short loc_18009CA9D
0x18009ca6c  mov     [rsp+100h+DueTime], eax
0x18009ca70  lea     r9, aKerbbuildfulls; "KerbBuildFullServiceKdcName failed Kerb"...
0x18009ca77  mov     r8d, 0DA3h
0x18009ca7d  lea     rdx, aKerbgetdmsatgt; "KerbGetDmsaTgt::<lambda_2925410eb9906e3"...
0x18009ca84  mov     ecx, 1
0x18009ca89  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18009ca8e  mov     ecx, r14d; int
0x18009ca91  call    ?KerbMapKerbError@@YAJJ@Z; KerbMapKerbError(long)
0x18009ca96  mov     ebx, eax
0x18009ca98  jmp     loc_18009D198
0x18009ca9d  mov     r8, [rdi+10h]
0x18009caa1  mov     r9, [rdi+20h]; struct _KERB_TICKET_CACHE_ENTRY **
0x18009caa5  mov     r8, [r8]; struct _UNICODE_STRING *
0x18009caa8  mov     rcx, rbx; struct _KERB_LOGON_SESSION *
0x18009caab  call    ?KerbGetTgtToS4URealm@@YAJPEAU_KERB_LOGON_SESSION@@PEAU_KERB_CREDENTIAL@@PEAU_UNICODE_STRING@@PEAPEAU_KERB_TICKET_CACHE_ENTRY@@KKK@Z; KerbGetTgtToS4URealm(_KERB_LOGON_SESSION *,_KERB_CREDENTIAL *,_UNICODE_STRING *,_KERB_TICKET_CACHE_ENTRY * *,ulong,ulong,ulong)
0x18009cab0  mov     ebx, eax
0x18009cab2  test    eax, eax
0x18009cab4  jns     short loc_18009CADD
0x18009cab6  lea     r9, aKerbgettgttos4_0; "KerbGetTgtToS4URealm cannot get S4U Tgt"...
0x18009cabd  mov     r8d, 0DB4h
0x18009cac3  mov     [rsp+100h+DueTime], eax
0x18009cac7  lea     rdx, aKerbgetdmsatgt; "KerbGetDmsaTgt::<lambda_2925410eb9906e3"...
0x18009cace  mov     ecx, 1
0x18009cad3  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18009cad8  jmp     loc_18009D198
0x18009cadd  mov     rdx, [rdi+8]
0x18009cae1  mov     rcx, [rdi+28h]
0x18009cae5  add     rcx, 8; struct KERB_PRINCIPAL_NAME *
0x18009cae9  mov     rdx, [rdx]; struct _KERB_INTERNAL_NAME *
0x18009caec  call    ?KerbConvertKdcNameToPrincipalName@@YAJPEAUKERB_PRINCIPAL_NAME@@PEAU_KERB_INTERNAL_NAME@@@Z; KerbConvertKdcNameToPrincipalName(KERB_PRINCIPAL_NAME *,_KERB_INTERNAL_NAME *)
0x18009caf1  mov     ebx, eax
0x18009caf3  test    eax, eax
0x18009caf5  jz      short loc_18009CB20
0x18009caf7  lea     r9, aKerbconvertkdc; "KerbConvertKdcNameToPrincipalName faile"...
0x18009cafe  mov     r8d, 0DBEh
0x18009cb04  mov     [rsp+100h+DueTime], ebx
0x18009cb08  lea     rdx, aKerbgetdmsatgt; "KerbGetDmsaTgt::<lambda_2925410eb9906e3"...
0x18009cb0f  mov     ecx, 1
0x18009cb14  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18009cb19  mov     ecx, ebx
0x18009cb1b  jmp     loc_18009CA91
0x18009cb20  mov     rax, [rdi+28h]
0x18009cb24  mov     ecx, 80h
0x18009cb29  or      [rax], cx
0x18009cb2c  mov     rdx, [rdi+10h]
0x18009cb30  mov     rcx, [rdi+28h]
0x18009cb34  add     rcx, 18h
0x18009cb38  mov     rdx, [rdx]
0x18009cb3b  call    KerbConvertUnicodeStringToRealm
0x18009cb40  mov     ebx, eax
0x18009cb42  test    eax, eax
0x18009cb44  jz      short loc_18009CB55
0x18009cb46  lea     r9, aKerbconvertuni; "KerbConvertUnicodeStringToRealm failed "...
0x18009cb4d  mov     r8d, 0DC7h
0x18009cb53  jmp     short loc_18009CB04
0x18009cb55  mov     rax, [rdi+28h]
0x18009cb59  mov     r13d, 40h ; '@'
0x18009cb5f  or      [rax], r13w
0x18009cb63  mov     [rbp+57h+arg_8], r13d
0x18009cb67  mov     dword ptr [rbp+57h+arg_0], 8
0x18009cb6e  mov     eax, dword ptr [rbp+57h+arg_0]
0x18009cb71  or      [rbp+57h+arg_8], eax
0x18009cb74  mov     rax, [rdi+28h]
0x18009cb78  or      word ptr [rax], 10h
0x18009cb7c  mov     rax, [rdi+28h]
0x18009cb80  mov     dword ptr [rax+30h], 20h ; ' '
0x18009cb87  mov     rax, [rdi+28h]
0x18009cb8b  lea     rcx, [rbp+57h+arg_8]
0x18009cb8f  mov     [rax+38h], rcx
0x18009cb93  mov     rcx, [rdi+18h]
0x18009cb97  mov     r9, [rdi+20h]
0x18009cb9b  mov     rax, [rdi+58h]
0x18009cb9f  mov     [rsp+100h+var_58], rax; struct _DMSA_KEY_PACKAGE *
0x18009cba7  mov     rax, [rdi+50h]
0x18009cbab  mov     [rsp+100h+var_60], rax; unsigned int *
0x18009cbb3  mov     rax, [rdi+48h]
0x18009cbb7  mov     [rsp+100h+var_68], rax; struct _UNICODE_STRING *
0x18009cbbf  mov     rax, [rdi+40h]
0x18009cbc3  mov     [rsp+100h+var_70], rax; unsigned int *
0x18009cbcb  mov     rax, [rdi+38h]
0x18009cbcf  mov     [rsp+100h+var_78], rax; struct KERB_ENCRYPTED_KDC_REPLY **
0x18009cbd7  mov     rax, [rdi+30h]
0x18009cbdb  mov     [rsp+100h+var_80], rax; struct KERB_KDC_REPLY **
0x18009cbe3  mov     [rsp+100h+var_88], r12; union _LARGE_INTEGER *
0x18009cbe8  mov     [rsp+100h+var_90], r12; struct _KERB_ENCRYPTION_KEY *
0x18009cbed  mov     [rsp+100h+var_98], r12; struct KERB_TICKET *
0x18009cbf2  mov     [rsp+100h+var_A0], r12; struct KERB_TGT_REPLY *
0x18009cbf7  mov     [rsp+100h+var_A8], r12; struct KERB_KDC_REQUEST_preauth_data_s *
0x18009cbfc  mov     rax, [rdi+28h]
0x18009cc00  mov     [rsp+100h+var_B0], rax; struct PA_S4U_X509_USER *
0x18009cc05  mov     [rsp+100h+var_B8], r12; struct KERB_PA_FOR_USER *
0x18009cc0a  mov     [rsp+100h+var_C0], r12; struct PKERB_AUTHORIZATION_DATA_s *
0x18009cc0f  mov     dword ptr [rsp+100h+var_C8], r12d; unsigned int
0x18009cc14  mov     [rsp+100h+Flags], r12d; unsigned int
0x18009cc19  mov     [rsp+100h+Period], r12d; unsigned int
0x18009cc1e  mov     rax, [rcx]
0x18009cc21  mov     qword ptr [rsp+100h+DueTime], rax; struct _KERB_INTERNAL_NAME *
0x18009cc26  mov     r9, [r9]; struct _KERB_TICKET_CACHE_ENTRY *
0x18009cc29  xor     r8d, r8d; struct _KERB_PROXY_LOGON_CRED *
0x18009cc2c  xor     edx, edx; struct _KERB_CREDENTIAL *
0x18009cc2e  xor     ecx, ecx; struct _KERB_LOGON_SESSION *
0x18009cc30  call    ?KerbGetTgsTicketEx@@YAJPEAU_KERB_LOGON_SESSION@@PEAU_KERB_CREDENTIAL@@PEAU_KERB_PROXY_LOGON_CRED@@PEAU_KERB_TICKET_CACHE_ENTRY@@PEAU_KERB_INTERNAL_NAME@@KKKPEAUPKERB_AUTHORIZATION_DATA_s@@PEAUKERB_PA_FOR_USER@@PEAUPA_S4U_X509_USER@@PEAUKERB_KDC_REQUEST_preauth_data_s@@PEAUKERB_TGT_REPLY@@PEAUKERB_TICKET@@PEAU_KERB_ENCRYPTION_KEY@@PEAT_LARGE_INTEGER@@PEAPEAUKERB_KDC_REPLY@@PEAPEAUKERB_ENCRYPTED_KDC_REPLY@@PEAKPEAU_UNICODE_STRING@@PEAKPEAU_DMSA_KEY_PACKAGE@@@Z; KerbGetTgsTicketEx(_KERB_LOGON_SESSION *,_KERB_CREDENTIAL *,_KERB_PROXY_LOGON_CRED *,_KERB_TICKET_CACHE_ENTRY *,_KERB_INTERNAL_NAME *,ulong,ulong,ulong,PKERB_AUTHORIZATION_DATA_s *,KERB_PA_FOR_USER *,PA_S4U_X509_USER *,KERB_KDC_REQUEST_preauth_data_s *,KERB_TGT_REPLY *,KERB_TICKET *,_KERB_ENCRYPTION_KEY *,_LARGE_INTEGER *,KERB_KDC_REPLY * *,KERB_ENCRYPTED_KDC_REPLY * *,ulong *,_UNICODE_STRING *,ulong *,_DMSA_KEY_PACKAGE *)
0x18009cc35  mov     ebx, eax
0x18009cc37  test    eax, eax
0x18009cc39  jns     short loc_18009CC4D
0x18009cc3b  lea     r9, aFailedToGetDms; "Failed to get DMSA Tgt - %x\n"
0x18009cc42  mov     r8d, 0DEEh
0x18009cc48  jmp     loc_18009CAC3
0x18009cc4d  mov     rax, [rdi+40h]
0x18009cc51  cmp     [rax], r12d
0x18009cc54  jz      short loc_18009CC5B
0x18009cc56  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009cc5b  mov     rax, [rdi+58h]
0x18009cc5f  cmp     [rax+10h], r12
0x18009cc63  jl      loc_18009D170
0x18009cc69  cmp     [rax+18h], r12
0x18009cc6d  jl      loc_18009D170
0x18009cc73  mov     rax, [rdi]
0x18009cc76  mov     rdx, [rax]
0x18009cc79  add     rdx, 50h ; 'P'
0x18009cc7d  lea     rcx, [rbp+57h+arg_10]
0x18009cc81  call    ?RtlEnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AJPEAU1@@Z$1?RtlLeaveCriticalSection@@YAJ0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::RtlEnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18009cc86  nop
0x18009cc87  mov     rax, [rdi]
0x18009cc8a  mov     rcx, [rax]
0x18009cc8d  mov     rax, [rdi+20h]
0x18009cc91  mov     r8, [rax]
0x18009cc94  lea     r9, [rcx+88h]
0x18009cc9b  add     rcx, 168h
0x18009cca2  mov     rax, [rdi+50h]
0x18009cca6  mov     r10d, [rax]
0x18009cca9  mov     esi, 1
0x18009ccae  or      r10d, esi
0x18009ccb1  mov     rdx, [rdi+38h]
0x18009ccb5  mov     r11, [rdi+30h]
0x18009ccb9  mov     rax, [rdi+60h]
0x18009ccbd  mov     [rsp+100h+var_A0], rax; struct _KERB_TICKET_CACHE_ENTRY **
0x18009ccc2  mov     [rsp+100h+var_A8], r12; unsigned __int64
0x18009ccc7  mov     [rsp+100h+var_B0], r9; struct _UNICODE_STRING *
0x18009cccc  mov     rax, [rdi+48h]
0x18009ccd0  mov     [rsp+100h+var_B8], rax; struct _UNICODE_STRING *
0x18009ccd5  mov     [rsp+100h+var_C0], r12; struct _KERB_ENCRYPTION_KEY *
0x18009ccda  mov     [rsp+100h+var_C8], rcx; struct _KERB_TICKET_CACHE *
0x18009ccdf  mov     eax, [r8+158h]
0x18009cce6  mov     [rsp+100h+Flags], eax; int
0x18009ccea  mov     [rsp+100h+Period], r10d; unsigned int
0x18009ccef  mov     qword ptr [rsp+100h+DueTime], r12; struct _UNICODE_STRING *
0x18009ccf4  xor     r9d, r9d; struct _KERB_INTERNAL_NAME *
0x18009ccf7  mov     r8, [r8+0A8h]; struct KerbCredIsoApi *
0x18009ccfe  mov     rdx, [rdx]; struct KERB_ENCRYPTED_KDC_REPLY *
0x18009cd01  mov     rcx, [r11]; struct KERB_KDC_REPLY *
0x18009cd04  call    ?KerbCreateTicketCacheEntry@@YAJPEAUKERB_KDC_REPLY@@PEAUKERB_ENCRYPTED_KDC_REPLY@@PEAVKerbCredIsoApi@@PEAU_KERB_INTERNAL_NAME@@PEAU_UNICODE_STRING@@KJPEAU_KERB_TICKET_CACHE@@PEAU_KERB_ENCRYPTION_KEY@@44_KPEAPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbCreateTicketCacheEntry(KERB_KDC_REPLY *,KERB_ENCRYPTED_KDC_REPLY *,KerbCredIsoApi *,_KERB_INTERNAL_NAME *,_UNICODE_STRING *,ulong,long,_KERB_TICKET_CACHE *,_KERB_ENCRYPTION_KEY *,_UNICODE_STRING *,_UNICODE_STRING *,unsigned __int64,_KERB_TICKET_CACHE_ENTRY * *)
0x18009cd09  mov     ebx, eax
0x18009cd0b  test    eax, eax
0x18009cd0d  jns     short loc_18009CD3D
0x18009cd0f  lea     r9, aFailedToCreate_0; "Failed to create a cache entry and inse"...
0x18009cd16  mov     r8d, 0E0Eh
0x18009cd1c  mov     [rsp+100h+DueTime], eax
0x18009cd20  lea     rdx, aKerbgetdmsatgt; "KerbGetDmsaTgt::<lambda_2925410eb9906e3"...
0x18009cd27  mov     ecx, esi
0x18009cd29  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18009cd2e  nop
0x18009cd2f  lea     rcx, [rbp+57h+arg_10]
0x18009cd33  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AJPEAU1@@Z$1?RtlLeaveCriticalSection@@YAJ0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,long (*)(_RTL_CRITICAL_SECTION *),&RtlLeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,2>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,long (*)(_RTL_CRITICAL_SECTION *),&RtlLeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,2>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18009cd38  jmp     loc_18009D198
0x18009cd3d  mov     rax, [rdi]
0x18009cd40  mov     r14, [rax]
0x18009cd43  call    ?KerbGetSystemTime@@YA?AT_LARGE_INTEGER@@XZ; KerbGetSystemTime(void)
0x18009cd48  mov     r10, rax
0x18009cd4b  mov     [rbp+57h+arg_18], r12
0x18009cd4f  mov     [rbp+57h+arg_0], r12
0x18009cd53  mov     [rbp+57h+var_48], 23C34600h
0x18009cd5b  mov     r11, [rdi+58h]
0x18009cd5f  lea     r8, [rbp+57h+arg_0]
0x18009cd63  mov     rdx, rax
0x18009cd66  mov     rcx, [r11+10h]
0x18009cd6a  call    RtlLongLongAdd
0x18009cd6f  mov     ebx, eax
0x18009cd71  test    eax, eax
0x18009cd73  jns     short loc_18009CD84
0x18009cd75  lea     r9, aRtllonglongadd; "RtlLongLongAdd failed for  ExpirationTi"...
0x18009cd7c  mov     r8d, 0E1Dh
0x18009cd82  jmp     short loc_18009CD1C
0x18009cd84  lea     r8, [rbp+57h+arg_18]
0x18009cd88  mov     rdx, r10
0x18009cd8b  mov     rcx, [r11+18h]
0x18009cd8f  call    RtlLongLongAdd
0x18009cd94  mov     ebx, eax
0x18009cd96  test    eax, eax
0x18009cd98  jns     short loc_18009CDAC
0x18009cd9a  lea     r9, aRtllonglongadd; "RtlLongLongAdd failed for  ExpirationTi"...
0x18009cda1  mov     r8d, 0E24h
0x18009cda7  jmp     loc_18009CD1C
0x18009cdac  mov     rax, [rdi+68h]
0x18009cdb0  mov     rcx, [rax]
0x18009cdb3  test    rcx, rcx
0x18009cdb6  jz      short loc_18009CDBA
0x18009cdb8  mov     [rcx], esi
0x18009cdba  lea     r10, [r14+2F0h]
0x18009cdc1  lea     r8, [rbp+57h+var_48]
0x18009cdc5  lea     rdx, [rbp+57h+arg_0]
0x18009cdc9  mov     rcx, r10
0x18009cdcc  call    KerbCheckTimeSkew
0x18009cdd1  test    al, al
0x18009cdd3  jz      short loc_18009CDFE
0x18009cdd5  lea     rcx, [r14+2F8h]
0x18009cddc  lea     r8, [rbp+57h+var_48]
0x18009cde0  lea     rdx, [rbp+57h+arg_18]
0x18009cde4  call    KerbCheckTimeSkew
0x18009cde9  test    al, al
0x18009cdeb  jz      short loc_18009CDFE
0x18009cded  lea     rcx, [rbp+57h+arg_10]
0x18009cdf1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AJPEAU1@@Z$1?RtlLeaveCriticalSection@@YAJ0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,long (*)(_RTL_CRITICAL_SECTION *),&RtlLeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,2>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,long (*)(_RTL_CRITICAL_SECTION *),&RtlLeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,2>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18009cdf6  mov     ebx, r12d
0x18009cdf9  jmp     loc_18009D198
0x18009cdfe  mov     rax, [rdi+70h]
0x18009ce02  mov     [rax], esi
0x18009ce04  mov     rax, [rbp+57h+arg_0]
0x18009ce08  mov     [r10], rax
0x18009ce0b  mov     rax, [rbp+57h+arg_18]
0x18009ce0f  mov     [r14+2F8h], rax
0x18009ce16  mov     rax, [rdi]
0x18009ce19  mov     rcx, [rax]
0x18009ce1c  mov     rcx, [rcx+110h]
0x18009ce23  call    cs:__imp_?KerbClientFreeStoredCred@@YAXPEAU_KERB_STORED_CREDENTIAL@@@Z; KerbClientFreeStoredCred(_KERB_STORED_CREDENTIAL *)
0x18009ce29  mov     rax, [rdi]
0x18009ce2c  mov     rcx, [rax]
0x18009ce2f  mov     rcx, [rcx+108h]
0x18009ce36  call    cs:__imp_?KerbClientFreeStoredCred@@YAXPEAU_KERB_STORED_CREDENTIAL@@@Z; KerbClientFreeStoredCred(_KERB_STORED_CREDENTIAL *)
0x18009ce3c  mov     rdx, [rdi+58h]
0x18009ce40  mov     rax, [rdi]
0x18009ce43  mov     rcx, [rax]
0x18009ce46  mov     rax, [rdx+8]
0x18009ce4a  mov     [rcx+108h], rax
0x18009ce51  mov     rdx, [rdi+58h]
0x18009ce55  mov     rax, [rdi]
0x18009ce58  mov     rcx, [rax]
0x18009ce5b  mov     rax, [rdx]
0x18009ce5e  mov     [rcx+110h], rax
0x18009ce65  mov     rax, [rdi+58h]
0x18009ce69  mov     [rax+8], r12
0x18009ce6d  mov     rax, [rdi+58h]
0x18009ce71  mov     [rax], r12
0x18009ce74  mov     rax, [rdi]
0x18009ce77  mov     rcx, [rax]
0x18009ce7a  add     rcx, 78h ; 'x'; struct _KERB_PRIMARY_CREDENTIAL *
0x18009ce7e  test    [rcx+198h], r13b
0x18009ce85  jz      loc_18009CFAB
0x18009ce8b  mov     rdx, [rdi+78h]; struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **
0x18009ce8f  call    ?KerbGetSuppCredArrayForDmsa@@YAJAEBU_KERB_PRIMARY_CREDENTIAL@@PEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@@Z; KerbGetSuppCredArrayForDmsa(_KERB_PRIMARY_CREDENTIAL const &,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *)
0x18009ce94  mov     ebx, eax
0x18009ce96  test    eax, eax
0x18009ce98  jns     short loc_18009CEB5
0x18009ce9a  call    MicrosoftTelemetryAssertTriggeredNoArgs
  ... truncated ...
```
