# NlsCheckStaleCache

- ea: `0x18004a820`
- end: `0x18004b285`
- name: `NlsCheckStaleCache`
- size: `2661`
- prototype: ``
- caller_count: `6`
- callee_count: `18`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001cd50`
- `0x180022a60`
- `0x180023c10`
- `0x180027400`
- `0x180028630`
- `0x180046ac0`

## callees

- `0x18001cd34`
- `0x180024c80`
- `0x1800265f0`
- `0x180028360`
- `0x180028490`
- `0x1800285f0`
- `0x18002aabc`
- `0x1800486a0`
- `0x18004a310`
- `0x18004a820`
- `0x18004b2a0`
- `0x18004b408`
- `0x18004b9d0`
- `0x18012c3ac`
- `0x1801369c9`
- `0x180142ba0`
- `0x180194eb9`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18004b073`
- `ntdll!RtlInitUnicodeString` at `0x18004b16d`
- `ntdll!RtlInitUnicodeString` at `0x18004b073`
- `ntdll!RtlInitUnicodeString` at `0x18004b16d`
- `ntdll!RtlSetLastWin32Error` at `0x18004af74`
- `ntdll!RtlSetLastWin32Error` at `0x18004af74`
- `ntdll!NtOpenKey` at `0x18004b0bd`
- `ntdll!NtOpenKey` at `0x18004b1b7`
- `ntdll!NtOpenKey` at `0x18004b0bd`
- `ntdll!NtOpenKey` at `0x18004b1b7`
- `ntdll!NtCreateEvent` at `0x18004af53`
- `ntdll!NtCreateEvent` at `0x18004af53`
- `ntdll!NtCreateKey` at `0x18004b0f5`
- `ntdll!NtCreateKey` at `0x18004b1ef`
- `ntdll!NtCreateKey` at `0x18004b0f5`
- `ntdll!NtCreateKey` at `0x18004b1ef`
- `ntdll!RtlOpenCurrentUser` at `0x18004acb4`
- `ntdll!RtlOpenCurrentUser` at `0x18004ada9`
- `ntdll!RtlOpenCurrentUser` at `0x18004acb4`
- `ntdll!RtlOpenCurrentUser` at `0x18004ada9`
- `ntdll!NtNotifyChangeKey` at `0x18004afd0`
- `ntdll!NtNotifyChangeKey` at `0x18004afd0`
- `ntdll!CsrClientCallServer` at `0x18004abfc`
- `ntdll!CsrClientCallServer` at `0x18004abfc`
- `ntdll!CsrCaptureMessageBuffer` at `0x18004abd6`
- `ntdll!CsrCaptureMessageBuffer` at `0x18004abd6`
- `ntdll!CsrFreeCaptureBuffer` at `0x18004ac27`
- `ntdll!CsrFreeCaptureBuffer` at `0x18004ac27`
- `ntdll!CsrAllocateCaptureBuffer` at `0x18004a954`
- `ntdll!CsrAllocateCaptureBuffer` at `0x18004a954`
- `ntdll!NtClose` at `0x18004a9c9`
- `ntdll!NtClose` at `0x18004ad47`
- `ntdll!NtClose` at `0x18004ae38`
- `ntdll!NtClose` at `0x18004b10d`
- `ntdll!NtClose` at `0x18004b14f`
- `ntdll!NtClose` at `0x18004b207`
- `ntdll!NtClose` at `0x18004b245`
- `ntdll!NtClose` at `0x18004a9c9`
- `ntdll!NtClose` at `0x18004ad47`
- `ntdll!NtClose` at `0x18004ae38`
- `ntdll!NtClose` at `0x18004b10d`
- `ntdll!NtClose` at `0x18004b14f`
- `ntdll!NtClose` at `0x18004b207`
- `ntdll!NtClose` at `0x18004b245`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18004a904`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18004aa51`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18004af0d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18004a904`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18004aa51`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18004af0d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18004ab3d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18004ab79`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18004afe3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18004ab3d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18004ab79`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18004afe3`

## pseudocode

```c
void NlsCheckStaleCache()
{
  HANDLE v0; // rbx
  __int64 v1; // r14
  const WCHAR *v2; // r15
  __int16 v3; // ax
  struct _CSR_CAPTURE_BUFFER *CaptureBuffer; // rax
  struct _CSR_CAPTURE_BUFFER *v5; // rbx
  NTSTATUS v6; // esi
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
  int GlobalizationUserModelType; // eax
  int v18; // eax
  WCHAR *v19; // rax
  __int64 v20; // rcx
  __int64 v21; // r9
  __int64 v22; // rcx
  bool v23; // zf
  __int64 v24; // r8
  const WCHAR *v25; // rdx
  WCHAR *v26; // r9
  WCHAR *v27; // rcx
  int v28; // eax
  int v29; // eax
  WCHAR *v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rdi
  WCHAR *v33; // rdx
  WCHAR *v34; // rcx
  __int64 v35; // rdx
  int v36; // eax
  NTSTATUS v37; // eax
  ULONG v38; // ecx
  HANDLE v39; // rax
  int v40; // eax
  NTSTATUS v41; // ebx
  HANDLE v42; // rcx
  void *v43; // rbx
  NTSTATUS v44; // ebx
  HANDLE v45; // rcx
  void *v46; // rbx
  HANDLE Handle; // [rsp+58h] [rbp-B0h] BYREF
  HANDLE KeyHandle; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD ObjectAttributes[7]; // [rsp+68h] [rbp-A0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-68h] BYREF
  WCHAR ApiMessage[32]; // [rsp+B8h] [rbp-50h] BYREF
  PVOID CapturedData; // [rsp+F8h] [rbp-10h] BYREF
  int v53; // [rsp+100h] [rbp-8h]

  v0 = gNlsProcessLocalCache;
  if ( BasepIsSecureProcess )
    return;
  v1 = 2147483646;
  v2 = L"Control Panel\\International";
  if ( !gNlsProcessLocalCache )
  {
    Handle = 0;
    KeyHandle = 0;
    LODWORD(ObjectAttributes[0]) = 0;
    memset(&ObjectAttributes[1], 0, 44);
    DestinationString = 0;
    GlobalizationUserModelType = GetGlobalizationUserModelType();
    if ( GlobalizationUserModelType == 1 )
    {
      v18 = RtlOpenCurrentUser(0x2000000u, &KeyHandle);
    }
    else
    {
      v36 = GlobalizationUserModelType - 2;
      if ( v36 )
      {
        if ( v36 != 1 )
          goto LABEL_70;
        HIDWORD(ObjectAttributes[0]) = 0;
        v18 = OpenGlobalizationUserSettingsKey_ForMua(0x2000000u, 0, &KeyHandle, (_DWORD *)ObjectAttributes + 1);
      }
      else
      {
        v18 = OpenGlobalizationUserSettingsKey_ForSingleUserModel(0x2000000u, &KeyHandle);
      }
    }
    if ( v18 >= 0 )
    {
      ApiMessage[0] = 0;
      v19 = ApiMessage;
      v20 = 512;
      do
      {
        if ( !*v19 )
          break;
        ++v19;
        --v20;
      }
      while ( v20 );
      v21 = 512 - v20;
      if ( !v20 )
        goto LABEL_68;
      v22 = 2147483646;
      v24 = 512 - v21;
      v23 = v21 == 512;
      v25 = L"Control Panel\\International";
      v26 = &ApiMessage[v21];
      if ( !v23 )
      {
        do
        {
          if ( !v22 )
            break;
          if ( !*v25 )
            break;
          *v26++ = *v25++;
          --v22;
          --v24;
        }
        while ( v24 );
      }
      v27 = v26 - 1;
      if ( v24 )
        v27 = v26;
      *v27 = 0;
      if ( v24 )
      {
        RtlInitUnicodeString(&DestinationString, ApiMessage);
        ObjectAttributes[2] = KeyHandle;
        LODWORD(ObjectAttributes[1]) = 48;
        ObjectAttributes[3] = &DestinationString;
        LODWORD(ObjectAttributes[4]) = 64;
        *(_OWORD *)&ObjectAttributes[5] = 0;
        LODWORD(ObjectAttributes[0]) = 0;
        v41 = NtOpenKey(&Handle, 0x20019u, (POBJECT_ATTRIBUTES)&ObjectAttributes[1]);
        if ( v41 < 0 )
          v41 = NtCreateKey(
                  &Handle,
                  0x20019u,
                  (POBJECT_ATTRIBUTES)&ObjectAttributes[1],
                  0,
                  0,
                  0,
                  (PULONG)ObjectAttributes);
        if ( KeyHandle )
          NtClose(KeyHandle);
        if ( v41 >= 0 )
        {
          v42 = Handle;
        }
        else
        {
          v42 = 0;
          Handle = 0;
        }
        if ( v41 >= 0 )
        {
          v43 = (void *)_InterlockedCompareExchange64(
                          (volatile signed __int64 *)&gNlsProcessLocalCache,
                          (signed __int64)v42,
                          0);
          if ( v43 )
          {
            if ( Handle )
              NtClose(Handle);
            Handle = v43;
          }
          goto LABEL_4;
        }
      }
      else
      {
LABEL_68:
        if ( KeyHandle )
          NtClose(KeyHandle);
      }
    }
LABEL_70:
    SetLastError_0(0x3F1u);
LABEL_4:
    v0 = Handle;
  }
  if ( v0 && (!Event || !WaitForSingleObjectEx(Event, 0, 0)) )
  {
    word_1803AC296 = 1;
    RtlAcquireSRWLockExclusive(&gNlsProcessCacheLock);
    if ( !Event )
    {
      KeyHandle = 0;
      memset(&ObjectAttributes[1], 0, 44);
      DestinationString = 0;
      v37 = NtCreateEvent(&KeyHandle, 0x1F0003u, 0, SynchronizationEvent, 0);
      if ( v37 < 0 )
      {
        BaseSetLastNTError((unsigned int)v37);
        v39 = 0;
      }
      else
      {
        if ( v37 == 0x40000000 )
          v38 = 183;
        else
          v38 = 0;
        RtlSetLastWin32Error(v38);
        v39 = KeyHandle;
      }
      Event = v39;
    }
    if ( Event )
      NtNotifyChangeKey(v0, Event, 0, 0, &IoStatusRegChange, 0x10000005u, 1u, 0, 0, 1u);
    RtlReleaseSRWLockExclusive(&gNlsProcessCacheLock);
  }
  if ( word_1803AC296 )
  {
    v3 = word_1803AC294;
    if ( word_1803AC294 != 3 )
    {
      RtlAcquireSRWLockExclusive(&gNlsProcessCacheLock);
      v3 = word_1803AC294;
      if ( word_1803AC294 != 3 )
      {
        if ( !word_1803AC296 )
        {
LABEL_44:
          RtlReleaseSRWLockExclusive(&gNlsProcessCacheLock);
          return;
        }
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
        v53 = 1660;
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
      {
LABEL_20:
        if ( word_1803ABC18 == -1 )
        {
          qword_1803ABC10 = 0;
        }
        else
        {
          v8 = gpOneCustomHashNode;
          _InterlockedExchange64(&qword_1803ABC10, GetNamedLocaleHashNode(word_1803ABC1A, 0));
          if ( !v8 && gpOneCustomHashNode )
            gpOneCustomHashNode = 0;
          if ( qword_1803ABC10 )
          {
LABEL_43:
            _InterlockedCompareExchange16(&word_1803AC296, 0, 2);
            if ( word_1803AC294 == 3 )
              return;
            goto LABEL_44;
          }
        }
        v9 = gpSysLocHashN;
        if ( gpSysLocHashN || BasepIsSecureProcess )
        {
LABEL_42:
          qword_1803ABC10 = v9;
          goto LABEL_43;
        }
        RtlAcquireSRWLockExclusive(&gTblPtrsLock);
        if ( gpSysLocHashN )
          goto LABEL_41;
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
          goto LABEL_41;
        if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
          goto LABEL_92;
        WindowsLocaleData = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
        if ( WindowsLocaleData )
        {
          if ( (_WORD)v10 != 127 )
          {
            v14 = HIWORD(v10);
            if ( (v14 & 0xF) == 0 )
            {
              v15 = (_WORD *)(qword_1803A6BD0 + 2 + 2LL * *WindowsLocaleData);
LABEL_37:
              NamedLocaleHashNode = MakeNamedLocaleHashNode(v15, 0);
              goto LABEL_38;
            }
            v35 = WindowsLocaleData[54];
            v15 = (_WORD *)qword_1803A6BD0;
            if ( (_DWORD)v35 )
              v15 = (_WORD *)(qword_1803A6BD0
                            + 2LL * *(unsigned int *)(qword_1803A6BD0 + 2 * (v35 + 2LL * (v14 & 0xF)) - 2)
                            + 2);
            if ( v15 && *v15 )
              goto LABEL_37;
LABEL_92:
            gpSysLocHashN = 0;
LABEL_39:
            gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
            if ( !gpSysLocHashN )
              gpSysLocHashN = gpInvLocHashN;
            goto LABEL_41;
          }
          NamedLocaleHashNode = MakeLocHashNodeFromSystemLocale(WindowsLocaleData, v10, v13, 0);
        }
        else
        {
          if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
            goto LABEL_92;
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
LABEL_38:
        gpSysLocHashN = NamedLocaleHashNode;
        if ( !NamedLocaleHashNode )
          goto LABEL_39;
LABEL_41:
        RtlReleaseSRWLockExclusive(&gTblPtrsLock);
        v9 = gpSysLocHashN;
        goto LABEL_42;
      }
    }
    Handle = 0;
    if ( gNlsProcessLocalCache )
    {
      Handle = gNlsProcessLocalCache;
LABEL_17:
      v7 = Handle;
      NlsUpdateCacheInfo(&word_1803ABC18, Handle, 1);
      if ( word_1803AC294 == 3 && v7 )
        NtClose(v7);
      goto LABEL_20;
    }
    KeyHandle = 0;
    LODWORD(ObjectAttributes[0]) = 0;
    memset(&ObjectAttributes[1], 0, 44);
    DestinationString = 0;
    v28 = GetGlobalizationUserModelType();
    if ( v28 == 1 )
    {
      v29 = RtlOpenCurrentUser(0x2000000u, &KeyHandle);
    }
    else
    {
      v40 = v28 - 2;
      if ( v40 )
      {
        if ( v40 != 1 )
        {
LABEL_87:
          SetLastError_0(0x3F1u);
          goto LABEL_17;
        }
        HIDWORD(ObjectAttributes[0]) = 0;
        v29 = OpenGlobalizationUserSettingsKey_ForMua(0x2000000u, 0, &KeyHandle, (_DWORD *)ObjectAttributes + 1);
      }
      else
      {
        v29 = OpenGlobalizationUserSettingsKey_ForSingleUserModel(0x2000000u, &KeyHandle);
      }
    }
    if ( v29 >= 0 )
    {
      ApiMessage[0] = 0;
      v30 = ApiMessage;
      v31 = 512;
      do
      {
        if ( !*v30 )
          break;
        ++v30;
        --v31;
      }
      while ( v31 );
      if ( !v31 )
        goto LABEL_85;
      v32 = v31;
      v33 = &ApiMessage[512 - v31];
      do
      {
        if ( !v1 )
          break;
        if ( !*v2 )
          break;
        *v33++ = *v2++;
        --v1;
        --v32;
      }
      while ( v32 );
      v34 = v33 - 1;
      if ( v32 )
        v34 = v33;
      *v34 = 0;
      if ( v32 )
      {
        RtlInitUnicodeString(&DestinationString, ApiMessage);
        ObjectAttributes[2] = KeyHandle;
        LODWORD(ObjectAttributes[1]) = 48;
        ObjectAttributes[3] = &DestinationString;
        LODWORD(ObjectAttributes[4]) = 64;
        *(_OWORD *)&ObjectAttributes[5] = 0;
        LODWORD(ObjectAttributes[0]) = 0;
        v44 = NtOpenKey(&Handle, 0x20019u, (POBJECT_ATTRIBUTES)&ObjectAttributes[1]);
        if ( v44 < 0 )
          v44 = NtCreateKey(
                  &Handle,
                  0x20019u,
                  (POBJECT_ATTRIBUTES)&ObjectAttributes[1],
                  0,
                  0,
                  0,
                  (PULONG)ObjectAttributes);
        if ( KeyHandle )
          NtClose(KeyHandle);
        if ( v44 >= 0 )
        {
          v45 = Handle;
        }
        else
        {
          v45 = 0;
          Handle = 0;
        }
        if ( v44 >= 0 )
        {
          v46 = (void *)_InterlockedCompareExchange64(
                          (volatile signed __int64 *)&gNlsProcessLocalCache,
                          (signed __int64)v45,
                          0);
          if ( v46 )
          {
            if ( Handle )
              NtClose(Handle);
            Handle = v46;
          }
          goto LABEL_17;
        }
      }
      else
      {
LABEL_85:
        if ( KeyHandle )
          NtClose(KeyHandle);
      }
    }
    goto LABEL_87;
  }
}

```

## disassembly

```asm
0x18004a820  mov     r11, rsp
0x18004a823  push    rbp
0x18004a824  push    rbx
0x18004a825  lea     rbp, [r11-3E8h]
0x18004a82c  sub     rsp, 4D8h
0x18004a833  mov     rax, cs:__security_cookie
0x18004a83a  xor     rax, rsp
0x18004a83d  mov     [rbp+3E0h+var_30], rax
0x18004a844  mov     rbx, cs:gNlsProcessLocalCache
0x18004a84b  cmp     cs:BasepIsSecureProcess, 0
0x18004a852  jnz     loc_18004ABAD
0x18004a858  mov     [r11+10h], rdi
0x18004a85c  mov     edi, 200h
0x18004a861  mov     [r11+18h], r12
0x18004a865  xor     r12d, r12d
0x18004a868  mov     [r11-18h], r13
0x18004a86c  mov     [r11-20h], r14
0x18004a870  mov     r14d, 7FFFFFFEh
0x18004a876  mov     [r11-28h], r15
0x18004a87a  lea     r15, aControlPanelIn; "Control Panel\\International"
0x18004a881  test    rbx, rbx
0x18004a884  jnz     short loc_18004A8AC
0x18004a886  mov     rax, cs:gNlsProcessLocalCache
0x18004a88d  mov     [rsp+4E0h+Handle], r12
0x18004a892  test    rax, rax
0x18004a895  jz      loc_18004AC6D
0x18004a89b  mov     rax, cs:gNlsProcessLocalCache
0x18004a8a2  mov     [rsp+4E0h+Handle], rax
0x18004a8a7  mov     rbx, [rsp+4E0h+Handle]
0x18004a8ac  mov     r13d, 1
0x18004a8b2  test    rbx, rbx
0x18004a8b5  jz      short loc_18004A8E0
0x18004a8b7  mov     rax, cs:Event
0x18004a8be  test    rax, rax
0x18004a8c1  jz      loc_18004AEFE
0x18004a8c7  mov     rcx, cs:Event; hHandle
0x18004a8ce  xor     r8d, r8d; bAlertable
0x18004a8d1  xor     edx, edx; dwMilliseconds
0x18004a8d3  call    WaitForSingleObjectEx
0x18004a8d8  test    eax, eax
0x18004a8da  jz      loc_18004AEFE
0x18004a8e0  movzx   eax, cs:word_1803AC296
0x18004a8e7  test    ax, ax
0x18004a8ea  jz      loc_18004AB85
0x18004a8f0  movzx   eax, cs:word_1803AC294
0x18004a8f7  cmp     ax, 3
0x18004a8fb  jz      short loc_18004A921
0x18004a8fd  lea     rcx, gNlsProcessCacheLock
0x18004a904  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18004a90b  nop     dword ptr [rax+rax+00h]
0x18004a910  movzx   eax, cs:word_1803AC294
0x18004a917  cmp     ax, 3
0x18004a91b  jnz     loc_18004AC45
0x18004a921  mov     [rsp+4E0h+arg_0], rsi
0x18004a929  mov     ecx, 2
0x18004a92e  mov     cs:word_1803AC296, cx
0x18004a935  cmp     ax, r13w
0x18004a939  jnz     short loc_18004A97F
0x18004a93b  xor     edx, edx; Val
0x18004a93d  lea     rcx, [rbp+3E0h+ApiMessage]; void *
0x18004a941  mov     r8d, 3B8h; Size
0x18004a947  call    memset_0
0x18004a94c  mov     edx, 67Ch; BufferSize
0x18004a951  mov     ecx, r13d; ArgumentCount
0x18004a954  call    cs:__imp_CsrAllocateCaptureBuffer
0x18004a95b  nop     dword ptr [rax+rax+00h]
0x18004a960  mov     rbx, rax
0x18004a963  test    rax, rax
0x18004a966  jnz     loc_18004ABC7
0x18004a96c  mov     esi, 0C0000017h
0x18004a971  cmp     cs:word_1803AC294, r13w
0x18004a979  jz      loc_18004AC38
0x18004a97f  mov     rax, cs:gNlsProcessLocalCache
0x18004a986  mov     [rsp+4E0h+Handle], r12
0x18004a98b  test    rax, rax
0x18004a98e  jz      loc_18004AD62
0x18004a994  mov     rax, cs:gNlsProcessLocalCache
0x18004a99b  mov     [rsp+4E0h+Handle], rax
0x18004a9a0  mov     rbx, [rsp+4E0h+Handle]
0x18004a9a5  lea     rcx, word_1803ABC18
0x18004a9ac  mov     rdx, rbx
0x18004a9af  mov     r8d, r13d
0x18004a9b2  call    NlsUpdateCacheInfo
0x18004a9b7  cmp     cs:word_1803AC294, 3
0x18004a9bf  jnz     short loc_18004A9D5
0x18004a9c1  test    rbx, rbx
0x18004a9c4  jz      short loc_18004A9D5
0x18004a9c6  mov     rcx, rbx; Handle
0x18004a9c9  call    cs:__imp_NtClose
0x18004a9d0  nop     dword ptr [rax+rax+00h]
0x18004a9d5  mov     rsi, [rsp+4E0h+arg_0]
0x18004a9dd  mov     eax, 0FFFFh
0x18004a9e2  cmp     cs:word_1803ABC18, ax
0x18004a9e9  jz      loc_18004AC61
0x18004a9ef  mov     rbx, cs:gpOneCustomHashNode
0x18004a9f6  lea     rcx, word_1803ABC1A
0x18004a9fd  xor     edx, edx
0x18004a9ff  call    GetNamedLocaleHashNode
0x18004aa04  xchg    rax, cs:qword_1803ABC10
0x18004aa0b  test    rbx, rbx
0x18004aa0e  jnz     short loc_18004AA20
0x18004aa10  cmp     cs:gpOneCustomHashNode, r12
0x18004aa17  jz      short loc_18004AA20
0x18004aa19  mov     cs:gpOneCustomHashNode, r12
0x18004aa20  cmp     cs:qword_1803ABC10, r12
0x18004aa27  jnz     loc_18004AB57
0x18004aa2d  mov     rax, cs:gpSysLocHashN
0x18004aa34  test    rax, rax
0x18004aa37  jnz     loc_18004AB50
0x18004aa3d  cmp     cs:BasepIsSecureProcess, r12b
0x18004aa44  jnz     loc_18004AB50
0x18004aa4a  lea     rcx, gTblPtrsLock
0x18004aa51  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18004aa58  nop     dword ptr [rax+rax+00h]
0x18004aa5d  cmp     cs:gpSysLocHashN, r12
0x18004aa64  jnz     loc_18004AB36
0x18004aa6a  mov     ebx, cs:gSystemLocale
0x18004aa70  mov     rax, cs:P
0x18004aa77  mov     ecx, ebx
0x18004aa79  shr     rcx, 7
0x18004aa7d  xor     rcx, rbx
0x18004aa80  shr     rcx, 7
0x18004aa84  xor     rcx, rbx
0x18004aa87  and     ecx, 7Fh
0x18004aa8a  mov     rdx, [rax+rcx*8]
0x18004aa8e  test    rdx, rdx
0x18004aa91  jz      short loc_18004AA9B
0x18004aa93  cmp     [rdx], ebx
0x18004aa95  jnz     loc_18004AE92
0x18004aa9b  mov     cs:gpSysLocHashN, rdx
0x18004aaa2  test    rdx, rdx
0x18004aaa5  jnz     loc_18004AB36
0x18004aaab  test    ebx, 0FFF00000h
0x18004aab1  jnz     loc_18004AE86
0x18004aab7  cmp     cs:BasepIsSecureProcess, r12b
0x18004aabe  jnz     loc_18004AE86
0x18004aac4  mov     ecx, ebx
0x18004aac6  call    GetWindowsLocaleData
0x18004aacb  test    rax, rax
0x18004aace  jz      loc_18004AEA4
0x18004aad4  cmp     bx, 7Fh
0x18004aad8  jz      loc_18004AEEC
0x18004aade  shr     ebx, 10h
0x18004aae1  test    bl, 0Fh
0x18004aae4  jnz     loc_18004AE53
0x18004aaea  mov     ecx, [rax]
0x18004aaec  mov     rax, cs:qword_1803A6BD0
0x18004aaf3  add     rax, 2
0x18004aaf7  lea     rcx, [rax+rcx*2]
0x18004aafb  xor     edx, edx
0x18004aafd  call    MakeNamedLocaleHashNode
0x18004ab02  mov     cs:gpSysLocHashN, rax
0x18004ab09  test    rax, rax
0x18004ab0c  jnz     short loc_18004AB36
0x18004ab0e  xor     edx, edx
0x18004ab10  lea     rcx, aEnUs; "en-US"
0x18004ab17  call    MakeNamedLocaleHashNode
0x18004ab1c  mov     cs:gpSysLocHashN, rax
0x18004ab23  test    rax, rax
0x18004ab26  jnz     short loc_18004AB36
0x18004ab28  mov     rdx, cs:gpInvLocHashN
0x18004ab2f  mov     cs:gpSysLocHashN, rdx
0x18004ab36  lea     rcx, gTblPtrsLock
0x18004ab3d  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18004ab44  nop     dword ptr [rax+rax+00h]
0x18004ab49  mov     rax, cs:gpSysLocHashN
0x18004ab50  mov     cs:qword_1803ABC10, rax
0x18004ab57  mov     eax, 2
0x18004ab5c  mov     edx, r12d
0x18004ab5f  lock cmpxchg cs:word_1803AC296, dx
0x18004ab68  cmp     cs:word_1803AC294, 3
0x18004ab70  jz      short loc_18004AB85
0x18004ab72  lea     rcx, gNlsProcessCacheLock
0x18004ab79  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18004ab80  nop     dword ptr [rax+rax+00h]
0x18004ab85  mov     r14, [rsp+4E0h+var_18]
0x18004ab8d  mov     r13, [rsp+4D0h]
0x18004ab95  mov     r12, [rsp+4E0h+arg_10]
0x18004ab9d  mov     rdi, [rsp+4E0h+arg_8]
0x18004aba5  mov     r15, [rsp+4E0h+var_20]
0x18004abad  mov     rcx, [rbp+3E0h+var_30]
0x18004abb4  xor     rcx, rsp; StackCookie
0x18004abb7  call    __security_check_cookie
0x18004abbc  add     rsp, 4D8h
0x18004abc3  pop     rbx
0x18004abc4  pop     rbp
0x18004abc5  retn
0x18004abc7  lea     r9, [rbp+3E0h+CapturedData]; CapturedData
0x18004abcb  xor     edx, edx; MessageBuffer
0x18004abcd  mov     r8d, 67Ch; MessageLength
0x18004abd3  mov     rcx, rbx; CaptureBuffer
0x18004abd6  call    cs:__imp_CsrCaptureMessageBuffer
0x18004abdd  nop     dword ptr [rax+rax+00h]
0x18004abe2  mov     r9d, 10h; DataLength
0x18004abe8  mov     [rbp+3E0h+var_3E8], 67Ch
0x18004abef  mov     r8d, 1001Bh; ApiNumber
0x18004abf5  lea     rcx, [rbp+3E0h+ApiMessage]; ApiMessage
0x18004abf9  mov     rdx, rbx; CaptureBuffer
0x18004abfc  call    cs:__imp_CsrClientCallServer
0x18004ac03  nop     dword ptr [rax+rax+00h]
0x18004ac08  mov     esi, eax
0x18004ac0a  test    eax, eax
0x18004ac0c  js      short loc_18004AC24
0x18004ac0e  mov     rdx, [rbp+3E0h+CapturedData]; Src
0x18004ac12  lea     rcx, word_1803ABC18; void *
0x18004ac19  mov     r8d, 67Ch; Size
0x18004ac1f  call    memcpy_0
0x18004ac24  mov     rcx, rbx; CaptureBuffer
0x18004ac27  call    cs:__imp_CsrFreeCaptureBuffer
0x18004ac2e  nop     dword ptr [rax+rax+00h]
0x18004ac33  jmp     loc_18004A971
0x18004ac38  test    esi, esi
0x18004ac3a  jns     loc_18004A9D5
0x18004ac40  jmp     loc_18004A97F
0x18004ac45  movzx   eax, cs:word_1803AC296
0x18004ac4c  test    ax, ax
0x18004ac4f  jz      loc_18004AB72
0x18004ac55  movzx   eax, cs:word_1803AC294
0x18004ac5c  jmp     loc_18004A921
0x18004ac61  mov     cs:qword_1803ABC10, r12
0x18004ac68  jmp     loc_18004AA2D
0x18004ac6d  mov     rcx, [rsp+4E0h+Handle]
0x18004ac72  test    rcx, rcx
0x18004ac75  jnz     loc_18004B131
0x18004ac7b  xorps   xmm0, xmm0
0x18004ac7e  mov     [rsp+4E0h+KeyHandle], r12
0x18004ac83  movups  xmmword ptr [rsp+4E0h+ObjectAttributes+18h], xmm0
0x18004ac88  xor     eax, eax
0x18004ac8a  mov     dword ptr [rsp+4E0h+ObjectAttributes], r12d
0x18004ac8f  movups  xmmword ptr [rbp+3E0h+ObjectAttributes+24h], xmm0
0x18004ac93  movups  xmmword ptr [rsp+4E0h+ObjectAttributes+8], xmm0
0x18004ac98  movups  xmmword ptr [rbp+3E0h+DestinationString.Length], xmm0
0x18004ac9c  call    GetGlobalizationUserModelType
0x18004aca1  cmp     eax, 1
0x18004aca4  jnz     loc_18004AECF
0x18004acaa  lea     rdx, [rsp+4E0h+KeyHandle]; KeyHandle
0x18004acaf  mov     ecx, 2000000h; DesiredAccess
0x18004acb4  call    cs:__imp_RtlOpenCurrentUser
0x18004acbb  nop     dword ptr [rax+rax+00h]
0x18004acc0  test    eax, eax
0x18004acc2  js      loc_18004AD53
0x18004acc8  mov     [rbp+3E0h+ApiMessage], r12w
0x18004accd  lea     rax, [rbp+3E0h+ApiMessage]
0x18004acd1  mov     rcx, rdi
0x18004acd4  cmp     [rax], r12w
0x18004acd8  jz      short loc_18004ACE4
0x18004acda  add     rax, 2
0x18004acde  sub     rcx, 1
0x18004ace2  jnz     short loc_18004ACD4
0x18004ace4  mov     r9, rdi
0x18004ace7  sub     r9, rcx
0x18004acea  test    rcx, rcx
0x18004aced  cmovz   r9, r12
0x18004acf1  jz      short loc_18004AD3D
0x18004acf3  mov     r8, rdi
0x18004acf6  mov     rcx, r14
0x18004acf9  sub     r8, r9
0x18004acfc  mov     rdx, r15
0x18004acff  lea     r9, [rbp+r9*2+3E0h+ApiMessage]
0x18004ad04  jz      short loc_18004AD28
0x18004ad06  test    rcx, rcx
0x18004ad09  jz      short loc_18004AD28
0x18004ad0b  movzx   eax, word ptr [rdx]
0x18004ad0e  test    ax, ax
0x18004ad11  jz      short loc_18004AD28
0x18004ad13  mov     [r9], ax
0x18004ad17  add     rdx, 2
0x18004ad1b  add     r9, 2
0x18004ad1f  dec     rcx
0x18004ad22  sub     r8, 1
0x18004ad26  jnz     short loc_18004AD06
0x18004ad28  test    r8, r8
0x18004ad2b  lea     rcx, [r9-2]
0x18004ad2f  cmovnz  rcx, r9
0x18004ad33  mov     [rcx], r12w
0x18004ad37  jnz     loc_18004B06B
0x18004ad3d  mov     rcx, [rsp+4E0h+KeyHandle]; Handle
0x18004ad42  test    rcx, rcx
0x18004ad45  jz      short loc_18004AD53
0x18004ad47  call    cs:__imp_NtClose
0x18004ad4e  nop     dword ptr [rax+rax+00h]
0x18004ad53  mov     ecx, 3F1h; dwErrCode
0x18004ad58  call    SetLastError_0
0x18004ad5d  jmp     loc_18004A8A7
0x18004ad62  mov     rcx, [rsp+4E0h+Handle]
0x18004ad67  test    rcx, rcx
0x18004ad6a  jnz     loc_18004B227
0x18004ad70  xorps   xmm0, xmm0
0x18004ad73  mov     [rsp+4E0h+KeyHandle], r12
0x18004ad78  movups  xmmword ptr [rsp+4E0h+ObjectAttributes+18h], xmm0
0x18004ad7d  xor     eax, eax
0x18004ad7f  mov     dword ptr [rsp+4E0h+ObjectAttributes], r12d
0x18004ad84  movups  xmmword ptr [rbp+3E0h+ObjectAttributes+24h], xmm0
0x18004ad88  movups  xmmword ptr [rsp+4E0h+ObjectAttributes+8], xmm0
0x18004ad8d  movups  xmmword ptr [rbp+3E0h+DestinationString.Length], xmm0
0x18004ad91  call    GetGlobalizationUserModelType
0x18004ad96  cmp     eax, r13d
0x18004ad99  jnz     loc_18004AFF4
0x18004ad9f  lea     rdx, [rsp+4E0h+KeyHandle]; KeyHandle
0x18004ada4  mov     ecx, 2000000h; DesiredAccess
  ... truncated ...
```
