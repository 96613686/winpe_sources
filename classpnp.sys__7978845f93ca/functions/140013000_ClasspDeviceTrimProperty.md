# ClasspDeviceTrimProperty

- ea: `0x140013000`
- end: `0x140013238`
- name: `ClasspDeviceTrimProperty`
- size: `568`
- prototype: `NTSTATUS __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140019de0`

## callees

- `0x140005190`
- `0x140013000`
- `0x1400134a0`
- `0x1400175e0`
- `0x14003e940`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14001317c`
- `ntoskrnl!IofCallDriver` at `0x14001317c`
- `ntoskrnl!KeGetCurrentIrql` at `0x140013063`
- `ntoskrnl!KeGetCurrentIrql` at `0x140013063`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140013120`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140013120`

## pseudocode

```c
NTSTATUS __fastcall ClasspDeviceTrimProperty(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  struct _COMMON_DEVICE_EXTENSION *DeviceExtension; // rsi
  _IO_STACK_LOCATION *CurrentStackLocation; // rbp
  unsigned int Information; // r14d
  int v7; // ecx
  size_t Length; // r12
  _IRP *MasterIrp; // r15
  _PHYSICAL_DEVICE_EXTENSION *ChildList; // rcx
  int PartitionZeroExtension_high; // eax
  NTSTATUS RemoveTrackingUntrackedCount; // ebp
  _DWORD **v13; // r8
  signed __int32 v14; // eax
  NTSTATUS v16; // eax
  signed __int32 v17; // ett
  _PHYSICAL_DEVICE_EXTENSION *v18; // rax

  DeviceExtension = (struct _COMMON_DEVICE_EXTENSION *)DeviceObject->DeviceExtension;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  if ( DeviceObject->DeviceType != 7
    || (DeviceObject->Characteristics & 4) != 0
    || HIDWORD(DeviceExtension[2].ChildList->CommonExtension.PartitionZeroExtension) == 1 )
  {
    *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
    *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                               + 6);
    CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
    CurrentStackLocation[-1].Control = 0;
    ClassReleaseRemoveLock(DeviceObject, Irp);
    return IofCallDriver(DeviceExtension->LowerDeviceObject, Irp);
  }
  Information = 0;
  v7 = *(_DWORD *)(&Irp->AssociatedIrp.MasterIrp->Size + 1);
  if ( v7 == 1 )
  {
    RemoveTrackingUntrackedCount = 0;
  }
  else if ( v7 )
  {
    RemoveTrackingUntrackedCount = -1073741637;
  }
  else if ( KeGetCurrentIrql() >= 2u )
  {
    RemoveTrackingUntrackedCount = -1073741496;
  }
  else
  {
    Length = CurrentStackLocation->Parameters.Read.Length;
    MasterIrp = Irp->AssociatedIrp.MasterIrp;
    if ( (unsigned int)Length < 0xC )
    {
      if ( (unsigned int)Length < 8 )
      {
        RemoveTrackingUntrackedCount = -1073741789;
      }
      else
      {
        Information = 8;
        *(_DWORD *)&MasterIrp->Type = 12;
        *(_DWORD *)(&MasterIrp->Size + 1) = 12;
        RemoveTrackingUntrackedCount = 0;
      }
      goto LABEL_12;
    }
    ChildList = DeviceExtension[2].ChildList;
    PartitionZeroExtension_high = HIDWORD(ChildList->CommonExtension.PartitionZeroExtension);
    if ( PartitionZeroExtension_high )
    {
      RemoveTrackingUntrackedCount = 0;
      if ( PartitionZeroExtension_high != 2 )
        goto LABEL_12;
      RemoveTrackingUntrackedCount = ChildList->CommonExtension.RemoveTrackingUntrackedCount;
      if ( RemoveTrackingUntrackedCount < 0 )
        goto LABEL_12;
    }
    else
    {
      v16 = ClassForwardIrpSynchronous(DeviceExtension, Irp);
      RemoveTrackingUntrackedCount = v16;
      if ( v16 != -1073741637 && v16 != -1073741822 && v16 != -1073741808 && v16 != -1073741585 )
      {
        HIDWORD(DeviceExtension[2].ChildList->CommonExtension.PartitionZeroExtension) = 1;
        Information = Irp->IoStatus.Information;
        goto LABEL_12;
      }
      v18 = DeviceExtension[2].ChildList;
      RemoveTrackingUntrackedCount = v18->CommonExtension.RemoveTrackingUntrackedCount;
      HIDWORD(v18->CommonExtension.PartitionZeroExtension) = 2;
      if ( RemoveTrackingUntrackedCount < 0 )
        goto LABEL_12;
    }
    memset(MasterIrp, 0, Length);
    *(_DWORD *)&MasterIrp->Type = 12;
    Information = 12;
    *(_DWORD *)(&MasterIrp->Size + 1) = 12;
    LOBYTE(MasterIrp->MdlAddress) = *((_BYTE *)&DeviceExtension[2].ChildList->CommonExtension.RemoveTrackingUntrackedCount
                                    + 5) >> 7;
  }
LABEL_12:
  Irp->IoStatus.Information = Information;
  Irp->IoStatus.Status = RemoveTrackingUntrackedCount;
  v13 = (_DWORD **)DeviceObject->DeviceExtension;
  v14 = *v13[55];
  if ( v14 )
  {
    while ( 1 )
    {
      v17 = v14;
      v14 = _InterlockedCompareExchange(v13[55], v14 - 1, v14);
      if ( v17 == v14 )
        break;
      if ( !v14 )
        goto LABEL_13;
    }
  }
  else
  {
LABEL_13:
    ExReleaseRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)(v13[55] + 2));
  }
  ClassCompleteRequest(DeviceObject, Irp, 0);
  return RemoveTrackingUntrackedCount;
}

```

## disassembly

```asm
0x140013000  mov     [rsp+arg_18], rbx
0x140013005  push    rbp
0x140013006  push    rsi
0x140013007  push    rdi
0x140013008  sub     rsp, 20h
0x14001300c  cmp     dword ptr [rcx+48h], 7
0x140013010  mov     rdi, rdx
0x140013013  mov     rsi, [rcx+40h]
0x140013017  mov     rbx, rcx
0x14001301a  mov     rbp, [rdx+0B8h]
0x140013021  jnz     loc_14001314A
0x140013027  mov     eax, [rcx+34h]
0x14001302a  test    al, 4
0x14001302c  jnz     loc_14001314A
0x140013032  mov     rax, [rsi+480h]
0x140013039  cmp     dword ptr [rax+1Ch], 1
0x14001303d  jz      loc_14001314A
0x140013043  mov     rax, [rdx+18h]
0x140013047  mov     [rsp+38h+arg_8], r14
0x14001304c  xor     r14d, r14d
0x14001304f  mov     ecx, [rax+4]
0x140013052  cmp     ecx, 1
0x140013055  jz      loc_14001318A
0x14001305b  test    ecx, ecx
0x14001305d  jnz     loc_14001319B
0x140013063  call    cs:__imp_KeGetCurrentIrql
0x14001306a  nop     dword ptr [rax+rax+00h]
0x14001306f  cmp     al, 2
0x140013071  jnb     loc_140013191
0x140013077  mov     [rsp+38h+arg_0], r12
0x14001307c  mov     r12d, [rbp+8]
0x140013080  mov     [rsp+38h+arg_10], r15
0x140013085  mov     r15, [rdi+18h]
0x140013089  cmp     r12d, 0Ch
0x14001308d  jb      loc_1400131A5
0x140013093  mov     rcx, [rsi+480h]
0x14001309a  mov     eax, [rcx+1Ch]
0x14001309d  test    eax, eax
0x14001309f  jz      loc_1400131CB
0x1400130a5  xor     ebp, ebp
0x1400130a7  cmp     eax, 2
0x1400130aa  jnz     short loc_1400130E7
0x1400130ac  mov     ebp, [rcx+58h]
0x1400130af  test    ebp, ebp
0x1400130b1  js      short loc_1400130E7
0x1400130b3  mov     r8, r12; Size
0x1400130b6  xor     edx, edx; Val
0x1400130b8  mov     rcx, r15; void *
0x1400130bb  call    memset
0x1400130c0  mov     dword ptr [r15], 0Ch
0x1400130c7  mov     r14d, 0Ch
0x1400130cd  mov     dword ptr [r15+4], 0Ch
0x1400130d5  mov     rax, [rsi+480h]
0x1400130dc  movzx   ecx, byte ptr [rax+5Dh]
0x1400130e0  shr     cl, 7
0x1400130e3  mov     [r15+8], cl
0x1400130e7  mov     r12, [rsp+38h+arg_0]
0x1400130ec  mov     r15, [rsp+38h+arg_10]
0x1400130f1  mov     eax, r14d
0x1400130f4  mov     r14, [rsp+38h+arg_8]
0x1400130f9  mov     [rdi+38h], rax
0x1400130fd  mov     [rdi+30h], ebp
0x140013100  mov     r8, [rbx+40h]
0x140013104  mov     rax, [r8+1B8h]
0x14001310b  mov     eax, [rax]
0x14001310d  test    eax, eax
0x14001310f  jnz     loc_14001321B
0x140013115  mov     rcx, [r8+1B8h]
0x14001311c  add     rcx, 8; RunRefCacheAware
0x140013120  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140013127  nop     dword ptr [rax+rax+00h]
0x14001312c  xor     r8d, r8d; PriorityBoost
0x14001312f  mov     rdx, rdi; Irp
0x140013132  mov     rcx, rbx; DeviceObject
0x140013135  call    ClassCompleteRequest
0x14001313a  mov     eax, ebp
0x14001313c  mov     rbx, [rsp+38h+arg_18]
0x140013141  add     rsp, 20h
0x140013145  pop     rdi
0x140013146  pop     rsi
0x140013147  pop     rbp
0x140013148  retn
0x14001314a  movups  xmm0, xmmword ptr [rbp+0]
0x14001314e  movups  xmmword ptr [rbp-48h], xmm0
0x140013152  movups  xmm1, xmmword ptr [rbp+10h]
0x140013156  movups  xmmword ptr [rbp-38h], xmm1
0x14001315a  movups  xmm0, xmmword ptr [rbp+20h]
0x14001315e  movups  xmmword ptr [rbp-28h], xmm0
0x140013162  movsd   xmm1, qword ptr [rbp+30h]
0x140013167  movsd   qword ptr [rbp-18h], xmm1
0x14001316c  mov     byte ptr [rbp-45h], 0
0x140013170  call    ClassReleaseRemoveLock
0x140013175  mov     rcx, [rsi+10h]; DeviceObject
0x140013179  mov     rdx, rdi; Irp
0x14001317c  call    cs:__imp_IofCallDriver
0x140013183  nop     dword ptr [rax+rax+00h]
0x140013188  jmp     short loc_14001313C
0x14001318a  xor     ebp, ebp
0x14001318c  jmp     loc_1400130F1
0x140013191  mov     ebp, 0C0000148h
0x140013196  jmp     loc_1400130F1
0x14001319b  mov     ebp, 0C00000BBh
0x1400131a0  jmp     loc_1400130F1
0x1400131a5  cmp     r12d, 8
0x1400131a9  jb      loc_140040264
0x1400131af  mov     r14d, 8
0x1400131b5  mov     dword ptr [r15], 0Ch
0x1400131bc  mov     dword ptr [r15+4], 0Ch
0x1400131c4  xor     ebp, ebp
0x1400131c6  jmp     loc_1400130E7
0x1400131cb  mov     rdx, rdi; Irp
0x1400131ce  mov     rcx, rsi; CommonExtension
0x1400131d1  call    ClassForwardIrpSynchronous
0x1400131d6  mov     ebp, eax
0x1400131d8  cmp     eax, 0C00000BBh
0x1400131dd  jz      loc_14004026E
0x1400131e3  cmp     eax, 0C0000002h
0x1400131e8  jz      loc_14004026E
0x1400131ee  cmp     eax, 0C0000010h
0x1400131f3  jz      loc_14004026E
0x1400131f9  cmp     eax, 0C00000EFh
0x1400131fe  jz      loc_14004026E
0x140013204  mov     rcx, [rsi+480h]
0x14001320b  mov     dword ptr [rcx+1Ch], 1
0x140013212  mov     r14d, [rdi+38h]
0x140013216  jmp     loc_1400130E7
0x14001321b  mov     rcx, [r8+1B8h]
0x140013222  lea     edx, [rax-1]
0x140013225  lock cmpxchg [rcx], edx
0x140013229  jz      loc_14001312C
0x14001322f  test    eax, eax
0x140013231  jnz     short loc_14001321B
0x140013233  jmp     loc_140013115
0x140040264  mov     ebp, 0C0000023h
0x140040269  jmp     loc_1400130E7
0x14004026e  mov     rax, [rsi+480h]
0x140040275  mov     ebp, [rax+58h]
0x140040278  mov     dword ptr [rax+1Ch], 2
0x14004027f  test    ebp, ebp
0x140040281  js      loc_1400130E7
0x140040287  jmp     loc_1400130B3
```
