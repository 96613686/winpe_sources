# LpkCharsetDraw

- ea: `0x180018070`
- end: `0x180018719`
- name: `LpkCharsetDraw`
- size: `1705`
- prototype: `__int64 __usercall@<rax>(HDC hdc@<rcx>, char, int iY, __int64, int cString, int, int, int)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, installer_update`

## callers

- `0x180017df0`

## callees

- `0x180004f34`
- `0x180006a28`
- `0x18000e550`
- `0x180018070`
- `0x180018720`
- `0x180018860`
- `0x180018940`
- `0x180018a20`
- `0x180018c30`
- `0x180018df0`
- `0x180018f00`
- `0x180018fe0`
- `0x1800190c0`
- `0x180019310`
- `0x180019520`
- `0x180019630`
- `0x180019840`
- `0x180019b90`
- `0x180022b20`
- `0x180023a20`
- `0x1800242f0`
- `0x18002f680`
- `0x18007def0`
- `0x18007f800`
- `0x1800805e0`

## import_xrefs

- `GDI32!SelectObject` at `0x180018687`
- `GDI32!SelectObject` at `0x1800186f7`
- `GDI32!SelectObject` at `0x180018687`
- `GDI32!SelectObject` at `0x1800186f7`
- `GDI32!GdiSetLastError` at `0x1800186bb`
- `GDI32!GdiSetLastError` at `0x1800186bb`
- `GDI32!DeleteObject` at `0x180018708`
- `GDI32!DeleteObject` at `0x180018708`
- `win32u!NtGdiExtGetObjectW` at `0x1800185da`
- `win32u!NtGdiExtGetObjectW` at `0x1800185da`
- `win32u!NtGdiAnyLinkedFonts` at `0x1800183bb`
- `win32u!NtGdiAnyLinkedFonts` at `0x1800183bb`

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
0x180018070  mov     rax, rsp
0x180018073  mov     [rax+18h], rbx
0x180018077  push    rbp
0x180018078  push    rsi
0x180018079  push    rdi
0x18001807a  push    r12
0x18001807c  push    r13
0x18001807e  push    r14
0x180018080  push    r15
0x180018082  lea     rbp, [rsp-80h]
0x180018087  sub     rsp, 180h
0x18001808e  movaps  xmmword ptr [rax-48h], xmm6
0x180018092  movaps  xmmword ptr [rax-58h], xmm7
0x180018096  movaps  xmmword ptr [rax-68h], xmm8
0x18001809b  mov     rax, cs:__security_cookie
0x1800180a2  xor     rax, rsp
0x1800180a5  mov     [rbp+0B0h+var_70], rax
0x1800180a9  mov     rax, [rbp+0B0h+arg_30]
0x1800180b0  mov     r15, rcx
0x1800180b3  xor     ecx, ecx
0x1800180b5  mov     [rbp+0B0h+pString], rax
0x1800180b9  xor     eax, eax
0x1800180bb  mov     [rbp+0B0h+iX], edx
0x1800180be  xorps   xmm0, xmm0
0x1800180c1  mov     [rbp+0B0h+ssa], rcx
0x1800180c5  movups  [rbp+0B0h+var_F8], xmm0
0x1800180c9  mov     [rbp+0B0h+var_E8], rax
0x1800180cd  cmp     [rbp+0B0h+cString], eax
0x1800180d3  jle     loc_1800184C9
0x1800180d9  mov     r14d, [rbp+0B0h+arg_48]
0x1800180e0  mov     r12d, r14d
0x1800180e3  and     r12d, 40h
0x1800180e7  jz      short loc_180018105
0x1800180e9  lea     rax, [rbp+0B0h+arg_20]
0x1800180f0  mov     dword ptr [rbp+0B0h+var_F8], 1
0x1800180f7  mov     qword ptr [rbp+0B0h+var_F8+8], rax
0x1800180fb  mov     dword ptr [rbp+0B0h+var_E8], ecx
0x1800180fe  mov     dword ptr [rbp+0B0h+var_F8+4], 4
0x180018105  mov     rbx, rcx
0x180018108  mov     qword ptr [rbp+0B0h+size.cx], rcx
0x18001810c  mov     qword ptr [rsp+1B0h+sz.cx], rcx
0x180018111  mov     rdi, rcx
0x180018114  mov     qword ptr [rbp+0B0h+point.x], rcx
0x180018118  mov     rsi, rcx
0x18001811b  mov     qword ptr [rbp+0B0h+var_118.x], rcx
0x18001811f  mov     [rbp+0B0h+h], rcx
0x180018123  mov     [rbp+0B0h+ho], rcx
0x180018127  mov     rcx, r15; hdc
0x18001812a  call    GetMapMode
0x18001812f  mov     [rbp+0B0h+iMode], eax
0x180018132  cmp     eax, 7
0x180018135  jnz     loc_1800182CC
0x18001813b  xorps   xmm0, xmm0
0x18001813e  lea     rdx, [rbp+0B0h+size]; lpsize
0x180018142  movups  xmmword ptr [rbp+0B0h+var_90], xmm0
0x180018146  mov     rcx, r15; hdc
0x180018149  movups  xmmword ptr [rbp+0B0h+var_90+0Ch], xmm0
0x18001814d  movups  [rbp+0B0h+var_D0], xmm0
0x180018151  movups  [rbp+0B0h+var_C0], xmm0
0x180018155  movups  [rbp+0B0h+var_B0], xmm0
0x180018159  movups  [rbp+0B0h+var_A0], xmm0
0x18001815d  call    GetWindowExtEx
0x180018162  test    eax, eax
0x180018164  jz      loc_1800184C9
0x18001816a  lea     rdx, [rsp+1B0h+sz]; lpsize
0x18001816f  mov     rcx, r15; hdc
0x180018172  call    GetViewportExtEx
0x180018177  test    eax, eax
0x180018179  jz      loc_1800184C9
0x18001817f  lea     rdx, [rbp+0B0h+point]; lppoint
0x180018183  mov     rcx, r15; hdc
0x180018186  call    GetWindowOrgEx
0x18001818b  test    eax, eax
0x18001818d  jz      loc_1800184C9
0x180018193  lea     rdx, [rbp+0B0h+var_118]; lppoint
0x180018197  mov     rcx, r15; hdc
0x18001819a  call    GetViewportOrgEx
0x18001819f  test    eax, eax
0x1800181a1  jz      loc_1800184C9
0x1800181a7  mov     rbx, qword ptr [rbp+0B0h+size.cx]
0x1800181ab  test    ebx, ebx
0x1800181ad  jz      loc_1800184C9
0x1800181b3  mov     r13d, [rbp+0B0h+size.cy]
0x1800181b7  test    r13d, r13d
0x1800181ba  jz      loc_1800184C9
0x1800181c0  movd    xmm6, [rsp+1B0h+sz.cx]
0x1800181c6  mov     edx, 1; iMode
0x1800181cb  movd    xmm8, [rsp+1B0h+sz.cy]
0x1800181d2  mov     rcx, r15; hdc
0x1800181d5  movd    xmm0, ebx
0x1800181d9  cvtdq2ps xmm6, xmm6
0x1800181dc  cvtdq2ps xmm0, xmm0
0x1800181df  cvtdq2ps xmm8, xmm8
0x1800181e3  divss   xmm6, xmm0
0x1800181e7  call    SetMapMode
0x1800181ec  mov     rdi, qword ptr [rbp+0B0h+point.x]
0x1800181f0  mov     rsi, qword ptr [rbp+0B0h+var_118.x]
0x1800181f4  movsd   xmm7, cs:__real@3fe0000000000000
0x1800181fc  test    eax, eax
0x1800181fe  jnz     loc_1800184D0
0x180018204  mov     edx, [rbp+0B0h+iMode]; iMode
0x180018207  xor     r14d, r14d
0x18001820a  mov     rcx, r15; hdc
0x18001820d  call    SetMapMode
0x180018212  mov     r8d, [rbp+0B0h+point.y]; y
0x180018216  xor     r9d, r9d; lppt
0x180018219  mov     edx, edi; x
0x18001821b  mov     rcx, r15; hdc
0x18001821e  call    SetWindowOrgEx
0x180018223  mov     r8d, [rbp+0B0h+var_118.y]; y
0x180018227  xor     r9d, r9d; lppt
0x18001822a  mov     edx, esi; x
0x18001822c  mov     rcx, r15; hdc
0x18001822f  call    SetViewportOrgEx
0x180018234  lea     r9, [rbp+0B0h+size]; lpsz
0x180018238  mov     r8d, r13d; y
0x18001823b  mov     edx, ebx; x
0x18001823d  mov     rcx, r15; hdc
0x180018240  call    SetWindowExtEx
0x180018245  mov     r8d, [rsp+1B0h+sz.cy]; y
0x18001824a  lea     r9, [rsp+1B0h+sz]; lpsz
0x18001824f  mov     edx, [rsp+1B0h+sz.cx]; x
0x180018253  mov     rcx, r15; hdc
0x180018256  call    SetViewportExtEx
0x18001825b  mov     rdx, [rbp+0B0h+h]; h
0x18001825f  test    rdx, rdx
0x180018262  jnz     loc_1800186F4
0x180018268  mov     rcx, [rbp+0B0h+ho]; ho
0x18001826c  test    rcx, rcx
0x18001826f  jnz     loc_180018708
0x180018275  movd    xmm0, r14d
0x18001827a  cvtdq2ps xmm0, xmm0
0x18001827d  divss   xmm0, xmm6
0x180018281  cvtps2pd xmm0, xmm0
0x180018284  addsd   xmm0, xmm7; X
0x180018288  call    floor
0x18001828d  cvttsd2si r14d, xmm0
0x180018292  mov     eax, r14d
0x180018295  mov     rcx, [rbp+0B0h+var_70]
0x180018299  xor     rcx, rsp; StackCookie
0x18001829c  call    __security_check_cookie
0x1800182a1  lea     r11, [rsp+1B0h+var_30]
0x1800182a9  mov     rbx, [r11+50h]
0x1800182ad  movaps  xmm6, xmmword ptr [r11-10h]
0x1800182b2  movaps  xmm7, xmmword ptr [r11-20h]
0x1800182b7  movaps  xmm8, xmmword ptr [r11-30h]
0x1800182bc  mov     rsp, r11
0x1800182bf  pop     r15
0x1800182c1  pop     r14
0x1800182c3  pop     r13
0x1800182c5  pop     r12
0x1800182c7  pop     rdi
0x1800182c8  pop     rsi
0x1800182c9  pop     rbp
0x1800182ca  retn
0x1800182cc  mov     r13d, [rbp+0B0h+size.cy]
0x1800182d0  xorps   xmm6, xmm6
0x1800182d3  movsd   xmm7, cs:__real@3fe0000000000000
0x1800182db  mov     rcx, r15; h
0x1800182de  call    GetObjectType
0x1800182e3  xor     ecx, ecx
0x1800182e5  mov     r8d, eax
0x1800182e8  test    r12d, r12d
0x1800182eb  lea     rax, [rbp+0B0h+var_F8]
0x1800182ef  mov     edx, 800h
0x1800182f4  cmovz   rax, rcx
0x1800182f8  mov     [rbp+0B0h+var_E0], rax
0x1800182fc  test    edx, r14d
0x1800182ff  jnz     short loc_18001831E
0x180018301  mov     ecx, r14d
0x180018304  mov     eax, 2000h
0x180018309  and     ecx, 200000h
0x18001830f  bts     ecx, 12h
0x180018313  shr     ecx, 8
0x180018316  bt      r14d, 14h
0x18001831b  cmovb   ecx, eax
0x18001831e  neg     r12d
0x180018321  lea     eax, [r8-4]
0x180018325  sbb     r12d, r12d
0x180018328  and     r12d, 2
0x18001832c  or      r12d, ecx
0x18001832f  xor     ecx, ecx
0x180018331  test    eax, 0FFFFFFF7h
0x180018336  cmovnz  edx, ecx
0x180018339  or      r12d, edx
0x18001833c  cmp     [rbp+0B0h+arg_50], 0FFFFFFFFh
0x180018343  jz      loc_1800186AC
0x180018349  mov     rcx, r15
0x18001834c  call    GdiIsPlayMetafileDC
0x180018351  test    eax, eax
0x180018353  jnz     loc_1800186AC
0x180018359  mov     eax, 8000000h
0x18001835e  or      r12d, eax
0x180018361  bt      r14d, 11h
0x180018366  jb      loc_1800184BF
0x18001836c  mov     rcx, r15; hdc
0x18001836f  call    GetTextAlign
0x180018374  bt      eax, 8
0x180018378  jb      loc_1800184B6
0x18001837e  mov     eax, 80h
0x180018383  or      r12d, eax
0x180018386  mov     dword ptr [rsp+1B0h+psc.uDefaultLanguage], 0
0x18001838e  xor     eax, eax
0x180018390  mov     word ptr [rsp+1B0h+pss.uBidiLevel], ax
0x180018395  call    CheckUpdateNLSScriptSettings
0x18001839a  lea     r8, [rsp+1B0h+pss]; pss
0x18001839f  lea     rdx, [rsp+1B0h+psc]; psc
0x1800183a4  lea     rcx, g_DigitSubstitute; psds
0x1800183ab  call    ScriptApplyDigitSubstitution
0x1800183b0  mov     eax, cs:g_iUseFontLinking
0x1800183b6  cmp     eax, 0FFFFFFFFh
0x1800183b9  jnz     short loc_1800183CD
0x1800183bb  call    cs:__imp_NtGdiAnyLinkedFonts
0x1800183c2  nop     dword ptr [rax+rax+00h]
0x1800183c7  mov     cs:g_iUseFontLinking, eax
0x1800183cd  test    eax, eax
0x1800183cf  jz      short loc_1800183D6
0x1800183d1  bts     r12d, 0Ch
0x1800183d6  mov     r8d, [rbp+0B0h+cString]; cString
0x1800183dd  lea     rax, [rbp+0B0h+ssa]
0x1800183e1  mov     rdx, [rbp+0B0h+pString]; pString
0x1800183e5  xor     r9d, r9d; cGlyphs
0x1800183e8  or      dword ptr [rsp+1B0h+psc.uDefaultLanguage], 1800000h
0x1800183f0  mov     rcx, r15; hdc
0x1800183f3  mov     [rsp+1B0h+pssa], rax; pssa
0x1800183f8  mov     rax, [rbp+0B0h+var_E0]
0x1800183fc  mov     [rsp+1B0h+pbInClass], 0; pbInClass
0x180018405  mov     [rsp+1B0h+pTabdef], rax; pTabdef
0x18001840a  lea     rax, [rsp+1B0h+pss]
0x18001840f  mov     [rsp+1B0h+piDx], 0; piDx
0x180018418  mov     [rsp+1B0h+psState], rax; psState
0x18001841d  lea     rax, [rsp+1B0h+psc]
0x180018422  mov     [rsp+1B0h+psControl], rax; psControl
0x180018427  mov     [rsp+1B0h+iReqWidth], 0; iReqWidth
0x18001842f  mov     [rsp+1B0h+dwFlags], r12d; dwFlags
0x180018434  mov     [rsp+1B0h+iCharset], 0FFFFFFFFh; iCharset
0x18001843c  call    ScriptStringAnalyse
0x180018441  test    eax, eax
0x180018443  js      loc_1800186EC
0x180018449  cmp     [rbp+0B0h+arg_40], 0
0x180018450  mov     rcx, [rbp+0B0h+ssa]; ssa
0x180018454  mov     r14d, [rcx+1A8h]
0x18001845b  jz      short loc_18001849C
0x18001845d  test    [rbp+0B0h+arg_48], 400h
0x180018467  jnz     short loc_18001849C
0x180018469  mov     r8d, [rbp+0B0h+iY]; iY
0x180018470  xor     r9d, r9d; uOptions
0x180018473  mov     edx, [rbp+0B0h+iX]; iX
0x180018476  mov     dword ptr [rsp+1B0h+psControl], 0; fDisabled
0x18001847e  mov     [rsp+1B0h+iReqWidth], 0; iMaxSel
0x180018486  mov     [rsp+1B0h+dwFlags], 0; iMinSel
0x18001848e  mov     qword ptr [rsp+1B0h+iCharset], 0; prc
0x180018497  call    ScriptStringOut
0x18001849c  lea     rcx, [rbp+0B0h+ssa]; pssa
0x1800184a0  call    ScriptStringFree
0x1800184a5  mov     edx, [rbp+0B0h+iMode]
0x1800184a8  cmp     edx, 7
0x1800184ab  jnz     loc_180018292
0x1800184b1  jmp     loc_18001820A
0x1800184b6  cmp     eax, 0FFFFFFFFh
0x1800184b9  jz      loc_18001837E
0x1800184bf  mov     eax, 180h
0x1800184c4  jmp     loc_180018383
0x1800184c9  xor     eax, eax
0x1800184cb  jmp     loc_180018295
0x1800184d0  xor     r9d, r9d; lppt
0x1800184d3  xor     r8d, r8d; y
0x1800184d6  xor     edx, edx; x
0x1800184d8  mov     rcx, r15; hdc
0x1800184db  call    SetWindowOrgEx
0x1800184e0  test    eax, eax
0x1800184e2  jz      loc_180018204
0x1800184e8  mov     ecx, [rbp+0B0h+iY]
0x1800184ee  xorps   xmm0, xmm0
0x1800184f1  cvtsi2ss xmm0, r13d
0x1800184f6  mov     eax, ecx
0x1800184f8  sub     eax, [rbp+0B0h+point.y]
0x1800184fb  xorps   xmm2, xmm2
0x1800184fe  xorps   xmm1, xmm1
0x180018501  divss   xmm8, xmm0
0x180018506  cvtsi2ss xmm2, eax
0x18001850a  xorps   xmm0, xmm0
0x18001850d  cvtsi2ss xmm0, [rbp+0B0h+var_118.y]
0x180018512  mulss   xmm2, xmm8
0x180018517  cvtsi2ss xmm1, ecx
0x18001851b  addss   xmm2, xmm0
0x18001851f  subss   xmm2, xmm1
0x180018523  cvtps2pd xmm0, xmm2
0x180018526  addsd   xmm0, xmm7; X
0x18001852a  call    floor
0x18001852f  mov     ecx, [rbp+0B0h+iX]
0x180018532  xorps   xmm2, xmm2
0x180018535  cvttsd2si r14d, xmm0
0x18001853a  mov     eax, ecx
0x18001853c  sub     eax, edi
0x18001853e  xorps   xmm0, xmm0
0x180018541  xorps   xmm1, xmm1
0x180018544  cvtsi2ss xmm2, eax
0x180018548  cvtsi2ss xmm0, esi
0x18001854c  mulss   xmm2, xmm6
  ... truncated ...
```
