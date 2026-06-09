# Dot11DeInitProtocol(_ADAPT *)

- ea: `0x14003bf28`
- end: `0x14003c0c0`
- name: `?Dot11DeInitProtocol@@YAXPEAU_ADAPT@@@Z`
- size: `408`
- prototype: `void __fastcall(struct _ADAPT *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140035ae0`
- `0x14003c18c`

## callees

- `0x14000d21c`
- `0x140019bbc`
- `0x14003bf28`
- `0x14009bbb0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003bfd2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003c018`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003c05e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003bfd2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003c018`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003c05e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003bfe3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c029`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c06f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003bfe3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c029`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c06f`

## pseudocode

```c
void __fastcall Dot11DeInitProtocol(struct _ADAPT *a1)
{
  _DOT11_SUPPORTED_PHY_TYPES *pDot11SupportedPhyTypes; // rcx
  ULONG *dot11PHYType; // rcx
  _DOT11_BAND_CAPABILITIES *pBandCapabilities; // rcx
  unsigned int *p_uChannelFrequenciesOffset; // rcx
  DOT11_FIPS_CAPABILITIES *fipsCapabilities; // rcx
  ULONG *FIPSCertifiedCipherAlgorithmsList; // rcx
  __int64 v8; // [rsp+30h] [rbp-28h] BYREF
  int v9; // [rsp+38h] [rbp-20h]

  v8 = 0;
  v9 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_4f70633c889d3d5ba5e904434b809e78_Traceguids);
  HIDWORD(v8) = *(_DWORD *)a1->CurrentAddress;
  LOWORD(v9) = *(_WORD *)&a1->CurrentAddress[4];
  BYTE2(v9) = 0;
  LODWORD(v8) = 3;
  PtRequestAdapterSync(a1, 0xCu, 0xD010310u, &v8, 0xCu);
  pDot11SupportedPhyTypes = a1->pDot11SupportedPhyTypes;
  if ( pDot11SupportedPhyTypes )
  {
    dot11PHYType = (ULONG *)pDot11SupportedPhyTypes[-2].dot11PHYType;
    if ( *(_QWORD *)dot11PHYType )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)dot11PHYType, dot11PHYType);
    else
      ExFreePoolWithTag(dot11PHYType, dot11PHYType[2]);
    a1->pDot11SupportedPhyTypes = 0;
  }
  pBandCapabilities = a1->pBandCapabilities;
  if ( pBandCapabilities )
  {
    p_uChannelFrequenciesOffset = &pBandCapabilities[-1].BandDescriptors[0].uChannelFrequenciesOffset;
    if ( *(_QWORD *)p_uChannelFrequenciesOffset )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)p_uChannelFrequenciesOffset, p_uChannelFrequenciesOffset);
    else
      ExFreePoolWithTag(p_uChannelFrequenciesOffset, p_uChannelFrequenciesOffset[2]);
    a1->pBandCapabilities = 0;
  }
  fipsCapabilities = a1->fipsCapabilities;
  if ( fipsCapabilities )
  {
    FIPSCertifiedCipherAlgorithmsList = (ULONG *)fipsCapabilities[-2].FIPSCertifiedCipherAlgorithmsList;
    if ( *(_QWORD *)FIPSCertifiedCipherAlgorithmsList )
      ExFreeToNPagedLookasideList(
        *(PNPAGED_LOOKASIDE_LIST *)FIPSCertifiedCipherAlgorithmsList,
        FIPSCertifiedCipherAlgorithmsList);
    else
      ExFreePoolWithTag(FIPSCertifiedCipherAlgorithmsList, FIPSCertifiedCipherAlgorithmsList[2]);
    a1->fipsCapabilities = 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_4f70633c889d3d5ba5e904434b809e78_Traceguids);
}

```

## disassembly

```asm
0x14003bf28  mov     [rsp+arg_8], rbx
0x14003bf2d  push    rsi
0x14003bf2e  sub     rsp, 50h
0x14003bf32  mov     rax, cs:__security_cookie
0x14003bf39  xor     rax, rsp
0x14003bf3c  mov     [rsp+58h+var_18], rax
0x14003bf41  xor     eax, eax
0x14003bf43  mov     rbx, rcx
0x14003bf46  mov     [rsp+58h+var_28], rax
0x14003bf4b  mov     [rsp+58h+var_20], eax
0x14003bf4f  mov     rcx, cs:WPP_GLOBAL_Control
0x14003bf56  lea     rsi, WPP_GLOBAL_Control
0x14003bf5d  cmp     rcx, rsi
0x14003bf60  jz      short loc_14003BF75
0x14003bf62  mov     rcx, [rcx+18h]
0x14003bf66  lea     edx, [rax+34h]
0x14003bf69  lea     r8, WPP_4f70633c889d3d5ba5e904434b809e78_Traceguids
0x14003bf70  call    WPP_SF_
0x14003bf75  mov     eax, [rbx+110h]
0x14003bf7b  lea     r9, [rsp+58h+var_28]; void *
0x14003bf80  mov     dword ptr [rsp+58h+var_28+4], eax
0x14003bf84  mov     edx, 0Ch; unsigned int
0x14003bf89  movzx   eax, word ptr [rbx+114h]
0x14003bf90  mov     r8d, 0D010310h; unsigned int
0x14003bf96  mov     rcx, rbx; struct _ADAPT *
0x14003bf99  mov     word ptr [rsp+58h+var_20], ax
0x14003bf9e  mov     byte ptr [rsp+58h+var_20+2], 0
0x14003bfa3  mov     dword ptr [rsp+58h+var_28], 3
0x14003bfab  mov     [rsp+58h+var_38], edx; unsigned int
0x14003bfaf  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x14003bfb4  mov     rcx, [rbx+120h]
0x14003bfbb  test    rcx, rcx
0x14003bfbe  jz      short loc_14003BFFA
0x14003bfc0  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14003bfc4  mov     rax, [rcx]
0x14003bfc7  test    rax, rax
0x14003bfca  jz      short loc_14003BFE0
0x14003bfcc  mov     rdx, rcx; Entry
0x14003bfcf  mov     rcx, rax; Lookaside
0x14003bfd2  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003bfd9  nop     dword ptr [rax+rax+00h]
0x14003bfde  jmp     short loc_14003BFEF
0x14003bfe0  mov     edx, [rcx+8]; Tag
0x14003bfe3  call    cs:__imp_ExFreePoolWithTag
0x14003bfea  nop     dword ptr [rax+rax+00h]
0x14003bfef  mov     qword ptr [rbx+120h], 0
0x14003bffa  mov     rcx, [rbx+690h]
0x14003c001  test    rcx, rcx
0x14003c004  jz      short loc_14003C040
0x14003c006  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14003c00a  mov     rax, [rcx]
0x14003c00d  test    rax, rax
0x14003c010  jz      short loc_14003C026
0x14003c012  mov     rdx, rcx; Entry
0x14003c015  mov     rcx, rax; Lookaside
0x14003c018  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003c01f  nop     dword ptr [rax+rax+00h]
0x14003c024  jmp     short loc_14003C035
0x14003c026  mov     edx, [rcx+8]; Tag
0x14003c029  call    cs:__imp_ExFreePoolWithTag
0x14003c030  nop     dword ptr [rax+rax+00h]
0x14003c035  mov     qword ptr [rbx+690h], 0
0x14003c040  mov     rcx, [rbx+698h]
0x14003c047  test    rcx, rcx
0x14003c04a  jz      short loc_14003C086
0x14003c04c  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14003c050  mov     rax, [rcx]
0x14003c053  test    rax, rax
0x14003c056  jz      short loc_14003C06C
0x14003c058  mov     rdx, rcx; Entry
0x14003c05b  mov     rcx, rax; Lookaside
0x14003c05e  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003c065  nop     dword ptr [rax+rax+00h]
0x14003c06a  jmp     short loc_14003C07B
0x14003c06c  mov     edx, [rcx+8]; Tag
0x14003c06f  call    cs:__imp_ExFreePoolWithTag
0x14003c076  nop     dword ptr [rax+rax+00h]
0x14003c07b  mov     qword ptr [rbx+698h], 0
0x14003c086  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c08d  cmp     rcx, rsi
0x14003c090  jz      short loc_14003C0A7
0x14003c092  mov     rcx, [rcx+18h]
0x14003c096  lea     r8, WPP_4f70633c889d3d5ba5e904434b809e78_Traceguids
0x14003c09d  mov     edx, 35h ; '5'
0x14003c0a2  call    WPP_SF_
0x14003c0a7  mov     rcx, [rsp+58h+var_18]
0x14003c0ac  xor     rcx, rsp; StackCookie
0x14003c0af  call    __security_check_cookie
0x14003c0b4  mov     rbx, [rsp+58h+arg_8]
0x14003c0b9  add     rsp, 50h
0x14003c0bd  pop     rsi
0x14003c0be  retn
```
