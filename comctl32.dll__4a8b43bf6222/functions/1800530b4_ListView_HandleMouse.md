# ListView_HandleMouse

- ea: `0x1800530b4`
- end: `0x18005388f`
- name: `ListView_HandleMouse`
- size: `2011`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `installer_update`

## callers

- `0x18005c0a0`

## callees

- `0x1800181a0`
- `0x18001853c`
- `0x180035f8c`
- `0x180035fe0`
- `0x18004c5dc`
- `0x180050854`
- `0x1800517b4`
- `0x18005181c`
- `0x180051ac4`
- `0x180051bec`
- `0x1800530b4`
- `0x180053898`
- `0x1800563ec`
- `0x18005b6b4`
- `0x18005e448`
- `0x1800733e0`
- `0x180078300`
- `0x18008ea60`

## import_xrefs

- `USER32!ClientToScreen` at `0x180053840`
- `USER32!ClientToScreen` at `0x180053840`
- `USER32!SetCapture` at `0x1800531e6`
- `USER32!SetCapture` at `0x1800531e6`
- `USER32!IsWindow` at `0x180053154`
- `USER32!IsWindow` at `0x180053354`
- `USER32!IsWindow` at `0x1800533ae`
- `USER32!IsWindow` at `0x1800534ae`
- `USER32!IsWindow` at `0x180053525`
- `USER32!IsWindow` at `0x1800535b8`
- `USER32!IsWindow` at `0x180053642`
- `USER32!IsWindow` at `0x1800536ce`
- `USER32!IsWindow` at `0x180053728`
- `USER32!IsWindow` at `0x1800537b5`
- `USER32!IsWindow` at `0x18005386c`
- `USER32!IsWindow` at `0x180053154`
- `USER32!IsWindow` at `0x180053354`
- `USER32!IsWindow` at `0x1800533ae`
- `USER32!IsWindow` at `0x1800534ae`
- `USER32!IsWindow` at `0x180053525`
- `USER32!IsWindow` at `0x1800535b8`
- `USER32!IsWindow` at `0x180053642`
- `USER32!IsWindow` at `0x1800536ce`
- `USER32!IsWindow` at `0x180053728`
- `USER32!IsWindow` at `0x1800537b5`
- `USER32!IsWindow` at `0x18005386c`
- `USER32!GetCapture` at `0x18005320b`
- `USER32!GetCapture` at `0x18005320b`
- `USER32!SendMessageW` at `0x180053861`
- `USER32!SendMessageW` at `0x180053861`
- `USER32!GetDoubleClickTime` at `0x180053575`
- `USER32!GetDoubleClickTime` at `0x18005369b`
- `USER32!GetDoubleClickTime` at `0x180053575`
- `USER32!GetDoubleClickTime` at `0x18005369b`
- `USER32!IsChild` at `0x1800531cc`
- `USER32!IsChild` at `0x1800531cc`
- `USER32!SetFocus` at `0x18005351c`
- `USER32!SetFocus` at `0x1800536c5`
- `USER32!SetFocus` at `0x18005371f`
- `USER32!SetFocus` at `0x18005351c`
- `USER32!SetFocus` at `0x1800536c5`
- `USER32!SetFocus` at `0x18005371f`
- `USER32!GetFocus` at `0x180053162`
- `USER32!GetFocus` at `0x180053162`
- `USER32!UpdateWindow` at `0x18005348f`
- `USER32!UpdateWindow` at `0x18005348f`
- `USER32!SetTimer` at `0x180053588`
- `USER32!SetTimer` at `0x1800536ae`
- `USER32!SetTimer` at `0x180053588`
- `USER32!SetTimer` at `0x1800536ae`
- `USER32!KillTimer` at `0x180053132`
- `USER32!KillTimer` at `0x180053309`
- `USER32!KillTimer` at `0x180053132`
- `USER32!KillTimer` at `0x180053309`
- `USER32!GetShellWindow` at `0x1800531c0`
- `USER32!GetShellWindow` at `0x1800531c0`

## pseudocode

```c
int __fastcall ListView_HandleMouse(__int64 a1, int a2, LONG a3, LONG a4, unsigned int a5, int a6)
{
  int result; // eax
  HWND v10; // rbx
  int v11; // eax
  bool v12; // zf
  HWND Focus; // rax
  HWND v14; // rdx
  unsigned int v15; // edi
  HWND v16; // rbx
  HWND ShellWindow; // rax
  HWND v18; // rbx
  __int16 v19; // bx
  unsigned int v20; // r12d
  __int16 v21; // di
  unsigned int v22; // r15d
  int v23; // esi
  int ItemState; // eax
  LONG v25; // r8d
  LONG v26; // edx
  int v27; // r13d
  HWND v28; // rsi
  LONG x; // esi
  HWND v30; // rsi
  UINT v31; // eax
  BOOL v32; // r15d
  BOOL v33; // eax
  __int128 v34; // xmm0
  __int128 v35; // xmm1
  HWND v36; // rsi
  __int128 v37; // xmm0
  __int128 v38; // xmm1
  UINT DoubleClickTime; // eax
  HWND v40; // rsi
  HWND v41; // rsi
  LONG v42; // esi
  LONG v43; // r15d
  HWND v44; // rcx
  int v45; // [rsp+3Ch] [rbp-95h]
  int v46; // [rsp+40h] [rbp-91h]
  char v47; // [rsp+44h] [rbp-8Dh]
  HWND v48; // [rsp+50h] [rbp-81h]
  int v49; // [rsp+5Ch] [rbp-75h]
  _WORD v50[4]; // [rsp+60h] [rbp-71h] BYREF
  __int64 v51; // [rsp+68h] [rbp-69h]
  unsigned int v52; // [rsp+70h] [rbp-61h]
  HWND v53; // [rsp+78h] [rbp-59h]
  HWND v54; // [rsp+80h] [rbp-51h]
  _OWORD v55[9]; // [rsp+88h] [rbp-49h] BYREF
  struct tagPOINT Point; // [rsp+128h] [rbp+57h] BYREF
  int v57; // [rsp+130h] [rbp+5Fh]
  LONG v58; // [rsp+138h] [rbp+67h]
  LONG v59; // [rsp+140h] [rbp+6Fh]

  v59 = a4;
  v58 = a3;
  v57 = a2;
  v51 = 0;
  v52 = 0;
  memset(v55, 0, 0x48u);
  result = *(_DWORD *)(a1 + 56);
  if ( (result & 2) != 0 )
    return result;
  v10 = *(HWND *)a1;
  v11 = result | 2;
  v12 = (*(_BYTE *)(a1 + 76) & 0x40) == 0;
  v48 = *(HWND *)a1;
  *(_DWORD *)(a1 + 56) = v11;
  if ( !v12 && (v11 & 8) != 0 && (v11 & 4) != 0 )
  {
    KillTimer(v10, 0x2Eu);
    *(_DWORD *)(a1 + 56) &= ~8u;
    CCSendNotify(a1, -114, a1 + 352);
    result = IsWindow(v10);
    if ( !result )
      return result;
  }
  Focus = GetFocus();
  v14 = *(HWND *)a1;
  v15 = a5;
  v53 = Focus;
  v54 = v14;
  v49 = a5 & 2;
  v45 = v49 != 0 ? -5 : -2;
  if ( (unsigned int)ChildOfActiveWindow(v14)
    || (unsigned int)fShouldFirstClickActivate()
    || (v16 = *(HWND *)a1, ShellWindow = GetShellWindow(), v46 = 0, IsChild(ShellWindow, v16)) )
  {
    v46 = 1;
  }
  SetCapture(*(HWND *)a1);
  *(_DWORD *)(a1 + 620) = a3;
  *(_DWORD *)(a1 + 624) = a4;
  if ( !(unsigned int)ListView_DismissEdit(a1) )
  {
    v18 = *(HWND *)a1;
    if ( GetCapture() != v18 )
      goto LABEL_120;
  }
  CCReleaseCapture(a1);
  v19 = HIWORD(v58);
  v50[0] = a3;
  v20 = v15 & 0xFFFFFFF3;
  v50[1] = HIWORD(v58);
  v12 = (*(_BYTE *)(a1 + 16) & 4) == 0;
  v50[2] = a4;
  if ( v12 )
    v20 = v15;
  v21 = HIWORD(v59);
  v50[3] = HIWORD(v59);
  v22 = ListView_OnSubItemHitTest(a1, v50);
  if ( !v52 || (*(_BYTE *)(a1 + 76) & 0x20) != 0 || (*(_DWORD *)(a1 + 16) & 0x400) != 0 )
  {
    v23 = v51;
    v47 = v51;
  }
  else
  {
    v22 = -1;
    v47 = 1;
    v23 = 1;
  }
  WORD6(v55[2]) = v58;
  LOWORD(v55[3]) = v59;
  *((_QWORD *)&v55[1] + 1) = __PAIR64__(v52, v22);
  DWORD2(v55[2]) = 0;
  HIWORD(v55[2]) = v19;
  WORD1(v55[3]) = v21;
  LODWORD(v55[4]) = GetLVKeyFlags();
  LODWORD(v55[2]) = 0;
  *(_DWORD *)(a1 + 544) = v22;
  if ( (v22 & 0x80000000) != 0 || (ItemState = ListView_OnGetItemState(a1, v22, 2), Point.x = 1, !ItemState) )
    Point.x = 0;
  if ( !v57 )
  {
    if ( (v23 & 6) == 0 )
    {
      if ( (v23 & 8) != 0 )
      {
        v40 = *(HWND *)a1;
        SetFocus(*(HWND *)a1);
        result = IsWindow(v40);
        if ( !result )
          return result;
        if ( CCSendNotify(a1, v45, (LPARAM)v55) )
          goto LABEL_120;
        if ( (*(_BYTE *)(a1 + 76) & 4) != 0 )
          ListView_HandleStateIconClick(a1, v22);
        goto LABEL_118;
      }
      if ( (v23 & 1) == 0 )
        goto LABEL_120;
      v41 = *(HWND *)a1;
      SetFocus(*(HWND *)a1);
      result = IsWindow(v41);
      if ( !result )
        return result;
      if ( (*(_BYTE *)(a1 + 16) & 4) != 0
        || (v42 = v59, v43 = v58, !(unsigned int)CheckForDragBegin(*(HWND *)a1))
        || CCSendNotify(a1, -156, (LPARAM)v55) )
      {
        result = IsWindow(v48);
        if ( !result )
          return result;
        if ( v53 != v54 && (*(_BYTE *)(a1 + 16) & 8) == 0 && (v20 & 8) == 0 && (v20 & 4) == 0 && (v20 & 2) == 0 || !v46 )
          goto LABEL_120;
        if ( (v20 & 4) == 0 && (v20 & 8) == 0 )
          ListView_DeselectAll(a1);
        if ( CCSendNotify(a1, v45, (LPARAM)v55) )
          goto LABEL_120;
        goto LABEL_118;
      }
      if ( (v20 & 0xC) == 0 )
        ListView_DeselectAll(a1);
      v25 = v42;
      v26 = v43;
      goto LABEL_104;
    }
    CCPlaySound(L"CCSelect");
    if ( (v20 & 2) == 0 || (v20 & 0xC) == 0 )
      ListView_ButtonSelect(a1, v22, v20, (unsigned int)Point.x);
    if ( !a6 && (unsigned int)CheckForDragBegin(*(HWND *)a1) )
    {
      if ( (*(_BYTE *)(a1 + 76) & 0x20) == 0
        || (*(_DWORD *)(a1 + 16) & 3) != 1
        || (*(_DWORD *)(a1 + 16) & 0x404) != 0
        || v52
        || v23 != 14
        || CCSendNotify(a1, -156, (LPARAM)v55) )
      {
        ListView_SetFocusSel(a1, v22, 1, 0, 0);
        if ( (v20 & 4) == 0 )
          *(_DWORD *)(a1 + 148) = v22;
        UpdateWindow(*(HWND *)a1);
        CCSendNotify(a1, v49 != 0 ? -111 : -109, (LPARAM)v55);
        goto LABEL_120;
      }
      v25 = v59;
      v26 = v58;
LABEL_104:
      ListView_DragSelect(a1, v26, v25);
      v32 = CCSendNotify(a1, v45, (LPARAM)v55) == 0;
      goto LABEL_105;
    }
    result = IsWindow(v48);
    if ( !result )
      return result;
    if ( (v20 & 2) != 0 || (v20 & 8) == 0 )
    {
      v27 = v20 & 4;
      if ( (v20 & 4) != 0 )
        goto LABEL_63;
    }
    else
    {
      if ( (v20 & 4) != 0 )
      {
        ListView_SetFocusSel(a1, v22, 0, 0, 0);
        v27 = v20 & 4;
        goto LABEL_63;
      }
      ListView_SetFocusSel(a1, v22, 1, 0, 1);
      v27 = v20 & 4;
    }
    *(_DWORD *)(a1 + 148) = v22;
LABEL_63:
    v28 = *(HWND *)a1;
    SetFocus(*(HWND *)a1);
    result = IsWindow(v28);
    if ( !result )
      return result;
    if ( !v27 && (v20 & 0xA) == 0 )
    {
      ListView_DeselectAll(a1);
      x = Point.x;
      if ( (v47 & 4) == 0
        || !Point.x
        || (*(_BYTE *)(a1 + 76) & 0xC0) != 0
        || v53 != v54 && (*(_DWORD *)(a1 + 16) & 0x400) == 0 )
      {
LABEL_73:
        v32 = CCSendNotify(a1, v45, (LPARAM)v55) == 0;
        result = IsWindow(v48);
        if ( !result )
          return result;
        if ( (*(_BYTE *)(a1 + 76) & 0xC0) != 0
          && (v20 & 2) == 0
          && ((*(_DWORD *)(a1 + 76) & 0x40) != 0 && (*(_BYTE *)(a1 + 56) & 4) != 0 || x)
          && v46 )
        {
          v33 = (*(_DWORD *)(a1 + 76) & 0x40) != 0 && (v20 & 0xC) == 0;
          if ( x && *(char *)(a1 + 76) < 0 )
            goto LABEL_88;
          if ( !v33 )
            goto LABEL_105;
          if ( g_bUseDblClickTimer )
          {
            v34 = v55[0];
            v35 = v55[1];
            *(_DWORD *)(a1 + 56) |= 8u;
            v36 = *(HWND *)a1;
            *(_OWORD *)(a1 + 352) = v34;
            v37 = v55[2];
            *(_OWORD *)(a1 + 368) = v35;
            v38 = v55[3];
            *(_OWORD *)(a1 + 384) = v37;
            *(_QWORD *)&v37 = *(_QWORD *)&v55[4];
            *(_OWORD *)(a1 + 400) = v38;
            *(_QWORD *)(a1 + 416) = v37;
            DoubleClickTime = GetDoubleClickTime();
            SetTimer(v36, 0x2Eu, DoubleClickTime, 0);
          }
          else
          {
LABEL_88:
            CCSendNotify(a1, -114, (LPARAM)v55);
            result = IsWindow(v48);
            if ( !result )
              return result;
          }
        }
LABEL_105:
        if ( v32 )
        {
LABEL_118:
          if ( v49 )
          {
            v44 = *(HWND *)a1;
            LOWORD(Point.x) = v58;
            LOWORD(Point.y) = v59;
            HIWORD(Point.x) = v19;
            HIWORD(Point.y) = v21;
            ClientToScreen(v44, &Point);
            SendMessageW(*(HWND *)a1, 0x7Bu, *(_QWORD *)a1, LOWORD(Point.x) | (unsigned __int64)(LOWORD(Point.y) << 16));
          }
        }
LABEL_120:
        result = IsWindow(v48);
        if ( result )
          *(_DWORD *)(a1 + 56) &= ~2u;
        return result;
      }
      v30 = *(HWND *)a1;
      v31 = GetDoubleClickTime();
      SetTimer(v30, 0x2Au, v31, 0);
      *(_DWORD *)(a1 + 72) |= 8u;
    }
    x = Point.x;
    goto LABEL_73;
  }
  ListView_CancelPendingTimer(a1, 8, 42);
  KillTimer(*(HWND *)a1, 0x2Bu);
  if ( (v23 & 1) != 0 && (v20 & 0xC) == 0 )
    ListView_DeselectAll(a1);
  if ( CCSendNotify(a1, (v20 & 2) != 0 ? -6 : -3, (LPARAM)v55) )
    goto LABEL_120;
  result = IsWindow(v48);
  if ( result )
  {
    if ( (v20 & 2) == 0 )
    {
      if ( (v23 & 6) != 0 )
      {
        if ( (*(_BYTE *)(a1 + 76) & 0x40) == 0 || (*(_BYTE *)(a1 + 56) & 4) == 0 || (v20 & 0xC) != 0 )
          CCSendNotify(a1, -114, (LPARAM)v55);
      }
      else if ( (v23 & 8) != 0 && (*(_BYTE *)(a1 + 76) & 4) != 0 )
      {
        ListView_HandleStateIconClick(a1, v22);
      }
    }
    result = IsWindow(v48);
    if ( result )
      goto LABEL_120;
  }
  return result;
}

```

## disassembly

```asm
0x1800530b4  mov     rax, rsp
0x1800530b7  mov     [rax+20h], r9d
0x1800530bb  mov     [rax+18h], r8d
0x1800530bf  mov     [rax+10h], edx
0x1800530c2  push    rbp
0x1800530c3  push    rbx
0x1800530c4  push    rsi
0x1800530c5  push    rdi
0x1800530c6  push    r12
0x1800530c8  push    r13
0x1800530ca  push    r14
0x1800530cc  push    r15
0x1800530ce  lea     rbp, [rax-4Fh]
0x1800530d2  sub     rsp, 0D8h
0x1800530d9  xor     edx, edx; Val
0x1800530db  mov     [rbp+47h+var_B0], 0
0x1800530e3  mov     r15d, r8d
0x1800530e6  mov     [rbp+47h+var_A8], 0
0x1800530ed  mov     r14, rcx
0x1800530f0  mov     esi, r9d
0x1800530f3  lea     rcx, [rbp+47h+var_90]; void *
0x1800530f7  lea     r8d, [rdx+48h]; Size
0x1800530fb  call    memset
0x180053100  mov     eax, [r14+38h]
0x180053104  test    al, 2
0x180053106  jnz     loc_18005387B
0x18005310c  mov     rbx, [r14]
0x18005310f  or      eax, 2
0x180053112  test    byte ptr [r14+4Ch], 40h
0x180053117  mov     [rsp+48h], rbx
0x18005311c  mov     [r14+38h], eax
0x180053120  jz      short loc_180053162
0x180053122  test    al, 8
0x180053124  jz      short loc_180053162
0x180053126  test    al, 4
0x180053128  jz      short loc_180053162
0x18005312a  mov     edx, 2Eh ; '.'; uIDEvent
0x18005312f  mov     rcx, rbx; hWnd
0x180053132  call    cs:__imp_KillTimer
0x180053138  and     dword ptr [r14+38h], 0FFFFFFF7h
0x18005313d  lea     r8, [r14+160h]
0x180053144  mov     edx, 0FFFFFF8Eh
0x180053149  mov     rcx, r14
0x18005314c  call    CCSendNotify
0x180053151  mov     rcx, rbx; hWnd
0x180053154  call    cs:__imp_IsWindow
0x18005315a  test    eax, eax
0x18005315c  jz      loc_18005387B
0x180053162  call    cs:__imp_GetFocus
0x180053168  mov     rdx, [r14]
0x18005316b  mov     edi, [rbp+47h+arg_20]
0x18005316e  mov     r8d, edi
0x180053171  mov     [rbp+47h+var_A0], rax
0x180053175  and     r8d, 2
0x180053179  mov     ecx, r8d
0x18005317c  mov     [rbp+47h+var_98], rdx
0x180053180  neg     ecx
0x180053182  mov     [rbp+47h+var_BC], r8d
0x180053186  mov     rcx, rdx; hWnd
0x180053189  sbb     eax, eax
0x18005318b  and     eax, 0FFFFFFFDh
0x18005318e  add     eax, 0FFFFFFFEh
0x180053191  mov     [rsp+110h+var_DC], eax
0x180053195  mov     eax, r8d
0x180053198  neg     eax
0x18005319a  sbb     eax, eax
0x18005319c  and     eax, 0FFFFFFFEh
0x18005319f  add     eax, 0FFFFFF93h
0x1800531a2  mov     [rbp+47h+var_C0], eax
0x1800531a5  call    ChildOfActiveWindow
0x1800531aa  mov     r13d, 1
0x1800531b0  test    eax, eax
0x1800531b2  jnz     short loc_1800531DE
0x1800531b4  call    fShouldFirstClickActivate
0x1800531b9  test    eax, eax
0x1800531bb  jnz     short loc_1800531DE
0x1800531bd  mov     rbx, [r14]
0x1800531c0  call    cs:__imp_GetShellWindow
0x1800531c6  mov     rcx, rax; hWndParent
0x1800531c9  mov     rdx, rbx; hWnd
0x1800531cc  call    cs:__imp_IsChild
0x1800531d2  mov     [rsp+110h+var_D8], 0
0x1800531da  test    eax, eax
0x1800531dc  jz      short loc_1800531E3
0x1800531de  mov     [rsp+110h+var_D8], r13d
0x1800531e3  mov     rcx, [r14]; hWnd
0x1800531e6  call    cs:__imp_SetCapture
0x1800531ec  xor     edx, edx
0x1800531ee  mov     [r14+26Ch], r15d
0x1800531f5  mov     rcx, r14; int
0x1800531f8  mov     [r14+270h], esi
0x1800531ff  call    ListView_DismissEdit
0x180053204  test    eax, eax
0x180053206  jnz     short loc_18005321A
0x180053208  mov     rbx, [r14]
0x18005320b  call    cs:__imp_GetCapture
0x180053211  cmp     rax, rbx
0x180053214  jnz     loc_180053867
0x18005321a  mov     rcx, r14
0x18005321d  call    CCReleaseCapture
0x180053222  movzx   ebx, [rbp+47h+arg_12]
0x180053226  lea     rdx, [rbp+47h+var_B8]
0x18005322a  mov     r12d, edi
0x18005322d  mov     [rbp+47h+var_B8], r15w
0x180053232  and     r12d, 0FFFFFFF3h
0x180053236  mov     [rbp+47h+var_B6], bx
0x18005323a  test    byte ptr [r14+10h], 4
0x18005323f  mov     rcx, r14
0x180053242  mov     [rbp+47h+var_B4], si
0x180053246  cmovz   r12d, edi
0x18005324a  movzx   edi, [rbp+47h+arg_1A]
0x18005324e  mov     [rbp+47h+var_B2], di
0x180053252  call    ListView_OnSubItemHitTest
0x180053257  mov     r15d, eax
0x18005325a  mov     eax, [rbp+47h+var_A8]
0x18005325d  test    eax, eax
0x18005325f  jz      short loc_180053280
0x180053261  test    byte ptr [r14+4Ch], 20h
0x180053266  jnz     short loc_180053280
0x180053268  test    dword ptr [r14+10h], 400h
0x180053270  jnz     short loc_180053280
0x180053272  or      r15d, 0FFFFFFFFh
0x180053276  mov     [rsp+3Ch], r13d
0x18005327b  mov     esi, r13d
0x18005327e  jmp     short loc_180053287
0x180053280  mov     esi, dword ptr [rbp+47h+var_B0]
0x180053283  mov     [rsp+3Ch], esi
0x180053287  mov     [rbp+47h+var_74], eax
0x18005328a  mov     eax, [rbp+67h]
0x18005328d  mov     word ptr [rbp+47h+var_70+0Ch], ax
0x180053291  mov     eax, [rbp+6Fh]
0x180053294  mov     word ptr [rbp+47h+var_60], ax
0x180053298  mov     [rbp+47h+var_78], r15d
0x18005329c  mov     dword ptr [rbp+47h+var_70+8], 0
0x1800532a3  mov     word ptr [rbp+47h+var_70+0Eh], bx
0x1800532a7  mov     word ptr [rbp+47h+var_60+2], di
0x1800532ab  call    GetLVKeyFlags
0x1800532b0  mov     dword ptr [rbp+47h+var_50], eax
0x1800532b3  mov     dword ptr [rbp+47h+var_70], 0
0x1800532ba  mov     [r14+220h], r15d
0x1800532c1  test    r15d, r15d
0x1800532c4  js      short loc_1800532DF
0x1800532c6  mov     r8d, 2
0x1800532cc  mov     edx, r15d
0x1800532cf  mov     rcx, r14
0x1800532d2  call    ListView_OnGetItemState
0x1800532d7  mov     [rbp+47h+Point.x], r13d
0x1800532db  test    eax, eax
0x1800532dd  jnz     short loc_1800532E6
0x1800532df  mov     [rbp+47h+Point.x], 0
0x1800532e6  cmp     [rbp+47h+arg_8], 0
0x1800532ea  jz      loc_1800533C1
0x1800532f0  mov     edx, 8
0x1800532f5  mov     rcx, r14
0x1800532f8  lea     r8d, [rdx+22h]
0x1800532fc  call    ListView_CancelPendingTimer
0x180053301  mov     rcx, [r14]; hWnd
0x180053304  mov     edx, 2Bh ; '+'; uIDEvent
0x180053309  call    cs:__imp_KillTimer
0x18005330f  test    r13b, sil
0x180053312  jz      short loc_180053325
0x180053314  test    r12b, 0Ch
0x180053318  jnz     short loc_180053325
0x18005331a  or      edx, 0FFFFFFFFh
0x18005331d  mov     rcx, r14
0x180053320  call    ListView_DeselectAll
0x180053325  mov     ebx, r12d
0x180053328  lea     r8, [rbp+47h+var_90]
0x18005332c  and     ebx, 2
0x18005332f  mov     rcx, r14
0x180053332  mov     eax, ebx
0x180053334  neg     eax
0x180053336  sbb     edx, edx
0x180053338  and     edx, 0FFFFFFFDh
0x18005333b  add     edx, 0FFFFFFFDh
0x18005333e  call    CCSendNotify
0x180053343  test    rax, rax
0x180053346  jnz     loc_180053867
0x18005334c  mov     rdi, [rsp+48h]
0x180053351  mov     rcx, rdi; hWnd
0x180053354  call    cs:__imp_IsWindow
0x18005335a  test    eax, eax
0x18005335c  jz      loc_18005387B
0x180053362  test    ebx, ebx
0x180053364  jnz     short loc_1800533AB
0x180053366  test    sil, 6
0x18005336a  jz      short loc_180053393
0x18005336c  test    byte ptr [r14+4Ch], 40h
0x180053371  jz      short loc_180053380
0x180053373  test    byte ptr [r14+38h], 4
0x180053378  jz      short loc_180053380
0x18005337a  test    r12b, 0Ch
0x18005337e  jz      short loc_1800533AB
0x180053380  lea     r8, [rbp+47h+var_90]
0x180053384  mov     edx, 0FFFFFF8Eh
0x180053389  mov     rcx, r14
0x18005338c  call    CCSendNotify
0x180053391  jmp     short loc_1800533AB
0x180053393  test    sil, 8
0x180053397  jz      short loc_1800533AB
0x180053399  test    byte ptr [r14+4Ch], 4
0x18005339e  jz      short loc_1800533AB
0x1800533a0  mov     edx, r15d
0x1800533a3  mov     rcx, r14
0x1800533a6  call    ListView_HandleStateIconClick
0x1800533ab  mov     rcx, rdi; hWnd
0x1800533ae  call    cs:__imp_IsWindow
0x1800533b4  test    eax, eax
0x1800533b6  jz      loc_18005387B
0x1800533bc  jmp     loc_180053867
0x1800533c1  test    sil, 6
0x1800533c5  jz      loc_1800536B9
0x1800533cb  lea     rcx, c_szSelect; "CCSelect"
0x1800533d2  call    CCPlaySound
0x1800533d7  mov     eax, r12d
0x1800533da  and     eax, 2
0x1800533dd  mov     dword ptr [rsp+110h+var_D0], eax
0x1800533e1  jz      short loc_1800533E9
0x1800533e3  test    r12b, 0Ch
0x1800533e7  jnz     short loc_1800533FB
0x1800533e9  mov     r9d, [rbp+47h+Point.x]
0x1800533ed  mov     r8d, r12d
0x1800533f0  mov     edx, r15d
0x1800533f3  mov     rcx, r14
0x1800533f6  call    ListView_ButtonSelect
0x1800533fb  cmp     [rbp+47h+arg_28], 0
0x1800533ff  jnz     loc_1800534A9
0x180053405  mov     r8d, [rbp+6Fh]
0x180053409  mov     edx, [rbp+67h]
0x18005340c  mov     rcx, [r14]; hWnd
0x18005340f  call    CheckForDragBegin
0x180053414  test    eax, eax
0x180053416  jz      loc_1800534A9
0x18005341c  test    byte ptr [r14+4Ch], 20h
0x180053421  jz      short loc_180053465
0x180053423  mov     eax, [r14+10h]
0x180053427  and     al, 3
0x180053429  cmp     al, r13b
0x18005342c  jnz     short loc_180053465
0x18005342e  test    dword ptr [r14+10h], 404h
0x180053436  jnz     short loc_180053465
0x180053438  cmp     [rbp+47h+var_A8], 0
0x18005343c  jnz     short loc_180053465
0x18005343e  cmp     esi, 0Eh
0x180053441  jnz     short loc_180053465
0x180053443  lea     r8, [rbp+47h+var_90]
0x180053447  mov     edx, 0FFFFFF64h
0x18005344c  mov     rcx, r14
0x18005344f  call    CCSendNotify
0x180053454  test    rax, rax
0x180053457  jnz     short loc_180053465
0x180053459  mov     r8d, [rbp+6Fh]
0x18005345d  mov     edx, [rbp+67h]
0x180053460  jmp     loc_180053783
0x180053465  xor     r9d, r9d
0x180053468  mov     dword ptr [rsp+20h], 0
0x180053470  mov     r8d, r13d
0x180053473  mov     edx, r15d
0x180053476  mov     rcx, r14
0x180053479  call    ListView_SetFocusSel
0x18005347e  bt      r12d, 2
0x180053483  jb      short loc_18005348C
0x180053485  mov     [r14+94h], r15d
0x18005348c  mov     rcx, [r14]; hWnd
0x18005348f  call    cs:__imp_UpdateWindow
0x180053495  mov     edx, [rbp+47h+var_C0]
0x180053498  lea     r8, [rbp+47h+var_90]
0x18005349c  mov     rcx, r14
0x18005349f  call    CCSendNotify
0x1800534a4  jmp     loc_180053867
0x1800534a9  mov     rcx, [rsp+48h]; hWnd
0x1800534ae  call    cs:__imp_IsWindow
0x1800534b4  test    eax, eax
0x1800534b6  jz      loc_18005387B
0x1800534bc  cmp     dword ptr [rsp+110h+var_D0], 0
0x1800534c1  jnz     short loc_180053506
0x1800534c3  bt      r12d, 3
0x1800534c8  jnb     short loc_180053506
0x1800534ca  xor     r9d, r9d
0x1800534cd  mov     edx, r15d
0x1800534d0  mov     rcx, r14
0x1800534d3  bt      r12d, 2
0x1800534d8  jnb     short loc_1800534F0
0x1800534da  xor     r8d, r8d
0x1800534dd  mov     [rsp+20h], r9d
0x1800534e2  call    ListView_SetFocusSel
0x1800534e7  mov     r13d, r12d
0x1800534ea  and     r13d, 4
0x1800534ee  jmp     short loc_180053516
0x1800534f0  mov     r8d, r13d
0x1800534f3  mov     [rsp+20h], r13d
0x1800534f8  call    ListView_SetFocusSel
0x1800534fd  mov     r13d, r12d
0x180053500  and     r13d, 4
0x180053504  jmp     short loc_18005350F
0x180053506  mov     r13d, r12d
0x180053509  and     r13d, 4
0x18005350d  jnz     short loc_180053516
0x18005350f  mov     [r14+94h], r15d
0x180053516  mov     rsi, [r14]
  ... truncated ...
```
