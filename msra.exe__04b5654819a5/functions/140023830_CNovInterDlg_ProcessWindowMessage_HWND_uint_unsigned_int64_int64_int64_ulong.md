# CNovInterDlg::ProcessWindowMessage(HWND__ *,uint,unsigned __int64,__int64,__int64 &,ulong)

- ea: `0x140023830`
- end: `0x140023d63`
- name: `?ProcessWindowMessage@CNovInterDlg@@UEAAHPEAUHWND__@@I_K_JAEA_JK@Z`
- size: `1331`
- prototype: `__int64 __usercall@<rax>(CNovInterDlg *__hidden this@<rcx>, HWND@<rdx>, unsigned int@<r8d>, unsigned __int64@<r9>, __int64, __int64 *, unsigned int)`
- caller_count: `0`
- callee_count: `32`
- tags: `registry_config`

## callees

- `0x14001f624`
- `0x14001f9ac`
- `0x14002090c`
- `0x140020b18`
- `0x140020c24`
- `0x140020e0c`
- `0x140020e6c`
- `0x140020ef8`
- `0x140020fac`
- `0x1400211f0`
- `0x1400213ac`
- `0x1400214ac`
- `0x140021540`
- `0x140021a5c`
- `0x140021d04`
- `0x140021e00`
- `0x1400223c4`
- `0x1400225cc`
- `0x140022778`
- `0x140022900`
- `0x140022b68`
- `0x140022c68`
- `0x140022f78`
- `0x140023830`
- `0x140024734`
- `0x140028a2c`
- `0x14002a3d0`
- `0x14002b040`
- `0x14002c5f4`
- `0x14002ca28`
- `0x140037e7c`
- `0x14004d010`

## import_xrefs

- `USER32!GetDlgItem` at `0x140023b44`
- `USER32!GetDlgItem` at `0x140023c84`
- `USER32!GetDlgItem` at `0x140023b44`
- `USER32!GetDlgItem` at `0x140023c84`
- `USER32!IsIconic` at `0x140023a9d`
- `USER32!IsIconic` at `0x140023a9d`
- `USER32!OpenIcon` at `0x140023ab1`
- `USER32!OpenIcon` at `0x140023ab1`
- `USER32!PostMessageW` at `0x1400239bd`
- `USER32!PostMessageW` at `0x140023b25`
- `USER32!PostMessageW` at `0x1400239bd`
- `USER32!PostMessageW` at `0x140023b25`
- `USER32!SetForegroundWindow` at `0x140023ac1`
- `USER32!SetForegroundWindow` at `0x140023ac1`
- `USER32!SetFocus` at `0x140023b59`
- `USER32!SetFocus` at `0x140023b59`

## pseudocode

```c
__int64 __fastcall CNovInterDlg::ProcessWindowMessage(
        CNovInterDlg *this,
        __int64 a2,
        unsigned __int64 a3,
        HWND a4,
        LPARAM a5,
        CNovInterDlg *a6,
        unsigned int a7)
{
  __int16 v7; // si
  __int64 inited; // rax
  unsigned int v11; // edx
  int v12; // eax
  unsigned __int16 v13; // dx
  unsigned __int16 v14; // r8
  HWND v15; // r9
  __int64 v16; // rax
  int v17; // edx
  __int64 v18; // r9
  unsigned int v19; // ecx
  __int64 v20; // rsi
  __int64 v21; // rsi
  HWND DlgItem; // rcx
  __int64 v23; // rcx
  HWND v24; // rax
  __int64 v25; // rsi
  int *v26; // [rsp+20h] [rbp-28h]
  int v27[6]; // [rsp+30h] [rbp-18h] BYREF

  v7 = (__int16)a4;
  if ( !a7 )
  {
    switch ( (_DWORD)a3 )
    {
      case 0x110:
        inited = CNovInterDlg::OnInitDialog(this);
LABEL_4:
        *(_QWORD *)a6 = inited;
        return 1;
      case 5:
        inited = CNovInterDlg::OnDialogResize(this, a2, (WPARAM)a4, a5);
        goto LABEL_4;
      case 0x24:
        inited = CNovInterDlg::OnMinMaxInfo(this, a2, a3, a5, v26);
        goto LABEL_4;
      case 0x10:
        v11 = 16;
LABEL_11:
        inited = CNovInterDlg::OnDialogDestroy(this, v11, a3, (__int64)a4, v26);
        goto LABEL_4;
    }
    v11 = 17;
    switch ( (_DWORD)a3 )
    {
      case 0x11:
        goto LABEL_11;
      case 0x4E:
        v12 = *(_DWORD *)(a5 + 16);
        if ( v12 == -530 )
        {
          CNovInterDlg::DisplayTooltip(this, a5);
        }
        else if ( ((v12 + 4) & 0xFFFFFFFD) == 0 && a4 == (HWND)1006 )
        {
          CNovInterDlg::ChangeFromPNRPToFile(this);
        }
        goto LABEL_24;
      case 0x312:
        if ( a4 == (HWND)41251 )
        {
          CSqmManager::RecordUIUsage(this, 0x1Bu);
          CNovInterDlg::OnButtonStopControl(this, v13, v14, v15, v26);
        }
        goto LABEL_24;
      case 0x53:
        goto LABEL_23;
      case 0x113:
        v16 = CNovInterDlg::OnTimer(this, 0x11u, a3, (__int64)a4, v26);
LABEL_28:
        *(_QWORD *)a6 = v16;
        return 1;
      case 0x120:
        a7 = 0;
        v17 = *((_DWORD *)_AtlModule + 222);
        if ( v17 <= 0 )
          goto LABEL_34;
        v18 = *((_QWORD *)_AtlModule + 110);
        v19 = 0;
        while ( *(_WORD *)(v18 + 6LL * v19 + 2) != v7 )
        {
          if ( (int)++v19 >= v17 )
            goto LABEL_34;
        }
        v21 = *(unsigned __int16 *)(v18 + 6LL * v19 + 4);
        if ( (_WORD)v21 )
        {
          IsToolbarButtonEnabled(*((HWND *)this + 9), v21, (int *)&a7);
          if ( a7 == 1 )
            PostMessageW(*((HWND *)this + 1), 0x111u, (unsigned int)v21, 0);
          v20 = v21 | 0x20000;
        }
        else
        {
LABEL_34:
          v20 = 0;
        }
        *(_QWORD *)a6 = v20;
        return 1;
      case 0x14:
        v16 = CNovInterDlg::OnEraseBackground(this, 0x11u, (unsigned __int64)a4, (__int64)a4, v26);
        goto LABEL_28;
      case 0x800C:
        v16 = CNovInterDlg::OnConnectionRequestAnswer(this, 0x11u, (unsigned __int64)a4, a5, v26);
        goto LABEL_28;
      case 0x800B:
        v16 = CNovInterDlg::OnControlRequestAnswer(this, 0x11u, (unsigned __int64)a4, (__int64)a4, v26);
        goto LABEL_28;
      case 0x800D:
        v16 = CNovInterDlg::OnBadPasswordReceived(this, 0x11u, a3, (__int64)a4, v26);
        goto LABEL_28;
      case 0x8013:
        v16 = CNovInterDlg::OnGoodPasswordReceived(this, 0x8013u, (unsigned __int64)a4, a5, v26);
        goto LABEL_28;
      case 0x800E:
        v16 = CNovInterDlg::OnLevelChangeRequest(this, 0x800Eu, (unsigned __int64)a4, a5, v26);
        goto LABEL_28;
      case 0x8019:
        v16 = CNovInterDlg::OnConnectionChanged(this, 0x800Eu, (unsigned __int64)a4, a5, v26);
        goto LABEL_28;
      case 0x801B:
        v16 = CNovInterDlg::OnSendContactInfo(this, 0x800Eu, (unsigned __int64)a4, a5, v26);
        goto LABEL_28;
      case 0x8080:
        if ( IsIconic(*((HWND *)this + 1)) )
          OpenIcon(*((HWND *)this + 1));
        SetForegroundWindow(*((HWND *)this + 1));
        FlashAndBeep(*((HWND *)this + 1));
        goto LABEL_24;
      case 0x138:
        v16 = CNovInterDlg::OnRequestColor(this, 0x800Eu, (unsigned __int64)a4, a5, v26);
        goto LABEL_28;
      case 6:
        if ( (unsigned __int16)((_WORD)a4 - 1) <= 1u || !(_DWORD)a4 )
        {
          PostMessageW(*((HWND *)this + 1), 5u, 0, 0);
          if ( v7 )
          {
            if ( *((_DWORD *)this + 28) == 1 )
              DlgItem = GetDlgItem(*((HWND *)this + 1), 1036);
            else
              DlgItem = (HWND)*((_QWORD *)this + 9);
            SetFocus(DlgItem);
          }
        }
        *(_QWORD *)a6 = 1;
        return 1;
      case 0x111:
        switch ( (_WORD)a4 )
        {
          case 0x109:
            v16 = CNovInterDlg::OnButtonStopControl(this, 0x800Eu, 0x111u, a4, v26);
            goto LABEL_28;
          case 0x121:
            a7 = 0;
            CSqmManager::RecordUIUsage(this, 0x121u);
            IsToolbarButtonEnabled(*((HWND *)this + 9), 289, (int *)&a7);
            if ( a7 )
            {
              v23 = *((_QWORD *)this + 13);
              *((_DWORD *)this + 22) = 2;
              (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v23 + 72LL))(v23, (char *)this + 92);
              SwapButton(*((HWND *)this + 9), 0xBB9u, 6u, 0x1F5u, 0x121u);
              CNovInterDlg::SetControlStatus(this, CTRL_LEVEL_NONE, *((void **)this + 13));
              *((_DWORD *)_AtlModule + 138) |= 0x40u;
            }
            goto LABEL_24;
          case 0xBB9:
            v16 = CNovInterDlg::OnButtonUnpauseConnection(this, 0x800Eu, 0x111u, a4, v26);
            goto LABEL_28;
          case 0xE2:
LABEL_23:
            ShowRAHelpText(*((HWND *)this + 9));
LABEL_24:
            *(_QWORD *)a6 = 0;
            return 1;
          case 0xE3:
            v16 = CNovInterDlg::OnButtonSettings((HWND *)this, 32782, a3, a4);
            goto LABEL_28;
          case 0xBBD:
            v16 = CNovInterDlg::OnButtonChat(this, 0x800Eu, 0x111u, a4, v26);
            goto LABEL_28;
          case 0xBBF:
            CSqmManager::RecordUIUsage(this, 0xBBFu);
            v24 = GetDlgItem(*((HWND *)this + 1), 1042);
            PWFieldCopyText(v24);
            goto LABEL_24;
          case 0x12B:
            v27[0] = 0;
            v25 = 0;
            a7 = 0;
            CSqmManager::RecordUIUsage(this, 0x12Bu);
            IsToolbarButtonEnabled(*((HWND *)this + 9), 299, (int *)&a7);
            if ( a7 )
            {
              QueryForTroubleshooting(*((HWND *)this + 1), v27);
              if ( v27[0] == 1 )
              {
                *((_DWORD *)_AtlModule + 251) = 2;
                v25 = CNovInterDlg::OnCloseDialog(this, 0x10u);
              }
            }
            *(_QWORD *)a6 = v25;
            return 1;
          case 0x40D:
            if ( !WORD1(a4) )
            {
LABEL_93:
              v16 = CNovInterDlg::OnSendChatButton(this, 0xBBFu, 0x111u, a4, v26);
              goto LABEL_28;
            }
            break;
          default:
            if ( (_DWORD)a4 == 1 )
              goto LABEL_93;
            break;
        }
        break;
      case 2:
        *(_QWORD *)a6 = 1;
        break;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140023830  push    rbp
0x140023832  push    rbx
0x140023833  push    rsi
0x140023834  push    rdi
0x140023835  push    r14
0x140023837  push    r15
0x140023839  mov     rbp, rsp
0x14002383c  sub     rsp, 48h
0x140023840  xor     r14d, r14d
0x140023843  mov     rsi, r9
0x140023846  mov     rdi, rcx
0x140023849  cmp     [rbp+arg_30], r14d
0x14002384d  jnz     loc_140023D53
0x140023853  cmp     r8d, 110h
0x14002385a  jnz     short loc_140023872
0x14002385c  call    ?OnInitDialog@CNovInterDlg@@QEAA_JI_K_JAEAH@Z; CNovInterDlg::OnInitDialog(uint,unsigned __int64,__int64,int &)
0x140023861  mov     rcx, [rbp+arg_28]; this
0x140023865  mov     [rcx], rax
0x140023868  mov     eax, 1
0x14002386d  jmp     loc_140023D55
0x140023872  cmp     r8d, 5
0x140023876  jnz     short loc_140023886
0x140023878  mov     r9, [rbp+arg_20]; __int64
0x14002387c  mov     r8, rsi; unsigned __int64
0x14002387f  call    ?OnDialogResize@CNovInterDlg@@QEAA_JI_K_JAEAH@Z; CNovInterDlg::OnDialogResize(uint,unsigned __int64,__int64,int &)
0x140023884  jmp     short loc_140023861
0x140023886  cmp     r8d, 24h ; '$'
0x14002388a  jnz     short loc_140023897
0x14002388c  mov     r9, [rbp+arg_20]; __int64
0x140023890  call    ?OnMinMaxInfo@CNovInterDlg@@QEAA_JI_K_JAEAH@Z; CNovInterDlg::OnMinMaxInfo(uint,unsigned __int64,__int64,int &)
0x140023895  jmp     short loc_140023861
0x140023897  cmp     r8d, 10h
0x14002389b  jnz     short loc_1400238A7
0x14002389d  mov     edx, r8d; unsigned int
0x1400238a0  call    ?OnDialogDestroy@CNovInterDlg@@QEAA_JI_K_JAEAH@Z; CNovInterDlg::OnDialogDestroy(uint,unsigned __int64,__int64,int &)
0x1400238a5  jmp     short loc_140023861
0x1400238a7  mov     edx, 11h; unsigned int
0x1400238ac  cmp     r8d, edx
0x1400238af  jz      short loc_1400238A0
0x1400238b1  lea     ebx, [rdx-10h]
0x1400238b4  cmp     r8d, 4Eh ; 'N'
0x1400238b8  jnz     short loc_1400238E9
0x1400238ba  mov     rdx, [rbp+arg_20]; __int64
0x1400238be  mov     eax, [rdx+10h]
0x1400238c1  cmp     eax, 0FFFFFDEEh
0x1400238c6  jz      short loc_1400238E2
0x1400238c8  add     eax, 4
0x1400238cb  test    eax, 0FFFFFFFDh
0x1400238d0  jnz     short loc_14002391E
0x1400238d2  cmp     rsi, 3EEh
0x1400238d9  jnz     short loc_14002391E
0x1400238db  call    ?ChangeFromPNRPToFile@CNovInterDlg@@AEAAJXZ; CNovInterDlg::ChangeFromPNRPToFile(void)
0x1400238e0  jmp     short loc_14002391E
0x1400238e2  call    ?DisplayTooltip@CNovInterDlg@@AEAAH_J@Z; CNovInterDlg::DisplayTooltip(__int64)
0x1400238e7  jmp     short loc_14002391E
0x1400238e9  cmp     r8d, 312h
0x1400238f0  jnz     short loc_14002390F
0x1400238f2  cmp     rsi, 0A123h
0x1400238f9  jnz     short loc_14002391E
0x1400238fb  mov     edx, 1Bh; unsigned int
0x140023900  call    ?RecordUIUsage@CSqmManager@@QEAAXK@Z; CSqmManager::RecordUIUsage(ulong)
0x140023905  mov     rcx, rdi; this
0x140023908  call    ?OnButtonStopControl@CNovInterDlg@@QEAA_JGGPEAUHWND__@@AEAH@Z; CNovInterDlg::OnButtonStopControl(ushort,ushort,HWND__ *,int &)
0x14002390d  jmp     short loc_14002391E
0x14002390f  cmp     r8d, 53h ; 'S'
0x140023913  jnz     short loc_14002392C
0x140023915  mov     rcx, [rcx+48h]; HWND
0x140023919  call    ?ShowRAHelpText@@YAXPEAUHWND__@@@Z; ShowRAHelpText(HWND__ *)
0x14002391e  mov     rax, [rbp+arg_28]
0x140023922  mov     [rax], r14
0x140023925  mov     eax, ebx
0x140023927  jmp     loc_140023D55
0x14002392c  cmp     r8d, 113h
0x140023933  jnz     short loc_140023943
0x140023935  call    ?OnTimer@CNovInterDlg@@QEAA_JI_K_JAEAH@Z; CNovInterDlg::OnTimer(uint,unsigned __int64,__int64,int &)
0x14002393a  mov     rcx, [rbp+arg_28]
0x14002393e  mov     [rcx], rax
0x140023941  jmp     short loc_140023925
0x140023943  cmp     r8d, 120h
0x14002394a  jnz     loc_1400239D0
0x140023950  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140023957  mov     [rbp+arg_30], r14d
0x14002395b  mov     edx, [rax+378h]
0x140023961  test    edx, edx
0x140023963  jle     short loc_140023983
0x140023965  mov     r9, [rax+370h]
0x14002396c  mov     ecx, r14d
0x14002396f  mov     eax, ecx
0x140023971  lea     r8, [rax+rax*2]
0x140023975  cmp     [r9+r8*2+2], si
0x14002397b  jz      short loc_14002398F
0x14002397d  add     ecx, ebx
0x14002397f  cmp     ecx, edx
0x140023981  jl      short loc_14002396F
0x140023983  mov     rsi, r14
0x140023986  mov     rax, [rbp+arg_28]
0x14002398a  mov     [rax], rsi
0x14002398d  jmp     short loc_140023925
0x14002398f  movzx   esi, word ptr [r9+r8*2+4]
0x140023995  test    si, si
0x140023998  jz      short loc_140023983
0x14002399a  mov     rcx, [rdi+48h]; HWND
0x14002399e  lea     r8, [rbp+arg_30]; int *
0x1400239a2  mov     edx, esi; int
0x1400239a4  call    ?IsToolbarButtonEnabled@@YAJPEAUHWND__@@HPEAH@Z; IsToolbarButtonEnabled(HWND__ *,int,int *)
0x1400239a9  cmp     [rbp+arg_30], ebx
0x1400239ac  jnz     short loc_1400239C9
0x1400239ae  mov     rcx, [rdi+8]; hWnd
0x1400239b2  xor     r9d, r9d; lParam
0x1400239b5  mov     r8d, esi; wParam
0x1400239b8  mov     edx, 111h; Msg
0x1400239bd  call    cs:__imp_PostMessageW
0x1400239c4  nop     dword ptr [rax+rax+00h]
0x1400239c9  bts     rsi, 11h
0x1400239ce  jmp     short loc_140023986
0x1400239d0  cmp     r8d, 14h
0x1400239d4  jnz     short loc_1400239E3
0x1400239d6  mov     r8, rsi; unsigned __int64
0x1400239d9  call    ?OnEraseBackground@CNovInterDlg@@QEAA_JI_K_JAEAH@Z; CNovInterDlg::OnEraseBackground(uint,unsigned __int64,__int64,int &)
0x1400239de  jmp     loc_14002393A
0x1400239e3  cmp     r8d, 800Ch
0x1400239ea  jnz     short loc_1400239FD
0x1400239ec  mov     r9, [rbp+arg_20]; __int64
0x1400239f0  mov     r8, rsi; unsigned __int64
0x1400239f3  call    ?OnConnectionRequestAnswer@CNovInterDlg@@QEAA_JI_K_JAEAH@Z; CNovInterDlg::OnConnectionRequestAnswer(uint,unsigned __int64,__int64,int &)
0x1400239f8  jmp     loc_14002393A
0x1400239fd  cmp     r8d, 800Bh
0x140023a04  jnz     short loc_140023A13
0x140023a06  mov     r8, rsi; unsigned __int64
0x140023a09  call    ?OnControlRequestAnswer@CNovInterDlg@@QEAA_JI_K_JAEAH@Z; CNovInterDlg::OnControlRequestAnswer(uint,unsigned __int64,__int64,int &)
0x140023a0e  jmp     loc_14002393A
0x140023a13  cmp     r8d, 800Dh
0x140023a1a  jnz     short loc_140023A26
0x140023a1c  call    ?OnBadPasswordReceived@CNovInterDlg@@QEAA_JI_K_JAEAH@Z; CNovInterDlg::OnBadPasswordReceived(uint,unsigned __int64,__int64,int &)
0x140023a21  jmp     loc_14002393A
0x140023a26  mov     edx, 8013h; unsigned int
0x140023a2b  cmp     r8d, edx
0x140023a2e  jnz     short loc_140023A41
0x140023a30  mov     r9, [rbp+arg_20]; __int64
0x140023a34  mov     r8, rsi; unsigned __int64
0x140023a37  call    ?OnGoodPasswordReceived@CNovInterDlg@@QEAA_JI_K_JAEAH@Z; CNovInterDlg::OnGoodPasswordReceived(uint,unsigned __int64,__int64,int &)
0x140023a3c  jmp     loc_14002393A
0x140023a41  mov     edx, 800Eh; unsigned __int16
0x140023a46  cmp     r8d, edx
0x140023a49  jnz     short loc_140023A5C
0x140023a4b  mov     r9, [rbp+arg_20]; __int64
0x140023a4f  mov     r8, rsi; unsigned __int64
0x140023a52  call    ?OnLevelChangeRequest@CNovInterDlg@@QEAA_JI_K_JAEAH@Z; CNovInterDlg::OnLevelChangeRequest(uint,unsigned __int64,__int64,int &)
0x140023a57  jmp     loc_14002393A
0x140023a5c  cmp     r8d, 8019h
0x140023a63  jnz     short loc_140023A76
0x140023a65  mov     r9, [rbp+arg_20]; __int64
0x140023a69  mov     r8, rsi; unsigned __int64
0x140023a6c  call    ?OnConnectionChanged@CNovInterDlg@@QEAA_JI_K_JAEAH@Z; CNovInterDlg::OnConnectionChanged(uint,unsigned __int64,__int64,int &)
0x140023a71  jmp     loc_14002393A
0x140023a76  cmp     r8d, 801Bh
0x140023a7d  jnz     short loc_140023A90
0x140023a7f  mov     r9, [rbp+arg_20]; __int64
0x140023a83  mov     r8, rsi; unsigned __int64
0x140023a86  call    ?OnSendContactInfo@CNovInterDlg@@QEAA_JI_K_JAEAH@Z; CNovInterDlg::OnSendContactInfo(uint,unsigned __int64,__int64,int &)
0x140023a8b  jmp     loc_14002393A
0x140023a90  cmp     r8d, 8080h
0x140023a97  jnz     short loc_140023ADB
0x140023a99  mov     rcx, [rcx+8]; hWnd
0x140023a9d  call    cs:__imp_IsIconic
0x140023aa4  nop     dword ptr [rax+rax+00h]
0x140023aa9  test    eax, eax
0x140023aab  jz      short loc_140023ABD
0x140023aad  mov     rcx, [rdi+8]; hWnd
0x140023ab1  call    cs:__imp_OpenIcon
0x140023ab8  nop     dword ptr [rax+rax+00h]
0x140023abd  mov     rcx, [rdi+8]; hWnd
0x140023ac1  call    cs:__imp_SetForegroundWindow
0x140023ac8  nop     dword ptr [rax+rax+00h]
0x140023acd  mov     rcx, [rdi+8]; HWND
0x140023ad1  call    ?FlashAndBeep@@YAXPEAUHWND__@@@Z; FlashAndBeep(HWND__ *)
0x140023ad6  jmp     loc_14002391E
0x140023adb  cmp     r8d, 138h
0x140023ae2  jnz     short loc_140023AF5
0x140023ae4  mov     r9, [rbp+arg_20]; __int64
0x140023ae8  mov     r8, rsi; unsigned __int64
0x140023aeb  call    ?OnRequestColor@CNovInterDlg@@QEAA_JI_K_JAEAH@Z; CNovInterDlg::OnRequestColor(uint,unsigned __int64,__int64,int &)
0x140023af0  jmp     loc_14002393A
0x140023af5  cmp     r8d, 6
0x140023af9  jnz     short loc_140023B71
0x140023afb  movzx   eax, si
0x140023afe  sub     ax, bx
0x140023b01  cmp     ax, bx
0x140023b04  jbe     short loc_140023B17
0x140023b06  test    si, si
0x140023b09  jnz     short loc_140023B65
0x140023b0b  mov     rax, rsi
0x140023b0e  shr     rax, 10h
0x140023b12  test    ax, ax
0x140023b15  jnz     short loc_140023B65
0x140023b17  mov     rcx, [rcx+8]; hWnd
0x140023b1b  xor     r9d, r9d; lParam
0x140023b1e  xor     r8d, r8d; wParam
0x140023b21  lea     edx, [r9+5]; Msg
0x140023b25  call    cs:__imp_PostMessageW
0x140023b2c  nop     dword ptr [rax+rax+00h]
0x140023b31  test    si, si
0x140023b34  jz      short loc_140023B65
0x140023b36  cmp     [rdi+70h], ebx
0x140023b39  jnz     short loc_140023B55
0x140023b3b  mov     rcx, [rdi+8]; hDlg
0x140023b3f  mov     edx, 40Ch; nIDDlgItem
0x140023b44  call    cs:__imp_GetDlgItem
0x140023b4b  nop     dword ptr [rax+rax+00h]
0x140023b50  mov     rcx, rax
0x140023b53  jmp     short loc_140023B59
0x140023b55  mov     rcx, [rdi+48h]; hWnd
0x140023b59  call    cs:__imp_SetFocus
0x140023b60  nop     dword ptr [rax+rax+00h]
0x140023b65  mov     rax, [rbp+arg_28]
0x140023b69  mov     [rax], rbx
0x140023b6c  jmp     loc_140023925
0x140023b71  cmp     r8d, 111h
0x140023b78  jnz     loc_140023D46
0x140023b7e  lea     eax, [r8-8]
0x140023b82  cmp     ax, si
0x140023b85  jnz     short loc_140023B91
0x140023b87  call    ?OnButtonStopControl@CNovInterDlg@@QEAA_JGGPEAUHWND__@@AEAH@Z; CNovInterDlg::OnButtonStopControl(ushort,ushort,HWND__ *,int &)
0x140023b8c  jmp     loc_14002393A
0x140023b91  mov     r15d, 121h
0x140023b97  cmp     r15w, si
0x140023b9b  jnz     loc_140023C22
0x140023ba1  mov     edx, r15d; unsigned int
0x140023ba4  mov     [rbp+arg_30], r14d
0x140023ba8  call    ?RecordUIUsage@CSqmManager@@QEAAXK@Z; CSqmManager::RecordUIUsage(ulong)
0x140023bad  mov     rcx, [rdi+48h]; HWND
0x140023bb1  lea     r8, [rbp+arg_30]; int *
0x140023bb5  mov     edx, r15d; int
0x140023bb8  call    ?IsToolbarButtonEnabled@@YAJPEAUHWND__@@HPEAH@Z; IsToolbarButtonEnabled(HWND__ *,int,int *)
0x140023bbd  cmp     [rbp+arg_30], r14d
0x140023bc1  jz      loc_14002391E
0x140023bc7  mov     rcx, [rdi+68h]
0x140023bcb  lea     rdx, [rdi+5Ch]
0x140023bcf  mov     dword ptr [rdi+58h], 2
0x140023bd6  mov     rax, [rcx]
0x140023bd9  mov     rax, [rax+48h]
0x140023bdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023be2  mov     rcx, [rdi+48h]; hWnd
0x140023be6  mov     edx, 0BB9h; unsigned int
0x140023beb  mov     r9d, 1F5h; unsigned int
0x140023bf1  mov     [rsp+48h+var_28], r15d; unsigned int
0x140023bf6  mov     r8d, 6; unsigned int
0x140023bfc  call    ?SwapButton@@YAJPEAUHWND__@@IIII@Z; SwapButton(HWND__ *,uint,uint,uint,uint)
0x140023c01  mov     r8, [rdi+68h]; void *
0x140023c05  mov     edx, ebx; enum __MIDL___MIDL_itf_rdpencomapi_0000_0000_0001
0x140023c07  mov     rcx, rdi; this
0x140023c0a  call    ?SetControlStatus@CNovInterDlg@@QEAAXW4__MIDL___MIDL_itf_rdpencomapi_0000_0000_0001@@PEAX@Z; CNovInterDlg::SetControlStatus(__MIDL___MIDL_itf_rdpencomapi_0000_0000_0001,void *)
0x140023c0f  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140023c16  or      dword ptr [rax+228h], 40h
0x140023c1d  jmp     loc_14002391E
0x140023c22  mov     eax, 0BB9h
0x140023c27  cmp     ax, si
0x140023c2a  jnz     short loc_140023C36
0x140023c2c  call    ?OnButtonUnpauseConnection@CNovInterDlg@@QEAA_JGGPEAUHWND__@@AEAH@Z; CNovInterDlg::OnButtonUnpauseConnection(ushort,ushort,HWND__ *,int &)
0x140023c31  jmp     loc_14002393A
0x140023c36  mov     eax, 0E2h
0x140023c3b  cmp     ax, si
0x140023c3e  jz      loc_140023915
0x140023c44  mov     eax, 0E3h
0x140023c49  cmp     ax, si
0x140023c4c  jnz     short loc_140023C58
0x140023c4e  call    ?OnButtonSettings@CNovInterDlg@@QEAA_JGGPEAUHWND__@@AEAH@Z; CNovInterDlg::OnButtonSettings(ushort,ushort,HWND__ *,int &)
0x140023c53  jmp     loc_14002393A
0x140023c58  mov     eax, 0BBDh
0x140023c5d  cmp     ax, si
0x140023c60  jnz     short loc_140023C6C
0x140023c62  call    ?OnButtonChat@CNovInterDlg@@QEAA_JGGPEAUHWND__@@AEAH@Z; CNovInterDlg::OnButtonChat(ushort,ushort,HWND__ *,int &)
0x140023c67  jmp     loc_14002393A
0x140023c6c  mov     edx, 0BBFh; unsigned __int16
0x140023c71  cmp     dx, si
0x140023c74  jnz     short loc_140023C9D
0x140023c76  call    ?RecordUIUsage@CSqmManager@@QEAAXK@Z; CSqmManager::RecordUIUsage(ulong)
0x140023c7b  mov     rcx, [rdi+8]; hDlg
0x140023c7f  mov     edx, 412h; nIDDlgItem
0x140023c84  call    cs:__imp_GetDlgItem
0x140023c8b  nop     dword ptr [rax+rax+00h]
0x140023c90  mov     rcx, rax; hWndNewOwner
0x140023c93  call    ?PWFieldCopyText@@YAJPEAUHWND__@@@Z; PWFieldCopyText(HWND__ *)
0x140023c98  jmp     loc_14002391E
0x140023c9d  mov     r15d, 12Bh
0x140023ca3  cmp     r15w, si
0x140023ca7  jnz     short loc_140023D11
0x140023ca9  mov     edx, r15d; unsigned int
0x140023cac  mov     [rbp+var_18], r14d
0x140023cb0  mov     rsi, r14
0x140023cb3  mov     [rbp+arg_30], r14d
0x140023cb7  call    ?RecordUIUsage@CSqmManager@@QEAAXK@Z; CSqmManager::RecordUIUsage(ulong)
0x140023cbc  mov     rcx, [rdi+48h]; HWND
0x140023cc0  lea     r8, [rbp+arg_30]; int *
0x140023cc4  mov     edx, r15d; int
0x140023cc7  call    ?IsToolbarButtonEnabled@@YAJPEAUHWND__@@HPEAH@Z; IsToolbarButtonEnabled(HWND__ *,int,int *)
0x140023ccc  cmp     [rbp+arg_30], r14d
0x140023cd0  jz      short loc_140023D05
0x140023cd2  mov     rcx, [rdi+8]; HWND
0x140023cd6  lea     rdx, [rbp+var_18]; int *
  ... truncated ...
```
