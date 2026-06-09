# HidServReportDispatch

- ea: `0x1800030d4`
- end: `0x180003513`
- name: `HidServReportDispatch`
- size: `1087`
- prototype: `void __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180004310`

## callees

- `0x1800030d4`
- `0x180005038`
- `0x180005084`

## import_xrefs

- `USER32!PostMessageW` at `0x180003247`
- `USER32!PostMessageW` at `0x1800032a5`
- `USER32!PostMessageW` at `0x180003409`
- `USER32!PostMessageW` at `0x1800034dc`
- `USER32!PostMessageW` at `0x180003247`
- `USER32!PostMessageW` at `0x1800032a5`
- `USER32!PostMessageW` at `0x180003409`
- `USER32!PostMessageW` at `0x1800034dc`

## pseudocode

```c
void __fastcall HidServReportDispatch(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  unsigned int v5; // r15d
  _QWORD *v6; // r10
  unsigned __int16 v7; // ax
  unsigned __int16 *v8; // rdi
  _WORD *v9; // r14
  int i; // ecx
  unsigned int j; // edx
  __int16 v12; // ax
  unsigned __int16 *v13; // rsi
  __int16 *v14; // rcx
  unsigned int v15; // ecx
  __int64 v16; // rdx
  HWND v17; // rcx
  __int64 v18; // rcx

  v3 = *(_QWORD *)(a1 + 192);
  v5 = 0;
  if ( *(_DWORD *)(a1 + 200) )
  {
    v6 = WPP_GLOBAL_Control;
    do
    {
      v7 = *(_WORD *)(v3 + 6);
      if ( !v7 )
      {
        *(_WORD *)(v3 + 6) = 1;
        v7 = 1;
        v6 = WPP_GLOBAL_Control;
      }
      if ( *(_DWORD *)(v3 + 8) != 1114112 )
        goto LABEL_62;
      if ( *(_BYTE *)v3 )
      {
        if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 && *((_BYTE *)v6 + 25) >= 4u )
        {
          WPP_SF_DD(v6[2], 26, WPP_a78e9b98c57431a096020c8f92b2d1b7_Traceguids, *(unsigned __int16 *)(v3 + 2), v7);
          v6 = WPP_GLOBAL_Control;
        }
        v8 = *(unsigned __int16 **)(v3 + 24);
        v9 = *(_WORD **)(v3 + 32);
        while ( *v8 )
        {
          if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x10) != 0 && *((_BYTE *)v6 + 25) >= 4u )
          {
            WPP_SF_DD(v6[2], 27, WPP_a78e9b98c57431a096020c8f92b2d1b7_Traceguids, v8[1], *v8);
            v6 = WPP_GLOBAL_Control;
          }
          if ( *(_BYTE *)(a1 + 204) )
          {
            *v8 |= 0x8000u;
            v6 = WPP_GLOBAL_Control;
          }
          a3 = *(unsigned __int16 *)(v3 + 6);
          for ( i = 0; i < 16; ++i )
          {
            if ( *(_DWORD *)((char *)PendingButtonList + 6 * (unsigned int)i) == __PAIR32__(v8[1], a3)
              && *((_WORD *)PendingButtonList + 3 * (unsigned int)i + 2) == *v8 )
            {
              goto LABEL_33;
            }
          }
          PostMessageW(
            hWndHidServ,
            0x813Au,
            *v8 | ((unsigned __int64)*(unsigned __int16 *)(v3 + 6) << 16),
            ((unsigned __int64)v8[1] << 16) | 1);
          for ( j = 0; (int)j < 16; ++j )
          {
            if ( !*((_WORD *)PendingButtonList + 3 * j)
              && !*((_WORD *)PendingButtonList + 3 * j + 1)
              && !*((_WORD *)PendingButtonList + 3 * j + 2) )
            {
              *((_WORD *)PendingButtonList + 3 * j) = *(_WORD *)(v3 + 6);
              *((_WORD *)PendingButtonList + 3 * j + 1) = v8[1];
              *((_WORD *)PendingButtonList + 3 * j + 2) = *v8;
              goto LABEL_32;
            }
          }
          if ( j != 16 )
            goto LABEL_32;
          PostMessageW(
            hWndHidServ,
            0x813Au,
            *v8 | ((unsigned __int64)*(unsigned __int16 *)(v3 + 6) << 16),
            (unsigned __int64)v8[1] << 16);
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_DDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, a3, *(unsigned __int16 *)(v3 + 6), *v8, v8[1]);
LABEL_32:
            v6 = WPP_GLOBAL_Control;
          }
LABEL_33:
          v8 += 2;
        }
        for ( ; *v9; v9 += 2 )
        {
          v12 = *v8;
          v13 = v9 + 1;
          if ( *v8 )
          {
            v14 = (__int16 *)v8;
            while ( *v9 != v12 || *v13 != v14[1] )
            {
              v14 += 2;
              v12 = *v14;
              if ( !*v14 )
                goto LABEL_41;
            }
          }
          else
          {
LABEL_41:
            if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 && *((_BYTE *)v6 + 25) >= 4u )
            {
              WPP_SF_DDD(v6[2], 29, a3, *(unsigned __int16 *)(v3 + 6), (unsigned __int16)*v9, *v13);
              v6 = WPP_GLOBAL_Control;
            }
            a3 = *(unsigned __int16 *)(v3 + 6);
            v15 = 0;
            while ( 1 )
            {
              v16 = 3LL * v15;
              if ( *(_DWORD *)((char *)PendingButtonList + 6 * v15) == __PAIR32__(*v13, a3)
                && *((_WORD *)PendingButtonList + 3 * v15 + 2) == *v9 )
              {
                break;
              }
              if ( (int)++v15 >= 16 )
                goto LABEL_52;
            }
            v17 = hWndHidServ;
            *(_DWORD *)((char *)PendingButtonList + 2 * v16) = 0;
            *((_WORD *)PendingButtonList + v16 + 2) = 0;
            PostMessageW(
              v17,
              0x813Au,
              (unsigned __int16)*v9 | ((unsigned __int64)*(unsigned __int16 *)(v3 + 6) << 16),
              (unsigned __int64)*v13 << 16);
            v6 = WPP_GLOBAL_Control;
          }
LABEL_52:
          ;
        }
        v18 = *(_QWORD *)(v3 + 24);
        *(_QWORD *)(v3 + 24) = *(_QWORD *)(v3 + 32);
        *(_QWORD *)(v3 + 32) = v18;
      }
      else
      {
        if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 && *((_BYTE *)v6 + 25) >= 4u )
        {
          WPP_SF_DDD(v6[2], 30, a3, *(unsigned __int16 *)(v3 + 2), *(unsigned __int16 *)(v3 + 16), v7);
          v6 = WPP_GLOBAL_Control;
        }
        if ( !*(_DWORD *)(v3 + 24) || !*(_DWORD *)(v3 + 28) )
          goto LABEL_62;
        PostMessageW(
          hWndHidServ,
          0x813Au,
          ((unsigned __int64)*(unsigned __int16 *)(v3 + 6) << 16) | *(unsigned __int16 *)(v3 + 16),
          ((unsigned __int64)*(unsigned __int16 *)(v3 + 2) << 16)
        | (unsigned __int16)(int)((double)*(int *)(v3 + 24) / (double)*(int *)(v3 + 28) * 65536.0));
      }
      v6 = WPP_GLOBAL_Control;
LABEL_62:
      ++v5;
      v3 += 40;
    }
    while ( v5 < *(_DWORD *)(a1 + 200) );
  }
}

```

## disassembly

```asm
0x1800030d4  push    rbx
0x1800030d6  push    rbp
0x1800030d7  push    rsi
0x1800030d8  push    rdi
0x1800030d9  push    r12
0x1800030db  push    r14
0x1800030dd  push    r15
0x1800030df  sub     rsp, 30h
0x1800030e3  mov     rbx, [rcx+0C0h]
0x1800030ea  xor     r12d, r12d
0x1800030ed  mov     rbp, rcx
0x1800030f0  mov     r15d, r12d
0x1800030f3  cmp     [rcx+0C8h], r12d
0x1800030fa  jbe     loc_180003504
0x180003100  mov     r10, cs:WPP_GLOBAL_Control
0x180003107  lea     esi, [r12+1]
0x18000310c  lea     rdx, WPP_GLOBAL_Control
0x180003113  movzx   eax, word ptr [rbx+6]
0x180003117  test    ax, ax
0x18000311a  jnz     short loc_18000312A
0x18000311c  mov     [rbx+6], si
0x180003120  movzx   eax, si
0x180003123  mov     r10, cs:WPP_GLOBAL_Control
0x18000312a  cmp     dword ptr [rbx+8], 110000h
0x180003131  jnz     loc_1800034E9
0x180003137  cmp     [rbx], r12b
0x18000313a  jz      loc_180003445
0x180003140  cmp     r10, rdx
0x180003143  jz      short loc_180003182
0x180003145  test    byte ptr [r10+1Ch], 4
0x18000314a  jz      short loc_180003182
0x18000314c  cmp     byte ptr [r10+19h], 4
0x180003151  jb      short loc_180003182
0x180003153  movzx   r9d, word ptr [rbx+2]
0x180003158  lea     r8, WPP_a78e9b98c57431a096020c8f92b2d1b7_Traceguids
0x18000315f  mov     rcx, [r10+10h]
0x180003163  mov     edx, 1Ah
0x180003168  movzx   eax, ax
0x18000316b  mov     [rsp+68h+var_48], eax
0x18000316f  call    WPP_SF_DD
0x180003174  mov     r10, cs:WPP_GLOBAL_Control
0x18000317b  lea     rdx, WPP_GLOBAL_Control
0x180003182  mov     rdi, [rbx+18h]
0x180003186  mov     r14, [rbx+20h]
0x18000318a  jmp     loc_180003300
0x18000318f  cmp     r10, rdx
0x180003192  jz      short loc_1800031CA
0x180003194  test    byte ptr [r10+1Ch], 10h
0x180003199  jz      short loc_1800031CA
0x18000319b  cmp     byte ptr [r10+19h], 4
0x1800031a0  jb      short loc_1800031CA
0x1800031a2  movzx   eax, word ptr [rdi]
0x1800031a5  lea     r8, WPP_a78e9b98c57431a096020c8f92b2d1b7_Traceguids
0x1800031ac  movzx   r9d, word ptr [rdi+2]
0x1800031b1  mov     edx, 1Bh
0x1800031b6  mov     rcx, [r10+10h]
0x1800031ba  mov     [rsp+68h+var_48], eax
0x1800031be  call    WPP_SF_DD
0x1800031c3  mov     r10, cs:WPP_GLOBAL_Control
0x1800031ca  cmp     [rbp+0CCh], r12b
0x1800031d1  jz      short loc_1800031E2
0x1800031d3  mov     eax, 8000h
0x1800031d8  or      [rdi], ax
0x1800031db  mov     r10, cs:WPP_GLOBAL_Control
0x1800031e2  movzx   r8d, word ptr [rbx+6]
0x1800031e7  lea     r9, PendingButtonList
0x1800031ee  mov     ecx, r12d
0x1800031f1  mov     eax, ecx
0x1800031f3  lea     rdx, [rax+rax*2]
0x1800031f7  cmp     [r9+rdx*2], r8w
0x1800031fc  jnz     short loc_180003219
0x1800031fe  movzx   eax, word ptr [rdi+2]
0x180003202  cmp     [r9+rdx*2+2], ax
0x180003208  jnz     short loc_180003219
0x18000320a  movzx   eax, word ptr [rdi]
0x18000320d  cmp     [r9+rdx*2+4], ax
0x180003213  jz      loc_1800032F5
0x180003219  add     ecx, esi
0x18000321b  cmp     ecx, 10h
0x18000321e  jl      short loc_1800031F1
0x180003220  movzx   r9d, word ptr [rdi+2]
0x180003225  mov     edx, 813Ah; Msg
0x18000322a  movzx   r8d, word ptr [rbx+6]
0x18000322f  movzx   eax, word ptr [rdi]
0x180003232  mov     rcx, cs:hWndHidServ; hWnd
0x180003239  shl     r9, 10h
0x18000323d  shl     r8, 10h
0x180003241  or      r9, rsi; lParam
0x180003244  or      r8, rax; wParam
0x180003247  call    cs:__imp_PostMessageW
0x18000324d  mov     edx, r12d
0x180003250  lea     r9, PendingButtonList
0x180003257  mov     eax, edx
0x180003259  lea     rcx, [rax+rax*2]
0x18000325d  cmp     [r9+rcx*2], r12w
0x180003262  jnz     short loc_180003278
0x180003264  cmp     [r9+rcx*2+2], r12w
0x18000326a  jnz     short loc_180003278
0x18000326c  cmp     [r9+rcx*2+4], r12w
0x180003272  jz      loc_1800033BA
0x180003278  add     edx, esi
0x18000327a  cmp     edx, 10h
0x18000327d  jl      short loc_180003257
0x18000327f  jnz     short loc_1800032EE
0x180003281  movzx   r8d, word ptr [rbx+6]
0x180003286  mov     edx, 813Ah; Msg
0x18000328b  movzx   r9d, word ptr [rdi+2]
0x180003290  movzx   eax, word ptr [rdi]
0x180003293  mov     rcx, cs:hWndHidServ; hWnd
0x18000329a  shl     r8, 10h
0x18000329e  or      r8, rax; wParam
0x1800032a1  shl     r9, 10h; lParam
0x1800032a5  call    cs:__imp_PostMessageW
0x1800032ab  mov     r10, cs:WPP_GLOBAL_Control
0x1800032b2  lea     rdx, WPP_GLOBAL_Control
0x1800032b9  cmp     r10, rdx
0x1800032bc  jz      short loc_1800032FC
0x1800032be  test    byte ptr [r10+1Ch], 4
0x1800032c3  jz      short loc_1800032FC
0x1800032c5  cmp     byte ptr [r10+19h], 4
0x1800032ca  jb      short loc_1800032FC
0x1800032cc  movzx   ecx, word ptr [rdi]
0x1800032cf  mov     edx, 1Ch
0x1800032d4  movzx   eax, word ptr [rdi+2]
0x1800032d8  movzx   r9d, word ptr [rbx+6]
0x1800032dd  mov     [rsp+68h+var_40], eax
0x1800032e1  mov     [rsp+68h+var_48], ecx
0x1800032e5  mov     rcx, [r10+10h]
0x1800032e9  call    WPP_SF_DDD
0x1800032ee  mov     r10, cs:WPP_GLOBAL_Control
0x1800032f5  lea     rdx, WPP_GLOBAL_Control
0x1800032fc  add     rdi, 4
0x180003300  cmp     [rdi], r12w
0x180003304  jnz     loc_18000318F
0x18000330a  cmp     [r14], r12w
0x18000330e  jz      loc_180003430
0x180003314  movzx   eax, word ptr [rdi]
0x180003317  lea     rsi, [r14+2]
0x18000331b  test    ax, ax
0x18000331e  jz      short loc_180003342
0x180003320  mov     rcx, rdi
0x180003323  cmp     [r14], ax
0x180003327  jnz     short loc_180003336
0x180003329  movzx   eax, word ptr [rcx+2]
0x18000332d  cmp     [rsi], ax
0x180003330  jz      loc_180003416
0x180003336  add     rcx, 4
0x18000333a  movzx   eax, word ptr [rcx]
0x18000333d  test    ax, ax
0x180003340  jnz     short loc_180003323
0x180003342  cmp     r10, rdx
0x180003345  jz      short loc_18000337E
0x180003347  test    byte ptr [r10+1Ch], 4
0x18000334c  jz      short loc_18000337E
0x18000334e  cmp     byte ptr [r10+19h], 4
0x180003353  jb      short loc_18000337E
0x180003355  movzx   ecx, word ptr [r14]
0x180003359  mov     edx, 1Dh
0x18000335e  movzx   eax, word ptr [rsi]
0x180003361  movzx   r9d, word ptr [rbx+6]
0x180003366  mov     [rsp+68h+var_40], eax
0x18000336a  mov     [rsp+68h+var_48], ecx
0x18000336e  mov     rcx, [r10+10h]
0x180003372  call    WPP_SF_DDD
0x180003377  mov     r10, cs:WPP_GLOBAL_Control
0x18000337e  movzx   r8d, word ptr [rbx+6]
0x180003383  lea     r9, PendingButtonList
0x18000338a  mov     ecx, r12d
0x18000338d  mov     eax, ecx
0x18000338f  lea     rdx, [rax+rax*2]
0x180003393  cmp     [r9+rdx*2], r8w
0x180003398  jnz     short loc_1800033B1
0x18000339a  movzx   eax, word ptr [rsi]
0x18000339d  cmp     [r9+rdx*2+2], ax
0x1800033a3  jnz     short loc_1800033B1
0x1800033a5  movzx   eax, word ptr [r14]
0x1800033a9  cmp     [r9+rdx*2+4], ax
0x1800033af  jz      short loc_1800033DB
0x1800033b1  inc     ecx
0x1800033b3  cmp     ecx, 10h
0x1800033b6  jl      short loc_18000338D
0x1800033b8  jmp     short loc_180003416
0x1800033ba  movzx   eax, word ptr [rbx+6]
0x1800033be  mov     [r9+rcx*2], ax
0x1800033c3  movzx   eax, word ptr [rdi+2]
0x1800033c7  mov     [r9+rcx*2+2], ax
0x1800033cd  movzx   eax, word ptr [rdi]
0x1800033d0  mov     [r9+rcx*2+4], ax
0x1800033d6  jmp     loc_1800032EE
0x1800033db  mov     rcx, cs:hWndHidServ; hWnd
0x1800033e2  mov     [r9+rdx*2], r12d
0x1800033e6  mov     [r9+rdx*2+4], r12w
0x1800033ec  mov     edx, 813Ah; Msg
0x1800033f1  movzx   r8d, word ptr [rbx+6]
0x1800033f6  movzx   r9d, word ptr [rsi]
0x1800033fa  movzx   eax, word ptr [r14]
0x1800033fe  shl     r8, 10h
0x180003402  or      r8, rax; wParam
0x180003405  shl     r9, 10h; lParam
0x180003409  call    cs:__imp_PostMessageW
0x18000340f  mov     r10, cs:WPP_GLOBAL_Control
0x180003416  add     r14, 4
0x18000341a  lea     rdx, WPP_GLOBAL_Control
0x180003421  cmp     [r14], r12w
0x180003425  jnz     loc_180003314
0x18000342b  mov     esi, 1
0x180003430  mov     rcx, [rbx+18h]
0x180003434  mov     rax, [rbx+20h]
0x180003438  mov     [rbx+18h], rax
0x18000343c  mov     [rbx+20h], rcx
0x180003440  jmp     loc_1800034E2
0x180003445  cmp     r10, rdx
0x180003448  jz      short loc_180003481
0x18000344a  test    byte ptr [r10+1Ch], 4
0x18000344f  jz      short loc_180003481
0x180003451  cmp     byte ptr [r10+19h], 4
0x180003456  jb      short loc_180003481
0x180003458  movzx   ecx, word ptr [rbx+10h]
0x18000345c  mov     edx, 1Eh
0x180003461  movzx   r9d, word ptr [rbx+2]
0x180003466  movzx   eax, ax
0x180003469  mov     [rsp+68h+var_40], eax
0x18000346d  mov     [rsp+68h+var_48], ecx
0x180003471  mov     rcx, [r10+10h]
0x180003475  call    WPP_SF_DDD
0x18000347a  mov     r10, cs:WPP_GLOBAL_Control
0x180003481  cmp     [rbx+18h], r12d
0x180003485  jz      short loc_1800034E9
0x180003487  cmp     [rbx+1Ch], r12d
0x18000348b  jz      short loc_1800034E9
0x18000348d  mov     eax, [rbx+1Ch]
0x180003490  xorps   xmm0, xmm0
0x180003493  movd    xmm1, dword ptr [rbx+18h]
0x180003498  mov     edx, 813Ah; Msg
0x18000349d  movzx   r8d, word ptr [rbx+10h]
0x1800034a2  mov     rcx, cs:hWndHidServ; hWnd
0x1800034a9  cvtsi2sd xmm0, rax
0x1800034ae  cvtdq2pd xmm1, xmm1
0x1800034b2  divsd   xmm1, xmm0
0x1800034b6  mulsd   xmm1, cs:__real@40f0000000000000
0x1800034be  cvttsd2si eax, xmm1
0x1800034c2  movzx   r9d, ax
0x1800034c6  movzx   eax, word ptr [rbx+2]
0x1800034ca  shl     rax, 10h
0x1800034ce  or      r9, rax; lParam
0x1800034d1  movzx   eax, word ptr [rbx+6]
0x1800034d5  shl     rax, 10h
0x1800034d9  or      r8, rax; wParam
0x1800034dc  call    cs:__imp_PostMessageW
0x1800034e2  mov     r10, cs:WPP_GLOBAL_Control
0x1800034e9  add     r15d, esi
0x1800034ec  lea     rdx, WPP_GLOBAL_Control
0x1800034f3  add     rbx, 28h ; '('
0x1800034f7  cmp     r15d, [rbp+0C8h]
0x1800034fe  jb      loc_180003113
0x180003504  add     rsp, 30h
0x180003508  pop     r15
0x18000350a  pop     r14
0x18000350c  pop     r12
0x18000350e  pop     rdi
0x18000350f  pop     rsi
0x180003510  pop     rbp
0x180003511  pop     rbx
0x180003512  retn
```
