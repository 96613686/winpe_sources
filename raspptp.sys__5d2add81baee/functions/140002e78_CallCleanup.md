# CallCleanup

- ea: `0x140002e78`
- end: `0x14000355c`
- name: `CallCleanup`
- size: `1764`
- prototype: ``
- caller_count: `15`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400051f0`
- `0x140005730`
- `0x14000f224`
- `0x14000f344`
- `0x14000f8d8`
- `0x140010250`
- `0x1400102fc`
- `0x140010ef0`
- `0x140010f80`
- `0x140011050`
- `0x1400133d0`
- `0x140015a40`
- `0x140016180`
- `0x1400162f0`
- `0x140016980`

## callees

- `0x140001a70`
- `0x140002e78`
- `0x140003564`
- `0x140003aa8`
- `0x140003e38`
- `0x140003fa4`
- `0x140004008`
- `0x140010974`
- `0x140010aa4`
- `0x140012798`
- `0x1400162cc`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140002f33`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003076`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000310b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000318a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400031e7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000324b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003370`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400033ec`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000345f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400034e6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400034fa`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002f33`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003076`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000310b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000318a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400031e7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000324b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003370`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400033ec`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000345f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400034e6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400034fa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002ed7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002f9c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003095`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003135`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400031a2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400032a4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400033c4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003445`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002ed7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002f9c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003095`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003135`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400031a2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400032a4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400033c4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003445`
- `NDIS!NdisCmDispatchIncomingCloseCall` at `0x140003126`
- `NDIS!NdisCmDispatchIncomingCloseCall` at `0x140003126`
- `NDIS!NdisCmCloseCallComplete` at `0x140003295`
- `NDIS!NdisCmCloseCallComplete` at `0x140003295`
- `NDIS!NdisMCmDeleteVc` at `0x1400033b5`
- `NDIS!NdisMCmDeleteVc` at `0x1400033b5`
- `NDIS!NdisCmMakeCallComplete` at `0x140002f8d`
- `NDIS!NdisCmMakeCallComplete` at `0x140002f8d`

## pseudocode

```c
__int64 __fastcall CallCleanup(__int64 a1)
{
  int v2; // ecx
  KIRQL v3; // dl
  NDIS_STATUS v4; // esi
  __int64 v5; // r8
  int v6; // eax
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // rdx
  KIRQL v9; // al
  int v10; // r8d
  int v11; // edx
  KIRQL v12; // al
  int v13; // ecx
  KIRQL v14; // dl
  KIRQL v15; // al
  int v16; // r8d
  int v17; // edx
  PDEVICE_OBJECT v18; // rcx
  __int64 v19; // rdx
  KIRQL v20; // dl
  KSPIN_LOCK *v21; // rcx
  KIRQL v22; // al
  KIRQL v23; // al
  __int64 v24; // rdx
  __int64 v25; // r8

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      19,
      WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids,
      *(unsigned int *)(a1 + 200));
  }
  *(_BYTE *)(a1 + 104) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
  _InterlockedIncrement((volatile signed __int32 *)a1);
  v2 = *(_DWORD *)(a1 + 424);
  if ( !v2 || (*(_DWORD *)(a1 + 428) & 0x80000) != 0 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), *(_BYTE *)(a1 + 104));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_dDD(
        WPP_GLOBAL_Control->AttachedDevice,
        v24,
        v25,
        *(unsigned int *)(a1 + 200),
        *(_DWORD *)(a1 + 424),
        *(_DWORD *)(a1 + 428));
    }
    return DereferenceRefCount(a1);
  }
  if ( (v2 & 0x60000) != 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_83;
    }
    v8 = 21;
    goto LABEL_82;
  }
  if ( (v2 & 0x1000) != 0 )
  {
    v3 = *(_BYTE *)(a1 + 104);
    v4 = *(_DWORD *)(a1 + 592);
    *(_DWORD *)(a1 + 424) = v2 & 0xFFFFEFFF;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), v3);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 22, v5, *(unsigned int *)(a1 + 200), v4);
    }
    NdisCmMakeCallComplete(v4, *(NDIS_HANDLE *)(a1 + 224), 0, 0, *(PCO_CALL_PARAMETERS *)(a1 + 232));
    *(_BYTE *)(a1 + 104) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
    *(_QWORD *)(a1 + 232) = 0;
  }
  v6 = *(_DWORD *)(a1 + 424);
  if ( (v6 & 0x100) != 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_83;
    }
    v8 = 23;
    goto LABEL_82;
  }
  if ( (v6 & 8) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        24,
        WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids,
        *(unsigned int *)(a1 + 200));
    }
    *(_DWORD *)(a1 + 424) = *(_DWORD *)(a1 + 424) & 0xFFFFFFB7 | 0x40;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        25,
        WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids,
        *(unsigned int *)(a1 + 200));
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), *(_BYTE *)(a1 + 104));
    CallFlushTxNBLQueue(a1);
    CallFlushRxNBLQueue(a1);
    v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
    v10 = *(_DWORD *)(a1 + 428);
    v11 = *(_DWORD *)(a1 + 424);
    *(_BYTE *)(a1 + 104) = v9;
    if ( (v10 & 0x800) == 0 && (v11 & 0x10) == 0 )
    {
      *(_DWORD *)(a1 + 428) = v10 | 0x800;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          26,
          WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids,
          *(unsigned int *)(a1 + 200));
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), *(_BYTE *)(a1 + 104));
      NdisCmDispatchIncomingCloseCall(0, *(NDIS_HANDLE *)(a1 + 224), 0, 0);
      v12 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
      *(_DWORD *)(a1 + 428) &= ~0x800u;
      *(_BYTE *)(a1 + 104) = v12;
    }
    else
    {
      *(_DWORD *)(a1 + 424) = v11 & 0xFFFFFFBF;
    }
    DereferenceRefCount(a1);
  }
  v13 = *(_DWORD *)(a1 + 424);
  if ( (v13 & 0x10010) == 0x10010 )
  {
    v14 = *(_BYTE *)(a1 + 104);
    *(_DWORD *)(a1 + 428) |= 0x80000u;
    *(_DWORD *)(a1 + 424) = v13 & 0xFFFEFFFF;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), v14);
    DereferenceRefCount(a1 + 32);
    v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
    *(_DWORD *)(a1 + 428) &= ~0x80000u;
    *(_BYTE *)(a1 + 104) = v15;
  }
  v16 = *(_DWORD *)(a1 + 428);
  v17 = *(_DWORD *)(a1 + 424);
  if ( (v16 & 0x800) == 0 && (v17 & 0x40) == 0 )
  {
    if ( (v17 & 4) != 0 )
    {
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), *(_BYTE *)(a1 + 104));
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v19 = 28;
LABEL_77:
        WPP_SF_d(v18->AttachedDevice, v19, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids, *(unsigned int *)(a1 + 200));
        return DereferenceRefCount(a1);
      }
      return DereferenceRefCount(a1);
    }
    if ( (v17 & 0x8000) != 0 )
    {
      v20 = *(_BYTE *)(a1 + 104);
      v21 = (KSPIN_LOCK *)(a1 + 96);
      if ( (v16 & 0x200) != 0 )
      {
LABEL_84:
        KeReleaseSpinLock(v21, v20);
        return DereferenceRefCount(a1);
      }
      *(_DWORD *)(a1 + 428) = v16 | 0x200;
      KeReleaseSpinLock(v21, v20);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          29,
          WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids,
          *(unsigned int *)(a1 + 200));
      }
      NdisCmCloseCallComplete(0, *(NDIS_HANDLE *)(a1 + 224), 0);
      v22 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
      *(_DWORD *)(a1 + 424) &= ~0x8000u;
      v17 = *(_DWORD *)(a1 + 424);
      *(_BYTE *)(a1 + 104) = v22;
    }
    if ( !*(_BYTE *)(a1 + 192) )
      goto LABEL_83;
    if ( (v17 & 0x100) == 0 )
    {
      if ( *(_QWORD *)(a1 + 232) )
      {
        PptpCmFreeCallParams();
        *(_QWORD *)(a1 + 232) = 0;
      }
      if ( (*(_DWORD *)(a1 + 424) & 0x42) == 2 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            31,
            WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids,
            *(unsigned int *)(a1 + 200));
        }
        *(_DWORD *)(a1 + 424) &= ~2u;
        KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), *(_BYTE *)(a1 + 104));
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            32,
            WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids,
            *(unsigned int *)(a1 + 200));
        }
        NdisMCmDeleteVc(*(NDIS_HANDLE *)(a1 + 224));
        v23 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
        *(_QWORD *)(a1 + 224) = 0;
        *(_BYTE *)(a1 + 104) = v23;
        CallDetachFromAdapter(a1);
        KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), *(_BYTE *)(a1 + 104));
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            33,
            WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids,
            *(unsigned int *)(a1 + 200));
        }
        CtlDisconnectCall(a1);
        CallpCancelCallTimers(a1);
        DereferenceRefCount(a1);
        *(_BYTE *)(a1 + 104) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
      }
      goto LABEL_83;
    }
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
LABEL_83:
      v20 = *(_BYTE *)(a1 + 104);
      v21 = (KSPIN_LOCK *)(a1 + 96);
      goto LABEL_84;
    }
    v8 = 30;
LABEL_82:
    WPP_SF_d(v7->AttachedDevice, v8, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids, *(unsigned int *)(a1 + 200));
    goto LABEL_83;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), *(_BYTE *)(a1 + 104));
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v19 = 27;
    goto LABEL_77;
  }
  return DereferenceRefCount(a1);
}

```

## disassembly

```asm
0x140002e78  push    rbx
0x140002e7a  push    rbp
0x140002e7b  push    rsi
0x140002e7c  push    rdi
0x140002e7d  push    r12
0x140002e7f  push    r14
0x140002e81  push    r15
0x140002e83  sub     rsp, 30h
0x140002e87  mov     rbx, rcx
0x140002e8a  mov     rcx, cs:WPP_GLOBAL_Control
0x140002e91  lea     r15, WPP_GLOBAL_Control
0x140002e98  lea     r12, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids
0x140002e9f  mov     bpl, 2
0x140002ea2  mov     r14b, 10h
0x140002ea5  cmp     rcx, r15
0x140002ea8  jz      short loc_140002ED0
0x140002eaa  mov     eax, [rcx+2Ch]
0x140002ead  test    r14b, al
0x140002eb0  jz      short loc_140002ED0
0x140002eb2  cmp     [rcx+29h], bpl
0x140002eb6  jb      short loc_140002ED0
0x140002eb8  mov     r9d, [rbx+0C8h]
0x140002ebf  mov     edx, 13h
0x140002ec4  mov     rcx, [rcx+18h]
0x140002ec8  mov     r8, r12
0x140002ecb  call    WPP_SF_d
0x140002ed0  lea     rdi, [rbx+60h]
0x140002ed4  mov     rcx, rdi; SpinLock
0x140002ed7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002ede  nop     dword ptr [rax+rax+00h]
0x140002ee3  mov     [rbx+68h], al
0x140002ee6  lock inc dword ptr [rbx]
0x140002ee9  mov     ecx, [rbx+1A8h]
0x140002eef  test    ecx, ecx
0x140002ef1  jz      loc_1400034F4
0x140002ef7  test    dword ptr [rbx+1ACh], 80000h
0x140002f01  jnz     loc_1400034F4
0x140002f07  test    ecx, 60000h
0x140002f0d  jnz     loc_1400034AE
0x140002f13  bt      ecx, 0Ch
0x140002f17  jnb     loc_140002FB6
0x140002f1d  mov     dl, [rbx+68h]; NewIrql
0x140002f20  btr     ecx, 0Ch
0x140002f24  mov     esi, [rbx+250h]
0x140002f2a  mov     [rbx+1A8h], ecx
0x140002f30  mov     rcx, rdi; SpinLock
0x140002f33  call    cs:__imp_KeReleaseSpinLock
0x140002f3a  nop     dword ptr [rax+rax+00h]
0x140002f3f  mov     rcx, cs:WPP_GLOBAL_Control
0x140002f46  cmp     rcx, r15
0x140002f49  jz      short loc_140002F72
0x140002f4b  mov     eax, [rcx+2Ch]
0x140002f4e  test    r14b, al
0x140002f51  jz      short loc_140002F72
0x140002f53  cmp     [rcx+29h], bpl
0x140002f57  jb      short loc_140002F72
0x140002f59  mov     r9d, [rbx+0C8h]
0x140002f60  mov     edx, 16h
0x140002f65  mov     rcx, [rcx+18h]
0x140002f69  mov     dword ptr [rsp+68h+CallParameters], esi
0x140002f6d  call    WPP_SF_dd
0x140002f72  mov     rax, [rbx+0E8h]
0x140002f79  xor     r9d, r9d; CallMgrPartyContext
0x140002f7c  mov     rdx, [rbx+0E0h]; NdisVcHandle
0x140002f83  xor     r8d, r8d; NdisPartyHandle
0x140002f86  mov     ecx, esi; Status
0x140002f88  mov     [rsp+68h+CallParameters], rax; CallParameters
0x140002f8d  call    cs:__imp_NdisCmMakeCallComplete
0x140002f94  nop     dword ptr [rax+rax+00h]
0x140002f99  mov     rcx, rdi; SpinLock
0x140002f9c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002fa3  nop     dword ptr [rax+rax+00h]
0x140002fa8  mov     [rbx+68h], al
0x140002fab  mov     qword ptr [rbx+0E8h], 0
0x140002fb6  mov     eax, [rbx+1A8h]
0x140002fbc  bt      eax, 8
0x140002fc0  jnb     short loc_140002FF2
0x140002fc2  mov     rcx, cs:WPP_GLOBAL_Control
0x140002fc9  cmp     rcx, r15
0x140002fcc  jz      loc_1400034E0
0x140002fd2  mov     eax, [rcx+2Ch]
0x140002fd5  test    r14b, al
0x140002fd8  jz      loc_1400034E0
0x140002fde  cmp     [rcx+29h], bpl
0x140002fe2  jb      loc_1400034E0
0x140002fe8  mov     edx, 17h
0x140002fed  jmp     loc_1400034CD
0x140002ff2  test    al, 8
0x140002ff4  jz      loc_14000315F
0x140002ffa  mov     rcx, cs:WPP_GLOBAL_Control
0x140003001  cmp     rcx, r15
0x140003004  jz      short loc_14000302C
0x140003006  mov     eax, [rcx+2Ch]
0x140003009  test    r14b, al
0x14000300c  jz      short loc_14000302C
0x14000300e  cmp     [rcx+29h], bpl
0x140003012  jb      short loc_14000302C
0x140003014  mov     r9d, [rbx+0C8h]
0x14000301b  mov     edx, 18h
0x140003020  mov     rcx, [rcx+18h]
0x140003024  mov     r8, r12
0x140003027  call    WPP_SF_d
0x14000302c  mov     eax, [rbx+1A8h]
0x140003032  and     eax, 0FFFFFFF7h
0x140003035  or      eax, 40h
0x140003038  mov     [rbx+1A8h], eax
0x14000303e  mov     rcx, cs:WPP_GLOBAL_Control
0x140003045  cmp     rcx, r15
0x140003048  jz      short loc_140003070
0x14000304a  mov     eax, [rcx+2Ch]
0x14000304d  test    r14b, al
0x140003050  jz      short loc_140003070
0x140003052  cmp     [rcx+29h], bpl
0x140003056  jb      short loc_140003070
0x140003058  mov     r9d, [rbx+0C8h]
0x14000305f  mov     edx, 19h
0x140003064  mov     rcx, [rcx+18h]
0x140003068  mov     r8, r12
0x14000306b  call    WPP_SF_d
0x140003070  mov     dl, [rbx+68h]; NewIrql
0x140003073  mov     rcx, rdi; SpinLock
0x140003076  call    cs:__imp_KeReleaseSpinLock
0x14000307d  nop     dword ptr [rax+rax+00h]
0x140003082  mov     rcx, rbx
0x140003085  call    CallFlushTxNBLQueue
0x14000308a  mov     rcx, rbx
0x14000308d  call    CallFlushRxNBLQueue
0x140003092  mov     rcx, rdi; SpinLock
0x140003095  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000309c  nop     dword ptr [rax+rax+00h]
0x1400030a1  mov     r8d, [rbx+1ACh]
0x1400030a8  bt      r8d, 0Bh
0x1400030ad  mov     edx, [rbx+1A8h]
0x1400030b3  setnb   cl
0x1400030b6  mov     [rbx+68h], al
0x1400030b9  test    r14b, dl
0x1400030bc  setz    al
0x1400030bf  test    al, cl
0x1400030c1  jz      loc_14000314E
0x1400030c7  bts     r8d, 0Bh
0x1400030cc  mov     [rbx+1ACh], r8d
0x1400030d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400030da  cmp     rcx, r15
0x1400030dd  jz      short loc_140003105
0x1400030df  mov     eax, [rcx+2Ch]
0x1400030e2  test    r14b, al
0x1400030e5  jz      short loc_140003105
0x1400030e7  cmp     [rcx+29h], bpl
0x1400030eb  jb      short loc_140003105
0x1400030ed  mov     r9d, [rbx+0C8h]
0x1400030f4  mov     edx, 1Ah
0x1400030f9  mov     rcx, [rcx+18h]
0x1400030fd  mov     r8, r12
0x140003100  call    WPP_SF_d
0x140003105  mov     dl, [rbx+68h]; NewIrql
0x140003108  mov     rcx, rdi; SpinLock
0x14000310b  call    cs:__imp_KeReleaseSpinLock
0x140003112  nop     dword ptr [rax+rax+00h]
0x140003117  mov     rdx, [rbx+0E0h]; NdisVcHandle
0x14000311e  xor     r9d, r9d; Size
0x140003121  xor     r8d, r8d; Buffer
0x140003124  xor     ecx, ecx; CloseStatus
0x140003126  call    cs:__imp_NdisCmDispatchIncomingCloseCall
0x14000312d  nop     dword ptr [rax+rax+00h]
0x140003132  mov     rcx, rdi; SpinLock
0x140003135  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000313c  nop     dword ptr [rax+rax+00h]
0x140003141  btr     dword ptr [rbx+1ACh], 0Bh
0x140003149  mov     [rbx+68h], al
0x14000314c  jmp     short loc_140003157
0x14000314e  and     edx, 0FFFFFFBFh
0x140003151  mov     [rbx+1A8h], edx
0x140003157  mov     rcx, rbx
0x14000315a  call    DereferenceRefCount
0x14000315f  mov     ecx, [rbx+1A8h]
0x140003165  mov     edx, 10010h
0x14000316a  mov     eax, ecx
0x14000316c  and     eax, edx
0x14000316e  cmp     eax, edx
0x140003170  jnz     short loc_1400031B9
0x140003172  mov     dl, [rbx+68h]; NewIrql
0x140003175  btr     ecx, 10h
0x140003179  bts     dword ptr [rbx+1ACh], 13h
0x140003181  mov     [rbx+1A8h], ecx
0x140003187  mov     rcx, rdi; SpinLock
0x14000318a  call    cs:__imp_KeReleaseSpinLock
0x140003191  nop     dword ptr [rax+rax+00h]
0x140003196  lea     rcx, [rbx+20h]
0x14000319a  call    DereferenceRefCount
0x14000319f  mov     rcx, rdi; SpinLock
0x1400031a2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400031a9  nop     dword ptr [rax+rax+00h]
0x1400031ae  btr     dword ptr [rbx+1ACh], 13h
0x1400031b6  mov     [rbx+68h], al
0x1400031b9  mov     r8d, [rbx+1ACh]
0x1400031c0  bt      r8d, 0Bh
0x1400031c5  mov     edx, [rbx+1A8h]
0x1400031cb  setnb   cl
0x1400031ce  test    dl, 40h
0x1400031d1  setz    al
0x1400031d4  test    al, cl
0x1400031d6  jz      loc_140003459
0x1400031dc  test    dl, 4
0x1400031df  jz      short loc_140003223
0x1400031e1  mov     dl, [rbx+68h]; NewIrql
0x1400031e4  mov     rcx, rdi; SpinLock
0x1400031e7  call    cs:__imp_KeReleaseSpinLock
0x1400031ee  nop     dword ptr [rax+rax+00h]
0x1400031f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400031fa  cmp     rcx, r15
0x1400031fd  jz      loc_140003544
0x140003203  mov     eax, [rcx+2Ch]
0x140003206  test    r14b, al
0x140003209  jz      loc_140003544
0x14000320f  cmp     [rcx+29h], bpl
0x140003213  jb      loc_140003544
0x140003219  mov     edx, 1Ch
0x14000321e  jmp     loc_140003496
0x140003223  bt      edx, 0Fh
0x140003227  jnb     loc_1400032C1
0x14000322d  mov     dl, [rbx+68h]; NewIrql
0x140003230  mov     eax, 200h
0x140003235  mov     rcx, rdi; SpinLock
0x140003238  test    eax, r8d
0x14000323b  jnz     loc_1400034E6
0x140003241  or      r8d, eax
0x140003244  mov     [rbx+1ACh], r8d
0x14000324b  call    cs:__imp_KeReleaseSpinLock
0x140003252  nop     dword ptr [rax+rax+00h]
0x140003257  mov     rcx, cs:WPP_GLOBAL_Control
0x14000325e  cmp     rcx, r15
0x140003261  jz      short loc_140003289
0x140003263  mov     eax, [rcx+2Ch]
0x140003266  test    r14b, al
0x140003269  jz      short loc_140003289
0x14000326b  cmp     [rcx+29h], bpl
0x14000326f  jb      short loc_140003289
0x140003271  mov     r9d, [rbx+0C8h]
0x140003278  mov     edx, 1Dh
0x14000327d  mov     rcx, [rcx+18h]
0x140003281  mov     r8, r12
0x140003284  call    WPP_SF_d
0x140003289  mov     rdx, [rbx+0E0h]; NdisVcHandle
0x140003290  xor     r8d, r8d; NdisPartyHandle
0x140003293  xor     ecx, ecx; Status
0x140003295  call    cs:__imp_NdisCmCloseCallComplete
0x14000329c  nop     dword ptr [rax+rax+00h]
0x1400032a1  mov     rcx, rdi; SpinLock
0x1400032a4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400032ab  nop     dword ptr [rax+rax+00h]
0x1400032b0  btr     dword ptr [rbx+1A8h], 0Fh
0x1400032b8  mov     edx, [rbx+1A8h]
0x1400032be  mov     [rbx+68h], al
0x1400032c1  cmp     byte ptr [rbx+0C0h], 0
0x1400032c8  jz      loc_1400034E0
0x1400032ce  bt      edx, 8
0x1400032d2  jnb     short loc_140003304
0x1400032d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400032db  cmp     rcx, r15
0x1400032de  jz      loc_1400034E0
0x1400032e4  mov     eax, [rcx+2Ch]
0x1400032e7  test    r14b, al
0x1400032ea  jz      loc_1400034E0
0x1400032f0  cmp     [rcx+29h], bpl
0x1400032f4  jb      loc_1400034E0
0x1400032fa  mov     edx, 1Eh
0x1400032ff  jmp     loc_1400034CD
0x140003304  mov     rcx, [rbx+0E8h]
0x14000330b  test    rcx, rcx
0x14000330e  jz      short loc_140003320
0x140003310  call    PptpCmFreeCallParams
0x140003315  mov     qword ptr [rbx+0E8h], 0
0x140003320  mov     eax, [rbx+1A8h]
0x140003326  and     al, 42h
0x140003328  cmp     al, bpl
0x14000332b  jnz     loc_1400034E0
0x140003331  mov     rcx, cs:WPP_GLOBAL_Control
0x140003338  cmp     rcx, r15
0x14000333b  jz      short loc_140003363
0x14000333d  mov     eax, [rcx+2Ch]
0x140003340  test    r14b, al
0x140003343  jz      short loc_140003363
0x140003345  cmp     [rcx+29h], bpl
0x140003349  jb      short loc_140003363
0x14000334b  mov     r9d, [rbx+0C8h]
0x140003352  mov     edx, 1Fh
0x140003357  mov     rcx, [rcx+18h]
0x14000335b  mov     r8, r12
0x14000335e  call    WPP_SF_d
0x140003363  and     dword ptr [rbx+1A8h], 0FFFFFFFDh
0x14000336a  mov     rcx, rdi; SpinLock
0x14000336d  mov     dl, [rbx+68h]; NewIrql
0x140003370  call    cs:__imp_KeReleaseSpinLock
0x140003377  nop     dword ptr [rax+rax+00h]
0x14000337c  mov     rcx, cs:WPP_GLOBAL_Control
0x140003383  cmp     rcx, r15
0x140003386  jz      short loc_1400033AE
0x140003388  mov     eax, [rcx+2Ch]
0x14000338b  test    r14b, al
0x14000338e  jz      short loc_1400033AE
  ... truncated ...
```
