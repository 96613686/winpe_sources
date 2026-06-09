# PmUpdateAttributes(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *)

- ea: `0x14001ccb4`
- end: `0x14001cdd7`
- name: `?PmUpdateAttributes@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z`
- size: `291`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _DRIVE_LAYOUT_INFORMATION_EX *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x140005b2c`

## callees

- `0x14000ab3c`
- `0x14000d878`
- `0x14001ccb4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001cdb3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001cdb3`

## pseudocode

```c
__int64 __fastcall PmUpdateAttributes(struct _DEVICE_EXTENSION *a1, struct _DRIVE_LAYOUT_INFORMATION_EX *a2)
{
  PVOID v2; // r14
  unsigned int v3; // r15d
  unsigned __int64 v5; // rsi
  __int64 v6; // rdi
  int v7; // r8d
  int SnapshotData; // eax
  __int128 v10; // [rsp+20h] [rbp-30h] BYREF
  __int128 v11; // [rsp+30h] [rbp-20h]
  __int64 v12; // [rsp+40h] [rbp-10h]
  unsigned int v13; // [rsp+80h] [rbp+30h] BYREF
  PVOID P; // [rsp+88h] [rbp+38h] BYREF

  v2 = 0;
  v12 = 0;
  v3 = 0;
  v13 = 0;
  P = 0;
  v10 = 0;
  v11 = 0;
  if ( (*((_BYTE *)a1 + 604) || *((_DWORD *)a1 + 148) || *((_DWORD *)a1 + 149) || *((_DWORD *)a1 + 150))
    && (*((_QWORD *)a1 + 66) & 3) != 0 )
  {
    v5 = *((_QWORD *)&v10 + 1) & 0xFFFFFFFFFFFFFFFCuLL;
    v6 = v11 | 3;
    *((_QWORD *)&v10 + 1) &= 0xFFFFFFFFFFFFFFFCuLL;
    *(_QWORD *)&v11 = v11 | 3;
  }
  else
  {
    v6 = v11;
    v5 = *((_QWORD *)&v10 + 1);
  }
  if ( (*((_QWORD *)a1 + 66) & 1) != 0 || (v5 & 1) != 0 )
  {
    v7 = 0;
  }
  else
  {
    SnapshotData = PmGetSnapshotData(a1, a2, (struct _DISK_SNAPSHOT_DATA **)&P, &v13);
    v2 = P;
    v3 = SnapshotData;
    if ( SnapshotData < 0 )
      goto LABEL_16;
    v7 = 0;
    if ( *((_DWORD *)P + 5) == 1 )
    {
      *((_BYTE *)a1 + 604) = 0;
      v6 |= 1uLL;
      *((_QWORD *)&v10 + 1) = v5 | 1;
      *(_QWORD *)&v11 = v6;
      v7 = 3;
    }
  }
  if ( v6 )
  {
    LODWORD(v10) = 40;
    BYTE4(v10) = 1;
    v3 = PmSetDiskAttributes((__int64)a1, (__int64)&v10, v7);
  }
LABEL_16:
  if ( v2 )
    ExFreePoolWithTag(v2, 0);
  return v3;
}

```

## disassembly

```asm
0x14001ccb4  mov     [rsp-28h+arg_10], rbx
0x14001ccb9  push    rbp
0x14001ccba  push    rsi
0x14001ccbb  push    rdi
0x14001ccbc  push    r14
0x14001ccbe  push    r15
0x14001ccc0  mov     rbp, rsp
0x14001ccc3  sub     rsp, 50h
0x14001ccc7  xor     eax, eax
0x14001ccc9  xor     r14d, r14d
0x14001cccc  xorps   xmm0, xmm0
0x14001cccf  mov     [rbp+var_10], rax
0x14001ccd3  xor     r15d, r15d
0x14001ccd6  mov     [rbp+arg_0], eax
0x14001ccd9  mov     rbx, rcx
0x14001ccdc  mov     [rbp+P], r14
0x14001cce0  movups  [rbp+var_30], xmm0
0x14001cce4  movups  [rbp+var_20], xmm0
0x14001cce8  cmp     [rcx+25Ch], al
0x14001ccee  jnz     short loc_14001CD08
0x14001ccf0  cmp     [rcx+250h], eax
0x14001ccf6  jnz     short loc_14001CD08
0x14001ccf8  cmp     [rcx+254h], eax
0x14001ccfe  jnz     short loc_14001CD08
0x14001cd00  cmp     [rcx+258h], eax
0x14001cd06  jz      short loc_14001CD2D
0x14001cd08  mov     rax, [rcx+210h]
0x14001cd0f  test    al, 3
0x14001cd11  jz      short loc_14001CD2D
0x14001cd13  mov     rsi, qword ptr [rbp+var_30+8]
0x14001cd17  mov     rdi, qword ptr [rbp+var_20]
0x14001cd1b  and     rsi, 0FFFFFFFFFFFFFFFCh
0x14001cd1f  or      rdi, 3
0x14001cd23  mov     qword ptr [rbp+var_30+8], rsi
0x14001cd27  mov     qword ptr [rbp+var_20], rdi
0x14001cd2b  jmp     short loc_14001CD35
0x14001cd2d  mov     rdi, qword ptr [rbp+var_20]
0x14001cd31  mov     rsi, qword ptr [rbp+var_30+8]
0x14001cd35  mov     rax, [rcx+210h]
0x14001cd3c  test    al, 1
0x14001cd3e  jz      short loc_14001CD45
0x14001cd40  xor     r8d, r8d
0x14001cd43  jmp     short loc_14001CD8A
0x14001cd45  test    sil, 1
0x14001cd49  jnz     short loc_14001CD40
0x14001cd4b  lea     r9, [rbp+arg_0]; unsigned int *
0x14001cd4f  lea     r8, [rbp+P]; struct _DISK_SNAPSHOT_DATA **
0x14001cd53  call    ?PmGetSnapshotData@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEAPEAU_DISK_SNAPSHOT_DATA@@PEAK@Z; PmGetSnapshotData(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *,_DISK_SNAPSHOT_DATA * *,ulong *)
0x14001cd58  mov     r14, [rbp+P]
0x14001cd5c  mov     r15d, eax
0x14001cd5f  test    eax, eax
0x14001cd61  js      short loc_14001CDA9
0x14001cd63  xor     r8d, r8d
0x14001cd66  cmp     dword ptr [r14+14h], 1
0x14001cd6b  jnz     short loc_14001CD8A
0x14001cd6d  or      rsi, 1
0x14001cd71  mov     byte ptr [rbx+25Ch], 0
0x14001cd78  or      rdi, 1
0x14001cd7c  mov     qword ptr [rbp+var_30+8], rsi
0x14001cd80  mov     qword ptr [rbp+var_20], rdi
0x14001cd84  mov     r8d, 3
0x14001cd8a  test    rdi, rdi
0x14001cd8d  jz      short loc_14001CDA9
0x14001cd8f  lea     rdx, [rbp+var_30]
0x14001cd93  mov     dword ptr [rbp+var_30], 28h ; '('
0x14001cd9a  mov     rcx, rbx
0x14001cd9d  mov     byte ptr [rbp+var_30+4], 1
0x14001cda1  call    ?PmSetDiskAttributes@@YAJPEAU_DEVICE_EXTENSION@@PEAU_SET_DISK_ATTRIBUTES@@W4_DISK_OFFLINE_REASON@@@Z; PmSetDiskAttributes(_DEVICE_EXTENSION *,_SET_DISK_ATTRIBUTES *,_DISK_OFFLINE_REASON)
0x14001cda6  mov     r15d, eax
0x14001cda9  test    r14, r14
0x14001cdac  jz      short loc_14001CDBF
0x14001cdae  xor     edx, edx; Tag
0x14001cdb0  mov     rcx, r14; P
0x14001cdb3  call    cs:__imp_ExFreePoolWithTag
0x14001cdba  nop     dword ptr [rax+rax+00h]
0x14001cdbf  mov     rbx, [rsp+50h+arg_10]
0x14001cdc7  mov     eax, r15d
0x14001cdca  add     rsp, 50h
0x14001cdce  pop     r15
0x14001cdd0  pop     r14
0x14001cdd2  pop     rdi
0x14001cdd3  pop     rsi
0x14001cdd4  pop     rbp
0x14001cdd5  retn
```
