# CPopupWindow::CreatePopupWindow(HWND__ *,char const *,tagHH_POPUP *)

- ea: `0x180047ffc`
- end: `0x180048425`
- name: `?CreatePopupWindow@CPopupWindow@@QEAAPEAUHWND__@@PEAU2@PEBDPEAUtagHH_POPUP@@@Z`
- size: `1065`
- prototype: `HWND(CPopupWindow *__hidden this, HWND, const char *, struct tagHH_POPUP *)`
- caller_count: `1`
- callee_count: `22`
- tags: `loader_planting`

## callers

- `0x180048b54`

## callees

- `0x180003fc0`
- `0x1800095c8`
- `0x18000f460`
- `0x1800115b0`
- `0x18002018c`
- `0x18002e344`
- `0x18002e3e0`
- `0x180042da8`
- `0x180047db8`
- `0x180047f54`
- `0x180047ffc`
- `0x180048910`
- `0x180048ab0`
- `0x180048be4`
- `0x180065438`
- `0x1800661d0`
- `0x1800675c0`
- `0x180067688`
- `0x180069430`
- `0x18006c384`
- `0x180075c90`
- `0x180078010`

## import_xrefs

- `msvcrt!malloc` at `0x180048122`
- `msvcrt!malloc` at `0x1800482af`
- `msvcrt!malloc` at `0x180048122`
- `msvcrt!malloc` at `0x1800482af`
- `msvcrt!free` at `0x1800482a4`
- `msvcrt!free` at `0x1800482a4`
- `USER32!GetWindowRect` at `0x1800483a5`
- `USER32!GetWindowRect` at `0x1800483a5`
- `USER32!IsWindow` at `0x18004838b`
- `USER32!IsWindow` at `0x18004838b`
- `GDI32!DeleteObject` at `0x18004833b`
- `GDI32!DeleteObject` at `0x18004833b`

## pseudocode

```c
HWND __fastcall CPopupWindow::CreatePopupWindow(CPopupWindow *this, HWND a2, const char *a3, struct tagHH_POPUP *a4)
{
  CPopupWindow *v7; // rdi
  const char *pszText; // rcx
  char *v9; // rax
  int v10; // edx
  char v11; // bl
  __int64 v12; // rdx
  int i; // ebx
  const char *v14; // r15
  const char *NonSpace; // rax
  void *v16; // rax
  const char *StringResource; // rax
  __int64 v18; // rcx
  int v19; // ebx
  int v20; // edx
  __int64 v21; // r9
  __int64 v22; // r8
  _BYTE *v23; // r14
  UINT idString; // ebx
  const char *v25; // rax
  void *v26; // rcx
  void *v27; // rax
  const char *v28; // rax
  LONG bottom; // ecx
  LONG left; // eax
  LONG top; // eax
  LONG right; // eax
  LPCTSTR pszFont; // rax
  void *v34; // rcx
  const char *v35; // rcx
  struct tagPOINT v36; // rbx
  POINT pt; // [rsp+30h] [rbp-D0h] BYREF
  struct tagRECT Rect; // [rsp+38h] [rbp-C8h] BYREF
  char v40[256]; // [rsp+50h] [rbp-B0h] BYREF

  if ( !a4 )
    return 0;
  v7 = g_pPopupWindow;
  *((_QWORD *)g_pPopupWindow + 4) = a2;
  if ( a4->idString )
  {
    v11 = 0;
    if ( a4->hinst )
    {
      v16 = malloc(0x101u);
      *((_QWORD *)v7 + 7) = v16;
      if ( !v16 )
        return 0;
      StringResource = GetStringResource(a4->idString, a4->hinst);
      if ( StringResource && *StringResource )
      {
        StringCchCopyA(*((char **)v7 + 7), 0x100u, StringResource);
        v11 = 1;
      }
      goto LABEL_39;
    }
  }
  else
  {
    pszText = a4->pszText;
    if ( pszText && *pszText )
    {
      v9 = lcStrDup(pszText);
      *((_QWORD *)v7 + 7) = v9;
      if ( v9 )
      {
LABEL_6:
        v10 = 0;
        goto LABEL_45;
      }
      return 0;
    }
    v11 = 0;
  }
  if ( a3 && *a3 )
  {
    if ( CPopupWindow::ReadTextFile(v7, a3) )
    {
      v12 = *((_QWORD *)v7 + 11);
      for ( i = 1; i <= *(_DWORD *)(v12 + 32) - 1; ++i )
      {
        v14 = *(const char **)(*(_QWORD *)(v12 + 16) + 8LL * i);
        if ( (unsigned int)IsSamePrefix(v14, ".topic", -1) )
        {
          NonSpace = (const char *)FirstNonSpace(v14 + 6);
          if ( NonSpace )
          {
            if ( a4->idString == (unsigned int)Atoi(NonSpace) )
              break;
          }
        }
        v12 = *((_QWORD *)v7 + 11);
      }
      if ( i <= *(_DWORD *)(*((_QWORD *)v7 + 11) + 32LL) - 1 )
      {
        CStr::CStr((CStr *)&pt, txtZeroLength);
        v18 = *((_QWORD *)v7 + 11);
        v19 = i + 1;
        if ( v19 <= *(_DWORD *)(v18 + 32) - 1 )
        {
          v20 = 0;
          do
          {
            v21 = *(_QWORD *)(v18 + 16);
            v22 = v19;
            v23 = *(_BYTE **)(v21 + 8LL * v19);
            if ( *v23 == 46 )
              break;
            if ( *v23 )
            {
              if ( v20 )
                CStr::operator+=(&pt, " ");
              CStr::operator+=(&pt, v23);
              v20 = 1;
              ++v19;
            }
            else
            {
              if ( ++v19 <= *(_DWORD *)(v18 + 32) - 1 && **(_BYTE **)(v21 + 8 * v22 + 8) != 46 )
                CStr::operator+=(&pt, "\r\n");
              v20 = 0;
            }
            v18 = *((_QWORD *)v7 + 11);
          }
          while ( v19 <= *(_DWORD *)(v18 + 32) - 1 );
        }
        *((POINT *)v7 + 7) = pt;
        pt = 0;
        CWStr::~CWStr((CWStr *)&pt);
        goto LABEL_6;
      }
      if ( (unsigned int)IsHelpAuthor(0) )
      {
        idString = a4->idString;
        v25 = (const char *)((__int64 (__fastcall *)(__int64))pGetDllStringResource)(120581);
        StringCchPrintfA(v40, 0x100u, v25, idString, a3);
        doAuthorMsg(0x1D72Cu, v40);
      }
      goto LABEL_40;
    }
    doAuthorMsg(0x1D805u, a3);
LABEL_39:
    v10 = 0;
    if ( v11 )
      goto LABEL_45;
  }
LABEL_40:
  v26 = (void *)*((_QWORD *)v7 + 7);
  if ( v26 )
    free(v26);
  v27 = malloc(0x101u);
  *((_QWORD *)v7 + 7) = v27;
  if ( !v27 )
    return 0;
  v28 = GetStringResource(0x41Du);
  if ( !v28 )
  {
    CPopupWindow::CleanUp(v7);
    return 0;
  }
  StringCchCopyA(*((char **)v7 + 7), 0x100u, v28);
  v10 = 1;
LABEL_45:
  bottom = 5;
  left = 5;
  if ( a4->rcMargins.left >= 0 )
    left = a4->rcMargins.left;
  *((_DWORD *)v7 + 18) = left;
  top = 5;
  if ( a4->rcMargins.top >= 0 )
    top = a4->rcMargins.top;
  *((_DWORD *)v7 + 19) = top;
  right = 5;
  if ( a4->rcMargins.right >= 0 )
    right = a4->rcMargins.right;
  *((_DWORD *)v7 + 20) = right;
  if ( a4->rcMargins.bottom >= 0 )
    bottom = a4->rcMargins.bottom;
  *((_DWORD *)v7 + 21) = bottom;
  pszFont = a4->pszFont;
  if ( pszFont && *pszFont && !v10 )
  {
    v34 = (void *)*((_QWORD *)v7 + 8);
    if ( v34 )
      DeleteObject(v34);
    v35 = a4->pszFont;
    goto LABEL_61;
  }
  if ( !*((_QWORD *)v7 + 8) )
  {
    v35 = GetStringResource(0x403u);
LABEL_61:
    *((_QWORD *)v7 + 8) = CreateUserFont(v35, 0, 0, -1);
  }
  pt = a4->pt;
  v36 = pt;
  if ( pt == -1 )
  {
    if ( IsWindow(a2) )
    {
      Rect = 0;
      GetWindowRect(a2, &Rect);
      pt.x = Rect.left + (Rect.right - Rect.left) / 2;
      pt.y = Rect.top;
      v36 = pt;
    }
  }
  CPopupWindow::CalculateRect(v7, v36);
  CPopupWindow::SetColors(v7, a4->clrForeground, a4->clrBackground);
  return CPopupWindow::doPopupWindow(v7);
}

```

## disassembly

```asm
0x180047ffc  mov     [rsp-8+arg_0], rbx
0x180048001  push    rbp
0x180048002  push    rsi
0x180048003  push    rdi
0x180048004  push    r12
0x180048006  push    r13
0x180048008  push    r14
0x18004800a  push    r15
0x18004800c  lea     rbp, [rsp-60h]
0x180048011  sub     rsp, 160h
0x180048018  mov     rax, cs:__security_cookie
0x18004801f  xor     rax, rsp
0x180048022  mov     [rbp+90h+var_40], rax
0x180048026  xor     r13d, r13d
0x180048029  mov     rsi, r9
0x18004802c  mov     r14, r8
0x18004802f  mov     r12, rdx
0x180048032  test    r9, r9
0x180048035  jz      loc_1800483FC
0x18004803b  mov     rdi, cs:?g_pPopupWindow@@3PEAVCPopupWindow@@EA; CPopupWindow * g_pPopupWindow
0x180048042  lea     r15d, [r13+1]
0x180048046  mov     [rdi+20h], rdx
0x18004804a  cmp     [r9+10h], r13d
0x18004804e  jnz     loc_180048110
0x180048054  mov     rcx, [r9+18h]; char *
0x180048058  test    rcx, rcx
0x18004805b  jz      short loc_18004807C
0x18004805d  cmp     [rcx], r13b
0x180048060  jz      short loc_18004807C
0x180048062  call    ?lcStrDup@@YAPEADPEBD@Z; lcStrDup(char const *)
0x180048067  mov     [rdi+38h], rax
0x18004806b  test    rax, rax
0x18004806e  jz      loc_1800483FC
0x180048074  mov     edx, r13d
0x180048077  jmp     loc_1800482E9
0x18004807c  mov     bl, r13b
0x18004807f  test    r14, r14
0x180048082  jz      loc_18004829B
0x180048088  cmp     [r8], r13b
0x18004808b  jz      loc_18004829B
0x180048091  mov     rdx, r14; char *
0x180048094  mov     rcx, rdi; this
0x180048097  call    ?ReadTextFile@CPopupWindow@@QEAAHPEBD@Z; CPopupWindow::ReadTextFile(char const *)
0x18004809c  test    eax, eax
0x18004809e  jz      loc_180048287
0x1800480a4  mov     rdx, [rdi+58h]
0x1800480a8  mov     ebx, r15d
0x1800480ab  mov     eax, [rdx+20h]
0x1800480ae  sub     eax, r15d
0x1800480b1  cmp     eax, r15d
0x1800480b4  jl      loc_180048172
0x1800480ba  mov     rax, [rdx+10h]
0x1800480be  or      r8d, 0FFFFFFFFh; int
0x1800480c2  movsxd  rcx, ebx
0x1800480c5  lea     rdx, aTopic_0; ".topic"
0x1800480cc  mov     r15, [rax+rcx*8]
0x1800480d0  mov     rcx, r15; char *
0x1800480d3  call    ?IsSamePrefix@@YAHPEBD0H@Z; IsSamePrefix(char const *,char const *,int)
0x1800480d8  test    eax, eax
0x1800480da  jz      short loc_1800480F7
0x1800480dc  lea     rcx, [r15+6]
0x1800480e0  call    FirstNonSpace
0x1800480e5  test    rax, rax
0x1800480e8  jz      short loc_1800480F7
0x1800480ea  mov     rcx, rax; char *
0x1800480ed  call    ?Atoi@@YAHPEBD@Z; Atoi(char const *)
0x1800480f2  cmp     [rsi+10h], eax
0x1800480f5  jz      short loc_18004816C
0x1800480f7  mov     rdx, [rdi+58h]
0x1800480fb  mov     r15d, 1
0x180048101  add     ebx, r15d
0x180048104  mov     eax, [rdx+20h]
0x180048107  sub     eax, r15d
0x18004810a  cmp     ebx, eax
0x18004810c  jle     short loc_1800480BA
0x18004810e  jmp     short loc_180048172
0x180048110  mov     bl, r13b
0x180048113  cmp     [r9+8], r13
0x180048117  jz      loc_18004807F
0x18004811d  mov     ecx, 101h; Size
0x180048122  call    cs:__imp_malloc
0x180048128  mov     [rdi+38h], rax
0x18004812c  test    rax, rax
0x18004812f  jz      loc_1800483FC
0x180048135  mov     rdx, [rsi+8]; HINSTANCE
0x180048139  mov     ecx, [rsi+10h]; int
0x18004813c  call    ?GetStringResource@@YAPEBDHPEAUHINSTANCE__@@@Z; GetStringResource(int,HINSTANCE__ *)
0x180048141  test    rax, rax
0x180048144  jz      loc_180048294
0x18004814a  cmp     [rax], r13b
0x18004814d  jz      loc_180048294
0x180048153  mov     rcx, [rdi+38h]; char *
0x180048157  mov     r8, rax; char *
0x18004815a  mov     edx, 100h; unsigned __int64
0x18004815f  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180048164  mov     bl, r15b
0x180048167  jmp     loc_180048294
0x18004816c  mov     r15d, 1
0x180048172  mov     rax, [rdi+58h]
0x180048176  mov     ecx, [rax+20h]
0x180048179  sub     ecx, r15d
0x18004817c  cmp     ebx, ecx
0x18004817e  jg      loc_18004823D
0x180048184  lea     rdx, ?txtZeroLength@@3QBDB; char *
0x18004818b  lea     rcx, [rsp+190h+var_160]; this
0x180048190  call    ??0CStr@@QEAA@PEBD@Z; CStr::CStr(char const *)
0x180048195  mov     rcx, [rdi+58h]
0x180048199  add     ebx, r15d
0x18004819c  mov     eax, [rcx+20h]
0x18004819f  sub     eax, r15d
0x1800481a2  cmp     ebx, eax
0x1800481a4  jg      short loc_180048220
0x1800481a6  mov     edx, r13d
0x1800481a9  mov     r9, [rcx+10h]
0x1800481ad  movsxd  r8, ebx
0x1800481b0  mov     r14, [r9+r8*8]
0x1800481b4  mov     al, [r14]
0x1800481b7  cmp     al, 2Eh ; '.'
0x1800481b9  jz      short loc_180048220
0x1800481bb  test    al, al
0x1800481bd  jnz     short loc_1800481EB
0x1800481bf  mov     eax, [rcx+20h]
0x1800481c2  inc     ebx
0x1800481c4  sub     eax, r15d
0x1800481c7  cmp     ebx, eax
0x1800481c9  jg      short loc_1800481E6
0x1800481cb  mov     rax, [r9+r8*8+8]
0x1800481d0  cmp     byte ptr [rax], 2Eh ; '.'
0x1800481d3  jz      short loc_1800481E6
0x1800481d5  lea     rdx, asc_18007F490; "\r\n"
0x1800481dc  lea     rcx, [rsp+190h+var_160]
0x1800481e1  call    ??YCStr@@QEAAXPEBD@Z; CStr::operator+=(char const *)
0x1800481e6  mov     edx, r13d
0x1800481e9  jmp     short loc_180048212
0x1800481eb  test    edx, edx
0x1800481ed  jz      short loc_180048200
0x1800481ef  lea     rdx, asc_18007F48C; " "
0x1800481f6  lea     rcx, [rsp+190h+var_160]
0x1800481fb  call    ??YCStr@@QEAAXPEBD@Z; CStr::operator+=(char const *)
0x180048200  mov     rdx, r14
0x180048203  lea     rcx, [rsp+190h+var_160]
0x180048208  call    ??YCStr@@QEAAXPEBD@Z; CStr::operator+=(char const *)
0x18004820d  mov     edx, r15d
0x180048210  inc     ebx
0x180048212  mov     rcx, [rdi+58h]
0x180048216  mov     eax, [rcx+20h]
0x180048219  sub     eax, r15d
0x18004821c  cmp     ebx, eax
0x18004821e  jle     short loc_1800481A9
0x180048220  mov     rax, [rsp+190h+var_160]
0x180048225  lea     rcx, [rsp+190h+var_160]; this
0x18004822a  mov     [rdi+38h], rax
0x18004822e  mov     [rsp+190h+var_160], r13
0x180048233  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180048238  jmp     loc_180048074
0x18004823d  xor     ecx, ecx; HWND
0x18004823f  call    ?IsHelpAuthor@@YAHPEAUHWND__@@@Z; IsHelpAuthor(HWND__ *)
0x180048244  test    eax, eax
0x180048246  jz      short loc_18004829B
0x180048248  mov     rax, cs:?pGetDllStringResource@@3P6APEBDH@ZEA; char const * (*pGetDllStringResource)(int)
0x18004824f  mov     ecx, 1D705h
0x180048254  mov     ebx, [rsi+10h]
0x180048257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004825c  mov     r9d, ebx
0x18004825f  mov     [rsp+190h+var_170], r14
0x180048264  mov     r8, rax; char *
0x180048267  lea     rcx, [rsp+190h+var_140]; char *
0x18004826c  mov     edx, 100h; unsigned __int64
0x180048271  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180048276  lea     rdx, [rsp+190h+var_140]; char *
0x18004827b  mov     ecx, 1D72Ch; unsigned int
0x180048280  call    ?doAuthorMsg@@YAXIPEBD@Z; doAuthorMsg(uint,char const *)
0x180048285  jmp     short loc_18004829B
0x180048287  mov     rdx, r14; char *
0x18004828a  mov     ecx, 1D805h; unsigned int
0x18004828f  call    ?doAuthorMsg@@YAXIPEBD@Z; doAuthorMsg(uint,char const *)
0x180048294  mov     edx, r13d
0x180048297  test    bl, bl
0x180048299  jnz     short loc_1800482E9
0x18004829b  mov     rcx, [rdi+38h]; Block
0x18004829f  test    rcx, rcx
0x1800482a2  jz      short loc_1800482AA
0x1800482a4  call    cs:__imp_free
0x1800482aa  mov     ecx, 101h; Size
0x1800482af  call    cs:__imp_malloc
0x1800482b5  mov     [rdi+38h], rax
0x1800482b9  test    rax, rax
0x1800482bc  jz      loc_1800483FC
0x1800482c2  mov     ecx, 41Dh; uID
0x1800482c7  call    ?GetStringResource@@YAPEBDH@Z; GetStringResource(int)
0x1800482cc  test    rax, rax
0x1800482cf  jz      loc_1800483F4
0x1800482d5  mov     rcx, [rdi+38h]; char *
0x1800482d9  mov     r8, rax; char *
0x1800482dc  mov     edx, 100h; unsigned __int64
0x1800482e1  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800482e6  mov     edx, r15d
0x1800482e9  cmp     [rsi+30h], r13d
0x1800482ed  mov     ecx, 5
0x1800482f2  mov     eax, ecx
0x1800482f4  cmovge  eax, [rsi+30h]
0x1800482f8  mov     [rdi+48h], eax
0x1800482fb  mov     eax, ecx
0x1800482fd  cmp     [rsi+34h], r13d
0x180048301  cmovge  eax, [rsi+34h]
0x180048305  mov     [rdi+4Ch], eax
0x180048308  mov     eax, ecx
0x18004830a  cmp     [rsi+38h], r13d
0x18004830e  cmovge  eax, [rsi+38h]
0x180048312  mov     [rdi+50h], eax
0x180048315  cmp     [rsi+3Ch], r13d
0x180048319  cmovge  ecx, [rsi+3Ch]
0x18004831d  mov     [rdi+54h], ecx
0x180048320  mov     rax, [rsi+40h]
0x180048324  test    rax, rax
0x180048327  jz      short loc_180048347
0x180048329  cmp     [rax], r13b
0x18004832c  jz      short loc_180048347
0x18004832e  test    edx, edx
0x180048330  jnz     short loc_180048347
0x180048332  mov     rcx, [rdi+40h]; ho
0x180048336  test    rcx, rcx
0x180048339  jz      short loc_180048341
0x18004833b  call    cs:__imp_DeleteObject
0x180048341  mov     rcx, [rsi+40h]
0x180048345  jmp     short loc_18004835A
0x180048347  cmp     [rdi+40h], r13
0x18004834b  jnz     short loc_18004836C
0x18004834d  mov     ecx, 403h; uID
0x180048352  call    ?GetStringResource@@YAPEBDH@Z; GetStringResource(int)
0x180048357  mov     rcx, rax; char *
0x18004835a  or      r9d, 0FFFFFFFFh; int
0x18004835e  xor     r8d, r8d; HDC
0x180048361  xor     edx, edx; unsigned int *
0x180048363  call    ?CreateUserFont@@YAPEAUHFONT__@@PEBDPEAKPEAUHDC__@@H@Z; CreateUserFont(char const *,ulong *,HDC__ *,int)
0x180048368  mov     [rdi+40h], rax
0x18004836c  mov     rbx, [rsi+20h]
0x180048370  mov     [rsp+190h+var_160], rbx
0x180048375  cmp     dword ptr [rsp+190h+var_160], 0FFFFFFFFh
0x18004837a  jnz     short loc_1800483D0
0x18004837c  mov     rax, rbx
0x18004837f  shr     rax, 20h
0x180048383  cmp     eax, 0FFFFFFFFh
0x180048386  jnz     short loc_1800483D0
0x180048388  mov     rcx, r12; hWnd
0x18004838b  call    cs:__imp_IsWindow
0x180048391  test    eax, eax
0x180048393  jz      short loc_1800483D0
0x180048395  xorps   xmm0, xmm0
0x180048398  lea     rdx, [rsp+190h+Rect]; lpRect
0x18004839d  mov     rcx, r12; hWnd
0x1800483a0  movups  xmmword ptr [rsp+190h+Rect.left], xmm0
0x1800483a5  call    cs:__imp_GetWindowRect
0x1800483ab  mov     eax, [rsp+190h+Rect.right]
0x1800483af  mov     ecx, 2
0x1800483b4  sub     eax, [rsp+190h+Rect.left]
0x1800483b8  cdq
0x1800483b9  idiv    ecx
0x1800483bb  add     eax, [rsp+190h+Rect.left]
0x1800483bf  mov     dword ptr [rsp+190h+var_160], eax
0x1800483c3  mov     eax, [rsp+190h+Rect.top]
0x1800483c7  mov     dword ptr [rsp+190h+var_160+4], eax
0x1800483cb  mov     rbx, [rsp+190h+var_160]
0x1800483d0  mov     rdx, rbx; struct tagPOINT
0x1800483d3  mov     rcx, rdi; this
0x1800483d6  call    ?CalculateRect@CPopupWindow@@IEAAXUtagPOINT@@@Z; CPopupWindow::CalculateRect(tagPOINT)
0x1800483db  mov     r8d, [rsi+2Ch]; unsigned int
0x1800483df  mov     rcx, rdi; this
0x1800483e2  mov     edx, [rsi+28h]; unsigned int
0x1800483e5  call    ?SetColors@CPopupWindow@@IEAAXKK@Z; CPopupWindow::SetColors(ulong,ulong)
0x1800483ea  mov     rcx, rdi; this
0x1800483ed  call    ?doPopupWindow@CPopupWindow@@IEAAPEAUHWND__@@XZ; CPopupWindow::doPopupWindow(void)
0x1800483f2  jmp     short loc_1800483FE
0x1800483f4  mov     rcx, rdi; this
0x1800483f7  call    ?CleanUp@CPopupWindow@@QEAAXXZ; CPopupWindow::CleanUp(void)
0x1800483fc  xor     eax, eax
0x1800483fe  mov     rcx, [rbp+90h+var_40]
0x180048402  xor     rcx, rsp; StackCookie
0x180048405  call    __security_check_cookie
0x18004840a  mov     rbx, [rsp+190h+arg_0]
0x180048412  add     rsp, 160h
0x180048419  pop     r15
0x18004841b  pop     r14
0x18004841d  pop     r13
0x18004841f  pop     r12
0x180048421  pop     rdi
0x180048422  pop     rsi
0x180048423  pop     rbp
0x180048424  retn
```
