# SetWinType(char const *,tagHH_WINTYPE *,CHmData *)

- ea: `0x1800391b0`
- end: `0x180039698`
- name: `?SetWinType@@YAPEAUHWND__@@PEBDPEAUtagHH_WINTYPE@@PEAVCHmData@@@Z`
- size: `1256`
- prototype: `HWND __fastcall(const char *, struct tagHH_WINTYPE *, struct CHmData *)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1800399ec`
- `0x18005e364`

## callees

- `0x180006708`
- `0x1800095c8`
- `0x18002cff8`
- `0x1800391b0`
- `0x1800519d4`
- `0x180051bb8`
- `0x1800521f4`
- `0x180052258`
- `0x1800523d8`
- `0x18005300c`
- `0x180053084`
- `0x18005d238`
- `0x180068dd0`

## import_xrefs

- `KERNEL32!lstrlenA` at `0x1800394db`
- `KERNEL32!lstrlenA` at `0x1800394db`
- `USER32!MoveWindow` at `0x180039661`
- `USER32!MoveWindow` at `0x180039661`
- `USER32!SetWindowTextA` at `0x180039515`
- `USER32!SetWindowTextA` at `0x180039515`
- `USER32!ShowWindow` at `0x18003967f`
- `USER32!ShowWindow` at `0x18003967f`
- `USER32!GetWindowLongA` at `0x18003957b`
- `USER32!GetWindowLongA` at `0x18003957b`
- `USER32!SetWindowLongA` at `0x18003954c`
- `USER32!SetWindowLongA` at `0x1800395a6`
- `USER32!SetWindowLongA` at `0x18003954c`
- `USER32!SetWindowLongA` at `0x1800395a6`
- `USER32!SetWindowPos` at `0x1800395da`
- `USER32!SetWindowPos` at `0x1800395da`
- `USER32!GetWindowRect` at `0x180039603`
- `USER32!GetWindowRect` at `0x180039603`

## pseudocode

```c
HWND __fastcall SetWinType(const char *a1, struct tagHH_WINTYPE *a2, struct CHmData *a3)
{
  LPCTSTR pszType; // rcx
  struct CHHWinType *WindowSlot; // rax
  struct CHHWinType *v8; // rbx
  DWORD fsValidMembers; // ecx
  int nShowState; // eax
  int v11; // ecx
  DWORD fsToolBarFlags; // eax
  int tabpos; // eax
  int v14; // ecx
  LPCSTR *v15; // rsi
  LPCSTR v16; // rdi
  int v17; // eax
  char v19; // si
  HWND v20; // rcx
  LONG Styles; // eax
  HWND *v22; // rsi
  LONG left; // eax
  LONG right; // eax
  LONG top; // eax
  LONG bottom; // eax

  if ( !a2 )
    return 0;
  pszType = a2->pszType;
  if ( !pszType || !*pszType )
    return 0;
  if ( a1 && *a1 )
  {
    if ( IsGlobalWinType(pszType) && FindWindowType(a2->pszType, 0, 0) )
      return 0;
    if ( !a3 )
      FindCurFileData(a1);
  }
  else if ( !IsGlobalWinType(pszType) )
  {
    CGlobalWinTypes::Add((CGlobalWinTypes *)&off_18008B4E8, a2->pszType);
  }
  WindowSlot = FindOrCreateWindowSlot(a2->pszType, a1);
  v8 = WindowSlot;
  if ( !WindowSlot )
    return 0;
  *((_DWORD *)WindowSlot + 1) = a2->fUniCodeStrings;
  CHHWinType::SetString(WindowSlot, a2->pszCaption, (char **)WindowSlot + 3);
  CHHWinType::SetUrl(v8, a2->pszToc, (char **)v8 + 17);
  CHHWinType::SetUrl(v8, a2->pszIndex, (char **)v8 + 18);
  CHHWinType::SetUrl(v8, a2->pszFile, (char **)v8 + 19);
  fsValidMembers = a2->fsValidMembers;
  *((_DWORD *)v8 + 4) = fsValidMembers;
  if ( (fsValidMembers & 2) != 0 )
    *((_DWORD *)v8 + 5) = a2->fsWinProperties;
  if ( (fsValidMembers & 4) != 0 )
    *((_DWORD *)v8 + 8) = a2->dwStyles;
  if ( (fsValidMembers & 8) != 0 )
    *((_DWORD *)v8 + 9) = a2->dwExStyles;
  if ( (fsValidMembers & 0x10) != 0 )
    *(RECT *)((char *)v8 + 40) = a2->rcWindowPos;
  if ( (fsValidMembers & 0x40) != 0 )
    nShowState = a2->nShowState;
  else
    nShowState = 5;
  *((_DWORD *)v8 + 14) = nShowState;
  if ( (fsValidMembers & 0x200) != 0 )
    *((_DWORD *)v8 + 43) = a2->fNotExpanded;
  if ( (fsValidMembers & 0x20) != 0 )
    *((_DWORD *)v8 + 28) = a2->iNavWidth;
  *((_QWORD *)v8 + 9) = a2->hwndCaller;
  CHHWinType::SetUrl(v8, a2->pszHome, (char **)v8 + 20);
  v11 = *((_DWORD *)v8 + 4);
  if ( (v11 & 0x100) != 0 )
    fsToolBarFlags = a2->fsToolBarFlags;
  else
    fsToolBarFlags = 12294;
  *((_DWORD *)v8 + 42) = fsToolBarFlags;
  if ( (v11 & 0x400) != 0 )
    tabpos = a2->tabpos;
  else
    tabpos = 0;
  *((_DWORD *)v8 + 45) = tabpos;
  if ( (v11 & 0x800) != 0 )
  {
    *(_OWORD *)((char *)v8 + 188) = *(_OWORD *)a2->tabOrder;
    *((_DWORD *)v8 + 51) = *(_DWORD *)&a2->tabOrder[16];
  }
  else
  {
    *((_DWORD *)v8 + 48) = -1;
    v14 = 11;
    *((_WORD *)v8 + 98) = -1;
    *((_BYTE *)v8 + 198) = -1;
    *((_DWORD *)v8 + 47) = 50462976;
    *((_BYTE *)v8 + 192) = 4;
    do
    {
      *((_BYTE *)v8 + (unsigned int)v14 + 188) = v14;
      ++v14;
    }
    while ( v14 <= 19 );
    *((_DWORD *)v8 + 4) |= 0x800u;
  }
  if ( (*((_DWORD *)v8 + 42) & 0x40000) != 0 && a2->pszUrlJump1 )
  {
    CHHWinType::SetString(v8, a2->pszJump1, (char **)v8 + 27);
    CHHWinType::SetUrl(v8, a2->pszUrlJump1, (char **)v8 + 29);
  }
  if ( (*((_DWORD *)v8 + 42) & 0x80000) != 0 && a2->pszUrlJump2 )
  {
    CHHWinType::SetString(v8, a2->pszJump2, (char **)v8 + 28);
    CHHWinType::SetUrl(v8, a2->pszUrlJump2, (char **)v8 + 30);
  }
  if ( (*((_DWORD *)v8 + 4) & 0x2000) != 0 )
    *((_DWORD *)v8 + 44) = a2->curNavType;
  *((_DWORD *)v8 + 46) = a2->idNotify;
  if ( a3 )
    *((_QWORD *)v8 + 77) = a3;
  if ( !(unsigned int)CHHWinType::IsValidNavPane(v8, 0) && (*((_DWORD *)v8 + 4) & 0x100) != 0 )
    *((_DWORD *)v8 + 42) &= 0xFF9FFFFF;
  if ( (unsigned int)CHHWinType::GetValidNavPane(v8) == -1 )
  {
    *((_DWORD *)v8 + 42) &= ~2u;
    *((_DWORD *)v8 + 43) = 1;
  }
  v15 = (LPCSTR *)((char *)v8 + 8);
  if ( !*((_QWORD *)v8 + 1) )
  {
    CHHWinType::SetString(v8, a2->pszType, (char **)v8 + 1);
    v16 = *v15;
    if ( *v15 )
    {
      if ( *v16 == 62 )
      {
        v17 = lstrlenA(*v15);
        StringCchCopyA((char *)*v15, v17, v16 + 1);
      }
    }
    return (HWND)*((_QWORD *)v8 + 8);
  }
  if ( a2->pszCaption && (unsigned int)IsValidWindow(*((HWND *)v8 + 8)) )
    SetWindowTextA(*((HWND *)v8 + 8), *((LPCSTR *)v8 + 3));
  v19 = 0;
  if ( (a2->fsValidMembers & 4) != 0 )
  {
    v20 = (HWND)*((_QWORD *)v8 + 8);
    *((_DWORD *)v8 + 8) |= 0x14000000u;
    if ( (unsigned int)IsValidWindow(v20) )
    {
      Styles = CHHWinType::GetStyles(v8);
      SetWindowLongA(*((HWND *)v8 + 8), -16, Styles);
      v19 = 1;
    }
  }
  if ( (a2->fsValidMembers & 8) == 0 )
    goto LABEL_73;
  if ( (a2->fsWinProperties & 0x10) == 0 )
  {
    if ( (unsigned int)IsValidWindow(*((HWND *)v8 + 8)) )
      *((_DWORD *)v8 + 8) |= GetWindowLongA(*((HWND *)v8 + 8), -20);
    if ( (a2->fsWinProperties & 2) != 0 )
      *((_DWORD *)v8 + 8) |= 8u;
  }
  if ( (unsigned int)IsValidWindow(*((HWND *)v8 + 8)) )
  {
    SetWindowLongA(*((HWND *)v8 + 8), -20, *((_DWORD *)v8 + 9));
  }
  else
  {
LABEL_73:
    if ( !v19 )
    {
      v22 = (HWND *)((char *)v8 + 64);
      goto LABEL_76;
    }
  }
  v22 = (HWND *)((char *)v8 + 64);
  SetWindowPos(*((HWND *)v8 + 8), 0, 0, 0, 0, 0, 0x27u);
LABEL_76:
  if ( (a2->fsValidMembers & 0x10) != 0 )
  {
    v22 = (HWND *)((char *)v8 + 64);
    if ( (unsigned int)IsValidWindow(*((HWND *)v8 + 8)) )
      GetWindowRect(*v22, (LPRECT)((char *)v8 + 40));
    left = a2->rcWindowPos.left;
    if ( left >= 0 )
      *((_DWORD *)v8 + 10) = left;
    right = a2->rcWindowPos.right;
    if ( right >= 0 )
      *((_DWORD *)v8 + 12) = right;
    top = a2->rcWindowPos.top;
    if ( top >= 0 )
      *((_DWORD *)v8 + 11) = top;
    bottom = a2->rcWindowPos.bottom;
    if ( bottom >= 0 )
      *((_DWORD *)v8 + 13) = bottom;
    if ( (unsigned int)IsValidWindow(*((HWND *)v8 + 8)) )
      MoveWindow(
        *v22,
        *((_DWORD *)v8 + 10),
        *((_DWORD *)v8 + 11),
        *((_DWORD *)v8 + 12) - *((_DWORD *)v8 + 10),
        *((_DWORD *)v8 + 13) - *((_DWORD *)v8 + 11),
        1);
  }
  if ( (a2->fsValidMembers & 0x40) != 0 && (unsigned int)IsValidWindow(*v22) )
    ShowWindow(*v22, *((_DWORD *)v8 + 14));
  return *v22;
}

```

## disassembly

```asm
0x1800391b0  push    rbx
0x1800391b2  push    rsi
0x1800391b3  push    rdi
0x1800391b4  push    r14
0x1800391b6  push    r15
0x1800391b8  sub     rsp, 40h
0x1800391bc  mov     rsi, r8
0x1800391bf  mov     rdi, rdx
0x1800391c2  mov     rbx, rcx
0x1800391c5  test    rdx, rdx
0x1800391c8  jz      loc_18003968A
0x1800391ce  mov     rcx, [rdx+8]; char *
0x1800391d2  test    rcx, rcx
0x1800391d5  jz      loc_18003968A
0x1800391db  cmp     byte ptr [rcx], 0
0x1800391de  jz      loc_18003968A
0x1800391e4  test    rbx, rbx
0x1800391e7  jz      short loc_18003921D
0x1800391e9  cmp     byte ptr [rbx], 0
0x1800391ec  jz      short loc_18003921D
0x1800391ee  call    ?IsGlobalWinType@@YA_NPEBD@Z; IsGlobalWinType(char const *)
0x1800391f3  test    al, al
0x1800391f5  jz      short loc_18003920E
0x1800391f7  mov     rcx, [rdi+8]; char *
0x1800391fb  xor     r8d, r8d; char *
0x1800391fe  xor     edx, edx; HWND
0x180039200  call    ?FindWindowType@@YAPEAVCHHWinType@@PEBDPEAUHWND__@@0@Z; FindWindowType(char const *,HWND__ *,char const *)
0x180039205  test    rax, rax
0x180039208  jnz     loc_18003968A
0x18003920e  test    rsi, rsi
0x180039211  jnz     short loc_180039236
0x180039213  mov     rcx, rbx; char *
0x180039216  call    ?FindCurFileData@@YAPEAVCHmData@@PEBD@Z; FindCurFileData(char const *)
0x18003921b  jmp     short loc_180039236
0x18003921d  call    ?IsGlobalWinType@@YA_NPEBD@Z; IsGlobalWinType(char const *)
0x180039222  test    al, al
0x180039224  jnz     short loc_180039236
0x180039226  mov     rdx, [rdi+8]; char *
0x18003922a  lea     rcx, off_18008B4E8; this
0x180039231  call    ?Add@CGlobalWinTypes@@QEAAXPEBD@Z; CGlobalWinTypes::Add(char const *)
0x180039236  mov     rcx, [rdi+8]; char *
0x18003923a  mov     rdx, rbx; char *
0x18003923d  call    ?FindOrCreateWindowSlot@@YAPEAVCHHWinType@@PEBD0@Z; FindOrCreateWindowSlot(char const *,char const *)
0x180039242  mov     rbx, rax
0x180039245  test    rax, rax
0x180039248  jz      loc_18003968A
0x18003924e  mov     ecx, [rdi+4]
0x180039251  lea     r8, [rax+18h]; char **
0x180039255  mov     [rax+4], ecx
0x180039258  mov     rcx, rax; this
0x18003925b  mov     rdx, [rdi+18h]; char *
0x18003925f  call    ?SetString@CHHWinType@@QEAAXPEBDPEAPEAD@Z; CHHWinType::SetString(char const *,char * *)
0x180039264  mov     rdx, [rdi+88h]; char *
0x18003926b  lea     r8, [rbx+88h]; char **
0x180039272  mov     rcx, rbx; this
0x180039275  call    ?SetUrl@CHHWinType@@QEAAXPEBDPEAPEAD@Z; CHHWinType::SetUrl(char const *,char * *)
0x18003927a  mov     rdx, [rdi+90h]; char *
0x180039281  lea     r8, [rbx+90h]; char **
0x180039288  mov     rcx, rbx; this
0x18003928b  call    ?SetUrl@CHHWinType@@QEAAXPEBDPEAPEAD@Z; CHHWinType::SetUrl(char const *,char * *)
0x180039290  mov     rdx, [rdi+98h]; char *
0x180039297  lea     r8, [rbx+98h]; char **
0x18003929e  mov     rcx, rbx; this
0x1800392a1  call    ?SetUrl@CHHWinType@@QEAAXPEBDPEAPEAD@Z; CHHWinType::SetUrl(char const *,char * *)
0x1800392a6  mov     ecx, [rdi+10h]
0x1800392a9  mov     [rbx+10h], ecx
0x1800392ac  test    cl, 2
0x1800392af  jz      short loc_1800392B7
0x1800392b1  mov     eax, [rdi+14h]
0x1800392b4  mov     [rbx+14h], eax
0x1800392b7  test    cl, 4
0x1800392ba  jz      short loc_1800392C2
0x1800392bc  mov     eax, [rdi+20h]
0x1800392bf  mov     [rbx+20h], eax
0x1800392c2  test    cl, 8
0x1800392c5  jz      short loc_1800392CD
0x1800392c7  mov     eax, [rdi+24h]
0x1800392ca  mov     [rbx+24h], eax
0x1800392cd  test    cl, 10h
0x1800392d0  jz      short loc_1800392DB
0x1800392d2  movups  xmm0, xmmword ptr [rdi+28h]
0x1800392d6  movdqu  xmmword ptr [rbx+28h], xmm0
0x1800392db  test    cl, 40h
0x1800392de  jz      short loc_1800392E5
0x1800392e0  mov     eax, [rdi+38h]
0x1800392e3  jmp     short loc_1800392EA
0x1800392e5  mov     eax, 5
0x1800392ea  mov     [rbx+38h], eax
0x1800392ed  bt      ecx, 9
0x1800392f1  jnb     short loc_1800392FF
0x1800392f3  mov     eax, [rdi+0ACh]
0x1800392f9  mov     [rbx+0ACh], eax
0x1800392ff  test    cl, 20h
0x180039302  jz      short loc_18003930A
0x180039304  mov     eax, [rdi+70h]
0x180039307  mov     [rbx+70h], eax
0x18003930a  mov     rax, [rdi+48h]
0x18003930e  lea     r8, [rbx+0A0h]; char **
0x180039315  mov     [rbx+48h], rax
0x180039319  mov     rcx, rbx; this
0x18003931c  mov     rdx, [rdi+0A0h]; char *
0x180039323  call    ?SetUrl@CHHWinType@@QEAAXPEBDPEAPEAD@Z; CHHWinType::SetUrl(char const *,char * *)
0x180039328  mov     ecx, [rbx+10h]
0x18003932b  bt      ecx, 8
0x18003932f  jnb     short loc_180039339
0x180039331  mov     eax, [rdi+0A8h]
0x180039337  jmp     short loc_18003933E
0x180039339  mov     eax, 3006h
0x18003933e  mov     [rbx+0A8h], eax
0x180039344  bt      ecx, 0Ah
0x180039348  jnb     short loc_180039352
0x18003934a  mov     eax, [rdi+0B4h]
0x180039350  jmp     short loc_180039354
0x180039352  xor     eax, eax
0x180039354  or      r15, 0FFFFFFFFFFFFFFFFh
0x180039358  mov     [rbx+0B4h], eax
0x18003935e  mov     edx, 800h
0x180039363  test    edx, ecx
0x180039365  jz      short loc_180039383
0x180039367  movups  xmm0, xmmword ptr [rdi+0BCh]
0x18003936e  movups  xmmword ptr [rbx+0BCh], xmm0
0x180039375  mov     eax, [rdi+0CCh]
0x18003937b  mov     [rbx+0CCh], eax
0x180039381  jmp     short loc_1800393C2
0x180039383  mov     [rbx+0C0h], r15d
0x18003938a  mov     ecx, 0Bh
0x18003938f  mov     [rbx+0C4h], r15w
0x180039397  mov     [rbx+0C6h], r15b
0x18003939e  mov     dword ptr [rbx+0BCh], 3020100h
0x1800393a8  mov     byte ptr [rbx+0C0h], 4
0x1800393af  mov     eax, ecx
0x1800393b1  mov     [rax+rbx+0BCh], cl
0x1800393b8  inc     ecx
0x1800393ba  cmp     ecx, 13h
0x1800393bd  jle     short loc_1800393AF
0x1800393bf  or      [rbx+10h], edx
0x1800393c2  test    dword ptr [rbx+0A8h], 40000h
0x1800393cc  jz      short loc_180039404
0x1800393ce  cmp     qword ptr [rdi+0E8h], 0
0x1800393d6  jz      short loc_180039404
0x1800393d8  mov     rdx, [rdi+0D8h]; char *
0x1800393df  lea     r8, [rbx+0D8h]; char **
0x1800393e6  mov     rcx, rbx; this
0x1800393e9  call    ?SetString@CHHWinType@@QEAAXPEBDPEAPEAD@Z; CHHWinType::SetString(char const *,char * *)
0x1800393ee  mov     rdx, [rdi+0E8h]; char *
0x1800393f5  lea     r8, [rbx+0E8h]; char **
0x1800393fc  mov     rcx, rbx; this
0x1800393ff  call    ?SetUrl@CHHWinType@@QEAAXPEBDPEAPEAD@Z; CHHWinType::SetUrl(char const *,char * *)
0x180039404  test    dword ptr [rbx+0A8h], 80000h
0x18003940e  jz      short loc_180039446
0x180039410  cmp     qword ptr [rdi+0F0h], 0
0x180039418  jz      short loc_180039446
0x18003941a  mov     rdx, [rdi+0E0h]; char *
0x180039421  lea     r8, [rbx+0E0h]; char **
0x180039428  mov     rcx, rbx; this
0x18003942b  call    ?SetString@CHHWinType@@QEAAXPEBDPEAPEAD@Z; CHHWinType::SetString(char const *,char * *)
0x180039430  mov     rdx, [rdi+0F0h]; char *
0x180039437  lea     r8, [rbx+0F0h]; char **
0x18003943e  mov     rcx, rbx; this
0x180039441  call    ?SetUrl@CHHWinType@@QEAAXPEBDPEAPEAD@Z; CHHWinType::SetUrl(char const *,char * *)
0x180039446  test    dword ptr [rbx+10h], 2000h
0x18003944d  jz      short loc_18003945B
0x18003944f  mov     eax, [rdi+0B0h]
0x180039455  mov     [rbx+0B0h], eax
0x18003945b  mov     eax, [rdi+0B8h]
0x180039461  mov     [rbx+0B8h], eax
0x180039467  test    rsi, rsi
0x18003946a  jz      short loc_180039473
0x18003946c  mov     [rbx+268h], rsi
0x180039473  xor     edx, edx; int
0x180039475  mov     rcx, rbx; this
0x180039478  call    ?IsValidNavPane@CHHWinType@@QEAAHH@Z; CHHWinType::IsValidNavPane(int)
0x18003947d  test    eax, eax
0x18003947f  jnz     short loc_180039494
0x180039481  test    dword ptr [rbx+10h], 100h
0x180039488  jz      short loc_180039494
0x18003948a  and     dword ptr [rbx+0A8h], 0FF9FFFFFh
0x180039494  mov     rcx, rbx; this
0x180039497  call    ?GetValidNavPane@CHHWinType@@QEAAHXZ; CHHWinType::GetValidNavPane(void)
0x18003949c  cmp     eax, r15d
0x18003949f  jnz     short loc_1800394B2
0x1800394a1  and     dword ptr [rbx+0A8h], 0FFFFFFFDh
0x1800394a8  mov     dword ptr [rbx+0ACh], 1
0x1800394b2  lea     rsi, [rbx+8]
0x1800394b6  cmp     qword ptr [rsi], 0
0x1800394ba  jnz     short loc_1800394F9
0x1800394bc  mov     rdx, [rdi+8]; char *
0x1800394c0  mov     r8, rsi; char **
0x1800394c3  mov     rcx, rbx; this
0x1800394c6  call    ?SetString@CHHWinType@@QEAAXPEBDPEAPEAD@Z; CHHWinType::SetString(char const *,char * *)
0x1800394cb  mov     rdi, [rsi]
0x1800394ce  test    rdi, rdi
0x1800394d1  jz      short loc_1800394F0
0x1800394d3  cmp     byte ptr [rdi], 3Eh ; '>'
0x1800394d6  jnz     short loc_1800394F0
0x1800394d8  mov     rcx, rdi; lpString
0x1800394db  call    cs:__imp_lstrlenA
0x1800394e1  mov     rcx, [rsi]; char *
0x1800394e4  lea     r8, [rdi+1]; char *
0x1800394e8  movsxd  rdx, eax; unsigned __int64
0x1800394eb  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800394f0  mov     rax, [rbx+40h]
0x1800394f4  jmp     loc_18003968C
0x1800394f9  cmp     qword ptr [rdi+18h], 0
0x1800394fe  jz      short loc_18003951B
0x180039500  mov     rcx, [rbx+40h]; HWND
0x180039504  call    ?IsValidWindow@@YAHPEAUHWND__@@@Z; IsValidWindow(HWND__ *)
0x180039509  test    eax, eax
0x18003950b  jz      short loc_18003951B
0x18003950d  mov     rdx, [rbx+18h]; lpString
0x180039511  mov     rcx, [rbx+40h]; hWnd
0x180039515  call    cs:__imp_SetWindowTextA
0x18003951b  xor     sil, sil
0x18003951e  test    byte ptr [rdi+10h], 4
0x180039522  jz      short loc_180039555
0x180039524  mov     rcx, [rbx+40h]; HWND
0x180039528  or      dword ptr [rbx+20h], 14000000h
0x18003952f  call    ?IsValidWindow@@YAHPEAUHWND__@@@Z; IsValidWindow(HWND__ *)
0x180039534  test    eax, eax
0x180039536  jz      short loc_180039555
0x180039538  mov     rcx, rbx; this
0x18003953b  call    ?GetStyles@CHHWinType@@QEBAKXZ; CHHWinType::GetStyles(void)
0x180039540  mov     rcx, [rbx+40h]; hWnd
0x180039544  mov     r8d, eax; dwNewLong
0x180039547  mov     edx, 0FFFFFFF0h; nIndex
0x18003954c  call    cs:__imp_SetWindowLongA
0x180039552  mov     sil, 1
0x180039555  test    byte ptr [rdi+10h], 8
0x180039559  jz      short loc_1800395AE
0x18003955b  test    byte ptr [rdi+14h], 10h
0x18003955f  mov     r14d, 0FFFFFFECh
0x180039565  jnz     short loc_18003958E
0x180039567  mov     rcx, [rbx+40h]; HWND
0x18003956b  call    ?IsValidWindow@@YAHPEAUHWND__@@@Z; IsValidWindow(HWND__ *)
0x180039570  test    eax, eax
0x180039572  jz      short loc_180039584
0x180039574  mov     rcx, [rbx+40h]; hWnd
0x180039578  mov     edx, r14d; nIndex
0x18003957b  call    cs:__imp_GetWindowLongA
0x180039581  or      [rbx+20h], eax
0x180039584  test    byte ptr [rdi+14h], 2
0x180039588  jz      short loc_18003958E
0x18003958a  or      dword ptr [rbx+20h], 8
0x18003958e  mov     rcx, [rbx+40h]; HWND
0x180039592  call    ?IsValidWindow@@YAHPEAUHWND__@@@Z; IsValidWindow(HWND__ *)
0x180039597  test    eax, eax
0x180039599  jz      short loc_1800395AE
0x18003959b  mov     r8d, [rbx+24h]; dwNewLong
0x18003959f  mov     edx, r14d; nIndex
0x1800395a2  mov     rcx, [rbx+40h]; hWnd
0x1800395a6  call    cs:__imp_SetWindowLongA
0x1800395ac  jmp     short loc_1800395B3
0x1800395ae  test    sil, sil
0x1800395b1  jz      short loc_1800395E2
0x1800395b3  mov     [rsp+68h+uFlags], 27h ; '''; uFlags
0x1800395bb  lea     rsi, [rbx+40h]
0x1800395bf  mov     rcx, [rsi]; hWnd
0x1800395c2  xor     r9d, r9d; Y
0x1800395c5  mov     [rsp+68h+cy], 0; cy
0x1800395cd  xor     r8d, r8d; X
0x1800395d0  xor     edx, edx; hWndInsertAfter
0x1800395d2  mov     [rsp+68h+nHeight], 0; cx
0x1800395da  call    cs:__imp_SetWindowPos
0x1800395e0  jmp     short loc_1800395E6
0x1800395e2  lea     rsi, [rbx+40h]
0x1800395e6  test    byte ptr [rdi+10h], 10h
0x1800395ea  jz      short loc_180039667
0x1800395ec  lea     rsi, [rbx+40h]
0x1800395f0  mov     rcx, [rsi]; HWND
0x1800395f3  call    ?IsValidWindow@@YAHPEAUHWND__@@@Z; IsValidWindow(HWND__ *)
0x1800395f8  test    eax, eax
0x1800395fa  jz      short loc_180039609
0x1800395fc  mov     rcx, [rsi]; hWnd
0x1800395ff  lea     rdx, [rbx+28h]; lpRect
0x180039603  call    cs:__imp_GetWindowRect
0x180039609  mov     eax, [rdi+28h]
0x18003960c  test    eax, eax
0x18003960e  js      short loc_180039613
0x180039610  mov     [rbx+28h], eax
0x180039613  mov     eax, [rdi+30h]
0x180039616  test    eax, eax
0x180039618  js      short loc_18003961D
0x18003961a  mov     [rbx+30h], eax
0x18003961d  mov     eax, [rdi+2Ch]
0x180039620  test    eax, eax
0x180039622  js      short loc_180039627
0x180039624  mov     [rbx+2Ch], eax
0x180039627  mov     eax, [rdi+34h]
0x18003962a  test    eax, eax
0x18003962c  js      short loc_180039631
0x18003962e  mov     [rbx+34h], eax
0x180039631  mov     rcx, [rbx+40h]; HWND
0x180039635  call    ?IsValidWindow@@YAHPEAUHWND__@@@Z; IsValidWindow(HWND__ *)
0x18003963a  test    eax, eax
0x18003963c  jz      short loc_180039667
0x18003963e  mov     eax, [rbx+34h]
0x180039641  mov     r9d, [rbx+30h]
0x180039645  sub     eax, [rbx+2Ch]
0x180039648  mov     edx, [rbx+28h]; X
0x18003964b  sub     r9d, edx; nWidth
  ... truncated ...
```
