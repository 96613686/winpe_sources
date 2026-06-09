# CFileOwnerDialog::OnCommand(HWND__ *,unsigned __int64,__int64)

- ea: `0x180013d44`
- end: `0x18001410d`
- name: `?OnCommand@CFileOwnerDialog@@AEAA_JPEAUHWND__@@_K_J@Z`
- size: `969`
- prototype: `__int64 __fastcall(CFileOwnerDialog *__hidden this, HWND hDlg, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x1800131a0`

## callees

- `0x1800022b4`
- `0x180012e94`
- `0x1800130ac`
- `0x1800132b0`
- `0x180013a48`
- `0x180013b8c`
- `0x180013d44`
- `0x180014ca8`
- `0x180014e68`
- `0x18001510c`
- `0x180019d24`
- `0x180019dd0`
- `0x180019ee0`
- `0x180019f38`
- `0x18001a5f0`
- `0x18001a708`
- `0x18001a73c`
- `0x18001ab24`

## import_xrefs

- `SHELL32!SHBrowseForFolderW` at `0x180013ee6`
- `SHELL32!SHBrowseForFolderW` at `0x180013ee6`
- `SHLWAPI!PathStripToRootW` at `0x180013f9b`
- `SHLWAPI!PathStripToRootW` at `0x180013f9b`
- `USER32!IsWindowEnabled` at `0x180013e60`
- `USER32!IsWindowEnabled` at `0x180013e60`
- `USER32!SetWindowTextW` at `0x180013f08`
- `USER32!SetWindowTextW` at `0x180014000`
- `USER32!SetWindowTextW` at `0x180013f08`
- `USER32!SetWindowTextW` at `0x180014000`
- `USER32!GetWindowTextLengthW` at `0x180013f45`
- `USER32!GetWindowTextLengthW` at `0x180013f45`
- `USER32!GetWindowTextW` at `0x180013f63`
- `USER32!GetWindowTextW` at `0x180013f63`
- `USER32!EnableWindow` at `0x180013e79`
- `USER32!EnableWindow` at `0x180013e79`
- `USER32!SendMessageW` at `0x180013e10`
- `USER32!SendMessageW` at `0x180014082`
- `USER32!SendMessageW` at `0x1800140a7`
- `USER32!SendMessageW` at `0x1800140e2`
- `USER32!SendMessageW` at `0x180013e10`
- `USER32!SendMessageW` at `0x180014082`
- `USER32!SendMessageW` at `0x1800140a7`
- `USER32!SendMessageW` at `0x1800140e2`
- `USER32!CheckDlgButton` at `0x180013dfb`
- `USER32!CheckDlgButton` at `0x180013dfb`
- `USER32!GetDlgItem` at `0x180013e47`
- `USER32!GetDlgItem` at `0x180013e47`
- `USER32!EndDialog` at `0x1800140ef`
- `USER32!EndDialog` at `0x1800140ef`
- `USER32!SetFocus` at `0x18001400a`
- `USER32!SetFocus` at `0x18001400a`
- `USER32!IsDlgButtonChecked` at `0x180013dd7`
- `USER32!IsDlgButtonChecked` at `0x180013dd7`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CFileOwnerDialog::OnCommand(CFileOwnerDialog *this, HWND hDlg, unsigned __int64 a3)
{
  unsigned __int64 v5; // r9
  int v6; // ebx
  __int64 v7; // r8
  int v8; // eax
  HWND DlgItem; // rbx
  BOOL ShouldEnableControl; // esi
  LPITEMIDLIST v11; // rbx
  int v12; // ebx
  WCHAR *Buffer; // rax
  const unsigned __int16 **v14; // rbx
  WCHAR *v15; // rax
  CFileOwnerDialog *v16; // rcx
  int IsSameVolume; // eax
  unsigned int v18; // r8d
  int v19; // eax
  int v20; // edi
  HWND v21; // rbx
  void **v23; // [rsp+20h] [rbp-49h] BYREF
  __int64 v24; // [rsp+28h] [rbp-41h]
  void **v25; // [rsp+30h] [rbp-39h] BYREF
  LPCWSTR *v26; // [rsp+38h] [rbp-31h]
  void **v27; // [rsp+40h] [rbp-29h] BYREF
  WCHAR **v28; // [rsp+48h] [rbp-21h]
  _browseinfoW bi; // [rsp+50h] [rbp-19h] BYREF

  v5 = a3 >> 16;
  v6 = (unsigned __int16)a3;
  v7 = 1;
  switch ( v6 )
  {
    case 2:
      EndDialog(hDlg, 0);
      return 0;
    case 1073:
      if ( (_WORD)v5 == 1 )
      {
        v19 = SendMessageW(*((HWND *)this + 4), 0x147u, 0, 0);
        v20 = v19 - 1;
        if ( *((int *)this + 23) <= 1 )
          v20 = v19;
        v21 = (HWND)*((_QWORD *)this + 3);
        SendMessageW(v21, 0xBu, 0, 0);
        CFileOwnerDialog::CreateListColumns(this, *((HWND *)this + 3), v20 == -1);
        CFileOwnerDialog::FillListView(this, (CFileOwnerDialog *)((char *)this + 80), *((HWND *)this + 3), v20);
        SendMessageW(v21, 0xBu, 1u, 0);
      }
      return 0;
    case 1079:
      CFileOwnerDialog::DeleteSelectedFiles(this, *((HWND *)this + 3));
      return 0;
    case 1080:
      CFileOwnerDialog::TakeOwnershipOfSelectedFiles((HWND *)this, *((HWND *)this + 3));
      return 1;
    case 1081:
      CString::CString((CString *)&v23);
      v23 = &CPath::`vftable';
      CString::CString((CString *)&v27);
      v27 = &CPath::`vftable';
      v12 = GetWindowTextLengthW(*((HWND *)this + 5)) + 1;
      Buffer = CString::GetBuffer((CString *)&v23, v12);
      GetWindowTextW(*((HWND *)this + 5), Buffer, v12);
      CString::ReleaseBuffer((CString *)&v23);
      CString::Trim((CString *)&v23);
      v14 = (const unsigned __int16 **)v24;
      v26 = (LPCWSTR *)v24;
      _InterlockedAdd((volatile signed __int32 *)(v24 + 12), 1u);
      v25 = &CPath::`vftable';
      v15 = CString::GetBuffer((CString *)&v25, -1);
      PathStripToRootW(v15);
      CString::ReleaseBuffer((CString *)&v25);
      CString::operator=(&v27, &v25);
      CString::Length((CString *)&v27);
      v25 = &CPath::`vftable';
      CString::~CString((CString *)&v25);
      IsSameVolume = CFileOwnerDialog::IsSameVolume(v16, *v28, **((WCHAR ***)this + 8));
      if ( IsSameVolume )
      {
        if ( IsSameVolume == 1 )
          CFileOwnerDialog::MoveSelectedFiles(this, *((HWND *)this + 3), *v14);
      }
      else
      {
        DiskQuotaMsgBox(*((HWND *)this + 2), 0x9EB1u, v18, 0x40u);
        SetWindowTextW(*((HWND *)this + 5), *v14);
        SetFocus(*((HWND *)this + 5));
      }
      v27 = &CPath::`vftable';
      CString::~CString((CString *)&v27);
      v23 = &CPath::`vftable';
      CString::~CString((CString *)&v23);
      return 0;
    case 1082:
      CString::CString((CString *)&v27);
      memset_0(&bi, 0, sizeof(bi));
      CString::CString((CString *)&v25, *(HINSTANCE *)this, 40624);
      bi.hwndOwner = hDlg;
      bi.pidlRoot = 0;
      bi.pszDisplayName = 0;
      bi.lpszTitle = *v26;
      bi.ulFlags = 1;
      bi.lpfn = (BFFCALLBACK)CFileOwnerDialog::BrowseForFolderCallback;
      bi.lParam = (LPARAM)&v27;
      bi.iImage = 0;
      v11 = SHBrowseForFolderW(&bi);
      CString::~CString((CString *)&v25);
      if ( v11 )
        SetWindowTextW(*((HWND *)this + 5), *v28);
      CString::~CString((CString *)&v27);
      return 1;
    case 1083:
      if ( (_WORD)v5 == 1024 )
      {
        DlgItem = GetDlgItem(*((HWND *)this + 2), 1081);
        ShouldEnableControl = CFileOwnerDialog::ShouldEnableControl(this, 0x439u);
        if ( ShouldEnableControl != IsWindowEnabled(DlgItem) )
          EnableWindow(DlgItem, ShouldEnableControl);
      }
      return 1;
  }
  if ( (unsigned int)(v6 - 1095) <= 1 && !(_WORD)v5 )
  {
    if ( IsDlgButtonChecked(*((HWND *)this + 2), v6) )
      CheckDlgButton(*((HWND *)this + 2), 1096 - ((_WORD)v6 != 1095), 0);
    v8 = SendMessageW(*((HWND *)this + 4), 0x147u, 0, 0);
    CFileOwnerDialog::FillListView(this, (CFileOwnerDialog *)((char *)this + 80), *((HWND *)this + 3), v8 - 1);
    return 1;
  }
  return v7;
}

```

## disassembly

```asm
0x180013d44  mov     [rsp-8+arg_18], r9
0x180013d49  push    rbp
0x180013d4a  push    rbx
0x180013d4b  push    rsi
0x180013d4c  push    rdi
0x180013d4d  push    r12
0x180013d4f  push    r14
0x180013d51  lea     rbp, [rsp-2Fh]
0x180013d56  sub     rsp, 98h
0x180013d5d  mov     rdi, rdx
0x180013d60  mov     r14, rcx
0x180013d63  mov     r9, r8
0x180013d66  shr     r9, 10h
0x180013d6a  movzx   ebx, r8w
0x180013d6e  mov     r12d, 1
0x180013d74  mov     r8d, r12d
0x180013d77  mov     ecx, ebx
0x180013d79  sub     ecx, 2
0x180013d7c  jz      loc_1800140EA
0x180013d82  sub     ecx, 42Fh
0x180013d88  jz      loc_180014069
0x180013d8e  sub     ecx, 6
0x180013d91  jz      loc_180014058
0x180013d97  sub     ecx, r8d
0x180013d9a  jz      loc_180014047
0x180013da0  sub     ecx, r8d
0x180013da3  jz      loc_180013F20
0x180013da9  sub     ecx, r8d
0x180013dac  jz      loc_180013E84
0x180013db2  sub     ecx, r8d
0x180013db5  jz      short loc_180013E2F
0x180013db7  sub     ecx, 0Ch
0x180013dba  jz      short loc_180013DC5
0x180013dbc  cmp     ecx, r8d
0x180013dbf  jnz     loc_1800140FA
0x180013dc5  xor     edi, edi
0x180013dc7  cmp     di, r9w
0x180013dcb  jnz     loc_1800140FA
0x180013dd1  mov     edx, ebx; nIDButton
0x180013dd3  mov     rcx, [r14+10h]; hDlg
0x180013dd7  call    cs:__imp_IsDlgButtonChecked
0x180013ddd  test    eax, eax
0x180013ddf  jz      short loc_180013E01
0x180013de1  mov     eax, 447h
0x180013de6  sub     ax, bx
0x180013de9  neg     ax
0x180013dec  sbb     edx, edx
0x180013dee  add     edx, 448h; nIDButton
0x180013df4  xor     r8d, r8d; uCheck
0x180013df7  mov     rcx, [r14+10h]; hDlg
0x180013dfb  call    cs:__imp_CheckDlgButton
0x180013e01  xor     r9d, r9d; lParam
0x180013e04  xor     r8d, r8d; wParam
0x180013e07  mov     edx, 147h; Msg
0x180013e0c  mov     rcx, [r14+20h]; hWnd
0x180013e10  call    cs:__imp_SendMessageW
0x180013e16  lea     r9d, [rax-1]; int
0x180013e1a  lea     rdx, [r14+50h]; struct COwnerList *
0x180013e1e  mov     r8, [r14+18h]; HWND
0x180013e22  mov     rcx, r14; this
0x180013e25  call    ?FillListView@CFileOwnerDialog@@AEAAXAEBVCOwnerList@@PEAUHWND__@@H@Z; CFileOwnerDialog::FillListView(COwnerList const &,HWND__ *,int)
0x180013e2a  jmp     loc_180013F18
0x180013e2f  mov     eax, 400h
0x180013e34  cmp     ax, r9w
0x180013e38  jnz     loc_180013F18
0x180013e3e  lea     edi, [rax+39h]
0x180013e41  mov     edx, edi; nIDDlgItem
0x180013e43  mov     rcx, [r14+10h]; hDlg
0x180013e47  call    cs:__imp_GetDlgItem
0x180013e4d  mov     rbx, rax
0x180013e50  mov     edx, edi; unsigned int
0x180013e52  mov     rcx, r14; this
0x180013e55  call    ?ShouldEnableControl@CFileOwnerDialog@@AEAA_NI@Z; CFileOwnerDialog::ShouldEnableControl(uint)
0x180013e5a  movzx   esi, al
0x180013e5d  mov     rcx, rbx; hWnd
0x180013e60  call    cs:__imp_IsWindowEnabled
0x180013e66  test    eax, eax
0x180013e68  setnz   cl
0x180013e6b  cmp     sil, cl
0x180013e6e  jz      loc_180013F18
0x180013e74  mov     edx, esi; bEnable
0x180013e76  mov     rcx, rbx; hWnd
0x180013e79  call    cs:__imp_EnableWindow
0x180013e7f  jmp     loc_180013F18
0x180013e84  lea     rcx, [rbp+57h+var_80]; this
0x180013e88  call    ??0CString@@QEAA@XZ; CString::CString(void)
0x180013e8d  nop
0x180013e8e  xor     edx, edx; Val
0x180013e90  lea     r8d, [rdx+40h]; Size
0x180013e94  lea     rcx, [rbp+57h+bi]; void *
0x180013e98  call    memset_0
0x180013e9d  mov     r8d, 9EB0h; int
0x180013ea3  mov     rdx, [r14]; HINSTANCE
0x180013ea6  lea     rcx, [rbp+57h+var_90]; this
0x180013eaa  call    ??0CString@@QEAA@PEAUHINSTANCE__@@HZZ; CString::CString(HINSTANCE__ *,int,...)
0x180013eaf  mov     [rbp+57h+bi.hwndOwner], rdi
0x180013eb3  xor     edi, edi
0x180013eb5  mov     [rbp+57h+bi.pidlRoot], rdi
0x180013eb9  mov     [rbp+57h+bi.pszDisplayName], rdi
0x180013ebd  mov     rax, [rbp+57h+var_88]
0x180013ec1  mov     rcx, [rax]
0x180013ec4  mov     [rbp+57h+bi.lpszTitle], rcx
0x180013ec8  mov     [rbp+57h+bi.ulFlags], r12d
0x180013ecc  lea     rax, ?BrowseForFolderCallback@CFileOwnerDialog@@CAHPEAUHWND__@@I_J1@Z; CFileOwnerDialog::BrowseForFolderCallback(HWND__ *,uint,__int64,__int64)
0x180013ed3  mov     [rbp+57h+bi.lpfn], rax
0x180013ed7  lea     rax, [rbp+57h+var_80]
0x180013edb  mov     [rbp+57h+bi.lParam], rax
0x180013edf  mov     [rbp+57h+bi.iImage], edi
0x180013ee2  lea     rcx, [rbp+57h+bi]; lpbi
0x180013ee6  call    cs:__imp_SHBrowseForFolderW
0x180013eec  mov     rbx, rax
0x180013eef  lea     rcx, [rbp+57h+var_90]; this
0x180013ef3  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x180013ef8  test    rbx, rbx
0x180013efb  jz      short loc_180013F0F
0x180013efd  mov     rdx, [rbp+57h+var_78]
0x180013f01  mov     rdx, [rdx]; lpString
0x180013f04  mov     rcx, [r14+28h]; hWnd
0x180013f08  call    cs:__imp_SetWindowTextW
0x180013f0e  nop
0x180013f0f  lea     rcx, [rbp+57h+var_80]; this
0x180013f13  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x180013f18  mov     r8, r12
0x180013f1b  jmp     loc_1800140FA
0x180013f20  lea     rcx, [rbp+57h+var_A0]; this
0x180013f24  call    ??0CString@@QEAA@XZ; CString::CString(void)
0x180013f29  lea     rsi, ??_7CPath@@6B@; const CPath::`vftable'
0x180013f30  mov     [rbp+57h+var_A0], rsi
0x180013f34  lea     rcx, [rbp+57h+var_80]; this
0x180013f38  call    ??0CString@@QEAA@XZ; CString::CString(void)
0x180013f3d  mov     [rbp+57h+var_80], rsi
0x180013f41  mov     rcx, [r14+28h]; hWnd
0x180013f45  call    cs:__imp_GetWindowTextLengthW
0x180013f4b  lea     ebx, [rax+1]
0x180013f4e  mov     edx, ebx; int
0x180013f50  lea     rcx, [rbp+57h+var_A0]; this
0x180013f54  call    ?GetBuffer@CString@@QEAAPEAGH@Z; CString::GetBuffer(int)
0x180013f59  mov     r8d, ebx; nMaxCount
0x180013f5c  mov     rdx, rax; lpString
0x180013f5f  mov     rcx, [r14+28h]; hWnd
0x180013f63  call    cs:__imp_GetWindowTextW
0x180013f69  lea     rcx, [rbp+57h+var_A0]; this
0x180013f6d  call    ?ReleaseBuffer@CString@@QEAAXXZ; CString::ReleaseBuffer(void)
0x180013f72  lea     rcx, [rbp+57h+var_A0]; this
0x180013f76  call    ?Trim@CString@@QEAAXXZ; CString::Trim(void)
0x180013f7b  mov     rbx, [rbp+57h+var_98]
0x180013f7f  mov     [rbp+57h+var_88], rbx
0x180013f83  lock add [rbx+0Ch], r12d
0x180013f88  mov     [rbp+57h+var_90], rsi
0x180013f8c  or      edx, 0FFFFFFFFh; int
0x180013f8f  lea     rcx, [rbp+57h+var_90]; this
0x180013f93  call    ?GetBuffer@CString@@QEAAPEAGH@Z; CString::GetBuffer(int)
0x180013f98  mov     rcx, rax; pszPath
0x180013f9b  call    cs:__imp_PathStripToRootW
0x180013fa1  lea     rcx, [rbp+57h+var_90]; this
0x180013fa5  call    ?ReleaseBuffer@CString@@QEAAXXZ; CString::ReleaseBuffer(void)
0x180013faa  lea     rdx, [rbp+57h+var_90]
0x180013fae  lea     rcx, [rbp+57h+var_80]
0x180013fb2  call    ??4CString@@QEAAAEAV0@AEBV0@@Z; CString::operator=(CString const &)
0x180013fb7  lea     rcx, [rbp+57h+var_80]; this
0x180013fbb  call    ?Length@CString@@QEBAHXZ; CString::Length(void)
0x180013fc0  nop
0x180013fc1  mov     [rbp+57h+var_90], rsi
0x180013fc5  lea     rcx, [rbp+57h+var_90]; this
0x180013fc9  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x180013fce  mov     r8, [r14+40h]
0x180013fd2  mov     r8, [r8]; unsigned __int16 *
0x180013fd5  mov     rdx, [rbp+57h+var_78]
0x180013fd9  mov     rdx, [rdx]; unsigned __int16 *
0x180013fdc  call    ?IsSameVolume@CFileOwnerDialog@@AEAAJPEBG0@Z; CFileOwnerDialog::IsSameVolume(ushort const *,ushort const *)
0x180013fe1  xor     edi, edi
0x180013fe3  test    eax, eax
0x180013fe5  jnz     short loc_180014012
0x180013fe7  mov     edx, 9EB1h; unsigned int
0x180013fec  lea     r9d, [rdi+40h]; unsigned int
0x180013ff0  mov     rcx, [r14+10h]; hWnd
0x180013ff4  call    ?DiskQuotaMsgBox@@YAHPEAUHWND__@@III@Z; DiskQuotaMsgBox(HWND__ *,uint,uint,uint)
0x180013ff9  mov     rdx, [rbx]; lpString
0x180013ffc  mov     rcx, [r14+28h]; hWnd
0x180014000  call    cs:__imp_SetWindowTextW
0x180014006  mov     rcx, [r14+28h]; hWnd
0x18001400a  call    cs:__imp_SetFocus
0x180014010  jmp     short loc_180014027
0x180014012  cmp     eax, r12d
0x180014015  jnz     short loc_180014027
0x180014017  mov     r8, [rbx]; unsigned __int16 *
0x18001401a  mov     rdx, [r14+18h]; hWnd
0x18001401e  mov     rcx, r14; this
0x180014021  call    ?MoveSelectedFiles@CFileOwnerDialog@@AEAAXPEAUHWND__@@PEBG@Z; CFileOwnerDialog::MoveSelectedFiles(HWND__ *,ushort const *)
0x180014026  nop
0x180014027  mov     [rbp+57h+var_80], rsi
0x18001402b  lea     rcx, [rbp+57h+var_80]; this
0x18001402f  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x180014034  nop
0x180014035  mov     [rbp+57h+var_A0], rsi
0x180014039  lea     rcx, [rbp+57h+var_A0]; this
0x18001403d  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x180014042  jmp     loc_1800140F7
0x180014047  mov     rdx, [r14+18h]; hWnd
0x18001404b  mov     rcx, r14; this
0x18001404e  call    ?TakeOwnershipOfSelectedFiles@CFileOwnerDialog@@AEAAJPEAUHWND__@@@Z; CFileOwnerDialog::TakeOwnershipOfSelectedFiles(HWND__ *)
0x180014053  jmp     loc_180013F18
0x180014058  mov     rdx, [r14+18h]; hWnd
0x18001405c  mov     rcx, r14; this
0x18001405f  call    ?DeleteSelectedFiles@CFileOwnerDialog@@AEAAXPEAUHWND__@@@Z; CFileOwnerDialog::DeleteSelectedFiles(HWND__ *)
0x180014064  jmp     loc_1800140F5
0x180014069  cmp     r12w, r9w
0x18001406d  jnz     loc_1800140F5
0x180014073  xor     r9d, r9d; lParam
0x180014076  xor     r8d, r8d; wParam
0x180014079  mov     edx, 147h; Msg
0x18001407e  mov     rcx, [r14+20h]; hWnd
0x180014082  call    cs:__imp_SendMessageW
0x180014088  lea     edi, [rax-1]
0x18001408b  cmp     [r14+5Ch], r12d
0x18001408f  cmovle  edi, eax
0x180014092  mov     rbx, [r14+18h]
0x180014096  mov     [rbp+57h+arg_18], rbx
0x18001409a  xor     r9d, r9d; lParam
0x18001409d  xor     r8d, r8d; wParam
0x1800140a0  lea     edx, [r9+0Bh]; Msg
0x1800140a4  mov     rcx, rbx; hWnd
0x1800140a7  call    cs:__imp_SendMessageW
0x1800140ad  nop
0x1800140ae  cmp     edi, 0FFFFFFFFh
0x1800140b1  setz    r8b; bool
0x1800140b5  mov     rdx, [r14+18h]; HWND
0x1800140b9  mov     rcx, r14; this
0x1800140bc  call    ?CreateListColumns@CFileOwnerDialog@@AEAAXPEAUHWND__@@_N@Z; CFileOwnerDialog::CreateListColumns(HWND__ *,bool)
0x1800140c1  mov     r9d, edi; int
0x1800140c4  mov     r8, [r14+18h]; HWND
0x1800140c8  lea     rdx, [r14+50h]; struct COwnerList *
0x1800140cc  mov     rcx, r14; this
0x1800140cf  call    ?FillListView@CFileOwnerDialog@@AEAAXAEBVCOwnerList@@PEAUHWND__@@H@Z; CFileOwnerDialog::FillListView(COwnerList const &,HWND__ *,int)
0x1800140d4  nop
0x1800140d5  xor     r9d, r9d; lParam
0x1800140d8  mov     r8, r12; wParam
0x1800140db  lea     edx, [r9+0Bh]; Msg
0x1800140df  mov     rcx, rbx; hWnd
0x1800140e2  call    cs:__imp_SendMessageW
0x1800140e8  jmp     short loc_1800140F5
0x1800140ea  xor     edx, edx; nResult
0x1800140ec  mov     rcx, rdi; hDlg
0x1800140ef  call    cs:__imp_EndDialog
0x1800140f5  xor     edi, edi
0x1800140f7  mov     r8, rdi
0x1800140fa  mov     rax, r8
0x1800140fd  add     rsp, 98h
0x180014104  pop     r14
0x180014106  pop     r12
0x180014108  pop     rdi
0x180014109  pop     rsi
0x18001410a  pop     rbx
0x18001410b  pop     rbp
0x18001410c  retn
```
