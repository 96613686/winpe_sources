# PATHMAP_ENTRY::Initialize(CONFIG_CACHE *,PARSE_ERROR_INFO *)

- ea: `0x18004461c`
- end: `0x180044cb6`
- name: `?Initialize@PATHMAP_ENTRY@@AEAAJPEAVCONFIG_CACHE@@PEAVPARSE_ERROR_INFO@@@Z`
- size: `1690`
- prototype: `int(PATHMAP_ENTRY *__hidden this, struct CONFIG_CACHE *, struct PARSE_ERROR_INFO *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800444b0`

## callees

- `0x1800100d0`
- `0x180010468`
- `0x180014b34`
- `0x180016aa0`
- `0x180017850`
- `0x18001be64`
- `0x18001e610`
- `0x1800266e4`
- `0x180044228`
- `0x180044414`
- `0x18004461c`
- `0x180044df0`
- `0x180044ea0`
- `0x18004ebb4`
- `0x180050a34`
- `0x180059230`
- `0x18005989c`
- `0x180059bea`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `msvcrt!wcspbrk` at `0x1800449a3`
- `msvcrt!wcspbrk` at `0x1800449a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044b79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044b79`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180044b6f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180044b6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044b25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044b25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180044b37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180044b4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180044b37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180044b4b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180044c7a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180044c84`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180044c7a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180044c84`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180044945`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800449e5`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180044afd`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180044945`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800449e5`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180044afd`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800446a2`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800446c3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800446a2`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800446c3`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180044937`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180044952`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180044937`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180044952`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800449d1`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800449d1`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180044973`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180044ac9`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180044973`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180044ac9`

## string_xrefs

- `0x180044742`: `configurationRedirection`
- `0x180044abe`: `\config\applicationHost.config`
- `0x180044bfa`: `redirection.config`
- `0x180044968`: `\applicationHost.config`
- `0x18004495a`: `applicationHost.config`
- `0x180044bac`: `PATHMAP_ENTRY::Initialize`

## pseudocode

```c
__int64 __fastcall PATHMAP_ENTRY::Initialize(PATHMAP_ENTRY *this, struct CONFIG_CACHE *a2, struct PARSE_ERROR_INFO *a3)
{
  HANDLE *v6; // r14
  int ConfigElement; // esi
  const unsigned __int16 *v8; // rbx
  int ConfigFileInternal; // eax
  CONFIG_FILE *v10; // r12
  const unsigned __int16 *ParseErrorFileName; // rax
  char *v12; // rbx
  __int64 v13; // r15
  int v14; // edx
  int v15; // ecx
  unsigned __int16 *v16; // rbx
  unsigned int CCH; // eax
  const unsigned __int16 *v18; // rdx
  wchar_t *v19; // rax
  wchar_t *v20; // rbx
  unsigned __int16 *v21; // rbx
  unsigned __int16 *v22; // rax
  const unsigned __int16 *v23; // rax
  const unsigned __int16 *Str; // rax
  __int64 *v25; // r15
  void *v26; // rcx
  HANDLE CurrentProcess; // rdi
  void *ImpersonationToken; // rbx
  HANDLE v29; // rax
  signed int LastError; // eax
  __int64 v31; // rbx
  unsigned int v32; // eax
  int v33; // edx
  int v34; // ecx
  __int64 v35; // r9
  wchar_t *String; // [rsp+40h] [rbp-C0h] BYREF
  struct INativePropertyException *v38; // [rsp+48h] [rbp-B8h] BYREF
  int v39; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v40; // [rsp+54h] [rbp-ACh] BYREF
  int v41; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpSrc; // [rsp+60h] [rbp-A0h] BYREF
  TOKEN_CACHE_ENTRY *v43; // [rsp+68h] [rbp-98h] BYREF
  CONFIG_ELEMENT *v44; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v45; // [rsp+78h] [rbp-88h] BYREF
  CONFIG_FILE *v46; // [rsp+80h] [rbp-80h] BYREF
  __int64 v47; // [rsp+88h] [rbp-78h] BYREF
  __int128 v48; // [rsp+90h] [rbp-70h] BYREF
  CONFIG_CACHE *v49; // [rsp+A0h] [rbp-60h]
  _BYTE v50[56]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v51[64]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v52[32]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v53[264]; // [rsp+160h] [rbp+60h] BYREF

  v49 = a2;
  v40 = 0;
  v46 = 0;
  v44 = 0;
  v39 = 0;
  lpSrc = 0;
  String = 0;
  v45 = 0;
  v41 = 0;
  v47 = 0;
  memset_0(v53, 0, 0x208u);
  STRU::STRU((STRU *)v50, v53, 0x104u);
  memset_0(v52, 0, sizeof(v52));
  STRU::STRU((STRU *)v51, v52, 0x20u);
  v43 = 0;
  v38 = 0;
  v6 = 0;
  v48 = 0;
  if ( !a2 )
  {
    ConfigElement = -2147024809;
    goto LABEL_74;
  }
  if ( *((_DWORD *)this + 9) != 3 )
  {
    ConfigElement = -2147024883;
    goto LABEL_74;
  }
  if ( (*((_BYTE *)this + 32) & 8) != 0 )
  {
    ConfigElement = 0;
    goto LABEL_74;
  }
  v8 = L"MACHINE/REDIRECTION";
  ConfigFileInternal = CONFIG_CACHE::GetConfigFileInternal(a2, L"MACHINE/REDIRECTION", &v46);
  v10 = v46;
  ConfigElement = ConfigFileInternal;
  if ( ConfigFileInternal < 0 )
    goto LABEL_64;
  if ( !v46 )
  {
    ConfigElement = -2147024894;
LABEL_64:
    if ( a3 )
    {
      if ( **((char **)a2 + 2) >= 0 )
        v8 = L"redirection.config";
      SMALL_STRU::Copy((struct PARSE_ERROR_INFO *)((char *)a3 + 32), v8);
      v35 = 3221228255LL;
      if ( ConfigElement != -2147024891 )
        v35 = 3221228229LL;
      PARSE_ERROR_INFO::SetErrorInfo(a3, (unsigned int)ConfigElement, 4, v35, &v48, 0, 0, 0, (_DWORD)String, v38);
    }
    goto LABEL_70;
  }
  ConfigElement = CONFIG_FILE::GetConfigElement(v46, &szDomain, L"configurationRedirection", &v44, a3);
  if ( ConfigElement < 0 )
  {
    if ( a3 )
    {
      ParseErrorFileName = CONFIG_FILE::QueryParseErrorFileName(v10);
      SMALL_STRU::Copy((struct PARSE_ERROR_INFO *)((char *)a3 + 32), ParseErrorFileName);
    }
    goto LABEL_61;
  }
  v12 = (char *)v44 + 16;
  ConfigElement = (*(__int64 (__fastcall **)(char *, const wchar_t *, int *, _QWORD, _QWORD))(*((_QWORD *)v44 + 2) + 72LL))(
                    (char *)v44 + 16,
                    L"enabled",
                    &v39,
                    0,
                    0);
  if ( ConfigElement < 0 )
    goto LABEL_61;
  ConfigElement = (*(__int64 (__fastcall **)(char *, const wchar_t *, int *, struct INativePropertyException **, _QWORD))(*(_QWORD *)v12 + 72LL))(
                    v12,
                    L"enableUncPolling",
                    &v41,
                    &v38,
                    0);
  if ( ConfigElement < 0 )
    goto LABEL_61;
  ConfigElement = (*(__int64 (__fastcall **)(char *, const wchar_t *, __int64 *, struct INativePropertyException **, _QWORD))(*(_QWORD *)v12 + 80LL))(
                    v12,
                    L"pollingPeriod",
                    &v47,
                    &v38,
                    0);
  if ( ConfigElement < 0 )
    goto LABEL_61;
  v13 = v47 / 10000;
  if ( (unsigned __int64)(v47 / 10000) > 0xFFFFFFFF )
  {
    ConfigElement = -2147024362;
    goto LABEL_59;
  }
  if ( !v39 )
  {
    ConfigElement = PATHMAP_TABLE::FindIISDirectory((struct STRU *)v50);
    if ( ConfigElement < 0 )
      goto LABEL_61;
    ConfigElement = STRU::Append((STRU *)v50, L"\\config\\applicationHost.config");
    if ( ConfigElement < 0 )
      goto LABEL_61;
LABEL_47:
    ConfigElement = CONFIG_CACHE::UpdateTimerDrivenPollPeriod(v49, v41 != 0 ? v13 : 0);
    if ( ConfigElement >= 0 )
    {
      Str = STRU::QueryStr((STRU *)v50);
      ConfigElement = SMALL_STRU::Copy((PATHMAP_ENTRY *)((char *)this + 24), Str);
      if ( ConfigElement >= 0 )
      {
        v25 = (__int64 *)((char *)this + 40);
        v26 = (void *)*((_QWORD *)this + 5);
        if ( v26 )
        {
          CloseHandle(v26);
          *v25 = 0;
        }
        if ( v6 )
        {
          CurrentProcess = GetCurrentProcess();
          ImpersonationToken = TOKEN_CACHE_ENTRY::QueryImpersonationToken(v6);
          v29 = GetCurrentProcess();
          if ( !DuplicateHandle(v29, ImpersonationToken, CurrentProcess, (LPHANDLE)this + 5, 0, 0, 2u) )
          {
            LastError = GetLastError();
            ConfigElement = LastError;
            if ( LastError > 0 )
              ConfigElement = (unsigned __int16)LastError | 0x80070000;
            goto LABEL_59;
          }
          if ( (Microsoft_Windows_IIS_ConfigurationEnableBits & 1) != 0 )
          {
            v31 = *v25;
            v32 = (unsigned int)TOKEN_CACHE_ENTRY::QueryImpersonationToken(v6);
            McTemplateU0zpp_EtwEventWriteTransfer(v34, v33, (unsigned int)L"PATHMAP_ENTRY::Initialize", v32, v31);
          }
        }
        *((_DWORD *)this + 8) |= 8u;
      }
    }
LABEL_59:
    if ( v6 )
      TOKEN_CACHE_ENTRY::DereferenceCacheEntry((TOKEN_CACHE_ENTRY *)v6);
    goto LABEL_61;
  }
  ConfigElement = (*(__int64 (__fastcall **)(char *, const unsigned __int16 *, LPCWSTR *, _QWORD, _QWORD))(*(_QWORD *)v12 + 64LL))(
                    v12,
                    L"path",
                    &lpSrc,
                    0,
                    0);
  if ( ConfigElement < 0 )
    goto LABEL_61;
  ConfigElement = (*(__int64 (__fastcall **)(char *, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v12 + 64LL))(
                    v12,
                    L"userName",
                    &String,
                    0,
                    0);
  if ( ConfigElement < 0 )
    goto LABEL_61;
  ConfigElement = (*(__int64 (__fastcall **)(char *, const wchar_t *, unsigned __int16 **, struct INativePropertyException **, _QWORD))(*(_QWORD *)v12 + 64LL))(
                    v12,
                    L"password",
                    &v45,
                    &v38,
                    0);
  if ( ConfigElement < 0 )
    goto LABEL_61;
  if ( (Microsoft_Windows_IIS_ConfigurationEnableBits & 0x10) != 0 )
    McTemplateU0zzz_EtwEventWriteTransfer(v15, v14, (_DWORD)lpSrc, (_DWORD)String, (__int64)v45);
  if ( v38 )
  {
    if ( a3 )
      PARSE_ERROR_INFO::CopyPropertyException(a3, v38);
    ConfigElement = -2147024883;
    goto LABEL_61;
  }
  ConfigElement = ExpandEnvironmentVariables(lpSrc, (struct STRU *)v50);
  if ( ConfigElement < 0 )
    goto LABEL_61;
  if ( !STRU::QueryCCH((STRU *)v50)
    || (v16 = STRU::QueryStr((STRU *)v50),
        CCH = STRU::QueryCCH((STRU *)v50),
        v18 = L"applicationHost.config",
        v16[CCH - 1] != 92) )
  {
    v18 = L"\\applicationHost.config";
  }
  ConfigElement = STRU::Append((STRU *)v50, v18);
  if ( ConfigElement < 0 )
    goto LABEL_61;
  if ( !String || !*String )
    goto LABEL_47;
  v19 = wcspbrk(String, L"/\\");
  v20 = v19;
  if ( !v19 )
  {
    v21 = String;
    v22 = (unsigned __int16 *)&szDomain;
LABEL_37:
    ConfigElement = TOKEN_CACHE::GetCachedToken((TOKEN_CACHE *)&v43, v21, v22, v45, 8u, &v43, &v40);
    if ( ConfigElement < 0 )
    {
LABEL_41:
      if ( a3 )
      {
        v23 = CONFIG_FILE::QueryParseErrorFileName(v10);
        SMALL_STRU::Copy((struct PARSE_ERROR_INFO *)((char *)a3 + 32), v23);
        *(_QWORD *)&v48 = lpSrc;
        *((_QWORD *)&v48 + 1) = String;
        PARSE_ERROR_INFO::SetErrorInfo(
          a3,
          (unsigned int)ConfigElement,
          3,
          3221228273LL,
          &v48,
          *((_DWORD *)v44 + 16),
          0,
          *((_QWORD *)v44 + 7),
          (_DWORD)String,
          v38);
      }
      v6 = (HANDLE *)v43;
      goto LABEL_59;
    }
    ConfigElement = v40;
    if ( v40 )
    {
      if ( (int)v40 > 0 )
        ConfigElement = (unsigned __int16)v40 | 0x80070000;
      goto LABEL_41;
    }
    v6 = (HANDLE *)v43;
    goto LABEL_47;
  }
  ConfigElement = STRU::Copy((STRU *)v51, String, v19 - String);
  if ( ConfigElement >= 0 )
  {
    v22 = STRU::QueryStr((STRU *)v51);
    v21 = v20 + 1;
    goto LABEL_37;
  }
LABEL_61:
  if ( v44 )
    CONFIG_ELEMENT::DereferenceConfigElement(v44);
LABEL_70:
  if ( v10 )
    CONFIG_FILE::DereferenceConfigFile(v10);
  if ( v38 )
  {
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v38 + 16LL))(v38);
    v38 = 0;
  }
LABEL_74:
  STRU::~STRU((STRU *)v51);
  STRU::~STRU((STRU *)v50);
  return (unsigned int)ConfigElement;
}

```

## disassembly

```asm
0x18004461c  mov     [rsp-8+arg_18], rbx
0x180044621  push    rbp
0x180044622  push    rsi
0x180044623  push    rdi
0x180044624  push    r12
0x180044626  push    r13
0x180044628  push    r14
0x18004462a  push    r15
0x18004462c  lea     rbp, [rsp-280h]
0x180044634  sub     rsp, 380h
0x18004463b  mov     rax, cs:__security_cookie
0x180044642  xor     rax, rsp
0x180044645  mov     [rbp+2B0h+var_40], rax
0x18004464c  xor     ebx, ebx
0x18004464e  mov     [rbp+2B0h+var_310], rdx
0x180044652  mov     rdi, r8
0x180044655  mov     [rsp+3B0h+var_35C], ebx
0x180044659  mov     r15, rdx
0x18004465c  mov     [rbp+2B0h+var_330], rbx
0x180044660  mov     r13, rcx
0x180044663  mov     [rsp+3B0h+var_340], rbx
0x180044668  xor     edx, edx; Val
0x18004466a  mov     [rsp+3B0h+var_360], ebx
0x18004466e  mov     r8d, 208h; Size
0x180044674  mov     [rsp+3B0h+lpSrc], rbx
0x180044679  lea     rcx, [rbp+2B0h+var_250]; void *
0x18004467d  mov     [rsp+3B0h+String], rbx
0x180044682  mov     [rsp+3B0h+var_338], rbx
0x180044687  mov     [rsp+3B0h+var_358], ebx
0x18004468b  mov     [rbp+2B0h+var_328], rbx
0x18004468f  call    memset_0
0x180044694  mov     r8d, 104h
0x18004469a  lea     rdx, [rbp+2B0h+var_250]
0x18004469e  lea     rcx, [rbp+2B0h+var_308]
0x1800446a2  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800446a8  xor     edx, edx; Val
0x1800446aa  lea     r8d, [rbx+40h]; Size
0x1800446ae  lea     rcx, [rbp+2B0h+var_290]; void *
0x1800446b2  call    memset_0
0x1800446b7  lea     r8d, [rbx+20h]
0x1800446bb  lea     rdx, [rbp+2B0h+var_290]
0x1800446bf  lea     rcx, [rbp+2B0h+var_2D0]
0x1800446c3  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800446c9  mov     [rsp+3B0h+var_348], rbx
0x1800446ce  xorps   xmm0, xmm0
0x1800446d1  mov     [rsp+3B0h+var_368], rbx
0x1800446d6  mov     r14d, ebx
0x1800446d9  movups  [rbp+2B0h+var_320], xmm0
0x1800446dd  test    r15, r15
0x1800446e0  jnz     short loc_1800446EC
0x1800446e2  mov     esi, 80070057h
0x1800446e7  jmp     loc_180044C76
0x1800446ec  cmp     dword ptr [r13+24h], 3
0x1800446f1  jz      short loc_1800446FD
0x1800446f3  mov     esi, 8007000Dh
0x1800446f8  jmp     loc_180044C76
0x1800446fd  test    byte ptr [r13+20h], 8
0x180044702  jz      short loc_18004470B
0x180044704  mov     esi, ebx
0x180044706  jmp     loc_180044C76
0x18004470b  lea     rbx, Str; "MACHINE/REDIRECTION"
0x180044712  mov     rcx, r15; this
0x180044715  mov     rdx, rbx; unsigned __int16 *
0x180044718  lea     r8, [rbp+2B0h+var_330]; struct CONFIG_FILE **
0x18004471c  call    ?GetConfigFileInternal@CONFIG_CACHE@@QEAAJPEBGPEAPEAVCONFIG_FILE@@@Z; CONFIG_CACHE::GetConfigFileInternal(ushort const *,CONFIG_FILE * *)
0x180044721  mov     r12, [rbp+2B0h+var_330]
0x180044725  mov     esi, eax
0x180044727  test    eax, eax
0x180044729  js      loc_180044BEA
0x18004472f  test    r12, r12
0x180044732  jz      loc_180044BE5
0x180044738  lea     r9, [rsp+3B0h+var_340]; struct CONFIG_ELEMENT **
0x18004473d  mov     qword ptr [rsp+3B0h+dwDesiredAccess], rdi; struct PARSE_ERROR_INFO *
0x180044742  lea     r8, aConfigurationr; "configurationRedirection"
0x180044749  mov     rcx, r12; this
0x18004474c  lea     rdx, szDomain; unsigned __int16 *
0x180044753  call    ?GetConfigElement@CONFIG_FILE@@QEAAJPEBG0PEAPEAVCONFIG_ELEMENT@@PEAVPARSE_ERROR_INFO@@@Z; CONFIG_FILE::GetConfigElement(ushort const *,ushort const *,CONFIG_ELEMENT * *,PARSE_ERROR_INFO *)
0x180044758  mov     esi, eax
0x18004475a  test    eax, eax
0x18004475c  jns     short loc_180044780
0x18004475e  test    rdi, rdi
0x180044761  jz      loc_180044BD1
0x180044767  mov     rcx, r12; this
0x18004476a  call    ?QueryParseErrorFileName@CONFIG_FILE@@QEBAPEBGXZ; CONFIG_FILE::QueryParseErrorFileName(void)
0x18004476f  lea     rcx, [rdi+20h]; this
0x180044773  mov     rdx, rax; unsigned __int16 *
0x180044776  call    ?Copy@SMALL_STRU@@QEAAJPEBG@Z; SMALL_STRU::Copy(ushort const *)
0x18004477b  jmp     loc_180044BD1
0x180044780  mov     rbx, [rsp+3B0h+var_340]
0x180044785  lea     r8, [rsp+3B0h+var_360]
0x18004478a  add     rbx, 10h
0x18004478e  mov     qword ptr [rsp+3B0h+dwDesiredAccess], r14
0x180044793  xor     r9d, r9d
0x180044796  lea     rdx, aEnabled; "enabled"
0x18004479d  mov     rcx, rbx
0x1800447a0  mov     rax, [rbx]
0x1800447a3  mov     rax, [rax+48h]
0x1800447a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800447ac  mov     esi, eax
0x1800447ae  test    eax, eax
0x1800447b0  js      loc_180044BD1
0x1800447b6  mov     rax, [rbx]
0x1800447b9  lea     r9, [rsp+3B0h+var_368]
0x1800447be  lea     r8, [rsp+3B0h+var_358]
0x1800447c3  mov     qword ptr [rsp+3B0h+dwDesiredAccess], r14
0x1800447c8  lea     rdx, aEnableuncpolli; "enableUncPolling"
0x1800447cf  mov     rcx, rbx
0x1800447d2  mov     rax, [rax+48h]
0x1800447d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800447db  mov     esi, eax
0x1800447dd  test    eax, eax
0x1800447df  js      loc_180044BD1
0x1800447e5  mov     rax, [rbx]
0x1800447e8  lea     r9, [rsp+3B0h+var_368]
0x1800447ed  lea     r8, [rbp+2B0h+var_328]
0x1800447f1  mov     qword ptr [rsp+3B0h+dwDesiredAccess], r14
0x1800447f6  lea     rdx, aPollingperiod; "pollingPeriod"
0x1800447fd  mov     rcx, rbx
0x180044800  mov     rax, [rax+50h]
0x180044804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044809  mov     esi, eax
0x18004480b  test    eax, eax
0x18004480d  js      loc_180044BD1
0x180044813  mov     rax, 346DC5D63886594Bh
0x18004481d  imul    [rbp+2B0h+var_328]
0x180044821  mov     r15, rdx
0x180044824  sar     r15, 0Bh
0x180044828  mov     rax, r15
0x18004482b  shr     rax, 3Fh
0x18004482f  add     r15, rax
0x180044832  mov     eax, 0FFFFFFFFh
0x180044837  cmp     r15, rax
0x18004483a  ja      loc_180044BBF
0x180044840  xor     edx, edx
0x180044842  cmp     [rsp+3B0h+var_360], edx
0x180044846  jz      loc_180044AAB
0x18004484c  mov     rax, [rbx]
0x18004484f  lea     r8, [rsp+3B0h+lpSrc]
0x180044854  mov     qword ptr [rsp+3B0h+dwDesiredAccess], rdx
0x180044859  xor     r9d, r9d
0x18004485c  lea     rdx, aPath; "path"
0x180044863  mov     rcx, rbx
0x180044866  mov     rax, [rax+40h]
0x18004486a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004486f  mov     esi, eax
0x180044871  test    eax, eax
0x180044873  js      loc_180044BD1
0x180044879  mov     rax, [rbx]
0x18004487c  lea     r8, [rsp+3B0h+String]
0x180044881  xor     r9d, r9d
0x180044884  mov     qword ptr [rsp+3B0h+dwDesiredAccess], r14
0x180044889  lea     rdx, aUsername; "userName"
0x180044890  mov     rcx, rbx
0x180044893  mov     rax, [rax+40h]
0x180044897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004489c  mov     esi, eax
0x18004489e  test    eax, eax
0x1800448a0  js      loc_180044BD1
0x1800448a6  mov     rax, [rbx]
0x1800448a9  lea     r9, [rsp+3B0h+var_368]
0x1800448ae  lea     r8, [rsp+3B0h+var_338]
0x1800448b3  mov     qword ptr [rsp+3B0h+dwDesiredAccess], r14
0x1800448b8  lea     rdx, aPassword; "password"
0x1800448bf  mov     rcx, rbx
0x1800448c2  mov     rax, [rax+40h]
0x1800448c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800448cb  mov     esi, eax
0x1800448cd  test    eax, eax
0x1800448cf  js      loc_180044BD1
0x1800448d5  test    cs:Microsoft_Windows_IIS_ConfigurationEnableBits, 10h
0x1800448dc  jz      short loc_1800448F7
0x1800448de  mov     rax, [rsp+3B0h+var_338]
0x1800448e3  mov     r9, [rsp+3B0h+String]
0x1800448e8  mov     r8, [rsp+3B0h+lpSrc]
0x1800448ed  mov     qword ptr [rsp+3B0h+dwDesiredAccess], rax
0x1800448f2  call    McTemplateU0zzz_EtwEventWriteTransfer
0x1800448f7  mov     rcx, [rsp+3B0h+var_368]
0x1800448fc  test    rcx, rcx
0x1800448ff  jz      short loc_18004491B
0x180044901  test    rdi, rdi
0x180044904  jz      short loc_180044911
0x180044906  mov     rdx, rcx; struct INativePropertyException *
0x180044909  mov     rcx, rdi; this
0x18004490c  call    ?CopyPropertyException@PARSE_ERROR_INFO@@QEAAJPEAVINativePropertyException@@@Z; PARSE_ERROR_INFO::CopyPropertyException(INativePropertyException *)
0x180044911  mov     esi, 8007000Dh
0x180044916  jmp     loc_180044BD1
0x18004491b  mov     rcx, [rsp+3B0h+lpSrc]; lpSrc
0x180044920  lea     rdx, [rbp+2B0h+var_308]; struct STRU *
0x180044924  call    ?ExpandEnvironmentVariables@@YAJPEBGPEAVSTRU@@@Z; ExpandEnvironmentVariables(ushort const *,STRU *)
0x180044929  mov     esi, eax
0x18004492b  test    eax, eax
0x18004492d  js      loc_180044BD1
0x180044933  lea     rcx, [rbp+2B0h+var_308]
0x180044937  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18004493d  test    eax, eax
0x18004493f  jz      short loc_180044968
0x180044941  lea     rcx, [rbp+2B0h+var_308]
0x180044945  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18004494b  lea     rcx, [rbp+2B0h+var_308]
0x18004494f  mov     rbx, rax
0x180044952  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180044958  dec     eax
0x18004495a  lea     rdx, aApplicationhos_0; "applicationHost.config"
0x180044961  cmp     word ptr [rbx+rax*2], 5Ch ; '\'
0x180044966  jz      short loc_18004496F
0x180044968  lea     rdx, aApplicationhos; "\\applicationHost.config"
0x18004496f  lea     rcx, [rbp+2B0h+var_308]
0x180044973  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180044979  mov     esi, eax
0x18004497b  xor     eax, eax
0x18004497d  test    esi, esi
0x18004497f  js      loc_180044BD1
0x180044985  mov     rcx, [rsp+3B0h+String]; String
0x18004498a  test    rcx, rcx
0x18004498d  jz      loc_180044AD9
0x180044993  cmp     [rcx], ax
0x180044996  jz      loc_180044AD9
0x18004499c  lea     rdx, Control; "/\\"
0x1800449a3  call    cs:__imp_wcspbrk
0x1800449a9  mov     rbx, rax
0x1800449ac  test    rax, rax
0x1800449af  jnz     short loc_1800449BF
0x1800449b1  mov     rbx, [rsp+3B0h+String]
0x1800449b6  lea     rax, szDomain
0x1800449bd  jmp     short loc_1800449EF
0x1800449bf  mov     rdx, [rsp+3B0h+String]
0x1800449c4  lea     rcx, [rbp+2B0h+var_2D0]
0x1800449c8  mov     r8, rbx
0x1800449cb  sub     r8, rdx
0x1800449ce  sar     r8, 1
0x1800449d1  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x1800449d7  mov     esi, eax
0x1800449d9  test    eax, eax
0x1800449db  js      loc_180044BD1
0x1800449e1  lea     rcx, [rbp+2B0h+var_2D0]
0x1800449e5  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800449eb  add     rbx, 2
0x1800449ef  mov     r9, [rsp+3B0h+var_338]; unsigned __int16 *
0x1800449f4  lea     rcx, [rsp+3B0h+var_35C]
0x1800449f9  mov     qword ptr [rsp+3B0h+dwOptions], rcx; unsigned int *
0x1800449fe  mov     r8, rax; unsigned __int16 *
0x180044a01  lea     rcx, [rsp+3B0h+var_348]; this
0x180044a06  mov     rdx, rbx; unsigned __int16 *
0x180044a09  mov     qword ptr [rsp+3B0h+bInheritHandle], rcx; struct TOKEN_CACHE_ENTRY **
0x180044a0e  mov     [rsp+3B0h+dwDesiredAccess], 8; unsigned int
0x180044a16  call    ?GetCachedToken@TOKEN_CACHE@@QEAAJPEAG00KPEAPEAVTOKEN_CACHE_ENTRY@@PEAK@Z; TOKEN_CACHE::GetCachedToken(ushort *,ushort *,ushort *,ulong,TOKEN_CACHE_ENTRY * *,ulong *)
0x180044a1b  xor     ebx, ebx
0x180044a1d  mov     esi, eax
0x180044a1f  test    eax, eax
0x180044a21  js      short loc_180044A36
0x180044a23  mov     esi, [rsp+3B0h+var_35C]
0x180044a27  test    esi, esi
0x180044a29  jz      short loc_180044AA4
0x180044a2b  jle     short loc_180044A36
0x180044a2d  movzx   esi, si
0x180044a30  or      esi, 80070000h
0x180044a36  test    rdi, rdi
0x180044a39  jz      short loc_180044A9A
0x180044a3b  mov     rcx, r12; this
0x180044a3e  call    ?QueryParseErrorFileName@CONFIG_FILE@@QEBAPEBGXZ; CONFIG_FILE::QueryParseErrorFileName(void)
0x180044a43  lea     rcx, [rdi+20h]; this
0x180044a47  mov     rdx, rax; unsigned __int16 *
0x180044a4a  call    ?Copy@SMALL_STRU@@QEAAJPEBG@Z; SMALL_STRU::Copy(ushort const *)
0x180044a4f  mov     rax, [rsp+3B0h+lpSrc]
0x180044a54  mov     r9d, 0C0000AF1h
0x180044a5a  mov     rcx, [rsp+3B0h+var_340]
0x180044a5f  mov     r8d, 3
0x180044a65  mov     qword ptr [rbp+2B0h+var_320], rax
0x180044a69  mov     edx, esi
0x180044a6b  mov     rax, [rsp+3B0h+String]
0x180044a70  mov     qword ptr [rbp+2B0h+var_320+8], rax
0x180044a74  mov     rax, [rcx+38h]
0x180044a78  mov     [rsp+3B0h+var_378], rax
0x180044a7d  mov     eax, [rcx+40h]
0x180044a80  mov     rcx, rdi
0x180044a83  mov     qword ptr [rsp+3B0h+dwOptions], rbx
0x180044a88  mov     [rsp+3B0h+bInheritHandle], eax
0x180044a8c  lea     rax, [rbp+2B0h+var_320]
0x180044a90  mov     qword ptr [rsp+3B0h+dwDesiredAccess], rax
0x180044a95  call    ?SetErrorInfo@PARSE_ERROR_INFO@@QEAAJJW4PARSE_ERROR_TYPE@@KQEAPEBDKPEAVIConfigDom@@PEAVIConfigDomNode@@@Z; PARSE_ERROR_INFO::SetErrorInfo(long,PARSE_ERROR_TYPE,ulong,char const * * const,ulong,IConfigDom *,IConfigDomNode *)
0x180044a9a  mov     r14, [rsp+3B0h+var_348]
0x180044a9f  jmp     loc_180044BC4
0x180044aa4  mov     r14, [rsp+3B0h+var_348]
0x180044aa9  jmp     short loc_180044ADB
0x180044aab  lea     rcx, [rbp+2B0h+var_308]; struct STRU *
0x180044aaf  call    ?FindIISDirectory@PATHMAP_TABLE@@SAJPEAVSTRU@@@Z; PATHMAP_TABLE::FindIISDirectory(STRU *)
0x180044ab4  mov     esi, eax
0x180044ab6  test    eax, eax
0x180044ab8  js      loc_180044BD1
0x180044abe  lea     rdx, aConfigApplicat; "\\config\\applicationHost.config"
0x180044ac5  lea     rcx, [rbp+2B0h+var_308]
0x180044ac9  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180044acf  mov     esi, eax
0x180044ad1  test    eax, eax
0x180044ad3  js      loc_180044BD1
0x180044ad9  xor     ebx, ebx
0x180044adb  mov     eax, [rsp+3B0h+var_358]
0x180044adf  mov     rcx, [rbp+2B0h+var_310]; this
0x180044ae3  neg     eax
0x180044ae5  sbb     edx, edx
  ... truncated ...
```
