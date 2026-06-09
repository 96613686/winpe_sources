# DrInit

- ea: `0x18000bd74`
- end: `0x18000c555`
- name: `DrInit`
- size: `2017`
- prototype: `__int64 __fastcall(HWND hWnd, _BYTE *)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000b510`

## callees

- `0x18000b630`
- `0x18000b694`
- `0x18000b7ec`
- `0x18000b8d8`
- `0x18000baf4`
- `0x18000bc30`
- `0x18000bc88`
- `0x18000bd74`
- `0x18000c7f0`
- `0x18002b6e0`
- `0x18002b74c`
- `0x18003b784`
- `0x18003c43c`
- `0x18003d184`
- `0x180046234`
- `0x180047a50`
- `0x180048364`
- `0x180048b6c`
- `0x18004d0d2`
- `0x18004d110`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000bdfc`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000bdfc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c156`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c156`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000c138`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000c19b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000c138`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000c19b`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000c12f`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000c12f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c459`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c459`
- `USER32!ShowWindow` at `0x18000bfea`
- `USER32!ShowWindow` at `0x18000bff9`
- `USER32!ShowWindow` at `0x18000c02d`
- `USER32!ShowWindow` at `0x18000c4ef`
- `USER32!ShowWindow` at `0x18000bfea`
- `USER32!ShowWindow` at `0x18000bff9`
- `USER32!ShowWindow` at `0x18000c02d`
- `USER32!ShowWindow` at `0x18000c4ef`
- `USER32!SetWindowLongPtrW` at `0x18000be76`
- `USER32!SetWindowLongPtrW` at `0x18000be76`
- `USER32!SendMessageW` at `0x18000bf90`
- `USER32!SendMessageW` at `0x18000c1c2`
- `USER32!SendMessageW` at `0x18000c1ec`
- `USER32!SendMessageW` at `0x18000c205`
- `USER32!SendMessageW` at `0x18000c24b`
- `USER32!SendMessageW` at `0x18000c2b9`
- `USER32!SendMessageW` at `0x18000c2d1`
- `USER32!SendMessageW` at `0x18000c492`
- `USER32!SendMessageW` at `0x18000bf90`
- `USER32!SendMessageW` at `0x18000c1c2`
- `USER32!SendMessageW` at `0x18000c1ec`
- `USER32!SendMessageW` at `0x18000c205`
- `USER32!SendMessageW` at `0x18000c24b`
- `USER32!SendMessageW` at `0x18000c2b9`
- `USER32!SendMessageW` at `0x18000c2d1`
- `USER32!SendMessageW` at `0x18000c492`
- `USER32!EndDialog` at `0x18000be33`
- `USER32!EndDialog` at `0x18000c3ce`
- `USER32!EndDialog` at `0x18000be33`
- `USER32!EndDialog` at `0x18000c3ce`
- `USER32!SetWindowTextW` at `0x18000c14b`
- `USER32!SetWindowTextW` at `0x18000c192`
- `USER32!SetWindowTextW` at `0x18000c1d6`
- `USER32!SetWindowTextW` at `0x18000c219`
- `USER32!SetWindowTextW` at `0x18000c339`
- `USER32!SetWindowTextW` at `0x18000c14b`
- `USER32!SetWindowTextW` at `0x18000c192`
- `USER32!SetWindowTextW` at `0x18000c1d6`
- `USER32!SetWindowTextW` at `0x18000c219`
- `USER32!SetWindowTextW` at `0x18000c339`
- `USER32!GetDlgItem` at `0x18000beb0`
- `USER32!GetDlgItem` at `0x18000becc`
- `USER32!GetDlgItem` at `0x18000bee8`
- `USER32!GetDlgItem` at `0x18000befa`
- `USER32!GetDlgItem` at `0x18000bf0c`
- `USER32!GetDlgItem` at `0x18000bf1e`
- `USER32!GetDlgItem` at `0x18000bf30`
- `USER32!GetDlgItem` at `0x18000bfa4`
- `USER32!GetDlgItem` at `0x18000bfc0`
- `USER32!GetDlgItem` at `0x18000bfd2`
- `USER32!GetDlgItem` at `0x18000c022`
- `USER32!GetDlgItem` at `0x18000c041`
- `USER32!GetDlgItem` at `0x18000c053`
- `USER32!GetDlgItem` at `0x18000c065`
- `USER32!GetDlgItem` at `0x18000c077`
- `USER32!GetDlgItem` at `0x18000c186`
- `USER32!GetDlgItem` at `0x18000c4d6`
- `USER32!GetDlgItem` at `0x18000beb0`
- `USER32!GetDlgItem` at `0x18000becc`
- `USER32!GetDlgItem` at `0x18000bee8`
- `USER32!GetDlgItem` at `0x18000befa`
- `USER32!GetDlgItem` at `0x18000bf0c`
- `USER32!GetDlgItem` at `0x18000bf1e`
- `USER32!GetDlgItem` at `0x18000bf30`
- `USER32!GetDlgItem` at `0x18000bfa4`
- `USER32!GetDlgItem` at `0x18000bfc0`
- `USER32!GetDlgItem` at `0x18000bfd2`
- `USER32!GetDlgItem` at `0x18000c022`
- `USER32!GetDlgItem` at `0x18000c041`
- `USER32!GetDlgItem` at `0x18000c053`
- `USER32!GetDlgItem` at `0x18000c065`
- `USER32!GetDlgItem` at `0x18000c077`
- `USER32!GetDlgItem` at `0x18000c186`
- `USER32!GetDlgItem` at `0x18000c4d6`
- `USER32!EnableWindow` at `0x18000c008`
- `USER32!EnableWindow` at `0x18000c301`
- `USER32!EnableWindow` at `0x18000c30d`
- `USER32!EnableWindow` at `0x18000c319`
- `USER32!EnableWindow` at `0x18000c4bc`
- `USER32!EnableWindow` at `0x18000c4e4`
- `USER32!EnableWindow` at `0x18000c008`
- `USER32!EnableWindow` at `0x18000c301`
- `USER32!EnableWindow` at `0x18000c30d`
- `USER32!EnableWindow` at `0x18000c319`
- `USER32!EnableWindow` at `0x18000c4bc`
- `USER32!EnableWindow` at `0x18000c4e4`
- `rtutils!TracePrintfExA` at `0x18000bdd2`
- `rtutils!TracePrintfExA` at `0x18000be91`
- `rtutils!TracePrintfExA` at `0x18000bdd2`
- `rtutils!TracePrintfExA` at `0x18000be91`
- `SHELL32!SHGetStockIconInfo` at `0x18000bf6e`
- `SHELL32!SHGetStockIconInfo` at `0x18000bf6e`

## pseudocode

```c
__int64 __fastcall DrInit(HWND hWnd, _BYTE *a2)
{
  unsigned int v2; // r13d
  HGLOBAL v5; // rax
  LONG_PTR v6; // rdi
  __int64 v7; // r15
  int v8; // r12d
  HWND DlgItem; // rax
  HICON hIcon; // r8
  HWND v11; // rcx
  HWND v12; // rax
  HWND v13; // rcx
  int v14; // edx
  HWND v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  void *Text; // rax
  void *v19; // rbx
  WCHAR *v20; // rbx
  HWND v21; // rax
  __int16 v22; // ax
  __int64 v23; // rax
  HWND v24; // rcx
  unsigned int v25; // ebx
  int v26; // edx
  __int64 v27; // rax
  __int64 v29; // rax
  BOOL v30; // ebx
  LPARAM v31; // r9
  HWND v32; // rbx
  int lpBuffer; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[4]; // [rsp+48h] [rbp-B8h] BYREF
  va_list Arguments; // [rsp+50h] [rbp-B0h] BYREF
  SHSTOCKICONINFO psii; // [rsp+60h] [rbp-A0h] BYREF

  v2 = 1;
  v34 = 1;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "DrInit");
  if ( !a2 || !hWnd )
    return v2;
  SetSmallAndBigIcon(hWnd);
  v5 = GlobalAlloc(0x40u, 0xF8u);
  v6 = (LONG_PTR)v5;
  if ( !v5 )
  {
    ErrorDlgUtil(hWnd, 0x13Eu, 8u, lpBuffer, 0x169u, 0xFAu);
LABEL_7:
    EndDialog(hWnd, 0);
    return v2;
  }
  memset_0(v5, 0, 0xF8u);
  *(_QWORD *)v6 = a2;
  *(_QWORD *)(v6 + 8) = hWnd;
  *(_DWORD *)(v6 + 176) = -1;
  *(_DWORD *)(v6 + 228) = *(_DWORD *)(*(_QWORD *)a2 + 476LL);
  SetWindowLongPtrW(hWnd, 16, v6);
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "Context set");
  v7 = *(_QWORD *)(*(_QWORD *)a2 + 440LL);
  v8 = *(_DWORD *)(v7 + 548);
  *(_QWORD *)(v6 + 104) = GetDlgItem(hWnd, 1100);
  if ( (a2[8] & 0x11) != 0 )
  {
    *(_QWORD *)(v6 + 16) = GetDlgItem(hWnd, 1104);
    if ( (a2[8] & 1) != 0 )
    {
      *(_QWORD *)(v6 + 24) = GetDlgItem(hWnd, 1103);
      *(_QWORD *)(v6 + 40) = GetDlgItem(hWnd, 1101);
      *(_QWORD *)(v6 + 48) = GetDlgItem(hWnd, 1622);
      *(_QWORD *)(v6 + 56) = GetDlgItem(hWnd, 1623);
      DlgItem = GetDlgItem(hWnd, 1638);
      *(_QWORD *)(v6 + 112) = DlgItem;
      if ( DlgItem )
      {
        *(&psii.cbSize + 1) = 0;
        memset_0(&psii.cbSize + 1, 0, 0x218u);
        psii.cbSize = 544;
        if ( SHGetStockIconInfo(SIID_SHIELD, 0x101u, &psii) >= 0 )
        {
          hIcon = psii.hIcon;
          v11 = *(HWND *)(v6 + 112);
          *(_QWORD *)(v6 + 152) = psii.hIcon;
          SendMessageW(v11, 0x170u, (WPARAM)hIcon, 0);
        }
      }
    }
    if ( (a2[8] & 2) != 0 )
      *(_QWORD *)(v6 + 32) = GetDlgItem(hWnd, 1102);
  }
  if ( (a2[8] & 4) != 0 )
  {
    *(_QWORD *)(v6 + 64) = GetDlgItem(hWnd, 1416);
    v12 = GetDlgItem(hWnd, 1401);
    *(_QWORD *)(v6 + 240) = v12;
    if ( v8 )
    {
      ShowWindow(*(HWND *)(v6 + 64), 0);
      v13 = *(HWND *)(v6 + 64);
    }
    else
    {
      ShowWindow(v12, 0);
      v13 = *(HWND *)(v6 + 240);
    }
    EnableWindow(v13, 0);
    v14 = 1412;
    if ( *(_DWORD *)(v7 + 24) != 2 )
      v14 = 1437;
    v15 = GetDlgItem(hWnd, v14);
    ShowWindow(v15, 0);
    if ( (a2[8] & 8) != 0 )
    {
      *(_QWORD *)(v6 + 72) = GetDlgItem(hWnd, 1415);
      *(_QWORD *)(v6 + 80) = GetDlgItem(hWnd, 1414);
      *(_QWORD *)(v6 + 88) = GetDlgItem(hWnd, 1108);
    }
  }
  *(_QWORD *)(v6 + 96) = GetDlgItem(hWnd, 1107);
  v16 = *(_QWORD *)(*(_QWORD *)a2 + 32LL);
  *(_DWORD *)(v6 + 224) = *(_DWORD *)(v16 + 8) == 0;
  if ( (a2[8] & 8) != 0 && (unsigned int)TapiNoLocationDlg(v16, v6 + 144, hWnd) )
  {
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a2 + 24LL) + 28LL) = 0;
    goto LABEL_7;
  }
  v17 = *(_QWORD *)a2;
  *(_QWORD *)Buffer = 0;
  Arguments = 0;
  if ( *(_DWORD *)(v17 + 396) )
    Text = (void *)PszFromId(g_hinstDll, 0x636u);
  else
    Text = (void *)GetText(hWnd);
  v19 = Text;
  if ( Text )
  {
    Arguments = *(va_list *)(v7 + 8);
    *(_QWORD *)Buffer = 0;
    FormatMessageW(0x2500u, Text, 0, 0, Buffer, 1u, &Arguments);
    GlobalFree(v19);
    if ( *(_QWORD *)Buffer )
    {
      SetWindowTextW(hWnd, *(LPCWSTR *)Buffer);
      LocalFree(*(HLOCAL *)Buffer);
    }
  }
  if ( *(_DWORD *)(v7 + 24) != 1 )
  {
    v20 = (WCHAR *)PszFromId(g_hinstDll, 0x202u);
    if ( v20 )
    {
      v21 = GetDlgItem(hWnd, 1590);
      SetWindowTextW(v21, v20);
      GlobalFree(v20);
    }
  }
  if ( (a2[8] & 1) != 0 )
  {
    SendMessageW(*(HWND *)(v6 + 16), 0xC5u, 0x100u, 0);
    SetWindowTextW(*(HWND *)(v6 + 16), (LPCWSTR)(*(_QWORD *)a2 + 1522LL));
    SendMessageW(*(HWND *)(v6 + 24), 0xC5u, 0x100u, 0);
    if ( (a2[8] & 2) != 0 )
    {
      SendMessageW(*(HWND *)(v6 + 32), 0xC5u, 0xFu, 0);
      SetWindowTextW(*(HWND *)(v6 + 32), (LPCWSTR)(*(_QWORD *)a2 + 2550LL));
    }
    if ( *(_DWORD *)(*(_QWORD *)a2 + 392LL) || *(_DWORD *)(*(_QWORD *)a2 + 456LL) )
    {
      EnableWindow(*(HWND *)(v6 + 40), 0);
      EnableWindow(*(HWND *)(v6 + 48), 0);
      EnableWindow(*(HWND *)(v6 + 56), 0);
      EncodePasswordW(*(_QWORD *)a2 + 2036LL);
      SetWindowTextW(*(HWND *)(v6 + 24), (LPCWSTR)(*(_QWORD *)a2 + 2036LL));
      EncodePasswordW(*(_QWORD *)a2 + 2036LL);
      goto LABEL_52;
    }
    v22 = SendMessageW(*(HWND *)(v6 + 24), 0xD2u, 0, 0);
    *(_WORD *)(v6 + 120) = v22;
    if ( !v22 )
      *(_WORD *)(v6 + 120) = 9679;
    DrGetFriendlyFont(hWnd, 1, (HFONT *)(v6 + 136));
    DrGetFriendlyFont(hWnd, 0, (HFONT *)(v6 + 128));
    v23 = *(_QWORD *)a2;
    if ( *(_DWORD *)(*(_QWORD *)a2 + 460LL) )
    {
      v24 = *(HWND *)(v6 + 48);
    }
    else
    {
      v25 = 0;
      if ( !*(_DWORD *)(v23 + 464) || !*(_DWORD *)(v23 + 360) )
        goto LABEL_50;
      v24 = *(HWND *)(v6 + 56);
    }
    SendMessageW(v24, 0xF1u, 1u, 0);
    v25 = 1;
LABEL_50:
    SendMessageW(*(HWND *)(v6 + 40), 0xF1u, v25, 0);
    DrEnableDisablePwControls(v6, v25);
    DrPopulatePasswordField(v6, 1, 0, &v34);
    v2 = v34;
  }
LABEL_52:
  if ( (a2[8] & 4) != 0 )
  {
    *(_QWORD *)(v6 + 160) = 0;
    v26 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a2 + 24LL) + 24LL);
    if ( !v26
      || (v27 = DtlNodeFromIndex(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)a2 + 440LL) + 32LL), (unsigned int)(v26 - 1)),
          (*(_QWORD *)(v6 + 160) = v27) == 0) )
    {
      v27 = **(_QWORD **)(*(_QWORD *)(*(_QWORD *)a2 + 440LL) + 32LL);
      *(_QWORD *)(v6 + 160) = v27;
    }
    *(_QWORD *)(v6 + 168) = *(_QWORD *)(v27 + 16);
    if ( v8 )
    {
      DrFreeComboBox(*(HWND *)(v6 + 240));
      DrFillFriendlyNames(v6);
    }
    else
    {
      if ( (unsigned int)DrFindAndSubclassClbNumbersControls((HANDLE)v6) )
      {
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a2 + 24LL) + 28LL) = 1168;
        EndDialog(hWnd, 0);
        return 1;
      }
      v29 = *(_QWORD *)(v6 + 168);
      if ( *(_DWORD *)(v29 + 184) )
        *(_DWORD *)(v29 + 176) = 0;
      *(_DWORD *)(v6 + 176) = *(_DWORD *)(*(_QWORD *)(v6 + 168) + 176LL);
      DrFillNumbersList(v6);
    }
    if ( (a2[8] & 8) != 0 )
      DrFillLocationList(v6);
  }
  if ( !*(_QWORD *)(v6 + 216) )
    CoCreateInstance(&CLSID_NetConnectionUiUtilities, 0, 1u, &IID_INetConnectionUiUtilities, (LPVOID *)(v6 + 216));
  v30 = *(_DWORD *)(*(_QWORD *)a2 + 392LL) == 0;
  if ( !*(_DWORD *)(v6 + 224) || (v31 = 1, v8) )
    v31 = 0;
  SendMessageW(*(HWND *)(v6 + 96), 0x160Cu, 0, v31);
  if ( *(_DWORD *)(*(_QWORD *)a2 + 392LL) && *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a2 + 168LL) + 24LL) )
    v30 = 1;
  EnableWindow(*(HWND *)(v6 + 96), v30);
  if ( *(_DWORD *)(*(_QWORD *)a2 + 392LL) )
  {
    v32 = GetDlgItem(hWnd, 1592);
    EnableWindow(v32, 0);
    ShowWindow(v32, 0);
  }
  PositionDlg(hWnd);
  CenterExpandWindowRemainLeftMargin(*(HWND *)(v6 + 104), hWnd, *(HWND *)(v6 + 16));
  return v2;
}

```

## disassembly

```asm
0x18000bd74  mov     [rsp-8+arg_10], rbx
0x18000bd79  push    rbp
0x18000bd7a  push    rsi
0x18000bd7b  push    rdi
0x18000bd7c  push    r12
0x18000bd7e  push    r13
0x18000bd80  push    r14
0x18000bd82  push    r15
0x18000bd84  lea     rbp, [rsp-190h]
0x18000bd8c  sub     rsp, 290h
0x18000bd93  mov     rax, cs:__security_cookie
0x18000bd9a  xor     rax, rsp
0x18000bd9d  mov     [rbp+1C0h+var_40], rax
0x18000bda4  mov     r13d, 1
0x18000bdaa  mov     r14, rcx
0x18000bdad  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000bdb3  or      r15d, 0FFFFFFFFh
0x18000bdb7  mov     [rsp+2C0h+var_280], r13d
0x18000bdbc  mov     rsi, rdx
0x18000bdbf  lea     r12d, [r13+0Bh]
0x18000bdc3  cmp     ecx, r15d
0x18000bdc6  jz      short loc_18000BDD8
0x18000bdc8  lea     r8, aDrinit; "DrInit"
0x18000bdcf  mov     edx, r12d; dwFlags
0x18000bdd2  call    cs:__imp_TracePrintfExA
0x18000bdd8  xor     ebx, ebx
0x18000bdda  test    rsi, rsi
0x18000bddd  jz      loc_18000C528
0x18000bde3  test    r14, r14
0x18000bde6  jz      loc_18000C528
0x18000bdec  mov     rcx, r14; hWnd
0x18000bdef  call    SetSmallAndBigIcon
0x18000bdf4  mov     edx, 0F8h; dwBytes
0x18000bdf9  lea     ecx, [rbx+40h]; uFlags
0x18000bdfc  call    cs:__imp_GlobalAlloc
0x18000be02  mov     rdi, rax
0x18000be05  test    rax, rax
0x18000be08  jnz     short loc_18000BE3E
0x18000be0a  mov     dword ptr [rsp+2C0h+Arguments], 0FAh; UINT
0x18000be12  lea     r8d, [rbx+8]; dwMessageId
0x18000be16  xor     r9d, r9d
0x18000be19  mov     [rsp+2C0h+nSize], 169h; UINT
0x18000be21  mov     edx, 13Eh; uID
0x18000be26  mov     rcx, r14; hWnd
0x18000be29  call    ErrorDlgUtil
0x18000be2e  xor     edx, edx; nResult
0x18000be30  mov     rcx, r14; hDlg
0x18000be33  call    cs:__imp_EndDialog
0x18000be39  jmp     loc_18000C528
0x18000be3e  xor     edx, edx; Val
0x18000be40  mov     r8d, 0F8h; Size
0x18000be46  mov     rcx, rdi; void *
0x18000be49  call    memset_0
0x18000be4e  mov     [rdi], rsi
0x18000be51  mov     r8, rdi; dwNewLong
0x18000be54  mov     [rdi+8], r14
0x18000be58  mov     edx, 10h; nIndex
0x18000be5d  mov     [rdi+0B0h], r15d
0x18000be64  mov     rax, [rsi]
0x18000be67  mov     ecx, [rax+1DCh]
0x18000be6d  mov     [rdi+0E4h], ecx
0x18000be73  mov     rcx, r14; hWnd
0x18000be76  call    cs:__imp_SetWindowLongPtrW
0x18000be7c  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000be82  cmp     ecx, r15d
0x18000be85  jz      short loc_18000BE97
0x18000be87  lea     r8, aContextSet; "Context set"
0x18000be8e  mov     edx, r12d; dwFlags
0x18000be91  call    cs:__imp_TracePrintfExA
0x18000be97  mov     rax, [rsi]
0x18000be9a  mov     edx, 44Ch; nIDDlgItem
0x18000be9f  mov     rcx, r14; hDlg
0x18000bea2  mov     r15, [rax+1B8h]
0x18000bea9  mov     r12d, [r15+224h]
0x18000beb0  call    cs:__imp_GetDlgItem
0x18000beb6  mov     [rdi+68h], rax
0x18000beba  test    byte ptr [rsi+8], 11h
0x18000bebe  jz      loc_18000BFAE
0x18000bec4  mov     edx, 450h; nIDDlgItem
0x18000bec9  mov     rcx, r14; hDlg
0x18000becc  call    cs:__imp_GetDlgItem
0x18000bed2  mov     [rdi+10h], rax
0x18000bed6  test    [rsi+8], r13b
0x18000beda  jz      loc_18000BF96
0x18000bee0  mov     edx, 44Fh; nIDDlgItem
0x18000bee5  mov     rcx, r14; hDlg
0x18000bee8  call    cs:__imp_GetDlgItem
0x18000beee  mov     edx, 44Dh; nIDDlgItem
0x18000bef3  mov     rcx, r14; hDlg
0x18000bef6  mov     [rdi+18h], rax
0x18000befa  call    cs:__imp_GetDlgItem
0x18000bf00  mov     edx, 656h; nIDDlgItem
0x18000bf05  mov     rcx, r14; hDlg
0x18000bf08  mov     [rdi+28h], rax
0x18000bf0c  call    cs:__imp_GetDlgItem
0x18000bf12  mov     edx, 657h; nIDDlgItem
0x18000bf17  mov     rcx, r14; hDlg
0x18000bf1a  mov     [rdi+30h], rax
0x18000bf1e  call    cs:__imp_GetDlgItem
0x18000bf24  mov     edx, 666h; nIDDlgItem
0x18000bf29  mov     rcx, r14; hDlg
0x18000bf2c  mov     [rdi+38h], rax
0x18000bf30  call    cs:__imp_GetDlgItem
0x18000bf36  mov     [rdi+70h], rax
0x18000bf3a  test    rax, rax
0x18000bf3d  jz      short loc_18000BF96
0x18000bf3f  xor     eax, eax
0x18000bf41  lea     rcx, [rsp+2C0h+psii+4]; void *
0x18000bf46  xor     edx, edx; Val
0x18000bf48  mov     dword ptr [rsp+2C0h+psii+4], eax
0x18000bf4c  mov     r8d, 218h; Size
0x18000bf52  call    memset_0
0x18000bf57  lea     r8, [rsp+2C0h+psii]; psii
0x18000bf5c  mov     [rsp+2C0h+psii.cbSize], 220h
0x18000bf64  mov     edx, 101h; uFlags
0x18000bf69  mov     ecx, 4Dh ; 'M'; siid
0x18000bf6e  call    cs:__imp_SHGetStockIconInfo
0x18000bf74  test    eax, eax
0x18000bf76  js      short loc_18000BF96
0x18000bf78  mov     r8, [rsp+2C0h+psii.hIcon]; wParam
0x18000bf7d  xor     r9d, r9d; lParam
0x18000bf80  mov     rcx, [rdi+70h]; hWnd
0x18000bf84  mov     edx, 170h; Msg
0x18000bf89  mov     [rdi+98h], r8
0x18000bf90  call    cs:__imp_SendMessageW
0x18000bf96  test    byte ptr [rsi+8], 2
0x18000bf9a  jz      short loc_18000BFAE
0x18000bf9c  mov     edx, 44Eh; nIDDlgItem
0x18000bfa1  mov     rcx, r14; hDlg
0x18000bfa4  call    cs:__imp_GetDlgItem
0x18000bfaa  mov     [rdi+20h], rax
0x18000bfae  test    byte ptr [rsi+8], 4
0x18000bfb2  jz      loc_18000C06F
0x18000bfb8  mov     edx, 588h; nIDDlgItem
0x18000bfbd  mov     rcx, r14; hDlg
0x18000bfc0  call    cs:__imp_GetDlgItem
0x18000bfc6  mov     edx, 579h; nIDDlgItem
0x18000bfcb  mov     rcx, r14; hDlg
0x18000bfce  mov     [rdi+40h], rax
0x18000bfd2  call    cs:__imp_GetDlgItem
0x18000bfd8  xor     edx, edx; nCmdShow
0x18000bfda  mov     [rdi+0F0h], rax
0x18000bfe1  test    r12d, r12d
0x18000bfe4  jz      short loc_18000BFF6
0x18000bfe6  mov     rcx, [rdi+40h]; hWnd
0x18000bfea  call    cs:__imp_ShowWindow
0x18000bff0  mov     rcx, [rdi+40h]
0x18000bff4  jmp     short loc_18000C006
0x18000bff6  mov     rcx, rax; hWnd
0x18000bff9  call    cs:__imp_ShowWindow
0x18000bfff  mov     rcx, [rdi+0F0h]; hWnd
0x18000c006  xor     edx, edx; bEnable
0x18000c008  call    cs:__imp_EnableWindow
0x18000c00e  cmp     dword ptr [r15+18h], 2
0x18000c013  mov     rcx, r14; hDlg
0x18000c016  mov     edx, 584h
0x18000c01b  jz      short loc_18000C022
0x18000c01d  mov     edx, 59Dh; nIDDlgItem
0x18000c022  call    cs:__imp_GetDlgItem
0x18000c028  mov     rcx, rax; hWnd
0x18000c02b  xor     edx, edx; nCmdShow
0x18000c02d  call    cs:__imp_ShowWindow
0x18000c033  test    byte ptr [rsi+8], 8
0x18000c037  jz      short loc_18000C06F
0x18000c039  mov     edx, 587h; nIDDlgItem
0x18000c03e  mov     rcx, r14; hDlg
0x18000c041  call    cs:__imp_GetDlgItem
0x18000c047  mov     edx, 586h; nIDDlgItem
0x18000c04c  mov     rcx, r14; hDlg
0x18000c04f  mov     [rdi+48h], rax
0x18000c053  call    cs:__imp_GetDlgItem
0x18000c059  mov     edx, 454h; nIDDlgItem
0x18000c05e  mov     rcx, r14; hDlg
0x18000c061  mov     [rdi+50h], rax
0x18000c065  call    cs:__imp_GetDlgItem
0x18000c06b  mov     [rdi+58h], rax
0x18000c06f  mov     edx, 453h; nIDDlgItem
0x18000c074  mov     rcx, r14; hDlg
0x18000c077  call    cs:__imp_GetDlgItem
0x18000c07d  mov     [rdi+60h], rax
0x18000c081  mov     rax, [rsi]
0x18000c084  mov     rcx, [rax+20h]
0x18000c088  mov     eax, ebx
0x18000c08a  cmp     [rcx+8], ebx
0x18000c08d  setz    al
0x18000c090  mov     [rdi+0E0h], eax
0x18000c096  test    byte ptr [rsi+8], 8
0x18000c09a  jz      short loc_18000C0BE
0x18000c09c  lea     rdx, [rdi+90h]
0x18000c0a3  mov     r8, r14
0x18000c0a6  call    TapiNoLocationDlg
0x18000c0ab  test    eax, eax
0x18000c0ad  jz      short loc_18000C0BE
0x18000c0af  mov     rax, [rsi]
0x18000c0b2  mov     rcx, [rax+18h]
0x18000c0b6  mov     [rcx+1Ch], ebx
0x18000c0b9  jmp     loc_18000BE2E
0x18000c0be  mov     rax, [rsi]
0x18000c0c1  mov     qword ptr [rsp+2C0h+Buffer], rbx
0x18000c0c6  mov     [rsp+2C0h+var_270], rbx
0x18000c0cb  cmp     [rax+18Ch], ebx
0x18000c0d1  jz      short loc_18000C0E6
0x18000c0d3  mov     rcx, cs:g_hinstDll; hInstance
0x18000c0da  mov     edx, 636h; uID
0x18000c0df  call    PszFromId
0x18000c0e4  jmp     short loc_18000C0EE
0x18000c0e6  mov     rcx, r14; hWnd
0x18000c0e9  call    GetText
0x18000c0ee  mov     rbx, rax
0x18000c0f1  test    rax, rax
0x18000c0f4  jz      short loc_18000C15C
0x18000c0f6  mov     rax, [r15+8]
0x18000c0fa  xor     r9d, r9d; dwLanguageId
0x18000c0fd  mov     [rsp+2C0h+var_270], rax
0x18000c102  xor     r8d, r8d; dwMessageId
0x18000c105  lea     rax, [rsp+2C0h+var_270]
0x18000c10a  mov     qword ptr [rsp+2C0h+Buffer], 0
0x18000c113  mov     [rsp+2C0h+Arguments], rax; Arguments
0x18000c118  mov     rdx, rbx; lpSource
0x18000c11b  lea     rax, [rsp+2C0h+Buffer]
0x18000c120  mov     [rsp+2C0h+nSize], r13d; nSize
0x18000c125  mov     ecx, 2500h; dwFlags
0x18000c12a  mov     [rsp+2C0h+lpBuffer], rax; lpBuffer
0x18000c12f  call    cs:__imp_FormatMessageW
0x18000c135  mov     rcx, rbx; hMem
0x18000c138  call    cs:__imp_GlobalFree
0x18000c13e  mov     rdx, qword ptr [rsp+2C0h+Buffer]; lpString
0x18000c143  test    rdx, rdx
0x18000c146  jz      short loc_18000C15C
0x18000c148  mov     rcx, r14; hWnd
0x18000c14b  call    cs:__imp_SetWindowTextW
0x18000c151  mov     rcx, qword ptr [rsp+2C0h+Buffer]; hMem
0x18000c156  call    cs:__imp_LocalFree
0x18000c15c  cmp     [r15+18h], r13d
0x18000c160  jz      short loc_18000C1A3
0x18000c162  mov     rcx, cs:g_hinstDll; hInstance
0x18000c169  mov     edx, 202h; uID
0x18000c16e  call    PszFromId
0x18000c173  xor     r15d, r15d
0x18000c176  mov     rbx, rax
0x18000c179  test    rax, rax
0x18000c17c  jz      short loc_18000C1A6
0x18000c17e  mov     edx, 636h; nIDDlgItem
0x18000c183  mov     rcx, r14; hDlg
0x18000c186  call    cs:__imp_GetDlgItem
0x18000c18c  mov     rcx, rax; hWnd
0x18000c18f  mov     rdx, rbx; lpString
0x18000c192  call    cs:__imp_SetWindowTextW
0x18000c198  mov     rcx, rbx; hMem
0x18000c19b  call    cs:__imp_GlobalFree
0x18000c1a1  jmp     short loc_18000C1A6
0x18000c1a3  xor     r15d, r15d
0x18000c1a6  test    [rsi+8], r13b
0x18000c1aa  jz      loc_18000C34A
0x18000c1b0  mov     rcx, [rdi+10h]; hWnd
0x18000c1b4  mov     ebx, 100h
0x18000c1b9  xor     r9d, r9d; lParam
0x18000c1bc  mov     r8d, ebx; wParam
0x18000c1bf  lea     edx, [rbx-3Bh]; Msg
0x18000c1c2  call    cs:__imp_SendMessageW
0x18000c1c8  mov     rdx, [rsi]
0x18000c1cb  mov     rcx, [rdi+10h]; hWnd
0x18000c1cf  add     rdx, 5F2h; lpString
0x18000c1d6  call    cs:__imp_SetWindowTextW
0x18000c1dc  mov     rcx, [rdi+18h]; hWnd
0x18000c1e0  mov     r8d, ebx; wParam
0x18000c1e3  xor     r9d, r9d; lParam
0x18000c1e6  lea     ebx, [r8-3Bh]
0x18000c1ea  mov     edx, ebx; Msg
0x18000c1ec  call    cs:__imp_SendMessageW
0x18000c1f2  test    byte ptr [rsi+8], 2
0x18000c1f6  jz      short loc_18000C21F
0x18000c1f8  mov     rcx, [rdi+20h]; hWnd
0x18000c1fc  xor     r9d, r9d; lParam
0x18000c1ff  mov     edx, ebx; Msg
0x18000c201  lea     r8d, [r9+0Fh]; wParam
0x18000c205  call    cs:__imp_SendMessageW
0x18000c20b  mov     rdx, [rsi]
0x18000c20e  mov     rcx, [rdi+20h]; hWnd
0x18000c212  add     rdx, 9F6h; lpString
0x18000c219  call    cs:__imp_SetWindowTextW
0x18000c21f  mov     rax, [rsi]
0x18000c222  cmp     [rax+188h], r15d
0x18000c229  jnz     loc_18000C2FB
0x18000c22f  cmp     [rax+1C8h], r15d
0x18000c236  jnz     loc_18000C2FB
0x18000c23c  mov     rcx, [rdi+18h]; hWnd
0x18000c240  xor     r9d, r9d; lParam
0x18000c243  xor     r8d, r8d; wParam
0x18000c246  mov     edx, 0D2h; Msg
0x18000c24b  call    cs:__imp_SendMessageW
0x18000c251  mov     [rdi+78h], ax
0x18000c255  test    ax, ax
0x18000c258  jnz     short loc_18000C260
0x18000c25a  mov     word ptr [rdi+78h], 25CFh
0x18000c260  lea     r8, [rdi+88h]
0x18000c267  mov     edx, r13d
0x18000c26a  mov     rcx, r14; hWnd
0x18000c26d  call    DrGetFriendlyFont
0x18000c272  lea     r8, [rdi+80h]
  ... truncated ...
```
