# TpiDispatchCleanup

- ea: `0x1400031f0`
- end: `0x1400034c6`
- name: `TpiDispatchCleanup`
- size: `726`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400018b0`
- `0x1400031f0`
- `0x140005110`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000324c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003339`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000341d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000324c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003339`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000341d`
- `ntoskrnl!IofCompleteRequest` at `0x140003308`
- `ntoskrnl!IofCompleteRequest` at `0x14000349f`
- `ntoskrnl!IofCompleteRequest` at `0x140003308`
- `ntoskrnl!IofCompleteRequest` at `0x14000349f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000328a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003486`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000328a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003486`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000336e`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000336e`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x14000331a`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x14000331a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000338f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400033d9`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000338f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400033d9`
- `NDIS!NdisFreeNetBufferListPool` at `0x14000345b`
- `NDIS!NdisFreeNetBufferListPool` at `0x14000345b`
- `NDIS!NdisCmRegisterSapComplete` at `0x1400032d4`
- `NDIS!NdisCmRegisterSapComplete` at `0x1400032d4`
- `NDIS!NdisCmDeregisterSapComplete` at `0x1400032b0`
- `NDIS!NdisCmDeregisterSapComplete` at `0x1400032b0`

## pseudocode

```c
__int64 __fastcall TpiDispatchCleanup(__int64 a1, IRP *a2)
{
  PFILE_OBJECT FileObject; // r14
  struct _FILE_OBJECT *v4; // r12
  KIRQL v5; // al
  int v6; // ebx
  int v7; // ebx
  struct _IO_CSQ *v8; // rbx
  PIRP v9; // rax
  KIRQL v10; // al
  NDIS_HANDLE *v11; // rdx
  KIRQL v12; // r13
  char *v13; // rbx
  _BYTE *v14; // rsi
  KSPIN_LOCK v15; // rax
  void **v16; // rcx
  __int64 v17; // r8
  char *v19; // [rsp+78h] [rbp+10h]

  FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  v4 = (struct _FILE_OBJECT *)*((_QWORD *)SstpGlobals + 3);
  if ( FileObject != *((PFILE_OBJECT *)SstpGlobals + 2) && FileObject != v4 )
    goto LABEL_28;
  if ( FileObject != v4 )
  {
    *((_QWORD *)SstpGlobals + 2) = 0;
    v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SstpGlobals + 55);
    v6 = *((_DWORD *)SstpGlobals + 112);
    *((_DWORD *)SstpGlobals + 112) = 0;
    *((_BYTE *)SstpGlobals + 568) = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)SstpGlobals + 55, v5);
    v7 = v6 - 1;
    if ( v7 )
    {
      if ( v7 != 1 )
        goto LABEL_10;
      NdisCmDeregisterSapComplete(0, *((NDIS_HANDLE *)SstpGlobals + 57));
    }
    else
    {
      NdisCmRegisterSapComplete(-1073676286, *((NDIS_HANDLE *)SstpGlobals + 57), 0);
    }
    *((_QWORD *)SstpGlobals + 57) = 0;
LABEL_10:
    DeregisterTPIFromFsm();
    v8 = (struct _IO_CSQ *)SstpGlobals;
    while ( 1 )
    {
      v9 = IoCsqRemoveNextIrp(v8 + 1, 0);
      if ( !v9 )
        break;
      v9->IoStatus.Status = -1073741536;
      IofCompleteRequest(v9, 0);
    }
    goto LABEL_13;
  }
  *((_QWORD *)SstpGlobals + 3) = 0;
LABEL_13:
  v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SstpGlobals + 59);
  v11 = (NDIS_HANDLE *)SstpGlobals;
  v12 = v10;
  v13 = (char *)*((_QWORD *)SstpGlobals + 60);
  if ( v13 != (char *)SstpGlobals + 480 )
  {
    do
    {
      v19 = *(char **)v13;
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)v13 + 2);
      v14 = v13 + 21116;
      if ( FileObject != v4 || *v14 )
      {
        v15 = *(_QWORD *)v13;
        if ( *(char **)(*(_QWORD *)v13 + 8LL) != v13 || (v16 = (void **)*((_QWORD *)v13 + 1), *v16 != v13) )
          __fastfail(3u);
        *v16 = (void *)v15;
        *(_QWORD *)(v15 + 8) = v16;
        *((_QWORD *)v13 + 1) = v13;
        *(_QWORD *)v13 = v13;
        KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)SstpGlobals + 59);
        if ( *v14 && v13[21076] )
          *((_DWORD *)v13 + 5268) &= ~0x200u;
        LOBYTE(v17) = v12;
        InitiateSstpContextCleanup((__int64)(v13 - 16), 4, v17);
        v12 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SstpGlobals + 59);
      }
      else
      {
        KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)v13 + 2);
      }
      v11 = (NDIS_HANDLE *)SstpGlobals;
      v13 = v19;
    }
    while ( v19 != (char *)SstpGlobals + 480 );
  }
  if ( !v11[2] && !v11[3] )
  {
    NdisFreeNetBufferListPool(v11[72]);
    *((_QWORD *)SstpGlobals + 72) = 0;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)SstpGlobals + 59, v12);
LABEL_28:
  a2->IoStatus.Status = 0;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  return 0;
}

```

## disassembly

```asm
0x1400031f0  push    rbx
0x1400031f2  push    rbp
0x1400031f3  push    rsi
0x1400031f4  push    rdi
0x1400031f5  push    r12
0x1400031f7  push    r13
0x1400031f9  push    r14
0x1400031fb  push    r15
0x1400031fd  sub     rsp, 28h
0x140003201  mov     rax, [rdx+0B8h]
0x140003208  xor     r15d, r15d
0x14000320b  mov     rbp, rdx
0x14000320e  mov     r14, [rax+30h]
0x140003212  mov     rax, cs:SstpGlobals
0x140003219  mov     r12, [rax+18h]
0x14000321d  cmp     r14, [rax+10h]
0x140003221  jz      short loc_14000322C
0x140003223  cmp     r14, r12
0x140003226  jnz     loc_140003492
0x14000322c  cmp     r14, r12
0x14000322f  jnz     short loc_14000323A
0x140003231  mov     [rax+18h], r15
0x140003235  jmp     loc_14000332B
0x14000323a  mov     [rax+10h], r15
0x14000323e  mov     rcx, cs:SstpGlobals
0x140003245  add     rcx, 1B8h; SpinLock
0x14000324c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003253  nop     dword ptr [rax+rax+00h]
0x140003258  mov     rcx, cs:SstpGlobals
0x14000325f  mov     dl, al; NewIrql
0x140003261  mov     ebx, [rcx+1C0h]
0x140003267  mov     [rcx+1C0h], r15d
0x14000326e  mov     rcx, cs:SstpGlobals
0x140003275  mov     [rcx+238h], r15b
0x14000327c  mov     rcx, cs:SstpGlobals
0x140003283  add     rcx, 1B8h; SpinLock
0x14000328a  call    cs:__imp_KeReleaseSpinLock
0x140003291  nop     dword ptr [rax+rax+00h]
0x140003296  sub     ebx, 1
0x140003299  jz      short loc_1400032BE
0x14000329b  cmp     ebx, 1
0x14000329e  jnz     short loc_1400032EE
0x1400032a0  mov     rdx, cs:SstpGlobals
0x1400032a7  xor     ecx, ecx; Status
0x1400032a9  mov     rdx, [rdx+1C8h]; NdisSapHandle
0x1400032b0  call    cs:__imp_NdisCmDeregisterSapComplete
0x1400032b7  nop     dword ptr [rax+rax+00h]
0x1400032bc  jmp     short loc_1400032E0
0x1400032be  mov     rdx, cs:SstpGlobals
0x1400032c5  xor     r8d, r8d; CallMgrSapContext
0x1400032c8  mov     ecx, 0C0010002h; Status
0x1400032cd  mov     rdx, [rdx+1C8h]; NdisSapHandle
0x1400032d4  call    cs:__imp_NdisCmRegisterSapComplete
0x1400032db  nop     dword ptr [rax+rax+00h]
0x1400032e0  mov     rax, cs:SstpGlobals
0x1400032e7  mov     [rax+1C8h], r15
0x1400032ee  call    DeregisterTPIFromFsm
0x1400032f3  mov     rbx, cs:SstpGlobals
0x1400032fa  jmp     short loc_140003314
0x1400032fc  xor     edx, edx; PriorityBoost
0x1400032fe  mov     dword ptr [rax+30h], 0C0000120h
0x140003305  mov     rcx, rax; Irp
0x140003308  call    cs:__imp_IofCompleteRequest
0x14000330f  nop     dword ptr [rax+rax+00h]
0x140003314  xor     edx, edx; PeekContext
0x140003316  lea     rcx, [rbx+40h]; Csq
0x14000331a  call    cs:__imp_IoCsqRemoveNextIrp
0x140003321  nop     dword ptr [rax+rax+00h]
0x140003326  test    rax, rax
0x140003329  jnz     short loc_1400032FC
0x14000332b  mov     rcx, cs:SstpGlobals
0x140003332  add     rcx, 1D8h; SpinLock
0x140003339  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003340  nop     dword ptr [rax+rax+00h]
0x140003345  mov     rdx, cs:SstpGlobals
0x14000334c  mov     r13b, al
0x14000334f  lea     rcx, [rdx+1E0h]
0x140003356  mov     rbx, [rcx]
0x140003359  cmp     rbx, rcx
0x14000335c  jz      loc_140003448
0x140003362  mov     rax, [rbx]
0x140003365  lea     rcx, [rbx+10h]; SpinLock
0x140003369  mov     [rsp+68h+arg_8], rax
0x14000336e  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140003375  nop     dword ptr [rax+rax+00h]
0x14000337a  lea     rsi, [rbx+527Ch]
0x140003381  cmp     r14, r12
0x140003384  jnz     short loc_1400033A3
0x140003386  cmp     byte ptr [rsi], 0
0x140003389  jnz     short loc_1400033A3
0x14000338b  lea     rcx, [rbx+10h]; SpinLock
0x14000338f  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140003396  nop     dword ptr [rax+rax+00h]
0x14000339b  xor     r15d, r15d
0x14000339e  jmp     loc_14000342C
0x1400033a3  mov     rax, [rbx]
0x1400033a6  cmp     [rax+8], rbx
0x1400033aa  jnz     loc_1400034BF
0x1400033b0  mov     rcx, [rbx+8]
0x1400033b4  cmp     [rcx], rbx
0x1400033b7  jnz     loc_1400034BF
0x1400033bd  mov     [rcx], rax
0x1400033c0  mov     [rax+8], rcx
0x1400033c4  mov     [rbx+8], rbx
0x1400033c8  mov     [rbx], rbx
0x1400033cb  mov     rcx, cs:SstpGlobals
0x1400033d2  add     rcx, 1D8h; SpinLock
0x1400033d9  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400033e0  nop     dword ptr [rax+rax+00h]
0x1400033e5  xor     r15d, r15d
0x1400033e8  cmp     [rsi], r15b
0x1400033eb  jz      short loc_1400033FE
0x1400033ed  cmp     [rbx+5254h], r15b
0x1400033f4  jz      short loc_1400033FE
0x1400033f6  btr     dword ptr [rbx+5250h], 9
0x1400033fe  mov     r8b, r13b
0x140003401  lea     rcx, [rbx-10h]
0x140003405  mov     edx, 4
0x14000340a  call    InitiateSstpContextCleanup
0x14000340f  mov     rcx, cs:SstpGlobals
0x140003416  add     rcx, 1D8h; SpinLock
0x14000341d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003424  nop     dword ptr [rax+rax+00h]
0x140003429  mov     r13b, al
0x14000342c  mov     rdx, cs:SstpGlobals
0x140003433  mov     rbx, [rsp+68h+arg_8]
0x140003438  lea     rax, [rdx+1E0h]
0x14000343f  cmp     rbx, rax
0x140003442  jnz     loc_140003362
0x140003448  cmp     [rdx+10h], r15
0x14000344c  jnz     short loc_140003475
0x14000344e  cmp     [rdx+18h], r15
0x140003452  jnz     short loc_140003475
0x140003454  mov     rcx, [rdx+240h]; PoolHandle
0x14000345b  call    cs:__imp_NdisFreeNetBufferListPool
0x140003462  nop     dword ptr [rax+rax+00h]
0x140003467  mov     rax, cs:SstpGlobals
0x14000346e  mov     [rax+240h], r15
0x140003475  mov     rcx, cs:SstpGlobals
0x14000347c  mov     dl, r13b; NewIrql
0x14000347f  add     rcx, 1D8h; SpinLock
0x140003486  call    cs:__imp_KeReleaseSpinLock
0x14000348d  nop     dword ptr [rax+rax+00h]
0x140003492  xor     edx, edx; PriorityBoost
0x140003494  mov     [rbp+30h], r15d
0x140003498  mov     rcx, rbp; Irp
0x14000349b  mov     [rbp+38h], r15
0x14000349f  call    cs:__imp_IofCompleteRequest
0x1400034a6  nop     dword ptr [rax+rax+00h]
0x1400034ab  xor     eax, eax
0x1400034ad  add     rsp, 28h
0x1400034b1  pop     r15
0x1400034b3  pop     r14
0x1400034b5  pop     r13
0x1400034b7  pop     r12
0x1400034b9  pop     rdi
0x1400034ba  pop     rsi
0x1400034bb  pop     rbp
0x1400034bc  pop     rbx
0x1400034bd  retn
0x1400034bf  mov     ecx, 3
0x1400034c4  int     29h; Win8: RtlFailFast(ecx)
```
