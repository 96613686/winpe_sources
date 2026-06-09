# GdiDrawStream

- ea: `0x1800400d0`
- end: `0x1800405dd`
- name: `GdiDrawStream`
- size: `1293`
- prototype: `__int64 __fastcall(HDC hdc)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18001d880`
- `0x18001ec70`
- `0x18001fe20`
- `0x1800218b0`
- `0x18003ba90`
- `0x1800400d0`
- `0x18006f310`
- `0x18007ac50`
- `0x18007ba24`

## import_xrefs

- `GDI32!DeleteDC` at `0x1800405bb`
- `GDI32!DeleteDC` at `0x1800405bb`
- `GDI32!CreateRectRgn` at `0x1800404fd`
- `GDI32!CreateRectRgn` at `0x1800404fd`
- `GDI32!IntersectClipRect` at `0x180040555`
- `GDI32!IntersectClipRect` at `0x180040555`
- `GDI32!SelectClipRgn` at `0x180040531`
- `GDI32!SelectClipRgn` at `0x180040590`
- `GDI32!SelectClipRgn` at `0x180040531`
- `GDI32!SelectClipRgn` at `0x180040590`
- `GDI32!SelectObject` at `0x180040373`
- `GDI32!SelectObject` at `0x180040373`
- `GDI32!DeleteObject` at `0x18004031b`
- `GDI32!DeleteObject` at `0x1800405a9`
- `GDI32!DeleteObject` at `0x1800405c9`
- `GDI32!DeleteObject` at `0x18004031b`
- `GDI32!DeleteObject` at `0x1800405a9`
- `GDI32!DeleteObject` at `0x1800405c9`
- `win32u!NtGdiDrawStream` at `0x18004011f`
- `win32u!NtGdiDrawStream` at `0x1800403e5`
- `win32u!NtGdiDrawStream` at `0x18004011f`
- `win32u!NtGdiDrawStream` at `0x1800403e5`

## pseudocode

```c
__int64 __fastcall GdiDrawStream(HDC hdc, __int64 a2, _DWORD *a3)
{
  int v3; // r15d
  _DWORD *v6; // rdi
  int v7; // edx
  HRGN v8; // r12
  unsigned int v9; // r15d
  int v10; // r14d
  int v11; // r13d
  int v12; // r10d
  int wSrc; // r14d
  int v14; // ecx
  int hSrc; // r13d
  int v16; // r9d
  int v17; // eax
  int v18; // r8d
  int v19; // edx
  HDC CompatibleDC; // rax
  int v21; // eax
  BOOL v22; // eax
  unsigned int v23; // r14d
  int v24; // r13d
  HRGN RectRgn; // rax
  unsigned int v26; // edi
  HRGN v27; // rdx
  HRGN v28; // rdx
  int xoriginDest; // [rsp+68h] [rbp-98h]
  int ClipRgn; // [rsp+6Ch] [rbp-94h]
  int top; // [rsp+74h] [rbp-8Ch]
  int topa; // [rsp+74h] [rbp-8Ch]
  int right; // [rsp+78h] [rbp-88h]
  int righta; // [rsp+78h] [rbp-88h]
  int bottom; // [rsp+7Ch] [rbp-84h]
  int bottoma; // [rsp+7Ch] [rbp-84h]
  HDC hdca; // [rsp+80h] [rbp-80h]
  HBITMAP ho; // [rsp+88h] [rbp-78h]
  int v39; // [rsp+90h] [rbp-70h]
  int v40; // [rsp+94h] [rbp-6Ch]
  int v41; // [rsp+98h] [rbp-68h]
  _BYTE pbmi[48]; // [rsp+A0h] [rbp-60h] BYREF
  int v43; // [rsp+D0h] [rbp-30h]
  __int64 v44; // [rsp+E0h] [rbp-20h] BYREF
  int v45; // [rsp+E8h] [rbp-18h]
  __int64 v46; // [rsp+ECh] [rbp-14h]
  int v47; // [rsp+F4h] [rbp-Ch]
  int v48; // [rsp+F8h] [rbp-8h]
  int v49; // [rsp+FCh] [rbp-4h]
  int v50; // [rsp+100h] [rbp+0h]
  __int64 v51; // [rsp+104h] [rbp+4h]
  int v52; // [rsp+10Ch] [rbp+Ch]
  int v53; // [rsp+110h] [rbp+10h]
  int v54; // [rsp+114h] [rbp+14h]
  __int128 v55; // [rsp+118h] [rbp+18h]
  int v56; // [rsp+128h] [rbp+28h]
  __int128 v57; // [rsp+12Ch] [rbp+2Ch]
  int v58; // [rsp+13Ch] [rbp+3Ch]

  v3 = a2;
  if ( ((unsigned int)hdc & 0x7F0000) == 0x10000 )
  {
    LODWORD(NtCurrentTeb()->Win32ClientInfo[1]) = 0;
    return NtGdiDrawStream(hdc, a2, a3);
  }
  if ( (unsigned int)a2 < 4 || *a3 != 1148352339 )
    return 0;
  v6 = a3 + 1;
  v7 = -1;
  v41 = 0;
  v8 = 0;
  ho = 0;
  hdca = 0;
  v9 = v3 - 4;
  ClipRgn = -1;
  while ( 1 )
  {
    if ( v9 < 4 )
    {
      v26 = 1;
      goto LABEL_59;
    }
    if ( !*v6 )
    {
      if ( v9 < 0x18 || (HDC)(int)v6[1] != hdc )
        goto LABEL_58;
      v24 = v6[2];
      topa = v6[3];
      righta = v6[4];
      bottoma = v6[5];
      if ( v8 )
      {
        if ( v7 )
          v27 = v8;
        else
          v27 = 0;
        SelectClipRgn(hdc, v27);
      }
      else
      {
        RectRgn = CreateRectRgn(0, 0, 0, 0);
        v8 = RectRgn;
        if ( !RectRgn )
          goto LABEL_58;
        ClipRgn = GetClipRgn(hdc, RectRgn);
        if ( ClipRgn == -1 )
        {
          v26 = 0;
          goto LABEL_64;
        }
      }
      v23 = 24;
      IntersectClipRect(hdc, v24, topa, righta, bottoma);
      goto LABEL_55;
    }
    if ( *v6 != 1 )
      break;
    if ( v9 < 8 )
      goto LABEL_58;
    v23 = 8;
    v41 = v6[1];
LABEL_56:
    v9 -= v23;
    v6 += (unsigned __int64)v23 >> 2;
  }
  if ( *v6 == 9 )
  {
    v10 = v6[7];
    v11 = v6[4];
    v39 = v6[5];
    v40 = v6[8];
    top = v6[6];
    xoriginDest = v6[1];
    bottom = v6[2];
    right = v6[3];
    memset(pbmi, 0, sizeof(pbmi));
    v43 = 0;
    memset_0(&v44, 0, 0x60u);
    v12 = v6[9];
    if ( (v12 & 0xFFFFFF80) == 0 )
    {
      wSrc = v10 - v39;
      if ( wSrc >= 0 )
      {
        v14 = v40 - top;
        if ( v40 - top >= 0 )
        {
          hSrc = v11 - bottom;
          if ( (v12 & 0x20) != 0 )
          {
            if ( right - xoriginDest <= wSrc )
              wSrc = right - xoriginDest;
            if ( hSrc <= v14 )
              v14 = hSrc;
            hSrc = v14;
          }
          else
          {
            v16 = v6[10];
            if ( v16 < 0 )
              goto LABEL_58;
            v17 = v6[11];
            if ( v17 < 0 )
              goto LABEL_58;
            v18 = v6[12];
            if ( v18 < 0 )
              goto LABEL_58;
            v19 = v6[13];
            if ( v19 < 0 )
              goto LABEL_58;
            if ( v16 > wSrc )
              goto LABEL_58;
            if ( v17 > wSrc )
              goto LABEL_58;
            if ( v18 > v14 )
              goto LABEL_58;
            if ( v19 > v14 )
              goto LABEL_58;
            if ( v16 + v17 > wSrc )
              goto LABEL_58;
            wSrc = right - xoriginDest;
            if ( v19 + v18 > v14 )
              goto LABEL_58;
          }
          if ( (v12 & 0xC) != 0xC )
          {
            *(_DWORD *)pbmi = 40;
            *(_QWORD *)&pbmi[4] = __PAIR64__(hSrc, wSrc);
            *(_DWORD *)&pbmi[12] = 2097153;
            *(_OWORD *)&pbmi[16] = 3u;
            *(_QWORD *)&pbmi[32] = 3;
            *(_QWORD *)&pbmi[40] = 0xFF0000FF0000LL;
            v43 = 255;
            if ( ho )
              DeleteObject(ho);
            ho = CreateDIBitmap(hdc, (const BITMAPINFOHEADER *)pbmi, 2u, 0, (const BITMAPINFO *)pbmi, 0);
            if ( ho )
            {
              CompatibleDC = hdca;
              if ( hdca || (CompatibleDC = CreateCompatibleDC(hdc), (hdca = CompatibleDC) != 0) )
              {
                SelectObject(CompatibleDC, ho);
                v45 = (int)hdca;
                v50 = v41;
                v44 = 1148352339;
                v46 = 0;
                v47 = wSrc;
                v48 = hSrc;
                v49 = 1;
                v51 = 9;
                v52 = 0;
                v53 = wSrc;
                v54 = hSrc;
                v55 = *(_OWORD *)(v6 + 5);
                v56 = v6[9];
                v57 = *(_OWORD *)(v6 + 10);
                v21 = v6[14];
                v56 &= 0xFFFFFFF3;
                v58 = v21;
                NtGdiDrawStream(hdca, 96, &v44);
                if ( (v6[9] & 8) != 0 )
                  v22 = GdiTransparentBlt(hdc, xoriginDest, bottom, wSrc, hSrc, hdca, 0, 0, wSrc, hSrc, v6[14]);
                else
                  v22 = (v6[9] & 4) != 0
                      ? GdiAlphaBlend(
                          hdc,
                          xoriginDest,
                          bottom,
                          wSrc,
                          hSrc,
                          hdca,
                          0,
                          0,
                          wSrc,
                          hSrc,
                          (BLENDFUNCTION)33488896)
                      : BitBlt(hdc, xoriginDest, bottom, wSrc, hSrc, hdca, 0, 0, 0xCC0020u);
                if ( v22 )
                {
                  v23 = 60;
LABEL_55:
                  v7 = ClipRgn;
                  goto LABEL_56;
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_58:
  v26 = 0;
LABEL_59:
  if ( ClipRgn == 1 )
  {
    v28 = v8;
    goto LABEL_62;
  }
  if ( !ClipRgn )
  {
    v28 = 0;
LABEL_62:
    SelectClipRgn(hdc, v28);
  }
LABEL_64:
  if ( ho )
    DeleteObject(ho);
  if ( hdca )
    DeleteDC(hdca);
  if ( v8 )
    DeleteObject(v8);
  return v26;
}

```

## disassembly

```asm
0x1800400d0  mov     [rsp-8+arg_18], rbx
0x1800400d5  push    rbp
0x1800400d6  push    rsi
0x1800400d7  push    rdi
0x1800400d8  push    r12
0x1800400da  push    r13
0x1800400dc  push    r14
0x1800400de  push    r15
0x1800400e0  lea     rbp, [rsp-50h]
0x1800400e5  sub     rsp, 150h
0x1800400ec  mov     rax, cs:__security_cookie
0x1800400f3  xor     rax, rsp
0x1800400f6  mov     [rbp+80h+var_40], rax
0x1800400fa  mov     eax, ecx
0x1800400fc  mov     r15d, edx
0x1800400ff  and     eax, 7F0000h
0x180040104  mov     rsi, rcx
0x180040107  cmp     eax, 10000h
0x18004010c  jnz     short loc_18004014C
0x18004010e  mov     rax, gs:30h
0x180040117  xor     ebx, ebx
0x180040119  mov     [rax+808h], ebx
0x18004011f  call    cs:__imp_NtGdiDrawStream
0x180040125  mov     rcx, [rbp+80h+var_40]
0x180040129  xor     rcx, rsp; StackCookie
0x18004012c  call    __security_check_cookie
0x180040131  mov     rbx, [rsp+180h+arg_18]
0x180040139  add     rsp, 150h
0x180040140  pop     r15
0x180040142  pop     r14
0x180040144  pop     r13
0x180040146  pop     r12
0x180040148  pop     rdi
0x180040149  pop     rsi
0x18004014a  pop     rbp
0x18004014b  retn
0x18004014c  cmp     r15d, 4
0x180040150  jb      loc_1800405D6
0x180040156  cmp     dword ptr [r8], 44727753h
0x18004015d  jnz     loc_1800405D6
0x180040163  xor     ebx, ebx
0x180040165  lea     rdi, [r8+4]
0x180040169  or      edx, 0FFFFFFFFh
0x18004016c  mov     [rbp+80h+var_E8], rbx
0x180040170  mov     r12d, ebx
0x180040173  mov     [rbp+80h+ho], rbx
0x180040177  mov     [rbp+80h+hdc], rbx
0x18004017b  add     r15d, 0FFFFFFFCh
0x18004017f  mov     [rsp+180h+var_114], edx
0x180040183  cmp     r15d, 4
0x180040187  jb      loc_180040572
0x18004018d  mov     ecx, [rdi]
0x18004018f  test    ecx, ecx
0x180040191  jz      loc_1800404BE
0x180040197  sub     ecx, 1
0x18004019a  jz      loc_1800404A1
0x1800401a0  cmp     ecx, 8
0x1800401a3  jnz     loc_180040579
0x1800401a9  mov     eax, [rdi+14h]
0x1800401ac  xorps   xmm0, xmm0
0x1800401af  mov     ecx, [rdi+0Ch]
0x1800401b2  xor     edx, edx; Val
0x1800401b4  mov     r14d, [rdi+1Ch]
0x1800401b8  mov     r13d, [rdi+10h]
0x1800401bc  mov     [rbp+80h+var_F0], eax
0x1800401bf  mov     eax, [rdi+20h]
0x1800401c2  mov     [rbp+80h+var_EC], eax
0x1800401c5  mov     eax, [rdi+18h]
0x1800401c8  mov     [rsp+180h+top], eax
0x1800401cc  mov     eax, [rdi+4]
0x1800401cf  mov     [rsp+180h+xoriginDest], eax
0x1800401d3  mov     eax, [rdi+8]
0x1800401d6  mov     [rsp+180h+bottom], eax
0x1800401da  mov     [rsp+180h+yoriginDest], eax
0x1800401de  xor     eax, eax
0x1800401e0  mov     [rsp+180h+right], ecx
0x1800401e4  lea     rcx, [rbp+80h+var_A0]; void *
0x1800401e8  movups  xmmword ptr [rbp+80h+var_E0], xmm0
0x1800401ec  mov     [rbp+80h+var_B0], eax
0x1800401ef  lea     r8d, [rax+60h]; Size
0x1800401f3  movups  xmmword ptr [rbp+80h+var_E0+10h], xmm0
0x1800401f7  movups  xmmword ptr [rbp+80h+var_E0+20h], xmm0
0x1800401fb  call    memset_0
0x180040200  mov     r10d, [rdi+24h]
0x180040204  test    r10d, 0FFFFFF80h
0x18004020b  jnz     loc_180040579
0x180040211  sub     r14d, [rbp+80h+var_F0]
0x180040215  js      loc_180040579
0x18004021b  mov     ecx, [rbp+80h+var_EC]
0x18004021e  sub     ecx, [rsp+180h+top]
0x180040222  js      loc_180040579
0x180040228  mov     r11d, [rsp+180h+right]
0x18004022d  mov     edx, 20h ; ' '
0x180040232  sub     r11d, [rsp+180h+xoriginDest]
0x180040237  sub     r13d, [rsp+180h+bottom]
0x18004023c  test    dl, r10b
0x18004023f  jz      short loc_180040254
0x180040241  cmp     r11d, r14d
0x180040244  cmovle  r14d, r11d
0x180040248  cmp     r13d, ecx
0x18004024b  cmovle  ecx, r13d
0x18004024f  mov     r13d, ecx
0x180040252  jmp     short loc_1800402C2
0x180040254  mov     r9d, [rdi+28h]
0x180040258  test    r9d, r9d
0x18004025b  js      loc_180040579
0x180040261  mov     eax, [rdi+2Ch]
0x180040264  test    eax, eax
0x180040266  js      loc_180040579
0x18004026c  mov     r8d, [rdi+30h]
0x180040270  test    r8d, r8d
0x180040273  js      loc_180040579
0x180040279  mov     edx, [rdi+34h]
0x18004027c  test    edx, edx
0x18004027e  js      loc_180040579
0x180040284  cmp     r9d, r14d
0x180040287  jg      loc_180040579
0x18004028d  cmp     eax, r14d
0x180040290  jg      loc_180040579
0x180040296  cmp     r8d, ecx
0x180040299  jg      loc_180040579
0x18004029f  cmp     edx, ecx
0x1800402a1  jg      loc_180040579
0x1800402a7  add     eax, r9d
0x1800402aa  cmp     eax, r14d
0x1800402ad  jg      loc_180040579
0x1800402b3  lea     eax, [rdx+r8]
0x1800402b7  mov     r14d, r11d
0x1800402ba  cmp     eax, ecx
0x1800402bc  jg      loc_180040579
0x1800402c2  and     r10d, 0Ch
0x1800402c6  cmp     r10b, 0Ch
0x1800402ca  jz      loc_180040579
0x1800402d0  mov     rax, [rbp+80h+ho]
0x1800402d4  mov     dword ptr [rbp+80h+var_E0], 28h ; '('
0x1800402db  mov     dword ptr [rbp+80h+var_E0+4], r14d
0x1800402df  mov     dword ptr [rbp+80h+var_E0+8], r13d
0x1800402e3  mov     dword ptr [rbp+80h+var_E0+0Ch], 200001h
0x1800402ea  mov     qword ptr [rbp+80h+var_E0+10h], 3
0x1800402f2  mov     qword ptr [rbp+80h+var_E0+18h], rbx
0x1800402f6  mov     qword ptr [rbp+80h+var_E0+20h], 3
0x1800402fe  mov     dword ptr [rbp+80h+var_E0+28h], 0FF0000h
0x180040305  mov     dword ptr [rbp+80h+var_E0+2Ch], 0FF00h
0x18004030c  mov     [rbp+80h+var_B0], 0FFh
0x180040313  test    rax, rax
0x180040316  jz      short loc_180040321
0x180040318  mov     rcx, rax; ho
0x18004031b  call    cs:__imp_DeleteObject
0x180040321  xor     r9d, r9d; pjBits
0x180040324  mov     [rsp+180h+iUsage], ebx; iUsage
0x180040328  lea     rax, [rbp+80h+var_E0]
0x18004032c  mov     rcx, rsi; hdc
0x18004032f  lea     rdx, [rbp+80h+var_E0]; pbmih
0x180040333  mov     [rsp+180h+pbmi], rax; pbmi
0x180040338  lea     r8d, [r9+2]; flInit
0x18004033c  call    CreateDIBitmap
0x180040341  mov     [rbp+80h+ho], rax
0x180040345  test    rax, rax
0x180040348  jz      loc_180040579
0x18004034e  mov     rax, [rbp+80h+hdc]
0x180040352  test    rax, rax
0x180040355  jnz     short loc_18004036C
0x180040357  mov     rcx, rsi; hdc
0x18004035a  call    CreateCompatibleDC
0x18004035f  mov     [rbp+80h+hdc], rax
0x180040363  test    rax, rax
0x180040366  jz      loc_180040579
0x18004036c  mov     rdx, [rbp+80h+ho]; h
0x180040370  mov     rcx, rax; hdc
0x180040373  call    cs:__imp_SelectObject
0x180040379  mov     r9, [rbp+80h+hdc]
0x18004037d  lea     r8, [rbp+80h+var_A0]
0x180040381  mov     rax, [rbp+80h+var_E8]
0x180040385  mov     edx, 60h ; '`'
0x18004038a  mov     [rbp+80h+var_98], r9d
0x18004038e  mov     [rbp+80h+var_80], eax
0x180040391  mov     [rbp+80h+var_A0], 44727753h
0x180040399  mov     [rbp+80h+var_94], rbx
0x18004039d  mov     [rbp+80h+var_8C], r14d
0x1800403a1  mov     [rbp+80h+var_88], r13d
0x1800403a5  mov     [rbp+80h+var_84], 1
0x1800403ac  mov     [rbp+80h+var_7C], 9
0x1800403b4  mov     [rbp+80h+var_74], ebx
0x1800403b7  mov     [rbp+80h+var_70], r14d
0x1800403bb  mov     [rbp+80h+var_6C], r13d
0x1800403bf  movups  xmm0, xmmword ptr [rdi+14h]
0x1800403c3  movdqu  [rbp+80h+var_68], xmm0
0x1800403c8  mov     ecx, [rdi+24h]
0x1800403cb  mov     [rbp+80h+var_58], ecx
0x1800403ce  and     ecx, 0FFFFFFF3h
0x1800403d1  movups  xmm0, xmmword ptr [rdi+28h]
0x1800403d5  movups  [rbp+80h+var_54], xmm0
0x1800403d9  mov     eax, [rdi+38h]
0x1800403dc  mov     [rbp+80h+var_58], ecx
0x1800403df  mov     rcx, r9
0x1800403e2  mov     [rbp+80h+var_44], eax
0x1800403e5  call    cs:__imp_NtGdiDrawStream
0x1800403eb  test    byte ptr [rdi+24h], 8
0x1800403ef  mov     r9d, r14d; cx
0x1800403f2  mov     r8d, [rsp+180h+yoriginDest]; y
0x1800403f7  mov     rcx, rsi; hdc
0x1800403fa  mov     edx, [rsp+180h+xoriginDest]; x
0x1800403fe  jz      short loc_18004042E
0x180040400  mov     eax, [rdi+38h]
0x180040403  mov     [rsp+180h+crTransparent], eax; crTransparent
0x180040407  mov     rax, [rbp+80h+hdc]
0x18004040b  mov     [rsp+180h+hSrc], r13d; hSrc
0x180040410  mov     [rsp+180h+wSrc], r14d; wSrc
0x180040415  mov     [rsp+180h+yoriginSrc], ebx; yoriginSrc
0x180040419  mov     [rsp+180h+xoriginSrc], ebx; xoriginSrc
0x18004041d  mov     qword ptr [rsp+180h+iUsage], rax; hdcSrc
0x180040422  mov     dword ptr [rsp+180h+pbmi], r13d; hDest
0x180040427  call    GdiTransparentBlt
0x18004042c  jmp     short loc_18004048E
0x18004042e  test    byte ptr [rdi+24h], 4
0x180040432  jz      short loc_18004046B
0x180040434  mov     dword ptr [rsp+180h+ftn.BlendOp], 1FF0000h
0x18004043c  mov     eax, dword ptr [rsp+180h+ftn.BlendOp]
0x180040440  mov     [rsp+180h+crTransparent], eax; ftn
0x180040444  mov     rax, [rbp+80h+hdc]
0x180040448  mov     [rsp+180h+hSrc], r13d; hSrc
0x18004044d  mov     [rsp+180h+wSrc], r14d; wSrc
0x180040452  mov     [rsp+180h+yoriginSrc], ebx; yoriginSrc
0x180040456  mov     [rsp+180h+xoriginSrc], ebx; xoriginSrc
0x18004045a  mov     qword ptr [rsp+180h+iUsage], rax; hdcSrc
0x18004045f  mov     dword ptr [rsp+180h+pbmi], r13d; hDest
0x180040464  call    GdiAlphaBlend
0x180040469  jmp     short loc_18004048E
0x18004046b  mov     rax, [rbp+80h+hdc]
0x18004046f  mov     [rsp+180h+wSrc], 0CC0020h; rop
0x180040477  mov     [rsp+180h+yoriginSrc], ebx; y1
0x18004047b  mov     [rsp+180h+xoriginSrc], ebx; x1
0x18004047f  mov     qword ptr [rsp+180h+iUsage], rax; hdcSrc
0x180040484  mov     dword ptr [rsp+180h+pbmi], r13d; cy
0x180040489  call    BitBlt
0x18004048e  test    eax, eax
0x180040490  jz      loc_180040579
0x180040496  mov     r14d, 3Ch ; '<'
0x18004049c  jmp     loc_18004055B
0x1800404a1  cmp     r15d, 8
0x1800404a5  jb      loc_180040579
0x1800404ab  movsxd  rax, dword ptr [rdi+4]
0x1800404af  mov     r14d, 8
0x1800404b5  mov     [rbp+80h+var_E8], rax
0x1800404b9  jmp     loc_18004055F
0x1800404be  cmp     r15d, 18h
0x1800404c2  jb      loc_180040579
0x1800404c8  movsxd  rax, dword ptr [rdi+4]
0x1800404cc  cmp     rax, rsi
0x1800404cf  jnz     loc_180040579
0x1800404d5  mov     eax, [rdi+0Ch]
0x1800404d8  mov     r13d, [rdi+8]
0x1800404dc  mov     [rsp+180h+top], eax
0x1800404e0  mov     eax, [rdi+10h]
0x1800404e3  mov     [rsp+180h+right], eax
0x1800404e7  mov     eax, [rdi+14h]
0x1800404ea  mov     [rsp+180h+bottom], eax
0x1800404ee  test    r12, r12
0x1800404f1  jnz     short loc_180040523
0x1800404f3  xor     r9d, r9d; y2
0x1800404f6  xor     r8d, r8d; x2
0x1800404f9  xor     edx, edx; y1
0x1800404fb  xor     ecx, ecx; x1
0x1800404fd  call    cs:__imp_CreateRectRgn
0x180040503  mov     r12, rax
0x180040506  test    rax, rax
0x180040509  jz      short loc_180040579
0x18004050b  mov     rdx, rax; hrgn
0x18004050e  mov     rcx, rsi; hdc
0x180040511  call    GetClipRgn
0x180040516  mov     [rsp+180h+var_114], eax
0x18004051a  cmp     eax, 0FFFFFFFFh
0x18004051d  jnz     short loc_180040537
0x18004051f  mov     edi, ebx
0x180040521  jmp     short loc_18004059D
0x180040523  mov     rcx, rsi; hdc
0x180040526  test    edx, edx
0x180040528  jz      short loc_18004052F
0x18004052a  mov     rdx, r12
0x18004052d  jmp     short loc_180040531
0x18004052f  xor     edx, edx; hrgn
0x180040531  call    cs:__imp_SelectClipRgn
0x180040537  mov     eax, [rsp+180h+bottom]
0x18004053b  mov     edx, r13d; left
0x18004053e  mov     r9d, [rsp+180h+right]; right
0x180040543  mov     rcx, rsi; hdc
0x180040546  mov     r8d, [rsp+180h+top]; top
0x18004054b  mov     r14d, 18h
0x180040551  mov     dword ptr [rsp+180h+pbmi], eax; bottom
0x180040555  call    cs:__imp_IntersectClipRect
0x18004055b  mov     edx, [rsp+180h+var_114]
0x18004055f  mov     eax, r14d
0x180040562  shr     rax, 2
0x180040566  sub     r15d, r14d
0x180040569  lea     rdi, [rdi+rax*4]
0x18004056d  jmp     loc_180040183
0x180040572  mov     edi, 1
0x180040577  jmp     short loc_18004057B
0x180040579  mov     edi, ebx
0x18004057b  mov     r8d, [rsp+180h+var_114]
  ... truncated ...
```
