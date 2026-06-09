# PmUpdateIds(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *)

- ea: `0x1400214fc`
- end: `0x1400215c7`
- name: `?PmUpdateIds@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z`
- size: `203`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _DRIVE_LAYOUT_INFORMATION_EX *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x14002184c`
- `0x140025ab8`

## callees

- `0x14000d878`
- `0x14000dbd0`
- `0x14001d090`
- `0x1400214fc`
- `0x1400215d0`
- `0x140021738`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400215a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400215a5`

## pseudocode

```c
__int64 __fastcall PmUpdateIds(struct _DEVICE_EXTENSION *a1, struct _DRIVE_LAYOUT_INFORMATION_EX *a2)
{
  int SnapshotData; // eax
  unsigned __int8 v5; // dl
  UCHAR *v6; // rdi
  int v7; // esi
  unsigned __int8 v8; // bp
  unsigned int v10; // [rsp+50h] [rbp+18h] BYREF
  PVOID P; // [rsp+58h] [rbp+20h] BYREF

  v10 = 0;
  P = 0;
  SnapshotData = PmGetSnapshotData(a1, a2, (struct _DISK_SNAPSHOT_DATA **)&P, &v10);
  v6 = (UCHAR *)P;
  v7 = SnapshotData;
  if ( SnapshotData >= 0 )
  {
    v8 = 0;
    if ( *((_DWORD *)P + 5) == 1 )
    {
      *((_DWORD *)P + 5) = 2;
      v8 = 1;
    }
    if ( a2->PartitionStyle )
    {
      if ( a2->PartitionStyle == 1 )
        PmUpdateIdsGpt(a2, v8);
    }
    else
    {
      PmUpdateIdsMbr(a2, v5);
    }
    v7 = PmWritePartitionTable(*((struct _DEVICE_OBJECT **)a1 + 1), a2);
    if ( v7 >= 0 && v8 )
      v7 = PmSetSnapshotData(a1, a2, v6, v10);
  }
  if ( v6 )
    ExFreePoolWithTag(v6, 0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400214fc  mov     rax, rsp
0x1400214ff  mov     [rax+8], rbx
0x140021503  mov     [rax+10h], rbp
0x140021507  push    rsi
0x140021508  push    rdi
0x140021509  push    r14
0x14002150b  sub     rsp, 20h
0x14002150f  lea     r9, [rax+18h]; unsigned int *
0x140021513  mov     dword ptr [rax+18h], 0
0x14002151a  lea     r8, [rax+20h]; struct _DISK_SNAPSHOT_DATA **
0x14002151e  mov     qword ptr [rax+20h], 0
0x140021526  mov     rbx, rdx
0x140021529  mov     r14, rcx
0x14002152c  call    ?PmGetSnapshotData@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEAPEAU_DISK_SNAPSHOT_DATA@@PEAK@Z; PmGetSnapshotData(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *,_DISK_SNAPSHOT_DATA * *,ulong *)
0x140021531  mov     rdi, [rsp+38h+P]
0x140021536  mov     esi, eax
0x140021538  test    eax, eax
0x14002153a  js      short loc_14002159B
0x14002153c  xor     bpl, bpl
0x14002153f  cmp     dword ptr [rdi+14h], 1
0x140021543  jnz     short loc_14002154F
0x140021545  mov     dword ptr [rdi+14h], 2
0x14002154c  mov     bpl, 1
0x14002154f  mov     ecx, [rbx]
0x140021551  test    ecx, ecx
0x140021553  jz      short loc_140021567
0x140021555  cmp     ecx, 1
0x140021558  jnz     short loc_14002156F
0x14002155a  mov     dl, bpl; unsigned __int8
0x14002155d  mov     rcx, rbx; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x140021560  call    ?PmUpdateIdsGpt@@YAXPEAU_DRIVE_LAYOUT_INFORMATION_EX@@E@Z; PmUpdateIdsGpt(_DRIVE_LAYOUT_INFORMATION_EX *,uchar)
0x140021565  jmp     short loc_14002156F
0x140021567  mov     rcx, rbx; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x14002156a  call    ?PmUpdateIdsMbr@@YAXPEAU_DRIVE_LAYOUT_INFORMATION_EX@@E@Z; PmUpdateIdsMbr(_DRIVE_LAYOUT_INFORMATION_EX *,uchar)
0x14002156f  mov     rcx, [r14+8]; struct _DEVICE_OBJECT *
0x140021573  mov     rdx, rbx; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x140021576  call    ?PmWritePartitionTable@@YAJPEAU_DEVICE_OBJECT@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; PmWritePartitionTable(_DEVICE_OBJECT *,_DRIVE_LAYOUT_INFORMATION_EX *)
0x14002157b  mov     esi, eax
0x14002157d  test    eax, eax
0x14002157f  js      short loc_14002159B
0x140021581  test    bpl, bpl
0x140021584  jz      short loc_14002159B
0x140021586  mov     r9d, [rsp+38h+arg_10]; unsigned int
0x14002158b  mov     r8, rdi; struct _DISK_SNAPSHOT_DATA *
0x14002158e  mov     rdx, rbx; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x140021591  mov     rcx, r14; struct _DEVICE_EXTENSION *
0x140021594  call    ?PmSetSnapshotData@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEAU_DISK_SNAPSHOT_DATA@@K@Z; PmSetSnapshotData(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *,_DISK_SNAPSHOT_DATA *,ulong)
0x140021599  mov     esi, eax
0x14002159b  test    rdi, rdi
0x14002159e  jz      short loc_1400215B1
0x1400215a0  xor     edx, edx; Tag
0x1400215a2  mov     rcx, rdi; P
0x1400215a5  call    cs:__imp_ExFreePoolWithTag
0x1400215ac  nop     dword ptr [rax+rax+00h]
0x1400215b1  mov     rbx, [rsp+38h+arg_0]
0x1400215b6  mov     eax, esi
0x1400215b8  mov     rbp, [rsp+38h+arg_8]
0x1400215bd  add     rsp, 20h
0x1400215c1  pop     r14
0x1400215c3  pop     rdi
0x1400215c4  pop     rsi
0x1400215c5  retn
```
