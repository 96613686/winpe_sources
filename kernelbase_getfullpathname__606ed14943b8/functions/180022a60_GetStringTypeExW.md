# GetStringTypeExW

- ea: `0x180022a60`
- end: `0x180023bfe`
- name: `GetStringTypeExW`
- size: `4510`
- prototype: `BOOL __stdcall(LCID Locale, DWORD dwInfoType, LPCWCH lpSrcStr, int cchSrc, LPWORD lpCharType)`
- caller_count: `0`
- callee_count: `20`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18001cd34`
- `0x180022a60`
- `0x180024c80`
- `0x1800265f0`
- `0x180028360`
- `0x180028490`
- `0x1800285f0`
- `0x1800294a0`
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

- `ntdll!RtlInitUnicodeString` at `0x180023a06`
- `ntdll!RtlInitUnicodeString` at `0x180023a06`
- `ntdll!NtOpenKey` at `0x180023a53`
- `ntdll!NtOpenKey` at `0x180023a53`
- `ntdll!NtCreateKey` at `0x180023a92`
- `ntdll!NtCreateKey` at `0x180023a92`
- `ntdll!RtlLcidToLocaleName` at `0x18002383f`
- `ntdll!RtlLcidToLocaleName` at `0x18002383f`
- `ntdll!RtlOpenCurrentUser` at `0x18002349c`
- `ntdll!RtlOpenCurrentUser` at `0x18002349c`
- `ntdll!CsrClientCallServer` at `0x180023319`
- `ntdll!CsrClientCallServer` at `0x180023319`
- `ntdll!CsrCaptureMessageBuffer` at `0x1800232f3`
- `ntdll!CsrCaptureMessageBuffer` at `0x1800232f3`
- `ntdll!CsrFreeCaptureBuffer` at `0x180023345`
- `ntdll!CsrFreeCaptureBuffer` at `0x180023345`
- `ntdll!CsrAllocateCaptureBuffer` at `0x180022ecc`
- `ntdll!CsrAllocateCaptureBuffer` at `0x180022ecc`
- `ntdll!NtClose` at `0x180022f4c`
- `ntdll!NtClose` at `0x180023543`
- `ntdll!NtClose` at `0x180023aaa`
- `ntdll!NtClose` at `0x180023aeb`
- `ntdll!NtClose` at `0x180022f4c`
- `ntdll!NtClose` at `0x180023543`
- `ntdll!NtClose` at `0x180023aaa`
- `ntdll!NtClose` at `0x180023aeb`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180022b06`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180022e82`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180022fcc`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180023136`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180023292`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180022b06`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180022e82`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180022fcc`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180023136`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180023292`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180022bf3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800230b8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800230f1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180023223`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800232c1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180022bf3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800230b8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800230f1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180023223`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800232c1`
- `ntdll!RtlAllocateHeap` at `0x180023940`
- `ntdll!RtlAllocateHeap` at `0x1800239a5`
- `ntdll!RtlAllocateHeap` at `0x180023940`
- `ntdll!RtlAllocateHeap` at `0x1800239a5`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
BOOL __stdcall GetStringTypeExW(LCID Locale, DWORD dwInfoType, LPCWCH lpSrcStr, int cchSrc, LPWORD lpCharType)
{
  unsigned __int64 v7; // rsi
  DWORD v8; // edi
  _DWORD *v9; // rax
  DWORD v10; // edi
  __int64 k; // rdx
  unsigned int *v12; // rax
  __int64 v13; // r8
  DWORD v14; // edi
  _WORD *v15; // rcx
  __int64 v16; // rax
  BOOL v17; // r12d
  __int64 v18; // r15
  __int64 v19; // rdi
  HANDLE v20; // rcx
  LPCWCH m; // rbx
  __int64 n; // r10
  __int64 v23; // r9
  unsigned __int64 v24; // rax
  __int64 IsImpersonating; // rcx
  int IsInteractiveUserProcess; // eax
  __int16 v28; // ax
  struct _CSR_CAPTURE_BUFFER *CaptureBuffer; // rax
  struct _CSR_CAPTURE_BUFFER *v30; // rdi
  NTSTATUS v31; // r15d
  HANDLE v32; // rdi
  __int64 v33; // rdi
  __int64 v34; // rax
  DWORD v35; // edi
  __int64 j; // rdx
  unsigned int *v37; // rax
  __int64 v38; // r8
  DWORD v39; // edi
  _WORD *v40; // rcx
  __int64 LocHashNodeFromSystemLocale; // rax
  HANDLE *NlsCache; // rdi
  DWORD v43; // edi
  __int64 i; // rdx
  unsigned int *WindowsLocaleData; // rax
  __int64 v46; // r8
  DWORD v47; // edi
  _WORD *v48; // rcx
  __int64 NamedLocaleHashNode; // rax
  __int64 v50; // rdx
  __int64 v51; // rdx
  int GlobalizationUserModelType; // eax
  int v53; // eax
  __int64 v54; // rcx
  WCHAR *v55; // rax
  __int64 v56; // r9
  const WCHAR *v57; // rdx
  WCHAR *v58; // r8
  __int64 v59; // rcx
  WCHAR *v60; // rcx
  __int64 v61; // rdx
  int v62; // ecx
  int v63; // r12d
  int v64; // eax
  HANDLE *v65; // rdi
  __int64 ii; // r10
  __int64 v67; // r9
  unsigned __int64 v68; // rax
  __int64 jj; // r10
  __int64 v70; // r9
  unsigned __int64 v71; // rax
  HANDLE *Heap; // rax
  HANDLE *v73; // rax
  NTSTATUS v74; // edi
  HANDLE v75; // rcx
  void *v76; // rdi
  unsigned int *v77; // rcx
  __int64 v78; // r8
  _WORD *v79; // rcx
  __int64 LocaleHashNode; // rax
  __int64 v81; // rax
  HANDLE Handle; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v83; // [rsp+48h] [rbp-B8h]
  ULONG Disposition; // [rsp+4Ch] [rbp-B4h] BYREF
  HANDLE KeyHandle[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v86; // [rsp+60h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-68h] BYREF
  WCHAR ApiMessage[32]; // [rsp+B0h] [rbp-50h] BYREF
  PVOID CapturedData; // [rsp+F0h] [rbp-10h] BYREF
  int v91; // [rsp+F8h] [rbp-8h]

  v83 = dwInfoType;
  v7 = Locale;
  v8 = dwInfoType;
  if ( Locale == 127 )
  {
    v9 = (_DWORD *)gpInvLocHashN;
LABEL_27:
    v17 = 1;
    goto LABEL_28;
  }
  if ( Locale <= 0xC00 )
  {
    if ( Locale != 3072 && Locale && Locale != 1024 )
    {
      if ( Locale != 2048 )
        goto LABEL_7;
      v9 = (_DWORD *)gpSysLocHashN;
      if ( gpSysLocHashN || BasepIsSecureProcess )
        goto LABEL_27;
      RtlAcquireSRWLockExclusive(&gTblPtrsLock);
      if ( gpSysLocHashN )
        goto LABEL_126;
      v43 = gSystemLocale;
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
        goto LABEL_126;
      if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
        goto LABEL_154;
      WindowsLocaleData = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
      if ( WindowsLocaleData )
      {
        if ( (_WORD)v43 != 127 )
        {
          v47 = HIWORD(v43);
          if ( (v47 & 0xF) == 0 )
          {
            v48 = (_WORD *)(qword_1803A6BD0 + 2 + 2LL * *WindowsLocaleData);
LABEL_122:
            NamedLocaleHashNode = MakeNamedLocaleHashNode(v48, 0);
            goto LABEL_123;
          }
          v51 = WindowsLocaleData[54];
          v48 = (_WORD *)qword_1803A6BD0;
          if ( (_DWORD)v51 )
            v48 = (_WORD *)(qword_1803A6BD0
                          + 2LL * *(unsigned int *)(qword_1803A6BD0 + 2 * (v51 + 2LL * (v47 & 0xF)) - 2)
                          + 2);
          if ( v48 && *v48 )
            goto LABEL_122;
LABEL_154:
          gpSysLocHashN = 0;
          goto LABEL_124;
        }
        NamedLocaleHashNode = MakeLocHashNodeFromSystemLocale(WindowsLocaleData, v43, v46, 0);
      }
      else
      {
        if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
          goto LABEL_154;
        if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
          || (unsigned int)CreateTransientLocales() )
        {
          NamedLocaleHashNode = FindLocaleHashNode(v43);
        }
        else
        {
          NamedLocaleHashNode = 0;
        }
      }
LABEL_123:
      gpSysLocHashN = NamedLocaleHashNode;
      if ( NamedLocaleHashNode )
      {
LABEL_126:
        RtlReleaseSRWLockExclusive(&gTblPtrsLock);
        v9 = (_DWORD *)gpSysLocHashN;
        goto LABEL_27;
      }
LABEL_124:
      gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
      if ( !gpSysLocHashN )
        gpSysLocHashN = gpInvLocHashN;
      goto LABEL_126;
    }
    IsImpersonating = NtCurrentTeb()->IsImpersonating;
    if ( !(_DWORD)IsImpersonating )
    {
      IsInteractiveUserProcess = gInteractiveLogonUserProcess;
      if ( gInteractiveLogonUserProcess == -1 )
        IsInteractiveUserProcess = NlsInitIsInteractiveUserProcess(IsImpersonating, dwInfoType, lpSrcStr);
      if ( IsInteractiveUserProcess )
      {
        if ( dword_1803AC290 != *(_DWORD *)(gpServerNlsUserInfo + 1656) )
          word_1803AC296 = 1;
        if ( !word_1803AC296 )
          goto LABEL_107;
        v28 = word_1803AC294;
        if ( word_1803AC294 != 3 )
        {
          RtlAcquireSRWLockExclusive(&gNlsProcessCacheLock);
          v28 = word_1803AC294;
          if ( word_1803AC294 != 3 )
          {
            if ( !word_1803AC296 )
              goto LABEL_106;
            v28 = word_1803AC294;
          }
        }
        word_1803AC296 = 2;
        if ( v28 == 1 )
        {
          memset_0(ApiMessage, 0, 0x3B8u);
          CaptureBuffer = CsrAllocateCaptureBuffer(1u, 0x67Cu);
          v30 = CaptureBuffer;
          if ( CaptureBuffer )
          {
            CsrCaptureMessageBuffer(CaptureBuffer, 0, 0x67Cu, &CapturedData);
            v91 = 1660;
            v31 = CsrClientCallServer(ApiMessage, v30, (CSR_API_NUMBER)0x1001B, 0x10u);
            if ( v31 >= 0 )
              memcpy_0(&word_1803ABC18, CapturedData, 0x67Cu);
            CsrFreeCaptureBuffer(v30);
          }
          else
          {
            v31 = -1073741801;
          }
          if ( word_1803AC294 == 1 && v31 >= 0 )
          {
LABEL_82:
            if ( word_1803ABC18 == -1 )
            {
              qword_1803ABC10 = 0;
            }
            else
            {
              v33 = gpOneCustomHashNode;
              _InterlockedExchange64(&qword_1803ABC10, GetNamedLocaleHashNode(word_1803ABC1A, 0));
              if ( !v33 && gpOneCustomHashNode )
                gpOneCustomHashNode = 0;
              if ( qword_1803ABC10 )
              {
LABEL_105:
                _InterlockedCompareExchange16(&word_1803AC296, 0, 2);
                if ( word_1803AC294 == 3 )
                {
LABEL_107:
                  NlsCache = &gNlsProcessLocalCache;
LABEL_108:
                  v17 = 1;
LABEL_109:
                  v9 = NlsCache[2];
                  goto LABEL_28;
                }
LABEL_106:
                RtlReleaseSRWLockExclusive(&gNlsProcessCacheLock);
                goto LABEL_107;
              }
            }
            v34 = gpSysLocHashN;
            if ( gpSysLocHashN || BasepIsSecureProcess )
            {
LABEL_104:
              qword_1803ABC10 = v34;
              goto LABEL_105;
            }
            RtlAcquireSRWLockExclusive(&gTblPtrsLock);
            if ( gpSysLocHashN )
              goto LABEL_103;
            v35 = gSystemLocale;
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
              goto LABEL_103;
            if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
              goto LABEL_183;
            v37 = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
            if ( v37 )
            {
              if ( (_WORD)v35 != 127 )
              {
                v39 = HIWORD(v35);
                if ( (v39 & 0xF) == 0 )
                {
                  v40 = (_WORD *)(qword_1803A6BD0 + 2 + 2LL * *v37);
LABEL_99:
                  LocHashNodeFromSystemLocale = MakeNamedLocaleHashNode(v40, 0);
                  goto LABEL_100;
                }
                v61 = v37[54];
                v40 = (_WORD *)qword_1803A6BD0;
                if ( (_DWORD)v61 )
                  v40 = (_WORD *)(qword_1803A6BD0
                                + 2LL * *(unsigned int *)(qword_1803A6BD0 + 2 * (v61 + 2LL * (v39 & 0xF)) - 2)
                                + 2);
                if ( v40 && *v40 )
                  goto LABEL_99;
LABEL_183:
                gpSysLocHashN = 0;
LABEL_101:
                gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
                if ( !gpSysLocHashN )
                  gpSysLocHashN = gpInvLocHashN;
                goto LABEL_103;
              }
              LocHashNodeFromSystemLocale = MakeLocHashNodeFromSystemLocale(v37, v35, v38, 0);
            }
            else
            {
              if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
                goto LABEL_183;
              if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
                || (unsigned int)CreateTransientLocales() )
              {
                LocHashNodeFromSystemLocale = FindLocaleHashNode(v35);
              }
              else
              {
                LocHashNodeFromSystemLocale = 0;
              }
            }
LABEL_100:
            gpSysLocHashN = LocHashNodeFromSystemLocale;
            if ( !LocHashNodeFromSystemLocale )
              goto LABEL_101;
LABEL_103:
            RtlReleaseSRWLockExclusive(&gTblPtrsLock);
            v34 = gpSysLocHashN;
            goto LABEL_104;
          }
        }
        Handle = 0;
        if ( gNlsProcessLocalCache )
        {
          Handle = gNlsProcessLocalCache;
LABEL_79:
          v32 = Handle;
          NlsUpdateCacheInfo(&word_1803ABC18, Handle, 1);
          if ( word_1803AC294 == 3 && v32 )
            NtClose(v32);
          goto LABEL_82;
        }
        KeyHandle[0] = 0;
        Disposition = 0;
        memset(&ObjectAttributes, 0, 44);
        DestinationString = 0;
        GlobalizationUserModelType = GetGlobalizationUserModelType(0, *(_QWORD *)&dwInfoType, lpSrcStr);
        if ( GlobalizationUserModelType == 1 )
        {
          v53 = RtlOpenCurrentUser(0x2000000u, KeyHandle);
        }
        else
        {
          v64 = GlobalizationUserModelType - 2;
          if ( v64 )
          {
            if ( v64 != 1 )
            {
LABEL_178:
              SetLastError_0(0x3F1u);
              goto LABEL_79;
            }
            v86 = 0;
            v53 = OpenGlobalizationUserSettingsKey_ForMua(0x2000000u, 0, KeyHandle, &v86);
          }
          else
          {
            v53 = OpenGlobalizationUserSettingsKey_ForSingleUserModel(0x2000000u, KeyHandle);
          }
        }
        if ( v53 >= 0 )
        {
          ApiMessage[0] = 0;
          v54 = 512;
          v55 = ApiMessage;
          do
          {
            if ( !*v55 )
              break;
            ++v55;
            --v54;
          }
          while ( v54 );
          if ( !v54 )
            goto LABEL_176;
          v56 = v54;
          v57 = L"Control Panel\\International";
          v58 = &ApiMessage[512 - v54];
          v59 = 2147483646;
          do
          {
            if ( !v59 )
              break;
            if ( !*v57 )
              break;
            *v58++ = *v57++;
            --v59;
            --v56;
          }
          while ( v56 );
          v60 = v58 - 1;
          if ( v56 )
            v60 = v58;
          *v60 = 0;
          if ( v56 )
          {
            RtlInitUnicodeString(&DestinationString, ApiMessage);
            ObjectAttributes.RootDirectory = KeyHandle[0];
            ObjectAttributes.Length = 48;
            ObjectAttributes.ObjectName = &DestinationString;
            ObjectAttributes.Attributes = 64;
            *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
            Disposition = 0;
            v74 = NtOpenKey(&Handle, 0x20019u, &ObjectAttributes);
            if ( v74 < 0 )
              v74 = NtCreateKey(&Handle, 0x20019u, &ObjectAttributes, 0, 0, 0, &Disposition);
            if ( KeyHandle[0] )
              NtClose(KeyHandle[0]);
            if ( v74 >= 0 )
            {
              v75 = Handle;
            }
            else
            {
              v75 = 0;
              Handle = 0;
            }
            if ( v74 >= 0 )
            {
              v76 = (void *)_InterlockedCompareExchange64(
                              (volatile signed __int64 *)&gNlsProcessLocalCache,
                              (signed __int64)v75,
                              0);
              if ( v76 )
              {
                if ( Handle )
                  NtClose(Handle);
                Handle = v76;
              }
              goto LABEL_79;
            }
          }
          else
          {
LABEL_176:
            if ( KeyHandle[0] )
              NtClose(KeyHandle[0]);
          }
        }
        goto LABEL_178;
      }
      NlsCheckStaleCache();
      goto LABEL_185;
    }
    NlsCache = 0;
    v62 = IsImpersonating - 1;
    if ( v62 )
    {
      if ( v62 != 1 )
        goto LABEL_186;
      if ( BasepIsSecureProcess )
      {
LABEL_185:
        NlsCache = &gNlsProcessLocalCache;
LABEL_186:
        v17 = 1;
        goto LABEL_109;
      }
      v63 = 0;
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
          v63 = 1;
        }
        else
        {
          NlsCache = &gNlsProcessLocalCache;
        }
        NtCurrentTeb()->NlsCache = NlsCache;
      }
      if ( NlsCache == &gNlsProcessLocalCache || !v63 && *((_WORD *)NlsCache + 843) != 1 )
        goto LABEL_108;
      v17 = 1;
      *((_WORD *)NlsCache + 843) = 1;
      UpdateNlsInfoCache((__int64)NlsCache, 0, (__int64)lpSrcStr);
      v9 = NlsCache[2];
    }
    else
    {
      if ( BasepIsSecureProcess )
      {
        v65 = &gNlsProcessLocalCache;
      }
      else
      {
        v65 = (HANDLE *)NtCurrentTeb()->NlsCache;
        if ( !v65 )
        {
          v73 = (HANDLE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x698u);
          v65 = v73;
          if ( v73 )
          {
            *v73 = 0;
            v73[1] = 0;
            v73[2] = 0;
            *((_WORD *)v73 + 842) = 3;
            *((_WORD *)v73 + 843) = 1;
          }
          else
          {
            v65 = &gNlsProcessLocalCache;
          }
          NtCurrentTeb()->NlsCache = v65;
        }
        if ( v65 != &gNlsProcessLocalCache )
        {
          *((_WORD *)v65 + 843) = 1;
          UpdateNlsInfoCache((__int64)v65, 0, (__int64)lpSrcStr);
        }
      }
      NtCurrentTeb()->IsImpersonating = 2;
      v17 = 1;
      v9 = v65[2];
    }
LABEL_28:
    if ( v9 )
    {
LABEL_33:
      v8 = v83;
      goto LABEL_34;
    }
LABEL_29:
    v18 = 8LL * (((unsigned __int8)v7 ^ (unsigned __int8)((v7 ^ (v7 >> 7)) >> 7)) & 0x7F);
    v19 = *(_QWORD *)((char *)P + v18);
    if ( v19 )
    {
      while ( *(_DWORD *)v19 != (_DWORD)v7 )
      {
        v19 = *(_QWORD *)(v19 + 88);
        if ( !v19 )
          goto LABEL_133;
      }
LABEL_31:
      if ( v19 )
      {
        v20 = *(HANDLE *)(v19 + 104);
        if ( v20 )
          goto LABEL_33;
      }
      else
      {
        v20 = 0;
      }
      if ( (_DWORD)v7 == 4096 || (v7 & 0x3FF) == 0 && (unsigned int)(v7 - 0x2000) <= 0x2C00 )
        v20 = GetCurrentNlsCache()[2];
      if ( !v20 )
      {
        SetLastError_0(0x57u);
        return 0;
      }
      goto LABEL_33;
    }
LABEL_133:
    RtlAcquireSRWLockExclusive(&gTblPtrsLock);
    v19 = *(_QWORD *)((char *)P + v18);
    if ( v19 )
    {
      while ( *(_DWORD *)v19 != (_DWORD)v7 )
      {
        v19 = *(_QWORD *)(v19 + 88);
        if ( !v19 )
          goto LABEL_254;
      }
      goto LABEL_135;
    }
LABEL_254:
    if ( (v7 & 0xFFF00000) == 0 && !BasepIsSecureProcess )
    {
      v77 = (unsigned int *)GetWindowsLocaleData((unsigned int)v7);
      if ( v77 )
      {
        if ( (_WORD)v7 == 127 )
        {
          v19 = MakeLocHashNodeFromSystemLocale(v77, (unsigned int)v7, v78, 0);
          goto LABEL_135;
        }
        if ( (v7 & 0xF0000) == 0 )
        {
          v79 = (_WORD *)(qword_1803A6BD0 + 2 + 2LL * *v77);
LABEL_260:
          LocaleHashNode = MakeNamedLocaleHashNode(v79, 0);
LABEL_261:
          v19 = LocaleHashNode;
LABEL_135:
          RtlReleaseSRWLockExclusive(&gTblPtrsLock);
          goto LABEL_31;
        }
        v81 = v77[54];
        v79 = (_WORD *)qword_1803A6BD0;
        if ( (_DWORD)v81 )
          v79 = (_WORD *)(qword_1803A6BD0
                        + 2LL * *(unsigned int *)(qword_1803A6BD0 + 2 * (v81 + 2LL * (BYTE2(v7) & 0xF)) - 2)
                        + 2);
        if ( v79 && *v79 )
          goto LABEL_260;
      }
      else if ( !(unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
             && ((unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
              || (unsigned int)CreateTransientLocales()) )
      {
        LocaleHashNode = FindLocaleHashNode((unsigned int)v7);
        goto LABEL_261;
      }
    }
    v19 = 0;
    goto LABEL_135;
  }
  if ( Locale == 4096 )
  {
    v9 = (_DWORD *)gpOneCustomHashNode;
    if ( gpOneCustomHashNode )
      goto LABEL_27;
  }
  else if ( Locale != 5120 )
  {
    goto LABEL_7;
  }
  KeyHandle[0] = (HANDLE)11141120;
  KeyHandle[1] = ApiMessage;
  if ( (int)RtlLcidToLocaleName(Locale, KeyHandle, 0, 0) < 0 || !GetNamedLocaleHashNode(KeyHandle[1], 0) )
  {
LABEL_7:
    v9 = (_DWORD *)gpSysLocHashN;
    if ( gpSysLocHashN || BasepIsSecureProcess )
    {
LABEL_24:
      v17 = 1;
      if ( (_DWORD)v7 != *v9 )
        goto LABEL_29;
      goto LABEL_28;
    }
    RtlAcquireSRWLockExclusive(&gTblPtrsLock);
    if ( gpSysLocHashN )
      goto LABEL_23;
    v10 = gSystemLocale;
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
      goto LABEL_131;
    v12 = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
    if ( v12 )
    {
      if ( (_WORD)v10 != 127 )
      {
        v14 = HIWORD(v10);
        if ( (v14 & 0xF) == 0 )
        {
          v15 = (_WORD *)(qword_1803A6BD0 + 2 + 2LL * *v12);
LABEL_19:
          v16 = MakeNamedLocaleHashNode(v15, 0);
          goto LABEL_20;
        }
        v50 = v12[54];
        v15 = (_WORD *)qword_1803A6BD0;
        if ( (_DWORD)v50 )
          v15 = (_WORD *)(qword_1803A6BD0
                        + 2LL * *(unsigned int *)(qword_1803A6BD0 + 2 * (v50 + 2LL * (v14 & 0xF)) - 2)
                        + 2);
        if ( v15 && *v15 )
          goto LABEL_19;
LABEL_131:
        gpSysLocHashN = 0;
LABEL_21:
        gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
        if ( !gpSysLocHashN )
          gpSysLocHashN = gpInvLocHashN;
        goto LABEL_23;
      }
      v16 = MakeLocHashNodeFromSystemLocale(v12, v10, v13, 0);
    }
    else
    {
      if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
        goto LABEL_131;
      if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
        || (unsigned int)CreateTransientLocales() )
      {
        v16 = FindLocaleHashNode(v10);
      }
      else
      {
        v16 = 0;
      }
    }
LABEL_20:
    gpSysLocHashN = v16;
    if ( !v16 )
      goto LABEL_21;
LABEL_23:
    RtlReleaseSRWLockExclusive(&gTblPtrsLock);
    v9 = (_DWORD *)gpSysLocHashN;
    goto LABEL_24;
  }
  v17 = 1;
LABEL_34:
  if ( lpSrcStr && cchSrc && lpCharType && lpSrcStr != lpCharType )
  {
    if ( cchSrc <= -1 )
    {
      for ( m = lpSrcStr; *m; ++m )
      {
        if ( !*++m )
          break;
        if ( !*++m )
          break;
        if ( !*++m )
          break;
        if ( !*++m )
          break;
        if ( !*++m )
          break;
        if ( !*++m )
          break;
        if ( !*++m )
          break;
        if ( !*++m )
          break;
        if ( !*++m )
          break;
        if ( !*++m )
          break;
        if ( !*++m )
          break;
        if ( !*++m )
          break;
        if ( !*++m )
          break;
        if ( !*++m )
          break;
        if ( !*++m )
          break;
      }
      cchSrc = m - lpSrcStr + 1;
    }
    switch ( v8 )
    {
      case 1u:
        for ( n = 0;
              (int)n < cchSrc;
              lpCharType[v23] = *(_WORD *)(qword_1803A6BE0
                                         + 6LL
                                         * *(unsigned __int8 *)((v24 & 0xF)
                                                              + qword_1803A6BE8
                                                              + *(unsigned __int16 *)(qword_1803A6BE8
                                                                                    + 2
                                                                                    * (((unsigned __int64)(unsigned __int8)v24 >> 4)
                                                                                     + ((unsigned __int64)*(unsigned __int16 *)(qword_1803A6BE8 + 2 * (v24 >> 8)) >> 1))))) )
        {
          v23 = n;
          v24 = lpSrcStr[n];
          n = (unsigned int)(n + 1);
        }
        break;
      case 2u:
        for ( ii = 0;
              (int)ii < cchSrc;
              lpCharType[v67] = *(_WORD *)(qword_1803A6BE0
                                         + 6LL
                                         * *(unsigned __int8 *)((v68 & 0xF)
                                                              + qword_1803A6BE8
                                                              + *(unsigned __int16 *)(qword_1803A6BE8
                                                                                    + 2
                                                                                    * (((unsigned __int64)(unsigned __int8)v68 >> 4)
                                                                                     + ((unsigned __int64)*(unsigned __int16 *)(qword_1803A6BE8 + 2 * (v68 >> 8)) >> 1))))
                                         + 2) )
        {
          v67 = ii;
          v68 = lpSrcStr[ii];
          ii = (unsigned int)(ii + 1);
        }
        break;
      case 4u:
        for ( jj = 0;
              (int)jj < cchSrc;
              lpCharType[v70] = *(_WORD *)(qword_1803A6BE0
                                         + 6LL
                                         * *(unsigned __int8 *)((v71 & 0xF)
                                                              + qword_1803A6BE8
                                                              + *(unsigned __int16 *)(qword_1803A6BE8
                                                                                    + 2
                                                                                    * (((unsigned __int64)(unsigned __int8)v71 >> 4)
                                                                                     + ((unsigned __int64)*(unsigned __int16 *)(qword_1803A6BE8 + 2 * (v71 >> 8)) >> 1))))
                                         + 4) )
        {
          v70 = jj;
          v71 = lpSrcStr[jj];
          jj = (unsigned int)(jj + 1);
        }
        break;
      default:
        SetLastError_0(0x3ECu);
        return 0;
    }
  }
  else
  {
    SetLastError_0(0x57u);
    return 0;
  }
  return v17;
}

```

## disassembly

```asm
0x180022a60  push    rbp
0x180022a62  push    rbx
0x180022a63  push    rsi
0x180022a64  push    rdi
0x180022a65  push    r12
0x180022a67  push    r13
0x180022a69  push    r14
0x180022a6b  push    r15
0x180022a6d  lea     rbp, [rsp-3C8h]
0x180022a75  sub     rsp, 4C8h
0x180022a7c  mov     rax, cs:__security_cookie
0x180022a83  xor     rax, rsp
0x180022a86  mov     [rbp+400h+var_50], rax
0x180022a8d  mov     r13, [rbp+400h+lpCharType]
0x180022a94  mov     ebx, r9d
0x180022a97  mov     [rsp+500h+var_4B8], edx
0x180022a9b  mov     r14, r8
0x180022a9e  mov     esi, ecx
0x180022aa0  mov     edi, edx
0x180022aa2  mov     r15d, 1
0x180022aa8  cmp     ecx, 7Fh
0x180022aab  jz      loc_180022C0F
0x180022ab1  cmp     esi, 0C00h
0x180022ab7  ja      loc_180022DF4
0x180022abd  jz      loc_180022E11
0x180022ac3  test    ecx, ecx
0x180022ac5  jz      loc_180022E11
0x180022acb  cmp     esi, 400h
0x180022ad1  jz      loc_180022E11
0x180022ad7  cmp     esi, 800h
0x180022add  jz      loc_180023113
0x180022ae3  mov     rax, cs:gpSysLocHashN
0x180022aea  test    rax, rax
0x180022aed  jnz     loc_180022C06
0x180022af3  cmp     cs:BasepIsSecureProcess, al
0x180022af9  jnz     loc_180022C06
0x180022aff  lea     rcx, gTblPtrsLock
0x180022b06  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180022b0d  nop     dword ptr [rax+rax+00h]
0x180022b12  cmp     cs:gpSysLocHashN, 0
0x180022b1a  jnz     loc_180022BEC
0x180022b20  mov     edi, cs:gSystemLocale
0x180022b26  mov     rax, cs:P
0x180022b2d  mov     ecx, edi
0x180022b2f  shr     rcx, 7
0x180022b33  xor     rcx, rdi
0x180022b36  shr     rcx, 7
0x180022b3a  xor     rcx, rdi
0x180022b3d  and     ecx, 7Fh
0x180022b40  mov     rdx, [rax+rcx*8]
0x180022b44  test    rdx, rdx
0x180022b47  jz      short loc_180022B51
0x180022b49  cmp     [rdx], edi
0x180022b4b  jnz     loc_1800232D2
0x180022b51  mov     cs:gpSysLocHashN, rdx
0x180022b58  test    rdx, rdx
0x180022b5b  jnz     loc_180022BEC
0x180022b61  test    edi, 0FFF00000h
0x180022b67  jnz     loc_18002326E
0x180022b6d  cmp     cs:BasepIsSecureProcess, dl
0x180022b73  jnz     loc_18002326E
0x180022b79  mov     ecx, edi
0x180022b7b  call    GetWindowsLocaleData
0x180022b80  test    rax, rax
0x180022b83  jz      loc_180023390
0x180022b89  cmp     di, 7Fh
0x180022b8d  jz      loc_180023401
0x180022b93  shr     edi, 10h
0x180022b96  test    dil, 0Fh
0x180022b9a  jnz     loc_18002323B
0x180022ba0  mov     ecx, [rax]
0x180022ba2  mov     rax, cs:qword_1803A6BD0
0x180022ba9  add     rax, 2
0x180022bad  lea     rcx, [rax+rcx*2]
0x180022bb1  xor     edx, edx
0x180022bb3  call    MakeNamedLocaleHashNode
0x180022bb8  mov     cs:gpSysLocHashN, rax
0x180022bbf  test    rax, rax
0x180022bc2  jnz     short loc_180022BEC
0x180022bc4  xor     edx, edx
0x180022bc6  lea     rcx, aEnUs; "en-US"
0x180022bcd  call    MakeNamedLocaleHashNode
0x180022bd2  mov     cs:gpSysLocHashN, rax
0x180022bd9  test    rax, rax
0x180022bdc  jnz     short loc_180022BEC
0x180022bde  mov     rax, cs:gpInvLocHashN
0x180022be5  mov     cs:gpSysLocHashN, rax
0x180022bec  lea     rcx, gTblPtrsLock
0x180022bf3  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180022bfa  nop     dword ptr [rax+rax+00h]
0x180022bff  mov     rax, cs:gpSysLocHashN
0x180022c06  mov     r12d, r15d
0x180022c09  cmp     esi, [rax]
0x180022c0b  jnz     short loc_180022C1E
0x180022c0d  jmp     short loc_180022C19
0x180022c0f  mov     rax, cs:gpInvLocHashN
0x180022c16  mov     r12d, r15d
0x180022c19  test    rax, rax
0x180022c1c  jnz     short loc_180022C6C
0x180022c1e  mov     rax, cs:P
0x180022c25  mov     rcx, rsi
0x180022c28  shr     rcx, 7
0x180022c2c  xor     rcx, rsi
0x180022c2f  shr     rcx, 7
0x180022c33  xor     rcx, rsi
0x180022c36  and     ecx, 7Fh
0x180022c39  lea     r15, ds:0[rcx*8]
0x180022c41  mov     rdi, [r15+rax]
0x180022c45  test    rdi, rdi
0x180022c48  jz      loc_18002328B
0x180022c4e  cmp     [rdi], esi
0x180022c50  jnz     loc_18002327E
0x180022c56  test    rdi, rdi
0x180022c59  jz      loc_180023413
0x180022c5f  mov     rcx, [rdi+68h]
0x180022c63  test    rcx, rcx
0x180022c66  jz      loc_180023415
0x180022c6c  mov     edi, [rsp+500h+var_4B8]
0x180022c70  test    r14, r14
0x180022c73  jz      loc_180023674
0x180022c79  test    ebx, ebx
0x180022c7b  jz      loc_180023674
0x180022c81  test    r13, r13
0x180022c84  jz      loc_180023674
0x180022c8a  cmp     r14, r13
0x180022c8d  jz      loc_180023674
0x180022c93  cmp     ebx, 0FFFFFFFFh
0x180022c96  jg      loc_180022D68
0x180022c9c  cmp     word ptr [r14], 0
0x180022ca1  mov     rbx, r14
0x180022ca4  jz      loc_180022D60
0x180022caa  nop     word ptr [rax+rax+00h]
0x180022cb0  add     rbx, 2
0x180022cb4  cmp     word ptr [rbx], 0
0x180022cb8  jz      loc_180022D60
0x180022cbe  add     rbx, 2
0x180022cc2  cmp     word ptr [rbx], 0
0x180022cc6  jz      loc_180022D60
0x180022ccc  add     rbx, 2
0x180022cd0  cmp     word ptr [rbx], 0
0x180022cd4  jz      loc_180022D60
0x180022cda  add     rbx, 2
0x180022cde  cmp     word ptr [rbx], 0
0x180022ce2  jz      short loc_180022D60
0x180022ce4  add     rbx, 2
0x180022ce8  cmp     word ptr [rbx], 0
0x180022cec  jz      short loc_180022D60
0x180022cee  add     rbx, 2
0x180022cf2  cmp     word ptr [rbx], 0
0x180022cf6  jz      short loc_180022D60
0x180022cf8  add     rbx, 2
0x180022cfc  cmp     word ptr [rbx], 0
0x180022d00  jz      short loc_180022D60
0x180022d02  add     rbx, 2
0x180022d06  cmp     word ptr [rbx], 0
0x180022d0a  jz      short loc_180022D60
0x180022d0c  add     rbx, 2
0x180022d10  cmp     word ptr [rbx], 0
0x180022d14  jz      short loc_180022D60
0x180022d16  add     rbx, 2
0x180022d1a  cmp     word ptr [rbx], 0
0x180022d1e  jz      short loc_180022D60
0x180022d20  add     rbx, 2
0x180022d24  cmp     word ptr [rbx], 0
0x180022d28  jz      short loc_180022D60
0x180022d2a  add     rbx, 2
0x180022d2e  cmp     word ptr [rbx], 0
0x180022d32  jz      short loc_180022D60
0x180022d34  add     rbx, 2
0x180022d38  cmp     word ptr [rbx], 0
0x180022d3c  jz      short loc_180022D60
0x180022d3e  add     rbx, 2
0x180022d42  cmp     word ptr [rbx], 0
0x180022d46  jz      short loc_180022D60
0x180022d48  add     rbx, 2
0x180022d4c  cmp     word ptr [rbx], 0
0x180022d50  jz      short loc_180022D60
0x180022d52  add     rbx, 2
0x180022d56  cmp     word ptr [rbx], 0
0x180022d5a  jnz     loc_180022CB0
0x180022d60  sub     rbx, r14
0x180022d63  sar     rbx, 1
0x180022d66  inc     ebx
0x180022d68  cmp     edi, 1
0x180022d6b  jnz     loc_18002378A
0x180022d71  xor     r10d, r10d
0x180022d74  test    ebx, ebx
0x180022d76  jle     short loc_180022DCD
0x180022d78  mov     rdx, cs:qword_1803A6BE8
0x180022d7f  lea     r9, [r10+r10]
0x180022d83  movzx   eax, word ptr [r14+r9]
0x180022d88  inc     r10d
0x180022d8b  movzx   r8d, al
0x180022d8f  shr     rax, 8
0x180022d93  movzx   ecx, word ptr [rdx+rax*2]
0x180022d97  mov     eax, r8d
0x180022d9a  shr     rax, 4
0x180022d9e  and     r8d, 0Fh
0x180022da2  shr     rcx, 1
0x180022da5  add     rcx, rax
0x180022da8  movzx   eax, word ptr [rdx+rcx*2]
0x180022dac  add     rax, rdx
0x180022daf  movzx   ecx, byte ptr [r8+rax]
0x180022db4  mov     rax, cs:qword_1803A6BE0
0x180022dbb  lea     rcx, [rcx+rcx*2]
0x180022dbf  movzx   ecx, word ptr [rax+rcx*2]
0x180022dc3  mov     [r9+r13], cx
0x180022dc8  cmp     r10d, ebx
0x180022dcb  jl      short loc_180022D78
0x180022dcd  mov     eax, r12d
0x180022dd0  mov     rcx, [rbp+400h+var_50]
0x180022dd7  xor     rcx, rsp; StackCookie
0x180022dda  call    __security_check_cookie
0x180022ddf  add     rsp, 4C8h
0x180022de6  pop     r15
0x180022de8  pop     r14
0x180022dea  pop     r13
0x180022dec  pop     r12
0x180022dee  pop     rdi
0x180022def  pop     rsi
0x180022df0  pop     rbx
0x180022df1  pop     rbp
0x180022df2  retn
0x180022df4  cmp     esi, 1000h
0x180022dfa  jz      loc_180023807
0x180022e00  cmp     esi, 1400h
0x180022e06  jnz     loc_180022AE3
0x180022e0c  jmp     loc_180023817
0x180022e11  mov     rax, gs:30h
0x180022e1a  mov     ecx, [rax+179Ch]
0x180022e20  test    ecx, ecx
0x180022e22  jnz     loc_1800235B4
0x180022e28  mov     eax, cs:gInteractiveLogonUserProcess
0x180022e2e  cmp     eax, 0FFFFFFFFh
0x180022e31  jz      loc_1800236E4
0x180022e37  test    eax, eax
0x180022e39  jz      loc_1800235A0
0x180022e3f  mov     rax, cs:gpServerNlsUserInfo
0x180022e46  mov     ecx, [rax+678h]
0x180022e4c  mov     eax, cs:dword_1803AC290
0x180022e52  cmp     eax, ecx
0x180022e54  jz      short loc_180022E5E
0x180022e56  mov     cs:word_1803AC296, r15w
0x180022e5e  movzx   eax, cs:word_1803AC296
0x180022e65  test    ax, ax
0x180022e68  jz      loc_1800230FD
0x180022e6e  movzx   eax, cs:word_1803AC294
0x180022e75  cmp     ax, 3
0x180022e79  jz      short loc_180022E9F
0x180022e7b  lea     rcx, gNlsProcessCacheLock
0x180022e82  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180022e89  nop     dword ptr [rax+rax+00h]
0x180022e8e  movzx   eax, cs:word_1803AC294
0x180022e95  cmp     ax, 3
0x180022e99  jnz     loc_180023364
0x180022e9f  mov     r12d, 2
0x180022ea5  mov     cs:word_1803AC296, r12w
0x180022ead  cmp     ax, r15w
0x180022eb1  jnz     short loc_180022EFE
0x180022eb3  xor     edx, edx; Val
0x180022eb5  lea     rcx, [rbp+400h+ApiMessage]; void *
0x180022eb9  mov     r8d, 3B8h; Size
0x180022ebf  call    memset_0
0x180022ec4  mov     edx, 67Ch; BufferSize
0x180022ec9  mov     ecx, r15d; ArgumentCount
0x180022ecc  call    cs:__imp_CsrAllocateCaptureBuffer
0x180022ed3  nop     dword ptr [rax+rax+00h]
0x180022ed8  mov     rdi, rax
0x180022edb  test    rax, rax
0x180022ede  jnz     loc_1800232E4
0x180022ee4  mov     r15d, 0C0000017h
0x180022eea  cmp     cs:word_1803AC294, 1
0x180022ef2  jz      loc_180023356
0x180022ef8  mov     r15d, 1
0x180022efe  mov     rax, cs:gNlsProcessLocalCache
0x180022f05  mov     [rsp+500h+Handle], 0
0x180022f0e  test    rax, rax
0x180022f11  jz      loc_180023456
0x180022f17  mov     rax, cs:gNlsProcessLocalCache
0x180022f1e  mov     [rsp+500h+Handle], rax
0x180022f23  mov     rdi, [rsp+500h+Handle]
0x180022f28  lea     rcx, word_1803ABC18
0x180022f2f  mov     rdx, rdi
0x180022f32  mov     r8d, r15d
0x180022f35  call    NlsUpdateCacheInfo
0x180022f3a  cmp     cs:word_1803AC294, 3
0x180022f42  jnz     short loc_180022F58
0x180022f44  test    rdi, rdi
0x180022f47  jz      short loc_180022F58
0x180022f49  mov     rcx, rdi; Handle
0x180022f4c  call    cs:__imp_NtClose
0x180022f53  nop     dword ptr [rax+rax+00h]
0x180022f58  mov     eax, 0FFFFh
0x180022f5d  cmp     cs:word_1803ABC18, ax
0x180022f64  jz      loc_180023380
0x180022f6a  mov     rdi, cs:gpOneCustomHashNode
0x180022f71  lea     rcx, word_1803ABC1A
0x180022f78  xor     edx, edx
0x180022f7a  call    GetNamedLocaleHashNode
0x180022f7f  xchg    rax, cs:qword_1803ABC10
  ... truncated ...
```
