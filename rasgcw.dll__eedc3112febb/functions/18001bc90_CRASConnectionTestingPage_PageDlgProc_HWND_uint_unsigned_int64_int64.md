# CRASConnectionTestingPage::PageDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18001bc90`
- end: `0x18001bf75`
- name: `?PageDlgProc@CRASConnectionTestingPage@@KAHPEAUHWND__@@I_K_J@Z`
- size: `741`
- prototype: `__int64 __fastcall(HWND hWnd, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18001ae18`
- `0x18001ba94`
- `0x18001bc90`
- `0x18001c074`
- `0x18002b970`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001bf23`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001bf23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bf4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bf4c`
- `USER32!SetWindowLongPtrW` at `0x18001bec1`
- `USER32!SetWindowLongPtrW` at `0x18001bec1`
- `USER32!PostMessageW` at `0x18001bdab`
- `USER32!PostMessageW` at `0x18001be70`
- `USER32!PostMessageW` at `0x18001bdab`
- `USER32!PostMessageW` at `0x18001be70`
- `USER32!GetPropW` at `0x18001bd36`
- `USER32!GetPropW` at `0x18001bd36`
- `USER32!RemovePropW` at `0x18001bd2e`
- `USER32!RemovePropW` at `0x18001bd2e`
- `USER32!ShowWindow` at `0x18001bcf1`
- `USER32!ShowWindow` at `0x18001bcf1`
- `USER32!SetPropW` at `0x18001bcc9`
- `USER32!SetPropW` at `0x18001bcc9`
- `USER32!GetDlgItem` at `0x18001bce6`
- `USER32!GetDlgItem` at `0x18001bd00`
- `USER32!GetDlgItem` at `0x18001bd13`
- `USER32!GetDlgItem` at `0x18001bce6`
- `USER32!GetDlgItem` at `0x18001bd00`
- `USER32!GetDlgItem` at `0x18001bd13`
- `USER32!SendMessageW` at `0x18001bdeb`
- `USER32!SendMessageW` at `0x18001be26`
- `USER32!SendMessageW` at `0x18001bdeb`
- `USER32!SendMessageW` at `0x18001be26`
- `USER32!GetParent` at `0x18001bd96`
- `USER32!GetParent` at `0x18001bdd7`
- `USER32!GetParent` at `0x18001be12`
- `USER32!GetParent` at `0x18001be35`
- `USER32!GetParent` at `0x18001be3e`
- `USER32!GetParent` at `0x18001be5b`
- `USER32!GetParent` at `0x18001bd96`
- `USER32!GetParent` at `0x18001bdd7`
- `USER32!GetParent` at `0x18001be12`
- `USER32!GetParent` at `0x18001be35`
- `USER32!GetParent` at `0x18001be3e`
- `USER32!GetParent` at `0x18001be5b`
- `rtutils!TracePrintfExA` at `0x18001bd8c`
- `rtutils!TracePrintfExA` at `0x18001be8b`
- `rtutils!TracePrintfExA` at `0x18001bf14`
- `rtutils!TracePrintfExA` at `0x18001bf3f`
- `rtutils!TracePrintfExA` at `0x18001bd8c`
- `rtutils!TracePrintfExA` at `0x18001be8b`
- `rtutils!TracePrintfExA` at `0x18001bf14`
- `rtutils!TracePrintfExA` at `0x18001bf3f`

## string_xrefs

- `0x18001bf08`: `RAS:CRASConnectionTestingPage::PageDlgProc: Waiting for connect thread to finish execution.`
- `0x18001bf33`: `RAS:CRASConnectionTestingPage::PageDlgProc: PSN_WIZNEXT: Closing thread handle.`

## pseudocode

```c
__int64 __fastcall CRASConnectionTestingPage::PageDlgProc(HWND hWnd, int a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rbx
  bool v8; // zf
  int v9; // edx
  HWND DlgItem; // rax
  HWND v11; // rax
  HWND v12; // rcx
  int *PropW; // rax
  int *v14; // rdi
  HWND Parent; // rax
  LPARAM StringPcch; // rbx
  HWND v18; // rax
  LPARAM v19; // rbx
  HWND v20; // rax
  HWND v21; // rcx
  HWND v22; // rax

  v4 = a4;
  if ( a2 != 272 )
  {
    if ( a2 == 2 )
    {
      RemovePropW(hWnd, L"_Win32_this_");
    }
    else
    {
      PropW = (int *)GetPropW(hWnd, L"_Win32_this_");
      v14 = PropW;
      if ( a2 == 78 )
      {
        if ( *(_DWORD *)(v4 + 16) == -207 )
        {
          if ( !PropW[282] )
          {
            if ( PropW[283] )
            {
              if ( *((_QWORD *)PropW + 142) )
              {
                if ( g_dwTraceId != -1 )
                  TracePrintfExA(
                    g_dwTraceId,
                    0xCu,
                    "RAS:CRASConnectionTestingPage::PageDlgProc: Waiting for connect thread to finish execution.");
                WaitForSingleObject(*((HANDLE *)v14 + 142), 0xFFFFFFFF);
                if ( g_dwTraceId != -1 )
                  TracePrintfExA(
                    g_dwTraceId,
                    0xCu,
                    "RAS:CRASConnectionTestingPage::PageDlgProc: PSN_WIZNEXT: Closing thread handle.");
                CloseHandle(*((HANDLE *)v14 + 142));
                *((_QWORD *)v14 + 142) = 0;
              }
            }
            else
            {
              CRASConnectionTestingPage::AbortConnecting((CRASConnectionTestingPage *)PropW, 0xC98u);
            }
          }
          return 1;
        }
        if ( *(_DWORD *)(v4 + 16) == -200 )
        {
          CRASConnectionTestingPage::ResetFlagsInPropertyBag((struct CRASConnectionTestingPage *)PropW);
          if ( a3 == 4294967089LL )
          {
            if ( g_dwTraceId != -1 )
              TracePrintfExA(
                g_dwTraceId,
                0xCu,
                "RAS:CRASConnectionTestingPage::PageDlgProc: PSN_SETACTIVE: PSN_WIZNEXT");
            Parent = GetParent(*((HWND *)v14 + 1));
            PostMessageW(Parent, 0x470u, 1u, 0);
            StringPcch = PszLoadStringPcch(hInst);
            v18 = GetParent(hWnd);
            SendMessageW(v18, 0x489u, 0, StringPcch);
            v19 = PszLoadStringPcch(hInst);
            v20 = GetParent(hWnd);
            SendMessageW(v20, 0x479u, 0, v19);
            v21 = hWnd;
            if ( v14[10] > 2 )
              v21 = GetParent(hWnd);
            *((_QWORD *)v14 + 2) = GetParent(v21);
            if ( !(unsigned int)CRASConnectionTestingPage::LaunchConnectThread((CRASConnectionTestingPage *)v14) )
            {
              v22 = GetParent(hWnd);
              PostMessageW(v22, 0x471u, 5u, 0);
            }
          }
          else
          {
            if ( g_dwTraceId != -1 )
              TracePrintfExA(
                g_dwTraceId,
                0xCu,
                "RAS:CRASConnectionTestingPage::PageDlgProc: PSN_SETACTIVE: PSN_WIZBACK");
            (*(void (__fastcall **)(_QWORD, int *, const wchar_t *, _QWORD, _QWORD))(**((_QWORD **)v14 + 10) + 56LL))(
              *((_QWORD *)v14 + 10),
              v14 + 11,
              L"InternetTestFailed",
              0,
              0);
            SetWindowLongPtrW(hWnd, 0, -1);
          }
          return 1;
        }
      }
    }
    return 0;
  }
  if ( *(_DWORD *)a4 == 104 )
    v4 = *(_QWORD *)(a4 + 48);
  SetPropW(hWnd, L"_Win32_this_", (HANDLE)v4);
  v8 = *(_DWORD *)(v4 + 60) == 0;
  *(_QWORD *)(v4 + 8) = hWnd;
  v9 = 2083;
  if ( v8 )
    v9 = 2084;
  DlgItem = GetDlgItem(hWnd, v9);
  ShowWindow(DlgItem, 0);
  v11 = GetDlgItem(*(HWND *)(v4 + 8), 2086);
  v12 = *(HWND *)(v4 + 8);
  *(_QWORD *)(v4 + 24) = v11;
  *(_QWORD *)(v4 + 32) = GetDlgItem(v12, 2085);
  return 1;
}

```

## disassembly

```asm
0x18001bc90  mov     [rsp+arg_0], rbx
0x18001bc95  mov     [rsp+arg_10], rbp
0x18001bc9a  push    rsi
0x18001bc9b  push    rdi
0x18001bc9c  push    r14
0x18001bc9e  sub     rsp, 30h
0x18001bca2  mov     rbx, r9
0x18001bca5  mov     r14, r8
0x18001bca8  mov     ebp, edx
0x18001bcaa  mov     rsi, rcx
0x18001bcad  cmp     edx, 110h
0x18001bcb3  jnz     short loc_18001BD22
0x18001bcb5  cmp     dword ptr [r9], 68h ; 'h'
0x18001bcb9  jnz     short loc_18001BCBF
0x18001bcbb  mov     rbx, [r9+30h]
0x18001bcbf  mov     r8, rbx; hData
0x18001bcc2  lea     rdx, aWin32This_6; "_Win32_this_"
0x18001bcc9  call    cs:__imp_SetPropW
0x18001bccf  cmp     dword ptr [rbx+3Ch], 0
0x18001bcd3  mov     rcx, rsi; hDlg
0x18001bcd6  mov     [rbx+8], rsi
0x18001bcda  mov     edx, 823h
0x18001bcdf  jnz     short loc_18001BCE6
0x18001bce1  mov     edx, 824h; nIDDlgItem
0x18001bce6  call    cs:__imp_GetDlgItem
0x18001bcec  mov     rcx, rax; hWnd
0x18001bcef  xor     edx, edx; nCmdShow
0x18001bcf1  call    cs:__imp_ShowWindow
0x18001bcf7  mov     rcx, [rbx+8]; hDlg
0x18001bcfb  mov     edx, 826h; nIDDlgItem
0x18001bd00  call    cs:__imp_GetDlgItem
0x18001bd06  mov     rcx, [rbx+8]; hDlg
0x18001bd0a  mov     edx, 825h; nIDDlgItem
0x18001bd0f  mov     [rbx+18h], rax
0x18001bd13  call    cs:__imp_GetDlgItem
0x18001bd19  mov     [rbx+20h], rax
0x18001bd1d  jmp     loc_18001BF5D
0x18001bd22  lea     rdx, aWin32This_6; "_Win32_this_"
0x18001bd29  cmp     ebp, 2
0x18001bd2c  jnz     short loc_18001BD36
0x18001bd2e  call    cs:__imp_RemovePropW
0x18001bd34  jmp     short loc_18001BD5B
0x18001bd36  call    cs:__imp_GetPropW
0x18001bd3c  mov     rdi, rax
0x18001bd3f  cmp     ebp, 4Eh ; 'N'
0x18001bd42  jnz     short loc_18001BD5B
0x18001bd44  mov     ebp, 0FFFFFF31h
0x18001bd49  cmp     [rbx+10h], ebp
0x18001bd4c  jz      loc_18001BECC
0x18001bd52  cmp     dword ptr [rbx+10h], 0FFFFFF38h
0x18001bd59  jz      short loc_18001BD62
0x18001bd5b  xor     eax, eax
0x18001bd5d  jmp     loc_18001BF62
0x18001bd62  mov     rcx, rdi; struct CRASConnectionTestingPage *
0x18001bd65  call    ?ResetFlagsInPropertyBag@CRASConnectionTestingPage@@KAXPEAV1@@Z; CRASConnectionTestingPage::ResetFlagsInPropertyBag(CRASConnectionTestingPage *)
0x18001bd6a  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001bd70  or      ebx, 0FFFFFFFFh
0x18001bd73  cmp     r14, rbp
0x18001bd76  jnz     loc_18001BE7B
0x18001bd7c  cmp     ecx, ebx
0x18001bd7e  jz      short loc_18001BD92
0x18001bd80  lea     r8, aRasCrasconnect; "RAS:CRASConnectionTestingPage::PageDlgP"...
0x18001bd87  mov     edx, 0Ch; dwFlags
0x18001bd8c  call    cs:__imp_TracePrintfExA
0x18001bd92  mov     rcx, [rdi+8]; hWnd
0x18001bd96  call    cs:__imp_GetParent
0x18001bd9c  xor     r9d, r9d; lParam
0x18001bd9f  mov     edx, 470h; Msg
0x18001bda4  mov     rcx, rax; hWnd
0x18001bda7  lea     r8d, [r9+1]; wParam
0x18001bdab  call    cs:__imp_PostMessageW
0x18001bdb1  mov     rcx, cs:hInst; hModule
0x18001bdb8  lea     r8, [rsp+48h+arg_8]
0x18001bdbd  mov     ebp, 0C00h
0x18001bdc2  mov     [rsp+48h+arg_8], 0
0x18001bdca  mov     edx, ebp
0x18001bdcc  call    PszLoadStringPcch
0x18001bdd1  mov     rcx, rsi; hWnd
0x18001bdd4  mov     rbx, rax
0x18001bdd7  call    cs:__imp_GetParent
0x18001bddd  mov     r9, rbx; lParam
0x18001bde0  xor     r8d, r8d; wParam
0x18001bde3  mov     rcx, rax; hWnd
0x18001bde6  mov     edx, 489h; Msg
0x18001bdeb  call    cs:__imp_SendMessageW
0x18001bdf1  mov     rcx, cs:hInst; hModule
0x18001bdf8  lea     r8, [rsp+48h+arg_8]
0x18001bdfd  mov     edx, ebp
0x18001bdff  mov     [rsp+48h+arg_8], 0
0x18001be07  call    PszLoadStringPcch
0x18001be0c  mov     rcx, rsi; hWnd
0x18001be0f  mov     rbx, rax
0x18001be12  call    cs:__imp_GetParent
0x18001be18  mov     r9, rbx; lParam
0x18001be1b  xor     r8d, r8d; wParam
0x18001be1e  mov     rcx, rax; hWnd
0x18001be21  mov     edx, 479h; Msg
0x18001be26  call    cs:__imp_SendMessageW
0x18001be2c  cmp     dword ptr [rdi+28h], 2
0x18001be30  mov     rcx, rsi; hWnd
0x18001be33  jle     short loc_18001BE3E
0x18001be35  call    cs:__imp_GetParent
0x18001be3b  mov     rcx, rax; hWnd
0x18001be3e  call    cs:__imp_GetParent
0x18001be44  mov     rcx, rdi; this
0x18001be47  mov     [rdi+10h], rax
0x18001be4b  call    ?LaunchConnectThread@CRASConnectionTestingPage@@IEAAHXZ; CRASConnectionTestingPage::LaunchConnectThread(void)
0x18001be50  test    eax, eax
0x18001be52  jnz     loc_18001BF5D
0x18001be58  mov     rcx, rsi; hWnd
0x18001be5b  call    cs:__imp_GetParent
0x18001be61  xor     r9d, r9d; lParam
0x18001be64  mov     edx, 471h; Msg
0x18001be69  mov     rcx, rax; hWnd
0x18001be6c  lea     r8d, [r9+5]; wParam
0x18001be70  call    cs:__imp_PostMessageW
0x18001be76  jmp     loc_18001BF5D
0x18001be7b  cmp     ecx, ebx
0x18001be7d  jz      short loc_18001BE91
0x18001be7f  lea     r8, aRasCrasconnect_2; "RAS:CRASConnectionTestingPage::PageDlgP"...
0x18001be86  mov     edx, 0Ch; dwFlags
0x18001be8b  call    cs:__imp_TracePrintfExA
0x18001be91  mov     rcx, [rdi+50h]
0x18001be95  lea     rdx, [rdi+2Ch]
0x18001be99  xor     r9d, r9d
0x18001be9c  mov     [rsp+48h+var_28], 0
0x18001bea5  lea     r8, aInternettestfa_0; "InternetTestFailed"
0x18001beac  mov     rax, [rcx]
0x18001beaf  mov     rax, [rax+38h]
0x18001beb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001beb8  or      r8, 0FFFFFFFFFFFFFFFFh; dwNewLong
0x18001bebc  xor     edx, edx; nIndex
0x18001bebe  mov     rcx, rsi; hWnd
0x18001bec1  call    cs:__imp_SetWindowLongPtrW
0x18001bec7  jmp     loc_18001BF5D
0x18001becc  cmp     dword ptr [rax+468h], 0
0x18001bed3  jnz     loc_18001BF5D
0x18001bed9  cmp     dword ptr [rax+46Ch], 0
0x18001bee0  jnz     short loc_18001BEF1
0x18001bee2  mov     edx, 0C98h; unsigned int
0x18001bee7  mov     rcx, rdi; this
0x18001beea  call    ?AbortConnecting@CRASConnectionTestingPage@@IEAAXK@Z; CRASConnectionTestingPage::AbortConnecting(ulong)
0x18001beef  jmp     short loc_18001BF5D
0x18001bef1  cmp     qword ptr [rax+470h], 0
0x18001bef9  jz      short loc_18001BF5D
0x18001befb  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001bf01  or      ebx, 0FFFFFFFFh
0x18001bf04  cmp     ecx, ebx
0x18001bf06  jz      short loc_18001BF1A
0x18001bf08  lea     r8, aRasCrasconnect_1; "RAS:CRASConnectionTestingPage::PageDlgP"...
0x18001bf0f  mov     edx, 0Ch; dwFlags
0x18001bf14  call    cs:__imp_TracePrintfExA
0x18001bf1a  mov     rcx, [rdi+470h]; hHandle
0x18001bf21  mov     edx, ebx; dwMilliseconds
0x18001bf23  call    cs:__imp_WaitForSingleObject
0x18001bf29  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001bf2f  cmp     ecx, ebx
0x18001bf31  jz      short loc_18001BF45
0x18001bf33  lea     r8, aRasCrasconnect_0; "RAS:CRASConnectionTestingPage::PageDlgP"...
0x18001bf3a  mov     edx, 0Ch; dwFlags
0x18001bf3f  call    cs:__imp_TracePrintfExA
0x18001bf45  mov     rcx, [rdi+470h]; hObject
0x18001bf4c  call    cs:__imp_CloseHandle
0x18001bf52  mov     qword ptr [rdi+470h], 0
0x18001bf5d  mov     eax, 1
0x18001bf62  mov     rbx, [rsp+48h+arg_0]
0x18001bf67  mov     rbp, [rsp+48h+arg_10]
0x18001bf6c  add     rsp, 30h
0x18001bf70  pop     r14
0x18001bf72  pop     rdi
0x18001bf73  pop     rsi
0x18001bf74  retn
```
