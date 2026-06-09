# FTP_COMMAND::HandleUSER(int *)

- ea: `0x18003d220`
- end: `0x18003d860`
- name: `?HandleUSER@FTP_COMMAND@@QEAAXPEAH@Z`
- size: `1600`
- prototype: `void __fastcall(FTP_COMMAND *__hidden this, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003732c`

## callees

- `0x180009090`
- `0x18002b84c`
- `0x180036028`
- `0x180036bf8`
- `0x180038ac0`
- `0x18003d220`
- `0x18003e564`
- `0x18004700f`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18003d77b`
- `msvcrt!_wcsnicmp` at `0x18003d7a8`
- `msvcrt!_wcsnicmp` at `0x18003d77b`
- `msvcrt!_wcsnicmp` at `0x18003d7a8`
- `msvcrt!wcschr` at `0x18003d2f9`
- `msvcrt!wcschr` at `0x18003d349`
- `msvcrt!wcschr` at `0x18003d37e`
- `msvcrt!wcschr` at `0x18003d39a`
- `msvcrt!wcschr` at `0x18003d2f9`
- `msvcrt!wcschr` at `0x18003d349`
- `msvcrt!wcschr` at `0x18003d37e`
- `msvcrt!wcschr` at `0x18003d39a`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18003d29a`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18003d29a`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18003d47b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18003d47b`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18003d459`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18003d459`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18003d2e3`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18003d2e3`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003d524`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003d5bd`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003d674`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003d702`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003d524`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003d5bd`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003d674`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003d702`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18003d3e7`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18003d7f6`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18003d3e7`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18003d7f6`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18003d288`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18003d2c1`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18003d288`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18003d2c1`
- `iisutil!WriteRefTraceLog` at `0x18003d43c`
- `iisutil!WriteRefTraceLog` at `0x18003d43c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18003d470`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18003d487`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18003d470`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18003d487`

## string_xrefs

- `0x18003d516`: `Hostname didn't match any configured ftp site.`
- `0x18003d840`: `Anonymous access allowed, send identity (e-mail name) as password.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall FTP_COMMAND::HandleUSER(FTP_COMMAND *this, int *a2)
{
  FTP_COMMAND *v2; // rbx
  __int64 v3; // r13
  wchar_t *v4; // rax
  wchar_t *v5; // rsi
  wchar_t *v6; // rdi
  __int64 v7; // r14
  __int64 v8; // rcx
  wchar_t *v9; // rax
  wchar_t *v10; // rax
  wchar_t *v11; // r15
  int v12; // eax
  volatile signed __int32 *v13; // rsi
  unsigned __int32 v14; // ebx
  int v15; // eax
  FTP_SESSION *v16; // rcx
  struct FTP_SITE_CONFIG *ReferencedSiteConfig; // rax
  const unsigned __int16 *v18; // rdx
  int v19; // edx
  signed int v20; // eax
  signed int v21; // ecx
  const unsigned __int16 *v22; // rdx
  int v23; // r12d
  __int64 v24; // r15
  int v25; // [rsp+20h] [rbp-E0h] BYREF
  FTP_COMMAND *v26; // [rsp+28h] [rbp-D8h]
  int *v27; // [rsp+30h] [rbp-D0h]
  _BYTE v28[32]; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t *Str; // [rsp+58h] [rbp-A8h]
  _BYTE v30[32]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v31; // [rsp+90h] [rbp-70h]
  _BYTE v32[56]; // [rsp+A8h] [rbp-58h] BYREF
  char v33[64]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v34[64]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v35[64]; // [rsp+1A0h] [rbp+A0h] BYREF

  v27 = a2;
  v2 = this;
  v26 = this;
  v25 = 0;
  memset_0(v34, 0, sizeof(v34));
  STRU::STRU((STRU *)v30, v34, 0x40u);
  STRA::STRA((STRA *)v32, v33, 0x40u);
  memset_0(v35, 0, sizeof(v35));
  STRU::STRU((STRU *)v28, v35, 0x40u);
  v3 = *((_QWORD *)v2 + 132);
  FTP_SESSION::ResetFtpUser((FTP_SESSION *)v3);
  if ( (int)STRU::CopyA((STRU *)v28, *((const char **)v2 + 20)) < 0 )
    goto LABEL_29;
  v4 = wcschr(Str, 0x7Cu);
  v5 = Str;
  if ( v4 )
  {
    v6 = v4 + 1;
    v7 = -1;
    do
      ++v7;
    while ( v6[v7] );
    if ( Str )
    {
      v8 = v4 - Str;
      goto LABEL_19;
    }
  }
  else
  {
    v6 = 0;
    LODWORD(v7) = 0;
  }
  if ( !FTP_COMMAND::sm_fUseDomainNameAsHostName )
    goto LABEL_33;
  v9 = wcschr(Str, 0x5Cu);
  if ( v9 )
  {
    v5 = Str;
    v8 = v9 - Str;
    v6 = v9 + 1;
    v7 = -1;
    do
      ++v7;
    while ( v6[v7] );
  }
  else
  {
    v10 = wcschr(Str, 0x40u);
    if ( !v10 )
      goto LABEL_33;
    do
    {
      v11 = v10;
      v5 = v10 + 1;
      v10 = wcschr(v10 + 1, 0x40u);
    }
    while ( v10 );
    v2 = v26;
    v8 = -1;
    do
      ++v8;
    while ( v5[v8] );
    v6 = Str;
    LODWORD(v7) = v11 - Str;
  }
  if ( !v5 )
  {
LABEL_33:
    v16 = (FTP_SESSION *)*((_QWORD *)v2 + 132);
    if ( !*(_DWORD *)(*((_QWORD *)v16 + 12) + 4LL) )
    {
      if ( !*((_DWORD *)v2 + 292) )
        *((_DWORD *)v2 + 292) = -2147013895;
      goto LABEL_36;
    }
    if ( !v6 )
    {
      v6 = (wchar_t *)*((_QWORD *)v2 + 43);
      v7 = -1;
      do
        ++v7;
      while ( v6[v7] );
    }
    ReferencedSiteConfig = FTP_SESSION::GetReferencedSiteConfig(v16);
    v13 = (volatile signed __int32 *)ReferencedSiteConfig;
    if ( *((_DWORD *)ReferencedSiteConfig + 28) == 1 )
    {
      if ( *(_DWORD *)(v3 + 1100) != 2 )
      {
        if ( !*((_DWORD *)v2 + 292) )
          *((_DWORD *)v2 + 292) = -2147024891;
        if ( *((_DWORD *)v2 + 274) )
          goto LABEL_49;
        *((_DWORD *)v2 + 274) = 25;
        v18 = L"SSL policy requires SSL for control channel.";
LABEL_48:
        STRU::Copy((FTP_COMMAND *)((char *)v2 + 1112), v18);
        *((_QWORD *)v2 + 138) = *((_QWORD *)v2 + 143);
LABEL_49:
        FTP_COMMAND::WriteResponseAndLog(v2, "534", "Policy requires SSL.");
        goto LABEL_24;
      }
    }
    else if ( *((_DWORD *)ReferencedSiteConfig + 28) == 2 && *(_DWORD *)(v3 + 1100) != 2 )
    {
      if ( !*((_DWORD *)v2 + 292) )
        *((_DWORD *)v2 + 292) = -2147024891;
      if ( *((_DWORD *)v2 + 274) )
        goto LABEL_49;
      *((_DWORD *)v2 + 274) = 26;
      v18 = L"SSL policy requires SSL for credentials.";
      goto LABEL_48;
    }
    if ( *((_DWORD *)ReferencedSiteConfig + 30) && *(_DWORD *)(v3 + 1100) == 2 && *(_DWORD *)(v3 + 1160) < 0x80u )
    {
      if ( !*((_DWORD *)v2 + 292) )
        *((_DWORD *)v2 + 292) = -2147024891;
      if ( !*((_DWORD *)v2 + 274) )
      {
        *((_DWORD *)v2 + 274) = 55;
        STRU::Copy((FTP_COMMAND *)((char *)v2 + 1112), L"128 bit encryption is required for SSL connections.");
        *((_QWORD *)v2 + 138) = *((_QWORD *)v2 + 143);
      }
      FTP_COMMAND::WriteResponseAndLog(v2, "534", "Policy requires stronger SSL encryption level.");
      goto LABEL_24;
    }
    v19 = *((_DWORD *)ReferencedSiteConfig + 266);
    if ( v19 )
    {
      v20 = *(_DWORD *)(v3 + 1164);
      if ( v20 > 0 )
        v21 = (unsigned __int16)v20 | 0x80070000;
      else
        v21 = *(_DWORD *)(v3 + 1164);
      if ( v21 < 0 )
      {
        if ( v20 > 0 )
          v20 = (unsigned __int16)v20 | 0x80070000;
        if ( !*((_DWORD *)v2 + 292) )
          *((_DWORD *)v2 + 292) = v20;
        if ( *((_DWORD *)v2 + 274) )
          goto LABEL_76;
        *((_DWORD *)v2 + 274) = 48;
        v22 = L"User provided invalid client certificate.";
LABEL_75:
        STRU::Copy((FTP_COMMAND *)((char *)v2 + 1112), v22);
        *((_QWORD *)v2 + 138) = *((_QWORD *)v2 + 143);
LABEL_76:
        FTP_COMMAND::WriteResponseAndLog(v2, "534", "Policy requires valid SSL Client certificate.");
        goto LABEL_24;
      }
      if ( v19 == 2 && !*(_QWORD *)(v3 + 1168) )
      {
        if ( !*((_DWORD *)v2 + 292) )
          *((_DWORD *)v2 + 292) = -2147024891;
        if ( *((_DWORD *)v2 + 274) )
          goto LABEL_76;
        *((_DWORD *)v2 + 274) = 47;
        v22 = L"SSL policy requires client certificate.";
        goto LABEL_75;
      }
    }
    if ( (_DWORD)v7 == 3 )
    {
      if ( !_wcsnicmp(v6, L"Ftp", 3u) )
      {
        v6 = (wchar_t *)L"Anonymous";
        LODWORD(v7) = 9;
        goto LABEL_87;
      }
    }
    else if ( (_DWORD)v7 == 9 )
    {
LABEL_87:
      v23 = 1;
      if ( !_wcsnicmp(v6, L"Anonymous", 9u) )
        goto LABEL_89;
    }
    v23 = 0;
LABEL_89:
    v12 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)(*((_QWORD *)v2 + 132) + 1056LL) + 24LL))(
            *(_QWORD *)(*((_QWORD *)v2 + 132) + 1056LL),
            &v25);
    if ( v12 < 0 )
      goto LABEL_21;
    v24 = *((_QWORD *)v2 + 132);
    v12 = STRU::Copy((STRU *)(v24 + 384), v6, v7);
    if ( v12 < 0 )
      goto LABEL_21;
    v12 = ConvertFromUnicode(*(LPCWCH *)(v24 + 416), *(_DWORD *)(v24 + 4788), (struct STRA *)(v24 + 568));
    if ( v12 < 0 )
      goto LABEL_21;
    if ( v25 && v23 )
      FTP_COMMAND::WriteResponseAndLog(v2, "331", "Anonymous access allowed, send identity (e-mail name) as password.");
    else
      FTP_COMMAND::WriteResponseAndLog(v2, "331", "Password required");
LABEL_24:
    if ( v13 )
    {
      v14 = _InterlockedDecrement(v13);
      if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
        WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v14);
      if ( !v14 )
      {
        FTP_SITE_CONFIG::~FTP_SITE_CONFIG((FTP_SITE_CONFIG *)v13);
        ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, (void *)v13);
      }
    }
    goto LABEL_29;
  }
LABEL_19:
  v12 = STRU::Copy((STRU *)v30, v5, v8);
  if ( v12 < 0 )
  {
    v13 = 0;
LABEL_21:
    if ( !*((_DWORD *)v2 + 292) )
      *((_DWORD *)v2 + 292) = v12;
    FTP_COMMAND::WriteResponseAndLog(v2, "451", "Internal error.");
    goto LABEL_24;
  }
  v15 = FTP_SESSION::TransferToNewFtpSite(*((FTP_SESSION **)v2 + 132), v31);
  if ( v15 >= 0 )
    goto LABEL_33;
  if ( !*((_DWORD *)v2 + 292) )
    *((_DWORD *)v2 + 292) = v15;
LABEL_36:
  if ( !*((_DWORD *)v2 + 274) )
  {
    *((_DWORD *)v2 + 274) = 37;
    STRU::Copy((FTP_COMMAND *)((char *)v2 + 1112), L"Hostname didn't match any configured ftp site.");
    *((_QWORD *)v2 + 138) = *((_QWORD *)v2 + 143);
  }
  FTP_COMMAND::WriteResponseAndLog(v2, "530", "Valid hostname is expected.");
LABEL_29:
  *v27 = 1;
  STRU::~STRU(v28);
  STRA::~STRA((STRA *)v32);
  STRU::~STRU(v30);
}

```

## disassembly

```asm
0x18003d220  mov     [rsp-8+arg_10], rbx
0x18003d225  push    rbp
0x18003d226  push    rsi
0x18003d227  push    rdi
0x18003d228  push    r12
0x18003d22a  push    r13
0x18003d22c  push    r14
0x18003d22e  push    r15
0x18003d230  lea     rbp, [rsp-130h]
0x18003d238  sub     rsp, 230h
0x18003d23f  mov     rax, cs:__security_cookie
0x18003d246  xor     rax, rsp
0x18003d249  mov     [rbp+160h+var_40], rax
0x18003d250  mov     [rsp+260h+var_230], rdx
0x18003d255  mov     rbx, rcx
0x18003d258  mov     [rsp+260h+var_238], rcx
0x18003d25d  xor     r15d, r15d
0x18003d260  mov     [rsp+260h+var_240], r15d
0x18003d265  mov     edi, 80h
0x18003d26a  mov     r8d, edi; Size
0x18003d26d  xor     edx, edx; Val
0x18003d26f  lea     rcx, [rbp+160h+var_140]; void *
0x18003d273  call    memset_0
0x18003d278  lea     r12d, [r15+40h]
0x18003d27c  mov     r8d, r12d
0x18003d27f  lea     rdx, [rbp+160h+var_140]
0x18003d283  lea     rcx, [rsp+260h+var_1F0]
0x18003d288  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18003d28e  nop
0x18003d28f  mov     r8d, r12d
0x18003d292  lea     rdx, [rbp+160h+var_180]
0x18003d296  lea     rcx, [rbp+160h+var_1B8]
0x18003d29a  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18003d2a0  nop
0x18003d2a1  mov     r8d, edi; Size
0x18003d2a4  xor     edx, edx; Val
0x18003d2a6  lea     rcx, [rbp+160h+var_C0]; void *
0x18003d2ad  call    memset_0
0x18003d2b2  mov     r8d, r12d
0x18003d2b5  lea     rdx, [rbp+160h+var_C0]
0x18003d2bc  lea     rcx, [rsp+260h+var_228]
0x18003d2c1  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18003d2c7  nop
0x18003d2c8  mov     r13, [rbx+420h]
0x18003d2cf  mov     rcx, r13; this
0x18003d2d2  call    ?ResetFtpUser@FTP_SESSION@@QEAAXXZ; FTP_SESSION::ResetFtpUser(void)
0x18003d2d7  mov     rdx, [rbx+0A0h]
0x18003d2de  lea     rcx, [rsp+260h+var_228]
0x18003d2e3  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x18003d2e9  test    eax, eax
0x18003d2eb  js      loc_18003D460
0x18003d2f1  lea     edx, [rdi-4]; Ch
0x18003d2f4  mov     rcx, [rsp+260h+Str]; Str
0x18003d2f9  call    cs:__imp_wcschr
0x18003d2ff  mov     rcx, rax
0x18003d302  mov     rsi, [rsp+260h+Str]
0x18003d307  test    rax, rax
0x18003d30a  jz      short loc_18003D32E
0x18003d30c  lea     rdi, [rax+2]
0x18003d310  or      r14, 0FFFFFFFFFFFFFFFFh
0x18003d314  inc     r14
0x18003d317  cmp     [rdi+r14*2], r15w
0x18003d31c  jnz     short loc_18003D314
0x18003d31e  test    rsi, rsi
0x18003d321  jz      short loc_18003D334
0x18003d323  sub     rcx, rsi
0x18003d326  sar     rcx, 1
0x18003d329  jmp     loc_18003D3DC
0x18003d32e  mov     rdi, r15
0x18003d331  mov     r14d, r15d
0x18003d334  cmp     cs:?sm_fUseDomainNameAsHostName@FTP_COMMAND@@0HA, r15d; int FTP_COMMAND::sm_fUseDomainNameAsHostName
0x18003d33b  jz      loc_18003D4DF
0x18003d341  mov     edx, 5Ch ; '\'; Ch
0x18003d346  mov     rcx, rsi; Str
0x18003d349  call    cs:__imp_wcschr
0x18003d34f  test    rax, rax
0x18003d352  jz      short loc_18003D376
0x18003d354  mov     rsi, [rsp+260h+Str]
0x18003d359  mov     rcx, rax
0x18003d35c  sub     rcx, rsi
0x18003d35f  sar     rcx, 1
0x18003d362  lea     rdi, [rax+2]
0x18003d366  or      r14, 0FFFFFFFFFFFFFFFFh
0x18003d36a  inc     r14
0x18003d36d  cmp     [rdi+r14*2], r15w
0x18003d372  jnz     short loc_18003D36A
0x18003d374  jmp     short loc_18003D3D3
0x18003d376  mov     edx, r12d; Ch
0x18003d379  mov     rcx, [rsp+260h+Str]; Str
0x18003d37e  call    cs:__imp_wcschr
0x18003d384  test    rax, rax
0x18003d387  jz      loc_18003D4DF
0x18003d38d  mov     r15, rax
0x18003d390  lea     rsi, [rax+2]
0x18003d394  mov     edx, r12d; Ch
0x18003d397  mov     rcx, rsi; Str
0x18003d39a  call    cs:__imp_wcschr
0x18003d3a0  test    rax, rax
0x18003d3a3  jnz     short loc_18003D38D
0x18003d3a5  test    r15, r15
0x18003d3a8  mov     rbx, [rsp+260h+var_238]
0x18003d3ad  jz      loc_18003D4DC
0x18003d3b3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003d3b7  xor     edx, edx
0x18003d3b9  inc     rcx
0x18003d3bc  cmp     [rsi+rcx*2], dx
0x18003d3c0  jnz     short loc_18003D3B9
0x18003d3c2  mov     rdi, [rsp+260h+Str]
0x18003d3c7  sub     r15, rdi
0x18003d3ca  sar     r15, 1
0x18003d3cd  mov     r14d, r15d
0x18003d3d0  xor     r15d, r15d
0x18003d3d3  test    rsi, rsi
0x18003d3d6  jz      loc_18003D4DF
0x18003d3dc  mov     r8d, ecx
0x18003d3df  mov     rdx, rsi
0x18003d3e2  lea     rcx, [rsp+260h+var_1F0]
0x18003d3e7  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18003d3ed  test    eax, eax
0x18003d3ef  jns     loc_18003D4B7
0x18003d3f5  mov     rsi, r15
0x18003d3f8  cmp     [rbx+490h], r15d
0x18003d3ff  jnz     short loc_18003D407
0x18003d401  mov     [rbx+490h], eax
0x18003d407  lea     rdx, a451; "451"
0x18003d40e  lea     r8, aInternalError; "Internal error."
0x18003d415  mov     rcx, rbx; this
0x18003d418  call    ?WriteResponseAndLog@FTP_COMMAND@@QEAAJPEBD0ZZ; FTP_COMMAND::WriteResponseAndLog(char const *,char const *,...)
0x18003d41d  test    rsi, rsi
0x18003d420  jz      short loc_18003D460
0x18003d422  or      ebx, 0FFFFFFFFh
0x18003d425  lock xadd [rsi], ebx
0x18003d429  dec     ebx
0x18003d42b  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18003d432  test    rcx, rcx
0x18003d435  jz      short loc_18003D442
0x18003d437  mov     r8, rsi
0x18003d43a  mov     edx, ebx
0x18003d43c  call    cs:__imp_WriteRefTraceLog
0x18003d442  test    ebx, ebx
0x18003d444  jnz     short loc_18003D460
0x18003d446  mov     rcx, rsi; this
0x18003d449  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x18003d44e  nop
0x18003d44f  mov     rdx, rsi
0x18003d452  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x18003d459  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18003d45f  nop
0x18003d460  mov     rax, [rsp+260h+var_230]
0x18003d465  mov     dword ptr [rax], 1
0x18003d46b  lea     rcx, [rsp+260h+var_228]
0x18003d470  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18003d476  nop
0x18003d477  lea     rcx, [rbp+160h+var_1B8]
0x18003d47b  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18003d481  nop
0x18003d482  lea     rcx, [rsp+260h+var_1F0]
0x18003d487  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18003d48d  mov     rcx, [rbp+160h+var_40]
0x18003d494  xor     rcx, rsp; StackCookie
0x18003d497  call    __security_check_cookie
0x18003d49c  mov     rbx, [rsp+260h+arg_10]
0x18003d4a4  add     rsp, 230h
0x18003d4ab  pop     r15
0x18003d4ad  pop     r14
0x18003d4af  pop     r13
0x18003d4b1  pop     r12
0x18003d4b3  pop     rdi
0x18003d4b4  pop     rsi
0x18003d4b5  pop     rbp
0x18003d4b6  retn
0x18003d4b7  mov     rdx, [rbp+160h+var_1D0]; unsigned __int16 *
0x18003d4bb  mov     rcx, [rbx+420h]; this
0x18003d4c2  call    ?TransferToNewFtpSite@FTP_SESSION@@QEAAJPEBG@Z; FTP_SESSION::TransferToNewFtpSite(ushort const *)
0x18003d4c7  test    eax, eax
0x18003d4c9  jns     short loc_18003D4DF
0x18003d4cb  cmp     [rbx+490h], r15d
0x18003d4d2  jnz     short loc_18003D503
0x18003d4d4  mov     [rbx+490h], eax
0x18003d4da  jmp     short loc_18003D503
0x18003d4dc  xor     r15d, r15d
0x18003d4df  mov     rcx, [rbx+420h]; this
0x18003d4e6  mov     rax, [rcx+60h]
0x18003d4ea  cmp     [rax+4], r15d
0x18003d4ee  jnz     short loc_18003D553
0x18003d4f0  cmp     [rbx+490h], r15d
0x18003d4f7  jnz     short loc_18003D503
0x18003d4f9  mov     dword ptr [rbx+490h], 80072AF9h
0x18003d503  cmp     [rbx+448h], r15d
0x18003d50a  jnz     short loc_18003D538
0x18003d50c  mov     dword ptr [rbx+448h], 25h ; '%'
0x18003d516  lea     rdx, aHostnameDidnTM; "Hostname didn't match any configured ft"...
0x18003d51d  lea     rcx, [rbx+458h]
0x18003d524  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18003d52a  mov     rax, [rbx+478h]
0x18003d531  mov     [rbx+450h], rax
0x18003d538  lea     r8, aValidHostnameI; "Valid hostname is expected."
0x18003d53f  lea     rdx, a530; "530"
0x18003d546  mov     rcx, rbx; this
0x18003d549  call    ?WriteResponseAndLog@FTP_COMMAND@@QEAAJPEBD0ZZ; FTP_COMMAND::WriteResponseAndLog(char const *,char const *,...)
0x18003d54e  jmp     loc_18003D460
0x18003d553  test    rdi, rdi
0x18003d556  jnz     short loc_18003D56D
0x18003d558  mov     rdi, [rbx+158h]
0x18003d55f  or      r14, 0FFFFFFFFFFFFFFFFh
0x18003d563  inc     r14
0x18003d566  cmp     [rdi+r14*2], r15w
0x18003d56b  jnz     short loc_18003D563
0x18003d56d  call    ?GetReferencedSiteConfig@FTP_SESSION@@QEAAPEAVFTP_SITE_CONFIG@@XZ; FTP_SESSION::GetReferencedSiteConfig(void)
0x18003d572  mov     rsi, rax
0x18003d575  cmp     dword ptr [rax+70h], 1
0x18003d579  jnz     short loc_18003D5E4
0x18003d57b  cmp     dword ptr [r13+44Ch], 2
0x18003d583  jz      loc_18003D623
0x18003d589  cmp     [rbx+490h], r15d
0x18003d590  jnz     short loc_18003D59C
0x18003d592  mov     dword ptr [rbx+490h], 80070005h
0x18003d59c  cmp     [rbx+448h], r15d
0x18003d5a3  jnz     short loc_18003D5D1
0x18003d5a5  mov     dword ptr [rbx+448h], 19h
0x18003d5af  lea     rdx, aSslPolicyRequi; "SSL policy requires SSL for control cha"...
0x18003d5b6  lea     rcx, [rbx+458h]
0x18003d5bd  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18003d5c3  mov     rax, [rbx+478h]
0x18003d5ca  mov     [rbx+450h], rax
0x18003d5d1  lea     rdx, a534; "534"
0x18003d5d8  lea     r8, aPolicyRequires_1; "Policy requires SSL."
0x18003d5df  jmp     loc_18003D415
0x18003d5e4  cmp     dword ptr [rax+70h], 2
0x18003d5e8  jnz     short loc_18003D623
0x18003d5ea  cmp     dword ptr [r13+44Ch], 2
0x18003d5f2  jz      short loc_18003D623
0x18003d5f4  cmp     [rbx+490h], r15d
0x18003d5fb  jnz     short loc_18003D607
0x18003d5fd  mov     dword ptr [rbx+490h], 80070005h
0x18003d607  cmp     [rbx+448h], r15d
0x18003d60e  jnz     short loc_18003D5D1
0x18003d610  mov     dword ptr [rbx+448h], 1Ah
0x18003d61a  lea     rdx, aSslPolicyRequi_0; "SSL policy requires SSL for credentials"...
0x18003d621  jmp     short loc_18003D5B6
0x18003d623  cmp     [rax+78h], r15d
0x18003d627  jz      short loc_18003D69B
0x18003d629  cmp     dword ptr [r13+44Ch], 2
0x18003d631  jnz     short loc_18003D69B
0x18003d633  cmp     dword ptr [r13+488h], 80h
0x18003d63e  jnb     short loc_18003D69B
0x18003d640  cmp     [rbx+490h], r15d
0x18003d647  jnz     short loc_18003D653
0x18003d649  mov     dword ptr [rbx+490h], 80070005h
0x18003d653  cmp     [rbx+448h], r15d
0x18003d65a  jnz     short loc_18003D688
0x18003d65c  mov     dword ptr [rbx+448h], 37h ; '7'
0x18003d666  lea     rcx, [rbx+458h]
0x18003d66d  lea     rdx, a128BitEncrypti; "128 bit encryption is required for SSL "...
0x18003d674  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18003d67a  mov     rax, [rbx+478h]
0x18003d681  mov     [rbx+450h], rax
0x18003d688  lea     rdx, a534; "534"
0x18003d68f  lea     r8, aPolicyRequires; "Policy requires stronger SSL encryption"...
0x18003d696  jmp     loc_18003D415
0x18003d69b  mov     edx, [rax+428h]
0x18003d6a1  test    edx, edx
0x18003d6a3  jz      loc_18003D766
0x18003d6a9  mov     eax, [r13+48Ch]
0x18003d6b0  mov     r8d, 80070000h
0x18003d6b6  test    eax, eax
0x18003d6b8  jg      short loc_18003D6BE
0x18003d6ba  mov     ecx, eax
0x18003d6bc  jmp     short loc_18003D6C4
0x18003d6be  movzx   ecx, ax
0x18003d6c1  or      ecx, r8d
0x18003d6c4  test    ecx, ecx
0x18003d6c6  jns     short loc_18003D729
0x18003d6c8  test    eax, eax
0x18003d6ca  jle     short loc_18003D6D2
0x18003d6cc  movzx   eax, ax
0x18003d6cf  or      eax, r8d
0x18003d6d2  cmp     [rbx+490h], r15d
0x18003d6d9  jnz     short loc_18003D6E1
0x18003d6db  mov     [rbx+490h], eax
0x18003d6e1  cmp     [rbx+448h], r15d
0x18003d6e8  jnz     short loc_18003D716
0x18003d6ea  mov     dword ptr [rbx+448h], 30h ; '0'
0x18003d6f4  lea     rdx, aUserProvidedIn; "User provided invalid client certificat"...
0x18003d6fb  lea     rcx, [rbx+458h]
0x18003d702  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18003d708  mov     rax, [rbx+478h]
0x18003d70f  mov     [rbx+450h], rax
0x18003d716  lea     rdx, a534; "534"
0x18003d71d  lea     r8, aPolicyRequires_0; "Policy requires valid SSL Client certif"...
0x18003d724  jmp     loc_18003D415
0x18003d729  cmp     edx, 2
0x18003d72c  jnz     short loc_18003D766
0x18003d72e  cmp     [r13+490h], r15
0x18003d735  jnz     short loc_18003D766
0x18003d737  cmp     [rbx+490h], r15d
0x18003d73e  jnz     short loc_18003D74A
0x18003d740  mov     dword ptr [rbx+490h], 80070005h
0x18003d74a  cmp     [rbx+448h], r15d
0x18003d751  jnz     short loc_18003D716
  ... truncated ...
```
