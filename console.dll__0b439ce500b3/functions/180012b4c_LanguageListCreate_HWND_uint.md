# LanguageListCreate(HWND__ *,uint)

- ea: `0x180012b4c`
- end: `0x180012d14`
- name: `?LanguageListCreate@@YAHPEAUHWND__@@I@Z`
- size: `456`
- prototype: `__int64 __fastcall(HWND hDlg, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b5a0`

## callees

- `0x1800015b0`
- `0x180002088`
- `0x180012b4c`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetOEMCP` at `0x180012bb2`
- `api-ms-win-core-localization-l1-2-0!GetOEMCP` at `0x180012bb2`
- `api-ms-win-core-localization-l1-2-0!GetCPInfoExW` at `0x180012bc9`
- `api-ms-win-core-localization-l1-2-0!GetCPInfoExW` at `0x180012c43`
- `api-ms-win-core-localization-l1-2-0!GetCPInfoExW` at `0x180012bc9`
- `api-ms-win-core-localization-l1-2-0!GetCPInfoExW` at `0x180012c43`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x180012ce9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x180012ce9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180012ba6`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180012be9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180012c0b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180012c29`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180012c61`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180012c81`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180012c9d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180012cb7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180012cd1`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180012ba6`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180012be9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180012c0b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180012c29`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180012c61`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180012c81`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180012c9d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180012cb7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180012cd1`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180012b89`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180012b89`

## pseudocode

```c
__int64 __fastcall LanguageListCreate(HWND hDlg, int a2)
{
  HWND DlgItem; // rdi
  UINT OEMCP; // esi
  unsigned int v6; // eax
  unsigned int v7; // ebx
  unsigned int v8; // eax
  unsigned int v9; // ebx
  int v10; // eax
  unsigned int v11; // ebx
  struct _cpinfoexW CPInfoEx; // [rsp+20h] [rbp-258h] BYREF

  memset_0(&CPInfoEx, 0, sizeof(CPInfoEx));
  DlgItem = GetDlgItem(hDlg, 113);
  SendMessageW(DlgItem, 0x14Bu, 0, 0);
  OEMCP = GetOEMCP();
  if ( GetCPInfoExW(OEMCP, 0, &CPInfoEx) )
  {
    v6 = SendMessageW(DlgItem, 0x143u, 0, (LPARAM)CPInfoEx.CodePageName);
    v7 = v6;
    if ( v6 != -1 )
    {
      SendMessageW(DlgItem, 0x151u, v6, OEMCP);
      if ( a2 == OEMCP )
        SendMessageW(DlgItem, 0x14Eu, (int)v7, 0);
    }
  }
  if ( GetCPInfoExW(0x1B5u, 0, &CPInfoEx) )
  {
    v8 = SendMessageW(DlgItem, 0x143u, 0, (LPARAM)CPInfoEx.CodePageName);
    v9 = v8;
    if ( v8 != -1 )
    {
      SendMessageW(DlgItem, 0x151u, v8, 437);
      if ( a2 == 437 )
        SendMessageW(DlgItem, 0x14Eu, (int)v9, 0);
    }
  }
  v10 = SendMessageW(DlgItem, 0x147u, 0, 0);
  v11 = SendMessageW(DlgItem, 0x150u, v10, 0);
  EnableWindow(DlgItem, g_fEastAsianSystem);
  return v11;
}

```

## disassembly

```asm
0x180012b4c  push    rbx
0x180012b4e  push    rbp
0x180012b4f  push    rsi
0x180012b50  push    rdi
0x180012b51  sub     rsp, 258h
0x180012b58  mov     rax, cs:__security_cookie
0x180012b5f  xor     rax, rsp
0x180012b62  mov     [rsp+278h+var_38], rax
0x180012b6a  mov     ebp, edx
0x180012b6c  mov     rbx, rcx
0x180012b6f  xor     edx, edx; Val
0x180012b71  lea     rcx, [rsp+278h+CPInfoEx]; void *
0x180012b76  mov     r8d, 220h; Size
0x180012b7c  call    memset_0
0x180012b81  mov     edx, 71h ; 'q'; nIDDlgItem
0x180012b86  mov     rcx, rbx; hDlg
0x180012b89  call    cs:__imp_GetDlgItem
0x180012b90  nop     dword ptr [rax+rax+00h]
0x180012b95  xor     r9d, r9d; lParam
0x180012b98  xor     r8d, r8d; wParam
0x180012b9b  mov     rcx, rax; hWnd
0x180012b9e  mov     edx, 14Bh; Msg
0x180012ba3  mov     rdi, rax
0x180012ba6  call    cs:__imp_SendMessageW
0x180012bad  nop     dword ptr [rax+rax+00h]
0x180012bb2  call    cs:__imp_GetOEMCP
0x180012bb9  nop     dword ptr [rax+rax+00h]
0x180012bbe  lea     r8, [rsp+278h+CPInfoEx]; lpCPInfoEx
0x180012bc3  xor     edx, edx; dwFlags
0x180012bc5  mov     ecx, eax; CodePage
0x180012bc7  mov     esi, eax
0x180012bc9  call    cs:__imp_GetCPInfoExW
0x180012bd0  nop     dword ptr [rax+rax+00h]
0x180012bd5  test    eax, eax
0x180012bd7  jz      short loc_180012C35
0x180012bd9  lea     r9, [rsp+278h+CPInfoEx.CodePageName]; lParam
0x180012bde  xor     r8d, r8d; wParam
0x180012be1  mov     edx, 143h; Msg
0x180012be6  mov     rcx, rdi; hWnd
0x180012be9  call    cs:__imp_SendMessageW
0x180012bf0  nop     dword ptr [rax+rax+00h]
0x180012bf5  mov     rbx, rax
0x180012bf8  cmp     eax, 0FFFFFFFFh
0x180012bfb  jz      short loc_180012C35
0x180012bfd  mov     r9d, esi; lParam
0x180012c00  mov     r8d, ebx; wParam
0x180012c03  mov     edx, 151h; Msg
0x180012c08  mov     rcx, rdi; hWnd
0x180012c0b  call    cs:__imp_SendMessageW
0x180012c12  nop     dword ptr [rax+rax+00h]
0x180012c17  cmp     ebp, esi
0x180012c19  jnz     short loc_180012C35
0x180012c1b  movsxd  r8, ebx; wParam
0x180012c1e  xor     r9d, r9d; lParam
0x180012c21  mov     edx, 14Eh; Msg
0x180012c26  mov     rcx, rdi; hWnd
0x180012c29  call    cs:__imp_SendMessageW
0x180012c30  nop     dword ptr [rax+rax+00h]
0x180012c35  mov     esi, 1B5h
0x180012c3a  lea     r8, [rsp+278h+CPInfoEx]; lpCPInfoEx
0x180012c3f  mov     ecx, esi; CodePage
0x180012c41  xor     edx, edx; dwFlags
0x180012c43  call    cs:__imp_GetCPInfoExW
0x180012c4a  nop     dword ptr [rax+rax+00h]
0x180012c4f  test    eax, eax
0x180012c51  jz      short loc_180012CA9
0x180012c53  lea     r9, [rsp+278h+CPInfoEx.CodePageName]; lParam
0x180012c58  xor     r8d, r8d; wParam
0x180012c5b  lea     edx, [rsi-72h]; Msg
0x180012c5e  mov     rcx, rdi; hWnd
0x180012c61  call    cs:__imp_SendMessageW
0x180012c68  nop     dword ptr [rax+rax+00h]
0x180012c6d  mov     rbx, rax
0x180012c70  cmp     eax, 0FFFFFFFFh
0x180012c73  jz      short loc_180012CA9
0x180012c75  mov     r8d, ebx; wParam
0x180012c78  lea     edx, [rsi-64h]; Msg
0x180012c7b  mov     r9d, esi; lParam
0x180012c7e  mov     rcx, rdi; hWnd
0x180012c81  call    cs:__imp_SendMessageW
0x180012c88  nop     dword ptr [rax+rax+00h]
0x180012c8d  cmp     ebp, esi
0x180012c8f  jnz     short loc_180012CA9
0x180012c91  movsxd  r8, ebx; wParam
0x180012c94  lea     edx, [rsi-67h]; Msg
0x180012c97  xor     r9d, r9d; lParam
0x180012c9a  mov     rcx, rdi; hWnd
0x180012c9d  call    cs:__imp_SendMessageW
0x180012ca4  nop     dword ptr [rax+rax+00h]
0x180012ca9  xor     r9d, r9d; lParam
0x180012cac  xor     r8d, r8d; wParam
0x180012caf  mov     edx, 147h; Msg
0x180012cb4  mov     rcx, rdi; hWnd
0x180012cb7  call    cs:__imp_SendMessageW
0x180012cbe  nop     dword ptr [rax+rax+00h]
0x180012cc3  movsxd  r8, eax; wParam
0x180012cc6  xor     r9d, r9d; lParam
0x180012cc9  mov     edx, 150h; Msg
0x180012cce  mov     rcx, rdi; hWnd
0x180012cd1  call    cs:__imp_SendMessageW
0x180012cd8  nop     dword ptr [rax+rax+00h]
0x180012cdd  mov     edx, cs:?g_fEastAsianSystem@@3HA; bEnable
0x180012ce3  mov     rcx, rdi; hWnd
0x180012ce6  mov     rbx, rax
0x180012ce9  call    cs:__imp_EnableWindow
0x180012cf0  nop     dword ptr [rax+rax+00h]
0x180012cf5  mov     eax, ebx
0x180012cf7  mov     rcx, [rsp+278h+var_38]
0x180012cff  xor     rcx, rsp; StackCookie
0x180012d02  call    __security_check_cookie
0x180012d07  add     rsp, 258h
0x180012d0e  pop     rdi
0x180012d0f  pop     rsi
0x180012d10  pop     rbp
0x180012d11  pop     rbx
0x180012d12  retn
```
