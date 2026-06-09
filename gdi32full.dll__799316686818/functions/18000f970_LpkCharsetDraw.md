# LpkCharsetDraw

- ea: `0x18000f970`
- end: `0x18000fff4`
- name: `LpkCharsetDraw`
- size: `1668`
- prototype: `__int64 __usercall@<rax>(HDC hdc@<rcx>, char, int iY, __int64, int cString, int, int, int)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, installer_update`

## callers

- `0x18000f6f0`

## callees

- `0x18000d6c0`
- `0x18000e8b4`
- `0x18000f630`
- `0x18000f970`
- `0x180010000`
- `0x180010140`
- `0x180010210`
- `0x1800102f0`
- `0x1800104e0`
- `0x180010690`
- `0x180010790`
- `0x180010870`
- `0x180010950`
- `0x180010b70`
- `0x180010d60`
- `0x180010e60`
- `0x180011050`
- `0x180011770`
- `0x180015aa0`
- `0x180016900`
- `0x180017770`
- `0x180026640`
- `0x180079350`
- `0x18007ac50`
- `0x18007ba00`

## import_xrefs

- `GDI32!SelectObject` at `0x18000ff7a`
- `GDI32!SelectObject` at `0x18000ffde`
- `GDI32!SelectObject` at `0x18000ff7a`
- `GDI32!SelectObject` at `0x18000ffde`
- `GDI32!GdiSetLastError` at `0x18000ffa8`
- `GDI32!GdiSetLastError` at `0x18000ffa8`
- `GDI32!DeleteObject` at `0x18000ffe9`
- `GDI32!DeleteObject` at `0x18000ffe9`
- `win32u!NtGdiExtGetObjectW` at `0x18000fed3`
- `win32u!NtGdiExtGetObjectW` at `0x18000fed3`
- `win32u!NtGdiAnyLinkedFonts` at `0x18000fcba`
- `win32u!NtGdiAnyLinkedFonts` at `0x18000fcba`

## pseudocode

```c
__int64 __fastcall LpkCharsetDraw(
        HDC hdc,
        int a2,
        __int64 a3,
        __int64 a4,
        char a5,
        int iY,
        void *a7,
        int cString,
        int a9,
        int a10,
        int a11)
{
  int v12; // r14d
  int v13; // r12d
  LONG cx; // ebx
  LONG x; // edi
  LONG v16; // esi
  LONG cy; // r13d
  float v18; // xmm8_4
  float v19; // xmm6_4
  int v20; // eax
  double v21; // xmm7_8
  int v22; // edx
  int v23; // r14d
  DWORD ObjectType; // eax
  unsigned int v26; // ecx
  DWORD v27; // r8d
  SCRIPT_TABDEF *v28; // rax
  int v29; // edx
  int v30; // r12d
  int v31; // r12d
  int v32; // eax
  int v33; // r12d
  UINT TextAlign; // eax
  int v35; // eax
  DWORD dwFlags; // r12d
  int v37; // eax
  float v38; // xmm8_4
  int v39; // r14d
  double v40; // xmm0_8
  HCOLORSPACE DCObject; // rax
  unsigned int v42; // ecx
  int ObjectW; // eax
  void *FontIndirectWImpl; // rax
  SCRIPT_STATE pss; // [rsp+70h] [rbp-90h] BYREF
  SCRIPT_CONTROL psc; // [rsp+74h] [rbp-8Ch] BYREF
  struct tagSIZE sz; // [rsp+78h] [rbp-88h] BYREF
  int iX; // [rsp+80h] [rbp-80h]
  int iMode; // [rsp+84h] [rbp-7Ch]
  struct tagSIZE size; // [rsp+88h] [rbp-78h] BYREF
  struct tagPOINT point; // [rsp+90h] [rbp-70h] BYREF
  struct tagPOINT v52; // [rsp+98h] [rbp-68h] BYREF
  SCRIPT_STRING_ANALYSIS ssa; // [rsp+A0h] [rbp-60h] BYREF
  HGDIOBJ h; // [rsp+A8h] [rbp-58h]
  HGDIOBJ ho; // [rsp+B0h] [rbp-50h]
  __int128 v56; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v57; // [rsp+C8h] [rbp-38h]
  SCRIPT_TABDEF *pTabdef; // [rsp+D0h] [rbp-30h]
  void *pString; // [rsp+D8h] [rbp-28h]
  _OWORD v60[6]; // [rsp+E0h] [rbp-20h] BYREF

  pString = a7;
  iX = a2;
  ssa = 0;
  v56 = 0;
  v57 = 0;
  if ( cString > 0 )
  {
    v12 = a10;
    v13 = a10 & 0x40;
    if ( (a10 & 0x40) != 0 )
    {
      *(_QWORD *)&v56 = 0x400000001LL;
      *((_QWORD *)&v56 + 1) = &a5;
      LODWORD(v57) = 0;
    }
    cx = 0;
    size = 0;
    sz = 0;
    x = 0;
    point = 0;
    v16 = 0;
    v52 = 0;
    h = 0;
    ho = 0;
    iMode = GetMapMode(hdc);
    if ( iMode != 7 )
    {
      cy = size.cy;
      v19 = 0.0;
      v21 = DOUBLE_0_5;
      goto LABEL_20;
    }
    memset(v60, 0, 92);
    if ( GetWindowExtEx(hdc, &size) )
    {
      if ( GetViewportExtEx(hdc, &sz) )
      {
        if ( GetWindowOrgEx(hdc, &point) )
        {
          if ( GetViewportOrgEx(hdc, &v52) )
          {
            cx = size.cx;
            if ( size.cx )
            {
              cy = size.cy;
              if ( size.cy )
              {
                v18 = (float)sz.cy;
                v19 = (float)sz.cx / (float)size.cx;
                v20 = SetMapMode(hdc, 1);
                x = point.x;
                v16 = v52.x;
                v21 = DOUBLE_0_5;
                if ( !v20 )
                  goto LABEL_12;
                if ( !SetWindowOrgEx(hdc, 0, 0, 0) )
                  goto LABEL_12;
                v38 = v18 / (float)cy;
                v39 = (int)floor((float)((float)((float)((float)(iY - point.y) * v38) + (float)v52.y) - (float)iY) + 0.5);
                v40 = floor((float)((float)((float)((float)(iX - x) * v19) + (float)v16) - (float)iX) + 0.5);
                if ( !SetViewportOrgEx(hdc, (int)v40, v39, 0) )
                  goto LABEL_12;
                DCObject = (HCOLORSPACE)GetDCObject(hdc, 655360);
                if ( !DCObject )
                  goto LABEL_12;
                v42 = (unsigned int)DCObject & 0x7F0000;
                if ( ((unsigned int)DCObject & 0x7F0000) > 0x210000 )
                {
                  if ( v42 != 4587520 && v42 != 2490368 )
                    goto LABEL_58;
                }
                else if ( v42 != 2162688 )
                {
                  if ( v42 == 589824 )
                  {
                    ObjectW = GetLogColorSpaceW(DCObject, (LPLOGCOLORSPACEW)v60, 0x5Cu) ? 0x24C : 0;
                    goto LABEL_59;
                  }
                  if ( v42 != 0x10000 )
                  {
                    if ( v42 == 655360 )
                    {
                      ObjectW = NtGdiExtGetObjectW(DCObject, 92, v60);
LABEL_59:
                      if ( ObjectW )
                      {
                        LODWORD(v60[0]) = (int)floor(
                                                 (float)(COERCE_FLOAT(LODWORD(v38) & _xmm) * (float)SLODWORD(v60[0]))
                                               + 0.5);
                        DWORD1(v60[0]) = (int)floor(
                                                (float)(COERCE_FLOAT(LODWORD(v19) & _xmm) * (float)SDWORD1(v60[0]))
                                              + 0.5);
                        FontIndirectWImpl = (void *)CreateFontIndirectWImpl(v60);
                        ho = FontIndirectWImpl;
                        if ( FontIndirectWImpl )
                        {
                          h = SelectObject(hdc, FontIndirectWImpl);
                          if ( h )
                          {
                            v12 = a10;
LABEL_20:
                            ObjectType = GetObjectType(hdc);
                            v26 = 0;
                            v27 = ObjectType;
                            v28 = (SCRIPT_TABDEF *)&v56;
                            v29 = 2048;
                            if ( !v13 )
                              v28 = 0;
                            pTabdef = v28;
                            if ( (v12 & 0x800) == 0 )
                            {
                              v26 = (v12 & 0x200000 | 0x40000u) >> 8;
                              if ( (v12 & 0x100000) != 0 )
                                v26 = 0x2000;
                            }
                            v30 = v26 | (v13 != 0 ? 2 : 0);
                            if ( ((v27 - 4) & 0xFFFFFFF7) != 0 )
                              v29 = 0;
                            v31 = v29 | v30;
                            if ( a11 == -1 || (unsigned int)GdiIsPlayMetafileDC(hdc) )
                              v32 = 32;
                            else
                              v32 = 0x8000000;
                            v33 = v32 | v31;
                            if ( (v12 & 0x20000) != 0
                              || (TextAlign = GetTextAlign(hdc), (TextAlign & 0x100) != 0) && TextAlign != -1 )
                            {
                              v35 = 384;
                            }
                            else
                            {
                              v35 = 128;
                            }
                            dwFlags = v35 | v33;
                            psc = 0;
                            pss = 0;
                            CheckUpdateNLSScriptSettings();
                            ScriptApplyDigitSubstitution(&g_DigitSubstitute, &psc, &pss);
                            v37 = g_iUseFontLinking;
                            if ( g_iUseFontLinking == -1 )
                            {
                              v37 = NtGdiAnyLinkedFonts();
                              g_iUseFontLinking = v37;
                            }
                            if ( v37 )
                              dwFlags |= 0x1000u;
                            psc = (SCRIPT_CONTROL)(*(_DWORD *)&psc | 0x1800000);
                            if ( ScriptStringAnalyse(
                                   hdc,
                                   pString,
                                   cString,
                                   0,
                                   -1,
                                   dwFlags,
                                   0,
                                   &psc,
                                   &pss,
                                   0,
                                   pTabdef,
                                   0,
                                   &ssa) < 0 )
                            {
                              v23 = 0;
                            }
                            else
                            {
                              v23 = *((_DWORD *)ssa + 106);
                              if ( a9 && (a10 & 0x400) == 0 )
                                ScriptStringOut(ssa, iX, iY, 0, 0, 0, 0, 0);
                              ScriptStringFree(&ssa);
                            }
                            v22 = iMode;
                            if ( iMode != 7 )
                              return (unsigned int)v23;
                            goto LABEL_13;
                          }
                        }
                      }
LABEL_12:
                      v22 = iMode;
                      v23 = 0;
LABEL_13:
                      SetMapMode(hdc, v22);
                      SetWindowOrgEx(hdc, x, point.y, 0);
                      SetViewportOrgEx(hdc, v16, v52.y, 0);
                      SetWindowExtEx(hdc, cx, cy, &size);
                      SetViewportExtEx(hdc, sz.cx, sz.cy, &sz);
                      if ( h )
                        SelectObject(hdc, h);
                      if ( ho )
                        DeleteObject(ho);
                      return (unsigned int)(int)floor((float)((float)v23 / v19) + v21);
                    }
LABEL_58:
                    ObjectW = cjGetNonFontObject(DCObject, 92, v60);
                    goto LABEL_59;
                  }
                }
                GdiSetLastError(6);
                goto LABEL_12;
              }
            }
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000f970  mov     rax, rsp
0x18000f973  mov     [rax+18h], rbx
0x18000f977  push    rbp
0x18000f978  push    rsi
0x18000f979  push    rdi
0x18000f97a  push    r12
0x18000f97c  push    r13
0x18000f97e  push    r14
0x18000f980  push    r15
0x18000f982  lea     rbp, [rsp-80h]
0x18000f987  sub     rsp, 180h
0x18000f98e  movaps  xmmword ptr [rax-48h], xmm6
0x18000f992  movaps  xmmword ptr [rax-58h], xmm7
0x18000f996  movaps  xmmword ptr [rax-68h], xmm8
0x18000f99b  mov     rax, cs:__security_cookie
0x18000f9a2  xor     rax, rsp
0x18000f9a5  mov     [rbp+0B0h+var_70], rax
0x18000f9a9  mov     rax, [rbp+0B0h+arg_30]
0x18000f9b0  mov     r15, rcx
0x18000f9b3  xor     ecx, ecx
0x18000f9b5  mov     [rbp+0B0h+pString], rax
0x18000f9b9  xor     eax, eax
0x18000f9bb  mov     [rbp+0B0h+iX], edx
0x18000f9be  xorps   xmm0, xmm0
0x18000f9c1  mov     [rbp+0B0h+ssa], rcx
0x18000f9c5  movups  [rbp+0B0h+var_F8], xmm0
0x18000f9c9  mov     [rbp+0B0h+var_E8], rax
0x18000f9cd  cmp     [rbp+0B0h+cString], eax
0x18000f9d3  jle     loc_18000FDC2
0x18000f9d9  mov     r14d, [rbp+0B0h+arg_48]
0x18000f9e0  mov     r12d, r14d
0x18000f9e3  and     r12d, 40h
0x18000f9e7  jz      short loc_18000FA05
0x18000f9e9  lea     rax, [rbp+0B0h+arg_20]
0x18000f9f0  mov     dword ptr [rbp+0B0h+var_F8], 1
0x18000f9f7  mov     qword ptr [rbp+0B0h+var_F8+8], rax
0x18000f9fb  mov     dword ptr [rbp+0B0h+var_E8], ecx
0x18000f9fe  mov     dword ptr [rbp+0B0h+var_F8+4], 4
0x18000fa05  mov     rbx, rcx
0x18000fa08  mov     qword ptr [rbp+0B0h+size.cx], rcx
0x18000fa0c  mov     qword ptr [rsp+1B0h+sz.cx], rcx
0x18000fa11  mov     rdi, rcx
0x18000fa14  mov     qword ptr [rbp+0B0h+point.x], rcx
0x18000fa18  mov     rsi, rcx
0x18000fa1b  mov     qword ptr [rbp+0B0h+var_118.x], rcx
0x18000fa1f  mov     [rbp+0B0h+h], rcx
0x18000fa23  mov     [rbp+0B0h+ho], rcx
0x18000fa27  mov     rcx, r15; hdc
0x18000fa2a  call    GetMapMode
0x18000fa2f  mov     [rbp+0B0h+iMode], eax
0x18000fa32  cmp     eax, 7
0x18000fa35  jnz     loc_18000FBCB
0x18000fa3b  xorps   xmm0, xmm0
0x18000fa3e  lea     rdx, [rbp+0B0h+size]; lpsize
0x18000fa42  movups  xmmword ptr [rbp+0B0h+var_90], xmm0
0x18000fa46  mov     rcx, r15; hdc
0x18000fa49  movups  xmmword ptr [rbp+0B0h+var_90+0Ch], xmm0
0x18000fa4d  movups  [rbp+0B0h+var_D0], xmm0
0x18000fa51  movups  [rbp+0B0h+var_C0], xmm0
0x18000fa55  movups  [rbp+0B0h+var_B0], xmm0
0x18000fa59  movups  [rbp+0B0h+var_A0], xmm0
0x18000fa5d  call    GetWindowExtEx
0x18000fa62  test    eax, eax
0x18000fa64  jz      loc_18000FDC2
0x18000fa6a  lea     rdx, [rsp+1B0h+sz]; lpsize
0x18000fa6f  mov     rcx, r15; hdc
0x18000fa72  call    GetViewportExtEx
0x18000fa77  test    eax, eax
0x18000fa79  jz      loc_18000FDC2
0x18000fa7f  lea     rdx, [rbp+0B0h+point]; lppoint
0x18000fa83  mov     rcx, r15; hdc
0x18000fa86  call    GetWindowOrgEx
0x18000fa8b  test    eax, eax
0x18000fa8d  jz      loc_18000FDC2
0x18000fa93  lea     rdx, [rbp+0B0h+var_118]; lppoint
0x18000fa97  mov     rcx, r15; hdc
0x18000fa9a  call    GetViewportOrgEx
0x18000fa9f  test    eax, eax
0x18000faa1  jz      loc_18000FDC2
0x18000faa7  mov     rbx, qword ptr [rbp+0B0h+size.cx]
0x18000faab  test    ebx, ebx
0x18000faad  jz      loc_18000FDC2
0x18000fab3  mov     r13d, [rbp+0B0h+size.cy]
0x18000fab7  test    r13d, r13d
0x18000faba  jz      loc_18000FDC2
0x18000fac0  movd    xmm6, [rsp+1B0h+sz.cx]
0x18000fac6  mov     edx, 1; iMode
0x18000facb  movd    xmm8, [rsp+1B0h+sz.cy]
0x18000fad2  mov     rcx, r15; hdc
0x18000fad5  movd    xmm0, ebx
0x18000fad9  cvtdq2ps xmm6, xmm6
0x18000fadc  cvtdq2ps xmm0, xmm0
0x18000fadf  cvtdq2ps xmm8, xmm8
0x18000fae3  divss   xmm6, xmm0
0x18000fae7  call    SetMapMode
0x18000faec  mov     rdi, qword ptr [rbp+0B0h+point.x]
0x18000faf0  mov     rsi, qword ptr [rbp+0B0h+var_118.x]
0x18000faf4  movsd   xmm7, cs:__real@3fe0000000000000
0x18000fafc  test    eax, eax
0x18000fafe  jnz     loc_18000FDC9
0x18000fb04  mov     edx, [rbp+0B0h+iMode]; iMode
0x18000fb07  xor     r14d, r14d
0x18000fb0a  mov     rcx, r15; hdc
0x18000fb0d  call    SetMapMode
0x18000fb12  mov     r8d, [rbp+0B0h+point.y]; y
0x18000fb16  xor     r9d, r9d; lppt
0x18000fb19  mov     edx, edi; x
0x18000fb1b  mov     rcx, r15; hdc
0x18000fb1e  call    SetWindowOrgEx
0x18000fb23  mov     r8d, [rbp+0B0h+var_118.y]; y
0x18000fb27  xor     r9d, r9d; lppt
0x18000fb2a  mov     edx, esi; x
0x18000fb2c  mov     rcx, r15; hdc
0x18000fb2f  call    SetViewportOrgEx
0x18000fb34  lea     r9, [rbp+0B0h+size]; lpsz
0x18000fb38  mov     r8d, r13d; y
0x18000fb3b  mov     edx, ebx; x
0x18000fb3d  mov     rcx, r15; hdc
0x18000fb40  call    SetWindowExtEx
0x18000fb45  mov     r8d, [rsp+1B0h+sz.cy]; y
0x18000fb4a  lea     r9, [rsp+1B0h+sz]; lpsz
0x18000fb4f  mov     edx, [rsp+1B0h+sz.cx]; x
0x18000fb53  mov     rcx, r15; hdc
0x18000fb56  call    SetViewportExtEx
0x18000fb5b  mov     rdx, [rbp+0B0h+h]; h
0x18000fb5f  test    rdx, rdx
0x18000fb62  jnz     loc_18000FFDB
0x18000fb68  mov     rcx, [rbp+0B0h+ho]; ho
0x18000fb6c  test    rcx, rcx
0x18000fb6f  jnz     loc_18000FFE9
0x18000fb75  movd    xmm0, r14d
0x18000fb7a  cvtdq2ps xmm0, xmm0
0x18000fb7d  divss   xmm0, xmm6
0x18000fb81  cvtps2pd xmm0, xmm0
0x18000fb84  addsd   xmm0, xmm7; X
0x18000fb88  call    floor
0x18000fb8d  cvttsd2si r14d, xmm0
0x18000fb92  mov     eax, r14d
0x18000fb95  mov     rcx, [rbp+0B0h+var_70]
0x18000fb99  xor     rcx, rsp; StackCookie
0x18000fb9c  call    __security_check_cookie
0x18000fba1  lea     r11, [rsp+1B0h+var_30]
0x18000fba9  mov     rbx, [r11+50h]
0x18000fbad  movaps  xmm6, xmmword ptr [r11-10h]
0x18000fbb2  movaps  xmm7, xmmword ptr [r11-20h]
0x18000fbb7  movaps  xmm8, xmmword ptr [r11-30h]
0x18000fbbc  mov     rsp, r11
0x18000fbbf  pop     r15
0x18000fbc1  pop     r14
0x18000fbc3  pop     r13
0x18000fbc5  pop     r12
0x18000fbc7  pop     rdi
0x18000fbc8  pop     rsi
0x18000fbc9  pop     rbp
0x18000fbca  retn
0x18000fbcb  mov     r13d, [rbp+0B0h+size.cy]
0x18000fbcf  xorps   xmm6, xmm6
0x18000fbd2  movsd   xmm7, cs:__real@3fe0000000000000
0x18000fbda  mov     rcx, r15; h
0x18000fbdd  call    GetObjectType
0x18000fbe2  xor     ecx, ecx
0x18000fbe4  mov     r8d, eax
0x18000fbe7  test    r12d, r12d
0x18000fbea  lea     rax, [rbp+0B0h+var_F8]
0x18000fbee  mov     edx, 800h
0x18000fbf3  cmovz   rax, rcx
0x18000fbf7  mov     [rbp+0B0h+var_E0], rax
0x18000fbfb  test    edx, r14d
0x18000fbfe  jnz     short loc_18000FC1D
0x18000fc00  mov     ecx, r14d
0x18000fc03  mov     eax, 2000h
0x18000fc08  and     ecx, 200000h
0x18000fc0e  bts     ecx, 12h
0x18000fc12  shr     ecx, 8
0x18000fc15  bt      r14d, 14h
0x18000fc1a  cmovb   ecx, eax
0x18000fc1d  neg     r12d
0x18000fc20  lea     eax, [r8-4]
0x18000fc24  sbb     r12d, r12d
0x18000fc27  and     r12d, 2
0x18000fc2b  or      r12d, ecx
0x18000fc2e  xor     ecx, ecx
0x18000fc30  test    eax, 0FFFFFFF7h
0x18000fc35  cmovnz  edx, ecx
0x18000fc38  or      r12d, edx
0x18000fc3b  cmp     [rbp+0B0h+arg_50], 0FFFFFFFFh
0x18000fc42  jz      loc_18000FF99
0x18000fc48  mov     rcx, r15
0x18000fc4b  call    GdiIsPlayMetafileDC
0x18000fc50  test    eax, eax
0x18000fc52  jnz     loc_18000FF99
0x18000fc58  mov     eax, 8000000h
0x18000fc5d  or      r12d, eax
0x18000fc60  bt      r14d, 11h
0x18000fc65  jb      loc_18000FDB8
0x18000fc6b  mov     rcx, r15; hdc
0x18000fc6e  call    GetTextAlign
0x18000fc73  bt      eax, 8
0x18000fc77  jb      loc_18000FDAF
0x18000fc7d  mov     eax, 80h
0x18000fc82  or      r12d, eax
0x18000fc85  mov     dword ptr [rsp+1B0h+psc.uDefaultLanguage], 0
0x18000fc8d  xor     eax, eax
0x18000fc8f  mov     word ptr [rsp+1B0h+pss.uBidiLevel], ax
0x18000fc94  call    CheckUpdateNLSScriptSettings
0x18000fc99  lea     r8, [rsp+1B0h+pss]; pss
0x18000fc9e  lea     rdx, [rsp+1B0h+psc]; psc
0x18000fca3  lea     rcx, g_DigitSubstitute; psds
0x18000fcaa  call    ScriptApplyDigitSubstitution
0x18000fcaf  mov     eax, cs:g_iUseFontLinking
0x18000fcb5  cmp     eax, 0FFFFFFFFh
0x18000fcb8  jnz     short loc_18000FCC6
0x18000fcba  call    cs:__imp_NtGdiAnyLinkedFonts
0x18000fcc0  mov     cs:g_iUseFontLinking, eax
0x18000fcc6  test    eax, eax
0x18000fcc8  jz      short loc_18000FCCF
0x18000fcca  bts     r12d, 0Ch
0x18000fccf  mov     r8d, [rbp+0B0h+cString]; cString
0x18000fcd6  lea     rax, [rbp+0B0h+ssa]
0x18000fcda  mov     rdx, [rbp+0B0h+pString]; pString
0x18000fcde  xor     r9d, r9d; cGlyphs
0x18000fce1  or      dword ptr [rsp+1B0h+psc.uDefaultLanguage], 1800000h
0x18000fce9  mov     rcx, r15; hdc
0x18000fcec  mov     [rsp+1B0h+pssa], rax; pssa
0x18000fcf1  mov     rax, [rbp+0B0h+var_E0]
0x18000fcf5  mov     [rsp+1B0h+pbInClass], 0; pbInClass
0x18000fcfe  mov     [rsp+1B0h+pTabdef], rax; pTabdef
0x18000fd03  lea     rax, [rsp+1B0h+pss]
0x18000fd08  mov     [rsp+1B0h+piDx], 0; piDx
0x18000fd11  mov     [rsp+1B0h+psState], rax; psState
0x18000fd16  lea     rax, [rsp+1B0h+psc]
0x18000fd1b  mov     [rsp+1B0h+psControl], rax; psControl
0x18000fd20  mov     [rsp+1B0h+iReqWidth], 0; iReqWidth
0x18000fd28  mov     [rsp+1B0h+dwFlags], r12d; dwFlags
0x18000fd2d  mov     [rsp+1B0h+iCharset], 0FFFFFFFFh; iCharset
0x18000fd35  call    ScriptStringAnalyse
0x18000fd3a  test    eax, eax
0x18000fd3c  js      loc_18000FFD3
0x18000fd42  cmp     [rbp+0B0h+arg_40], 0
0x18000fd49  mov     rcx, [rbp+0B0h+ssa]; ssa
0x18000fd4d  mov     r14d, [rcx+1A8h]
0x18000fd54  jz      short loc_18000FD95
0x18000fd56  test    [rbp+0B0h+arg_48], 400h
0x18000fd60  jnz     short loc_18000FD95
0x18000fd62  mov     r8d, [rbp+0B0h+iY]; iY
0x18000fd69  xor     r9d, r9d; uOptions
0x18000fd6c  mov     edx, [rbp+0B0h+iX]; iX
0x18000fd6f  mov     dword ptr [rsp+1B0h+psControl], 0; fDisabled
0x18000fd77  mov     [rsp+1B0h+iReqWidth], 0; iMaxSel
0x18000fd7f  mov     [rsp+1B0h+dwFlags], 0; iMinSel
0x18000fd87  mov     qword ptr [rsp+1B0h+iCharset], 0; prc
0x18000fd90  call    ScriptStringOut
0x18000fd95  lea     rcx, [rbp+0B0h+ssa]; pssa
0x18000fd99  call    ScriptStringFree
0x18000fd9e  mov     edx, [rbp+0B0h+iMode]
0x18000fda1  cmp     edx, 7
0x18000fda4  jnz     loc_18000FB92
0x18000fdaa  jmp     loc_18000FB0A
0x18000fdaf  cmp     eax, 0FFFFFFFFh
0x18000fdb2  jz      loc_18000FC7D
0x18000fdb8  mov     eax, 180h
0x18000fdbd  jmp     loc_18000FC82
0x18000fdc2  xor     eax, eax
0x18000fdc4  jmp     loc_18000FB95
0x18000fdc9  xor     r9d, r9d; lppt
0x18000fdcc  xor     r8d, r8d; y
0x18000fdcf  xor     edx, edx; x
0x18000fdd1  mov     rcx, r15; hdc
0x18000fdd4  call    SetWindowOrgEx
0x18000fdd9  test    eax, eax
0x18000fddb  jz      loc_18000FB04
0x18000fde1  mov     ecx, [rbp+0B0h+iY]
0x18000fde7  xorps   xmm0, xmm0
0x18000fdea  cvtsi2ss xmm0, r13d
0x18000fdef  mov     eax, ecx
0x18000fdf1  sub     eax, [rbp+0B0h+point.y]
0x18000fdf4  xorps   xmm2, xmm2
0x18000fdf7  xorps   xmm1, xmm1
0x18000fdfa  divss   xmm8, xmm0
0x18000fdff  cvtsi2ss xmm2, eax
0x18000fe03  xorps   xmm0, xmm0
0x18000fe06  cvtsi2ss xmm0, [rbp+0B0h+var_118.y]
0x18000fe0b  mulss   xmm2, xmm8
0x18000fe10  cvtsi2ss xmm1, ecx
0x18000fe14  addss   xmm2, xmm0
0x18000fe18  subss   xmm2, xmm1
0x18000fe1c  cvtps2pd xmm0, xmm2
0x18000fe1f  addsd   xmm0, xmm7; X
0x18000fe23  call    floor
0x18000fe28  mov     ecx, [rbp+0B0h+iX]
0x18000fe2b  xorps   xmm2, xmm2
0x18000fe2e  cvttsd2si r14d, xmm0
0x18000fe33  mov     eax, ecx
0x18000fe35  sub     eax, edi
0x18000fe37  xorps   xmm0, xmm0
0x18000fe3a  xorps   xmm1, xmm1
0x18000fe3d  cvtsi2ss xmm2, eax
0x18000fe41  cvtsi2ss xmm0, esi
0x18000fe45  mulss   xmm2, xmm6
0x18000fe49  cvtsi2ss xmm1, ecx
  ... truncated ...
```
