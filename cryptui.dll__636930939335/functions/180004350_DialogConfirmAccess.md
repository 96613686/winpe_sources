# DialogConfirmAccess

- ea: `0x180004350`
- end: `0x1800046d9`
- name: `DialogConfirmAccess`
- size: `905`
- prototype: `__int64 __fastcall(HWND hWndParent)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180003600`
- `0x1800038ac`
- `0x180004350`
- `0x180004f2c`
- `0x180004fe0`
- `0x1800052f0`
- `0x18003e576`
- `0x18003e5c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004534`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000453e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004534`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000453e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004518`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004518`
- `USER32!SetWindowLongPtrW` at `0x180004529`
- `USER32!SetWindowLongPtrW` at `0x180004529`
- `USER32!SendMessageW` at `0x18000444f`
- `USER32!SendMessageW` at `0x18000463c`
- `USER32!SendMessageW` at `0x18000444f`
- `USER32!SendMessageW` at `0x18000463c`
- `USER32!EndDialog` at `0x1800043ee`
- `USER32!EndDialog` at `0x18000450b`
- `USER32!EndDialog` at `0x180004549`
- `USER32!EndDialog` at `0x1800043ee`
- `USER32!EndDialog` at `0x18000450b`
- `USER32!EndDialog` at `0x180004549`
- `USER32!SetWindowTextW` at `0x180004566`
- `USER32!SetWindowTextW` at `0x180004589`
- `USER32!SetWindowTextW` at `0x18000461a`
- `USER32!SetWindowTextW` at `0x180004566`
- `USER32!SetWindowTextW` at `0x180004589`
- `USER32!SetWindowTextW` at `0x18000461a`
- `USER32!GetWindowLongPtrW` at `0x1800043b2`
- `USER32!GetWindowLongPtrW` at `0x180004406`
- `USER32!GetWindowLongPtrW` at `0x1800043b2`
- `USER32!GetWindowLongPtrW` at `0x180004406`
- `USER32!ShowWindow` at `0x1800045db`
- `USER32!ShowWindow` at `0x18000465d`
- `USER32!ShowWindow` at `0x18000468f`
- `USER32!ShowWindow` at `0x1800045db`
- `USER32!ShowWindow` at `0x18000465d`
- `USER32!ShowWindow` at `0x18000468f`
- `USER32!GetDlgItem` at `0x18000443b`
- `USER32!GetDlgItem` at `0x180004468`
- `USER32!GetDlgItem` at `0x18000457d`
- `USER32!GetDlgItem` at `0x1800045d0`
- `USER32!GetDlgItem` at `0x18000460a`
- `USER32!GetDlgItem` at `0x180004628`
- `USER32!GetDlgItem` at `0x180004652`
- `USER32!GetDlgItem` at `0x18000466b`
- `USER32!GetDlgItem` at `0x180004684`
- `USER32!GetDlgItem` at `0x18000469d`
- `USER32!GetDlgItem` at `0x18000443b`
- `USER32!GetDlgItem` at `0x180004468`
- `USER32!GetDlgItem` at `0x18000457d`
- `USER32!GetDlgItem` at `0x1800045d0`
- `USER32!GetDlgItem` at `0x18000460a`
- `USER32!GetDlgItem` at `0x180004628`
- `USER32!GetDlgItem` at `0x180004652`
- `USER32!GetDlgItem` at `0x18000466b`
- `USER32!GetDlgItem` at `0x180004684`
- `USER32!GetDlgItem` at `0x18000469d`
- `USER32!EnableWindow` at `0x180004676`
- `USER32!EnableWindow` at `0x1800046a8`
- `USER32!EnableWindow` at `0x180004676`
- `USER32!EnableWindow` at `0x1800046a8`
- `USER32!GetWindowTextW` at `0x18000447c`
- `USER32!GetWindowTextW` at `0x18000447c`

## pseudocode

```c
__int64 __fastcall DialogConfirmAccess(HWND hWndParent, int a2, __int16 a3, LONG_PTR a4)
{
  int v6; // edx
  LONG_PTR WindowLongPtrW; // rax
  LONG_PTR v9; // rax
  _QWORD *v10; // rsi
  HWND v11; // rax
  BOOL v12; // ebp
  HWND v13; // rax
  __int64 WindowTextW; // r14
  __int64 v15; // rcx
  WCHAR *v16; // rax
  DWORD LastError; // eax
  __int64 v18; // rbp
  const WCHAR *v19; // rdx
  const WCHAR *v20; // rbx
  HWND DlgItem; // rax
  int v22; // eax
  HWND v23; // rax
  int v24; // edx
  HWND v25; // rax
  HWND v26; // rax
  HWND v27; // rax
  HWND v28; // rax
  HWND v29; // rax
  HWND v30; // rax
  WCHAR String[256]; // [rsp+30h] [rbp-228h] BYREF

  v6 = a2 - 272;
  if ( !v6 )
  {
    SetLastError(0);
    if ( !SetWindowLongPtrW(hWndParent, -21, a4) && GetLastError() )
    {
      LastError = GetLastError();
      EndDialog(hWndParent, LastError);
      return 0;
    }
    v18 = *(_QWORD *)(a4 + 8);
    v19 = *(const WCHAR **)(v18 + 16);
    if ( v19 )
      SetWindowTextW(hWndParent, v19);
    v20 = *(const WCHAR **)(a4 + 16);
    if ( v20 )
    {
      DlgItem = GetDlgItem(hWndParent, 1035);
      SetWindowTextW(DlgItem, v20);
    }
    if ( (*(_BYTE *)(v18 + 4) & 8) == 0 )
    {
      v27 = GetDlgItem(hWndParent, 1030);
      ShowWindow(v27, 0);
      v28 = GetDlgItem(hWndParent, 1030);
      EnableWindow(v28, 0);
      v29 = GetDlgItem(hWndParent, 1020);
      ShowWindow(v29, 0);
      v24 = 1020;
      goto LABEL_44;
    }
    v22 = g_dwAllowCachePW;
    if ( !g_dwAllowCachePW )
    {
      if ( !IsCachePWAllowed() )
      {
        g_dwAllowCachePW = 1;
LABEL_40:
        v23 = GetDlgItem(hWndParent, 1030);
        ShowWindow(v23, 0);
        v24 = 1030;
LABEL_44:
        v30 = GetDlgItem(hWndParent, v24);
        EnableWindow(v30, 0);
        return 1;
      }
      v22 = 2;
      g_dwAllowCachePW = 2;
    }
    if ( v22 != 1 )
    {
      if ( (unsigned int)SearchProtectPasswordCache(*(_QWORD *)a4, *(_QWORD *)(a4 + 24), 0) )
      {
        v25 = GetDlgItem(hWndParent, 1020);
        SetWindowTextW(v25, g_szGooPassword);
        v26 = GetDlgItem(hWndParent, 1030);
        SendMessageW(v26, 0xF1u, 1u, 0);
        *(_DWORD *)(a4 + 32) = 1;
        *(_DWORD *)(a4 + 44) = 1;
      }
      return 1;
    }
    goto LABEL_40;
  }
  if ( v6 != 1 )
    return 0;
  if ( a3 != 1 )
  {
    if ( a3 == 2 )
    {
      EndDialog(hWndParent, 1223);
      return 1;
    }
    if ( a3 == 1029 )
    {
      WindowLongPtrW = GetWindowLongPtrW(hWndParent, -21);
      if ( WindowLongPtrW )
        IsolationAwareDialogBoxParamW(
          g_hInstProtectUI,
          (LPCWSTR)0x9B,
          hWndParent,
          (DLGPROC)DialogAdvancedSecurityDetails,
          WindowLongPtrW);
    }
    return 0;
  }
  v9 = GetWindowLongPtrW(hWndParent, -21);
  v10 = (_QWORD *)v9;
  if ( !v9 )
    return 0;
  if ( (*(_BYTE *)(*(_QWORD *)(v9 + 8) + 4LL) & 8) != 0 )
  {
    v12 = 0;
    if ( g_dwAllowCachePW != 1 )
    {
      v11 = GetDlgItem(hWndParent, 1030);
      if ( SendMessageW(v11, 0xF0u, 0, 0) == 1 )
        v12 = 1;
    }
    v13 = GetDlgItem(hWndParent, 1020);
    WindowTextW = GetWindowTextW(v13, String, 256);
    if ( !v12 )
    {
      if ( !*((_DWORD *)v10 + 8) )
        goto LABEL_21;
      SearchProtectPasswordCache(*v10, v10[3], 1);
    }
    if ( *((_DWORD *)v10 + 8) && 2 * WindowTextW == 58 && !memcmp_0(String, g_szGooPassword, 0x3Au) )
    {
LABEL_23:
      v15 = 512;
      v16 = String;
      do
      {
        *(_BYTE *)v16 = 0;
        v16 = (WCHAR *)((char *)v16 + 1);
        --v15;
      }
      while ( v15 );
      goto LABEL_25;
    }
LABEL_21:
    ComputePasswordHash(*((_DWORD *)v10 + 9), (UCHAR *)String, 2 * WindowTextW, (UCHAR *)v10[3]);
    *((_DWORD *)v10 + 11) = 1;
    if ( v12 )
      AddProtectPasswordCache(*v10, v10[3]);
    goto LABEL_23;
  }
LABEL_25:
  EndDialog(hWndParent, 0);
  return 1;
}

```

## disassembly

```asm
0x180004350  mov     [rsp+arg_8], rbx
0x180004355  mov     [rsp+arg_10], rbp
0x18000435a  push    rsi
0x18000435b  push    rdi
0x18000435c  push    r14
0x18000435e  sub     rsp, 240h
0x180004365  mov     rax, cs:__security_cookie
0x18000436c  xor     rax, rsp
0x18000436f  mov     [rsp+258h+var_28], rax
0x180004377  mov     rsi, r9
0x18000437a  mov     rdi, rcx
0x18000437d  sub     edx, 110h
0x180004383  jz      loc_180004516
0x180004389  cmp     edx, 1
0x18000438c  jnz     loc_18000454F
0x180004392  movzx   ecx, r8w
0x180004396  sub     ecx, edx
0x180004398  jz      short loc_1800043FE
0x18000439a  sub     ecx, edx
0x18000439c  jz      short loc_1800043E6
0x18000439e  cmp     ecx, 403h
0x1800043a4  jnz     loc_18000454F
0x1800043aa  mov     edx, 0FFFFFFEBh; nIndex
0x1800043af  mov     rcx, rdi; hWnd
0x1800043b2  call    cs:__imp_GetWindowLongPtrW
0x1800043b8  test    rax, rax
0x1800043bb  jz      loc_18000454F
0x1800043c1  mov     rcx, cs:g_hInstProtectUI; hInstance
0x1800043c8  lea     r9, DialogAdvancedSecurityDetails; lpDialogFunc
0x1800043cf  mov     r8, rdi; hWndParent
0x1800043d2  mov     [rsp+258h+var_238], rax; LPARAM
0x1800043d7  mov     edx, 9Bh; lpTemplateName
0x1800043dc  call    IsolationAwareDialogBoxParamW
0x1800043e1  jmp     loc_18000454F
0x1800043e6  mov     edx, 4C7h; nResult
0x1800043eb  mov     rcx, rdi; hDlg
0x1800043ee  call    cs:__imp_EndDialog
0x1800043f4  mov     eax, 1
0x1800043f9  jmp     loc_1800046B1
0x1800043fe  mov     edx, 0FFFFFFEBh; nIndex
0x180004403  mov     rcx, rdi; hWnd
0x180004406  call    cs:__imp_GetWindowLongPtrW
0x18000440c  mov     rsi, rax
0x18000440f  test    rax, rax
0x180004412  jz      loc_18000454F
0x180004418  mov     rcx, [rax+8]
0x18000441c  mov     ebx, 1
0x180004421  test    byte ptr [rcx+4], 8
0x180004425  jz      loc_180004506
0x18000442b  cmp     cs:g_dwAllowCachePW, ebx
0x180004431  jz      short loc_18000445E
0x180004433  mov     edx, 406h; nIDDlgItem
0x180004438  mov     rcx, rdi; hDlg
0x18000443b  call    cs:__imp_GetDlgItem
0x180004441  xor     r9d, r9d; lParam
0x180004444  xor     r8d, r8d; wParam
0x180004447  mov     rcx, rax; hWnd
0x18000444a  mov     edx, 0F0h; Msg
0x18000444f  call    cs:__imp_SendMessageW
0x180004455  cmp     rax, rbx
0x180004458  jnz     short loc_18000445E
0x18000445a  mov     ebp, ebx
0x18000445c  jmp     short loc_180004460
0x18000445e  xor     ebp, ebp
0x180004460  mov     edx, 3FCh; nIDDlgItem
0x180004465  mov     rcx, rdi; hDlg
0x180004468  call    cs:__imp_GetDlgItem
0x18000446e  mov     r8d, 100h; nMaxCount
0x180004474  lea     rdx, [rsp+258h+String]; lpString
0x180004479  mov     rcx, rax; hWnd
0x18000447c  call    cs:__imp_GetWindowTextW
0x180004482  movsxd  r14, eax
0x180004485  test    ebp, ebp
0x180004487  jnz     short loc_18000449D
0x180004489  cmp     [rsi+20h], ebp
0x18000448c  jz      short loc_1800044C9
0x18000448e  mov     rdx, [rsi+18h]
0x180004492  mov     r8d, ebx
0x180004495  mov     rcx, [rsi]
0x180004498  call    SearchProtectPasswordCache
0x18000449d  cmp     dword ptr [rsi+20h], 0
0x1800044a1  jz      short loc_1800044C9
0x1800044a3  mov     rax, r14
0x1800044a6  mov     r8d, 3Ah ; ':'; Size
0x1800044ac  add     rax, rax
0x1800044af  cmp     rax, r8
0x1800044b2  jnz     short loc_1800044C9
0x1800044b4  lea     rdx, g_szGooPassword; "(*&#$(^(#%^))(*&(^(*{}_SAF^^%"
0x1800044bb  lea     rcx, [rsp+258h+String]; Buf1
0x1800044c0  call    memcmp_0
0x1800044c5  test    eax, eax
0x1800044c7  jz      short loc_1800044F1
0x1800044c9  mov     r9, [rsi+18h]
0x1800044cd  lea     r8d, [r14+r14]
0x1800044d1  mov     ecx, [rsi+24h]
0x1800044d4  lea     rdx, [rsp+258h+String]
0x1800044d9  call    ComputePasswordHash
0x1800044de  mov     [rsi+2Ch], ebx
0x1800044e1  test    ebp, ebp
0x1800044e3  jz      short loc_1800044F1
0x1800044e5  mov     rdx, [rsi+18h]
0x1800044e9  mov     rcx, [rsi]
0x1800044ec  call    AddProtectPasswordCache
0x1800044f1  mov     ecx, 200h
0x1800044f6  lea     rax, [rsp+258h+String]
0x1800044fb  mov     byte ptr [rax], 0
0x1800044fe  add     rax, rbx
0x180004501  sub     rcx, rbx
0x180004504  jnz     short loc_1800044FB
0x180004506  xor     edx, edx; nResult
0x180004508  mov     rcx, rdi; hDlg
0x18000450b  call    cs:__imp_EndDialog
0x180004511  jmp     loc_1800046AE
0x180004516  xor     ecx, ecx; dwErrCode
0x180004518  call    cs:__imp_SetLastError
0x18000451e  mov     r8, rsi; dwNewLong
0x180004521  mov     edx, 0FFFFFFEBh; nIndex
0x180004526  mov     rcx, rdi; hWnd
0x180004529  call    cs:__imp_SetWindowLongPtrW
0x18000452f  test    rax, rax
0x180004532  jnz     short loc_180004556
0x180004534  call    cs:__imp_GetLastError
0x18000453a  test    eax, eax
0x18000453c  jz      short loc_180004556
0x18000453e  call    cs:__imp_GetLastError
0x180004544  mov     edx, eax; nResult
0x180004546  mov     rcx, rdi; hDlg
0x180004549  call    cs:__imp_EndDialog
0x18000454f  xor     eax, eax
0x180004551  jmp     loc_1800046B1
0x180004556  mov     rbp, [rsi+8]
0x18000455a  mov     rdx, [rbp+10h]; lpString
0x18000455e  test    rdx, rdx
0x180004561  jz      short loc_18000456C
0x180004563  mov     rcx, rdi; hWnd
0x180004566  call    cs:__imp_SetWindowTextW
0x18000456c  mov     rbx, [rsi+10h]
0x180004570  test    rbx, rbx
0x180004573  jz      short loc_18000458F
0x180004575  mov     edx, 40Bh; nIDDlgItem
0x18000457a  mov     rcx, rdi; hDlg
0x18000457d  call    cs:__imp_GetDlgItem
0x180004583  mov     rcx, rax; hWnd
0x180004586  mov     rdx, rbx; lpString
0x180004589  call    cs:__imp_SetWindowTextW
0x18000458f  test    byte ptr [rbp+4], 8
0x180004593  mov     ebx, 1
0x180004598  jz      loc_18000464A
0x18000459e  mov     eax, cs:g_dwAllowCachePW
0x1800045a4  test    eax, eax
0x1800045a6  jnz     short loc_1800045C4
0x1800045a8  call    IsCachePWAllowed
0x1800045ad  test    eax, eax
0x1800045af  jnz     short loc_1800045B9
0x1800045b1  mov     cs:g_dwAllowCachePW, ebx
0x1800045b7  jmp     short loc_1800045C8
0x1800045b9  mov     eax, 2
0x1800045be  mov     cs:g_dwAllowCachePW, eax
0x1800045c4  cmp     eax, ebx
0x1800045c6  jnz     short loc_1800045EB
0x1800045c8  mov     edx, 406h; nIDDlgItem
0x1800045cd  mov     rcx, rdi; hDlg
0x1800045d0  call    cs:__imp_GetDlgItem
0x1800045d6  mov     rcx, rax; hWnd
0x1800045d9  xor     edx, edx; nCmdShow
0x1800045db  call    cs:__imp_ShowWindow
0x1800045e1  mov     edx, 406h
0x1800045e6  jmp     loc_18000469A
0x1800045eb  mov     rdx, [rsi+18h]
0x1800045ef  xor     r8d, r8d
0x1800045f2  mov     rcx, [rsi]
0x1800045f5  call    SearchProtectPasswordCache
0x1800045fa  test    eax, eax
0x1800045fc  jz      loc_1800046AE
0x180004602  mov     edx, 3FCh; nIDDlgItem
0x180004607  mov     rcx, rdi; hDlg
0x18000460a  call    cs:__imp_GetDlgItem
0x180004610  mov     rcx, rax; hWnd
0x180004613  lea     rdx, g_szGooPassword; "(*&#$(^(#%^))(*&(^(*{}_SAF^^%"
0x18000461a  call    cs:__imp_SetWindowTextW
0x180004620  mov     edx, 406h; nIDDlgItem
0x180004625  mov     rcx, rdi; hDlg
0x180004628  call    cs:__imp_GetDlgItem
0x18000462e  xor     r9d, r9d; lParam
0x180004631  mov     r8, rbx; wParam
0x180004634  mov     rcx, rax; hWnd
0x180004637  mov     edx, 0F1h; Msg
0x18000463c  call    cs:__imp_SendMessageW
0x180004642  mov     [rsi+20h], ebx
0x180004645  mov     [rsi+2Ch], ebx
0x180004648  jmp     short loc_1800046AE
0x18000464a  mov     edx, 406h; nIDDlgItem
0x18000464f  mov     rcx, rdi; hDlg
0x180004652  call    cs:__imp_GetDlgItem
0x180004658  mov     rcx, rax; hWnd
0x18000465b  xor     edx, edx; nCmdShow
0x18000465d  call    cs:__imp_ShowWindow
0x180004663  mov     edx, 406h; nIDDlgItem
0x180004668  mov     rcx, rdi; hDlg
0x18000466b  call    cs:__imp_GetDlgItem
0x180004671  mov     rcx, rax; hWnd
0x180004674  xor     edx, edx; bEnable
0x180004676  call    cs:__imp_EnableWindow
0x18000467c  mov     edx, 3FCh; nIDDlgItem
0x180004681  mov     rcx, rdi; hDlg
0x180004684  call    cs:__imp_GetDlgItem
0x18000468a  mov     rcx, rax; hWnd
0x18000468d  xor     edx, edx; nCmdShow
0x18000468f  call    cs:__imp_ShowWindow
0x180004695  mov     edx, 3FCh; nIDDlgItem
0x18000469a  mov     rcx, rdi; hDlg
0x18000469d  call    cs:__imp_GetDlgItem
0x1800046a3  mov     rcx, rax; hWnd
0x1800046a6  xor     edx, edx; bEnable
0x1800046a8  call    cs:__imp_EnableWindow
0x1800046ae  mov     rax, rbx
0x1800046b1  mov     rcx, [rsp+258h+var_28]
0x1800046b9  xor     rcx, rsp; StackCookie
0x1800046bc  call    __security_check_cookie
0x1800046c1  lea     r11, [rsp+258h+var_18]
0x1800046c9  mov     rbx, [r11+28h]
0x1800046cd  mov     rbp, [r11+30h]
0x1800046d1  mov     rsp, r11
0x1800046d4  pop     r14
0x1800046d6  pop     rdi
0x1800046d7  pop     rsi
0x1800046d8  retn
```
