# MdaAccessCheck

- ea: `0x1400095b0`
- end: `0x140009a3a`
- name: `MdaAccessCheck`
- size: `1162`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1400316d0`

## callees

- `0x1400095b0`
- `0x1400159cc`
- `0x1400159fc`
- `0x1400173f8`
- `0x140018310`

## pseudocode

```c
char __fastcall MdaAccessCheck(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v4; // r14d
  __int64 v7; // rsi
  BOOL v9; // ebp
  _DWORD *v10; // rdx
  int v11; // eax
  int v12; // ecx
  int v13; // r8d
  int v14; // eax
  unsigned int v15; // r9d
  __int64 i; // rcx
  int v17; // r10d
  unsigned int v18; // eax
  int v19; // r15d
  unsigned int v20; // r15d
  _DWORD *v21; // rcx
  int v22; // eax
  int v23; // edx
  int v24; // r8d
  int v25; // eax
  unsigned int v26; // r9d
  __int64 j; // rdx
  int v28; // r10d
  int v29; // edx
  int v30; // ebp
  int v31; // edx
  int v32; // r8d
  int v33; // edx
  int v34; // edx
  PDEVICE_OBJECT v35; // rcx
  __int64 v36; // rdx
  PDEVICE_OBJECT v37; // rcx
  __int64 v38; // rdx
  bool v39; // bl
  const char *v40; // r9

  v4 = a4;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 109, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids, a4);
  v7 = *(_QWORD *)(a1 + 40);
  if ( !*(_DWORD *)(v7 + 36) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
      WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 110, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids, "GRANTED");
    return 1;
  }
  v9 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_cca3db0522623f5e31396e1525c29988_Traceguids);
  v10 = *(_DWORD **)(a1 + 40);
  v11 = *(_DWORD *)(a2 + 12);
  v12 = v10[9];
  if ( v12 == v11 || (_WORD)v12 == (_WORD)v11 )
  {
    v9 = *(_BYTE *)(a2 + 4) >= 0;
  }
  else
  {
    v13 = *(_DWORD *)(a2 + 16);
    v14 = v10[10];
    if ( v14 == v13 || (_WORD)v14 == (_WORD)v13 )
    {
      v9 = (*(_DWORD *)(a2 + 4) & 0x10) == 0;
    }
    else
    {
      v15 = v10[11];
      for ( i = 0; (unsigned int)i < v15; i = (unsigned int)(i + 1) )
      {
        v17 = v10[i + 12];
        if ( v17 == v13 || (_WORD)v17 == (_WORD)v13 )
        {
          if ( (*(_DWORD *)(a2 + 4) & 0x10) == 0 )
            v9 = 1;
          goto LABEL_28;
        }
      }
      if ( (_DWORD)i == v15 && (*(_DWORD *)(a2 + 4) & 2) == 0 )
        v9 = 1;
    }
  }
LABEL_28:
  v18 = *(_DWORD *)a2;
  if ( *(_DWORD *)a2 == 2 )
  {
    v19 = 16;
  }
  else if ( v18 <= 2 || v18 >= 8 || v18 == 5 )
  {
    v19 = 32;
  }
  else
  {
    v19 = 4;
  }
  v20 = v9 | v19;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
      WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_cca3db0522623f5e31396e1525c29988_Traceguids, v20, v20);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_cca3db0522623f5e31396e1525c29988_Traceguids);
  }
  v21 = *(_DWORD **)(a1 + 40);
  v22 = *(_DWORD *)(a2 + 12);
  v23 = v21[9];
  if ( v23 == v22 || (_WORD)v23 == (_WORD)v22 )
  {
    v34 = *(_DWORD *)(a2 + 4);
    v30 = ((v34 & 0x100) << 16) | 0x2000000;
    if ( (v34 & 0x80u) == 0 )
      v30 = (*(_DWORD *)(a2 + 4) & 0x100) << 16;
    if ( (v34 & 0x40) != 0 )
LABEL_67:
      v30 |= 0x4000000u;
  }
  else
  {
    v24 = *(_DWORD *)(a2 + 16);
    v25 = v21[10];
    if ( v25 == v24 || (_WORD)v25 == (_WORD)v24 )
    {
      v32 = *(_DWORD *)(a2 + 4);
      v33 = ((v32 & 0x20) << 19) | 0x2000000;
      if ( (v32 & 0x10) == 0 )
        v33 = (*(_DWORD *)(a2 + 4) & 0x20) << 19;
      v30 = v33 | 0x4000000;
      if ( (v32 & 8) == 0 )
        v30 = v33;
    }
    else
    {
      v26 = v21[11];
      for ( j = 0; (unsigned int)j < v26; j = (unsigned int)(j + 1) )
      {
        v28 = v21[j + 12];
        if ( v28 == v24 || (_WORD)v28 == (_WORD)v24 )
        {
          v29 = *(_DWORD *)(a2 + 4);
          v30 = ((v29 & 0x20) << 19) | 0x2000000;
          if ( (v29 & 0x10) == 0 )
            v30 = (*(_DWORD *)(a2 + 4) & 0x20) << 19;
          if ( (v29 & 8) != 0 )
            goto LABEL_67;
          goto LABEL_68;
        }
      }
      v30 = 0;
      if ( (_DWORD)j == v26 )
      {
        v31 = *(_DWORD *)(a2 + 4);
        v30 = ((v31 & 4) << 22) | 0x2000000;
        if ( (v31 & 2) == 0 )
          v30 = (*(_DWORD *)(a2 + 4) & 4) << 22;
        if ( (v31 & 1) != 0 )
          goto LABEL_67;
      }
    }
  }
LABEL_68:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_cca3db0522623f5e31396e1525c29988_Traceguids);
  if ( (v20 & 0x10) != 0 )
  {
    if ( (v4 & 0xFEE0FE00) != 0 )
    {
      v35 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_92;
      v36 = 111;
      goto LABEL_91;
    }
LABEL_80:
    v39 = 1;
    if ( (v4 & 0xFEE0FE46) != 0 && (v20 & 1) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 113, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
      v39 = *(_DWORD *)(v7 + 36) == 0;
    }
    if ( (v20 & 0x10) == 0 )
    {
      if ( !v39 || (v30 & 0x5000000) != 0 || (v4 & 1) == 0 )
        goto LABEL_105;
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_104;
      v38 = 115;
      goto LABEL_103;
    }
    if ( !v39 )
      goto LABEL_105;
    if ( (v30 & 0x1000000) != 0 || (v4 & 1) == 0 )
      goto LABEL_93;
    v35 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
    {
LABEL_92:
      v39 = 0;
LABEL_93:
      if ( !v39 || (v30 & 0x4000000) != 0 || (v4 & 0x20) == 0 )
        goto LABEL_105;
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_104;
      v38 = 116;
      goto LABEL_103;
    }
    v36 = 114;
LABEL_91:
    WPP_SF_(v35->AttachedDevice, v36, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
    goto LABEL_92;
  }
  if ( (v4 & 0xFEE0FE40) == 0 )
    goto LABEL_80;
  v37 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
    goto LABEL_104;
  v38 = 112;
LABEL_103:
  WPP_SF_(v37->AttachedDevice, v38, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
LABEL_104:
  v39 = 0;
LABEL_105:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
  {
    v40 = "GRANTED";
    if ( !v39 )
      v40 = "NOTGRANTED";
    WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 117, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids, v40);
  }
  return v39;
}

```

## disassembly

```asm
0x1400095b0  mov     [rsp+arg_10], rbx
0x1400095b5  mov     [rsp+arg_18], rsi
0x1400095ba  push    rdi
0x1400095bb  push    r12
0x1400095bd  push    r14
0x1400095bf  sub     rsp, 30h
0x1400095c3  mov     r14d, r9d
0x1400095c6  mov     rdi, rdx
0x1400095c9  mov     rbx, rcx
0x1400095cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400095d3  lea     r12, WPP_GLOBAL_Control
0x1400095da  cmp     rcx, r12
0x1400095dd  jz      short loc_1400095FB
0x1400095df  mov     eax, [rcx+2Ch]
0x1400095e2  test    al, 8
0x1400095e4  jz      short loc_1400095FB
0x1400095e6  mov     rcx, [rcx+18h]
0x1400095ea  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x1400095f1  mov     edx, 6Dh ; 'm'
0x1400095f6  call    WPP_SF_d
0x1400095fb  mov     rsi, [rbx+28h]
0x1400095ff  cmp     dword ptr [rsi+24h], 0
0x140009603  jnz     short loc_14000963B
0x140009605  mov     rcx, cs:WPP_GLOBAL_Control
0x14000960c  cmp     rcx, r12
0x14000960f  jz      short loc_140009634
0x140009611  mov     eax, [rcx+2Ch]
0x140009614  test    al, 8
0x140009616  jz      short loc_140009634
0x140009618  mov     rcx, [rcx+18h]
0x14000961c  lea     r9, aGranted; "GRANTED"
0x140009623  mov     edx, 6Eh ; 'n'
0x140009628  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x14000962f  call    WPP_SF_s
0x140009634  mov     al, 1
0x140009636  jmp     loc_140009A25
0x14000963b  mov     [rsp+48h+arg_0], rbp
0x140009640  xor     ebp, ebp
0x140009642  mov     [rsp+48h+arg_8], r15
0x140009647  mov     rcx, cs:WPP_GLOBAL_Control
0x14000964e  cmp     rcx, r12
0x140009651  jz      short loc_14000966F
0x140009653  mov     eax, [rcx+2Ch]
0x140009656  test    al, 8
0x140009658  jz      short loc_14000966F
0x14000965a  mov     rcx, [rcx+18h]
0x14000965e  lea     r8, WPP_cca3db0522623f5e31396e1525c29988_Traceguids
0x140009665  mov     edx, 15h
0x14000966a  call    WPP_SF_
0x14000966f  mov     rdx, [rbx+28h]
0x140009673  mov     eax, [rdi+0Ch]
0x140009676  mov     ecx, [rdx+24h]
0x140009679  cmp     ecx, eax
0x14000967b  jz      short loc_1400096DE
0x14000967d  cmp     cx, ax
0x140009680  jz      short loc_1400096DE
0x140009682  mov     r8d, [rdi+10h]
0x140009686  mov     eax, [rdx+28h]
0x140009689  cmp     eax, r8d
0x14000968c  jz      short loc_1400096D1
0x14000968e  cmp     ax, r8w
0x140009692  jz      short loc_1400096D1
0x140009694  mov     r9d, [rdx+2Ch]
0x140009698  xor     ecx, ecx
0x14000969a  cmp     ecx, r9d
0x14000969d  jnb     short loc_1400096C1
0x14000969f  mov     r10d, [rdx+rcx*4+30h]
0x1400096a4  cmp     r10d, r8d
0x1400096a7  jz      short loc_1400096B3
0x1400096a9  cmp     r10w, r8w
0x1400096ad  jz      short loc_1400096B3
0x1400096af  inc     ecx
0x1400096b1  jmp     short loc_14000969A
0x1400096b3  mov     eax, [rdi+4]
0x1400096b6  test    al, 10h
0x1400096b8  jnz     short loc_1400096EE
0x1400096ba  mov     ebp, 1
0x1400096bf  jmp     short loc_1400096EE
0x1400096c1  jnz     short loc_1400096EE
0x1400096c3  mov     eax, [rdi+4]
0x1400096c6  test    al, 2
0x1400096c8  jnz     short loc_1400096EE
0x1400096ca  mov     ebp, 1
0x1400096cf  jmp     short loc_1400096EE
0x1400096d1  mov     ebp, [rdi+4]
0x1400096d4  shr     ebp, 4
0x1400096d7  not     ebp
0x1400096d9  and     ebp, 1
0x1400096dc  jmp     short loc_1400096EE
0x1400096de  test    byte ptr [rdi+4], 80h
0x1400096e2  mov     eax, ebp
0x1400096e4  mov     ebp, 1
0x1400096e9  cmovz   eax, ebp
0x1400096ec  mov     ebp, eax
0x1400096ee  mov     eax, [rdi]
0x1400096f0  cmp     eax, 2
0x1400096f3  jnz     short loc_1400096FD
0x1400096f5  mov     r15d, 10h
0x1400096fb  jmp     short loc_140009717
0x1400096fd  jbe     short loc_140009711
0x1400096ff  cmp     eax, 8
0x140009702  jnb     short loc_140009711
0x140009704  cmp     eax, 5
0x140009707  jz      short loc_140009711
0x140009709  mov     r15d, 4
0x14000970f  jmp     short loc_140009717
0x140009711  mov     r15d, 20h ; ' '
0x140009717  or      r15d, ebp
0x14000971a  mov     rcx, cs:WPP_GLOBAL_Control
0x140009721  cmp     rcx, r12
0x140009724  jz      short loc_140009772
0x140009726  mov     eax, [rcx+2Ch]
0x140009729  test    al, 8
0x14000972b  jz      short loc_14000974A
0x14000972d  mov     rcx, [rcx+18h]
0x140009731  lea     r8, WPP_cca3db0522623f5e31396e1525c29988_Traceguids
0x140009738  mov     edx, 16h
0x14000973d  mov     [rsp+48h+var_28], r15d
0x140009742  mov     r9d, r15d
0x140009745  call    WPP_SF_dd
0x14000974a  mov     rcx, cs:WPP_GLOBAL_Control
0x140009751  cmp     rcx, r12
0x140009754  jz      short loc_140009772
0x140009756  mov     eax, [rcx+2Ch]
0x140009759  test    al, 8
0x14000975b  jz      short loc_140009772
0x14000975d  mov     rcx, [rcx+18h]
0x140009761  lea     r8, WPP_cca3db0522623f5e31396e1525c29988_Traceguids
0x140009768  mov     edx, 17h
0x14000976d  call    WPP_SF_
0x140009772  mov     rcx, [rbx+28h]
0x140009776  mov     eax, [rdi+0Ch]
0x140009779  mov     edx, [rcx+24h]
0x14000977c  cmp     edx, eax
0x14000977e  jz      loc_14000982A
0x140009784  cmp     dx, ax
0x140009787  jz      loc_14000982A
0x14000978d  mov     r8d, [rdi+10h]
0x140009791  mov     eax, [rcx+28h]
0x140009794  cmp     eax, r8d
0x140009797  jz      short loc_140009801
0x140009799  cmp     ax, r8w
0x14000979d  jz      short loc_140009801
0x14000979f  mov     r9d, [rcx+2Ch]
0x1400097a3  xor     edx, edx
0x1400097a5  cmp     edx, r9d
0x1400097a8  jnb     short loc_1400097DC
0x1400097aa  mov     r10d, [rcx+rdx*4+30h]
0x1400097af  cmp     r10d, r8d
0x1400097b2  jz      short loc_1400097BE
0x1400097b4  cmp     r10w, r8w
0x1400097b8  jz      short loc_1400097BE
0x1400097ba  inc     edx
0x1400097bc  jmp     short loc_1400097A5
0x1400097be  mov     edx, [rdi+4]
0x1400097c1  mov     ecx, edx
0x1400097c3  and     ecx, 20h
0x1400097c6  shl     ecx, 13h
0x1400097c9  mov     ebp, ecx
0x1400097cb  bts     ebp, 19h
0x1400097cf  test    dl, 10h
0x1400097d2  cmovz   ebp, ecx
0x1400097d5  test    dl, 8
0x1400097d8  jnz     short loc_140009849
0x1400097da  jmp     short loc_14000984D
0x1400097dc  xor     ebp, ebp
0x1400097de  cmp     edx, r9d
0x1400097e1  jnz     short loc_14000984D
0x1400097e3  mov     edx, [rdi+4]
0x1400097e6  mov     ecx, edx
0x1400097e8  and     ecx, 4
0x1400097eb  shl     ecx, 16h
0x1400097ee  mov     ebp, ecx
0x1400097f0  bts     ebp, 19h
0x1400097f4  test    dl, 2
0x1400097f7  cmovz   ebp, ecx
0x1400097fa  test    dl, 1
0x1400097fd  jnz     short loc_140009849
0x1400097ff  jmp     short loc_14000984D
0x140009801  mov     r8d, [rdi+4]
0x140009805  mov     ecx, r8d
0x140009808  and     ecx, 20h
0x14000980b  shl     ecx, 13h
0x14000980e  mov     edx, ecx
0x140009810  bts     edx, 19h
0x140009814  test    r8b, 10h
0x140009818  cmovz   edx, ecx
0x14000981b  mov     ebp, edx
0x14000981d  bts     ebp, 1Ah
0x140009821  test    r8b, 8
0x140009825  cmovz   ebp, edx
0x140009828  jmp     short loc_14000984D
0x14000982a  mov     edx, [rdi+4]
0x14000982d  mov     ecx, edx
0x14000982f  and     ecx, 100h
0x140009835  shl     ecx, 10h
0x140009838  mov     ebp, ecx
0x14000983a  bts     ebp, 19h
0x14000983e  test    dl, 80h
0x140009841  cmovz   ebp, ecx
0x140009844  test    dl, 40h
0x140009847  jz      short loc_14000984D
0x140009849  bts     ebp, 1Ah
0x14000984d  mov     rcx, cs:WPP_GLOBAL_Control
0x140009854  cmp     rcx, r12
0x140009857  jz      short loc_140009875
0x140009859  mov     eax, [rcx+2Ch]
0x14000985c  test    al, 8
0x14000985e  jz      short loc_140009875
0x140009860  mov     rcx, [rcx+18h]
0x140009864  lea     r8, WPP_cca3db0522623f5e31396e1525c29988_Traceguids
0x14000986b  mov     edx, 18h
0x140009870  call    WPP_SF_
0x140009875  mov     edi, r15d
0x140009878  and     edi, 10h
0x14000987b  jz      short loc_1400098AB
0x14000987d  test    r14d, 0FEE0FE00h
0x140009884  jz      short loc_1400098D9
0x140009886  mov     rcx, cs:WPP_GLOBAL_Control
0x14000988d  cmp     rcx, r12
0x140009890  jz      loc_140009968
0x140009896  mov     eax, [rcx+2Ch]
0x140009899  test    al, 1
0x14000989b  jz      loc_140009968
0x1400098a1  mov     edx, 6Fh ; 'o'
0x1400098a6  jmp     loc_140009958
0x1400098ab  test    r14d, 0FEE0FE40h
0x1400098b2  jz      short loc_1400098D9
0x1400098b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400098bb  cmp     rcx, r12
0x1400098be  jz      loc_1400099DA
0x1400098c4  mov     eax, [rcx+2Ch]
0x1400098c7  test    al, 1
0x1400098c9  jz      loc_1400099DA
0x1400098cf  mov     edx, 70h ; 'p'
0x1400098d4  jmp     loc_1400099CA
0x1400098d9  test    r14d, 0FEE0FE46h
0x1400098e0  mov     bl, 1
0x1400098e2  setnz   cl
0x1400098e5  test    bl, r15b
0x1400098e8  setnz   al
0x1400098eb  test    al, cl
0x1400098ed  jz      short loc_140009922
0x1400098ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400098f6  cmp     rcx, r12
0x1400098f9  jz      short loc_140009917
0x1400098fb  mov     eax, [rcx+2Ch]
0x1400098fe  test    bl, al
0x140009900  jz      short loc_140009917
0x140009902  mov     rcx, [rcx+18h]
0x140009906  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x14000990d  mov     edx, 71h ; 'q'
0x140009912  call    WPP_SF_
0x140009917  xor     eax, eax
0x140009919  movzx   ebx, bl
0x14000991c  cmp     [rsi+24h], eax
0x14000991f  cmovnz  ebx, eax
0x140009922  test    edi, edi
0x140009924  jz      short loc_14000999A
0x140009926  test    bl, bl
0x140009928  jz      loc_1400099DC
0x14000992e  bt      ebp, 18h
0x140009932  setnb   cl
0x140009935  test    r14b, 1
0x140009939  setnz   al
0x14000993c  test    al, cl
0x14000993e  jz      short loc_14000996A
0x140009940  mov     rcx, cs:WPP_GLOBAL_Control
0x140009947  cmp     rcx, r12
0x14000994a  jz      short loc_140009968
0x14000994c  mov     eax, [rcx+2Ch]
0x14000994f  test    al, 1
0x140009951  jz      short loc_140009968
0x140009953  mov     edx, 72h ; 'r'
0x140009958  mov     rcx, [rcx+18h]
0x14000995c  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x140009963  call    WPP_SF_
0x140009968  xor     bl, bl
0x14000996a  test    bl, bl
0x14000996c  jz      short loc_1400099DC
0x14000996e  bt      ebp, 1Ah
0x140009972  setnb   cl
0x140009975  test    r14b, 20h
0x140009979  setnz   al
0x14000997c  test    al, cl
0x14000997e  jz      short loc_1400099DC
0x140009980  mov     rcx, cs:WPP_GLOBAL_Control
0x140009987  cmp     rcx, r12
0x14000998a  jz      short loc_1400099DA
0x14000998c  mov     eax, [rcx+2Ch]
0x14000998f  test    al, 1
0x140009991  jz      short loc_1400099DA
0x140009993  mov     edx, 74h ; 't'
0x140009998  jmp     short loc_1400099CA
0x14000999a  test    bl, bl
0x14000999c  jz      short loc_1400099DC
0x14000999e  test    ebp, 5000000h
0x1400099a4  setz    cl
0x1400099a7  test    r14b, 1
0x1400099ab  setnz   al
  ... truncated ...
```
