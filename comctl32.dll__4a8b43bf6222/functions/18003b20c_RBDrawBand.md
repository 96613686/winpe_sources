# RBDrawBand

- ea: `0x18003b20c`
- end: `0x18003b79b`
- name: `RBDrawBand`
- size: `1423`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18003cfb8`

## callees

- `0x1800115f0`
- `0x180017cac`
- `0x180036e24`
- `0x18003ac04`
- `0x18003b20c`
- `0x180085ba0`
- `0x180089774`
- `0x18008ea60`

## import_xrefs

- `GDI32!SelectObject` at `0x18003b60e`
- `GDI32!SelectObject` at `0x18003b6b3`
- `GDI32!SelectObject` at `0x18003b60e`
- `GDI32!SelectObject` at `0x18003b6b3`
- `GDI32!SetBkMode` at `0x18003b316`
- `GDI32!SetBkMode` at `0x18003b758`
- `GDI32!SetBkMode` at `0x18003b316`
- `GDI32!SetBkMode` at `0x18003b758`
- `GDI32!SetBkColor` at `0x18003b2fc`
- `GDI32!SetBkColor` at `0x18003b76e`
- `GDI32!SetBkColor` at `0x18003b2fc`
- `GDI32!SetBkColor` at `0x18003b76e`
- `GDI32!SetTextColor` at `0x18003b2c8`
- `GDI32!SetTextColor` at `0x18003b763`
- `GDI32!SetTextColor` at `0x18003b2c8`
- `GDI32!SetTextColor` at `0x18003b763`
- `GDI32!TextOutW` at `0x18003b6a7`
- `GDI32!TextOutW` at `0x18003b6a7`
- `KERNEL32!lstrlenW` at `0x18003b671`
- `KERNEL32!lstrlenW` at `0x18003b690`
- `KERNEL32!lstrlenW` at `0x18003b671`
- `KERNEL32!lstrlenW` at `0x18003b690`
- `USER32!SetRect` at `0x18003b48e`
- `USER32!SetRect` at `0x18003b48e`
- `USER32!CopyRect` at `0x18003b6ed`
- `USER32!CopyRect` at `0x18003b6ed`
- `USER32!DrawTextW` at `0x18003b688`
- `USER32!DrawTextW` at `0x18003b688`
- `USER32!OffsetRect` at `0x18003b4c1`
- `USER32!OffsetRect` at `0x18003b4c1`

## pseudocode

```c
COLORREF __fastcall RBDrawBand(__int64 a1, __int64 a2, HDC a3)
{
  COLORREF result; // eax
  COLORREF v7; // edx
  COLORREF v8; // eax
  COLORREF v9; // edx
  COLORREF v10; // edi
  COLORREF v11; // ebx
  unsigned int v12; // r10d
  unsigned int v13; // r11d
  unsigned int v14; // r9d
  int v15; // eax
  unsigned int v16; // edx
  int v17; // r8d
  int v18; // edx
  bool v19; // zf
  char v20; // al
  int v21; // r12d
  int v22; // eax
  int v23; // r13d
  int v24; // ebx
  int v25; // edi
  int v26; // edi
  int v27; // r13d
  LONG top; // edx
  LONG right; // ecx
  int v30; // edi
  int v31; // r12d
  int v32; // ecx
  struct _IMAGELIST *v33; // rax
  int v34; // r13d
  int v35; // edx
  _WORD *v36; // rax
  HGDIOBJ v37; // r12
  LONG v38; // edx
  LONG v39; // ebx
  int v40; // edx
  LONG v41; // ecx
  LONG v42; // ecx
  bool v43; // cc
  const WCHAR *v44; // rbx
  UINT v45; // edi
  int v46; // eax
  int v47; // eax
  LONG left; // ecx
  LONG v49; // ecx
  COLORREF v50; // [rsp+30h] [rbp-D0h]
  COLORREF v51; // [rsp+34h] [rbp-CCh]
  int v52; // [rsp+38h] [rbp-C8h]
  int v53; // [rsp+3Ch] [rbp-C4h]
  int mode; // [rsp+40h] [rbp-C0h]
  char v55; // [rsp+48h] [rbp-B8h]
  int v56; // [rsp+50h] [rbp-B0h]
  __int64 v57; // [rsp+58h] [rbp-A8h]
  IMAGELISTDRAWPARAMS pimldp; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v59[10]; // [rsp+C0h] [rbp-40h] BYREF
  struct tagRECT rc; // [rsp+110h] [rbp+10h] BYREF

  v52 = *(_DWORD *)(a1 + 16) & 0x80;
  if ( !v52 || (*(_DWORD *)(a1 + 16) & 0x4000) != 0 )
  {
    v53 = 1;
    v57 = 116;
  }
  else
  {
    v53 = 0;
    v57 = 112;
  }
  result = (unsigned int)memset(v59, 0, sizeof(v59));
  if ( (*(_BYTE *)a2 & 8) == 0 )
  {
    v7 = *(_DWORD *)(a2 + 4);
    mode = 0;
    if ( v7 == -16777216 )
    {
      v7 = g_clrBtnText;
    }
    else if ( v7 == -1 )
    {
      v7 = *(_DWORD *)(a1 + 164);
      if ( v7 == -16777216 )
        v7 = g_clrBtnText;
    }
    v8 = SetTextColor(a3, v7);
    v9 = *(_DWORD *)(a2 + 8);
    v10 = v8;
    v51 = v8;
    if ( v9 == -16777216 )
    {
      v9 = g_clrBtnFace;
    }
    else if ( v9 == -1 )
    {
      v9 = *(_DWORD *)(a1 + 160);
      if ( v9 == -16777216 )
        v9 = g_clrBtnFace;
    }
    v11 = SetBkColor(a3, v9);
    v50 = v11;
    if ( *(_QWORD *)(a2 + 56) )
      mode = SetBkMode(a3, 1);
    v12 = *(_DWORD *)(a2 + 68);
    v13 = v12 + *(_DWORD *)(a2 + 76);
    v14 = *(_DWORD *)(a2 + 64);
    v15 = *(_DWORD *)a2 & 0x202;
    v16 = *(_DWORD *)(a2 + 40);
    v59[7] = *(unsigned int *)(a2 + 92);
    v59[9] = *(_QWORD *)(a2 + 112);
    v59[4] = a3;
    LODWORD(v59[8]) = 0;
    v59[5] = __PAIR64__(v12, v14);
    HIDWORD(v59[6]) = v13;
    if ( v15 == 512 && *(_DWORD *)(a2 + 88) > v16 )
      v17 = g_cxEdge + 4 * g_cxEdge + 2;
    else
      v17 = 0;
    v18 = v14 - v16 - v17 + *(_DWORD *)(a2 + 84);
    v19 = *(_BYTE *)(a1 + 16) >= 0;
    LODWORD(v59[6]) = v18;
    if ( !v19 )
    {
      v59[5] = __PAIR64__(v14, v12);
      v59[6] = __PAIR64__(v18, v13);
    }
    v20 = CICustomDrawNotify(a1, 65537, v59);
    v55 = v20;
    if ( (v20 & 4) == 0 )
    {
      v21 = g_cxEdge;
      if ( (*(_DWORD *)(a1 + 16) & 0x4080) == 0x4080 )
      {
        if ( (*(_DWORD *)a2 & 0x202) == 0x200 && *(_DWORD *)(a2 + 88) > *(_DWORD *)(a2 + 40) )
          v22 = g_cxEdge + 4 * g_cxEdge + 2;
        else
          v22 = 0;
        v23 = *(_DWORD *)(a2 + 84) - *(_DWORD *)(a2 + 40) - v22;
        v24 = *(_DWORD *)(a2 + 64) + v23 / 2;
      }
      else
      {
        v23 = *(_DWORD *)(a2 + 76);
        v24 = *(_DWORD *)(a2 + 68) + v23 / 2;
      }
      v25 = *(_DWORD *)(a2 + 64);
      if ( (*(_DWORD *)a2 & 0x100) != 0 || *(char *)a2 >= 0 && !(unsigned int)RBCanBandMove(a1, a2) )
      {
        v27 = v52;
      }
      else
      {
        rc = 0;
        v56 = 3 * g_cyBorder;
        v26 = v25 + 2 * g_cxBorder;
        SetRect(&rc, v26, *(_DWORD *)(a2 + 68) + v21, v26 + 3 * g_cyBorder, v23 + *(_DWORD *)(a2 + 68) - v21);
        v27 = v52;
        if ( v52 )
        {
          top = rc.top;
          if ( (*(_DWORD *)(a1 + 16) & 0x4080) == 0x4080 )
          {
            OffsetRect(&rc, rc.top - rc.left, rc.left - rc.top);
            rc.bottom -= g_cyEdge;
            top = rc.left;
          }
          else
          {
            right = rc.right;
            rc.top = rc.left;
            rc.right = rc.bottom;
            rc.bottom = right;
            rc.left = top;
          }
          if ( (*(_DWORD *)(a1 + 16) & 0x4080) == 0x4080 )
            v26 = top;
        }
        CCDrawEdge(a3, &rc, 4, 2063, a1 + 176);
        v25 = v56 + v26;
        v21 = g_cxEdge;
      }
      if ( v27 )
        v21 = g_cyEdge;
      v30 = v25 + 2 * v21;
      v31 = *(_DWORD *)(a2 + 28);
      if ( v31 == -1 )
      {
        v34 = v53;
      }
      else
      {
        memset(&pimldp, 0, sizeof(pimldp));
        v32 = v24 - (*(_DWORD *)(a1 + v57) >> 1);
        pimldp.i = v31;
        v33 = *(struct _IMAGELIST **)(a1 + 104);
        pimldp.cbSize = 88;
        v34 = v53;
        pimldp.himl = v33;
        pimldp.hdcDst = a3;
        if ( v53 )
        {
          pimldp.x = v30;
          pimldp.y = v32;
        }
        else
        {
          pimldp.x = v32;
          pimldp.y = v30;
        }
        pimldp.fStyle = 1;
        pimldp.rgbBk = -16777216;
        pimldp.rgbFg = -16777216;
        ImageList_DrawIndirect(&pimldp);
        if ( v53 )
          v35 = *(_DWORD *)(a1 + 112) + g_cxEdge;
        else
          v35 = *(_DWORD *)(a1 + 116) + g_cyEdge;
        v30 += v35;
      }
      if ( (*(_DWORD *)a2 & 0x400) == 0 )
      {
        v36 = *(_WORD **)(a2 + 16);
        if ( v36 )
        {
          if ( *v36 )
          {
            v37 = SelectObject(a3, *(HGDIOBJ *)(a1 + 120));
            *(_QWORD *)&rc.left = 0;
            if ( v34 )
            {
              v38 = v30;
              v39 = v24 - (*(_DWORD *)(a1 + 128) >> 1) - 1;
            }
            else
            {
              v40 = v24;
              v39 = v30;
              v38 = v40 - (*(_DWORD *)(a2 + 24) >> 1);
            }
            v41 = v38 + *(_DWORD *)(a2 + 24);
            rc.top = v39;
            rc.right = v41;
            v42 = v39 + *(_DWORD *)(a1 + 128);
            rc.left = v38;
            v43 = *(_QWORD *)(a1 + 40) < 5LL;
            v44 = *(const WCHAR **)(a2 + 16);
            rc.bottom = v42;
            if ( v43 )
            {
              v47 = lstrlenW(v44);
              TextOutW(a3, rc.left, rc.top, v44, v47);
            }
            else
            {
              v45 = (*(_WORD *)(a1 + 48) & 2) << 19;
              v46 = lstrlenW(v44);
              DrawTextW(a3, v44, v46, &rc, v45);
            }
            SelectObject(a3, v37);
          }
        }
      }
      if ( (*(_DWORD *)a2 & 0x202) == 0x200
        && *(_DWORD *)(a2 + 88) > *(_DWORD *)(a2 + 40)
        && (*(_BYTE *)(a2 + 120) & 1) != 0 )
      {
        rc = 0;
        CopyRect(&rc, (const RECT *)(a2 + 124));
        if ( *(char *)(a1 + 16) < 0 )
        {
          left = rc.left;
          rc.left = rc.top;
          rc.top = left;
          v49 = rc.right;
          rc.right = rc.bottom;
          rc.bottom = v49;
        }
        DrawChevron(a3);
      }
      v10 = v51;
      v11 = v50;
      v20 = v55;
    }
    if ( (v20 & 0x10) != 0 )
      CICustomDrawNotify(a1, 65538, v59);
    if ( *(_QWORD *)(a2 + 56) )
      SetBkMode(a3, mode);
    SetTextColor(a3, v10);
    return SetBkColor(a3, v11);
  }
  return result;
}

```

## disassembly

```asm
0x18003b20c  mov     [rsp-8+arg_18], rbx
0x18003b211  push    rbp
0x18003b212  push    rsi
0x18003b213  push    rdi
0x18003b214  push    r12
0x18003b216  push    r13
0x18003b218  push    r14
0x18003b21a  push    r15
0x18003b21c  lea     rbp, [rsp-30h]
0x18003b221  sub     rsp, 130h
0x18003b228  mov     rax, cs:__security_cookie
0x18003b22f  xor     rax, rsp
0x18003b232  mov     [rbp+60h+var_40], rax
0x18003b236  mov     eax, [rcx+10h]
0x18003b239  xor     r13d, r13d
0x18003b23c  and     eax, 80h
0x18003b241  mov     r15, r8
0x18003b244  mov     [rsp+160h+var_128], eax
0x18003b248  mov     rsi, rdx
0x18003b24b  mov     r14, rcx
0x18003b24e  jz      short loc_18003B269
0x18003b250  test    dword ptr [rcx+10h], 4000h
0x18003b257  jnz     short loc_18003B269
0x18003b259  mov     [rsp+160h+var_124], r13d
0x18003b25e  mov     [rsp+160h+var_108], 70h ; 'p'
0x18003b267  jmp     short loc_18003B27A
0x18003b269  mov     [rsp+160h+var_124], 1
0x18003b271  mov     [rsp+160h+var_108], 74h ; 't'
0x18003b27a  xor     edx, edx; Val
0x18003b27c  lea     rcx, [rbp+60h+var_A0]; void *
0x18003b280  lea     r8d, [rdx+50h]; Size
0x18003b284  call    memset
0x18003b289  test    byte ptr [rsi], 8
0x18003b28c  jnz     loc_18003B774
0x18003b292  mov     edx, [rsi+4]
0x18003b295  or      ebx, 0FFFFFFFFh
0x18003b298  mov     r12d, 0FF000000h
0x18003b29e  mov     [rsp+160h+mode], r13d
0x18003b2a3  cmp     edx, r12d
0x18003b2a6  jz      short loc_18003B2BF
0x18003b2a8  cmp     edx, ebx
0x18003b2aa  jnz     short loc_18003B2C5
0x18003b2ac  mov     edx, [r14+0A4h]
0x18003b2b3  cmp     edx, r12d
0x18003b2b6  cmovz   edx, cs:g_clrBtnText
0x18003b2bd  jmp     short loc_18003B2C5
0x18003b2bf  mov     edx, cs:g_clrBtnText; color
0x18003b2c5  mov     rcx, r15; hdc
0x18003b2c8  call    cs:__imp_SetTextColor
0x18003b2ce  mov     edx, [rsi+8]
0x18003b2d1  mov     edi, eax
0x18003b2d3  mov     [rsp+160h+var_12C], eax
0x18003b2d7  cmp     edx, r12d
0x18003b2da  jz      short loc_18003B2F3
0x18003b2dc  cmp     edx, ebx
0x18003b2de  jnz     short loc_18003B2F9
0x18003b2e0  mov     edx, [r14+0A0h]
0x18003b2e7  cmp     edx, r12d
0x18003b2ea  cmovz   edx, cs:g_clrBtnFace
0x18003b2f1  jmp     short loc_18003B2F9
0x18003b2f3  mov     edx, cs:g_clrBtnFace; color
0x18003b2f9  mov     rcx, r15; hdc
0x18003b2fc  call    cs:__imp_SetBkColor
0x18003b302  mov     ebx, eax
0x18003b304  mov     [rsp+160h+var_130], eax
0x18003b308  cmp     [rsi+38h], r13
0x18003b30c  jz      short loc_18003B320
0x18003b30e  mov     edx, 1; mode
0x18003b313  mov     rcx, r15; hdc
0x18003b316  call    cs:__imp_SetBkMode
0x18003b31c  mov     [rsp+160h+mode], eax
0x18003b320  mov     ecx, [rsi+5Ch]
0x18003b323  mov     r10d, [rsi+44h]
0x18003b327  mov     r11d, [rsi+4Ch]
0x18003b32b  mov     eax, [rsi]
0x18003b32d  add     r11d, r10d
0x18003b330  mov     r9d, [rsi+40h]
0x18003b334  and     eax, 202h
0x18003b339  mov     edx, [rsi+28h]
0x18003b33c  mov     [rbp+60h+var_68], rcx
0x18003b340  mov     rcx, [rsi+70h]
0x18003b344  mov     [rbp+60h+var_58], rcx
0x18003b348  mov     [rbp+60h+var_80], r15
0x18003b34c  mov     [rbp+60h+var_60], r13d
0x18003b350  mov     [rbp+60h+var_74], r10d
0x18003b354  mov     [rbp+60h+var_78], r9d
0x18003b358  mov     [rbp+60h+var_6C], r11d
0x18003b35c  cmp     eax, 200h
0x18003b361  jnz     short loc_18003B37B
0x18003b363  cmp     [rsi+58h], edx
0x18003b366  jbe     short loc_18003B37B
0x18003b368  mov     eax, cs:g_cxEdge
0x18003b36e  lea     r8d, ds:2[rax*4]
0x18003b376  add     r8d, eax
0x18003b379  jmp     short loc_18003B37E
0x18003b37b  mov     r8d, r13d
0x18003b37e  mov     ecx, r9d
0x18003b381  sub     ecx, edx
0x18003b383  mov     edx, [rsi+54h]
0x18003b386  sub     ecx, r8d
0x18003b389  add     edx, ecx
0x18003b38b  test    byte ptr [r14+10h], 80h
0x18003b390  mov     [rbp+60h+var_70], edx
0x18003b393  jz      short loc_18003B3A4
0x18003b395  mov     [rbp+60h+var_78], r10d
0x18003b399  mov     [rbp+60h+var_74], r9d
0x18003b39d  mov     [rbp+60h+var_70], r11d
0x18003b3a1  mov     [rbp+60h+var_6C], edx
0x18003b3a4  lea     r8, [rbp+60h+var_A0]
0x18003b3a8  mov     edx, 10001h
0x18003b3ad  mov     rcx, r14
0x18003b3b0  call    CICustomDrawNotify
0x18003b3b5  mov     eax, eax
0x18003b3b7  mov     [rsp+160h+var_118], rax
0x18003b3bc  test    al, 4
0x18003b3be  jnz     loc_18003B736
0x18003b3c4  mov     eax, [r14+10h]
0x18003b3c8  mov     ecx, 4080h
0x18003b3cd  mov     r12d, cs:g_cxEdge
0x18003b3d4  and     eax, ecx
0x18003b3d6  cmp     eax, ecx
0x18003b3d8  jnz     short loc_18003B41A
0x18003b3da  mov     eax, [rsi]
0x18003b3dc  and     eax, 202h
0x18003b3e1  cmp     eax, 200h
0x18003b3e6  jnz     short loc_18003B3FD
0x18003b3e8  mov     eax, [rsi+28h]
0x18003b3eb  cmp     [rsi+58h], eax
0x18003b3ee  jbe     short loc_18003B3FD
0x18003b3f0  lea     eax, ds:2[r12*4]
0x18003b3f8  add     eax, r12d
0x18003b3fb  jmp     short loc_18003B400
0x18003b3fd  mov     eax, r13d
0x18003b400  mov     r13d, [rsi+54h]
0x18003b404  sub     r13d, [rsi+28h]
0x18003b408  sub     r13d, eax
0x18003b40b  mov     eax, r13d
0x18003b40e  cdq
0x18003b40f  sub     eax, edx
0x18003b411  sar     eax, 1
0x18003b413  mov     ebx, eax
0x18003b415  add     ebx, [rsi+40h]
0x18003b418  jmp     short loc_18003B42B
0x18003b41a  mov     r13d, [rsi+4Ch]
0x18003b41e  mov     eax, r13d
0x18003b421  cdq
0x18003b422  sub     eax, edx
0x18003b424  sar     eax, 1
0x18003b426  mov     ebx, eax
0x18003b428  add     ebx, [rsi+44h]
0x18003b42b  test    dword ptr [rsi], 100h
0x18003b431  mov     edi, [rsi+40h]
0x18003b434  jnz     loc_18003B528
0x18003b43a  test    byte ptr [rsi], 80h
0x18003b43d  jnz     short loc_18003B452
0x18003b43f  mov     rdx, rsi
0x18003b442  mov     rcx, r14
0x18003b445  call    RBCanBandMove
0x18003b44a  test    eax, eax
0x18003b44c  jz      loc_18003B528
0x18003b452  mov     eax, cs:g_cyBorder
0x18003b458  xorps   xmm0, xmm0
0x18003b45b  movups  xmmword ptr [rbp+60h+rc.left], xmm0
0x18003b45f  lea     r8d, [rax+rax*2]
0x18003b463  mov     eax, cs:g_cxBorder
0x18003b469  mov     [rsp+160h+var_110], r8d
0x18003b46e  lea     edx, [rdi+rax*2]; xLeft
0x18003b471  mov     eax, [rsi+44h]
0x18003b474  mov     ecx, eax
0x18003b476  lea     r9d, [rdx+r8]; xRight
0x18003b47a  sub     ecx, r12d
0x18003b47d  mov     edi, edx
0x18003b47f  add     ecx, r13d
0x18003b482  mov     [rsp+160h+yBottom], ecx; yBottom
0x18003b486  lea     r8d, [rax+r12]; yTop
0x18003b48a  lea     rcx, [rbp+60h+rc]; lprc
0x18003b48e  call    cs:__imp_SetRect
0x18003b494  mov     r13d, [rsp+160h+var_128]
0x18003b499  test    r13d, r13d
0x18003b49c  jz      short loc_18003B4F7
0x18003b49e  mov     eax, [r14+10h]
0x18003b4a2  mov     r12d, 4080h
0x18003b4a8  mov     edx, [rbp+60h+rc.top]
0x18003b4ab  and     eax, r12d
0x18003b4ae  cmp     eax, r12d
0x18003b4b1  jnz     short loc_18003B4D5
0x18003b4b3  mov     r8d, [rbp+60h+rc.left]
0x18003b4b7  lea     rcx, [rbp+60h+rc]; lprc
0x18003b4bb  sub     r8d, edx; dy
0x18003b4be  sub     edx, [rbp+60h+rc.left]; dx
0x18003b4c1  call    cs:__imp_OffsetRect
0x18003b4c7  mov     eax, cs:g_cyEdge
0x18003b4cd  sub     [rbp+60h+rc.bottom], eax
0x18003b4d0  mov     edx, [rbp+60h+rc.left]
0x18003b4d3  jmp     short loc_18003B4EA
0x18003b4d5  mov     eax, [rbp+60h+rc.left]
0x18003b4d8  mov     ecx, [rbp+60h+rc.right]
0x18003b4db  mov     [rbp+60h+rc.top], eax
0x18003b4de  mov     eax, [rbp+60h+rc.bottom]
0x18003b4e1  mov     [rbp+60h+rc.right], eax
0x18003b4e4  mov     [rbp+60h+rc.bottom], ecx
0x18003b4e7  mov     [rbp+60h+rc.left], edx
0x18003b4ea  mov     eax, [r14+10h]
0x18003b4ee  and     eax, r12d
0x18003b4f1  cmp     eax, r12d
0x18003b4f4  cmovz   edi, edx
0x18003b4f7  lea     rax, [r14+0B0h]
0x18003b4fe  mov     r9d, 80Fh
0x18003b504  mov     r8d, 4
0x18003b50a  mov     qword ptr [rsp+160h+yBottom], rax; __int64
0x18003b50f  lea     rdx, [rbp+60h+rc]; lprcDst
0x18003b513  mov     rcx, r15; hdc
0x18003b516  call    CCDrawEdge
0x18003b51b  add     edi, [rsp+160h+var_110]
0x18003b51f  mov     r12d, cs:g_cxEdge
0x18003b526  jmp     short loc_18003B52D
0x18003b528  mov     r13d, [rsp+160h+var_128]
0x18003b52d  test    r13d, r13d
0x18003b530  cmovnz  r12d, cs:g_cyEdge
0x18003b538  lea     edi, [rdi+r12*2]
0x18003b53c  mov     r12d, [rsi+1Ch]
0x18003b540  cmp     r12d, 0FFFFFFFFh
0x18003b544  jz      loc_18003B5DC
0x18003b54a  mov     r13d, 58h ; 'X'
0x18003b550  lea     rcx, [rsp+160h+pimldp]; void *
0x18003b555  mov     r8d, r13d; Size
0x18003b558  xor     edx, edx; Val
0x18003b55a  call    memset
0x18003b55f  mov     rcx, [rsp+160h+var_108]
0x18003b564  mov     eax, [r14+rcx]
0x18003b568  mov     ecx, ebx
0x18003b56a  shr     eax, 1
0x18003b56c  sub     ecx, eax
0x18003b56e  mov     [rsp+160h+pimldp.i], r12d
0x18003b573  mov     rax, [r14+68h]
0x18003b577  xor     r12d, r12d
0x18003b57a  mov     [rsp+160h+pimldp.cbSize], r13d
0x18003b57f  mov     r13d, [rsp+160h+var_124]
0x18003b584  mov     [rsp+160h+pimldp.himl], rax
0x18003b589  mov     [rsp+160h+pimldp.hdcDst], r15
0x18003b58e  test    r13d, r13d
0x18003b591  jnz     short loc_18003B59B
0x18003b593  mov     [rbp+60h+pimldp.x], ecx
0x18003b596  mov     [rbp+60h+pimldp.y], edi
0x18003b599  jmp     short loc_18003B5A1
0x18003b59b  mov     [rbp+60h+pimldp.x], edi
0x18003b59e  mov     [rbp+60h+pimldp.y], ecx
0x18003b5a1  mov     eax, 0FF000000h
0x18003b5a6  mov     [rbp+60h+pimldp.fStyle], 1
0x18003b5ad  lea     rcx, [rsp+160h+pimldp]; pimldp
0x18003b5b2  mov     [rbp+60h+pimldp.rgbBk], eax
0x18003b5b5  mov     [rbp+60h+pimldp.rgbFg], eax
0x18003b5b8  call    ImageList_DrawIndirect
0x18003b5bd  test    r13d, r13d
0x18003b5c0  jz      short loc_18003B5CE
0x18003b5c2  mov     edx, cs:g_cxEdge
0x18003b5c8  add     edx, [r14+70h]
0x18003b5cc  jmp     short loc_18003B5D8
0x18003b5ce  mov     edx, cs:g_cyEdge
0x18003b5d4  add     edx, [r14+74h]
0x18003b5d8  add     edi, edx
0x18003b5da  jmp     short loc_18003B5E4
0x18003b5dc  mov     r13d, [rsp+160h+var_124]
0x18003b5e1  xor     r12d, r12d
0x18003b5e4  test    dword ptr [rsi], 400h
0x18003b5ea  jnz     loc_18003B6B9
0x18003b5f0  mov     rax, [rsi+10h]
0x18003b5f4  test    rax, rax
0x18003b5f7  jz      loc_18003B6B9
0x18003b5fd  cmp     [rax], r12w
0x18003b601  jz      loc_18003B6B9
0x18003b607  mov     rdx, [r14+78h]; h
0x18003b60b  mov     rcx, r15; hdc
0x18003b60e  call    cs:__imp_SelectObject
0x18003b614  mov     r12, rax
0x18003b617  xor     eax, eax
0x18003b619  mov     qword ptr [rbp+60h+rc.left], rax
0x18003b61d  test    r13d, r13d
0x18003b620  jz      short loc_18003B633
0x18003b622  mov     ecx, [r14+80h]
0x18003b629  mov     edx, edi
0x18003b62b  shr     ecx, 1
0x18003b62d  sub     ebx, ecx
0x18003b62f  dec     ebx
0x18003b631  jmp     short loc_18003B63E
0x18003b633  mov     eax, [rsi+18h]
0x18003b636  mov     edx, ebx
0x18003b638  shr     eax, 1
0x18003b63a  mov     ebx, edi
0x18003b63c  sub     edx, eax
0x18003b63e  mov     ecx, [rsi+18h]
0x18003b641  add     ecx, edx
0x18003b643  mov     [rbp+60h+rc.top], ebx
0x18003b646  mov     [rbp+60h+rc.right], ecx
0x18003b649  mov     ecx, [r14+80h]
0x18003b650  add     ecx, ebx
0x18003b652  mov     [rbp+60h+rc.left], edx
0x18003b655  cmp     qword ptr [r14+28h], 5
0x18003b65a  mov     rbx, [rsi+10h]
0x18003b65e  mov     [rbp+60h+rc.bottom], ecx
  ... truncated ...
```
