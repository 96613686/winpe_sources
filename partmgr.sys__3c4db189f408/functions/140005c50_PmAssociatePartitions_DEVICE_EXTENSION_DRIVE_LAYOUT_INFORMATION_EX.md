# PmAssociatePartitions(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *)

- ea: `0x140005c50`
- end: `0x140005d6f`
- name: `?PmAssociatePartitions@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z`
- size: `287`
- prototype: `__int64 __fastcall(KSPIN_LOCK *, struct _DRIVE_LAYOUT_INFORMATION_EX *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140005b2c`

## callees

- `0x140004c80`
- `0x140004db8`
- `0x140005c50`
- `0x14000a21c`
- `0x14000c47c`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140005d2a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005d61`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005d2a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005d61`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005c6e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005c6e`

## pseudocode

```c
__int64 __fastcall PmAssociatePartitions(KSPIN_LOCK *a1, struct _DRIVE_LAYOUT_INFORMATION_EX *a2)
{
  KSPIN_LOCK *v2; // r14
  int inserted; // ebp
  _QWORD **v6; // rdi
  KIRQL v7; // r15
  _QWORD *i; // rbx
  _QWORD *v9; // rdx
  _QWORD *j; // rbx
  struct _PARTITION_EXTENSION *v11; // rcx

  v2 = a1 + 14;
  inserted = 0;
  v6 = (_QWORD **)(a1 + 112);
  v7 = KeAcquireSpinLockRaiseToDpc(a1 + 14);
  for ( i = *v6; i != v6; i = (_QWORD *)*i )
  {
    v9 = i - 18;
    *(i - 14) = 0;
    if ( a2->PartitionStyle == 1
      && v9[25] == *(_QWORD *)&PARTITION_PATCH_GUID.Data1
      && v9[26] == *(_QWORD *)PARTITION_PATCH_GUID.Data4 )
    {
      *((_DWORD *)v9 + 10) |= 0x40u;
      inserted = PmAssociatePartition((struct _DEVICE_EXTENSION *)a1, (struct _PARTITION_EXTENSION *)v9);
      if ( inserted < 0 )
      {
LABEL_16:
        KeReleaseSpinLock(v2, v7);
        goto LABEL_15;
      }
    }
  }
  for ( j = *v6; j != v6; j = (_QWORD *)*j )
  {
    v11 = (struct _PARTITION_EXTENSION *)(j - 18);
    if ( (*(_DWORD *)(j - 13) & 0x40) == 0
      && *((struct _PARTITION_EXTENSION **)v11 + 41) == (struct _PARTITION_EXTENSION *)((char *)v11 + 328) )
    {
      inserted = PartitionInsertPatch(v11, 0, *((_QWORD *)v11 + 22), *((_QWORD *)v11 + 23));
      if ( inserted < 0 )
        goto LABEL_16;
    }
  }
  KeReleaseSpinLock(v2, v7);
  PmCommitPending((struct _DEVICE_EXTENSION *)a1, a2);
LABEL_15:
  PmFreePending((struct _DEVICE_EXTENSION *)a1);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x140005c50  push    rbx
0x140005c52  push    rbp
0x140005c53  push    rsi
0x140005c54  push    rdi
0x140005c55  push    r12
0x140005c57  push    r14
0x140005c59  push    r15
0x140005c5b  sub     rsp, 20h
0x140005c5f  lea     r14, [rcx+70h]
0x140005c63  mov     rsi, rcx
0x140005c66  mov     rcx, r14; SpinLock
0x140005c69  xor     ebp, ebp
0x140005c6b  mov     r12, rdx
0x140005c6e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005c75  nop     dword ptr [rax+rax+00h]
0x140005c7a  lea     rdi, [rsi+380h]
0x140005c81  mov     r15b, al
0x140005c84  mov     rbx, [rdi]
0x140005c87  jmp     short loc_140005CDD
0x140005c89  lea     rdx, [rbx-90h]; struct _PARTITION_EXTENSION *
0x140005c90  mov     qword ptr [rdx+20h], 0
0x140005c98  cmp     dword ptr [r12], 1
0x140005c9d  jnz     short loc_140005CDA
0x140005c9f  mov     rax, [rdx+0C8h]
0x140005ca6  cmp     rax, qword ptr cs:PARTITION_PATCH_GUID.Data1
0x140005cad  jnz     short loc_140005CDA
0x140005caf  mov     rax, [rdx+0D0h]
0x140005cb6  cmp     rax, qword ptr cs:PARTITION_PATCH_GUID.Data4
0x140005cbd  jnz     short loc_140005CDA
0x140005cbf  mov     eax, [rdx+28h]
0x140005cc2  mov     rcx, rsi; struct _DEVICE_EXTENSION *
0x140005cc5  or      eax, 40h
0x140005cc8  mov     [rdx+28h], eax
0x140005ccb  call    ?PmAssociatePartition@@YAJPEAU_DEVICE_EXTENSION@@PEAU_PARTITION_EXTENSION@@@Z; PmAssociatePartition(_DEVICE_EXTENSION *,_PARTITION_EXTENSION *)
0x140005cd0  mov     ebp, eax
0x140005cd2  test    eax, eax
0x140005cd4  js      loc_140005D5B
0x140005cda  mov     rbx, [rbx]
0x140005cdd  cmp     rbx, rdi
0x140005ce0  jnz     short loc_140005C89
0x140005ce2  mov     rbx, [rdi]
0x140005ce5  jmp     short loc_140005D1F
0x140005ce7  lea     rcx, [rbx-90h]; struct _PARTITION_EXTENSION *
0x140005cee  mov     eax, [rcx+28h]
0x140005cf1  test    al, 40h
0x140005cf3  jnz     short loc_140005D1C
0x140005cf5  lea     rax, [rcx+148h]
0x140005cfc  cmp     [rax], rax
0x140005cff  jnz     short loc_140005D1C
0x140005d01  mov     r9, [rcx+0B8h]; unsigned __int64
0x140005d08  xor     edx, edx; unsigned __int64
0x140005d0a  mov     r8, [rcx+0B0h]; unsigned __int64
0x140005d11  call    ?PartitionInsertPatch@@YAJPEAU_PARTITION_EXTENSION@@_K11@Z; PartitionInsertPatch(_PARTITION_EXTENSION *,unsigned __int64,unsigned __int64,unsigned __int64)
0x140005d16  mov     ebp, eax
0x140005d18  test    eax, eax
0x140005d1a  js      short loc_140005D5B
0x140005d1c  mov     rbx, [rbx]
0x140005d1f  cmp     rbx, rdi
0x140005d22  jnz     short loc_140005CE7
0x140005d24  mov     dl, r15b; NewIrql
0x140005d27  mov     rcx, r14; SpinLock
0x140005d2a  call    cs:__imp_KeReleaseSpinLock
0x140005d31  nop     dword ptr [rax+rax+00h]
0x140005d36  mov     rdx, r12; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x140005d39  mov     rcx, rsi; struct _DEVICE_EXTENSION *
0x140005d3c  call    ?PmCommitPending@@YAXPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; PmCommitPending(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *)
0x140005d41  mov     rcx, rsi; struct _DEVICE_EXTENSION *
0x140005d44  call    ?PmFreePending@@YAXPEAU_DEVICE_EXTENSION@@@Z; PmFreePending(_DEVICE_EXTENSION *)
0x140005d49  mov     eax, ebp
0x140005d4b  add     rsp, 20h
0x140005d4f  pop     r15
0x140005d51  pop     r14
0x140005d53  pop     r12
0x140005d55  pop     rdi
0x140005d56  pop     rsi
0x140005d57  pop     rbp
0x140005d58  pop     rbx
0x140005d59  retn
0x140005d5b  mov     dl, r15b; NewIrql
0x140005d5e  mov     rcx, r14; SpinLock
0x140005d61  call    cs:__imp_KeReleaseSpinLock
0x140005d68  nop     dword ptr [rax+rax+00h]
0x140005d6d  jmp     short loc_140005D41
```
