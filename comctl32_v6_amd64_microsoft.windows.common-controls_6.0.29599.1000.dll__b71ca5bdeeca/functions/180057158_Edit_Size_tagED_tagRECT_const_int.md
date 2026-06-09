# Edit_Size(tagED *,tagRECT const *,int)

- ea: `0x180057158`
- end: `0x18005746c`
- name: `?Edit_Size@@YAXPEAUtagED@@PEBUtagRECT@@H@Z`
- size: `788`
- prototype: `void __fastcall(struct tagED *, RECT *lprcSrc, int)`
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180056a44`
- `0x180056cc0`
- `0x18005a9c0`
- `0x18005b520`

## callees

- `0x180056b30`
- `0x180056bac`
- `0x180057158`
- `0x18005773c`
- `0x18005d8bc`
- `0x180114520`
- `0x1801d1010`

## import_xrefs

- `USER32!GetKeyboardLayout` at `0x1800573b1`
- `USER32!GetKeyboardLayout` at `0x1800573b1`
- `USER32!CopyRect` at `0x18005724d`
- `USER32!CopyRect` at `0x180057391`
- `USER32!CopyRect` at `0x18005724d`
- `USER32!CopyRect` at `0x180057391`
- `USER32!InflateRect` at `0x18005730c`
- `USER32!InflateRect` at `0x18005730c`
- `USER32!GetSystemMetrics` at `0x1800572be`
- `USER32!GetSystemMetrics` at `0x1800572d7`
- `USER32!GetSystemMetrics` at `0x1800573a1`
- `USER32!GetSystemMetrics` at `0x1800572be`
- `USER32!GetSystemMetrics` at `0x1800572d7`
- `USER32!GetSystemMetrics` at `0x1800573a1`
- `USER32!GetClientRect` at `0x1800571bf`
- `USER32!GetClientRect` at `0x1800571bf`
- `USER32!InvalidateRect` at `0x180057275`
- `USER32!InvalidateRect` at `0x180057275`
- `USER32!GetCaretPos` at `0x1800573d4`
- `USER32!GetCaretPos` at `0x1800573d4`
- `UxTheme!GetThemeMargins` at `0x180057418`
- `UxTheme!GetThemeMargins` at `0x180057418`
- `IMM32!ImmIsIME` at `0x1800573ba`
- `IMM32!ImmIsIME` at `0x1800573ba`

## pseudocode

```c
void __fastcall Edit_Size(struct tagED *a1, RECT *lprcSrc, int a3)
{
  int right; // edx
  LONG left; // r8d
  LONG bottom; // r9d
  LONG top; // r10d
  int v10; // r11d
  int v11; // ebx
  bool v12; // zf
  int SystemMetrics; // r14d
  int ScaledBorderWidth; // r14d
  int v15; // ebx
  int ScaledBorderHeight; // eax
  int v17; // eax
  int v18; // edx
  HKL KeyboardLayout; // rax
  struct tagRECT Rect; // [rsp+40h] [rbp-30h] BYREF
  struct tagPOINT Point[2]; // [rsp+50h] [rbp-20h] BYREF

  Rect = 0;
  (*(void (__fastcall **)(char *))(*((_QWORD *)a1 + 65) + 16LL))((char *)a1 + 520);
  if ( *((_DWORD *)a1 + 51) )
  {
    *((_DWORD *)a1 + 29) |= 0x100000u;
    if ( lprcSrc )
      CopyRect(&Rect, lprcSrc);
    else
      GetClientRect(*((HWND *)a1 + 8), &Rect);
    right = Rect.right;
    left = Rect.left;
    if ( Rect.right == Rect.left || (bottom = Rect.bottom, top = Rect.top, Rect.bottom == Rect.top) )
    {
      if ( *((_DWORD *)a1 + 22) != *((_DWORD *)a1 + 20) )
        return;
      v17 = *((_DWORD *)a1 + 50);
      left = 0;
      bottom = *((_DWORD *)a1 + 51);
      top = 0;
      *(_QWORD *)&Rect.left = 0;
      Rect.bottom = bottom;
      right = 10 * v17;
      Rect.right = 10 * v17;
    }
    if ( !lprcSrc )
    {
      v10 = *((_DWORD *)a1 + 67);
      v11 = *((_DWORD *)a1 + 68);
      if ( right - left > v11 + v10 )
      {
        left += v10;
        right -= v11;
        Rect.left = left;
        Rect.right = right;
      }
    }
    if ( (*((_DWORD *)a1 + 29) & 0x100) != 0 )
    {
      if ( (*((_DWORD *)a1 + 29) & 0x2000000) != 0 )
      {
        SystemMetrics = GetSystemMetrics(5);
        ScaledBorderWidth = DPISCALEINFO::GetScaledBorderWidth((struct tagED *)((char *)a1 + 500)) + SystemMetrics;
        v15 = GetSystemMetrics(6);
        ScaledBorderHeight = v15 + DPISCALEINFO::GetScaledBorderHeight((struct tagED *)((char *)a1 + 500));
      }
      else
      {
        ScaledBorderWidth = DPISCALEINFO::GetScaledBorderWidth((struct tagED *)((char *)a1 + 500));
        ScaledBorderHeight = DPISCALEINFO::GetScaledBorderHeight((struct tagED *)((char *)a1 + 500));
      }
      if ( Rect.bottom < Rect.top + *((_DWORD *)a1 + 51) + 2 * ScaledBorderHeight )
        ScaledBorderHeight = 0;
      InflateRect(&Rect, -ScaledBorderWidth, -ScaledBorderHeight);
      bottom = Rect.bottom;
      right = Rect.right;
      top = Rect.top;
      left = Rect.left;
    }
    if ( (*((_BYTE *)a1 + 116) & 1) != 0 )
    {
      v12 = (*((_BYTE *)a1 + 400) & 2) == 0;
      *(_OWORD *)&Point[0].x = 0;
      if ( !v12 && GetThemeMargins(*((HTHEME *)a1 + 45), 0, 5, 1, 3602, 0, (MARGINS *)Point) >= 0 )
      {
        Rect.left += Point[0].x;
        Rect.top += Point[1].x;
        Rect.right -= Point[0].y;
        Rect.bottom -= Point[1].y;
      }
    }
    else if ( right - left < *((_DWORD *)a1 + 50) || !((bottom - top) / *((_DWORD *)a1 + 51)) )
    {
      return;
    }
    *((_DWORD *)a1 + 29) &= ~0x100000u;
    CopyRect((LPRECT)a1 + 5, &Rect);
    if ( (*((_BYTE *)a1 + 116) & 1) != 0 )
    {
      v18 = Rect.top + *((_DWORD *)a1 + 51);
      if ( Rect.bottom < v18 )
        v18 = Rect.bottom;
      *((_DWORD *)a1 + 23) = v18;
    }
    else
    {
      EditML_Size(a1, a3);
    }
    if ( a3 )
      InvalidateRect(*((HWND *)a1 + 8), 0, 1);
    if ( (*((_BYTE *)a1 + 116) & 8) != 0 && GetSystemMetrics(82) )
    {
      KeyboardLayout = GetKeyboardLayout(0);
      if ( ImmIsIME(KeyboardLayout) )
      {
        Point[0] = 0;
        GetCaretPos(Point);
        Edit_ImmSetCompositionWindow(a1, Point[0].x, Point[0].y);
      }
    }
  }
}

```

## disassembly

```asm
0x180057158  mov     [rsp-28h+arg_18], rbx
0x18005715d  push    rbp
0x18005715e  push    rsi
0x18005715f  push    rdi
0x180057160  push    r14
0x180057162  push    r15
0x180057164  mov     rbp, rsp
0x180057167  sub     rsp, 70h
0x18005716b  mov     rax, cs:__security_cookie
0x180057172  xor     rax, rsp
0x180057175  mov     [rbp+var_10], rax
0x180057179  mov     rdi, rcx
0x18005717c  xorps   xmm0, xmm0
0x18005717f  add     rcx, 208h
0x180057186  mov     r15d, r8d
0x180057189  mov     rbx, rdx
0x18005718c  movups  xmmword ptr [rbp+Rect.left], xmm0
0x180057190  mov     rax, [rcx]
0x180057193  mov     rax, [rax+10h]
0x180057197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005719c  cmp     dword ptr [rdi+0CCh], 0
0x1800571a3  jz      loc_180057285
0x1800571a9  bts     dword ptr [rdi+74h], 14h
0x1800571ae  test    rbx, rbx
0x1800571b1  jnz     loc_18005738A
0x1800571b7  mov     rcx, [rdi+40h]; hWnd
0x1800571bb  lea     rdx, [rbp+Rect]; lpRect
0x1800571bf  call    cs:__imp_GetClientRect
0x1800571c5  mov     edx, [rbp+Rect.right]
0x1800571c8  mov     r8d, [rbp+Rect.left]
0x1800571cc  cmp     edx, r8d
0x1800571cf  jz      loc_180057326
0x1800571d5  mov     r9d, [rbp+Rect.bottom]
0x1800571d9  mov     r10d, [rbp+Rect.top]
0x1800571dd  cmp     r9d, r10d
0x1800571e0  jz      loc_180057326
0x1800571e6  test    rbx, rbx
0x1800571e9  jnz     short loc_180057211
0x1800571eb  mov     r11d, [rdi+10Ch]
0x1800571f2  mov     eax, edx
0x1800571f4  mov     ebx, [rdi+110h]
0x1800571fa  sub     eax, r8d
0x1800571fd  lea     ecx, [rbx+r11]
0x180057201  cmp     eax, ecx
0x180057203  jle     short loc_180057211
0x180057205  add     r8d, r11d
0x180057208  sub     edx, ebx
0x18005720a  mov     [rbp+Rect.left], r8d
0x18005720e  mov     [rbp+Rect.right], edx
0x180057211  test    dword ptr [rdi+74h], 100h
0x180057218  jnz     loc_1800572A5
0x18005721e  mov     ebx, 1
0x180057223  test    [rdi+74h], bl
0x180057226  jz      loc_180057443
0x18005722c  test    byte ptr [rdi+190h], 2
0x180057233  xorps   xmm0, xmm0
0x180057236  movups  xmmword ptr [rbp+Point.x], xmm0
0x18005723a  jnz     loc_1800573EE
0x180057240  btr     dword ptr [rdi+74h], 14h
0x180057245  lea     rcx, [rdi+50h]; lprcDst
0x180057249  lea     rdx, [rbp+Rect]; lprcSrc
0x18005724d  call    cs:__imp_CopyRect
0x180057253  test    [rdi+74h], bl
0x180057256  jnz     loc_18005735A
0x18005725c  mov     edx, r15d; int
0x18005725f  mov     rcx, rdi; struct tagED *
0x180057262  call    ?EditML_Size@@YAXPEAUtagED@@H@Z; EditML_Size(tagED *,int)
0x180057267  test    r15d, r15d
0x18005726a  jz      short loc_18005727B
0x18005726c  mov     rcx, [rdi+40h]; hWnd
0x180057270  mov     r8d, ebx; bErase
0x180057273  xor     edx, edx; lpRect
0x180057275  call    cs:__imp_InvalidateRect
0x18005727b  test    byte ptr [rdi+74h], 8
0x18005727f  jnz     loc_18005739C
0x180057285  mov     rcx, [rbp+var_10]
0x180057289  xor     rcx, rsp; StackCookie
0x18005728c  call    __security_check_cookie
0x180057291  mov     rbx, [rsp+70h+arg_18]
0x180057299  add     rsp, 70h
0x18005729d  pop     r15
0x18005729f  pop     r14
0x1800572a1  pop     rdi
0x1800572a2  pop     rsi
0x1800572a3  pop     rbp
0x1800572a4  retn
0x1800572a5  test    dword ptr [rdi+74h], 2000000h
0x1800572ac  lea     rsi, [rdi+1F4h]
0x1800572b3  jz      loc_180057372
0x1800572b9  mov     ecx, 5; nIndex
0x1800572be  call    cs:__imp_GetSystemMetrics
0x1800572c4  mov     rcx, rsi; this
0x1800572c7  mov     r14d, eax
0x1800572ca  call    ?GetScaledBorderWidth@DPISCALEINFO@@QEBAHXZ; DPISCALEINFO::GetScaledBorderWidth(void)
0x1800572cf  mov     ecx, 6; nIndex
0x1800572d4  add     r14d, eax
0x1800572d7  call    cs:__imp_GetSystemMetrics
0x1800572dd  mov     rcx, rsi; this
0x1800572e0  mov     ebx, eax
0x1800572e2  call    ?GetScaledBorderHeight@DPISCALEINFO@@QEBAHXZ; DPISCALEINFO::GetScaledBorderHeight(void)
0x1800572e7  add     eax, ebx
0x1800572e9  mov     ecx, [rdi+0CCh]
0x1800572ef  lea     edx, [rcx+rax*2]
0x1800572f2  xor     ecx, ecx
0x1800572f4  add     edx, [rbp+Rect.top]
0x1800572f7  cmp     [rbp+Rect.bottom], edx
0x1800572fa  cmovl   eax, ecx
0x1800572fd  neg     r14d
0x180057300  neg     eax
0x180057302  lea     rcx, [rbp+Rect]; lprc
0x180057306  mov     r8d, eax; dy
0x180057309  mov     edx, r14d; dx
0x18005730c  call    cs:__imp_InflateRect
0x180057312  mov     r9d, [rbp+Rect.bottom]
0x180057316  mov     edx, [rbp+Rect.right]
0x180057319  mov     r10d, [rbp+Rect.top]
0x18005731d  mov     r8d, [rbp+Rect.left]
0x180057321  jmp     loc_18005721E
0x180057326  mov     eax, [rdi+58h]
0x180057329  cmp     eax, [rdi+50h]
0x18005732c  jnz     loc_180057285
0x180057332  mov     eax, [rdi+0C8h]
0x180057338  xor     r8d, r8d
0x18005733b  mov     r9d, [rdi+0CCh]
0x180057342  xor     r10d, r10d
0x180057345  mov     qword ptr [rbp+Rect.left], r8
0x180057349  mov     [rbp+Rect.bottom], r9d
0x18005734d  lea     edx, [rax+rax*4]
0x180057350  add     edx, edx
0x180057352  mov     [rbp+Rect.right], edx
0x180057355  jmp     loc_1800571E6
0x18005735a  mov     edx, [rdi+0CCh]
0x180057360  add     edx, [rbp+Rect.top]
0x180057363  cmp     [rbp+Rect.bottom], edx
0x180057366  cmovl   edx, [rbp+Rect.bottom]
0x18005736a  mov     [rdi+5Ch], edx
0x18005736d  jmp     loc_180057267
0x180057372  mov     rcx, rsi; this
0x180057375  call    ?GetScaledBorderWidth@DPISCALEINFO@@QEBAHXZ; DPISCALEINFO::GetScaledBorderWidth(void)
0x18005737a  mov     rcx, rsi; this
0x18005737d  mov     r14d, eax
0x180057380  call    ?GetScaledBorderHeight@DPISCALEINFO@@QEBAHXZ; DPISCALEINFO::GetScaledBorderHeight(void)
0x180057385  jmp     loc_1800572E9
0x18005738a  mov     rdx, rbx; lprcSrc
0x18005738d  lea     rcx, [rbp+Rect]; lprcDst
0x180057391  call    cs:__imp_CopyRect
0x180057397  jmp     loc_1800571C5
0x18005739c  mov     ecx, 52h ; 'R'; nIndex
0x1800573a1  call    cs:__imp_GetSystemMetrics
0x1800573a7  test    eax, eax
0x1800573a9  jz      loc_180057285
0x1800573af  xor     ecx, ecx; idThread
0x1800573b1  call    cs:__imp_GetKeyboardLayout
0x1800573b7  mov     rcx, rax; HKL
0x1800573ba  call    cs:__imp_ImmIsIME
0x1800573c0  test    eax, eax
0x1800573c2  jz      loc_180057285
0x1800573c8  lea     rcx, [rbp+Point]; lpPoint
0x1800573cc  mov     qword ptr [rbp+Point.x], 0
0x1800573d4  call    cs:__imp_GetCaretPos
0x1800573da  mov     r8d, [rbp+Point.y]; int
0x1800573de  mov     rcx, rdi; struct tagED *
0x1800573e1  mov     edx, [rbp+Point.x]; int
0x1800573e4  call    ?Edit_ImmSetCompositionWindow@@YAXPEAUtagED@@JJ@Z; Edit_ImmSetCompositionWindow(tagED *,long,long)
0x1800573e9  jmp     loc_180057285
0x1800573ee  mov     rcx, [rdi+168h]; hTheme
0x1800573f5  lea     rax, [rbp+Point]
0x1800573f9  mov     [rsp+70h+pMargins], rax; pMargins
0x1800573fe  xor     edx, edx; hdc
0x180057400  mov     [rsp+70h+prc], 0; prc
0x180057409  mov     r9d, ebx; iStateId
0x18005740c  mov     [rsp+70h+iPropId], 0E12h; iPropId
0x180057414  lea     r8d, [rdx+5]; iPartId
0x180057418  call    cs:__imp_GetThemeMargins
0x18005741e  test    eax, eax
0x180057420  js      loc_180057240
0x180057426  mov     eax, [rbp+Point.x]
0x180057429  add     [rbp+Rect.left], eax
0x18005742c  mov     eax, [rbp+Point.x+8]
0x18005742f  add     [rbp+Rect.top], eax
0x180057432  mov     eax, [rbp+Point.y]
0x180057435  sub     [rbp+Rect.right], eax
0x180057438  mov     eax, [rbp+Point.y+8]
0x18005743b  sub     [rbp+Rect.bottom], eax
0x18005743e  jmp     loc_180057240
0x180057443  sub     edx, r8d
0x180057446  cmp     edx, [rdi+0C8h]
0x18005744c  jl      loc_180057285
0x180057452  sub     r9d, r10d
0x180057455  mov     eax, r9d
0x180057458  cdq
0x180057459  idiv    dword ptr [rdi+0CCh]
0x18005745f  test    eax, eax
0x180057461  jnz     loc_180057240
0x180057467  jmp     loc_180057285
```
