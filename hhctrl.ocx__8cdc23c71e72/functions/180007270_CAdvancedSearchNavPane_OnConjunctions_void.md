# CAdvancedSearchNavPane::OnConjunctions(void)

- ea: `0x180007270`
- end: `0x1800075fd`
- name: `?OnConjunctions@CAdvancedSearchNavPane@@IEAAXXZ`
- size: `909`
- prototype: `void __fastcall(CAdvancedSearchNavPane *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path`

## callers

- `0x1800071e0`

## callees

- `0x180001710`
- `0x180001768`
- `0x180001c58`
- `0x180001e50`
- `0x1800029b8`
- `0x180004224`
- `0x180007270`
- `0x1800094d8`
- `0x180064acc`
- `0x1800675c0`
- `0x180075c5a`
- `0x180075c90`

## import_xrefs

- `msvcrt!_strnset` at `0x1800074d0`
- `msvcrt!_strnset` at `0x1800074d0`
- `KERNEL32!IsDBCSLeadByte` at `0x180007463`
- `KERNEL32!IsDBCSLeadByte` at `0x1800074a0`
- `KERNEL32!IsDBCSLeadByte` at `0x180007463`
- `KERNEL32!IsDBCSLeadByte` at `0x1800074a0`
- `USER32!CharNextA` at `0x180007471`
- `USER32!CharNextA` at `0x1800074ae`
- `USER32!CharNextA` at `0x180007471`
- `USER32!CharNextA` at `0x1800074ae`
- `USER32!GetWindowTextA` at `0x180007430`
- `USER32!GetWindowTextA` at `0x180007430`
- `USER32!SetWindowTextA` at `0x1800073f3`
- `USER32!SetWindowTextA` at `0x18000757e`
- `USER32!SetWindowTextA` at `0x1800073f3`
- `USER32!SetWindowTextA` at `0x18000757e`
- `USER32!GetWindowTextLengthA` at `0x1800073dd`
- `USER32!GetWindowTextLengthA` at `0x1800073dd`
- `USER32!TrackPopupMenuEx` at `0x1800073b7`
- `USER32!TrackPopupMenuEx` at `0x1800073b7`
- `USER32!CreatePopupMenu` at `0x1800072a5`
- `USER32!CreatePopupMenu` at `0x1800072a5`
- `USER32!SetFocus` at `0x1800075a1`
- `USER32!SetFocus` at `0x1800075a1`
- `USER32!GetWindowRect` at `0x18000736a`
- `USER32!GetWindowRect` at `0x18000736a`
- `USER32!SendMessageA` at `0x1800075c0`
- `USER32!SendMessageA` at `0x1800075c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CAdvancedSearchNavPane::OnConjunctions(CAdvancedSearchNavPane *this)
{
  CAdvancedSearchNavPane *v1; // rsi
  HMENU PopupMenu; // rdi
  unsigned int v3; // edx
  int v4; // eax
  int v5; // ebx
  BOOL v6; // eax
  _BOOL8 v7; // r13
  int WindowTextLengthA; // eax
  int v9; // ebx
  __int64 v10; // rbx
  CHAR *v11; // rax
  char *v12; // rdi
  int v13; // r14d
  BYTE *v14; // rbx
  int v15; // r12d
  int v16; // r15d
  int v17; // r12d
  BYTE *v18; // rbx
  int v19; // r15d
  unsigned __int64 v20; // rdx
  __int64 v21; // rax
  int v22; // [rsp+30h] [rbp-D0h]
  int v23; // [rsp+34h] [rbp-CCh]
  struct tagRECT Rect; // [rsp+40h] [rbp-C0h] BYREF
  TPMPARAMS tpm; // [rsp+50h] [rbp-B0h] BYREF
  char *v27; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v28[8]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v29[8]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v30[16]; // [rsp+80h] [rbp-80h] BYREF
  CHAR Destination[256]; // [rsp+90h] [rbp-70h] BYREF

  v1 = this;
  PopupMenu = CreatePopupMenu();
  `eh vector constructor iterator'(&v27, 8u, 4u, (void (*)(void *))CStr::CStr, (void (*)(void *))CWStr::~CWStr);
  GetStringResource(0x4B0u);
  CStr::operator=(&v27);
  GetStringResource(0x4B1u);
  CStr::operator=(v28);
  GetStringResource(0x4B2u);
  CStr::operator=(v29);
  GetStringResource(0x4B3u);
  CStr::operator=(v30);
  v4 = 0;
  do
  {
    v5 = v4 + 1;
    HxAppendMenu(PopupMenu, v3, v4 + 1, *(const char **)&v28[8 * v4 - 8]);
    v4 = v5;
  }
  while ( v5 < 4 );
  Rect = 0;
  GetWindowRect(*((HWND *)v1 + 17), &Rect);
  tpm.cbSize = 20;
  tpm.rcExclude = Rect;
  v6 = TrackPopupMenuEx(PopupMenu, 0x180u, Rect.right, Rect.top, *((HWND *)v1 + 1), &tpm);
  v7 = v6;
  if ( v6 > 0 )
  {
    memset_0(Destination, 0, 0xFAu);
    WindowTextLengthA = GetWindowTextLengthA(*((HWND *)v1 + 5));
    v9 = WindowTextLengthA;
    if ( WindowTextLengthA <= 0 )
    {
      SetWindowTextA(*((HWND *)v1 + 5), *((LPCSTR *)&tpm.rcExclude.bottom + v7));
      v10 = -1;
      do
        ++v10;
      while ( *(_BYTE *)(*((_QWORD *)&tpm.rcExclude.bottom + v7) + v10) );
LABEL_27:
      SetFocus(*((HWND *)v1 + 5));
      SendMessageA(
        *((HWND *)v1 + 5),
        0x142u,
        0,
        (unsigned __int16)v10 | ((unsigned __int64)(unsigned __int16)v10 << 16));
      goto LABEL_28;
    }
    v11 = (CHAR *)operator new[](WindowTextLengthA + 1LL);
    v12 = v11;
    if ( v11 )
    {
      GetWindowTextA(*((HWND *)v1 + 5), v11, v9 + 1);
      v22 = *((unsigned __int16 *)v1 + 561);
      v13 = *((unsigned __int16 *)v1 + 560);
      v14 = (BYTE *)v12;
      v15 = 0;
      v23 = 0;
      v16 = 0;
      if ( *v12 )
      {
        do
        {
          if ( v16 >= v13 )
            break;
          v15 += IsDBCSLeadByte(*v14) + 1;
          v14 = (BYTE *)CharNextA((LPCSTR)v14);
          ++v16;
        }
        while ( *v14 );
        v23 = v15;
      }
      v17 = 0;
      v18 = (BYTE *)v12;
      v19 = 0;
      if ( *v12 )
      {
        do
        {
          if ( v19 >= v22 )
            break;
          v17 += IsDBCSLeadByte(*v18) + 1;
          v18 = (BYTE *)CharNextA((LPCSTR)v18);
          ++v19;
        }
        while ( *v18 );
        v1 = this;
      }
      _strnset(Destination, 0, 0xFAu);
      v10 = -1;
      v21 = -1;
      do
        ++v21;
      while ( *(_BYTE *)(*((_QWORD *)&tpm.rcExclude.bottom + v7) + v21) );
      if ( v13 + (int)v21 + v22 + 3 <= 250 )
      {
        if ( v13 )
          StringCchCatNA(Destination, v20, v12, v23);
        StringCchCatA(Destination, 0xFAu, " ");
        StringCchCatA(Destination, 0xFAu, *((const char **)&tpm.rcExclude.bottom + v7));
        StringCchCatA(Destination, 0xFAu, " ");
        do
          ++v10;
        while ( Destination[v10] );
        StringCchCatA(Destination, 0xFAu, &v12[v17]);
        SetWindowTextA(*((HWND *)v1 + 5), Destination);
      }
      else
      {
        LOWORD(v10) = v13;
      }
      operator delete[](v12);
      goto LABEL_27;
    }
  }
LABEL_28:
  `eh vector destructor iterator'(&v27, 8u, 4u, (void (*)(void *))CWStr::~CWStr);
}

```

## disassembly

```asm
0x180007270  push    rbp
0x180007272  push    rbx
0x180007273  push    rsi
0x180007274  push    rdi
0x180007275  push    r12
0x180007277  push    r13
0x180007279  push    r14
0x18000727b  push    r15
0x18000727d  lea     rbp, [rsp-0A8h]
0x180007285  sub     rsp, 1A8h
0x18000728c  mov     rax, cs:__security_cookie
0x180007293  xor     rax, rsp
0x180007296  mov     [rbp+0E0h+var_50], rax
0x18000729d  mov     rsi, rcx
0x1800072a0  mov     [rsp+1E0h+var_1A8], rcx
0x1800072a5  call    cs:__imp_CreatePopupMenu
0x1800072ab  mov     rdi, rax
0x1800072ae  lea     r15, ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x1800072b5  mov     [rsp+1E0h+hwnd], r15; void (*)(void *)
0x1800072ba  lea     r9, ??0CStr@@QEAA@XZ; void (*)(void *)
0x1800072c1  mov     r14d, 4
0x1800072c7  mov     r8d, r14d; unsigned __int64
0x1800072ca  lea     r12d, [r14+4]
0x1800072ce  mov     edx, r12d; unsigned __int64
0x1800072d1  lea     rcx, [rsp+1E0h+var_178]; void *
0x1800072d6  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1800072db  nop
0x1800072dc  mov     ecx, 4B0h; uID
0x1800072e1  call    ?GetStringResource@@YAPEBDH@Z; GetStringResource(int)
0x1800072e6  mov     rdx, rax
0x1800072e9  lea     rcx, [rsp+1E0h+var_178]
0x1800072ee  call    ??4CStr@@QEAAXPEBD@Z; CStr::operator=(char const *)
0x1800072f3  mov     ecx, 4B1h; uID
0x1800072f8  call    ?GetStringResource@@YAPEBDH@Z; GetStringResource(int)
0x1800072fd  mov     rdx, rax
0x180007300  lea     rcx, [rsp+1E0h+var_170]
0x180007305  call    ??4CStr@@QEAAXPEBD@Z; CStr::operator=(char const *)
0x18000730a  mov     ecx, 4B2h; uID
0x18000730f  call    ?GetStringResource@@YAPEBDH@Z; GetStringResource(int)
0x180007314  mov     rdx, rax
0x180007317  lea     rcx, [rsp+1E0h+var_168]
0x18000731c  call    ??4CStr@@QEAAXPEBD@Z; CStr::operator=(char const *)
0x180007321  mov     ecx, 4B3h; uID
0x180007326  call    ?GetStringResource@@YAPEBDH@Z; GetStringResource(int)
0x18000732b  mov     rdx, rax
0x18000732e  lea     rcx, [rbp+0E0h+var_160]
0x180007332  call    ??4CStr@@QEAAXPEBD@Z; CStr::operator=(char const *)
0x180007337  xor     eax, eax
0x180007339  lea     ebx, [rax+1]
0x18000733c  mov     r9d, eax
0x18000733f  mov     r9, [rsp+r9*8+1E0h+var_178]; char *
0x180007344  mov     r8d, ebx; unsigned int
0x180007347  mov     rcx, rdi; hMenu
0x18000734a  call    ?HxAppendMenu@@YAHPEAUHMENU__@@IIPEBD@Z; HxAppendMenu(HMENU__ *,uint,uint,char const *)
0x18000734f  mov     eax, ebx
0x180007351  cmp     ebx, r14d
0x180007354  jl      short loc_180007339
0x180007356  xorps   xmm0, xmm0
0x180007359  movups  xmmword ptr [rsp+1E0h+Rect.left], xmm0
0x18000735e  lea     rdx, [rsp+1E0h+Rect]; lpRect
0x180007363  mov     rcx, [rsi+88h]; hWnd
0x18000736a  call    cs:__imp_GetWindowRect
0x180007370  mov     [rsp+1E0h+tpm.cbSize], 14h
0x180007378  mov     eax, [rsp+1E0h+Rect.left]
0x18000737c  mov     [rsp+1E0h+tpm.rcExclude.left], eax
0x180007380  mov     r9d, [rsp+1E0h+Rect.top]; y
0x180007385  mov     [rsp+1E0h+tpm.rcExclude.top], r9d
0x18000738a  mov     r8d, [rsp+1E0h+Rect.right]; x
0x18000738f  mov     [rsp+1E0h+tpm.rcExclude.right], r8d
0x180007394  mov     eax, [rsp+1E0h+Rect.bottom]
0x180007398  mov     [rsp+1E0h+tpm.rcExclude.bottom], eax
0x18000739c  lea     rax, [rsp+1E0h+tpm]
0x1800073a1  mov     [rsp+1E0h+lptpm], rax; lptpm
0x1800073a6  mov     rax, [rsi+8]
0x1800073aa  mov     [rsp+1E0h+hwnd], rax; hwnd
0x1800073af  mov     edx, 180h; uFlags
0x1800073b4  mov     rcx, rdi; hMenu
0x1800073b7  call    cs:__imp_TrackPopupMenuEx
0x1800073bd  movsxd  r13, eax
0x1800073c0  test    eax, eax
0x1800073c2  jle     loc_1800075C7
0x1800073c8  xor     edx, edx; Val
0x1800073ca  mov     r8d, 0FAh; Size
0x1800073d0  lea     rcx, [rbp+0E0h+Destination]; void *
0x1800073d4  call    memset_0
0x1800073d9  mov     rcx, [rsi+28h]; hWnd
0x1800073dd  call    cs:__imp_GetWindowTextLengthA
0x1800073e3  movsxd  rbx, eax
0x1800073e6  test    eax, eax
0x1800073e8  jg      short loc_180007410
0x1800073ea  mov     rdx, qword ptr [rsp+r13*8+1E0h+tpm.rcExclude.bottom]; lpString
0x1800073ef  mov     rcx, [rsi+28h]; hWnd
0x1800073f3  call    cs:__imp_SetWindowTextA
0x1800073f9  mov     rax, qword ptr [rsp+r13*8+1E0h+tpm.rcExclude.bottom]
0x1800073fe  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180007402  inc     rbx
0x180007405  cmp     byte ptr [rax+rbx], 0
0x180007409  jnz     short loc_180007402
0x18000740b  jmp     loc_18000759D
0x180007410  lea     rcx, [rbx+1]; unsigned __int64
0x180007414  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180007419  mov     rdi, rax
0x18000741c  test    rax, rax
0x18000741f  jz      loc_1800075C7
0x180007425  lea     r8d, [rbx+1]; nMaxCount
0x180007429  mov     rdx, rax; lpString
0x18000742c  mov     rcx, [rsi+28h]; hWnd
0x180007430  call    cs:__imp_GetWindowTextA
0x180007436  movzx   eax, word ptr [rsi+462h]
0x18000743d  mov     [rsp+1E0h+var_1B0], eax
0x180007441  movzx   r14d, word ptr [rsi+460h]
0x180007449  mov     rbx, rdi
0x18000744c  xor     r12d, r12d
0x18000744f  mov     [rsp+1E0h+var_1AC], r12d
0x180007454  xor     r15d, r15d
0x180007457  cmp     [rdi], r12b
0x18000745a  jz      short loc_180007487
0x18000745c  cmp     r15d, r14d
0x18000745f  jge     short loc_180007482
0x180007461  mov     cl, [rbx]; TestChar
0x180007463  call    cs:__imp_IsDBCSLeadByte
0x180007469  inc     eax
0x18000746b  add     r12d, eax
0x18000746e  mov     rcx, rbx; lpsz
0x180007471  call    cs:__imp_CharNextA
0x180007477  mov     rbx, rax
0x18000747a  inc     r15d
0x18000747d  cmp     byte ptr [rax], 0
0x180007480  jnz     short loc_18000745C
0x180007482  mov     [rsp+1E0h+var_1AC], r12d
0x180007487  xor     r12d, r12d
0x18000748a  mov     rbx, rdi
0x18000748d  xor     r15d, r15d
0x180007490  cmp     [rdi], r12b
0x180007493  jz      short loc_1800074C4
0x180007495  mov     esi, [rsp+1E0h+var_1B0]
0x180007499  cmp     r15d, esi
0x18000749c  jge     short loc_1800074BF
0x18000749e  mov     cl, [rbx]; TestChar
0x1800074a0  call    cs:__imp_IsDBCSLeadByte
0x1800074a6  inc     eax
0x1800074a8  add     r12d, eax
0x1800074ab  mov     rcx, rbx; lpsz
0x1800074ae  call    cs:__imp_CharNextA
0x1800074b4  mov     rbx, rax
0x1800074b7  inc     r15d
0x1800074ba  cmp     byte ptr [rax], 0
0x1800074bd  jnz     short loc_180007499
0x1800074bf  mov     rsi, [rsp+1E0h+var_1A8]
0x1800074c4  xor     edx, edx; Value
0x1800074c6  mov     r8d, 0FAh; Count
0x1800074cc  lea     rcx, [rbp+0E0h+Destination]; Destination
0x1800074d0  call    cs:__imp__strnset
0x1800074d6  mov     r15, r13
0x1800074d9  mov     rcx, qword ptr [rsp+r13*8+1E0h+tpm.rcExclude.bottom]
0x1800074de  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800074e2  mov     rax, rbx
0x1800074e5  inc     rax
0x1800074e8  cmp     byte ptr [rcx+rax], 0
0x1800074ec  jnz     short loc_1800074E5
0x1800074ee  add     eax, r14d
0x1800074f1  mov     ecx, [rsp+1E0h+var_1B0]
0x1800074f5  add     ecx, 3
0x1800074f8  add     ecx, eax
0x1800074fa  mov     r13d, 0FAh
0x180007500  cmp     ecx, r13d
0x180007503  jle     short loc_18000750A
0x180007505  mov     ebx, r14d
0x180007508  jmp     short loc_180007584
0x18000750a  test    r14d, r14d
0x18000750d  jz      short loc_180007520
0x18000750f  movsxd  r9, [rsp+1E0h+var_1AC]; unsigned __int64
0x180007514  mov     r8, rdi; char *
0x180007517  lea     rcx, [rbp+0E0h+Destination]; char *
0x18000751b  call    ?StringCchCatNA@@YAJPEAD_KPEBD1@Z; StringCchCatNA(char *,unsigned __int64,char const *,unsigned __int64)
0x180007520  lea     r8, lParam; " "
0x180007527  mov     rdx, r13; unsigned __int64
0x18000752a  lea     rcx, [rbp+0E0h+Destination]; char *
0x18000752e  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x180007533  mov     r8, qword ptr [rsp+r15*8+1E0h+tpm.rcExclude.bottom]; char *
0x180007538  mov     rdx, r13; unsigned __int64
0x18000753b  lea     rcx, [rbp+0E0h+Destination]; char *
0x18000753f  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x180007544  lea     r8, lParam; " "
0x18000754b  mov     rdx, r13; unsigned __int64
0x18000754e  lea     rcx, [rbp+0E0h+Destination]; char *
0x180007552  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x180007557  lea     rax, [rbp+0E0h+Destination]
0x18000755b  inc     rbx
0x18000755e  cmp     byte ptr [rax+rbx], 0
0x180007562  jnz     short loc_18000755B
0x180007564  movsxd  r8, r12d
0x180007567  add     r8, rdi; char *
0x18000756a  mov     rdx, r13; unsigned __int64
0x18000756d  lea     rcx, [rbp+0E0h+Destination]; char *
0x180007571  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x180007576  lea     rdx, [rbp+0E0h+Destination]; lpString
0x18000757a  mov     rcx, [rsi+28h]; hWnd
0x18000757e  call    cs:__imp_SetWindowTextA
0x180007584  mov     rcx, rdi; void *
0x180007587  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18000758c  mov     r14d, 4
0x180007592  lea     r15, ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180007599  lea     r12d, [r14+4]
0x18000759d  mov     rcx, [rsi+28h]; hWnd
0x1800075a1  call    cs:__imp_SetFocus
0x1800075a7  movzx   eax, bx
0x1800075aa  mov     r9d, eax
0x1800075ad  shl     r9, 10h
0x1800075b1  or      r9, rax; lParam
0x1800075b4  xor     r8d, r8d; wParam
0x1800075b7  mov     edx, 142h; Msg
0x1800075bc  mov     rcx, [rsi+28h]; hWnd
0x1800075c0  call    cs:__imp_SendMessageA
0x1800075c6  nop
0x1800075c7  mov     r9, r15; void (*)(void *)
0x1800075ca  mov     r8, r14; unsigned __int64
0x1800075cd  mov     rdx, r12; unsigned __int64
0x1800075d0  lea     rcx, [rsp+1E0h+var_178]; void *
0x1800075d5  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800075da  mov     rcx, [rbp+0E0h+var_50]
0x1800075e1  xor     rcx, rsp; StackCookie
0x1800075e4  call    __security_check_cookie
0x1800075e9  add     rsp, 1A8h
0x1800075f0  pop     r15
0x1800075f2  pop     r14
0x1800075f4  pop     r13
0x1800075f6  pop     r12
0x1800075f8  pop     rdi
0x1800075f9  pop     rsi
0x1800075fa  pop     rbx
0x1800075fb  pop     rbp
0x1800075fc  retn
```
