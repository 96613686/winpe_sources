# CToc::InitTreeView(void)

- ea: `0x1800197c8`
- end: `0x18001a08d`
- name: `?InitTreeView@CToc@@QEAAHXZ`
- size: `2245`
- prototype: `__int64 __fastcall(LONG_PTR dwNewLong)`
- caller_count: `5`
- callee_count: `27`
- tags: `broker_com_uri`

## callers

- `0x18001a608`
- `0x18001b530`
- `0x18001c520`
- `0x18002efa0`
- `0x180050a70`

## callees

- `0x180005a4c`
- `0x18000e64c`
- `0x180010b14`
- `0x180010fcc`
- `0x1800111d0`
- `0x180011b84`
- `0x1800131d4`
- `0x180013b20`
- `0x180019668`
- `0x1800197c8`
- `0x18001a448`
- `0x18001c9f8`
- `0x18001d42c`
- `0x18002cab4`
- `0x18002fb58`
- `0x18002fef8`
- `0x180037594`
- `0x18003a9e0`
- `0x180051cfc`
- `0x180051e00`
- `0x1800559d0`
- `0x1800661d0`
- `0x1800665d0`
- `0x180066f30`
- `0x180069e70`
- `0x180075c5a`
- `0x180075c90`

## import_xrefs

- `msvcrt!realloc` at `0x1800199ce`
- `msvcrt!realloc` at `0x1800199ce`
- `msvcrt!malloc` at `0x1800199bc`
- `msvcrt!malloc` at `0x1800199bc`
- `msvcrt!free` at `0x1800199e3`
- `msvcrt!free` at `0x180019aa3`
- `msvcrt!free` at `0x1800199e3`
- `msvcrt!free` at `0x180019aa3`
- `USER32!GetWindowDC` at `0x180019de6`
- `USER32!GetWindowDC` at `0x180019de6`
- `USER32!SetPropA` at `0x180019f3f`
- `USER32!SetPropA` at `0x180019f3f`
- `USER32!ReleaseDC` at `0x180019e34`
- `USER32!ReleaseDC` at `0x180019e34`
- `USER32!ShowWindow` at `0x18001a061`
- `USER32!ShowWindow` at `0x18001a061`
- `USER32!SetWindowLongPtrA` at `0x180019f24`
- `USER32!SetWindowLongPtrA` at `0x180019f24`
- `USER32!SetWindowPos` at `0x180019835`
- `USER32!SetWindowPos` at `0x180019835`
- `USER32!SendMessageA` at `0x18001995a`
- `USER32!SendMessageA` at `0x180019971`
- `USER32!SendMessageA` at `0x180019b26`
- `USER32!SendMessageA` at `0x180019f56`
- `USER32!SendMessageA` at `0x180019f9a`
- `USER32!SendMessageA` at `0x180019fba`
- `USER32!SendMessageA` at `0x18001a001`
- `USER32!SendMessageA` at `0x18001a019`
- `USER32!SendMessageA` at `0x18001995a`
- `USER32!SendMessageA` at `0x180019971`
- `USER32!SendMessageA` at `0x180019b26`
- `USER32!SendMessageA` at `0x180019f56`
- `USER32!SendMessageA` at `0x180019f9a`
- `USER32!SendMessageA` at `0x180019fba`
- `USER32!SendMessageA` at `0x18001a001`
- `USER32!SendMessageA` at `0x18001a019`
- `USER32!IsWindowUnicode` at `0x180019ee2`
- `USER32!IsWindowUnicode` at `0x180019ee2`
- `GDI32!GetObjectA` at `0x180019ea8`
- `GDI32!GetObjectA` at `0x180019ea8`
- `GDI32!GetNearestColor` at `0x180019e01`
- `GDI32!GetNearestColor` at `0x180019e12`
- `GDI32!GetNearestColor` at `0x180019e01`
- `GDI32!GetNearestColor` at `0x180019e12`
- `GDI32!CreateSolidBrush` at `0x180019e45`
- `GDI32!CreateSolidBrush` at `0x180019e45`

## pseudocode

```c
__int64 __fastcall CToc::InitTreeView(LONG_PTR dwNewLong)
{
  unsigned __int16 v2; // si
  const char *v3; // rcx
  int v4; // eax
  int v5; // r9d
  __int64 ImageA; // rax
  unsigned int ResourceInstance; // eax
  int v8; // r9d
  void *v9; // rbx
  CHHWinType *v10; // rcx
  int ContentCharset; // eax
  __int64 v12; // rcx
  int v13; // ebx
  LONG_PTR v14; // rax
  __int64 v15; // rbx
  __int64 v16; // rcx
  unsigned int CodePage; // edx
  const unsigned __int16 *WideStr; // rax
  unsigned int *v19; // rdx
  HDC v20; // r8
  unsigned __int16 *v21; // rsi
  int v22; // r9d
  HFONT AccessableContentFont; // r8
  CHHWinType *v24; // rcx
  __int64 v25; // r8
  LPARAM inserted; // r12
  int v27; // eax
  int v28; // r13d
  int v29; // esi
  __int64 v30; // rcx
  __int64 v31; // r14
  __int64 v32; // rbx
  __int64 v33; // r15
  int v34; // r9d
  int v35; // r14d
  struct SITE_ENTRY_URL *v36; // rax
  int v37; // r9d
  int v38; // edx
  int v39; // r9d
  __int64 v40; // rcx
  unsigned __int8 v41; // r10
  HWND v42; // rcx
  __int64 v43; // rax
  __int64 v44; // rax
  unsigned __int8 ImageNumber; // al
  HWND v46; // rcx
  HDC WindowDC; // rsi
  COLORREF NearestColor; // ebx
  COLORREF v49; // ecx
  const char *v50; // rcx
  struct CHtmlHelpControl *v51; // r9
  void *v52; // rcx
  BOOL v53; // ebx
  __int64 (*WndProc)(HWND, unsigned int, unsigned __int64, __int64); // rax
  HWND v55; // rcx
  __int64 v56; // rax
  __int64 v57; // rcx
  LPARAM v58; // r9
  __int64 v59; // rax
  __int64 v60; // rcx
  const char **v61; // rcx
  const char *v62; // rdx
  int cy; // [rsp+28h] [rbp-D8h]
  LPARAM lParam[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v66; // [rsp+50h] [rbp-B0h]
  __int64 v67; // [rsp+58h] [rbp-A8h]
  __int64 v68; // [rsp+68h] [rbp-98h]
  int v69; // [rsp+74h] [rbp-8Ch]
  int v70; // [rsp+78h] [rbp-88h]
  int v71; // [rsp+7Ch] [rbp-84h]
  __int64 v72; // [rsp+80h] [rbp-80h]
  __int128 pv; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v74; // [rsp+B0h] [rbp-50h]
  char v75[8]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v76[408]; // [rsp+C8h] [rbp-38h] BYREF

  v2 = 108;
  if ( g_RTL_Mirror_Style )
    v2 = 206;
  SetWindowPos(*(HWND *)(dwNewLong + 424), 0, 0, 0, 1, 1, 0x27u);
  if ( !*(_DWORD *)(dwNewLong + 480) )
  {
    v3 = *(const char **)(dwNewLong + 264);
    if ( v3 && !*(_DWORD *)(dwNewLong + 8) )
    {
      if ( *(_QWORD *)(dwNewLong + 496) )
        v4 = CHtmlHelpControl::ConvertToCacheFile(
               *(CHtmlHelpControl **)(dwNewLong + 496),
               *(const char **)(dwNewLong + 264),
               v75,
               0x104u);
      else
        v4 = ConvertToCacheFile(v3, v75, 0x104u);
      if ( v4 )
      {
        ImageA = IsolationAwareImageList_LoadImageA(
                   0,
                   (unsigned int)v75,
                   *(_DWORD *)(dwNewLong + 272),
                   v5,
                   *(_DWORD *)(dwNewLong + 280),
                   cy,
                   16);
        *(_QWORD *)(dwNewLong + 488) = ImageA;
        if ( ImageA )
          goto LABEL_15;
      }
      else
      {
        *(_QWORD *)(dwNewLong + 488) = 0;
      }
      FindMessageParent(*(HWND *)(dwNewLong + 424));
      AuthorMsg(0x1D805u, *(char **)(dwNewLong + 264));
    }
    ResourceInstance = (unsigned int)CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
    *(_QWORD *)(dwNewLong + 488) = IsolationAwareImageList_LoadImageA(ResourceInstance, v2, 16, v8, 16711935, cy, 0);
  }
LABEL_15:
  if ( !*(_DWORD *)(dwNewLong + 8) )
    *(_DWORD *)(dwNewLong + 276) = IsolationAwareImageList_GetImageCount(*(_QWORD *)(dwNewLong + 488));
  SendMessageA(*(HWND *)(dwNewLong + 424), 0x1109u, 0, *(_QWORD *)(dwNewLong + 488));
  SendMessageA(*(HWND *)(dwNewLong + 424), 0xBu, 0, 0);
  if ( !*(_DWORD *)(dwNewLong + 8) && *(_QWORD *)(dwNewLong + 296) )
  {
    if ( *(_DWORD *)(dwNewLong + 480) )
      goto LABEL_39;
    if ( ++*(_DWORD *)(dwNewLong + 464) == 1 )
    {
      v9 = malloc(8LL * *(int *)(dwNewLong + 464));
    }
    else
    {
      v9 = realloc(*(void **)(dwNewLong + 472), 8LL * *(int *)(dwNewLong + 464));
      if ( !v9 )
        free(*(void **)(dwNewLong + 472));
    }
    *(_QWORD *)(dwNewLong + 472) = v9;
    v10 = *(CHHWinType **)(dwNewLong + 536);
    if ( v10 )
    {
      ContentCharset = CHHWinType::GetContentCharset(v10);
      v12 = *(_QWORD *)(dwNewLong + 536);
      v13 = ContentCharset;
      v14 = dwNewLong + 496;
    }
    else
    {
      v14 = dwNewLong + 496;
      v12 = 0;
      v15 = *(_QWORD *)(dwNewLong + 496);
      if ( v15 )
        v13 = *(_DWORD *)(v15 + 1208);
      else
        v13 = -1;
    }
    if ( g_fSysWinNT )
    {
      if ( v12 && (v16 = *(_QWORD *)(v12 + 608)) != 0 )
      {
        CodePage = CTitleInformation::GetCodePage(*(CTitleInformation **)(v16 + 192));
      }
      else
      {
        CodePage = 0;
        if ( *(_QWORD *)v14 )
          CodePage = *(_DWORD *)(*(_QWORD *)v14 + 1204LL);
      }
      WideStr = MakeWideStr(*(char **)(dwNewLong + 296), CodePage);
      v21 = (unsigned __int16 *)WideStr;
      v22 = v13;
      if ( WideStr )
      {
        *(_QWORD *)(*(_QWORD *)(dwNewLong + 472) + 8LL * *(int *)(dwNewLong + 464) - 8) = CreateUserFontW(
                                                                                            WideStr,
                                                                                            v19,
                                                                                            v20,
                                                                                            v13);
        free(v21);
        goto LABEL_39;
      }
    }
    else
    {
      v22 = v13;
    }
    *(_QWORD *)(*(_QWORD *)(dwNewLong + 472) + 8LL * *(int *)(dwNewLong + 464) - 8) = CreateUserFont(
                                                                                        *(const char **)(dwNewLong + 296),
                                                                                        0,
                                                                                        0,
                                                                                        v22);
LABEL_39:
    AccessableContentFont = *(HFONT *)(*(_QWORD *)(dwNewLong + 472) + 8LL * *(int *)(dwNewLong + 464) - 8);
    if ( !AccessableContentFont )
      goto LABEL_46;
    goto LABEL_45;
  }
  v24 = *(CHHWinType **)(dwNewLong + 536);
  if ( v24 )
  {
    AccessableContentFont = CHHWinType::GetAccessableContentFont(v24);
  }
  else
  {
    v25 = *(_QWORD *)(dwNewLong + 496);
    if ( !v25 )
      goto LABEL_46;
    AccessableContentFont = *(HFONT *)(v25 + 1216);
  }
LABEL_45:
  SendMessageA(*(HWND *)(dwNewLong + 424), 0x30u, (WPARAM)AccessableContentFont, 0);
LABEL_46:
  if ( *(_DWORD *)(dwNewLong + 8) )
  {
    LoadFirstLevel(
      *(struct CTreeNode **)(dwNewLong + 16),
      *(HWND *)(dwNewLong + 424),
      (struct _TREEITEM **)(dwNewLong + 376));
  }
  else
  {
    *(_QWORD *)(dwNewLong + 384) = lcCalloc(8 * *(_DWORD *)(dwNewLong + 64));
    memset_0(lParam, 0, 0x60u);
    lParam[1] = -65534;
    v66 = 103;
    v67 = 0;
    v68 = -1;
    memset_0(v76, 0, 0x190u);
    inserted = -65536;
    v27 = *(_DWORD *)(dwNewLong + 64) - 1;
    *(_QWORD *)v75 = -65536;
    if ( v27 >= 1 )
    {
      v28 = 1;
      v29 = 0;
      do
      {
LABEL_49:
        v30 = *(_QWORD *)(dwNewLong + 48);
        v31 = v28;
        v32 = *(_QWORD *)(v30 + 8LL * v28);
        if ( (*(_BYTE *)(v32 + 27) & 0x10) == 0 )
        {
          if ( *(_WORD *)(v32 + 22) )
          {
            v33 = *(_QWORD *)(dwNewLong + 560);
            if ( v33 )
            {
              v34 = 0;
              v35 = *(_DWORD *)(*(_QWORD *)(v33 + 8) + 32LL) - 1;
              if ( v35 >= 32 )
              {
                while ( 1 )
                {
                  v36 = CInfoType::AreTheseInfoTypesDefined(
                          (CInfoType *)v33,
                          (struct _tagSiteMapEntry *)v32,
                          *(_DWORD *)(*(_QWORD *)(v33 + 80) + 4LL * v34),
                          v34);
                  if ( v35 <= 32 )
                    break;
                  if ( v36 )
                  {
                    v30 = *(_QWORD *)(dwNewLong + 48);
                    v31 = v28;
                    goto LABEL_60;
                  }
                  v35 -= 32;
                  v34 = v37 + 1;
                }
              }
              else
              {
                v36 = CInfoType::AreTheseInfoTypesDefined(
                        *(CInfoType **)(dwNewLong + 560),
                        *(struct _tagSiteMapEntry **)(v30 + 8LL * v28),
                        **(_DWORD **)(v33 + 80),
                        0);
              }
              if ( !v36 )
                goto LABEL_81;
              v30 = *(_QWORD *)(dwNewLong + 48);
              v31 = v28;
            }
          }
        }
LABEL_60:
        if ( (*(_BYTE *)(v32 + 27) & 1) != 0 )
        {
          if ( *(_BYTE *)(v32 + 25) )
          {
            v44 = *(unsigned __int8 *)(v32 + 25);
            if ( (int)v44 <= v29 )
            {
              inserted = *(_QWORD *)&v75[8 * v44 - 8];
              v29 = v44 - 1;
            }
          }
          ImageNumber = CSiteMap::GetImageNumber((CSiteMap *)(dwNewLong + 32), (struct _tagSiteMapEntry *)v32);
          *(_BYTE *)(v32 + 24) = ImageNumber;
          v46 = *(HWND *)(dwNewLong + 424);
          lParam[0] = inserted;
          v69 = ImageNumber - 1;
          v70 = v69;
          v71 = 0;
          v72 = v31;
          *(_QWORD *)(*(_QWORD *)(dwNewLong + 384) + 8 * v31) = W_TreeView_InsertItem_fn(v46, (LPARAM)lParam);
        }
        else
        {
          v38 = 0;
          v39 = v28 + 1;
          while ( 1 )
          {
            v40 = *(_QWORD *)(v30 + 8LL * (v39 + v38));
            if ( !v40 )
              break;
            if ( *(_BYTE *)(v40 + 25) <= *(_BYTE *)(v32 + 25) )
            {
              v28 = v39 + v38;
              goto LABEL_49;
            }
            if ( (*(_BYTE *)(v40 + 27) & 1) != 0 )
              break;
            v30 = *(_QWORD *)(dwNewLong + 48);
            ++v38;
          }
          if ( *(unsigned __int8 *)(v32 + 25) <= v29 + 1 )
          {
            LOBYTE(v29) = *(_BYTE *)(v32 + 25);
          }
          else
          {
            LOBYTE(v29) = v29 + 1;
            *(_BYTE *)(v32 + 25) = v29;
          }
          if ( (_BYTE)v29 )
          {
            v29 = (unsigned __int8)v29;
            if ( (unsigned __int8)v29 > 0x32u )
              v29 = 50;
          }
          else
          {
            v29 = 1;
          }
          v41 = CSiteMap::GetImageNumber((CSiteMap *)(dwNewLong + 32), (struct _tagSiteMapEntry *)v32);
          *(_BYTE *)(v32 + 24) = v41;
          if ( ((v41 - 2) & 0xF9) == 0 )
            *(_BYTE *)(v32 + 24) = --v41;
          v69 = v41 - 1;
          v70 = v69;
          v42 = *(HWND *)(dwNewLong + 424);
          lParam[0] = *(_QWORD *)&v75[8 * v29 - 8];
          v72 = (unsigned int)v28;
          v71 = 1;
          inserted = (LPARAM)W_TreeView_InsertItem_fn(v42, (LPARAM)lParam);
          v43 = *(_QWORD *)(dwNewLong + 384);
          *(_QWORD *)&v75[8 * v29] = inserted;
          *(_QWORD *)(v43 + 8 * v31) = inserted;
        }
LABEL_81:
        ++v28;
      }
      while ( v28 <= *(_DWORD *)(dwNewLong + 64) - 1 );
    }
  }
  if ( !*(_DWORD *)(dwNewLong + 8) && !*(_DWORD *)(dwNewLong + 480) )
  {
    if ( *(_DWORD *)(dwNewLong + 284) != -1 && *(_DWORD *)(dwNewLong + 288) != -1 )
    {
      WindowDC = GetWindowDC(*(HWND *)(dwNewLong + 424));
      if ( (unsigned int)GetHighContrastFlag()
        || (NearestColor = GetNearestColor(WindowDC, *(_DWORD *)(dwNewLong + 288)),
            GetNearestColor(WindowDC, *(_DWORD *)(dwNewLong + 284)) == NearestColor) )
      {
        *(_DWORD *)(dwNewLong + 288) = -1;
        *(_DWORD *)(dwNewLong + 284) = -1;
      }
      ReleaseDC(*(HWND *)(dwNewLong + 424), WindowDC);
    }
    v49 = *(_DWORD *)(dwNewLong + 284);
    if ( v49 != -1 )
      *(_QWORD *)(dwNewLong + 448) = CreateSolidBrush(v49);
    v50 = *(const char **)(dwNewLong + 320);
    if ( v50
      && !*(_QWORD *)(dwNewLong + 432)
      && (unsigned int)ConvertToCacheFile(v50, v75, 0x104u)
      && (unsigned int)LoadGif(v75, (HBITMAP *)(dwNewLong + 432), (HPALETTE *)(dwNewLong + 440), v51) )
    {
      v52 = *(void **)(dwNewLong + 432);
      pv = 0;
      v74 = 0;
      GetObjectA(v52, 32, &pv);
      *(_QWORD *)(dwNewLong + 456) = *(_QWORD *)((char *)&pv + 4);
    }
  }
  if ( *(_QWORD *)(dwNewLong + 536) || *(_QWORD *)(dwNewLong + 448) || *(_QWORD *)(dwNewLong + 432) )
  {
    v53 = IsWindowUnicode(*(HWND *)(dwNewLong + 424));
    WndProc = W_GetWndProc(*(HWND *)(dwNewLong + 424), v53);
    v55 = *(HWND *)(dwNewLong + 424);
    g_lpfnlTreeViewWndProc = WndProc;
    W_SubClassWindow(v55, (__int64)TreeViewProc, v53);
    SetWindowLongPtrA(*(HWND *)(dwNewLong + 424), -21, dwNewLong);
    SetPropA(*(HWND *)(dwNewLong + 424), "HHDefProc", g_lpfnlTreeViewWndProc);
  }
  SendMessageA(*(HWND *)(dwNewLong + 424), 0xBu, 1u, 0);
  *(_DWORD *)(dwNewLong + 408) = 1;
  if ( *(_DWORD *)(dwNewLong + 8) )
  {
    v58 = *(_QWORD *)(dwNewLong + 376);
    if ( v58 )
    {
      SendMessageA(*(HWND *)(dwNewLong + 424), 0x110Bu, 5u, v58);
      *(_QWORD *)(dwNewLong + 400) = *(_QWORD *)(dwNewLong + 376);
    }
  }
  else
  {
    v56 = *(int *)(dwNewLong + 392);
    if ( (_DWORD)v56 )
    {
      v57 = *(_QWORD *)(dwNewLong + 384);
      if ( v57 )
        SendMessageA(*(HWND *)(dwNewLong + 424), 0x110Bu, 5u, *(_QWORD *)(v57 + 8 * v56));
    }
  }
  if ( !*(_DWORD *)(dwNewLong + 8) )
  {
    v59 = *(int *)(dwNewLong + 396);
    if ( (_DWORD)v59 )
    {
      v60 = *(_QWORD *)(dwNewLong + 384);
      if ( v60 )
        SendMessageA(*(HWND *)(dwNewLong + 424), 0x110Bu, 9u, *(_QWORD *)(v60 + 8 * v59));
    }
  }
  *(_QWORD *)(dwNewLong + 400) = SendMessageA(*(HWND *)(dwNewLong + 424), 0x110Au, 9u, 0);
  *(_DWORD *)(dwNewLong + 408) = 0;
  if ( *(_DWORD *)(dwNewLong + 480) && !(unsigned int)CStr::IsEmpty((CStr *)(dwNewLong + 544)) )
  {
    v62 = *v61;
    *(_DWORD *)(dwNewLong + 532) = 0;
    CToc::Synchronize((CToc *)dwNewLong, v62);
  }
  ShowWindow(*(HWND *)(dwNewLong + 424), 5);
  return 1;
}

```

## disassembly

```asm
0x1800197c8  push    rbp
0x1800197ca  push    rbx
0x1800197cb  push    rsi
0x1800197cc  push    rdi
0x1800197cd  push    r12
0x1800197cf  push    r13
0x1800197d1  push    r14
0x1800197d3  push    r15
0x1800197d5  lea     rbp, [rsp-178h]
0x1800197dd  sub     rsp, 278h
0x1800197e4  mov     rax, cs:__security_cookie
0x1800197eb  xor     rax, rsp
0x1800197ee  mov     [rbp+1B0h+var_50], rax
0x1800197f5  xor     r15d, r15d
0x1800197f8  mov     rdi, rcx
0x1800197fb  cmp     cs:?g_RTL_Mirror_Style@@3KA, r15d; ulong g_RTL_Mirror_Style
0x180019802  mov     esi, 6Ch ; 'l'
0x180019807  jz      short loc_18001980E
0x180019809  mov     esi, 0CEh
0x18001980e  mov     rcx, [rcx+1A8h]; hWnd
0x180019815  mov     r14d, 1
0x18001981b  mov     [rsp+2B0h+uFlags], 27h ; '''; uFlags
0x180019823  xor     r9d, r9d; Y
0x180019826  mov     [rsp+2B0h+cy], r14d; cy
0x18001982b  xor     r8d, r8d; X
0x18001982e  xor     edx, edx; hWndInsertAfter
0x180019830  mov     [rsp+2B0h+var_290], r14d; cx
0x180019835  call    cs:__imp_SetWindowPos
0x18001983b  lea     r12d, [r14+0Fh]
0x18001983f  mov     r13d, 104h
0x180019845  cmp     [rdi+1E0h], r15d
0x18001984c  jnz     loc_18001992C
0x180019852  mov     rcx, [rdi+108h]; char *
0x180019859  test    rcx, rcx
0x18001985c  jz      loc_1800198FC
0x180019862  cmp     [rdi+8], r15d
0x180019866  jnz     loc_1800198FC
0x18001986c  mov     rax, [rdi+1F0h]
0x180019873  test    rax, rax
0x180019876  jz      short loc_18001988C
0x180019878  mov     rdx, rcx; char *
0x18001987b  lea     r8, [rbp+1B0h+var_1F0]; char *
0x18001987f  mov     rcx, rax; this
0x180019882  mov     r9d, r13d; unsigned __int64
0x180019885  call    ?ConvertToCacheFile@CHtmlHelpControl@@QEAAHPEBDPEAD_K@Z; CHtmlHelpControl::ConvertToCacheFile(char const *,char *,unsigned __int64)
0x18001988a  jmp     short loc_180019898
0x18001988c  mov     r8, r13; unsigned __int64
0x18001988f  lea     rdx, [rbp+1B0h+var_1F0]; char *
0x180019893  call    ?ConvertToCacheFile@@YAHPEBDPEAD_K@Z; ConvertToCacheFile(char const *,char *,unsigned __int64)
0x180019898  test    eax, eax
0x18001989a  jz      short loc_1800198CB
0x18001989c  mov     eax, [rdi+118h]
0x1800198a2  lea     rdx, [rbp+1B0h+var_1F0]
0x1800198a6  mov     r8d, [rdi+110h]
0x1800198ad  xor     ecx, ecx
0x1800198af  mov     [rsp+2B0h+uFlags], r12d
0x1800198b4  mov     [rsp+2B0h+var_290], eax
0x1800198b8  call    IsolationAwareImageList_LoadImageA
0x1800198bd  mov     [rdi+1E8h], rax
0x1800198c4  test    rax, rax
0x1800198c7  jnz     short loc_18001992C
0x1800198c9  jmp     short loc_1800198D2
0x1800198cb  mov     [rdi+1E8h], r15
0x1800198d2  mov     rcx, [rdi+1A8h]; HWND
0x1800198d9  mov     rbx, [rdi+1F0h]
0x1800198e0  call    ?FindMessageParent@@YAPEAUHWND__@@PEAU1@@Z; FindMessageParent(HWND__ *)
0x1800198e5  mov     rdx, [rdi+108h]; char *
0x1800198ec  mov     r9, rbx
0x1800198ef  mov     r8, rax
0x1800198f2  mov     ecx, 1D805h; unsigned int
0x1800198f7  call    AuthorMsg
0x1800198fc  lea     rcx, ?_Module@@3VCHtmlHelpModule@@A; this
0x180019903  movzx   ebx, si
0x180019906  call    ?GetResourceInstance@CHtmlHelpModule@@QEAAPEAUHINSTANCE__@@XZ; CHtmlHelpModule::GetResourceInstance(void)
0x18001990b  mov     r8d, r12d
0x18001990e  mov     [rsp+2B0h+uFlags], r15d
0x180019913  mov     edx, ebx
0x180019915  mov     [rsp+2B0h+var_290], 0FF00FFh
0x18001991d  mov     rcx, rax
0x180019920  call    IsolationAwareImageList_LoadImageA
0x180019925  mov     [rdi+1E8h], rax
0x18001992c  cmp     [rdi+8], r15d
0x180019930  jnz     short loc_180019944
0x180019932  mov     rcx, [rdi+1E8h]
0x180019939  call    IsolationAwareImageList_GetImageCount
0x18001993e  mov     [rdi+114h], eax
0x180019944  mov     r9, [rdi+1E8h]; lParam
0x18001994b  xor     r8d, r8d; wParam
0x18001994e  mov     rcx, [rdi+1A8h]; hWnd
0x180019955  mov     edx, 1109h; Msg
0x18001995a  call    cs:__imp_SendMessageA
0x180019960  mov     rcx, [rdi+1A8h]; hWnd
0x180019967  xor     r9d, r9d; lParam
0x18001996a  xor     r8d, r8d; wParam
0x18001996d  lea     edx, [r9+0Bh]; Msg
0x180019971  call    cs:__imp_SendMessageA
0x180019977  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001997b  cmp     [rdi+8], r15d
0x18001997f  jnz     loc_180019AEF
0x180019985  cmp     [rdi+128h], r15
0x18001998c  jz      loc_180019AEF
0x180019992  cmp     [rdi+1E0h], r15d
0x180019999  jnz     loc_180019AD5
0x18001999f  add     [rdi+1D0h], r14d
0x1800199a6  movsxd  rax, dword ptr [rdi+1D0h]
0x1800199ad  mov     rdx, rax
0x1800199b0  shl     rdx, 3; Size
0x1800199b4  cmp     eax, r14d
0x1800199b7  jnz     short loc_1800199C7
0x1800199b9  mov     rcx, rdx; Size
0x1800199bc  call    cs:__imp_malloc
0x1800199c2  mov     rbx, rax
0x1800199c5  jmp     short loc_1800199E9
0x1800199c7  mov     rcx, [rdi+1D8h]; Block
0x1800199ce  call    cs:__imp_realloc
0x1800199d4  mov     rbx, rax
0x1800199d7  test    rax, rax
0x1800199da  jnz     short loc_1800199E9
0x1800199dc  mov     rcx, [rdi+1D8h]; Block
0x1800199e3  call    cs:__imp_free
0x1800199e9  mov     [rdi+1D8h], rbx
0x1800199f0  mov     rcx, [rdi+218h]; this
0x1800199f7  test    rcx, rcx
0x1800199fa  jz      short loc_180019A13
0x1800199fc  call    ?GetContentCharset@CHHWinType@@QEAAHXZ; CHHWinType::GetContentCharset(void)
0x180019a01  mov     rcx, [rdi+218h]
0x180019a08  mov     ebx, eax
0x180019a0a  lea     rax, [rdi+1F0h]
0x180019a11  jmp     short loc_180019A30
0x180019a13  lea     rax, [rdi+1F0h]
0x180019a1a  mov     rcx, r15
0x180019a1d  mov     rbx, [rax]
0x180019a20  test    rbx, rbx
0x180019a23  jz      short loc_180019A2D
0x180019a25  mov     ebx, [rbx+4B8h]
0x180019a2b  jmp     short loc_180019A30
0x180019a2d  mov     ebx, r12d
0x180019a30  cmp     cs:?g_fSysWinNT@@3HA, r15d; int g_fSysWinNT
0x180019a37  jz      short loc_180019AAB
0x180019a39  test    rcx, rcx
0x180019a3c  jz      short loc_180019A5A
0x180019a3e  mov     rcx, [rcx+260h]
0x180019a45  test    rcx, rcx
0x180019a48  jz      short loc_180019A5A
0x180019a4a  mov     rcx, [rcx+0C0h]; this
0x180019a51  call    ?GetCodePage@CTitleInformation@@QEAAIXZ; CTitleInformation::GetCodePage(void)
0x180019a56  mov     edx, eax
0x180019a58  jmp     short loc_180019A6B
0x180019a5a  mov     rcx, [rax]
0x180019a5d  mov     edx, r15d
0x180019a60  test    rcx, rcx
0x180019a63  jz      short loc_180019A6B
0x180019a65  mov     edx, [rcx+4B4h]; unsigned int
0x180019a6b  mov     rcx, [rdi+128h]; char *
0x180019a72  call    ?MakeWideStr@@YAPEAGPEADI@Z; MakeWideStr(char *,uint)
0x180019a77  mov     rsi, rax
0x180019a7a  mov     r9d, ebx; int
0x180019a7d  test    rax, rax
0x180019a80  jz      short loc_180019AAE
0x180019a82  mov     rcx, rax; unsigned __int16 *
0x180019a85  call    ?CreateUserFontW@@YAPEAUHFONT__@@PEBGPEAKPEAUHDC__@@H@Z; CreateUserFontW(ushort const *,ulong *,HDC__ *,int)
0x180019a8a  movsxd  rcx, dword ptr [rdi+1D0h]
0x180019a91  mov     rdx, rax
0x180019a94  mov     rax, [rdi+1D8h]
0x180019a9b  mov     [rax+rcx*8-8], rdx
0x180019aa0  mov     rcx, rsi; Block
0x180019aa3  call    cs:__imp_free
0x180019aa9  jmp     short loc_180019AD5
0x180019aab  mov     r9d, ebx; int
0x180019aae  mov     rcx, [rdi+128h]; char *
0x180019ab5  xor     r8d, r8d; HDC
0x180019ab8  xor     edx, edx; unsigned int *
0x180019aba  call    ?CreateUserFont@@YAPEAUHFONT__@@PEBDPEAKPEAUHDC__@@H@Z; CreateUserFont(char const *,ulong *,HDC__ *,int)
0x180019abf  movsxd  rcx, dword ptr [rdi+1D0h]
0x180019ac6  mov     rdx, rax
0x180019ac9  mov     rax, [rdi+1D8h]
0x180019ad0  mov     [rax+rcx*8-8], rdx
0x180019ad5  movsxd  rcx, dword ptr [rdi+1D0h]
0x180019adc  mov     rax, [rdi+1D8h]
0x180019ae3  mov     r8, [rax+rcx*8-8]
0x180019ae8  test    r8, r8
0x180019aeb  jz      short loc_180019B2C
0x180019aed  jmp     short loc_180019B18
0x180019aef  mov     rcx, [rdi+218h]; this
0x180019af6  test    rcx, rcx
0x180019af9  jz      short loc_180019B05
0x180019afb  call    ?GetAccessableContentFont@CHHWinType@@QEAAPEAUHFONT__@@XZ; CHHWinType::GetAccessableContentFont(void)
0x180019b00  mov     r8, rax
0x180019b03  jmp     short loc_180019B18
0x180019b05  mov     r8, [rdi+1F0h]
0x180019b0c  test    r8, r8
0x180019b0f  jz      short loc_180019B2C
0x180019b11  mov     r8, [r8+4C0h]; wParam
0x180019b18  mov     rcx, [rdi+1A8h]; hWnd
0x180019b1f  xor     r9d, r9d; lParam
0x180019b22  lea     edx, [r9+30h]; Msg
0x180019b26  call    cs:__imp_SendMessageA
0x180019b2c  cmp     [rdi+8], r15d
0x180019b30  jnz     loc_180019D9B
0x180019b36  mov     ecx, [rdi+40h]
0x180019b39  shl     ecx, 3; int
0x180019b3c  call    ?lcCalloc@@YAPEAXH@Z; lcCalloc(int)
0x180019b41  xor     edx, edx; Val
0x180019b43  mov     [rdi+180h], rax
0x180019b4a  lea     rcx, [rsp+2B0h+lParam]; void *
0x180019b4f  lea     r8d, [rdx+60h]; Size
0x180019b53  call    memset_0
0x180019b58  xor     edx, edx; Val
0x180019b5a  mov     [rsp+2B0h+var_268], 0FFFFFFFFFFFF0002h
0x180019b63  mov     r8d, 190h; Size
0x180019b69  mov     [rsp+2B0h+var_260], 67h ; 'g'
0x180019b71  lea     rcx, [rbp+1B0h+var_1E8]; void *
0x180019b75  mov     [rsp+2B0h+var_258], r15
0x180019b7a  mov     [rsp+2B0h+var_248], r12
0x180019b7f  call    memset_0
0x180019b84  mov     eax, [rdi+40h]
0x180019b87  mov     r12, 0FFFFFFFFFFFF0000h
0x180019b8e  sub     eax, r14d
0x180019b91  mov     qword ptr [rbp+1B0h+var_1F0], r12
0x180019b95  cmp     eax, r14d
0x180019b98  jl      loc_180019DB2
0x180019b9e  mov     r13d, r14d
0x180019ba1  mov     esi, r15d
0x180019ba4  mov     rcx, [rdi+30h]
0x180019ba8  movsxd  r14, r13d
0x180019bab  mov     rbx, [rcx+r14*8]
0x180019baf  test    byte ptr [rbx+1Bh], 10h
0x180019bb3  jnz     loc_180019C3B
0x180019bb9  cmp     [rbx+16h], r15w
0x180019bbe  jz      short loc_180019C3B
0x180019bc0  mov     r15, [rdi+230h]
0x180019bc7  test    r15, r15
0x180019bca  jz      short loc_180019C38
0x180019bcc  mov     rax, [r15+8]
0x180019bd0  xor     r9d, r9d; int
0x180019bd3  mov     r14d, [rax+20h]
0x180019bd7  dec     r14d
0x180019bda  cmp     r14d, 20h ; ' '
0x180019bde  jge     short loc_180019C07
0x180019be0  mov     r8, [r15+50h]
0x180019be4  mov     rdx, rbx; struct _tagSiteMapEntry *
0x180019be7  mov     rcx, r15; this
0x180019bea  mov     r8d, [r8]; unsigned int
0x180019bed  call    ?AreTheseInfoTypesDefined@CInfoType@@QEBAPEAUSITE_ENTRY_URL@@PEAU_tagSiteMapEntry@@IH@Z; CInfoType::AreTheseInfoTypesDefined(_tagSiteMapEntry *,uint,int)
0x180019bf2  xor     r15d, r15d
0x180019bf5  test    rax, rax
0x180019bf8  jz      loc_180019D7B
0x180019bfe  mov     rcx, [rdi+30h]
0x180019c02  movsxd  r14, r13d
0x180019c05  jmp     short loc_180019C3B
0x180019c07  mov     r8, [r15+50h]
0x180019c0b  mov     rdx, rbx; struct _tagSiteMapEntry *
0x180019c0e  movsxd  rax, r9d
0x180019c11  mov     rcx, r15; this
0x180019c14  mov     r8d, [r8+rax*4]; unsigned int
0x180019c18  call    ?AreTheseInfoTypesDefined@CInfoType@@QEBAPEAUSITE_ENTRY_URL@@PEAU_tagSiteMapEntry@@IH@Z; CInfoType::AreTheseInfoTypesDefined(_tagSiteMapEntry *,uint,int)
0x180019c1d  cmp     r14d, 20h ; ' '
0x180019c21  jle     short loc_180019BF2
0x180019c23  test    rax, rax
0x180019c26  jnz     short loc_180019C31
0x180019c28  sub     r14d, 20h ; ' '
0x180019c2c  inc     r9d
0x180019c2f  jmp     short loc_180019C07
0x180019c31  mov     rcx, [rdi+30h]
0x180019c35  movsxd  r14, r13d
0x180019c38  xor     r15d, r15d
0x180019c3b  test    byte ptr [rbx+1Bh], 1
0x180019c3f  jnz     loc_180019D1C
0x180019c45  mov     edx, r15d
0x180019c48  lea     r9d, [r13+1]
0x180019c4c  lea     r8d, [r9+rdx]
0x180019c50  movsxd  rax, r8d
0x180019c53  mov     rcx, [rcx+rax*8]
0x180019c57  test    rcx, rcx
0x180019c5a  jz      short loc_180019C7A
0x180019c5c  mov     al, [rbx+19h]
0x180019c5f  cmp     [rcx+19h], al
0x180019c62  jbe     short loc_180019C72
0x180019c64  test    byte ptr [rcx+1Bh], 1
0x180019c68  jnz     short loc_180019C7A
0x180019c6a  mov     rcx, [rdi+30h]
0x180019c6e  inc     edx
0x180019c70  jmp     short loc_180019C4C
0x180019c72  mov     r13d, r8d
0x180019c75  jmp     loc_180019BA4
0x180019c7a  movzx   ecx, byte ptr [rbx+19h]
0x180019c7e  lea     eax, [rsi+1]
0x180019c81  cmp     ecx, eax
0x180019c83  jle     short loc_180019C8E
0x180019c85  inc     sil
0x180019c88  mov     [rbx+19h], sil
0x180019c8c  jmp     short loc_180019C91
0x180019c8e  mov     sil, cl
0x180019c91  cmp     sil, 1
0x180019c95  jnb     short loc_180019C9E
0x180019c97  mov     esi, 1
0x180019c9c  jmp     short loc_180019CAC
0x180019c9e  movzx   esi, sil
0x180019ca2  mov     eax, 32h ; '2'
0x180019ca7  cmp     esi, eax
  ... truncated ...
```
