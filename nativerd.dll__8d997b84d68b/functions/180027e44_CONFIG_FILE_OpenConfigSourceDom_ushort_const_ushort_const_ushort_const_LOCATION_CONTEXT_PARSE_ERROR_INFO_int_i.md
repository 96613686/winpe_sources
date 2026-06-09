# CONFIG_FILE::OpenConfigSourceDom(ushort const *,ushort const *,ushort const *,LOCATION_CONTEXT *,PARSE_ERROR_INFO *,int,int,IConfigDomNode * *,CONFIG_SOURCE_ENTRY * *)

- ea: `0x180027e44`
- end: `0x1800284d2`
- name: `?OpenConfigSourceDom@CONFIG_FILE@@QEAAJPEBG00PEAVLOCATION_CONTEXT@@PEAVPARSE_ERROR_INFO@@HHPEAPEAVIConfigDomNode@@PEAPEAVCONFIG_SOURCE_ENTRY@@@Z`
- size: `1678`
- prototype: `__int64 __fastcall(CONFIG_FILE *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct LOCATION_CONTEXT *, struct PARSE_ERROR_INFO *, int, int, struct IConfigDomNode **, struct CONFIG_SOURCE_ENTRY **)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180013138`
- `0x18002eb10`

## callees

- `0x180010468`
- `0x180011130`
- `0x180016aa0`
- `0x18001be64`
- `0x18001c250`
- `0x18001fe34`
- `0x180027e44`
- `0x18002a914`
- `0x1800412fc`
- `0x180059bea`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180027fee`
- `msvcrt!wcsrchr` at `0x180027fee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028155`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028155`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x1800282a6`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x1800282a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028475`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028475`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002847f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180028489`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180028493`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002849d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800284a7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002847f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180028489`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180028493`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002849d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800284a7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180028073`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800280e7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180028108`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180028209`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180028263`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800282ea`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800282f7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180028073`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800280e7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180028108`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180028209`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180028263`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800282ea`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800282f7`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180027ed7`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180027f0d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180027f38`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180027f68`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180027f93`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180027ed7`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180027f0d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180027f38`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180027f68`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180027f93`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002805f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800280a9`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800280f4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002805f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800280a9`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800280f4`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18002801e`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18002801e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180028039`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180028050`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800280c4`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800280db`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180028039`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180028050`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800280c4`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800280db`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800283b8`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800283b8`
- `iisutil!MakePathCanonicalizationProof` at `0x180028080`
- `iisutil!MakePathCanonicalizationProof` at `0x180028080`

## string_xrefs

- `0x180028117`: `CONFIG_FILE::OpenConfigSourceDom`

## pseudocode

```c
__int64 __fastcall CONFIG_FILE::OpenConfigSourceDom(
        CONFIG_FILE *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct LOCATION_CONTEXT *a5,
        struct PARSE_ERROR_INFO *a6,
        int a7,
        int a8,
        struct IConfigDomNode **a9,
        struct CONFIG_SOURCE_ENTRY **a10)
{
  CONFIG_XML_DOM *v13; // rdi
  __int64 v14; // r12
  const WCHAR *v15; // r14
  int v16; // eax
  const wchar_t *v17; // rcx
  wchar_t *v18; // r8
  __int64 v19; // rcx
  const WCHAR *v20; // rax
  const unsigned __int16 *v21; // rdx
  __int64 v22; // r8
  signed int PathCanonicalizationProof; // ebx
  const unsigned __int16 *Str; // rax
  const unsigned __int16 *ParseErrorFileName; // rax
  int v26; // eax
  const unsigned __int16 *v27; // rax
  const unsigned __int16 *v28; // rax
  signed int LastError; // eax
  CONFIG_XML_DOM *v30; // rax
  CONFIG_XML_DOM *v31; // rax
  int v32; // eax
  const unsigned __int16 *v33; // rsi
  const unsigned __int16 *v34; // rax
  unsigned __int16 *v35; // rax
  signed __int64 v36; // r8
  int v37; // edx
  int v38; // ecx
  _QWORD *v39; // rsi
  const unsigned __int16 *v40; // r13
  const unsigned __int16 *v41; // rbx
  const WCHAR *v42; // rdi
  const unsigned __int16 *v43; // rax
  int v44; // edx
  struct IConfigDomNode *v45; // rax
  struct IConfigDomNode *v47; // [rsp+50h] [rbp-B0h] BYREF
  struct _FILETIME LastWriteTime; // [rsp+58h] [rbp-A8h] BYREF
  const unsigned __int16 *v49; // [rsp+60h] [rbp-A0h]
  struct CONFIG_SOURCE_ENTRY **v50; // [rsp+68h] [rbp-98h]
  struct LOCATION_CONTEXT *v51; // [rsp+70h] [rbp-90h]
  const unsigned __int16 *v52; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v53; // [rsp+80h] [rbp-80h]
  struct IConfigDomNode **v54; // [rsp+88h] [rbp-78h]
  _BYTE v55[56]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v56[56]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v57[56]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v58[56]; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v59[64]; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int16 v60[256]; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int16 v61[256]; // [rsp+3B0h] [rbp+2B0h] BYREF
  unsigned __int16 v62[256]; // [rsp+5B0h] [rbp+4B0h] BYREF
  unsigned __int16 v63[256]; // [rsp+7B0h] [rbp+6B0h] BYREF
  unsigned __int16 v64[264]; // [rsp+9B0h] [rbp+8B0h] BYREF

  v51 = a5;
  v52 = a3;
  v53 = a2;
  v50 = a10;
  v49 = a4;
  v54 = a9;
  memset_0(v60, 0, sizeof(v60));
  STRU::STRU((STRU *)v56, v60, 0x100u);
  v13 = 0;
  v47 = 0;
  v14 = -1;
  memset_0(v61, 0, sizeof(v61));
  STRU::STRU((STRU *)v59, v61, 0x100u);
  memset_0(v62, 0, sizeof(v62));
  STRU::STRU((STRU *)v57, v62, 0x100u);
  LastWriteTime = 0;
  memset_0(v63, 0, sizeof(v63));
  STRU::STRU((STRU *)v58, v63, 0x100u);
  memset_0(v64, 0, 0x208u);
  STRU::STRU((STRU *)v55, v64, 0x104u);
  if ( !a3 || !a6 || !a4 || !a9 )
  {
    PathCanonicalizationProof = -2147024809;
    goto LABEL_70;
  }
  v15 = &szDomain;
  if ( a8 )
  {
    v16 = ExpandEnvironmentVariables(a3, (struct STRU *)v56);
  }
  else
  {
    v17 = &szDomain;
    if ( *((_QWORD *)this + 5) )
      v17 = (const wchar_t *)*((_QWORD *)this + 5);
    v18 = wcsrchr(v17, 0x5Cu);
    if ( v18 )
    {
      v19 = *((_QWORD *)this + 5);
      v20 = &szDomain;
      v21 = &szDomain;
      if ( v19 )
        v20 = (const WCHAR *)*((_QWORD *)this + 5);
      v22 = v18 - v20;
      if ( v19 )
        v21 = (const unsigned __int16 *)*((_QWORD *)this + 5);
      PathCanonicalizationProof = STRU::Copy((STRU *)v56, v21, v22);
      if ( PathCanonicalizationProof < 0 )
        goto LABEL_70;
      PathCanonicalizationProof = STRU::Append((STRU *)v56, L"\\");
      if ( PathCanonicalizationProof < 0 )
        goto LABEL_70;
      v16 = STRU::Append((STRU *)v56, a3);
    }
    else
    {
      v16 = STRU::Copy((STRU *)v56, a3);
    }
  }
  PathCanonicalizationProof = v16;
  if ( v16 < 0 )
    goto LABEL_70;
  Str = STRU::QueryStr((STRU *)v56);
  PathCanonicalizationProof = MakePathCanonicalizationProof(Str, (struct STRU *)v57);
  if ( PathCanonicalizationProof < 0 )
    goto LABEL_70;
  if ( *((char *)this + 276) >= 0 )
  {
    v27 = STRU::QueryStr((STRU *)v57);
    v26 = STRU::Copy((STRU *)v55, v27);
  }
  else
  {
    ParseErrorFileName = CONFIG_FILE::QueryParseErrorFileName(this);
    PathCanonicalizationProof = STRU::Copy((STRU *)v55, ParseErrorFileName);
    if ( PathCanonicalizationProof < 0 )
      goto LABEL_70;
    PathCanonicalizationProof = STRU::Append((STRU *)v55, L" | ");
    if ( PathCanonicalizationProof < 0 )
      goto LABEL_70;
    v26 = STRU::Append((STRU *)v55, a3);
  }
  PathCanonicalizationProof = v26;
  if ( v26 < 0 )
  {
LABEL_70:
    if ( v47 )
    {
      (*(void (__fastcall **)(struct IConfigDomNode *))(*(_QWORD *)v47 + 120LL))(v47);
      v47 = 0;
    }
    if ( v13 )
      (*(void (__fastcall **)(CONFIG_XML_DOM *))(*(_QWORD *)v13 + 56LL))(v13);
    goto LABEL_74;
  }
  v28 = STRU::QueryStr((STRU *)v57);
  v14 = (__int64)FILE_HELPER::CreateFileAndWriteEvent(
                   L"CONFIG_FILE::OpenConfigSourceDom",
                   v28,
                   0,
                   1,
                   3u,
                   0x80u,
                   (char *)0xFFFFFFFFFFFFFFFFLL);
  if ( v14 == -1 && !a7 )
  {
LABEL_28:
    LastError = GetLastError();
    PathCanonicalizationProof = LastError;
    if ( LastError > 0 )
      PathCanonicalizationProof = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_70;
  }
  v30 = (CONFIG_XML_DOM *)operator new(0x90u);
  if ( !v30 )
    goto LABEL_68;
  v31 = CONFIG_XML_DOM::CONFIG_XML_DOM(v30);
  v13 = v31;
  if ( !v31 )
    goto LABEL_68;
  if ( v14 == -1 || a7 )
  {
    v33 = v49;
    v32 = (**(__int64 (__fastcall ***)(CONFIG_XML_DOM *, const unsigned __int16 *))v31)(v31, v49);
  }
  else
  {
    v32 = (*(__int64 (__fastcall **)(CONFIG_XML_DOM *, __int64, struct PARSE_ERROR_INFO *, bool, bool))(*(_QWORD *)v31 + 8LL))(
            v31,
            v14,
            a6,
            *((_QWORD *)this + 38) != 0,
            (unsigned int)(((int)(*((_DWORD *)this + 68) << 22) >> 28) - 1) > 2);
    v33 = v49;
  }
  PathCanonicalizationProof = v32;
  if ( v32 < 0 )
  {
    v34 = STRU::QueryStr((STRU *)v55);
    SMALL_STRU::Copy((struct PARSE_ERROR_INFO *)((char *)a6 + 32), v34);
    goto LABEL_70;
  }
  PathCanonicalizationProof = (*(__int64 (__fastcall **)(CONFIG_XML_DOM *, struct IConfigDomNode **))(*(_QWORD *)v13 + 16LL))(
                                v13,
                                &v47);
  if ( PathCanonicalizationProof < 0 )
    goto LABEL_70;
  PathCanonicalizationProof = (**(__int64 (__fastcall ***)(struct IConfigDomNode *, _BYTE *, _QWORD))v47)(v47, v58, 0);
  if ( PathCanonicalizationProof < 0 )
    goto LABEL_70;
  v35 = STRU::QueryStr((STRU *)v58);
  v36 = (char *)v33 - (char *)v35;
  do
  {
    v37 = *(unsigned __int16 *)((char *)v35 + v36);
    v38 = *v35 - v37;
    if ( v38 )
      break;
    ++v35;
  }
  while ( v37 );
  if ( v38 )
  {
    PathCanonicalizationProof = -2147024883;
    goto LABEL_70;
  }
  if ( v14 == -1 )
  {
    LastWriteTime = 0;
  }
  else if ( !GetFileTime((HANDLE)v14, 0, 0, &LastWriteTime) )
  {
    goto LABEL_28;
  }
  v39 = operator new(0x28u);
  if ( !v39 )
  {
LABEL_68:
    PathCanonicalizationProof = -2147024888;
    goto LABEL_70;
  }
  *v39 = &CONFIG_SOURCE_ENTRY::`vftable';
  v39[2] = 0;
  v39[3] = 0;
  v39[4] = 0;
  v40 = STRU::QueryStr((STRU *)v55);
  v41 = STRU::QueryStr((STRU *)v57);
  if ( !v41 || !v40 )
  {
    PathCanonicalizationProof = -2147024809;
    goto LABEL_67;
  }
  v39[1] = LastWriteTime;
  v39[3] = v13;
  (*(void (__fastcall **)(CONFIG_XML_DOM *))(*(_QWORD *)v13 + 48LL))(v13);
  PathCanonicalizationProof = SMALL_STRU::Copy((SMALL_STRU *)(v39 + 2), v41);
  if ( PathCanonicalizationProof < 0 )
    goto LABEL_67;
  PathCanonicalizationProof = SMALL_STRU::Copy((SMALL_STRU *)(v39 + 4), v40);
  if ( PathCanonicalizationProof < 0 )
    goto LABEL_67;
  (*(void (__fastcall **)(CONFIG_XML_DOM *))(*(_QWORD *)v13 + 56LL))(v13);
  PathCanonicalizationProof = ARRAY_LIST::AddEntry(
                                (CONFIG_FILE *)((char *)this + 312),
                                (struct IArrayListEntry *)v39,
                                0xFFFFFFFF);
  if ( PathCanonicalizationProof < 0 )
  {
    v13 = 0;
LABEL_67:
    (*(void (__fastcall **)(_QWORD *, __int64))(*v39 + 8LL))(v39, 1);
    goto LABEL_70;
  }
  if ( v50 )
    *v50 = (struct CONFIG_SOURCE_ENTRY *)v39;
  PathCanonicalizationProof = 0;
  if ( (Microsoft_Windows_IIS_ConfigurationEnableBits & 0x10) != 0 )
  {
    v42 = &szDomain;
    if ( v51 && *((_QWORD *)v51 + 1) )
      v42 = (const WCHAR *)*((_QWORD *)v51 + 1);
    v43 = STRU::QueryStr((CONFIG_FILE *)((char *)this + 72));
    if ( *((_QWORD *)this + 5) )
      v15 = (const WCHAR *)*((_QWORD *)this + 5);
    McTemplateU0zzzzzzm_EtwEventWriteTransfer(
      (_DWORD)v52,
      v44,
      (_DWORD)v53,
      (_DWORD)v15,
      (__int64)v43,
      (__int64)v42,
      (__int64)v52,
      (__int64)v49,
      (__int64)&LastWriteTime);
  }
  v45 = v47;
  v47 = 0;
  *v54 = v45;
LABEL_74:
  if ( v14 != -1 )
    CloseHandle((HANDLE)v14);
  STRU::~STRU((STRU *)v55);
  STRU::~STRU((STRU *)v58);
  STRU::~STRU((STRU *)v57);
  STRU::~STRU((STRU *)v59);
  STRU::~STRU((STRU *)v56);
  return (unsigned int)PathCanonicalizationProof;
}

```

## disassembly

```asm
0x180027e44  push    rbp
0x180027e46  push    rbx
0x180027e47  push    rsi
0x180027e48  push    rdi
0x180027e49  push    r12
0x180027e4b  push    r13
0x180027e4d  push    r14
0x180027e4f  push    r15
0x180027e51  lea     rbp, [rsp-0AD8h]
0x180027e59  sub     rsp, 0BD8h
0x180027e60  mov     rax, cs:__security_cookie
0x180027e67  xor     rax, rsp
0x180027e6a  mov     [rbp+0B10h+var_50], rax
0x180027e71  mov     rax, [rbp+0B10h+arg_20]
0x180027e78  mov     rbx, r9
0x180027e7b  mov     r14, [rbp+0B10h+arg_40]
0x180027e82  mov     rsi, r8
0x180027e85  mov     r13, [rbp+0B10h+arg_28]
0x180027e8c  mov     r15, rcx
0x180027e8f  mov     [rsp+0C10h+var_BA0], rax
0x180027e94  lea     rcx, [rbp+0B10h+var_A60]; void *
0x180027e9b  mov     rax, [rbp+0B10h+arg_48]
0x180027ea2  mov     [rsp+0C10h+var_B98], r8
0x180027ea7  mov     r8d, 200h; Size
0x180027ead  mov     [rbp+0B10h+var_B90], rdx
0x180027eb1  xor     edx, edx; Val
0x180027eb3  mov     [rsp+0C10h+var_BA8], rax
0x180027eb8  mov     [rsp+0C10h+var_BB0], rbx
0x180027ebd  mov     [rbp+0B10h+var_B88], r14
0x180027ec1  call    memset_0
0x180027ec6  mov     r8d, 100h
0x180027ecc  lea     rdx, [rbp+0B10h+var_A60]
0x180027ed3  lea     rcx, [rbp+0B10h+var_B48]
0x180027ed7  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180027edd  xor     edi, edi
0x180027edf  lea     rcx, [rbp+0B10h+var_860]; void *
0x180027ee6  xor     edx, edx; Val
0x180027ee8  mov     [rsp+0C10h+var_BC0], rdi
0x180027eed  mov     r8d, 200h; Size
0x180027ef3  or      r12, 0FFFFFFFFFFFFFFFFh
0x180027ef7  call    memset_0
0x180027efc  mov     r8d, 100h
0x180027f02  lea     rdx, [rbp+0B10h+var_860]
0x180027f09  lea     rcx, [rbp+0B10h+var_AA0]
0x180027f0d  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180027f13  xor     edx, edx; Val
0x180027f15  lea     rcx, [rbp+0B10h+var_660]; void *
0x180027f1c  mov     r8d, 200h; Size
0x180027f22  call    memset_0
0x180027f27  mov     r8d, 100h
0x180027f2d  lea     rdx, [rbp+0B10h+var_660]
0x180027f34  lea     rcx, [rbp+0B10h+var_B10]
0x180027f38  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180027f3e  xor     edx, edx; Val
0x180027f40  mov     qword ptr [rsp+0C10h+LastWriteTime.dwLowDateTime], rdi
0x180027f45  mov     r8d, 200h; Size
0x180027f4b  lea     rcx, [rbp+0B10h+var_460]; void *
0x180027f52  call    memset_0
0x180027f57  mov     r8d, 100h
0x180027f5d  lea     rdx, [rbp+0B10h+var_460]
0x180027f64  lea     rcx, [rbp+0B10h+var_AD8]
0x180027f68  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180027f6e  xor     edx, edx; Val
0x180027f70  lea     rcx, [rbp+0B10h+var_260]; void *
0x180027f77  mov     r8d, 208h; Size
0x180027f7d  call    memset_0
0x180027f82  mov     r8d, 104h
0x180027f88  lea     rdx, [rbp+0B10h+var_260]
0x180027f8f  lea     rcx, [rbp+0B10h+var_B80]
0x180027f93  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180027f99  test    rsi, rsi
0x180027f9c  jz      loc_180028434
0x180027fa2  test    r13, r13
0x180027fa5  jz      loc_180028434
0x180027fab  test    rbx, rbx
0x180027fae  jz      loc_180028434
0x180027fb4  test    r14, r14
0x180027fb7  jz      loc_180028434
0x180027fbd  lea     r14, szDomain
0x180027fc4  cmp     [rbp+0B10h+arg_38], edi
0x180027fca  jz      short loc_180027FDD
0x180027fcc  lea     rdx, [rbp+0B10h+var_B48]; struct STRU *
0x180027fd0  mov     rcx, rsi; lpSrc
0x180027fd3  call    ?ExpandEnvironmentVariables@@YAJPEBGPEAVSTRU@@@Z; ExpandEnvironmentVariables(ushort const *,STRU *)
0x180027fd8  jmp     loc_180028065
0x180027fdd  cmp     [r15+28h], rdi
0x180027fe1  mov     rcx, r14
0x180027fe4  mov     edx, 5Ch ; '\'; Ch
0x180027fe9  cmovnz  rcx, [r15+28h]; Str
0x180027fee  call    cs:__imp_wcsrchr
0x180027ff4  mov     r8, rax
0x180027ff7  test    rax, rax
0x180027ffa  jz      short loc_180028058
0x180027ffc  mov     rcx, [r15+28h]
0x180028000  mov     rax, r14
0x180028003  test    rcx, rcx
0x180028006  mov     rdx, r14
0x180028009  cmovnz  rax, rcx
0x18002800d  sub     r8, rax
0x180028010  sar     r8, 1
0x180028013  test    rcx, rcx
0x180028016  cmovnz  rdx, rcx
0x18002801a  lea     rcx, [rbp+0B10h+var_B48]
0x18002801e  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180028024  mov     ebx, eax
0x180028026  test    eax, eax
0x180028028  js      loc_180028439
0x18002802e  lea     rdx, asc_18005F940; "\\"
0x180028035  lea     rcx, [rbp+0B10h+var_B48]
0x180028039  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18002803f  mov     ebx, eax
0x180028041  test    eax, eax
0x180028043  js      loc_180028439
0x180028049  mov     rdx, rsi
0x18002804c  lea     rcx, [rbp+0B10h+var_B48]
0x180028050  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180028056  jmp     short loc_180028065
0x180028058  mov     rdx, rsi
0x18002805b  lea     rcx, [rbp+0B10h+var_B48]
0x18002805f  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180028065  mov     ebx, eax
0x180028067  test    eax, eax
0x180028069  js      loc_180028439
0x18002806f  lea     rcx, [rbp+0B10h+var_B48]
0x180028073  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180028079  mov     rcx, rax
0x18002807c  lea     rdx, [rbp+0B10h+var_B10]
0x180028080  call    cs:__imp_?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,STRU *)
0x180028086  mov     ebx, eax
0x180028088  test    eax, eax
0x18002808a  js      loc_180028439
0x180028090  test    byte ptr [r15+114h], 80h
0x180028098  jz      short loc_1800280E3
0x18002809a  mov     rcx, r15; this
0x18002809d  call    ?QueryParseErrorFileName@CONFIG_FILE@@QEBAPEBGXZ; CONFIG_FILE::QueryParseErrorFileName(void)
0x1800280a2  mov     rdx, rax
0x1800280a5  lea     rcx, [rbp+0B10h+var_B80]
0x1800280a9  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800280af  mov     ebx, eax
0x1800280b1  test    eax, eax
0x1800280b3  js      loc_180028439
0x1800280b9  lea     rdx, asc_180060988; " | "
0x1800280c0  lea     rcx, [rbp+0B10h+var_B80]
0x1800280c4  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800280ca  mov     ebx, eax
0x1800280cc  test    eax, eax
0x1800280ce  js      loc_180028439
0x1800280d4  mov     rdx, rsi
0x1800280d7  lea     rcx, [rbp+0B10h+var_B80]
0x1800280db  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800280e1  jmp     short loc_1800280FA
0x1800280e3  lea     rcx, [rbp+0B10h+var_B10]
0x1800280e7  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800280ed  mov     rdx, rax
0x1800280f0  lea     rcx, [rbp+0B10h+var_B80]
0x1800280f4  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800280fa  mov     ebx, eax
0x1800280fc  test    eax, eax
0x1800280fe  js      loc_180028439
0x180028104  lea     rcx, [rbp+0B10h+var_B10]
0x180028108  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002810e  mov     [rsp+0C10h+var_BE0], 0FFFFFFFFFFFFFFFFh; void *
0x180028117  lea     rcx, aConfigFileOpen; "CONFIG_FILE::OpenConfigSourceDom"
0x18002811e  mov     rdx, rax; unsigned __int16 *
0x180028121  mov     [rsp+0C10h+var_BE8], 80h; unsigned int
0x180028129  mov     r9d, 1; unsigned int
0x18002812f  mov     [rsp+0C10h+var_BF0], 3; unsigned int
0x180028137  mov     r8d, 80000000h; unsigned int
0x18002813d  call    ?CreateFileAndWriteEvent@FILE_HELPER@@SAPEAXPEBG0KKKKPEAX@Z; FILE_HELPER::CreateFileAndWriteEvent(ushort const *,ushort const *,ulong,ulong,ulong,ulong,void *)
0x180028142  mov     ebx, [rbp+0B10h+arg_30]
0x180028148  mov     r12, rax
0x18002814b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002814f  jnz     short loc_180028173
0x180028151  test    ebx, ebx
0x180028153  jnz     short loc_180028173
0x180028155  call    cs:__imp_GetLastError
0x18002815b  mov     ebx, eax
0x18002815d  test    eax, eax
0x18002815f  jle     loc_180028439
0x180028165  movzx   ebx, ax
0x180028168  or      ebx, 80070000h
0x18002816e  jmp     loc_180028439
0x180028173  mov     ecx, 90h; Size
0x180028178  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002817d  test    rax, rax
0x180028180  jz      loc_18002842D
0x180028186  mov     rcx, rax; this
0x180028189  call    ??0CONFIG_XML_DOM@@QEAA@XZ; CONFIG_XML_DOM::CONFIG_XML_DOM(void)
0x18002818e  mov     rdi, rax
0x180028191  test    rax, rax
0x180028194  jz      loc_18002842D
0x18002819a  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x18002819e  jz      short loc_1800281E9
0x1800281a0  test    ebx, ebx
0x1800281a2  jnz     short loc_1800281E9
0x1800281a4  mov     ecx, [r15+110h]
0x1800281ab  xor     edx, edx
0x1800281ad  mov     rax, [rax]
0x1800281b0  mov     r8, r13
0x1800281b3  shl     ecx, 16h
0x1800281b6  sar     ecx, 1Ch
0x1800281b9  dec     ecx
0x1800281bb  mov     rax, [rax+8]
0x1800281bf  cmp     ecx, 2
0x1800281c2  mov     rcx, rdi
0x1800281c5  setnbe  dl
0x1800281c8  xor     r9d, r9d
0x1800281cb  cmp     [r15+130h], r9
0x1800281d2  mov     [rsp+0C10h+var_BF0], edx
0x1800281d6  mov     rdx, r12
0x1800281d9  setnz   r9b
0x1800281dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281e2  mov     rsi, [rsp+0C10h+var_BB0]
0x1800281e7  jmp     short loc_1800281FF
0x1800281e9  mov     rax, [rax]
0x1800281ec  mov     rcx, rdi
0x1800281ef  mov     rsi, [rsp+0C10h+var_BB0]
0x1800281f4  mov     rdx, rsi
0x1800281f7  mov     rax, [rax]
0x1800281fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281ff  mov     ebx, eax
0x180028201  test    eax, eax
0x180028203  jns     short loc_180028220
0x180028205  lea     rcx, [rbp+0B10h+var_B80]
0x180028209  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002820f  mov     rdx, rax; unsigned __int16 *
0x180028212  lea     rcx, [r13+20h]; this
0x180028216  call    ?Copy@SMALL_STRU@@QEAAJPEBG@Z; SMALL_STRU::Copy(ushort const *)
0x18002821b  jmp     loc_180028439
0x180028220  mov     rax, [rdi]
0x180028223  lea     rdx, [rsp+0C10h+var_BC0]
0x180028228  mov     rcx, rdi
0x18002822b  mov     rax, [rax+10h]
0x18002822f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028234  mov     ebx, eax
0x180028236  test    eax, eax
0x180028238  js      loc_180028439
0x18002823e  mov     rcx, [rsp+0C10h+var_BC0]
0x180028243  lea     rdx, [rbp+0B10h+var_AD8]
0x180028247  xor     r8d, r8d
0x18002824a  mov     rax, [rcx]
0x18002824d  mov     rax, [rax]
0x180028250  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028255  mov     ebx, eax
0x180028257  test    eax, eax
0x180028259  js      loc_180028439
0x18002825f  lea     rcx, [rbp+0B10h+var_AD8]
0x180028263  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180028269  mov     r8, rsi
0x18002826c  sub     r8, rax
0x18002826f  movzx   ecx, word ptr [rax]
0x180028272  movzx   edx, word ptr [rax+r8]
0x180028277  sub     ecx, edx
0x180028279  jnz     short loc_180028283
0x18002827b  add     rax, 2
0x18002827f  test    edx, edx
0x180028281  jnz     short loc_18002826F
0x180028283  xor     ebx, ebx
0x180028285  test    ecx, ecx
0x180028287  jz      short loc_180028293
0x180028289  mov     ebx, 8007000Dh
0x18002828e  jmp     loc_180028439
0x180028293  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x180028297  jz      short loc_1800282B5
0x180028299  lea     r9, [rsp+0C10h+LastWriteTime]; lpLastWriteTime
0x18002829e  xor     r8d, r8d; lpLastAccessTime
0x1800282a1  xor     edx, edx; lpCreationTime
0x1800282a3  mov     rcx, r12; hFile
0x1800282a6  call    cs:__imp_GetFileTime
0x1800282ac  test    eax, eax
0x1800282ae  jnz     short loc_1800282BA
0x1800282b0  jmp     loc_180028155
0x1800282b5  mov     qword ptr [rsp+0C10h+LastWriteTime.dwLowDateTime], rbx
0x1800282ba  mov     ecx, 28h ; '('; Size
0x1800282bf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800282c4  mov     rsi, rax
0x1800282c7  test    rax, rax
0x1800282ca  jz      loc_18002842D
0x1800282d0  lea     rax, ??_7CONFIG_SOURCE_ENTRY@@6B@; const CONFIG_SOURCE_ENTRY::`vftable'
0x1800282d7  mov     [rsi], rax
0x1800282da  lea     rcx, [rbp+0B10h+var_B80]
0x1800282de  mov     [rsi+10h], rbx
0x1800282e2  mov     [rsi+18h], rbx
0x1800282e6  mov     [rsi+20h], rbx
0x1800282ea  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800282f0  lea     rcx, [rbp+0B10h+var_B10]
0x1800282f4  mov     r13, rax
0x1800282f7  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800282fd  mov     rbx, rax
0x180028300  test    rax, rax
0x180028303  jz      loc_180028412
0x180028309  test    r13, r13
0x18002830c  jz      loc_180028412
0x180028312  mov     rcx, qword ptr [rsp+0C10h+LastWriteTime.dwLowDateTime]
0x180028317  mov     [rsi+8], rcx
0x18002831b  mov     [rsi+18h], rdi
0x18002831f  mov     rcx, [rdi]
0x180028322  mov     rax, [rcx+30h]
0x180028326  mov     rcx, rdi
0x180028329  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
