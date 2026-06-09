# PmSetSnapshotData(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *,_DISK_SNAPSHOT_DATA *,ulong)

- ea: `0x14000dbd0`
- end: `0x14000def2`
- name: `?PmSetSnapshotData@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEAU_DISK_SNAPSHOT_DATA@@K@Z`
- size: `802`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _DRIVE_LAYOUT_INFORMATION_EX *, UCHAR *, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400214fc`
- `0x140021c90`

## callees

- `0x14000a014`
- `0x14000a964`
- `0x14000ada0`
- `0x14000cb34`
- `0x14000db5c`
- `0x14000dbd0`
- `0x14001c20c`
- `0x14001d090`
- `0x140021ec8`

## import_xrefs

- `ntoskrnl!RtlComputeCrc32` at `0x14000dc22`
- `ntoskrnl!RtlComputeCrc32` at `0x14000dc22`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000deb3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000deb3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000de6f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000de6f`

## pseudocode

```c
__int64 __fastcall PmSetSnapshotData(
        struct _DEVICE_EXTENSION *a1,
        struct _DRIVE_LAYOUT_INFORMATION_EX *a2,
        UCHAR *a3,
        unsigned int a4)
{
  int PartitionAttributesMbr; // edi
  ULONG v9; // r8d
  ULONG v10; // eax
  bool v11; // zf
  __int64 v12; // r8
  __int64 v13; // r10
  __int64 v14; // r11
  __int64 v15; // rdi
  __int64 v16; // r14
  __int64 v17; // r12
  __int64 v18; // r13
  __int64 v19; // r9
  __int64 v20; // rcx
  PARTITION_INFORMATION_MBR Mbr; // rax
  KIRQL v22; // r14
  struct _DEVICE_EXTENSION *i; // r8
  unsigned __int64 v25[11]; // [rsp+20h] [rbp-58h] BYREF

  v25[0] = 0;
  if ( !PmVerifySnapshotData(a3, a4, 0) )
    return (unsigned int)-1073741811;
  v9 = *((_DWORD *)a3 + 3);
  *((_DWORD *)a3 + 4) = 0;
  v10 = RtlComputeCrc32(0, a3, v9);
  v11 = *((_DWORD *)a3 + 5) == 2;
  *((_DWORD *)a3 + 4) = v10;
  if ( !v11 )
    goto LABEL_42;
  if ( !a2->PartitionStyle )
  {
    PartitionAttributesMbr = PmGetPartitionAttributesMbr(a1, a2, v25);
    if ( PartitionAttributesMbr < 0 )
      return (unsigned int)PartitionAttributesMbr;
    PartitionAttributesMbr = PmSetPartitionAttributesMbr(a1, a2, v25[0] | 0xF000000000000000uLL);
    if ( PartitionAttributesMbr < 0 )
      return (unsigned int)PartitionAttributesMbr;
    goto LABEL_38;
  }
  if ( a2->PartitionStyle != 1 )
  {
LABEL_38:
    v22 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 14);
    for ( i = (struct _DEVICE_EXTENSION *)*((_QWORD *)a1 + 112);
          i != (struct _DEVICE_EXTENSION *)((char *)a1 + 896);
          i = *(struct _DEVICE_EXTENSION **)i )
    {
      *((_DWORD *)i - 26) |= 0x10u;
    }
    PmQueueNotificationWorkItem(a1, "PmSetSnapshotData");
    KeReleaseSpinLock((PKSPIN_LOCK)a1 + 14, v22);
LABEL_42:
    PartitionAttributesMbr = PmWriteSnapshotData(a1, a2, (struct _DISK_SNAPSHOT_DATA *)a3, a4);
    if ( PartitionAttributesMbr >= 0 )
      PmInvalidateSnapshotDataCache(a1);
    return (unsigned int)PartitionAttributesMbr;
  }
  v12 = 0;
  if ( a2->PartitionCount )
  {
    v13 = *(_QWORD *)PARTITION_BSP_GUID.Data4;
    v14 = *(_QWORD *)PARTITION_DPP_GUID.Data4;
    v15 = *(_QWORD *)&PARTITION_DPP_GUID.Data1;
    v16 = *(_QWORD *)PARTITION_BASIC_DATA_GUID.Data4;
    v17 = *(_QWORD *)&PARTITION_BASIC_DATA_GUID.Data1;
    v18 = *(_QWORD *)PARTITION_MAIN_OS_GUID.Data4;
    v19 = *(_QWORD *)PARTITION_WINDOWS_SYSTEM_GUID.Data4;
    do
    {
      v20 = v12;
      Mbr = a2->PartitionEntry[v12].Mbr;
      if ( Mbr == *(_QWORD *)&PARTITION_BSP_GUID.Data1
        && *(_QWORD *)a2->PartitionEntry[v20].Gpt.PartitionType.Data4 == v13
        || Mbr == v15 && *(_QWORD *)a2->PartitionEntry[v20].Gpt.PartitionType.Data4 == v14
        || Mbr == v17 && *(_QWORD *)a2->PartitionEntry[v20].Gpt.PartitionType.Data4 == v16
        || Mbr == *(_QWORD *)&PARTITION_MAIN_OS_GUID.Data1
        && *(_QWORD *)a2->PartitionEntry[v20].Gpt.PartitionType.Data4 == v18
        || Mbr == *(_QWORD *)&PARTITION_MSFT_RECOVERY_GUID.Data1
        && *(_QWORD *)a2->PartitionEntry[v20].Gpt.PartitionType.Data4 == *(_QWORD *)PARTITION_MSFT_RECOVERY_GUID.Data4
        || *(_QWORD *)&a2->PartitionEntry[v20].Mbr == *(_QWORD *)&PARTITION_OS_DATA_GUID.Data1
        && *(_QWORD *)a2->PartitionEntry[v20].Gpt.PartitionType.Data4 == *(_QWORD *)PARTITION_OS_DATA_GUID.Data4
        || *(_QWORD *)&a2->PartitionEntry[v20].Mbr == *(_QWORD *)&PARTITION_PRE_INSTALLED_GUID.Data1
        && *(_QWORD *)a2->PartitionEntry[v20].Gpt.PartitionType.Data4 == *(_QWORD *)PARTITION_PRE_INSTALLED_GUID.Data4
        || *(_QWORD *)&a2->PartitionEntry[v20].Mbr == PARTITION_SERVICING_FILES_GUID
        && *(_QWORD *)a2->PartitionEntry[v20].Gpt.PartitionType.Data4 == 0x6A00C0A9EA8D4CAELL
        || *(_QWORD *)&a2->PartitionEntry[v20].Mbr == PARTITION_SERVICING_METADATA_GUID
        && *(_QWORD *)a2->PartitionEntry[v20].Gpt.PartitionType.Data4 == 0xCE29D2AF3D704EBBuLL
        || *(_QWORD *)&a2->PartitionEntry[v20].Mbr == PARTITION_SERVICING_RESERVE_GUID
        && *(_QWORD *)a2->PartitionEntry[v20].Gpt.PartitionType.Data4 == 0x146D13FEB6FF19A3LL
        || *(_QWORD *)&a2->PartitionEntry[v20].Mbr == PARTITION_SERVICING_STAGING_ROOT_GUID
        && *(_QWORD *)a2->PartitionEntry[v20].Gpt.PartitionType.Data4 == 0xDFB904BDBBECF3AAuLL
        || *(_QWORD *)&a2->PartitionEntry[v20].Mbr == *(_QWORD *)&PARTITION_WINDOWS_SYSTEM_GUID.Data1
        && *(_QWORD *)a2->PartitionEntry[v20].Gpt.PartitionType.Data4 == v19 )
      {
        a2->PartitionEntry[v20].Gpt.Attributes |= 0xF000000000000000uLL;
        v13 = *(_QWORD *)PARTITION_BSP_GUID.Data4;
        v14 = *(_QWORD *)PARTITION_DPP_GUID.Data4;
        v15 = *(_QWORD *)&PARTITION_DPP_GUID.Data1;
        v16 = *(_QWORD *)PARTITION_BASIC_DATA_GUID.Data4;
        v17 = *(_QWORD *)&PARTITION_BASIC_DATA_GUID.Data1;
        v18 = *(_QWORD *)PARTITION_MAIN_OS_GUID.Data4;
        v19 = *(_QWORD *)PARTITION_WINDOWS_SYSTEM_GUID.Data4;
      }
      v12 = (unsigned int)(v12 + 1);
    }
    while ( (unsigned int)v12 < a2->PartitionCount );
  }
  PartitionAttributesMbr = PmWritePartitionTable(*((struct _DEVICE_OBJECT **)a1 + 1), a2);
  if ( PartitionAttributesMbr >= 0 )
  {
    PmInvalidatePartitionTableCache(a1);
    goto LABEL_38;
  }
  return (unsigned int)PartitionAttributesMbr;
}

```

## disassembly

```asm
0x14000dbd0  push    rbx
0x14000dbd2  push    rbp
0x14000dbd3  push    rsi
0x14000dbd4  push    rdi
0x14000dbd5  push    r12
0x14000dbd7  push    r13
0x14000dbd9  push    r14
0x14000dbdb  push    r15
0x14000dbdd  sub     rsp, 38h
0x14000dbe1  mov     rbp, r8
0x14000dbe4  mov     [rsp+78h+var_58], 0
0x14000dbed  mov     rbx, rdx
0x14000dbf0  mov     rsi, rcx
0x14000dbf3  mov     rcx, rbp; Buffer
0x14000dbf6  xor     r8d, r8d; unsigned __int8
0x14000dbf9  mov     edx, r9d; unsigned int
0x14000dbfc  mov     r15d, r9d
0x14000dbff  call    ?PmVerifySnapshotData@@YAEPEAU_DISK_SNAPSHOT_DATA@@KE@Z; PmVerifySnapshotData(_DISK_SNAPSHOT_DATA *,ulong,uchar)
0x14000dc04  test    al, al
0x14000dc06  jnz     short loc_14000DC12
0x14000dc08  mov     edi, 0C000000Dh
0x14000dc0d  jmp     loc_14000DEDE
0x14000dc12  mov     r8d, [rbp+0Ch]; Length
0x14000dc16  mov     rdx, rbp; Buffer
0x14000dc19  xor     ecx, ecx; InitialCrc
0x14000dc1b  mov     dword ptr [rbp+10h], 0
0x14000dc22  call    cs:__imp_RtlComputeCrc32
0x14000dc29  nop     dword ptr [rax+rax+00h]
0x14000dc2e  cmp     dword ptr [rbp+14h], 2
0x14000dc32  mov     [rbp+10h], eax
0x14000dc35  jnz     loc_14000DEBF
0x14000dc3b  mov     ecx, [rbx]
0x14000dc3d  test    ecx, ecx
0x14000dc3f  jz      loc_14000DE2E
0x14000dc45  cmp     ecx, 1
0x14000dc48  jnz     loc_14000DE6B
0x14000dc4e  xor     r8d, r8d
0x14000dc51  cmp     [rbx+4], r8d
0x14000dc55  jbe     loc_14000DE0E
0x14000dc5b  mov     r10, qword ptr cs:PARTITION_BSP_GUID.Data4
0x14000dc62  mov     rdx, 0F000000000000000h
0x14000dc6c  mov     r11, qword ptr cs:PARTITION_DPP_GUID.Data4
0x14000dc73  mov     rdi, qword ptr cs:PARTITION_DPP_GUID.Data1
0x14000dc7a  mov     r14, qword ptr cs:PARTITION_BASIC_DATA_GUID.Data4
0x14000dc81  mov     r12, qword ptr cs:PARTITION_BASIC_DATA_GUID.Data1
0x14000dc88  mov     r13, qword ptr cs:PARTITION_MAIN_OS_GUID.Data4
0x14000dc8f  mov     r9, qword ptr cs:PARTITION_WINDOWS_SYSTEM_GUID.Data4
0x14000dc96  lea     rcx, [r8+r8*8]
0x14000dc9a  shl     rcx, 4
0x14000dc9e  mov     rax, [rcx+rbx+50h]
0x14000dca3  cmp     rax, qword ptr cs:PARTITION_BSP_GUID.Data1
0x14000dcaa  jnz     short loc_14000DCB7
0x14000dcac  cmp     [rcx+rbx+58h], r10
0x14000dcb1  jz      loc_14000DDCB
0x14000dcb7  cmp     rax, rdi
0x14000dcba  jnz     short loc_14000DCC7
0x14000dcbc  cmp     [rcx+rbx+58h], r11
0x14000dcc1  jz      loc_14000DDCB
0x14000dcc7  cmp     rax, r12
0x14000dcca  jnz     short loc_14000DCD7
0x14000dccc  cmp     [rcx+rbx+58h], r14
0x14000dcd1  jz      loc_14000DDCB
0x14000dcd7  cmp     rax, qword ptr cs:PARTITION_MAIN_OS_GUID.Data1
0x14000dcde  jnz     short loc_14000DCEB
0x14000dce0  cmp     [rcx+rbx+58h], r13
0x14000dce5  jz      loc_14000DDCB
0x14000dceb  cmp     rax, qword ptr cs:PARTITION_MSFT_RECOVERY_GUID.Data1
0x14000dcf2  jnz     short loc_14000DD06
0x14000dcf4  mov     rax, [rcx+rbx+58h]
0x14000dcf9  cmp     rax, qword ptr cs:PARTITION_MSFT_RECOVERY_GUID.Data4
0x14000dd00  jz      loc_14000DDCB
0x14000dd06  mov     rax, [rcx+rbx+50h]
0x14000dd0b  cmp     rax, qword ptr cs:PARTITION_OS_DATA_GUID.Data1
0x14000dd12  jnz     short loc_14000DD26
0x14000dd14  mov     rax, [rcx+rbx+58h]
0x14000dd19  cmp     rax, qword ptr cs:PARTITION_OS_DATA_GUID.Data4
0x14000dd20  jz      loc_14000DDCB
0x14000dd26  mov     rax, [rcx+rbx+50h]
0x14000dd2b  cmp     rax, qword ptr cs:PARTITION_PRE_INSTALLED_GUID.Data1
0x14000dd32  jnz     short loc_14000DD46
0x14000dd34  mov     rax, [rcx+rbx+58h]
0x14000dd39  cmp     rax, qword ptr cs:PARTITION_PRE_INSTALLED_GUID.Data4
0x14000dd40  jz      loc_14000DDCB
0x14000dd46  mov     rax, [rcx+rbx+50h]
0x14000dd4b  cmp     rax, cs:PARTITION_SERVICING_FILES_GUID
0x14000dd52  jnz     short loc_14000DD62
0x14000dd54  mov     rax, [rcx+rbx+58h]
0x14000dd59  cmp     rax, cs:qword_140013820
0x14000dd60  jz      short loc_14000DDCB
0x14000dd62  mov     rax, [rcx+rbx+50h]
0x14000dd67  cmp     rax, cs:PARTITION_SERVICING_METADATA_GUID
0x14000dd6e  jnz     short loc_14000DD7E
0x14000dd70  mov     rax, [rcx+rbx+58h]
0x14000dd75  cmp     rax, cs:qword_140013830
0x14000dd7c  jz      short loc_14000DDCB
0x14000dd7e  mov     rax, [rcx+rbx+50h]
0x14000dd83  cmp     rax, cs:PARTITION_SERVICING_RESERVE_GUID
0x14000dd8a  jnz     short loc_14000DD9A
0x14000dd8c  mov     rax, [rcx+rbx+58h]
0x14000dd91  cmp     rax, cs:qword_140013870
0x14000dd98  jz      short loc_14000DDCB
0x14000dd9a  mov     rax, [rcx+rbx+50h]
0x14000dd9f  cmp     rax, cs:PARTITION_SERVICING_STAGING_ROOT_GUID
0x14000dda6  jnz     short loc_14000DDB6
0x14000dda8  mov     rax, [rcx+rbx+58h]
0x14000ddad  cmp     rax, cs:qword_140013840
0x14000ddb4  jz      short loc_14000DDCB
0x14000ddb6  mov     rax, [rcx+rbx+50h]
0x14000ddbb  cmp     rax, qword ptr cs:PARTITION_WINDOWS_SYSTEM_GUID.Data1
0x14000ddc2  jnz     short loc_14000DE01
0x14000ddc4  cmp     [rcx+rbx+58h], r9
0x14000ddc9  jnz     short loc_14000DE01
0x14000ddcb  or      [rcx+rbx+70h], rdx
0x14000ddd0  mov     r10, qword ptr cs:PARTITION_BSP_GUID.Data4
0x14000ddd7  mov     r11, qword ptr cs:PARTITION_DPP_GUID.Data4
0x14000ddde  mov     rdi, qword ptr cs:PARTITION_DPP_GUID.Data1
0x14000dde5  mov     r14, qword ptr cs:PARTITION_BASIC_DATA_GUID.Data4
0x14000ddec  mov     r12, qword ptr cs:PARTITION_BASIC_DATA_GUID.Data1
0x14000ddf3  mov     r13, qword ptr cs:PARTITION_MAIN_OS_GUID.Data4
0x14000ddfa  mov     r9, qword ptr cs:PARTITION_WINDOWS_SYSTEM_GUID.Data4
0x14000de01  inc     r8d
0x14000de04  cmp     r8d, [rbx+4]
0x14000de08  jb      loc_14000DC96
0x14000de0e  mov     rcx, [rsi+8]; struct _DEVICE_OBJECT *
0x14000de12  mov     rdx, rbx; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x14000de15  call    ?PmWritePartitionTable@@YAJPEAU_DEVICE_OBJECT@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; PmWritePartitionTable(_DEVICE_OBJECT *,_DRIVE_LAYOUT_INFORMATION_EX *)
0x14000de1a  mov     edi, eax
0x14000de1c  test    eax, eax
0x14000de1e  js      loc_14000DEDE
0x14000de24  mov     rcx, rsi; struct _DEVICE_EXTENSION *
0x14000de27  call    ?PmInvalidatePartitionTableCache@@YAXPEAU_DEVICE_EXTENSION@@@Z; PmInvalidatePartitionTableCache(_DEVICE_EXTENSION *)
0x14000de2c  jmp     short loc_14000DE6B
0x14000de2e  lea     r8, [rsp+78h+var_58]; unsigned __int64 *
0x14000de33  mov     rdx, rbx; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x14000de36  mov     rcx, rsi; struct _DEVICE_EXTENSION *
0x14000de39  call    ?PmGetPartitionAttributesMbr@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEA_K@Z; PmGetPartitionAttributesMbr(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *,unsigned __int64 *)
0x14000de3e  mov     edi, eax
0x14000de40  test    eax, eax
0x14000de42  js      loc_14000DEDE
0x14000de48  mov     r8, [rsp+78h+var_58]
0x14000de4d  mov     rdx, 0F000000000000000h
0x14000de57  or      r8, rdx; unsigned __int64
0x14000de5a  mov     rcx, rsi; struct _DEVICE_EXTENSION *
0x14000de5d  mov     rdx, rbx; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x14000de60  call    ?PmSetPartitionAttributesMbr@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@_K@Z; PmSetPartitionAttributesMbr(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *,unsigned __int64)
0x14000de65  mov     edi, eax
0x14000de67  test    eax, eax
0x14000de69  js      short loc_14000DEDE
0x14000de6b  lea     rcx, [rsi+70h]; SpinLock
0x14000de6f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000de76  nop     dword ptr [rax+rax+00h]
0x14000de7b  lea     r9, [rsi+380h]
0x14000de82  mov     r14b, al
0x14000de85  mov     r8, [r9]
0x14000de88  jmp     short loc_14000DE98
0x14000de8a  mov     edx, [r8-68h]
0x14000de8e  or      edx, 10h
0x14000de91  mov     [r8-68h], edx
0x14000de95  mov     r8, [r8]
0x14000de98  cmp     r8, r9
0x14000de9b  jnz     short loc_14000DE8A
0x14000de9d  lea     rdx, aPmsetsnapshotd; "PmSetSnapshotData"
0x14000dea4  mov     rcx, rsi; struct _DEVICE_EXTENSION *
0x14000dea7  call    ?PmQueueNotificationWorkItem@@YAJPEAU_DEVICE_EXTENSION@@PEBD@Z; PmQueueNotificationWorkItem(_DEVICE_EXTENSION *,char const *)
0x14000deac  mov     dl, r14b; NewIrql
0x14000deaf  lea     rcx, [rsi+70h]; SpinLock
0x14000deb3  call    cs:__imp_KeReleaseSpinLock
0x14000deba  nop     dword ptr [rax+rax+00h]
0x14000debf  mov     r9d, r15d; unsigned int
0x14000dec2  mov     r8, rbp; struct _DISK_SNAPSHOT_DATA *
0x14000dec5  mov     rdx, rbx; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x14000dec8  mov     rcx, rsi; struct _DEVICE_EXTENSION *
0x14000decb  call    ?PmWriteSnapshotData@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEAU_DISK_SNAPSHOT_DATA@@K@Z; PmWriteSnapshotData(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *,_DISK_SNAPSHOT_DATA *,ulong)
0x14000ded0  mov     edi, eax
0x14000ded2  test    eax, eax
0x14000ded4  js      short loc_14000DEDE
0x14000ded6  mov     rcx, rsi; struct _DEVICE_EXTENSION *
0x14000ded9  call    ?PmInvalidateSnapshotDataCache@@YAXPEAU_DEVICE_EXTENSION@@@Z; PmInvalidateSnapshotDataCache(_DEVICE_EXTENSION *)
0x14000dede  mov     eax, edi
0x14000dee0  add     rsp, 38h
0x14000dee4  pop     r15
0x14000dee6  pop     r14
0x14000dee8  pop     r13
0x14000deea  pop     r12
0x14000deec  pop     rdi
0x14000deed  pop     rsi
0x14000deee  pop     rbp
0x14000deef  pop     rbx
0x14000def0  retn
```
