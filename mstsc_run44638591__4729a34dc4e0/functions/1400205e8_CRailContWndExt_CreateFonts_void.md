# CRailContWndExt::CreateFonts(void)

- ea: `0x1400205e8`
- end: `0x140020b02`
- name: `?CreateFonts@CRailContWndExt@@AEAAJXZ`
- size: `1306`
- prototype: `__int64 __fastcall(CRailContWndExt *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14001fbe0`

## callees

- `0x140004703`
- `0x140008a34`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14000d078`
- `0x1400205e8`
- `0x140024b80`
- `0x1400fcad0`
- `0x140113390`

## import_xrefs

- `USER32!ReleaseDC` at `0x140020ac9`
- `USER32!ReleaseDC` at `0x140020ada`
- `USER32!ReleaseDC` at `0x140020ac9`
- `USER32!ReleaseDC` at `0x140020ada`
- `USER32!GetDC` at `0x1400206d6`
- `USER32!GetDC` at `0x1400206e2`
- `USER32!GetDC` at `0x1400206d6`
- `USER32!GetDC` at `0x1400206e2`
- `USER32!GetDlgItem` at `0x140020665`
- `USER32!GetDlgItem` at `0x1400206ca`
- `USER32!GetDlgItem` at `0x140020665`
- `USER32!GetDlgItem` at `0x1400206ca`
- `USER32!SendMessageW` at `0x140020a53`
- `USER32!SendMessageW` at `0x140020a69`
- `USER32!SendMessageW` at `0x140020a53`
- `USER32!SendMessageW` at `0x140020a69`
- `msvcrt!_wtoi` at `0x1400208f0`
- `msvcrt!_wtoi` at `0x1400208fc`
- `msvcrt!_wtoi` at `0x1400208f0`
- `msvcrt!_wtoi` at `0x1400208fc`
- `KERNEL32!GetLastError` at `0x1400207d4`
- `KERNEL32!GetLastError` at `0x140020858`
- `KERNEL32!GetLastError` at `0x1400208aa`
- `KERNEL32!GetLastError` at `0x1400207d4`
- `KERNEL32!GetLastError` at `0x140020858`
- `KERNEL32!GetLastError` at `0x1400208aa`
- `GDI32!SetTextColor` at `0x140020a77`
- `GDI32!SetTextColor` at `0x140020a77`
- `GDI32!DeleteObject` at `0x14002096b`
- `GDI32!DeleteObject` at `0x140020988`
- `GDI32!DeleteObject` at `0x14002096b`
- `GDI32!DeleteObject` at `0x140020988`
- `GDI32!CreateFontIndirectW` at `0x14002099e`
- `GDI32!CreateFontIndirectW` at `0x1400209f5`
- `GDI32!CreateFontIndirectW` at `0x14002099e`
- `GDI32!CreateFontIndirectW` at `0x1400209f5`

## pseudocode

```c
__int64 __fastcall CRailContWndExt::CreateFonts(CRailContWndExt *this)
{
  HWND DlgItem; // r15
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v4; // ebx
  HWND v5; // r13
  HDC DC; // r12
  HDC v7; // rax
  HDC v8; // r14
  unsigned int v9; // eax
  unsigned int v10; // eax
  int v11; // edx
  const char *v12; // rcx
  signed int LastError; // edi
  unsigned int v14; // eax
  __int64 v15; // rdx
  int v16; // ebx
  int v17; // edi
  void *v18; // rcx
  void *v19; // rcx
  HFONT v20; // rax
  HFONT v21; // rax
  WPARAM v22; // r8
  unsigned int v23; // eax
  LOGFONTW lf; // [rsp+30h] [rbp-D0h] BYREF
  LOGFONTW v26; // [rsp+90h] [rbp-70h] BYREF
  wchar_t String[8]; // [rsp+F0h] [rbp-10h] BYREF
  int v28; // [rsp+100h] [rbp+0h]
  wchar_t v29[8]; // [rsp+108h] [rbp+8h] BYREF
  int v30; // [rsp+118h] [rbp+18h]
  unsigned __int16 v31[32]; // [rsp+120h] [rbp+20h] BYREF

  memset_0(&lf, 0, sizeof(lf));
  memset_0(&v26, 0, sizeof(v26));
  v30 = 0;
  v28 = 0;
  *(_OWORD *)v29 = 0;
  *(_OWORD *)String = 0;
  memset_0(v31, 0, sizeof(v31));
  DlgItem = GetDlgItem(*((HWND *)this + 16), 13203);
  if ( !DlgItem )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        107,
        &WPP_054707ce312e306d358833de4c0f150b_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
    return (unsigned int)-2147418113;
  }
  v5 = GetDlgItem(*((HWND *)this + 16), 13204);
  DC = GetDC(DlgItem);
  v7 = GetDC(v5);
  v8 = v7;
  if ( !DC )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        109,
        (unsigned int)&WPP_054707ce312e306d358833de4c0f150b_Traceguids,
        v9,
        (__int64)"hdcTitle",
        5);
    }
    v4 = -2147467259;
    goto LABEL_62;
  }
  if ( v7 )
  {
    if ( TSLoadString(*((HINSTANCE *)this + 1), 0x4E6Du, String, 10) )
    {
      if ( TSLoadString(*((HINSTANCE *)this + 1), 0x4E6Eu, v29, 10) )
      {
        if ( TSLoadString(*((HINSTANCE *)this + 1), 0x4E70u, v31, 32) )
        {
          v16 = _wtoi(String);
          v17 = _wtoi(v29);
          lf.lfHeight = CRailContWndExt::ScaleForCurrentDpi(this, -v16);
          lf.lfWeight = 500;
          lf.lfQuality = 0;
          StringCchCopyW(lf.lfFaceName, 0x20u, v31);
          v26.lfHeight = CRailContWndExt::ScaleForCurrentDpi(this, -v17);
          v26.lfWeight = 400;
          v26.lfQuality = 0;
          StringCchCopyW(v26.lfFaceName, 0x20u, v31);
          v18 = (void *)*((_QWORD *)this + 254);
          if ( v18 )
          {
            DeleteObject(v18);
            *((_QWORD *)this + 254) = 0;
          }
          v19 = (void *)*((_QWORD *)this + 255);
          if ( v19 )
          {
            DeleteObject(v19);
            *((_QWORD *)this + 255) = 0;
          }
          v20 = CreateFontIndirectW(&lf);
          *((_QWORD *)this + 254) = v20;
          if ( v20 )
          {
            v21 = CreateFontIndirectW(&v26);
            v22 = *((_QWORD *)this + 254);
            *((_QWORD *)this + 255) = v21;
            if ( v22 )
            {
              v4 = 0;
              SendMessageW(DlgItem, 0x30u, v22, 1);
              SendMessageW(v5, 0x30u, *((_QWORD *)this + 255), 1);
              if ( SetTextColor(DC, 0x993300u) == -1
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v23 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  118,
                  &WPP_054707ce312e306d358833de4c0f150b_Traceguids,
                  v23);
              }
              goto LABEL_61;
            }
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_19;
            }
            v10 = RdpWppGetCurrentThreadActivityIdPrefix();
            v11 = 117;
          }
          else
          {
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_19;
            }
            v10 = RdpWppGetCurrentThreadActivityIdPrefix();
            v11 = 116;
          }
          v12 = "_hfnTitleText";
          goto LABEL_18;
        }
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_26:
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          if ( LastError >= 0 )
            LastError = -2147467259;
          v4 = LastError;
          goto LABEL_61;
        }
        v14 = RdpWppGetCurrentThreadActivityIdPrefix();
        v15 = 113;
      }
      else
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_26;
        }
        v14 = RdpWppGetCurrentThreadActivityIdPrefix();
        v15 = 112;
      }
    }
    else
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_26;
      }
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      v15 = 111;
    }
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v15,
      &WPP_054707ce312e306d358833de4c0f150b_Traceguids,
      v14,
      LastError);
    goto LABEL_26;
  }
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    goto LABEL_19;
  }
  v10 = RdpWppGetCurrentThreadActivityIdPrefix();
  v11 = 110;
  v12 = "hdcConnectionStatus";
LABEL_18:
  WPP_SF_DsD(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    v11,
    (unsigned int)&WPP_054707ce312e306d358833de4c0f150b_Traceguids,
    v10,
    (__int64)v12,
    5);
LABEL_19:
  v4 = -2147467259;
LABEL_61:
  ReleaseDC(DlgItem, DC);
LABEL_62:
  if ( v8 )
    ReleaseDC(v5, v8);
  return v4;
}

```

## disassembly

```asm
0x1400205e8  push    rbp
0x1400205ea  push    rbx
0x1400205eb  push    rsi
0x1400205ec  push    rdi
0x1400205ed  push    r12
0x1400205ef  push    r13
0x1400205f1  push    r14
0x1400205f3  push    r15
0x1400205f5  lea     rbp, [rsp-78h]
0x1400205fa  sub     rsp, 178h
0x140020601  mov     rax, cs:__security_cookie
0x140020608  xor     rax, rsp
0x14002060b  mov     [rbp+0B0h+var_50], rax
0x14002060f  mov     rsi, rcx
0x140020612  mov     ebx, 5Ch ; '\'
0x140020617  mov     r8d, ebx; Size
0x14002061a  lea     rcx, [rsp+1B0h+lf]; void *
0x14002061f  xor     edx, edx; Val
0x140020621  call    memset_0
0x140020626  mov     r8d, ebx; Size
0x140020629  lea     rcx, [rbp+0B0h+var_120]; void *
0x14002062d  xor     edx, edx; Val
0x14002062f  call    memset_0
0x140020634  xor     eax, eax
0x140020636  lea     r8d, [rbx-1Ch]; Size
0x14002063a  xorps   xmm0, xmm0
0x14002063d  mov     [rbp+0B0h+var_98], eax
0x140020640  xorps   xmm1, xmm1
0x140020643  mov     [rbp+0B0h+var_B0], eax
0x140020646  xor     edx, edx; Val
0x140020648  lea     rcx, [rbp+0B0h+var_90]; void *
0x14002064c  movups  xmmword ptr [rbp+0B0h+var_A8], xmm0
0x140020650  movups  xmmword ptr [rbp+0B0h+String], xmm1
0x140020654  call    memset_0
0x140020659  mov     rcx, [rsi+80h]; hDlg
0x140020660  mov     edx, 3393h; nIDDlgItem
0x140020665  call    cs:__imp_GetDlgItem
0x14002066b  mov     r15, rax
0x14002066e  test    rax, rax
0x140020671  jnz     short loc_1400206BE
0x140020673  mov     rcx, cs:WPP_GLOBAL_Control
0x14002067a  lea     rax, WPP_GLOBAL_Control
0x140020681  cmp     rcx, rax
0x140020684  jz      short loc_1400206B4
0x140020686  test    byte ptr [rcx+1Ch], 1
0x14002068a  jz      short loc_1400206B4
0x14002068c  cmp     byte ptr [rcx+19h], 2
0x140020690  jb      short loc_1400206B4
0x140020692  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140020697  mov     rcx, cs:WPP_GLOBAL_Control
0x14002069e  lea     edx, [rbx+0Fh]
0x1400206a1  mov     r9d, eax
0x1400206a4  lea     r8, WPP_054707ce312e306d358833de4c0f150b_Traceguids
0x1400206ab  mov     rcx, [rcx+10h]
0x1400206af  call    WPP_SF_d
0x1400206b4  mov     ebx, 8000FFFFh
0x1400206b9  jmp     loc_140020AE0
0x1400206be  mov     rcx, [rsi+80h]; hDlg
0x1400206c5  mov     edx, 3394h; nIDDlgItem
0x1400206ca  call    cs:__imp_GetDlgItem
0x1400206d0  mov     rcx, r15; hWnd
0x1400206d3  mov     r13, rax
0x1400206d6  call    cs:__imp_GetDC
0x1400206dc  mov     rcx, r13; hWnd
0x1400206df  mov     r12, rax
0x1400206e2  call    cs:__imp_GetDC
0x1400206e8  mov     r14, rax
0x1400206eb  test    r12, r12
0x1400206ee  jnz     short loc_140020751
0x1400206f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400206f7  lea     rax, WPP_GLOBAL_Control
0x1400206fe  cmp     rcx, rax
0x140020701  jz      short loc_140020747
0x140020703  test    byte ptr [rcx+1Ch], 8
0x140020707  jz      short loc_140020747
0x140020709  cmp     byte ptr [rcx+19h], 2
0x14002070d  jb      short loc_140020747
0x14002070f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140020714  lea     rcx, aHdctitle; "hdcTitle"
0x14002071b  mov     [rsp+1B0h+var_188], 80004005h
0x140020723  mov     [rsp+1B0h+var_190], rcx
0x140020728  lea     edx, [r12+6Dh]
0x14002072d  mov     rcx, cs:WPP_GLOBAL_Control
0x140020734  lea     r8, WPP_054707ce312e306d358833de4c0f150b_Traceguids
0x14002073b  mov     r9d, eax
0x14002073e  mov     rcx, [rcx+10h]
0x140020742  call    WPP_SF_DsD
0x140020747  mov     ebx, 80004005h
0x14002074c  jmp     loc_140020ACF
0x140020751  test    r14, r14
0x140020754  jnz     short loc_1400207B6
0x140020756  mov     rcx, cs:WPP_GLOBAL_Control
0x14002075d  lea     rax, WPP_GLOBAL_Control
0x140020764  cmp     rcx, rax
0x140020767  jz      short loc_1400207AC
0x140020769  test    byte ptr [rcx+1Ch], 8
0x14002076d  jz      short loc_1400207AC
0x14002076f  cmp     byte ptr [rcx+19h], 2
0x140020773  jb      short loc_1400207AC
0x140020775  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14002077a  lea     edx, [r14+6Eh]
0x14002077e  lea     rcx, aHdcconnections; "hdcConnectionStatus"
0x140020785  mov     [rsp+1B0h+var_188], 80004005h
0x14002078d  lea     r8, WPP_054707ce312e306d358833de4c0f150b_Traceguids
0x140020794  mov     [rsp+1B0h+var_190], rcx
0x140020799  mov     r9d, eax
0x14002079c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400207a3  mov     rcx, [rcx+10h]
0x1400207a7  call    WPP_SF_DsD
0x1400207ac  mov     ebx, 80004005h
0x1400207b1  jmp     loc_140020AC3
0x1400207b6  mov     rcx, [rsi+8]; HINSTANCE
0x1400207ba  lea     r8, [rbp+0B0h+String]; unsigned __int16 *
0x1400207be  mov     ebx, 0Ah
0x1400207c3  mov     edx, 4E6Dh; unsigned int
0x1400207c8  mov     r9d, ebx; int
0x1400207cb  call    ?TSLoadString@@YAHPEAUHINSTANCE__@@IPEAGH@Z; TSLoadString(HINSTANCE__ *,uint,ushort *,int)
0x1400207d0  test    eax, eax
0x1400207d2  jnz     short loc_14002083F
0x1400207d4  call    cs:__imp_GetLastError
0x1400207da  mov     edi, eax
0x1400207dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400207e3  lea     rax, WPP_GLOBAL_Control
0x1400207ea  cmp     rcx, rax
0x1400207ed  jz      short loc_140020821
0x1400207ef  test    byte ptr [rcx+1Ch], 8
0x1400207f3  jz      short loc_140020821
0x1400207f5  cmp     byte ptr [rcx+19h], 2
0x1400207f9  jb      short loc_140020821
0x1400207fb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140020800  lea     edx, [rbx+65h]
0x140020803  mov     rcx, cs:WPP_GLOBAL_Control
0x14002080a  lea     r8, WPP_054707ce312e306d358833de4c0f150b_Traceguids
0x140020811  mov     r9d, eax
0x140020814  mov     dword ptr [rsp+1B0h+var_190], edi
0x140020818  mov     rcx, [rcx+10h]
0x14002081c  call    WPP_SF_Dd
0x140020821  test    edi, edi
0x140020823  jle     short loc_14002082E
0x140020825  movzx   edi, di
0x140020828  or      edi, 80070000h
0x14002082e  mov     ebx, 80004005h
0x140020833  test    edi, edi
0x140020835  cmovns  edi, ebx
0x140020838  mov     ebx, edi
0x14002083a  jmp     loc_140020AC3
0x14002083f  mov     rcx, [rsi+8]; HINSTANCE
0x140020843  lea     r8, [rbp+0B0h+var_A8]; unsigned __int16 *
0x140020847  mov     r9d, ebx; int
0x14002084a  mov     edx, 4E6Eh; unsigned int
0x14002084f  call    ?TSLoadString@@YAHPEAUHINSTANCE__@@IPEAGH@Z; TSLoadString(HINSTANCE__ *,uint,ushort *,int)
0x140020854  test    eax, eax
0x140020856  jnz     short loc_14002088E
0x140020858  call    cs:__imp_GetLastError
0x14002085e  mov     edi, eax
0x140020860  mov     rcx, cs:WPP_GLOBAL_Control
0x140020867  lea     rax, WPP_GLOBAL_Control
0x14002086e  cmp     rcx, rax
0x140020871  jz      short loc_140020821
0x140020873  test    byte ptr [rcx+1Ch], 8
0x140020877  jz      short loc_140020821
0x140020879  cmp     byte ptr [rcx+19h], 2
0x14002087d  jb      short loc_140020821
0x14002087f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140020884  mov     edx, 70h ; 'p'
0x140020889  jmp     loc_140020803
0x14002088e  mov     rcx, [rsi+8]; HINSTANCE
0x140020892  lea     r8, [rbp+0B0h+var_90]; unsigned __int16 *
0x140020896  mov     r9d, 20h ; ' '; int
0x14002089c  mov     edx, 4E70h; unsigned int
0x1400208a1  call    ?TSLoadString@@YAHPEAUHINSTANCE__@@IPEAGH@Z; TSLoadString(HINSTANCE__ *,uint,ushort *,int)
0x1400208a6  test    eax, eax
0x1400208a8  jnz     short loc_1400208EC
0x1400208aa  call    cs:__imp_GetLastError
0x1400208b0  mov     edi, eax
0x1400208b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400208b9  lea     rax, WPP_GLOBAL_Control
0x1400208c0  cmp     rcx, rax
0x1400208c3  jz      loc_140020821
0x1400208c9  test    byte ptr [rcx+1Ch], 8
0x1400208cd  jz      loc_140020821
0x1400208d3  cmp     byte ptr [rcx+19h], 2
0x1400208d7  jb      loc_140020821
0x1400208dd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400208e2  mov     edx, 71h ; 'q'
0x1400208e7  jmp     loc_140020803
0x1400208ec  lea     rcx, [rbp+0B0h+String]; String
0x1400208f0  call    cs:__imp__wtoi
0x1400208f6  lea     rcx, [rbp+0B0h+var_A8]; String
0x1400208fa  mov     ebx, eax
0x1400208fc  call    cs:__imp__wtoi
0x140020902  neg     ebx
0x140020904  mov     rcx, rsi; this
0x140020907  mov     edx, ebx; int
0x140020909  mov     edi, eax
0x14002090b  call    ?ScaleForCurrentDpi@CRailContWndExt@@AEAAHH@Z; CRailContWndExt::ScaleForCurrentDpi(int)
0x140020910  mov     ebx, 20h ; ' '
0x140020915  mov     [rsp+1B0h+lf.lfHeight], eax
0x140020919  mov     edx, ebx; unsigned __int64
0x14002091b  mov     [rsp+1B0h+lf.lfWeight], 1F4h
0x140020923  lea     r8, [rbp+0B0h+var_90]; unsigned __int16 *
0x140020927  mov     [rsp+1B0h+lf.lfQuality], 0
0x14002092c  lea     rcx, [rsp+1B0h+lf.lfFaceName]; unsigned __int16 *
0x140020931  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140020936  neg     edi
0x140020938  mov     rcx, rsi; this
0x14002093b  mov     edx, edi; int
0x14002093d  call    ?ScaleForCurrentDpi@CRailContWndExt@@AEAAHH@Z; CRailContWndExt::ScaleForCurrentDpi(int)
0x140020942  lea     r8, [rbp+0B0h+var_90]; unsigned __int16 *
0x140020946  mov     [rbp+0B0h+var_120.lfHeight], eax
0x140020949  mov     edx, ebx; unsigned __int64
0x14002094b  mov     [rbp+0B0h+var_120.lfWeight], 190h
0x140020952  lea     rcx, [rbp+0B0h+var_120.lfFaceName]; unsigned __int16 *
0x140020956  mov     [rbp+0B0h+var_120.lfQuality], 0
0x14002095a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14002095f  mov     rcx, [rsi+7F0h]; ho
0x140020966  test    rcx, rcx
0x140020969  jz      short loc_14002097C
0x14002096b  call    cs:__imp_DeleteObject
0x140020971  mov     qword ptr [rsi+7F0h], 0
0x14002097c  mov     rcx, [rsi+7F8h]; ho
0x140020983  test    rcx, rcx
0x140020986  jz      short loc_140020999
0x140020988  call    cs:__imp_DeleteObject
0x14002098e  mov     qword ptr [rsi+7F8h], 0
0x140020999  lea     rcx, [rsp+1B0h+lf]; lplf
0x14002099e  call    cs:__imp_CreateFontIndirectW
0x1400209a4  mov     [rsi+7F0h], rax
0x1400209ab  test    rax, rax
0x1400209ae  jnz     short loc_1400209F1
0x1400209b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400209b7  lea     rax, WPP_GLOBAL_Control
0x1400209be  cmp     rcx, rax
0x1400209c1  jz      loc_1400207AC
0x1400209c7  test    byte ptr [rcx+1Ch], 8
0x1400209cb  jz      loc_1400207AC
0x1400209d1  cmp     byte ptr [rcx+19h], 2
0x1400209d5  jb      loc_1400207AC
0x1400209db  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400209e0  mov     edx, 74h ; 't'
0x1400209e5  lea     rcx, aHfntitletext; "_hfnTitleText"
0x1400209ec  jmp     loc_140020785
0x1400209f1  lea     rcx, [rbp+0B0h+var_120]; lplf
0x1400209f5  call    cs:__imp_CreateFontIndirectW
0x1400209fb  mov     r8, [rsi+7F0h]; wParam
0x140020a02  mov     [rsi+7F8h], rax
0x140020a09  test    r8, r8
0x140020a0c  jnz     short loc_140020A45
0x140020a0e  mov     rcx, cs:WPP_GLOBAL_Control
0x140020a15  lea     rax, WPP_GLOBAL_Control
0x140020a1c  cmp     rcx, rax
0x140020a1f  jz      loc_1400207AC
0x140020a25  test    byte ptr [rcx+1Ch], 8
0x140020a29  jz      loc_1400207AC
0x140020a2f  cmp     byte ptr [rcx+19h], 2
0x140020a33  jb      loc_1400207AC
0x140020a39  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140020a3e  mov     edx, 75h ; 'u'
0x140020a43  jmp     short loc_1400209E5
0x140020a45  xor     ebx, ebx
0x140020a47  mov     rcx, r15; hWnd
0x140020a4a  lea     edi, [rbx+30h]
0x140020a4d  mov     edx, edi; Msg
0x140020a4f  lea     r9d, [rbx+1]; lParam
0x140020a53  call    cs:__imp_SendMessageW
0x140020a59  mov     r8, [rsi+7F8h]; wParam
0x140020a60  lea     r9d, [rbx+1]; lParam
0x140020a64  mov     edx, edi; Msg
0x140020a66  mov     rcx, r13; hWnd
0x140020a69  call    cs:__imp_SendMessageW
0x140020a6f  mov     edx, 993300h; color
0x140020a74  mov     rcx, r12; hdc
0x140020a77  call    cs:__imp_SetTextColor
0x140020a7d  cmp     eax, 0FFFFFFFFh
0x140020a80  jnz     short loc_140020AC3
0x140020a82  mov     rcx, cs:WPP_GLOBAL_Control
0x140020a89  lea     rax, WPP_GLOBAL_Control
0x140020a90  cmp     rcx, rax
0x140020a93  jz      short loc_140020AC3
0x140020a95  test    byte ptr [rcx+1Ch], 1
0x140020a99  jz      short loc_140020AC3
0x140020a9b  cmp     byte ptr [rcx+19h], 2
0x140020a9f  jb      short loc_140020AC3
0x140020aa1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140020aa6  mov     rcx, cs:WPP_GLOBAL_Control
0x140020aad  lea     edx, [rbx+76h]
0x140020ab0  mov     r9d, eax
0x140020ab3  lea     r8, WPP_054707ce312e306d358833de4c0f150b_Traceguids
0x140020aba  mov     rcx, [rcx+10h]
0x140020abe  call    WPP_SF_d
0x140020ac3  mov     rdx, r12; hDC
0x140020ac6  mov     rcx, r15; hWnd
0x140020ac9  call    cs:__imp_ReleaseDC
0x140020acf  test    r14, r14
0x140020ad2  jz      short loc_140020AE0
0x140020ad4  mov     rdx, r14; hDC
0x140020ad7  mov     rcx, r13; hWnd
0x140020ada  call    cs:__imp_ReleaseDC
0x140020ae0  mov     eax, ebx
0x140020ae2  mov     rcx, [rbp+0B0h+var_50]
  ... truncated ...
```
