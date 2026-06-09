# FindDbg(_PROCESS_ENTRY *,ushort const *,ushort const *,ushort *,_FINDDBG_CALLBACK *)

- ea: `0x1800120f0`
- end: `0x180012c20`
- name: `?FindDbg@@YAPEAXPEAU_PROCESS_ENTRY@@PEBG1PEAGPEAU_FINDDBG_CALLBACK@@@Z`
- size: `2864`
- prototype: `void *__fastcall(struct _PROCESS_ENTRY *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, struct _FINDDBG_CALLBACK *)`
- caller_count: `4`
- callee_count: `20`
- tags: ``

## callers

- `0x180011cb0`
- `0x1801a9980`
- `0x1801a9d10`
- `0x1801a9e00`

## callees

- `0x1800089f0`
- `0x18000e378`
- `0x180011fb8`
- `0x1800120f0`
- `0x180012e28`
- `0x180012e6c`
- `0x180012ed4`
- `0x180012f54`
- `0x1800130f4`
- `0x18001adec`
- `0x180021340`
- `0x180023498`
- `0x1800273f0`
- `0x1800273fc`
- `0x180168f90`
- `0x18019ffa0`
- `0x1801a82d0`
- `0x1801a8c98`
- `0x1801aeedc`
- `0x1801d6350`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800124e1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800124e1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180012662`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180012662`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18001227f`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800123a6`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180012588`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18001227f`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800123a6`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180012588`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x1800128b3`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x1800128d1`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x1800128b3`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x1800128d1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800121d3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180012400`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180012479`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800127fc`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800121d3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180012400`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180012479`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800127fc`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1800125ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180012b75`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1800125ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180012b75`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001216a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001216a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012bed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012bed`

## string_xrefs

- `0x180012653`: `cache*`

## pseudocode

```c
unsigned __int16 *__fastcall FindDbg(
        struct _PROCESS_ENTRY *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        struct _FINDDBG_CALLBACK *a5)
{
  unsigned __int16 *result; // rax
  __int64 v8; // rbx
  __int64 v9; // rcx
  const unsigned __int16 *v10; // rax
  __int64 v11; // rdi
  wchar_t *v12; // r8
  unsigned int *v13; // rcx
  __int64 v14; // rdx
  wchar_t *v15; // rcx
  __int16 v16; // ax
  const wchar_t *v17; // rdx
  wchar_t *v18; // rax
  __int64 v19; // rcx
  __int16 v20; // ax
  wchar_t *p_Ext; // r14
  wchar_t v22; // ax
  const wchar_t *v23; // rcx
  int v24; // r8d
  unsigned __int16 *v25; // r15
  const unsigned __int16 *v26; // r12
  unsigned int v27; // esi
  unsigned __int64 v28; // r8
  int v29; // eax
  unsigned int v30; // r9d
  unsigned int FileMultiIndex; // eax
  int v32; // eax
  const wchar_t *v33; // rdx
  rsize_t v34; // r11
  wchar_t *v35; // rax
  __int64 v36; // rcx
  __int16 v37; // ax
  __int64 v38; // rdx
  int v39; // eax
  const unsigned __int16 *v40; // r8
  int FileFromCache; // eax
  int v42; // ecx
  int v43; // r9d
  struct _FINDDBG_CALLBACK *v44; // rdi
  unsigned int v45; // r9d
  unsigned int v46; // r9d
  unsigned int FilenameCount; // [rsp+30h] [rbp-1FD8h]
  int v48; // [rsp+58h] [rbp-1FB0h]
  int v49; // [rsp+5Ch] [rbp-1FACh]
  unsigned int v50[2]; // [rsp+60h] [rbp-1FA8h] BYREF
  int v51; // [rsp+68h] [rbp-1FA0h]
  struct _FINDDBG_CALLBACK *v52; // [rsp+70h] [rbp-1F98h]
  int *v53; // [rsp+78h] [rbp-1F90h]
  unsigned int v54[2]; // [rsp+80h] [rbp-1F88h] BYREF
  int v55; // [rsp+88h] [rbp-1F80h]
  int v56; // [rsp+90h] [rbp-1F78h] BYREF
  unsigned int v57; // [rsp+94h] [rbp-1F74h]
  __int64 j; // [rsp+98h] [rbp-1F70h]
  unsigned __int16 *v59; // [rsp+A0h] [rbp-1F68h]
  __int64 i; // [rsp+A8h] [rbp-1F60h]
  wchar_t *v61; // [rsp+B0h] [rbp-1F58h]
  int v62; // [rsp+B8h] [rbp-1F50h]
  wchar_t *v63; // [rsp+C0h] [rbp-1F48h]
  __int64 v64; // [rsp+C8h] [rbp-1F40h]
  wchar_t *v65; // [rsp+D0h] [rbp-1F38h]
  const wchar_t *v66; // [rsp+D8h] [rbp-1F30h]
  wchar_t *v67; // [rsp+E0h] [rbp-1F28h]
  const wchar_t *v68; // [rsp+E8h] [rbp-1F20h]
  int v69; // [rsp+F0h] [rbp-1F18h]
  struct _GUID v70; // [rsp+F8h] [rbp-1F10h] BYREF
  wchar_t Drive; // [rsp+108h] [rbp-1F00h] BYREF
  wchar_t Buffer[264]; // [rsp+110h] [rbp-1EF8h] BYREF
  wchar_t Ext; // [rsp+320h] [rbp-1CE8h] BYREF
  _BYTE v74[526]; // [rsp+322h] [rbp-1CE6h] BYREF
  unsigned __int16 v75[6]; // [rsp+530h] [rbp-1AD8h] BYREF
  __int64 v76; // [rsp+53Ch] [rbp-1ACCh] BYREF
  wchar_t Str[264]; // [rsp+740h] [rbp-18C8h] BYREF
  unsigned __int16 v78[264]; // [rsp+950h] [rbp-16B8h] BYREF
  wchar_t Source[264]; // [rsp+B60h] [rbp-14A8h] BYREF
  unsigned __int16 v80[264]; // [rsp+D70h] [rbp-1298h] BYREF
  wchar_t Dir[264]; // [rsp+F80h] [rbp-1088h] BYREF
  wchar_t v82[256]; // [rsp+1190h] [rbp-E78h] BYREF
  wchar_t Destination[1560]; // [rsp+1390h] [rbp-C78h] BYREF

  v59 = a4;
  v52 = a5;
  v56 = 0;
  *(_QWORD *)v50 = 0;
  v51 = 0;
  *(_QWORD *)v54 = 0;
  v55 = 0;
  v70 = 0;
  if ( a2 )
  {
    v8 = -1;
    v53 = &v56;
    v48 = 1;
    v49 = 0;
    if ( !a3 )
      a3 = &word_18022B134;
    v9 = 1560;
    v10 = a3;
    do
    {
      if ( !*v10 )
        break;
      ++v10;
      --v9;
    }
    while ( v9 );
    if ( v9 )
    {
      wcscpy_s(Destination, 0x618u, a3);
    }
    else
    {
      Destination[0] = 0;
      *(_DWORD *)((__int64 (*)(void))_o__errno)() = 34;
    }
    if ( a5 && (v11 = *((_QWORD *)a5 + 1)) != 0 )
    {
      if ( *(_DWORD *)v11 == 4888 )
      {
        if ( !a1 )
          a1 = *(struct _PROCESS_ENTRY **)(v11 + 8);
        if ( (dword_1802AF9CC & 0x200000) == 0 )
        {
          Drive = 0;
          Dir[0] = 0;
          _wsplitpath_s((const wchar_t *)(v11 + 58), &Drive, 4u, Dir, 0x101u, 0, 0, 0, 0);
          BackslashCut(Dir);
          wcscat_s_ex(Destination, 0x618u, L";");
          if ( Drive || Dir[0] )
          {
            wcscat_s_ex(Destination, 0x618u, &Drive);
            v12 = Dir;
          }
          else
          {
            v12 = (wchar_t *)L".";
          }
          wcscat_s_ex(Destination, 0x618u, v12);
        }
        v50[0] = *(_DWORD *)(v11 + 48);
        v13 = v50;
        if ( v50[0] )
          v13 = &v50[1];
        *v13 = *(_DWORD *)(v11 + 2224);
        v54[0] = *(_DWORD *)(v11 + 40);
        if ( (*(_BYTE *)(v11 + 4276) & 2) != 0 )
          v54[1] = *(_DWORD *)(v11 + 44);
      }
    }
    else
    {
      v11 = 0;
    }
    *v59 = 0;
    v78[0] = 0;
    v80[0] = 0;
    _wsplitpath_s(a2, &Drive, 4u, v82, 0x100u, Source, 0x101u, &Ext, 0x101u);
    v14 = 261;
    v64 = 261;
    v15 = Source;
    v63 = Source;
    do
    {
      v16 = *v15++;
      v63 = v15;
      if ( !v16 )
        break;
      v64 = --v14;
    }
    while ( v14 );
    if ( v14 )
    {
      wcscpy_s(Str, 0x105u, Source);
    }
    else
    {
      Str[0] = 0;
      *(_DWORD *)((__int64 (*)(void))_o__errno)() = 34;
    }
    v18 = Str;
    v65 = Str;
    v19 = 261;
    for ( i = 261; ; i = v19 )
    {
      if ( !v19 )
        goto LABEL_38;
      if ( !*v18 )
        break;
      v65 = ++v18;
      --v19;
    }
    v17 = L".dbg";
    v66 = L".dbg";
    do
    {
      v20 = *v17++;
      v66 = v17;
      if ( !v20 )
        break;
      i = --v19;
    }
    while ( v19 );
    if ( !v19 )
    {
LABEL_38:
      Str[0] = 0;
      *(_DWORD *)_o__errno(v19, v17, Str, 1) = 34;
      goto LABEL_43;
    }
    wcscat_s(Str, 0x105u, L".dbg");
LABEL_43:
    if ( (unsigned int)_o__wcsicmp(&Ext, L".dbg") )
    {
      p_Ext = &Ext;
      v22 = Ext;
      if ( Ext )
        p_Ext = (wchar_t *)v74;
      v61 = p_Ext;
    }
    else
    {
      p_Ext = v82;
      v61 = v82;
      v22 = Ext;
    }
    if ( *((_QWORD *)a5 + 1) )
    {
      if ( *(_DWORD *)v11 == 4888 )
      {
        if ( !*p_Ext )
        {
          v23 = (const wchar_t *)(v11 + 58);
          if ( *(_WORD *)(v11 + 58) || (v23 = (const wchar_t *)(v11 + 3604), *(_WORD *)(v11 + 3604)) )
          {
            _wsplitpath_s(v23, 0, 0, 0, 0, 0, 0, &Ext, 0x101u);
          }
          else
          {
            p_Ext = &Ext;
            if ( v22 )
              p_Ext = (wchar_t *)v74;
            v61 = p_Ext;
          }
        }
        v53 = (int *)(v11 + 3308);
      }
      else
      {
        v11 = 0;
      }
    }
    result = ExpandPath(Destination);
    v25 = result;
    if ( result )
    {
      if ( (dword_1802AF9CC & 0x200) != 0 )
        uMode = SetErrorMode(1u);
      v26 = v25;
LABEL_63:
      while ( v26 )
      {
        v26 = TokenFromSymbolPath(v26, v75, v24);
        v24 = 0;
        if ( v75[0] )
        {
          v8 = -1;
          v27 = 0;
          v57 = 0;
          while ( v27 < 3 )
          {
            Buffer[0] = 0;
            if ( (unsigned int)_o__wcsnicmp(v75, L"cache*", 6) )
            {
              v29 = symsrvTest(a1, v75, v28, 1);
              v24 = 0;
              if ( v29 )
              {
                if ( !v11 || v27 || !v48 )
                  goto LABEL_63;
                *v53 = 4;
                FileMultiIndex = symsrvGetFileMultiIndex(a1, v75, v80, Str, v50, v54, FilenameCount, Buffer);
                v24 = 0;
                if ( FileMultiIndex == 232 )
                {
                  v48 = 0;
                  v69 = 0;
                }
              }
              else
              {
                if ( v27 && !*p_Ext )
                  goto LABEL_63;
                *v53 = 1;
                if ( v75[0] && Source[0] )
                {
                  wcscpy_s_ex(Buffer, 0x105u, v75);
                  v32 = BackslashCat(Buffer, 261);
                  v24 = 0;
                  if ( !v32 )
                    goto LABEL_63;
                  if ( v27 )
                  {
                    if ( v27 != 1 )
                    {
                      v35 = Buffer;
                      v67 = Buffer;
                      v36 = (unsigned int)v34;
                      for ( j = (unsigned int)v34; ; j = v36 )
                      {
                        if ( !v36 )
                          goto LABEL_86;
                        if ( !*v35 )
                          break;
                        v67 = ++v35;
                        --v36;
                      }
                      v33 = L"symbols";
                      v68 = L"symbols";
                      do
                      {
                        v37 = *v33++;
                        v68 = v33;
                        if ( !v37 )
                          break;
                        j = --v36;
                      }
                      while ( v36 );
                      if ( !v36 )
                      {
LABEL_86:
                        Buffer[0] = 0;
                        *(_DWORD *)_o__errno(v36, v33, 0, 1) = 34;
                        goto LABEL_91;
                      }
                      wcscat_s(Buffer, v34, L"symbols");
LABEL_91:
                      if ( !(unsigned int)BackslashCat(Buffer, 261) )
                        goto LABEL_63;
                    }
                    wcscat_s_ex(Buffer, v34, p_Ext);
                    v34 = 261;
                  }
                  if ( !(unsigned int)BackslashCat(Buffer, v34) )
                    goto LABEL_63;
                  _o_wcsncat_s(Buffer, v38, Source, -1);
                  _o_wcsncat_s(Buffer, 261, L".dbg", -1);
                  v39 = 1;
                  v24 = 0;
                }
                else
                {
                  v39 = 0;
                }
                if ( !v39 )
                  goto LABEL_63;
              }
            }
            else
            {
              if ( !(_WORD)v76 || (_WORD)v76 == 42 )
              {
                if ( !word_1802B0BBA )
                  SymSetHomeDirectoryW(0, 0);
                v40 = &word_1802B0BBA;
              }
              else
              {
                v40 = (const unsigned __int16 *)&v76;
              }
              wcscpy_s_ex(v80, 0x105u, v40);
              v24 = 0;
              if ( v27 || !v48 || !v11 )
                goto LABEL_63;
              v70 = 0;
              v70.Data1 = v50[0];
              FileFromCache = GetFileFromCache(a1, 0, v80, Str, &v70, v54[0], 0, 0, Buffer);
              v42 = v49;
              v24 = 0;
              if ( FileFromCache )
                v42 = 1;
              v49 = v42;
              v62 = v42;
            }
            if ( Buffer[0] )
            {
              if ( !v27 )
                v8 = (__int64)CheckDirForDbgs(a1, Buffer, v78, v30, v52);
              if ( v8 != -1 )
                goto LABEL_117;
              v8 = (__int64)OpenDbg(a1, Buffer, v78, v30, v52);
              if ( v8 != -1 )
                goto LABEL_117;
              v24 = 0;
            }
            v57 = ++v27;
          }
        }
      }
LABEL_117:
      FreeIt(v25);
      if ( ((v8 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
        if ( v82[0] == 92 )
        {
          swprintf_s(Buffer, 0x105u, L"%s%s%s.dbg", &Drive, v82, Source);
          v44 = v52;
          v8 = (__int64)OpenDbg(a1, Buffer, v78, v45, v52);
        }
        else
        {
          v44 = v52;
        }
        if ( ((dword_1802AF9CC & 0x400) == 0 || (dword_1802AF9CC & 0x40) != 0)
          && ((v8 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0
          && v78[0]
          && (!*(_QWORD *)v44 || *(BOOL (__stdcall **)(HANDLE, PCWSTR, PVOID))v44 == cbFindDbg) )
        {
          *v53 = 1;
          wcscpy_s_ex(Buffer, 0x104u, v78);
          v8 = (__int64)OpenDbg(a1, Buffer, v78, v46, 0);
        }
      }
      if ( (dword_1802AF9CC & 0x200) != 0 )
        SetErrorMode(uMode);
      if ( v8 == -1 )
        v8 = 0;
      if ( v8 )
      {
        if ( v80[0] )
        {
          if ( !v49 )
            v8 = (__int64)CopyOpenFileToCache(a1, (void *)v8, Buffer, v43, v80);
        }
        wcscpy_s_ex(v59, 0x105u, Buffer);
      }
      return (unsigned __int16 *)v8;
    }
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800120f0  push    rbx
0x1800120f2  push    rsi
0x1800120f3  push    rdi
0x1800120f4  push    r12
0x1800120f6  push    r13
0x1800120f8  push    r14
0x1800120fa  push    r15
0x1800120fc  mov     eax, 1FD0h
0x180012101  call    _alloca_probe
0x180012106  sub     rsp, rax
0x180012109  mov     rax, cs:__security_cookie
0x180012110  xor     rax, rsp
0x180012113  mov     [rsp+2008h+var_48], rax
0x18001211b  mov     [rsp+2008h+var_1F68], r9
0x180012123  mov     rsi, rdx
0x180012126  mov     r13, rcx
0x180012129  mov     r15, [rsp+2008h+arg_20]
0x180012131  mov     [rsp+2008h+var_1F98], r15
0x180012136  xor     eax, eax
0x180012138  mov     [rsp+2008h+var_1F78], eax
0x18001213f  mov     qword ptr [rsp+2008h+var_1FA8], rax
0x180012144  mov     [rsp+2008h+var_1FA0], eax
0x180012148  mov     qword ptr [rsp+2008h+var_1F88], rax
0x180012150  mov     [rsp+2008h+var_1F80], eax
0x180012157  xorps   xmm0, xmm0
0x18001215a  movups  xmmword ptr [rsp+2008h+var_1F10.Data1], xmm0
0x180012162  test    rdx, rdx
0x180012165  jnz     short loc_180012177
0x180012167  lea     ecx, [rdx+57h]; dwErrCode
0x18001216a  call    cs:__imp_SetLastError
0x180012170  xor     eax, eax
0x180012172  jmp     loc_180012BFD
0x180012177  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001217b  mov     [rsp+2008h+hObject], rbx
0x180012180  lea     r12, [rsp+2008h+var_1F78]
0x180012188  mov     [rsp+2008h+var_1F90], r12
0x18001218d  lea     r9d, [rbx+2]
0x180012191  mov     [rsp+2008h+var_1FB0], r9d
0x180012196  xor     r12d, r12d
0x180012199  mov     [rsp+2008h+var_1FAC], r12d
0x18001219e  lea     rax, word_18022B134
0x1800121a5  test    r8, r8
0x1800121a8  cmovz   r8, rax; Source
0x1800121ac  mov     edx, 618h; SizeInWords
0x1800121b1  mov     ecx, edx
0x1800121b3  mov     rax, r8
0x1800121b6  cmp     [rax], r12w
0x1800121ba  jz      short loc_1800121C5
0x1800121bc  add     rax, 2
0x1800121c0  sub     rcx, r9
0x1800121c3  jnz     short loc_1800121B6
0x1800121c5  test    rcx, rcx
0x1800121c8  jnz     short loc_1800121E4
0x1800121ca  mov     [rsp+2008h+Destination], r12w
0x1800121d3  call    cs:__imp__o__errno
0x1800121d9  mov     r14d, 22h ; '"'
0x1800121df  mov     [rax], r14d
0x1800121e2  jmp     short loc_1800121F7
0x1800121e4  lea     rcx, [rsp+2008h+Destination]; Destination
0x1800121ec  call    wcscpy_s
0x1800121f1  mov     r14d, 22h ; '"'
0x1800121f7  test    r15, r15
0x1800121fa  jz      short loc_180012205
0x1800121fc  mov     rdi, [r15+8]
0x180012200  test    rdi, rdi
0x180012203  jnz     short loc_180012211
0x180012205  mov     rdi, r12
0x180012208  test    r12, r12
0x18001220b  jz      loc_18001233A
0x180012211  cmp     dword ptr [rdi], 1318h
0x180012217  jnz     loc_18001233A
0x18001221d  test    r13, r13
0x180012220  jnz     short loc_180012226
0x180012222  mov     r13, [rdi+8]
0x180012226  test    cs:dword_1802AF9CC, 200000h
0x180012230  jnz     loc_1800122FE
0x180012236  mov     [rsp+2008h+Drive], r12w
0x18001223f  mov     [rsp+2008h+Dir], r12w
0x180012248  lea     rcx, [rdi+3Ah]; FullPath
0x18001224c  mov     [rsp+2008h+ExtCount], r12; ExtCount
0x180012251  mov     [rsp+2008h+Ext], r12; Ext
0x180012256  mov     [rsp+2008h+FilenameCount], r12; FilenameCount
0x18001225b  mov     [rsp+2008h+Filename], r12; Filename
0x180012260  mov     [rsp+2008h+DirCount], 101h; DirCount
0x180012269  lea     r9, [rsp+2008h+Dir]; Dir
0x180012271  mov     r8d, 4; DriveCount
0x180012277  lea     rdx, [rsp+2008h+Drive]; Drive
0x18001227f  call    cs:__imp__wsplitpath_s
0x180012285  lea     rcx, [rsp+2008h+Dir]; unsigned __int16 *
0x18001228d  call    ?BackslashCut@@YAXPEAG@Z; BackslashCut(ushort *)
0x180012292  lea     r8, asc_180253C24; ";"
0x180012299  mov     edx, 618h; unsigned __int64
0x18001229e  lea     rcx, [rsp+2008h+Destination]; unsigned __int16 *
0x1800122a6  call    ?wcscat_s_ex@@YAHPEAG_KPEBG@Z; wcscat_s_ex(ushort *,unsigned __int64,ushort const *)
0x1800122ab  cmp     [rsp+2008h+Drive], r12w
0x1800122b4  jnz     short loc_1800122CA
0x1800122b6  cmp     [rsp+2008h+Dir], r12w
0x1800122bf  jnz     short loc_1800122CA
0x1800122c1  lea     r8, asc_18022ACFC; "."
0x1800122c8  jmp     short loc_1800122EC
0x1800122ca  lea     r8, [rsp+2008h+Drive]; unsigned __int16 *
0x1800122d2  mov     edx, 618h; unsigned __int64
0x1800122d7  lea     rcx, [rsp+2008h+Destination]; unsigned __int16 *
0x1800122df  call    ?wcscat_s_ex@@YAHPEAG_KPEBG@Z; wcscat_s_ex(ushort *,unsigned __int64,ushort const *)
0x1800122e4  lea     r8, [rsp+2008h+Dir]; unsigned __int16 *
0x1800122ec  mov     edx, 618h; unsigned __int64
0x1800122f1  lea     rcx, [rsp+2008h+Destination]; unsigned __int16 *
0x1800122f9  call    ?wcscat_s_ex@@YAHPEAG_KPEBG@Z; wcscat_s_ex(ushort *,unsigned __int64,ushort const *)
0x1800122fe  mov     eax, [rdi+30h]
0x180012301  mov     [rsp+2008h+var_1FA8], eax
0x180012305  lea     rcx, [rsp+2008h+var_1FA8]
0x18001230a  lea     rdx, [rsp+2008h+var_1FA8+4]
0x18001230f  test    eax, eax
0x180012311  cmovnz  rcx, rdx
0x180012315  mov     eax, [rdi+8B0h]
0x18001231b  mov     [rcx], eax
0x18001231d  mov     eax, [rdi+28h]
0x180012320  mov     [rsp+2008h+var_1F88], eax
0x180012327  test    byte ptr [rdi+10B4h], 2
0x18001232e  jz      short loc_18001233A
0x180012330  mov     eax, [rdi+2Ch]
0x180012333  mov     [rsp+2008h+var_1F88+4], eax
0x18001233a  mov     rcx, [rsp+2008h+var_1F68]
0x180012342  mov     [rcx], r12w
0x180012346  mov     [rsp+2008h+var_16B8], r12w
0x18001234f  mov     [rsp+2008h+var_1298], r12w
0x180012358  mov     [rsp+2008h+ExtCount], 101h; ExtCount
0x180012361  lea     rax, [rsp+2008h+var_1CE8]
0x180012369  mov     [rsp+2008h+Ext], rax; Ext
0x18001236e  mov     [rsp+2008h+FilenameCount], 101h; unsigned int
0x180012377  lea     rax, [rsp+2008h+Source]
0x18001237f  mov     [rsp+2008h+Filename], rax; Filename
0x180012384  mov     [rsp+2008h+DirCount], 100h; DirCount
0x18001238d  lea     r9, [rsp+2008h+var_E78]; Dir
0x180012395  mov     r8d, 4; DriveCount
0x18001239b  lea     rdx, [rsp+2008h+Drive]; Drive
0x1800123a3  mov     rcx, rsi; FullPath
0x1800123a6  call    cs:__imp__wsplitpath_s
0x1800123ac  lea     r8, [rsp+2008h+Str]
0x1800123b4  mov     esi, 105h
0x1800123b9  mov     edx, esi
0x1800123bb  mov     [rsp+2008h+var_1F40], rdx
0x1800123c3  lea     rcx, [rsp+2008h+Source]
0x1800123cb  mov     [rsp+2008h+var_1F48], rcx
0x1800123d3  movzx   eax, word ptr [rcx]
0x1800123d6  add     rcx, 2
0x1800123da  mov     [rsp+2008h+var_1F48], rcx
0x1800123e2  test    ax, ax
0x1800123e5  jz      short loc_1800123F7
0x1800123e7  sub     rdx, 1
0x1800123eb  mov     [rsp+2008h+var_1F40], rdx
0x1800123f3  jz      short loc_1800123F7
0x1800123f5  jmp     short loc_1800123D3
0x1800123f7  test    rdx, rdx
0x1800123fa  jnz     short loc_18001240B
0x1800123fc  mov     [r8], r12w
0x180012400  call    cs:__imp__o__errno
0x180012406  mov     [rax], r14d
0x180012409  jmp     short loc_180012423
0x18001240b  lea     r8, [rsp+2008h+Source]; Source
0x180012413  mov     rdx, rsi; SizeInWords
0x180012416  lea     rcx, [rsp+2008h+Str]; Destination
0x18001241e  call    wcscpy_s
0x180012423  lea     r8, [rsp+2008h+Str]
0x18001242b  lea     rax, [rsp+2008h+Str]
0x180012433  mov     [rsp+2008h+var_1F38], rax
0x18001243b  mov     rcx, rsi
0x18001243e  mov     [rsp+2008h+var_1F60], rcx
0x180012446  mov     r9d, 1
0x18001244c  test    rcx, rcx
0x18001244f  jz      short loc_180012475
0x180012451  cmp     [rax], r12w
0x180012455  jz      short loc_180012470
0x180012457  add     rax, 2
0x18001245b  mov     [rsp+2008h+var_1F38], rax
0x180012463  sub     rcx, r9
0x180012466  mov     [rsp+2008h+var_1F60], rcx
0x18001246e  jmp     short loc_18001244C
0x180012470  test    rcx, rcx
0x180012473  jnz     short loc_180012484
0x180012475  mov     [r8], r12w
0x180012479  call    cs:__imp__o__errno
0x18001247f  mov     [rax], r14d
0x180012482  jmp     short loc_1800124D2
0x180012484  lea     rdx, aDbg_0; ".dbg"
0x18001248b  mov     [rsp+2008h+var_1F30], rdx
0x180012493  movzx   eax, word ptr [rdx]
0x180012496  add     rdx, 2
0x18001249a  mov     [rsp+2008h+var_1F30], rdx
0x1800124a2  test    ax, ax
0x1800124a5  jz      short loc_1800124B6
0x1800124a7  sub     rcx, r9
0x1800124aa  mov     [rsp+2008h+var_1F60], rcx
0x1800124b2  jz      short loc_1800124B6
0x1800124b4  jmp     short loc_180012493
0x1800124b6  test    rcx, rcx
0x1800124b9  jz      short loc_180012475
0x1800124bb  lea     r8, aDbg_0; ".dbg"
0x1800124c2  mov     rdx, rsi; SizeInWords
0x1800124c5  lea     rcx, [rsp+2008h+Str]; Destination
0x1800124cd  call    wcscat_s
0x1800124d2  lea     rdx, aDbg_0; ".dbg"
0x1800124d9  lea     rcx, [rsp+2008h+var_1CE8]
0x1800124e1  call    cs:__imp__o__wcsicmp
0x1800124e7  test    eax, eax
0x1800124e9  jnz     short loc_180012505
0x1800124eb  lea     r14, [rsp+2008h+var_E78]
0x1800124f3  mov     [rsp+2008h+var_1F58], r14
0x1800124fb  movzx   eax, [rsp+2008h+var_1CE8]
0x180012503  jmp     short loc_18001252C
0x180012505  lea     r14, [rsp+2008h+var_1CE8]
0x18001250d  lea     rcx, [rsp+2008h+var_1CE6]
0x180012515  movzx   eax, [rsp+2008h+var_1CE8]
0x18001251d  test    ax, ax
0x180012520  cmovnz  r14, rcx
0x180012524  mov     [rsp+2008h+var_1F58], r14
0x18001252c  cmp     [r15+8], r12
0x180012530  jz      loc_1800125C0
0x180012536  cmp     dword ptr [rdi], 1318h
0x18001253c  jnz     short loc_1800125BD
0x18001253e  cmp     [r14], r12w
0x180012542  jnz     short loc_1800125AF
0x180012544  lea     rcx, [rdi+3Ah]
0x180012548  cmp     [rcx], r12w
0x18001254c  jnz     short loc_18001255B
0x18001254e  lea     rcx, [rdi+0E14h]; FullPath
0x180012555  cmp     [rcx], r12w
0x180012559  jz      short loc_180012590
0x18001255b  mov     [rsp+2008h+ExtCount], 101h; ExtCount
0x180012564  lea     rax, [rsp+2008h+var_1CE8]
0x18001256c  mov     [rsp+2008h+Ext], rax; Ext
0x180012571  mov     [rsp+2008h+FilenameCount], r12; FilenameCount
0x180012576  mov     [rsp+2008h+Filename], r12; Filename
0x18001257b  mov     [rsp+2008h+DirCount], r12; DirCount
0x180012580  xor     r9d, r9d; Dir
0x180012583  xor     r8d, r8d; DriveCount
0x180012586  xor     edx, edx; Drive
0x180012588  call    cs:__imp__wsplitpath_s
0x18001258e  jmp     short loc_1800125AF
0x180012590  lea     r14, [rsp+2008h+var_1CE8]
0x180012598  lea     rcx, [rsp+2008h+var_1CE6]
0x1800125a0  test    ax, ax
0x1800125a3  cmovnz  r14, rcx
0x1800125a7  mov     [rsp+2008h+var_1F58], r14
0x1800125af  lea     rax, [rdi+0CECh]
0x1800125b6  mov     [rsp+2008h+var_1F90], rax
0x1800125bb  jmp     short loc_1800125C0
0x1800125bd  mov     rdi, r12
0x1800125c0  lea     rcx, [rsp+2008h+Destination]; unsigned __int16 *
0x1800125c8  call    ?ExpandPath@@YAPEAGPEBG@Z; ExpandPath(ushort const *)
0x1800125cd  mov     r15, rax
0x1800125d0  test    rax, rax
0x1800125d3  jz      loc_180012BFD
0x1800125d9  test    cs:dword_1802AF9CC, 200h
0x1800125e3  jz      short loc_1800125F6
0x1800125e5  mov     ecx, 1; uMode
0x1800125ea  call    cs:__imp_SetErrorMode
0x1800125f0  mov     cs:uMode, eax
0x1800125f6  mov     r12, r15
0x1800125f9  test    r12, r12
0x1800125fc  jz      loc_180012A4D
0x180012602  lea     rdx, [rsp+2008h+var_1AD8]; unsigned __int16 *
0x18001260a  mov     rcx, r12; unsigned __int16 *
0x18001260d  call    ?TokenFromSymbolPath@@YAPEAGPEBGPEAGH@Z; TokenFromSymbolPath(ushort const *,ushort *,int)
0x180012612  mov     r12, rax
0x180012615  xor     r8d, r8d
0x180012618  cmp     [rsp+2008h+var_1AD8], r8w
0x180012621  jz      loc_1800128F6
0x180012627  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001262b  mov     [rsp+2008h+hObject], rbx
0x180012630  mov     esi, r8d
0x180012633  mov     [rsp+2008h+var_1F74], r8d
0x18001263b  cmp     esi, 3
0x18001263e  jnb     loc_1800128EC
0x180012644  mov     [rsp+2008h+Buffer], r8w
0x18001264d  mov     r8d, 6
0x180012653  lea     rdx, aCache_0; "cache*"
0x18001265a  lea     rcx, [rsp+2008h+var_1AD8]
0x180012662  call    cs:__imp__o__wcsnicmp
0x180012668  xor     ecx, ecx; hProcess
0x18001266a  test    eax, eax
0x18001266c  jz      loc_1800128FB
0x180012672  lea     r9d, [rcx+1]; int
0x180012676  lea     rdx, [rsp+2008h+var_1AD8]; unsigned __int16 *
0x18001267e  mov     rcx, r13; struct _PROCESS_ENTRY *
0x180012681  call    ?symsrvTest@@YAHPEAU_PROCESS_ENTRY@@PEAG_KH@Z; symsrvTest(_PROCESS_ENTRY *,ushort *,unsigned __int64,int)
0x180012686  xor     r8d, r8d
0x180012689  test    eax, eax
0x18001268b  jz      loc_18001271D
0x180012691  test    rdi, rdi
0x180012694  jz      loc_1800128EC
0x18001269a  test    esi, esi
0x18001269c  jnz     loc_1800128EC
0x1800126a2  cmp     [rsp+2008h+var_1FB0], r8d
0x1800126a7  jz      loc_1800128EC
0x1800126ad  mov     rax, [rsp+2008h+var_1F90]
0x1800126b2  mov     dword ptr [rax], 4
0x1800126b8  lea     rax, [rsp+2008h+Buffer]
0x1800126c0  mov     [rsp+2008h+Ext], rax; unsigned __int16 *
0x1800126c5  lea     rax, [rsp+2008h+var_1F88]
  ... truncated ...
```
