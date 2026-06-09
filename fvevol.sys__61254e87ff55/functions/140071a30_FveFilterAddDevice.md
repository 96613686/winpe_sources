# FveFilterAddDevice

- ea: `0x140071a30`
- end: `0x140071df1`
- name: `FveFilterAddDevice`
- size: `961`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject, PDEVICE_OBJECT TargetDevice)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x14000a210`
- `0x14000f254`
- `0x14000f2c0`
- `0x140023040`
- `0x14002445c`
- `0x140027aec`
- `0x14002d140`
- `0x140052dec`
- `0x140063f30`
- `0x140071a30`
- `0x140072b20`
- `0x14007bd40`
- `0x140087220`
- `0x1400e8b98`

## import_xrefs

- `ntoskrnl!MmIsThisAnNtAsSystem` at `0x140071b31`
- `ntoskrnl!MmIsThisAnNtAsSystem` at `0x140071b31`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x140071d78`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x140071d78`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140071d0e`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140071d0e`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140071d5c`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140071d5c`
- `ntoskrnl!IoDeleteDevice` at `0x140071d8f`
- `ntoskrnl!IoDeleteDevice` at `0x140071d8f`
- `ntoskrnl!ExSizeOfRundownProtectionCacheAware` at `0x140071aa3`
- `ntoskrnl!ExSizeOfRundownProtectionCacheAware` at `0x140071aa3`
- `ntoskrnl!IoCreateDevice` at `0x140071af7`
- `ntoskrnl!IoCreateDevice` at `0x140071af7`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140071bef`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140071bef`
- `ntoskrnl!ExInitializeRundownProtectionCacheAware` at `0x140071c0c`
- `ntoskrnl!ExInitializeRundownProtectionCacheAware` at `0x140071c0c`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x140071c1f`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x140071c1f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140071d27`
- `ntoskrnl!ExFreePoolWithTag` at `0x140071d47`
- `ntoskrnl!ExFreePoolWithTag` at `0x140071d27`
- `ntoskrnl!ExFreePoolWithTag` at `0x140071d47`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x140071a94`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x140071a94`

## pseudocode

```c
__int64 __fastcall FveFilterAddDevice(PDRIVER_OBJECT DriverObject, PDEVICE_OBJECT TargetDevice)
{
  _QWORD *DeviceExtension; // rbx
  PVOID DriverObjectExtension; // r15
  unsigned __int64 v6; // r14
  unsigned __int64 v7; // rdx
  NTSTATUS DcbVol; // edi
  BOOLEAN IsThisAnNtAsSystem; // al
  __int64 v10; // r8
  __int64 v11; // rdx
  PDEVICE_OBJECT v12; // rax
  __int64 v13; // rax
  struct _NPAGED_LOOKASIDE_LIST *v14; // rcx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v15; // rcx
  signed __int32 v17[8]; // [rsp+0h] [rbp-40h] BYREF
  PDEVICE_OBJECT SourceDevice; // [rsp+80h] [rbp+40h] BYREF

  SourceDevice = 0;
  DeviceExtension = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 152, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids);
  }
  DriverObjectExtension = IoGetDriverObjectExtension(DriverObject, DriverObject);
  v6 = ExSizeOfRundownProtectionCacheAware();
  Feature_BitLocker_Scalable_Remove_Lock__private_IsEnabledPreCheck();
  v7 = v6 + 5216;
  if ( v6 + 5216 < v6 || v7 > 0xFFFFFFFF )
  {
    DcbVol = -1073741670;
    goto LABEL_21;
  }
  DcbVol = IoCreateDevice(DriverObject, v7, 0, 0x22u, 0x100u, 0, &SourceDevice);
  if ( DcbVol < 0 )
    goto LABEL_21;
  DeviceExtension = SourceDevice->DeviceExtension;
  memset(DeviceExtension, 0, 0x1460u);
  *((_BYTE *)DeviceExtension + 1476) = 1;
  Feature_BitLocker_Priority_From_Current_Thread__private_IsEnabledPreCheck();
  IsThisAnNtAsSystem = MmIsThisAnNtAsSystem();
  LOBYTE(v10) = 1;
  *((_BYTE *)DeviceExtension + 1477) = IsThisAnNtAsSystem != 0;
  DcbVol = FveInitializeRemoveLock(DeviceExtension + 7, DeviceExtension, v10);
  if ( DcbVol < 0 )
    goto LABEL_21;
  *DeviceExtension = SourceDevice;
  DeviceExtension[1] = DriverObjectExtension;
  DeviceExtension[591] = 0;
  DcbVol = FveQueueInit(DeviceExtension);
  if ( DcbVol < 0
    || (v11 = TargetDevice->Flags >> 8,
        LOBYTE(v11) = BYTE1(TargetDevice->Flags) & 1,
        DcbVol = FveInit(DeviceExtension, v11),
        DcbVol < 0)
    || (FveTestRwInitialize(DeviceExtension),
        DeviceExtension[15] = TargetDevice,
        DcbVol = FveResolveDeviceType(DeviceExtension),
        DcbVol < 0)
    || (DcbVol = FveCreateDcbVol(DeviceExtension), DcbVol < 0) )
  {
LABEL_21:
    if ( SourceDevice )
    {
      FveDisconnectVol(DeviceExtension);
      FveQueueCleanup(DeviceExtension);
      v13 = DeviceExtension[294];
      if ( v13 )
      {
        v14 = *(struct _NPAGED_LOOKASIDE_LIST **)(v13 + 8);
        if ( v14 )
        {
          ExDeleteNPagedLookasideList(v14);
          ExFreePoolWithTag(*(PVOID *)(DeviceExtension[294] + 8LL), 0x30455646u);
          *(_QWORD *)(DeviceExtension[294] + 8LL) = 0;
        }
        ExFreePoolWithTag((PVOID)DeviceExtension[294], 0x30455646u);
      }
      v15 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)DeviceExtension[13];
      if ( v15 )
      {
        ExFreeCacheAwareRundownProtection(v15);
        DeviceExtension[13] = 0;
      }
      if ( DeviceExtension[558] )
      {
        ExUnsubscribeWnfStateChange();
        DeviceExtension[558] = 0;
      }
      IoDeleteDevice(SourceDevice);
      SourceDevice = 0;
    }
    goto LABEL_31;
  }
  *((_DWORD *)DeviceExtension + 368) = 0;
  DeviceExtension[185] = 0;
  *((_DWORD *)DeviceExtension + 372) = 5;
  ExInitializeRundownProtection((PEX_RUNDOWN_REF)DeviceExtension + 181);
  DeviceExtension[183] = DeviceExtension + 652;
  ExInitializeRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)(DeviceExtension + 652), v6);
  v12 = IoAttachDeviceToDeviceStack(SourceDevice, TargetDevice);
  DeviceExtension[14] = v12;
  if ( !v12 )
  {
    DcbVol = -1073741810;
    goto LABEL_21;
  }
  SourceDevice->DeviceType = v12->DeviceType;
  SourceDevice->Flags |= 0x10u;
  SourceDevice->Flags |= *(_DWORD *)(DeviceExtension[14] + 48LL) & 0x6000;
  SourceDevice->Characteristics |= *(_DWORD *)(DeviceExtension[14] + 52LL) & 0x5010F;
  FvePerfTraceDevPtr(DeviceExtension, FVE_PERF_VOLUME_CREATE, TargetDevice);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 153, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids, DeviceExtension);
  }
  _InterlockedOr(v17, 0);
  SourceDevice->Flags &= ~0x80u;
LABEL_31:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      154,
      WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids,
      (unsigned int)DcbVol);
  }
  return (unsigned int)DcbVol;
}

```

## disassembly

```asm
0x140071a30  mov     [rsp-28h+arg_0], rbx
0x140071a35  mov     [rsp-28h+arg_8], rsi
0x140071a3a  push    rbp
0x140071a3b  push    rdi
0x140071a3c  push    r12
0x140071a3e  push    r14
0x140071a40  push    r15
0x140071a42  mov     rbp, rsp
0x140071a45  sub     rsp, 40h
0x140071a49  xor     r12d, r12d
0x140071a4c  mov     rsi, rdx
0x140071a4f  mov     [rbp+SourceDevice], r12
0x140071a53  mov     ebx, r12d
0x140071a56  mov     rdi, rcx
0x140071a59  mov     rcx, cs:WPP_GLOBAL_Control
0x140071a60  lea     rax, WPP_GLOBAL_Control
0x140071a67  cmp     rcx, rax
0x140071a6a  jz      short loc_140071A8E
0x140071a6c  mov     eax, [rcx+2Ch]
0x140071a6f  test    al, 40h
0x140071a71  jz      short loc_140071A8E
0x140071a73  cmp     byte ptr [rcx+29h], 5
0x140071a77  jb      short loc_140071A8E
0x140071a79  mov     rcx, [rcx+18h]
0x140071a7d  lea     r8, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids
0x140071a84  mov     edx, 98h
0x140071a89  call    WPP_SF_
0x140071a8e  mov     rdx, rdi; ClientIdentificationAddress
0x140071a91  mov     rcx, rdi; DriverObject
0x140071a94  call    cs:__imp_IoGetDriverObjectExtension
0x140071a9b  nop     dword ptr [rax+rax+00h]
0x140071aa0  mov     r15, rax
0x140071aa3  call    cs:__imp_ExSizeOfRundownProtectionCacheAware
0x140071aaa  nop     dword ptr [rax+rax+00h]
0x140071aaf  mov     r14, rax
0x140071ab2  call    Feature_BitLocker_Scalable_Remove_Lock__private_IsEnabledPreCheck
0x140071ab7  lea     rdx, [r14+1460h]; DeviceExtensionSize
0x140071abe  cmp     rdx, r14
0x140071ac1  jb      loc_140071CD5
0x140071ac7  mov     eax, 0FFFFFFFFh
0x140071acc  cmp     rdx, rax
0x140071acf  ja      loc_140071CD5
0x140071ad5  lea     rax, [rbp+SourceDevice]
0x140071ad9  mov     r9d, 22h ; '"'; DeviceType
0x140071adf  mov     [rsp+40h+DeviceObject], rax; DeviceObject
0x140071ae4  xor     r8d, r8d; DeviceName
0x140071ae7  mov     [rsp+40h+Exclusive], r12b; Exclusive
0x140071aec  mov     rcx, rdi; DriverObject
0x140071aef  mov     [rsp+40h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x140071af7  call    cs:__imp_IoCreateDevice
0x140071afe  nop     dword ptr [rax+rax+00h]
0x140071b03  mov     edi, eax
0x140071b05  test    eax, eax
0x140071b07  js      loc_140071CDA
0x140071b0d  mov     rax, [rbp+SourceDevice]
0x140071b11  xor     edx, edx; Val
0x140071b13  mov     r8d, 1460h; Size
0x140071b19  mov     rbx, [rax+40h]
0x140071b1d  mov     rcx, rbx; void *
0x140071b20  call    memset
0x140071b25  mov     byte ptr [rbx+5C4h], 1
0x140071b2c  call    Feature_BitLocker_Priority_From_Current_Thread__private_IsEnabledPreCheck
0x140071b31  call    cs:__imp_MmIsThisAnNtAsSystem
0x140071b38  nop     dword ptr [rax+rax+00h]
0x140071b3d  lea     rcx, [rbx+38h]
0x140071b41  mov     r8b, 1
0x140071b44  test    al, al
0x140071b46  mov     rdx, rbx
0x140071b49  setnz   al
0x140071b4c  mov     [rbx+5C5h], al
0x140071b52  call    FveInitializeRemoveLock
0x140071b57  mov     edi, eax
0x140071b59  test    eax, eax
0x140071b5b  js      loc_140071CDA
0x140071b61  mov     rax, [rbp+SourceDevice]
0x140071b65  mov     rcx, rbx
0x140071b68  mov     [rbx], rax
0x140071b6b  mov     [rbx+8], r15
0x140071b6f  mov     [rbx+1278h], r12
0x140071b76  call    FveQueueInit
0x140071b7b  mov     edi, eax
0x140071b7d  test    eax, eax
0x140071b7f  js      loc_140071CDA
0x140071b85  mov     edx, [rsi+30h]
0x140071b88  mov     rcx, rbx
0x140071b8b  shr     edx, 8
0x140071b8e  and     dl, 1
0x140071b91  call    FveInit
0x140071b96  mov     edi, eax
0x140071b98  test    eax, eax
0x140071b9a  js      loc_140071CDA
0x140071ba0  mov     rcx, rbx
0x140071ba3  call    FveTestRwInitialize
0x140071ba8  mov     rcx, rbx
0x140071bab  mov     [rbx+78h], rsi
0x140071baf  call    FveResolveDeviceType
0x140071bb4  mov     edi, eax
0x140071bb6  test    eax, eax
0x140071bb8  js      loc_140071CDA
0x140071bbe  mov     rcx, rbx
0x140071bc1  call    FveCreateDcbVol
0x140071bc6  mov     edi, eax
0x140071bc8  test    eax, eax
0x140071bca  js      loc_140071CDA
0x140071bd0  lea     rcx, [rbx+5A8h]; RunRef
0x140071bd7  mov     [rbx+5C0h], r12d
0x140071bde  mov     [rbx+5C8h], r12
0x140071be5  mov     dword ptr [rbx+5D0h], 5
0x140071bef  call    cs:__imp_ExInitializeRundownProtection
0x140071bf6  nop     dword ptr [rax+rax+00h]
0x140071bfb  lea     rcx, [rbx+1460h]; RunRefCacheAware
0x140071c02  mov     rdx, r14; RunRefSize
0x140071c05  mov     [rbx+5B8h], rcx
0x140071c0c  call    cs:__imp_ExInitializeRundownProtectionCacheAware
0x140071c13  nop     dword ptr [rax+rax+00h]
0x140071c18  mov     rcx, [rbp+SourceDevice]; SourceDevice
0x140071c1c  mov     rdx, rsi; TargetDevice
0x140071c1f  call    cs:__imp_IoAttachDeviceToDeviceStack
0x140071c26  nop     dword ptr [rax+rax+00h]
0x140071c2b  mov     [rbx+70h], rax
0x140071c2f  test    rax, rax
0x140071c32  jnz     short loc_140071C3E
0x140071c34  mov     edi, 0C000000Eh
0x140071c39  jmp     loc_140071CDA
0x140071c3e  mov     ecx, [rax+48h]
0x140071c41  mov     r8, rsi
0x140071c44  mov     rax, [rbp+SourceDevice]
0x140071c48  mov     [rax+48h], ecx
0x140071c4b  mov     rax, [rbp+SourceDevice]
0x140071c4f  or      dword ptr [rax+30h], 10h
0x140071c53  mov     rax, [rbx+70h]
0x140071c57  mov     rdx, [rbp+SourceDevice]
0x140071c5b  mov     ecx, [rax+30h]
0x140071c5e  and     ecx, 6000h
0x140071c64  or      [rdx+30h], ecx
0x140071c67  mov     rax, [rbx+70h]
0x140071c6b  mov     rdx, [rbp+SourceDevice]
0x140071c6f  mov     ecx, [rax+34h]
0x140071c72  and     ecx, 5010Fh
0x140071c78  or      [rdx+34h], ecx
0x140071c7b  lea     rdx, FVE_PERF_VOLUME_CREATE
0x140071c82  mov     rcx, rbx
0x140071c85  call    FvePerfTraceDevPtr
0x140071c8a  mov     rcx, cs:WPP_GLOBAL_Control
0x140071c91  lea     rsi, WPP_GLOBAL_Control
0x140071c98  cmp     rcx, rsi
0x140071c9b  jz      short loc_140071CC2
0x140071c9d  mov     eax, [rcx+2Ch]
0x140071ca0  test    al, 40h
0x140071ca2  jz      short loc_140071CC2
0x140071ca4  cmp     byte ptr [rcx+29h], 4
0x140071ca8  jb      short loc_140071CC2
0x140071caa  mov     rcx, [rcx+18h]
0x140071cae  lea     r8, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids
0x140071cb5  mov     edx, 99h
0x140071cba  mov     r9, rbx
0x140071cbd  call    WPP_SF_q
0x140071cc2  lock or [rsp+40h+var_40], r12d
0x140071cc7  mov     rax, [rbp+SourceDevice]
0x140071ccb  btr     dword ptr [rax+30h], 7
0x140071cd0  jmp     loc_140071DA6
0x140071cd5  mov     edi, 0C000009Ah
0x140071cda  cmp     [rbp+SourceDevice], r12
0x140071cde  jz      loc_140071D9F
0x140071ce4  mov     rcx, rbx
0x140071ce7  call    FveDisconnectVol
0x140071cec  mov     rcx, rbx
0x140071cef  call    FveQueueCleanup
0x140071cf4  mov     rax, [rbx+930h]
0x140071cfb  test    rax, rax
0x140071cfe  jz      short loc_140071D53
0x140071d00  mov     rcx, [rax+8]; Lookaside
0x140071d04  mov     esi, 30455646h
0x140071d09  test    rcx, rcx
0x140071d0c  jz      short loc_140071D3E
0x140071d0e  call    cs:__imp_ExDeleteNPagedLookasideList
0x140071d15  nop     dword ptr [rax+rax+00h]
0x140071d1a  mov     rcx, [rbx+930h]
0x140071d21  mov     edx, esi; Tag
0x140071d23  mov     rcx, [rcx+8]; P
0x140071d27  call    cs:__imp_ExFreePoolWithTag
0x140071d2e  nop     dword ptr [rax+rax+00h]
0x140071d33  mov     rax, [rbx+930h]
0x140071d3a  mov     [rax+8], r12
0x140071d3e  mov     rcx, [rbx+930h]; P
0x140071d45  mov     edx, esi; Tag
0x140071d47  call    cs:__imp_ExFreePoolWithTag
0x140071d4e  nop     dword ptr [rax+rax+00h]
0x140071d53  mov     rcx, [rbx+68h]; RunRefCacheAware
0x140071d57  test    rcx, rcx
0x140071d5a  jz      short loc_140071D6C
0x140071d5c  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x140071d63  nop     dword ptr [rax+rax+00h]
0x140071d68  mov     [rbx+68h], r12
0x140071d6c  mov     rcx, [rbx+1170h]
0x140071d73  test    rcx, rcx
0x140071d76  jz      short loc_140071D8B
0x140071d78  call    cs:__imp_ExUnsubscribeWnfStateChange
0x140071d7f  nop     dword ptr [rax+rax+00h]
0x140071d84  mov     [rbx+1170h], r12
0x140071d8b  mov     rcx, [rbp+SourceDevice]; DeviceObject
0x140071d8f  call    cs:__imp_IoDeleteDevice
0x140071d96  nop     dword ptr [rax+rax+00h]
0x140071d9b  mov     [rbp+SourceDevice], r12
0x140071d9f  lea     rsi, WPP_GLOBAL_Control
0x140071da6  mov     rcx, cs:WPP_GLOBAL_Control
0x140071dad  cmp     rcx, rsi
0x140071db0  jz      short loc_140071DD7
0x140071db2  mov     eax, [rcx+2Ch]
0x140071db5  test    al, 40h
0x140071db7  jz      short loc_140071DD7
0x140071db9  cmp     byte ptr [rcx+29h], 5
0x140071dbd  jb      short loc_140071DD7
0x140071dbf  mov     rcx, [rcx+18h]
0x140071dc3  lea     r8, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids
0x140071dca  mov     edx, 9Ah
0x140071dcf  mov     r9d, edi
0x140071dd2  call    WPP_SF_d
0x140071dd7  mov     rbx, [rsp+40h+arg_0]
0x140071ddc  mov     eax, edi
0x140071dde  mov     rsi, [rsp+40h+arg_8]
0x140071de3  add     rsp, 40h
0x140071de7  pop     r15
0x140071de9  pop     r14
0x140071deb  pop     r12
0x140071ded  pop     rdi
0x140071dee  pop     rbp
0x140071def  retn
```
