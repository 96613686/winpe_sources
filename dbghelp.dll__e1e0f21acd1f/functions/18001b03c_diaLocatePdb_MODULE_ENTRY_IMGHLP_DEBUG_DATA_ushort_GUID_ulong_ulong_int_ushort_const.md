# diaLocatePdb(_MODULE_ENTRY *,_IMGHLP_DEBUG_DATA *,ushort *,_GUID *,ulong,ulong,int,ushort const *)

- ea: `0x18001b03c`
- end: `0x18001bc48`
- name: `?diaLocatePdb@@YAJPEAU_MODULE_ENTRY@@PEAU_IMGHLP_DEBUG_DATA@@PEAGPEAU_GUID@@KKHPEBG@Z`
- size: `3084`
- prototype: `int(struct _MODULE_ENTRY *, struct _IMGHLP_DEBUG_DATA *, unsigned __int16 *, struct _GUID *, unsigned int, unsigned int, int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops`

## callers

- `0x1800035b0`

## callees

- `0x1800051cc`
- `0x180005650`
- `0x180005764`
- `0x180009790`
- `0x18000dfac`
- `0x180011e98`
- `0x180011fb8`
- `0x180012ca0`
- `0x180012e6c`
- `0x180012f54`
- `0x180016ebc`
- `0x1800186b0`
- `0x18001adec`
- `0x18001b03c`
- `0x180021340`
- `0x180021374`
- `0x180027430`
- `0x18019fd0c`
- `0x1801d6350`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18001b327`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18001b3c1`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18001b943`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18001b327`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18001b3c1`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18001b943`

## pseudocode

```c
__int64 __fastcall diaLocatePdb(
        struct _MODULE_ENTRY *a1,
        struct _IMGHLP_DEBUG_DATA *a2,
        unsigned __int16 *a3,
        struct _GUID *a4,
        unsigned int a5,
        unsigned int a6,
        int a7,
        const unsigned __int16 *a8)
{
  __int64 result; // rax
  unsigned int v13; // edi
  __int64 v14; // rax
  __int64 v15; // rax
  int v16; // r12d
  unsigned int Data1; // eax
  unsigned __int64 v18; // r8
  int v19; // eax
  wchar_t *v20; // rcx
  int v21; // edx
  unsigned __int16 *v22; // r12
  int v23; // r12d
  struct _PROCESS_ENTRY *v24; // rcx
  int v25; // r12d
  wchar_t *v26; // rcx
  int v27; // r8d
  int v28; // edx
  __int16 v29; // r10
  wchar_t *v30; // r9
  const wchar_t *v31; // r8
  int DirCount; // [rsp+20h] [rbp-E0h]
  const wchar_t *DirCounta; // [rsp+20h] [rbp-E0h]
  int DirCountb; // [rsp+20h] [rbp-E0h]
  int DirCountc; // [rsp+20h] [rbp-E0h]
  wchar_t *DirCountd; // [rsp+20h] [rbp-E0h]
  size_t FilenameCount; // [rsp+30h] [rbp-D0h]
  unsigned __int16 *v38; // [rsp+50h] [rbp-B0h]
  unsigned int v39; // [rsp+60h] [rbp-A0h]
  int v40; // [rsp+64h] [rbp-9Ch]
  int v41; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v43; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v44; // [rsp+88h] [rbp-78h]
  struct _GUID v45; // [rsp+90h] [rbp-70h] BYREF
  wchar_t Drive[8]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t v47; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v48[526]; // [rsp+B2h] [rbp-4Eh] BYREF
  wchar_t Dir[264]; // [rsp+2C0h] [rbp+1C0h] BYREF
  wchar_t Buffer[264]; // [rsp+4D0h] [rbp+3D0h] BYREF
  unsigned __int16 v51[264]; // [rsp+6E0h] [rbp+5E0h] BYREF
  unsigned __int16 v52[264]; // [rsp+8F0h] [rbp+7F0h] BYREF
  wchar_t Filename[264]; // [rsp+B00h] [rbp+A00h] BYREF
  wchar_t Ext[264]; // [rsp+D10h] [rbp+C10h] BYREF

  v47 = 0;
  v45 = 0;
  memset_0(v48, 0, 0x208u);
  memset_0(v51, 0, 0x20Au);
  memset_0(v52, 0, 0x20Au);
  wcscpy_s_ex(v52, 0x105u, a3);
  if ( SymGetExtendedOption((IMAGEHLP_EXTENDED_OPTIONS)3) )
  {
    if ( (unsigned int)spew() )
      _pwprint(*((struct _PROCESS_ENTRY **)a2 + 1), L"load symbols is disabled!\n");
    return 4;
  }
  if ( !a5
    && !(unsigned int)extmatch((const unsigned __int16 *)a2 + 29, L".pdb")
    && !(unsigned int)ValidGuid(a4)
    && (dword_1802AF9CC & 0x400) != 0 )
  {
    result = 2154627078LL;
    dword_1802AF9D0 = a5 + 1;
    return result;
  }
  if ( !*((_QWORD *)a2 + 527) )
    return 19;
  v51[0] = 0;
  if ( (unsigned int)extmatch((const unsigned __int16 *)a2 + 29, L".pdb") )
  {
    wcscpy_s_ex(&v47, 0x105u, (const unsigned __int16 *)a2 + 29);
    v13 = DiaOpenPdbEx(
            &v47,
            a4,
            a5,
            a6,
            DirCount,
            *((struct DIA **)a2 + 527),
            *((struct _PROCESS_ENTRY **)a2 + 1),
            (int *)a2 + 1213,
            (unsigned __int16 *)a2 + 2140);
    if ( v13 )
      return 2154627077LL;
LABEL_35:
    *((_DWORD *)a2 + 828) = 2;
    goto LABEL_107;
  }
  if ( *((_DWORD *)a1 + 6041) == 4 && *((_WORD *)a1 + 11560) )
  {
    wcscpy_s_ex(&v47, 0x105u, (const unsigned __int16 *)a1 + 11560);
    v13 = DiaOpenPdbEx(
            &v47,
            a4,
            a5,
            a6,
            DirCount,
            *((struct DIA **)a2 + 527),
            *((struct _PROCESS_ENTRY **)a2 + 1),
            (int *)a2 + 1213,
            (unsigned __int16 *)a2 + 2140);
    if ( !v13 )
    {
      *((_DWORD *)a2 + 828) = 2;
      *((_DWORD *)a1 + 6041) = 8;
      v14 = *((_QWORD *)a2 + 527);
      if ( v14 )
        *(_DWORD *)(v14 + 48) = 8;
      goto LABEL_107;
    }
    return 2154627077LL;
  }
  v15 = *((_QWORD *)a2 + 533);
  v45 = 0;
  v13 = -2140340219;
  v40 = 0;
  v16 = 0;
  if ( *(_DWORD *)(v15 + 4) == 3 && *(_DWORD *)(v15 + 16) == 20 )
  {
    a4 = *(struct _GUID **)(v15 + 8);
    Data1 = a4[1].Data1;
  }
  else
  {
    Data1 = a6;
  }
  v39 = Data1;
  if ( a5 )
  {
    v45.Data1 = a5;
  }
  else if ( a4 )
  {
    v45 = *a4;
  }
  _wsplitpath_s(a3, 0, 0, 0, 0, Filename, 0x105u, Ext, 0x101u);
  DirCounta = L".pdb";
  swprintf_s(Buffer, 0x105u, L"%s%s", Filename);
  v19 = dword_1802AF9CC;
  if ( (dword_1802AF9CC & 0x8000000) != 0 )
  {
    if ( (dword_1802AF9CC & 0x200000) == 0 && *((_QWORD *)a2 + 138) && *((_WORD *)a2 + 29) )
    {
      _wsplitpath_s((const wchar_t *)a2 + 29, Drive, 6u, Dir, 0x105u, 0, 0, 0, 0);
      swprintf_s(&v47, 0x105u, L"%s%s%s", Drive, Dir, Buffer);
      if ( (unsigned int)diaCopyFileToCache(*((unsigned __int16 **)a2 + 2), *((HANDLE *)a2 + 449), 0, &v47, a3, 0x104u) )
      {
        wcscpy_s_ex(&v47, 0x105u, a3);
        v16 = 1;
        v40 = 1;
      }
      v13 = DiaOpenPdbEx(
              &v47,
              a4,
              a5,
              v39,
              DirCountb,
              *((struct DIA **)a2 + 527),
              *((struct _PROCESS_ENTRY **)a2 + 1),
              (int *)a2 + 1213,
              (unsigned __int16 *)a2 + 2140);
      if ( !v13 )
        goto LABEL_35;
      v19 = dword_1802AF9CC;
    }
    v20 = &v47;
    do
    {
      v21 = v20[1056];
      LODWORD(v18) = *v20 - v21;
      if ( (_DWORD)v18 )
        break;
      ++v20;
    }
    while ( v21 );
    if ( (_DWORD)v18 && (v19 & 0x80u) == 0 )
    {
      wcscpy_s_ex(&v47, 0x105u, v52);
      if ( !v16
        && (unsigned int)diaCopyFileToCache(*((unsigned __int16 **)a2 + 2), *((HANDLE *)a2 + 449), 0, &v47, a3, 0x104u) )
      {
        wcscpy_s_ex(&v47, 0x105u, a3);
        v40 = 1;
      }
      v13 = DiaOpenPdbEx(
              &v47,
              a4,
              a5,
              v39,
              (int)DirCounta,
              *((struct DIA **)a2 + 527),
              *((struct _PROCESS_ENTRY **)a2 + 1),
              (int *)a2 + 1213,
              (unsigned __int16 *)a2 + 2140);
      if ( !v13 )
      {
LABEL_94:
        *((_DWORD *)a2 + 828) = 5;
        goto LABEL_107;
      }
      v19 = dword_1802AF9CC;
    }
  }
  v22 = (unsigned __int16 *)*((_QWORD *)a2 + 2);
  v41 = 1;
  v43 = v22;
  if ( !v22 )
    goto LABEL_73;
  do
  {
    v44 = TokenFromSymbolPath(v22, Dir, v18);
    if ( Dir[0] )
    {
      if ( !IsCacheDir(Dir, v51, v18) )
        goto LABEL_52;
      if ( (unsigned int)GetFileFromCache(*((struct _PROCESS_ENTRY **)a2 + 1), a1, v51, Buffer, &v45, v39, 0, 0, &v47) )
      {
        v13 = DiaOpenPdbEx(
                &v47,
                a4,
                a5,
                v39,
                (int)DirCounta,
                *((struct DIA **)a2 + 527),
                *((struct _PROCESS_ENTRY **)a2 + 1),
                (int *)a2 + 1213,
                (unsigned __int16 *)a2 + 2140);
        if ( !v13 )
        {
          if ( (unsigned int)diaCopyFileToCache(
                               *((unsigned __int16 **)a2 + 2),
                               *((HANDLE *)a2 + 449),
                               v22,
                               &v47,
                               a3,
                               0x104u) )
            wcscpy_s_ex(&v47, 0x105u, a3);
          goto LABEL_107;
        }
LABEL_52:
        v23 = 0;
        while ( (unsigned int)symsrvTest(*((struct _PROCESS_ENTRY **)a2 + 1), Dir, v18, 1) )
        {
          if ( v23 || !v41 )
            goto LABEL_71;
          v24 = (struct _PROCESS_ENTRY *)*((_QWORD *)a2 + 1);
          v47 = 0;
          *((_DWORD *)a2 + 828) = 4;
          if ( symsrvGetFile(v24, a1, Dir, v51, Buffer, &v45, v39, 0, 0, &v47, v38) == 232 )
            goto LABEL_60;
          if ( !v47 )
          {
            if ( !a7 )
              goto LABEL_70;
            if ( symsrvGetFile(
                   *((struct _PROCESS_ENTRY **)a2 + 1),
                   a1,
                   Dir,
                   v51,
                   Buffer,
                   &v45,
                   0xFFFFFFFF,
                   0,
                   0,
                   &v47,
                   v38) == 232 )
LABEL_60:
              v41 = 0;
LABEL_66:
            if ( !v47 )
              goto LABEL_70;
          }
          if ( (unsigned int)diaCopyFileToCache(
                               *((unsigned __int16 **)a2 + 2),
                               *((HANDLE *)a2 + 449),
                               v43,
                               &v47,
                               a3,
                               0x104u) )
          {
            wcscpy_s_ex(&v47, 0x105u, a3);
            v40 = 1;
          }
          v13 = DiaOpenPdbEx(
                  &v47,
                  a4,
                  a5,
                  v39,
                  DirCountc,
                  *((struct DIA **)a2 + 527),
                  *((struct _PROCESS_ENTRY **)a2 + 1),
                  (int *)a2 + 1213,
                  (unsigned __int16 *)a2 + 2140);
          if ( !v13 )
            goto LABEL_107;
LABEL_70:
          if ( (unsigned int)++v23 >= 3 )
            goto LABEL_71;
        }
        if ( v23 && !*a8 )
          goto LABEL_71;
        *((_DWORD *)a2 + 828) = 1;
        if ( !CreateSymbolPath(v23, Dir, a8, Filename, Ext, &v47, FilenameCount) )
          goto LABEL_71;
        if ( !v23 )
        {
          v13 = CheckDirForPdbsEx(
                  &v47,
                  a4,
                  a5,
                  v39,
                  *((void **)a2 + 527),
                  *((struct _PROCESS_ENTRY **)a2 + 1),
                  (int *)a2 + 1213,
                  (unsigned __int16 *)a2 + 2140);
          if ( !v13 )
            goto LABEL_107;
        }
        goto LABEL_66;
      }
    }
LABEL_71:
    v22 = v44;
    v43 = v44;
  }
  while ( v44 );
  v19 = dword_1802AF9CC;
LABEL_73:
  if ( (v19 & 0x8000000) != 0 )
    goto LABEL_96;
  if ( (v19 & 0x200000) != 0 || !*((_QWORD *)a2 + 138) || !*((_WORD *)a2 + 29) )
  {
    v25 = v40;
    goto LABEL_85;
  }
  _wsplitpath_s((const wchar_t *)a2 + 29, Drive, 6u, Dir, 0x105u, 0, 0, 0, 0);
  DirCountd = Dir;
  swprintf_s(&v47, 0x105u, L"%s%s%s", Drive);
  v25 = v40;
  if ( !v40
    && (unsigned int)diaCopyFileToCache(*((unsigned __int16 **)a2 + 2), *((HANDLE *)a2 + 449), 0, &v47, a3, 0x104u) )
  {
    wcscpy_s_ex(&v47, 0x105u, a3);
    v25 = 1;
  }
  v13 = DiaOpenPdbEx(
          &v47,
          a4,
          a5,
          v39,
          (int)DirCountd,
          *((struct DIA **)a2 + 527),
          *((struct _PROCESS_ENTRY **)a2 + 1),
          (int *)a2 + 1213,
          (unsigned __int16 *)a2 + 2140);
  if ( !v13 )
    goto LABEL_35;
  LOBYTE(v19) = dword_1802AF9CC;
LABEL_85:
  v26 = &v47;
  do
  {
    v27 = v26[1056];
    v28 = *v26 - v27;
    if ( v28 )
      break;
    ++v26;
  }
  while ( v27 );
  if ( v28 && (v19 & 0x80u) == 0 )
  {
    wcscpy_s_ex(&v47, 0x105u, v52);
    if ( !v25
      && (unsigned int)diaCopyFileToCache(*((unsigned __int16 **)a2 + 2), *((HANDLE *)a2 + 449), 0, &v47, a3, 0x104u) )
    {
      wcscpy_s_ex(&v47, 0x105u, a3);
    }
    v13 = DiaOpenPdbEx(
            &v47,
            a4,
            a5,
            v39,
            (int)DirCounta,
            *((struct DIA **)a2 + 527),
            *((struct _PROCESS_ENTRY **)a2 + 1),
            (int *)a2 + 1213,
            (unsigned __int16 *)a2 + 2140);
    if ( !v13 )
      goto LABEL_94;
    LOBYTE(v19) = dword_1802AF9CC;
  }
LABEL_96:
  if ( *((_WORD *)a2 + 2140) )
  {
    if ( (v19 & 0x40) != 0 )
    {
      wcscpy_s_ex(&v47, 0x105u, (const unsigned __int16 *)a2 + 2140);
      v13 = DiaOpenPdbEx(
              &v47,
              0,
              0,
              0,
              (int)DirCounta,
              *((struct DIA **)a2 + 527),
              *((struct _PROCESS_ENTRY **)a2 + 1),
              (int *)a2 + 1213,
              (unsigned __int16 *)a2 + 2140);
      if ( !v13 )
        *((_DWORD *)a2 + 828) = 1;
    }
    *((_DWORD *)a2 + 1201) &= 1u;
    if ( (unsigned int)spew() )
    {
      v30 = Buffer;
      if ( *((_WORD *)a2 + 29) != v29 )
        v30 = (wchar_t *)((char *)a2 + 58);
      v31 = L"Loaded";
      if ( v13 )
        v31 = L"Couldn't load";
      _pwprint(*((struct _PROCESS_ENTRY **)a2 + 1), L"%s mismatched pdb for %s\n", v31, v30);
    }
    if ( !v13 )
    {
LABEL_107:
      wcscpy_s_ex(a3, 0x104u, &v47);
      dword_1802AF9D0 = 0;
    }
  }
  return v13;
}

```

## disassembly

```asm
0x18001b03c  push    rbp
0x18001b03e  push    rbx
0x18001b03f  push    rsi
0x18001b040  push    rdi
0x18001b041  push    r12
0x18001b043  push    r13
0x18001b045  push    r14
0x18001b047  push    r15
0x18001b049  lea     rbp, [rsp-0E38h]
0x18001b051  sub     rsp, 0F38h
0x18001b058  mov     rax, cs:__security_cookie
0x18001b05f  xor     rax, rsp
0x18001b062  mov     [rbp+0E70h+var_50], rax
0x18001b069  mov     rax, [rbp+0E70h+arg_38]
0x18001b070  mov     r15, r8
0x18001b073  mov     [rsp+0F70h+var_EF8], rax
0x18001b078  mov     rbx, rdx
0x18001b07b  xor     eax, eax
0x18001b07d  mov     [rsp+0F70h+var_F00], rcx
0x18001b082  mov     r14, rcx
0x18001b085  mov     [rbp+0E70h+var_EC0], ax
0x18001b089  xorps   xmm0, xmm0
0x18001b08c  lea     rcx, [rbp+0E70h+var_EBE]; void *
0x18001b090  xor     edx, edx; Val
0x18001b092  mov     r8d, 208h; Size
0x18001b098  mov     rsi, r9
0x18001b09b  movups  xmmword ptr [rbp+0E70h+var_EE0.Data1], xmm0
0x18001b09f  call    memset_0
0x18001b0a4  mov     edi, 20Ah
0x18001b0a9  lea     rcx, [rbp+0E70h+var_890]; void *
0x18001b0b0  mov     r8d, edi; Size
0x18001b0b3  xor     edx, edx; Val
0x18001b0b5  call    memset_0
0x18001b0ba  mov     r8d, edi; Size
0x18001b0bd  lea     rcx, [rbp+0E70h+var_680]; void *
0x18001b0c4  xor     edx, edx; Val
0x18001b0c6  call    memset_0
0x18001b0cb  mov     r12d, 105h
0x18001b0d1  lea     rcx, [rbp+0E70h+var_680]; unsigned __int16 *
0x18001b0d8  mov     edx, r12d; unsigned __int64
0x18001b0db  mov     r8, r15; unsigned __int16 *
0x18001b0de  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x18001b0e3  mov     ecx, 3; option
0x18001b0e8  call    SymGetExtendedOption
0x18001b0ed  xor     edi, edi
0x18001b0ef  test    eax, eax
0x18001b0f1  jz      short loc_18001B116
0x18001b0f3  call    ?spew@@YAHXZ; spew(void)
0x18001b0f8  test    eax, eax
0x18001b0fa  jz      short loc_18001B10C
0x18001b0fc  mov     rcx, [rbx+8]; struct _PROCESS_ENTRY *
0x18001b100  lea     rdx, aLoadSymbolsIsD; "load symbols is disabled!\n"
0x18001b107  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x18001b10c  mov     eax, 4
0x18001b111  jmp     loc_18001BC25
0x18001b116  mov     r13d, [rbp+0E70h+arg_20]
0x18001b11d  lea     rdx, aPdb_3; ".pdb"
0x18001b124  test    r13d, r13d
0x18001b127  jnz     short loc_18001B16A
0x18001b129  lea     rcx, [rbx+3Ah]; unsigned __int16 *
0x18001b12d  call    ?extmatch@@YAHPEBG0@Z; extmatch(ushort const *,ushort const *)
0x18001b132  test    eax, eax
0x18001b134  jnz     short loc_18001B163
0x18001b136  mov     rcx, rsi; struct _GUID *
0x18001b139  call    ?ValidGuid@@YAHPEAU_GUID@@@Z; ValidGuid(_GUID *)
0x18001b13e  test    eax, eax
0x18001b140  jnz     short loc_18001B163
0x18001b142  test    cs:dword_1802AF9CC, 400h
0x18001b14c  jz      short loc_18001B163
0x18001b14e  lea     r14d, [r13+1]
0x18001b152  mov     eax, 806D0006h
0x18001b157  mov     cs:dword_1802AF9D0, r14d
0x18001b15e  jmp     loc_18001BC25
0x18001b163  lea     rdx, aPdb_3; ".pdb"
0x18001b16a  cmp     [rbx+1078h], rdi
0x18001b171  jnz     short loc_18001B17D
0x18001b173  mov     eax, 13h
0x18001b178  jmp     loc_18001BC25
0x18001b17d  lea     rcx, [rbx+3Ah]; unsigned __int16 *
0x18001b181  mov     [rbp+0E70h+var_890], di
0x18001b188  call    ?extmatch@@YAHPEBG0@Z; extmatch(ushort const *,ushort const *)
0x18001b18d  xor     ecx, ecx
0x18001b18f  test    eax, eax
0x18001b191  jz      short loc_18001B1FA
0x18001b193  lea     r8, [rbx+3Ah]; unsigned __int16 *
0x18001b197  mov     rdx, r12; unsigned __int64
0x18001b19a  lea     rcx, [rbp+0E70h+var_EC0]; unsigned __int16 *
0x18001b19e  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x18001b1a3  mov     r9d, [rbp+0E70h+arg_28]; unsigned int
0x18001b1aa  lea     rax, [rbx+10B8h]
0x18001b1b1  mov     [rsp+0F70h+ExtCount], rax; unsigned __int16 *
0x18001b1b6  lea     rcx, [rbx+12F4h]
0x18001b1bd  mov     rax, [rbx+8]
0x18001b1c1  mov     r8d, r13d; unsigned int
0x18001b1c4  mov     [rsp+0F70h+Ext], rcx; int *
0x18001b1c9  mov     rdx, rsi; struct _GUID *
0x18001b1cc  mov     [rsp+0F70h+FilenameCount], rax; struct _PROCESS_ENTRY *
0x18001b1d1  lea     rcx, [rbp+0E70h+var_EC0]; unsigned __int16 *
0x18001b1d5  mov     rax, [rbx+1078h]
0x18001b1dc  mov     [rsp+0F70h+Filename], rax; struct DIA *
0x18001b1e1  call    ?DiaOpenPdbEx@@YAJPEBGPEAU_GUID@@KKHPEAXPEAU_PROCESS_ENTRY@@PEAHPEAG@Z; DiaOpenPdbEx(ushort const *,_GUID *,ulong,ulong,int,void *,_PROCESS_ENTRY *,int *,ushort *)
0x18001b1e6  mov     edi, eax
0x18001b1e8  test    eax, eax
0x18001b1ea  jz      loc_18001B47D
0x18001b1f0  mov     eax, 806D0005h
0x18001b1f5  jmp     loc_18001BC25
0x18001b1fa  cmp     dword ptr [r14+5E64h], 4
0x18001b202  jnz     loc_18001B29A
0x18001b208  lea     r8, [r14+5A50h]; unsigned __int16 *
0x18001b20f  cmp     [r8], cx
0x18001b213  jz      loc_18001B29A
0x18001b219  mov     rdx, r12; unsigned __int64
0x18001b21c  lea     rcx, [rbp+0E70h+var_EC0]; unsigned __int16 *
0x18001b220  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x18001b225  mov     r9d, [rbp+0E70h+arg_28]; unsigned int
0x18001b22c  lea     rax, [rbx+10B8h]
0x18001b233  mov     [rsp+0F70h+ExtCount], rax; unsigned __int16 *
0x18001b238  lea     rcx, [rbx+12F4h]
0x18001b23f  mov     rax, [rbx+8]
0x18001b243  mov     r8d, r13d; unsigned int
0x18001b246  mov     [rsp+0F70h+Ext], rcx; int *
0x18001b24b  mov     rdx, rsi; struct _GUID *
0x18001b24e  mov     [rsp+0F70h+FilenameCount], rax; struct _PROCESS_ENTRY *
0x18001b253  lea     rcx, [rbp+0E70h+var_EC0]; unsigned __int16 *
0x18001b257  mov     rax, [rbx+1078h]
0x18001b25e  mov     [rsp+0F70h+Filename], rax; struct DIA *
0x18001b263  call    ?DiaOpenPdbEx@@YAJPEBGPEAU_GUID@@KKHPEAXPEAU_PROCESS_ENTRY@@PEAHPEAG@Z; DiaOpenPdbEx(ushort const *,_GUID *,ulong,ulong,int,void *,_PROCESS_ENTRY *,int *,ushort *)
0x18001b268  mov     edi, eax
0x18001b26a  test    eax, eax
0x18001b26c  jnz     short loc_18001B1F0
0x18001b26e  lea     edx, [rax+8]
0x18001b271  mov     dword ptr [rbx+0CF0h], 2
0x18001b27b  mov     [r14+5E64h], edx
0x18001b282  mov     rax, [rbx+1078h]
0x18001b289  test    rax, rax
0x18001b28c  jz      loc_18001BC08
0x18001b292  mov     [rax+30h], edx
0x18001b295  jmp     loc_18001BC08
0x18001b29a  mov     rax, [rbx+10A8h]
0x18001b2a1  xorps   xmm0, xmm0
0x18001b2a4  movups  xmmword ptr [rbp+0E70h+var_EE0.Data1], xmm0
0x18001b2a8  mov     edi, 806D0005h
0x18001b2ad  mov     [rsp+0F70h+var_F0C], ecx
0x18001b2b1  mov     r12d, ecx
0x18001b2b4  cmp     dword ptr [rax+4], 3
0x18001b2b8  jnz     short loc_18001B2C9
0x18001b2ba  cmp     dword ptr [rax+10h], 14h
0x18001b2be  jnz     short loc_18001B2C9
0x18001b2c0  mov     rsi, [rax+8]
0x18001b2c4  mov     eax, [rsi+10h]
0x18001b2c7  jmp     short loc_18001B2CF
0x18001b2c9  mov     eax, [rbp+0E70h+arg_28]
0x18001b2cf  mov     [rsp+0F70h+var_F10], eax
0x18001b2d3  test    r13d, r13d
0x18001b2d6  jz      short loc_18001B2DE
0x18001b2d8  mov     [rbp+0E70h+var_EE0.Data1], r13d
0x18001b2dc  jmp     short loc_18001B2EB
0x18001b2de  test    rsi, rsi
0x18001b2e1  jz      short loc_18001B2EB
0x18001b2e3  movups  xmm0, xmmword ptr [rsi]
0x18001b2e6  movdqu  xmmword ptr [rbp+0E70h+var_EE0.Data1], xmm0
0x18001b2eb  mov     [rsp+0F70h+ExtCount], 101h; ExtCount
0x18001b2f4  lea     rax, [rbp+0E70h+var_260]
0x18001b2fb  mov     [rsp+0F70h+Ext], rax; Ext
0x18001b300  mov     r14d, 105h
0x18001b306  lea     rax, [rbp+0E70h+var_470]
0x18001b30d  mov     [rsp+0F70h+FilenameCount], r14; FilenameCount
0x18001b312  mov     [rsp+0F70h+Filename], rax; Filename
0x18001b317  xor     r9d, r9d; Dir
0x18001b31a  mov     [rsp+0F70h+DirCount], rcx; DirCount
0x18001b31f  xor     r8d, r8d; DriveCount
0x18001b322  mov     rcx, r15; FullPath
0x18001b325  xor     edx, edx; Drive
0x18001b327  call    cs:__imp__wsplitpath_s
0x18001b32d  lea     rax, aPdb_3; ".pdb"
0x18001b334  mov     edx, r14d; BufferCount
0x18001b337  lea     r9, [rbp+0E70h+var_470]
0x18001b33e  mov     [rsp+0F70h+DirCount], rax
0x18001b343  lea     r8, aSS_3; "%s%s"
0x18001b34a  lea     rcx, [rbp+0E70h+Buffer]; Buffer
0x18001b351  call    swprintf_s
0x18001b356  mov     eax, cs:dword_1802AF9CC
0x18001b35c  xor     r10d, r10d
0x18001b35f  mov     r14d, 1
0x18001b365  bt      eax, 1Bh
0x18001b369  jnb     loc_18001B57D
0x18001b36f  bt      eax, 15h
0x18001b373  jb      loc_18001B492
0x18001b379  cmp     [rbx+450h], r10
0x18001b380  jz      loc_18001B492
0x18001b386  lea     rcx, [rbx+3Ah]; FullPath
0x18001b38a  cmp     [rcx], r10w
0x18001b38e  jz      loc_18001B492
0x18001b394  mov     [rsp+0F70h+ExtCount], r10; ExtCount
0x18001b399  lea     r9, [rbp+0E70h+Dir]; Dir
0x18001b3a0  mov     [rsp+0F70h+Ext], r10; Ext
0x18001b3a5  lea     r8d, [r14+5]; DriveCount
0x18001b3a9  mov     [rsp+0F70h+FilenameCount], r10; FilenameCount
0x18001b3ae  lea     rdx, [rbp+0E70h+Drive]; Drive
0x18001b3b2  mov     [rsp+0F70h+Filename], r10; Filename
0x18001b3b7  mov     edi, 105h
0x18001b3bc  mov     [rsp+0F70h+DirCount], rdi; DirCount
0x18001b3c1  call    cs:__imp__wsplitpath_s
0x18001b3c7  lea     rax, [rbp+0E70h+Buffer]
0x18001b3ce  mov     edx, edi; BufferCount
0x18001b3d0  mov     [rsp+0F70h+Filename], rax
0x18001b3d5  lea     r9, [rbp+0E70h+Drive]
0x18001b3d9  lea     rax, [rbp+0E70h+Dir]
0x18001b3e0  lea     r8, aSSS; "%s%s%s"
0x18001b3e7  mov     [rsp+0F70h+DirCount], rax
0x18001b3ec  lea     rcx, [rbp+0E70h+var_EC0]; Buffer
0x18001b3f0  call    swprintf_s
0x18001b3f5  mov     rdx, [rbx+0E08h]; hProcess
0x18001b3fc  lea     r9, [rbp+0E70h+var_EC0]; unsigned __int16 *
0x18001b400  mov     rcx, [rbx+10h]; unsigned __int16 *
0x18001b404  xor     r8d, r8d; unsigned __int16 *
0x18001b407  mov     dword ptr [rsp+0F70h+Filename], 104h; unsigned int
0x18001b40f  mov     [rsp+0F70h+DirCount], r15; int
0x18001b414  call    ?diaCopyFileToCache@@YAHPEAGPEAX000K@Z; diaCopyFileToCache(ushort *,void *,ushort *,ushort *,ushort *,ulong)
0x18001b419  test    eax, eax
0x18001b41b  jz      short loc_18001B433
0x18001b41d  mov     r8, r15; unsigned __int16 *
0x18001b420  lea     rcx, [rbp+0E70h+var_EC0]; unsigned __int16 *
0x18001b424  mov     edx, edi; unsigned __int64
0x18001b426  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x18001b42b  mov     r12d, r14d
0x18001b42e  mov     [rsp+0F70h+var_F0C], r14d
0x18001b433  mov     r9d, [rsp+0F70h+var_F10]; unsigned int
0x18001b438  lea     rax, [rbx+10B8h]
0x18001b43f  mov     [rsp+0F70h+ExtCount], rax; unsigned __int16 *
0x18001b444  lea     rcx, [rbx+12F4h]
0x18001b44b  mov     rax, [rbx+8]
0x18001b44f  mov     r8d, r13d; unsigned int
0x18001b452  mov     [rsp+0F70h+Ext], rcx; int *
0x18001b457  mov     rdx, rsi; struct _GUID *
0x18001b45a  mov     [rsp+0F70h+FilenameCount], rax; struct _PROCESS_ENTRY *
0x18001b45f  lea     rcx, [rbp+0E70h+var_EC0]; unsigned __int16 *
0x18001b463  mov     rax, [rbx+1078h]
0x18001b46a  mov     [rsp+0F70h+Filename], rax; struct DIA *
0x18001b46f  call    ?DiaOpenPdbEx@@YAJPEBGPEAU_GUID@@KKHPEAXPEAU_PROCESS_ENTRY@@PEAHPEAG@Z; DiaOpenPdbEx(ushort const *,_GUID *,ulong,ulong,int,void *,_PROCESS_ENTRY *,int *,ushort *)
0x18001b474  xor     r10d, r10d
0x18001b477  mov     edi, eax
0x18001b479  test    eax, eax
0x18001b47b  jnz     short loc_18001B48C
0x18001b47d  mov     dword ptr [rbx+0CF0h], 2
0x18001b487  jmp     loc_18001BC08
0x18001b48c  mov     eax, cs:dword_1802AF9CC
0x18001b492  lea     rcx, [rbp+0E70h+var_EC0]
0x18001b496  lea     r9, [rbp+0E70h+var_680]
0x18001b49d  sub     r9, rcx
0x18001b4a0  movzx   r8d, word ptr [rcx]
0x18001b4a4  movzx   edx, word ptr [rcx+r9]
0x18001b4a9  sub     r8d, edx; int
0x18001b4ac  jnz     short loc_18001B4B6
0x18001b4ae  add     rcx, 2
0x18001b4b2  test    edx, edx
0x18001b4b4  jnz     short loc_18001B4A0
0x18001b4b6  test    r8d, r8d
0x18001b4b9  jz      loc_18001B575
0x18001b4bf  test    al, al
0x18001b4c1  js      loc_18001B575
0x18001b4c7  lea     r8, [rbp+0E70h+var_680]; unsigned __int16 *
0x18001b4ce  mov     edx, 105h; unsigned __int64
0x18001b4d3  lea     rcx, [rbp+0E70h+var_EC0]; unsigned __int16 *
0x18001b4d7  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x18001b4dc  test    r12d, r12d
0x18001b4df  jnz     short loc_18001B51F
0x18001b4e1  mov     rdx, [rbx+0E08h]; hProcess
0x18001b4e8  lea     r9, [rbp+0E70h+var_EC0]; unsigned __int16 *
0x18001b4ec  mov     rcx, [rbx+10h]; unsigned __int16 *
0x18001b4f0  xor     r8d, r8d; unsigned __int16 *
0x18001b4f3  mov     dword ptr [rsp+0F70h+Filename], 104h; unsigned int
0x18001b4fb  mov     [rsp+0F70h+DirCount], r15; int
0x18001b500  call    ?diaCopyFileToCache@@YAHPEAGPEAX000K@Z; diaCopyFileToCache(ushort *,void *,ushort *,ushort *,ushort *,ulong)
0x18001b505  test    eax, eax
0x18001b507  jz      short loc_18001B51F
0x18001b509  mov     r8, r15; unsigned __int16 *
0x18001b50c  lea     rcx, [rbp+0E70h+var_EC0]; unsigned __int16 *
0x18001b510  mov     edx, 105h; unsigned __int64
0x18001b515  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x18001b51a  mov     [rsp+0F70h+var_F0C], r14d
0x18001b51f  mov     r9d, [rsp+0F70h+var_F10]; unsigned int
0x18001b524  lea     rax, [rbx+10B8h]
0x18001b52b  mov     [rsp+0F70h+ExtCount], rax; unsigned __int16 *
0x18001b530  lea     rcx, [rbx+12F4h]
0x18001b537  mov     rax, [rbx+8]
0x18001b53b  mov     r8d, r13d; unsigned int
0x18001b53e  mov     [rsp+0F70h+Ext], rcx; int *
0x18001b543  mov     rdx, rsi; struct _GUID *
0x18001b546  mov     [rsp+0F70h+FilenameCount], rax; struct _PROCESS_ENTRY *
0x18001b54b  lea     rcx, [rbp+0E70h+var_EC0]; unsigned __int16 *
0x18001b54f  mov     rax, [rbx+1078h]
0x18001b556  mov     [rsp+0F70h+Filename], rax; struct DIA *
0x18001b55b  call    ?DiaOpenPdbEx@@YAJPEBGPEAU_GUID@@KKHPEAXPEAU_PROCESS_ENTRY@@PEAHPEAG@Z; DiaOpenPdbEx(ushort const *,_GUID *,ulong,ulong,int,void *,_PROCESS_ENTRY *,int *,ushort *)
0x18001b560  xor     r10d, r10d
0x18001b563  mov     edi, eax
0x18001b565  test    eax, eax
0x18001b567  jz      loc_18001BB30
0x18001b56d  mov     eax, cs:dword_1802AF9CC
0x18001b573  jmp     short loc_18001B57D
  ... truncated ...
```
