# AboutPageProc

- ea: `0x18000a3b0`
- end: `0x18000a664`
- name: `AboutPageProc`
- size: `692`
- prototype: `__int64 __fastcall(HWND, const CHAR *, UINT, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x180002e4c`
- `0x1800052b8`
- `0x18000a3b0`
- `0x18000d3b4`
- `0x18000dc18`
- `0x1800116d4`
- `0x180014aae`
- `0x180014ae0`

## import_xrefs

- `USER32!SendMessageW` at `0x18000a553`
- `USER32!SendMessageW` at `0x18000a59b`
- `USER32!SendMessageW` at `0x18000a5d4`
- `USER32!SendMessageW` at `0x18000a618`
- `USER32!SendMessageW` at `0x18000a553`
- `USER32!SendMessageW` at `0x18000a59b`
- `USER32!SendMessageW` at `0x18000a5d4`
- `USER32!SendMessageW` at `0x18000a618`
- `USER32!GetDlgItem` at `0x18000a3f9`
- `USER32!GetDlgItem` at `0x18000a3f9`
- `USER32!LoadStringW` at `0x18000a476`
- `USER32!LoadStringW` at `0x18000a4db`
- `USER32!LoadStringW` at `0x18000a476`
- `USER32!LoadStringW` at `0x18000a4db`
- `KERNEL32!GetSystemDirectoryW` at `0x18000a41b`
- `KERNEL32!GetSystemDirectoryW` at `0x18000a41b`

## pseudocode

```c
__int64 __fastcall AboutPageProc(HWND a1, const CHAR *a2, UINT a3, __int64 a4)
{
  HWND DlgItem; // rsi
  unsigned int i; // r14d
  int v6; // ebx
  __int64 v8; // [rsp+20h] [rbp-E0h]
  __int64 v9; // [rsp+28h] [rbp-D8h]
  __int64 v10; // [rsp+30h] [rbp-D0h]
  LPARAM v11; // [rsp+40h] [rbp-C0h] BYREF
  int v12; // [rsp+48h] [rbp-B8h]
  int v13; // [rsp+4Ch] [rbp-B4h]
  int v14; // [rsp+50h] [rbp-B0h]
  WCHAR *v15; // [rsp+58h] [rbp-A8h]
  _DWORD lParam[6]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR *v17; // [rsp+B8h] [rbp-48h]
  int v18; // [rsp+C4h] [rbp-3Ch]
  _BYTE v19[1536]; // [rsp+100h] [rbp+0h] BYREF
  unsigned int v20; // [rsp+700h] [rbp+600h]
  int v21; // [rsp+704h] [rbp+604h]
  int v22; // [rsp+708h] [rbp+608h]
  int v23; // [rsp+70Ch] [rbp+60Ch]
  WCHAR v24[128]; // [rsp+710h] [rbp+610h] BYREF
  WCHAR v25[128]; // [rsp+810h] [rbp+710h] BYREF
  wchar_t pszDest[264]; // [rsp+910h] [rbp+810h] BYREF
  WCHAR Buffer[264]; // [rsp+B20h] [rbp+A20h] BYREF

  if ( (_DWORD)a2 != 78 )
  {
    if ( (_DWORD)a2 == 272 )
    {
      DlgItem = GetDlgItem(a1, 1897);
      LoadListTitles(DlgItem, 0x76Au);
      GetSystemDirectoryW(Buffer, 0x105u);
      for ( i = 0; i < 6; ++i )
      {
        memset_0(v19, 0, 0x610u);
        memset_0(lParam, 0, 0x58u);
        LoadStringW(g_hResDLL, *((_DWORD *)&CoreFiles + 4 * (int)i + 2), v25, 128);
        StringCchPrintfW(pszDest, 0x105u, L"%s\\%s", Buffer, (&CoreFiles)[2 * (int)i]);
        if ( (unsigned int)GetFileVersion(pszDest, v19) )
        {
          LODWORD(v10) = v23;
          LODWORD(v9) = v22;
          LODWORD(v8) = v21;
          StringCchPrintfW(v24, 0x80u, L"%d.%d.%d.%d", v20, v8, v9, v10);
        }
        else
        {
          LoadStringW(g_hResDLL, 0x772u, v24, 128);
        }
        lParam[1] = i;
        v17 = v25;
        lParam[2] = 0;
        v18 = 0;
        lParam[0] = 1;
        v6 = SendMessageW(DlgItem, 0x104Du, 0, (LPARAM)lParam);
        if ( v6 == -1 )
          return 1;
        memset_0(&v11, 0, 0x58u);
        v15 = v24;
        v12 = 1;
        SendMessageW(DlgItem, 0x1074u, v6, (LPARAM)&v11);
        memset_0(&v11, 0, 0x58u);
        v12 = 2;
        v15 = pszDest;
        SendMessageW(DlgItem, 0x1074u, v6, (LPARAM)&v11);
      }
      SetColumnWidth(DlgItem);
      memset_0(&v11, 0, 0x58u);
      v14 = 3;
      v13 = 3;
      SendMessageW(DlgItem, 0x102Bu, 0, (LPARAM)&v11);
    }
    return 0;
  }
  if ( *(_DWORD *)(a4 + 16) != -205 )
    return 0;
  HtmlHelpA(a1, a2, a3, 0xC8u);
  return 1;
}

```

## disassembly

```asm
0x18000a3b0  mov     [rsp-8+arg_8], rbx
0x18000a3b5  mov     [rsp-8+arg_10], rsi
0x18000a3ba  push    rbp
0x18000a3bb  push    r14
0x18000a3bd  push    r15
0x18000a3bf  lea     rbp, [rsp-0C40h]
0x18000a3c7  sub     rsp, 0D40h
0x18000a3ce  mov     rax, cs:__security_cookie
0x18000a3d5  xor     rax, rsp
0x18000a3d8  mov     [rbp+0C50h+var_20], rax
0x18000a3df  cmp     edx, 4Eh ; 'N'
0x18000a3e2  jz      loc_18000A648
0x18000a3e8  cmp     edx, 110h
0x18000a3ee  jnz     loc_18000A61E
0x18000a3f4  mov     edx, 769h; nIDDlgItem
0x18000a3f9  call    cs:__imp_GetDlgItem
0x18000a3ff  mov     rcx, rax; hWnd
0x18000a402  mov     edx, 76Ah; uID
0x18000a407  mov     rsi, rax
0x18000a40a  call    LoadListTitles
0x18000a40f  mov     edx, 105h; uSize
0x18000a414  lea     rcx, [rbp+0C50h+Buffer]; lpBuffer
0x18000a41b  call    cs:__imp_GetSystemDirectoryW
0x18000a421  xor     r14d, r14d
0x18000a424  lea     r15d, [r14+58h]
0x18000a428  cmp     r14d, 6
0x18000a42c  jnb     loc_18000A5E2
0x18000a432  xor     edx, edx; Val
0x18000a434  lea     rcx, [rbp+0C50h+var_C50]; void *
0x18000a438  mov     r8d, 610h; Size
0x18000a43e  call    memset_0
0x18000a443  mov     r8, r15; Size
0x18000a446  lea     rcx, [rbp+0C50h+lParam]; void *
0x18000a44a  xor     edx, edx; Val
0x18000a44c  call    memset_0
0x18000a451  mov     rcx, cs:g_hResDLL; hInstance
0x18000a458  lea     rdx, CoreFiles
0x18000a45f  movsxd  rbx, r14d
0x18000a462  lea     r8, [rbp+0C50h+var_540]; lpBuffer
0x18000a469  add     rbx, rbx
0x18000a46c  mov     r9d, 80h; cchBufferMax
0x18000a472  mov     edx, [rdx+rbx*8+8]; uID
0x18000a476  call    cs:__imp_LoadStringW
0x18000a47c  lea     rax, CoreFiles
0x18000a483  mov     edx, 105h; cchDest
0x18000a488  mov     rax, [rax+rbx*8]
0x18000a48c  lea     r9, [rbp+0C50h+Buffer]
0x18000a493  lea     r8, aSS_0; "%s\\%s"
0x18000a49a  mov     [rsp+0D50h+var_D30], rax
0x18000a49f  lea     rcx, [rbp+0C50h+pszDest]; pszDest
0x18000a4a6  call    StringCchPrintfW
0x18000a4ab  xor     r8d, r8d
0x18000a4ae  lea     rdx, [rbp+0C50h+var_C50]; void *
0x18000a4b2  lea     rcx, [rbp+0C50h+pszDest]; lptstrFilename
0x18000a4b9  call    GetFileVersion
0x18000a4be  test    eax, eax
0x18000a4c0  jnz     short loc_18000A4E3
0x18000a4c2  mov     rcx, cs:g_hResDLL; hInstance
0x18000a4c9  lea     r8, [rbp+0C50h+var_640]; lpBuffer
0x18000a4d0  mov     r9d, 80h; cchBufferMax
0x18000a4d6  mov     edx, 772h; uID
0x18000a4db  call    cs:__imp_LoadStringW
0x18000a4e1  jmp     short loc_18000A520
0x18000a4e3  mov     eax, [rbp+0C50h+var_644]
0x18000a4e9  lea     r8, aDDDD; "%d.%d.%d.%d"
0x18000a4f0  mov     r9d, [rbp+0C50h+var_650]
0x18000a4f7  lea     rcx, [rbp+0C50h+var_640]; pszDest
0x18000a4fe  mov     [rsp+0D50h+var_D20], eax
0x18000a502  mov     edx, 80h; cchDest
0x18000a507  mov     eax, [rbp+0C50h+var_648]
0x18000a50d  mov     dword ptr [rsp+0D50h+var_D28], eax
0x18000a511  mov     eax, [rbp+0C50h+var_64C]
0x18000a517  mov     dword ptr [rsp+0D50h+var_D30], eax
0x18000a51b  call    StringCchPrintfW
0x18000a520  lea     rax, [rbp+0C50h+var_540]
0x18000a527  mov     dword ptr [rbp+0C50h+lParam+4], r14d
0x18000a52b  lea     r9, [rbp+0C50h+lParam]; lParam
0x18000a52f  mov     [rbp+0C50h+var_C98], rax
0x18000a533  xor     r8d, r8d; wParam
0x18000a536  mov     [rbp+0C50h+var_CA8], 0
0x18000a53d  mov     edx, 104Dh; Msg
0x18000a542  mov     [rbp+0C50h+var_C8C], 0
0x18000a549  mov     rcx, rsi; hWnd
0x18000a54c  mov     dword ptr [rbp+0C50h+lParam], 1
0x18000a553  call    cs:__imp_SendMessageW
0x18000a559  mov     rbx, rax
0x18000a55c  cmp     eax, 0FFFFFFFFh
0x18000a55f  jz      loc_18000A65D
0x18000a565  mov     r8, r15; Size
0x18000a568  lea     rcx, [rsp+0D50h+var_D10]; void *
0x18000a56d  xor     edx, edx; Val
0x18000a56f  call    memset_0
0x18000a574  lea     rax, [rbp+0C50h+var_640]
0x18000a57b  movsxd  rbx, ebx
0x18000a57e  mov     r8, rbx; wParam
0x18000a581  mov     [rsp+0D50h+var_CF8], rax
0x18000a586  lea     r9, [rsp+0D50h+var_D10]; lParam
0x18000a58b  mov     [rsp+0D50h+var_D08], 1
0x18000a593  mov     edx, 1074h; Msg
0x18000a598  mov     rcx, rsi; hWnd
0x18000a59b  call    cs:__imp_SendMessageW
0x18000a5a1  mov     r8, r15; Size
0x18000a5a4  lea     rcx, [rsp+0D50h+var_D10]; void *
0x18000a5a9  xor     edx, edx; Val
0x18000a5ab  call    memset_0
0x18000a5b0  lea     rax, [rbp+0C50h+pszDest]
0x18000a5b7  mov     [rsp+0D50h+var_D08], 2
0x18000a5bf  lea     r9, [rsp+0D50h+var_D10]; lParam
0x18000a5c4  mov     [rsp+0D50h+var_CF8], rax
0x18000a5c9  mov     r8, rbx; wParam
0x18000a5cc  mov     edx, 1074h; Msg
0x18000a5d1  mov     rcx, rsi; hWnd
0x18000a5d4  call    cs:__imp_SendMessageW
0x18000a5da  inc     r14d
0x18000a5dd  jmp     loc_18000A428
0x18000a5e2  mov     ebx, 3
0x18000a5e7  mov     rcx, rsi; hWnd
0x18000a5ea  mov     edx, ebx
0x18000a5ec  call    SetColumnWidth
0x18000a5f1  mov     r8, r15; Size
0x18000a5f4  lea     rcx, [rsp+0D50h+var_D10]; void *
0x18000a5f9  xor     edx, edx; Val
0x18000a5fb  call    memset_0
0x18000a600  lea     r9, [rsp+0D50h+var_D10]; lParam
0x18000a605  mov     [rsp+0D50h+var_D00], ebx
0x18000a609  xor     r8d, r8d; wParam
0x18000a60c  mov     [rsp+0D50h+var_D04], ebx
0x18000a610  mov     edx, 102Bh; Msg
0x18000a615  mov     rcx, rsi; hWnd
0x18000a618  call    cs:__imp_SendMessageW
0x18000a61e  xor     eax, eax
0x18000a620  mov     rcx, [rbp+0C50h+var_20]
0x18000a627  xor     rcx, rsp; StackCookie
0x18000a62a  call    __security_check_cookie
0x18000a62f  lea     r11, [rsp+0D50h+var_10]
0x18000a637  mov     rbx, [r11+28h]
0x18000a63b  mov     rsi, [r11+30h]
0x18000a63f  mov     rsp, r11
0x18000a642  pop     r15
0x18000a644  pop     r14
0x18000a646  pop     rbp
0x18000a647  retn
0x18000a648  cmp     dword ptr [r9+10h], 0FFFFFF33h
0x18000a650  jnz     short loc_18000A61E
0x18000a652  mov     r9d, 0C8h; dwData
0x18000a658  call    HtmlHelpA
0x18000a65d  mov     eax, 1
0x18000a662  jmp     short loc_18000A620
```
