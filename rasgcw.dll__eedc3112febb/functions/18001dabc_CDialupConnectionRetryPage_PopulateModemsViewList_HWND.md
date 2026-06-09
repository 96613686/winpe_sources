# CDialupConnectionRetryPage::PopulateModemsViewList(HWND__ *)

- ea: `0x18001dabc`
- end: `0x18001e098`
- name: `?PopulateModemsViewList@CDialupConnectionRetryPage@@AEAAXPEAUHWND__@@@Z`
- size: `1500`
- prototype: `void __fastcall(CDialupConnectionRetryPage *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001e0a0`

## callees

- `0x180010c38`
- `0x1800116e4`
- `0x18001dabc`
- `0x18002b970`
- `0x18002c1b0`
- `0x18002ec04`
- `0x18002ed4c`
- `0x18002f382`
- `0x18002f3b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001db40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dde3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001de3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001db40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dde3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001de3c`
- `USER32!GetClientRect` at `0x18001db29`
- `USER32!GetClientRect` at `0x18001db29`
- `USER32!LoadImageW` at `0x18001ddaf`
- `USER32!LoadImageW` at `0x18001ddaf`
- `USER32!SendMessageW` at `0x18001dbbe`
- `USER32!SendMessageW` at `0x18001dbdc`
- `USER32!SendMessageW` at `0x18001dc30`
- `USER32!SendMessageW` at `0x18001dca0`
- `USER32!SendMessageW` at `0x18001dcb8`
- `USER32!SendMessageW` at `0x18001dedc`
- `USER32!SendMessageW` at `0x18001df23`
- `USER32!SendMessageW` at `0x18001df69`
- `USER32!SendMessageW` at `0x18001dffe`
- `USER32!SendMessageW` at `0x18001e016`
- `USER32!SendMessageW` at `0x18001e055`
- `USER32!SendMessageW` at `0x18001e06f`
- `USER32!SendMessageW` at `0x18001dbbe`
- `USER32!SendMessageW` at `0x18001dbdc`
- `USER32!SendMessageW` at `0x18001dc30`
- `USER32!SendMessageW` at `0x18001dca0`
- `USER32!SendMessageW` at `0x18001dcb8`
- `USER32!SendMessageW` at `0x18001dedc`
- `USER32!SendMessageW` at `0x18001df23`
- `USER32!SendMessageW` at `0x18001df69`
- `USER32!SendMessageW` at `0x18001dffe`
- `USER32!SendMessageW` at `0x18001e016`
- `USER32!SendMessageW` at `0x18001e055`
- `USER32!SendMessageW` at `0x18001e06f`
- `USER32!GetSystemMetrics` at `0x18001dc15`
- `USER32!GetSystemMetrics` at `0x18001dc5e`
- `USER32!GetSystemMetrics` at `0x18001dc6b`
- `USER32!GetSystemMetrics` at `0x18001dd62`
- `USER32!GetSystemMetrics` at `0x18001dd6f`
- `USER32!GetSystemMetrics` at `0x18001dc15`
- `USER32!GetSystemMetrics` at `0x18001dc5e`
- `USER32!GetSystemMetrics` at `0x18001dc6b`
- `USER32!GetSystemMetrics` at `0x18001dd62`
- `USER32!GetSystemMetrics` at `0x18001dd6f`
- `rtutils!TracePrintfExA` at `0x18001db58`
- `rtutils!TracePrintfExA` at `0x18001dc56`
- `rtutils!TracePrintfExA` at `0x18001dcd8`
- `rtutils!TracePrintfExA` at `0x18001de2b`
- `rtutils!TracePrintfExA` at `0x18001de57`
- `rtutils!TracePrintfExA` at `0x18001dfb5`
- `rtutils!TracePrintfExA` at `0x18001dfea`
- `rtutils!TracePrintfExA` at `0x18001db58`
- `rtutils!TracePrintfExA` at `0x18001dc56`
- `rtutils!TracePrintfExA` at `0x18001dcd8`
- `rtutils!TracePrintfExA` at `0x18001de2b`
- `rtutils!TracePrintfExA` at `0x18001de57`
- `rtutils!TracePrintfExA` at `0x18001dfb5`
- `rtutils!TracePrintfExA` at `0x18001dfea`

## string_xrefs

- `0x18001dccf`: `Failed to create an image list for list view.`
- `0x18001de1f`: `Unable to replace button %d images. hr = %#x`

## pseudocode

```c
void __fastcall CDialupConnectionRetryPage::PopulateModemsViewList(CDialupConnectionRetryPage *this, HWND a2)
{
  bool v3; // cc
  DWORD LastError; // eax
  signed int v5; // ebx
  int v6; // r14d
  HWND v7; // rcx
  int v8; // ebx
  int SystemMetrics; // eax
  HWND v10; // rcx
  int v11; // ebx
  int v12; // eax
  HIMAGELIST v13; // rax
  struct _IMAGELIST *v14; // r12
  unsigned int v15; // r13d
  unsigned int v16; // esi
  int v17; // ebx
  int v18; // eax
  __int64 v19; // r15
  HICON ImageW; // rax
  DWORD v21; // eax
  HWND v22; // rbx
  int v23; // eax
  DWORD v24; // eax
  unsigned __int16 *StringPcch; // rax
  HWND v26; // rcx
  int v27; // ebx
  HWND v28; // rcx
  HWND v29; // rcx
  int v30; // eax
  unsigned int v31; // ecx
  WPARAM v32; // r8
  LPARAM *v33; // r9
  HWND v34; // rcx
  UINT v35; // edx
  HWND v36; // rcx
  int v37; // eax
  HWND hWnd; // [rsp+30h] [rbp-D0h]
  int v39; // [rsp+38h] [rbp-C8h]
  int v40; // [rsp+40h] [rbp-C0h] BYREF
  int v41; // [rsp+44h] [rbp-BCh] BYREF
  LPARAM *v42; // [rsp+58h] [rbp-A8h]
  int v43; // [rsp+64h] [rbp-9Ch]
  struct tagRECT Rect; // [rsp+A0h] [rbp-60h] BYREF
  LPARAM lParam[2]; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v46[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v47; // [rsp+E0h] [rbp-20h]
  WCHAR v48[264]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v49[264]; // [rsp+320h] [rbp+220h] BYREF

  v39 = 0;
  memset_0(&v40, 0, 0x58u);
  v3 = *((_DWORD *)this + 28) <= 4u;
  Rect = 0;
  if ( v3 )
  {
    v14 = 0;
    v6 = 0;
  }
  else
  {
    if ( !GetClientRect(*((HWND *)this + 11), &Rect) )
    {
      if ( g_dwTraceId != -1 )
      {
        LastError = GetLastError();
        TracePrintfExA(g_dwTraceId, 0xCu, "Failed to get client area size. Error = %d", LastError);
      }
      return;
    }
    v5 = 0;
    v6 = 1;
    do
    {
      v47 = 0;
      *(_OWORD *)lParam = 0;
      LODWORD(lParam[0]) = 10;
      memset(v46, 0, sizeof(v46));
      HIDWORD(v46[0]) = v5;
      v7 = (HWND)*((_QWORD *)this + 11);
      LODWORD(lParam[1]) = *((_DWORD *)&CDialupConnectionRetryPage::ListViewColumnWidths + v5)
                         * (Rect.right - Rect.left)
                         / 100;
      SendMessageW(v7, 0x1061u, v5++, (LPARAM)lParam);
    }
    while ( (unsigned int)v5 < 2 );
    if ( (unsigned int)SendMessageW(*((HWND *)this + 11), 0x108Eu, 4u, 0) == 1 )
    {
      v8 = Rect.right - Rect.left;
      v46[0] = 0x200000000uLL;
      lParam[0] = 0x300000028LL;
      lParam[1] = 1;
      SystemMetrics = GetSystemMetrics(2);
      v10 = (HWND)*((_QWORD *)this + 11);
      HIDWORD(lParam[1]) = v8 - SystemMetrics;
      if ( SendMessageW(v10, 0x10A2u, 0, (LPARAM)lParam) )
      {
        v39 = 1;
      }
      else if ( g_dwTraceId != -1 )
      {
        TracePrintfExA(g_dwTraceId, 0xCu, "Failed to set tile view info.");
      }
    }
    v11 = GetSystemMetrics(12);
    v12 = GetSystemMetrics(11);
    v13 = ImageList_Create(v12, v11, 0x21u, 10, 0);
    v14 = v13;
    if ( !v13 )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "Failed to create an image list for list view.");
      return;
    }
    SendMessageW(*((HWND *)this + 11), 0x1003u, 0, (LPARAM)v13);
    SendMessageW(*((HWND *)this + 11), 0x1036u, 0, 1088);
  }
  v15 = 0;
  hWnd = 0;
  v16 = 0;
  if ( *((_DWORD *)this + 28) )
  {
    while ( 1 )
    {
      memset_0(v48, 0, 0x20Au);
      memset_0(v49, 0, 0x20Au);
      if ( v6 )
      {
        memset_0(&v41, 0, 0x54u);
        v40 = 11;
      }
      else
      {
        hWnd = (HWND)*((_QWORD *)this + v16 + 7);
      }
      if ( !v14 && v6 )
        goto LABEL_48;
      v17 = GetSystemMetrics(12);
      v18 = GetSystemMetrics(11);
      v19 = 264LL * v16;
      ImageW = (HICON)LoadImageW(
                        hInst,
                        (LPCWSTR)(unsigned __int16)(*(_WORD *)(v19 + *((_QWORD *)this + 13) + 260) + 10001),
                        1u,
                        v18,
                        v17,
                        0x8000u);
      if ( !ImageW )
        break;
      if ( v6 )
      {
        v43 = ImageList_ReplaceIcon(v14, -1, ImageW);
        if ( v43 == -1 && g_dwTraceId != -1 )
        {
          v21 = GetLastError();
          TracePrintfExA(g_dwTraceId, 0xCu, "Failed to add icon to image list. Error = %d", v21);
        }
LABEL_33:
        v22 = hWnd;
        goto LABEL_34;
      }
      v22 = hWnd;
      v23 = HrReplaceAllImagesForCommandLinkButton(hWnd, ImageW, 0);
      if ( v23 < 0 && g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "Unable to replace button %d images. hr = %#x", v16 + 1051, v23);
LABEL_34:
      StringCchCopyW(v48, 0x105u, (unsigned __int16 *)(v19 + *((_QWORD *)this + 13)));
      StringPcch = (unsigned __int16 *)PszLoadStringPcch(hInst);
      StringCchCopyW(v49, 0x105u, StringPcch);
      if ( !v6 )
      {
        SendMessageW(v22, 0xCu, 0, (LPARAM)v48);
        v33 = (LPARAM *)v49;
        v32 = 0;
        v35 = 5641;
        v34 = v22;
LABEL_47:
        SendMessageW(v34, v35, v32, (LPARAM)v33);
        goto LABEL_48;
      }
      v26 = (HWND)*((_QWORD *)this + 11);
      v42 = (LPARAM *)v48;
      v27 = SendMessageW(v26, 0x104Du, 0, (LPARAM)&v40);
      v41 = v27;
      if ( v27 == -1 )
      {
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "Failed to insert item in list view. hr = %#x", -2147467259);
        goto LABEL_48;
      }
      memset_0(lParam, 0, 0x58u);
      v28 = (HWND)*((_QWORD *)this + 11);
      *((_QWORD *)&v46[0] + 1) = v49;
      LODWORD(lParam[1]) = 1;
      SendMessageW(v28, 0x1074u, v27, (LPARAM)lParam);
      if ( v39 )
      {
        v29 = (HWND)*((_QWORD *)this + 11);
        HIDWORD(lParam[0]) = v41;
        lParam[1] = 1;
        *(_QWORD *)&v46[0] = &CDialupConnectionRetryPage::ListViewColumns;
        *((_QWORD *)&v46[0] + 1) = 0;
        LODWORD(lParam[0]) = 32;
        if ( SendMessageW(v29, 0x10A4u, 0, (LPARAM)lParam) )
        {
          v30 = CompareStringWrapW(v48, (PCNZWCH)(*((_QWORD *)this + 12) + 4436LL));
          v31 = v16;
          if ( v30 )
            v31 = v15;
          v15 = v31;
          goto LABEL_48;
        }
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "Failed to set tile info. hr = %#x", -2147467259);
        v32 = SHIDWORD(lParam[0]);
        v33 = 0;
        v34 = (HWND)*((_QWORD *)this + 11);
        v35 = 4104;
        goto LABEL_47;
      }
LABEL_48:
      if ( ++v16 >= *((_DWORD *)this + 28) )
        goto LABEL_49;
    }
    if ( g_dwTraceId != -1 )
    {
      v24 = GetLastError();
      TracePrintfExA(g_dwTraceId, 0xCu, "Failed to load specified icon image. Error = %d", v24);
    }
    goto LABEL_33;
  }
LABEL_49:
  if ( v6 )
  {
    memset_0(lParam, 0, 0x58u);
    v36 = (HWND)*((_QWORD *)this + 11);
    LODWORD(v46[0]) = 3;
    HIDWORD(lParam[1]) = 3;
    v37 = SendMessageW(v36, 0x1004u, 0, 0);
    SendMessageW(*((HWND *)this + 11), 0x102Bu, v37 + ~v15, (LPARAM)lParam);
  }
}

```

## disassembly

```asm
0x18001dabc  push    rbp
0x18001dabe  push    rbx
0x18001dabf  push    rsi
0x18001dac0  push    rdi
0x18001dac1  push    r12
0x18001dac3  push    r13
0x18001dac5  push    r14
0x18001dac7  push    r15
0x18001dac9  lea     rbp, [rsp-448h]
0x18001dad1  sub     rsp, 548h
0x18001dad8  mov     rax, cs:__security_cookie
0x18001dadf  xor     rax, rsp
0x18001dae2  mov     [rbp+480h+var_50], rax
0x18001dae9  xor     r15d, r15d
0x18001daec  mov     rdi, rcx
0x18001daef  xor     edx, edx; Val
0x18001daf1  mov     [rsp+580h+var_548], r15d
0x18001daf6  lea     rcx, [rsp+580h+var_540]; void *
0x18001dafb  lea     r8d, [r15+58h]; Size
0x18001daff  call    memset_0
0x18001db04  or      r13d, 0FFFFFFFFh
0x18001db08  lea     esi, [r15+0Ch]
0x18001db0c  cmp     dword ptr [rdi+70h], 4
0x18001db10  lea     r12d, [r15+1]
0x18001db14  xorps   xmm0, xmm0
0x18001db17  movups  xmmword ptr [rbp+480h+Rect.left], xmm0
0x18001db1b  jbe     loc_18001DCE3
0x18001db21  mov     rcx, [rdi+58h]; hWnd
0x18001db25  lea     rdx, [rbp+480h+Rect]; lpRect
0x18001db29  call    cs:__imp_GetClientRect
0x18001db2f  test    eax, eax
0x18001db31  jnz     short loc_18001DB63
0x18001db33  cmp     cs:g_dwTraceId, r13d
0x18001db3a  jz      loc_18001E075
0x18001db40  call    cs:__imp_GetLastError
0x18001db46  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001db4c  lea     r8, aFailedToGetCli; "Failed to get client area size. Error ="...
0x18001db53  mov     r9d, eax
0x18001db56  mov     edx, esi; dwFlags
0x18001db58  call    cs:__imp_TracePrintfExA
0x18001db5e  jmp     loc_18001E075
0x18001db63  mov     ebx, r15d
0x18001db66  mov     r14d, r12d
0x18001db69  mov     ecx, [rbp+480h+Rect.right]
0x18001db6c  lea     r9, [rbp+480h+lParam]; lParam
0x18001db70  sub     ecx, [rbp+480h+Rect.left]
0x18001db73  xor     eax, eax
0x18001db75  mov     [rbp+480h+var_4A0], rax
0x18001db79  xorps   xmm0, xmm0
0x18001db7c  lea     rax, ?ListViewColumnWidths@CDialupConnectionRetryPage@@0QBHB; int const near * const CDialupConnectionRetryPage::ListViewColumnWidths
0x18001db83  movsxd  r8, ebx; wParam
0x18001db86  movups  xmmword ptr [rbp+480h+lParam], xmm0
0x18001db8a  mov     dword ptr [rbp+480h+lParam], 0Ah
0x18001db91  movups  [rbp+480h+var_4C0], xmm0
0x18001db95  mov     dword ptr [rbp+480h+var_4C0+0Ch], ebx
0x18001db98  imul    ecx, [rax+r8*4]
0x18001db9d  mov     eax, 51EB851Fh
0x18001dba2  movups  [rbp+480h+var_4B0], xmm0
0x18001dba6  imul    ecx
0x18001dba8  mov     rcx, [rdi+58h]; hWnd
0x18001dbac  sar     edx, 5
0x18001dbaf  mov     eax, edx
0x18001dbb1  shr     eax, 1Fh
0x18001dbb4  add     edx, eax
0x18001dbb6  mov     dword ptr [rbp+480h+lParam+8], edx
0x18001dbb9  mov     edx, 1061h; Msg
0x18001dbbe  call    cs:__imp_SendMessageW
0x18001dbc4  add     ebx, r12d
0x18001dbc7  cmp     ebx, 2
0x18001dbca  jb      short loc_18001DB69
0x18001dbcc  mov     rcx, [rdi+58h]; hWnd
0x18001dbd0  xor     r9d, r9d; lParam
0x18001dbd3  mov     edx, 108Eh; Msg
0x18001dbd8  lea     r8d, [r9+4]; wParam
0x18001dbdc  call    cs:__imp_SendMessageW
0x18001dbe2  cmp     eax, r12d
0x18001dbe5  jnz     short loc_18001DC5C
0x18001dbe7  mov     ebx, [rbp+480h+Rect.right]
0x18001dbea  mov     eax, 2
0x18001dbef  sub     ebx, [rbp+480h+Rect.left]
0x18001dbf2  xorps   xmm0, xmm0
0x18001dbf5  mov     ecx, eax; nIndex
0x18001dbf7  mov     [rbp+480h+lParam+0Ch], r15
0x18001dbfb  movdqu  [rbp+480h+var_4C0+8], xmm0
0x18001dc00  mov     dword ptr [rbp+480h+lParam], 28h ; '('
0x18001dc07  mov     dword ptr [rbp+480h+var_4C0+4], eax
0x18001dc0a  mov     dword ptr [rbp+480h+lParam+4], 3
0x18001dc11  mov     dword ptr [rbp+480h+lParam+8], r12d
0x18001dc15  call    cs:__imp_GetSystemMetrics
0x18001dc1b  mov     rcx, [rdi+58h]; hWnd
0x18001dc1f  lea     r9, [rbp+480h+lParam]; lParam
0x18001dc23  sub     ebx, eax
0x18001dc25  xor     r8d, r8d; wParam
0x18001dc28  mov     edx, 10A2h; Msg
0x18001dc2d  mov     dword ptr [rbp+480h+lParam+0Ch], ebx
0x18001dc30  call    cs:__imp_SendMessageW
0x18001dc36  test    rax, rax
0x18001dc39  jz      short loc_18001DC42
0x18001dc3b  mov     [rsp+580h+var_548], r12d
0x18001dc40  jmp     short loc_18001DC5C
0x18001dc42  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001dc48  cmp     ecx, r13d
0x18001dc4b  jz      short loc_18001DC5C
0x18001dc4d  lea     r8, aFailedToSetTil_0; "Failed to set tile view info."
0x18001dc54  mov     edx, esi; dwFlags
0x18001dc56  call    cs:__imp_TracePrintfExA
0x18001dc5c  mov     ecx, esi; nIndex
0x18001dc5e  call    cs:__imp_GetSystemMetrics
0x18001dc64  mov     ecx, 0Bh; nIndex
0x18001dc69  mov     ebx, eax
0x18001dc6b  call    cs:__imp_GetSystemMetrics
0x18001dc71  mov     r9d, 0Ah; cInitial
0x18001dc77  mov     [rsp+580h+cGrow], r15d; cGrow
0x18001dc7c  mov     edx, ebx; cy
0x18001dc7e  mov     ecx, eax; cx
0x18001dc80  lea     r8d, [r9+17h]; flags
0x18001dc84  call    ImageList_Create
0x18001dc89  mov     r12, rax
0x18001dc8c  test    rax, rax
0x18001dc8f  jz      short loc_18001DCC0
0x18001dc91  mov     rcx, [rdi+58h]; hWnd
0x18001dc95  mov     r9, rax; lParam
0x18001dc98  xor     r8d, r8d; wParam
0x18001dc9b  mov     edx, 1003h; Msg
0x18001dca0  call    cs:__imp_SendMessageW
0x18001dca6  mov     rcx, [rdi+58h]; hWnd
0x18001dcaa  mov     r9d, 440h; lParam
0x18001dcb0  xor     r8d, r8d; wParam
0x18001dcb3  mov     edx, 1036h; Msg
0x18001dcb8  call    cs:__imp_SendMessageW
0x18001dcbe  jmp     short loc_18001DCE9
0x18001dcc0  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001dcc6  cmp     ecx, r13d
0x18001dcc9  jz      loc_18001E075
0x18001dccf  lea     r8, aFailedToCreate; "Failed to create an image list for list"...
0x18001dcd6  mov     edx, esi; dwFlags
0x18001dcd8  call    cs:__imp_TracePrintfExA
0x18001dcde  jmp     loc_18001E075
0x18001dce3  mov     r12, r15
0x18001dce6  mov     r14d, r15d
0x18001dce9  mov     r13d, r15d
0x18001dcec  mov     [rsp+580h+hWnd], r15
0x18001dcf1  mov     esi, r15d
0x18001dcf4  cmp     [rdi+70h], r15d
0x18001dcf8  jbe     loc_18001E027
0x18001dcfe  xor     edx, edx; Val
0x18001dd00  lea     rcx, [rbp+480h+var_470]; void *
0x18001dd04  mov     r8d, 20Ah; Size
0x18001dd0a  call    memset_0
0x18001dd0f  xor     edx, edx; Val
0x18001dd11  lea     rcx, [rbp+480h+var_260]; void *
0x18001dd18  mov     r8d, 20Ah; Size
0x18001dd1e  call    memset_0
0x18001dd23  mov     r15d, esi
0x18001dd26  test    r14d, r14d
0x18001dd29  jz      short loc_18001DD45
0x18001dd2b  xor     edx, edx; Val
0x18001dd2d  lea     rcx, [rsp+580h+var_540+4]; void *
0x18001dd32  lea     r8d, [rdx+54h]; Size
0x18001dd36  call    memset_0
0x18001dd3b  mov     dword ptr [rsp+580h+var_540], 0Bh
0x18001dd43  jmp     short loc_18001DD4F
0x18001dd45  mov     rax, [rdi+r15*8+38h]
0x18001dd4a  mov     [rsp+580h+hWnd], rax
0x18001dd4f  test    r12, r12
0x18001dd52  jnz     short loc_18001DD5D
0x18001dd54  test    r14d, r14d
0x18001dd57  jnz     loc_18001E01C
0x18001dd5d  mov     ecx, 0Ch; nIndex
0x18001dd62  call    cs:__imp_GetSystemMetrics
0x18001dd68  mov     ecx, 0Bh; nIndex
0x18001dd6d  mov     ebx, eax
0x18001dd6f  call    cs:__imp_GetSystemMetrics
0x18001dd75  mov     rdx, [rdi+68h]
0x18001dd79  mov     r8d, 2711h
0x18001dd7f  mov     rcx, cs:hInst; hInst
0x18001dd86  mov     r9d, eax; cx
0x18001dd89  imul    r15, 108h
0x18001dd90  mov     [rsp+580h+fuLoad], 8000h; fuLoad
0x18001dd98  mov     [rsp+580h+cGrow], ebx; cy
0x18001dd9c  add     r8w, [r15+rdx+104h]
0x18001dda5  movzx   edx, r8w; name
0x18001dda9  mov     r8d, 1; type
0x18001ddaf  call    cs:__imp_LoadImageW
0x18001ddb5  test    rax, rax
0x18001ddb8  jz      short loc_18001DE33
0x18001ddba  test    r14d, r14d
0x18001ddbd  jz      short loc_18001DDF2
0x18001ddbf  mov     r8, rax; hicon
0x18001ddc2  or      edx, 0FFFFFFFFh; i
0x18001ddc5  mov     rcx, r12; himl
0x18001ddc8  call    ImageList_ReplaceIcon
0x18001ddcd  mov     [rsp+580h+var_51C], eax
0x18001ddd1  cmp     eax, 0FFFFFFFFh
0x18001ddd4  jnz     loc_18001DE5D
0x18001ddda  cmp     cs:g_dwTraceId, 0FFFFFFFFh
0x18001dde1  jz      short loc_18001DE5D
0x18001dde3  call    cs:__imp_GetLastError
0x18001dde9  lea     r8, aFailedToAddIco; "Failed to add icon to image list. Error"...
0x18001ddf0  jmp     short loc_18001DE49
0x18001ddf2  mov     rbx, [rsp+580h+hWnd]
0x18001ddf7  xor     r8d, r8d
0x18001ddfa  mov     rcx, rbx; hWnd
0x18001ddfd  mov     rdx, rax; hicon
0x18001de00  call    HrReplaceAllImagesForCommandLinkButton
0x18001de05  test    eax, eax
0x18001de07  jns     short loc_18001DE62
0x18001de09  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001de0f  cmp     ecx, 0FFFFFFFFh
0x18001de12  jz      short loc_18001DE62
0x18001de14  lea     r9d, [rsi+41Bh]
0x18001de1b  mov     [rsp+580h+cGrow], eax
0x18001de1f  lea     r8, aUnableToReplac; "Unable to replace button %d images. hr "...
0x18001de26  mov     edx, 0Ch; dwFlags
0x18001de2b  call    cs:__imp_TracePrintfExA
0x18001de31  jmp     short loc_18001DE62
0x18001de33  cmp     cs:g_dwTraceId, 0FFFFFFFFh
0x18001de3a  jz      short loc_18001DE5D
0x18001de3c  call    cs:__imp_GetLastError
0x18001de42  lea     r8, aFailedToLoadSp; "Failed to load specified icon image. Er"...
0x18001de49  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001de4f  mov     r9d, eax
0x18001de52  mov     edx, 0Ch; dwFlags
0x18001de57  call    cs:__imp_TracePrintfExA
0x18001de5d  mov     rbx, [rsp+580h+hWnd]
0x18001de62  mov     r8, [rdi+68h]
0x18001de66  lea     rcx, [rbp+480h+var_470]; unsigned __int16 *
0x18001de6a  add     r8, r15; unsigned __int16 *
0x18001de6d  mov     edx, 105h; unsigned __int64
0x18001de72  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001de77  mov     rax, [rdi+68h]
0x18001de7b  lea     r8, [rsp+580h+var_544]
0x18001de80  mov     rcx, cs:hInst; hModule
0x18001de87  mov     [rsp+580h+var_544], 0
0x18001de8f  mov     edx, [r15+rax+104h]
0x18001de97  add     edx, 0C94h
0x18001de9d  call    PszLoadStringPcch
0x18001dea2  mov     r8, rax; unsigned __int16 *
0x18001dea5  lea     rcx, [rbp+480h+var_260]; unsigned __int16 *
0x18001deac  mov     edx, 105h; unsigned __int64
0x18001deb1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001deb6  xor     r8d, r8d; wParam
0x18001deb9  xor     r15d, r15d
0x18001debc  test    r14d, r14d
0x18001debf  jz      loc_18001DFF2
0x18001dec5  mov     rcx, [rdi+58h]; hWnd
0x18001dec9  lea     rax, [rbp+480h+var_470]
0x18001decd  lea     r9, [rsp+580h+var_540]; lParam
0x18001ded2  mov     [rsp+580h+var_528], rax
0x18001ded7  mov     edx, 104Dh; Msg
0x18001dedc  call    cs:__imp_SendMessageW
0x18001dee2  mov     rbx, rax
0x18001dee5  mov     dword ptr [rsp+580h+var_540+4], ebx
0x18001dee9  cmp     eax, 0FFFFFFFFh
0x18001deec  jz      loc_18001DFCD
0x18001def2  xor     edx, edx; Val
0x18001def4  lea     r8d, [r15+58h]; Size
0x18001def8  lea     rcx, [rbp+480h+lParam]; void *
0x18001defc  call    memset_0
0x18001df01  mov     rcx, [rdi+58h]; hWnd
0x18001df05  lea     rax, [rbp+480h+var_260]
0x18001df0c  movsxd  r8, ebx; wParam
0x18001df0f  lea     r9, [rbp+480h+lParam]; lParam
0x18001df13  mov     edx, 1074h; Msg
0x18001df18  mov     qword ptr [rbp+480h+var_4C0+8], rax
0x18001df1c  mov     dword ptr [rbp+480h+lParam+8], 1
0x18001df23  call    cs:__imp_SendMessageW
0x18001df29  cmp     [rsp+580h+var_548], r15d
0x18001df2e  jz      loc_18001E01C
0x18001df34  mov     eax, dword ptr [rsp+580h+var_540+4]
0x18001df38  lea     r9, [rbp+480h+lParam]; lParam
0x18001df3c  mov     rcx, [rdi+58h]; hWnd
0x18001df40  xor     r8d, r8d; wParam
0x18001df43  mov     dword ptr [rbp+480h+lParam+4], eax
0x18001df46  mov     edx, 10A4h; Msg
0x18001df4b  lea     rax, ?ListViewColumns@CDialupConnectionRetryPage@@0PAIA; uint near * CDialupConnectionRetryPage::ListViewColumns
0x18001df52  mov     [rbp+480h+lParam+8], 1
0x18001df5a  mov     qword ptr [rbp+480h+var_4C0], rax
0x18001df5e  mov     qword ptr [rbp+480h+var_4C0+8], r15
0x18001df62  mov     dword ptr [rbp+480h+lParam], 20h ; ' '
0x18001df69  call    cs:__imp_SendMessageW
0x18001df6f  test    rax, rax
0x18001df72  jz      short loc_18001DF98
0x18001df74  mov     rdx, [rdi+60h]
0x18001df78  lea     rcx, [rbp+480h+var_470]; lpString1
0x18001df7c  add     rdx, 1154h; lpString2
0x18001df83  call    CompareStringWrapW
0x18001df88  test    eax, eax
0x18001df8a  mov     ecx, esi
0x18001df8c  cmovnz  ecx, r13d
0x18001df90  mov     r13d, ecx
0x18001df93  jmp     loc_18001E01C
0x18001df98  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001df9e  cmp     ecx, 0FFFFFFFFh
0x18001dfa1  jz      short loc_18001DFBB
0x18001dfa3  mov     r9d, 80004005h
0x18001dfa9  lea     r8, aFailedToSetTil; "Failed to set tile info. hr = %#x"
0x18001dfb0  mov     edx, 0Ch; dwFlags
0x18001dfb5  call    cs:__imp_TracePrintfExA
0x18001dfbb  movsxd  r8, dword ptr [rbp+480h+lParam+4]
  ... truncated ...
```
