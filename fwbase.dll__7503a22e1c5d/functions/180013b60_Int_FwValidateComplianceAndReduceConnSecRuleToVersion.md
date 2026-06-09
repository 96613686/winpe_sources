# Int_FwValidateComplianceAndReduceConnSecRuleToVersion

- ea: `0x180013b60`
- end: `0x180014020`
- name: `Int_FwValidateComplianceAndReduceConnSecRuleToVersion`
- size: `1216`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800150e0`

## callees

- `0x180004840`
- `0x18000ccd4`
- `0x180010d70`
- `0x180013b60`
- `0x180017d1c`

## pseudocode

```c
__int64 __fastcall Int_FwValidateComplianceAndReduceConnSecRuleToVersion(
        __int64 a1,
        enum _tag_FW_RULE_STATUS *a2,
        unsigned __int16 a3)
{
  __int16 *v6; // rcx
  __int16 v7; // ax
  __int64 v8; // r9
  unsigned int v9; // esi
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 i; // r8
  char v14; // r9
  __int16 v15; // ax
  enum _tag_FW_RULE_STATUS *v16; // r14
  unsigned int v17; // eax
  unsigned __int16 v18; // ax
  __int64 v19; // rcx
  __int64 v20; // rcx
  unsigned __int16 v21; // ax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 340, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids);
  v6 = (__int16 *)(a1 + 340);
  if ( a3 >= 0x208u )
  {
    if ( a3 >= 0x209u )
    {
      if ( a3 >= 0x20Au )
      {
        v9 = 0;
        v16 = (enum _tag_FW_RULE_STATUS *)(a1 + 384);
        if ( a3 >= 0x214u )
        {
          if ( a3 >= 0x218u )
            return v9;
          goto LABEL_73;
        }
LABEL_48:
        if ( *(_DWORD *)(a1 + 496) )
        {
          if ( a2 )
          {
            v8 = 87;
            *(_DWORD *)a2 = 1048820;
            v9 = 87;
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v11 = 347;
              goto LABEL_10;
            }
            return v9;
          }
          *(_DWORD *)v16 = 0x40000;
        }
        v18 = *(_WORD *)(a1 + 340);
        if ( v18 >= 0x40u )
        {
          if ( a2 )
          {
            if ( (v18 & 0x40) != 0 )
            {
              v8 = 87;
              *(_DWORD *)a2 = 1049874;
              v9 = 87;
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v11 = 348;
                goto LABEL_10;
              }
              return v9;
            }
            if ( (v18 & 0x80u) != 0 )
            {
              v8 = 87;
              *(_DWORD *)a2 = 1049875;
              v9 = 87;
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v11 = 349;
                goto LABEL_10;
              }
              return v9;
            }
          }
          else
          {
            *(_DWORD *)v16 = 0x20000;
            *(_WORD *)(a1 + 340) = v18 & 0x3F;
          }
        }
        v19 = *(_QWORD *)(a1 + 504);
        if ( v19 )
        {
          if ( a2 )
          {
            v8 = 87;
            *(_DWORD *)a2 = 1049876;
            v9 = 87;
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v11 = 350;
              goto LABEL_10;
            }
            return v9;
          }
          *(_DWORD *)(a1 + 384) = 0x20000;
          FwFree(v19);
          v20 = *(_QWORD *)(a1 + 512);
          *(_QWORD *)(a1 + 504) = 0;
          if ( v20 )
          {
            *(_DWORD *)(a1 + 384) = 0x20000;
            FwFree(v20);
            *(_QWORD *)(a1 + 512) = 0;
          }
        }
LABEL_73:
        v21 = *(_WORD *)(a1 + 340);
        if ( v21 >= 0x100u )
        {
          if ( !a2 )
          {
            *(_DWORD *)(a1 + 384) = 0x20000;
            *(_WORD *)(a1 + 340) = (unsigned __int8)v21;
            return v9;
          }
          if ( (v21 & 0x100) != 0 )
          {
            v8 = 87;
            *(_DWORD *)a2 = 1049881;
            v9 = 87;
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v11 = 352;
              goto LABEL_10;
            }
          }
        }
        return v9;
      }
LABEL_36:
      v15 = *v6;
      if ( (unsigned __int16)*v6 < 4u )
      {
        v16 = (enum _tag_FW_RULE_STATUS *)(a1 + 384);
      }
      else
      {
        if ( a2 )
        {
          v8 = 87;
          *(_DWORD *)a2 = 1048761;
          v9 = 87;
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v11 = 345;
            goto LABEL_10;
          }
          return v9;
        }
        v16 = (enum _tag_FW_RULE_STATUS *)(a1 + 384);
        *(_DWORD *)(a1 + 384) = 0x20000;
        *v6 = v15 & 3;
      }
      v17 = FwValidateComplianceAndReduceRuleOnPortList(
              (struct _tag_FW_PORTS *)(a1 + 256),
              (struct _tag_FW_PORTS *)(a1 + 280),
              a2,
              v16);
      v9 = v17;
      if ( v17 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 346;
          v8 = v17;
          goto LABEL_10;
        }
        return v9;
      }
      goto LABEL_48;
    }
LABEL_28:
    if ( (*(_BYTE *)v6 & 2) != 0 && *(_DWORD *)(a1 + 336) == 4 )
    {
      if ( a2 )
      {
        v8 = 87;
        *(_DWORD *)a2 = 1048818;
        v9 = 87;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 344;
          goto LABEL_10;
        }
        return v9;
      }
      *(_DWORD *)(a1 + 384) = 0x40000;
    }
    goto LABEL_36;
  }
  v7 = *v6;
  if ( (unsigned __int16)*v6 >= 2u )
  {
    if ( a2 )
    {
      v8 = 87;
      *(_DWORD *)a2 = 1048654;
      v9 = 87;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 341;
LABEL_10:
        WPP_SF_d(v10[2], v11, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, v8);
        return v9;
      }
      return v9;
    }
    *(_DWORD *)(a1 + 384) = 0x20000;
    *v6 = v7 & 1;
    *(_DWORD *)(a1 + 212) = 0;
    *(_DWORD *)(a1 + 232) = 0;
    *(_OWORD *)(a1 + 216) = 0;
    *(_OWORD *)(a1 + 236) = 0;
  }
  v12 = *(_QWORD *)(a1 + 360);
  if ( v12 )
  {
    if ( *(_DWORD *)(a1 + 352) )
    {
LABEL_14:
      for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 352); i = (unsigned int)(i + 1) )
      {
        if ( (*(_BYTE *)(v12 + 4 * i) & 0xF8u) >= 8 )
        {
          if ( a2 )
          {
            v8 = 87;
            *(_DWORD *)a2 = 1048801;
            v9 = 87;
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v11 = 343;
              goto LABEL_10;
            }
            return v9;
          }
          v14 = *(_BYTE *)(v12 + 4 * i) & 7;
          *(_DWORD *)(a1 + 384) = 0x20000;
          *(_BYTE *)(v12 + 4 * i) = v14;
          v12 = *(_QWORD *)(a1 + 360);
        }
      }
      goto LABEL_28;
    }
  }
  else if ( !*(_DWORD *)(a1 + 352) )
  {
    goto LABEL_14;
  }
  v8 = 87;
  *(_DWORD *)a2 = 1048800;
  v9 = 87;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v11 = 342;
    goto LABEL_10;
  }
  return v9;
}

```

## disassembly

```asm
0x180013b60  push    rbx
0x180013b62  push    rbp
0x180013b63  push    rsi
0x180013b64  push    rdi
0x180013b65  push    r12
0x180013b67  push    r13
0x180013b69  push    r14
0x180013b6b  sub     rsp, 20h
0x180013b6f  movzx   ebp, r8w
0x180013b73  mov     rdi, rdx
0x180013b76  mov     rbx, rcx
0x180013b79  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b80  lea     r13, WPP_GLOBAL_Control
0x180013b87  lea     r11, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids
0x180013b8e  cmp     rcx, r13
0x180013b91  jz      short loc_180013BB1
0x180013b93  test    byte ptr [rcx+1Ch], 8
0x180013b97  jz      short loc_180013BB1
0x180013b99  mov     rcx, [rcx+10h]
0x180013b9d  mov     edx, 154h
0x180013ba2  mov     r8, r11
0x180013ba5  call    WPP_SF_
0x180013baa  lea     r11, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids
0x180013bb1  mov     esi, 4
0x180013bb6  lea     rcx, [rbx+154h]
0x180013bbd  mov     eax, 208h
0x180013bc2  lea     r12d, [rsi-3]
0x180013bc6  cmp     bp, ax
0x180013bc9  jnb     loc_180013D16
0x180013bcf  movzx   eax, word ptr [rcx]
0x180013bd2  cmp     ax, 2
0x180013bd6  jb      short loc_180013C53
0x180013bd8  test    rdi, rdi
0x180013bdb  jz      short loc_180013C1A
0x180013bdd  lea     r9d, [rsi+53h]
0x180013be1  mov     dword ptr [rdi], 10004Eh
0x180013be7  mov     esi, r9d
0x180013bea  mov     rcx, cs:WPP_GLOBAL_Control
0x180013bf1  cmp     rcx, r13
0x180013bf4  jz      loc_18001400F
0x180013bfa  test    [rcx+1Ch], r12b
0x180013bfe  jz      loc_18001400F
0x180013c04  mov     edx, 155h
0x180013c09  mov     r8, r11
0x180013c0c  mov     rcx, [rcx+10h]
0x180013c10  call    WPP_SF_d
0x180013c15  jmp     loc_18001400F
0x180013c1a  mov     dword ptr [rbx+180h], 20000h
0x180013c24  and     ax, r12w
0x180013c28  mov     [rcx], ax
0x180013c2b  xorps   xmm0, xmm0
0x180013c2e  mov     dword ptr [rbx+0D4h], 0
0x180013c38  xorps   xmm1, xmm1
0x180013c3b  mov     dword ptr [rbx+0E8h], 0
0x180013c45  movups  xmmword ptr [rbx+0D8h], xmm0
0x180013c4c  movups  xmmword ptr [rbx+0ECh], xmm1
0x180013c53  mov     rdx, [rbx+168h]
0x180013c5a  test    rdx, rdx
0x180013c5d  jnz     short loc_180013CA7
0x180013c5f  cmp     [rbx+160h], edx
0x180013c65  jnz     short loc_180013CB0
0x180013c67  xor     r8d, r8d
0x180013c6a  cmp     r8d, [rbx+160h]
0x180013c71  jnb     loc_180013D20
0x180013c77  mov     r9b, [rdx+r8*4]
0x180013c7b  mov     al, r9b
0x180013c7e  and     al, 0F8h
0x180013c80  cmp     al, 8
0x180013c82  jb      short loc_180013CA2
0x180013c84  test    rdi, rdi
0x180013c87  jnz     short loc_180013CE3
0x180013c89  and     r9b, 7
0x180013c8d  mov     dword ptr [rbx+180h], 20000h
0x180013c97  mov     [rdx+r8*4], r9b
0x180013c9b  mov     rdx, [rbx+168h]
0x180013ca2  add     r8d, r12d
0x180013ca5  jmp     short loc_180013C6A
0x180013ca7  cmp     dword ptr [rbx+160h], 0
0x180013cae  jnz     short loc_180013C67
0x180013cb0  mov     r9d, 57h ; 'W'
0x180013cb6  mov     dword ptr [rdi], 1000E0h
0x180013cbc  mov     esi, r9d
0x180013cbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180013cc6  cmp     rcx, r13
0x180013cc9  jz      loc_18001400F
0x180013ccf  test    [rcx+1Ch], r12b
0x180013cd3  jz      loc_18001400F
0x180013cd9  mov     edx, 156h
0x180013cde  jmp     loc_180013C09
0x180013ce3  mov     r9d, 57h ; 'W'
0x180013ce9  mov     dword ptr [rdi], 1000E1h
0x180013cef  mov     esi, r9d
0x180013cf2  mov     rcx, cs:WPP_GLOBAL_Control
0x180013cf9  cmp     rcx, r13
0x180013cfc  jz      loc_18001400F
0x180013d02  test    [rcx+1Ch], r12b
0x180013d06  jz      loc_18001400F
0x180013d0c  mov     edx, 157h
0x180013d11  jmp     loc_180013C09
0x180013d16  mov     eax, 209h
0x180013d1b  cmp     bp, ax
0x180013d1e  jnb     short loc_180013D71
0x180013d20  test    byte ptr [rcx], 2
0x180013d23  jz      short loc_180013D7F
0x180013d25  cmp     [rbx+150h], esi
0x180013d2b  jnz     short loc_180013D7F
0x180013d2d  test    rdi, rdi
0x180013d30  jz      short loc_180013D65
0x180013d32  mov     r9d, 57h ; 'W'
0x180013d38  mov     dword ptr [rdi], 1000F2h
0x180013d3e  mov     esi, r9d
0x180013d41  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d48  cmp     rcx, r13
0x180013d4b  jz      loc_18001400F
0x180013d51  test    [rcx+1Ch], r12b
0x180013d55  jz      loc_18001400F
0x180013d5b  mov     edx, 158h
0x180013d60  jmp     loc_180013C09
0x180013d65  mov     dword ptr [rbx+180h], 40000h
0x180013d6f  jmp     short loc_180013D7F
0x180013d71  mov     eax, 20Ah
0x180013d76  cmp     bp, ax
0x180013d79  jnb     loc_180013E2A
0x180013d7f  movzx   eax, word ptr [rcx]
0x180013d82  cmp     ax, si
0x180013d85  jb      short loc_180013DD6
0x180013d87  test    rdi, rdi
0x180013d8a  jz      short loc_180013DBF
0x180013d8c  mov     r9d, 57h ; 'W'
0x180013d92  mov     dword ptr [rdi], 1000B9h
0x180013d98  mov     esi, r9d
0x180013d9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180013da2  cmp     rcx, r13
0x180013da5  jz      loc_18001400F
0x180013dab  test    [rcx+1Ch], r12b
0x180013daf  jz      loc_18001400F
0x180013db5  mov     edx, 159h
0x180013dba  jmp     loc_180013C09
0x180013dbf  lea     r14, [rbx+180h]
0x180013dc6  and     ax, 3
0x180013dca  mov     dword ptr [r14], 20000h
0x180013dd1  mov     [rcx], ax
0x180013dd4  jmp     short loc_180013DDD
0x180013dd6  lea     r14, [rbx+180h]
0x180013ddd  lea     rdx, [rbx+118h]; struct _tag_FW_PORTS *
0x180013de4  mov     r9, r14; enum _tag_FW_RULE_STATUS *
0x180013de7  lea     rcx, [rbx+100h]; struct _tag_FW_PORTS *
0x180013dee  mov     r8, rdi; enum _tag_FW_RULE_STATUS *
0x180013df1  call    ?FwValidateComplianceAndReduceRuleOnPortList@@YAKPEAU_tag_FW_PORTS@@0PEAW4_tag_FW_RULE_STATUS@@1@Z; FwValidateComplianceAndReduceRuleOnPortList(_tag_FW_PORTS *,_tag_FW_PORTS *,_tag_FW_RULE_STATUS *,_tag_FW_RULE_STATUS *)
0x180013df6  mov     esi, eax
0x180013df8  test    eax, eax
0x180013dfa  jz      short loc_180013E41
0x180013dfc  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e03  cmp     rcx, r13
0x180013e06  jz      loc_18001400F
0x180013e0c  test    [rcx+1Ch], r12b
0x180013e10  jz      loc_18001400F
0x180013e16  mov     edx, 15Ah
0x180013e1b  mov     r9d, eax
0x180013e1e  lea     r8, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids
0x180013e25  jmp     loc_180013C0C
0x180013e2a  xor     esi, esi
0x180013e2c  lea     r14, [rbx+180h]
0x180013e33  mov     eax, 214h
0x180013e38  cmp     bp, ax
0x180013e3b  jnb     loc_180013FA6
0x180013e41  cmp     dword ptr [rbx+1F0h], 0
0x180013e48  jz      short loc_180013E86
0x180013e4a  test    rdi, rdi
0x180013e4d  jz      short loc_180013E7F
0x180013e4f  mov     r9d, 57h ; 'W'
0x180013e55  mov     dword ptr [rdi], 1000F4h
0x180013e5b  mov     esi, r9d
0x180013e5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e65  cmp     rcx, r13
0x180013e68  jz      loc_18001400F
0x180013e6e  test    [rcx+1Ch], r12b
0x180013e72  jz      loc_18001400F
0x180013e78  mov     edx, 15Bh
0x180013e7d  jmp     short loc_180013E1E
0x180013e7f  mov     dword ptr [r14], 40000h
0x180013e86  movzx   eax, word ptr [rbx+154h]
0x180013e8d  cmp     ax, 40h ; '@'
0x180013e91  jb      loc_180013F1C
0x180013e97  test    rdi, rdi
0x180013e9a  jz      short loc_180013F0A
0x180013e9c  test    al, 40h
0x180013e9e  jz      short loc_180013ED3
0x180013ea0  mov     r9d, 57h ; 'W'
0x180013ea6  mov     dword ptr [rdi], 100512h
0x180013eac  mov     esi, r9d
0x180013eaf  mov     rcx, cs:WPP_GLOBAL_Control
0x180013eb6  cmp     rcx, r13
0x180013eb9  jz      loc_18001400F
0x180013ebf  test    [rcx+1Ch], r12b
0x180013ec3  jz      loc_18001400F
0x180013ec9  mov     edx, 15Ch
0x180013ece  jmp     loc_180013E1E
0x180013ed3  test    al, al
0x180013ed5  jns     short loc_180013F1C
0x180013ed7  mov     r9d, 57h ; 'W'
0x180013edd  mov     dword ptr [rdi], 100513h
0x180013ee3  mov     esi, r9d
0x180013ee6  mov     rcx, cs:WPP_GLOBAL_Control
0x180013eed  cmp     rcx, r13
0x180013ef0  jz      loc_18001400F
0x180013ef6  test    [rcx+1Ch], r12b
0x180013efa  jz      loc_18001400F
0x180013f00  mov     edx, 15Dh
0x180013f05  jmp     loc_180013E1E
0x180013f0a  and     ax, 3Fh
0x180013f0e  mov     dword ptr [r14], 20000h
0x180013f15  mov     [rbx+154h], ax
0x180013f1c  mov     rcx, [rbx+1F8h]
0x180013f23  test    rcx, rcx
0x180013f26  jz      loc_180013FB0
0x180013f2c  test    rdi, rdi
0x180013f2f  jz      short loc_180013F64
0x180013f31  mov     r9d, 57h ; 'W'
0x180013f37  mov     dword ptr [rdi], 100514h
0x180013f3d  mov     esi, r9d
0x180013f40  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f47  cmp     rcx, r13
0x180013f4a  jz      loc_18001400F
0x180013f50  test    [rcx+1Ch], r12b
0x180013f54  jz      loc_18001400F
0x180013f5a  mov     edx, 15Eh
0x180013f5f  jmp     loc_180013E1E
0x180013f64  mov     dword ptr [rbx+180h], 20000h
0x180013f6e  call    FwFree
0x180013f73  mov     rcx, [rbx+200h]
0x180013f7a  mov     qword ptr [rbx+1F8h], 0
0x180013f85  test    rcx, rcx
0x180013f88  jz      short loc_180013FB0
0x180013f8a  mov     dword ptr [rbx+180h], 20000h
0x180013f94  call    FwFree
0x180013f99  mov     qword ptr [rbx+200h], 0
0x180013fa4  jmp     short loc_180013FB0
0x180013fa6  mov     eax, 218h
0x180013fab  cmp     bp, ax
0x180013fae  jnb     short loc_18001400F
0x180013fb0  movzx   eax, word ptr [rbx+154h]
0x180013fb7  mov     ecx, 100h
0x180013fbc  cmp     ax, cx
0x180013fbf  jb      short loc_18001400F
0x180013fc1  test    rdi, rdi
0x180013fc4  jz      short loc_180013FF6
0x180013fc6  test    cx, ax
0x180013fc9  jz      short loc_18001400F
0x180013fcb  mov     r9d, 57h ; 'W'
0x180013fd1  mov     dword ptr [rdi], 100519h
0x180013fd7  mov     esi, r9d
0x180013fda  mov     rcx, cs:WPP_GLOBAL_Control
0x180013fe1  cmp     rcx, r13
0x180013fe4  jz      short loc_18001400F
0x180013fe6  test    [rcx+1Ch], r12b
0x180013fea  jz      short loc_18001400F
0x180013fec  mov     edx, 160h
0x180013ff1  jmp     loc_180013E1E
0x180013ff6  mov     ecx, 0FFh
0x180013ffb  mov     dword ptr [rbx+180h], 20000h
0x180014005  and     ax, cx
0x180014008  mov     [rbx+154h], ax
0x18001400f  mov     eax, esi
0x180014011  add     rsp, 20h
0x180014015  pop     r14
0x180014017  pop     r13
0x180014019  pop     r12
0x18001401b  pop     rdi
0x18001401c  pop     rsi
0x18001401d  pop     rbp
0x18001401e  pop     rbx
0x18001401f  retn
```
