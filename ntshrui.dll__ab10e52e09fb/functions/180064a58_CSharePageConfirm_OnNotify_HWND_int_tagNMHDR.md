# CSharePageConfirm::_OnNotify(HWND__ *,int,tagNMHDR *)

- ea: `0x180064a58`
- end: `0x180064db9`
- name: `?_OnNotify@CSharePageConfirm@@AEAA_JPEAUHWND__@@HPEAUtagNMHDR@@@Z`
- size: `865`
- prototype: `__int64 __fastcall(CSharePageConfirm *__hidden this, HWND hwnd, int, struct tagNMHDR *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180065a60`

## callees

- `0x1800254e0`
- `0x180026394`
- `0x180064774`
- `0x18006488c`
- `0x180064a58`
- `0x180064dc0`
- `0x180064f98`
- `0x1800650a8`
- `0x180065c9c`
- `0x1800678a0`
- `0x180074180`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180064d5c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180064d5c`
- `SHELL32!ShellExecuteW` at `0x180064b7c`
- `SHELL32!ShellExecuteW` at `0x180064b7c`
- `SHLWAPI!__imp_StrCmpICW` at `0x180064c4f`
- `SHLWAPI!__imp_StrCmpICW` at `0x180064cb3`
- `SHLWAPI!__imp_StrCmpICW` at `0x180064cd5`
- `SHLWAPI!__imp_StrCmpICW` at `0x180064cf6`
- `SHLWAPI!__imp_StrCmpICW` at `0x180064d14`
- `SHLWAPI!__imp_StrCmpICW` at `0x180064d2f`
- `SHLWAPI!__imp_StrCmpICW` at `0x180064c4f`
- `SHLWAPI!__imp_StrCmpICW` at `0x180064cb3`
- `SHLWAPI!__imp_StrCmpICW` at `0x180064cd5`
- `SHLWAPI!__imp_StrCmpICW` at `0x180064cf6`
- `SHLWAPI!__imp_StrCmpICW` at `0x180064d14`
- `SHLWAPI!__imp_StrCmpICW` at `0x180064d2f`
- `USER32!DestroyMenu` at `0x180064c21`
- `USER32!DestroyMenu` at `0x180064c21`
- `USER32!TrackPopupMenu` at `0x180064c09`
- `USER32!TrackPopupMenu` at `0x180064c09`
- `USER32!ClientToScreen` at `0x180064bde`
- `USER32!ClientToScreen` at `0x180064bde`
- `USER32!SetForegroundWindow` at `0x180064bc7`
- `USER32!SetForegroundWindow` at `0x180064bc7`
- `USER32!GetSubMenu` at `0x180064bb5`
- `USER32!GetSubMenu` at `0x180064bb5`
- `USER32!LoadMenuW` at `0x180064b9e`
- `USER32!LoadMenuW` at `0x180064b9e`
- `USER32!SendMessageW` at `0x180064b52`
- `USER32!SendMessageW` at `0x180064b52`

## string_xrefs

- `0x180064ccb`: `CopyLinks`
- `0x180064ca9`: `EmailLinks`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSharePageConfirm::_OnNotify(CSharePageConfirm *this, HWND hwnd, int a3, struct tagNMHDR *a4)
{
  __int64 v7; // r15
  UINT code; // eax
  HMENU MenuW; // rax
  HMENU v10; // rsi
  HMENU SubMenu; // r14
  const WCHAR *p_code; // rbx
  __int64 v13; // rcx
  CSharePageEmail *v14; // rcx
  __int64 v15; // rdx
  CSharePageConfirm *v16; // rcx
  CSharePageConfirm *v17; // rcx
  struct tagPOINT Point; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v21; // [rsp+50h] [rbp-B0h]
  __int64 v22; // [rsp+58h] [rbp-A8h]
  __int64 v23; // [rsp+60h] [rbp-A0h]
  LPARAM lParam; // [rsp+70h] [rbp-90h] BYREF
  int v25; // [rsp+78h] [rbp-88h]
  __int16 *v26; // [rsp+88h] [rbp-78h]
  int v27; // [rsp+90h] [rbp-70h]
  __int16 v28; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR File[263]; // [rsp+D2h] [rbp-2Eh] BYREF

  v7 = 0;
  if ( a4->idFrom == 4101 )
  {
LABEL_21:
    if ( ((a4->code + 4) & 0xFFFFFFFD) == 0 )
    {
      p_code = (const WCHAR *)&a4[5].code;
      if ( StrCmpICW((LPCWSTR)&a4[5].code, L"ShowErrors") )
      {
        if ( StrCmpICW(p_code, L"EmailLinks") )
        {
          if ( StrCmpICW(p_code, L"CopyLinks") )
          {
            if ( StrCmpICW(p_code, L"ShowFiles") )
            {
              if ( StrCmpICW(p_code, L"ShowShares") )
              {
                if ( !StrCmpICW(p_code, L"ShowPowerCPL") )
                {
                  Point = 0;
                  if ( CoCreateInstance(
                         &CLSID_OpenControlPanel,
                         0,
                         1u,
                         &GUID_d11ad862_66de_4df4_bf6c_1f5621996af1,
                         (LPVOID *)&Point) >= 0 )
                  {
                    (*(void (__fastcall **)(struct tagPOINT, const wchar_t *, _QWORD, _QWORD))(**(_QWORD **)&Point + 24LL))(
                      Point,
                      L"Microsoft.PowerOptions",
                      0,
                      0);
                    (*(void (__fastcall **)(struct tagPOINT))(**(_QWORD **)&Point + 16LL))(Point);
                  }
                }
              }
              else
              {
                CSharePageConfirm::_OnShowShares(v17);
              }
            }
            else
            {
              CSharePageConfirm::_OnShowFiles(v16);
            }
          }
          else
          {
            CSharePageConfirm::_OnCopyLinks((HWND *)this, v15);
          }
        }
        else
        {
          CSharePageEmail::Send(v14, *((CUserObjectList ***)this + 2));
        }
      }
      else
      {
        v13 = *((_QWORD *)this + 2);
        v20 = 0;
        v23 = 0;
        v21 = *((_QWORD *)this + 1);
        v22 = v13;
        _InterlockedIncrement((volatile signed __int32 *)(v13 + 96));
        SHFusionDialogBoxParam(v13, 3006, v21, CShareErrorDlg::s_DlgProc, &v20);
        CShareErrorDlg::~CShareErrorDlg((CShareErrorDlg *)&v20);
      }
    }
    return v7;
  }
  if ( a4->idFrom != 4102 )
  {
    if ( a4->idFrom - 4104 >= 2 )
    {
      code = a4->code;
      if ( code == -208 || code == -207 || code == -206 || code == -203 || code == -200 )
        return CSharePageConfirm::_OnPageNotify(this, hwnd, a3, a4);
      return v7;
    }
    goto LABEL_21;
  }
  if ( a4->code == -5 )
  {
    if ( LODWORD(a4[1].hwndFrom) != -1 )
    {
      MenuW = LoadMenuW(g_hInstance, (LPCWSTR)0x1392);
      v10 = MenuW;
      if ( MenuW )
      {
        SubMenu = GetSubMenu(MenuW, 0);
        if ( SubMenu )
        {
          SetForegroundWindow(*((HWND *)this + 1));
          Point = *(struct tagPOINT *)(&a4[1].code + 1);
          ClientToScreen(a4->hwndFrom, &Point);
          if ( TrackPopupMenu(SubMenu, 0x102u, Point.x, Point.y, 0, *((HWND *)this + 1), 0) == 5011 )
            CSharePageConfirm::_OnCopySelectedLinks((HWND *)this);
        }
        DestroyMenu(v10);
      }
    }
  }
  else if ( a4->code == -3 && LODWORD(a4[1].hwndFrom) != -1 )
  {
    v28 = 0;
    memset_0(&lParam, 0, 0x58u);
    v25 = 1;
    v27 = 261;
    v26 = &v28;
    SendMessageW(a4->hwndFrom, 0x1073u, SLODWORD(a4[1].hwndFrom), (LPARAM)&lParam);
    if ( v28 )
      ShellExecuteW(hwnd, 0, File, 0, 0, 1);
  }
  return v7;
}

```

## disassembly

```asm
0x180064a58  push    rbp
0x180064a5a  push    rbx
0x180064a5b  push    rsi
0x180064a5c  push    rdi
0x180064a5d  push    r12
0x180064a5f  push    r14
0x180064a61  push    r15
0x180064a63  lea     rbp, [rsp-1F0h]
0x180064a6b  sub     rsp, 2F0h
0x180064a72  mov     rax, cs:__security_cookie
0x180064a79  xor     rax, rsp
0x180064a7c  mov     [rbp+220h+var_40], rax
0x180064a83  mov     rbx, r9
0x180064a86  mov     rsi, rdx
0x180064a89  mov     rdi, rcx
0x180064a8c  xor     r12d, r12d
0x180064a8f  mov     r15d, r12d
0x180064a92  mov     rax, [r9+8]
0x180064a96  sub     rax, 1005h
0x180064a9c  jz      loc_180064C2C
0x180064aa2  sub     rax, 1
0x180064aa6  jz      short loc_180064AF4
0x180064aa8  sub     rax, 2
0x180064aac  jz      loc_180064C2C
0x180064ab2  cmp     rax, 1
0x180064ab6  jz      loc_180064C2C
0x180064abc  mov     eax, [r9+10h]
0x180064ac0  cmp     eax, 0FFFFFF30h
0x180064ac5  jz      short loc_180064AE7
0x180064ac7  cmp     eax, 0FFFFFF31h
0x180064acc  jz      short loc_180064AE7
0x180064ace  cmp     eax, 0FFFFFF32h
0x180064ad3  jz      short loc_180064AE7
0x180064ad5  cmp     eax, 0FFFFFF35h
0x180064ada  jz      short loc_180064AE7
0x180064adc  cmp     eax, 0FFFFFF38h
0x180064ae1  jnz     loc_180064D95
0x180064ae7  call    ?_OnPageNotify@CSharePageConfirm@@AEAA_JPEAUHWND__@@HPEBUtagNMHDR@@@Z; CSharePageConfirm::_OnPageNotify(HWND__ *,int,tagNMHDR const *)
0x180064aec  mov     r15, rax
0x180064aef  jmp     loc_180064D95
0x180064af4  cmp     dword ptr [r9+10h], 0FFFFFFFBh
0x180064af9  jz      loc_180064B87
0x180064aff  cmp     dword ptr [r9+10h], 0FFFFFFFDh
0x180064b04  jnz     loc_180064D95
0x180064b0a  cmp     dword ptr [r9+18h], 0FFFFFFFFh
0x180064b0f  jz      loc_180064D95
0x180064b15  mov     [rbp+220h+var_250], r12w
0x180064b1a  xor     edx, edx; Val
0x180064b1c  lea     r8d, [rdx+58h]; Size
0x180064b20  lea     rcx, [rsp+320h+lParam]; void *
0x180064b25  call    memset_0
0x180064b2a  mov     [rsp+320h+var_2A8], 1
0x180064b32  mov     [rbp+220h+var_290], 105h
0x180064b39  lea     rax, [rbp+220h+var_250]
0x180064b3d  mov     [rbp+220h+var_298], rax
0x180064b41  movsxd  r8, dword ptr [rbx+18h]; wParam
0x180064b45  lea     r9, [rsp+320h+lParam]; lParam
0x180064b4a  mov     edx, 1073h; Msg
0x180064b4f  mov     rcx, [rbx]; hWnd
0x180064b52  call    cs:__imp_SendMessageW
0x180064b58  cmp     [rbp+220h+var_250], r12w
0x180064b5d  jz      loc_180064D95
0x180064b63  mov     [rsp+320h+nShowCmd], 1; nShowCmd
0x180064b6b  mov     [rsp+320h+lpDirectory], r12; lpDirectory
0x180064b70  xor     r9d, r9d; lpParameters
0x180064b73  lea     r8, [rbp+220h+File]; lpFile
0x180064b77  xor     edx, edx; lpOperation
0x180064b79  mov     rcx, rsi; hwnd
0x180064b7c  call    cs:__imp_ShellExecuteW
0x180064b82  jmp     loc_180064D95
0x180064b87  cmp     dword ptr [r9+18h], 0FFFFFFFFh
0x180064b8c  jz      loc_180064D95
0x180064b92  mov     edx, 1392h; lpMenuName
0x180064b97  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180064b9e  call    cs:__imp_LoadMenuW
0x180064ba4  mov     rsi, rax
0x180064ba7  test    rax, rax
0x180064baa  jz      loc_180064D95
0x180064bb0  xor     edx, edx; nPos
0x180064bb2  mov     rcx, rax; hMenu
0x180064bb5  call    cs:__imp_GetSubMenu
0x180064bbb  mov     r14, rax
0x180064bbe  test    rax, rax
0x180064bc1  jz      short loc_180064C1E
0x180064bc3  mov     rcx, [rdi+8]; hWnd
0x180064bc7  call    cs:__imp_SetForegroundWindow
0x180064bcd  mov     rcx, [rbx+2Ch]
0x180064bd1  mov     qword ptr [rsp+320h+Point.x], rcx
0x180064bd6  lea     rdx, [rsp+320h+Point]; lpPoint
0x180064bdb  mov     rcx, [rbx]; hWnd
0x180064bde  call    cs:__imp_ClientToScreen
0x180064be4  mov     [rsp+320h+prcRect], r12; prcRect
0x180064be9  mov     rcx, [rdi+8]
0x180064bed  mov     qword ptr [rsp+320h+nShowCmd], rcx; hWnd
0x180064bf2  mov     dword ptr [rsp+320h+lpDirectory], r12d; nReserved
0x180064bf7  mov     r9d, [rsp+320h+Point.y]; y
0x180064bfc  mov     r8d, [rsp+320h+Point.x]; x
0x180064c01  mov     edx, 102h; uFlags
0x180064c06  mov     rcx, r14; hMenu
0x180064c09  call    cs:__imp_TrackPopupMenu
0x180064c0f  cmp     eax, 1393h
0x180064c14  jnz     short loc_180064C1E
0x180064c16  mov     rcx, rdi; this
0x180064c19  call    ?_OnCopySelectedLinks@CSharePageConfirm@@AEAAXXZ; CSharePageConfirm::_OnCopySelectedLinks(void)
0x180064c1e  mov     rcx, rsi; hMenu
0x180064c21  call    cs:__imp_DestroyMenu
0x180064c27  jmp     loc_180064D95
0x180064c2c  mov     eax, [r9+10h]
0x180064c30  add     eax, 4
0x180064c33  test    eax, 0FFFFFFFDh
0x180064c38  jnz     loc_180064D95
0x180064c3e  add     rbx, 88h
0x180064c45  lea     rdx, aShowerrors; "ShowErrors"
0x180064c4c  mov     rcx, rbx; pszStr1
0x180064c4f  call    cs:__imp_StrCmpICW
0x180064c55  test    eax, eax
0x180064c57  jnz     short loc_180064CA9
0x180064c59  mov     rcx, [rdi+10h]
0x180064c5d  mov     [rsp+320h+var_2D8], r12
0x180064c62  mov     [rsp+320h+var_2C0], r12
0x180064c67  mov     rax, [rdi+8]
0x180064c6b  mov     [rsp+320h+var_2D0], rax
0x180064c70  mov     [rsp+320h+var_2C8], rcx
0x180064c75  lock inc dword ptr [rcx+60h]
0x180064c79  lea     rax, [rsp+320h+var_2D8]
0x180064c7e  mov     [rsp+320h+lpDirectory], rax
0x180064c83  lea     r9, ?s_DlgProc@CShareErrorDlg@@CA_JPEAUHWND__@@I_K_J@Z; CShareErrorDlg::s_DlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x180064c8a  mov     r8, [rsp+320h+var_2D0]
0x180064c8f  mov     edx, 0BBEh
0x180064c94  call    SHFusionDialogBoxParam
0x180064c99  nop
0x180064c9a  lea     rcx, [rsp+320h+var_2D8]; this
0x180064c9f  call    ??1CShareErrorDlg@@QEAA@XZ; CShareErrorDlg::~CShareErrorDlg(void)
0x180064ca4  jmp     loc_180064D95
0x180064ca9  lea     rdx, aEmaillinks; "EmailLinks"
0x180064cb0  mov     rcx, rbx; pszStr1
0x180064cb3  call    cs:__imp_StrCmpICW
0x180064cb9  test    eax, eax
0x180064cbb  jnz     short loc_180064CCB
0x180064cbd  mov     rdx, [rdi+10h]; struct CSharePageSharedData *
0x180064cc1  call    ?Send@CSharePageEmail@@QEAAJPEAVCSharePageSharedData@@@Z; CSharePageEmail::Send(CSharePageSharedData *)
0x180064cc6  jmp     loc_180064D95
0x180064ccb  lea     rdx, aCopylinks; "CopyLinks"
0x180064cd2  mov     rcx, rbx; pszStr1
0x180064cd5  call    cs:__imp_StrCmpICW
0x180064cdb  test    eax, eax
0x180064cdd  jnz     short loc_180064CEC
0x180064cdf  mov     rcx, rdi; this
0x180064ce2  call    ?_OnCopyLinks@CSharePageConfirm@@AEAAXXZ; CSharePageConfirm::_OnCopyLinks(void)
0x180064ce7  jmp     loc_180064D95
0x180064cec  lea     rdx, aShowfiles; "ShowFiles"
0x180064cf3  mov     rcx, rbx; pszStr1
0x180064cf6  call    cs:__imp_StrCmpICW
0x180064cfc  test    eax, eax
0x180064cfe  jnz     short loc_180064D0A
0x180064d00  call    ?_OnShowFiles@CSharePageConfirm@@AEAAXXZ; CSharePageConfirm::_OnShowFiles(void)
0x180064d05  jmp     loc_180064D95
0x180064d0a  lea     rdx, aShowshares; "ShowShares"
0x180064d11  mov     rcx, rbx; pszStr1
0x180064d14  call    cs:__imp_StrCmpICW
0x180064d1a  test    eax, eax
0x180064d1c  jnz     short loc_180064D25
0x180064d1e  call    ?_OnShowShares@CSharePageConfirm@@AEAAXXZ; CSharePageConfirm::_OnShowShares(void)
0x180064d23  jmp     short loc_180064D95
0x180064d25  lea     rdx, aShowpowercpl; "ShowPowerCPL"
0x180064d2c  mov     rcx, rbx; pszStr1
0x180064d2f  call    cs:__imp_StrCmpICW
0x180064d35  test    eax, eax
0x180064d37  jnz     short loc_180064D95
0x180064d39  mov     qword ptr [rsp+320h+Point.x], r12
0x180064d3e  lea     rax, [rsp+320h+Point]
0x180064d43  mov     [rsp+320h+lpDirectory], rax; ppv
0x180064d48  lea     r9, _GUID_d11ad862_66de_4df4_bf6c_1f5621996af1; riid
0x180064d4f  xor     edx, edx; pUnkOuter
0x180064d51  lea     r8d, [rdx+1]; dwClsContext
0x180064d55  lea     rcx, CLSID_OpenControlPanel; rclsid
0x180064d5c  call    cs:__imp_CoCreateInstance
0x180064d62  test    eax, eax
0x180064d64  js      short loc_180064D95
0x180064d66  mov     rcx, qword ptr [rsp+320h+Point.x]
0x180064d6b  mov     rax, [rcx]
0x180064d6e  xor     r9d, r9d
0x180064d71  xor     r8d, r8d
0x180064d74  lea     rdx, aMicrosoftPower; "Microsoft.PowerOptions"
0x180064d7b  mov     rax, [rax+18h]
0x180064d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064d84  mov     rcx, qword ptr [rsp+320h+Point.x]
0x180064d89  mov     rax, [rcx]
0x180064d8c  mov     rax, [rax+10h]
0x180064d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064d95  mov     rax, r15
0x180064d98  mov     rcx, [rbp+220h+var_40]
0x180064d9f  xor     rcx, rsp; StackCookie
0x180064da2  call    __security_check_cookie
0x180064da7  add     rsp, 2F0h
0x180064dae  pop     r15
0x180064db0  pop     r14
0x180064db2  pop     r12
0x180064db4  pop     rdi
0x180064db5  pop     rsi
0x180064db6  pop     rbx
0x180064db7  pop     rbp
0x180064db8  retn
```
