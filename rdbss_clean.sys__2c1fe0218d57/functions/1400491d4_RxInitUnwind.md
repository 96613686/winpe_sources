# RxInitUnwind

- ea: `0x1400491d4`
- end: `0x1400494ac`
- name: `RxInitUnwind`
- size: `728`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400499a0`
- `0x14008321c`

## callees

- `0x14001d330`
- `0x140025d00`
- `0x1400491d4`
- `0x14004ad3c`
- `0x1400524d4`
- `0x1400645f0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400493ef`
- `ntoskrnl!KeSetEvent` at `0x1400493ef`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400493bc`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400493bc`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400493cd`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400493cd`
- `ntoskrnl!ObfDereferenceObject` at `0x140049426`
- `ntoskrnl!ObfDereferenceObject` at `0x140049426`
- `ntoskrnl!ZwClose` at `0x1400492e1`
- `ntoskrnl!ZwClose` at `0x1400492e1`
- `ntoskrnl!IoDeleteDevice` at `0x1400493a4`
- `ntoskrnl!IoDeleteDevice` at `0x1400493a4`
- `ntoskrnl!KeFreeCalloutStack` at `0x140049243`
- `ntoskrnl!KeFreeCalloutStack` at `0x140049266`
- `ntoskrnl!KeFreeCalloutStack` at `0x140049243`
- `ntoskrnl!KeFreeCalloutStack` at `0x140049266`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x140049470`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x140049470`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049489`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049489`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400492b1`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400492b1`
- `ntoskrnl!PsUnregisterSiloMonitor` at `0x140049289`
- `ntoskrnl!PsUnregisterSiloMonitor` at `0x140049289`
- `ntoskrnl!KeWaitForSingleObject` at `0x140049413`
- `ntoskrnl!KeWaitForSingleObject` at `0x140049413`

## pseudocode

```c
void __fastcall RxInitUnwind(__int64 a1, int a2, __int64 a3)
{
  int v3; // edx
  int v4; // edx
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  int v9; // edx
  int i; // ebx
  struct _LIST_ENTRY *Flink; // rcx
  struct _LIST_ENTRY *Blink; // rdx
  struct _LIST_ENTRY *v13; // rcx
  _BYTE *Alignment; // rbx
  unsigned int v15; // edi
  unsigned __int64 v16; // rcx
  UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF

  DestinationString = 0;
  if ( !a2 )
  {
    if ( *(_QWORD *)&RxContextLookasideList.L.Depth )
    {
      KeFreeCalloutStack();
      *(_QWORD *)&RxContextLookasideList.L.Depth = 0;
    }
    if ( RxContextLookasideList.L.ListHead.Region )
    {
      KeFreeCalloutStack();
      RxContextLookasideList.L.ListHead.Region = 0;
    }
    goto LABEL_15;
  }
  v3 = a2 - 1;
  if ( !v3 )
  {
LABEL_15:
    if ( g_RxSiloMonitor )
    {
      PsUnregisterSiloMonitor();
      g_RxSiloMonitor = 0;
      g_RxSiloContextSlot = -1;
    }
    goto LABEL_17;
  }
  v4 = v3 - 1;
  if ( !v4 || (v5 = v4 - 1) == 0 )
  {
LABEL_17:
    ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)&WPP_MAIN_CB.DeviceQueue);
    for ( i = (int)WPP_MAIN_CB.Queue.Wcb.DeviceRoutine; i > 0; --i )
    {
      --LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceRoutine);
      ZwClose(*((HANDLE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + (unsigned int)i - 1));
    }
    goto LABEL_20;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
LABEL_20:
    RxUninitializePowerPolicy();
LABEL_21:
    Flink = RxFileSystemDeviceObject->RxNetNameTableInDeviceObject.HashBuckets[29].Flink;
    if ( Flink )
    {
      RxSecurityDescriptorDelete(Flink);
      RxFileSystemDeviceObject->RxNetNameTableInDeviceObject.HashBuckets[29].Flink = 0;
    }
    Blink = RxFileSystemDeviceObject->RxNetNameTableInDeviceObject.HashBuckets[27].Blink;
    if ( Blink )
    {
      LOBYTE(a3) = 1;
      RdbssStatisticsIoctlReleaseEntries(
        RxFileSystemDeviceObject->RxNetNameTableInDeviceObject.HashBuckets[27].Flink,
        Blink,
        a3);
      RdbssStatisticsDatabaseDeleteInstance(RxFileSystemDeviceObject->RxNetNameTableInDeviceObject.HashBuckets[27].Blink);
      RxFileSystemDeviceObject->RxNetNameTableInDeviceObject.HashBuckets[27].Blink = 0;
    }
    v13 = RxFileSystemDeviceObject->RxNetNameTableInDeviceObject.HashBuckets[27].Flink;
    if ( v13 )
    {
      ((void (*)(void))v13->Flink)();
      RxFileSystemDeviceObject->RxNetNameTableInDeviceObject.HashBuckets[27].Flink = 0;
    }
    IoDeleteDevice(&RxFileSystemDeviceObject->DeviceObject);
    goto LABEL_28;
  }
  v7 = v6 - 1;
  if ( !v7 )
    goto LABEL_21;
  v8 = v7 - 1;
  if ( !v8 )
    goto LABEL_21;
  v9 = v8 - 1;
  if ( v9 )
  {
    if ( v9 != 1 )
      goto LABEL_32;
    goto LABEL_29;
  }
LABEL_28:
  RtlInitUnicodeString(&DestinationString, L"\\??\\fsWrap");
  IoDeleteSymbolicLink(&DestinationString);
LABEL_29:
  if ( Object )
  {
    KeSetEvent((PRKEVENT)&WPP_MAIN_CB.DeviceExtension, 0, 0);
    KeWaitForSingleObject(Object, Executive, 0, 0, 0);
    ObfDereferenceObject(Object);
  }
  Object = 0;
  qword_140043098 = 0;
LABEL_32:
  Alignment = (_BYTE *)RxContextLookasideList.L.ListHead.Alignment;
  if ( RxContextLookasideList.L.ListHead.Alignment )
  {
    v15 = *(_DWORD *)RxContextLookasideList.L.ListHead.Alignment;
    while ( (--v15 & 0x80000000) == 0 )
    {
      v16 = (unsigned __int64)v15 << 7;
      if ( Alignment[v16 + 176] )
        ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)&Alignment[v16 + 64]);
    }
    ExFreePoolWithTag(Alignment, 0x734D7852u);
    RxContextLookasideList.L.ListHead.Alignment = 0;
  }
}

```

## disassembly

```asm
0x1400491d4  mov     [rsp+arg_0], rbx
0x1400491d9  push    rdi
0x1400491da  sub     rsp, 40h
0x1400491de  xorps   xmm0, xmm0
0x1400491e1  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x1400491e6  test    edx, edx
0x1400491e8  jz      short loc_140049237
0x1400491ea  sub     edx, 1
0x1400491ed  jz      loc_14004927D
0x1400491f3  sub     edx, 1
0x1400491f6  jz      loc_1400492AA
0x1400491fc  sub     edx, 1
0x1400491ff  jz      loc_1400492AA
0x140049205  sub     edx, 1
0x140049208  jz      loc_1400492F3
0x14004920e  sub     edx, 1
0x140049211  jz      loc_1400492F8
0x140049217  sub     edx, 1
0x14004921a  jz      loc_1400492F8
0x140049220  sub     edx, 1
0x140049223  jz      loc_1400493B0
0x140049229  cmp     edx, 1
0x14004922c  jz      loc_1400493D9
0x140049232  jmp     loc_140049448
0x140049237  mov     rcx, qword ptr cs:RxContextLookasideList.L.Depth
0x14004923e  test    rcx, rcx
0x140049241  jz      short loc_14004925A
0x140049243  call    cs:__imp_KeFreeCalloutStack
0x14004924a  nop     dword ptr [rax+rax+00h]
0x14004924f  mov     qword ptr cs:RxContextLookasideList.L.Depth, 0
0x14004925a  mov     rcx, qword ptr cs:RxContextLookasideList.L+8
0x140049261  test    rcx, rcx
0x140049264  jz      short loc_14004927D
0x140049266  call    cs:__imp_KeFreeCalloutStack
0x14004926d  nop     dword ptr [rax+rax+00h]
0x140049272  mov     qword ptr cs:RxContextLookasideList.L+8, 0
0x14004927d  mov     rcx, cs:g_RxSiloMonitor
0x140049284  test    rcx, rcx
0x140049287  jz      short loc_1400492AA
0x140049289  call    cs:__imp_PsUnregisterSiloMonitor
0x140049290  nop     dword ptr [rax+rax+00h]
0x140049295  mov     cs:g_RxSiloMonitor, 0
0x1400492a0  mov     cs:g_RxSiloContextSlot, 0FFFFFFFFh
0x1400492aa  lea     rcx, WPP_MAIN_CB.DeviceQueue; RunRef
0x1400492b1  call    cs:__imp_ExWaitForRundownProtectionRelease
0x1400492b8  nop     dword ptr [rax+rax+00h]
0x1400492bd  mov     ebx, dword ptr cs:WPP_MAIN_CB.Queue+18h
0x1400492c3  jmp     short loc_1400492EF
0x1400492c5  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+18h
0x1400492cb  dec     eax
0x1400492cd  mov     ecx, ebx
0x1400492cf  mov     dword ptr cs:WPP_MAIN_CB.Queue+18h, eax
0x1400492d5  lea     rax, WPP_MAIN_CB.Queue+10h
0x1400492dc  mov     rcx, [rax+rcx*8-8]; Handle
0x1400492e1  call    cs:__imp_ZwClose
0x1400492e8  nop     dword ptr [rax+rax+00h]
0x1400492ed  dec     ebx
0x1400492ef  test    ebx, ebx
0x1400492f1  jg      short loc_1400492C5
0x1400492f3  call    RxUninitializePowerPolicy
0x1400492f8  mov     rax, cs:RxFileSystemDeviceObject
0x1400492ff  mov     rcx, [rax+508h]; P
0x140049306  test    rcx, rcx
0x140049309  jz      short loc_140049329
0x14004930b  movzx   edx, byte ptr [rax+510h]
0x140049312  call    RxSecurityDescriptorDelete
0x140049317  mov     rax, cs:RxFileSystemDeviceObject
0x14004931e  mov     qword ptr [rax+508h], 0
0x140049329  mov     rcx, cs:RxFileSystemDeviceObject
0x140049330  mov     rdx, [rcx+4F0h]
0x140049337  test    rdx, rdx
0x14004933a  jz      short loc_140049370
0x14004933c  mov     rcx, [rcx+4E8h]
0x140049343  mov     r8b, 1
0x140049346  call    RdbssStatisticsIoctlReleaseEntries
0x14004934b  mov     rcx, cs:RxFileSystemDeviceObject
0x140049352  mov     rcx, [rcx+4F0h]
0x140049359  call    RdbssStatisticsDatabaseDeleteInstance
0x14004935e  mov     rax, cs:RxFileSystemDeviceObject
0x140049365  mov     qword ptr [rax+4F0h], 0
0x140049370  mov     rax, cs:RxFileSystemDeviceObject
0x140049377  mov     rcx, [rax+4E8h]
0x14004937e  test    rcx, rcx
0x140049381  jz      short loc_14004939D
0x140049383  mov     rax, [rcx]
0x140049386  call    _guard_dispatch_icall
0x14004938b  mov     rax, cs:RxFileSystemDeviceObject
0x140049392  mov     qword ptr [rax+4E8h], 0
0x14004939d  mov     rcx, cs:RxFileSystemDeviceObject; DeviceObject
0x1400493a4  call    cs:__imp_IoDeleteDevice
0x1400493ab  nop     dword ptr [rax+rax+00h]
0x1400493b0  lea     rdx, SourceString; "\\??\\fsWrap"
0x1400493b7  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x1400493bc  call    cs:__imp_RtlInitUnicodeString
0x1400493c3  nop     dword ptr [rax+rax+00h]
0x1400493c8  lea     rcx, [rsp+48h+DestinationString]; SymbolicLinkName
0x1400493cd  call    cs:__imp_IoDeleteSymbolicLink
0x1400493d4  nop     dword ptr [rax+rax+00h]
0x1400493d9  cmp     cs:Object, 0
0x1400493e1  jz      short loc_140049432
0x1400493e3  xor     r8d, r8d; Wait
0x1400493e6  lea     rcx, WPP_MAIN_CB.DeviceExtension; Event
0x1400493ed  xor     edx, edx; Increment
0x1400493ef  call    cs:__imp_KeSetEvent
0x1400493f6  nop     dword ptr [rax+rax+00h]
0x1400493fb  mov     rcx, cs:Object; Object
0x140049402  xor     r9d, r9d; Alertable
0x140049405  xor     r8d, r8d; WaitMode
0x140049408  mov     [rsp+48h+Timeout], 0; Timeout
0x140049411  xor     edx, edx; WaitReason
0x140049413  call    cs:__imp_KeWaitForSingleObject
0x14004941a  nop     dword ptr [rax+rax+00h]
0x14004941f  mov     rcx, cs:Object; Object
0x140049426  call    cs:__imp_ObfDereferenceObject
0x14004942d  nop     dword ptr [rax+rax+00h]
0x140049432  mov     cs:Object, 0
0x14004943d  mov     cs:qword_140043098, 0
0x140049448  mov     rbx, qword ptr cs:RxContextLookasideList.L
0x14004944f  test    rbx, rbx
0x140049452  jz      short loc_1400494A0
0x140049454  mov     edi, [rbx]
0x140049456  jmp     short loc_14004947C
0x140049458  mov     ecx, edi
0x14004945a  shl     rcx, 7
0x14004945e  mov     al, [rcx+rbx+0B0h]
0x140049465  test    al, al
0x140049467  jz      short loc_14004947C
0x140049469  add     rcx, 40h ; '@'
0x14004946d  add     rcx, rbx; Lookaside
0x140049470  call    cs:__imp_ExDeleteLookasideListEx
0x140049477  nop     dword ptr [rax+rax+00h]
0x14004947c  sub     edi, 1
0x14004947f  jns     short loc_140049458
0x140049481  mov     edx, 734D7852h; Tag
0x140049486  mov     rcx, rbx; P
0x140049489  call    cs:__imp_ExFreePoolWithTag
0x140049490  nop     dword ptr [rax+rax+00h]
0x140049495  mov     qword ptr cs:RxContextLookasideList.L, 0
0x1400494a0  mov     rbx, [rsp+48h+arg_0]
0x1400494a5  add     rsp, 40h
0x1400494a9  pop     rdi
0x1400494aa  retn
```
