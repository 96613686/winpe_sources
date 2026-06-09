# ExtSTAStopVElan(EXTSTA_VELAN *)

- ea: `0x140066160`
- end: `0x14006626b`
- name: `?ExtSTAStopVElan@@YAXPEAUEXTSTA_VELAN@@@Z`
- size: `267`
- prototype: `void __fastcall(struct EXTSTA_VELAN *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140065108`
- `0x14006533c`
- `0x140066160`
- `0x140067704`
- `0x14007b664`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400661cf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006623c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400661cf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006623c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400661e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006624d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400661e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006624d`
- `NETIO!CancelMibChangeNotify2` at `0x140066175`
- `NETIO!CancelMibChangeNotify2` at `0x140066175`

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
0x140066160  push    rbx
0x140066162  sub     rsp, 20h
0x140066166  mov     rbx, rcx
0x140066169  mov     rcx, [rcx+0A68h]; NotificationHandle
0x140066170  test    rcx, rcx
0x140066173  jz      short loc_14006618C
0x140066175  call    cs:__imp_CancelMibChangeNotify2
0x14006617c  nop     dword ptr [rax+rax+00h]
0x140066181  mov     qword ptr [rbx+0A68h], 0
0x14006618c  xor     edx, edx; unsigned __int8
0x14006618e  mov     rcx, rbx; struct EXTSTA_VELAN *
0x140066191  call    ?iReportNicAOACCompliance@@YAXPEAUEXTSTA_VELAN@@E@Z; iReportNicAOACCompliance(EXTSTA_VELAN *,uchar)
0x140066196  mov     rcx, rbx
0x140066199  call    ExtSTADeInitPmSettings
0x14006619e  mov     rcx, rbx; struct EXTSTA_VELAN *
0x1400661a1  call    ExtSTADeInitialize
0x1400661a6  mov     rcx, [rbx+6A0h]
0x1400661ad  test    rcx, rcx
0x1400661b0  jz      short loc_1400661F7
0x1400661b2  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x1400661b6  mov     qword ptr [rbx+698h], 0
0x1400661c1  mov     rax, [rcx]
0x1400661c4  test    rax, rax
0x1400661c7  jz      short loc_1400661DD
0x1400661c9  mov     rdx, rcx; Entry
0x1400661cc  mov     rcx, rax; Lookaside
0x1400661cf  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400661d6  nop     dword ptr [rax+rax+00h]
0x1400661db  jmp     short loc_1400661EC
0x1400661dd  mov     edx, [rcx+8]; Tag
0x1400661e0  call    cs:__imp_ExFreePoolWithTag
0x1400661e7  nop     dword ptr [rax+rax+00h]
0x1400661ec  mov     qword ptr [rbx+6A0h], 0
0x1400661f7  mov     rcx, [rbx+0A40h]; struct _WFD_ROLE *
0x1400661fe  test    rcx, rcx
0x140066201  jz      short loc_140066213
0x140066203  call    ?WFDRoleDeInitialize@@YAXPEAU_WFD_ROLE@@@Z; WFDRoleDeInitialize(_WFD_ROLE *)
0x140066208  mov     qword ptr [rbx+0A40h], 0
0x140066213  mov     rcx, [rbx+718h]
0x14006621a  test    rcx, rcx
0x14006621d  jz      short loc_140066264
0x14006621f  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140066223  mov     qword ptr [rbx+720h], 0
0x14006622e  mov     rax, [rcx]
0x140066231  test    rax, rax
0x140066234  jz      short loc_14006624A
0x140066236  mov     rdx, rcx; Entry
0x140066239  mov     rcx, rax; Lookaside
0x14006623c  call    cs:__imp_ExFreeToNPagedLookasideList
0x140066243  nop     dword ptr [rax+rax+00h]
0x140066248  jmp     short loc_140066259
0x14006624a  mov     edx, [rcx+8]; Tag
0x14006624d  call    cs:__imp_ExFreePoolWithTag
0x140066254  nop     dword ptr [rax+rax+00h]
0x140066259  mov     qword ptr [rbx+718h], 0
0x140066264  add     rsp, 20h
0x140066268  pop     rbx
0x140066269  retn
```
