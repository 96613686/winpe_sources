# Dot11RsnaOnDisconnect(_VELAN *)

- ea: `0x140046910`
- end: `0x140046be7`
- name: `?Dot11RsnaOnDisconnect@@YAXPEAU_VELAN@@@Z`
- size: `727`
- prototype: `void __fastcall(struct _VELAN *)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x140036ab4`
- `0x1400631e8`

## callees

- `0x140013b90`
- `0x14001f664`
- `0x140020fbc`
- `0x140025028`
- `0x1400366f8`
- `0x140041398`
- `0x140046910`
- `0x140047998`
- `0x14004f7bc`
- `0x14004fbec`
- `0x14004fc44`
- `0x140053cb0`
- `0x14008f87c`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140046960`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400469a0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400469e0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140046a20`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140046a60`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140046ae6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140046b5c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140046960`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400469a0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400469e0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140046a20`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140046a60`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140046ae6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140046b5c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046971`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400469b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400469f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046a31`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046a71`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046af7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046b6d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046971`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400469b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400469f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046a31`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046a71`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046af7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046b6d`

## pseudocode

```c
void __fastcall Dot11RsnaOnDisconnect(struct _VELAN *a1, __int64 a2, __int64 a3, __int64 a4)
{
  _NWF_KEY_CONTEXT *p_KeyContext; // rbx
  int bRSNASecured; // esi
  struct _NWF_KEY_CONTEXT *v7; // rdx
  unsigned __int8 *pAssocRequestRsnIE; // rcx
  unsigned __int8 *v9; // rcx
  unsigned __int8 *pAssocRequestRsnXeIE; // rcx
  unsigned __int8 *v11; // rcx
  unsigned __int8 *pBeaconRsnIE; // rcx
  unsigned __int8 *v13; // rcx
  unsigned __int8 *pBeaconRsnXeIE; // rcx
  unsigned __int8 *v15; // rcx
  DOT11_CONNECTION_INFO *pConnectionInfo; // rcx
  ULONG *p_Rssi; // rcx
  struct NWF_EAPOL_HEADER *pEapolHdr; // rcx
  ULONG *v19; // rcx
  NWF_PMK_ENTRY *pOpPmk; // rcx
  NWF_PMK_ENTRY *v21; // rax
  NWF_PMK_ENTRY *v22; // rcx
  ULONG *v23; // rcx

  p_KeyContext = &a1->KeyContext;
  bRSNASecured = a1->KeyContext.bRSNASecured;
  if ( (unsigned int)Feature_53299205__private_IsEnabledDeviceUsageNoInline(a1, a2, a3, a4) )
  {
    RsnOConnection::CleanupRsnIEs((RsnOConnection *)p_KeyContext, v7);
  }
  else
  {
    pAssocRequestRsnIE = p_KeyContext->pAssocRequestRsnIE;
    if ( pAssocRequestRsnIE )
    {
      v9 = pAssocRequestRsnIE - 16;
      if ( *(_QWORD *)v9 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v9, v9);
      else
        ExFreePoolWithTag(v9, *((_DWORD *)v9 + 2));
      p_KeyContext->pAssocRequestRsnIE = 0;
    }
    pAssocRequestRsnXeIE = p_KeyContext->pAssocRequestRsnXeIE;
    if ( pAssocRequestRsnXeIE )
    {
      v11 = pAssocRequestRsnXeIE - 16;
      if ( *(_QWORD *)v11 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v11, v11);
      else
        ExFreePoolWithTag(v11, *((_DWORD *)v11 + 2));
      p_KeyContext->pAssocRequestRsnXeIE = 0;
    }
    pBeaconRsnIE = p_KeyContext->pBeaconRsnIE;
    if ( pBeaconRsnIE )
    {
      v13 = pBeaconRsnIE - 16;
      if ( *(_QWORD *)v13 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v13, v13);
      else
        ExFreePoolWithTag(v13, *((_DWORD *)v13 + 2));
      p_KeyContext->pBeaconRsnIE = 0;
    }
    pBeaconRsnXeIE = p_KeyContext->pBeaconRsnXeIE;
    if ( pBeaconRsnXeIE )
    {
      v15 = pBeaconRsnXeIE - 16;
      if ( *(_QWORD *)v15 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v15, v15);
      else
        ExFreePoolWithTag(v15, *((_DWORD *)v15 + 2));
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
  PmkCacheDeInit(&a1->Dot11PmkCache);
  Dot11DeallocateOWEContext(&a1->pOWEContext);
  if ( a1->KeyContext.M1Cache.pMacStateEntry )
    Dot11ReleaseMacState(&a1->KeyContext.M1Cache.pMacStateEntry);
  pEapolHdr = p_KeyContext->M1Cache.pEapolHdr;
  if ( pEapolHdr )
  {
    v19 = (ULONG *)((char *)pEapolHdr - 16);
    if ( *(_QWORD *)v19 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v19, v19);
    else
      ExFreePoolWithTag(v19, v19[2]);
    p_KeyContext->M1Cache.pEapolHdr = 0;
  }
  pOpPmk = p_KeyContext->pOpPmk;
  if ( pOpPmk )
  {
    memset(&pOpPmk->149, 0, sizeof(pOpPmk->149));
    v21 = p_KeyContext->pOpPmk;
    *(_OWORD *)v21->ucRecvKey = 0;
    *(_OWORD *)&v21->ucRecvKey[16] = 0;
    v22 = p_KeyContext->pOpPmk;
    if ( v22 )
    {
      v23 = (ULONG *)&v22[-1].ucKey[51];
      if ( *(_QWORD *)v23 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v23, v23);
      else
        ExFreePoolWithTag(v23, v23[2]);
      p_KeyContext->pOpPmk = 0;
    }
  }
  SetRSNASecured(a1, 0);
  SetReplayCounter(a1, 0);
  memset(p_KeyContext, 0, sizeof(_NWF_KEY_CONTEXT));
  DeletePMK(a1->pDefaultMacState);
  Dot11EnumMacState(&a1->MacStateTable, DeletePMKCallback, 0);
  if ( bRSNASecured )
    NotifySecureConnectionChange(a1);
}

```

## disassembly

```asm
0x140046910  mov     [rsp+arg_0], rbx
0x140046915  mov     [rsp+arg_8], rsi
0x14004691a  push    rdi
0x14004691b  sub     rsp, 20h
0x14004691f  lea     rbx, [rcx+1710h]
0x140046926  mov     rdi, rcx
0x140046929  mov     esi, [rbx+4E8h]
0x14004692f  call    Feature_53299205__private_IsEnabledDeviceUsageNoInline
0x140046934  test    eax, eax
0x140046936  jz      short loc_140046945
0x140046938  mov     rcx, rbx; this
0x14004693b  call    ?CleanupRsnIEs@RsnOConnection@@YAXPEAU_NWF_KEY_CONTEXT@@@Z; RsnOConnection::CleanupRsnIEs(_NWF_KEY_CONTEXT *)
0x140046940  jmp     loc_140046A45
0x140046945  mov     rcx, [rbx+38h]
0x140046949  test    rcx, rcx
0x14004694c  jz      short loc_140046985
0x14004694e  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140046952  mov     rax, [rcx]
0x140046955  test    rax, rax
0x140046958  jz      short loc_14004696E
0x14004695a  mov     rdx, rcx; Entry
0x14004695d  mov     rcx, rax; Lookaside
0x140046960  call    cs:__imp_ExFreeToNPagedLookasideList
0x140046967  nop     dword ptr [rax+rax+00h]
0x14004696c  jmp     short loc_14004697D
0x14004696e  mov     edx, [rcx+8]; Tag
0x140046971  call    cs:__imp_ExFreePoolWithTag
0x140046978  nop     dword ptr [rax+rax+00h]
0x14004697d  mov     qword ptr [rbx+38h], 0
0x140046985  mov     rcx, [rbx+48h]
0x140046989  test    rcx, rcx
0x14004698c  jz      short loc_1400469C5
0x14004698e  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140046992  mov     rax, [rcx]
0x140046995  test    rax, rax
0x140046998  jz      short loc_1400469AE
0x14004699a  mov     rdx, rcx; Entry
0x14004699d  mov     rcx, rax; Lookaside
0x1400469a0  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400469a7  nop     dword ptr [rax+rax+00h]
0x1400469ac  jmp     short loc_1400469BD
0x1400469ae  mov     edx, [rcx+8]; Tag
0x1400469b1  call    cs:__imp_ExFreePoolWithTag
0x1400469b8  nop     dword ptr [rax+rax+00h]
0x1400469bd  mov     qword ptr [rbx+48h], 0
0x1400469c5  mov     rcx, [rbx+60h]
0x1400469c9  test    rcx, rcx
0x1400469cc  jz      short loc_140046A05
0x1400469ce  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x1400469d2  mov     rax, [rcx]
0x1400469d5  test    rax, rax
0x1400469d8  jz      short loc_1400469EE
0x1400469da  mov     rdx, rcx; Entry
0x1400469dd  mov     rcx, rax; Lookaside
0x1400469e0  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400469e7  nop     dword ptr [rax+rax+00h]
0x1400469ec  jmp     short loc_1400469FD
0x1400469ee  mov     edx, [rcx+8]; Tag
0x1400469f1  call    cs:__imp_ExFreePoolWithTag
0x1400469f8  nop     dword ptr [rax+rax+00h]
0x1400469fd  mov     qword ptr [rbx+60h], 0
0x140046a05  mov     rcx, [rbx+70h]
0x140046a09  test    rcx, rcx
0x140046a0c  jz      short loc_140046A45
0x140046a0e  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140046a12  mov     rax, [rcx]
0x140046a15  test    rax, rax
0x140046a18  jz      short loc_140046A2E
0x140046a1a  mov     rdx, rcx; Entry
0x140046a1d  mov     rcx, rax; Lookaside
0x140046a20  call    cs:__imp_ExFreeToNPagedLookasideList
0x140046a27  nop     dword ptr [rax+rax+00h]
0x140046a2c  jmp     short loc_140046A3D
0x140046a2e  mov     edx, [rcx+8]; Tag
0x140046a31  call    cs:__imp_ExFreePoolWithTag
0x140046a38  nop     dword ptr [rax+rax+00h]
0x140046a3d  mov     qword ptr [rbx+70h], 0
0x140046a45  mov     rcx, [rbx+58h]
0x140046a49  test    rcx, rcx
0x140046a4c  jz      short loc_140046A85
0x140046a4e  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140046a52  mov     rax, [rcx]
0x140046a55  test    rax, rax
0x140046a58  jz      short loc_140046A6E
0x140046a5a  mov     rdx, rcx; Entry
0x140046a5d  mov     rcx, rax; Lookaside
0x140046a60  call    cs:__imp_ExFreeToNPagedLookasideList
0x140046a67  nop     dword ptr [rax+rax+00h]
0x140046a6c  jmp     short loc_140046A7D
0x140046a6e  mov     edx, [rcx+8]; Tag
0x140046a71  call    cs:__imp_ExFreePoolWithTag
0x140046a78  nop     dword ptr [rax+rax+00h]
0x140046a7d  mov     qword ptr [rbx+58h], 0
0x140046a85  lea     rcx, [rbx+510h]; struct NWF_FT_CONTEXT **
0x140046a8c  call    ?FreeFTContext@@YAXPEAPEAUNWF_FT_CONTEXT@@@Z; FreeFTContext(NWF_FT_CONTEXT * *)
0x140046a91  mov     edx, 47h ; 'G'
0x140046a96  mov     rcx, rdi
0x140046a99  call    ?SAERequestCleanupConnection@@YAXPEAU_VELAN@@W4_DOT11_SAE_STATUS@@@Z; SAERequestCleanupConnection(_VELAN *,_DOT11_SAE_STATUS)
0x140046a9e  lea     rcx, [rdi+1FE8h]; struct _DOT11_PMK_CACHE *
0x140046aa5  call    PmkCacheDeInit
0x140046aaa  lea     rcx, [rdi+2170h]; struct _OWE_CONTEXT **
0x140046ab1  call    ?Dot11DeallocateOWEContext@@YAXPEAPEAU_OWE_CONTEXT@@@Z; Dot11DeallocateOWEContext(_OWE_CONTEXT * *)
0x140046ab6  lea     rcx, [rdi+17F0h]; struct DOT11_MAC_STATE_ENTRY **
0x140046abd  cmp     qword ptr [rcx], 0
0x140046ac1  jz      short loc_140046AC8
0x140046ac3  call    ?Dot11ReleaseMacState@@YAXPEAPEAUDOT11_MAC_STATE_ENTRY@@@Z; Dot11ReleaseMacState(DOT11_MAC_STATE_ENTRY * *)
0x140046ac8  mov     rcx, [rbx+0E8h]
0x140046acf  test    rcx, rcx
0x140046ad2  jz      short loc_140046B0E
0x140046ad4  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140046ad8  mov     rax, [rcx]
0x140046adb  test    rax, rax
0x140046ade  jz      short loc_140046AF4
0x140046ae0  mov     rdx, rcx; Entry
0x140046ae3  mov     rcx, rax; Lookaside
0x140046ae6  call    cs:__imp_ExFreeToNPagedLookasideList
0x140046aed  nop     dword ptr [rax+rax+00h]
0x140046af2  jmp     short loc_140046B03
0x140046af4  mov     edx, [rcx+8]; Tag
0x140046af7  call    cs:__imp_ExFreePoolWithTag
0x140046afe  nop     dword ptr [rax+rax+00h]
0x140046b03  mov     qword ptr [rbx+0E8h], 0
0x140046b0e  mov     rcx, [rbx+0F0h]
0x140046b15  test    rcx, rcx
0x140046b18  jz      short loc_140046B84
0x140046b1a  xor     edx, edx; Val
0x140046b1c  add     rcx, 95h; void *
0x140046b23  lea     r8d, [rdx+41h]; Size
0x140046b27  call    memset
0x140046b2c  mov     rax, [rbx+0F0h]
0x140046b33  xorps   xmm0, xmm0
0x140046b36  movups  xmmword ptr [rax+34h], xmm0
0x140046b3a  movups  xmmword ptr [rax+44h], xmm0
0x140046b3e  mov     rcx, [rbx+0F0h]
0x140046b45  test    rcx, rcx
0x140046b48  jz      short loc_140046B84
0x140046b4a  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140046b4e  mov     rax, [rcx]
0x140046b51  test    rax, rax
0x140046b54  jz      short loc_140046B6A
0x140046b56  mov     rdx, rcx; Entry
0x140046b59  mov     rcx, rax; Lookaside
0x140046b5c  call    cs:__imp_ExFreeToNPagedLookasideList
0x140046b63  nop     dword ptr [rax+rax+00h]
0x140046b68  jmp     short loc_140046B79
0x140046b6a  mov     edx, [rcx+8]; Tag
0x140046b6d  call    cs:__imp_ExFreePoolWithTag
0x140046b74  nop     dword ptr [rax+rax+00h]
0x140046b79  mov     qword ptr [rbx+0F0h], 0
0x140046b84  xor     edx, edx; int
0x140046b86  mov     rcx, rdi; struct _VELAN *
0x140046b89  call    ?SetRSNASecured@@YAXPEAU_VELAN@@H@Z; SetRSNASecured(_VELAN *,int)
0x140046b8e  xor     edx, edx; unsigned __int64
0x140046b90  mov     rcx, rdi; struct _VELAN *
0x140046b93  call    ?SetReplayCounter@@YAXPEAU_VELAN@@_K@Z; SetReplayCounter(_VELAN *,unsigned __int64)
0x140046b98  xor     edx, edx; Val
0x140046b9a  mov     r8d, 858h; Size
0x140046ba0  mov     rcx, rbx; void *
0x140046ba3  call    memset
0x140046ba8  mov     rcx, [rdi+10D0h]
0x140046baf  call    DeletePMK
0x140046bb4  lea     rcx, [rdi+0A0h]; struct DOT11_MAC_STATE_MODULE *
0x140046bbb  xor     r8d, r8d; void *
0x140046bbe  lea     rdx, DeletePMKCallback; int (*)(struct DOT11_MAC_STATE_ENTRY *, void *)
0x140046bc5  call    ?Dot11EnumMacState@@YAXPEAUDOT11_MAC_STATE_MODULE@@P6AHPEAUDOT11_MAC_STATE_ENTRY@@PEAX@Z2@Z; Dot11EnumMacState(DOT11_MAC_STATE_MODULE *,int (*)(DOT11_MAC_STATE_ENTRY *,void *),void *)
0x140046bca  test    esi, esi
0x140046bcc  jz      short loc_140046BD6
0x140046bce  mov     rcx, rdi; struct _VELAN *
0x140046bd1  call    ?NotifySecureConnectionChange@@YAXPEAU_VELAN@@@Z; NotifySecureConnectionChange(_VELAN *)
0x140046bd6  mov     rbx, [rsp+28h+arg_0]
0x140046bdb  mov     rsi, [rsp+28h+arg_8]
0x140046be0  add     rsp, 20h
0x140046be4  pop     rdi
0x140046be5  retn
```
