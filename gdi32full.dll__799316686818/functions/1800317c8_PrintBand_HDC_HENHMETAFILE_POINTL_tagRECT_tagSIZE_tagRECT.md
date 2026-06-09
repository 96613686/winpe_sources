# PrintBand(HDC__ *,HENHMETAFILE__ *,_POINTL *,tagRECT *,tagSIZE *,tagRECT *)

- ea: `0x1800317c8`
- end: `0x180031b1d`
- name: `?PrintBand@@YAXPEAUHDC__@@PEAUHENHMETAFILE__@@PEAU_POINTL@@PEAUtagRECT@@PEAUtagSIZE@@3@Z`
- size: `853`
- prototype: `void __usercall(HDC hdc@<rcx>, HENHMETAFILE@<rdx>, struct _POINTL *@<r8>, struct tagRECT *@<r9>, struct tagSIZE *, struct tagRECT *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800511f8`
- `0x180094054`

## callees

- `0x1800104e0`
- `0x1800317c8`
- `0x180031b30`
- `0x18007ac50`
- `0x180086a10`

## import_xrefs

- `GDI32!CreateRectRgn` at `0x180031a3d`
- `GDI32!CreateRectRgn` at `0x180031a3d`
- `GDI32!GetClipBox` at `0x180031a5c`
- `GDI32!GetClipBox` at `0x180031a5c`
- `GDI32!RestoreDC` at `0x180031ac3`
- `GDI32!RestoreDC` at `0x180031ac3`
- `GDI32!SaveDC` at `0x180031a6a`
- `GDI32!SaveDC` at `0x180031a6a`
- `GDI32!SelectClipRgn` at `0x180031a9c`
- `GDI32!SelectClipRgn` at `0x180031acd`
- `GDI32!SelectClipRgn` at `0x180031a9c`
- `GDI32!SelectClipRgn` at `0x180031acd`
- `GDI32!ExtSelectClipRgn` at `0x180031a8e`
- `GDI32!ExtSelectClipRgn` at `0x180031a8e`
- `GDI32!DeleteObject` at `0x180031ad6`
- `GDI32!DeleteObject` at `0x180031ad6`
- `USER32!IntersectRect` at `0x1800319d3`
- `USER32!IntersectRect` at `0x1800319d3`
- `win32u!NtGdiGetPerBandInfo` at `0x180031875`
- `win32u!NtGdiGetPerBandInfo` at `0x180031875`

## pseudocode

```c
void __fastcall PrintBand(
        HDC hdc,
        HENHMETAFILE a2,
        struct _POINTL *a3,
        struct tagRECT *a4,
        struct tagSIZE *a5,
        struct tagRECT *lprcSrc1)
{
  struct tagSIZE *v6; // r15
  struct _POINTL *v8; // r14
  int v10; // r8d
  int v11; // edx
  int v12; // ebx
  int v13; // edi
  int cy; // eax
  int PerBandInfo; // eax
  int v16; // edx
  int cx; // ecx
  float v18; // xmm7_4
  float v19; // xmm6_4
  __m128i v20; // xmm1
  float y; // xmm0_4
  LONG x; // edi
  int v23; // ebx
  int v24; // edx
  int v25; // ecx
  int v26; // r9d
  int v27; // r8d
  int v28; // r14d
  int v29; // r15d
  LONG right; // r8d
  LONG bottom; // r9d
  int v32; // r15d
  HRGN RectRgn; // r14
  int y2[4]; // [rsp+40h] [rbp-71h] BYREF
  int v37; // [rsp+50h] [rbp-61h]
  RECT rect; // [rsp+58h] [rbp-59h] BYREF
  RECT rcSrc2; // [rsp+68h] [rbp-49h] BYREF
  struct tagRECT rcDst; // [rsp+78h] [rbp-39h] BYREF

  v6 = a5;
  *(_OWORD *)y2 = 0;
  v37 = 0;
  v8 = a3;
  do
  {
    v10 = -v8->y;
    v11 = -v8->x;
    rect = *a4;
    SetViewportOrgEx(hdc, v11, v10, 0);
    v12 = a4->right - a4->left;
    v13 = a4->bottom - a4->top;
    y2[1] = v6->cx;
    cy = v6->cy;
    y2[3] = v12;
    v37 = v13;
    y2[2] = cy;
    y2[0] = 0;
    PerBandInfo = NtGdiGetPerBandInfo(hdc, y2);
    if ( PerBandInfo == -1 )
      break;
    if ( PerBandInfo )
    {
      if ( v12 != y2[3] || v13 != v37 )
      {
        v18 = (float)v12 / (float)y2[3];
        v19 = (float)v13 / (float)v37;
        rect.left = (int)(float)((float)rect.left / v18);
        rect.top = (int)(float)((float)rect.top / v19);
        v20 = _mm_cvtsi32_si128(v8->x);
        rect.right = (int)(float)((float)rect.right / v18);
        y = (float)v8->y;
        rect.bottom = (int)(float)((float)rect.bottom / v19);
        x = (int)(float)(_mm_cvtepi32_ps(v20).m128_f32[0] / v18);
        v23 = (int)(float)(y / v19);
        SetViewportOrgEx(hdc, -x, -v23, 0);
        v24 = 0;
        v25 = 0;
        v26 = (int)(float)((float)y2[2] / v19);
        v27 = (int)(float)((float)y2[1] / v18);
LABEL_23:
        v32 = 0;
        RectRgn = CreateRectRgn(v25, v24, v27, v26);
        if ( RectRgn )
        {
          rcDst = 0;
          if ( (unsigned int)GetClipBox(hdc, &rcDst) <= 1 )
          {
            SelectClipRgn(hdc, RectRgn);
          }
          else
          {
            SaveDC(hdc);
            OffsetClipRgn(hdc, -x, -v23);
            ExtSelectClipRgn(hdc, RectRgn, 1);
            v32 = 1;
          }
        }
        PlayEnhMetaFile(hdc, a2, &rect);
        if ( RectRgn )
        {
          if ( v32 )
            RestoreDC(hdc, -1);
          else
            SelectClipRgn(hdc, 0);
          DeleteObject(RectRgn);
        }
        goto LABEL_32;
      }
      v16 = y2[2];
      cx = y2[1];
    }
    else
    {
      cx = v6->cx;
      v16 = v6->cy;
      y2[1] = v6->cx;
      y2[2] = v16;
      y2[0] = 0;
      y2[3] = v12;
      v37 = v13;
    }
    v28 = 0;
    v29 = 0;
    x = a3->x;
    v23 = a3->y;
    if ( !lprcSrc1 )
    {
      right = a4->right;
      bottom = a4->bottom;
LABEL_16:
      if ( x + cx <= right )
        v27 = cx;
      else
        v27 = right - x;
      if ( v23 + v16 <= bottom )
        v26 = v16;
      else
        v26 = bottom - v23;
      v24 = v29;
      v25 = v28;
      goto LABEL_23;
    }
    rcSrc2.left = a3->x;
    rcSrc2.right = x + cx;
    rcSrc2.top = v23;
    rcSrc2.bottom = v23 + v16;
    rcDst = 0;
    if ( IntersectRect(&rcDst, lprcSrc1, &rcSrc2) )
    {
      right = lprcSrc1->right;
      bottom = lprcSrc1->bottom;
      if ( lprcSrc1->left > x )
        v28 = lprcSrc1->left - x;
      v16 = y2[2];
      cx = y2[1];
      if ( lprcSrc1->top > v23 )
        v29 = lprcSrc1->top - v23;
      goto LABEL_16;
    }
LABEL_32:
    v8 = a3;
    v6 = a5;
  }
  while ( y2[0] );
}

```

## disassembly

```asm
0x1800317c8  mov     rax, rsp
0x1800317cb  push    rbp
0x1800317cc  push    rbx
0x1800317cd  push    rsi
0x1800317ce  push    rdi
0x1800317cf  push    r12
0x1800317d1  push    r13
0x1800317d3  push    r14
0x1800317d5  push    r15
0x1800317d7  lea     rbp, [rax-4Fh]
0x1800317db  sub     rsp, 0B8h
0x1800317e2  movaps  xmmword ptr [rax-58h], xmm6
0x1800317e6  movaps  xmmword ptr [rax-68h], xmm7
0x1800317ea  mov     rax, cs:__security_cookie
0x1800317f1  xor     rax, rsp
0x1800317f4  mov     [rbp+47h+var_70], rax
0x1800317f8  mov     r15, [rbp+47h+arg_20]
0x1800317fc  xorps   xmm0, xmm0
0x1800317ff  mov     r12, [rbp+47h+lprcSrc1]
0x180031803  xor     eax, eax
0x180031805  mov     [rbp+47h+var_C0], r15
0x180031809  mov     r13, r9
0x18003180c  movups  xmmword ptr [rbp+47h+y2], xmm0
0x180031810  mov     [rbp+47h+var_A8], eax
0x180031813  mov     r14, r8
0x180031816  mov     [rsp+0F0h+var_D0], r8
0x18003181b  mov     rsi, rcx
0x18003181e  mov     [rsp+0F0h+hmf], rdx
0x180031823  movups  xmm0, xmmword ptr [r13+0]
0x180031828  mov     r8d, [r14+4]
0x18003182c  xor     r9d, r9d; lppt
0x18003182f  mov     edx, [r14]
0x180031832  neg     r8d; y
0x180031835  neg     edx; x
0x180031837  mov     rcx, rsi; hdc
0x18003183a  movdqu  xmmword ptr [rbp+47h+rect.left], xmm0
0x18003183f  call    SetViewportOrgEx
0x180031844  mov     eax, [r15]
0x180031847  lea     rdx, [rbp+47h+y2]
0x18003184b  mov     ebx, [r13+8]
0x18003184f  mov     rcx, rsi
0x180031852  mov     edi, [r13+0Ch]
0x180031856  sub     ebx, [r13+0]
0x18003185a  sub     edi, [r13+4]
0x18003185e  mov     [rbp+47h+y2+4], eax
0x180031861  mov     eax, [r15+4]
0x180031865  mov     [rbp+47h+y2+0Ch], ebx
0x180031868  mov     [rbp+47h+var_A8], edi
0x18003186b  mov     [rbp+47h+y2+8], eax
0x18003186e  mov     [rbp+47h+y2], 0
0x180031875  call    cs:__imp_NtGdiGetPerBandInfo
0x18003187b  cmp     eax, 0FFFFFFFFh
0x18003187e  jz      loc_180031AEF
0x180031884  test    eax, eax
0x180031886  jz      loc_180031980
0x18003188c  cmp     ebx, [rbp+47h+y2+0Ch]
0x18003188f  jnz     short loc_1800318A1
0x180031891  cmp     edi, [rbp+47h+var_A8]
0x180031894  jnz     short loc_1800318A1
0x180031896  mov     edx, [rbp+47h+y2+8]
0x180031899  mov     ecx, [rbp+47h+y2+4]
0x18003189c  jmp     loc_18003199A
0x1800318a1  movd    xmm1, [rbp+47h+rect.left]
0x1800318a6  xorps   xmm0, xmm0
0x1800318a9  cvtdq2ps xmm1, xmm1
0x1800318ac  mov     eax, ebx
0x1800318ae  xor     r9d, r9d; lppt
0x1800318b1  mov     rcx, rsi; hdc
0x1800318b4  xorps   xmm7, xmm7
0x1800318b7  xorps   xmm6, xmm6
0x1800318ba  cvtsi2ss xmm7, rax
0x1800318bf  mov     eax, [rbp+47h+y2+0Ch]
0x1800318c2  cvtsi2ss xmm0, rax
0x1800318c7  mov     eax, edi
0x1800318c9  cvtsi2ss xmm6, rax
0x1800318ce  mov     eax, [rbp+47h+var_A8]
0x1800318d1  divss   xmm7, xmm0
0x1800318d5  xorps   xmm0, xmm0
0x1800318d8  cvtsi2ss xmm0, rax
0x1800318dd  divss   xmm1, xmm7
0x1800318e1  divss   xmm6, xmm0
0x1800318e5  movd    xmm0, [rbp+47h+rect.top]
0x1800318ea  cvttss2si eax, xmm1
0x1800318ee  movd    xmm1, [rbp+47h+rect.right]
0x1800318f3  cvtdq2ps xmm0, xmm0
0x1800318f6  mov     [rbp+47h+rect.left], eax
0x1800318f9  cvtdq2ps xmm1, xmm1
0x1800318fc  divss   xmm0, xmm6
0x180031900  divss   xmm1, xmm7
0x180031904  cvttss2si eax, xmm0
0x180031908  movd    xmm0, [rbp+47h+rect.bottom]
0x18003190d  cvtdq2ps xmm0, xmm0
0x180031910  mov     [rbp+47h+rect.top], eax
0x180031913  cvttss2si eax, xmm1
0x180031917  movd    xmm1, dword ptr [r14]
0x18003191c  divss   xmm0, xmm6
0x180031920  mov     [rbp+47h+rect.right], eax
0x180031923  cvtdq2ps xmm1, xmm1
0x180031926  cvttss2si eax, xmm0
0x18003192a  movd    xmm0, dword ptr [r14+4]
0x180031930  cvtdq2ps xmm0, xmm0
0x180031933  mov     [rbp+47h+rect.bottom], eax
0x180031936  divss   xmm1, xmm7
0x18003193a  divss   xmm0, xmm6
0x18003193e  cvttss2si edi, xmm1
0x180031942  cvttss2si ebx, xmm0
0x180031946  mov     edx, edi
0x180031948  neg     edx; x
0x18003194a  mov     r8d, ebx
0x18003194d  neg     r8d; y
0x180031950  call    SetViewportOrgEx
0x180031955  movd    xmm0, [rbp+47h+y2+8]
0x18003195a  xor     edx, edx
0x18003195c  movd    xmm1, [rbp+47h+y2+4]
0x180031961  xor     ecx, ecx
0x180031963  cvtdq2ps xmm0, xmm0
0x180031966  cvtdq2ps xmm1, xmm1
0x180031969  divss   xmm0, xmm6
0x18003196d  divss   xmm1, xmm7
0x180031971  cvttss2si r9, xmm0
0x180031976  cvttss2si r8, xmm1
0x18003197b  jmp     loc_180031A3D
0x180031980  mov     ecx, [r15]
0x180031983  mov     edx, [r15+4]
0x180031987  mov     [rbp+47h+y2+4], ecx
0x18003198a  mov     [rbp+47h+y2+8], edx
0x18003198d  mov     [rbp+47h+y2], 0
0x180031994  mov     [rbp+47h+y2+0Ch], ebx
0x180031997  mov     [rbp+47h+var_A8], edi
0x18003199a  mov     rbx, [rsp+0F0h+var_D0]
0x18003199f  xor     r14d, r14d
0x1800319a2  xor     r15d, r15d
0x1800319a5  mov     edi, [rbx]
0x1800319a7  mov     ebx, [rbx+4]
0x1800319aa  test    r12, r12
0x1800319ad  jz      short loc_180031A0F
0x1800319af  lea     eax, [rdi+rcx]
0x1800319b2  mov     [rbp+47h+rcSrc2.left], edi
0x1800319b5  mov     [rbp+47h+rcSrc2.right], eax
0x1800319b8  lea     r8, [rbp+47h+rcSrc2]; lprcSrc2
0x1800319bc  lea     eax, [rbx+rdx]
0x1800319bf  mov     [rbp+47h+rcSrc2.top], ebx
0x1800319c2  xorps   xmm0, xmm0
0x1800319c5  mov     [rbp+47h+rcSrc2.bottom], eax
0x1800319c8  mov     rdx, r12; lprcSrc1
0x1800319cb  lea     rcx, [rbp+47h+rcDst]; lprcDst
0x1800319cf  movups  xmmword ptr [rbp+47h+rcDst.left], xmm0
0x1800319d3  call    cs:__imp_IntersectRect
0x1800319d9  test    eax, eax
0x1800319db  jz      loc_180031ADC
0x1800319e1  mov     r8d, [r12+8]
0x1800319e6  mov     r9d, [r12+0Ch]
0x1800319eb  cmp     [r12], edi
0x1800319ef  jle     short loc_1800319F8
0x1800319f1  mov     r14d, [r12]
0x1800319f5  sub     r14d, edi
0x1800319f8  mov     edx, [rbp+47h+y2+8]
0x1800319fb  mov     ecx, [rbp+47h+y2+4]
0x1800319fe  cmp     [r12+4], ebx
0x180031a03  jle     short loc_180031A17
0x180031a05  mov     r15d, [r12+4]
0x180031a0a  sub     r15d, ebx
0x180031a0d  jmp     short loc_180031A17
0x180031a0f  mov     r8d, [r13+8]
0x180031a13  mov     r9d, [r13+0Ch]
0x180031a17  lea     eax, [rdi+rcx]
0x180031a1a  cmp     eax, r8d
0x180031a1d  jle     short loc_180031A24
0x180031a1f  sub     r8d, edi
0x180031a22  jmp     short loc_180031A27
0x180031a24  mov     r8d, ecx; x2
0x180031a27  lea     eax, [rbx+rdx]
0x180031a2a  cmp     eax, r9d
0x180031a2d  jle     short loc_180031A34
0x180031a2f  sub     r9d, ebx
0x180031a32  jmp     short loc_180031A37
0x180031a34  mov     r9d, edx; y2
0x180031a37  mov     edx, r15d; y1
0x180031a3a  mov     ecx, r14d; x1
0x180031a3d  call    cs:__imp_CreateRectRgn
0x180031a43  xor     r15d, r15d
0x180031a46  mov     r14, rax
0x180031a49  test    rax, rax
0x180031a4c  jz      short loc_180031AA2
0x180031a4e  xorps   xmm0, xmm0
0x180031a51  lea     rdx, [rbp+47h+rcDst]; lprect
0x180031a55  mov     rcx, rsi; hdc
0x180031a58  movups  xmmword ptr [rbp+47h+rcDst.left], xmm0
0x180031a5c  call    cs:__imp_GetClipBox
0x180031a62  mov     rcx, rsi; hdc
0x180031a65  cmp     eax, 1
0x180031a68  jbe     short loc_180031A99
0x180031a6a  call    cs:__imp_SaveDC
0x180031a70  neg     ebx
0x180031a72  neg     edi
0x180031a74  mov     r8d, ebx; y
0x180031a77  mov     edx, edi; x
0x180031a79  mov     rcx, rsi; hdc
0x180031a7c  call    OffsetClipRgn
0x180031a81  lea     ebx, [r15+1]
0x180031a85  mov     rdx, r14; hrgn
0x180031a88  mov     r8d, ebx; mode
0x180031a8b  mov     rcx, rsi; hdc
0x180031a8e  call    cs:__imp_ExtSelectClipRgn
0x180031a94  mov     r15d, ebx
0x180031a97  jmp     short loc_180031AA2
0x180031a99  mov     rdx, r14; hrgn
0x180031a9c  call    cs:__imp_SelectClipRgn
0x180031aa2  mov     rdx, [rsp+0F0h+hmf]; hmf
0x180031aa7  lea     r8, [rbp+47h+rect]; lprect
0x180031aab  mov     rcx, rsi; hdc
0x180031aae  call    PlayEnhMetaFile
0x180031ab3  test    r14, r14
0x180031ab6  jz      short loc_180031ADC
0x180031ab8  mov     rcx, rsi; hdc
0x180031abb  test    r15d, r15d
0x180031abe  jz      short loc_180031ACB
0x180031ac0  or      edx, 0FFFFFFFFh; nSavedDC
0x180031ac3  call    cs:__imp_RestoreDC
0x180031ac9  jmp     short loc_180031AD3
0x180031acb  xor     edx, edx; hrgn
0x180031acd  call    cs:__imp_SelectClipRgn
0x180031ad3  mov     rcx, r14; ho
0x180031ad6  call    cs:__imp_DeleteObject
0x180031adc  cmp     [rbp+47h+y2], 0
0x180031ae0  mov     r14, [rsp+0F0h+var_D0]
0x180031ae5  mov     r15, [rbp+47h+var_C0]
0x180031ae9  jnz     loc_180031823
0x180031aef  mov     rcx, [rbp+47h+var_70]
0x180031af3  xor     rcx, rsp; StackCookie
0x180031af6  call    __security_check_cookie
0x180031afb  lea     r11, [rsp+0F0h+var_38]
0x180031b03  movaps  xmm6, xmmword ptr [r11-18h]
0x180031b08  movaps  xmm7, xmmword ptr [r11-28h]
0x180031b0d  mov     rsp, r11
0x180031b10  pop     r15
0x180031b12  pop     r14
0x180031b14  pop     r13
0x180031b16  pop     r12
0x180031b18  pop     rdi
0x180031b19  pop     rsi
0x180031b1a  pop     rbx
0x180031b1b  pop     rbp
0x180031b1c  retn
```
