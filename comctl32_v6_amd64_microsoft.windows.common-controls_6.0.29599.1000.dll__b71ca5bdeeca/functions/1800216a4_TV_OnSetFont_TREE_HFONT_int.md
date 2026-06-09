# TV_OnSetFont(_TREE *,HFONT__ *,int)

- ea: `0x1800216a4`
- end: `0x1800218f1`
- name: `?TV_OnSetFont@@YAXPEAU_TREE@@PEAUHFONT__@@H@Z`
- size: `589`
- prototype: `void __fastcall(struct _TREE *, HFONT h, int)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18001d900`
- `0x1800201f0`

## callees

- `0x18001d4fc`
- `0x1800216a4`
- `0x1800218f8`
- `0x180021d94`
- `0x180021f94`
- `0x180022044`
- `0x180022098`
- `0x180024d20`
- `0x18004c6f0`
- `0x180072398`
- `0x180114520`
- `0x180114ebc`
- `0x1801378fc`

## import_xrefs

- `GDI32!DeleteObject` at `0x180021825`
- `GDI32!DeleteObject` at `0x180021825`
- `GDI32!SelectObject` at `0x180021718`
- `GDI32!SelectObject` at `0x1800218bf`
- `GDI32!SelectObject` at `0x180021718`
- `GDI32!SelectObject` at `0x1800218bf`
- `GDI32!CreateFontIndirectW` at `0x1800218b1`
- `GDI32!CreateFontIndirectW` at `0x1800218b1`
- `GDI32!GetTextExtentPointW` at `0x180021739`
- `GDI32!GetTextExtentPointW` at `0x180021739`
- `USER32!GetDC` at `0x180021700`
- `USER32!GetDC` at `0x180021700`
- `USER32!SendMessageW` at `0x1800218e6`
- `USER32!SendMessageW` at `0x1800218e6`
- `USER32!GetSystemMetrics` at `0x180021744`
- `USER32!GetSystemMetrics` at `0x180021744`
- `USER32!ReleaseDC` at `0x180021768`
- `USER32!ReleaseDC` at `0x180021768`
- `UxTheme!GetThemeFont` at `0x1800218a2`
- `UxTheme!GetThemeFont` at `0x1800218a2`

## pseudocode

```c
void __fastcall TV_OnSetFont(struct _TREE *a1, HFONT h)
{
  bool v2; // zf
  HDC DC; // rax
  HDC v6; // rsi
  HGDIOBJ v7; // rbp
  HWND v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  HFONT IconTitleFont; // rax
  WCHAR String; // [rsp+30h] [rbp-98h] BYREF
  struct tagSIZE sz; // [rsp+38h] [rbp-90h] BYREF
  LOGFONTW lf; // [rsp+40h] [rbp-88h] BYREF

  v2 = (*((_BYTE *)a1 + 64) & 0x40) == 0;
  String = 74;
  sz = 0;
  if ( !v2 )
  {
    v9 = (void *)*((_QWORD *)a1 + 29);
    if ( v9 )
    {
      DeleteObject(v9);
      *((_DWORD *)a1 + 16) &= ~0x40u;
    }
  }
  if ( !h )
  {
    memset_0(&lf, 0, sizeof(lf));
    v10 = (void *)*((_QWORD *)a1 + 61);
    if ( v10 && GetThemeFont(v10, 0, 1, 1, 210, &lf) >= 0 )
      IconTitleFont = CreateFontIndirectW(&lf);
    else
      IconTitleFont = DPISCALEINFO::CreateIconTitleFont((struct _TREE *)((char *)a1 + 52));
    *((_DWORD *)a1 + 16) |= 0x40u;
    h = IconTitleFont;
  }
  DC = GetDC(*(HWND *)a1);
  v6 = DC;
  if ( h )
    v7 = SelectObject(DC, h);
  else
    v7 = 0;
  sz.cy = 0;
  GetTextExtentPointW(v6, &String, 1, &sz);
  *((_WORD *)a1 + 178) = LOWORD(sz.cy) + 2 * GetSystemMetrics(6);
  if ( v7 )
    SelectObject(v6, v7);
  ReleaseDC(*(HWND *)a1, v6);
  v2 = *((_QWORD *)a1 + 31) == 0;
  *((_QWORD *)a1 + 29) = h;
  if ( !v2 )
    TV_CreateBoldFont(a1);
  TV_RecomputeItemWidths(a1);
  *((_DWORD *)a1 + 7) = GetCodePageForFont(h);
  TV_DeleteHotFonts(a1);
  TV_SetIndent(a1, 0x13u);
  TV_SetImageList(a1, *((HIMAGELIST *)a1 + 22), 0, 1);
  if ( (*((_DWORD *)a1 + 4) & 0xA000) == 0 )
  {
    TV_RecomputeItemWidths(a1);
    *((_WORD *)a1 + 186) = TV_RecomputeMaxWidth(a1);
  }
  TV_CalcScrollBars(a1);
  TV_SetItemHeight(a1);
  v8 = (HWND)*((_QWORD *)a1 + 54);
  if ( v8 )
    SendMessageW(v8, 0x30u, *((_QWORD *)a1 + 29), 1);
}

```

## disassembly

```asm
0x1800216a4  mov     [rsp+arg_10], rbx
0x1800216a9  mov     [rsp+arg_18], rbp
0x1800216ae  push    rsi
0x1800216af  push    rdi
0x1800216b0  push    r15
0x1800216b2  sub     rsp, 0B0h
0x1800216b9  mov     rax, cs:__security_cookie
0x1800216c0  xor     rax, rsp
0x1800216c3  mov     [rsp+0C8h+var_28], rax
0x1800216cb  test    byte ptr [rcx+40h], 40h
0x1800216cf  mov     eax, 4Ah ; 'J'
0x1800216d4  mov     [rsp+0C8h+String], ax
0x1800216d9  mov     rdi, rdx
0x1800216dc  mov     rbx, rcx
0x1800216df  mov     qword ptr [rsp+0C8h+sz.cx], 0
0x1800216e8  jnz     loc_180021815
0x1800216ee  mov     r15d, 1
0x1800216f4  test    rdi, rdi
0x1800216f7  jz      loc_18002183B
0x1800216fd  mov     rcx, [rbx]; hWnd
0x180021700  call    cs:__imp_GetDC
0x180021706  mov     rsi, rax
0x180021709  test    rdi, rdi
0x18002170c  jz      loc_180021834
0x180021712  mov     rdx, rdi; h
0x180021715  mov     rcx, rax; hdc
0x180021718  call    cs:__imp_SelectObject
0x18002171e  mov     rbp, rax
0x180021721  lea     r9, [rsp+0C8h+sz]; lpsz
0x180021726  mov     [rsp+0C8h+sz.cy], 0
0x18002172e  mov     r8d, r15d; c
0x180021731  lea     rdx, [rsp+0C8h+String]; lpString
0x180021736  mov     rcx, rsi; hdc
0x180021739  call    cs:__imp_GetTextExtentPointW
0x18002173f  mov     ecx, 6; nIndex
0x180021744  call    cs:__imp_GetSystemMetrics
0x18002174a  add     ax, ax
0x18002174d  add     ax, word ptr [rsp+0C8h+sz.cy]
0x180021752  mov     [rbx+164h], ax
0x180021759  test    rbp, rbp
0x18002175c  jnz     loc_1800218B9
0x180021762  mov     rcx, [rbx]; hWnd
0x180021765  mov     rdx, rsi; hDC
0x180021768  call    cs:__imp_ReleaseDC
0x18002176e  cmp     qword ptr [rbx+0F8h], 0
0x180021776  mov     [rbx+0E8h], rdi
0x18002177d  jnz     loc_1800218CA
0x180021783  mov     rcx, rbx; struct _TREE *
0x180021786  call    ?TV_RecomputeItemWidths@@YAXPEAU_TREE@@@Z; TV_RecomputeItemWidths(_TREE *)
0x18002178b  mov     rcx, rdi; h
0x18002178e  call    GetCodePageForFont
0x180021793  mov     rcx, rbx; struct _TREE *
0x180021796  mov     [rbx+1Ch], eax
0x180021799  call    ?TV_DeleteHotFonts@@YAXPEAU_TREE@@@Z; TV_DeleteHotFonts(_TREE *)
0x18002179e  mov     edx, 13h; unsigned __int64
0x1800217a3  mov     rcx, rbx; struct _TREE *
0x1800217a6  call    ?TV_SetIndent@@YAXPEAU_TREE@@_K@Z; TV_SetIndent(_TREE *,unsigned __int64)
0x1800217ab  mov     rdx, [rbx+0B0h]; himl
0x1800217b2  mov     r9d, r15d; int
0x1800217b5  xor     r8d, r8d; int
0x1800217b8  mov     rcx, rbx; struct _TREE *
0x1800217bb  call    ?TV_SetImageList@@YAPEAU_IMAGELIST@@PEAU_TREE@@PEAU1@HH@Z; TV_SetImageList(_TREE *,_IMAGELIST *,int,int)
0x1800217c0  test    dword ptr [rbx+10h], 0A000h
0x1800217c7  jz      loc_18002186C
0x1800217cd  mov     rcx, rbx; struct _TREE *
0x1800217d0  call    ?TV_CalcScrollBars@@YAHPEAU_TREE@@@Z; TV_CalcScrollBars(_TREE *)
0x1800217d5  mov     rcx, rbx; struct _TREE *
0x1800217d8  call    ?TV_SetItemHeight@@YAXPEAU_TREE@@@Z; TV_SetItemHeight(_TREE *)
0x1800217dd  mov     rcx, [rbx+1B0h]; hWnd
0x1800217e4  test    rcx, rcx
0x1800217e7  jnz     loc_1800218D7
0x1800217ed  mov     rcx, [rsp+0C8h+var_28]
0x1800217f5  xor     rcx, rsp; StackCookie
0x1800217f8  call    __security_check_cookie
0x1800217fd  lea     r11, [rsp+0C8h+var_18]
0x180021805  mov     rbx, [r11+30h]
0x180021809  mov     rbp, [r11+38h]
0x18002180d  mov     rsp, r11
0x180021810  pop     r15
0x180021812  pop     rdi
0x180021813  pop     rsi
0x180021814  retn
0x180021815  mov     rcx, [rcx+0E8h]; ho
0x18002181c  test    rcx, rcx
0x18002181f  jz      loc_1800216EE
0x180021825  call    cs:__imp_DeleteObject
0x18002182b  and     dword ptr [rbx+40h], 0FFFFFFBFh
0x18002182f  jmp     loc_1800216EE
0x180021834  xor     ebp, ebp
0x180021836  jmp     loc_180021721
0x18002183b  xor     edx, edx; Val
0x18002183d  lea     rcx, [rsp+0C8h+lf]; void *
0x180021842  lea     r8d, [rdx+5Ch]; Size
0x180021846  call    memset_0
0x18002184b  mov     rcx, [rbx+1E8h]; hTheme
0x180021852  test    rcx, rcx
0x180021855  jnz     short loc_180021888
0x180021857  lea     rcx, [rbx+34h]; this
0x18002185b  call    ?CreateIconTitleFont@DPISCALEINFO@@QEBAPEAUHFONT__@@XZ; DPISCALEINFO::CreateIconTitleFont(void)
0x180021860  or      dword ptr [rbx+40h], 40h
0x180021864  mov     rdi, rax
0x180021867  jmp     loc_1800216FD
0x18002186c  mov     rcx, rbx; struct _TREE *
0x18002186f  call    ?TV_RecomputeItemWidths@@YAXPEAU_TREE@@@Z; TV_RecomputeItemWidths(_TREE *)
0x180021874  mov     rcx, rbx; struct _TREE *
0x180021877  call    ?TV_RecomputeMaxWidth@@YAIPEAU_TREE@@@Z; TV_RecomputeMaxWidth(_TREE *)
0x18002187c  mov     [rbx+174h], ax
0x180021883  jmp     loc_1800217CD
0x180021888  lea     rax, [rsp+0C8h+lf]
0x18002188d  mov     r9d, r15d; iStateId
0x180021890  mov     [rsp+0C8h+pFont], rax; pFont
0x180021895  mov     r8d, r15d; iPartId
0x180021898  xor     edx, edx; hdc
0x18002189a  mov     [rsp+0C8h+iPropId], 0D2h; iPropId
0x1800218a2  call    cs:__imp_GetThemeFont
0x1800218a8  test    eax, eax
0x1800218aa  js      short loc_180021857
0x1800218ac  lea     rcx, [rsp+0C8h+lf]; lplf
0x1800218b1  call    cs:__imp_CreateFontIndirectW
0x1800218b7  jmp     short loc_180021860
0x1800218b9  mov     rdx, rbp; h
0x1800218bc  mov     rcx, rsi; hdc
0x1800218bf  call    cs:__imp_SelectObject
0x1800218c5  jmp     loc_180021762
0x1800218ca  mov     rcx, rbx; struct _TREE *
0x1800218cd  call    ?TV_CreateBoldFont@@YAXPEAU_TREE@@@Z; TV_CreateBoldFont(_TREE *)
0x1800218d2  jmp     loc_180021783
0x1800218d7  mov     r8, [rbx+0E8h]; wParam
0x1800218de  mov     r9, r15; lParam
0x1800218e1  mov     edx, 30h ; '0'; Msg
0x1800218e6  call    cs:__imp_SendMessageW
0x1800218ec  jmp     loc_1800217ED
```
