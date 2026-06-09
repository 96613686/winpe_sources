# RefsForcePurgeCacheAndCloseSection

- ea: `0x1c00a1320`
- end: `0x1c00a1634`
- name: `RefsForcePurgeCacheAndCloseSection`
- size: `788`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x1c00a5970`
- `0x1c00a652c`

## callees

- `0x1c0004300`
- `0x1c00043a8`
- `0x1c000f770`
- `0x1c003c2b8`
- `0x1c0064454`
- `0x1c0068168`
- `0x1c00a1320`
- `0x1c01632d4`

## import_xrefs

- `ntoskrnl!CcPurgeCacheSection` at `0x1c00a1382`
- `ntoskrnl!CcPurgeCacheSection` at `0x1c00a1382`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1c00a1618`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1c00a1618`
- `ntoskrnl!MmFlushImageSection` at `0x1c00a135a`
- `ntoskrnl!MmFlushImageSection` at `0x1c00a135a`
- `ntoskrnl!MmForceSectionClosed` at `0x1c00a155d`
- `ntoskrnl!MmForceSectionClosed` at `0x1c00a157d`
- `ntoskrnl!MmForceSectionClosed` at `0x1c00a155d`
- `ntoskrnl!MmForceSectionClosed` at `0x1c00a157d`

## pseudocode

```c
__int64 __fastcall RefsForcePurgeCacheAndCloseSection(__int64 a1, __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // r15
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 v8; // rax
  BOOL v9; // eax
  int Status; // [rsp+30h] [rbp-28h]
  char v12; // [rsp+70h] [rbp+18h] BYREF

  Status = 0;
  v4 = *(_QWORD *)(a2 + 240);
  v5 = *(_QWORD *)(v4 + 8);
  if ( *(_QWORD *)(v4 + 24) )
    MmFlushImageSection((PSECTION_OBJECT_POINTERS)(v4 + 8), MmFlushForWrite);
  if ( v5 && !CcPurgeCacheSection((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(a2 + 240) + 8LL), 0, 0, 0) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_e0cd40d9014935e250daf1cae00b3533_Traceguids, 3221225499LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741797);
    Status = -1073741797;
  }
  if ( (unsigned __int16)(*(_WORD *)a2 - 2051) <= 1u )
  {
    if ( !*(_QWORD *)(a2 + 384) )
      goto LABEL_22;
    v12 = 0;
    RefsBindMinstoreTransaction(a1);
    Status = MsUpdateTree(*(_QWORD *)(a1 + 24), *(_QWORD *)(a2 + 384), 2, 0, (__int64)&v12);
    v7 = *(_QWORD *)(a2 + 384);
  }
  else
  {
    RefsBindMinstoreTransaction(a1);
    v6 = *(_QWORD *)(*(_QWORD *)(a2 + 120) + 240LL);
    if ( v6 )
      Status = MsUpdateTree(*(_QWORD *)(a1 + 24), v6, 2, 0, 0);
    if ( *(_QWORD *)(a2 + 360) )
      Status = MsFlushStream(*(CmsTransactionContext **)(a1 + 24));
    v7 = *(_QWORD *)(*(_QWORD *)(a2 + 120) + 240LL);
  }
  if ( v7 )
    MsUninitializeCachingTableObject(*(_QWORD *)(a1 + 24));
LABEL_22:
  RefsCheckpointCurrentTransaction(a1);
  v8 = *(_QWORD *)(a2 + 240);
  if ( *(_QWORD *)(v8 + 8) )
  {
    MmForceSectionClosed((PSECTION_OBJECT_POINTERS)(v8 + 8), 1u);
    v8 = *(_QWORD *)(a2 + 240);
  }
  if ( *(_QWORD *)(v8 + 32) )
    MmForceSectionClosed((PSECTION_OBJECT_POINTERS)(v8 + 32), 1u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
  {
    if ( Status < 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
LABEL_33:
        WPP_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          25,
          WPP_e0cd40d9014935e250daf1cae00b3533_Traceguids,
          (unsigned int)Status);
        goto LABEL_34;
      }
      v9 = 0;
    }
    else
    {
      v9 = BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
    }
    if ( !v9 )
      goto LABEL_34;
    goto LABEL_33;
  }
LABEL_34:
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(Status);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1c00a1320  mov     [rsp+arg_0], rsi
0x1c00a1325  mov     [rsp+arg_8], rdx
0x1c00a132a  push    rdi
0x1c00a132b  push    r14
0x1c00a132d  push    r15
0x1c00a132f  sub     rsp, 40h
0x1c00a1333  mov     rdi, rdx
0x1c00a1336  mov     r14, rcx
0x1c00a1339  and     [rsp+58h+Status], 0
0x1c00a133e  mov     rax, [rdx+0F0h]
0x1c00a1345  lea     rcx, [rax+8]; SectionObjectPointer
0x1c00a1349  mov     r15, [rcx]
0x1c00a134c  mov     esi, 1
0x1c00a1351  cmp     qword ptr [rax+18h], 0
0x1c00a1356  jz      short loc_1C00A1366
0x1c00a1358  mov     edx, esi; FlushType
0x1c00a135a  call    cs:__imp_MmFlushImageSection
0x1c00a1361  nop     dword ptr [rax+rax+00h]
0x1c00a1366  test    r15, r15
0x1c00a1369  jz      loc_1C00A13FA
0x1c00a136f  mov     rcx, [rdi+0F0h]
0x1c00a1376  add     rcx, 8; SectionObjectPointer
0x1c00a137a  xor     r9d, r9d; Flags
0x1c00a137d  xor     r8d, r8d; Length
0x1c00a1380  xor     edx, edx; FileOffset
0x1c00a1382  call    cs:__imp_CcPurgeCacheSection
0x1c00a1389  nop     dword ptr [rax+rax+00h]
0x1c00a138e  test    al, al
0x1c00a1390  jnz     short loc_1C00A13FA
0x1c00a1392  lea     r15, WPP_GLOBAL_Control
0x1c00a1399  mov     rcx, cs:WPP_GLOBAL_Control
0x1c00a13a0  cmp     rcx, r15
0x1c00a13a3  jz      short loc_1C00A13CF
0x1c00a13a5  test    dword ptr [rcx+2Ch], 100h
0x1c00a13ac  jz      short loc_1C00A13CF
0x1c00a13ae  cmp     byte ptr [rcx+29h], 4
0x1c00a13b2  jb      short loc_1C00A13CF
0x1c00a13b4  mov     edx, 17h
0x1c00a13b9  mov     r9d, 0C000001Bh
0x1c00a13bf  lea     r8, WPP_e0cd40d9014935e250daf1cae00b3533_Traceguids
0x1c00a13c6  mov     rcx, [rcx+18h]
0x1c00a13ca  call    WPP_SF_D
0x1c00a13cf  mov     al, cs:RefsStatusDebugEnabled
0x1c00a13d5  test    al, al
0x1c00a13d7  jz      short loc_1C00A13F0
0x1c00a13d9  mov     r8d, 2B1h
0x1c00a13df  lea     rdx, aSelfhealC; "SelfHeal.c"
0x1c00a13e6  mov     ecx, 0C000001Bh; Status
0x1c00a13eb  call    RefsStatusDebug
0x1c00a13f0  mov     [rsp+58h+Status], 0C000001Bh
0x1c00a13f8  jmp     short loc_1C00A1401
0x1c00a13fa  lea     r15, WPP_GLOBAL_Control
0x1c00a1401  mov     ecx, 803h
0x1c00a1406  movzx   eax, word ptr [rdi]
0x1c00a1409  sub     ax, cx
0x1c00a140c  cmp     ax, si
0x1c00a140f  jbe     short loc_1C00A1470
0x1c00a1411  mov     rcx, r14
0x1c00a1414  call    RefsBindMinstoreTransaction
0x1c00a1419  mov     rax, [rdi+78h]
0x1c00a141d  mov     rdx, [rax+0F0h]
0x1c00a1424  test    rdx, rdx
0x1c00a1427  jz      short loc_1C00A1443
0x1c00a1429  and     [rsp+58h+var_38], 0
0x1c00a142f  xor     r9d, r9d
0x1c00a1432  lea     r8d, [r9+2]
0x1c00a1436  mov     rcx, [r14+18h]
0x1c00a143a  call    MsUpdateTree
0x1c00a143f  mov     [rsp+58h+Status], eax
0x1c00a1443  mov     rdx, [rdi+168h]
0x1c00a144a  test    rdx, rdx
0x1c00a144d  jz      short loc_1C00A1463
0x1c00a144f  xor     r9d, r9d
0x1c00a1452  lea     r8d, [r9+2]
0x1c00a1456  mov     rcx, [r14+18h]; this
0x1c00a145a  call    MsFlushStream
0x1c00a145f  mov     [rsp+58h+Status], eax
0x1c00a1463  mov     rax, [rdi+78h]
0x1c00a1467  mov     rdx, [rax+0F0h]
0x1c00a146e  jmp     short loc_1C00A14B5
0x1c00a1470  mov     rdx, [rdi+180h]
0x1c00a1477  test    rdx, rdx
0x1c00a147a  jz      short loc_1C00A14C3
0x1c00a147c  mov     [rsp+58h+arg_10], 0
0x1c00a1481  mov     rcx, r14
0x1c00a1484  call    RefsBindMinstoreTransaction
0x1c00a1489  lea     rax, [rsp+58h+arg_10]
0x1c00a148e  mov     [rsp+58h+var_38], rax
0x1c00a1493  xor     r9d, r9d
0x1c00a1496  lea     r8d, [r9+2]
0x1c00a149a  mov     rdx, [rdi+180h]
0x1c00a14a1  mov     rcx, [r14+18h]
0x1c00a14a5  call    MsUpdateTree
0x1c00a14aa  mov     [rsp+58h+Status], eax
0x1c00a14ae  mov     rdx, [rdi+180h]
0x1c00a14b5  test    rdx, rdx
0x1c00a14b8  jz      short loc_1C00A14C3
0x1c00a14ba  mov     rcx, [r14+18h]
0x1c00a14be  call    MsUninitializeCachingTableObject
0x1c00a14c3  mov     rcx, r14
0x1c00a14c6  call    RefsCheckpointCurrentTransaction
0x1c00a14cb  jmp     short loc_1C00A1549
0x1c00a14cd  mov     r9d, eax
0x1c00a14d0  mov     [rsp+58h+Status], eax
0x1c00a14d4  lea     rax, WPP_GLOBAL_Control
0x1c00a14db  mov     rcx, cs:WPP_GLOBAL_Control
0x1c00a14e2  cmp     rcx, rax
0x1c00a14e5  jz      short loc_1C00A1518
0x1c00a14e7  test    dword ptr [rcx+2Ch], 100h
0x1c00a14ee  jz      short loc_1C00A1518
0x1c00a14f0  test    r9d, r9d
0x1c00a14f3  js      short loc_1C00A14FD
0x1c00a14f5  cmp     byte ptr [rcx+29h], 5
0x1c00a14f9  jnb     short loc_1C00A1503
0x1c00a14fb  jmp     short loc_1C00A1518
0x1c00a14fd  cmp     byte ptr [rcx+29h], 4
0x1c00a1501  jb      short loc_1C00A1518
0x1c00a1503  mov     edx, 18h
0x1c00a1508  lea     r8, WPP_e0cd40d9014935e250daf1cae00b3533_Traceguids
0x1c00a150f  mov     rcx, [rcx+18h]
0x1c00a1513  call    WPP_SF_D
0x1c00a1518  mov     al, cs:RefsStatusDebugEnabled
0x1c00a151e  test    al, al
0x1c00a1520  jz      short loc_1C00A1538
0x1c00a1522  mov     r8d, 2FCh
0x1c00a1528  lea     rdx, aSelfhealC; "SelfHeal.c"
0x1c00a152f  mov     ecx, [rsp+58h+Status]; Status
0x1c00a1533  call    RefsStatusDebug
0x1c00a1538  mov     esi, 1
0x1c00a153d  lea     r15, WPP_GLOBAL_Control
0x1c00a1544  mov     rdi, [rsp+58h+arg_8]
0x1c00a1549  mov     rax, [rdi+0F0h]
0x1c00a1550  lea     rcx, [rax+8]; SectionObjectPointer
0x1c00a1554  cmp     qword ptr [rcx], 0
0x1c00a1558  jz      short loc_1C00A1570
0x1c00a155a  mov     dl, sil; DelayClose
0x1c00a155d  call    cs:__imp_MmForceSectionClosed
0x1c00a1564  nop     dword ptr [rax+rax+00h]
0x1c00a1569  mov     rax, [rdi+0F0h]
0x1c00a1570  lea     rcx, [rax+20h]; SectionObjectPointer
0x1c00a1574  cmp     qword ptr [rcx], 0
0x1c00a1578  jz      short loc_1C00A1589
0x1c00a157a  mov     dl, sil; DelayClose
0x1c00a157d  call    cs:__imp_MmForceSectionClosed
0x1c00a1584  nop     dword ptr [rax+rax+00h]
0x1c00a1589  mov     rcx, cs:WPP_GLOBAL_Control
0x1c00a1590  cmp     rcx, r15
0x1c00a1593  jz      short loc_1C00A15D6
0x1c00a1595  test    dword ptr [rcx+2Ch], 100h
0x1c00a159c  jz      short loc_1C00A15D6
0x1c00a159e  cmp     [rsp+58h+Status], 0
0x1c00a15a3  jl      short loc_1C00A15B0
0x1c00a15a5  xor     eax, eax
0x1c00a15a7  cmp     byte ptr [rcx+29h], 5
0x1c00a15ab  setnb   al
0x1c00a15ae  jmp     short loc_1C00A15B8
0x1c00a15b0  cmp     byte ptr [rcx+29h], 4
0x1c00a15b4  jnb     short loc_1C00A15BC
0x1c00a15b6  xor     eax, eax
0x1c00a15b8  test    eax, eax
0x1c00a15ba  jz      short loc_1C00A15D6
0x1c00a15bc  mov     edx, 19h
0x1c00a15c1  mov     r9d, [rsp+58h+Status]
0x1c00a15c6  lea     r8, WPP_e0cd40d9014935e250daf1cae00b3533_Traceguids
0x1c00a15cd  mov     rcx, [rcx+18h]
0x1c00a15d1  call    WPP_SF_D
0x1c00a15d6  mov     al, cs:RefsStatusDebugEnabled
0x1c00a15dc  test    al, al
0x1c00a15de  jz      short loc_1C00A15F6
0x1c00a15e0  mov     r8d, 310h
0x1c00a15e6  lea     rdx, aSelfhealC; "SelfHeal.c"
0x1c00a15ed  mov     ecx, [rsp+58h+Status]; Status
0x1c00a15f1  call    RefsStatusDebug
0x1c00a15f6  mov     eax, [rsp+58h+Status]
0x1c00a15fa  mov     rsi, [rsp+58h+arg_0]
0x1c00a15ff  add     rsp, 40h
0x1c00a1603  pop     r15
0x1c00a1605  pop     r14
0x1c00a1607  pop     rdi
0x1c00a1608  retn
0x1c00a160a  push    rbp
0x1c00a160c  sub     rsp, 30h
0x1c00a1610  mov     rbp, rdx
0x1c00a1613  mov     rax, [rcx]
0x1c00a1616  mov     ecx, [rax]; Exception
0x1c00a1618  call    cs:__imp_FsRtlIsNtstatusExpected
0x1c00a161f  nop     dword ptr [rax+rax+00h]
0x1c00a1624  xor     ecx, ecx
0x1c00a1626  test    al, al
0x1c00a1628  setnz   cl
0x1c00a162b  mov     eax, ecx
0x1c00a162d  add     rsp, 30h
0x1c00a1631  pop     rbp
0x1c00a1632  retn
```
