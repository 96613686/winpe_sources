# DrawThumb2(HWND__ *,tagSBCALC const *,HDC__ *,int,uint,int)

- ea: `0x180004528`
- end: `0x180004c6d`
- name: `?DrawThumb2@@YAXPEAUHWND__@@PEBUtagSBCALC@@PEAUHDC__@@HIH@Z`
- size: `1861`
- prototype: `void __usercall(HWND hWnd@<rcx>, const struct tagSBCALC *@<rdx>, HDC@<r8>, int@<r9d>, unsigned int, int)`
- caller_count: `4`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180003014`
- `0x180005464`
- `0x180005bf0`
- `0x1800e3a20`

## callees

- `0x180004498`
- `0x180004528`
- `0x180004c74`
- `0x180004c90`
- `0x180004cc4`
- `0x180004dec`
- `0x180004e58`
- `0x180004e7c`
- `0x180004e9c`
- `0x1800050fc`
- `0x180005d8c`
- `0x180114520`
- `0x18011dc70`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a08`
- `GDI32!SelectObject` at `0x1800046ec`
- `GDI32!SelectObject` at `0x18000497e`
- `GDI32!SelectObject` at `0x1800046ec`
- `GDI32!SelectObject` at `0x18000497e`
- `USER32!InvertRect` at `0x180004c19`
- `USER32!InvertRect` at `0x180004c19`
- `USER32!FillRect` at `0x180004b6a`
- `USER32!FillRect` at `0x180004baa`
- `USER32!FillRect` at `0x180004b6a`
- `USER32!FillRect` at `0x180004baa`
- `USER32!GetSysColorBrush` at `0x180004b9a`
- `USER32!GetSysColorBrush` at `0x180004b9a`
- `USER32!GetWindowThreadProcessId` at `0x180004a00`
- `USER32!GetWindowThreadProcessId` at `0x180004a00`
- `USER32!GetWindow` at `0x180004ad5`
- `USER32!GetWindow` at `0x180004ad5`
- `USER32!GetParent` at `0x1800049ca`
- `USER32!GetParent` at `0x1800049ca`
- `USER32!GetWindowLongW` at `0x1800049b9`
- `USER32!GetWindowLongW` at `0x1800049b9`
- `USER32!DefWindowProcW` at `0x1800046d7`
- `USER32!DefWindowProcW` at `0x1800049e8`
- `USER32!DefWindowProcW` at `0x1800046d7`
- `USER32!DefWindowProcW` at `0x1800049e8`
- `USER32!SendMessageW` at `0x180004a20`
- `USER32!SendMessageW` at `0x180004a20`
- `USER32!DrawEdge` at `0x180004b8f`
- `USER32!DrawEdge` at `0x180004b8f`
- `UxTheme!DrawThemeBackground` at `0x1800047cc`
- `UxTheme!DrawThemeBackground` at `0x180004896`
- `UxTheme!DrawThemeBackground` at `0x180004944`
- `UxTheme!DrawThemeBackground` at `0x180004c62`
- `UxTheme!DrawThemeBackground` at `0x1800047cc`
- `UxTheme!DrawThemeBackground` at `0x180004896`
- `UxTheme!DrawThemeBackground` at `0x180004944`
- `UxTheme!DrawThemeBackground` at `0x180004c62`
- `UxTheme!GetThemePartSize` at `0x180004905`
- `UxTheme!GetThemePartSize` at `0x180004905`
- `UxTheme!GetThemeBackgroundContentRect` at `0x1800048c3`
- `UxTheme!GetThemeBackgroundContentRect` at `0x1800048c3`

## pseudocode

```c
void __fastcall DrawThumb2(HWND hWnd, const struct tagSBCALC *a2, HDC a3, int a4, char a5, int a6)
{
  void *SBTheme; // rdx
  RECT *p_top; // rcx
  RECT *p_pBoundingRect; // r12
  LONG v13; // eax
  int v14; // eax
  struct CUxScrollBar *v15; // rax
  _DWORD *v16; // r13
  int v17; // ebx
  unsigned int v18; // eax
  bool v19; // zf
  RECT v20; // xmm0
  int v21; // ebx
  HBRUSH v22; // r13
  LONG v23; // ecx
  LONG v24; // edx
  LONG v25; // eax
  LONG *p_right; // rdi
  LONG v27; // ecx
  struct CUxScrollBar *v28; // rax
  int v29; // ebx
  int v30; // r9d
  void *v31; // r13
  BOOL v32; // r12d
  struct tagSBTRACK *SBTrack; // rdi
  struct CUxScrollBar *v34; // rax
  int v35; // ebx
  int v36; // ebx
  BOOL v37; // edi
  LONG *v38; // r12
  LONG *v39; // rdi
  struct tagSBTRACK *v40; // rax
  struct tagSBTRACK *v41; // rbx
  int v42; // eax
  HWND Window; // rax
  HWND v44; // r12
  DWORD WindowThreadProcessId; // ebx
  LRESULT v46; // rax
  struct CUxScrollBar *v47; // rax
  HBRUSH SysColorBrush; // rax
  LONG *v49; // rcx
  int v50; // r8d
  const struct tagRECT *pClipRect; // [rsp+28h] [rbp-71h]
  int ThemeThumbStateId; // [rsp+40h] [rbp-59h]
  LONG *v53; // [rsp+40h] [rbp-59h]
  RECT *v54; // [rsp+48h] [rbp-51h]
  LONG *v55; // [rsp+48h] [rbp-51h]
  HTHEME v56; // [rsp+50h] [rbp-49h]
  HGDIOBJ h; // [rsp+58h] [rbp-41h]
  SIZE iPartId; // [rsp+60h] [rbp-39h] BYREF
  RECT pBoundingRect; // [rsp+70h] [rbp-29h] BYREF
  HTHEME hTheme[2]; // [rsp+80h] [rbp-19h] BYREF
  RECT rc2; // [rsp+90h] [rbp-9h] BYREF

  if ( *((_DWORD *)a2 + 4) < *((_DWORD *)a2 + 5) && *((_DWORD *)a2 + 6) < *((_DWORD *)a2 + 7) )
  {
    h = 0;
    SBTheme = CUxScrollBar::GetSBTheme(hWnd);
    v56 = SBTheme;
    p_top = (RECT *)&pBoundingRect.top;
    if ( a4 )
      p_top = &pBoundingRect;
    p_pBoundingRect = &pBoundingRect;
    if ( a4 )
      p_pBoundingRect = (RECT *)&pBoundingRect.top;
    v13 = *((_DWORD *)a2 + 6);
    pBoundingRect = 0;
    p_top->left = v13;
    p_top->right = *((_DWORD *)a2 + 7);
    v54 = p_pBoundingRect;
    if ( (a5 & 3) == 3 || (v14 = *((_DWORD *)a2 + 10) - *((_DWORD *)a2 + 9), iPartId.cx = 1, v14 < *((_DWORD *)a2 + 8)) )
      iPartId.cx = 0;
    if ( SBTheme )
    {
      if ( !a6 )
      {
        v15 = CUxScrollBar::FromHwnd(hWnd);
        if ( v15 )
        {
          v16 = (_DWORD *)((char *)v15 + 184);
          v17 = *(_DWORD *)((char *)v15 + (-(__int64)(a4 != 0) & 0xFFFFFFFFFFFFFFF4uLL) + 356);
          ThemeThumbStateId = ScrollBar_GetThemeThumbStateId(hWnd, a4);
          v18 = ScrollBar_SoftFadeDuration(v56, (a4 != 0) + 2, v17, ThemeThumbStateId);
          v19 = iPartId.cx == 0;
          p_pBoundingRect->left = *((_DWORD *)a2 + 9);
          p_pBoundingRect->right = *((_DWORD *)a2 + 10);
          v20 = pBoundingRect;
          rc2 = pBoundingRect;
          if ( !v19 )
          {
            p_pBoundingRect->left = *((_DWORD *)a2 + 13);
            p_pBoundingRect->right = *((_DWORD *)a2 + 12);
            v20 = pBoundingRect;
          }
          *(RECT *)hTheme = v20;
          a3 = CCSoftFadeInitialize(v16, hWnd, a3, &rc2, (struct tagRECT *)hTheme, pClipRect, v18);
          if ( a4 )
            v16[40] = ThemeThumbStateId;
          else
            v16[43] = ThemeThumbStateId;
        }
      }
    }
    if ( (unsigned int)IsScrollBarControl(hWnd) )
    {
      if ( GetWindowLongW(hWnd, -16) < 0 )
        Window = GetWindow(hWnd, 4u);
      else
        Window = GetParent(hWnd);
      v44 = Window;
      if ( !Window )
        v44 = hWnd;
      v21 = 0;
      v22 = (HBRUSH)DefWindowProcW(v44, 0x137u, (WPARAM)a3, (LPARAM)hWnd);
      if ( v44 )
      {
        WindowThreadProcessId = GetWindowThreadProcessId(v44, 0);
        if ( WindowThreadProcessId == GetCurrentThreadId()
          && (v46 = SendMessageW(v44, 0x137u, (WPARAM)a3, (LPARAM)hWnd)) != 0
          && (HBRUSH)v46 != v22 )
        {
          v21 = 1;
          v22 = (HBRUSH)v46;
        }
        else
        {
          v21 = 0;
        }
      }
      p_pBoundingRect = v54;
    }
    else
    {
      v21 = 0;
      v22 = (HBRUSH)DefWindowProcW(hWnd, 0x137u, (WPARAM)a3, (LPARAM)hWnd);
    }
    if ( !a6 )
      h = SelectObject(a3, v22);
    v53 = (LONG *)((char *)a2 + 52);
    if ( iPartId.cx )
    {
      v23 = *((_DWORD *)a2 + 13);
      v24 = *((_DWORD *)a2 + 9);
      if ( v24 < v23 )
      {
        p_pBoundingRect->right = v23;
        p_pBoundingRect->left = v24;
        ScrollBar_PaintTrack(hWnd, a3, v22, &pBoundingRect, a4, a4 != 0 ? 6 : 4, v21);
      }
      v25 = *((_DWORD *)a2 + 10);
      v55 = (LONG *)((char *)a2 + 48);
      p_right = &p_pBoundingRect->right;
      v27 = *v55;
      if ( *v55 < v25 )
      {
        *p_right = v25;
        p_pBoundingRect->left = v27;
        iPartId.cx = a4 != 0 ? 7 : 5;
        hTheme[0] = CUxScrollBar::GetSBTheme(hWnd);
        if ( !hTheme[0] || v21 == 1 )
        {
          FillRect(a3, &pBoundingRect, v22);
        }
        else
        {
          v28 = CUxScrollBar::FromHwnd(hWnd);
          if ( v28 )
            v29 = *(_DWORD *)((char *)v28 + (-(__int64)(a4 != 0) & 0xFFFFFFFFFFFFFFFCuLL) + 160);
          else
            v29 = 0;
          if ( (CUxScrollBarCtl::GetDisableFlags(hWnd) & 3) == 3 )
          {
            v30 = 4;
          }
          else if ( v29 == 63 )
          {
            v30 = 2;
          }
          else
          {
            v30 = v29 != 0 ? 5 : 1;
          }
          DrawThemeBackground(hTheme[0], a3, iPartId.cx, v30, &pBoundingRect, 0);
        }
      }
      v31 = v56;
      p_pBoundingRect->left = *v53;
      *p_right = *v55;
      if ( v56 )
      {
        if ( CUxScrollBar::FromHwnd(hWnd) )
        {
          v32 = a4 != 0;
          SBTrack = CUxScrollBar::GetSBTrack(hWnd);
          v34 = CUxScrollBar::FromHwnd(hWnd);
          v35 = v34 ? *(_DWORD *)((char *)v34 + (-(__int64)(a4 != 0) & 0xFFFFFFFFFFFFFFFCuLL) + 160) : 0;
          if ( (CUxScrollBarCtl::GetDisableFlags(hWnd) & 3) == 3 )
          {
            v36 = 4;
          }
          else if ( SBTrack && ((*(_DWORD *)SBTrack >> 1) & 1) == a4 && *((_DWORD *)SBTrack + 14) == 4 )
          {
            v36 = 3;
          }
          else
          {
            v36 = v35 == 64 ? 2 : v35 != 0 ? 5 : 1;
          }
          DrawThemeBackground(v56, a3, v32 + 2, v36, &pBoundingRect, 0);
          *(_OWORD *)hTheme = 0;
          if ( GetThemeBackgroundContentRect(v56, a3, v32 + 2, v36, &pBoundingRect, (LPRECT)hTheme) >= 0 )
          {
            iPartId = 0;
            v37 = a4 != 0;
            if ( GetThemePartSize(v56, a3, v37 + 8, v36, (LPCRECT)hTheme, TS_TRUE, &iPartId) >= 0
              && iPartId.cx < LODWORD(hTheme[1]) - LODWORD(hTheme[0])
              && iPartId.cy < HIDWORD(hTheme[1]) - HIDWORD(hTheme[0]) )
            {
              DrawThemeBackground(v56, a3, v37 + 8, v36, (LPCRECT)hTheme, 0);
            }
          }
        }
      }
      else
      {
        DrawEdge(a3, &pBoundingRect, 5u, 0x200Fu);
        SysColorBrush = GetSysColorBrush(15);
        FillRect(a3, &pBoundingRect, SysColorBrush);
      }
      v38 = v53;
      v39 = v55;
    }
    else
    {
      p_pBoundingRect->left = *((_DWORD *)a2 + 9);
      p_pBoundingRect->right = *((_DWORD *)a2 + 10);
      ScrollBar_PaintTrack(hWnd, a3, v22, &pBoundingRect, a4, a4 != 0 ? 6 : 4, v21);
      v31 = v56;
      v38 = (LONG *)((char *)a2 + 52);
      v39 = (LONG *)((char *)a2 + 48);
    }
    v40 = CUxScrollBar::GetSBTrack(hWnd);
    v41 = v40;
    if ( v40 )
    {
      v42 = *((_DWORD *)v40 + 14);
      if ( (unsigned int)(v42 - 2) <= 1 && hWnd == *((HWND *)v41 + 1) && ((*(_DWORD *)v41 >> 1) & 1) == a4 )
      {
        if ( (*(_BYTE *)v41 & 8) != 0 )
        {
          RecalcTrackRect(v41);
          *(_DWORD *)v41 &= ~8u;
          v42 = *((_DWORD *)v41 + 14);
        }
        v49 = (LONG *)((char *)v41 + 36);
        if ( !a4 )
          v49 = (LONG *)((char *)v41 + 32);
        if ( v42 == 2 )
          v49[2] = *v38;
        else
          *v49 = *v39;
        if ( *v49 < v49[2] )
        {
          if ( v31 )
          {
            if ( *((_DWORD *)v41 + 14) == 2 )
              v50 = a4 != 0 ? 6 : 4;
            else
              v50 = a4 != 0 ? 7 : 5;
            DrawThemeBackground(v31, a3, v50, 3, (LPCRECT)v41 + 2, 0);
          }
          else
          {
            InvertRect(a3, (const RECT *)v41 + 2);
          }
        }
      }
    }
    if ( !a6 )
      SelectObject(a3, h);
    if ( v31 && !a6 )
    {
      v47 = CUxScrollBar::FromHwnd(hWnd);
      if ( v47 )
        CCSoftFadeStart((UINT_PTR)v47 + 184);
    }
  }
}

```

## disassembly

```asm
0x180004528  mov     [rsp-8+arg_8], rbx
0x18000452d  push    rbp
0x18000452e  push    rsi
0x18000452f  push    rdi
0x180004530  push    r12
0x180004532  push    r13
0x180004534  push    r14
0x180004536  push    r15
0x180004538  lea     rbp, [rsp-17h]
0x18000453d  sub     rsp, 0B0h
0x180004544  mov     rax, cs:__security_cookie
0x18000454b  xor     rax, rsp
0x18000454e  mov     [rbp+47h+var_40], rax
0x180004552  mov     eax, [rdx+14h]
0x180004555  mov     r14d, r9d
0x180004558  mov     r15, r8
0x18000455b  mov     rdi, rdx
0x18000455e  mov     rsi, rcx
0x180004561  cmp     [rdx+10h], eax
0x180004564  jge     loc_18000498D
0x18000456a  mov     eax, [rdx+1Ch]
0x18000456d  cmp     [rdx+18h], eax
0x180004570  jge     loc_18000498D
0x180004576  mov     [rbp+47h+h], 0
0x18000457e  call    ?GetSBTheme@CUxScrollBar@@SAPEAXPEAUHWND__@@@Z; CUxScrollBar::GetSBTheme(HWND__ *)
0x180004583  mov     rdx, rax
0x180004586  mov     [rbp+47h+var_90], rax
0x18000458a  test    r14d, r14d
0x18000458d  lea     rax, [rbp+47h+pBoundingRect]
0x180004591  lea     rcx, [rbp+47h+pBoundingRect.top]
0x180004595  xorps   xmm0, xmm0
0x180004598  cmovnz  rcx, rax
0x18000459c  lea     r12, [rbp+47h+pBoundingRect]
0x1800045a0  lea     rax, [rbp+47h+pBoundingRect.top]
0x1800045a4  cmovnz  r12, rax
0x1800045a8  mov     eax, [rdi+18h]
0x1800045ab  movups  xmmword ptr [rbp+47h+pBoundingRect.left], xmm0
0x1800045af  mov     [rcx], eax
0x1800045b1  mov     eax, [rdi+1Ch]
0x1800045b4  mov     [rcx+8], eax
0x1800045b7  mov     eax, dword ptr [rbp+47h+arg_20]
0x1800045ba  and     eax, 3
0x1800045bd  mov     [rbp+47h+var_98], r12
0x1800045c1  cmp     al, 3
0x1800045c3  jnz     short loc_1800045CE
0x1800045c5  mov     [rbp+47h+iPartId.cx], 0
0x1800045cc  jmp     short loc_1800045E0
0x1800045ce  mov     eax, [rdi+28h]
0x1800045d1  sub     eax, [rdi+24h]
0x1800045d4  mov     [rbp+47h+iPartId.cx], 1
0x1800045db  cmp     eax, [rdi+20h]
0x1800045de  jl      short loc_1800045C5
0x1800045e0  test    rdx, rdx
0x1800045e3  jz      loc_1800046B7
0x1800045e9  cmp     [rbp+47h+arg_28], 0
0x1800045ed  jnz     loc_1800046B7
0x1800045f3  mov     rcx, rsi; HWND
0x1800045f6  call    ?FromHwnd@CUxScrollBar@@SAPEAV1@PEAUHWND__@@@Z; CUxScrollBar::FromHwnd(HWND__ *)
0x1800045fb  test    rax, rax
0x1800045fe  jz      loc_1800046B7
0x180004604  lea     r13, [rax+0B8h]
0x18000460b  mov     edx, r14d; int
0x18000460e  mov     eax, r14d
0x180004611  neg     eax
0x180004613  sbb     rcx, rcx
0x180004616  and     rcx, 0FFFFFFFFFFFFFFF4h
0x18000461a  mov     ebx, [rcx+r13+0ACh]
0x180004622  mov     rcx, rsi; HWND
0x180004625  call    ?ScrollBar_GetThemeThumbStateId@@YAHPEAUHWND__@@H@Z; ScrollBar_GetThemeThumbStateId(HWND__ *,int)
0x18000462a  mov     ecx, eax
0x18000462c  mov     dword ptr [rbp+47h+var_A0], eax
0x18000462f  mov     eax, r14d
0x180004632  mov     r9d, ecx; int
0x180004635  mov     rcx, [rbp+47h+var_90]; hTheme
0x180004639  neg     eax
0x18000463b  mov     r8d, ebx; int
0x18000463e  sbb     edx, edx
0x180004640  neg     edx
0x180004642  add     edx, 2; iPartId
0x180004645  call    ?ScrollBar_SoftFadeDuration@@YAKPEAXHHH@Z; ScrollBar_SoftFadeDuration(void *,int,int,int)
0x18000464a  cmp     [rbp+47h+iPartId.cx], 0
0x18000464e  mov     ecx, eax
0x180004650  mov     eax, [rdi+24h]
0x180004653  mov     [r12], eax
0x180004657  mov     eax, [rdi+28h]
0x18000465a  mov     [r12+8], eax
0x18000465f  movaps  xmm0, xmmword ptr [rbp+47h+pBoundingRect.left]
0x180004663  movdqa  xmmword ptr [rbp+47h+rc2.left], xmm0
0x180004668  jz      short loc_18000467D
0x18000466a  mov     eax, [rdi+34h]
0x18000466d  mov     [r12], eax
0x180004671  mov     eax, [rdi+30h]
0x180004674  mov     [r12+8], eax
0x180004679  movaps  xmm0, xmmword ptr [rbp+47h+pBoundingRect.left]
0x18000467d  mov     dword ptr [rsp+0E0h+psz], ecx; unsigned int
0x180004681  lea     rax, [rbp+47h+hTheme]
0x180004685  mov     rcx, r13; uIDEvent
0x180004688  mov     [rsp+0E0h+pRect], rax; struct tagRECT *
0x18000468d  lea     r9, [rbp+47h+rc2]; lprc2
0x180004691  movdqa  xmmword ptr [rbp+47h+hTheme], xmm0
0x180004696  mov     r8, r15; hdc
0x180004699  mov     rdx, rsi; hWnd
0x18000469c  call    ?CCSoftFadeInitialize@@YAPEAUHDC__@@PEAUtagCCSOFTFADE@@PEAUHWND__@@PEAU1@PEBUtagRECT@@33K@Z; CCSoftFadeInitialize(tagCCSOFTFADE *,HWND__ *,HDC__ *,tagRECT const *,tagRECT const *,tagRECT const *,ulong)
0x1800046a1  mov     r15, rax
0x1800046a4  mov     eax, dword ptr [rbp+47h+var_A0]
0x1800046a7  test    r14d, r14d
0x1800046aa  jz      loc_180004ABA
0x1800046b0  mov     [r13+0A0h], eax
0x1800046b7  mov     rcx, rsi; HWND
0x1800046ba  call    ?IsScrollBarControl@@YAHPEAUHWND__@@@Z; IsScrollBarControl(HWND__ *)
0x1800046bf  mov     rcx, rsi; hWnd
0x1800046c2  test    eax, eax
0x1800046c4  jnz     loc_1800049B4
0x1800046ca  xor     ebx, ebx
0x1800046cc  mov     r9, rsi; lParam
0x1800046cf  mov     r8, r15; wParam
0x1800046d2  mov     edx, 137h; Msg
0x1800046d7  call    cs:__imp_DefWindowProcW
0x1800046dd  mov     r13, rax
0x1800046e0  cmp     [rbp+47h+arg_28], 0
0x1800046e4  jnz     short loc_1800046F6
0x1800046e6  mov     rdx, r13; h
0x1800046e9  mov     rcx, r15; hdc
0x1800046ec  call    cs:__imp_SelectObject
0x1800046f2  mov     [rbp+47h+h], rax
0x1800046f6  cmp     [rbp+47h+iPartId.cx], 0
0x1800046fa  lea     rax, [rdi+34h]
0x1800046fe  mov     [rbp+47h+var_A0], rax
0x180004702  jz      loc_180004AE0
0x180004708  mov     ecx, [rax]
0x18000470a  mov     edx, [rdi+24h]
0x18000470d  cmp     edx, ecx
0x18000470f  jl      loc_180004A40
0x180004715  mov     eax, [rdi+28h]
0x180004718  lea     rcx, [rdi+30h]
0x18000471c  mov     [rbp+47h+var_98], rcx
0x180004720  lea     rdi, [r12+8]
0x180004725  mov     ecx, [rcx]
0x180004727  cmp     ecx, eax
0x180004729  jge     loc_1800047D2
0x18000472f  mov     [rdi], eax
0x180004731  mov     eax, r14d
0x180004734  neg     eax
0x180004736  mov     [r12], ecx
0x18000473a  mov     rcx, rsi; HWND
0x18000473d  sbb     eax, eax
0x18000473f  and     eax, 2
0x180004742  add     eax, 5
0x180004745  mov     [rbp+47h+iPartId.cx], eax
0x180004748  call    ?GetSBTheme@CUxScrollBar@@SAPEAXPEAUHWND__@@@Z; CUxScrollBar::GetSBTheme(HWND__ *)
0x18000474d  mov     [rbp+47h+hTheme], rax
0x180004751  test    rax, rax
0x180004754  jz      loc_180004B60
0x18000475a  cmp     ebx, 1
0x18000475d  jz      loc_180004B60
0x180004763  mov     rcx, rsi; HWND
0x180004766  call    ?FromHwnd@CUxScrollBar@@SAPEAV1@PEAUHWND__@@@Z; CUxScrollBar::FromHwnd(HWND__ *)
0x18000476b  test    rax, rax
0x18000476e  jz      loc_180004B4E
0x180004774  mov     ecx, r14d
0x180004777  neg     ecx
0x180004779  sbb     rdx, rdx
0x18000477c  and     rdx, 0FFFFFFFFFFFFFFFCh
0x180004780  mov     ebx, [rdx+rax+0A0h]
0x180004787  mov     rcx, rsi; HWND
0x18000478a  call    ?GetDisableFlags@CUxScrollBarCtl@@SAIPEAUHWND__@@@Z; CUxScrollBarCtl::GetDisableFlags(HWND__ *)
0x18000478f  and     eax, 3
0x180004792  cmp     al, 3
0x180004794  jz      loc_180004B36
0x18000479a  cmp     ebx, 3Fh ; '?'
0x18000479d  jz      loc_180004B55
0x1800047a3  neg     ebx
0x1800047a5  sbb     r9d, r9d
0x1800047a8  and     r9d, 4
0x1800047ac  inc     r9d; iStateId
0x1800047af  mov     r8d, [rbp+47h+iPartId.cx]; iPartId
0x1800047b3  lea     rax, [rbp+47h+pBoundingRect]
0x1800047b7  mov     rcx, [rbp+47h+hTheme]; hTheme
0x1800047bb  mov     rdx, r15; hdc
0x1800047be  mov     [rsp+0E0h+pClipRect], 0; pClipRect
0x1800047c7  mov     [rsp+0E0h+pRect], rax; pRect
0x1800047cc  call    cs:__imp_DrawThemeBackground
0x1800047d2  mov     rax, [rbp+47h+var_A0]
0x1800047d6  mov     r13, [rbp+47h+var_90]
0x1800047da  mov     eax, [rax]
0x1800047dc  mov     [r12], eax
0x1800047e0  mov     rax, [rbp+47h+var_98]
0x1800047e4  mov     eax, [rax]
0x1800047e6  mov     [rdi], eax
0x1800047e8  test    r13, r13
0x1800047eb  jz      loc_180004B7C
0x1800047f1  mov     rcx, rsi; HWND
0x1800047f4  call    ?FromHwnd@CUxScrollBar@@SAPEAV1@PEAUHWND__@@@Z; CUxScrollBar::FromHwnd(HWND__ *)
0x1800047f9  test    rax, rax
0x1800047fc  jz      loc_18000494A
0x180004802  mov     eax, r14d
0x180004805  mov     rcx, rsi; HWND
0x180004808  neg     eax
0x18000480a  sbb     r12d, r12d
0x18000480d  neg     r12d
0x180004810  call    ?GetSBTrack@CUxScrollBar@@SAPEAUtagSBTRACK@@PEAUHWND__@@@Z; CUxScrollBar::GetSBTrack(HWND__ *)
0x180004815  mov     rcx, rsi; HWND
0x180004818  mov     rdi, rax
0x18000481b  call    ?FromHwnd@CUxScrollBar@@SAPEAV1@PEAUHWND__@@@Z; CUxScrollBar::FromHwnd(HWND__ *)
0x180004820  test    rax, rax
0x180004823  jz      loc_180004B75
0x180004829  mov     ecx, r14d
0x18000482c  neg     ecx
0x18000482e  sbb     rdx, rdx
0x180004831  and     rdx, 0FFFFFFFFFFFFFFFCh
0x180004835  mov     ebx, [rdx+rax+0A0h]
0x18000483c  mov     rcx, rsi; HWND
0x18000483f  call    ?GetDisableFlags@CUxScrollBarCtl@@SAIPEAUHWND__@@@Z; CUxScrollBarCtl::GetDisableFlags(HWND__ *)
0x180004844  and     eax, 3
0x180004847  cmp     al, 3
0x180004849  jz      loc_180004B2C
0x18000484f  test    rdi, rdi
0x180004852  jz      short loc_180004864
0x180004854  mov     eax, [rdi]
0x180004856  shr     eax, 1
0x180004858  and     eax, 1
0x18000485b  cmp     eax, r14d
0x18000485e  jz      loc_180004AA6
0x180004864  cmp     ebx, 40h ; '@'
0x180004867  jz      loc_180004AC6
0x18000486d  neg     ebx
0x18000486f  sbb     ebx, ebx
0x180004871  and     ebx, 4
0x180004874  inc     ebx
0x180004876  lea     rax, [rbp+47h+pBoundingRect]
0x18000487a  mov     [rsp+0E0h+pClipRect], 0; pClipRect
0x180004883  mov     r9d, ebx; iStateId
0x180004886  mov     [rsp+0E0h+pRect], rax; pRect
0x18000488b  lea     r8d, [r12+2]; iPartId
0x180004890  mov     rdx, r15; hdc
0x180004893  mov     rcx, r13; hTheme
0x180004896  call    cs:__imp_DrawThemeBackground
0x18000489c  lea     rax, [rbp+47h+hTheme]
0x1800048a0  xorps   xmm0, xmm0
0x1800048a3  mov     [rsp+0E0h+pClipRect], rax; pContentRect
0x1800048a8  lea     r8d, [r12+2]; iPartId
0x1800048ad  lea     rax, [rbp+47h+pBoundingRect]
0x1800048b1  mov     r9d, ebx; iStateId
0x1800048b4  mov     rdx, r15; hdc
0x1800048b7  mov     [rsp+0E0h+pRect], rax; pBoundingRect
0x1800048bc  mov     rcx, r13; hTheme
0x1800048bf  movups  xmmword ptr [rbp+47h+hTheme], xmm0
0x1800048c3  call    cs:__imp_GetThemeBackgroundContentRect
0x1800048c9  test    eax, eax
0x1800048cb  js      short loc_18000494A
0x1800048cd  mov     eax, r14d
0x1800048d0  mov     qword ptr [rbp+47h+iPartId.cx], 0
0x1800048d8  neg     eax
0x1800048da  mov     r9d, ebx; iStateId
0x1800048dd  lea     rax, [rbp+47h+iPartId]
0x1800048e1  mov     rdx, r15; hdc
0x1800048e4  mov     [rsp+0E0h+psz], rax; psz
0x1800048e9  sbb     edi, edi
0x1800048eb  lea     rax, [rbp+47h+hTheme]
0x1800048ef  mov     dword ptr [rsp+0E0h+pClipRect], 1; eSize
0x1800048f7  neg     edi
0x1800048f9  mov     [rsp+0E0h+pRect], rax; prc
0x1800048fe  mov     rcx, r13; hTheme
0x180004901  lea     r8d, [rdi+8]; iPartId
0x180004905  call    cs:__imp_GetThemePartSize
0x18000490b  test    eax, eax
0x18000490d  js      short loc_18000494A
0x18000490f  mov     eax, dword ptr [rbp+47h+hTheme+8]
0x180004912  sub     eax, dword ptr [rbp+47h+hTheme]
0x180004915  cmp     [rbp+47h+iPartId.cx], eax
0x180004918  jge     short loc_18000494A
0x18000491a  mov     eax, dword ptr [rbp+47h+hTheme+0Ch]
0x18000491d  sub     eax, dword ptr [rbp+47h+hTheme+4]
0x180004920  cmp     [rbp+47h+iPartId.cy], eax
0x180004923  jge     short loc_18000494A
0x180004925  lea     rax, [rbp+47h+hTheme]
0x180004929  mov     [rsp+0E0h+pClipRect], 0; pClipRect
0x180004932  mov     r9d, ebx; iStateId
0x180004935  mov     [rsp+0E0h+pRect], rax; pRect
0x18000493a  lea     r8d, [rdi+8]; iPartId
0x18000493e  mov     rdx, r15; hdc
0x180004941  mov     rcx, r13; hTheme
0x180004944  call    cs:__imp_DrawThemeBackground
0x18000494a  mov     r12, [rbp+47h+var_A0]
0x18000494e  mov     rdi, [rbp+47h+var_98]
0x180004952  mov     rcx, rsi; HWND
0x180004955  call    ?GetSBTrack@CUxScrollBar@@SAPEAUtagSBTRACK@@PEAUHWND__@@@Z; CUxScrollBar::GetSBTrack(HWND__ *)
0x18000495a  mov     rbx, rax
0x18000495d  test    rax, rax
0x180004960  jz      short loc_180004971
0x180004962  mov     eax, [rax+38h]
0x180004965  lea     ecx, [rax-2]
0x180004968  cmp     ecx, 1
0x18000496b  jbe     loc_180004BB5
0x180004971  cmp     [rbp+47h+arg_28], 0
0x180004975  jnz     short loc_180004984
0x180004977  mov     rdx, [rbp+47h+h]; h
0x18000497b  mov     rcx, r15; hdc
0x18000497e  call    cs:__imp_SelectObject
0x180004984  test    r13, r13
  ... truncated ...
```
