# ListView_WndProc

- ea: `0x18005c0a0`
- end: `0x18005ddd8`
- name: `ListView_WndProc`
- size: `7480`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `0`
- callee_count: `101`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800115f0`
- `0x180017a0c`
- `0x180018158`
- `0x1800183dc`
- `0x180018464`
- `0x1800186c0`
- `0x180018d24`
- `0x180018d90`
- `0x1800190a4`
- `0x1800197bc`
- `0x180019aa8`
- `0x18002fd4c`
- `0x180030440`
- `0x18003a400`
- `0x18003a530`
- `0x180050924`
- `0x180052994`
- `0x1800529fc`
- `0x18005305c`
- `0x1800530b4`
- `0x180053c94`
- `0x180053d94`
- `0x180053f50`
- `0x180054344`
- `0x1800549b8`
- `0x180054bc0`
- `0x180054c90`
- `0x18005506c`
- `0x180055458`
- `0x180055608`
- `0x18005594c`
- `0x180055a14`
- `0x180055bf8`
- `0x180055c74`
- `0x180055de0`
- `0x1800561dc`
- `0x180056298`
- `0x180056370`
- `0x1800563ec`
- `0x18005643c`
- `0x180056604`
- `0x1800566b8`
- `0x180056894`
- `0x180056970`
- `0x180056c24`
- `0x180056f4c`
- `0x1800572dc`
- `0x18005736c`
- `0x180057540`
- `0x180057658`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18005c14f`
- `KERNEL32!GetProcessHeap` at `0x18005c14f`
- `KERNEL32!LocalFree` at `0x18005cb55`
- `KERNEL32!LocalFree` at `0x18005cbbe`
- `KERNEL32!LocalFree` at `0x18005cc21`
- `KERNEL32!LocalFree` at `0x18005cea8`
- `KERNEL32!LocalFree` at `0x18005d118`
- `KERNEL32!LocalFree` at `0x18005cb55`
- `KERNEL32!LocalFree` at `0x18005cbbe`
- `KERNEL32!LocalFree` at `0x18005cc21`
- `KERNEL32!LocalFree` at `0x18005cea8`
- `KERNEL32!LocalFree` at `0x18005d118`
- `KERNEL32!lstrlenW` at `0x18005d819`
- `KERNEL32!lstrlenW` at `0x18005d819`
- `KERNEL32!LocalAlloc` at `0x18005c101`
- `KERNEL32!LocalAlloc` at `0x18005c101`
- `KERNEL32!WideCharToMultiByte` at `0x18005d406`
- `KERNEL32!WideCharToMultiByte` at `0x18005d406`
- `KERNEL32!lstrlenA` at `0x18005cf38`
- `KERNEL32!lstrlenA` at `0x18005cf38`
- `USER32!GetClientRect` at `0x18005c345`
- `USER32!GetClientRect` at `0x18005c345`
- `USER32!IsWindow` at `0x18005c8a9`
- `USER32!IsWindow` at `0x18005d153`
- `USER32!IsWindow` at `0x18005c8a9`
- `USER32!IsWindow` at `0x18005d153`
- `USER32!SendMessageW` at `0x18005c35f`
- `USER32!SendMessageW` at `0x18005c712`
- `USER32!SendMessageW` at `0x18005d135`
- `USER32!SendMessageW` at `0x18005d1e9`
- `USER32!SendMessageW` at `0x18005da2e`
- `USER32!SendMessageW` at `0x18005c35f`
- `USER32!SendMessageW` at `0x18005c712`
- `USER32!SendMessageW` at `0x18005d135`
- `USER32!SendMessageW` at `0x18005d1e9`
- `USER32!SendMessageW` at `0x18005da2e`
- `USER32!ScreenToClient` at `0x18005db09`
- `USER32!ScreenToClient` at `0x18005db09`
- `USER32!CopyRect` at `0x18005d643`
- `USER32!CopyRect` at `0x18005d643`
- `USER32!SetWindowLongPtrW` at `0x18005c161`
- `USER32!SetWindowLongPtrW` at `0x18005c161`
- `USER32!GetDlgCtrlID` at `0x18005c501`
- `USER32!GetDlgCtrlID` at `0x18005c501`
- `USER32!SetFocus` at `0x18005c8a0`
- `USER32!SetFocus` at `0x18005c8a0`
- `USER32!GetFocus` at `0x18005d061`
- `USER32!GetFocus` at `0x18005dc1c`
- `USER32!GetFocus` at `0x18005d061`
- `USER32!GetFocus` at `0x18005dc1c`
- `USER32!InvalidateRect` at `0x18005c40d`
- `USER32!InvalidateRect` at `0x18005d7e8`
- `USER32!InvalidateRect` at `0x18005c40d`
- `USER32!InvalidateRect` at `0x18005d7e8`
- `USER32!LoadCursorW` at `0x18005d588`
- `USER32!LoadCursorW` at `0x18005d59d`
- `USER32!LoadCursorW` at `0x18005d588`
- `USER32!LoadCursorW` at `0x18005d59d`
- `USER32!GetWindowLongPtrW` at `0x18005c0db`
- `USER32!GetWindowLongPtrW` at `0x18005c0db`
- `USER32!DefWindowProcW` at `0x18005c517`
- `USER32!DefWindowProcW` at `0x18005c517`
- `USER32!UpdateWindow` at `0x18005d031`
- `USER32!UpdateWindow` at `0x18005d031`
- `USER32!GetScrollInfo` at `0x18005d9ab`
- `USER32!GetScrollInfo` at `0x18005d9ab`
- `USER32!GetKeyboardLayout` at `0x18005c7d6`
- `USER32!GetKeyboardLayout` at `0x18005c7d6`
- `USER32!GetKeyboardState` at `0x18005db45`
- `USER32!GetKeyboardState` at `0x18005db45`
- `USER32!SetKeyboardState` at `0x18005db57`
- `USER32!SetKeyboardState` at `0x18005db57`

## pseudocode

```c
__int64 __fastcall ListView_WndProc(HWND hWnd, unsigned int a2, HDC a3, LPARAM a4)
{
  LONG_PTR WindowLongPtrW; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  char *v12; // r14
  _QWORD *v13; // rdi
  _DWORD *v14; // rax
  LONG_PTR v15; // rdi
  HDC v16; // r8
  int v17; // edx
  HWND v18; // rcx
  __int64 v19; // r15
  int v20; // ecx
  bool v21; // zf
  __int64 result; // rax
  __int64 v23; // r8
  __int64 v24; // r9
  int v25; // eax
  __int64 v26; // rdx
  int v27; // eax
  int v28; // eax
  __int64 v29; // rcx
  unsigned int v30; // eax
  HWND v31; // rcx
  __int64 v32; // rcx
  UINT v33; // r10d
  int v34; // edx
  __int64 v35; // rcx
  int v36; // r8d
  __int64 v37; // rcx
  __int64 v38; // rcx
  int v39; // ebx
  int StringWidth; // edi
  void *v41; // rbx
  __int64 v42; // r12
  __int64 v43; // r14
  __int64 v44; // rax
  void *v46; // rbx
  __int64 v47; // r12
  __int64 v48; // r14
  __int64 v49; // rax
  int v50; // edi
  __int64 v51; // rax
  void *v52; // r15
  int inserted; // ebx
  __int64 v54; // rax
  int *v55; // rax
  __int64 v56; // rbx
  int v57; // eax
  int v58; // r14d
  int v59; // ebx
  void *v60; // r15
  __int64 v61; // r12
  __int64 v62; // r14
  __int64 v63; // rax
  void *v64; // rcx
  __int64 v65; // r12
  __int64 v66; // r14
  __int64 v67; // rax
  const CHAR *v68; // rdx
  int v69; // r14d
  __int64 v70; // rsi
  int v71; // ecx
  HWND v72; // rbx
  int v73; // ecx
  int v74; // eax
  UINT v75; // edx
  int v76; // eax
  HWND v77; // rcx
  int v78; // eax
  int v79; // eax
  int v80; // eax
  int v81; // eax
  __int64 v82; // r9
  CHAR *lpMultiByteStr; // rcx
  __int128 v84; // xmm2
  __int64 v85; // xmm0_8
  char v86; // al
  int v87; // ecx
  __int64 v88; // rsi
  __int64 v89; // r8
  __int64 v90; // r9
  int v91; // edx
  int v92; // eax
  __int64 v93; // rbx
  __int64 v94; // rcx
  char v95; // r8
  __int64 v96; // r8
  int v97; // ecx
  int v98; // r14d
  int WindowStyle; // r12d
  int v100; // r12d
  BOOL v101; // r13d
  int v102; // eax
  HWND v103; // rbx
  HWND v104; // rcx
  BOOL ScrollInfo; // eax
  int v106; // r12d
  int v107; // ebx
  int v108; // eax
  unsigned int v109; // eax
  HWND v110; // rcx
  DWORD_PTR v111; // rcx
  int v112; // eax
  wchar_t *v113; // rcx
  HWND v114; // rbx
  __int64 v115; // r8
  int v116; // r9d
  unsigned int v117; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v118; // [rsp+48h] [rbp-B8h] BYREF
  DWORD_PTR pdwRefData[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE lParam[64]; // [rsp+60h] [rbp-A0h] BYREF
  struct tagTRACKMOUSEEVENT EventTrack; // [rsp+A0h] [rbp-60h] BYREF
  BYTE KeyState[16]; // [rsp+C0h] [rbp-40h] BYREF
  char v123; // [rsp+D0h] [rbp-30h]

  WindowLongPtrW = GetWindowLongPtrW(hWnd, 0);
  v12 = 0;
  v13 = (_QWORD *)WindowLongPtrW;
  if ( !WindowLongPtrW )
  {
    if ( a2 != 129 )
    {
LABEL_5:
      v16 = a3;
      v17 = a2;
      v18 = hWnd;
      return DefWindowProcW(v18, v17, (WPARAM)v16, a4);
    }
    v14 = LocalAlloc(0x40u, 0x298u);
    v15 = (LONG_PTR)v14;
    if ( v14 )
    {
      *(_QWORD *)v14 = hWnd;
      v14[36] = -1;
      v14[37] = -1;
      v14[116] = -1;
      v14[129] = -1;
      v14[118] = 1;
      v14[64] = 1;
      v14[18] = 16;
      *((_QWORD *)v14 + 15) = GetProcessHeap();
      SetWindowLongPtrW(hWnd, 0, v15);
      goto LABEL_5;
    }
    return 0;
  }
  v19 = 1;
  if ( a2 - 512 <= 0xD && (*(_BYTE *)(WindowLongPtrW + 76) & 0xC8) != 0 )
  {
    EventTrack.hwndTrack = *(HWND *)WindowLongPtrW;
    EventTrack.dwHoverTime = *(_DWORD *)(WindowLongPtrW + 548);
    *(&EventTrack.dwHoverTime + 1) = 0;
    EventTrack.cbSize = 24;
    EventTrack.dwFlags = 1073741827;
    TrackMouseEvent(&EventTrack);
    v20 = (LOBYTE(EventTrack.dwFlags) ^ 0xFE) & 3;
    v21 = (*((_BYTE *)v13 + 76) & 8) == 0;
    EventTrack.dwFlags = v20;
    if ( !v21 )
    {
      v20 ^= 1u;
      EventTrack.dwFlags = v20;
    }
    EventTrack.hwndTrack = (HWND)*v13;
    EventTrack.dwHoverTime = *((_DWORD *)v13 + 137);
    EventTrack.cbSize = 24;
    if ( (v20 & 3) != 0 )
      TrackMouseEvent(&EventTrack);
  }
  if ( a2 == g_uDragImages )
    return LVGenerateDragImage((__int64)v13, a4);
  if ( a2 > 0x1015 )
  {
    if ( a2 <= 0x103B )
    {
      if ( a2 == 4155 )
      {
        v75 = 4625;
        return SendMessageW((HWND)v13[55], v75, (WPARAM)a3, a4);
      }
      switch ( a2 )
      {
        case 0x1016u:
          LODWORD(result) = ListView_OnArrange(v13, (unsigned int)a3);
          return (int)result;
        case 0x1017u:
          if ( a4 )
            v12 = (char *)ProduceWFromA(*((_DWORD *)v13 + 7), (LPCCH)a4);
          v56 = ListView_OnEditLabel((int)v13, (int)a3);
          if ( (unsigned __int64)(v12 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            LocalFree(v12);
          return v56;
        case 0x1018u:
          return v13[41];
        case 0x1019u:
          LODWORD(result) = ListView_OnGetColumnA(v13, (unsigned int)a3, a4);
          return (int)result;
        case 0x101Au:
          if ( !a4 )
            return 0;
          v60 = 0;
          v61 = 0;
          if ( (*(_BYTE *)a4 & 4) == 0 )
            goto LABEL_255;
          v62 = *(_QWORD *)(a4 + 16);
          if ( !v62 )
            goto LABEL_255;
          v63 = ProduceWFromA(*((_DWORD *)v13 + 7), *(LPCCH *)(a4 + 16));
          v60 = (void *)v63;
          if ( !v63 )
            return 0;
          v61 = v62;
          *(_QWORD *)(a4 + 16) = v63;
LABEL_255:
          v59 = ListView_OnSetColumn(v13, (unsigned int)a3, a4);
          if ( !v60 )
            return v59;
          *(_QWORD *)(a4 + 16) = v61;
          if ( v60 == (void *)-1LL )
            return v59;
          v64 = v60;
          goto LABEL_258;
        case 0x101Bu:
          if ( !a4 )
            return -1;
          v52 = 0;
          v65 = 0;
          if ( (*(_BYTE *)a4 & 4) == 0 )
            goto LABEL_265;
          v66 = *(_QWORD *)(a4 + 16);
          if ( !v66 )
            goto LABEL_265;
          v67 = ProduceWFromA(*((_DWORD *)v13 + 7), *(LPCCH *)(a4 + 16));
          v52 = (void *)v67;
          if ( !v67 )
            return -1;
          v65 = v66;
          *(_QWORD *)(a4 + 16) = v67;
LABEL_265:
          inserted = ListView_OnInsertColumn(v13, (unsigned int)a3, a4);
          if ( !v52 )
            return inserted;
          *(_QWORD *)(a4 + 16) = v65;
          goto LABEL_213;
        case 0x101Cu:
          LODWORD(result) = ListView_OnDeleteColumn((int)v13);
          return (int)result;
        case 0x101Du:
          v76 = v13[2] & 3;
          if ( v76 == 1 )
          {
            memset(lParam, 0, sizeof(lParam));
            v77 = (HWND)v13[55];
            *(_DWORD *)lParam = 1;
            SendMessageW(v77, 0x120Bu, (int)a3, (LPARAM)lParam);
            LODWORD(result) = *(_DWORD *)&lParam[4];
            return (int)result;
          }
          if ( v76 != 3 )
            goto LABEL_268;
          LODWORD(result) = *((_DWORD *)v13 + 63);
          return (int)result;
        case 0x101Eu:
          LODWORD(result) = ListView_ISetColumnWidth(v13, (unsigned int)a3, (unsigned int)(__int16)a4, 1);
          return (int)result;
        case 0x101Fu:
          v56 = v13[55];
          if ( a4 && IsWindow((HWND)a4) )
            v13[55] = a4;
          return v56;
        case 0x1021u:
          return (__int64)ListView_OnCreateDragImage((__int64)v13, (int)a3, (LONG *)a4);
        case 0x1022u:
          if ( !a4 )
            return 0;
          ListView_GetViewRect2(v13, a4, *((unsigned int *)v13 + 41), *((unsigned int *)v13 + 42));
          return v19;
        case 0x1023u:
          return *((unsigned int *)v13 + 26);
        case 0x1024u:
          *((_DWORD *)v13 + 26) = a4;
          return v19;
        case 0x1025u:
          return *((unsigned int *)v13 + 27);
        case 0x1026u:
          *((_DWORD *)v13 + 27) = a4;
          return v19;
        case 0x1027u:
          v78 = v13[2] & 3;
          if ( v78 == 1 )
          {
            v79 = *((_DWORD *)v13 + 115);
            goto LABEL_319;
          }
          if ( v78 != 3 )
            goto LABEL_268;
          v80 = *((_DWORD *)v13 + 62);
          goto LABEL_322;
        case 0x1028u:
          v81 = v13[2] & 3;
          if ( v81 == 1 )
          {
            v79 = *((_DWORD *)v13 + 42) - *((_DWORD *)v13 + 112);
LABEL_319:
            LODWORD(result) = v79 / *((_DWORD *)v13 + 64);
          }
          else if ( v81 == 3 )
          {
            v80 = *((_DWORD *)v13 + 41);
LABEL_322:
            LODWORD(result) = *((_DWORD *)v13 + 65) * (v80 / *((_DWORD *)v13 + 63));
          }
          else
          {
            LODWORD(result) = *((_DWORD *)v13 + 128);
          }
          break;
        case 0x1029u:
          if ( !a4 || (((v13[2] & 3) - 1) & 0xFFFFFFFD) == 0 )
            return 0;
          *(_QWORD *)a4 = v13[37];
          return v19;
        case 0x102Au:
          ListView_OnUpdate(v13, (unsigned int)a3);
          UpdateWindow((HWND)*v13);
          return v19;
        case 0x102Bu:
          if ( !a4 )
            return 0;
          LODWORD(result) = ListView_OnSetItemState(
                              v13,
                              (unsigned int)a3,
                              *(unsigned int *)(a4 + 12),
                              *(unsigned int *)(a4 + 16));
          return (int)result;
        case 0x102Cu:
          LODWORD(result) = ListView_OnGetItemState(v13, (unsigned int)a3, (unsigned int)a4);
          return (unsigned int)result;
        case 0x102Du:
          if ( !a4 )
            goto LABEL_268;
          *(_DWORD *)a4 = 1;
          *(_DWORD *)(a4 + 4) = (_DWORD)a3;
          if ( !(unsigned int)ListView_OnGetItemA(v13, a4) )
            goto LABEL_268;
          LODWORD(result) = lstrlenA(*(LPCSTR *)(a4 + 24));
          return (int)result;
        case 0x102Eu:
          if ( !a4 )
            return 0;
          v68 = *(const CHAR **)(a4 + 24);
          v69 = *(_DWORD *)(a4 + 8);
          v70 = 0;
          if ( v68 )
          {
            v70 = ProduceWFromA(*((_DWORD *)v13 + 7), v68);
            if ( !v70 )
              return 0;
          }
          v21 = (v13[2] & 0x1000) == 0;
          memset(lParam, 0, 56);
          if ( v21 )
          {
            ListView_InvalidateTTLastHit(v13, (unsigned int)a3, v10, v11);
            *(_DWORD *)lParam = 1;
            *(_QWORD *)&lParam[24] = v70;
            *(_DWORD *)&lParam[4] = (_DWORD)a3;
            *(_DWORD *)&lParam[8] = v69;
            v59 = ListView_OnSetItem(v71);
          }
          else
          {
            v59 = 0;
          }
          if ( (unsigned __int64)(v70 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
            return v59;
          v64 = (void *)v70;
          goto LABEL_258;
        case 0x102Fu:
          LODWORD(result) = ListView_OnSetItemCount((int)v13, (int)a3);
          return (int)result;
        case 0x1030u:
          v82 = 1;
          goto LABEL_336;
        case 0x1031u:
          if ( !a4 )
            return 0;
LABEL_229:
          LODWORD(result) = ListView_OnSetItemPosition((int)v13);
          return (int)result;
        case 0x1032u:
          if ( (v13[2] & 0x1000) != 0 )
            (*(void (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)v13[62] + 104LL))(v13[62], v13 + 23);
          return *((unsigned int *)v13 + 46);
        case 0x1033u:
          if ( a3 )
          {
            v73 = *((unsigned __int16 *)v13 + 128);
            v74 = *((unsigned __int16 *)v13 + 126);
          }
          else
          {
            v73 = *((unsigned __int16 *)v13 + 134);
            v74 = *((unsigned __int16 *)v13 + 132);
          }
          LODWORD(result) = (v73 << 16) | v74;
          return (int)result;
        case 0x1034u:
          v72 = (HWND)*v13;
          if ( GetFocus() != v72 )
            return 0;
          LODWORD(result) = GetIncrementSearchStringA(v13 + 79, *((unsigned int *)v13 + 7), a4);
          return (int)result;
        case 0x1035u:
          v56 = (unsigned int)ListView_OnSetIconSpacing(v13, a4);
          if ( (v13[9] & 0x12) == 0x12 && (v13[2] & 0x100) != 0 && (v13[2] & 1) == 0 )
            ListView_OnArrange(v13, 0);
          return v56;
        case 0x1036u:
          LODWORD(result) = ListView_ExtendedStyleChange((_DWORD)v13);
          return (unsigned int)result;
        case 0x1037u:
          return *((unsigned int *)v13 + 19);
        case 0x1038u:
          LODWORD(result) = ListView_OnGetSubItemRect(v13, (unsigned int)a3, a4);
          return (int)result;
        case 0x1039u:
          LODWORD(result) = ListView_OnSubItemHitTest(v13, a4);
          return (int)result;
        case 0x103Au:
          v75 = 4626;
          return SendMessageW((HWND)v13[55], v75, (WPARAM)a3, a4);
        default:
          goto LABEL_440;
      }
      return (int)result;
    }
    if ( a2 > 0x104D )
    {
      if ( a2 <= 0x1073 )
      {
        if ( a2 == 4211 )
        {
          if ( a4 && (*(_DWORD *)a4 = 1, *(_DWORD *)(a4 + 4) = (_DWORD)a3, (unsigned int)ListView_OnGetItem(v13, a4)) )
            LODWORD(result) = lstrlenW(*(LPCWSTR *)(a4 + 24));
          else
LABEL_268:
            LODWORD(result) = 0;
        }
        else if ( a2 > 0x1053 )
        {
          switch ( a2 )
          {
            case 0x1054u:
              *((_DWORD *)v13 + 14) &= ~0x40u;
              Str_Set(v13 + 76, 0);
              if ( !*((_DWORD *)v13 + 128) )
                InvalidateRect((HWND)*v13, 0, 1);
              return v19;
            case 0x1057u:
              LODWORD(result) = ListView_OnGetStringWidth(v13, a4, 0);
              break;
            case 0x105Fu:
              LODWORD(result) = ListView_OnGetColumn(v13, (unsigned int)a3, a4);
              break;
            case 0x1060u:
              LODWORD(result) = ListView_OnSetColumn(v13, (unsigned int)a3, a4);
              break;
            case 0x1061u:
              LODWORD(result) = ListView_OnInsertColumn(v13, (unsigned int)a3, a4);
              break;
            default:
              goto LABEL_440;
          }
        }
        else
        {
          switch ( a2 )
          {
            case 0x1053u:
              LODWORD(result) = ListView_OnFindItem(v13, (unsigned int)a3, a4);
              break;
            case 0x104Eu:
              return v13[26];
            case 0x104Fu:
              return *((unsigned int *)v13 + 154);
            case 0x1050u:
              *((_DWORD *)v13 + 154) = a4;
              return v19;
            case 0x1051u:
              v82 = 0;
LABEL_336:
              LODWORD(result) = ListView_OnSortItems(v13, a3, a4, v82);
              break;
            default:
              if ( (_DWORD)a3 )
              {
                if ( (_DWORD)a3 != 1 )
                  return 0;
                v93 = 63;
              }
              else
              {
                v93 = 62;
              }
              v94 = v13[v93];
              if ( v94 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
              v13[v93] = a4;
              if ( a4 )
                (*(void (__fastcall **)(LPARAM))(*(_QWORD *)a4 + 8LL))(a4);
              return v19;
          }
        }
        return (int)result;
      }
      switch ( a2 )
      {
        case 0x1074u:
          if ( !a4 )
            return 0;
          LODWORD(result) = 0;
          v21 = (v13[2] & 0x1000) == 0;
          memset(lParam, 0, 56);
          if ( v21 )
          {
            ListView_InvalidateTTLastHit(v13, (unsigned int)a3, *(_QWORD *)(a4 + 24), *(unsigned int *)(a4 + 8));
            *(_DWORD *)lParam = 1;
            *(_QWORD *)&lParam[24] = v115;
            *(_DWORD *)&lParam[4] = (_DWORD)a3;
            *(_DWORD *)&lParam[8] = v116;
LABEL_502:
            LODWORD(result) = ListView_OnSetItem(v87);
          }
          return (int)result;
        case 0x1075u:
          v114 = (HWND)*v13;
          if ( GetFocus() != v114 )
            return 0;
          LODWORD(result) = GetIncrementSearchString(v13 + 79, a4);
          return (int)result;
        case 0x1076u:
          return ListView_OnEditLabel((int)v13, (int)a3);
        case 0x108Au:
          LODWORD(result) = ListView_OnSetBkImage(v13, a4);
          return (int)result;
      }
      if ( a2 != 4235 )
        goto LABEL_440;
      result = 0;
      if ( !a4 )
        return result;
      *(_DWORD *)a4 = *((_DWORD *)v13 + 142);
      result = 0;
      if ( (v13[71] & 3) != 0 )
      {
        if ( (v13[71] & 3) == 1 )
        {
LABEL_353:
          *(_QWORD *)(a4 + 8) = v13[72];
        }
        else
        {
          if ( (v13[71] & 3) != 2 )
            goto LABEL_355;
          v113 = *(wchar_t **)(a4 + 16);
          if ( !v113 )
            goto LABEL_355;
          StringCchCopyW(v113, *(unsigned int *)(a4 + 24), (STRSAFE_LPCWSTR)v13[73]);
        }
      }
    }
    else
    {
      if ( a2 == 4173 )
      {
        LODWORD(result) = ListView_OnInsertItem((_DWORD)v13);
        return (int)result;
      }
      switch ( a2 )
      {
        case 0x103Cu:
          v88 = *((int *)v13 + 133);
          if ( (_DWORD)a3 == -1 || (unsigned int)a3 < *((_DWORD *)v13 + 128) )
            ListView_OnSetHotItem((int)v13);
          return v88;
        case 0x103Du:
          return *((int *)v13 + 133);
        case 0x103Eu:
          result = v13[69];
          v13[69] = a4;
          return result;
        case 0x103Fu:
          result = v13[69];
          if ( !result )
          {
            result = (__int64)LoadCursorW(0, (LPCWSTR)0x7F89);
            if ( !result )
              result = (__int64)LoadCursorW(g_hinst, (LPCWSTR)0x6C);
            v13[69] = result;
          }
          return result;
        case 0x1040u:
          v89 = (unsigned int)(__int16)a4;
          v90 = (unsigned int)SWORD1(a4);
          if ( (_DWORD)a3 == -1 )
            LODWORD(a3) = *((_DWORD *)v13 + 128);
          if ( (_DWORD)v89 == -1 )
            v89 = *((unsigned int *)v13 + 41);
          if ( (_DWORD)v90 == -1 )
            v90 = *((unsigned int *)v13 + 42);
          LODWORD(result) = ((__int64 (__fastcall *)(_QWORD *, _QWORD, __int64, __int64))pfnListView_ApproximateViewRect[v13[2] & 3])(
                              v13,
                              (unsigned int)a3,
                              v89,
                              v90);
          return (unsigned int)result;
        case 0x1041u:
          ListView_OnSetWorkAreas((__int64)v13, (int)a3, (const RECT *)a4);
          return 0;
        case 0x1042u:
          return *((int *)v13 + 37);
        case 0x1043u:
          result = *((int *)v13 + 37);
          if ( (_DWORD)a4 == -1 || (unsigned int)a4 < *((_DWORD *)v13 + 128) )
            *((_DWORD *)v13 + 37) = a4;
          return result;
        case 0x1044u:
          v84 = *(_OWORD *)(a4 + 16);
          v85 = *(_QWORD *)(a4 + 32);
          v86 = _mm_cvtsi128_si32(*(__m128i *)a4);
          *(_OWORD *)lParam = *(_OWORD *)a4;
          *(_QWORD *)&lParam[32] = v85;
          *(_OWORD *)&lParam[16] = v84;
          if ( (v86 & 3) != 2 || !(_QWORD)v84 )
            goto LABEL_360;
          *(_QWORD *)&lParam[16] = ProduceWFromA(*((_DWORD *)v13 + 7), (LPCCH)v84);
          if ( *(_QWORD *)&lParam[16] )
          {
            LODWORD(v12) = 1;
LABEL_360:
            v59 = ListView_OnSetBkImage(v13, lParam);
            if ( (_DWORD)v12 )
            {
              v64 = *(void **)&lParam[16];
              if ( (unsigned __int64)(*(_QWORD *)&lParam[16] - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
LABEL_258:
                LocalFree(v64);
            }
          }
          else
          {
            return 0;
          }
          return v59;
        case 0x1045u:
          result = 0;
          if ( !a4 )
            return result;
          *(_DWORD *)a4 = *((_DWORD *)v13 + 142);
          result = 0;
          if ( (v13[71] & 3) == 0 )
            break;
          if ( (v13[71] & 3) == 1 )
            goto LABEL_353;
          if ( (v13[71] & 3) != 2 )
            goto LABEL_355;
          lpMultiByteStr = *(CHAR **)(a4 + 16);
          if ( !lpMultiByteStr )
            goto LABEL_355;
          WideCharToMultiByte(*((_DWORD *)v13 + 7), 0, (LPCWCH)v13[73], -1, lpMultiByteStr, *(_DWORD *)(a4 + 24), 0, 0);
          break;
        case 0x1046u:
          while ( 1 )
          {
            v91 = *((_DWORD *)v13 + 43);
            v92 = v91;
            if ( v91 >= (int)a3 )
              v92 = (int)a3;
            if ( (int)v12 >= v92 )
              break;
            if ( (int)v12 >= v91 )
              *(_OWORD *)(a4 + 16LL * (int)v12) = 0;
            else
              CopyRect((LPRECT)(a4 + 16LL * (int)v12), (const RECT *)(16LL * (int)v12 + v13[22]));
            LODWORD(v12) = (_DWORD)v12 + 1;
          }
          return 0;
        case 0x1047u:
          result = *((unsigned int *)v13 + 137);
          *((_DWORD *)v13 + 137) = a4;
          return result;
        case 0x1048u:
          return *((unsigned int *)v13 + 137);
        case 0x1049u:
          if ( a4 )
            *(_DWORD *)a4 = *((_DWORD *)v13 + 43);
          return 0;
        case 0x104Au:
          result = v13[26];
          v13[26] = a3;
          return result;
        case 0x104Bu:
          LODWORD(result) = ListView_OnGetItem(v13, a4);
          return (int)result;
        case 0x104Cu:
          v87 = (int)v13;
          goto LABEL_502;
        default:
          goto LABEL_440;
      }
    }
    result = 1;
LABEL_355:
    *(_DWORD *)(a4 + 28) = *((_DWORD *)v13 + 148);
    *(_DWORD *)(a4 + 32) = *((_DWORD *)v13 + 149);
    return result;
  }
  if ( a2 == 4117 )
  {
    v57 = *((_DWORD *)v13 + 128);
    if ( (int)a3 < v57 )
    {
      v58 = v57 - 1;
      if ( (int)a4 < v57 )
        v58 = a4;
      while ( (int)a3 <= v58 )
      {
        ListView_InvalidateItemEx((__int64)v13, (int)a3, 0, 5u, 0);
        LODWORD(a3) = (_DWORD)a3 + 1;
      }
    }
    return v19;
  }
  if ( a2 > 0x201 )
  {
    if ( a2 > 0x1003 )
    {
      switch ( a2 )
      {
        case 0x1004u:
          if ( (v13[2] & 0x1000) != 0 )
            return *((int *)v13 + 128);
          v55 = (int *)v13[8];
          if ( !v55 )
            return 0;
          return *v55;
        case 0x1005u:
          LODWORD(result) = ListView_OnGetItemA(v13, a4);
          return (int)result;
        case 0x1006u:
          if ( !a4 )
            return 0;
          v41 = 0;
          v42 = 0;
          if ( (*(_BYTE *)a4 & 1) == 0 )
            goto LABEL_190;
          v43 = *(_QWORD *)(a4 + 24);
          if ( !v43 )
            goto LABEL_190;
          v44 = ProduceWFromA(*((_DWORD *)v13 + 7), *(LPCCH *)(a4 + 24));
          v41 = (void *)v44;
          if ( !v44 )
            return 0;
          v42 = v43;
          *(_QWORD *)(a4 + 24) = v44;
LABEL_190:
          StringWidth = ListView_OnSetItem((int)v13);
          if ( !v41 )
            return StringWidth;
          *(_QWORD *)(a4 + 24) = v42;
          goto LABEL_192;
        case 0x1007u:
          if ( !a4 )
            return -1;
          v46 = 0;
          v47 = 0;
          if ( (*(_BYTE *)a4 & 1) == 0 )
            goto LABEL_201;
          v48 = *(_QWORD *)(a4 + 24);
          if ( !v48 )
            goto LABEL_201;
          v49 = ProduceWFromA(*((_DWORD *)v13 + 7), *(LPCCH *)(a4 + 24));
          v46 = (void *)v49;
          if ( !v49 )
            return -1;
          v47 = v48;
          *(_QWORD *)(a4 + 24) = v49;
LABEL_201:
          v50 = ListView_OnInsertItem((_DWORD)v13);
          if ( v46 )
          {
            *(_QWORD *)(a4 + 24) = v47;
            if ( v46 != (void *)-1LL )
              LocalFree(v46);
          }
          return v50;
        case 0x1008u:
          LODWORD(result) = ListView_OnDeleteItem((int)v13);
          return (int)result;
        case 0x1009u:
          v56 = (int)ListView_OnDeleteAllItems(v13);
          MyNotifyWinEvent(32772, hWnd, 4294967292LL);
          MyNotifyWinEvent(32769, *v13, 4294967292LL);
          MyNotifyWinEvent(0x8000, *v13, 4294967292LL);
          v13[65] = 0;
          return v56;
        case 0x100Au:
          return *((unsigned int *)v13 + 40);
        case 0x100Bu:
          *((_DWORD *)v13 + 40) = (_DWORD)a3;
          return v19;
        case 0x100Cu:
          LODWORD(result) = ListView_OnGetNextItem(v13, (unsigned int)a3, (unsigned int)a4);
          return (int)result;
        case 0x100Du:
          if ( !a4 )
            return -1;
          if ( (*(_BYTE *)a4 & 0x41) != 0 )
          {
            v52 = 0;
          }
          else
          {
            v12 = *(char **)(a4 + 8);
            v51 = ProduceWFromA(*((_DWORD *)v13 + 7), v12);
            v52 = (void *)v51;
            if ( !v51 )
              return -1;
            *(_QWORD *)(a4 + 8) = v51;
          }
          inserted = ListView_OnFindItem(v13, (unsigned int)a3, a4);
          if ( !v52 )
            return inserted;
          *(_QWORD *)(a4 + 8) = v12;
          break;
        case 0x100Eu:
          LODWORD(result) = ListView_OnGetItemRect(v13, (unsigned int)a3, a4);
          return (int)result;
        case 0x100Fu:
          goto LABEL_229;
        case 0x1010u:
          LODWORD(result) = ListView_OnGetItemPosition(v13, (unsigned int)a3, a4);
          return (int)result;
        case 0x1011u:
          if ( a4 && (v54 = ProduceWFromA(*((_DWORD *)v13 + 7), (LPCCH)a4), (v41 = (void *)v54) != 0) )
          {
            StringWidth = ListView_OnGetStringWidth(v13, v54, 0);
LABEL_192:
            if ( v41 != (void *)-1LL )
              LocalFree(v41);
          }
          else
          {
            return 0;
          }
          return StringWidth;
        case 0x1012u:
          LODWORD(result) = ListView_OnHitTest(v13, a4);
          return (int)result;
        case 0x1013u:
          LODWORD(result) = ListView_OnEnsureVisible((int)v13, (int)a3);
          return (int)result;
        case 0x1014u:
          LODWORD(v118) = (_DWORD)a3;
          v117 = a4;
          if ( !(unsigned int)ListView_ValidateScrollParams(v13, &v118, &v117)
            || !(unsigned int)ListView_OnScroll(v13, (unsigned int)v118, v117) )
          {
            return 0;
          }
          return v19;
        default:
          goto LABEL_440;
      }
LABEL_213:
      if ( v52 != (void *)-1LL )
        LocalFree(v52);
      return inserted;
    }
    if ( a2 == 4099 )
      return ListView_OnSetImageList(v13, a4, (unsigned int)a3);
    if ( a2 <= 0x2A3 )
    {
      if ( a2 == 675 )
      {
        ListView_OnSetHotItem((int)v13);
        *((_DWORD *)v13 + 136) = -1;
        goto LABEL_5;
      }
      if ( a2 == 514 )
        goto LABEL_151;
      if ( a2 != 515 )
      {
        if ( a2 == 516 )
        {
LABEL_145:
          v37 = v13[26];
          if ( v37 )
            RelayToToolTips(v37, (_DWORD)hWnd, a2, (_DWORD)a3, a4);
LABEL_150:
          ListView_HandleMouse((_DWORD)v13, (_DWORD)a3, 0);
          goto LABEL_5;
        }
        if ( a2 == 517 )
        {
LABEL_151:
          v35 = v13[26];
          if ( !v35 )
            goto LABEL_5;
          v36 = a2;
          goto LABEL_144;
        }
        if ( a2 != 518 )
        {
          if ( a2 == 519 )
          {
            SetFocus(hWnd);
            if ( !IsWindow(hWnd) )
              goto LABEL_5;
            v35 = v13[26];
            if ( !v35 )
              goto LABEL_5;
            v36 = 519;
LABEL_144:
            RelayToToolTips(v35, (_DWORD)hWnd, v36, (_DWORD)a3, a4);
            goto LABEL_5;
          }
          if ( a2 != 520 )
          {
            if ( a2 == 673 )
            {
              ListView_OnMouseHover(v13, (unsigned int)(__int16)a4, (unsigned int)SWORD1(a4));
              goto LABEL_5;
            }
            goto LABEL_440;
          }
          goto LABEL_151;
        }
      }
      v38 = v13[26];
      if ( v38 )
        RelayToToolTips(v38, (_DWORD)hWnd, a2, (_DWORD)a3, a4);
      goto LABEL_150;
    }
    if ( a2 != 783 )
    {
      if ( a2 != 785 )
      {
        switch ( a2 )
        {
          case 0x318u:
            goto LABEL_176;
          case 0x400u:
            if ( *((_DWORD *)v13 + 132) )
            {
              ListView_Recompute((int)v13);
              ListView_UpdateScrollBars(v13);
            }
            return 0;
          case 0x401u:
            goto LABEL_173;
          case 0x1000u:
            return *(unsigned int *)((char *)v13 + ((v13[2] & 0x8000000 | 0xC0000000uLL) >> 25));
        }
        if ( a2 != 4097 )
        {
          if ( a2 == 4098 )
          {
            if ( !(_DWORD)a3 )
              return v13[34];
            v39 = (_DWORD)a3 - 1;
            if ( !v39 )
              return v13[29];
            if ( v39 == 1 )
              return v13[60];
            return 0;
          }
          goto LABEL_440;
        }
        *((_DWORD *)v13 + 18) |= 0x800u;
        if ( (v13[2] & 0x8000000) != 0 )
        {
          *((_DWORD *)v13 + 25) = a4;
          return v19;
        }
        LODWORD(result) = ListView_OnSetBkColor(v13, (unsigned int)a4);
        return (int)result;
      }
      if ( a3 == (HDC)hWnd )
        goto LABEL_5;
    }
    ListView_Realize(v13, 0, a2 == 785);
    return v19;
  }
  if ( a2 == 513 )
    goto LABEL_145;
  if ( a2 > 0x53 )
  {
    if ( a2 <= 0x102 )
    {
      switch ( a2 )
      {
        case 0x102u:
          v28 = *((_DWORD *)v13 + 48);
          if ( !v28 )
          {
            ListView_OnChar((_DWORD)v13);
            return 0;
          }
          *((_DWORD *)v13 + 48) = v28 - 1;
          return v19;
        case 0x55u:
          return CIHandleNotifyFormat(v13, a4);
        case 0x7Cu:
          if ( (_DWORD)a3 == -16 )
            *(_DWORD *)(a4 + 4) ^= (*(_DWORD *)a4
                                  ^ *(_DWORD *)(a4 + 4))
                                 & ((*((_DWORD *)v13 + 19) & 0x200) != 0 ? 4099 : 4096);
          return 0;
        case 0x7Du:
          ListView_OnStyleChanged((int)v13);
          return 0;
        case 0x82u:
          ListView_OnNCDestroy(v13);
          return 0;
        case 0x87u:
          return 129;
      }
      if ( a2 != 160 )
      {
        if ( a2 != 256 )
        {
          if ( a2 == 257 )
          {
            *((_DWORD *)v13 + 106) = 0;
            goto LABEL_5;
          }
          goto LABEL_440;
        }
LABEL_95:
        ListView_OnKey((int)v13, WORD1(a4));
        goto LABEL_5;
      }
      goto LABEL_151;
    }
    switch ( a2 )
    {
      case 0x104u:
        goto LABEL_95;
      case 0x10Fu:
        if ( !g_fDBCSInputEnabled || ((unsigned __int64)GetKeyboardLayout(0) & 0xF000FFFF) != 0xE0000412 )
          goto LABEL_5;
        if ( (unsigned int)ListView_OnImeComposition((int)v13) )
        {
          a4 &= ~0x800uLL;
          goto LABEL_5;
        }
        return 0;
      case 0x111u:
        ListView_OnCommand((_DWORD)v13);
        return 0;
      case 0x113u:
        ListView_OnTimer((int)v13, (unsigned int)a3);
        return 0;
      case 0x114u:
      case 0x115u:
        ListView_OnHVScroll((_DWORD)v13);
        return 0;
      case 0x128u:
        if ( (unsigned int)CCOnUIState(v13, v9, (unsigned int)a3 & 0x1FFFF) )
        {
          v34 = *((_DWORD *)v13 + 36);
          if ( v34 >= 0 )
            ListView_InvalidateItemEx(v32, v34, 0, v33, 0);
        }
        goto LABEL_5;
      case 0x200u:
        v29 = v13[26];
        if ( v29 )
        {
          LODWORD(v118) = 0;
          v117 = 0;
          RelayToToolTips(v29, (_DWORD)hWnd, 512, (_DWORD)a3, a4);
          v30 = ((__int64 (__fastcall *)(_QWORD *, _QWORD, _QWORD, __int64 *, unsigned int *))pfnListView_ItemHitTest[v13[2] & 3])(
                  v13,
                  (unsigned int)(__int16)a4,
                  (unsigned int)SWORD1(a4),
                  &v118,
                  &v117);
          if ( __PAIR64__(v117, v30) != v13[27] )
          {
            v31 = (HWND)v13[26];
            if ( v31 )
              SendMessageW(v31, 0x41Cu, 0, 0);
          }
        }
        ListView_OnMouseMove((_DWORD)v13);
        goto LABEL_5;
    }
LABEL_440:
    v118 = 0;
    if ( (unsigned int)CCWndProc((_DWORD)v13, a2, (_DWORD)a3, v11, (__int64)&v118) )
      return v118;
    if ( a2 != 522 )
      goto LABEL_5;
    v96 = v95 & 0xC;
    v97 = gcWheelDelta - SWORD1(a3);
    LODWORD(v118) = SWORD1(a3);
    gcWheelDelta = v97;
    memset(lParam, 0, 28);
    v98 = v97 / 120;
    v117 = v97 / 120;
    if ( v97 / 120 )
      gcWheelDelta = v97 % 120;
    if ( v96 )
    {
      if ( ((unsigned __int8)a3 & 4) == 0 )
        goto LABEL_5;
      HIDWORD(EventTrack.hwndTrack) = 0;
      EventTrack.dwHoverTime = 0;
      EventTrack.cbSize = (__int16)a4;
      *(_QWORD *)&EventTrack.dwFlags = (unsigned int)SWORD1(a4);
      ScreenToClient(hWnd, (LPPOINT)&EventTrack);
      if ( (int)v118 <= 0
        || (int)ListView_OnSubItemHitTest(v13, &EventTrack) < 0
        || ((__int64)EventTrack.hwndTrack & 0xE) == 0
        || !v98 )
      {
        goto LABEL_5;
      }
      if ( GetKeyboardState(KeyState) )
      {
        v123 &= ~0x80u;
        SetKeyboardState(KeyState);
      }
      ListView_HandleMouse((_DWORD)v13, 0, 1);
      ListView_HandleMouse((_DWORD)v13, 0, 1);
      return v19;
    }
    if ( g_ucScrollLines )
    {
      if ( v98 )
      {
        WindowStyle = ListView_GetWindowStyle(v13);
        if ( (WindowStyle & 0x300000) != 0 )
        {
          v100 = WindowStyle & 0x200000;
          v101 = v100 != 0;
          v102 = ((__int64 (__fastcall *)(_QWORD *, bool))pfnListView_GetScrollUnitsPerLine[v13[2] & 3])(v13, v100 != 0);
          v103 = (HWND)*v13;
          v21 = (*((_DWORD *)v13 + 19) & 0x100) == 0;
          v104 = (HWND)*v13;
          LODWORD(v118) = v102;
          *(_QWORD *)lParam = 0x60000001CLL;
          if ( v21 )
          {
LABEL_452:
            ScrollInfo = GetScrollInfo(v104, v100 != 0, (LPSCROLLINFO)lParam);
            goto LABEL_453;
          }
          pdwRefData[0] = 0;
          GetWindowSubclass(v104, FlatSB_SubclassWndProc, 0, pdwRefData);
          if ( !pdwRefData[0] )
          {
            v104 = v103;
            goto LABEL_452;
          }
          if ( pdwRefData[0] == -1 || *(HWND *)(pdwRefData[0] + 264) != v103 )
          {
            ScrollInfo = 0;
            goto LABEL_453;
          }
          v111 = pdwRefData[0] + 292;
          if ( !v100 )
            v111 = pdwRefData[0] + 276;
          if ( (lParam[4] & 1) != 0 )
            *(_QWORD *)&lParam[8] = *(_QWORD *)v111;
          if ( (lParam[4] & 4) != 0 )
            *(_DWORD *)&lParam[20] = *(_DWORD *)(v111 + 12);
          if ( (lParam[4] & 2) != 0 )
            *(_DWORD *)&lParam[16] = *(_DWORD *)(v111 + 8);
          if ( (lParam[4] & 0x10) == 0 )
          {
LABEL_480:
            ScrollInfo = 1;
LABEL_453:
            if ( ScrollInfo )
            {
              v106 = v118;
              v107 = g_ucScrollLines;
              v108 = *(_DWORD *)&lParam[16] - v118;
              if ( (int)v118 > *(_DWORD *)&lParam[16] - (int)v118 )
                v108 = v118;
              v109 = v108 / (int)v118;
              if ( v109 < g_ucScrollLines )
                v107 = v109;
              ListView_DismissEdit((int)v13);
              ListView_ComOnScroll(v13, 5, *(_DWORD *)&lParam[20] + v106 * v117 * v107, v101, v106, -1);
              ListView_UpdateScrollBars(v13);
              v110 = (HWND)v13[26];
              if ( v110 )
                SendMessageW(v110, 0x41Cu, 0, 0);
              RelayToToolTips(v13[26], *v13, 160, 1, a4);
            }
            return v19;
          }
          if ( *(_QWORD *)(pdwRefData[0] + 88) )
          {
            if ( v100 )
            {
              if ( *(_DWORD *)(pdwRefData[0] + 104) )
              {
LABEL_476:
                v112 = *(_DWORD *)(pdwRefData[0] + 80);
LABEL_479:
                *(_DWORD *)&lParam[24] = v112;
                goto LABEL_480;
              }
            }
            else if ( !*(_DWORD *)(pdwRefData[0] + 104) )
            {
              goto LABEL_476;
            }
          }
          v112 = *(_DWORD *)(v111 + 12);
          goto LABEL_479;
        }
      }
    }
    return v19;
  }
  if ( a2 == 83 )
  {
    if ( a4 && (v13[2] & 3) == 1 && !*(_DWORD *)(a4 + 8) )
    {
      *(_QWORD *)(a4 + 16) = *v13;
      *(_DWORD *)(a4 + 8) = GetDlgCtrlID((HWND)*v13);
    }
    v18 = (HWND)*v13;
    v16 = 0;
    v17 = 83;
    return DefWindowProcW(v18, v17, (WPARAM)v16, a4);
  }
  if ( a2 > 0x15 )
  {
    switch ( a2 )
    {
      case 0x18u:
        v27 = *((_DWORD *)v13 + 18);
        if ( a3 )
        {
          if ( (v27 & 2) == 0 )
          {
            *((_DWORD *)v13 + 18) = v27 | 2;
            ListView_UpdateScrollBars(v13);
          }
        }
        else
        {
          *((_DWORD *)v13 + 18) = v27 & 0xFFFFFFFD;
        }
        goto LABEL_5;
      case 0x1Au:
        ListView_OnWinIniChange(v13, a3, a4);
        goto LABEL_5;
      case 0x20u:
        if ( !(unsigned int)ListView_OnSetCursorMsg(v13) )
          goto LABEL_5;
        return v19;
      case 0x30u:
        ListView_OnSetFont((__int64)v13, (HFONT)a3, a4);
        return 0;
      case 0x31u:
        return v13[11];
      case 0x3Du:
        if ( (_DWORD)a4 == -12 )
          return 65555;
        goto LABEL_5;
    }
    if ( a2 != 71 )
    {
      if ( a2 == 78 )
        return ListView_OnNotify(v13, v9, a4);
      goto LABEL_440;
    }
LABEL_173:
    ListView_OnWindowPosChanged((_DWORD)v13);
    goto LABEL_5;
  }
  switch ( a2 )
  {
    case 0x15u:
      InitGlobalColors();
      v25 = v13[9] & 0x800;
      if ( (v13[2] & 0x8000000) != 0 )
      {
        if ( !v25 )
          *((_DWORD *)v13 + 25) = g_clrWindow;
        v26 = g_clrBtnFace;
      }
      else
      {
        if ( v25 )
          goto LABEL_55;
        v26 = g_clrWindow;
      }
      ListView_OnSetBkColor(v13, v26);
LABEL_55:
      if ( (*((_BYTE *)v13 + 76) & 4) != 0 )
        ListView_InitCheckBoxes(v13, 0);
LABEL_57:
      InvalidateRect((HWND)*v13, 0, 1);
      goto LABEL_5;
    case 1u:
      return ((unsigned int)ListView_OnCreate(v13, a4) != 0) - 1LL;
    case 2u:
      ListView_OnDestroy(v13);
      return 0;
    case 5u:
      if ( v13[26] )
      {
        memset(lParam, 0, sizeof(lParam));
        if ( (*((_DWORD *)v13 + 19) & 0x4000) != 0 )
          ListView_InvalidateTTLastHit(v13, *((unsigned int *)v13 + 54), v23, v24);
        *(_QWORD *)&lParam[8] = *v13;
        *(_DWORD *)lParam = 64;
        *(_QWORD *)&lParam[16] = 0;
        GetClientRect(*(HWND *)&lParam[8], (LPRECT)&lParam[24]);
        SendMessageW((HWND)v13[26], 0x434u, 0, (LPARAM)lParam);
      }
      if ( (v13[71] & 3) == 0 || !*((_DWORD *)v13 + 148) && !*((_DWORD *)v13 + 149) )
        goto LABEL_5;
      goto LABEL_57;
    case 7u:
      ListView_OnSetFocus((int)v13);
      return 0;
    case 8u:
      ListView_OnKillFocus((_DWORD)v13);
      return 0;
    case 0xAu:
      ListView_EnableWindow(v13, a3 != 0);
      goto LABEL_5;
    case 0xBu:
      ListView_OnSetRedraw((int)v13);
      return 0;
    case 0xFu:
LABEL_176:
      ListView_OnPaint((__int64)v13, a3);
      return 0;
  }
  if ( a2 != 20 )
    goto LABEL_440;
  LODWORD(result) = ListView_OnEraseBkgnd(v13, a3);
  return (unsigned int)result;
}

```

## disassembly

```asm
0x18005c0a0  push    rbp
0x18005c0a2  push    rbx
0x18005c0a3  push    rsi
0x18005c0a4  push    rdi
0x18005c0a5  push    r12
0x18005c0a7  push    r13
0x18005c0a9  push    r14
0x18005c0ab  push    r15
0x18005c0ad  lea     rbp, [rsp-0D8h]
0x18005c0b5  sub     rsp, 1D8h
0x18005c0bc  mov     rax, cs:__security_cookie
0x18005c0c3  xor     rax, rsp
0x18005c0c6  mov     [rbp+110h+var_50], rax
0x18005c0cd  mov     r13d, edx
0x18005c0d0  mov     rsi, r9
0x18005c0d3  xor     edx, edx; nIndex
0x18005c0d5  mov     rbx, r8
0x18005c0d8  mov     r12, rcx
0x18005c0db  call    cs:__imp_GetWindowLongPtrW
0x18005c0e1  xor     r14d, r14d
0x18005c0e4  mov     rdi, rax
0x18005c0e7  test    rax, rax
0x18005c0ea  jnz     loc_18005C175
0x18005c0f0  cmp     r13d, 81h
0x18005c0f7  jnz     short loc_18005C167
0x18005c0f9  mov     edx, 298h; uBytes
0x18005c0fe  lea     ecx, [rax+40h]; uFlags
0x18005c101  call    cs:__imp_LocalAlloc
0x18005c107  mov     rdi, rax
0x18005c10a  test    rax, rax
0x18005c10d  jz      loc_18005C396
0x18005c113  or      r14, 0FFFFFFFFFFFFFFFFh
0x18005c117  mov     [rax], r12
0x18005c11a  lea     r15d, [r13-80h]
0x18005c11e  mov     [rax+90h], r14d
0x18005c125  mov     [rax+94h], r14d
0x18005c12c  mov     [rax+1D0h], r14d
0x18005c133  mov     [rax+204h], r14d
0x18005c13a  mov     [rax+1D8h], r15d
0x18005c141  mov     [rax+100h], r15d
0x18005c148  mov     dword ptr [rax+48h], 10h
0x18005c14f  call    cs:__imp_GetProcessHeap
0x18005c155  mov     r8, rdi; dwNewLong
0x18005c158  xor     edx, edx; nIndex
0x18005c15a  mov     rcx, r12; hWnd
0x18005c15d  mov     [rdi+78h], rax
0x18005c161  call    cs:__imp_SetWindowLongPtrW
0x18005c167  mov     r8, rbx
0x18005c16a  mov     edx, r13d
0x18005c16d  mov     rcx, r12
0x18005c170  jmp     loc_18005C514
0x18005c175  lea     eax, [r13-200h]
0x18005c17c  mov     r15d, 1
0x18005c182  cmp     eax, 0Dh
0x18005c185  ja      short loc_18005C1F5
0x18005c187  test    byte ptr [rdi+4Ch], 0C8h
0x18005c18b  jz      short loc_18005C1F5
0x18005c18d  mov     rax, [rdi]
0x18005c190  lea     rcx, [rbp+110h+EventTrack]; lpEventTrack
0x18005c194  mov     [rbp+110h+EventTrack.hwndTrack], rax
0x18005c198  mov     eax, [rdi+224h]
0x18005c19e  mov     [rbp+110h+EventTrack.dwHoverTime], eax
0x18005c1a1  mov     dword ptr [rbp+110h+EventTrack+14h], r14d
0x18005c1a5  mov     [rbp+110h+EventTrack.cbSize], 18h
0x18005c1ac  mov     [rbp+110h+EventTrack.dwFlags], 40000003h
0x18005c1b3  call    _TrackMouseEvent
0x18005c1b8  mov     ecx, [rbp+110h+EventTrack.dwFlags]
0x18005c1bb  xor     ecx, 0FFFFFFFEh
0x18005c1be  and     ecx, 3
0x18005c1c1  test    byte ptr [rdi+4Ch], 8
0x18005c1c5  mov     [rbp+110h+EventTrack.dwFlags], ecx
0x18005c1c8  jz      short loc_18005C1D0
0x18005c1ca  xor     ecx, r15d
0x18005c1cd  mov     [rbp+110h+EventTrack.dwFlags], ecx
0x18005c1d0  mov     rax, [rdi]
0x18005c1d3  mov     [rbp+110h+EventTrack.hwndTrack], rax
0x18005c1d7  mov     eax, [rdi+224h]
0x18005c1dd  mov     [rbp+110h+EventTrack.dwHoverTime], eax
0x18005c1e0  mov     [rbp+110h+EventTrack.cbSize], 18h
0x18005c1e7  test    cl, 3
0x18005c1ea  jz      short loc_18005C1F5
0x18005c1ec  lea     rcx, [rbp+110h+EventTrack]; lpEventTrack
0x18005c1f0  call    _TrackMouseEvent
0x18005c1f5  cmp     r13d, cs:g_uDragImages
0x18005c1fc  jnz     short loc_18005C20E
0x18005c1fe  mov     rdx, rsi
0x18005c201  mov     rcx, rdi
0x18005c204  call    LVGenerateDragImage
0x18005c209  jmp     loc_18005DC96
0x18005c20e  mov     ecx, 2
0x18005c213  lea     r11, cs:180000000h
0x18005c21a  mov     eax, 1015h
0x18005c21f  lea     r10d, [rcx+3]
0x18005c223  cmp     r13d, eax
0x18005c226  ja      loc_18005CE05
0x18005c22c  jz      loc_18005CDC3
0x18005c232  mov     eax, 201h
0x18005c237  cmp     r13d, eax
0x18005c23a  ja      loc_18005C80F
0x18005c240  jz      loc_18005C8E2
0x18005c246  cmp     r13d, 53h ; 'S'
0x18005c24a  ja      loc_18005C522
0x18005c250  jz      loc_18005C4E2
0x18005c256  cmp     r13d, 15h
0x18005c25a  ja      loc_18005C418
0x18005c260  jz      loc_18005C3B8
0x18005c266  mov     eax, r13d
0x18005c269  sub     eax, r15d
0x18005c26c  jz      loc_18005C39D
0x18005c272  sub     eax, r15d
0x18005c275  jz      loc_18005C38E
0x18005c27b  sub     eax, 3
0x18005c27e  jz      short loc_18005C2FB
0x18005c280  sub     eax, ecx
0x18005c282  jz      short loc_18005C2EB
0x18005c284  sub     eax, r15d
0x18005c287  jz      short loc_18005C2DB
0x18005c289  sub     eax, ecx
0x18005c28b  jz      short loc_18005C2C5
0x18005c28d  sub     eax, r15d
0x18005c290  jz      short loc_18005C2B6
0x18005c292  sub     eax, 4
0x18005c295  jz      loc_18005CA7B
0x18005c29b  cmp     eax, r10d
0x18005c29e  jnz     def_18005CAE5; jumptable 000000018005CAE5 default case
0x18005c2a4  mov     rdx, rbx
0x18005c2a7  mov     rcx, rdi
0x18005c2aa  call    ListView_OnEraseBkgnd
0x18005c2af  mov     eax, eax
0x18005c2b1  jmp     loc_18005DC96
0x18005c2b6  mov     edx, ebx
0x18005c2b8  mov     rcx, rdi; int
0x18005c2bb  call    ListView_OnSetRedraw
0x18005c2c0  jmp     loc_18005C396
0x18005c2c5  test    rbx, rbx
0x18005c2c8  mov     edx, r14d
0x18005c2cb  mov     rcx, rdi
0x18005c2ce  setnz   dl
0x18005c2d1  call    ListView_EnableWindow
0x18005c2d6  jmp     loc_18005C167
0x18005c2db  mov     rdx, rbx
0x18005c2de  mov     rcx, rdi
0x18005c2e1  call    ListView_OnKillFocus
0x18005c2e6  jmp     loc_18005C396
0x18005c2eb  mov     rdx, rbx
0x18005c2ee  mov     rcx, rdi; int
0x18005c2f1  call    ListView_OnSetFocus
0x18005c2f6  jmp     loc_18005C396
0x18005c2fb  cmp     [rdi+0D0h], r14
0x18005c302  jz      short loc_18005C365
0x18005c304  xor     edx, edx; Val
0x18005c306  lea     rcx, [rsp+210h+lParam]; void *
0x18005c30b  lea     r8d, [rdx+40h]; Size
0x18005c30f  call    memset
0x18005c314  test    dword ptr [rdi+4Ch], 4000h
0x18005c31b  jz      short loc_18005C32B
0x18005c31d  mov     edx, [rdi+0D8h]
0x18005c323  mov     rcx, rdi
0x18005c326  call    ListView_InvalidateTTLastHit
0x18005c32b  mov     rcx, [rdi]; hWnd
0x18005c32e  lea     rdx, [rsp+210h+Rect.right]; lpRect
0x18005c333  mov     [rsp+210h+lParam+8], rcx
0x18005c338  mov     dword ptr [rsp+210h+lParam], 40h ; '@'
0x18005c340  mov     qword ptr [rsp+210h+Rect.left], r14
0x18005c345  call    cs:__imp_GetClientRect
0x18005c34b  mov     rcx, [rdi+0D0h]; hWnd
0x18005c352  lea     r9, [rsp+210h+lParam]; lParam
0x18005c357  xor     r8d, r8d; wParam
0x18005c35a  mov     edx, 434h; Msg
0x18005c35f  call    cs:__imp_SendMessageW
0x18005c365  test    byte ptr [rdi+238h], 3
0x18005c36c  jz      loc_18005C167
0x18005c372  cmp     [rdi+250h], r14d
0x18005c379  jnz     loc_18005C405
0x18005c37f  cmp     [rdi+254h], r14d
0x18005c386  jz      loc_18005C167
0x18005c38c  jmp     short loc_18005C405
0x18005c38e  mov     rcx, rdi
0x18005c391  call    ListView_OnDestroy
0x18005c396  xor     eax, eax
0x18005c398  jmp     loc_18005DC96
0x18005c39d  mov     rdx, rsi
0x18005c3a0  mov     rcx, rdi
0x18005c3a3  call    ListView_OnCreate
0x18005c3a8  neg     eax
0x18005c3aa  sbb     rax, rax
0x18005c3ad  neg     rax
0x18005c3b0  sub     rax, r15
0x18005c3b3  jmp     loc_18005DC96
0x18005c3b8  call    InitGlobalColors
0x18005c3bd  mov     eax, [rdi+48h]
0x18005c3c0  and     eax, 800h
0x18005c3c5  test    dword ptr [rdi+10h], 8000000h
0x18005c3cc  jz      short loc_18005C3E3
0x18005c3ce  test    eax, eax
0x18005c3d0  jnz     short loc_18005C3DB
0x18005c3d2  mov     eax, cs:g_clrWindow
0x18005c3d8  mov     [rdi+64h], eax
0x18005c3db  mov     edx, cs:g_clrBtnFace
0x18005c3e1  jmp     short loc_18005C3ED
0x18005c3e3  test    eax, eax
0x18005c3e5  jnz     short loc_18005C3F5
0x18005c3e7  mov     edx, cs:g_clrWindow
0x18005c3ed  mov     rcx, rdi
0x18005c3f0  call    ListView_OnSetBkColor
0x18005c3f5  test    byte ptr [rdi+4Ch], 4
0x18005c3f9  jz      short loc_18005C405
0x18005c3fb  xor     edx, edx
0x18005c3fd  mov     rcx, rdi
0x18005c400  call    ListView_InitCheckBoxes
0x18005c405  mov     rcx, [rdi]; hWnd
0x18005c408  mov     r8d, r15d; bErase
0x18005c40b  xor     edx, edx; lpRect
0x18005c40d  call    cs:__imp_InvalidateRect
0x18005c413  jmp     loc_18005C167
0x18005c418  mov     eax, r13d
0x18005c41b  sub     eax, 18h
0x18005c41e  jz      loc_18005C4B5
0x18005c424  sub     eax, ecx
0x18005c426  jz      short loc_18005C4A2
0x18005c428  sub     eax, 6
0x18005c42b  jz      short loc_18005C48D
0x18005c42d  sub     eax, 10h
0x18005c430  jz      short loc_18005C47A
0x18005c432  sub     eax, r15d
0x18005c435  jz      short loc_18005C471
0x18005c437  sub     eax, 0Ch
0x18005c43a  jz      short loc_18005C45E
0x18005c43c  sub     eax, 0Ah
0x18005c43f  jz      loc_18005CA49
0x18005c445  cmp     eax, 7
0x18005c448  jnz     def_18005CAE5; jumptable 000000018005CAE5 default case
0x18005c44e  mov     r8, rsi
0x18005c451  mov     rcx, rdi
0x18005c454  call    ListView_OnNotify
0x18005c459  jmp     loc_18005DC96
0x18005c45e  cmp     esi, 0FFFFFFF4h
0x18005c461  jnz     loc_18005C167
0x18005c467  mov     eax, 10013h
0x18005c46c  jmp     loc_18005DC96
0x18005c471  mov     rax, [rdi+58h]
0x18005c475  jmp     loc_18005DC96
0x18005c47a  mov     r8d, esi
0x18005c47d  mov     rdx, rbx
0x18005c480  mov     rcx, rdi
0x18005c483  call    ListView_OnSetFont
0x18005c488  jmp     loc_18005C396
0x18005c48d  mov     rcx, rdi
0x18005c490  call    ListView_OnSetCursorMsg
0x18005c495  test    eax, eax
0x18005c497  jnz     loc_18005CAAF
0x18005c49d  jmp     loc_18005C167
0x18005c4a2  mov     r8, rsi
0x18005c4a5  mov     rdx, rbx
0x18005c4a8  mov     rcx, rdi
0x18005c4ab  call    ListView_OnWinIniChange
0x18005c4b0  jmp     loc_18005C167
0x18005c4b5  mov     eax, [rdi+48h]
0x18005c4b8  test    rbx, rbx
0x18005c4bb  jz      short loc_18005C4D7
0x18005c4bd  test    cl, al
0x18005c4bf  jnz     loc_18005C167
0x18005c4c5  or      eax, ecx
0x18005c4c7  mov     rcx, rdi
0x18005c4ca  mov     [rdi+48h], eax
0x18005c4cd  call    ListView_UpdateScrollBars
0x18005c4d2  jmp     loc_18005C167
0x18005c4d7  and     eax, 0FFFFFFFDh
0x18005c4da  mov     [rdi+48h], eax
0x18005c4dd  jmp     loc_18005C167
0x18005c4e2  test    rsi, rsi
0x18005c4e5  jz      short loc_18005C50A
0x18005c4e7  mov     eax, [rdi+10h]
0x18005c4ea  and     al, 3
0x18005c4ec  cmp     al, r15b
0x18005c4ef  jnz     short loc_18005C50A
0x18005c4f1  cmp     [rsi+8], r14d
0x18005c4f5  jnz     short loc_18005C50A
0x18005c4f7  mov     rax, [rdi]
0x18005c4fa  mov     [rsi+10h], rax
0x18005c4fe  mov     rcx, [rdi]; hWnd
0x18005c501  call    cs:__imp_GetDlgCtrlID
0x18005c507  mov     [rsi+8], eax
0x18005c50a  mov     rcx, [rdi]; hWnd
0x18005c50d  xor     r8d, r8d; wParam
0x18005c510  lea     edx, [r8+53h]; Msg
0x18005c514  mov     r9, rsi; lParam
0x18005c517  call    cs:__imp_DefWindowProcW
0x18005c51d  jmp     loc_18005DC96
0x18005c522  mov     eax, 102h
0x18005c527  cmp     r13d, eax
0x18005c52a  ja      loc_18005C62E
0x18005c530  jz      loc_18005C603
0x18005c536  mov     eax, r13d
0x18005c539  sub     eax, 55h ; 'U'
0x18005c53c  jz      loc_18005C5F3
0x18005c542  sub     eax, 27h ; '''
0x18005c545  jz      short loc_18005C5C6
0x18005c547  sub     eax, r15d
0x18005c54a  jz      short loc_18005C5B4
  ... truncated ...
```
