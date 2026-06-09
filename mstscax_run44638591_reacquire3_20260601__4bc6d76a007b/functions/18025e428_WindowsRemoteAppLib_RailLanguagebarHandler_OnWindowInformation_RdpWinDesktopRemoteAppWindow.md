# WindowsRemoteAppLib::RailLanguagebarHandler::OnWindowInformation(RdpWinDesktopRemoteAppWindow *)

- ea: `0x18025e428`
- end: `0x18025ec2f`
- name: `?OnWindowInformation@RailLanguagebarHandler@WindowsRemoteAppLib@@QEAAXPEAVRdpWinDesktopRemoteAppWindow@@@Z`
- size: `2055`
- prototype: `void __fastcall(WindowsRemoteAppLib::RailLanguagebarHandler *__hidden this, struct RdpWinDesktopRemoteAppWindow *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, installer_update`

## callers

- `0x180247df0`

## callees

- `0x18002a334`
- `0x180039c98`
- `0x180039ce4`
- `0x1800e9b1c`
- `0x1800f47c8`
- `0x1802593c8`
- `0x18025dfa0`
- `0x18025e0ec`
- `0x18025e12c`
- `0x18025e238`
- `0x18025e26c`
- `0x18025e428`
- `0x18025ec38`
- `0x18025f0d8`
- `0x180688fc0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18025e4e4`
- `KERNEL32!GetLastError` at `0x18025e7fc`
- `KERNEL32!GetLastError` at `0x18025e951`
- `KERNEL32!GetLastError` at `0x18025ea31`
- `KERNEL32!GetLastError` at `0x18025ea9a`
- `KERNEL32!GetLastError` at `0x18025ebd2`
- `KERNEL32!GetLastError` at `0x18025e4e4`
- `KERNEL32!GetLastError` at `0x18025e7fc`
- `KERNEL32!GetLastError` at `0x18025e951`
- `KERNEL32!GetLastError` at `0x18025ea31`
- `KERNEL32!GetLastError` at `0x18025ea9a`
- `KERNEL32!GetLastError` at `0x18025ebd2`
- `USER32!GetWindowRect` at `0x18025e4da`
- `USER32!GetWindowRect` at `0x18025ebc8`
- `USER32!GetWindowRect` at `0x18025e4da`
- `USER32!GetWindowRect` at `0x18025ebc8`
- `USER32!SetWindowPos` at `0x18025e7f2`
- `USER32!SetWindowPos` at `0x18025e947`
- `USER32!SetWindowPos` at `0x18025ea90`
- `USER32!SetWindowPos` at `0x18025e7f2`
- `USER32!SetWindowPos` at `0x18025e947`
- `USER32!SetWindowPos` at `0x18025ea90`
- `USER32!CopyRect` at `0x18025e635`
- `USER32!CopyRect` at `0x18025e635`
- `USER32!IsRectEmpty` at `0x18025e60e`
- `USER32!IsRectEmpty` at `0x18025e60e`
- `USER32!IsWindowVisible` at `0x18025e63e`
- `USER32!IsWindowVisible` at `0x18025e63e`
- `USER32!SystemParametersInfoW` at `0x18025ea27`
- `USER32!SystemParametersInfoW` at `0x18025ea27`

## string_xrefs

- `0x18025eb48`: `UpdateServerWithGeometry failed`

## pseudocode

```c
void __fastcall WindowsRemoteAppLib::RailLanguagebarHandler::OnWindowInformation(
        WindowsRemoteAppLib::RailLanguagebarHandler *this,
        struct RdpWinDesktopRemoteAppWindow *a2)
{
  HWND v4; // r12
  unsigned int CurrentThreadActivityIdPrefix; // eax
  DWORD LastError; // edi
  unsigned int v7; // eax
  __int64 v8; // rdx
  HKEY v9; // rax
  int v10; // edi
  unsigned int v11; // eax
  int v12; // ebx
  int v13; // edi
  int v14; // esi
  int v15; // r14d
  unsigned int v16; // eax
  WindowsRemoteAppLib::RailLanguagebarHandler *v17; // rcx
  char v18; // bl
  unsigned int v19; // eax
  unsigned int v20; // eax
  __int64 v21; // rdx
  WindowsRemoteAppLib::RailLanguagebarHandler *v22; // rcx
  LONG left; // r8d
  LONG top; // r9d
  unsigned int v25; // eax
  HKEY v26; // rax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  int updated; // edi
  unsigned int v31; // eax
  int v32; // edx
  unsigned int v33; // eax
  unsigned int v34; // eax
  __int64 cy; // [rsp+28h] [rbp-58h]
  struct tagRECT Rect; // [rsp+48h] [rbp-38h] BYREF
  struct tagRECT v37; // [rsp+58h] [rbp-28h] BYREF
  __int128 pvParam; // [rsp+68h] [rbp-18h] BYREF

  v37 = 0;
  Rect = 0;
  if ( !*(_DWORD *)this )
    return;
  v4 = (HWND)*((_QWORD *)a2 + 6);
  if ( !v4 || !WindowsRemoteAppLib::RailLanguagebarHandler::IsRailLanguageBar(this, *((HWND *)a2 + 6)) )
    return;
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      WPP_e269da8258e73cb74ef521a4ccd959d6_Traceguids,
      CurrentThreadActivityIdPrefix,
      (_DWORD)v4);
  }
  if ( !GetWindowRect(v4, &Rect) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 19;
LABEL_13:
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, WPP_e269da8258e73cb74ef521a4ccd959d6_Traceguids, v7, LastError);
      return;
    }
    return;
  }
  v9 = WPP_GLOBAL_Control;
  v10 = 0;
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control )
  {
    if ( ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v11 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ddddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        WPP_e269da8258e73cb74ef521a4ccd959d6_Traceguids,
        v11,
        Rect.top,
        Rect.left,
        Rect.right,
        Rect.bottom);
      v9 = WPP_GLOBAL_Control;
    }
    if ( v9 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v9[7] & 1) != 0 && *((_BYTE *)v9 + 25) >= 3u )
    {
      v12 = *((_DWORD *)this + 13);
      v13 = *((_DWORD *)this + 12);
      v14 = *((_DWORD *)this + 10);
      v15 = *((_DWORD *)this + 11);
      v16 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ddddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        WPP_e269da8258e73cb74ef521a4ccd959d6_Traceguids,
        v16,
        v15,
        v14,
        v13,
        v12);
      v10 = 0;
    }
  }
  if ( !IsRectEmpty((const RECT *)((char *)this + 40))
    && !(unsigned int)WindowsRemoteAppLib::RailLanguagebarHandler::IsEqualRect(
                        v17,
                        &Rect,
                        (const struct tagRECT *)((char *)this + 40)) )
  {
    v10 = 1;
  }
  CopyRect((LPRECT)((char *)this + 40), &Rect);
  if ( IsWindowVisible(v4) )
  {
    v18 = 1;
  }
  else
  {
    v18 = 0;
    if ( WindowsRemoteAppLib::RailLanguagebarHandler::GetDeskbandWindow(this) )
    {
      WindowsRemoteAppLib::RailLanguagebarHandler::HideRailDeskband(this);
      *((_QWORD *)a2 + 33) = 0;
    }
  }
  if ( (*((_DWORD *)this + 4) & 0x800) == 0 )
  {
    if ( (*((_BYTE *)this + 16) & 1) == 0 )
      return;
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v27 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_e269da8258e73cb74ef521a4ccd959d6_Traceguids, v27);
      v26 = WPP_GLOBAL_Control;
    }
    if ( !*((_DWORD *)this + 5) )
      goto LABEL_110;
    if ( !v10 )
      return;
    if ( v26 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v26[7] & 1) != 0 && *((_BYTE *)v26 + 25) >= 3u )
    {
      v28 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_e269da8258e73cb74ef521a4ccd959d6_Traceguids, v28);
    }
    if ( *((_DWORD *)this + 14) )
    {
      if ( !SetWindowPos(v4, 0, *((_DWORD *)this + 6), *((_DWORD *)this + 7), 0, 0, 0x2315u) )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v7 = RdpWppGetCurrentThreadActivityIdPrefix();
          v8 = 29;
          goto LABEL_13;
        }
        return;
      }
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v29 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_e269da8258e73cb74ef521a4ccd959d6_Traceguids, v29);
      }
      updated = RdpWinDesktopRemoteAppWindow::UpdateServerWithGeometry(a2, 4);
      if ( updated >= 0
        || WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_109;
      }
      v31 = RdpWppGetCurrentThreadActivityIdPrefix();
      v32 = 31;
    }
    else
    {
      pvParam = 0;
      if ( !SystemParametersInfoW(0x30u, 0, &pvParam, 0) )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v7 = RdpWppGetCurrentThreadActivityIdPrefix();
          v8 = 32;
          goto LABEL_13;
        }
        return;
      }
      if ( !SetWindowPos(v4, 0, Rect.left + DWORD2(pvParam) - Rect.right, SDWORD1(pvParam), 0, 0, 0x2315u) )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v7 = RdpWppGetCurrentThreadActivityIdPrefix();
          v8 = 33;
          goto LABEL_13;
        }
        return;
      }
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v33 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_e269da8258e73cb74ef521a4ccd959d6_Traceguids, v33);
      }
      updated = RdpWinDesktopRemoteAppWindow::UpdateServerWithGeometry(a2, 5);
      if ( updated >= 0
        || WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_109;
      }
      v31 = RdpWppGetCurrentThreadActivityIdPrefix();
      v32 = 35;
    }
    LODWORD(cy) = updated;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v32,
      (unsigned int)WPP_e269da8258e73cb74ef521a4ccd959d6_Traceguids,
      v31,
      (__int64)"UpdateServerWithGeometry failed",
      cy);
LABEL_109:
    WindowsRemoteAppLib::RailLanguagebarHandler::HideRailDeskband(this);
    *((_QWORD *)a2 + 33) = 0;
    *((_DWORD *)this + 5) = 0;
    v26 = WPP_GLOBAL_Control;
LABEL_110:
    if ( v26 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v26[7] & 1) != 0 && *((_BYTE *)v26 + 25) >= 3u )
    {
      v34 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_e269da8258e73cb74ef521a4ccd959d6_Traceguids, v34);
    }
    if ( GetWindowRect(v4, (LPRECT)((char *)this + 24)) )
    {
      *((_DWORD *)this + 14) = 1;
    }
    else
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v7 = RdpWppGetCurrentThreadActivityIdPrefix();
        v8 = 37;
        goto LABEL_13;
      }
    }
    return;
  }
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    v19 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_e269da8258e73cb74ef521a4ccd959d6_Traceguids, v19);
  }
  if ( v18 && !WindowsRemoteAppLib::RailLanguagebarHandler::GetDeskbandWindow(this) )
  {
    if ( !(unsigned int)WindowsRemoteAppLib::RailLanguagebarHandler::ShowRailDeskband(this) )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return;
      }
      v20 = RdpWppGetCurrentThreadActivityIdPrefix();
      v21 = 23;
      goto LABEL_41;
    }
    *((_DWORD *)this + 5) = 0;
    *((_QWORD *)a2 + 33) = WindowsRemoteAppLib::RailLanguagebarHandler::GetTrayWindow(this);
  }
  if ( !WindowsRemoteAppLib::RailLanguagebarHandler::RefreshRailDeskband(this, &Rect, &v37) )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return;
    }
    v20 = RdpWppGetCurrentThreadActivityIdPrefix();
    v21 = 24;
LABEL_41:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, WPP_e269da8258e73cb74ef521a4ccd959d6_Traceguids, v20);
    return;
  }
  if ( !(unsigned int)WindowsRemoteAppLib::RailLanguagebarHandler::IsEqualRect(v22, &Rect, &v37) )
  {
    left = v37.left;
    top = v37.top;
    if ( (v37.left + v37.right - (Rect.right - Rect.left)) / 2 > v37.left )
      left = (v37.left + v37.right - (Rect.right - Rect.left)) / 2;
    if ( (v37.top + v37.bottom - (Rect.bottom - Rect.top)) / 2 > v37.top )
      top = (v37.top + v37.bottom - (Rect.bottom - Rect.top)) / 2;
    if ( SetWindowPos(v4, 0, left, top, Rect.right - Rect.left, Rect.bottom - Rect.top, 0x2314u) )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v25 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_e269da8258e73cb74ef521a4ccd959d6_Traceguids, v25);
      }
      RdpWinDesktopRemoteAppWindow::UpdateServerWithGeometry(a2, 3);
    }
    else
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v7 = RdpWppGetCurrentThreadActivityIdPrefix();
        v8 = 25;
        goto LABEL_13;
      }
    }
  }
}

```

## disassembly

```asm
0x18025e428  mov     [rsp-38h+arg_10], rbx
0x18025e42d  push    rbp
0x18025e42e  push    rsi
0x18025e42f  push    rdi
0x18025e430  push    r12
0x18025e432  push    r13
0x18025e434  push    r14
0x18025e436  push    r15
0x18025e438  mov     rbp, rsp
0x18025e43b  sub     rsp, 80h
0x18025e442  mov     rax, cs:__security_cookie
0x18025e449  xor     rax, rsp
0x18025e44c  mov     [rbp+var_8], rax
0x18025e450  xor     esi, esi
0x18025e452  xorps   xmm0, xmm0
0x18025e455  xorps   xmm1, xmm1
0x18025e458  mov     r13, rdx
0x18025e45b  mov     r15, rcx
0x18025e45e  movups  xmmword ptr [rbp+var_28.left], xmm0
0x18025e462  movups  xmmword ptr [rbp+Rect.left], xmm1
0x18025e466  cmp     [rcx], esi
0x18025e468  jz      loc_18025EC08
0x18025e46e  mov     r12, [rdx+30h]
0x18025e472  test    r12, r12
0x18025e475  jz      loc_18025EC08
0x18025e47b  mov     rdx, r12; HWND
0x18025e47e  call    ?IsRailLanguageBar@RailLanguagebarHandler@WindowsRemoteAppLib@@IEAAHPEAUHWND__@@@Z; WindowsRemoteAppLib::RailLanguagebarHandler::IsRailLanguageBar(HWND__ *)
0x18025e483  test    eax, eax
0x18025e485  jz      loc_18025EC08
0x18025e48b  mov     rax, cs:WPP_GLOBAL_Control
0x18025e492  lea     r14, WPP_GLOBAL_Control
0x18025e499  lea     ebx, [rsi+1]
0x18025e49c  cmp     rax, r14
0x18025e49f  jz      short loc_18025E4D3
0x18025e4a1  test    [rax+1Ch], bl
0x18025e4a4  jz      short loc_18025E4D3
0x18025e4a6  cmp     byte ptr [rax+19h], 3
0x18025e4aa  jb      short loc_18025E4D3
0x18025e4ac  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18025e4b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18025e4b8  lea     edx, [rsi+12h]
0x18025e4bb  mov     r9d, eax
0x18025e4be  mov     [rsp+80h+var_60], r12d
0x18025e4c3  lea     r8, WPP_e269da8258e73cb74ef521a4ccd959d6_Traceguids
0x18025e4ca  mov     rcx, [rcx+10h]
0x18025e4ce  call    WPP_SF_Dd
0x18025e4d3  lea     rdx, [rbp+Rect]; lpRect
0x18025e4d7  mov     rcx, r12; hWnd
0x18025e4da  call    cs:__imp_GetWindowRect
0x18025e4e0  test    eax, eax
0x18025e4e2  jnz     short loc_18025E53F
0x18025e4e4  call    cs:__imp_GetLastError
0x18025e4ea  mov     edi, eax
0x18025e4ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18025e4f3  cmp     rcx, r14
0x18025e4f6  jz      loc_18025EC08
0x18025e4fc  test    byte ptr [rcx+1Ch], 8
0x18025e500  jz      loc_18025EC08
0x18025e506  mov     ebx, 2
0x18025e50b  cmp     [rcx+19h], bl
0x18025e50e  jb      loc_18025EC08
0x18025e514  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18025e519  lea     edx, [rbx+11h]
0x18025e51c  mov     rcx, cs:WPP_GLOBAL_Control
0x18025e523  lea     r8, WPP_e269da8258e73cb74ef521a4ccd959d6_Traceguids
0x18025e52a  mov     r9d, eax
0x18025e52d  mov     [rsp+80h+var_60], edi
0x18025e531  mov     rcx, [rcx+10h]
0x18025e535  call    WPP_SF_Dd
0x18025e53a  jmp     loc_18025EC08
0x18025e53f  mov     rax, cs:WPP_GLOBAL_Control
0x18025e546  mov     edi, esi
0x18025e548  mov     [rbp+var_40], esi
0x18025e54b  cmp     rax, r14
0x18025e54e  jz      loc_18025E607
0x18025e554  test    [rax+1Ch], bl
0x18025e557  jz      short loc_18025E5A6
0x18025e559  cmp     byte ptr [rax+19h], 3
0x18025e55d  jb      short loc_18025E5A6
0x18025e55f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18025e564  mov     ecx, [rbp+Rect.bottom]
0x18025e567  lea     r8, WPP_e269da8258e73cb74ef521a4ccd959d6_Traceguids
0x18025e56e  mov     [rsp+80h+var_48], ecx
0x18025e572  mov     edx, 14h
0x18025e577  mov     ecx, [rbp+Rect.right]
0x18025e57a  mov     r9d, eax
0x18025e57d  mov     [rsp+80h+uFlags], ecx
0x18025e581  mov     ecx, [rbp+Rect.left]
0x18025e584  mov     dword ptr [rsp+80h+cy], ecx
0x18025e588  mov     ecx, [rbp+Rect.top]
0x18025e58b  mov     [rsp+80h+var_60], ecx
0x18025e58f  mov     rcx, cs:WPP_GLOBAL_Control
0x18025e596  mov     rcx, [rcx+10h]
0x18025e59a  call    WPP_SF_Ddddd
0x18025e59f  mov     rax, cs:WPP_GLOBAL_Control
0x18025e5a6  cmp     rax, r14
0x18025e5a9  jz      short loc_18025E607
0x18025e5ab  test    [rax+1Ch], bl
0x18025e5ae  jz      short loc_18025E607
0x18025e5b0  cmp     byte ptr [rax+19h], 3
0x18025e5b4  jb      short loc_18025E607
0x18025e5b6  mov     ebx, [r15+34h]
0x18025e5ba  mov     edi, [r15+30h]
0x18025e5be  mov     esi, [r15+28h]
0x18025e5c2  mov     r14d, [r15+2Ch]
0x18025e5c6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18025e5cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18025e5d2  lea     r8, WPP_e269da8258e73cb74ef521a4ccd959d6_Traceguids
0x18025e5d9  mov     [rsp+80h+var_48], ebx
0x18025e5dd  mov     edx, 15h
0x18025e5e2  mov     [rsp+80h+uFlags], edi
0x18025e5e6  mov     r9d, eax
0x18025e5e9  mov     dword ptr [rsp+80h+cy], esi
0x18025e5ed  mov     rcx, [rcx+10h]
0x18025e5f1  mov     [rsp+80h+var_60], r14d
0x18025e5f6  call    WPP_SF_Ddddd
0x18025e5fb  mov     edi, [rbp+var_40]
0x18025e5fe  lea     r14, WPP_GLOBAL_Control
0x18025e605  xor     esi, esi
0x18025e607  lea     rbx, [r15+28h]
0x18025e60b  mov     rcx, rbx; lprc
0x18025e60e  call    cs:__imp_IsRectEmpty
0x18025e614  test    eax, eax
0x18025e616  jnz     short loc_18025E62E
0x18025e618  mov     r8, rbx; struct tagRECT *
0x18025e61b  lea     rdx, [rbp+Rect]; struct tagRECT *
0x18025e61f  call    ?IsEqualRect@RailLanguagebarHandler@WindowsRemoteAppLib@@IEAAHPEBUtagRECT@@0@Z; WindowsRemoteAppLib::RailLanguagebarHandler::IsEqualRect(tagRECT const *,tagRECT const *)
0x18025e624  test    eax, eax
0x18025e626  mov     ecx, 1
0x18025e62b  cmovz   edi, ecx
0x18025e62e  lea     rdx, [rbp+Rect]; lprcSrc
0x18025e632  mov     rcx, rbx; lprcDst
0x18025e635  call    cs:__imp_CopyRect
0x18025e63b  mov     rcx, r12; hWnd
0x18025e63e  call    cs:__imp_IsWindowVisible
0x18025e644  mov     ecx, 1
0x18025e649  cmp     eax, ecx
0x18025e64b  jnz     short loc_18025E651
0x18025e64d  mov     bl, cl
0x18025e64f  jmp     short loc_18025E675
0x18025e651  mov     rcx, r15; this
0x18025e654  mov     bl, sil
0x18025e657  call    ?GetDeskbandWindow@RailLanguagebarHandler@WindowsRemoteAppLib@@IEAAPEAUHWND__@@XZ; WindowsRemoteAppLib::RailLanguagebarHandler::GetDeskbandWindow(void)
0x18025e65c  test    rax, rax
0x18025e65f  jz      short loc_18025E670
0x18025e661  mov     rcx, r15; this
0x18025e664  call    ?HideRailDeskband@RailLanguagebarHandler@WindowsRemoteAppLib@@IEAAXXZ; WindowsRemoteAppLib::RailLanguagebarHandler::HideRailDeskband(void)
0x18025e669  mov     [r13+108h], rsi
0x18025e670  mov     ecx, 1
0x18025e675  test    dword ptr [r15+10h], 800h
0x18025e67d  jz      loc_18025E886
0x18025e683  mov     rax, cs:WPP_GLOBAL_Control
0x18025e68a  cmp     rax, r14
0x18025e68d  jz      short loc_18025E6BE
0x18025e68f  test    [rax+1Ch], cl
0x18025e692  jz      short loc_18025E6BE
0x18025e694  cmp     byte ptr [rax+19h], 3
0x18025e698  jb      short loc_18025E6BE
0x18025e69a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18025e69f  mov     rcx, cs:WPP_GLOBAL_Control
0x18025e6a6  lea     r8, WPP_e269da8258e73cb74ef521a4ccd959d6_Traceguids
0x18025e6ad  mov     edx, 16h
0x18025e6b2  mov     r9d, eax
0x18025e6b5  mov     rcx, [rcx+10h]
0x18025e6b9  call    WPP_SF_d
0x18025e6be  test    bl, bl
0x18025e6c0  jz      short loc_18025E73D
0x18025e6c2  mov     rcx, r15; this
0x18025e6c5  call    ?GetDeskbandWindow@RailLanguagebarHandler@WindowsRemoteAppLib@@IEAAPEAUHWND__@@XZ; WindowsRemoteAppLib::RailLanguagebarHandler::GetDeskbandWindow(void)
0x18025e6ca  test    rax, rax
0x18025e6cd  jnz     short loc_18025E73D
0x18025e6cf  mov     rcx, r15; this
0x18025e6d2  call    ?ShowRailDeskband@RailLanguagebarHandler@WindowsRemoteAppLib@@IEAAHXZ; WindowsRemoteAppLib::RailLanguagebarHandler::ShowRailDeskband(void)
0x18025e6d7  test    eax, eax
0x18025e6d9  jnz     short loc_18025E72A
0x18025e6db  mov     rax, cs:WPP_GLOBAL_Control
0x18025e6e2  cmp     rax, r14
0x18025e6e5  jz      loc_18025EC08
0x18025e6eb  test    byte ptr [rax+1Ch], 8
0x18025e6ef  jz      loc_18025EC08
0x18025e6f5  mov     ebx, 2
0x18025e6fa  cmp     [rax+19h], bl
0x18025e6fd  jb      loc_18025EC08
0x18025e703  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18025e708  lea     edx, [rbx+15h]
0x18025e70b  mov     rcx, cs:WPP_GLOBAL_Control
0x18025e712  lea     r8, WPP_e269da8258e73cb74ef521a4ccd959d6_Traceguids
0x18025e719  mov     r9d, eax
0x18025e71c  mov     rcx, [rcx+10h]
0x18025e720  call    WPP_SF_d
0x18025e725  jmp     loc_18025EC08
0x18025e72a  mov     rcx, r15; this
0x18025e72d  mov     [r15+14h], esi
0x18025e731  call    ?GetTrayWindow@RailLanguagebarHandler@WindowsRemoteAppLib@@IEAAPEAUHWND__@@XZ; WindowsRemoteAppLib::RailLanguagebarHandler::GetTrayWindow(void)
0x18025e736  mov     [r13+108h], rax
0x18025e73d  lea     r8, [rbp+var_28]; struct tagRECT *
0x18025e741  mov     rcx, r15; this
0x18025e744  lea     rdx, [rbp+Rect]; struct tagRECT *
0x18025e748  call    ?RefreshRailDeskband@RailLanguagebarHandler@WindowsRemoteAppLib@@IEAAHPEBUtagRECT@@PEAU3@@Z; WindowsRemoteAppLib::RailLanguagebarHandler::RefreshRailDeskband(tagRECT const *,tagRECT *)
0x18025e74d  test    eax, eax
0x18025e74f  jnz     short loc_18025E783
0x18025e751  mov     rax, cs:WPP_GLOBAL_Control
0x18025e758  cmp     rax, r14
0x18025e75b  jz      loc_18025EC08
0x18025e761  test    byte ptr [rax+1Ch], 8
0x18025e765  jz      loc_18025EC08
0x18025e76b  mov     ebx, 2
0x18025e770  cmp     [rax+19h], bl
0x18025e773  jb      loc_18025EC08
0x18025e779  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18025e77e  lea     edx, [rbx+16h]
0x18025e781  jmp     short loc_18025E70B
0x18025e783  lea     r8, [rbp+var_28]; struct tagRECT *
0x18025e787  lea     rdx, [rbp+Rect]; struct tagRECT *
0x18025e78b  call    ?IsEqualRect@RailLanguagebarHandler@WindowsRemoteAppLib@@IEAAHPEBUtagRECT@@0@Z; WindowsRemoteAppLib::RailLanguagebarHandler::IsEqualRect(tagRECT const *,tagRECT const *)
0x18025e790  test    eax, eax
0x18025e792  jnz     loc_18025EC08
0x18025e798  mov     r8d, [rbp+var_28.left]
0x18025e79c  mov     ebx, 2
0x18025e7a1  mov     r11d, [rbp+Rect.right]
0x18025e7a5  mov     rcx, r12; hWnd
0x18025e7a8  sub     r11d, [rbp+Rect.left]
0x18025e7ac  mov     eax, [rbp+var_28.right]
0x18025e7af  mov     r9d, [rbp+var_28.top]
0x18025e7b3  sub     eax, r11d
0x18025e7b6  mov     r10d, [rbp+Rect.bottom]
0x18025e7ba  add     eax, r8d
0x18025e7bd  sub     r10d, [rbp+Rect.top]
0x18025e7c1  cdq
0x18025e7c2  idiv    ebx
0x18025e7c4  mov     [rsp+80h+uFlags], 2314h; uFlags
0x18025e7cc  cmp     eax, r8d
0x18025e7cf  mov     dword ptr [rsp+80h+cy], r10d; cy
0x18025e7d4  mov     [rsp+80h+var_60], r11d; cx
0x18025e7d9  cmovg   r8d, eax; X
0x18025e7dd  mov     eax, [rbp+var_28.bottom]
0x18025e7e0  sub     eax, r10d
0x18025e7e3  add     eax, r9d
0x18025e7e6  cdq
0x18025e7e7  idiv    ebx
0x18025e7e9  cmp     eax, r9d
0x18025e7ec  cmovg   r9d, eax; Y
0x18025e7f0  xor     edx, edx; hWndInsertAfter
0x18025e7f2  call    cs:__imp_SetWindowPos
0x18025e7f8  test    eax, eax
0x18025e7fa  jnz     short loc_18025E834
0x18025e7fc  call    cs:__imp_GetLastError
0x18025e802  mov     edi, eax
0x18025e804  mov     rcx, cs:WPP_GLOBAL_Control
0x18025e80b  cmp     rcx, r14
0x18025e80e  jz      loc_18025EC08
0x18025e814  test    byte ptr [rcx+1Ch], 8
0x18025e818  jz      loc_18025EC08
0x18025e81e  cmp     [rcx+19h], bl
0x18025e821  jb      loc_18025EC08
0x18025e827  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18025e82c  lea     edx, [rbx+17h]
0x18025e82f  jmp     loc_18025E51C
0x18025e834  mov     rax, cs:WPP_GLOBAL_Control
0x18025e83b  cmp     rax, r14
0x18025e83e  jz      short loc_18025E874
0x18025e840  mov     ecx, 1
0x18025e845  test    [rax+1Ch], cl
0x18025e848  jz      short loc_18025E874
0x18025e84a  cmp     byte ptr [rax+19h], 3
0x18025e84e  jb      short loc_18025E874
0x18025e850  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18025e855  mov     rcx, cs:WPP_GLOBAL_Control
0x18025e85c  lea     r8, WPP_e269da8258e73cb74ef521a4ccd959d6_Traceguids
0x18025e863  mov     edx, 1Ah
0x18025e868  mov     r9d, eax
0x18025e86b  mov     rcx, [rcx+10h]
0x18025e86f  call    WPP_SF_d
0x18025e874  mov     edx, 3
0x18025e879  mov     rcx, r13
0x18025e87c  call    ?UpdateServerWithGeometry@RdpWinDesktopRemoteAppWindow@@QEAAJW4UpdateServerWithGeometryReason@@@Z; RdpWinDesktopRemoteAppWindow::UpdateServerWithGeometry(UpdateServerWithGeometryReason)
0x18025e881  jmp     loc_18025EC08
0x18025e886  test    [r15+10h], cl
0x18025e88a  jz      loc_18025EC08
0x18025e890  mov     rax, cs:WPP_GLOBAL_Control
0x18025e897  cmp     rax, r14
0x18025e89a  jz      short loc_18025E8D7
0x18025e89c  test    [rax+1Ch], cl
0x18025e89f  jz      short loc_18025E8D7
0x18025e8a1  cmp     byte ptr [rax+19h], 3
0x18025e8a5  jb      short loc_18025E8D7
0x18025e8a7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18025e8ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18025e8b3  lea     r8, WPP_e269da8258e73cb74ef521a4ccd959d6_Traceguids
0x18025e8ba  mov     edx, 1Bh
0x18025e8bf  mov     r9d, eax
0x18025e8c2  mov     rcx, [rcx+10h]
0x18025e8c6  call    WPP_SF_d
0x18025e8cb  mov     rax, cs:WPP_GLOBAL_Control
0x18025e8d2  mov     ecx, 1
0x18025e8d7  mov     ebx, 2
0x18025e8dc  cmp     [r15+14h], esi
0x18025e8e0  jz      loc_18025EB8C
0x18025e8e6  test    edi, edi
0x18025e8e8  jz      loc_18025EC08
  ... truncated ...
```
