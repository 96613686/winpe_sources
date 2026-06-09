# CscpRegistryMonitorWorkerThreadRoutine

- ea: `0x140089590`
- end: `0x140089a39`
- name: `CscpRegistryMonitorWorkerThreadRoutine`
- size: `1193`
- prototype: `__int64 __fastcall(PKDPC Dpc)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140048130`

## callees

- `0x1400169d4`
- `0x140016a04`
- `0x140018930`
- `0x14001a69c`
- `0x140022764`
- `0x14002f010`
- `0x140089590`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140089747`
- `ntoskrnl!ZwClose` at `0x1400899d2`
- `ntoskrnl!ZwClose` at `0x14008f9ab`
- `ntoskrnl!ZwClose` at `0x140089747`
- `ntoskrnl!ZwClose` at `0x1400899d2`
- `ntoskrnl!ZwClose` at `0x14008f9ab`
- `ntoskrnl!ZwQueryValueKey` at `0x140089899`
- `ntoskrnl!ZwQueryValueKey` at `0x140089899`
- `ntoskrnl!ZwOpenKey` at `0x140089659`
- `ntoskrnl!ZwOpenKey` at `0x140089820`
- `ntoskrnl!ZwOpenKey` at `0x140089659`
- `ntoskrnl!ZwOpenKey` at `0x140089820`
- `ntoskrnl!KeSetTimer` at `0x140089765`
- `ntoskrnl!KeSetTimer` at `0x140089765`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14008996c`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14008996c`
- `ntoskrnl!ZwNotifyChangeKey` at `0x1400896ee`
- `ntoskrnl!ZwNotifyChangeKey` at `0x1400896ee`

## pseudocode

```c
char __fastcall CscpRegistryMonitorWorkerThreadRoutine(PKDPC Dpc)
{
  HANDLE *p_ProcessorHistory; // r12
  void *ProcessorHistory; // rcx
  NTSTATUS Timer_high; // eax
  int DeferredRoutine; // ebx
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx
  int v8; // r9d
  void *KeyHandle; // [rsp+58h] [rbp-B0h] BYREF
  ULONG ResultLength; // [rsp+60h] [rbp-A8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES v13; // [rsp+98h] [rbp-70h] BYREF
  __int128 KeyValueInformation; // [rsp+C8h] [rbp-40h] BYREF
  int v15; // [rsp+D8h] [rbp-30h]

  KeyHandle = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_2b75d2c79bf13edf2fcedbc11f778651_Traceguids, Dpc);
  p_ProcessorHistory = (HANDLE *)&Dpc[3].ProcessorHistory;
  ProcessorHistory = (void *)Dpc[3].ProcessorHistory;
  if ( ProcessorHistory )
  {
    ZwClose(ProcessorHistory);
    *p_ProcessorHistory = 0;
    LOBYTE(Timer_high) = KeSetTimer((PKTIMER)&Dpc[1], *(LARGE_INTEGER *)&Dpc[2].TargetInfoAsUlong, Dpc);
    DeferredRoutine = (int)Dpc[3].DeferredRoutine;
    if ( DeferredRoutine < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_37;
      Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (Timer_high & 0x20) == 0 )
        goto LABEL_37;
      v7 = 21;
LABEL_14:
      LOBYTE(Timer_high) = WPP_SF_d(
                             v6->AttachedDevice,
                             v7,
                             WPP_2b75d2c79bf13edf2fcedbc11f778651_Traceguids,
                             (unsigned int)DeferredRoutine);
      goto LABEL_37;
    }
  }
  else
  {
    memset(&ObjectAttributes.Length + 1, 0, 44);
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)Dpc[2].DpcData;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    Timer_high = ZwOpenKey((PHANDLE)&Dpc[3].ProcessorHistory, 0x20019u, &ObjectAttributes);
    DeferredRoutine = Timer_high;
    if ( Timer_high < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        LOBYTE(Timer_high) = WPP_SF_ZD(
                               WPP_GLOBAL_Control->AttachedDevice,
                               19,
                               (unsigned int)WPP_2b75d2c79bf13edf2fcedbc11f778651_Traceguids,
                               Dpc[2].DpcData,
                               Timer_high);
      goto LABEL_37;
    }
    Timer_high = ZwNotifyChangeKey(
                   *p_ProcessorHistory,
                   0,
                   (PIO_APC_ROUTINE)&Dpc[2].ProcessorHistory,
                   (PVOID)1,
                   (PIO_STATUS_BLOCK)&Dpc[3].DeferredRoutine,
                   4u,
                   1u,
                   0,
                   0,
                   1u);
    DeferredRoutine = Timer_high;
    if ( Timer_high < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_37;
      Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (Timer_high & 0x20) == 0 )
        goto LABEL_37;
      v7 = 20;
      goto LABEL_14;
    }
  }
  memset(&v13.Length + 1, 0, 44);
  ResultLength = 0;
  KeyValueInformation = 0;
  v15 = 0;
  v13.Length = 48;
  v13.Attributes = 576;
  v13.ObjectName = *(PUNICODE_STRING *)&Dpc[3].TargetInfoAsUlong;
  *(_OWORD *)&v13.SecurityDescriptor = 0;
  Timer_high = ZwOpenKey(&KeyHandle, 0x20019u, &v13);
  DeferredRoutine = Timer_high;
  if ( Timer_high >= 0 )
  {
    Timer_high = ZwQueryValueKey(
                   KeyHandle,
                   (PUNICODE_STRING)Dpc[3].DpcListEntry.Next,
                   KeyValuePartialInformation,
                   &KeyValueInformation,
                   0x14u,
                   &ResultLength);
    DeferredRoutine = Timer_high;
    if ( Timer_high >= 0 )
    {
      v8 = DWORD1(KeyValueInformation);
      if ( *(_QWORD *)((char *)&KeyValueInformation + 4) == __PAIR64__(DWORD1(KeyValueInformation), 4) )
      {
        if ( HIDWORD(KeyValueInformation) && !_InterlockedExchange((volatile __int32 *)&Dpc[3].SystemArgument1, 1) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
          {
            WPP_SF_(
              WPP_GLOBAL_Control->AttachedDevice,
              (unsigned int)(v8 + 21),
              WPP_2b75d2c79bf13edf2fcedbc11f778651_Traceguids);
          }
          Timer_high = ZwUpdateWnfStateData(&WNF_CSC_SERVICE_START, 0, 0, 0, 0, 0, 0);
          DeferredRoutine = Timer_high;
        }
      }
      else
      {
        DeferredRoutine = -1073741811;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
          if ( (Timer_high & 0x20) != 0 )
            LOBYTE(Timer_high) = WPP_SF_ddD(WPP_GLOBAL_Control->AttachedDevice);
        }
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (Timer_high & 0x20) != 0 )
        LOBYTE(Timer_high) = WPP_SF_ZD(
                               WPP_GLOBAL_Control->AttachedDevice,
                               23,
                               (unsigned int)WPP_2b75d2c79bf13edf2fcedbc11f778651_Traceguids,
                               Dpc[3].DpcListEntry.Next,
                               DeferredRoutine);
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (Timer_high & 0x20) != 0 )
      LOBYTE(Timer_high) = WPP_SF_ZD(
                             WPP_GLOBAL_Control->AttachedDevice,
                             22,
                             (unsigned int)WPP_2b75d2c79bf13edf2fcedbc11f778651_Traceguids,
                             *(_QWORD *)&Dpc[3].TargetInfoAsUlong,
                             DeferredRoutine);
  }
LABEL_37:
  if ( KeyHandle )
  {
    LOBYTE(Timer_high) = ZwClose(KeyHandle);
    KeyHandle = 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (Timer_high & 0x20) != 0 )
      LOBYTE(Timer_high) = WPP_SF_d(
                             WPP_GLOBAL_Control->AttachedDevice,
                             26,
                             WPP_2b75d2c79bf13edf2fcedbc11f778651_Traceguids,
                             (unsigned int)DeferredRoutine);
  }
  return Timer_high;
}

```

## disassembly

```asm
0x140089590  mov     [rsp+arg_8], rbx
0x140089595  mov     [rsp+arg_10], rdi
0x14008959a  push    r12
0x14008959c  push    r13
0x14008959e  push    r15
0x1400895a0  sub     rsp, 0F0h
0x1400895a7  mov     rax, cs:__security_cookie
0x1400895ae  xor     rax, rsp
0x1400895b1  mov     [rsp+108h+var_28], rax
0x1400895b9  mov     rdi, rcx
0x1400895bc  xor     r13d, r13d
0x1400895bf  mov     [rsp+108h+KeyHandle], r13
0x1400895c4  lea     r15, WPP_GLOBAL_Control
0x1400895cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400895d2  cmp     rcx, r15
0x1400895d5  jz      short loc_1400895F6
0x1400895d7  mov     eax, [rcx+2Ch]
0x1400895da  test    al, 20h
0x1400895dc  jz      short loc_1400895F6
0x1400895de  lea     edx, [r13+12h]
0x1400895e2  mov     r9, rdi
0x1400895e5  lea     r8, WPP_2b75d2c79bf13edf2fcedbc11f778651_Traceguids
0x1400895ec  mov     rcx, [rcx+18h]
0x1400895f0  call    WPP_SF_q
0x1400895f5  nop
0x1400895f6  lea     r12, [rdi+0D0h]
0x1400895fd  mov     rcx, [r12]; Handle
0x140089601  test    rcx, rcx
0x140089604  jnz     loc_140089747
0x14008960a  xorps   xmm0, xmm0
0x14008960d  movups  xmmword ptr [rsp+108h+ObjectAttributes.Length], xmm0
0x140089612  movups  xmmword ptr [rsp+108h+ObjectAttributes.ObjectName], xmm0
0x140089617  movups  xmmword ptr [rsp+108h+ObjectAttributes.SecurityDescriptor], xmm0
0x14008961f  mov     [rsp+108h+ObjectAttributes.Length], 30h ; '0'
0x140089627  mov     [rsp+108h+ObjectAttributes.RootDirectory], r13
0x14008962c  mov     [rsp+108h+ObjectAttributes.Attributes], 240h
0x140089637  mov     rax, [rdi+0B8h]
0x14008963e  mov     [rsp+108h+ObjectAttributes.ObjectName], rax
0x140089643  movdqu  xmmword ptr [rsp+108h+ObjectAttributes.SecurityDescriptor], xmm0
0x14008964c  lea     r8, [rsp+108h+ObjectAttributes]; ObjectAttributes
0x140089651  mov     edx, 20019h; DesiredAccess
0x140089656  mov     rcx, r12; KeyHandle
0x140089659  call    cs:__imp_ZwOpenKey
0x140089660  nop     dword ptr [rax+rax+00h]
0x140089665  mov     ebx, eax
0x140089667  mov     [rsp+108h+var_B8], eax
0x14008966b  test    eax, eax
0x14008966d  jns     short loc_1400896B0
0x14008966f  mov     rcx, cs:WPP_GLOBAL_Control
0x140089676  cmp     rcx, r15
0x140089679  jz      loc_1400899C8
0x14008967f  mov     edx, [rcx+2Ch]
0x140089682  test    dl, 20h
0x140089685  jz      loc_1400899C8
0x14008968b  mov     edx, 13h
0x140089690  mov     dword ptr [rsp+108h+IoStatusBlock], eax
0x140089694  mov     r9, [rdi+0B8h]
0x14008969b  lea     r8, WPP_2b75d2c79bf13edf2fcedbc11f778651_Traceguids
0x1400896a2  mov     rcx, [rcx+18h]
0x1400896a6  call    WPP_SF_ZD
0x1400896ab  jmp     loc_1400899C8
0x1400896b0  lea     rax, [rdi+0D8h]
0x1400896b7  lea     r8, [rdi+90h]; ApcRoutine
0x1400896be  mov     r15d, 1
0x1400896c4  mov     [rsp+108h+Asynchronous], r15b; Asynchronous
0x1400896c9  mov     [rsp+108h+BufferSize], r13d; BufferSize
0x1400896ce  mov     [rsp+108h+Buffer], r13; Buffer
0x1400896d3  mov     [rsp+108h+WatchTree], r15b; WatchTree
0x1400896d8  mov     [rsp+108h+CompletionFilter], 4; CompletionFilter
0x1400896e0  mov     [rsp+108h+IoStatusBlock], rax; IoStatusBlock
0x1400896e5  mov     r9d, r15d; ApcContext
0x1400896e8  xor     edx, edx; Event
0x1400896ea  mov     rcx, [r12]; KeyHandle
0x1400896ee  call    cs:__imp_ZwNotifyChangeKey
0x1400896f5  nop     dword ptr [rax+rax+00h]
0x1400896fa  mov     ebx, eax
0x1400896fc  mov     [rsp+108h+var_B8], eax
0x140089700  test    eax, eax
0x140089702  jns     loc_1400897A7
0x140089708  mov     rcx, cs:WPP_GLOBAL_Control
0x14008970f  lea     r15, WPP_GLOBAL_Control
0x140089716  cmp     rcx, r15
0x140089719  jz      loc_1400899C8
0x14008971f  mov     eax, [rcx+2Ch]
0x140089722  test    al, 20h
0x140089724  jz      loc_1400899C8
0x14008972a  mov     edx, 14h
0x14008972f  mov     r9d, ebx
0x140089732  lea     r8, WPP_2b75d2c79bf13edf2fcedbc11f778651_Traceguids
0x140089739  mov     rcx, [rcx+18h]
0x14008973d  call    WPP_SF_d
0x140089742  jmp     loc_1400899C8
0x140089747  call    cs:__imp_ZwClose
0x14008974e  nop     dword ptr [rax+rax+00h]
0x140089753  mov     [r12], r13
0x140089757  lea     rcx, [rdi+40h]; Timer
0x14008975b  mov     r8, rdi; Dpc
0x14008975e  mov     rdx, [rdi+80h]; DueTime
0x140089765  call    cs:__imp_KeSetTimer
0x14008976c  nop     dword ptr [rax+rax+00h]
0x140089771  mov     ebx, [rdi+0D8h]
0x140089777  mov     [rsp+108h+var_B8], ebx
0x14008977b  test    ebx, ebx
0x14008977d  jns     short loc_1400897A1
0x14008977f  mov     rcx, cs:WPP_GLOBAL_Control
0x140089786  cmp     rcx, r15
0x140089789  jz      loc_1400899C8
0x14008978f  mov     eax, [rcx+2Ch]
0x140089792  test    al, 20h
0x140089794  jz      loc_1400899C8
0x14008979a  mov     edx, 15h
0x14008979f  jmp     short loc_14008972F
0x1400897a1  mov     r15d, 1
0x1400897a7  xorps   xmm0, xmm0
0x1400897aa  movups  xmmword ptr [rsp+108h+var_70.Length], xmm0
0x1400897b2  movups  xmmword ptr [rsp+108h+var_70.ObjectName], xmm0
0x1400897ba  movups  xmmword ptr [rsp+108h+var_70.SecurityDescriptor], xmm0
0x1400897c2  mov     [rsp+108h+ResultLength], r13d
0x1400897c7  xor     eax, eax
0x1400897c9  movups  [rsp+108h+KeyValueInformation], xmm0
0x1400897d1  mov     [rsp+108h+var_30], eax
0x1400897d8  mov     [rsp+108h+var_70.Length], 30h ; '0'
0x1400897e3  mov     [rsp+108h+var_70.RootDirectory], r13
0x1400897eb  mov     [rsp+108h+var_70.Attributes], 240h
0x1400897f6  mov     rax, [rdi+0C0h]
0x1400897fd  mov     [rsp+108h+var_70.ObjectName], rax
0x140089805  movdqu  xmmword ptr [rsp+108h+var_70.SecurityDescriptor], xmm0
0x14008980e  lea     r8, [rsp+108h+var_70]; ObjectAttributes
0x140089816  mov     edx, 20019h; DesiredAccess
0x14008981b  lea     rcx, [rsp+108h+KeyHandle]; KeyHandle
0x140089820  call    cs:__imp_ZwOpenKey
0x140089827  nop     dword ptr [rax+rax+00h]
0x14008982c  mov     ebx, eax
0x14008982e  mov     [rsp+108h+var_B8], eax
0x140089832  test    eax, eax
0x140089834  jns     short loc_14008986D
0x140089836  mov     rcx, cs:WPP_GLOBAL_Control
0x14008983d  lea     r15, WPP_GLOBAL_Control
0x140089844  cmp     rcx, r15
0x140089847  jz      loc_1400899C8
0x14008984d  mov     eax, [rcx+2Ch]
0x140089850  test    al, 20h
0x140089852  jz      loc_1400899C8
0x140089858  mov     edx, 16h
0x14008985d  mov     dword ptr [rsp+108h+IoStatusBlock], ebx
0x140089861  mov     r9, [rdi+0C0h]
0x140089868  jmp     loc_14008969B
0x14008986d  lea     rax, [rsp+108h+ResultLength]
0x140089872  mov     qword ptr [rsp+108h+CompletionFilter], rax; ResultLength
0x140089877  mov     dword ptr [rsp+108h+IoStatusBlock], 14h; Length
0x14008987f  lea     r9, [rsp+108h+KeyValueInformation]; KeyValueInformation
0x140089887  mov     r8d, 2; KeyValueInformationClass
0x14008988d  mov     rdx, [rdi+0C8h]; ValueName
0x140089894  mov     rcx, [rsp+108h+KeyHandle]; KeyHandle
0x140089899  call    cs:__imp_ZwQueryValueKey
0x1400898a0  nop     dword ptr [rax+rax+00h]
0x1400898a5  mov     ebx, eax
0x1400898a7  mov     [rsp+108h+var_B8], eax
0x1400898ab  test    eax, eax
0x1400898ad  jns     short loc_1400898E6
0x1400898af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400898b6  lea     r15, WPP_GLOBAL_Control
0x1400898bd  cmp     rcx, r15
0x1400898c0  jz      loc_1400899C8
0x1400898c6  mov     eax, [rcx+2Ch]
0x1400898c9  test    al, 20h
0x1400898cb  jz      loc_1400899C8
0x1400898d1  mov     edx, 17h
0x1400898d6  mov     dword ptr [rsp+108h+IoStatusBlock], ebx
0x1400898da  mov     r9, [rdi+0C8h]
0x1400898e1  jmp     loc_14008969B
0x1400898e6  mov     r9d, dword ptr [rsp+108h+KeyValueInformation+4]
0x1400898ee  cmp     r9d, 4
0x1400898f2  jnz     loc_140089980
0x1400898f8  cmp     dword ptr [rsp+108h+KeyValueInformation+8], r9d
0x140089900  jnz     short loc_140089980
0x140089902  cmp     dword ptr [rsp+108h+KeyValueInformation+0Ch], r13d
0x14008990a  jz      loc_1400899C1
0x140089910  xchg    r15d, [rdi+0E8h]
0x140089917  test    r15d, r15d
0x14008991a  jnz     loc_1400899C1
0x140089920  mov     rcx, cs:WPP_GLOBAL_Control
0x140089927  lea     r15, WPP_GLOBAL_Control
0x14008992e  cmp     rcx, r15
0x140089931  jz      short loc_14008994E
0x140089933  mov     eax, [rcx+2Ch]
0x140089936  test    al, 20h
0x140089938  jz      short loc_14008994E
0x14008993a  lea     edx, [r9+15h]
0x14008993e  lea     r8, WPP_2b75d2c79bf13edf2fcedbc11f778651_Traceguids
0x140089945  mov     rcx, [rcx+18h]
0x140089949  call    WPP_SF_
0x14008994e  mov     dword ptr [rsp+108h+WatchTree], r13d
0x140089953  mov     [rsp+108h+CompletionFilter], r13d
0x140089958  mov     [rsp+108h+IoStatusBlock], r13
0x14008995d  xor     r9d, r9d
0x140089960  xor     r8d, r8d
0x140089963  xor     edx, edx
0x140089965  lea     rcx, WNF_CSC_SERVICE_START
0x14008996c  call    cs:__imp_ZwUpdateWnfStateData
0x140089973  nop     dword ptr [rax+rax+00h]
0x140089978  mov     ebx, eax
0x14008997a  mov     [rsp+108h+var_B8], eax
0x14008997e  jmp     short loc_1400899C8
0x140089980  mov     ebx, 0C000000Dh
0x140089985  mov     [rsp+108h+var_B8], ebx
0x140089989  mov     rcx, cs:WPP_GLOBAL_Control
0x140089990  lea     r15, WPP_GLOBAL_Control
0x140089997  cmp     rcx, r15
0x14008999a  jz      short loc_1400899C8
0x14008999c  mov     eax, [rcx+2Ch]
0x14008999f  test    al, 20h
0x1400899a1  jz      short loc_1400899C8
0x1400899a3  mov     [rsp+108h+CompletionFilter], 0C000000Dh
0x1400899ab  mov     eax, dword ptr [rsp+108h+KeyValueInformation+8]
0x1400899b2  mov     dword ptr [rsp+108h+IoStatusBlock], eax
0x1400899b6  mov     rcx, [rcx+18h]
0x1400899ba  call    WPP_SF_ddD
0x1400899bf  jmp     short loc_1400899C8
0x1400899c1  lea     r15, WPP_GLOBAL_Control
0x1400899c8  mov     rcx, [rsp+108h+KeyHandle]; Handle
0x1400899cd  test    rcx, rcx
0x1400899d0  jz      short loc_1400899E3
0x1400899d2  call    cs:__imp_ZwClose
0x1400899d9  nop     dword ptr [rax+rax+00h]
0x1400899de  mov     [rsp+108h+KeyHandle], r13
0x1400899e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400899ea  cmp     rcx, r15
0x1400899ed  jz      short loc_140089A0E
0x1400899ef  mov     eax, [rcx+2Ch]
0x1400899f2  test    al, 20h
0x1400899f4  jz      short loc_140089A0E
0x1400899f6  mov     edx, 1Ah
0x1400899fb  mov     r9d, ebx
0x1400899fe  lea     r8, WPP_2b75d2c79bf13edf2fcedbc11f778651_Traceguids
0x140089a05  mov     rcx, [rcx+18h]
0x140089a09  call    WPP_SF_d
0x140089a0e  mov     rcx, [rsp+108h+var_28]
0x140089a16  xor     rcx, rsp; StackCookie
0x140089a19  call    __security_check_cookie
0x140089a1e  lea     r11, [rsp+108h+var_18]
0x140089a26  mov     rbx, [r11+28h]
0x140089a2a  mov     rdi, [r11+30h]
0x140089a2e  mov     rsp, r11
0x140089a31  pop     r15
0x140089a33  pop     r13
0x140089a35  pop     r12
0x140089a37  retn
0x14008f999  push    rbp
0x14008f99b  sub     rsp, 50h
0x14008f99f  mov     rbp, rdx
0x14008f9a2  mov     rcx, [rbp+58h]; Handle
0x14008f9a6  test    rcx, rcx
0x14008f9a9  jz      short loc_14008F9B8
0x14008f9ab  call    cs:__imp_ZwClose
0x14008f9b2  nop     dword ptr [rax+rax+00h]
0x14008f9b7  nop
0x14008f9b8  add     rsp, 50h
0x14008f9bc  pop     rbp
0x14008f9bd  retn
```
