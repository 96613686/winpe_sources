# IoctlSetPMK(_FILE_OBJECT *,void *,ulong,ulong *)

- ea: `0x14004ed8c`
- end: `0x14004f503`
- name: `?IoctlSetPMK@@YAJPEAU_FILE_OBJECT@@PEAXKPEAK@Z`
- size: `1911`
- prototype: `__int64 __fastcall(struct _FILE_OBJECT *, char *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400337f4`

## callees

- `0x14000a82c`
- `0x14000d22c`
- `0x1400208f0`
- `0x140020dc0`
- `0x140020f20`
- `0x140025028`
- `0x140025480`
- `0x14002f1bc`
- `0x14003125c`
- `0x140032b68`
- `0x140036a80`
- `0x14003ae2c`
- `0x14003aec8`
- `0x1400425d8`
- `0x140043c60`
- `0x14004ed8c`
- `0x140052768`
- `0x140053cb0`
- `0x140090750`
- `0x14009a4c0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004f0d2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004f0d2`
- `NDIS!NdisAcquireRWLockWrite` at `0x14004ef3a`
- `NDIS!NdisAcquireRWLockWrite` at `0x14004ef3a`
- `NDIS!NdisReleaseRWLock` at `0x14004f12f`
- `NDIS!NdisReleaseRWLock` at `0x14004f12f`

## pseudocode

```c
__int64 __fastcall IoctlSetPMK(struct _FILE_OBJECT *a1, char *a2, unsigned int a3, unsigned int *a4)
{
  _QWORD *FsContext; // r14
  int v8; // esi
  __int64 v9; // r9
  char *v10; // r12
  struct _VELAN *v11; // r14
  unsigned int v12; // edx
  int v13; // ecx
  struct DOT11_MAC_STATE_ENTRY **v14; // rcx
  struct DOT11_MAC_STATE_ENTRY *pDefaultMacState; // rdi
  _DWORD *v16; // r13
  char *v17; // rax
  NWF_PMK_ENTRY *pPmk; // r12
  NWF_FT_CONTEXT *pFTContext; // rax
  char *v20; // rdx
  size_t v21; // rcx
  unsigned int v22; // eax
  _DEVICE_OBJECT *AttachedDevice; // rcx
  size_t v24; // [rsp+20h] [rbp-30h]
  _QWORD v25[2]; // [rsp+40h] [rbp-10h] BYREF
  struct DOT11_MAC_STATE_ENTRY *v26; // [rsp+90h] [rbp+40h] BYREF
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
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 339, WPP_e90d411d816e312466897e39e745b158_Traceguids, a3, 156);
    goto LABEL_85;
  }
  v9 = *(unsigned int *)a2;
  if ( (_DWORD)v9 != 1 )
  {
    v8 = -1073741811;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 340, WPP_e90d411d816e312466897e39e745b158_Traceguids, v9, 1);
    goto LABEL_85;
  }
  if ( *((_DWORD *)a2 + 29) > 0x20u || *((_DWORD *)a2 + 11) > 0x41u )
  {
    v8 = -1073741811;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_ddddd(WPP_GLOBAL_Control->AttachedDevice, 341, WPP_e90d411d816e312466897e39e745b158_Traceguids);
    goto LABEL_85;
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
          (unsigned int)WPP_e90d411d816e312466897e39e745b158_Traceguids,
          (_DWORD)v10,
          (__int64)&dword_1400A1094);
      goto LABEL_85;
    }
    if ( *(_QWORD *)(a2 + 20) != -1 )
    {
      v8 = -1073741811;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 343, WPP_e90d411d816e312466897e39e745b158_Traceguids);
      goto LABEL_85;
    }
  }
  v11 = (struct _VELAN *)FsContext[2];
  NdisAcquireRWLockWrite(v11->pRWLock, (PLOCK_STATE_EX)&LockState, 0);
  if ( v11->pSecurityEndpoint == a1 || v11->pMSSecurityEndpoint == a1 )
  {
    v8 = 0;
    if ( (*v10 & 1) != 0 )
    {
      pDefaultMacState = v11->pDefaultMacState;
      v16 = a2 + 44;
      v26 = pDefaultMacState;
    }
    else
    {
      v14 = (struct DOT11_MAC_STATE_ENTRY **)&v11->MacStateTable.Hash.Buckets[((unsigned __int8)v10[4]
                                                                             ^ (unsigned __int8)v10[5])
                                                                            & 0x800000FF];
      for ( pDefaultMacState = *v14;
            v14 != (struct DOT11_MAC_STATE_ENTRY **)pDefaultMacState;
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
      v26 = pDefaultMacState;
      v16 = a2 + 44;
      if ( !pDefaultMacState )
      {
        if ( !*v16 )
        {
LABEL_48:
          if ( pDefaultMacState )
            Dot11DecObjCnt(&v26, v12);
          goto LABEL_50;
        }
        v8 = Dot11AddMacState(&v11->MacStateTable, (const unsigned __int8 (*)[6])v10, &v26);
        if ( v8 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 345, WPP_e90d411d816e312466897e39e745b158_Traceguids);
          pDefaultMacState = v26;
          goto LABEL_48;
        }
        pDefaultMacState = v26;
      }
    }
    Dot11FlushPMKIDCache(v11, pDefaultMacState);
    if ( !pDefaultMacState->pPmk )
    {
      v16 = a2 + 44;
      if ( !*((_DWORD *)a2 + 11) )
        goto LABEL_74;
      ++pDefaultMacState->uObjCnt;
      _InterlockedIncrement((volatile signed __int32 *)&pDefaultMacState->uRefCnt);
      pDefaultMacState->pPmk = 0;
      v17 = (char *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead);
      if ( !v17 )
      {
        v8 = -1073741670;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 346, WPP_e90d411d816e312466897e39e745b158_Traceguids, 216);
        goto LABEL_48;
      }
      *(_QWORD *)v17 = &WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      *((_DWORD *)v17 + 2) = 2053731191;
      v8 = 0;
      pDefaultMacState->pPmk = (NWF_PMK_ENTRY *)(v17 + 16);
      memset(v17 + 16, 0, 0xD8u);
    }
    if ( *v16 )
    {
      pPmk = pDefaultMacState->pPmk;
      pPmk->ullExpiry = *(_QWORD *)(a2 + 20);
      pPmk->AuthAlgo = v11->KeyContext.AuthAlgo;
      if ( (unsigned int)Feature_60009473__private_IsEnabledDeviceUsageNoInline() )
        pPmk->PMKFlags.ulValue = *((_DWORD *)a2 + 1);
      pFTContext = v11->KeyContext.pFTContext;
      if ( pFTContext )
      {
        pPmk->MDID = pFTContext->MDID;
        pPmk->uTKLength = v11->KeyContext.pFTContext->uTKLength;
      }
      LODWORD(v24) = *v16;
      PmkCacheUpdatePmkForFullAuth(&v11->Dot11PmkCache, v24, a2 + 48);
      SAERequestCleanupConnection(v11, 70);
      v20 = a2 + 48;
      v21 = *((unsigned int *)a2 + 11);
      if ( (*((_DWORD *)a2 + 1) & 2) != 0 )
      {
        pPmk->PassphraseLength = v21;
        memmove(pPmk->Passphrase, v20, (unsigned int)*v16);
      }
      else
      {
        pPmk->uSendKeyLength = v21;
        memmove(&pPmk->149, v20, v21);
        v22 = *((_DWORD *)a2 + 29);
        pPmk->uRecvKeyLength = v22;
        memmove(pPmk->ucRecvKey, a2 + 120, v22);
        *(_OWORD *)pPmk->PMKID = *(_OWORD *)(a2 + 28);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        WPP_SF__MAC_(
          WPP_GLOBAL_Control->AttachedDevice,
          347,
          WPP_e90d411d816e312466897e39e745b158_Traceguids,
          pDefaultMacState->MacHashEntry.MacKey);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 348, WPP_e90d411d816e312466897e39e745b158_Traceguids, pPmk->MDID);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
            v25[0] = 16;
            v25[1] = pPmk->PMKID;
            WPP_SF__HEX_(AttachedDevice, 349, WPP_e90d411d816e312466897e39e745b158_Traceguids, v25);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              WPP_SF_q(
                WPP_GLOBAL_Control->AttachedDevice,
                350,
                WPP_e90d411d816e312466897e39e745b158_Traceguids,
                pPmk->ullExpiry);
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  351,
                  WPP_e90d411d816e312466897e39e745b158_Traceguids,
                  (unsigned int)pPmk->AuthAlgo);
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    352,
                    WPP_e90d411d816e312466897e39e745b158_Traceguids,
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
          WPP_e90d411d816e312466897e39e745b158_Traceguids,
          pPmk->PMKFlags.ulValue);
      }
      if ( v11->KeyContext.bAccept1XPacket )
      {
        if ( (*((_DWORD *)pDefaultMacState + 10) & 2) != 0 )
        {
          v11->KeyContext.bReplayCounterAvailable = 0;
          v11->KeyContext.bFastRoaming = 0;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            WPP_SF__MAC_(
              WPP_GLOBAL_Control->AttachedDevice,
              354,
              WPP_e90d411d816e312466897e39e745b158_Traceguids,
              pDefaultMacState->MacHashEntry.MacKey);
        }
      }
LABEL_77:
      if ( v11->KeyContext.M1Cache.pEapolHdr && *v16 && v11->KeyContext.M1Cache.pMacStateEntry == pDefaultMacState )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 356, WPP_e90d411d816e312466897e39e745b158_Traceguids);
        Dot11ReceiveM1(v11, v11->KeyContext.M1Cache.pMacStateEntry, v11->KeyContext.M1Cache.pEapolHdr, &LockState);
      }
      goto LABEL_50;
    }
LABEL_74:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF__MAC_(
        WPP_GLOBAL_Control->AttachedDevice,
        355,
        WPP_e90d411d816e312466897e39e745b158_Traceguids,
        pDefaultMacState->MacHashEntry.MacKey);
    DeletePMK(pDefaultMacState);
    goto LABEL_77;
  }
  v8 = -1073741757;
  if ( v11->pIHVSecurityEndpoint != a1 )
    v8 = -1073741790;
  if ( (byte_1400AF802 & 1) != 0 )
    McTemplateK0pjq_EtwWriteTransfer(
      v13,
      (unsigned int)RejectSetPMK,
      (_DWORD)v11 + 4920,
      (_DWORD)v11,
      (__int64)&v11->gDeviceId,
      v8);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 344, WPP_e90d411d816e312466897e39e745b158_Traceguids);
LABEL_50:
  NdisReleaseRWLock(v11->pRWLock, (PLOCK_STATE_EX)&LockState);
LABEL_85:
  memset(a2, 0, (unsigned int)Size);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14004ed8c  mov     [rsp-38h+arg_8], rbx
0x14004ed91  mov     [rsp-38h+LockState], r9
0x14004ed96  mov     dword ptr [rsp-38h+Size], r8d
0x14004ed9b  push    rbp
0x14004ed9c  push    rsi
0x14004ed9d  push    rdi
0x14004ed9e  push    r12
0x14004eda0  push    r13
0x14004eda2  push    r14
0x14004eda4  push    r15
0x14004eda6  mov     rbp, rsp
0x14004eda9  sub     rsp, 50h
0x14004edad  mov     r14, [rcx+18h]
0x14004edb1  mov     rbx, rcx
0x14004edb4  xor     ecx, ecx
0x14004edb6  mov     byte ptr [rbp+LockState], 0
0x14004edba  mov     word ptr [rbp+LockState+1], cx
0x14004edbe  mov     eax, r8d
0x14004edc1  mov     r15, rdx
0x14004edc4  test    r14, r14
0x14004edc7  jnz     short loc_14004EDD3
0x14004edc9  mov     eax, 0C0000010h
0x14004edce  jmp     loc_14004F4EA
0x14004edd3  mov     r8d, 9Ch
0x14004edd9  cmp     eax, r8d
0x14004eddc  jnb     short loc_14004EE1C
0x14004edde  mov     esi, 0C000000Dh
0x14004ede3  mov     rcx, cs:WPP_GLOBAL_Control
0x14004edea  lea     rbx, WPP_GLOBAL_Control
0x14004edf1  cmp     rcx, rbx
0x14004edf4  jz      loc_14004F4DA
0x14004edfa  mov     edx, 153h
0x14004edff  mov     dword ptr [rsp+50h+var_30], r8d
0x14004ee04  mov     r9d, eax
0x14004ee07  mov     rcx, [rcx+18h]
0x14004ee0b  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004ee12  call    WPP_SF_Dd
0x14004ee17  jmp     loc_14004F4DA
0x14004ee1c  mov     r9d, [rdx]
0x14004ee1f  mov     edi, 1
0x14004ee24  cmp     r9d, edi
0x14004ee27  jz      short loc_14004EE50
0x14004ee29  mov     esi, 0C000000Dh
0x14004ee2e  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ee35  lea     rbx, WPP_GLOBAL_Control
0x14004ee3c  cmp     rcx, rbx
0x14004ee3f  jz      loc_14004F4DA
0x14004ee45  mov     edx, 154h
0x14004ee4a  mov     dword ptr [rsp+50h+var_30], edi
0x14004ee4e  jmp     short loc_14004EE07
0x14004ee50  mov     r9d, [rdx+74h]
0x14004ee54  cmp     r9d, 20h ; ' '
0x14004ee58  ja      loc_14004F48D
0x14004ee5e  mov     ecx, [rdx+2Ch]
0x14004ee61  mov     eax, [rdx+4]
0x14004ee64  cmp     ecx, 41h ; 'A'
0x14004ee67  ja      loc_14004F48D
0x14004ee6d  lea     r12, [rdx+8]
0x14004ee71  test    [r12], dil
0x14004ee75  jz      loc_14004EF28
0x14004ee7b  mov     eax, [r12]
0x14004ee7f  cmp     eax, cs:dword_1400A1094
0x14004ee85  jnz     short loc_14004EEE3
0x14004ee87  movzx   eax, word ptr [r12+4]
0x14004ee8d  cmp     ax, cs:word_1400A1098
0x14004ee94  jnz     short loc_14004EEE3
0x14004ee96  mov     r9, [rdx+14h]
0x14004ee9a  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x14004ee9e  jz      loc_14004EF28
0x14004eea4  mov     esi, 0C000000Dh
0x14004eea9  mov     rcx, cs:WPP_GLOBAL_Control
0x14004eeb0  lea     rbx, WPP_GLOBAL_Control
0x14004eeb7  cmp     rcx, rbx
0x14004eeba  jz      loc_14004F4DA
0x14004eec0  mov     rcx, [rcx+18h]
0x14004eec4  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004eecb  mov     edx, 157h
0x14004eed0  mov     [rsp+50h+var_30], 0FFFFFFFFFFFFFFFFh
0x14004eed9  call    WPP_SF_qq
0x14004eede  jmp     loc_14004F4DA
0x14004eee3  mov     esi, 0C000000Dh
0x14004eee8  mov     rcx, cs:WPP_GLOBAL_Control
0x14004eeef  lea     rbx, WPP_GLOBAL_Control
0x14004eef6  cmp     rcx, rbx
0x14004eef9  jz      loc_14004F4DA
0x14004eeff  mov     rcx, [rcx+18h]
0x14004ef03  lea     rax, dword_1400A1094
0x14004ef0a  mov     edx, 156h
0x14004ef0f  mov     [rsp+50h+var_30], rax
0x14004ef14  mov     r9, r12
0x14004ef17  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004ef1e  call    WPP_SF__MAC__MAC_
0x14004ef23  jmp     loc_14004F4DA
0x14004ef28  mov     r14, [r14+10h]
0x14004ef2c  lea     rdx, [rbp+LockState]; LockState
0x14004ef30  xor     r8d, r8d; Flags
0x14004ef33  mov     rcx, [r14+90h]; Lock
0x14004ef3a  call    cs:__imp_NdisAcquireRWLockWrite
0x14004ef41  nop     dword ptr [rax+rax+00h]
0x14004ef46  cmp     [r14+1700h], rbx
0x14004ef4d  jz      short loc_14004EFC3
0x14004ef4f  cmp     [r14+16F0h], rbx
0x14004ef56  jz      short loc_14004EFC3
0x14004ef58  cmp     [r14+16F8h], rbx
0x14004ef5f  mov     esi, 0C0000043h
0x14004ef64  lea     eax, [rsi-21h]
0x14004ef67  cmovnz  esi, eax
0x14004ef6a  test    cs:byte_1400AF802, dil
0x14004ef71  jz      short loc_14004EF92
0x14004ef73  lea     r8, [r14+1338h]
0x14004ef7a  mov     dword ptr [rsp+50h+Src], esi
0x14004ef7e  mov     r9, r14
0x14004ef81  mov     [rsp+50h+var_30], r8
0x14004ef86  lea     rdx, RejectSetPMK
0x14004ef8d  call    McTemplateK0pjq_EtwWriteTransfer
0x14004ef92  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ef99  lea     rbx, WPP_GLOBAL_Control
0x14004efa0  cmp     rcx, rbx
0x14004efa3  jz      loc_14004F124
0x14004efa9  mov     rcx, [rcx+18h]
0x14004efad  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004efb4  mov     edx, 158h
0x14004efb9  call    WPP_SF_
0x14004efbe  jmp     loc_14004F124
0x14004efc3  xor     esi, esi
0x14004efc5  test    [r12], dil
0x14004efc9  jnz     loc_14004F085
0x14004efcf  movzx   ecx, byte ptr [r12+5]
0x14004efd5  movzx   eax, byte ptr [r12+4]
0x14004efdb  xor     ecx, eax
0x14004efdd  and     ecx, 800000FFh
0x14004efe3  jge     short loc_14004EFEF
0x14004efe5  sub     ecx, edi
0x14004efe7  or      ecx, 0FFFFFF00h
0x14004efed  add     ecx, edi
0x14004efef  add     rcx, 0Ah
0x14004eff3  shl     rcx, 4
0x14004eff7  add     rcx, r14
0x14004effa  mov     rdi, [rcx]
0x14004effd  jmp     short loc_14004F017
0x14004efff  mov     eax, [rdi+10h]
0x14004f002  cmp     eax, [r12]
0x14004f006  jnz     short loc_14004F014
0x14004f008  movzx   eax, word ptr [rdi+14h]
0x14004f00c  cmp     ax, [r12+4]
0x14004f012  jz      short loc_14004F01E
0x14004f014  mov     rdi, [rdi]
0x14004f017  cmp     rcx, rdi
0x14004f01a  jnz     short loc_14004EFFF
0x14004f01c  xor     edi, edi
0x14004f01e  mov     [rbp+arg_0], rdi
0x14004f022  lea     r13, [r15+2Ch]
0x14004f026  test    rdi, rdi
0x14004f029  jnz     short loc_14004F094
0x14004f02b  cmp     [r13+0], esi
0x14004f02f  jz      loc_14004F116
0x14004f035  lea     rcx, [r14+0A0h]; struct DOT11_MAC_STATE_MODULE *
0x14004f03c  mov     rdx, r12; unsigned __int8 (*)[6]
0x14004f03f  lea     r8, [rbp+arg_0]; struct DOT11_MAC_STATE_ENTRY **
0x14004f043  call    ?Dot11AddMacState@@YAHPEAUDOT11_MAC_STATE_MODULE@@PEAY05$$CBEPEAPEAUDOT11_MAC_STATE_ENTRY@@@Z; Dot11AddMacState(DOT11_MAC_STATE_MODULE *,uchar const (*)[6],DOT11_MAC_STATE_ENTRY * *)
0x14004f048  mov     esi, eax
0x14004f04a  test    eax, eax
0x14004f04c  jns     short loc_14004F07F
0x14004f04e  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f055  lea     rbx, WPP_GLOBAL_Control
0x14004f05c  cmp     rcx, rbx
0x14004f05f  jz      short loc_14004F076
0x14004f061  mov     rcx, [rcx+18h]
0x14004f065  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004f06c  mov     edx, 159h
0x14004f071  call    WPP_SF_
0x14004f076  mov     rdi, [rbp+arg_0]
0x14004f07a  jmp     loc_14004F116
0x14004f07f  mov     rdi, [rbp+arg_0]
0x14004f083  jmp     short loc_14004F094
0x14004f085  mov     rdi, [r14+10D0h]
0x14004f08c  lea     r13, [r15+2Ch]
0x14004f090  mov     [rbp+arg_0], rdi
0x14004f094  mov     rdx, rdi; struct DOT11_MAC_STATE_ENTRY *
0x14004f097  mov     rcx, r14; struct _VELAN *
0x14004f09a  call    ?Dot11FlushPMKIDCache@@YAJPEAU_VELAN@@PEAUDOT11_MAC_STATE_ENTRY@@@Z; Dot11FlushPMKIDCache(_VELAN *,DOT11_MAC_STATE_ENTRY *)
0x14004f09f  cmp     qword ptr [rdi+68h], 0
0x14004f0a4  jnz     loc_14004F161
0x14004f0aa  lea     r13, [r15+2Ch]
0x14004f0ae  cmp     dword ptr [r13+0], 0
0x14004f0b3  jz      loc_14004F3F2
0x14004f0b9  inc     dword ptr [rdi+20h]
0x14004f0bc  lock inc dword ptr [rdi+24h]
0x14004f0c0  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14004f0c7  mov     qword ptr [rdi+68h], 0
0x14004f0cf  mov     rcx, rbx; Lookaside
0x14004f0d2  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004f0d9  nop     dword ptr [rax+rax+00h]
0x14004f0de  test    rax, rax
0x14004f0e1  jnz     short loc_14004F140
0x14004f0e3  mov     esi, 0C000009Ah
0x14004f0e8  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f0ef  lea     rbx, WPP_GLOBAL_Control
0x14004f0f6  cmp     rcx, rbx
0x14004f0f9  jz      short loc_14004F116
0x14004f0fb  mov     rcx, [rcx+18h]
0x14004f0ff  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004f106  mov     edx, 15Ah
0x14004f10b  mov     r9d, 0D8h
0x14004f111  call    WPP_SF_d
0x14004f116  test    rdi, rdi
0x14004f119  jz      short loc_14004F124
0x14004f11b  lea     rcx, [rbp+arg_0]; struct DOT11_MAC_STATE_ENTRY **
0x14004f11f  call    ?Dot11DecObjCnt@@YAXPEAPEAUDOT11_MAC_STATE_ENTRY@@K@Z; Dot11DecObjCnt(DOT11_MAC_STATE_ENTRY * *,ulong)
0x14004f124  mov     rcx, [r14+90h]; Lock
0x14004f12b  lea     rdx, [rbp+LockState]; LockState
0x14004f12f  call    cs:__imp_NdisReleaseRWLock
0x14004f136  nop     dword ptr [rax+rax+00h]
0x14004f13b  jmp     loc_14004F4DA
0x14004f140  lea     rcx, [rax+10h]; void *
0x14004f144  mov     [rax], rbx
0x14004f147  mov     dword ptr [rax+8], 7A697377h
0x14004f14e  xor     esi, esi
0x14004f150  xor     edx, edx; Val
0x14004f152  mov     [rdi+68h], rcx
0x14004f156  mov     r8d, 0D8h; Size
0x14004f15c  call    memset
0x14004f161  cmp     dword ptr [r13+0], 0
0x14004f166  jz      loc_14004F3F2
0x14004f16c  mov     rax, [r15+14h]
0x14004f170  mov     r12, [rdi+68h]
0x14004f174  mov     [r12+10h], rax
0x14004f179  mov     eax, [r14+171Ch]
0x14004f180  mov     [r12], eax
0x14004f184  call    Feature_60009473__private_IsEnabledDeviceUsageNoInline
0x14004f189  test    eax, eax
0x14004f18b  jz      short loc_14004F196
0x14004f18d  mov     eax, [r15+4]
0x14004f191  mov     [r12+0Ch], eax
0x14004f196  mov     rax, [r14+1C20h]
0x14004f19d  test    rax, rax
0x14004f1a0  jz      short loc_14004F1BE
0x14004f1a2  movzx   eax, word ptr [rax+24h]
0x14004f1a6  mov     [r12+4], ax
0x14004f1ac  mov     rax, [r14+1C20h]
0x14004f1b3  mov     ecx, [rax+88h]
0x14004f1b9  mov     [r12+8], ecx
0x14004f1be  mov     r9d, [r15+4]
0x14004f1c2  lea     rbx, [r15+30h]
0x14004f1c6  mov     eax, [r13+0]
0x14004f1ca  lea     r8, [rdi+10h]
0x14004f1ce  mov     edx, [r14+1718h]
0x14004f1d5  lea     rcx, [r14+1FE8h]; struct _DOT11_PMK_CACHE *
0x14004f1dc  shr     r9d, 0Ch
0x14004f1e0  and     r9b, 1
0x14004f1e4  mov     [rsp+50h+Src], rbx; Src
0x14004f1e9  mov     dword ptr [rsp+50h+var_30], eax; Size
0x14004f1ed  call    PmkCacheUpdatePmkForFullAuth
0x14004f1f2  mov     edx, 46h ; 'F'
0x14004f1f7  mov     rcx, r14
0x14004f1fa  call    ?SAERequestCleanupConnection@@YAXPEAU_VELAN@@W4_DOT11_SAE_STATUS@@@Z; SAERequestCleanupConnection(_VELAN *,_DOT11_SAE_STATUS)
0x14004f1ff  mov     eax, [r15+4]
0x14004f203  mov     rdx, rbx; Src
0x14004f206  mov     ecx, [r15+2Ch]
0x14004f20a  test    al, 2
0x14004f20c  jz      short loc_14004F223
0x14004f20e  mov     [r12+2Ch], ecx
0x14004f213  lea     rcx, [r12+54h]; void *
0x14004f218  mov     r8d, [r13+0]; Size
0x14004f21c  call    memmove
0x14004f221  jmp     short loc_14004F25E
0x14004f223  mov     [r12+30h], ecx
0x14004f228  mov     r8, rcx; Size
0x14004f22b  lea     rcx, [r12+95h]; void *
0x14004f233  call    memmove
0x14004f238  mov     eax, [r15+74h]
0x14004f23c  lea     rdx, [r15+78h]; Src
0x14004f240  mov     r8d, eax; Size
0x14004f243  mov     [r12+28h], eax
0x14004f248  lea     rcx, [r12+34h]; void *
0x14004f24d  call    memmove
0x14004f252  movups  xmm0, xmmword ptr [r15+1Ch]
0x14004f257  movdqu  xmmword ptr [r12+18h], xmm0
0x14004f25e  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f265  lea     rbx, WPP_GLOBAL_Control
0x14004f26c  cmp     rcx, rbx
0x14004f26f  jz      loc_14004F37B
0x14004f275  mov     rcx, [rcx+18h]
0x14004f279  lea     r9, [rdi+10h]
0x14004f27d  mov     edx, 15Bh
0x14004f282  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004f289  call    WPP_SF__MAC_
0x14004f28e  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f295  cmp     rcx, rbx
0x14004f298  jz      loc_14004F37B
0x14004f29e  movzx   r9d, word ptr [r12+4]
0x14004f2a4  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004f2ab  mov     rcx, [rcx+18h]
0x14004f2af  mov     edx, 15Ch
0x14004f2b4  call    WPP_SF_d
0x14004f2b9  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f2c0  cmp     rcx, rbx
0x14004f2c3  jz      loc_14004F37B
0x14004f2c9  mov     rcx, [rcx+18h]
0x14004f2cd  lea     r9, [rbp+var_10]
  ... truncated ...
```
