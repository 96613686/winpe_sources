# WizardDialogProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x140034200`
- end: `0x1400344d6`
- name: `?WizardDialogProc@@YAHPEAUHWND__@@I_K_J@Z`
- size: `726`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140016a34`
- `0x14002c0a4`
- `0x1400313e4`
- `0x140031918`
- `0x140031a2c`
- `0x140031adc`
- `0x140031e8c`
- `0x14003207c`
- `0x140032274`
- `0x1400328fc`
- `0x140032bf0`
- `0x140033d68`
- `0x140034200`
- `0x14004ad80`

## import_xrefs

- `USER32!ScrollWindow` at `0x140034370`
- `USER32!ScrollWindow` at `0x140034370`
- `USER32!GetScrollInfo` at `0x1400342d3`
- `USER32!GetScrollInfo` at `0x14003433a`
- `USER32!GetScrollInfo` at `0x1400342d3`
- `USER32!GetScrollInfo` at `0x14003433a`
- `USER32!SetScrollInfo` at `0x140034324`
- `USER32!SetScrollInfo` at `0x140034324`
- `USER32!UpdateWindow` at `0x14003437f`
- `USER32!UpdateWindow` at `0x14003437f`

## pseudocode

```c
__int64 __fastcall WizardDialogProc(HWND a1, unsigned int a2, unsigned __int64 a3, __int64 a4)
{
  unsigned int v5; // r14d
  CEventLogger *v6; // rcx
  int v7; // ebx
  __int64 v8; // rax
  unsigned int v9; // edx
  unsigned int v10; // edx
  unsigned int v11; // edx
  unsigned int v12; // edx
  int v13; // ecx
  unsigned int v14; // edx
  unsigned int v15; // edx
  unsigned int v16; // edx
  CWizard *v17; // rsi
  CRemoteAssistanceApp *v18; // rcx
  SCROLLINFO v20; // [rsp+30h] [rbp-30h] BYREF

  v5 = 0;
  v6 = _AtlModule;
  v7 = a3;
  v8 = *((_QWORD *)_AtlModule + 61);
  if ( v8 && *(_DWORD *)(v8 + 40) != 1 )
  {
    *(_DWORD *)(v8 + 40) = 1;
    if ( a2 > 0x8016 )
    {
      v14 = a2 - 32791;
      if ( v14 )
      {
        v15 = v14 - 3;
        if ( v15 )
        {
          v16 = v15 - 8;
          if ( v16 )
          {
            if ( v16 == 1 )
            {
              v17 = (CWizard *)*((_QWORD *)v6 + 61);
              if ( a3 == 1 )
              {
                CWizard::CloseDownWizard(*((_QWORD *)v6 + 61), 111, 0);
              }
              else
              {
                ShowErrorMessage(0x243u, 0x244u, a1, 0, (unsigned __int16 *)0xFFFE, 759);
                CRemoteAssistanceApp::ResetTicketAndClearVC(v18);
                CWizard::SetCurrentPage(v17, 0x7D9u);
              }
            }
          }
          else
          {
            CWizard::HandlePNRPStatus(*((CWizard **)v6 + 61), a3, a1);
          }
        }
        else
        {
          CWizard::HandleContactSearch(*((CWizard **)v6 + 61), a3, a4, a1);
        }
      }
      else
      {
        CWizard::HandleOfferRAString(*((CWizard **)v6 + 61), a3, a1);
      }
      goto LABEL_34;
    }
    if ( a2 == 32790 )
    {
      CWizard::HandleOfferRASessions(*((CWizard **)v6 + 61), a3, a1);
    }
    else
    {
      v9 = a2 - 78;
      if ( v9 )
      {
        v10 = v9 - 194;
        if ( v10 )
        {
          v11 = v10 - 1;
          if ( v11 )
          {
            v12 = v11 - 4;
            if ( v12 )
            {
              if ( v12 == 32512 )
                CWizard::HandleEmailClientReturn(*((CWizard **)v6 + 61), a3, a1);
              goto LABEL_34;
            }
            v20.cbSize = 28;
            v20.fMask = 23;
            memset(&v20.nMin, 0, 20);
            GetScrollInfo(a1, 1, &v20);
            dword_1400642A4 = v20.nPos;
            if ( (_WORD)v7 )
            {
              if ( (unsigned __int16)v7 != 1 )
              {
                if ( (unsigned __int16)v7 == 5 )
                  v20.nPos = HIWORD(v7);
                goto LABEL_18;
              }
              v13 = v20.nPos + 1;
            }
            else
            {
              v13 = v20.nPos - 1;
            }
            v20.nPos = v13;
LABEL_18:
            v20.fMask = 4;
            SetScrollInfo(a1, 1, &v20, 1);
            GetScrollInfo(a1, 1, &v20);
            if ( v20.nPos != dword_1400642A4 )
            {
              ScrollWindow(a1, 0, dword_140064238 * (dword_1400642A4 - v20.nPos), 0, 0);
              UpdateWindow(a1);
            }
            goto LABEL_34;
          }
          CWizard::OnCommand(*((CWizard **)v6 + 61), a1, a3, a4);
        }
        else
        {
          CWizard::OnInitDialog(*((struct IRaContactControl ***)v6 + 61), a1);
        }
      }
      else
      {
        v5 = CWizard::OnNotify(*((CWizard **)v6 + 61), a3, a4, a1);
      }
    }
LABEL_34:
    *(_DWORD *)(*((_QWORD *)_AtlModule + 61) + 40LL) = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x140034200  mov     [rsp-28h+arg_8], rbx
0x140034205  push    rbp
0x140034206  push    rsi
0x140034207  push    rdi
0x140034208  push    r14
0x14003420a  push    r15
0x14003420c  mov     rbp, rsp
0x14003420f  sub     rsp, 60h
0x140034213  mov     rax, cs:__security_cookie
0x14003421a  xor     rax, rsp
0x14003421d  mov     [rbp+var_10], rax
0x140034221  mov     rdi, rcx
0x140034224  xor     r14d, r14d
0x140034227  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14003422e  mov     r10, r9
0x140034231  mov     rbx, r8
0x140034234  mov     rax, [rcx+1E8h]
0x14003423b  test    rax, rax
0x14003423e  jz      loc_1400344B2
0x140034244  lea     r15d, [r14+1]
0x140034248  cmp     [rax+28h], r15d
0x14003424c  jz      loc_1400344B2
0x140034252  mov     [rax+28h], r15d
0x140034256  mov     eax, 8016h
0x14003425b  cmp     edx, eax
0x14003425d  ja      loc_1400343EC
0x140034263  jz      loc_1400343D5
0x140034269  sub     edx, 4Eh ; 'N'
0x14003426c  jz      loc_1400343B8
0x140034272  sub     edx, 0C2h
0x140034278  jz      loc_1400343A4
0x14003427e  sub     edx, r15d
0x140034281  jz      loc_140034390
0x140034287  sub     edx, 4
0x14003428a  jz      short loc_1400342AF
0x14003428c  cmp     edx, 7F00h
0x140034292  jnz     loc_14003449D
0x140034298  mov     rcx, [rcx+1E8h]; this
0x14003429f  mov     r8, rdi; HWND
0x1400342a2  mov     rdx, rbx; unsigned __int64
0x1400342a5  call    ?HandleEmailClientReturn@CWizard@@QEAAJ_KPEAUHWND__@@@Z; CWizard::HandleEmailClientReturn(unsigned __int64,HWND__ *)
0x1400342aa  jmp     loc_14003449D
0x1400342af  xorps   xmm0, xmm0
0x1400342b2  mov     [rbp+var_30.nTrackPos], r14d
0x1400342b6  lea     r8, [rbp+var_30]; lpsi
0x1400342ba  mov     [rbp+var_30.cbSize], 1Ch
0x1400342c1  mov     edx, r15d; nBar
0x1400342c4  mov     [rbp+var_30.fMask], 17h
0x1400342cb  mov     rcx, rdi; hwnd
0x1400342ce  movdqu  xmmword ptr [rbp+var_30.nMin], xmm0
0x1400342d3  call    cs:__imp_GetScrollInfo
0x1400342da  nop     dword ptr [rax+rax+00h]
0x1400342df  mov     ecx, [rbp+var_30.nPos]
0x1400342e2  movzx   edx, bx
0x1400342e5  mov     cs:dword_1400642A4, ecx
0x1400342eb  test    edx, edx
0x1400342ed  jz      short loc_14003430A
0x1400342ef  sub     edx, r15d
0x1400342f2  jz      short loc_140034305
0x1400342f4  cmp     edx, 4
0x1400342f7  jnz     short loc_140034310
0x1400342f9  shr     rbx, 10h
0x1400342fd  movzx   eax, bx
0x140034300  mov     [rbp+var_30.nPos], eax
0x140034303  jmp     short loc_140034310
0x140034305  add     ecx, r15d
0x140034308  jmp     short loc_14003430D
0x14003430a  sub     ecx, r15d
0x14003430d  mov     [rbp+var_30.nPos], ecx
0x140034310  mov     r9d, r15d; redraw
0x140034313  mov     [rbp+var_30.fMask], 4
0x14003431a  lea     r8, [rbp+var_30]; lpsi
0x14003431e  mov     edx, r15d; nBar
0x140034321  mov     rcx, rdi; hwnd
0x140034324  call    cs:__imp_SetScrollInfo
0x14003432b  nop     dword ptr [rax+rax+00h]
0x140034330  lea     r8, [rbp+var_30]; lpsi
0x140034334  mov     edx, r15d; nBar
0x140034337  mov     rcx, rdi; hwnd
0x14003433a  call    cs:__imp_GetScrollInfo
0x140034341  nop     dword ptr [rax+rax+00h]
0x140034346  mov     r8d, cs:dword_1400642A4
0x14003434d  cmp     [rbp+var_30.nPos], r8d
0x140034351  jz      loc_14003449D
0x140034357  sub     r8d, [rbp+var_30.nPos]
0x14003435b  xor     r9d, r9d; lpRect
0x14003435e  imul    r8d, cs:dword_140064238; YAmount
0x140034366  xor     edx, edx; XAmount
0x140034368  mov     rcx, rdi; hWnd
0x14003436b  mov     [rsp+60h+lpClipRect], r14; lpClipRect
0x140034370  call    cs:__imp_ScrollWindow
0x140034377  nop     dword ptr [rax+rax+00h]
0x14003437c  mov     rcx, rdi; hWnd
0x14003437f  call    cs:__imp_UpdateWindow
0x140034386  nop     dword ptr [rax+rax+00h]
0x14003438b  jmp     loc_14003449D
0x140034390  mov     rcx, [rcx+1E8h]; this
0x140034397  mov     rdx, rdi; HWND
0x14003439a  call    ?OnCommand@CWizard@@QEAAJPEAUHWND__@@_K_J@Z; CWizard::OnCommand(HWND__ *,unsigned __int64,__int64)
0x14003439f  jmp     loc_14003449D
0x1400343a4  mov     rcx, [rcx+1E8h]; this
0x1400343ab  mov     rdx, rdi; HWND
0x1400343ae  call    ?OnInitDialog@CWizard@@QEAAJPEAUHWND__@@@Z; CWizard::OnInitDialog(HWND__ *)
0x1400343b3  jmp     loc_14003449D
0x1400343b8  mov     rcx, [rcx+1E8h]; this
0x1400343bf  mov     r9, rdi; HWND
0x1400343c2  mov     r8, r10; __int64
0x1400343c5  mov     rdx, rbx; unsigned __int64
0x1400343c8  call    ?OnNotify@CWizard@@QEAAH_K_JPEAUHWND__@@@Z; CWizard::OnNotify(unsigned __int64,__int64,HWND__ *)
0x1400343cd  mov     r14d, eax
0x1400343d0  jmp     loc_14003449D
0x1400343d5  mov     rcx, [rcx+1E8h]; this
0x1400343dc  mov     r8, rdi; HWND
0x1400343df  mov     rdx, rbx; unsigned int
0x1400343e2  call    ?HandleOfferRASessions@CWizard@@QEAAJ_KPEAUHWND__@@@Z; CWizard::HandleOfferRASessions(unsigned __int64,HWND__ *)
0x1400343e7  jmp     loc_14003449D
0x1400343ec  sub     edx, 8017h
0x1400343f2  jz      loc_14003448B
0x1400343f8  sub     edx, 3
0x1400343fb  jz      short loc_140034474
0x1400343fd  sub     edx, 8
0x140034400  jz      short loc_140034460
0x140034402  cmp     edx, r15d
0x140034405  jnz     loc_14003449D
0x14003440b  mov     rsi, [rcx+1E8h]
0x140034412  cmp     rbx, r15
0x140034415  jnz     short loc_140034428
0x140034417  xor     r8d, r8d
0x14003441a  mov     rcx, rsi
0x14003441d  lea     edx, [r8+6Fh]
0x140034421  call    ?CloseDownWizard@CWizard@@AEAAXIW4_RATYPE@@@Z; CWizard::CloseDownWizard(uint,_RATYPE)
0x140034426  jmp     short loc_14003449D
0x140034428  mov     edx, 244h; int
0x14003442d  mov     [rsp+60h+var_38], 2F7h; int
0x140034435  xor     r9d, r9d; int
0x140034438  mov     [rsp+60h+lpClipRect], 0FFFEh; unsigned __int16 *
0x140034441  mov     r8, rdi; HWND
0x140034444  lea     ecx, [rdx-1]; int
0x140034447  call    ?ShowErrorMessage@@YAJHHPEAUHWND__@@JPEBGH@Z; ShowErrorMessage(int,int,HWND__ *,long,ushort const *,int)
0x14003444c  call    ?ResetTicketAndClearVC@CRemoteAssistanceApp@@QEAAJXZ; CRemoteAssistanceApp::ResetTicketAndClearVC(void)
0x140034451  mov     edx, 7D9h; unsigned int
0x140034456  mov     rcx, rsi; this
0x140034459  call    ?SetCurrentPage@CWizard@@QEAAXI@Z; CWizard::SetCurrentPage(uint)
0x14003445e  jmp     short loc_14003449D
0x140034460  mov     rcx, [rcx+1E8h]; this
0x140034467  mov     r8, rdi; HWND
0x14003446a  mov     rdx, rbx; unsigned __int64
0x14003446d  call    ?HandlePNRPStatus@CWizard@@QEAAJ_KPEAUHWND__@@@Z; CWizard::HandlePNRPStatus(unsigned __int64,HWND__ *)
0x140034472  jmp     short loc_14003449D
0x140034474  mov     rcx, [rcx+1E8h]; this
0x14003447b  mov     r9, rdi; HWND
0x14003447e  mov     r8, r10; __int64
0x140034481  mov     rdx, rbx; unsigned __int64
0x140034484  call    ?HandleContactSearch@CWizard@@QEAAJ_K_JPEAUHWND__@@@Z; CWizard::HandleContactSearch(unsigned __int64,__int64,HWND__ *)
0x140034489  jmp     short loc_14003449D
0x14003448b  mov     rcx, [rcx+1E8h]; this
0x140034492  mov     r8, rdi; HWND
0x140034495  mov     rdx, rbx; unsigned int
0x140034498  call    ?HandleOfferRAString@CWizard@@QEAAJ_KPEAUHWND__@@@Z; CWizard::HandleOfferRAString(unsigned __int64,HWND__ *)
0x14003449d  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x1400344a4  mov     rcx, [rax+1E8h]
0x1400344ab  mov     dword ptr [rcx+28h], 0
0x1400344b2  mov     eax, r14d
0x1400344b5  mov     rcx, [rbp+var_10]
0x1400344b9  xor     rcx, rsp; StackCookie
0x1400344bc  call    __security_check_cookie
0x1400344c1  mov     rbx, [rsp+60h+arg_8]
0x1400344c9  add     rsp, 60h
0x1400344cd  pop     r15
0x1400344cf  pop     r14
0x1400344d1  pop     rdi
0x1400344d2  pop     rsi
0x1400344d3  pop     rbp
0x1400344d4  retn
```
