# CFICache::GetFontInfoFromFaceNameHelper(FONTINFO &,short,CFontOptions const &,FONTINFO_FLAGS &,CCharFlags &)

- ea: `0x180011030`
- end: `0x1800117de`
- name: `?GetFontInfoFromFaceNameHelper@CFICache@@CAXAEAUFONTINFO@@FAEBVCFontOptions@@AEATFONTINFO_FLAGS@@AEAVCCharFlags@@@Z`
- size: `1966`
- prototype: `void __fastcall(struct FONTINFO *, __int16, const struct CFontOptions *, union FONTINFO_FLAGS *, struct CCharFlags *)`
- caller_count: `6`
- callee_count: `13`
- tags: ``

## callers

- `0x18000f800`
- `0x180010e6c`
- `0x180012a58`
- `0x18002fa30`
- `0x18005674c`
- `0x18009d060`

## callees

- `0x180011030`
- `0x18001db40`
- `0x180034728`
- `0x180044ea4`
- `0x180052d00`
- `0x1800adcc8`
- `0x1800adf98`
- `0x1800af038`
- `0x1800f0cb8`
- `0x1800f6784`
- `0x18013ce80`
- `0x18013dce6`
- `0x18027f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001116a`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001116a`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800115c1`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800115c1`

## pseudocode

```c
void __fastcall CFICache::GetFontInfoFromFaceNameHelper(
        struct FONTINFO *a1,
        __int16 a2,
        const struct CFontOptions *a3,
        union FONTINFO_FLAGS *a4,
        struct CCharFlags *a5)
{
  __int16 cjMaxGlyph32; // ax
  const struct CFontOptions *v7; // r13
  unsigned __int64 v8; // rsi
  char v10; // r15
  HDC ScreenDC; // rax
  const unsigned __int16 *FontName; // rax
  __int64 v13; // r9
  HGDIOBJ v14; // rcx
  unsigned __int16 *v15; // r8
  unsigned __int16 *v16; // r10
  unsigned __int16 v17; // dx
  unsigned __int16 v18; // cx
  __int16 v19; // r8
  int v20; // edx
  int v21; // ecx
  const struct CXScribe *XScribe; // rax
  __int16 v23; // ax
  __int64 v24; // rcx
  __int16 v25; // r11
  int v26; // [rsp+20h] [rbp-E0h]
  char v27; // [rsp+60h] [rbp-A0h] BYREF
  char v28; // [rsp+61h] [rbp-9Fh] BYREF
  _BYTE v29[6]; // [rsp+62h] [rbp-9Eh] BYREF
  unsigned __int64 v30; // [rsp+68h] [rbp-98h] BYREF
  int v31; // [rsp+70h] [rbp-90h] BYREF
  struct IGraphicContext *GraphicContext; // [rsp+78h] [rbp-88h] BYREF
  char v33; // [rsp+80h] [rbp-80h]
  __int64 v34; // [rsp+84h] [rbp-7Ch]
  char v35; // [rsp+8Ch] [rbp-74h]
  __int64 v36; // [rsp+90h] [rbp-70h] BYREF
  _OWORD v37[2]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v38; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v39; // [rsp+C8h] [rbp-38h]
  int v40; // [rsp+D8h] [rbp-28h]
  struct IGraphicContext **p_GraphicContext; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v42[96]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v43; // [rsp+148h] [rbp+48h]
  __int64 v44; // [rsp+150h] [rbp+50h]
  int v45; // [rsp+158h] [rbp+58h]
  __int16 v46; // [rsp+15Ch] [rbp+5Ch]
  char v47; // [rsp+15Eh] [rbp+5Eh]
  char v48; // [rsp+160h] [rbp+60h]
  _BYTE v49[96]; // [rsp+170h] [rbp+70h] BYREF
  HGDIOBJ ho[2]; // [rsp+1D0h] [rbp+D0h]
  int v51; // [rsp+1E0h] [rbp+E0h]
  __int16 v52; // [rsp+1E4h] [rbp+E4h]
  char v53; // [rsp+1E6h] [rbp+E6h]
  _DWORD v54[5]; // [rsp+1F0h] [rbp+F0h] BYREF
  char v55; // [rsp+207h] [rbp+107h]
  unsigned __int16 v56[34]; // [rsp+20Ch] [rbp+10Ch] BYREF
  _BYTE v57[16]; // [rsp+250h] [rbp+150h] BYREF
  _BYTE v58[16]; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v59[16]; // [rsp+270h] [rbp+170h] BYREF
  unsigned __int16 v60[32]; // [rsp+280h] [rbp+180h] BYREF

  cjMaxGlyph32 = a1->cjMaxGlyph32;
  v30 = (unsigned __int64)a3;
  v7 = a3;
  v8 = a2;
  *(_WORD *)a4 = cjMaxGlyph32;
  if ( (cjMaxGlyph32 & 1) != 0 )
  {
    *(_OWORD *)a5 = *(_OWORD *)&a1->cjThis;
    goto LABEL_3;
  }
  v10 = *((_BYTE *)a3 + 8);
  if ( v10 )
    ScreenDC = 0;
  else
    ScreenDC = CW32System::GetScreenDC();
  GraphicContext = CreateGraphicContext(v10, *((const struct IDpiAccessor **)v7 + 2), ScreenDC, 0);
  v33 = 0;
  v34 = 0;
  v35 = 0;
  *(_OWORD *)ho = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  memset_0(v49, 0, 0x5Cu);
  memset_0(v54, 0, 0x5Cu);
  FontName = CFICache::GetFontName(v8);
  if ( FontName )
  {
    _o_wcsncpy_s(v56, 32, FontName);
    v56[31] = 0;
  }
  else
  {
    v56[0] = 0;
  }
  v55 = 1;
  v54[0] = -2048;
  LOBYTE(v13) = 9;
  if ( (*(unsigned __int8 (__fastcall **)(struct IGraphicContext *, _DWORD *, _BYTE *, __int64))(*(_QWORD *)GraphicContext
                                                                                               + 136LL))(
         GraphicContext,
         v54,
         v49,
         v13) )
  {
    v43 = 0;
    v44 = 0;
    p_GraphicContext = &GraphicContext;
    v45 = 0;
    v46 = 0;
    v47 = 0;
    memset_0(v42, 0, 0x5Cu);
    v48 = 0;
    v48 = (*(__int64 (__fastcall **)(struct IGraphicContext *, _BYTE *, _BYTE *))(*(_QWORD *)*p_GraphicContext + 384LL))(
            *p_GraphicContext,
            v49,
            v42);
    if ( !v48 )
    {
LABEL_52:
      CSelectFont::Unselect((CSelectFont *)&p_GraphicContext);
      CFont::Destroy((CFont *)v42);
      goto LABEL_12;
    }
    v27 = 0;
    v28 = 0;
    v60[0] = 0;
    (*(void (__fastcall **)(struct IGraphicContext *, __int64, unsigned __int16 *))(*(_QWORD *)GraphicContext + 160LL))(
      GraphicContext,
      32,
      v60);
    v15 = v56;
    v16 = v60;
    do
    {
      v17 = *v16;
      if ( *v16 <= 0x5Au && *v15 >= 0x41u )
        v17 += 32;
      v18 = *v15;
      if ( (unsigned __int16)(*v15 - 65) <= 0x19u )
        v18 += 32;
      if ( v17 != v18 )
        break;
      ++v16;
      ++v15;
    }
    while ( v18 );
    v7 = (const struct CFontOptions *)v30;
    if ( v17 == v18
      || (v30 = 0, (CCharFlags::GetCharFlagsHelper(v60, 2, 0, 0, 0, v10, &v30) & 0xF00000) != 0)
      && (v30 = 0, (CCharFlags::GetCharFlagsHelper(v56, 2, 0, 0, 0, v10, &v30) & 0xC0) != 0) )
    {
      v29[0] = 0;
      *(_OWORD *)a5 = *(_OWORD *)CFICache::GetCharFlagsFromDC(
                                   v57,
                                   &GraphicContext,
                                   (unsigned __int16)v8,
                                   v29,
                                   &v27,
                                   &v28);
      if ( v29[0] )
        *(_WORD *)a4 |= 0x10u;
      if ( (int)v8 >= 70 )
      {
        if ( !(unsigned int)CW32System::wcsicmp(v60, L"Apple Color Emoji") )
        {
          *(_WORD *)a4 = v25 | 0x4000;
          *((_QWORD *)a5 + 1) |= 3uLL;
        }
LABEL_31:
        if ( (*(unsigned int (__fastcall **)(struct IGraphicContext *, __int64, _QWORD, _QWORD))(*(_QWORD *)GraphicContext
                                                                                               + 152LL))(
               GraphicContext,
               1213481293,
               0,
               0) == -1 )
        {
LABEL_32:
          if ( (int)v8 >= 70 )
          {
            if ( (*(unsigned int (__fastcall **)(struct IGraphicContext *, __int64, _QWORD, _QWORD))(*(_QWORD *)GraphicContext + 152LL))(
                   GraphicContext,
                   1380732739,
                   0,
                   0) != -1 )
              *(_WORD *)a4 |= 0x4000u;
          }
          else if ( (_DWORD)v8 == 49 )
          {
            *(_WORD *)a4 |= 0x4000u;
            *((_QWORD *)a5 + 1) |= 2uLL;
          }
          LOBYTE(v26) = 1;
          memset(v37, 0, 28);
          (*(void (__fastcall **)(struct IGraphicContext *, _OWORD *, _QWORD, __int64, int))(*(_QWORD *)GraphicContext
                                                                                           + 192LL))(
            GraphicContext,
            v37,
            0,
            0xFFFFFFFFLL,
            v26);
          v19 = (8 * (BYTE9(v37[1]) & 1)) | *(_WORD *)a4 & 0xFFF3 | (4 * (BYTE8(v37[1]) & 1)) & 0xF7;
          *(_WORD *)a4 = v19;
          if ( (v19 & 2) == 0 && (*(_QWORD *)a5 & 0x200000080000LL) == 0x80000 )
          {
            if ( !DWORD2(v37[0]) || (v23 = 64, SDWORD1(v37[0]) / SDWORD2(v37[0]) >= 3) )
              v23 = 0;
            v19 = v23 | v19 & 0xFFBF;
            *(_WORD *)a4 = v19;
          }
          if ( (int)v8 >= 70 || (_WORD)v8 == 5 || (_DWORD)v8 == 9 || v27 || v28 )
          {
            v40 = 0;
            v38 = 0;
            v39 = 0;
            if ( (*(unsigned __int8 (__fastcall **)(struct IGraphicContext *, __int128 *))(*(_QWORD *)GraphicContext
                                                                                         + 200LL))(
                   GraphicContext,
                   &v38) )
            {
              v20 = -(int)v39;
              if ( (int)v39 > 0 )
                v20 = v39;
              if ( (v38 & 0x80u) != 0LL || v27 || DWORD1(v37[0]) > 2 * (v20 + DWORD2(v38)) )
                *(_WORD *)a4 |= 0x100u;
              v21 = -HIDWORD(v38);
              if ( SHIDWORD(v38) > 0 )
                v21 = HIDWORD(v38);
              if ( DWORD2(v37[0]) > 3 * v21 || v28 )
                *(_WORD *)a4 |= 0x2000u;
              HIWORD(a1->cjMaxGlyph4) = WORD4(v38);
              LOWORD(a1->cjMaxGlyph8) = v21;
              HIWORD(a1->cjMaxGlyph8) = v20;
              if ( (int)v8 >= 70 && (*(_DWORD *)a5 & 0xF00000) == 0 && !v10 )
              {
                LODWORD(v30) = 0;
                v31 = 0;
                v36 = 0;
                XScribe = GetXScribe(0);
                if ( XScribe )
                {
                  LOWORD(v31) = v31 & 0xFC00 | *((unsigned __int8 *)XScribe + 18);
                  if ( !(*(unsigned int (__fastcall **)(struct IGraphicContext *, __int64 *, const wchar_t *, __int64, int, int *, _BYTE *, _BYTE *, _BYTE *, unsigned __int64 *, _BYTE))(*(_QWORD *)GraphicContext + 312LL))(
                          GraphicContext,
                          &v36,
                          L"final",
                          5,
                          5,
                          &v31,
                          v57,
                          v59,
                          v58,
                          &v30,
                          0)
                    && (_DWORD)v30 == 4 )
                  {
                    *(_WORD *)a4 |= 0x200u;
                  }
                }
              }
            }
          }
          else if ( (unsigned __int16)v8 <= 0x39u )
          {
            v24 = 0x200100000000008LL;
            if ( _bittest64(&v24, v8) )
              *(_WORD *)a4 = v19 | 0x200;
          }
          goto LABEL_52;
        }
LABEL_76:
        *(_WORD *)a4 |= 0x80u;
        *(_QWORD *)a5 |= 0x30001C8uLL;
        goto LABEL_32;
      }
    }
    else
    {
      *(_WORD *)a4 |= 2u;
      if ( (int)v8 >= 70 )
        goto LABEL_31;
    }
    if ( (_WORD)v8 != 5 )
      goto LABEL_32;
    goto LABEL_76;
  }
LABEL_12:
  v14 = ho[0];
  *(_WORD *)a4 |= 1u;
  *(_OWORD *)&a1->cjThis = *(_OWORD *)a5;
  LOWORD(a1->cjMaxGlyph32) = *(_WORD *)a4;
  if ( v14 )
  {
    if ( (_BYTE)v52 )
    {
      (*(void (__fastcall **)(HGDIOBJ))(*(_QWORD *)v14 + 16LL))(v14);
      if ( ho[1] )
        (*(void (__fastcall **)(HGDIOBJ))(*(_QWORD *)ho[1] + 16LL))(ho[1]);
    }
    else
    {
      DeleteObject(v14);
    }
    *(_OWORD *)ho = 0;
  }
  if ( GraphicContext )
    (**(void (__fastcall ***)(struct IGraphicContext *))GraphicContext)(GraphicContext);
LABEL_3:
  if ( *(_QWORD *)v7 )
  {
    if ( *(_QWORD *)a5 != 0x40000 )
    {
      *(_QWORD *)a5 = -262145;
      *((_QWORD *)a5 + 1) = -1;
    }
  }
}

```

## disassembly

```asm
0x180011030  push    rbp
0x180011032  push    rbx
0x180011033  push    rsi
0x180011034  push    rdi
0x180011035  push    r12
0x180011037  push    r13
0x180011039  push    r14
0x18001103b  push    r15
0x18001103d  lea     rbp, [rsp-1D8h]
0x180011045  sub     rsp, 2D8h
0x18001104c  mov     rax, cs:__security_cookie
0x180011053  xor     rax, rsp
0x180011056  mov     [rbp+210h+var_50], rax
0x18001105d  movzx   eax, word ptr [rcx+18h]
0x180011061  xor     r12d, r12d
0x180011064  mov     rdi, [rbp+210h+arg_20]
0x18001106b  mov     rbx, r9
0x18001106e  mov     [rsp+310h+var_2A8], r8
0x180011073  mov     r13, r8
0x180011076  movsx   rsi, dx
0x18001107a  mov     r14, rcx
0x18001107d  mov     [r9], ax
0x180011081  test    al, 1
0x180011083  jz      short loc_1800110D0
0x180011085  movups  xmm0, xmmword ptr [rcx]
0x180011088  movdqu  xmmword ptr [rdi], xmm0
0x18001108c  cmp     [r13+0], r12
0x180011090  jnz     short loc_1800110B6
0x180011092  mov     rcx, [rbp+210h+var_50]
0x180011099  xor     rcx, rsp; StackCookie
0x18001109c  call    __security_check_cookie
0x1800110a1  add     rsp, 2D8h
0x1800110a8  pop     r15
0x1800110aa  pop     r14
0x1800110ac  pop     r13
0x1800110ae  pop     r12
0x1800110b0  pop     rdi
0x1800110b1  pop     rsi
0x1800110b2  pop     rbx
0x1800110b3  pop     rbp
0x1800110b4  retn
0x1800110b6  cmp     qword ptr [rdi], 40000h
0x1800110bd  jz      short loc_180011092
0x1800110bf  mov     qword ptr [rdi], 0FFFFFFFFFFFBFFFFh
0x1800110c6  mov     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x1800110ce  jmp     short loc_180011092
0x1800110d0  mov     r15b, [r8+8]
0x1800110d4  test    r15b, r15b
0x1800110d7  jz      loc_1800111FB
0x1800110dd  mov     rax, r12
0x1800110e0  mov     rdx, [r13+10h]; struct IDpiAccessor *
0x1800110e4  xor     r9d, r9d; struct ITextRenderTarget *
0x1800110e7  mov     r8, rax; HDC
0x1800110ea  mov     cl, r15b; bool
0x1800110ed  call    ?CreateGraphicContext@@YAPEAVIGraphicContext@@_NPEBVIDpiAccessor@@PEAUHDC__@@PEAUITextRenderTarget@@@Z; CreateGraphicContext(bool,IDpiAccessor const *,HDC__ *,ITextRenderTarget *)
0x1800110f2  xor     edx, edx; Val
0x1800110f4  mov     [rsp+310h+var_298], rax
0x1800110f9  xorps   xmm0, xmm0
0x1800110fc  mov     [rbp+210h+var_290], r12b
0x180011100  lea     rcx, [rbp+210h+var_1A0]; void *
0x180011104  mov     [rbp+210h+var_28C], r12
0x180011108  mov     [rbp+210h+var_284], r12b
0x18001110c  lea     r8d, [rdx+5Ch]; Size
0x180011110  movdqa  xmmword ptr [rbp+210h+ho], xmm0
0x180011118  mov     [rbp+210h+var_130], r12d
0x18001111f  mov     [rbp+210h+var_12C], r12w
0x180011127  mov     [rbp+210h+var_12A], r12b
0x18001112e  call    memset_0
0x180011133  xor     edx, edx; Val
0x180011135  lea     rcx, [rbp+210h+var_120]; void *
0x18001113c  lea     r8d, [rdx+5Ch]; Size
0x180011140  call    memset_0
0x180011145  movzx   ecx, si; __int16
0x180011148  call    ?GetFontName@CFICache@@SAPEBGF@Z; CFICache::GetFontName(short)
0x18001114d  test    rax, rax
0x180011150  jz      loc_180011248
0x180011156  mov     r9d, 1Fh
0x18001115c  lea     rcx, [rbp+210h+var_104]
0x180011163  mov     r8, rax
0x180011166  lea     edx, [r9+1]
0x18001116a  call    cs:__imp__o_wcsncpy_s
0x180011171  nop     dword ptr [rax+rax+00h]
0x180011176  mov     [rbp+210h+var_C6], r12w
0x18001117e  mov     rcx, [rsp+310h+var_298]
0x180011183  lea     r8, [rbp+210h+var_1A0]
0x180011187  mov     [rbp+210h+var_109], 1
0x18001118e  lea     rdx, [rbp+210h+var_120]
0x180011195  mov     [rbp+210h+var_120], 0FFFFF800h
0x18001119f  mov     r9b, 9
0x1800111a2  mov     rax, [rcx]
0x1800111a5  mov     rax, [rax+88h]
0x1800111ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111b1  test    al, al
0x1800111b3  jnz     loc_180011255
0x1800111b9  mov     rcx, [rbp+210h+ho]; ho
0x1800111c0  mov     edx, 1
0x1800111c5  or      [rbx], dx
0x1800111c8  movups  xmm0, xmmword ptr [rdi]
0x1800111cb  movdqu  xmmword ptr [r14], xmm0
0x1800111d0  movzx   eax, word ptr [rbx]
0x1800111d3  mov     [r14+18h], ax
0x1800111d8  test    rcx, rcx
0x1800111db  jnz     short loc_180011205
0x1800111dd  mov     rcx, [rsp+310h+var_298]
0x1800111e2  test    rcx, rcx
0x1800111e5  jz      loc_18001108C
0x1800111eb  mov     rax, [rcx]
0x1800111ee  mov     rax, [rax]
0x1800111f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111f6  jmp     loc_18001108C
0x1800111fb  call    ?GetScreenDC@CW32System@@SAPEAUHDC__@@XZ; CW32System::GetScreenDC(void)
0x180011200  jmp     loc_1800110E0
0x180011205  cmp     byte ptr [rbp+210h+var_12C], r12b
0x18001120c  jz      loc_1800115C1
0x180011212  mov     rax, [rcx]
0x180011215  mov     rax, [rax+10h]
0x180011219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001121e  mov     rcx, [rbp+210h+ho+8]
0x180011225  test    rcx, rcx
0x180011228  jz      short loc_180011236
0x18001122a  mov     rax, [rcx]
0x18001122d  mov     rax, [rax+10h]
0x180011231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011236  xorps   xmm0, xmm0
0x180011239  mov     edx, 1
0x18001123e  movdqa  xmmword ptr [rbp+210h+ho], xmm0
0x180011246  jmp     short loc_1800111DD
0x180011248  mov     [rbp+210h+var_104], r12w
0x180011250  jmp     loc_18001117E
0x180011255  xor     edx, edx; Val
0x180011257  mov     [rbp+210h+var_1C8], r12
0x18001125b  lea     rax, [rsp+310h+var_298]
0x180011260  mov     [rbp+210h+var_1C0], r12
0x180011264  lea     rcx, [rbp+210h+var_228]; void *
0x180011268  mov     [rbp+210h+var_230], rax
0x18001126c  mov     [rbp+210h+var_1B8], r12d
0x180011270  lea     r8d, [rdx+5Ch]; Size
0x180011274  mov     [rbp+210h+var_1B4], r12w
0x180011279  mov     [rbp+210h+var_1B2], r12b
0x18001127d  call    memset_0
0x180011282  mov     rax, [rbp+210h+var_230]
0x180011286  lea     r8, [rbp+210h+var_228]
0x18001128a  mov     [rbp+210h+var_1B0], r12b
0x18001128e  lea     rdx, [rbp+210h+var_1A0]
0x180011292  mov     rcx, [rax]
0x180011295  mov     rax, [rcx]
0x180011298  mov     rax, [rax+180h]
0x18001129f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112a4  mov     [rbp+210h+var_1B0], al
0x1800112a7  test    al, al
0x1800112a9  jz      loc_180011596
0x1800112af  mov     rcx, [rsp+310h+var_298]
0x1800112b4  lea     r8, [rbp+210h+var_90]
0x1800112bb  mov     [rsp+310h+var_2B0], r12b
0x1800112c0  mov     r13d, 20h ; ' '
0x1800112c6  mov     [rsp+310h+var_2AF], r12b
0x1800112cb  mov     edx, r13d
0x1800112ce  mov     [rbp+210h+var_90], r12w
0x1800112d6  mov     rax, [rcx]
0x1800112d9  mov     rax, [rax+0A0h]
0x1800112e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112e5  lea     r8, [rbp+210h+var_104]
0x1800112ec  lea     r10, [rbp+210h+var_90]
0x1800112f3  lea     r11d, [r13-1Eh]
0x1800112f7  movzx   edx, word ptr [r10]
0x1800112fb  cmp     dx, 5Ah ; 'Z'
0x1800112ff  jbe     loc_1800115AD
0x180011305  movzx   ecx, word ptr [r8]
0x180011309  lea     eax, [rcx-41h]
0x18001130c  cmp     ax, 19h
0x180011310  jbe     loc_180011731
0x180011316  movzx   r9d, dx
0x18001131a  movzx   eax, cx
0x18001131d  sub     r9d, eax
0x180011320  jnz     short loc_18001132D
0x180011322  add     r10, r11
0x180011325  add     r8, r11
0x180011328  test    cx, cx
0x18001132b  jnz     short loc_1800112F7
0x18001132d  mov     r13, [rsp+310h+var_2A8]
0x180011332  test    r9d, r9d
0x180011335  jz      loc_1800116C5
0x18001133b  lea     rax, [rsp+310h+var_2A8]
0x180011340  mov     [rsp+310h+var_2A8], r12
0x180011345  mov     [rsp+310h+var_2E0], rax; unsigned __int64 *
0x18001134a  lea     rcx, [rbp+210h+var_90]; unsigned __int16 *
0x180011351  mov     [rsp+310h+var_2E8], r15b; bool
0x180011356  xor     r9d, r9d; enum CharLevel *
0x180011359  xor     r8d, r8d; unsigned __int8
0x18001135c  mov     [rsp+310h+var_2F0], r12b; bool
0x180011361  mov     edx, r11d; int
0x180011364  call    ?GetCharFlagsHelper@CCharFlags@@SA_KPEBGJEPEAW4CharLevel@@_N2PEA_K@Z; CCharFlags::GetCharFlagsHelper(ushort const *,long,uchar,CharLevel *,bool,bool,unsigned __int64 *)
0x180011369  test    rax, 0F00000h
0x18001136f  jnz     loc_18001173A
0x180011375  mov     eax, 2
0x18001137a  or      [rbx], ax
0x18001137d  cmp     esi, 46h ; 'F'
0x180011380  jl      loc_18001170F
0x180011386  mov     rcx, [rsp+310h+var_298]
0x18001138b  xor     r9d, r9d
0x18001138e  xor     r8d, r8d
0x180011391  mov     edx, 4854414Dh
0x180011396  mov     rax, [rcx]
0x180011399  mov     rax, [rax+98h]
0x1800113a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113a5  cmp     eax, 0FFFFFFFFh
0x1800113a8  jnz     loc_18001171D
0x1800113ae  cmp     esi, 46h ; 'F'
0x1800113b1  jge     loc_180011690
0x1800113b7  cmp     esi, 31h ; '1'
0x1800113ba  jz      loc_1800117B0
0x1800113c0  mov     rcx, [rsp+310h+var_298]
0x1800113c5  lea     rdx, [rbp+210h+var_278]
0x1800113c9  xorps   xmm0, xmm0
0x1800113cc  mov     [rsp+310h+var_2F0], 1
0x1800113d1  movups  [rbp+210h+var_278], xmm0
0x1800113d5  or      r9d, 0FFFFFFFFh
0x1800113d9  xor     r8d, r8d
0x1800113dc  movups  [rbp+210h+var_278+0Ch], xmm0
0x1800113e0  mov     rax, [rcx]
0x1800113e3  mov     rax, [rax+0C0h]
0x1800113ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113ef  mov     al, [rbp+210h+var_260]
0x1800113f2  mov     ecx, 0FFFBh
0x1800113f7  and     al, 1
0x1800113f9  movzx   r8d, al
0x1800113fd  movzx   eax, word ptr [rbx]
0x180011400  and     ax, cx
0x180011403  shl     r8w, 2
0x180011408  or      r8w, ax
0x18001140c  lea     eax, [rcx-4]
0x18001140f  and     r8w, ax
0x180011413  mov     al, [rbp+210h+var_25F]
0x180011416  and     al, 1
0x180011418  movzx   ecx, al
0x18001141b  shl     cx, 3
0x18001141f  or      r8w, cx
0x180011423  mov     [rbx], r8w
0x180011427  test    r8b, 2
0x18001142b  jz      loc_1800115D2
0x180011431  cmp     esi, 46h ; 'F'
0x180011434  jl      loc_18001161E
0x18001143a  mov     rcx, [rsp+310h+var_298]
0x18001143f  lea     rdx, [rbp+210h+var_258]
0x180011443  xor     eax, eax
0x180011445  xorps   xmm0, xmm0
0x180011448  mov     [rbp+210h+var_238], eax
0x18001144b  movups  [rbp+210h+var_258], xmm0
0x18001144f  movups  [rbp+210h+var_248], xmm0
0x180011453  mov     rax, [rcx]
0x180011456  mov     rax, [rax+0C8h]
0x18001145d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011462  test    al, al
0x180011464  jz      loc_180011596
0x18001146a  mov     edx, dword ptr [rbp+210h+var_248]
0x18001146d  neg     edx
0x18001146f  cmovs   edx, dword ptr [rbp+210h+var_248]
0x180011473  test    byte ptr [rbp+210h+var_258], 80h
0x180011477  jnz     loc_1800117C2
0x18001147d  cmp     [rsp+310h+var_2B0], r12b
0x180011482  jnz     loc_1800117C2
0x180011488  mov     ecx, dword ptr [rbp+210h+var_258+8]
0x18001148b  add     ecx, edx
0x18001148d  add     ecx, ecx
0x18001148f  cmp     dword ptr [rbp+210h+var_278+4], ecx
0x180011492  ja      loc_1800117C2
0x180011498  mov     ecx, dword ptr [rbp+210h+var_258+0Ch]
0x18001149b  movzx   r8d, word ptr [rbx]
0x18001149f  neg     ecx
0x1800114a1  cmovs   ecx, dword ptr [rbp+210h+var_258+0Ch]
0x1800114a5  lea     eax, [rcx+rcx*2]
0x1800114a8  cmp     dword ptr [rbp+210h+var_278+8], eax
0x1800114ab  ja      loc_1800117CF
0x1800114b1  cmp     [rsp+310h+var_2AF], r12b
0x1800114b6  jnz     loc_1800117CF
0x1800114bc  movzx   eax, word ptr [rbp+210h+var_258+8]
0x1800114c0  mov     [r14+12h], ax
0x1800114c5  mov     [r14+14h], cx
0x1800114ca  mov     [r14+16h], dx
0x1800114cf  cmp     esi, 46h ; 'F'
0x1800114d2  jl      loc_180011596
0x1800114d8  mov     eax, [rdi]
0x1800114da  test    rax, 0F00000h
0x1800114e0  jnz     loc_180011596
0x1800114e6  test    r15b, r15b
0x1800114e9  jnz     loc_180011596
0x1800114ef  xor     ecx, ecx; bool
0x1800114f1  mov     dword ptr [rsp+310h+var_2A8], r12d
0x1800114f6  mov     [rsp+310h+var_2A0], r12d
0x1800114fb  mov     [rbp+210h+var_280], r12
0x1800114ff  call    ?GetXScribe@@YAPEBVCXScribe@@_N@Z; GetXScribe(bool)
0x180011504  test    rax, rax
0x180011507  jz      loc_180011596
0x18001150d  movzx   ecx, byte ptr [rax+12h]
0x180011511  lea     r8, aFinal; "final"
0x180011518  movzx   eax, word ptr [rsp+310h+var_2A0]
0x18001151d  mov     edx, 0FC00h
0x180011522  and     ax, dx
0x180011525  mov     [rsp+310h+var_2C0], r12b
0x18001152a  or      cx, ax
  ... truncated ...
```
