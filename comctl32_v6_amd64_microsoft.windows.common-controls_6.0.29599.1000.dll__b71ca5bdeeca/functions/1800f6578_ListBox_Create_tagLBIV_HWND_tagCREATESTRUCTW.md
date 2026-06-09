# ListBox_Create(tagLBIV *,HWND__ *,tagCREATESTRUCTW *)

- ea: `0x1800f6578`
- end: `0x1800f6919`
- name: `?ListBox_Create@@YAJPEAUtagLBIV@@PEAUHWND__@@PEAUtagCREATESTRUCTW@@@Z`
- size: `929`
- prototype: `__int64 __fastcall(struct tagLBIV *, HWND hWnd, struct tagCREATESTRUCTW *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x18009f150`

## callees

- `0x180055dac`
- `0x1800a27d4`
- `0x1800a2df8`
- `0x1800e4b60`
- `0x1800f6578`
- `0x180114520`
- `0x18013dc5c`
- `0x18013e3a8`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x1800f6793`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x1800f6793`
- `USER32!SetPropW` at `0x1800f68b3`
- `USER32!SetPropW` at `0x1800f68b3`
- `USER32!GetDC` at `0x1800f67ee`
- `USER32!GetDC` at `0x1800f67ee`
- `USER32!SendMessageW` at `0x1800f6879`
- `USER32!SendMessageW` at `0x1800f6879`
- `USER32!GetWindowLongPtrW` at `0x1800f67aa`
- `USER32!GetWindowLongPtrW` at `0x1800f67aa`
- `USER32!GetDlgCtrlID` at `0x1800f684a`
- `USER32!GetDlgCtrlID` at `0x1800f684a`
- `USER32!ReleaseDC` at `0x1800f6815`
- `USER32!ReleaseDC` at `0x1800f6815`
- `USER32!PostMessageW` at `0x1800f68f5`
- `USER32!PostMessageW` at `0x1800f68f5`
- `UxTheme!OpenThemeData` at `0x1800f660b`
- `UxTheme!OpenThemeData` at `0x1800f660b`
- `UxTheme!__imp_IsDarkModeAllowedForWindow` at `0x1800f65ee`
- `UxTheme!__imp_IsDarkModeAllowedForWindow` at `0x1800f65ee`

## pseudocode

```c
__int64 __fastcall ListBox_Create(struct tagSIZE *a1, HWND hWnd, struct tagCREATESTRUCTW *a3)
{
  LONG style; // ebx
  DWORD dwExStyle; // r14d
  HWND hwndParent; // r15
  HWND v8; // rcx
  HTHEME v9; // rax
  unsigned int v10; // r8d
  unsigned int v11; // r8d
  unsigned int cy; // r9d
  unsigned int v13; // eax
  HDC DC; // rbx
  int v16; // eax
  unsigned int DlgCtrlID; // eax
  HWND v18; // rcx
  WPARAM v19; // r8
  LONG v20; // eax
  struct tagSIZE psizl; // [rsp+20h] [rbp-30h] BYREF
  LPARAM lParam[2]; // [rsp+28h] [rbp-28h] BYREF
  __int128 v23; // [rsp+38h] [rbp-18h]

  a1[13].cy |= 0x40000000u;
  a1[29].cx &= 0xFFFFFFFC;
  style = a3->style;
  dwExStyle = a3->dwExStyle;
  hwndParent = a3->hwndParent;
  *(_OWORD *)lParam = 0;
  psizl = 0;
  v23 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59149161>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_59149161>::GetImpl'::`2'::impl) )
  {
    a1[31].cx = CCIsHighContrastOn_Uncached() != 0;
    a1[31].cy = (unsigned __int8)((__int64 (__fastcall *)(_QWORD))IsDarkModeAllowedForWindow)(*a1);
  }
  v8 = (HWND)*a1;
  a1[1] = (struct tagSIZE)hwndParent;
  v9 = OpenThemeData(v8, L"Listbox");
  a1[14].cx &= ~1u;
  a1[2] = (struct tagSIZE)v9;
  v10 = ((a1[13].cy & 0xFFFFFF73 | ~(_BYTE)style & 4) ^ ((style & 1) << 7)) & 0x7F1FFFFF
      | (4 * (style & 0x300000 | ((style & 0x1000 | ((dwExStyle & 0xFFFFF000) << 10)) << 7)));
  a1[14].cx |= (dwExStyle & 0x2000 | 0x4000) >> 13;
  if ( (style & 0x4000) != 0 )
  {
    v11 = v10 & 0xFDFFFFCF | 0x2000000;
  }
  else if ( (style & 0x800) != 0 )
  {
    v11 = v10 & 0xFFFFFFCF | 0x20;
  }
  else
  {
    v11 = v10 & 0xFFFFFFCF | (2 * (style & 8));
  }
  cy = v11 & 0xFFE5FFFF | ((style & 0x80) != 0 ? 0x20000 : 0) | ((style & 0x400 | (2 * (style & 0x100))) << 10);
  a1[13].cy = cy;
  if ( (style & 0x80) != 0 )
  {
    ListBox_SetTabStopsHandler((struct tagLBIV *)a1, 0, 0);
    cy = a1[13].cy;
  }
  a1[15].cx = -1;
  a1[15].cy = -1;
  a1[16].cx = -1;
  v13 = cy & 0xFFFBFFFF | ((style & 0x200 | 0x20) << 9);
  if ( (style & 0x10) != 0 )
  {
    v13 = cy & 0xFFFBFFFC | ((style & 0x200 | 0x20) << 9) | 1;
  }
  else if ( (style & 0x20) != 0 && (((style & 0x200 | 0x20) << 9) & 0x40000) == 0 )
  {
    v13 = cy & 0xFFF3FFFC | ((style & 0x200 | 0x20) << 9) & 0xFFF7FFFC | 0x80002;
  }
  if ( (v13 & 3) != 0 && (style & 0x40) == 0 )
    v13 &= ~0x4000u;
  a1[13].cy = v13 & 0xFFFFFFBF | (32 * (style & 2 | 0x400));
  if ( (style & 0x2000) != 0 && (v13 & 3) == 1 && !(v13 & 0x4000 | (32 * (style & 2)) & 0x40) )
    a1[13].cy = v13 & 0xFFFF7FBF | (unsigned __int8)(32 * (style & 2));
  a1[22].cx = GetThreadLocale();
  if ( (style & 0x8000) != 0 )
    a1[20] = (struct tagSIZE)GetWindowLongPtrW(hwndParent, 0);
  a1[13].cy |= 0x10000u;
  a1[4].cy = -1;
  a1[21] = 0;
  ListBox_InitHStrings((struct tagLBIV *)a1);
  if ( (a1[13].cy & 0x4000) != 0 && !*(_QWORD *)&a1[8] )
    return 0xFFFFFFFFLL;
  DC = GetDC(hWnd);
  GetCharDimensions(DC, &psizl);
  a1[10] = psizl;
  ReleaseDC(hWnd, DC);
  if ( !a1[10].cx || !a1[10].cy )
  {
    a1[10].cx = 8;
    a1[10].cy = 16;
  }
  v16 = a1[13].cy & 3;
  if ( v16 == 1 )
  {
    LODWORD(lParam[0]) = 2;
    DlgCtrlID = GetDlgCtrlID(hWnd);
    v18 = (HWND)a1[1];
    v19 = DlgCtrlID;
    v20 = a1[10].cy;
    HIDWORD(lParam[0]) = v19;
    LODWORD(v23) = v20;
    HIDWORD(lParam[1]) = 0;
    *((_QWORD *)&v23 + 1) = 0;
    SendMessageW(v18, 0x2Cu, v19, (LPARAM)lParam);
    if ( (_DWORD)v23 )
      a1[10].cy = v23;
    if ( (a1[13].cy & 0x40000) != 0 )
      a1[11].cx = HIDWORD(lParam[1]);
  }
  else if ( v16 == 2 )
  {
    a1[10].cy = 0;
  }
  SetPropW(*(HWND *)a1, (LPCWSTR)(unsigned __int16)g_atomTabletPcPenService, HANDLE_FLAG_INHERIT);
  if ( (a1[13].cy & 0x40000) != 0 )
  {
    if ( a1[11].cx <= 0 )
      a1[11].cx = 15 * a1[10].cx;
    a1[11].cy = 1;
    a1[12].cx = 1;
  }
  ListBox_SetCItemFullMax((struct tagLBIV *)a1);
  if ( (a1[13].cy & 0x80000) == 0 )
    PostMessageW(hWnd, 5u, 0, 0);
  return 1;
}

```

## disassembly

```asm
0x1800f6578  push    rbp
0x1800f657a  push    rbx
0x1800f657b  push    rsi
0x1800f657c  push    rdi
0x1800f657d  push    r13
0x1800f657f  push    r14
0x1800f6581  push    r15
0x1800f6583  mov     rbp, rsp
0x1800f6586  sub     rsp, 50h
0x1800f658a  mov     rax, cs:__security_cookie
0x1800f6591  xor     rax, rsp
0x1800f6594  mov     [rbp+var_8], rax
0x1800f6598  bts     dword ptr [rcx+6Ch], 1Eh
0x1800f659d  xorps   xmm0, xmm0
0x1800f65a0  and     dword ptr [rcx+0E8h], 0FFFFFFFCh
0x1800f65a7  mov     rsi, rdx
0x1800f65aa  mov     ebx, [r8+30h]
0x1800f65ae  mov     rdi, rcx
0x1800f65b1  mov     r14d, [r8+48h]
0x1800f65b5  mov     r15, [r8+18h]
0x1800f65b9  movups  xmmword ptr [rbp+lParam], xmm0
0x1800f65bd  mov     qword ptr [rbp+psizl.cx], 0
0x1800f65c5  movups  [rbp+var_18], xmm0
0x1800f65c9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59149161@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59149161@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59149161> `wil::Feature<__WilFeatureTraits_Feature_59149161>::GetImpl(void)'::`2'::impl
0x1800f65d0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59149161@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59149161>::__private_IsEnabled(wil::ReportingKind)
0x1800f65d5  test    al, al
0x1800f65d7  jz      short loc_1800F65FD
0x1800f65d9  call    CCIsHighContrastOn_Uncached
0x1800f65de  xor     ecx, ecx
0x1800f65e0  test    eax, eax
0x1800f65e2  setnz   cl
0x1800f65e5  mov     [rdi+0F8h], ecx
0x1800f65eb  mov     rcx, [rdi]
0x1800f65ee  call    cs:__imp_IsDarkModeAllowedForWindow
0x1800f65f4  movzx   eax, al
0x1800f65f7  mov     [rdi+0FCh], eax
0x1800f65fd  mov     rcx, [rdi]; hwnd
0x1800f6600  lea     rdx, aListbox; "Listbox"
0x1800f6607  mov     [rdi+8], r15
0x1800f660b  call    cs:__imp_OpenThemeData
0x1800f6611  and     dword ptr [rdi+70h], 0FFFFFFFEh
0x1800f6615  mov     r8d, r14d
0x1800f6618  mov     [rdi+10h], rax
0x1800f661c  and     r8d, 0FFFFF000h
0x1800f6623  mov     eax, [rdi+6Ch]
0x1800f6626  and     r14d, 2000h
0x1800f662d  and     eax, 0FFFFFFF3h
0x1800f6630  shl     r8d, 0Ah
0x1800f6634  mov     ecx, ebx
0x1800f6636  mov     r13d, 1
0x1800f663c  not     ecx
0x1800f663e  and     ecx, 4
0x1800f6641  or      ecx, eax
0x1800f6643  mov     eax, ebx
0x1800f6645  and     eax, 1000h
0x1800f664a  btr     ecx, 7
0x1800f664e  or      r8d, eax
0x1800f6651  mov     eax, ebx
0x1800f6653  and     eax, 300000h
0x1800f6658  shl     r8d, 7
0x1800f665c  or      r8d, eax
0x1800f665f  mov     eax, ebx
0x1800f6661  and     eax, r13d
0x1800f6664  shl     r8d, 2
0x1800f6668  shl     eax, 7
0x1800f666b  xor     eax, ecx
0x1800f666d  and     eax, 7F1FFFFFh
0x1800f6672  or      r8d, eax
0x1800f6675  mov     eax, 4000h
0x1800f667a  or      r14d, eax
0x1800f667d  shr     r14d, 0Dh
0x1800f6681  or      [rdi+70h], r14d
0x1800f6685  test    eax, ebx
0x1800f6687  jz      short loc_1800F6694
0x1800f6689  and     r8d, 0FFFFFFCFh
0x1800f668d  bts     r8d, 19h
0x1800f6692  jmp     short loc_1800F66B7
0x1800f6694  bt      ebx, 0Bh
0x1800f6698  jnb     short loc_1800F66A4
0x1800f669a  and     r8d, 0FFFFFFEFh
0x1800f669e  or      r8d, 20h
0x1800f66a2  jmp     short loc_1800F66B7
0x1800f66a4  mov     eax, r8d
0x1800f66a7  mov     ecx, ebx
0x1800f66a9  and     ecx, 8
0x1800f66ac  and     eax, 0FFFFFFCFh
0x1800f66af  add     ecx, ecx
0x1800f66b1  mov     r8d, ecx
0x1800f66b4  or      r8d, eax
0x1800f66b7  mov     r9d, ebx
0x1800f66ba  mov     eax, ebx
0x1800f66bc  and     r9d, 100h
0x1800f66c3  and     eax, 400h
0x1800f66c8  add     r9d, r9d
0x1800f66cb  mov     edx, ebx
0x1800f66cd  or      r9d, eax
0x1800f66d0  and     edx, 80h
0x1800f66d6  shl     r9d, 0Ah
0x1800f66da  mov     eax, edx
0x1800f66dc  neg     eax
0x1800f66de  sbb     ecx, ecx
0x1800f66e0  and     r8d, 0FFE5FFFFh
0x1800f66e7  and     ecx, 20000h
0x1800f66ed  or      r9d, ecx
0x1800f66f0  or      r9d, r8d
0x1800f66f3  mov     [rdi+6Ch], r9d
0x1800f66f7  test    edx, edx
0x1800f66f9  jz      short loc_1800F670C
0x1800f66fb  xor     r8d, r8d; int *
0x1800f66fe  xor     edx, edx; int
0x1800f6700  mov     rcx, rdi; struct tagLBIV *
0x1800f6703  call    ?ListBox_SetTabStopsHandler@@YAHPEAUtagLBIV@@HPEBH@Z; ListBox_SetTabStopsHandler(tagLBIV *,int,int const *)
0x1800f6708  mov     r9d, [rdi+6Ch]
0x1800f670c  or      r14d, 0FFFFFFFFh
0x1800f6710  btr     r9d, 12h
0x1800f6715  mov     eax, ebx
0x1800f6717  mov     [rdi+78h], r14d
0x1800f671b  and     eax, 200h
0x1800f6720  mov     [rdi+7Ch], r14d
0x1800f6724  or      eax, 20h
0x1800f6727  mov     [rdi+80h], r14d
0x1800f672e  shl     eax, 9
0x1800f6731  or      eax, r9d
0x1800f6734  test    bl, 10h
0x1800f6737  jz      short loc_1800F6741
0x1800f6739  and     eax, 0FFFFFFFDh
0x1800f673c  or      eax, r13d
0x1800f673f  jmp     short loc_1800F6754
0x1800f6741  test    bl, 20h
0x1800f6744  jz      short loc_1800F6754
0x1800f6746  bt      eax, 12h
0x1800f674a  jb      short loc_1800F6754
0x1800f674c  and     eax, 0FFFFFFFEh
0x1800f674f  or      eax, 80002h
0x1800f6754  test    al, 3
0x1800f6756  jz      short loc_1800F6761
0x1800f6758  test    bl, 40h
0x1800f675b  jnz     short loc_1800F6761
0x1800f675d  btr     eax, 0Eh
0x1800f6761  and     eax, 0FFFFFFBFh
0x1800f6764  mov     ecx, ebx
0x1800f6766  and     ecx, 2
0x1800f6769  bts     ecx, 0Ah
0x1800f676d  shl     ecx, 5
0x1800f6770  or      ecx, eax
0x1800f6772  mov     [rdi+6Ch], ecx
0x1800f6775  bt      ebx, 0Dh
0x1800f6779  jnb     short loc_1800F6793
0x1800f677b  mov     eax, ecx
0x1800f677d  and     al, 3
0x1800f677f  cmp     al, r13b
0x1800f6782  jnz     short loc_1800F6793
0x1800f6784  test    ecx, 4040h
0x1800f678a  jnz     short loc_1800F6793
0x1800f678c  btr     ecx, 0Fh
0x1800f6790  mov     [rdi+6Ch], ecx
0x1800f6793  call    cs:__imp_GetThreadLocale
0x1800f6799  mov     [rdi+0B0h], eax
0x1800f679f  bt      ebx, 0Fh
0x1800f67a3  jnb     short loc_1800F67B7
0x1800f67a5  xor     edx, edx; nIndex
0x1800f67a7  mov     rcx, r15; hWnd
0x1800f67aa  call    cs:__imp_GetWindowLongPtrW
0x1800f67b0  mov     [rdi+0A0h], rax
0x1800f67b7  bts     dword ptr [rdi+6Ch], 10h
0x1800f67bc  mov     rcx, rdi; struct tagLBIV *
0x1800f67bf  mov     [rdi+24h], r14d
0x1800f67c3  mov     qword ptr [rdi+0A8h], 0
0x1800f67ce  call    ?ListBox_InitHStrings@@YAXPEAUtagLBIV@@@Z; ListBox_InitHStrings(tagLBIV *)
0x1800f67d3  test    dword ptr [rdi+6Ch], 4000h
0x1800f67da  jz      short loc_1800F67EB
0x1800f67dc  cmp     qword ptr [rdi+40h], 0
0x1800f67e1  jnz     short loc_1800F67EB
0x1800f67e3  mov     eax, r14d
0x1800f67e6  jmp     loc_1800F68FE
0x1800f67eb  mov     rcx, rsi; hWnd
0x1800f67ee  call    cs:__imp_GetDC
0x1800f67f4  mov     rcx, rax; hdc
0x1800f67f7  lea     rdx, [rbp+psizl]; psizl
0x1800f67fb  mov     rbx, rax
0x1800f67fe  call    GetCharDimensions
0x1800f6803  mov     ecx, [rbp+psizl.cx]
0x1800f6806  mov     rdx, rbx; hDC
0x1800f6809  mov     [rdi+50h], ecx
0x1800f680c  mov     ecx, [rbp+psizl.cy]
0x1800f680f  mov     [rdi+54h], ecx
0x1800f6812  mov     rcx, rsi; hWnd
0x1800f6815  call    cs:__imp_ReleaseDC
0x1800f681b  cmp     dword ptr [rdi+50h], 0
0x1800f681f  jz      short loc_1800F6827
0x1800f6821  cmp     dword ptr [rdi+54h], 0
0x1800f6825  jnz     short loc_1800F6835
0x1800f6827  mov     dword ptr [rdi+50h], 8
0x1800f682e  mov     dword ptr [rdi+54h], 10h
0x1800f6835  mov     eax, [rdi+6Ch]
0x1800f6838  and     eax, 3
0x1800f683b  cmp     eax, r13d
0x1800f683e  jnz     short loc_1800F689A
0x1800f6840  mov     rcx, rsi; hWnd
0x1800f6843  mov     dword ptr [rbp+lParam], 2
0x1800f684a  call    cs:__imp_GetDlgCtrlID
0x1800f6850  mov     rcx, [rdi+8]; hWnd
0x1800f6854  lea     r9, [rbp+lParam]; lParam
0x1800f6858  mov     r8d, eax; wParam
0x1800f685b  mov     edx, 2Ch ; ','; Msg
0x1800f6860  mov     eax, [rdi+54h]
0x1800f6863  mov     dword ptr [rbp+lParam+4], r8d
0x1800f6867  mov     dword ptr [rbp+var_18], eax
0x1800f686a  mov     dword ptr [rbp+lParam+0Ch], 0
0x1800f6871  mov     qword ptr [rbp+var_18+8], 0
0x1800f6879  call    cs:__imp_SendMessageW
0x1800f687f  mov     eax, dword ptr [rbp+var_18]
0x1800f6882  test    eax, eax
0x1800f6884  jz      short loc_1800F6889
0x1800f6886  mov     [rdi+54h], eax
0x1800f6889  test    dword ptr [rdi+6Ch], 40000h
0x1800f6890  jz      short loc_1800F68A6
0x1800f6892  mov     eax, dword ptr [rbp+lParam+0Ch]
0x1800f6895  mov     [rdi+58h], eax
0x1800f6898  jmp     short loc_1800F68A6
0x1800f689a  cmp     eax, 2
0x1800f689d  jnz     short loc_1800F68A6
0x1800f689f  mov     dword ptr [rdi+54h], 0
0x1800f68a6  movzx   edx, cs:g_atomTabletPcPenService; lpString
0x1800f68ad  mov     r8, r13; hData
0x1800f68b0  mov     rcx, [rdi]; hWnd
0x1800f68b3  call    cs:__imp_SetPropW
0x1800f68b9  test    dword ptr [rdi+6Ch], 40000h
0x1800f68c0  jz      short loc_1800F68D7
0x1800f68c2  cmp     dword ptr [rdi+58h], 0
0x1800f68c6  jg      short loc_1800F68CF
0x1800f68c8  imul    eax, [rdi+50h], 0Fh
0x1800f68cc  mov     [rdi+58h], eax
0x1800f68cf  mov     [rdi+5Ch], r13d
0x1800f68d3  mov     [rdi+60h], r13d
0x1800f68d7  mov     rcx, rdi; struct tagLBIV *
0x1800f68da  call    ?ListBox_SetCItemFullMax@@YAXPEAUtagLBIV@@@Z; ListBox_SetCItemFullMax(tagLBIV *)
0x1800f68df  test    dword ptr [rdi+6Ch], 80000h
0x1800f68e6  jnz     short loc_1800F68FB
0x1800f68e8  xor     r9d, r9d; lParam
0x1800f68eb  xor     r8d, r8d; wParam
0x1800f68ee  mov     rcx, rsi; hWnd
0x1800f68f1  lea     edx, [r9+5]; Msg
0x1800f68f5  call    cs:__imp_PostMessageW
0x1800f68fb  mov     eax, r13d
0x1800f68fe  mov     rcx, [rbp+var_8]
0x1800f6902  xor     rcx, rsp; StackCookie
0x1800f6905  call    __security_check_cookie
0x1800f690a  add     rsp, 50h
0x1800f690e  pop     r15
0x1800f6910  pop     r14
0x1800f6912  pop     r13
0x1800f6914  pop     rdi
0x1800f6915  pop     rsi
0x1800f6916  pop     rbx
0x1800f6917  pop     rbp
0x1800f6918  retn
```
