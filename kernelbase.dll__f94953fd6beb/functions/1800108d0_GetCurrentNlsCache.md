# GetCurrentNlsCache

- ea: `0x1800108d0`
- end: `0x180011b87`
- name: `GetCurrentNlsCache`
- size: `4791`
- prototype: ``
- caller_count: `53`
- callee_count: `19`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000bb00`
- `0x180010080`
- `0x180010320`
- `0x180014ad0`
- `0x180015820`
- `0x180015e20`
- `0x1800181e0`
- `0x180019090`
- `0x18001a230`
- `0x18001d7c0`
- `0x18001ea50`
- `0x18001eec0`
- `0x180037730`
- `0x180038db0`
- `0x18003abc0`
- `0x18003b110`
- `0x18003b620`
- `0x18003bb00`
- `0x18003cb20`
- `0x18003cde0`
- `0x18003cec0`
- `0x18003d060`
- `0x18003d8e0`
- `0x18003db80`
- `0x18003de00`
- `0x18003e5d0`
- `0x18003ef30`
- `0x18003fc74`
- `0x18003fd00`
- `0x180040000`
- `0x180040160`
- `0x180070a70`
- `0x180072390`
- `0x1800726b0`
- `0x180073d30`
- `0x180088c90`
- `0x1800899c0`
- `0x180089a10`
- `0x1800a2b80`
- `0x1800a2d6c`
- `0x1800a3b54`
- `0x1800a4198`
- `0x1800b1630`
- `0x1800b20e0`
- `0x1800b66a0`
- `0x1800bd588`
- `0x1800bd890`
- `0x1800c57b0`
- `0x1800ddee0`
- `0x1800e1e70`

## callees

- `0x180010080`
- `0x1800108d0`
- `0x180011b90`
- `0x180012dc0`
- `0x180012f10`
- `0x1800134a0`
- `0x18001a1b8`
- `0x18001c970`
- `0x18001e794`
- `0x18001e8c0`
- `0x18001ea10`
- `0x180037714`
- `0x180071550`
- `0x18007217c`
- `0x180122e60`
- `0x18012d119`
- `0x180138ebc`
- `0x180188eb9`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18001178f`
- `ntdll!RtlInitUnicodeString` at `0x18001186b`
- `ntdll!RtlInitUnicodeString` at `0x1800119b6`
- `ntdll!RtlInitUnicodeString` at `0x18001178f`
- `ntdll!RtlInitUnicodeString` at `0x18001186b`
- `ntdll!RtlInitUnicodeString` at `0x1800119b6`
- `ntdll!RtlEqualSid` at `0x180011b06`
- `ntdll!RtlEqualSid` at `0x180011b06`
- `ntdll!RtlSetLastWin32Error` at `0x1800115ae`
- `ntdll!RtlSetLastWin32Error` at `0x1800115ae`
- `ntdll!NtOpenKey` at `0x1800117d2`
- `ntdll!NtOpenKey` at `0x1800118ae`
- `ntdll!NtOpenKey` at `0x1800119f9`
- `ntdll!NtOpenKey` at `0x1800117d2`
- `ntdll!NtOpenKey` at `0x1800118ae`
- `ntdll!NtOpenKey` at `0x1800119f9`
- `ntdll!NtCreateEvent` at `0x180011593`
- `ntdll!NtCreateEvent` at `0x180011593`
- `ntdll!NtCreateKey` at `0x180011804`
- `ntdll!NtCreateKey` at `0x1800118e1`
- `ntdll!NtCreateKey` at `0x180011a2b`
- `ntdll!NtCreateKey` at `0x180011804`
- `ntdll!NtCreateKey` at `0x1800118e1`
- `ntdll!NtCreateKey` at `0x180011a2b`
- `ntdll!RtlOpenCurrentUser` at `0x180010ced`
- `ntdll!RtlOpenCurrentUser` at `0x18001118f`
- `ntdll!RtlOpenCurrentUser` at `0x1800112c2`
- `ntdll!RtlOpenCurrentUser` at `0x180010ced`
- `ntdll!RtlOpenCurrentUser` at `0x18001118f`
- `ntdll!RtlOpenCurrentUser` at `0x1800112c2`
- `ntdll!NtNotifyChangeKey` at `0x180011604`
- `ntdll!NtNotifyChangeKey` at `0x180011604`
- `ntdll!NtQueryInformationToken` at `0x180011963`
- `ntdll!NtQueryInformationToken` at `0x180011aeb`
- `ntdll!NtQueryInformationToken` at `0x180011963`
- `ntdll!NtQueryInformationToken` at `0x180011aeb`
- `ntdll!CsrClientCallServer` at `0x180010c3f`
- `ntdll!CsrClientCallServer` at `0x1800110df`
- `ntdll!CsrClientCallServer` at `0x180010c3f`
- `ntdll!CsrClientCallServer` at `0x1800110df`
- `ntdll!CsrCaptureMessageBuffer` at `0x180010c1f`
- `ntdll!CsrCaptureMessageBuffer` at `0x1800110bf`
- `ntdll!CsrCaptureMessageBuffer` at `0x180010c1f`
- `ntdll!CsrCaptureMessageBuffer` at `0x1800110bf`
- `ntdll!CsrFreeCaptureBuffer` at `0x180010c65`
- `ntdll!CsrFreeCaptureBuffer` at `0x180011107`
- `ntdll!CsrFreeCaptureBuffer` at `0x180010c65`
- `ntdll!CsrFreeCaptureBuffer` at `0x180011107`
- `ntdll!CsrAllocateCaptureBuffer` at `0x1800109cb`
- `ntdll!CsrAllocateCaptureBuffer` at `0x180010ebc`
- `ntdll!CsrAllocateCaptureBuffer` at `0x1800109cb`
- `ntdll!CsrAllocateCaptureBuffer` at `0x180010ebc`
- `ntdll!NtClose` at `0x180010a3b`
- `ntdll!NtClose` at `0x180010d83`
- `ntdll!NtClose` at `0x180010f31`
- `ntdll!NtClose` at `0x180011225`
- `ntdll!NtClose` at `0x18001133f`
- `ntdll!NtClose` at `0x180011816`
- `ntdll!NtClose` at `0x180011852`
- `ntdll!NtClose` at `0x1800118f4`
- `ntdll!NtClose` at `0x180011932`
- `ntdll!NtClose` at `0x180011a3d`
- `ntdll!NtClose` at `0x180011a79`
- `ntdll!NtClose` at `0x180010a3b`
- `ntdll!NtClose` at `0x180010d83`
- `ntdll!NtClose` at `0x180010f31`
- `ntdll!NtClose` at `0x180011225`
- `ntdll!NtClose` at `0x18001133f`
- `ntdll!NtClose` at `0x180011816`
- `ntdll!NtClose` at `0x180011852`
- `ntdll!NtClose` at `0x1800118f4`
- `ntdll!NtClose` at `0x180011932`
- `ntdll!NtClose` at `0x180011a3d`
- `ntdll!NtClose` at `0x180011a79`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180010987`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180010ab5`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180010e78`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180010fab`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180011553`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180010987`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180010ab5`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180010e78`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180010fab`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180011553`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180010b9a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180010bcc`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180011611`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180010b9a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180010bcc`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180011611`
- `ntdll!RtlFreeHeap` at `0x180011b24`
- `ntdll!RtlFreeHeap` at `0x180011b24`
- `ntdll!RtlAllocateHeap` at `0x1800116d1`
- `ntdll!RtlAllocateHeap` at `0x180011743`
- `ntdll!RtlAllocateHeap` at `0x180011abc`
- `ntdll!RtlAllocateHeap` at `0x1800116d1`
- `ntdll!RtlAllocateHeap` at `0x180011743`
- `ntdll!RtlAllocateHeap` at `0x180011abc`

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
        word_1803A4274 = 1;
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
      word_1803A4274 = 1;
    else
      word_1803A4274 = 20;
LABEL_3:
    if ( v2 )
    {
      if ( dword_1803A4270 != *(_DWORD *)(gpServerNlsUserInfo + 1656) )
        word_1803A4276 = 1;
      if ( !word_1803A4276 )
        return &gNlsProcessLocalCache;
      v3 = word_1803A4274;
      if ( word_1803A4274 != 3 )
      {
        RtlAcquireSRWLockExclusive(&gNlsProcessCacheLock);
        v3 = word_1803A4274;
        if ( word_1803A4274 != 3 )
        {
          if ( !word_1803A4276 )
            goto LABEL_42;
          v3 = word_1803A4274;
        }
      }
      word_1803A4276 = 2;
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
            memcpy_0(&word_1803A3BF8, CapturedData, 0x67Cu);
          CsrFreeCaptureBuffer(v5);
        }
        else
        {
          v6 = -1073741801;
        }
        if ( word_1803A4274 == 1 && v6 >= 0 )
          goto LABEL_18;
      }
      Handle = 0;
      if ( gNlsProcessLocalCache )
      {
        Handle = gNlsProcessLocalCache;
LABEL_15:
        v7 = Handle;
        NlsUpdateCacheInfo(&word_1803A3BF8, Handle, 1);
        if ( word_1803A4274 == 3 && v7 )
          NtClose(v7);
LABEL_18:
        if ( word_1803A3BF8 == -1 )
        {
          qword_1803A3BF0 = 0;
          goto LABEL_23;
        }
        v8 = gpOneCustomHashNode;
        _InterlockedExchange64(&qword_1803A3BF0, GetNamedLocaleHashNode(word_1803A3BFA, 0));
        if ( !v8 && gpOneCustomHashNode )
          gpOneCustomHashNode = 0;
        if ( !qword_1803A3BF0 )
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
                v15 = (_WORD *)(qword_18039EC90 + 2 + 2LL * *WindowsLocaleData);
LABEL_35:
                NamedLocaleHashNode = MakeNamedLocaleHashNode(v15, 0);
                goto LABEL_36;
              }
              v28 = WindowsLocaleData[54];
              v15 = (_WORD *)qword_18039EC90;
              if ( (_DWORD)v28 )
                v15 = (_WORD *)(qword_18039EC90
                              + 2LL * *(unsigned int *)(qword_18039EC90 + 2 * (v28 + 2LL * (v14 & 0xF)) - 2)
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
          qword_1803A3BF0 = v9;
        }
LABEL_41:
        _InterlockedCompareExchange16(&word_1803A4276, 0, 2);
        if ( word_1803A4274 == 3 )
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
        word_1803A4276 = 1;
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
      if ( !word_1803A4276 )
        return &gNlsProcessLocalCache;
      v32 = word_1803A4274;
      if ( word_1803A4274 != 3 )
      {
        RtlAcquireSRWLockExclusive(&gNlsProcessCacheLock);
        v32 = word_1803A4274;
        if ( word_1803A4274 != 3 )
        {
          if ( !word_1803A4276 )
            goto LABEL_42;
          v32 = word_1803A4274;
        }
      }
      word_1803A4276 = 2;
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
            memcpy_0(&word_1803A3BF8, CapturedData, 0x67Cu);
          CsrFreeCaptureBuffer((PCSR_CAPTURE_BUFFER)KeyHandle);
        }
        else
        {
          v35 = -1073741801;
        }
        if ( word_1803A4274 == 1 && v35 >= 0 )
        {
LABEL_92:
          if ( word_1803A3BF8 == -1 )
          {
            qword_1803A3BF0 = 0;
          }
          else
          {
            v37 = gpOneCustomHashNode;
            _InterlockedExchange64(&qword_1803A3BF0, GetNamedLocaleHashNode(word_1803A3BFA, 0));
            if ( !v37 && gpOneCustomHashNode )
              gpOneCustomHashNode = 0;
            if ( qword_1803A3BF0 )
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
                v43 = (_WORD *)(qword_18039EC90 + 2 + 2LL * *v40);
LABEL_109:
                LocHashNodeFromSystemLocale = MakeNamedLocaleHashNode(v43, 0);
                goto LABEL_110;
              }
              v63 = v40[54];
              v43 = (_WORD *)qword_18039EC90;
              if ( (_DWORD)v63 )
                v43 = (_WORD *)(qword_18039EC90
                              + 2LL * *(unsigned int *)(qword_18039EC90 + 2 * (v63 + 2LL * (v42 & 0xF)) - 2)
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
        NlsUpdateCacheInfo(&word_1803A3BF8, Handle, 1);
        if ( word_1803A4274 == 3 && v36 )
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
0x1800108d0  mov     [rsp-8+arg_10], rbx
0x1800108d5  push    rbp
0x1800108d6  push    rdi
0x1800108d7  push    r12
0x1800108d9  push    r13
0x1800108db  push    r14
0x1800108dd  lea     rbp, [rsp-3C0h]
0x1800108e5  sub     rsp, 4C0h
0x1800108ec  mov     rax, cs:__security_cookie
0x1800108f3  xor     rax, rsp
0x1800108f6  mov     [rbp+3E0h+var_30], rax
0x1800108fd  mov     rax, gs:30h
0x180010906  xor     r14d, r14d
0x180010909  mov     ecx, [rax+179Ch]
0x18001090f  test    ecx, ecx
0x180010911  jnz     loc_180011096
0x180010917  mov     ebx, cs:gInteractiveLogonUserProcess
0x18001091d  mov     r12d, 1
0x180010923  cmp     ebx, 0FFFFFFFFh
0x180010926  jz      loc_180011392
0x18001092c  mov     [rsp+4E0h+arg_0], rsi
0x180010934  mov     [rsp+4E0h+arg_8], r15
0x18001093c  test    ebx, ebx
0x18001093e  jz      loc_180010DD6
0x180010944  mov     ecx, cs:dword_1803A4270
0x18001094a  mov     rax, cs:gpServerNlsUserInfo
0x180010951  mov     eax, [rax+678h]
0x180010957  cmp     ecx, eax
0x180010959  jz      short loc_180010963
0x18001095b  mov     cs:word_1803A4276, r12w
0x180010963  movzx   eax, cs:word_1803A4276
0x18001096a  test    ax, ax
0x18001096d  jz      loc_180010BD2
0x180010973  movzx   eax, cs:word_1803A4274
0x18001097a  cmp     ax, 3
0x18001097e  jz      short loc_18001099E
0x180010980  lea     rcx, gNlsProcessCacheLock
0x180010987  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001098d  movzx   eax, cs:word_1803A4274
0x180010994  cmp     ax, 3
0x180010998  jnz     loc_180010C7E
0x18001099e  mov     r13d, 2
0x1800109a4  mov     cs:word_1803A4276, r13w
0x1800109ac  cmp     ax, r12w
0x1800109b0  jnz     short loc_1800109F1
0x1800109b2  xor     edx, edx; Val
0x1800109b4  lea     rcx, [rbp+3E0h+ApiMessage]; void *
0x1800109b8  mov     r8d, 3B8h; Size
0x1800109be  call    memset_0
0x1800109c3  mov     edx, 67Ch; BufferSize
0x1800109c8  mov     ecx, r12d; ArgumentCount
0x1800109cb  call    cs:__imp_CsrAllocateCaptureBuffer
0x1800109d1  mov     rbx, rax
0x1800109d4  test    rax, rax
0x1800109d7  jnz     loc_180010C10
0x1800109dd  mov     r15d, 0C0000017h
0x1800109e3  cmp     cs:word_1803A4274, r12w
0x1800109eb  jz      loc_180010C70
0x1800109f1  mov     rax, cs:gNlsProcessLocalCache
0x1800109f8  mov     [rsp+4E0h+Handle], r14
0x1800109fd  test    rax, rax
0x180010a00  jz      loc_180010CA6
0x180010a06  mov     rax, cs:gNlsProcessLocalCache
0x180010a0d  mov     [rsp+4E0h+Handle], rax
0x180010a12  mov     rbx, [rsp+4E0h+Handle]
0x180010a17  lea     rcx, word_1803A3BF8
0x180010a1e  mov     rdx, rbx
0x180010a21  mov     r8d, r12d
0x180010a24  call    NlsUpdateCacheInfo
0x180010a29  cmp     cs:word_1803A4274, 3
0x180010a31  jnz     short loc_180010A41
0x180010a33  test    rbx, rbx
0x180010a36  jz      short loc_180010A41
0x180010a38  mov     rcx, rbx; Handle
0x180010a3b  call    cs:__imp_NtClose
0x180010a41  mov     eax, 0FFFFh
0x180010a46  cmp     cs:word_1803A3BF8, ax
0x180010a4d  jz      loc_180010C9A
0x180010a53  mov     rbx, cs:gpOneCustomHashNode
0x180010a5a  lea     rcx, word_1803A3BFA
0x180010a61  xor     edx, edx
0x180010a63  call    GetNamedLocaleHashNode
0x180010a68  xchg    rax, cs:qword_1803A3BF0
0x180010a6f  test    rbx, rbx
0x180010a72  jnz     short loc_180010A84
0x180010a74  cmp     cs:gpOneCustomHashNode, r14
0x180010a7b  jz      short loc_180010A84
0x180010a7d  mov     cs:gpOneCustomHashNode, r14
0x180010a84  cmp     cs:qword_1803A3BF0, r14
0x180010a8b  jnz     loc_180010BAE
0x180010a91  mov     rax, cs:gpSysLocHashN
0x180010a98  test    rax, rax
0x180010a9b  jnz     loc_180010BA7
0x180010aa1  cmp     cs:BasepIsSecureProcess, r14b
0x180010aa8  jnz     loc_180010BA7
0x180010aae  lea     rcx, gTblPtrsLock
0x180010ab5  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180010abb  cmp     cs:gpSysLocHashN, r14
0x180010ac2  jnz     loc_180010B93
0x180010ac8  mov     ebx, cs:gSystemLocale
0x180010ace  mov     rax, cs:P
0x180010ad5  mov     ecx, ebx
0x180010ad7  shr     rcx, 7
0x180010adb  xor     rcx, rbx
0x180010ade  shr     rcx, 7
0x180010ae2  xor     rcx, rbx
0x180010ae5  and     ecx, 7Fh
0x180010ae8  mov     rdx, [rax+rcx*8]
0x180010aec  test    rdx, rdx
0x180010aef  jz      short loc_180010AF9
0x180010af1  cmp     [rdx], ebx
0x180010af3  jnz     loc_18001123A
0x180010af9  mov     cs:gpSysLocHashN, rdx
0x180010b00  test    rdx, rdx
0x180010b03  jnz     loc_180010B93
0x180010b09  test    ebx, 0FFF00000h
0x180010b0f  jnz     loc_180010DCA
0x180010b15  cmp     cs:BasepIsSecureProcess, r14b
0x180010b1c  jnz     loc_180010DCA
0x180010b22  mov     ecx, ebx
0x180010b24  call    GetWindowsLocaleData
0x180010b29  test    rax, rax
0x180010b2c  jz      loc_18001124C
0x180010b32  cmp     bx, 7Fh
0x180010b36  jz      loc_180011431
0x180010b3c  shr     ebx, 10h
0x180010b3f  test    bl, 0Fh
0x180010b42  jnz     loc_180010D98
0x180010b48  mov     ecx, [rax]
0x180010b4a  mov     rax, cs:qword_18039EC90
0x180010b51  add     rax, r13
0x180010b54  lea     rcx, [rax+rcx*2]
0x180010b58  xor     edx, edx
0x180010b5a  call    MakeNamedLocaleHashNode
0x180010b5f  mov     cs:gpSysLocHashN, rax
0x180010b66  test    rax, rax
0x180010b69  jnz     short loc_180010B93
0x180010b6b  xor     edx, edx
0x180010b6d  lea     rcx, aEnUs; "en-US"
0x180010b74  call    MakeNamedLocaleHashNode
0x180010b79  mov     cs:gpSysLocHashN, rax
0x180010b80  test    rax, rax
0x180010b83  jnz     short loc_180010B93
0x180010b85  mov     rdx, cs:gpInvLocHashN
0x180010b8c  mov     cs:gpSysLocHashN, rdx
0x180010b93  lea     rcx, gTblPtrsLock
0x180010b9a  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180010ba0  mov     rax, cs:gpSysLocHashN
0x180010ba7  mov     cs:qword_1803A3BF0, rax
0x180010bae  mov     eax, r13d
0x180010bb1  lock cmpxchg cs:word_1803A4276, r14w
0x180010bbb  cmp     cs:word_1803A4274, 3
0x180010bc3  jz      short loc_180010BD2
0x180010bc5  lea     rcx, gNlsProcessCacheLock
0x180010bcc  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180010bd2  mov     rsi, [rsp+4E0h+arg_0]
0x180010bda  lea     rax, gNlsProcessLocalCache
0x180010be1  mov     r15, [rsp+4E0h+arg_8]
0x180010be9  mov     rcx, [rbp+3E0h+var_30]
0x180010bf0  xor     rcx, rsp; StackCookie
0x180010bf3  call    __security_check_cookie
0x180010bf8  mov     rbx, [rsp+4E0h+arg_10]
0x180010c00  add     rsp, 4C0h
0x180010c07  pop     r14
0x180010c09  pop     r13
0x180010c0b  pop     r12
0x180010c0d  pop     rdi
0x180010c0e  pop     rbp
0x180010c0f  retn
0x180010c10  lea     r9, [rbp+3E0h+CapturedData]; CapturedData
0x180010c14  xor     edx, edx; MessageBuffer
0x180010c16  mov     r8d, 67Ch; MessageLength
0x180010c1c  mov     rcx, rbx; CaptureBuffer
0x180010c1f  call    cs:__imp_CsrCaptureMessageBuffer
0x180010c25  mov     r9d, 10h; DataLength
0x180010c2b  mov     [rbp+3E0h+var_3E8], 67Ch
0x180010c32  mov     r8d, 1001Bh; ApiNumber
0x180010c38  lea     rcx, [rbp+3E0h+ApiMessage]; ApiMessage
0x180010c3c  mov     rdx, rbx; CaptureBuffer
0x180010c3f  call    cs:__imp_CsrClientCallServer
0x180010c45  mov     r15d, eax
0x180010c48  test    eax, eax
0x180010c4a  js      short loc_180010C62
0x180010c4c  mov     rdx, [rbp+3E0h+CapturedData]; Src
0x180010c50  lea     rcx, word_1803A3BF8; void *
0x180010c57  mov     r8d, 67Ch; Size
0x180010c5d  call    memcpy_0
0x180010c62  mov     rcx, rbx; CaptureBuffer
0x180010c65  call    cs:__imp_CsrFreeCaptureBuffer
0x180010c6b  jmp     loc_1800109E3
0x180010c70  test    r15d, r15d
0x180010c73  jns     loc_180010A41
0x180010c79  jmp     loc_1800109F1
0x180010c7e  movzx   eax, cs:word_1803A4276
0x180010c85  test    ax, ax
0x180010c88  jz      loc_180010BC5
0x180010c8e  movzx   eax, cs:word_1803A4274
0x180010c95  jmp     loc_18001099E
0x180010c9a  mov     cs:qword_1803A3BF0, r14
0x180010ca1  jmp     loc_180010A91
0x180010ca6  mov     rcx, [rsp+4E0h+Handle]
0x180010cab  test    rcx, rcx
0x180010cae  jnz     loc_180011834
0x180010cb4  xorps   xmm0, xmm0
0x180010cb7  mov     [rsp+4E0h+KeyHandle], r14
0x180010cbc  movups  xmmword ptr [rbp+3E0h+ObjectAttributes.ObjectName], xmm0
0x180010cc0  xor     eax, eax
0x180010cc2  mov     [rsp+4E0h+Disposition], r14d
0x180010cc7  movups  xmmword ptr [rbp+3E0h+ObjectAttributes+1Ch], xmm0
0x180010ccb  movups  xmmword ptr [rsp+4E0h+ObjectAttributes.Length], xmm0
0x180010cd0  movups  xmmword ptr [rsp+4E0h+DestinationString.Length], xmm0
0x180010cd5  call    GetGlobalizationUserModelType
0x180010cda  cmp     eax, r12d
0x180010cdd  jnz     loc_180011443
0x180010ce3  lea     rdx, [rsp+4E0h+KeyHandle]; KeyHandle
0x180010ce8  mov     ecx, 2000000h; DesiredAccess
0x180010ced  call    cs:__imp_RtlOpenCurrentUser
0x180010cf3  test    eax, eax
0x180010cf5  js      loc_180010D89
0x180010cfb  mov     edi, 200h
0x180010d00  mov     [rbp+3E0h+ApiMessage], r14w
0x180010d05  mov     ecx, edi
0x180010d07  lea     rax, [rbp+3E0h+ApiMessage]
0x180010d0b  nop     dword ptr [rax+rax+00h]
0x180010d10  cmp     [rax], r14w
0x180010d14  jz      short loc_180010D1E
0x180010d16  add     rax, r13
0x180010d19  sub     rcx, r12
0x180010d1c  jnz     short loc_180010D10
0x180010d1e  mov     rax, rdi
0x180010d21  sub     rax, rcx
0x180010d24  test    rcx, rcx
0x180010d27  cmovz   rax, r14
0x180010d2b  jz      short loc_180010D79
0x180010d2d  lea     rcx, [rbp+3E0h+ApiMessage]
0x180010d31  mov     ebx, 7FFFFFFEh
0x180010d36  lea     rcx, [rcx+rax*2]
0x180010d3a  lea     rsi, aControlPanelIn; "Control Panel\\International"
0x180010d41  sub     rdi, rax
0x180010d44  jz      short loc_180010D64
0x180010d46  test    rbx, rbx
0x180010d49  jz      short loc_180010D64
0x180010d4b  movzx   eax, word ptr [rsi]
0x180010d4e  test    ax, ax
0x180010d51  jz      short loc_180010D64
0x180010d53  mov     [rcx], ax
0x180010d56  add     rsi, r13
0x180010d59  add     rcx, r13
0x180010d5c  dec     rbx
0x180010d5f  sub     rdi, r12
0x180010d62  jnz     short loc_180010D46
0x180010d64  test    rdi, rdi
0x180010d67  lea     rax, [rcx-2]
0x180010d6b  cmovnz  rax, rcx
0x180010d6f  mov     [rax], r14w
0x180010d73  jnz     loc_180011786
0x180010d79  mov     rcx, [rsp+4E0h+KeyHandle]; Handle
0x180010d7e  test    rcx, rcx
0x180010d81  jz      short loc_180010D89
0x180010d83  call    cs:__imp_NtClose
0x180010d89  mov     ecx, 3F1h; dwErrCode
0x180010d8e  call    SetLastError_0
0x180010d93  jmp     loc_180010A12
0x180010d98  mov     edx, [rax+0D8h]
0x180010d9e  mov     rcx, cs:qword_18039EC90
0x180010da5  test    edx, edx
0x180010da7  jz      short loc_180010DBB
0x180010da9  and     ebx, 0Fh
0x180010dac  lea     rdx, [rdx+rbx*2]
0x180010db0  mov     eax, [rcx+rdx*2-2]
0x180010db4  lea     rcx, [rcx+rax*2]
0x180010db8  add     rcx, r13
0x180010dbb  test    rcx, rcx
0x180010dbe  jz      short loc_180010DCA
0x180010dc0  cmp     [rcx], r14w
0x180010dc4  jnz     loc_180010B58
0x180010dca  mov     cs:gpSysLocHashN, r14
0x180010dd1  jmp     loc_180010B6B
0x180010dd6  mov     r15, cs:gNlsProcessLocalCache
0x180010ddd  cmp     cs:BasepIsSecureProcess, r14b
0x180010de4  jnz     loc_180010BD2
0x180010dea  lea     rsi, aControlPanelIn; "Control Panel\\International"
0x180010df1  mov     edi, 200h
0x180010df6  mov     ebx, 7FFFFFFEh
0x180010dfb  test    r15, r15
0x180010dfe  jnz     short loc_180010E2B
0x180010e00  mov     rax, cs:gNlsProcessLocalCache
0x180010e07  mov     [rsp+4E0h+Handle], r14
0x180010e0c  test    rax, rax
0x180010e0f  jz      loc_180011148
0x180010e15  mov     rax, cs:gNlsProcessLocalCache
0x180010e1c  mov     [rsp+4E0h+Handle], rax
0x180010e21  mov     r15, [rsp+4E0h+Handle]
0x180010e26  test    r15, r15
0x180010e29  jz      short loc_180010E54
0x180010e2b  mov     rax, cs:Event
0x180010e32  test    rax, rax
0x180010e35  jz      loc_180011544
0x180010e3b  mov     rcx, cs:Event; hHandle
0x180010e42  xor     r8d, r8d; bAlertable
  ... truncated ...
```
