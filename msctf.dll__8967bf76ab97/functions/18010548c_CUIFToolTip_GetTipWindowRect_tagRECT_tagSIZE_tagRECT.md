# CUIFToolTip::GetTipWindowRect(tagRECT *,tagSIZE,tagRECT *)

- ea: `0x18010548c`
- end: `0x18010561f`
- name: `?GetTipWindowRect@CUIFToolTip@@IEAAXPEAUtagRECT@@UtagSIZE@@0@Z`
- size: `403`
- prototype: `void __fastcall(CUIFToolTip *__hidden this, struct tagRECT *, struct tagSIZE, struct tagRECT *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180105f68`

## callees

- `0x1800d9da0`
- `0x18010548c`
- `0x180106a60`

## import_xrefs

- `USER32!GetCursor` at `0x180105511`
- `USER32!GetCursor` at `0x180105511`
- `USER32!GetCursorPos` at `0x1801054ef`
- `USER32!GetCursorPos` at `0x1801054ef`
- `USER32!GetIconInfo` at `0x180105523`
- `USER32!GetIconInfo` at `0x180105523`
- `USER32!GetSystemMetrics` at `0x1801054fa`
- `USER32!GetSystemMetrics` at `0x180105505`
- `USER32!GetSystemMetrics` at `0x1801054fa`
- `USER32!GetSystemMetrics` at `0x180105505`
- `GDI32!DeleteObject` at `0x180105569`
- `GDI32!DeleteObject` at `0x180105573`
- `GDI32!DeleteObject` at `0x180105569`
- `GDI32!DeleteObject` at `0x180105573`
- `GDI32!GetObjectW` at `0x180105539`
- `GDI32!GetObjectW` at `0x180105539`

## pseudocode

```c
void __fastcall CUIFToolTip::GetTipWindowRect(
        CUIFToolTip *this,
        struct tagRECT *a2,
        struct tagSIZE a3,
        struct tagRECT *a4)
{
  LONG cy; // esi
  LONG cx; // ebx
  int SystemMetrics; // r14d
  DWORD yHotspot; // r15d
  HCURSOR Cursor; // rax
  LONG x; // edx
  LONG y; // ecx
  LONG v13; // r8d
  LONG v14; // ecx
  int v15; // eax
  int v16; // eax
  struct tagPOINT Point; // [rsp+20h] [rbp-60h] BYREF
  ICONINFO piconinfo; // [rsp+28h] [rbp-58h] BYREF
  _OWORD pv[2]; // [rsp+48h] [rbp-38h] BYREF
  __int128 pvParam; // [rsp+68h] [rbp-18h] BYREF

  Point = 0;
  cy = a3.cy;
  cx = a3.cx;
  memset(&piconinfo, 0, sizeof(piconinfo));
  memset(pv, 0, sizeof(pv));
  pvParam = 0;
  *a2 = 0;
  GetCursorPos(&Point);
  GetSystemMetrics(13);
  SystemMetrics = GetSystemMetrics(14);
  yHotspot = 0;
  Cursor = GetCursor();
  if ( Cursor && GetIconInfo(Cursor, &piconinfo) )
  {
    GetObjectW(piconinfo.hbmMask, 32, pv);
    if ( !piconinfo.fIcon )
    {
      yHotspot = piconinfo.yHotspot;
      SystemMetrics = DWORD2(pv[0]);
      if ( piconinfo.hbmColor )
        goto LABEL_7;
      SystemMetrics = SDWORD2(pv[0]) / 2;
    }
    if ( !piconinfo.hbmColor )
    {
LABEL_8:
      DeleteObject(piconinfo.hbmMask);
      goto LABEL_9;
    }
LABEL_7:
    DeleteObject(piconinfo.hbmColor);
    goto LABEL_8;
  }
LABEL_9:
  CUIGetWorkAreaRect(Point, &pvParam);
  x = Point.x;
  y = Point.y;
  a2->left = Point.x;
  v13 = SystemMetrics - yHotspot + y;
  a2->right = cx + x;
  a2->top = v13;
  a2->bottom = v13 + cy;
  if ( SHIDWORD(pvParam) >= v13 + cy )
  {
    v14 = SystemMetrics - yHotspot + y;
  }
  else
  {
    if ( y >= a4->top )
      y = a4->top;
    v14 = y - cy;
    a2->top = v14;
    a2->bottom = cy + v14;
  }
  v15 = DWORD1(pvParam);
  if ( v14 < SDWORD1(pvParam) )
  {
    a2->top = DWORD1(pvParam);
    a2->bottom = cy + v15;
  }
  if ( SDWORD2(pvParam) < cx + x )
  {
    x = DWORD2(pvParam) - cx;
    a2->left = DWORD2(pvParam) - cx;
    a2->right = x + cx;
  }
  v16 = pvParam;
  if ( x < (int)pvParam )
  {
    a2->left = pvParam;
    a2->right = cx + v16;
  }
}

```

## disassembly

```asm
0x18010548c  mov     [rsp-28h+arg_0], rbx
0x180105491  mov     [rsp-28h+arg_18], rsi
0x180105496  push    rbp
0x180105497  push    rdi
0x180105498  push    r13
0x18010549a  push    r14
0x18010549c  push    r15
0x18010549e  mov     rbp, rsp
0x1801054a1  sub     rsp, 80h
0x1801054a8  mov     rax, cs:__security_cookie
0x1801054af  xor     rax, rsp
0x1801054b2  mov     [rbp+var_8], rax
0x1801054b6  xorps   xmm0, xmm0
0x1801054b9  mov     qword ptr [rbp+Point.x], 0
0x1801054c1  xorps   xmm1, xmm1
0x1801054c4  lea     rcx, [rbp+Point]; lpPoint
0x1801054c8  mov     rsi, r8
0x1801054cb  mov     r13, r9
0x1801054ce  shr     rsi, 20h
0x1801054d2  mov     rbx, r8
0x1801054d5  movups  xmmword ptr [rbp+piconinfo.fIcon], xmm0
0x1801054d9  mov     rdi, rdx
0x1801054dc  movups  xmmword ptr [rbp+piconinfo.hbmMask], xmm0
0x1801054e0  movups  [rbp+pv], xmm1
0x1801054e4  movups  [rbp+var_28], xmm1
0x1801054e8  movups  [rbp+pvParam], xmm0
0x1801054ec  movups  xmmword ptr [rdx], xmm1
0x1801054ef  call    cs:__imp_GetCursorPos
0x1801054f5  mov     ecx, 0Dh; nIndex
0x1801054fa  call    cs:__imp_GetSystemMetrics
0x180105500  mov     ecx, 0Eh; nIndex
0x180105505  call    cs:__imp_GetSystemMetrics
0x18010550b  mov     r14d, eax
0x18010550e  xor     r15d, r15d
0x180105511  call    cs:__imp_GetCursor
0x180105517  test    rax, rax
0x18010551a  jz      short loc_180105579
0x18010551c  lea     rdx, [rbp+piconinfo]; piconinfo
0x180105520  mov     rcx, rax; hIcon
0x180105523  call    cs:__imp_GetIconInfo
0x180105529  test    eax, eax
0x18010552b  jz      short loc_180105579
0x18010552d  mov     rcx, [rbp+piconinfo.hbmMask]; h
0x180105531  lea     r8, [rbp+pv]; pv
0x180105535  lea     edx, [r15+20h]; c
0x180105539  call    cs:__imp_GetObjectW
0x18010553f  mov     rcx, [rbp+piconinfo.hbmColor]; ho
0x180105543  cmp     [rbp+piconinfo.fIcon], r15d
0x180105547  jnz     short loc_180105564
0x180105549  mov     r15d, [rbp+piconinfo.yHotspot]
0x18010554d  mov     r14d, dword ptr [rbp+pv+8]
0x180105551  test    rcx, rcx
0x180105554  jnz     short loc_180105569
0x180105556  mov     eax, r14d
0x180105559  lea     r8d, [rcx+2]
0x18010555d  cdq
0x18010555e  idiv    r8d
0x180105561  mov     r14d, eax
0x180105564  test    rcx, rcx
0x180105567  jz      short loc_18010556F
0x180105569  call    cs:__imp_DeleteObject
0x18010556f  mov     rcx, [rbp+piconinfo.hbmMask]; ho
0x180105573  call    cs:__imp_DeleteObject
0x180105579  mov     rcx, qword ptr [rbp+Point.x]; pt
0x18010557d  lea     rdx, [rbp+pvParam]; pvParam
0x180105581  call    ?CUIGetWorkAreaRect@@YAXUtagPOINT@@PEAUtagRECT@@@Z; CUIGetWorkAreaRect(tagPOINT,tagRECT *)
0x180105586  mov     edx, [rbp+Point.x]
0x180105589  sub     r14d, r15d
0x18010558c  mov     ecx, [rbp+Point.y]
0x18010558f  mov     [rdi], edx
0x180105591  lea     r9d, [rbx+rdx]
0x180105595  lea     r8d, [r14+rcx]
0x180105599  mov     [rdi+8], r9d
0x18010559d  lea     eax, [r8+rsi]
0x1801055a1  mov     [rdi+4], r8d
0x1801055a5  mov     [rdi+0Ch], eax
0x1801055a8  cmp     dword ptr [rbp+pvParam+0Ch], eax
0x1801055ab  jge     short loc_1801055C4
0x1801055ad  cmp     ecx, [r13+4]
0x1801055b1  jl      short loc_1801055B7
0x1801055b3  mov     ecx, [r13+4]
0x1801055b7  sub     ecx, esi
0x1801055b9  mov     [rdi+4], ecx
0x1801055bc  lea     eax, [rsi+rcx]
0x1801055bf  mov     [rdi+0Ch], eax
0x1801055c2  jmp     short loc_1801055C7
0x1801055c4  mov     ecx, r8d
0x1801055c7  mov     eax, dword ptr [rbp+pvParam+4]
0x1801055ca  cmp     ecx, eax
0x1801055cc  jge     short loc_1801055D6
0x1801055ce  mov     [rdi+4], eax
0x1801055d1  add     eax, esi
0x1801055d3  mov     [rdi+0Ch], eax
0x1801055d6  cmp     dword ptr [rbp+pvParam+8], r9d
0x1801055da  jge     short loc_1801055E9
0x1801055dc  mov     edx, dword ptr [rbp+pvParam+8]
0x1801055df  sub     edx, ebx
0x1801055e1  mov     [rdi], edx
0x1801055e3  lea     eax, [rdx+rbx]
0x1801055e6  mov     [rdi+8], eax
0x1801055e9  mov     eax, dword ptr [rbp+pvParam]
0x1801055ec  cmp     edx, eax
0x1801055ee  jge     short loc_1801055F7
0x1801055f0  mov     [rdi], eax
0x1801055f2  add     eax, ebx
0x1801055f4  mov     [rdi+8], eax
0x1801055f7  mov     rcx, [rbp+var_8]
0x1801055fb  xor     rcx, rsp; StackCookie
0x1801055fe  call    __security_check_cookie
0x180105603  lea     r11, [rsp+80h+var_s0]
0x18010560b  mov     rbx, [r11+30h]
0x18010560f  mov     rsi, [r11+48h]
0x180105613  mov     rsp, r11
0x180105616  pop     r15
0x180105618  pop     r14
0x18010561a  pop     r13
0x18010561c  pop     rdi
0x18010561d  pop     rbp
0x18010561e  retn
```
