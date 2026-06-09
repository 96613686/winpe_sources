# NlsValidateLocale

- ea: `0x180028630`
- end: `0x18002948d`
- name: `NlsValidateLocale`
- size: `3677`
- prototype: ``
- caller_count: `25`
- callee_count: `21`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001e3e0`
- `0x18004d080`
- `0x18004e490`
- `0x180076070`
- `0x1800760e0`
- `0x18007a3f0`
- `0x18007cb20`
- `0x180086700`
- `0x18009ca70`
- `0x18009d030`
- `0x1800b0090`
- `0x1800b03d0`
- `0x1800ba940`
- `0x1800c55c0`
- `0x1800ef610`
- `0x1800f01e0`
- `0x1800f8400`
- `0x1800fd160`
- `0x1801058f0`
- `0x180111b50`
- `0x18012c760`
- `0x1801434e0`
- `0x180143550`
- `0x180143610`
- `0x180146190`

## callees

- `0x18001cd34`
- `0x180024c80`
- `0x1800265f0`
- `0x180028360`
- `0x180028490`
- `0x1800285f0`
- `0x180028630`
- `0x1800294a0`
- `0x180029660`
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

- `ntdll!RtlInitUnicodeString` at `0x1800292b4`
- `ntdll!RtlInitUnicodeString` at `0x1800292b4`
- `ntdll!NtOpenKey` at `0x180029301`
- `ntdll!NtOpenKey` at `0x180029301`
- `ntdll!NtCreateKey` at `0x180029340`
- `ntdll!NtCreateKey` at `0x180029340`
- `ntdll!RtlLcidToLocaleName` at `0x1800291e9`
- `ntdll!RtlLcidToLocaleName` at `0x1800291e9`
- `ntdll!RtlOpenCurrentUser` at `0x180028f03`
- `ntdll!RtlOpenCurrentUser` at `0x180028f03`
- `ntdll!CsrClientCallServer` at `0x180028d90`
- `ntdll!CsrClientCallServer` at `0x180028d90`
- `ntdll!CsrCaptureMessageBuffer` at `0x180028d6a`
- `ntdll!CsrCaptureMessageBuffer` at `0x180028d6a`
- `ntdll!CsrFreeCaptureBuffer` at `0x180028dbb`
- `ntdll!CsrFreeCaptureBuffer` at `0x180028dbb`
- `ntdll!CsrAllocateCaptureBuffer` at `0x180028a71`
- `ntdll!CsrAllocateCaptureBuffer` at `0x180028a71`
- `ntdll!NtClose` at `0x180028aea`
- `ntdll!NtClose` at `0x180028fa7`
- `ntdll!NtClose` at `0x180029358`
- `ntdll!NtClose` at `0x180029399`
- `ntdll!NtClose` at `0x180028aea`
- `ntdll!NtClose` at `0x180028fa7`
- `ntdll!NtClose` at `0x180029358`
- `ntdll!NtClose` at `0x180029399`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800286c2`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180028801`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180028a27`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180028b6a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180028d09`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800286c2`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180028801`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180028a27`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180028b6a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180028d09`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800287ae`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800288ee`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180028c55`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180028c8e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180028d38`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800287ae`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800288ee`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180028c55`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180028c8e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180028d38`
- `ntdll!RtlAllocateHeap` at `0x180029260`
- `ntdll!RtlAllocateHeap` at `0x180029260`

## pseudocode

```c
unsigned int *__fastcall NlsValidateLocale(unsigned int *a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // ebx
  int v4; // r15d
  unsigned int *result; // rax
  DWORD v7; // ebx
  __int64 j; // rdx
  unsigned int *v9; // rax
  __int64 v10; // r8
  DWORD v11; // ebx
  _WORD *v12; // rcx
  __int64 LocHashNodeFromSystemLocale; // rax
  DWORD v14; // edi
  __int64 i; // rdx
  unsigned int *WindowsLocaleData; // rax
  __int64 v17; // r8
  DWORD v18; // edi
  _WORD *v19; // rcx
  __int64 NamedLocaleHashNode; // rax
  unsigned __int64 v21; // rdi
  __int64 v22; // r14
  __int64 v23; // rbx
  __int64 IsImpersonating; // rcx
  int IsInteractiveUserProcess; // eax
  __int16 v26; // ax
  struct _CSR_CAPTURE_BUFFER *CaptureBuffer; // rax
  struct _CSR_CAPTURE_BUFFER *v28; // rbx
  NTSTATUS v29; // edi
  HANDLE v30; // rbx
  __int64 v31; // rbx
  __int64 v32; // rax
  DWORD v33; // ebx
  __int64 k; // rdx
  unsigned int *v35; // rax
  __int64 v36; // r8
  DWORD v37; // ebx
  _WORD *v38; // rcx
  __int64 LocaleHashNode; // rax
  HANDLE *NlsCache; // rbx
  __int64 v41; // rdx
  __int64 v42; // rdx
  unsigned int v43; // ecx
  int GlobalizationUserModelType; // eax
  int v45; // eax
  __int64 v46; // rcx
  WCHAR *v47; // rax
  __int64 v48; // r9
  const WCHAR *v49; // rdx
  WCHAR *v50; // r8
  __int64 v51; // rcx
  WCHAR *v52; // rcx
  __int64 v53; // rdx
  int v54; // ecx
  int v55; // r12d
  int v56; // eax
  __int64 NlsTebCache; // rax
  HANDLE *Heap; // rax
  NTSTATUS v59; // ebx
  HANDLE v60; // rcx
  void *v61; // rbx
  unsigned int *v62; // rax
  __int64 v63; // r8
  unsigned int v64; // edi
  _WORD *v65; // rcx
  __int64 v66; // rax
  __int64 v67; // rdx
  HANDLE Handle; // [rsp+40h] [rbp-C0h] BYREF
  ULONG Disposition; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE KeyHandle[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v71; // [rsp+60h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-68h] BYREF
  WCHAR ApiMessage[32]; // [rsp+B0h] [rbp-50h] BYREF
  PVOID CapturedData; // [rsp+F0h] [rbp-10h] BYREF
  int v76; // [rsp+F8h] [rbp-8h]

  v3 = *a1;
  v4 = a2;
  if ( *a1 == 127 )
  {
    result = (unsigned int *)gpInvLocHashN;
    goto LABEL_44;
  }
  if ( v3 > 0xC00 )
  {
    if ( v3 == 4096 )
    {
      result = (unsigned int *)gpOneCustomHashNode;
      if ( gpOneCustomHashNode )
        goto LABEL_53;
    }
    else if ( v3 != 5120 )
    {
      goto LABEL_26;
    }
    KeyHandle[0] = (HANDLE)11141120;
    KeyHandle[1] = ApiMessage;
    if ( (int)RtlLcidToLocaleName(v3, KeyHandle, 0, 0) >= 0 )
    {
      result = (unsigned int *)GetNamedLocaleHashNode(KeyHandle[1], 0);
      if ( result )
        goto LABEL_53;
    }
LABEL_26:
    result = (unsigned int *)gpSysLocHashN;
    if ( gpSysLocHashN || BasepIsSecureProcess )
    {
LABEL_43:
      if ( v3 != *result )
        goto LABEL_45;
      goto LABEL_44;
    }
    RtlAcquireSRWLockExclusive(&gTblPtrsLock);
    if ( gpSysLocHashN )
      goto LABEL_42;
    v14 = gSystemLocale;
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
      goto LABEL_103;
    WindowsLocaleData = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
    if ( WindowsLocaleData )
    {
      if ( (_WORD)v14 != 127 )
      {
        v18 = HIWORD(v14);
        if ( (v18 & 0xF) == 0 )
        {
          v19 = (_WORD *)(qword_1803A6BD0 + 2 + 2LL * *WindowsLocaleData);
LABEL_38:
          NamedLocaleHashNode = MakeNamedLocaleHashNode(v19, 0);
          goto LABEL_39;
        }
        v41 = WindowsLocaleData[54];
        v19 = (_WORD *)qword_1803A6BD0;
        if ( (_DWORD)v41 )
          v19 = (_WORD *)(qword_1803A6BD0
                        + 2LL * *(unsigned int *)(qword_1803A6BD0 + 2 * (v41 + 2LL * (v18 & 0xF)) - 2)
                        + 2);
        if ( v19 && *v19 )
          goto LABEL_38;
LABEL_103:
        gpSysLocHashN = 0;
LABEL_40:
        gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
        if ( !gpSysLocHashN )
          gpSysLocHashN = gpInvLocHashN;
        goto LABEL_42;
      }
      NamedLocaleHashNode = MakeLocHashNodeFromSystemLocale(WindowsLocaleData, v14, v17, 0);
    }
    else
    {
      if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
        goto LABEL_103;
      if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
        || (unsigned int)CreateTransientLocales() )
      {
        NamedLocaleHashNode = FindLocaleHashNode(v14);
      }
      else
      {
        NamedLocaleHashNode = 0;
      }
    }
LABEL_39:
    gpSysLocHashN = NamedLocaleHashNode;
    if ( !NamedLocaleHashNode )
      goto LABEL_40;
LABEL_42:
    RtlReleaseSRWLockExclusive(&gTblPtrsLock);
    result = (unsigned int *)gpSysLocHashN;
    goto LABEL_43;
  }
  if ( v3 != 3072 && v3 && v3 != 1024 )
  {
    if ( v3 == 2048 )
    {
      result = (unsigned int *)gpSysLocHashN;
      if ( gpSysLocHashN )
        goto LABEL_53;
      if ( BasepIsSecureProcess )
        goto LABEL_44;
      RtlAcquireSRWLockExclusive(&gTblPtrsLock);
      if ( gpSysLocHashN )
        goto LABEL_23;
      v7 = gSystemLocale;
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
        goto LABEL_126;
      v9 = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
      if ( v9 )
      {
        if ( (_WORD)v7 != 127 )
        {
          v11 = HIWORD(v7);
          if ( (v11 & 0xF) == 0 )
          {
            v12 = (_WORD *)(qword_1803A6BD0 + 2 + 2LL * *v9);
LABEL_19:
            LocHashNodeFromSystemLocale = MakeNamedLocaleHashNode(v12, 0);
            goto LABEL_20;
          }
          v42 = v9[54];
          v12 = (_WORD *)qword_1803A6BD0;
          if ( (_DWORD)v42 )
            v12 = (_WORD *)(qword_1803A6BD0
                          + 2LL * *(unsigned int *)(qword_1803A6BD0 + 2 * (v42 + 2LL * (v11 & 0xF)) - 2)
                          + 2);
          if ( v12 && *v12 )
            goto LABEL_19;
LABEL_126:
          gpSysLocHashN = 0;
          goto LABEL_21;
        }
        LocHashNodeFromSystemLocale = MakeLocHashNodeFromSystemLocale(v9, v7, v10, 0);
      }
      else
      {
        if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
          goto LABEL_126;
        if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
          || (unsigned int)CreateTransientLocales() )
        {
          LocHashNodeFromSystemLocale = FindLocaleHashNode(v7);
        }
        else
        {
          LocHashNodeFromSystemLocale = 0;
        }
      }
LABEL_20:
      gpSysLocHashN = LocHashNodeFromSystemLocale;
      if ( LocHashNodeFromSystemLocale )
      {
LABEL_23:
        RtlReleaseSRWLockExclusive(&gTblPtrsLock);
        result = (unsigned int *)gpSysLocHashN;
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
      IsInteractiveUserProcess = NlsInitIsInteractiveUserProcess(IsImpersonating, a2, a3);
    if ( !IsInteractiveUserProcess )
    {
      NlsCheckStaleCache();
      goto LABEL_97;
    }
    if ( dword_1803AC290 != *(_DWORD *)(gpServerNlsUserInfo + 1656) )
      word_1803AC296 = 1;
    if ( !word_1803AC296 )
      goto LABEL_97;
    v26 = word_1803AC294;
    if ( word_1803AC294 != 3 )
    {
      RtlAcquireSRWLockExclusive(&gNlsProcessCacheLock);
      v26 = word_1803AC294;
      if ( word_1803AC294 != 3 )
      {
        if ( !word_1803AC296 )
          goto LABEL_96;
        v26 = word_1803AC294;
      }
    }
    word_1803AC296 = 2;
    if ( v26 == 1 )
    {
      memset_0(ApiMessage, 0, 0x3B8u);
      CaptureBuffer = CsrAllocateCaptureBuffer(1u, 0x67Cu);
      v28 = CaptureBuffer;
      if ( CaptureBuffer )
      {
        CsrCaptureMessageBuffer(CaptureBuffer, 0, 0x67Cu, &CapturedData);
        v76 = 1660;
        v29 = CsrClientCallServer(ApiMessage, v28, (CSR_API_NUMBER)0x1001B, 0x10u);
        if ( v29 >= 0 )
          memcpy_0(&word_1803ABC18, CapturedData, 0x67Cu);
        CsrFreeCaptureBuffer(v28);
      }
      else
      {
        v29 = -1073741801;
      }
      if ( word_1803AC294 == 1 && v29 >= 0 )
      {
LABEL_72:
        if ( word_1803ABC18 == -1 )
        {
          qword_1803ABC10 = 0;
        }
        else
        {
          v31 = gpOneCustomHashNode;
          _InterlockedExchange64(&qword_1803ABC10, GetNamedLocaleHashNode(word_1803ABC1A, 0));
          if ( !v31 && gpOneCustomHashNode )
            gpOneCustomHashNode = 0;
          if ( qword_1803ABC10 )
          {
LABEL_95:
            _InterlockedCompareExchange16(&word_1803AC296, 0, 2);
            if ( word_1803AC294 != 3 )
LABEL_96:
              RtlReleaseSRWLockExclusive(&gNlsProcessCacheLock);
LABEL_97:
            NlsCache = &gNlsProcessLocalCache;
LABEL_98:
            result = (unsigned int *)NlsCache[2];
            goto LABEL_44;
          }
        }
        v32 = gpSysLocHashN;
        if ( gpSysLocHashN || BasepIsSecureProcess )
        {
LABEL_94:
          qword_1803ABC10 = v32;
          goto LABEL_95;
        }
        RtlAcquireSRWLockExclusive(&gTblPtrsLock);
        if ( gpSysLocHashN )
          goto LABEL_93;
        v33 = gSystemLocale;
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
          goto LABEL_93;
        if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
          goto LABEL_154;
        v35 = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
        if ( v35 )
        {
          if ( (_WORD)v33 != 127 )
          {
            v37 = HIWORD(v33);
            if ( (v37 & 0xF) == 0 )
            {
              v38 = (_WORD *)(qword_1803A6BD0 + 2 + 2LL * *v35);
LABEL_89:
              LocaleHashNode = MakeNamedLocaleHashNode(v38, 0);
              goto LABEL_90;
            }
            v53 = v35[54];
            v38 = (_WORD *)qword_1803A6BD0;
            if ( (_DWORD)v53 )
              v38 = (_WORD *)(qword_1803A6BD0
                            + 2LL * *(unsigned int *)(qword_1803A6BD0 + 2 * (v53 + 2LL * (v37 & 0xF)) - 2)
                            + 2);
            if ( v38 && *v38 )
              goto LABEL_89;
LABEL_154:
            gpSysLocHashN = 0;
LABEL_91:
            gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
            if ( !gpSysLocHashN )
              gpSysLocHashN = gpInvLocHashN;
            goto LABEL_93;
          }
          LocaleHashNode = MakeLocHashNodeFromSystemLocale(v35, v33, v36, 0);
        }
        else
        {
          if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
            goto LABEL_154;
          if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
            || (unsigned int)CreateTransientLocales() )
          {
            LocaleHashNode = FindLocaleHashNode(v33);
          }
          else
          {
            LocaleHashNode = 0;
          }
        }
LABEL_90:
        gpSysLocHashN = LocaleHashNode;
        if ( !LocaleHashNode )
          goto LABEL_91;
LABEL_93:
        RtlReleaseSRWLockExclusive(&gTblPtrsLock);
        v32 = gpSysLocHashN;
        goto LABEL_94;
      }
    }
    Handle = 0;
    if ( gNlsProcessLocalCache )
    {
      Handle = gNlsProcessLocalCache;
LABEL_69:
      v30 = Handle;
      NlsUpdateCacheInfo(&word_1803ABC18, Handle, 1);
      if ( word_1803AC294 == 3 && v30 )
        NtClose(v30);
      goto LABEL_72;
    }
    KeyHandle[0] = 0;
    Disposition = 0;
    memset(&ObjectAttributes, 0, 44);
    DestinationString = 0;
    GlobalizationUserModelType = GetGlobalizationUserModelType(0, a2, a3);
    if ( GlobalizationUserModelType == 1 )
    {
      v45 = RtlOpenCurrentUser(0x2000000u, KeyHandle);
    }
    else
    {
      v56 = GlobalizationUserModelType - 2;
      if ( v56 )
      {
        if ( v56 != 1 )
        {
LABEL_149:
          SetLastError_0(0x3F1u);
          goto LABEL_69;
        }
        v71 = 0;
        v45 = OpenGlobalizationUserSettingsKey_ForMua(0x2000000u, 0, KeyHandle, &v71);
      }
      else
      {
        v45 = OpenGlobalizationUserSettingsKey_ForSingleUserModel(0x2000000u, KeyHandle);
      }
    }
    if ( v45 >= 0 )
    {
      ApiMessage[0] = 0;
      v46 = 512;
      v47 = ApiMessage;
      do
      {
        if ( !*v47 )
          break;
        ++v47;
        --v46;
      }
      while ( v46 );
      if ( !v46 )
        goto LABEL_147;
      v48 = v46;
      v49 = L"Control Panel\\International";
      v50 = &ApiMessage[512 - v46];
      v51 = 2147483646;
      do
      {
        if ( !v51 )
          break;
        if ( !*v49 )
          break;
        *v50++ = *v49++;
        --v51;
        --v48;
      }
      while ( v48 );
      v52 = v50 - 1;
      if ( v48 )
        v52 = v50;
      *v52 = 0;
      if ( v48 )
      {
        RtlInitUnicodeString(&DestinationString, ApiMessage);
        ObjectAttributes.RootDirectory = KeyHandle[0];
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        Disposition = 0;
        v59 = NtOpenKey(&Handle, 0x20019u, &ObjectAttributes);
        if ( v59 < 0 )
          v59 = NtCreateKey(&Handle, 0x20019u, &ObjectAttributes, 0, 0, 0, &Disposition);
        if ( KeyHandle[0] )
          NtClose(KeyHandle[0]);
        if ( v59 >= 0 )
        {
          v60 = Handle;
        }
        else
        {
          v60 = 0;
          Handle = 0;
        }
        if ( v59 >= 0 )
        {
          v61 = (void *)_InterlockedCompareExchange64(
                          (volatile signed __int64 *)&gNlsProcessLocalCache,
                          (signed __int64)v60,
                          0);
          if ( v61 )
          {
            if ( Handle )
              NtClose(Handle);
            Handle = v61;
          }
          goto LABEL_69;
        }
      }
      else
      {
LABEL_147:
        if ( KeyHandle[0] )
          NtClose(KeyHandle[0]);
      }
    }
    goto LABEL_149;
  }
  NlsCache = 0;
  v54 = IsImpersonating - 1;
  if ( v54 )
  {
    if ( v54 != 1 )
      goto LABEL_98;
    if ( BasepIsSecureProcess )
      goto LABEL_97;
    v55 = 0;
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
        v55 = 1;
        *((_WORD *)Heap + 842) = 3;
        *((_WORD *)Heap + 843) = 1;
      }
      else
      {
        NlsCache = &gNlsProcessLocalCache;
      }
      NtCurrentTeb()->NlsCache = NlsCache;
    }
    if ( NlsCache == &gNlsProcessLocalCache || !v55 && *((_WORD *)NlsCache + 843) != 1 )
      goto LABEL_98;
    *((_WORD *)NlsCache + 843) = 1;
    UpdateNlsInfoCache(NlsCache, 0);
    result = (unsigned int *)NlsCache[2];
  }
  else
  {
    NlsTebCache = GetNlsTebCache(1, a2, a3);
    NtCurrentTeb()->IsImpersonating = 2;
    result = *(unsigned int **)(NlsTebCache + 16);
  }
LABEL_44:
  if ( result )
    goto LABEL_53;
LABEL_45:
  v21 = *a1;
  v22 = 8LL * (((unsigned __int8)v21 ^ (unsigned __int8)((v21 ^ (v21 >> 7)) >> 7)) & 0x7F);
  v23 = *(_QWORD *)((char *)P + v22);
  if ( !v23 )
  {
LABEL_105:
    RtlAcquireSRWLockExclusive(&gTblPtrsLock);
    v23 = *(_QWORD *)((char *)P + v22);
    if ( v23 )
    {
      while ( *(_DWORD *)v23 != (_DWORD)v21 )
      {
        v23 = *(_QWORD *)(v23 + 88);
        if ( !v23 )
          goto LABEL_206;
      }
      goto LABEL_107;
    }
LABEL_206:
    if ( (v21 & 0xFFF00000) == 0 && !BasepIsSecureProcess )
    {
      v62 = (unsigned int *)GetWindowsLocaleData((unsigned int)v21);
      if ( v62 )
      {
        if ( (_WORD)v21 == 127 )
        {
          v23 = MakeLocHashNodeFromSystemLocale(v62, (unsigned int)v21, v63, 0);
          goto LABEL_107;
        }
        v64 = WORD1(v21);
        if ( (v64 & 0xF) == 0 )
        {
          v65 = (_WORD *)(qword_1803A6BD0 + 2 + 2LL * *v62);
LABEL_212:
          v66 = MakeNamedLocaleHashNode(v65, 0);
LABEL_213:
          v23 = v66;
LABEL_107:
          RtlReleaseSRWLockExclusive(&gTblPtrsLock);
          goto LABEL_47;
        }
        v67 = v62[54];
        v65 = (_WORD *)qword_1803A6BD0;
        if ( (_DWORD)v67 )
          v65 = (_WORD *)(qword_1803A6BD0
                        + 2LL * *(unsigned int *)(qword_1803A6BD0 + 2 * (v67 + 2LL * (v64 & 0xF)) - 2)
                        + 2);
        if ( v65 && *v65 )
          goto LABEL_212;
      }
      else if ( !(unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
             && ((unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
              || (unsigned int)CreateTransientLocales()) )
      {
        v66 = FindLocaleHashNode((unsigned int)v21);
        goto LABEL_213;
      }
    }
    v23 = 0;
    goto LABEL_107;
  }
  while ( *(_DWORD *)v23 != (_DWORD)v21 )
  {
    v23 = *(_QWORD *)(v23 + 88);
    if ( !v23 )
      goto LABEL_105;
  }
LABEL_47:
  if ( !v23 )
  {
    result = 0;
LABEL_128:
    v43 = *a1;
    if ( *a1 != 4096 && ((v43 & 0x3FF) != 0 || v43 - 0x2000 > 0x2C00) )
      return result;
    result = (unsigned int *)GetCurrentNlsCache()[2];
LABEL_53:
    *a1 = *result;
    return result;
  }
  if ( v4 )
    return (unsigned int *)v23;
  result = *(unsigned int **)(v23 + 104);
  if ( !result )
    goto LABEL_128;
  return result;
}

```

## disassembly

```asm
0x180028630  mov     [rsp-8+arg_10], rbx
0x180028635  push    rbp
0x180028636  push    rsi
0x180028637  push    rdi
0x180028638  push    r14
0x18002863a  push    r15
0x18002863c  lea     rbp, [rsp-3C0h]
0x180028644  sub     rsp, 4C0h
0x18002864b  mov     rax, cs:__security_cookie
0x180028652  xor     rax, rsp
0x180028655  mov     [rbp+3E0h+var_30], rax
0x18002865c  mov     ebx, [rcx]
0x18002865e  mov     r15d, edx
0x180028661  mov     rsi, rcx
0x180028664  cmp     ebx, 7Fh
0x180028667  jz      loc_18002898D
0x18002866d  cmp     ebx, 0C00h
0x180028673  ja      loc_1800287C6
0x180028679  jz      loc_1800289A8
0x18002867f  test    ebx, ebx
0x180028681  jz      loc_1800289A8
0x180028687  cmp     ebx, 400h
0x18002868d  jz      loc_1800289A8
0x180028693  cmp     ebx, 800h
0x180028699  jnz     loc_1800287DE
0x18002869f  mov     rax, cs:gpSysLocHashN
0x1800286a6  test    rax, rax
0x1800286a9  jnz     loc_1800289A2
0x1800286af  cmp     cs:BasepIsSecureProcess, al
0x1800286b5  jnz     loc_180028905
0x1800286bb  lea     rcx, gTblPtrsLock
0x1800286c2  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800286c9  nop     dword ptr [rax+rax+00h]
0x1800286ce  cmp     cs:gpSysLocHashN, 0
0x1800286d6  jnz     loc_1800287A7
0x1800286dc  mov     ebx, cs:gSystemLocale
0x1800286e2  mov     rax, cs:P
0x1800286e9  mov     ecx, ebx
0x1800286eb  shr     rcx, 7
0x1800286ef  xor     rcx, rbx
0x1800286f2  shr     rcx, 7
0x1800286f6  xor     rcx, rbx
0x1800286f9  and     ecx, 7Fh
0x1800286fc  mov     rdx, [rax+rcx*8]
0x180028700  test    rdx, rdx
0x180028703  jz      short loc_18002870D
0x180028705  cmp     [rdx], ebx
0x180028707  jnz     loc_1800290A2
0x18002870d  mov     cs:gpSysLocHashN, rdx
0x180028714  test    rdx, rdx
0x180028717  jnz     loc_1800287A7
0x18002871d  test    ebx, 0FFF00000h
0x180028723  jnz     loc_180028E66
0x180028729  cmp     cs:BasepIsSecureProcess, dl
0x18002872f  jnz     loc_180028E66
0x180028735  mov     ecx, ebx
0x180028737  call    GetWindowsLocaleData
0x18002873c  test    rax, rax
0x18002873f  jz      loc_1800290B4
0x180028745  cmp     bx, 7Fh
0x180028749  jz      loc_1800290EC
0x18002874f  shr     ebx, 10h
0x180028752  test    bl, 0Fh
0x180028755  jnz     loc_180028E33
0x18002875b  mov     ecx, [rax]
0x18002875d  mov     rax, cs:qword_1803A6BD0
0x180028764  add     rax, 2
0x180028768  lea     rcx, [rax+rcx*2]
0x18002876c  xor     edx, edx
0x18002876e  call    MakeNamedLocaleHashNode
0x180028773  mov     cs:gpSysLocHashN, rax
0x18002877a  test    rax, rax
0x18002877d  jnz     short loc_1800287A7
0x18002877f  xor     edx, edx
0x180028781  lea     rcx, aEnUs; "en-US"
0x180028788  call    MakeNamedLocaleHashNode
0x18002878d  mov     cs:gpSysLocHashN, rax
0x180028794  test    rax, rax
0x180028797  jnz     short loc_1800287A7
0x180028799  mov     rax, cs:gpInvLocHashN
0x1800287a0  mov     cs:gpSysLocHashN, rax
0x1800287a7  lea     rcx, gTblPtrsLock
0x1800287ae  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800287b5  nop     dword ptr [rax+rax+00h]
0x1800287ba  mov     rax, cs:gpSysLocHashN
0x1800287c1  jmp     loc_180028905
0x1800287c6  cmp     ebx, 1000h
0x1800287cc  jz      loc_1800291B1
0x1800287d2  cmp     ebx, 1400h
0x1800287d8  jz      loc_1800291C1
0x1800287de  mov     rax, cs:gpSysLocHashN
0x1800287e5  test    rax, rax
0x1800287e8  jnz     loc_180028901
0x1800287ee  cmp     cs:BasepIsSecureProcess, al
0x1800287f4  jnz     loc_180028901
0x1800287fa  lea     rcx, gTblPtrsLock
0x180028801  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180028808  nop     dword ptr [rax+rax+00h]
0x18002880d  cmp     cs:gpSysLocHashN, 0
0x180028815  jnz     loc_1800288E7
0x18002881b  mov     edi, cs:gSystemLocale
0x180028821  mov     rax, cs:P
0x180028828  mov     ecx, edi
0x18002882a  shr     rcx, 7
0x18002882e  xor     rcx, rdi
0x180028831  shr     rcx, 7
0x180028835  xor     rcx, rdi
0x180028838  and     ecx, 7Fh
0x18002883b  mov     rdx, [rax+rcx*8]
0x18002883f  test    rdx, rdx
0x180028842  jz      short loc_18002884C
0x180028844  cmp     [rdx], edi
0x180028846  jnz     loc_180028D49
0x18002884c  mov     cs:gpSysLocHashN, rdx
0x180028853  test    rdx, rdx
0x180028856  jnz     loc_1800288E7
0x18002885c  test    edi, 0FFF00000h
0x180028862  jnz     loc_180028CE5
0x180028868  cmp     cs:BasepIsSecureProcess, dl
0x18002886e  jnz     loc_180028CE5
0x180028874  mov     ecx, edi
0x180028876  call    GetWindowsLocaleData
0x18002887b  test    rax, rax
0x18002887e  jz      loc_180028E05
0x180028884  cmp     di, 7Fh
0x180028888  jz      loc_180028EAB
0x18002888e  shr     edi, 10h
0x180028891  test    dil, 0Fh
0x180028895  jnz     loc_180028CB2
0x18002889b  mov     ecx, [rax]
0x18002889d  mov     rax, cs:qword_1803A6BD0
0x1800288a4  add     rax, 2
0x1800288a8  lea     rcx, [rax+rcx*2]
0x1800288ac  xor     edx, edx
0x1800288ae  call    MakeNamedLocaleHashNode
0x1800288b3  mov     cs:gpSysLocHashN, rax
0x1800288ba  test    rax, rax
0x1800288bd  jnz     short loc_1800288E7
0x1800288bf  xor     edx, edx
0x1800288c1  lea     rcx, aEnUs; "en-US"
0x1800288c8  call    MakeNamedLocaleHashNode
0x1800288cd  mov     cs:gpSysLocHashN, rax
0x1800288d4  test    rax, rax
0x1800288d7  jnz     short loc_1800288E7
0x1800288d9  mov     rax, cs:gpInvLocHashN
0x1800288e0  mov     cs:gpSysLocHashN, rax
0x1800288e7  lea     rcx, gTblPtrsLock
0x1800288ee  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800288f5  nop     dword ptr [rax+rax+00h]
0x1800288fa  mov     rax, cs:gpSysLocHashN
0x180028901  cmp     ebx, [rax]
0x180028903  jnz     short loc_18002890E
0x180028905  test    rax, rax
0x180028908  jnz     loc_1800289A2
0x18002890e  mov     edi, [rsi]
0x180028910  mov     rax, cs:P
0x180028917  mov     ecx, edi
0x180028919  shr     rcx, 7
0x18002891d  xor     rcx, rdi
0x180028920  shr     rcx, 7
0x180028924  xor     rcx, rdi
0x180028927  and     ecx, 7Fh
0x18002892a  lea     r14, ds:0[rcx*8]
0x180028932  mov     rbx, [r14+rax]
0x180028936  test    rbx, rbx
0x180028939  jz      loc_180028D02
0x18002893f  cmp     [rbx], edi
0x180028941  jnz     loc_180028CF5
0x180028947  test    rbx, rbx
0x18002894a  jz      loc_180028E76
0x180028950  test    r15d, r15d
0x180028953  jnz     loc_180029217
0x180028959  mov     rax, [rbx+68h]
0x18002895d  test    rax, rax
0x180028960  jz      loc_180028E78
0x180028966  mov     rcx, [rbp+3E0h+var_30]
0x18002896d  xor     rcx, rsp; StackCookie
0x180028970  call    __security_check_cookie
0x180028975  mov     rbx, [rsp+4E0h+arg_10]
0x18002897d  add     rsp, 4C0h
0x180028984  pop     r15
0x180028986  pop     r14
0x180028988  pop     rdi
0x180028989  pop     rsi
0x18002898a  pop     rbp
0x18002898b  retn
0x18002898d  mov     rax, cs:gpInvLocHashN
0x180028994  jmp     loc_180028905
0x180028999  call    GetCurrentNlsCache
0x18002899e  mov     rax, [rax+10h]
0x1800289a2  mov     ecx, [rax]
0x1800289a4  mov     [rsi], ecx
0x1800289a6  jmp     short loc_180028966
0x1800289a8  mov     rax, gs:30h
0x1800289b1  mov     [rsp+4E0h+arg_8], r12
0x1800289b9  mov     ecx, [rax+179Ch]
0x1800289bf  test    ecx, ecx
0x1800289c1  jnz     loc_18002900E
0x1800289c7  mov     eax, cs:gInteractiveLogonUserProcess
0x1800289cd  cmp     eax, 0FFFFFFFFh
0x1800289d0  jz      loc_180029138
0x1800289d6  test    eax, eax
0x1800289d8  jz      loc_180029004
0x1800289de  mov     rax, cs:gpServerNlsUserInfo
0x1800289e5  mov     r14d, 1
0x1800289eb  mov     ecx, [rax+678h]
0x1800289f1  mov     eax, cs:dword_1803AC290
0x1800289f7  cmp     eax, ecx
0x1800289f9  jz      short loc_180028A03
0x1800289fb  mov     cs:word_1803AC296, r14w
0x180028a03  movzx   eax, cs:word_1803AC296
0x180028a0a  test    ax, ax
0x180028a0d  jz      loc_180028C9A
0x180028a13  movzx   eax, cs:word_1803AC294
0x180028a1a  cmp     ax, 3
0x180028a1e  jz      short loc_180028A44
0x180028a20  lea     rcx, gNlsProcessCacheLock
0x180028a27  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180028a2e  nop     dword ptr [rax+rax+00h]
0x180028a33  movzx   eax, cs:word_1803AC294
0x180028a3a  cmp     ax, 3
0x180028a3e  jnz     loc_180028DD9
0x180028a44  mov     r12d, 2
0x180028a4a  mov     cs:word_1803AC296, r12w
0x180028a52  cmp     ax, r14w
0x180028a56  jnz     short loc_180028A9C
0x180028a58  xor     edx, edx; Val
0x180028a5a  lea     rcx, [rbp+3E0h+ApiMessage]; void *
0x180028a5e  mov     r8d, 3B8h; Size
0x180028a64  call    memset_0
0x180028a69  mov     edx, 67Ch; BufferSize
0x180028a6e  mov     ecx, r14d; ArgumentCount
0x180028a71  call    cs:__imp_CsrAllocateCaptureBuffer
0x180028a78  nop     dword ptr [rax+rax+00h]
0x180028a7d  mov     rbx, rax
0x180028a80  test    rax, rax
0x180028a83  jnz     loc_180028D5B
0x180028a89  mov     edi, 0C0000017h
0x180028a8e  cmp     cs:word_1803AC294, r14w
0x180028a96  jz      loc_180028DCC
0x180028a9c  mov     rax, cs:gNlsProcessLocalCache
0x180028aa3  mov     [rsp+4E0h+Handle], 0
0x180028aac  test    rax, rax
0x180028aaf  jz      loc_180028EBD
0x180028ab5  mov     rax, cs:gNlsProcessLocalCache
0x180028abc  mov     [rsp+4E0h+Handle], rax
0x180028ac1  mov     rbx, [rsp+4E0h+Handle]
0x180028ac6  lea     rcx, word_1803ABC18
0x180028acd  mov     rdx, rbx
0x180028ad0  mov     r8d, r14d
0x180028ad3  call    NlsUpdateCacheInfo
0x180028ad8  cmp     cs:word_1803AC294, 3
0x180028ae0  jnz     short loc_180028AF6
0x180028ae2  test    rbx, rbx
0x180028ae5  jz      short loc_180028AF6
0x180028ae7  mov     rcx, rbx; Handle
0x180028aea  call    cs:__imp_NtClose
0x180028af1  nop     dword ptr [rax+rax+00h]
0x180028af6  mov     eax, 0FFFFh
0x180028afb  cmp     cs:word_1803ABC18, ax
0x180028b02  jz      loc_180028DF5
0x180028b08  mov     rbx, cs:gpOneCustomHashNode
0x180028b0f  lea     rcx, word_1803ABC1A
0x180028b16  xor     edx, edx
0x180028b18  call    GetNamedLocaleHashNode
0x180028b1d  xchg    rax, cs:qword_1803ABC10
0x180028b24  test    rbx, rbx
0x180028b27  jnz     short loc_180028B39
0x180028b29  cmp     cs:gpOneCustomHashNode, rbx
0x180028b30  jz      short loc_180028B39
0x180028b32  mov     cs:gpOneCustomHashNode, rbx
0x180028b39  cmp     cs:qword_1803ABC10, 0
0x180028b41  jnz     loc_180028C6F
0x180028b47  mov     rax, cs:gpSysLocHashN
0x180028b4e  test    rax, rax
0x180028b51  jnz     loc_180028C68
0x180028b57  cmp     cs:BasepIsSecureProcess, al
0x180028b5d  jnz     loc_180028C68
0x180028b63  lea     rcx, gTblPtrsLock
0x180028b6a  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180028b71  nop     dword ptr [rax+rax+00h]
0x180028b76  cmp     cs:gpSysLocHashN, 0
0x180028b7e  jnz     loc_180028C4E
0x180028b84  mov     ebx, cs:gSystemLocale
0x180028b8a  mov     rax, cs:P
0x180028b91  mov     ecx, ebx
0x180028b93  shr     rcx, 7
0x180028b97  xor     rcx, rbx
0x180028b9a  shr     rcx, 7
0x180028b9e  xor     rcx, rbx
0x180028ba1  and     ecx, 7Fh
0x180028ba4  mov     rdx, [rax+rcx*8]
0x180028ba8  test    rdx, rdx
0x180028bab  jz      short loc_180028BB5
0x180028bad  cmp     [rdx], ebx
0x180028baf  jnz     loc_1800290DA
0x180028bb5  mov     cs:gpSysLocHashN, rdx
0x180028bbc  test    rdx, rdx
0x180028bbf  jnz     loc_180028C4E
0x180028bc5  test    ebx, 0FFF00000h
  ... truncated ...
```
