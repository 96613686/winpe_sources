# TpCmCallCleanup

- ea: `0x140002e0c`
- end: `0x1400035af`
- name: `TpCmCallCleanup`
- size: `1955`
- prototype: ``
- caller_count: `12`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140001608`
- `0x140003d18`
- `0x140005ab0`
- `0x140005bc0`
- `0x1400108d4`
- `0x140016310`
- `0x140016534`
- `0x140017740`
- `0x140017a00`
- `0x140017cf0`
- `0x140018230`
- `0x1400182e0`

## callees

- `0x14000110c`
- `0x14000113c`
- `0x1400011b4`
- `0x1400024dc`
- `0x140002520`
- `0x140002e0c`
- `0x1400035b8`
- `0x14000547c`
- `0x140006b80`
- `0x140018230`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140002e88`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002ef1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002f40`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002fac`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003059`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400030d6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003129`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400031d6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003227`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003321`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000340e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400034fc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003535`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000357a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002e88`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002ef1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002f40`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002fac`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003059`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400030d6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003129`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400031d6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003227`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003321`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000340e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400034fc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003535`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000357a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002e6f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002ec2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002f84`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003083`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000319c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400032c0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000337a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003436`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000350c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003566`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002e6f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002ec2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002f84`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003083`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000319c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400032c0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000337a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003436`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000350c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003566`
- `NDIS!NdisCmDispatchIncomingCloseCall` at `0x140003074`
- `NDIS!NdisCmDispatchIncomingCloseCall` at `0x140003074`
- `NDIS!NdisCmCloseCallComplete` at `0x14000336b`
- `NDIS!NdisCmCloseCallComplete` at `0x14000336b`
- `NDIS!NdisMCmDeleteVc` at `0x1400034df`
- `NDIS!NdisMCmDeleteVc` at `0x1400034df`
- `NDIS!NdisCmMakeCallComplete` at `0x14000318d`
- `NDIS!NdisCmMakeCallComplete` at `0x14000318d`
- `NDIS!NdisMCmDeactivateVc` at `0x14000326c`
- `NDIS!NdisMCmDeactivateVc` at `0x14000326c`

## pseudocode

```c
void __fastcall TpCmCallCleanup(__int64 a1, unsigned int a2)
{
  KIRQL v4; // al
  KIRQL v5; // al
  int v6; // ecx
  bool v7; // zf
  __int64 v8; // r9
  volatile signed __int32 *v9; // r14
  int v10; // ecx
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  KIRQL v13; // dl
  KIRQL v14; // dl
  int v15; // eax
  KIRQL v16; // dl
  KSPIN_LOCK *v17; // rcx
  int v18; // eax
  KIRQL v19; // dl
  unsigned int v20; // ebx
  int v21; // eax
  KIRQL v22; // al
  KIRQL v23; // dl
  __int64 v24; // rdi
  KIRQL v25; // al
  __int64 v26; // rcx
  KIRQL v27; // dl

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids, a1, a2);
  }
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
  *(_DWORD *)(a1 + 92) |= 0x10000u;
  *(_BYTE *)(a1 + 64) = v4;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), v4);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids);
  }
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
  v6 = *(_DWORD *)(a1 + 80);
  *(_BYTE *)(a1 + 64) = v5;
  if ( (v6 & 0x18) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids);
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
    v8 = 3221225473LL;
  }
  else
  {
    v7 = *(_DWORD *)(a1 + 72) == 8;
    *(_DWORD *)(a1 + 80) = v6 | 8;
    if ( v7 )
      *(_DWORD *)(a1 + 72) = 9;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), v5);
    TpDropCall(a1, a2);
    v8 = 259;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids, v8);
  }
  *(_BYTE *)(a1 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
  v9 = (volatile signed __int32 *)(a1 + 24);
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 24));
  v10 = *(_DWORD *)(a1 + 88);
  if ( !v10 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
    {
      goto LABEL_110;
    }
    v12 = 22;
    goto LABEL_27;
  }
  if ( (v10 & 8) != 0 && (*(_DWORD *)(a1 + 92) & 0x800) == 0 && (v10 & 0x10) == 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids, a1);
    }
    v13 = *(_BYTE *)(a1 + 64);
    *(_DWORD *)(a1 + 92) |= 0x800u;
    *(_DWORD *)(a1 + 88) |= 0x40u;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), v13);
    NdisCmDispatchIncomingCloseCall(0, *(NDIS_HANDLE *)(a1 + 168), 0, 0);
    *(_BYTE *)(a1 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids, a1);
    }
    *(_DWORD *)(a1 + 88) &= ~0x40u;
    v10 = *(_DWORD *)(a1 + 88);
  }
  if ( (v10 & 0x40) != 0 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
    {
      goto LABEL_110;
    }
    v12 = 25;
LABEL_27:
    WPP_SF_q(v11->AttachedDevice, v12, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids, a1);
    goto LABEL_110;
  }
  if ( (v10 & 0x1000) != 0 )
  {
    v14 = *(_BYTE *)(a1 + 64);
    *(_DWORD *)(a1 + 88) = v10 & 0xFFFFEFFF;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), v14);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_qd(
        WPP_GLOBAL_Control->AttachedDevice,
        26,
        WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids,
        a1,
        -1073741823);
    }
    NdisCmMakeCallComplete(-1073741823, *(NDIS_HANDLE *)(a1 + 168), 0, 0, *(PCO_CALL_PARAMETERS *)(a1 + 176));
    *(_BYTE *)(a1 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
    *(_QWORD *)(a1 + 176) = 0;
  }
  v15 = *(_DWORD *)(a1 + 88);
  if ( (v15 & 0x2000) == 0 )
  {
    if ( (v15 & 4) != 0 )
    {
      v18 = *(_DWORD *)(a1 + 92);
      if ( (v18 & 0x400) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids, a1);
        }
      }
      else
      {
        v19 = *(_BYTE *)(a1 + 64);
        *(_DWORD *)(a1 + 92) = v18 | 0x400;
        KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), v19);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids, a1);
        }
        v20 = NdisMCmDeactivateVc(*(NDIS_HANDLE *)(a1 + 168));
        if ( v20 != 259 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids, a1);
          }
          PppoeCmDeactivateVcComplete(v20, a1);
        }
        *(_BYTE *)(a1 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
      }
    }
    v16 = *(_BYTE *)(a1 + 64);
    if ( (*(_DWORD *)(a1 + 88) & 0x8004) == 0x8000 )
    {
      *(_DWORD *)(a1 + 88) &= ~0x8000u;
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), v16);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids, a1);
      }
      NdisCmCloseCallComplete(0, *(NDIS_HANDLE *)(a1 + 168), 0);
      v16 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
      *(_BYTE *)(a1 + 64) = v16;
    }
    v21 = *(_DWORD *)(a1 + 88);
    if ( (v21 & 8) != 0 )
    {
      if ( (v21 & 0x10) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids, a1);
        }
        *(_DWORD *)(a1 + 88) &= 0xFFFFFFE7;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids, a1);
        }
        *(_DWORD *)(a1 + 88) &= ~8u;
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
      if ( _InterlockedExchangeAdd(v9, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(__int64))(a1 + 32))(a1 + 24);
      v22 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
      *(_BYTE *)(a1 + 64) = v22;
      v16 = v22;
    }
    if ( *(_BYTE *)(a1 + 76) )
    {
      if ( *(_QWORD *)(a1 + 176) )
        *(_QWORD *)(a1 + 176) = 0;
      if ( (*(_DWORD *)(a1 + 88) & 6) == 2 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids, a1);
        }
        *(_DWORD *)(a1 + 88) &= ~2u;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids, a1);
        }
        NdisMCmDeleteVc(*(NDIS_HANDLE *)(a1 + 168));
        v23 = *(_BYTE *)(a1 + 64);
        v24 = *(_QWORD *)(a1 + 96);
        *(_QWORD *)(a1 + 168) = 0;
        KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), v23);
        v25 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v24 + 8));
        v26 = *(_QWORD *)(v24 + 96);
        *(_BYTE *)(v24 + 16) = v25;
        RemoveFromHandleTable(v26, *(_QWORD *)(a1 + 112));
        v27 = *(_BYTE *)(v24 + 16);
        --*(_DWORD *)(v24 + 684);
        KeReleaseSpinLock((PKSPIN_LOCK)(v24 + 8), v27);
        DereferenceAdapter(*(_QWORD *)(a1 + 96));
        if ( _InterlockedExchangeAdd(v9, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(__int64))(a1 + 32))(a1 + 24);
        v16 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
        *(_BYTE *)(a1 + 64) = v16;
      }
    }
    v17 = (KSPIN_LOCK *)(a1 + 56);
    goto LABEL_109;
  }
  v16 = *(_BYTE *)(a1 + 64);
  v17 = (KSPIN_LOCK *)(a1 + 56);
  if ( (v15 & 0x4000) == 0 )
  {
LABEL_109:
    KeReleaseSpinLock(v17, v16);
    goto LABEL_110;
  }
  *(_DWORD *)(a1 + 88) = v15 & 0xFFFFBFFF;
  KeReleaseSpinLock(v17, v16);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 40), 0xFFFFFFFF) == 1 )
    (*(void (**)(void))(a1 + 48))();
LABEL_110:
  if ( _InterlockedExchangeAdd(v9, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(__int64))(a1 + 32))(a1 + 24);
}

```

## disassembly

```asm
0x140002e0c  push    rbx
0x140002e0e  push    rbp
0x140002e0f  push    rsi
0x140002e10  push    rdi
0x140002e11  push    r12
0x140002e13  push    r13
0x140002e15  push    r14
0x140002e17  push    r15
0x140002e19  sub     rsp, 38h
0x140002e1d  mov     ebx, edx
0x140002e1f  mov     rsi, rcx
0x140002e22  mov     rcx, cs:WPP_GLOBAL_Control
0x140002e29  lea     r13, WPP_GLOBAL_Control
0x140002e30  lea     r14, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids
0x140002e37  mov     r12b, 3
0x140002e3a  mov     dil, 2
0x140002e3d  cmp     rcx, r13
0x140002e40  jz      short loc_140002E68
0x140002e42  mov     eax, [rcx+2Ch]
0x140002e45  test    dil, al
0x140002e48  jz      short loc_140002E68
0x140002e4a  cmp     [rcx+29h], r12b
0x140002e4e  jb      short loc_140002E68
0x140002e50  mov     rcx, [rcx+18h]
0x140002e54  mov     edx, 15h
0x140002e59  mov     r9, rsi
0x140002e5c  mov     dword ptr [rsp+78h+CallParameters], ebx
0x140002e60  mov     r8, r14
0x140002e63  call    WPP_SF_qd
0x140002e68  lea     rbp, [rsi+38h]
0x140002e6c  mov     rcx, rbp; SpinLock
0x140002e6f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002e76  nop     dword ptr [rax+rax+00h]
0x140002e7b  bts     dword ptr [rsi+5Ch], 10h
0x140002e80  mov     rcx, rbp; SpinLock
0x140002e83  mov     dl, al; NewIrql
0x140002e85  mov     [rsi+40h], al
0x140002e88  call    cs:__imp_KeReleaseSpinLock
0x140002e8f  nop     dword ptr [rax+rax+00h]
0x140002e94  mov     rcx, cs:WPP_GLOBAL_Control
0x140002e9b  cmp     rcx, r13
0x140002e9e  jz      short loc_140002EBF
0x140002ea0  mov     eax, [rcx+2Ch]
0x140002ea3  test    dil, al
0x140002ea6  jz      short loc_140002EBF
0x140002ea8  cmp     [rcx+29h], r12b
0x140002eac  jb      short loc_140002EBF
0x140002eae  mov     rcx, [rcx+18h]
0x140002eb2  mov     edx, 23h ; '#'
0x140002eb7  mov     r8, r14
0x140002eba  call    WPP_SF_
0x140002ebf  mov     rcx, rbp; SpinLock
0x140002ec2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002ec9  nop     dword ptr [rax+rax+00h]
0x140002ece  mov     ecx, [rsi+50h]
0x140002ed1  mov     [rsi+40h], al
0x140002ed4  test    cl, 18h
0x140002ed7  jnz     short loc_140002F0F
0x140002ed9  or      ecx, 8
0x140002edc  cmp     dword ptr [rsi+48h], 8
0x140002ee0  mov     [rsi+50h], ecx
0x140002ee3  jnz     short loc_140002EEC
0x140002ee5  mov     dword ptr [rsi+48h], 9
0x140002eec  mov     dl, al; NewIrql
0x140002eee  mov     rcx, rbp; SpinLock
0x140002ef1  call    cs:__imp_KeReleaseSpinLock
0x140002ef8  nop     dword ptr [rax+rax+00h]
0x140002efd  mov     edx, ebx
0x140002eff  mov     rcx, rsi
0x140002f02  call    TpDropCall
0x140002f07  mov     r9d, 103h
0x140002f0d  jmp     short loc_140002F52
0x140002f0f  mov     rcx, cs:WPP_GLOBAL_Control
0x140002f16  cmp     rcx, r13
0x140002f19  jz      short loc_140002F3A
0x140002f1b  mov     eax, [rcx+2Ch]
0x140002f1e  test    dil, al
0x140002f21  jz      short loc_140002F3A
0x140002f23  cmp     [rcx+29h], r12b
0x140002f27  jb      short loc_140002F3A
0x140002f29  mov     rcx, [rcx+18h]
0x140002f2d  mov     edx, 25h ; '%'
0x140002f32  mov     r8, r14
0x140002f35  call    WPP_SF_
0x140002f3a  mov     dl, [rsi+40h]; NewIrql
0x140002f3d  mov     rcx, rbp; SpinLock
0x140002f40  call    cs:__imp_KeReleaseSpinLock
0x140002f47  nop     dword ptr [rax+rax+00h]
0x140002f4c  mov     r9d, 0C0000001h
0x140002f52  mov     rcx, cs:WPP_GLOBAL_Control
0x140002f59  cmp     rcx, r13
0x140002f5c  jz      short loc_140002F81
0x140002f5e  mov     eax, [rcx+2Ch]
0x140002f61  test    dil, al
0x140002f64  jz      short loc_140002F81
0x140002f66  cmp     [rcx+29h], r12b
0x140002f6a  jb      short loc_140002F81
0x140002f6c  mov     rcx, [rcx+18h]
0x140002f70  lea     r8, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids
0x140002f77  mov     edx, 26h ; '&'
0x140002f7c  call    WPP_SF_d
0x140002f81  mov     rcx, rbp; SpinLock
0x140002f84  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002f8b  nop     dword ptr [rax+rax+00h]
0x140002f90  mov     [rsi+40h], al
0x140002f93  lea     r14, [rsi+18h]
0x140002f97  lock inc dword ptr [r14]
0x140002f9b  mov     ecx, [rsi+58h]
0x140002f9e  or      r15d, 0FFFFFFFFh
0x140002fa2  test    ecx, ecx
0x140002fa4  jnz     short loc_140002FFA
0x140002fa6  mov     dl, [rsi+40h]; NewIrql
0x140002fa9  mov     rcx, rbp; SpinLock
0x140002fac  call    cs:__imp_KeReleaseSpinLock
0x140002fb3  nop     dword ptr [rax+rax+00h]
0x140002fb8  mov     rcx, cs:WPP_GLOBAL_Control
0x140002fbf  cmp     rcx, r13
0x140002fc2  jz      loc_140003586
0x140002fc8  mov     eax, [rcx+2Ch]
0x140002fcb  test    dil, al
0x140002fce  jz      loc_140003586
0x140002fd4  cmp     [rcx+29h], r12b
0x140002fd8  jb      loc_140003586
0x140002fde  lea     edx, [r15+17h]
0x140002fe2  mov     rcx, [rcx+18h]
0x140002fe6  lea     r8, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids
0x140002fed  mov     r9, rsi
0x140002ff0  call    WPP_SF_q
0x140002ff5  jmp     loc_140003586
0x140002ffa  test    cl, 8
0x140002ffd  jz      loc_1400030CB
0x140003003  mov     ebx, 800h
0x140003008  test    [rsi+5Ch], ebx
0x14000300b  jnz     loc_1400030CB
0x140003011  test    cl, 10h
0x140003014  jnz     loc_1400030CB
0x14000301a  mov     rcx, cs:WPP_GLOBAL_Control
0x140003021  cmp     rcx, r13
0x140003024  jz      short loc_14000304C
0x140003026  mov     eax, [rcx+2Ch]
0x140003029  test    dil, al
0x14000302c  jz      short loc_14000304C
0x14000302e  cmp     [rcx+29h], r12b
0x140003032  jb      short loc_14000304C
0x140003034  mov     rcx, [rcx+18h]
0x140003038  lea     r8, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids
0x14000303f  mov     edx, 17h
0x140003044  mov     r9, rsi
0x140003047  call    WPP_SF_q
0x14000304c  mov     dl, [rsi+40h]; NewIrql
0x14000304f  mov     rcx, rbp; SpinLock
0x140003052  or      [rsi+5Ch], ebx
0x140003055  or      dword ptr [rsi+58h], 40h
0x140003059  call    cs:__imp_KeReleaseSpinLock
0x140003060  nop     dword ptr [rax+rax+00h]
0x140003065  mov     rdx, [rsi+0A8h]; NdisVcHandle
0x14000306c  xor     r9d, r9d; Size
0x14000306f  xor     r8d, r8d; Buffer
0x140003072  xor     ecx, ecx; CloseStatus
0x140003074  call    cs:__imp_NdisCmDispatchIncomingCloseCall
0x14000307b  nop     dword ptr [rax+rax+00h]
0x140003080  mov     rcx, rbp; SpinLock
0x140003083  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000308a  nop     dword ptr [rax+rax+00h]
0x14000308f  mov     [rsi+40h], al
0x140003092  mov     rcx, cs:WPP_GLOBAL_Control
0x140003099  cmp     rcx, r13
0x14000309c  jz      short loc_1400030C4
0x14000309e  mov     eax, [rcx+2Ch]
0x1400030a1  test    dil, al
0x1400030a4  jz      short loc_1400030C4
0x1400030a6  cmp     [rcx+29h], r12b
0x1400030aa  jb      short loc_1400030C4
0x1400030ac  mov     rcx, [rcx+18h]
0x1400030b0  lea     r8, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids
0x1400030b7  mov     edx, 18h
0x1400030bc  mov     r9, rsi
0x1400030bf  call    WPP_SF_q
0x1400030c4  and     dword ptr [rsi+58h], 0FFFFFFBFh
0x1400030c8  mov     ecx, [rsi+58h]
0x1400030cb  test    cl, 40h
0x1400030ce  jz      short loc_140003112
0x1400030d0  mov     dl, [rsi+40h]; NewIrql
0x1400030d3  mov     rcx, rbp; SpinLock
0x1400030d6  call    cs:__imp_KeReleaseSpinLock
0x1400030dd  nop     dword ptr [rax+rax+00h]
0x1400030e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400030e9  cmp     rcx, r13
0x1400030ec  jz      loc_140003586
0x1400030f2  mov     eax, [rcx+2Ch]
0x1400030f5  test    dil, al
0x1400030f8  jz      loc_140003586
0x1400030fe  cmp     [rcx+29h], r12b
0x140003102  jb      loc_140003586
0x140003108  mov     edx, 19h
0x14000310d  jmp     loc_140002FE2
0x140003112  bt      ecx, 0Ch
0x140003116  jnb     loc_1400031B6
0x14000311c  mov     dl, [rsi+40h]; NewIrql
0x14000311f  btr     ecx, 0Ch
0x140003123  mov     [rsi+58h], ecx
0x140003126  mov     rcx, rbp; SpinLock
0x140003129  call    cs:__imp_KeReleaseSpinLock
0x140003130  nop     dword ptr [rax+rax+00h]
0x140003135  mov     rcx, cs:WPP_GLOBAL_Control
0x14000313c  cmp     rcx, r13
0x14000313f  jz      short loc_14000316F
0x140003141  mov     eax, [rcx+2Ch]
0x140003144  test    dil, al
0x140003147  jz      short loc_14000316F
0x140003149  cmp     [rcx+29h], r12b
0x14000314d  jb      short loc_14000316F
0x14000314f  mov     rcx, [rcx+18h]
0x140003153  lea     r8, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids
0x14000315a  mov     edx, 1Ah
0x14000315f  mov     dword ptr [rsp+78h+CallParameters], 0C0000001h
0x140003167  mov     r9, rsi
0x14000316a  call    WPP_SF_qd
0x14000316f  mov     rax, [rsi+0B0h]
0x140003176  xor     r9d, r9d; CallMgrPartyContext
0x140003179  mov     rdx, [rsi+0A8h]; NdisVcHandle
0x140003180  xor     r8d, r8d; NdisPartyHandle
0x140003183  mov     ecx, 0C0000001h; Status
0x140003188  mov     [rsp+78h+CallParameters], rax; CallParameters
0x14000318d  call    cs:__imp_NdisCmMakeCallComplete
0x140003194  nop     dword ptr [rax+rax+00h]
0x140003199  mov     rcx, rbp; SpinLock
0x14000319c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400031a3  nop     dword ptr [rax+rax+00h]
0x1400031a8  mov     [rsi+40h], al
0x1400031ab  mov     qword ptr [rsi+0B0h], 0
0x1400031b6  mov     eax, [rsi+58h]
0x1400031b9  bt      eax, 0Dh
0x1400031bd  jnb     short loc_140003204
0x1400031bf  mov     dl, [rsi+40h]; NewIrql
0x1400031c2  mov     rcx, rbp; SpinLock
0x1400031c5  bt      eax, 0Eh
0x1400031c9  jnb     loc_14000357A
0x1400031cf  btr     eax, 0Eh
0x1400031d3  mov     [rsi+58h], eax
0x1400031d6  call    cs:__imp_KeReleaseSpinLock
0x1400031dd  nop     dword ptr [rax+rax+00h]
0x1400031e2  lea     rcx, [rsi+28h]
0x1400031e6  mov     eax, r15d
0x1400031e9  lock xadd [rcx], eax
0x1400031ed  cmp     eax, 1
0x1400031f0  jnz     loc_140003586
0x1400031f6  mov     rax, [rcx+8]
0x1400031fa  call    _guard_dispatch_icall
0x1400031ff  jmp     loc_140003586
0x140003204  test    al, 4
0x140003206  jz      loc_140003303
0x14000320c  mov     eax, [rsi+5Ch]
0x14000320f  mov     ecx, 400h
0x140003214  test    ecx, eax
0x140003216  jnz     loc_1400032D1
0x14000321c  mov     dl, [rsi+40h]; NewIrql
0x14000321f  or      eax, ecx
0x140003221  mov     rcx, rbp; SpinLock
0x140003224  mov     [rsi+5Ch], eax
0x140003227  call    cs:__imp_KeReleaseSpinLock
0x14000322e  nop     dword ptr [rax+rax+00h]
0x140003233  mov     rcx, cs:WPP_GLOBAL_Control
0x14000323a  cmp     rcx, r13
0x14000323d  jz      short loc_140003265
0x14000323f  mov     eax, [rcx+2Ch]
0x140003242  test    dil, al
0x140003245  jz      short loc_140003265
0x140003247  cmp     [rcx+29h], r12b
0x14000324b  jb      short loc_140003265
0x14000324d  mov     rcx, [rcx+18h]
0x140003251  lea     r8, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids
0x140003258  mov     edx, 1Bh
0x14000325d  mov     r9, rsi
0x140003260  call    WPP_SF_q
0x140003265  mov     rcx, [rsi+0A8h]; NdisVcHandle
0x14000326c  call    cs:__imp_NdisMCmDeactivateVc
0x140003273  nop     dword ptr [rax+rax+00h]
0x140003278  mov     ebx, eax
0x14000327a  cmp     eax, 103h
0x14000327f  jz      short loc_1400032BD
0x140003281  mov     rcx, cs:WPP_GLOBAL_Control
0x140003288  cmp     rcx, r13
0x14000328b  jz      short loc_1400032B3
0x14000328d  mov     edx, [rcx+2Ch]
0x140003290  test    dil, dl
0x140003293  jz      short loc_1400032B3
0x140003295  cmp     [rcx+29h], r12b
0x140003299  jb      short loc_1400032B3
0x14000329b  mov     rcx, [rcx+18h]
0x14000329f  lea     r8, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids
0x1400032a6  mov     edx, 1Ch
0x1400032ab  mov     r9, rsi
0x1400032ae  call    WPP_SF_q
0x1400032b3  mov     rdx, rsi
0x1400032b6  mov     ecx, ebx
0x1400032b8  call    PppoeCmDeactivateVcComplete
0x1400032bd  mov     rcx, rbp; SpinLock
0x1400032c0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400032c7  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
