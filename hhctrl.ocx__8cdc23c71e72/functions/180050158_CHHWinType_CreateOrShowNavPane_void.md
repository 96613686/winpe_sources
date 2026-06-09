# CHHWinType::CreateOrShowNavPane(void)

- ea: `0x180050158`
- end: `0x1800508c8`
- name: `?CreateOrShowNavPane@CHHWinType@@QEAAXXZ`
- size: `1904`
- prototype: `void __fastcall(CHHWinType *__hidden this)`
- caller_count: `2`
- callee_count: `27`
- tags: `broker_com_uri`

## callers

- `0x180053170`
- `0x18006eaf4`

## callees

- `0x180001728`
- `0x1800053b4`
- `0x180006708`
- `0x18000d5bc`
- `0x18001054c`
- `0x180011490`
- `0x1800139bc`
- `0x18001706c`
- `0x180028598`
- `0x18004f8dc`
- `0x180050004`
- `0x180050158`
- `0x180051cfc`
- `0x180052228`
- `0x180052258`
- `0x1800523d8`
- `0x180058818`
- `0x18005c928`
- `0x18005c9b0`
- `0x18005ef14`
- `0x180064990`
- `0x1800675c0`
- `0x180067798`
- `0x18006a240`
- `0x18007236c`
- `0x180075c90`
- `0x180078010`

## import_xrefs

- `msvcrt!malloc` at `0x1800504e0`
- `msvcrt!malloc` at `0x1800504e0`
- `msvcrt!free` at `0x180050527`
- `msvcrt!free` at `0x180050527`
- `USER32!ReleaseDC` at `0x180050266`
- `USER32!ReleaseDC` at `0x180050266`
- `USER32!GetDC` at `0x18005022f`
- `USER32!GetDC` at `0x18005022f`
- `USER32!SetWindowTextW` at `0x18005036f`
- `USER32!SetWindowTextW` at `0x18005036f`
- `USER32!ShowWindow` at `0x180050414`
- `USER32!ShowWindow` at `0x180050423`
- `USER32!ShowWindow` at `0x1800507ab`
- `USER32!ShowWindow` at `0x1800507c2`
- `USER32!ShowWindow` at `0x1800507d6`
- `USER32!ShowWindow` at `0x1800507ea`
- `USER32!ShowWindow` at `0x180050414`
- `USER32!ShowWindow` at `0x180050423`
- `USER32!ShowWindow` at `0x1800507ab`
- `USER32!ShowWindow` at `0x1800507c2`
- `USER32!ShowWindow` at `0x1800507d6`
- `USER32!ShowWindow` at `0x1800507ea`
- `USER32!SendMessageA` at `0x180050316`
- `USER32!SendMessageA` at `0x1800503e8`
- `USER32!SendMessageA` at `0x180050558`
- `USER32!SendMessageA` at `0x1800505e9`
- `USER32!SendMessageA` at `0x18005085b`
- `USER32!SendMessageA` at `0x180050316`
- `USER32!SendMessageA` at `0x1800503e8`
- `USER32!SendMessageA` at `0x180050558`
- `USER32!SendMessageA` at `0x1800505e9`
- `USER32!SendMessageA` at `0x18005085b`
- `USER32!SendMessageW` at `0x18005051e`
- `USER32!SendMessageW` at `0x1800505cd`
- `USER32!SendMessageW` at `0x18005051e`
- `USER32!SendMessageW` at `0x1800505cd`
- `GDI32!SelectObject` at `0x18005023e`
- `GDI32!SelectObject` at `0x18005025b`
- `GDI32!SelectObject` at `0x18005023e`
- `GDI32!SelectObject` at `0x18005025b`
- `GDI32!GetTextMetricsA` at `0x18005024f`
- `GDI32!GetTextMetricsA` at `0x18005024f`

## string_xrefs

- `0x1800503ba`: `COMBOBOX`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CHHWinType::CreateOrShowNavPane(CHHWinType *this)
{
  int *v2; // r12
  int v3; // eax
  CResourceCache *v4; // rcx
  __int64 v5; // rax
  HDC DC; // rdi
  HGDIOBJ v7; // rbx
  int v8; // r15d
  HINSTANCE v9; // rsi
  HWND v10; // r14
  const CHAR *StringResource; // rax
  HWND Window; // rax
  LONG tmHeight; // edx
  int v14; // ebx
  int v15; // r14d
  int v16; // esi
  int v17; // edi
  const WCHAR *StringResourceW; // rax
  HFONT AccessableContentFont; // rax
  int v20; // eax
  __int64 v21; // rsi
  __int64 v22; // rdi
  __int64 v23; // rcx
  __int64 v24; // rax
  int v25; // eax
  unsigned int v26; // ecx
  struct CTitleInformation *Info; // rbx
  unsigned int v28; // r12d
  __int64 v29; // rcx
  unsigned int v30; // r14d
  WCHAR *v31; // rax
  int v32; // r9d
  WCHAR *v33; // rbx
  unsigned int v34; // eax
  int v35; // r9d
  struct CStructuralSubset *v36; // rdx
  CSSList *v37; // rcx
  int v38; // ebx
  int i; // edx
  int IsValidNavPane; // eax
  int v41; // edx
  int v42; // ecx
  int v43; // edi
  int j; // ebx
  CTabControl *v45; // rax
  CTabControl *v46; // rax
  HWND *v47; // rcx
  HWND v48; // rcx
  HWND v49; // rcx
  int ValidNavPane; // edx
  __int64 v51; // rdx
  int TabIndexFromNavPaneIndex; // eax
  HWND *v53; // r10
  __int64 v54; // rcx
  __int64 v55; // rcx
  CSizeBar *v56; // rcx
  void *v57; // [rsp+58h] [rbp-A8h]
  HFONT wParam; // [rsp+70h] [rbp-90h]
  struct tagTEXTMETRICA tm; // [rsp+78h] [rbp-88h] BYREF
  WCHAR lParam[56]; // [rsp+B0h] [rbp-50h] BYREF

  v2 = (int *)((char *)this + 520);
  if ( (*((_DWORD *)this + 5) & 0x4000) != 0 )
    *v2 = *((_DWORD *)this + 31);
  if ( !(unsigned int)IsValidWindow(*((HWND *)this + 12)) )
  {
    *((_DWORD *)this + 128) = 0;
    if ( *((int *)this + 130) <= 0 )
    {
      v3 = 290;
      if ( *((_DWORD *)this + 28) )
        v3 = *((_DWORD *)this + 28);
      *v2 = v3;
    }
    CHHWinType::CalcHtmlPaneRect(this);
    v5 = *((_QWORD *)this + 76);
    if ( v5 )
    {
      if ( *(_DWORD *)(v5 + 116) )
      {
        if ( !*(_DWORD *)(*(_QWORD *)(v5 + 128) + 1096LL) )
        {
          memset(&tm, 0, sizeof(tm));
          wParam = CResourceCache::GetAccessableUIFont(v4);
          DC = GetDC(0);
          v7 = SelectObject(DC, wParam);
          GetTextMetricsA(DC, &tm);
          SelectObject(DC, v7);
          ReleaseDC(0, DC);
          *((_DWORD *)this + 129) += 5;
          v8 = *((_DWORD *)this + 129);
          *((_DWORD *)this + 164) = 5;
          v9 = hInstance;
          v10 = (HWND)*((_QWORD *)this + 8);
          LODWORD(v7) = *((_DWORD *)this + 128);
          LODWORD(DC) = *((_DWORD *)this + 130) - (_DWORD)v7 - 8;
          StringResource = GetStringResource(0x4D3u);
          Window = IsolationAwareCreateWindowExA(
                     0,
                     "STATIC",
                     StringResource,
                     0x40000000u,
                     (int)v7 + 6,
                     v8,
                     (int)DC,
                     tm.tmHeight,
                     v10,
                     0,
                     v9,
                     0);
          *((_QWORD *)this + 81) = Window;
          if ( Window )
          {
            SendMessageA(Window, 0x30u, (WPARAM)wParam, 0);
            tmHeight = tm.tmHeight;
            *((_DWORD *)this + 129) += tm.tmHeight + 2;
            v14 = *((_DWORD *)this + 129);
            *((_DWORD *)this + 164) += tmHeight + 2;
            v15 = *((_DWORD *)this + 128) + 6;
            v16 = *v2 - 10;
            v17 = v14 + tmHeight + 10;
            if ( g_bWinNT5 )
            {
              StringResourceW = GetStringResourceW(0x4D3u);
              SetWindowTextW(*((HWND *)this + 81), StringResourceW);
            }
            *((_QWORD *)this + 80) = IsolationAwareCreateWindowExA(
                                       0,
                                       "COMBOBOX",
                                       0,
                                       0x40200103u,
                                       v15,
                                       v14,
                                       v16 - v15,
                                       v17 - v14 + 80,
                                       *((HWND *)this + 8),
                                       (HMENU)0x1831,
                                       hInstance,
                                       0);
            AccessableContentFont = CHHWinType::GetAccessableContentFont(this);
            SendMessageA(*((HWND *)this + 80), 0x30u, (WPARAM)AccessableContentFont, 0);
            v20 = tm.tmHeight + 11;
            *((_DWORD *)this + 129) += tm.tmHeight + 11;
            *((_DWORD *)this + 164) += v20;
            ShowWindow(*((HWND *)this + 81), 5);
            ShowWindow(*((HWND *)this + 80), 5);
            if ( *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 76) + 128LL) + 48LL) )
            {
              v21 = 0;
              v22 = 0;
              while ( 1 )
              {
                v23 = *(_QWORD *)(*((_QWORD *)this + 76) + 128LL);
                v24 = *(_QWORD *)(v23 + 48);
                v22 = v22 ? *(_QWORD *)(v22 + 120) : *(_QWORD *)(v24 + 8);
                if ( !v22 )
                  break;
                v25 = *(_DWORD *)(v22 + 128);
                if ( (v25 & 4) == 0 )
                {
                  if ( g_bWinNT5 )
                  {
                    if ( (v25 & 1) != 0 )
                    {
                      CLanguage::_Init((CLanguage *)&off_18008B4C0);
                      v26 = (unsigned __int16)word_18008B4C8;
                    }
                    else
                    {
                      Info = CExTitle::GetInfo(*(CExTitle **)(v23 + 1080));
                      CTitleInformation::Init(Info);
                      v26 = *((_DWORD *)Info + 4);
                    }
                    v28 = CodePageFromLCID(v26);
                    v29 = -1;
                    do
                      ++v29;
                    while ( *(_BYTE *)(v22 + v29 + 16) );
                    v30 = 2 * v29 + 4;
                    v31 = (WCHAR *)malloc(v30);
                    v33 = v31;
                    if ( v31 )
                    {
                      HHMultiByteToWideChar(v28, 1u, (const char *)(v22 + 16), v32, v31, v30 >> 1);
                      SendMessageW(*((HWND *)this + 80), 0x143u, 0, (LPARAM)v33);
                      free(v33);
                    }
                  }
                  else
                  {
                    SendMessageA(*((HWND *)this + 80), 0x143u, 0, v22 + 16);
                  }
                }
                if ( (*(_BYTE *)(v22 + 128) & 0x10) != 0 )
                  v21 = v22;
              }
              if ( !v21 )
                v21 = *(_QWORD *)(v24 + 48);
              if ( g_bWinNT5 && (*(_BYTE *)(v21 + 128) & 1) != 0 )
              {
                lParam[0] = 0;
                CLanguage::_Init((CLanguage *)&off_18008B4C0);
                v34 = CodePageFromLCID((unsigned __int16)word_18008B4C8);
                HHMultiByteToWideChar(v34, 1u, (const char *)(v21 + 16), v35, lParam, 51);
                SendMessageW(*((HWND *)this + 80), 0x14Du, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)lParam);
              }
              else
              {
                SendMessageA(*((HWND *)this + 80), 0x14Du, 0xFFFFFFFFFFFFFFFFuLL, v21 + 16);
              }
              CSSList::Set(
                *(CSSList **)(*((_QWORD *)this + 76) + 128LL),
                (struct CStructuralSubset *)v21,
                (struct CStructuralSubset **)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 76) + 128LL) + 48LL) + 16LL),
                8u);
              CSSList::Set(
                *((CSSList **)this + 76),
                v36,
                (struct CStructuralSubset **)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 76) + 128LL) + 48LL) + 24LL),
                0x20u);
              CSSList::Set(
                v37,
                (struct CStructuralSubset *)v21,
                (struct CStructuralSubset **)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 76) + 128LL) + 48LL) + 32LL),
                0x10u);
              CStructuralSubset::SelectAsTOCSubset(
                (CStructuralSubset *)v21,
                *(struct CExCollection **)(*((_QWORD *)this + 76) + 128LL));
            }
          }
        }
      }
    }
    *((_QWORD *)this + 12) = W_CreateWindowEx(
                               0,
                               L"HH Child",
                               0,
                               0x40000000u,
                               *((_DWORD *)this + 128),
                               *((_DWORD *)this + 129),
                               *((_DWORD *)this + 130) - *((_DWORD *)this + 128),
                               *((_DWORD *)this + 131) - *((_DWORD *)this + 129),
                               *((HWND *)this + 8),
                               0,
                               hInstance,
                               v57,
                               0);
    v38 = 0;
    for ( i = 0; i < 20; i = v41 + 1 )
    {
      IsValidNavPane = CHHWinType::IsValidNavPane(this, i);
      v42 = v38 + 1;
      if ( !IsValidNavPane )
        v42 = v38;
      v38 = v42;
    }
    if ( v42 > 1 )
    {
      v43 = 19;
      for ( j = 0; j < v43; ++j )
      {
        if ( !(unsigned int)CHHWinType::IsValidNavPane(this, *((unsigned __int8 *)this + j + 188)) )
        {
          MemMove((char *)this + j + 188, (char *)this + j + 189, v43 - j);
          --j;
          --v43;
        }
      }
      v45 = (CTabControl *)operator new(0xC0u);
      if ( v45 )
        v46 = CTabControl::CTabControl(v45, *((HWND *)this + 12), *((_DWORD *)this + 45), this);
      else
        v46 = 0;
      *((_QWORD *)this + 74) = v46;
    }
    ResizeWindow(this, 1);
  }
  if ( (*((_DWORD *)this + 5) & 0x8000) == 0 )
    ShowWindow(*((HWND *)this + 12), 5);
  v47 = (HWND *)*((_QWORD *)this + 74);
  if ( v47 )
    ShowWindow(*v47, 5);
  v48 = (HWND)*((_QWORD *)this + 81);
  if ( v48 )
    ShowWindow(v48, 5);
  v49 = (HWND)*((_QWORD *)this + 80);
  if ( v49 )
    ShowWindow(v49, 5);
  if ( (unsigned int)CHHWinType::IsValidNavPane(this, *((_DWORD *)this + 44))
    || (ValidNavPane = CHHWinType::GetValidNavPane(this), *((_DWORD *)this + 44) = ValidNavPane, ValidNavPane >= 0) )
  {
    CHHWinType::CreateNavPane(this, ValidNavPane);
    v51 = *((int *)this + 44);
    if ( *((_QWORD *)this + v51 + 42) )
    {
      if ( (_DWORD)v51 && *((_QWORD *)this + 74) )
      {
        TabIndexFromNavPaneIndex = CHHWinType::GetTabIndexFromNavPaneIndex(this, v51);
        SendMessageA(*v53, 0x130Cu, TabIndexFromNavPaneIndex, 0);
      }
      v54 = *((_QWORD *)this + *((int *)this + 44) + 42);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 40LL))(v54);
      v55 = *((_QWORD *)this + *((int *)this + 44) + 42);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 24LL))(v55);
    }
    v56 = (CSizeBar *)*((_QWORD *)this + 40);
    if ( v56 )
      CSizeBar::ResizeWindow(v56);
  }
}

```

## disassembly

```asm
0x180050158  push    rbp
0x18005015a  push    rbx
0x18005015b  push    rsi
0x18005015c  push    rdi
0x18005015d  push    r12
0x18005015f  push    r13
0x180050161  push    r14
0x180050163  push    r15
0x180050165  lea     rbp, [rsp-38h]
0x18005016a  sub     rsp, 138h
0x180050171  mov     rax, cs:__security_cookie
0x180050178  xor     rax, rsp
0x18005017b  mov     [rbp+70h+var_50], rax
0x18005017f  mov     r13, rcx
0x180050182  lea     r12, [rcx+208h]
0x180050189  test    dword ptr [rcx+14h], 4000h
0x180050190  jz      short loc_180050199
0x180050192  mov     eax, [rcx+7Ch]
0x180050195  mov     [r12], eax
0x180050199  mov     rcx, [rcx+60h]; HWND
0x18005019d  call    ?IsValidWindow@@YAHPEAUHWND__@@@Z; IsValidWindow(HWND__ *)
0x1800501a2  mov     esi, 5
0x1800501a7  xor     r15d, r15d
0x1800501aa  test    eax, eax
0x1800501ac  jnz     loc_18005079B
0x1800501b2  mov     [r13+200h], r15d
0x1800501b9  cmp     [r13+208h], r15d
0x1800501c0  jg      short loc_1800501D4
0x1800501c2  mov     eax, 122h
0x1800501c7  cmp     [r13+70h], r15d
0x1800501cb  cmovnz  eax, [r13+70h]
0x1800501d0  mov     [r12], eax
0x1800501d4  mov     rcx, r13; this
0x1800501d7  call    ?CalcHtmlPaneRect@CHHWinType@@QEAAXXZ; CHHWinType::CalcHtmlPaneRect(void)
0x1800501dc  mov     rax, [r13+260h]
0x1800501e3  test    rax, rax
0x1800501e6  jz      loc_18005066E
0x1800501ec  cmp     [rax+74h], r15d
0x1800501f0  jz      loc_18005066E
0x1800501f6  mov     rax, [rax+80h]
0x1800501fd  cmp     [rax+448h], r15d
0x180050204  jnz     loc_18005066E
0x18005020a  xorps   xmm0, xmm0
0x18005020d  xor     eax, eax
0x18005020f  movups  xmmword ptr [rsp+170h+tm.tmHeight], xmm0
0x180050214  movups  xmmword ptr [rbp+70h+tm.tmExternalLeading], xmm0
0x180050218  movups  xmmword ptr [rbp+70h+tm.tmOverhang], xmm0
0x18005021c  mov     qword ptr [rbp+70h+tm.tmItalic], rax
0x180050220  call    ?GetAccessableUIFont@CResourceCache@@QEAAPEAUHFONT__@@XZ; CResourceCache::GetAccessableUIFont(void)
0x180050225  mov     rbx, rax
0x180050228  mov     [rsp+170h+wParam], rax
0x18005022d  xor     ecx, ecx; hWnd
0x18005022f  call    cs:__imp_GetDC
0x180050235  mov     rdi, rax
0x180050238  mov     rdx, rbx; h
0x18005023b  mov     rcx, rax; hdc
0x18005023e  call    cs:__imp_SelectObject
0x180050244  mov     rbx, rax
0x180050247  lea     rdx, [rsp+170h+tm]; lptm
0x18005024c  mov     rcx, rdi; hdc
0x18005024f  call    cs:__imp_GetTextMetricsA
0x180050255  mov     rdx, rbx; h
0x180050258  mov     rcx, rdi; hdc
0x18005025b  call    cs:__imp_SelectObject
0x180050261  mov     rdx, rdi; hDC
0x180050264  xor     ecx, ecx; hWnd
0x180050266  call    cs:__imp_ReleaseDC
0x18005026c  add     [r13+204h], esi
0x180050273  mov     r15d, [r13+204h]
0x18005027a  mov     [r13+290h], esi
0x180050281  mov     rsi, cs:hInstance
0x180050288  mov     r14, [r13+40h]
0x18005028c  mov     ebx, [r13+200h]
0x180050293  mov     edi, [r13+208h]
0x18005029a  sub     edi, ebx
0x18005029c  add     edi, 0FFFFFFF8h
0x18005029f  mov     ecx, 4D3h; uID
0x1800502a4  call    ?GetStringResource@@YAPEBDH@Z; GetStringResource(int)
0x1800502a9  add     ebx, 6
0x1800502ac  mov     [rsp+170h+var_118], 0; LPVOID
0x1800502b5  mov     [rsp+170h+var_120], rsi; HINSTANCE
0x1800502ba  mov     [rsp+170h+var_128], 0; HMENU
0x1800502c3  mov     [rsp+170h+var_130], r14; HWND
0x1800502c8  mov     ecx, [rsp+170h+tm.tmHeight]
0x1800502cc  mov     [rsp+170h+var_138], ecx; int
0x1800502d0  mov     [rsp+170h+var_140], edi; int
0x1800502d4  mov     [rsp+170h+var_148], r15d; int
0x1800502d9  mov     dword ptr [rsp+170h+var_150], ebx; int
0x1800502dd  mov     r9d, 40000000h; dwStyle
0x1800502e3  mov     r8, rax; lpWindowName
0x1800502e6  lea     rdx, aStatic_1; "STATIC"
0x1800502ed  xor     ecx, ecx; dwExStyle
0x1800502ef  call    IsolationAwareCreateWindowExA
0x1800502f4  mov     [r13+288h], rax
0x1800502fb  xor     r15d, r15d
0x1800502fe  test    rax, rax
0x180050301  jz      loc_18005066E
0x180050307  xor     r9d, r9d; lParam
0x18005030a  mov     r8, [rsp+170h+wParam]; wParam
0x18005030f  lea     edx, [r15+30h]; Msg
0x180050313  mov     rcx, rax; hWnd
0x180050316  call    cs:__imp_SendMessageA
0x18005031c  mov     edx, [rsp+170h+tm.tmHeight]
0x180050320  lea     eax, [rdx+2]
0x180050323  add     [r13+204h], eax
0x18005032a  mov     ebx, [r13+204h]
0x180050331  lea     eax, [rdx+2]
0x180050334  add     [r13+290h], eax
0x18005033b  mov     r14d, [r13+200h]
0x180050342  add     r14d, 6
0x180050346  mov     esi, [r12]
0x18005034a  add     esi, 0FFFFFFF6h
0x18005034d  lea     edi, [rdx+0Ah]
0x180050350  add     edi, ebx
0x180050352  cmp     cs:?g_bWinNT5@@3HA, r15d; int g_bWinNT5
0x180050359  jz      short loc_180050375
0x18005035b  mov     ecx, 4D3h; uID
0x180050360  call    ?GetStringResourceW@@YAPEBGH@Z; GetStringResourceW(int)
0x180050365  mov     rdx, rax; lpString
0x180050368  mov     rcx, [r13+288h]; hWnd
0x18005036f  call    cs:__imp_SetWindowTextW
0x180050375  sub     edi, ebx
0x180050377  add     edi, 50h ; 'P'
0x18005037a  sub     esi, r14d
0x18005037d  mov     [rsp+170h+var_118], r15; void *
0x180050382  mov     rax, cs:hInstance
0x180050389  mov     [rsp+170h+var_120], rax; HINSTANCE
0x18005038e  mov     [rsp+170h+var_128], 1831h; HMENU
0x180050397  mov     rax, [r13+40h]
0x18005039b  mov     [rsp+170h+var_130], rax; HWND
0x1800503a0  mov     [rsp+170h+var_138], edi; int
0x1800503a4  mov     [rsp+170h+var_140], esi; int
0x1800503a8  mov     [rsp+170h+var_148], ebx; int
0x1800503ac  mov     dword ptr [rsp+170h+var_150], r14d; int
0x1800503b1  mov     r9d, 40200103h; dwStyle
0x1800503b7  xor     r8d, r8d; lpWindowName
0x1800503ba  lea     rdx, aCombobox_0; "COMBOBOX"
0x1800503c1  xor     ecx, ecx; dwExStyle
0x1800503c3  call    IsolationAwareCreateWindowExA
0x1800503c8  mov     [r13+280h], rax
0x1800503cf  mov     rcx, r13; this
0x1800503d2  call    ?GetAccessableContentFont@CHHWinType@@QEAAPEAUHFONT__@@XZ; CHHWinType::GetAccessableContentFont(void)
0x1800503d7  xor     r9d, r9d; lParam
0x1800503da  mov     r8, rax; wParam
0x1800503dd  lea     edx, [r9+30h]; Msg
0x1800503e1  mov     rcx, [r13+280h]; hWnd
0x1800503e8  call    cs:__imp_SendMessageA
0x1800503ee  mov     ecx, [rsp+170h+tm.tmHeight]
0x1800503f2  lea     eax, [rcx+0Bh]
0x1800503f5  add     [r13+204h], eax
0x1800503fc  lea     eax, [rcx+0Bh]
0x1800503ff  add     [r13+290h], eax
0x180050406  mov     ebx, 5
0x18005040b  mov     edx, ebx; nCmdShow
0x18005040d  mov     rcx, [r13+288h]; hWnd
0x180050414  call    cs:__imp_ShowWindow
0x18005041a  mov     edx, ebx; nCmdShow
0x18005041c  mov     rcx, [r13+280h]; hWnd
0x180050423  call    cs:__imp_ShowWindow
0x180050429  mov     rax, [r13+260h]
0x180050430  mov     rcx, [rax+80h]
0x180050437  cmp     [rcx+30h], r15
0x18005043b  jz      loc_18005066E
0x180050441  mov     rsi, r15
0x180050444  mov     rdi, r15
0x180050447  mov     rax, [r13+260h]
0x18005044e  mov     rcx, [rax+80h]
0x180050455  mov     rax, [rcx+30h]
0x180050459  test    rdi, rdi
0x18005045c  jz      short loc_180050464
0x18005045e  mov     rdi, [rdi+78h]
0x180050462  jmp     short loc_180050468
0x180050464  mov     rdi, [rax+8]
0x180050468  test    rdi, rdi
0x18005046b  jz      loc_180050560
0x180050471  mov     eax, [rdi+80h]
0x180050477  test    al, 4
0x180050479  jnz     loc_180050530
0x18005047f  cmp     cs:?g_bWinNT5@@3HA, r15d; int g_bWinNT5
0x180050486  jz      loc_180050545
0x18005048c  test    al, 1
0x18005048e  jz      short loc_1800504A5
0x180050490  lea     rcx, off_18008B4C0; this
0x180050497  call    ?_Init@CLanguage@@AEAAXXZ; CLanguage::_Init(void)
0x18005049c  movzx   ecx, cs:word_18008B4C8
0x1800504a3  jmp     short loc_1800504BF
0x1800504a5  mov     rcx, [rcx+438h]; this
0x1800504ac  call    ?GetInfo@CExTitle@@QEAAPEAVCTitleInformation@@XZ; CExTitle::GetInfo(void)
0x1800504b1  mov     rbx, rax
0x1800504b4  mov     rcx, rax; this
0x1800504b7  call    ?Init@CTitleInformation@@AEAAHXZ; CTitleInformation::Init(void)
0x1800504bc  mov     ecx, [rbx+10h]; unsigned int
0x1800504bf  call    ?CodePageFromLCID@@YAIK@Z; CodePageFromLCID(ulong)
0x1800504c4  mov     r12d, eax
0x1800504c7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800504cb  inc     rcx
0x1800504ce  cmp     byte ptr [rdi+rcx+10h], 0
0x1800504d3  jnz     short loc_1800504CB
0x1800504d5  lea     r14d, ds:4[rcx*2]
0x1800504dd  mov     ecx, r14d; Size
0x1800504e0  call    cs:__imp_malloc
0x1800504e6  mov     rbx, rax
0x1800504e9  test    rax, rax
0x1800504ec  jz      short loc_18005052D
0x1800504ee  shr     r14d, 1
0x1800504f1  mov     [rsp+170h+var_148], r14d; int
0x1800504f6  mov     [rsp+170h+var_150], rax; LPWSTR
0x1800504fb  lea     r8, [rdi+10h]; char *
0x1800504ff  mov     edx, 1; unsigned int
0x180050504  mov     ecx, r12d; unsigned int
0x180050507  call    ?HHMultiByteToWideChar@@YAHIKPEBDHPEAGH@Z; HHMultiByteToWideChar(uint,ulong,char const *,int,ushort *,int)
0x18005050c  mov     r9, rbx; lParam
0x18005050f  xor     r8d, r8d; wParam
0x180050512  mov     edx, 143h; Msg
0x180050517  mov     rcx, [r13+280h]; hWnd
0x18005051e  call    cs:__imp_SendMessageW
0x180050524  mov     rcx, rbx; Block
0x180050527  call    cs:__imp_free
0x18005052d  xor     r15d, r15d
0x180050530  test    byte ptr [rdi+80h], 10h
0x180050537  jz      loc_180050447
0x18005053d  mov     rsi, rdi
0x180050540  jmp     loc_180050447
0x180050545  lea     r9, [rdi+10h]; lParam
0x180050549  xor     r8d, r8d; wParam
0x18005054c  mov     edx, 143h; Msg
0x180050551  mov     rcx, [r13+280h]; hWnd
0x180050558  call    cs:__imp_SendMessageA
0x18005055e  jmp     short loc_180050530
0x180050560  test    rsi, rsi
0x180050563  jnz     short loc_180050569
0x180050565  mov     rsi, [rax+30h]
0x180050569  cmp     cs:?g_bWinNT5@@3HA, r15d; int g_bWinNT5
0x180050570  jz      short loc_1800505D5
0x180050572  test    byte ptr [rsi+80h], 1
0x180050579  jz      short loc_1800505D5
0x18005057b  mov     [rbp+70h+lParam], r15w
0x180050580  lea     rcx, off_18008B4C0; this
0x180050587  call    ?_Init@CLanguage@@AEAAXXZ; CLanguage::_Init(void)
0x18005058c  movzx   ecx, cs:word_18008B4C8; unsigned int
0x180050593  call    ?CodePageFromLCID@@YAIK@Z; CodePageFromLCID(ulong)
0x180050598  lea     r8, [rsi+10h]; char *
0x18005059c  mov     [rsp+170h+var_148], 33h ; '3'; int
0x1800505a4  lea     rcx, [rbp+70h+lParam]
0x1800505a8  mov     [rsp+170h+var_150], rcx; LPWSTR
0x1800505ad  mov     edx, 1; unsigned int
0x1800505b2  mov     ecx, eax; unsigned int
0x1800505b4  call    ?HHMultiByteToWideChar@@YAHIKPEBDHPEAGH@Z; HHMultiByteToWideChar(uint,ulong,char const *,int,ushort *,int)
0x1800505b9  lea     r9, [rbp+70h+lParam]; lParam
0x1800505bd  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x1800505c1  mov     edx, 14Dh; Msg
0x1800505c6  mov     rcx, [r13+280h]; hWnd
0x1800505cd  call    cs:__imp_SendMessageW
0x1800505d3  jmp     short loc_1800505EF
0x1800505d5  lea     r9, [rsi+10h]; lParam
0x1800505d9  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x1800505dd  mov     edx, 14Dh; Msg
0x1800505e2  mov     rcx, [r13+280h]; hWnd
0x1800505e9  call    cs:__imp_SendMessageA
0x1800505ef  mov     rax, [r13+260h]
0x1800505f6  mov     rcx, [rax+80h]; this
0x1800505fd  mov     r8, [rcx+30h]
0x180050601  add     r8, 10h; struct CStructuralSubset **
0x180050605  mov     r9d, 8; unsigned int
0x18005060b  mov     rdx, rsi; struct CStructuralSubset *
0x18005060e  call    ?Set@CSSList@@AEAAXPEAVCStructuralSubset@@PEAPEAV2@K@Z; CSSList::Set(CStructuralSubset *,CStructuralSubset * *,ulong)
0x180050613  mov     rcx, [r13+260h]; this
0x18005061a  mov     rax, [rcx+80h]
0x180050621  mov     r8, [rax+30h]
0x180050625  add     r8, 18h; struct CStructuralSubset **
0x180050629  mov     r9d, 20h ; ' '; unsigned int
0x18005062f  call    ?Set@CSSList@@AEAAXPEAVCStructuralSubset@@PEAPEAV2@K@Z; CSSList::Set(CStructuralSubset *,CStructuralSubset * *,ulong)
0x180050634  mov     rdx, [r13+260h]
0x18005063b  mov     rax, [rdx+80h]
0x180050642  mov     r8, [rax+30h]
0x180050646  add     r8, 20h ; ' '; struct CStructuralSubset **
0x18005064a  mov     r9d, 10h; unsigned int
0x180050650  mov     rdx, rsi; struct CStructuralSubset *
0x180050653  call    ?Set@CSSList@@AEAAXPEAVCStructuralSubset@@PEAPEAV2@K@Z; CSSList::Set(CStructuralSubset *,CStructuralSubset * *,ulong)
0x180050658  mov     rdx, [r13+260h]
0x18005065f  mov     rdx, [rdx+80h]; struct CExCollection *
0x180050666  mov     rcx, rsi; this
0x180050669  call    ?SelectAsTOCSubset@CStructuralSubset@@QEAAXPEAVCExCollection@@@Z; CStructuralSubset::SelectAsTOCSubset(CExCollection *)
0x18005066e  mov     edx, [r13+20Ch]
0x180050675  sub     edx, [r13+204h]
0x18005067c  mov     r8d, [r13+200h]
0x180050683  mov     ecx, [r13+208h]
0x18005068a  sub     ecx, r8d
0x18005068d  mov     [rsp+170h+var_110], r15; int *
0x180050692  mov     rax, cs:hInstance
0x180050699  mov     [rsp+170h+var_120], rax; HINSTANCE
0x18005069e  mov     [rsp+170h+var_128], r15; HMENU
0x1800506a3  mov     rax, [r13+40h]
0x1800506a7  mov     [rsp+170h+var_130], rax; HWND
0x1800506ac  mov     [rsp+170h+var_138], edx; int
0x1800506b0  mov     [rsp+170h+var_140], ecx; int
0x1800506b4  mov     eax, [r13+204h]
0x1800506bb  mov     [rsp+170h+var_148], eax; int
0x1800506bf  mov     dword ptr [rsp+170h+var_150], r8d; int
0x1800506c4  mov     r9d, 40000000h; dwStyle
  ... truncated ...
```
