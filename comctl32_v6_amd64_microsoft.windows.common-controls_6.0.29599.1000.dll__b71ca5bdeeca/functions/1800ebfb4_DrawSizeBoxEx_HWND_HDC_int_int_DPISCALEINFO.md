# DrawSizeBoxEx(HWND__ *,HDC__ *,int,int,DPISCALEINFO *)

- ea: `0x1800ebfb4`
- end: `0x1800ec13b`
- name: `?DrawSizeBoxEx@@YAXPEAUHWND__@@PEAUHDC__@@HHPEAUDPISCALEINFO@@@Z`
- size: `391`
- prototype: `void __usercall(HWND@<rcx>, HDC hdc@<rdx>, int@<r8d>, int@<r9d>, struct DPISCALEINFO *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800ebf50`
- `0x18011df60`

## callees

- `0x180004e58`
- `0x180004e7c`
- `0x180005cc4`
- `0x1800ebfb4`
- `0x1800ec150`
- `0x180114520`

## import_xrefs

- `GDI32!CreateSolidBrush` at `0x1800ec04f`
- `GDI32!CreateSolidBrush` at `0x1800ec04f`
- `GDI32!DeleteObject` at `0x1800ec11d`
- `GDI32!DeleteObject` at `0x1800ec11d`
- `USER32!FillRect` at `0x1800ec068`
- `USER32!FillRect` at `0x1800ec068`
- `USER32!DrawFrameControl` at `0x1800ec0c5`
- `USER32!DrawFrameControl` at `0x1800ec0c5`
- `USER32!GetSystemMetricsForDpi` at `0x1800ebff3`
- `USER32!GetSystemMetricsForDpi` at `0x1800ec007`
- `USER32!GetSystemMetricsForDpi` at `0x1800ebff3`
- `USER32!GetSystemMetricsForDpi` at `0x1800ec007`
- `UxTheme!DrawThemeBackground` at `0x1800ec10f`
- `UxTheme!DrawThemeBackground` at `0x1800ec10f`
- `UxTheme!GetThemeColor` at `0x1800ec045`
- `UxTheme!GetThemeColor` at `0x1800ec045`

## pseudocode

```c
void __fastcall DrawSizeBoxEx(HWND a1, HDC hdc, LONG a3, LONG a4, struct DPISCALEINFO *a5)
{
  int SystemMetricsForDpi; // eax
  __int64 v10; // rdx
  void *SBTheme; // rax
  COLORREF v12; // ecx
  void *v13; // rsi
  HBRUSH SolidBrush; // rax
  HBRUSH v15; // rbx
  int v16; // edi
  int v17; // eax
  COLORREF color; // [rsp+30h] [rbp-48h] BYREF
  RECT rc; // [rsp+38h] [rbp-40h] BYREF

  rc.left = a3;
  rc.top = a4;
  SystemMetricsForDpi = GetSystemMetricsForDpi(2, *(unsigned int *)a5);
  v10 = *((unsigned int *)a5 + 1);
  rc.right = a3 + SystemMetricsForDpi;
  rc.bottom = a4 + GetSystemMetricsForDpi(3, v10);
  SBTheme = CUxScrollBar::GetSBTheme(a1);
  v12 = 15;
  v13 = SBTheme;
  color = 15;
  if ( SBTheme )
  {
    GetThemeColor(SBTheme, 11, 0, 3802, &color);
    v12 = color;
  }
  SolidBrush = CreateSolidBrush(v12);
  v15 = SolidBrush;
  if ( SolidBrush )
    FillRect(hdc, &rc, SolidBrush);
  if ( (unsigned int)IsScrollBarControl(a1) && (unsigned int)TestWF(a1, 3088) || SizeBoxHwnd(a1) )
  {
    v16 = TestWF(a1, 2368);
    if ( v13 )
    {
      v17 = TestWF(a1, 2624);
      DrawThemeBackground(v13, hdc, 10, ((v16 != 0) ^ (v17 != 0)) + 1, &rc, 0);
    }
    else
    {
      DrawFrameControl(hdc, &rc, 3u, v16 != 0 ? 16 : 8);
    }
  }
  if ( v15 )
    DeleteObject(v15);
}

```

## disassembly

```asm
0x1800ebfb4  push    rbx
0x1800ebfb6  push    rbp
0x1800ebfb7  push    rsi
0x1800ebfb8  push    rdi
0x1800ebfb9  push    r14
0x1800ebfbb  sub     rsp, 50h
0x1800ebfbf  mov     rax, cs:__security_cookie
0x1800ebfc6  xor     rax, rsp
0x1800ebfc9  mov     [rsp+78h+var_30], rax
0x1800ebfce  mov     rbx, [rsp+78h+arg_20]
0x1800ebfd6  mov     r14, rdx
0x1800ebfd9  mov     rbp, rcx
0x1800ebfdc  mov     [rsp+78h+rc.left], r8d
0x1800ebfe1  mov     ecx, 2
0x1800ebfe6  mov     [rsp+78h+rc.top], r9d
0x1800ebfeb  mov     esi, r9d
0x1800ebfee  mov     edi, r8d
0x1800ebff1  mov     edx, [rbx]
0x1800ebff3  call    cs:__imp_GetSystemMetricsForDpi
0x1800ebff9  mov     edx, [rbx+4]
0x1800ebffc  mov     ecx, 3
0x1800ec001  add     eax, edi
0x1800ec003  mov     [rsp+78h+rc.right], eax
0x1800ec007  call    cs:__imp_GetSystemMetricsForDpi
0x1800ec00d  add     eax, esi
0x1800ec00f  mov     rcx, rbp; HWND
0x1800ec012  mov     [rsp+78h+rc.bottom], eax
0x1800ec016  call    ?GetSBTheme@CUxScrollBar@@SAPEAXPEAUHWND__@@@Z; CUxScrollBar::GetSBTheme(HWND__ *)
0x1800ec01b  mov     ecx, 0Fh
0x1800ec020  mov     rsi, rax
0x1800ec023  mov     [rsp+78h+color], ecx
0x1800ec027  test    rax, rax
0x1800ec02a  jz      short loc_1800EC04F
0x1800ec02c  lea     rax, [rsp+78h+color]
0x1800ec031  mov     r9d, 0EDAh; iPropId
0x1800ec037  lea     edx, [rcx-4]; iPartId
0x1800ec03a  mov     [rsp+78h+pColor], rax; pColor
0x1800ec03f  mov     rcx, rsi; hTheme
0x1800ec042  xor     r8d, r8d; iStateId
0x1800ec045  call    cs:__imp_GetThemeColor
0x1800ec04b  mov     ecx, [rsp+78h+color]; color
0x1800ec04f  call    cs:__imp_CreateSolidBrush
0x1800ec055  mov     rbx, rax
0x1800ec058  test    rax, rax
0x1800ec05b  jz      short loc_1800EC06E
0x1800ec05d  mov     r8, rax; hbr
0x1800ec060  lea     rdx, [rsp+78h+rc]; lprc
0x1800ec065  mov     rcx, r14; hDC
0x1800ec068  call    cs:__imp_FillRect
0x1800ec06e  mov     rcx, rbp; HWND
0x1800ec071  call    ?IsScrollBarControl@@YAHPEAUHWND__@@@Z; IsScrollBarControl(HWND__ *)
0x1800ec076  test    eax, eax
0x1800ec078  jz      short loc_1800EC08B
0x1800ec07a  mov     edx, 0C10h
0x1800ec07f  mov     rcx, rbp
0x1800ec082  call    TestWF
0x1800ec087  test    eax, eax
0x1800ec089  jnz     short loc_1800EC098
0x1800ec08b  mov     rcx, rbp; HWND
0x1800ec08e  call    SizeBoxHwnd
0x1800ec093  test    rax, rax
0x1800ec096  jz      short loc_1800EC115
0x1800ec098  mov     edx, 940h
0x1800ec09d  mov     rcx, rbp
0x1800ec0a0  call    TestWF
0x1800ec0a5  mov     edi, eax
0x1800ec0a7  test    rsi, rsi
0x1800ec0aa  jnz     short loc_1800EC0CD
0x1800ec0ac  neg     edi
0x1800ec0ae  lea     r8d, [rsi+3]; UINT
0x1800ec0b2  lea     rdx, [rsp+78h+rc]; LPRECT
0x1800ec0b7  mov     rcx, r14; HDC
0x1800ec0ba  sbb     r9d, r9d
0x1800ec0bd  and     r9d, 8
0x1800ec0c1  add     r9d, 8; UINT
0x1800ec0c5  call    cs:__imp_DrawFrameControl
0x1800ec0cb  jmp     short loc_1800EC115
0x1800ec0cd  mov     edx, 0A40h
0x1800ec0d2  mov     rcx, rbp
0x1800ec0d5  call    TestWF
0x1800ec0da  xor     r9d, r9d
0x1800ec0dd  mov     [rsp+78h+pClipRect], 0; pClipRect
0x1800ec0e6  test    eax, eax
0x1800ec0e8  mov     r8d, 0Ah; iPartId
0x1800ec0ee  mov     rdx, r14; hdc
0x1800ec0f1  mov     rcx, rsi; hTheme
0x1800ec0f4  setnz   r9b
0x1800ec0f8  xor     eax, eax
0x1800ec0fa  test    edi, edi
0x1800ec0fc  setnz   al
0x1800ec0ff  xor     r9d, eax
0x1800ec102  lea     rax, [rsp+78h+rc]
0x1800ec107  inc     r9d; iStateId
0x1800ec10a  mov     [rsp+78h+pColor], rax; pRect
0x1800ec10f  call    cs:__imp_DrawThemeBackground
0x1800ec115  test    rbx, rbx
0x1800ec118  jz      short loc_1800EC123
0x1800ec11a  mov     rcx, rbx; ho
0x1800ec11d  call    cs:__imp_DeleteObject
0x1800ec123  mov     rcx, [rsp+78h+var_30]
0x1800ec128  xor     rcx, rsp; StackCookie
0x1800ec12b  call    __security_check_cookie
0x1800ec130  add     rsp, 50h
0x1800ec134  pop     r14
0x1800ec136  pop     rdi
0x1800ec137  pop     rsi
0x1800ec138  pop     rbp
0x1800ec139  pop     rbx
0x1800ec13a  retn
```
