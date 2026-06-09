# CheckSpecialLocales

- ea: `0x180024ed0`
- end: `0x1800265e2`
- name: `CheckSpecialLocales`
- size: `5906`
- prototype: ``
- caller_count: `20`
- callee_count: `20`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001cd50`
- `0x18001e3e0`
- `0x1800202d0`
- `0x180020860`
- `0x180020b00`
- `0x180021ee0`
- `0x1800225d0`
- `0x180044780`
- `0x18004d080`
- `0x18004de60`
- `0x18004e490`
- `0x180066d50`
- `0x180078f70`
- `0x18007a6f0`
- `0x18007aa00`
- `0x1800b1e10`
- `0x1800b2920`
- `0x1800b35a0`
- `0x1800b6b10`
- `0x1800c1870`

## callees

- `0x18001cd34`
- `0x180024c80`
- `0x180024ed0`
- `0x1800265f0`
- `0x180028360`
- `0x180028490`
- `0x1800285f0`
- `0x180029ec0`
- `0x18002aabc`
- `0x1800486a0`
- `0x18004a310`
- `0x18004b2a0`
- `0x18004b408`
- `0x18004b9d0`
- `0x1801035c4`
- `0x18012c3ac`
- `0x1801369c9`
- `0x180142ba0`
- `0x180194eb9`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180026182`
- `ntdll!RtlInitUnicodeString` at `0x180026277`
- `ntdll!RtlInitUnicodeString` at `0x1800263e0`
- `ntdll!RtlInitUnicodeString` at `0x180026182`
- `ntdll!RtlInitUnicodeString` at `0x180026277`
- `ntdll!RtlInitUnicodeString` at `0x1800263e0`
- `ntdll!RtlEqualSid` at `0x180026555`
- `ntdll!RtlEqualSid` at `0x180026555`
- `ntdll!RtlSetLastWin32Error` at `0x180025f93`
- `ntdll!RtlSetLastWin32Error` at `0x180025f93`
- `ntdll!NtOpenKey` at `0x1800261c8`
- `ntdll!NtOpenKey` at `0x1800262bd`
- `ntdll!NtOpenKey` at `0x180026426`
- `ntdll!NtOpenKey` at `0x1800261c8`
- `ntdll!NtOpenKey` at `0x1800262bd`
- `ntdll!NtOpenKey` at `0x180026426`
- `ntdll!NtCreateEvent` at `0x180025f72`
- `ntdll!NtCreateEvent` at `0x180025f72`
- `ntdll!NtCreateKey` at `0x1800261fe`
- `ntdll!NtCreateKey` at `0x1800262f4`
- `ntdll!NtCreateKey` at `0x18002645c`
- `ntdll!NtCreateKey` at `0x1800261fe`
- `ntdll!NtCreateKey` at `0x1800262f4`
- `ntdll!NtCreateKey` at `0x18002645c`
- `ntdll!RtlLcidToLocaleName` at `0x180025ed3`
- `ntdll!RtlLcidToLocaleName` at `0x180025ed3`
- `ntdll!RtlOpenCurrentUser` at `0x1800256ff`
- `ntdll!RtlOpenCurrentUser` at `0x180025bb9`
- `ntdll!RtlOpenCurrentUser` at `0x180025cfb`
- `ntdll!RtlOpenCurrentUser` at `0x1800256ff`
- `ntdll!RtlOpenCurrentUser` at `0x180025bb9`
- `ntdll!RtlOpenCurrentUser` at `0x180025cfb`
- `ntdll!NtNotifyChangeKey` at `0x180025fee`
- `ntdll!NtNotifyChangeKey` at `0x180025fee`
- `ntdll!NtQueryInformationToken` at `0x180026387`
- `ntdll!NtQueryInformationToken` at `0x180026534`
- `ntdll!NtQueryInformationToken` at `0x180026387`
- `ntdll!NtQueryInformationToken` at `0x180026534`
- `ntdll!CsrClientCallServer` at `0x18002559c`
- `ntdll!CsrClientCallServer` at `0x180025afd`
- `ntdll!CsrClientCallServer` at `0x18002559c`
- `ntdll!CsrClientCallServer` at `0x180025afd`
- `ntdll!CsrCaptureMessageBuffer` at `0x180025576`
- `ntdll!CsrCaptureMessageBuffer` at `0x180025ad7`
- `ntdll!CsrCaptureMessageBuffer` at `0x180025576`
- `ntdll!CsrCaptureMessageBuffer` at `0x180025ad7`
- `ntdll!CsrFreeCaptureBuffer` at `0x1800255c8`
- `ntdll!CsrFreeCaptureBuffer` at `0x180025b2b`
- `ntdll!CsrFreeCaptureBuffer` at `0x1800255c8`
- `ntdll!CsrFreeCaptureBuffer` at `0x180025b2b`
- `ntdll!CsrAllocateCaptureBuffer` at `0x1800252b8`
- `ntdll!CsrAllocateCaptureBuffer` at `0x18002589b`
- `ntdll!CsrAllocateCaptureBuffer` at `0x1800252b8`
- `ntdll!CsrAllocateCaptureBuffer` at `0x18002589b`
- `ntdll!NtClose` at `0x18002532e`
- `ntdll!NtClose` at `0x180025794`
- `ntdll!NtClose` at `0x180025916`
- `ntdll!NtClose` at `0x180025c4f`
- `ntdll!NtClose` at `0x180025d8d`
- `ntdll!NtClose` at `0x180026216`
- `ntdll!NtClose` at `0x180026258`
- `ntdll!NtClose` at `0x18002630d`
- `ntdll!NtClose` at `0x180026351`
- `ntdll!NtClose` at `0x180026474`
- `ntdll!NtClose` at `0x1800264b6`
- `ntdll!NtClose` at `0x18002532e`
- `ntdll!NtClose` at `0x180025794`
- `ntdll!NtClose` at `0x180025916`
- `ntdll!NtClose` at `0x180025c4f`
- `ntdll!NtClose` at `0x180025d8d`
- `ntdll!NtClose` at `0x180026216`
- `ntdll!NtClose` at `0x180026258`
- `ntdll!NtClose` at `0x18002630d`
- `ntdll!NtClose` at `0x180026351`
- `ntdll!NtClose` at `0x180026474`
- `ntdll!NtClose` at `0x1800264b6`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180024f5b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002509a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002526e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800253ae`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180025851`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180025996`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180025f2d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180024f5b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002509a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002526e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800253ae`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180025851`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180025996`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180025f2d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180025047`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180025187`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180025499`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800254d0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180026001`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180025047`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180025187`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180025499`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800254d0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180026001`
- `ntdll!RtlFreeHeap` at `0x180026579`
- `ntdll!RtlFreeHeap` at `0x180026579`
- `ntdll!RtlAllocateHeap` at `0x1800260b8`
- `ntdll!RtlAllocateHeap` at `0x180026130`
- `ntdll!RtlAllocateHeap` at `0x1800264ff`
- `ntdll!RtlAllocateHeap` at `0x1800260b8`
- `ntdll!RtlAllocateHeap` at `0x180026130`
- `ntdll!RtlAllocateHeap` at `0x1800264ff`

## pseudocode

```c
_DWORD *__fastcall CheckSpecialLocales(__int64 a1)
{
  int v1; // ebx
  _DWORD *result; // rax
  DWORD v3; // ebx
  __int64 m; // rdx
  unsigned int *v5; // rax
  __int64 v6; // r8
  DWORD v7; // ebx
  _WORD *v8; // rcx
  __int64 TransientLocale; // rax
  DWORD v10; // edi
  __int64 i; // rdx
  unsigned int *WindowsLocaleData; // rax
  __int64 v13; // r8
  DWORD v14; // edi
  _WORD *v15; // rcx
  __int64 NamedLocaleHashNode; // rax
  HANDLE *v17; // rdi
  ULONG IsImpersonating; // ecx
  int v19; // ebx
  __int16 v20; // ax
  struct _CSR_CAPTURE_BUFFER *CaptureBuffer; // rax
  struct _CSR_CAPTURE_BUFFER *v22; // rbx
  NTSTATUS v23; // r13d
  HANDLE v24; // rbx
  __int64 v25; // rbx
  __int64 v26; // rax
  DWORD v27; // ebx
  __int64 j; // rdx
  unsigned int *v29; // rax
  __int64 v30; // r8
  DWORD v31; // ebx
  _WORD *v32; // rcx
  __int64 LocHashNodeFromSystemLocale; // rax
  __int64 v34; // rdx
  __int64 v35; // rdx
  __int64 v36; // rdx
  int GlobalizationUserModelType; // ecx
  NTSTATUS v38; // eax
  __int64 v39; // rcx
  WCHAR *v40; // rax
  __int64 v41; // rax
  __int64 v42; // rsi
  WCHAR *v43; // rcx
  const WCHAR *v44; // r14
  __int64 v45; // rbx
  WCHAR *v46; // rax
  HANDLE v47; // r12
  const WCHAR *v48; // r14
  __int64 v49; // rsi
  __int16 v50; // ax
  PCSR_CAPTURE_BUFFER v51; // rax
  struct _CSR_CAPTURE_BUFFER *v52; // r13
  NTSTATUS v53; // r13d
  HANDLE v54; // rbx
  __int64 v55; // rbx
  __int64 k; // rdx
  ULONG v57; // ecx
  HANDLE *NlsCache; // rsi
  int v59; // ecx
  NTSTATUS v60; // eax
  WCHAR *v61; // rax
  __int64 v62; // rcx
  __int64 v63; // rax
  WCHAR *v64; // r9
  __int64 v65; // rcx
  const WCHAR *v66; // rdx
  __int64 v67; // r8
  WCHAR *v68; // rax
  int v69; // ecx
  NTSTATUS v70; // eax
  WCHAR *v71; // rax
  __int64 v72; // rcx
  __int64 v73; // rax
  WCHAR *v74; // rcx
  __int64 v75; // rbx
  WCHAR *v76; // rax
  int v77; // ecx
  HANDLE *v78; // rsi
  int v79; // ecx
  NTSTATUS Event; // eax
  ULONG v81; // ecx
  HANDLE v82; // rax
  int v83; // ecx
  HANDLE *Heap; // rax
  HANDLE *v85; // rax
  NTSTATUS v86; // ebx
  HANDLE v87; // rcx
  void *v88; // rbx
  NTSTATUS v89; // r12d
  HANDLE v90; // rcx
  void *v91; // r12
  NTSTATUS v92; // ebx
  HANDLE v93; // rcx
  void *v94; // rbx
  PSID *v95; // rsi
  HANDLE Handle; // [rsp+50h] [rbp-B0h] BYREF
  ULONG Disposition; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE KeyHandle[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v99; // [rsp+70h] [rbp-90h]
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-88h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-78h] BYREF
  __int64 v102; // [rsp+B8h] [rbp-48h]
  WCHAR ApiMessage[32]; // [rsp+C0h] [rbp-40h] BYREF
  PVOID CapturedData; // [rsp+100h] [rbp+0h] BYREF
  int v105; // [rsp+108h] [rbp+8h]

  v1 = a1;
  if ( (_DWORD)a1 == 127 )
    return (_DWORD *)gpInvLocHashN;
  if ( (unsigned int)a1 > 0xC00 )
  {
    if ( (_DWORD)a1 == 4096 )
    {
      result = (_DWORD *)gpOneCustomHashNode;
      if ( gpOneCustomHashNode )
        return result;
    }
    else if ( (_DWORD)a1 != 5120 )
    {
      goto LABEL_26;
    }
    KeyHandle[0] = (HANDLE)11141120;
    KeyHandle[1] = ApiMessage;
    if ( (int)RtlLcidToLocaleName(a1, KeyHandle, 0, 0) >= 0 )
    {
      result = (_DWORD *)GetNamedLocaleHashNode(KeyHandle[1], 0);
      if ( result )
        return result;
    }
LABEL_26:
    result = (_DWORD *)gpSysLocHashN;
    if ( gpSysLocHashN || BasepIsSecureProcess )
    {
LABEL_43:
      if ( v1 != *result )
        return 0;
      return result;
    }
    RtlAcquireSRWLockExclusive(&gTblPtrsLock);
    if ( gpSysLocHashN )
      goto LABEL_42;
    v10 = gSystemLocale;
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
      goto LABEL_95;
    WindowsLocaleData = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
    if ( WindowsLocaleData )
    {
      if ( (_WORD)v10 != 127 )
      {
        v14 = HIWORD(v10);
        if ( (v14 & 0xF) == 0 )
        {
          v15 = (_WORD *)(qword_1803A6BD0 + 2 + 2LL * *WindowsLocaleData);
LABEL_38:
          NamedLocaleHashNode = MakeNamedLocaleHashNode(v15, 0);
          goto LABEL_39;
        }
        v34 = WindowsLocaleData[54];
        v15 = (_WORD *)qword_1803A6BD0;
        if ( (_DWORD)v34 )
          v15 = (_WORD *)(qword_1803A6BD0
                        + 2LL * *(unsigned int *)(qword_1803A6BD0 + 2 * (v34 + 2LL * (v14 & 0xF)) - 2)
                        + 2);
        if ( v15 && *v15 )
          goto LABEL_38;
LABEL_95:
        gpSysLocHashN = 0;
LABEL_40:
        gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
        if ( !gpSysLocHashN )
          gpSysLocHashN = gpInvLocHashN;
        goto LABEL_42;
      }
      NamedLocaleHashNode = MakeLocHashNodeFromSystemLocale(WindowsLocaleData, v10, v13, 0);
    }
    else
    {
      if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
        goto LABEL_95;
      NamedLocaleHashNode = GetTransientLocale(v10);
    }
LABEL_39:
    gpSysLocHashN = NamedLocaleHashNode;
    if ( !NamedLocaleHashNode )
      goto LABEL_40;
LABEL_42:
    RtlReleaseSRWLockExclusive(&gTblPtrsLock);
    result = (_DWORD *)gpSysLocHashN;
    goto LABEL_43;
  }
  if ( (_DWORD)a1 == 3072 || !(_DWORD)a1 || (_DWORD)a1 == 1024 )
  {
    v17 = 0;
    IsImpersonating = NtCurrentTeb()->IsImpersonating;
    if ( IsImpersonating )
    {
      v57 = IsImpersonating - 1;
      if ( v57 )
      {
        if ( v57 == 1 )
        {
          if ( BasepIsSecureProcess )
          {
            v17 = &gNlsProcessLocalCache;
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
                LODWORD(v17) = 1;
                *((_WORD *)Heap + 842) = 3;
                *((_WORD *)Heap + 843) = 1;
              }
              else
              {
                NlsCache = &gNlsProcessLocalCache;
              }
              NtCurrentTeb()->NlsCache = NlsCache;
            }
            if ( NlsCache != &gNlsProcessLocalCache && ((_DWORD)v17 || *((_WORD *)NlsCache + 843) == 1) )
            {
              *((_WORD *)NlsCache + 843) = 1;
              UpdateNlsInfoCache(NlsCache, 0);
            }
            v17 = NlsCache;
          }
        }
      }
      else
      {
        if ( BasepIsSecureProcess )
        {
          v78 = &gNlsProcessLocalCache;
        }
        else
        {
          v78 = (HANDLE *)NtCurrentTeb()->NlsCache;
          if ( !v78 )
          {
            v85 = (HANDLE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x698u);
            v78 = v85;
            if ( v85 )
            {
              *v85 = 0;
              v85[1] = 0;
              v85[2] = 0;
              *((_WORD *)v85 + 842) = 3;
              *((_WORD *)v85 + 843) = 1;
            }
            else
            {
              v78 = &gNlsProcessLocalCache;
            }
            NtCurrentTeb()->NlsCache = v78;
          }
          if ( v78 != &gNlsProcessLocalCache )
          {
            *((_WORD *)v78 + 843) = 1;
            UpdateNlsInfoCache(v78, 0);
          }
        }
        v17 = v78;
        NtCurrentTeb()->IsImpersonating = 2;
      }
      return v17[2];
    }
    v19 = gInteractiveLogonUserProcess;
    if ( gInteractiveLogonUserProcess == -1 )
    {
      Disposition = 0;
      v19 = 0;
      memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
      v102 = 0;
      if ( !BasepIsSecureProcess
        && NtQueryInformationToken(
             (HANDLE)0xFFFFFFFFFFFFFFFCLL,
             TokenStatistics,
             &ObjectAttributes,
             0x38u,
             &Disposition) >= 0 )
      {
        if ( *(HANDLE *)(gpServerNlsUserInfo + 1580) == ObjectAttributes.RootDirectory )
        {
          v19 = 1;
          gInteractiveLogonUserProcess = 1;
          word_1803AC294 = 1;
          goto LABEL_49;
        }
        v95 = (PSID *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x54u);
        if ( v95 )
        {
          if ( NtQueryInformationToken((HANDLE)0xFFFFFFFFFFFFFFFCLL, TokenUser, v95, 0x54u, &Disposition) >= 0 )
            v19 = RtlEqualSid(*v95, (PSID)(gpServerNlsUserInfo + 1588)) != 0;
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v95);
        }
      }
      gInteractiveLogonUserProcess = v19;
      if ( v19 )
        word_1803AC294 = 1;
      else
        word_1803AC294 = 20;
    }
LABEL_49:
    if ( v19 )
    {
      if ( dword_1803AC290 != *(_DWORD *)(gpServerNlsUserInfo + 1656) )
        word_1803AC296 = 1;
      if ( !word_1803AC296 )
        goto LABEL_89;
      v20 = word_1803AC294;
      if ( word_1803AC294 != 3 )
      {
        RtlAcquireSRWLockExclusive(&gNlsProcessCacheLock);
        v20 = word_1803AC294;
        if ( word_1803AC294 != 3 )
        {
          if ( !word_1803AC296 )
            goto LABEL_88;
          v20 = word_1803AC294;
        }
      }
      word_1803AC296 = 2;
      if ( v20 == 1 )
      {
        memset_0(ApiMessage, 0, 0x3B8u);
        CaptureBuffer = CsrAllocateCaptureBuffer(1u, 0x67Cu);
        v22 = CaptureBuffer;
        if ( CaptureBuffer )
        {
          CsrCaptureMessageBuffer(CaptureBuffer, 0, 0x67Cu, &CapturedData);
          v105 = 1660;
          v23 = CsrClientCallServer(ApiMessage, v22, (CSR_API_NUMBER)0x1001B, 0x10u);
          if ( v23 >= 0 )
            memcpy_0(&word_1803ABC18, CapturedData, 0x67Cu);
          CsrFreeCaptureBuffer(v22);
        }
        else
        {
          v23 = -1073741801;
        }
        if ( word_1803AC294 == 1 && v23 >= 0 )
          goto LABEL_64;
      }
      Handle = 0;
      if ( gNlsProcessLocalCache )
      {
        Handle = gNlsProcessLocalCache;
LABEL_61:
        v24 = Handle;
        NlsUpdateCacheInfo(&word_1803ABC18, Handle, 1);
        if ( word_1803AC294 == 3 && v24 )
          NtClose(v24);
LABEL_64:
        if ( word_1803ABC18 == -1 )
        {
          qword_1803ABC10 = 0;
          goto LABEL_69;
        }
        v25 = gpOneCustomHashNode;
        _InterlockedExchange64(&qword_1803ABC10, GetNamedLocaleHashNode(word_1803ABC1A, 0));
        if ( !v25 && gpOneCustomHashNode )
          gpOneCustomHashNode = 0;
        if ( !qword_1803ABC10 )
        {
LABEL_69:
          v26 = gpSysLocHashN;
          if ( gpSysLocHashN || BasepIsSecureProcess )
            goto LABEL_86;
          RtlAcquireSRWLockExclusive(&gTblPtrsLock);
          if ( gpSysLocHashN )
            goto LABEL_85;
          v27 = gSystemLocale;
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
            goto LABEL_85;
          if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
            goto LABEL_117;
          v29 = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
          if ( v29 )
          {
            if ( (_WORD)v27 != 127 )
            {
LABEL_79:
              v31 = HIWORD(v27);
              if ( (v31 & 0xF) == 0 )
              {
                v32 = (_WORD *)(qword_1803A6BD0 + 2 + 2LL * *v29);
LABEL_81:
                LocHashNodeFromSystemLocale = MakeNamedLocaleHashNode(v32, 0);
                goto LABEL_82;
              }
              v36 = v29[54];
              v32 = (_WORD *)qword_1803A6BD0;
              if ( (_DWORD)v36 )
                v32 = (_WORD *)(qword_1803A6BD0
                              + 2LL * *(unsigned int *)(qword_1803A6BD0 + 2 * (v36 + 2LL * (v31 & 0xF)) - 2)
                              + 2);
              if ( v32 && *v32 )
                goto LABEL_81;
LABEL_117:
              gpSysLocHashN = 0;
LABEL_83:
              gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
              if ( !gpSysLocHashN )
                gpSysLocHashN = gpInvLocHashN;
              goto LABEL_85;
            }
            goto LABEL_169;
          }
          goto LABEL_207;
        }
LABEL_87:
        _InterlockedCompareExchange16(&word_1803AC296, 0, 2);
        if ( word_1803AC294 == 3 )
        {
LABEL_89:
          v17 = &gNlsProcessLocalCache;
          return v17[2];
        }
LABEL_88:
        RtlReleaseSRWLockExclusive(&gNlsProcessCacheLock);
        goto LABEL_89;
      }
      KeyHandle[0] = 0;
      Disposition = 0;
      memset(&ObjectAttributes, 0, 44);
      DestinationString = 0;
      GlobalizationUserModelType = GetGlobalizationUserModelType();
      if ( GlobalizationUserModelType == 1 )
      {
        v38 = RtlOpenCurrentUser(0x2000000u, KeyHandle);
      }
      else
      {
        v77 = GlobalizationUserModelType - 2;
        if ( v77 )
        {
          if ( v77 != 1 )
          {
LABEL_135:
            SetLastError_0(0x3F1u);
            goto LABEL_61;
          }
          v99 = 0;
          v38 = OpenGlobalizationUserSettingsKey_ForMua(0x2000000u, 0, KeyHandle);
        }
        else
        {
          v38 = OpenGlobalizationUserSettingsKey_ForSingleUserModel(0x2000000u, KeyHandle);
        }
      }
      if ( v38 >= 0 )
      {
        ApiMessage[0] = 0;
        v39 = 512;
        v40 = ApiMessage;
        do
        {
          if ( !*v40 )
            break;
          ++v40;
          --v39;
        }
        while ( v39 );
        v41 = 512 - v39;
        if ( !v39 )
          goto LABEL_133;
        v42 = 2147483646;
        v43 = &ApiMessage[v41];
        v44 = L"Control Panel\\International";
        v45 = 512 - v41;
        if ( 512 != v41 )
        {
          do
          {
            if ( !v42 )
              break;
            if ( !*v44 )
              break;
            *v43++ = *v44++;
            --v42;
            --v45;
          }
          while ( v45 );
        }
        v46 = v43 - 1;
        if ( v45 )
          v46 = v43;
        *v46 = 0;
        if ( v45 )
        {
          RtlInitUnicodeString(&DestinationString, ApiMessage);
          ObjectAttributes.RootDirectory = KeyHandle[0];
          ObjectAttributes.Length = 48;
          ObjectAttributes.ObjectName = &DestinationString;
          ObjectAttributes.Attributes = 64;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          Disposition = 0;
          v86 = NtOpenKey(&Handle, 0x20019u, &ObjectAttributes);
          if ( v86 < 0 )
            v86 = NtCreateKey(&Handle, 0x20019u, &ObjectAttributes, 0, 0, 0, &Disposition);
          if ( KeyHandle[0] )
            NtClose(KeyHandle[0]);
          if ( v86 >= 0 )
          {
            v87 = Handle;
          }
          else
          {
            v87 = 0;
            Handle = 0;
          }
          if ( v86 >= 0 )
          {
            v88 = (void *)_InterlockedCompareExchange64(
                            (volatile signed __int64 *)&gNlsProcessLocalCache,
                            (signed __int64)v87,
                            0);
            if ( v88 )
            {
              if ( Handle )
                NtClose(Handle);
              Handle = v88;
            }
            goto LABEL_61;
          }
        }
        else
        {
LABEL_133:
          if ( KeyHandle[0] )
            NtClose(KeyHandle[0]);
        }
      }
      goto LABEL_135;
    }
    v47 = gNlsProcessLocalCache;
    if ( BasepIsSecureProcess )
      goto LABEL_89;
    v48 = L"Control Panel\\International";
    v49 = 2147483646;
    if ( gNlsProcessLocalCache )
    {
LABEL_140:
      if ( !::Event || !WaitForSingleObjectEx(::Event, 0, 0) )
      {
        word_1803AC296 = 1;
        RtlAcquireSRWLockExclusive(&gNlsProcessCacheLock);
        if ( !::Event )
        {
          KeyHandle[0] = 0;
          memset(&ObjectAttributes, 0, 44);
          DestinationString = 0;
          Event = NtCreateEvent(KeyHandle, 0x1F0003u, 0, SynchronizationEvent, 0);
          if ( Event < 0 )
          {
            BaseSetLastNTError((unsigned int)Event);
            v82 = 0;
          }
          else
          {
            if ( Event == 0x40000000 )
              v81 = 183;
            else
              v81 = 0;
            RtlSetLastWin32Error(v81);
            v82 = KeyHandle[0];
          }
          ::Event = v82;
        }
        if ( ::Event )
          NtNotifyChangeKey(v47, ::Event, 0, 0, &IoStatusRegChange, 0x10000005u, 1u, 0, 0, 1u);
        RtlReleaseSRWLockExclusive(&gNlsProcessCacheLock);
      }
LABEL_142:
      if ( !word_1803AC296 )
        goto LABEL_89;
      v50 = word_1803AC294;
      if ( word_1803AC294 != 3 )
      {
        RtlAcquireSRWLockExclusive(&gNlsProcessCacheLock);
        v50 = word_1803AC294;
        if ( word_1803AC294 != 3 )
        {
          if ( !word_1803AC296 )
            goto LABEL_88;
          v50 = word_1803AC294;
        }
      }
      word_1803AC296 = 2;
      if ( v50 == 1 )
      {
        memset_0(ApiMessage, 0, 0x3B8u);
        v51 = CsrAllocateCaptureBuffer(1u, 0x67Cu);
        KeyHandle[0] = v51;
        v52 = v51;
        if ( v51 )
        {
          CsrCaptureMessageBuffer(v51, 0, 0x67Cu, &CapturedData);
          v105 = 1660;
          v53 = CsrClientCallServer(ApiMessage, v52, (CSR_API_NUMBER)0x1001B, 0x10u);
          if ( v53 >= 0 )
            memcpy_0(&word_1803ABC18, CapturedData, 0x67Cu);
          CsrFreeCaptureBuffer((PCSR_CAPTURE_BUFFER)KeyHandle[0]);
        }
        else
        {
          v53 = -1073741801;
        }
        if ( word_1803AC294 == 1 && v53 >= 0 )
        {
LABEL_154:
          if ( word_1803ABC18 == -1 )
          {
            qword_1803ABC10 = 0;
          }
          else
          {
            v55 = gpOneCustomHashNode;
            _InterlockedExchange64(&qword_1803ABC10, GetNamedLocaleHashNode(word_1803ABC1A, 0));
            if ( !v55 && gpOneCustomHashNode )
              gpOneCustomHashNode = 0;
            if ( qword_1803ABC10 )
              goto LABEL_87;
          }
          v26 = gpSysLocHashN;
          if ( gpSysLocHashN || BasepIsSecureProcess )
            goto LABEL_86;
          RtlAcquireSRWLockExclusive(&gTblPtrsLock);
          if ( gpSysLocHashN )
            goto LABEL_85;
          v27 = gSystemLocale;
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
            goto LABEL_85;
          if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
            goto LABEL_117;
          v29 = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
          if ( v29 )
          {
            if ( (_WORD)v27 != 127 )
              goto LABEL_79;
LABEL_169:
            LocHashNodeFromSystemLocale = MakeLocHashNodeFromSystemLocale(v29, v27, v30, 0);
            goto LABEL_82;
          }
LABEL_207:
          if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
            goto LABEL_117;
          if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
            || (unsigned int)CreateTransientLocales() )
          {
            LocHashNodeFromSystemLocale = FindLocaleHashNode(v27);
          }
          else
          {
            LocHashNodeFromSystemLocale = 0;
          }
LABEL_82:
          gpSysLocHashN = LocHashNodeFromSystemLocale;
          if ( !LocHashNodeFromSystemLocale )
            goto LABEL_83;
LABEL_85:
          RtlReleaseSRWLockExclusive(&gTblPtrsLock);
          v26 = gpSysLocHashN;
LABEL_86:
          qword_1803ABC10 = v26;
          goto LABEL_87;
        }
      }
      Handle = 0;
      if ( gNlsProcessLocalCache )
      {
        Handle = gNlsProcessLocalCache;
LABEL_151:
        v54 = Handle;
        NlsUpdateCacheInfo(&word_1803ABC18, Handle, 1);
        if ( word_1803AC294 == 3 && v54 )
          NtClose(v54);
        goto LABEL_154;
      }
      KeyHandle[0] = 0;
      Disposition = 0;
      memset(&ObjectAttributes, 0, 44);
      DestinationString = 0;
      v69 = GetGlobalizationUserModelType();
      if ( v69 == 1 )
      {
        v70 = RtlOpenCurrentUser(0x2000000u, KeyHandle);
      }
      else
      {
        v83 = v69 - 2;
        if ( v83 )
        {
          if ( v83 != 1 )
          {
LABEL_229:
            SetLastError_0(0x3F1u);
            goto LABEL_151;
          }
          v99 = 0;
          v70 = OpenGlobalizationUserSettingsKey_ForMua(0x2000000u, 0, KeyHandle);
        }
        else
        {
          v70 = OpenGlobalizationUserSettingsKey_ForSingleUserModel(0x2000000u, KeyHandle);
        }
      }
      if ( v70 >= 0 )
      {
        ApiMessage[0] = 0;
        v71 = ApiMessage;
        v72 = 512;
        do
        {
          if ( !*v71 )
            break;
          ++v71;
          --v72;
        }
        while ( v72 );
        v73 = 512 - v72;
        if ( !v72 )
          goto LABEL_227;
        v74 = &ApiMessage[v73];
        v75 = 512 - v73;
        if ( 512 != v73 )
        {
          do
          {
            if ( !v49 )
              break;
            if ( !*v48 )
              break;
            *v74++ = *v48++;
            --v49;
            --v75;
          }
          while ( v75 );
        }
        v76 = v74 - 1;
        if ( v75 )
          v76 = v74;
        *v76 = 0;
        if ( v75 )
        {
          RtlInitUnicodeString(&DestinationString, ApiMessage);
          ObjectAttributes.RootDirectory = KeyHandle[0];
          ObjectAttributes.Length = 48;
          ObjectAttributes.ObjectName = &DestinationString;
          ObjectAttributes.Attributes = 64;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          Disposition = 0;
          v92 = NtOpenKey(&Handle, 0x20019u, &ObjectAttributes);
          if ( v92 < 0 )
            v92 = NtCreateKey(&Handle, 0x20019u, &ObjectAttributes, 0, 0, 0, &Disposition);
          if ( KeyHandle[0] )
            NtClose(KeyHandle[0]);
          if ( v92 >= 0 )
          {
            v93 = Handle;
          }
          else
          {
            v93 = 0;
            Handle = 0;
          }
          if ( v92 >= 0 )
          {
            v94 = (void *)_InterlockedCompareExchange64(
                            (volatile signed __int64 *)&gNlsProcessLocalCache,
                            (signed __int64)v93,
                            0);
            if ( v94 )
            {
              if ( Handle )
                NtClose(Handle);
              Handle = v94;
            }
            goto LABEL_151;
          }
        }
        else
        {
LABEL_227:
          if ( KeyHandle[0] )
            NtClose(KeyHandle[0]);
        }
      }
      goto LABEL_229;
    }
    Handle = 0;
    KeyHandle[0] = 0;
    Disposition = 0;
    memset(&ObjectAttributes, 0, 44);
    DestinationString = 0;
    v59 = GetGlobalizationUserModelType();
    if ( v59 == 1 )
    {
      v60 = RtlOpenCurrentUser(0x2000000u, KeyHandle);
    }
    else
    {
      v79 = v59 - 2;
      if ( v79 )
      {
        if ( v79 != 1 )
          goto LABEL_206;
        v99 = 0;
        v60 = OpenGlobalizationUserSettingsKey_ForMua(0x2000000u, 0, KeyHandle);
      }
      else
      {
        v60 = OpenGlobalizationUserSettingsKey_ForSingleUserModel(0x2000000u, KeyHandle);
      }
    }
    if ( v60 >= 0 )
    {
      ApiMessage[0] = 0;
      v61 = ApiMessage;
      v62 = 512;
      do
      {
        if ( !*v61 )
          break;
        ++v61;
        --v62;
      }
      while ( v62 );
      v63 = 512 - v62;
      if ( !v62 )
        goto LABEL_204;
      v64 = &ApiMessage[v63];
      v65 = 2147483646;
      v66 = L"Control Panel\\International";
      v67 = 512 - v63;
      if ( v63 != 512 )
      {
        do
        {
          if ( !v65 )
            break;
          if ( !*v66 )
            break;
          *v64++ = *v66++;
          --v65;
          --v67;
        }
        while ( v67 );
      }
      v68 = v64 - 1;
      if ( v67 )
        v68 = v64;
      *v68 = 0;
      if ( v67 )
      {
        RtlInitUnicodeString(&DestinationString, ApiMessage);
        ObjectAttributes.RootDirectory = KeyHandle[0];
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        Disposition = 0;
        v89 = NtOpenKey(&Handle, 0x20019u, &ObjectAttributes);
        if ( v89 < 0 )
          v89 = NtCreateKey(&Handle, 0x20019u, &ObjectAttributes, 0, 0, 0, &Disposition);
        if ( KeyHandle[0] )
          NtClose(KeyHandle[0]);
        if ( v89 >= 0 )
        {
          v90 = Handle;
        }
        else
        {
          v90 = 0;
          Handle = 0;
        }
        if ( v89 >= 0 )
        {
          v91 = (void *)_InterlockedCompareExchange64(
                          (volatile signed __int64 *)&gNlsProcessLocalCache,
                          (signed __int64)v90,
                          0);
          if ( v91 )
          {
            if ( Handle )
              NtClose(Handle);
            Handle = v91;
          }
LABEL_139:
          v47 = Handle;
          if ( !Handle )
            goto LABEL_142;
          goto LABEL_140;
        }
      }
      else
      {
LABEL_204:
        if ( KeyHandle[0] )
          NtClose(KeyHandle[0]);
      }
    }
LABEL_206:
    SetLastError_0(0x3F1u);
    goto LABEL_139;
  }
  if ( (_DWORD)a1 != 2048 )
    goto LABEL_26;
  result = (_DWORD *)gpSysLocHashN;
  if ( !gpSysLocHashN && !BasepIsSecureProcess )
  {
    RtlAcquireSRWLockExclusive(&gTblPtrsLock);
    if ( gpSysLocHashN )
      goto LABEL_23;
    v3 = gSystemLocale;
    for ( m = *((_QWORD *)P
              + (((unsigned __int8)gSystemLocale
                ^ (unsigned __int8)((gSystemLocale ^ ((unsigned __int64)gSystemLocale >> 7)) >> 7))
               & 0x7F)); m; m = *(_QWORD *)(m + 88) )
    {
      if ( *(_DWORD *)m == gSystemLocale )
        break;
    }
    gpSysLocHashN = m;
    if ( m )
      goto LABEL_23;
    if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
      goto LABEL_112;
    v5 = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
    if ( v5 )
    {
      if ( (_WORD)v3 != 127 )
      {
        v7 = HIWORD(v3);
        if ( (v7 & 0xF) == 0 )
        {
          v8 = (_WORD *)(qword_1803A6BD0 + 2 + 2LL * *v5);
LABEL_19:
          TransientLocale = MakeNamedLocaleHashNode(v8, 0);
          goto LABEL_20;
        }
        v35 = v5[54];
        v8 = (_WORD *)qword_1803A6BD0;
        if ( (_DWORD)v35 )
          v8 = (_WORD *)(qword_1803A6BD0
                       + 2LL * *(unsigned int *)(qword_1803A6BD0 + 2 * (v35 + 2LL * (v7 & 0xF)) - 2)
                       + 2);
        if ( v8 && *v8 )
          goto LABEL_19;
LABEL_112:
        gpSysLocHashN = 0;
        goto LABEL_21;
      }
      TransientLocale = MakeLocHashNodeFromSystemLocale(v5, v3, v6, 0);
    }
    else
    {
      if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
        goto LABEL_112;
      TransientLocale = GetTransientLocale(v3);
    }
LABEL_20:
    gpSysLocHashN = TransientLocale;
    if ( TransientLocale )
    {
LABEL_23:
      RtlReleaseSRWLockExclusive(&gTblPtrsLock);
      return (_DWORD *)gpSysLocHashN;
    }
LABEL_21:
    gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
    if ( !gpSysLocHashN )
      gpSysLocHashN = gpInvLocHashN;
    goto LABEL_23;
  }
  return result;
}

```

## disassembly

```asm
0x180024ed0  push    rbp
0x180024ed2  push    rbx
0x180024ed3  lea     rbp, [rsp-3E8h]
0x180024edb  sub     rsp, 4E8h
0x180024ee2  mov     rax, cs:__security_cookie
0x180024ee9  xor     rax, rsp
0x180024eec  mov     [rbp+3F0h+var_30], rax
0x180024ef3  mov     ebx, ecx
0x180024ef5  cmp     ecx, 7Fh
0x180024ef8  jz      loc_1800251C4
0x180024efe  mov     [rsp+4F0h+arg_10], rdi
0x180024f06  cmp     ecx, 0C00h
0x180024f0c  ja      loc_18002505F
0x180024f12  jz      loc_1800251CD
0x180024f18  test    ecx, ecx
0x180024f1a  jz      loc_1800251CD
0x180024f20  cmp     ecx, 400h
0x180024f26  jz      loc_1800251CD
0x180024f2c  cmp     ecx, 800h
0x180024f32  jnz     loc_180025077
0x180024f38  mov     rax, cs:gpSysLocHashN
0x180024f3f  test    rax, rax
0x180024f42  jnz     loc_1800251A2
0x180024f48  cmp     cs:BasepIsSecureProcess, al
0x180024f4e  jnz     loc_1800251A2
0x180024f54  lea     rcx, gTblPtrsLock
0x180024f5b  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180024f62  nop     dword ptr [rax+rax+00h]
0x180024f67  cmp     cs:gpSysLocHashN, 0
0x180024f6f  jnz     loc_180025040
0x180024f75  mov     ebx, cs:gSystemLocale
0x180024f7b  mov     rax, cs:P
0x180024f82  mov     ecx, ebx
0x180024f84  shr     rcx, 7
0x180024f88  xor     rcx, rbx
0x180024f8b  shr     rcx, 7
0x180024f8f  xor     rcx, rbx
0x180024f92  and     ecx, 7Fh
0x180024f95  mov     rdx, [rax+rcx*8]
0x180024f99  test    rdx, rdx
0x180024f9c  jz      short loc_180024FA6
0x180024f9e  cmp     [rdx], ebx
0x180024fa0  jnz     loc_180025A9D
0x180024fa6  mov     cs:gpSysLocHashN, rdx
0x180024fad  test    rdx, rdx
0x180024fb0  jnz     loc_180025040
0x180024fb6  test    ebx, 0FFF00000h
0x180024fbc  jnz     loc_18002565B
0x180024fc2  cmp     cs:BasepIsSecureProcess, dl
0x180024fc8  jnz     loc_18002565B
0x180024fce  mov     ecx, ebx
0x180024fd0  call    GetWindowsLocaleData
0x180024fd5  test    rax, rax
0x180024fd8  jz      loc_180025AAF
0x180024fde  cmp     bx, 7Fh
0x180024fe2  jz      loc_180025CA2
0x180024fe8  shr     ebx, 10h
0x180024feb  test    bl, 0Fh
0x180024fee  jnz     loc_180025628
0x180024ff4  mov     ecx, [rax]
0x180024ff6  mov     rax, cs:qword_1803A6BD0
0x180024ffd  add     rax, 2
0x180025001  lea     rcx, [rax+rcx*2]
0x180025005  xor     edx, edx
0x180025007  call    MakeNamedLocaleHashNode
0x18002500c  mov     cs:gpSysLocHashN, rax
0x180025013  test    rax, rax
0x180025016  jnz     short loc_180025040
0x180025018  xor     edx, edx
0x18002501a  lea     rcx, aEnUs; "en-US"
0x180025021  call    MakeNamedLocaleHashNode
0x180025026  mov     cs:gpSysLocHashN, rax
0x18002502d  test    rax, rax
0x180025030  jnz     short loc_180025040
0x180025032  mov     rax, cs:gpInvLocHashN
0x180025039  mov     cs:gpSysLocHashN, rax
0x180025040  lea     rcx, gTblPtrsLock
0x180025047  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002504e  nop     dword ptr [rax+rax+00h]
0x180025053  mov     rax, cs:gpSysLocHashN
0x18002505a  jmp     loc_1800251A2
0x18002505f  cmp     ebx, 1000h
0x180025065  jz      loc_180025E9D
0x18002506b  cmp     ebx, 1400h
0x180025071  jz      loc_180025EAD
0x180025077  mov     rax, cs:gpSysLocHashN
0x18002507e  test    rax, rax
0x180025081  jnz     loc_18002519A
0x180025087  cmp     cs:BasepIsSecureProcess, al
0x18002508d  jnz     loc_18002519A
0x180025093  lea     rcx, gTblPtrsLock
0x18002509a  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800250a1  nop     dword ptr [rax+rax+00h]
0x1800250a6  cmp     cs:gpSysLocHashN, 0
0x1800250ae  jnz     loc_180025180
0x1800250b4  mov     edi, cs:gSystemLocale
0x1800250ba  mov     rax, cs:P
0x1800250c1  mov     ecx, edi
0x1800250c3  shr     rcx, 7
0x1800250c7  xor     rcx, rdi
0x1800250ca  shr     rcx, 7
0x1800250ce  xor     rcx, rdi
0x1800250d1  and     ecx, 7Fh
0x1800250d4  mov     rdx, [rax+rcx*8]
0x1800250d8  test    rdx, rdx
0x1800250db  jz      short loc_1800250E5
0x1800250dd  cmp     [rdx], edi
0x1800250df  jnz     loc_180025555
0x1800250e5  mov     cs:gpSysLocHashN, rdx
0x1800250ec  test    rdx, rdx
0x1800250ef  jnz     loc_180025180
0x1800250f5  test    edi, 0FFF00000h
0x1800250fb  jnz     loc_180025547
0x180025101  cmp     cs:BasepIsSecureProcess, dl
0x180025107  jnz     loc_180025547
0x18002510d  mov     ecx, edi
0x18002510f  call    GetWindowsLocaleData
0x180025114  test    rax, rax
0x180025117  jz      loc_18002560F
0x18002511d  cmp     di, 7Fh
0x180025121  jz      loc_1800256A6
0x180025127  shr     edi, 10h
0x18002512a  test    dil, 0Fh
0x18002512e  jnz     loc_180025514
0x180025134  mov     ecx, [rax]
0x180025136  mov     rax, cs:qword_1803A6BD0
0x18002513d  add     rax, 2
0x180025141  lea     rcx, [rax+rcx*2]
0x180025145  xor     edx, edx
0x180025147  call    MakeNamedLocaleHashNode
0x18002514c  mov     cs:gpSysLocHashN, rax
0x180025153  test    rax, rax
0x180025156  jnz     short loc_180025180
0x180025158  xor     edx, edx
0x18002515a  lea     rcx, aEnUs; "en-US"
0x180025161  call    MakeNamedLocaleHashNode
0x180025166  mov     cs:gpSysLocHashN, rax
0x18002516d  test    rax, rax
0x180025170  jnz     short loc_180025180
0x180025172  mov     rax, cs:gpInvLocHashN
0x180025179  mov     cs:gpSysLocHashN, rax
0x180025180  lea     rcx, gTblPtrsLock
0x180025187  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002518e  nop     dword ptr [rax+rax+00h]
0x180025193  mov     rax, cs:gpSysLocHashN
0x18002519a  cmp     ebx, [rax]
0x18002519c  jnz     loc_180025E84
0x1800251a2  mov     rdi, [rsp+4F0h+arg_10]
0x1800251aa  mov     rcx, [rbp+3F0h+var_30]
0x1800251b1  xor     rcx, rsp; StackCookie
0x1800251b4  call    __security_check_cookie
0x1800251b9  add     rsp, 4E8h
0x1800251c0  pop     rbx
0x1800251c1  pop     rbp
0x1800251c2  retn
0x1800251c4  mov     rax, cs:gpInvLocHashN
0x1800251cb  jmp     short loc_1800251AA
0x1800251cd  mov     rax, gs:30h
0x1800251d6  xor     edi, edi
0x1800251d8  mov     [rsp+4F0h+arg_8], rsi
0x1800251e0  mov     [rsp+4F0h+arg_18], r12
0x1800251e8  mov     [rsp+4F0h+var_20], r15
0x1800251f0  mov     ecx, [rax+179Ch]
0x1800251f6  test    ecx, ecx
0x1800251f8  jnz     loc_180025A35
0x1800251fe  mov     ebx, cs:gInteractiveLogonUserProcess
0x180025204  mov     r15d, 1
0x18002520a  cmp     ebx, 0FFFFFFFFh
0x18002520d  jz      loc_180025DA8
0x180025213  mov     [rsp+4F0h+var_10], r13
0x18002521b  mov     [rsp+4F0h+var_18], r14
0x180025223  test    ebx, ebx
0x180025225  jz      loc_1800257AF
0x18002522b  mov     ecx, cs:dword_1803AC290
0x180025231  mov     rax, cs:gpServerNlsUserInfo
0x180025238  mov     eax, [rax+678h]
0x18002523e  cmp     ecx, eax
0x180025240  jz      short loc_18002524A
0x180025242  mov     cs:word_1803AC296, r15w
0x18002524a  movzx   eax, cs:word_1803AC296
0x180025251  test    ax, ax
0x180025254  jz      loc_1800254DC
0x18002525a  movzx   eax, cs:word_1803AC294
0x180025261  cmp     ax, 3
0x180025265  jz      short loc_18002528B
0x180025267  lea     rcx, gNlsProcessCacheLock
0x18002526e  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180025275  nop     dword ptr [rax+rax+00h]
0x18002527a  movzx   eax, cs:word_1803AC294
0x180025281  cmp     ax, 3
0x180025285  jnz     loc_1800255E7
0x18002528b  mov     r12d, 2
0x180025291  mov     cs:word_1803AC296, r12w
0x180025299  cmp     ax, r15w
0x18002529d  jnz     short loc_1800252E4
0x18002529f  xor     edx, edx; Val
0x1800252a1  lea     rcx, [rbp+3F0h+ApiMessage]; void *
0x1800252a5  mov     r8d, 3B8h; Size
0x1800252ab  call    memset_0
0x1800252b0  mov     edx, 67Ch; BufferSize
0x1800252b5  mov     ecx, r15d; ArgumentCount
0x1800252b8  call    cs:__imp_CsrAllocateCaptureBuffer
0x1800252bf  nop     dword ptr [rax+rax+00h]
0x1800252c4  mov     rbx, rax
0x1800252c7  test    rax, rax
0x1800252ca  jnz     loc_180025567
0x1800252d0  mov     r13d, 0C0000017h
0x1800252d6  cmp     cs:word_1803AC294, r15w
0x1800252de  jz      loc_1800255D9
0x1800252e4  mov     rax, cs:gNlsProcessLocalCache
0x1800252eb  mov     [rsp+4F0h+Handle], rdi
0x1800252f0  test    rax, rax
0x1800252f3  jz      loc_1800256B8
0x1800252f9  mov     rax, cs:gNlsProcessLocalCache
0x180025300  mov     [rsp+4F0h+Handle], rax
0x180025305  mov     rbx, [rsp+4F0h+Handle]
0x18002530a  lea     rcx, word_1803ABC18
0x180025311  mov     rdx, rbx
0x180025314  mov     r8d, r15d
0x180025317  call    NlsUpdateCacheInfo
0x18002531c  cmp     cs:word_1803AC294, 3
0x180025324  jnz     short loc_18002533A
0x180025326  test    rbx, rbx
0x180025329  jz      short loc_18002533A
0x18002532b  mov     rcx, rbx; Handle
0x18002532e  call    cs:__imp_NtClose
0x180025335  nop     dword ptr [rax+rax+00h]
0x18002533a  mov     eax, 0FFFFh
0x18002533f  cmp     cs:word_1803ABC18, ax
0x180025346  jz      loc_180025603
0x18002534c  mov     rbx, cs:gpOneCustomHashNode
0x180025353  lea     rcx, word_1803ABC1A
0x18002535a  xor     edx, edx
0x18002535c  call    GetNamedLocaleHashNode
0x180025361  xchg    rax, cs:qword_1803ABC10
0x180025368  test    rbx, rbx
0x18002536b  jnz     short loc_18002537D
0x18002536d  cmp     cs:gpOneCustomHashNode, rdi
0x180025374  jz      short loc_18002537D
0x180025376  mov     cs:gpOneCustomHashNode, rdi
0x18002537d  cmp     cs:qword_1803ABC10, rdi
0x180025384  jnz     loc_1800254B3
0x18002538a  mov     rax, cs:gpSysLocHashN
0x180025391  test    rax, rax
0x180025394  jnz     loc_1800254AC
0x18002539a  cmp     cs:BasepIsSecureProcess, dil
0x1800253a1  jnz     loc_1800254AC
0x1800253a7  lea     rcx, gTblPtrsLock
0x1800253ae  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800253b5  nop     dword ptr [rax+rax+00h]
0x1800253ba  cmp     cs:gpSysLocHashN, rdi
0x1800253c1  jnz     loc_180025492
0x1800253c7  mov     ebx, cs:gSystemLocale
0x1800253cd  mov     rax, cs:P
0x1800253d4  mov     ecx, ebx
0x1800253d6  shr     rcx, 7
0x1800253da  xor     rcx, rbx
0x1800253dd  shr     rcx, 7
0x1800253e1  xor     rcx, rbx
0x1800253e4  and     ecx, 7Fh
0x1800253e7  mov     rdx, [rax+rcx*8]
0x1800253eb  test    rdx, rdx
0x1800253ee  jz      short loc_1800253F8
0x1800253f0  cmp     [rdx], ebx
0x1800253f2  jnz     loc_180025C90
0x1800253f8  mov     cs:gpSysLocHashN, rdx
0x1800253ff  test    rdx, rdx
0x180025402  jnz     loc_180025492
0x180025408  test    ebx, 0FFF00000h
0x18002540e  jnz     loc_18002569A
0x180025414  cmp     cs:BasepIsSecureProcess, dil
0x18002541b  jnz     loc_18002569A
0x180025421  mov     ecx, ebx
0x180025423  call    GetWindowsLocaleData
0x180025428  test    rax, rax
0x18002542b  jz      loc_180025C6A
0x180025431  cmp     bx, 7Fh
0x180025435  jz      loc_180025A23
0x18002543b  shr     ebx, 10h
0x18002543e  test    bl, 0Fh
0x180025441  jnz     loc_180025669
0x180025447  mov     ecx, [rax]
0x180025449  mov     rax, cs:qword_1803A6BD0
0x180025450  add     rax, r12
0x180025453  lea     rcx, [rax+rcx*2]
0x180025457  xor     edx, edx
0x180025459  call    MakeNamedLocaleHashNode
0x18002545e  mov     cs:gpSysLocHashN, rax
0x180025465  test    rax, rax
0x180025468  jnz     short loc_180025492
0x18002546a  xor     edx, edx
0x18002546c  lea     rcx, aEnUs; "en-US"
0x180025473  call    MakeNamedLocaleHashNode
0x180025478  mov     cs:gpSysLocHashN, rax
0x18002547f  test    rax, rax
0x180025482  jnz     short loc_180025492
0x180025484  mov     rax, cs:gpInvLocHashN
0x18002548b  mov     cs:gpSysLocHashN, rax
0x180025492  lea     rcx, gTblPtrsLock
0x180025499  call    cs:__imp_RtlReleaseSRWLockExclusive
  ... truncated ...
```
