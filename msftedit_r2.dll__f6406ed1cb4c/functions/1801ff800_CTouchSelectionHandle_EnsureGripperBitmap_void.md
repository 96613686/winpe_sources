# CTouchSelectionHandle::EnsureGripperBitmap(void)

- ea: `0x1801ff800`
- end: `0x1801ffb9a`
- name: `?EnsureGripperBitmap@CTouchSelectionHandle@@IEAAXXZ`
- size: `922`
- prototype: `void __fastcall(CTouchSelectionHandle *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180203b78`

## callees

- `0x18013ce80`
- `0x1801ff800`
- `0x1802005e4`
- `0x180202ba4`

## import_xrefs

- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x1801ffb37`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x1801ffb37`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x1801ff8e0`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x1801ff8e0`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801ff90a`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801ffb28`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801ff90a`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801ffb28`
- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x1801ff8af`
- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x1801ff8af`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801ffb4c`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801ffb4c`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!GetDC` at `0x1801ff888`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!GetDC` at `0x1801ff888`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!ReleaseDC` at `0x1801ff8cc`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!ReleaseDC` at `0x1801ff8f8`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!ReleaseDC` at `0x1801ff8cc`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!ReleaseDC` at `0x1801ff8f8`

## pseudocode

```c
void __fastcall CTouchSelectionHandle::EnsureGripperBitmap(CTouchSelectionHandle *this)
{
  LONG v2; // ebx
  HDC DC; // rsi
  HBITMAP v4; // r13
  HDC CompatibleDC; // r12
  HGDIOBJ v6; // rax
  unsigned int v7; // r8d
  int v8; // edx
  int v9; // r14d
  int v10; // eax
  __int64 v11; // rcx
  int v12; // r11d
  unsigned int v13; // r15d
  int v14; // r9d
  int v15; // r14d
  int v16; // r8d
  int i; // r10d
  int v18; // ecx
  __int64 v19; // r12
  int v20; // esi
  int v21; // ecx
  __int64 j; // rsi
  unsigned int v23; // r9d
  void *v24; // rcx
  __int64 v25; // rax
  int v26; // ecx
  unsigned int v27; // [rsp+30h] [rbp-59h] BYREF
  bool v28[4]; // [rsp+34h] [rbp-55h] BYREF
  unsigned int v29; // [rsp+38h] [rbp-51h]
  int v30; // [rsp+3Ch] [rbp-4Dh]
  void *ppvBits; // [rsp+40h] [rbp-49h] BYREF
  int v32; // [rsp+48h] [rbp-41h]
  HDC v33; // [rsp+50h] [rbp-39h]
  HBITMAP v34; // [rsp+58h] [rbp-31h]
  HGDIOBJ h; // [rsp+60h] [rbp-29h]
  BITMAPINFO pbmi; // [rsp+68h] [rbp-21h] BYREF

  if ( !*((_QWORD *)this + 10) || *((_BYTE *)this + 100) )
  {
    v2 = *(_DWORD *)(*((_QWORD *)this + 16) + 8LL);
    memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
    pbmi.bmiHeader.biSize = 40;
    pbmi.bmiHeader.biWidth = v2;
    pbmi.bmiHeader.biHeight = v2;
    *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
    ppvBits = 0;
    v27 = 0;
    *(_DWORD *)v28 = 0;
    CTouchSelectionHandle::GetGripperColorsFromTextHost(this, &v27, (unsigned int *)v28);
    DC = GetDC(0);
    v34 = CreateDIBSection(DC, &pbmi, 0, &ppvBits, 0, 0);
    v4 = v34;
    if ( !v34 )
    {
      ReleaseDC(0, DC);
      return;
    }
    CompatibleDC = CreateCompatibleDC(DC);
    v33 = CompatibleDC;
    ReleaseDC(0, DC);
    v6 = SelectObject(CompatibleDC, v4);
    v7 = *(_DWORD *)v28;
    h = v6;
    v8 = 0;
    v9 = v2 * v2;
    v32 = v2 * v2;
    v30 = *(_WORD *)v28 & 0xFF00 | (v28[0] << 16) | v28[2];
    v10 = v30 ^ 0xFFFFFF;
    v29 = v30 ^ 0xFFFFFF;
    if ( v2 * v2 > 0 )
    {
      do
      {
        v11 = (unsigned int)v8++;
        *((_DWORD *)ppvBits + v11) = v10 | 0x1000000;
      }
      while ( v8 < v9 );
      v7 = *(_DWORD *)v28;
    }
    CTouchSelectionHandle::RenderHandle(this, CompatibleDC, v7, v27, v7);
    v12 = 0;
    v13 = v27 & 0xFF00 | ((unsigned __int8)v27 << 16) | BYTE2(v27);
    if ( v2 > 0 )
    {
LABEL_9:
      v14 = 0;
      v15 = -1;
      v16 = 0;
      for ( i = 1; ; v16 += i )
      {
        if ( i <= 0 )
        {
          if ( v16 < 0 )
            goto LABEL_25;
        }
        else if ( v16 >= v2 )
        {
          goto LABEL_25;
        }
        v18 = v16 + v12 * v2;
        v19 = v18;
        v20 = *((_DWORD *)ppvBits + v18);
        if ( v20 == v30 || v20 == v13 )
        {
          if ( i != 1 )
          {
            v15 = v16 + v12 * v2;
LABEL_25:
            while ( v14 <= v15 )
              *((_DWORD *)ppvBits + v14++) |= 0xFF000000;
            if ( ++v12 >= v2 )
            {
              v9 = v32;
              CompatibleDC = v33;
              v4 = v34;
              break;
            }
            goto LABEL_9;
          }
          i = -1;
          v16 = v2 - 1;
          v14 = v18;
        }
        else if ( !*((_BYTE *)ppvBits + 4 * v18 + 3) )
        {
          v21 = -((unsigned __int8)v20 + BYTE1(v20) + BYTE2(v20) - BYTE1(v29) - HIWORD(v29) - (unsigned __int8)v29);
          if ( (int)((unsigned __int8)v20 + BYTE1(v20) + BYTE2(v20) - BYTE1(v29) - HIWORD(v29) - (unsigned __int8)v29) > 0 )
            v21 = (unsigned __int8)v20 + BYTE1(v20) + BYTE2(v20) - BYTE1(v29) - HIWORD(v29) - (unsigned __int8)v29;
          *((_DWORD *)ppvBits + v19) = v30
                                     | ((unsigned __int8)(((((unsigned __int64)(1431655766LL * v21) >> 32) & 0x80000000) != 0LL)
                                                        + ((unsigned __int64)(1431655766LL * v21) >> 32)) << 24);
        }
      }
    }
    for ( j = 0; (int)j < v9; j = (unsigned int)(j + 1) )
    {
      v23 = HIBYTE(*((_DWORD *)ppvBits + j));
      *((_DWORD *)ppvBits + j) = (unsigned __int8)(v23 * (unsigned __int8)*((_DWORD *)ppvBits + j) / 0xFF)
                               | ((unsigned __int8)(v23 * (unsigned __int8)BYTE2(*((_DWORD *)ppvBits + j)) / 0xFF) << 16)
                               | ((unsigned __int8)(v23 * BYTE1(*((_DWORD *)ppvBits + j)) / 0xFF) << 8)
                               | _byteswap_ulong(v23);
    }
    SelectObject(CompatibleDC, h);
    DeleteDC(CompatibleDC);
    v24 = (void *)*((_QWORD *)this + 10);
    if ( v24 )
      DeleteObject(v24);
    v25 = *((_QWORD *)this + 16);
    *((_QWORD *)this + 10) = v4;
    *((_BYTE *)this + 100) = 0;
    v26 = *(_DWORD *)(v25 + 4);
    *((_DWORD *)this + 23) = v27;
    *((_DWORD *)this + 24) = *(_DWORD *)v28;
    *((_DWORD *)this + 22) = v26;
  }
}

```

## disassembly

```asm
0x1801ff800  push    rbp
0x1801ff802  push    rbx
0x1801ff803  push    rsi
0x1801ff804  push    rdi
0x1801ff805  push    r12
0x1801ff807  push    r13
0x1801ff809  push    r14
0x1801ff80b  push    r15
0x1801ff80d  lea     rbp, [rsp-1Fh]
0x1801ff812  sub     rsp, 0A8h
0x1801ff819  mov     rax, cs:__security_cookie
0x1801ff820  xor     rax, rsp
0x1801ff823  mov     [rbp+57h+var_48], rax
0x1801ff827  xor     r15d, r15d
0x1801ff82a  mov     rdi, rcx
0x1801ff82d  cmp     [rcx+50h], r15
0x1801ff831  jz      short loc_1801FF83D
0x1801ff833  cmp     [rcx+64h], r15b
0x1801ff837  jz      loc_1801FFB79
0x1801ff83d  mov     rax, [rcx+80h]
0x1801ff844  lea     r8, [rbp+57h+var_AC]; unsigned int *
0x1801ff848  xorps   xmm0, xmm0
0x1801ff84b  lea     rdx, [rbp+57h+var_B0]; unsigned int *
0x1801ff84f  mov     ebx, [rax+8]
0x1801ff852  xor     eax, eax
0x1801ff854  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biWidth], xmm0
0x1801ff858  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biClrImportant], rax
0x1801ff85c  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biSizeImage], xmm0
0x1801ff860  mov     [rbp+57h+pbmi.bmiHeader.biSize], 28h ; '('
0x1801ff867  mov     [rbp+57h+pbmi.bmiHeader.biWidth], ebx
0x1801ff86a  mov     [rbp+57h+pbmi.bmiHeader.biHeight], ebx
0x1801ff86d  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biPlanes], 200001h
0x1801ff875  mov     [rbp+57h+ppvBits], r15
0x1801ff879  mov     [rbp+57h+var_B0], r15d
0x1801ff87d  mov     dword ptr [rbp+57h+var_AC], r15d
0x1801ff881  call    ?GetGripperColorsFromTextHost@CTouchSelectionHandle@@IEBAXAEAK0@Z; CTouchSelectionHandle::GetGripperColorsFromTextHost(ulong &,ulong &)
0x1801ff886  xor     ecx, ecx; hWnd
0x1801ff888  call    cs:__imp_GetDC
0x1801ff88f  nop     dword ptr [rax+rax+00h]
0x1801ff894  mov     [rsp+0E0h+offset], r15d; offset
0x1801ff899  lea     r9, [rbp+57h+ppvBits]; ppvBits
0x1801ff89d  mov     rcx, rax; hdc
0x1801ff8a0  mov     [rsp+0E0h+hSection], r15; hSection
0x1801ff8a5  xor     r8d, r8d; usage
0x1801ff8a8  lea     rdx, [rbp+57h+pbmi]; pbmi
0x1801ff8ac  mov     rsi, rax
0x1801ff8af  call    cs:__imp_CreateDIBSection
0x1801ff8b6  nop     dword ptr [rax+rax+00h]
0x1801ff8bb  mov     [rbp+57h+var_88], rax
0x1801ff8bf  mov     r13, rax
0x1801ff8c2  test    rax, rax
0x1801ff8c5  jnz     short loc_1801FF8DD
0x1801ff8c7  mov     rdx, rsi; hDC
0x1801ff8ca  xor     ecx, ecx; hWnd
0x1801ff8cc  call    cs:__imp_ReleaseDC
0x1801ff8d3  nop     dword ptr [rax+rax+00h]
0x1801ff8d8  jmp     loc_1801FFB79
0x1801ff8dd  mov     rcx, rsi; hdc
0x1801ff8e0  call    cs:__imp_CreateCompatibleDC
0x1801ff8e7  nop     dword ptr [rax+rax+00h]
0x1801ff8ec  mov     rdx, rsi; hDC
0x1801ff8ef  xor     ecx, ecx; hWnd
0x1801ff8f1  mov     r12, rax
0x1801ff8f4  mov     [rbp+57h+var_90], rax
0x1801ff8f8  call    cs:__imp_ReleaseDC
0x1801ff8ff  nop     dword ptr [rax+rax+00h]
0x1801ff904  mov     rdx, r13; h
0x1801ff907  mov     rcx, r12; hdc
0x1801ff90a  call    cs:__imp_SelectObject
0x1801ff911  nop     dword ptr [rax+rax+00h]
0x1801ff916  mov     r8d, dword ptr [rbp+57h+var_AC]
0x1801ff91a  mov     esi, 0FF00h
0x1801ff91f  mov     [rbp+57h+h], rax
0x1801ff923  mov     ecx, r8d
0x1801ff926  shr     ecx, 10h
0x1801ff929  mov     r14d, ebx
0x1801ff92c  movzx   eax, cl
0x1801ff92f  mov     edx, r15d
0x1801ff932  imul    r14d, ebx
0x1801ff936  movzx   ecx, r8b
0x1801ff93a  shl     ecx, 10h
0x1801ff93d  or      eax, ecx
0x1801ff93f  mov     ecx, r8d
0x1801ff942  and     ecx, esi
0x1801ff944  or      eax, ecx
0x1801ff946  mov     [rbp+57h+var_98], r14d
0x1801ff94a  mov     [rbp+57h+var_A4], eax
0x1801ff94d  xor     eax, 0FFFFFFh
0x1801ff952  mov     [rbp+57h+var_A8], eax
0x1801ff955  test    r14d, r14d
0x1801ff958  jle     short loc_1801FF977
0x1801ff95a  mov     r8d, eax
0x1801ff95d  bts     r8d, 18h
0x1801ff962  mov     rax, [rbp+57h+ppvBits]
0x1801ff966  mov     ecx, edx
0x1801ff968  inc     edx
0x1801ff96a  mov     [rax+rcx*4], r8d
0x1801ff96e  cmp     edx, r14d
0x1801ff971  jl      short loc_1801FF962
0x1801ff973  mov     r8d, dword ptr [rbp+57h+var_AC]; bool
0x1801ff977  mov     r9d, [rbp+57h+var_B0]; unsigned int
0x1801ff97b  mov     rdx, r12; HDC
0x1801ff97e  mov     rcx, rdi; this
0x1801ff981  mov     dword ptr [rsp+0E0h+hSection], r8d; unsigned int
0x1801ff986  call    ?RenderHandle@CTouchSelectionHandle@@IEBAXPEAUHDC__@@_NKK@Z; CTouchSelectionHandle::RenderHandle(HDC__ *,bool,ulong,ulong)
0x1801ff98b  mov     ecx, [rbp+57h+var_B0]
0x1801ff98e  xor     r11d, r11d
0x1801ff991  mov     eax, ecx
0x1801ff993  shr     eax, 10h
0x1801ff996  movzx   r15d, al
0x1801ff99a  movzx   eax, cl
0x1801ff99d  and     ecx, esi
0x1801ff99f  shl     eax, 10h
0x1801ff9a2  or      r15d, eax
0x1801ff9a5  or      r15d, ecx
0x1801ff9a8  test    ebx, ebx
0x1801ff9aa  jle     loc_1801FFAA4
0x1801ff9b0  lea     edx, [r11+1]
0x1801ff9b4  xor     r9d, r9d
0x1801ff9b7  or      r14d, 0FFFFFFFFh
0x1801ff9bb  xor     r8d, r8d
0x1801ff9be  mov     r10d, edx
0x1801ff9c1  test    r10d, r10d
0x1801ff9c4  jle     short loc_1801FF9D1
0x1801ff9c6  cmp     r8d, ebx
0x1801ff9c9  jge     loc_1801FFA87
0x1801ff9cf  jmp     short loc_1801FF9DA
0x1801ff9d1  test    r8d, r8d
0x1801ff9d4  js      loc_1801FFA87
0x1801ff9da  mov     r13, [rbp+57h+ppvBits]
0x1801ff9de  mov     ecx, ebx
0x1801ff9e0  imul    ecx, r11d
0x1801ff9e4  add     ecx, r8d
0x1801ff9e7  movsxd  r12, ecx
0x1801ff9ea  mov     esi, [r13+r12*4+0]
0x1801ff9ef  cmp     esi, [rbp+57h+var_A4]
0x1801ff9f2  jz      short loc_1801FFA59
0x1801ff9f4  cmp     esi, r15d
0x1801ff9f7  jz      short loc_1801FFA59
0x1801ff9f9  cmp     byte ptr [r13+r12*4+3], 0
0x1801ff9ff  jnz     short loc_1801FFA69
0x1801ffa01  movzx   ecx, word ptr [rbp+57h+var_A8]
0x1801ffa05  mov     eax, esi
0x1801ffa07  shr     eax, 10h
0x1801ffa0a  movzx   edx, al
0x1801ffa0d  shr     ecx, 8
0x1801ffa10  sub     edx, ecx
0x1801ffa12  movzx   eax, si
0x1801ffa15  mov     ecx, [rbp+57h+var_A8]
0x1801ffa18  shr     eax, 8
0x1801ffa1b  add     edx, eax
0x1801ffa1d  mov     eax, ecx
0x1801ffa1f  shr     eax, 10h
0x1801ffa22  sub     edx, eax
0x1801ffa24  movzx   eax, cl
0x1801ffa27  sub     edx, eax
0x1801ffa29  movzx   eax, sil
0x1801ffa2d  add     edx, eax
0x1801ffa2f  mov     eax, 55555556h
0x1801ffa34  mov     ecx, edx
0x1801ffa36  neg     ecx
0x1801ffa38  cmovs   ecx, edx
0x1801ffa3b  imul    ecx
0x1801ffa3d  mov     eax, edx
0x1801ffa3f  shr     eax, 1Fh
0x1801ffa42  add     edx, eax
0x1801ffa44  movzx   eax, dl
0x1801ffa47  mov     edx, 1
0x1801ffa4c  shl     eax, 18h
0x1801ffa4f  or      eax, [rbp+57h+var_A4]
0x1801ffa52  mov     [r13+r12*4+0], eax
0x1801ffa57  jmp     short loc_1801FFA69
0x1801ffa59  cmp     r10d, edx
0x1801ffa5c  jnz     short loc_1801FFA71
0x1801ffa5e  or      r10d, 0FFFFFFFFh
0x1801ffa62  lea     r8d, [rbx-1]
0x1801ffa66  mov     r9d, ecx
0x1801ffa69  add     r8d, r10d
0x1801ffa6c  jmp     loc_1801FF9C1
0x1801ffa71  mov     r14d, ecx
0x1801ffa74  jmp     short loc_1801FFA87
0x1801ffa76  mov     rax, [rbp+57h+ppvBits]
0x1801ffa7a  movsxd  rcx, r9d
0x1801ffa7d  or      dword ptr [rax+rcx*4], 0FF000000h
0x1801ffa84  add     r9d, edx
0x1801ffa87  cmp     r9d, r14d
0x1801ffa8a  jle     short loc_1801FFA76
0x1801ffa8c  add     r11d, edx
0x1801ffa8f  cmp     r11d, ebx
0x1801ffa92  jl      loc_1801FF9B4
0x1801ffa98  mov     r14d, [rbp+57h+var_98]
0x1801ffa9c  mov     r12, [rbp+57h+var_90]
0x1801ffaa0  mov     r13, [rbp+57h+var_88]
0x1801ffaa4  xor     esi, esi
0x1801ffaa6  test    r14d, r14d
0x1801ffaa9  jle     short loc_1801FFB21
0x1801ffaab  mov     r15d, 80808081h
0x1801ffab1  mov     r11, [rbp+57h+ppvBits]
0x1801ffab5  mov     eax, r15d
0x1801ffab8  mov     r8d, [r11+rsi*4]
0x1801ffabc  mov     r9d, r8d
0x1801ffabf  shr     r9d, 18h
0x1801ffac3  movzx   ecx, r8w
0x1801ffac7  mov     r10d, r9d
0x1801ffaca  shr     ecx, 8
0x1801ffacd  imul    ecx, r9d
0x1801ffad1  bswap   r10d
0x1801ffad4  mul     ecx
0x1801ffad6  shr     edx, 7
0x1801ffad9  movzx   eax, dl
0x1801ffadc  shl     eax, 8
0x1801ffadf  or      r10d, eax
0x1801ffae2  mov     eax, r8d
0x1801ffae5  shr     eax, 10h
0x1801ffae8  movzx   ecx, al
0x1801ffaeb  mov     eax, r15d
0x1801ffaee  imul    ecx, r9d
0x1801ffaf2  mul     ecx
0x1801ffaf4  movzx   ecx, r8b
0x1801ffaf8  shr     edx, 7
0x1801ffafb  movzx   eax, dl
0x1801ffafe  shl     eax, 10h
0x1801ffb01  or      r10d, eax
0x1801ffb04  imul    ecx, r9d
0x1801ffb08  mov     eax, r15d
0x1801ffb0b  mul     ecx
0x1801ffb0d  shr     edx, 7
0x1801ffb10  movzx   eax, dl
0x1801ffb13  or      r10d, eax
0x1801ffb16  mov     [r11+rsi*4], r10d
0x1801ffb1a  inc     esi
0x1801ffb1c  cmp     esi, r14d
0x1801ffb1f  jl      short loc_1801FFAB1
0x1801ffb21  mov     rdx, [rbp+57h+h]; h
0x1801ffb25  mov     rcx, r12; hdc
0x1801ffb28  call    cs:__imp_SelectObject
0x1801ffb2f  nop     dword ptr [rax+rax+00h]
0x1801ffb34  mov     rcx, r12; hdc
0x1801ffb37  call    cs:__imp_DeleteDC
0x1801ffb3e  nop     dword ptr [rax+rax+00h]
0x1801ffb43  mov     rcx, [rdi+50h]; ho
0x1801ffb47  test    rcx, rcx
0x1801ffb4a  jz      short loc_1801FFB58
0x1801ffb4c  call    cs:__imp_DeleteObject
0x1801ffb53  nop     dword ptr [rax+rax+00h]
0x1801ffb58  mov     rax, [rdi+80h]
0x1801ffb5f  mov     [rdi+50h], r13
0x1801ffb63  mov     byte ptr [rdi+64h], 0
0x1801ffb67  mov     ecx, [rax+4]
0x1801ffb6a  mov     eax, [rbp+57h+var_B0]
0x1801ffb6d  mov     [rdi+5Ch], eax
0x1801ffb70  mov     eax, dword ptr [rbp+57h+var_AC]
0x1801ffb73  mov     [rdi+60h], eax
0x1801ffb76  mov     [rdi+58h], ecx
0x1801ffb79  mov     rcx, [rbp+57h+var_48]
0x1801ffb7d  xor     rcx, rsp; StackCookie
0x1801ffb80  call    __security_check_cookie
0x1801ffb85  add     rsp, 0A8h
0x1801ffb8c  pop     r15
0x1801ffb8e  pop     r14
0x1801ffb90  pop     r13
0x1801ffb92  pop     r12
0x1801ffb94  pop     rdi
0x1801ffb95  pop     rsi
0x1801ffb96  pop     rbx
0x1801ffb97  pop     rbp
0x1801ffb98  retn
```
