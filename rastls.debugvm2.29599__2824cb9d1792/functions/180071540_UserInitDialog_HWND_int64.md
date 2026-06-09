# UserInitDialog(HWND__ *,__int64)

- ea: `0x180071540`
- end: `0x1800718a6`
- name: `?UserInitDialog@@YAHPEAUHWND__@@_J@Z`
- size: `870`
- prototype: `__int64 __fastcall(HWND hWnd, struct _EAPTLS_USER_DIALOG *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800714b0`

## callees

- `0x1800075b0`
- `0x1800362d8`
- `0x18006d2c8`
- `0x18006dbd0`
- `0x18006e7a8`
- `0x18006f2b4`
- `0x18007022c`
- `0x180071540`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800717fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800717fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800717db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800717db`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007177b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007177b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071880`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071889`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071880`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071889`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ShowWindow` at `0x1800716d2`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ShowWindow` at `0x1800716de`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ShowWindow` at `0x1800716d2`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ShowWindow` at `0x1800716de`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowTextW` at `0x1800716fe`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowTextW` at `0x180071877`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowTextW` at `0x1800716fe`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowTextW` at `0x180071877`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetFocus` at `0x180071708`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetFocus` at `0x180071708`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18007164d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18007167a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x1800716aa`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18007164d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18007167a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x1800716aa`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x18007156f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x18007156f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1800717d5`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1800717d5`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x1800717f4`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x1800717f4`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!FindWindowW` at `0x1800717c2`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!FindWindowW` at `0x1800717c2`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetParent` at `0x180071578`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetParent` at `0x180071578`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18007159c`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x1800715b3`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x1800715c5`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x1800715d7`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x1800715e9`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x1800715fb`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18007160d`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18007161f`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18007159c`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x1800715b3`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x1800715c5`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x1800715d7`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x1800715e9`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x1800715fb`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18007160d`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18007161f`
- `ext-ms-win-ntuser-window-l1-1-0!BringWindowToTop` at `0x18007158e`
- `ext-ms-win-ntuser-window-l1-1-0!BringWindowToTop` at `0x18007158e`

## pseudocode

```c
__int64 __fastcall UserInitDialog(HWND hWnd, struct _EAPTLS_USER_DIALOG *a2)
{
  int v2; // r13d
  HWND v4; // rdi
  wchar_t *v5; // rbp
  wchar_t *v6; // r14
  HWND DlgItem; // rax
  HWND v8; // rax
  bool v9; // zf
  HWND v10; // r12
  struct _EAPTLS_CERT_NODE *v11; // rax
  _QWORD *v12; // r15
  unsigned int v13; // esi
  struct _EAPTLS_CERT_NODE *v14; // rdi
  const wchar_t *v15; // r9
  int v16; // eax
  const WCHAR *v17; // rdx
  UINT v18; // edx
  unsigned __int16 *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rsi
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // r9
  __int64 v25; // rax
  HWND WindowW; // rax
  DWORD LastError; // eax
  struct _EAPTLS_CONTROL_BLOCK *v28; // rcx
  __int64 v29; // rdx
  struct _EAPTLS_CERT_NODE *dwProcessId; // [rsp+68h] [rbp+10h] BYREF

  v2 = 0;
  v4 = hWnd;
  v5 = 0;
  v6 = 0;
  SetWindowLongPtrW(hWnd, 16, (LONG_PTR)a2);
  if ( !GetParent(v4) )
    CenterWindowOnDesktop(v4);
  BringWindowToTop(v4);
  DlgItem = GetDlgItem(v4, 1401);
  *((_QWORD *)a2 + 8) = DlgItem;
  if ( !DlgItem )
    *((_QWORD *)a2 + 8) = GetDlgItem(v4, 1600);
  *((_QWORD *)a2 + 9) = GetDlgItem(v4, 1011);
  *((_QWORD *)a2 + 10) = GetDlgItem(v4, 1403);
  *((_QWORD *)a2 + 11) = GetDlgItem(v4, 1405);
  *((_QWORD *)a2 + 12) = GetDlgItem(v4, 1407);
  *((_QWORD *)a2 + 13) = GetDlgItem(v4, 1408);
  v8 = GetDlgItem(v4, 1409);
  v9 = (*(_BYTE *)a2 & 4) == 0;
  v10 = (HWND)*((_QWORD *)a2 + 8);
  *((_QWORD *)a2 + 14) = v8;
  v11 = (struct _EAPTLS_CERT_NODE *)*((_QWORD *)a2 + 2);
  dwProcessId = v11;
  if ( v9 )
  {
    InitComboBox(v10, *((_QWORD *)a2 + 1), v11);
  }
  else
  {
    v12 = (_QWORD *)*((_QWORD *)a2 + 3);
    SendMessageW(v10, 0x14Bu, 0, 0);
    v13 = 0;
    if ( v12 )
    {
      v14 = dwProcessId;
      do
      {
        v15 = L" ";
        if ( v12[1] )
          v15 = (const wchar_t *)v12[1];
        SendMessageW(v10, 0x143u, 0, (LPARAM)v15);
        v9 = v12[2] == (_QWORD)v14;
        v16 = v2;
        v12 = (_QWORD *)*v12;
        if ( !v9 )
          v16 = v13;
        ++v2;
        v13 = v16;
      }
      while ( v12 );
      v4 = hWnd;
    }
    SendMessageW(v10, 0x14Eu, v13, 0);
  }
  if ( *((_QWORD *)a2 + 14) && (*(_BYTE *)a2 & 1) == 0 )
  {
    ShowWindow(*((HWND *)a2 + 13), 0);
    ShowWindow(*((HWND *)a2 + 14), 0);
  }
  DisplayCertInfo(a2);
  v17 = *(const WCHAR **)(*((_QWORD *)a2 + 4) + 40LL);
  if ( *v17 )
    SetWindowTextW(*((HWND *)a2 + 14), v17);
  SetFocus(*((HWND *)a2 + 8));
  if ( (*(_BYTE *)a2 & 2) != 0 )
  {
    v18 = 1206;
    if ( !*((_QWORD *)a2 + 5) )
      v18 = 1209;
    v19 = WszFromId(g_hInstance, v18);
    v5 = v19;
    if ( v19 )
    {
      v20 = *((_QWORD *)a2 + 5);
      if ( v20 )
      {
        v21 = -1;
        v22 = -1;
        do
          ++v22;
        while ( v19[v22] );
        v23 = -1;
        do
          ++v23;
        while ( *(_WORD *)(v20 + 2 * v23) );
        v6 = (wchar_t *)LocalAlloc(0x40u, 2 * (v23 + v22));
        if ( v6 )
        {
          v24 = *((_QWORD *)a2 + 5);
          v25 = -1;
          LODWORD(dwProcessId) = 0;
          do
            ++v25;
          while ( v5[v25] );
          do
            ++v21;
          while ( *(_WORD *)(v24 + 2 * v21) );
          swprintf_s(v6, v21 + v25, v5);
          WindowW = FindWindowW(0, v6);
          if ( WindowW )
          {
            GetWindowThreadProcessId(WindowW, (LPDWORD)&dwProcessId);
            if ( GetCurrentProcessId() == (_DWORD)dwProcessId )
            {
              if ( !PostMessageW(v4, 2u, 0, 0) )
              {
                LastError = GetLastError();
                if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                  WPP_SF_l(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    63,
                    &WPP_c4e812f99669349517681909258710e2_Traceguids,
                    LastError);
              }
              goto LABEL_45;
            }
            v28 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            {
              v29 = 64;
LABEL_43:
              WPP_SF_(*((_QWORD *)v28 + 2), v29, &WPP_c4e812f99669349517681909258710e2_Traceguids);
            }
          }
          else
          {
            v28 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            {
              v29 = 65;
              goto LABEL_43;
            }
          }
          SetWindowTextW(v4, v6);
        }
      }
    }
  }
LABEL_45:
  LocalFree(v5);
  LocalFree(v6);
  return 0;
}

```

## disassembly

```asm
0x180071540  mov     [rsp+arg_10], rbx
0x180071545  mov     [rsp+arg_0], rcx
0x18007154a  push    rbp
0x18007154b  push    rsi
0x18007154c  push    rdi
0x18007154d  push    r12
0x18007154f  push    r13
0x180071551  push    r14
0x180071553  push    r15
0x180071555  sub     rsp, 20h
0x180071559  xor     r13d, r13d
0x18007155c  mov     rbx, rdx
0x18007155f  mov     r8, rdx; dwNewLong
0x180071562  mov     rdi, rcx
0x180071565  mov     ebp, r13d
0x180071568  mov     r14d, r13d
0x18007156b  lea     edx, [r13+10h]; nIndex
0x18007156f  call    cs:__imp_SetWindowLongPtrW
0x180071575  mov     rcx, rdi; hWnd
0x180071578  call    cs:__imp_GetParent
0x18007157e  test    rax, rax
0x180071581  jnz     short loc_18007158B
0x180071583  mov     rcx, rdi; hWnd
0x180071586  call    ?CenterWindowOnDesktop@@YAXPEAUHWND__@@@Z; CenterWindowOnDesktop(HWND__ *)
0x18007158b  mov     rcx, rdi; hWnd
0x18007158e  call    cs:__imp_BringWindowToTop
0x180071594  mov     edx, 579h; nIDDlgItem
0x180071599  mov     rcx, rdi; hDlg
0x18007159c  call    cs:__imp_GetDlgItem
0x1800715a2  mov     [rbx+40h], rax
0x1800715a6  test    rax, rax
0x1800715a9  jnz     short loc_1800715BD
0x1800715ab  mov     edx, 640h; nIDDlgItem
0x1800715b0  mov     rcx, rdi; hDlg
0x1800715b3  call    cs:__imp_GetDlgItem
0x1800715b9  mov     [rbx+40h], rax
0x1800715bd  mov     edx, 3F3h; nIDDlgItem
0x1800715c2  mov     rcx, rdi; hDlg
0x1800715c5  call    cs:__imp_GetDlgItem
0x1800715cb  mov     edx, 57Bh; nIDDlgItem
0x1800715d0  mov     rcx, rdi; hDlg
0x1800715d3  mov     [rbx+48h], rax
0x1800715d7  call    cs:__imp_GetDlgItem
0x1800715dd  mov     edx, 57Dh; nIDDlgItem
0x1800715e2  mov     rcx, rdi; hDlg
0x1800715e5  mov     [rbx+50h], rax
0x1800715e9  call    cs:__imp_GetDlgItem
0x1800715ef  mov     edx, 57Fh; nIDDlgItem
0x1800715f4  mov     rcx, rdi; hDlg
0x1800715f7  mov     [rbx+58h], rax
0x1800715fb  call    cs:__imp_GetDlgItem
0x180071601  mov     edx, 580h; nIDDlgItem
0x180071606  mov     rcx, rdi; hDlg
0x180071609  mov     [rbx+60h], rax
0x18007160d  call    cs:__imp_GetDlgItem
0x180071613  mov     edx, 581h; nIDDlgItem
0x180071618  mov     rcx, rdi; hDlg
0x18007161b  mov     [rbx+68h], rax
0x18007161f  call    cs:__imp_GetDlgItem
0x180071625  test    byte ptr [rbx], 4
0x180071628  mov     r12, [rbx+40h]
0x18007162c  mov     [rbx+70h], rax
0x180071630  mov     rcx, r12; hWnd
0x180071633  mov     rax, [rbx+10h]
0x180071637  mov     [rsp+58h+dwProcessId], rax
0x18007163c  jz      short loc_1800716B5
0x18007163e  mov     r15, [rbx+18h]
0x180071642  xor     r9d, r9d; lParam
0x180071645  xor     r8d, r8d; wParam
0x180071648  mov     edx, 14Bh; Msg
0x18007164d  call    cs:__imp_SendMessageW
0x180071653  xor     esi, esi
0x180071655  test    r15, r15
0x180071658  jz      short loc_18007169C
0x18007165a  mov     rdi, [rsp+58h+dwProcessId]
0x18007165f  cmp     [r15+8], rbp
0x180071663  lea     r9, asc_180086E74; " "
0x18007166a  mov     edx, 143h; Msg
0x18007166f  mov     rcx, r12; hWnd
0x180071672  cmovnz  r9, [r15+8]; lParam
0x180071677  xor     r8d, r8d; wParam
0x18007167a  call    cs:__imp_SendMessageW
0x180071680  cmp     [r15+10h], rdi
0x180071684  mov     eax, r13d
0x180071687  mov     r15, [r15]
0x18007168a  cmovnz  eax, esi
0x18007168d  inc     r13d
0x180071690  mov     esi, eax
0x180071692  test    r15, r15
0x180071695  jnz     short loc_18007165F
0x180071697  mov     rdi, [rsp+58h+arg_0]
0x18007169c  mov     r8d, esi; wParam
0x18007169f  xor     r9d, r9d; lParam
0x1800716a2  mov     edx, 14Eh; Msg
0x1800716a7  mov     rcx, r12; hWnd
0x1800716aa  call    cs:__imp_SendMessageW
0x1800716b0  xor     r13d, r13d
0x1800716b3  jmp     short loc_1800716C1
0x1800716b5  mov     rdx, [rbx+8]; lParam
0x1800716b9  mov     r8, rax; struct _EAPTLS_CERT_NODE *
0x1800716bc  call    ?InitComboBox@@YAXPEAUHWND__@@PEAU_EAPTLS_CERT_NODE@@1@Z; InitComboBox(HWND__ *,_EAPTLS_CERT_NODE *,_EAPTLS_CERT_NODE *)
0x1800716c1  cmp     [rbx+70h], r13
0x1800716c5  jz      short loc_1800716E4
0x1800716c7  test    byte ptr [rbx], 1
0x1800716ca  jnz     short loc_1800716E4
0x1800716cc  mov     rcx, [rbx+68h]; hWnd
0x1800716d0  xor     edx, edx; nCmdShow
0x1800716d2  call    cs:__imp_ShowWindow
0x1800716d8  mov     rcx, [rbx+70h]; hWnd
0x1800716dc  xor     edx, edx; nCmdShow
0x1800716de  call    cs:__imp_ShowWindow
0x1800716e4  mov     rcx, rbx; struct _EAPTLS_USER_DIALOG *
0x1800716e7  call    ?DisplayCertInfo@@YAXPEAU_EAPTLS_USER_DIALOG@@@Z; DisplayCertInfo(_EAPTLS_USER_DIALOG *)
0x1800716ec  mov     rax, [rbx+20h]
0x1800716f0  mov     rdx, [rax+28h]; lpString
0x1800716f4  cmp     [rdx], r13w
0x1800716f8  jz      short loc_180071704
0x1800716fa  mov     rcx, [rbx+70h]; hWnd
0x1800716fe  call    cs:__imp_SetWindowTextW
0x180071704  mov     rcx, [rbx+40h]; hWnd
0x180071708  call    cs:__imp_SetFocus
0x18007170e  test    byte ptr [rbx], 2
0x180071711  jz      loc_18007187D
0x180071717  mov     edx, 4B6h
0x18007171c  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180071723  cmp     [rbx+28h], r13
0x180071727  jnz     short loc_18007172E
0x180071729  mov     edx, 4B9h; uID
0x18007172e  call    ?WszFromId@@YAPEAGPEAUHINSTANCE__@@K@Z; WszFromId(HINSTANCE__ *,ulong)
0x180071733  mov     rbp, rax
0x180071736  test    rax, rax
0x180071739  jz      loc_18007187D
0x18007173f  mov     rdx, [rbx+28h]
0x180071743  test    rdx, rdx
0x180071746  jz      loc_18007187D
0x18007174c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180071750  mov     rcx, rsi
0x180071753  inc     rcx
0x180071756  cmp     [rbp+rcx*2+0], r13w
0x18007175c  jnz     short loc_180071753
0x18007175e  mov     rax, rsi
0x180071761  inc     rax
0x180071764  cmp     [rdx+rax*2], r13w
0x180071769  jnz     short loc_180071761
0x18007176b  lea     rdx, [rax+rcx]
0x18007176f  mov     r15d, 40h ; '@'
0x180071775  add     rdx, rdx; uBytes
0x180071778  mov     ecx, r15d; uFlags
0x18007177b  call    cs:__imp_LocalAlloc
0x180071781  mov     r14, rax
0x180071784  test    rax, rax
0x180071787  jz      loc_18007187D
0x18007178d  mov     r9, [rbx+28h]
0x180071791  mov     rax, rsi
0x180071794  mov     dword ptr [rsp+58h+dwProcessId], r13d
0x180071799  inc     rax
0x18007179c  cmp     [rbp+rax*2+0], r13w
0x1800717a2  jnz     short loc_180071799
0x1800717a4  inc     rsi
0x1800717a7  cmp     [r9+rsi*2], r13w
0x1800717ac  jnz     short loc_1800717A4
0x1800717ae  lea     rdx, [rsi+rax]; BufferCount
0x1800717b2  mov     r8, rbp; Format
0x1800717b5  mov     rcx, r14; Buffer
0x1800717b8  call    swprintf_s
0x1800717bd  mov     rdx, r14; lpWindowName
0x1800717c0  xor     ecx, ecx; lpClassName
0x1800717c2  call    cs:__imp_FindWindowW
0x1800717c8  test    rax, rax
0x1800717cb  jz      short loc_180071849
0x1800717cd  lea     rdx, [rsp+58h+dwProcessId]; lpdwProcessId
0x1800717d2  mov     rcx, rax; hWnd
0x1800717d5  call    cs:__imp_GetWindowThreadProcessId
0x1800717db  call    cs:__imp_GetCurrentProcessId
0x1800717e1  cmp     eax, dword ptr [rsp+58h+dwProcessId]
0x1800717e5  jnz     short loc_180071831
0x1800717e7  xor     r9d, r9d; lParam
0x1800717ea  xor     r8d, r8d; wParam
0x1800717ed  mov     rcx, rdi; hWnd
0x1800717f0  lea     edx, [r9+2]; Msg
0x1800717f4  call    cs:__imp_PostMessageW
0x1800717fa  test    eax, eax
0x1800717fc  jnz     short loc_18007187D
0x1800717fe  call    cs:__imp_GetLastError
0x180071804  mov     rcx, cs:WPP_GLOBAL_Control
0x18007180b  lea     rdx, WPP_GLOBAL_Control
0x180071812  cmp     rcx, rdx
0x180071815  jz      short loc_18007187D
0x180071817  mov     rcx, [rcx+10h]
0x18007181b  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x180071822  mov     edx, 3Fh ; '?'
0x180071827  mov     r9d, eax
0x18007182a  call    WPP_SF_l
0x18007182f  jmp     short loc_18007187D
0x180071831  mov     rcx, cs:WPP_GLOBAL_Control
0x180071838  lea     rdx, WPP_GLOBAL_Control
0x18007183f  cmp     rcx, rdx
0x180071842  jz      short loc_180071871
0x180071844  mov     edx, r15d
0x180071847  jmp     short loc_180071861
0x180071849  mov     rcx, cs:WPP_GLOBAL_Control
0x180071850  lea     rdx, WPP_GLOBAL_Control
0x180071857  cmp     rcx, rdx
0x18007185a  jz      short loc_180071871
0x18007185c  mov     edx, 41h ; 'A'
0x180071861  mov     rcx, [rcx+10h]
0x180071865  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x18007186c  call    WPP_SF_
0x180071871  mov     rdx, r14; lpString
0x180071874  mov     rcx, rdi; hWnd
0x180071877  call    cs:__imp_SetWindowTextW
0x18007187d  mov     rcx, rbp; hMem
0x180071880  call    cs:__imp_LocalFree
0x180071886  mov     rcx, r14; hMem
0x180071889  call    cs:__imp_LocalFree
0x18007188f  mov     rbx, [rsp+58h+arg_10]
0x180071894  xor     eax, eax
0x180071896  add     rsp, 20h
0x18007189a  pop     r15
0x18007189c  pop     r14
0x18007189e  pop     r13
0x1800718a0  pop     r12
0x1800718a2  pop     rdi
0x1800718a3  pop     rsi
0x1800718a4  pop     rbp
0x1800718a5  retn
```
