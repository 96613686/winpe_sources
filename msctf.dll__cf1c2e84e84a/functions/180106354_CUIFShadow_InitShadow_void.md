# CUIFShadow::InitShadow(void)

- ea: `0x180106354`
- end: `0x180106726`
- name: `?InitShadow@CUIFShadow@@IEAAXXZ`
- size: `978`
- prototype: `void __fastcall(CUIFShadow *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180106754`
- `0x180106820`
- `0x1801068f0`

## callees

- `0x18009eaea`
- `0x180106354`
- `0x180106a60`

## import_xrefs

- `USER32!GetWindowLongW` at `0x1801063be`
- `USER32!GetWindowLongW` at `0x1801063be`
- `USER32!GetWindowRect` at `0x1801063e5`
- `USER32!GetWindowRect` at `0x1801063e5`
- `USER32!UpdateLayeredWindow` at `0x1801066d7`
- `USER32!UpdateLayeredWindow` at `0x1801066d7`
- `USER32!ReleaseDC` at `0x180106427`
- `USER32!ReleaseDC` at `0x180106491`
- `USER32!ReleaseDC` at `0x1801066ee`
- `USER32!ReleaseDC` at `0x180106427`
- `USER32!ReleaseDC` at `0x180106491`
- `USER32!ReleaseDC` at `0x1801066ee`
- `USER32!GetDC` at `0x1801063ff`
- `USER32!GetDC` at `0x1801063ff`
- `USER32!SetWindowLongW` at `0x1801063d4`
- `USER32!SetWindowLongW` at `0x1801063d4`
- `GDI32!DeleteObject` at `0x180106700`
- `GDI32!DeleteObject` at `0x180106700`
- `GDI32!CreateCompatibleDC` at `0x180106414`
- `GDI32!CreateCompatibleDC` at `0x180106414`
- `GDI32!DeleteDC` at `0x18010649a`
- `GDI32!DeleteDC` at `0x1801066f7`
- `GDI32!DeleteDC` at `0x18010649a`
- `GDI32!DeleteDC` at `0x1801066f7`
- `GDI32!SelectObject` at `0x180106699`
- `GDI32!SelectObject` at `0x1801066e3`
- `GDI32!SelectObject` at `0x180106699`
- `GDI32!SelectObject` at `0x1801066e3`
- `GDI32!CreateDIBSection` at `0x18010647c`
- `GDI32!CreateDIBSection` at `0x18010647c`

## pseudocode

```c
void __fastcall CUIFShadow::InitShadow(HWND *this)
{
  LONG WindowLongW; // eax
  HDC DC; // rax
  HDC v4; // rdi
  HDC CompatibleDC; // rsi
  HBITMAP v6; // r12
  LONG cy; // r10d
  LONG cx; // r8d
  int i; // r9d
  char v10; // r11
  int v11; // edx
  __int64 v12; // rax
  int v13; // edx
  int v14; // eax
  int j; // r9d
  int k; // r11d
  char v17; // r14
  HGDIOBJ v18; // rbx
  SIZE psize; // [rsp+50h] [rbp-59h] BYREF
  BLENDFUNCTION pblend; // [rsp+58h] [rbp-51h] BYREF
  void *ppvBits; // [rsp+60h] [rbp-49h] BYREF
  POINT pptSrc; // [rsp+68h] [rbp-41h] BYREF
  struct tagRECT Rect; // [rsp+70h] [rbp-39h] BYREF
  BITMAPINFO pbmi; // [rsp+80h] [rbp-29h] BYREF

  psize = 0;
  ppvBits = 0;
  pptSrc = 0;
  Rect = 0;
  pblend = 0;
  memset(&pbmi, 0, sizeof(pbmi));
  if ( *((_DWORD *)this + 65) )
  {
    WindowLongW = GetWindowLongW(this[21], -20);
    SetWindowLongW(this[21], -20, WindowLongW | 0x80000);
    GetWindowRect(this[21], &Rect);
    psize.cx = Rect.right - Rect.left;
    psize.cy = Rect.bottom - Rect.top;
    DC = GetDC(0);
    v4 = DC;
    if ( DC )
    {
      CompatibleDC = CreateCompatibleDC(DC);
      if ( CompatibleDC )
      {
        *(SIZE *)&pbmi.bmiHeader.biWidth = psize;
        pbmi.bmiHeader.biSize = 40;
        *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
        pbmi.bmiHeader.biXPelsPerMeter = 100;
        *(_QWORD *)&pbmi.bmiHeader.biYPelsPerMeter = 100;
        pbmi.bmiHeader.biSizeImage = 0;
        pbmi.bmiHeader.biClrImportant = 0;
        v6 = CreateDIBSection(v4, &pbmi, 0, &ppvBits, 0, 0);
        if ( ppvBits )
        {
          memset_0(ppvBits, 0, psize.cy * (32 * psize.cx / 8));
          cy = psize.cy;
          cx = psize.cx;
          for ( i = 0; i < 5; ++i )
          {
            v10 = *((_BYTE *)&dword_18012629C + (unsigned int)i);
            if ( i <= (cy + 1) / 2 )
            {
              v11 = 5;
              if ( cx - 5 > 5 )
              {
                do
                {
                  v12 = v11++;
                  *((_BYTE *)ppvBits + 4 * v12 + 4 * i * cx + 3) = v10;
                  cx = psize.cx;
                }
                while ( v11 < psize.cx - 5 );
                cy = psize.cy;
              }
            }
            if ( i <= (cx + 1) / 2 )
            {
              v13 = 5;
              if ( cy - 5 > 5 )
              {
                do
                {
                  v14 = v13 * cx;
                  ++v13;
                  *((char *)ppvBits + 4 * (cx - i) + 4 * (__int64)v14 - 1) = v10;
                  cy = psize.cy;
                  cx = psize.cx;
                }
                while ( v13 < psize.cy - 5 );
              }
            }
          }
          for ( j = 0; j < 5; ++j )
          {
            for ( k = 0; k < 5; ++k )
            {
              v17 = *((_BYTE *)qword_180126280 + 5 * j - (unsigned int)k + 4);
              if ( j <= (cy + 1) / 2 && k <= (cx + 1) / 2 )
              {
                *((char *)ppvBits + 4 * (cx - k) + 4 * (__int64)(cx * (cy - j - 1)) - 1) = v17;
                cy = psize.cy;
                cx = psize.cx;
              }
              if ( j <= (cy + 1) / 2 && k <= (cx + 1) / 2 )
              {
                *((_BYTE *)ppvBits + 4 * (unsigned int)k + 4 * (__int64)(cx * (j + 1)) + 3) = v17;
                cy = psize.cy;
                cx = psize.cx;
              }
              if ( j <= (cy + 1) / 2 && k <= (cx + 1) / 2 )
              {
                *((char *)ppvBits + 4 * (cx - k) + 4 * (__int64)(cx * (j + 1)) - 1) = v17;
                cy = psize.cy;
                cx = psize.cx;
              }
            }
          }
          pptSrc = 0;
          pblend = (BLENDFUNCTION)33488896;
          v18 = SelectObject(CompatibleDC, v6);
          UpdateLayeredWindow(this[21], v4, 0, &psize, CompatibleDC, &pptSrc, 0, &pblend, 2u);
          SelectObject(CompatibleDC, v18);
          ReleaseDC(0, v4);
          DeleteDC(CompatibleDC);
          DeleteObject(v6);
        }
        else
        {
          ReleaseDC(0, v4);
          DeleteDC(CompatibleDC);
        }
      }
      else
      {
        ReleaseDC(0, v4);
      }
    }
  }
}

```

## disassembly

```asm
0x180106354  push    rbp
0x180106356  push    rbx
0x180106357  push    rsi
0x180106358  push    rdi
0x180106359  push    r12
0x18010635b  push    r13
0x18010635d  push    r14
0x18010635f  push    r15
0x180106361  lea     rbp, [rsp-1Fh]
0x180106366  sub     rsp, 0C8h
0x18010636d  mov     rax, cs:__security_cookie
0x180106374  xor     rax, rsp
0x180106377  mov     [rbp+57h+var_50], rax
0x18010637b  xor     r13d, r13d
0x18010637e  xorps   xmm0, xmm0
0x180106381  mov     r15, rcx
0x180106384  mov     qword ptr [rbp+57h+psize.cx], r13
0x180106388  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biCompression], xmm0
0x18010638c  mov     [rbp+57h+ppvBits], r13
0x180106390  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biYPelsPerMeter], xmm0
0x180106394  mov     qword ptr [rbp+57h+pptSrc.x], r13
0x180106398  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x18010639c  mov     dword ptr [rbp+57h+var_A8.BlendOp], r13d
0x1801063a0  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biSize], xmm0
0x1801063a4  cmp     [rcx+104h], r13d
0x1801063ab  jz      loc_180106706
0x1801063b1  mov     rcx, [rcx+0A8h]; hWnd
0x1801063b8  lea     ebx, [r13-14h]
0x1801063bc  mov     edx, ebx; nIndex
0x1801063be  call    cs:__imp_GetWindowLongW
0x1801063c4  mov     rcx, [r15+0A8h]; hWnd
0x1801063cb  mov     edx, ebx; nIndex
0x1801063cd  bts     eax, 13h
0x1801063d1  mov     r8d, eax; dwNewLong
0x1801063d4  call    cs:__imp_SetWindowLongW
0x1801063da  mov     rcx, [r15+0A8h]; hWnd
0x1801063e1  lea     rdx, [rbp+57h+Rect]; lpRect
0x1801063e5  call    cs:__imp_GetWindowRect
0x1801063eb  mov     eax, [rbp+57h+Rect.right]
0x1801063ee  xor     ecx, ecx; hWnd
0x1801063f0  sub     eax, [rbp+57h+Rect.left]
0x1801063f3  mov     [rbp+57h+psize.cx], eax
0x1801063f6  mov     eax, [rbp+57h+Rect.bottom]
0x1801063f9  sub     eax, [rbp+57h+Rect.top]
0x1801063fc  mov     [rbp+57h+psize.cy], eax
0x1801063ff  call    cs:__imp_GetDC
0x180106405  mov     rdi, rax
0x180106408  test    rax, rax
0x18010640b  jz      loc_180106706
0x180106411  mov     rcx, rax; hdc
0x180106414  call    cs:__imp_CreateCompatibleDC
0x18010641a  mov     rsi, rax
0x18010641d  test    rax, rax
0x180106420  jnz     short loc_180106432
0x180106422  mov     rdx, rdi; hDC
0x180106425  xor     ecx, ecx; hWnd
0x180106427  call    cs:__imp_ReleaseDC
0x18010642d  jmp     loc_180106706
0x180106432  mov     eax, [rbp+57h+psize.cx]
0x180106435  lea     r9, [rbp+57h+ppvBits]; ppvBits
0x180106439  mov     [rbp+57h+pbmi.bmiHeader.biWidth], eax
0x18010643c  lea     rdx, [rbp+57h+pbmi]; pbmi
0x180106440  mov     eax, [rbp+57h+psize.cy]
0x180106443  mov     ebx, 1
0x180106448  mov     [rbp+57h+pbmi.bmiHeader.biHeight], eax
0x18010644b  xor     r8d, r8d; usage
0x18010644e  mov     [rsp+100h+offset], r13d; offset
0x180106453  mov     rcx, rdi; hdc
0x180106456  mov     [rbp+57h+pbmi.bmiHeader.biSize], 28h ; '('
0x18010645d  lea     eax, [rbx+63h]
0x180106460  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biPlanes], 200001h
0x180106468  mov     [rbp+57h+pbmi.bmiHeader.biXPelsPerMeter], eax
0x18010646b  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biYPelsPerMeter], rax
0x18010646f  mov     [rbp+57h+pbmi.bmiHeader.biSizeImage], r13d
0x180106473  mov     [rbp+57h+pbmi.bmiHeader.biClrImportant], r13d
0x180106477  mov     [rsp+100h+hSection], r13; hSection
0x18010647c  call    cs:__imp_CreateDIBSection
0x180106482  mov     rcx, [rbp+57h+ppvBits]; void *
0x180106486  mov     r12, rax
0x180106489  test    rcx, rcx
0x18010648c  jnz     short loc_1801064A5
0x18010648e  mov     rdx, rdi; hDC
0x180106491  call    cs:__imp_ReleaseDC
0x180106497  mov     rcx, rsi; hdc
0x18010649a  call    cs:__imp_DeleteDC
0x1801064a0  jmp     loc_180106706
0x1801064a5  mov     eax, [rbp+57h+psize.cx]
0x1801064a8  mov     r8d, 8
0x1801064ae  shl     eax, 5
0x1801064b1  cdq
0x1801064b2  idiv    r8d
0x1801064b5  xor     edx, edx; Val
0x1801064b7  imul    eax, [rbp+57h+psize.cy]
0x1801064bb  movsxd  r8, eax; Size
0x1801064be  call    memset_0
0x1801064c3  mov     r10d, [rbp+57h+psize.cy]
0x1801064c7  mov     ecx, 2
0x1801064cc  mov     r8d, [rbp+57h+psize.cx]
0x1801064d0  mov     r9d, r13d
0x1801064d3  lea     r14d, [rcx+3]
0x1801064d7  mov     eax, r9d
0x1801064da  lea     r11, dword_18012629C
0x1801064e1  mov     r11b, [rax+r11]
0x1801064e5  lea     eax, [r10+1]
0x1801064e9  cdq
0x1801064ea  idiv    ecx
0x1801064ec  cmp     r9d, eax
0x1801064ef  jg      short loc_18010652A
0x1801064f1  lea     eax, [r8-5]
0x1801064f5  mov     edx, r14d
0x1801064f8  cmp     eax, r14d
0x1801064fb  jle     short loc_18010652A
0x1801064fd  imul    r8d, r9d
0x180106501  movsxd  rax, edx
0x180106504  add     edx, ebx
0x180106506  movsxd  rcx, r8d
0x180106509  add     rcx, rax
0x18010650c  mov     rax, [rbp+57h+ppvBits]
0x180106510  mov     [rax+rcx*4+3], r11b
0x180106515  mov     r8d, [rbp+57h+psize.cx]
0x180106519  lea     eax, [r8-5]
0x18010651d  cmp     edx, eax
0x18010651f  jl      short loc_1801064FD
0x180106521  mov     r10d, [rbp+57h+psize.cy]
0x180106525  mov     ecx, 2
0x18010652a  lea     eax, [r8+1]
0x18010652e  cdq
0x18010652f  idiv    ecx
0x180106531  cmp     r9d, eax
0x180106534  jg      short loc_180106574
0x180106536  lea     eax, [r10-5]
0x18010653a  mov     edx, r14d
0x18010653d  cmp     eax, r14d
0x180106540  jle     short loc_180106574
0x180106542  mov     eax, r8d
0x180106545  sub     r8d, r9d
0x180106548  imul    eax, edx
0x18010654b  add     edx, ebx
0x18010654d  movsxd  rcx, eax
0x180106550  movsxd  rax, r8d
0x180106553  add     rcx, rax
0x180106556  mov     rax, [rbp+57h+ppvBits]
0x18010655a  mov     [rax+rcx*4-1], r11b
0x18010655f  mov     r10d, [rbp+57h+psize.cy]
0x180106563  mov     r8d, [rbp+57h+psize.cx]
0x180106567  lea     eax, [r10-5]
0x18010656b  cmp     edx, eax
0x18010656d  jl      short loc_180106542
0x18010656f  mov     ecx, 2
0x180106574  add     r9d, ebx
0x180106577  cmp     r9d, r14d
0x18010657a  jl      loc_1801064D7
0x180106580  mov     r9d, r13d
0x180106583  mov     eax, r9d
0x180106586  mov     r11d, r13d
0x180106589  mov     r13d, 2
0x18010658f  lea     rbx, [rax+rax*4]
0x180106593  lea     rax, qword_180126280
0x18010659a  add     rbx, rax
0x18010659d  mov     eax, r11d
0x1801065a0  mov     rcx, rbx
0x1801065a3  sub     rcx, rax
0x1801065a6  lea     eax, [r10+1]
0x1801065aa  cdq
0x1801065ab  idiv    r13d
0x1801065ae  mov     r14b, [rcx+4]
0x1801065b2  cmp     r9d, eax
0x1801065b5  jg      short loc_1801065EB
0x1801065b7  lea     eax, [r8+1]
0x1801065bb  cdq
0x1801065bc  idiv    r13d
0x1801065bf  cmp     r11d, eax
0x1801065c2  jg      short loc_1801065EB
0x1801065c4  sub     r10d, r9d
0x1801065c7  dec     r10d
0x1801065ca  imul    r10d, r8d
0x1801065ce  sub     r8d, r11d
0x1801065d1  movsxd  rax, r8d
0x1801065d4  movsxd  rcx, r10d
0x1801065d7  add     rcx, rax
0x1801065da  mov     rax, [rbp+57h+ppvBits]
0x1801065de  mov     [rax+rcx*4-1], r14b
0x1801065e3  mov     r10d, [rbp+57h+psize.cy]
0x1801065e7  mov     r8d, [rbp+57h+psize.cx]
0x1801065eb  lea     eax, [r10+1]
0x1801065ef  cdq
0x1801065f0  idiv    r13d
0x1801065f3  cmp     r9d, eax
0x1801065f6  jg      short loc_180106627
0x1801065f8  lea     eax, [r8+1]
0x1801065fc  cdq
0x1801065fd  idiv    r13d
0x180106600  cmp     r11d, eax
0x180106603  jg      short loc_180106627
0x180106605  lea     eax, [r9+1]
0x180106609  imul    eax, r8d
0x18010660d  movsxd  rcx, eax
0x180106610  mov     eax, r11d
0x180106613  add     rcx, rax
0x180106616  mov     rax, [rbp+57h+ppvBits]
0x18010661a  mov     [rax+rcx*4+3], r14b
0x18010661f  mov     r10d, [rbp+57h+psize.cy]
0x180106623  mov     r8d, [rbp+57h+psize.cx]
0x180106627  lea     eax, [r10+1]
0x18010662b  cdq
0x18010662c  idiv    r13d
0x18010662f  cmp     r9d, eax
0x180106632  jg      short loc_180106666
0x180106634  lea     eax, [r8+1]
0x180106638  cdq
0x180106639  idiv    r13d
0x18010663c  cmp     r11d, eax
0x18010663f  jg      short loc_180106666
0x180106641  lea     eax, [r9+1]
0x180106645  imul    eax, r8d
0x180106649  sub     r8d, r11d
0x18010664c  movsxd  rcx, eax
0x18010664f  movsxd  rax, r8d
0x180106652  add     rcx, rax
0x180106655  mov     rax, [rbp+57h+ppvBits]
0x180106659  mov     [rax+rcx*4-1], r14b
0x18010665e  mov     r10d, [rbp+57h+psize.cy]
0x180106662  mov     r8d, [rbp+57h+psize.cx]
0x180106666  inc     r11d
0x180106669  mov     r14d, 5
0x18010666f  cmp     r11d, r14d
0x180106672  jl      loc_18010659D
0x180106678  inc     r9d
0x18010667b  lea     r13d, [r14-5]
0x18010667f  cmp     r9d, r14d
0x180106682  jl      loc_180106583
0x180106688  mov     rdx, r12; h
0x18010668b  mov     qword ptr [rbp+57h+pptSrc.x], r13
0x18010668f  mov     rcx, rsi; hdc
0x180106692  mov     dword ptr [rbp+57h+var_A8.BlendOp], 1FF0000h
0x180106699  call    cs:__imp_SelectObject
0x18010669f  mov     rcx, [r15+0A8h]; hWnd
0x1801066a6  lea     r9, [rbp+57h+psize]; psize
0x1801066aa  mov     [rsp+100h+dwFlags], 2; dwFlags
0x1801066b2  mov     rbx, rax
0x1801066b5  lea     rax, [rbp+57h+var_A8]
0x1801066b9  xor     r8d, r8d; pptDst
0x1801066bc  mov     [rsp+100h+pblend], rax; pblend
0x1801066c1  mov     rdx, rdi; hdcDst
0x1801066c4  lea     rax, [rbp+57h+pptSrc]
0x1801066c8  mov     [rsp+100h+crKey], r13d; crKey
0x1801066cd  mov     qword ptr [rsp+100h+offset], rax; pptSrc
0x1801066d2  mov     [rsp+100h+hSection], rsi; hdcSrc
0x1801066d7  call    cs:__imp_UpdateLayeredWindow
0x1801066dd  mov     rdx, rbx; h
0x1801066e0  mov     rcx, rsi; hdc
0x1801066e3  call    cs:__imp_SelectObject
0x1801066e9  mov     rdx, rdi; hDC
0x1801066ec  xor     ecx, ecx; hWnd
0x1801066ee  call    cs:__imp_ReleaseDC
0x1801066f4  mov     rcx, rsi; hdc
0x1801066f7  call    cs:__imp_DeleteDC
0x1801066fd  mov     rcx, r12; ho
0x180106700  call    cs:__imp_DeleteObject
0x180106706  mov     rcx, [rbp+57h+var_50]
0x18010670a  xor     rcx, rsp; StackCookie
0x18010670d  call    __security_check_cookie
0x180106712  add     rsp, 0C8h
0x180106719  pop     r15
0x18010671b  pop     r14
0x18010671d  pop     r13
0x18010671f  pop     r12
0x180106721  pop     rdi
0x180106722  pop     rsi
0x180106723  pop     rbx
0x180106724  pop     rbp
0x180106725  retn
```
