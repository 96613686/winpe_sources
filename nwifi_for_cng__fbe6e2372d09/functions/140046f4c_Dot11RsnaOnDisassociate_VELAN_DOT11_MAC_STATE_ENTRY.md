# Dot11RsnaOnDisassociate(_VELAN *,DOT11_MAC_STATE_ENTRY *)

- ea: `0x140046f4c`
- end: `0x1400474ad`
- name: `?Dot11RsnaOnDisassociate@@YAXPEAU_VELAN@@PEAUDOT11_MAC_STATE_ENTRY@@@Z`
- size: `1377`
- prototype: `void __fastcall(struct _VELAN *, struct DOT11_MAC_STATE_ENTRY *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140060814`

## callees

- `0x14000d21c`
- `0x140013b80`
- `0x1400208f0`
- `0x140020dc0`
- `0x14002f44c`
- `0x140036918`
- `0x14003b04c`
- `0x140041e34`
- `0x140046f4c`
- `0x140048c20`
- `0x140050ddc`
- `0x140050f44`
- `0x140050f84`
- `0x1400513b4`
- `0x14005140c`
- `0x1400554d0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400470c8`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400470c8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400471ed`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004722d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004726d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400472ad`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400472ed`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004735b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400471ed`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004722d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004726d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400472ad`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400472ed`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004735b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400471fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004723e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004727e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400472be`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400472fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004736c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400471fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004723e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004727e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400472be`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400472fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004736c`

## pseudocode

```c
void __fastcall Dot11RsnaOnDisassociate(struct _VELAN *a1, struct DOT11_MAC_STATE_ENTRY *a2)
{
  _NWF_KEY_CONTEXT *p_KeyContext; // rbx
  int bRSNASecured; // r14d
  _DEVICE_OBJECT *AttachedDevice; // rcx
  struct NWF_PMK_ENTRY *pPmk; // rcx
  unsigned int AuthAlgo; // eax
  int v9; // ecx
  char *v10; // rax
  NWF_PMK_ENTRY *pOpPmk; // rcx
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
  NWF_PMK_ENTRY *v26; // rdi
  _DEVICE_OBJECT *v27; // rcx
  __int128 v28; // [rsp+20h] [rbp-10h] BYREF

  p_KeyContext = &a1->KeyContext;
  bRSNASecured = a1->KeyContext.bRSNASecured;
  if ( a1->KeyContext.pOpPmk )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 381, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          382,
          WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
          p_KeyContext->pOpPmk->MDID);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
          v28 = 0;
          LOWORD(v28) = 16;
          *((_QWORD *)&v28 + 1) = p_KeyContext->pOpPmk->PMKID;
          WPP_SF__HEX_(AttachedDevice, 383, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, &v28);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            WPP_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              384,
              WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
              p_KeyContext->pOpPmk->ullExpiry);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                385,
                WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
                p_KeyContext->pOpPmk->AuthAlgo);
          }
        }
      }
    }
  }
  pPmk = a2->pPmk;
  if ( pPmk )
  {
    if ( !(unsigned int)IsPMKExpired(pPmk) )
    {
      AuthAlgo = p_KeyContext->AuthAlgo;
      if ( AuthAlgo <= 0xB )
      {
        v9 = 2880;
        if ( _bittest(&v9, AuthAlgo) )
        {
          if ( !p_KeyContext->pOpPmk )
          {
            p_KeyContext->pOpPmk = 0;
            v10 = (char *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead);
            if ( v10 )
            {
              *((_DWORD *)v10 + 2) = 2053731191;
              *(_QWORD *)v10 = &WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
              p_KeyContext->pOpPmk = (NWF_PMK_ENTRY *)(v10 + 16);
            }
          }
          pOpPmk = p_KeyContext->pOpPmk;
          if ( pOpPmk )
          {
            v12 = a2->pPmk;
            *(_OWORD *)&pOpPmk->AuthAlgo = *(_OWORD *)&v12->AuthAlgo;
            *(_OWORD *)&pOpPmk->ullExpiry = *(_OWORD *)&v12->ullExpiry;
            *(_OWORD *)&pOpPmk->PMKID[8] = *(_OWORD *)&v12->PMKID[8];
            *(_OWORD *)&pOpPmk->uSendKeyLength = *(_OWORD *)&v12->uSendKeyLength;
            *(_OWORD *)&pOpPmk->ucRecvKey[12] = *(_OWORD *)&v12->ucRecvKey[12];
            *(_OWORD *)&pOpPmk->ucRecvKey[28] = *(_OWORD *)&v12->ucRecvKey[28];
            *(_OWORD *)&pOpPmk->Passphrase[12] = *(_OWORD *)&v12->Passphrase[12];
            *(_OWORD *)&pOpPmk->Passphrase[28] = *(_OWORD *)&v12->Passphrase[28];
            *(_OWORD *)&pOpPmk->Passphrase[44] = *(_OWORD *)&v12->Passphrase[44];
            *(_OWORD *)&pOpPmk->Passphrase[60] = *(_OWORD *)&v12->Passphrase[60];
            *(_OWORD *)&pOpPmk->ucKey[11] = *(_OWORD *)&v12->ucKey[11];
            *(_OWORD *)&pOpPmk->ucKey[27] = *(_OWORD *)&v12->ucKey[27];
            *(_OWORD *)&pOpPmk->ucKey[43] = *(_OWORD *)&v12->ucKey[43];
            *(_QWORD *)&pOpPmk->ucKey[59] = *(_QWORD *)&v12->ucKey[59];
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              WPP_SF__MAC_(
                WPP_GLOBAL_Control->AttachedDevice,
                386,
                WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
                a2->MacHashEntry.MacKey);
          }
        }
      }
    }
  }
  if ( (unsigned int)Feature_53299205__private_IsEnabledDeviceUsageNoInline() )
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
  SAERequestCleanupConnection(a1, 0x47u);
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
  v26 = p_KeyContext->pOpPmk;
  SetReplayCounter(a1, 0);
  SetRSNASecured(a1, 0);
  memset(p_KeyContext, 0, sizeof(_NWF_KEY_CONTEXT));
  p_KeyContext->pOpPmk = v26;
  if ( v26 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 387, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 388, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, v26->MDID);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          v27 = WPP_GLOBAL_Control->AttachedDevice;
          *(_QWORD *)&v28 = 16;
          *((_QWORD *)&v28 + 1) = v26->PMKID;
          WPP_SF__HEX_(v27, 389, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids, &v28);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            WPP_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              390,
              WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
              v26->ullExpiry);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                391,
                WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
                (unsigned int)v26->AuthAlgo);
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
0x140046f4c  push    rbp
0x140046f4e  push    rbx
0x140046f4f  push    rsi
0x140046f50  push    rdi
0x140046f51  push    r12
0x140046f53  push    r13
0x140046f55  push    r14
0x140046f57  mov     rbp, rsp
0x140046f5a  sub     rsp, 30h
0x140046f5e  lea     rbx, [rcx+1710h]
0x140046f65  mov     rdi, rdx
0x140046f68  cmp     qword ptr [rbx+0F0h], 0
0x140046f70  lea     r13, WPP_GLOBAL_Control
0x140046f77  mov     r14d, [rbx+4E8h]
0x140046f7e  lea     r12, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x140046f85  mov     rsi, rcx
0x140046f88  jz      loc_140047078
0x140046f8e  mov     rcx, cs:WPP_GLOBAL_Control
0x140046f95  cmp     rcx, r13
0x140046f98  jz      loc_140047078
0x140046f9e  mov     rcx, [rcx+18h]
0x140046fa2  mov     edx, 17Dh
0x140046fa7  mov     r8, r12
0x140046faa  call    WPP_SF_
0x140046faf  mov     rcx, cs:WPP_GLOBAL_Control
0x140046fb6  cmp     rcx, r13
0x140046fb9  jz      loc_140047078
0x140046fbf  mov     rax, [rbx+0F0h]
0x140046fc6  mov     edx, 17Eh
0x140046fcb  mov     rcx, [rcx+18h]
0x140046fcf  mov     r8, r12
0x140046fd2  movzx   r9d, word ptr [rax+4]
0x140046fd7  call    WPP_SF_d
0x140046fdc  mov     rcx, cs:WPP_GLOBAL_Control
0x140046fe3  cmp     rcx, r13
0x140046fe6  jz      loc_140047078
0x140046fec  mov     rcx, [rcx+18h]
0x140046ff0  lea     r9, [rbp+var_10]
0x140046ff4  xorps   xmm0, xmm0
0x140046ff7  mov     eax, 10h
0x140046ffc  movups  [rbp+var_10], xmm0
0x140047000  mov     word ptr [rbp+var_10], ax
0x140047004  mov     edx, 17Fh
0x140047009  mov     rax, [rbx+0F0h]
0x140047010  mov     r8, r12
0x140047013  add     rax, 18h
0x140047017  mov     qword ptr [rbp+var_10+8], rax
0x14004701b  movaps  xmm0, [rbp+var_10]
0x14004701f  movdqa  [rbp+var_10], xmm0
0x140047024  call    WPP_SF__HEX_
0x140047029  mov     rcx, cs:WPP_GLOBAL_Control
0x140047030  cmp     rcx, r13
0x140047033  jz      short loc_140047078
0x140047035  mov     r9, [rbx+0F0h]
0x14004703c  mov     edx, 180h
0x140047041  mov     rcx, [rcx+18h]
0x140047045  mov     r8, r12
0x140047048  mov     r9, [r9+10h]
0x14004704c  call    WPP_SF_q
0x140047051  mov     rcx, cs:WPP_GLOBAL_Control
0x140047058  cmp     rcx, r13
0x14004705b  jz      short loc_140047078
0x14004705d  mov     r9, [rbx+0F0h]
0x140047064  mov     edx, 181h
0x140047069  mov     rcx, [rcx+18h]
0x14004706d  mov     r8, r12
0x140047070  mov     r9d, [r9]
0x140047073  call    WPP_SF_d
0x140047078  mov     rcx, [rdi+68h]; struct NWF_PMK_ENTRY *
0x14004707c  test    rcx, rcx
0x14004707f  jz      loc_1400471BC
0x140047085  call    ?IsPMKExpired@@YAHPEAUNWF_PMK_ENTRY@@@Z; IsPMKExpired(NWF_PMK_ENTRY *)
0x14004708a  test    eax, eax
0x14004708c  jnz     loc_1400471BC
0x140047092  mov     eax, [rbx+0Ch]
0x140047095  cmp     eax, 0Bh
0x140047098  ja      loc_1400471BC
0x14004709e  mov     ecx, 0B40h
0x1400470a3  bt      ecx, eax
0x1400470a6  jnb     loc_1400471BC
0x1400470ac  cmp     qword ptr [rbx+0F0h], 0
0x1400470b4  jnz     short loc_1400470F5
0x1400470b6  lea     rcx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead; Lookaside
0x1400470bd  mov     qword ptr [rbx+0F0h], 0
0x1400470c8  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400470cf  nop     dword ptr [rax+rax+00h]
0x1400470d4  test    rax, rax
0x1400470d7  jz      short loc_1400470F5
0x1400470d9  mov     dword ptr [rax+8], 7A697377h
0x1400470e0  lea     rcx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400470e7  mov     [rax], rcx
0x1400470ea  add     rax, 10h
0x1400470ee  mov     [rbx+0F0h], rax
0x1400470f5  mov     rcx, [rbx+0F0h]
0x1400470fc  test    rcx, rcx
0x1400470ff  jz      loc_1400471BC
0x140047105  mov     rax, [rdi+68h]
0x140047109  movups  xmm0, xmmword ptr [rax]
0x14004710c  movups  xmmword ptr [rcx], xmm0
0x14004710f  movups  xmm1, xmmword ptr [rax+10h]
0x140047113  movups  xmmword ptr [rcx+10h], xmm1
0x140047117  movups  xmm0, xmmword ptr [rax+20h]
0x14004711b  movups  xmmword ptr [rcx+20h], xmm0
0x14004711f  movups  xmm1, xmmword ptr [rax+30h]
0x140047123  movups  xmmword ptr [rcx+30h], xmm1
0x140047127  movups  xmm0, xmmword ptr [rax+40h]
0x14004712b  movups  xmmword ptr [rcx+40h], xmm0
0x14004712f  movups  xmm1, xmmword ptr [rax+50h]
0x140047133  movups  xmmword ptr [rcx+50h], xmm1
0x140047137  movups  xmm0, xmmword ptr [rax+60h]
0x14004713b  movups  xmmword ptr [rcx+60h], xmm0
0x14004713f  movups  xmm1, xmmword ptr [rax+70h]
0x140047143  movups  xmmword ptr [rcx+70h], xmm1
0x140047147  movups  xmm0, xmmword ptr [rax+80h]
0x14004714e  movups  xmmword ptr [rcx+80h], xmm0
0x140047155  movups  xmm1, xmmword ptr [rax+90h]
0x14004715c  movups  xmmword ptr [rcx+90h], xmm1
0x140047163  movups  xmm0, xmmword ptr [rax+0A0h]
0x14004716a  movups  xmmword ptr [rcx+0A0h], xmm0
0x140047171  movups  xmm1, xmmword ptr [rax+0B0h]
0x140047178  movups  xmmword ptr [rcx+0B0h], xmm1
0x14004717f  movups  xmm0, xmmword ptr [rax+0C0h]
0x140047186  movups  xmmword ptr [rcx+0C0h], xmm0
0x14004718d  mov     rax, [rax+0D0h]
0x140047194  mov     [rcx+0D0h], rax
0x14004719b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400471a2  cmp     rcx, r13
0x1400471a5  jz      short loc_1400471BC
0x1400471a7  mov     rcx, [rcx+18h]
0x1400471ab  lea     r9, [rdi+10h]
0x1400471af  mov     edx, 182h
0x1400471b4  mov     r8, r12
0x1400471b7  call    WPP_SF__MAC_
0x1400471bc  call    Feature_53299205__private_IsEnabledDeviceUsageNoInline
0x1400471c1  test    eax, eax
0x1400471c3  jz      short loc_1400471D2
0x1400471c5  mov     rcx, rbx; this
0x1400471c8  call    ?CleanupRsnIEs@RsnOConnection@@YAXPEAU_NWF_KEY_CONTEXT@@@Z; RsnOConnection::CleanupRsnIEs(_NWF_KEY_CONTEXT *)
0x1400471cd  jmp     loc_1400472D2
0x1400471d2  mov     rcx, [rbx+38h]
0x1400471d6  test    rcx, rcx
0x1400471d9  jz      short loc_140047212
0x1400471db  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x1400471df  mov     rax, [rcx]
0x1400471e2  test    rax, rax
0x1400471e5  jz      short loc_1400471FB
0x1400471e7  mov     rdx, rcx; Entry
0x1400471ea  mov     rcx, rax; Lookaside
0x1400471ed  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400471f4  nop     dword ptr [rax+rax+00h]
0x1400471f9  jmp     short loc_14004720A
0x1400471fb  mov     edx, [rcx+8]; Tag
0x1400471fe  call    cs:__imp_ExFreePoolWithTag
0x140047205  nop     dword ptr [rax+rax+00h]
0x14004720a  mov     qword ptr [rbx+38h], 0
0x140047212  mov     rcx, [rbx+48h]
0x140047216  test    rcx, rcx
0x140047219  jz      short loc_140047252
0x14004721b  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14004721f  mov     rax, [rcx]
0x140047222  test    rax, rax
0x140047225  jz      short loc_14004723B
0x140047227  mov     rdx, rcx; Entry
0x14004722a  mov     rcx, rax; Lookaside
0x14004722d  call    cs:__imp_ExFreeToNPagedLookasideList
0x140047234  nop     dword ptr [rax+rax+00h]
0x140047239  jmp     short loc_14004724A
0x14004723b  mov     edx, [rcx+8]; Tag
0x14004723e  call    cs:__imp_ExFreePoolWithTag
0x140047245  nop     dword ptr [rax+rax+00h]
0x14004724a  mov     qword ptr [rbx+48h], 0
0x140047252  mov     rcx, [rbx+60h]
0x140047256  test    rcx, rcx
0x140047259  jz      short loc_140047292
0x14004725b  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14004725f  mov     rax, [rcx]
0x140047262  test    rax, rax
0x140047265  jz      short loc_14004727B
0x140047267  mov     rdx, rcx; Entry
0x14004726a  mov     rcx, rax; Lookaside
0x14004726d  call    cs:__imp_ExFreeToNPagedLookasideList
0x140047274  nop     dword ptr [rax+rax+00h]
0x140047279  jmp     short loc_14004728A
0x14004727b  mov     edx, [rcx+8]; Tag
0x14004727e  call    cs:__imp_ExFreePoolWithTag
0x140047285  nop     dword ptr [rax+rax+00h]
0x14004728a  mov     qword ptr [rbx+60h], 0
0x140047292  mov     rcx, [rbx+70h]
0x140047296  test    rcx, rcx
0x140047299  jz      short loc_1400472D2
0x14004729b  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14004729f  mov     rax, [rcx]
0x1400472a2  test    rax, rax
0x1400472a5  jz      short loc_1400472BB
0x1400472a7  mov     rdx, rcx; Entry
0x1400472aa  mov     rcx, rax; Lookaside
0x1400472ad  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400472b4  nop     dword ptr [rax+rax+00h]
0x1400472b9  jmp     short loc_1400472CA
0x1400472bb  mov     edx, [rcx+8]; Tag
0x1400472be  call    cs:__imp_ExFreePoolWithTag
0x1400472c5  nop     dword ptr [rax+rax+00h]
0x1400472ca  mov     qword ptr [rbx+70h], 0
0x1400472d2  mov     rcx, [rbx+58h]
0x1400472d6  test    rcx, rcx
0x1400472d9  jz      short loc_140047312
0x1400472db  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x1400472df  mov     rax, [rcx]
0x1400472e2  test    rax, rax
0x1400472e5  jz      short loc_1400472FB
0x1400472e7  mov     rdx, rcx; Entry
0x1400472ea  mov     rcx, rax; Lookaside
0x1400472ed  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400472f4  nop     dword ptr [rax+rax+00h]
0x1400472f9  jmp     short loc_14004730A
0x1400472fb  mov     edx, [rcx+8]; Tag
0x1400472fe  call    cs:__imp_ExFreePoolWithTag
0x140047305  nop     dword ptr [rax+rax+00h]
0x14004730a  mov     qword ptr [rbx+58h], 0
0x140047312  lea     rcx, [rbx+510h]; struct NWF_FT_CONTEXT **
0x140047319  call    ?FreeFTContext@@YAXPEAPEAUNWF_FT_CONTEXT@@@Z; FreeFTContext(NWF_FT_CONTEXT * *)
0x14004731e  mov     edx, 47h ; 'G'
0x140047323  mov     rcx, rsi
0x140047326  call    ?SAERequestCleanupConnection@@YAXPEAU_VELAN@@W4_DOT11_SAE_STATUS@@@Z; SAERequestCleanupConnection(_VELAN *,_DOT11_SAE_STATUS)
0x14004732b  lea     rcx, [rsi+17F0h]; struct DOT11_MAC_STATE_ENTRY **
0x140047332  cmp     qword ptr [rcx], 0
0x140047336  jz      short loc_14004733D
0x140047338  call    ?Dot11ReleaseMacState@@YAXPEAPEAUDOT11_MAC_STATE_ENTRY@@@Z; Dot11ReleaseMacState(DOT11_MAC_STATE_ENTRY * *)
0x14004733d  mov     rcx, [rbx+0E8h]
0x140047344  test    rcx, rcx
0x140047347  jz      short loc_140047383
0x140047349  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14004734d  mov     rax, [rcx]
0x140047350  test    rax, rax
0x140047353  jz      short loc_140047369
0x140047355  mov     rdx, rcx; Entry
0x140047358  mov     rcx, rax; Lookaside
0x14004735b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140047362  nop     dword ptr [rax+rax+00h]
0x140047367  jmp     short loc_140047378
0x140047369  mov     edx, [rcx+8]; Tag
0x14004736c  call    cs:__imp_ExFreePoolWithTag
0x140047373  nop     dword ptr [rax+rax+00h]
0x140047378  mov     qword ptr [rbx+0E8h], 0
0x140047383  mov     rdi, [rbx+0F0h]
0x14004738a  xor     edx, edx; unsigned __int64
0x14004738c  mov     rcx, rsi; struct _VELAN *
0x14004738f  call    ?SetReplayCounter@@YAXPEAU_VELAN@@_K@Z; SetReplayCounter(_VELAN *,unsigned __int64)
0x140047394  xor     edx, edx; int
0x140047396  mov     rcx, rsi; struct _VELAN *
0x140047399  call    ?SetRSNASecured@@YAXPEAU_VELAN@@H@Z; SetRSNASecured(_VELAN *,int)
0x14004739e  xor     edx, edx; Val
0x1400473a0  mov     r8d, 858h; Size
0x1400473a6  mov     rcx, rbx; void *
0x1400473a9  call    memset
0x1400473ae  mov     [rbx+0F0h], rdi
0x1400473b5  test    rdi, rdi
0x1400473b8  jz      loc_140047488
0x1400473be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400473c5  cmp     rcx, r13
0x1400473c8  jz      loc_140047488
0x1400473ce  mov     rcx, [rcx+18h]
0x1400473d2  mov     edx, 183h
0x1400473d7  mov     r8, r12
0x1400473da  call    WPP_SF_
0x1400473df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400473e6  cmp     rcx, r13
0x1400473e9  jz      loc_140047488
0x1400473ef  movzx   r9d, word ptr [rdi+4]
0x1400473f4  mov     edx, 184h
0x1400473f9  mov     rcx, [rcx+18h]
0x1400473fd  mov     r8, r12
0x140047400  call    WPP_SF_d
0x140047405  mov     rcx, cs:WPP_GLOBAL_Control
0x14004740c  cmp     rcx, r13
0x14004740f  jz      short loc_140047488
0x140047411  mov     rcx, [rcx+18h]
0x140047415  lea     r9, [rbp+var_10]
0x140047419  xorps   xmm0, xmm0
0x14004741c  mov     eax, 10h
0x140047421  movups  [rbp+var_10], xmm0
0x140047425  mov     word ptr [rbp+var_10], ax
0x140047429  mov     edx, 185h
0x14004742e  lea     rax, [rdi+18h]
0x140047432  mov     r8, r12
0x140047435  mov     qword ptr [rbp+var_10+8], rax
0x140047439  movaps  xmm0, [rbp+var_10]
0x14004743d  movdqa  [rbp+var_10], xmm0
0x140047442  call    WPP_SF__HEX_
0x140047447  mov     rcx, cs:WPP_GLOBAL_Control
0x14004744e  cmp     rcx, r13
0x140047451  jz      short loc_140047488
0x140047453  mov     r9, [rdi+10h]
0x140047457  mov     edx, 186h
0x14004745c  mov     rcx, [rcx+18h]
0x140047460  mov     r8, r12
0x140047463  call    WPP_SF_q
0x140047468  mov     rcx, cs:WPP_GLOBAL_Control
0x14004746f  cmp     rcx, r13
0x140047472  jz      short loc_140047488
  ... truncated ...
```
