# DfscInitUnwind

- ea: `0x140012930`
- end: `0x140012b95`
- name: `DfscInitUnwind`
- size: `613`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140012bd0`
- `0x14002a904`

## callees

- `0x140002570`
- `0x1400053f0`
- `0x140011b78`
- `0x140012534`
- `0x140012930`
- `0x140012be8`
- `0x140018068`
- `0x140018484`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14001295f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140012b54`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001295f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140012b54`
- `ntoskrnl!IoDeleteDevice` at `0x140012b78`
- `ntoskrnl!IoDeleteDevice` at `0x140012b78`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140012b65`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140012b65`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140012ac0`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140012ac0`
- `ntoskrnl!KeFreeCalloutStack` at `0x140012b1f`
- `ntoskrnl!KeFreeCalloutStack` at `0x140012b1f`
- `ntoskrnl!PsUnregisterSiloMonitor` at `0x1400129c0`
- `ntoskrnl!PsUnregisterSiloMonitor` at `0x1400129c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012a26`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012a26`
- `ntoskrnl!ExDeleteResourceLite` at `0x140012ae6`
- `ntoskrnl!ExDeleteResourceLite` at `0x140012af9`
- `ntoskrnl!ExDeleteResourceLite` at `0x140012ae6`
- `ntoskrnl!ExDeleteResourceLite` at `0x140012af9`
- `MUP!MupSurrogateDeregisterProvider` at `0x140012970`
- `MUP!MupSurrogateDeregisterProvider` at `0x140012970`

## pseudocode

```c
void DfscInitUnwind()
{
  char v0; // al
  char v1; // al
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-28h] BYREF
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+30h] [rbp-18h] BYREF

  SymbolicLinkName = 0;
  DfscTearDownTimer();
  if ( ((__int64)WPP_MAIN_CB.Queue.Wcb.DeviceObject & 1) != 0 )
  {
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"\\Device\\DfsClient");
    MupSurrogateDeregisterProvider(&DestinationString);
    LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceObject) &= ~1u;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_32bb75f7aa823fb724b87f7e3287c67a_Traceguids);
  if ( qword_14000C7F8 )
  {
    PsUnregisterSiloMonitor();
    qword_14000C7F8 = 0;
  }
  WppCleanupKm();
  v0 = DfscInitializationStatus;
  if ( (DfscInitializationStatus & 4) != 0 )
  {
    DfscCacheDelete(*(PVOID *)&WPP_MAIN_CB.ActiveThreadCount);
    v0 = DfscInitializationStatus & 0xFB;
    DfscInitializationStatus &= ~4u;
  }
  if ( (v0 & 8) != 0 )
  {
    DfscCacheDelete(WPP_MAIN_CB.SecurityDescriptor);
    DfscInitializationStatus &= ~8u;
  }
  if ( Destination.Buffer )
  {
    ExFreePoolWithTag(Destination.Buffer, 0);
    Destination.Buffer = 0;
  }
  if ( (DfscInitializationStatus & 0x100) != 0 )
    DfscDeInitSiteNameMonitoring();
  v1 = DfscInitializationStatus;
  if ( (DfscInitializationStatus & 0x10) != 0 )
  {
    DfscNetUseTableFree(0, Table);
    v1 = DfscInitializationStatus & 0xEF;
    DfscInitializationStatus &= ~0x10u;
  }
  if ( (v1 & 0x20) != 0 )
  {
    DfscNetUseTableFree(0, qword_14000C710);
    v1 = DfscInitializationStatus & 0xDF;
    DfscInitializationStatus &= ~0x20u;
  }
  if ( (v1 & 0x40) != 0 )
  {
    DfscCredTableFree(*(PVOID *)&WPP_MAIN_CB.DeviceLock.Header.Lock);
    v1 = DfscInitializationStatus & 0xBF;
    DfscInitializationStatus &= ~0x40u;
  }
  if ( (v1 & 2) != 0 )
  {
    ExDeletePagedLookasideList(&DfscPathNameLookasideList);
    v1 = DfscInitializationStatus & 0xFD;
    DfscInitializationStatus &= ~2u;
  }
  if ( (v1 & 1) != 0 )
  {
    ExDeleteResourceLite((PERESOURCE)&WPP_MAIN_CB.AlignmentRequirement);
    ExDeleteResourceLite((PERESOURCE)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead);
    v1 = DfscInitializationStatus & 0xFE;
    DfscInitializationStatus &= ~1u;
  }
  if ( v1 < 0 )
  {
    KeFreeCalloutStack(Context);
    DfscInitializationStatus &= ~0x80u;
    Context = 0;
  }
  if ( WPP_MAIN_CB.Queue.Wcb.CurrentIrp )
  {
    RtlInitUnicodeString(&SymbolicLinkName, L"\\Dfs");
    IoDeleteSymbolicLink(&SymbolicLinkName);
    IoDeleteDevice((PDEVICE_OBJECT)WPP_MAIN_CB.Queue.Wcb.CurrentIrp);
    WPP_MAIN_CB.Queue.Wcb.CurrentIrp = 0;
  }
}

```

## disassembly

```asm
0x140012930  sub     rsp, 48h
0x140012934  xorps   xmm0, xmm0
0x140012937  movups  xmmword ptr [rsp+48h+SymbolicLinkName.Length], xmm0
0x14001293c  call    DfscTearDownTimer
0x140012941  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+30h
0x140012947  test    al, 1
0x140012949  jz      short loc_140012983
0x14001294b  xorps   xmm0, xmm0
0x14001294e  lea     rdx, SourceString; "\\Device\\DfsClient"
0x140012955  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x14001295a  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x14001295f  call    cs:__imp_RtlInitUnicodeString
0x140012966  nop     dword ptr [rax+rax+00h]
0x14001296b  lea     rcx, [rsp+48h+DestinationString]
0x140012970  call    cs:__imp_MupSurrogateDeregisterProvider
0x140012977  nop     dword ptr [rax+rax+00h]
0x14001297c  and     dword ptr cs:WPP_MAIN_CB.Queue+30h, 0FFFFFFFEh
0x140012983  mov     rcx, cs:WPP_GLOBAL_Control
0x14001298a  lea     rax, WPP_GLOBAL_Control
0x140012991  cmp     rcx, rax
0x140012994  jz      short loc_1400129B4
0x140012996  test    dword ptr [rcx+2Ch], 200000h
0x14001299d  jz      short loc_1400129B4
0x14001299f  mov     rcx, [rcx+18h]
0x1400129a3  lea     r8, WPP_32bb75f7aa823fb724b87f7e3287c67a_Traceguids
0x1400129aa  mov     edx, 19h
0x1400129af  call    WPP_SF_
0x1400129b4  mov     rcx, cs:qword_14000C7F8
0x1400129bb  test    rcx, rcx
0x1400129be  jz      short loc_1400129D7
0x1400129c0  call    cs:__imp_PsUnregisterSiloMonitor
0x1400129c7  nop     dword ptr [rax+rax+00h]
0x1400129cc  mov     cs:qword_14000C7F8, 0
0x1400129d7  call    WppCleanupKm
0x1400129dc  mov     eax, cs:DfscInitializationStatus
0x1400129e2  test    al, 4
0x1400129e4  jz      short loc_140012A01
0x1400129e6  mov     rcx, qword ptr cs:WPP_MAIN_CB.ActiveThreadCount; P
0x1400129ed  call    DfscCacheDelete
0x1400129f2  mov     eax, cs:DfscInitializationStatus
0x1400129f8  and     eax, 0FFFFFFFBh
0x1400129fb  mov     cs:DfscInitializationStatus, eax
0x140012a01  test    al, 8
0x140012a03  jz      short loc_140012A18
0x140012a05  mov     rcx, cs:WPP_MAIN_CB.SecurityDescriptor; P
0x140012a0c  call    DfscCacheDelete
0x140012a11  and     cs:DfscInitializationStatus, 0FFFFFFF7h
0x140012a18  mov     rcx, cs:Destination.Buffer; P
0x140012a1f  test    rcx, rcx
0x140012a22  jz      short loc_140012A3D
0x140012a24  xor     edx, edx; Tag
0x140012a26  call    cs:__imp_ExFreePoolWithTag
0x140012a2d  nop     dword ptr [rax+rax+00h]
0x140012a32  mov     cs:Destination.Buffer, 0
0x140012a3d  test    cs:DfscInitializationStatus, 100h
0x140012a47  jz      short loc_140012A4E
0x140012a49  call    DfscDeInitSiteNameMonitoring
0x140012a4e  mov     eax, cs:DfscInitializationStatus
0x140012a54  test    al, 10h
0x140012a56  jz      short loc_140012A75
0x140012a58  mov     rdx, cs:Table
0x140012a5f  xor     ecx, ecx
0x140012a61  call    DfscNetUseTableFree
0x140012a66  mov     eax, cs:DfscInitializationStatus
0x140012a6c  and     eax, 0FFFFFFEFh
0x140012a6f  mov     cs:DfscInitializationStatus, eax
0x140012a75  test    al, 20h
0x140012a77  jz      short loc_140012A96
0x140012a79  mov     rdx, cs:qword_14000C710
0x140012a80  xor     ecx, ecx
0x140012a82  call    DfscNetUseTableFree
0x140012a87  mov     eax, cs:DfscInitializationStatus
0x140012a8d  and     eax, 0FFFFFFDFh
0x140012a90  mov     cs:DfscInitializationStatus, eax
0x140012a96  test    al, 40h
0x140012a98  jz      short loc_140012AB5
0x140012a9a  mov     rcx, qword ptr cs:WPP_MAIN_CB.DeviceLock.Header; P
0x140012aa1  call    DfscCredTableFree
0x140012aa6  mov     eax, cs:DfscInitializationStatus
0x140012aac  and     eax, 0FFFFFFBFh
0x140012aaf  mov     cs:DfscInitializationStatus, eax
0x140012ab5  test    al, 2
0x140012ab7  jz      short loc_140012ADB
0x140012ab9  lea     rcx, DfscPathNameLookasideList; Lookaside
0x140012ac0  call    cs:__imp_ExDeletePagedLookasideList
0x140012ac7  nop     dword ptr [rax+rax+00h]
0x140012acc  mov     eax, cs:DfscInitializationStatus
0x140012ad2  and     eax, 0FFFFFFFDh
0x140012ad5  mov     cs:DfscInitializationStatus, eax
0x140012adb  test    al, 1
0x140012add  jz      short loc_140012B14
0x140012adf  lea     rcx, WPP_MAIN_CB.AlignmentRequirement; Resource
0x140012ae6  call    cs:__imp_ExDeleteResourceLite
0x140012aed  nop     dword ptr [rax+rax+00h]
0x140012af2  lea     rcx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead; Resource
0x140012af9  call    cs:__imp_ExDeleteResourceLite
0x140012b00  nop     dword ptr [rax+rax+00h]
0x140012b05  mov     eax, cs:DfscInitializationStatus
0x140012b0b  and     eax, 0FFFFFFFEh
0x140012b0e  mov     cs:DfscInitializationStatus, eax
0x140012b14  test    al, al
0x140012b16  jns     short loc_140012B3E
0x140012b18  mov     rcx, cs:Context
0x140012b1f  call    cs:__imp_KeFreeCalloutStack
0x140012b26  nop     dword ptr [rax+rax+00h]
0x140012b2b  btr     cs:DfscInitializationStatus, 7
0x140012b33  mov     cs:Context, 0
0x140012b3e  cmp     qword ptr cs:WPP_MAIN_CB.Queue+38h, 0
0x140012b46  jz      short loc_140012B8F
0x140012b48  lea     rdx, aDfs; "\\Dfs"
0x140012b4f  lea     rcx, [rsp+48h+SymbolicLinkName]; DestinationString
0x140012b54  call    cs:__imp_RtlInitUnicodeString
0x140012b5b  nop     dword ptr [rax+rax+00h]
0x140012b60  lea     rcx, [rsp+48h+SymbolicLinkName]; SymbolicLinkName
0x140012b65  call    cs:__imp_IoDeleteSymbolicLink
0x140012b6c  nop     dword ptr [rax+rax+00h]
0x140012b71  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+38h; DeviceObject
0x140012b78  call    cs:__imp_IoDeleteDevice
0x140012b7f  nop     dword ptr [rax+rax+00h]
0x140012b84  mov     qword ptr cs:WPP_MAIN_CB.Queue+38h, 0
0x140012b8f  add     rsp, 48h
0x140012b93  retn
```
