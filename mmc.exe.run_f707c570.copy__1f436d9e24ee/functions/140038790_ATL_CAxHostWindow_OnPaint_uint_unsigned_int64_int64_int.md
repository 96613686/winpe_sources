# ATL::CAxHostWindow::OnPaint(uint,unsigned __int64,__int64,int &)

- ea: `0x140038790`
- end: `0x1400389f7`
- name: `?OnPaint@CAxHostWindow@ATL@@QEAA_JI_K_JAEAH@Z`
- size: `615`
- prototype: `__int64 __fastcall(ATL::CAxHostWindow *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001cf70`

## callees

- `0x140038790`
- `0x140062455`
- `0x1400e9e10`
- `0x1400f3010`

## import_xrefs

- `GDI32!SelectObject` at `0x14003885a`
- `GDI32!SelectObject` at `0x140038931`
- `GDI32!SelectObject` at `0x14003885a`
- `GDI32!SelectObject` at `0x140038931`
- `GDI32!CreateSolidBrush` at `0x140038872`
- `GDI32!CreateSolidBrush` at `0x1400389b8`
- `GDI32!CreateSolidBrush` at `0x140038872`
- `GDI32!CreateSolidBrush` at `0x1400389b8`
- `GDI32!BitBlt` at `0x140038925`
- `GDI32!BitBlt` at `0x140038925`
- `GDI32!DeleteDC` at `0x14003893a`
- `GDI32!DeleteDC` at `0x14003893a`
- `GDI32!CreateCompatibleDC` at `0x140038842`
- `GDI32!CreateCompatibleDC` at `0x140038842`
- `GDI32!CreateCompatibleBitmap` at `0x14003882d`
- `GDI32!CreateCompatibleBitmap` at `0x14003882d`
- `GDI32!DeleteObject` at `0x140038897`
- `GDI32!DeleteObject` at `0x1400389d9`
- `GDI32!DeleteObject` at `0x140038897`
- `GDI32!DeleteObject` at `0x1400389d9`
- `USER32!EndPaint` at `0x1400389e7`
- `USER32!EndPaint` at `0x1400389e7`
- `USER32!BeginPaint` at `0x1400387f5`
- `USER32!BeginPaint` at `0x14003898f`
- `USER32!BeginPaint` at `0x1400387f5`
- `USER32!BeginPaint` at `0x14003898f`
- `USER32!GetClientRect` at `0x140038816`
- `USER32!GetClientRect` at `0x1400389ac`
- `USER32!GetClientRect` at `0x140038816`
- `USER32!GetClientRect` at `0x1400389ac`
- `USER32!FillRect` at `0x14003888e`
- `USER32!FillRect` at `0x1400389d0`
- `USER32!FillRect` at `0x14003888e`
- `USER32!FillRect` at `0x1400389d0`

## pseudocode

```c
__int64 __fastcall ATL::CAxHostWindow::OnPaint(ATL::CAxHostWindow *this, __int64 a2, __int64 a3, __int64 a4, int *a5)
{
  HDC v6; // rsi
  HWND v7; // rcx
  HBITMAP CompatibleBitmap; // r14
  HDC CompatibleDC; // rax
  HDC hdcSrc; // rdi
  HGDIOBJ v11; // r15
  HBRUSH SolidBrush; // rax
  HBRUSH v13; // r12
  HBITMAP v14; // rcx
  HDC v16; // rsi
  HWND v17; // rcx
  HBRUSH v18; // rax
  HBRUSH v19; // rdi
  struct tagRECT Rect; // [rsp+60h] [rbp-41h] BYREF
  tagPAINTSTRUCT Paint; // [rsp+70h] [rbp-31h] BYREF

  if ( *((_QWORD *)this + 24) )
  {
    if ( (*((_BYTE *)this + 248) & 8) != 0 )
    {
      memset_0(&Paint, 0, sizeof(Paint));
      v6 = BeginPaint(*((HWND *)this + 1), &Paint);
      if ( v6 )
      {
        v7 = (HWND)*((_QWORD *)this + 1);
        Rect = 0;
        GetClientRect(v7, &Rect);
        CompatibleBitmap = CreateCompatibleBitmap(v6, Rect.right - Rect.left, Rect.bottom - Rect.top);
        if ( CompatibleBitmap )
        {
          CompatibleDC = CreateCompatibleDC(v6);
          hdcSrc = CompatibleDC;
          if ( CompatibleDC )
          {
            v11 = SelectObject(CompatibleDC, CompatibleBitmap);
            if ( v11 )
            {
              SolidBrush = CreateSolidBrush(*((_DWORD *)this + 74));
              v13 = SolidBrush;
              if ( SolidBrush )
              {
                FillRect(hdcSrc, &Rect, SolidBrush);
                DeleteObject(v13);
                (*(void (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)this + 24) + 24LL))(
                  *((_QWORD *)this + 24),
                  1,
                  0xFFFFFFFFLL);
                BitBlt(v6, 0, 0, Rect.right, Rect.bottom, hdcSrc, 0, 0, 0xCC0020u);
              }
              SelectObject(hdcSrc, v11);
            }
            DeleteDC(hdcSrc);
          }
          v14 = CompatibleBitmap;
          goto LABEL_17;
        }
        goto LABEL_18;
      }
    }
    else
    {
      *a5 = 0;
    }
    return 0;
  }
  memset_0(&Paint, 0, sizeof(Paint));
  v16 = BeginPaint(*((HWND *)this + 1), &Paint);
  if ( !v16 )
    return 0;
  v17 = (HWND)*((_QWORD *)this + 1);
  Rect = 0;
  GetClientRect(v17, &Rect);
  v18 = CreateSolidBrush(*((_DWORD *)this + 74));
  v19 = v18;
  if ( v18 )
  {
    FillRect(v16, &Rect, v18);
    v14 = (HBITMAP)v19;
LABEL_17:
    DeleteObject(v14);
  }
LABEL_18:
  EndPaint(*((HWND *)this + 1), &Paint);
  return 1;
}

```

## disassembly

```asm
0x140038790  mov     [rsp-8+arg_8], rbx
0x140038795  mov     [rsp-8+arg_10], rsi
0x14003879a  push    rbp
0x14003879b  push    rdi
0x14003879c  push    r12
0x14003879e  push    r14
0x1400387a0  push    r15
0x1400387a2  lea     rbp, [rsp-2Fh]
0x1400387a7  sub     rsp, 0D0h
0x1400387ae  mov     rax, cs:__security_cookie
0x1400387b5  xor     rax, rsp
0x1400387b8  mov     [rbp+4Fh+var_30], rax
0x1400387bc  cmp     qword ptr [rcx+0C0h], 0
0x1400387c4  mov     rbx, rcx
0x1400387c7  mov     rax, [rbp+4Fh+arg_20]
0x1400387cb  jz      loc_140038978
0x1400387d1  test    byte ptr [rcx+0F8h], 8
0x1400387d8  jz      loc_140038948
0x1400387de  xor     edx, edx; Val
0x1400387e0  lea     rcx, [rbp+4Fh+Paint]; void *
0x1400387e4  lea     r8d, [rdx+48h]; Size
0x1400387e8  call    memset_0
0x1400387ed  mov     rcx, [rbx+8]; hWnd
0x1400387f1  lea     rdx, [rbp+4Fh+Paint]; lpPaint
0x1400387f5  call    cs:__imp_BeginPaint
0x1400387fb  mov     rsi, rax
0x1400387fe  test    rax, rax
0x140038801  jz      loc_14003894E
0x140038807  mov     rcx, [rbx+8]; hWnd
0x14003880b  lea     rdx, [rbp+4Fh+Rect]; lpRect
0x14003880f  xorps   xmm0, xmm0
0x140038812  movups  xmmword ptr [rbp+4Fh+Rect.left], xmm0
0x140038816  call    cs:__imp_GetClientRect
0x14003881c  mov     r8d, [rbp+4Fh+Rect.bottom]
0x140038820  mov     rcx, rsi; hdc
0x140038823  mov     edx, [rbp+4Fh+Rect.right]
0x140038826  sub     r8d, [rbp+4Fh+Rect.top]; cy
0x14003882a  sub     edx, [rbp+4Fh+Rect.left]; cx
0x14003882d  call    cs:__imp_CreateCompatibleBitmap
0x140038833  mov     r14, rax
0x140038836  test    rax, rax
0x140038839  jz      loc_1400389DF
0x14003883f  mov     rcx, rsi; hdc
0x140038842  call    cs:__imp_CreateCompatibleDC
0x140038848  mov     rdi, rax
0x14003884b  test    rax, rax
0x14003884e  jz      loc_140038940
0x140038854  mov     rdx, r14; h
0x140038857  mov     rcx, rax; hdc
0x14003885a  call    cs:__imp_SelectObject
0x140038860  mov     r15, rax
0x140038863  test    rax, rax
0x140038866  jz      loc_140038937
0x14003886c  mov     ecx, [rbx+128h]; color
0x140038872  call    cs:__imp_CreateSolidBrush
0x140038878  mov     r12, rax
0x14003887b  test    rax, rax
0x14003887e  jz      loc_14003892B
0x140038884  mov     r8, rax; hbr
0x140038887  lea     rdx, [rbp+4Fh+Rect]; lprc
0x14003888b  mov     rcx, rdi; hDC
0x14003888e  call    cs:__imp_FillRect
0x140038894  mov     rcx, r12; ho
0x140038897  call    cs:__imp_DeleteObject
0x14003889d  mov     rcx, [rbx+0C0h]
0x1400388a4  lea     rdx, [rbx+114h]
0x1400388ab  mov     [rsp+0F0h+var_A0], 0
0x1400388b4  xor     r9d, r9d
0x1400388b7  mov     [rsp+0F0h+var_A8], 0
0x1400388c0  or      r8d, 0FFFFFFFFh
0x1400388c4  mov     qword ptr [rsp+0F0h+rop], rdx
0x1400388c9  mov     rax, [rcx]
0x1400388cc  mov     qword ptr [rsp+0F0h+y1], rdx
0x1400388d1  lea     edx, [r9+1]
0x1400388d5  mov     qword ptr [rsp+0F0h+x1], rdi
0x1400388da  mov     [rsp+0F0h+hdcSrc], 0
0x1400388e3  mov     rax, [rax+18h]
0x1400388e7  mov     qword ptr [rsp+0F0h+cy], 0
0x1400388f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400388f5  mov     eax, [rbp+4Fh+Rect.bottom]
0x1400388f8  xor     r8d, r8d; y
0x1400388fb  mov     r9d, [rbp+4Fh+Rect.right]; cx
0x1400388ff  xor     edx, edx; x
0x140038901  mov     [rsp+0F0h+rop], 0CC0020h; rop
0x140038909  mov     rcx, rsi; hdc
0x14003890c  mov     [rsp+0F0h+y1], 0; y1
0x140038914  mov     [rsp+0F0h+x1], 0; x1
0x14003891c  mov     [rsp+0F0h+hdcSrc], rdi; hdcSrc
0x140038921  mov     [rsp+0F0h+cy], eax; cy
0x140038925  call    cs:__imp_BitBlt
0x14003892b  mov     rdx, r15; h
0x14003892e  mov     rcx, rdi; hdc
0x140038931  call    cs:__imp_SelectObject
0x140038937  mov     rcx, rdi; hdc
0x14003893a  call    cs:__imp_DeleteDC
0x140038940  mov     rcx, r14
0x140038943  jmp     loc_1400389D9
0x140038948  mov     dword ptr [rax], 0
0x14003894e  xor     eax, eax
0x140038950  mov     rcx, [rbp+4Fh+var_30]
0x140038954  xor     rcx, rsp; StackCookie
0x140038957  call    __security_check_cookie
0x14003895c  lea     r11, [rsp+0F0h+var_20]
0x140038964  mov     rbx, [r11+38h]
0x140038968  mov     rsi, [r11+40h]
0x14003896c  mov     rsp, r11
0x14003896f  pop     r15
0x140038971  pop     r14
0x140038973  pop     r12
0x140038975  pop     rdi
0x140038976  pop     rbp
0x140038977  retn
0x140038978  xor     edx, edx; Val
0x14003897a  lea     rcx, [rbp+4Fh+Paint]; void *
0x14003897e  lea     r8d, [rdx+48h]; Size
0x140038982  call    memset_0
0x140038987  mov     rcx, [rbx+8]; hWnd
0x14003898b  lea     rdx, [rbp+4Fh+Paint]; lpPaint
0x14003898f  call    cs:__imp_BeginPaint
0x140038995  mov     rsi, rax
0x140038998  test    rax, rax
0x14003899b  jz      short loc_14003894E
0x14003899d  mov     rcx, [rbx+8]; hWnd
0x1400389a1  lea     rdx, [rbp+4Fh+Rect]; lpRect
0x1400389a5  xorps   xmm0, xmm0
0x1400389a8  movups  xmmword ptr [rbp+4Fh+Rect.left], xmm0
0x1400389ac  call    cs:__imp_GetClientRect
0x1400389b2  mov     ecx, [rbx+128h]; color
0x1400389b8  call    cs:__imp_CreateSolidBrush
0x1400389be  mov     rdi, rax
0x1400389c1  test    rax, rax
0x1400389c4  jz      short loc_1400389DF
0x1400389c6  mov     r8, rax; hbr
0x1400389c9  lea     rdx, [rbp+4Fh+Rect]; lprc
0x1400389cd  mov     rcx, rsi; hDC
0x1400389d0  call    cs:__imp_FillRect
0x1400389d6  mov     rcx, rdi; ho
0x1400389d9  call    cs:__imp_DeleteObject
0x1400389df  mov     rcx, [rbx+8]; hWnd
0x1400389e3  lea     rdx, [rbp+4Fh+Paint]; lpPaint
0x1400389e7  call    cs:__imp_EndPaint
0x1400389ed  mov     eax, 1
0x1400389f2  jmp     loc_140038950
```
