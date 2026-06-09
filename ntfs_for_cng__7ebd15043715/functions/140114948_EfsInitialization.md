# EfsInitialization

- ea: `0x140114948`
- end: `0x1401150ee`
- name: `EfsInitialization`
- size: `1958`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400dfa80`

## callees

- `0x140057868`
- `0x140057e78`
- `0x140057fdc`
- `0x1400581a8`
- `0x1400596c0`
- `0x1400df74c`
- `0x1400f7490`
- `0x140114804`
- `0x140114948`
- `0x14011a214`
- `0x14011a3cc`
- `0x14011d1b0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140114feb`
- `ntoskrnl!ObfDereferenceObject` at `0x140114feb`
- `ntoskrnl!ZwClose` at `0x140114bfc`
- `ntoskrnl!ZwClose` at `0x140114faa`
- `ntoskrnl!ZwClose` at `0x140114fd3`
- `ntoskrnl!ZwClose` at `0x140114bfc`
- `ntoskrnl!ZwClose` at `0x140114faa`
- `ntoskrnl!ZwClose` at `0x140114fd3`
- `ntoskrnl!PsCreateSystemThread` at `0x140114f92`
- `ntoskrnl!PsCreateSystemThread` at `0x140114f92`
- `ntoskrnl!ZwOpenKey` at `0x140114ae8`
- `ntoskrnl!ZwOpenKey` at `0x140114ae8`
- `ntoskrnl!ZwQueryValueKey` at `0x140114b61`
- `ntoskrnl!ZwQueryValueKey` at `0x140114bbc`
- `ntoskrnl!ZwQueryValueKey` at `0x140114b61`
- `ntoskrnl!ZwQueryValueKey` at `0x140114bbc`
- `ntoskrnl!ZwOpenFile` at `0x140114e17`
- `ntoskrnl!ZwOpenFile` at `0x140114e17`
- `ntoskrnl!RtlInitUnicodeString` at `0x140114a90`
- `ntoskrnl!RtlInitUnicodeString` at `0x140114b30`
- `ntoskrnl!RtlInitUnicodeString` at `0x140114b89`
- `ntoskrnl!RtlInitUnicodeString` at `0x140114c2d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140114dab`
- `ntoskrnl!RtlInitUnicodeString` at `0x140114eb9`
- `ntoskrnl!RtlInitUnicodeString` at `0x140114a90`
- `ntoskrnl!RtlInitUnicodeString` at `0x140114b30`
- `ntoskrnl!RtlInitUnicodeString` at `0x140114b89`
- `ntoskrnl!RtlInitUnicodeString` at `0x140114c2d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140114dab`
- `ntoskrnl!RtlInitUnicodeString` at `0x140114eb9`
- `ntoskrnl!KeInitializeEvent` at `0x1401149d3`
- `ntoskrnl!KeInitializeEvent` at `0x140114a31`
- `ntoskrnl!KeInitializeEvent` at `0x140114a5e`
- `ntoskrnl!KeInitializeEvent` at `0x140114c84`
- `ntoskrnl!KeInitializeEvent` at `0x140114cb1`
- `ntoskrnl!KeInitializeEvent` at `0x1401149d3`
- `ntoskrnl!KeInitializeEvent` at `0x140114a31`
- `ntoskrnl!KeInitializeEvent` at `0x140114a5e`
- `ntoskrnl!KeInitializeEvent` at `0x140114c84`
- `ntoskrnl!KeInitializeEvent` at `0x140114cb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140114be8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140114be8`
- `ntoskrnl!ZwOpenEvent` at `0x140114f44`
- `ntoskrnl!ZwOpenEvent` at `0x140114f44`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14011507e`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1401150b7`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14011507e`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1401150b7`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140114d1d`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140114d53`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140114d1d`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140114d53`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140115091`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1401150a4`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140115091`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1401150a4`
- `ntoskrnl!NtClose` at `0x14011506b`
- `ntoskrnl!NtClose` at `0x14011506b`
- `ntoskrnl!ExAllocatePool2` at `0x140114b0c`
- `ntoskrnl!ExAllocatePool2` at `0x140114b0c`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140114cec`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140114d84`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140114cec`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140114d84`
- `ntoskrnl!ZwCreateEvent` at `0x140114f13`
- `ntoskrnl!ZwCreateEvent` at `0x140114f13`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x140115005`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14011501f`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x140115039`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x140115053`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x140115005`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14011501f`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x140115039`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x140115053`

## string_xrefs

- `0x140114a6a`: `\Registry\Machine\System\CurrentControlSet\Services\NTFS\EFS\Parameters`
- `0x140114b7d`: `EFSKCACHEPERIOD`

## pseudocode

```c
__int64 EfsInitialization()
{
  _DWORD *Pool2; // rbx
  int v1; // ecx
  int inited; // ebx
  NTSTATUS v3; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-88h] BYREF
  struct _UNICODE_STRING v6; // [rsp+50h] [rbp-78h] BYREF
  struct _UNICODE_STRING v7; // [rsp+60h] [rbp-68h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-58h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-48h] BYREF
  ULONG ResultLength; // [rsp+D0h] [rbp+8h] BYREF
  void *KeyHandle; // [rsp+D8h] [rbp+10h] BYREF
  void *ThreadHandle; // [rsp+E0h] [rbp+18h] BYREF

  KeyHandle = 0;
  ResultLength = 0;
  v6 = 0;
  DestinationString = 0;
  v7 = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  TraceLoggingRegisterEx_EtwRegister_EtwSetInformation((char *)&dword_140092288, 0, 0);
  TlgRegisterAggregateProviderEx(&dword_140092250);
  stru_140092460.Owner = 0;
  stru_140092460.Count = 1;
  stru_140092460.Contention = 0;
  KeInitializeEvent(&stru_140092460.Event, SynchronizationEvent, 0);
  TlgRegisterAggregateProviderEx(&dword_1400922F8);
  memset(&EfsData, 0, 0x4C0u);
  dword_140093A84 = 50000000;
  stru_140093E98.Count = 1;
  stru_140093E98.Owner = 0;
  stru_140093E98.Contention = 0;
  KeInitializeEvent(&stru_140093E98.Event, SynchronizationEvent, 0);
  stru_140093EF0.Count = 1;
  stru_140093EF0.Owner = 0;
  stru_140093EF0.Contention = 0;
  KeInitializeEvent(&stru_140093EF0.Event, SynchronizationEvent, 0);
  qword_140093ED0 = 0;
  dword_140093ED8 = 0;
  qword_140093EE0 = 0;
  dword_140093EE8 = 0;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\NTFS\\EFS\\Parameters");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    Pool2 = (_DWORD *)ExAllocatePool2(64, 1024, 1836279365);
    if ( Pool2 )
    {
      RtlInitUnicodeString(&DestinationString, L"MaximumBlob");
      if ( ZwQueryValueKey(KeyHandle, &DestinationString, KeyValuePartialInformation, Pool2, 0x400u, &ResultLength) >= 0
        && Pool2[3] )
      {
        byte_140093DE5 = 1;
      }
      RtlInitUnicodeString(&DestinationString, L"EFSKCACHEPERIOD");
      if ( ZwQueryValueKey(KeyHandle, &DestinationString, KeyValuePartialInformation, Pool2, 0x400u, &ResultLength) >= 0 )
      {
        v1 = Pool2[3];
        if ( (unsigned int)(v1 - 2) <= 0x1C )
          dword_140093A84 = 10000000 * v1;
      }
      ExFreePoolWithTag(Pool2, 0);
    }
    ZwClose(KeyHandle);
  }
  EfsData = 79695364;
  byte_140093DE4 = 0;
  dword_140093DE8 = 0;
  RtlInitUnicodeString(&::DestinationString, AttrName);
  stru_140093C18.Count = 1;
  qword_140093BC8 = (__int64)&qword_140093BC0;
  qword_140093BC0 = (__int64)&qword_140093BC0;
  stru_140093C18.Owner = 0;
  qword_140093C10 = (__int64)&qword_140093C08;
  qword_140093C08 = (__int64)&qword_140093C08;
  stru_140093C18.Contention = 0;
  KeInitializeEvent(&stru_140093C18.Event, SynchronizationEvent, 0);
  stru_140093BD0.Count = 1;
  stru_140093BD0.Owner = 0;
  stru_140093BD0.Contention = 0;
  KeInitializeEvent(&stru_140093BD0.Event, SynchronizationEvent, 0);
  ExInitializeNPagedLookasideList(&stru_140093AC0, 0, 0, 0x200u, 0x20u, 0x6E6F6345u, 5u);
  ExInitializePagedLookasideList(&stru_140093B40, 0, 0, 0x200u, 0x40u, 0x68636F45u, 5u);
  ExInitializePagedLookasideList(&stru_140093C80, 0, 0, 0x200u, 0x20u, 0x6D736645u, 3u);
  ExInitializeNPagedLookasideList(&Lookaside, 0, 0, 0x200u, 0x80u, 0x6D736645u, 3u);
  inited = NtOfsRegisterCallBacks();
  if ( inited < 0 )
    goto LABEL_24;
  RtlInitUnicodeString(&v6, L"\\Device\\KsecDD");
  ObjectAttributes.ObjectName = &v6;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  inited = ZwOpenFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 7u, 0x20u);
  if ( inited < 0 )
    goto LABEL_24;
  inited = EfsInitAes(&qword_140093D80, &dword_140093D88, &dword_140093D8C);
  if ( inited < 0 )
    goto LABEL_24;
  inited = EfsInitXtsAes(&qword_140093D90, (UCHAR *)&dword_140093D98);
  if ( inited < 0 )
    goto LABEL_24;
  inited = EfsInitDes(&qword_140093DC0, &dword_140093DC8, &qword_140093DD0, &dword_140093DD8);
  if ( inited < 0 )
    goto LABEL_24;
  inited = EfsInitFekProtection();
  if ( inited < 0 )
    goto LABEL_24;
  EfsInitFips();
  RtlInitUnicodeString(&v7, L"\\EFSInitEvent");
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 0;
  ObjectAttributes.ObjectName = &v7;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = ZwCreateEvent(&Handle, 2u, &ObjectAttributes, NotificationEvent, 0);
  inited = v3;
  if ( v3 < 0 )
  {
    if ( v3 != -1073741771 )
      goto LABEL_24;
    inited = ZwOpenEvent(&Handle, 2u, &ObjectAttributes);
    if ( inited < 0 )
      goto LABEL_24;
  }
  inited = EfsRpcInit();
  if ( inited >= 0 )
  {
    ThreadHandle = 0;
    if ( PsCreateSystemThread(&ThreadHandle, 0x1FFFFFu, 0, 0, 0, EfspCheckEfsPolicy, 0) >= 0 )
      ZwClose(ThreadHandle);
    byte_140093DE4 = 1;
  }
  else
  {
LABEL_24:
    EfsRpcUnInit();
    if ( Handle )
      ZwClose(Handle);
    if ( Object )
      ObfDereferenceObject(Object);
    if ( qword_140093D80 )
      BCryptCloseAlgorithmProvider(qword_140093D80, 0);
    if ( qword_140093D90 )
      BCryptCloseAlgorithmProvider(qword_140093D90, 0);
    if ( qword_140093DC0 )
      BCryptCloseAlgorithmProvider(qword_140093DC0, 0);
    if ( qword_140093DD0 )
      BCryptCloseAlgorithmProvider(qword_140093DD0, 0);
    if ( FileHandle )
      NtClose(FileHandle);
    ExDeleteNPagedLookasideList(&stru_140093AC0);
    ExDeletePagedLookasideList(&stru_140093B40);
    ExDeletePagedLookasideList(&stru_140093C80);
    ExDeleteNPagedLookasideList(&Lookaside);
    memset(&EfsData, 0, 0x4C0u);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x140114948  mov     r11, rsp
0x14011494b  mov     [r11+20h], rbx
0x14011494f  push    rsi
0x140114950  push    rdi
0x140114951  push    r14
0x140114953  sub     rsp, 0B0h
0x14011495a  xorps   xmm0, xmm0
0x14011495d  lea     rcx, dword_140092288; CallbackContext
0x140114964  xorps   xmm1, xmm1
0x140114967  xor     esi, esi
0x140114969  movups  xmmword ptr [r11-38h], xmm0
0x14011496e  xor     eax, eax
0x140114970  mov     [r11+10h], rsi
0x140114974  xor     r8d, r8d
0x140114977  mov     [r11+8], esi
0x14011497b  xor     edx, edx
0x14011497d  movups  xmmword ptr [r11-2Ch], xmm0
0x140114982  movups  xmmword ptr [rsp+0C8h+var_78.Length], xmm0
0x140114987  movups  xmmword ptr [rsp+0C8h+DestinationString.Length], xmm1
0x14011498c  movups  xmmword ptr [rsp+0C8h+var_68.Length], xmm0
0x140114991  movups  xmmword ptr [rsp+0C8h+IoStatusBlock], xmm0
0x140114996  movups  xmmword ptr [r11-48h], xmm0
0x14011499b  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x1401149a0  xor     edx, edx
0x1401149a2  lea     rcx, dword_140092250; CallbackContext
0x1401149a9  call    TlgRegisterAggregateProviderEx
0x1401149ae  lea     r14d, [rsi+1]
0x1401149b2  mov     cs:stru_140092460.Owner, rsi
0x1401149b9  mov     edx, r14d; Type
0x1401149bc  mov     cs:stru_140092460.Count, r14d
0x1401149c3  xor     r8d, r8d; State
0x1401149c6  mov     cs:stru_140092460.Contention, esi
0x1401149cc  lea     rcx, stru_140092460.Event; Event
0x1401149d3  call    cs:__imp_KeInitializeEvent
0x1401149da  nop     dword ptr [rax+rax+00h]
0x1401149df  lea     rdx, EEL_EtwEventHandler
0x1401149e6  lea     rcx, dword_1400922F8; CallbackContext
0x1401149ed  call    TlgRegisterAggregateProviderEx
0x1401149f2  xor     edx, edx; Val
0x1401149f4  lea     rcx, EfsData; void *
0x1401149fb  mov     r8d, 4C0h; Size
0x140114a01  call    memset
0x140114a06  xor     r8d, r8d; State
0x140114a09  mov     cs:dword_140093A84, 2FAF080h
0x140114a13  mov     edx, r14d; Type
0x140114a16  mov     cs:stru_140093E98.Count, r14d
0x140114a1d  lea     rcx, stru_140093E98.Event; Event
0x140114a24  mov     cs:stru_140093E98.Owner, rsi
0x140114a2b  mov     cs:stru_140093E98.Contention, esi
0x140114a31  call    cs:__imp_KeInitializeEvent
0x140114a38  nop     dword ptr [rax+rax+00h]
0x140114a3d  xor     r8d, r8d; State
0x140114a40  mov     cs:stru_140093EF0.Count, r14d
0x140114a47  mov     edx, r14d; Type
0x140114a4a  mov     cs:stru_140093EF0.Owner, rsi
0x140114a51  lea     rcx, stru_140093EF0.Event; Event
0x140114a58  mov     cs:stru_140093EF0.Contention, esi
0x140114a5e  call    cs:__imp_KeInitializeEvent
0x140114a65  nop     dword ptr [rax+rax+00h]
0x140114a6a  lea     rdx, aRegistryMachin_3; "\\Registry\\Machine\\System\\CurrentCon"...
0x140114a71  mov     cs:qword_140093ED0, rsi
0x140114a78  lea     rcx, [rsp+0C8h+DestinationString]; DestinationString
0x140114a7d  mov     cs:dword_140093ED8, esi
0x140114a83  mov     cs:qword_140093EE0, rsi
0x140114a8a  mov     cs:dword_140093EE8, esi
0x140114a90  call    cs:__imp_RtlInitUnicodeString
0x140114a97  nop     dword ptr [rax+rax+00h]
0x140114a9c  lea     rax, [rsp+0C8h+DestinationString]
0x140114aa1  mov     [rsp+0C8h+ObjectAttributes.Length], 30h ; '0'
0x140114aac  xorps   xmm0, xmm0
0x140114aaf  mov     [rsp+0C8h+ObjectAttributes.ObjectName], rax
0x140114ab7  lea     r8, [rsp+0C8h+ObjectAttributes]; ObjectAttributes
0x140114abf  mov     [rsp+0C8h+ObjectAttributes.RootDirectory], rsi
0x140114ac7  mov     edx, 20019h; DesiredAccess
0x140114acc  mov     [rsp+0C8h+ObjectAttributes.Attributes], 240h
0x140114ad7  lea     rcx, [rsp+0C8h+KeyHandle]; KeyHandle
0x140114adf  movdqu  xmmword ptr [rsp+0C8h+ObjectAttributes.SecurityDescriptor], xmm0
0x140114ae8  call    cs:__imp_ZwOpenKey
0x140114aef  nop     dword ptr [rax+rax+00h]
0x140114af4  test    eax, eax
0x140114af6  js      loc_140114C08
0x140114afc  mov     edi, 400h
0x140114b01  lea     ecx, [rsi+40h]
0x140114b04  mov     edx, edi
0x140114b06  mov     r8d, 6D736645h
0x140114b0c  call    cs:__imp_ExAllocatePool2
0x140114b13  nop     dword ptr [rax+rax+00h]
0x140114b18  mov     rbx, rax
0x140114b1b  test    rax, rax
0x140114b1e  jz      loc_140114BF4
0x140114b24  lea     rdx, aMaximumblob; "MaximumBlob"
0x140114b2b  lea     rcx, [rsp+0C8h+DestinationString]; DestinationString
0x140114b30  call    cs:__imp_RtlInitUnicodeString
0x140114b37  nop     dword ptr [rax+rax+00h]
0x140114b3c  mov     rcx, [rsp+0C8h+KeyHandle]; KeyHandle
0x140114b44  lea     rax, [rsp+0C8h+arg_0]
0x140114b4c  mov     [rsp+0C8h+ResultLength], rax; ResultLength
0x140114b51  lea     r8d, [rsi+2]; KeyValueInformationClass
0x140114b55  mov     r9, rbx; KeyValueInformation
0x140114b58  mov     [rsp+0C8h+Length], edi; Length
0x140114b5c  lea     rdx, [rsp+0C8h+DestinationString]; ValueName
0x140114b61  call    cs:__imp_ZwQueryValueKey
0x140114b68  nop     dword ptr [rax+rax+00h]
0x140114b6d  test    eax, eax
0x140114b6f  js      short loc_140114B7D
0x140114b71  cmp     [rbx+0Ch], esi
0x140114b74  jz      short loc_140114B7D
0x140114b76  mov     cs:byte_140093DE5, r14b
0x140114b7d  lea     rdx, aEfskcacheperio; "EFSKCACHEPERIOD"
0x140114b84  lea     rcx, [rsp+0C8h+DestinationString]; DestinationString
0x140114b89  call    cs:__imp_RtlInitUnicodeString
0x140114b90  nop     dword ptr [rax+rax+00h]
0x140114b95  mov     rcx, [rsp+0C8h+KeyHandle]; KeyHandle
0x140114b9d  lea     rax, [rsp+0C8h+arg_0]
0x140114ba5  mov     [rsp+0C8h+ResultLength], rax; ResultLength
0x140114baa  lea     rdx, [rsp+0C8h+DestinationString]; ValueName
0x140114baf  mov     r9, rbx; KeyValueInformation
0x140114bb2  mov     [rsp+0C8h+Length], edi; Length
0x140114bb6  mov     r8d, 2; KeyValueInformationClass
0x140114bbc  call    cs:__imp_ZwQueryValueKey
0x140114bc3  nop     dword ptr [rax+rax+00h]
0x140114bc8  test    eax, eax
0x140114bca  js      short loc_140114BE3
0x140114bcc  mov     ecx, [rbx+0Ch]
0x140114bcf  lea     eax, [rcx-2]
0x140114bd2  cmp     eax, 1Ch
0x140114bd5  ja      short loc_140114BE3
0x140114bd7  imul    eax, ecx, 989680h
0x140114bdd  mov     cs:dword_140093A84, eax
0x140114be3  xor     edx, edx; Tag
0x140114be5  mov     rcx, rbx; P
0x140114be8  call    cs:__imp_ExFreePoolWithTag
0x140114bef  nop     dword ptr [rax+rax+00h]
0x140114bf4  mov     rcx, [rsp+0C8h+KeyHandle]; Handle
0x140114bfc  call    cs:__imp_ZwClose
0x140114c03  nop     dword ptr [rax+rax+00h]
0x140114c08  lea     rdx, AttrName; "$EFS"
0x140114c0f  mov     cs:EfsData, 4C00E04h
0x140114c19  lea     rcx, DestinationString; DestinationString
0x140114c20  mov     cs:byte_140093DE4, sil
0x140114c27  mov     cs:dword_140093DE8, esi
0x140114c2d  call    cs:__imp_RtlInitUnicodeString
0x140114c34  nop     dword ptr [rax+rax+00h]
0x140114c39  lea     rax, qword_140093BC0
0x140114c40  mov     cs:stru_140093C18.Count, r14d
0x140114c47  mov     cs:qword_140093BC8, rax
0x140114c4e  lea     rcx, stru_140093C18.Event; Event
0x140114c55  mov     cs:qword_140093BC0, rax
0x140114c5c  xor     r8d, r8d; State
0x140114c5f  lea     rax, qword_140093C08
0x140114c66  mov     cs:stru_140093C18.Owner, rsi
0x140114c6d  mov     edx, r14d; Type
0x140114c70  mov     cs:qword_140093C10, rax
0x140114c77  mov     cs:qword_140093C08, rax
0x140114c7e  mov     cs:stru_140093C18.Contention, esi
0x140114c84  call    cs:__imp_KeInitializeEvent
0x140114c8b  nop     dword ptr [rax+rax+00h]
0x140114c90  xor     r8d, r8d; State
0x140114c93  mov     cs:stru_140093BD0.Count, r14d
0x140114c9a  mov     edx, r14d; Type
0x140114c9d  mov     cs:stru_140093BD0.Owner, rsi
0x140114ca4  lea     rcx, stru_140093BD0.Event; Event
0x140114cab  mov     cs:stru_140093BD0.Contention, esi
0x140114cb1  call    cs:__imp_KeInitializeEvent
0x140114cb8  nop     dword ptr [rax+rax+00h]
0x140114cbd  mov     ebx, 5
0x140114cc2  lea     rcx, stru_140093AC0; Lookaside
0x140114cc9  mov     [rsp+0C8h+Depth], bx; Depth
0x140114cce  mov     edi, 200h
0x140114cd3  mov     dword ptr [rsp+0C8h+ResultLength], 6E6F6345h; Tag
0x140114cdb  mov     r9d, edi; Flags
0x140114cde  xor     r8d, r8d; Free
0x140114ce1  mov     qword ptr [rsp+0C8h+Length], 20h ; ' '; Size
0x140114cea  xor     edx, edx; Allocate
0x140114cec  call    cs:__imp_ExInitializeNPagedLookasideList
0x140114cf3  nop     dword ptr [rax+rax+00h]
0x140114cf8  mov     [rsp+0C8h+Depth], bx; Depth
0x140114cfd  lea     rcx, stru_140093B40; Lookaside
0x140114d04  mov     dword ptr [rsp+0C8h+ResultLength], 68636F45h; Tag
0x140114d0c  mov     r9d, edi; Flags
0x140114d0f  xor     r8d, r8d; Free
0x140114d12  mov     qword ptr [rsp+0C8h+Length], 40h ; '@'; Size
0x140114d1b  xor     edx, edx; Allocate
0x140114d1d  call    cs:__imp_ExInitializePagedLookasideList
0x140114d24  nop     dword ptr [rax+rax+00h]
0x140114d29  mov     ebx, 3
0x140114d2e  lea     rcx, stru_140093C80; Lookaside
0x140114d35  mov     [rsp+0C8h+Depth], bx; Depth
0x140114d3a  mov     r9d, edi; Flags
0x140114d3d  mov     dword ptr [rsp+0C8h+ResultLength], 6D736645h; Tag
0x140114d45  xor     r8d, r8d; Free
0x140114d48  xor     edx, edx; Allocate
0x140114d4a  mov     qword ptr [rsp+0C8h+Length], 20h ; ' '; Size
0x140114d53  call    cs:__imp_ExInitializePagedLookasideList
0x140114d5a  nop     dword ptr [rax+rax+00h]
0x140114d5f  mov     [rsp+0C8h+Depth], bx; Depth
0x140114d64  lea     rcx, Lookaside; Lookaside
0x140114d6b  mov     dword ptr [rsp+0C8h+ResultLength], 6D736645h; Tag
0x140114d73  mov     r9d, edi; Flags
0x140114d76  xor     r8d, r8d; Free
0x140114d79  mov     qword ptr [rsp+0C8h+Length], 80h; Size
0x140114d82  xor     edx, edx; Allocate
0x140114d84  call    cs:__imp_ExInitializeNPagedLookasideList
0x140114d8b  nop     dword ptr [rax+rax+00h]
0x140114d90  call    NtOfsRegisterCallBacks
0x140114d95  mov     ebx, eax
0x140114d97  test    eax, eax
0x140114d99  js      loc_140114FC2
0x140114d9f  lea     rdx, aDeviceKsecdd; "\\Device\\KsecDD"
0x140114da6  lea     rcx, [rsp+0C8h+var_78]; DestinationString
0x140114dab  call    cs:__imp_RtlInitUnicodeString
0x140114db2  nop     dword ptr [rax+rax+00h]
0x140114db7  lea     rax, [rsp+0C8h+var_78]
0x140114dbc  mov     dword ptr [rsp+0C8h+ResultLength], 20h ; ' '; OpenOptions
0x140114dc4  xorps   xmm0, xmm0
0x140114dc7  mov     [rsp+0C8h+ObjectAttributes.ObjectName], rax
0x140114dcf  lea     r9, [rsp+0C8h+IoStatusBlock]; IoStatusBlock
0x140114dd4  mov     [rsp+0C8h+ObjectAttributes.Length], 30h ; '0'
0x140114ddf  lea     r8, [rsp+0C8h+ObjectAttributes]; ObjectAttributes
0x140114de7  mov     [rsp+0C8h+ObjectAttributes.RootDirectory], rsi
0x140114def  mov     edx, 100001h; DesiredAccess
0x140114df4  mov     [rsp+0C8h+ObjectAttributes.Attributes], 240h
0x140114dff  lea     rcx, FileHandle; FileHandle
0x140114e06  mov     [rsp+0C8h+Length], 7; ShareAccess
0x140114e0e  movdqu  xmmword ptr [rsp+0C8h+ObjectAttributes.SecurityDescriptor], xmm0
0x140114e17  call    cs:__imp_ZwOpenFile
0x140114e1e  nop     dword ptr [rax+rax+00h]
0x140114e23  mov     ebx, eax
0x140114e25  test    eax, eax
0x140114e27  js      loc_140114FC2
0x140114e2d  lea     r8, dword_140093D8C
0x140114e34  lea     rdx, dword_140093D88
0x140114e3b  lea     rcx, qword_140093D80
0x140114e42  call    EfsInitAes
0x140114e47  mov     ebx, eax
0x140114e49  test    eax, eax
0x140114e4b  js      loc_140114FC2
0x140114e51  lea     rdx, dword_140093D98
0x140114e58  lea     rcx, qword_140093D90
0x140114e5f  call    EfsInitXtsAes
0x140114e64  mov     ebx, eax
0x140114e66  test    eax, eax
0x140114e68  js      loc_140114FC2
0x140114e6e  lea     r9, dword_140093DD8
0x140114e75  lea     r8, qword_140093DD0
0x140114e7c  lea     rdx, dword_140093DC8
0x140114e83  lea     rcx, qword_140093DC0
0x140114e8a  call    EfsInitDes
0x140114e8f  mov     ebx, eax
0x140114e91  test    eax, eax
0x140114e93  js      loc_140114FC2
0x140114e99  call    EfsInitFekProtection
0x140114e9e  mov     ebx, eax
0x140114ea0  test    eax, eax
0x140114ea2  js      loc_140114FC2
0x140114ea8  call    EfsInitFips
0x140114ead  lea     rdx, aEfsinitevent; "\\EFSInitEvent"
0x140114eb4  lea     rcx, [rsp+0C8h+var_68]; DestinationString
0x140114eb9  call    cs:__imp_RtlInitUnicodeString
0x140114ec0  nop     dword ptr [rax+rax+00h]
0x140114ec5  xor     r9d, r9d; EventType
0x140114ec8  mov     [rsp+0C8h+ObjectAttributes.Length], 30h ; '0'
0x140114ed3  lea     rax, [rsp+0C8h+var_68]
0x140114ed8  mov     [rsp+0C8h+ObjectAttributes.RootDirectory], rsi
0x140114ee0  xorps   xmm0, xmm0
0x140114ee3  mov     [rsp+0C8h+ObjectAttributes.Attributes], esi
0x140114eea  lea     r8, [rsp+0C8h+ObjectAttributes]; ObjectAttributes
0x140114ef2  mov     [rsp+0C8h+ObjectAttributes.ObjectName], rax
0x140114efa  lea     edx, [r9+2]; DesiredAccess
0x140114efe  mov     byte ptr [rsp+0C8h+Length], sil; InitialState
0x140114f03  lea     rcx, Handle; EventHandle
0x140114f0a  movdqu  xmmword ptr [rsp+0C8h+ObjectAttributes.SecurityDescriptor], xmm0
0x140114f13  call    cs:__imp_ZwCreateEvent
0x140114f1a  nop     dword ptr [rax+rax+00h]
0x140114f1f  mov     ebx, eax
0x140114f21  test    eax, eax
0x140114f23  jns     short loc_140114F56
0x140114f25  cmp     eax, 0C0000035h
0x140114f2a  jnz     loc_140114FC2
0x140114f30  lea     r8, [rsp+0C8h+ObjectAttributes]; ObjectAttributes
0x140114f38  mov     edx, 2; DesiredAccess
0x140114f3d  lea     rcx, Handle; EventHandle
0x140114f44  call    cs:__imp_ZwOpenEvent
0x140114f4b  nop     dword ptr [rax+rax+00h]
0x140114f50  mov     ebx, eax
0x140114f52  test    eax, eax
0x140114f54  js      short loc_140114FC2
0x140114f56  call    EfsRpcInit
0x140114f5b  mov     ebx, eax
0x140114f5d  test    eax, eax
0x140114f5f  js      short loc_140114FC2
0x140114f61  lea     rax, EfspCheckEfsPolicy
0x140114f68  mov     qword ptr [rsp+0C8h+Depth], rsi; StartContext
0x140114f6d  mov     [rsp+0C8h+ResultLength], rax; StartRoutine
0x140114f72  lea     rcx, [rsp+0C8h+ThreadHandle]; ThreadHandle
0x140114f7a  xor     r9d, r9d; ProcessHandle
0x140114f7d  mov     qword ptr [rsp+0C8h+Length], rsi; ClientId
0x140114f82  xor     r8d, r8d; ObjectAttributes
0x140114f85  mov     [rsp+0C8h+ThreadHandle], rsi
0x140114f8d  mov     edx, 1FFFFFh; DesiredAccess
  ... truncated ...
```
