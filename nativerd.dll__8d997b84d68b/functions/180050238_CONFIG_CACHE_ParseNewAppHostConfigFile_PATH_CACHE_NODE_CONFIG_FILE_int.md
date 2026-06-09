# CONFIG_CACHE::ParseNewAppHostConfigFile(_PATH_CACHE_NODE *,CONFIG_FILE * *,int *)

- ea: `0x180050238`
- end: `0x180050615`
- name: `?ParseNewAppHostConfigFile@CONFIG_CACHE@@AEAAJPEAU_PATH_CACHE_NODE@@PEAPEAVCONFIG_FILE@@PEAH@Z`
- size: `989`
- prototype: `__int64 __fastcall(unsigned int **this, struct _PATH_CACHE_NODE *, struct CONFIG_FILE **, int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004fae0`

## callees

- `0x1800012c0`
- `0x180003480`
- `0x180016440`
- `0x1800174d0`
- `0x18001753c`
- `0x180017610`
- `0x180017850`
- `0x1800178dc`
- `0x180019a80`
- `0x18001be64`
- `0x18004ebb4`
- `0x180050238`
- `0x180053068`
- `0x180059bea`
- `0x180059c30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050424`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050424`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180050450`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180050450`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18005041a`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18005041a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050572`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005059f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800505b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050572`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005059f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800505b8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800505ea`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800505ea`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800503cc`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800504a1`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800503cc`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800504a1`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18005029a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18005029a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180050386`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180050386`

## pseudocode

```c
__int64 __fastcall CONFIG_CACHE::ParseNewAppHostConfigFile(
        unsigned int **this,
        struct _PATH_CACHE_NODE *a2,
        struct CONFIG_FILE **a3,
        int *a4)
{
  __int64 v8; // rsi
  CONFIG_FILE *v9; // r14
  CONFIG_FILE *v10; // rdi
  int ConfigFileInternal; // ebx
  __int64 v12; // rax
  const unsigned __int16 *v13; // rdx
  const unsigned __int16 *ParseErrorFileName; // rbx
  const unsigned __int16 *Str; // rax
  int FileHandle; // eax
  signed int LastError; // eax
  int v18; // r15d
  struct CONFIG_FILE **v19; // rax
  HANDLE v20; // rbx
  HANDLE v21; // rdi
  const unsigned __int16 *v22; // rax
  int v23; // eax
  int v24; // eax
  unsigned int v26; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-98h] BYREF
  HANDLE TokenHandle; // [rsp+70h] [rbp-90h] BYREF
  HANDLE hFile; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v30; // [rsp+80h] [rbp-80h]
  CONFIG_FILE *v31; // [rsp+88h] [rbp-78h] BYREF
  struct CONFIG_FILE *v32; // [rsp+90h] [rbp-70h] BYREF
  struct _FILETIME LastWriteTime; // [rsp+98h] [rbp-68h] BYREF
  struct CONFIG_FILE **v34; // [rsp+A0h] [rbp-60h]
  _QWORD v35[2]; // [rsp+B0h] [rbp-50h] BYREF
  int v36; // [rsp+C0h] [rbp-40h]
  __int64 v37; // [rsp+C8h] [rbp-38h]
  __int128 v38; // [rsp+D0h] [rbp-30h]
  __int128 v39; // [rsp+E0h] [rbp-20h]
  _BYTE v40[64]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v41[3]; // [rsp+130h] [rbp+30h] BYREF
  int v42; // [rsp+148h] [rbp+48h]
  int v43; // [rsp+14Ch] [rbp+4Ch]
  int v44; // [rsp+150h] [rbp+50h]
  char v45; // [rsp+154h] [rbp+54h] BYREF
  unsigned __int16 v46[264]; // [rsp+2E0h] [rbp+1E0h] BYREF

  v34 = a3;
  memset_0(v46, 0, 0x208u);
  STRU::STRU((STRU *)v40, v46, 0x104u);
  v44 &= 0xFFFFFFF0;
  v35[0] = &PARSE_ERROR_INFO::`vftable';
  v26 = 0;
  v8 = -1;
  v41[0] = &v45;
  v35[1] = 1;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v9 = 0;
  v39 = 0;
  v10 = 0;
  hObject = 0;
  TokenHandle = 0;
  LastWriteTime = 0;
  v32 = 0;
  hFile = (HANDLE)-1LL;
  v31 = 0;
  v41[1] = 0;
  v41[2] = 0;
  v42 = -1;
  v43 = -1;
  if ( !a2 || !a3 || !a4 )
  {
    v18 = 0;
    ConfigFileInternal = -2147024809;
    goto LABEL_26;
  }
  ConfigFileInternal = PATH::Parse((PATH *)v41, L"MACHINE/WEBROOT/APPHOST");
  if ( ConfigFileInternal >= 0 )
  {
    ConfigFileInternal = CONFIG_PATH_MAPPER::MapConfigFast((CONFIG_PATH_MAPPER *)(this + 8), a2, 0, &hObject, &v26);
    if ( ConfigFileInternal >= 0 )
    {
      v12 = *((_QWORD *)a2 + 4);
      v13 = &szDomain;
      if ( *(_QWORD *)(v12 + 40) )
        v13 = *(const unsigned __int16 **)(v12 + 40);
      ConfigFileInternal = STRU::Copy((STRU *)v40, v13);
      if ( ConfigFileInternal >= 0 )
      {
        v30 = *(_DWORD *)(*((_QWORD *)a2 + 4) + 276LL);
        ConfigFileInternal = CONFIG_CACHE::Impersonate(hObject, &TokenHandle);
        if ( ConfigFileInternal >= 0 )
        {
          ParseErrorFileName = CONFIG_FILE::QueryParseErrorFileName(*((CONFIG_FILE **)a2 + 4));
          Str = STRU::QueryStr((STRU *)v40);
          FileHandle = CONFIG_CACHE::GetFileHandle(
                         Str,
                         &v26,
                         &hFile,
                         ParseErrorFileName,
                         (struct PARSE_ERROR_INFO *)v35);
          v8 = (__int64)hFile;
          ConfigFileInternal = FileHandle;
          if ( FileHandle >= 0 )
          {
            if ( (v26 & 0x300) == 0x300 )
            {
              if ( !GetFileTime(hFile, 0, 0, &LastWriteTime) )
              {
                LastError = GetLastError();
                ConfigFileInternal = LastError;
                if ( LastError > 0 )
                  ConfigFileInternal = (unsigned __int16)LastError | 0x80070000;
                goto LABEL_15;
              }
              if ( !CompareFileTime((const FILETIME *)(*((_QWORD *)a2 + 4) + 56LL), &LastWriteTime) )
              {
                v19 = v34;
                v18 = 1;
                *a4 = 1;
                ConfigFileInternal = 0;
                *v19 = 0;
                goto LABEL_28;
              }
              *a4 = 0;
              ConfigFileInternal = CONFIG_CACHE::GetConfigFileInternal((CONFIG_CACHE *)this, L"MACHINE/WEBROOT", &v32);
              if ( ConfigFileInternal >= 0 )
              {
                v20 = hObject;
                v21 = TokenHandle;
                v22 = STRU::QueryStr((STRU *)v40);
                v9 = v32;
                v23 = CONFIG_CACHE::CreateConfigFile(
                        (CONFIG_CACHE *)this,
                        (struct PATH *)v41,
                        2u,
                        v22,
                        v26,
                        0,
                        (void *)v8,
                        v32,
                        v21,
                        v20,
                        v30,
                        &v31);
                v10 = v31;
                ConfigFileInternal = v23;
                if ( v23 < 0 )
                {
                  v18 = 1;
                }
                else
                {
                  ConfigFileInternal = CONFIG_CACHE::ParseConfigFile(
                                         0,
                                         v31,
                                         (void *)v8,
                                         *this[2],
                                         0,
                                         0,
                                         (struct PARSE_ERROR_INFO *)v35);
                  v18 = 1;
                  if ( ConfigFileInternal >= 0 )
                  {
                    *v34 = v10;
                    goto LABEL_28;
                  }
                }
LABEL_26:
                if ( v10 )
                  CONFIG_FILE::DereferenceConfigFile(v10);
                goto LABEL_28;
              }
              v9 = v32;
            }
            else
            {
              ConfigFileInternal = -2147024894;
            }
          }
LABEL_15:
          v18 = 1;
LABEL_28:
          if ( v8 != -1 )
            CloseHandle((HANDLE)v8);
          if ( v18 )
          {
            v24 = CONFIG_CACHE::Unimpersonate(hObject, TokenHandle);
            if ( v24 < 0 && ConfigFileInternal >= 0 )
              ConfigFileInternal = v24;
          }
        }
      }
    }
  }
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  if ( v9 )
    CONFIG_FILE::DereferenceConfigFile(v9);
  PATH::Destroy((PATH *)v41);
  PARSE_ERROR_INFO::~PARSE_ERROR_INFO((PARSE_ERROR_INFO *)v35);
  STRU::~STRU((STRU *)v40);
  return (unsigned int)ConfigFileInternal;
}

```

## disassembly

```asm
0x180050238  push    rbp
0x18005023a  push    rbx
0x18005023b  push    rsi
0x18005023c  push    rdi
0x18005023d  push    r12
0x18005023f  push    r13
0x180050241  push    r14
0x180050243  push    r15
0x180050245  lea     rbp, [rsp-408h]
0x18005024d  sub     rsp, 508h
0x180050254  mov     rax, cs:__security_cookie
0x18005025b  xor     rax, rsp
0x18005025e  mov     [rbp+440h+var_50], rax
0x180050265  mov     rbx, r8
0x180050268  mov     r15, rdx
0x18005026b  mov     r13, rcx
0x18005026e  mov     [rbp+440h+var_4A0], rbx
0x180050272  xor     edx, edx; Val
0x180050274  lea     rcx, [rbp+440h+var_260]; void *
0x18005027b  mov     r8d, 208h; Size
0x180050281  mov     r12, r9
0x180050284  call    memset_0
0x180050289  mov     r8d, 104h
0x18005028f  lea     rdx, [rbp+440h+var_260]
0x180050296  lea     rcx, [rbp+440h+var_450]
0x18005029a  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800502a0  and     [rbp+440h+var_3F0], 0FFFFFFF0h
0x1800502a4  lea     rax, ??_7PARSE_ERROR_INFO@@6B@; const PARSE_ERROR_INFO::`vftable'
0x1800502ab  xor     ecx, ecx
0x1800502ad  mov     [rbp+440h+var_490], rax
0x1800502b1  lea     rax, [rbp+440h+var_3EC]
0x1800502b5  mov     [rsp+540h+var_4E0], ecx
0x1800502b9  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800502bd  mov     [rbp+440h+var_410], rax
0x1800502c1  or      eax, 0FFFFFFFFh
0x1800502c4  mov     [rbp+440h+var_488], 1
0x1800502cc  mov     [rbp+440h+var_480], ecx
0x1800502cf  xorps   xmm0, xmm0
0x1800502d2  mov     [rbp+440h+var_478], rcx
0x1800502d6  xorps   xmm1, xmm1
0x1800502d9  movdqa  [rbp+440h+var_470], xmm0
0x1800502de  mov     r14d, ecx
0x1800502e1  movdqa  [rbp+440h+var_460], xmm1
0x1800502e6  mov     edi, ecx
0x1800502e8  mov     [rsp+540h+hObject], rcx
0x1800502ed  mov     [rsp+540h+TokenHandle], rcx
0x1800502f2  mov     qword ptr [rbp+440h+LastWriteTime.dwLowDateTime], rcx
0x1800502f6  mov     [rbp+440h+var_4B0], rcx
0x1800502fa  mov     [rsp+540h+hFile], rsi
0x1800502ff  mov     [rbp+440h+var_4B8], rcx
0x180050303  mov     [rbp+440h+var_408], rcx
0x180050307  mov     [rbp+440h+var_400], rcx
0x18005030b  mov     [rbp+440h+var_3F8], eax
0x18005030e  mov     [rbp+440h+var_3F4], eax
0x180050311  test    r15, r15
0x180050314  jz      loc_180050554
0x18005031a  test    rbx, rbx
0x18005031d  jz      loc_180050554
0x180050323  test    r12, r12
0x180050326  jz      loc_180050554
0x18005032c  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180050333  lea     rcx, [rbp+440h+var_410]; this
0x180050337  call    ?Parse@PATH@@QEAAJPEBG@Z; PATH::Parse(ushort const *)
0x18005033c  mov     ebx, eax
0x18005033e  test    eax, eax
0x180050340  js      loc_180050595
0x180050346  lea     rax, [rsp+540h+var_4E0]
0x18005034b  xor     r8d, r8d; struct STRU *
0x18005034e  lea     rcx, [r13+40h]; this
0x180050352  mov     [rsp+540h+var_520], rax; unsigned int *
0x180050357  lea     r9, [rsp+540h+hObject]; void **
0x18005035c  mov     rdx, r15; struct _PATH_CACHE_NODE *
0x18005035f  call    ?MapConfigFast@CONFIG_PATH_MAPPER@@QEAAJPEAU_PATH_CACHE_NODE@@PEAVSTRU@@PEAPEAXPEAK@Z; CONFIG_PATH_MAPPER::MapConfigFast(_PATH_CACHE_NODE *,STRU *,void * *,ulong *)
0x180050364  mov     ebx, eax
0x180050366  test    eax, eax
0x180050368  js      loc_180050595
0x18005036e  mov     rax, [r15+20h]
0x180050372  lea     rdx, szDomain
0x180050379  lea     rcx, [rbp+440h+var_450]
0x18005037d  cmp     [rax+28h], rdi
0x180050381  cmovnz  rdx, [rax+28h]
0x180050386  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18005038c  mov     ebx, eax
0x18005038e  test    eax, eax
0x180050390  js      loc_180050595
0x180050396  mov     rax, [r15+20h]
0x18005039a  lea     rdx, [rsp+540h+TokenHandle]; TokenHandle
0x18005039f  mov     rcx, [rsp+540h+hObject]; hToken
0x1800503a4  mov     eax, [rax+114h]
0x1800503aa  mov     [rbp+440h+var_4C0], eax
0x1800503ad  call    ?Impersonate@CONFIG_CACHE@@SAJPEAXPEAPEAX@Z; CONFIG_CACHE::Impersonate(void *,void * *)
0x1800503b2  mov     ebx, eax
0x1800503b4  test    eax, eax
0x1800503b6  js      loc_180050595
0x1800503bc  mov     rcx, [r15+20h]; this
0x1800503c0  call    ?QueryParseErrorFileName@CONFIG_FILE@@QEBAPEBGXZ; CONFIG_FILE::QueryParseErrorFileName(void)
0x1800503c5  lea     rcx, [rbp+440h+var_450]
0x1800503c9  mov     rbx, rax
0x1800503cc  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800503d2  lea     rcx, [rbp+440h+var_490]
0x1800503d6  mov     r9, rbx; unsigned __int16 *
0x1800503d9  mov     [rsp+540h+var_520], rcx; struct PARSE_ERROR_INFO *
0x1800503de  lea     r8, [rsp+540h+hFile]; void **
0x1800503e3  mov     rcx, rax; unsigned __int16 *
0x1800503e6  lea     rdx, [rsp+540h+var_4E0]; unsigned int *
0x1800503eb  call    ?GetFileHandle@CONFIG_CACHE@@SAJPEBGPEAKPEAPEAX0PEAVPARSE_ERROR_INFO@@@Z; CONFIG_CACHE::GetFileHandle(ushort const *,ulong *,void * *,ushort const *,PARSE_ERROR_INFO *)
0x1800503f0  mov     rsi, [rsp+540h+hFile]
0x1800503f5  mov     ebx, eax
0x1800503f7  test    eax, eax
0x1800503f9  js      short loc_180050439
0x1800503fb  mov     eax, [rsp+540h+var_4E0]
0x1800503ff  mov     ecx, 300h
0x180050404  and     eax, ecx
0x180050406  cmp     eax, ecx
0x180050408  jnz     loc_18005054A
0x18005040e  lea     r9, [rbp+440h+LastWriteTime]; lpLastWriteTime
0x180050412  xor     r8d, r8d; lpLastAccessTime
0x180050415  xor     edx, edx; lpCreationTime
0x180050417  mov     rcx, rsi; hFile
0x18005041a  call    cs:__imp_GetFileTime
0x180050420  test    eax, eax
0x180050422  jnz     short loc_180050444
0x180050424  call    cs:__imp_GetLastError
0x18005042a  mov     ebx, eax
0x18005042c  test    eax, eax
0x18005042e  jle     short loc_180050439
0x180050430  movzx   ebx, ax
0x180050433  or      ebx, 80070000h
0x180050439  mov     r15d, 1
0x18005043f  jmp     loc_180050569
0x180050444  mov     rcx, [r15+20h]
0x180050448  lea     rdx, [rbp+440h+LastWriteTime]; lpFileTime2
0x18005044c  add     rcx, 38h ; '8'; lpFileTime1
0x180050450  call    cs:__imp_CompareFileTime
0x180050456  xor     ecx, ecx
0x180050458  test    eax, eax
0x18005045a  jnz     short loc_180050472
0x18005045c  mov     rax, [rbp+440h+var_4A0]
0x180050460  lea     r15d, [rcx+1]
0x180050464  mov     [r12], r15d
0x180050468  mov     ebx, ecx
0x18005046a  mov     [rax], rcx
0x18005046d  jmp     loc_180050569
0x180050472  mov     [r12], ecx
0x180050476  lea     r8, [rbp+440h+var_4B0]; struct CONFIG_FILE **
0x18005047a  mov     rcx, r13; this
0x18005047d  lea     rdx, aMachineWebroot_0; "MACHINE/WEBROOT"
0x180050484  call    ?GetConfigFileInternal@CONFIG_CACHE@@QEAAJPEBGPEAPEAVCONFIG_FILE@@@Z; CONFIG_CACHE::GetConfigFileInternal(ushort const *,CONFIG_FILE * *)
0x180050489  mov     ebx, eax
0x18005048b  test    eax, eax
0x18005048d  js      loc_180050541
0x180050493  mov     rbx, [rsp+540h+hObject]
0x180050498  lea     rcx, [rbp+440h+var_450]
0x18005049c  mov     rdi, [rsp+540h+TokenHandle]
0x1800504a1  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800504a7  mov     r14, [rbp+440h+var_4B0]
0x1800504ab  lea     rcx, [rbp+440h+var_4B8]
0x1800504af  mov     [rsp+540h+var_4E8], rcx; struct CONFIG_FILE **
0x1800504b4  lea     rdx, [rbp+440h+var_410]; struct PATH *
0x1800504b8  mov     ecx, [rbp+440h+var_4C0]
0x1800504bb  mov     r9, rax; unsigned __int16 *
0x1800504be  mov     [rsp+540h+var_4F0], ecx; unsigned int
0x1800504c2  mov     r8d, 2; unsigned int
0x1800504c8  mov     ecx, [rsp+540h+var_4E0]
0x1800504cc  mov     [rsp+540h+var_4F8], rbx; void *
0x1800504d1  mov     [rsp+540h+var_500], rdi; void *
0x1800504d6  mov     [rsp+540h+var_508], r14; struct CONFIG_FILE *
0x1800504db  mov     [rsp+540h+var_510], rsi; void *
0x1800504e0  mov     dword ptr [rsp+540h+var_518], 0; int
0x1800504e8  mov     dword ptr [rsp+540h+var_520], ecx; unsigned int
0x1800504ec  mov     rcx, r13; this
0x1800504ef  call    ?CreateConfigFile@CONFIG_CACHE@@AEAAJPEAVPATH@@KPEBGKHPEAXPEAVCONFIG_FILE@@22KPEAPEAV3@@Z; CONFIG_CACHE::CreateConfigFile(PATH *,ulong,ushort const *,ulong,int,void *,CONFIG_FILE *,void *,void *,ulong,CONFIG_FILE * *)
0x1800504f4  mov     rdi, [rbp+440h+var_4B8]
0x1800504f8  xor     ecx, ecx; this
0x1800504fa  mov     ebx, eax
0x1800504fc  test    eax, eax
0x1800504fe  js      short loc_180050539
0x180050500  mov     r9, [r13+10h]
0x180050504  lea     rax, [rbp+440h+var_490]
0x180050508  mov     [rsp+540h+var_510], rax; struct PARSE_ERROR_INFO *
0x18005050d  mov     r8, rsi; void *
0x180050510  mov     [rsp+540h+var_518], rcx; struct DELAY_LOAD_LOCATION_TAG_INFO *
0x180050515  mov     rdx, rdi; struct CONFIG_FILE *
0x180050518  mov     dword ptr [rsp+540h+var_520], ecx; int
0x18005051c  mov     r9d, [r9]; unsigned int
0x18005051f  call    ?ParseConfigFile@CONFIG_CACHE@@AEAAJPEAVCONFIG_FILE@@PEAXKHPEAVDELAY_LOAD_LOCATION_TAG_INFO@@PEAVPARSE_ERROR_INFO@@@Z; CONFIG_CACHE::ParseConfigFile(CONFIG_FILE *,void *,ulong,int,DELAY_LOAD_LOCATION_TAG_INFO *,PARSE_ERROR_INFO *)
0x180050524  mov     ebx, eax
0x180050526  mov     r15d, 1
0x18005052c  test    eax, eax
0x18005052e  js      short loc_18005055C
0x180050530  mov     rax, [rbp+440h+var_4A0]
0x180050534  mov     [rax], rdi
0x180050537  jmp     short loc_180050569
0x180050539  mov     r15d, 1
0x18005053f  jmp     short loc_18005055C
0x180050541  mov     r14, [rbp+440h+var_4B0]
0x180050545  jmp     loc_180050439
0x18005054a  mov     ebx, 80070002h
0x18005054f  jmp     loc_180050439
0x180050554  mov     r15d, ecx
0x180050557  mov     ebx, 80070057h
0x18005055c  test    rdi, rdi
0x18005055f  jz      short loc_180050569
0x180050561  mov     rcx, rdi; this
0x180050564  call    ?DereferenceConfigFile@CONFIG_FILE@@QEAAXXZ; CONFIG_FILE::DereferenceConfigFile(void)
0x180050569  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18005056d  jz      short loc_180050578
0x18005056f  mov     rcx, rsi; hObject
0x180050572  call    cs:__imp_CloseHandle
0x180050578  test    r15d, r15d
0x18005057b  jz      short loc_180050595
0x18005057d  mov     rdx, [rsp+540h+TokenHandle]; void *
0x180050582  mov     rcx, [rsp+540h+hObject]; void *
0x180050587  call    ?Unimpersonate@CONFIG_CACHE@@SAJPEAX0@Z; CONFIG_CACHE::Unimpersonate(void *,void *)
0x18005058c  test    eax, eax
0x18005058e  jns     short loc_180050595
0x180050590  test    ebx, ebx
0x180050592  cmovns  ebx, eax
0x180050595  mov     rcx, [rsp+540h+hObject]; hObject
0x18005059a  test    rcx, rcx
0x18005059d  jz      short loc_1800505AE
0x18005059f  call    cs:__imp_CloseHandle
0x1800505a5  mov     [rsp+540h+hObject], 0
0x1800505ae  mov     rcx, [rsp+540h+TokenHandle]; hObject
0x1800505b3  test    rcx, rcx
0x1800505b6  jz      short loc_1800505C7
0x1800505b8  call    cs:__imp_CloseHandle
0x1800505be  mov     [rsp+540h+TokenHandle], 0
0x1800505c7  test    r14, r14
0x1800505ca  jz      short loc_1800505D4
0x1800505cc  mov     rcx, r14; this
0x1800505cf  call    ?DereferenceConfigFile@CONFIG_FILE@@QEAAXXZ; CONFIG_FILE::DereferenceConfigFile(void)
0x1800505d4  lea     rcx, [rbp+440h+var_410]; this
0x1800505d8  call    ?Destroy@PATH@@QEAAXXZ; PATH::Destroy(void)
0x1800505dd  lea     rcx, [rbp+440h+var_490]; this
0x1800505e1  call    ??1PARSE_ERROR_INFO@@UEAA@XZ; PARSE_ERROR_INFO::~PARSE_ERROR_INFO(void)
0x1800505e6  lea     rcx, [rbp+440h+var_450]
0x1800505ea  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800505f0  mov     eax, ebx
0x1800505f2  mov     rcx, [rbp+440h+var_50]
0x1800505f9  xor     rcx, rsp; StackCookie
0x1800505fc  call    __security_check_cookie
0x180050601  add     rsp, 508h
0x180050608  pop     r15
0x18005060a  pop     r14
0x18005060c  pop     r13
0x18005060e  pop     r12
0x180050610  pop     rdi
0x180050611  pop     rsi
0x180050612  pop     rbx
0x180050613  pop     rbp
0x180050614  retn
```
