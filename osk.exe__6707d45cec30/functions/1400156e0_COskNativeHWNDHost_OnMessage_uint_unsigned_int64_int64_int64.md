# COskNativeHWNDHost::OnMessage(uint,unsigned __int64,__int64,__int64 *)

- ea: `0x1400156e0`
- end: `0x140015c52`
- name: `?OnMessage@COskNativeHWNDHost@@EEAAJI_K_JPEA_J@Z`
- size: `1394`
- prototype: `__int64 __usercall@<rax>(COskNativeHWNDHost *__hidden this@<rcx>, unsigned int@<edx>, unsigned __int64@<r8>, __int64@<r9>, __int64 *)`
- caller_count: `0`
- callee_count: `31`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x14000def8`
- `0x14000df20`
- `0x14000fdf0`
- `0x140010c54`
- `0x140011494`
- `0x1400114b8`
- `0x1400121a0`
- `0x140012db0`
- `0x1400139a0`
- `0x140013aa0`
- `0x140014634`
- `0x140014974`
- `0x1400149c0`
- `0x1400151bc`
- `0x1400154b8`
- `0x140015684`
- `0x1400156e0`
- `0x140015c7c`
- `0x140015d58`
- `0x140015dcc`
- `0x140015f34`
- `0x14001614c`
- `0x140016318`
- `0x140016598`
- `0x140016abc`
- `0x140016cf4`
- `0x140017990`
- `0x1400182a4`
- `0x14001b190`
- `0x14001b7bc`
- `0x14001b7e4`

## import_xrefs

- `KERNEL32!GlobalDeleteAtom` at `0x140015831`
- `KERNEL32!GlobalDeleteAtom` at `0x140015831`
- `USER32!ScreenToClient` at `0x140015a5d`
- `USER32!ScreenToClient` at `0x140015a5d`
- `USER32!SendMessageW` at `0x1400157ab`
- `USER32!SendMessageW` at `0x1400157ab`
- `USER32!DestroyWindow` at `0x140015850`
- `USER32!DestroyWindow` at `0x140015850`
- `USER32!RemovePropW` at `0x140015827`
- `USER32!RemovePropW` at `0x140015827`
- `USER32!SetForegroundWindow` at `0x1400158ac`
- `USER32!SetForegroundWindow` at `0x1400158ac`
- `OLEACC!AccSetRunningUtilityState` at `0x1400157cd`
- `OLEACC!AccSetRunningUtilityState` at `0x1400157cd`

## pseudocode

```c
__int64 __fastcall COskNativeHWNDHost::OnMessage(
        COskNativeHWNDHost *this,
        unsigned int a2,
        unsigned __int64 a3,
        HKL a4,
        __int64 *Point)
{
  __int64 *v5; // r14
  unsigned int v9; // edi
  unsigned int v10; // edx
  unsigned int v11; // edx
  unsigned int v12; // edx
  unsigned int v13; // edx
  unsigned int v14; // edx
  unsigned int v15; // edx
  bool IsNavKeyboardVisible; // al
  HWND v17; // rsi
  HWND HWND; // rax
  unsigned int v19; // edx
  unsigned int v20; // edx
  unsigned int v21; // edx
  unsigned int v22; // edx
  unsigned int v23; // edx
  unsigned int v24; // edx
  __int64 v25; // rax
  unsigned int v26; // edx
  unsigned int v27; // edx
  unsigned int v28; // edx
  unsigned int v29; // edx
  unsigned int v30; // edx
  unsigned int v31; // edx
  HWND v32; // rcx
  COSKKeyboardManager *v33; // rcx
  unsigned int v34; // edx
  unsigned int v35; // edx
  unsigned int v36; // edx
  unsigned int v37; // edx
  __int64 v38; // rdx
  int v40; // [rsp+78h] [rbp+10h] BYREF

  v5 = Point;
  v9 = 1;
  *Point = 0;
  if ( a2 > 0x116 )
  {
    if ( a2 <= 0x40C )
    {
      if ( a2 == 1036 )
      {
        COskNativeHWNDHost::SetForegroundWindowFromCachedHandle(this);
        return v9;
      }
      v26 = a2 - 561;
      if ( !v26 )
      {
        if ( COSKKeyboardManager::s_pCOSKKeyboardManager )
          COSKKeyboardManager::ClearPredictionsInternal(COSKKeyboardManager::s_pCOSKKeyboardManager);
        return v9;
      }
      v27 = v26 - 1;
      if ( !v27 )
      {
        COskNativeHWNDHost::SetForegroundWindowFromCachedHandle(this);
        COskNativeHWNDHost::SetOSKUIBasedOnScreenResolution(this, 0);
        *((_DWORD *)this + 30) = 0;
        return v9;
      }
      v28 = v27 - 232;
      if ( !v28 )
      {
LABEL_12:
        COskNativeHWNDHost::StoreDPI(this);
        IsNavKeyboardVisible = COSKKeyboardManager::IsNavKeyboardVisible();
        *(_QWORD *)((char *)this + 92) = **(_QWORD **)&COskNativeHWNDHost::DetermineOSKWindowSize(
                                                         this,
                                                         (int)&Point,
                                                         560,
                                                         IsNavKeyboardVisible ? 22 : -122);
        return v9;
      }
      v29 = v28 - 4;
      if ( !v29 )
      {
        COSKKeyboardManager::HandleSettingChange();
        return v9;
      }
      v30 = v29 - 151;
      if ( v30 )
      {
        v31 = v30 - 85;
        if ( !v31 )
        {
          v32 = (HWND)*((_QWORD *)this + 1);
          Point = (__int64 *)__PAIR64__((unsigned int)a4, a3);
          ScreenToClient(v32, (LPPOINT)&Point);
          COSKKeyboardManager::SimulateMouseClickInternal(v33, (struct tagPOINT *)&Point);
          return v9;
        }
        if ( v31 != 1 )
          return v9;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_701f9d48580b340774086315e62b6ed1_Traceguids);
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_701f9d48580b340774086315e62b6ed1_Traceguids);
        if ( *((_DWORD *)COSKKeyboardManager::s_pCOSKKeyboardManager + 41) != 3
          || !*((_DWORD *)COSKKeyboardManager::s_pCOSKKeyboardManager + 44) )
        {
          return v9;
        }
      }
      COskNativeHWNDHost::OnHandleScanKeyPress(this);
      return v9;
    }
    v34 = a2 - 1037;
    if ( v34 )
    {
      v35 = v34 - 1;
      if ( !v35 )
      {
        COskNativeHWNDHost::MoveOSKWindow(this, *((HWND *)this + 1), a3 != 0, WORD1(a4) != 0, (_WORD)a4 != 0);
        return v9;
      }
      v36 = v35 - 1;
      if ( !v36 )
      {
        COskNativeHWNDHost::HandleNavModeChange(this, a3 != 0);
        return v9;
      }
      v37 = v36 - 2;
      if ( !v37 )
      {
        COskNativeHWNDHost::SetOSKWindowDockedState(this, *((_BYTE *)this + 124) == 0, a3 != 0, 1);
        if ( !a3 && *((_BYTE *)this + 124) )
          COSKKeyboardManager::ToggleDockKeyVisualState();
        return v9;
      }
      v38 = v37 - 84;
      if ( !(_DWORD)v38 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_701f9d48580b340774086315e62b6ed1_Traceguids, a4);
        COSKKeyboardManager::HandleFocusChange(a4);
        return v9;
      }
      if ( (_DWORD)v38 != 32644 )
        return v9;
      LOBYTE(v38) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_OSK_SecureOnLockScreen>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_OSK_SecureOnLockScreen>::GetImpl'::`2'::impl,
        v38);
      if ( !COSKUtils::ShouldRunSecureOnLockScreen() )
        OSKSettingsManager::UpdateAllListeners();
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_701f9d48580b340774086315e62b6ed1_Traceguids);
      COSKKeyboardManager::HandleSetScanActive(1);
    }
    return 0;
  }
  if ( a2 == 278 )
  {
    *((_DWORD *)this + 16) = 0;
    return v9;
  }
  if ( a2 > 0x1C )
  {
    v19 = a2 - 32;
    if ( !v19 )
    {
      COskNativeHWNDHost::OnSetCursor(this, (__int64)a4);
      return v9;
    }
    v20 = v19 - 1;
    if ( !v20 )
    {
      v25 = 3;
      if ( (_WORD)a4 != 1 )
        v25 = 1;
      *v5 = v25;
      return (_WORD)a4 != 1;
    }
    v21 = v20 - 3;
    if ( !v21 )
    {
      if ( a4 )
      {
        a4[6] = *(_DWORD *)(HKL)((int)this + 92);
        a4[7] = *(_DWORD *)(HKL)((int)this + 96);
      }
      return v9;
    }
    v22 = v21 - 90;
    if ( !v22 )
    {
      COskNativeHWNDHost::HandleDisplayChange(this);
      return v9;
    }
    v23 = v22 - 147;
    if ( !v23 )
    {
      COskNativeHWNDHost::OnCommand(this, 0, a3, (__int64)a4);
      return v9;
    }
    v24 = v23 - 1;
    if ( v24 )
    {
      if ( v24 != 1 )
        return v9;
      COskNativeHWNDHost::OnTimer(this, a3);
LABEL_29:
      *v5 = 0;
      return 0;
    }
    if ( !*((_BYTE *)this + 124) || a3 != 61472 )
      return v9;
    return 0;
  }
  if ( a2 == 28 )
  {
    if ( a3 )
      return v9;
    COskNativeHWNDHost::ShowOSKToolTip(this, 0, 0);
    if ( *((_QWORD *)this + 7) && (COskOptionsDlg::GetHWND() || COskMessageDlg::GetHWND()) )
      *((_QWORD *)this + 7) = 0;
    goto LABEL_29;
  }
  v10 = a2 - 3;
  if ( !v10 )
  {
    COskNativeHWNDHost::OnPositionChanged(this);
    return v9;
  }
  v11 = v10 - 2;
  if ( !v11 )
  {
    COskNativeHWNDHost::OnSizeChanged(this, a3);
    return v9;
  }
  v12 = v11 - 1;
  if ( !v12 )
  {
    if ( a3 - 1 > 1 )
      return v9;
    if ( !a4 || a4 != (HKL)COskOptionsDlg::GetHWND() && a4 != (HKL)COskMessageDlg::GetHWND() )
    {
      HWND = COskMessageDlg::GetHWND();
      if ( HWND || (HWND = COskOptionsDlg::GetHWND()) != 0 )
        SetForegroundWindow(HWND);
      return v9;
    }
    COskNativeHWNDHost::SetForegroundWindowFromCachedHandle(this);
    goto LABEL_29;
  }
  v13 = v12 - 10;
  if ( !v13 )
  {
    v17 = (HWND)*((_QWORD *)this + 1);
    v40 = AccSetRunningUtilityState(v17, 1u, 0);
    COSKUtils::TryRecoverFromAccessDenied(&v40);
    if ( v40 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_701f9d48580b340774086315e62b6ed1_Traceguids,
        (unsigned int)v40);
    if ( *((_WORD *)this + 51) )
    {
      RemovePropW(v17, (LPCWSTR)*((unsigned __int16 *)this + 51));
      GlobalDeleteAtom(*((_WORD *)this + 51));
    }
    if ( *((_BYTE *)this + 124) )
      COskNativeHWNDHost::SetOSKWindowDockedState(this, 0, 0, 0);
    DestroyWindow(v17);
    return 0;
  }
  v14 = v13 - 1;
  if ( !v14 )
  {
    *v5 = 1;
    return v9;
  }
  v15 = v14 - 5;
  if ( !v15 )
  {
    SendMessageW(*((HWND *)this + 1), 2u, 0, 0);
    *v5 = 0;
    return v9;
  }
  if ( v15 == 4 )
    goto LABEL_12;
  return v9;
}

```

## disassembly

```asm
0x1400156e0  push    rbx
0x1400156e2  push    rbp
0x1400156e3  push    rsi
0x1400156e4  push    rdi
0x1400156e5  push    r14
0x1400156e7  push    r15
0x1400156e9  sub     rsp, 38h
0x1400156ed  mov     r14, qword ptr [rsp+68h+Point.x]
0x1400156f5  xor     r15d, r15d
0x1400156f8  mov     eax, 116h
0x1400156fd  mov     rsi, r9
0x140015700  mov     rbp, r8
0x140015703  mov     rbx, rcx
0x140015706  mov     edi, 1
0x14001570b  mov     [r14], r15
0x14001570e  cmp     edx, eax
0x140015710  ja      loc_1400159B7
0x140015716  jz      loc_1400159AE
0x14001571c  cmp     edx, 1Ch
0x14001571f  ja      loc_140015901
0x140015725  jz      loc_1400158CE
0x14001572b  sub     edx, 3
0x14001572e  jz      loc_1400158C4
0x140015734  sub     edx, 2
0x140015737  jz      loc_1400158B7
0x14001573d  sub     edx, edi
0x14001573f  jz      loc_14001585B
0x140015745  sub     edx, 0Ah
0x140015748  jz      short loc_1400157C1
0x14001574a  sub     edx, edi
0x14001574c  jz      short loc_1400157B9
0x14001574e  sub     edx, 5
0x140015751  jz      short loc_14001579D
0x140015753  cmp     edx, 4
0x140015756  jnz     loc_140015C43
0x14001575c  call    ?StoreDPI@COskNativeHWNDHost@@AEAA_NXZ; COskNativeHWNDHost::StoreDPI(void)
0x140015761  call    ?IsNavKeyboardVisible@COSKKeyboardManager@@SA_NXZ; COSKKeyboardManager::IsNavKeyboardVisible(void)
0x140015766  neg     al
0x140015768  mov     [rsp+68h+var_48], dil
0x14001576d  mov     r8d, 230h; int
0x140015773  lea     rdx, [rsp+68h+Point]; int
0x14001577b  sbb     r9d, r9d
0x14001577e  mov     rcx, rbx; this
0x140015781  and     r9d, 0FFFFFF90h
0x140015785  add     r9d, 86h; bool
0x14001578c  call    ?DetermineOSKWindowSize@COskNativeHWNDHost@@AEAA?AUtagSIZE@@HH_N@Z; COskNativeHWNDHost::DetermineOSKWindowSize(int,int,bool)
0x140015791  mov     rcx, [rax]
0x140015794  mov     [rbx+5Ch], rcx
0x140015798  jmp     loc_140015C43
0x14001579d  mov     rcx, [rcx+8]; hWnd
0x1400157a1  xor     r9d, r9d; lParam
0x1400157a4  xor     r8d, r8d; wParam
0x1400157a7  lea     edx, [r9+2]; Msg
0x1400157ab  call    cs:__imp_SendMessageW
0x1400157b1  mov     [r14], r15
0x1400157b4  jmp     loc_140015C43
0x1400157b9  mov     [r14], rdi
0x1400157bc  jmp     loc_140015C43
0x1400157c1  mov     rsi, [rcx+8]
0x1400157c5  xor     r8d, r8d; dwUtilityState
0x1400157c8  mov     rcx, rsi; hwndApp
0x1400157cb  mov     edx, edi; dwUtilityStateMask
0x1400157cd  call    cs:__imp_AccSetRunningUtilityState
0x1400157d3  lea     rcx, [rsp+68h+arg_8]; int *
0x1400157d8  mov     [rsp+68h+arg_8], eax
0x1400157dc  call    ?TryRecoverFromAccessDenied@COSKUtils@@SAXPEAJ@Z; COSKUtils::TryRecoverFromAccessDenied(long *)
0x1400157e1  mov     r9d, [rsp+68h+arg_8]
0x1400157e6  test    r9d, r9d
0x1400157e9  jns     short loc_140015819
0x1400157eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400157f2  lea     rax, WPP_GLOBAL_Control
0x1400157f9  cmp     rcx, rax
0x1400157fc  jz      short loc_140015819
0x1400157fe  test    [rcx+1Ch], dil
0x140015802  jz      short loc_140015819
0x140015804  mov     rcx, [rcx+10h]
0x140015808  lea     r8, WPP_701f9d48580b340774086315e62b6ed1_Traceguids
0x14001580f  mov     edx, 11h
0x140015814  call    WPP_SF_d
0x140015819  cmp     r15w, [rbx+66h]
0x14001581e  jz      short loc_140015837
0x140015820  movzx   edx, word ptr [rbx+66h]; lpString
0x140015824  mov     rcx, rsi; hWnd
0x140015827  call    cs:__imp_RemovePropW
0x14001582d  movzx   ecx, word ptr [rbx+66h]; nAtom
0x140015831  call    cs:__imp_GlobalDeleteAtom
0x140015837  cmp     [rbx+7Ch], r15b
0x14001583b  jz      short loc_14001584D
0x14001583d  xor     r9d, r9d; bool
0x140015840  xor     r8d, r8d; bool
0x140015843  xor     edx, edx; bool
0x140015845  mov     rcx, rbx; this
0x140015848  call    ?SetOSKWindowDockedState@COskNativeHWNDHost@@AEAAJ_N00@Z; COskNativeHWNDHost::SetOSKWindowDockedState(bool,bool,bool)
0x14001584d  mov     rcx, rsi; hWnd
0x140015850  call    cs:__imp_DestroyWindow
0x140015856  jmp     loc_140015C40
0x14001585b  lea     rax, [r8-1]
0x14001585f  cmp     rax, rdi
0x140015862  ja      loc_140015C43
0x140015868  test    rsi, rsi
0x14001586b  jz      short loc_140015891
0x14001586d  call    ?GetHWND@COskOptionsDlg@@SAPEAUHWND__@@XZ; COskOptionsDlg::GetHWND(void)
0x140015872  cmp     rsi, rax
0x140015875  jz      short loc_140015881
0x140015877  call    ?GetHWND@COskMessageDlg@@SAPEAUHWND__@@XZ; COskMessageDlg::GetHWND(void)
0x14001587c  cmp     rsi, rax
0x14001587f  jnz     short loc_140015891
0x140015881  mov     rcx, rbx; this
0x140015884  call    ?SetForegroundWindowFromCachedHandle@COskNativeHWNDHost@@AEAAXXZ; COskNativeHWNDHost::SetForegroundWindowFromCachedHandle(void)
0x140015889  mov     [r14], r15
0x14001588c  jmp     loc_140015C40
0x140015891  call    ?GetHWND@COskMessageDlg@@SAPEAUHWND__@@XZ; COskMessageDlg::GetHWND(void)
0x140015896  test    rax, rax
0x140015899  jnz     short loc_1400158A9
0x14001589b  call    ?GetHWND@COskOptionsDlg@@SAPEAUHWND__@@XZ; COskOptionsDlg::GetHWND(void)
0x1400158a0  test    rax, rax
0x1400158a3  jz      loc_140015C43
0x1400158a9  mov     rcx, rax; hWnd
0x1400158ac  call    cs:__imp_SetForegroundWindow
0x1400158b2  jmp     loc_140015C43
0x1400158b7  mov     rdx, rbp; unsigned __int64
0x1400158ba  call    ?OnSizeChanged@COskNativeHWNDHost@@AEAAX_K@Z; COskNativeHWNDHost::OnSizeChanged(unsigned __int64)
0x1400158bf  jmp     loc_140015C43
0x1400158c4  call    ?OnPositionChanged@COskNativeHWNDHost@@AEAAXXZ; COskNativeHWNDHost::OnPositionChanged(void)
0x1400158c9  jmp     loc_140015C43
0x1400158ce  test    rbp, rbp
0x1400158d1  jnz     loc_140015C43
0x1400158d7  xor     r8d, r8d; int
0x1400158da  xor     edx, edx; bool
0x1400158dc  call    ?ShowOSKToolTip@COskNativeHWNDHost@@AEAAX_NH@Z; COskNativeHWNDHost::ShowOSKToolTip(bool,int)
0x1400158e1  cmp     [rbx+38h], r15
0x1400158e5  jz      short loc_140015889
0x1400158e7  call    ?GetHWND@COskOptionsDlg@@SAPEAUHWND__@@XZ; COskOptionsDlg::GetHWND(void)
0x1400158ec  test    rax, rax
0x1400158ef  jnz     short loc_1400158FB
0x1400158f1  call    ?GetHWND@COskMessageDlg@@SAPEAUHWND__@@XZ; COskMessageDlg::GetHWND(void)
0x1400158f6  test    rax, rax
0x1400158f9  jz      short loc_140015889
0x1400158fb  mov     [rbx+38h], r15
0x1400158ff  jmp     short loc_140015889
0x140015901  sub     edx, 20h ; ' '
0x140015904  jz      loc_1400159A1
0x14001590a  sub     edx, edi
0x14001590c  jz      short loc_140015985
0x14001590e  sub     edx, 3
0x140015911  jz      short loc_140015969
0x140015913  sub     edx, 5Ah ; 'Z'
0x140015916  jz      short loc_14001595F
0x140015918  sub     edx, 93h; unsigned int
0x14001591e  jz      short loc_140015955
0x140015920  sub     edx, edi
0x140015922  jz      short loc_140015939
0x140015924  cmp     edx, edi
0x140015926  jnz     loc_140015C43
0x14001592c  mov     rdx, rbp; unsigned __int64
0x14001592f  call    ?OnTimer@COskNativeHWNDHost@@AEAAX_K@Z; COskNativeHWNDHost::OnTimer(unsigned __int64)
0x140015934  jmp     loc_140015889
0x140015939  cmp     [rcx+7Ch], r15b
0x14001593d  jz      loc_140015C43
0x140015943  cmp     rbp, 0F020h
0x14001594a  jnz     loc_140015C43
0x140015950  jmp     loc_140015C40
0x140015955  call    ?OnCommand@COskNativeHWNDHost@@AEAAXI_K_J@Z; COskNativeHWNDHost::OnCommand(uint,unsigned __int64,__int64)
0x14001595a  jmp     loc_140015C43
0x14001595f  call    ?HandleDisplayChange@COskNativeHWNDHost@@AEAAXXZ; COskNativeHWNDHost::HandleDisplayChange(void)
0x140015964  jmp     loc_140015C43
0x140015969  test    rsi, rsi
0x14001596c  jz      loc_140015C43
0x140015972  mov     eax, [rcx+5Ch]
0x140015975  mov     [r9+18h], eax
0x140015979  mov     eax, [rcx+60h]
0x14001597c  mov     [r9+1Ch], eax
0x140015980  jmp     loc_140015C43
0x140015985  cmp     si, di
0x140015988  mov     eax, 3
0x14001598d  cmovnz  rax, rdi
0x140015991  mov     [r14], rax
0x140015994  mov     eax, r15d
0x140015997  setnz   al
0x14001599a  mov     edi, eax
0x14001599c  jmp     loc_140015C43
0x1400159a1  mov     rdx, rsi; __int64
0x1400159a4  call    ?OnSetCursor@COskNativeHWNDHost@@AEAAX_J@Z; COskNativeHWNDHost::OnSetCursor(__int64)
0x1400159a9  jmp     loc_140015C43
0x1400159ae  mov     [rcx+40h], r15d
0x1400159b2  jmp     loc_140015C43
0x1400159b7  mov     eax, 40Ch
0x1400159bc  cmp     edx, eax
0x1400159be  ja      loc_140015B1B
0x1400159c4  jz      loc_140015B11
0x1400159ca  sub     edx, 231h
0x1400159d0  jz      loc_140015AF7
0x1400159d6  sub     edx, edi
0x1400159d8  jz      loc_140015ADF
0x1400159de  sub     edx, 0E8h
0x1400159e4  jz      loc_14001575C
0x1400159ea  sub     edx, 4
0x1400159ed  jz      loc_140015AD5
0x1400159f3  sub     edx, 97h
0x1400159f9  jz      short loc_140015A75
0x1400159fb  sub     edx, 55h ; 'U'
0x1400159fe  jz      short loc_140015A43
0x140015a00  cmp     edx, edi
0x140015a02  jnz     loc_140015C43
0x140015a08  mov     rcx, cs:WPP_GLOBAL_Control
0x140015a0f  lea     rax, WPP_GLOBAL_Control
0x140015a16  cmp     rcx, rax
0x140015a19  jz      loc_140015AC8
0x140015a1f  test    byte ptr [rcx+1Ch], 10h
0x140015a23  jz      loc_140015AC8
0x140015a29  mov     rcx, [rcx+10h]
0x140015a2d  lea     r8, WPP_701f9d48580b340774086315e62b6ed1_Traceguids
0x140015a34  mov     edx, 10h
0x140015a39  call    WPP_SF_
0x140015a3e  jmp     loc_140015AC8
0x140015a43  mov     rcx, [rcx+8]; hWnd
0x140015a47  lea     rdx, [rsp+68h+Point]; lpPoint
0x140015a4f  mov     [rsp+68h+Point.x], ebp
0x140015a56  mov     [rsp+68h+Point.y], esi
0x140015a5d  call    cs:__imp_ScreenToClient
0x140015a63  lea     rdx, [rsp+68h+Point]; struct tagPOINT *
0x140015a6b  call    ?SimulateMouseClickInternal@COSKKeyboardManager@@AEAAXPEAUtagPOINT@@@Z; COSKKeyboardManager::SimulateMouseClickInternal(tagPOINT *)
0x140015a70  jmp     loc_140015C43
0x140015a75  mov     rcx, cs:WPP_GLOBAL_Control
0x140015a7c  lea     rax, WPP_GLOBAL_Control
0x140015a83  cmp     rcx, rax
0x140015a86  jz      short loc_140015AA3
0x140015a88  test    byte ptr [rcx+1Ch], 10h
0x140015a8c  jz      short loc_140015AA3
0x140015a8e  mov     rcx, [rcx+10h]
0x140015a92  lea     r8, WPP_701f9d48580b340774086315e62b6ed1_Traceguids
0x140015a99  mov     edx, 0Fh
0x140015a9e  call    WPP_SF_
0x140015aa3  mov     rcx, cs:?s_pCOSKKeyboardManager@COSKKeyboardManager@@0PEAV1@EA; COSKKeyboardManager * COSKKeyboardManager::s_pCOSKKeyboardManager
0x140015aaa  mov     eax, 3
0x140015aaf  cmp     [rcx+0A4h], eax
0x140015ab5  jnz     loc_140015C43
0x140015abb  cmp     [rcx+0B0h], r15d
0x140015ac2  jz      loc_140015C43
0x140015ac8  mov     rcx, rbx; this
0x140015acb  call    ?OnHandleScanKeyPress@COskNativeHWNDHost@@AEAAXXZ; COskNativeHWNDHost::OnHandleScanKeyPress(void)
0x140015ad0  jmp     loc_140015C43
0x140015ad5  call    ?HandleSettingChange@COSKKeyboardManager@@SAXXZ; COSKKeyboardManager::HandleSettingChange(void)
0x140015ada  jmp     loc_140015C43
0x140015adf  call    ?SetForegroundWindowFromCachedHandle@COskNativeHWNDHost@@AEAAXXZ; COskNativeHWNDHost::SetForegroundWindowFromCachedHandle(void)
0x140015ae4  xor     edx, edx; bool
0x140015ae6  mov     rcx, rbx; this
0x140015ae9  call    ?SetOSKUIBasedOnScreenResolution@COskNativeHWNDHost@@AEAAX_N@Z; COskNativeHWNDHost::SetOSKUIBasedOnScreenResolution(bool)
0x140015aee  mov     [rbx+78h], r15d
0x140015af2  jmp     loc_140015C43
0x140015af7  mov     rcx, cs:?s_pCOSKKeyboardManager@COSKKeyboardManager@@0PEAV1@EA; this
0x140015afe  test    rcx, rcx
0x140015b01  jz      loc_140015C43
0x140015b07  call    ?ClearPredictionsInternal@COSKKeyboardManager@@AEAAXXZ; COSKKeyboardManager::ClearPredictionsInternal(void)
0x140015b0c  jmp     loc_140015C43
0x140015b11  call    ?SetForegroundWindowFromCachedHandle@COskNativeHWNDHost@@AEAAXXZ; COskNativeHWNDHost::SetForegroundWindowFromCachedHandle(void)
0x140015b16  jmp     loc_140015C43
0x140015b1b  sub     edx, 40Dh
0x140015b21  jz      loc_140015C0A
0x140015b27  sub     edx, edi
0x140015b29  jz      loc_140015BE3
0x140015b2f  sub     edx, edi
0x140015b31  jz      loc_140015BD6
0x140015b37  sub     edx, 2
0x140015b3a  jz      short loc_140015BAE
0x140015b3c  sub     edx, 54h ; 'T'
0x140015b3f  jz      short loc_140015B73
0x140015b41  cmp     edx, 7F84h
0x140015b47  jnz     loc_140015C43
0x140015b4d  mov     dl, dil
0x140015b50  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OSK_SecureOnLockScreen@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OSK_SecureOnLockScreen@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OSK_SecureOnLockScreen> `wil::Feature<__WilFeatureTraits_Feature_OSK_SecureOnLockScreen>::GetImpl(void)'::`2'::impl
0x140015b57  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_OSK_SecureOnLockScreen@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OSK_SecureOnLockScreen>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x140015b5c  call    ?ShouldRunSecureOnLockScreen@COSKUtils@@SA_NXZ; COSKUtils::ShouldRunSecureOnLockScreen(void)
0x140015b61  test    al, al
0x140015b63  jnz     loc_140015C40
0x140015b69  call    ?UpdateAllListeners@OSKSettingsManager@@SAXXZ; OSKSettingsManager::UpdateAllListeners(void)
0x140015b6e  jmp     loc_140015C40
0x140015b73  mov     rcx, cs:WPP_GLOBAL_Control
0x140015b7a  lea     rax, WPP_GLOBAL_Control
0x140015b81  cmp     rcx, rax
0x140015b84  jz      short loc_140015BA1
0x140015b86  test    byte ptr [rcx+1Ch], 10h
0x140015b8a  jz      short loc_140015BA1
0x140015b8c  mov     rcx, [rcx+10h]
0x140015b90  lea     r8, WPP_701f9d48580b340774086315e62b6ed1_Traceguids
0x140015b97  mov     edx, 0Eh
0x140015b9c  call    WPP_SF_d
0x140015ba1  mov     rcx, rsi; HKL
0x140015ba4  call    ?HandleFocusChange@COSKKeyboardManager@@SAXPEAUHKL__@@@Z; COSKKeyboardManager::HandleFocusChange(HKL__ *)
0x140015ba9  jmp     loc_140015C43
0x140015bae  test    rbp, rbp
0x140015bb1  mov     r9b, dil; bool
0x140015bb4  setnz   r8b; bool
0x140015bb8  cmp     [rcx+7Ch], r15b
0x140015bbc  setz    dl; bool
0x140015bbf  call    ?SetOSKWindowDockedState@COskNativeHWNDHost@@AEAAJ_N00@Z; COskNativeHWNDHost::SetOSKWindowDockedState(bool,bool,bool)
0x140015bc4  test    rbp, rbp
0x140015bc7  jnz     short loc_140015C43
0x140015bc9  cmp     [rbx+7Ch], r15b
0x140015bcd  jz      short loc_140015C43
  ... truncated ...
```
