# CompareStringW

- ea: `0x180027400`
- end: `0x180028359`
- name: `CompareStringW`
- size: `3929`
- prototype: `int __stdcall(LCID Locale, DWORD dwCmpFlags, PCNZWCH lpString1, int cchCount1, PCNZWCH lpString2, int cchCount2)`
- caller_count: `6`
- callee_count: `25`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800050b0`
- `0x1800b2f74`
- `0x1800bbab0`
- `0x1800e3e58`
- `0x1800ee220`
- `0x180109800`

## callees

- `0x18001cd34`
- `0x180024c80`
- `0x1800265f0`
- `0x180027400`
- `0x180028360`
- `0x180028490`
- `0x1800285f0`
- `0x1800294a0`
- `0x180029660`
- `0x180029ec0`
- `0x18002aabc`
- `0x1800461b0`
- `0x180046520`
- `0x180046ac0`
- `0x1800486a0`
- `0x180048f20`
- `0x18004a310`
- `0x18004a820`
- `0x18004b408`
- `0x18012c3ac`
- `0x1801369c9`
- `0x180142ba0`
- `0x180194eb9`
- `0x180194f10`
- `0x1801a4010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180028181`
- `ntdll!RtlInitUnicodeString` at `0x180028181`
- `ntdll!NtOpenKey` at `0x1800281cb`
- `ntdll!NtOpenKey` at `0x1800281cb`
- `ntdll!NtCreateKey` at `0x180028209`
- `ntdll!NtCreateKey` at `0x180028209`
- `ntdll!RtlLcidToLocaleName` at `0x1800280b1`
- `ntdll!RtlLcidToLocaleName` at `0x1800280b1`
- `ntdll!RtlOpenCurrentUser` at `0x180027dd3`
- `ntdll!RtlOpenCurrentUser` at `0x180027dd3`
- `ntdll!CsrClientCallServer` at `0x180027bc6`
- `ntdll!CsrClientCallServer` at `0x180027bc6`
- `ntdll!CsrCaptureMessageBuffer` at `0x180027ba0`
- `ntdll!CsrCaptureMessageBuffer` at `0x180027ba0`
- `ntdll!CsrFreeCaptureBuffer` at `0x180027bf1`
- `ntdll!CsrFreeCaptureBuffer` at `0x180027bf1`
- `ntdll!CsrAllocateCaptureBuffer` at `0x1800278ab`
- `ntdll!CsrAllocateCaptureBuffer` at `0x1800278ab`
- `ntdll!NtClose` at `0x180027924`
- `ntdll!NtClose` at `0x180027e77`
- `ntdll!NtClose` at `0x180028221`
- `ntdll!NtClose` at `0x180028262`
- `ntdll!NtClose` at `0x180027924`
- `ntdll!NtClose` at `0x180027e77`
- `ntdll!NtClose` at `0x180028221`
- `ntdll!NtClose` at `0x180028262`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800274ab`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800275ea`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180027861`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800279a4`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180027b3f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180027cd5`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800274ab`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800275ea`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180027861`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800279a4`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180027b3f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180027cd5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180027597`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800276d6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180027a8f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180027ac8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180027b6e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180027d33`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180027597`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800276d6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180027a8f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180027ac8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180027b6e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180027d33`
- `ntdll!RtlAllocateHeap` at `0x18002812c`
- `ntdll!RtlAllocateHeap` at `0x18002812c`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
int __stdcall CompareStringW(
        LCID Locale,
        DWORD dwCmpFlags,
        PCNZWCH lpString1,
        int cchCount1,
        PCNZWCH lpString2,
        int cchCount2)
{
  unsigned int v6; // r14d
  unsigned __int64 v9; // rdi
  HANDLE NamedLocaleHashNode; // rax
  DWORD v11; // ebx
  __int64 j; // rdx
  unsigned int *v13; // rax
  __int64 v14; // r8
  DWORD v15; // ebx
  _WORD *v16; // rcx
  __int64 LocaleHashNode; // rax
  DWORD v18; // ebx
  __int64 i; // rdx
  unsigned int *WindowsLocaleData; // rax
  __int64 v21; // r8
  DWORD v22; // ebx
  _WORD *v23; // rcx
  __int64 LocHashNodeFromSystemLocale; // rax
  __int64 v25; // rcx
  __int64 v26; // rbx
  __int64 v27; // rsi
  __int16 *v28; // rbx
  __int64 SortNode; // rax
  __int64 IsImpersonating; // rcx
  int IsInteractiveUserProcess; // eax
  __int16 v33; // ax
  struct _CSR_CAPTURE_BUFFER *CaptureBuffer; // rax
  struct _CSR_CAPTURE_BUFFER *v35; // rbx
  NTSTATUS v36; // esi
  HANDLE v37; // rbx
  __int64 v38; // rbx
  __int64 v39; // rax
  DWORD v40; // ebx
  __int64 k; // rdx
  unsigned int *v42; // rax
  __int64 v43; // r8
  DWORD v44; // ebx
  _WORD *v45; // rcx
  __int64 v46; // rax
  HANDLE *NlsCache; // rbx
  __int64 v48; // rdx
  __int64 v49; // rdx
  int v50; // eax
  int GlobalizationUserModelType; // eax
  int v52; // eax
  __int64 v53; // rcx
  WCHAR *v54; // rax
  __int64 v55; // r9
  const WCHAR *v56; // rdx
  WCHAR *v57; // r8
  __int64 v58; // rcx
  WCHAR *v59; // rcx
  __int64 v60; // rdx
  int v61; // ecx
  int v62; // r14d
  int v63; // eax
  __int64 NlsTebCache; // rax
  HANDLE *Heap; // rax
  NTSTATUS v66; // ebx
  HANDLE v67; // rcx
  void *v68; // rbx
  unsigned int *v69; // rcx
  __int64 v70; // r8
  _WORD *v71; // rcx
  __int64 v72; // rax
  __int64 v73; // rax
  HANDLE Handle; // [rsp+50h] [rbp-B0h] BYREF
  ULONG Disposition; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE KeyHandle[2]; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  __int64 v78; // [rsp+80h] [rbp-80h]
  __int64 v79; // [rsp+88h] [rbp-78h]
  int v80; // [rsp+90h] [rbp-70h] BYREF
  int v81; // [rsp+94h] [rbp-6Ch]
  PCNZWCH v82; // [rsp+98h] [rbp-68h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ApiMessage[32]; // [rsp+D0h] [rbp-30h] BYREF
  PVOID CapturedData; // [rsp+110h] [rbp+10h] BYREF
  int v86; // [rsp+118h] [rbp+18h]

  v6 = cchCount1;
  v82 = lpString2;
  v81 = cchCount1;
  v9 = Locale;
  if ( Locale == 127 )
  {
    NamedLocaleHashNode = (HANDLE)gpInvLocHashN;
    goto LABEL_44;
  }
  if ( Locale > 0xC00 )
  {
    if ( Locale == 4096 )
    {
      NamedLocaleHashNode = (HANDLE)gpOneCustomHashNode;
      if ( gpOneCustomHashNode )
        goto LABEL_49;
    }
    else if ( Locale != 5120 )
    {
      goto LABEL_26;
    }
    KeyHandle[0] = (HANDLE)11141120;
    KeyHandle[1] = ApiMessage;
    if ( (int)RtlLcidToLocaleName(Locale, KeyHandle, 0, 0) >= 0 )
    {
      NamedLocaleHashNode = (HANDLE)GetNamedLocaleHashNode(KeyHandle[1], 0);
      if ( NamedLocaleHashNode )
        goto LABEL_49;
    }
LABEL_26:
    NamedLocaleHashNode = (HANDLE)gpSysLocHashN;
    if ( gpSysLocHashN || BasepIsSecureProcess )
    {
LABEL_43:
      if ( (_DWORD)v9 != *(_DWORD *)NamedLocaleHashNode )
        goto LABEL_45;
      goto LABEL_44;
    }
    RtlAcquireSRWLockExclusive(&gTblPtrsLock);
    if ( gpSysLocHashN )
      goto LABEL_42;
    v18 = gSystemLocale;
    for ( i = *((_QWORD *)P
              + (((unsigned __int8)gSystemLocale
                ^ (unsigned __int8)((gSystemLocale ^ ((unsigned __int64)gSystemLocale >> 7)) >> 7))
               & 0x7F)); i; i = *(_QWORD *)(i + 88) )
    {
      if ( *(_DWORD *)i == gSystemLocale )
        break;
    }
    gpSysLocHashN = i;
    if ( i )
      goto LABEL_42;
    if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
      goto LABEL_104;
    WindowsLocaleData = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
    if ( WindowsLocaleData )
    {
      if ( (_WORD)v18 != 127 )
      {
        v22 = HIWORD(v18);
        if ( (v22 & 0xF) == 0 )
        {
          v23 = (_WORD *)(qword_1803A6BD0 + 2 + 2LL * *WindowsLocaleData);
LABEL_38:
          LocHashNodeFromSystemLocale = MakeNamedLocaleHashNode(v23, 0);
          goto LABEL_39;
        }
        v48 = WindowsLocaleData[54];
        v23 = (_WORD *)qword_1803A6BD0;
        if ( (_DWORD)v48 )
          v23 = (_WORD *)(qword_1803A6BD0
                        + 2LL * *(unsigned int *)(qword_1803A6BD0 + 2 * (v48 + 2LL * (v22 & 0xF)) - 2)
                        + 2);
        if ( v23 && *v23 )
          goto LABEL_38;
LABEL_104:
        gpSysLocHashN = 0;
LABEL_40:
        gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
        if ( !gpSysLocHashN )
          gpSysLocHashN = gpInvLocHashN;
        goto LABEL_42;
      }
      LocHashNodeFromSystemLocale = MakeLocHashNodeFromSystemLocale(WindowsLocaleData, v18, v21, 0);
    }
    else
    {
      if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
        goto LABEL_104;
      if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
        || (unsigned int)CreateTransientLocales() )
      {
        LocHashNodeFromSystemLocale = FindLocaleHashNode(v18);
      }
      else
      {
        LocHashNodeFromSystemLocale = 0;
      }
    }
LABEL_39:
    gpSysLocHashN = LocHashNodeFromSystemLocale;
    if ( !LocHashNodeFromSystemLocale )
      goto LABEL_40;
LABEL_42:
    RtlReleaseSRWLockExclusive(&gTblPtrsLock);
    NamedLocaleHashNode = (HANDLE)gpSysLocHashN;
    goto LABEL_43;
  }
  if ( Locale != 3072 && Locale && Locale != 1024 )
  {
    if ( Locale == 2048 )
    {
      NamedLocaleHashNode = (HANDLE)gpSysLocHashN;
      if ( gpSysLocHashN )
        goto LABEL_49;
      if ( BasepIsSecureProcess )
        goto LABEL_44;
      RtlAcquireSRWLockExclusive(&gTblPtrsLock);
      if ( gpSysLocHashN )
        goto LABEL_23;
      v11 = gSystemLocale;
      for ( j = *((_QWORD *)P
                + (((unsigned __int8)gSystemLocale
                  ^ (unsigned __int8)((gSystemLocale ^ ((unsigned __int64)gSystemLocale >> 7)) >> 7))
                 & 0x7F)); j; j = *(_QWORD *)(j + 88) )
      {
        if ( *(_DWORD *)j == gSystemLocale )
          break;
      }
      gpSysLocHashN = j;
      if ( j )
        goto LABEL_23;
      if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
        goto LABEL_127;
      v13 = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
      if ( v13 )
      {
        if ( (_WORD)v11 != 127 )
        {
          v15 = HIWORD(v11);
          if ( (v15 & 0xF) == 0 )
          {
            v16 = (_WORD *)(qword_1803A6BD0 + 2 + 2LL * *v13);
LABEL_19:
            LocaleHashNode = MakeNamedLocaleHashNode(v16, 0);
            goto LABEL_20;
          }
          v49 = v13[54];
          v16 = (_WORD *)qword_1803A6BD0;
          if ( (_DWORD)v49 )
            v16 = (_WORD *)(qword_1803A6BD0
                          + 2LL * *(unsigned int *)(qword_1803A6BD0 + 2 * (v49 + 2LL * (v15 & 0xF)) - 2)
                          + 2);
          if ( v16 && *v16 )
            goto LABEL_19;
LABEL_127:
          gpSysLocHashN = 0;
          goto LABEL_21;
        }
        LocaleHashNode = MakeLocHashNodeFromSystemLocale(v13, v11, v14, 0);
      }
      else
      {
        if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
          goto LABEL_127;
        if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
          || (unsigned int)CreateTransientLocales() )
        {
          LocaleHashNode = FindLocaleHashNode(v11);
        }
        else
        {
          LocaleHashNode = 0;
        }
      }
LABEL_20:
      gpSysLocHashN = LocaleHashNode;
      if ( LocaleHashNode )
      {
LABEL_23:
        RtlReleaseSRWLockExclusive(&gTblPtrsLock);
        NamedLocaleHashNode = (HANDLE)gpSysLocHashN;
        goto LABEL_44;
      }
LABEL_21:
      gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
      if ( !gpSysLocHashN )
        gpSysLocHashN = gpInvLocHashN;
      goto LABEL_23;
    }
    goto LABEL_26;
  }
  IsImpersonating = NtCurrentTeb()->IsImpersonating;
  if ( !(_DWORD)IsImpersonating )
  {
    IsInteractiveUserProcess = gInteractiveLogonUserProcess;
    if ( gInteractiveLogonUserProcess == -1 )
      IsInteractiveUserProcess = NlsInitIsInteractiveUserProcess(IsImpersonating, dwCmpFlags, lpString1);
    if ( !IsInteractiveUserProcess )
    {
      NlsCheckStaleCache();
      goto LABEL_98;
    }
    if ( dword_1803AC290 != *(_DWORD *)(gpServerNlsUserInfo + 1656) )
      word_1803AC296 = 1;
    if ( !word_1803AC296 )
      goto LABEL_98;
    v33 = word_1803AC294;
    if ( word_1803AC294 != 3 )
    {
      RtlAcquireSRWLockExclusive(&gNlsProcessCacheLock);
      v33 = word_1803AC294;
      if ( word_1803AC294 != 3 )
      {
        if ( !word_1803AC296 )
          goto LABEL_97;
        v33 = word_1803AC294;
      }
    }
    word_1803AC296 = 2;
    if ( v33 == 1 )
    {
      memset_0(ApiMessage, 0, 0x3B8u);
      CaptureBuffer = CsrAllocateCaptureBuffer(1u, 0x67Cu);
      v35 = CaptureBuffer;
      if ( CaptureBuffer )
      {
        CsrCaptureMessageBuffer(CaptureBuffer, 0, 0x67Cu, &CapturedData);
        v86 = 1660;
        v36 = CsrClientCallServer(ApiMessage, v35, (CSR_API_NUMBER)0x1001B, 0x10u);
        if ( v36 >= 0 )
          memcpy_0(&word_1803ABC18, CapturedData, 0x67Cu);
        CsrFreeCaptureBuffer(v35);
      }
      else
      {
        v36 = -1073741801;
      }
      if ( word_1803AC294 == 1 && v36 >= 0 )
      {
LABEL_73:
        if ( word_1803ABC18 == -1 )
        {
          qword_1803ABC10 = 0;
        }
        else
        {
          v38 = gpOneCustomHashNode;
          _InterlockedExchange64(&qword_1803ABC10, GetNamedLocaleHashNode(word_1803ABC1A, 0));
          if ( !v38 && gpOneCustomHashNode )
            gpOneCustomHashNode = 0;
          if ( qword_1803ABC10 )
          {
LABEL_96:
            _InterlockedCompareExchange16(&word_1803AC296, 0, 2);
            if ( word_1803AC294 != 3 )
LABEL_97:
              RtlReleaseSRWLockExclusive(&gNlsProcessCacheLock);
LABEL_98:
            NlsCache = &gNlsProcessLocalCache;
LABEL_99:
            NamedLocaleHashNode = NlsCache[2];
            v6 = v81;
            goto LABEL_44;
          }
        }
        v39 = gpSysLocHashN;
        if ( gpSysLocHashN || BasepIsSecureProcess )
        {
LABEL_95:
          qword_1803ABC10 = v39;
          goto LABEL_96;
        }
        RtlAcquireSRWLockExclusive(&gTblPtrsLock);
        if ( gpSysLocHashN )
          goto LABEL_94;
        v40 = gSystemLocale;
        for ( k = *((_QWORD *)P
                  + (((unsigned __int8)gSystemLocale
                    ^ (unsigned __int8)((gSystemLocale ^ ((unsigned __int64)gSystemLocale >> 7)) >> 7))
                   & 0x7F)); k; k = *(_QWORD *)(k + 88) )
        {
          if ( *(_DWORD *)k == gSystemLocale )
            break;
        }
        gpSysLocHashN = k;
        if ( k )
          goto LABEL_94;
        if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
          goto LABEL_162;
        v42 = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
        if ( v42 )
        {
          if ( (_WORD)v40 != 127 )
          {
            v44 = HIWORD(v40);
            if ( (v44 & 0xF) == 0 )
            {
              v45 = (_WORD *)(qword_1803A6BD0 + 2 + 2LL * *v42);
LABEL_90:
              v46 = MakeNamedLocaleHashNode(v45, 0);
              goto LABEL_91;
            }
            v60 = v42[54];
            v45 = (_WORD *)qword_1803A6BD0;
            if ( (_DWORD)v60 )
              v45 = (_WORD *)(qword_1803A6BD0
                            + 2LL * *(unsigned int *)(qword_1803A6BD0 + 2 * (v60 + 2LL * (v44 & 0xF)) - 2)
                            + 2);
            if ( v45 && *v45 )
              goto LABEL_90;
LABEL_162:
            gpSysLocHashN = 0;
LABEL_92:
            gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
            if ( !gpSysLocHashN )
              gpSysLocHashN = gpInvLocHashN;
            goto LABEL_94;
          }
          v46 = MakeLocHashNodeFromSystemLocale(v42, v40, v43, 0);
        }
        else
        {
          if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
            goto LABEL_162;
          if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
            || (unsigned int)CreateTransientLocales() )
          {
            v46 = FindLocaleHashNode(v40);
          }
          else
          {
            v46 = 0;
          }
        }
LABEL_91:
        gpSysLocHashN = v46;
        if ( !v46 )
          goto LABEL_92;
LABEL_94:
        RtlReleaseSRWLockExclusive(&gTblPtrsLock);
        v39 = gpSysLocHashN;
        goto LABEL_95;
      }
    }
    Handle = 0;
    if ( gNlsProcessLocalCache )
    {
      Handle = gNlsProcessLocalCache;
LABEL_70:
      v37 = Handle;
      NlsUpdateCacheInfo(&word_1803ABC18, Handle, 1);
      if ( word_1803AC294 == 3 && v37 )
        NtClose(v37);
      goto LABEL_73;
    }
    KeyHandle[0] = 0;
    Disposition = 0;
    memset(&ObjectAttributes, 0, 44);
    DestinationString = 0;
    GlobalizationUserModelType = GetGlobalizationUserModelType(0, *(_QWORD *)&dwCmpFlags, lpString1);
    if ( GlobalizationUserModelType == 1 )
    {
      v52 = RtlOpenCurrentUser(0x2000000u, KeyHandle);
    }
    else
    {
      v63 = GlobalizationUserModelType - 2;
      if ( v63 )
      {
        if ( v63 != 1 )
        {
LABEL_157:
          SetLastError_0(0x3F1u);
          goto LABEL_70;
        }
        v80 = 0;
        v52 = OpenGlobalizationUserSettingsKey_ForMua(0x2000000u, 0, KeyHandle, &v80);
      }
      else
      {
        v52 = OpenGlobalizationUserSettingsKey_ForSingleUserModel(0x2000000u, KeyHandle);
      }
    }
    if ( v52 >= 0 )
    {
      ApiMessage[0] = 0;
      v53 = 512;
      v54 = ApiMessage;
      do
      {
        if ( !*v54 )
          break;
        ++v54;
        --v53;
      }
      while ( v53 );
      if ( !v53 )
        goto LABEL_155;
      v55 = v53;
      v56 = L"Control Panel\\International";
      v57 = &ApiMessage[512 - v53];
      v58 = 2147483646;
      do
      {
        if ( !v58 )
          break;
        if ( !*v56 )
          break;
        *v57++ = *v56++;
        --v58;
        --v55;
      }
      while ( v55 );
      v59 = v57 - 1;
      if ( v55 )
        v59 = v57;
      *v59 = 0;
      if ( v55 )
      {
        RtlInitUnicodeString(&DestinationString, ApiMessage);
        ObjectAttributes.RootDirectory = KeyHandle[0];
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        Disposition = 0;
        v66 = NtOpenKey(&Handle, 0x20019u, &ObjectAttributes);
        if ( v66 < 0 )
          v66 = NtCreateKey(&Handle, 0x20019u, &ObjectAttributes, 0, 0, 0, &Disposition);
        if ( KeyHandle[0] )
          NtClose(KeyHandle[0]);
        if ( v66 >= 0 )
        {
          v67 = Handle;
        }
        else
        {
          v67 = 0;
          Handle = 0;
        }
        if ( v66 >= 0 )
        {
          v68 = (void *)_InterlockedCompareExchange64(
                          (volatile signed __int64 *)&gNlsProcessLocalCache,
                          (signed __int64)v67,
                          0);
          if ( v68 )
          {
            if ( Handle )
              NtClose(Handle);
            Handle = v68;
          }
          goto LABEL_70;
        }
      }
      else
      {
LABEL_155:
        if ( KeyHandle[0] )
          NtClose(KeyHandle[0]);
      }
    }
    goto LABEL_157;
  }
  NlsCache = 0;
  v61 = IsImpersonating - 1;
  if ( v61 )
  {
    if ( v61 != 1 )
      goto LABEL_99;
    if ( BasepIsSecureProcess )
      goto LABEL_98;
    v62 = 0;
    NlsCache = (HANDLE *)NtCurrentTeb()->NlsCache;
    if ( !NlsCache )
    {
      Heap = (HANDLE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x698u);
      NlsCache = Heap;
      if ( Heap )
      {
        *Heap = 0;
        Heap[1] = 0;
        Heap[2] = 0;
        v62 = 1;
        *((_WORD *)Heap + 842) = 3;
        *((_WORD *)Heap + 843) = 1;
      }
      else
      {
        NlsCache = &gNlsProcessLocalCache;
      }
      NtCurrentTeb()->NlsCache = NlsCache;
    }
    if ( NlsCache == &gNlsProcessLocalCache || !v62 && *((_WORD *)NlsCache + 843) != 1 )
      goto LABEL_99;
    *((_WORD *)NlsCache + 843) = 1;
    UpdateNlsInfoCache(NlsCache, 0);
    NamedLocaleHashNode = NlsCache[2];
    v6 = v81;
  }
  else
  {
    NlsTebCache = GetNlsTebCache(1, dwCmpFlags, lpString1);
    NtCurrentTeb()->IsImpersonating = 2;
    NamedLocaleHashNode = *(HANDLE *)(NlsTebCache + 16);
    v6 = v81;
  }
LABEL_44:
  if ( NamedLocaleHashNode )
    goto LABEL_49;
LABEL_45:
  v25 = ((unsigned __int8)v9 ^ (unsigned __int8)((v9 ^ (v9 >> 7)) >> 7)) & 0x7F;
  v26 = *((_QWORD *)P + v25);
  v27 = 8 * v25;
  if ( v26 )
  {
    while ( *(_DWORD *)v26 != (_DWORD)v9 )
    {
      v26 = *(_QWORD *)(v26 + 88);
      if ( !v26 )
        goto LABEL_106;
    }
    goto LABEL_47;
  }
LABEL_106:
  RtlAcquireSRWLockExclusive(&gTblPtrsLock);
  v26 = *(_QWORD *)((char *)P + v27);
  if ( v26 )
  {
    while ( *(_DWORD *)v26 != (_DWORD)v9 )
    {
      v26 = *(_QWORD *)(v26 + 88);
      if ( !v26 )
        goto LABEL_215;
    }
    goto LABEL_108;
  }
LABEL_215:
  if ( (v9 & 0xFFF00000) != 0 || BasepIsSecureProcess )
    goto LABEL_227;
  v69 = (unsigned int *)GetWindowsLocaleData((unsigned int)v9);
  if ( !v69 )
  {
    if ( !(unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
      && ((unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
       || (unsigned int)CreateTransientLocales()) )
    {
      v72 = FindLocaleHashNode((unsigned int)v9);
      goto LABEL_222;
    }
    goto LABEL_227;
  }
  if ( (_WORD)v9 == 127 )
  {
    v26 = MakeLocHashNodeFromSystemLocale(v69, (unsigned int)v9, v70, 0);
    goto LABEL_108;
  }
  if ( (v9 & 0xF0000) != 0 )
  {
    v73 = v69[54];
    v71 = (_WORD *)qword_1803A6BD0;
    if ( (_DWORD)v73 )
      v71 = (_WORD *)(qword_1803A6BD0
                    + 2LL * *(unsigned int *)(qword_1803A6BD0 + 2 * (v73 + 2LL * (BYTE2(v9) & 0xF)) - 2)
                    + 2);
    if ( v71 && *v71 )
      goto LABEL_221;
LABEL_227:
    v26 = 0;
    goto LABEL_108;
  }
  v71 = (_WORD *)(qword_1803A6BD0 + 2 + 2LL * *v69);
LABEL_221:
  v72 = MakeNamedLocaleHashNode(v71, 0);
LABEL_222:
  v26 = v72;
LABEL_108:
  RtlReleaseSRWLockExclusive(&gTblPtrsLock);
LABEL_47:
  if ( v26 )
  {
    NamedLocaleHashNode = *(HANDLE *)(v26 + 104);
    if ( NamedLocaleHashNode )
      goto LABEL_49;
  }
  else
  {
    NamedLocaleHashNode = 0;
  }
  if ( (_DWORD)v9 == 4096 || (v9 & 0x3FF) == 0 && (unsigned int)(v9 - 0x2000) <= 0x2C00 )
    NamedLocaleHashNode = GetCurrentNlsCache()[2];
  if ( !NamedLocaleHashNode )
    goto LABEL_50;
LABEL_49:
  v28 = (__int16 *)*((_QWORD *)NamedLocaleHashNode + 4);
  if ( !v28 )
    goto LABEL_50;
  if ( !g_definedDefaultSortVersion )
  {
    *(_QWORD *)&DestinationString.Length = 32;
    DestinationString.Buffer = 0;
    v78 = 0;
    v79 = 0;
    RtlAcquireSRWLockExclusive(&gTblPtrsLock);
    if ( !g_definedDefaultSortVersion )
    {
      if ( (unsigned int)QueryRegDefaultSortingVersion(&DestinationString)
        && (unsigned int)QueryRegSortVersionDll(&DestinationString, 0, 0) )
      {
        v50 = *(_DWORD *)(&DestinationString.MaximumLength + 1);
      }
      else
      {
        v50 = 256;
      }
      dword_1803A52B4 = v50 | 0xFF;
      dword_1803A52B8 = v50 | 0xFF;
      _InterlockedExchange(&g_definedDefaultSortVersion, 1);
    }
    RtlReleaseSRWLockExclusive(&gTblPtrsLock);
  }
  SortNode = GetSortNode(v28, (__int64)g_defaultSortVersion, 0);
  if ( !SortNode )
  {
LABEL_50:
    SetLastError_0(0x57u);
    return 0;
  }
  return (*(__int64 (__fastcall **)(__int64, _QWORD, PCNZWCH, _QWORD, PCNZWCH, int, _QWORD, _QWORD))(SortNode + 240))(
           SortNode,
           dwCmpFlags ^ 0x8000000,
           lpString1,
           v6,
           v82,
           cchCount2,
           0,
           0);
}

```

## disassembly

```asm
0x180027400  push    rbp
0x180027402  push    rbx
0x180027403  push    rsi
0x180027404  push    rdi
0x180027405  push    r12
0x180027407  push    r13
0x180027409  push    r14
0x18002740b  push    r15
0x18002740d  lea     rbp, [rsp-3E8h]
0x180027415  sub     rsp, 4E8h
0x18002741c  mov     rax, cs:__security_cookie
0x180027423  xor     rax, rsp
0x180027426  mov     [rbp+420h+var_50], rax
0x18002742d  mov     rax, [rbp+420h+lpString2]
0x180027434  mov     r14d, r9d
0x180027437  mov     [rbp+420h+var_488], rax
0x18002743b  mov     r13, r8
0x18002743e  mov     [rbp+420h+var_48C], r9d
0x180027442  mov     r12d, edx
0x180027445  mov     edi, ecx
0x180027447  mov     r15d, 1
0x18002744d  cmp     ecx, 7Fh
0x180027450  jz      loc_180027779
0x180027456  cmp     edi, 0C00h
0x18002745c  ja      loc_1800275AF
0x180027462  jz      loc_1800277F0
0x180027468  test    ecx, ecx
0x18002746a  jz      loc_1800277F0
0x180027470  cmp     edi, 400h
0x180027476  jz      loc_1800277F0
0x18002747c  cmp     edi, 800h
0x180027482  jnz     loc_1800275C7
0x180027488  mov     rax, cs:gpSysLocHashN
0x18002748f  test    rax, rax
0x180027492  jnz     loc_180027740
0x180027498  cmp     cs:BasepIsSecureProcess, al
0x18002749e  jnz     loc_1800276ED
0x1800274a4  lea     rcx, gTblPtrsLock
0x1800274ab  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800274b2  nop     dword ptr [rax+rax+00h]
0x1800274b7  cmp     cs:gpSysLocHashN, 0
0x1800274bf  jnz     loc_180027590
0x1800274c5  mov     ebx, cs:gSystemLocale
0x1800274cb  mov     rax, cs:P
0x1800274d2  mov     ecx, ebx
0x1800274d4  shr     rcx, 7
0x1800274d8  xor     rcx, rbx
0x1800274db  shr     rcx, 7
0x1800274df  xor     rcx, rbx
0x1800274e2  and     ecx, 7Fh
0x1800274e5  mov     rdx, [rax+rcx*8]
0x1800274e9  test    rdx, rdx
0x1800274ec  jz      short loc_1800274F6
0x1800274ee  cmp     [rdx], ebx
0x1800274f0  jnz     loc_180027F6B
0x1800274f6  mov     cs:gpSysLocHashN, rdx
0x1800274fd  test    rdx, rdx
0x180027500  jnz     loc_180027590
0x180027506  test    ebx, 0FFF00000h
0x18002750c  jnz     loc_180027C9C
0x180027512  cmp     cs:BasepIsSecureProcess, dl
0x180027518  jnz     loc_180027C9C
0x18002751e  mov     ecx, ebx
0x180027520  call    GetWindowsLocaleData
0x180027525  test    rax, rax
0x180027528  jz      loc_180027F7D
0x18002752e  cmp     bx, 7Fh
0x180027532  jz      loc_180027FBE
0x180027538  shr     ebx, 10h
0x18002753b  test    bl, 0Fh
0x18002753e  jnz     loc_180027C69
0x180027544  mov     ecx, [rax]
0x180027546  mov     rax, cs:qword_1803A6BD0
0x18002754d  add     rax, 2
0x180027551  lea     rcx, [rax+rcx*2]
0x180027555  xor     edx, edx
0x180027557  call    MakeNamedLocaleHashNode
0x18002755c  mov     cs:gpSysLocHashN, rax
0x180027563  test    rax, rax
0x180027566  jnz     short loc_180027590
0x180027568  xor     edx, edx
0x18002756a  lea     rcx, aEnUs; "en-US"
0x180027571  call    MakeNamedLocaleHashNode
0x180027576  mov     cs:gpSysLocHashN, rax
0x18002757d  test    rax, rax
0x180027580  jnz     short loc_180027590
0x180027582  mov     rax, cs:gpInvLocHashN
0x180027589  mov     cs:gpSysLocHashN, rax
0x180027590  lea     rcx, gTblPtrsLock
0x180027597  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002759e  nop     dword ptr [rax+rax+00h]
0x1800275a3  mov     rax, cs:gpSysLocHashN
0x1800275aa  jmp     loc_1800276ED
0x1800275af  cmp     edi, 1000h
0x1800275b5  jz      loc_180028079
0x1800275bb  cmp     edi, 1400h
0x1800275c1  jz      loc_180028089
0x1800275c7  mov     rax, cs:gpSysLocHashN
0x1800275ce  test    rax, rax
0x1800275d1  jnz     loc_1800276E9
0x1800275d7  cmp     cs:BasepIsSecureProcess, al
0x1800275dd  jnz     loc_1800276E9
0x1800275e3  lea     rcx, gTblPtrsLock
0x1800275ea  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800275f1  nop     dword ptr [rax+rax+00h]
0x1800275f6  cmp     cs:gpSysLocHashN, 0
0x1800275fe  jnz     loc_1800276CF
0x180027604  mov     ebx, cs:gSystemLocale
0x18002760a  mov     rax, cs:P
0x180027611  mov     ecx, ebx
0x180027613  shr     rcx, 7
0x180027617  xor     rcx, rbx
0x18002761a  shr     rcx, 7
0x18002761e  xor     rcx, rbx
0x180027621  and     ecx, 7Fh
0x180027624  mov     rdx, [rax+rcx*8]
0x180027628  test    rdx, rdx
0x18002762b  jz      short loc_180027635
0x18002762d  cmp     [rdx], ebx
0x18002762f  jnz     loc_180027B7F
0x180027635  mov     cs:gpSysLocHashN, rdx
0x18002763c  test    rdx, rdx
0x18002763f  jnz     loc_1800276CF
0x180027645  test    ebx, 0FFF00000h
0x18002764b  jnz     loc_180027B1B
0x180027651  cmp     cs:BasepIsSecureProcess, dl
0x180027657  jnz     loc_180027B1B
0x18002765d  mov     ecx, ebx
0x18002765f  call    GetWindowsLocaleData
0x180027664  test    rax, rax
0x180027667  jz      loc_180027C3B
0x18002766d  cmp     bx, 7Fh
0x180027671  jz      loc_180027D7C
0x180027677  shr     ebx, 10h
0x18002767a  test    bl, 0Fh
0x18002767d  jnz     loc_180027AE8
0x180027683  mov     ecx, [rax]
0x180027685  mov     rax, cs:qword_1803A6BD0
0x18002768c  add     rax, 2
0x180027690  lea     rcx, [rax+rcx*2]
0x180027694  xor     edx, edx
0x180027696  call    MakeNamedLocaleHashNode
0x18002769b  mov     cs:gpSysLocHashN, rax
0x1800276a2  test    rax, rax
0x1800276a5  jnz     short loc_1800276CF
0x1800276a7  xor     edx, edx
0x1800276a9  lea     rcx, aEnUs; "en-US"
0x1800276b0  call    MakeNamedLocaleHashNode
0x1800276b5  mov     cs:gpSysLocHashN, rax
0x1800276bc  test    rax, rax
0x1800276bf  jnz     short loc_1800276CF
0x1800276c1  mov     rax, cs:gpInvLocHashN
0x1800276c8  mov     cs:gpSysLocHashN, rax
0x1800276cf  lea     rcx, gTblPtrsLock
0x1800276d6  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800276dd  nop     dword ptr [rax+rax+00h]
0x1800276e2  mov     rax, cs:gpSysLocHashN
0x1800276e9  cmp     edi, [rax]
0x1800276eb  jnz     short loc_1800276F2
0x1800276ed  test    rax, rax
0x1800276f0  jnz     short loc_180027740
0x1800276f2  mov     rax, cs:P
0x1800276f9  mov     rcx, rdi
0x1800276fc  shr     rcx, 7
0x180027700  xor     rcx, rdi
0x180027703  shr     rcx, 7
0x180027707  xor     rcx, rdi
0x18002770a  and     ecx, 7Fh
0x18002770d  mov     rbx, [rax+rcx*8]
0x180027711  lea     rsi, ds:0[rcx*8]
0x180027719  test    rbx, rbx
0x18002771c  jz      loc_180027B38
0x180027722  cmp     [rbx], edi
0x180027724  jnz     loc_180027B2B
0x18002772a  test    rbx, rbx
0x18002772d  jz      loc_180027D44
0x180027733  mov     rax, [rbx+68h]
0x180027737  test    rax, rax
0x18002773a  jz      loc_180027D46
0x180027740  mov     rbx, [rax+20h]
0x180027744  test    rbx, rbx
0x180027747  jnz     short loc_180027785
0x180027749  mov     ecx, 57h ; 'W'; dwErrCode
0x18002774e  call    SetLastError_0
0x180027753  xor     eax, eax
0x180027755  mov     rcx, [rbp+420h+var_50]
0x18002775c  xor     rcx, rsp; StackCookie
0x18002775f  call    __security_check_cookie
0x180027764  add     rsp, 4E8h
0x18002776b  pop     r15
0x18002776d  pop     r14
0x18002776f  pop     r13
0x180027771  pop     r12
0x180027773  pop     rdi
0x180027774  pop     rsi
0x180027775  pop     rbx
0x180027776  pop     rbp
0x180027777  retn
0x180027779  mov     rax, cs:gpInvLocHashN
0x180027780  jmp     loc_1800276ED
0x180027785  cmp     cs:g_definedDefaultSortVersion, 0
0x18002778c  jz      loc_180027CAC
0x180027792  xor     r8d, r8d
0x180027795  lea     rdx, g_defaultSortVersion
0x18002779c  mov     rcx, rbx
0x18002779f  call    GetSortNode
0x1800277a4  test    rax, rax
0x1800277a7  jz      short loc_180027749
0x1800277a9  mov     ecx, [rbp+420h+cchCount2]
0x1800277af  btc     r12d, 1Bh
0x1800277b4  mov     [rsp+520h+var_4E8], 0
0x1800277bd  mov     r9d, r14d
0x1800277c0  mov     [rsp+520h+Disposition], 0
0x1800277c9  mov     r8, r13
0x1800277cc  mov     [rsp+520h+CreateOptions], ecx
0x1800277d0  mov     edx, r12d
0x1800277d3  mov     rcx, [rbp+420h+var_488]
0x1800277d7  mov     [rsp+520h+Class], rcx
0x1800277dc  mov     rcx, rax
0x1800277df  mov     rax, [rax+0F0h]
0x1800277e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800277eb  jmp     loc_180027755
0x1800277f0  mov     rax, gs:30h
0x1800277f9  mov     ecx, [rax+179Ch]
0x1800277ff  test    ecx, ecx
0x180027801  jnz     loc_180027EDE
0x180027807  mov     eax, cs:gInteractiveLogonUserProcess
0x18002780d  cmp     eax, 0FFFFFFFFh
0x180027810  jz      loc_180028006
0x180027816  test    eax, eax
0x180027818  jz      loc_180027ED4
0x18002781e  mov     rax, cs:gpServerNlsUserInfo
0x180027825  mov     ecx, [rax+678h]
0x18002782b  mov     eax, cs:dword_1803AC290
0x180027831  cmp     eax, ecx
0x180027833  jz      short loc_18002783D
0x180027835  mov     cs:word_1803AC296, r15w
0x18002783d  movzx   eax, cs:word_1803AC296
0x180027844  test    ax, ax
0x180027847  jz      loc_180027AD4
0x18002784d  movzx   eax, cs:word_1803AC294
0x180027854  cmp     ax, 3
0x180027858  jz      short loc_18002787E
0x18002785a  lea     rcx, gNlsProcessCacheLock
0x180027861  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180027868  nop     dword ptr [rax+rax+00h]
0x18002786d  movzx   eax, cs:word_1803AC294
0x180027874  cmp     ax, 3
0x180027878  jnz     loc_180027C0F
0x18002787e  mov     r14d, 2
0x180027884  mov     cs:word_1803AC296, r14w
0x18002788c  cmp     ax, r15w
0x180027890  jnz     short loc_1800278D6
0x180027892  xor     edx, edx; Val
0x180027894  lea     rcx, [rbp+420h+ApiMessage]; void *
0x180027898  mov     r8d, 3B8h; Size
0x18002789e  call    memset_0
0x1800278a3  mov     edx, 67Ch; BufferSize
0x1800278a8  mov     ecx, r15d; ArgumentCount
0x1800278ab  call    cs:__imp_CsrAllocateCaptureBuffer
0x1800278b2  nop     dword ptr [rax+rax+00h]
0x1800278b7  mov     rbx, rax
0x1800278ba  test    rax, rax
0x1800278bd  jnz     loc_180027B91
0x1800278c3  mov     esi, 0C0000017h
0x1800278c8  cmp     cs:word_1803AC294, r15w
0x1800278d0  jz      loc_180027C02
0x1800278d6  mov     rax, cs:gNlsProcessLocalCache
0x1800278dd  mov     [rsp+520h+Handle], 0
0x1800278e6  test    rax, rax
0x1800278e9  jz      loc_180027D8E
0x1800278ef  mov     rax, cs:gNlsProcessLocalCache
0x1800278f6  mov     [rsp+520h+Handle], rax
0x1800278fb  mov     rbx, [rsp+520h+Handle]
0x180027900  lea     rcx, word_1803ABC18
0x180027907  mov     rdx, rbx
0x18002790a  mov     r8d, r15d
0x18002790d  call    NlsUpdateCacheInfo
0x180027912  cmp     cs:word_1803AC294, 3
0x18002791a  jnz     short loc_180027930
0x18002791c  test    rbx, rbx
0x18002791f  jz      short loc_180027930
0x180027921  mov     rcx, rbx; Handle
0x180027924  call    cs:__imp_NtClose
0x18002792b  nop     dword ptr [rax+rax+00h]
0x180027930  mov     eax, 0FFFFh
0x180027935  cmp     cs:word_1803ABC18, ax
0x18002793c  jz      loc_180027C2B
0x180027942  mov     rbx, cs:gpOneCustomHashNode
0x180027949  lea     rcx, word_1803ABC1A
0x180027950  xor     edx, edx
0x180027952  call    GetNamedLocaleHashNode
0x180027957  xchg    rax, cs:qword_1803ABC10
0x18002795e  test    rbx, rbx
0x180027961  jnz     short loc_180027973
0x180027963  cmp     cs:gpOneCustomHashNode, rbx
0x18002796a  jz      short loc_180027973
0x18002796c  mov     cs:gpOneCustomHashNode, rbx
0x180027973  cmp     cs:qword_1803ABC10, 0
0x18002797b  jnz     loc_180027AA9
  ... truncated ...
```
