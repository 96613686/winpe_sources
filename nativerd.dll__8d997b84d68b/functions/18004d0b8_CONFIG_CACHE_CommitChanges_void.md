# CONFIG_CACHE::CommitChanges(void)

- ea: `0x18004d0b8`
- end: `0x18004d66e`
- name: `?CommitChanges@CONFIG_CACHE@@QEAAJXZ`
- size: `1462`
- prototype: `__int64 __fastcall(unsigned int **this)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180039f40`

## callees

- `0x180001080`
- `0x180008d00`
- `0x1800100d0`
- `0x180010468`
- `0x180015230`
- `0x1800155a0`
- `0x180015620`
- `0x180015ee0`
- `0x180016440`
- `0x1800178bc`
- `0x18001a588`
- `0x18001a648`
- `0x18001be64`
- `0x18001c250`
- `0x18001fda0`
- `0x1800225cc`
- `0x1800273e8`
- `0x18004127c`
- `0x18004d0b8`
- `0x18004db44`
- `0x18004f1a0`
- `0x18005207c`
- `0x180058ba0`
- `0x180059bea`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18004d3e5`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18004d3e5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004d62c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004d639`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004d643`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004d62c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004d639`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004d643`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004d22e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004d317`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004d434`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004d48d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004d512`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004d22e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004d317`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004d434`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004d48d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004d512`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18004d11c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18004d14e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18004d173`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18004d11c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18004d14e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18004d173`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004d212`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004d212`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18004d5f4`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18004d5f4`

## pseudocode

```c
__int64 __fastcall CONFIG_CACHE::CommitChanges(unsigned int **this)
{
  unsigned int v1; // r15d
  int v3; // r14d
  int v4; // r12d
  int PathString; // ebx
  const unsigned __int16 *Str; // rax
  struct _PATH_CACHE_NODE *v7; // rdi
  unsigned int *v8; // rax
  __int64 v9; // r9
  __int64 v10; // rdx
  struct _PATH_CACHE_NODE *v11; // r15
  const FILETIME *v12; // rdx
  unsigned int v13; // ebx
  int dwHighDateTime; // ecx
  DWORD dwLowDateTime; // r13d
  __int64 v16; // rax
  const FILETIME *v17; // rcx
  unsigned __int16 *v18; // rax
  __int64 v19; // rcx
  CONFIG_CHANGE_NOTIFIER *v20; // rbx
  const unsigned __int16 *v21; // rax
  __int64 v22; // rax
  __int64 v23; // r12
  char v24; // r15
  unsigned int *v25; // rbx
  const WCHAR *v26; // rdi
  unsigned int v27; // eax
  CONFIG_FILE *v28; // rcx
  const unsigned __int16 *ParseErrorFileName; // rax
  CONFIG_EXCEPTION *v30; // rax
  CONFIG_EXCEPTION *v31; // rax
  IErrorInfo *v32; // rdi
  int v34; // [rsp+40h] [rbp-C0h]
  struct PARSE_ERROR_INFO *v35; // [rsp+48h] [rbp-B8h]
  int v36; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v37; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v38; // [rsp+68h] [rbp-98h] BYREF
  struct _PATH_CACHE_NODE *v39; // [rsp+70h] [rbp-90h] BYREF
  struct _PATH_CACHE_NODE *v40; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v41; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v42; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v43[2]; // [rsp+90h] [rbp-70h] BYREF
  int v44; // [rsp+A0h] [rbp-60h]
  __int64 v45; // [rsp+A8h] [rbp-58h]
  _OWORD v46[2]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v47[2]; // [rsp+D0h] [rbp-30h] BYREF
  int v48; // [rsp+E0h] [rbp-20h]
  __int64 v49; // [rsp+E8h] [rbp-18h]
  __int128 v50; // [rsp+F0h] [rbp-10h]
  __int128 v51; // [rsp+100h] [rbp+0h]
  _BYTE v52[56]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v53[56]; // [rsp+148h] [rbp+48h] BYREF
  _BYTE v54[64]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int16 v55[64]; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned __int16 v56[264]; // [rsp+240h] [rbp+140h] BYREF
  unsigned __int16 v57[264]; // [rsp+450h] [rbp+350h] BYREF

  v1 = 0;
  v42 = 0;
  v37 = 0;
  v38 = 0;
  memset_0(v55, 0, sizeof(v55));
  STRU::STRU((STRU *)v52, v55, 0x40u);
  memset_0(v56, 0, 0x208u);
  STRU::STRU((STRU *)v54, v56, 0x104u);
  memset_0(v57, 0, 0x208u);
  STRU::STRU((STRU *)v53, v57, 0x104u);
  v39 = 0;
  v43[0] = &PARSE_ERROR_INFO::`vftable';
  memset(v46, 0, sizeof(v46));
  v3 = 1;
  v47[0] = &PARSE_ERROR_INFO::`vftable';
  v50 = 0;
  v4 = 0;
  v51 = 0;
  v40 = 0;
  v43[1] = 1;
  v44 = 0;
  v45 = 0;
  v47[1] = 1;
  v48 = 0;
  v49 = 0;
  v41 = 0;
  v36 = 0;
  CONFIG_CACHE::WriteLock((CONFIG_CACHE *)this);
  PathString = PATH::GetPathString(
                 (PATH *)(this + 44),
                 *((_DWORD *)this + 94) - 1,
                 (const unsigned __int16 **)&v42,
                 &v37,
                 0);
  if ( PathString < 0 )
    goto LABEL_52;
  PathString = STRU::Copy((STRU *)v52, v42);
  PATH::RevertString((PATH *)(this + 44));
  if ( PathString < 0 )
    goto LABEL_52;
  Str = STRU::QueryStr((STRU *)v52);
  PathString = PATH_CACHE::GetNode((PATH_CACHE *)(this + 3), Str, v37, &v39);
  if ( PathString < 0 )
    goto LABEL_52;
  v7 = v39;
  v8 = this[99];
  if ( v39 )
  {
    if ( !v8 )
    {
      v9 = 3221228259LL;
      PathString = -2147024883;
      goto LABEL_12;
    }
    if ( *((_DWORD *)this + 203) )
    {
      v11 = v39;
      while ( v11 || v4 )
      {
        PathString = CONFIG_CACHE::GetNodeChanged(
                       (CONFIG_CACHE *)this,
                       (struct PATH *)(this + 44),
                       v7,
                       &v36,
                       (struct PARSE_ERROR_INFO *)v47);
        if ( PathString < 0 )
          goto LABEL_52;
        v11 = (struct _PATH_CACHE_NODE *)*((_QWORD *)v11 + 1);
        v4 = v36;
      }
      v1 = 0;
    }
LABEL_23:
    v12 = (const FILETIME *)this[99];
    v13 = 0;
    dwHighDateTime = v12[8].dwHighDateTime;
    dwLowDateTime = v12[8].dwLowDateTime;
    v36 = dwHighDateTime;
    if ( v7 )
    {
      v16 = *((_QWORD *)v7 + 4);
      if ( v16 )
      {
        v1 = *(_DWORD *)(v16 + 64);
        v13 = *(_DWORD *)(v16 + 68);
      }
    }
    if ( v7 )
    {
      v17 = (const FILETIME *)*((_QWORD *)v7 + 4);
      if ( v17 && !CompareFileTime(v17 + 7, v12 + 7) )
      {
        PathString = CONFIG_FILE::HandleMergedCommitElements(*((CONFIG_FILE **)v7 + 4));
        if ( PathString >= 0 )
        {
          PathString = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)v7 + 4) + 16LL) + 80LL))(*((_QWORD *)v7 + 4) + 16LL);
          if ( PathString >= 0 )
          {
            if ( Microsoft_Windows_IIS_ConfigurationEnableBits < 0 )
            {
              v18 = STRU::QueryStr((STRU *)v52);
              McTemplateU0z_EtwEventWriteTransfer(v19, NATIVERD_EVENT_CHANGES_SUCCESSFULLY_COMMITTED, v18);
            }
            PathString = CONFIG_CACHE::DeleteNode((CONFIG_CACHE *)this, v7, 1);
            if ( PathString >= 0 )
            {
              (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)this[99] + 16LL))(this[99]);
              this[99] = 0;
              CONFIG_CACHE::WriteUnlock((CONFIG_CACHE *)this);
              v20 = (CONFIG_CHANGE_NOTIFIER *)*this;
              v3 = 0;
              v21 = STRU::QueryStr((STRU *)v52);
              PathString = CONFIG_CHANGE_NOTIFIER::InformListenersChangeNotification(v20, v21, 0);
            }
          }
        }
        goto LABEL_52;
      }
      dwHighDateTime = v36;
    }
    if ( (Microsoft_Windows_IIS_ConfigurationEnableBits & 4) != 0 )
    {
      v40 = (struct _PATH_CACHE_NODE *)__PAIR64__(v1, v13);
      if ( v7 && (v22 = *((_QWORD *)v7 + 4)) != 0 )
        v23 = v22 + 56;
      else
        v23 = 0;
      v24 = v7 && *((_QWORD *)v7 + 4);
      v25 = this[99];
      v26 = &szDomain;
      v39 = (struct _PATH_CACHE_NODE *)__PAIR64__(dwLowDateTime, dwHighDateTime);
      if ( *((_QWORD *)v25 + 5) )
        v26 = (const WCHAR *)*((_QWORD *)v25 + 5);
      v27 = (unsigned int)STRU::QueryStr((STRU *)v52);
      McTemplateU0zztmxtmxt_EtwEventWriteTransfer(
        (_DWORD)v39,
        (unsigned int)NATIVERD_EVENT_CANNOT_COMMIT_CHANGES_DUE_TO_STALE_CONFIG_VIEW,
        v27,
        (_DWORD)v26,
        1,
        (__int64)(v25 + 14),
        (char)v39,
        v24,
        v23,
        (char)v40,
        0);
    }
    v28 = (CONFIG_FILE *)this[99];
    if ( v28 )
    {
      ParseErrorFileName = CONFIG_FILE::QueryParseErrorFileName(v28);
      SMALL_STRU::Copy((SMALL_STRU *)v46, ParseErrorFileName);
    }
    PathString = -2147024864;
    v9 = 3221228275LL;
    v10 = 2147942432LL;
    goto LABEL_51;
  }
  if ( v8 )
    goto LABEL_23;
  if ( (((_BYTE)this[48] & 4) == 0
     || CONFIG_CACHE::GetApplicationHost((CONFIG_CACHE *)this, *this[2], (struct PARSE_ERROR_INFO *)v47) >= 0)
    && (int)CONFIG_CACHE::CacheLookup((CONFIG_CACHE *)this, (struct PATH *)(this + 44), &v40) >= 0
    && CONFIG_PATH_MAPPER::MapConfig(
         (CONFIG_PATH_MAPPER *)(this + 8),
         (struct PATH *)(this + 44),
         *((_DWORD *)this + 94) - 1,
         v40,
         (struct STRU *)v54,
         (struct STRU *)v53,
         0,
         &v38,
         0,
         (struct PARSE_ERROR_INFO *)v47) >= 0 )
  {
    if ( (v38 & 0x1000) != 0 )
    {
      PathString = -2147024883;
      v41 = STRU::QueryStr((STRU *)v52);
      v9 = 3221228212LL;
LABEL_12:
      v10 = 2147942413LL;
LABEL_51:
      PARSE_ERROR_INFO::SetErrorInfo(v43, v10, 4, v9, &v41, 0, 0, 0, v34, v35);
      goto LABEL_52;
    }
    PathString = 0;
  }
LABEL_52:
  if ( (unsigned int)PARSE_ERROR_INFO::QueryIsSet((PARSE_ERROR_INFO *)v43) )
  {
    v30 = (CONFIG_EXCEPTION *)operator new(0x178u);
    if ( v30 )
    {
      v31 = CONFIG_EXCEPTION::CONFIG_EXCEPTION(v30);
      v32 = (IErrorInfo *)v31;
      if ( v31 )
      {
        if ( (int)CONFIG_EXCEPTION::Create(v31, (struct PARSE_ERROR_INFO *)v43) >= 0 )
          SetErrorInfo(0, v32 + 1);
        ((void (__fastcall *)(IErrorInfo *))v32->lpVtbl->Release)(v32);
      }
    }
  }
  if ( v3 )
    CONFIG_CACHE::WriteUnlock((CONFIG_CACHE *)this);
  PARSE_ERROR_INFO::~PARSE_ERROR_INFO((PARSE_ERROR_INFO *)v47);
  PARSE_ERROR_INFO::~PARSE_ERROR_INFO((PARSE_ERROR_INFO *)v43);
  STRU::~STRU((STRU *)v53);
  STRU::~STRU((STRU *)v54);
  STRU::~STRU((STRU *)v52);
  return (unsigned int)PathString;
}

```

## disassembly

```asm
0x18004d0b8  push    rbp
0x18004d0ba  push    rbx
0x18004d0bb  push    rsi
0x18004d0bc  push    rdi
0x18004d0bd  push    r12
0x18004d0bf  push    r13
0x18004d0c1  push    r14
0x18004d0c3  push    r15
0x18004d0c5  lea     rbp, [rsp-578h]
0x18004d0cd  sub     rsp, 678h
0x18004d0d4  mov     rax, cs:__security_cookie
0x18004d0db  xor     rax, rsp
0x18004d0de  mov     [rbp+5B0h+var_50], rax
0x18004d0e5  xor     r15d, r15d
0x18004d0e8  mov     rsi, rcx
0x18004d0eb  lea     rcx, [rbp+5B0h+var_4F0]; void *
0x18004d0f2  mov     [rbp+5B0h+var_628], r15
0x18004d0f6  xor     edx, edx; Val
0x18004d0f8  mov     [rsp+6B0h+var_64C], r15d
0x18004d0fd  mov     r8d, 80h; Size
0x18004d103  mov     [rsp+6B0h+var_648], r15d
0x18004d108  call    memset_0
0x18004d10d  lea     r8d, [r15+40h]
0x18004d111  lea     rdx, [rbp+5B0h+var_4F0]
0x18004d118  lea     rcx, [rbp+5B0h+var_5A0]
0x18004d11c  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18004d122  mov     edi, 208h
0x18004d127  lea     rcx, [rbp+5B0h+var_470]; void *
0x18004d12e  mov     r8d, edi; Size
0x18004d131  xor     edx, edx; Val
0x18004d133  call    memset_0
0x18004d138  mov     ebx, 104h
0x18004d13d  lea     rdx, [rbp+5B0h+var_470]
0x18004d144  mov     r8d, ebx
0x18004d147  lea     rcx, [rbp+5B0h+var_530]
0x18004d14e  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18004d154  mov     r8d, edi; Size
0x18004d157  lea     rcx, [rbp+5B0h+var_260]; void *
0x18004d15e  xor     edx, edx; Val
0x18004d160  call    memset_0
0x18004d165  mov     r8d, ebx
0x18004d168  lea     rdx, [rbp+5B0h+var_260]
0x18004d16f  lea     rcx, [rbp+5B0h+var_568]
0x18004d173  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18004d179  lea     rax, ??_7PARSE_ERROR_INFO@@6B@; const PARSE_ERROR_INFO::`vftable'
0x18004d180  mov     [rsp+6B0h+var_640], r15
0x18004d185  xorps   xmm0, xmm0
0x18004d188  mov     [rbp+5B0h+var_620], rax
0x18004d18c  xorps   xmm1, xmm1
0x18004d18f  movdqa  [rbp+5B0h+var_600], xmm0
0x18004d194  lea     r14d, [r15+1]
0x18004d198  movdqa  [rbp+5B0h+var_5F0], xmm1
0x18004d19d  mov     rcx, rsi; this
0x18004d1a0  mov     [rbp+5B0h+var_5E0], rax
0x18004d1a4  movdqa  [rbp+5B0h+var_5C0], xmm0
0x18004d1a9  mov     r12d, r15d
0x18004d1ac  movdqa  [rbp+5B0h+var_5B0], xmm1
0x18004d1b1  mov     [rsp+6B0h+var_638], r15
0x18004d1b6  mov     [rbp+5B0h+var_618], r14
0x18004d1ba  mov     [rbp+5B0h+var_610], r15d
0x18004d1be  mov     [rbp+5B0h+var_608], r15
0x18004d1c2  mov     [rbp+5B0h+var_5D8], r14
0x18004d1c6  mov     [rbp+5B0h+var_5D0], r15d
0x18004d1ca  mov     [rbp+5B0h+var_5C8], r15
0x18004d1ce  mov     [rbp+5B0h+var_630], r15
0x18004d1d2  mov     [rsp+6B0h+var_650], r15d
0x18004d1d7  call    ?WriteLock@CONFIG_CACHE@@AEAAXXZ; CONFIG_CACHE::WriteLock(void)
0x18004d1dc  lea     r13, [rsi+160h]
0x18004d1e3  mov     [rsp+6B0h+var_690], r15; unsigned __int64 *
0x18004d1e8  mov     edx, [r13+18h]
0x18004d1ec  lea     r9, [rsp+6B0h+var_64C]; unsigned int *
0x18004d1f1  sub     edx, r14d; unsigned int
0x18004d1f4  lea     r8, [rbp+5B0h+var_628]; unsigned __int16 **
0x18004d1f8  mov     rcx, r13; this
0x18004d1fb  call    ?GetPathString@PATH@@QEAAJKPEAPEBGPEAKPEA_K@Z; PATH::GetPathString(ulong,ushort const * *,ulong *,unsigned __int64 *)
0x18004d200  mov     ebx, eax
0x18004d202  test    eax, eax
0x18004d204  js      loc_18004D5B2
0x18004d20a  mov     rdx, [rbp+5B0h+var_628]
0x18004d20e  lea     rcx, [rbp+5B0h+var_5A0]
0x18004d212  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18004d218  mov     rcx, r13; this
0x18004d21b  mov     ebx, eax
0x18004d21d  call    ?RevertString@PATH@@QEAAXXZ; PATH::RevertString(void)
0x18004d222  test    ebx, ebx
0x18004d224  js      loc_18004D5B2
0x18004d22a  lea     rcx, [rbp+5B0h+var_5A0]
0x18004d22e  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18004d234  mov     r8d, [rsp+6B0h+var_64C]; unsigned int
0x18004d239  lea     rcx, [rsi+18h]; this
0x18004d23d  mov     rdx, rax; unsigned __int16 *
0x18004d240  lea     r9, [rsp+6B0h+var_640]; struct _PATH_CACHE_NODE **
0x18004d245  call    ?GetNode@PATH_CACHE@@QEAAJPEBGKPEAPEAU_PATH_CACHE_NODE@@@Z; PATH_CACHE::GetNode(ushort const *,ulong,_PATH_CACHE_NODE * *)
0x18004d24a  mov     ebx, eax
0x18004d24c  test    eax, eax
0x18004d24e  js      loc_18004D5B2
0x18004d254  mov     rdi, [rsp+6B0h+var_640]
0x18004d259  mov     rax, [rsi+318h]
0x18004d260  test    rdi, rdi
0x18004d263  jnz     loc_18004D336
0x18004d269  test    rax, rax
0x18004d26c  jnz     loc_18004D394
0x18004d272  test    byte ptr [rsi+180h], 4
0x18004d279  jz      short loc_18004D295
0x18004d27b  mov     rdx, [rsi+10h]
0x18004d27f  lea     r8, [rbp+5B0h+var_5E0]; struct PARSE_ERROR_INFO *
0x18004d283  mov     rcx, rsi; this
0x18004d286  mov     edx, [rdx]; unsigned int
0x18004d288  call    ?GetApplicationHost@CONFIG_CACHE@@AEAAJKPEAVPARSE_ERROR_INFO@@@Z; CONFIG_CACHE::GetApplicationHost(ulong,PARSE_ERROR_INFO *)
0x18004d28d  test    eax, eax
0x18004d28f  js      loc_18004D5B2
0x18004d295  lea     r8, [rsp+6B0h+var_638]; struct _PATH_CACHE_NODE **
0x18004d29a  mov     rdx, r13; struct PATH *
0x18004d29d  mov     rcx, rsi; this
0x18004d2a0  call    ?CacheLookup@CONFIG_CACHE@@AEAAJPEAVPATH@@PEAPEAU_PATH_CACHE_NODE@@@Z; CONFIG_CACHE::CacheLookup(PATH *,_PATH_CACHE_NODE * *)
0x18004d2a5  test    eax, eax
0x18004d2a7  js      loc_18004D5B2
0x18004d2ad  mov     r8d, [rsi+178h]
0x18004d2b4  lea     rax, [rbp+5B0h+var_5E0]
0x18004d2b8  mov     r9, [rsp+6B0h+var_638]; struct _PATH_CACHE_NODE *
0x18004d2bd  lea     rcx, [rsi+40h]; this
0x18004d2c1  mov     [rsp+6B0h+var_668], rax; struct PARSE_ERROR_INFO *
0x18004d2c6  sub     r8d, r14d; unsigned int
0x18004d2c9  mov     [rsp+6B0h+var_670], r15; struct CONFIG_VDIR **
0x18004d2ce  lea     rax, [rsp+6B0h+var_648]
0x18004d2d3  mov     [rsp+6B0h+var_678], rax; unsigned int *
0x18004d2d8  mov     rdx, r13; struct PATH *
0x18004d2db  lea     rax, [rbp+5B0h+var_568]
0x18004d2df  mov     [rsp+6B0h+var_680], r15; void **
0x18004d2e4  mov     [rsp+6B0h+var_688], rax; struct STRU *
0x18004d2e9  lea     rax, [rbp+5B0h+var_530]
0x18004d2f0  mov     [rsp+6B0h+var_690], rax; struct STRU *
0x18004d2f5  call    ?MapConfig@CONFIG_PATH_MAPPER@@QEAAJPEAVPATH@@KPEAU_PATH_CACHE_NODE@@PEAVSTRU@@2PEAPEAXPEAKPEAPEAVCONFIG_VDIR@@PEAVPARSE_ERROR_INFO@@@Z; CONFIG_PATH_MAPPER::MapConfig(PATH *,ulong,_PATH_CACHE_NODE *,STRU *,STRU *,void * *,ulong *,CONFIG_VDIR * *,PARSE_ERROR_INFO *)
0x18004d2fa  test    eax, eax
0x18004d2fc  js      loc_18004D5B2
0x18004d302  test    [rsp+6B0h+var_648], 1000h
0x18004d30a  jz      short loc_18004D32E
0x18004d30c  mov     edi, 8007000Dh
0x18004d311  lea     rcx, [rbp+5B0h+var_5A0]
0x18004d315  mov     ebx, edi
0x18004d317  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18004d31d  mov     [rbp+5B0h+var_630], rax
0x18004d321  mov     r9d, 0C0000AB4h
0x18004d327  mov     edx, edi
0x18004d329  jmp     loc_18004D58B
0x18004d32e  mov     ebx, r15d
0x18004d331  jmp     loc_18004D5B2
0x18004d336  test    rax, rax
0x18004d339  jnz     short loc_18004D34A
0x18004d33b  mov     edi, 8007000Dh
0x18004d340  mov     r9d, 0C0000AE3h
0x18004d346  mov     ebx, edi
0x18004d348  jmp     short loc_18004D327
0x18004d34a  cmp     [rsi+32Ch], r15d
0x18004d351  jz      short loc_18004D394
0x18004d353  mov     r15, rdi
0x18004d356  test    r15, r15
0x18004d359  jnz     short loc_18004D360
0x18004d35b  test    r12d, r12d
0x18004d35e  jz      short loc_18004D391
0x18004d360  lea     rax, [rbp+5B0h+var_5E0]
0x18004d364  mov     r8, rdi; struct _PATH_CACHE_NODE *
0x18004d367  lea     r9, [rsp+6B0h+var_650]; int *
0x18004d36c  mov     [rsp+6B0h+var_690], rax; struct PARSE_ERROR_INFO *
0x18004d371  mov     rdx, r13; struct PATH *
0x18004d374  mov     rcx, rsi; this
0x18004d377  call    ?GetNodeChanged@CONFIG_CACHE@@AEAAJPEAVPATH@@PEAU_PATH_CACHE_NODE@@PEAHPEAVPARSE_ERROR_INFO@@@Z; CONFIG_CACHE::GetNodeChanged(PATH *,_PATH_CACHE_NODE *,int *,PARSE_ERROR_INFO *)
0x18004d37c  mov     ebx, eax
0x18004d37e  test    eax, eax
0x18004d380  js      loc_18004D5B2
0x18004d386  mov     r15, [r15+8]
0x18004d38a  mov     r12d, [rsp+6B0h+var_650]
0x18004d38f  jmp     short loc_18004D356
0x18004d391  xor     r15d, r15d
0x18004d394  mov     rdx, [rsi+318h]
0x18004d39b  mov     ebx, r15d
0x18004d39e  mov     ecx, [rdx+44h]
0x18004d3a1  mov     r13d, [rdx+40h]
0x18004d3a5  mov     [rsp+6B0h+var_650], ecx
0x18004d3a9  test    rdi, rdi
0x18004d3ac  jz      short loc_18004D3BE
0x18004d3ae  mov     rax, [rdi+20h]
0x18004d3b2  test    rax, rax
0x18004d3b5  jz      short loc_18004D3BE
0x18004d3b7  mov     r15d, [rax+40h]
0x18004d3bb  mov     ebx, [rax+44h]
0x18004d3be  test    r12d, r12d
0x18004d3c1  jnz     loc_18004D4AC
0x18004d3c7  test    rdi, rdi
0x18004d3ca  jz      loc_18004D4AC
0x18004d3d0  mov     rcx, [rdi+20h]
0x18004d3d4  test    rcx, rcx
0x18004d3d7  jz      loc_18004D4A8
0x18004d3dd  add     rdx, 38h ; '8'; lpFileTime2
0x18004d3e1  add     rcx, 38h ; '8'; lpFileTime1
0x18004d3e5  call    cs:__imp_CompareFileTime
0x18004d3eb  test    eax, eax
0x18004d3ed  jnz     loc_18004D4A8
0x18004d3f3  mov     rcx, [rdi+20h]; this
0x18004d3f7  call    ?HandleMergedCommitElements@CONFIG_FILE@@QEAAJXZ; CONFIG_FILE::HandleMergedCommitElements(void)
0x18004d3fc  xor     r15d, r15d
0x18004d3ff  mov     ebx, eax
0x18004d401  test    eax, eax
0x18004d403  js      loc_18004D5B2
0x18004d409  mov     rcx, [rdi+20h]
0x18004d40d  add     rcx, 10h
0x18004d411  mov     rax, [rcx]
0x18004d414  mov     rax, [rax+50h]
0x18004d418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d41d  mov     ebx, eax
0x18004d41f  test    eax, eax
0x18004d421  js      loc_18004D5B2
0x18004d427  cmp     cs:Microsoft_Windows_IIS_ConfigurationEnableBits, r15b
0x18004d42e  jge     short loc_18004D449
0x18004d430  lea     rcx, [rbp+5B0h+var_5A0]
0x18004d434  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18004d43a  mov     r8, rax
0x18004d43d  lea     rdx, NATIVERD_EVENT_CHANGES_SUCCESSFULLY_COMMITTED
0x18004d444  call    McTemplateU0z_EtwEventWriteTransfer
0x18004d449  mov     r8d, r14d; int
0x18004d44c  mov     rdx, rdi; struct _PATH_CACHE_NODE *
0x18004d44f  mov     rcx, rsi; this
0x18004d452  call    ?DeleteNode@CONFIG_CACHE@@AEAAJPEAU_PATH_CACHE_NODE@@H@Z; CONFIG_CACHE::DeleteNode(_PATH_CACHE_NODE *,int)
0x18004d457  mov     ebx, eax
0x18004d459  test    eax, eax
0x18004d45b  js      loc_18004D5B2
0x18004d461  mov     rcx, [rsi+318h]
0x18004d468  mov     rax, [rcx]
0x18004d46b  mov     rax, [rax+10h]
0x18004d46f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d474  mov     rcx, rsi; this
0x18004d477  mov     [rsi+318h], r15
0x18004d47e  call    ?WriteUnlock@CONFIG_CACHE@@AEAAXXZ; CONFIG_CACHE::WriteUnlock(void)
0x18004d483  mov     rbx, [rsi]
0x18004d486  lea     rcx, [rbp+5B0h+var_5A0]
0x18004d48a  mov     r14d, r15d
0x18004d48d  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18004d493  xor     r8d, r8d; struct GRANULAR_CHANGE_LIST *
0x18004d496  mov     rcx, rbx; this
0x18004d499  mov     rdx, rax; unsigned __int16 *
0x18004d49c  call    ?InformListenersChangeNotification@CONFIG_CHANGE_NOTIFIER@@QEAAJPEBGPEAVGRANULAR_CHANGE_LIST@@@Z; CONFIG_CHANGE_NOTIFIER::InformListenersChangeNotification(ushort const *,GRANULAR_CHANGE_LIST *)
0x18004d4a1  mov     ebx, eax
0x18004d4a3  jmp     loc_18004D5B2
0x18004d4a8  mov     ecx, [rsp+6B0h+var_650]
0x18004d4ac  test    cs:Microsoft_Windows_IIS_ConfigurationEnableBits, 4
0x18004d4b3  jz      loc_18004D55E
0x18004d4b9  mov     dword ptr [rsp+6B0h+var_638], ebx
0x18004d4bd  mov     dword ptr [rsp+6B0h+var_638+4], r15d
0x18004d4c2  test    rdi, rdi
0x18004d4c5  jz      short loc_18004D4D6
0x18004d4c7  mov     rax, [rdi+20h]
0x18004d4cb  test    rax, rax
0x18004d4ce  jz      short loc_18004D4D6
0x18004d4d0  lea     r12, [rax+38h]
0x18004d4d4  jmp     short loc_18004D4D9
0x18004d4d6  xor     r12d, r12d
0x18004d4d9  test    rdi, rdi
0x18004d4dc  jz      short loc_18004D4EA
0x18004d4de  cmp     qword ptr [rdi+20h], 0
0x18004d4e3  jz      short loc_18004D4EA
0x18004d4e5  mov     r15d, r14d
0x18004d4e8  jmp     short loc_18004D4ED
0x18004d4ea  xor     r15d, r15d
0x18004d4ed  mov     rbx, [rsi+318h]
0x18004d4f4  lea     rdi, szDomain
0x18004d4fb  mov     dword ptr [rsp+6B0h+var_640], ecx
0x18004d4ff  lea     rcx, [rbp+5B0h+var_5A0]
0x18004d503  mov     dword ptr [rsp+6B0h+var_640+4], r13d
0x18004d508  cmp     qword ptr [rbx+28h], 0
0x18004d50d  cmovnz  rdi, [rbx+28h]
0x18004d512  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18004d518  mov     rcx, [rsp+6B0h+var_638]
0x18004d51d  lea     rdx, [rbx+38h]
0x18004d521  mov     [rsp+6B0h+var_660], 0
0x18004d529  mov     r9, rdi
0x18004d52c  mov     [rsp+6B0h+var_668], rcx
0x18004d531  mov     r8, rax
0x18004d534  mov     rcx, [rsp+6B0h+var_640]
0x18004d539  mov     [rsp+6B0h+var_670], r12
0x18004d53e  mov     dword ptr [rsp+6B0h+var_678], r15d
0x18004d543  mov     [rsp+6B0h+var_680], rcx
0x18004d548  mov     [rsp+6B0h+var_688], rdx
0x18004d54d  lea     rdx, NATIVERD_EVENT_CANNOT_COMMIT_CHANGES_DUE_TO_STALE_CONFIG_VIEW
0x18004d554  mov     dword ptr [rsp+6B0h+var_690], r14d
0x18004d559  call    McTemplateU0zztmxtmxt_EtwEventWriteTransfer
0x18004d55e  mov     rcx, [rsi+318h]; this
0x18004d565  xor     r15d, r15d
0x18004d568  test    rcx, rcx
0x18004d56b  jz      short loc_18004D57E
0x18004d56d  call    ?QueryParseErrorFileName@CONFIG_FILE@@QEBAPEBGXZ; CONFIG_FILE::QueryParseErrorFileName(void)
0x18004d572  mov     rdx, rax; unsigned __int16 *
0x18004d575  lea     rcx, [rbp+5B0h+var_600]; this
0x18004d579  call    ?Copy@SMALL_STRU@@QEAAJPEBG@Z; SMALL_STRU::Copy(ushort const *)
0x18004d57e  mov     ebx, 80070020h
0x18004d583  mov     r9d, 0C0000AF3h
0x18004d589  mov     edx, ebx
0x18004d58b  mov     [rsp+6B0h+var_678], r15
0x18004d590  lea     rax, [rbp+5B0h+var_630]
0x18004d594  mov     [rsp+6B0h+var_680], r15
0x18004d599  lea     rcx, [rbp+5B0h+var_620]
  ... truncated ...
```
