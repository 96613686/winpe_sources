# DetailsView::OnCommand(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18000de10`
- end: `0x18000e189`
- name: `?OnCommand@DetailsView@@AEAA_JPEAUHWND__@@I_K_J@Z`
- size: `889`
- prototype: `__int64 __fastcall(DetailsView *__hidden this, HWND hWnd, unsigned int, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180010960`

## callees

- `0x180001510`
- `0x1800022b4`
- `0x18000adf4`
- `0x18000c45c`
- `0x18000c8c4`
- `0x18000d138`
- `0x18000d4d0`
- `0x18000d5f8`
- `0x18000d800`
- `0x18000da5c`
- `0x18000dc40`
- `0x18000dd24`
- `0x18000de10`
- `0x18000f31c`
- `0x1800101b4`
- `0x180010238`
- `0x180016d98`
- `0x18001c210`
- `0x18001f010`

## import_xrefs

- `SHELL32!ShellAboutW` at `0x18000df20`
- `SHELL32!ShellAboutW` at `0x18000df20`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000df09`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000df09`
- `ole32!OleSetClipboard` at `0x18000e0dc`
- `ole32!OleSetClipboard` at `0x18000e0dc`
- `USER32!SendMessageW` at `0x18000dfba`
- `USER32!SendMessageW` at `0x18000dfba`
- `USER32!SetCursor` at `0x18000df6a`
- `USER32!SetCursor` at `0x18000e027`
- `USER32!SetCursor` at `0x18000e06a`
- `USER32!SetCursor` at `0x18000df6a`
- `USER32!SetCursor` at `0x18000e027`
- `USER32!SetCursor` at `0x18000e06a`
- `USER32!LoadCursorW` at `0x18000df61`
- `USER32!LoadCursorW` at `0x18000e01e`
- `USER32!LoadCursorW` at `0x18000df61`
- `USER32!LoadCursorW` at `0x18000e01e`
- `USER32!ShowCursor` at `0x18000df78`
- `USER32!ShowCursor` at `0x18000e03a`
- `USER32!ShowCursor` at `0x18000e058`
- `USER32!ShowCursor` at `0x18000df78`
- `USER32!ShowCursor` at `0x18000e03a`
- `USER32!ShowCursor` at `0x18000e058`
- `USER32!SetFocus` at `0x18000df82`
- `USER32!SetFocus` at `0x18000e131`
- `USER32!SetFocus` at `0x18000df82`
- `USER32!SetFocus` at `0x18000e131`
- `USER32!DestroyWindow` at `0x18000df2f`
- `USER32!DestroyWindow` at `0x18000df2f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DetailsView::OnCommand(DetailsView *this, HWND hWnd, __int64 a3, unsigned __int16 a4)
{
  int v6; // edx
  HCURSOR CursorW; // rax
  HCURSOR v8; // rbx
  HCURSOR v9; // rax
  LPDATAOBJECT *v10; // rbx
  LPARAM lParam; // [rsp+40h] [rbp-288h] BYREF
  int v13; // [rsp+4Ch] [rbp-27Ch]
  int v14; // [rsp+50h] [rbp-278h]
  WCHAR Buffer[264]; // [rsp+A0h] [rbp-228h] BYREF

  if ( a4 <= 0x9C54u )
  {
    if ( a4 != 40020 )
    {
      if ( a4 > 0x9C4Du )
      {
        switch ( a4 )
        {
          case 0x9C4Eu:
            v6 = 7;
            goto LABEL_43;
          case 0x9C4Fu:
            DetailsView::Refresh(this, 1);
            break;
          case 0x9C50u:
            DetailsView::OnCmdProperties(this);
            break;
          case 0x9C51u:
            DestroyWindow(*((HWND *)this + 12));
            break;
          case 0x9C53u:
            LoadStringW(g_hInstDll, 0x9E34u, Buffer, 260);
            ShellAboutW(hWnd, Buffer, 0, 0);
            break;
        }
      }
      else
      {
        switch ( a4 )
        {
          case 0x9C4Du:
            v6 = 6;
            goto LABEL_43;
          case 0x9C41u:
            DetailsView::OnCmdNew(this);
            break;
          case 0x9C43u:
            DetailsView::OnCmdViewToolBar(this);
            break;
          case 0x9C44u:
            DetailsView::OnCmdViewStatusBar(this);
            break;
          case 0x9C4Au:
            v6 = 2;
            goto LABEL_43;
          case 0x9C4Bu:
            v6 = 4;
            goto LABEL_43;
          case 0x9C4Cu:
            v6 = 5;
LABEL_43:
            DetailsView::SortObjects(this, v6, *((_DWORD *)this + 131));
            return 0;
        }
      }
      return 0;
    }
    CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
    v8 = SetCursor(CursorW);
    ShowCursor(1);
    SetFocus(*((HWND *)this + 13));
    memset_0(&lParam, 0, 0x58u);
    v14 = 2;
    v13 = 2;
    SendMessageW(*((HWND *)this + 13), 0x102Bu, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)&lParam);
LABEL_39:
    ShowCursor(0);
    if ( v8 )
      SetCursor(v8);
    return 0;
  }
  if ( a4 > 0x9C69u )
  {
    switch ( a4 )
    {
      case 0x9C6Au:
        if ( *((_QWORD *)this + 23) )
          SHFusionDialogBoxParam(
            g_hInstDll,
            (LPCWSTR)0x92,
            *((HWND *)this + 13),
            (DLGPROC)DetailsView::Finder::DlgProc,
            *((_QWORD *)this + 23));
        break;
      case 0x9C6Bu:
        SetFocus(*((HWND *)this + 16));
        return 0;
      case 0x9C6Cu:
        DetailsView::OnCmdImport(this);
        return 0;
      case 0x9C6Du:
        DetailsView::OnCmdExport((HWND *)this);
        return 0;
      case 0x9EB8u:
        v6 = 3;
        goto LABEL_43;
    }
    return 0;
  }
  switch ( a4 )
  {
    case 0x9C69u:
      v10 = (LPDATAOBJECT *)((char *)this + 496);
      if ( (**(int (__fastcall ***)(DetailsView *, GUID *, char *))this)(
             this,
             &GUID_0000010e_0000_0000_c000_000000000046,
             (char *)this + 496) >= 0 )
      {
        OleSetClipboard(*v10);
        ((void (__fastcall *)(LPDATAOBJECT))(*v10)->lpVtbl->Release)(*v10);
      }
      return 0;
    case 0x9C55u:
      DetailsView::InvertSelectedItems(this);
      return 0;
    case 0x9C59u:
      DetailsView::OnCmdViewShowFolder(this);
      return 0;
    case 0x9C5Au:
      DetailsView::OnCmdDelete(this);
      DetailsView::FocusOnSomething(this);
      return 0;
    case 0x9C63u:
      v6 = 1;
      goto LABEL_43;
    case 0x9C64u:
      v6 = 0;
      goto LABEL_43;
  }
  if ( a4 == 40040 && *((_QWORD *)this + 24) )
  {
    v9 = LoadCursorW(0, (LPCWSTR)0x7F02);
    v8 = SetCursor(v9);
    ShowCursor(1);
    UndoList::Undo(*((UndoList **)this + 24));
    DetailsView::ShowItemCountInStatusBar(this);
    goto LABEL_39;
  }
  return 0;
}

```

## disassembly

```asm
0x18000de10  mov     [rsp+arg_10], rbx
0x18000de15  push    rdi
0x18000de16  sub     rsp, 2C0h
0x18000de1d  mov     rax, cs:__security_cookie
0x18000de24  xor     rax, rsp
0x18000de27  mov     [rsp+2C8h+var_18], rax
0x18000de2f  mov     rbx, rdx
0x18000de32  mov     rdi, rcx
0x18000de35  movzx   edx, r9w
0x18000de39  mov     eax, 9C54h
0x18000de3e  cmp     edx, eax
0x18000de40  ja      loc_18000DFC5
0x18000de46  jz      loc_18000DF5A
0x18000de4c  mov     eax, 9C4Dh
0x18000de51  cmp     edx, eax
0x18000de53  ja      short loc_18000DEC2
0x18000de55  jz      short loc_18000DEB8
0x18000de57  sub     edx, 9C41h
0x18000de5d  jz      short loc_18000DEAE
0x18000de5f  sub     edx, 2
0x18000de62  jz      short loc_18000DEA4
0x18000de64  sub     edx, 1
0x18000de67  jz      short loc_18000DE9A
0x18000de69  sub     edx, 6
0x18000de6c  jz      short loc_18000DE90
0x18000de6e  sub     edx, 1
0x18000de71  jz      short loc_18000DE86
0x18000de73  cmp     edx, 1
0x18000de76  jnz     loc_18000E166
0x18000de7c  mov     edx, 5
0x18000de81  jmp     loc_18000E07E
0x18000de86  mov     edx, 4
0x18000de8b  jmp     loc_18000E07E
0x18000de90  mov     edx, 2
0x18000de95  jmp     loc_18000E07E
0x18000de9a  call    ?OnCmdViewStatusBar@DetailsView@@AEAA_JXZ; DetailsView::OnCmdViewStatusBar(void)
0x18000de9f  jmp     loc_18000E166
0x18000dea4  call    ?OnCmdViewToolBar@DetailsView@@AEAA_JXZ; DetailsView::OnCmdViewToolBar(void)
0x18000dea9  jmp     loc_18000E166
0x18000deae  call    ?OnCmdNew@DetailsView@@AEAA_JXZ; DetailsView::OnCmdNew(void)
0x18000deb3  jmp     loc_18000E166
0x18000deb8  mov     edx, 6
0x18000debd  jmp     loc_18000E07E
0x18000dec2  sub     edx, 9C4Eh
0x18000dec8  jz      loc_18000DF50
0x18000dece  sub     edx, 1
0x18000ded1  jz      short loc_18000DF44
0x18000ded3  sub     edx, 1
0x18000ded6  jz      short loc_18000DF3A
0x18000ded8  sub     edx, 1
0x18000dedb  jz      short loc_18000DF2B
0x18000dedd  sub     edx, 1
0x18000dee0  jz      loc_18000E166
0x18000dee6  cmp     edx, 1
0x18000dee9  jnz     loc_18000E166
0x18000deef  mov     r9d, 104h; cchBufferMax
0x18000def5  lea     r8, [rsp+2C8h+Buffer]; lpBuffer
0x18000defd  mov     edx, 9E34h; uID
0x18000df02  mov     rcx, cs:?g_hInstDll@@3PEAUHINSTANCE__@@EA; hInstance
0x18000df09  call    cs:__imp_LoadStringW
0x18000df0f  xor     r9d, r9d; hIcon
0x18000df12  xor     r8d, r8d; szOtherStuff
0x18000df15  lea     rdx, [rsp+2C8h+Buffer]; szApp
0x18000df1d  mov     rcx, rbx; hWnd
0x18000df20  call    cs:__imp_ShellAboutW
0x18000df26  jmp     loc_18000E166
0x18000df2b  mov     rcx, [rcx+60h]; hWnd
0x18000df2f  call    cs:__imp_DestroyWindow
0x18000df35  jmp     loc_18000E166
0x18000df3a  call    ?OnCmdProperties@DetailsView@@AEAA_JXZ; DetailsView::OnCmdProperties(void)
0x18000df3f  jmp     loc_18000E166
0x18000df44  mov     dl, 1; bool
0x18000df46  call    ?Refresh@DetailsView@@AEAA_J_N@Z; DetailsView::Refresh(bool)
0x18000df4b  jmp     loc_18000E166
0x18000df50  mov     edx, 7
0x18000df55  jmp     loc_18000E07E
0x18000df5a  mov     edx, 7F02h; lpCursorName
0x18000df5f  xor     ecx, ecx; hInstance
0x18000df61  call    cs:__imp_LoadCursorW
0x18000df67  mov     rcx, rax; hCursor
0x18000df6a  call    cs:__imp_SetCursor
0x18000df70  mov     rbx, rax
0x18000df73  mov     ecx, 1; bShow
0x18000df78  call    cs:__imp_ShowCursor
0x18000df7e  mov     rcx, [rdi+68h]; hWnd
0x18000df82  call    cs:__imp_SetFocus
0x18000df88  xor     edx, edx; Val
0x18000df8a  lea     r8d, [rdx+58h]; Size
0x18000df8e  lea     rcx, [rsp+2C8h+lParam]; void *
0x18000df93  call    memset_0
0x18000df98  mov     [rsp+2C8h+var_278], 2
0x18000dfa0  mov     [rsp+2C8h+var_27C], 2
0x18000dfa8  lea     r9, [rsp+2C8h+lParam]; lParam
0x18000dfad  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x18000dfb1  mov     edx, 102Bh; Msg
0x18000dfb6  mov     rcx, [rdi+68h]; hWnd
0x18000dfba  call    cs:__imp_SendMessageW
0x18000dfc0  jmp     loc_18000E056
0x18000dfc5  mov     eax, 9C69h
0x18000dfca  cmp     edx, eax
0x18000dfcc  ja      loc_18000E0F3
0x18000dfd2  jz      loc_18000E0B5
0x18000dfd8  sub     edx, 9C55h
0x18000dfde  jz      loc_18000E0AB
0x18000dfe4  sub     edx, 4
0x18000dfe7  jz      loc_18000E0A1
0x18000dfed  sub     edx, 1
0x18000dff0  jz      loc_18000E08F
0x18000dff6  sub     edx, 9
0x18000dff9  jz      short loc_18000E079
0x18000dffb  sub     edx, 1
0x18000dffe  jz      short loc_18000E075
0x18000e000  cmp     edx, 4
0x18000e003  jnz     loc_18000E166
0x18000e009  cmp     qword ptr [rcx+0C0h], 0
0x18000e011  jz      loc_18000E166
0x18000e017  mov     edx, 7F02h; lpCursorName
0x18000e01c  xor     ecx, ecx; hInstance
0x18000e01e  call    cs:__imp_LoadCursorW
0x18000e024  mov     rcx, rax; hCursor
0x18000e027  call    cs:__imp_SetCursor
0x18000e02d  mov     rbx, rax
0x18000e030  mov     [rsp+2C8h+var_298], rax
0x18000e035  mov     ecx, 1; bShow
0x18000e03a  call    cs:__imp_ShowCursor
0x18000e040  nop
0x18000e041  mov     rcx, [rdi+0C0h]; this
0x18000e048  call    ?Undo@UndoList@@QEAAXXZ; UndoList::Undo(void)
0x18000e04d  mov     rcx, rdi; this
0x18000e050  call    ?ShowItemCountInStatusBar@DetailsView@@AEAA_JXZ; DetailsView::ShowItemCountInStatusBar(void)
0x18000e055  nop
0x18000e056  xor     ecx, ecx; bShow
0x18000e058  call    cs:__imp_ShowCursor
0x18000e05e  test    rbx, rbx
0x18000e061  jz      loc_18000E166
0x18000e067  mov     rcx, rbx; hCursor
0x18000e06a  call    cs:__imp_SetCursor
0x18000e070  jmp     loc_18000E166
0x18000e075  xor     edx, edx
0x18000e077  jmp     short loc_18000E07E
0x18000e079  mov     edx, 1; unsigned int
0x18000e07e  mov     r8d, [rcx+20Ch]; unsigned int
0x18000e085  call    ?SortObjects@DetailsView@@AEAA_JKK@Z; DetailsView::SortObjects(ulong,ulong)
0x18000e08a  jmp     loc_18000E166
0x18000e08f  call    ?OnCmdDelete@DetailsView@@AEAA_JXZ; DetailsView::OnCmdDelete(void)
0x18000e094  mov     rcx, rdi; this
0x18000e097  call    ?FocusOnSomething@DetailsView@@AEAAXXZ; DetailsView::FocusOnSomething(void)
0x18000e09c  jmp     loc_18000E166
0x18000e0a1  call    ?OnCmdViewShowFolder@DetailsView@@AEAA_JXZ; DetailsView::OnCmdViewShowFolder(void)
0x18000e0a6  jmp     loc_18000E166
0x18000e0ab  call    ?InvertSelectedItems@DetailsView@@AEAA_JXZ; DetailsView::InvertSelectedItems(void)
0x18000e0b0  jmp     loc_18000E166
0x18000e0b5  lea     rbx, [rcx+1F0h]
0x18000e0bc  mov     rax, [rcx]
0x18000e0bf  mov     r8, rbx
0x18000e0c2  lea     rdx, _GUID_0000010e_0000_0000_c000_000000000046
0x18000e0c9  mov     rax, [rax]
0x18000e0cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0d1  test    eax, eax
0x18000e0d3  js      loc_18000E166
0x18000e0d9  mov     rcx, [rbx]; pDataObj
0x18000e0dc  call    cs:__imp_OleSetClipboard
0x18000e0e2  mov     rcx, [rbx]
0x18000e0e5  mov     rax, [rcx]
0x18000e0e8  mov     rax, [rax+10h]
0x18000e0ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0f1  jmp     short loc_18000E166
0x18000e0f3  sub     edx, 9C6Ah
0x18000e0f9  jz      short loc_18000E139
0x18000e0fb  sub     edx, 1
0x18000e0fe  jz      short loc_18000E12A
0x18000e100  sub     edx, 1
0x18000e103  jz      short loc_18000E123
0x18000e105  sub     edx, 1
0x18000e108  jz      short loc_18000E11C
0x18000e10a  cmp     edx, 24Bh
0x18000e110  jnz     short loc_18000E166
0x18000e112  mov     edx, 3
0x18000e117  jmp     loc_18000E07E
0x18000e11c  call    ?OnCmdExport@DetailsView@@AEAA_JXZ; DetailsView::OnCmdExport(void)
0x18000e121  jmp     short loc_18000E166
0x18000e123  call    ?OnCmdImport@DetailsView@@AEAA_JXZ; DetailsView::OnCmdImport(void)
0x18000e128  jmp     short loc_18000E166
0x18000e12a  mov     rcx, [rcx+80h]; hWnd
0x18000e131  call    cs:__imp_SetFocus
0x18000e137  jmp     short loc_18000E166
0x18000e139  mov     rax, [rcx+0B8h]
0x18000e140  test    rax, rax
0x18000e143  jz      short loc_18000E166
0x18000e145  mov     [rsp+2C8h+var_2A8], rax; LPARAM
0x18000e14a  lea     r9, ?DlgProc@Finder@DetailsView@@SA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x18000e151  mov     r8, [rcx+68h]; hWndParent
0x18000e155  mov     edx, 92h; lpTemplateName
0x18000e15a  mov     rcx, cs:?g_hInstDll@@3PEAUHINSTANCE__@@EA; hInstance
0x18000e161  call    SHFusionDialogBoxParam
0x18000e166  xor     eax, eax
0x18000e168  mov     rcx, [rsp+2C8h+var_18]
0x18000e170  xor     rcx, rsp; StackCookie
0x18000e173  call    __security_check_cookie
0x18000e178  mov     rbx, [rsp+2C8h+arg_10]
0x18000e180  add     rsp, 2C0h
0x18000e187  pop     rdi
0x18000e188  retn
```
