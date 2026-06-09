# CToolbar::TBGenerateDragImage(SHDRAGIMAGE *)

- ea: `0x1800eff34`
- end: `0x1800f0168`
- name: `?TBGenerateDragImage@CToolbar@@AEAA_JPEAUSHDRAGIMAGE@@@Z`
- size: `564`
- prototype: `__int64 __fastcall(CToolbar *__hidden this, struct SHDRAGIMAGE *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800134f0`

## callees

- `0x180007fc4`
- `0x180017714`
- `0x180017808`
- `0x180018b88`
- `0x180034a84`
- `0x1800eff34`
- `0x180114520`
- `0x180114ebc`

## import_xrefs

- `GDI32!SelectObject` at `0x1800f005e`
- `GDI32!SelectObject` at `0x1800f012d`
- `GDI32!SelectObject` at `0x1800f005e`
- `GDI32!SelectObject` at `0x1800f012d`
- `GDI32!DeleteDC` at `0x1800f0136`
- `GDI32!DeleteDC` at `0x1800f0136`
- `GDI32!CreateCompatibleDC` at `0x1800eff8a`
- `GDI32!CreateCompatibleDC` at `0x1800eff8a`
- `GDI32!SetLayout` at `0x1800effad`
- `GDI32!SetLayout` at `0x1800effad`
- `GDI32!CreateBitmap` at `0x1800f0030`
- `GDI32!CreateBitmap` at `0x1800f0030`
- `GDI32!GetDeviceCaps` at `0x1800f0004`
- `GDI32!GetDeviceCaps` at `0x1800f0014`
- `GDI32!GetDeviceCaps` at `0x1800f0004`
- `GDI32!GetDeviceCaps` at `0x1800f0014`
- `USER32!PtInRect` at `0x1800f00f1`
- `USER32!PtInRect` at `0x1800f00f1`

## pseudocode

```c
__int64 __fastcall CToolbar::TBGenerateDragImage(POINT *this, struct SHDRAGIMAGE *a2)
{
  HDC CompatibleDC; // rax
  HDC v5; // rsi
  UINT DeviceCaps; // ebx
  UINT v7; // eax
  HBITMAP Bitmap; // rax
  HGDIOBJ v9; // rax
  void *v10; // r15
  LONG x; // ebx
  unsigned int y; // edx
  LONG v13; // ecx
  LONG v14; // eax
  _DWORD v16[4]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v17; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v18[24]; // [rsp+58h] [rbp-A8h] BYREF
  HDC v19; // [rsp+70h] [rbp-90h]
  RECT rc; // [rsp+F0h] [rbp-10h] BYREF

  v17 = 0;
  memset_0(v18, 0, 0x98u);
  if ( this[43].y == -1 )
    return 0;
  CompatibleDC = CreateCompatibleDC(0);
  v5 = CompatibleDC;
  if ( !CompatibleDC )
    return 0;
  if ( (this[11].x & 0x400000) != 0 )
    SetLayout(CompatibleDC, 1u);
  v19 = v5;
  this[9].y = CICustomDrawNotify(&this[7], 1, &v17);
  a2->sizeDragImage.cx = CToolbar::TBWidthOfButton(
                           (CToolbar *)this,
                           (struct _TBBUTTONDATA *)(*(_QWORD *)&this[18] + 80LL * this[43].y),
                           v5);
  a2->sizeDragImage.cy = this[31].x;
  DeviceCaps = GetDeviceCaps(v5, 12);
  v7 = GetDeviceCaps(v5, 14);
  Bitmap = CreateBitmap(a2->sizeDragImage.cx, a2->sizeDragImage.cy, v7, DeviceCaps, 0);
  a2->hbmpDragImage = Bitmap;
  if ( !Bitmap )
    return 0;
  rc.right = a2->sizeDragImage.cx;
  rc.bottom = a2->sizeDragImage.cy;
  *(_QWORD *)&rc.left = 0;
  v9 = SelectObject(v5, Bitmap);
  a2->crColorKey = -1;
  v10 = v9;
  FillRectClr(v5, &rc, 0xFFFFFFFF);
  x = this[9].x;
  this[9].x = x | 0x8000;
  v16[0] = this[43].y;
  v16[1] = 2;
  CToolbar::DrawButton(
    (CToolbar *)this,
    v5,
    0,
    0,
    (struct _TBBUTTONDATA *)(*(_QWORD *)&this[18] + 80LL * v16[0]),
    1,
    (const struct CTBHotState *)v16);
  y = this[43].y;
  this[9].x = x;
  CToolbar::TB_GetItemRect((CToolbar *)this, y, &rc);
  if ( PtInRect(&rc, this[20]) )
  {
    v13 = this[20].x;
    if ( (this[11].x & 0x400000) != 0 )
      v14 = rc.right - v13;
    else
      v14 = v13 - rc.left;
    a2->ptOffset.x = v14;
    a2->ptOffset.y = this[20].y - rc.top;
  }
  SelectObject(v5, v10);
  DeleteDC(v5);
  return 1;
}

```

## disassembly

```asm
0x1800eff34  mov     [rsp-8+arg_10], rbx
0x1800eff39  push    rbp
0x1800eff3a  push    rsi
0x1800eff3b  push    rdi
0x1800eff3c  push    r14
0x1800eff3e  push    r15
0x1800eff40  lea     rbp, [rsp-10h]
0x1800eff45  sub     rsp, 110h
0x1800eff4c  mov     rax, cs:__security_cookie
0x1800eff53  xor     rax, rsp
0x1800eff56  mov     [rbp+30h+var_30], rax
0x1800eff5a  mov     r14, rdx
0x1800eff5d  mov     [rsp+130h+var_E0], 0
0x1800eff66  mov     rdi, rcx
0x1800eff69  xor     edx, edx; Val
0x1800eff6b  lea     rcx, [rsp+130h+var_D8]; void *
0x1800eff70  mov     r8d, 98h; Size
0x1800eff76  call    memset_0
0x1800eff7b  cmp     dword ptr [rdi+15Ch], 0FFFFFFFFh
0x1800eff82  jz      loc_1800F0143
0x1800eff88  xor     ecx, ecx; hdc
0x1800eff8a  call    cs:__imp_CreateCompatibleDC
0x1800eff90  mov     rsi, rax
0x1800eff93  test    rax, rax
0x1800eff96  jz      loc_1800F0143
0x1800eff9c  test    dword ptr [rdi+58h], 400000h
0x1800effa3  jz      short loc_1800EFFB3
0x1800effa5  mov     edx, 1; l
0x1800effaa  mov     rcx, rax; hdc
0x1800effad  call    cs:__imp_SetLayout
0x1800effb3  lea     r8, [rsp+130h+var_E0]
0x1800effb8  mov     [rsp+130h+var_C0], rsi
0x1800effbd  mov     edx, 1
0x1800effc2  lea     rcx, [rdi+38h]
0x1800effc6  call    CICustomDrawNotify
0x1800effcb  mov     [rdi+4Ch], eax
0x1800effce  mov     r8, rsi; hdc
0x1800effd1  movsxd  rax, dword ptr [rdi+15Ch]
0x1800effd8  mov     rcx, rdi; this
0x1800effdb  lea     rdx, [rax+rax*4]
0x1800effdf  shl     rdx, 4
0x1800effe3  add     rdx, [rdi+90h]; struct _TBBUTTONDATA *
0x1800effea  call    ?TBWidthOfButton@CToolbar@@AEAAHPEAU_TBBUTTONDATA@@PEAUHDC__@@@Z; CToolbar::TBWidthOfButton(_TBBUTTONDATA *,HDC__ *)
0x1800effef  mov     [r14], eax
0x1800efff2  mov     edx, 0Ch; index
0x1800efff7  mov     eax, [rdi+0F8h]
0x1800efffd  mov     rcx, rsi; hdc
0x1800f0000  mov     [r14+4], eax
0x1800f0004  call    cs:__imp_GetDeviceCaps
0x1800f000a  mov     edx, 0Eh; index
0x1800f000f  mov     rcx, rsi; hdc
0x1800f0012  mov     ebx, eax
0x1800f0014  call    cs:__imp_GetDeviceCaps
0x1800f001a  mov     edx, [r14+4]; nHeight
0x1800f001e  mov     r9d, ebx; nBitCount
0x1800f0021  mov     ecx, [r14]; nWidth
0x1800f0024  mov     r8d, eax; nPlanes
0x1800f0027  mov     [rsp+130h+lpBits], 0; lpBits
0x1800f0030  call    cs:__imp_CreateBitmap
0x1800f0036  mov     [r14+10h], rax
0x1800f003a  test    rax, rax
0x1800f003d  jz      loc_1800F0143
0x1800f0043  mov     ecx, [r14]
0x1800f0046  mov     rdx, rax; h
0x1800f0049  mov     [rbp+30h+rc.right], ecx
0x1800f004c  mov     ecx, [r14+4]
0x1800f0050  mov     [rbp+30h+rc.bottom], ecx
0x1800f0053  mov     rcx, rsi; hdc
0x1800f0056  mov     qword ptr [rbp+30h+rc.left], 0
0x1800f005e  call    cs:__imp_SelectObject
0x1800f0064  or      r8d, 0FFFFFFFFh; color
0x1800f0068  lea     rdx, [rbp+30h+rc]; lprect
0x1800f006c  mov     rcx, rsi; hdc
0x1800f006f  mov     [r14+18h], r8d
0x1800f0073  mov     r15, rax
0x1800f0076  call    FillRectClr
0x1800f007b  mov     ebx, [rdi+48h]
0x1800f007e  lea     rax, [rsp+130h+var_F0]
0x1800f0083  mov     [rsp+130h+var_100], rax; struct CTBHotState *
0x1800f0088  mov     ecx, ebx
0x1800f008a  bts     ecx, 0Fh
0x1800f008e  mov     [rsp+130h+var_108], 1; int
0x1800f0096  mov     [rdi+48h], ecx
0x1800f0099  xor     r9d, r9d; yTop
0x1800f009c  movsxd  rcx, dword ptr [rdi+15Ch]
0x1800f00a3  xor     r8d, r8d; xLeft
0x1800f00a6  mov     [rsp+130h+var_F0], ecx
0x1800f00aa  mov     rdx, rsi; HDC
0x1800f00ad  mov     [rsp+130h+var_EC], 2
0x1800f00b5  lea     rcx, [rcx+rcx*4]
0x1800f00b9  shl     rcx, 4
0x1800f00bd  add     rcx, [rdi+90h]
0x1800f00c4  mov     [rsp+130h+lpBits], rcx; struct _TBBUTTONDATA *
0x1800f00c9  mov     rcx, rdi; this
0x1800f00cc  call    ?DrawButton@CToolbar@@AEAAXPEAUHDC__@@HHPEAU_TBBUTTONDATA@@HAEBUCTBHotState@@@Z; CToolbar::DrawButton(HDC__ *,int,int,_TBBUTTONDATA *,int,CTBHotState const &)
0x1800f00d1  mov     edx, [rdi+15Ch]; unsigned int
0x1800f00d7  lea     r8, [rbp+30h+rc]; struct tagRECT *
0x1800f00db  mov     rcx, rdi; this
0x1800f00de  mov     [rdi+48h], ebx
0x1800f00e1  call    ?TB_GetItemRect@CToolbar@@AEAAHIPEAUtagRECT@@@Z; CToolbar::TB_GetItemRect(uint,tagRECT *)
0x1800f00e6  mov     rdx, [rdi+0A0h]; pt
0x1800f00ed  lea     rcx, [rbp+30h+rc]; lprc
0x1800f00f1  call    cs:__imp_PtInRect
0x1800f00f7  test    eax, eax
0x1800f00f9  jz      short loc_1800F0127
0x1800f00fb  test    dword ptr [rdi+58h], 400000h
0x1800f0102  mov     ecx, [rdi+0A0h]
0x1800f0108  jz      short loc_1800F0111
0x1800f010a  mov     eax, [rbp+30h+rc.right]
0x1800f010d  sub     eax, ecx
0x1800f010f  jmp     short loc_1800F0116
0x1800f0111  mov     eax, ecx
0x1800f0113  sub     eax, [rbp+30h+rc.left]
0x1800f0116  mov     [r14+8], eax
0x1800f011a  mov     ecx, [rdi+0A4h]
0x1800f0120  sub     ecx, [rbp+30h+rc.top]
0x1800f0123  mov     [r14+0Ch], ecx
0x1800f0127  mov     rdx, r15; h
0x1800f012a  mov     rcx, rsi; hdc
0x1800f012d  call    cs:__imp_SelectObject
0x1800f0133  mov     rcx, rsi; hdc
0x1800f0136  call    cs:__imp_DeleteDC
0x1800f013c  mov     eax, 1
0x1800f0141  jmp     short loc_1800F0145
0x1800f0143  xor     eax, eax
0x1800f0145  mov     rcx, [rbp+30h+var_30]
0x1800f0149  xor     rcx, rsp; StackCookie
0x1800f014c  call    __security_check_cookie
0x1800f0151  mov     rbx, [rsp+130h+arg_10]
0x1800f0159  add     rsp, 110h
0x1800f0160  pop     r15
0x1800f0162  pop     r14
0x1800f0164  pop     rdi
0x1800f0165  pop     rsi
0x1800f0166  pop     rbp
0x1800f0167  retn
```
