# DetailsView::Finder::ConnectToolbarCombo(HWND__ *)

- ea: `0x1800092f4`
- end: `0x180009464`
- name: `?ConnectToolbarCombo@Finder@DetailsView@@QEAAXPEAUHWND__@@@Z`
- size: `368`
- prototype: `void __fastcall(LONG_PTR dwNewLong, HWND hWnd)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009b34`

## callees

- `0x180001510`
- `0x1800092f4`

## import_xrefs

- `SHLWAPI!__imp_StrCmpICW` at `0x1800093ea`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800093ea`
- `USER32!GetTopWindow` at `0x1800093b5`
- `USER32!GetTopWindow` at `0x1800093b5`
- `USER32!GetWindow` at `0x1800093fc`
- `USER32!GetWindow` at `0x1800093fc`
- `USER32!GetClassNameW` at `0x1800093d9`
- `USER32!GetClassNameW` at `0x1800093d9`
- `USER32!GetParent` at `0x180009326`
- `USER32!GetParent` at `0x180009332`
- `USER32!GetParent` at `0x180009326`
- `USER32!GetParent` at `0x180009332`
- `USER32!SendMessageW` at `0x180009349`
- `USER32!SendMessageW` at `0x1800093ac`
- `USER32!SendMessageW` at `0x180009349`
- `USER32!SendMessageW` at `0x1800093ac`
- `USER32!GetWindowLongPtrW` at `0x180009424`
- `USER32!GetWindowLongPtrW` at `0x180009424`
- `USER32!SetWindowLongPtrW` at `0x180009414`
- `USER32!SetWindowLongPtrW` at `0x18000943a`
- `USER32!SetWindowLongPtrW` at `0x180009414`
- `USER32!SetWindowLongPtrW` at `0x18000943a`

## pseudocode

```c
void __fastcall DetailsView::Finder::ConnectToolbarCombo(LONG_PTR dwNewLong, HWND hWnd)
{
  HWND Parent; // rbx
  HWND v5; // r14
  HWND v6; // rcx
  HWND i; // rax
  HWND v8; // rbx
  LPARAM lParam[2]; // [rsp+20h] [rbp-60h] BYREF
  __int128 v10; // [rsp+30h] [rbp-50h]
  __int64 v11; // [rsp+40h] [rbp-40h]
  HINSTANCE v12; // [rsp+48h] [rbp-38h]
  __int64 v13; // [rsp+50h] [rbp-30h]
  __int64 v14; // [rsp+58h] [rbp-28h]
  __int64 v15; // [rsp+60h] [rbp-20h]

  *(_QWORD *)dwNewLong = hWnd;
  Parent = GetParent(hWnd);
  v5 = GetParent(Parent);
  v6 = (HWND)SendMessageW(Parent, 0x423u, 0, 0);
  if ( v6 )
  {
    v12 = g_hInstDll;
    v11 = 0;
    v14 = 0;
    v15 = 0;
    lParam[0] = 0x1300000048LL;
    v13 = 40517;
    lParam[1] = (LPARAM)v5;
    v10 = (unsigned __int64)hWnd;
    SendMessageW(v6, 0x432u, 0, (LPARAM)lParam);
  }
  for ( i = GetTopWindow(*(HWND *)dwNewLong); ; i = GetWindow(v8, 2u) )
  {
    v8 = i;
    if ( !i )
      break;
    v11 = 0;
    *(_OWORD *)lParam = 0;
    v10 = 0;
    GetClassNameW(i, (LPWSTR)lParam, 20);
    if ( !StrCmpICW((LPCWSTR)lParam, L"Edit") )
    {
      SetWindowLongPtrW(v8, -21, dwNewLong);
      *(_QWORD *)(dwNewLong + 24) = GetWindowLongPtrW(v8, -4);
      SetWindowLongPtrW(v8, -4, (LONG_PTR)DetailsView::Finder::ToolbarComboSubClassWndProc);
      return;
    }
  }
}

```

## disassembly

```asm
0x1800092f4  mov     [rsp-18h+arg_10], rbx
0x1800092f9  mov     [rsp-18h+arg_18], rsi
0x1800092fe  push    rbp
0x1800092ff  push    rdi
0x180009300  push    r14
0x180009302  mov     rbp, rsp
0x180009305  sub     rsp, 80h
0x18000930c  mov     rax, cs:__security_cookie
0x180009313  xor     rax, rsp
0x180009316  mov     [rbp+var_10], rax
0x18000931a  mov     rdi, rcx
0x18000931d  mov     [rcx], rdx
0x180009320  mov     rcx, rdx; hWnd
0x180009323  mov     rsi, rdx
0x180009326  call    cs:__imp_GetParent
0x18000932c  mov     rcx, rax; hWnd
0x18000932f  mov     rbx, rax
0x180009332  call    cs:__imp_GetParent
0x180009338  xor     r9d, r9d; lParam
0x18000933b  xor     r8d, r8d; wParam
0x18000933e  mov     edx, 423h; Msg
0x180009343  mov     rcx, rbx; hWnd
0x180009346  mov     r14, rax
0x180009349  call    cs:__imp_SendMessageW
0x18000934f  mov     rcx, rax; hWnd
0x180009352  test    rax, rax
0x180009355  jz      short loc_1800093B2
0x180009357  mov     rax, cs:?g_hInstDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstDll
0x18000935e  lea     r9, [rbp+lParam]; lParam
0x180009362  xor     r8d, r8d; wParam
0x180009365  mov     [rbp+var_38], rax
0x180009369  mov     edx, 432h; Msg
0x18000936e  mov     qword ptr [rbp+var_50+8], 0
0x180009376  mov     [rbp+var_40], 0
0x18000937e  mov     [rbp+var_28], 0
0x180009386  mov     [rbp+var_20], 0
0x18000938e  mov     dword ptr [rbp+lParam], 48h ; 'H'
0x180009395  mov     dword ptr [rbp+lParam+4], 13h
0x18000939c  mov     [rbp+var_30], 9E45h
0x1800093a4  mov     [rbp+lParam+8], r14
0x1800093a8  mov     qword ptr [rbp+var_50], rsi
0x1800093ac  call    cs:__imp_SendMessageW
0x1800093b2  mov     rcx, [rdi]; hWnd
0x1800093b5  call    cs:__imp_GetTopWindow
0x1800093bb  jmp     short loc_180009402
0x1800093bd  xor     eax, eax
0x1800093bf  lea     rdx, [rbp+lParam]; lpClassName
0x1800093c3  xorps   xmm0, xmm0
0x1800093c6  mov     [rbp+var_40], rax
0x1800093ca  mov     rcx, rbx; hWnd
0x1800093cd  movups  xmmword ptr [rbp+lParam], xmm0
0x1800093d1  lea     r8d, [rax+14h]; nMaxCount
0x1800093d5  movups  [rbp+var_50], xmm0
0x1800093d9  call    cs:__imp_GetClassNameW
0x1800093df  lea     rdx, pszStr2; "Edit"
0x1800093e6  lea     rcx, [rbp+lParam]; pszStr1
0x1800093ea  call    cs:__imp_StrCmpICW
0x1800093f0  mov     rcx, rbx; hWnd
0x1800093f3  test    eax, eax
0x1800093f5  jz      short loc_18000940C
0x1800093f7  mov     edx, 2; uCmd
0x1800093fc  call    cs:__imp_GetWindow
0x180009402  mov     rbx, rax
0x180009405  test    rax, rax
0x180009408  jnz     short loc_1800093BD
0x18000940a  jmp     short loc_180009440
0x18000940c  mov     r8, rdi; dwNewLong
0x18000940f  mov     edx, 0FFFFFFEBh; nIndex
0x180009414  call    cs:__imp_SetWindowLongPtrW
0x18000941a  mov     esi, 0FFFFFFFCh
0x18000941f  mov     rcx, rbx; hWnd
0x180009422  mov     edx, esi; nIndex
0x180009424  call    cs:__imp_GetWindowLongPtrW
0x18000942a  lea     r8, ?ToolbarComboSubClassWndProc@Finder@DetailsView@@SA_JPEAUHWND__@@I_K_J@Z; dwNewLong
0x180009431  mov     edx, esi; nIndex
0x180009433  mov     rcx, rbx; hWnd
0x180009436  mov     [rdi+18h], rax
0x18000943a  call    cs:__imp_SetWindowLongPtrW
0x180009440  mov     rcx, [rbp+var_10]
0x180009444  xor     rcx, rsp; StackCookie
0x180009447  call    __security_check_cookie
0x18000944c  lea     r11, [rsp+80h+var_s0]
0x180009454  mov     rbx, [r11+30h]
0x180009458  mov     rsi, [r11+38h]
0x18000945c  mov     rsp, r11
0x18000945f  pop     r14
0x180009461  pop     rdi
0x180009462  pop     rbp
0x180009463  retn
```
