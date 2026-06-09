# CallpNewIncomingConnection

- ea: `0x140011050`
- end: `0x1400114c2`
- name: `CallpNewIncomingConnection`
- size: `1138`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140001a70`
- `0x140002e78`
- `0x140003564`
- `0x1400039f8`
- `0x140003e08`
- `0x140003e38`
- `0x140004204`
- `0x140004248`
- `0x140005674`
- `0x140006c14`
- `0x14000f0d8`
- `0x140011050`
- `0x140015da8`
- `0x1400162f0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140011159`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001118b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400111ec`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011240`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400112b8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011331`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400113a6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011463`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011483`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001149e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011159`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001118b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400111ec`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011240`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400112b8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011331`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400113a6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011463`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011483`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001149e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001112c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001116c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011224`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001128e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011312`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400113e7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001112c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001116c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011224`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001128e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011312`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400113e7`
- `NDIS!NdisCmDispatchIncomingCall` at `0x14001135b`
- `NDIS!NdisCmDispatchIncomingCall` at `0x14001135b`
- `NDIS!NdisMCmCreateVc` at `0x14001120f`
- `NDIS!NdisMCmCreateVc` at `0x14001120f`

## pseudocode

```c
__int64 __fastcall CallpNewIncomingConnection(__int64 a1)
{
  __int64 v1; // rbx
  NDIS_STATUS Vc; // edi
  char v3; // r12
  __int64 v4; // r14
  KIRQL v5; // al
  bool v6; // zf
  KIRQL v7; // dl
  KSPIN_LOCK *v8; // rcx
  KIRQL v9; // dl
  KSPIN_LOCK *v10; // rcx
  KIRQL v11; // al
  KIRQL v12; // al
  unsigned int v13; // ecx
  struct _CO_CALL_PARAMETERS *v14; // rbp
  PDEVICE_OBJECT v15; // rcx
  __int64 v16; // rdx
  unsigned int v17; // eax
  KIRQL v18; // al
  __int64 v19; // r8
  __int64 v20; // r9

  v1 = *(_QWORD *)(a1 + 24);
  Vc = -1073741823;
  v3 = 1;
  v4 = *(_QWORD *)(v1 + 56);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids);
  }
  if ( _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xBu) )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      *(_BYTE *)(v1 + 194) = 1;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xBu)
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids, v1);
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xBu)
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids, v1);
        }
      }
    }
  }
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 8));
  v6 = *(_QWORD *)(v4 + 152) == 0;
  *(_BYTE *)(v4 + 16) = v5;
  if ( v6 || !*(_QWORD *)v4 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 8), v5);
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_43;
    }
    v16 = 44;
LABEL_42:
    WPP_SF_(v15->AttachedDevice, v16, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids);
    goto LABEL_43;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 8), v5);
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 96));
  *(_BYTE *)(v1 + 104) = v7;
  v8 = (KSPIN_LOCK *)(v1 + 96);
  if ( (unsigned int)(*(_DWORD *)(v1 + 112) - 4) > 1 )
  {
    KeReleaseSpinLock(v8, v7);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qd(
        WPP_GLOBAL_Control->AttachedDevice,
        45,
        WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids,
        v1,
        -1073741823);
    }
    goto LABEL_43;
  }
  _InterlockedIncrement((volatile signed __int32 *)v1);
  v9 = *(_BYTE *)(v1 + 104);
  *(_DWORD *)(v1 + 424) |= 0x40000u;
  KeReleaseSpinLock(v8, v9);
  Vc = NdisMCmCreateVc(*(NDIS_HANDLE *)v4, *(NDIS_HANDLE *)(v4 + 152), (NDIS_HANDLE)v1, (PNDIS_HANDLE)(v1 + 224));
  v10 = (KSPIN_LOCK *)(v1 + 96);
  if ( Vc )
  {
    v11 = KeAcquireSpinLockRaiseToDpc(v10);
    *(_DWORD *)(v1 + 424) &= ~0x40000u;
    *(_BYTE *)(v1 + 104) = v11;
    KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 96), v11);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids, v1, Vc);
    }
    DereferenceRefCount(v1);
    goto LABEL_43;
  }
  v12 = KeAcquireSpinLockRaiseToDpc(v10);
  v13 = *(_DWORD *)(v1 + 424) & 0xFFFBFFFF;
  *(_BYTE *)(v1 + 104) = v12;
  *(_DWORD *)(v1 + 424) = v13 | 0x102;
  KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 96), v12);
  v14 = (struct _CO_CALL_PARAMETERS *)PptpCmBuildCallParams(v1);
  if ( !v14 )
  {
    Vc = -1073741823;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_43;
    }
    v16 = 47;
    goto LABEL_42;
  }
  *(_BYTE *)(v1 + 104) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 96));
  *(_QWORD *)(v1 + 232) = v14;
  _InterlockedIncrement((volatile signed __int32 *)v1);
  KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 96), *(_BYTE *)(v1 + 104));
  if ( (unsigned __int8)ReferenceSap(*(_QWORD *)(v1 + 56)) )
  {
    v17 = NdisCmDispatchIncomingCall(*(NDIS_HANDLE *)(*(_QWORD *)(v1 + 56) + 136LL), *(NDIS_HANDLE *)(v1 + 224), v14);
    v3 = 0;
    Vc = v17;
    if ( v17 != 259 )
      PptpCmIncomingCallComplete(v17, v1, v14);
    DereferenceSap(*(_QWORD *)(v1 + 56));
  }
  else
  {
    Vc = -1073676256;
    DereferenceRefCount(v1);
  }
LABEL_43:
  v18 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 96));
  *(_BYTE *)(v1 + 104) = v18;
  if ( v3 )
    *(_DWORD *)(v1 + 424) &= ~0x100u;
  if ( Vc >= 0 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 96), v18);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        48,
        WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids,
        (unsigned int)Vc);
    }
    LOBYTE(v20) = 1;
    CallSetState(v1, 11, v19, v20);
    if ( *(_DWORD *)(v1 + 424) )
    {
      KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 96), *(_BYTE *)(v1 + 104));
    }
    else
    {
      CallDetachFromAdapter(v1);
      KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 96), *(_BYTE *)(v1 + 104));
      CallDisconnectFromCtl(v1, *(_QWORD *)(v1 + 80));
    }
    CallCleanup(v1);
  }
  return DereferenceRefCount(v1);
}

```

## disassembly

```asm
0x140011050  push    rbx
0x140011052  push    rbp
0x140011053  push    rsi
0x140011054  push    rdi
0x140011055  push    r12
0x140011057  push    r14
0x140011059  push    r15
0x14001105b  sub     rsp, 30h
0x14001105f  mov     rbx, [rcx+18h]
0x140011063  mov     r15d, 0C0000001h
0x140011069  mov     edi, r15d
0x14001106c  mov     r12b, 1
0x14001106f  mov     r14, [rbx+38h]
0x140011073  mov     rcx, cs:WPP_GLOBAL_Control
0x14001107a  lea     rbp, WPP_GLOBAL_Control
0x140011081  cmp     rcx, rbp
0x140011084  jz      short loc_1400110A8
0x140011086  mov     eax, [rcx+2Ch]
0x140011089  test    al, 10h
0x14001108b  jz      short loc_1400110A8
0x14001108d  cmp     byte ptr [rcx+29h], 2
0x140011091  jb      short loc_1400110A8
0x140011093  mov     rcx, [rcx+18h]
0x140011097  lea     r8, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids
0x14001109e  mov     edx, 29h ; ')'
0x1400110a3  call    WPP_SF_
0x1400110a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400110af  bt      dword ptr [rcx+2Ch], 0Bh
0x1400110b4  jnb     short loc_140011125
0x1400110b6  cmp     byte ptr [rcx+29h], 4
0x1400110ba  jb      short loc_140011125
0x1400110bc  mov     [rbx+0C2h], r12b
0x1400110c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400110ca  cmp     rcx, rbp
0x1400110cd  jz      short loc_140011125
0x1400110cf  bt      dword ptr [rcx+2Ch], 0Bh
0x1400110d4  jnb     short loc_1400110F4
0x1400110d6  cmp     byte ptr [rcx+29h], 4
0x1400110da  jb      short loc_1400110F4
0x1400110dc  mov     rcx, [rcx+18h]
0x1400110e0  lea     r8, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids
0x1400110e7  mov     edx, 2Ah ; '*'
0x1400110ec  mov     r9, rbx
0x1400110ef  call    WPP_SF_q
0x1400110f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400110fb  cmp     rcx, rbp
0x1400110fe  jz      short loc_140011125
0x140011100  bt      dword ptr [rcx+2Ch], 0Bh
0x140011105  jnb     short loc_140011125
0x140011107  cmp     byte ptr [rcx+29h], 4
0x14001110b  jb      short loc_140011125
0x14001110d  mov     rcx, [rcx+18h]
0x140011111  lea     r8, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids
0x140011118  mov     edx, 2Bh ; '+'
0x14001111d  mov     r9, rbx
0x140011120  call    WPP_SF_q
0x140011125  lea     rsi, [r14+8]
0x140011129  mov     rcx, rsi; SpinLock
0x14001112c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140011133  nop     dword ptr [rax+rax+00h]
0x140011138  cmp     qword ptr [r14+98h], 0
0x140011140  mov     [r14+10h], al
0x140011144  jz      loc_1400113A1
0x14001114a  cmp     qword ptr [r14], 0
0x14001114e  jz      loc_1400113A1
0x140011154  mov     dl, al; NewIrql
0x140011156  mov     rcx, rsi; SpinLock
0x140011159  call    cs:__imp_KeReleaseSpinLock
0x140011160  nop     dword ptr [rax+rax+00h]
0x140011165  lea     rsi, [rbx+60h]
0x140011169  mov     rcx, rsi; SpinLock
0x14001116c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140011173  nop     dword ptr [rax+rax+00h]
0x140011178  mov     dl, al; NewIrql
0x14001117a  mov     [rbx+68h], al
0x14001117d  mov     eax, [rbx+70h]
0x140011180  mov     rcx, rsi; SpinLock
0x140011183  sub     eax, 4
0x140011186  cmp     eax, 1
0x140011189  jbe     short loc_1400111DE
0x14001118b  call    cs:__imp_KeReleaseSpinLock
0x140011192  nop     dword ptr [rax+rax+00h]
0x140011197  mov     rcx, cs:WPP_GLOBAL_Control
0x14001119e  cmp     rcx, rbp
0x1400111a1  jz      loc_1400113E0
0x1400111a7  mov     eax, [rcx+2Ch]
0x1400111aa  test    al, 10h
0x1400111ac  jz      loc_1400113E0
0x1400111b2  cmp     [rcx+29h], r12b
0x1400111b6  jb      loc_1400113E0
0x1400111bc  mov     rcx, [rcx+18h]
0x1400111c0  lea     r8, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids
0x1400111c7  mov     edx, 2Dh ; '-'
0x1400111cc  mov     [rsp+68h+var_48], r15d
0x1400111d1  mov     r9, rbx
0x1400111d4  call    WPP_SF_qd
0x1400111d9  jmp     loc_1400113E0
0x1400111de  lock inc dword ptr [rbx]
0x1400111e1  mov     dl, [rbx+68h]; NewIrql
0x1400111e4  bts     dword ptr [rbx+1A8h], 12h
0x1400111ec  call    cs:__imp_KeReleaseSpinLock
0x1400111f3  nop     dword ptr [rax+rax+00h]
0x1400111f8  mov     rdx, [r14+98h]; NdisAfHandle
0x1400111ff  lea     r15, [rbx+0E0h]
0x140011206  mov     rcx, [r14]; MiniportAdapterHandle
0x140011209  mov     r9, r15; NdisVcHandle
0x14001120c  mov     r8, rbx; MiniportVcContext
0x14001120f  call    cs:__imp_NdisMCmCreateVc
0x140011216  nop     dword ptr [rax+rax+00h]
0x14001121b  mov     edi, eax
0x14001121d  mov     rcx, rsi; SpinLock
0x140011220  test    eax, eax
0x140011222  jz      short loc_14001128E
0x140011224  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001122b  nop     dword ptr [rax+rax+00h]
0x140011230  btr     dword ptr [rbx+1A8h], 12h
0x140011238  mov     rcx, rsi; SpinLock
0x14001123b  mov     dl, al; NewIrql
0x14001123d  mov     [rbx+68h], al
0x140011240  call    cs:__imp_KeReleaseSpinLock
0x140011247  nop     dword ptr [rax+rax+00h]
0x14001124c  mov     rcx, cs:WPP_GLOBAL_Control
0x140011253  cmp     rcx, rbp
0x140011256  jz      short loc_140011281
0x140011258  mov     eax, [rcx+2Ch]
0x14001125b  test    al, 10h
0x14001125d  jz      short loc_140011281
0x14001125f  cmp     [rcx+29h], r12b
0x140011263  jb      short loc_140011281
0x140011265  mov     rcx, [rcx+18h]
0x140011269  lea     r8, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids
0x140011270  mov     edx, 2Eh ; '.'
0x140011275  mov     [rsp+68h+var_48], edi
0x140011279  mov     r9, rbx
0x14001127c  call    WPP_SF_qd
0x140011281  mov     rcx, rbx
0x140011284  call    DereferenceRefCount
0x140011289  jmp     loc_1400113E0
0x14001128e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140011295  nop     dword ptr [rax+rax+00h]
0x14001129a  mov     ecx, [rbx+1A8h]
0x1400112a0  mov     dl, al; NewIrql
0x1400112a2  btr     ecx, 12h
0x1400112a6  mov     [rbx+68h], al
0x1400112a9  or      ecx, 102h
0x1400112af  mov     [rbx+1A8h], ecx
0x1400112b5  mov     rcx, rsi; SpinLock
0x1400112b8  call    cs:__imp_KeReleaseSpinLock
0x1400112bf  nop     dword ptr [rax+rax+00h]
0x1400112c4  mov     rcx, rbx
0x1400112c7  call    PptpCmBuildCallParams
0x1400112cc  mov     rbp, rax
0x1400112cf  test    rax, rax
0x1400112d2  jnz     short loc_14001130F
0x1400112d4  mov     edi, 0C0000001h
0x1400112d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400112e0  lea     rbp, WPP_GLOBAL_Control
0x1400112e7  cmp     rcx, rbp
0x1400112ea  jz      loc_1400113E0
0x1400112f0  mov     eax, [rcx+2Ch]
0x1400112f3  test    al, 10h
0x1400112f5  jz      loc_1400113E0
0x1400112fb  cmp     [rcx+29h], r12b
0x1400112ff  jb      loc_1400113E0
0x140011305  mov     edx, 2Fh ; '/'
0x14001130a  jmp     loc_1400113D0
0x14001130f  mov     rcx, rsi; SpinLock
0x140011312  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140011319  nop     dword ptr [rax+rax+00h]
0x14001131e  mov     [rbx+68h], al
0x140011321  mov     [rbx+0E8h], rbp
0x140011328  lock inc dword ptr [rbx]
0x14001132b  mov     dl, [rbx+68h]; NewIrql
0x14001132e  mov     rcx, rsi; SpinLock
0x140011331  call    cs:__imp_KeReleaseSpinLock
0x140011338  nop     dword ptr [rax+rax+00h]
0x14001133d  mov     rcx, [rbx+38h]
0x140011341  call    ReferenceSap
0x140011346  test    al, al
0x140011348  jz      short loc_140011392
0x14001134a  mov     rcx, [rbx+38h]
0x14001134e  mov     r8, rbp; CallParameters
0x140011351  mov     rdx, [r15]; NdisVcHandle
0x140011354  mov     rcx, [rcx+88h]; NdisSapHandle
0x14001135b  call    cs:__imp_NdisCmDispatchIncomingCall
0x140011362  nop     dword ptr [rax+rax+00h]
0x140011367  xor     r12b, r12b
0x14001136a  mov     edi, eax
0x14001136c  cmp     eax, 103h
0x140011371  jz      short loc_140011380
0x140011373  mov     r8, rbp
0x140011376  mov     rdx, rbx
0x140011379  mov     ecx, eax
0x14001137b  call    PptpCmIncomingCallComplete
0x140011380  mov     rcx, [rbx+38h]
0x140011384  call    DereferenceSap
0x140011389  lea     rbp, WPP_GLOBAL_Control
0x140011390  jmp     short loc_1400113E0
0x140011392  mov     rcx, rbx
0x140011395  mov     edi, 0C0010020h
0x14001139a  call    DereferenceRefCount
0x14001139f  jmp     short loc_140011389
0x1400113a1  mov     dl, al; NewIrql
0x1400113a3  mov     rcx, rsi; SpinLock
0x1400113a6  call    cs:__imp_KeReleaseSpinLock
0x1400113ad  nop     dword ptr [rax+rax+00h]
0x1400113b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400113b9  cmp     rcx, rbp
0x1400113bc  jz      short loc_1400113E0
0x1400113be  mov     eax, [rcx+2Ch]
0x1400113c1  test    al, 10h
0x1400113c3  jz      short loc_1400113E0
0x1400113c5  cmp     [rcx+29h], r12b
0x1400113c9  jb      short loc_1400113E0
0x1400113cb  mov     edx, 2Ch ; ','
0x1400113d0  mov     rcx, [rcx+18h]
0x1400113d4  lea     r8, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids
0x1400113db  call    WPP_SF_
0x1400113e0  lea     rsi, [rbx+60h]
0x1400113e4  mov     rcx, rsi; SpinLock
0x1400113e7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400113ee  nop     dword ptr [rax+rax+00h]
0x1400113f3  mov     [rbx+68h], al
0x1400113f6  test    r12b, r12b
0x1400113f9  jz      short loc_140011403
0x1400113fb  btr     dword ptr [rbx+1A8h], 8
0x140011403  test    edi, edi
0x140011405  jns     loc_140011499
0x14001140b  mov     rcx, cs:WPP_GLOBAL_Control
0x140011412  cmp     rcx, rbp
0x140011415  jz      short loc_14001143C
0x140011417  mov     eax, [rcx+2Ch]
0x14001141a  test    al, 10h
0x14001141c  jz      short loc_14001143C
0x14001141e  cmp     byte ptr [rcx+29h], 1
0x140011422  jb      short loc_14001143C
0x140011424  mov     rcx, [rcx+18h]
0x140011428  lea     r8, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids
0x14001142f  mov     edx, 30h ; '0'
0x140011434  mov     r9d, edi
0x140011437  call    WPP_SF_d
0x14001143c  mov     r9b, 1
0x14001143f  mov     edx, 0Bh
0x140011444  mov     rcx, rbx
0x140011447  call    CallSetState
0x14001144c  cmp     dword ptr [rbx+1A8h], 0
0x140011453  jnz     short loc_14001147D
0x140011455  mov     rcx, rbx
0x140011458  call    CallDetachFromAdapter
0x14001145d  mov     dl, [rbx+68h]; NewIrql
0x140011460  mov     rcx, rsi; SpinLock
0x140011463  call    cs:__imp_KeReleaseSpinLock
0x14001146a  nop     dword ptr [rax+rax+00h]
0x14001146f  mov     rdx, [rbx+50h]
0x140011473  mov     rcx, rbx
0x140011476  call    CallDisconnectFromCtl
0x14001147b  jmp     short loc_14001148F
0x14001147d  mov     dl, [rbx+68h]; NewIrql
0x140011480  mov     rcx, rsi; SpinLock
0x140011483  call    cs:__imp_KeReleaseSpinLock
0x14001148a  nop     dword ptr [rax+rax+00h]
0x14001148f  mov     rcx, rbx
0x140011492  call    CallCleanup
0x140011497  jmp     short loc_1400114AA
0x140011499  mov     dl, al; NewIrql
0x14001149b  mov     rcx, rsi; SpinLock
0x14001149e  call    cs:__imp_KeReleaseSpinLock
0x1400114a5  nop     dword ptr [rax+rax+00h]
0x1400114aa  mov     rcx, rbx
0x1400114ad  call    DereferenceRefCount
0x1400114b2  add     rsp, 30h
0x1400114b6  pop     r15
0x1400114b8  pop     r14
0x1400114ba  pop     r12
0x1400114bc  pop     rdi
0x1400114bd  pop     rsi
0x1400114be  pop     rbp
0x1400114bf  pop     rbx
0x1400114c0  retn
```
