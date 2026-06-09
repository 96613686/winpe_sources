# RxAddToWorkque

- ea: `0x140007710`
- end: `0x14000789b`
- name: `RxAddToWorkque`
- size: `395`
- prototype: `void __stdcall(PRX_CONTEXT RxContext, PIRP Irp)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140004ac0`
- `0x140007ca0`

## callees

- `0x140007710`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400077cb`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400077cb`
- `ntoskrnl!IoInitializeWorkItem` at `0x1400077e4`
- `ntoskrnl!IoInitializeWorkItem` at `0x1400077e4`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14000782d`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14000782d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007811`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007885`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007811`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007885`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007732`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007732`

## pseudocode

```c
void __stdcall RxAddToWorkque(PRX_CONTEXT RxContext, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  PDEVICE_OBJECT DeviceObject; // rdi
  KIRQL v5; // al
  PSZ FileName; // rcx
  KIRQL v7; // bp
  PSZ v8; // rcx
  PSZ v9; // rdx
  PSZ *v10; // r8
  struct _IO_WORKITEM *v11; // r14
  PSZ v12; // rcx
  union _RX_CONTEXT::$5B7AEA49E590911F8F12743B7A0B9162 **DeviceRoutine; // rcx
  union _RX_CONTEXT::$5B7AEA49E590911F8F12743B7A0B9162 *p_Info; // rbx

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  BYTE3(RxContext->RealDevice) = 0;
  DeviceObject = CurrentStackLocation->DeviceObject;
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&DeviceObject[1].Queue);
  FileName = RxContext->TrackerHistory[9].FileName;
  v7 = v5;
  if ( FileName )
  {
    _InterlockedIncrement((volatile signed __int32 *)FileName + 6);
    v8 = RxContext->TrackerHistory[9].FileName;
    if ( v8 )
    {
      if ( *(PSZ *)v8 != v8 || *((_DWORD *)v8 + 5) >= LODWORD(WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink) )
      {
        _InterlockedOr((volatile signed __int32 *)&RxContext->ScavengerEntry, 0x40u);
        v9 = RxContext->TrackerHistory[9].FileName;
        v10 = (PSZ *)*((_QWORD *)v9 + 1);
        if ( *v10 == v9 )
        {
          *(_QWORD *)&RxContext->Info.FsInformationClass = v9;
          RxContext->Info.Buffer = v10;
          *v10 = (PSZ)&RxContext->Info;
          *((_QWORD *)v9 + 1) = &RxContext->Info;
          ++*((_DWORD *)RxContext->TrackerHistory[9].FileName + 4);
LABEL_14:
          KeReleaseSpinLock((PKSPIN_LOCK)&DeviceObject[1].Queue, v5);
          return;
        }
        goto LABEL_12;
      }
    }
  }
  if ( HIDWORD(DeviceObject[1].Queue.Wcb.DmaWaitEntry.Blink) >= FspPerDeviceThreshold )
  {
    _InterlockedOr((volatile signed __int32 *)&RxContext->ScavengerEntry, 0x10u);
    DeviceRoutine = (union _RX_CONTEXT::$5B7AEA49E590911F8F12743B7A0B9162 **)DeviceObject[1].Queue.Wcb.DeviceRoutine;
    if ( *DeviceRoutine == (union _RX_CONTEXT::$5B7AEA49E590911F8F12743B7A0B9162 *)&DeviceObject[1].Queue.Wcb.NumberOfChannels )
    {
      p_Info = (union _RX_CONTEXT::$5B7AEA49E590911F8F12743B7A0B9162 *)&RxContext->Info;
      *(_QWORD *)&p_Info->Info.FsInformationClass = (char *)DeviceObject + 432;
      p_Info->Info.Buffer = DeviceRoutine;
      *DeviceRoutine = p_Info;
      DeviceObject[1].Queue.Wcb.DeviceRoutine = (PDRIVER_CONTROL)p_Info;
      ++LODWORD(DeviceObject[1].Queue.Wcb.DmaWaitEntry.Blink);
      goto LABEL_14;
    }
LABEL_12:
    __fastfail(3u);
  }
  v11 = (struct _IO_WORKITEM *)ExpInterlockedPopEntrySList((PSLIST_HEADER)&DeviceObject[1].Queue.Wcb.DeviceContext);
  IoInitializeWorkItem(RxFileSystemDeviceObject, v11);
  _InterlockedIncrement((volatile signed __int32 *)&DeviceObject[1].Queue.Wcb.DmaWaitEntry.Blink + 1);
  v12 = RxContext->TrackerHistory[9].FileName;
  if ( v12 )
    ++*((_DWORD *)v12 + 5);
  KeReleaseSpinLock((PKSPIN_LOCK)&DeviceObject[1].Queue, v7);
  IoQueueWorkItemEx(v11, RxFspDispatch, CriticalWorkQueue, RxContext);
}

```

## disassembly

```asm
0x140007710  push    rbx
0x140007712  push    rbp
0x140007713  push    rsi
0x140007714  push    rdi
0x140007715  sub     rsp, 28h
0x140007719  mov     rax, [rdx+0B8h]
0x140007720  mov     rbx, rcx
0x140007723  mov     byte ptr [rcx+23h], 0
0x140007727  mov     rdi, [rax+28h]
0x14000772b  lea     rcx, [rdi+1A0h]; SpinLock
0x140007732  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007739  nop     dword ptr [rax+rax+00h]
0x14000773e  mov     rcx, [rbx+360h]
0x140007745  movzx   ebp, al
0x140007748  test    rcx, rcx
0x14000774b  jz      short loc_1400077AD
0x14000774d  lock inc dword ptr [rcx+18h]
0x140007751  mov     rcx, [rbx+360h]
0x140007758  test    rcx, rcx
0x14000775b  jz      short loc_1400077AD
0x14000775d  cmp     [rcx], rcx
0x140007760  jnz     short loc_14000776D
0x140007762  mov     eax, dword ptr cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink
0x140007768  cmp     [rcx+14h], eax
0x14000776b  jb      short loc_1400077AD
0x14000776d  lock or dword ptr [rbx+80h], 40h
0x140007775  mov     rdx, [rbx+360h]
0x14000777c  mov     r8, [rdx+8]
0x140007780  cmp     [r8], rdx
0x140007783  jnz     loc_140007858
0x140007789  lea     rax, [rbx+170h]
0x140007790  mov     [rax], rdx
0x140007793  mov     [rax+8], r8
0x140007797  mov     [r8], rax
0x14000779a  mov     [rdx+8], rax
0x14000779e  mov     rax, [rbx+360h]
0x1400077a5  inc     dword ptr [rax+10h]
0x1400077a8  jmp     loc_14000787A
0x1400077ad  mov     eax, cs:FspPerDeviceThreshold
0x1400077b3  cmp     [rdi+1ACh], eax
0x1400077b9  jnb     loc_140007840
0x1400077bf  lea     rcx, [rdi+1C0h]; ListHead
0x1400077c6  mov     [rsp+48h+arg_0], r14
0x1400077cb  call    cs:__imp_ExpInterlockedPopEntrySList
0x1400077d2  nop     dword ptr [rax+rax+00h]
0x1400077d7  mov     rcx, cs:RxFileSystemDeviceObject; IoObject
0x1400077de  mov     rdx, rax; IoWorkItem
0x1400077e1  mov     r14, rax
0x1400077e4  call    cs:__imp_IoInitializeWorkItem
0x1400077eb  nop     dword ptr [rax+rax+00h]
0x1400077f0  lock inc dword ptr [rdi+1ACh]
0x1400077f7  mov     rcx, [rbx+360h]
0x1400077fe  test    rcx, rcx
0x140007801  jz      short loc_140007806
0x140007803  inc     dword ptr [rcx+14h]
0x140007806  movzx   edx, bpl; NewIrql
0x14000780a  lea     rcx, [rdi+1A0h]; SpinLock
0x140007811  call    cs:__imp_KeReleaseSpinLock
0x140007818  nop     dword ptr [rax+rax+00h]
0x14000781d  mov     r9, rbx; Context
0x140007820  lea     rdx, RxFspDispatch; WorkerRoutine
0x140007827  xor     r8d, r8d; QueueType
0x14000782a  mov     rcx, r14; IoWorkItem
0x14000782d  call    cs:__imp_IoQueueWorkItemEx
0x140007834  nop     dword ptr [rax+rax+00h]
0x140007839  mov     r14, [rsp+48h+arg_0]
0x14000783e  jmp     short loc_140007891
0x140007840  lock or dword ptr [rbx+80h], 10h
0x140007848  lea     rax, [rdi+1B0h]
0x14000784f  mov     rcx, [rax+8]
0x140007853  cmp     [rcx], rax
0x140007856  jz      short loc_14000785F
0x140007858  mov     ecx, 3
0x14000785d  int     29h; Win8: RtlFailFast(ecx)
0x14000785f  add     rbx, 170h
0x140007866  mov     [rbx], rax
0x140007869  mov     [rbx+8], rcx
0x14000786d  mov     [rcx], rbx
0x140007870  mov     [rax+8], rbx
0x140007874  inc     dword ptr [rdi+1A8h]
0x14000787a  movzx   edx, bpl; NewIrql
0x14000787e  lea     rcx, [rdi+1A0h]; SpinLock
0x140007885  call    cs:__imp_KeReleaseSpinLock
0x14000788c  nop     dword ptr [rax+rax+00h]
0x140007891  add     rsp, 28h
0x140007895  pop     rdi
0x140007896  pop     rsi
0x140007897  pop     rbp
0x140007898  pop     rbx
0x140007899  retn
```
