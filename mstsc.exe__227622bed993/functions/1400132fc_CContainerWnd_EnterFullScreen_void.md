# CContainerWnd::EnterFullScreen(void)

- ea: `0x1400132fc`
- end: `0x140013993`
- name: `?EnterFullScreen@CContainerWnd@@AEAAXXZ`
- size: `1687`
- prototype: `void __fastcall(CContainerWnd *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x140017538`
- `0x140022110`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x14000d078`
- `0x1400132fc`
- `0x1400148ec`
- `0x14001e7ec`
- `0x140027dd0`
- `0x140027fc8`
- `0x140028690`
- `0x14009ea34`
- `0x140111220`
- `0x140112010`

## import_xrefs

- `USER32!SetWindowRgn` at `0x1400138e4`
- `USER32!SetWindowRgn` at `0x1400138e4`
- `USER32!SetWindowLongW` at `0x1400134f9`
- `USER32!SetWindowLongW` at `0x14001350a`
- `USER32!SetWindowLongW` at `0x1400134f9`
- `USER32!SetWindowLongW` at `0x14001350a`
- `USER32!LockWindowUpdate` at `0x140013464`
- `USER32!LockWindowUpdate` at `0x1400138ec`
- `USER32!LockWindowUpdate` at `0x140013464`
- `USER32!LockWindowUpdate` at `0x1400138ec`
- `USER32!ShowWindow` at `0x1400138a4`
- `USER32!ShowWindow` at `0x1400138a4`
- `USER32!GetWindowLongW` at `0x1400134e2`
- `USER32!GetWindowLongW` at `0x1400134e2`
- `USER32!SetWindowPos` at `0x1400138d4`
- `USER32!SetWindowPos` at `0x1400138d4`
- `USER32!GetWindowPlacement` at `0x1400134b0`
- `USER32!GetWindowPlacement` at `0x1400134b0`
- `USER32!IsIconic` at `0x14001349e`
- `USER32!IsIconic` at `0x14001349e`
- `GDI32!OffsetRgn` at `0x1400137b8`
- `GDI32!OffsetRgn` at `0x1400137b8`
- `GDI32!GetRgnBox` at `0x1400137a3`
- `GDI32!GetRgnBox` at `0x1400137a3`
- `OLEAUT32!__imp_VariantInit` at `0x140013538`
- `OLEAUT32!__imp_VariantInit` at `0x140013538`
- `OLEAUT32!__imp_VariantClear` at `0x1400135ce`
- `OLEAUT32!__imp_VariantClear` at `0x1400137de`
- `OLEAUT32!__imp_VariantClear` at `0x1400135ce`
- `OLEAUT32!__imp_VariantClear` at `0x1400137de`

## pseudocode

```c
void __fastcall CContainerWnd::EnterFullScreen(CContainerWnd *this)
{
  __int64 (__fastcall ***v2)(_QWORD, GUID *, __int64 *); // rcx
  HRGN v3; // r14
  __int64 (__fastcall **v4)(_QWORD, GUID *, __int64 *); // rax
  int v5; // eax
  char v6; // di
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v8; // edx
  const char *v9; // rcx
  int v10; // eax
  int v11; // edi
  __int64 v12; // rsi
  __int64 v13; // rsi
  HWND v14; // rcx
  __int64 v15; // rax
  LONG WindowLongW; // eax
  int v17; // eax
  char v18; // di
  unsigned int v19; // eax
  int v20; // edx
  const char *v21; // rcx
  __int64 v22; // rcx
  int v23; // eax
  char v24; // si
  unsigned int v25; // eax
  __int64 (__fastcall ***v26)(_QWORD, GUID *, int *); // rcx
  int v27; // eax
  int v28; // eax
  struct IRdpMonitorList *v29; // rdi
  int SelectedMonitorRegion; // eax
  __int64 v31; // rcx
  __int64 v32; // rcx
  unsigned int v33; // eax
  __int64 v34; // rcx
  int v35[2]; // [rsp+40h] [rbp-49h] BYREF
  __int16 v36; // [rsp+48h] [rbp-41h] BYREF
  __int64 v37; // [rsp+50h] [rbp-39h] BYREF
  unsigned int v38; // [rsp+58h] [rbp-31h] BYREF
  HRGN hrgn; // [rsp+60h] [rbp-29h] BYREF
  int X[4]; // [rsp+68h] [rbp-21h] BYREF
  struct tagRECT rc; // [rsp+78h] [rbp-11h] BYREF
  WINDOWPLACEMENT wndpl; // [rsp+88h] [rbp-1h] BYREF

  v37 = 0;
  v2 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 15);
  v38 = 0;
  *(_OWORD *)X = 0;
  v36 = 0;
  v3 = 0;
  v4 = *v2;
  hrgn = 0;
  v5 = (*v4)(v2, &IID_IMsRdpClientNonScriptable5, &v37);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_63;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v8 = 202;
    v9 = "QI for IID_IMsRdpClientNonScriptable5 failed!";
    goto LABEL_6;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v37 + 440LL))(v37, &v38);
  v6 = v10;
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_63;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v8 = 203;
    v9 = "get_RemoteMonitorCount failed!";
LABEL_6:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      (unsigned int)&WPP_c53b5e828c42300d429425e15b0600ad_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v9,
      v6);
    goto LABEL_63;
  }
  if ( v38 > 1 || (unsigned int)CTscSettings::HasSelectedMonitors(*((CTscSettings **)this + 95)) )
  {
    v11 = 1;
    v23 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v37 + 456LL))(v37, &v36);
    v24 = v23;
    if ( v23 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v25 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          204,
          (unsigned int)&WPP_c53b5e828c42300d429425e15b0600ad_Traceguids,
          v25,
          (__int64)"get_RemoteMonitorLayoutMatchesLocal failed!",
          v24);
      }
      goto LABEL_63;
    }
  }
  else
  {
    v11 = 0;
  }
  *(_DWORD *)(*((_QWORD *)this + 95) + 201344LL) = 1;
  LockWindowUpdate(*((HWND *)this + 1));
  v12 = *((_QWORD *)this + 95);
  *((_DWORD *)this + 28) = 1;
  v13 = v12 + 64;
  if ( v13 )
  {
    if ( *((_DWORD *)this + 192) )
    {
      v14 = (HWND)*((_QWORD *)this + 1);
      memset(&wndpl, 0, sizeof(wndpl));
      wndpl.length = 44;
      if ( !IsIconic(v14) )
      {
        if ( GetWindowPlacement(*((HWND *)this + 1), &wndpl) )
        {
          v15 = *((_QWORD *)this + 95);
          *(_OWORD *)(v15 + 64) = *(_OWORD *)&wndpl.length;
          *(_OWORD *)(v15 + 80) = *(_OWORD *)&wndpl.ptMinPosition.y;
          *(RECT *)(v15 + 92) = wndpl.rcNormalPosition;
        }
      }
    }
  }
  WindowLongW = GetWindowLongW(*((HWND *)this + 1), -16);
  SetWindowLongW(*((HWND *)this + 1), -16, WindowLongW & 0xFF3AFFFF);
  SetWindowLongW(*((HWND *)this + 1), -12, 0);
  *((_DWORD *)this + 470) = 0;
  *((_DWORD *)this + 471) = v11;
  if ( v11 && v36 )
  {
    *(_QWORD *)v35 = 0;
    VariantInit((VARIANTARG *)&wndpl);
    rc = 0;
    v17 = (*(__int64 (__fastcall **)(__int64, int *, int *, int *, int *))(*(_QWORD *)v37 + 448LL))(
            v37,
            X,
            &X[1],
            &X[2],
            &X[3]);
    v18 = v17;
    if ( v17 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 205;
        v21 = "GetRemoteMonitorsBoundingBox failed";
LABEL_28:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v20,
          (unsigned int)&WPP_c53b5e828c42300d429425e15b0600ad_Traceguids,
          v19,
          (__int64)v21,
          v18);
        goto LABEL_29;
      }
      goto LABEL_29;
    }
    v26 = (__int64 (__fastcall ***)(_QWORD, GUID *, int *))*((_QWORD *)this + 15);
    ++X[2];
    ++X[3];
    v27 = (**v26)(v26, &IID_IMsRdpExtendedSettings, v35);
    v18 = v27;
    if ( v27 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 206;
        v21 = "QueryInterface failed for IMsRdpExtendedSettings";
        goto LABEL_28;
      }
LABEL_29:
      VariantClear((VARIANTARG *)&wndpl);
      v22 = *(_QWORD *)v35;
      if ( *(_QWORD *)v35 )
      {
        *(_QWORD *)v35 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      }
      goto LABEL_63;
    }
    v28 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, WINDOWPLACEMENT *))(**(_QWORD **)v35 + 32LL))(
            *(_QWORD *)v35,
            L"SelectedMonitors",
            &wndpl);
    v18 = v28;
    if ( v28 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 207;
        v21 = "get_Property (UTREG_UI_SELECTED_MONITORS) failed";
        goto LABEL_28;
      }
      goto LABEL_29;
    }
    v29 = *(struct IRdpMonitorList **)&wndpl.showCmd;
    if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)&wndpl.showCmd + 24LL))(*(_QWORD *)&wndpl.showCmd) )
    {
      SelectedMonitorRegion = CSH::GetSelectedMonitorRegion(v29, &hrgn);
      v18 = SelectedMonitorRegion;
      if ( SelectedMonitorRegion < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v19 = RdpWppGetCurrentThreadActivityIdPrefix();
          v20 = 208;
          v21 = "GetSelectedMonitorRegion failed";
          goto LABEL_28;
        }
        goto LABEL_29;
      }
      v3 = hrgn;
      GetRgnBox(hrgn, &rc);
      OffsetRgn(v3, -rc.left, -rc.top);
      X[2] += rc.left - X[0];
      X[3] += rc.top - X[1];
      X[0] = rc.left;
      X[1] = rc.top;
    }
    VariantClear((VARIANTARG *)&wndpl);
    v31 = *(_QWORD *)v35;
    if ( *(_QWORD *)v35 )
    {
      *(_QWORD *)v35 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
  }
  else
  {
    v32 = *((_QWORD *)this + 15);
    v35[0] = 0;
    LODWORD(hrgn) = 0;
    (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v32 + 152LL))(v32, v35);
    (*(void (__fastcall **)(_QWORD, HRGN *))(**((_QWORD **)this + 15) + 168LL))(*((_QWORD *)this + 15), &hrgn);
    if ( (unsigned int)CSH::FullScreenSpansMonitors(v35[0], (int)hrgn) )
    {
      X[0] = xGetSystemMetrics(76);
      X[1] = xGetSystemMetrics(77);
      X[2] = X[0] + xGetSystemMetrics(78);
      X[3] = X[1] + xGetSystemMetrics(79);
      *((_DWORD *)this + 470) = 1;
    }
    else
    {
      CSH::MonitorRectFromNearestRect((LPCRECT)(v13 + 28), (LPRECT)X);
    }
  }
  ShowWindow(*((HWND *)this + 1), 9);
  SetWindowPos(*((HWND *)this + 1), 0, X[0], X[1], X[2] - X[0], X[3] - X[1], 0x30u);
  SetWindowRgn(*((HWND *)this + 1), v3, 1);
  LockWindowUpdate(0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v33 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 209, &WPP_c53b5e828c42300d429425e15b0600ad_Traceguids, v33);
  }
  CClientUtilsWin32::NotifyShellOfFullScreen(
    *((HWND *)this + 1),
    1,
    (struct ITaskbarList2 **)this + 229,
    (int *)this + 460);
LABEL_63:
  v34 = v37;
  if ( v37 )
  {
    v37 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  }
}

```

## disassembly

```asm
0x1400132fc  mov     [rsp-8+arg_8], rbx
0x140013301  mov     [rsp-8+arg_10], rsi
0x140013306  push    rbp
0x140013307  push    rdi
0x140013308  push    r12
0x14001330a  push    r13
0x14001330c  push    r14
0x14001330e  lea     rbp, [rsp-37h]
0x140013313  sub     rsp, 0C0h
0x14001331a  mov     rax, cs:__security_cookie
0x140013321  xor     rax, rsp
0x140013324  mov     [rbp+57h+var_28], rax
0x140013328  xor     r12d, r12d
0x14001332b  lea     r8, [rbp+57h+var_90]
0x14001332f  mov     rbx, rcx
0x140013332  mov     [rbp+57h+var_90], r12
0x140013336  mov     rcx, [rcx+78h]
0x14001333a  lea     rdx, IID_IMsRdpClientNonScriptable5
0x140013341  xorps   xmm0, xmm0
0x140013344  mov     [rbp+57h+var_88], r12d
0x140013348  movups  xmmword ptr [rbp+57h+X], xmm0
0x14001334c  mov     [rbp+57h+var_98], r12w
0x140013351  mov     r14d, r12d
0x140013354  mov     rax, [rcx]
0x140013357  mov     [rbp+57h+hrgn], r12
0x14001335b  mov     rax, [rax]
0x14001335e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013363  mov     edi, eax
0x140013365  test    eax, eax
0x140013367  jns     short loc_1400133CD
0x140013369  mov     rdx, cs:WPP_GLOBAL_Control
0x140013370  lea     rcx, WPP_GLOBAL_Control
0x140013377  cmp     rdx, rcx
0x14001337a  jz      loc_140013952
0x140013380  test    byte ptr [rdx+1Ch], 8
0x140013384  jz      loc_140013952
0x14001338a  cmp     byte ptr [rdx+19h], 2
0x14001338e  jb      loc_140013952
0x140013394  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140013399  mov     edx, 0CAh
0x14001339e  lea     rcx, aQiForIidImsrdp_5; "QI for IID_IMsRdpClientNonScriptable5 f"...
0x1400133a5  mov     [rsp+0E0h+cy], edi
0x1400133a9  mov     qword ptr [rsp+0E0h+var_C0], rcx
0x1400133ae  lea     r8, WPP_c53b5e828c42300d429425e15b0600ad_Traceguids
0x1400133b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400133bc  mov     r9d, eax
0x1400133bf  mov     rcx, [rcx+10h]
0x1400133c3  call    WPP_SF_DsD
0x1400133c8  jmp     loc_140013952
0x1400133cd  mov     rcx, [rbp+57h+var_90]
0x1400133d1  lea     rdx, [rbp+57h+var_88]
0x1400133d5  mov     rax, [rcx]
0x1400133d8  mov     rax, [rax+1B8h]
0x1400133df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400133e4  mov     edi, eax
0x1400133e6  test    eax, eax
0x1400133e8  jns     short loc_14001342B
0x1400133ea  mov     rdx, cs:WPP_GLOBAL_Control
0x1400133f1  lea     rcx, WPP_GLOBAL_Control
0x1400133f8  cmp     rdx, rcx
0x1400133fb  jz      loc_140013952
0x140013401  test    byte ptr [rdx+1Ch], 8
0x140013405  jz      loc_140013952
0x14001340b  cmp     byte ptr [rdx+19h], 2
0x14001340f  jb      loc_140013952
0x140013415  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14001341a  mov     edx, 0CBh
0x14001341f  lea     rcx, aGetRemotemonit; "get_RemoteMonitorCount failed!"
0x140013426  jmp     loc_1400133A5
0x14001342b  mov     r13d, 1
0x140013431  cmp     [rbp+57h+var_88], r13d
0x140013435  ja      loc_1400135F6
0x14001343b  mov     rcx, [rbx+2F8h]; this
0x140013442  call    ?HasSelectedMonitors@CTscSettings@@QEBAHXZ; CTscSettings::HasSelectedMonitors(void)
0x140013447  test    eax, eax
0x140013449  jnz     loc_1400135F6
0x14001344f  mov     edi, r12d
0x140013452  mov     rax, [rbx+2F8h]
0x140013459  mov     [rax+31280h], r13d
0x140013460  mov     rcx, [rbx+8]; hWndLock
0x140013464  call    cs:__imp_LockWindowUpdate
0x14001346a  mov     rsi, [rbx+2F8h]
0x140013471  mov     [rbx+70h], r13d
0x140013475  add     rsi, 40h ; '@'
0x140013479  jz      short loc_1400134D9
0x14001347b  cmp     [rbx+300h], r12d
0x140013482  jz      short loc_1400134D9
0x140013484  mov     rcx, [rbx+8]; hWnd
0x140013488  xorps   xmm0, xmm0
0x14001348b  movups  xmmword ptr [rbp+57h+wndpl.length], xmm0
0x14001348f  mov     [rbp+57h+wndpl.length], 2Ch ; ','
0x140013496  movups  xmmword ptr [rbp+57h+wndpl.ptMinPosition.y], xmm0
0x14001349a  movups  xmmword ptr [rbp+57h+wndpl.rcNormalPosition.left], xmm0
0x14001349e  call    cs:__imp_IsIconic
0x1400134a4  test    eax, eax
0x1400134a6  jnz     short loc_1400134D9
0x1400134a8  mov     rcx, [rbx+8]; hWnd
0x1400134ac  lea     rdx, [rbp+57h+wndpl]; lpwndpl
0x1400134b0  call    cs:__imp_GetWindowPlacement
0x1400134b6  test    eax, eax
0x1400134b8  jz      short loc_1400134D9
0x1400134ba  movups  xmm0, xmmword ptr [rbp+57h+wndpl.length]
0x1400134be  mov     rax, [rbx+2F8h]
0x1400134c5  movups  xmmword ptr [rax+40h], xmm0
0x1400134c9  movups  xmm1, xmmword ptr [rbp+57h+wndpl.ptMinPosition.y]
0x1400134cd  movups  xmmword ptr [rax+50h], xmm1
0x1400134d1  movups  xmm0, xmmword ptr [rbp+57h+wndpl.rcNormalPosition.left]
0x1400134d5  movups  xmmword ptr [rax+5Ch], xmm0
0x1400134d9  mov     rcx, [rbx+8]; hWnd
0x1400134dd  mov     edx, 0FFFFFFF0h; nIndex
0x1400134e2  call    cs:__imp_GetWindowLongW
0x1400134e8  mov     rcx, [rbx+8]; hWnd
0x1400134ec  mov     edx, 0FFFFFFF0h; nIndex
0x1400134f1  and     eax, 0FF3AFFFFh
0x1400134f6  mov     r8d, eax; dwNewLong
0x1400134f9  call    cs:__imp_SetWindowLongW
0x1400134ff  mov     rcx, [rbx+8]; hWnd
0x140013503  xor     r8d, r8d; dwNewLong
0x140013506  lea     edx, [r8-0Ch]; nIndex
0x14001350a  call    cs:__imp_SetWindowLongW
0x140013510  mov     [rbx+758h], r12d
0x140013517  mov     [rbx+75Ch], edi
0x14001351d  test    edi, edi
0x14001351f  jz      loc_140013806
0x140013525  cmp     [rbp+57h+var_98], r12w
0x14001352a  jz      loc_140013806
0x140013530  lea     rcx, [rbp+57h+wndpl]; pvarg
0x140013534  mov     qword ptr [rbp+57h+var_A0], r12
0x140013538  call    cs:__imp_VariantInit
0x14001353e  mov     rcx, [rbp+57h+var_90]
0x140013542  lea     rdx, [rbp+57h+X+0Ch]
0x140013546  xorps   xmm0, xmm0
0x140013549  mov     qword ptr [rsp+0E0h+var_C0], rdx
0x14001354e  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x140013552  lea     r9, [rbp+57h+X+8]
0x140013556  mov     rax, [rcx]
0x140013559  lea     r8, [rbp+57h+X+4]
0x14001355d  lea     rdx, [rbp+57h+X]
0x140013561  mov     rax, [rax+1C0h]
0x140013568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001356d  mov     edi, eax
0x14001356f  test    eax, eax
0x140013571  jns     loc_14001365F
0x140013577  mov     rdx, cs:WPP_GLOBAL_Control
0x14001357e  lea     rcx, WPP_GLOBAL_Control
0x140013585  cmp     rdx, rcx
0x140013588  jz      short loc_1400135CA
0x14001358a  test    byte ptr [rdx+1Ch], 8
0x14001358e  jz      short loc_1400135CA
0x140013590  cmp     byte ptr [rdx+19h], 2
0x140013594  jb      short loc_1400135CA
0x140013596  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14001359b  mov     edx, 0CDh
0x1400135a0  lea     rcx, aGetremotemonit; "GetRemoteMonitorsBoundingBox failed"
0x1400135a7  mov     [rsp+0E0h+cy], edi
0x1400135ab  lea     r8, WPP_c53b5e828c42300d429425e15b0600ad_Traceguids
0x1400135b2  mov     qword ptr [rsp+0E0h+var_C0], rcx
0x1400135b7  mov     r9d, eax
0x1400135ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400135c1  mov     rcx, [rcx+10h]
0x1400135c5  call    WPP_SF_DsD
0x1400135ca  lea     rcx, [rbp+57h+wndpl]; pvarg
0x1400135ce  call    cs:__imp_VariantClear
0x1400135d4  mov     rcx, qword ptr [rbp+57h+var_A0]
0x1400135d8  test    rcx, rcx
0x1400135db  jz      loc_140013952
0x1400135e1  mov     qword ptr [rbp+57h+var_A0], r12
0x1400135e5  mov     rax, [rcx]
0x1400135e8  mov     rax, [rax+10h]
0x1400135ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400135f1  jmp     loc_140013952
0x1400135f6  mov     rcx, [rbp+57h+var_90]
0x1400135fa  lea     rdx, [rbp+57h+var_98]
0x1400135fe  mov     edi, r13d
0x140013601  mov     rax, [rcx]
0x140013604  mov     rax, [rax+1C8h]
0x14001360b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013610  mov     esi, eax
0x140013612  test    eax, eax
0x140013614  jns     loc_140013452
0x14001361a  mov     rdx, cs:WPP_GLOBAL_Control
0x140013621  lea     rcx, WPP_GLOBAL_Control
0x140013628  cmp     rdx, rcx
0x14001362b  jz      loc_140013952
0x140013631  test    byte ptr [rdx+1Ch], 8
0x140013635  jz      loc_140013952
0x14001363b  cmp     byte ptr [rdx+19h], 2
0x14001363f  jb      loc_140013952
0x140013645  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14001364a  mov     edx, 0CCh
0x14001364f  mov     [rsp+0E0h+cy], esi
0x140013653  lea     rcx, aGetRemotemonit_0; "get_RemoteMonitorLayoutMatchesLocal fai"...
0x14001365a  jmp     loc_1400133A9
0x14001365f  mov     rcx, [rbx+78h]
0x140013663  lea     r8, [rbp+57h+var_A0]
0x140013667  add     [rbp+57h+X+8], r13d
0x14001366b  lea     rdx, IID_IMsRdpExtendedSettings
0x140013672  add     [rbp+57h+X+0Ch], r13d
0x140013676  mov     rax, [rcx]
0x140013679  mov     rax, [rax]
0x14001367c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013681  mov     edi, eax
0x140013683  test    eax, eax
0x140013685  jns     short loc_1400136C8
0x140013687  mov     rdx, cs:WPP_GLOBAL_Control
0x14001368e  lea     rcx, WPP_GLOBAL_Control
0x140013695  cmp     rdx, rcx
0x140013698  jz      loc_1400135CA
0x14001369e  test    byte ptr [rdx+1Ch], 8
0x1400136a2  jz      loc_1400135CA
0x1400136a8  cmp     byte ptr [rdx+19h], 2
0x1400136ac  jb      loc_1400135CA
0x1400136b2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400136b7  mov     edx, 0CEh
0x1400136bc  lea     rcx, aQueryinterface_8; "QueryInterface failed for IMsRdpExtende"...
0x1400136c3  jmp     loc_1400135A7
0x1400136c8  mov     rcx, qword ptr [rbp+57h+var_A0]
0x1400136cc  lea     r8, [rbp+57h+wndpl]
0x1400136d0  lea     rdx, aSelectedmonito; "SelectedMonitors"
0x1400136d7  mov     rax, [rcx]
0x1400136da  mov     rax, [rax+20h]
0x1400136de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400136e3  mov     edi, eax
0x1400136e5  test    eax, eax
0x1400136e7  jns     short loc_14001372A
0x1400136e9  mov     rdx, cs:WPP_GLOBAL_Control
0x1400136f0  lea     rcx, WPP_GLOBAL_Control
0x1400136f7  cmp     rdx, rcx
0x1400136fa  jz      loc_1400135CA
0x140013700  test    byte ptr [rdx+1Ch], 8
0x140013704  jz      loc_1400135CA
0x14001370a  cmp     byte ptr [rdx+19h], 2
0x14001370e  jb      loc_1400135CA
0x140013714  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140013719  mov     edx, 0CFh
0x14001371e  lea     rcx, aGetPropertyUtr; "get_Property (UTREG_UI_SELECTED_MONITOR"...
0x140013725  jmp     loc_1400135A7
0x14001372a  mov     rdi, qword ptr [rbp+57h+wndpl.showCmd]
0x14001372e  mov     rcx, rdi
0x140013731  mov     rax, [rdi]
0x140013734  mov     rax, [rax+18h]
0x140013738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001373d  test    eax, eax
0x14001373f  jz      loc_1400137DA
0x140013745  lea     rdx, [rbp+57h+hrgn]; HRGN *
0x140013749  mov     rcx, rdi; struct IRdpMonitorList *
0x14001374c  call    ?GetSelectedMonitorRegion@CSH@@SAJPEAVIRdpMonitorList@@PEAPEAUHRGN__@@@Z; CSH::GetSelectedMonitorRegion(IRdpMonitorList *,HRGN__ * *)
0x140013751  mov     edi, eax
0x140013753  test    eax, eax
0x140013755  jns     short loc_140013798
0x140013757  mov     rdx, cs:WPP_GLOBAL_Control
0x14001375e  lea     rcx, WPP_GLOBAL_Control
0x140013765  cmp     rdx, rcx
0x140013768  jz      loc_1400135CA
0x14001376e  test    byte ptr [rdx+1Ch], 8
0x140013772  jz      loc_1400135CA
0x140013778  cmp     byte ptr [rdx+19h], 2
0x14001377c  jb      loc_1400135CA
0x140013782  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140013787  mov     edx, 0D0h
0x14001378c  lea     rcx, aGetselectedmon; "GetSelectedMonitorRegion failed"
0x140013793  jmp     loc_1400135A7
0x140013798  mov     r14, [rbp+57h+hrgn]
0x14001379c  lea     rdx, [rbp+57h+rc]; lprc
0x1400137a0  mov     rcx, r14; hrgn
0x1400137a3  call    cs:__imp_GetRgnBox
0x1400137a9  mov     r8d, [rbp+57h+rc.top]
0x1400137ad  mov     rcx, r14; hrgn
0x1400137b0  mov     edx, [rbp+57h+rc.left]
0x1400137b3  neg     r8d; y
0x1400137b6  neg     edx; x
0x1400137b8  call    cs:__imp_OffsetRgn
0x1400137be  mov     edx, [rbp+57h+rc.left]
0x1400137c1  mov     eax, edx
0x1400137c3  sub     eax, [rbp+57h+X]
0x1400137c6  add     [rbp+57h+X+8], eax
0x1400137c9  mov     ecx, [rbp+57h+rc.top]
0x1400137cc  mov     eax, ecx
0x1400137ce  sub     eax, [rbp+57h+X+4]
0x1400137d1  add     [rbp+57h+X+0Ch], eax
0x1400137d4  mov     [rbp+57h+X], edx
0x1400137d7  mov     [rbp+57h+X+4], ecx
0x1400137da  lea     rcx, [rbp+57h+wndpl]; pvarg
0x1400137de  call    cs:__imp_VariantClear
0x1400137e4  mov     rcx, qword ptr [rbp+57h+var_A0]
0x1400137e8  test    rcx, rcx
0x1400137eb  jz      loc_14001389B
0x1400137f1  mov     qword ptr [rbp+57h+var_A0], r12
0x1400137f5  mov     rax, [rcx]
0x1400137f8  mov     rax, [rax+10h]
0x1400137fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013801  jmp     loc_14001389B
0x140013806  mov     rcx, [rbx+78h]
0x14001380a  lea     rdx, [rbp+57h+var_A0]
0x14001380e  mov     [rbp+57h+var_A0], r12d
0x140013812  mov     dword ptr [rbp+57h+hrgn], r12d
0x140013816  mov     rax, [rcx]
0x140013819  mov     rax, [rax+98h]
0x140013820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013825  mov     rcx, [rbx+78h]
  ... truncated ...
```
