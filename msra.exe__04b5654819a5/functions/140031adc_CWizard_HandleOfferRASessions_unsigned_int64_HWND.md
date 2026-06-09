# CWizard::HandleOfferRASessions(unsigned __int64,HWND__ *)

- ea: `0x140031adc`
- end: `0x140031e84`
- name: `?HandleOfferRASessions@CWizard@@QEAAJ_KPEAUHWND__@@@Z`
- size: `936`
- prototype: `__int64 __fastcall(CWizard *__hidden this, unsigned int, HWND)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140034200`

## callees

- `0x14002c0a4`
- `0x1400313e4`
- `0x14003175c`
- `0x140031adc`
- `0x140033d68`
- `0x140034ce4`

## import_xrefs

- `USER32!SendMessageW` at `0x140031bb2`
- `USER32!SendMessageW` at `0x140031c5e`
- `USER32!SendMessageW` at `0x140031c9c`
- `USER32!SendMessageW` at `0x140031cff`
- `USER32!SendMessageW` at `0x140031d73`
- `USER32!SendMessageW` at `0x140031e68`
- `USER32!SendMessageW` at `0x140031bb2`
- `USER32!SendMessageW` at `0x140031c5e`
- `USER32!SendMessageW` at `0x140031c9c`
- `USER32!SendMessageW` at `0x140031cff`
- `USER32!SendMessageW` at `0x140031d73`
- `USER32!SendMessageW` at `0x140031e68`
- `USER32!ShowWindow` at `0x140031da4`
- `USER32!ShowWindow` at `0x140031dce`
- `USER32!ShowWindow` at `0x140031df3`
- `USER32!ShowWindow` at `0x140031e1b`
- `USER32!ShowWindow` at `0x140031da4`
- `USER32!ShowWindow` at `0x140031dce`
- `USER32!ShowWindow` at `0x140031df3`
- `USER32!ShowWindow` at `0x140031e1b`
- `USER32!GetDlgItem` at `0x140031b95`
- `USER32!GetDlgItem` at `0x140031d93`
- `USER32!GetDlgItem` at `0x140031db8`
- `USER32!GetDlgItem` at `0x140031de2`
- `USER32!GetDlgItem` at `0x140031e07`
- `USER32!GetDlgItem` at `0x140031b95`
- `USER32!GetDlgItem` at `0x140031d93`
- `USER32!GetDlgItem` at `0x140031db8`
- `USER32!GetDlgItem` at `0x140031de2`
- `USER32!GetDlgItem` at `0x140031e07`
- `USER32!EnableWindow` at `0x140031e2d`
- `USER32!EnableWindow` at `0x140031e2d`
- `USER32!SetFocus` at `0x140031e3c`
- `USER32!SetFocus` at `0x140031e3c`
- `USER32!GetParent` at `0x140031e4e`
- `USER32!GetParent` at `0x140031e4e`
- `msvcrt!_wcsicmp` at `0x140031c10`
- `msvcrt!_wcsicmp` at `0x140031c10`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140031cb6`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140031cb6`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x140031bd1`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x140031bd1`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140031c82`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140031c82`

## pseudocode

```c
__int64 __fastcall CWizard::HandleOfferRASessions(CWizard *this, signed int a2, HWND a3)
{
  unsigned int v6; // ecx
  unsigned __int16 v7; // dx
  CEventLogger *v8; // rcx
  HWND DlgItem; // rsi
  CEventLogger *v10; // rdx
  int v11; // ebx
  const wchar_t *v12; // rcx
  int v13; // r14d
  int i; // ebx
  LPARAM v15; // r9
  CEventLogger *v16; // rax
  bool v17; // zf
  CWizard *v18; // rcx
  LPARAM v19; // rbx
  HWND v20; // rax
  HWND v21; // rax
  HWND v22; // rax
  HWND v23; // rbx
  HWND Parent; // rax
  void *ppvData; // [rsp+78h] [rbp+10h] BYREF

  ppvData = 0;
  if ( a2 >= 0 && *((_DWORD *)_AtlModule + 250) )
    goto LABEL_7;
  v6 = 572;
  v7 = 656 - (a2 != -2147023174);
  if ( a2 != -2147023174 )
    v6 = 540;
  ShowErrorMessage(v6, v7, a3, 0, (unsigned __int16 *)0xFFFE, 0);
  CWizard::SetCurrentPage(this, 0x7DBu);
  if ( a2 >= 0 )
  {
LABEL_7:
    DlgItem = GetDlgItem(a3, 1054);
    SendMessageW(DlgItem, 0x14Bu, 0, 0);
    SafeArrayAccessData(*((SAFEARRAY **)_AtlModule + 124), &ppvData);
    v10 = _AtlModule;
    if ( *((_QWORD *)_AtlModule + 80) )
    {
      v11 = 0;
      if ( *((int *)_AtlModule + 250) > 0 )
      {
        do
        {
          v12 = (const wchar_t *)*((_QWORD *)ppvData + v11);
          if ( v12 )
          {
            if ( !_wcsicmp(v12, *((const wchar_t **)v10 + 80)) )
            {
              v13 = 1;
              SendMessageW(DlgItem, 0x143u, 0, *((_QWORD *)ppvData + v11));
              v10 = _AtlModule;
              goto LABEL_17;
            }
            v10 = _AtlModule;
          }
          ++v11;
        }
        while ( v11 < *((_DWORD *)v10 + 250) );
      }
    }
    v13 = 0;
    for ( i = 0; i < *((_DWORD *)v10 + 250); ++i )
    {
      v15 = *((_QWORD *)ppvData + i);
      if ( v15 )
      {
        SendMessageW(DlgItem, 0x143u, 0, v15);
        v10 = _AtlModule;
      }
    }
LABEL_17:
    SafeArrayUnaccessData(*((SAFEARRAY **)v10 + 124));
    SendMessageW(DlgItem, 0x14Eu, 0, 0);
    SafeArrayDestroy(*((SAFEARRAY **)_AtlModule + 124));
    v16 = _AtlModule;
    v17 = *((_QWORD *)_AtlModule + 80) == 0;
    *((_QWORD *)_AtlModule + 124) = 0;
    *((_DWORD *)v16 + 250) = 0;
    if ( (v17 || v13) && SendMessageW(DlgItem, 0x146u, 0, 0) == 1 )
    {
      if ( CWizard::GetOfferRATicketString(v18, a3) < 0 )
      {
        ShowErrorMessage(0x213u, 0x28Au, a3, 0, (unsigned __int16 *)0xFFFE, 0);
        CWizard::CloseDownWizard(this, 0xFFFFFFFFLL, 0);
      }
      v19 = 16;
    }
    else
    {
      v20 = GetDlgItem(a3, 1055);
      ShowWindow(v20, 0);
      v21 = GetDlgItem(a3, 1056);
      ShowWindow(v21, 5);
      v22 = GetDlgItem(a3, 1079);
      ShowWindow(v22, 0);
      v23 = GetDlgItem(a3, 1054);
      ShowWindow(v23, 5);
      EnableWindow(v23, 1);
      SetFocus(v23);
      v19 = 18;
    }
    Parent = GetParent(a3);
    SendMessageW(Parent, 0x470u, 0, v19);
  }
  else
  {
    CEventLogger::LogError(
      v8,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\wizard.cpp",
      0x799u,
      L"CWizard::HandleOfferRASessions",
      a2);
  }
  return 0;
}

```

## disassembly

```asm
0x140031adc  push    rbx
0x140031ade  push    rbp
0x140031adf  push    rsi
0x140031ae0  push    rdi
0x140031ae1  push    r14
0x140031ae3  push    r15
0x140031ae5  sub     rsp, 38h
0x140031ae9  mov     [rsp+68h+ppvData], 0
0x140031af2  mov     rdi, r8
0x140031af5  mov     rbx, rdx
0x140031af8  mov     r15, rcx
0x140031afb  test    edx, edx
0x140031afd  js      short loc_140031B0F
0x140031aff  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140031b06  cmp     dword ptr [rax+3E8h], 0
0x140031b0d  jnz     short loc_140031B8D
0x140031b0f  mov     r8d, 800706BAh
0x140031b15  mov     [rsp+68h+var_40], 0; int
0x140031b1d  mov     ecx, 23Ch
0x140031b22  mov     [rsp+68h+var_48], 0FFFEh; unsigned __int16 *
0x140031b2b  mov     eax, ebx
0x140031b2d  sub     eax, r8d
0x140031b30  neg     eax
0x140031b32  lea     eax, [rcx-20h]
0x140031b35  sbb     edx, edx
0x140031b37  add     edx, 290h; int
0x140031b3d  cmp     ebx, r8d
0x140031b40  mov     r8, rdi; HWND
0x140031b43  cmovnz  ecx, eax; int
0x140031b46  xor     r9d, r9d; int
0x140031b49  call    ?ShowErrorMessage@@YAJHHPEAUHWND__@@JPEBGH@Z; ShowErrorMessage(int,int,HWND__ *,long,ushort const *,int)
0x140031b4e  mov     edx, 7DBh; unsigned int
0x140031b53  mov     rcx, r15; this
0x140031b56  call    ?SetCurrentPage@CWizard@@QEAAXI@Z; CWizard::SetCurrentPage(uint)
0x140031b5b  test    ebx, ebx
0x140031b5d  jns     short loc_140031B8D
0x140031b5f  lea     rax, aCwizardHandleo; "CWizard::HandleOfferRASessions"
0x140031b66  mov     [rsp+68h+var_40], ebx; unsigned int
0x140031b6a  mov     r9d, 799h; unsigned int
0x140031b70  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x140031b75  lea     r8, aBaseDiagnosisR_12; "base\\diagnosis\\ra\\ui\\wizard.cpp"
0x140031b7c  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140031b83  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140031b88  jmp     loc_140031E74
0x140031b8d  mov     edx, 41Eh; nIDDlgItem
0x140031b92  mov     rcx, rdi; hDlg
0x140031b95  call    cs:__imp_GetDlgItem
0x140031b9c  nop     dword ptr [rax+rax+00h]
0x140031ba1  xor     r9d, r9d; lParam
0x140031ba4  xor     r8d, r8d; wParam
0x140031ba7  mov     rcx, rax; hWnd
0x140031baa  mov     edx, 14Bh; Msg
0x140031baf  mov     rsi, rax
0x140031bb2  call    cs:__imp_SendMessageW
0x140031bb9  nop     dword ptr [rax+rax+00h]
0x140031bbe  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140031bc5  lea     rdx, [rsp+68h+ppvData]; ppvData
0x140031bca  mov     rcx, [rcx+3E0h]; psa
0x140031bd1  call    cs:__imp_SafeArrayAccessData
0x140031bd8  nop     dword ptr [rax+rax+00h]
0x140031bdd  mov     rdx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140031be4  cmp     qword ptr [rdx+280h], 0
0x140031bec  jz      short loc_140031C35
0x140031bee  xor     ebx, ebx
0x140031bf0  cmp     [rdx+3E8h], ebx
0x140031bf6  jle     short loc_140031C35
0x140031bf8  mov     rax, [rsp+68h+ppvData]
0x140031bfd  movsxd  rbp, ebx
0x140031c00  mov     rcx, [rax+rbp*8]; String1
0x140031c04  test    rcx, rcx
0x140031c07  jz      short loc_140031C2B
0x140031c09  mov     rdx, [rdx+280h]; String2
0x140031c10  call    cs:__imp__wcsicmp
0x140031c17  nop     dword ptr [rax+rax+00h]
0x140031c1c  test    eax, eax
0x140031c1e  jz      loc_140031D59
0x140031c24  mov     rdx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140031c2b  inc     ebx
0x140031c2d  cmp     ebx, [rdx+3E8h]
0x140031c33  jl      short loc_140031BF8
0x140031c35  xor     r14d, r14d
0x140031c38  xor     ebx, ebx
0x140031c3a  cmp     [rdx+3E8h], ebx
0x140031c40  jle     short loc_140031C7B
0x140031c42  mov     rax, [rsp+68h+ppvData]
0x140031c47  movsxd  rcx, ebx
0x140031c4a  mov     r9, [rax+rcx*8]; lParam
0x140031c4e  test    r9, r9
0x140031c51  jz      short loc_140031C71
0x140031c53  xor     r8d, r8d; wParam
0x140031c56  mov     edx, 143h; Msg
0x140031c5b  mov     rcx, rsi; hWnd
0x140031c5e  call    cs:__imp_SendMessageW
0x140031c65  nop     dword ptr [rax+rax+00h]
0x140031c6a  mov     rdx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140031c71  inc     ebx
0x140031c73  cmp     ebx, [rdx+3E8h]
0x140031c79  jl      short loc_140031C42
0x140031c7b  mov     rcx, [rdx+3E0h]; psa
0x140031c82  call    cs:__imp_SafeArrayUnaccessData
0x140031c89  nop     dword ptr [rax+rax+00h]
0x140031c8e  xor     r9d, r9d; lParam
0x140031c91  xor     r8d, r8d; wParam
0x140031c94  mov     edx, 14Eh; Msg
0x140031c99  mov     rcx, rsi; hWnd
0x140031c9c  call    cs:__imp_SendMessageW
0x140031ca3  nop     dword ptr [rax+rax+00h]
0x140031ca8  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140031caf  mov     rcx, [rcx+3E0h]; psa
0x140031cb6  call    cs:__imp_SafeArrayDestroy
0x140031cbd  nop     dword ptr [rax+rax+00h]
0x140031cc2  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140031cc9  cmp     qword ptr [rax+280h], 0
0x140031cd1  mov     qword ptr [rax+3E0h], 0
0x140031cdc  mov     dword ptr [rax+3E8h], 0
0x140031ce6  jz      short loc_140031CF1
0x140031ce8  test    r14d, r14d
0x140031ceb  jz      loc_140031D8B
0x140031cf1  xor     r9d, r9d; lParam
0x140031cf4  xor     r8d, r8d; wParam
0x140031cf7  mov     edx, 146h; Msg
0x140031cfc  mov     rcx, rsi; hWnd
0x140031cff  call    cs:__imp_SendMessageW
0x140031d06  nop     dword ptr [rax+rax+00h]
0x140031d0b  cmp     rax, 1
0x140031d0f  jnz     short loc_140031D8B
0x140031d11  mov     rdx, rdi; HWND
0x140031d14  call    ?GetOfferRATicketString@CWizard@@AEAAJPEAUHWND__@@@Z; CWizard::GetOfferRATicketString(HWND__ *)
0x140031d19  test    eax, eax
0x140031d1b  jns     short loc_140031D4F
0x140031d1d  mov     edx, 28Ah; int
0x140031d22  mov     [rsp+68h+var_40], 0; int
0x140031d2a  xor     r9d, r9d; int
0x140031d2d  mov     [rsp+68h+var_48], 0FFFEh; unsigned __int16 *
0x140031d36  mov     r8, rdi; HWND
0x140031d39  lea     ecx, [rdx-77h]; int
0x140031d3c  call    ?ShowErrorMessage@@YAJHHPEAUHWND__@@JPEBGH@Z; ShowErrorMessage(int,int,HWND__ *,long,ushort const *,int)
0x140031d41  xor     r8d, r8d
0x140031d44  or      edx, 0FFFFFFFFh
0x140031d47  mov     rcx, r15
0x140031d4a  call    ?CloseDownWizard@CWizard@@AEAAXIW4_RATYPE@@@Z; CWizard::CloseDownWizard(uint,_RATYPE)
0x140031d4f  mov     ebx, 10h
0x140031d54  jmp     loc_140031E4B
0x140031d59  mov     r9, [rsp+68h+ppvData]
0x140031d5e  xor     r8d, r8d; wParam
0x140031d61  mov     edx, 143h; Msg
0x140031d66  mov     rcx, rsi; hWnd
0x140031d69  mov     r14d, 1
0x140031d6f  mov     r9, [r9+rbp*8]; lParam
0x140031d73  call    cs:__imp_SendMessageW
0x140031d7a  nop     dword ptr [rax+rax+00h]
0x140031d7f  mov     rdx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140031d86  jmp     loc_140031C7B
0x140031d8b  mov     edx, 41Fh; nIDDlgItem
0x140031d90  mov     rcx, rdi; hDlg
0x140031d93  call    cs:__imp_GetDlgItem
0x140031d9a  nop     dword ptr [rax+rax+00h]
0x140031d9f  mov     rcx, rax; hWnd
0x140031da2  xor     edx, edx; nCmdShow
0x140031da4  call    cs:__imp_ShowWindow
0x140031dab  nop     dword ptr [rax+rax+00h]
0x140031db0  mov     edx, 420h; nIDDlgItem
0x140031db5  mov     rcx, rdi; hDlg
0x140031db8  call    cs:__imp_GetDlgItem
0x140031dbf  nop     dword ptr [rax+rax+00h]
0x140031dc4  mov     esi, 5
0x140031dc9  mov     rcx, rax; hWnd
0x140031dcc  mov     edx, esi; nCmdShow
0x140031dce  call    cs:__imp_ShowWindow
0x140031dd5  nop     dword ptr [rax+rax+00h]
0x140031dda  mov     edx, 437h; nIDDlgItem
0x140031ddf  mov     rcx, rdi; hDlg
0x140031de2  call    cs:__imp_GetDlgItem
0x140031de9  nop     dword ptr [rax+rax+00h]
0x140031dee  mov     rcx, rax; hWnd
0x140031df1  xor     edx, edx; nCmdShow
0x140031df3  call    cs:__imp_ShowWindow
0x140031dfa  nop     dword ptr [rax+rax+00h]
0x140031dff  mov     edx, 41Eh; nIDDlgItem
0x140031e04  mov     rcx, rdi; hDlg
0x140031e07  call    cs:__imp_GetDlgItem
0x140031e0e  nop     dword ptr [rax+rax+00h]
0x140031e13  mov     rcx, rax; hWnd
0x140031e16  mov     edx, esi; nCmdShow
0x140031e18  mov     rbx, rax
0x140031e1b  call    cs:__imp_ShowWindow
0x140031e22  nop     dword ptr [rax+rax+00h]
0x140031e27  lea     edx, [rsi-4]; bEnable
0x140031e2a  mov     rcx, rbx; hWnd
0x140031e2d  call    cs:__imp_EnableWindow
0x140031e34  nop     dword ptr [rax+rax+00h]
0x140031e39  mov     rcx, rbx; hWnd
0x140031e3c  call    cs:__imp_SetFocus
0x140031e43  nop     dword ptr [rax+rax+00h]
0x140031e48  lea     ebx, [rsi+0Dh]
0x140031e4b  mov     rcx, rdi; hWnd
0x140031e4e  call    cs:__imp_GetParent
0x140031e55  nop     dword ptr [rax+rax+00h]
0x140031e5a  mov     r9, rbx; lParam
0x140031e5d  xor     r8d, r8d; wParam
0x140031e60  mov     rcx, rax; hWnd
0x140031e63  mov     edx, 470h; Msg
0x140031e68  call    cs:__imp_SendMessageW
0x140031e6f  nop     dword ptr [rax+rax+00h]
0x140031e74  xor     eax, eax
0x140031e76  add     rsp, 38h
0x140031e7a  pop     r15
0x140031e7c  pop     r14
0x140031e7e  pop     rdi
0x140031e7f  pop     rsi
0x140031e80  pop     rbp
0x140031e81  pop     rbx
0x140031e82  retn
```
