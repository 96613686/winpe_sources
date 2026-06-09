# XHDC::DrawControl(CRectF const &,uint,uint)

- ea: `0x180b452c0`
- end: `0x180b455e1`
- name: `?DrawControl@XHDC@@UEBAJAEBVCRectF@@II@Z`
- size: `801`
- prototype: `__int64 __fastcall(XHDC *__hidden this, const struct CRectF *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1800c8650`
- `0x180b42034`
- `0x180b43d14`
- `0x180b44860`
- `0x180b452c0`
- `0x180b45860`
- `0x180b46b74`
- `0x1810f65c0`

## import_xrefs

- `GDI32!DeleteDC` at `0x180b4553d`
- `GDI32!DeleteDC` at `0x180b4556b`
- `GDI32!DeleteDC` at `0x180b4553d`
- `GDI32!DeleteDC` at `0x180b4556b`
- `GDI32!GetTextColor` at `0x180b453b8`
- `GDI32!GetTextColor` at `0x180b453b8`
- `GDI32!GetBkColor` at `0x180b453a5`
- `GDI32!GetBkColor` at `0x180b453a5`
- `GDI32!DeleteObject` at `0x180b4554e`
- `GDI32!DeleteObject` at `0x180b4555d`
- `GDI32!DeleteObject` at `0x180b4554e`
- `GDI32!DeleteObject` at `0x180b4555d`
- `GDI32!SelectObject` at `0x180b45483`
- `GDI32!SelectObject` at `0x180b4552e`
- `GDI32!SelectObject` at `0x180b45483`
- `GDI32!SelectObject` at `0x180b4552e`
- `GDI32!GetDeviceCaps` at `0x180b45322`
- `GDI32!GetDeviceCaps` at `0x180b45339`
- `GDI32!GetDeviceCaps` at `0x180b45322`
- `GDI32!GetDeviceCaps` at `0x180b45339`
- `GDI32!BitBlt` at `0x180b454b9`
- `GDI32!BitBlt` at `0x180b454b9`
- `GDI32!CreateCompatibleBitmap` at `0x180b45453`
- `GDI32!CreateCompatibleBitmap` at `0x180b45453`
- `GDI32!CreateCompatibleDC` at `0x180b4541d`
- `GDI32!CreateCompatibleDC` at `0x180b4541d`
- `GDI32!SetTextColor` at `0x180b453e3`
- `GDI32!SetTextColor` at `0x180b455af`
- `GDI32!SetTextColor` at `0x180b453e3`
- `GDI32!SetTextColor` at `0x180b455af`
- `GDI32!SetBkColor` at `0x180b453d1`
- `GDI32!SetBkColor` at `0x180b4559b`
- `GDI32!SetBkColor` at `0x180b453d1`
- `GDI32!SetBkColor` at `0x180b4559b`
- `USER32!DrawFrameControl` at `0x180b454d7`
- `USER32!DrawFrameControl` at `0x180b454d7`

## pseudocode

```c
__int64 __fastcall XHDC::DrawControl(HDC *this, const struct CRectF *a2, UINT a3, UINT a4)
{
  int DeviceCaps; // ebx
  int v6; // eax
  int v7; // r14d
  COLORREF BkColor; // r13d
  unsigned int ObjectType; // eax
  HDC hdcSrc; // rsi
  LONG cy; // r15d
  LONG v13; // r12d
  HBITMAP CompatibleBitmap; // rax
  HGDIOBJ v15; // rbx
  const struct CWorldTransform *v16; // r8
  const struct XHDC *v17; // rax
  COLORREF color; // [rsp+60h] [rbp-A8h]
  struct tagRECT color_8; // [rsp+68h] [rbp-A0h] BYREF
  HGDIOBJ ho; // [rsp+78h] [rbp-90h]
  struct tagRECT v23; // [rsp+80h] [rbp-88h] BYREF
  _BYTE v24[240]; // [rsp+98h] [rbp-70h] BYREF

  DeviceCaps = GetDeviceCaps(this[4], 2);
  v6 = GetDeviceCaps(this[4], 24);
  color_8 = 0;
  v7 = v6;
  CRect::SetRect((CRect *)&color_8, *(float *)a2, *((float *)a2 + 1), *((float *)a2 + 2), *((float *)a2 + 3), 0);
  if ( DeviceCaps && DeviceCaps != 2 && DeviceCaps != 5 )
    return 1;
  if ( v7 == 2 )
  {
    BkColor = GetBkColor(this[4]);
    color = GetTextColor(this[4]);
    SetBkColor(this[4], 0xFFFFFFu);
    SetTextColor(this[4], 0);
  }
  else
  {
    BkColor = 0;
    color = 0;
  }
  ObjectType = XHDC::GetObjectType((XHDC *)this);
  if ( (ObjectType == 4 || ObjectType == 12) && v7 == 2 )
  {
    hdcSrc = CreateCompatibleDC(this[4]);
    if ( hdcSrc )
    {
      cy = color_8.bottom - color_8.top;
      v13 = color_8.right - color_8.left;
      CompatibleBitmap = CreateCompatibleBitmap(this[4], color_8.right - color_8.left, color_8.bottom - color_8.top);
      ho = CompatibleBitmap;
      if ( CompatibleBitmap )
      {
        v23.right = v13;
        *(_QWORD *)&v23.left = 0;
        v23.bottom = cy;
        v15 = SelectObject(hdcSrc, CompatibleBitmap);
        BitBlt(hdcSrc, 0, 0, v13, cy, hdcSrc, 0, 0, 0xFF0062u);
        DrawFrameControl(hdcSrc, &v23, a3, a4);
        v17 = XHDC::XHDC((XHDC *)v24, hdcSrc, v16);
        XHDC::BitBlt((XHDC *)this, color_8.left, color_8.top, v13, cy, v17, 0, 0, 0xCC0020u);
        XHDC::~XHDC((XHDC *)v24);
        SelectObject(hdcSrc, v15);
        DeleteDC(hdcSrc);
        DeleteObject(ho);
        DeleteObject(v15);
LABEL_16:
        SetBkColor(this[4], BkColor);
        SetTextColor(this[4], color);
        return 0;
      }
      DeleteDC(hdcSrc);
    }
  }
  XHDC::DrawFrameControl((XHDC *)this, &color_8, a3, a4);
  if ( v7 == 2 )
    goto LABEL_16;
  return 0;
}

```

## disassembly

```asm
0x180b452c0  mov     rax, rsp
0x180b452c3  mov     [rax+20h], r9d
0x180b452c7  mov     [rax+18h], r8d
0x180b452cb  mov     [rax+10h], rdx
0x180b452cf  mov     [rax+8], rcx
0x180b452d3  push    rbp
0x180b452d4  push    rbx
0x180b452d5  push    rsi
0x180b452d6  push    rdi
0x180b452d7  push    r12
0x180b452d9  push    r13
0x180b452db  push    r14
0x180b452dd  push    r15
0x180b452df  lea     rbp, [rax-0D8h]
0x180b452e6  sub     rsp, 198h
0x180b452ed  mov     rax, cs:__security_cookie
0x180b452f4  xor     rax, rsp
0x180b452f7  mov     [rbp+0D0h+var_50], rax
0x180b452fe  mov     eax, [rbp+0D0h+arg_10]
0x180b45304  mov     edx, 2; index
0x180b45309  mov     rdi, [rbp+0D0h+arg_0]
0x180b45310  mov     [rsp+54h], eax
0x180b45314  mov     eax, [rbp+0D0h+arg_18]
0x180b4531a  mov     [rsp+1D0h+var_180], eax
0x180b4531e  mov     rcx, [rdi+20h]; hdc
0x180b45322  call    cs:__imp_GetDeviceCaps
0x180b45329  nop     dword ptr [rax+rax+00h]
0x180b4532e  mov     rcx, [rdi+20h]; hdc
0x180b45332  mov     edx, 18h; index
0x180b45337  mov     ebx, eax
0x180b45339  call    cs:__imp_GetDeviceCaps
0x180b45340  nop     dword ptr [rax+rax+00h]
0x180b45345  mov     rcx, [rbp+0D0h+arg_8]
0x180b4534c  xorps   xmm0, xmm0
0x180b4534f  movdqu  xmmword ptr [rsp+1D0h+color+8], xmm0
0x180b45355  mov     dword ptr [rsp+1D0h+hdcSrc], 0; int
0x180b4535d  mov     r14d, eax
0x180b45360  movss   xmm0, dword ptr [rcx+0Ch]
0x180b45365  movss   xmm3, dword ptr [rcx+8]; float
0x180b4536a  movss   xmm2, dword ptr [rcx+4]; float
0x180b4536f  movss   xmm1, dword ptr [rcx]; float
0x180b45373  lea     rcx, [rsp+1D0h+color+8]; this
0x180b45378  movss   [rsp+1D0h+cy], xmm0; float
0x180b4537e  call    ?SetRect@CRect@@QEAAXMMMMH@Z; CRect::SetRect(float,float,float,float,int)
0x180b45383  test    ebx, ebx
0x180b45385  jz      short loc_180B4539B
0x180b45387  cmp     ebx, 2
0x180b4538a  jz      short loc_180B4539B
0x180b4538c  cmp     ebx, 5
0x180b4538f  jz      short loc_180B4539B
0x180b45391  mov     eax, 1
0x180b45396  jmp     loc_180B455BD
0x180b4539b  cmp     r14d, 2
0x180b4539f  jnz     short loc_180B453F1
0x180b453a1  mov     rcx, [rdi+20h]; hdc
0x180b453a5  call    cs:__imp_GetBkColor
0x180b453ac  nop     dword ptr [rax+rax+00h]
0x180b453b1  mov     rcx, [rdi+20h]; hdc
0x180b453b5  mov     r13d, eax
0x180b453b8  call    cs:__imp_GetTextColor
0x180b453bf  nop     dword ptr [rax+rax+00h]
0x180b453c4  mov     rcx, [rdi+20h]; hdc
0x180b453c8  mov     edx, 0FFFFFFh; color
0x180b453cd  mov     [rsp+1D0h+color], eax
0x180b453d1  call    cs:__imp_SetBkColor
0x180b453d8  nop     dword ptr [rax+rax+00h]
0x180b453dd  mov     rcx, [rdi+20h]; hdc
0x180b453e1  xor     edx, edx; color
0x180b453e3  call    cs:__imp_SetTextColor
0x180b453ea  nop     dword ptr [rax+rax+00h]
0x180b453ef  jmp     short loc_180B453F9
0x180b453f1  xor     r13d, r13d
0x180b453f4  mov     [rsp+1D0h+color], r13d
0x180b453f9  mov     rcx, rdi; this
0x180b453fc  call    ?GetObjectType@XHDC@@QEBAKXZ; XHDC::GetObjectType(void)
0x180b45401  cmp     eax, 4
0x180b45404  jz      short loc_180B4540F
0x180b45406  cmp     eax, 0Ch
0x180b45409  jnz     loc_180B45577
0x180b4540f  cmp     r14d, 2
0x180b45413  jnz     loc_180B45577
0x180b45419  mov     rcx, [rdi+20h]; hdc
0x180b4541d  call    cs:__imp_CreateCompatibleDC
0x180b45424  nop     dword ptr [rax+rax+00h]
0x180b45429  mov     rsi, rax
0x180b4542c  test    rax, rax
0x180b4542f  jz      loc_180B45577
0x180b45435  mov     r15d, dword ptr [rsp+1D0h+var_168+4]
0x180b4543a  mov     r12d, dword ptr [rsp+1D0h+var_168]
0x180b4543f  sub     r15d, [rsp+1D0h+color+0Ch]
0x180b45444  sub     r12d, [rsp+1D0h+color+8]
0x180b45449  mov     r8d, r15d; cy
0x180b4544c  mov     rcx, [rdi+20h]; hdc
0x180b45450  mov     edx, r12d; cx
0x180b45453  call    cs:__imp_CreateCompatibleBitmap
0x180b4545a  nop     dword ptr [rax+rax+00h]
0x180b4545f  mov     [rsp+1D0h+ho], rax
0x180b45464  mov     rcx, rsi; hdc
0x180b45467  test    rax, rax
0x180b4546a  jz      loc_180B4556B
0x180b45470  xor     r14d, r14d
0x180b45473  mov     [rbp+0D0h+var_158.right], r12d
0x180b45477  mov     rdx, rax; h
0x180b4547a  mov     qword ptr [rsp+1D0h+var_158.left], r14
0x180b4547f  mov     [rbp+0D0h+var_158.bottom], r15d
0x180b45483  call    cs:__imp_SelectObject
0x180b4548a  nop     dword ptr [rax+rax+00h]
0x180b4548f  mov     dword ptr [rsp+40h], 0FF0062h; rop
0x180b45497  mov     r9d, r12d; cx
0x180b4549a  mov     [rsp+1D0h+y1], r14d; y1
0x180b4549f  xor     r8d, r8d; y
0x180b454a2  mov     [rsp+1D0h+x1], r14d; x1
0x180b454a7  xor     edx, edx; x
0x180b454a9  mov     [rsp+1D0h+hdcSrc], rsi; hdcSrc
0x180b454ae  mov     rcx, rsi; hdc
0x180b454b1  mov     [rsp+1D0h+cy], r15d; cy
0x180b454b6  mov     rbx, rax
0x180b454b9  call    cs:__imp_BitBlt
0x180b454c0  nop     dword ptr [rax+rax+00h]
0x180b454c5  mov     r9d, [rsp+1D0h+var_180]; UINT
0x180b454ca  lea     rdx, [rsp+1D0h+var_158]; LPRECT
0x180b454cf  mov     r8d, [rsp+54h]; UINT
0x180b454d4  mov     rcx, rsi; HDC
0x180b454d7  call    cs:__imp_DrawFrameControl
0x180b454de  nop     dword ptr [rax+rax+00h]
0x180b454e3  mov     rdx, rsi; HDC
0x180b454e6  lea     rcx, [rbp+0D0h+var_140]; this
0x180b454ea  call    ??0XHDC@@QEAA@PEAUHDC__@@PEBVCWorldTransform@@@Z; XHDC::XHDC(HDC__ *,CWorldTransform const *)
0x180b454ef  mov     r8d, [rsp+1D0h+color+0Ch]; int
0x180b454f4  mov     r9d, r12d; int
0x180b454f7  mov     edx, [rsp+1D0h+color+8]; int
0x180b454fb  mov     rcx, rdi; this
0x180b454fe  mov     dword ptr [rsp+40h], 0CC0020h; unsigned int
0x180b45506  mov     [rsp+1D0h+y1], r14d; int
0x180b4550b  mov     [rsp+1D0h+x1], r14d; int
0x180b45510  mov     [rsp+1D0h+hdcSrc], rax; struct XHDC *
0x180b45515  mov     [rsp+1D0h+cy], r15d; int
0x180b4551a  call    ?BitBlt@XHDC@@QEBAHHHHHAEBV1@HHK@Z; XHDC::BitBlt(int,int,int,int,XHDC const &,int,int,ulong)
0x180b4551f  lea     rcx, [rbp+0D0h+var_140]; this
0x180b45523  call    ??1XHDC@@QEAA@XZ; XHDC::~XHDC(void)
0x180b45528  mov     rdx, rbx; h
0x180b4552b  mov     rcx, rsi; hdc
0x180b4552e  call    cs:__imp_SelectObject
0x180b45535  nop     dword ptr [rax+rax+00h]
0x180b4553a  mov     rcx, rsi; hdc
0x180b4553d  call    cs:__imp_DeleteDC
0x180b45544  nop     dword ptr [rax+rax+00h]
0x180b45549  mov     rcx, [rsp+1D0h+ho]; ho
0x180b4554e  call    cs:__imp_DeleteObject
0x180b45555  nop     dword ptr [rax+rax+00h]
0x180b4555a  mov     rcx, rbx; ho
0x180b4555d  call    cs:__imp_DeleteObject
0x180b45564  nop     dword ptr [rax+rax+00h]
0x180b45569  jmp     short loc_180B45594
0x180b4556b  call    cs:__imp_DeleteDC
0x180b45572  nop     dword ptr [rax+rax+00h]
0x180b45577  mov     r9d, [rsp+1D0h+var_180]; unsigned int
0x180b4557c  lea     rdx, [rsp+1D0h+color+8]; struct tagRECT *
0x180b45581  mov     r8d, [rsp+54h]; unsigned int
0x180b45586  mov     rcx, rdi; this
0x180b45589  call    ?DrawFrameControl@XHDC@@QEBAHPEAUtagRECT@@II@Z; XHDC::DrawFrameControl(tagRECT *,uint,uint)
0x180b4558e  cmp     r14d, 2
0x180b45592  jnz     short loc_180B455BB
0x180b45594  mov     rcx, [rdi+20h]; hdc
0x180b45598  mov     edx, r13d; color
0x180b4559b  call    cs:__imp_SetBkColor
0x180b455a2  nop     dword ptr [rax+rax+00h]
0x180b455a7  mov     edx, [rsp+1D0h+color]; color
0x180b455ab  mov     rcx, [rdi+20h]; hdc
0x180b455af  call    cs:__imp_SetTextColor
0x180b455b6  nop     dword ptr [rax+rax+00h]
0x180b455bb  xor     eax, eax
0x180b455bd  mov     rcx, [rbp+0D0h+var_50]
0x180b455c4  xor     rcx, rsp; StackCookie
0x180b455c7  call    __security_check_cookie
0x180b455cc  add     rsp, 198h
0x180b455d3  pop     r15
0x180b455d5  pop     r14
0x180b455d7  pop     r13
0x180b455d9  pop     r12
0x180b455db  pop     rdi
0x180b455dc  pop     rsi
0x180b455dd  pop     rbx
0x180b455de  pop     rbp
0x180b455df  retn
```
