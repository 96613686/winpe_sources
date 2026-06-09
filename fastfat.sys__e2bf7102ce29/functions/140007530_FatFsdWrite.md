# FatFsdWrite

- ea: `0x140007530`
- end: `0x14000769d`
- name: `FatFsdWrite`
- size: `365`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1400023c0`
- `0x140005288`
- `0x140007530`
- `0x140023d4c`
- `0x140039550`
- `0x14003960c`
- `0x140047d24`
- `0x14004af08`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140007556`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140007556`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14000760d`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140007665`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140007678`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14000760d`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140007665`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140007678`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400075aa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140007684`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400075aa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140007684`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1400075d2`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1400075d2`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400075f0`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400075f0`

## pseudocode

```c
__int64 __fastcall FatFsdWrite(__int64 a1, IRP *a2)
{
  char v3; // di
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  PDEVICE_OBJECT DeviceObject; // rdx
  __int64 FsContext; // rdx
  char IsIrpTopLevel; // r14
  BOOLEAN IsOperationSynchronous; // al
  unsigned __int8 *IrpContext; // rsi
  unsigned int v11; // eax
  unsigned int v12; // ebx

  v3 = 0;
  KeEnterCriticalRegion();
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  DeviceObject = CurrentStackLocation->DeviceObject;
  if ( DeviceObject == (PDEVICE_OBJECT)qword_140017CC8
    || DeviceObject == (PDEVICE_OBJECT)qword_140017CD0
    || (FsContext = (__int64)CurrentStackLocation->FileObject->FsContext, *(_WORD *)FsContext != 1282)
    || (*(_DWORD *)(FsContext + 192) & 4) == 0 )
  {
    IsIrpTopLevel = FatIsIrpTopLevel(a2);
    IsOperationSynchronous = IoIsOperationSynchronous(a2);
    IrpContext = (unsigned __int8 *)FatCreateIrpContext(a2, IsOperationSynchronous);
    if ( IoGetTopLevelIrp() == (PIRP)3 )
    {
      v3 = 1;
      IoSetTopLevelIrp(a2);
    }
    if ( (IrpContext[65] & 4) != 0 )
      v11 = FatCompleteMdl(IrpContext, a2);
    else
      v11 = FatCommonWrite((__int64)IrpContext, a2);
    v12 = v11;
    if ( v3 )
      IoSetTopLevelIrp((PIRP)3);
    if ( IsIrpTopLevel )
      IoSetTopLevelIrp(0);
    KeLeaveCriticalRegion();
    return v12;
  }
  else
  {
    CurrentStackLocation->Control |= 1u;
    FatPagingFileIo(a2, FsContext);
    KeLeaveCriticalRegion();
    return 259;
  }
}

```

## disassembly

```asm
0x140007530  mov     rax, rsp
0x140007533  mov     [rax+10h], rdx
0x140007537  push    rbx
0x140007538  push    rsi
0x140007539  push    rdi
0x14000753a  push    r14
0x14000753c  sub     rsp, 38h
0x140007540  mov     rbx, rdx
0x140007543  mov     qword ptr [rax-30h], 0
0x14000754b  xor     dil, dil
0x14000754e  mov     [rax-38h], dil
0x140007552  mov     [rax-37h], dil
0x140007556  call    cs:__imp_KeEnterCriticalRegion
0x14000755d  nop     dword ptr [rax+rax+00h]
0x140007562  mov     rcx, [rbx+0B8h]
0x140007569  mov     rdx, [rcx+28h]
0x14000756d  cmp     rdx, cs:qword_140017CC8
0x140007574  jz      short loc_1400075C0
0x140007576  cmp     rdx, cs:qword_140017CD0
0x14000757d  jz      short loc_1400075C0
0x14000757f  mov     rax, [rcx+30h]
0x140007583  mov     rdx, [rax+18h]
0x140007587  mov     eax, 502h
0x14000758c  cmp     [rdx], ax
0x14000758f  jnz     short loc_1400075C0
0x140007591  mov     eax, [rdx+0C0h]
0x140007597  test    al, 4
0x140007599  jz      short loc_1400075C0
0x14000759b  mov     dil, 1
0x14000759e  or      [rcx+3], dil
0x1400075a2  mov     rcx, rbx; Irp
0x1400075a5  call    FatPagingFileIo
0x1400075aa  call    cs:__imp_KeLeaveCriticalRegion
0x1400075b1  nop     dword ptr [rax+rax+00h]
0x1400075b6  mov     eax, 103h
0x1400075bb  jmp     loc_140007692
0x1400075c0  mov     rcx, rbx; Irp
0x1400075c3  call    FatIsIrpTopLevel
0x1400075c8  mov     r14b, al
0x1400075cb  mov     [rsp+58h+var_37], al
0x1400075cf  mov     rcx, rbx; Irp
0x1400075d2  call    cs:__imp_IoIsOperationSynchronous
0x1400075d9  nop     dword ptr [rax+rax+00h]
0x1400075de  mov     dl, al
0x1400075e0  mov     rcx, rbx
0x1400075e3  call    FatCreateIrpContext
0x1400075e8  mov     rsi, rax
0x1400075eb  mov     [rsp+58h+Entry], rax
0x1400075f0  call    cs:__imp_IoGetTopLevelIrp
0x1400075f7  nop     dword ptr [rax+rax+00h]
0x1400075fc  cmp     rax, 3
0x140007600  jnz     short loc_140007619
0x140007602  mov     dil, 1
0x140007605  mov     [rsp+58h+var_38], dil
0x14000760a  mov     rcx, rbx; Irp
0x14000760d  call    cs:__imp_IoSetTopLevelIrp
0x140007614  nop     dword ptr [rax+rax+00h]
0x140007619  mov     rdx, rbx; int
0x14000761c  mov     rcx, rsi; int
0x14000761f  test    byte ptr [rsi+41h], 4
0x140007623  jz      short loc_14000762C
0x140007625  call    FatCompleteMdl
0x14000762a  jmp     short loc_140007631
0x14000762c  call    FatCommonWrite
0x140007631  mov     [rsp+58h+var_34], eax
0x140007635  mov     ebx, eax
0x140007637  jmp     short loc_14000765B
0x140007639  mov     r8d, eax
0x14000763c  mov     rdx, [rsp+58h+Irp]; Irp
0x140007641  mov     rcx, [rsp+58h+Entry]; Entry
0x140007646  call    FatProcessException
0x14000764b  mov     ebx, eax
0x14000764d  mov     [rsp+58h+var_34], eax
0x140007651  mov     dil, [rsp+58h+var_38]
0x140007656  mov     r14b, [rsp+58h+var_37]
0x14000765b  test    dil, dil
0x14000765e  jz      short loc_140007671
0x140007660  mov     ecx, 3; Irp
0x140007665  call    cs:__imp_IoSetTopLevelIrp
0x14000766c  nop     dword ptr [rax+rax+00h]
0x140007671  test    r14b, r14b
0x140007674  jz      short loc_140007684
0x140007676  xor     ecx, ecx; Irp
0x140007678  call    cs:__imp_IoSetTopLevelIrp
0x14000767f  nop     dword ptr [rax+rax+00h]
0x140007684  call    cs:__imp_KeLeaveCriticalRegion
0x14000768b  nop     dword ptr [rax+rax+00h]
0x140007690  mov     eax, ebx
0x140007692  add     rsp, 38h
0x140007696  pop     r14
0x140007698  pop     rdi
0x140007699  pop     rsi
0x14000769a  pop     rbx
0x14000769b  retn
0x14000d3d8  push    rbp
0x14000d3da  sub     rsp, 20h
0x14000d3de  mov     rbp, rdx
0x14000d3e1  mov     rdx, rcx
0x14000d3e4  mov     rcx, [rbp+28h]
0x14000d3e8  call    FatExceptionFilter
0x14000d3ed  nop
0x14000d3ee  add     rsp, 20h
0x14000d3f2  pop     rbp
0x14000d3f3  retn
```
