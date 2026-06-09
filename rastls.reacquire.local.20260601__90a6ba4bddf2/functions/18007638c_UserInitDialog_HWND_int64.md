# UserInitDialog(HWND__ *,__int64)

- ea: `0x18007638c`
- end: `0x1800766fe`
- name: `?UserInitDialog@@YAHPEAUHWND__@@_J@Z`
- size: `882`
- prototype: `__int64 __fastcall(HWND hWnd, struct _EAPTLS_USER_DIALOG *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800762f0`

## callees

- `0x180007d00`
- `0x180038ee8`
- `0x180071b64`
- `0x1800724e8`
- `0x180073184`
- `0x180073dec`
- `0x180074e4c`
- `0x180074efc`
- `0x18007638c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076643`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076643`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180076610`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180076610`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007659a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007659a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800766d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800766e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800766d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800766e2`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ShowWindow` at `0x1800764dd`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ShowWindow` at `0x1800764ef`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ShowWindow` at `0x1800764dd`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ShowWindow` at `0x1800764ef`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowTextW` at `0x180076515`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowTextW` at `0x1800766c4`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowTextW` at `0x180076515`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowTextW` at `0x1800766c4`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetFocus` at `0x180076525`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetFocus` at `0x180076525`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x1800763af`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x1800763af`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180076604`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180076604`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18007662f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18007662f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!FindWindowW` at `0x1800765e7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!FindWindowW` at `0x1800765e7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetParent` at `0x1800763be`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetParent` at `0x1800763be`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x1800763ee`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18007640b`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180076423`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18007643b`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180076453`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18007646b`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180076483`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18007649b`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x1800763ee`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18007640b`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180076423`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18007643b`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180076453`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18007646b`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180076483`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18007649b`
- `ext-ms-win-ntuser-window-l1-1-0!BringWindowToTop` at `0x1800763da`
- `ext-ms-win-ntuser-window-l1-1-0!BringWindowToTop` at `0x1800763da`

## pseudocode

```c
__int64 __fastcall UserInitDialog(HWND hWnd, struct _EAPTLS_USER_DIALOG *a2)
{
  wchar_t *v4; // rbp
  wchar_t *v5; // r14
  HWND DlgItem; // rax
  HWND v7; // rax
  bool v8; // zf
  struct _EAPTLS_CERT_NODE *v9; // r8
  HWND v10; // rcx
  const WCHAR *v11; // rdx
  UINT v12; // edx
  unsigned __int16 *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rsi
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // r9
  __int64 v19; // rax
  HWND WindowW; // rax
  DWORD LastError; // eax
  struct _EAPTLS_CONTROL_BLOCK *v22; // rcx
  __int64 v23; // rdx
  DWORD dwProcessId; // [rsp+68h] [rbp+10h] BYREF

  v4 = 0;
  v5 = 0;
  SetWindowLongPtrW(hWnd, 16, (LONG_PTR)a2);
  if ( !GetParent(hWnd) )
    CenterWindowOnDesktop(hWnd);
  BringWindowToTop(hWnd);
  DlgItem = GetDlgItem(hWnd, 1401);
  *((_QWORD *)a2 + 8) = DlgItem;
  if ( !DlgItem )
    *((_QWORD *)a2 + 8) = GetDlgItem(hWnd, 1600);
  *((_QWORD *)a2 + 9) = GetDlgItem(hWnd, 1011);
  *((_QWORD *)a2 + 10) = GetDlgItem(hWnd, 1403);
  *((_QWORD *)a2 + 11) = GetDlgItem(hWnd, 1405);
  *((_QWORD *)a2 + 12) = GetDlgItem(hWnd, 1407);
  *((_QWORD *)a2 + 13) = GetDlgItem(hWnd, 1408);
  v7 = GetDlgItem(hWnd, 1409);
  v8 = (*(_BYTE *)a2 & 4) == 0;
  v9 = (struct _EAPTLS_CERT_NODE *)*((_QWORD *)a2 + 2);
  v10 = (HWND)*((_QWORD *)a2 + 8);
  *((_QWORD *)a2 + 14) = v7;
  if ( v8 )
    InitComboBox(v10, *((_QWORD *)a2 + 1), v9);
  else
    InitComboBoxFromGroup(v10, *((struct _EAPTLS_GROUPED_CERT_NODES **)a2 + 3), v9);
  if ( *((_QWORD *)a2 + 14) && (*(_BYTE *)a2 & 1) == 0 )
  {
    ShowWindow(*((HWND *)a2 + 13), 0);
    ShowWindow(*((HWND *)a2 + 14), 0);
  }
  DisplayCertInfo(a2);
  v11 = *(const WCHAR **)(*((_QWORD *)a2 + 4) + 40LL);
  if ( *v11 )
    SetWindowTextW(*((HWND *)a2 + 14), v11);
  SetFocus(*((HWND *)a2 + 8));
  if ( (*(_BYTE *)a2 & 2) != 0 )
  {
    v12 = 1206;
    if ( !*((_QWORD *)a2 + 5) )
      v12 = 1209;
    v13 = WszFromId(g_hInstance, v12);
    v4 = v13;
    if ( v13 )
    {
      v14 = *((_QWORD *)a2 + 5);
      if ( v14 )
      {
        v15 = -1;
        v16 = -1;
        do
          ++v16;
        while ( v13[v16] );
        v17 = -1;
        do
          ++v17;
        while ( *(_WORD *)(v14 + 2 * v17) );
        v5 = (wchar_t *)LocalAlloc(0x40u, 2 * (v17 + v16));
        if ( v5 )
        {
          v18 = *((_QWORD *)a2 + 5);
          v19 = -1;
          dwProcessId = 0;
          do
            ++v19;
          while ( v4[v19] );
          do
            ++v15;
          while ( *(_WORD *)(v18 + 2 * v15) );
          swprintf_s(v5, v15 + v19, v4);
          WindowW = FindWindowW(0, v5);
          if ( WindowW )
          {
            GetWindowThreadProcessId(WindowW, &dwProcessId);
            if ( GetCurrentProcessId() == dwProcessId )
            {
              if ( !PostMessageW(hWnd, 2u, 0, 0) )
              {
                LastError = GetLastError();
                if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                  WPP_SF_l(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    63,
                    &WPP_c4e812f99669349517681909258710e2_Traceguids,
                    LastError);
              }
              goto LABEL_37;
            }
            v22 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            {
              v23 = 64;
LABEL_35:
              WPP_SF_(*((_QWORD *)v22 + 2), v23, &WPP_c4e812f99669349517681909258710e2_Traceguids);
            }
          }
          else
          {
            v22 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            {
              v23 = 65;
              goto LABEL_35;
            }
          }
          SetWindowTextW(hWnd, v5);
        }
      }
    }
  }
LABEL_37:
  LocalFree(v4);
  LocalFree(v5);
  return 0;
}

```

## disassembly

```asm
0x18007638c  push    rbx
0x18007638e  push    rbp
0x18007638f  push    rsi
0x180076390  push    rdi
0x180076391  push    r14
0x180076393  push    r15
0x180076395  sub     rsp, 28h
0x180076399  xor     r15d, r15d
0x18007639c  mov     rbx, rdx
0x18007639f  mov     r8, rdx; dwNewLong
0x1800763a2  mov     rdi, rcx
0x1800763a5  mov     ebp, r15d
0x1800763a8  mov     r14d, r15d
0x1800763ab  lea     edx, [r15+10h]; nIndex
0x1800763af  call    cs:__imp_SetWindowLongPtrW
0x1800763b6  nop     dword ptr [rax+rax+00h]
0x1800763bb  mov     rcx, rdi; hWnd
0x1800763be  call    cs:__imp_GetParent
0x1800763c5  nop     dword ptr [rax+rax+00h]
0x1800763ca  test    rax, rax
0x1800763cd  jnz     short loc_1800763D7
0x1800763cf  mov     rcx, rdi; hWnd
0x1800763d2  call    ?CenterWindowOnDesktop@@YAXPEAUHWND__@@@Z; CenterWindowOnDesktop(HWND__ *)
0x1800763d7  mov     rcx, rdi; hWnd
0x1800763da  call    cs:__imp_BringWindowToTop
0x1800763e1  nop     dword ptr [rax+rax+00h]
0x1800763e6  mov     edx, 579h; nIDDlgItem
0x1800763eb  mov     rcx, rdi; hDlg
0x1800763ee  call    cs:__imp_GetDlgItem
0x1800763f5  nop     dword ptr [rax+rax+00h]
0x1800763fa  mov     [rbx+40h], rax
0x1800763fe  test    rax, rax
0x180076401  jnz     short loc_18007641B
0x180076403  mov     edx, 640h; nIDDlgItem
0x180076408  mov     rcx, rdi; hDlg
0x18007640b  call    cs:__imp_GetDlgItem
0x180076412  nop     dword ptr [rax+rax+00h]
0x180076417  mov     [rbx+40h], rax
0x18007641b  mov     edx, 3F3h; nIDDlgItem
0x180076420  mov     rcx, rdi; hDlg
0x180076423  call    cs:__imp_GetDlgItem
0x18007642a  nop     dword ptr [rax+rax+00h]
0x18007642f  mov     edx, 57Bh; nIDDlgItem
0x180076434  mov     rcx, rdi; hDlg
0x180076437  mov     [rbx+48h], rax
0x18007643b  call    cs:__imp_GetDlgItem
0x180076442  nop     dword ptr [rax+rax+00h]
0x180076447  mov     edx, 57Dh; nIDDlgItem
0x18007644c  mov     rcx, rdi; hDlg
0x18007644f  mov     [rbx+50h], rax
0x180076453  call    cs:__imp_GetDlgItem
0x18007645a  nop     dword ptr [rax+rax+00h]
0x18007645f  mov     edx, 57Fh; nIDDlgItem
0x180076464  mov     rcx, rdi; hDlg
0x180076467  mov     [rbx+58h], rax
0x18007646b  call    cs:__imp_GetDlgItem
0x180076472  nop     dword ptr [rax+rax+00h]
0x180076477  mov     edx, 580h; nIDDlgItem
0x18007647c  mov     rcx, rdi; hDlg
0x18007647f  mov     [rbx+60h], rax
0x180076483  call    cs:__imp_GetDlgItem
0x18007648a  nop     dword ptr [rax+rax+00h]
0x18007648f  mov     edx, 581h; nIDDlgItem
0x180076494  mov     rcx, rdi; hDlg
0x180076497  mov     [rbx+68h], rax
0x18007649b  call    cs:__imp_GetDlgItem
0x1800764a2  nop     dword ptr [rax+rax+00h]
0x1800764a7  test    byte ptr [rbx], 4
0x1800764aa  mov     r8, [rbx+10h]; struct _EAPTLS_CERT_NODE *
0x1800764ae  mov     rcx, [rbx+40h]; hWnd
0x1800764b2  mov     [rbx+70h], rax
0x1800764b6  jz      short loc_1800764C3
0x1800764b8  mov     rdx, [rbx+18h]; struct _EAPTLS_GROUPED_CERT_NODES *
0x1800764bc  call    ?InitComboBoxFromGroup@@YAXPEAUHWND__@@PEAU_EAPTLS_GROUPED_CERT_NODES@@PEAU_EAPTLS_CERT_NODE@@@Z; InitComboBoxFromGroup(HWND__ *,_EAPTLS_GROUPED_CERT_NODES *,_EAPTLS_CERT_NODE *)
0x1800764c1  jmp     short loc_1800764CC
0x1800764c3  mov     rdx, [rbx+8]; lParam
0x1800764c7  call    ?InitComboBox@@YAXPEAUHWND__@@PEAU_EAPTLS_CERT_NODE@@1@Z; InitComboBox(HWND__ *,_EAPTLS_CERT_NODE *,_EAPTLS_CERT_NODE *)
0x1800764cc  cmp     [rbx+70h], r15
0x1800764d0  jz      short loc_1800764FB
0x1800764d2  test    byte ptr [rbx], 1
0x1800764d5  jnz     short loc_1800764FB
0x1800764d7  mov     rcx, [rbx+68h]; hWnd
0x1800764db  xor     edx, edx; nCmdShow
0x1800764dd  call    cs:__imp_ShowWindow
0x1800764e4  nop     dword ptr [rax+rax+00h]
0x1800764e9  mov     rcx, [rbx+70h]; hWnd
0x1800764ed  xor     edx, edx; nCmdShow
0x1800764ef  call    cs:__imp_ShowWindow
0x1800764f6  nop     dword ptr [rax+rax+00h]
0x1800764fb  mov     rcx, rbx; struct _EAPTLS_USER_DIALOG *
0x1800764fe  call    ?DisplayCertInfo@@YAXPEAU_EAPTLS_USER_DIALOG@@@Z; DisplayCertInfo(_EAPTLS_USER_DIALOG *)
0x180076503  mov     rax, [rbx+20h]
0x180076507  mov     rdx, [rax+28h]; lpString
0x18007650b  cmp     [rdx], r15w
0x18007650f  jz      short loc_180076521
0x180076511  mov     rcx, [rbx+70h]; hWnd
0x180076515  call    cs:__imp_SetWindowTextW
0x18007651c  nop     dword ptr [rax+rax+00h]
0x180076521  mov     rcx, [rbx+40h]; hWnd
0x180076525  call    cs:__imp_SetFocus
0x18007652c  nop     dword ptr [rax+rax+00h]
0x180076531  test    byte ptr [rbx], 2
0x180076534  jz      loc_1800766D0
0x18007653a  mov     edx, 4B6h
0x18007653f  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180076546  cmp     [rbx+28h], r15
0x18007654a  jnz     short loc_180076551
0x18007654c  mov     edx, 4B9h; uID
0x180076551  call    ?WszFromId@@YAPEAGPEAUHINSTANCE__@@K@Z; WszFromId(HINSTANCE__ *,ulong)
0x180076556  mov     rbp, rax
0x180076559  test    rax, rax
0x18007655c  jz      loc_1800766D0
0x180076562  mov     rdx, [rbx+28h]
0x180076566  test    rdx, rdx
0x180076569  jz      loc_1800766D0
0x18007656f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180076573  mov     rcx, rsi
0x180076576  inc     rcx
0x180076579  cmp     [rbp+rcx*2+0], r15w
0x18007657f  jnz     short loc_180076576
0x180076581  mov     rax, rsi
0x180076584  inc     rax
0x180076587  cmp     [rdx+rax*2], r15w
0x18007658c  jnz     short loc_180076584
0x18007658e  lea     rdx, [rax+rcx]
0x180076592  mov     ecx, 40h ; '@'; uFlags
0x180076597  add     rdx, rdx; uBytes
0x18007659a  call    cs:__imp_LocalAlloc
0x1800765a1  nop     dword ptr [rax+rax+00h]
0x1800765a6  mov     r14, rax
0x1800765a9  test    rax, rax
0x1800765ac  jz      loc_1800766D0
0x1800765b2  mov     r9, [rbx+28h]
0x1800765b6  mov     rax, rsi
0x1800765b9  mov     [rsp+58h+dwProcessId], r15d
0x1800765be  inc     rax
0x1800765c1  cmp     [rbp+rax*2+0], r15w
0x1800765c7  jnz     short loc_1800765BE
0x1800765c9  inc     rsi
0x1800765cc  cmp     [r9+rsi*2], r15w
0x1800765d1  jnz     short loc_1800765C9
0x1800765d3  lea     rdx, [rsi+rax]; BufferCount
0x1800765d7  mov     r8, rbp; Format
0x1800765da  mov     rcx, r14; Buffer
0x1800765dd  call    swprintf_s
0x1800765e2  mov     rdx, r14; lpWindowName
0x1800765e5  xor     ecx, ecx; lpClassName
0x1800765e7  call    cs:__imp_FindWindowW
0x1800765ee  nop     dword ptr [rax+rax+00h]
0x1800765f3  test    rax, rax
0x1800765f6  jz      loc_180076696
0x1800765fc  lea     rdx, [rsp+58h+dwProcessId]; lpdwProcessId
0x180076601  mov     rcx, rax; hWnd
0x180076604  call    cs:__imp_GetWindowThreadProcessId
0x18007660b  nop     dword ptr [rax+rax+00h]
0x180076610  call    cs:__imp_GetCurrentProcessId
0x180076617  nop     dword ptr [rax+rax+00h]
0x18007661c  cmp     eax, [rsp+58h+dwProcessId]
0x180076620  jnz     short loc_18007667C
0x180076622  xor     r9d, r9d; lParam
0x180076625  xor     r8d, r8d; wParam
0x180076628  mov     rcx, rdi; hWnd
0x18007662b  lea     edx, [r9+2]; Msg
0x18007662f  call    cs:__imp_PostMessageW
0x180076636  nop     dword ptr [rax+rax+00h]
0x18007663b  test    eax, eax
0x18007663d  jnz     loc_1800766D0
0x180076643  call    cs:__imp_GetLastError
0x18007664a  nop     dword ptr [rax+rax+00h]
0x18007664f  mov     rcx, cs:WPP_GLOBAL_Control
0x180076656  lea     rdx, WPP_GLOBAL_Control
0x18007665d  cmp     rcx, rdx
0x180076660  jz      short loc_1800766D0
0x180076662  mov     rcx, [rcx+10h]
0x180076666  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x18007666d  mov     edx, 3Fh ; '?'
0x180076672  mov     r9d, eax
0x180076675  call    WPP_SF_l
0x18007667a  jmp     short loc_1800766D0
0x18007667c  mov     rcx, cs:WPP_GLOBAL_Control
0x180076683  lea     rdx, WPP_GLOBAL_Control
0x18007668a  cmp     rcx, rdx
0x18007668d  jz      short loc_1800766BE
0x18007668f  mov     edx, 40h ; '@'
0x180076694  jmp     short loc_1800766AE
0x180076696  mov     rcx, cs:WPP_GLOBAL_Control
0x18007669d  lea     rdx, WPP_GLOBAL_Control
0x1800766a4  cmp     rcx, rdx
0x1800766a7  jz      short loc_1800766BE
0x1800766a9  mov     edx, 41h ; 'A'
0x1800766ae  mov     rcx, [rcx+10h]
0x1800766b2  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x1800766b9  call    WPP_SF_
0x1800766be  mov     rdx, r14; lpString
0x1800766c1  mov     rcx, rdi; hWnd
0x1800766c4  call    cs:__imp_SetWindowTextW
0x1800766cb  nop     dword ptr [rax+rax+00h]
0x1800766d0  mov     rcx, rbp; hMem
0x1800766d3  call    cs:__imp_LocalFree
0x1800766da  nop     dword ptr [rax+rax+00h]
0x1800766df  mov     rcx, r14; hMem
0x1800766e2  call    cs:__imp_LocalFree
0x1800766e9  nop     dword ptr [rax+rax+00h]
0x1800766ee  xor     eax, eax
0x1800766f0  add     rsp, 28h
0x1800766f4  pop     r15
0x1800766f6  pop     r14
0x1800766f8  pop     rdi
0x1800766f9  pop     rsi
0x1800766fa  pop     rbp
0x1800766fb  pop     rbx
0x1800766fc  retn
```
