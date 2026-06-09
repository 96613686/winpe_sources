# CSampleDialog::FillDirs(HWND__ *,HWND__ *)

- ea: `0x180049ddc`
- end: `0x18004a3fa`
- name: `?FillDirs@CSampleDialog@@QEAAXPEAUHWND__@@0@Z`
- size: `1566`
- prototype: `void(CSampleDialog *__hidden this, HWND, HWND)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18004af3c`

## callees

- `0x1800095c8`
- `0x180042d40`
- `0x180049ddc`
- `0x18004cbec`
- `0x180075c42`
- `0x180075c5a`
- `0x180075c90`

## import_xrefs

- `msvcrt!malloc` at `0x18004a0bc`
- `msvcrt!malloc` at `0x18004a223`
- `msvcrt!malloc` at `0x18004a0bc`
- `msvcrt!malloc` at `0x18004a223`
- `msvcrt!free` at `0x180049eaf`
- `msvcrt!free` at `0x180049eaf`
- `KERNEL32!IsDBCSLeadByte` at `0x18004a2f0`
- `KERNEL32!IsDBCSLeadByte` at `0x18004a2f0`
- `KERNEL32!lstrcmpiA` at `0x18004a059`
- `KERNEL32!lstrcmpiA` at `0x18004a059`
- `KERNEL32!FindFirstFileA` at `0x180049f89`
- `KERNEL32!FindFirstFileA` at `0x180049f89`
- `KERNEL32!AreFileApisANSI` at `0x180049f24`
- `KERNEL32!AreFileApisANSI` at `0x180049f24`
- `KERNEL32!SetFileApisToOEM` at `0x180049f2e`
- `KERNEL32!SetFileApisToOEM` at `0x180049f2e`
- `KERNEL32!FindNextFileA` at `0x18004a128`
- `KERNEL32!FindNextFileA` at `0x18004a128`
- `KERNEL32!SetFileApisToANSI` at `0x18004a3ca`
- `KERNEL32!SetFileApisToANSI` at `0x18004a3ca`
- `USER32!CharLowerA` at `0x18004a004`
- `USER32!CharLowerA` at `0x18004a004`
- `USER32!OemToCharBuffA` at `0x180049eef`
- `USER32!OemToCharBuffA` at `0x180049ffa`
- `USER32!OemToCharBuffA` at `0x18004a166`
- `USER32!OemToCharBuffA` at `0x180049eef`
- `USER32!OemToCharBuffA` at `0x180049ffa`
- `USER32!OemToCharBuffA` at `0x18004a166`
- `USER32!CharPrevA` at `0x180049f58`
- `USER32!CharPrevA` at `0x180049f58`
- `USER32!ShowScrollBar` at `0x18004a370`
- `USER32!ShowScrollBar` at `0x18004a370`
- `USER32!ReleaseDC` at `0x18004a3bd`
- `USER32!ReleaseDC` at `0x18004a3bd`
- `USER32!GetDC` at `0x180049e49`
- `USER32!GetDC` at `0x180049e49`
- `USER32!CharNextA` at `0x180049f69`
- `USER32!CharNextA` at `0x18004a1b2`
- `USER32!CharNextA` at `0x180049f69`
- `USER32!CharNextA` at `0x18004a1b2`
- `USER32!SetWindowTextA` at `0x180049eff`
- `USER32!SetWindowTextA` at `0x180049eff`
- `USER32!GetWindowRect` at `0x180049e5c`
- `USER32!GetWindowRect` at `0x180049e5c`
- `USER32!InvalidateRect` at `0x18004a3af`
- `USER32!InvalidateRect` at `0x18004a3af`
- `USER32!SendMessageA` at `0x180049e6f`
- `USER32!SendMessageA` at `0x180049e83`
- `USER32!SendMessageA` at `0x180049ea1`
- `USER32!SendMessageA` at `0x180049ec9`
- `USER32!SendMessageA` at `0x18004a01f`
- `USER32!SendMessageA` at `0x18004a043`
- `USER32!SendMessageA` at `0x18004a07d`
- `USER32!SendMessageA` at `0x18004a09c`
- `USER32!SendMessageA` at `0x18004a0ea`
- `USER32!SendMessageA` at `0x18004a202`
- `USER32!SendMessageA` at `0x18004a26c`
- `USER32!SendMessageA` at `0x18004a350`
- `USER32!SendMessageA` at `0x18004a38b`
- `USER32!SendMessageA` at `0x18004a3a1`
- `USER32!SendMessageA` at `0x180049e6f`
- `USER32!SendMessageA` at `0x180049e83`
- `USER32!SendMessageA` at `0x180049ea1`
- `USER32!SendMessageA` at `0x180049ec9`
- `USER32!SendMessageA` at `0x18004a01f`
- `USER32!SendMessageA` at `0x18004a043`
- `USER32!SendMessageA` at `0x18004a07d`
- `USER32!SendMessageA` at `0x18004a09c`
- `USER32!SendMessageA` at `0x18004a0ea`
- `USER32!SendMessageA` at `0x18004a202`
- `USER32!SendMessageA` at `0x18004a26c`
- `USER32!SendMessageA` at `0x18004a350`
- `USER32!SendMessageA` at `0x18004a38b`
- `USER32!SendMessageA` at `0x18004a3a1`
- `GDI32!GetTextExtentPoint32A` at `0x18004a10f`
- `GDI32!GetTextExtentPoint32A` at `0x18004a298`
- `GDI32!GetTextExtentPoint32A` at `0x18004a10f`
- `GDI32!GetTextExtentPoint32A` at `0x18004a298`

## pseudocode

```c
void __fastcall CSampleDialog::FillDirs(CSampleDialog *this, HWND a2, HWND a3)
{
  CSampleDialog *v5; // r12
  int v6; // esi
  unsigned int i; // ebx
  void *v8; // rax
  __int64 v9; // r8
  const CHAR *v10; // r15
  __int64 v11; // rcx
  WPARAM v12; // rbx
  LPSTR v13; // rsi
  unsigned __int64 v14; // rdx
  const char *v15; // r8
  HANDLE FirstFileA; // r13
  BOOL NextFileA; // eax
  HDC v18; // rsi
  LONG cx; // r15d
  __int64 v20; // r8
  int v21; // r14d
  unsigned int j; // eax
  WPARAM v23; // r12
  __int64 v24; // rax
  size_t v25; // r14
  void *v26; // rax
  LPARAM v27; // rbx
  __int64 v28; // r8
  int v29; // r14d
  __int64 v30; // r8
  CHAR *v31; // rsi
  unsigned __int16 v32; // r13
  LPARAM *v33; // rbx
  BYTE v34; // cl
  __int64 v35; // rax
  LPSTR v36; // rax
  __int64 v37; // rax
  size_t v38; // r14
  void *v39; // rax
  void *v40; // rbx
  size_t v41; // r8
  __int64 v42; // r8
  int v43; // eax
  char v44; // al
  int v45; // esi
  unsigned int v46; // eax
  LONG v47; // [rsp+20h] [rbp-E0h]
  int v48; // [rsp+24h] [rbp-DCh]
  struct tagSIZE psizl; // [rsp+28h] [rbp-D8h] BYREF
  BOOL v50; // [rsp+30h] [rbp-D0h]
  HDC hdc; // [rsp+38h] [rbp-C8h]
  CHAR *v52; // [rsp+40h] [rbp-C0h]
  CSampleDialog *v53; // [rsp+48h] [rbp-B8h]
  const CHAR *v54; // [rsp+50h] [rbp-B0h]
  struct tagRECT Rect; // [rsp+58h] [rbp-A8h] BYREF
  _WIN32_FIND_DATAA FindFileData; // [rsp+70h] [rbp-90h] BYREF
  CHAR v57[512]; // [rsp+1B0h] [rbp+B0h] BYREF
  CHAR lParam[512]; // [rsp+3B0h] [rbp+2B0h] BYREF
  CHAR szDst[512]; // [rsp+5B0h] [rbp+4B0h] BYREF
  char Src[512]; // [rsp+7B0h] [rbp+6B0h] BYREF

  v53 = this;
  v5 = this;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v47 = 0;
  Rect = 0;
  v48 = 0;
  psizl = 0;
  hdc = GetDC(a2);
  GetWindowRect(a2, &Rect);
  SendMessageA(a2, 0xBu, 0, 0);
  v6 = SendMessageA(a2, 0x18Bu, 0, 0);
  for ( i = 0; (int)i < v6; ++i )
  {
    v8 = (void *)SendMessageA(a2, 0x199u, i, 0);
    if ( v8 )
      free(v8);
  }
  SendMessageA(a2, 0x184u, 0, 0);
  v9 = -1;
  do
    ++v9;
  while ( *((_BYTE *)v5 + v9 + 108) );
  OemToCharBuffA((LPCSTR)v5 + 108, szDst, v9 + 1);
  SetWindowTextA(a3, szDst);
  v10 = (char *)v5 + 620;
  v54 = (char *)v5 + 620;
  StringCbCopyA((char *)v5 + 620, 0x200u, (const char *)v5 + 108);
  v50 = AreFileApisANSI();
  SetFileApisToOEM();
  v11 = -1;
  v12 = 0;
  do
    ++v11;
  while ( v10[v11] );
  v13 = (char *)v5 + v11 + 620;
  v52 = v13;
  if ( *CharPrevA((LPCSTR)v5 + 620, v13) != 92 )
  {
    *v13 = 92;
    v13 = CharNextA(v13);
    v52 = v13;
    *v13 = 0;
  }
  StringCbCatA((char *)v5 + 620, v14, v15);
  FirstFileA = FindFirstFileA((LPCSTR)v5 + 620, &FindFileData);
  NextFileA = 1;
  if ( FirstFileA != (HANDLE)-1LL )
  {
    v18 = hdc;
    cx = 0;
    while ( NextFileA )
    {
      if ( (FindFileData.dwFileAttributes & 0x10) != 0 && FindFileData.cFileName[0] != 46 )
      {
        StringCchCopyA(Src, 0x200u, FindFileData.cFileName);
        v20 = -1;
        do
          ++v20;
        while ( FindFileData.cFileName[v20] );
        OemToCharBuffA(FindFileData.cFileName, FindFileData.cFileName, v20 + 1);
        CharLowerA(FindFileData.cFileName);
        v21 = 0;
        for ( j = SendMessageA(a2, 0x18Au, 0, (LPARAM)lParam); j != -1; j = SendMessageA(
                                                                              a2,
                                                                              0x18Au,
                                                                              v21,
                                                                              (LPARAM)lParam) )
        {
          if ( j >= 0x200 )
            break;
          if ( SendMessageA(a2, 0x189u, v12, (LPARAM)lParam) == -1 )
            break;
          if ( lstrcmpiA(FindFileData.cFileName, lParam) < 0 )
            break;
          v12 = ++v21;
        }
        v23 = v21;
        SendMessageA(a2, 0x181u, v21, (LPARAM)FindFileData.cFileName);
        v24 = -1;
        do
          ++v24;
        while ( Src[v24] );
        v25 = v24 + 1;
        v26 = malloc(v24 + 1);
        v27 = (LPARAM)v26;
        if ( v26 )
        {
          memcpy_0(v26, Src, v25);
          SendMessageA(a2, 0x19Au, v23, v27);
        }
        v28 = -1;
        v12 = 0;
        do
          ++v28;
        while ( FindFileData.cFileName[v28] );
        GetTextExtentPoint32A(v18, FindFileData.cFileName, v28, &psizl);
        if ( psizl.cx > cx )
          cx = psizl.cx;
      }
      NextFileA = FindNextFileA(FirstFileA, &FindFileData);
    }
    v13 = v52;
    v5 = v53;
    v47 = cx;
    v10 = v54;
  }
  *v13 = 0;
  v29 = 0;
  v30 = -1;
  do
    ++v30;
  while ( v10[v30] );
  OemToCharBuffA(v10, szDst, v30 + 1);
  v31 = szDst;
  v32 = 0;
  v33 = (LPARAM *)v57;
  while ( 1 )
  {
    v34 = *v31;
    if ( !*v31 )
      break;
    if ( v29 == 1 )
    {
      v35 = -1;
      do
        ++v35;
      while ( v57[v35] );
      v10 += v35;
      if ( *v10 == 92 )
      {
        v36 = CharNextA(v10);
        v34 = *v31;
        v10 = v36;
      }
      v29 = 0;
    }
    if ( v34 == 92 )
    {
      if ( !v32 )
      {
        *(_BYTE *)v33 = 92;
        v33 = (LPARAM *)((char *)v33 + 1);
      }
      if ( v33 == (LPARAM *)v57 )
      {
        v57[0] = 0;
      }
      else
      {
        *(_BYTE *)v33 = 0;
        SendMessageA(a2, 0x181u, v32, (LPARAM)v57);
        v37 = -1;
        do
          ++v37;
        while ( v57[v37] );
        v38 = v37 + 1;
        v39 = malloc(v37 + 1);
        v40 = v39;
        if ( v39 )
        {
          memset_0(v39, 0, v38);
          v41 = -1;
          do
            ++v41;
          while ( v57[v41] );
          memcpy_0(v40, v10, v41);
          SendMessageA(a2, 0x19Au, v32, (LPARAM)v40);
        }
        v42 = -1;
        do
          ++v42;
        while ( v57[v42] );
        GetTextExtentPoint32A(hdc, v57, v42, &psizl);
        v5 = v53;
        v33 = (LPARAM *)v57;
        v43 = v48;
        if ( v32 * (*((_DWORD *)v53 + 290) / 2) + psizl.cx + 17 > v48 )
          v43 = v32 * (*((_DWORD *)v53 + 290) / 2) + psizl.cx + 17;
        ++v32;
        v48 = v43;
      }
      v29 = 1;
    }
    else
    {
      if ( IsDBCSLeadByte(v34) )
      {
        v44 = *v31++;
        *(_BYTE *)v33 = v44;
        v33 = (LPARAM *)((char *)v33 + 1);
      }
      *(_BYTE *)v33 = *v31;
      v33 = (LPARAM *)((char *)v33 + 1);
    }
    ++v31;
  }
  v45 = v48;
  if ( v48 <= v32 * (*((_DWORD *)v5 + 290) / 2) + v47 + 17 )
    v45 = v32 * (*((_DWORD *)v5 + 290) / 2) + v47 + 17;
  SendMessageA(a2, 0x194u, v45, 0);
  ShowScrollBar(a2, 0, Rect.right - Rect.left <= v45);
  v46 = v32 - 1;
  *(_DWORD *)v5 = v46;
  SendMessageA(a2, 0x186u, v46, 0);
  SendMessageA(a2, 0xBu, 1u, 0);
  InvalidateRect(a2, 0, 1);
  ReleaseDC(a2, hdc);
  if ( v50 )
    SetFileApisToANSI();
}

```

## disassembly

```asm
0x180049ddc  mov     [rsp-8+arg_18], rbx
0x180049de1  push    rbp
0x180049de2  push    rsi
0x180049de3  push    rdi
0x180049de4  push    r12
0x180049de6  push    r13
0x180049de8  push    r14
0x180049dea  push    r15
0x180049dec  lea     rbp, [rsp-8C0h]
0x180049df4  sub     rsp, 9C0h
0x180049dfb  mov     rax, cs:__security_cookie
0x180049e02  xor     rax, rsp
0x180049e05  mov     [rbp+8F0h+var_40], rax
0x180049e0c  mov     r14, r8
0x180049e0f  mov     [rsp+9F0h+var_9A8], rcx
0x180049e14  mov     rdi, rdx
0x180049e17  mov     r12, rcx
0x180049e1a  xor     edx, edx; Val
0x180049e1c  lea     rcx, [rsp+9F0h+FindFileData]; void *
0x180049e21  mov     r8d, 140h; Size
0x180049e27  call    memset_0
0x180049e2c  xor     r15d, r15d
0x180049e2f  xorps   xmm0, xmm0
0x180049e32  mov     rcx, rdi; hWnd
0x180049e35  mov     [rsp+9F0h+var_9D0], r15d
0x180049e3a  movups  xmmword ptr [rsp+9F0h+Rect.left], xmm0
0x180049e3f  mov     [rsp+9F0h+var_9CC], r15d
0x180049e44  mov     qword ptr [rsp+9F0h+psizl.cx], r15
0x180049e49  call    cs:__imp_GetDC
0x180049e4f  lea     rdx, [rsp+9F0h+Rect]; lpRect
0x180049e54  mov     rcx, rdi; hWnd
0x180049e57  mov     [rsp+9F0h+hdc], rax
0x180049e5c  call    cs:__imp_GetWindowRect
0x180049e62  xor     r9d, r9d; lParam
0x180049e65  lea     edx, [r15+0Bh]; Msg
0x180049e69  xor     r8d, r8d; wParam
0x180049e6c  mov     rcx, rdi; hWnd
0x180049e6f  call    cs:__imp_SendMessageA
0x180049e75  xor     r9d, r9d; lParam
0x180049e78  xor     r8d, r8d; wParam
0x180049e7b  mov     edx, 18Bh; Msg
0x180049e80  mov     rcx, rdi; hWnd
0x180049e83  call    cs:__imp_SendMessageA
0x180049e89  mov     rsi, rax
0x180049e8c  mov     ebx, r15d
0x180049e8f  test    eax, eax
0x180049e91  jle     short loc_180049EBB
0x180049e93  mov     r8d, ebx; wParam
0x180049e96  xor     r9d, r9d; lParam
0x180049e99  mov     edx, 199h; Msg
0x180049e9e  mov     rcx, rdi; hWnd
0x180049ea1  call    cs:__imp_SendMessageA
0x180049ea7  test    rax, rax
0x180049eaa  jz      short loc_180049EB5
0x180049eac  mov     rcx, rax; Block
0x180049eaf  call    cs:__imp_free
0x180049eb5  inc     ebx
0x180049eb7  cmp     ebx, esi
0x180049eb9  jl      short loc_180049E93
0x180049ebb  xor     r9d, r9d; lParam
0x180049ebe  xor     r8d, r8d; wParam
0x180049ec1  mov     edx, 184h; Msg
0x180049ec6  mov     rcx, rdi; hWnd
0x180049ec9  call    cs:__imp_SendMessageA
0x180049ecf  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180049ed3  mov     r8, rsi
0x180049ed6  inc     r8
0x180049ed9  cmp     [r12+r8+6Ch], r15b
0x180049ede  jnz     short loc_180049ED6
0x180049ee0  inc     r8d; cchDstLength
0x180049ee3  lea     rdx, [rbp+8F0h+szDst]; lpszDst
0x180049eea  lea     rcx, [r12+6Ch]; lpszSrc
0x180049eef  call    cs:__imp_OemToCharBuffA
0x180049ef5  lea     rdx, [rbp+8F0h+szDst]; lpString
0x180049efc  mov     rcx, r14; hWnd
0x180049eff  call    cs:__imp_SetWindowTextA
0x180049f05  lea     r15, [r12+26Ch]
0x180049f0d  mov     edx, 200h; unsigned __int64
0x180049f12  mov     rcx, r15; char *
0x180049f15  mov     [rsp+9F0h+var_9A0], r15
0x180049f1a  lea     r8, [r12+6Ch]; char *
0x180049f1f  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x180049f24  call    cs:__imp_AreFileApisANSI
0x180049f2a  mov     [rsp+9F0h+var_9C0], eax
0x180049f2e  call    cs:__imp_SetFileApisToOEM
0x180049f34  mov     rcx, rsi
0x180049f37  xor     ebx, ebx
0x180049f39  inc     rcx
0x180049f3c  cmp     [r15+rcx], bl
0x180049f40  jnz     short loc_180049F39
0x180049f42  lea     rsi, [r12+26Ch]
0x180049f4a  add     rsi, rcx
0x180049f4d  mov     rcx, r15; lpszStart
0x180049f50  mov     rdx, rsi; lpszCurrent
0x180049f53  mov     [rsp+9F0h+var_9B0], rsi
0x180049f58  call    cs:__imp_CharPrevA
0x180049f5e  cmp     byte ptr [rax], 5Ch ; '\'
0x180049f61  jz      short loc_180049F79
0x180049f63  mov     rcx, rsi; lpsz
0x180049f66  mov     byte ptr [rsi], 5Ch ; '\'
0x180049f69  call    cs:__imp_CharNextA
0x180049f6f  mov     rsi, rax
0x180049f72  mov     [rsp+9F0h+var_9B0], rax
0x180049f77  mov     [rax], bl
0x180049f79  mov     rcx, r15; char *
0x180049f7c  call    ?StringCbCatA@@YAJPEAD_KPEBD@Z; StringCbCatA(char *,unsigned __int64,char const *)
0x180049f81  lea     rdx, [rsp+9F0h+FindFileData]; lpFindFileData
0x180049f86  mov     rcx, r15; lpFileName
0x180049f89  call    cs:__imp_FindFirstFileA
0x180049f8f  mov     r13, rax
0x180049f92  mov     eax, 1
0x180049f97  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x180049f9b  jz      loc_18004A147
0x180049fa1  mov     rsi, [rsp+9F0h+hdc]
0x180049fa6  mov     r15d, ebx
0x180049fa9  test    eax, eax
0x180049fab  jz      loc_18004A133
0x180049fb1  test    byte ptr [rsp+9F0h+FindFileData.dwFileAttributes], 10h
0x180049fb6  jz      loc_18004A120
0x180049fbc  cmp     [rbp+8F0h+FindFileData.cFileName], 2Eh ; '.'
0x180049fc0  jz      loc_18004A120
0x180049fc6  lea     r8, [rbp+8F0h+FindFileData.cFileName]; char *
0x180049fca  mov     edx, 200h; unsigned __int64
0x180049fcf  lea     rcx, [rbp+8F0h+Src]; char *
0x180049fd6  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180049fdb  or      r12, 0FFFFFFFFFFFFFFFFh
0x180049fdf  lea     r10, [rbp+8F0h+FindFileData.cFileName]
0x180049fe3  mov     r8, r12
0x180049fe6  inc     r8
0x180049fe9  cmp     [r10+r8], bl
0x180049fed  jnz     short loc_180049FE6
0x180049fef  inc     r8d; cchDstLength
0x180049ff2  lea     rdx, [rbp+8F0h+FindFileData.cFileName]; lpszDst
0x180049ff6  lea     rcx, [rbp+8F0h+FindFileData.cFileName]; lpszSrc
0x180049ffa  call    cs:__imp_OemToCharBuffA
0x18004a000  lea     rcx, [rbp+8F0h+FindFileData.cFileName]; lpsz
0x18004a004  call    cs:__imp_CharLowerA
0x18004a00a  lea     r9, [rbp+8F0h+lParam]; lParam
0x18004a011  xor     r8d, r8d; wParam
0x18004a014  mov     edx, 18Ah; Msg
0x18004a019  mov     rcx, rdi; hWnd
0x18004a01c  mov     r14d, ebx
0x18004a01f  call    cs:__imp_SendMessageA
0x18004a025  cmp     eax, r12d
0x18004a028  jz      short loc_18004A08A
0x18004a02a  cmp     eax, 200h
0x18004a02f  jnb     short loc_18004A088
0x18004a031  lea     r9, [rbp+8F0h+lParam]; lParam
0x18004a038  mov     r8, rbx; wParam
0x18004a03b  mov     edx, 189h; Msg
0x18004a040  mov     rcx, rdi; hWnd
0x18004a043  call    cs:__imp_SendMessageA
0x18004a049  cmp     rax, r12
0x18004a04c  jz      short loc_18004A088
0x18004a04e  lea     rdx, [rbp+8F0h+lParam]; lpString2
0x18004a055  lea     rcx, [rbp+8F0h+FindFileData.cFileName]; lpString1
0x18004a059  call    cs:__imp_lstrcmpiA
0x18004a05f  xor     ebx, ebx
0x18004a061  test    eax, eax
0x18004a063  js      short loc_18004A08A
0x18004a065  inc     r14d
0x18004a068  lea     r9, [rbp+8F0h+lParam]; lParam
0x18004a06f  movsxd  rbx, r14d
0x18004a072  mov     edx, 18Ah; Msg
0x18004a077  mov     r8, rbx; wParam
0x18004a07a  mov     rcx, rdi; hWnd
0x18004a07d  call    cs:__imp_SendMessageA
0x18004a083  cmp     eax, r12d
0x18004a086  jnz     short loc_18004A02A
0x18004a088  xor     ebx, ebx
0x18004a08a  movsxd  r12, r14d
0x18004a08d  lea     r9, [rbp+8F0h+FindFileData.cFileName]; lParam
0x18004a091  mov     r8, r12; wParam
0x18004a094  mov     edx, 181h; Msg
0x18004a099  mov     rcx, rdi; hWnd
0x18004a09c  call    cs:__imp_SendMessageA
0x18004a0a2  lea     rcx, [rbp+8F0h+Src]
0x18004a0a9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004a0ad  inc     rax
0x18004a0b0  cmp     [rcx+rax], bl
0x18004a0b3  jnz     short loc_18004A0AD
0x18004a0b5  lea     r14, [rax+1]
0x18004a0b9  mov     rcx, r14; Size
0x18004a0bc  call    cs:__imp_malloc
0x18004a0c2  mov     rbx, rax
0x18004a0c5  test    rax, rax
0x18004a0c8  jz      short loc_18004A0F0
0x18004a0ca  mov     r8, r14; Size
0x18004a0cd  lea     rdx, [rbp+8F0h+Src]; Src
0x18004a0d4  mov     rcx, rax; void *
0x18004a0d7  call    memcpy_0
0x18004a0dc  mov     r9, rbx; lParam
0x18004a0df  mov     r8, r12; wParam
0x18004a0e2  mov     edx, 19Ah; Msg
0x18004a0e7  mov     rcx, rdi; hWnd
0x18004a0ea  call    cs:__imp_SendMessageA
0x18004a0f0  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004a0f4  lea     rax, [rbp+8F0h+FindFileData.cFileName]
0x18004a0f8  xor     ebx, ebx
0x18004a0fa  inc     r8; c
0x18004a0fd  cmp     [rax+r8], bl
0x18004a101  jnz     short loc_18004A0FA
0x18004a103  lea     r9, [rsp+9F0h+psizl]; psizl
0x18004a108  mov     rcx, rsi; hdc
0x18004a10b  lea     rdx, [rbp+8F0h+FindFileData.cFileName]; lpString
0x18004a10f  call    cs:__imp_GetTextExtentPoint32A
0x18004a115  cmp     [rsp+9F0h+psizl.cx], r15d
0x18004a11a  cmovg   r15d, [rsp+9F0h+psizl.cx]
0x18004a120  lea     rdx, [rsp+9F0h+FindFileData]; lpFindFileData
0x18004a125  mov     rcx, r13; hFindFile
0x18004a128  call    cs:__imp_FindNextFileA
0x18004a12e  jmp     loc_180049FA9
0x18004a133  mov     rsi, [rsp+9F0h+var_9B0]
0x18004a138  mov     r12, [rsp+9F0h+var_9A8]
0x18004a13d  mov     [rsp+9F0h+var_9D0], r15d
0x18004a142  mov     r15, [rsp+9F0h+var_9A0]
0x18004a147  mov     [rsi], bl
0x18004a149  mov     r14d, ebx
0x18004a14c  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004a150  inc     r8
0x18004a153  cmp     [r15+r8], bl
0x18004a157  jnz     short loc_18004A150
0x18004a159  inc     r8d; cchDstLength
0x18004a15c  lea     rdx, [rbp+8F0h+szDst]; lpszDst
0x18004a163  mov     rcx, r15; lpszSrc
0x18004a166  call    cs:__imp_OemToCharBuffA
0x18004a16c  xor     edx, edx
0x18004a16e  lea     rsi, [rbp+8F0h+szDst]
0x18004a175  mov     r13d, ebx
0x18004a178  lea     rbx, [rbp+8F0h+var_840]
0x18004a17f  lea     r8d, [rdx+1]
0x18004a183  mov     cl, [rsi]
0x18004a185  test    cl, cl
0x18004a187  jz      loc_18004A319
0x18004a18d  cmp     r14d, r8d
0x18004a190  jnz     short loc_18004A1C6
0x18004a192  lea     r9, [rbp+8F0h+var_840]
0x18004a199  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004a19d  inc     rax
0x18004a1a0  cmp     [r9+rax], dl
0x18004a1a4  jnz     short loc_18004A19D
0x18004a1a6  add     r15, rax
0x18004a1a9  cmp     byte ptr [r15], 5Ch ; '\'
0x18004a1ad  jnz     short loc_18004A1C3
0x18004a1af  mov     rcx, r15; lpsz
0x18004a1b2  call    cs:__imp_CharNextA
0x18004a1b8  mov     cl, [rsi]; TestChar
0x18004a1ba  xor     edx, edx
0x18004a1bc  mov     r15, rax
0x18004a1bf  lea     r8d, [rdx+1]
0x18004a1c3  mov     r14d, edx
0x18004a1c6  cmp     cl, 5Ch ; '\'
0x18004a1c9  jnz     loc_18004A2F0
0x18004a1cf  test    r13w, r13w
0x18004a1d3  jnz     short loc_18004A1DA
0x18004a1d5  mov     [rbx], cl
0x18004a1d7  add     rbx, r8
0x18004a1da  lea     rax, [rbp+8F0h+var_840]
0x18004a1e1  cmp     rbx, rax
0x18004a1e4  jz      loc_18004A2E5
0x18004a1ea  mov     [rbx], dl
0x18004a1ec  lea     r9, [rbp+8F0h+var_840]; lParam
0x18004a1f3  movzx   r12d, r13w
0x18004a1f7  mov     edx, 181h; Msg
0x18004a1fc  mov     r8d, r12d; wParam
0x18004a1ff  mov     rcx, rdi; hWnd
0x18004a202  call    cs:__imp_SendMessageA
0x18004a208  lea     rcx, [rbp+8F0h+var_840]
0x18004a20f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004a213  inc     rax
0x18004a216  cmp     byte ptr [rcx+rax], 0
0x18004a21a  jnz     short loc_18004A213
0x18004a21c  lea     r14, [rax+1]
0x18004a220  mov     rcx, r14; Size
0x18004a223  call    cs:__imp_malloc
0x18004a229  mov     rbx, rax
0x18004a22c  test    rax, rax
0x18004a22f  jz      short loc_18004A272
0x18004a231  mov     r8, r14; Size
0x18004a234  xor     edx, edx; Val
0x18004a236  mov     rcx, rax; void *
0x18004a239  call    memset_0
0x18004a23e  lea     rax, [rbp+8F0h+var_840]
0x18004a245  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004a249  inc     r8; Size
0x18004a24c  cmp     byte ptr [rax+r8], 0
0x18004a251  jnz     short loc_18004A249
0x18004a253  mov     rdx, r15; Src
0x18004a256  mov     rcx, rbx; void *
0x18004a259  call    memcpy_0
0x18004a25e  mov     r9, rbx; lParam
0x18004a261  mov     r8, r12; wParam
0x18004a264  mov     edx, 19Ah; Msg
0x18004a269  mov     rcx, rdi; hWnd
0x18004a26c  call    cs:__imp_SendMessageA
0x18004a272  lea     rax, [rbp+8F0h+var_840]
0x18004a279  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004a27d  inc     r8; c
0x18004a280  cmp     byte ptr [rax+r8], 0
0x18004a285  jnz     short loc_18004A27D
  ... truncated ...
```
