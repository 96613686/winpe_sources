# GdiDrawStream

- ea: `0x18004ac60`
- end: `0x18004b1b3`
- name: `GdiDrawStream`
- size: `1363`
- prototype: `__int64 __fastcall(HDC hdc)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1800200a0`
- `0x18002a660`
- `0x180035af0`
- `0x180036560`
- `0x180047380`
- `0x18004ac60`
- `0x180073fe0`
- `0x18007f800`
- `0x180080604`

## import_xrefs

- `GDI32!DeleteDC` at `0x18004b185`
- `GDI32!DeleteDC` at `0x18004b185`
- `GDI32!CreateRectRgn` at `0x18004b0a6`
- `GDI32!CreateRectRgn` at `0x18004b0a6`
- `GDI32!IntersectClipRect` at `0x18004b10d`
- `GDI32!IntersectClipRect` at `0x18004b10d`
- `GDI32!SelectClipRgn` at `0x18004b0e3`
- `GDI32!SelectClipRgn` at `0x18004b14e`
- `GDI32!SelectClipRgn` at `0x18004b0e3`
- `GDI32!SelectClipRgn` at `0x18004b14e`
- `GDI32!SelectObject` at `0x18004af10`
- `GDI32!SelectObject` at `0x18004af10`
- `GDI32!DeleteObject` at `0x18004aeb2`
- `GDI32!DeleteObject` at `0x18004b16d`
- `GDI32!DeleteObject` at `0x18004b199`
- `GDI32!DeleteObject` at `0x18004aeb2`
- `GDI32!DeleteObject` at `0x18004b16d`
- `GDI32!DeleteObject` at `0x18004b199`
- `win32u!NtGdiDrawStream` at `0x18004acaf`
- `win32u!NtGdiDrawStream` at `0x18004af88`
- `win32u!NtGdiDrawStream` at `0x18004acaf`
- `win32u!NtGdiDrawStream` at `0x18004af88`

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
0x18004ac60  mov     [rsp-8+arg_18], rbx
0x18004ac65  push    rbp
0x18004ac66  push    rsi
0x18004ac67  push    rdi
0x18004ac68  push    r12
0x18004ac6a  push    r13
0x18004ac6c  push    r14
0x18004ac6e  push    r15
0x18004ac70  lea     rbp, [rsp-50h]
0x18004ac75  sub     rsp, 150h
0x18004ac7c  mov     rax, cs:__security_cookie
0x18004ac83  xor     rax, rsp
0x18004ac86  mov     [rbp+80h+var_40], rax
0x18004ac8a  mov     eax, ecx
0x18004ac8c  mov     r15d, edx
0x18004ac8f  and     eax, 7F0000h
0x18004ac94  mov     rsi, rcx
0x18004ac97  cmp     eax, 10000h
0x18004ac9c  jnz     short loc_18004ACE3
0x18004ac9e  mov     rax, gs:30h
0x18004aca7  xor     ebx, ebx
0x18004aca9  mov     [rax+808h], ebx
0x18004acaf  call    cs:__imp_NtGdiDrawStream
0x18004acb6  nop     dword ptr [rax+rax+00h]
0x18004acbb  mov     rcx, [rbp+80h+var_40]
0x18004acbf  xor     rcx, rsp; StackCookie
0x18004acc2  call    __security_check_cookie
0x18004acc7  mov     rbx, [rsp+180h+arg_18]
0x18004accf  add     rsp, 150h
0x18004acd6  pop     r15
0x18004acd8  pop     r14
0x18004acda  pop     r13
0x18004acdc  pop     r12
0x18004acde  pop     rdi
0x18004acdf  pop     rsi
0x18004ace0  pop     rbp
0x18004ace1  retn
0x18004ace3  cmp     r15d, 4
0x18004ace7  jb      loc_18004B1AC
0x18004aced  cmp     dword ptr [r8], 44727753h
0x18004acf4  jnz     loc_18004B1AC
0x18004acfa  xor     ebx, ebx
0x18004acfc  lea     rdi, [r8+4]
0x18004ad00  or      edx, 0FFFFFFFFh
0x18004ad03  mov     [rbp+80h+var_E8], rbx
0x18004ad07  mov     r12d, ebx
0x18004ad0a  mov     [rbp+80h+ho], rbx
0x18004ad0e  mov     [rbp+80h+hdc], rbx
0x18004ad12  add     r15d, 0FFFFFFFCh
0x18004ad16  mov     [rsp+180h+var_114], edx
0x18004ad1a  cmp     r15d, 4
0x18004ad1e  jb      loc_18004B130
0x18004ad24  mov     ecx, [rdi]
0x18004ad26  test    ecx, ecx
0x18004ad28  jz      loc_18004B067
0x18004ad2e  sub     ecx, 1
0x18004ad31  jz      loc_18004B04A
0x18004ad37  cmp     ecx, 8
0x18004ad3a  jnz     loc_18004B137
0x18004ad40  mov     eax, [rdi+14h]
0x18004ad43  xorps   xmm0, xmm0
0x18004ad46  mov     ecx, [rdi+0Ch]
0x18004ad49  xor     edx, edx; Val
0x18004ad4b  mov     r14d, [rdi+1Ch]
0x18004ad4f  mov     r13d, [rdi+10h]
0x18004ad53  mov     [rbp+80h+var_F0], eax
0x18004ad56  mov     eax, [rdi+20h]
0x18004ad59  mov     [rbp+80h+var_EC], eax
0x18004ad5c  mov     eax, [rdi+18h]
0x18004ad5f  mov     [rsp+180h+top], eax
0x18004ad63  mov     eax, [rdi+4]
0x18004ad66  mov     [rsp+180h+xoriginDest], eax
0x18004ad6a  mov     eax, [rdi+8]
0x18004ad6d  mov     [rsp+180h+bottom], eax
0x18004ad71  mov     [rsp+180h+yoriginDest], eax
0x18004ad75  xor     eax, eax
0x18004ad77  mov     [rsp+180h+right], ecx
0x18004ad7b  lea     rcx, [rbp+80h+var_A0]; void *
0x18004ad7f  movups  xmmword ptr [rbp+80h+var_E0], xmm0
0x18004ad83  mov     [rbp+80h+var_B0], eax
0x18004ad86  lea     r8d, [rax+60h]; Size
0x18004ad8a  movups  xmmword ptr [rbp+80h+var_E0+10h], xmm0
0x18004ad8e  movups  xmmword ptr [rbp+80h+var_E0+20h], xmm0
0x18004ad92  call    memset_0
0x18004ad97  mov     r10d, [rdi+24h]
0x18004ad9b  test    r10d, 0FFFFFF80h
0x18004ada2  jnz     loc_18004B137
0x18004ada8  sub     r14d, [rbp+80h+var_F0]
0x18004adac  js      loc_18004B137
0x18004adb2  mov     ecx, [rbp+80h+var_EC]
0x18004adb5  sub     ecx, [rsp+180h+top]
0x18004adb9  js      loc_18004B137
0x18004adbf  mov     r11d, [rsp+180h+right]
0x18004adc4  mov     edx, 20h ; ' '
0x18004adc9  sub     r11d, [rsp+180h+xoriginDest]
0x18004adce  sub     r13d, [rsp+180h+bottom]
0x18004add3  test    dl, r10b
0x18004add6  jz      short loc_18004ADEB
0x18004add8  cmp     r11d, r14d
0x18004addb  cmovle  r14d, r11d
0x18004addf  cmp     r13d, ecx
0x18004ade2  cmovle  ecx, r13d
0x18004ade6  mov     r13d, ecx
0x18004ade9  jmp     short loc_18004AE59
0x18004adeb  mov     r9d, [rdi+28h]
0x18004adef  test    r9d, r9d
0x18004adf2  js      loc_18004B137
0x18004adf8  mov     eax, [rdi+2Ch]
0x18004adfb  test    eax, eax
0x18004adfd  js      loc_18004B137
0x18004ae03  mov     r8d, [rdi+30h]
0x18004ae07  test    r8d, r8d
0x18004ae0a  js      loc_18004B137
0x18004ae10  mov     edx, [rdi+34h]
0x18004ae13  test    edx, edx
0x18004ae15  js      loc_18004B137
0x18004ae1b  cmp     r9d, r14d
0x18004ae1e  jg      loc_18004B137
0x18004ae24  cmp     eax, r14d
0x18004ae27  jg      loc_18004B137
0x18004ae2d  cmp     r8d, ecx
0x18004ae30  jg      loc_18004B137
0x18004ae36  cmp     edx, ecx
0x18004ae38  jg      loc_18004B137
0x18004ae3e  add     eax, r9d
0x18004ae41  cmp     eax, r14d
0x18004ae44  jg      loc_18004B137
0x18004ae4a  lea     eax, [rdx+r8]
0x18004ae4e  mov     r14d, r11d
0x18004ae51  cmp     eax, ecx
0x18004ae53  jg      loc_18004B137
0x18004ae59  and     r10d, 0Ch
0x18004ae5d  cmp     r10b, 0Ch
0x18004ae61  jz      loc_18004B137
0x18004ae67  mov     rax, [rbp+80h+ho]
0x18004ae6b  mov     dword ptr [rbp+80h+var_E0], 28h ; '('
0x18004ae72  mov     dword ptr [rbp+80h+var_E0+4], r14d
0x18004ae76  mov     dword ptr [rbp+80h+var_E0+8], r13d
0x18004ae7a  mov     dword ptr [rbp+80h+var_E0+0Ch], 200001h
0x18004ae81  mov     qword ptr [rbp+80h+var_E0+10h], 3
0x18004ae89  mov     qword ptr [rbp+80h+var_E0+18h], rbx
0x18004ae8d  mov     qword ptr [rbp+80h+var_E0+20h], 3
0x18004ae95  mov     dword ptr [rbp+80h+var_E0+28h], 0FF0000h
0x18004ae9c  mov     dword ptr [rbp+80h+var_E0+2Ch], 0FF00h
0x18004aea3  mov     [rbp+80h+var_B0], 0FFh
0x18004aeaa  test    rax, rax
0x18004aead  jz      short loc_18004AEBE
0x18004aeaf  mov     rcx, rax; ho
0x18004aeb2  call    cs:__imp_DeleteObject
0x18004aeb9  nop     dword ptr [rax+rax+00h]
0x18004aebe  xor     r9d, r9d; pjBits
0x18004aec1  mov     [rsp+180h+iUsage], ebx; iUsage
0x18004aec5  lea     rax, [rbp+80h+var_E0]
0x18004aec9  mov     rcx, rsi; hdc
0x18004aecc  lea     rdx, [rbp+80h+var_E0]; pbmih
0x18004aed0  mov     [rsp+180h+pbmi], rax; pbmi
0x18004aed5  lea     r8d, [r9+2]; flInit
0x18004aed9  call    CreateDIBitmap
0x18004aede  mov     [rbp+80h+ho], rax
0x18004aee2  test    rax, rax
0x18004aee5  jz      loc_18004B137
0x18004aeeb  mov     rax, [rbp+80h+hdc]
0x18004aeef  test    rax, rax
0x18004aef2  jnz     short loc_18004AF09
0x18004aef4  mov     rcx, rsi; hdc
0x18004aef7  call    CreateCompatibleDC
0x18004aefc  mov     [rbp+80h+hdc], rax
0x18004af00  test    rax, rax
0x18004af03  jz      loc_18004B137
0x18004af09  mov     rdx, [rbp+80h+ho]; h
0x18004af0d  mov     rcx, rax; hdc
0x18004af10  call    cs:__imp_SelectObject
0x18004af17  nop     dword ptr [rax+rax+00h]
0x18004af1c  mov     r9, [rbp+80h+hdc]
0x18004af20  lea     r8, [rbp+80h+var_A0]
0x18004af24  mov     rax, [rbp+80h+var_E8]
0x18004af28  mov     edx, 60h ; '`'
0x18004af2d  mov     [rbp+80h+var_98], r9d
0x18004af31  mov     [rbp+80h+var_80], eax
0x18004af34  mov     [rbp+80h+var_A0], 44727753h
0x18004af3c  mov     [rbp+80h+var_94], rbx
0x18004af40  mov     [rbp+80h+var_8C], r14d
0x18004af44  mov     [rbp+80h+var_88], r13d
0x18004af48  mov     [rbp+80h+var_84], 1
0x18004af4f  mov     [rbp+80h+var_7C], 9
0x18004af57  mov     [rbp+80h+var_74], ebx
0x18004af5a  mov     [rbp+80h+var_70], r14d
0x18004af5e  mov     [rbp+80h+var_6C], r13d
0x18004af62  movups  xmm0, xmmword ptr [rdi+14h]
0x18004af66  movdqu  [rbp+80h+var_68], xmm0
0x18004af6b  mov     ecx, [rdi+24h]
0x18004af6e  mov     [rbp+80h+var_58], ecx
0x18004af71  and     ecx, 0FFFFFFF3h
0x18004af74  movups  xmm0, xmmword ptr [rdi+28h]
0x18004af78  movups  [rbp+80h+var_54], xmm0
0x18004af7c  mov     eax, [rdi+38h]
0x18004af7f  mov     [rbp+80h+var_58], ecx
0x18004af82  mov     rcx, r9
0x18004af85  mov     [rbp+80h+var_44], eax
0x18004af88  call    cs:__imp_NtGdiDrawStream
0x18004af8f  nop     dword ptr [rax+rax+00h]
0x18004af94  test    byte ptr [rdi+24h], 8
0x18004af98  mov     r9d, r14d; cx
0x18004af9b  mov     r8d, [rsp+180h+yoriginDest]; y
0x18004afa0  mov     rcx, rsi; hdc
0x18004afa3  mov     edx, [rsp+180h+xoriginDest]; x
0x18004afa7  jz      short loc_18004AFD7
0x18004afa9  mov     eax, [rdi+38h]
0x18004afac  mov     [rsp+180h+crTransparent], eax; crTransparent
0x18004afb0  mov     rax, [rbp+80h+hdc]
0x18004afb4  mov     [rsp+180h+hSrc], r13d; hSrc
0x18004afb9  mov     [rsp+180h+wSrc], r14d; wSrc
0x18004afbe  mov     [rsp+180h+yoriginSrc], ebx; yoriginSrc
0x18004afc2  mov     [rsp+180h+xoriginSrc], ebx; xoriginSrc
0x18004afc6  mov     qword ptr [rsp+180h+iUsage], rax; hdcSrc
0x18004afcb  mov     dword ptr [rsp+180h+pbmi], r13d; hDest
0x18004afd0  call    GdiTransparentBlt
0x18004afd5  jmp     short loc_18004B037
0x18004afd7  test    byte ptr [rdi+24h], 4
0x18004afdb  jz      short loc_18004B014
0x18004afdd  mov     dword ptr [rsp+180h+ftn.BlendOp], 1FF0000h
0x18004afe5  mov     eax, dword ptr [rsp+180h+ftn.BlendOp]
0x18004afe9  mov     [rsp+180h+crTransparent], eax; ftn
0x18004afed  mov     rax, [rbp+80h+hdc]
0x18004aff1  mov     [rsp+180h+hSrc], r13d; hSrc
0x18004aff6  mov     [rsp+180h+wSrc], r14d; wSrc
0x18004affb  mov     [rsp+180h+yoriginSrc], ebx; yoriginSrc
0x18004afff  mov     [rsp+180h+xoriginSrc], ebx; xoriginSrc
0x18004b003  mov     qword ptr [rsp+180h+iUsage], rax; hdcSrc
0x18004b008  mov     dword ptr [rsp+180h+pbmi], r13d; hDest
0x18004b00d  call    GdiAlphaBlend
0x18004b012  jmp     short loc_18004B037
0x18004b014  mov     rax, [rbp+80h+hdc]
0x18004b018  mov     [rsp+180h+wSrc], 0CC0020h; rop
0x18004b020  mov     [rsp+180h+yoriginSrc], ebx; y1
0x18004b024  mov     [rsp+180h+xoriginSrc], ebx; x1
0x18004b028  mov     qword ptr [rsp+180h+iUsage], rax; hdcSrc
0x18004b02d  mov     dword ptr [rsp+180h+pbmi], r13d; cy
0x18004b032  call    BitBlt
0x18004b037  test    eax, eax
0x18004b039  jz      loc_18004B137
0x18004b03f  mov     r14d, 3Ch ; '<'
0x18004b045  jmp     loc_18004B119
0x18004b04a  cmp     r15d, 8
0x18004b04e  jb      loc_18004B137
0x18004b054  movsxd  rax, dword ptr [rdi+4]
0x18004b058  mov     r14d, 8
0x18004b05e  mov     [rbp+80h+var_E8], rax
0x18004b062  jmp     loc_18004B11D
0x18004b067  cmp     r15d, 18h
0x18004b06b  jb      loc_18004B137
0x18004b071  movsxd  rax, dword ptr [rdi+4]
0x18004b075  cmp     rax, rsi
0x18004b078  jnz     loc_18004B137
0x18004b07e  mov     eax, [rdi+0Ch]
0x18004b081  mov     r13d, [rdi+8]
0x18004b085  mov     [rsp+180h+top], eax
0x18004b089  mov     eax, [rdi+10h]
0x18004b08c  mov     [rsp+180h+right], eax
0x18004b090  mov     eax, [rdi+14h]
0x18004b093  mov     [rsp+180h+bottom], eax
0x18004b097  test    r12, r12
0x18004b09a  jnz     short loc_18004B0D5
0x18004b09c  xor     r9d, r9d; y2
0x18004b09f  xor     r8d, r8d; x2
0x18004b0a2  xor     edx, edx; y1
0x18004b0a4  xor     ecx, ecx; x1
0x18004b0a6  call    cs:__imp_CreateRectRgn
0x18004b0ad  nop     dword ptr [rax+rax+00h]
0x18004b0b2  mov     r12, rax
0x18004b0b5  test    rax, rax
0x18004b0b8  jz      short loc_18004B137
0x18004b0ba  mov     rdx, rax; hrgn
0x18004b0bd  mov     rcx, rsi; hdc
0x18004b0c0  call    GetClipRgn
0x18004b0c5  mov     [rsp+180h+var_114], eax
0x18004b0c9  cmp     eax, 0FFFFFFFFh
0x18004b0cc  jnz     short loc_18004B0EF
0x18004b0ce  mov     edi, ebx
0x18004b0d0  jmp     loc_18004B161
0x18004b0d5  mov     rcx, rsi; hdc
0x18004b0d8  test    edx, edx
0x18004b0da  jz      short loc_18004B0E1
0x18004b0dc  mov     rdx, r12
0x18004b0df  jmp     short loc_18004B0E3
0x18004b0e1  xor     edx, edx; hrgn
0x18004b0e3  call    cs:__imp_SelectClipRgn
0x18004b0ea  nop     dword ptr [rax+rax+00h]
0x18004b0ef  mov     eax, [rsp+180h+bottom]
0x18004b0f3  mov     edx, r13d; left
0x18004b0f6  mov     r9d, [rsp+180h+right]; right
0x18004b0fb  mov     rcx, rsi; hdc
0x18004b0fe  mov     r8d, [rsp+180h+top]; top
0x18004b103  mov     r14d, 18h
0x18004b109  mov     dword ptr [rsp+180h+pbmi], eax; bottom
0x18004b10d  call    cs:__imp_IntersectClipRect
0x18004b114  nop     dword ptr [rax+rax+00h]
0x18004b119  mov     edx, [rsp+180h+var_114]
0x18004b11d  mov     eax, r14d
0x18004b120  shr     rax, 2
  ... truncated ...
```
