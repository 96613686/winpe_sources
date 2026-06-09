# Dot11RsnaOnDisconnect(_VELAN *)

- ea: `0x1400474b4`
- end: `0x14004778b`
- name: `?Dot11RsnaOnDisconnect@@YAXPEAU_VELAN@@@Z`
- size: `727`
- prototype: `void __fastcall(struct _VELAN *)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x140036cd4`
- `0x140064a18`

## callees

- `0x140013b80`
- `0x14001f664`
- `0x140020fbc`
- `0x1400252ac`
- `0x140036918`
- `0x140041e34`
- `0x1400474b4`
- `0x140048c20`
- `0x140050f84`
- `0x1400513b4`
- `0x14005140c`
- `0x1400554d0`
- `0x14009105c`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047504`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047544`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047584`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400475c4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047604`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004768a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047700`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047504`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047544`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047584`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400475c4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047604`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004768a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140047700`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047515`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047555`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047595`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400475d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047615`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004769b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047711`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047515`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047555`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047595`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400475d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047615`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004769b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047711`

## pseudocode

```c
void __fastcall Dot11RsnaOnDisconnect(struct _VELAN *a1)
{
  _NWF_KEY_CONTEXT *p_KeyContext; // rbx
  int bRSNASecured; // esi
  struct _NWF_KEY_CONTEXT *v4; // rdx
  unsigned __int8 *pAssocRequestRsnIE; // rcx
  unsigned __int8 *v6; // rcx
  unsigned __int8 *pAssocRequestRsnXeIE; // rcx
  unsigned __int8 *v8; // rcx
  unsigned __int8 *pBeaconRsnIE; // rcx
  unsigned __int8 *v10; // rcx
  unsigned __int8 *pBeaconRsnXeIE; // rcx
  unsigned __int8 *v12; // rcx
  DOT11_CONNECTION_INFO *pConnectionInfo; // rcx
  ULONG *p_Rssi; // rcx
  struct NWF_EAPOL_HEADER *pEapolHdr; // rcx
  ULONG *v16; // rcx
  NWF_PMK_ENTRY *pOpPmk; // rcx
  NWF_PMK_ENTRY *v18; // rax
  NWF_PMK_ENTRY *v19; // rcx
  ULONG *v20; // rcx

  p_KeyContext = &a1->KeyContext;
  bRSNASecured = a1->KeyContext.bRSNASecured;
  if ( (unsigned int)Feature_53299205__private_IsEnabledDeviceUsageNoInline() )
  {
    RsnOConnection::CleanupRsnIEs((RsnOConnection *)p_KeyContext, v4);
  }
  else
  {
    pAssocRequestRsnIE = p_KeyContext->pAssocRequestRsnIE;
    if ( pAssocRequestRsnIE )
    {
      v6 = pAssocRequestRsnIE - 16;
      if ( *(_QWORD *)v6 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v6, v6);
      else
        ExFreePoolWithTag(v6, *((_DWORD *)v6 + 2));
      p_KeyContext->pAssocRequestRsnIE = 0;
    }
    pAssocRequestRsnXeIE = p_KeyContext->pAssocRequestRsnXeIE;
    if ( pAssocRequestRsnXeIE )
    {
      v8 = pAssocRequestRsnXeIE - 16;
      if ( *(_QWORD *)v8 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v8, v8);
      else
        ExFreePoolWithTag(v8, *((_DWORD *)v8 + 2));
      p_KeyContext->pAssocRequestRsnXeIE = 0;
    }
    pBeaconRsnIE = p_KeyContext->pBeaconRsnIE;
    if ( pBeaconRsnIE )
    {
      v10 = pBeaconRsnIE - 16;
      if ( *(_QWORD *)v10 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v10, v10);
      else
        ExFreePoolWithTag(v10, *((_DWORD *)v10 + 2));
      p_KeyContext->pBeaconRsnIE = 0;
    }
    pBeaconRsnXeIE = p_KeyContext->pBeaconRsnXeIE;
    if ( pBeaconRsnXeIE )
    {
      v12 = pBeaconRsnXeIE - 16;
      if ( *(_QWORD *)v12 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v12, v12);
      else
        ExFreePoolWithTag(v12, *((_DWORD *)v12 + 2));
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
    v16 = (ULONG *)((char *)pEapolHdr - 16);
    if ( *(_QWORD *)v16 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v16, v16);
    else
      ExFreePoolWithTag(v16, v16[2]);
    p_KeyContext->M1Cache.pEapolHdr = 0;
  }
  pOpPmk = p_KeyContext->pOpPmk;
  if ( pOpPmk )
  {
    memset(&pOpPmk->149, 0, sizeof(pOpPmk->149));
    v18 = p_KeyContext->pOpPmk;
    *(_OWORD *)v18->ucRecvKey = 0;
    *(_OWORD *)&v18->ucRecvKey[16] = 0;
    v19 = p_KeyContext->pOpPmk;
    if ( v19 )
    {
      v20 = (ULONG *)&v19[-1].ucKey[51];
      if ( *(_QWORD *)v20 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v20, v20);
      else
        ExFreePoolWithTag(v20, v20[2]);
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
0x1400474b4  mov     [rsp+arg_0], rbx
0x1400474b9  mov     [rsp+arg_8], rsi
0x1400474be  push    rdi
0x1400474bf  sub     rsp, 20h
0x1400474c3  lea     rbx, [rcx+1710h]
0x1400474ca  mov     rdi, rcx
0x1400474cd  mov     esi, [rbx+4E8h]
0x1400474d3  call    Feature_53299205__private_IsEnabledDeviceUsageNoInline
0x1400474d8  test    eax, eax
0x1400474da  jz      short loc_1400474E9
0x1400474dc  mov     rcx, rbx; this
0x1400474df  call    ?CleanupRsnIEs@RsnOConnection@@YAXPEAU_NWF_KEY_CONTEXT@@@Z; RsnOConnection::CleanupRsnIEs(_NWF_KEY_CONTEXT *)
0x1400474e4  jmp     loc_1400475E9
0x1400474e9  mov     rcx, [rbx+38h]
0x1400474ed  test    rcx, rcx
0x1400474f0  jz      short loc_140047529
0x1400474f2  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x1400474f6  mov     rax, [rcx]
0x1400474f9  test    rax, rax
0x1400474fc  jz      short loc_140047512
0x1400474fe  mov     rdx, rcx; Entry
0x140047501  mov     rcx, rax; Lookaside
0x140047504  call    cs:__imp_ExFreeToNPagedLookasideList
0x14004750b  nop     dword ptr [rax+rax+00h]
0x140047510  jmp     short loc_140047521
0x140047512  mov     edx, [rcx+8]; Tag
0x140047515  call    cs:__imp_ExFreePoolWithTag
0x14004751c  nop     dword ptr [rax+rax+00h]
0x140047521  mov     qword ptr [rbx+38h], 0
0x140047529  mov     rcx, [rbx+48h]
0x14004752d  test    rcx, rcx
0x140047530  jz      short loc_140047569
0x140047532  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140047536  mov     rax, [rcx]
0x140047539  test    rax, rax
0x14004753c  jz      short loc_140047552
0x14004753e  mov     rdx, rcx; Entry
0x140047541  mov     rcx, rax; Lookaside
0x140047544  call    cs:__imp_ExFreeToNPagedLookasideList
0x14004754b  nop     dword ptr [rax+rax+00h]
0x140047550  jmp     short loc_140047561
0x140047552  mov     edx, [rcx+8]; Tag
0x140047555  call    cs:__imp_ExFreePoolWithTag
0x14004755c  nop     dword ptr [rax+rax+00h]
0x140047561  mov     qword ptr [rbx+48h], 0
0x140047569  mov     rcx, [rbx+60h]
0x14004756d  test    rcx, rcx
0x140047570  jz      short loc_1400475A9
0x140047572  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140047576  mov     rax, [rcx]
0x140047579  test    rax, rax
0x14004757c  jz      short loc_140047592
0x14004757e  mov     rdx, rcx; Entry
0x140047581  mov     rcx, rax; Lookaside
0x140047584  call    cs:__imp_ExFreeToNPagedLookasideList
0x14004758b  nop     dword ptr [rax+rax+00h]
0x140047590  jmp     short loc_1400475A1
0x140047592  mov     edx, [rcx+8]; Tag
0x140047595  call    cs:__imp_ExFreePoolWithTag
0x14004759c  nop     dword ptr [rax+rax+00h]
0x1400475a1  mov     qword ptr [rbx+60h], 0
0x1400475a9  mov     rcx, [rbx+70h]
0x1400475ad  test    rcx, rcx
0x1400475b0  jz      short loc_1400475E9
0x1400475b2  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x1400475b6  mov     rax, [rcx]
0x1400475b9  test    rax, rax
0x1400475bc  jz      short loc_1400475D2
0x1400475be  mov     rdx, rcx; Entry
0x1400475c1  mov     rcx, rax; Lookaside
0x1400475c4  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400475cb  nop     dword ptr [rax+rax+00h]
0x1400475d0  jmp     short loc_1400475E1
0x1400475d2  mov     edx, [rcx+8]; Tag
0x1400475d5  call    cs:__imp_ExFreePoolWithTag
0x1400475dc  nop     dword ptr [rax+rax+00h]
0x1400475e1  mov     qword ptr [rbx+70h], 0
0x1400475e9  mov     rcx, [rbx+58h]
0x1400475ed  test    rcx, rcx
0x1400475f0  jz      short loc_140047629
0x1400475f2  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x1400475f6  mov     rax, [rcx]
0x1400475f9  test    rax, rax
0x1400475fc  jz      short loc_140047612
0x1400475fe  mov     rdx, rcx; Entry
0x140047601  mov     rcx, rax; Lookaside
0x140047604  call    cs:__imp_ExFreeToNPagedLookasideList
0x14004760b  nop     dword ptr [rax+rax+00h]
0x140047610  jmp     short loc_140047621
0x140047612  mov     edx, [rcx+8]; Tag
0x140047615  call    cs:__imp_ExFreePoolWithTag
0x14004761c  nop     dword ptr [rax+rax+00h]
0x140047621  mov     qword ptr [rbx+58h], 0
0x140047629  lea     rcx, [rbx+510h]; struct NWF_FT_CONTEXT **
0x140047630  call    ?FreeFTContext@@YAXPEAPEAUNWF_FT_CONTEXT@@@Z; FreeFTContext(NWF_FT_CONTEXT * *)
0x140047635  mov     edx, 47h ; 'G'
0x14004763a  mov     rcx, rdi
0x14004763d  call    ?SAERequestCleanupConnection@@YAXPEAU_VELAN@@W4_DOT11_SAE_STATUS@@@Z; SAERequestCleanupConnection(_VELAN *,_DOT11_SAE_STATUS)
0x140047642  lea     rcx, [rdi+1FE8h]; struct _DOT11_PMK_CACHE *
0x140047649  call    PmkCacheDeInit
0x14004764e  lea     rcx, [rdi+2170h]; struct _OWE_CONTEXT **
0x140047655  call    ?Dot11DeallocateOWEContext@@YAXPEAPEAU_OWE_CONTEXT@@@Z; Dot11DeallocateOWEContext(_OWE_CONTEXT * *)
0x14004765a  lea     rcx, [rdi+17F0h]; struct DOT11_MAC_STATE_ENTRY **
0x140047661  cmp     qword ptr [rcx], 0
0x140047665  jz      short loc_14004766C
0x140047667  call    ?Dot11ReleaseMacState@@YAXPEAPEAUDOT11_MAC_STATE_ENTRY@@@Z; Dot11ReleaseMacState(DOT11_MAC_STATE_ENTRY * *)
0x14004766c  mov     rcx, [rbx+0E8h]
0x140047673  test    rcx, rcx
0x140047676  jz      short loc_1400476B2
0x140047678  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14004767c  mov     rax, [rcx]
0x14004767f  test    rax, rax
0x140047682  jz      short loc_140047698
0x140047684  mov     rdx, rcx; Entry
0x140047687  mov     rcx, rax; Lookaside
0x14004768a  call    cs:__imp_ExFreeToNPagedLookasideList
0x140047691  nop     dword ptr [rax+rax+00h]
0x140047696  jmp     short loc_1400476A7
0x140047698  mov     edx, [rcx+8]; Tag
0x14004769b  call    cs:__imp_ExFreePoolWithTag
0x1400476a2  nop     dword ptr [rax+rax+00h]
0x1400476a7  mov     qword ptr [rbx+0E8h], 0
0x1400476b2  mov     rcx, [rbx+0F0h]
0x1400476b9  test    rcx, rcx
0x1400476bc  jz      short loc_140047728
0x1400476be  xor     edx, edx; Val
0x1400476c0  add     rcx, 95h; void *
0x1400476c7  lea     r8d, [rdx+41h]; Size
0x1400476cb  call    memset
0x1400476d0  mov     rax, [rbx+0F0h]
0x1400476d7  xorps   xmm0, xmm0
0x1400476da  movups  xmmword ptr [rax+34h], xmm0
0x1400476de  movups  xmmword ptr [rax+44h], xmm0
0x1400476e2  mov     rcx, [rbx+0F0h]
0x1400476e9  test    rcx, rcx
0x1400476ec  jz      short loc_140047728
0x1400476ee  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x1400476f2  mov     rax, [rcx]
0x1400476f5  test    rax, rax
0x1400476f8  jz      short loc_14004770E
0x1400476fa  mov     rdx, rcx; Entry
0x1400476fd  mov     rcx, rax; Lookaside
0x140047700  call    cs:__imp_ExFreeToNPagedLookasideList
0x140047707  nop     dword ptr [rax+rax+00h]
0x14004770c  jmp     short loc_14004771D
0x14004770e  mov     edx, [rcx+8]; Tag
0x140047711  call    cs:__imp_ExFreePoolWithTag
0x140047718  nop     dword ptr [rax+rax+00h]
0x14004771d  mov     qword ptr [rbx+0F0h], 0
0x140047728  xor     edx, edx; int
0x14004772a  mov     rcx, rdi; struct _VELAN *
0x14004772d  call    ?SetRSNASecured@@YAXPEAU_VELAN@@H@Z; SetRSNASecured(_VELAN *,int)
0x140047732  xor     edx, edx; unsigned __int64
0x140047734  mov     rcx, rdi; struct _VELAN *
0x140047737  call    ?SetReplayCounter@@YAXPEAU_VELAN@@_K@Z; SetReplayCounter(_VELAN *,unsigned __int64)
0x14004773c  xor     edx, edx; Val
0x14004773e  mov     r8d, 858h; Size
0x140047744  mov     rcx, rbx; void *
0x140047747  call    memset
0x14004774c  mov     rcx, [rdi+10D0h]
0x140047753  call    DeletePMK
0x140047758  lea     rcx, [rdi+0A0h]; struct DOT11_MAC_STATE_MODULE *
0x14004775f  xor     r8d, r8d; void *
0x140047762  lea     rdx, DeletePMKCallback; int (*)(struct DOT11_MAC_STATE_ENTRY *, void *)
0x140047769  call    ?Dot11EnumMacState@@YAXPEAUDOT11_MAC_STATE_MODULE@@P6AHPEAUDOT11_MAC_STATE_ENTRY@@PEAX@Z2@Z; Dot11EnumMacState(DOT11_MAC_STATE_MODULE *,int (*)(DOT11_MAC_STATE_ENTRY *,void *),void *)
0x14004776e  test    esi, esi
0x140047770  jz      short loc_14004777A
0x140047772  mov     rcx, rdi; struct _VELAN *
0x140047775  call    ?NotifySecureConnectionChange@@YAXPEAU_VELAN@@@Z; NotifySecureConnectionChange(_VELAN *)
0x14004777a  mov     rbx, [rsp+28h+arg_0]
0x14004777f  mov     rsi, [rsp+28h+arg_8]
0x140047784  add     rsp, 20h
0x140047788  pop     rdi
0x140047789  retn
```
