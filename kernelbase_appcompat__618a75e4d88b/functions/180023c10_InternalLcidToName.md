# InternalLcidToName

- ea: `0x180023c10`
- end: `0x180024c78`
- name: `InternalLcidToName`
- size: `4200`
- prototype: ``
- caller_count: `9`
- callee_count: `19`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180021b10`
- `0x180021ee0`
- `0x1800225d0`
- `0x180034120`
- `0x1800418a0`
- `0x180078a90`
- `0x180096e80`
- `0x180097030`
- `0x1800cb650`

## callees

- `0x18001cd34`
- `0x180023c10`
- `0x180024c80`
- `0x1800265f0`
- `0x180028360`
- `0x180028490`
- `0x1800285f0`
- `0x180029ec0`
- `0x18002aabc`
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

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180024955`
- `ntdll!RtlInitUnicodeString` at `0x180024955`
- `ntdll!RtlEqualSid` at `0x180024ba5`
- `ntdll!RtlEqualSid` at `0x180024ba5`
- `ntdll!NtOpenKey` at `0x1800249a1`
- `ntdll!NtOpenKey` at `0x1800249a1`
- `ntdll!NtCreateKey` at `0x1800249e0`
- `ntdll!NtCreateKey` at `0x1800249e0`
- `ntdll!RtlLcidToLocaleName` at `0x180024816`
- `ntdll!RtlLcidToLocaleName` at `0x180024816`
- `ntdll!RtlOpenCurrentUser` at `0x1800244d5`
- `ntdll!RtlOpenCurrentUser` at `0x1800244d5`
- `ntdll!NtQueryInformationToken` at `0x180024ae3`
- `ntdll!NtQueryInformationToken` at `0x180024b84`
- `ntdll!NtQueryInformationToken` at `0x180024ae3`
- `ntdll!NtQueryInformationToken` at `0x180024b84`
- `ntdll!CsrClientCallServer` at `0x180024360`
- `ntdll!CsrClientCallServer` at `0x180024360`
- `ntdll!CsrCaptureMessageBuffer` at `0x18002433a`
- `ntdll!CsrCaptureMessageBuffer` at `0x18002433a`
- `ntdll!CsrFreeCaptureBuffer` at `0x18002438b`
- `ntdll!CsrFreeCaptureBuffer` at `0x18002438b`
- `ntdll!CsrAllocateCaptureBuffer` at `0x180023f13`
- `ntdll!CsrAllocateCaptureBuffer` at `0x180023f13`
- `ntdll!NtClose` at `0x180023f8c`
- `ntdll!NtClose` at `0x180024577`
- `ntdll!NtClose` at `0x1800249f8`
- `ntdll!NtClose` at `0x180024a39`
- `ntdll!NtClose` at `0x180023f8c`
- `ntdll!NtClose` at `0x180024577`
- `ntdll!NtClose` at `0x1800249f8`
- `ntdll!NtClose` at `0x180024a39`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180023c9a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180023ec9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002400c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002417f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800242d9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180023c9a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180023ec9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002400c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002417f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800242d9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180023d85`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800240f7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180024130`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002426a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180024308`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180023d85`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800240f7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180024130`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002426a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180024308`
- `ntdll!RtlFreeHeap` at `0x180024bc9`
- `ntdll!RtlFreeHeap` at `0x180024bc9`
- `ntdll!RtlAllocateHeap` at `0x180024896`
- `ntdll!RtlAllocateHeap` at `0x1800248f7`
- `ntdll!RtlAllocateHeap` at `0x180024b4f`
- `ntdll!RtlAllocateHeap` at `0x180024896`
- `ntdll!RtlAllocateHeap` at `0x1800248f7`
- `ntdll!RtlAllocateHeap` at `0x180024b4f`

## pseudocode

```c
__int64 __fastcall InternalLcidToName(unsigned int a1, int a2)
{
  unsigned __int64 v2; // rdi
  _QWORD *v4; // rbx
  DWORD v5; // ebx
  __int64 k; // rdx
  unsigned int *v7; // rax
  __int64 v8; // r8
  DWORD v9; // ebx
  _WORD *v10; // rcx
  __int64 LocaleHashNode; // rax
  __int64 v12; // rsi
  ULONG IsImpersonating; // ecx
  int v15; // ebx
  __int16 v16; // ax
  struct _CSR_CAPTURE_BUFFER *CaptureBuffer; // rax
  struct _CSR_CAPTURE_BUFFER *v18; // rbx
  NTSTATUS v19; // esi
  HANDLE v20; // rbx
  __int64 v21; // rbx
  __int64 v22; // rax
  DWORD v23; // ebx
  __int64 j; // rdx
  unsigned int *v25; // rax
  __int64 v26; // r8
  DWORD v27; // ebx
  _WORD *v28; // rcx
  __int64 LocHashNodeFromSystemLocale; // rax
  HANDLE *NlsCache; // rbx
  DWORD v31; // ebx
  __int64 i; // rdx
  unsigned int *WindowsLocaleData; // rax
  __int64 v34; // r8
  DWORD v35; // ebx
  _WORD *v36; // rcx
  __int64 NamedLocaleHashNode; // rax
  __int64 v38; // rdx
  __int64 v39; // rdx
  int GlobalizationUserModelType; // eax
  int v41; // eax
  __int64 v42; // rcx
  WCHAR *v43; // rax
  __int64 v44; // r9
  const WCHAR *v45; // rdx
  WCHAR *v46; // r8
  __int64 v47; // rcx
  WCHAR *v48; // rcx
  __int64 v49; // rdx
  ULONG v50; // ecx
  int v51; // r15d
  int v52; // eax
  HANDLE *v53; // rax
  HANDLE *Heap; // rax
  NTSTATUS v55; // ebx
  HANDLE v56; // rcx
  void *v57; // rbx
  unsigned int *v58; // rcx
  __int64 v59; // r8
  _WORD *v60; // rcx
  __int64 v61; // rax
  PSID *v62; // rsi
  __int64 v63; // rax
  ULONG ReturnLength; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE KeyHandle[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v67; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-88h] BYREF
  __int64 v70; // [rsp+A8h] [rbp-58h]
  WCHAR ApiMessage[32]; // [rsp+B0h] [rbp-50h] BYREF
  PVOID CapturedData; // [rsp+F0h] [rbp-10h] BYREF
  int v73; // [rsp+F8h] [rbp-8h]

  v2 = a1;
  if ( a1 == 127 )
  {
    v4 = (_QWORD *)gpInvLocHashN;
    goto LABEL_25;
  }
  if ( a1 <= 0xC00 )
  {
    if ( a1 != 3072 && a1 && a1 != 1024 )
    {
      if ( a1 != 2048 )
        goto LABEL_7;
      v4 = (_QWORD *)gpSysLocHashN;
      if ( gpSysLocHashN )
        return v4[4];
      if ( BasepIsSecureProcess )
        goto LABEL_25;
      RtlAcquireSRWLockExclusive(&gTblPtrsLock);
      if ( gpSysLocHashN )
        goto LABEL_96;
      v31 = gSystemLocale;
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
        goto LABEL_96;
      if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
        goto LABEL_124;
      WindowsLocaleData = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
      if ( WindowsLocaleData )
      {
        if ( (_WORD)v31 != 127 )
        {
          v35 = HIWORD(v31);
          if ( (v35 & 0xF) == 0 )
          {
            v36 = (_WORD *)(qword_1803A6BD0 + 2 + 2LL * *WindowsLocaleData);
LABEL_92:
            NamedLocaleHashNode = MakeNamedLocaleHashNode(v36, 0);
            goto LABEL_93;
          }
          v39 = WindowsLocaleData[54];
          v36 = (_WORD *)qword_1803A6BD0;
          if ( (_DWORD)v39 )
            v36 = (_WORD *)(qword_1803A6BD0
                          + 2LL * *(unsigned int *)(qword_1803A6BD0 + 2 * (v39 + 2LL * (v35 & 0xF)) - 2)
                          + 2);
          if ( v36 && *v36 )
            goto LABEL_92;
LABEL_124:
          gpSysLocHashN = 0;
LABEL_94:
          gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
          if ( !gpSysLocHashN )
            gpSysLocHashN = gpInvLocHashN;
          goto LABEL_96;
        }
        NamedLocaleHashNode = MakeLocHashNodeFromSystemLocale(WindowsLocaleData, v31, v34, 0);
      }
      else
      {
        if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
          goto LABEL_124;
        if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
          || (unsigned int)CreateTransientLocales() )
        {
          NamedLocaleHashNode = FindLocaleHashNode(v31);
        }
        else
        {
          NamedLocaleHashNode = 0;
        }
      }
LABEL_93:
      gpSysLocHashN = NamedLocaleHashNode;
      if ( !NamedLocaleHashNode )
        goto LABEL_94;
LABEL_96:
      RtlReleaseSRWLockExclusive(&gTblPtrsLock);
      v4 = (_QWORD *)gpSysLocHashN;
      goto LABEL_25;
    }
    IsImpersonating = NtCurrentTeb()->IsImpersonating;
    if ( IsImpersonating )
    {
      NlsCache = 0;
      v50 = IsImpersonating - 1;
      if ( !v50 )
      {
        if ( BasepIsSecureProcess )
        {
          NlsCache = &gNlsProcessLocalCache;
        }
        else
        {
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
              *((_WORD *)Heap + 842) = 3;
              *((_WORD *)Heap + 843) = 1;
            }
            else
            {
              NlsCache = &gNlsProcessLocalCache;
            }
            NtCurrentTeb()->NlsCache = NlsCache;
          }
          if ( NlsCache != &gNlsProcessLocalCache )
          {
            *((_WORD *)NlsCache + 843) = 1;
            UpdateNlsInfoCache(NlsCache, 0);
          }
        }
        NtCurrentTeb()->IsImpersonating = 2;
        goto LABEL_79;
      }
      if ( v50 != 1 )
      {
LABEL_79:
        v4 = NlsCache[2];
        goto LABEL_25;
      }
      if ( !BasepIsSecureProcess )
      {
        v51 = 0;
        NlsCache = (HANDLE *)NtCurrentTeb()->NlsCache;
        if ( !NlsCache )
        {
          v53 = (HANDLE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x698u);
          NlsCache = v53;
          if ( v53 )
          {
            *v53 = 0;
            v53[1] = 0;
            v53[2] = 0;
            v51 = 1;
            *((_WORD *)v53 + 842) = 3;
            *((_WORD *)v53 + 843) = 1;
          }
          else
          {
            NlsCache = &gNlsProcessLocalCache;
          }
          NtCurrentTeb()->NlsCache = NlsCache;
        }
        if ( NlsCache != &gNlsProcessLocalCache && (v51 || *((_WORD *)NlsCache + 843) == 1) )
        {
          *((_WORD *)NlsCache + 843) = 1;
          UpdateNlsInfoCache(NlsCache, 0);
        }
        goto LABEL_79;
      }
      goto LABEL_78;
    }
    v15 = gInteractiveLogonUserProcess;
    if ( gInteractiveLogonUserProcess == -1 )
    {
      v15 = 0;
      v70 = 0;
      memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
      ReturnLength = 0;
      if ( !BasepIsSecureProcess
        && NtQueryInformationToken(
             (HANDLE)0xFFFFFFFFFFFFFFFCLL,
             TokenStatistics,
             &ObjectAttributes,
             0x38u,
             &ReturnLength) >= 0 )
      {
        if ( *(HANDLE *)(gpServerNlsUserInfo + 1580) == ObjectAttributes.RootDirectory )
        {
          v15 = 1;
          gInteractiveLogonUserProcess = 1;
          word_1803AC294 = 1;
          goto LABEL_38;
        }
        v62 = (PSID *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x54u);
        if ( v62 )
        {
          if ( NtQueryInformationToken((HANDLE)0xFFFFFFFFFFFFFFFCLL, TokenUser, v62, 0x54u, &ReturnLength) >= 0 )
            v15 = RtlEqualSid(*v62, (PSID)(gpServerNlsUserInfo + 1588)) != 0;
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v62);
        }
      }
      gInteractiveLogonUserProcess = v15;
      if ( v15 )
        word_1803AC294 = 1;
      else
        word_1803AC294 = 20;
    }
LABEL_38:
    if ( !v15 )
    {
      NlsCheckStaleCache();
      goto LABEL_78;
    }
    if ( dword_1803AC290 != *(_DWORD *)(gpServerNlsUserInfo + 1656) )
      word_1803AC296 = 1;
    if ( !word_1803AC296 )
      goto LABEL_78;
    v16 = word_1803AC294;
    if ( word_1803AC294 != 3 )
    {
      RtlAcquireSRWLockExclusive(&gNlsProcessCacheLock);
      v16 = word_1803AC294;
      if ( word_1803AC294 != 3 )
      {
        if ( !word_1803AC296 )
          goto LABEL_77;
        v16 = word_1803AC294;
      }
    }
    word_1803AC296 = 2;
    if ( v16 == 1 )
    {
      memset_0(ApiMessage, 0, 0x3B8u);
      CaptureBuffer = CsrAllocateCaptureBuffer(1u, 0x67Cu);
      v18 = CaptureBuffer;
      if ( CaptureBuffer )
      {
        CsrCaptureMessageBuffer(CaptureBuffer, 0, 0x67Cu, &CapturedData);
        v73 = 1660;
        v19 = CsrClientCallServer(ApiMessage, v18, (CSR_API_NUMBER)0x1001B, 0x10u);
        if ( v19 >= 0 )
          memcpy_0(&word_1803ABC18, CapturedData, 0x67Cu);
        CsrFreeCaptureBuffer(v18);
      }
      else
      {
        v19 = -1073741801;
      }
      if ( word_1803AC294 == 1 && v19 >= 0 )
      {
LABEL_53:
        if ( word_1803ABC18 == -1 )
        {
          qword_1803ABC10 = 0;
        }
        else
        {
          v21 = gpOneCustomHashNode;
          _InterlockedExchange64(&qword_1803ABC10, GetNamedLocaleHashNode(word_1803ABC1A, 0));
          if ( !v21 && gpOneCustomHashNode )
            gpOneCustomHashNode = 0;
          if ( qword_1803ABC10 )
          {
LABEL_76:
            _InterlockedCompareExchange16(&word_1803AC296, 0, 2);
            if ( word_1803AC294 != 3 )
LABEL_77:
              RtlReleaseSRWLockExclusive(&gNlsProcessCacheLock);
LABEL_78:
            NlsCache = &gNlsProcessLocalCache;
            goto LABEL_79;
          }
        }
        v22 = gpSysLocHashN;
        if ( gpSysLocHashN || BasepIsSecureProcess )
        {
LABEL_75:
          qword_1803ABC10 = v22;
          goto LABEL_76;
        }
        RtlAcquireSRWLockExclusive(&gTblPtrsLock);
        if ( gpSysLocHashN )
          goto LABEL_74;
        v23 = gSystemLocale;
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
          goto LABEL_74;
        if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
          goto LABEL_152;
        v25 = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
        if ( v25 )
        {
          if ( (_WORD)v23 != 127 )
          {
            v27 = HIWORD(v23);
            if ( (v27 & 0xF) == 0 )
            {
              v28 = (_WORD *)(qword_1803A6BD0 + 2 + 2LL * *v25);
LABEL_70:
              LocHashNodeFromSystemLocale = MakeNamedLocaleHashNode(v28, 0);
              goto LABEL_71;
            }
            v49 = v25[54];
            v28 = (_WORD *)qword_1803A6BD0;
            if ( (_DWORD)v49 )
              v28 = (_WORD *)(qword_1803A6BD0
                            + 2LL * *(unsigned int *)(qword_1803A6BD0 + 2 * (v49 + 2LL * (v27 & 0xF)) - 2)
                            + 2);
            if ( v28 && *v28 )
              goto LABEL_70;
LABEL_152:
            gpSysLocHashN = 0;
LABEL_72:
            gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
            if ( !gpSysLocHashN )
              gpSysLocHashN = gpInvLocHashN;
            goto LABEL_74;
          }
          LocHashNodeFromSystemLocale = MakeLocHashNodeFromSystemLocale(v25, v23, v26, 0);
        }
        else
        {
          if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
            goto LABEL_152;
          if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
            || (unsigned int)CreateTransientLocales() )
          {
            LocHashNodeFromSystemLocale = FindLocaleHashNode(v23);
          }
          else
          {
            LocHashNodeFromSystemLocale = 0;
          }
        }
LABEL_71:
        gpSysLocHashN = LocHashNodeFromSystemLocale;
        if ( !LocHashNodeFromSystemLocale )
          goto LABEL_72;
LABEL_74:
        RtlReleaseSRWLockExclusive(&gTblPtrsLock);
        v22 = gpSysLocHashN;
        goto LABEL_75;
      }
    }
    Handle = 0;
    if ( gNlsProcessLocalCache )
    {
      Handle = gNlsProcessLocalCache;
LABEL_50:
      v20 = Handle;
      NlsUpdateCacheInfo(&word_1803ABC18, Handle, 1);
      if ( word_1803AC294 == 3 && v20 )
        NtClose(v20);
      goto LABEL_53;
    }
    KeyHandle[0] = 0;
    ReturnLength = 0;
    memset(&ObjectAttributes, 0, 44);
    DestinationString = 0;
    GlobalizationUserModelType = GetGlobalizationUserModelType();
    if ( GlobalizationUserModelType == 1 )
    {
      v41 = RtlOpenCurrentUser(0x2000000u, KeyHandle);
    }
    else
    {
      v52 = GlobalizationUserModelType - 2;
      if ( v52 )
      {
        if ( v52 != 1 )
        {
LABEL_147:
          SetLastError_0(0x3F1u);
          goto LABEL_50;
        }
        v67 = 0;
        v41 = OpenGlobalizationUserSettingsKey_ForMua(0x2000000u, 0, KeyHandle, &v67);
      }
      else
      {
        v41 = OpenGlobalizationUserSettingsKey_ForSingleUserModel(0x2000000u, KeyHandle);
      }
    }
    if ( v41 >= 0 )
    {
      ApiMessage[0] = 0;
      v42 = 512;
      v43 = ApiMessage;
      do
      {
        if ( !*v43 )
          break;
        ++v43;
        --v42;
      }
      while ( v42 );
      if ( !v42 )
        goto LABEL_145;
      v44 = v42;
      v45 = L"Control Panel\\International";
      v46 = &ApiMessage[512 - v42];
      v47 = 2147483646;
      do
      {
        if ( !v47 )
          break;
        if ( !*v45 )
          break;
        *v46++ = *v45++;
        --v47;
        --v44;
      }
      while ( v44 );
      v48 = v46 - 1;
      if ( v44 )
        v48 = v46;
      *v48 = 0;
      if ( v44 )
      {
        RtlInitUnicodeString(&DestinationString, ApiMessage);
        ObjectAttributes.RootDirectory = KeyHandle[0];
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        ReturnLength = 0;
        v55 = NtOpenKey(&Handle, 0x20019u, &ObjectAttributes);
        if ( v55 < 0 )
          v55 = NtCreateKey(&Handle, 0x20019u, &ObjectAttributes, 0, 0, 0, &ReturnLength);
        if ( KeyHandle[0] )
          NtClose(KeyHandle[0]);
        if ( v55 >= 0 )
        {
          v56 = Handle;
        }
        else
        {
          v56 = 0;
          Handle = 0;
        }
        if ( v55 >= 0 )
        {
          v57 = (void *)_InterlockedCompareExchange64(
                          (volatile signed __int64 *)&gNlsProcessLocalCache,
                          (signed __int64)v56,
                          0);
          if ( v57 )
          {
            if ( Handle )
              NtClose(Handle);
            Handle = v57;
          }
          goto LABEL_50;
        }
      }
      else
      {
LABEL_145:
        if ( KeyHandle[0] )
          NtClose(KeyHandle[0]);
      }
    }
    goto LABEL_147;
  }
  if ( a1 == 4096 )
  {
    v4 = (_QWORD *)gpOneCustomHashNode;
    if ( gpOneCustomHashNode )
      return v4[4];
  }
  else if ( a1 != 5120 )
  {
    goto LABEL_7;
  }
  KeyHandle[0] = (HANDLE)11141120;
  KeyHandle[1] = ApiMessage;
  if ( (int)RtlLcidToLocaleName(a1, KeyHandle, 0, 0) >= 0 )
  {
    v4 = (_QWORD *)GetNamedLocaleHashNode(KeyHandle[1], 0);
    if ( v4 )
      return v4[4];
  }
LABEL_7:
  v4 = (_QWORD *)gpSysLocHashN;
  if ( !gpSysLocHashN && !BasepIsSecureProcess )
  {
    RtlAcquireSRWLockExclusive(&gTblPtrsLock);
    if ( gpSysLocHashN )
      goto LABEL_23;
    v5 = gSystemLocale;
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
      goto LABEL_23;
    if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
      goto LABEL_101;
    v7 = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
    if ( v7 )
    {
      if ( (_WORD)v5 != 127 )
      {
        v9 = HIWORD(v5);
        if ( (v9 & 0xF) == 0 )
        {
          v10 = (_WORD *)(qword_1803A6BD0 + 2 + 2LL * *v7);
LABEL_19:
          LocaleHashNode = MakeNamedLocaleHashNode(v10, 0);
          goto LABEL_20;
        }
        v38 = v7[54];
        v10 = (_WORD *)qword_1803A6BD0;
        if ( (_DWORD)v38 )
          v10 = (_WORD *)(qword_1803A6BD0
                        + 2LL * *(unsigned int *)(qword_1803A6BD0 + 2 * (v38 + 2LL * (v9 & 0xF)) - 2)
                        + 2);
        if ( v10 && *v10 )
          goto LABEL_19;
LABEL_101:
        gpSysLocHashN = 0;
        goto LABEL_21;
      }
      LocaleHashNode = MakeLocHashNodeFromSystemLocale(v7, v5, v8, 0);
    }
    else
    {
      if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
        goto LABEL_101;
      if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
        || (unsigned int)CreateTransientLocales() )
      {
        LocaleHashNode = FindLocaleHashNode(v5);
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
      v4 = (_QWORD *)gpSysLocHashN;
      goto LABEL_24;
    }
LABEL_21:
    gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
    if ( !gpSysLocHashN )
      gpSysLocHashN = gpInvLocHashN;
    goto LABEL_23;
  }
LABEL_24:
  if ( (_DWORD)v2 != *(_DWORD *)v4 )
    goto LABEL_26;
LABEL_25:
  if ( v4 )
    return v4[4];
LABEL_26:
  v12 = 8LL * (((unsigned __int8)v2 ^ (unsigned __int8)((v2 ^ (v2 >> 7)) >> 7)) & 0x7F);
  v4 = *(_QWORD **)((char *)P + v12);
  if ( !v4 )
  {
LABEL_103:
    RtlAcquireSRWLockExclusive(&gTblPtrsLock);
    v4 = *(_QWORD **)((char *)P + v12);
    if ( v4 )
    {
      while ( *(_DWORD *)v4 != (_DWORD)v2 )
      {
        v4 = (_QWORD *)v4[11];
        if ( !v4 )
          goto LABEL_214;
      }
      goto LABEL_105;
    }
LABEL_214:
    if ( (v2 & 0xFFF00000) == 0 && !BasepIsSecureProcess )
    {
      v58 = (unsigned int *)GetWindowsLocaleData((unsigned int)v2);
      if ( v58 )
      {
        if ( (_WORD)v2 == 127 )
        {
          v4 = (_QWORD *)MakeLocHashNodeFromSystemLocale(v58, (unsigned int)v2, v59, 0);
          goto LABEL_105;
        }
        if ( (v2 & 0xF0000) == 0 )
        {
          v60 = (_WORD *)(qword_1803A6BD0 + 2 + 2LL * *v58);
LABEL_220:
          v61 = MakeNamedLocaleHashNode(v60, 0);
LABEL_221:
          v4 = (_QWORD *)v61;
LABEL_105:
          RtlReleaseSRWLockExclusive(&gTblPtrsLock);
          goto LABEL_28;
        }
        v63 = v58[54];
        v60 = (_WORD *)qword_1803A6BD0;
        if ( (_DWORD)v63 )
          v60 = (_WORD *)(qword_1803A6BD0
                        + 2LL * *(unsigned int *)(qword_1803A6BD0 + 2 * (v63 + 2LL * (BYTE2(v2) & 0xF)) - 2)
                        + 2);
        if ( v60 && *v60 )
          goto LABEL_220;
      }
      else if ( !(unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
             && ((unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
              || (unsigned int)CreateTransientLocales()) )
      {
        v61 = FindLocaleHashNode((unsigned int)v2);
        goto LABEL_221;
      }
    }
    v4 = 0;
    goto LABEL_105;
  }
  while ( *(_DWORD *)v4 != (_DWORD)v2 )
  {
    v4 = (_QWORD *)v4[11];
    if ( !v4 )
      goto LABEL_103;
  }
LABEL_28:
  if ( v4 )
  {
    if ( a2 )
      return v4[4];
    v4 = (_QWORD *)v4[13];
    if ( v4 )
      return v4[4];
  }
  if ( (_DWORD)v2 == 4096 || (v2 & 0x3FF) == 0 && (unsigned int)(v2 - 0x2000) <= 0x2C00 )
    v4 = GetCurrentNlsCache()[2];
  if ( v4 )
    return v4[4];
  return 0;
}

```

## disassembly

```asm
0x180023c10  push    rbp
0x180023c12  push    rbx
0x180023c13  push    rsi
0x180023c14  push    rdi
0x180023c15  push    r12
0x180023c17  lea     rbp, [rsp-3C0h]
0x180023c1f  sub     rsp, 4C0h
0x180023c26  mov     rax, cs:__security_cookie
0x180023c2d  xor     rax, rsp
0x180023c30  mov     [rbp+3E0h+var_30], rax
0x180023c37  mov     edi, ecx
0x180023c39  mov     r12d, edx
0x180023c3c  cmp     ecx, 7Fh
0x180023c3f  jz      loc_180023E19
0x180023c45  cmp     edi, 0C00h
0x180023c4b  ja      loc_180023E25
0x180023c51  jz      loc_180023E42
0x180023c57  test    ecx, ecx
0x180023c59  jz      loc_180023E42
0x180023c5f  cmp     edi, 400h
0x180023c65  jz      loc_180023E42
0x180023c6b  cmp     edi, 800h
0x180023c71  jz      loc_18002415C
0x180023c77  mov     rbx, cs:gpSysLocHashN
0x180023c7e  test    rbx, rbx
0x180023c81  jnz     loc_180023D98
0x180023c87  cmp     cs:BasepIsSecureProcess, bl
0x180023c8d  jnz     loc_180023D98
0x180023c93  lea     rcx, gTblPtrsLock
0x180023c9a  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180023ca1  nop     dword ptr [rax+rax+00h]
0x180023ca6  cmp     cs:gpSysLocHashN, rbx
0x180023cad  jnz     loc_180023D7E
0x180023cb3  mov     ebx, cs:gSystemLocale
0x180023cb9  mov     rax, cs:P
0x180023cc0  mov     ecx, ebx
0x180023cc2  shr     rcx, 7
0x180023cc6  xor     rcx, rbx
0x180023cc9  shr     rcx, 7
0x180023ccd  xor     rcx, rbx
0x180023cd0  and     ecx, 7Fh
0x180023cd3  mov     rdx, [rax+rcx*8]
0x180023cd7  test    rdx, rdx
0x180023cda  jz      short loc_180023CE4
0x180023cdc  cmp     [rdx], ebx
0x180023cde  jnz     loc_180024319
0x180023ce4  mov     cs:gpSysLocHashN, rdx
0x180023ceb  test    rdx, rdx
0x180023cee  jnz     loc_180023D7E
0x180023cf4  test    ebx, 0FFF00000h
0x180023cfa  jnz     loc_1800242B5
0x180023d00  cmp     cs:BasepIsSecureProcess, dl
0x180023d06  jnz     loc_1800242B5
0x180023d0c  mov     ecx, ebx
0x180023d0e  call    GetWindowsLocaleData
0x180023d13  test    rax, rax
0x180023d16  jz      loc_1800243D5
0x180023d1c  cmp     bx, 7Fh
0x180023d20  jz      loc_18002447D
0x180023d26  shr     ebx, 10h
0x180023d29  test    bl, 0Fh
0x180023d2c  jnz     loc_180024282
0x180023d32  mov     ecx, [rax]
0x180023d34  mov     rax, cs:qword_1803A6BD0
0x180023d3b  add     rax, 2
0x180023d3f  lea     rcx, [rax+rcx*2]
0x180023d43  xor     edx, edx
0x180023d45  call    MakeNamedLocaleHashNode
0x180023d4a  mov     cs:gpSysLocHashN, rax
0x180023d51  test    rax, rax
0x180023d54  jnz     short loc_180023D7E
0x180023d56  xor     edx, edx
0x180023d58  lea     rcx, aEnUs; "en-US"
0x180023d5f  call    MakeNamedLocaleHashNode
0x180023d64  mov     cs:gpSysLocHashN, rax
0x180023d6b  test    rax, rax
0x180023d6e  jnz     short loc_180023D7E
0x180023d70  mov     rax, cs:gpInvLocHashN
0x180023d77  mov     cs:gpSysLocHashN, rax
0x180023d7e  lea     rcx, gTblPtrsLock
0x180023d85  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180023d8c  nop     dword ptr [rax+rax+00h]
0x180023d91  mov     rbx, cs:gpSysLocHashN
0x180023d98  cmp     edi, [rbx]
0x180023d9a  jnz     short loc_180023DA1
0x180023d9c  test    rbx, rbx
0x180023d9f  jnz     short loc_180023DF7
0x180023da1  mov     rbx, cs:P
0x180023da8  mov     rcx, rdi
0x180023dab  shr     rcx, 7
0x180023daf  xor     rcx, rdi
0x180023db2  shr     rcx, 7
0x180023db6  xor     rcx, rdi
0x180023db9  and     ecx, 7Fh
0x180023dbc  lea     rsi, ds:0[rcx*8]
0x180023dc4  mov     rbx, [rsi+rbx]
0x180023dc8  test    rbx, rbx
0x180023dcb  jz      loc_1800242D2
0x180023dd1  cmp     [rbx], edi
0x180023dd3  jnz     loc_1800242C5
0x180023dd9  test    rbx, rbx
0x180023ddc  jz      loc_180024446
0x180023de2  test    r12d, r12d
0x180023de5  jnz     short loc_180023DF7
0x180023de7  mov     rax, [rbx+68h]
0x180023deb  mov     rbx, rax
0x180023dee  test    rax, rax
0x180023df1  jz      loc_180024446
0x180023df7  mov     rax, [rbx+20h]
0x180023dfb  mov     rcx, [rbp+3E0h+var_30]
0x180023e02  xor     rcx, rsp; StackCookie
0x180023e05  call    __security_check_cookie
0x180023e0a  add     rsp, 4C0h
0x180023e11  pop     r12
0x180023e13  pop     rdi
0x180023e14  pop     rsi
0x180023e15  pop     rbx
0x180023e16  pop     rbp
0x180023e17  retn
0x180023e19  mov     rbx, cs:gpInvLocHashN
0x180023e20  jmp     loc_180023D9C
0x180023e25  cmp     edi, 1000h
0x180023e2b  jz      loc_1800247DE
0x180023e31  cmp     edi, 1400h
0x180023e37  jnz     loc_180023C77
0x180023e3d  jmp     loc_1800247EE
0x180023e42  mov     rax, gs:30h
0x180023e4b  mov     [rsp+4E0h+arg_8], r14
0x180023e53  mov     [rsp+4E0h+arg_10], r15
0x180023e5b  mov     ecx, [rax+179Ch]
0x180023e61  test    ecx, ecx
0x180023e63  jnz     loc_1800245DE
0x180023e69  mov     ebx, cs:gInteractiveLogonUserProcess
0x180023e6f  mov     r14d, 1
0x180023e75  cmp     ebx, 0FFFFFFFFh
0x180023e78  jz      loc_1800246FC
0x180023e7e  test    ebx, ebx
0x180023e80  jz      loc_1800245D4
0x180023e86  mov     rax, cs:gpServerNlsUserInfo
0x180023e8d  mov     ecx, [rax+678h]
0x180023e93  mov     eax, cs:dword_1803AC290
0x180023e99  cmp     eax, ecx
0x180023e9b  jz      short loc_180023EA5
0x180023e9d  mov     cs:word_1803AC296, r14w
0x180023ea5  movzx   eax, cs:word_1803AC296
0x180023eac  test    ax, ax
0x180023eaf  jz      loc_18002413C
0x180023eb5  movzx   eax, cs:word_1803AC294
0x180023ebc  cmp     ax, 3
0x180023ec0  jz      short loc_180023EE6
0x180023ec2  lea     rcx, gNlsProcessCacheLock
0x180023ec9  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180023ed0  nop     dword ptr [rax+rax+00h]
0x180023ed5  movzx   eax, cs:word_1803AC294
0x180023edc  cmp     ax, 3
0x180023ee0  jnz     loc_1800243A9
0x180023ee6  mov     r15d, 2
0x180023eec  mov     cs:word_1803AC296, r15w
0x180023ef4  cmp     ax, r14w
0x180023ef8  jnz     short loc_180023F3E
0x180023efa  xor     edx, edx; Val
0x180023efc  lea     rcx, [rbp+3E0h+ApiMessage]; void *
0x180023f00  mov     r8d, 3B8h; Size
0x180023f06  call    memset_0
0x180023f0b  mov     edx, 67Ch; BufferSize
0x180023f10  mov     ecx, r14d; ArgumentCount
0x180023f13  call    cs:__imp_CsrAllocateCaptureBuffer
0x180023f1a  nop     dword ptr [rax+rax+00h]
0x180023f1f  mov     rbx, rax
0x180023f22  test    rax, rax
0x180023f25  jnz     loc_18002432B
0x180023f2b  mov     esi, 0C0000017h
0x180023f30  cmp     cs:word_1803AC294, r14w
0x180023f38  jz      loc_18002439C
0x180023f3e  mov     rax, cs:gNlsProcessLocalCache
0x180023f45  mov     [rsp+4E0h+Handle], 0
0x180023f4e  test    rax, rax
0x180023f51  jz      loc_18002448F
0x180023f57  mov     rax, cs:gNlsProcessLocalCache
0x180023f5e  mov     [rsp+4E0h+Handle], rax
0x180023f63  mov     rbx, [rsp+4E0h+Handle]
0x180023f68  lea     rcx, word_1803ABC18
0x180023f6f  mov     rdx, rbx
0x180023f72  mov     r8d, r14d
0x180023f75  call    NlsUpdateCacheInfo
0x180023f7a  cmp     cs:word_1803AC294, 3
0x180023f82  jnz     short loc_180023F98
0x180023f84  test    rbx, rbx
0x180023f87  jz      short loc_180023F98
0x180023f89  mov     rcx, rbx; Handle
0x180023f8c  call    cs:__imp_NtClose
0x180023f93  nop     dword ptr [rax+rax+00h]
0x180023f98  mov     eax, 0FFFFh
0x180023f9d  cmp     cs:word_1803ABC18, ax
0x180023fa4  jz      loc_1800243C5
0x180023faa  mov     rbx, cs:gpOneCustomHashNode
0x180023fb1  lea     rcx, word_1803ABC1A
0x180023fb8  xor     edx, edx
0x180023fba  call    GetNamedLocaleHashNode
0x180023fbf  xchg    rax, cs:qword_1803ABC10
0x180023fc6  test    rbx, rbx
0x180023fc9  jnz     short loc_180023FDB
0x180023fcb  cmp     cs:gpOneCustomHashNode, rbx
0x180023fd2  jz      short loc_180023FDB
0x180023fd4  mov     cs:gpOneCustomHashNode, rbx
0x180023fdb  cmp     cs:qword_1803ABC10, 0
0x180023fe3  jnz     loc_180024111
0x180023fe9  mov     rax, cs:gpSysLocHashN
0x180023ff0  test    rax, rax
0x180023ff3  jnz     loc_18002410A
0x180023ff9  cmp     cs:BasepIsSecureProcess, al
0x180023fff  jnz     loc_18002410A
0x180024005  lea     rcx, gTblPtrsLock
0x18002400c  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180024013  nop     dword ptr [rax+rax+00h]
0x180024018  cmp     cs:gpSysLocHashN, 0
0x180024020  jnz     loc_1800240F0
0x180024026  mov     ebx, cs:gSystemLocale
0x18002402c  mov     rax, cs:P
0x180024033  mov     ecx, ebx
0x180024035  shr     rcx, 7
0x180024039  xor     rcx, rbx
0x18002403c  shr     rcx, 7
0x180024040  xor     rcx, rbx
0x180024043  and     ecx, 7Fh
0x180024046  mov     rdx, [rax+rcx*8]
0x18002404a  test    rdx, rdx
0x18002404d  jz      short loc_180024057
0x18002404f  cmp     [rdx], ebx
0x180024051  jnz     loc_18002469E
0x180024057  mov     cs:gpSysLocHashN, rdx
0x18002405e  test    rdx, rdx
0x180024061  jnz     loc_1800240F0
0x180024067  test    ebx, 0FFF00000h
0x18002406d  jnz     loc_1800245C4
0x180024073  cmp     cs:BasepIsSecureProcess, dl
0x180024079  jnz     loc_1800245C4
0x18002407f  mov     ecx, ebx
0x180024081  call    GetWindowsLocaleData
0x180024086  test    rax, rax
0x180024089  jz      loc_1800246C2
0x18002408f  cmp     bx, 7Fh
0x180024093  jz      loc_18002473F
0x180024099  shr     ebx, 10h
0x18002409c  test    bl, 0Fh
0x18002409f  jnz     loc_180024592
0x1800240a5  mov     ecx, [rax]
0x1800240a7  mov     rax, cs:qword_1803A6BD0
0x1800240ae  add     rax, r15
0x1800240b1  lea     rcx, [rax+rcx*2]
0x1800240b5  xor     edx, edx
0x1800240b7  call    MakeNamedLocaleHashNode
0x1800240bc  mov     cs:gpSysLocHashN, rax
0x1800240c3  test    rax, rax
0x1800240c6  jnz     short loc_1800240F0
0x1800240c8  xor     edx, edx
0x1800240ca  lea     rcx, aEnUs; "en-US"
0x1800240d1  call    MakeNamedLocaleHashNode
0x1800240d6  mov     cs:gpSysLocHashN, rax
0x1800240dd  test    rax, rax
0x1800240e0  jnz     short loc_1800240F0
0x1800240e2  mov     rcx, cs:gpInvLocHashN
0x1800240e9  mov     cs:gpSysLocHashN, rcx
0x1800240f0  lea     rcx, gTblPtrsLock
0x1800240f7  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800240fe  nop     dword ptr [rax+rax+00h]
0x180024103  mov     rax, cs:gpSysLocHashN
0x18002410a  mov     cs:qword_1803ABC10, rax
0x180024111  mov     eax, r15d
0x180024114  xor     edx, edx
0x180024116  lock cmpxchg cs:word_1803AC296, dx
0x18002411f  cmp     cs:word_1803AC294, 3
0x180024127  jz      short loc_18002413C
0x180024129  lea     rcx, gNlsProcessCacheLock
0x180024130  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180024137  nop     dword ptr [rax+rax+00h]
0x18002413c  lea     rbx, gNlsProcessLocalCache
0x180024143  mov     rbx, [rbx+10h]
0x180024147  mov     r15, [rsp+4E0h+arg_10]
0x18002414f  mov     r14, [rsp+4E0h+arg_8]
0x180024157  jmp     loc_180023D9C
0x18002415c  mov     rbx, cs:gpSysLocHashN
0x180024163  test    rbx, rbx
0x180024166  jnz     loc_180023DF7
0x18002416c  cmp     cs:BasepIsSecureProcess, bl
0x180024172  jnz     loc_180023D9C
0x180024178  lea     rcx, gTblPtrsLock
0x18002417f  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180024186  nop     dword ptr [rax+rax+00h]
0x18002418b  cmp     cs:gpSysLocHashN, rbx
0x180024192  jnz     loc_180024263
0x180024198  mov     ebx, cs:gSystemLocale
0x18002419e  mov     rax, cs:P
0x1800241a5  mov     ecx, ebx
0x1800241a7  shr     rcx, 7
0x1800241ab  xor     rcx, rbx
0x1800241ae  shr     rcx, 7
0x1800241b2  xor     rcx, rbx
0x1800241b5  and     ecx, 7Fh
0x1800241b8  mov     rdx, [rax+rcx*8]
  ... truncated ...
```
