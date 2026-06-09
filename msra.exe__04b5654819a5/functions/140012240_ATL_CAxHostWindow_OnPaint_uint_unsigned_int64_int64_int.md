# ATL::CAxHostWindow::OnPaint(uint,unsigned __int64,__int64,int &)

- ea: `0x140012240`
- end: `0x14001250e`
- name: `?OnPaint@CAxHostWindow@ATL@@QEAA_JI_K_JAEAH@Z`
- size: `718`
- prototype: `__int64 __fastcall(ATL::CAxHostWindow *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140014a50`

## callees

- `0x140002463`
- `0x140012240`
- `0x14004ad80`
- `0x14004d010`

## import_xrefs

- `GDI32!CreateSolidBrush` at `0x140012340`
- `GDI32!CreateSolidBrush` at `0x1400124b7`
- `GDI32!CreateSolidBrush` at `0x140012340`
- `GDI32!CreateSolidBrush` at `0x1400124b7`
- `GDI32!CreateCompatibleDC` at `0x140012304`
- `GDI32!CreateCompatibleDC` at `0x140012304`
- `GDI32!CreateCompatibleBitmap` at `0x1400122e9`
- `GDI32!CreateCompatibleBitmap` at `0x1400122e9`
- `GDI32!SelectObject` at `0x140012322`
- `GDI32!SelectObject` at `0x140012417`
- `GDI32!SelectObject` at `0x140012322`
- `GDI32!SelectObject` at `0x140012417`
- `GDI32!BitBlt` at `0x140012405`
- `GDI32!BitBlt` at `0x140012405`
- `GDI32!DeleteDC` at `0x140012426`
- `GDI32!DeleteDC` at `0x140012426`
- `GDI32!DeleteObject` at `0x140012371`
- `GDI32!DeleteObject` at `0x1400124e4`
- `GDI32!DeleteObject` at `0x140012371`
- `GDI32!DeleteObject` at `0x1400124e4`
- `USER32!BeginPaint` at `0x1400122a5`
- `USER32!BeginPaint` at `0x140012482`
- `USER32!BeginPaint` at `0x1400122a5`
- `USER32!BeginPaint` at `0x140012482`
- `USER32!EndPaint` at `0x1400124f8`
- `USER32!EndPaint` at `0x1400124f8`
- `USER32!FillRect` at `0x140012362`
- `USER32!FillRect` at `0x1400124d5`
- `USER32!FillRect` at `0x140012362`
- `USER32!FillRect` at `0x1400124d5`
- `USER32!GetClientRect` at `0x1400122cc`
- `USER32!GetClientRect` at `0x1400124a5`
- `USER32!GetClientRect` at `0x1400122cc`
- `USER32!GetClientRect` at `0x1400124a5`

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

  if ( *((_QWORD *)this + 28) )
  {
    if ( (*((_BYTE *)this + 280) & 8) != 0 )
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
              SolidBrush = CreateSolidBrush(*((_DWORD *)this + 85));
              v13 = SolidBrush;
              if ( SolidBrush )
              {
                FillRect(hdcSrc, &Rect, SolidBrush);
                DeleteObject(v13);
                (*(void (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)this + 28) + 24LL))(
                  *((_QWORD *)this + 28),
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
  v18 = CreateSolidBrush(*((_DWORD *)this + 85));
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
0x140012240  mov     [rsp-8+arg_8], rbx
0x140012245  mov     [rsp-8+arg_10], rsi
0x14001224a  push    rbp
0x14001224b  push    rdi
0x14001224c  push    r12
0x14001224e  push    r14
0x140012250  push    r15
0x140012252  lea     rbp, [rsp-2Fh]
0x140012257  sub     rsp, 0D0h
0x14001225e  mov     rax, cs:__security_cookie
0x140012265  xor     rax, rsp
0x140012268  mov     [rbp+4Fh+var_30], rax
0x14001226c  cmp     qword ptr [rcx+0E0h], 0
0x140012274  mov     rbx, rcx
0x140012277  mov     rax, [rbp+4Fh+arg_20]
0x14001227b  jz      loc_14001246B
0x140012281  test    byte ptr [rcx+118h], 8
0x140012288  jz      loc_14001243A
0x14001228e  xor     edx, edx; Val
0x140012290  lea     rcx, [rbp+4Fh+Paint]; void *
0x140012294  lea     r8d, [rdx+48h]; Size
0x140012298  call    memset_0
0x14001229d  mov     rcx, [rbx+8]; hWnd
0x1400122a1  lea     rdx, [rbp+4Fh+Paint]; lpPaint
0x1400122a5  call    cs:__imp_BeginPaint
0x1400122ac  nop     dword ptr [rax+rax+00h]
0x1400122b1  mov     rsi, rax
0x1400122b4  test    rax, rax
0x1400122b7  jz      loc_140012440
0x1400122bd  mov     rcx, [rbx+8]; hWnd
0x1400122c1  lea     rdx, [rbp+4Fh+Rect]; lpRect
0x1400122c5  xorps   xmm0, xmm0
0x1400122c8  movups  xmmword ptr [rbp+4Fh+Rect.left], xmm0
0x1400122cc  call    cs:__imp_GetClientRect
0x1400122d3  nop     dword ptr [rax+rax+00h]
0x1400122d8  mov     r8d, [rbp+4Fh+Rect.bottom]
0x1400122dc  mov     rcx, rsi; hdc
0x1400122df  mov     edx, [rbp+4Fh+Rect.right]
0x1400122e2  sub     r8d, [rbp+4Fh+Rect.top]; cy
0x1400122e6  sub     edx, [rbp+4Fh+Rect.left]; cx
0x1400122e9  call    cs:__imp_CreateCompatibleBitmap
0x1400122f0  nop     dword ptr [rax+rax+00h]
0x1400122f5  mov     r14, rax
0x1400122f8  test    rax, rax
0x1400122fb  jz      loc_1400124F0
0x140012301  mov     rcx, rsi; hdc
0x140012304  call    cs:__imp_CreateCompatibleDC
0x14001230b  nop     dword ptr [rax+rax+00h]
0x140012310  mov     rdi, rax
0x140012313  test    rax, rax
0x140012316  jz      loc_140012432
0x14001231c  mov     rdx, r14; h
0x14001231f  mov     rcx, rax; hdc
0x140012322  call    cs:__imp_SelectObject
0x140012329  nop     dword ptr [rax+rax+00h]
0x14001232e  mov     r15, rax
0x140012331  test    rax, rax
0x140012334  jz      loc_140012423
0x14001233a  mov     ecx, [rbx+154h]; color
0x140012340  call    cs:__imp_CreateSolidBrush
0x140012347  nop     dword ptr [rax+rax+00h]
0x14001234c  mov     r12, rax
0x14001234f  test    rax, rax
0x140012352  jz      loc_140012411
0x140012358  mov     r8, rax; hbr
0x14001235b  lea     rdx, [rbp+4Fh+Rect]; lprc
0x14001235f  mov     rcx, rdi; hDC
0x140012362  call    cs:__imp_FillRect
0x140012369  nop     dword ptr [rax+rax+00h]
0x14001236e  mov     rcx, r12; ho
0x140012371  call    cs:__imp_DeleteObject
0x140012378  nop     dword ptr [rax+rax+00h]
0x14001237d  mov     rcx, [rbx+0E0h]
0x140012384  lea     rdx, [rbx+134h]
0x14001238b  mov     [rsp+0F0h+var_A0], 0
0x140012394  xor     r9d, r9d
0x140012397  mov     [rsp+0F0h+var_A8], 0
0x1400123a0  or      r8d, 0FFFFFFFFh
0x1400123a4  mov     qword ptr [rsp+0F0h+rop], rdx
0x1400123a9  mov     rax, [rcx]
0x1400123ac  mov     qword ptr [rsp+0F0h+y1], rdx
0x1400123b1  lea     edx, [r9+1]
0x1400123b5  mov     qword ptr [rsp+0F0h+x1], rdi
0x1400123ba  mov     [rsp+0F0h+hdcSrc], 0
0x1400123c3  mov     rax, [rax+18h]
0x1400123c7  mov     qword ptr [rsp+0F0h+cy], 0
0x1400123d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400123d5  mov     eax, [rbp+4Fh+Rect.bottom]
0x1400123d8  xor     r8d, r8d; y
0x1400123db  mov     r9d, [rbp+4Fh+Rect.right]; cx
0x1400123df  xor     edx, edx; x
0x1400123e1  mov     [rsp+0F0h+rop], 0CC0020h; rop
0x1400123e9  mov     rcx, rsi; hdc
0x1400123ec  mov     [rsp+0F0h+y1], 0; y1
0x1400123f4  mov     [rsp+0F0h+x1], 0; x1
0x1400123fc  mov     [rsp+0F0h+hdcSrc], rdi; hdcSrc
0x140012401  mov     [rsp+0F0h+cy], eax; cy
0x140012405  call    cs:__imp_BitBlt
0x14001240c  nop     dword ptr [rax+rax+00h]
0x140012411  mov     rdx, r15; h
0x140012414  mov     rcx, rdi; hdc
0x140012417  call    cs:__imp_SelectObject
0x14001241e  nop     dword ptr [rax+rax+00h]
0x140012423  mov     rcx, rdi; hdc
0x140012426  call    cs:__imp_DeleteDC
0x14001242d  nop     dword ptr [rax+rax+00h]
0x140012432  mov     rcx, r14
0x140012435  jmp     loc_1400124E4
0x14001243a  mov     dword ptr [rax], 0
0x140012440  xor     eax, eax
0x140012442  mov     rcx, [rbp+4Fh+var_30]
0x140012446  xor     rcx, rsp; StackCookie
0x140012449  call    __security_check_cookie
0x14001244e  lea     r11, [rsp+0F0h+var_20]
0x140012456  mov     rbx, [r11+38h]
0x14001245a  mov     rsi, [r11+40h]
0x14001245e  mov     rsp, r11
0x140012461  pop     r15
0x140012463  pop     r14
0x140012465  pop     r12
0x140012467  pop     rdi
0x140012468  pop     rbp
0x140012469  retn
0x14001246b  xor     edx, edx; Val
0x14001246d  lea     rcx, [rbp+4Fh+Paint]; void *
0x140012471  lea     r8d, [rdx+48h]; Size
0x140012475  call    memset_0
0x14001247a  mov     rcx, [rbx+8]; hWnd
0x14001247e  lea     rdx, [rbp+4Fh+Paint]; lpPaint
0x140012482  call    cs:__imp_BeginPaint
0x140012489  nop     dword ptr [rax+rax+00h]
0x14001248e  mov     rsi, rax
0x140012491  test    rax, rax
0x140012494  jz      short loc_140012440
0x140012496  mov     rcx, [rbx+8]; hWnd
0x14001249a  lea     rdx, [rbp+4Fh+Rect]; lpRect
0x14001249e  xorps   xmm0, xmm0
0x1400124a1  movups  xmmword ptr [rbp+4Fh+Rect.left], xmm0
0x1400124a5  call    cs:__imp_GetClientRect
0x1400124ac  nop     dword ptr [rax+rax+00h]
0x1400124b1  mov     ecx, [rbx+154h]; color
0x1400124b7  call    cs:__imp_CreateSolidBrush
0x1400124be  nop     dword ptr [rax+rax+00h]
0x1400124c3  mov     rdi, rax
0x1400124c6  test    rax, rax
0x1400124c9  jz      short loc_1400124F0
0x1400124cb  mov     r8, rax; hbr
0x1400124ce  lea     rdx, [rbp+4Fh+Rect]; lprc
0x1400124d2  mov     rcx, rsi; hDC
0x1400124d5  call    cs:__imp_FillRect
0x1400124dc  nop     dword ptr [rax+rax+00h]
0x1400124e1  mov     rcx, rdi; ho
0x1400124e4  call    cs:__imp_DeleteObject
0x1400124eb  nop     dword ptr [rax+rax+00h]
0x1400124f0  mov     rcx, [rbx+8]; hWnd
0x1400124f4  lea     rdx, [rbp+4Fh+Paint]; lpPaint
0x1400124f8  call    cs:__imp_EndPaint
0x1400124ff  nop     dword ptr [rax+rax+00h]
0x140012504  mov     eax, 1
0x140012509  jmp     loc_140012442
```
