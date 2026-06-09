# MCIWndiOpen

- ea: `0x180013edc`
- end: `0x18001440d`
- name: `MCIWndiOpen`
- size: `1329`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x180010cc0`
- `0x180014414`

## callees

- `0x1800014b0`
- `0x180002280`
- `0x180010134`
- `0x180010824`
- `0x180010aa4`
- `0x180010c08`
- `0x1800129a0`
- `0x180012f08`
- `0x180013358`
- `0x1800135a4`
- `0x180013edc`
- `0x180014adc`
- `0x180014c78`
- `0x180014cc8`
- `0x180015124`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800143b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800143b0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014377`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014377`
- `USER32!SendMessageW` at `0x180013f4d`
- `USER32!SendMessageW` at `0x180014157`
- `USER32!SendMessageW` at `0x1800143a7`
- `USER32!SendMessageW` at `0x1800143cc`
- `USER32!SendMessageW` at `0x180013f4d`
- `USER32!SendMessageW` at `0x180014157`
- `USER32!SendMessageW` at `0x1800143a7`
- `USER32!SendMessageW` at `0x1800143cc`
- `USER32!SetCursor` at `0x180013fdc`
- `USER32!SetCursor` at `0x18001408e`
- `USER32!SetCursor` at `0x180013fdc`
- `USER32!SetCursor` at `0x18001408e`
- `USER32!InvalidateRect` at `0x1800140b5`
- `USER32!InvalidateRect` at `0x1800143da`
- `USER32!InvalidateRect` at `0x1800140b5`
- `USER32!InvalidateRect` at `0x1800143da`
- `USER32!KillTimer` at `0x180013fa1`
- `USER32!KillTimer` at `0x180013fa1`
- `USER32!SetRect` at `0x18001416b`
- `USER32!SetRect` at `0x18001416b`
- `USER32!LoadCursorW` at `0x180013fd3`
- `USER32!LoadCursorW` at `0x180013fd3`

## string_xrefs

- `0x180014065`: `open "%s" alias %d wait type AVIVideo`
- `0x1800141f7`: `configure test`
- `0x180014017`: `open "%s" alias %d wait shareable`
- `0x180013fed`: `open new type %s alias %d wait`
- `0x18001403e`: `open "%s" alias %d wait`

## pseudocode

```c
__int64 __fastcall MCIWndiOpen(__int64 a1, char a2, LPARAM *a3)
{
  __int64 v3; // rbp
  LPARAM *v4; // rsi
  int v6; // r14d
  __int64 result; // rax
  int v8; // r12d
  unsigned __int64 v9; // rax
  HCURSOR CursorW; // rax
  HCURSOR v11; // r15
  wchar_t *v12; // r8
  unsigned __int64 v13; // rax
  int Value; // r14d
  HWND v15; // rcx
  HWND v16; // r9
  int v17; // eax
  bool v18; // zf
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // r14d
  CHAR *v23; // rax
  CHAR *v24; // rbp
  HWND v25; // rcx
  HWND v26; // rcx
  int yBottom[2]; // [rsp+20h] [rbp-158h]
  int v28; // [rsp+28h] [rbp-150h]
  wchar_t lParam[128]; // [rsp+30h] [rbp-148h] BYREF

  v3 = -1;
  v4 = a3;
  if ( (a2 & 1) != 0 )
  {
    v6 = 1;
    if ( !a3 || !*(_WORD *)a3 )
    {
      if ( !*(_DWORD *)(a1 + 20) )
        return 42;
      SendMessageW(*(HWND *)a1, 0x4E1u, 0x80u, (LPARAM)lParam);
LABEL_10:
      v4 = (LPARAM *)lParam;
    }
  }
  else
  {
    v6 = 0;
    if ( a3 == (LPARAM *)-1LL )
    {
      if ( StringCchCopyW(lParam, 0x80u, (STRSAFE_LPCWSTR)(a1 + 244)) < 0 || !(unsigned int)MCIWndOpenDlg(a1, 0, lParam) )
        return -1;
      goto LABEL_10;
    }
  }
  v8 = *(_DWORD *)(a1 + 20);
  KillTimer(*(HWND *)a1, 0x2Au);
  ++*(_DWORD *)(a1 + 16);
  v9 = -1;
  *(_DWORD *)(a1 + 20) = 0;
  do
    ++v9;
  while ( *((_WORD *)v4 + v9) );
  if ( v9 >= 0x80 )
  {
    result = 296;
    *(_DWORD *)(a1 + 28) = 296;
    return result;
  }
  CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
  v11 = SetCursor(CursorW);
  if ( v6 )
  {
    v12 = szNew;
    v28 = *(_DWORD *)(a1 + 16);
LABEL_24:
    *(_QWORD *)yBottom = v4;
    Value = MCIWndGetValue(a1, 1, v12, 0);
    goto LABEL_25;
  }
  v13 = -1;
  do
    ++v13;
  while ( *((_WORD *)v4 + v13) );
  if ( v13 > 4 && *((_WORD *)v4 + v13 - 4) == 46
    || (v28 = *(_DWORD *)(a1 + 16), *(_QWORD *)yBottom = v4, (Value = MCIWndGetValue(a1, 0, szOpenShareable, 0)) == 0) )
  {
    v28 = *(_DWORD *)(a1 + 16);
    *(_QWORD *)yBottom = v4;
    Value = MCIWndGetValue(a1, 0, szOpen, 0);
    if ( !Value )
    {
      v12 = szOpenAVI;
      v28 = *(_DWORD *)(a1 + 16);
      goto LABEL_24;
    }
  }
LABEL_25:
  if ( v11 )
    SetCursor(v11);
  if ( !Value )
  {
    *(_DWORD *)(a1 + 20) = v8;
    MCIWndiSetTimer(a1);
    v15 = *(HWND *)a1;
    --*(_DWORD *)(a1 + 16);
    InvalidateRect(v15, 0, 1);
    return *(unsigned int *)(a1 + 28);
  }
  if ( v8 )
  {
    --*(_DWORD *)(a1 + 16);
    *(_DWORD *)(a1 + 20) = v8;
    MCIWndiClose(a1, 0);
    ++*(_DWORD *)(a1 + 16);
  }
  *(_DWORD *)(a1 + 20) = Value;
  *(_DWORD *)(a1 + 224) = -1;
  *(_DWORD *)(a1 + 228) = -1;
  if ( StringCchCopyW((STRSAFE_LPWSTR)(a1 + 244), 0x80u, (STRSAFE_LPCWSTR)v4) < 0 )
    return -1;
  MCIWndiSetCaption(a1);
  v16 = *(HWND *)a1;
  *(_DWORD *)(a1 + 88) = 1;
  v17 = MCIWndString(a1, 0, szWindowHandle, v16, *(_QWORD *)yBottom);
  *(_DWORD *)(a1 + 60) = v17 == 0;
  if ( v17 )
    SetRect((LPRECT)(a1 + 140), 0, 0, 0, 0);
  else
    SendMessageW(*(HWND *)a1, 0x48Eu, 0, a1 + 140);
  *(_DWORD *)(a1 + 64) = MCIWndString(a1, 0, szStatusPalette) == 0;
  *(_DWORD *)(a1 + 68) = MCIWndDevCaps(a1, 1);
  *(_DWORD *)(a1 + 72) = MCIWndDevCaps(a1, 8);
  *(_DWORD *)(a1 + 76) = MCIWndDevCaps(a1, 9);
  *(_DWORD *)(a1 + 80) = MCIWndDevCaps(a1, 7);
  *(_DWORD *)(a1 + 92) = MCIWndDevCaps(a1, 5);
  *(_DWORD *)(a1 + 96) = MCIWndDevCaps(a1, 3);
  *(_DWORD *)(a1 + 100) = MCIWndDevCaps(a1, 2);
  *(_DWORD *)(a1 + 84) = MCIWndString(a1, 0, szConfigureTest) == 0;
  if ( (unsigned int)MCIWndString(a1, 0, szSetSpeed1000Test)
    || (unsigned int)MCIWndString(a1, 0, szSetSpeed500Test)
    || (v18 = (unsigned int)MCIWndString(a1, 0, szSetSpeedTest, 2000) == 0, v19 = 1, !v18) )
  {
    v19 = 0;
  }
  *(_DWORD *)(a1 + 124) = v19;
  if ( (unsigned int)MCIWndString(a1, 0, szSetVolumeTest, 1000)
    || (v18 = (unsigned int)MCIWndString(a1, 0, szSetVolume0Test) == 0, v20 = 1, !v18) )
  {
    v20 = 0;
  }
  *(_DWORD *)(a1 + 116) = v20;
  *(_DWORD *)(a1 + 120) = 100;
  if ( !(unsigned int)MCIWndString(a1, 0, szSetVolumeTest, 2000) )
    *(_DWORD *)(a1 + 120) = 200;
  v21 = MCIWndString(a1, 0, szSetFormatTMSF);
  *(_DWORD *)(a1 + 36) = v21 == 0;
  if ( !v21 && (unsigned int)MCIWndString(a1, 0, szSetFormatMS) )
    *(_DWORD *)(a1 + 36) = 0;
  if ( !*(_DWORD *)(a1 + 36) && (unsigned int)MCIWndString(a1, 0, szSetFormatFrames) )
    MCIWndString(a1, 0, szSetFormatMS);
  MCIWndiValidateMedia(a1);
  MCIWndiFixMyPlaybar(a1);
  MCIWndiMakeMeAMenu(a1);
  MCIWndiSetTimer(a1);
  MCIWndiSize(a1, *(_DWORD *)(a1 + 232));
  if ( (*(_DWORD *)(a1 + 32) & 0x800) != 0 )
  {
    if ( *(char *)(a1 + 32) >= 0 )
    {
      v26 = *(HWND *)(a1 + 8);
      if ( v26 )
        SendMessageW(v26, 0x4CBu, *(_QWORD *)a1, (LPARAM)v4);
    }
    else
    {
      do
        ++v3;
      while ( *((_WORD *)v4 + v3) );
      v22 = v3 + 1;
      v23 = (CHAR *)LocalAlloc(0x40u, (int)v3 + 1);
      v24 = v23;
      if ( v23 )
      {
        Iwcstombs(v23, (LPCWCH)v4, v22);
        v25 = *(HWND *)(a1 + 8);
        if ( v25 )
          SendMessageW(v25, 0x4CBu, *(_QWORD *)a1, (LPARAM)v24);
        LocalFree(v24);
      }
    }
  }
  InvalidateRect(*(HWND *)a1, 0, 1);
  return 0;
}

```

## disassembly

```asm
0x180013edc  mov     [rsp+arg_8], rbx
0x180013ee1  push    rbp
0x180013ee2  push    rsi
0x180013ee3  push    rdi
0x180013ee4  push    r12
0x180013ee6  push    r13
0x180013ee8  push    r14
0x180013eea  push    r15
0x180013eec  sub     rsp, 140h
0x180013ef3  mov     rax, cs:__security_cookie
0x180013efa  xor     rax, rsp
0x180013efd  mov     [rsp+178h+var_48], rax
0x180013f05  mov     r15d, 80h
0x180013f0b  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180013f0f  xor     edi, edi
0x180013f11  mov     rsi, r8
0x180013f14  mov     rbx, rcx
0x180013f17  lea     r13d, [r15-7Fh]
0x180013f1b  test    r13b, dl
0x180013f1e  jz      short loc_180013F55
0x180013f20  mov     r14d, r13d
0x180013f23  test    r8, r8
0x180013f26  jz      short loc_180013F2E
0x180013f28  cmp     [r8], di
0x180013f2c  jnz     short loc_180013F95
0x180013f2e  cmp     [rcx+14h], edi
0x180013f31  jnz     short loc_180013F3D
0x180013f33  mov     eax, 2Ah ; '*'
0x180013f38  jmp     loc_1800143E2
0x180013f3d  mov     rcx, [rcx]; hWnd
0x180013f40  lea     r9, [rsp+178h+lParam]; lParam
0x180013f45  mov     r8, r15; wParam
0x180013f48  mov     edx, 4E1h; Msg
0x180013f4d  call    cs:__imp_SendMessageW
0x180013f53  jmp     short loc_180013F90
0x180013f55  mov     r14d, edi
0x180013f58  cmp     r8, rbp
0x180013f5b  jnz     short loc_180013F95
0x180013f5d  lea     r8, [rcx+0F4h]; pszSrc
0x180013f64  mov     rdx, r15; cchDest
0x180013f67  lea     rcx, [rsp+178h+lParam]; pszDest
0x180013f6c  call    StringCchCopyW
0x180013f71  test    eax, eax
0x180013f73  js      loc_18001410C
0x180013f79  lea     r8, [rsp+178h+lParam]
0x180013f7e  xor     edx, edx
0x180013f80  mov     rcx, rbx
0x180013f83  call    MCIWndOpenDlg
0x180013f88  test    eax, eax
0x180013f8a  jz      loc_18001410C
0x180013f90  lea     rsi, [rsp+178h+lParam]
0x180013f95  mov     rcx, [rbx]; hWnd
0x180013f98  mov     edx, 2Ah ; '*'; uIDEvent
0x180013f9d  mov     r12d, [rbx+14h]
0x180013fa1  call    cs:__imp_KillTimer
0x180013fa7  add     [rbx+10h], r13d
0x180013fab  mov     rax, rbp
0x180013fae  mov     [rbx+14h], edi
0x180013fb1  inc     rax
0x180013fb4  cmp     [rsi+rax*2], di
0x180013fb8  jnz     short loc_180013FB1
0x180013fba  cmp     rax, r15
0x180013fbd  jb      short loc_180013FCC
0x180013fbf  mov     eax, 128h
0x180013fc4  mov     [rbx+1Ch], eax
0x180013fc7  jmp     loc_1800143E2
0x180013fcc  mov     edx, 7F02h; lpCursorName
0x180013fd1  xor     ecx, ecx; hInstance
0x180013fd3  call    cs:__imp_LoadCursorW
0x180013fd9  mov     rcx, rax; hCursor
0x180013fdc  call    cs:__imp_SetCursor
0x180013fe2  mov     r15, rax
0x180013fe5  test    r14d, r14d
0x180013fe8  jz      short loc_180013FFA
0x180013fea  mov     ecx, [rbx+10h]
0x180013fed  lea     r8, szNew; "open new type %s alias %d wait"
0x180013ff4  mov     [rsp+178h+var_150], ecx
0x180013ff8  jmp     short loc_180014070
0x180013ffa  mov     rax, rbp
0x180013ffd  inc     rax
0x180014000  cmp     [rsi+rax*2], di
0x180014004  jnz     short loc_180013FFD
0x180014006  cmp     rax, 4
0x18001400a  jbe     short loc_180014014
0x18001400c  cmp     word ptr [rsi+rax*2-8], 2Eh ; '.'
0x180014012  jz      short loc_18001403B
0x180014014  mov     eax, [rbx+10h]
0x180014017  lea     r8, szOpenShareable; "open \"%s\" alias %d wait shareable"
0x18001401e  mov     [rsp+178h+var_150], eax
0x180014022  xor     r9d, r9d
0x180014025  xor     edx, edx
0x180014027  mov     qword ptr [rsp+178h+yBottom], rsi
0x18001402c  mov     rcx, rbx
0x18001402f  call    MCIWndGetValue
0x180014034  mov     r14d, eax
0x180014037  test    eax, eax
0x180014039  jnz     short loc_180014086
0x18001403b  mov     eax, [rbx+10h]
0x18001403e  lea     r8, szOpen; "open \"%s\" alias %d wait"
0x180014045  mov     [rsp+178h+var_150], eax
0x180014049  xor     r9d, r9d
0x18001404c  xor     edx, edx
0x18001404e  mov     qword ptr [rsp+178h+yBottom], rsi
0x180014053  mov     rcx, rbx
0x180014056  call    MCIWndGetValue
0x18001405b  mov     r14d, eax
0x18001405e  test    eax, eax
0x180014060  jnz     short loc_180014086
0x180014062  mov     eax, [rbx+10h]
0x180014065  lea     r8, szOpenAVI; "open \"%s\" alias %d wait type AVIVideo"
0x18001406c  mov     [rsp+178h+var_150], eax
0x180014070  xor     r9d, r9d
0x180014073  mov     qword ptr [rsp+178h+yBottom], rsi
0x180014078  mov     edx, r13d
0x18001407b  mov     rcx, rbx
0x18001407e  call    MCIWndGetValue
0x180014083  mov     r14d, eax
0x180014086  test    r15, r15
0x180014089  jz      short loc_180014094
0x18001408b  mov     rcx, r15; hCursor
0x18001408e  call    cs:__imp_SetCursor
0x180014094  test    r14d, r14d
0x180014097  jnz     short loc_1800140C3
0x180014099  mov     rcx, rbx
0x18001409c  mov     [rbx+14h], r12d
0x1800140a0  call    MCIWndiSetTimer
0x1800140a5  mov     rcx, [rbx]; hWnd
0x1800140a8  or      r15d, 0FFFFFFFFh
0x1800140ac  add     [rbx+10h], r15d
0x1800140b0  mov     r8d, r13d; bErase
0x1800140b3  xor     edx, edx; lpRect
0x1800140b5  call    cs:__imp_InvalidateRect
0x1800140bb  mov     eax, [rbx+1Ch]
0x1800140be  jmp     loc_1800143E2
0x1800140c3  or      r15d, 0FFFFFFFFh
0x1800140c7  test    r12d, r12d
0x1800140ca  jz      short loc_1800140E2
0x1800140cc  add     [rbx+10h], r15d
0x1800140d0  xor     edx, edx
0x1800140d2  mov     rcx, rbx
0x1800140d5  mov     [rbx+14h], r12d
0x1800140d9  call    MCIWndiClose
0x1800140de  add     [rbx+10h], r13d
0x1800140e2  lea     rcx, [rbx+0F4h]; pszDest
0x1800140e9  mov     [rbx+14h], r14d
0x1800140ed  mov     r8, rsi; pszSrc
0x1800140f0  mov     [rbx+0E0h], r15d
0x1800140f7  mov     edx, 80h; cchDest
0x1800140fc  mov     [rbx+0E4h], r15d
0x180014103  call    StringCchCopyW
0x180014108  test    eax, eax
0x18001410a  jns     short loc_180014114
0x18001410c  mov     rax, rbp
0x18001410f  jmp     loc_1800143E2
0x180014114  mov     rcx, rbx
0x180014117  call    MCIWndiSetCaption
0x18001411c  mov     r9, [rbx]
0x18001411f  lea     r8, szWindowHandle; "window handle %u"
0x180014126  xor     edx, edx
0x180014128  mov     [rbx+58h], r13d
0x18001412c  mov     rcx, rbx
0x18001412f  call    MCIWndString
0x180014134  mov     ecx, edi
0x180014136  test    eax, eax
0x180014138  setz    cl
0x18001413b  mov     [rbx+3Ch], ecx
0x18001413e  lea     rcx, [rbx+8Ch]; lprc
0x180014145  test    eax, eax
0x180014147  jnz     short loc_18001415F
0x180014149  mov     r9, rcx; lParam
0x18001414c  xor     r8d, r8d; wParam
0x18001414f  mov     rcx, [rbx]; hWnd
0x180014152  mov     edx, 48Eh; Msg
0x180014157  call    cs:__imp_SendMessageW
0x18001415d  jmp     short loc_180014171
0x18001415f  xor     r9d, r9d; xRight
0x180014162  mov     [rsp+178h+yBottom], edi; yBottom
0x180014166  xor     r8d, r8d; yTop
0x180014169  xor     edx, edx; xLeft
0x18001416b  call    cs:__imp_SetRect
0x180014171  lea     r8, szStatusPalette; "status palette handle"
0x180014178  xor     edx, edx
0x18001417a  mov     rcx, rbx
0x18001417d  call    MCIWndString
0x180014182  mov     ecx, edi
0x180014184  test    eax, eax
0x180014186  mov     edx, r13d
0x180014189  setz    cl
0x18001418c  mov     [rbx+40h], ecx
0x18001418f  mov     rcx, rbx
0x180014192  call    MCIWndDevCaps
0x180014197  mov     edx, 8
0x18001419c  mov     [rbx+44h], eax
0x18001419f  mov     rcx, rbx
0x1800141a2  call    MCIWndDevCaps
0x1800141a7  mov     edx, 9
0x1800141ac  mov     [rbx+48h], eax
0x1800141af  mov     rcx, rbx
0x1800141b2  call    MCIWndDevCaps
0x1800141b7  mov     edx, 7
0x1800141bc  mov     [rbx+4Ch], eax
0x1800141bf  mov     rcx, rbx
0x1800141c2  call    MCIWndDevCaps
0x1800141c7  mov     edx, 5
0x1800141cc  mov     [rbx+50h], eax
0x1800141cf  mov     rcx, rbx
0x1800141d2  call    MCIWndDevCaps
0x1800141d7  mov     edx, 3
0x1800141dc  mov     [rbx+5Ch], eax
0x1800141df  mov     rcx, rbx
0x1800141e2  call    MCIWndDevCaps
0x1800141e7  mov     edx, 2
0x1800141ec  mov     [rbx+60h], eax
0x1800141ef  mov     rcx, rbx
0x1800141f2  call    MCIWndDevCaps
0x1800141f7  lea     r8, szConfigureTest; "configure test"
0x1800141fe  mov     [rbx+64h], eax
0x180014201  xor     edx, edx
0x180014203  mov     rcx, rbx
0x180014206  call    MCIWndString
0x18001420b  mov     ecx, edi
0x18001420d  lea     r8, szSetSpeed1000Test; "set speed 1000 test"
0x180014214  test    eax, eax
0x180014216  setz    cl
0x180014219  xor     edx, edx
0x18001421b  mov     [rbx+54h], ecx
0x18001421e  mov     rcx, rbx
0x180014221  call    MCIWndString
0x180014226  mov     r14d, 7D0h
0x18001422c  test    eax, eax
0x18001422e  jnz     short loc_180014260
0x180014230  lea     r8, szSetSpeed500Test; "set speed 500 test"
0x180014237  xor     edx, edx
0x180014239  mov     rcx, rbx
0x18001423c  call    MCIWndString
0x180014241  test    eax, eax
0x180014243  jnz     short loc_180014260
0x180014245  mov     r9d, r14d
0x180014248  lea     r8, szSetSpeedTest; "set speed %d test"
0x18001424f  xor     edx, edx
0x180014251  mov     rcx, rbx
0x180014254  call    MCIWndString
0x180014259  test    eax, eax
0x18001425b  mov     eax, r13d
0x18001425e  jz      short loc_180014262
0x180014260  mov     eax, edi
0x180014262  mov     r9d, 3E8h
0x180014268  mov     [rbx+7Ch], eax
0x18001426b  lea     r8, szSetVolumeTest; "setaudio volume to %d test"
0x180014272  xor     edx, edx
0x180014274  mov     rcx, rbx
0x180014277  call    MCIWndString
0x18001427c  test    eax, eax
0x18001427e  jnz     short loc_180014298
0x180014280  lea     r8, szSetVolume0Test; "setaudio volume to 0 test"
0x180014287  xor     edx, edx
0x180014289  mov     rcx, rbx
0x18001428c  call    MCIWndString
0x180014291  test    eax, eax
0x180014293  mov     eax, r13d
0x180014296  jz      short loc_18001429A
0x180014298  mov     eax, edi
0x18001429a  mov     r9d, r14d
0x18001429d  mov     [rbx+74h], eax
0x1800142a0  lea     r8, szSetVolumeTest; "setaudio volume to %d test"
0x1800142a7  mov     dword ptr [rbx+78h], 64h ; 'd'
0x1800142ae  xor     edx, edx
0x1800142b0  mov     rcx, rbx
0x1800142b3  call    MCIWndString
0x1800142b8  test    eax, eax
0x1800142ba  jnz     short loc_1800142C3
0x1800142bc  mov     dword ptr [rbx+78h], 0C8h
0x1800142c3  lea     r8, szSetFormatTMSF; "set time format tmsf"
0x1800142ca  xor     edx, edx
0x1800142cc  mov     rcx, rbx
0x1800142cf  call    MCIWndString
0x1800142d4  test    eax, eax
0x1800142d6  mov     ecx, edi
0x1800142d8  setz    cl
0x1800142db  mov     [rbx+24h], ecx
0x1800142de  test    eax, eax
0x1800142e0  jnz     short loc_1800142FA
0x1800142e2  lea     r8, szSetFormatMS; "set time format ms"
0x1800142e9  xor     edx, edx
0x1800142eb  mov     rcx, rbx
0x1800142ee  call    MCIWndString
0x1800142f3  test    eax, eax
0x1800142f5  jz      short loc_1800142FA
0x1800142f7  mov     [rbx+24h], edi
0x1800142fa  cmp     [rbx+24h], edi
0x1800142fd  jnz     short loc_180014325
0x1800142ff  lea     r8, szSetFormatFrames; "set time format frames"
0x180014306  xor     edx, edx
0x180014308  mov     rcx, rbx
0x18001430b  call    MCIWndString
0x180014310  test    eax, eax
0x180014312  jz      short loc_180014325
0x180014314  lea     r8, szSetFormatMS; "set time format ms"
0x18001431b  xor     edx, edx
0x18001431d  mov     rcx, rbx
  ... truncated ...
```
