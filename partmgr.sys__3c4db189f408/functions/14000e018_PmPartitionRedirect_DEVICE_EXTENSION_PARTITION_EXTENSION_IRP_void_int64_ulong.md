# PmPartitionRedirect(_DEVICE_EXTENSION *,_PARTITION_EXTENSION *,_IRP *,void *,__int64,ulong)

- ea: `0x14000e018`
- end: `0x14000e169`
- name: `?PmPartitionRedirect@@YAJPEAU_DEVICE_EXTENSION@@PEAU_PARTITION_EXTENSION@@PEAU_IRP@@PEAX_JK@Z`
- size: `337`
- prototype: `int(struct _DEVICE_EXTENSION *, struct _PARTITION_EXTENSION *, struct _IRP *, void *, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400087c0`
- `0x14000e170`

## callees

- `0x140005a84`
- `0x14000e018`

## import_xrefs

- `ntoskrnl!IoForwardIrpSynchronously` at `0x14000e148`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x14000e148`
- `ntoskrnl!IoReuseIrp` at `0x14000e0f0`
- `ntoskrnl!IoReuseIrp` at `0x14000e0f0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e0a4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e0a4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e04b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e04b`

## pseudocode

```c
__int64 __fastcall PmPartitionRedirect(
        KSPIN_LOCK *a1,
        struct _PARTITION_EXTENSION *a2,
        struct _IRP *a3,
        void *a4,
        __int64 a5,
        unsigned int a6)
{
  int v10; // ebx
  KIRQL v11; // r10
  __int64 v12; // rsi
  __int64 v13; // rax
  IRP *v14; // rcx
  KSPIN_LOCK v15; // rax
  IRP *v16; // rbx
  struct _DEVICE_OBJECT *v17; // rcx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  __int128 v20; // [rsp+20h] [rbp-68h] BYREF
  __int128 v21; // [rsp+30h] [rbp-58h]
  __int128 v22; // [rsp+40h] [rbp-48h]

  v20 = 0;
  v21 = 0;
  v10 = 0;
  v22 = 0;
  KeAcquireSpinLockRaiseToDpc(a1 + 14);
  if ( PartitionOffset(a2, 1) != *((_QWORD *)a2 + 22) && !*((_QWORD *)a2 + 4) )
    v10 = -1073741790;
  v12 = a5;
  if ( *((_QWORD *)a2 + 4) )
  {
    v13 = *((_QWORD *)a2 + 29);
    a2 = (struct _PARTITION_EXTENSION *)*((_QWORD *)a2 + 4);
    v12 = (v13 & 0xFFFFFFFFFFFFFF00uLL) + a5;
  }
  KeReleaseSpinLock(a1 + 14, v11);
  if ( v10 >= 0 )
  {
    v14 = (IRP *)a1[107];
    *(_QWORD *)&v21 = a3;
    *(_QWORD *)&v20 = *((_QWORD *)a2 + 1);
    *((_QWORD *)&v20 + 1) = a1[3];
    DWORD2(v22) = a6;
    *((_QWORD *)&v21 + 1) = a4;
    *(_QWORD *)&v22 = v12;
    IoReuseIrp(v14, -1073741637);
    v15 = a1[107];
    --*(_BYTE *)(v15 + 67);
    *(_QWORD *)(v15 + 184) -= 72LL;
    v16 = (IRP *)a1[107];
    v17 = *(struct _DEVICE_OBJECT **)(*((_QWORD *)a2 + 14) + 40LL);
    CurrentStackLocation = v16->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation->MajorFunction = 15;
    v16->AssociatedIrp.MasterIrp = (struct _IRP *)&v20;
    CurrentStackLocation->Parameters.Read.Length = 0;
    CurrentStackLocation->Parameters.Create.Options = 48;
    CurrentStackLocation->Parameters.Read.ByteOffset.LowPart = 7733300;
    IoForwardIrpSynchronously(v17, v16);
    return (unsigned int)v16->IoStatus.Status;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14000e018  push    rbx
0x14000e01a  push    rbp
0x14000e01b  push    rsi
0x14000e01c  push    rdi
0x14000e01d  push    r12
0x14000e01f  push    r14
0x14000e021  push    r15
0x14000e023  sub     rsp, 50h
0x14000e027  xorps   xmm0, xmm0
0x14000e02a  mov     r14, rcx
0x14000e02d  add     rcx, 70h ; 'p'; SpinLock
0x14000e031  mov     r15, r9
0x14000e034  movups  [rsp+88h+var_68], xmm0
0x14000e039  mov     r12, r8
0x14000e03c  mov     rdi, rdx
0x14000e03f  movups  [rsp+88h+var_58], xmm0
0x14000e044  xor     ebx, ebx
0x14000e046  movups  [rsp+88h+var_48], xmm0
0x14000e04b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000e052  nop     dword ptr [rax+rax+00h]
0x14000e057  mov     dl, 1; unsigned __int8
0x14000e059  mov     rcx, rdi; struct _PARTITION_EXTENSION *
0x14000e05c  mov     r10b, al
0x14000e05f  call    ?PartitionOffset@@YA_KPEAU_PARTITION_EXTENSION@@E@Z; PartitionOffset(_PARTITION_EXTENSION *,uchar)
0x14000e064  cmp     rax, [rdi+0B0h]
0x14000e06b  jz      short loc_14000E079
0x14000e06d  cmp     [rdi+20h], rbx
0x14000e071  mov     eax, 0C0000022h
0x14000e076  cmovz   ebx, eax
0x14000e079  mov     rcx, [rdi+20h]
0x14000e07d  mov     rsi, [rsp+88h+arg_20]
0x14000e085  test    rcx, rcx
0x14000e088  jz      short loc_14000E09D
0x14000e08a  mov     rax, [rdi+0E8h]
0x14000e091  mov     rdi, rcx
0x14000e094  and     rax, 0FFFFFFFFFFFFFF00h
0x14000e09a  add     rsi, rax
0x14000e09d  mov     dl, r10b; NewIrql
0x14000e0a0  lea     rcx, [r14+70h]; SpinLock
0x14000e0a4  call    cs:__imp_KeReleaseSpinLock
0x14000e0ab  nop     dword ptr [rax+rax+00h]
0x14000e0b0  test    ebx, ebx
0x14000e0b2  js      loc_14000E157
0x14000e0b8  mov     rcx, [r14+358h]; Irp
0x14000e0bf  mov     edx, 0C00000BBh; Iostatus
0x14000e0c4  mov     qword ptr [rsp+88h+var_58], r12
0x14000e0c9  mov     rax, [rdi+8]
0x14000e0cd  mov     qword ptr [rsp+88h+var_68], rax
0x14000e0d2  mov     rax, [r14+18h]
0x14000e0d6  mov     qword ptr [rsp+88h+var_68+8], rax
0x14000e0db  mov     eax, [rsp+88h+arg_28]
0x14000e0e2  mov     dword ptr [rsp+88h+var_48+8], eax
0x14000e0e6  mov     qword ptr [rsp+88h+var_58+8], r15
0x14000e0eb  mov     qword ptr [rsp+88h+var_48], rsi
0x14000e0f0  call    cs:__imp_IoReuseIrp
0x14000e0f7  nop     dword ptr [rax+rax+00h]
0x14000e0fc  mov     rax, [r14+358h]
0x14000e103  lea     rdx, [rsp+88h+var_68]
0x14000e108  dec     byte ptr [rax+43h]
0x14000e10b  add     qword ptr [rax+0B8h], 0FFFFFFFFFFFFFFB8h
0x14000e113  mov     rax, [rdi+70h]
0x14000e117  mov     rbx, [r14+358h]
0x14000e11e  mov     rcx, [rax+28h]; DeviceObject
0x14000e122  mov     rax, [rbx+0B8h]
0x14000e129  mov     byte ptr [rax], 0Fh
0x14000e12c  mov     [rbx+18h], rdx
0x14000e130  mov     rdx, rbx; Irp
0x14000e133  mov     dword ptr [rax+8], 0
0x14000e13a  mov     dword ptr [rax+10h], 30h ; '0'
0x14000e141  mov     dword ptr [rax+18h], 760034h
0x14000e148  call    cs:__imp_IoForwardIrpSynchronously
0x14000e14f  nop     dword ptr [rax+rax+00h]
0x14000e154  mov     ebx, [rbx+30h]
0x14000e157  mov     eax, ebx
0x14000e159  add     rsp, 50h
0x14000e15d  pop     r15
0x14000e15f  pop     r14
0x14000e161  pop     r12
0x14000e163  pop     rdi
0x14000e164  pop     rsi
0x14000e165  pop     rbp
0x14000e166  pop     rbx
0x14000e167  retn
```
