# FatCreateNewDirent

- ea: `0x14003062c`
- end: `0x140030afb`
- name: `FatCreateNewDirent`
- size: `1231`
- prototype: `__int64 __fastcall(int, int, ULONG NumberToSet)`
- caller_count: `7`
- callee_count: `8`
- tags: ``

## callers

- `0x14000363c`
- `0x140028cc0`
- `0x140029774`
- `0x1400333d0`
- `0x140035e50`
- `0x14003bea4`
- `0x14004ab20`

## callees

- `0x1400019b8`
- `0x140024020`
- `0x140024228`
- `0x140024584`
- `0x14003062c`
- `0x140030b04`
- `0x140032ff0`
- `0x14003958c`

## import_xrefs

- `ntoskrnl!RtlClearBits` at `0x14003093a`
- `ntoskrnl!RtlClearBits` at `0x14003093a`
- `ntoskrnl!RtlSetBits` at `0x140030aa9`
- `ntoskrnl!RtlSetBits` at `0x140030aa9`
- `ntoskrnl!CcUnpinData` at `0x1400307f3`
- `ntoskrnl!CcUnpinData` at `0x140030951`
- `ntoskrnl!CcUnpinData` at `0x1400309ae`
- `ntoskrnl!CcUnpinData` at `0x1400309d6`
- `ntoskrnl!CcUnpinData` at `0x140030a85`
- `ntoskrnl!CcUnpinData` at `0x14005cf68`
- `ntoskrnl!CcUnpinData` at `0x14005cf8e`
- `ntoskrnl!CcUnpinData` at `0x14005cfb4`
- `ntoskrnl!CcUnpinData` at `0x1400307f3`
- `ntoskrnl!CcUnpinData` at `0x140030951`
- `ntoskrnl!CcUnpinData` at `0x1400309ae`
- `ntoskrnl!CcUnpinData` at `0x1400309d6`
- `ntoskrnl!CcUnpinData` at `0x140030a85`
- `ntoskrnl!CcUnpinData` at `0x14005cf68`
- `ntoskrnl!CcUnpinData` at `0x14005cf8e`
- `ntoskrnl!CcUnpinData` at `0x14005cfb4`
- `ntoskrnl!RtlFindClearBits` at `0x1400306c5`
- `ntoskrnl!RtlFindClearBits` at `0x1400306c5`
- `ntoskrnl!ExRaiseStatus` at `0x140030869`
- `ntoskrnl!ExRaiseStatus` at `0x140030a73`
- `ntoskrnl!ExRaiseStatus` at `0x140030aee`
- `ntoskrnl!ExRaiseStatus` at `0x140030869`
- `ntoskrnl!ExRaiseStatus` at `0x140030a73`
- `ntoskrnl!ExRaiseStatus` at `0x140030aee`

## pseudocode

```c
__int64 __fastcall FatCreateNewDirent(__int64 a1, __int64 a2, ULONG NumberToSet)
{
  __int64 v3; // r12
  unsigned int v6; // esi
  _DWORD *v7; // rdx
  unsigned int v8; // edi
  int ClearBits; // edi
  __int64 v10; // rcx
  _DWORD *v11; // rax
  int v12; // ecx
  unsigned __int64 v13; // r15
  int v14; // r9d
  _BYTE *v15; // rcx
  PVOID v16; // rcx
  unsigned int i; // r15d
  unsigned __int64 v18; // r13
  unsigned int v19; // r13d
  PVOID *v21; // [rsp+30h] [rbp-68h]
  PVOID Bcb; // [rsp+58h] [rbp-40h] BYREF
  PVOID v23; // [rsp+60h] [rbp-38h] BYREF
  PVOID v24; // [rsp+68h] [rbp-30h] BYREF
  int v25; // [rsp+A8h] [rbp+10h]
  __int64 v26; // [rsp+B8h] [rbp+20h] BYREF

  v3 = NumberToSet;
  Bcb = 0;
  v23 = 0;
  LODWORD(v26) = 0;
  v6 = *(_DWORD *)(a2 + 376);
  if ( v6 == -1 )
  {
    FatRescanDirectory(a1, a2);
    v6 = *(_DWORD *)(a2 + 376);
  }
  v25 = *(_DWORD *)(a2 + 380);
  v7 = (_DWORD *)(a2 + 24);
  if ( 32 * v3 + (unsigned __int64)v6 <= *(unsigned int *)(a2 + 24) )
  {
    v8 = v6;
    v6 += 32 * v3;
    goto LABEL_23;
  }
  ClearBits = RtlFindClearBits((PRTL_BITMAP)(a2 + 400), v3, *(_DWORD *)(a2 + 380) >> 5);
  v10 = a2 + 184;
  if ( *(_BYTE *)(*(_QWORD *)(a2 + 184) + 376LL) == 32 || ClearBits != -1 )
  {
    v7 = (_DWORD *)(a2 + 24);
  }
  else
  {
    v7 = (_DWORD *)(a2 + 24);
    if ( *(_WORD *)a2 == 1284 && *v7 <= 0x40000u )
    {
      ClearBits = FatDefragDirectory(a1, a2, v3);
      v11 = (_DWORD *)(a2 + 24);
      v10 = a2 + 184;
      v7 = (_DWORD *)(a2 + 24);
      goto LABEL_12;
    }
  }
  v11 = v7;
LABEL_12:
  if ( ClearBits == -1 )
  {
    if ( *v11 >= 0x200000u || *(_BYTE *)(*(_QWORD *)v10 + 376LL) != 32 && *(_WORD *)a2 == 1284 )
    {
      *(_DWORD *)(a1 + 72) = -1073741078;
      ExRaiseStatus(-1073741078);
    }
    v8 = v6;
    v6 += 32 * v3;
    Bcb = 0;
    v24 = 0;
    FatPrepareWriteDirectoryFile(a1, a2, v6, 1u, &Bcb, &v24, (__int64)v21, 1, &v26);
    if ( Bcb )
      CcUnpinData(Bcb);
    v7 = (_DWORD *)(a2 + 24);
  }
  else
  {
    v8 = 32 * ClearBits;
    v12 = 32 * v3;
    if ( v8 == v25 )
      v25 += v12;
    if ( 32 * v3 + (unsigned __int64)v8 > v6 )
      v6 = v8 + v12;
  }
LABEL_23:
  Bcb = 0;
  if ( (byte_140017D4C & 1) != 0 && (_DWORD)v3 == 1 && v8 > (unsigned __int64)(*(_WORD *)a2 != 1284 ? 0x40 : 0) )
  {
    v13 = v8 - 32LL;
    if ( v13 >= (unsigned int)*v7 )
    {
      LODWORD(v26) = -1073741807;
      goto LABEL_28;
    }
    FatReadDirectoryFile(a1, a2, (v8 - 32) & 0xFFFFF000, 0x1000u, 0, &Bcb, &v23, &v26);
    v15 = (char *)v23 + (v13 & 0xFFF);
    v23 = v15;
    if ( (_DWORD)v26 || !*v15 )
    {
LABEL_28:
      FatPopUpFileCorrupt(a1, (struct _UNICODE_STRING *)a2);
      *(_DWORD *)(a1 + 72) = -1073741566;
      ExRaiseStatus(-1073741566);
    }
    if ( v15[11] == 15 && *v15 != 0xE5 )
    {
      FatPinMappedData(a1, a2, v8 - 32, v14, &Bcb);
      *(_BYTE *)v23 = -27;
      FatSetDirtyBcb(a1, Bcb, *(_QWORD *)(a2 + 184), 1);
      RtlClearBits((PRTL_BITMAP)(a2 + 400), v13 >> 5, 1u);
    }
    if ( Bcb )
    {
      CcUnpinData(Bcb);
      Bcb = 0;
    }
  }
  v16 = 0;
  Bcb = 0;
  for ( i = 0; i < (unsigned int)v3; ++i )
  {
    v18 = v8 + 32LL * i;
    if ( v18 < *(unsigned int *)(a2 + 24) )
    {
      v19 = v18 & 0xFFF;
      if ( !v19 || !v16 )
      {
        if ( v16 )
        {
          CcUnpinData(v16);
          Bcb = 0;
        }
        FatReadDirectoryFile(a1, a2, (v8 + 32 * i) & 0xFFFFF000, 0x1000u, 0, &Bcb, &v23, &v26);
        v23 = (char *)v23 + v19;
        v16 = Bcb;
      }
    }
    else
    {
      LODWORD(v26) = -1073741807;
      if ( v16 )
      {
        CcUnpinData(v16);
        v16 = 0;
        Bcb = 0;
      }
    }
    if ( (_DWORD)v26 || *(_BYTE *)v23 && *(_BYTE *)v23 != 0xE5 )
    {
      FatPopUpFileCorrupt(a1, (struct _UNICODE_STRING *)a2);
      *(_DWORD *)(a1 + 72) = -1073741566;
      ExRaiseStatus(-1073741566);
    }
  }
  if ( v16 )
  {
    CcUnpinData(v16);
    Bcb = 0;
  }
  RtlSetBits((PRTL_BITMAP)(a2 + 400), v8 >> 5, v3);
  *(_DWORD *)(a2 + 376) = v6;
  *(_DWORD *)(a2 + 380) = v25;
  return v8;
}

```

## disassembly

```asm
0x14003062c  mov     r11, rsp
0x14003062f  mov     [r11+8], rbx
0x140030633  mov     [r11+18h], rsi
0x140030637  mov     [r11+20h], r9b
0x14003063b  push    rdi
0x14003063c  push    r12
0x14003063e  push    r13
0x140030640  push    r14
0x140030642  push    r15
0x140030644  sub     rsp, 70h
0x140030648  mov     r12d, r8d
0x14003064b  mov     rbx, rdx
0x14003064e  mov     r14, rcx
0x140030651  xor     eax, eax
0x140030653  mov     [r11-40h], rax
0x140030657  mov     [r11-38h], rax
0x14003065b  mov     [r11+20h], eax
0x14003065f  mov     esi, [rdx+178h]
0x140030665  or      r15d, 0FFFFFFFFh
0x140030669  cmp     esi, r15d
0x14003066c  jnz     short loc_140030679
0x14003066e  call    FatRescanDirectory
0x140030673  mov     esi, [rbx+178h]
0x140030679  mov     r9d, [rbx+17Ch]
0x140030680  mov     [rsp+98h+arg_8], r9d
0x140030688  mov     r13, r12
0x14003068b  shl     r13, 5
0x14003068f  mov     ecx, esi
0x140030691  lea     rdx, [rbx+18h]
0x140030695  add     rcx, r13
0x140030698  mov     eax, [rdx]
0x14003069a  cmp     rcx, rax
0x14003069d  ja      short loc_1400306B4
0x14003069f  mov     edi, esi
0x1400306a1  mov     eax, r12d
0x1400306a4  shl     eax, 5
0x1400306a7  add     esi, eax
0x1400306a9  mov     r15d, 504h
0x1400306af  jmp     loc_140030803
0x1400306b4  mov     r8d, r9d
0x1400306b7  shr     r8d, 5; HintIndex
0x1400306bb  lea     rcx, [rbx+190h]; BitMapHeader
0x1400306c2  mov     edx, r12d; NumberToFind
0x1400306c5  call    cs:__imp_RtlFindClearBits
0x1400306cc  nop     dword ptr [rax+rax+00h]
0x1400306d1  mov     edi, eax
0x1400306d3  lea     rcx, [rbx+0B8h]
0x1400306da  mov     rax, [rcx]
0x1400306dd  cmp     byte ptr [rax+178h], 20h ; ' '
0x1400306e4  jz      short loc_140030724
0x1400306e6  cmp     edi, r15d
0x1400306e9  jnz     short loc_140030724
0x1400306eb  mov     r15d, 504h
0x1400306f1  lea     rdx, [rbx+18h]
0x1400306f5  cmp     [rbx], r15w
0x1400306f9  jnz     short loc_14003072E
0x1400306fb  cmp     dword ptr [rdx], 40000h
0x140030701  ja      short loc_14003072E
0x140030703  mov     r8d, r12d
0x140030706  mov     rdx, rbx
0x140030709  mov     rcx, r14
0x14003070c  call    FatDefragDirectory
0x140030711  mov     edi, eax
0x140030713  lea     rax, [rbx+18h]
0x140030717  lea     rcx, [rbx+0B8h]
0x14003071e  lea     rdx, [rbx+18h]
0x140030722  jmp     short loc_140030731
0x140030724  lea     rdx, [rbx+18h]
0x140030728  mov     r15d, 504h
0x14003072e  mov     rax, rdx
0x140030731  cmp     edi, 0FFFFFFFFh
0x140030734  jz      short loc_140030770
0x140030736  shl     edi, 5
0x140030739  mov     r9d, [rsp+98h+arg_8]
0x140030741  mov     ecx, r12d
0x140030744  shl     ecx, 5
0x140030747  cmp     edi, r9d
0x14003074a  jnz     short loc_140030757
0x14003074c  add     r9d, ecx
0x14003074f  mov     [rsp+98h+arg_8], r9d
0x140030757  mov     eax, edi
0x140030759  add     rax, r13
0x14003075c  mov     r8d, esi
0x14003075f  cmp     rax, r8
0x140030762  jbe     loc_140030803
0x140030768  lea     esi, [rdi+rcx]
0x14003076b  jmp     loc_140030803
0x140030770  cmp     dword ptr [rax], 200000h
0x140030776  jnb     loc_140030AE5
0x14003077c  mov     rax, [rcx]
0x14003077f  cmp     byte ptr [rax+178h], 20h ; ' '
0x140030786  jz      short loc_140030792
0x140030788  cmp     [rbx], r15w
0x14003078c  jz      loc_140030AE5
0x140030792  mov     edi, esi
0x140030794  mov     eax, r12d
0x140030797  shl     eax, 5
0x14003079a  add     esi, eax
0x14003079c  mov     [rsp+98h+Bcb], 0
0x1400307a5  mov     [rsp+98h+var_30], 0
0x1400307ae  lea     rax, [rsp+98h+arg_18]
0x1400307b6  mov     [rsp+98h+var_58], rax
0x1400307bb  mov     byte ptr [rsp+98h+var_60], 1
0x1400307c0  lea     rax, [rsp+98h+var_30]
0x1400307c5  mov     [rsp+98h+var_70], rax
0x1400307ca  lea     rax, [rsp+98h+Bcb]
0x1400307cf  mov     [rsp+98h+var_78], rax
0x1400307d4  mov     r9d, 1
0x1400307da  mov     r8d, esi
0x1400307dd  mov     rdx, rbx
0x1400307e0  mov     rcx, r14
0x1400307e3  call    FatPrepareWriteDirectoryFile
0x1400307e8  nop
0x1400307e9  mov     rcx, [rsp+98h+Bcb]; Bcb
0x1400307ee  test    rcx, rcx
0x1400307f1  jz      short loc_1400307FF
0x1400307f3  call    cs:__imp_CcUnpinData
0x1400307fa  nop     dword ptr [rax+rax+00h]
0x1400307ff  lea     rdx, [rbx+18h]
0x140030803  mov     [rsp+98h+Bcb], 0
0x14003080c  mov     al, cs:byte_140017D4C
0x140030812  test    al, 1
0x140030814  jz      loc_140030966
0x14003081a  cmp     r12d, 1
0x14003081e  jnz     loc_140030966
0x140030824  mov     ecx, edi
0x140030826  movzx   eax, word ptr [rbx]
0x140030829  sub     ax, r15w
0x14003082d  neg     ax
0x140030830  sbb     rax, rax
0x140030833  and     eax, 40h
0x140030836  cmp     rcx, rax
0x140030839  jbe     loc_140030966
0x14003083f  lea     r15, [rcx-20h]
0x140030843  mov     eax, [rdx]
0x140030845  cmp     r15, rax
0x140030848  jb      short loc_140030875
0x14003084a  mov     dword ptr [rsp+98h+arg_18], 0C0000011h
0x140030855  mov     rdx, rbx
0x140030858  mov     rcx, r14
0x14003085b  call    FatPopUpFileCorrupt
0x140030860  mov     ecx, 0C0000102h; Status
0x140030865  mov     [r14+48h], ecx
0x140030869  call    cs:__imp_ExRaiseStatus
0x140030875  lea     r8d, [rdi-20h]
0x140030879  and     r8d, 0FFFFF000h; int
0x140030880  lea     rax, [rsp+98h+arg_18]
0x140030888  mov     [rsp+98h+var_60], rax; __int64
0x14003088d  lea     rax, [rsp+98h+var_38]
0x140030892  mov     [rsp+98h+var_68], rax; PVOID *
0x140030897  lea     rax, [rsp+98h+Bcb]
0x14003089c  mov     [rsp+98h+var_70], rax; PVOID *
0x1400308a1  mov     byte ptr [rsp+98h+var_78], 0; char
0x1400308a6  mov     r9d, 1000h; int
0x1400308ac  mov     rdx, rbx; int
0x1400308af  mov     rcx, r14; int
0x1400308b2  call    FatReadDirectoryFile
0x1400308b7  mov     rax, r15
0x1400308ba  and     eax, 0FFFh
0x1400308bf  mov     rcx, [rsp+98h+var_38]
0x1400308c4  add     rcx, rax
0x1400308c7  mov     [rsp+98h+var_38], rcx
0x1400308cc  cmp     dword ptr [rsp+98h+arg_18], 0
0x1400308d4  jnz     loc_140030855
0x1400308da  mov     al, [rcx]
0x1400308dc  test    al, al
0x1400308de  jz      loc_140030855
0x1400308e4  cmp     byte ptr [rcx+0Bh], 0Fh
0x1400308e8  jnz     short loc_140030947
0x1400308ea  cmp     al, 0E5h
0x1400308ec  jz      short loc_140030947
0x1400308ee  lea     rax, [rsp+98h+Bcb]
0x1400308f3  mov     [rsp+98h+var_78], rax; PVOID *
0x1400308f8  lea     r8d, [rdi-20h]; int
0x1400308fc  mov     rdx, rbx; int
0x1400308ff  mov     rcx, r14; int
0x140030902  call    FatPinMappedData
0x140030907  mov     rax, [rsp+98h+var_38]
0x14003090c  mov     byte ptr [rax], 0E5h
0x14003090f  mov     r9b, 1
0x140030912  mov     r8, [rbx+0B8h]
0x140030919  mov     rdx, [rsp+98h+Bcb]
0x14003091e  mov     rcx, r14
0x140030921  call    FatSetDirtyBcb
0x140030926  shr     r15, 5
0x14003092a  lea     rcx, [rbx+190h]; BitMapHeader
0x140030931  mov     r8d, 1; NumberToClear
0x140030937  mov     edx, r15d; StartingIndex
0x14003093a  call    cs:__imp_RtlClearBits
0x140030941  nop     dword ptr [rax+rax+00h]
0x140030946  nop
0x140030947  mov     rcx, [rsp+98h+Bcb]; Bcb
0x14003094c  test    rcx, rcx
0x14003094f  jz      short loc_140030966
0x140030951  call    cs:__imp_CcUnpinData
0x140030958  nop     dword ptr [rax+rax+00h]
0x14003095d  mov     [rsp+98h+Bcb], 0
0x140030966  mov     [rsp+98h+var_48], 0
0x14003096e  xor     ecx, ecx; Bcb
0x140030970  mov     [rsp+98h+Bcb], rcx
0x140030975  xor     r15d, r15d
0x140030978  mov     [rsp+98h+var_48], r15d
0x14003097d  cmp     r15d, r12d
0x140030980  jnb     loc_140030A80
0x140030986  mov     r13d, r15d
0x140030989  shl     r13, 5
0x14003098d  mov     eax, edi
0x14003098f  add     r13, rax
0x140030992  mov     eax, [rbx+18h]
0x140030995  cmp     r13, rax
0x140030998  jb      short loc_1400309C3
0x14003099a  mov     dword ptr [rsp+98h+arg_18], 0C0000011h
0x1400309a5  test    rcx, rcx
0x1400309a8  jz      loc_140030A3D
0x1400309ae  call    cs:__imp_CcUnpinData
0x1400309b5  nop     dword ptr [rax+rax+00h]
0x1400309ba  xor     ecx, ecx
0x1400309bc  mov     [rsp+98h+Bcb], rcx
0x1400309c1  jmp     short loc_140030A3D
0x1400309c3  and     r13d, 0FFFh
0x1400309ca  jz      short loc_1400309D1
0x1400309cc  test    rcx, rcx
0x1400309cf  jnz     short loc_140030A3D
0x1400309d1  test    rcx, rcx
0x1400309d4  jz      short loc_1400309EB
0x1400309d6  call    cs:__imp_CcUnpinData
0x1400309dd  nop     dword ptr [rax+rax+00h]
0x1400309e2  mov     [rsp+98h+Bcb], 0
0x1400309eb  mov     r8d, r15d
0x1400309ee  shl     r8d, 5
0x1400309f2  add     r8d, edi
0x1400309f5  and     r8d, 0FFFFF000h; int
0x1400309fc  lea     rax, [rsp+98h+arg_18]
0x140030a04  mov     [rsp+98h+var_60], rax; __int64
0x140030a09  lea     rax, [rsp+98h+var_38]
0x140030a0e  mov     [rsp+98h+var_68], rax; PVOID *
0x140030a13  lea     rax, [rsp+98h+Bcb]
0x140030a18  mov     [rsp+98h+var_70], rax; PVOID *
0x140030a1d  mov     byte ptr [rsp+98h+var_78], 0; char
0x140030a22  mov     r9d, 1000h; int
0x140030a28  mov     rdx, rbx; int
0x140030a2b  mov     rcx, r14; int
0x140030a2e  call    FatReadDirectoryFile
0x140030a33  add     [rsp+98h+var_38], r13
0x140030a38  mov     rcx, [rsp+98h+Bcb]
0x140030a3d  cmp     dword ptr [rsp+98h+arg_18], 0
0x140030a45  jnz     short loc_140030A5F
0x140030a47  mov     rax, [rsp+98h+var_38]
0x140030a4c  mov     dl, [rax]
0x140030a4e  test    dl, dl
0x140030a50  jz      short loc_140030A57
0x140030a52  cmp     dl, 0E5h
0x140030a55  jnz     short loc_140030A5F
0x140030a57  inc     r15d
0x140030a5a  jmp     loc_140030978
0x140030a5f  mov     rdx, rbx
0x140030a62  mov     rcx, r14
0x140030a65  call    FatPopUpFileCorrupt
0x140030a6a  mov     ecx, 0C0000102h; Status
0x140030a6f  mov     [r14+48h], ecx
0x140030a73  call    cs:__imp_ExRaiseStatus
0x140030a80  test    rcx, rcx
0x140030a83  jz      short loc_140030A9A
0x140030a85  call    cs:__imp_CcUnpinData
0x140030a8c  nop     dword ptr [rax+rax+00h]
0x140030a91  mov     [rsp+98h+Bcb], 0
0x140030a9a  mov     edx, edi
0x140030a9c  shr     edx, 5; StartingIndex
0x140030a9f  lea     rcx, [rbx+190h]; BitMapHeader
0x140030aa6  mov     r8d, r12d; NumberToSet
0x140030aa9  call    cs:__imp_RtlSetBits
0x140030ab0  nop     dword ptr [rax+rax+00h]
0x140030ab5  mov     [rbx+178h], esi
0x140030abb  mov     eax, [rsp+98h+arg_8]
0x140030ac2  mov     [rbx+17Ch], eax
0x140030ac8  mov     eax, edi
0x140030aca  lea     r11, [rsp+98h+var_28]
0x140030acf  mov     rbx, [r11+30h]
0x140030ad3  mov     rsi, [r11+40h]
0x140030ad7  mov     rsp, r11
0x140030ada  pop     r15
0x140030adc  pop     r14
0x140030ade  pop     r13
0x140030ae0  pop     r12
0x140030ae2  pop     rdi
0x140030ae3  retn
0x140030ae5  mov     ecx, 0C00002EAh; Status
0x140030aea  mov     [r14+48h], ecx
0x140030aee  call    cs:__imp_ExRaiseStatus
0x14005cf56  push    rbp
0x14005cf58  sub     rsp, 50h
0x14005cf5c  mov     rbp, rdx
0x14005cf5f  mov     rcx, [rbp+58h]; Bcb
0x14005cf63  test    rcx, rcx
0x14005cf66  jz      short loc_14005CF75
0x14005cf68  call    cs:__imp_CcUnpinData
0x14005cf6f  nop     dword ptr [rax+rax+00h]
0x14005cf74  nop
0x14005cf75  add     rsp, 50h
0x14005cf79  pop     rbp
  ... truncated ...
```
