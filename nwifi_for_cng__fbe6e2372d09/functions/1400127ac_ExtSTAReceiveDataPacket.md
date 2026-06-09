# ExtSTAReceiveDataPacket

- ea: `0x1400127ac`
- end: `0x1400130af`
- name: `ExtSTAReceiveDataPacket`
- size: `2307`
- prototype: `__int64 __fastcall(struct EXTSTA_VELAN *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140012560`

## callees

- `0x14000d21c`
- `0x1400127ac`
- `0x1400131b0`
- `0x140016e00`
- `0x140018a0c`
- `0x140031e64`
- `0x140032d88`
- `0x140043404`
- `0x14006a098`
- `0x14006b818`
- `0x14006b92c`
- `0x14006b99c`
- `0x14009bbb0`
- `0x14009bbf0`
- `0x14009c4e0`

## import_xrefs

- `NDIS!NdisAcquireRWLockWrite` at `0x140012ba5`
- `NDIS!NdisAcquireRWLockWrite` at `0x140012ba5`
- `NDIS!NdisReleaseRWLock` at `0x140012b85`
- `NDIS!NdisReleaseRWLock` at `0x140012ca5`
- `NDIS!NdisReleaseRWLock` at `0x140012b85`
- `NDIS!NdisReleaseRWLock` at `0x140012ca5`
- `NDIS!NdisAcquireRWLockRead` at `0x140012cc5`
- `NDIS!NdisAcquireRWLockRead` at `0x140012cc5`

## pseudocode

```c
__int64 __fastcall ExtSTAReceiveDataPacket(
        struct EXTSTA_VELAN *a1,
        struct NWIFI_MSDU *a2,
        struct _NWIFI_LOCK_STATE *a3)
{
  unsigned __int16 *pvLookaheadBuf; // r15
  unsigned int v6; // ebx
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r8
  const unsigned __int8 *v10; // r12
  _DOT11_BSS_TYPE *p_CurrentBSSType; // rsi
  __int64 v12; // r9
  int v13; // edx
  PDEVICE_OBJECT v14; // rcx
  int v15; // edx
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  __int64 uMacHdrSize; // r10
  _VELAN **p_pGenVElan; // rcx
  __int64 v20; // r11
  unsigned int v21; // eax
  unsigned int i; // r10d
  unsigned int v23; // esi
  const struct _EVENT_DESCRIPTOR *v24; // rdx
  _VELAN *pGenVElan; // rax
  _FILE_OBJECT *pSecurityEndpoint; // rcx
  _NET_BUFFER_LIST *pNdisPacket; // rax
  char *FsContext; // rsi
  unsigned __int64 v29; // rcx
  char v30; // al
  _VELAN *v31; // r14
  int v32; // r12d
  unsigned int v33; // r15d
  __int64 v34; // rdx
  _QWORD *v35; // rcx
  unsigned __int8 v37; // [rsp+20h] [rbp-79h]
  const struct _GUID *v38; // [rsp+28h] [rbp-71h]
  __int16 v39; // [rsp+40h] [rbp-59h]
  __int16 v40; // [rsp+40h] [rbp-59h]
  unsigned __int8 *CurrentBSSID; // [rsp+48h] [rbp-51h]
  __int64 v42; // [rsp+48h] [rbp-51h]
  unsigned int v43; // [rsp+50h] [rbp-49h]
  _VELAN **v44; // [rsp+58h] [rbp-41h]
  unsigned __int16 *LockStatea; // [rsp+60h] [rbp-39h]
  __int128 v47; // [rsp+78h] [rbp-21h] BYREF
  __int128 v48; // [rsp+88h] [rbp-11h]
  __int64 v49; // [rsp+98h] [rbp-1h]
  struct _GUID v50; // [rsp+A0h] [rbp+7h] BYREF

  pvLookaheadBuf = (unsigned __int16 *)a2->MSDUCore.pvLookaheadBuf;
  v39 = *pvLookaheadBuf;
  if ( (*pvLookaheadBuf & 0x300) != 0 )
  {
    p_CurrentBSSType = &a1->RoD.CurrentBSSType;
    if ( a1->RoD.CurrentBSSType != dot11_BSS_type_infrastructure )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0 )
      {
        return 65539;
      }
      v8 = 12;
LABEL_9:
      WPP_SF_(v7->AttachedDevice, v8, WPP_cd320d255d73392dd823018075971813_Traceguids);
      return 65539;
    }
    v10 = (const unsigned __int8 *)(pvLookaheadBuf + 5);
    CurrentBSSID = a1->RoD.CurrentBSSID;
    v6 = 0;
    if ( memcmp(a1->RoD.CurrentBSSID, pvLookaheadBuf + 5, 6u) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      {
        WPP_SF__MAC__MAC_(
          WPP_GLOBAL_Control->AttachedDevice,
          13,
          (unsigned int)WPP_cd320d255d73392dd823018075971813_Traceguids,
          (_DWORD)pvLookaheadBuf + 10,
          (__int64)CurrentBSSID);
      }
      return 65539;
    }
    v9 = (__int64)(pvLookaheadBuf + 8);
  }
  else
  {
    v6 = 0;
    if ( !a1->bIsPBSSNotInDS && a1->RoD.CurrentBSSType != dot11_BSS_type_independent
      || memcmp(a1->RoD.CurrentBSSID, pvLookaheadBuf + 8, 6u) )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0 )
      {
        return 65539;
      }
      v8 = 11;
      goto LABEL_9;
    }
    v9 = (__int64)(pvLookaheadBuf + 8);
    v10 = (const unsigned __int8 *)(pvLookaheadBuf + 5);
    p_CurrentBSSType = &a1->RoD.CurrentBSSType;
  }
  v12 = *(_QWORD *)(*(_QWORD *)&a2->MSDUCore.pNdisPacket->Context->ContextData[a2->MSDUCore.pNdisPacket->Context->Offset]
                  + 8LL);
  v42 = v12;
  if ( !v12 || (v13 = *(_DWORD *)(v12 + 40), (v13 & 2) == 0) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    {
      WPP_SF__MAC__MAC__MAC_(WPP_GLOBAL_Control->AttachedDevice, 14, v9, (_DWORD)v10, (__int64)(pvLookaheadBuf + 2), v9);
    }
    if ( *p_CurrentBSSType == dot11_BSS_type_independent
      && !memcmp(a1->pGenVElan->CurrentAddress, pvLookaheadBuf + 2, 6u) )
    {
      ProbeAdhocPeer(
        a1,
        *((_DWORD *)a2->MSDUCore.pNdisPacket->NetBufferListInfo[6] + 2),
        (const unsigned __int8 (*)[6])v10);
    }
    return 65539;
  }
  if ( (v13 & 0x20) != 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0 )
    {
      return 65539;
    }
    v15 = 15;
    goto LABEL_29;
  }
  if ( (v39 & 0x40) != 0 )
  {
    v6 = 65539;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    {
      v17 = 16;
LABEL_35:
      WPP_SF_(v16->AttachedDevice, v17, WPP_cd320d255d73392dd823018075971813_Traceguids);
      return v6;
    }
    return v6;
  }
  uMacHdrSize = a2->MSDUCore.uMacHdrSize;
  if ( a2->uPktLength < (unsigned __int64)(uMacHdrSize + 8) )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0 )
    {
      return 65539;
    }
    v8 = 17;
    goto LABEL_9;
  }
  if ( (v13 & 4) == 0 )
  {
    p_pGenVElan = &a1->pGenVElan;
LABEL_68:
    v44 = p_pGenVElan;
    goto LABEL_69;
  }
  if ( !a1->pGenVElan->pSecurityEndpoint )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0 )
    {
      return 65539;
    }
    v8 = 18;
    goto LABEL_9;
  }
  p_pGenVElan = &a1->pGenVElan;
  *(_QWORD *)&v50.Data1 = a1->pGenVElan;
  v44 = &a1->pGenVElan;
  v20 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v50.Data1 + 5888LL) + 24LL);
  v21 = *(_DWORD *)(v20 + 168);
  v43 = v21;
  if ( !v21 )
    goto LABEL_68;
  v40 = *(unsigned __int16 *)((char *)pvLookaheadBuf + uMacHdrSize + 6);
  for ( i = 0; i < v21; ++i )
  {
    v12 = v42;
    if ( *(_WORD *)(*(_QWORD *)(v20 + 176) + 2LL * i) == v40 )
    {
      v23 = *pvLookaheadBuf;
      if ( (v23 & 0x100) == 0 && !memcmp((const void *)(*(_QWORD *)&v50.Data1 + 4906LL), pvLookaheadBuf + 2, 6u) )
      {
        NdisReleaseRWLock(a1->pGenVElan->pRWLock, &a3->lockStateEx);
        NdisAcquireRWLockWrite(a1->pGenVElan->pRWLock, &a3->lockStateEx, 0);
        if ( a1->RoD.CurrentBSSType == dot11_BSS_type_independent
          && (*(_BYTE *)(v42 + 40) & 0x16) == 0x16
          && a1->pGenVElan->pSecurityEndpoint )
        {
          _ExtSTAFixupDeAuth(a1);
        }
        if ( (unsigned int)Dot11Intercept1XMessage(a1->pGenVElan, a2, a3) )
        {
          v49 = 0;
          pGenVElan = a1->pGenVElan;
          v47 = 0;
          v48 = 0;
          pSecurityEndpoint = pGenVElan->pSecurityEndpoint;
          pNdisPacket = a2->MSDUCore.pNdisPacket;
          FsContext = (char *)pSecurityEndpoint->FsContext;
          v50 = 0;
          v29 = (__int64)pNdisPacket->NetBufferListInfo[13] & 0x7FFFFFFFFFFFFFFFLL;
          v50 = (struct _GUID)v29;
          if ( Microsoft_Windows_Networking_CorrelationEnabled )
            EtwEx_tidActivityInfoTransfer(v29, v24, &v50, &a1->pGenVElan->gDeviceId, v37, v38, 3);
          LODWORD(v47) = 2;
          *(_QWORD *)&v48 = a2;
          DWORD2(v47) = *((_DWORD *)FsContext + 40);
          v6 = NwfUpcallMsg((PIO_CSQ)(FsContext + 40), (const struct DOT11_AUTH_UPCALL_REQUEST *)&v47);
        }
        NdisReleaseRWLock(a1->pGenVElan->pRWLock, &a3->lockStateEx);
        NdisAcquireRWLockRead(a1->pGenVElan->pRWLock, &a3->lockStateEx, 0);
        return v6;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      {
        WPP_SF_D_MAC__MAC_(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)WPP_GLOBAL_Control,
          v9,
          (v23 >> 8) & 1,
          (__int64)a1->pGenVElan->CurrentAddress,
          (__int64)(pvLookaheadBuf + 2));
      }
      return 65539;
    }
    v21 = v43;
  }
LABEL_69:
  if ( (*(_DWORD *)(v12 + 40) & 0x10) != 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0 )
    {
      return 65539;
    }
    v15 = 20;
LABEL_29:
    WPP_SF__MAC__MAC__MAC_(v14->AttachedDevice, v15, v9, (_DWORD)v10, (__int64)(pvLookaheadBuf + 2), v9);
    return 65539;
  }
  if ( (v13 & 0xC) == 4 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0 )
    {
      return 65539;
    }
    v8 = 21;
    goto LABEL_9;
  }
  LockStatea = pvLookaheadBuf + 2;
  v30 = *((_BYTE *)pvLookaheadBuf + 4);
  if ( (v30 & 1) == 0 )
  {
    v31 = *p_pGenVElan;
    if ( ((*p_pGenVElan)->uPacketFilter & 1) == 0 )
    {
      v6 = 65539;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      {
        v17 = 24;
        goto LABEL_35;
      }
      return v6;
    }
    goto LABEL_101;
  }
  if ( v30 != -1
    || *((_BYTE *)pvLookaheadBuf + 5) != 0xFF
    || *((_BYTE *)pvLookaheadBuf + 6) != 0xFF
    || *((_BYTE *)pvLookaheadBuf + 7) != 0xFF
    || *((_BYTE *)pvLookaheadBuf + 8) != 0xFF
    || *((_BYTE *)pvLookaheadBuf + 9) != 0xFF )
  {
    v31 = a1->pGenVElan;
    if ( (v31->uPacketFilter & 2) == 0 )
    {
      v6 = 65539;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      {
        v17 = 23;
        goto LABEL_35;
      }
      return v6;
    }
LABEL_101:
    v32 = 0;
    if ( v31->State == MP6_RUNNING )
    {
      v33 = Dot11Translate80211ToEthernetNdisPacket(v31);
      if ( v33 )
      {
LABEL_103:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_38fc73abf7313b8bec012c05ad7a4fa6_Traceguids);
        }
        if ( v32 )
          Dot11PacketConverterReturnPacket(a2->MSDUCore.pNdisPacket);
        return v33;
      }
      _InterlockedIncrement((volatile signed __int32 *)&v31->OutstandingIndications);
      if ( v31->State == MP6_RUNNING )
      {
        v34 = *(_QWORD *)&a2->MSDUCore.pNdisPacket->Context->ContextData[a2->MSDUCore.pNdisPacket->Context->Offset];
        v35 = *(_QWORD **)(v34 + 40);
        *(_QWORD *)(v34 + 40) = v35 + 3;
        *v35 = Dot11PacketConverterReturnPacket;
        v35[2] = 0;
        v35[1] = v31;
        a2->MSDUCore.pNdisPacket->NetBufferListInfo[6] = *(void **)(*(_QWORD *)&a2->MSDUCore.pNdisPacket->Context->ContextData[a2->MSDUCore.pNdisPacket->Context->Offset]
                                                                  + 24LL);
        ((void (__fastcall *)(_VELAN *, _NET_BUFFER_LIST *, unsigned __int16 *))g_pfnDot11QueueRecvPacket)(
          *v44,
          a2->MSDUCore.pNdisPacket,
          LockStatea);
        return 259;
      }
      v32 = 1;
    }
    v33 = -1071448022;
    goto LABEL_103;
  }
  v31 = a1->pGenVElan;
  if ( (v31->uPacketFilter & 8) != 0 )
    goto LABEL_101;
  v6 = 65539;
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
  {
    v17 = 22;
    goto LABEL_35;
  }
  return v6;
}

```

## disassembly

```asm
0x1400127ac  mov     [rsp-8+arg_18], rbx
0x1400127b1  push    rbp
0x1400127b2  push    rsi
0x1400127b3  push    rdi
0x1400127b4  push    r12
0x1400127b6  push    r13
0x1400127b8  push    r14
0x1400127ba  push    r15
0x1400127bc  lea     rbp, [rsp-27h]
0x1400127c1  sub     rsp, 0C0h
0x1400127c8  mov     rax, cs:__security_cookie
0x1400127cf  xor     rax, rsp
0x1400127d2  mov     [rbp+57h+var_40], rax
0x1400127d6  mov     r15, [rdx+18h]
0x1400127da  mov     r14, rcx
0x1400127dd  mov     ecx, 300h
0x1400127e2  mov     [rbp+57h+LockState], r8
0x1400127e6  mov     r13, rdx
0x1400127e9  movzx   eax, word ptr [r15]
0x1400127ed  mov     dword ptr [rbp+57h+var_B0], eax
0x1400127f0  test    cx, ax
0x1400127f3  jnz     loc_14001288D
0x1400127f9  xor     ebx, ebx
0x1400127fb  cmp     [r14+0ABCh], ebx
0x140012802  jnz     short loc_14001280E
0x140012804  cmp     dword ptr [r14+64Ch], 2
0x14001280c  jnz     short loc_14001282C
0x14001280e  lea     rdx, [r15+10h]; Buf2
0x140012812  mov     r8d, 6; Size
0x140012818  lea     rcx, [r14+644h]; Buf1
0x14001281f  mov     [rbp+57h+var_A8], rdx
0x140012823  call    memcmp
0x140012828  test    eax, eax
0x14001282a  jz      short loc_140012879
0x14001282c  mov     rcx, cs:WPP_GLOBAL_Control
0x140012833  lea     rax, WPP_GLOBAL_Control
0x14001283a  cmp     rcx, rax
0x14001283d  jz      loc_140013080
0x140012843  mov     sil, 4
0x140012846  cmp     [rcx+29h], sil
0x14001284a  jb      loc_140013080
0x140012850  mov     eax, [rcx+2Ch]
0x140012853  mov     dil, 20h ; ' '
0x140012856  test    dil, al
0x140012859  jz      loc_140013080
0x14001285f  mov     edx, 0Bh
0x140012864  mov     rcx, [rcx+18h]
0x140012868  lea     r8, WPP_cd320d255d73392dd823018075971813_Traceguids
0x14001286f  call    WPP_SF_
0x140012874  jmp     loc_140013080
0x140012879  mov     r8, [rbp+57h+var_A8]
0x14001287d  lea     r12, [r15+0Ah]
0x140012881  lea     rsi, [r14+64Ch]
0x140012888  jmp     loc_140012954
0x14001288d  lea     rsi, [r14+64Ch]
0x140012894  cmp     dword ptr [rsi], 1
0x140012897  jz      short loc_1400128D3
0x140012899  mov     rcx, cs:WPP_GLOBAL_Control
0x1400128a0  lea     rax, WPP_GLOBAL_Control
0x1400128a7  cmp     rcx, rax
0x1400128aa  jz      loc_140013080
0x1400128b0  mov     sil, 4
0x1400128b3  cmp     [rcx+29h], sil
0x1400128b7  jb      loc_140013080
0x1400128bd  mov     eax, [rcx+2Ch]
0x1400128c0  mov     dil, 20h ; ' '
0x1400128c3  test    dil, al
0x1400128c6  jz      loc_140013080
0x1400128cc  mov     edx, 0Ch
0x1400128d1  jmp     short loc_140012864
0x1400128d3  lea     rax, [r14+644h]
0x1400128da  mov     r8d, 6; Size
0x1400128e0  lea     r12, [r15+0Ah]
0x1400128e4  mov     [rbp+57h+var_A8], rax
0x1400128e8  mov     rdx, r12; Buf2
0x1400128eb  mov     rcx, rax; Buf1
0x1400128ee  call    memcmp
0x1400128f3  xor     ebx, ebx
0x1400128f5  test    eax, eax
0x1400128f7  jz      short loc_140012950
0x1400128f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140012900  lea     rax, WPP_GLOBAL_Control
0x140012907  cmp     rcx, rax
0x14001290a  jz      loc_140013080
0x140012910  mov     sil, 4
0x140012913  cmp     [rcx+29h], sil
0x140012917  jb      loc_140013080
0x14001291d  mov     eax, [rcx+2Ch]
0x140012920  mov     dil, 20h ; ' '
0x140012923  test    dil, al
0x140012926  jz      loc_140013080
0x14001292c  mov     rax, [rbp+57h+var_A8]
0x140012930  lea     edx, [rbx+0Dh]
0x140012933  mov     rcx, [rcx+18h]
0x140012937  lea     r8, WPP_cd320d255d73392dd823018075971813_Traceguids
0x14001293e  mov     r9, r12
0x140012941  mov     [rsp+0F0h+var_D0], rax
0x140012946  call    WPP_SF__MAC__MAC_
0x14001294b  jmp     loc_140013080
0x140012950  lea     r8, [r15+10h]
0x140012954  mov     rax, [r13+20h]
0x140012958  mov     rcx, [rax+10h]
0x14001295c  movzx   eax, word ptr [rcx+0Ah]
0x140012960  mov     rcx, [rax+rcx+10h]
0x140012965  mov     r9, [rcx+8]
0x140012969  mov     [rbp+57h+var_A8], r9
0x14001296d  test    r9, r9
0x140012970  jz      loc_140012FFE
0x140012976  mov     edx, [r9+28h]
0x14001297a  test    dl, 2
0x14001297d  jz      loc_140012FFE
0x140012983  mov     dil, 20h ; ' '
0x140012986  test    dil, dl
0x140012989  jz      short loc_1400129DC
0x14001298b  mov     rcx, cs:WPP_GLOBAL_Control
0x140012992  lea     rax, WPP_GLOBAL_Control
0x140012999  cmp     rcx, rax
0x14001299c  jz      loc_140013080
0x1400129a2  cmp     byte ptr [rcx+29h], 2
0x1400129a6  jb      loc_140013080
0x1400129ac  mov     eax, [rcx+2Ch]
0x1400129af  test    dil, al
0x1400129b2  jz      loc_140013080
0x1400129b8  mov     edx, 0Fh
0x1400129bd  mov     rcx, [rcx+18h]
0x1400129c1  lea     rax, [r15+4]
0x1400129c5  mov     [rsp+0F0h+var_C8], r8
0x1400129ca  mov     r9, r12
0x1400129cd  mov     [rsp+0F0h+var_D0], rax
0x1400129d2  call    WPP_SF__MAC__MAC__MAC_
0x1400129d7  jmp     loc_140013080
0x1400129dc  test    byte ptr [rbp+57h+var_B0], 40h
0x1400129e0  jz      short loc_140012A31
0x1400129e2  mov     ebx, 10003h
0x1400129e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400129ee  lea     rax, WPP_GLOBAL_Control
0x1400129f5  cmp     rcx, rax
0x1400129f8  jz      loc_140013085
0x1400129fe  mov     sil, 4
0x140012a01  cmp     [rcx+29h], sil
0x140012a05  jb      loc_140013085
0x140012a0b  mov     eax, [rcx+2Ch]
0x140012a0e  test    dil, al
0x140012a11  jz      loc_140013085
0x140012a17  mov     edx, 10h
0x140012a1c  mov     rcx, [rcx+18h]
0x140012a20  lea     r8, WPP_cd320d255d73392dd823018075971813_Traceguids
0x140012a27  call    WPP_SF_
0x140012a2c  jmp     loc_140013085
0x140012a31  mov     r10d, [r13+0Ch]
0x140012a35  mov     ecx, [r13+3Ch]
0x140012a39  lea     rax, [r10+8]
0x140012a3d  cmp     rcx, rax
0x140012a40  jnb     short loc_140012A7C
0x140012a42  mov     rcx, cs:WPP_GLOBAL_Control
0x140012a49  lea     rax, WPP_GLOBAL_Control
0x140012a50  cmp     rcx, rax
0x140012a53  jz      loc_140013080
0x140012a59  mov     sil, 4
0x140012a5c  cmp     [rcx+29h], sil
0x140012a60  jb      loc_140013080
0x140012a66  mov     eax, [rcx+2Ch]
0x140012a69  test    dil, al
0x140012a6c  jz      loc_140013080
0x140012a72  mov     edx, 11h
0x140012a77  jmp     loc_140012864
0x140012a7c  mov     sil, 4
0x140012a7f  test    sil, dl
0x140012a82  jz      loc_140012D36
0x140012a88  mov     rax, [r14+0A38h]
0x140012a8f  cmp     [rax+1700h], rbx
0x140012a96  jnz     short loc_140012ACF
0x140012a98  mov     rcx, cs:WPP_GLOBAL_Control
0x140012a9f  lea     rax, WPP_GLOBAL_Control
0x140012aa6  cmp     rcx, rax
0x140012aa9  jz      loc_140013080
0x140012aaf  cmp     [rcx+29h], sil
0x140012ab3  jb      loc_140013080
0x140012ab9  mov     eax, [rcx+2Ch]
0x140012abc  test    dil, al
0x140012abf  jz      loc_140013080
0x140012ac5  mov     edx, 12h
0x140012aca  jmp     loc_140012864
0x140012acf  lea     rcx, [r14+0A38h]
0x140012ad6  mov     rax, [rcx]
0x140012ad9  mov     qword ptr [rbp+57h+var_50.Data1], rax
0x140012add  mov     [rbp+57h+var_98], rcx
0x140012ae1  mov     rax, [rax+1700h]
0x140012ae8  mov     r11, [rax+18h]
0x140012aec  mov     eax, [r11+0A8h]
0x140012af3  mov     dword ptr [rbp+57h+var_A0], eax
0x140012af6  test    eax, eax
0x140012af8  jz      loc_140012D3D
0x140012afe  movzx   r10d, word ptr [r10+r15+6]
0x140012b04  mov     [rbp+57h+var_B0], r10w
0x140012b09  mov     r10, [r11+0B0h]
0x140012b10  movzx   r11d, [rbp+57h+var_B0]
0x140012b15  mov     [rbp+57h+var_80], r10
0x140012b19  mov     r10d, ebx
0x140012b1c  cmp     r10d, eax
0x140012b1f  jnb     loc_140012D41
0x140012b25  mov     r9, [rbp+57h+var_80]
0x140012b29  mov     eax, r10d
0x140012b2c  cmp     [r9+rax*2], r11w
0x140012b31  mov     r9, [rbp+57h+var_A8]
0x140012b35  jz      short loc_140012B3F
0x140012b37  mov     eax, dword ptr [rbp+57h+var_A0]
0x140012b3a  inc     r10d
0x140012b3d  jmp     short loc_140012B1C
0x140012b3f  movzx   esi, word ptr [r15]
0x140012b43  bt      si, 8
0x140012b48  jb      loc_140012CD6
0x140012b4e  mov     rcx, qword ptr [rbp+57h+var_50.Data1]
0x140012b52  lea     rdx, [r15+4]; Buf2
0x140012b56  add     rcx, 132Ah; Buf1
0x140012b5d  mov     r8d, 6; Size
0x140012b63  call    memcmp
0x140012b68  test    eax, eax
0x140012b6a  jnz     loc_140012CD6
0x140012b70  mov     rcx, [r14+0A38h]
0x140012b77  mov     rdi, [rbp+57h+LockState]
0x140012b7b  mov     rdx, rdi; LockState
0x140012b7e  mov     rcx, [rcx+90h]; Lock
0x140012b85  call    cs:__imp_NdisReleaseRWLock
0x140012b8c  nop     dword ptr [rax+rax+00h]
0x140012b91  mov     rcx, [r14+0A38h]
0x140012b98  xor     r8d, r8d; Flags
0x140012b9b  mov     rdx, rdi; LockState
0x140012b9e  mov     rcx, [rcx+90h]; Lock
0x140012ba5  call    cs:__imp_NdisAcquireRWLockWrite
0x140012bac  nop     dword ptr [rax+rax+00h]
0x140012bb1  cmp     dword ptr [r14+64Ch], 2
0x140012bb9  jnz     short loc_140012BE1
0x140012bbb  mov     rdx, [rbp+57h+var_A8]
0x140012bbf  mov     eax, [rdx+28h]
0x140012bc2  and     eax, 16h
0x140012bc5  cmp     al, 16h
0x140012bc7  jnz     short loc_140012BE1
0x140012bc9  mov     rax, [r14+0A38h]
0x140012bd0  cmp     [rax+1700h], rbx
0x140012bd7  jz      short loc_140012BE1
0x140012bd9  mov     rcx, r14
0x140012bdc  call    __ExtSTAFixupDeAuth
0x140012be1  mov     rcx, [r14+0A38h]; struct _VELAN *
0x140012be8  mov     r8, rdi; struct _NWIFI_LOCK_STATE *
0x140012beb  mov     rdx, r13; struct NWIFI_MSDU *
0x140012bee  call    ?Dot11Intercept1XMessage@@YAHPEAU_VELAN@@PEAUNWIFI_MSDU@@PEAU_NWIFI_LOCK_STATE@@@Z; Dot11Intercept1XMessage(_VELAN *,NWIFI_MSDU *,_NWIFI_LOCK_STATE *)
0x140012bf3  test    eax, eax
0x140012bf5  jz      loc_140012C94
0x140012bfb  xor     eax, eax
0x140012bfd  mov     [rbp+57h+LockState+8], rbx
0x140012c01  mov     [rbp+57h+var_58], rax
0x140012c05  xorps   xmm0, xmm0
0x140012c08  mov     rax, [r14+0A38h]
0x140012c0f  movups  [rbp+57h+var_78], xmm0
0x140012c13  movups  [rbp+57h+var_68], xmm0
0x140012c17  mov     rcx, [rax+1700h]
0x140012c1e  mov     rax, [r13+20h]
0x140012c22  mov     rsi, [rcx+18h]
0x140012c26  movups  xmmword ptr [rbp+57h+var_50.Data1], xmm0
0x140012c2a  mov     rcx, [rax+0F8h]
0x140012c31  mov     rax, 7FFFFFFFFFFFFFFFh
0x140012c3b  and     rcx, rax; unsigned __int64
0x140012c3e  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x140012c44  mov     [rbp+57h+LockState], rcx
0x140012c48  movaps  xmm0, xmmword ptr [rbp+57h+LockState]
0x140012c4c  movdqa  xmmword ptr [rbp+57h+var_50.Data1], xmm0
0x140012c51  test    eax, eax
0x140012c53  jz      short loc_140012C74
0x140012c55  mov     r9, [r14+0A38h]
0x140012c5c  lea     r8, [rbp+57h+var_50]; struct _GUID *
0x140012c60  add     r9, 1338h; struct _GUID *
0x140012c67  mov     dword ptr [rsp+0F0h+var_C0], 3; char
0x140012c6f  call    ?EtwEx_tidActivityInfoTransfer@@YAK_KPEBU_EVENT_DESCRIPTOR@@PEBU_GUID@@2E2K@Z; EtwEx_tidActivityInfoTransfer(unsigned __int64,_EVENT_DESCRIPTOR const *,_GUID const *,_GUID const *,uchar,_GUID const *,ulong)
0x140012c74  lea     rcx, [rsi+28h]; Csq
0x140012c78  mov     dword ptr [rbp+57h+var_78], 2
0x140012c7f  mov     qword ptr [rbp+57h+var_68], r13
0x140012c83  lea     rdx, [rbp+57h+var_78]; struct DOT11_AUTH_UPCALL_REQUEST *
0x140012c87  mov     eax, [rcx+78h]
0x140012c8a  mov     dword ptr [rbp+57h+var_78+8], eax
0x140012c8d  call    ?NwfUpcallMsg@@YAJPEAUNWF_AUTH_UPCALL@@PEBUDOT11_AUTH_UPCALL_REQUEST@@@Z; NwfUpcallMsg(NWF_AUTH_UPCALL *,DOT11_AUTH_UPCALL_REQUEST const *)
0x140012c92  mov     ebx, eax
0x140012c94  mov     rcx, [r14+0A38h]
0x140012c9b  mov     rdx, rdi; LockState
0x140012c9e  mov     rcx, [rcx+90h]; Lock
0x140012ca5  call    cs:__imp_NdisReleaseRWLock
0x140012cac  nop     dword ptr [rax+rax+00h]
0x140012cb1  mov     rcx, [r14+0A38h]
0x140012cb8  xor     r8d, r8d; Flags
0x140012cbb  mov     rdx, rdi; LockState
0x140012cbe  mov     rcx, [rcx+90h]; Lock
0x140012cc5  call    cs:__imp_NdisAcquireRWLockRead
0x140012ccc  nop     dword ptr [rax+rax+00h]
0x140012cd1  jmp     loc_140013085
0x140012cd6  mov     rdx, cs:WPP_GLOBAL_Control
0x140012cdd  lea     rax, WPP_GLOBAL_Control
0x140012ce4  cmp     rdx, rax
0x140012ce7  jz      loc_140013080
0x140012ced  cmp     byte ptr [rdx+29h], 2
0x140012cf1  jb      loc_140013080
  ... truncated ...
```
