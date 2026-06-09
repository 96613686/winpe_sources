# CSimpleHeader::_OnPaint(HWND__ *)

- ea: `0x18006d958`
- end: `0x18006de1e`
- name: `?_OnPaint@CSimpleHeader@@AEAAXPEAUHWND__@@@Z`
- size: `1222`
- prototype: `void __fastcall(CSimpleHeader *__hidden this, HWND hWnd)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180028894`

## callees

- `0x18006d4f8`
- `0x18006d958`
- `0x18006df5c`
- `0x180082198`
- `0x180082948`
- `0x18008330c`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x18006d9c8`
- `GDI32!CreateCompatibleDC` at `0x18006d9c8`
- `GDI32!SelectObject` at `0x18006da0d`
- `GDI32!SelectObject` at `0x18006daa0`
- `GDI32!SelectObject` at `0x18006ddb3`
- `GDI32!SelectObject` at `0x18006da0d`
- `GDI32!SelectObject` at `0x18006daa0`
- `GDI32!SelectObject` at `0x18006ddb3`
- `GDI32!BitBlt` at `0x18006dda6`
- `GDI32!BitBlt` at `0x18006dda6`
- `GDI32!DeleteDC` at `0x18006ddd3`
- `GDI32!DeleteDC` at `0x18006ddd3`
- `GDI32!DeleteObject` at `0x18006ddca`
- `GDI32!DeleteObject` at `0x18006ddca`
- `GDI32!SaveDC` at `0x18006d9d4`
- `GDI32!SaveDC` at `0x18006d9d4`
- `GDI32!CreateCompatibleBitmap` at `0x18006da90`
- `GDI32!CreateCompatibleBitmap` at `0x18006da90`
- `GDI32!SetBkMode` at `0x18006dafb`
- `GDI32!SetBkMode` at `0x18006dafb`
- `GDI32!SetBkColor` at `0x18006db0f`
- `GDI32!SetBkColor` at `0x18006db0f`
- `GDI32!SetTextColor` at `0x18006db2a`
- `GDI32!SetTextColor` at `0x18006db2a`
- `GDI32!RestoreDC` at `0x18006ddc0`
- `GDI32!RestoreDC` at `0x18006ddc0`
- `USER32!GetSysColorBrush` at `0x18006dab9`
- `USER32!GetSysColorBrush` at `0x18006dab9`
- `USER32!GetClientRect` at `0x18006da1a`
- `USER32!GetClientRect` at `0x18006da52`
- `USER32!GetClientRect` at `0x18006da1a`
- `USER32!GetClientRect` at `0x18006da52`
- `USER32!GetSystemMetrics` at `0x18006da2c`
- `USER32!GetSystemMetrics` at `0x18006dad4`
- `USER32!GetSystemMetrics` at `0x18006daea`
- `USER32!GetSystemMetrics` at `0x18006dbfe`
- `USER32!GetSystemMetrics` at `0x18006da2c`
- `USER32!GetSystemMetrics` at `0x18006dad4`
- `USER32!GetSystemMetrics` at `0x18006daea`
- `USER32!GetSystemMetrics` at `0x18006dbfe`
- `USER32!FillRect` at `0x18006dac9`
- `USER32!FillRect` at `0x18006dac9`
- `USER32!GetSysColor` at `0x18006db04`
- `USER32!GetSysColor` at `0x18006db1f`
- `USER32!GetSysColor` at `0x18006db04`
- `USER32!GetSysColor` at `0x18006db1f`
- `USER32!BeginPaint` at `0x18006d9b8`
- `USER32!BeginPaint` at `0x18006d9b8`
- `USER32!EndPaint` at `0x18006dde0`
- `USER32!EndPaint` at `0x18006dde0`

## pseudocode

```c
void __fastcall CSimpleHeader::_OnPaint(CSimpleHeader *this, HWND hWnd)
{
  HWND v2; // r13
  HDC v4; // rdi
  HDC hdcSrc; // r15
  LONG right; // ebx
  int SystemMetrics; // eax
  int v8; // r12d
  int v9; // r14d
  CCommunityRatings *v10; // rcx
  HGDIOBJ v11; // rax
  int v12; // edi
  unsigned int v13; // ebx
  HBRUSH SysColorBrush; // rax
  int v15; // r12d
  COLORREF SysColor; // eax
  COLORREF v17; // eax
  CSimpleHeader *v18; // rcx
  int LineHeight; // eax
  char *v20; // rdi
  char v21; // cl
  int v22; // ebx
  int v23; // r12d
  unsigned __int64 v24; // rcx
  _WORD *v25; // rax
  unsigned __int16 *v26; // r8
  _WORD *v27; // rax
  _WORD *v28; // rax
  unsigned __int16 *v29; // r8
  __int64 v30; // rax
  _WORD *v31; // rax
  CCommunityRatings *v32; // rcx
  int v33; // [rsp+50h] [rbp-B0h] BYREF
  struct tagSIZE v34; // [rsp+58h] [rbp-A8h] BYREF
  int cy; // [rsp+60h] [rbp-A0h]
  int v36; // [rsp+64h] [rbp-9Ch]
  int nSavedDC; // [rsp+68h] [rbp-98h]
  HGDIOBJ h; // [rsp+70h] [rbp-90h] BYREF
  HWND v39; // [rsp+78h] [rbp-88h]
  HDC hdc; // [rsp+80h] [rbp-80h]
  HGDIOBJ v41; // [rsp+88h] [rbp-78h]
  HGDIOBJ ho; // [rsp+90h] [rbp-70h]
  struct tagRECT Rect; // [rsp+98h] [rbp-68h] BYREF
  struct tagRECT v44; // [rsp+A8h] [rbp-58h] BYREF
  tagPAINTSTRUCT Paint; // [rsp+C0h] [rbp-40h] BYREF

  v39 = hWnd;
  v2 = hWnd;
  h = 0;
  memset_0(&Paint, 0, sizeof(Paint));
  Rect = 0;
  v44 = 0;
  hdc = BeginPaint(v2, &Paint);
  v4 = hdc;
  hdcSrc = CreateCompatibleDC(hdc);
  nSavedDC = SaveDC(hdcSrc);
  if ( g_lpIFontCache
    && !(*(unsigned int (__fastcall **)(struct IFontCache *, __int64, _QWORD, HGDIOBJ *))(*(_QWORD *)g_lpIFontCache
                                                                                        + 32LL))(
          g_lpIFontCache,
          1,
          0,
          &h) )
  {
    SelectObject(hdcSrc, h);
  }
  GetClientRect(v2, &Rect);
  right = Rect.right;
  v36 = Rect.right;
  SystemMetrics = GetSystemMetrics(5);
  v8 = *((_DWORD *)this + 17);
  v9 = right - 4 * SystemMetrics;
  cy = v8;
  if ( *((_DWORD *)this + 18) )
  {
    GetClientRect(*((HWND *)this + 5), &v44);
    v9 = v9 - v44.right - 4;
  }
  v10 = (CCommunityRatings *)*((_QWORD *)this + 19);
  if ( v10 )
  {
    v34 = 0;
    if ( (int)CCommunityRatings::GetSize(v10, &v34) >= 0 )
      v9 -= v34.cx;
  }
  ho = CreateCompatibleBitmap(v4, right, v8);
  v11 = SelectObject(hdcSrc, ho);
  v12 = *((_DWORD *)this + 16);
  v41 = v11;
  v13 = v12 != 0 ? 0xFFFFFFFE : 0;
  SysColorBrush = GetSysColorBrush(v13 + 15);
  FillRect(hdcSrc, &Rect, SysColorBrush);
  v33 = 2 * GetSystemMetrics(5) + 4;
  v15 = GetSystemMetrics(6);
  SetBkMode(hdcSrc, 2);
  SysColor = GetSysColor(v13 + 15);
  SetBkColor(hdcSrc, SysColor);
  v17 = GetSysColor(v12 != 0 ? 14 : 18);
  SetTextColor(hdcSrc, v17);
  LineHeight = CSimpleHeader::_GetLineHeight(v18, hdcSrc);
  v20 = (char *)*((_QWORD *)this + 13);
  v21 = *v20;
  if ( *v20 )
  {
    v22 = 2 * v15 + 4;
    v23 = LineHeight;
    while ( 1 )
    {
      if ( v21 == 38 )
      {
        if ( *++v20 == 67 )
          goto LABEL_41;
        v24 = (unsigned int)(*v20 - 70);
        switch ( *v20 )
        {
          case 'F':
LABEL_32:
            if ( *v20 == 102 || (v28 = (_WORD *)*((_QWORD *)this + 14)) != 0 && *v28 )
            {
              CSimpleHeader::_OutputHeaderText(this, hdcSrc, (unsigned __int16 *)0x488, &v33, v22, v9, 3u);
              v33 += 4;
            }
            v29 = (unsigned __int16 *)*((_QWORD *)this + 14);
            if ( v29 )
              CSimpleHeader::_OutputHeaderText(this, hdcSrc, v29, &v33, v22, v9, 0);
            v30 = *((_QWORD *)this + 19);
            if ( v30 && *(_DWORD *)(v30 + 328) )
              CCommunityRatings::AddMVPImage((CCommunityRatings *)v24, hdcSrc, &v33, v22);
            goto LABEL_48;
          case 'S':
            goto LABEL_27;
          case 'T':
LABEL_21:
            if ( *v20 == 116 || (v25 = (_WORD *)*((_QWORD *)this + 17)) != 0 && *v25 )
            {
              CSimpleHeader::_OutputHeaderText(this, hdcSrc, (unsigned __int16 *)0x48A, &v33, v22, v9, 3u);
              v33 += 4;
            }
            v26 = (unsigned __int16 *)*((_QWORD *)this + 17);
            goto LABEL_46;
          case 'b':
            v22 += v23 + 2;
            v33 = 2 * GetSystemMetrics(5) + 4;
            break;
          case 'c':
LABEL_41:
            if ( *v20 == 99 || (v31 = (_WORD *)*((_QWORD *)this + 16)) != 0 && *v31 )
            {
              CSimpleHeader::_OutputHeaderText(this, hdcSrc, (unsigned __int16 *)0x48B, &v33, v22, v9, 3u);
              v33 += 4;
            }
            v26 = (unsigned __int16 *)*((_QWORD *)this + 16);
LABEL_46:
            if ( v26 )
              CSimpleHeader::_OutputHeaderText(this, hdcSrc, v26, &v33, v22, v9, 0);
LABEL_48:
            v33 += 8;
            break;
          default:
            v24 = (unsigned int)(*v20 - 102);
            switch ( *v20 )
            {
              case 'f':
                goto LABEL_32;
              case 's':
LABEL_27:
                if ( *v20 == 115 || (v27 = (_WORD *)*((_QWORD *)this + 15)) != 0 && *v27 )
                {
                  CSimpleHeader::_OutputHeaderText(this, hdcSrc, (unsigned __int16 *)0x48D, &v33, v22, v9, 3u);
                  v33 += 4;
                }
                v26 = (unsigned __int16 *)*((_QWORD *)this + 15);
                goto LABEL_46;
              case 't':
                goto LABEL_21;
            }
            break;
        }
      }
      v21 = *++v20;
      if ( !*v20 )
      {
        v2 = v39;
        break;
      }
    }
  }
  BitBlt(hdc, 0, 0, v36, cy, hdcSrc, 0, 0, 0xCC0020u);
  SelectObject(hdcSrc, v41);
  RestoreDC(hdcSrc, nSavedDC);
  DeleteObject(ho);
  DeleteDC(hdcSrc);
  EndPaint(v2, &Paint);
  v32 = (CCommunityRatings *)*((_QWORD *)this + 19);
  if ( v32 )
    CCommunityRatings::Refresh(v32);
}

```

## disassembly

```asm
0x18006d958  mov     [rsp-8+arg_10], rbx
0x18006d95d  push    rbp
0x18006d95e  push    rsi
0x18006d95f  push    rdi
0x18006d960  push    r12
0x18006d962  push    r13
0x18006d964  push    r14
0x18006d966  push    r15
0x18006d968  lea     rbp, [rsp-20h]
0x18006d96d  sub     rsp, 120h
0x18006d974  mov     rax, cs:__security_cookie
0x18006d97b  xor     rax, rsp
0x18006d97e  mov     [rbp+50h+var_40], rax
0x18006d982  xor     ebx, ebx
0x18006d984  mov     [rsp+150h+var_D8], rdx
0x18006d989  mov     r13, rdx
0x18006d98c  mov     [rsp+150h+h], rbx
0x18006d991  mov     rsi, rcx
0x18006d994  xor     edx, edx; Val
0x18006d996  lea     rcx, [rbp+50h+Paint]; void *
0x18006d99a  lea     r8d, [rbx+48h]; Size
0x18006d99e  call    memset_0
0x18006d9a3  xorps   xmm0, xmm0
0x18006d9a6  lea     rdx, [rbp+50h+Paint]; lpPaint
0x18006d9aa  xorps   xmm1, xmm1
0x18006d9ad  mov     rcx, r13; hWnd
0x18006d9b0  movups  xmmword ptr [rbp+50h+Rect.left], xmm0
0x18006d9b4  movups  xmmword ptr [rbp+50h+var_A8.left], xmm1
0x18006d9b8  call    cs:__imp_BeginPaint
0x18006d9be  mov     rcx, rax; hdc
0x18006d9c1  mov     [rbp+50h+hdc], rax
0x18006d9c5  mov     rdi, rax
0x18006d9c8  call    cs:__imp_CreateCompatibleDC
0x18006d9ce  mov     rcx, rax; hdc
0x18006d9d1  mov     r15, rax
0x18006d9d4  call    cs:__imp_SaveDC
0x18006d9da  mov     rcx, cs:?g_lpIFontCache@@3PEAUIFontCache@@EA; IFontCache * g_lpIFontCache
0x18006d9e1  mov     [rsp+150h+nSavedDC], eax
0x18006d9e5  test    rcx, rcx
0x18006d9e8  jz      short loc_18006DA13
0x18006d9ea  mov     rdx, [rcx]
0x18006d9ed  lea     r9, [rsp+150h+h]
0x18006d9f2  xor     r8d, r8d
0x18006d9f5  mov     rax, [rdx+20h]
0x18006d9f9  lea     edx, [rbx+1]
0x18006d9fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006da01  test    eax, eax
0x18006da03  jnz     short loc_18006DA13
0x18006da05  mov     rdx, [rsp+150h+h]; h
0x18006da0a  mov     rcx, r15; hdc
0x18006da0d  call    cs:__imp_SelectObject
0x18006da13  lea     rdx, [rbp+50h+Rect]; lpRect
0x18006da17  mov     rcx, r13; hWnd
0x18006da1a  call    cs:__imp_GetClientRect
0x18006da20  mov     ebx, [rbp+50h+Rect.right]
0x18006da23  mov     ecx, 5; nIndex
0x18006da28  mov     [rsp+150h+var_EC], ebx
0x18006da2c  call    cs:__imp_GetSystemMetrics
0x18006da32  mov     r12d, [rsi+44h]
0x18006da36  mov     r14d, ebx
0x18006da39  shl     eax, 2
0x18006da3c  sub     r14d, eax
0x18006da3f  mov     [rsp+150h+var_F0], r12d
0x18006da44  cmp     dword ptr [rsi+48h], 0
0x18006da48  jz      short loc_18006DA60
0x18006da4a  mov     rcx, [rsi+28h]; hWnd
0x18006da4e  lea     rdx, [rbp+50h+var_A8]; lpRect
0x18006da52  call    cs:__imp_GetClientRect
0x18006da58  sub     r14d, [rbp+50h+var_A8.right]
0x18006da5c  sub     r14d, 4
0x18006da60  mov     rcx, [rsi+98h]; this
0x18006da67  test    rcx, rcx
0x18006da6a  jz      short loc_18006DA88
0x18006da6c  lea     rdx, [rsp+150h+var_F8]; struct tagSIZE *
0x18006da71  mov     qword ptr [rsp+150h+var_F8.cx], 0
0x18006da7a  call    ?GetSize@CCommunityRatings@@QEAAJPEAUtagSIZE@@@Z; CCommunityRatings::GetSize(tagSIZE *)
0x18006da7f  test    eax, eax
0x18006da81  js      short loc_18006DA88
0x18006da83  sub     r14d, [rsp+150h+var_F8.cx]
0x18006da88  mov     r8d, r12d; cy
0x18006da8b  mov     edx, ebx; cx
0x18006da8d  mov     rcx, rdi; hdc
0x18006da90  call    cs:__imp_CreateCompatibleBitmap
0x18006da96  mov     rdx, rax; h
0x18006da99  mov     [rbp+50h+ho], rax
0x18006da9d  mov     rcx, r15; hdc
0x18006daa0  call    cs:__imp_SelectObject
0x18006daa6  mov     edi, [rsi+40h]
0x18006daa9  mov     ecx, edi
0x18006daab  neg     ecx
0x18006daad  mov     [rbp+50h+var_C8], rax
0x18006dab1  sbb     ebx, ebx
0x18006dab3  and     ebx, 0FFFFFFFEh
0x18006dab6  lea     ecx, [rbx+0Fh]; nIndex
0x18006dab9  call    cs:__imp_GetSysColorBrush
0x18006dabf  lea     rdx, [rbp+50h+Rect]; lprc
0x18006dac3  mov     rcx, r15; hDC
0x18006dac6  mov     r8, rax; hbr
0x18006dac9  call    cs:__imp_FillRect
0x18006dacf  mov     ecx, 5; nIndex
0x18006dad4  call    cs:__imp_GetSystemMetrics
0x18006dada  mov     ecx, 6; nIndex
0x18006dadf  lea     eax, ds:4[rax*2]
0x18006dae6  mov     [rsp+150h+var_100], eax
0x18006daea  call    cs:__imp_GetSystemMetrics
0x18006daf0  mov     edx, 2; mode
0x18006daf5  mov     rcx, r15; hdc
0x18006daf8  mov     r12d, eax
0x18006dafb  call    cs:__imp_SetBkMode
0x18006db01  lea     ecx, [rbx+0Fh]; nIndex
0x18006db04  call    cs:__imp_GetSysColor
0x18006db0a  mov     edx, eax; color
0x18006db0c  mov     rcx, r15; hdc
0x18006db0f  call    cs:__imp_SetBkColor
0x18006db15  neg     edi
0x18006db17  sbb     ecx, ecx
0x18006db19  and     ecx, 0FFFFFFFCh
0x18006db1c  add     ecx, 12h; nIndex
0x18006db1f  call    cs:__imp_GetSysColor
0x18006db25  mov     edx, eax; color
0x18006db27  mov     rcx, r15; hdc
0x18006db2a  call    cs:__imp_SetTextColor
0x18006db30  mov     rdx, r15; HDC
0x18006db33  call    ?_GetLineHeight@CSimpleHeader@@AEAAHPEAUHDC__@@@Z; CSimpleHeader::_GetLineHeight(HDC__ *)
0x18006db38  mov     rdi, [rsi+68h]
0x18006db3c  xor     ebx, ebx
0x18006db3e  mov     cl, [rdi]
0x18006db40  test    cl, cl
0x18006db42  jz      loc_18006DD7B
0x18006db48  lea     ebx, ds:4[r12*2]
0x18006db50  xor     r13d, r13d
0x18006db53  mov     r12d, eax
0x18006db56  cmp     cl, 26h ; '&'
0x18006db59  jnz     loc_18006DD67
0x18006db5f  inc     rdi
0x18006db62  movsx   ecx, byte ptr [rdi]
0x18006db65  sub     ecx, 43h ; 'C'
0x18006db68  jz      loc_18006DCF5
0x18006db6e  sub     ecx, 3
0x18006db71  jz      loc_18006DC63
0x18006db77  sub     ecx, 0Dh
0x18006db7a  jz      loc_18006DC1A
0x18006db80  sub     ecx, 1
0x18006db83  jz      short loc_18006DBAA
0x18006db85  sub     ecx, 0Eh
0x18006db88  jz      short loc_18006DBF9
0x18006db8a  sub     ecx, 1
0x18006db8d  jz      loc_18006DCF5
0x18006db93  sub     ecx, 3
0x18006db96  jz      loc_18006DC63
0x18006db9c  sub     ecx, 0Dh
0x18006db9f  jz      short loc_18006DC1A
0x18006dba1  cmp     ecx, 1
0x18006dba4  jnz     loc_18006DD67
0x18006dbaa  cmp     byte ptr [rdi], 74h ; 't'
0x18006dbad  jz      short loc_18006DBC1
0x18006dbaf  mov     rax, [rsi+88h]
0x18006dbb6  test    rax, rax
0x18006dbb9  jz      short loc_18006DBED
0x18006dbbb  cmp     [rax], r13w
0x18006dbbf  jz      short loc_18006DBED
0x18006dbc1  mov     [rsp+150h+x1], 3; unsigned int
0x18006dbc9  lea     r9, [rsp+150h+var_100]; int *
0x18006dbce  mov     dword ptr [rsp+150h+hdcSrc], r14d; int
0x18006dbd3  mov     r8d, 48Ah; unsigned __int16 *
0x18006dbd9  mov     rdx, r15; HDC
0x18006dbdc  mov     [rsp+150h+cy], ebx; int
0x18006dbe0  mov     rcx, rsi; this
0x18006dbe3  call    ?_OutputHeaderText@CSimpleHeader@@AEAAXPEAUHDC__@@PEAGPEAHHHK@Z; CSimpleHeader::_OutputHeaderText(HDC__ *,ushort *,int *,int,int,ulong)
0x18006dbe8  add     [rsp+150h+var_100], 4
0x18006dbed  mov     r8, [rsi+88h]
0x18006dbf4  jmp     loc_18006DD3F
0x18006dbf9  mov     ecx, 5; nIndex
0x18006dbfe  call    cs:__imp_GetSystemMetrics
0x18006dc04  add     ebx, 2
0x18006dc07  add     ebx, r12d
0x18006dc0a  lea     eax, ds:4[rax*2]
0x18006dc11  mov     [rsp+150h+var_100], eax
0x18006dc15  jmp     loc_18006DD67
0x18006dc1a  cmp     byte ptr [rdi], 73h ; 's'
0x18006dc1d  jz      short loc_18006DC2E
0x18006dc1f  mov     rax, [rsi+78h]
0x18006dc23  test    rax, rax
0x18006dc26  jz      short loc_18006DC5A
0x18006dc28  cmp     [rax], r13w
0x18006dc2c  jz      short loc_18006DC5A
0x18006dc2e  mov     [rsp+150h+x1], 3; unsigned int
0x18006dc36  lea     r9, [rsp+150h+var_100]; int *
0x18006dc3b  mov     dword ptr [rsp+150h+hdcSrc], r14d; int
0x18006dc40  mov     r8d, 48Dh; unsigned __int16 *
0x18006dc46  mov     rdx, r15; HDC
0x18006dc49  mov     [rsp+150h+cy], ebx; int
0x18006dc4d  mov     rcx, rsi; this
0x18006dc50  call    ?_OutputHeaderText@CSimpleHeader@@AEAAXPEAUHDC__@@PEAGPEAHHHK@Z; CSimpleHeader::_OutputHeaderText(HDC__ *,ushort *,int *,int,int,ulong)
0x18006dc55  add     [rsp+150h+var_100], 4
0x18006dc5a  mov     r8, [rsi+78h]
0x18006dc5e  jmp     loc_18006DD3F
0x18006dc63  cmp     byte ptr [rdi], 66h ; 'f'
0x18006dc66  jz      short loc_18006DC77
0x18006dc68  mov     rax, [rsi+70h]
0x18006dc6c  test    rax, rax
0x18006dc6f  jz      short loc_18006DCA3
0x18006dc71  cmp     [rax], r13w
0x18006dc75  jz      short loc_18006DCA3
0x18006dc77  mov     [rsp+150h+x1], 3; unsigned int
0x18006dc7f  lea     r9, [rsp+150h+var_100]; int *
0x18006dc84  mov     dword ptr [rsp+150h+hdcSrc], r14d; int
0x18006dc89  mov     r8d, 488h; unsigned __int16 *
0x18006dc8f  mov     rdx, r15; HDC
0x18006dc92  mov     [rsp+150h+cy], ebx; int
0x18006dc96  mov     rcx, rsi; this
0x18006dc99  call    ?_OutputHeaderText@CSimpleHeader@@AEAAXPEAUHDC__@@PEAGPEAHHHK@Z; CSimpleHeader::_OutputHeaderText(HDC__ *,ushort *,int *,int,int,ulong)
0x18006dc9e  add     [rsp+150h+var_100], 4
0x18006dca3  mov     r8, [rsi+70h]; unsigned __int16 *
0x18006dca7  test    r8, r8
0x18006dcaa  jz      short loc_18006DCCA
0x18006dcac  mov     [rsp+150h+x1], r13d; unsigned int
0x18006dcb1  lea     r9, [rsp+150h+var_100]; int *
0x18006dcb6  mov     dword ptr [rsp+150h+hdcSrc], r14d; int
0x18006dcbb  mov     rdx, r15; HDC
0x18006dcbe  mov     rcx, rsi; this
0x18006dcc1  mov     [rsp+150h+cy], ebx; int
0x18006dcc5  call    ?_OutputHeaderText@CSimpleHeader@@AEAAXPEAUHDC__@@PEAGPEAHHHK@Z; CSimpleHeader::_OutputHeaderText(HDC__ *,ushort *,int *,int,int,ulong)
0x18006dcca  mov     rax, [rsi+98h]
0x18006dcd1  test    rax, rax
0x18006dcd4  jz      loc_18006DD62
0x18006dcda  cmp     [rax+148h], r13d
0x18006dce1  jz      short loc_18006DD62
0x18006dce3  mov     r9d, ebx; int
0x18006dce6  lea     r8, [rsp+150h+var_100]; int *
0x18006dceb  mov     rdx, r15; HDC
0x18006dcee  call    ?AddMVPImage@CCommunityRatings@@QEAAJPEAUHDC__@@PEAHH@Z; CCommunityRatings::AddMVPImage(HDC__ *,int *,int)
0x18006dcf3  jmp     short loc_18006DD62
0x18006dcf5  cmp     byte ptr [rdi], 63h ; 'c'
0x18006dcf8  jz      short loc_18006DD0C
0x18006dcfa  mov     rax, [rsi+80h]
0x18006dd01  test    rax, rax
0x18006dd04  jz      short loc_18006DD38
0x18006dd06  cmp     [rax], r13w
0x18006dd0a  jz      short loc_18006DD38
0x18006dd0c  mov     [rsp+150h+x1], 3; unsigned int
0x18006dd14  lea     r9, [rsp+150h+var_100]; int *
0x18006dd19  mov     dword ptr [rsp+150h+hdcSrc], r14d; int
0x18006dd1e  mov     r8d, 48Bh; unsigned __int16 *
0x18006dd24  mov     rdx, r15; HDC
0x18006dd27  mov     [rsp+150h+cy], ebx; int
0x18006dd2b  mov     rcx, rsi; this
0x18006dd2e  call    ?_OutputHeaderText@CSimpleHeader@@AEAAXPEAUHDC__@@PEAGPEAHHHK@Z; CSimpleHeader::_OutputHeaderText(HDC__ *,ushort *,int *,int,int,ulong)
0x18006dd33  add     [rsp+150h+var_100], 4
0x18006dd38  mov     r8, [rsi+80h]; unsigned __int16 *
0x18006dd3f  test    r8, r8
0x18006dd42  jz      short loc_18006DD62
0x18006dd44  mov     [rsp+150h+x1], r13d; unsigned int
0x18006dd49  lea     r9, [rsp+150h+var_100]; int *
0x18006dd4e  mov     dword ptr [rsp+150h+hdcSrc], r14d; int
0x18006dd53  mov     rdx, r15; HDC
0x18006dd56  mov     rcx, rsi; this
0x18006dd59  mov     [rsp+150h+cy], ebx; int
0x18006dd5d  call    ?_OutputHeaderText@CSimpleHeader@@AEAAXPEAUHDC__@@PEAGPEAHHHK@Z; CSimpleHeader::_OutputHeaderText(HDC__ *,ushort *,int *,int,int,ulong)
0x18006dd62  add     [rsp+150h+var_100], 8
0x18006dd67  inc     rdi
0x18006dd6a  mov     cl, [rdi]
0x18006dd6c  test    cl, cl
0x18006dd6e  jnz     loc_18006DB56
0x18006dd74  mov     r13, [rsp+150h+var_D8]
0x18006dd79  xor     ebx, ebx
0x18006dd7b  mov     eax, [rsp+150h+var_F0]
0x18006dd7f  xor     r8d, r8d; y
0x18006dd82  mov     r9d, [rsp+150h+var_EC]; cx
0x18006dd87  xor     edx, edx; x
0x18006dd89  mov     rcx, [rbp+50h+hdc]; hdc
0x18006dd8d  mov     [rsp+150h+rop], 0CC0020h; rop
0x18006dd95  mov     [rsp+150h+y1], ebx; y1
0x18006dd99  mov     [rsp+150h+x1], ebx; x1
0x18006dd9d  mov     [rsp+150h+hdcSrc], r15; hdcSrc
0x18006dda2  mov     [rsp+150h+cy], eax; cy
0x18006dda6  call    cs:__imp_BitBlt
0x18006ddac  mov     rdx, [rbp+50h+var_C8]; h
0x18006ddb0  mov     rcx, r15; hdc
0x18006ddb3  call    cs:__imp_SelectObject
0x18006ddb9  mov     edx, [rsp+150h+nSavedDC]; nSavedDC
0x18006ddbd  mov     rcx, r15; hdc
0x18006ddc0  call    cs:__imp_RestoreDC
0x18006ddc6  mov     rcx, [rbp+50h+ho]; ho
0x18006ddca  call    cs:__imp_DeleteObject
0x18006ddd0  mov     rcx, r15; hdc
0x18006ddd3  call    cs:__imp_DeleteDC
0x18006ddd9  lea     rdx, [rbp+50h+Paint]; lpPaint
0x18006dddd  mov     rcx, r13; hWnd
0x18006dde0  call    cs:__imp_EndPaint
0x18006dde6  mov     rcx, [rsi+98h]; this
0x18006dded  test    rcx, rcx
0x18006ddf0  jz      short loc_18006DDF7
0x18006ddf2  call    ?Refresh@CCommunityRatings@@QEAAJXZ; CCommunityRatings::Refresh(void)
0x18006ddf7  mov     rcx, [rbp+50h+var_40]
0x18006ddfb  xor     rcx, rsp; StackCookie
0x18006ddfe  call    __security_check_cookie
0x18006de03  mov     rbx, [rsp+150h+arg_10]
0x18006de0b  add     rsp, 120h
0x18006de12  pop     r15
  ... truncated ...
```
