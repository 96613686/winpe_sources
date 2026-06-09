# UpdateStateInfo(HWND__ *,uint,int)

- ea: `0x180008358`
- end: `0x18000870d`
- name: `?UpdateStateInfo@@YAHPEAUHWND__@@IH@Z`
- size: `949`
- prototype: `__int64 __fastcall(HWND hDlg, unsigned int, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000b2e4`
- `0x18000bdf0`
- `0x18000cea0`

## callees

- `0x180008300`
- `0x180008358`

## import_xrefs

- `ext-ms-win-ntuser-dialogbox-l1-1-2!CheckRadioButton` at `0x18000841f`
- `ext-ms-win-ntuser-dialogbox-l1-1-2!CheckRadioButton` at `0x18000841f`

## pseudocode

```c
__int64 __fastcall UpdateStateInfo(HWND hDlg, unsigned int a2, signed int a3)
{
  unsigned int v4; // edx
  unsigned int v5; // edx
  unsigned int v6; // edx
  unsigned int v7; // edx
  unsigned int v8; // edx
  unsigned int v9; // edx
  unsigned int v10; // edx
  unsigned int v11; // edx
  struct _CONSOLE_STATE_INFO *v12; // rax
  HWND v13; // rcx
  int v14; // ecx
  int v15; // ecx
  struct _CONSOLE_STATE_INFO *v16; // rcx
  int v17; // eax
  bool v18; // zf
  struct _CONSOLE_STATE_INFO *v19; // rcx
  unsigned int v20; // edx
  unsigned int v21; // edx
  unsigned int v22; // edx
  unsigned int v23; // edx
  unsigned int v24; // edx
  unsigned int v25; // edx
  unsigned int v26; // edx
  unsigned int v27; // edx
  struct _CONSOLE_STATE_INFO *v28; // rax
  __int16 v29; // r8
  struct _CONSOLE_STATE_INFO *v30; // rcx
  signed int v31; // eax
  struct _CONSOLE_STATE_INFO *v32; // rcx
  struct _CONSOLE_STATE_INFO *v33; // rcx
  signed int v34; // eax
  struct _CONSOLE_STATE_INFO *v35; // rax
  __int16 v36; // r8

  if ( a2 > 0x193 )
  {
    switch ( a2 )
    {
      case 0x194u:
        v35 = gpStateInfo;
        *((_WORD *)gpStateInfo + 51) &= 0xFu;
        v36 = 16 * a3;
        goto LABEL_70;
      case 0x195u:
      case 0x196u:
      case 0x197u:
      case 0x198u:
      case 0x199u:
      case 0x19Au:
      case 0x19Bu:
      case 0x19Cu:
      case 0x19Du:
      case 0x19Eu:
      case 0x19Fu:
      case 0x1A0u:
      case 0x1A1u:
      case 0x1A2u:
      case 0x1A3u:
      case 0x1A4u:
        *((_DWORD *)gpStateInfo + a2 - 377) = a3;
        return 1;
      default:
        return 0;
    }
  }
  if ( a2 == 403 )
  {
    v35 = gpStateInfo;
    *((_WORD *)gpStateInfo + 51) &= 0xF0u;
    v36 = a3 & 0xF;
LABEL_70:
    *((_WORD *)v35 + 51) |= v36;
    return 1;
  }
  if ( a2 > 0x12D )
  {
    v21 = a2 - 303;
    if ( v21 )
    {
      v22 = v21 - 2;
      if ( v22 )
      {
        v23 = v22 - 2;
        if ( v23 )
        {
          v24 = v23 - 2;
          if ( !v24 )
          {
            if ( a3 >= 0 )
            {
              if ( a3 >= 0x7FFF )
                a3 = 0x7FFF;
            }
            else if ( a3 <= -32768 )
            {
              a3 = -32768;
            }
            *((_DWORD *)gpStateInfo + 2) = a3;
            return 1;
          }
          v25 = v24 - 2;
          if ( !v25 )
          {
            if ( a3 >= 0 )
            {
              if ( a3 >= 0x7FFF )
                a3 = 0x7FFF;
            }
            else if ( a3 <= -32768 )
            {
              a3 = -32768;
            }
            *((_DWORD *)gpStateInfo + 3) = a3;
            return 1;
          }
          v26 = v25 - 2;
          if ( v26 )
          {
            v27 = v26 - 88;
            if ( v27 )
            {
              if ( v27 != 1 )
                return 0;
              v28 = gpStateInfo;
              *((_WORD *)gpStateInfo + 50) &= 0xFu;
              v29 = 16 * a3;
            }
            else
            {
              v28 = gpStateInfo;
              *((_WORD *)gpStateInfo + 50) &= 0xF0u;
              v29 = a3 & 0xF;
            }
            *((_WORD *)v28 + 50) |= v29;
            return 1;
          }
          v16 = gpStateInfo;
          v17 = (*((_DWORD *)gpStateInfo + 24) ^ (4 * a3)) & 4;
LABEL_46:
          *((_DWORD *)v16 + 24) ^= v17;
          return 1;
        }
        v30 = gpStateInfo;
        v31 = *((__int16 *)gpStateInfo + 1);
        *((_WORD *)gpStateInfo + 3) = a3;
        if ( v31 >= a3 )
          return 1;
        *((_WORD *)v30 + 1) = a3;
        v20 = 303;
      }
      else
      {
        v18 = !g_fForceV2;
        v32 = gpStateInfo;
        *((_WORD *)gpStateInfo + 2) = a3;
        if ( (v18 || !*((_DWORD *)v32 + 54)) && *(__int16 *)v32 >= a3 )
          return 1;
        *(_WORD *)v32 = a3;
        v20 = 301;
      }
    }
    else
    {
      v33 = gpStateInfo;
      v34 = *((__int16 *)gpStateInfo + 3);
      *((_WORD *)gpStateInfo + 1) = a3;
      if ( v34 <= a3 )
        return 1;
      *((_WORD *)v33 + 3) = a3;
      v20 = 307;
    }
LABEL_33:
    UpdateItem(hDlg, v20, a3);
    return 1;
  }
  if ( a2 == 301 )
  {
    v18 = !g_fForceV2;
    v19 = gpStateInfo;
    *(_WORD *)gpStateInfo = a3;
    if ( (v18 || !*((_DWORD *)v19 + 54)) && *((__int16 *)v19 + 2) <= a3 )
      return 1;
    *((_WORD *)v19 + 2) = a3;
    v20 = 305;
    goto LABEL_33;
  }
  v4 = a2 - 103;
  if ( !v4 )
  {
    v16 = gpStateInfo;
    v17 = (*((_DWORD *)gpStateInfo + 24) ^ (2 * a3)) & 2;
    goto LABEL_46;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    v16 = gpStateInfo;
    v17 = (*((_DWORD *)gpStateInfo + 24) ^ (8 * a3)) & 8;
    goto LABEL_46;
  }
  v6 = v5 - 4;
  if ( !v6 )
  {
    v15 = 1;
    if ( a3 >= 1 )
      v15 = a3;
    *((_DWORD *)gpStateInfo + 26) = v15;
    return 1;
  }
  v7 = v6 - 2;
  if ( !v7 )
  {
    v14 = 1;
    if ( a3 >= 1 )
      v14 = a3;
    *((_DWORD *)gpStateInfo + 27) = v14;
    return 1;
  }
  v8 = v7 - 2;
  if ( !v8 )
  {
    *((_DWORD *)gpStateInfo + 24) ^= (*((_DWORD *)gpStateInfo + 24) ^ (16 * a3)) & 0x10;
    return 1;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    *((_DWORD *)gpStateInfo + 52) = a3;
    return 1;
  }
  v10 = v9 - 37;
  if ( !v10 )
  {
    v12 = gpStateInfo;
    *((_DWORD *)gpStateInfo + 23) = 25;
LABEL_17:
    v13 = g_hTerminalDlg;
    *((_DWORD *)v12 + 60) = 0;
    if ( v13 != HWND_MESSAGE|0x2LL )
      CheckRadioButton(v13, 617, 621, 617);
    return 1;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    v12 = gpStateInfo;
    *((_DWORD *)gpStateInfo + 23) = 50;
    goto LABEL_17;
  }
  if ( v11 == 1 )
  {
    v12 = gpStateInfo;
    *((_DWORD *)gpStateInfo + 23) = 100;
    goto LABEL_17;
  }
  return 0;
}

```

## disassembly

```asm
0x180008358  sub     rsp, 28h
0x18000835c  mov     eax, 193h
0x180008361  mov     r9, rcx
0x180008364  cmp     edx, eax
0x180008366  ja      loc_180008691
0x18000836c  jz      loc_180008675
0x180008372  lea     r10d, [rax-66h]
0x180008376  cmp     edx, r10d
0x180008379  ja      loc_180008506
0x18000837f  jz      loc_1800084C5
0x180008385  sub     edx, 67h ; 'g'
0x180008388  jz      loc_1800084AF
0x18000838e  sub     edx, 1
0x180008391  jz      loc_180008495
0x180008397  sub     edx, 4
0x18000839a  jz      loc_18000847A
0x1800083a0  sub     edx, 2
0x1800083a3  jz      loc_18000845F
0x1800083a9  sub     edx, 2
0x1800083ac  jz      loc_180008443
0x1800083b2  sub     edx, 1
0x1800083b5  jz      short loc_180008430
0x1800083b7  sub     edx, 25h ; '%'
0x1800083ba  jz      short loc_1800083EA
0x1800083bc  sub     edx, 1
0x1800083bf  jz      short loc_1800083DA
0x1800083c1  cmp     edx, 1
0x1800083c4  jnz     def_1800086B7; jumptable 00000001800086B7 default case
0x1800083ca  mov     rax, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x1800083d1  mov     dword ptr [rax+5Ch], 64h ; 'd'
0x1800083d8  jmp     short loc_1800083F8
0x1800083da  mov     rax, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x1800083e1  mov     dword ptr [rax+5Ch], 32h ; '2'
0x1800083e8  jmp     short loc_1800083F8
0x1800083ea  mov     rax, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x1800083f1  mov     dword ptr [rax+5Ch], 19h
0x1800083f8  mov     rcx, cs:?g_hTerminalDlg@@3PEAUHWND__@@EA; hDlg
0x1800083ff  mov     dword ptr [rax+0F0h], 0
0x180008409  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000840d  jz      loc_1800086E2
0x180008413  mov     edx, 269h; nIDFirstButton
0x180008418  mov     r9d, edx; nIDCheckButton
0x18000841b  lea     r8d, [rdx+4]; nIDLastButton
0x18000841f  call    cs:__imp_CheckRadioButton
0x180008426  nop     dword ptr [rax+rax+00h]
0x18000842b  jmp     loc_1800086E2
0x180008430  mov     rax, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x180008437  mov     [rax+0D0h], r8d
0x18000843e  jmp     loc_1800086E2
0x180008443  mov     rax, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x18000844a  shl     r8d, 4
0x18000844e  xor     r8d, [rax+60h]
0x180008452  and     r8d, 10h; unsigned int
0x180008456  xor     [rax+60h], r8d
0x18000845a  jmp     loc_1800086E2
0x18000845f  mov     rax, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x180008466  mov     ecx, 1
0x18000846b  cmp     r8d, ecx
0x18000846e  cmovge  ecx, r8d
0x180008472  mov     [rax+6Ch], ecx
0x180008475  jmp     loc_1800086E2
0x18000847a  mov     rax, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x180008481  mov     ecx, 1
0x180008486  cmp     r8d, ecx
0x180008489  cmovge  ecx, r8d
0x18000848d  mov     [rax+68h], ecx
0x180008490  jmp     loc_1800086E2
0x180008495  mov     rcx, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x18000849c  lea     eax, ds:0[r8*8]
0x1800084a4  xor     eax, [rcx+60h]
0x1800084a7  and     eax, 8
0x1800084aa  jmp     loc_18000858F
0x1800084af  mov     rcx, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x1800084b6  lea     eax, [r8+r8]
0x1800084ba  xor     eax, [rcx+60h]
0x1800084bd  and     eax, 2
0x1800084c0  jmp     loc_18000858F
0x1800084c5  cmp     cs:?g_fForceV2@@3HA, 0; int g_fForceV2
0x1800084cc  mov     rcx, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x1800084d3  mov     [rcx], r8w
0x1800084d7  jz      short loc_1800084E2
0x1800084d9  cmp     dword ptr [rcx+0D8h], 0
0x1800084e0  jnz     short loc_1800084EF
0x1800084e2  movsx   eax, word ptr [rcx+4]
0x1800084e6  cmp     eax, r8d
0x1800084e9  jle     loc_1800086E2
0x1800084ef  mov     [rcx+4], r8w
0x1800084f4  mov     edx, 131h; nIDDlgItem
0x1800084f9  mov     rcx, r9; hDlg
0x1800084fc  call    ?UpdateItem@@YAXPEAUHWND__@@II@Z; UpdateItem(HWND__ *,uint,uint)
0x180008501  jmp     loc_1800086E2
0x180008506  mov     r11d, 12Fh
0x18000850c  sub     edx, r11d
0x18000850f  jz      loc_180008651
0x180008515  sub     edx, 2
0x180008518  jz      loc_18000861B
0x18000851e  sub     edx, 2
0x180008521  jz      loc_1800085F5
0x180008527  sub     edx, 2
0x18000852a  jz      loc_1800085C6
0x180008530  sub     edx, 2
0x180008533  jz      short loc_180008597
0x180008535  sub     edx, 2
0x180008538  jz      short loc_18000857A
0x18000853a  sub     edx, 58h ; 'X'
0x18000853d  jz      short loc_18000855B
0x18000853f  cmp     edx, 1
0x180008542  jnz     def_1800086B7; jumptable 00000001800086B7 default case
0x180008548  mov     rax, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x18000854f  and     word ptr [rax+64h], 0Fh
0x180008554  shl     r8w, 4
0x180008559  jmp     short loc_180008570
0x18000855b  mov     rax, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x180008562  mov     ecx, 0F0h
0x180008567  and     [rax+64h], cx
0x18000856b  and     r8w, 0Fh
0x180008570  or      [rax+64h], r8w
0x180008575  jmp     loc_1800086E2
0x18000857a  mov     rcx, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x180008581  lea     eax, ds:0[r8*4]
0x180008589  xor     eax, [rcx+60h]
0x18000858c  and     eax, 4
0x18000858f  xor     [rcx+60h], eax
0x180008592  jmp     loc_1800086E2
0x180008597  test    r8d, r8d
0x18000859a  jns     short loc_1800085AA
0x18000859c  mov     eax, 0FFFF8000h
0x1800085a1  cmp     r8d, eax
0x1800085a4  cmovle  r8d, eax
0x1800085a8  jmp     short loc_1800085B6
0x1800085aa  mov     eax, 7FFFh
0x1800085af  cmp     r8d, eax
0x1800085b2  cmovge  r8d, eax
0x1800085b6  mov     rax, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x1800085bd  mov     [rax+0Ch], r8d
0x1800085c1  jmp     loc_1800086E2
0x1800085c6  test    r8d, r8d
0x1800085c9  jns     short loc_1800085D9
0x1800085cb  mov     eax, 0FFFF8000h
0x1800085d0  cmp     r8d, eax
0x1800085d3  cmovle  r8d, eax
0x1800085d7  jmp     short loc_1800085E5
0x1800085d9  mov     eax, 7FFFh
0x1800085de  cmp     r8d, eax
0x1800085e1  cmovge  r8d, eax
0x1800085e5  mov     rax, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x1800085ec  mov     [rax+8], r8d
0x1800085f0  jmp     loc_1800086E2
0x1800085f5  mov     rcx, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x1800085fc  movsx   eax, word ptr [rcx+2]
0x180008600  mov     [rcx+6], r8w
0x180008605  cmp     eax, r8d
0x180008608  jge     loc_1800086E2
0x18000860e  mov     [rcx+2], r8w
0x180008613  mov     edx, r11d
0x180008616  jmp     loc_1800084F9
0x18000861b  cmp     cs:?g_fForceV2@@3HA, 0; int g_fForceV2
0x180008622  mov     rcx, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x180008629  mov     [rcx+4], r8w
0x18000862e  jz      short loc_180008639
0x180008630  cmp     dword ptr [rcx+0D8h], 0
0x180008637  jnz     short loc_180008645
0x180008639  movsx   eax, word ptr [rcx]
0x18000863c  cmp     eax, r8d
0x18000863f  jge     loc_1800086E2
0x180008645  mov     [rcx], r8w
0x180008649  mov     edx, r10d
0x18000864c  jmp     loc_1800084F9
0x180008651  mov     rcx, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x180008658  movsx   eax, word ptr [rcx+6]
0x18000865c  mov     [rcx+2], r8w
0x180008661  cmp     eax, r8d
0x180008664  jle     short loc_1800086E2
0x180008666  mov     [rcx+6], r8w
0x18000866b  mov     edx, 133h
0x180008670  jmp     loc_1800084F9
0x180008675  mov     rax, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x18000867c  mov     ecx, 0F0h
0x180008681  and     [rax+66h], cx
0x180008685  and     r8w, 0Fh
0x18000868a  or      [rax+66h], r8w
0x18000868f  jmp     short loc_1800086E2
0x180008691  lea     eax, [rdx-194h]; switch 17 cases
0x180008697  cmp     eax, 10h
0x18000869a  ja      short def_1800086B7; jumptable 00000001800086B7 default case
0x18000869c  lea     r9, __ImageBase
0x1800086a3  movzx   eax, ds:(byte_1800086FC - 180000000h)[r9+rax]
0x1800086ac  mov     ecx, ds:(jpt_1800086B7 - 180000000h)[r9+rax*4]
0x1800086b4  add     rcx, r9
0x1800086b7  jmp     rcx; switch jump
0x1800086bd  mov     rax, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; jumptable 00000001800086B7 case 404
0x1800086c4  and     word ptr [rax+66h], 0Fh
0x1800086c9  shl     r8w, 4
0x1800086ce  jmp     short loc_18000868A
0x1800086d0  mov     rcx, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; jumptable 00000001800086B7 cases 405-420
0x1800086d7  add     edx, 0FFFFFE6Bh
0x1800086dd  mov     [rcx+rdx*4+70h], r8d
0x1800086e2  mov     eax, 1
0x1800086e7  jmp     short loc_1800086EB
0x1800086e9  xor     eax, eax; jumptable 00000001800086B7 default case
0x1800086eb  add     rsp, 28h
0x1800086ef  retn
```
