# CCalendar::_Paint(HDC__ *,int)

- ea: `0x18010d6d4`
- end: `0x18010da09`
- name: `?_Paint@CCalendar@@AEAAXPEAUHDC__@@H@Z`
- size: `821`
- prototype: `void __fastcall(CCalendar *__hidden this, HDC, int)`
- caller_count: `3`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1800fec40`
- `0x180154870`
- `0x180156fbc`

## callees

- `0x1800cef08`
- `0x1800e30d0`
- `0x1800fcd1c`
- `0x1800fd274`
- `0x18010d6d4`
- `0x18010da10`
- `0x180114520`
- `0x180155584`
- `0x180155eb4`
- `0x180156004`
- `0x1801570dc`
- `0x18015734c`
- `0x180157cc0`
- `0x1801d1010`

## import_xrefs

- `GDI32!CreateSolidBrush` at `0x18010d78e`
- `GDI32!CreateSolidBrush` at `0x18010d78e`
- `GDI32!DeleteObject` at `0x18010d941`
- `GDI32!DeleteObject` at `0x18010d951`
- `GDI32!DeleteObject` at `0x18010d941`
- `GDI32!DeleteObject` at `0x18010d951`
- `GDI32!SetBkMode` at `0x18010d7cb`
- `GDI32!SetBkMode` at `0x18010d919`
- `GDI32!SetBkMode` at `0x18010d7cb`
- `GDI32!SetBkMode` at `0x18010d919`
- `GDI32!SetTextColor` at `0x18010d7de`
- `GDI32!SetTextColor` at `0x18010d926`
- `GDI32!SetTextColor` at `0x18010d7de`
- `GDI32!SetTextColor` at `0x18010d926`
- `GDI32!RectVisible` at `0x18010d846`
- `GDI32!RectVisible` at `0x18010d99a`
- `GDI32!RectVisible` at `0x18010d846`
- `GDI32!RectVisible` at `0x18010d99a`
- `GDI32!SelectObject` at `0x18010d7b6`
- `GDI32!SelectObject` at `0x18010d934`
- `GDI32!SelectObject` at `0x18010d7b6`
- `GDI32!SelectObject` at `0x18010d934`
- `GDI32!CreatePen` at `0x18010d7a6`
- `GDI32!CreatePen` at `0x18010d7a6`
- `USER32!DrawFocusRect` at `0x18010d9ac`
- `USER32!DrawFocusRect` at `0x18010d9ac`
- `USER32!InflateRect` at `0x18010d988`
- `USER32!InflateRect` at `0x18010d988`

## pseudocode

```c
void __fastcall CCalendar::_Paint(CCalendar *this, HDC a2, int a3)
{
  _DWORD *v5; // rcx
  BOOL v6; // r15d
  _DWORD *v7; // rcx
  BOOL v8; // r14d
  HPEN Pen; // r13
  int v10; // edi
  int v11; // esi
  __int128 v12; // xmm1
  __int64 v13; // rcx
  int i; // eax
  unsigned int CalendarUnit; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18; // r9d
  bool v19; // zf
  int mode; // [rsp+30h] [rbp-49h]
  COLORREF color; // [rsp+34h] [rbp-45h]
  HGDIOBJ h; // [rsp+38h] [rbp-41h]
  HDC hdc; // [rsp+40h] [rbp-39h] BYREF
  struct tagRECT rc; // [rsp+48h] [rbp-31h] BYREF
  RECT rect; // [rsp+58h] [rbp-21h] BYREF
  _OWORD v26[2]; // [rsp+68h] [rbp-11h] BYREF
  __int64 v27; // [rsp+88h] [rbp+Fh]

  hdc = a2;
  if ( a3 && (unsigned int)CCalendar::_InitZoomEffect(this, 0) && (v5 = (_DWORD *)*((_QWORD *)this + 100), v5[12]) )
  {
    v6 = (*(int (__fastcall **)(_DWORD *, HDC, HDC *))(*(_QWORD *)v5 + 16LL))(v5, hdc, &hdc) >= 0;
  }
  else
  {
    v6 = 0;
    if ( !a3 )
    {
LABEL_9:
      v8 = 0;
      goto LABEL_10;
    }
  }
  if ( !(unsigned int)CCalendar::_InitSlideEffect(this, 0) )
    goto LABEL_9;
  v7 = (_DWORD *)*((_QWORD *)this + 101);
  if ( !v7[12] )
    goto LABEL_9;
  v8 = (*(int (__fastcall **)(_DWORD *, HDC, HDC *))(*(_QWORD *)v7 + 16LL))(v7, hdc, &hdc) >= 0;
LABEL_10:
  *((_QWORD *)this + 93) = CreateSolidBrush(*((_DWORD *)this + 194));
  Pen = CreatePen(0, 0, *((_DWORD *)this + 193));
  v10 = 1;
  h = SelectObject(hdc, Pen);
  mode = SetBkMode(hdc, 1);
  color = SetTextColor(hdc, *((_DWORD *)this + 193));
  CCalendar::_PaintBackground(this, hdc);
  v11 = 0;
  v12 = *(_OWORD *)((char *)this + 1260);
  v26[0] = *(_OWORD *)((char *)this + 1244);
  v27 = *(_QWORD *)((char *)this + 1276);
  v26[1] = v12;
  for ( i = CCalInfo::CalDateCompare(v13, v26, (char *)this + 1284, 6, 0);
        i <= 0;
        i = CCalInfo::CalDateCompare(v17, v26, (char *)this + 1284, 6, 0) )
  {
    rect = 0;
    if ( CCalendar::_GetRectForOffset(this, v11, &rect) && RectVisible(hdc, &rect) )
      CCalendar::_PaintCalendar(this, hdc, &rect, v11, (const struct CALDATETIME *)v26);
    CalendarUnit = CCalendar::_GetCalendarUnit(this);
    if ( (unsigned int)CCalendar::_DateAdjustByStart(v16, v26, 1, CalendarUnit) == 1 )
      break;
    ++v11;
  }
  if ( !*((_QWORD *)this + 186) || (v18 = 1, *((_DWORD *)this + 392) != 33619971) )
    v18 = 0;
  CCalendar::_PaintArrowBtn(this, hdc, 1, v18);
  if ( !*((_QWORD *)this + 186) || *((_DWORD *)this + 392) != 16842755 )
    v10 = 0;
  CCalendar::_PaintArrowBtn(this, hdc, 0, v10);
  if ( (*((_BYTE *)this + 16) & 0x10) == 0 )
    CCalendar::_PaintFooter(this, hdc);
  SetBkMode(hdc, mode);
  SetTextColor(hdc, color);
  SelectObject(hdc, h);
  DeleteObject(*((HGDIOBJ *)this + 93));
  *((_QWORD *)this + 93) = 0;
  DeleteObject(Pen);
  v19 = (*((_BYTE *)this + 1588) & 0x10) == 0;
  rc = 0;
  if ( !v19
    && (unsigned int)CCalendar::_GetRectForDate(this, (CCalendar *)((char *)this + 1204), &rc)
    && InflateRect(&rc, -1, -1)
    && RectVisible(hdc, &rc) )
  {
    DrawFocusRect(hdc, &rc);
  }
  if ( v6 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 100) + 24LL))(*((_QWORD *)this + 100));
  if ( v8 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 101) + 24LL))(*((_QWORD *)this + 101));
}

```

## disassembly

```asm
0x18010d6d4  mov     [rsp-8+arg_10], rbx
0x18010d6d9  push    rbp
0x18010d6da  push    rsi
0x18010d6db  push    rdi
0x18010d6dc  push    r12
0x18010d6de  push    r13
0x18010d6e0  push    r14
0x18010d6e2  push    r15
0x18010d6e4  lea     rbp, [rsp-27h]
0x18010d6e9  sub     rsp, 0A0h
0x18010d6f0  mov     rax, cs:__security_cookie
0x18010d6f7  xor     rax, rsp
0x18010d6fa  mov     [rbp+57h+var_40], rax
0x18010d6fe  mov     [rbp+57h+hdc], rdx
0x18010d702  mov     edi, r8d
0x18010d705  mov     rbx, rcx
0x18010d708  test    r8d, r8d
0x18010d70b  jz      short loc_18010D744
0x18010d70d  xor     edx, edx; int
0x18010d70f  call    ?_InitZoomEffect@CCalendar@@AEAAHH@Z; CCalendar::_InitZoomEffect(int)
0x18010d714  test    eax, eax
0x18010d716  jz      short loc_18010D744
0x18010d718  mov     rcx, [rbx+320h]
0x18010d71f  cmp     dword ptr [rcx+30h], 0
0x18010d723  jz      short loc_18010D744
0x18010d725  mov     rax, [rcx]
0x18010d728  lea     r8, [rbp+57h+hdc]
0x18010d72c  mov     rdx, [rbp+57h+hdc]
0x18010d730  mov     rax, [rax+10h]
0x18010d734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d739  xor     r15d, r15d
0x18010d73c  test    eax, eax
0x18010d73e  setns   r15b
0x18010d742  jmp     short loc_18010D74B
0x18010d744  xor     r15d, r15d
0x18010d747  test    edi, edi
0x18010d749  jz      short loc_18010D785
0x18010d74b  xor     edx, edx; int
0x18010d74d  mov     rcx, rbx; this
0x18010d750  call    ?_InitSlideEffect@CCalendar@@AEAAHH@Z; CCalendar::_InitSlideEffect(int)
0x18010d755  test    eax, eax
0x18010d757  jz      short loc_18010D785
0x18010d759  mov     rcx, [rbx+328h]
0x18010d760  cmp     dword ptr [rcx+30h], 0
0x18010d764  jz      short loc_18010D785
0x18010d766  mov     rax, [rcx]
0x18010d769  lea     r8, [rbp+57h+hdc]
0x18010d76d  mov     rdx, [rbp+57h+hdc]
0x18010d771  mov     rax, [rax+10h]
0x18010d775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d77a  xor     r14d, r14d
0x18010d77d  test    eax, eax
0x18010d77f  setns   r14b
0x18010d783  jmp     short loc_18010D788
0x18010d785  xor     r14d, r14d
0x18010d788  mov     ecx, [rbx+308h]; color
0x18010d78e  call    cs:__imp_CreateSolidBrush
0x18010d794  mov     [rbx+2E8h], rax
0x18010d79b  xor     edx, edx; cWidth
0x18010d79d  mov     r8d, [rbx+304h]; color
0x18010d7a4  xor     ecx, ecx; iStyle
0x18010d7a6  call    cs:__imp_CreatePen
0x18010d7ac  mov     rcx, [rbp+57h+hdc]; hdc
0x18010d7b0  mov     rdx, rax; h
0x18010d7b3  mov     r13, rax
0x18010d7b6  call    cs:__imp_SelectObject
0x18010d7bc  mov     rcx, [rbp+57h+hdc]; hdc
0x18010d7c0  mov     edi, 1
0x18010d7c5  mov     edx, edi; mode
0x18010d7c7  mov     [rbp+57h+h], rax
0x18010d7cb  call    cs:__imp_SetBkMode
0x18010d7d1  mov     edx, [rbx+304h]; color
0x18010d7d7  mov     rcx, [rbp+57h+hdc]; hdc
0x18010d7db  mov     [rbp+57h+mode], eax
0x18010d7de  call    cs:__imp_SetTextColor
0x18010d7e4  mov     rdx, [rbp+57h+hdc]; HDC
0x18010d7e8  mov     rcx, rbx; this
0x18010d7eb  mov     [rbp+57h+color], eax
0x18010d7ee  call    ?_PaintBackground@CCalendar@@AEAAXPEAUHDC__@@@Z; CCalendar::_PaintBackground(HDC__ *)
0x18010d7f3  movups  xmm0, xmmword ptr [rbx+4DCh]
0x18010d7fa  xor     esi, esi
0x18010d7fc  lea     r12, [rbx+504h]
0x18010d803  movups  xmm1, xmmword ptr [rbx+4ECh]
0x18010d80a  mov     dword ptr [rsp+0D0h+var_B0], esi
0x18010d80e  movups  [rbp+57h+var_68], xmm0
0x18010d812  movsd   xmm0, qword ptr [rbx+4FCh]
0x18010d81a  movsd   [rbp+57h+var_48], xmm0
0x18010d81f  movups  [rbp+57h+var_58], xmm1
0x18010d823  jmp     short loc_18010D891
0x18010d825  xorps   xmm0, xmm0
0x18010d828  lea     r8, [rbp+57h+rect]; struct tagRECT *
0x18010d82c  mov     edx, esi; int
0x18010d82e  mov     rcx, rbx; this
0x18010d831  movups  xmmword ptr [rbp+57h+rect.left], xmm0
0x18010d835  call    ?_GetRectForOffset@CCalendar@@AEAAHHPEAUtagRECT@@@Z; CCalendar::_GetRectForOffset(int,tagRECT *)
0x18010d83a  test    eax, eax
0x18010d83c  jz      short loc_18010D86C
0x18010d83e  mov     rcx, [rbp+57h+hdc]; hdc
0x18010d842  lea     rdx, [rbp+57h+rect]; lprect
0x18010d846  call    cs:__imp_RectVisible
0x18010d84c  test    eax, eax
0x18010d84e  jz      short loc_18010D86C
0x18010d850  mov     rdx, [rbp+57h+hdc]; hdc
0x18010d854  lea     rax, [rbp+57h+var_68]
0x18010d858  mov     r9d, esi; int
0x18010d85b  mov     [rsp+0D0h+var_B0], rax; struct CALDATETIME *
0x18010d860  lea     r8, [rbp+57h+rect]; struct tagRECT *
0x18010d864  mov     rcx, rbx; this
0x18010d867  call    ?_PaintCalendar@CCalendar@@AEAAXPEAUHDC__@@PEBUtagRECT@@HPEBUCALDATETIME@@@Z; CCalendar::_PaintCalendar(HDC__ *,tagRECT const *,int,CALDATETIME const *)
0x18010d86c  mov     rcx, rbx
0x18010d86f  call    ?_GetCalendarUnit@CCalendar@@AEAA?AW4CALUNIT@@XZ; CCalendar::_GetCalendarUnit(void)
0x18010d874  mov     r9d, eax
0x18010d877  lea     rdx, [rbp+57h+var_68]
0x18010d87b  mov     r8d, edi
0x18010d87e  call    ?_DateAdjustByStart@CCalendar@@AEAAHPEAUCALDATETIME@@HW4CALUNIT@@@Z; CCalendar::_DateAdjustByStart(CALDATETIME *,int,CALUNIT)
0x18010d883  cmp     eax, edi
0x18010d885  jz      short loc_18010D8AB
0x18010d887  add     esi, edi
0x18010d889  mov     dword ptr [rsp+0D0h+var_B0], 0
0x18010d891  mov     r9d, 6
0x18010d897  lea     rdx, [rbp+57h+var_68]
0x18010d89b  mov     r8, r12
0x18010d89e  call    ?CalDateCompare@CCalInfo@@QEAAHPEBUCALDATETIME@@0W4CALUNIT@@1@Z; CCalInfo::CalDateCompare(CALDATETIME const *,CALDATETIME const *,CALUNIT,CALUNIT)
0x18010d8a3  test    eax, eax
0x18010d8a5  jle     loc_18010D825
0x18010d8ab  xor     esi, esi
0x18010d8ad  cmp     [rbx+5D0h], rsi
0x18010d8b4  jz      short loc_18010D8C5
0x18010d8b6  cmp     dword ptr [rbx+620h], 2010003h
0x18010d8c0  mov     r9d, edi
0x18010d8c3  jz      short loc_18010D8C8
0x18010d8c5  mov     r9d, esi; int
0x18010d8c8  mov     rdx, [rbp+57h+hdc]; HDC
0x18010d8cc  mov     r8d, edi; int
0x18010d8cf  mov     rcx, rbx; this
0x18010d8d2  call    ?_PaintArrowBtn@CCalendar@@AEAAXPEAUHDC__@@HH@Z; CCalendar::_PaintArrowBtn(HDC__ *,int,int)
0x18010d8d7  cmp     [rbx+5D0h], rsi
0x18010d8de  jz      short loc_18010D8EC
0x18010d8e0  cmp     dword ptr [rbx+620h], 1010003h
0x18010d8ea  jz      short loc_18010D8EE
0x18010d8ec  mov     edi, esi
0x18010d8ee  mov     rdx, [rbp+57h+hdc]; HDC
0x18010d8f2  mov     r9d, edi; int
0x18010d8f5  xor     r8d, r8d; int
0x18010d8f8  mov     rcx, rbx; this
0x18010d8fb  call    ?_PaintArrowBtn@CCalendar@@AEAAXPEAUHDC__@@HH@Z; CCalendar::_PaintArrowBtn(HDC__ *,int,int)
0x18010d900  test    byte ptr [rbx+10h], 10h
0x18010d904  jnz     short loc_18010D912
0x18010d906  mov     rdx, [rbp+57h+hdc]; HDC
0x18010d90a  mov     rcx, rbx; this
0x18010d90d  call    ?_PaintFooter@CCalendar@@AEAAXPEAUHDC__@@@Z; CCalendar::_PaintFooter(HDC__ *)
0x18010d912  mov     edx, [rbp+57h+mode]; mode
0x18010d915  mov     rcx, [rbp+57h+hdc]; hdc
0x18010d919  call    cs:__imp_SetBkMode
0x18010d91f  mov     edx, [rbp+57h+color]; color
0x18010d922  mov     rcx, [rbp+57h+hdc]; hdc
0x18010d926  call    cs:__imp_SetTextColor
0x18010d92c  mov     rdx, [rbp+57h+h]; h
0x18010d930  mov     rcx, [rbp+57h+hdc]; hdc
0x18010d934  call    cs:__imp_SelectObject
0x18010d93a  mov     rcx, [rbx+2E8h]; ho
0x18010d941  call    cs:__imp_DeleteObject
0x18010d947  mov     rcx, r13; ho
0x18010d94a  mov     [rbx+2E8h], rsi
0x18010d951  call    cs:__imp_DeleteObject
0x18010d957  test    byte ptr [rbx+634h], 10h
0x18010d95e  xorps   xmm0, xmm0
0x18010d961  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x18010d965  jz      short loc_18010D9B2
0x18010d967  lea     rdx, [rbx+4B4h]; struct CALDATETIME *
0x18010d96e  mov     rcx, rbx; this
0x18010d971  lea     r8, [rbp+57h+rc]; struct tagRECT *
0x18010d975  call    ?_GetRectForDate@CCalendar@@AEAAHPEBUCALDATETIME@@PEAUtagRECT@@@Z; CCalendar::_GetRectForDate(CALDATETIME const *,tagRECT *)
0x18010d97a  test    eax, eax
0x18010d97c  jz      short loc_18010D9B2
0x18010d97e  or      edx, 0FFFFFFFFh; dx
0x18010d981  lea     rcx, [rbp+57h+rc]; lprc
0x18010d985  mov     r8d, edx; dy
0x18010d988  call    cs:__imp_InflateRect
0x18010d98e  test    eax, eax
0x18010d990  jz      short loc_18010D9B2
0x18010d992  mov     rcx, [rbp+57h+hdc]; hdc
0x18010d996  lea     rdx, [rbp+57h+rc]; lprect
0x18010d99a  call    cs:__imp_RectVisible
0x18010d9a0  test    eax, eax
0x18010d9a2  jz      short loc_18010D9B2
0x18010d9a4  mov     rcx, [rbp+57h+hdc]; hDC
0x18010d9a8  lea     rdx, [rbp+57h+rc]; lprc
0x18010d9ac  call    cs:__imp_DrawFocusRect
0x18010d9b2  test    r15d, r15d
0x18010d9b5  jz      short loc_18010D9CA
0x18010d9b7  mov     rcx, [rbx+320h]
0x18010d9be  mov     rax, [rcx]
0x18010d9c1  mov     rax, [rax+18h]
0x18010d9c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d9ca  test    r14d, r14d
0x18010d9cd  jz      short loc_18010D9E2
0x18010d9cf  mov     rcx, [rbx+328h]
0x18010d9d6  mov     rax, [rcx]
0x18010d9d9  mov     rax, [rax+18h]
0x18010d9dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d9e2  mov     rcx, [rbp+57h+var_40]
0x18010d9e6  xor     rcx, rsp; StackCookie
0x18010d9e9  call    __security_check_cookie
0x18010d9ee  mov     rbx, [rsp+0D0h+arg_10]
0x18010d9f6  add     rsp, 0A0h
0x18010d9fd  pop     r15
0x18010d9ff  pop     r14
0x18010da01  pop     r13
0x18010da03  pop     r12
0x18010da05  pop     rdi
0x18010da06  pop     rsi
0x18010da07  pop     rbp
0x18010da08  retn
```
