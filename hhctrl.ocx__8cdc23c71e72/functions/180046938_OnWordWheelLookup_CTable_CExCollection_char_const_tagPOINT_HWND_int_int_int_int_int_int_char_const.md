# OnWordWheelLookup(CTable *,CExCollection *,char const *,tagPOINT *,HWND__ *,int,int,int,int,int,int,char const *)

- ea: `0x180046938`
- end: `0x180046f47`
- name: `?OnWordWheelLookup@@YAJPEAVCTable@@PEAVCExCollection@@PEBDPEAUtagPOINT@@PEAUHWND__@@HHHHHH2@Z`
- size: `1551`
- prototype: `__int64 __fastcall(struct CTable *, struct CExCollection *, const char *, struct tagPOINT *, HWND, int, int, int, int, int, int, const char *)`
- caller_count: `2`
- callee_count: `29`
- tags: `broker_com_uri`

## callers

- `0x180044dd0`
- `0x180046f50`

## callees

- `0x1800029b8`
- `0x180003fc0`
- `0x1800095c8`
- `0x1800115b0`
- `0x180011e94`
- `0x1800123d0`
- `0x1800128a8`
- `0x180019668`
- `0x18001c904`
- `0x18002018c`
- `0x180025a78`
- `0x180025d84`
- `0x180025f28`
- `0x180025ff4`
- `0x180028598`
- `0x180038640`
- `0x18003aba4`
- `0x180044330`
- `0x180046938`
- `0x18004f794`
- `0x180051bb8`
- `0x180052104`
- `0x18005d3ac`
- `0x180064acc`
- `0x18006a284`
- `0x18006fa2c`
- `0x180075c90`
- `0x180075d50`
- `0x180078010`

## import_xrefs

- `KERNEL32!GetSystemDefaultLCID` at `0x180046b44`
- `KERNEL32!GetSystemDefaultLCID` at `0x180046b44`
- `USER32!TrackPopupMenu` at `0x180046c2d`
- `USER32!TrackPopupMenu` at `0x180046c2d`
- `USER32!GetActiveWindow` at `0x1800469fa`
- `USER32!GetActiveWindow` at `0x1800469fa`
- `USER32!CreatePopupMenu` at `0x180046b83`
- `USER32!CreatePopupMenu` at `0x180046b83`
- `USER32!GetWindowLongA` at `0x180046a3b`
- `USER32!GetWindowLongA` at `0x180046a3b`
- `USER32!GetWindowRect` at `0x180046a5b`
- `USER32!GetWindowRect` at `0x180046a5b`
- `USER32!IsWindow` at `0x180046e8b`
- `USER32!IsWindow` at `0x180046e8b`
- `USER32!DestroyMenu` at `0x180046c39`
- `USER32!DestroyMenu` at `0x180046c39`
- `USER32!GetCursorPos` at `0x180046a1a`
- `USER32!GetCursorPos` at `0x180046a1a`
- `USER32!GetFocus` at `0x180046a25`
- `USER32!GetFocus` at `0x180046a25`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall OnWordWheelLookup(
        struct CTable *a1,
        CExTitle **a2,
        const char *a3,
        struct tagPOINT *p_Point,
        HWND a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        int a11,
        const char *a12)
{
  HWND hWnd; // r15
  CTitleInformation *Info; // rax
  unsigned int CodePage; // ebx
  __int64 v18; // rdx
  HWND Focus; // rax
  HWND v20; // rbx
  int WordWheelHits; // ebx
  int v22; // eax
  CResourceCache *v23; // rcx
  int v24; // r8d
  HMENU PopupMenu; // r14
  int i; // esi
  unsigned int v27; // edx
  LPARAM *v28; // r9
  __int64 v29; // rax
  _BOOL8 v30; // rsi
  HFONT ContentFont; // rsi
  CTitleInformation *v32; // rax
  __int64 v33; // rdx
  unsigned __int64 v34; // rbx
  __int64 v35; // rdx
  unsigned __int64 v36; // rax
  int v37; // ecx
  struct CHHWinType *WindowType; // rax
  struct CHHWinType *v39; // rdi
  struct CTable *v41; // [rsp+40h] [rbp-C0h] BYREF
  struct tagPOINT Point; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v43[3]; // [rsp+50h] [rbp-B0h] BYREF
  int v44; // [rsp+68h] [rbp-98h]
  int v45; // [rsp+6Ch] [rbp-94h]
  int v46; // [rsp+70h] [rbp-90h]
  _QWORD v47[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v48; // [rsp+D0h] [rbp-30h]
  LCID SystemDefaultLCID; // [rsp+FCh] [rbp-4h]
  __int64 v50; // [rsp+100h] [rbp+0h]
  _QWORD v51[16]; // [rsp+140h] [rbp+40h] BYREF
  struct tagRECT Rect; // [rsp+1C0h] [rbp+C0h] BYREF
  char v53[2096]; // [rsp+1D0h] [rbp+D0h] BYREF
  char v54[2216]; // [rsp+A00h] [rbp+900h] BYREF
  int v55; // [rsp+12A8h] [rbp+11A8h]

  v41 = a1;
  hWnd = a5;
  if ( a2 )
  {
    Info = CExTitle::GetInfo(a2[136]);
    CodePage = CTitleInformation::GetCodePage(Info);
  }
  else
  {
    CodePage = 0;
  }
  CWTable::CWTable((CWTable *)v47, CodePage);
  CWTable::CWTable((CWTable *)v51, CodePage);
  v43[0] = &CTable::`vftable';
  v44 = 20967424;
  v45 = 0x100000;
  CTable::InitializeTable((CTable *)v43);
  if ( a2 )
  {
    if ( !a5 )
      hWnd = GetActiveWindow();
    Point = 0;
    if ( !p_Point )
    {
      GetCursorPos(&Point);
      p_Point = &Point;
      Focus = GetFocus();
      v20 = Focus;
      if ( Focus )
      {
        if ( (GetWindowLongA(Focus, -16) & 0x4000) != 0 )
        {
          Rect = 0;
          if ( GetWindowRect(v20, &Rect) )
          {
            Point.y = Rect.top + (Rect.right - Rect.left) / 2;
            Point.x = Rect.left + 2 * ((Rect.bottom - Rect.top) / 3);
          }
        }
      }
    }
    WordWheelHits = GetWordWheelHits(
                      (struct CExCollection *)a2,
                      v41,
                      (struct CTable *)v43,
                      (struct CWTable *)v47,
                      (struct CWTable *)v51,
                      a7,
                      a8,
                      a9);
  }
  else
  {
    WordWheelHits = -2147220731;
  }
  if ( !a8 )
  {
    if ( WordWheelHits < 0 || (v22 = v46, v23 = (CResourceCache *)(unsigned int)(v46 - 1), (int)v23 < 1) )
    {
      if ( a2 && a3 )
      {
        LOBYTE(v18) = 58;
        if ( StrRChr(a3, v18) )
        {
          StringCchCopyA(v53, 0x824u, a3);
        }
        else
        {
          v41 = 0;
          GetCurrentURL((struct CStr *)&v41, hWnd);
          *(_QWORD *)&Rect.left = 0;
          LOBYTE(v33) = 58;
          v34 = StrRChr(v41, v33);
          LOBYTE(v35) = 47;
          v36 = StrRChr(v41, v35);
          if ( v34 > v36 )
            v36 = v34;
          StringCchCopyNA(v53, 0x824u, (const char *)v41, v36 - (_QWORD)v41 + 2);
          StringCchCatA(v53, 0x824u, a3);
          CWStr::~CWStr((CWStr *)&Rect);
          CWStr::~CWStr((CWStr *)&v41);
        }
        WordWheelHits = 0;
LABEL_68:
        if ( a12 && *a12 )
        {
          CStr::CStr((CStr *)&v41, v53);
          WindowType = FindWindowType(a12, 0, *((const char **)a2[1] + 17));
          v39 = WindowType;
          if ( WindowType && IsWindow(*((HWND *)WindowType + 8)) )
          {
            doHHWindowJump((const char *)v41, *((HWND *)v39 + 8));
          }
          else
          {
            CStr::operator+=(&v41, ">");
            CStr::operator+=(&v41, a12);
            OnDisplayTopic(hWnd, (const char *)v41, 0);
          }
          CWStr::~CWStr((CWStr *)&v41);
          goto LABEL_76;
        }
LABEL_75:
        doHHWindowJump(v53, hWnd);
        goto LABEL_76;
      }
      switch ( WordWheelHits )
      {
        case -2147220736:
          v37 = 1400;
          break;
        case -2147220735:
          v37 = 1401;
          break;
        case -2147220734:
          v37 = 1402;
          break;
        case -2147220733:
          v37 = 1403;
          break;
        case -2147220732:
          v37 = 1404;
          break;
        default:
          v37 = 1900;
          if ( WordWheelHits != -2147220731 )
            v37 = 1053;
          break;
      }
      MsgBox(v37, 0x10030u);
    }
    else
    {
      if ( !a10 && v46 == 2 )
      {
        v24 = 1;
LABEL_20:
        CTable::GetString((CTable *)v43, v53, v24, 0x824u);
        goto LABEL_67;
      }
      if ( a11 )
      {
        SystemDefaultLCID = GetSystemDefaultLCID();
        v50 = 0;
        (*(void (__fastcall **)(_QWORD *, __int64))(v47[0] + 8LL))(v47, 4);
        v22 = v46;
      }
      if ( a6 || v22 - 1 >= 20 )
      {
        if ( a2 )
        {
          ContentFont = CHmData::GetContentFont(a2[1]);
          v32 = CExTitle::GetInfo(a2[136]);
          CTitleInformation::GetCodePage(v32);
        }
        else
        {
          ContentFont = CResourceCache::GetUIFont(v23);
        }
        CTopicList::CTopicList((CTopicList *)v54, hWnd, (struct CWTable *)v47, ContentFont, (struct CWTable *)v51);
        if ( (unsigned int)CDlg::DoModal((LPARAM)v54) )
          CTable::GetString((CTable *)v43, v53, **(_DWORD **)(v48 + 8LL * v55), 0x824u);
        else
          WordWheelHits = -2147220736;
        CDlg::~CDlg((CDlg *)v54);
      }
      else
      {
        PopupMenu = CreatePopupMenu();
        if ( !PopupMenu )
          goto LABEL_67;
        for ( i = 1; i <= v46 - 1; ++i )
        {
          v27 = i;
          v28 = (LPARAM *)(*(_QWORD *)(v48 + 8LL * i) + 4LL);
          if ( *(_QWORD *)(v48 + 8LL * i) != -4 )
          {
            if ( *(_BYTE *)v28 )
            {
              v29 = -1;
              do
                ++v29;
              while ( *((_BYTE *)v28 + v29) );
              if ( (int)v29 >= 511 )
              {
                StringCchCopyA(v54, 0x200u, (const char *)v28);
                v28 = (LPARAM *)v54;
              }
            }
          }
          HxAppendMenu(PopupMenu, v27, i + 57344, (const char *)v28);
        }
        v30 = TrackPopupMenu(PopupMenu, 0x182u, p_Point->x, p_Point->y, 0, hWnd, 0);
        DestroyMenu(PopupMenu);
        if ( v30 )
        {
          v24 = **(_DWORD **)(v48 + 8 * v30 - 458752);
          goto LABEL_20;
        }
        WordWheelHits = -2147220736;
      }
    }
    if ( WordWheelHits < 0 )
      goto LABEL_76;
LABEL_67:
    if ( !a2 )
      goto LABEL_75;
    goto LABEL_68;
  }
LABEL_76:
  v43[0] = &CTable::`vftable';
  CTable::Cleanup((CTable *)v43);
  v51[0] = &CTable::`vftable';
  CTable::Cleanup((CTable *)v51);
  v47[0] = &CTable::`vftable';
  CTable::Cleanup((CTable *)v47);
  return (unsigned int)WordWheelHits;
}

```

## disassembly

```asm
0x180046938  push    rbp
0x18004693a  push    rbx
0x18004693b  push    rsi
0x18004693c  push    rdi
0x18004693d  push    r12
0x18004693f  push    r13
0x180046941  push    r14
0x180046943  push    r15
0x180046945  lea     rbp, [rsp-11D8h]
0x18004694d  mov     eax, 12D8h
0x180046952  call    _alloca_probe
0x180046957  sub     rsp, rax
0x18004695a  mov     rax, cs:__security_cookie
0x180046961  xor     rax, rsp
0x180046964  mov     [rbp+1210h+var_50], rax
0x18004696b  mov     r12, r9
0x18004696e  mov     rsi, r8
0x180046971  mov     rdi, rdx
0x180046974  mov     [rsp+1310h+var_12D0], rcx
0x180046979  mov     r15, [rbp+1210h+arg_20]
0x180046980  mov     r13, [rbp+1210h+arg_58]
0x180046987  test    rdx, rdx
0x18004698a  jz      short loc_1800469A4
0x18004698c  mov     rcx, [rdx+440h]; this
0x180046993  call    ?GetInfo@CExTitle@@QEAAPEAVCTitleInformation@@XZ; CExTitle::GetInfo(void)
0x180046998  mov     rcx, rax; this
0x18004699b  call    ?GetCodePage@CTitleInformation@@QEAAIXZ; CTitleInformation::GetCodePage(void)
0x1800469a0  mov     ebx, eax
0x1800469a2  jmp     short loc_1800469A6
0x1800469a4  xor     ebx, ebx
0x1800469a6  mov     edx, ebx; unsigned int
0x1800469a8  lea     rcx, [rbp+1210h+var_1250]; this
0x1800469ac  call    ??0CWTable@@QEAA@I@Z; CWTable::CWTable(uint)
0x1800469b1  nop
0x1800469b2  mov     edx, ebx; unsigned int
0x1800469b4  lea     rcx, [rbp+1210h+var_11D0]; this
0x1800469b8  call    ??0CWTable@@QEAA@I@Z; CWTable::CWTable(uint)
0x1800469bd  nop
0x1800469be  lea     rax, ??_7CTable@@6B@; const CTable::`vftable'
0x1800469c5  mov     [rsp+1310h+var_12C0], rax
0x1800469ca  mov     [rsp+1310h+var_12A8], 13FF000h
0x1800469d2  mov     [rsp+1310h+var_12A4], 100000h
0x1800469da  lea     rcx, [rsp+1310h+var_12C0]; this
0x1800469df  call    ?InitializeTable@CTable@@IEAAXXZ; CTable::InitializeTable(void)
0x1800469e4  nop
0x1800469e5  mov     r14d, [rbp+1210h+arg_38]
0x1800469ec  test    rdi, rdi
0x1800469ef  jz      loc_180046AE5
0x1800469f5  test    r15, r15
0x1800469f8  jnz     short loc_180046A03
0x1800469fa  call    cs:__imp_GetActiveWindow
0x180046a00  mov     r15, rax
0x180046a03  mov     qword ptr [rsp+1310h+Point.x], 0
0x180046a0c  test    r12, r12
0x180046a0f  jnz     loc_180046AA9
0x180046a15  lea     rcx, [rsp+1310h+Point]; lpPoint
0x180046a1a  call    cs:__imp_GetCursorPos
0x180046a20  lea     r12, [rsp+1310h+Point]
0x180046a25  call    cs:__imp_GetFocus
0x180046a2b  mov     rbx, rax
0x180046a2e  test    rax, rax
0x180046a31  jz      short loc_180046AA9
0x180046a33  mov     edx, 0FFFFFFF0h; nIndex
0x180046a38  mov     rcx, rax; hWnd
0x180046a3b  call    cs:__imp_GetWindowLongA
0x180046a41  bt      eax, 0Eh
0x180046a45  jnb     short loc_180046AA9
0x180046a47  xorps   xmm0, xmm0
0x180046a4a  movups  xmmword ptr [rbp+1210h+Rect.left], xmm0
0x180046a51  lea     rdx, [rbp+1210h+Rect]; lpRect
0x180046a58  mov     rcx, rbx; hWnd
0x180046a5b  call    cs:__imp_GetWindowRect
0x180046a61  test    eax, eax
0x180046a63  jz      short loc_180046AA9
0x180046a65  mov     r8d, [rbp+1210h+Rect.left]
0x180046a6c  mov     eax, [rbp+1210h+Rect.right]
0x180046a72  sub     eax, r8d
0x180046a75  cdq
0x180046a76  mov     ecx, 2
0x180046a7b  idiv    ecx
0x180046a7d  add     eax, [rbp+1210h+Rect.top]
0x180046a83  mov     [rsp+1310h+Point.y], eax
0x180046a87  mov     ecx, [rbp+1210h+Rect.bottom]
0x180046a8d  sub     ecx, [rbp+1210h+Rect.top]
0x180046a93  mov     eax, 55555556h
0x180046a98  imul    ecx
0x180046a9a  mov     eax, edx
0x180046a9c  shr     eax, 1Fh
0x180046a9f  add     edx, eax
0x180046aa1  lea     eax, [r8+rdx*2]
0x180046aa5  mov     [rsp+1310h+Point.x], eax
0x180046aa9  mov     eax, [rbp+1210h+arg_40]
0x180046aaf  mov     [rsp+1310h+var_12D8], eax; int
0x180046ab3  mov     dword ptr [rsp+1310h+prcRect], r14d; int
0x180046ab8  mov     eax, [rbp+1210h+arg_30]
0x180046abe  mov     dword ptr [rsp+1310h+hWnd], eax; int
0x180046ac2  lea     rax, [rbp+1210h+var_11D0]
0x180046ac6  mov     qword ptr [rsp+1310h+nReserved], rax; struct CWTable *
0x180046acb  lea     r9, [rbp+1210h+var_1250]; struct CWTable *
0x180046acf  lea     r8, [rsp+1310h+var_12C0]; struct CTable *
0x180046ad4  mov     rdx, [rsp+1310h+var_12D0]; struct CTable *
0x180046ad9  mov     rcx, rdi; this
0x180046adc  call    ?GetWordWheelHits@@YAJPEAVCExCollection@@PEAVCTable@@1PEAVCWTable@@2HHH@Z; GetWordWheelHits(CExCollection *,CTable *,CTable *,CWTable *,CWTable *,int,int,int)
0x180046ae1  mov     ebx, eax
0x180046ae3  jmp     short loc_180046AEA
0x180046ae5  mov     ebx, 80040305h
0x180046aea  test    r14d, r14d
0x180046aed  jnz     loc_180046EF0
0x180046af3  xor     r14d, r14d
0x180046af6  test    ebx, ebx
0x180046af8  js      loc_180046D04
0x180046afe  mov     eax, [rsp+1310h+var_12A0]
0x180046b02  lea     ecx, [rax-1]
0x180046b05  cmp     ecx, 1
0x180046b08  jl      loc_180046D04
0x180046b0e  cmp     [rbp+1210h+arg_48], r14d
0x180046b15  jnz     short loc_180046B3B
0x180046b17  cmp     ecx, 1
0x180046b1a  jnz     short loc_180046B3B
0x180046b1c  mov     r8d, ecx; int
0x180046b1f  mov     r9d, 824h; unsigned __int64
0x180046b25  lea     rdx, [rbp+1210h+var_1140]; char *
0x180046b2c  lea     rcx, [rsp+1310h+var_12C0]; this
0x180046b31  call    ?GetString@CTable@@QEBAHPEADH_K@Z; CTable::GetString(char *,int,unsigned __int64)
0x180046b36  jmp     loc_180046E3C
0x180046b3b  cmp     [rbp+1210h+arg_50], r14d
0x180046b42  jz      short loc_180046B6B
0x180046b44  call    cs:__imp_GetSystemDefaultLCID
0x180046b4a  mov     [rbp+1210h+var_1214], eax
0x180046b4d  mov     [rbp+1210h+var_1210], r14
0x180046b51  mov     rax, [rbp+1210h+var_1250]
0x180046b55  mov     edx, 4
0x180046b5a  lea     rcx, [rbp+1210h+var_1250]
0x180046b5e  mov     rax, [rax+8]
0x180046b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046b67  mov     eax, [rsp+1310h+var_12A0]
0x180046b6b  cmp     [rbp+1210h+arg_28], r14d
0x180046b72  jnz     loc_180046C64
0x180046b78  dec     eax
0x180046b7a  cmp     eax, 14h
0x180046b7d  jge     loc_180046C64
0x180046b83  call    cs:__imp_CreatePopupMenu
0x180046b89  mov     r14, rax
0x180046b8c  test    rax, rax
0x180046b8f  jz      loc_180046E39
0x180046b95  mov     esi, 1
0x180046b9a  mov     ecx, [rsp+1310h+var_12A0]
0x180046b9e  dec     ecx
0x180046ba0  cmp     ecx, esi
0x180046ba2  jl      short loc_180046C06
0x180046ba4  movsxd  rdx, esi
0x180046ba7  mov     rcx, [rbp+1210h+var_1240]
0x180046bab  mov     r9, [rcx+rdx*8]
0x180046baf  add     r9, 4
0x180046bb3  jz      short loc_180046BEB
0x180046bb5  cmp     byte ptr [r9], 0
0x180046bb9  jz      short loc_180046BEB
0x180046bbb  or      rax, 0FFFFFFFFFFFFFFFFh
0x180046bbf  inc     rax
0x180046bc2  cmp     byte ptr [r9+rax], 0
0x180046bc7  jnz     short loc_180046BBF
0x180046bc9  cmp     eax, 1FFh
0x180046bce  jl      short loc_180046BEB
0x180046bd0  mov     r8, r9; char *
0x180046bd3  mov     edx, 200h; unsigned __int64
0x180046bd8  lea     rcx, [rbp+1210h+var_910]; char *
0x180046bdf  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180046be4  lea     r9, [rbp+1210h+var_910]; char *
0x180046beb  lea     r8d, [rsi+0E000h]; unsigned int
0x180046bf2  mov     rcx, r14; hMenu
0x180046bf5  call    ?HxAppendMenu@@YAHPEAUHMENU__@@IIPEBD@Z; HxAppendMenu(HMENU__ *,uint,uint,char const *)
0x180046bfa  inc     esi
0x180046bfc  mov     eax, [rsp+1310h+var_12A0]
0x180046c00  dec     eax
0x180046c02  cmp     esi, eax
0x180046c04  jle     short loc_180046BA4
0x180046c06  mov     [rsp+1310h+prcRect], 0; prcRect
0x180046c0f  mov     [rsp+1310h+hWnd], r15; hWnd
0x180046c14  mov     [rsp+1310h+nReserved], 0; nReserved
0x180046c1c  mov     r9d, [r12+4]; y
0x180046c21  mov     r8d, [r12]; x
0x180046c25  mov     edx, 182h; uFlags
0x180046c2a  mov     rcx, r14; hMenu
0x180046c2d  call    cs:__imp_TrackPopupMenu
0x180046c33  movsxd  rsi, eax
0x180046c36  mov     rcx, r14; hMenu
0x180046c39  call    cs:__imp_DestroyMenu
0x180046c3f  xor     r14d, r14d
0x180046c42  test    esi, esi
0x180046c44  jz      short loc_180046C5A
0x180046c46  mov     rax, [rbp+1210h+var_1240]
0x180046c4a  mov     r8, [rax+rsi*8-70000h]
0x180046c52  mov     r8d, [r8]
0x180046c55  jmp     loc_180046B1F
0x180046c5a  mov     ebx, 80040300h
0x180046c5f  jmp     loc_180046E2F
0x180046c64  test    rdi, rdi
0x180046c67  jz      short loc_180046C8B
0x180046c69  mov     rcx, [rdi+8]; this
0x180046c6d  call    ?GetContentFont@CHmData@@QEAAPEAUHFONT__@@XZ; CHmData::GetContentFont(void)
0x180046c72  mov     rsi, rax
0x180046c75  mov     rcx, [rdi+440h]; this
0x180046c7c  call    ?GetInfo@CExTitle@@QEAAPEAVCTitleInformation@@XZ; CExTitle::GetInfo(void)
0x180046c81  mov     rcx, rax; this
0x180046c84  call    ?GetCodePage@CTitleInformation@@QEAAIXZ; CTitleInformation::GetCodePage(void)
0x180046c89  jmp     short loc_180046C93
0x180046c8b  call    ?GetUIFont@CResourceCache@@QEAAPEAUHFONT__@@XZ; CResourceCache::GetUIFont(void)
0x180046c90  mov     rsi, rax
0x180046c93  lea     rax, [rbp+1210h+var_11D0]
0x180046c97  mov     qword ptr [rsp+1310h+nReserved], rax; struct CWTable *
0x180046c9c  mov     r9, rsi; HFONT
0x180046c9f  lea     r8, [rbp+1210h+var_1250]; struct CWTable *
0x180046ca3  mov     rdx, r15; HWND
0x180046ca6  lea     rcx, [rbp+1210h+var_910]; this
0x180046cad  call    ??0CTopicList@@QEAA@PEAUHWND__@@PEAVCWTable@@PEAUHFONT__@@1@Z; CTopicList::CTopicList(HWND__ *,CWTable *,HFONT__ *,CWTable *)
0x180046cb2  nop
0x180046cb3  lea     rcx, [rbp+1210h+var_910]; this
0x180046cba  call    ?DoModal@CDlg@@QEAAHXZ; CDlg::DoModal(void)
0x180046cbf  test    eax, eax
0x180046cc1  jz      short loc_180046CEE
0x180046cc3  movsxd  rcx, [rbp+1210h+var_68]
0x180046cca  mov     rax, [rbp+1210h+var_1240]
0x180046cce  mov     r8, [rax+rcx*8]
0x180046cd2  mov     r9d, 824h; unsigned __int64
0x180046cd8  mov     r8d, [r8]; int
0x180046cdb  lea     rdx, [rbp+1210h+var_1140]; char *
0x180046ce2  lea     rcx, [rsp+1310h+var_12C0]; this
0x180046ce7  call    ?GetString@CTable@@QEBAHPEADH_K@Z; CTable::GetString(char *,int,unsigned __int64)
0x180046cec  jmp     short loc_180046CF3
0x180046cee  mov     ebx, 80040300h
0x180046cf3  lea     rcx, [rbp+1210h+var_910]; this
0x180046cfa  call    ??1CDlg@@QEAA@XZ; CDlg::~CDlg(void)
0x180046cff  jmp     loc_180046E2F
0x180046d04  test    rdi, rdi
0x180046d07  jz      loc_180046DC7
0x180046d0d  test    rsi, rsi
0x180046d10  jz      loc_180046DC7
0x180046d16  mov     dl, 3Ah ; ':'
0x180046d18  mov     rcx, rsi
0x180046d1b  call    StrRChr
0x180046d20  test    rax, rax
0x180046d23  jnz     loc_180046DAE
0x180046d29  mov     [rsp+1310h+var_12D0], r14
0x180046d2e  mov     rdx, r15; hWnd
0x180046d31  lea     rcx, [rsp+1310h+var_12D0]; struct CStr *
0x180046d36  call    ?GetCurrentURL@@YAHPEAVCStr@@PEAUHWND__@@@Z; GetCurrentURL(CStr *,HWND__ *)
0x180046d3b  mov     qword ptr [rbp+1210h+Rect.left], r14
0x180046d42  mov     dl, 3Ah ; ':'
0x180046d44  mov     rcx, [rsp+1310h+var_12D0]
0x180046d49  call    StrRChr
0x180046d4e  mov     rbx, rax
0x180046d51  mov     dl, 2Fh ; '/'
0x180046d53  mov     rcx, [rsp+1310h+var_12D0]
0x180046d58  call    StrRChr
0x180046d5d  cmp     rbx, rax
0x180046d60  cmova   rax, rbx
0x180046d64  mov     r8, [rsp+1310h+var_12D0]; char *
0x180046d69  sub     rax, r8
0x180046d6c  lea     r9, [rax+2]; unsigned __int64
0x180046d70  mov     edx, 824h; unsigned __int64
0x180046d75  lea     rcx, [rbp+1210h+var_1140]; char *
0x180046d7c  call    ?StringCchCopyNA@@YAJPEAD_KPEBD1@Z; StringCchCopyNA(char *,unsigned __int64,char const *,unsigned __int64)
0x180046d81  mov     r8, rsi; char *
0x180046d84  mov     edx, 824h; unsigned __int64
0x180046d89  lea     rcx, [rbp+1210h+var_1140]; char *
0x180046d90  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x180046d95  lea     rcx, [rbp+1210h+Rect]; this
0x180046d9c  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180046da1  nop
0x180046da2  lea     rcx, [rsp+1310h+var_12D0]; this
0x180046da7  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180046dac  jmp     short loc_180046DC2
0x180046dae  mov     r8, rsi; char *
0x180046db1  mov     edx, 824h; unsigned __int64
0x180046db6  lea     rcx, [rbp+1210h+var_1140]; char *
0x180046dbd  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180046dc2  mov     ebx, r14d
0x180046dc5  jmp     short loc_180046E45
0x180046dc7  cmp     ebx, 80040300h
0x180046dcd  jz      short loc_180046E20
0x180046dcf  cmp     ebx, 80040301h
0x180046dd5  jz      short loc_180046E19
0x180046dd7  cmp     ebx, 80040302h
0x180046ddd  jz      short loc_180046E12
0x180046ddf  cmp     ebx, 80040303h
0x180046de5  jz      short loc_180046E0B
0x180046de7  cmp     ebx, 80040304h
0x180046ded  jz      short loc_180046E04
0x180046def  mov     ecx, 76Ch
0x180046df4  mov     eax, 41Dh
0x180046df9  cmp     ebx, 80040305h
0x180046dff  cmovnz  ecx, eax
0x180046e02  jmp     short loc_180046E25
0x180046e04  mov     ecx, 57Ch
0x180046e09  jmp     short loc_180046E25
0x180046e0b  mov     ecx, 57Bh
0x180046e10  jmp     short loc_180046E25
0x180046e12  mov     ecx, 57Ah
0x180046e17  jmp     short loc_180046E25
0x180046e19  mov     ecx, 579h
  ... truncated ...
```
