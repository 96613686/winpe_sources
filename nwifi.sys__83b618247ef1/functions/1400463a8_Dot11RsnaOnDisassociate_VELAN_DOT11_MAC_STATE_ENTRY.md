# Dot11RsnaOnDisassociate(_VELAN *,DOT11_MAC_STATE_ENTRY *)

- ea: `0x1400463a8`
- end: `0x140046909`
- name: `?Dot11RsnaOnDisassociate@@YAXPEAU_VELAN@@PEAUDOT11_MAC_STATE_ENTRY@@@Z`
- size: `1377`
- prototype: `void __fastcall(struct _VELAN *, struct DOT11_MAC_STATE_ENTRY *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14005efe4`

## callees

- `0x14000d22c`
- `0x140013b90`
- `0x1400208f0`
- `0x140020dc0`
- `0x14002f1bc`
- `0x1400366f8`
- `0x14003ae2c`
- `0x140041398`
- `0x1400463a8`
- `0x140047998`
- `0x14004f614`
- `0x14004f77c`
- `0x14004f7bc`
- `0x14004fbec`
- `0x14004fc44`
- `0x140053cb0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140046524`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140046524`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140046649`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140046689`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400466c9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140046709`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140046749`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400467b7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140046649`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140046689`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400466c9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140046709`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140046749`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400467b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004665a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004669a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400466da`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004671a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004675a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400467c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004665a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004669a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400466da`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004671a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004675a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400467c8`

## pseudocode

```c
void __fastcall Dot11RsnaOnDisassociate(struct _VELAN *a1, struct DOT11_MAC_STATE_ENTRY *a2, __int64 a3, __int64 a4)
{
  _NWF_KEY_CONTEXT *p_KeyContext; // rbx
  int bRSNASecured; // r14d
  _DEVICE_OBJECT *AttachedDevice; // rcx
  __int64 pPmk; // rcx
  unsigned int AuthAlgo; // eax
  char *v11; // rax
  NWF_PMK_ENTRY *v12; // rax
  struct _NWF_KEY_CONTEXT *v13; // rdx
  unsigned __int8 *pAssocRequestRsnIE; // rcx
  unsigned __int8 *v15; // rcx
  unsigned __int8 *pAssocRequestRsnXeIE; // rcx
  unsigned __int8 *v17; // rcx
  unsigned __int8 *pBeaconRsnIE; // rcx
  unsigned __int8 *v19; // rcx
  unsigned __int8 *pBeaconRsnXeIE; // rcx
  unsigned __int8 *v21; // rcx
  DOT11_CONNECTION_INFO *pConnectionInfo; // rcx
  ULONG *p_Rssi; // rcx
  struct NWF_EAPOL_HEADER *pEapolHdr; // rcx
  ULONG *v25; // rcx
  NWF_PMK_ENTRY *pOpPmk; // rdi
  _DEVICE_OBJECT *v27; // rcx
  __int128 v28; // [rsp+20h] [rbp-10h] BYREF

  p_KeyContext = &a1->KeyContext;
  bRSNASecured = a1->KeyContext.bRSNASecured;
  if ( a1->KeyContext.pOpPmk )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 381, WPP_e90d411d816e312466897e39e745b158_Traceguids);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          382,
          WPP_e90d411d816e312466897e39e745b158_Traceguids,
          p_KeyContext->pOpPmk->MDID);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
          v28 = 0;
          LOWORD(v28) = 16;
          *((_QWORD *)&v28 + 1) = p_KeyContext->pOpPmk->PMKID;
          WPP_SF__HEX_(AttachedDevice, 383, WPP_e90d411d816e312466897e39e745b158_Traceguids, &v28);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            WPP_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              384,
              WPP_e90d411d816e312466897e39e745b158_Traceguids,
              p_KeyContext->pOpPmk->ullExpiry);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                385,
                WPP_e90d411d816e312466897e39e745b158_Traceguids,
                p_KeyContext->pOpPmk->AuthAlgo);
          }
        }
      }
    }
  }
  pPmk = (__int64)a2->pPmk;
  if ( pPmk )
  {
    if ( !(unsigned int)IsPMKExpired((struct NWF_PMK_ENTRY *)pPmk) )
    {
      AuthAlgo = p_KeyContext->AuthAlgo;
      if ( AuthAlgo <= 0xB )
      {
        pPmk = 2880;
        if ( _bittest((const int *)&pPmk, AuthAlgo) )
        {
          if ( !p_KeyContext->pOpPmk )
          {
            p_KeyContext->pOpPmk = 0;
            v11 = (char *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead);
            if ( v11 )
            {
              *((_DWORD *)v11 + 2) = 2053731191;
              *(_QWORD *)v11 = &WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
              p_KeyContext->pOpPmk = (NWF_PMK_ENTRY *)(v11 + 16);
            }
          }
          pPmk = (__int64)p_KeyContext->pOpPmk;
          if ( pPmk )
          {
            v12 = a2->pPmk;
            *(_OWORD *)pPmk = *(_OWORD *)&v12->AuthAlgo;
            *(_OWORD *)(pPmk + 16) = *(_OWORD *)&v12->ullExpiry;
            *(_OWORD *)(pPmk + 32) = *(_OWORD *)&v12->PMKID[8];
            *(_OWORD *)(pPmk + 48) = *(_OWORD *)&v12->uSendKeyLength;
            *(_OWORD *)(pPmk + 64) = *(_OWORD *)&v12->ucRecvKey[12];
            *(_OWORD *)(pPmk + 80) = *(_OWORD *)&v12->ucRecvKey[28];
            *(_OWORD *)(pPmk + 96) = *(_OWORD *)&v12->Passphrase[12];
            *(_OWORD *)(pPmk + 112) = *(_OWORD *)&v12->Passphrase[28];
            *(_OWORD *)(pPmk + 128) = *(_OWORD *)&v12->Passphrase[44];
            *(_OWORD *)(pPmk + 144) = *(_OWORD *)&v12->Passphrase[60];
            *(_OWORD *)(pPmk + 160) = *(_OWORD *)&v12->ucKey[11];
            *(_OWORD *)(pPmk + 176) = *(_OWORD *)&v12->ucKey[27];
            *(_OWORD *)(pPmk + 192) = *(_OWORD *)&v12->ucKey[43];
            *(_QWORD *)(pPmk + 208) = *(_QWORD *)&v12->ucKey[59];
            pPmk = (__int64)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              WPP_SF__MAC_(
                WPP_GLOBAL_Control->AttachedDevice,
                386,
                WPP_e90d411d816e312466897e39e745b158_Traceguids,
                a2->MacHashEntry.MacKey);
          }
        }
      }
    }
  }
  if ( (unsigned int)Feature_53299205__private_IsEnabledDeviceUsageNoInline(pPmk, a2, a3, a4) )
  {
    RsnOConnection::CleanupRsnIEs((RsnOConnection *)p_KeyContext, v13);
  }
  else
  {
    pAssocRequestRsnIE = p_KeyContext->pAssocRequestRsnIE;
    if ( pAssocRequestRsnIE )
    {
      v15 = pAssocRequestRsnIE - 16;
      if ( *(_QWORD *)v15 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v15, v15);
      else
        ExFreePoolWithTag(v15, *((_DWORD *)v15 + 2));
      p_KeyContext->pAssocRequestRsnIE = 0;
    }
    pAssocRequestRsnXeIE = p_KeyContext->pAssocRequestRsnXeIE;
    if ( pAssocRequestRsnXeIE )
    {
      v17 = pAssocRequestRsnXeIE - 16;
      if ( *(_QWORD *)v17 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v17, v17);
      else
        ExFreePoolWithTag(v17, *((_DWORD *)v17 + 2));
      p_KeyContext->pAssocRequestRsnXeIE = 0;
    }
    pBeaconRsnIE = p_KeyContext->pBeaconRsnIE;
    if ( pBeaconRsnIE )
    {
      v19 = pBeaconRsnIE - 16;
      if ( *(_QWORD *)v19 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v19, v19);
      else
        ExFreePoolWithTag(v19, *((_DWORD *)v19 + 2));
      p_KeyContext->pBeaconRsnIE = 0;
    }
    pBeaconRsnXeIE = p_KeyContext->pBeaconRsnXeIE;
    if ( pBeaconRsnXeIE )
    {
      v21 = pBeaconRsnXeIE - 16;
      if ( *(_QWORD *)v21 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v21, v21);
      else
        ExFreePoolWithTag(v21, *((_DWORD *)v21 + 2));
      p_KeyContext->pBeaconRsnXeIE = 0;
    }
  }
  pConnectionInfo = p_KeyContext->pConnectionInfo;
  if ( pConnectionInfo )
  {
    p_Rssi = (ULONG *)&pConnectionInfo[-1].LinkInfo[0].Rssi;
    if ( *(_QWORD *)p_Rssi )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)p_Rssi, p_Rssi);
    else
      ExFreePoolWithTag(p_Rssi, p_Rssi[2]);
    p_KeyContext->pConnectionInfo = 0;
  }
  FreeFTContext(&p_KeyContext->pFTContext);
  SAERequestCleanupConnection(a1, 71);
  if ( a1->KeyContext.M1Cache.pMacStateEntry )
    Dot11ReleaseMacState(&a1->KeyContext.M1Cache.pMacStateEntry);
  pEapolHdr = p_KeyContext->M1Cache.pEapolHdr;
  if ( pEapolHdr )
  {
    v25 = (ULONG *)((char *)pEapolHdr - 16);
    if ( *(_QWORD *)v25 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v25, v25);
    else
      ExFreePoolWithTag(v25, v25[2]);
    p_KeyContext->M1Cache.pEapolHdr = 0;
  }
  pOpPmk = p_KeyContext->pOpPmk;
  SetReplayCounter(a1, 0);
  SetRSNASecured(a1, 0);
  memset(p_KeyContext, 0, sizeof(_NWF_KEY_CONTEXT));
  p_KeyContext->pOpPmk = pOpPmk;
  if ( pOpPmk )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 387, WPP_e90d411d816e312466897e39e745b158_Traceguids);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 388, WPP_e90d411d816e312466897e39e745b158_Traceguids, pOpPmk->MDID);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          v27 = WPP_GLOBAL_Control->AttachedDevice;
          *(_QWORD *)&v28 = 16;
          *((_QWORD *)&v28 + 1) = pOpPmk->PMKID;
          WPP_SF__HEX_(v27, 389, WPP_e90d411d816e312466897e39e745b158_Traceguids, &v28);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            WPP_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              390,
              WPP_e90d411d816e312466897e39e745b158_Traceguids,
              pOpPmk->ullExpiry);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                391,
                WPP_e90d411d816e312466897e39e745b158_Traceguids,
                (unsigned int)pOpPmk->AuthAlgo);
          }
        }
      }
    }
  }
  NotifyReplayCounterUpdated(a1);
  if ( bRSNASecured )
    NotifySecureConnectionChange(a1);
}

```

## disassembly

```asm
0x1400463a8  push    rbp
0x1400463aa  push    rbx
0x1400463ab  push    rsi
0x1400463ac  push    rdi
0x1400463ad  push    r12
0x1400463af  push    r13
0x1400463b1  push    r14
0x1400463b3  mov     rbp, rsp
0x1400463b6  sub     rsp, 30h
0x1400463ba  lea     rbx, [rcx+1710h]
0x1400463c1  mov     rdi, rdx
0x1400463c4  cmp     qword ptr [rbx+0F0h], 0
0x1400463cc  lea     r13, WPP_GLOBAL_Control
0x1400463d3  mov     r14d, [rbx+4E8h]
0x1400463da  lea     r12, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x1400463e1  mov     rsi, rcx
0x1400463e4  jz      loc_1400464D4
0x1400463ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400463f1  cmp     rcx, r13
0x1400463f4  jz      loc_1400464D4
0x1400463fa  mov     rcx, [rcx+18h]
0x1400463fe  mov     edx, 17Dh
0x140046403  mov     r8, r12
0x140046406  call    WPP_SF_
0x14004640b  mov     rcx, cs:WPP_GLOBAL_Control
0x140046412  cmp     rcx, r13
0x140046415  jz      loc_1400464D4
0x14004641b  mov     rax, [rbx+0F0h]
0x140046422  mov     edx, 17Eh
0x140046427  mov     rcx, [rcx+18h]
0x14004642b  mov     r8, r12
0x14004642e  movzx   r9d, word ptr [rax+4]
0x140046433  call    WPP_SF_d
0x140046438  mov     rcx, cs:WPP_GLOBAL_Control
0x14004643f  cmp     rcx, r13
0x140046442  jz      loc_1400464D4
0x140046448  mov     rcx, [rcx+18h]
0x14004644c  lea     r9, [rbp+var_10]
0x140046450  xorps   xmm0, xmm0
0x140046453  mov     eax, 10h
0x140046458  movups  [rbp+var_10], xmm0
0x14004645c  mov     word ptr [rbp+var_10], ax
0x140046460  mov     edx, 17Fh
0x140046465  mov     rax, [rbx+0F0h]
0x14004646c  mov     r8, r12
0x14004646f  add     rax, 18h
0x140046473  mov     qword ptr [rbp+var_10+8], rax
0x140046477  movaps  xmm0, [rbp+var_10]
0x14004647b  movdqa  [rbp+var_10], xmm0
0x140046480  call    WPP_SF__HEX_
0x140046485  mov     rcx, cs:WPP_GLOBAL_Control
0x14004648c  cmp     rcx, r13
0x14004648f  jz      short loc_1400464D4
0x140046491  mov     r9, [rbx+0F0h]
0x140046498  mov     edx, 180h
0x14004649d  mov     rcx, [rcx+18h]
0x1400464a1  mov     r8, r12
0x1400464a4  mov     r9, [r9+10h]
0x1400464a8  call    WPP_SF_q
0x1400464ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400464b4  cmp     rcx, r13
0x1400464b7  jz      short loc_1400464D4
0x1400464b9  mov     r9, [rbx+0F0h]
0x1400464c0  mov     edx, 181h
0x1400464c5  mov     rcx, [rcx+18h]
0x1400464c9  mov     r8, r12
0x1400464cc  mov     r9d, [r9]
0x1400464cf  call    WPP_SF_d
0x1400464d4  mov     rcx, [rdi+68h]; struct NWF_PMK_ENTRY *
0x1400464d8  test    rcx, rcx
0x1400464db  jz      loc_140046618
0x1400464e1  call    ?IsPMKExpired@@YAHPEAUNWF_PMK_ENTRY@@@Z; IsPMKExpired(NWF_PMK_ENTRY *)
0x1400464e6  test    eax, eax
0x1400464e8  jnz     loc_140046618
0x1400464ee  mov     eax, [rbx+0Ch]
0x1400464f1  cmp     eax, 0Bh
0x1400464f4  ja      loc_140046618
0x1400464fa  mov     ecx, 0B40h
0x1400464ff  bt      ecx, eax
0x140046502  jnb     loc_140046618
0x140046508  cmp     qword ptr [rbx+0F0h], 0
0x140046510  jnz     short loc_140046551
0x140046512  lea     rcx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead; Lookaside
0x140046519  mov     qword ptr [rbx+0F0h], 0
0x140046524  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004652b  nop     dword ptr [rax+rax+00h]
0x140046530  test    rax, rax
0x140046533  jz      short loc_140046551
0x140046535  mov     dword ptr [rax+8], 7A697377h
0x14004653c  lea     rcx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140046543  mov     [rax], rcx
0x140046546  add     rax, 10h
0x14004654a  mov     [rbx+0F0h], rax
0x140046551  mov     rcx, [rbx+0F0h]
0x140046558  test    rcx, rcx
0x14004655b  jz      loc_140046618
0x140046561  mov     rax, [rdi+68h]
0x140046565  movups  xmm0, xmmword ptr [rax]
0x140046568  movups  xmmword ptr [rcx], xmm0
0x14004656b  movups  xmm1, xmmword ptr [rax+10h]
0x14004656f  movups  xmmword ptr [rcx+10h], xmm1
0x140046573  movups  xmm0, xmmword ptr [rax+20h]
0x140046577  movups  xmmword ptr [rcx+20h], xmm0
0x14004657b  movups  xmm1, xmmword ptr [rax+30h]
0x14004657f  movups  xmmword ptr [rcx+30h], xmm1
0x140046583  movups  xmm0, xmmword ptr [rax+40h]
0x140046587  movups  xmmword ptr [rcx+40h], xmm0
0x14004658b  movups  xmm1, xmmword ptr [rax+50h]
0x14004658f  movups  xmmword ptr [rcx+50h], xmm1
0x140046593  movups  xmm0, xmmword ptr [rax+60h]
0x140046597  movups  xmmword ptr [rcx+60h], xmm0
0x14004659b  movups  xmm1, xmmword ptr [rax+70h]
0x14004659f  movups  xmmword ptr [rcx+70h], xmm1
0x1400465a3  movups  xmm0, xmmword ptr [rax+80h]
0x1400465aa  movups  xmmword ptr [rcx+80h], xmm0
0x1400465b1  movups  xmm1, xmmword ptr [rax+90h]
0x1400465b8  movups  xmmword ptr [rcx+90h], xmm1
0x1400465bf  movups  xmm0, xmmword ptr [rax+0A0h]
0x1400465c6  movups  xmmword ptr [rcx+0A0h], xmm0
0x1400465cd  movups  xmm1, xmmword ptr [rax+0B0h]
0x1400465d4  movups  xmmword ptr [rcx+0B0h], xmm1
0x1400465db  movups  xmm0, xmmword ptr [rax+0C0h]
0x1400465e2  movups  xmmword ptr [rcx+0C0h], xmm0
0x1400465e9  mov     rax, [rax+0D0h]
0x1400465f0  mov     [rcx+0D0h], rax
0x1400465f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400465fe  cmp     rcx, r13
0x140046601  jz      short loc_140046618
0x140046603  mov     rcx, [rcx+18h]
0x140046607  lea     r9, [rdi+10h]
0x14004660b  mov     edx, 182h
0x140046610  mov     r8, r12
0x140046613  call    WPP_SF__MAC_
0x140046618  call    Feature_53299205__private_IsEnabledDeviceUsageNoInline
0x14004661d  test    eax, eax
0x14004661f  jz      short loc_14004662E
0x140046621  mov     rcx, rbx; this
0x140046624  call    ?CleanupRsnIEs@RsnOConnection@@YAXPEAU_NWF_KEY_CONTEXT@@@Z; RsnOConnection::CleanupRsnIEs(_NWF_KEY_CONTEXT *)
0x140046629  jmp     loc_14004672E
0x14004662e  mov     rcx, [rbx+38h]
0x140046632  test    rcx, rcx
0x140046635  jz      short loc_14004666E
0x140046637  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14004663b  mov     rax, [rcx]
0x14004663e  test    rax, rax
0x140046641  jz      short loc_140046657
0x140046643  mov     rdx, rcx; Entry
0x140046646  mov     rcx, rax; Lookaside
0x140046649  call    cs:__imp_ExFreeToNPagedLookasideList
0x140046650  nop     dword ptr [rax+rax+00h]
0x140046655  jmp     short loc_140046666
0x140046657  mov     edx, [rcx+8]; Tag
0x14004665a  call    cs:__imp_ExFreePoolWithTag
0x140046661  nop     dword ptr [rax+rax+00h]
0x140046666  mov     qword ptr [rbx+38h], 0
0x14004666e  mov     rcx, [rbx+48h]
0x140046672  test    rcx, rcx
0x140046675  jz      short loc_1400466AE
0x140046677  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14004667b  mov     rax, [rcx]
0x14004667e  test    rax, rax
0x140046681  jz      short loc_140046697
0x140046683  mov     rdx, rcx; Entry
0x140046686  mov     rcx, rax; Lookaside
0x140046689  call    cs:__imp_ExFreeToNPagedLookasideList
0x140046690  nop     dword ptr [rax+rax+00h]
0x140046695  jmp     short loc_1400466A6
0x140046697  mov     edx, [rcx+8]; Tag
0x14004669a  call    cs:__imp_ExFreePoolWithTag
0x1400466a1  nop     dword ptr [rax+rax+00h]
0x1400466a6  mov     qword ptr [rbx+48h], 0
0x1400466ae  mov     rcx, [rbx+60h]
0x1400466b2  test    rcx, rcx
0x1400466b5  jz      short loc_1400466EE
0x1400466b7  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x1400466bb  mov     rax, [rcx]
0x1400466be  test    rax, rax
0x1400466c1  jz      short loc_1400466D7
0x1400466c3  mov     rdx, rcx; Entry
0x1400466c6  mov     rcx, rax; Lookaside
0x1400466c9  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400466d0  nop     dword ptr [rax+rax+00h]
0x1400466d5  jmp     short loc_1400466E6
0x1400466d7  mov     edx, [rcx+8]; Tag
0x1400466da  call    cs:__imp_ExFreePoolWithTag
0x1400466e1  nop     dword ptr [rax+rax+00h]
0x1400466e6  mov     qword ptr [rbx+60h], 0
0x1400466ee  mov     rcx, [rbx+70h]
0x1400466f2  test    rcx, rcx
0x1400466f5  jz      short loc_14004672E
0x1400466f7  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x1400466fb  mov     rax, [rcx]
0x1400466fe  test    rax, rax
0x140046701  jz      short loc_140046717
0x140046703  mov     rdx, rcx; Entry
0x140046706  mov     rcx, rax; Lookaside
0x140046709  call    cs:__imp_ExFreeToNPagedLookasideList
0x140046710  nop     dword ptr [rax+rax+00h]
0x140046715  jmp     short loc_140046726
0x140046717  mov     edx, [rcx+8]; Tag
0x14004671a  call    cs:__imp_ExFreePoolWithTag
0x140046721  nop     dword ptr [rax+rax+00h]
0x140046726  mov     qword ptr [rbx+70h], 0
0x14004672e  mov     rcx, [rbx+58h]
0x140046732  test    rcx, rcx
0x140046735  jz      short loc_14004676E
0x140046737  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14004673b  mov     rax, [rcx]
0x14004673e  test    rax, rax
0x140046741  jz      short loc_140046757
0x140046743  mov     rdx, rcx; Entry
0x140046746  mov     rcx, rax; Lookaside
0x140046749  call    cs:__imp_ExFreeToNPagedLookasideList
0x140046750  nop     dword ptr [rax+rax+00h]
0x140046755  jmp     short loc_140046766
0x140046757  mov     edx, [rcx+8]; Tag
0x14004675a  call    cs:__imp_ExFreePoolWithTag
0x140046761  nop     dword ptr [rax+rax+00h]
0x140046766  mov     qword ptr [rbx+58h], 0
0x14004676e  lea     rcx, [rbx+510h]; struct NWF_FT_CONTEXT **
0x140046775  call    ?FreeFTContext@@YAXPEAPEAUNWF_FT_CONTEXT@@@Z; FreeFTContext(NWF_FT_CONTEXT * *)
0x14004677a  mov     edx, 47h ; 'G'
0x14004677f  mov     rcx, rsi
0x140046782  call    ?SAERequestCleanupConnection@@YAXPEAU_VELAN@@W4_DOT11_SAE_STATUS@@@Z; SAERequestCleanupConnection(_VELAN *,_DOT11_SAE_STATUS)
0x140046787  lea     rcx, [rsi+17F0h]; struct DOT11_MAC_STATE_ENTRY **
0x14004678e  cmp     qword ptr [rcx], 0
0x140046792  jz      short loc_140046799
0x140046794  call    ?Dot11ReleaseMacState@@YAXPEAPEAUDOT11_MAC_STATE_ENTRY@@@Z; Dot11ReleaseMacState(DOT11_MAC_STATE_ENTRY * *)
0x140046799  mov     rcx, [rbx+0E8h]
0x1400467a0  test    rcx, rcx
0x1400467a3  jz      short loc_1400467DF
0x1400467a5  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x1400467a9  mov     rax, [rcx]
0x1400467ac  test    rax, rax
0x1400467af  jz      short loc_1400467C5
0x1400467b1  mov     rdx, rcx; Entry
0x1400467b4  mov     rcx, rax; Lookaside
0x1400467b7  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400467be  nop     dword ptr [rax+rax+00h]
0x1400467c3  jmp     short loc_1400467D4
0x1400467c5  mov     edx, [rcx+8]; Tag
0x1400467c8  call    cs:__imp_ExFreePoolWithTag
0x1400467cf  nop     dword ptr [rax+rax+00h]
0x1400467d4  mov     qword ptr [rbx+0E8h], 0
0x1400467df  mov     rdi, [rbx+0F0h]
0x1400467e6  xor     edx, edx; unsigned __int64
0x1400467e8  mov     rcx, rsi; struct _VELAN *
0x1400467eb  call    ?SetReplayCounter@@YAXPEAU_VELAN@@_K@Z; SetReplayCounter(_VELAN *,unsigned __int64)
0x1400467f0  xor     edx, edx; int
0x1400467f2  mov     rcx, rsi; struct _VELAN *
0x1400467f5  call    ?SetRSNASecured@@YAXPEAU_VELAN@@H@Z; SetRSNASecured(_VELAN *,int)
0x1400467fa  xor     edx, edx; Val
0x1400467fc  mov     r8d, 858h; Size
0x140046802  mov     rcx, rbx; void *
0x140046805  call    memset
0x14004680a  mov     [rbx+0F0h], rdi
0x140046811  test    rdi, rdi
0x140046814  jz      loc_1400468E4
0x14004681a  mov     rcx, cs:WPP_GLOBAL_Control
0x140046821  cmp     rcx, r13
0x140046824  jz      loc_1400468E4
0x14004682a  mov     rcx, [rcx+18h]
0x14004682e  mov     edx, 183h
0x140046833  mov     r8, r12
0x140046836  call    WPP_SF_
0x14004683b  mov     rcx, cs:WPP_GLOBAL_Control
0x140046842  cmp     rcx, r13
0x140046845  jz      loc_1400468E4
0x14004684b  movzx   r9d, word ptr [rdi+4]
0x140046850  mov     edx, 184h
0x140046855  mov     rcx, [rcx+18h]
0x140046859  mov     r8, r12
0x14004685c  call    WPP_SF_d
0x140046861  mov     rcx, cs:WPP_GLOBAL_Control
0x140046868  cmp     rcx, r13
0x14004686b  jz      short loc_1400468E4
0x14004686d  mov     rcx, [rcx+18h]
0x140046871  lea     r9, [rbp+var_10]
0x140046875  xorps   xmm0, xmm0
0x140046878  mov     eax, 10h
0x14004687d  movups  [rbp+var_10], xmm0
0x140046881  mov     word ptr [rbp+var_10], ax
0x140046885  mov     edx, 185h
0x14004688a  lea     rax, [rdi+18h]
0x14004688e  mov     r8, r12
0x140046891  mov     qword ptr [rbp+var_10+8], rax
0x140046895  movaps  xmm0, [rbp+var_10]
0x140046899  movdqa  [rbp+var_10], xmm0
0x14004689e  call    WPP_SF__HEX_
0x1400468a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400468aa  cmp     rcx, r13
0x1400468ad  jz      short loc_1400468E4
0x1400468af  mov     r9, [rdi+10h]
0x1400468b3  mov     edx, 186h
0x1400468b8  mov     rcx, [rcx+18h]
0x1400468bc  mov     r8, r12
0x1400468bf  call    WPP_SF_q
0x1400468c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400468cb  cmp     rcx, r13
0x1400468ce  jz      short loc_1400468E4
  ... truncated ...
```
