# CDlgBase::DrawShieldBanner(HDC__ *,uint,uint,uint,CDlgBase::_BANNER_GRADIENT_TYPE)

- ea: `0x180648bb4`
- end: `0x18064917c`
- name: `?DrawShieldBanner@CDlgBase@@IEAAHPEAUHDC__@@IIIW4_BANNER_GRADIENT_TYPE@1@@Z`
- size: `1480`
- prototype: `int __high(HDC, unsigned int, unsigned int, unsigned int, enum CDlgBase::_BANNER_GRADIENT_TYPE)`
- caller_count: `3`
- callee_count: `13`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1804e23d0`
- `0x1804f5880`
- `0x1804ffe3c`

## callees

- `0x18002a334`
- `0x180039ce4`
- `0x1800e9b1c`
- `0x18010215c`
- `0x1801569f0`
- `0x1801aa66c`
- `0x1801bcd8c`
- `0x18064829c`
- `0x180648adc`
- `0x180648bb4`
- `0x180688f3e`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `GDI32!DeleteObject` at `0x180649128`
- `GDI32!DeleteObject` at `0x180649128`
- `GDI32!SelectObject` at `0x180649084`
- `GDI32!SelectObject` at `0x18064910b`
- `GDI32!SelectObject` at `0x180649084`
- `GDI32!SelectObject` at `0x18064910b`
- `GDI32!SetBkMode` at `0x180648f8f`
- `GDI32!SetBkMode` at `0x180648f8f`
- `GDI32!SetTextColor` at `0x180648f7f`
- `GDI32!SetTextColor` at `0x180648f7f`
- `GDI32!GetObjectW` at `0x180649052`
- `GDI32!GetObjectW` at `0x180649052`
- `GDI32!CreateFontIndirectW` at `0x180649070`
- `GDI32!CreateFontIndirectW` at `0x180649070`
- `USER32!GetSystemMetrics` at `0x180648c47`
- `USER32!GetSystemMetrics` at `0x180648c47`
- `USER32!ShowWindow` at `0x180648f1c`
- `USER32!ShowWindow` at `0x180648f1c`
- `USER32!SetWindowPos` at `0x180648ec6`
- `USER32!SetWindowPos` at `0x180648ec6`
- `USER32!LoadImageW` at `0x180648fb0`
- `USER32!LoadImageW` at `0x180648fb0`
- `USER32!DestroyIcon` at `0x18064911a`
- `USER32!DestroyIcon` at `0x18064911a`
- `USER32!DrawIconEx` at `0x18064902c`
- `USER32!DrawIconEx` at `0x18064902c`
- `USER32!GetClientRect` at `0x180648c5b`
- `USER32!GetClientRect` at `0x180648c5b`
- `USER32!SendMessageW` at `0x180649040`
- `USER32!SendMessageW` at `0x180649040`
- `USER32!DrawTextW` at `0x1806490c4`
- `USER32!DrawTextW` at `0x1806490fa`
- `USER32!DrawTextW` at `0x1806490c4`
- `USER32!DrawTextW` at `0x1806490fa`
- `USER32!GetSysColor` at `0x180648f74`
- `USER32!GetSysColor` at `0x180648f74`
- `OLEAUT32!__imp_VariantInit` at `0x180648c23`
- `OLEAUT32!__imp_VariantInit` at `0x180648c23`
- `OLE32!CoCreateInstance` at `0x180648d45`
- `OLE32!CoCreateInstance` at `0x180648d45`

## string_xrefs

- `0x180648dba`: `Failed to set banner accessible name`

## pseudocode

```c
__int64 __fastcall CDlgBase::DrawShieldBanner(__int64 a1, HDC a2, LONG a3, int a4, unsigned int a5, unsigned int a6)
{
  unsigned int v6; // ebx
  unsigned int v7; // r15d
  int SystemMetricsForDpi; // eax
  int v12; // edi
  LONG right; // r12d
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rdx
  int v18; // r15d
  unsigned int v19; // eax
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 (__fastcall *v22)(LPVOID, __int64, __int64, _QWORD, GUID *, __int128 *); // rax
  int v23; // r15d
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // ebx
  unsigned int v27; // ebx
  COLORREF SysColor; // edx
  HICON ImageW; // r12
  HFONT v30; // rdi
  unsigned int v31; // r13d
  HGDIOBJ v32; // r15
  void *v33; // rax
  CDlgBase *v34; // rcx
  HFONT v35; // rax
  LONG bottom; // ebx
  LPVOID v37; // rcx
  int cy[2]; // [rsp+28h] [rbp-D8h]
  int cya[2]; // [rsp+28h] [rbp-D8h]
  int v41; // [rsp+54h] [rbp-ACh]
  LPVOID ppv; // [rsp+58h] [rbp-A8h] BYREF
  int v43; // [rsp+60h] [rbp-A0h]
  int cchText; // [rsp+64h] [rbp-9Ch]
  struct tagRECT v45; // [rsp+68h] [rbp-98h] BYREF
  GUID v46; // [rsp+80h] [rbp-80h] BYREF
  VARIANTARG pvarg; // [rsp+90h] [rbp-70h] BYREF
  __int128 v48; // [rsp+B0h] [rbp-50h] BYREF
  IRecordInfo *pRecInfo; // [rsp+C0h] [rbp-40h]
  struct tagRECT rc; // [rsp+D0h] [rbp-30h] BYREF
  struct tagRECT Rect; // [rsp+E0h] [rbp-20h] BYREF
  struct tagLOGFONTW pv; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR chText[128]; // [rsp+150h] [rbp+50h] BYREF

  v6 = a6;
  v7 = 0;
  v43 = a4;
  memset_0(&pv, 0, sizeof(pv));
  ppv = 0;
  Rect = 0;
  rc = 0;
  VariantInit(&pvarg);
  if ( *(_DWORD *)(a1 + 64) )
    SystemMetricsForDpi = Win32DpiApi::GetSystemMetricsForDpi(*(Win32DpiApi **)(a1 + 56), 11, *(_DWORD *)(a1 + 68));
  else
    SystemMetricsForDpi = GetSystemMetrics(11);
  v12 = SystemMetricsForDpi;
  v41 = SystemMetricsForDpi;
  GetClientRect(*(HWND *)(a1 + 8), &Rect);
  right = Rect.right;
  v45.right = Rect.right;
  v45.bottom = a3;
  *(_QWORD *)&v45.left = 0;
  if ( a6 > 4 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_26668ec9d1183481e5fb81b64c4b74bc_Traceguids);
    }
    v6 = 1;
  }
  cchText = TSLoadString(*(HINSTANCE *)(a1 + 32), a5, chText, 128);
  if ( !cchText )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v15 = 31;
LABEL_15:
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v15,
        WPP_26668ec9d1183481e5fb81b64c4b74bc_Traceguids,
        CurrentThreadActivityIdPrefix);
      goto LABEL_54;
    }
    goto LABEL_54;
  }
  if ( CoCreateInstance(&CLSID_AccPropServices, 0, 0x15u, &GUID_6e26e776_04f0_495d_80e4_3330352e3169, &ppv) >= 0 )
  {
    v16 = *(_QWORD *)ppv;
    v17 = *(_QWORD *)(a1 + 24);
    v46 = PROPID_ACC_NAME;
    v18 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64, _QWORD, GUID *, WCHAR *))(v16 + 56))(
            ppv,
            v17,
            4294967292LL,
            0,
            &v46,
            chText);
    if ( v18 < 0
      && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v19 = RdpWppGetCurrentThreadActivityIdPrefix();
      cy[0] = v18;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        (unsigned int)WPP_26668ec9d1183481e5fb81b64c4b74bc_Traceguids,
        v19,
        (__int64)"Failed to set banner accessible name",
        *(_QWORD *)cy);
    }
    pvarg.vt = 3;
    pvarg.lVal = 41;
    v20 = *(_QWORD *)ppv;
    v21 = *(_QWORD *)(a1 + 24);
    v48 = *(_OWORD *)&pvarg.vt;
    v22 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64, _QWORD, GUID *, __int128 *))(v20 + 48);
    pRecInfo = pvarg.pRecInfo;
    v46 = PROPID_ACC_ROLE;
    v23 = v22(ppv, v21, 4294967292LL, 0, &v46, &v48);
    if ( v23 < 0
      && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v24 = RdpWppGetCurrentThreadActivityIdPrefix();
      cya[0] = v23;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        (unsigned int)WPP_26668ec9d1183481e5fb81b64c4b74bc_Traceguids,
        v24,
        (__int64)"SetHwndProp for PROPID_ACC_ROLE = ROLE_SYSTEM_STATICTEXT failed!",
        *(_QWORD *)cya);
    }
    v7 = 0;
  }
  if ( !SetWindowPos(*(HWND *)(a1 + 24), 0, 0, 0, right, a3, 2u)
    && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v25 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_26668ec9d1183481e5fb81b64c4b74bc_Traceguids, v25);
  }
  ShowWindow(*(HWND *)(a1 + 24), 5);
  if ( *(_DWORD *)(a1 + 52) )
  {
    SysColor = GetSysColor(8);
    goto LABEL_41;
  }
  CDlgBase::DrawGradientRectHorz(
    (CDlgBase *)&CDlgBase::_bannerGradients,
    a2,
    &v45,
    *((_DWORD *)&CDlgBase::_bannerGradients + 2 * v6),
    *((_DWORD *)&CDlgBase::_bannerGradients + 2 * v6 + 1));
  if ( !v6 )
    goto LABEL_39;
  v26 = v6 - 1;
  if ( v26 )
  {
    v27 = v26 - 1;
    if ( v27 )
    {
      if ( v27 - 1 > 1 )
        goto LABEL_42;
      goto LABEL_38;
    }
LABEL_39:
    SysColor = 0xFFFFFF;
    goto LABEL_41;
  }
LABEL_38:
  SysColor = 0;
LABEL_41:
  SetTextColor(a2, SysColor);
LABEL_42:
  SetBkMode(a2, 1);
  ImageW = (HICON)LoadImageW(*(HINSTANCE *)(a1 + 32), (LPCWSTR)(unsigned __int16)v43, 1u, v12, v12, 0);
  if ( ImageW )
  {
    v30 = 0;
    v31 = (unsigned int)(a3 - v41) >> 1;
    v32 = 0;
    DrawIconEx(a2, v31, v31, ImageW, 0, 0, 0, 0, 3u);
    v33 = (void *)SendMessageW(*(HWND *)(a1 + 8), 0x31u, 0, 0);
    if ( GetObjectW(v33, 92, &pv) )
    {
      pv.lfWeight = 700;
      CDlgBase::AdjustLOGFONT(v34, &pv);
      v35 = CreateFontIndirectW(&pv);
      v30 = v35;
      if ( v35 )
        v32 = SelectObject(a2, v35);
    }
    bottom = v45.bottom;
    rc.left = v41 + 2 * v31;
    rc.top = 0;
    rc.right = v45.right - v31;
    rc.bottom = v45.bottom;
    DrawTextW(a2, chText, cchText, &rc, 0x510u);
    rc.top = (bottom - rc.bottom) / 2;
    rc.bottom += rc.top;
    DrawTextW(a2, chText, cchText, &rc, 0x10u);
    if ( v32 )
      SelectObject(a2, v32);
    v7 = 1;
    DestroyIcon(ImageW);
    if ( v30 )
      DeleteObject(v30);
  }
  else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
         && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v15 = 35;
    goto LABEL_15;
  }
LABEL_54:
  wil::details::close_invoke_helper<1,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),tagVARIANT *>::close(&pvarg);
  v37 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v37 + 16LL))(v37);
  }
  return v7;
}

```

## disassembly

```asm
0x180648bb4  push    rbp
0x180648bb6  push    rbx
0x180648bb7  push    rsi
0x180648bb8  push    rdi
0x180648bb9  push    r12
0x180648bbb  push    r13
0x180648bbd  push    r14
0x180648bbf  push    r15
0x180648bc1  lea     rbp, [rsp-168h]
0x180648bc9  sub     rsp, 268h
0x180648bd0  mov     rax, cs:__security_cookie
0x180648bd7  xor     rax, rsp
0x180648bda  mov     [rbp+1A0h+var_50], rax
0x180648be1  mov     ebx, [rbp+1A0h+arg_28]
0x180648be7  xor     r15d, r15d
0x180648bea  mov     r13d, r8d
0x180648bed  mov     [rsp+2A0h+var_240], r9d
0x180648bf2  mov     r14, rdx
0x180648bf5  mov     [rsp+2A0h+var_250], r15d
0x180648bfa  mov     rsi, rcx
0x180648bfd  xor     edx, edx; Val
0x180648bff  lea     r8d, [r15+5Ch]; Size
0x180648c03  lea     rcx, [rbp+1A0h+pv]; void *
0x180648c07  call    memset_0
0x180648c0c  xorps   xmm0, xmm0
0x180648c0f  mov     [rsp+2A0h+var_248], r15
0x180648c14  xorps   xmm1, xmm1
0x180648c17  lea     rcx, [rbp+1A0h+pvarg]; pvarg
0x180648c1b  movups  xmmword ptr [rbp+1A0h+Rect.left], xmm0
0x180648c1f  movups  xmmword ptr [rbp+1A0h+rc.left], xmm1
0x180648c23  call    cs:__imp_VariantInit
0x180648c29  cmp     [rsi+40h], r15d
0x180648c2d  jz      short loc_180648C42
0x180648c2f  mov     r8d, [rsi+44h]; unsigned int
0x180648c33  lea     edx, [r15+0Bh]; int
0x180648c37  mov     rcx, [rsi+38h]; this
0x180648c3b  call    ?GetSystemMetricsForDpi@Win32DpiApi@@QEAAHHI@Z; Win32DpiApi::GetSystemMetricsForDpi(int,uint)
0x180648c40  jmp     short loc_180648C4D
0x180648c42  mov     ecx, 0Bh; nIndex
0x180648c47  call    cs:__imp_GetSystemMetrics
0x180648c4d  mov     rcx, [rsi+8]; hWnd
0x180648c51  lea     rdx, [rbp+1A0h+Rect]; lpRect
0x180648c55  mov     edi, eax
0x180648c57  mov     [rsp+2A0h+var_24C], eax
0x180648c5b  call    cs:__imp_GetClientRect
0x180648c61  mov     r12d, [rbp+1A0h+Rect.right]
0x180648c65  lea     rax, WPP_GLOBAL_Control
0x180648c6c  mov     [rsp+2A0h+var_238.right], r12d
0x180648c71  mov     [rsp+2A0h+var_238.bottom], r13d
0x180648c76  mov     qword ptr [rsp+2A0h+var_238.left], r15
0x180648c7b  cmp     ebx, 4
0x180648c7e  jbe     short loc_180648CB2
0x180648c80  mov     rcx, cs:WPP_GLOBAL_Control
0x180648c87  cmp     rcx, rax
0x180648c8a  jz      short loc_180648CAD
0x180648c8c  test    byte ptr [rcx+1Ch], 1
0x180648c90  jz      short loc_180648CAD
0x180648c92  cmp     byte ptr [rcx+19h], 1
0x180648c96  jb      short loc_180648CAD
0x180648c98  mov     rcx, [rcx+10h]
0x180648c9c  lea     r8, WPP_26668ec9d1183481e5fb81b64c4b74bc_Traceguids
0x180648ca3  mov     edx, 1Eh
0x180648ca8  call    WPP_SF_
0x180648cad  mov     ebx, 1
0x180648cb2  mov     edx, [rbp+1A0h+arg_20]; unsigned int
0x180648cb8  lea     r8, [rbp+1A0h+chText]; unsigned __int16 *
0x180648cbc  mov     rcx, [rsi+20h]; HINSTANCE
0x180648cc0  mov     r9d, 80h; int
0x180648cc6  call    ?TSLoadString@@YAHPEAUHINSTANCE__@@IPEAGH@Z; TSLoadString(HINSTANCE__ *,uint,ushort *,int)
0x180648ccb  mov     [rsp+2A0h+cchText], eax
0x180648ccf  test    eax, eax
0x180648cd1  jnz     short loc_180648D27
0x180648cd3  mov     rax, cs:WPP_GLOBAL_Control
0x180648cda  lea     rcx, WPP_GLOBAL_Control
0x180648ce1  cmp     rax, rcx
0x180648ce4  jz      loc_18064912E
0x180648cea  test    byte ptr [rax+1Ch], 1
0x180648cee  jz      loc_18064912E
0x180648cf4  cmp     byte ptr [rax+19h], 2
0x180648cf8  jb      loc_18064912E
0x180648cfe  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180648d03  mov     edx, 1Fh
0x180648d08  mov     rcx, cs:WPP_GLOBAL_Control
0x180648d0f  lea     r8, WPP_26668ec9d1183481e5fb81b64c4b74bc_Traceguids
0x180648d16  mov     r9d, eax
0x180648d19  mov     rcx, [rcx+10h]
0x180648d1d  call    WPP_SF_d
0x180648d22  jmp     loc_18064912E
0x180648d27  xor     edx, edx; pUnkOuter
0x180648d29  lea     rax, [rsp+2A0h+var_248]
0x180648d2e  lea     r9, _GUID_6e26e776_04f0_495d_80e4_3330352e3169; riid
0x180648d35  mov     [rsp+2A0h+ppv], rax; ppv
0x180648d3a  lea     rcx, CLSID_AccPropServices; rclsid
0x180648d41  lea     r8d, [rdx+15h]; dwClsContext
0x180648d45  call    cs:__imp_CoCreateInstance
0x180648d4b  test    eax, eax
0x180648d4d  js      loc_180648EA8
0x180648d53  mov     rcx, [rsp+2A0h+var_248]
0x180648d58  lea     rdx, [rbp+1A0h+chText]
0x180648d5c  movups  xmm0, xmmword ptr cs:PROPID_ACC_NAME.Data1
0x180648d63  mov     qword ptr [rsp+2A0h+cy], rdx
0x180648d68  xor     r9d, r9d
0x180648d6b  lea     rdx, [rbp+1A0h+var_220]
0x180648d6f  mov     r8d, 0FFFFFFFCh
0x180648d75  mov     rax, [rcx]
0x180648d78  mov     [rsp+2A0h+ppv], rdx
0x180648d7d  mov     rdx, [rsi+18h]
0x180648d81  movdqu  [rbp+1A0h+var_220], xmm0
0x180648d86  mov     rax, [rax+38h]
0x180648d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180648d8f  mov     r15d, eax
0x180648d92  test    eax, eax
0x180648d94  jns     short loc_180648DEA
0x180648d96  mov     rax, cs:WPP_GLOBAL_Control
0x180648d9d  lea     rcx, WPP_GLOBAL_Control
0x180648da4  cmp     rax, rcx
0x180648da7  jz      short loc_180648DEA
0x180648da9  test    byte ptr [rax+1Ch], 8
0x180648dad  jz      short loc_180648DEA
0x180648daf  cmp     byte ptr [rax+19h], 2
0x180648db3  jb      short loc_180648DEA
0x180648db5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180648dba  lea     rcx, aFailedToSetBan; "Failed to set banner accessible name"
0x180648dc1  mov     [rsp+2A0h+cy], r15d
0x180648dc6  mov     [rsp+2A0h+ppv], rcx
0x180648dcb  lea     r8, WPP_26668ec9d1183481e5fb81b64c4b74bc_Traceguids
0x180648dd2  mov     rcx, cs:WPP_GLOBAL_Control
0x180648dd9  mov     edx, 20h ; ' '
0x180648dde  mov     r9d, eax
0x180648de1  mov     rcx, [rcx+10h]
0x180648de5  call    WPP_SF_DsD
0x180648dea  mov     rcx, [rsp+2A0h+var_248]
0x180648def  lea     rdx, [rbp+1A0h+var_1F0]
0x180648df3  movsd   xmm1, qword ptr [rbp+1A0h+pvarg+10h]
0x180648df8  mov     eax, 3
0x180648dfd  mov     word ptr [rbp+1A0h+pvarg], ax
0x180648e01  xor     r9d, r9d
0x180648e04  mov     qword ptr [rsp+2A0h+cy], rdx
0x180648e09  mov     r8d, 0FFFFFFFCh
0x180648e0f  mov     dword ptr [rbp+1A0h+pvarg+8], 29h ; ')'
0x180648e16  lea     rdx, [rbp+1A0h+var_220]
0x180648e1a  movups  xmm0, xmmword ptr [rbp+1A0h+pvarg]
0x180648e1e  mov     rax, [rcx]
0x180648e21  mov     [rsp+2A0h+ppv], rdx
0x180648e26  mov     rdx, [rsi+18h]
0x180648e2a  movaps  [rbp+1A0h+var_1F0], xmm0
0x180648e2e  movups  xmm0, xmmword ptr cs:PROPID_ACC_ROLE.Data1
0x180648e35  mov     rax, [rax+30h]
0x180648e39  movsd   [rbp+1A0h+var_1E0], xmm1
0x180648e3e  movdqu  [rbp+1A0h+var_220], xmm0
0x180648e43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180648e48  mov     r15d, eax
0x180648e4b  test    eax, eax
0x180648e4d  jns     short loc_180648EA3
0x180648e4f  mov     rax, cs:WPP_GLOBAL_Control
0x180648e56  lea     rcx, WPP_GLOBAL_Control
0x180648e5d  cmp     rax, rcx
0x180648e60  jz      short loc_180648EA3
0x180648e62  test    byte ptr [rax+1Ch], 8
0x180648e66  jz      short loc_180648EA3
0x180648e68  cmp     byte ptr [rax+19h], 2
0x180648e6c  jb      short loc_180648EA3
0x180648e6e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180648e73  lea     rcx, aSethwndpropFor; "SetHwndProp for PROPID_ACC_ROLE = ROLE_"...
0x180648e7a  mov     [rsp+2A0h+cy], r15d
0x180648e7f  mov     [rsp+2A0h+ppv], rcx
0x180648e84  lea     r8, WPP_26668ec9d1183481e5fb81b64c4b74bc_Traceguids
0x180648e8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180648e92  mov     edx, 21h ; '!'
0x180648e97  mov     r9d, eax
0x180648e9a  mov     rcx, [rcx+10h]
0x180648e9e  call    WPP_SF_DsD
0x180648ea3  mov     r15d, [rsp+2A0h+var_250]
0x180648ea8  mov     rcx, [rsi+18h]; hWnd
0x180648eac  xor     r9d, r9d; Y
0x180648eaf  mov     [rsp+2A0h+uFlags], 2; uFlags
0x180648eb7  xor     r8d, r8d; X
0x180648eba  mov     [rsp+2A0h+cy], r13d; cy
0x180648ebf  xor     edx, edx; hWndInsertAfter
0x180648ec1  mov     dword ptr [rsp+2A0h+ppv], r12d; cx
0x180648ec6  call    cs:__imp_SetWindowPos
0x180648ecc  test    eax, eax
0x180648ece  jnz     short loc_180648F13
0x180648ed0  mov     rax, cs:WPP_GLOBAL_Control
0x180648ed7  lea     rcx, WPP_GLOBAL_Control
0x180648ede  cmp     rax, rcx
0x180648ee1  jz      short loc_180648F13
0x180648ee3  test    byte ptr [rax+1Ch], 1
0x180648ee7  jz      short loc_180648F13
0x180648ee9  cmp     byte ptr [rax+19h], 2
0x180648eed  jb      short loc_180648F13
0x180648eef  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180648ef4  mov     rcx, cs:WPP_GLOBAL_Control
0x180648efb  lea     r8, WPP_26668ec9d1183481e5fb81b64c4b74bc_Traceguids
0x180648f02  mov     edx, 22h ; '"'
0x180648f07  mov     r9d, eax
0x180648f0a  mov     rcx, [rcx+10h]
0x180648f0e  call    WPP_SF_d
0x180648f13  mov     rcx, [rsi+18h]; hWnd
0x180648f17  mov     edx, 5; nCmdShow
0x180648f1c  call    cs:__imp_ShowWindow
0x180648f22  cmp     dword ptr [rsi+34h], 0
0x180648f26  jnz     short loc_180648F6F
0x180648f28  mov     r9d, ebx
0x180648f2b  lea     rcx, ?_bannerGradients@CDlgBase@@1QBU_BANNER_GRADIENT@1@B; this
0x180648f32  lea     r8, [rsp+2A0h+var_238]; struct tagRECT *
0x180648f37  mov     rdx, r14; HDC
0x180648f3a  mov     eax, [rcx+r9*8+4]
0x180648f3f  mov     r9d, [rcx+r9*8]; unsigned int
0x180648f43  mov     dword ptr [rsp+2A0h+ppv], eax; unsigned int
0x180648f47  call    ?DrawGradientRectHorz@CDlgBase@@IEAAXPEAUHDC__@@AEBUtagRECT@@KK@Z; CDlgBase::DrawGradientRectHorz(HDC__ *,tagRECT const &,ulong,ulong)
0x180648f4c  test    ebx, ebx
0x180648f4e  jz      short loc_180648F68
0x180648f50  sub     ebx, 1
0x180648f53  jz      short loc_180648F64
0x180648f55  sub     ebx, 1
0x180648f58  jz      short loc_180648F68
0x180648f5a  sub     ebx, 1
0x180648f5d  jz      short loc_180648F64
0x180648f5f  cmp     ebx, 1
0x180648f62  jnz     short loc_180648F85
0x180648f64  xor     edx, edx
0x180648f66  jmp     short loc_180648F7C
0x180648f68  mov     edx, 0FFFFFFh
0x180648f6d  jmp     short loc_180648F7C
0x180648f6f  mov     ecx, 8; nIndex
0x180648f74  call    cs:__imp_GetSysColor
0x180648f7a  mov     edx, eax; color
0x180648f7c  mov     rcx, r14; hdc
0x180648f7f  call    cs:__imp_SetTextColor
0x180648f85  mov     ebx, 1
0x180648f8a  mov     rcx, r14; hdc
0x180648f8d  mov     edx, ebx; mode
0x180648f8f  call    cs:__imp_SetBkMode
0x180648f95  movzx   edx, word ptr [rsp+2A0h+var_240]; name
0x180648f9a  mov     r9d, edi; cx
0x180648f9d  mov     rcx, [rsi+20h]; hInst
0x180648fa1  mov     r8d, ebx; type
0x180648fa4  mov     [rsp+2A0h+cy], 0; fuLoad
0x180648fac  mov     dword ptr [rsp+2A0h+ppv], edi; cy
0x180648fb0  call    cs:__imp_LoadImageW
0x180648fb6  mov     r12, rax
0x180648fb9  xor     eax, eax
0x180648fbb  test    r12, r12
0x180648fbe  jnz     short loc_180648FF7
0x180648fc0  mov     rax, cs:WPP_GLOBAL_Control
0x180648fc7  lea     rcx, WPP_GLOBAL_Control
0x180648fce  cmp     rax, rcx
0x180648fd1  jz      loc_18064912E
0x180648fd7  test    [rax+1Ch], bl
0x180648fda  jz      loc_18064912E
0x180648fe0  cmp     byte ptr [rax+19h], 2
0x180648fe4  jb      loc_18064912E
0x180648fea  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180648fef  lea     edx, [rbx+22h]
0x180648ff2  jmp     loc_180648D08
0x180648ff7  mov     ebx, [rsp+2A0h+var_24C]
0x180648ffb  mov     r9, r12; hIcon
0x180648ffe  mov     [rsp+2A0h+diFlags], 3; diFlags
0x180649006  sub     r13d, ebx
0x180649009  mov     [rsp+2A0h+hbrFlickerFreeDraw], rax; hbrFlickerFreeDraw
0x18064900e  mov     rcx, r14; hdc
0x180649011  mov     [rsp+2A0h+uFlags], eax; istepIfAniCur
0x180649015  mov     rdi, rax
0x180649018  shr     r13d, 1
0x18064901b  mov     r15, rax
0x18064901e  mov     [rsp+2A0h+cy], eax; cyWidth
0x180649022  mov     r8d, r13d; yTop
0x180649025  mov     edx, r13d; xLeft
0x180649028  mov     dword ptr [rsp+2A0h+ppv], eax; cxWidth
0x18064902c  call    cs:__imp_DrawIconEx
0x180649032  mov     rcx, [rsi+8]; hWnd
0x180649036  xor     r9d, r9d; lParam
0x180649039  xor     r8d, r8d; wParam
0x18064903c  lea     edx, [r9+31h]; Msg
0x180649040  call    cs:__imp_SendMessageW
0x180649046  lea     r8, [rbp+1A0h+pv]; pv
0x18064904a  mov     edx, 5Ch ; '\'; c
0x18064904f  mov     rcx, rax; h
0x180649052  call    cs:__imp_GetObjectW
0x180649058  test    eax, eax
0x18064905a  jz      short loc_18064908D
0x18064905c  lea     rdx, [rbp+1A0h+pv]; struct tagLOGFONTW *
0x180649060  mov     [rbp+1A0h+var_1A0], 2BCh
0x180649067  call    ?AdjustLOGFONT@CDlgBase@@IEAAXPEAUtagLOGFONTW@@@Z; CDlgBase::AdjustLOGFONT(tagLOGFONTW *)
0x18064906c  lea     rcx, [rbp+1A0h+pv]; lplf
0x180649070  call    cs:__imp_CreateFontIndirectW
0x180649076  mov     rdi, rax
0x180649079  test    rax, rax
0x18064907c  jz      short loc_18064908D
0x18064907e  mov     rdx, rax; h
0x180649081  mov     rcx, r14; hdc
0x180649084  call    cs:__imp_SelectObject
0x18064908a  mov     r15, rax
0x18064908d  mov     r8d, [rsp+2A0h+cchText]; cchText
0x180649092  lea     eax, [rbx+r13*2]
0x180649096  mov     ebx, [rsp+2A0h+var_238.bottom]
0x18064909a  lea     r9, [rbp+1A0h+rc]; lprc
0x18064909e  mov     [rbp+1A0h+rc.left], eax
0x1806490a1  lea     rdx, [rbp+1A0h+chText]; lpchText
  ... truncated ...
```
