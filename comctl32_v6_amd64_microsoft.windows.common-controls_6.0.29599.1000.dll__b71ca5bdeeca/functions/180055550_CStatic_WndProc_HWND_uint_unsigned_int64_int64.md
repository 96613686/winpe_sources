# CStatic::WndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180055550`
- end: `0x180055c77`
- name: `?WndProc@CStatic@@AEAA_JPEAUHWND__@@I_K_J@Z`
- size: `1831`
- prototype: `__int64 __fastcall(CStatic *__hidden this, HWND, UINT Msg, HDC hdc, LPARAM lParam)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, installer_update`

## callers

- `0x180055460`

## callees

- `0x180005a6c`
- `0x180026340`
- `0x180054c08`
- `0x180054d50`
- `0x180055550`
- `0x180055c80`
- `0x180055cdc`
- `0x180055e60`
- `0x1800565f4`
- `0x1800d3ab0`
- `0x1800ecf64`
- `0x180114520`
- `0x180114ebc`
- `0x180116cac`
- `0x18013b2c0`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800557ac`
- `GDI32!DeleteObject` at `0x1800557ac`
- `USER32!DestroyIcon` at `0x180055a23`
- `USER32!DestroyIcon` at `0x180055a23`
- `USER32!IsWindowVisible` at `0x1800557e1`
- `USER32!IsWindowVisible` at `0x18005592e`
- `USER32!IsWindowVisible` at `0x1800557e1`
- `USER32!IsWindowVisible` at `0x18005592e`
- `USER32!SetWindowPos` at `0x180055731`
- `USER32!SetWindowPos` at `0x180055731`
- `USER32!SetWindowLongW` at `0x1800559d4`
- `USER32!SetWindowLongW` at `0x1800559d4`
- `USER32!KillTimer` at `0x180055a19`
- `USER32!KillTimer` at `0x180055a19`
- `USER32!GetParent` at `0x1800556b1`
- `USER32!GetParent` at `0x1800556b1`
- `USER32!DefWindowProcW` at `0x180055602`
- `USER32!DefWindowProcW` at `0x18005565b`
- `USER32!DefWindowProcW` at `0x180055882`
- `USER32!DefWindowProcW` at `0x180055602`
- `USER32!DefWindowProcW` at `0x18005565b`
- `USER32!DefWindowProcW` at `0x180055882`
- `USER32!SetWindowLongPtrW` at `0x180055753`
- `USER32!SetWindowLongPtrW` at `0x180055753`
- `USER32!GetSystemMetrics` at `0x180055708`
- `USER32!GetSystemMetrics` at `0x1800559ec`
- `USER32!GetSystemMetrics` at `0x180055708`
- `USER32!GetSystemMetrics` at `0x1800559ec`
- `USER32!GetWindowLongPtrW` at `0x18005581b`
- `USER32!GetWindowLongPtrW` at `0x18005581b`
- `USER32!GetClientRect` at `0x1800556f3`
- `USER32!GetClientRect` at `0x1800556f3`
- `USER32!UpdateWindow` at `0x180055803`
- `USER32!UpdateWindow` at `0x180055803`
- `USER32!InvalidateRect` at `0x1800557fa`
- `USER32!InvalidateRect` at `0x1800557fa`
- `USER32!BeginPaint` at `0x180055922`
- `USER32!BeginPaint` at `0x180055922`
- `USER32!EndPaint` at `0x18005594d`
- `USER32!EndPaint` at `0x18005594d`
- `UxTheme!CloseThemeData` at `0x180055745`
- `UxTheme!CloseThemeData` at `0x180055745`
- `UxTheme!EnableThemeDialogTexture` at `0x1800556bf`
- `UxTheme!EnableThemeDialogTexture` at `0x1800556bf`

## pseudocode

```c
struct tagPOINT __fastcall CStatic::WndProc(HICON *this, HWND a2, HWND Msg, HDC hdc, LPARAM lParam)
{
  HDC v5; // r14
  __int64 v6; // rbx
  WPARAM v7; // rsi
  UINT v8; // edi
  HWND v9; // rbp
  __int64 v12; // rsi
  __int64 v13; // rdi
  HWND Parent; // rax
  LONG cy; // eax
  LONG right; // ecx
  HICON v17; // rcx
  __int64 v18; // rdx
  HICON v19; // rcx
  LONG_PTR WindowLongPtrW; // rax
  int v21; // r12d
  int v22; // ebx
  HICON v23; // rcx
  int v24; // edx
  HDC v25; // rdi
  int v26; // r9d
  struct tagRECT Rect; // [rsp+40h] [rbp-A8h] BYREF
  struct tagPAINTSTRUCT Paint; // [rsp+50h] [rbp-98h] BYREF

  v5 = (HDC)lParam;
  v6 = 0;
  v7 = (WPARAM)hdc;
  v8 = (unsigned int)Msg;
  v9 = a2;
  if ( (unsigned int)Msg <= 0x113 )
  {
    if ( (_DWORD)Msg != 275 )
    {
      switch ( (int)Msg )
      {
        case 1:
          CStatic::UpdateTheme((CStatic *)this);
          v13 = (_BYTE)this[6][3] & 0x1F;
          Parent = GetParent((HWND)*this);
          EnableThemeDialogTexture(Parent, 2u);
          if ( (byte_1801F06A8[v13] & 3) == 1 )
          {
            CStatic::LoadImageW((CStatic *)this, *(PCWSTR *)(lParam + 56));
          }
          else if ( (unsigned __int8)(v13 - 16) <= 1u )
          {
            Rect = 0;
            GetClientRect(v9, &Rect);
            if ( (_BYTE)v13 == 16 )
            {
              cy = GetSystemMetrics(46);
              right = Rect.right;
              Rect.bottom = cy;
            }
            else
            {
              right = GetSystemMetrics(45);
              Rect.right = right;
              cy = Rect.bottom;
            }
            SetWindowPos(v9, 0, 0, 0, right, cy, 0x16u);
          }
          return (struct tagPOINT)v6;
        case 2:
          v18 = (_BYTE)this[6][3] & 0x1F;
          if ( (byte_1801F06A8[v18] & 3) == 1 )
          {
            v19 = this[2];
            if ( v19 )
            {
              if ( ((_BYTE)this[4] & 1) != 0 )
              {
                if ( (_BYTE)v18 == 14 )
                {
                  DeleteObject(v19);
                }
                else if ( (_BYTE)v18 == 3 )
                {
                  if ( *((int *)this + 6) > 1 )
                    KillTimer(v9, 0xFFFDu);
                  DestroyIcon(this[2]);
                }
              }
            }
          }
          return (struct tagPOINT)v6;
        case 5:
          return (struct tagPOINT)v6;
        case 10:
          CStatic::Repaint((LPARAM)this);
          if ( ((_DWORD)this[6][3] & 0x100) == 0 )
            return (struct tagPOINT)v6;
          v26 = 3 - (v7 != 0);
          goto LABEL_63;
        case 12:
          if ( (byte_1801F06A8[(_BYTE)this[6][3] & 0x1F] & 0x10) == 0 || !DefWindowProcW(a2, 0xCu, (WPARAM)hdc, lParam) )
            return (struct tagPOINT)v6;
          CStatic::Repaint((LPARAM)this);
          return (struct tagPOINT)1LL;
        case 15:
          memset_0(&Paint, 0, sizeof(Paint));
          if ( v7 )
            v25 = (HDC)v7;
          else
            v25 = BeginPaint(v9, &Paint);
          if ( IsWindowVisible(v9) )
            CStatic::OnPaint((LPARAM)this, v25, v7 == 0);
          if ( !v7 )
            EndPaint(v9, &Paint);
          return (struct tagPOINT)v6;
        case 20:
          return (struct tagPOINT)1LL;
        case 48:
          if ( (byte_1801F06A8[(_BYTE)this[6][3] & 0x1F] & 8) != 0 )
          {
            this[1] = (HICON)hdc;
            if ( lParam )
            {
              if ( IsWindowVisible(a2) )
              {
                InvalidateRect(v9, 0, 1);
                UpdateWindow(v9);
              }
            }
          }
          return (struct tagPOINT)v6;
        case 49:
          if ( (byte_1801F06A8[(_BYTE)this[6][3] & 0x1F] & 8) == 0 )
            return (struct tagPOINT)v6;
          return (struct tagPOINT)this[1];
        case 61:
          v6 = 65539;
          if ( (_DWORD)lParam != -12 )
            return 0;
          return (struct tagPOINT)v6;
        case 129:
          *this = (HICON)a2;
          WindowLongPtrW = GetWindowLongPtrW(a2, -1);
          this[6] = (HICON)WindowLongPtrW;
          v21 = *(_DWORD *)(WindowLongPtrW + 8);
          v22 = *(_DWORD *)(WindowLongPtrW + 12);
          if ( (v21 & 0x1000) != 0 )
            AlterWindowStyle(v9);
          if ( (v22 & 0x1000) != 0 || (unsigned __int8)((v22 & 0x1F) - 16) <= 1u )
            SetWindowLongW(v9, -20, v21 | 0x20000);
          DPISCALEINFO::Initialize((DPISCALEINFO *)(this + 7), v9);
          return (struct tagPOINT)DefWindowProcW(v9, v8, v7, lParam);
        case 130:
          v17 = this[5];
          if ( v17 )
            CloseThemeData(v17);
          SetWindowLongPtrW(v9, 0, 0);
          operator delete(this, 0x48u);
          return (struct tagPOINT)v6;
        case 132:
          v12 = 1;
          if ( ((_DWORD)this[6][3] & 0x100) == 0 )
            return (struct tagPOINT)-1LL;
          return (struct tagPOINT)v12;
        case 135:
          return (struct tagPOINT)256LL;
        case 161:
          goto LABEL_87;
        case 163:
          goto LABEL_93;
        default:
          return (struct tagPOINT)DefWindowProcW(v9, v8, v7, lParam);
      }
    }
    if ( hdc == (HDC)65533 )
      CStatic::AniIconStep((CStatic *)this);
    return (struct tagPOINT)v6;
  }
  if ( (unsigned int)Msg > 0x201 )
  {
    if ( (_DWORD)Msg != 515 )
    {
      switch ( (_DWORD)Msg )
      {
        case 0x2E2:
          if ( (unsigned int)DPISCALEINFO::HandleDPIChanged(this + 7, a2, 21) )
            CStatic::UpdateTheme((CStatic *)this);
          return (struct tagPOINT)v6;
        case 0x318:
          CStatic::OnPaint((LPARAM)this, hdc, 0);
          return (struct tagPOINT)v6;
        case 0x31A:
          CStatic::UpdateTheme((CStatic *)this);
          return (struct tagPOINT)1LL;
      }
      return (struct tagPOINT)DefWindowProcW(v9, v8, v7, lParam);
    }
LABEL_93:
    CStatic::CopyText((CStatic *)this);
    if ( ((_DWORD)this[6][3] & 0x100) == 0 )
      return (struct tagPOINT)v6;
    v26 = 1;
LABEL_63:
    a2 = v9;
LABEL_64:
    CStatic::NotifyParent((CStatic *)this, a2, Msg, v26);
    return (struct tagPOINT)v6;
  }
  switch ( (_DWORD)Msg )
  {
    case 0x201:
LABEL_87:
      if ( ((_DWORD)this[6][3] & 0x100) == 0 )
        return (struct tagPOINT)v6;
      v26 = 0;
      goto LABEL_64;
    case 0x128:
      DefWindowProcW(a2, 0x128u, (WPARAM)hdc, lParam);
      if ( (v7 & 0x20000) != 0 )
      {
        v23 = this[6];
        v24 = *((_DWORD *)v23 + 3);
        if ( ((v24 & 0x1Fu) <= 2 || (unsigned __int8)((v24 & 0x1F) - 11) <= 2u)
          && (v24 & 0x80u) == 0
          && ((_DWORD)v23[2] & 0x40000000) == 0 )
        {
          *((_DWORD *)this + 8) |= 2u;
          CStatic::Repaint((LPARAM)this);
          *((_DWORD *)this + 8) &= ~2u;
        }
      }
      return (struct tagPOINT)v6;
    case 0x170:
      v5 = hdc;
      v7 = 1;
      break;
    case 0x171:
      v7 = 1;
      goto LABEL_77;
    case 0x172:
      if ( (unsigned __int64)hdc >= 4 )
        return (struct tagPOINT)v6;
      break;
    case 0x173:
      if ( (unsigned __int64)hdc >= 4 )
        return (struct tagPOINT)v6;
LABEL_77:
      if ( byte_1801F4B20[v7] == ((_BYTE)this[6][3] & 0x1F) )
        return (struct tagPOINT)this[2];
      return (struct tagPOINT)v6;
    default:
      return (struct tagPOINT)DefWindowProcW(v9, v8, v7, lParam);
  }
  if ( byte_1801F4B20[v7] == ((_BYTE)this[6][3] & 0x1F) )
    return CStatic::SetImage((CStatic *)this, v5, 0);
  return (struct tagPOINT)v6;
}

```

## disassembly

```asm
0x180055550  push    rbx
0x180055552  push    rbp
0x180055553  push    rsi
0x180055554  push    rdi
0x180055555  push    r12
0x180055557  push    r14
0x180055559  push    r15
0x18005555b  sub     rsp, 0B0h
0x180055562  mov     rax, cs:__security_cookie
0x180055569  xor     rax, rsp
0x18005556c  mov     [rsp+0E8h+var_48], rax
0x180055574  mov     r14, [rsp+0E8h+lParam]
0x18005557c  xor     ebx, ebx
0x18005557e  mov     rsi, r9
0x180055581  mov     edi, r8d
0x180055584  mov     rbp, rdx
0x180055587  mov     r15, rcx
0x18005558a  cmp     r8d, 113h
0x180055591  ja      short loc_1800555C1
0x180055593  jz      loc_180055AE0
0x180055599  lea     eax, [r8-1]; switch 163 cases
0x18005559d  cmp     eax, 0A2h
0x1800555a2  ja      short def_1800555BF; jumptable 00000001800555BF default case, cases 3,4,6-9,11,13,14,16-19,21-47,50-60,62-128,131,133,134,136-160,162
0x1800555a4  lea     r12, __ImageBase
0x1800555ab  movzx   eax, ds:(byte_180055BD4 - 180000000h)[r12+rax]
0x1800555b4  mov     ecx, ds:(jpt_1800555BF - 180000000h)[r12+rax*4]
0x1800555bc  add     rcx, r12
0x1800555bf  jmp     rcx; switch jump
0x1800555c1  cmp     edi, 201h
0x1800555c7  jbe     loc_180055861
0x1800555cd  mov     eax, edi
0x1800555cf  sub     eax, 203h
0x1800555d4  jz      loc_180055B6A; jumptable 00000001800555BF case 163
0x1800555da  sub     eax, 0DFh
0x1800555df  jz      loc_180055B46
0x1800555e5  sub     eax, 36h ; '6'
0x1800555e8  jz      loc_180055B36
0x1800555ee  cmp     eax, 2
0x1800555f1  jz      loc_180055B27
0x1800555f7  mov     r9, r14; jumptable 00000001800555BF default case, cases 3,4,6-9,11,13,14,16-19,21-47,50-60,62-128,131,133,134,136-160,162
0x1800555fa  mov     r8, rsi; wParam
0x1800555fd  mov     edx, edi; Msg
0x1800555ff  mov     rcx, rbp; hWnd
0x180055602  call    cs:__imp_DefWindowProcW
0x180055608  mov     rbx, rax
0x18005560b  mov     rax, rbx; jumptable 00000001800555BF case 5
0x18005560e  mov     rcx, [rsp+0E8h+var_48]
0x180055616  xor     rcx, rsp; StackCookie
0x180055619  call    __security_check_cookie
0x18005561e  add     rsp, 0B0h
0x180055625  pop     r15
0x180055627  pop     r14
0x180055629  pop     r12
0x18005562b  pop     rdi
0x18005562c  pop     rsi
0x18005562d  pop     rbp
0x18005562e  pop     rbx
0x18005562f  retn
0x180055630  mov     eax, 100h; jumptable 00000001800555BF case 135
0x180055635  jmp     short loc_18005560E
0x180055637  mov     rax, [r15+30h]; jumptable 00000001800555BF case 12
0x18005563b  movzx   ecx, byte ptr [rax+0Ch]
0x18005563f  and     ecx, 1Fh
0x180055642  test    byte ptr [rcx+r12+1F06A8h], 10h
0x18005564b  jz      short loc_18005560B; jumptable 00000001800555BF case 5
0x18005564d  mov     r9, r14; lParam
0x180055650  mov     r8, rsi; wParam
0x180055653  mov     edx, 0Ch; Msg
0x180055658  mov     rcx, rbp; hWnd
0x18005565b  call    cs:__imp_DefWindowProcW
0x180055661  test    rax, rax
0x180055664  jz      short loc_18005560B; jumptable 00000001800555BF case 5
0x180055666  mov     rcx, r15; lData
0x180055669  call    ?Repaint@CStatic@@AEAAXXZ; CStatic::Repaint(void)
0x18005566e  mov     eax, 1
0x180055673  jmp     short loc_18005560E
0x180055675  mov     rax, [r15+30h]; jumptable 00000001800555BF case 132
0x180055679  mov     esi, 1
0x18005567e  test    dword ptr [rax+0Ch], 100h
0x180055685  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18005568c  cmovz   rsi, rax
0x180055690  mov     rax, rsi
0x180055693  jmp     loc_18005560E
0x180055698  mov     rcx, r15; jumptable 00000001800555BF case 1
0x18005569b  call    ?UpdateTheme@CStatic@@AEAAXXZ; CStatic::UpdateTheme(void)
0x1800556a0  mov     rax, [r15+30h]
0x1800556a4  movzx   ecx, byte ptr [rax+0Ch]
0x1800556a8  and     cl, 1Fh
0x1800556ab  movzx   edi, cl
0x1800556ae  mov     rcx, [r15]; hWnd
0x1800556b1  call    cs:__imp_GetParent
0x1800556b7  mov     rcx, rax; hwnd
0x1800556ba  mov     edx, 2; dwFlags
0x1800556bf  call    cs:__imp_EnableThemeDialogTexture
0x1800556c5  movzx   eax, byte ptr [rdi+r12+1F06A8h]
0x1800556ce  and     al, 3
0x1800556d0  cmp     al, 1
0x1800556d2  jz      loc_180055958
0x1800556d8  lea     eax, [rdi-10h]
0x1800556db  cmp     al, 1
0x1800556dd  ja      loc_18005560B; jumptable 00000001800555BF case 5
0x1800556e3  xorps   xmm0, xmm0
0x1800556e6  lea     rdx, [rsp+0E8h+Rect]; lpRect
0x1800556eb  mov     rcx, rbp; hWnd
0x1800556ee  movups  xmmword ptr [rsp+0E8h+Rect.left], xmm0
0x1800556f3  call    cs:__imp_GetClientRect
0x1800556f9  cmp     dil, 10h
0x1800556fd  jnz     loc_1800559E7
0x180055703  mov     ecx, 2Eh ; '.'; nIndex
0x180055708  call    cs:__imp_GetSystemMetrics
0x18005570e  mov     ecx, [rsp+0E8h+Rect.right]
0x180055712  mov     [rsp+0E8h+Rect.bottom], eax
0x180055716  mov     [rsp+0E8h+uFlags], 16h; uFlags
0x18005571e  xor     r9d, r9d; Y
0x180055721  mov     [rsp+0E8h+cy], eax; cy
0x180055725  xor     r8d, r8d; X
0x180055728  mov     [rsp+0E8h+var_C8], ecx; cx
0x18005572c  xor     edx, edx; hWndInsertAfter
0x18005572e  mov     rcx, rbp; hWnd
0x180055731  call    cs:__imp_SetWindowPos
0x180055737  jmp     loc_18005560B; jumptable 00000001800555BF case 5
0x18005573c  mov     rcx, [r15+28h]; jumptable 00000001800555BF case 130
0x180055740  test    rcx, rcx
0x180055743  jz      short loc_18005574B
0x180055745  call    cs:__imp_CloseThemeData
0x18005574b  xor     r8d, r8d; dwNewLong
0x18005574e  xor     edx, edx; nIndex
0x180055750  mov     rcx, rbp; hWnd
0x180055753  call    cs:__imp_SetWindowLongPtrW
0x180055759  mov     edx, 48h ; 'H'; unsigned __int64
0x18005575e  mov     rcx, r15; void *
0x180055761  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180055766  jmp     loc_18005560B; jumptable 00000001800555BF case 5
0x18005576b  mov     rax, [r15+30h]; jumptable 00000001800555BF case 2
0x18005576f  movzx   ecx, byte ptr [rax+0Ch]
0x180055773  and     cl, 1Fh
0x180055776  movzx   edx, cl
0x180055779  movzx   eax, byte ptr [rdx+r12+1F06A8h]
0x180055782  and     al, 3
0x180055784  cmp     al, 1
0x180055786  jnz     loc_18005560B; jumptable 00000001800555BF case 5
0x18005578c  mov     rcx, [r15+10h]; ho
0x180055790  test    rcx, rcx
0x180055793  jz      loc_18005560B; jumptable 00000001800555BF case 5
0x180055799  test    [r15+20h], al
0x18005579d  jz      loc_18005560B; jumptable 00000001800555BF case 5
0x1800557a3  cmp     dl, 0Eh
0x1800557a6  jnz     loc_180055A01
0x1800557ac  call    cs:__imp_DeleteObject
0x1800557b2  jmp     loc_18005560B; jumptable 00000001800555BF case 5
0x1800557b7  mov     rax, [r15+30h]; jumptable 00000001800555BF case 48
0x1800557bb  movzx   ecx, byte ptr [rax+0Ch]
0x1800557bf  and     ecx, 1Fh
0x1800557c2  test    byte ptr [rcx+r12+1F06A8h], 8
0x1800557cb  jz      loc_18005560B; jumptable 00000001800555BF case 5
0x1800557d1  mov     [r15+8], rsi
0x1800557d5  test    r14, r14
0x1800557d8  jz      loc_18005560B; jumptable 00000001800555BF case 5
0x1800557de  mov     rcx, rbp; hWnd
0x1800557e1  call    cs:__imp_IsWindowVisible
0x1800557e7  test    eax, eax
0x1800557e9  jz      loc_18005560B; jumptable 00000001800555BF case 5
0x1800557ef  xor     edx, edx; lpRect
0x1800557f1  mov     r8d, 1; bErase
0x1800557f7  mov     rcx, rbp; hWnd
0x1800557fa  call    cs:__imp_InvalidateRect
0x180055800  mov     rcx, rbp; hWnd
0x180055803  call    cs:__imp_UpdateWindow
0x180055809  jmp     loc_18005560B; jumptable 00000001800555BF case 5
0x18005580e  mov     rdx, 0FFFFFFFFFFFFFFFFh; jumptable 00000001800555BF case 129
0x180055815  mov     [r15], rbp
0x180055818  mov     rcx, rbp; hWnd
0x18005581b  call    cs:__imp_GetWindowLongPtrW
0x180055821  mov     [r15+30h], rax
0x180055825  mov     r12d, [rax+8]
0x180055829  mov     ebx, [rax+0Ch]
0x18005582c  bt      r12d, 0Ch
0x180055831  jb      loc_1800559AC
0x180055837  bt      ebx, 0Ch
0x18005583b  jb      loc_1800559C4
0x180055841  and     bl, 1Fh
0x180055844  sub     bl, 10h
0x180055847  cmp     bl, 1
0x18005584a  jbe     loc_1800559C4
0x180055850  lea     rcx, [r15+38h]; this
0x180055854  mov     rdx, rbp; HWND
0x180055857  call    ?Initialize@DPISCALEINFO@@QEAAXPEAUHWND__@@@Z; DPISCALEINFO::Initialize(HWND__ *)
0x18005585c  jmp     def_1800555BF; jumptable 00000001800555BF default case, cases 3,4,6-9,11,13,14,16-19,21-47,50-60,62-128,131,133,134,136-160,162
0x180055861  jz      loc_180055B0E; jumptable 00000001800555BF case 161
0x180055867  mov     eax, edi
0x180055869  sub     eax, 128h
0x18005586e  jnz     loc_180055A2E
0x180055874  mov     r9, r14; lParam
0x180055877  mov     r8, rsi; wParam
0x18005587a  mov     edx, 128h; Msg
0x18005587f  mov     rcx, rbp; hWnd
0x180055882  call    cs:__imp_DefWindowProcW
0x180055888  shr     rsi, 10h
0x18005588c  test    sil, 2
0x180055890  jz      loc_18005560B; jumptable 00000001800555BF case 5
0x180055896  mov     rcx, [r15+30h]
0x18005589a  mov     edx, [rcx+0Ch]
0x18005589d  movzx   eax, dl
0x1800558a0  and     al, 1Fh
0x1800558a2  cmp     al, 2
0x1800558a4  jbe     short loc_1800558B0
0x1800558a6  sub     al, 0Bh
0x1800558a8  cmp     al, 2
0x1800558aa  ja      loc_18005560B; jumptable 00000001800555BF case 5
0x1800558b0  test    dl, dl
0x1800558b2  js      loc_18005560B; jumptable 00000001800555BF case 5
0x1800558b8  test    dword ptr [rcx+8], 40000000h
0x1800558bf  jnz     loc_18005560B; jumptable 00000001800555BF case 5
0x1800558c5  or      dword ptr [r15+20h], 2
0x1800558ca  mov     rcx, r15; lData
0x1800558cd  call    ?Repaint@CStatic@@AEAAXXZ; CStatic::Repaint(void)
0x1800558d2  and     dword ptr [r15+20h], 0FFFFFFFDh
0x1800558d7  jmp     loc_18005560B; jumptable 00000001800555BF case 5
0x1800558dc  mov     rax, [r15+30h]; jumptable 00000001800555BF case 49
0x1800558e0  movzx   ecx, byte ptr [rax+0Ch]
0x1800558e4  and     ecx, 1Fh
0x1800558e7  test    byte ptr [rcx+r12+1F06A8h], 8
0x1800558f0  jz      loc_18005560B; jumptable 00000001800555BF case 5
0x1800558f6  mov     rax, [r15+8]
0x1800558fa  jmp     loc_18005560E
0x1800558ff  xor     edx, edx; jumptable 00000001800555BF case 15
0x180055901  lea     rcx, [rsp+0E8h+Paint]; void *
0x180055906  mov     r8d, 48h ; 'H'; Size
0x18005590c  call    memset_0
0x180055911  test    rsi, rsi
0x180055914  jnz     loc_1800559DF
0x18005591a  lea     rdx, [rsp+0E8h+Paint]; lpPaint
0x18005591f  mov     rcx, rbp; hWnd
0x180055922  call    cs:__imp_BeginPaint
0x180055928  mov     rdi, rax
0x18005592b  mov     rcx, rbp; hWnd
0x18005592e  call    cs:__imp_IsWindowVisible
0x180055934  test    eax, eax
0x180055936  jnz     loc_180055AC6
0x18005593c  test    rsi, rsi
0x18005593f  jnz     loc_18005560B; jumptable 00000001800555BF case 5
0x180055945  lea     rdx, [rsp+0E8h+Paint]; lpPaint
0x18005594a  mov     rcx, rbp; hWnd
0x18005594d  call    cs:__imp_EndPaint
0x180055953  jmp     loc_18005560B; jumptable 00000001800555BF case 5
0x180055958  mov     rdx, [r14+38h]; pszName
0x18005595c  mov     rcx, r15; this
0x18005595f  call    ?LoadImageW@CStatic@@AEAAXPEBG@Z; CStatic::LoadImageW(ushort const *)
0x180055964  jmp     loc_18005560B; jumptable 00000001800555BF case 5
0x180055969  xor     eax, eax; jumptable 00000001800555BF case 61
0x18005596b  mov     ebx, 10003h
0x180055970  cmp     r14d, 0FFFFFFF4h
0x180055974  cmovnz  ebx, eax
0x180055977  jmp     loc_18005560B; jumptable 00000001800555BF case 5
0x18005597c  mov     rcx, r15; jumptable 00000001800555BF case 10
0x18005597f  call    ?Repaint@CStatic@@AEAAXXZ; CStatic::Repaint(void)
0x180055984  mov     rax, [r15+30h]
0x180055988  test    dword ptr [rax+0Ch], 100h
0x18005598f  jz      loc_18005560B; jumptable 00000001800555BF case 5
0x180055995  neg     rsi
0x180055998  sbb     r9d, r9d
0x18005599b  add     r9d, 3; int
0x18005599f  mov     rdx, rbp; HWND
0x1800559a2  call    ?NotifyParent@CStatic@@AEAA_JPEAUHWND__@@0H@Z; CStatic::NotifyParent(HWND__ *,HWND__ *,int)
0x1800559a7  jmp     loc_18005560B; jumptable 00000001800555BF case 5
0x1800559ac  mov     edx, 1Fh
0x1800559b1  mov     r8d, 2
0x1800559b7  mov     rcx, rbp; hWnd
0x1800559ba  call    AlterWindowStyle
0x1800559bf  jmp     loc_180055837
0x1800559c4  bts     r12d, 11h
0x1800559c9  mov     edx, 0FFFFFFECh; nIndex
0x1800559ce  mov     r8d, r12d; dwNewLong
0x1800559d1  mov     rcx, rbp; hWnd
0x1800559d4  call    cs:__imp_SetWindowLongW
0x1800559da  jmp     loc_180055850
0x1800559df  mov     rdi, rsi
0x1800559e2  jmp     loc_18005592B
0x1800559e7  mov     ecx, 2Dh ; '-'; nIndex
0x1800559ec  call    cs:__imp_GetSystemMetrics
0x1800559f2  mov     ecx, eax
0x1800559f4  mov     [rsp+0E8h+Rect.right], eax
0x1800559f8  mov     eax, [rsp+0E8h+Rect.bottom]
0x1800559fc  jmp     loc_180055716
0x180055a01  cmp     dl, 3
0x180055a04  jnz     loc_18005560B; jumptable 00000001800555BF case 5
0x180055a0a  cmp     dword ptr [r15+18h], 1
0x180055a0f  jle     short loc_180055A1F
0x180055a11  mov     edx, 0FFFDh; uIDEvent
0x180055a16  mov     rcx, rbp; hWnd
0x180055a19  call    cs:__imp_KillTimer
0x180055a1f  mov     rcx, [r15+10h]; hIcon
0x180055a23  call    cs:__imp_DestroyIcon
0x180055a29  jmp     loc_18005560B; jumptable 00000001800555BF case 5
0x180055a2e  sub     eax, 48h ; 'H'
0x180055a31  jz      loc_180055B01
0x180055a37  sub     eax, 1
0x180055a3a  jz      loc_180055AF7
0x180055a40  sub     eax, 1
0x180055a43  jz      short loc_180055A80
  ... truncated ...
```
