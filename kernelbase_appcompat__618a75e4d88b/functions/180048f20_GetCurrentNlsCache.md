# GetCurrentNlsCache

- ea: `0x180048f20`
- end: `0x18004a2ff`
- name: `GetCurrentNlsCache`
- size: `5087`
- prototype: ``
- caller_count: `53`
- callee_count: `19`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001cd50`
- `0x18001e3e0`
- `0x1800202d0`
- `0x180020860`
- `0x180020b00`
- `0x180021b10`
- `0x180021ee0`
- `0x1800225d0`
- `0x180022a60`
- `0x180023c10`
- `0x180027400`
- `0x180028630`
- `0x180029770`
- `0x18002b040`
- `0x18002bce0`
- `0x180034120`
- `0x180044780`
- `0x1800486a0`
- `0x180048920`
- `0x18004d080`
- `0x18004de60`
- `0x18004e490`
- `0x180066d50`
- `0x180076ef8`
- `0x180078590`
- `0x180078f70`
- `0x180079900`
- `0x18007a660`
- `0x18007a6f0`
- `0x18007aa00`
- `0x18007ab80`
- `0x180085d40`
- `0x180086700`
- `0x1800877d0`
- `0x180096e80`
- `0x180097030`
- `0x1800af910`
- `0x1800afb1c`
- `0x1800b08d4`
- `0x1800b1170`
- `0x1800b1e10`
- `0x1800b35a0`
- `0x1800b6b10`
- `0x1800bbbc0`
- `0x1800c1870`
- `0x1800c56d8`
- `0x1800c59f0`
- `0x1800cb510`
- `0x1800e76f0`
- `0x1800e9f44`

## callees

- `0x18001cd34`
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
- `0x18004b2a0`
- `0x18004b408`
- `0x18004b9d0`
- `0x18012c3ac`
- `0x1801369c9`
- `0x180142ba0`
- `0x180194eb9`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180049e8f`
- `ntdll!RtlInitUnicodeString` at `0x180049f89`
- `ntdll!RtlInitUnicodeString` at `0x18004a0f8`
- `ntdll!RtlInitUnicodeString` at `0x180049e8f`
- `ntdll!RtlInitUnicodeString` at `0x180049f89`
- `ntdll!RtlInitUnicodeString` at `0x18004a0f8`
- `ntdll!RtlEqualSid` at `0x18004a272`
- `ntdll!RtlEqualSid` at `0x18004a272`
- `ntdll!RtlSetLastWin32Error` at `0x180049c90`
- `ntdll!RtlSetLastWin32Error` at `0x180049c90`
- `ntdll!NtOpenKey` at `0x180049ed8`
- `ntdll!NtOpenKey` at `0x180049fd2`
- `ntdll!NtOpenKey` at `0x18004a141`
- `ntdll!NtOpenKey` at `0x180049ed8`
- `ntdll!NtOpenKey` at `0x180049fd2`
- `ntdll!NtOpenKey` at `0x18004a141`
- `ntdll!NtCreateEvent` at `0x180049c6f`
- `ntdll!NtCreateEvent` at `0x180049c6f`
- `ntdll!NtCreateKey` at `0x180049f10`
- `ntdll!NtCreateKey` at `0x18004a00b`
- `ntdll!NtCreateKey` at `0x18004a179`
- `ntdll!NtCreateKey` at `0x180049f10`
- `ntdll!NtCreateKey` at `0x18004a00b`
- `ntdll!NtCreateKey` at `0x18004a179`
- `ntdll!RtlOpenCurrentUser` at `0x180049374`
- `ntdll!RtlOpenCurrentUser` at `0x180049849`
- `ntdll!RtlOpenCurrentUser` at `0x180049988`
- `ntdll!RtlOpenCurrentUser` at `0x180049374`
- `ntdll!RtlOpenCurrentUser` at `0x180049849`
- `ntdll!RtlOpenCurrentUser` at `0x180049988`
- `ntdll!NtNotifyChangeKey` at `0x180049cec`
- `ntdll!NtNotifyChangeKey` at `0x180049cec`
- `ntdll!NtQueryInformationToken` at `0x18004a09f`
- `ntdll!NtQueryInformationToken` at `0x18004a251`
- `ntdll!NtQueryInformationToken` at `0x18004a09f`
- `ntdll!NtQueryInformationToken` at `0x18004a251`
- `ntdll!CsrClientCallServer` at `0x1800492ba`
- `ntdll!CsrClientCallServer` at `0x18004978d`
- `ntdll!CsrClientCallServer` at `0x1800492ba`
- `ntdll!CsrClientCallServer` at `0x18004978d`
- `ntdll!CsrCaptureMessageBuffer` at `0x180049294`
- `ntdll!CsrCaptureMessageBuffer` at `0x180049767`
- `ntdll!CsrCaptureMessageBuffer` at `0x180049294`
- `ntdll!CsrCaptureMessageBuffer` at `0x180049767`
- `ntdll!CsrFreeCaptureBuffer` at `0x1800492e6`
- `ntdll!CsrFreeCaptureBuffer` at `0x1800497bb`
- `ntdll!CsrFreeCaptureBuffer` at `0x1800492e6`
- `ntdll!CsrFreeCaptureBuffer` at `0x1800497bb`
- `ntdll!CsrAllocateCaptureBuffer` at `0x180049021`
- `ntdll!CsrAllocateCaptureBuffer` at `0x180049552`
- `ntdll!CsrAllocateCaptureBuffer` at `0x180049021`
- `ntdll!CsrAllocateCaptureBuffer` at `0x180049552`
- `ntdll!NtClose` at `0x180049097`
- `ntdll!NtClose` at `0x18004940d`
- `ntdll!NtClose` at `0x1800495cd`
- `ntdll!NtClose` at `0x1800498e5`
- `ntdll!NtClose` at `0x180049a0f`
- `ntdll!NtClose` at `0x180049f28`
- `ntdll!NtClose` at `0x180049f6a`
- `ntdll!NtClose` at `0x18004a024`
- `ntdll!NtClose` at `0x18004a068`
- `ntdll!NtClose` at `0x18004a191`
- `ntdll!NtClose` at `0x18004a1d3`
- `ntdll!NtClose` at `0x180049097`
- `ntdll!NtClose` at `0x18004940d`
- `ntdll!NtClose` at `0x1800495cd`
- `ntdll!NtClose` at `0x1800498e5`
- `ntdll!NtClose` at `0x180049a0f`
- `ntdll!NtClose` at `0x180049f28`
- `ntdll!NtClose` at `0x180049f6a`
- `ntdll!NtClose` at `0x18004a024`
- `ntdll!NtClose` at `0x18004a068`
- `ntdll!NtClose` at `0x18004a191`
- `ntdll!NtClose` at `0x18004a1d3`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180048fd7`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180049117`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180049508`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18004964d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180049c29`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180048fd7`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180049117`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180049508`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18004964d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180049c29`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180049202`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18004923a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180049cff`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180049202`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18004923a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180049cff`
- `ntdll!RtlFreeHeap` at `0x18004a296`
- `ntdll!RtlFreeHeap` at `0x18004a296`
- `ntdll!RtlAllocateHeap` at `0x180049dc5`
- `ntdll!RtlAllocateHeap` at `0x180049e3d`
- `ntdll!RtlAllocateHeap` at `0x18004a21c`
- `ntdll!RtlAllocateHeap` at `0x180049dc5`
- `ntdll!RtlAllocateHeap` at `0x180049e3d`
- `ntdll!RtlAllocateHeap` at `0x18004a21c`

## pseudocode

```c
HANDLE *GetCurrentNlsCache()
{
  int v0; // r14d
  ULONG IsImpersonating; // ecx
  int v2; // ebx
  __int16 v3; // ax
  struct _CSR_CAPTURE_BUFFER *CaptureBuffer; // rax
  struct _CSR_CAPTURE_BUFFER *v5; // rbx
  NTSTATUS v6; // r15d
  HANDLE v7; // rbx
  __int64 v8; // rbx
  __int64 v9; // rax
  DWORD v10; // ebx
  __int64 i; // rdx
  unsigned int *WindowsLocaleData; // rax
  __int64 v13; // r8
  DWORD v14; // ebx
  _WORD *v15; // rcx
  __int64 NamedLocaleHashNode; // rax
  HANDLE *result; // rax
  int GlobalizationUserModelType; // eax
  NTSTATUS v19; // eax
  __int64 v20; // rcx
  WCHAR *v21; // rax
  __int64 v22; // rax
  __int64 v23; // rbx
  WCHAR *v24; // rcx
  const WCHAR *v25; // rsi
  __int64 v26; // rdi
  WCHAR *v27; // rax
  __int64 v28; // rdx
  HANDLE v29; // r15
  const WCHAR *v30; // rsi
  __int64 v31; // rbx
  __int16 v32; // ax
  PCSR_CAPTURE_BUFFER v33; // rax
  struct _CSR_CAPTURE_BUFFER *v34; // r15
  NTSTATUS v35; // r15d
  HANDLE v36; // rbx
  __int64 v37; // rbx
  DWORD v38; // ebx
  __int64 j; // rdx
  unsigned int *v40; // rax
  __int64 v41; // r8
  DWORD v42; // ebx
  _WORD *v43; // rcx
  __int64 LocHashNodeFromSystemLocale; // rax
  ULONG v45; // ecx
  int v46; // eax
  NTSTATUS v47; // eax
  WCHAR *v48; // rax
  __int64 v49; // rcx
  __int64 v50; // rax
  WCHAR *v51; // r9
  __int64 v52; // rdx
  const WCHAR *v53; // r8
  WCHAR *v54; // rax
  int v55; // eax
  NTSTATUS v56; // eax
  WCHAR *v57; // rax
  __int64 v58; // rcx
  __int64 v59; // rax
  WCHAR *v60; // rcx
  __int64 v61; // rdi
  WCHAR *v62; // rax
  __int64 v63; // rdx
  HANDLE *NlsCache; // rdi
  int v65; // eax
  HANDLE *v66; // rdi
  int v67; // eax
  NTSTATUS v68; // eax
  ULONG v69; // ecx
  HANDLE v70; // rax
  int v71; // eax
  HANDLE *v72; // rax
  HANDLE *v73; // rax
  NTSTATUS v74; // ebx
  HANDLE v75; // rcx
  void *v76; // rbx
  NTSTATUS v77; // r15d
  HANDLE v78; // rcx
  void *v79; // r15
  NTSTATUS v80; // ebx
  HANDLE v81; // rcx
  void *v82; // rbx
  PSID *Heap; // rdi
  HANDLE Handle; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE KeyHandle; // [rsp+58h] [rbp-A8h] BYREF
  ULONG Disposition; // [rsp+60h] [rbp-A0h] BYREF
  int v87; // [rsp+64h] [rbp-9Ch]
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-88h] BYREF
  __int64 v90; // [rsp+A8h] [rbp-58h]
  WCHAR ApiMessage[32]; // [rsp+B0h] [rbp-50h] BYREF
  PVOID CapturedData; // [rsp+F0h] [rbp-10h] BYREF
  int v93; // [rsp+F8h] [rbp-8h]

  v0 = 0;
  IsImpersonating = NtCurrentTeb()->IsImpersonating;
  if ( !IsImpersonating )
  {
    v2 = gInteractiveLogonUserProcess;
    if ( gInteractiveLogonUserProcess != -1 )
      goto LABEL_3;
    Disposition = 0;
    v2 = 0;
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    v90 = 0;
    if ( !BasepIsSecureProcess
      && NtQueryInformationToken((HANDLE)0xFFFFFFFFFFFFFFFCLL, TokenStatistics, &ObjectAttributes, 0x38u, &Disposition) >= 0 )
    {
      if ( *(HANDLE *)(gpServerNlsUserInfo + 1580) == ObjectAttributes.RootDirectory )
      {
        v2 = 1;
        gInteractiveLogonUserProcess = 1;
        word_1803AC294 = 1;
        goto LABEL_3;
      }
      Heap = (PSID *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x54u);
      if ( Heap )
      {
        if ( NtQueryInformationToken((HANDLE)0xFFFFFFFFFFFFFFFCLL, TokenUser, Heap, 0x54u, &Disposition) >= 0 )
          v2 = RtlEqualSid(*Heap, (PSID)(gpServerNlsUserInfo + 1588)) != 0;
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      }
    }
    gInteractiveLogonUserProcess = v2;
    if ( v2 )
      word_1803AC294 = 1;
    else
      word_1803AC294 = 20;
LABEL_3:
    if ( v2 )
    {
      if ( dword_1803AC290 != *(_DWORD *)(gpServerNlsUserInfo + 1656) )
        word_1803AC296 = 1;
      if ( !word_1803AC296 )
        return &gNlsProcessLocalCache;
      v3 = word_1803AC294;
      if ( word_1803AC294 != 3 )
      {
        RtlAcquireSRWLockExclusive(&gNlsProcessCacheLock);
        v3 = word_1803AC294;
        if ( word_1803AC294 != 3 )
        {
          if ( !word_1803AC296 )
            goto LABEL_42;
          v3 = word_1803AC294;
        }
      }
      word_1803AC296 = 2;
      if ( v3 == 1 )
      {
        memset_0(ApiMessage, 0, 0x3B8u);
        CaptureBuffer = CsrAllocateCaptureBuffer(1u, 0x67Cu);
        v5 = CaptureBuffer;
        if ( CaptureBuffer )
        {
          CsrCaptureMessageBuffer(CaptureBuffer, 0, 0x67Cu, &CapturedData);
          v93 = 1660;
          v6 = CsrClientCallServer(ApiMessage, v5, (CSR_API_NUMBER)0x1001B, 0x10u);
          if ( v6 >= 0 )
            memcpy_0(&word_1803ABC18, CapturedData, 0x67Cu);
          CsrFreeCaptureBuffer(v5);
        }
        else
        {
          v6 = -1073741801;
        }
        if ( word_1803AC294 == 1 && v6 >= 0 )
          goto LABEL_18;
      }
      Handle = 0;
      if ( gNlsProcessLocalCache )
      {
        Handle = gNlsProcessLocalCache;
LABEL_15:
        v7 = Handle;
        NlsUpdateCacheInfo(&word_1803ABC18, Handle, 1);
        if ( word_1803AC294 == 3 && v7 )
          NtClose(v7);
LABEL_18:
        if ( word_1803ABC18 == -1 )
        {
          qword_1803ABC10 = 0;
          goto LABEL_23;
        }
        v8 = gpOneCustomHashNode;
        _InterlockedExchange64(&qword_1803ABC10, GetNamedLocaleHashNode(word_1803ABC1A, 0));
        if ( !v8 && gpOneCustomHashNode )
          gpOneCustomHashNode = 0;
        if ( !qword_1803ABC10 )
        {
LABEL_23:
          v9 = gpSysLocHashN;
          if ( gpSysLocHashN || BasepIsSecureProcess )
            goto LABEL_40;
          RtlAcquireSRWLockExclusive(&gTblPtrsLock);
          if ( gpSysLocHashN )
            goto LABEL_39;
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
            goto LABEL_39;
          if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
            goto LABEL_73;
          WindowsLocaleData = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
          if ( WindowsLocaleData )
          {
            if ( (_WORD)v10 != 127 )
            {
              v14 = HIWORD(v10);
              if ( (v14 & 0xF) == 0 )
              {
                v15 = (_WORD *)(qword_1803A6BD0 + 2 + 2LL * *WindowsLocaleData);
LABEL_35:
                NamedLocaleHashNode = MakeNamedLocaleHashNode(v15, 0);
                goto LABEL_36;
              }
              v28 = WindowsLocaleData[54];
              v15 = (_WORD *)qword_1803A6BD0;
              if ( (_DWORD)v28 )
                v15 = (_WORD *)(qword_1803A6BD0
                              + 2LL * *(unsigned int *)(qword_1803A6BD0 + 2 * (v28 + 2LL * (v14 & 0xF)) - 2)
                              + 2);
              if ( v15 && *v15 )
                goto LABEL_35;
LABEL_73:
              gpSysLocHashN = 0;
LABEL_37:
              gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
              if ( !gpSysLocHashN )
                gpSysLocHashN = gpInvLocHashN;
              goto LABEL_39;
            }
            NamedLocaleHashNode = MakeLocHashNodeFromSystemLocale(WindowsLocaleData, v10, v13, 0);
          }
          else
          {
            if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
              goto LABEL_73;
            if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
              || (unsigned int)CreateTransientLocales() )
            {
              NamedLocaleHashNode = FindLocaleHashNode(v10);
            }
            else
            {
              NamedLocaleHashNode = 0;
            }
          }
LABEL_36:
          gpSysLocHashN = NamedLocaleHashNode;
          if ( !NamedLocaleHashNode )
            goto LABEL_37;
LABEL_39:
          RtlReleaseSRWLockExclusive(&gTblPtrsLock);
          v9 = gpSysLocHashN;
LABEL_40:
          qword_1803ABC10 = v9;
        }
LABEL_41:
        _InterlockedCompareExchange16(&word_1803AC296, 0, 2);
        if ( word_1803AC294 == 3 )
          return &gNlsProcessLocalCache;
LABEL_42:
        RtlReleaseSRWLockExclusive(&gNlsProcessCacheLock);
        return &gNlsProcessLocalCache;
      }
      KeyHandle = 0;
      Disposition = 0;
      memset(&ObjectAttributes, 0, 44);
      DestinationString = 0;
      GlobalizationUserModelType = GetGlobalizationUserModelType();
      if ( GlobalizationUserModelType == 1 )
      {
        v19 = RtlOpenCurrentUser(0x2000000u, &KeyHandle);
      }
      else
      {
        v65 = GlobalizationUserModelType - 2;
        if ( v65 )
        {
          if ( v65 != 1 )
          {
LABEL_68:
            SetLastError_0(0x3F1u);
            goto LABEL_15;
          }
          v87 = 0;
          v19 = OpenGlobalizationUserSettingsKey_ForMua(0x2000000u, 0, &KeyHandle);
        }
        else
        {
          v19 = OpenGlobalizationUserSettingsKey_ForSingleUserModel(0x2000000u, &KeyHandle);
        }
      }
      if ( v19 >= 0 )
      {
        ApiMessage[0] = 0;
        v20 = 512;
        v21 = ApiMessage;
        do
        {
          if ( !*v21 )
            break;
          ++v21;
          --v20;
        }
        while ( v20 );
        v22 = 512 - v20;
        if ( !v20 )
          goto LABEL_66;
        v23 = 2147483646;
        v24 = &ApiMessage[v22];
        v25 = L"Control Panel\\International";
        v26 = 512 - v22;
        if ( 512 != v22 )
        {
          do
          {
            if ( !v23 )
              break;
            if ( !*v25 )
              break;
            *v24++ = *v25++;
            --v23;
            --v26;
          }
          while ( v26 );
        }
        v27 = v24 - 1;
        if ( v26 )
          v27 = v24;
        *v27 = 0;
        if ( v26 )
        {
          RtlInitUnicodeString(&DestinationString, ApiMessage);
          ObjectAttributes.RootDirectory = KeyHandle;
          ObjectAttributes.Length = 48;
          ObjectAttributes.ObjectName = &DestinationString;
          ObjectAttributes.Attributes = 64;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          Disposition = 0;
          v74 = NtOpenKey(&Handle, 0x20019u, &ObjectAttributes);
          if ( v74 < 0 )
            v74 = NtCreateKey(&Handle, 0x20019u, &ObjectAttributes, 0, 0, 0, &Disposition);
          if ( KeyHandle )
            NtClose(KeyHandle);
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
            goto LABEL_15;
          }
        }
        else
        {
LABEL_66:
          if ( KeyHandle )
            NtClose(KeyHandle);
        }
      }
      goto LABEL_68;
    }
    v29 = gNlsProcessLocalCache;
    if ( BasepIsSecureProcess )
      return &gNlsProcessLocalCache;
    v30 = L"Control Panel\\International";
    v31 = 2147483646;
    if ( gNlsProcessLocalCache )
    {
LABEL_78:
      if ( !Event || !WaitForSingleObjectEx(Event, 0, 0) )
      {
        word_1803AC296 = 1;
        RtlAcquireSRWLockExclusive(&gNlsProcessCacheLock);
        if ( !Event )
        {
          KeyHandle = 0;
          memset(&ObjectAttributes, 0, 44);
          DestinationString = 0;
          v68 = NtCreateEvent(&KeyHandle, 0x1F0003u, 0, SynchronizationEvent, 0);
          if ( v68 < 0 )
          {
            BaseSetLastNTError((unsigned int)v68);
            v70 = 0;
          }
          else
          {
            if ( v68 == 0x40000000 )
              v69 = 183;
            else
              v69 = 0;
            RtlSetLastWin32Error(v69);
            v70 = KeyHandle;
          }
          Event = v70;
        }
        if ( Event )
          NtNotifyChangeKey(v29, Event, 0, 0, &IoStatusRegChange, 0x10000005u, 1u, 0, 0, 1u);
        RtlReleaseSRWLockExclusive(&gNlsProcessCacheLock);
      }
LABEL_80:
      if ( !word_1803AC296 )
        return &gNlsProcessLocalCache;
      v32 = word_1803AC294;
      if ( word_1803AC294 != 3 )
      {
        RtlAcquireSRWLockExclusive(&gNlsProcessCacheLock);
        v32 = word_1803AC294;
        if ( word_1803AC294 != 3 )
        {
          if ( !word_1803AC296 )
            goto LABEL_42;
          v32 = word_1803AC294;
        }
      }
      word_1803AC296 = 2;
      if ( v32 == 1 )
      {
        memset_0(ApiMessage, 0, 0x3B8u);
        v33 = CsrAllocateCaptureBuffer(1u, 0x67Cu);
        KeyHandle = v33;
        v34 = v33;
        if ( v33 )
        {
          CsrCaptureMessageBuffer(v33, 0, 0x67Cu, &CapturedData);
          v93 = 1660;
          v35 = CsrClientCallServer(ApiMessage, v34, (CSR_API_NUMBER)0x1001B, 0x10u);
          if ( v35 >= 0 )
            memcpy_0(&word_1803ABC18, CapturedData, 0x67Cu);
          CsrFreeCaptureBuffer((PCSR_CAPTURE_BUFFER)KeyHandle);
        }
        else
        {
          v35 = -1073741801;
        }
        if ( word_1803AC294 == 1 && v35 >= 0 )
        {
LABEL_92:
          if ( word_1803ABC18 == -1 )
          {
            qword_1803ABC10 = 0;
          }
          else
          {
            v37 = gpOneCustomHashNode;
            _InterlockedExchange64(&qword_1803ABC10, GetNamedLocaleHashNode(word_1803ABC1A, 0));
            if ( !v37 && gpOneCustomHashNode )
              gpOneCustomHashNode = 0;
            if ( qword_1803ABC10 )
              goto LABEL_41;
          }
          v9 = gpSysLocHashN;
          if ( gpSysLocHashN || BasepIsSecureProcess )
            goto LABEL_40;
          RtlAcquireSRWLockExclusive(&gTblPtrsLock);
          if ( gpSysLocHashN )
            goto LABEL_39;
          v38 = gSystemLocale;
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
            goto LABEL_39;
          if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
            goto LABEL_168;
          v40 = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
          if ( v40 )
          {
            if ( (_WORD)v38 != 127 )
            {
              v42 = HIWORD(v38);
              if ( (v42 & 0xF) == 0 )
              {
                v43 = (_WORD *)(qword_1803A6BD0 + 2 + 2LL * *v40);
LABEL_109:
                LocHashNodeFromSystemLocale = MakeNamedLocaleHashNode(v43, 0);
                goto LABEL_110;
              }
              v63 = v40[54];
              v43 = (_WORD *)qword_1803A6BD0;
              if ( (_DWORD)v63 )
                v43 = (_WORD *)(qword_1803A6BD0
                              + 2LL * *(unsigned int *)(qword_1803A6BD0 + 2 * (v63 + 2LL * (v42 & 0xF)) - 2)
                              + 2);
              if ( v43 && *v43 )
                goto LABEL_109;
LABEL_168:
              gpSysLocHashN = 0;
              goto LABEL_111;
            }
            LocHashNodeFromSystemLocale = MakeLocHashNodeFromSystemLocale(v40, v38, v41, 0);
          }
          else
          {
            if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
              goto LABEL_168;
            if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
              || (unsigned int)CreateTransientLocales() )
            {
              LocHashNodeFromSystemLocale = FindLocaleHashNode(v38);
            }
            else
            {
              LocHashNodeFromSystemLocale = 0;
            }
          }
LABEL_110:
          gpSysLocHashN = LocHashNodeFromSystemLocale;
          if ( LocHashNodeFromSystemLocale )
            goto LABEL_39;
LABEL_111:
          gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
          if ( !gpSysLocHashN )
            gpSysLocHashN = gpInvLocHashN;
          goto LABEL_39;
        }
      }
      Handle = 0;
      if ( gNlsProcessLocalCache )
      {
        Handle = gNlsProcessLocalCache;
LABEL_89:
        v36 = Handle;
        NlsUpdateCacheInfo(&word_1803ABC18, Handle, 1);
        if ( word_1803AC294 == 3 && v36 )
          NtClose(v36);
        goto LABEL_92;
      }
      KeyHandle = 0;
      Disposition = 0;
      memset(&ObjectAttributes, 0, 44);
      DestinationString = 0;
      v55 = GetGlobalizationUserModelType();
      if ( v55 == 1 )
      {
        v56 = RtlOpenCurrentUser(0x2000000u, &KeyHandle);
      }
      else
      {
        v71 = v55 - 2;
        if ( v71 )
        {
          if ( v71 != 1 )
          {
LABEL_163:
            SetLastError_0(0x3F1u);
            goto LABEL_89;
          }
          v87 = 0;
          v56 = OpenGlobalizationUserSettingsKey_ForMua(0x2000000u, 0, &KeyHandle);
        }
        else
        {
          v56 = OpenGlobalizationUserSettingsKey_ForSingleUserModel(0x2000000u, &KeyHandle);
        }
      }
      if ( v56 >= 0 )
      {
        ApiMessage[0] = 0;
        v57 = ApiMessage;
        v58 = 512;
        do
        {
          if ( !*v57 )
            break;
          ++v57;
          --v58;
        }
        while ( v58 );
        v59 = 512 - v58;
        if ( !v58 )
          goto LABEL_161;
        v60 = &ApiMessage[v59];
        v61 = 512 - v59;
        if ( 512 != v59 )
        {
          do
          {
            if ( !v31 )
              break;
            if ( !*v30 )
              break;
            *v60++ = *v30++;
            --v31;
            --v61;
          }
          while ( v61 );
        }
        v62 = v60 - 1;
        if ( v61 )
          v62 = v60;
        *v62 = 0;
        if ( v61 )
        {
          RtlInitUnicodeString(&DestinationString, ApiMessage);
          ObjectAttributes.RootDirectory = KeyHandle;
          ObjectAttributes.Length = 48;
          ObjectAttributes.ObjectName = &DestinationString;
          ObjectAttributes.Attributes = 64;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          Disposition = 0;
          v80 = NtOpenKey(&Handle, 0x20019u, &ObjectAttributes);
          if ( v80 < 0 )
            v80 = NtCreateKey(&Handle, 0x20019u, &ObjectAttributes, 0, 0, 0, &Disposition);
          if ( KeyHandle )
            NtClose(KeyHandle);
          if ( v80 >= 0 )
          {
            v81 = Handle;
          }
          else
          {
            v81 = 0;
            Handle = 0;
          }
          if ( v80 >= 0 )
          {
            v82 = (void *)_InterlockedCompareExchange64(
                            (volatile signed __int64 *)&gNlsProcessLocalCache,
                            (signed __int64)v81,
                            0);
            if ( v82 )
            {
              if ( Handle )
                NtClose(Handle);
              Handle = v82;
            }
            goto LABEL_89;
          }
        }
        else
        {
LABEL_161:
          if ( KeyHandle )
            NtClose(KeyHandle);
        }
      }
      goto LABEL_163;
    }
    Handle = 0;
    KeyHandle = 0;
    Disposition = 0;
    memset(&ObjectAttributes, 0, 44);
    DestinationString = 0;
    v46 = GetGlobalizationUserModelType();
    if ( v46 == 1 )
    {
      v47 = RtlOpenCurrentUser(0x2000000u, &KeyHandle);
    }
    else
    {
      v67 = v46 - 2;
      if ( v67 )
      {
        if ( v67 != 1 )
          goto LABEL_140;
        v87 = 0;
        v47 = OpenGlobalizationUserSettingsKey_ForMua(0x2000000u, 0, &KeyHandle);
      }
      else
      {
        v47 = OpenGlobalizationUserSettingsKey_ForSingleUserModel(0x2000000u, &KeyHandle);
      }
    }
    if ( v47 >= 0 )
    {
      ApiMessage[0] = 0;
      v48 = ApiMessage;
      v49 = 512;
      do
      {
        if ( !*v48 )
          break;
        ++v48;
        --v49;
      }
      while ( v49 );
      v50 = 512 - v49;
      if ( !v49 )
        goto LABEL_138;
      v51 = &ApiMessage[v50];
      v52 = 2147483646;
      v53 = L"Control Panel\\International";
      if ( v50 != 512 )
      {
        do
        {
          if ( !v52 )
            break;
          if ( !*v53 )
            break;
          *v51++ = *v53++;
          --v52;
          --v49;
        }
        while ( v49 );
      }
      v54 = v51 - 1;
      if ( v49 )
        v54 = v51;
      *v54 = 0;
      if ( v49 )
      {
        RtlInitUnicodeString(&DestinationString, ApiMessage);
        ObjectAttributes.RootDirectory = KeyHandle;
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        Disposition = 0;
        v77 = NtOpenKey(&Handle, 0x20019u, &ObjectAttributes);
        if ( v77 < 0 )
          v77 = NtCreateKey(&Handle, 0x20019u, &ObjectAttributes, 0, 0, 0, &Disposition);
        if ( KeyHandle )
          NtClose(KeyHandle);
        if ( v77 >= 0 )
        {
          v78 = Handle;
        }
        else
        {
          v78 = 0;
          Handle = 0;
        }
        if ( v77 >= 0 )
        {
          v79 = (void *)_InterlockedCompareExchange64(
                          (volatile signed __int64 *)&gNlsProcessLocalCache,
                          (signed __int64)v78,
                          0);
          if ( v79 )
          {
            if ( Handle )
              NtClose(Handle);
            Handle = v79;
          }
LABEL_77:
          v29 = Handle;
          if ( !Handle )
            goto LABEL_80;
          goto LABEL_78;
        }
      }
      else
      {
LABEL_138:
        if ( KeyHandle )
          NtClose(KeyHandle);
      }
    }
LABEL_140:
    SetLastError_0(0x3F1u);
    goto LABEL_77;
  }
  v45 = IsImpersonating - 1;
  if ( v45 )
  {
    if ( v45 == 1 )
    {
      if ( BasepIsSecureProcess )
      {
        return &gNlsProcessLocalCache;
      }
      else
      {
        NlsCache = (HANDLE *)NtCurrentTeb()->NlsCache;
        if ( !NlsCache )
        {
          v72 = (HANDLE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x698u);
          NlsCache = v72;
          if ( v72 )
          {
            *v72 = 0;
            v72[1] = 0;
            v72[2] = 0;
            v0 = 1;
            *((_WORD *)v72 + 842) = 3;
            *((_WORD *)v72 + 843) = 1;
          }
          else
          {
            NlsCache = &gNlsProcessLocalCache;
          }
          NtCurrentTeb()->NlsCache = NlsCache;
        }
        if ( NlsCache != &gNlsProcessLocalCache && (v0 || *((_WORD *)NlsCache + 843) == 1) )
        {
          *((_WORD *)NlsCache + 843) = 1;
          UpdateNlsInfoCache(NlsCache, 0);
        }
        return NlsCache;
      }
    }
    else
    {
      return 0;
    }
  }
  else
  {
    if ( BasepIsSecureProcess )
    {
      v66 = &gNlsProcessLocalCache;
    }
    else
    {
      v66 = (HANDLE *)NtCurrentTeb()->NlsCache;
      if ( !v66 )
      {
        v73 = (HANDLE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x698u);
        v66 = v73;
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
          v66 = &gNlsProcessLocalCache;
        }
        NtCurrentTeb()->NlsCache = v66;
      }
      if ( v66 != &gNlsProcessLocalCache )
      {
        *((_WORD *)v66 + 843) = 1;
        UpdateNlsInfoCache(v66, 0);
      }
    }
    result = v66;
    NtCurrentTeb()->IsImpersonating = 2;
  }
  return result;
}

```

## disassembly

```asm
0x180048f20  mov     [rsp-8+arg_10], rbx
0x180048f25  push    rbp
0x180048f26  push    rdi
0x180048f27  push    r12
0x180048f29  push    r13
0x180048f2b  push    r14
0x180048f2d  lea     rbp, [rsp-3C0h]
0x180048f35  sub     rsp, 4C0h
0x180048f3c  mov     rax, cs:__security_cookie
0x180048f43  xor     rax, rsp
0x180048f46  mov     [rbp+3E0h+var_30], rax
0x180048f4d  mov     rax, gs:30h
0x180048f56  xor     r14d, r14d
0x180048f59  mov     ecx, [rax+179Ch]
0x180048f5f  test    ecx, ecx
0x180048f61  jnz     loc_18004973E
0x180048f67  mov     ebx, cs:gInteractiveLogonUserProcess
0x180048f6d  mov     r12d, 1
0x180048f73  cmp     ebx, 0FFFFFFFFh
0x180048f76  jz      loc_180049A68
0x180048f7c  mov     [rsp+4E0h+arg_0], rsi
0x180048f84  mov     [rsp+4E0h+arg_8], r15
0x180048f8c  test    ebx, ebx
0x180048f8e  jz      loc_180049466
0x180048f94  mov     ecx, cs:dword_1803AC290
0x180048f9a  mov     rax, cs:gpServerNlsUserInfo
0x180048fa1  mov     eax, [rax+678h]
0x180048fa7  cmp     ecx, eax
0x180048fa9  jz      short loc_180048FB3
0x180048fab  mov     cs:word_1803AC296, r12w
0x180048fb3  movzx   eax, cs:word_1803AC296
0x180048fba  test    ax, ax
0x180048fbd  jz      loc_180049246
0x180048fc3  movzx   eax, cs:word_1803AC294
0x180048fca  cmp     ax, 3
0x180048fce  jz      short loc_180048FF4
0x180048fd0  lea     rcx, gNlsProcessCacheLock
0x180048fd7  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180048fde  nop     dword ptr [rax+rax+00h]
0x180048fe3  movzx   eax, cs:word_1803AC294
0x180048fea  cmp     ax, 3
0x180048fee  jnz     loc_180049305
0x180048ff4  mov     r13d, 2
0x180048ffa  mov     cs:word_1803AC296, r13w
0x180049002  cmp     ax, r12w
0x180049006  jnz     short loc_18004904D
0x180049008  xor     edx, edx; Val
0x18004900a  lea     rcx, [rbp+3E0h+ApiMessage]; void *
0x18004900e  mov     r8d, 3B8h; Size
0x180049014  call    memset_0
0x180049019  mov     edx, 67Ch; BufferSize
0x18004901e  mov     ecx, r12d; ArgumentCount
0x180049021  call    cs:__imp_CsrAllocateCaptureBuffer
0x180049028  nop     dword ptr [rax+rax+00h]
0x18004902d  mov     rbx, rax
0x180049030  test    rax, rax
0x180049033  jnz     loc_180049285
0x180049039  mov     r15d, 0C0000017h
0x18004903f  cmp     cs:word_1803AC294, r12w
0x180049047  jz      loc_1800492F7
0x18004904d  mov     rax, cs:gNlsProcessLocalCache
0x180049054  mov     [rsp+4E0h+Handle], r14
0x180049059  test    rax, rax
0x18004905c  jz      loc_18004932D
0x180049062  mov     rax, cs:gNlsProcessLocalCache
0x180049069  mov     [rsp+4E0h+Handle], rax
0x18004906e  mov     rbx, [rsp+4E0h+Handle]
0x180049073  lea     rcx, word_1803ABC18
0x18004907a  mov     rdx, rbx
0x18004907d  mov     r8d, r12d
0x180049080  call    NlsUpdateCacheInfo
0x180049085  cmp     cs:word_1803AC294, 3
0x18004908d  jnz     short loc_1800490A3
0x18004908f  test    rbx, rbx
0x180049092  jz      short loc_1800490A3
0x180049094  mov     rcx, rbx; Handle
0x180049097  call    cs:__imp_NtClose
0x18004909e  nop     dword ptr [rax+rax+00h]
0x1800490a3  mov     eax, 0FFFFh
0x1800490a8  cmp     cs:word_1803ABC18, ax
0x1800490af  jz      loc_180049321
0x1800490b5  mov     rbx, cs:gpOneCustomHashNode
0x1800490bc  lea     rcx, word_1803ABC1A
0x1800490c3  xor     edx, edx
0x1800490c5  call    GetNamedLocaleHashNode
0x1800490ca  xchg    rax, cs:qword_1803ABC10
0x1800490d1  test    rbx, rbx
0x1800490d4  jnz     short loc_1800490E6
0x1800490d6  cmp     cs:gpOneCustomHashNode, r14
0x1800490dd  jz      short loc_1800490E6
0x1800490df  mov     cs:gpOneCustomHashNode, r14
0x1800490e6  cmp     cs:qword_1803ABC10, r14
0x1800490ed  jnz     loc_18004921C
0x1800490f3  mov     rax, cs:gpSysLocHashN
0x1800490fa  test    rax, rax
0x1800490fd  jnz     loc_180049215
0x180049103  cmp     cs:BasepIsSecureProcess, r14b
0x18004910a  jnz     loc_180049215
0x180049110  lea     rcx, gTblPtrsLock
0x180049117  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18004911e  nop     dword ptr [rax+rax+00h]
0x180049123  cmp     cs:gpSysLocHashN, r14
0x18004912a  jnz     loc_1800491FB
0x180049130  mov     ebx, cs:gSystemLocale
0x180049136  mov     rax, cs:P
0x18004913d  mov     ecx, ebx
0x18004913f  shr     rcx, 7
0x180049143  xor     rcx, rbx
0x180049146  shr     rcx, 7
0x18004914a  xor     rcx, rbx
0x18004914d  and     ecx, 7Fh
0x180049150  mov     rdx, [rax+rcx*8]
0x180049154  test    rdx, rdx
0x180049157  jz      short loc_180049161
0x180049159  cmp     [rdx], ebx
0x18004915b  jnz     loc_180049900
0x180049161  mov     cs:gpSysLocHashN, rdx
0x180049168  test    rdx, rdx
0x18004916b  jnz     loc_1800491FB
0x180049171  test    ebx, 0FFF00000h
0x180049177  jnz     loc_18004945A
0x18004917d  cmp     cs:BasepIsSecureProcess, r14b
0x180049184  jnz     loc_18004945A
0x18004918a  mov     ecx, ebx
0x18004918c  call    GetWindowsLocaleData
0x180049191  test    rax, rax
0x180049194  jz      loc_180049912
0x18004919a  cmp     bx, 7Fh
0x18004919e  jz      loc_180049B07
0x1800491a4  shr     ebx, 10h
0x1800491a7  test    bl, 0Fh
0x1800491aa  jnz     loc_180049428
0x1800491b0  mov     ecx, [rax]
0x1800491b2  mov     rax, cs:qword_1803A6BD0
0x1800491b9  add     rax, r13
0x1800491bc  lea     rcx, [rax+rcx*2]
0x1800491c0  xor     edx, edx
0x1800491c2  call    MakeNamedLocaleHashNode
0x1800491c7  mov     cs:gpSysLocHashN, rax
0x1800491ce  test    rax, rax
0x1800491d1  jnz     short loc_1800491FB
0x1800491d3  xor     edx, edx
0x1800491d5  lea     rcx, aEnUs; "en-US"
0x1800491dc  call    MakeNamedLocaleHashNode
0x1800491e1  mov     cs:gpSysLocHashN, rax
0x1800491e8  test    rax, rax
0x1800491eb  jnz     short loc_1800491FB
0x1800491ed  mov     rdx, cs:gpInvLocHashN
0x1800491f4  mov     cs:gpSysLocHashN, rdx
0x1800491fb  lea     rcx, gTblPtrsLock
0x180049202  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180049209  nop     dword ptr [rax+rax+00h]
0x18004920e  mov     rax, cs:gpSysLocHashN
0x180049215  mov     cs:qword_1803ABC10, rax
0x18004921c  mov     eax, r13d
0x18004921f  lock cmpxchg cs:word_1803AC296, r14w
0x180049229  cmp     cs:word_1803AC294, 3
0x180049231  jz      short loc_180049246
0x180049233  lea     rcx, gNlsProcessCacheLock
0x18004923a  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180049241  nop     dword ptr [rax+rax+00h]
0x180049246  mov     rsi, [rsp+4E0h+arg_0]
0x18004924e  lea     rax, gNlsProcessLocalCache
0x180049255  mov     r15, [rsp+4E0h+arg_8]
0x18004925d  mov     rcx, [rbp+3E0h+var_30]
0x180049264  xor     rcx, rsp; StackCookie
0x180049267  call    __security_check_cookie
0x18004926c  mov     rbx, [rsp+4E0h+arg_10]
0x180049274  add     rsp, 4C0h
0x18004927b  pop     r14
0x18004927d  pop     r13
0x18004927f  pop     r12
0x180049281  pop     rdi
0x180049282  pop     rbp
0x180049283  retn
0x180049285  lea     r9, [rbp+3E0h+CapturedData]; CapturedData
0x180049289  xor     edx, edx; MessageBuffer
0x18004928b  mov     r8d, 67Ch; MessageLength
0x180049291  mov     rcx, rbx; CaptureBuffer
0x180049294  call    cs:__imp_CsrCaptureMessageBuffer
0x18004929b  nop     dword ptr [rax+rax+00h]
0x1800492a0  mov     r9d, 10h; DataLength
0x1800492a6  mov     [rbp+3E0h+var_3E8], 67Ch
0x1800492ad  mov     r8d, 1001Bh; ApiNumber
0x1800492b3  lea     rcx, [rbp+3E0h+ApiMessage]; ApiMessage
0x1800492b7  mov     rdx, rbx; CaptureBuffer
0x1800492ba  call    cs:__imp_CsrClientCallServer
0x1800492c1  nop     dword ptr [rax+rax+00h]
0x1800492c6  mov     r15d, eax
0x1800492c9  test    eax, eax
0x1800492cb  js      short loc_1800492E3
0x1800492cd  mov     rdx, [rbp+3E0h+CapturedData]; Src
0x1800492d1  lea     rcx, word_1803ABC18; void *
0x1800492d8  mov     r8d, 67Ch; Size
0x1800492de  call    memcpy_0
0x1800492e3  mov     rcx, rbx; CaptureBuffer
0x1800492e6  call    cs:__imp_CsrFreeCaptureBuffer
0x1800492ed  nop     dword ptr [rax+rax+00h]
0x1800492f2  jmp     loc_18004903F
0x1800492f7  test    r15d, r15d
0x1800492fa  jns     loc_1800490A3
0x180049300  jmp     loc_18004904D
0x180049305  movzx   eax, cs:word_1803AC296
0x18004930c  test    ax, ax
0x18004930f  jz      loc_180049233
0x180049315  movzx   eax, cs:word_1803AC294
0x18004931c  jmp     loc_180048FF4
0x180049321  mov     cs:qword_1803ABC10, r14
0x180049328  jmp     loc_1800490F3
0x18004932d  mov     rcx, [rsp+4E0h+Handle]
0x180049332  test    rcx, rcx
0x180049335  jnz     loc_180049F4C
0x18004933b  xorps   xmm0, xmm0
0x18004933e  mov     [rsp+4E0h+KeyHandle], r14
0x180049343  movups  xmmword ptr [rbp+3E0h+ObjectAttributes.ObjectName], xmm0
0x180049347  xor     eax, eax
0x180049349  mov     [rsp+4E0h+Disposition], r14d
0x18004934e  movups  xmmword ptr [rbp+3E0h+ObjectAttributes+1Ch], xmm0
0x180049352  movups  xmmword ptr [rsp+4E0h+ObjectAttributes.Length], xmm0
0x180049357  movups  xmmword ptr [rsp+4E0h+DestinationString.Length], xmm0
0x18004935c  call    GetGlobalizationUserModelType
0x180049361  cmp     eax, r12d
0x180049364  jnz     loc_180049B19
0x18004936a  lea     rdx, [rsp+4E0h+KeyHandle]; KeyHandle
0x18004936f  mov     ecx, 2000000h; DesiredAccess
0x180049374  call    cs:__imp_RtlOpenCurrentUser
0x18004937b  nop     dword ptr [rax+rax+00h]
0x180049380  test    eax, eax
0x180049382  js      loc_180049419
0x180049388  mov     edi, 200h
0x18004938d  mov     [rbp+3E0h+ApiMessage], r14w
0x180049392  mov     ecx, edi
0x180049394  lea     rax, [rbp+3E0h+ApiMessage]
0x180049398  cmp     [rax], r14w
0x18004939c  jz      short loc_1800493A6
0x18004939e  add     rax, r13
0x1800493a1  sub     rcx, r12
0x1800493a4  jnz     short loc_180049398
0x1800493a6  mov     rax, rdi
0x1800493a9  sub     rax, rcx
0x1800493ac  test    rcx, rcx
0x1800493af  cmovz   rax, r14
0x1800493b3  jz      short loc_180049403
0x1800493b5  lea     rcx, [rbp+3E0h+ApiMessage]
0x1800493b9  mov     ebx, 7FFFFFFEh
0x1800493be  lea     rcx, [rcx+rax*2]
0x1800493c2  lea     rsi, aControlPanelIn; "Control Panel\\International"
0x1800493c9  sub     rdi, rax
0x1800493cc  jz      short loc_1800493EE
0x1800493ce  xchg    ax, ax
0x1800493d0  test    rbx, rbx
0x1800493d3  jz      short loc_1800493EE
0x1800493d5  movzx   eax, word ptr [rsi]
0x1800493d8  test    ax, ax
0x1800493db  jz      short loc_1800493EE
0x1800493dd  mov     [rcx], ax
0x1800493e0  add     rsi, r13
0x1800493e3  add     rcx, r13
0x1800493e6  dec     rbx
0x1800493e9  sub     rdi, r12
0x1800493ec  jnz     short loc_1800493D0
0x1800493ee  test    rdi, rdi
0x1800493f1  lea     rax, [rcx-2]
0x1800493f5  cmovnz  rax, rcx
0x1800493f9  mov     [rax], r14w
0x1800493fd  jnz     loc_180049E86
0x180049403  mov     rcx, [rsp+4E0h+KeyHandle]; Handle
0x180049408  test    rcx, rcx
0x18004940b  jz      short loc_180049419
0x18004940d  call    cs:__imp_NtClose
0x180049414  nop     dword ptr [rax+rax+00h]
0x180049419  mov     ecx, 3F1h; dwErrCode
0x18004941e  call    SetLastError_0
0x180049423  jmp     loc_18004906E
0x180049428  mov     edx, [rax+0D8h]
0x18004942e  mov     rcx, cs:qword_1803A6BD0
0x180049435  test    edx, edx
0x180049437  jz      short loc_18004944B
0x180049439  and     ebx, 0Fh
0x18004943c  lea     rdx, [rdx+rbx*2]
0x180049440  mov     eax, [rcx+rdx*2-2]
0x180049444  lea     rcx, [rcx+rax*2]
0x180049448  add     rcx, r13
0x18004944b  test    rcx, rcx
0x18004944e  jz      short loc_18004945A
0x180049450  cmp     [rcx], r14w
0x180049454  jnz     loc_1800491C0
0x18004945a  mov     cs:gpSysLocHashN, r14
0x180049461  jmp     loc_1800491D3
0x180049466  mov     r15, cs:gNlsProcessLocalCache
0x18004946d  cmp     cs:BasepIsSecureProcess, r14b
0x180049474  jnz     loc_180049246
0x18004947a  lea     rsi, aControlPanelIn; "Control Panel\\International"
0x180049481  mov     edi, 200h
0x180049486  mov     ebx, 7FFFFFFEh
0x18004948b  test    r15, r15
0x18004948e  jnz     short loc_1800494BB
0x180049490  mov     rax, cs:gNlsProcessLocalCache
0x180049497  mov     [rsp+4E0h+Handle], r14
0x18004949c  test    rax, rax
  ... truncated ...
```
