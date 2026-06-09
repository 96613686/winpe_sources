# NatCreateAddressPoolEntry

- ea: `0x14001308c`
- end: `0x140013548`
- name: `NatCreateAddressPoolEntry`
- size: `1212`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x140011e00`
- `0x1400128ec`
- `0x140013550`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x1400052a0`
- `0x14001308c`
- `0x140013b70`
- `0x140013ccc`

## import_xrefs

- `ntoskrnl!RtlFindClearBits` at `0x14001318a`
- `ntoskrnl!RtlFindClearBits` at `0x14001318a`
- `ntoskrnl!RtlSetBits` at `0x140013169`
- `ntoskrnl!RtlSetBits` at `0x140013268`
- `ntoskrnl!RtlSetBits` at `0x1400134e1`
- `ntoskrnl!RtlSetBits` at `0x140013169`
- `ntoskrnl!RtlSetBits` at `0x140013268`
- `ntoskrnl!RtlSetBits` at `0x1400134e1`
- `ntoskrnl!ExAllocatePool2` at `0x140013387`
- `ntoskrnl!ExAllocatePool2` at `0x140013387`

## pseudocode

```c
__int64 __fastcall NatCreateAddressPoolEntry(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        int a4,
        __int64 *a5,
        __int64 *a6)
{
  unsigned int v6; // edi
  __int64 v7; // r13
  unsigned __int32 v9; // ebp
  __int64 v10; // r12
  ULONG ClearBits; // esi
  __int64 v12; // rcx
  ULONG v13; // r8d
  __int64 v14; // r9
  PDEVICE_OBJECT v15; // rcx
  __int64 v16; // rdx
  unsigned __int32 v17; // eax
  __int64 *v18; // r15
  __int64 Pool2; // rax
  __int64 v21; // rbx
  int v22; // eax
  _QWORD *v23; // rcx
  __int16 v24; // dx
  __int16 v25; // ax
  _QWORD *v26; // rdx
  __int64 v27; // [rsp+70h] [rbp+8h] BYREF
  int v28; // [rsp+88h] [rbp+20h]

  v28 = a4;
  v6 = a3;
  v7 = a2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_DDD(WPP_GLOBAL_Control->AttachedDevice, 64, WPP_96cec5cc952234920ba0014d840adb44_Traceguids, a2, a3, a4);
  }
  v9 = 0;
  v27 = 0;
  *a6 = 0;
  if ( v6 )
    v9 = _byteswap_ulong(v6);
  v10 = 0;
  ClearBits = -1;
  if ( !*(_DWORD *)(a1 + 132) )
    goto LABEL_15;
  while ( 1 )
  {
    v12 = *(_QWORD *)(a1 + 136);
    if ( !v6 )
    {
      v13 = 0;
      while ( 1 )
      {
        ClearBits = RtlFindClearBits(*(PRTL_BITMAP *)(v12 + 24 * v10 + 16), 1u, v13);
        if ( ClearBits == -1 )
          goto LABEL_27;
        v14 = *(_QWORD *)(a1 + 136);
        v6 = _byteswap_ulong(ClearBits + _byteswap_ulong(*(_DWORD *)(v14 + 24 * v10)));
        if ( (v6 & ~*(_DWORD *)(v14 + 24 * v10 + 8)) != 0
          && (v6 & ~*(_DWORD *)(v14 + 24 * v10 + 8)) != ~*(_DWORD *)(v14 + 24 * v10 + 8) )
        {
          goto LABEL_15;
        }
        RtlSetBits(*(PRTL_BITMAP *)(v14 + 24 * v10 + 16), ClearBits, 1u);
        v12 = *(_QWORD *)(a1 + 136);
        v13 = ClearBits + 1;
        v6 = 0;
      }
    }
    if ( v9 <= _byteswap_ulong(*(_DWORD *)(v12 + 24 * v10 + 4)) )
      break;
LABEL_27:
    v10 = (unsigned int)(v10 + 1);
    if ( (unsigned int)v10 >= *(_DWORD *)(a1 + 132) )
      goto LABEL_15;
  }
  v17 = _byteswap_ulong(*(_DWORD *)(v12 + 24 * v10));
  if ( v9 < v17 )
  {
    ClearBits = -1;
    goto LABEL_27;
  }
  ClearBits = v9 - v17;
  if ( (v6 & ~*(_DWORD *)(v12 + 24 * v10 + 8)) == 0
    || (v6 & ~*(_DWORD *)(v12 + 24 * v10 + 8)) == ~*(_DWORD *)(v12 + 24 * v10 + 8) )
  {
    RtlSetBits(*(PRTL_BITMAP *)(v12 + 24 * v10 + 16), ClearBits, 1u);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 65, WPP_96cec5cc952234920ba0014d840adb44_Traceguids);
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      {
        v16 = 66;
        goto LABEL_49;
      }
    }
    return 3221225473LL;
  }
LABEL_15:
  if ( !v6 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 67, WPP_96cec5cc952234920ba0014d840adb44_Traceguids);
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      {
        v16 = 68;
        goto LABEL_49;
      }
    }
    return 3221225473LL;
  }
  v18 = a5;
  if ( a5 )
  {
LABEL_52:
    Pool2 = ExAllocatePool2(64, 88, 1096114510);
    v21 = Pool2;
    if ( Pool2 )
    {
      *(_OWORD *)(Pool2 + 56) = 0;
      *(_WORD *)(Pool2 + 86) = 0;
      *(_DWORD *)(Pool2 + 48) = v7;
      v22 = v28;
      *(_QWORD *)(v21 + 40) = v6 | (unsigned __int64)(v7 << 32);
      v23 = (_QWORD *)(v21 + 24);
      *(_QWORD *)(v21 + 32) = v21 + 24;
      *(_QWORD *)(v21 + 24) = v21 + 24;
      *(_DWORD *)(v21 + 52) = v6;
      *(_DWORD *)(v21 + 72) = v22;
      *(_DWORD *)(v21 + 76) = 1;
      *(_QWORD *)v21 = v21;
      *(_QWORD *)(v21 + 8) = 0;
      *(_QWORD *)(v21 + 16) = 0;
      if ( (v22 & 8) != 0 )
      {
        v24 = ReservedPortsLowerRange;
        v25 = ReservedPortsUpperRange;
        *(_WORD *)(v21 + 80) = ReservedPortsLowerRange;
        *(_WORD *)(v21 + 82) = v25;
      }
      else
      {
        v24 = 256;
        *(_DWORD *)(v21 + 80) = -16842496;
      }
      *(_WORD *)(v21 + 84) = v24;
      v26 = *(_QWORD **)(a1 + 160);
      if ( *v26 != a1 + 152 )
        __fastfail(3u);
      *(_QWORD *)(v21 + 32) = v26;
      *v23 = a1 + 152;
      *v26 = v23;
      *(_QWORD *)(a1 + 160) = v23;
      *(_QWORD *)(a1 + 144) = NatInsertAddressPoolEntry(*v18, v21);
      if ( ClearBits != -1 )
        RtlSetBits(*(PRTL_BITMAP *)(*(_QWORD *)(a1 + 136) + 24 * v10 + 16), ClearBits, 1u);
      *a6 = v21;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 73, WPP_96cec5cc952234920ba0014d840adb44_Traceguids, 0);
      }
      return 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 71, WPP_96cec5cc952234920ba0014d840adb44_Traceguids);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            72,
            WPP_96cec5cc952234920ba0014d840adb44_Traceguids,
            3221225495LL);
        }
      }
      return 3221225495LL;
    }
  }
  if ( !NatLookupAddressPoolEntry(*(_QWORD *)(a1 + 144), (unsigned int)v7, v6, &v27) )
  {
    v18 = &v27;
    goto LABEL_52;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 69, WPP_96cec5cc952234920ba0014d840adb44_Traceguids);
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      v16 = 70;
LABEL_49:
      WPP_SF_d(v15->AttachedDevice, v16, WPP_96cec5cc952234920ba0014d840adb44_Traceguids, 3221225473LL);
    }
  }
  return 3221225473LL;
}

```

## disassembly

```asm
0x14001308c  mov     [rsp+arg_8], rbx
0x140013091  mov     [rsp+arg_18], r9d
0x140013096  push    rbp
0x140013097  push    rsi
0x140013098  push    rdi
0x140013099  push    r12
0x14001309b  push    r13
0x14001309d  push    r14
0x14001309f  push    r15
0x1400130a1  sub     rsp, 30h
0x1400130a5  mov     edi, r8d
0x1400130a8  mov     r13d, edx
0x1400130ab  mov     r14, rcx
0x1400130ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400130b5  lea     rbx, WPP_GLOBAL_Control
0x1400130bc  mov     r15d, 1
0x1400130c2  cmp     rcx, rbx
0x1400130c5  jz      short loc_1400130F6
0x1400130c7  mov     eax, [rcx+2Ch]
0x1400130ca  test    r15b, al
0x1400130cd  jz      short loc_1400130F6
0x1400130cf  cmp     byte ptr [rcx+29h], 6
0x1400130d3  jb      short loc_1400130F6
0x1400130d5  mov     rcx, [rcx+18h]
0x1400130d9  lea     edx, [r15+3Fh]
0x1400130dd  mov     [rsp+68h+var_40], r9d
0x1400130e2  mov     r9d, r13d
0x1400130e5  mov     [rsp+68h+var_48], r8d
0x1400130ea  lea     r8, WPP_96cec5cc952234920ba0014d840adb44_Traceguids
0x1400130f1  call    WPP_SF_DDD
0x1400130f6  mov     rax, [rsp+68h+arg_28]
0x1400130fe  xor     ebp, ebp
0x140013100  mov     [rsp+68h+arg_0], rbp
0x140013105  mov     [rax], rbp
0x140013108  test    edi, edi
0x14001310a  jz      short loc_140013110
0x14001310c  mov     ebp, edi
0x14001310e  bswap   ebp
0x140013110  or      edx, 0FFFFFFFFh
0x140013113  xor     r12d, r12d
0x140013116  mov     esi, edx
0x140013118  cmp     [r14+84h], r12d
0x14001311f  jbe     loc_1400131B3
0x140013125  mov     rcx, [r14+88h]
0x14001312c  lea     rbx, [r12+r12*2]
0x140013130  test    edi, edi
0x140013132  jnz     loc_14001321C
0x140013138  xor     r8d, r8d
0x14001313b  jmp     short loc_140013182
0x14001313d  mov     r9, [r14+88h]
0x140013144  mov     edi, [r9+rbx*8]
0x140013148  mov     eax, [r9+rbx*8+8]
0x14001314d  bswap   edi
0x14001314f  add     edi, esi
0x140013151  not     eax
0x140013153  bswap   edi
0x140013155  mov     ecx, eax
0x140013157  and     ecx, edi
0x140013159  jz      short loc_14001315F
0x14001315b  cmp     ecx, eax
0x14001315d  jnz     short loc_1400131A4
0x14001315f  mov     rcx, [r9+rbx*8+10h]; BitMapHeader
0x140013164  mov     r8d, r15d; NumberToSet
0x140013167  mov     edx, esi; StartingIndex
0x140013169  call    cs:__imp_RtlSetBits
0x140013170  nop     dword ptr [rax+rax+00h]
0x140013175  mov     rcx, [r14+88h]
0x14001317c  lea     r8d, [rsi+1]; HintIndex
0x140013180  xor     edi, edi
0x140013182  mov     rcx, [rcx+rbx*8+10h]; BitMapHeader
0x140013187  mov     edx, r15d; NumberToFind
0x14001318a  call    cs:__imp_RtlFindClearBits
0x140013191  nop     dword ptr [rax+rax+00h]
0x140013196  or      edx, 0FFFFFFFFh
0x140013199  mov     esi, eax
0x14001319b  cmp     eax, edx
0x14001319d  jnz     short loc_14001313D
0x14001319f  jmp     loc_140013231
0x1400131a4  cmp     esi, edx
0x1400131a6  jz      loc_140013231
0x1400131ac  lea     rbx, WPP_GLOBAL_Control
0x1400131b3  test    edi, edi
0x1400131b5  jnz     loc_1400132DB
0x1400131bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400131c2  cmp     rcx, rbx
0x1400131c5  jz      loc_14001336A
0x1400131cb  mov     eax, [rcx+2Ch]
0x1400131ce  test    r15b, al
0x1400131d1  jz      short loc_1400131EC
0x1400131d3  cmp     byte ptr [rcx+29h], 2
0x1400131d7  jb      short loc_1400131EC
0x1400131d9  mov     rcx, [rcx+18h]
0x1400131dd  lea     edx, [rdi+43h]
0x1400131e0  lea     r8, WPP_96cec5cc952234920ba0014d840adb44_Traceguids
0x1400131e7  call    WPP_SF_
0x1400131ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400131f3  cmp     rcx, rbx
0x1400131f6  jz      loc_14001336A
0x1400131fc  mov     eax, [rcx+2Ch]
0x1400131ff  test    r15b, al
0x140013202  jz      loc_14001336A
0x140013208  cmp     byte ptr [rcx+29h], 6
0x14001320c  jb      loc_14001336A
0x140013212  mov     edx, 44h ; 'D'
0x140013217  jmp     loc_140013354
0x14001321c  mov     eax, [rcx+rbx*8+4]
0x140013220  bswap   eax
0x140013222  cmp     ebp, eax
0x140013224  ja      short loc_140013231
0x140013226  mov     eax, [rcx+rbx*8]
0x140013229  bswap   eax
0x14001322b  cmp     ebp, eax
0x14001322d  jnb     short loc_140013246
0x14001322f  mov     esi, edx
0x140013231  add     r12d, r15d
0x140013234  cmp     r12d, [r14+84h]
0x14001323b  jb      loc_140013125
0x140013241  jmp     loc_1400131AC
0x140013246  mov     esi, ebp
0x140013248  sub     esi, eax
0x14001324a  mov     eax, [rcx+rbx*8+8]
0x14001324e  not     eax
0x140013250  mov     edx, eax
0x140013252  and     edx, edi
0x140013254  jz      short loc_14001325E
0x140013256  cmp     edx, eax
0x140013258  jnz     loc_1400131AC
0x14001325e  mov     rcx, [rcx+rbx*8+10h]; BitMapHeader
0x140013263  mov     r8d, r15d; NumberToSet
0x140013266  mov     edx, esi; StartingIndex
0x140013268  call    cs:__imp_RtlSetBits
0x14001326f  nop     dword ptr [rax+rax+00h]
0x140013274  mov     rcx, cs:WPP_GLOBAL_Control
0x14001327b  lea     rbx, WPP_GLOBAL_Control
0x140013282  cmp     rcx, rbx
0x140013285  jz      loc_14001336A
0x14001328b  mov     eax, [rcx+2Ch]
0x14001328e  test    r15b, al
0x140013291  jz      short loc_1400132AE
0x140013293  cmp     byte ptr [rcx+29h], 2
0x140013297  jb      short loc_1400132AE
0x140013299  mov     rcx, [rcx+18h]
0x14001329d  lea     r8, WPP_96cec5cc952234920ba0014d840adb44_Traceguids
0x1400132a4  mov     edx, 41h ; 'A'
0x1400132a9  call    WPP_SF_
0x1400132ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400132b5  cmp     rcx, rbx
0x1400132b8  jz      loc_14001336A
0x1400132be  mov     eax, [rcx+2Ch]
0x1400132c1  test    r15b, al
0x1400132c4  jz      loc_14001336A
0x1400132ca  cmp     byte ptr [rcx+29h], 6
0x1400132ce  jb      loc_14001336A
0x1400132d4  mov     edx, 42h ; 'B'
0x1400132d9  jmp     short loc_140013354
0x1400132db  mov     r15, [rsp+68h+arg_20]
0x1400132e3  test    r15, r15
0x1400132e6  jnz     loc_140013379
0x1400132ec  mov     rcx, [r14+90h]
0x1400132f3  lea     r9, [rsp+68h+arg_0]
0x1400132f8  mov     r8d, edi
0x1400132fb  mov     edx, r13d
0x1400132fe  call    NatLookupAddressPoolEntry
0x140013303  test    rax, rax
0x140013306  jz      short loc_140013374
0x140013308  mov     rcx, cs:WPP_GLOBAL_Control
0x14001330f  cmp     rcx, rbx
0x140013312  jz      short loc_14001336A
0x140013314  mov     eax, [rcx+2Ch]
0x140013317  test    al, 1
0x140013319  jz      short loc_140013335
0x14001331b  cmp     byte ptr [rcx+29h], 5
0x14001331f  jb      short loc_140013335
0x140013321  mov     rcx, [rcx+18h]
0x140013325  lea     edx, [r15+45h]
0x140013329  lea     r8, WPP_96cec5cc952234920ba0014d840adb44_Traceguids
0x140013330  call    WPP_SF_
0x140013335  mov     rcx, cs:WPP_GLOBAL_Control
0x14001333c  cmp     rcx, rbx
0x14001333f  jz      short loc_14001336A
0x140013341  mov     edx, [rcx+2Ch]
0x140013344  test    dl, 1
0x140013347  jz      short loc_14001336A
0x140013349  cmp     byte ptr [rcx+29h], 6
0x14001334d  jb      short loc_14001336A
0x14001334f  mov     edx, 46h ; 'F'
0x140013354  mov     rcx, [rcx+18h]
0x140013358  lea     r8, WPP_96cec5cc952234920ba0014d840adb44_Traceguids
0x14001335f  mov     r9d, 0C0000001h
0x140013365  call    WPP_SF_d
0x14001336a  mov     eax, 0C0000001h
0x14001336f  jmp     loc_140013532
0x140013374  lea     r15, [rsp+68h+arg_0]
0x140013379  mov     edx, 58h ; 'X'
0x14001337e  mov     r8d, 4155614Eh
0x140013384  lea     ecx, [rdx-18h]
0x140013387  call    cs:__imp_ExAllocatePool2
0x14001338e  nop     dword ptr [rax+rax+00h]
0x140013393  mov     rbx, rax
0x140013396  test    rax, rax
0x140013399  jnz     short loc_14001340E
0x14001339b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400133a2  lea     rbx, WPP_GLOBAL_Control
0x1400133a9  mov     edi, 0C0000017h
0x1400133ae  cmp     rcx, rbx
0x1400133b1  jz      short loc_140013407
0x1400133b3  mov     eax, [rcx+2Ch]
0x1400133b6  test    al, 1
0x1400133b8  jz      short loc_1400133D5
0x1400133ba  cmp     byte ptr [rcx+29h], 2
0x1400133be  jb      short loc_1400133D5
0x1400133c0  mov     rcx, [rcx+18h]
0x1400133c4  lea     r8, WPP_96cec5cc952234920ba0014d840adb44_Traceguids
0x1400133cb  mov     edx, 47h ; 'G'
0x1400133d0  call    WPP_SF_
0x1400133d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400133dc  cmp     rcx, rbx
0x1400133df  jz      short loc_140013407
0x1400133e1  mov     edx, [rcx+2Ch]
0x1400133e4  test    dl, 1
0x1400133e7  jz      short loc_140013407
0x1400133e9  cmp     byte ptr [rcx+29h], 6
0x1400133ed  jb      short loc_140013407
0x1400133ef  mov     rcx, [rcx+18h]
0x1400133f3  lea     r8, WPP_96cec5cc952234920ba0014d840adb44_Traceguids
0x1400133fa  mov     edx, 48h ; 'H'
0x1400133ff  mov     r9d, edi
0x140013402  call    WPP_SF_d
0x140013407  mov     eax, edi
0x140013409  jmp     loc_140013532
0x14001340e  xorps   xmm0, xmm0
0x140013411  mov     rcx, r13
0x140013414  movups  xmmword ptr [rax+38h], xmm0
0x140013418  xor     eax, eax
0x14001341a  shl     rcx, 20h
0x14001341e  mov     [rbx+56h], ax
0x140013422  mov     eax, edi
0x140013424  or      rcx, rax
0x140013427  mov     [rbx+30h], r13d
0x14001342b  mov     eax, [rsp+68h+arg_18]
0x140013432  mov     [rbx+28h], rcx
0x140013436  lea     rcx, [rbx+18h]
0x14001343a  mov     [rcx+8], rcx
0x14001343e  mov     [rcx], rcx
0x140013441  mov     [rbx+34h], edi
0x140013444  mov     [rbx+48h], eax
0x140013447  mov     dword ptr [rbx+4Ch], 1
0x14001344e  mov     [rbx], rbx
0x140013451  mov     qword ptr [rbx+8], 0
0x140013459  mov     qword ptr [rbx+10h], 0
0x140013461  test    al, 8
0x140013463  jz      short loc_14001347D
0x140013465  movzx   edx, cs:ReservedPortsLowerRange
0x14001346c  movzx   eax, cs:ReservedPortsUpperRange
0x140013473  mov     [rbx+50h], dx
0x140013477  mov     [rbx+52h], ax
0x14001347b  jmp     short loc_140013489
0x14001347d  mov     edx, 100h
0x140013482  mov     dword ptr [rbx+50h], 0FEFF0100h
0x140013489  lea     rax, [r14+98h]
0x140013490  mov     [rbx+54h], dx
0x140013494  mov     rdx, [rax+8]
0x140013498  cmp     [rdx], rax
0x14001349b  jz      short loc_1400134A4
0x14001349d  mov     ecx, 3
0x1400134a2  int     29h; Win8: RtlFailFast(ecx)
0x1400134a4  mov     [rcx+8], rdx
0x1400134a8  mov     [rcx], rax
0x1400134ab  mov     [rdx], rcx
0x1400134ae  mov     rdx, rbx
0x1400134b1  mov     [rax+8], rcx
0x1400134b5  mov     rcx, [r15]
0x1400134b8  call    NatInsertAddressPoolEntry
0x1400134bd  mov     [r14+90h], rax
0x1400134c4  cmp     esi, 0FFFFFFFFh
0x1400134c7  jz      short loc_1400134ED
0x1400134c9  mov     rcx, [r14+88h]
0x1400134d0  lea     r9, [r12+r12*2]
0x1400134d4  mov     r8d, 1; NumberToSet
0x1400134da  mov     edx, esi; StartingIndex
0x1400134dc  mov     rcx, [rcx+r9*8+10h]; BitMapHeader
0x1400134e1  call    cs:__imp_RtlSetBits
0x1400134e8  nop     dword ptr [rax+rax+00h]
0x1400134ed  mov     rax, [rsp+68h+arg_28]
0x1400134f5  mov     [rax], rbx
0x1400134f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400134ff  lea     rbx, WPP_GLOBAL_Control
0x140013506  cmp     rcx, rbx
0x140013509  jz      short loc_140013530
0x14001350b  mov     eax, [rcx+2Ch]
0x14001350e  test    al, 1
0x140013510  jz      short loc_140013530
0x140013512  cmp     byte ptr [rcx+29h], 6
0x140013516  jb      short loc_140013530
0x140013518  mov     rcx, [rcx+18h]
0x14001351c  lea     r8, WPP_96cec5cc952234920ba0014d840adb44_Traceguids
0x140013523  mov     edx, 49h ; 'I'
0x140013528  xor     r9d, r9d
0x14001352b  call    WPP_SF_d
0x140013530  xor     eax, eax
  ... truncated ...
```
