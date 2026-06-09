# W3_CONTEXT::MapHandler(ulong,ushort const *,ushort const *,char const *,IScriptMapInfo * *,int)

- ea: `0x180022a10`
- end: `0x180022ee4`
- name: `?MapHandler@W3_CONTEXT@@UEAAJKPEBG0PEBDPEAPEAVIScriptMapInfo@@H@Z`
- size: `1236`
- prototype: `__int64 __fastcall(W3_CONTEXT *__hidden this, unsigned int, const unsigned __int16 *, wchar_t *Str, const char *, struct IScriptMapInfo **, int)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001580`
- `0x18000d968`
- `0x18000d9a0`
- `0x18000e220`
- `0x18000e3c0`
- `0x1800132e0`
- `0x18001773c`
- `0x18001ab30`
- `0x180022250`
- `0x180022a10`
- `0x18003443c`
- `0x18003773a`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `msvcrt!wcschr` at `0x180022b29`
- `msvcrt!wcschr` at `0x180022b29`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180022b66`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180022b76`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180022b86`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180022e49`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180022e59`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180022e69`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180022e86`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180022e96`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180022ea6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180022b66`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180022b76`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180022b86`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180022e49`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180022e59`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180022e69`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180022e86`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180022e96`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180022ea6`
- `iisutil!?QueryStr@MULTISZ@@QEBAPEAGXZ` at `0x180022d6e`
- `iisutil!?QueryStr@MULTISZ@@QEBAPEAGXZ` at `0x180022d6e`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180022bb5`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180022bb5`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180022ba2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180022ba2`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180022aa6`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180022ad1`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180022b02`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180022aa6`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180022ad1`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180022b02`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180022b50`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180022b50`

## pseudocode

```c
__int64 __fastcall W3_CONTEXT::MapHandler(
        W3_CONTEXT *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        wchar_t *Str,
        char *a5,
        struct IScriptMapInfo **a6,
        int a7)
{
  char *v8; // rbx
  __int64 v12; // rsi
  __int64 v13; // r15
  wchar_t *v14; // rax
  int v15; // ebx
  int v17; // edi
  struct W3_METADATA *v18; // rsi
  W3_URL_INFO *v19; // rbx
  W3_URL_INFO *v20; // rax
  W3_URL_INFO *v21; // rax
  MULTISZ *v22; // rcx
  const unsigned __int16 *v23; // rax
  struct IScriptMapInfo *v24; // r14
  CLONED_SCRIPT_MAP_ENTRY *v25; // rsi
  unsigned int v26; // [rsp+50h] [rbp-B0h] BYREF
  char *v27; // [rsp+58h] [rbp-A8h] BYREF
  _HTTP_VERB Index; // [rsp+60h] [rbp-A0h]
  struct IScriptMapInfo *v29; // [rsp+68h] [rbp-98h] BYREF
  struct W3_METADATA *v30; // [rsp+70h] [rbp-90h] BYREF
  char *v31; // [rsp+78h] [rbp-88h]
  struct IScriptMapInfo **v32; // [rsp+80h] [rbp-80h]
  _BYTE v33[56]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v34[56]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v35[56]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v36[496]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v37[128]; // [rsp+320h] [rbp+220h] BYREF
  unsigned __int16 v38[128]; // [rsp+420h] [rbp+320h] BYREF
  unsigned __int16 v39[1024]; // [rsp+520h] [rbp+420h] BYREF

  v8 = a5;
  v31 = a5;
  v32 = a6;
  v26 = a2;
  W3_URL_INFO_KEY::W3_URL_INFO_KEY((W3_URL_INFO_KEY *)v36);
  v27 = 0;
  v30 = 0;
  v29 = 0;
  memset_0(v37, 0, sizeof(v37));
  STRU::STRU((STRU *)v35, v37, 0x80u);
  memset_0(v38, 0, sizeof(v38));
  STRU::STRU((STRU *)v34, v38, 0x80u);
  memset_0(v39, 0, sizeof(v39));
  STRU::STRU((STRU *)v33, v39, 0x400u);
  v12 = -1;
  v13 = -1;
  do
    ++v13;
  while ( a3[v13] );
  v14 = wcschr(Str, 0x3Fu);
  if ( v14 )
  {
    v15 = STRU::Copy((STRU *)v33, Str, v14 - Str);
    if ( v15 < 0 )
    {
LABEL_5:
      STRU::~STRU((STRU *)v33);
      STRU::~STRU((STRU *)v34);
      STRU::~STRU((STRU *)v35);
      W3_URL_INFO_KEY::~W3_URL_INFO_KEY((W3_URL_INFO_KEY *)v36);
      return (unsigned int)v15;
    }
    Str = STRU::QueryStr((STRU *)v33);
    v8 = v31;
    LODWORD(v12) = STRU::QueryCCH((STRU *)v33);
  }
  else
  {
    do
      ++v12;
    while ( Str[v12] );
  }
  if ( a3 && Str && v8 && v32 )
  {
    Index = METHOD_HASH::GetIndex(v8);
    v15 = W3_URL_INFO_KEY::Initialize((W3_URL_INFO_KEY *)v36, Str, v12, a3, v13, a2);
    if ( v15 < 0 )
      goto LABEL_5;
    v17 = (*(__int64 (__fastcall **)(W3_SERVER *, _QWORD, _BYTE *, char **, _QWORD))(*(_QWORD *)g_pW3Server + 80LL))(
            g_pW3Server,
            0,
            v36,
            &v27,
            0);
    if ( v17 >= 0 && v27 )
    {
      v18 = (struct W3_METADATA *)*((_QWORD *)v27 + 73);
      v19 = (W3_URL_INFO *)(v27 - 8);
      if ( v18 )
      {
LABEL_24:
        if ( a7
          || (v22 = (MULTISZ *)(*((_QWORD *)this + 49) + 9368LL),
              v26 = 0,
              v23 = MULTISZ::QueryStr(v22),
              v29 = W3_METADATA::QueryStarScriptMap(v18, &v26, v23),
              (v24 = v29) == 0) )
        {
          v17 = W3_URL_INFO::ProcessUrl(v19, v18, 0, Index, v31, &v29, 0, 0, 0);
          if ( v17 < 0 )
            goto LABEL_35;
          v24 = v29;
        }
        if ( !v24 )
        {
          v25 = 0;
LABEL_34:
          *v32 = v25;
          goto LABEL_35;
        }
        v25 = (CLONED_SCRIPT_MAP_ENTRY *)(*(__int64 (__fastcall **)(W3_CONTEXT *, __int64))(*(_QWORD *)this + 144LL))(
                                           this,
                                           96);
        if ( v25 )
        {
          *(_QWORD *)v25 = &CLONED_SCRIPT_MAP_ENTRY::`vftable';
          v17 = CLONED_SCRIPT_MAP_ENTRY::Initialize(v25, this, v24);
          if ( v17 >= 0 )
            goto LABEL_34;
        }
        else
        {
          v17 = -2147024888;
        }
LABEL_35:
        (*(void (__fastcall **)(__int64))(*((_QWORD *)v19 + 1) + 16LL))((__int64)v19 + 8);
LABEL_37:
        STRU::~STRU((STRU *)v33);
        STRU::~STRU((STRU *)v34);
        STRU::~STRU((STRU *)v35);
        W3_URL_INFO_KEY::~W3_URL_INFO_KEY((W3_URL_INFO_KEY *)v36);
        return (unsigned int)v17;
      }
    }
    else
    {
      v20 = (W3_URL_INFO *)operator new(0x540u);
      if ( !v20 || (v21 = W3_URL_INFO::W3_URL_INFO(v20), (v19 = v21) == 0) )
      {
        v17 = -2147024888;
        goto LABEL_37;
      }
      v17 = W3_URL_INFO::Initialize(v21, Str, v12, v26, a3, v13);
      if ( v17 < 0 )
        goto LABEL_35;
      v27 = (char *)v19 + 8;
      (*(void (__fastcall **)(W3_SERVER *, __int64, _BYTE *, char **, _QWORD))(*(_QWORD *)g_pW3Server + 80LL))(
        g_pW3Server,
        1,
        v36,
        &v27,
        0);
    }
    v17 = (*(__int64 (__fastcall **)(W3_SERVER *, const unsigned __int16 *, wchar_t *, struct W3_METADATA **))(*(_QWORD *)g_pW3Server + 232LL))(
            g_pW3Server,
            a3,
            Str,
            &v30);
    if ( v17 < 0 )
      goto LABEL_35;
    v18 = v30;
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)v19 + 74, (signed __int64)v30, 0) )
    {
      (*(void (__fastcall **)(struct W3_METADATA *))(*(_QWORD *)v18 + 40LL))(v18);
      v18 = (struct W3_METADATA *)*((_QWORD *)v19 + 74);
    }
    goto LABEL_24;
  }
  STRU::~STRU((STRU *)v33);
  STRU::~STRU((STRU *)v34);
  STRU::~STRU((STRU *)v35);
  W3_URL_INFO_KEY::~W3_URL_INFO_KEY((W3_URL_INFO_KEY *)v36);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180022a10  push    rbp
0x180022a12  push    rbx
0x180022a13  push    rsi
0x180022a14  push    rdi
0x180022a15  push    r12
0x180022a17  push    r13
0x180022a19  push    r14
0x180022a1b  push    r15
0x180022a1d  lea     rbp, [rsp-0C38h]
0x180022a25  sub     rsp, 0D38h
0x180022a2c  mov     rax, cs:__security_cookie
0x180022a33  xor     rax, rsp
0x180022a36  mov     [rbp+0C70h+var_50], rax
0x180022a3d  mov     rax, [rbp+0C70h+arg_28]
0x180022a44  mov     r13, rcx
0x180022a47  mov     rbx, [rbp+0C70h+arg_20]
0x180022a4e  lea     rcx, [rbp+0C70h+var_C40]; this
0x180022a52  mov     [rsp+0D70h+var_CF8], rbx
0x180022a57  mov     r14, r9
0x180022a5a  mov     [rbp+0C70h+var_CF0], rax
0x180022a5e  mov     r12, r8
0x180022a61  mov     edi, edx
0x180022a63  mov     [rsp+0D70h+var_D20], edx
0x180022a67  call    ??0W3_URL_INFO_KEY@@QEAA@XZ; W3_URL_INFO_KEY::W3_URL_INFO_KEY(void)
0x180022a6c  xor     eax, eax
0x180022a6e  lea     rcx, [rbp+0C70h+var_A50]; void *
0x180022a75  mov     r15d, 100h
0x180022a7b  mov     [rsp+0D70h+var_D18], rax
0x180022a80  mov     r8d, r15d; Size
0x180022a83  mov     [rsp+0D70h+var_D00], rax
0x180022a88  xor     edx, edx; Val
0x180022a8a  mov     [rsp+0D70h+var_D08], rax
0x180022a8f  call    memset_0
0x180022a94  lea     esi, [r15-80h]
0x180022a98  mov     r8d, esi
0x180022a9b  lea     rdx, [rbp+0C70h+var_A50]
0x180022aa2  lea     rcx, [rbp+0C70h+var_C78]
0x180022aa6  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180022aad  nop     dword ptr [rax+rax+00h]
0x180022ab2  mov     r8d, r15d; Size
0x180022ab5  lea     rcx, [rbp+0C70h+var_950]; void *
0x180022abc  xor     edx, edx; Val
0x180022abe  call    memset_0
0x180022ac3  mov     r8d, esi
0x180022ac6  lea     rdx, [rbp+0C70h+var_950]
0x180022acd  lea     rcx, [rbp+0C70h+var_CB0]
0x180022ad1  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180022ad8  nop     dword ptr [rax+rax+00h]
0x180022add  xor     edx, edx; Val
0x180022adf  lea     rcx, [rbp+0C70h+var_850]; void *
0x180022ae6  mov     r8d, 800h; Size
0x180022aec  call    memset_0
0x180022af1  mov     r8d, 400h
0x180022af7  lea     rdx, [rbp+0C70h+var_850]
0x180022afe  lea     rcx, [rbp+0C70h+var_CE8]
0x180022b02  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180022b09  nop     dword ptr [rax+rax+00h]
0x180022b0e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180022b12  mov     r15, rsi
0x180022b15  xor     eax, eax
0x180022b17  inc     r15
0x180022b1a  cmp     [r12+r15*2], ax
0x180022b1f  jnz     short loc_180022B17
0x180022b21  mov     edx, 3Fh ; '?'; Ch
0x180022b26  mov     rcx, r14; Str
0x180022b29  call    cs:__imp_wcschr
0x180022b30  nop     dword ptr [rax+rax+00h]
0x180022b35  xor     ecx, ecx
0x180022b37  test    rax, rax
0x180022b3a  jz      loc_180022BCC
0x180022b40  sub     rax, r14
0x180022b43  lea     rcx, [rbp+0C70h+var_CE8]
0x180022b47  sar     rax, 1
0x180022b4a  mov     rdx, r14
0x180022b4d  mov     r8d, eax
0x180022b50  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180022b57  nop     dword ptr [rax+rax+00h]
0x180022b5c  lea     rcx, [rbp+0C70h+var_CE8]
0x180022b60  mov     ebx, eax
0x180022b62  test    eax, eax
0x180022b64  jns     short loc_180022BA2
0x180022b66  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180022b6d  nop     dword ptr [rax+rax+00h]
0x180022b72  lea     rcx, [rbp+0C70h+var_CB0]
0x180022b76  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180022b7d  nop     dword ptr [rax+rax+00h]
0x180022b82  lea     rcx, [rbp+0C70h+var_C78]
0x180022b86  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180022b8d  nop     dword ptr [rax+rax+00h]
0x180022b92  lea     rcx, [rbp+0C70h+var_C40]; this
0x180022b96  call    ??1W3_URL_INFO_KEY@@QEAA@XZ; W3_URL_INFO_KEY::~W3_URL_INFO_KEY(void)
0x180022b9b  mov     eax, ebx
0x180022b9d  jmp     loc_180022EC0
0x180022ba2  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180022ba9  nop     dword ptr [rax+rax+00h]
0x180022bae  lea     rcx, [rbp+0C70h+var_CE8]
0x180022bb2  mov     r14, rax
0x180022bb5  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180022bbc  nop     dword ptr [rax+rax+00h]
0x180022bc1  mov     rbx, [rsp+0D70h+var_CF8]
0x180022bc6  xor     ecx, ecx
0x180022bc8  mov     esi, eax
0x180022bca  jmp     short loc_180022BD6
0x180022bcc  inc     rsi
0x180022bcf  cmp     [r14+rsi*2], cx
0x180022bd4  jnz     short loc_180022BCC
0x180022bd6  test    r12, r12
0x180022bd9  jz      loc_180022E82
0x180022bdf  test    r14, r14
0x180022be2  jz      loc_180022E82
0x180022be8  test    rbx, rbx
0x180022beb  jz      loc_180022E82
0x180022bf1  cmp     [rbp+0C70h+var_CF0], rcx
0x180022bf5  jz      loc_180022E82
0x180022bfb  mov     rcx, rbx; char *
0x180022bfe  call    ?GetIndex@METHOD_HASH@@SA?AW4_HTTP_VERB@@PEBD@Z; METHOD_HASH::GetIndex(char const *)
0x180022c03  mov     r9, r12; unsigned __int16 *
0x180022c06  mov     dword ptr [rsp+0D70h+var_D48], edi; unsigned int
0x180022c0a  mov     r8d, esi; unsigned int
0x180022c0d  mov     [rsp+0D70h+var_D10], eax
0x180022c11  mov     rdx, r14; unsigned __int16 *
0x180022c14  mov     dword ptr [rsp+0D70h+var_D50], r15d; unsigned int
0x180022c19  lea     rcx, [rbp+0C70h+var_C40]; this
0x180022c1d  call    ?Initialize@W3_URL_INFO_KEY@@QEAAJPEBGK0KK@Z; W3_URL_INFO_KEY::Initialize(ushort const *,ulong,ushort const *,ulong,ulong)
0x180022c22  xor     edx, edx
0x180022c24  mov     ebx, eax
0x180022c26  test    eax, eax
0x180022c28  jns     short loc_180022C33
0x180022c2a  lea     rcx, [rbp+0C70h+var_CE8]
0x180022c2e  jmp     loc_180022B66
0x180022c33  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x180022c3a  lea     r9, [rsp+0D70h+var_D18]
0x180022c3f  lea     r8, [rbp+0C70h+var_C40]
0x180022c43  mov     [rsp+0D70h+var_D50], rdx
0x180022c48  mov     rax, [rcx]
0x180022c4b  mov     rax, [rax+50h]
0x180022c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c54  mov     edi, eax
0x180022c56  test    eax, eax
0x180022c58  js      short loc_180022C80
0x180022c5a  mov     rbx, [rsp+0D70h+var_D18]
0x180022c5f  test    rbx, rbx
0x180022c62  jz      short loc_180022C80
0x180022c64  mov     rsi, [rbx+248h]
0x180022c6b  add     rbx, 0FFFFFFFFFFFFFFF8h
0x180022c6f  xor     r15d, r15d
0x180022c72  test    rsi, rsi
0x180022c75  jz      loc_180022CFF
0x180022c7b  jmp     loc_180022D52
0x180022c80  mov     ecx, 540h; Size
0x180022c85  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022c8a  test    rax, rax
0x180022c8d  jz      loc_180022E40
0x180022c93  mov     rcx, rax; this
0x180022c96  call    ??0W3_URL_INFO@@QEAA@XZ; W3_URL_INFO::W3_URL_INFO(void)
0x180022c9b  mov     rbx, rax
0x180022c9e  test    rax, rax
0x180022ca1  jz      loc_180022E40
0x180022ca7  mov     r9d, [rsp+0D70h+var_D20]; unsigned int
0x180022cac  mov     r8d, esi; unsigned int
0x180022caf  mov     dword ptr [rsp+0D70h+var_D48], r15d; unsigned int
0x180022cb4  mov     rdx, r14; unsigned __int16 *
0x180022cb7  mov     rcx, rax; this
0x180022cba  mov     [rsp+0D70h+var_D50], r12; unsigned __int16 *
0x180022cbf  call    ?Initialize@W3_URL_INFO@@QEAAJPEBGKK0KPEAPEAVINativeSectionException@@@Z; W3_URL_INFO::Initialize(ushort const *,ulong,ulong,ushort const *,ulong,INativeSectionException * *)
0x180022cc4  xor     r15d, r15d
0x180022cc7  mov     edi, eax
0x180022cc9  test    eax, eax
0x180022ccb  js      loc_180022E2E
0x180022cd1  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x180022cd8  lea     rax, [rbx+8]
0x180022cdc  mov     [rsp+0D70h+var_D18], rax
0x180022ce1  lea     r9, [rsp+0D70h+var_D18]
0x180022ce6  lea     r8, [rbp+0C70h+var_C40]
0x180022cea  mov     [rsp+0D70h+var_D50], r15
0x180022cef  lea     edx, [r15+1]
0x180022cf3  mov     rax, [rcx]
0x180022cf6  mov     rax, [rax+50h]
0x180022cfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022cff  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x180022d06  lea     r9, [rsp+0D70h+var_D00]
0x180022d0b  mov     r8, r14
0x180022d0e  mov     rdx, r12
0x180022d11  mov     rax, [rcx]
0x180022d14  mov     rax, [rax+0E8h]
0x180022d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d20  mov     edi, eax
0x180022d22  test    eax, eax
0x180022d24  js      loc_180022E2E
0x180022d2a  mov     rsi, [rsp+0D70h+var_D00]
0x180022d2f  xor     eax, eax
0x180022d31  lock cmpxchg [rbx+250h], rsi
0x180022d3a  jz      short loc_180022D52
0x180022d3c  mov     rax, [rsi]
0x180022d3f  mov     rcx, rsi
0x180022d42  mov     rax, [rax+28h]
0x180022d46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d4b  mov     rsi, [rbx+250h]
0x180022d52  cmp     [rbp+0C70h+arg_30], r15d
0x180022d59  jnz     short loc_180022D97
0x180022d5b  mov     rcx, [r13+188h]
0x180022d62  add     rcx, 2498h
0x180022d69  mov     [rsp+0D70h+var_D20], r15d
0x180022d6e  call    cs:__imp_?QueryStr@MULTISZ@@QEBAPEAGXZ; MULTISZ::QueryStr(void)
0x180022d75  nop     dword ptr [rax+rax+00h]
0x180022d7a  lea     rdx, [rsp+0D70h+var_D20]; unsigned int *
0x180022d7f  mov     rcx, rsi; this
0x180022d82  mov     r8, rax; unsigned __int16 *
0x180022d85  call    ?QueryStarScriptMap@W3_METADATA@@QEAAPEAVMETA_SCRIPT_MAP_ENTRY@@PEAKPEBG@Z; W3_METADATA::QueryStarScriptMap(ulong *,ushort const *)
0x180022d8a  mov     [rsp+0D70h+var_D08], rax
0x180022d8f  mov     r14, rax
0x180022d92  test    rax, rax
0x180022d95  jnz     short loc_180022DD8
0x180022d97  mov     r9d, [rsp+0D70h+var_D10]; enum _HTTP_VERB
0x180022d9c  lea     rax, [rsp+0D70h+var_D08]
0x180022da1  mov     [rsp+0D70h+var_D30], r15; int *
0x180022da6  xor     r8d, r8d; struct W3_APPLICATION *
0x180022da9  mov     [rsp+0D70h+var_D38], r15; unsigned int *
0x180022dae  mov     rdx, rsi; struct W3_METADATA *
0x180022db1  mov     [rsp+0D70h+var_D40], r15; struct MULTISZ *
0x180022db6  mov     rcx, rbx; this
0x180022db9  mov     [rsp+0D70h+var_D48], rax; struct IScriptMapInfo **
0x180022dbe  mov     rax, [rsp+0D70h+var_CF8]
0x180022dc3  mov     [rsp+0D70h+var_D50], rax; char *
0x180022dc8  call    ?ProcessUrl@W3_URL_INFO@@QEAAJPEAVW3_METADATA@@PEAVW3_APPLICATION@@W4_HTTP_VERB@@PEBDPEAPEAVIScriptMapInfo@@PEAVMULTISZ@@PEAKPEAH@Z; W3_URL_INFO::ProcessUrl(W3_METADATA *,W3_APPLICATION *,_HTTP_VERB,char const *,IScriptMapInfo * *,MULTISZ *,ulong *,int *)
0x180022dcd  mov     edi, eax
0x180022dcf  test    eax, eax
0x180022dd1  js      short loc_180022E2E
0x180022dd3  mov     r14, [rsp+0D70h+var_D08]
0x180022dd8  test    r14, r14
0x180022ddb  jz      short loc_180022E24
0x180022ddd  mov     rax, [r13+0]
0x180022de1  mov     edx, 60h ; '`'
0x180022de6  mov     rcx, r13
0x180022de9  mov     rax, [rax+90h]
0x180022df0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022df5  mov     rsi, rax
0x180022df8  test    rax, rax
0x180022dfb  jz      short loc_180022E1D
0x180022dfd  lea     rax, ??_7CLONED_SCRIPT_MAP_ENTRY@@6B@; const CLONED_SCRIPT_MAP_ENTRY::`vftable'
0x180022e04  mov     r8, r14; struct IScriptMapInfo *
0x180022e07  mov     rdx, r13; struct IHttpContext *
0x180022e0a  mov     [rsi], rax
0x180022e0d  mov     rcx, rsi; this
0x180022e10  call    ?Initialize@CLONED_SCRIPT_MAP_ENTRY@@QEAAJPEAVIHttpContext@@PEAVIScriptMapInfo@@@Z; CLONED_SCRIPT_MAP_ENTRY::Initialize(IHttpContext *,IScriptMapInfo *)
0x180022e15  mov     edi, eax
0x180022e17  test    eax, eax
0x180022e19  js      short loc_180022E2E
0x180022e1b  jmp     short loc_180022E27
0x180022e1d  mov     edi, 80070008h
0x180022e22  jmp     short loc_180022E2E
0x180022e24  mov     rsi, r15
0x180022e27  mov     rax, [rbp+0C70h+var_CF0]
0x180022e2b  mov     [rax], rsi
0x180022e2e  lea     rcx, [rbx+8]
0x180022e32  mov     rax, [rcx]
0x180022e35  mov     rax, [rax+10h]
0x180022e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e3e  jmp     short loc_180022E45
0x180022e40  mov     edi, 80070008h
0x180022e45  lea     rcx, [rbp+0C70h+var_CE8]
0x180022e49  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180022e50  nop     dword ptr [rax+rax+00h]
0x180022e55  lea     rcx, [rbp+0C70h+var_CB0]
0x180022e59  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180022e60  nop     dword ptr [rax+rax+00h]
0x180022e65  lea     rcx, [rbp+0C70h+var_C78]
0x180022e69  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180022e70  nop     dword ptr [rax+rax+00h]
0x180022e75  lea     rcx, [rbp+0C70h+var_C40]; this
0x180022e79  call    ??1W3_URL_INFO_KEY@@QEAA@XZ; W3_URL_INFO_KEY::~W3_URL_INFO_KEY(void)
0x180022e7e  mov     eax, edi
0x180022e80  jmp     short loc_180022EC0
0x180022e82  lea     rcx, [rbp+0C70h+var_CE8]
0x180022e86  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180022e8d  nop     dword ptr [rax+rax+00h]
0x180022e92  lea     rcx, [rbp+0C70h+var_CB0]
0x180022e96  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180022e9d  nop     dword ptr [rax+rax+00h]
0x180022ea2  lea     rcx, [rbp+0C70h+var_C78]
0x180022ea6  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180022ead  nop     dword ptr [rax+rax+00h]
0x180022eb2  lea     rcx, [rbp+0C70h+var_C40]; this
0x180022eb6  call    ??1W3_URL_INFO_KEY@@QEAA@XZ; W3_URL_INFO_KEY::~W3_URL_INFO_KEY(void)
0x180022ebb  mov     eax, 80070057h
0x180022ec0  mov     rcx, [rbp+0C70h+var_50]
0x180022ec7  xor     rcx, rsp; StackCookie
0x180022eca  call    __security_check_cookie
0x180022ecf  add     rsp, 0D38h
0x180022ed6  pop     r15
0x180022ed8  pop     r14
0x180022eda  pop     r13
0x180022edc  pop     r12
0x180022ede  pop     rdi
0x180022edf  pop     rsi
0x180022ee0  pop     rbx
0x180022ee1  pop     rbp
0x180022ee2  retn
```
