# CIncomingConnectionSummaryPage::PageDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18001cf90`
- end: `0x18001d187`
- name: `?PageDlgProc@CIncomingConnectionSummaryPage@@CAHPEAUHWND__@@I_K_J@Z`
- size: `503`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180010cac`
- `0x1800112f0`
- `0x180011e20`
- `0x18001cea0`
- `0x18001cf90`
- `0x18002b970`
- `0x18002f3b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d0bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d0d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d0bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d0d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d0af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d0c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d0af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d0c8`
- `USER32!PostMessageW` at `0x18001d116`
- `USER32!PostMessageW` at `0x18001d116`
- `USER32!GetPropW` at `0x18001d000`
- `USER32!GetPropW` at `0x18001d000`
- `USER32!RemovePropW` at `0x18001cff5`
- `USER32!RemovePropW` at `0x18001cff5`
- `USER32!SetPropW` at `0x18001cfde`
- `USER32!SetPropW` at `0x18001cfde`
- `USER32!GetDlgItem` at `0x18001d03b`
- `USER32!GetDlgItem` at `0x18001d053`
- `USER32!GetDlgItem` at `0x18001d03b`
- `USER32!GetDlgItem` at `0x18001d053`
- `USER32!SendMessageW` at `0x18001d154`
- `USER32!SendMessageW` at `0x18001d154`
- `USER32!GetParent` at `0x18001d0fe`
- `USER32!GetParent` at `0x18001d140`
- `USER32!GetParent` at `0x18001d0fe`
- `USER32!GetParent` at `0x18001d140`

## pseudocode

```c
__int64 __fastcall CIncomingConnectionSummaryPage::PageDlgProc(HWND a1, int a2, __int64 a3, __int64 a4)
{
  _DWORD *v4; // rdi
  _DWORD *PropW; // rax
  _DWORD *v9; // rbp
  int v10; // ebx
  int v11; // ebx
  HWND DlgItem; // rax
  void *WindowTextString; // rdi
  HWND v14; // rax
  void *v15; // rbx
  __int64 v16; // rcx
  HANDLE ProcessHeap; // rax
  HANDLE v18; // rax
  HWND Parent; // rax
  LPARAM StringPcch; // rbx
  HWND v22; // rax
  wchar_t pszDest[1024]; // [rsp+60h] [rbp-828h] BYREF

  v4 = (_DWORD *)a4;
  if ( a2 == 272 )
  {
    if ( *(_DWORD *)a4 == 104 )
      v4 = *(_DWORD **)(a4 + 48);
    SetPropW(a1, L"_Win32_this_", v4);
    goto LABEL_16;
  }
  if ( a2 == 2 )
  {
    RemovePropW(a1, L"_Win32_this_");
    return 0;
  }
  PropW = GetPropW(a1, L"_Win32_this_");
  v9 = PropW;
  v10 = a2 - 78;
  if ( !v10 )
  {
    if ( v4[4] == -200 )
    {
      Parent = GetParent(a1);
      PostMessageW(Parent, 0x48Au, 1u, 17);
      StringPcch = PszLoadStringPcch(hInst);
      v22 = GetParent(a1);
      SendMessageW(v22, 0x489u, 0, StringPcch);
      return 1;
    }
    return 0;
  }
  v11 = v10 - 194;
  if ( v11 )
  {
    if ( v11 == 1 && a3 == 2044 )
    {
      DlgItem = GetDlgItem(a1, 2041);
      WindowTextString = (void *)GetWindowTextString(DlgItem);
      v14 = GetDlgItem(a1, 2042);
      v15 = (void *)GetWindowTextString(v14);
      StringCchPrintfExW(pszDest, 0x400u, 0, 0, 0x100u, L"%s\r\n\r\n%s%s", WindowTextString, v15, v9 + 22);
      PrintInfo(v16, pszDest);
      if ( WindowTextString )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, WindowTextString);
      }
      if ( v15 )
      {
        v18 = GetProcessHeap();
        HeapFree(v18, 0, v15);
      }
    }
    return 0;
  }
  v4 = PropW;
LABEL_16:
  CIncomingConnectionSummaryPage::InitDialogControls((CIncomingConnectionSummaryPage *)v4, a1);
  return 1;
}

```

## disassembly

```asm
0x18001cf90  mov     [rsp+arg_8], rbx
0x18001cf95  mov     [rsp+arg_10], rbp
0x18001cf9a  push    rsi
0x18001cf9b  push    rdi
0x18001cf9c  push    r14
0x18001cf9e  sub     rsp, 870h
0x18001cfa5  mov     rax, cs:__security_cookie
0x18001cfac  xor     rax, rsp
0x18001cfaf  mov     [rsp+888h+var_28], rax
0x18001cfb7  mov     rdi, r9
0x18001cfba  mov     r14, r8
0x18001cfbd  mov     ebx, edx
0x18001cfbf  mov     rsi, rcx
0x18001cfc2  cmp     edx, 110h
0x18001cfc8  jnz     short loc_18001CFE9
0x18001cfca  cmp     dword ptr [r9], 68h ; 'h'
0x18001cfce  jnz     short loc_18001CFD4
0x18001cfd0  mov     rdi, [r9+30h]
0x18001cfd4  mov     r8, rdi; hData
0x18001cfd7  lea     rdx, aWin32This_8; "_Win32_this_"
0x18001cfde  call    cs:__imp_SetPropW
0x18001cfe4  jmp     loc_18001D0E1
0x18001cfe9  lea     rdx, aWin32This_8; "_Win32_this_"
0x18001cff0  cmp     ebx, 2
0x18001cff3  jnz     short loc_18001D000
0x18001cff5  call    cs:__imp_RemovePropW
0x18001cffb  jmp     loc_18001D0F7
0x18001d000  call    cs:__imp_GetPropW
0x18001d006  mov     rbp, rax
0x18001d009  sub     ebx, 4Eh ; 'N'
0x18001d00c  jz      loc_18001D0EE
0x18001d012  sub     ebx, 0C2h
0x18001d018  jz      loc_18001D0DE
0x18001d01e  cmp     ebx, 1
0x18001d021  jnz     loc_18001D0F7
0x18001d027  cmp     r14, 7FCh
0x18001d02e  jnz     loc_18001D0F7
0x18001d034  lea     edx, [r14-3]; nIDDlgItem
0x18001d038  mov     rcx, rsi; hDlg
0x18001d03b  call    cs:__imp_GetDlgItem
0x18001d041  mov     rcx, rax; hWnd
0x18001d044  call    GetWindowTextString
0x18001d049  lea     edx, [r14-2]; nIDDlgItem
0x18001d04d  mov     rcx, rsi; hDlg
0x18001d050  mov     rdi, rax
0x18001d053  call    cs:__imp_GetDlgItem
0x18001d059  mov     rcx, rax; hWnd
0x18001d05c  call    GetWindowTextString
0x18001d061  lea     rcx, [rbp+58h]
0x18001d065  mov     rbx, rax
0x18001d068  mov     [rsp+888h+var_848], rcx
0x18001d06d  xor     r9d, r9d; unsigned __int64 *
0x18001d070  mov     [rsp+888h+var_850], rax
0x18001d075  lea     rcx, [rsp+888h+pszDest]; pszDest
0x18001d07a  lea     rax, aSSS; "%s\r\n\r\n%s%s"
0x18001d081  mov     [rsp+888h+var_858], rdi
0x18001d086  mov     [rsp+888h+var_860], rax; unsigned __int16 *
0x18001d08b  xor     r8d, r8d; unsigned __int16 **
0x18001d08e  mov     edx, 400h; unsigned __int64
0x18001d093  mov     [rsp+888h+var_868], 100h; unsigned int
0x18001d09b  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18001d0a0  lea     rdx, [rsp+888h+pszDest]
0x18001d0a5  call    PrintInfo
0x18001d0aa  test    rdi, rdi
0x18001d0ad  jz      short loc_18001D0C3
0x18001d0af  call    cs:__imp_GetProcessHeap
0x18001d0b5  mov     r8, rdi; lpMem
0x18001d0b8  xor     edx, edx; dwFlags
0x18001d0ba  mov     rcx, rax; hHeap
0x18001d0bd  call    cs:__imp_HeapFree
0x18001d0c3  test    rbx, rbx
0x18001d0c6  jz      short loc_18001D0F7
0x18001d0c8  call    cs:__imp_GetProcessHeap
0x18001d0ce  mov     r8, rbx; lpMem
0x18001d0d1  xor     edx, edx; dwFlags
0x18001d0d3  mov     rcx, rax; hHeap
0x18001d0d6  call    cs:__imp_HeapFree
0x18001d0dc  jmp     short loc_18001D0F7
0x18001d0de  mov     rdi, rbp
0x18001d0e1  mov     rdx, rsi; HWND
0x18001d0e4  mov     rcx, rdi; this
0x18001d0e7  call    ?InitDialogControls@CIncomingConnectionSummaryPage@@AEAAXPEAUHWND__@@@Z; CIncomingConnectionSummaryPage::InitDialogControls(HWND__ *)
0x18001d0ec  jmp     short loc_18001D15A
0x18001d0ee  cmp     dword ptr [rdi+10h], 0FFFFFF38h
0x18001d0f5  jz      short loc_18001D0FB
0x18001d0f7  xor     eax, eax
0x18001d0f9  jmp     short loc_18001D15F
0x18001d0fb  mov     rcx, rsi; hWnd
0x18001d0fe  call    cs:__imp_GetParent
0x18001d104  mov     r9d, 11h; lParam
0x18001d10a  mov     edx, 48Ah; Msg
0x18001d10f  mov     rcx, rax; hWnd
0x18001d112  lea     r8d, [r9-10h]; wParam
0x18001d116  call    cs:__imp_PostMessageW
0x18001d11c  mov     rcx, cs:hInst; hModule
0x18001d123  lea     r8, [rsp+888h+var_838]
0x18001d128  mov     edx, 0BFEh
0x18001d12d  mov     [rsp+888h+var_838], 0
0x18001d135  call    PszLoadStringPcch
0x18001d13a  mov     rcx, rsi; hWnd
0x18001d13d  mov     rbx, rax
0x18001d140  call    cs:__imp_GetParent
0x18001d146  mov     r9, rbx; lParam
0x18001d149  xor     r8d, r8d; wParam
0x18001d14c  mov     rcx, rax; hWnd
0x18001d14f  mov     edx, 489h; Msg
0x18001d154  call    cs:__imp_SendMessageW
0x18001d15a  mov     eax, 1
0x18001d15f  mov     rcx, [rsp+888h+var_28]
0x18001d167  xor     rcx, rsp; StackCookie
0x18001d16a  call    __security_check_cookie
0x18001d16f  lea     r11, [rsp+888h+var_18]
0x18001d177  mov     rbx, [r11+28h]
0x18001d17b  mov     rbp, [r11+30h]
0x18001d17f  mov     rsp, r11
0x18001d182  pop     r14
0x18001d184  pop     rdi
0x18001d185  pop     rsi
0x18001d186  retn
```
