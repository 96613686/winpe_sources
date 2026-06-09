# bRenderCurveWithPath

- ea: `0x1800b2424`
- end: `0x1800b2909`
- name: `bRenderCurveWithPath`
- size: `1253`
- prototype: `__int64 __fastcall(int, int, int, int, int left, int top, int right, int y2, int width, int yr1, int x4, int y4, DWORD r, int, int, int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800b2308`
- `0x180146880`
- `0x180146d74`

## callees

- `0x1800b1ee8`
- `0x1800b2424`
- `0x1800e9380`
- `0x1801456fc`

## import_xrefs

- `GDI32!Ellipse` at `0x1800b25e9`
- `GDI32!Ellipse` at `0x1800b25e9`
- `GDI32!Chord` at `0x1800b27fc`
- `GDI32!Chord` at `0x1800b27fc`
- `GDI32!Arc` at `0x1800b284e`
- `GDI32!Arc` at `0x1800b284e`
- `GDI32!AngleArc` at `0x1800b261c`
- `GDI32!AngleArc` at `0x1800b28b3`
- `GDI32!AngleArc` at `0x1800b261c`
- `GDI32!AngleArc` at `0x1800b28b3`
- `GDI32!PolyDraw` at `0x1800b2729`
- `GDI32!PolyDraw` at `0x1800b2752`
- `GDI32!PolyDraw` at `0x1800b2729`
- `GDI32!PolyDraw` at `0x1800b2752`
- `GDI32!PolyBezier` at `0x1800b2666`
- `GDI32!PolyBezier` at `0x1800b2666`
- `GDI32!EndPath` at `0x1800b286c`
- `GDI32!EndPath` at `0x1800b286c`
- `GDI32!PolyBezierTo` at `0x1800b2641`
- `GDI32!PolyBezierTo` at `0x1800b28cc`
- `GDI32!PolyBezierTo` at `0x1800b2641`
- `GDI32!PolyBezierTo` at `0x1800b28cc`
- `GDI32!BeginPath` at `0x1800b2554`
- `GDI32!BeginPath` at `0x1800b2554`
- `GDI32!Rectangle` at `0x1800b25bc`
- `GDI32!Rectangle` at `0x1800b25bc`
- `GDI32!SaveDC` at `0x1800b253c`
- `GDI32!SaveDC` at `0x1800b253c`
- `GDI32!RestoreDC` at `0x1800b26e8`
- `GDI32!RestoreDC` at `0x1800b26e8`
- `GDI32!RoundRect` at `0x1800b26a7`
- `GDI32!RoundRect` at `0x1800b26a7`
- `GDI32!Pie` at `0x1800b27a7`
- `GDI32!Pie` at `0x1800b27a7`

## pseudocode

```c
int __fastcall bRenderCurveWithPath(
        __int64 a1,
        const POINT *a2,
        const BYTE *a3,
        DWORD a4,
        int left,
        int top,
        int right,
        int y2,
        int width,
        int yr1,
        int x4,
        int y4,
        DWORD r,
        int a14,
        int SweepAngle,
        unsigned int a16)
{
  int v16; // ebx
  int v17; // r14d
  int v19; // r15d
  int v20; // r13d
  int v21; // eax
  int result; // eax
  int v23; // edi
  BOOL v24; // eax
  const POINT *v25; // r13
  int v29; // [rsp+70h] [rbp-49h] BYREF
  int v30; // [rsp+74h] [rbp-45h]
  int v31; // [rsp+78h] [rbp-41h]
  int v32; // [rsp+7Ch] [rbp-3Dh]
  int v33; // [rsp+80h] [rbp-39h]
  int v34; // [rsp+84h] [rbp-35h]
  int v35; // [rsp+88h] [rbp-31h]
  int v36; // [rsp+8Ch] [rbp-2Dh]

  v16 = 0;
  v17 = left;
  v19 = top;
  v20 = right;
  v32 = y2;
  v33 = width;
  v34 = yr1;
  v35 = x4;
  v36 = y4;
  v29 = left;
  v30 = top;
  v31 = right;
  if ( !pfnSetVirtualResolution )
  {
    if ( !(unsigned int)bXformWorkhorse(a2, a4, a1 + 84) )
      goto LABEL_25;
    v21 = bXformWorkhorse(&v29, 4, a1 + 84);
    v19 = v30;
    v17 = v29;
    if ( !v21 )
      goto LABEL_25;
    v20 = v31;
    y4 = v36;
    x4 = v35;
    yr1 = v34;
    width = v33;
    y2 = v32;
  }
  result = SaveDC(*(HDC *)(a1 + 40));
  if ( !result )
    return result;
  v16 = BeginPath(*(HDC *)(a1 + 40));
  if ( !v16 )
    goto LABEL_25;
  if ( a16 <= 0x2C )
  {
    switch ( a16 )
    {
      case 0x2Cu:
        v23 = 63;
        v24 = RoundRect(*(HDC *)(a1 + 40), v17, v19, v20, y2, width, yr1);
        goto LABEL_35;
      case 2u:
        v25 = a2;
        v23 = 64;
        v24 = PolyBezier(*(HDC *)(a1 + 40), a2, a4);
        break;
      case 5u:
        v25 = a2;
        v23 = 64;
        v24 = PolyBezierTo(*(HDC *)(a1 + 40), a2, a4);
        break;
      case 0x29u:
        v23 = 64;
        v24 = AngleArc(*(HDC *)(a1 + 40), v17, v19, r, *(FLOAT *)&a14, *(FLOAT *)&SweepAngle);
        goto LABEL_35;
      case 0x2Au:
        v23 = 63;
        v24 = Ellipse(*(HDC *)(a1 + 40), v17, v19, v20, y2);
        goto LABEL_35;
      case 0x2Bu:
        v23 = 63;
        v24 = Rectangle(*(HDC *)(a1 + 40), v17, v19, v20, y2);
LABEL_35:
        v25 = a2;
        break;
      default:
        goto LABEL_24;
    }
LABEL_36:
    v16 = v24;
    if ( v24 )
    {
      v16 = EndPath(*(HDC *)(a1 + 40));
      if ( v16 )
        v16 = DoRenderPath(a1, v23, 0);
    }
    goto LABEL_26;
  }
  switch ( a16 )
  {
    case '-':
      v23 = 64;
      v24 = Arc(*(HDC *)(a1 + 40), v17, v19, v20, y2, width, yr1, x4, y4);
      goto LABEL_35;
    case '.':
      v23 = 63;
      v24 = Chord(*(HDC *)(a1 + 40), v17, v19, v20, y2, width, yr1, x4, y4);
      goto LABEL_35;
    case '/':
      v23 = 63;
      v24 = Pie(*(HDC *)(a1 + 40), v17, v19, v20, y2, width, yr1, x4, y4);
      goto LABEL_35;
    case '8':
      v25 = a2;
      v23 = 64;
      v24 = PolyDraw(*(HDC *)(a1 + 40), a2, a3, a4);
      goto LABEL_36;
  }
LABEL_24:
  v16 = 0;
LABEL_25:
  v25 = a2;
LABEL_26:
  RestoreDC(*(HDC *)(a1 + 40), -1);
  if ( v16 )
  {
    switch ( a16 )
    {
      case 5u:
        PolyBezierTo(*(HDC *)(a1 + 40), v25, a4);
        break;
      case 0x29u:
        AngleArc(*(HDC *)(a1 + 40), v17, v19, r, *(FLOAT *)&a14, *(FLOAT *)&SweepAngle);
        break;
      case 0x38u:
        PolyDraw(*(HDC *)(a1 + 40), v25, a3, a4);
        break;
    }
  }
  return v16;
}

```

## disassembly

```asm
0x1800b2424  mov     rax, rsp
0x1800b2427  push    rbp
0x1800b2428  push    rbx
0x1800b2429  push    rsi
0x1800b242a  push    rdi
0x1800b242b  push    r12
0x1800b242d  push    r13
0x1800b242f  push    r14
0x1800b2431  push    r15
0x1800b2433  lea     rbp, [rax-47h]
0x1800b2437  sub     rsp, 0B8h
0x1800b243e  movaps  xmmword ptr [rax-58h], xmm6
0x1800b2442  movaps  xmmword ptr [rax-68h], xmm7
0x1800b2446  mov     rax, cs:__security_cookie
0x1800b244d  xor     rax, rsp
0x1800b2450  mov     [rbp+3Fh+var_68], rax
0x1800b2454  mov     eax, [rbp+3Fh+y2]
0x1800b245a  xor     ebx, ebx
0x1800b245c  cmp     cs:pfnSetVirtualResolution, rbx
0x1800b2463  mov     r10d, r9d
0x1800b2466  mov     r14d, [rbp+3Fh+left]
0x1800b246a  mov     rsi, rcx
0x1800b246d  mov     r15d, [rbp+3Fh+top]
0x1800b2471  mov     r13d, [rbp+3Fh+right]
0x1800b2475  mov     r12d, [rbp+3Fh+arg_78]
0x1800b247c  movss   xmm6, [rbp+3Fh+arg_70]
0x1800b2484  movss   xmm7, [rbp+3Fh+arg_68]
0x1800b248c  mov     [rbp+3Fh+var_7C], eax
0x1800b248f  mov     eax, [rbp+3Fh+width]
0x1800b2495  mov     [rbp+3Fh+var_78], eax
0x1800b2498  mov     eax, [rbp+3Fh+yr1]
0x1800b249e  mov     [rbp+3Fh+var_74], eax
0x1800b24a1  mov     eax, [rbp+3Fh+x4]
0x1800b24a7  mov     [rbp+3Fh+var_70], eax
0x1800b24aa  mov     eax, [rbp+3Fh+y4]
0x1800b24b0  mov     [rbp+3Fh+cpt], r9d
0x1800b24b4  mov     r9, rdx
0x1800b24b7  mov     [rbp+3Fh+var_6C], eax
0x1800b24ba  mov     [rbp+3Fh+aj], r8
0x1800b24be  mov     [rbp+3Fh+apt], rdx
0x1800b24c2  mov     [rbp+3Fh+var_88], r14d
0x1800b24c6  mov     [rbp+3Fh+var_84], r15d
0x1800b24ca  mov     [rbp+3Fh+var_80], r13d
0x1800b24ce  jnz     short loc_1800B2538
0x1800b24d0  lea     r8, [rcx+54h]
0x1800b24d4  mov     edx, r10d
0x1800b24d7  mov     rcx, r9
0x1800b24da  call    bXformWorkhorse
0x1800b24df  test    eax, eax
0x1800b24e1  jz      loc_1800B26DD
0x1800b24e7  lea     r8, [rsi+54h]
0x1800b24eb  lea     edx, [rbx+4]
0x1800b24ee  lea     rcx, [rbp+3Fh+var_88]
0x1800b24f2  call    bXformWorkhorse
0x1800b24f7  mov     r15d, [rbp+3Fh+var_84]
0x1800b24fb  mov     r14d, [rbp+3Fh+var_88]
0x1800b24ff  test    eax, eax
0x1800b2501  jz      loc_1800B26DD
0x1800b2507  mov     eax, [rbp+3Fh+var_6C]
0x1800b250a  mov     r13d, [rbp+3Fh+var_80]
0x1800b250e  mov     [rbp+3Fh+y4], eax
0x1800b2514  mov     eax, [rbp+3Fh+var_70]
0x1800b2517  mov     [rbp+3Fh+x4], eax
0x1800b251d  mov     eax, [rbp+3Fh+var_74]
0x1800b2520  mov     [rbp+3Fh+yr1], eax
0x1800b2526  mov     eax, [rbp+3Fh+var_78]
0x1800b2529  mov     [rbp+3Fh+width], eax
0x1800b252f  mov     eax, [rbp+3Fh+var_7C]
0x1800b2532  mov     [rbp+3Fh+y2], eax
0x1800b2538  mov     rcx, [rsi+28h]; hdc
0x1800b253c  call    cs:__imp_SaveDC
0x1800b2543  nop     dword ptr [rax+rax+00h]
0x1800b2548  test    eax, eax
0x1800b254a  jz      loc_1800B28DA
0x1800b2550  mov     rcx, [rsi+28h]; hdc
0x1800b2554  call    cs:__imp_BeginPath
0x1800b255b  nop     dword ptr [rax+rax+00h]
0x1800b2560  mov     ebx, eax
0x1800b2562  test    eax, eax
0x1800b2564  jz      loc_1800B26DD
0x1800b256a  cmp     r12d, 2Ch ; ','
0x1800b256e  ja      loc_1800B26B8
0x1800b2574  jz      loc_1800B2677
0x1800b257a  mov     eax, r12d
0x1800b257d  sub     eax, 2
0x1800b2580  jz      loc_1800B2652
0x1800b2586  sub     eax, 3
0x1800b2589  jz      loc_1800B262D
0x1800b258f  sub     eax, 24h ; '$'
0x1800b2592  jz      short loc_1800B25FA
0x1800b2594  sub     eax, 1
0x1800b2597  jz      short loc_1800B25CD
0x1800b2599  cmp     eax, 1
0x1800b259c  jnz     loc_1800B26DB
0x1800b25a2  mov     rcx, [rsi+28h]; hdc
0x1800b25a6  lea     edi, [rax+3Eh]
0x1800b25a9  mov     eax, [rbp+3Fh+y2]
0x1800b25af  mov     r9d, r13d; right
0x1800b25b2  mov     r8d, r15d; top
0x1800b25b5  mov     [rsp+0F0h+bottom], eax; bottom
0x1800b25b9  mov     edx, r14d; left
0x1800b25bc  call    cs:__imp_Rectangle
0x1800b25c3  nop     dword ptr [rax+rax+00h]
0x1800b25c8  jmp     loc_1800B285A
0x1800b25cd  mov     eax, [rbp+3Fh+y2]
0x1800b25d3  mov     r9d, r13d; right
0x1800b25d6  mov     rcx, [rsi+28h]; hdc
0x1800b25da  mov     r8d, r15d; top
0x1800b25dd  mov     edx, r14d; left
0x1800b25e0  mov     [rsp+0F0h+bottom], eax; bottom
0x1800b25e4  mov     edi, 3Fh ; '?'
0x1800b25e9  call    cs:__imp_Ellipse
0x1800b25f0  nop     dword ptr [rax+rax+00h]
0x1800b25f5  jmp     loc_1800B285A
0x1800b25fa  mov     r9d, [rbp+3Fh+r]; r
0x1800b2601  mov     r8d, r15d; y
0x1800b2604  mov     rcx, [rsi+28h]; hdc
0x1800b2608  mov     edx, r14d; x
0x1800b260b  movss   [rsp+0F0h+SweepAngle], xmm6; SweepAngle
0x1800b2611  mov     edi, 40h ; '@'
0x1800b2616  movss   [rsp+0F0h+bottom], xmm7; StartAngle
0x1800b261c  call    cs:__imp_AngleArc
0x1800b2623  nop     dword ptr [rax+rax+00h]
0x1800b2628  jmp     loc_1800B285A
0x1800b262d  mov     r13, [rbp+3Fh+apt]
0x1800b2631  mov     edi, 40h ; '@'
0x1800b2636  mov     r8d, [rbp+3Fh+cpt]; cpt
0x1800b263a  mov     rdx, r13; apt
0x1800b263d  mov     rcx, [rsi+28h]; hdc
0x1800b2641  call    cs:__imp_PolyBezierTo
0x1800b2648  nop     dword ptr [rax+rax+00h]
0x1800b264d  jmp     loc_1800B285E
0x1800b2652  mov     r13, [rbp+3Fh+apt]
0x1800b2656  mov     edi, 40h ; '@'
0x1800b265b  mov     r8d, [rbp+3Fh+cpt]; cpt
0x1800b265f  mov     rdx, r13; apt
0x1800b2662  mov     rcx, [rsi+28h]; hdc
0x1800b2666  call    cs:__imp_PolyBezier
0x1800b266d  nop     dword ptr [rax+rax+00h]
0x1800b2672  jmp     loc_1800B285E
0x1800b2677  mov     eax, [rbp+3Fh+yr1]
0x1800b267d  mov     r9d, r13d; right
0x1800b2680  mov     rcx, [rsi+28h]; hdc
0x1800b2684  mov     r8d, r15d; top
0x1800b2687  mov     [rsp+0F0h+height], eax; height
0x1800b268b  mov     edx, r14d; left
0x1800b268e  mov     eax, [rbp+3Fh+width]
0x1800b2694  mov     edi, 3Fh ; '?'
0x1800b2699  mov     [rsp+0F0h+SweepAngle], eax; width
0x1800b269d  mov     eax, [rbp+3Fh+y2]
0x1800b26a3  mov     [rsp+0F0h+bottom], eax; bottom
0x1800b26a7  call    cs:__imp_RoundRect
0x1800b26ae  nop     dword ptr [rax+rax+00h]
0x1800b26b3  jmp     loc_1800B285A
0x1800b26b8  mov     eax, r12d
0x1800b26bb  sub     eax, 2Dh ; '-'
0x1800b26be  jz      loc_1800B280A
0x1800b26c4  sub     eax, 1
0x1800b26c7  jz      loc_1800B27B8
0x1800b26cd  sub     eax, 1
0x1800b26d0  jz      loc_1800B2763
0x1800b26d6  cmp     eax, 9
0x1800b26d9  jz      short loc_1800B273A
0x1800b26db  xor     ebx, ebx
0x1800b26dd  mov     r13, [rbp+3Fh+apt]
0x1800b26e1  mov     rcx, [rsi+28h]; hdc
0x1800b26e5  or      edx, 0FFFFFFFFh; nSavedDC
0x1800b26e8  call    cs:__imp_RestoreDC
0x1800b26ef  nop     dword ptr [rax+rax+00h]
0x1800b26f4  test    ebx, ebx
0x1800b26f6  jz      loc_1800B28D8
0x1800b26fc  cmp     r12d, 5
0x1800b2700  jz      loc_1800B28C1
0x1800b2706  cmp     r12d, 29h ; ')'
0x1800b270a  jz      loc_1800B2896
0x1800b2710  cmp     r12d, 38h ; '8'
0x1800b2714  jnz     loc_1800B28D8
0x1800b271a  mov     r9d, [rbp+3Fh+cpt]; cpt
0x1800b271e  mov     rdx, r13; apt
0x1800b2721  mov     r8, [rbp+3Fh+aj]; aj
0x1800b2725  mov     rcx, [rsi+28h]; hdc
0x1800b2729  call    cs:__imp_PolyDraw
0x1800b2730  nop     dword ptr [rax+rax+00h]
0x1800b2735  jmp     loc_1800B28D8
0x1800b273a  mov     r13, [rbp+3Fh+apt]
0x1800b273e  mov     edi, 40h ; '@'
0x1800b2743  mov     r9d, [rbp+3Fh+cpt]; cpt
0x1800b2747  mov     rdx, r13; apt
0x1800b274a  mov     r8, [rbp+3Fh+aj]; aj
0x1800b274e  mov     rcx, [rsi+28h]; hdc
0x1800b2752  call    cs:__imp_PolyDraw
0x1800b2759  nop     dword ptr [rax+rax+00h]
0x1800b275e  jmp     loc_1800B285E
0x1800b2763  mov     eax, [rbp+3Fh+y4]
0x1800b2769  mov     r9d, r13d; right
0x1800b276c  mov     rcx, [rsi+28h]; hdc
0x1800b2770  mov     r8d, r15d; top
0x1800b2773  mov     [rsp+0F0h+yr2], eax; yr2
0x1800b2777  mov     edx, r14d; left
0x1800b277a  mov     eax, [rbp+3Fh+x4]
0x1800b2780  mov     edi, 3Fh ; '?'
0x1800b2785  mov     [rsp+0F0h+xr2], eax; xr2
0x1800b2789  mov     eax, [rbp+3Fh+yr1]
0x1800b278f  mov     [rsp+0F0h+height], eax; yr1
0x1800b2793  mov     eax, [rbp+3Fh+width]
0x1800b2799  mov     [rsp+0F0h+SweepAngle], eax; xr1
0x1800b279d  mov     eax, [rbp+3Fh+y2]
0x1800b27a3  mov     [rsp+0F0h+bottom], eax; bottom
0x1800b27a7  call    cs:__imp_Pie
0x1800b27ae  nop     dword ptr [rax+rax+00h]
0x1800b27b3  jmp     loc_1800B285A
0x1800b27b8  mov     eax, [rbp+3Fh+y4]
0x1800b27be  mov     r9d, r13d; x2
0x1800b27c1  mov     rcx, [rsi+28h]; hdc
0x1800b27c5  mov     r8d, r15d; y1
0x1800b27c8  mov     [rsp+0F0h+yr2], eax; y4
0x1800b27cc  mov     edx, r14d; x1
0x1800b27cf  mov     eax, [rbp+3Fh+x4]
0x1800b27d5  mov     edi, 3Fh ; '?'
0x1800b27da  mov     [rsp+0F0h+xr2], eax; x4
0x1800b27de  mov     eax, [rbp+3Fh+yr1]
0x1800b27e4  mov     [rsp+0F0h+height], eax; y3
0x1800b27e8  mov     eax, [rbp+3Fh+width]
0x1800b27ee  mov     [rsp+0F0h+SweepAngle], eax; x3
0x1800b27f2  mov     eax, [rbp+3Fh+y2]
0x1800b27f8  mov     [rsp+0F0h+bottom], eax; y2
0x1800b27fc  call    cs:__imp_Chord
0x1800b2803  nop     dword ptr [rax+rax+00h]
0x1800b2808  jmp     short loc_1800B285A
0x1800b280a  mov     eax, [rbp+3Fh+y4]
0x1800b2810  mov     r9d, r13d; x2
0x1800b2813  mov     rcx, [rsi+28h]; hdc
0x1800b2817  mov     r8d, r15d; y1
0x1800b281a  mov     [rsp+0F0h+yr2], eax; y4
0x1800b281e  mov     edx, r14d; x1
0x1800b2821  mov     eax, [rbp+3Fh+x4]
0x1800b2827  mov     edi, 40h ; '@'
0x1800b282c  mov     [rsp+0F0h+xr2], eax; x4
0x1800b2830  mov     eax, [rbp+3Fh+yr1]
0x1800b2836  mov     [rsp+0F0h+height], eax; y3
0x1800b283a  mov     eax, [rbp+3Fh+width]
0x1800b2840  mov     [rsp+0F0h+SweepAngle], eax; x3
0x1800b2844  mov     eax, [rbp+3Fh+y2]
0x1800b284a  mov     [rsp+0F0h+bottom], eax; y2
0x1800b284e  call    cs:__imp_Arc
0x1800b2855  nop     dword ptr [rax+rax+00h]
0x1800b285a  mov     r13, [rbp+3Fh+apt]
0x1800b285e  mov     ebx, eax
0x1800b2860  test    eax, eax
0x1800b2862  jz      loc_1800B26E1
0x1800b2868  mov     rcx, [rsi+28h]; hdc
0x1800b286c  call    cs:__imp_EndPath
0x1800b2873  nop     dword ptr [rax+rax+00h]
0x1800b2878  mov     ebx, eax
0x1800b287a  test    eax, eax
0x1800b287c  jz      loc_1800B26E1
0x1800b2882  xor     r8d, r8d
0x1800b2885  mov     edx, edi
0x1800b2887  mov     rcx, rsi
0x1800b288a  call    DoRenderPath
0x1800b288f  mov     ebx, eax
0x1800b2891  jmp     loc_1800B26E1
0x1800b2896  mov     r9d, [rbp+3Fh+r]; r
0x1800b289d  mov     r8d, r15d; y
0x1800b28a0  mov     rcx, [rsi+28h]; hdc
0x1800b28a4  mov     edx, r14d; x
0x1800b28a7  movss   [rsp+0F0h+SweepAngle], xmm6; SweepAngle
0x1800b28ad  movss   [rsp+0F0h+bottom], xmm7; StartAngle
0x1800b28b3  call    cs:__imp_AngleArc
0x1800b28ba  nop     dword ptr [rax+rax+00h]
0x1800b28bf  jmp     short loc_1800B28D8
0x1800b28c1  mov     r8d, [rbp+3Fh+cpt]; cpt
0x1800b28c5  mov     rdx, r13; apt
0x1800b28c8  mov     rcx, [rsi+28h]; hdc
0x1800b28cc  call    cs:__imp_PolyBezierTo
0x1800b28d3  nop     dword ptr [rax+rax+00h]
0x1800b28d8  mov     eax, ebx
0x1800b28da  mov     rcx, [rbp+3Fh+var_68]
0x1800b28de  xor     rcx, rsp; StackCookie
0x1800b28e1  call    __security_check_cookie
0x1800b28e6  lea     r11, [rsp+0F0h+var_38]
0x1800b28ee  movaps  xmm6, xmmword ptr [r11-18h]
0x1800b28f3  movaps  xmm7, xmmword ptr [r11-28h]
0x1800b28f8  mov     rsp, r11
0x1800b28fb  pop     r15
0x1800b28fd  pop     r14
0x1800b28ff  pop     r13
0x1800b2901  pop     r12
0x1800b2903  pop     rdi
0x1800b2904  pop     rsi
0x1800b2905  pop     rbx
0x1800b2906  pop     rbp
0x1800b2907  retn
```
