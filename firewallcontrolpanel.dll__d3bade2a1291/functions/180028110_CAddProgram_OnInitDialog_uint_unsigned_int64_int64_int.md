# CAddProgram::OnInitDialog(uint,unsigned __int64,__int64,int &)

- ea: `0x180028110`
- end: `0x18002839d`
- name: `?OnInitDialog@CAddProgram@@AEAA_JI_K_JAEAH@Z`
- size: `653`
- prototype: `__int64 __fastcall(CAddProgram *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180028710`

## callees

- `0x180011650`
- `0x180021f6c`
- `0x1800221a4`
- `0x180026f04`
- `0x180027438`
- `0x1800278b8`
- `0x180028110`
- `0x180030e6e`
- `0x180030ea0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028308`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028308`
- `SHELL32!SHBindToParent` at `0x18002828f`
- `SHELL32!SHBindToParent` at `0x18002828f`
- `SHELL32!SHParseDisplayName` at `0x18002826d`
- `SHELL32!SHParseDisplayName` at `0x18002826d`
- `SHELL32!__imp_Shell_GetImageLists` at `0x1800281d1`
- `SHELL32!__imp_Shell_GetImageLists` at `0x1800281d1`
- `USER32!SetCursor` at `0x180028192`
- `USER32!SetCursor` at `0x180028346`
- `USER32!SetCursor` at `0x180028192`
- `USER32!SetCursor` at `0x180028346`
- `USER32!LoadCursorW` at `0x180028163`
- `USER32!LoadCursorW` at `0x180028163`
- `USER32!SendMessageW` at `0x1800281c4`
- `USER32!SendMessageW` at `0x1800281f2`
- `USER32!SendMessageW` at `0x18002820e`
- `USER32!SendMessageW` at `0x180028244`
- `USER32!SendMessageW` at `0x180028338`
- `USER32!SendMessageW` at `0x1800281c4`
- `USER32!SendMessageW` at `0x1800281f2`
- `USER32!SendMessageW` at `0x18002820e`
- `USER32!SendMessageW` at `0x180028244`
- `USER32!SendMessageW` at `0x180028338`
- `USER32!GetSystemMetrics` at `0x180028227`
- `USER32!GetSystemMetrics` at `0x180028227`
- `USER32!GetClientRect` at `0x18002821c`
- `USER32!GetClientRect` at `0x18002821c`

## pseudocode

```c
__int64 __fastcall CAddProgram::OnInitDialog(CAddProgram *this)
{
  HCURSOR v2; // rsi
  HCURSOR CursorW; // rbx
  HWND *DlgItem; // rax
  HWND v5; // rcx
  HWND v6; // rcx
  __int16 SystemMetrics; // ax
  HWND v8; // rdx
  HWND v9; // rcx
  __int64 v10; // rbx
  unsigned int AllProfiles; // eax
  IShellFolder *pshf; // [rsp+40h] [rbp-C0h] BYREF
  LPITEMIDLIST ppidl; // [rsp+48h] [rbp-B8h] BYREF
  void *ppv; // [rsp+50h] [rbp-B0h] BYREF
  HIMAGELIST phimlSmall; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v17[8]; // [rsp+60h] [rbp-A0h] BYREF
  LPARAM lParam[2]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v19; // [rsp+78h] [rbp-88h]
  __int128 v20; // [rsp+88h] [rbp-78h]
  __int64 v21; // [rsp+98h] [rbp-68h]
  LPARAM v22; // [rsp+A0h] [rbp-60h] BYREF
  int v23; // [rsp+ACh] [rbp-54h]
  int v24; // [rsp+B0h] [rbp-50h]
  struct tagRECT Rect; // [rsp+100h] [rbp+0h] BYREF

  ppidl = 0;
  ppv = 0;
  pshf = 0;
  phimlSmall = 0;
  v2 = 0;
  CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
  v21 = 0;
  Rect = 0;
  *(_OWORD *)lParam = 0;
  v19 = 0;
  v20 = 0;
  if ( CursorW )
    v2 = SetCursor(CursorW);
  DlgItem = (HWND *)ATL::CWindow::GetDlgItem((char *)this + 8, v17, 1630);
  v5 = *DlgItem;
  *((_QWORD *)this + 11) = *DlgItem;
  SendMessageW(v5, 0x1036u, 0x20u, 32);
  if ( Shell_GetImageLists(0, &phimlSmall) )
    SendMessageW(*((HWND *)this + 11), 0x1003u, 1u, (LPARAM)phimlSmall);
  v6 = (HWND)*((_QWORD *)this + 11);
  lParam[0] = 1;
  SendMessageW(v6, 0x1061u, 0, (LPARAM)lParam);
  GetClientRect(*((HWND *)this + 11), &Rect);
  SystemMetrics = GetSystemMetrics(2);
  SendMessageW(*((HWND *)this + 11), 0x101Eu, 0, (unsigned __int16)(LOWORD(Rect.right) - SystemMetrics));
  ATL::CWindow::CenterWindow((CAddProgram *)((char *)this + 8), v8);
  if ( SHParseDisplayName(L"shell:::{7be9d83c-a729-4d97-b5a7-1b7313c39e0a}", 0, &ppidl, 0, 0) >= 0 )
  {
    if ( SHBindToParent(ppidl, &IID_IShellFolder, &ppv, 0) >= 0 )
    {
      if ( (*(int (__fastcall **)(void *, LPITEMIDLIST, _QWORD, GUID *, IShellFolder **))(*(_QWORD *)ppv + 40LL))(
             ppv,
             ppidl,
             0,
             &IID_IShellFolder,
             &pshf) >= 0 )
      {
        CAddProgram::AddProgramsToList(this, pshf);
        CAddProgram::EnumFoldersAndAddPrograms(this, pshf);
        ((void (__fastcall *)(IShellFolder *))pshf->lpVtbl->Release)(pshf);
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    CoTaskMemFree(ppidl);
  }
  memset_0(&v22, 0, 0x58u);
  v9 = (HWND)*((_QWORD *)this + 11);
  v24 = 3;
  v23 = 3;
  SendMessageW(v9, 0x102Bu, 0, (LPARAM)&v22);
  if ( CursorW )
    SetCursor(v2);
  v10 = *((_QWORD *)this + 12);
  AllProfiles = GetAllProfiles();
  CFwOpenPortMgr::GetProfileDisplayMask(
    *(CFwOpenPortMgr **)(v10 + 48),
    AllProfiles,
    0,
    (unsigned int *)this + 28,
    (unsigned int *)this + 29,
    (unsigned int *)this + 30,
    1);
  return 1;
}

```

## disassembly

```asm
0x180028110  push    rbp
0x180028112  push    rbx
0x180028113  push    rsi
0x180028114  push    rdi
0x180028115  push    r12
0x180028117  push    r14
0x180028119  lea     rbp, [rsp-28h]
0x18002811e  sub     rsp, 128h
0x180028125  mov     rax, cs:__security_cookie
0x18002812c  xor     rax, rsp
0x18002812f  mov     [rbp+50h+var_40], rax
0x180028133  mov     rdi, rcx
0x180028136  mov     [rsp+150h+ppidl], 0
0x18002813f  xor     ecx, ecx; hInstance
0x180028141  mov     [rsp+150h+ppv], 0
0x18002814a  mov     edx, 7F02h; lpCursorName
0x18002814f  mov     [rsp+150h+pshf], 0
0x180028158  mov     [rsp+150h+phimlSmall], 0
0x180028161  xor     esi, esi
0x180028163  call    cs:__imp_LoadCursorW
0x180028169  xorps   xmm1, xmm1
0x18002816c  xorps   xmm0, xmm0
0x18002816f  mov     rbx, rax
0x180028172  xor     eax, eax
0x180028174  mov     [rbp+50h+var_B8], rax
0x180028178  movups  xmmword ptr [rbp+50h+Rect.left], xmm0
0x18002817c  movups  xmmword ptr [rsp+150h+lParam], xmm1
0x180028181  movups  [rsp+150h+var_D8], xmm1
0x180028186  movups  [rbp+50h+var_C8], xmm1
0x18002818a  test    rbx, rbx
0x18002818d  jz      short loc_18002819B
0x18002818f  mov     rcx, rbx; hCursor
0x180028192  call    cs:__imp_SetCursor
0x180028198  mov     rsi, rax
0x18002819b  mov     r8d, 65Eh
0x1800281a1  lea     rdx, [rsp+150h+var_F0]
0x1800281a6  lea     rcx, [rdi+8]
0x1800281aa  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x1800281af  mov     r8d, 20h ; ' '; wParam
0x1800281b5  mov     edx, 1036h; Msg
0x1800281ba  mov     r9d, r8d; lParam
0x1800281bd  mov     rcx, [rax]; hWnd
0x1800281c0  mov     [rdi+58h], rcx
0x1800281c4  call    cs:__imp_SendMessageW
0x1800281ca  lea     rdx, [rsp+150h+phimlSmall]; phimlSmall
0x1800281cf  xor     ecx, ecx; phiml
0x1800281d1  call    cs:__imp_Shell_GetImageLists
0x1800281d7  mov     r12d, 1
0x1800281dd  test    eax, eax
0x1800281df  jz      short loc_1800281F8
0x1800281e1  mov     r9, [rsp+150h+phimlSmall]; lParam
0x1800281e6  mov     r8d, r12d; wParam
0x1800281e9  mov     rcx, [rdi+58h]; hWnd
0x1800281ed  mov     edx, 1003h; Msg
0x1800281f2  call    cs:__imp_SendMessageW
0x1800281f8  mov     rcx, [rdi+58h]; hWnd
0x1800281fc  lea     r9, [rsp+150h+lParam]; lParam
0x180028201  xor     r8d, r8d; wParam
0x180028204  mov     [rsp+150h+lParam], r12
0x180028209  mov     edx, 1061h; Msg
0x18002820e  call    cs:__imp_SendMessageW
0x180028214  mov     rcx, [rdi+58h]; hWnd
0x180028218  lea     rdx, [rbp+50h+Rect]; lpRect
0x18002821c  call    cs:__imp_GetClientRect
0x180028222  mov     ecx, 2; nIndex
0x180028227  call    cs:__imp_GetSystemMetrics
0x18002822d  movzx   edx, word ptr [rbp+50h+Rect.right]
0x180028231  xor     r8d, r8d; wParam
0x180028234  mov     rcx, [rdi+58h]; hWnd
0x180028238  sub     dx, ax
0x18002823b  movzx   r9d, dx; lParam
0x18002823f  mov     edx, 101Eh; Msg
0x180028244  call    cs:__imp_SendMessageW
0x18002824a  lea     rcx, [rdi+8]; this
0x18002824e  call    ?CenterWindow@CWindow@ATL@@QEAAHPEAUHWND__@@@Z; ATL::CWindow::CenterWindow(HWND__ *)
0x180028253  xor     r9d, r9d; sfgaoIn
0x180028256  mov     [rsp+150h+psfgaoOut], 0; psfgaoOut
0x18002825f  lea     r8, [rsp+150h+ppidl]; ppidl
0x180028264  xor     edx, edx; pbc
0x180028266  lea     rcx, pszName; "shell:::{7be9d83c-a729-4d97-b5a7-1b7313"...
0x18002826d  call    cs:__imp_SHParseDisplayName
0x180028273  test    eax, eax
0x180028275  js      loc_18002830E
0x18002827b  mov     rcx, [rsp+150h+ppidl]; pidl
0x180028280  lea     r8, [rsp+150h+ppv]; ppv
0x180028285  xor     r9d, r9d; ppidlLast
0x180028288  lea     rdx, IID_IShellFolder; riid
0x18002828f  call    cs:__imp_SHBindToParent
0x180028295  test    eax, eax
0x180028297  js      short loc_180028303
0x180028299  mov     rcx, [rsp+150h+ppv]
0x18002829e  lea     rdx, [rsp+150h+pshf]
0x1800282a3  mov     [rsp+150h+psfgaoOut], rdx
0x1800282a8  lea     r9, IID_IShellFolder
0x1800282af  mov     rdx, [rsp+150h+ppidl]
0x1800282b4  xor     r8d, r8d
0x1800282b7  mov     rax, [rcx]
0x1800282ba  mov     rax, [rax+28h]
0x1800282be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800282c3  test    eax, eax
0x1800282c5  js      short loc_1800282F2
0x1800282c7  mov     rdx, [rsp+150h+pshf]; pshf
0x1800282cc  mov     rcx, rdi; this
0x1800282cf  call    ?AddProgramsToList@CAddProgram@@AEAAJPEAUIShellFolder@@@Z; CAddProgram::AddProgramsToList(IShellFolder *)
0x1800282d4  mov     rdx, [rsp+150h+pshf]; struct IShellFolder *
0x1800282d9  mov     rcx, rdi; this
0x1800282dc  call    ?EnumFoldersAndAddPrograms@CAddProgram@@AEAAJPEAUIShellFolder@@@Z; CAddProgram::EnumFoldersAndAddPrograms(IShellFolder *)
0x1800282e1  mov     rcx, [rsp+150h+pshf]
0x1800282e6  mov     rax, [rcx]
0x1800282e9  mov     rax, [rax+10h]
0x1800282ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800282f2  mov     rcx, [rsp+150h+ppv]
0x1800282f7  mov     rax, [rcx]
0x1800282fa  mov     rax, [rax+10h]
0x1800282fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028303  mov     rcx, [rsp+150h+ppidl]; pv
0x180028308  call    cs:__imp_CoTaskMemFree
0x18002830e  xor     edx, edx; Val
0x180028310  lea     rcx, [rbp+50h+var_B0]; void *
0x180028314  lea     r8d, [rdx+58h]; Size
0x180028318  call    memset_0
0x18002831d  mov     rcx, [rdi+58h]; hWnd
0x180028321  lea     r9, [rbp+50h+var_B0]; lParam
0x180028325  mov     eax, 3
0x18002832a  xor     r8d, r8d; wParam
0x18002832d  mov     edx, 102Bh; Msg
0x180028332  mov     [rbp+50h+var_A0], eax
0x180028335  mov     [rbp+50h+var_A4], eax
0x180028338  call    cs:__imp_SendMessageW
0x18002833e  test    rbx, rbx
0x180028341  jz      short loc_18002834C
0x180028343  mov     rcx, rsi; hCursor
0x180028346  call    cs:__imp_SetCursor
0x18002834c  mov     rbx, [rdi+60h]
0x180028350  call    ?GetAllProfiles@@YAKXZ; GetAllProfiles(void)
0x180028355  mov     rcx, [rbx+30h]; this
0x180028359  lea     rdx, [rdi+78h]
0x18002835d  lea     r8, [rdi+74h]
0x180028361  mov     [rsp+150h+var_120], r12d; int
0x180028366  mov     [rsp+150h+var_128], rdx; unsigned int *
0x18002836b  lea     r9, [rdi+70h]; unsigned int *
0x18002836f  mov     [rsp+150h+psfgaoOut], r8; unsigned int *
0x180028374  mov     edx, eax; unsigned int
0x180028376  xor     r8d, r8d; int
0x180028379  call    ?GetProfileDisplayMask@CFwOpenPortMgr@@QEAAXKHAEAK00H@Z; CFwOpenPortMgr::GetProfileDisplayMask(ulong,int,ulong &,ulong &,ulong &,int)
0x18002837e  mov     rax, r12
0x180028381  mov     rcx, [rbp+50h+var_40]
0x180028385  xor     rcx, rsp; StackCookie
0x180028388  call    __security_check_cookie
0x18002838d  add     rsp, 128h
0x180028394  pop     r14
0x180028396  pop     r12
0x180028398  pop     rdi
0x180028399  pop     rsi
0x18002839a  pop     rbx
0x18002839b  pop     rbp
0x18002839c  retn
```
