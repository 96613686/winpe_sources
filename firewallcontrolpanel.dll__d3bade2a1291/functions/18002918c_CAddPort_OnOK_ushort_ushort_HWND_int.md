# CAddPort::OnOK(ushort,ushort,HWND__ *,int &)

- ea: `0x18002918c`
- end: `0x180029525`
- name: `?OnOK@CAddPort@@AEAA_JGGPEAUHWND__@@AEAH@Z`
- size: `921`
- prototype: `__int64 __fastcall(CAddPort *__hidden this, unsigned __int16, unsigned __int16, HWND, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180029530`

## callees

- `0x180009040`
- `0x18000c358`
- `0x18000d5b0`
- `0x180011650`
- `0x180015780`
- `0x180017ea8`
- `0x180018660`
- `0x18002918c`
- `0x1800299ac`
- `0x180030ea0`
- `0x180032010`

## import_xrefs

- `ntdll!WinSqmIncrementDWORD` at `0x18002949e`
- `ntdll!WinSqmIncrementDWORD` at `0x18002949e`
- `ntdll!EtwEventWrite` at `0x180029203`
- `ntdll!EtwEventWrite` at `0x1800294e4`
- `ntdll!EtwEventWrite` at `0x180029203`
- `ntdll!EtwEventWrite` at `0x1800294e4`
- `USER32!EndDialog` at `0x1800294aa`
- `USER32!EndDialog` at `0x1800294aa`
- `USER32!GetDlgItemInt` at `0x18002926f`
- `USER32!GetDlgItemInt` at `0x18002926f`
- `USER32!IsDlgButtonChecked` at `0x180029243`
- `USER32!IsDlgButtonChecked` at `0x180029243`
- `USER32!GetWindowTextW` at `0x180029234`
- `USER32!GetWindowTextW` at `0x180029234`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CAddPort::OnOK(CAddPort *this, __int16 a2, __int64 a3, HWND a4, int *a5)
{
  HWND *v6; // r12
  HWND *DlgItem; // rax
  UINT v8; // edi
  int v9; // r14d
  UINT DlgItemInt; // esi
  const unsigned __int16 *v11; // r13
  const unsigned __int16 *v12; // r15
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rax
  _QWORD *Next; // rax
  __int64 v17; // rdi
  CConfigureApps *v18; // rcx
  __int64 v19; // rax
  __int64 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+60h] [rbp-A0h] BYREF
  BOOL Translated; // [rsp+68h] [rbp-98h] BYREF
  const unsigned __int16 *v24; // [rsp+70h] [rbp-90h] BYREF
  const unsigned __int16 *v25; // [rsp+78h] [rbp-88h] BYREF
  __int64 v26; // [rsp+80h] [rbp-80h] BYREF
  WCHAR String[264]; // [rsp+90h] [rbp-70h] BYREF

  Translated = 0;
  v26 = 0;
  v24 = WTL::_atltmpPchNil;
  v25 = WTL::_atltmpPchNil;
  if ( a2 )
  {
    *a5 = 0;
    goto LABEL_28;
  }
  if ( g_Provider )
    EtwEventWrite(g_Provider, AddPortException_Start, 0, 0);
  *a5 = 1;
  v6 = (HWND *)((char *)this + 8);
  DlgItem = (HWND *)ATL::CWindow::GetDlgItem((char *)this + 8, &v22, 1637);
  GetWindowTextW(*DlgItem, String, 260);
  v8 = IsDlgButtonChecked(*((HWND *)this + 1), 1641);
  v9 = v8 != 0 ? 6 : 17;
  DlgItemInt = GetDlgItemInt(*((HWND *)this + 1), 1639, &Translated, 1);
  if ( DlgItemInt <= 0xFFFF && Translated )
  {
    WTL::CString::LoadStringW((WTL::CString *)&v24, 0x34u);
    WTL::CString::LoadStringW((WTL::CString *)&v25, 0x35u);
    v11 = v25;
    v12 = v25;
    if ( v8 )
      v12 = v24;
    if ( *((_DWORD *)this + 16)
      || (v13 = *((_QWORD *)this + 13), DlgItemInt != *(unsigned __int16 *)(v13 + 72))
      || v9 != *(_DWORD *)(v13 + 76) )
    {
      v14 = *(_QWORD *)(*((_QWORD *)this + 14) + 48LL);
      v15 = *(_QWORD *)(v14 + 16);
      v22 = v15;
      while ( v15 )
      {
        Next = (_QWORD *)ATL::CAtlList<CFwProfileViewUpdate *,ATL::CElementTraits<CFwProfileViewUpdate *>>::GetNext(
                           v14,
                           &v22);
        v17 = *Next;
        if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*Next + 96LL))(*Next) == 1
          && (_WORD)DlgItemInt == *(_WORD *)(v17 + 72)
          && v9 == *(_DWORD *)(v17 + 76) )
        {
          (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v17 + 24LL))(v17, &v26);
          MessageBoxFromResourceWithArgs(*v6, g_hinst, 0x2F5Au, 0x2Fu, 0x10010u, v12, DlgItemInt, String, v12, v26);
          goto LABEL_28;
        }
        v15 = v22;
      }
    }
    v18 = (CConfigureApps *)*((_QWORD *)this + 14);
    if ( *((_DWORD *)this + 16) )
    {
      if ( (int)CConfigureApps::AddPort(
                  v18,
                  String,
                  DlgItemInt,
                  v9,
                  *((_DWORD *)this + 40),
                  *((struct IFwCplLua **)this + 15)) < 0 )
      {
        MessageBoxFromResourceWithArgs(*v6, g_hinst, 0x2F5Au, 0x40u, 0x10010u, v12, DlgItemInt, String);
        goto LABEL_28;
      }
      goto LABEL_26;
    }
    if ( (int)CConfigureApps::EditPort(
                v18,
                String,
                DlgItemInt,
                v9,
                *((struct CFwOpenPort **)this + 13),
                *((_DWORD *)this + 40),
                *((_DWORD *)this + 41)) >= 0 )
    {
LABEL_26:
      WinSqmIncrementDWORD(0, 3102, 1);
      EndDialog(*v6, 0);
      goto LABEL_28;
    }
    v22 = 0;
    (*(void (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 13) + 24LL))(*((_QWORD *)this + 13), &v22);
    v19 = *((_QWORD *)this + 13);
    if ( *(_DWORD *)(v19 + 76) == 6 )
      v11 = v24;
    LODWORD(v21) = *(unsigned __int16 *)(v19 + 72);
    MessageBoxFromResourceWithArgs(*v6, g_hinst, 0x2F5Au, 0x41u, 0x10010u, v11, v21, v22, v12, DlgItemInt, String);
  }
  else
  {
    CTooltip::ShowErrBalloon((CAddPort *)((char *)this + 128), 0x667u, 0x3Eu, 0x3Du);
  }
LABEL_28:
  if ( g_Provider )
    EtwEventWrite(g_Provider, AddPortException_End, 0, 0);
  WTL::CString::~CString((WTL::CString *)&v25);
  WTL::CString::~CString((WTL::CString *)&v24);
  return 0;
}

```

## disassembly

```asm
0x18002918c  push    rbp
0x18002918e  push    rbx
0x18002918f  push    rsi
0x180029190  push    rdi
0x180029191  push    r12
0x180029193  push    r13
0x180029195  push    r14
0x180029197  push    r15
0x180029199  lea     rbp, [rsp-1B8h]
0x1800291a1  sub     rsp, 2B8h
0x1800291a8  mov     rax, cs:__security_cookie
0x1800291af  xor     rax, rsp
0x1800291b2  mov     [rbp+1F0h+var_50], rax
0x1800291b9  mov     rbx, rcx
0x1800291bc  mov     rdi, [rbp+1F0h+arg_20]
0x1800291c3  xor     ecx, ecx
0x1800291c5  mov     [rsp+2F0h+Translated], ecx
0x1800291c9  mov     [rbp+1F0h+var_270], rcx
0x1800291cd  mov     rax, cs:?_atltmpPchNil@WTL@@3PEBGEB; ushort const * const WTL::_atltmpPchNil
0x1800291d4  mov     [rsp+2F0h+var_280], rax
0x1800291d9  mov     [rsp+2F0h+var_278], rax
0x1800291de  test    dx, dx
0x1800291e1  jz      short loc_1800291EA
0x1800291e3  mov     [rdi], ecx
0x1800291e5  jmp     loc_1800294CB
0x1800291ea  mov     rcx, cs:g_Provider
0x1800291f1  test    rcx, rcx
0x1800291f4  jz      short loc_180029209
0x1800291f6  xor     r9d, r9d
0x1800291f9  xor     r8d, r8d
0x1800291fc  lea     rdx, AddPortException_Start
0x180029203  call    cs:__imp_EtwEventWrite
0x180029209  mov     esi, 1
0x18002920e  mov     [rdi], esi
0x180029210  lea     r12, [rbx+8]
0x180029214  mov     r8d, 665h
0x18002921a  lea     rdx, [rsp+2F0h+var_290]
0x18002921f  mov     rcx, r12
0x180029222  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180029227  mov     r8d, 104h; nMaxCount
0x18002922d  lea     rdx, [rbp+1F0h+String]; lpString
0x180029231  mov     rcx, [rax]; hWnd
0x180029234  call    cs:__imp_GetWindowTextW
0x18002923a  mov     edx, 669h; nIDButton
0x18002923f  mov     rcx, [r12]; hDlg
0x180029243  call    cs:__imp_IsDlgButtonChecked
0x180029249  mov     edi, eax
0x18002924b  mov     ecx, eax
0x18002924d  neg     ecx
0x18002924f  sbb     r14d, r14d
0x180029252  and     r14d, 0FFFFFFF5h
0x180029256  add     r14d, 11h
0x18002925a  mov     r9d, esi; bSigned
0x18002925d  lea     r8, [rsp+2F0h+Translated]; lpTranslated
0x180029262  mov     r15d, 667h
0x180029268  mov     edx, r15d; nIDDlgItem
0x18002926b  mov     rcx, [r12]; hDlg
0x18002926f  call    cs:__imp_GetDlgItemInt
0x180029275  mov     esi, eax
0x180029277  cmp     eax, 0FFFFh
0x18002927c  ja      loc_1800294B2
0x180029282  cmp     [rsp+2F0h+Translated], 0
0x180029287  jz      loc_1800294B2
0x18002928d  mov     edx, 34h ; '4'; uID
0x180029292  lea     rcx, [rsp+2F0h+var_280]; this
0x180029297  call    ?LoadStringW@CString@WTL@@QEAAHI@Z; WTL::CString::LoadStringW(uint)
0x18002929c  mov     edx, 35h ; '5'; uID
0x1800292a1  lea     rcx, [rsp+2F0h+var_278]; this
0x1800292a6  call    ?LoadStringW@CString@WTL@@QEAAHI@Z; WTL::CString::LoadStringW(uint)
0x1800292ab  mov     r13, [rsp+2F0h+var_278]
0x1800292b0  mov     r15, r13
0x1800292b3  test    edi, edi
0x1800292b5  cmovnz  r15, [rsp+2F0h+var_280]
0x1800292bb  cmp     dword ptr [rbx+40h], 0
0x1800292bf  jnz     short loc_1800292D7
0x1800292c1  mov     rcx, [rbx+68h]
0x1800292c5  movzx   eax, word ptr [rcx+48h]
0x1800292c9  cmp     esi, eax
0x1800292cb  jnz     short loc_1800292D7
0x1800292cd  cmp     r14d, [rcx+4Ch]
0x1800292d1  jz      loc_180029381
0x1800292d7  mov     rax, [rbx+70h]
0x1800292db  mov     rcx, [rax+30h]
0x1800292df  mov     rax, [rcx+10h]
0x1800292e3  mov     [rsp+2F0h+var_290], rax
0x1800292e8  test    rax, rax
0x1800292eb  jz      loc_180029381
0x1800292f1  lea     rdx, [rsp+2F0h+var_290]
0x1800292f6  call    ?GetNext@?$CAtlList@PEAVCFwProfileViewUpdate@@V?$CElementTraits@PEAVCFwProfileViewUpdate@@@ATL@@@ATL@@QEAAAEAPEAVCFwProfileViewUpdate@@AEAPEAU__POSITION@@@Z; ATL::CAtlList<CFwProfileViewUpdate *,ATL::CElementTraits<CFwProfileViewUpdate *>>::GetNext(__POSITION * &)
0x1800292fb  mov     rdi, [rax]
0x1800292fe  mov     rax, [rdi]
0x180029301  mov     rcx, rdi
0x180029304  mov     rax, [rax+60h]
0x180029308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002930d  cmp     eax, 1
0x180029310  jnz     short loc_18002931E
0x180029312  cmp     si, [rdi+48h]
0x180029316  jnz     short loc_18002931E
0x180029318  cmp     r14d, [rdi+4Ch]
0x18002931c  jz      short loc_180029325
0x18002931e  mov     rax, [rsp+2F0h+var_290]
0x180029323  jmp     short loc_1800292E8
0x180029325  mov     rax, [rdi]
0x180029328  lea     rdx, [rbp+1F0h+var_270]
0x18002932c  mov     rcx, rdi
0x18002932f  mov     rax, [rax+18h]
0x180029333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029338  mov     rax, [rbp+1F0h+var_270]
0x18002933c  mov     [rsp+2F0h+var_2A8], rax
0x180029341  mov     [rsp+2F0h+var_2B0], r15
0x180029346  lea     rax, [rbp+1F0h+String]
0x18002934a  mov     [rsp+2F0h+var_2B8], rax
0x18002934f  mov     dword ptr [rsp+2F0h+var_2C0], esi
0x180029353  mov     [rsp+2F0h+var_2C8], r15
0x180029358  mov     [rsp+2F0h+uType], 10010h; uType
0x180029360  mov     r9d, 2Fh ; '/'; UINT
0x180029366  mov     r8d, 2F5Ah; uID
0x18002936c  mov     rdx, cs:g_hinst; hInstance
0x180029373  mov     rcx, [r12]; hWnd
0x180029377  call    ?MessageBoxFromResourceWithArgs@@YAHPEAUHWND__@@PEAUHINSTANCE__@@IIIZZ; MessageBoxFromResourceWithArgs(HWND__ *,HINSTANCE__ *,uint,uint,uint,...)
0x18002937c  jmp     loc_1800294CB
0x180029381  mov     rcx, [rbx+70h]; this
0x180029385  movzx   r9d, r14w; unsigned __int16
0x180029389  movzx   r8d, si; unsigned __int16
0x18002938d  lea     rdx, [rbp+1F0h+String]; unsigned __int16 *
0x180029391  cmp     dword ptr [rbx+40h], 0
0x180029395  jz      short loc_1800293F2
0x180029397  mov     rax, [rbx+78h]
0x18002939b  mov     [rsp+2F0h+var_2C8], rax; struct IFwCplLua *
0x1800293a0  mov     eax, [rbx+0A0h]
0x1800293a6  mov     [rsp+2F0h+uType], eax; unsigned int
0x1800293aa  call    ?AddPort@CConfigureApps@@QEAAJPEBGGGKPEAUIFwCplLua@@@Z; CConfigureApps::AddPort(ushort const *,ushort,ushort,ulong,IFwCplLua *)
0x1800293af  test    eax, eax
0x1800293b1  jns     loc_180029493
0x1800293b7  lea     rax, [rbp+1F0h+String]
0x1800293bb  mov     [rsp+2F0h+var_2B8], rax
0x1800293c0  mov     dword ptr [rsp+2F0h+var_2C0], esi
0x1800293c4  mov     [rsp+2F0h+var_2C8], r15
0x1800293c9  mov     [rsp+2F0h+uType], 10010h; uType
0x1800293d1  mov     r9d, 40h ; '@'; UINT
0x1800293d7  mov     r8d, 2F5Ah; uID
0x1800293dd  mov     rdx, cs:g_hinst; hInstance
0x1800293e4  mov     rcx, [r12]; hWnd
0x1800293e8  call    ?MessageBoxFromResourceWithArgs@@YAHPEAUHWND__@@PEAUHINSTANCE__@@IIIZZ; MessageBoxFromResourceWithArgs(HWND__ *,HINSTANCE__ *,uint,uint,uint,...)
0x1800293ed  jmp     loc_1800294CB
0x1800293f2  mov     eax, [rbx+0A4h]
0x1800293f8  mov     dword ptr [rsp+2F0h+var_2C0], eax; int
0x1800293fc  mov     eax, [rbx+0A0h]
0x180029402  mov     dword ptr [rsp+2F0h+var_2C8], eax; unsigned int
0x180029406  mov     rax, [rbx+68h]
0x18002940a  mov     qword ptr [rsp+2F0h+uType], rax; struct CFwOpenPort *
0x18002940f  call    ?EditPort@CConfigureApps@@QEAAJPEBGGGPEAVCFwOpenPort@@KH@Z; CConfigureApps::EditPort(ushort const *,ushort,ushort,CFwOpenPort *,ulong,int)
0x180029414  test    eax, eax
0x180029416  jns     short loc_180029493
0x180029418  mov     [rsp+2F0h+var_290], 0
0x180029421  mov     rcx, [rbx+68h]
0x180029425  mov     rax, [rcx]
0x180029428  lea     rdx, [rsp+2F0h+var_290]
0x18002942d  mov     rax, [rax+18h]
0x180029431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029436  mov     rax, [rbx+68h]
0x18002943a  cmp     dword ptr [rax+4Ch], 6
0x18002943e  cmovz   r13, [rsp+2F0h+var_280]
0x180029444  movzx   ecx, word ptr [rax+48h]
0x180029448  lea     rax, [rbp+1F0h+String]
0x18002944c  mov     [rsp+2F0h+var_2A0], rax
0x180029451  mov     dword ptr [rsp+2F0h+var_2A8], esi
0x180029455  mov     [rsp+2F0h+var_2B0], r15
0x18002945a  mov     rax, [rsp+2F0h+var_290]
0x18002945f  mov     [rsp+2F0h+var_2B8], rax
0x180029464  mov     dword ptr [rsp+2F0h+var_2C0], ecx
0x180029468  mov     [rsp+2F0h+var_2C8], r13
0x18002946d  mov     [rsp+2F0h+uType], 10010h; uType
0x180029475  mov     r9d, 41h ; 'A'; UINT
0x18002947b  mov     r8d, 2F5Ah; uID
0x180029481  mov     rdx, cs:g_hinst; hInstance
0x180029488  mov     rcx, [r12]; hWnd
0x18002948c  call    ?MessageBoxFromResourceWithArgs@@YAHPEAUHWND__@@PEAUHINSTANCE__@@IIIZZ; MessageBoxFromResourceWithArgs(HWND__ *,HINSTANCE__ *,uint,uint,uint,...)
0x180029491  jmp     short loc_1800294CB
0x180029493  mov     edx, 0C1Eh
0x180029498  xor     ecx, ecx
0x18002949a  lea     r8d, [rcx+1]
0x18002949e  call    cs:__imp_WinSqmIncrementDWORD
0x1800294a4  xor     edx, edx; nResult
0x1800294a6  mov     rcx, [r12]; hDlg
0x1800294aa  call    cs:__imp_EndDialog
0x1800294b0  jmp     short loc_1800294CB
0x1800294b2  lea     rcx, [rbx+80h]; this
0x1800294b9  mov     r9d, 3Dh ; '='; unsigned int
0x1800294bf  lea     r8d, [r9+1]; unsigned int
0x1800294c3  mov     edx, r15d; unsigned int
0x1800294c6  call    ?ShowErrBalloon@CTooltip@@QEAAXIIIZZ; CTooltip::ShowErrBalloon(uint,uint,uint,...)
0x1800294cb  mov     rcx, cs:g_Provider
0x1800294d2  test    rcx, rcx
0x1800294d5  jz      short loc_1800294EB
0x1800294d7  xor     r9d, r9d
0x1800294da  xor     r8d, r8d
0x1800294dd  lea     rdx, AddPortException_End
0x1800294e4  call    cs:__imp_EtwEventWrite
0x1800294ea  nop
0x1800294eb  lea     rcx, [rsp+2F0h+var_278]; this
0x1800294f0  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x1800294f5  nop
0x1800294f6  lea     rcx, [rsp+2F0h+var_280]; this
0x1800294fb  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180029500  xor     eax, eax
0x180029502  mov     rcx, [rbp+1F0h+var_50]
0x180029509  xor     rcx, rsp; StackCookie
0x18002950c  call    __security_check_cookie
0x180029511  add     rsp, 2B8h
0x180029518  pop     r15
0x18002951a  pop     r14
0x18002951c  pop     r13
0x18002951e  pop     r12
0x180029520  pop     rdi
0x180029521  pop     rsi
0x180029522  pop     rbx
0x180029523  pop     rbp
0x180029524  retn
```
