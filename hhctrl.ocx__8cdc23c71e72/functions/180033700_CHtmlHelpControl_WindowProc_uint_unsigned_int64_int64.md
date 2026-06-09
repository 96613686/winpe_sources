# CHtmlHelpControl::WindowProc(uint,unsigned __int64,__int64)

- ea: `0x180033700`
- end: `0x180033e46`
- name: `?WindowProc@CHtmlHelpControl@@EEAA_JI_K_J@Z`
- size: `1862`
- prototype: `__int64 __fastcall(CHtmlHelpControl *__hidden this, UINT Msg, unsigned int, struct tagNMTREEVIEWA *)`
- caller_count: `0`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003fc0`
- `0x180004224`
- `0x180006708`
- `0x18000f460`
- `0x180012934`
- `0x18001acc0`
- `0x18001bc88`
- `0x18002018c`
- `0x18002e344`
- `0x18002f580`
- `0x180033700`
- `0x18003a9e0`
- `0x180045d7c`
- `0x1800464f0`
- `0x180064acc`
- `0x1800675c0`
- `0x180075c90`
- `0x180078010`

## import_xrefs

- `msvcrt!free` at `0x180033d41`
- `msvcrt!free` at `0x180033d41`
- `USER32!GetWindow` at `0x180033ada`
- `USER32!GetWindow` at `0x180033ada`
- `USER32!TrackPopupMenu` at `0x1800338cb`
- `USER32!TrackPopupMenu` at `0x1800338cb`
- `USER32!FillRect` at `0x180033a2a`
- `USER32!FillRect` at `0x180033a2a`
- `USER32!MapWindowPoints` at `0x180033a6d`
- `USER32!MapWindowPoints` at `0x180033a6d`
- `USER32!MessageBoxA` at `0x180033cd2`
- `USER32!MessageBoxA` at `0x180033d18`
- `USER32!MessageBoxA` at `0x180033cd2`
- `USER32!MessageBoxA` at `0x180033d18`
- `USER32!GetSysColor` at `0x180033d7c`
- `USER32!GetSysColor` at `0x180033d91`
- `USER32!GetSysColor` at `0x180033d7c`
- `USER32!GetSysColor` at `0x180033d91`
- `USER32!DefWindowProcA` at `0x180033e1d`
- `USER32!DefWindowProcA` at `0x180033e1d`
- `USER32!CreatePopupMenu` at `0x1800337cb`
- `USER32!CreatePopupMenu` at `0x1800337cb`
- `USER32!SetFocus` at `0x180033ae8`
- `USER32!SetFocus` at `0x180033ae8`
- `USER32!GetWindowRect` at `0x180033982`
- `USER32!GetWindowRect` at `0x180033982`
- `USER32!InvalidateRect` at `0x1800339b3`
- `USER32!InvalidateRect` at `0x1800339b3`
- `USER32!SendMessageA` at `0x180033a96`
- `USER32!SendMessageA` at `0x180033b5a`
- `USER32!SendMessageA` at `0x180033a96`
- `USER32!SendMessageA` at `0x180033b5a`
- `USER32!GetParent` at `0x1800337b5`
- `USER32!GetParent` at `0x180033a41`
- `USER32!GetParent` at `0x180033cb7`
- `USER32!GetParent` at `0x180033cff`
- `USER32!GetParent` at `0x1800337b5`
- `USER32!GetParent` at `0x180033a41`
- `USER32!GetParent` at `0x180033cb7`
- `USER32!GetParent` at `0x180033cff`
- `USER32!GetCursorPos` at `0x18003389d`
- `USER32!GetCursorPos` at `0x18003389d`
- `GDI32!SetBkColor` at `0x180033d71`
- `GDI32!SetBkColor` at `0x180033d71`
- `GDI32!GetClipBox` at `0x180033a15`
- `GDI32!GetClipBox` at `0x180033a15`
- `GDI32!SetTextColor` at `0x180033db2`
- `GDI32!SetTextColor` at `0x180033db2`
- `GDI32!SetWindowOrgEx` at `0x180033aae`
- `GDI32!SetWindowOrgEx` at `0x180033aae`
- `GDI32!OffsetWindowOrgEx` at `0x180033a84`
- `GDI32!OffsetWindowOrgEx` at `0x180033a84`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LRESULT __fastcall CHtmlHelpControl::WindowProc(CHtmlHelpControl *this, UINT Msg, HDC a3, struct tagNMTREEVIEWA *a4)
{
  HWND v8; // rax
  HMENU PopupMenu; // r15
  int i; // r13d
  unsigned int v11; // edx
  const char *v12; // rax
  unsigned int v13; // edx
  __int64 v14; // rcx
  LRESULT result; // rax
  int v16; // eax
  CToc *v17; // rcx
  __int64 v18; // rax
  HWND v19; // rax
  HWND v20; // r15
  LRESULT v21; // r15
  HWND Window; // rax
  __int64 v23; // rcx
  void (*v24)(void); // rax
  WPARAM v25; // r8
  CHtmlHelpControl *v26; // rcx
  __int64 v27; // rcx
  const char *v28; // rax
  HWND v29; // rax
  const CHAR *StringResource; // rbx
  HWND Parent; // rax
  COLORREF SysColor; // edx
  DWORD v33; // eax
  int v34; // ecx
  __int64 v35; // rcx
  struct tagPOINT Points; // [rsp+40h] [rbp-C0h] BYREF
  struct tagPOINT Point[2]; // [rsp+48h] [rbp-B8h] BYREF
  struct tagRECT Rect; // [rsp+58h] [rbp-A8h] BYREF
  CHAR Text[512]; // [rsp+70h] [rbp-90h] BYREF

  if ( Msg > 0x111 )
  {
    if ( Msg == 307 )
    {
      if ( !*((_QWORD *)this + 52) )
        goto LABEL_19;
      v35 = *((_QWORD *)this + 75);
      if ( !v35 || !(unsigned int)IsValidWindow(*(HWND *)(v35 + 424)) )
        goto LABEL_19;
    }
    else
    {
      if ( Msg == 309 )
      {
        result = *((_QWORD *)this + 52);
        if ( !result || *((struct tagNMTREEVIEWA **)this + 57) == a4 )
          goto LABEL_19;
        return result;
      }
      if ( Msg != 312 )
      {
        if ( Msg == 1553 )
        {
          AuthorMsg((unsigned int)a3, (char *)a4);
        }
        else
        {
          if ( Msg != 1554 )
            goto LABEL_19;
          if ( !a4 )
          {
            COleControl::ModalDialog(this, 1);
            StringResource = GetStringResource((UINT)a3);
            Parent = GetParent(*((HWND *)this + 28));
            MessageBoxA(Parent, StringResource, Class, 0x10u);
            COleControl::ModalDialog(this, 0);
            return 0;
          }
          v28 = GetStringResource((UINT)a3);
          if ( (int)StringCchPrintfA(Text, 0x200u, v28, a4) < 0 )
            Text[0] = 0;
          COleControl::ModalDialog(this, 1);
          v29 = GetParent(*((HWND *)this + 28));
          MessageBoxA(v29, Text, Class, 0x10u);
          COleControl::ModalDialog(this, 0);
        }
        free(a4);
        return 0;
      }
      if ( !*((_QWORD *)this + 52) )
      {
LABEL_19:
        v14 = *((_QWORD *)this + 30);
        if ( !v14 )
          return DefWindowProcA(*((HWND *)this + 28), Msg, (WPARAM)a3, (LPARAM)a4);
        Point[0] = 0;
        (*(void (__fastcall **)(__int64, _QWORD, HDC, struct tagNMTREEVIEWA *, struct tagPOINT *))(*(_QWORD *)v14 + 232LL))(
          v14,
          Msg,
          a3,
          a4,
          Point);
        return (LRESULT)Point[0];
      }
      if ( *((_DWORD *)this + 90) == 3 )
      {
        SetBkColor(a3, *((_DWORD *)this + 169));
        SysColor = GetSysColor(18);
        if ( SysColor == *((_DWORD *)this + 169) )
        {
          v33 = GetSysColor(8);
          v34 = *((_DWORD *)this + 169);
          SysColor = 0;
          if ( v33 != v34 )
            SysColor = v33;
          if ( SysColor == v34 )
            SysColor = 0xFFFFFF;
        }
        SetTextColor(a3, SysColor);
      }
    }
    return *((_QWORD *)this + 52);
  }
  switch ( Msg )
  {
    case 0x111u:
      if ( !WORD1(a3) || WORD1(a3) == 5 )
      {
        if ( *((_DWORD *)this + 140) && (unsigned __int16)a3 < 0xEFFEu )
        {
          if ( (unsigned int)CHtmlHelpControl::CheckSrcUrlSafety(this) )
            return 0;
          v26 = this;
          if ( (unsigned __int16)((_WORD)a3 + 0x2000) > 0x64u )
          {
            v24 = *(void (**)(void))(*(_QWORD *)this + 224LL);
            goto LABEL_62;
          }
LABEL_60:
          CHtmlHelpControl::OnRelatedCommand(v26, (unsigned __int16)a3);
          return 0;
        }
      }
      else
      {
        if ( WORD1(a3) == 6 )
        {
          v25 = 16385;
          goto LABEL_55;
        }
        if ( WORD1(a3) == 7 )
        {
          v25 = 0x4000;
LABEL_55:
          SendMessageA((HWND)a4, 0xF4u, v25, 1);
          return 0;
        }
      }
      if ( *((_DWORD *)this + 90) == 2 )
      {
        if ( (unsigned int)CHtmlHelpControl::CheckSrcUrlSafety(this) )
          return 0;
        v27 = *((_QWORD *)this + 75);
      }
      else
      {
        if ( *((_DWORD *)this + 90) != 3 )
        {
          if ( *((_DWORD *)this + 90) != 4 && (unsigned int)(*((_DWORD *)this + 90) - 16) > 1 )
            goto LABEL_19;
          if ( (unsigned int)CHtmlHelpControl::CheckSrcUrlSafety(this) )
            return 0;
          v26 = this;
          goto LABEL_60;
        }
        if ( (unsigned int)CHtmlHelpControl::CheckSrcUrlSafety(this) )
          return 0;
        v27 = *((_QWORD *)this + 76);
      }
      return (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, struct tagNMTREEVIEWA *))(*(_QWORD *)v27 + 16LL))(
               v27,
               *((_QWORD *)this + 28),
               (unsigned __int16)a3,
               WORD1(a3),
               a4);
    case 7u:
      if ( *((_DWORD *)this + 140) )
      {
        Window = GetWindow(*((HWND *)this + 28), 5u);
        if ( Window )
        {
          SetFocus(Window);
          return 0;
        }
      }
      if ( *((_DWORD *)this + 90) != 3 )
        goto LABEL_19;
      v23 = *((_QWORD *)this + 76);
      if ( !v23 )
        goto LABEL_19;
      v24 = *(void (**)(void))(*(_QWORD *)v23 + 64LL);
LABEL_62:
      v24();
      return 0;
    case 0x14u:
      if ( *((_DWORD *)this + 90) == 3 && *((_QWORD *)this + 52) )
      {
        *(_OWORD *)&Point[0].x = 0;
        GetClipBox(a3, (LPRECT)Point);
        FillRect(a3, (const RECT *)Point, *((HBRUSH *)this + 52));
        return 1;
      }
      v19 = GetParent(*((HWND *)this + 28));
      v20 = v19;
      if ( v19 )
      {
        Points = 0;
        MapWindowPoints(*((HWND *)this + 28), v19, &Points, 1u);
        OffsetWindowOrgEx(a3, Points.x, Points.y, &Points);
        v21 = SendMessageA(v20, 0x14u, (WPARAM)a3, (LPARAM)a4);
        SetWindowOrgEx(a3, Points.x, Points.y, 0);
        if ( v21 )
          return v21;
      }
      goto LABEL_19;
    case 0x2Bu:
      if ( *((_DWORD *)this + 91) == 2 )
      {
        CHtmlHelpControl::OnDrawStaticText(this, (struct tagDRAWITEMSTRUCT *)a4);
      }
      else if ( *((_DWORD *)this + 90) == 3 )
      {
        return 0;
      }
      goto LABEL_19;
    case 0x46u:
      Rect = 0;
      GetWindowRect(*((HWND *)this + 28), &Rect);
      v18 = *((_QWORD *)this + 153) - *(_QWORD *)&Rect.left;
      if ( !v18 )
        v18 = *((_QWORD *)this + 154) - *(_QWORD *)&Rect.right;
      if ( v18 )
        InvalidateRect(*((HWND *)this + 28), 0, 20);
      *(struct tagRECT *)((char *)this + 1224) = Rect;
      goto LABEL_19;
  }
  if ( Msg != 78 )
  {
    if ( Msg == 123 && (unsigned int)(*((_DWORD *)this + 90) - 3) <= 1 )
    {
      if ( !(unsigned int)CHtmlHelpControl::CheckSrcUrlSafety(this) )
      {
        v8 = GetParent(*((HWND *)this + 28));
        if ( (unsigned int)IsHelpAuthor(v8) )
        {
          PopupMenu = CreatePopupMenu();
          if ( PopupMenu )
          {
            if ( *((_DWORD *)this + 90) == 4 )
            {
              Points = 0;
              for ( i = 1; i <= *(_DWORD *)(*((_QWORD *)this + 67) + 32LL) - 1; ++i )
              {
                GetStringResource(0x410u);
                CStr::operator=(&Points);
                CStr::operator+=(
                  &Points,
                  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 67) + 16LL) + 8LL * i) + 8LL));
                HxAppendMenu(PopupMenu, v11, i + 61438, *(const char **)&Points);
              }
              CWStr::~CWStr((CWStr *)&Points);
            }
            else
            {
              v12 = (const char *)((__int64 (__fastcall *)(__int64))pGetDllStringResource)(120584);
              HxAppendMenu(PopupMenu, v13, 0xEFFEu, v12);
            }
            Point[0] = 0;
            GetCursorPos(Point);
            TrackPopupMenu(PopupMenu, 2u, Point[0].x, Point[0].y, 0, *((HWND *)this + 28), 0);
          }
        }
        goto LABEL_19;
      }
      return 0;
    }
    goto LABEL_19;
  }
  v16 = *((_DWORD *)this + 90);
  if ( v16 != 2 )
  {
    if ( v16 == 3 )
    {
      if ( a3 == (HDC)222 )
        (*(void (__fastcall **)(_QWORD, struct tagNMTREEVIEWA *))(**((_QWORD **)this + 76) + 104LL))(
          *((_QWORD *)this + 76),
          a4);
      return 0;
    }
    goto LABEL_19;
  }
  v17 = (CToc *)*((_QWORD *)this + 75);
  if ( *((_DWORD *)v17 + 2) )
    return CToc::OnBinaryTOCTVMsg(v17, (struct tagNMTVCUSTOMDRAW *)a4);
  else
    return CToc::OnSiteMapTVMsg(v17, (struct tagNMTVCUSTOMDRAW *)a4);
}

```

## disassembly

```asm
0x180033700  push    rbp
0x180033702  push    rbx
0x180033703  push    rsi
0x180033704  push    rdi
0x180033705  push    r12
0x180033707  push    r13
0x180033709  push    r14
0x18003370b  push    r15
0x18003370d  lea     rbp, [rsp-188h]
0x180033715  sub     rsp, 288h
0x18003371c  mov     rax, cs:__security_cookie
0x180033723  xor     rax, rsp
0x180033726  mov     [rbp+1C0h+var_50], rax
0x18003372d  mov     rsi, r9
0x180033730  mov     rbx, r8
0x180033733  mov     r14d, edx
0x180033736  mov     rdi, rcx
0x180033739  xor     r12d, r12d
0x18003373c  mov     eax, 111h
0x180033741  cmp     edx, eax
0x180033743  ja      loc_180033C45
0x180033749  jz      loc_180033B1C
0x18003374f  cmp     edx, 7
0x180033752  jz      loc_180033AC5
0x180033758  lea     r13d, [r12+14h]
0x18003375d  cmp     edx, r13d
0x180033760  jz      loc_1800339F3
0x180033766  cmp     edx, 2Bh ; '+'
0x180033769  jz      loc_1800339CB
0x18003376f  cmp     edx, 46h ; 'F'
0x180033772  jz      loc_18003396E
0x180033778  cmp     edx, 4Eh ; 'N'
0x18003377b  jz      loc_180033912
0x180033781  cmp     edx, 7Bh ; '{'
0x180033784  jnz     loc_1800338D1
0x18003378a  mov     ecx, [rcx+168h]
0x180033790  sub     ecx, 3
0x180033793  jz      short loc_18003379E
0x180033795  cmp     ecx, 1
0x180033798  jnz     loc_1800338D1
0x18003379e  mov     rcx, rdi; this
0x1800337a1  call    ?CheckSrcUrlSafety@CHtmlHelpControl@@QEAAJXZ; CHtmlHelpControl::CheckSrcUrlSafety(void)
0x1800337a6  test    eax, eax
0x1800337a8  jnz     loc_180033D47
0x1800337ae  mov     rcx, [rdi+0E0h]; hWnd
0x1800337b5  call    cs:__imp_GetParent
0x1800337bb  mov     rcx, rax; HWND
0x1800337be  call    ?IsHelpAuthor@@YAHPEAUHWND__@@@Z; IsHelpAuthor(HWND__ *)
0x1800337c3  test    eax, eax
0x1800337c5  jz      loc_1800338D1
0x1800337cb  call    cs:__imp_CreatePopupMenu
0x1800337d1  mov     r15, rax
0x1800337d4  test    rax, rax
0x1800337d7  jz      loc_1800338D1
0x1800337dd  cmp     dword ptr [rdi+168h], 4
0x1800337e4  jnz     loc_180033871
0x1800337ea  mov     qword ptr [rsp+2C0h+Points.x], r12
0x1800337ef  mov     r13d, 1
0x1800337f5  mov     rax, [rdi+218h]
0x1800337fc  mov     ecx, [rax+20h]
0x1800337ff  dec     ecx
0x180033801  cmp     ecx, r13d
0x180033804  jl      short loc_180033865
0x180033806  mov     ecx, 410h; uID
0x18003380b  call    ?GetStringResource@@YAPEBDH@Z; GetStringResource(int)
0x180033810  mov     rdx, rax
0x180033813  lea     rcx, [rsp+2C0h+Points]
0x180033818  call    ??4CStr@@QEAAXPEBD@Z; CStr::operator=(char const *)
0x18003381d  movsxd  rdx, r13d
0x180033820  mov     rax, [rdi+218h]
0x180033827  mov     rcx, [rax+10h]
0x18003382b  mov     rdx, [rcx+rdx*8]
0x18003382f  mov     rdx, [rdx+8]
0x180033833  lea     rcx, [rsp+2C0h+Points]
0x180033838  call    ??YCStr@@QEAAXPEBD@Z; CStr::operator+=(char const *)
0x18003383d  lea     r8d, [r13+0EFFEh]; unsigned int
0x180033844  mov     r9, qword ptr [rsp+2C0h+Points.x]; char *
0x180033849  mov     rcx, r15; hMenu
0x18003384c  call    ?HxAppendMenu@@YAHPEAUHMENU__@@IIPEBD@Z; HxAppendMenu(HMENU__ *,uint,uint,char const *)
0x180033851  inc     r13d
0x180033854  mov     rax, [rdi+218h]
0x18003385b  mov     ecx, [rax+20h]
0x18003385e  dec     ecx
0x180033860  cmp     r13d, ecx
0x180033863  jle     short loc_180033806
0x180033865  lea     rcx, [rsp+2C0h+Points]; this
0x18003386a  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x18003386f  jmp     short loc_180033893
0x180033871  mov     ecx, 1D708h
0x180033876  mov     rax, cs:?pGetDllStringResource@@3P6APEBDH@ZEA; char const * (*pGetDllStringResource)(int)
0x18003387d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033882  mov     r9, rax; char *
0x180033885  mov     r8d, 0EFFEh; unsigned int
0x18003388b  mov     rcx, r15; hMenu
0x18003388e  call    ?HxAppendMenu@@YAHPEAUHMENU__@@IIPEBD@Z; HxAppendMenu(HMENU__ *,uint,uint,char const *)
0x180033893  mov     qword ptr [rsp+2C0h+Point.x], r12
0x180033898  lea     rcx, [rsp+2C0h+Point]; lpPoint
0x18003389d  call    cs:__imp_GetCursorPos
0x1800338a3  mov     [rsp+2C0h+prcRect], r12; prcRect
0x1800338a8  mov     rax, [rdi+0E0h]
0x1800338af  mov     [rsp+2C0h+hWnd], rax; hWnd
0x1800338b4  mov     [rsp+2C0h+nReserved], r12d; nReserved
0x1800338b9  mov     r9d, [rsp+2C0h+Point.y]; y
0x1800338be  mov     r8d, [rsp+2C0h+Point.x]; x
0x1800338c3  mov     edx, 2; uFlags
0x1800338c8  mov     rcx, r15; hMenu
0x1800338cb  call    cs:__imp_TrackPopupMenu
0x1800338d1  mov     rcx, [rdi+0F0h]
0x1800338d8  mov     r9, rsi; lParam
0x1800338db  mov     r8, rbx; wParam
0x1800338de  test    rcx, rcx
0x1800338e1  jz      loc_180033E13
0x1800338e7  mov     qword ptr [rsp+2C0h+Point.x], r12
0x1800338ec  mov     rax, [rcx]
0x1800338ef  lea     rdx, [rsp+2C0h+Point]
0x1800338f4  mov     qword ptr [rsp+2C0h+nReserved], rdx
0x1800338f9  mov     edx, r14d
0x1800338fc  mov     rax, [rax+0E8h]
0x180033903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033908  mov     rax, qword ptr [rsp+2C0h+Point.x]
0x18003390d  jmp     loc_180033E23
0x180033912  mov     eax, [rcx+168h]
0x180033918  cmp     eax, 2
0x18003391b  jnz     short loc_180033941
0x18003391d  mov     rcx, [rcx+258h]; this
0x180033924  mov     rdx, rsi; struct tagNMTREEVIEWA *
0x180033927  cmp     [rcx+8], r12d
0x18003392b  jnz     short loc_180033937
0x18003392d  call    ?OnSiteMapTVMsg@CToc@@QEAA_JPEAUtagNMTREEVIEWA@@@Z; CToc::OnSiteMapTVMsg(tagNMTREEVIEWA *)
0x180033932  jmp     loc_180033E23
0x180033937  call    ?OnBinaryTOCTVMsg@CToc@@QEAA_JPEAUtagNMTREEVIEWA@@@Z; CToc::OnBinaryTOCTVMsg(tagNMTREEVIEWA *)
0x18003393c  jmp     loc_180033E23
0x180033941  cmp     eax, 3
0x180033944  jnz     short loc_1800338D1
0x180033946  cmp     rbx, 0DEh
0x18003394d  jnz     loc_180033D47
0x180033953  mov     rcx, [rcx+260h]
0x18003395a  mov     rax, [rcx]
0x18003395d  mov     rdx, rsi
0x180033960  mov     rax, [rax+68h]
0x180033964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033969  jmp     loc_180033D47
0x18003396e  xorps   xmm0, xmm0
0x180033971  movups  xmmword ptr [rsp+2C0h+Rect.left], xmm0
0x180033976  lea     rdx, [rsp+2C0h+Rect]; lpRect
0x18003397b  mov     rcx, [rcx+0E0h]; hWnd
0x180033982  call    cs:__imp_GetWindowRect
0x180033988  mov     rax, [rdi+4C8h]
0x18003398f  sub     rax, qword ptr [rsp+2C0h+Rect.left]
0x180033994  jnz     short loc_1800339A2
0x180033996  mov     rax, [rdi+4D0h]
0x18003399d  sub     rax, qword ptr [rsp+2C0h+Rect.right]
0x1800339a2  test    rax, rax
0x1800339a5  jz      short loc_1800339B9
0x1800339a7  mov     r8d, r13d; bErase
0x1800339aa  xor     edx, edx; lpRect
0x1800339ac  mov     rcx, [rdi+0E0h]; hWnd
0x1800339b3  call    cs:__imp_InvalidateRect
0x1800339b9  movups  xmm0, xmmword ptr [rsp+2C0h+Rect.left]
0x1800339be  movdqu  xmmword ptr [rdi+4C8h], xmm0
0x1800339c6  jmp     loc_1800338D1
0x1800339cb  cmp     dword ptr [rcx+16Ch], 2
0x1800339d2  jnz     short loc_1800339E1
0x1800339d4  mov     rdx, rsi; struct tagDRAWITEMSTRUCT *
0x1800339d7  call    ?OnDrawStaticText@CHtmlHelpControl@@QEAAXPEAUtagDRAWITEMSTRUCT@@@Z; CHtmlHelpControl::OnDrawStaticText(tagDRAWITEMSTRUCT *)
0x1800339dc  jmp     loc_1800338D1
0x1800339e1  cmp     dword ptr [rcx+168h], 3
0x1800339e8  jz      loc_180033D47
0x1800339ee  jmp     loc_1800338D1
0x1800339f3  cmp     dword ptr [rcx+168h], 3
0x1800339fa  jnz     short loc_180033A3A
0x1800339fc  cmp     [rcx+1A0h], r12
0x180033a03  jz      short loc_180033A3A
0x180033a05  xorps   xmm0, xmm0
0x180033a08  movups  xmmword ptr [rsp+2C0h+Point.x], xmm0
0x180033a0d  lea     rdx, [rsp+2C0h+Point]; lprect
0x180033a12  mov     rcx, rbx; hdc
0x180033a15  call    cs:__imp_GetClipBox
0x180033a1b  mov     r8, [rdi+1A0h]; hbr
0x180033a22  lea     rdx, [rsp+2C0h+Point]; lprc
0x180033a27  mov     rcx, rbx; hDC
0x180033a2a  call    cs:__imp_FillRect
0x180033a30  mov     eax, 1
0x180033a35  jmp     loc_180033E23
0x180033a3a  mov     rcx, [rcx+0E0h]; hWnd
0x180033a41  call    cs:__imp_GetParent
0x180033a47  mov     r15, rax
0x180033a4a  test    rax, rax
0x180033a4d  jz      loc_1800338D1
0x180033a53  mov     qword ptr [rsp+2C0h+Points.x], r12
0x180033a58  mov     r9d, 1; cPoints
0x180033a5e  lea     r8, [rsp+2C0h+Points]; lpPoints
0x180033a63  mov     rdx, rax; hWndTo
0x180033a66  mov     rcx, [rdi+0E0h]; hWndFrom
0x180033a6d  call    cs:__imp_MapWindowPoints
0x180033a73  lea     r9, [rsp+2C0h+Points]; lppt
0x180033a78  mov     r8d, [rsp+2C0h+Points.y]; y
0x180033a7d  mov     edx, [rsp+2C0h+Points.x]; x
0x180033a81  mov     rcx, rbx; hdc
0x180033a84  call    cs:__imp_OffsetWindowOrgEx
0x180033a8a  mov     r9, rsi; lParam
0x180033a8d  mov     r8, rbx; wParam
0x180033a90  mov     edx, r13d; Msg
0x180033a93  mov     rcx, r15; hWnd
0x180033a96  call    cs:__imp_SendMessageA
0x180033a9c  mov     r15, rax
0x180033a9f  xor     r9d, r9d; lppt
0x180033aa2  mov     r8d, [rsp+2C0h+Points.y]; y
0x180033aa7  mov     edx, [rsp+2C0h+Points.x]; x
0x180033aab  mov     rcx, rbx; hdc
0x180033aae  call    cs:__imp_SetWindowOrgEx
0x180033ab4  test    r15, r15
0x180033ab7  jz      loc_1800338D1
0x180033abd  mov     rax, r15
0x180033ac0  jmp     loc_180033E23
0x180033ac5  cmp     [rcx+230h], r12d
0x180033acc  jz      short loc_180033AF3
0x180033ace  mov     edx, 5; uCmd
0x180033ad3  mov     rcx, [rcx+0E0h]; hWnd
0x180033ada  call    cs:__imp_GetWindow
0x180033ae0  test    rax, rax
0x180033ae3  jz      short loc_180033AF3
0x180033ae5  mov     rcx, rax; hWnd
0x180033ae8  call    cs:__imp_SetFocus
0x180033aee  jmp     loc_180033D47
0x180033af3  cmp     dword ptr [rdi+168h], 3
0x180033afa  jnz     loc_1800338D1
0x180033b00  mov     rcx, [rdi+260h]
0x180033b07  test    rcx, rcx
0x180033b0a  jz      loc_1800338D1
0x180033b10  mov     rax, [rcx]
0x180033b13  mov     rax, [rax+40h]
0x180033b17  jmp     loc_180033BAF
0x180033b1c  mov     rax, rbx
0x180033b1f  shr     rax, 10h
0x180033b23  movzx   r15d, ax
0x180033b27  mov     ecx, r15d
0x180033b2a  test    r15d, r15d
0x180033b2d  jz      short loc_180033B65
0x180033b2f  sub     ecx, 5
0x180033b32  jz      short loc_180033B65
0x180033b34  sub     ecx, 1
0x180033b37  jz      short loc_180033B46
0x180033b39  cmp     ecx, 1
0x180033b3c  jnz     short loc_180033BB9
0x180033b3e  mov     r8d, 4000h
0x180033b44  jmp     short loc_180033B4C
0x180033b46  mov     r8d, 4001h; wParam
0x180033b4c  mov     r9d, 1; lParam
0x180033b52  mov     edx, 0F4h; Msg
0x180033b57  mov     rcx, rsi; hWnd
0x180033b5a  call    cs:__imp_SendMessageA
0x180033b60  jmp     loc_180033D47
0x180033b65  cmp     [rdi+230h], r12d
0x180033b6c  jz      short loc_180033BB9
0x180033b6e  mov     eax, 0EFFEh
0x180033b73  cmp     bx, ax
0x180033b76  jnb     short loc_180033BB9
0x180033b78  mov     rcx, rdi; this
0x180033b7b  call    ?CheckSrcUrlSafety@CHtmlHelpControl@@QEAAJXZ; CHtmlHelpControl::CheckSrcUrlSafety(void)
0x180033b80  test    eax, eax
0x180033b82  jnz     loc_180033D47
0x180033b88  mov     eax, 2000h
0x180033b8d  add     eax, ebx
0x180033b8f  mov     rcx, rdi; this
0x180033b92  cmp     ax, 64h ; 'd'
0x180033b96  ja      short loc_180033BA5
0x180033b98  movzx   edx, bx; int
0x180033b9b  call    ?OnRelatedCommand@CHtmlHelpControl@@QEAAXH@Z; CHtmlHelpControl::OnRelatedCommand(int)
0x180033ba0  jmp     loc_180033D47
0x180033ba5  mov     rax, [rdi]
0x180033ba8  mov     rax, [rax+0E0h]
0x180033baf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033bb4  jmp     loc_180033D47
0x180033bb9  mov     ecx, [rdi+168h]
0x180033bbf  sub     ecx, 2
0x180033bc2  jz      short loc_180033C2C
0x180033bc4  sub     ecx, 1
0x180033bc7  jz      short loc_180033BF1
0x180033bc9  sub     ecx, 1
0x180033bcc  jz      short loc_180033BDC
0x180033bce  sub     ecx, 0Ch
0x180033bd1  jz      short loc_180033BDC
0x180033bd3  cmp     ecx, 1
0x180033bd6  jnz     loc_1800338D1
0x180033bdc  mov     rcx, rdi; this
0x180033bdf  call    ?CheckSrcUrlSafety@CHtmlHelpControl@@QEAAJXZ; CHtmlHelpControl::CheckSrcUrlSafety(void)
0x180033be4  test    eax, eax
0x180033be6  jnz     loc_180033D47
0x180033bec  mov     rcx, rdi
0x180033bef  jmp     short loc_180033B98
0x180033bf1  mov     rcx, rdi; this
0x180033bf4  call    ?CheckSrcUrlSafety@CHtmlHelpControl@@QEAAJXZ; CHtmlHelpControl::CheckSrcUrlSafety(void)
0x180033bf9  test    eax, eax
0x180033bfb  jnz     loc_180033D47
0x180033c01  mov     rcx, [rdi+260h]
0x180033c08  mov     rax, [rcx]
0x180033c0b  movzx   r8d, bx
0x180033c0f  mov     qword ptr [rsp+2C0h+nReserved], rsi
0x180033c14  mov     r9d, r15d
  ... truncated ...
```
