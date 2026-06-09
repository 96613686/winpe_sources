# PmStartDeviceInternal(_DEVICE_EXTENSION *,_IRP *)

- ea: `0x140007674`
- end: `0x1400079f4`
- name: `?PmStartDeviceInternal@@YAJPEAU_DEVICE_EXTENSION@@PEAU_IRP@@@Z`
- size: `896`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _IRP *)`
- caller_count: `2`
- callee_count: `16`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140006280`
- `0x14000bf60`

## callees

- `0x1400060ac`
- `0x140007674`
- `0x140007bcc`
- `0x14000aa60`
- `0x14000ca1c`
- `0x14000d5a0`
- `0x14000da9c`
- `0x140011440`
- `0x14001c0e0`
- `0x14001c2c0`
- `0x14001f6b8`
- `0x140020c40`
- `0x140020ce0`
- `0x140024ac0`
- `0x14002589c`
- `0x1400261fc`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400078cc`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400078cc`
- `ntoskrnl!IoSynchronousCallDriver` at `0x140007995`
- `ntoskrnl!IoSynchronousCallDriver` at `0x140007995`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400076a3`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400076a3`
- `ntoskrnl!IofCompleteRequest` at `0x1400079bb`
- `ntoskrnl!IofCompleteRequest` at `0x1400079bb`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x1400076f5`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x14000771d`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x1400076f5`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x14000771d`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400079d4`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400079d4`
- `ntoskrnl!IoWMIRegistrationControl` at `0x14000775e`
- `ntoskrnl!IoWMIRegistrationControl` at `0x14000775e`
- `ntoskrnl!PoEnergyEstimationEnabled` at `0x140007790`
- `ntoskrnl!PoEnergyEstimationEnabled` at `0x140007790`
- `ntoskrnl!IoCreateArcName` at `0x14000785a`
- `ntoskrnl!IoCreateArcName` at `0x14000785a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400077fc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007890`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000792f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400077fc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007890`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000792f`
- `ntoskrnl!KeReleaseMutex` at `0x1400079a7`
- `ntoskrnl!KeReleaseMutex` at `0x1400079a7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400077db`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000786e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400078eb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400077db`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000786e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400078eb`

## pseudocode

```c
__int64 __fastcall PmStartDeviceInternal(struct _DEVICE_EXTENSION *a1, struct _IRP *a2)
{
  struct _DEVICE_OBJECT *v3; // rcx
  _BYTE *DeviceExtension; // r15
  NTSTATUS Status; // esi
  KIRQL v7; // al
  KIRQL v8; // al
  KIRQL v9; // al
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  unsigned __int8 v12; // [rsp+60h] [rbp+8h] BYREF
  unsigned __int8 v13; // [rsp+68h] [rbp+10h] BYREF

  v3 = (struct _DEVICE_OBJECT *)*((_QWORD *)a1 + 2);
  v12 = 0;
  v13 = 0;
  DeviceExtension = PmControlObject->DeviceExtension;
  IoForwardIrpSynchronously(v3, a2);
  Status = a2->IoStatus.Status;
  if ( Status >= 0 && (*((_DWORD *)a1 + 129) & 1) == 0 )
  {
    Status = PmInitializeDevice(a1, a2);
    if ( Status >= 0 )
    {
      Status = IoRegisterDeviceInterface(
                 *((PDEVICE_OBJECT *)a1 + 3),
                 &GUID_DEVINTERFACE_DISK,
                 0,
                 (PUNICODE_STRING)a1 + 30);
      if ( Status >= 0 )
      {
        Status = IoRegisterDeviceInterface(
                   *((PDEVICE_OBJECT *)a1 + 3),
                   &GUID_DEVINTERFACE_HIDDEN_DISK,
                   0,
                   (PUNICODE_STRING)a1 + 31);
        if ( Status >= 0 )
        {
          if ( DeviceExtension[169] )
          {
            PmInitializePartitionTableCache(a1);
            PmInitializeAttributesTableCache(a1);
            PmInitializeSnapshotDataCache(a1);
          }
          Status = IoWMIRegistrationControl(*((PDEVICE_OBJECT *)a1 + 1), 0x110001u);
          if ( Status >= 0 )
          {
            PmWmiCounterEnable((struct _PERF_COUNTER_CONTEXT **)a1 + 90);
            PmWmiCounterDisable((struct _PERF_COUNTER_CONTEXT **)a1 + 90, 0, 0);
            if ( (unsigned __int8)PoEnergyEstimationEnabled() )
              PmPowerCounterEnable(a1);
            Status = PmAttributesPhase1(a1, &v12);
            if ( Status >= 0 )
            {
              PmSetSystemCriticalFlagPhase1(a1, &v13);
              if ( (*((_QWORD *)a1 + 66) & 0x40) != 0 )
              {
                v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 14);
                *((_DWORD *)a1 + 129) |= 1u;
                KeReleaseSpinLock((PKSPIN_LOCK)a1 + 14, v7);
              }
              else if ( !PmEnforceService(a1)
                     || (Status = PmGetDriveLayoutEx((KSPIN_LOCK *)a1, 0), Status >= 0)
                     && ((*((_DWORD *)a1 + 129) & 0x4000) == 0 || (Status = PmApplyServiceProtection(a1), Status >= 0)) )
              {
                if ( (*((_QWORD *)a1 + 66) & 0x80u) == 0LL )
                {
                  if ( (int)IoCreateArcName(*((_QWORD *)a1 + 1)) >= 0 )
                  {
                    v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 14);
                    *((_DWORD *)a1 + 129) |= 0x400u;
                    KeReleaseSpinLock((PKSPIN_LOCK)a1 + 14, v8);
                  }
                  Status = 0;
                }
                if ( !v12 || (Status = PmAttributesPhase2(a1), Status >= 0) )
                {
                  KeWaitForSingleObject((char *)a1 + 56, Executive, 0, 0, 0);
                  if ( v13 )
                    PmSetSystemCriticalFlagPhase2(a1);
                  v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 14);
                  if ( *((_BYTE *)a1 + 604) && !DeviceExtension[168] )
                    *((_DWORD *)a1 + 129) &= ~0x1000u;
                  *((_DWORD *)a1 + 129) |= 1u;
                  KeReleaseSpinLock((PKSPIN_LOCK)a1 + 14, v9);
                  PmGetDriveLayoutEx((KSPIN_LOCK *)a1, 0);
                  if ( *((_BYTE *)a1 + 604) && !DeviceExtension[168] )
                  {
                    CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
                    memset(&CurrentStackLocation[-1], 0, sizeof(struct _IO_STACK_LOCATION));
                    *(_WORD *)&CurrentStackLocation[-1].MajorFunction = 5659;
                    CurrentStackLocation[-1].Parameters.SetLock.Lock = 1;
                    CurrentStackLocation[-1].Parameters.Create.Options = 4;
                    a2->IoStatus.Status = -1073741637;
                    a2->IoStatus.Information = 0;
                    IoSynchronousCallDriver(*((_QWORD *)a1 + 2), a2);
                  }
                  KeReleaseMutex((PRKMUTEX)a1 + 1, 0);
                }
              }
            }
          }
        }
      }
    }
  }
  a2->IoStatus.Status = Status;
  IofCompleteRequest(a2, 0);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)((char *)a1 + 120), a2, 0x20u);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140007674  mov     [rsp+arg_10], rbx
0x140007679  push    rbp
0x14000767a  push    rsi
0x14000767b  push    rdi
0x14000767c  push    r14
0x14000767e  push    r15
0x140007680  sub     rsp, 30h
0x140007684  mov     rax, cs:?PmControlObject@@3PEAU_DEVICE_OBJECT@@EA; _DEVICE_OBJECT * PmControlObject
0x14000768b  mov     rdi, rcx
0x14000768e  mov     rcx, [rcx+10h]; DeviceObject
0x140007692  mov     rbp, rdx
0x140007695  mov     [rsp+58h+arg_0], 0
0x14000769a  mov     [rsp+58h+arg_8], 0
0x14000769f  mov     r15, [rax+40h]
0x1400076a3  call    cs:__imp_IoForwardIrpSynchronously
0x1400076aa  nop     dword ptr [rax+rax+00h]
0x1400076af  mov     esi, [rbp+30h]
0x1400076b2  test    esi, esi
0x1400076b4  js      loc_1400079B3
0x1400076ba  mov     eax, [rdi+204h]
0x1400076c0  test    al, 1
0x1400076c2  jnz     loc_1400079B3
0x1400076c8  mov     rdx, rbp; struct _IRP *
0x1400076cb  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x1400076ce  call    ?PmInitializeDevice@@YAJPEAU_DEVICE_EXTENSION@@PEAU_IRP@@@Z; PmInitializeDevice(_DEVICE_EXTENSION *,_IRP *)
0x1400076d3  mov     esi, eax
0x1400076d5  test    eax, eax
0x1400076d7  js      loc_1400079B3
0x1400076dd  mov     rcx, [rdi+18h]; PhysicalDeviceObject
0x1400076e1  lea     rbx, [rdi+1E0h]
0x1400076e8  mov     r9, rbx; SymbolicLinkName
0x1400076eb  lea     rdx, GUID_DEVINTERFACE_DISK; InterfaceClassGuid
0x1400076f2  xor     r8d, r8d; ReferenceString
0x1400076f5  call    cs:__imp_IoRegisterDeviceInterface
0x1400076fc  nop     dword ptr [rax+rax+00h]
0x140007701  mov     esi, eax
0x140007703  test    eax, eax
0x140007705  js      loc_1400079B3
0x14000770b  mov     rcx, [rdi+18h]; PhysicalDeviceObject
0x14000770f  lea     r9, [rbx+10h]; SymbolicLinkName
0x140007713  xor     r8d, r8d; ReferenceString
0x140007716  lea     rdx, GUID_DEVINTERFACE_HIDDEN_DISK; InterfaceClassGuid
0x14000771d  call    cs:__imp_IoRegisterDeviceInterface
0x140007724  nop     dword ptr [rax+rax+00h]
0x140007729  mov     esi, eax
0x14000772b  test    eax, eax
0x14000772d  js      loc_1400079B3
0x140007733  cmp     byte ptr [r15+0A9h], 0
0x14000773b  jz      short loc_140007755
0x14000773d  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x140007740  call    ?PmInitializePartitionTableCache@@YAJPEAU_DEVICE_EXTENSION@@@Z; PmInitializePartitionTableCache(_DEVICE_EXTENSION *)
0x140007745  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x140007748  call    ?PmInitializeAttributesTableCache@@YAJPEAU_DEVICE_EXTENSION@@@Z; PmInitializeAttributesTableCache(_DEVICE_EXTENSION *)
0x14000774d  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x140007750  call    ?PmInitializeSnapshotDataCache@@YAJPEAU_DEVICE_EXTENSION@@@Z; PmInitializeSnapshotDataCache(_DEVICE_EXTENSION *)
0x140007755  mov     rcx, [rdi+8]; DeviceObject
0x140007759  mov     edx, 110001h; Action
0x14000775e  call    cs:__imp_IoWMIRegistrationControl
0x140007765  nop     dword ptr [rax+rax+00h]
0x14000776a  mov     esi, eax
0x14000776c  test    eax, eax
0x14000776e  js      loc_1400079B3
0x140007774  lea     rbx, [rdi+2D0h]
0x14000777b  mov     rcx, rbx; struct _PERF_COUNTER_CONTEXT **
0x14000777e  call    ?PmWmiCounterEnable@@YAJPEAPEAU_PERF_COUNTER_CONTEXT@@@Z; PmWmiCounterEnable(_PERF_COUNTER_CONTEXT * *)
0x140007783  xor     r8d, r8d; unsigned __int8
0x140007786  xor     edx, edx; unsigned __int8
0x140007788  mov     rcx, rbx; struct _PERF_COUNTER_CONTEXT **
0x14000778b  call    ?PmWmiCounterDisable@@YAEPEAPEAU_PERF_COUNTER_CONTEXT@@EE@Z; PmWmiCounterDisable(_PERF_COUNTER_CONTEXT * *,uchar,uchar)
0x140007790  call    cs:__imp_PoEnergyEstimationEnabled
0x140007797  nop     dword ptr [rax+rax+00h]
0x14000779c  test    al, al
0x14000779e  jz      short loc_1400077A8
0x1400077a0  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x1400077a3  call    ?PmPowerCounterEnable@@YAJPEAU_DEVICE_EXTENSION@@@Z; PmPowerCounterEnable(_DEVICE_EXTENSION *)
0x1400077a8  lea     rdx, [rsp+58h+arg_0]; unsigned __int8 *
0x1400077ad  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x1400077b0  call    ?PmAttributesPhase1@@YAJPEAU_DEVICE_EXTENSION@@PEAE@Z; PmAttributesPhase1(_DEVICE_EXTENSION *,uchar *)
0x1400077b5  mov     esi, eax
0x1400077b7  test    eax, eax
0x1400077b9  js      loc_1400079B3
0x1400077bf  lea     rdx, [rsp+58h+arg_8]; unsigned __int8 *
0x1400077c4  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x1400077c7  call    ?PmSetSystemCriticalFlagPhase1@@YAXPEAU_DEVICE_EXTENSION@@PEAE@Z; PmSetSystemCriticalFlagPhase1(_DEVICE_EXTENSION *,uchar *)
0x1400077cc  mov     rax, [rdi+210h]
0x1400077d3  test    al, 40h
0x1400077d5  jz      short loc_14000780D
0x1400077d7  lea     rcx, [rdi+70h]; SpinLock
0x1400077db  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400077e2  nop     dword ptr [rax+rax+00h]
0x1400077e7  mov     edx, [rdi+204h]
0x1400077ed  lea     rcx, [rdi+70h]; SpinLock
0x1400077f1  or      edx, 1
0x1400077f4  mov     [rdi+204h], edx
0x1400077fa  mov     dl, al; NewIrql
0x1400077fc  call    cs:__imp_KeReleaseSpinLock
0x140007803  nop     dword ptr [rax+rax+00h]
0x140007808  jmp     loc_1400079B3
0x14000780d  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x140007810  call    ?PmEnforceService@@YAEPEAU_DEVICE_EXTENSION@@@Z; PmEnforceService(_DEVICE_EXTENSION *)
0x140007815  test    al, al
0x140007817  jz      short loc_14000784B
0x140007819  xor     edx, edx; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x14000781b  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x14000781e  call    ?PmGetDriveLayoutEx@@YAJPEAU_DEVICE_EXTENSION@@PEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; PmGetDriveLayoutEx(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX * *)
0x140007823  mov     esi, eax
0x140007825  test    eax, eax
0x140007827  js      loc_1400079B3
0x14000782d  mov     eax, [rdi+204h]
0x140007833  bt      eax, 0Eh
0x140007837  jnb     short loc_14000784B
0x140007839  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x14000783c  call    ?PmApplyServiceProtection@@YAJPEAU_DEVICE_EXTENSION@@@Z; PmApplyServiceProtection(_DEVICE_EXTENSION *)
0x140007841  mov     esi, eax
0x140007843  test    eax, eax
0x140007845  js      loc_1400079B3
0x14000784b  mov     rax, [rdi+210h]
0x140007852  test    al, al
0x140007854  js      short loc_14000789E
0x140007856  mov     rcx, [rdi+8]
0x14000785a  call    cs:__imp_IoCreateArcName
0x140007861  nop     dword ptr [rax+rax+00h]
0x140007866  test    eax, eax
0x140007868  js      short loc_14000789C
0x14000786a  lea     rcx, [rdi+70h]; SpinLock
0x14000786e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007875  nop     dword ptr [rax+rax+00h]
0x14000787a  mov     edx, [rdi+204h]
0x140007880  lea     rcx, [rdi+70h]; SpinLock
0x140007884  bts     edx, 0Ah
0x140007888  mov     [rdi+204h], edx
0x14000788e  mov     dl, al; NewIrql
0x140007890  call    cs:__imp_KeReleaseSpinLock
0x140007897  nop     dword ptr [rax+rax+00h]
0x14000789c  xor     esi, esi
0x14000789e  cmp     [rsp+58h+arg_0], 0
0x1400078a3  jz      short loc_1400078B7
0x1400078a5  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x1400078a8  call    ?PmAttributesPhase2@@YAJPEAU_DEVICE_EXTENSION@@@Z; PmAttributesPhase2(_DEVICE_EXTENSION *)
0x1400078ad  mov     esi, eax
0x1400078af  test    eax, eax
0x1400078b1  js      loc_1400079B3
0x1400078b7  xor     r9d, r9d; Alertable
0x1400078ba  mov     [rsp+58h+Timeout], 0; Timeout
0x1400078c3  xor     r8d, r8d; WaitMode
0x1400078c6  lea     rcx, [rdi+38h]; Object
0x1400078ca  xor     edx, edx; WaitReason
0x1400078cc  call    cs:__imp_KeWaitForSingleObject
0x1400078d3  nop     dword ptr [rax+rax+00h]
0x1400078d8  cmp     [rsp+58h+arg_8], 0
0x1400078dd  jz      short loc_1400078E7
0x1400078df  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x1400078e2  call    ?PmSetSystemCriticalFlagPhase2@@YAJPEAU_DEVICE_EXTENSION@@@Z; PmSetSystemCriticalFlagPhase2(_DEVICE_EXTENSION *)
0x1400078e7  lea     rcx, [rdi+70h]; SpinLock
0x1400078eb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400078f2  nop     dword ptr [rax+rax+00h]
0x1400078f7  cmp     byte ptr [rdi+25Ch], 0
0x1400078fe  jz      short loc_14000791A
0x140007900  cmp     byte ptr [r15+0A8h], 0
0x140007908  jnz     short loc_14000791A
0x14000790a  mov     edx, [rdi+204h]
0x140007910  btr     edx, 0Ch
0x140007914  mov     [rdi+204h], edx
0x14000791a  mov     edx, [rdi+204h]
0x140007920  lea     rcx, [rdi+70h]; SpinLock
0x140007924  or      edx, 1
0x140007927  mov     [rdi+204h], edx
0x14000792d  mov     dl, al; NewIrql
0x14000792f  call    cs:__imp_KeReleaseSpinLock
0x140007936  nop     dword ptr [rax+rax+00h]
0x14000793b  xor     edx, edx; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x14000793d  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x140007940  call    ?PmGetDriveLayoutEx@@YAJPEAU_DEVICE_EXTENSION@@PEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; PmGetDriveLayoutEx(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX * *)
0x140007945  cmp     byte ptr [rdi+25Ch], 0
0x14000794c  jz      short loc_1400079A1
0x14000794e  cmp     byte ptr [r15+0A8h], 0
0x140007956  jnz     short loc_1400079A1
0x140007958  mov     rbx, [rbp+0B8h]
0x14000795f  xor     edx, edx; Val
0x140007961  lea     r8d, [rdx+48h]; Size
0x140007965  lea     rcx, [rbx-48h]; void *
0x140007969  call    memset
0x14000796e  mov     word ptr [rbx-48h], 161Bh
0x140007974  mov     rdx, rbp
0x140007977  mov     byte ptr [rbx-40h], 1
0x14000797b  mov     dword ptr [rbx-38h], 4
0x140007982  mov     dword ptr [rbp+30h], 0C00000BBh
0x140007989  mov     qword ptr [rbp+38h], 0
0x140007991  mov     rcx, [rdi+10h]
0x140007995  call    cs:__imp_IoSynchronousCallDriver
0x14000799c  nop     dword ptr [rax+rax+00h]
0x1400079a1  xor     edx, edx; Wait
0x1400079a3  lea     rcx, [rdi+38h]; Mutex
0x1400079a7  call    cs:__imp_KeReleaseMutex
0x1400079ae  nop     dword ptr [rax+rax+00h]
0x1400079b3  xor     edx, edx; PriorityBoost
0x1400079b5  mov     [rbp+30h], esi
0x1400079b8  mov     rcx, rbp; Irp
0x1400079bb  call    cs:__imp_IofCompleteRequest
0x1400079c2  nop     dword ptr [rax+rax+00h]
0x1400079c7  lea     rcx, [rdi+78h]; RemoveLock
0x1400079cb  mov     r8d, 20h ; ' '; RemlockSize
0x1400079d1  mov     rdx, rbp; Tag
0x1400079d4  call    cs:__imp_IoReleaseRemoveLockEx
0x1400079db  nop     dword ptr [rax+rax+00h]
0x1400079e0  mov     rbx, [rsp+58h+arg_10]
0x1400079e5  mov     eax, esi
0x1400079e7  add     rsp, 30h
0x1400079eb  pop     r15
0x1400079ed  pop     r14
0x1400079ef  pop     rdi
0x1400079f0  pop     rsi
0x1400079f1  pop     rbp
0x1400079f2  retn
```
