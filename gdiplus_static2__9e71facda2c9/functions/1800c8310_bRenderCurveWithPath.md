# bRenderCurveWithPath

- ea: `0x1800c8310`
- end: `0x1800c87f6`
- name: `bRenderCurveWithPath`
- size: `1254`
- prototype: `__int64 __fastcall(int, int, int, int, int left, int top, int right, int y2, int width, int yr1, int x4, int y4, DWORD r, int, int, int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800c8210`
- `0x18014c768`
- `0x18014cc50`

## callees

- `0x1800c790c`
- `0x1800c8310`
- `0x180105d40`
- `0x18014b6c0`

## import_xrefs

- `GDI32!RoundRect` at `0x1800c8594`
- `GDI32!RoundRect` at `0x1800c8594`
- `GDI32!Pie` at `0x1800c8694`
- `GDI32!Pie` at `0x1800c8694`
- `GDI32!Chord` at `0x1800c86e9`
- `GDI32!Chord` at `0x1800c86e9`
- `GDI32!Arc` at `0x1800c873b`
- `GDI32!Arc` at `0x1800c873b`
- `GDI32!AngleArc` at `0x1800c8509`
- `GDI32!AngleArc` at `0x1800c87a0`
- `GDI32!AngleArc` at `0x1800c8509`
- `GDI32!AngleArc` at `0x1800c87a0`
- `GDI32!PolyDraw` at `0x1800c8616`
- `GDI32!PolyDraw` at `0x1800c863f`
- `GDI32!PolyDraw` at `0x1800c8616`
- `GDI32!PolyDraw` at `0x1800c863f`
- `GDI32!PolyBezier` at `0x1800c8553`
- `GDI32!PolyBezier` at `0x1800c8553`
- `GDI32!EndPath` at `0x1800c8759`
- `GDI32!EndPath` at `0x1800c8759`
- `GDI32!PolyBezierTo` at `0x1800c852e`
- `GDI32!PolyBezierTo` at `0x1800c87b9`
- `GDI32!PolyBezierTo` at `0x1800c852e`
- `GDI32!PolyBezierTo` at `0x1800c87b9`
- `GDI32!BeginPath` at `0x1800c8441`
- `GDI32!BeginPath` at `0x1800c8441`
- `GDI32!Rectangle` at `0x1800c84a9`
- `GDI32!Rectangle` at `0x1800c84a9`
- `GDI32!SaveDC` at `0x1800c8429`
- `GDI32!SaveDC` at `0x1800c8429`
- `GDI32!RestoreDC` at `0x1800c85d5`
- `GDI32!RestoreDC` at `0x1800c85d5`
- `GDI32!Ellipse` at `0x1800c84d6`
- `GDI32!Ellipse` at `0x1800c84d6`

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
  int v17; // r14d
  int v18; // r15d
  int v19; // r13d
  int v20; // ebx
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

  v17 = left;
  v18 = top;
  v19 = right;
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
    v20 = 0;
    if ( !(unsigned int)bXformWorkhorse(a2, a4, a1 + 84) )
      goto LABEL_25;
    v21 = bXformWorkhorse(&v29, 4, a1 + 84);
    v18 = v30;
    v17 = v29;
    if ( !v21 )
      goto LABEL_25;
    v19 = v31;
    y4 = v36;
    x4 = v35;
    yr1 = v34;
    width = v33;
    y2 = v32;
  }
  result = SaveDC(*(HDC *)(a1 + 40));
  if ( !result )
    return result;
  v20 = BeginPath(*(HDC *)(a1 + 40));
  if ( !v20 )
    goto LABEL_25;
  if ( a16 <= 0x2C )
  {
    switch ( a16 )
    {
      case 0x2Cu:
        v23 = 63;
        v24 = RoundRect(*(HDC *)(a1 + 40), v17, v18, v19, y2, width, yr1);
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
        v24 = AngleArc(*(HDC *)(a1 + 40), v17, v18, r, *(FLOAT *)&a14, *(FLOAT *)&SweepAngle);
        goto LABEL_35;
      case 0x2Au:
        v23 = 63;
        v24 = Ellipse(*(HDC *)(a1 + 40), v17, v18, v19, y2);
        goto LABEL_35;
      case 0x2Bu:
        v23 = 63;
        v24 = Rectangle(*(HDC *)(a1 + 40), v17, v18, v19, y2);
LABEL_35:
        v25 = a2;
        break;
      default:
        goto LABEL_24;
    }
LABEL_36:
    v20 = v24;
    if ( v24 )
    {
      v20 = EndPath(*(HDC *)(a1 + 40));
      if ( v20 )
        v20 = DoRenderPath(a1, v23, 0);
    }
    goto LABEL_26;
  }
  switch ( a16 )
  {
    case '-':
      v23 = 64;
      v24 = Arc(*(HDC *)(a1 + 40), v17, v18, v19, y2, width, yr1, x4, y4);
      goto LABEL_35;
    case '.':
      v23 = 63;
      v24 = Chord(*(HDC *)(a1 + 40), v17, v18, v19, y2, width, yr1, x4, y4);
      goto LABEL_35;
    case '/':
      v23 = 63;
      v24 = Pie(*(HDC *)(a1 + 40), v17, v18, v19, y2, width, yr1, x4, y4);
      goto LABEL_35;
    case '8':
      v25 = a2;
      v23 = 64;
      v24 = PolyDraw(*(HDC *)(a1 + 40), a2, a3, a4);
      goto LABEL_36;
  }
LABEL_24:
  v20 = 0;
LABEL_25:
  v25 = a2;
LABEL_26:
  RestoreDC(*(HDC *)(a1 + 40), -1);
  if ( v20 )
  {
    switch ( a16 )
    {
      case 5u:
        PolyBezierTo(*(HDC *)(a1 + 40), v25, a4);
        break;
      case 0x29u:
        AngleArc(*(HDC *)(a1 + 40), v17, v18, r, *(FLOAT *)&a14, *(FLOAT *)&SweepAngle);
        break;
      case 0x38u:
        PolyDraw(*(HDC *)(a1 + 40), v25, a3, a4);
        break;
    }
  }
  return v20;
}

```

## disassembly

```asm
0x1800c8310  mov     rax, rsp
0x1800c8313  push    rbp
0x1800c8314  push    rbx
0x1800c8315  push    rsi
0x1800c8316  push    rdi
0x1800c8317  push    r12
0x1800c8319  push    r13
0x1800c831b  push    r14
0x1800c831d  push    r15
0x1800c831f  lea     rbp, [rax-47h]
0x1800c8323  sub     rsp, 0B8h
0x1800c832a  movaps  xmmword ptr [rax-58h], xmm6
0x1800c832e  movaps  xmmword ptr [rax-68h], xmm7
0x1800c8332  mov     rax, cs:__security_cookie
0x1800c8339  xor     rax, rsp
0x1800c833c  mov     [rbp+3Fh+var_68], rax
0x1800c8340  cmp     cs:pfnSetVirtualResolution, 0
0x1800c8348  mov     r10d, r9d
0x1800c834b  mov     eax, [rbp+3Fh+y2]
0x1800c8351  mov     rsi, rcx
0x1800c8354  mov     r14d, [rbp+3Fh+left]
0x1800c8358  mov     r15d, [rbp+3Fh+top]
0x1800c835c  mov     r13d, [rbp+3Fh+right]
0x1800c8360  mov     r12d, [rbp+3Fh+arg_78]
0x1800c8367  movss   xmm6, [rbp+3Fh+arg_70]
0x1800c836f  movss   xmm7, [rbp+3Fh+arg_68]
0x1800c8377  mov     [rbp+3Fh+var_7C], eax
0x1800c837a  mov     eax, [rbp+3Fh+width]
0x1800c8380  mov     [rbp+3Fh+var_78], eax
0x1800c8383  mov     eax, [rbp+3Fh+yr1]
0x1800c8389  mov     [rbp+3Fh+var_74], eax
0x1800c838c  mov     eax, [rbp+3Fh+x4]
0x1800c8392  mov     [rbp+3Fh+var_70], eax
0x1800c8395  mov     eax, [rbp+3Fh+y4]
0x1800c839b  mov     [rbp+3Fh+cpt], r9d
0x1800c839f  mov     r9, rdx
0x1800c83a2  mov     [rbp+3Fh+var_6C], eax
0x1800c83a5  mov     [rbp+3Fh+aj], r8
0x1800c83a9  mov     [rbp+3Fh+apt], rdx
0x1800c83ad  mov     [rbp+3Fh+var_88], r14d
0x1800c83b1  mov     [rbp+3Fh+var_84], r15d
0x1800c83b5  mov     [rbp+3Fh+var_80], r13d
0x1800c83b9  jnz     short loc_1800C8425
0x1800c83bb  lea     r8, [rcx+54h]
0x1800c83bf  mov     edx, r10d
0x1800c83c2  mov     rcx, r9
0x1800c83c5  xor     ebx, ebx
0x1800c83c7  call    bXformWorkhorse
0x1800c83cc  test    eax, eax
0x1800c83ce  jz      loc_1800C85CA
0x1800c83d4  lea     r8, [rsi+54h]
0x1800c83d8  lea     edx, [rbx+4]
0x1800c83db  lea     rcx, [rbp+3Fh+var_88]
0x1800c83df  call    bXformWorkhorse
0x1800c83e4  mov     r15d, [rbp+3Fh+var_84]
0x1800c83e8  mov     r14d, [rbp+3Fh+var_88]
0x1800c83ec  test    eax, eax
0x1800c83ee  jz      loc_1800C85CA
0x1800c83f4  mov     eax, [rbp+3Fh+var_6C]
0x1800c83f7  mov     r13d, [rbp+3Fh+var_80]
0x1800c83fb  mov     [rbp+3Fh+y4], eax
0x1800c8401  mov     eax, [rbp+3Fh+var_70]
0x1800c8404  mov     [rbp+3Fh+x4], eax
0x1800c840a  mov     eax, [rbp+3Fh+var_74]
0x1800c840d  mov     [rbp+3Fh+yr1], eax
0x1800c8413  mov     eax, [rbp+3Fh+var_78]
0x1800c8416  mov     [rbp+3Fh+width], eax
0x1800c841c  mov     eax, [rbp+3Fh+var_7C]
0x1800c841f  mov     [rbp+3Fh+y2], eax
0x1800c8425  mov     rcx, [rsi+28h]; hdc
0x1800c8429  call    cs:__imp_SaveDC
0x1800c8430  nop     dword ptr [rax+rax+00h]
0x1800c8435  test    eax, eax
0x1800c8437  jz      loc_1800C87C7
0x1800c843d  mov     rcx, [rsi+28h]; hdc
0x1800c8441  call    cs:__imp_BeginPath
0x1800c8448  nop     dword ptr [rax+rax+00h]
0x1800c844d  mov     ebx, eax
0x1800c844f  test    eax, eax
0x1800c8451  jz      loc_1800C85CA
0x1800c8457  cmp     r12d, 2Ch ; ','
0x1800c845b  ja      loc_1800C85A5
0x1800c8461  jz      loc_1800C8564
0x1800c8467  mov     eax, r12d
0x1800c846a  sub     eax, 2
0x1800c846d  jz      loc_1800C853F
0x1800c8473  sub     eax, 3
0x1800c8476  jz      loc_1800C851A
0x1800c847c  sub     eax, 24h ; '$'
0x1800c847f  jz      short loc_1800C84E7
0x1800c8481  sub     eax, 1
0x1800c8484  jz      short loc_1800C84BA
0x1800c8486  cmp     eax, 1
0x1800c8489  jnz     loc_1800C85C8
0x1800c848f  mov     rcx, [rsi+28h]; hdc
0x1800c8493  lea     edi, [rax+3Eh]
0x1800c8496  mov     eax, [rbp+3Fh+y2]
0x1800c849c  mov     r9d, r13d; right
0x1800c849f  mov     r8d, r15d; top
0x1800c84a2  mov     [rsp+0F0h+bottom], eax; bottom
0x1800c84a6  mov     edx, r14d; left
0x1800c84a9  call    cs:__imp_Rectangle
0x1800c84b0  nop     dword ptr [rax+rax+00h]
0x1800c84b5  jmp     loc_1800C8747
0x1800c84ba  mov     eax, [rbp+3Fh+y2]
0x1800c84c0  mov     r9d, r13d; right
0x1800c84c3  mov     rcx, [rsi+28h]; hdc
0x1800c84c7  mov     r8d, r15d; top
0x1800c84ca  mov     edx, r14d; left
0x1800c84cd  mov     [rsp+0F0h+bottom], eax; bottom
0x1800c84d1  mov     edi, 3Fh ; '?'
0x1800c84d6  call    cs:__imp_Ellipse
0x1800c84dd  nop     dword ptr [rax+rax+00h]
0x1800c84e2  jmp     loc_1800C8747
0x1800c84e7  mov     r9d, [rbp+3Fh+r]; r
0x1800c84ee  mov     r8d, r15d; y
0x1800c84f1  mov     rcx, [rsi+28h]; hdc
0x1800c84f5  mov     edx, r14d; x
0x1800c84f8  movss   [rsp+0F0h+SweepAngle], xmm6; SweepAngle
0x1800c84fe  mov     edi, 40h ; '@'
0x1800c8503  movss   [rsp+0F0h+bottom], xmm7; StartAngle
0x1800c8509  call    cs:__imp_AngleArc
0x1800c8510  nop     dword ptr [rax+rax+00h]
0x1800c8515  jmp     loc_1800C8747
0x1800c851a  mov     r13, [rbp+3Fh+apt]
0x1800c851e  mov     edi, 40h ; '@'
0x1800c8523  mov     r8d, [rbp+3Fh+cpt]; cpt
0x1800c8527  mov     rdx, r13; apt
0x1800c852a  mov     rcx, [rsi+28h]; hdc
0x1800c852e  call    cs:__imp_PolyBezierTo
0x1800c8535  nop     dword ptr [rax+rax+00h]
0x1800c853a  jmp     loc_1800C874B
0x1800c853f  mov     r13, [rbp+3Fh+apt]
0x1800c8543  mov     edi, 40h ; '@'
0x1800c8548  mov     r8d, [rbp+3Fh+cpt]; cpt
0x1800c854c  mov     rdx, r13; apt
0x1800c854f  mov     rcx, [rsi+28h]; hdc
0x1800c8553  call    cs:__imp_PolyBezier
0x1800c855a  nop     dword ptr [rax+rax+00h]
0x1800c855f  jmp     loc_1800C874B
0x1800c8564  mov     eax, [rbp+3Fh+yr1]
0x1800c856a  mov     r9d, r13d; right
0x1800c856d  mov     rcx, [rsi+28h]; hdc
0x1800c8571  mov     r8d, r15d; top
0x1800c8574  mov     [rsp+0F0h+height], eax; height
0x1800c8578  mov     edx, r14d; left
0x1800c857b  mov     eax, [rbp+3Fh+width]
0x1800c8581  mov     edi, 3Fh ; '?'
0x1800c8586  mov     [rsp+0F0h+SweepAngle], eax; width
0x1800c858a  mov     eax, [rbp+3Fh+y2]
0x1800c8590  mov     [rsp+0F0h+bottom], eax; bottom
0x1800c8594  call    cs:__imp_RoundRect
0x1800c859b  nop     dword ptr [rax+rax+00h]
0x1800c85a0  jmp     loc_1800C8747
0x1800c85a5  mov     eax, r12d
0x1800c85a8  sub     eax, 2Dh ; '-'
0x1800c85ab  jz      loc_1800C86F7
0x1800c85b1  sub     eax, 1
0x1800c85b4  jz      loc_1800C86A5
0x1800c85ba  sub     eax, 1
0x1800c85bd  jz      loc_1800C8650
0x1800c85c3  cmp     eax, 9
0x1800c85c6  jz      short loc_1800C8627
0x1800c85c8  xor     ebx, ebx
0x1800c85ca  mov     r13, [rbp+3Fh+apt]
0x1800c85ce  mov     rcx, [rsi+28h]; hdc
0x1800c85d2  or      edx, 0FFFFFFFFh; nSavedDC
0x1800c85d5  call    cs:__imp_RestoreDC
0x1800c85dc  nop     dword ptr [rax+rax+00h]
0x1800c85e1  test    ebx, ebx
0x1800c85e3  jz      loc_1800C87C5
0x1800c85e9  cmp     r12d, 5
0x1800c85ed  jz      loc_1800C87AE
0x1800c85f3  cmp     r12d, 29h ; ')'
0x1800c85f7  jz      loc_1800C8783
0x1800c85fd  cmp     r12d, 38h ; '8'
0x1800c8601  jnz     loc_1800C87C5
0x1800c8607  mov     r9d, [rbp+3Fh+cpt]; cpt
0x1800c860b  mov     rdx, r13; apt
0x1800c860e  mov     r8, [rbp+3Fh+aj]; aj
0x1800c8612  mov     rcx, [rsi+28h]; hdc
0x1800c8616  call    cs:__imp_PolyDraw
0x1800c861d  nop     dword ptr [rax+rax+00h]
0x1800c8622  jmp     loc_1800C87C5
0x1800c8627  mov     r13, [rbp+3Fh+apt]
0x1800c862b  mov     edi, 40h ; '@'
0x1800c8630  mov     r9d, [rbp+3Fh+cpt]; cpt
0x1800c8634  mov     rdx, r13; apt
0x1800c8637  mov     r8, [rbp+3Fh+aj]; aj
0x1800c863b  mov     rcx, [rsi+28h]; hdc
0x1800c863f  call    cs:__imp_PolyDraw
0x1800c8646  nop     dword ptr [rax+rax+00h]
0x1800c864b  jmp     loc_1800C874B
0x1800c8650  mov     eax, [rbp+3Fh+y4]
0x1800c8656  mov     r9d, r13d; right
0x1800c8659  mov     rcx, [rsi+28h]; hdc
0x1800c865d  mov     r8d, r15d; top
0x1800c8660  mov     [rsp+0F0h+yr2], eax; yr2
0x1800c8664  mov     edx, r14d; left
0x1800c8667  mov     eax, [rbp+3Fh+x4]
0x1800c866d  mov     edi, 3Fh ; '?'
0x1800c8672  mov     [rsp+0F0h+xr2], eax; xr2
0x1800c8676  mov     eax, [rbp+3Fh+yr1]
0x1800c867c  mov     [rsp+0F0h+height], eax; yr1
0x1800c8680  mov     eax, [rbp+3Fh+width]
0x1800c8686  mov     [rsp+0F0h+SweepAngle], eax; xr1
0x1800c868a  mov     eax, [rbp+3Fh+y2]
0x1800c8690  mov     [rsp+0F0h+bottom], eax; bottom
0x1800c8694  call    cs:__imp_Pie
0x1800c869b  nop     dword ptr [rax+rax+00h]
0x1800c86a0  jmp     loc_1800C8747
0x1800c86a5  mov     eax, [rbp+3Fh+y4]
0x1800c86ab  mov     r9d, r13d; x2
0x1800c86ae  mov     rcx, [rsi+28h]; hdc
0x1800c86b2  mov     r8d, r15d; y1
0x1800c86b5  mov     [rsp+0F0h+yr2], eax; y4
0x1800c86b9  mov     edx, r14d; x1
0x1800c86bc  mov     eax, [rbp+3Fh+x4]
0x1800c86c2  mov     edi, 3Fh ; '?'
0x1800c86c7  mov     [rsp+0F0h+xr2], eax; x4
0x1800c86cb  mov     eax, [rbp+3Fh+yr1]
0x1800c86d1  mov     [rsp+0F0h+height], eax; y3
0x1800c86d5  mov     eax, [rbp+3Fh+width]
0x1800c86db  mov     [rsp+0F0h+SweepAngle], eax; x3
0x1800c86df  mov     eax, [rbp+3Fh+y2]
0x1800c86e5  mov     [rsp+0F0h+bottom], eax; y2
0x1800c86e9  call    cs:__imp_Chord
0x1800c86f0  nop     dword ptr [rax+rax+00h]
0x1800c86f5  jmp     short loc_1800C8747
0x1800c86f7  mov     eax, [rbp+3Fh+y4]
0x1800c86fd  mov     r9d, r13d; x2
0x1800c8700  mov     rcx, [rsi+28h]; hdc
0x1800c8704  mov     r8d, r15d; y1
0x1800c8707  mov     [rsp+0F0h+yr2], eax; y4
0x1800c870b  mov     edx, r14d; x1
0x1800c870e  mov     eax, [rbp+3Fh+x4]
0x1800c8714  mov     edi, 40h ; '@'
0x1800c8719  mov     [rsp+0F0h+xr2], eax; x4
0x1800c871d  mov     eax, [rbp+3Fh+yr1]
0x1800c8723  mov     [rsp+0F0h+height], eax; y3
0x1800c8727  mov     eax, [rbp+3Fh+width]
0x1800c872d  mov     [rsp+0F0h+SweepAngle], eax; x3
0x1800c8731  mov     eax, [rbp+3Fh+y2]
0x1800c8737  mov     [rsp+0F0h+bottom], eax; y2
0x1800c873b  call    cs:__imp_Arc
0x1800c8742  nop     dword ptr [rax+rax+00h]
0x1800c8747  mov     r13, [rbp+3Fh+apt]
0x1800c874b  mov     ebx, eax
0x1800c874d  test    eax, eax
0x1800c874f  jz      loc_1800C85CE
0x1800c8755  mov     rcx, [rsi+28h]; hdc
0x1800c8759  call    cs:__imp_EndPath
0x1800c8760  nop     dword ptr [rax+rax+00h]
0x1800c8765  mov     ebx, eax
0x1800c8767  test    eax, eax
0x1800c8769  jz      loc_1800C85CE
0x1800c876f  xor     r8d, r8d
0x1800c8772  mov     edx, edi
0x1800c8774  mov     rcx, rsi
0x1800c8777  call    DoRenderPath
0x1800c877c  mov     ebx, eax
0x1800c877e  jmp     loc_1800C85CE
0x1800c8783  mov     r9d, [rbp+3Fh+r]; r
0x1800c878a  mov     r8d, r15d; y
0x1800c878d  mov     rcx, [rsi+28h]; hdc
0x1800c8791  mov     edx, r14d; x
0x1800c8794  movss   [rsp+0F0h+SweepAngle], xmm6; SweepAngle
0x1800c879a  movss   [rsp+0F0h+bottom], xmm7; StartAngle
0x1800c87a0  call    cs:__imp_AngleArc
0x1800c87a7  nop     dword ptr [rax+rax+00h]
0x1800c87ac  jmp     short loc_1800C87C5
0x1800c87ae  mov     r8d, [rbp+3Fh+cpt]; cpt
0x1800c87b2  mov     rdx, r13; apt
0x1800c87b5  mov     rcx, [rsi+28h]; hdc
0x1800c87b9  call    cs:__imp_PolyBezierTo
0x1800c87c0  nop     dword ptr [rax+rax+00h]
0x1800c87c5  mov     eax, ebx
0x1800c87c7  mov     rcx, [rbp+3Fh+var_68]
0x1800c87cb  xor     rcx, rsp; StackCookie
0x1800c87ce  call    __security_check_cookie
0x1800c87d3  lea     r11, [rsp+0F0h+var_38]
0x1800c87db  movaps  xmm6, xmmword ptr [r11-18h]
0x1800c87e0  movaps  xmm7, xmmword ptr [r11-28h]
0x1800c87e5  mov     rsp, r11
0x1800c87e8  pop     r15
0x1800c87ea  pop     r14
0x1800c87ec  pop     r13
0x1800c87ee  pop     r12
0x1800c87f0  pop     rdi
0x1800c87f1  pop     rsi
0x1800c87f2  pop     rbx
0x1800c87f3  pop     rbp
0x1800c87f4  retn
```
