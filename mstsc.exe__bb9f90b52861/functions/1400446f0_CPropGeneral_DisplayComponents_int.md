# CPropGeneral::DisplayComponents(int)

- ea: `0x1400446f0`
- end: `0x140044928`
- name: `?DisplayComponents@CPropGeneral@@QEAAXH@Z`
- size: `568`
- prototype: `void __fastcall(CPropGeneral *__hidden this, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140045184`

## callees

- `0x140003b2c`
- `0x1400283b8`
- `0x1400446f0`
- `0x140045434`
- `0x1400455bc`
- `0x1400a17e4`
- `0x1400b6ad4`
- `0x1400fca20`
- `0x140113390`

## import_xrefs

- `USER32!CreateDialogIndirectParamW` at `0x14004486e`
- `USER32!CreateDialogIndirectParamW` at `0x14004486e`
- `USER32!EnableWindow` at `0x140044775`
- `USER32!EnableWindow` at `0x1400447a3`
- `USER32!EnableWindow` at `0x140044775`
- `USER32!EnableWindow` at `0x1400447a3`
- `USER32!ShowWindow` at `0x140044883`
- `USER32!ShowWindow` at `0x1400448c8`
- `USER32!ShowWindow` at `0x140044883`
- `USER32!ShowWindow` at `0x1400448c8`
- `USER32!SetWindowPos` at `0x1400448bd`
- `USER32!SetWindowPos` at `0x1400448bd`
- `USER32!GetWindowRect` at `0x140044818`
- `USER32!GetWindowRect` at `0x140044818`
- `USER32!GetDlgItem` at `0x14004476a`
- `USER32!GetDlgItem` at `0x14004478f`
- `USER32!GetDlgItem` at `0x1400447f9`
- `USER32!GetDlgItem` at `0x14004488f`
- `USER32!GetDlgItem` at `0x1400448d4`
- `USER32!GetDlgItem` at `0x14004476a`
- `USER32!GetDlgItem` at `0x14004478f`
- `USER32!GetDlgItem` at `0x1400447f9`
- `USER32!GetDlgItem` at `0x14004488f`
- `USER32!GetDlgItem` at `0x1400448d4`
- `USER32!SetDlgItemTextW` at `0x1400448fc`
- `USER32!SetDlgItemTextW` at `0x1400448fc`

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
0x1400446f0  mov     [rsp+arg_8], rbx
0x1400446f5  mov     [rsp+arg_10], rbp
0x1400446fa  push    rsi
0x1400446fb  push    rdi
0x1400446fc  push    r12
0x1400446fe  push    r14
0x140044700  push    r15
0x140044702  sub     rsp, 60h
0x140044706  mov     rax, cs:__security_cookie
0x14004470d  xor     rax, rsp
0x140044710  mov     [rsp+88h+var_38], rax
0x140044715  xorps   xmm0, xmm0
0x140044718  mov     r12d, edx
0x14004471b  movups  xmmword ptr [rsp+88h+Rect.left], xmm0
0x140044720  mov     rdi, rcx
0x140044723  call    ?UpdateDisplayArea@CPropGeneral@@AEAAXXZ; CPropGeneral::UpdateDisplayArea(void)
0x140044728  mov     rax, [rdi]
0x14004472b  lea     rcx, ?_ctlStateMap@CPropGeneral@@0QBU_CTL_STATE_MAP@@B; _CTL_STATE_MAP const near * const CPropGeneral::_ctlStateMap
0x140044732  lea     rbp, ?_ctlStateMapPublicMode@CPropGeneral@@0QBU_CTL_STATE_MAP@@B; _CTL_STATE_MAP const near * const CPropGeneral::_ctlStateMapPublicMode
0x140044739  cmp     dword ptr [rax+32524h], 0
0x140044740  mov     r14d, [rax+31AC4h]
0x140044747  cmovz   rbp, rcx
0x14004474b  mov     r15d, r14d
0x14004474e  shl     r15, 2
0x140044752  xor     esi, esi
0x140044754  mov     rcx, [rdi+28h]; hDlg
0x140044758  imul    rdx, rsi, 1Ch
0x14004475c  imul    rax, rsi, 1Ch
0x140044760  mov     edx, [rdx+rbp]; nIDDlgItem
0x140044763  add     rax, r15
0x140044766  mov     ebx, [rax+rbp+4]
0x14004476a  call    cs:__imp_GetDlgItem
0x140044770  mov     rcx, rax; hWnd
0x140044773  mov     edx, ebx; bEnable
0x140044775  call    cs:__imp_EnableWindow
0x14004477b  mov     ebx, 1
0x140044780  add     rsi, rbx
0x140044783  cmp     rsi, 5
0x140044787  jnz     short loc_140044754
0x140044789  mov     rcx, [rdi+30h]; hDlg
0x14004478d  mov     edx, ebx; nIDDlgItem
0x14004478f  call    cs:__imp_GetDlgItem
0x140044795  mov     rcx, rax; hWnd
0x140044798  cmp     r14d, esi
0x14004479b  jnz     short loc_1400447A1
0x14004479d  xor     edx, edx
0x14004479f  jmp     short loc_1400447A3
0x1400447a1  mov     edx, ebx; bEnable
0x1400447a3  call    cs:__imp_EnableWindow
0x1400447a9  mov     esi, 32FAh
0x1400447ae  test    r12d, r12d
0x1400447b1  jz      loc_1400448CE
0x1400447b7  cmp     qword ptr [rdi+240h], 0
0x1400447bf  jnz     short loc_1400447F0
0x1400447c1  mov     ecx, 868h; Size
0x1400447c6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400447cb  test    rax, rax
0x1400447ce  jz      short loc_1400447E9
0x1400447d0  mov     r8, [rdi]
0x1400447d3  xor     r9d, r9d; int
0x1400447d6  mov     rdx, [rdi+8]; HINSTANCE
0x1400447da  add     r8, 35078h; struct ISharedSettings *
0x1400447e1  mov     rcx, rax; this
0x1400447e4  call    ??0CTscCredsPane@@QEAA@PEAUHINSTANCE__@@PEAVISharedSettings@@H@Z; CTscCredsPane::CTscCredsPane(HINSTANCE__ *,ISharedSettings *,int)
0x1400447e9  mov     [rdi+240h], rax
0x1400447f0  mov     rcx, [rdi+28h]; hDlg
0x1400447f4  mov     edx, 32FFh; nIDDlgItem
0x1400447f9  call    cs:__imp_GetDlgItem
0x1400447ff  cmp     qword ptr [rdi+240h], 0
0x140044807  mov     rbx, rax
0x14004480a  jz      loc_1400448C3
0x140044810  lea     rdx, [rsp+88h+Rect]; lpRect
0x140044815  mov     rcx, rax; hWnd
0x140044818  call    cs:__imp_GetWindowRect
0x14004481e  mov     rcx, [rdi+28h]; hWnd
0x140044822  lea     rdx, [rsp+88h+Rect]; lprc
0x140044827  call    ?ScreenToClientRect@CClientUtilsWin32@@SAXPEAUHWND__@@PEAUtagRECT@@@Z; CClientUtilsWin32::ScreenToClientRect(HWND__ *,tagRECT *)
0x14004482c  mov     rcx, [rdi+240h]
0x140044833  mov     edx, 32E9h; unsigned int
0x140044838  movups  xmm0, xmmword ptr [rsp+88h+Rect.left]
0x14004483d  movdqu  xmmword ptr [rcx+34h], xmm0
0x140044842  mov     rcx, [rdi+8]; HINSTANCE
0x140044846  call    ?TSLoadDlgTemplate@@YAPEAUDLGTEMPLATE@@PEAUHINSTANCE__@@I@Z; TSLoadDlgTemplate(HINSTANCE__ *,uint)
0x14004484b  test    rax, rax
0x14004484e  jz      short loc_1400448C3
0x140044850  mov     rcx, [rdi+240h]
0x140044857  lea     r9, ?StaticCredPaneDialogProc@CTscCredsPane@@SA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x14004485e  mov     r8, [rdi+28h]; hWndParent
0x140044862  mov     rdx, rax; lpTemplate
0x140044865  mov     [rsp+88h+dwInitParam], rcx; dwInitParam
0x14004486a  mov     rcx, [rdi+8]; hInstance
0x14004486e  call    cs:__imp_CreateDialogIndirectParamW
0x140044874  mov     rcx, rax; hWnd
0x140044877  mov     [rdi+248h], rax
0x14004487e  mov     edx, 5; nCmdShow
0x140044883  call    cs:__imp_ShowWindow
0x140044889  mov     rcx, [rdi+28h]; hDlg
0x14004488d  mov     edx, esi; nIDDlgItem
0x14004488f  call    cs:__imp_GetDlgItem
0x140044895  mov     rcx, [rdi+248h]; hWnd
0x14004489c  xor     r9d, r9d; Y
0x14004489f  mov     [rsp+88h+uFlags], 3; uFlags
0x1400448a7  mov     rdx, rax; hWndInsertAfter
0x1400448aa  mov     [rsp+88h+cy], 0; cy
0x1400448b2  xor     r8d, r8d; X
0x1400448b5  mov     dword ptr [rsp+88h+dwInitParam], 0; cx
0x1400448bd  call    cs:__imp_SetWindowPos
0x1400448c3  xor     edx, edx; nCmdShow
0x1400448c5  mov     rcx, rbx; hWnd
0x1400448c8  call    cs:__imp_ShowWindow
0x1400448ce  mov     rcx, [rdi+28h]; hDlg
0x1400448d2  mov     edx, esi; nIDDlgItem
0x1400448d4  call    cs:__imp_GetDlgItem
0x1400448da  mov     rcx, [rdi]; struct CTscSettings *
0x1400448dd  mov     rdx, rax; hWnd
0x1400448e0  call    ?InitServerAutoCmplCombo@CSH@@SAXPEAVCTscSettings@@PEAUHWND__@@@Z; CSH::InitServerAutoCmplCombo(CTscSettings *,HWND__ *)
0x1400448e5  xor     edx, edx; int
0x1400448e7  mov     rcx, rdi; this
0x1400448ea  call    ?SubclassEditControl@CPropGeneral@@AEAAXH@Z; CPropGeneral::SubclassEditControl(int)
0x1400448ef  mov     r8, [rdi]
0x1400448f2  mov     edx, esi; nIDDlgItem
0x1400448f4  mov     rcx, [rdi+28h]; hDlg
0x1400448f8  add     r8, 6Ch ; 'l'; lpString
0x1400448fc  call    cs:__imp_SetDlgItemTextW
0x140044902  mov     rcx, [rsp+88h+var_38]
0x140044907  xor     rcx, rsp; StackCookie
0x14004490a  call    __security_check_cookie
0x14004490f  lea     r11, [rsp+88h+var_28]
0x140044914  mov     rbx, [r11+38h]
0x140044918  mov     rbp, [r11+40h]
0x14004491c  mov     rsp, r11
0x14004491f  pop     r15
0x140044921  pop     r14
0x140044923  pop     r12
0x140044925  pop     rdi
0x140044926  pop     rsi
0x140044927  retn
```
