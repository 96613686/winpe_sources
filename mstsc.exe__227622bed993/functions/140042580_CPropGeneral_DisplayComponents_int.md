# CPropGeneral::DisplayComponents(int)

- ea: `0x140042580`
- end: `0x1400427b8`
- name: `?DisplayComponents@CPropGeneral@@QEAAXH@Z`
- size: `568`
- prototype: `void __fastcall(CPropGeneral *__hidden this, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140043014`

## callees

- `0x140003b2c`
- `0x1400283b8`
- `0x140042580`
- `0x1400432c4`
- `0x14004344c`
- `0x14009f674`
- `0x1400b4964`
- `0x1400fa8b0`
- `0x140111220`

## import_xrefs

- `USER32!CreateDialogIndirectParamW` at `0x1400426fe`
- `USER32!CreateDialogIndirectParamW` at `0x1400426fe`
- `USER32!EnableWindow` at `0x140042605`
- `USER32!EnableWindow` at `0x140042633`
- `USER32!EnableWindow` at `0x140042605`
- `USER32!EnableWindow` at `0x140042633`
- `USER32!ShowWindow` at `0x140042713`
- `USER32!ShowWindow` at `0x140042758`
- `USER32!ShowWindow` at `0x140042713`
- `USER32!ShowWindow` at `0x140042758`
- `USER32!SetWindowPos` at `0x14004274d`
- `USER32!SetWindowPos` at `0x14004274d`
- `USER32!GetWindowRect` at `0x1400426a8`
- `USER32!GetWindowRect` at `0x1400426a8`
- `USER32!GetDlgItem` at `0x1400425fa`
- `USER32!GetDlgItem` at `0x14004261f`
- `USER32!GetDlgItem` at `0x140042689`
- `USER32!GetDlgItem` at `0x14004271f`
- `USER32!GetDlgItem` at `0x140042764`
- `USER32!GetDlgItem` at `0x1400425fa`
- `USER32!GetDlgItem` at `0x14004261f`
- `USER32!GetDlgItem` at `0x140042689`
- `USER32!GetDlgItem` at `0x14004271f`
- `USER32!GetDlgItem` at `0x140042764`
- `USER32!SetDlgItemTextW` at `0x14004278c`
- `USER32!SetDlgItemTextW` at `0x14004278c`

## pseudocode

```c
void __fastcall CPropGeneral::DisplayComponents(CPropGeneral *this, int a2)
{
  const struct _CTL_STATE_MAP near *const *v4; // rbp
  unsigned int v5; // r14d
  __int64 i; // rsi
  int v7; // ebx
  HWND DlgItem; // rax
  HWND v9; // rcx
  CTscCredsPane *v10; // rax
  HWND v11; // rax
  HWND v12; // rbx
  const DLGTEMPLATE *v13; // rax
  HWND DialogIndirectParamW; // rax
  HWND v15; // rax
  HWND v16; // rax
  struct tagRECT Rect; // [rsp+40h] [rbp-48h] BYREF

  Rect = 0;
  CPropGeneral::UpdateDisplayArea(this);
  v4 = &CPropGeneral::_ctlStateMapPublicMode;
  v5 = *(_DWORD *)(*(_QWORD *)this + 203460LL);
  if ( !*(_DWORD *)(*(_QWORD *)this + 206116LL) )
    v4 = &CPropGeneral::_ctlStateMap;
  for ( i = 0; i != 5; ++i )
  {
    v7 = *((_DWORD *)v4 + 7 * i + v5 + 1);
    DlgItem = GetDlgItem(*((HWND *)this + 5), *((_DWORD *)v4 + 7 * i));
    EnableWindow(DlgItem, v7);
  }
  v9 = GetDlgItem(*((HWND *)this + 6), 1);
  EnableWindow(v9, v5 != 5);
  if ( a2 )
  {
    if ( !*((_QWORD *)this + 72) )
    {
      v10 = (CTscCredsPane *)operator new(0x868u);
      if ( v10 )
        v10 = CTscCredsPane::CTscCredsPane(
                v10,
                *((HINSTANCE *)this + 1),
                (struct ISharedSettings *)(*(_QWORD *)this + 217208LL),
                0);
      *((_QWORD *)this + 72) = v10;
    }
    v11 = GetDlgItem(*((HWND *)this + 5), 13055);
    v12 = v11;
    if ( *((_QWORD *)this + 72) )
    {
      GetWindowRect(v11, &Rect);
      CClientUtilsWin32::ScreenToClientRect(*((HWND *)this + 5), &Rect);
      *(struct tagRECT *)(*((_QWORD *)this + 72) + 52LL) = Rect;
      v13 = TSLoadDlgTemplate(*((HINSTANCE *)this + 1), 0x32E9u);
      if ( v13 )
      {
        DialogIndirectParamW = CreateDialogIndirectParamW(
                                 *((HINSTANCE *)this + 1),
                                 v13,
                                 *((HWND *)this + 5),
                                 CTscCredsPane::StaticCredPaneDialogProc,
                                 *((_QWORD *)this + 72));
        *((_QWORD *)this + 73) = DialogIndirectParamW;
        ShowWindow(DialogIndirectParamW, 5);
        v15 = GetDlgItem(*((HWND *)this + 5), 13050);
        SetWindowPos(*((HWND *)this + 73), v15, 0, 0, 0, 0, 3u);
      }
    }
    ShowWindow(v12, 0);
  }
  v16 = GetDlgItem(*((HWND *)this + 5), 13050);
  CSH::InitServerAutoCmplCombo(*(struct CTscSettings **)this, v16);
  CPropGeneral::SubclassEditControl(this, 0);
  SetDlgItemTextW(*((HWND *)this + 5), 13050, (LPCWSTR)(*(_QWORD *)this + 108LL));
}

```

## disassembly

```asm
0x140042580  mov     [rsp+arg_8], rbx
0x140042585  mov     [rsp+arg_10], rbp
0x14004258a  push    rsi
0x14004258b  push    rdi
0x14004258c  push    r12
0x14004258e  push    r14
0x140042590  push    r15
0x140042592  sub     rsp, 60h
0x140042596  mov     rax, cs:__security_cookie
0x14004259d  xor     rax, rsp
0x1400425a0  mov     [rsp+88h+var_38], rax
0x1400425a5  xorps   xmm0, xmm0
0x1400425a8  mov     r12d, edx
0x1400425ab  movups  xmmword ptr [rsp+88h+Rect.left], xmm0
0x1400425b0  mov     rdi, rcx
0x1400425b3  call    ?UpdateDisplayArea@CPropGeneral@@AEAAXXZ; CPropGeneral::UpdateDisplayArea(void)
0x1400425b8  mov     rax, [rdi]
0x1400425bb  lea     rcx, ?_ctlStateMap@CPropGeneral@@0QBU_CTL_STATE_MAP@@B; _CTL_STATE_MAP const near * const CPropGeneral::_ctlStateMap
0x1400425c2  lea     rbp, ?_ctlStateMapPublicMode@CPropGeneral@@0QBU_CTL_STATE_MAP@@B; _CTL_STATE_MAP const near * const CPropGeneral::_ctlStateMapPublicMode
0x1400425c9  cmp     dword ptr [rax+32524h], 0
0x1400425d0  mov     r14d, [rax+31AC4h]
0x1400425d7  cmovz   rbp, rcx
0x1400425db  mov     r15d, r14d
0x1400425de  shl     r15, 2
0x1400425e2  xor     esi, esi
0x1400425e4  mov     rcx, [rdi+28h]; hDlg
0x1400425e8  imul    rdx, rsi, 1Ch
0x1400425ec  imul    rax, rsi, 1Ch
0x1400425f0  mov     edx, [rdx+rbp]; nIDDlgItem
0x1400425f3  add     rax, r15
0x1400425f6  mov     ebx, [rax+rbp+4]
0x1400425fa  call    cs:__imp_GetDlgItem
0x140042600  mov     rcx, rax; hWnd
0x140042603  mov     edx, ebx; bEnable
0x140042605  call    cs:__imp_EnableWindow
0x14004260b  mov     ebx, 1
0x140042610  add     rsi, rbx
0x140042613  cmp     rsi, 5
0x140042617  jnz     short loc_1400425E4
0x140042619  mov     rcx, [rdi+30h]; hDlg
0x14004261d  mov     edx, ebx; nIDDlgItem
0x14004261f  call    cs:__imp_GetDlgItem
0x140042625  mov     rcx, rax; hWnd
0x140042628  cmp     r14d, esi
0x14004262b  jnz     short loc_140042631
0x14004262d  xor     edx, edx
0x14004262f  jmp     short loc_140042633
0x140042631  mov     edx, ebx; bEnable
0x140042633  call    cs:__imp_EnableWindow
0x140042639  mov     esi, 32FAh
0x14004263e  test    r12d, r12d
0x140042641  jz      loc_14004275E
0x140042647  cmp     qword ptr [rdi+240h], 0
0x14004264f  jnz     short loc_140042680
0x140042651  mov     ecx, 868h; Size
0x140042656  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004265b  test    rax, rax
0x14004265e  jz      short loc_140042679
0x140042660  mov     r8, [rdi]
0x140042663  xor     r9d, r9d; int
0x140042666  mov     rdx, [rdi+8]; HINSTANCE
0x14004266a  add     r8, 35078h; struct ISharedSettings *
0x140042671  mov     rcx, rax; this
0x140042674  call    ??0CTscCredsPane@@QEAA@PEAUHINSTANCE__@@PEAVISharedSettings@@H@Z; CTscCredsPane::CTscCredsPane(HINSTANCE__ *,ISharedSettings *,int)
0x140042679  mov     [rdi+240h], rax
0x140042680  mov     rcx, [rdi+28h]; hDlg
0x140042684  mov     edx, 32FFh; nIDDlgItem
0x140042689  call    cs:__imp_GetDlgItem
0x14004268f  cmp     qword ptr [rdi+240h], 0
0x140042697  mov     rbx, rax
0x14004269a  jz      loc_140042753
0x1400426a0  lea     rdx, [rsp+88h+Rect]; lpRect
0x1400426a5  mov     rcx, rax; hWnd
0x1400426a8  call    cs:__imp_GetWindowRect
0x1400426ae  mov     rcx, [rdi+28h]; hWnd
0x1400426b2  lea     rdx, [rsp+88h+Rect]; lprc
0x1400426b7  call    ?ScreenToClientRect@CClientUtilsWin32@@SAXPEAUHWND__@@PEAUtagRECT@@@Z; CClientUtilsWin32::ScreenToClientRect(HWND__ *,tagRECT *)
0x1400426bc  mov     rcx, [rdi+240h]
0x1400426c3  mov     edx, 32E9h; unsigned int
0x1400426c8  movups  xmm0, xmmword ptr [rsp+88h+Rect.left]
0x1400426cd  movdqu  xmmword ptr [rcx+34h], xmm0
0x1400426d2  mov     rcx, [rdi+8]; HINSTANCE
0x1400426d6  call    ?TSLoadDlgTemplate@@YAPEAUDLGTEMPLATE@@PEAUHINSTANCE__@@I@Z; TSLoadDlgTemplate(HINSTANCE__ *,uint)
0x1400426db  test    rax, rax
0x1400426de  jz      short loc_140042753
0x1400426e0  mov     rcx, [rdi+240h]
0x1400426e7  lea     r9, ?StaticCredPaneDialogProc@CTscCredsPane@@SA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x1400426ee  mov     r8, [rdi+28h]; hWndParent
0x1400426f2  mov     rdx, rax; lpTemplate
0x1400426f5  mov     [rsp+88h+dwInitParam], rcx; dwInitParam
0x1400426fa  mov     rcx, [rdi+8]; hInstance
0x1400426fe  call    cs:__imp_CreateDialogIndirectParamW
0x140042704  mov     rcx, rax; hWnd
0x140042707  mov     [rdi+248h], rax
0x14004270e  mov     edx, 5; nCmdShow
0x140042713  call    cs:__imp_ShowWindow
0x140042719  mov     rcx, [rdi+28h]; hDlg
0x14004271d  mov     edx, esi; nIDDlgItem
0x14004271f  call    cs:__imp_GetDlgItem
0x140042725  mov     rcx, [rdi+248h]; hWnd
0x14004272c  xor     r9d, r9d; Y
0x14004272f  mov     [rsp+88h+uFlags], 3; uFlags
0x140042737  mov     rdx, rax; hWndInsertAfter
0x14004273a  mov     [rsp+88h+cy], 0; cy
0x140042742  xor     r8d, r8d; X
0x140042745  mov     dword ptr [rsp+88h+dwInitParam], 0; cx
0x14004274d  call    cs:__imp_SetWindowPos
0x140042753  xor     edx, edx; nCmdShow
0x140042755  mov     rcx, rbx; hWnd
0x140042758  call    cs:__imp_ShowWindow
0x14004275e  mov     rcx, [rdi+28h]; hDlg
0x140042762  mov     edx, esi; nIDDlgItem
0x140042764  call    cs:__imp_GetDlgItem
0x14004276a  mov     rcx, [rdi]; struct CTscSettings *
0x14004276d  mov     rdx, rax; hWnd
0x140042770  call    ?InitServerAutoCmplCombo@CSH@@SAXPEAVCTscSettings@@PEAUHWND__@@@Z; CSH::InitServerAutoCmplCombo(CTscSettings *,HWND__ *)
0x140042775  xor     edx, edx; int
0x140042777  mov     rcx, rdi; this
0x14004277a  call    ?SubclassEditControl@CPropGeneral@@AEAAXH@Z; CPropGeneral::SubclassEditControl(int)
0x14004277f  mov     r8, [rdi]
0x140042782  mov     edx, esi; nIDDlgItem
0x140042784  mov     rcx, [rdi+28h]; hDlg
0x140042788  add     r8, 6Ch ; 'l'; lpString
0x14004278c  call    cs:__imp_SetDlgItemTextW
0x140042792  mov     rcx, [rsp+88h+var_38]
0x140042797  xor     rcx, rsp; StackCookie
0x14004279a  call    __security_check_cookie
0x14004279f  lea     r11, [rsp+88h+var_28]
0x1400427a4  mov     rbx, [r11+38h]
0x1400427a8  mov     rbp, [r11+40h]
0x1400427ac  mov     rsp, r11
0x1400427af  pop     r15
0x1400427b1  pop     r14
0x1400427b3  pop     r12
0x1400427b5  pop     rdi
0x1400427b6  pop     rsi
0x1400427b7  retn
```
