# FREB_SITE_META_STORED_CONTEXT::ScavengeFrebLogFiles(void)

- ea: `0x180006f98`
- end: `0x180007511`
- name: `?ScavengeFrebLogFiles@FREB_SITE_META_STORED_CONTEXT@@AEAAJXZ`
- size: `1401`
- prototype: `__int64 __fastcall(FREB_SITE_META_STORED_CONTEXT *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180008d98`

## callees

- `0x180001008`
- `0x180001048`
- `0x180006944`
- `0x180006f98`
- `0x18000a4dc`
- `0x18000ac52`
- `0x18000ac90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000717f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000717f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073ee`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000716b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000716b`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800073b4`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800073b4`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800074bd`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800074bd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800074e6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800074e6`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180006ff5`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180006ff5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800070fb`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800070fb`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180007133`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180007133`
- `iisutil!PuDbgPrintError` at `0x1800070e4`
- `iisutil!PuDbgPrintError` at `0x18000744a`
- `iisutil!PuDbgPrintError` at `0x1800070e4`
- `iisutil!PuDbgPrintError` at `0x18000744a`

## string_xrefs

- `0x1800070b5`: `Failed to allocate memory to lookup list of FREB log files to be deleted\n`
- `0x1800070dd`: `servercommon\inetsrv\iis\iisrearc\iis70\freb\freb_site_meta_context.cxx`
- `0x180007443`: `servercommon\inetsrv\iis\iisrearc\iis70\freb\freb_site_meta_context.cxx`
- `0x180007128`: `fr*.xml`

## pseudocode

```c
__int64 __fastcall FREB_SITE_META_STORED_CONTEXT::ScavengeFrebLogFiles(FREB_SITE_META_STORED_CONTEXT *this)
{
  unsigned int v1; // ebx
  signed int v3; // esi
  void *v4; // r13
  int v5; // r12d
  __int64 v6; // rdi
  unsigned int v7; // ebx
  unsigned int v8; // r15d
  bool v9; // zf
  __int64 v10; // r8
  int v11; // ebx
  int v12; // eax
  int v13; // eax
  signed int LastError; // eax
  FILETIME v15; // rbx
  unsigned __int64 v16; // rdi
  unsigned int v17; // r13d
  char *v18; // rdi
  const unsigned __int16 *v19; // rax
  const unsigned __int16 **v20; // rcx
  char *v21; // rax
  _WIN32_FIND_DATAW *p_FindFileData; // rcx
  __int64 v23; // rdx
  __int128 v24; // xmm0
  __int128 v25; // xmm0
  _QWORD *v26; // rcx
  _QWORD *i; // rax
  unsigned __int16 *v28; // rdi
  unsigned __int16 *v29; // rax
  unsigned __int16 **v30; // rcx
  unsigned __int16 *v31; // rax
  signed int v32; // eax
  int v34; // [rsp+20h] [rbp-E0h]
  const char *v35; // [rsp+28h] [rbp-D8h]
  int v36; // [rsp+30h] [rbp-D0h]
  HANDLE hFindFile; // [rsp+38h] [rbp-C8h]
  char *v38; // [rsp+40h] [rbp-C0h]
  _QWORD *v39; // [rsp+48h] [rbp-B8h] BYREF
  const unsigned __int16 *v40; // [rsp+50h] [rbp-B0h]
  FILETIME ftLastWriteTime; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v42; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *v43[3]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v44[32]; // [rsp+80h] [rbp-80h] BYREF
  LPCWSTR lpFileName; // [rsp+A0h] [rbp-60h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v47[264]; // [rsp+310h] [rbp+210h] BYREF

  v1 = *((_DWORD *)this + 18);
  v3 = 0;
  v4 = 0;
  memset_0(v47, 0, 0x208u);
  STRU::STRU((STRU *)v44, v47, 0x104u);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v42 = 0;
  v40 = (const unsigned __int16 *)&v39;
  v5 = 0;
  v39 = &v39;
  v6 = -1;
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 191, 1, 0) )
  {
    v11 = 0;
    goto LABEL_67;
  }
  v7 = v1 >> 1;
  v8 = 1;
  v9 = *((_DWORD *)this + 18) == 1;
  v36 = 1;
  if ( !v9 )
    v8 = v7;
  if ( !v8 || !*((_DWORD *)this + 189) && !*((_DWORD *)this + 187) )
  {
    v11 = 1;
    goto LABEL_67;
  }
  _InterlockedAdd(&FREB_LOG_FILE_MANAGER::sm_lScavengesSinceStartup, 1u);
  _InterlockedExchange((volatile __int32 *)this + 189, 0);
  v38 = (char *)operator new(saturated_mul(v8, 0x268u));
  v4 = v38;
  if ( !v38 )
  {
    v3 = -2147024888;
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_11;
    v10 = 546;
    v35 = "Failed to allocate memory to lookup list of FREB log files to be deleted\n";
    v34 = -2147024888;
    goto LABEL_10;
  }
  v12 = STRU::Copy((STRU *)v44, *((const unsigned __int16 **)this + 6));
  v3 = v12;
  if ( v12 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_11;
    v10 = 556;
    v35 = "Failed to build the pattern string for the FindFirstFileW() \n";
    v34 = v12;
    goto LABEL_10;
  }
  v13 = STRU::Append((STRU *)v44, L"fr*.xml");
  v3 = v13;
  if ( v13 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_11;
    v10 = 563;
    v35 = "Failed to build the pattern string for the FindFirstFileW() \n";
    v34 = v13;
    goto LABEL_10;
  }
  hFindFile = FindFirstFileW(lpFileName, &FindFileData);
  v6 = (__int64)hFindFile;
  if ( hFindFile == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( ((LastError - 2) & 0xFFFFFFEE) == 0 && LastError != 19 )
      goto LABEL_11;
    v3 = LastError > 0 ? (unsigned __int16)LastError | 0x80070000 : LastError;
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_11;
    v10 = 588;
    v35 = "FindFirstFileW() failed\n";
    v34 = v3;
LABEL_10:
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\freb\\freb_site_meta_context.cxx",
      v10,
      "FREB_SITE_META_STORED_CONTEXT::ScavengeFrebLogFiles",
      v34,
      v35);
    goto LABEL_11;
  }
  ftLastWriteTime = FindFileData.ftLastWriteTime;
  v15 = FindFileData.ftLastWriteTime;
  if ( !*(_QWORD *)&FindFileData.ftLastWriteTime )
  {
LABEL_55:
    v3 = -2147024846;
    goto LABEL_11;
  }
  v16 = v42;
  v17 = v8;
  while ( 1 )
  {
    if ( *(_QWORD *)&v15 > v16 )
    {
      if ( !v17 )
      {
        v19 = v40;
        if ( *(_QWORD ***)v40 != &v39 || (v20 = (const unsigned __int16 **)*((_QWORD *)v40 + 1), *v20 != v40) )
LABEL_64:
          __fastfail(3u);
        v40 = (const unsigned __int16 *)*((_QWORD *)v40 + 1);
        *v20 = (const unsigned __int16 *)&v39;
        v18 = (char *)(v19 - 296);
        v3 = FREB_SITE_META_STORED_CONTEXT::DeleteFrebLogFile(*((const unsigned __int16 **)this + 6), v19 - 274);
        if ( v3 < 0 )
        {
          if ( (unsigned int)++v5 >= 0x1E )
            goto LABEL_63;
          v3 = 0;
        }
        goto LABEL_40;
      }
    }
    else if ( !v17 )
    {
      v3 = FREB_SITE_META_STORED_CONTEXT::DeleteFrebLogFile(
             *((const unsigned __int16 **)this + 6),
             FindFileData.cFileName);
      if ( v3 < 0 )
      {
        if ( (unsigned int)++v5 >= 0x1E )
          goto LABEL_63;
        v3 = 0;
      }
      goto LABEL_52;
    }
    v18 = &v38[616 * --v17];
LABEL_40:
    v21 = v18;
    p_FindFileData = &FindFileData;
    v23 = 4;
    do
    {
      v24 = *(_OWORD *)&p_FindFileData->dwFileAttributes;
      p_FindFileData = (_WIN32_FIND_DATAW *)((char *)p_FindFileData + 128);
      *(_OWORD *)v21 = v24;
      v21 += 128;
      *((_OWORD *)v21 - 7) = *(_OWORD *)&p_FindFileData[-1].cFileName[218];
      *((_OWORD *)v21 - 6) = *(_OWORD *)&p_FindFileData[-1].cFileName[226];
      *((_OWORD *)v21 - 5) = *(_OWORD *)&p_FindFileData[-1].cFileName[234];
      *((_OWORD *)v21 - 4) = *(_OWORD *)&p_FindFileData[-1].cFileName[242];
      *((_OWORD *)v21 - 3) = *(_OWORD *)&p_FindFileData[-1].cFileName[250];
      *((_OWORD *)v21 - 2) = *(_OWORD *)&p_FindFileData[-1].cFileName[258];
      *((_OWORD *)v21 - 1) = *(_OWORD *)&p_FindFileData[-1].cAlternateFileName[6];
      --v23;
    }
    while ( v23 );
    *(_OWORD *)v21 = *(_OWORD *)&p_FindFileData->dwFileAttributes;
    *((_OWORD *)v21 + 1) = *(_OWORD *)&p_FindFileData->ftLastAccessTime.dwHighDateTime;
    *((_OWORD *)v21 + 2) = *(_OWORD *)&p_FindFileData->nFileSizeLow;
    *((_OWORD *)v21 + 3) = *(_OWORD *)&p_FindFileData->cFileName[2];
    v25 = *(_OWORD *)&p_FindFileData->cFileName[10];
    *((FILETIME *)v18 + 76) = v15;
    v26 = 0;
    *((_OWORD *)v21 + 4) = v25;
    for ( i = v39; i != &v39; i = (_QWORD *)*i )
    {
      v26 = i - 74;
      if ( *(unsigned __int64 *)&v15 >= i[2] )
        break;
    }
    v28 = (unsigned __int16 *)(v18 + 592);
    if ( v26 )
    {
      v29 = (unsigned __int16 *)(v26 + 74);
      v30 = (unsigned __int16 **)v26[75];
      if ( *v30 != v29 )
        goto LABEL_64;
      *(_QWORD *)v28 = v29;
      *((_QWORD *)v28 + 1) = v30;
      *v30 = v28;
      *((_QWORD *)v29 + 1) = v28;
      v28 = (unsigned __int16 *)v40;
    }
    else
    {
      v31 = (unsigned __int16 *)v40;
      if ( *(_QWORD ***)v40 != &v39 )
        goto LABEL_64;
      *((_QWORD *)v28 + 1) = v40;
      *(_QWORD *)v28 = &v39;
      *(_QWORD *)v31 = v28;
      v40 = v28;
    }
    v16 = *((_QWORD *)v28 + 2);
LABEL_52:
    if ( !FindNextFileW(hFindFile, &FindFileData) )
      break;
    ftLastWriteTime = FindFileData.ftLastWriteTime;
    v15 = FindFileData.ftLastWriteTime;
    if ( !*(_QWORD *)&FindFileData.ftLastWriteTime )
    {
      v6 = (__int64)hFindFile;
      v4 = v38;
      goto LABEL_55;
    }
  }
  v32 = GetLastError();
  if ( v32 == 18 )
  {
    *((_DWORD *)this + 190) = v8 - v17;
  }
  else
  {
    if ( v32 > 0 )
      v3 = (unsigned __int16)v32 | 0x80070000;
    else
      v3 = v32;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\freb\\freb_site_meta_context.cxx",
        712,
        "FREB_SITE_META_STORED_CONTEXT::ScavengeFrebLogFiles",
        v3,
        "FREB FindNextFileW() failed\n");
  }
LABEL_63:
  v6 = (__int64)hFindFile;
  v4 = v38;
LABEL_11:
  v11 = v36;
LABEL_67:
  *((_DWORD *)this + 187) = v5;
  if ( v3 < 0 )
  {
    v43[2] = *((unsigned __int16 **)this + 6);
    *((_DWORD *)this + 187) = -1;
    v43[0] = 0;
    v43[1] = 0;
    FREB_LOG_NT_EVENT_TABLE::LogEvent(0x800008F1, 3u, (const unsigned __int16 **const)v43, v3);
  }
  if ( v6 != -1 )
    FindClose((HANDLE)v6);
  if ( v4 )
    operator delete(v4);
  if ( v11 )
    _InterlockedCompareExchange((volatile signed __int32 *)this + 191, 0, 1);
  STRU::~STRU((STRU *)v44);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180006f98  push    rbp
0x180006f9a  push    rbx
0x180006f9b  push    rsi
0x180006f9c  push    rdi
0x180006f9d  push    r12
0x180006f9f  push    r13
0x180006fa1  push    r14
0x180006fa3  push    r15
0x180006fa5  lea     rbp, [rsp-438h]
0x180006fad  sub     rsp, 538h
0x180006fb4  mov     rax, cs:__security_cookie
0x180006fbb  xor     rax, rsp
0x180006fbe  mov     [rbp+470h+var_50], rax
0x180006fc5  mov     ebx, [rcx+48h]
0x180006fc8  mov     r14, rcx
0x180006fcb  lea     rcx, [rbp+470h+var_260]; void *
0x180006fd2  xor     edx, edx; Val
0x180006fd4  mov     r8d, 208h; Size
0x180006fda  xor     esi, esi
0x180006fdc  xor     r13d, r13d
0x180006fdf  call    memset_0
0x180006fe4  mov     r8d, 104h
0x180006fea  lea     rdx, [rbp+470h+var_260]
0x180006ff1  lea     rcx, [rbp+470h+var_4F0]
0x180006ff5  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180006ffb  xor     edx, edx; Val
0x180006ffd  lea     rcx, [rbp+470h+FindFileData]; void *
0x180007001  mov     r8d, 250h; Size
0x180007007  call    memset_0
0x18000700c  lea     rax, [rsp+570h+var_528]
0x180007011  mov     [rsp+570h+var_510], rsi
0x180007016  mov     [rsp+570h+var_520], rax
0x18000701b  lea     ecx, [rsi+1]
0x18000701e  lea     rax, [rsp+570h+var_528]
0x180007023  or      r8, 0FFFFFFFFFFFFFFFFh
0x180007027  xor     r12d, r12d
0x18000702a  mov     [rsp+570h+var_528], rax
0x18000702f  xor     eax, eax
0x180007031  mov     rdi, r8
0x180007034  lock cmpxchg [r14+2FCh], ecx
0x18000703d  jnz     loc_180007466
0x180007043  shr     ebx, 1
0x180007045  mov     r15d, ecx
0x180007048  cmp     [r14+48h], ecx
0x18000704c  mov     [rsp+570h+var_540], ecx
0x180007050  cmovnz  r15d, ebx
0x180007054  test    r15d, r15d
0x180007057  jz      loc_18000746A
0x18000705d  cmp     [r14+2F4h], esi
0x180007064  jnz     short loc_180007073
0x180007066  cmp     [r14+2ECh], esi
0x18000706d  jz      loc_18000746A
0x180007073  lock add cs:?sm_lScavengesSinceStartup@FREB_LOG_FILE_MANAGER@@0JA, ecx; long FREB_LOG_FILE_MANAGER::sm_lScavengesSinceStartup
0x18000707a  xor     eax, eax
0x18000707c  mov     ecx, r15d
0x18000707f  xchg    eax, [r14+2F4h]
0x180007086  mov     eax, 268h
0x18000708b  mul     rcx
0x18000708e  cmovb   rax, r8
0x180007092  mov     rcx, rax; Size
0x180007095  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000709a  mov     [rsp+570h+var_530], rax
0x18000709f  mov     r13, rax
0x1800070a2  test    rax, rax
0x1800070a5  jnz     short loc_1800070F3
0x1800070a7  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800070ae  mov     esi, 80070008h
0x1800070b3  jz      short loc_1800070EA
0x1800070b5  lea     rax, aFailedToAlloca; "Failed to allocate memory to lookup lis"...
0x1800070bc  mov     r8d, 222h
0x1800070c2  mov     [rsp+570h+var_548], rax
0x1800070c7  mov     [rsp+570h+var_550], 80070008h
0x1800070cf  mov     rcx, cs:g_pDebug
0x1800070d6  lea     r9, aFrebSiteMetaSt_0; "FREB_SITE_META_STORED_CONTEXT::Scavenge"...
0x1800070dd  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800070e4  call    cs:__imp_PuDbgPrintError
0x1800070ea  mov     ebx, [rsp+570h+var_540]
0x1800070ee  jmp     loc_18000746C
0x1800070f3  mov     rdx, [r14+30h]
0x1800070f7  lea     rcx, [rbp+470h+var_4F0]
0x1800070fb  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180007101  mov     esi, eax
0x180007103  test    eax, eax
0x180007105  jns     short loc_180007128
0x180007107  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000710e  jz      short loc_1800070EA
0x180007110  lea     rcx, aFailedToBuildT; "Failed to build the pattern string for "...
0x180007117  mov     r8d, 22Ch
0x18000711d  mov     [rsp+570h+var_548], rcx
0x180007122  mov     [rsp+570h+var_550], eax
0x180007126  jmp     short loc_1800070CF
0x180007128  lea     rdx, aFrXml; "fr*.xml"
0x18000712f  lea     rcx, [rbp+470h+var_4F0]
0x180007133  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180007139  mov     esi, eax
0x18000713b  test    eax, eax
0x18000713d  jns     short loc_180007163
0x18000713f  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180007146  jz      short loc_1800070EA
0x180007148  lea     rcx, aFailedToBuildT; "Failed to build the pattern string for "...
0x18000714f  mov     r8d, 233h
0x180007155  mov     [rsp+570h+var_548], rcx
0x18000715a  mov     [rsp+570h+var_550], eax
0x18000715e  jmp     loc_1800070CF
0x180007163  mov     rcx, [rbp+470h+lpFileName]; lpFileName
0x180007167  lea     rdx, [rbp+470h+FindFileData]; lpFindFileData
0x18000716b  call    cs:__imp_FindFirstFileW
0x180007171  mov     [rsp+570h+hFindFile], rax
0x180007176  mov     rdi, rax
0x180007179  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000717d  jnz     short loc_1800071D2
0x18000717f  call    cs:__imp_GetLastError
0x180007185  lea     ecx, [rax-2]
0x180007188  test    ecx, 0FFFFFFEEh
0x18000718e  jnz     short loc_180007199
0x180007190  cmp     eax, 13h
0x180007193  jnz     loc_1800070EA
0x180007199  test    eax, eax
0x18000719b  jg      short loc_1800071A1
0x18000719d  mov     esi, eax
0x18000719f  jmp     short loc_1800071AA
0x1800071a1  movzx   esi, ax
0x1800071a4  or      esi, 80070000h
0x1800071aa  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800071b1  jz      loc_1800070EA
0x1800071b7  lea     rax, aFindfirstfilew; "FindFirstFileW() failed\n"
0x1800071be  mov     r8d, 24Ch
0x1800071c4  mov     [rsp+570h+var_548], rax
0x1800071c9  mov     [rsp+570h+var_550], esi
0x1800071cd  jmp     loc_1800070CF
0x1800071d2  mov     eax, [rbp+470h+FindFileData.ftLastWriteTime.dwLowDateTime]
0x1800071d5  mov     dword ptr [rsp+570h+var_518], eax
0x1800071d9  mov     eax, [rbp+470h+FindFileData.ftLastWriteTime.dwHighDateTime]
0x1800071dc  mov     dword ptr [rsp+570h+var_518+4], eax
0x1800071e0  mov     rbx, [rsp+570h+var_518]
0x1800071e5  test    rbx, rbx
0x1800071e8  jz      loc_1800073E4
0x1800071ee  mov     rdi, [rsp+570h+var_510]
0x1800071f3  mov     r13d, r15d
0x1800071f6  cmp     rbx, rdi
0x1800071f9  ja      short loc_18000722B
0x1800071fb  test    r13d, r13d
0x1800071fe  jnz     short loc_180007230
0x180007200  mov     rcx, [r14+30h]; unsigned __int16 *
0x180007204  lea     rdx, [rbp+470h+FindFileData.cFileName]; unsigned __int16 *
0x180007208  call    ?DeleteFrebLogFile@FREB_SITE_META_STORED_CONTEXT@@CAJPEBG0@Z; FREB_SITE_META_STORED_CONTEXT::DeleteFrebLogFile(ushort const *,ushort const *)
0x18000720d  mov     esi, eax
0x18000720f  test    eax, eax
0x180007211  jns     loc_1800073AB
0x180007217  inc     r12d
0x18000721a  cmp     r12d, 1Eh
0x18000721e  jnb     loc_180007450
0x180007224  xor     esi, esi
0x180007226  jmp     loc_1800073AB
0x18000722b  test    r13d, r13d
0x18000722e  jz      short loc_180007244
0x180007230  dec     r13d
0x180007233  mov     eax, r13d
0x180007236  imul    rdi, rax, 268h
0x18000723d  add     rdi, [rsp+570h+var_530]
0x180007242  jmp     short loc_18000729A
0x180007244  mov     rax, [rsp+570h+var_520]
0x180007249  lea     rcx, [rsp+570h+var_528]
0x18000724e  cmp     [rax], rcx
0x180007251  jnz     loc_18000745F
0x180007257  mov     rcx, [rax+8]
0x18000725b  cmp     [rcx], rax
0x18000725e  jnz     loc_18000745F
0x180007264  mov     [rsp+570h+var_520], rcx
0x180007269  lea     rdx, [rsp+570h+var_528]
0x18000726e  mov     [rcx], rdx
0x180007271  lea     rdi, [rax-250h]
0x180007278  mov     rcx, [r14+30h]; unsigned __int16 *
0x18000727c  lea     rdx, [rdi+2Ch]; unsigned __int16 *
0x180007280  call    ?DeleteFrebLogFile@FREB_SITE_META_STORED_CONTEXT@@CAJPEBG0@Z; FREB_SITE_META_STORED_CONTEXT::DeleteFrebLogFile(ushort const *,ushort const *)
0x180007285  mov     esi, eax
0x180007287  test    eax, eax
0x180007289  jns     short loc_18000729A
0x18000728b  inc     r12d
0x18000728e  cmp     r12d, 1Eh
0x180007292  jnb     loc_180007450
0x180007298  xor     esi, esi
0x18000729a  mov     rax, rdi
0x18000729d  lea     rcx, [rbp+470h+FindFileData]
0x1800072a1  mov     edx, 4
0x1800072a6  movups  xmm0, xmmword ptr [rcx]
0x1800072a9  lea     rcx, [rcx+80h]
0x1800072b0  movups  xmmword ptr [rax], xmm0
0x1800072b3  lea     rax, [rax+80h]
0x1800072ba  movups  xmm1, xmmword ptr [rcx-70h]
0x1800072be  movups  xmmword ptr [rax-70h], xmm1
0x1800072c2  movups  xmm0, xmmword ptr [rcx-60h]
0x1800072c6  movups  xmmword ptr [rax-60h], xmm0
0x1800072ca  movups  xmm1, xmmword ptr [rcx-50h]
0x1800072ce  movups  xmmword ptr [rax-50h], xmm1
0x1800072d2  movups  xmm0, xmmword ptr [rcx-40h]
0x1800072d6  movups  xmmword ptr [rax-40h], xmm0
0x1800072da  movups  xmm1, xmmword ptr [rcx-30h]
0x1800072de  movups  xmmword ptr [rax-30h], xmm1
0x1800072e2  movups  xmm0, xmmword ptr [rcx-20h]
0x1800072e6  movups  xmmword ptr [rax-20h], xmm0
0x1800072ea  movups  xmm1, xmmword ptr [rcx-10h]
0x1800072ee  movups  xmmword ptr [rax-10h], xmm1
0x1800072f2  sub     rdx, 1
0x1800072f6  jnz     short loc_1800072A6
0x1800072f8  movups  xmm0, xmmword ptr [rcx]
0x1800072fb  movups  xmmword ptr [rax], xmm0
0x1800072fe  movups  xmm1, xmmword ptr [rcx+10h]
0x180007302  movups  xmmword ptr [rax+10h], xmm1
0x180007306  movups  xmm0, xmmword ptr [rcx+20h]
0x18000730a  movups  xmmword ptr [rax+20h], xmm0
0x18000730e  movups  xmm1, xmmword ptr [rcx+30h]
0x180007312  movups  xmmword ptr [rax+30h], xmm1
0x180007316  movups  xmm0, xmmword ptr [rcx+40h]
0x18000731a  mov     [rdi+260h], rbx
0x180007321  xor     ecx, ecx
0x180007323  movups  xmmword ptr [rax+40h], xmm0
0x180007327  mov     rax, [rsp+570h+var_528]
0x18000732c  jmp     short loc_180007341
0x18000732e  lea     rcx, [rax-250h]
0x180007335  cmp     rbx, [rcx+260h]
0x18000733c  jnb     short loc_18000734B
0x18000733e  mov     rax, [rax]
0x180007341  lea     rdx, [rsp+570h+var_528]
0x180007346  cmp     rax, rdx
0x180007349  jnz     short loc_18000732E
0x18000734b  add     rdi, 250h
0x180007352  test    rcx, rcx
0x180007355  jz      short loc_180007380
0x180007357  lea     rax, [rcx+250h]
0x18000735e  mov     rcx, [rax+8]
0x180007362  cmp     [rcx], rax
0x180007365  jnz     loc_18000745F
0x18000736b  mov     [rdi], rax
0x18000736e  mov     [rdi+8], rcx
0x180007372  mov     [rcx], rdi
0x180007375  mov     [rax+8], rdi
0x180007379  mov     rdi, [rsp+570h+var_520]
0x18000737e  jmp     short loc_1800073A7
0x180007380  mov     rax, [rsp+570h+var_520]
0x180007385  lea     rcx, [rsp+570h+var_528]
0x18000738a  cmp     [rax], rcx
0x18000738d  jnz     loc_18000745F
0x180007393  mov     [rdi+8], rax
0x180007397  lea     rcx, [rsp+570h+var_528]
0x18000739c  mov     [rdi], rcx
0x18000739f  mov     [rax], rdi
0x1800073a2  mov     [rsp+570h+var_520], rdi
0x1800073a7  mov     rdi, [rdi+10h]
0x1800073ab  mov     rcx, [rsp+570h+hFindFile]; hFindFile
0x1800073b0  lea     rdx, [rbp+470h+FindFileData]; lpFindFileData
0x1800073b4  call    cs:__imp_FindNextFileW
0x1800073ba  test    eax, eax
0x1800073bc  jz      short loc_1800073EE
0x1800073be  mov     eax, [rbp+470h+FindFileData.ftLastWriteTime.dwLowDateTime]
0x1800073c1  mov     dword ptr [rsp+570h+var_518], eax
0x1800073c5  mov     eax, [rbp+470h+FindFileData.ftLastWriteTime.dwHighDateTime]
0x1800073c8  mov     dword ptr [rsp+570h+var_518+4], eax
0x1800073cc  mov     rbx, [rsp+570h+var_518]
0x1800073d1  test    rbx, rbx
0x1800073d4  jnz     loc_1800071F6
0x1800073da  mov     rdi, [rsp+570h+hFindFile]
0x1800073df  mov     r13, [rsp+570h+var_530]
0x1800073e4  mov     esi, 80070032h
0x1800073e9  jmp     loc_1800070EA
0x1800073ee  call    cs:__imp_GetLastError
0x1800073f4  cmp     eax, 12h
0x1800073f7  jnz     short loc_180007405
0x1800073f9  sub     r15d, r13d
0x1800073fc  mov     [r14+2F8h], r15d
0x180007403  jmp     short loc_180007450
0x180007405  test    eax, eax
0x180007407  jg      short loc_18000740D
0x180007409  mov     esi, eax
0x18000740b  jmp     short loc_180007416
0x18000740d  movzx   esi, ax
0x180007410  or      esi, 80070000h
0x180007416  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000741d  jz      short loc_180007450
0x18000741f  mov     rcx, cs:g_pDebug
0x180007426  lea     rax, aFrebFindnextfi; "FREB FindNextFileW() failed\n"
0x18000742d  mov     [rsp+570h+var_548], rax
0x180007432  lea     r9, aFrebSiteMetaSt_0; "FREB_SITE_META_STORED_CONTEXT::Scavenge"...
0x180007439  mov     r8d, 2C8h
0x18000743f  mov     [rsp+570h+var_550], esi
0x180007443  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000744a  call    cs:__imp_PuDbgPrintError
0x180007450  mov     rdi, [rsp+570h+hFindFile]
0x180007455  mov     r13, [rsp+570h+var_530]
0x18000745a  jmp     loc_1800070EA
0x18000745f  mov     ecx, 3
0x180007464  int     29h; Win8: RtlFailFast(ecx)
0x180007466  xor     ebx, ebx
0x180007468  jmp     short loc_18000746C
0x18000746a  mov     ebx, ecx
0x18000746c  mov     [r14+2ECh], r12d
0x180007473  test    esi, esi
0x180007475  jns     short loc_1800074B4
0x180007477  mov     rax, [r14+30h]
0x18000747b  lea     r8, [rsp+570h+var_508]; unsigned __int16 **
  ... truncated ...
```
