# CSiteMap::CreateFavorites(int)

- ea: `0x180055060`
- end: `0x1800558f6`
- name: `?CreateFavorites@CSiteMap@@QEAAXH@Z`
- size: `2198`
- prototype: `void __fastcall(CSiteMap *__hidden this, int)`
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x180056b00`

## callees

- `0x1800029b8`
- `0x1800095c8`
- `0x180013b20`
- `0x180025d84`
- `0x180025fa4`
- `0x180025ff4`
- `0x1800261f0`
- `0x1800262c0`
- `0x180026424`
- `0x180042da8`
- `0x18004f794`
- `0x180054140`
- `0x180054e80`
- `0x180055060`
- `0x180065d30`
- `0x1800675c0`
- `0x18006a7ac`
- `0x180075c5a`
- `0x180075c90`

## import_xrefs

- `msvcrt!realloc` at `0x18005521e`
- `msvcrt!realloc` at `0x18005521e`
- `msvcrt!free` at `0x18005522f`
- `msvcrt!free` at `0x180055872`
- `msvcrt!free` at `0x18005587f`
- `msvcrt!free` at `0x180055894`
- `msvcrt!free` at `0x1800558cd`
- `msvcrt!free` at `0x18005522f`
- `msvcrt!free` at `0x180055872`
- `msvcrt!free` at `0x18005587f`
- `msvcrt!free` at `0x180055894`
- `msvcrt!free` at `0x1800558cd`
- `KERNEL32!VirtualAlloc` at `0x1800552f4`
- `KERNEL32!VirtualAlloc` at `0x1800553b1`
- `KERNEL32!VirtualAlloc` at `0x1800552f4`
- `KERNEL32!VirtualAlloc` at `0x1800553b1`
- `KERNEL32!GetPrivateProfileStringA` at `0x180055734`
- `KERNEL32!GetPrivateProfileStringA` at `0x180055734`
- `KERNEL32!FindFirstFileA` at `0x1800552ac`
- `KERNEL32!FindFirstFileA` at `0x1800552ac`
- `KERNEL32!FindNextFileA` at `0x18005544c`
- `KERNEL32!FindNextFileA` at `0x18005544c`
- `KERNEL32!FindClose` at `0x18005545d`
- `KERNEL32!FindClose` at `0x18005545d`
- `USER32!CharPrevA` at `0x18005517e`
- `USER32!CharPrevA` at `0x180055193`
- `USER32!CharPrevA` at `0x1800551a8`
- `USER32!CharPrevA` at `0x180055665`
- `USER32!CharPrevA` at `0x18005567a`
- `USER32!CharPrevA` at `0x18005568f`
- `USER32!CharPrevA` at `0x18005517e`
- `USER32!CharPrevA` at `0x180055193`
- `USER32!CharPrevA` at `0x1800551a8`
- `USER32!CharPrevA` at `0x180055665`
- `USER32!CharPrevA` at `0x18005567a`
- `USER32!CharPrevA` at `0x18005568f`
- `SHELL32!SHGetPathFromIDListW` at `0x1800550e6`
- `SHELL32!SHGetPathFromIDListW` at `0x1800550e6`
- `SHELL32!SHGetSpecialFolderLocation` at `0x1800550cc`
- `SHELL32!SHGetSpecialFolderLocation` at `0x1800550cc`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CSiteMap::CreateFavorites(CSiteMap *this)
{
  char *v2; // r14
  __int64 v3; // rcx
  __int64 v4; // r8
  CHAR *v5; // rbx
  CHAR *v6; // rdx
  unsigned __int64 v7; // rax
  char *v8; // rbx
  __int64 v9; // rax
  size_t v10; // rdi
  char *v11; // rax
  CHAR *v12; // r12
  HANDLE FirstFileA; // rbx
  __int64 v14; // rdx
  char *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rdx
  char *v18; // rax
  __int64 v19; // rdx
  const char *StringResource; // rax
  char *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  int v24; // r15d
  int v25; // ecx
  unsigned int v26; // eax
  int v27; // ebx
  int v28; // ecx
  unsigned int v29; // eax
  char v30; // r13
  __int64 v31; // rax
  CHAR *v32; // r8
  __int64 v33; // rdx
  CHAR *v34; // rcx
  CHAR v35; // r9
  CHAR *v36; // rax
  __int64 v37; // rcx
  CHAR *v38; // rbx
  CHAR *v39; // rdx
  unsigned __int64 v40; // rax
  __int64 v41; // r8
  __int64 v42; // rdx
  const char *v43; // rcx
  char *v44; // rbx
  _BYTE *v45; // rax
  int v46; // edi
  int v47; // ecx
  char *v48; // rax
  __int64 v49; // rdx
  __int64 v50; // rcx
  void *v51; // rcx
  LPITEMIDLIST ppidl; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v53; // [rsp+38h] [rbp-C8h]
  __int128 v54; // [rsp+48h] [rbp-B8h]
  _QWORD v55[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v56; // [rsp+70h] [rbp-90h]
  int v57; // [rsp+78h] [rbp-88h]
  int v58; // [rsp+7Ch] [rbp-84h]
  int v59; // [rsp+80h] [rbp-80h]
  int v60; // [rsp+84h] [rbp-7Ch]
  int v61; // [rsp+94h] [rbp-6Ch]
  unsigned int v62; // [rsp+9Ch] [rbp-64h]
  int v63; // [rsp+A0h] [rbp-60h]
  int v64; // [rsp+A8h] [rbp-58h]
  int v65; // [rsp+ACh] [rbp-54h]
  _QWORD v66[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v67; // [rsp+E0h] [rbp-20h]
  int v68; // [rsp+E8h] [rbp-18h]
  int v69; // [rsp+ECh] [rbp-14h]
  int v70; // [rsp+F0h] [rbp-10h]
  int v71; // [rsp+F4h] [rbp-Ch]
  int v72; // [rsp+104h] [rbp+4h]
  unsigned int v73; // [rsp+10Ch] [rbp+Ch]
  int v74; // [rsp+110h] [rbp+10h]
  int v75; // [rsp+118h] [rbp+18h]
  int v76; // [rsp+11Ch] [rbp+1Ch]
  char *v77; // [rsp+140h] [rbp+40h]
  char *v78; // [rsp+148h] [rbp+48h]
  int v79; // [rsp+154h] [rbp+54h]
  char *v80; // [rsp+158h] [rbp+58h]
  struct _WIN32_FIND_DATAA FindFileData; // [rsp+160h] [rbp+60h] BYREF
  CHAR szStart[272]; // [rsp+2A0h] [rbp+1A0h] BYREF
  CHAR FileName[272]; // [rsp+3B0h] [rbp+2B0h] BYREF
  WCHAR pszPath[264]; // [rsp+4C0h] [rbp+3C0h] BYREF
  CHAR ReturnedString[1040]; // [rsp+6D0h] [rbp+5D0h] BYREF

  v2 = 0;
  ppidl = 0;
  memset_0(szStart, 0, 0x104u);
  memset_0(pszPath, 0, 0x208u);
  if ( SHGetSpecialFolderLocation(0, 6, &ppidl) >= 0
    && SHGetPathFromIDListW(ppidl, pszPath)
    && pszPath[0]
    && ConvertPathToAnsiWithNoBestFitMatching(pszPath, szStart, 0x104u)
    && szStart[0] )
  {
    v3 = -1;
    do
      ++v3;
    while ( szStart[v3] );
    v4 = 0x200000000801LL;
    if ( (unsigned __int64)(v3 + 1) < 0x104 )
    {
      if ( g_fDBCSSystem )
      {
        v5 = &szStart[v3];
        if ( *CharPrevA(szStart, &szStart[v3]) != 92 && *CharPrevA(szStart, v5) != 47 && *CharPrevA(szStart, v5) != 58 )
          *(_WORD *)v5 = 92;
      }
      else
      {
        v6 = &szStart[(int)v3];
        v7 = (unsigned __int8)*(v6 - 1);
        LOBYTE(v7) = v7 - 47;
        if ( (unsigned __int8)v7 > 0x2Du || !_bittest64(&v4, v7) )
        {
          *v6 = 92;
          szStart[(int)v3 + 1] = 0;
        }
      }
    }
    v8 = lcStrDup(szStart);
    if ( !v8 )
      OOM();
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    v10 = (int)v9 + 4;
    v11 = (char *)realloc(v8, v10);
    v12 = v11;
    if ( !v11 )
    {
      free(v8);
      OOM();
    }
    v80 = v11;
    StringCchCatA(v11, v10, "*.*");
    v66[0] = &CTable::`vftable';
    v68 = 20967424;
    v69 = 0x100000;
    CTable::InitializeTable((CTable *)v66);
    v55[0] = &CTable::`vftable';
    v57 = 20967424;
    v58 = 0x100000;
    CTable::InitializeTable((CTable *)v55);
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    FirstFileA = FindFirstFileA(v12, &FindFileData);
    if ( FirstFileA != (HANDLE)-1LL )
    {
      do
      {
        if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
        {
          if ( FindFileData.cFileName[0] != 46 )
          {
            if ( v70 < v71 )
              goto LABEL_29;
            if ( !VirtualAlloc((LPVOID)(v67 + v72), 0x1000u, 0x1000u, 4u) )
              goto LABEL_81;
            v72 += 4096;
            v71 = (unsigned __int64)v72 >> 3;
            if ( v70 < v71 )
            {
LABEL_29:
              v14 = -1;
              do
                ++v14;
              while ( FindFileData.cFileName[v14] );
              v15 = CTable::TableMalloc((CTable *)v66, (int)v14 + 1);
              *(_QWORD *)(v67 + 8LL * v70) = v15;
              if ( v15 )
              {
                v16 = -1;
                do
                  ++v16;
                while ( FindFileData.cFileName[v16] );
                StringCchCopyA(*(char **)(v67 + 8LL * v70++), v16 + 1, FindFileData.cFileName);
              }
            }
          }
        }
        else
        {
          if ( v59 < v60 )
            goto LABEL_38;
          if ( !VirtualAlloc((LPVOID)(v56 + v61), 0x1000u, 0x1000u, 4u) )
LABEL_81:
            OOM();
          v61 += 4096;
          v60 = (unsigned __int64)v61 >> 3;
          if ( v59 < v60 )
          {
LABEL_38:
            v17 = -1;
            do
              ++v17;
            while ( FindFileData.cFileName[v17] );
            v18 = CTable::TableMalloc((CTable *)v55, (int)v17 + 1);
            *(_QWORD *)(v56 + 8LL * v59) = v18;
            if ( v18 )
            {
              v19 = -1;
              do
                ++v19;
              while ( FindFileData.cFileName[v19] );
              StringCchCopyA(*(char **)(v56 + 8LL * v59++), v19 + 1, FindFileData.cFileName);
            }
          }
        }
      }
      while ( FindNextFileA(FirstFileA, &FindFileData) );
      FindClose(FirstFileA);
    }
    if ( v70 != 1 || v59 != 1 )
    {
      v53 = 0;
      v54 = 0;
      BYTE9(v54) = 1;
      StringResource = GetStringResource(0x40Eu);
      *((_QWORD *)&v53 + 1) = CTable::StrDupA(this, StringResource);
      if ( *((_DWORD *)this + 8) >= *((_DWORD *)this + 9) )
        CTable::IncreaseTableBuffer(this);
      if ( *((_DWORD *)this + 8) < *((_DWORD *)this + 9) )
      {
        v21 = CTable::TableMalloc(this, 40);
        *(_QWORD *)(*((_QWORD *)this + 2) + 8LL * *((int *)this + 8)) = v21;
        if ( v21 )
        {
          v22 = *(_QWORD *)(*((_QWORD *)this + 2) + 8LL * *((int *)this + 8));
          *(_OWORD *)v22 = v53;
          *(_OWORD *)(v22 + 16) = v54;
          *(_QWORD *)(v22 + 32) = 0;
          v23 = *((int *)this + 8);
          *((_DWORD *)this + 8) = v23 + 1;
          if ( (_DWORD)v23 )
            **(_QWORD **)(*((_QWORD *)this + 2) + 8 * v23) = this;
        }
      }
      v24 = 1;
      v25 = v70;
      if ( v70 >= 3 )
      {
        v76 = 0;
        v26 = v73;
        if ( !v73 )
          v26 = g_lcidSystem;
        v73 = v26;
        v75 = v74 | 1;
        CTable::doLcidSort((CTable *)v66, 1, v70 - 1);
        v25 = v70;
      }
      v27 = 1;
      if ( v25 - 1 >= 1 )
      {
        do
          CSiteMap::AddFavoriteNodes(this, szStart, *(const char **)(v67 + 8LL * v27++), 2);
        while ( v27 <= v70 - 1 );
      }
      v28 = v59;
      if ( v59 >= 3 )
      {
        v65 = 0;
        v29 = v62;
        if ( !v62 )
          v29 = g_lcidSystem;
        v62 = v29;
        v64 = v63 | 1;
        CTable::doLcidSort((CTable *)v55, 1, v59 - 1);
        v28 = v59;
      }
      v30 = BYTE11(v54);
      while ( v24 <= v28 - 1 )
      {
        v31 = 2147483646;
        v32 = szStart;
        v33 = 260;
        v34 = FileName;
        do
        {
          if ( !v31 )
            break;
          v35 = *v32;
          if ( !*v32 )
            break;
          ++v32;
          *v34++ = v35;
          --v31;
          --v33;
        }
        while ( v33 );
        v36 = v34 - 1;
        if ( v33 )
          v36 = v34;
        *v36 = 0;
        v37 = -1;
        do
          ++v37;
        while ( FileName[v37] );
        if ( FileName[0] && (unsigned __int64)(v37 + 1) < 0x104 )
        {
          if ( g_fDBCSSystem )
          {
            v38 = &FileName[v37];
            if ( *CharPrevA(FileName, &FileName[v37]) != 92
              && *CharPrevA(FileName, v38) != 47
              && *CharPrevA(FileName, v38) != 58 )
            {
              *(_WORD *)v38 = 92;
            }
          }
          else
          {
            v39 = &FileName[(int)v37];
            v40 = (unsigned __int8)*(v39 - 1);
            LOBYTE(v40) = v40 - 47;
            if ( (unsigned __int8)v40 > 0x2Du || (v41 = 0x200000000801LL, !_bittest64(&v41, v40)) )
            {
              *v39 = 92;
              FileName[(int)v37 + 1] = 0;
            }
          }
        }
        StringCchCatA(FileName, 0x104u, *(const char **)(v56 + 8LL * v24));
        if ( GetPrivateProfileStringA("InternetShortcut", "URL", Class, ReturnedString, 0x410u, FileName)
          && ReturnedString[0] )
        {
          v43 = *(const char **)(v56 + 8LL * v24);
          if ( v43 )
          {
            v44 = lcStrDup(v43);
            v77 = v44;
            if ( !v44 )
              OOM();
          }
          else
          {
            v44 = v2;
            v77 = v2;
          }
          LOBYTE(v42) = 46;
          v45 = (_BYTE *)StrRChr(v44, v42);
          if ( v45 )
          {
            *v45 = 0;
            BYTE9(v54) = 2;
            *((_QWORD *)&v53 + 1) = CTable::StrDupA(this, v44);
            v46 = 4 * *((_DWORD *)this + 39);
            v2 = (char *)lcCalloc(32);
            v78 = v2;
            v47 = 4;
            if ( v46 )
              v47 = v46;
            *((_QWORD *)v2 + 3) = lcCalloc(v47);
            v79 = 0;
            *((_QWORD *)v2 + 1) = CSiteMap::AddUrl(this, ReturnedString);
            v30 |= 1u;
            BYTE11(v54) = v30;
            if ( *((_DWORD *)this + 8) >= *((_DWORD *)this + 9) )
              CTable::IncreaseTableBuffer(this);
            if ( *((_DWORD *)this + 8) < *((_DWORD *)this + 9) )
            {
              v48 = CTable::TableMalloc(this, 40);
              *(_QWORD *)(*((_QWORD *)this + 2) + 8LL * *((int *)this + 8)) = v48;
              if ( v48 )
              {
                v49 = *(_QWORD *)(*((_QWORD *)this + 2) + 8LL * *((int *)this + 8));
                *(_OWORD *)v49 = v53;
                *(_OWORD *)(v49 + 16) = v54;
                *(_QWORD *)(v49 + 32) = v2;
                v50 = *((int *)this + 8);
                *((_DWORD *)this + 8) = v50 + 1;
                if ( (_DWORD)v50 )
                  **(_QWORD **)(*((_QWORD *)this + 2) + 8 * v50) = this;
              }
            }
            if ( v2 )
            {
              v51 = (void *)*((_QWORD *)v2 + 3);
              if ( v51 )
              {
                free(v51);
                *((_QWORD *)v2 + 3) = 0;
              }
              free(v2);
              v2 = 0;
              v78 = 0;
            }
          }
          if ( v44 )
            free(v44);
        }
        ++v24;
        v28 = v59;
      }
    }
    v55[0] = &CTable::`vftable';
    CTable::Cleanup((CTable *)v55);
    v66[0] = &CTable::`vftable';
    CTable::Cleanup((CTable *)v66);
    free(v12);
  }
}

```

## disassembly

```asm
0x180055060  push    rbp
0x180055062  push    rbx
0x180055063  push    rsi
0x180055064  push    rdi
0x180055065  push    r12
0x180055067  push    r13
0x180055069  push    r14
0x18005506b  push    r15
0x18005506d  lea     rbp, [rsp-9F8h]
0x180055075  sub     rsp, 0AF8h
0x18005507c  mov     rax, cs:__security_cookie
0x180055083  xor     rax, rsp
0x180055086  mov     [rbp+0A30h+var_50], rax
0x18005508d  mov     rsi, rcx
0x180055090  xor     r14d, r14d
0x180055093  mov     [rsp+0B30h+ppidl], r14
0x180055098  xor     edx, edx; Val
0x18005509a  mov     r8d, 104h; Size
0x1800550a0  lea     rcx, [rbp+0A30h+szStart]; void *
0x1800550a7  call    memset_0
0x1800550ac  xor     edx, edx; Val
0x1800550ae  mov     r8d, 208h; Size
0x1800550b4  lea     rcx, [rbp+0A30h+pszPath]; void *
0x1800550bb  call    memset_0
0x1800550c0  lea     r8, [rsp+0B30h+ppidl]; ppidl
0x1800550c5  mov     edx, 6; csidl
0x1800550ca  xor     ecx, ecx; hwnd
0x1800550cc  call    cs:__imp_SHGetSpecialFolderLocation
0x1800550d2  test    eax, eax
0x1800550d4  js      loc_1800558D3
0x1800550da  lea     rdx, [rbp+0A30h+pszPath]; pszPath
0x1800550e1  mov     rcx, [rsp+0B30h+ppidl]; pidl
0x1800550e6  call    cs:__imp_SHGetPathFromIDListW
0x1800550ec  test    eax, eax
0x1800550ee  jz      loc_1800558D3
0x1800550f4  cmp     [rbp+0A30h+pszPath], r14w
0x1800550fc  jz      loc_1800558D3
0x180055102  mov     r8d, 104h; unsigned int
0x180055108  lea     rdx, [rbp+0A30h+szStart]; lpMultiByteStr
0x18005510f  lea     rcx, [rbp+0A30h+pszPath]; lpszLongPath
0x180055116  call    ?ConvertPathToAnsiWithNoBestFitMatching@@YA_NPEBGPEADK@Z; ConvertPathToAnsiWithNoBestFitMatching(ushort const *,char *,ulong)
0x18005511b  test    al, al
0x18005511d  jz      loc_1800558D3
0x180055123  cmp     [rbp+0A30h+szStart], r14b
0x18005512a  jz      loc_1800558D3
0x180055130  lea     rax, [rbp+0A30h+szStart]
0x180055137  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18005513e  inc     rcx
0x180055141  cmp     [rax+rcx], r14b
0x180055145  jnz     short loc_18005513E
0x180055147  lea     rax, [rcx+1]
0x18005514b  mov     r8, 200000000801h
0x180055155  cmp     rax, 104h
0x18005515b  jnb     loc_1800551E8
0x180055161  cmp     cs:?g_fDBCSSystem@@3HA, r14d; int g_fDBCSSystem
0x180055168  jz      short loc_1800551BA
0x18005516a  lea     rbx, [rbp+0A30h+szStart]
0x180055171  add     rbx, rcx
0x180055174  mov     rdx, rbx; lpszCurrent
0x180055177  lea     rcx, [rbp+0A30h+szStart]; lpszStart
0x18005517e  call    cs:__imp_CharPrevA
0x180055184  cmp     byte ptr [rax], 5Ch ; '\'
0x180055187  jz      short loc_1800551E8
0x180055189  mov     rdx, rbx; lpszCurrent
0x18005518c  lea     rcx, [rbp+0A30h+szStart]; lpszStart
0x180055193  call    cs:__imp_CharPrevA
0x180055199  cmp     byte ptr [rax], 2Fh ; '/'
0x18005519c  jz      short loc_1800551E8
0x18005519e  mov     rdx, rbx; lpszCurrent
0x1800551a1  lea     rcx, [rbp+0A30h+szStart]; lpszStart
0x1800551a8  call    cs:__imp_CharPrevA
0x1800551ae  cmp     byte ptr [rax], 3Ah ; ':'
0x1800551b1  jz      short loc_1800551E8
0x1800551b3  mov     word ptr [rbx], 5Ch ; '\'
0x1800551b8  jmp     short loc_1800551E8
0x1800551ba  movsxd  rax, ecx
0x1800551bd  lea     rdx, [rbp+0A30h+szStart]
0x1800551c4  add     rdx, rax
0x1800551c7  movzx   eax, byte ptr [rdx-1]
0x1800551cb  sub     al, 2Fh ; '/'
0x1800551cd  cmp     al, 2Dh ; '-'
0x1800551cf  ja      short loc_1800551D7
0x1800551d1  bt      r8, rax
0x1800551d5  jb      short loc_1800551E8
0x1800551d7  mov     byte ptr [rdx], 5Ch ; '\'
0x1800551da  lea     eax, [rcx+1]
0x1800551dd  movsxd  rcx, eax
0x1800551e0  mov     [rbp+rcx+0A30h+szStart], r14b
0x1800551e8  lea     rcx, [rbp+0A30h+szStart]; char *
0x1800551ef  call    ?lcStrDup@@YAPEADPEBD@Z; lcStrDup(char const *)
0x1800551f4  mov     rbx, rax
0x1800551f7  test    rax, rax
0x1800551fa  jnz     short loc_180055202
0x1800551fc  call    ?OOM@@YAXXZ; OOM(void)
0x180055202  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180055209  inc     rax
0x18005520c  cmp     byte ptr [rbx+rax], 0
0x180055210  jnz     short loc_180055209
0x180055212  add     eax, 4
0x180055215  movsxd  rdi, eax
0x180055218  mov     rdx, rdi; Size
0x18005521b  mov     rcx, rbx; Block
0x18005521e  call    cs:__imp_realloc
0x180055224  mov     r12, rax
0x180055227  test    rax, rax
0x18005522a  jnz     short loc_18005523B
0x18005522c  mov     rcx, rbx; Block
0x18005522f  call    cs:__imp_free
0x180055235  call    ?OOM@@YAXXZ; OOM(void)
0x18005523b  mov     [rbp+0A30h+var_9D8], r12
0x18005523f  lea     r8, asc_18007F5B4; "*.*"
0x180055246  mov     rdx, rdi; unsigned __int64
0x180055249  mov     rcx, r12; char *
0x18005524c  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x180055251  lea     rdi, ??_7CTable@@6B@; const CTable::`vftable'
0x180055258  mov     [rbp+0A30h+var_A60], rdi
0x18005525c  mov     [rbp+0A30h+var_A48], 13FF000h
0x180055263  mov     [rbp+0A30h+var_A44], 100000h
0x18005526a  lea     rcx, [rbp+0A30h+var_A60]; this
0x18005526e  call    ?InitializeTable@CTable@@IEAAXXZ; CTable::InitializeTable(void)
0x180055273  nop
0x180055274  mov     [rsp+0B30h+var_AD0], rdi
0x180055279  mov     [rsp+0B30h+var_AB8], 13FF000h
0x180055281  mov     [rsp+0B30h+var_AB4], 100000h
0x180055289  lea     rcx, [rsp+0B30h+var_AD0]; this
0x18005528e  call    ?InitializeTable@CTable@@IEAAXXZ; CTable::InitializeTable(void)
0x180055293  nop
0x180055294  xor     edx, edx; Val
0x180055296  mov     r8d, 140h; Size
0x18005529c  lea     rcx, [rbp+0A30h+FindFileData]; void *
0x1800552a0  call    memset_0
0x1800552a5  lea     rdx, [rbp+0A30h+FindFileData]; lpFindFileData
0x1800552a9  mov     rcx, r12; lpFileName
0x1800552ac  call    cs:__imp_FindFirstFileA
0x1800552b2  mov     rbx, rax
0x1800552b5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800552b9  jz      loc_180055463
0x1800552bf  test    byte ptr [rbp+0A30h+FindFileData.dwFileAttributes], 10h
0x1800552c3  jz      loc_180055392
0x1800552c9  cmp     [rbp+0A30h+FindFileData.cFileName], 2Eh ; '.'
0x1800552d0  jz      loc_180055445
0x1800552d6  mov     eax, [rbp+0A30h+var_A3C]
0x1800552d9  cmp     [rbp+0A30h+var_A40], eax
0x1800552dc  jl      short loc_180055321
0x1800552de  movsxd  rcx, [rbp+0A30h+var_A2C]
0x1800552e2  add     rcx, [rbp+0A30h+var_A50]; lpAddress
0x1800552e6  mov     edx, 1000h; dwSize
0x1800552eb  mov     r9d, 4; flProtect
0x1800552f1  mov     r8d, edx; flAllocationType
0x1800552f4  call    cs:__imp_VirtualAlloc
0x1800552fa  test    rax, rax
0x1800552fd  jz      loc_1800556A1
0x180055303  mov     eax, [rbp+0A30h+var_A2C]
0x180055306  add     eax, 1000h
0x18005530b  mov     [rbp+0A30h+var_A2C], eax
0x18005530e  movsxd  rcx, eax
0x180055311  shr     rcx, 3
0x180055315  mov     [rbp+0A30h+var_A3C], ecx
0x180055318  cmp     [rbp+0A30h+var_A40], ecx
0x18005531b  jge     loc_180055445
0x180055321  lea     rax, [rbp+0A30h+FindFileData.cFileName]
0x180055328  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18005532f  inc     rdx
0x180055332  cmp     byte ptr [rax+rdx], 0
0x180055336  jnz     short loc_18005532F
0x180055338  inc     edx; int
0x18005533a  lea     rcx, [rbp+0A30h+var_A60]; this
0x18005533e  call    ?TableMalloc@CTable@@QEAAPEADH@Z; CTable::TableMalloc(int)
0x180055343  movsxd  rdx, [rbp+0A30h+var_A40]
0x180055347  mov     rcx, [rbp+0A30h+var_A50]
0x18005534b  mov     [rcx+rdx*8], rax
0x18005534f  test    rax, rax
0x180055352  jz      loc_180055445
0x180055358  lea     rax, [rbp+0A30h+FindFileData.cFileName]
0x18005535f  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180055366  inc     rdx
0x180055369  cmp     byte ptr [rax+rdx], 0
0x18005536d  jnz     short loc_180055366
0x18005536f  inc     rdx; unsigned __int64
0x180055372  movsxd  rax, [rbp+0A30h+var_A40]
0x180055376  lea     r8, [rbp+0A30h+FindFileData.cFileName]; char *
0x18005537d  mov     rcx, [rbp+0A30h+var_A50]
0x180055381  mov     rcx, [rcx+rax*8]; char *
0x180055385  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18005538a  inc     [rbp+0A30h+var_A40]
0x18005538d  jmp     loc_180055445
0x180055392  mov     eax, [rbp+0A30h+var_AAC]
0x180055395  cmp     [rbp+0A30h+var_AB0], eax
0x180055398  jl      short loc_1800553DA
0x18005539a  movsxd  rcx, [rbp+0A30h+var_A9C]
0x18005539e  add     rcx, [rsp+0B30h+var_AC0]; lpAddress
0x1800553a3  mov     edx, 1000h; dwSize
0x1800553a8  mov     r9d, 4; flProtect
0x1800553ae  mov     r8d, edx; flAllocationType
0x1800553b1  call    cs:__imp_VirtualAlloc
0x1800553b7  test    rax, rax
0x1800553ba  jz      loc_1800556A1
0x1800553c0  mov     eax, [rbp+0A30h+var_A9C]
0x1800553c3  add     eax, 1000h
0x1800553c8  mov     [rbp+0A30h+var_A9C], eax
0x1800553cb  movsxd  rcx, eax
0x1800553ce  shr     rcx, 3
0x1800553d2  mov     [rbp+0A30h+var_AAC], ecx
0x1800553d5  cmp     [rbp+0A30h+var_AB0], ecx
0x1800553d8  jge     short loc_180055445
0x1800553da  lea     rax, [rbp+0A30h+FindFileData.cFileName]
0x1800553e1  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x1800553e8  inc     rdx
0x1800553eb  cmp     byte ptr [rax+rdx], 0
0x1800553ef  jnz     short loc_1800553E8
0x1800553f1  inc     edx; int
0x1800553f3  lea     rcx, [rsp+0B30h+var_AD0]; this
0x1800553f8  call    ?TableMalloc@CTable@@QEAAPEADH@Z; CTable::TableMalloc(int)
0x1800553fd  movsxd  rdx, [rbp+0A30h+var_AB0]
0x180055401  mov     rcx, [rsp+0B30h+var_AC0]
0x180055406  mov     [rcx+rdx*8], rax
0x18005540a  test    rax, rax
0x18005540d  jz      short loc_180055445
0x18005540f  lea     rax, [rbp+0A30h+FindFileData.cFileName]
0x180055416  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18005541d  inc     rdx
0x180055420  cmp     byte ptr [rax+rdx], 0
0x180055424  jnz     short loc_18005541D
0x180055426  inc     rdx; unsigned __int64
0x180055429  movsxd  rax, [rbp+0A30h+var_AB0]
0x18005542d  lea     r8, [rbp+0A30h+FindFileData.cFileName]; char *
0x180055434  mov     rcx, [rsp+0B30h+var_AC0]
0x180055439  mov     rcx, [rcx+rax*8]; char *
0x18005543d  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180055442  inc     [rbp+0A30h+var_AB0]
0x180055445  lea     rdx, [rbp+0A30h+FindFileData]; lpFindFileData
0x180055449  mov     rcx, rbx; hFindFile
0x18005544c  call    cs:__imp_FindNextFileA
0x180055452  test    eax, eax
0x180055454  jnz     loc_1800552BF
0x18005545a  mov     rcx, rbx; hFindFile
0x18005545d  call    cs:__imp_FindClose
0x180055463  cmp     [rbp+0A30h+var_A40], 1
0x180055467  jnz     short loc_180055473
0x180055469  cmp     [rbp+0A30h+var_AB0], 1
0x18005546d  jz      loc_1800558AC
0x180055473  xorps   xmm0, xmm0
0x180055476  xor     ebx, ebx
0x180055478  movups  [rsp+0B30h+var_AF8], xmm0
0x18005547d  movups  [rsp+0B30h+var_AE8], xmm0
0x180055482  mov     byte ptr [rsp+0B30h+var_AE8+9], 1
0x180055487  mov     ecx, 40Eh; uID
0x18005548c  call    ?GetStringResource@@YAPEBDH@Z; GetStringResource(int)
0x180055491  mov     rdx, rax; char *
0x180055494  mov     rcx, rsi; this
0x180055497  call    ?StrDupA@CTable@@QEAAPEBDPEBD@Z; CTable::StrDupA(char const *)
0x18005549c  mov     qword ptr [rsp+0B30h+var_AF8+8], rax
0x1800554a1  mov     eax, [rsi+24h]
0x1800554a4  cmp     [rsi+20h], eax
0x1800554a7  jl      short loc_1800554B1
0x1800554a9  mov     rcx, rsi; this
0x1800554ac  call    ?IncreaseTableBuffer@CTable@@QEAAXXZ; CTable::IncreaseTableBuffer(void)
0x1800554b1  mov     eax, [rsi+24h]
0x1800554b4  cmp     [rsi+20h], eax
0x1800554b7  jge     short loc_180055511
0x1800554b9  mov     edx, 28h ; '('; int
0x1800554be  mov     rcx, rsi; this
0x1800554c1  call    ?TableMalloc@CTable@@QEAAPEADH@Z; CTable::TableMalloc(int)
0x1800554c6  movsxd  rdx, dword ptr [rsi+20h]
0x1800554ca  mov     rcx, [rsi+10h]
0x1800554ce  mov     [rcx+rdx*8], rax
0x1800554d2  test    rax, rax
0x1800554d5  jz      short loc_180055511
0x1800554d7  movsxd  rcx, dword ptr [rsi+20h]
0x1800554db  mov     rax, [rsi+10h]
0x1800554df  mov     rdx, [rax+rcx*8]
0x1800554e3  movups  xmm0, [rsp+0B30h+var_AF8]
0x1800554e8  movups  xmmword ptr [rdx], xmm0
0x1800554eb  movups  xmm1, [rsp+0B30h+var_AE8]
0x1800554f0  movups  xmmword ptr [rdx+10h], xmm1
0x1800554f4  mov     [rdx+20h], rbx
0x1800554f8  movsxd  rcx, dword ptr [rsi+20h]
0x1800554fc  lea     eax, [rcx+1]
0x1800554ff  mov     [rsi+20h], eax
0x180055502  test    ecx, ecx
0x180055504  jz      short loc_180055511
0x180055506  mov     rax, [rsi+10h]
0x18005550a  mov     rcx, [rax+rcx*8]
0x18005550e  mov     [rcx], rsi
0x180055511  mov     r15d, 1
0x180055517  mov     ecx, [rbp+0A30h+var_A40]
0x18005551a  cmp     ecx, 3
0x18005551d  jl      short loc_18005554E
0x18005551f  mov     [rbp+0A30h+var_A14], r14d
0x180055523  mov     eax, [rbp+0A30h+var_A24]
0x180055526  test    eax, eax
0x180055528  cmovz   eax, cs:?g_lcidSystem@@3KA; ulong g_lcidSystem
0x18005552f  mov     [rbp+0A30h+var_A24], eax
0x180055532  mov     eax, [rbp+0A30h+var_A20]
0x180055535  or      eax, r15d
0x180055538  mov     [rbp+0A30h+var_A18], eax
0x18005553b  lea     r8d, [rcx-1]; int
0x18005553f  mov     edx, r15d; int
0x180055542  lea     rcx, [rbp+0A30h+var_A60]; this
0x180055546  call    ?doLcidSort@CTable@@IEAAXHH@Z; CTable::doLcidSort(int,int)
  ... truncated ...
```
