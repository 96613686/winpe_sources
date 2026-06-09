# Dot11DeInitProtocol(_ADAPT *)

- ea: `0x14003bd08`
- end: `0x14003bea0`
- name: `?Dot11DeInitProtocol@@YAXPEAU_ADAPT@@@Z`
- size: `408`
- prototype: `void __fastcall(struct _ADAPT *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400358c0`
- `0x14003bf6c`

## callees

- `0x14000d22c`
- `0x140019bbc`
- `0x14003bd08`
- `0x14009a3d0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003bdb2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003bdf8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003be3e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003bdb2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003bdf8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003be3e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003bdc3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003be09`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003be4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003bdc3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003be09`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003be4f`

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
0x14003bd08  mov     [rsp+arg_8], rbx
0x14003bd0d  push    rsi
0x14003bd0e  sub     rsp, 50h
0x14003bd12  mov     rax, cs:__security_cookie
0x14003bd19  xor     rax, rsp
0x14003bd1c  mov     [rsp+58h+var_18], rax
0x14003bd21  xor     eax, eax
0x14003bd23  mov     rbx, rcx
0x14003bd26  mov     [rsp+58h+var_28], rax
0x14003bd2b  mov     [rsp+58h+var_20], eax
0x14003bd2f  mov     rcx, cs:WPP_GLOBAL_Control
0x14003bd36  lea     rsi, WPP_GLOBAL_Control
0x14003bd3d  cmp     rcx, rsi
0x14003bd40  jz      short loc_14003BD55
0x14003bd42  mov     rcx, [rcx+18h]
0x14003bd46  lea     edx, [rax+34h]
0x14003bd49  lea     r8, WPP_4f70633c889d3d5ba5e904434b809e78_Traceguids
0x14003bd50  call    WPP_SF_
0x14003bd55  mov     eax, [rbx+110h]
0x14003bd5b  lea     r9, [rsp+58h+var_28]; void *
0x14003bd60  mov     dword ptr [rsp+58h+var_28+4], eax
0x14003bd64  mov     edx, 0Ch; unsigned int
0x14003bd69  movzx   eax, word ptr [rbx+114h]
0x14003bd70  mov     r8d, 0D010310h; unsigned int
0x14003bd76  mov     rcx, rbx; struct _ADAPT *
0x14003bd79  mov     word ptr [rsp+58h+var_20], ax
0x14003bd7e  mov     byte ptr [rsp+58h+var_20+2], 0
0x14003bd83  mov     dword ptr [rsp+58h+var_28], 3
0x14003bd8b  mov     [rsp+58h+var_38], edx; unsigned int
0x14003bd8f  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x14003bd94  mov     rcx, [rbx+120h]
0x14003bd9b  test    rcx, rcx
0x14003bd9e  jz      short loc_14003BDDA
0x14003bda0  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14003bda4  mov     rax, [rcx]
0x14003bda7  test    rax, rax
0x14003bdaa  jz      short loc_14003BDC0
0x14003bdac  mov     rdx, rcx; Entry
0x14003bdaf  mov     rcx, rax; Lookaside
0x14003bdb2  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003bdb9  nop     dword ptr [rax+rax+00h]
0x14003bdbe  jmp     short loc_14003BDCF
0x14003bdc0  mov     edx, [rcx+8]; Tag
0x14003bdc3  call    cs:__imp_ExFreePoolWithTag
0x14003bdca  nop     dword ptr [rax+rax+00h]
0x14003bdcf  mov     qword ptr [rbx+120h], 0
0x14003bdda  mov     rcx, [rbx+690h]
0x14003bde1  test    rcx, rcx
0x14003bde4  jz      short loc_14003BE20
0x14003bde6  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14003bdea  mov     rax, [rcx]
0x14003bded  test    rax, rax
0x14003bdf0  jz      short loc_14003BE06
0x14003bdf2  mov     rdx, rcx; Entry
0x14003bdf5  mov     rcx, rax; Lookaside
0x14003bdf8  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003bdff  nop     dword ptr [rax+rax+00h]
0x14003be04  jmp     short loc_14003BE15
0x14003be06  mov     edx, [rcx+8]; Tag
0x14003be09  call    cs:__imp_ExFreePoolWithTag
0x14003be10  nop     dword ptr [rax+rax+00h]
0x14003be15  mov     qword ptr [rbx+690h], 0
0x14003be20  mov     rcx, [rbx+698h]
0x14003be27  test    rcx, rcx
0x14003be2a  jz      short loc_14003BE66
0x14003be2c  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14003be30  mov     rax, [rcx]
0x14003be33  test    rax, rax
0x14003be36  jz      short loc_14003BE4C
0x14003be38  mov     rdx, rcx; Entry
0x14003be3b  mov     rcx, rax; Lookaside
0x14003be3e  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003be45  nop     dword ptr [rax+rax+00h]
0x14003be4a  jmp     short loc_14003BE5B
0x14003be4c  mov     edx, [rcx+8]; Tag
0x14003be4f  call    cs:__imp_ExFreePoolWithTag
0x14003be56  nop     dword ptr [rax+rax+00h]
0x14003be5b  mov     qword ptr [rbx+698h], 0
0x14003be66  mov     rcx, cs:WPP_GLOBAL_Control
0x14003be6d  cmp     rcx, rsi
0x14003be70  jz      short loc_14003BE87
0x14003be72  mov     rcx, [rcx+18h]
0x14003be76  lea     r8, WPP_4f70633c889d3d5ba5e904434b809e78_Traceguids
0x14003be7d  mov     edx, 35h ; '5'
0x14003be82  call    WPP_SF_
0x14003be87  mov     rcx, [rsp+58h+var_18]
0x14003be8c  xor     rcx, rsp; StackCookie
0x14003be8f  call    __security_check_cookie
0x14003be94  mov     rbx, [rsp+58h+arg_8]
0x14003be99  add     rsp, 50h
0x14003be9d  pop     rsi
0x14003be9e  retn
```
