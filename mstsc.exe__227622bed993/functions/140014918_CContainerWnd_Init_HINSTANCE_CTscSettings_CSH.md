# CContainerWnd::Init(HINSTANCE__ *,CTscSettings *,CSH *)

- ea: `0x140014918`
- end: `0x1400150ec`
- name: `?Init@CContainerWnd@@QEAAHPEAUHINSTANCE__@@PEAVCTscSettings@@PEAVCSH@@@Z`
- size: `2004`
- prototype: `__int64 __fastcall(CContainerWnd *__hidden this, HINSTANCE, struct CTscSettings *, struct CSH *)`
- caller_count: `1`
- callee_count: `29`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140041e24`

## callees

- `0x14000b7d8`
- `0x14000c7d0`
- `0x14000c7f8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14000d078`
- `0x14000dcac`
- `0x1400128d0`
- `0x140014918`
- `0x1400150f4`
- `0x140019444`
- `0x140019edc`
- `0x14001a1c8`
- `0x14001e130`
- `0x140028e10`
- `0x1400293c4`
- `0x140029fec`
- `0x140034900`
- `0x14004aedc`
- `0x140059610`
- `0x14005ffbc`
- `0x14006481c`
- `0x140096010`
- `0x1400965c4`
- `0x14009d6f8`
- `0x1400b4844`
- `0x1400fa960`
- `0x140111220`
- `0x140112010`

## import_xrefs

- `USER32!RegisterWindowMessageW` at `0x140014dbe`
- `USER32!RegisterWindowMessageW` at `0x140014dd1`
- `USER32!RegisterWindowMessageW` at `0x140014dbe`
- `USER32!RegisterWindowMessageW` at `0x140014dd1`
- `USER32!SetRect` at `0x140014acc`
- `USER32!SetRect` at `0x140014acc`
- `USER32!CopyRect` at `0x140014ab7`
- `USER32!CopyRect` at `0x140014ab7`
- `USER32!GetDesktopWindow` at `0x140014a92`
- `USER32!GetDesktopWindow` at `0x140014a92`
- `USER32!GetWindowRect` at `0x140014a9f`
- `USER32!GetWindowRect` at `0x140014a9f`
- `USER32!DestroyWindow` at `0x14001507f`
- `USER32!DestroyWindow` at `0x14001507f`
- `COMCTL32!InitCommonControlsEx` at `0x140014b49`
- `COMCTL32!InitCommonControlsEx` at `0x140014b49`

## string_xrefs

- `0x1400149cc`: `RdpEdpPolicyManager::CreateInstance failed!`
- `0x140014dc4`: `EnterMoveSizeLoop`

## pseudocode

```c
__int64 __fastcall CContainerWnd::Init(CContainerWnd *this, HINSTANCE a2, struct CTscSettings *a3, struct CSH *a4)
{
  unsigned int inited; // ebx
  struct CTscSettings *v6; // r12
  int v8; // eax
  char v9; // r14
  unsigned int CurrentThreadActivityIdPrefix; // eax
  RdpEdpPolicyManager *v11; // r14
  int v12; // eax
  char v13; // r12
  unsigned int v14; // eax
  HWND DesktopWindow; // rax
  int v16; // eax
  char v17; // bl
  unsigned int v18; // eax
  CTscSettings **v19; // r13
  unsigned int v20; // edx
  unsigned int v21; // eax
  HWND v22; // r8
  const unsigned __int16 *v23; // r9
  unsigned int v24; // eax
  __int64 v25; // rdx
  unsigned int DpiForWindow; // eax
  unsigned int v27; // edx
  struct IMsRdpClient *v28; // rdx
  int v29; // ebx
  int v30; // eax
  int v31; // r12d
  unsigned int v32; // eax
  int v33; // edx
  const char *v34; // rcx
  CTscSettings *v35; // rax
  unsigned int v36; // eax
  CTscSettings *v37; // rcx
  int DeviceCollection; // eax
  HINSTANCE v39; // rsi
  __int64 v40; // rax
  int v41; // r9d
  HWND v42; // rcx
  __int64 v43; // rcx
  unsigned int v45; // [rsp+28h] [rbp-41h]
  HICON v46; // [rsp+38h] [rbp-31h]
  HINSTANCE hInstance; // [rsp+40h] [rbp-29h] BYREF
  __int64 v48; // [rsp+48h] [rbp-21h] BYREF
  RdpEdpPolicyManager *v49; // [rsp+50h] [rbp-19h] BYREF
  INITCOMMONCONTROLSEX picce; // [rsp+58h] [rbp-11h] BYREF
  struct CTscSettings *v51; // [rsp+60h] [rbp-9h]
  struct tagRECT rcDst; // [rsp+68h] [rbp-1h] BYREF
  struct tagRECT Rect; // [rsp+78h] [rbp+Fh] BYREF

  inited = 0;
  v51 = a3;
  hInstance = a2;
  v48 = 0;
  v6 = a3;
  Rect = 0;
  rcDst = 0;
  if ( !a2 || !a3 || !a4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_c53b5e828c42300d429425e15b0600ad_Traceguids);
    }
    goto LABEL_105;
  }
  *((_DWORD *)this + 484) = CContainerWnd::InitDpiSupport(this);
  v49 = 0;
  v8 = RdpEdpPolicyManager::CreateInstance(&v49);
  v9 = v8;
  if ( v8 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      (unsigned int)&WPP_c53b5e828c42300d429425e15b0600ad_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)"RdpEdpPolicyManager::CreateInstance failed!",
      v9);
  }
  v11 = v49;
  if ( v49 )
  {
    v12 = RdpEdpPolicyManager::TryApplyProcessUIPolicy(v49);
    v13 = v12;
    if ( v12 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          (unsigned int)&WPP_c53b5e828c42300d429425e15b0600ad_Traceguids,
          v14,
          (__int64)"TryApplyProcessUIPolicy failed!",
          v13);
      }
      if ( v11 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v11 + 4) + 16LL))(*((_QWORD *)v11 + 4));
      goto LABEL_105;
    }
    v6 = v51;
    if ( v11 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v11 + 4) + 16LL))(*((_QWORD *)v11 + 4));
  }
  DesktopWindow = GetDesktopWindow();
  if ( GetWindowRect(DesktopWindow, &Rect) )
    CopyRect(&rcDst, &Rect);
  else
    SetRect(&rcDst, 0, 0, 1, 1);
  *((_QWORD *)this + 13) = hInstance;
  *((_QWORD *)this + 12) = a4;
  v16 = CContainerWnd::RegisterPopupParentWindowClass(this, 1);
  v17 = v16;
  if ( v16 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v18 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      (unsigned int)&WPP_c53b5e828c42300d429425e15b0600ad_Traceguids,
      v18,
      (__int64)"Failed RegisterPopupParentWindowClass(TRUE)",
      v17);
  }
  picce.dwSize = 8;
  picce.dwICC = 512;
  inited = InitCommonControlsEx(&picce);
  if ( !inited )
    goto LABEL_105;
  v19 = (CTscSettings **)((char *)this + 760);
  if ( v6 != *((struct CTscSettings **)this + 95) )
  {
    TCntPtr<CTSCoreEventSink>::SafeRelease((char *)this + 760);
    *v19 = v6;
    TCntPtr<CTscSettings>::SafeAddRef((char *)this + 760);
  }
  if ( !TSLoadString(hInstance, 0x3ECu, (unsigned __int16 *)this + 386, 260)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v21 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_c53b5e828c42300d429425e15b0600ad_Traceguids, v21);
  }
  CSH::SH_GetPathToDefaultFile((unsigned __int16 *)this + 648, v20);
  if ( !CTscFrameWnd::CreateWnd((LONG_PTR)this, hInstance, v22, v23, *((LPCWSTR *)this + 12), v45, &rcDst, v46) )
  {
    inited = 0;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_105;
    }
    v24 = RdpWppGetCurrentThreadActivityIdPrefix();
    v25 = 16;
LABEL_40:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v25, &WPP_c53b5e828c42300d429425e15b0600ad_Traceguids, v24);
LABEL_105:
    if ( *((_DWORD *)this + 472) )
    {
      v40 = *((_QWORD *)this + 95);
      if ( v40 )
        v41 = *(_DWORD *)(v40 + 6260);
      else
        v41 = 0;
      CSharedSH::SH_DisplayMsgBox(0, 0x33F5u, (int)a3, v41);
    }
    v42 = (HWND)*((_QWORD *)this + 1);
    if ( v42 )
      DestroyWindow(v42);
    v43 = *((_QWORD *)this + 15);
    if ( v43 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
      *((_QWORD *)this + 15) = 0;
    }
    if ( *((_QWORD *)this + 16) )
    {
      TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 128);
      *((_QWORD *)this + 16) = 0;
    }
    return inited;
  }
  if ( *((_DWORD *)this + 484) )
    DpiForWindow = Win32DpiApi::GetDpiForWindow(*((Win32DpiApi **)this + 241), *((HWND *)this + 1));
  else
    DpiForWindow = CSH::SH_GetDPI();
  *((_DWORD *)this + 485) = DpiForWindow;
  CContainerWnd::SetWindowIcon(this, v27);
  if ( (int)CContainerWnd::CreateTsControl(this) < 0 || (v28 = (struct IMsRdpClient *)*((_QWORD *)this + 15)) == 0 )
  {
    inited = 0;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_105;
    }
    v24 = RdpWppGetCurrentThreadActivityIdPrefix();
    v25 = 17;
    goto LABEL_40;
  }
  inited = CSH::SH_ReadControlVer(*((CSH **)this + 12), v28);
  if ( !inited )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_105;
    }
    v24 = RdpWppGetCurrentThreadActivityIdPrefix();
    v25 = inited + 18;
    goto LABEL_40;
  }
  if ( (*(int (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 15) + 312LL))(*((_QWORD *)this + 15), &v48) < 0
    || !v48 )
  {
    inited = 0;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_105;
    }
    v24 = RdpWppGetCurrentThreadActivityIdPrefix();
    v25 = 19;
    goto LABEL_40;
  }
  v29 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v48 + 136LL))(v48, 1);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
  if ( v29 < 0 )
  {
    inited = 0;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_105;
    }
    v24 = RdpWppGetCurrentThreadActivityIdPrefix();
    v25 = 20;
    goto LABEL_40;
  }
  inited = 1;
  v30 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, char *))this + 15))(
          *((_QWORD *)this + 15),
          &IID_IMsRdpClient9,
          (char *)this + 128);
  LOBYTE(v31) = v30;
  if ( v30 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return inited;
    }
    v32 = RdpWppGetCurrentThreadActivityIdPrefix();
    v33 = 21;
    v34 = "QI for IID_IMsRdpClient9 failed!";
    goto LABEL_59;
  }
  CContainerWnd::SetupSystemMenu(this);
  *((_DWORD *)this + 473) = RegisterWindowMessageW(L"HandleContainerWndDisplayChange");
  *((_DWORD *)this + 474) = RegisterWindowMessageW(L"EnterMoveSizeLoop");
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      &WPP_c53b5e828c42300d429425e15b0600ad_Traceguids,
      *((unsigned int *)this + 462),
      1);
  }
  v35 = *v19;
  *((_DWORD *)this + 462) = 1;
  if ( *((_DWORD *)v35 + 14) && *((_DWORD *)v35 + 51005) )
  {
    v31 = CRdpLaunchConsent::RunRdpLaunchConsentFlow(*((HINSTANCE *)this + 13), *((HWND *)this + 1));
    if ( v31 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return inited;
      }
      v32 = RdpWppGetCurrentThreadActivityIdPrefix();
      v33 = 23;
      v34 = "Failed to run RDP launch consent flow.";
LABEL_59:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v33,
        (unsigned int)&WPP_c53b5e828c42300d429425e15b0600ad_Traceguids,
        v32,
        (__int64)v34,
        v31);
      return inited;
    }
    *((_DWORD *)this + 472) = 0;
    inited = v31 == 0;
    if ( v31 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_105;
      }
      v24 = RdpWppGetCurrentThreadActivityIdPrefix();
      v25 = 24;
      goto LABEL_40;
    }
    *((_DWORD *)this + 472) = 1;
  }
  inited = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 233) + 24LL))(*((_QWORD *)this + 233));
  if ( !inited
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v36 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), inited + 25, &WPP_c53b5e828c42300d429425e15b0600ad_Traceguids, v36);
  }
  if ( (unsigned int)CUT::UT_ReadRegistryInt(&pszPassword, L"DynamicDeviceTestEnabled", 0, 2) )
  {
    v37 = *v19;
    hInstance = 0;
    DeviceCollection = CTscSettings::GetDeviceCollection(v37, (struct IMsRdpDeviceCollection **)&hInstance);
    v39 = hInstance;
    if ( DeviceCollection >= 0 )
      IDynamicDeviceTestServer::CreateInstance(
        (struct IMsRdpDeviceCollection *)hInstance,
        (struct IDynamicDeviceTestServer **)this + 238);
    if ( v39 )
      (*(void (__fastcall **)(HINSTANCE))(*(_QWORD *)v39 + 16LL))(v39);
  }
  if ( !inited )
    goto LABEL_105;
  return inited;
}

```

## disassembly

```asm
0x140014918  mov     [rsp-8+arg_10], rbx
0x14001491d  push    rbp
0x14001491e  push    rsi
0x14001491f  push    rdi
0x140014920  push    r12
0x140014922  push    r13
0x140014924  push    r14
0x140014926  push    r15
0x140014928  lea     rbp, [rsp-27h]
0x14001492d  sub     rsp, 90h
0x140014934  mov     rax, cs:__security_cookie
0x14001493b  xor     rax, rsp
0x14001493e  mov     [rbp+57h+var_38], rax
0x140014942  xor     ebx, ebx
0x140014944  mov     [rbp+57h+var_60], r8
0x140014948  mov     [rbp+57h+hInstance], rdx
0x14001494c  xorps   xmm0, xmm0
0x14001494f  mov     [rbp+57h+var_78], rbx
0x140014953  xorps   xmm1, xmm1
0x140014956  mov     r13, r9
0x140014959  mov     r12, r8
0x14001495c  mov     rdi, rcx
0x14001495f  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x140014963  movups  xmmword ptr [rbp+57h+rcDst.left], xmm1
0x140014967  test    rdx, rdx
0x14001496a  jz      loc_140015010
0x140014970  test    r8, r8
0x140014973  jz      loc_140015010
0x140014979  test    r9, r9
0x14001497c  jz      loc_140015010
0x140014982  call    ?InitDpiSupport@CContainerWnd@@AEAAHXZ; CContainerWnd::InitDpiSupport(void)
0x140014987  lea     rcx, [rbp+57h+var_70]; struct RdpEdpPolicyManager **
0x14001498b  mov     [rdi+790h], eax
0x140014991  mov     [rbp+57h+var_70], rbx
0x140014995  call    ?CreateInstance@RdpEdpPolicyManager@@SAJPEAPEAV1@@Z; RdpEdpPolicyManager::CreateInstance(RdpEdpPolicyManager * *)
0x14001499a  lea     r15, WPP_c53b5e828c42300d429425e15b0600ad_Traceguids
0x1400149a1  mov     r14d, eax
0x1400149a4  lea     rsi, WPP_GLOBAL_Control
0x1400149ab  test    eax, eax
0x1400149ad  jns     short loc_1400149F6
0x1400149af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400149b6  cmp     rcx, rsi
0x1400149b9  jz      short loc_1400149F6
0x1400149bb  test    byte ptr [rcx+1Ch], 8
0x1400149bf  jz      short loc_1400149F6
0x1400149c1  cmp     byte ptr [rcx+19h], 2
0x1400149c5  jb      short loc_1400149F6
0x1400149c7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400149cc  lea     rcx, aRdpedppolicyma; "RdpEdpPolicyManager::CreateInstance fai"...
0x1400149d3  mov     [rsp+0C0h+var_98], r14d
0x1400149d8  mov     qword ptr [rsp+0C0h+yBottom], rcx
0x1400149dd  lea     edx, [rbx+0Ch]
0x1400149e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400149e7  mov     r9d, eax
0x1400149ea  mov     r8, r15
0x1400149ed  mov     rcx, [rcx+10h]
0x1400149f1  call    WPP_SF_DsD
0x1400149f6  mov     r14, [rbp+57h+var_70]
0x1400149fa  test    r14, r14
0x1400149fd  jz      loc_140014A92
0x140014a03  mov     rcx, r14; this
0x140014a06  call    ?TryApplyProcessUIPolicy@RdpEdpPolicyManager@@QEAAJXZ; RdpEdpPolicyManager::TryApplyProcessUIPolicy(void)
0x140014a0b  mov     r12d, eax
0x140014a0e  test    eax, eax
0x140014a10  jns     short loc_140014A79
0x140014a12  mov     rcx, cs:WPP_GLOBAL_Control
0x140014a19  cmp     rcx, rsi
0x140014a1c  jz      short loc_140014A5B
0x140014a1e  test    byte ptr [rcx+1Ch], 8
0x140014a22  jz      short loc_140014A5B
0x140014a24  cmp     byte ptr [rcx+19h], 2
0x140014a28  jb      short loc_140014A5B
0x140014a2a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140014a2f  lea     rcx, aTryapplyproces_0; "TryApplyProcessUIPolicy failed!"
0x140014a36  mov     [rsp+0C0h+var_98], r12d
0x140014a3b  mov     qword ptr [rsp+0C0h+yBottom], rcx
0x140014a40  mov     edx, 0Dh
0x140014a45  mov     rcx, cs:WPP_GLOBAL_Control
0x140014a4c  mov     r9d, eax
0x140014a4f  mov     r8, r15
0x140014a52  mov     rcx, [rcx+10h]
0x140014a56  call    WPP_SF_DsD
0x140014a5b  test    r14, r14
0x140014a5e  jz      loc_140015049
0x140014a64  mov     rcx, [r14+20h]
0x140014a68  mov     rax, [rcx]
0x140014a6b  mov     rax, [rax+10h]
0x140014a6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014a74  jmp     loc_140015049
0x140014a79  mov     r12, [rbp+57h+var_60]
0x140014a7d  test    r14, r14
0x140014a80  jz      short loc_140014A92
0x140014a82  mov     rcx, [r14+20h]
0x140014a86  mov     rax, [rcx]
0x140014a89  mov     rax, [rax+10h]
0x140014a8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014a92  call    cs:__imp_GetDesktopWindow
0x140014a98  mov     rcx, rax; hWnd
0x140014a9b  lea     rdx, [rbp+57h+Rect]; lpRect
0x140014a9f  call    cs:__imp_GetWindowRect
0x140014aa5  mov     r14d, 1
0x140014aab  lea     rcx, [rbp+57h+rcDst]; lprc
0x140014aaf  test    eax, eax
0x140014ab1  jz      short loc_140014ABF
0x140014ab3  lea     rdx, [rbp+57h+Rect]; lprcSrc
0x140014ab7  call    cs:__imp_CopyRect
0x140014abd  jmp     short loc_140014AD2
0x140014abf  mov     r9d, r14d; xRight
0x140014ac2  mov     [rsp+0C0h+yBottom], r14d; yBottom
0x140014ac7  xor     r8d, r8d; yTop
0x140014aca  xor     edx, edx; xLeft
0x140014acc  call    cs:__imp_SetRect
0x140014ad2  mov     rax, [rbp+57h+hInstance]
0x140014ad6  mov     edx, r14d; int
0x140014ad9  mov     rcx, rdi; this
0x140014adc  mov     [rdi+68h], rax
0x140014ae0  mov     [rdi+60h], r13
0x140014ae4  call    ?RegisterPopupParentWindowClass@CContainerWnd@@AEAAJH@Z; CContainerWnd::RegisterPopupParentWindowClass(int)
0x140014ae9  mov     ebx, eax
0x140014aeb  test    eax, eax
0x140014aed  jns     short loc_140014B37
0x140014aef  mov     rcx, cs:WPP_GLOBAL_Control
0x140014af6  cmp     rcx, rsi
0x140014af9  jz      short loc_140014B37
0x140014afb  test    byte ptr [rcx+1Ch], 8
0x140014aff  jz      short loc_140014B37
0x140014b01  cmp     byte ptr [rcx+19h], 2
0x140014b05  jb      short loc_140014B37
0x140014b07  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140014b0c  lea     rcx, aFailedRegister; "Failed RegisterPopupParentWindowClass(T"...
0x140014b13  mov     [rsp+0C0h+var_98], ebx; unsigned int
0x140014b17  mov     qword ptr [rsp+0C0h+yBottom], rcx
0x140014b1c  mov     edx, 0Eh
0x140014b21  mov     rcx, cs:WPP_GLOBAL_Control
0x140014b28  mov     r9d, eax
0x140014b2b  mov     r8, r15
0x140014b2e  mov     rcx, [rcx+10h]
0x140014b32  call    WPP_SF_DsD
0x140014b37  lea     rcx, [rbp+57h+picce]; picce
0x140014b3b  mov     [rbp+57h+picce.dwSize], 8
0x140014b42  mov     [rbp+57h+picce.dwICC], 200h
0x140014b49  call    cs:__imp_InitCommonControlsEx
0x140014b4f  mov     ebx, eax
0x140014b51  test    eax, eax
0x140014b53  jz      loc_140015049
0x140014b59  lea     r13, [rdi+2F8h]
0x140014b60  cmp     r12, [r13+0]
0x140014b64  jz      short loc_140014B7A
0x140014b66  mov     rcx, r13
0x140014b69  call    ?SafeRelease@?$TCntPtr@VCTSCoreEventSink@@@@AEAAXXZ; TCntPtr<CTSCoreEventSink>::SafeRelease(void)
0x140014b6e  mov     rcx, r13
0x140014b71  mov     [r13+0], r12
0x140014b75  call    ?SafeAddRef@?$TCntPtr@VCTscSettings@@@@AEAAXXZ; TCntPtr<CTscSettings>::SafeAddRef(void)
0x140014b7a  mov     rbx, [rbp+57h+hInstance]
0x140014b7e  lea     r8, [rdi+304h]; unsigned __int16 *
0x140014b85  mov     rcx, rbx; HINSTANCE
0x140014b88  mov     edx, 3ECh; unsigned int
0x140014b8d  mov     r9d, 104h; int
0x140014b93  call    ?TSLoadString@@YAHPEAUHINSTANCE__@@IPEAGH@Z; TSLoadString(HINSTANCE__ *,uint,ushort *,int)
0x140014b98  test    eax, eax
0x140014b9a  jnz     short loc_140014BD4
0x140014b9c  mov     rax, cs:WPP_GLOBAL_Control
0x140014ba3  cmp     rax, rsi
0x140014ba6  jz      short loc_140014BD4
0x140014ba8  test    [rax+1Ch], r14b
0x140014bac  jz      short loc_140014BD4
0x140014bae  cmp     byte ptr [rax+19h], 2
0x140014bb2  jb      short loc_140014BD4
0x140014bb4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140014bb9  mov     rcx, cs:WPP_GLOBAL_Control
0x140014bc0  mov     edx, 0Fh
0x140014bc5  mov     r9d, eax
0x140014bc8  mov     r8, r15
0x140014bcb  mov     rcx, [rcx+10h]
0x140014bcf  call    WPP_SF_d
0x140014bd4  lea     rcx, [rdi+510h]; unsigned __int16 *
0x140014bdb  call    ?SH_GetPathToDefaultFile@CSH@@SAHPEAGI@Z; CSH::SH_GetPathToDefaultFile(ushort *,uint)
0x140014be0  lea     rax, [rbp+57h+rcDst]
0x140014be4  mov     rdx, rbx; hInstance
0x140014be7  mov     [rsp+0C0h+var_90], rax; struct tagRECT *
0x140014bec  mov     rcx, rdi; dwNewLong
0x140014bef  mov     rax, [rdi+60h]
0x140014bf3  mov     qword ptr [rsp+0C0h+yBottom], rax; lpWindowName
0x140014bf8  call    ?CreateWnd@CTscFrameWnd@@QEAAPEAUHWND__@@PEAUHINSTANCE__@@PEAU2@PEBG2KPEAUtagRECT@@PEAUHICON__@@@Z; CTscFrameWnd::CreateWnd(HINSTANCE__ *,HWND__ *,ushort const *,ushort const *,ulong,tagRECT *,HICON__ *)
0x140014bfd  test    rax, rax
0x140014c00  jnz     short loc_140014C4B
0x140014c02  xor     ebx, ebx
0x140014c04  mov     rax, cs:WPP_GLOBAL_Control
0x140014c0b  cmp     rax, rsi
0x140014c0e  jz      loc_140015049
0x140014c14  test    byte ptr [rax+1Ch], 8
0x140014c18  jz      loc_140015049
0x140014c1e  cmp     byte ptr [rax+19h], 2
0x140014c22  jb      loc_140015049
0x140014c28  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140014c2d  lea     edx, [rbx+10h]
0x140014c30  mov     rcx, cs:WPP_GLOBAL_Control
0x140014c37  mov     r9d, eax
0x140014c3a  mov     r8, r15
0x140014c3d  mov     rcx, [rcx+10h]
0x140014c41  call    WPP_SF_d
0x140014c46  jmp     loc_140015049
0x140014c4b  cmp     dword ptr [rdi+790h], 0
0x140014c52  jz      short loc_140014C66
0x140014c54  mov     rdx, [rdi+8]; HWND
0x140014c58  mov     rcx, [rdi+788h]; this
0x140014c5f  call    ?GetDpiForWindow@Win32DpiApi@@QEAAIPEAUHWND__@@@Z; Win32DpiApi::GetDpiForWindow(HWND__ *)
0x140014c64  jmp     short loc_140014C6B
0x140014c66  call    ?SH_GetDPI@CSH@@SAIXZ; CSH::SH_GetDPI(void)
0x140014c6b  mov     rcx, rdi; this
0x140014c6e  mov     [rdi+794h], eax
0x140014c74  call    ?SetWindowIcon@CContainerWnd@@AEAAXI@Z; CContainerWnd::SetWindowIcon(uint)
0x140014c79  mov     rcx, rdi; this
0x140014c7c  call    ?CreateTsControl@CContainerWnd@@AEAAJXZ; CContainerWnd::CreateTsControl(void)
0x140014c81  test    eax, eax
0x140014c83  js      loc_140014FE9
0x140014c89  mov     rdx, [rdi+78h]; struct IMsRdpClient *
0x140014c8d  test    rdx, rdx
0x140014c90  jz      loc_140014FE9
0x140014c96  mov     rcx, [rdi+60h]; this
0x140014c9a  call    ?SH_ReadControlVer@CSH@@QEAAHPEAUIMsRdpClient@@@Z; CSH::SH_ReadControlVer(IMsRdpClient *)
0x140014c9f  mov     ebx, eax
0x140014ca1  test    eax, eax
0x140014ca3  jnz     short loc_140014CD6
0x140014ca5  mov     rax, cs:WPP_GLOBAL_Control
0x140014cac  cmp     rax, rsi
0x140014caf  jz      loc_140015049
0x140014cb5  test    byte ptr [rax+1Ch], 8
0x140014cb9  jz      loc_140015049
0x140014cbf  cmp     byte ptr [rax+19h], 2
0x140014cc3  jb      loc_140015049
0x140014cc9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140014cce  lea     edx, [rbx+12h]
0x140014cd1  jmp     loc_140014C30
0x140014cd6  mov     rcx, [rdi+78h]
0x140014cda  lea     rdx, [rbp+57h+var_78]
0x140014cde  mov     rax, [rcx]
0x140014ce1  mov     rax, [rax+138h]
0x140014ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014ced  test    eax, eax
0x140014cef  js      loc_140014FC2
0x140014cf5  mov     rcx, [rbp+57h+var_78]
0x140014cf9  test    rcx, rcx
0x140014cfc  jz      loc_140014FC2
0x140014d02  mov     rax, [rcx]
0x140014d05  mov     edx, r14d
0x140014d08  mov     rax, [rax+88h]
0x140014d0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014d14  mov     rcx, [rbp+57h+var_78]
0x140014d18  mov     ebx, eax
0x140014d1a  mov     rdx, [rcx]
0x140014d1d  mov     rax, [rdx+10h]
0x140014d21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014d26  test    ebx, ebx
0x140014d28  js      loc_140014F8F
0x140014d2e  mov     rcx, [rdi+78h]
0x140014d32  lea     r8, [rdi+80h]
0x140014d39  lea     rdx, IID_IMsRdpClient9
0x140014d40  mov     ebx, r14d
0x140014d43  mov     rax, [rcx]
0x140014d46  mov     rax, [rax]
0x140014d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014d4e  mov     r12d, eax
0x140014d51  test    eax, eax
0x140014d53  jns     short loc_140014DAF
0x140014d55  mov     rcx, cs:WPP_GLOBAL_Control
0x140014d5c  cmp     rcx, rsi
0x140014d5f  jz      loc_1400150C3
0x140014d65  test    byte ptr [rcx+1Ch], 8
0x140014d69  jz      loc_1400150C3
0x140014d6f  cmp     byte ptr [rcx+19h], 2
0x140014d73  jb      loc_1400150C3
0x140014d79  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140014d7e  mov     edx, 15h
0x140014d83  lea     rcx, aQiForIidImsrdp_3; "QI for IID_IMsRdpClient9 failed!"
0x140014d8a  mov     [rsp+0C0h+var_98], r12d
0x140014d8f  mov     r9d, eax
0x140014d92  mov     qword ptr [rsp+0C0h+yBottom], rcx
0x140014d97  mov     r8, r15
0x140014d9a  mov     rcx, cs:WPP_GLOBAL_Control
0x140014da1  mov     rcx, [rcx+10h]
0x140014da5  call    WPP_SF_DsD
0x140014daa  jmp     loc_1400150C3
0x140014daf  mov     rcx, rdi; this
0x140014db2  call    ?SetupSystemMenu@CContainerWnd@@AEAAHXZ; CContainerWnd::SetupSystemMenu(void)
0x140014db7  lea     rcx, String; "HandleContainerWndDisplayChange"
0x140014dbe  call    cs:__imp_RegisterWindowMessageW
0x140014dc4  lea     rcx, aEntermovesizel; "EnterMoveSizeLoop"
0x140014dcb  mov     [rdi+764h], eax
0x140014dd1  call    cs:__imp_RegisterWindowMessageW
0x140014dd7  mov     [rdi+768h], eax
0x140014ddd  mov     rcx, cs:WPP_GLOBAL_Control
0x140014de4  cmp     rcx, rsi
0x140014de7  jz      short loc_140014E12
0x140014de9  test    [rcx+1Ch], r14b
0x140014ded  jz      short loc_140014E12
0x140014def  cmp     byte ptr [rcx+19h], 2
0x140014df3  jb      short loc_140014E12
0x140014df5  mov     r9d, [rdi+738h]
0x140014dfc  mov     edx, 16h
  ... truncated ...
```
