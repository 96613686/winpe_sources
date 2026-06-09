# SEARCH_RESULT_COLLECTION::AppendResultsFromConfigFile(ushort const *,CONFIG_SYSTEM *,MULTISZ *)

- ea: `0x1800469e8`
- end: `0x180046f05`
- name: `?AppendResultsFromConfigFile@SEARCH_RESULT_COLLECTION@@QEAAJPEBGPEAVCONFIG_SYSTEM@@PEAVMULTISZ@@@Z`
- size: `1309`
- prototype: `__int64 __fastcall(SEARCH_RESULT_COLLECTION *__hidden this, const unsigned __int16 *, struct CONFIG_SYSTEM *, struct MULTISZ *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config`

## callers

- `0x18003a834`

## callees

- `0x180016440`
- `0x180017850`
- `0x180017a1c`
- `0x180025f10`
- `0x180026b24`
- `0x18003a700`
- `0x1800469e8`
- `0x180046f0c`
- `0x180047044`
- `0x180059bea`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180046c99`
- `msvcrt!_wcsnicmp` at `0x180046c99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046de2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046de2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046eb3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046eb3`
- `iisutil!?QueryStringCount@MULTISZ@@QEBAKXZ` at `0x180046d6b`
- `iisutil!?QueryStringCount@MULTISZ@@QEBAKXZ` at `0x180046d6b`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x180046dc0`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x180046e0b`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x180046dc0`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x180046e0b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180046ec7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180046eda`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180046ec7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180046eda`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180046baf`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180046c41`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180046e25`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180046baf`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180046c41`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180046e25`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180046a58`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180046ac1`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180046a58`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180046ac1`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180046bbc`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180046bcf`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180046bbc`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180046bcf`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180046b9b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180046b9b`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180046c09`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180046c2d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180046c09`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180046c2d`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180046d37`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180046d37`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180046bdc`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180046bdc`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180046ad4`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180046ad4`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180046ebd`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180046ebd`

## pseudocode

```c
__int64 __fastcall SEARCH_RESULT_COLLECTION::AppendResultsFromConfigFile(
        SEARCH_RESULT_COLLECTION *this,
        const unsigned __int16 *a2,
        struct CONFIG_SYSTEM *a3,
        struct MULTISZ *a4)
{
  CONFIG_FILE *v7; // r14
  MULTISZ *v8; // r15
  CONFIG_ELEMENT_TABLE *v9; // rsi
  int ConfigFileInternal; // edi
  unsigned int i; // r12d
  unsigned __int16 *Str; // rbx
  unsigned int CCH; // eax
  const WCHAR *v14; // rax
  const unsigned __int16 *v15; // rdx
  unsigned __int16 *v16; // rax
  int v17; // edx
  size_t Length; // rax
  __int64 v19; // r9
  const wchar_t *v20; // r10
  unsigned __int64 v21; // rcx
  char *v22; // rbx
  unsigned int j; // r15d
  __int64 v24; // rcx
  __int64 v25; // rax
  signed int LastError; // eax
  HANDLE v27; // rbx
  const unsigned __int16 *v28; // rax
  SEARCH_RESULT_COLLECTION *v29; // rcx
  int appended; // eax
  unsigned int v32; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v33; // [rsp+44h] [rbp-BCh] BYREF
  int v34; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v35; // [rsp+50h] [rbp-B0h] BYREF
  CONFIG_ELEMENT_TABLE *v36; // [rsp+58h] [rbp-A8h] BYREF
  CONFIG_FILE *v37; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-98h] BYREF
  const unsigned __int16 *v39; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v40; // [rsp+78h] [rbp-88h] BYREF
  SEARCH_RESULT_COLLECTION *v41; // [rsp+80h] [rbp-80h]
  struct MULTISZ *v42; // [rsp+88h] [rbp-78h]
  void **v43; // [rsp+90h] [rbp-70h] BYREF
  __int64 v44; // [rsp+98h] [rbp-68h]
  int v45; // [rsp+A0h] [rbp-60h]
  __int64 v46; // [rsp+A8h] [rbp-58h]
  __int128 v47; // [rsp+B0h] [rbp-50h]
  __int128 v48; // [rsp+C0h] [rbp-40h]
  _BYTE v49[56]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v50[56]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v51[64]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 v52[128]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int16 v53[1024]; // [rsp+280h] [rbp+180h] BYREF

  v41 = this;
  v42 = a4;
  v37 = 0;
  v7 = 0;
  v8 = a4;
  memset_0(v53, 0, sizeof(v53));
  STRU::STRU((STRU *)v51, v53, 0x400u);
  hObject = 0;
  v43 = &PARSE_ERROR_INFO::`vftable';
  v47 = 0;
  v48 = 0;
  v34 = 0;
  v44 = 1;
  v45 = 0;
  v9 = 0;
  v46 = 0;
  v32 = 0;
  v36 = 0;
  memset_0(v52, 0, sizeof(v52));
  STRU::STRU((STRU *)v49, v52, 0x80u);
  v40 = 0;
  v33 = 0;
  MULTISZ::MULTISZ((MULTISZ *)v50);
  v35 = 0;
  v39 = 0;
  if ( a2 && v8 )
  {
    ConfigFileInternal = CONFIG_SYSTEM::GetConfigFileInternal(
                           a3,
                           a2,
                           &v37,
                           (struct STRU *)v51,
                           &hObject,
                           (enum _ALLOW_DEFINITION_LEVEL *)&v34,
                           (struct PARSE_ERROR_INFO *)&v43);
    if ( ConfigFileInternal >= 0 )
    {
      if ( (_DWORD)v44 == 1 )
      {
        v7 = v37;
        if ( v37 )
        {
          ConfigFileInternal = (*(__int64 (__fastcall **)(char *, unsigned int *))(*((_QWORD *)v37 + 2) + 24LL))(
                                 (char *)v37 + 16,
                                 &v32);
          if ( ConfigFileInternal < 0 )
            goto LABEL_56;
          for ( i = 0; ; ++i )
          {
            if ( i >= v32 )
            {
              v8 = v42;
              goto LABEL_48;
            }
            ConfigFileInternal = CONFIG_FILE::GetLocationByIndexInternal(v7, i, &v36);
            if ( ConfigFileInternal < 0 || (ConfigFileInternal = STRU::Copy((STRU *)v49, a2), ConfigFileInternal < 0) )
            {
              v9 = v36;
              goto LABEL_54;
            }
            Str = STRU::QueryStr((STRU *)v49);
            if ( Str[STRU::QueryCCH((STRU *)v49) - 1] == 47 )
            {
              CCH = STRU::QueryCCH((STRU *)v49);
              STRU::SetLen((STRU *)v49, CCH - 1);
            }
            v9 = v36;
            v14 = &szDomain;
            if ( *((_QWORD *)v36 + 12) )
              v14 = (const WCHAR *)*((_QWORD *)v36 + 12);
            if ( *v14 )
            {
              ConfigFileInternal = STRU::Append((STRU *)v49, L"/");
              if ( ConfigFileInternal < 0 )
                goto LABEL_54;
              v15 = &szDomain;
              if ( *((_QWORD *)v9 + 12) )
                v15 = (const unsigned __int16 *)*((_QWORD *)v9 + 12);
              ConfigFileInternal = STRU::Append((STRU *)v49, v15);
              if ( ConfigFileInternal < 0 )
                goto LABEL_54;
            }
            v16 = STRU::QueryStr((STRU *)v49);
            if ( v41 != (SEARCH_RESULT_COLLECTION *)-16LL )
            {
              v17 = *((_DWORD *)v41 + 10);
              if ( v17 != -1 )
              {
                if ( v16 )
                {
                  Length = PATH::GetLength((SEARCH_RESULT_COLLECTION *)((char *)v41 + 16), v17 - 1);
                  v21 = -1;
                  do
                    ++v21;
                  while ( v20[v21] );
                  if ( v21 >= Length && !_wcsnicmp(*(const wchar_t **)(v19 + 8), v20, Length) )
                    break;
                }
              }
            }
LABEL_43:
            CONFIG_ELEMENT_TABLE::DereferenceConfigElementTable(v9);
            v36 = 0;
            v9 = 0;
          }
          v22 = (char *)v9 + 16;
          ConfigFileInternal = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*((_QWORD *)v9 + 2) + 32LL))(
                                 (__int64)v9 + 16,
                                 &v33);
          if ( ConfigFileInternal >= 0 )
          {
            for ( j = 0; j < v33; ++j )
            {
              ConfigFileInternal = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *, _QWORD))(*(_QWORD *)v22 + 40LL))(
                                     (__int64)v9 + 16,
                                     j,
                                     &v35,
                                     0);
              if ( ConfigFileInternal < 0 )
                goto LABEL_54;
              v24 = v35;
              if ( v35 )
                v25 = v35 - 16;
              else
                v25 = 0;
              if ( (*(_BYTE *)(v25 + 36) & 2) == 0 )
              {
                ConfigFileInternal = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 **))(*(_QWORD *)v35 + 24LL))(
                                       v35,
                                       &v39);
                if ( ConfigFileInternal < 0 )
                  goto LABEL_54;
                if ( !MULTISZ::Append((MULTISZ *)v50, v39) )
                {
                  LastError = GetLastError();
                  ConfigFileInternal = LastError;
                  if ( LastError > 0 )
                    ConfigFileInternal = (unsigned __int16)LastError | 0x80070000;
                  goto LABEL_54;
                }
                v24 = v35;
              }
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
              v35 = 0;
            }
            if ( !MULTISZ::QueryStringCount((MULTISZ *)v50) )
              goto LABEL_43;
            ConfigFileInternal = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v22 + 24LL))(
                                   (__int64)v9 + 16,
                                   &v40);
            if ( ConfigFileInternal >= 0 )
            {
              ConfigFileInternal = SEARCH_RESULT_COLLECTION::CreateAndAppendSearchResult(
                                     v41,
                                     a2,
                                     v40,
                                     0,
                                     (struct MULTISZ *)v50);
              if ( ConfigFileInternal >= 0 )
              {
                MULTISZ::Reset((MULTISZ *)v50);
                goto LABEL_43;
              }
            }
          }
        }
        else
        {
LABEL_48:
          MULTISZ::Reset(v8);
          if ( (unsigned int)(v34 - 1) > 2 )
          {
            v27 = hObject;
            v28 = STRU::QueryStr((STRU *)v51);
            ConfigFileInternal = SEARCH_RESULT_COLLECTION::GetSubDirectoryLocations(v29, a2, v28, v27, v8);
          }
        }
        goto LABEL_54;
      }
      ConfigFileInternal = -2147024883;
      if ( (_DWORD)v44 == 2 )
        ConfigFileInternal = -2147024885;
    }
    appended = SEARCH_RESULT_COLLECTION::CreateAndAppendSearchResult(this, a2, &szDomain, ConfigFileInternal, 0);
    v7 = v37;
    ConfigFileInternal = appended;
    goto LABEL_56;
  }
  ConfigFileInternal = -2147024809;
LABEL_54:
  if ( v9 )
    CONFIG_ELEMENT_TABLE::DereferenceConfigElementTable(v9);
LABEL_56:
  if ( v35 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  if ( v7 )
    CONFIG_FILE::DereferenceConfigFile(v7);
  if ( hObject )
    CloseHandle(hObject);
  MULTISZ::~MULTISZ((MULTISZ *)v50);
  STRU::~STRU((STRU *)v49);
  PARSE_ERROR_INFO::~PARSE_ERROR_INFO((PARSE_ERROR_INFO *)&v43);
  STRU::~STRU((STRU *)v51);
  return (unsigned int)ConfigFileInternal;
}

```

## disassembly

```asm
0x1800469e8  push    rbp
0x1800469ea  push    rbx
0x1800469eb  push    rsi
0x1800469ec  push    rdi
0x1800469ed  push    r12
0x1800469ef  push    r13
0x1800469f1  push    r14
0x1800469f3  push    r15
0x1800469f5  lea     rbp, [rsp-998h]
0x1800469fd  sub     rsp, 0A98h
0x180046a04  mov     rax, cs:__security_cookie
0x180046a0b  xor     rax, rsp
0x180046a0e  mov     [rbp+9D0h+var_50], rax
0x180046a15  mov     rbx, r8
0x180046a18  mov     [rbp+9D0h+var_A50], rcx
0x180046a1c  mov     r13, rdx
0x180046a1f  mov     [rbp+9D0h+var_A48], r9
0x180046a23  mov     r12, rcx
0x180046a26  xor     edi, edi
0x180046a28  xor     edx, edx; Val
0x180046a2a  mov     [rsp+0AD0h+var_A70], rdi
0x180046a2f  mov     r8d, 800h; Size
0x180046a35  lea     rcx, [rbp+9D0h+var_850]; void *
0x180046a3c  mov     r14d, edi
0x180046a3f  mov     r15, r9
0x180046a42  call    memset_0
0x180046a47  mov     r8d, 400h
0x180046a4d  lea     rdx, [rbp+9D0h+var_850]
0x180046a54  lea     rcx, [rbp+9D0h+var_990]
0x180046a58  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180046a5e  lea     rax, ??_7PARSE_ERROR_INFO@@6B@; const PARSE_ERROR_INFO::`vftable'
0x180046a65  mov     [rsp+0AD0h+hObject], rdi
0x180046a6a  xorps   xmm0, xmm0
0x180046a6d  mov     [rbp+9D0h+var_A40], rax
0x180046a71  xorps   xmm1, xmm1
0x180046a74  movdqa  [rbp+9D0h+var_A20], xmm0
0x180046a79  xor     edx, edx; Val
0x180046a7b  movdqa  [rbp+9D0h+var_A10], xmm1
0x180046a80  mov     r8d, 100h; Size
0x180046a86  mov     [rsp+0AD0h+var_A88], edi
0x180046a8a  lea     rcx, [rbp+9D0h+var_950]; void *
0x180046a91  mov     [rbp+9D0h+var_A38], 1
0x180046a99  mov     [rbp+9D0h+var_A30], edi
0x180046a9c  mov     esi, edi
0x180046a9e  mov     [rbp+9D0h+var_A28], rdi
0x180046aa2  mov     [rsp+0AD0h+var_A90], edi
0x180046aa6  mov     [rsp+0AD0h+var_A78], rdi
0x180046aab  call    memset_0
0x180046ab0  mov     r8d, 80h
0x180046ab6  lea     rdx, [rbp+9D0h+var_950]
0x180046abd  lea     rcx, [rbp+9D0h+var_A00]
0x180046ac1  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180046ac7  lea     rcx, [rbp+9D0h+var_9C8]
0x180046acb  mov     [rsp+0AD0h+var_A58], rdi
0x180046ad0  mov     [rsp+0AD0h+var_A8C], edi
0x180046ad4  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180046ada  mov     [rsp+0AD0h+var_A80], rdi
0x180046adf  mov     [rsp+0AD0h+var_A60], rdi
0x180046ae4  test    r13, r13
0x180046ae7  jz      loc_180046E74
0x180046aed  test    r15, r15
0x180046af0  jz      loc_180046E74
0x180046af6  lea     rax, [rbp+9D0h+var_A40]
0x180046afa  mov     rdx, r13; unsigned __int16 *
0x180046afd  mov     [rsp+0AD0h+var_AA0], rax; struct PARSE_ERROR_INFO *
0x180046b02  lea     r9, [rbp+9D0h+var_990]; struct STRU *
0x180046b06  lea     rax, [rsp+0AD0h+var_A88]
0x180046b0b  mov     rcx, rbx; this
0x180046b0e  mov     [rsp+0AD0h+var_AA8], rax; enum _ALLOW_DEFINITION_LEVEL *
0x180046b13  lea     r8, [rsp+0AD0h+var_A70]; struct CONFIG_FILE **
0x180046b18  lea     rax, [rsp+0AD0h+hObject]
0x180046b1d  mov     [rsp+0AD0h+var_AB0], rax; void **
0x180046b22  call    ?GetConfigFileInternal@CONFIG_SYSTEM@@QEAAJPEBGPEAPEAVCONFIG_FILE@@PEAVSTRU@@PEAPEAXPEAW4_ALLOW_DEFINITION_LEVEL@@PEAVPARSE_ERROR_INFO@@@Z; CONFIG_SYSTEM::GetConfigFileInternal(ushort const *,CONFIG_FILE * *,STRU *,void * *,_ALLOW_DEFINITION_LEVEL *,PARSE_ERROR_INFO *)
0x180046b27  xor     ebx, ebx
0x180046b29  mov     edi, eax
0x180046b2b  test    eax, eax
0x180046b2d  js      loc_180046E51
0x180046b33  mov     ecx, dword ptr [rbp+9D0h+var_A38]
0x180046b36  cmp     ecx, 1
0x180046b39  jnz     loc_180046E42
0x180046b3f  mov     r14, [rsp+0AD0h+var_A70]
0x180046b44  test    r14, r14
0x180046b47  jz      loc_180046E08
0x180046b4d  lea     rcx, [r14+10h]
0x180046b51  mov     rax, [rcx]
0x180046b54  lea     rdx, [rsp+0AD0h+var_A90]
0x180046b59  mov     rax, [rax+18h]
0x180046b5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046b62  mov     edi, eax
0x180046b64  test    eax, eax
0x180046b66  js      loc_180046E86
0x180046b6c  mov     r12d, ebx
0x180046b6f  cmp     r12d, [rsp+0AD0h+var_A90]
0x180046b74  jnb     loc_180046E04
0x180046b7a  lea     r8, [rsp+0AD0h+var_A78]; struct CONFIG_ELEMENT_TABLE **
0x180046b7f  mov     edx, r12d; unsigned int
0x180046b82  mov     rcx, r14; this
0x180046b85  call    ?GetLocationByIndexInternal@CONFIG_FILE@@QEAAJKPEAPEAVCONFIG_ELEMENT_TABLE@@@Z; CONFIG_FILE::GetLocationByIndexInternal(ulong,CONFIG_ELEMENT_TABLE * *)
0x180046b8a  mov     edi, eax
0x180046b8c  test    eax, eax
0x180046b8e  js      loc_180046DFD
0x180046b94  mov     rdx, r13
0x180046b97  lea     rcx, [rbp+9D0h+var_A00]
0x180046b9b  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180046ba1  mov     edi, eax
0x180046ba3  test    eax, eax
0x180046ba5  js      loc_180046DFD
0x180046bab  lea     rcx, [rbp+9D0h+var_A00]
0x180046baf  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180046bb5  lea     rcx, [rbp+9D0h+var_A00]
0x180046bb9  mov     rbx, rax
0x180046bbc  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180046bc2  dec     eax
0x180046bc4  cmp     word ptr [rbx+rax*2], 2Fh ; '/'
0x180046bc9  jnz     short loc_180046BE2
0x180046bcb  lea     rcx, [rbp+9D0h+var_A00]
0x180046bcf  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180046bd5  lea     rcx, [rbp+9D0h+var_A00]
0x180046bd9  lea     edx, [rax-1]
0x180046bdc  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x180046be2  mov     rsi, [rsp+0AD0h+var_A78]
0x180046be7  lea     rax, szDomain
0x180046bee  xor     ebx, ebx
0x180046bf0  cmp     [rsi+60h], rbx
0x180046bf4  cmovnz  rax, [rsi+60h]
0x180046bf9  cmp     [rax], bx
0x180046bfc  jz      short loc_180046C3D
0x180046bfe  lea     rdx, asc_18005F044; "/"
0x180046c05  lea     rcx, [rbp+9D0h+var_A00]
0x180046c09  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180046c0f  mov     edi, eax
0x180046c11  test    eax, eax
0x180046c13  js      loc_180046E79
0x180046c19  cmp     [rsi+60h], rbx
0x180046c1d  lea     rdx, szDomain
0x180046c24  lea     rcx, [rbp+9D0h+var_A00]
0x180046c28  cmovnz  rdx, [rsi+60h]
0x180046c2d  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180046c33  mov     edi, eax
0x180046c35  test    eax, eax
0x180046c37  js      loc_180046E79
0x180046c3d  lea     rcx, [rbp+9D0h+var_A00]
0x180046c41  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180046c47  mov     r9, [rbp+9D0h+var_A50]
0x180046c4b  mov     r10, rax
0x180046c4e  add     r9, 10h
0x180046c52  jz      loc_180046DCA
0x180046c58  mov     edx, [r9+18h]
0x180046c5c  cmp     edx, 0FFFFFFFFh
0x180046c5f  jz      loc_180046DCA
0x180046c65  test    rax, rax
0x180046c68  jz      loc_180046DCA
0x180046c6e  dec     edx; unsigned int
0x180046c70  mov     rcx, r9; this
0x180046c73  call    ?GetLength@PATH@@QEAA_KK@Z; PATH::GetLength(ulong)
0x180046c78  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180046c7c  inc     rcx
0x180046c7f  cmp     [r10+rcx*2], bx
0x180046c84  jnz     short loc_180046C7C
0x180046c86  cmp     rcx, rax
0x180046c89  jb      loc_180046DCA
0x180046c8f  mov     rcx, [r9+8]; String1
0x180046c93  mov     r8, rax; MaxCount
0x180046c96  mov     rdx, r10; String2
0x180046c99  call    cs:__imp__wcsnicmp
0x180046c9f  test    eax, eax
0x180046ca1  jnz     loc_180046DCA
0x180046ca7  lea     rbx, [rsi+10h]
0x180046cab  mov     rax, [rbx]
0x180046cae  lea     rdx, [rsp+0AD0h+var_A8C]
0x180046cb3  mov     rcx, rbx
0x180046cb6  mov     rax, [rax+20h]
0x180046cba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046cbf  mov     edi, eax
0x180046cc1  test    eax, eax
0x180046cc3  js      loc_180046E79
0x180046cc9  xor     r15d, r15d
0x180046ccc  cmp     r15d, [rsp+0AD0h+var_A8C]
0x180046cd1  jnb     loc_180046D67
0x180046cd7  mov     rax, [rbx]
0x180046cda  lea     r8, [rsp+0AD0h+var_A80]
0x180046cdf  xor     r9d, r9d
0x180046ce2  mov     edx, r15d
0x180046ce5  mov     rcx, rbx
0x180046ce8  mov     rax, [rax+28h]
0x180046cec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046cf1  mov     edi, eax
0x180046cf3  test    eax, eax
0x180046cf5  js      loc_180046E79
0x180046cfb  mov     rcx, [rsp+0AD0h+var_A80]
0x180046d00  test    rcx, rcx
0x180046d03  jz      short loc_180046D0B
0x180046d05  lea     rax, [rcx-10h]
0x180046d09  jmp     short loc_180046D0D
0x180046d0b  xor     eax, eax
0x180046d0d  test    byte ptr [rax+24h], 2
0x180046d11  jnz     short loc_180046D4A
0x180046d13  mov     rax, [rcx]
0x180046d16  lea     rdx, [rsp+0AD0h+var_A60]
0x180046d1b  mov     rax, [rax+18h]
0x180046d1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046d24  mov     edi, eax
0x180046d26  test    eax, eax
0x180046d28  js      loc_180046E79
0x180046d2e  mov     rdx, [rsp+0AD0h+var_A60]
0x180046d33  lea     rcx, [rbp+9D0h+var_9C8]
0x180046d37  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x180046d3d  test    eax, eax
0x180046d3f  jz      loc_180046DE2
0x180046d45  mov     rcx, [rsp+0AD0h+var_A80]
0x180046d4a  mov     rax, [rcx]
0x180046d4d  mov     rax, [rax+10h]
0x180046d51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046d56  inc     r15d
0x180046d59  mov     [rsp+0AD0h+var_A80], 0
0x180046d62  jmp     loc_180046CCC
0x180046d67  lea     rcx, [rbp+9D0h+var_9C8]
0x180046d6b  call    cs:__imp_?QueryStringCount@MULTISZ@@QEBAKXZ; MULTISZ::QueryStringCount(void)
0x180046d71  test    eax, eax
0x180046d73  jz      short loc_180046DC8
0x180046d75  mov     rax, [rbx]
0x180046d78  lea     rdx, [rsp+0AD0h+var_A58]
0x180046d7d  mov     rcx, rbx
0x180046d80  mov     rax, [rax+18h]
0x180046d84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046d89  xor     ebx, ebx
0x180046d8b  mov     edi, eax
0x180046d8d  test    eax, eax
0x180046d8f  js      loc_180046E79
0x180046d95  mov     r8, [rsp+0AD0h+var_A58]; unsigned __int16 *
0x180046d9a  lea     rax, [rbp+9D0h+var_9C8]
0x180046d9e  mov     rcx, [rbp+9D0h+var_A50]; this
0x180046da2  xor     r9d, r9d; int
0x180046da5  mov     rdx, r13; unsigned __int16 *
0x180046da8  mov     [rsp+0AD0h+var_AB0], rax; struct MULTISZ *
0x180046dad  call    ?CreateAndAppendSearchResult@SEARCH_RESULT_COLLECTION@@AEAAJPEBG0JPEAVMULTISZ@@@Z; SEARCH_RESULT_COLLECTION::CreateAndAppendSearchResult(ushort const *,ushort const *,long,MULTISZ *)
0x180046db2  mov     edi, eax
0x180046db4  test    eax, eax
0x180046db6  js      loc_180046E79
0x180046dbc  lea     rcx, [rbp+9D0h+var_9C8]
0x180046dc0  call    cs:__imp_?Reset@MULTISZ@@QEAAXXZ; MULTISZ::Reset(void)
0x180046dc6  jmp     short loc_180046DCA
0x180046dc8  xor     ebx, ebx
0x180046dca  mov     rcx, rsi; this
0x180046dcd  call    ?DereferenceConfigElementTable@CONFIG_ELEMENT_TABLE@@QEAAXXZ; CONFIG_ELEMENT_TABLE::DereferenceConfigElementTable(void)
0x180046dd2  inc     r12d
0x180046dd5  mov     [rsp+0AD0h+var_A78], rbx
0x180046dda  mov     rsi, rbx
0x180046ddd  jmp     loc_180046B6F
0x180046de2  call    cs:__imp_GetLastError
0x180046de8  mov     edi, eax
0x180046dea  test    eax, eax
0x180046dec  jle     loc_180046E79
0x180046df2  movzx   edi, ax
0x180046df5  or      edi, 80070000h
0x180046dfb  jmp     short loc_180046E79
0x180046dfd  mov     rsi, [rsp+0AD0h+var_A78]
0x180046e02  jmp     short loc_180046E79
0x180046e04  mov     r15, [rbp+9D0h+var_A48]
0x180046e08  mov     rcx, r15
0x180046e0b  call    cs:__imp_?Reset@MULTISZ@@QEAAXXZ; MULTISZ::Reset(void)
0x180046e11  mov     eax, [rsp+0AD0h+var_A88]
0x180046e15  dec     eax
0x180046e17  cmp     eax, 2
0x180046e1a  jbe     short loc_180046E79
0x180046e1c  mov     rbx, [rsp+0AD0h+hObject]
0x180046e21  lea     rcx, [rbp+9D0h+var_990]
0x180046e25  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180046e2b  mov     r9, rbx; void *
0x180046e2e  mov     [rsp+0AD0h+var_AB0], r15; struct MULTISZ *
0x180046e33  mov     r8, rax; unsigned __int16 *
0x180046e36  mov     rdx, r13; unsigned __int16 *
0x180046e39  call    ?GetSubDirectoryLocations@SEARCH_RESULT_COLLECTION@@AEAAJPEBG0PEAXPEAVMULTISZ@@@Z; SEARCH_RESULT_COLLECTION::GetSubDirectoryLocations(ushort const *,ushort const *,void *,MULTISZ *)
0x180046e3e  mov     edi, eax
0x180046e40  jmp     short loc_180046E79
0x180046e42  mov     edi, 8007000Dh
0x180046e47  sub     ecx, 2
0x180046e4a  jnz     short loc_180046E51
0x180046e4c  mov     edi, 8007000Bh
0x180046e51  mov     r9d, edi; int
0x180046e54  mov     [rsp+0AD0h+var_AB0], rbx; struct MULTISZ *
0x180046e59  lea     r8, szDomain; unsigned __int16 *
0x180046e60  mov     rdx, r13; unsigned __int16 *
0x180046e63  mov     rcx, r12; this
0x180046e66  call    ?CreateAndAppendSearchResult@SEARCH_RESULT_COLLECTION@@AEAAJPEBG0JPEAVMULTISZ@@@Z; SEARCH_RESULT_COLLECTION::CreateAndAppendSearchResult(ushort const *,ushort const *,long,MULTISZ *)
0x180046e6b  mov     r14, [rsp+0AD0h+var_A70]
0x180046e70  mov     edi, eax
0x180046e72  jmp     short loc_180046E86
0x180046e74  mov     edi, 80070057h
0x180046e79  test    rsi, rsi
0x180046e7c  jz      short loc_180046E86
0x180046e7e  mov     rcx, rsi; this
0x180046e81  call    ?DereferenceConfigElementTable@CONFIG_ELEMENT_TABLE@@QEAAXXZ; CONFIG_ELEMENT_TABLE::DereferenceConfigElementTable(void)
0x180046e86  mov     rcx, [rsp+0AD0h+var_A80]
0x180046e8b  test    rcx, rcx
0x180046e8e  jz      short loc_180046E9C
0x180046e90  mov     rax, [rcx]
0x180046e93  mov     rax, [rax+10h]
0x180046e97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046e9c  test    r14, r14
  ... truncated ...
```
