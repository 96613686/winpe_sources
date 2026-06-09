# ExtSTAStopVElan(EXTSTA_VELAN *)

- ea: `0x140064930`
- end: `0x140064a3b`
- name: `?ExtSTAStopVElan@@YAXPEAUEXTSTA_VELAN@@@Z`
- size: `267`
- prototype: `void __fastcall(struct EXTSTA_VELAN *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1400638d8`
- `0x140063b0c`
- `0x140064930`
- `0x140065ed4`
- `0x140079e34`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006499f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140064a0c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006499f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140064a0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400649b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064a1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400649b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064a1d`
- `NETIO!CancelMibChangeNotify2` at `0x140064945`
- `NETIO!CancelMibChangeNotify2` at `0x140064945`

## pseudocode

```c
void __fastcall ExtSTAStopVElan(struct EXTSTA_VELAN *a1)
{
  void *hIfChangeNotificationHandle; // rcx
  DOT11_ENCAP_ENTRY *pEncapTable; // rcx
  DOT11_ENCAP_ENTRY *v4; // rcx
  struct _WFD_ROLE *pWFDRole; // rcx
  char *pMcastList; // rcx
  ULONG *v7; // rcx

  hIfChangeNotificationHandle = a1->hIfChangeNotificationHandle;
  if ( hIfChangeNotificationHandle )
  {
    CancelMibChangeNotify2(hIfChangeNotificationHandle);
    a1->hIfChangeNotificationHandle = 0;
  }
  iReportNicAOACCompliance(a1, 0);
  ExtSTADeInitPmSettings(a1);
  ExtSTADeInitialize(a1);
  pEncapTable = a1->RoD.pEncapTable;
  if ( pEncapTable )
  {
    v4 = pEncapTable - 4;
    *(_QWORD *)&a1->RoD.uMaxSizeOfEncapTable = 0;
    if ( *(_QWORD *)&v4->usEtherType )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)&v4->usEtherType, v4);
    else
      ExFreePoolWithTag(v4, *(_DWORD *)&v4[2]);
    a1->RoD.pEncapTable = 0;
  }
  pWFDRole = a1->pWFDRole;
  if ( pWFDRole )
  {
    WFDRoleDeInitialize(pWFDRole);
    a1->pWFDRole = 0;
  }
  pMcastList = (char *)a1->Rw.MulticastList.pMcastList;
  if ( pMcastList )
  {
    v7 = (ULONG *)(pMcastList - 16);
    *(_QWORD *)&a1->Rw.MulticastList.uCurrentListSize = 0;
    if ( *(_QWORD *)v7 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v7, v7);
    else
      ExFreePoolWithTag(v7, v7[2]);
    a1->Rw.MulticastList.pMcastList = 0;
  }
}

```

## disassembly

```asm
0x140064930  push    rbx
0x140064932  sub     rsp, 20h
0x140064936  mov     rbx, rcx
0x140064939  mov     rcx, [rcx+0A68h]; NotificationHandle
0x140064940  test    rcx, rcx
0x140064943  jz      short loc_14006495C
0x140064945  call    cs:__imp_CancelMibChangeNotify2
0x14006494c  nop     dword ptr [rax+rax+00h]
0x140064951  mov     qword ptr [rbx+0A68h], 0
0x14006495c  xor     edx, edx; unsigned __int8
0x14006495e  mov     rcx, rbx; struct EXTSTA_VELAN *
0x140064961  call    ?iReportNicAOACCompliance@@YAXPEAUEXTSTA_VELAN@@E@Z; iReportNicAOACCompliance(EXTSTA_VELAN *,uchar)
0x140064966  mov     rcx, rbx
0x140064969  call    ExtSTADeInitPmSettings
0x14006496e  mov     rcx, rbx; struct EXTSTA_VELAN *
0x140064971  call    ExtSTADeInitialize
0x140064976  mov     rcx, [rbx+6A0h]
0x14006497d  test    rcx, rcx
0x140064980  jz      short loc_1400649C7
0x140064982  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140064986  mov     qword ptr [rbx+698h], 0
0x140064991  mov     rax, [rcx]
0x140064994  test    rax, rax
0x140064997  jz      short loc_1400649AD
0x140064999  mov     rdx, rcx; Entry
0x14006499c  mov     rcx, rax; Lookaside
0x14006499f  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400649a6  nop     dword ptr [rax+rax+00h]
0x1400649ab  jmp     short loc_1400649BC
0x1400649ad  mov     edx, [rcx+8]; Tag
0x1400649b0  call    cs:__imp_ExFreePoolWithTag
0x1400649b7  nop     dword ptr [rax+rax+00h]
0x1400649bc  mov     qword ptr [rbx+6A0h], 0
0x1400649c7  mov     rcx, [rbx+0A40h]; struct _WFD_ROLE *
0x1400649ce  test    rcx, rcx
0x1400649d1  jz      short loc_1400649E3
0x1400649d3  call    ?WFDRoleDeInitialize@@YAXPEAU_WFD_ROLE@@@Z; WFDRoleDeInitialize(_WFD_ROLE *)
0x1400649d8  mov     qword ptr [rbx+0A40h], 0
0x1400649e3  mov     rcx, [rbx+718h]
0x1400649ea  test    rcx, rcx
0x1400649ed  jz      short loc_140064A34
0x1400649ef  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x1400649f3  mov     qword ptr [rbx+720h], 0
0x1400649fe  mov     rax, [rcx]
0x140064a01  test    rax, rax
0x140064a04  jz      short loc_140064A1A
0x140064a06  mov     rdx, rcx; Entry
0x140064a09  mov     rcx, rax; Lookaside
0x140064a0c  call    cs:__imp_ExFreeToNPagedLookasideList
0x140064a13  nop     dword ptr [rax+rax+00h]
0x140064a18  jmp     short loc_140064A29
0x140064a1a  mov     edx, [rcx+8]; Tag
0x140064a1d  call    cs:__imp_ExFreePoolWithTag
0x140064a24  nop     dword ptr [rax+rax+00h]
0x140064a29  mov     qword ptr [rbx+718h], 0
0x140064a34  add     rsp, 20h
0x140064a38  pop     rbx
0x140064a39  retn
```
