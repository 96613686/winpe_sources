# ScmCmMakeCall

- ea: `0x1400042e0`
- end: `0x14000474c`
- name: `ScmCmMakeCall`
- size: `1132`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140002bd8`
- `0x140002c08`
- `0x140002f88`
- `0x1400042e0`
- `0x140005f40`
- `0x140006240`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400043c5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000443d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400044c6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004551`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400045b6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400043c5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000443d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400044c6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004551`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400045b6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400043e4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004428`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004455`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400044de`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004569`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400045e3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000464b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400043e4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004428`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004455`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400044de`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004569`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400045e3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000464b`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x14000453a`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x14000453a`
- `NDIS!NdisQueueIoWorkItem` at `0x1400046a3`
- `NDIS!NdisQueueIoWorkItem` at `0x1400046ef`
- `NDIS!NdisQueueIoWorkItem` at `0x1400046a3`
- `NDIS!NdisQueueIoWorkItem` at `0x1400046ef`
- `NDIS!NdisAllocateIoWorkItem` at `0x1400044af`
- `NDIS!NdisAllocateIoWorkItem` at `0x1400044af`
- `NDIS!NdisFreeIoWorkItem` at `0x140004578`
- `NDIS!NdisFreeIoWorkItem` at `0x140004578`

## pseudocode

```c
__int64 __fastcall ScmCmMakeCall(__int64 a1, __int64 a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rcx
  struct _IRP *MasterIrp; // r12
  _DWORD *v7; // rbp
  KIRQL v8; // dl
  KSPIN_LOCK *v9; // rcx
  KIRQL v10; // al
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  NDIS_HANDLE IoWorkItem; // r15
  KIRQL v14; // al
  PIRP v15; // r14
  KIRQL v16; // al
  KIRQL v17; // al
  KIRQL v18; // r13
  char *v19; // rcx
  bool v20; // zf

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x81) == 0x81 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids);
  if ( (*(_DWORD *)a2 & 0x19) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids);
    }
    v4 = -1073741637;
    goto LABEL_48;
  }
  if ( (*(_DWORD *)a2 & 2) != 0
    || (v5 = *(_QWORD *)(a2 + 16), MasterIrp = 0, !v5)
    || *(_DWORD *)(v5 + 20) < 0x30u
    || *(_WORD *)(v5 + 56) < 0xB4u
    || (v7 = (_DWORD *)(v5 + *(_QWORD *)(v5 + 64) + 56LL), (v7[4] & 0xFFFFFEEF) != 0) )
  {
    v4 = -1073676267;
    goto LABEL_48;
  }
  v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 32));
  if ( *(_QWORD *)(a1 + 21048) )
  {
    v9 = (KSPIN_LOCK *)(a1 + 32);
    v4 = 65543;
    KeReleaseSpinLock(v9, v8);
    goto LABEL_48;
  }
  *(_QWORD *)(a1 + 21048) = a2;
  if ( v7[26] <= 0x2000u && (*(_DWORD *)((char *)v7 + (unsigned int)v7[27] + 48) & 1) != 0 )
    *(_BYTE *)(a1 + 21132) = 1;
  *(_DWORD *)(a1 + 21088) |= 0x41u;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 32), v8);
  if ( v7[26] > 0x2000u )
  {
    v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 32));
    *(_QWORD *)(a1 + 21048) = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 32), v10);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_26;
    }
    v12 = 34;
LABEL_25:
    WPP_SF__guid_(v11->AttachedDevice, v12, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids, a1 + 484);
LABEL_26:
    v4 = -1073741670;
    goto LABEL_48;
  }
  IoWorkItem = NdisAllocateIoWorkItem(*((NDIS_HANDLE *)SstpGlobals + 21));
  if ( !IoWorkItem )
  {
    v14 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 32));
    *(_QWORD *)(a1 + 21048) = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 32), v14);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids);
    }
    goto LABEL_26;
  }
  v15 = 0;
  if ( !*(_BYTE *)(a1 + 21132) )
  {
    v15 = IoCsqRemoveNextIrp((PIO_CSQ)SstpGlobals + 1, 0);
    if ( !v15 )
    {
      v16 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 32));
      *(_QWORD *)(a1 + 21048) = 0;
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 32), v16);
      NdisFreeIoWorkItem(IoWorkItem);
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_26;
      }
      v12 = 36;
      goto LABEL_25;
    }
  }
  v17 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 32));
  *(_DWORD *)(a1 + 21088) |= 0x4000u;
  v18 = v17;
  if ( !*(_BYTE *)(a1 + 21132) )
  {
    *(_DWORD *)(a1 + 21088) |= 0x2000u;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 32), v17);
    MasterIrp = v15->AssociatedIrp.MasterIrp;
    memset(&MasterIrp->Size + 1, 0, 0x200Cu);
    *(_DWORD *)&MasterIrp->Type = 4;
    *(_DWORD *)(&MasterIrp->Size + 1) = *(_DWORD *)(a1 + 112);
  }
  v19 = (char *)v7 + (unsigned int)v7[27];
  v20 = *(_BYTE *)(a1 + 21132) == 0;
  *(_QWORD *)(a1 + 21120) = v19;
  if ( v20 )
  {
    v4 = 259;
    memmove(&MasterIrp->Flags, (char *)v7 + (unsigned int)v7[27], (unsigned int)v7[26]);
    HIDWORD(MasterIrp->MdlAddress) = v7[26];
    v15->IoStatus.Status = 0;
    v15->IoStatus.Information = 8208;
    NdisQueueIoWorkItem(IoWorkItem, (NDIS_IO_WORKITEM_ROUTINE)ScmCmCompleteIrpPassive, v15);
  }
  else
  {
    memmove((void *)(a1 + 484), &v19[*((unsigned int *)v19 + 8)], *((unsigned int *)v19 + 9));
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 32), v18);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF__guid_(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids, a1 + 484);
    }
    v4 = 0;
    NdisQueueIoWorkItem(IoWorkItem, (NDIS_IO_WORKITEM_ROUTINE)ScmCmCompleteIrpPassive, 0);
  }
LABEL_48:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x81) == 0x81 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids);
  return v4;
}

```

## disassembly

```asm
0x1400042e0  push    rbx
0x1400042e2  push    rbp
0x1400042e3  push    rsi
0x1400042e4  push    rdi
0x1400042e5  push    r12
0x1400042e7  push    r13
0x1400042e9  push    r14
0x1400042eb  push    r15
0x1400042ed  sub     rsp, 28h
0x1400042f1  mov     rdi, rdx
0x1400042f4  mov     rbx, rcx
0x1400042f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400042fe  lea     r13, WPP_GLOBAL_Control
0x140004305  cmp     rcx, r13
0x140004308  jz      short loc_14000432B
0x14000430a  mov     eax, [rcx+2Ch]
0x14000430d  and     eax, 81h
0x140004312  cmp     al, 81h
0x140004314  jnz     short loc_14000432B
0x140004316  mov     rcx, [rcx+18h]
0x14000431a  lea     r8, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids
0x140004321  mov     edx, 20h ; ' '
0x140004326  call    WPP_SF_
0x14000432b  mov     r8d, [rdi]
0x14000432e  test    r8b, 19h
0x140004332  jz      short loc_140004373
0x140004334  mov     rcx, cs:WPP_GLOBAL_Control
0x14000433b  cmp     rcx, r13
0x14000433e  jz      short loc_140004369
0x140004340  mov     eax, [rcx+2Ch]
0x140004343  mov     dil, 1
0x140004346  test    dil, al
0x140004349  jz      short loc_140004369
0x14000434b  cmp     [rcx+29h], dil
0x14000434f  jb      short loc_140004369
0x140004351  mov     rcx, [rcx+18h]
0x140004355  mov     r9d, r8d
0x140004358  lea     r8, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids
0x14000435f  mov     edx, 21h ; '!'
0x140004364  call    WPP_SF_d
0x140004369  mov     ebx, 0C00000BBh
0x14000436e  jmp     loc_140004709
0x140004373  test    r8b, 2
0x140004377  jnz     loc_140004704
0x14000437d  mov     rcx, [rdi+10h]
0x140004381  xor     r12d, r12d
0x140004384  test    rcx, rcx
0x140004387  jz      loc_140004704
0x14000438d  cmp     dword ptr [rcx+14h], 30h ; '0'
0x140004391  jb      loc_140004704
0x140004397  mov     eax, 0B4h
0x14000439c  cmp     [rcx+38h], ax
0x1400043a0  jb      loc_140004704
0x1400043a6  mov     rbp, [rcx+40h]
0x1400043aa  add     rbp, 38h ; '8'
0x1400043ae  add     rbp, rcx
0x1400043b1  test    dword ptr [rbp+10h], 0FFFFFEEFh
0x1400043b8  jnz     loc_140004704
0x1400043be  lea     rsi, [rbx+20h]
0x1400043c2  mov     rcx, rsi; SpinLock
0x1400043c5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400043cc  nop     dword ptr [rax+rax+00h]
0x1400043d1  mov     dl, al; NewIrql
0x1400043d3  cmp     [rbx+5238h], r12
0x1400043da  jz      short loc_1400043F5
0x1400043dc  mov     rcx, rsi; SpinLock
0x1400043df  mov     ebx, 10007h
0x1400043e4  call    cs:__imp_KeReleaseSpinLock
0x1400043eb  nop     dword ptr [rax+rax+00h]
0x1400043f0  jmp     loc_140004709
0x1400043f5  mov     [rbx+5238h], rdi
0x1400043fc  mov     r14d, 2000h
0x140004402  mov     dil, 1
0x140004405  cmp     [rbp+68h], r14d
0x140004409  ja      short loc_14000441E
0x14000440b  mov     eax, [rbp+6Ch]
0x14000440e  mov     ecx, [rax+rbp+30h]
0x140004412  test    dil, cl
0x140004415  jz      short loc_14000441E
0x140004417  mov     [rbx+528Ch], dil
0x14000441e  or      dword ptr [rbx+5260h], 41h
0x140004425  mov     rcx, rsi; SpinLock
0x140004428  call    cs:__imp_KeReleaseSpinLock
0x14000442f  nop     dword ptr [rax+rax+00h]
0x140004434  cmp     [rbp+68h], r14d
0x140004438  jbe     short loc_1400044A1
0x14000443a  mov     rcx, rsi; SpinLock
0x14000443d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004444  nop     dword ptr [rax+rax+00h]
0x140004449  mov     rcx, rsi; SpinLock
0x14000444c  mov     [rbx+5238h], r12
0x140004453  mov     dl, al; NewIrql
0x140004455  call    cs:__imp_KeReleaseSpinLock
0x14000445c  nop     dword ptr [rax+rax+00h]
0x140004461  mov     rcx, cs:WPP_GLOBAL_Control
0x140004468  cmp     rcx, r13
0x14000446b  jz      short loc_140004497
0x14000446d  mov     eax, [rcx+2Ch]
0x140004470  test    dil, al
0x140004473  jz      short loc_140004497
0x140004475  cmp     [rcx+29h], dil
0x140004479  jb      short loc_140004497
0x14000447b  mov     edx, 22h ; '"'
0x140004480  mov     rcx, [rcx+18h]
0x140004484  lea     r9, [rbx+1E4h]
0x14000448b  lea     r8, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids
0x140004492  call    WPP_SF__guid_
0x140004497  mov     ebx, 0C000009Ah
0x14000449c  jmp     loc_140004709
0x1400044a1  mov     rcx, cs:SstpGlobals
0x1400044a8  mov     rcx, [rcx+0A8h]; NdisObjectHandle
0x1400044af  call    cs:__imp_NdisAllocateIoWorkItem
0x1400044b6  nop     dword ptr [rax+rax+00h]
0x1400044bb  mov     r15, rax
0x1400044be  test    rax, rax
0x1400044c1  jnz     short loc_14000451D
0x1400044c3  mov     rcx, rsi; SpinLock
0x1400044c6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400044cd  nop     dword ptr [rax+rax+00h]
0x1400044d2  mov     rcx, rsi; SpinLock
0x1400044d5  mov     [rbx+5238h], r12
0x1400044dc  mov     dl, al; NewIrql
0x1400044de  call    cs:__imp_KeReleaseSpinLock
0x1400044e5  nop     dword ptr [rax+rax+00h]
0x1400044ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400044f1  cmp     rcx, r13
0x1400044f4  jz      short loc_140004497
0x1400044f6  mov     eax, [rcx+2Ch]
0x1400044f9  test    dil, al
0x1400044fc  jz      short loc_140004497
0x1400044fe  cmp     [rcx+29h], dil
0x140004502  jb      short loc_140004497
0x140004504  mov     rcx, [rcx+18h]
0x140004508  lea     edx, [r15+23h]
0x14000450c  lea     r8, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids
0x140004513  call    WPP_SF_
0x140004518  jmp     loc_140004497
0x14000451d  mov     r14, r12
0x140004520  cmp     [rbx+528Ch], r12b
0x140004527  jnz     loc_1400045B3
0x14000452d  mov     rcx, cs:SstpGlobals
0x140004534  xor     edx, edx; PeekContext
0x140004536  add     rcx, 40h ; '@'; Csq
0x14000453a  call    cs:__imp_IoCsqRemoveNextIrp
0x140004541  nop     dword ptr [rax+rax+00h]
0x140004546  mov     r14, rax
0x140004549  test    rax, rax
0x14000454c  jnz     short loc_1400045B3
0x14000454e  mov     rcx, rsi; SpinLock
0x140004551  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004558  nop     dword ptr [rax+rax+00h]
0x14000455d  mov     rcx, rsi; SpinLock
0x140004560  mov     [rbx+5238h], r12
0x140004567  mov     dl, al; NewIrql
0x140004569  call    cs:__imp_KeReleaseSpinLock
0x140004570  nop     dword ptr [rax+rax+00h]
0x140004575  mov     rcx, r15; NdisIoWorkItemHandle
0x140004578  call    cs:__imp_NdisFreeIoWorkItem
0x14000457f  nop     dword ptr [rax+rax+00h]
0x140004584  mov     rcx, cs:WPP_GLOBAL_Control
0x14000458b  cmp     rcx, r13
0x14000458e  jz      loc_140004497
0x140004594  mov     eax, [rcx+2Ch]
0x140004597  test    dil, al
0x14000459a  jz      loc_140004497
0x1400045a0  cmp     [rcx+29h], dil
0x1400045a4  jb      loc_140004497
0x1400045aa  lea     edx, [r14+24h]
0x1400045ae  jmp     loc_140004480
0x1400045b3  mov     rcx, rsi; SpinLock
0x1400045b6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400045bd  nop     dword ptr [rax+rax+00h]
0x1400045c2  bts     dword ptr [rbx+5260h], 0Eh
0x1400045ca  mov     r13b, al
0x1400045cd  cmp     [rbx+528Ch], r12b
0x1400045d4  jnz     short loc_140004615
0x1400045d6  bts     dword ptr [rbx+5260h], 0Dh
0x1400045de  mov     dl, al; NewIrql
0x1400045e0  mov     rcx, rsi; SpinLock
0x1400045e3  call    cs:__imp_KeReleaseSpinLock
0x1400045ea  nop     dword ptr [rax+rax+00h]
0x1400045ef  mov     r12, [r14+18h]
0x1400045f3  xor     edx, edx; Val
0x1400045f5  mov     r8d, 200Ch; Size
0x1400045fb  lea     rcx, [r12+4]; void *
0x140004600  call    memset
0x140004605  mov     dword ptr [r12], 4
0x14000460d  mov     eax, [rbx+70h]
0x140004610  mov     [r12+4], eax
0x140004615  mov     ecx, [rbp+6Ch]
0x140004618  add     rcx, rbp
0x14000461b  cmp     byte ptr [rbx+528Ch], 0
0x140004622  mov     [rbx+5280h], rcx
0x140004629  jz      loc_1400046B1
0x14000462f  mov     edx, [rcx+20h]
0x140004632  mov     r8d, [rcx+24h]; Size
0x140004636  add     rdx, rcx; Src
0x140004639  lea     rcx, [rbx+1E4h]; void *
0x140004640  call    memmove
0x140004645  mov     dl, r13b; NewIrql
0x140004648  mov     rcx, rsi; SpinLock
0x14000464b  call    cs:__imp_KeReleaseSpinLock
0x140004652  nop     dword ptr [rax+rax+00h]
0x140004657  mov     rcx, cs:WPP_GLOBAL_Control
0x14000465e  lea     r13, WPP_GLOBAL_Control
0x140004665  cmp     rcx, r13
0x140004668  jz      short loc_140004694
0x14000466a  mov     eax, [rcx+2Ch]
0x14000466d  test    dil, al
0x140004670  jz      short loc_140004694
0x140004672  cmp     byte ptr [rcx+29h], 3
0x140004676  jb      short loc_140004694
0x140004678  mov     rcx, [rcx+18h]
0x14000467c  lea     r9, [rbx+1E4h]
0x140004683  mov     edx, 25h ; '%'
0x140004688  lea     r8, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids
0x14000468f  call    WPP_SF__guid_
0x140004694  xor     ebx, ebx
0x140004696  lea     rdx, ScmCmCompleteIrpPassive; Routine
0x14000469d  xor     r8d, r8d; WorkItemContext
0x1400046a0  mov     rcx, r15; NdisIoWorkItemHandle
0x1400046a3  call    cs:__imp_NdisQueueIoWorkItem
0x1400046aa  nop     dword ptr [rax+rax+00h]
0x1400046af  jmp     short loc_140004709
0x1400046b1  mov     edx, [rbp+6Ch]
0x1400046b4  lea     rcx, [r12+10h]; void *
0x1400046b9  mov     r8d, [rbp+68h]; Size
0x1400046bd  add     rdx, rbp; Src
0x1400046c0  mov     ebx, 103h
0x1400046c5  call    memmove
0x1400046ca  mov     eax, [rbp+68h]
0x1400046cd  lea     rdx, ScmCmCompleteIrpPassive; Routine
0x1400046d4  mov     [r12+0Ch], eax
0x1400046d9  mov     r8, r14; WorkItemContext
0x1400046dc  mov     rcx, r15; NdisIoWorkItemHandle
0x1400046df  mov     dword ptr [r14+30h], 0
0x1400046e7  mov     qword ptr [r14+38h], 2010h
0x1400046ef  call    cs:__imp_NdisQueueIoWorkItem
0x1400046f6  nop     dword ptr [rax+rax+00h]
0x1400046fb  lea     r13, WPP_GLOBAL_Control
0x140004702  jmp     short loc_140004709
0x140004704  mov     ebx, 0C0010015h
0x140004709  mov     rcx, cs:WPP_GLOBAL_Control
0x140004710  cmp     rcx, r13
0x140004713  jz      short loc_140004738
0x140004715  mov     edx, [rcx+2Ch]
0x140004718  and     edx, 81h
0x14000471e  cmp     dl, 81h
0x140004721  jnz     short loc_140004738
0x140004723  mov     rcx, [rcx+18h]
0x140004727  lea     r8, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids
0x14000472e  mov     edx, 26h ; '&'
0x140004733  call    WPP_SF_
0x140004738  mov     eax, ebx
0x14000473a  add     rsp, 28h
0x14000473e  pop     r15
0x140004740  pop     r14
0x140004742  pop     r13
0x140004744  pop     r12
0x140004746  pop     rdi
0x140004747  pop     rsi
0x140004748  pop     rbp
0x140004749  pop     rbx
0x14000474a  retn
```
