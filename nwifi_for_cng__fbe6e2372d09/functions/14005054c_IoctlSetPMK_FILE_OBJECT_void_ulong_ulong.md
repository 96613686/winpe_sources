# IoctlSetPMK(_FILE_OBJECT *,void *,ulong,ulong *)

- ea: `0x14005054c`
- end: `0x140050ccc`
- name: `?IoctlSetPMK@@YAJPEAU_FILE_OBJECT@@PEAXKPEAK@Z`
- size: `1920`
- prototype: `__int64 __fastcall(struct _FILE_OBJECT *, char *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140033a14`

## callees

- `0x14000a81c`
- `0x14000d21c`
- `0x1400208f0`
- `0x140020dc0`
- `0x140020f20`
- `0x1400252ac`
- `0x140025704`
- `0x14002f44c`
- `0x1400314ec`
- `0x140032d88`
- `0x140036ca0`
- `0x14003b04c`
- `0x14003b0e8`
- `0x140043158`
- `0x1400447e0`
- `0x14005054c`
- `0x140053f30`
- `0x140053f88`
- `0x1400554d0`
- `0x140091f30`
- `0x14009bcc0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140050892`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140050892`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400506fa`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400506fa`
- `NDIS!NdisReleaseRWLock` at `0x1400508ef`
- `NDIS!NdisReleaseRWLock` at `0x1400508ef`

## pseudocode

```c
__int64 __fastcall IoctlSetPMK(struct _FILE_OBJECT *a1, char *a2, unsigned int a3, unsigned int *a4)
{
  _QWORD *FsContext; // r14
  int v8; // esi
  __int64 v9; // r9
  char *v10; // r12
  __int64 v11; // r9
  struct _VELAN *v12; // r14
  unsigned int v13; // edx
  int v14; // ecx
  struct DOT11_MAC_STATE_ENTRY **v15; // rcx
  struct DOT11_MAC_STATE_ENTRY *pDefaultMacState; // rdi
  _DWORD *v17; // r13
  char *v18; // rax
  NWF_PMK_ENTRY *pPmk; // r12
  NWF_FT_CONTEXT *pFTContext; // rax
  char *v21; // rdx
  size_t v22; // rcx
  unsigned int v23; // eax
  _DEVICE_OBJECT *AttachedDevice; // rcx
  size_t v25; // [rsp+20h] [rbp-30h]
  _QWORD v26[2]; // [rsp+40h] [rbp-10h] BYREF
  struct DOT11_MAC_STATE_ENTRY *v27; // [rsp+90h] [rbp+40h] BYREF
  size_t Size; // [rsp+A0h] [rbp+50h]
  unsigned int *LockState; // [rsp+A8h] [rbp+58h] BYREF

  LockState = a4;
  LODWORD(Size) = a3;
  FsContext = a1->FsContext;
  LOBYTE(LockState) = 0;
  *(_WORD *)((char *)&LockState + 1) = 0;
  if ( !FsContext )
    return 3221225488LL;
  if ( a3 < 0x9C )
  {
    v8 = -1073741811;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 339, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, a3, 156);
    goto LABEL_86;
  }
  v9 = *(unsigned int *)a2;
  if ( (_DWORD)v9 != 1 )
  {
    v8 = -1073741811;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 340, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, v9, 1);
    goto LABEL_86;
  }
  if ( *((_DWORD *)a2 + 29) > 0x20u || *((_DWORD *)a2 + 11) > 0x41u )
  {
    v8 = -1073741811;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_ddddd(WPP_GLOBAL_Control->AttachedDevice, 341, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids);
    goto LABEL_86;
  }
  v10 = a2 + 8;
  if ( (a2[8] & 1) != 0 )
  {
    if ( *(_DWORD *)v10 != -1 || *((_WORD *)a2 + 6) != 0xFFFF )
    {
      v8 = -1073741811;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF__MAC__MAC_(
          WPP_GLOBAL_Control->AttachedDevice,
          342,
          (unsigned int)WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
          (_DWORD)v10,
          (__int64)&dword_1400A31D4);
      goto LABEL_86;
    }
    v11 = *(_QWORD *)(a2 + 20);
    if ( v11 != -1 )
    {
      v8 = -1073741811;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 343, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, v11, -1);
      goto LABEL_86;
    }
  }
  v12 = (struct _VELAN *)FsContext[2];
  NdisAcquireRWLockWrite(v12->pRWLock, (PLOCK_STATE_EX)&LockState, 0);
  if ( v12->pSecurityEndpoint == a1 || v12->pMSSecurityEndpoint == a1 )
  {
    v8 = 0;
    if ( (*v10 & 1) != 0 )
    {
      pDefaultMacState = v12->pDefaultMacState;
      v17 = a2 + 44;
      v27 = pDefaultMacState;
    }
    else
    {
      v15 = (struct DOT11_MAC_STATE_ENTRY **)&v12->MacStateTable.Hash.Buckets[((unsigned __int8)v10[4]
                                                                             ^ (unsigned __int8)v10[5])
                                                                            & 0x800000FF];
      for ( pDefaultMacState = *v15;
            v15 != (struct DOT11_MAC_STATE_ENTRY **)pDefaultMacState;
            pDefaultMacState = (struct DOT11_MAC_STATE_ENTRY *)pDefaultMacState->MacHashEntry.Linkage.Flink )
      {
        if ( *(_DWORD *)pDefaultMacState->MacHashEntry.MacKey == *(_DWORD *)v10
          && *(_WORD *)&pDefaultMacState->MacHashEntry.MacKey[4] == *((_WORD *)v10 + 2) )
        {
          goto LABEL_35;
        }
      }
      pDefaultMacState = 0;
LABEL_35:
      v27 = pDefaultMacState;
      v17 = a2 + 44;
      if ( !pDefaultMacState )
      {
        if ( !*v17 )
        {
LABEL_48:
          if ( pDefaultMacState )
            Dot11DecObjCnt(&v27, v13);
          goto LABEL_50;
        }
        v8 = Dot11AddMacState(&v12->MacStateTable, (const unsigned __int8 (*)[6])v10, &v27);
        if ( v8 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 345, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids);
          pDefaultMacState = v27;
          goto LABEL_48;
        }
        pDefaultMacState = v27;
      }
    }
    Dot11FlushPMKIDCache(v12, pDefaultMacState);
    if ( !pDefaultMacState->pPmk )
    {
      v17 = a2 + 44;
      if ( !*((_DWORD *)a2 + 11) )
        goto LABEL_74;
      ++pDefaultMacState->uObjCnt;
      _InterlockedIncrement((volatile signed __int32 *)&pDefaultMacState->uRefCnt);
      pDefaultMacState->pPmk = 0;
      v18 = (char *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead);
      if ( !v18 )
      {
        v8 = -1073741670;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 346, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, 216);
        goto LABEL_48;
      }
      *(_QWORD *)v18 = &WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      *((_DWORD *)v18 + 2) = 2053731191;
      v8 = 0;
      pDefaultMacState->pPmk = (NWF_PMK_ENTRY *)(v18 + 16);
      memset(v18 + 16, 0, 0xD8u);
    }
    if ( *v17 )
    {
      pPmk = pDefaultMacState->pPmk;
      pPmk->ullExpiry = *(_QWORD *)(a2 + 20);
      pPmk->AuthAlgo = v12->KeyContext.AuthAlgo;
      if ( (unsigned int)Feature_60009473__private_IsEnabledDeviceUsageNoInline() )
        pPmk->PMKFlags.ulValue = *((_DWORD *)a2 + 1);
      pFTContext = v12->KeyContext.pFTContext;
      if ( pFTContext )
      {
        pPmk->MDID = pFTContext->MDID;
        pPmk->uTKLength = v12->KeyContext.pFTContext->uTKLength;
      }
      LODWORD(v25) = *v17;
      PmkCacheUpdatePmkForFullAuth(&v12->Dot11PmkCache, v25, a2 + 48);
      SAERequestCleanupConnection(v12, 70);
      v21 = a2 + 48;
      v22 = *((unsigned int *)a2 + 11);
      if ( (*((_DWORD *)a2 + 1) & 2) != 0 )
      {
        pPmk->PassphraseLength = v22;
        memmove(pPmk->Passphrase, v21, (unsigned int)*v17);
      }
      else
      {
        pPmk->uSendKeyLength = v22;
        memmove(&pPmk->149, v21, v22);
        v23 = *((_DWORD *)a2 + 29);
        pPmk->uRecvKeyLength = v23;
        memmove(pPmk->ucRecvKey, a2 + 120, v23);
        *(_OWORD *)pPmk->PMKID = *(_OWORD *)(a2 + 28);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        WPP_SF__MAC_(
          WPP_GLOBAL_Control->AttachedDevice,
          347,
          WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
          pDefaultMacState->MacHashEntry.MacKey);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 348, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, pPmk->MDID);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
            v26[0] = 16;
            v26[1] = pPmk->PMKID;
            WPP_SF__HEX_(AttachedDevice, 349, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, v26);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              WPP_SF_q(
                WPP_GLOBAL_Control->AttachedDevice,
                350,
                WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
                pPmk->ullExpiry);
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  351,
                  WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
                  (unsigned int)pPmk->AuthAlgo);
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    352,
                    WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
                    (*((_DWORD *)a2 + 1) >> 1) & 1);
              }
            }
          }
        }
      }
      if ( (unsigned int)Feature_60009473__private_IsEnabledDeviceUsageNoInline()
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          353,
          WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
          pPmk->PMKFlags.ulValue);
      }
      if ( v12->KeyContext.bAccept1XPacket )
      {
        if ( (*((_DWORD *)pDefaultMacState + 10) & 2) != 0 )
        {
          v12->KeyContext.bReplayCounterAvailable = 0;
          v12->KeyContext.bFastRoaming = 0;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            WPP_SF__MAC_(
              WPP_GLOBAL_Control->AttachedDevice,
              354,
              WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
              pDefaultMacState->MacHashEntry.MacKey);
        }
      }
LABEL_78:
      if ( v12->KeyContext.M1Cache.pEapolHdr && *v17 && v12->KeyContext.M1Cache.pMacStateEntry == pDefaultMacState )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 356, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids);
        Dot11ReceiveM1(v12, v12->KeyContext.M1Cache.pMacStateEntry, v12->KeyContext.M1Cache.pEapolHdr, &LockState);
      }
      goto LABEL_50;
    }
LABEL_74:
    if ( (unsigned int)Feature_Bugfix_53850044__private_IsEnabledDeviceUsageNoInline()
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      WPP_SF__MAC_(
        WPP_GLOBAL_Control->AttachedDevice,
        355,
        WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
        pDefaultMacState->MacHashEntry.MacKey);
    }
    DeletePMK(pDefaultMacState);
    goto LABEL_78;
  }
  v8 = -1073741757;
  if ( v12->pIHVSecurityEndpoint != a1 )
    v8 = -1073741790;
  if ( (byte_1400B2802 & 1) != 0 )
    McTemplateK0pjq_EtwWriteTransfer(
      v14,
      (unsigned int)RejectSetPMK,
      (_DWORD)v12 + 4920,
      (_DWORD)v12,
      (__int64)&v12->gDeviceId,
      v8);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 344, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids);
LABEL_50:
  NdisReleaseRWLock(v12->pRWLock, (PLOCK_STATE_EX)&LockState);
LABEL_86:
  memset(a2, 0, (unsigned int)Size);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14005054c  mov     [rsp-38h+arg_8], rbx
0x140050551  mov     [rsp-38h+LockState], r9
0x140050556  mov     dword ptr [rsp-38h+Size], r8d
0x14005055b  push    rbp
0x14005055c  push    rsi
0x14005055d  push    rdi
0x14005055e  push    r12
0x140050560  push    r13
0x140050562  push    r14
0x140050564  push    r15
0x140050566  mov     rbp, rsp
0x140050569  sub     rsp, 50h
0x14005056d  mov     r14, [rcx+18h]
0x140050571  mov     rbx, rcx
0x140050574  xor     ecx, ecx
0x140050576  mov     byte ptr [rbp+LockState], 0
0x14005057a  mov     word ptr [rbp+LockState+1], cx
0x14005057e  mov     eax, r8d
0x140050581  mov     r15, rdx
0x140050584  test    r14, r14
0x140050587  jnz     short loc_140050593
0x140050589  mov     eax, 0C0000010h
0x14005058e  jmp     loc_140050CB3
0x140050593  mov     r8d, 9Ch
0x140050599  cmp     eax, r8d
0x14005059c  jnb     short loc_1400505DC
0x14005059e  mov     esi, 0C000000Dh
0x1400505a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400505aa  lea     rbx, WPP_GLOBAL_Control
0x1400505b1  cmp     rcx, rbx
0x1400505b4  jz      loc_140050CA3
0x1400505ba  mov     edx, 153h
0x1400505bf  mov     dword ptr [rsp+50h+var_30], r8d
0x1400505c4  mov     r9d, eax
0x1400505c7  mov     rcx, [rcx+18h]
0x1400505cb  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x1400505d2  call    WPP_SF_Dd
0x1400505d7  jmp     loc_140050CA3
0x1400505dc  mov     r9d, [rdx]
0x1400505df  mov     edi, 1
0x1400505e4  cmp     r9d, edi
0x1400505e7  jz      short loc_140050610
0x1400505e9  mov     esi, 0C000000Dh
0x1400505ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1400505f5  lea     rbx, WPP_GLOBAL_Control
0x1400505fc  cmp     rcx, rbx
0x1400505ff  jz      loc_140050CA3
0x140050605  mov     edx, 154h
0x14005060a  mov     dword ptr [rsp+50h+var_30], edi
0x14005060e  jmp     short loc_1400505C7
0x140050610  mov     r9d, [rdx+74h]
0x140050614  cmp     r9d, 20h ; ' '
0x140050618  ja      loc_140050C56
0x14005061e  mov     ecx, [rdx+2Ch]
0x140050621  mov     eax, [rdx+4]
0x140050624  cmp     ecx, 41h ; 'A'
0x140050627  ja      loc_140050C56
0x14005062d  lea     r12, [rdx+8]
0x140050631  test    [r12], dil
0x140050635  jz      loc_1400506E8
0x14005063b  mov     eax, [r12]
0x14005063f  cmp     eax, cs:dword_1400A31D4
0x140050645  jnz     short loc_1400506A3
0x140050647  movzx   eax, word ptr [r12+4]
0x14005064d  cmp     ax, cs:word_1400A31D8
0x140050654  jnz     short loc_1400506A3
0x140050656  mov     r9, [rdx+14h]
0x14005065a  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x14005065e  jz      loc_1400506E8
0x140050664  mov     esi, 0C000000Dh
0x140050669  mov     rcx, cs:WPP_GLOBAL_Control
0x140050670  lea     rbx, WPP_GLOBAL_Control
0x140050677  cmp     rcx, rbx
0x14005067a  jz      loc_140050CA3
0x140050680  mov     rcx, [rcx+18h]
0x140050684  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14005068b  mov     edx, 157h
0x140050690  mov     [rsp+50h+var_30], 0FFFFFFFFFFFFFFFFh
0x140050699  call    WPP_SF_qq
0x14005069e  jmp     loc_140050CA3
0x1400506a3  mov     esi, 0C000000Dh
0x1400506a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400506af  lea     rbx, WPP_GLOBAL_Control
0x1400506b6  cmp     rcx, rbx
0x1400506b9  jz      loc_140050CA3
0x1400506bf  mov     rcx, [rcx+18h]
0x1400506c3  lea     rax, dword_1400A31D4
0x1400506ca  mov     edx, 156h
0x1400506cf  mov     [rsp+50h+var_30], rax
0x1400506d4  mov     r9, r12
0x1400506d7  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x1400506de  call    WPP_SF__MAC__MAC_
0x1400506e3  jmp     loc_140050CA3
0x1400506e8  mov     r14, [r14+10h]
0x1400506ec  lea     rdx, [rbp+LockState]; LockState
0x1400506f0  xor     r8d, r8d; Flags
0x1400506f3  mov     rcx, [r14+90h]; Lock
0x1400506fa  call    cs:__imp_NdisAcquireRWLockWrite
0x140050701  nop     dword ptr [rax+rax+00h]
0x140050706  cmp     [r14+1700h], rbx
0x14005070d  jz      short loc_140050783
0x14005070f  cmp     [r14+16F0h], rbx
0x140050716  jz      short loc_140050783
0x140050718  cmp     [r14+16F8h], rbx
0x14005071f  mov     esi, 0C0000043h
0x140050724  lea     eax, [rsi-21h]
0x140050727  cmovnz  esi, eax
0x14005072a  test    cs:byte_1400B2802, dil
0x140050731  jz      short loc_140050752
0x140050733  lea     r8, [r14+1338h]
0x14005073a  mov     dword ptr [rsp+50h+Src], esi
0x14005073e  mov     r9, r14
0x140050741  mov     [rsp+50h+var_30], r8
0x140050746  lea     rdx, RejectSetPMK
0x14005074d  call    McTemplateK0pjq_EtwWriteTransfer
0x140050752  mov     rcx, cs:WPP_GLOBAL_Control
0x140050759  lea     rbx, WPP_GLOBAL_Control
0x140050760  cmp     rcx, rbx
0x140050763  jz      loc_1400508E4
0x140050769  mov     rcx, [rcx+18h]
0x14005076d  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x140050774  mov     edx, 158h
0x140050779  call    WPP_SF_
0x14005077e  jmp     loc_1400508E4
0x140050783  xor     esi, esi
0x140050785  test    [r12], dil
0x140050789  jnz     loc_140050845
0x14005078f  movzx   ecx, byte ptr [r12+5]
0x140050795  movzx   eax, byte ptr [r12+4]
0x14005079b  xor     ecx, eax
0x14005079d  and     ecx, 800000FFh
0x1400507a3  jge     short loc_1400507AF
0x1400507a5  sub     ecx, edi
0x1400507a7  or      ecx, 0FFFFFF00h
0x1400507ad  add     ecx, edi
0x1400507af  add     rcx, 0Ah
0x1400507b3  shl     rcx, 4
0x1400507b7  add     rcx, r14
0x1400507ba  mov     rdi, [rcx]
0x1400507bd  jmp     short loc_1400507D7
0x1400507bf  mov     eax, [rdi+10h]
0x1400507c2  cmp     eax, [r12]
0x1400507c6  jnz     short loc_1400507D4
0x1400507c8  movzx   eax, word ptr [rdi+14h]
0x1400507cc  cmp     ax, [r12+4]
0x1400507d2  jz      short loc_1400507DE
0x1400507d4  mov     rdi, [rdi]
0x1400507d7  cmp     rcx, rdi
0x1400507da  jnz     short loc_1400507BF
0x1400507dc  xor     edi, edi
0x1400507de  mov     [rbp+arg_0], rdi
0x1400507e2  lea     r13, [r15+2Ch]
0x1400507e6  test    rdi, rdi
0x1400507e9  jnz     short loc_140050854
0x1400507eb  cmp     [r13+0], esi
0x1400507ef  jz      loc_1400508D6
0x1400507f5  lea     rcx, [r14+0A0h]; struct DOT11_MAC_STATE_MODULE *
0x1400507fc  mov     rdx, r12; unsigned __int8 (*)[6]
0x1400507ff  lea     r8, [rbp+arg_0]; struct DOT11_MAC_STATE_ENTRY **
0x140050803  call    ?Dot11AddMacState@@YAHPEAUDOT11_MAC_STATE_MODULE@@PEAY05$$CBEPEAPEAUDOT11_MAC_STATE_ENTRY@@@Z; Dot11AddMacState(DOT11_MAC_STATE_MODULE *,uchar const (*)[6],DOT11_MAC_STATE_ENTRY * *)
0x140050808  mov     esi, eax
0x14005080a  test    eax, eax
0x14005080c  jns     short loc_14005083F
0x14005080e  mov     rcx, cs:WPP_GLOBAL_Control
0x140050815  lea     rbx, WPP_GLOBAL_Control
0x14005081c  cmp     rcx, rbx
0x14005081f  jz      short loc_140050836
0x140050821  mov     rcx, [rcx+18h]
0x140050825  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14005082c  mov     edx, 159h
0x140050831  call    WPP_SF_
0x140050836  mov     rdi, [rbp+arg_0]
0x14005083a  jmp     loc_1400508D6
0x14005083f  mov     rdi, [rbp+arg_0]
0x140050843  jmp     short loc_140050854
0x140050845  mov     rdi, [r14+10D0h]
0x14005084c  lea     r13, [r15+2Ch]
0x140050850  mov     [rbp+arg_0], rdi
0x140050854  mov     rdx, rdi; struct DOT11_MAC_STATE_ENTRY *
0x140050857  mov     rcx, r14; struct _VELAN *
0x14005085a  call    ?Dot11FlushPMKIDCache@@YAJPEAU_VELAN@@PEAUDOT11_MAC_STATE_ENTRY@@@Z; Dot11FlushPMKIDCache(_VELAN *,DOT11_MAC_STATE_ENTRY *)
0x14005085f  cmp     qword ptr [rdi+68h], 0
0x140050864  jnz     loc_140050921
0x14005086a  lea     r13, [r15+2Ch]
0x14005086e  cmp     dword ptr [r13+0], 0
0x140050873  jz      loc_140050BB2
0x140050879  inc     dword ptr [rdi+20h]
0x14005087c  lock inc dword ptr [rdi+24h]
0x140050880  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140050887  mov     qword ptr [rdi+68h], 0
0x14005088f  mov     rcx, rbx; Lookaside
0x140050892  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140050899  nop     dword ptr [rax+rax+00h]
0x14005089e  test    rax, rax
0x1400508a1  jnz     short loc_140050900
0x1400508a3  mov     esi, 0C000009Ah
0x1400508a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400508af  lea     rbx, WPP_GLOBAL_Control
0x1400508b6  cmp     rcx, rbx
0x1400508b9  jz      short loc_1400508D6
0x1400508bb  mov     rcx, [rcx+18h]
0x1400508bf  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x1400508c6  mov     edx, 15Ah
0x1400508cb  mov     r9d, 0D8h
0x1400508d1  call    WPP_SF_d
0x1400508d6  test    rdi, rdi
0x1400508d9  jz      short loc_1400508E4
0x1400508db  lea     rcx, [rbp+arg_0]; struct DOT11_MAC_STATE_ENTRY **
0x1400508df  call    ?Dot11DecObjCnt@@YAXPEAPEAUDOT11_MAC_STATE_ENTRY@@K@Z; Dot11DecObjCnt(DOT11_MAC_STATE_ENTRY * *,ulong)
0x1400508e4  mov     rcx, [r14+90h]; Lock
0x1400508eb  lea     rdx, [rbp+LockState]; LockState
0x1400508ef  call    cs:__imp_NdisReleaseRWLock
0x1400508f6  nop     dword ptr [rax+rax+00h]
0x1400508fb  jmp     loc_140050CA3
0x140050900  lea     rcx, [rax+10h]; void *
0x140050904  mov     [rax], rbx
0x140050907  mov     dword ptr [rax+8], 7A697377h
0x14005090e  xor     esi, esi
0x140050910  xor     edx, edx; Val
0x140050912  mov     [rdi+68h], rcx
0x140050916  mov     r8d, 0D8h; Size
0x14005091c  call    memset
0x140050921  cmp     dword ptr [r13+0], 0
0x140050926  jz      loc_140050BB2
0x14005092c  mov     rax, [r15+14h]
0x140050930  mov     r12, [rdi+68h]
0x140050934  mov     [r12+10h], rax
0x140050939  mov     eax, [r14+171Ch]
0x140050940  mov     [r12], eax
0x140050944  call    Feature_60009473__private_IsEnabledDeviceUsageNoInline
0x140050949  test    eax, eax
0x14005094b  jz      short loc_140050956
0x14005094d  mov     eax, [r15+4]
0x140050951  mov     [r12+0Ch], eax
0x140050956  mov     rax, [r14+1C20h]
0x14005095d  test    rax, rax
0x140050960  jz      short loc_14005097E
0x140050962  movzx   eax, word ptr [rax+24h]
0x140050966  mov     [r12+4], ax
0x14005096c  mov     rax, [r14+1C20h]
0x140050973  mov     ecx, [rax+88h]
0x140050979  mov     [r12+8], ecx
0x14005097e  mov     r9d, [r15+4]
0x140050982  lea     rbx, [r15+30h]
0x140050986  mov     eax, [r13+0]
0x14005098a  lea     r8, [rdi+10h]
0x14005098e  mov     edx, [r14+1718h]
0x140050995  lea     rcx, [r14+1FE8h]; struct _DOT11_PMK_CACHE *
0x14005099c  shr     r9d, 0Ch
0x1400509a0  and     r9b, 1
0x1400509a4  mov     [rsp+50h+Src], rbx; Src
0x1400509a9  mov     dword ptr [rsp+50h+var_30], eax; Size
0x1400509ad  call    PmkCacheUpdatePmkForFullAuth
0x1400509b2  mov     edx, 46h ; 'F'
0x1400509b7  mov     rcx, r14
0x1400509ba  call    ?SAERequestCleanupConnection@@YAXPEAU_VELAN@@W4_DOT11_SAE_STATUS@@@Z; SAERequestCleanupConnection(_VELAN *,_DOT11_SAE_STATUS)
0x1400509bf  mov     eax, [r15+4]
0x1400509c3  mov     rdx, rbx; Src
0x1400509c6  mov     ecx, [r15+2Ch]
0x1400509ca  test    al, 2
0x1400509cc  jz      short loc_1400509E3
0x1400509ce  mov     [r12+2Ch], ecx
0x1400509d3  lea     rcx, [r12+54h]; void *
0x1400509d8  mov     r8d, [r13+0]; Size
0x1400509dc  call    memmove
0x1400509e1  jmp     short loc_140050A1E
0x1400509e3  mov     [r12+30h], ecx
0x1400509e8  mov     r8, rcx; Size
0x1400509eb  lea     rcx, [r12+95h]; void *
0x1400509f3  call    memmove
0x1400509f8  mov     eax, [r15+74h]
0x1400509fc  lea     rdx, [r15+78h]; Src
0x140050a00  mov     r8d, eax; Size
0x140050a03  mov     [r12+28h], eax
0x140050a08  lea     rcx, [r12+34h]; void *
0x140050a0d  call    memmove
0x140050a12  movups  xmm0, xmmword ptr [r15+1Ch]
0x140050a17  movdqu  xmmword ptr [r12+18h], xmm0
0x140050a1e  mov     rcx, cs:WPP_GLOBAL_Control
0x140050a25  lea     rbx, WPP_GLOBAL_Control
0x140050a2c  cmp     rcx, rbx
0x140050a2f  jz      loc_140050B3B
0x140050a35  mov     rcx, [rcx+18h]
0x140050a39  lea     r9, [rdi+10h]
0x140050a3d  mov     edx, 15Bh
0x140050a42  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x140050a49  call    WPP_SF__MAC_
0x140050a4e  mov     rcx, cs:WPP_GLOBAL_Control
0x140050a55  cmp     rcx, rbx
0x140050a58  jz      loc_140050B3B
0x140050a5e  movzx   r9d, word ptr [r12+4]
0x140050a64  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x140050a6b  mov     rcx, [rcx+18h]
0x140050a6f  mov     edx, 15Ch
0x140050a74  call    WPP_SF_d
0x140050a79  mov     rcx, cs:WPP_GLOBAL_Control
0x140050a80  cmp     rcx, rbx
0x140050a83  jz      loc_140050B3B
0x140050a89  mov     rcx, [rcx+18h]
0x140050a8d  lea     r9, [rbp+var_10]
  ... truncated ...
```
