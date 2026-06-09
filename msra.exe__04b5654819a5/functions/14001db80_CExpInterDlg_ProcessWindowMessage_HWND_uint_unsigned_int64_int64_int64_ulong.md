# CExpInterDlg::ProcessWindowMessage(HWND__ *,uint,unsigned __int64,__int64,__int64 &,ulong)

- ea: `0x14001db80`
- end: `0x14001e21a`
- name: `?ProcessWindowMessage@CExpInterDlg@@UEAAHPEAUHWND__@@I_K_JAEA_JK@Z`
- size: `1690`
- prototype: `__int64 __usercall@<rax>(CExpInterDlg *__hidden this@<rcx>, HWND@<rdx>, unsigned int@<r8d>, unsigned __int64@<r9>, __int64, __int64 *, unsigned int)`
- caller_count: `0`
- callee_count: `26`
- tags: `registry_config, installer_update`

## callees

- `0x14000aa78`
- `0x14001a11c`
- `0x14001b044`
- `0x14001b16c`
- `0x14001b1fc`
- `0x14001b9c4`
- `0x14001ba74`
- `0x14001bb34`
- `0x14001bc44`
- `0x14001bd94`
- `0x14001bec0`
- `0x14001bf94`
- `0x14001c02c`
- `0x14001c458`
- `0x14001c9c8`
- `0x14001cbdc`
- `0x14001cd38`
- `0x14001d008`
- `0x14001d1ac`
- `0x14001d28c`
- `0x14001db80`
- `0x14001eb4c`
- `0x140028a2c`
- `0x14002a3d0`
- `0x14002c0a4`
- `0x14002c5f4`

## import_xrefs

- `GDI32!SetBkColor` at `0x14001e110`
- `GDI32!SetBkColor` at `0x14001e110`
- `GDI32!SetTextColor` at `0x14001e0ee`
- `GDI32!SetTextColor` at `0x14001e0ee`
- `USER32!GetDlgItem` at `0x14001dec3`
- `USER32!GetDlgItem` at `0x14001e0c6`
- `USER32!GetDlgItem` at `0x14001dec3`
- `USER32!GetDlgItem` at `0x14001e0c6`
- `USER32!LoadCursorW` at `0x14001e027`
- `USER32!LoadCursorW` at `0x14001e027`
- `USER32!IsIconic` at `0x14001df4a`
- `USER32!IsIconic` at `0x14001df4a`
- `USER32!GetSysColorBrush` at `0x14001e121`
- `USER32!GetSysColorBrush` at `0x14001e121`
- `USER32!SetCursor` at `0x14001e036`
- `USER32!SetCursor` at `0x14001e036`
- `USER32!PtInRect` at `0x14001e08d`
- `USER32!PtInRect` at `0x14001e08d`
- `USER32!OpenIcon` at `0x14001df5e`
- `USER32!OpenIcon` at `0x14001df5e`
- `USER32!KillTimer` at `0x14001ddea`
- `USER32!KillTimer` at `0x14001de4f`
- `USER32!KillTimer` at `0x14001def3`
- `USER32!KillTimer` at `0x14001ddea`
- `USER32!KillTimer` at `0x14001de4f`
- `USER32!KillTimer` at `0x14001def3`
- `USER32!PostMessageW` at `0x14001dd30`
- `USER32!PostMessageW` at `0x14001dd30`
- `USER32!SetForegroundWindow` at `0x14001df6e`
- `USER32!SetForegroundWindow` at `0x14001df6e`
- `USER32!SetFocus` at `0x14001ded2`
- `USER32!SetFocus` at `0x14001e062`
- `USER32!SetFocus` at `0x14001ded2`
- `USER32!SetFocus` at `0x14001e062`
- `USER32!GetSysColor` at `0x14001e0dd`
- `USER32!GetSysColor` at `0x14001e0ff`
- `USER32!GetSysColor` at `0x14001e0dd`
- `USER32!GetSysColor` at `0x14001e0ff`
- `USER32!ReleaseCapture` at `0x14001e00d`
- `USER32!ReleaseCapture` at `0x14001e00d`

## pseudocode

```c
_BOOL8 __fastcall CExpInterDlg::ProcessWindowMessage(
        CExpInterDlg *this,
        __int64 a2,
        unsigned __int64 a3,
        HWND a4,
        HWND a5,
        CExpInterDlg *a6,
        unsigned int a7)
{
  HBRUSH SysColorBrush; // r14
  __int64 v10; // rax
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // edx
  __int64 v19; // r9
  unsigned int v20; // ecx
  __int64 v21; // rsi
  __int64 v22; // rsi
  __int64 started; // rax
  __int64 v24; // rax
  bool v25; // zf
  unsigned __int16 v26; // dx
  unsigned int v27; // ecx
  unsigned int v28; // edx
  unsigned __int64 v29; // r8
  __int64 v30; // r9
  HWND DlgItem; // rax
  HCURSOR CursorW; // rax
  __int64 v33; // rdx
  COLORREF SysColor; // eax
  COLORREF v35; // eax
  int *v36; // [rsp+20h] [rbp-20h]
  int *v37; // [rsp+20h] [rbp-20h]
  POINT pt; // [rsp+30h] [rbp-10h]

  SysColorBrush = 0;
  if ( a7 )
    return 0;
  if ( (_DWORD)a3 != 272 )
  {
    switch ( (_DWORD)a3 )
    {
      case 5:
        v10 = CExpInterDlg::OnDialogResize(this, a2, (WPARAM)a4, (LPARAM)a5);
LABEL_7:
        *(_QWORD *)a6 = v10;
        return 1;
      case 0x10:
        v10 = CExpInterDlg::OnDialogDestroy(this, a2, a3, (__int64)a4, v36);
        goto LABEL_7;
      case 0x4E:
        if ( *((_DWORD *)a5 + 4) == -530 )
        {
          v12 = *((_DWORD *)a5 + 2);
          *((_QWORD *)a5 + 24) = 0;
          v13 = v12 - 225;
          if ( v13 )
          {
            v14 = v13 - 1;
            if ( v14 )
            {
              v15 = v14 - 1;
              if ( v15 )
              {
                v16 = v15 - 38;
                if ( v16 )
                {
                  v17 = v16 - 2737;
                  if ( v17 )
                  {
                    if ( v17 == 3 )
                      *((_QWORD *)a5 + 3) = 701;
                  }
                  else
                  {
                    *((_QWORD *)a5 + 3) = 697;
                  }
                }
                else
                {
                  *((_QWORD *)a5 + 3) = 694;
                }
              }
              else
              {
                *((_QWORD *)a5 + 3) = 696;
              }
            }
            else
            {
              *((_QWORD *)a5 + 3) = 695;
            }
          }
          else
          {
            *((_QWORD *)a5 + 3) = 692;
          }
        }
        goto LABEL_41;
      case 0x120:
        a7 = 0;
        v18 = *((_DWORD *)_AtlModule + 222);
        if ( v18 <= 0 )
          goto LABEL_29;
        v19 = *((_QWORD *)_AtlModule + 110);
        v20 = 0;
        while ( *(_WORD *)(v19 + 6LL * v20 + 2) != (_WORD)a4 )
        {
          if ( (int)++v20 >= v18 )
            goto LABEL_29;
        }
        v22 = *(unsigned __int16 *)(v19 + 6LL * v20 + 4);
        if ( (_WORD)v22 )
        {
          IsToolbarButtonEnabled(*((HWND *)this + 10), v22, (int *)&a7);
          if ( a7 == 1 )
            PostMessageW(*((HWND *)this + 1), 0x111u, (unsigned int)v22, 0);
          v21 = v22 | 0x20000;
        }
        else
        {
LABEL_29:
          v21 = 0;
        }
        *(_QWORD *)a6 = v21;
        return 1;
      case 0x113:
        started = CExpInterDlg::OnTimer(this, a2, (unsigned __int64)a4, (__int64)a4, v36);
LABEL_38:
        *(_QWORD *)a6 = started;
        return 1;
      case 0x53:
        goto LABEL_40;
      case 0x8018:
        started = CExpInterDlg::OnNeedPassword(this, a2, a3, (__int64)a5, v36);
        goto LABEL_38;
      case 0x801D:
        started = CExpInterDlg::OnStartConnection(this, a2, a3, (__int64)a4, v36);
        goto LABEL_38;
      case 0x8021:
        a7 = 1;
        v24 = CExpInterDlg::OnPreConnection(this, a2, a3, (__int64)a4, v36);
        v25 = a7 == 0;
        *(_QWORD *)a6 = v24;
        return !v25;
      case 0x800F:
        CSessionLogger::WriteToLog((int *)_AtlModule + 182, 18, 0);
        KillTimer(*((HWND *)this + 1), 1u);
        v26 = 668;
        v27 = 618;
        break;
      case 0x8010:
        CSessionLogger::WriteToLog((int *)_AtlModule + 182, 19, 0);
        KillTimer(*((HWND *)this + 1), 1u);
        v26 = 669;
        v27 = 619;
        break;
      case 0x8011:
        CSessionLogger::WriteToLog((int *)_AtlModule + 182, 20, 0);
        CExpInterDlg::EnableToolbarButton(this, 225, 1);
        *((_DWORD *)this + 40) = 1;
        goto LABEL_41;
      case 0x8012:
        if ( !*((_DWORD *)this + 36) )
          CExpInterDlg::OnButtonChat(this, a2, 0x8012u, a4, v36);
        DlgItem = GetDlgItem(*((HWND *)this + 1), 1035);
        SetFocus(DlgItem);
        goto LABEL_41;
      case 0x8014:
        KillTimer(*((HWND *)this + 1), 1u);
        v26 = 672;
        v27 = 630;
        break;
      default:
        switch ( (_DWORD)a3 )
        {
          case 0x801B:
            started = CExpInterDlg::OnSendContactInfo(this, a2, (unsigned __int64)a4, (__int64)a5, v36);
            goto LABEL_38;
          case 0x801E:
            started = CExpInterDlg::OnDiagnosisStart(this, a2, a3, (__int64)a5, v36);
            goto LABEL_38;
          case 0x8080:
            if ( IsIconic(*((HWND *)this + 1)) )
              OpenIcon(*((HWND *)this + 1));
            SetForegroundWindow(*((HWND *)this + 1));
            FlashAndBeep(*((HWND *)this + 1));
            goto LABEL_41;
          case 0x24:
            if ( a5 )
            {
              *((_DWORD *)a5 + 6) = 700;
              *((_DWORD *)a5 + 7) = 500;
            }
            goto LABEL_41;
          case 0x200:
            if ( *((_DWORD *)this + 36) )
            {
              if ( *((_DWORD *)this + 42) )
                CExpInterDlg::UpdateSplitterPosition(this, (unsigned __int16)a5, WORD1(a5));
              else
                CExpInterDlg::CheckHover(this, (unsigned __int16)a5, WORD1(a5));
            }
            goto LABEL_41;
          case 0x202:
            if ( *((_DWORD *)this + 42) )
            {
              *((_DWORD *)this + 42) = 0;
              ReleaseCapture();
              *((_DWORD *)this + 43) = 0;
              CursorW = LoadCursorW(0, (LPCWSTR)0x7F00);
              SetCursor(CursorW);
              CExpInterDlg::OnDialogResize(this, v33, 0, 0);
            }
            goto LABEL_41;
          case 0x201:
            SetFocus(*((HWND *)this + 1));
            pt.x = (unsigned __int16)a5;
            pt.y = WORD1(a5);
            if ( PtInRect((const RECT *)this + 11, pt) )
            {
              *((_DWORD *)this + 42) = 1;
              CExpInterDlg::DrawSplitter(this);
            }
            goto LABEL_41;
          case 0x138:
            if ( a5 == GetDlgItem(*((HWND *)this + 1), 1035) )
            {
              SysColor = GetSysColor(18);
              SetTextColor((HDC)a4, SysColor);
              v35 = GetSysColor(5);
              SetBkColor((HDC)a4, v35);
              SysColorBrush = GetSysColorBrush(5);
            }
            *(_QWORD *)a6 = SysColorBrush;
            return 1;
        }
        if ( (_DWORD)a3 != 273 )
        {
          if ( (_DWORD)a3 == 2 )
            *(_QWORD *)a6 = 1;
          return 0;
        }
        switch ( (_WORD)a4 )
        {
          case 0xE1:
            started = CExpInterDlg::OnButtonRequestControl(this, a2, 0x111u, a4, v36);
            goto LABEL_38;
          case 0x109:
            started = CExpInterDlg::OnButtonStopControl(this, a2, 0x111u, a4, v36);
            goto LABEL_38;
          case 0xE3:
            started = CExpInterDlg::OnButtonSettings(this, a2, 0x111u, a4, v36);
            goto LABEL_38;
          case 0xBBA:
            started = CExpInterDlg::OnButtonFitToScreen(this, a2, 0xBBAu, a4, v36);
            goto LABEL_38;
          case 0xBBD:
            started = CExpInterDlg::OnButtonChat(this, a2, 0xBBAu, a4, v36);
            goto LABEL_38;
        }
        if ( (_WORD)a4 != 226 )
        {
          if ( (_DWORD)a4 != 2 )
          {
            if ( (_WORD)a4 != 1 && (_WORD)a4 != 1037 || WORD1(a4) )
              return 0;
            started = CExpInterDlg::OnSendChatButton(this, a2, 0xBBAu, a4, v36);
            goto LABEL_38;
          }
LABEL_41:
          *(_QWORD *)a6 = 0;
          return 1;
        }
LABEL_40:
        ShowRAHelpText(*((HWND *)this + 10));
        goto LABEL_41;
    }
    ShowErrorMessage(v27, v26, *((HWND *)this + 1), 0, (unsigned __int16 *)0xFFFE, 0);
    CExpInterDlg::OnDialogDestroy(this, v28, v29, v30, v37);
    goto LABEL_41;
  }
  a7 = 1;
  *(_QWORD *)a6 = CExpInterDlg::OnInitDialog(this, a2, a3, (__int64)a4, (int *)&a7);
  if ( a7 )
    return 1;
  ATL::CDialogImplBaseT<ATL::CWindow>::ExecuteDlgInit(this, 112);
  *(_QWORD *)a6 = 1;
  return 0;
}

```

## disassembly

```asm
0x14001db80  push    rbp
0x14001db82  push    rbx
0x14001db83  push    rsi
0x14001db84  push    rdi
0x14001db85  push    r14
0x14001db87  mov     rbp, rsp
0x14001db8a  sub     rsp, 40h
0x14001db8e  xor     r14d, r14d
0x14001db91  mov     rsi, r9
0x14001db94  mov     rbx, rcx
0x14001db97  cmp     [rbp+arg_30], r14d
0x14001db9b  jnz     loc_14001E20C
0x14001dba1  cmp     r8d, 110h
0x14001dba8  jnz     short loc_14001DBE3
0x14001dbaa  lea     rax, [rbp+arg_30]
0x14001dbae  lea     edi, [r14+1]
0x14001dbb2  mov     [rsp+40h+var_20], rax; int *
0x14001dbb7  mov     [rbp+arg_30], edi
0x14001dbba  call    ?OnInitDialog@CExpInterDlg@@QEAA_JI_K_JAEAH@Z; CExpInterDlg::OnInitDialog(uint,unsigned __int64,__int64,int &)
0x14001dbbf  mov     rsi, [rbp+arg_28]
0x14001dbc3  mov     [rsi], rax
0x14001dbc6  cmp     [rbp+arg_30], r14d
0x14001dbca  jnz     loc_14001DCFB
0x14001dbd0  lea     edx, [rdi+6Fh]
0x14001dbd3  mov     rcx, rbx
0x14001dbd6  call    ?ExecuteDlgInit@?$CDialogImplBaseT@VCWindow@ATL@@@ATL@@QEAAHH@Z; ATL::CDialogImplBaseT<ATL::CWindow>::ExecuteDlgInit(int)
0x14001dbdb  mov     [rsi], rdi
0x14001dbde  jmp     loc_14001E20C
0x14001dbe3  cmp     r8d, 5
0x14001dbe7  jnz     short loc_14001DC06
0x14001dbe9  mov     r9, [rbp+arg_20]; __int64
0x14001dbed  mov     r8, rsi; unsigned __int64
0x14001dbf0  call    ?OnDialogResize@CExpInterDlg@@QEAA_JI_K_JAEAH@Z; CExpInterDlg::OnDialogResize(uint,unsigned __int64,__int64,int &)
0x14001dbf5  mov     rcx, [rbp+arg_28]; this
0x14001dbf9  mov     [rcx], rax
0x14001dbfc  mov     eax, 1
0x14001dc01  jmp     loc_14001E20E
0x14001dc06  cmp     r8d, 10h
0x14001dc0a  jnz     short loc_14001DC13
0x14001dc0c  call    ?OnDialogDestroy@CExpInterDlg@@QEAA_JI_K_JAEAH@Z; CExpInterDlg::OnDialogDestroy(uint,unsigned __int64,__int64,int &)
0x14001dc11  jmp     short loc_14001DBF5
0x14001dc13  mov     edi, 1
0x14001dc18  cmp     r8d, 4Eh ; 'N'
0x14001dc1c  jnz     loc_14001DCB1
0x14001dc22  mov     rdx, [rbp+arg_20]
0x14001dc26  cmp     dword ptr [rdx+10h], 0FFFFFDEEh
0x14001dc2d  jnz     loc_14001DD6C
0x14001dc33  mov     ecx, [rdx+8]
0x14001dc36  mov     [rdx+0C0h], r14
0x14001dc3d  sub     ecx, 0E1h
0x14001dc43  jz      short loc_14001DCA4
0x14001dc45  sub     ecx, edi
0x14001dc47  jz      short loc_14001DC97
0x14001dc49  sub     ecx, edi
0x14001dc4b  jz      short loc_14001DC8A
0x14001dc4d  sub     ecx, 26h ; '&'
0x14001dc50  jz      short loc_14001DC7D
0x14001dc52  sub     ecx, 0AB1h
0x14001dc58  jz      short loc_14001DC70
0x14001dc5a  cmp     ecx, 3
0x14001dc5d  jnz     loc_14001DD6C
0x14001dc63  mov     qword ptr [rdx+18h], 2BDh
0x14001dc6b  jmp     loc_14001DD6C
0x14001dc70  mov     qword ptr [rdx+18h], 2B9h
0x14001dc78  jmp     loc_14001DD6C
0x14001dc7d  mov     qword ptr [rdx+18h], 2B6h
0x14001dc85  jmp     loc_14001DD6C
0x14001dc8a  mov     qword ptr [rdx+18h], 2B8h
0x14001dc92  jmp     loc_14001DD6C
0x14001dc97  mov     qword ptr [rdx+18h], 2B7h
0x14001dc9f  jmp     loc_14001DD6C
0x14001dca4  mov     qword ptr [rdx+18h], 2B4h
0x14001dcac  jmp     loc_14001DD6C
0x14001dcb1  cmp     r8d, 120h
0x14001dcb8  jnz     loc_14001DD43
0x14001dcbe  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14001dcc5  mov     [rbp+arg_30], r14d
0x14001dcc9  mov     edx, [rax+378h]
0x14001dccf  test    edx, edx
0x14001dcd1  jle     short loc_14001DCF1
0x14001dcd3  mov     r9, [rax+370h]
0x14001dcda  mov     ecx, r14d
0x14001dcdd  mov     eax, ecx
0x14001dcdf  lea     r8, [rax+rax*2]
0x14001dce3  cmp     [r9+r8*2+2], si
0x14001dce9  jz      short loc_14001DD02
0x14001dceb  add     ecx, edi
0x14001dced  cmp     ecx, edx
0x14001dcef  jl      short loc_14001DCDD
0x14001dcf1  mov     rsi, r14
0x14001dcf4  mov     rax, [rbp+arg_28]
0x14001dcf8  mov     [rax], rsi
0x14001dcfb  mov     eax, edi
0x14001dcfd  jmp     loc_14001E20E
0x14001dd02  movzx   esi, word ptr [r9+r8*2+4]
0x14001dd08  test    si, si
0x14001dd0b  jz      short loc_14001DCF1
0x14001dd0d  mov     rcx, [rbx+50h]; HWND
0x14001dd11  lea     r8, [rbp+arg_30]; int *
0x14001dd15  mov     edx, esi; int
0x14001dd17  call    ?IsToolbarButtonEnabled@@YAJPEAUHWND__@@HPEAH@Z; IsToolbarButtonEnabled(HWND__ *,int,int *)
0x14001dd1c  cmp     [rbp+arg_30], edi
0x14001dd1f  jnz     short loc_14001DD3C
0x14001dd21  mov     rcx, [rbx+8]; hWnd
0x14001dd25  xor     r9d, r9d; lParam
0x14001dd28  mov     r8d, esi; wParam
0x14001dd2b  mov     edx, 111h; Msg
0x14001dd30  call    cs:__imp_PostMessageW
0x14001dd37  nop     dword ptr [rax+rax+00h]
0x14001dd3c  bts     rsi, 11h
0x14001dd41  jmp     short loc_14001DCF4
0x14001dd43  cmp     r8d, 113h
0x14001dd4a  jnz     short loc_14001DD5D
0x14001dd4c  mov     r8, rsi; unsigned __int64
0x14001dd4f  call    ?OnTimer@CExpInterDlg@@QEAA_JI_K_JAEAH@Z; CExpInterDlg::OnTimer(uint,unsigned __int64,__int64,int &)
0x14001dd54  mov     rcx, [rbp+arg_28]
0x14001dd58  mov     [rcx], rax
0x14001dd5b  jmp     short loc_14001DCFB
0x14001dd5d  cmp     r8d, 53h ; 'S'
0x14001dd61  jnz     short loc_14001DD75
0x14001dd63  mov     rcx, [rcx+50h]; HWND
0x14001dd67  call    ?ShowRAHelpText@@YAXPEAUHWND__@@@Z; ShowRAHelpText(HWND__ *)
0x14001dd6c  mov     rax, [rbp+arg_28]
0x14001dd70  mov     [rax], r14
0x14001dd73  jmp     short loc_14001DCFB
0x14001dd75  cmp     r8d, 8018h
0x14001dd7c  jnz     short loc_14001DD89
0x14001dd7e  mov     r9, [rbp+arg_20]; __int64
0x14001dd82  call    ?OnNeedPassword@CExpInterDlg@@QEAA_JI_K_JAEAH@Z; CExpInterDlg::OnNeedPassword(uint,unsigned __int64,__int64,int &)
0x14001dd87  jmp     short loc_14001DD54
0x14001dd89  cmp     r8d, 801Dh
0x14001dd90  jnz     short loc_14001DD99
0x14001dd92  call    ?OnStartConnection@CExpInterDlg@@QEAA_JI_K_JAEAH@Z; CExpInterDlg::OnStartConnection(uint,unsigned __int64,__int64,int &)
0x14001dd97  jmp     short loc_14001DD54
0x14001dd99  cmp     r8d, 8021h
0x14001dda0  jnz     short loc_14001DDC0
0x14001dda2  mov     [rbp+arg_30], edi
0x14001dda5  call    ?OnPreConnection@CExpInterDlg@@QEAA_JI_K_JAEAH@Z; CExpInterDlg::OnPreConnection(uint,unsigned __int64,__int64,int &)
0x14001ddaa  mov     rcx, [rbp+arg_28]
0x14001ddae  cmp     [rbp+arg_30], r14d
0x14001ddb2  mov     [rcx], rax
0x14001ddb5  mov     eax, r14d
0x14001ddb8  setnz   al
0x14001ddbb  jmp     loc_14001E20E
0x14001ddc0  cmp     r8d, 800Fh
0x14001ddc7  jnz     short loc_14001DE25
0x14001ddc9  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14001ddd0  xor     r8d, r8d
0x14001ddd3  add     rcx, 2D8h
0x14001ddda  lea     edx, [r8+12h]
0x14001ddde  call    ?WriteToLog@CSessionLogger@@QEAAJW4_SessionEvent@@PEAG@Z; CSessionLogger::WriteToLog(_SessionEvent,ushort *)
0x14001dde3  mov     rcx, [rbx+8]; hWnd
0x14001dde7  mov     rdx, rdi; uIDEvent
0x14001ddea  call    cs:__imp_KillTimer
0x14001ddf1  nop     dword ptr [rax+rax+00h]
0x14001ddf6  mov     edx, 29Ch; int
0x14001ddfb  lea     ecx, [rdx-32h]; int
0x14001ddfe  mov     r8, [rbx+8]; HWND
0x14001de02  xor     r9d, r9d; int
0x14001de05  mov     [rsp+40h+var_18], r14d; int
0x14001de0a  mov     [rsp+40h+var_20], 0FFFEh; int *
0x14001de13  call    ?ShowErrorMessage@@YAJHHPEAUHWND__@@JPEBGH@Z; ShowErrorMessage(int,int,HWND__ *,long,ushort const *,int)
0x14001de18  mov     rcx, rbx; this
0x14001de1b  call    ?OnDialogDestroy@CExpInterDlg@@QEAA_JI_K_JAEAH@Z; CExpInterDlg::OnDialogDestroy(uint,unsigned __int64,__int64,int &)
0x14001de20  jmp     loc_14001DD6C
0x14001de25  cmp     r8d, 8010h
0x14001de2c  jnz     short loc_14001DE65
0x14001de2e  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14001de35  xor     r8d, r8d
0x14001de38  add     rcx, 2D8h
0x14001de3f  lea     edx, [r8+13h]
0x14001de43  call    ?WriteToLog@CSessionLogger@@QEAAJW4_SessionEvent@@PEAG@Z; CSessionLogger::WriteToLog(_SessionEvent,ushort *)
0x14001de48  mov     rcx, [rbx+8]; hWnd
0x14001de4c  mov     rdx, rdi; uIDEvent
0x14001de4f  call    cs:__imp_KillTimer
0x14001de56  nop     dword ptr [rax+rax+00h]
0x14001de5b  mov     edx, 29Dh
0x14001de60  lea     ecx, [rdx-32h]
0x14001de63  jmp     short loc_14001DDFE
0x14001de65  cmp     r8d, 8011h
0x14001de6c  jnz     short loc_14001DEA3
0x14001de6e  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14001de75  xor     r8d, r8d
0x14001de78  add     rcx, 2D8h
0x14001de7f  lea     edx, [r8+14h]
0x14001de83  call    ?WriteToLog@CSessionLogger@@QEAAJW4_SessionEvent@@PEAG@Z; CSessionLogger::WriteToLog(_SessionEvent,ushort *)
0x14001de88  mov     r8d, edi; int
0x14001de8b  mov     edx, 0E1h; int
0x14001de90  mov     rcx, rbx; this
0x14001de93  call    ?EnableToolbarButton@CExpInterDlg@@QEAAJHH@Z; CExpInterDlg::EnableToolbarButton(int,int)
0x14001de98  mov     [rbx+0A0h], edi
0x14001de9e  jmp     loc_14001DD6C
0x14001dea3  cmp     r8d, 8012h
0x14001deaa  jnz     short loc_14001DEE3
0x14001deac  cmp     [rcx+90h], r14d
0x14001deb3  jnz     short loc_14001DEBA
0x14001deb5  call    ?OnButtonChat@CExpInterDlg@@QEAA_JGGPEAUHWND__@@AEAH@Z; CExpInterDlg::OnButtonChat(ushort,ushort,HWND__ *,int &)
0x14001deba  mov     rcx, [rbx+8]; hDlg
0x14001debe  mov     edx, 40Bh; nIDDlgItem
0x14001dec3  call    cs:__imp_GetDlgItem
0x14001deca  nop     dword ptr [rax+rax+00h]
0x14001decf  mov     rcx, rax; hWnd
0x14001ded2  call    cs:__imp_SetFocus
0x14001ded9  nop     dword ptr [rax+rax+00h]
0x14001dede  jmp     loc_14001DD6C
0x14001dee3  cmp     r8d, 8014h
0x14001deea  jnz     short loc_14001DF0C
0x14001deec  mov     rcx, [rcx+8]; hWnd
0x14001def0  mov     rdx, rdi; uIDEvent
0x14001def3  call    cs:__imp_KillTimer
0x14001defa  nop     dword ptr [rax+rax+00h]
0x14001deff  mov     edx, 2A0h; unsigned int
0x14001df04  lea     ecx, [rdx-2Ah]; this
0x14001df07  jmp     loc_14001DDFE
0x14001df0c  cmp     r8d, 801Bh
0x14001df13  jnz     short loc_14001DF26
0x14001df15  mov     r9, [rbp+arg_20]; __int64
0x14001df19  mov     r8, rsi; unsigned __int64
0x14001df1c  call    ?OnSendContactInfo@CExpInterDlg@@QEAA_JI_K_JAEAH@Z; CExpInterDlg::OnSendContactInfo(uint,unsigned __int64,__int64,int &)
0x14001df21  jmp     loc_14001DD54
0x14001df26  cmp     r8d, 801Eh
0x14001df2d  jnz     short loc_14001DF3D
0x14001df2f  mov     r9, [rbp+arg_20]; __int64
0x14001df33  call    ?OnDiagnosisStart@CExpInterDlg@@QEAA_JI_K_JAEAH@Z; CExpInterDlg::OnDiagnosisStart(uint,unsigned __int64,__int64,int &)
0x14001df38  jmp     loc_14001DD54
0x14001df3d  cmp     r8d, 8080h
0x14001df44  jnz     short loc_14001DF88
0x14001df46  mov     rcx, [rcx+8]; hWnd
0x14001df4a  call    cs:__imp_IsIconic
0x14001df51  nop     dword ptr [rax+rax+00h]
0x14001df56  test    eax, eax
0x14001df58  jz      short loc_14001DF6A
0x14001df5a  mov     rcx, [rbx+8]; hWnd
0x14001df5e  call    cs:__imp_OpenIcon
0x14001df65  nop     dword ptr [rax+rax+00h]
0x14001df6a  mov     rcx, [rbx+8]; hWnd
0x14001df6e  call    cs:__imp_SetForegroundWindow
0x14001df75  nop     dword ptr [rax+rax+00h]
0x14001df7a  mov     rcx, [rbx+8]; HWND
0x14001df7e  call    ?FlashAndBeep@@YAXPEAUHWND__@@@Z; FlashAndBeep(HWND__ *)
0x14001df83  jmp     loc_14001DD6C
0x14001df88  cmp     r8d, 24h ; '$'
0x14001df8c  jnz     short loc_14001DFAE
0x14001df8e  mov     rax, [rbp+arg_20]
0x14001df92  test    rax, rax
0x14001df95  jz      loc_14001DD6C
0x14001df9b  mov     dword ptr [rax+18h], 2BCh
0x14001dfa2  mov     dword ptr [rax+1Ch], 1F4h
0x14001dfa9  jmp     loc_14001DD6C
0x14001dfae  cmp     r8d, 200h
0x14001dfb5  jnz     short loc_14001DFF0
0x14001dfb7  cmp     [rcx+90h], r14d
0x14001dfbe  jz      loc_14001DD6C
0x14001dfc4  mov     rax, [rbp+arg_20]
0x14001dfc8  movzx   edx, ax; int
0x14001dfcb  shr     rax, 10h
0x14001dfcf  movzx   r8d, ax; int
0x14001dfd3  cmp     [rcx+0A8h], r14d
0x14001dfda  jz      short loc_14001DFE6
0x14001dfdc  call    ?UpdateSplitterPosition@CExpInterDlg@@AEAAXHH@Z; CExpInterDlg::UpdateSplitterPosition(int,int)
0x14001dfe1  jmp     loc_14001DD6C
0x14001dfe6  call    ?CheckHover@CExpInterDlg@@AEAAXHH@Z; CExpInterDlg::CheckHover(int,int)
0x14001dfeb  jmp     loc_14001DD6C
0x14001dff0  cmp     r8d, 202h
0x14001dff7  jnz     short loc_14001E055
0x14001dff9  cmp     [rcx+0A8h], r14d
0x14001e000  jz      loc_14001DD6C
0x14001e006  mov     [rcx+0A8h], r14d
0x14001e00d  call    cs:__imp_ReleaseCapture
0x14001e014  nop     dword ptr [rax+rax+00h]
0x14001e019  mov     edx, 7F00h; lpCursorName
0x14001e01e  mov     [rbx+0ACh], r14d
0x14001e025  xor     ecx, ecx; hInstance
0x14001e027  call    cs:__imp_LoadCursorW
0x14001e02e  nop     dword ptr [rax+rax+00h]
0x14001e033  mov     rcx, rax; hCursor
0x14001e036  call    cs:__imp_SetCursor
0x14001e03d  nop     dword ptr [rax+rax+00h]
0x14001e042  xor     r9d, r9d; __int64
0x14001e045  xor     r8d, r8d; unsigned __int64
0x14001e048  mov     rcx, rbx; this
0x14001e04b  call    ?OnDialogResize@CExpInterDlg@@QEAA_JI_K_JAEAH@Z; CExpInterDlg::OnDialogResize(uint,unsigned __int64,__int64,int &)
0x14001e050  jmp     loc_14001DD6C
0x14001e055  cmp     r8d, 201h
0x14001e05c  jnz     short loc_14001E0B4
0x14001e05e  mov     rcx, [rcx+8]; hWnd
0x14001e062  call    cs:__imp_SetFocus
0x14001e069  nop     dword ptr [rax+rax+00h]
0x14001e06e  mov     rcx, [rbp+arg_20]
0x14001e072  movzx   eax, cx
0x14001e075  shr     rcx, 10h
0x14001e079  mov     [rbp+pt.x], eax
0x14001e07c  movzx   eax, cx
0x14001e07f  lea     rcx, [rbx+0B0h]; lprc
0x14001e086  mov     [rbp+pt.y], eax
0x14001e089  mov     rdx, qword ptr [rbp+pt.x]; pt
0x14001e08d  call    cs:__imp_PtInRect
0x14001e094  nop     dword ptr [rax+rax+00h]
0x14001e099  test    eax, eax
0x14001e09b  jz      loc_14001DD6C
  ... truncated ...
```
