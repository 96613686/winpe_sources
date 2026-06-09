# W3_CONTEXT::MapHandler(ulong,ushort const *,ushort const *,char const *,IScriptMapInfo * *,int)

- ea: `0x180020e20`
- end: `0x180021289`
- name: `?MapHandler@W3_CONTEXT@@UEAAJKPEBG0PEBDPEAPEAVIScriptMapInfo@@H@Z`
- size: `1129`
- prototype: `__int64 __fastcall(W3_CONTEXT *__hidden this, unsigned int, const unsigned __int16 *, wchar_t *Str, const char *, struct IScriptMapInfo **, int)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001550`
- `0x18000c94c`
- `0x18000c980`
- `0x18000d1b8`
- `0x18000d848`
- `0x1800123c0`
- `0x18001644c`
- `0x180019558`
- `0x180020620`
- `0x180020e20`
- `0x180031630`
- `0x18003439a`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `msvcrt!wcschr` at `0x180020f27`
- `msvcrt!wcschr` at `0x180020f27`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180020f54`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180020f5e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180020f68`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180021213`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002121d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180021227`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002123e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180021248`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180021252`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180020f54`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180020f5e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180020f68`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180021213`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002121d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180021227`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002123e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180021248`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180021252`
- `iisutil!?QueryStr@MULTISZ@@QEBAPEAGXZ` at `0x18002113e`
- `iisutil!?QueryStr@MULTISZ@@QEBAPEAGXZ` at `0x18002113e`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180020f8b`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180020f8b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180020f7e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180020f7e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180020eb6`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180020edb`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180020f06`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180020eb6`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180020edb`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180020f06`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180020f44`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180020f44`

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
0x180020e20  push    rbp
0x180020e22  push    rbx
0x180020e23  push    rsi
0x180020e24  push    rdi
0x180020e25  push    r12
0x180020e27  push    r13
0x180020e29  push    r14
0x180020e2b  push    r15
0x180020e2d  lea     rbp, [rsp-0C38h]
0x180020e35  sub     rsp, 0D38h
0x180020e3c  mov     rax, cs:__security_cookie
0x180020e43  xor     rax, rsp
0x180020e46  mov     [rbp+0C70h+var_50], rax
0x180020e4d  mov     rax, [rbp+0C70h+arg_28]
0x180020e54  mov     r13, rcx
0x180020e57  mov     rbx, [rbp+0C70h+arg_20]
0x180020e5e  lea     rcx, [rbp+0C70h+var_C40]; this
0x180020e62  mov     [rsp+0D70h+var_CF8], rbx
0x180020e67  mov     r14, r9
0x180020e6a  mov     [rbp+0C70h+var_CF0], rax
0x180020e6e  mov     r12, r8
0x180020e71  mov     edi, edx
0x180020e73  mov     [rsp+0D70h+var_D20], edx
0x180020e77  call    ??0W3_URL_INFO_KEY@@QEAA@XZ; W3_URL_INFO_KEY::W3_URL_INFO_KEY(void)
0x180020e7c  xor     eax, eax
0x180020e7e  lea     rcx, [rbp+0C70h+var_A50]; void *
0x180020e85  mov     r15d, 100h
0x180020e8b  mov     [rsp+0D70h+var_D18], rax
0x180020e90  mov     r8d, r15d; Size
0x180020e93  mov     [rsp+0D70h+var_D00], rax
0x180020e98  xor     edx, edx; Val
0x180020e9a  mov     [rsp+0D70h+var_D08], rax
0x180020e9f  call    memset_0
0x180020ea4  lea     esi, [r15-80h]
0x180020ea8  mov     r8d, esi
0x180020eab  lea     rdx, [rbp+0C70h+var_A50]
0x180020eb2  lea     rcx, [rbp+0C70h+var_C78]
0x180020eb6  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180020ebc  mov     r8d, r15d; Size
0x180020ebf  lea     rcx, [rbp+0C70h+var_950]; void *
0x180020ec6  xor     edx, edx; Val
0x180020ec8  call    memset_0
0x180020ecd  mov     r8d, esi
0x180020ed0  lea     rdx, [rbp+0C70h+var_950]
0x180020ed7  lea     rcx, [rbp+0C70h+var_CB0]
0x180020edb  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180020ee1  xor     edx, edx; Val
0x180020ee3  lea     rcx, [rbp+0C70h+var_850]; void *
0x180020eea  mov     r8d, 800h; Size
0x180020ef0  call    memset_0
0x180020ef5  mov     r8d, 400h
0x180020efb  lea     rdx, [rbp+0C70h+var_850]
0x180020f02  lea     rcx, [rbp+0C70h+var_CE8]
0x180020f06  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180020f0c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180020f10  mov     r15, rsi
0x180020f13  xor     eax, eax
0x180020f15  inc     r15
0x180020f18  cmp     [r12+r15*2], ax
0x180020f1d  jnz     short loc_180020F15
0x180020f1f  mov     edx, 3Fh ; '?'; Ch
0x180020f24  mov     rcx, r14; Str
0x180020f27  call    cs:__imp_wcschr
0x180020f2d  xor     ecx, ecx
0x180020f2f  test    rax, rax
0x180020f32  jz      short loc_180020F9C
0x180020f34  sub     rax, r14
0x180020f37  lea     rcx, [rbp+0C70h+var_CE8]
0x180020f3b  sar     rax, 1
0x180020f3e  mov     rdx, r14
0x180020f41  mov     r8d, eax
0x180020f44  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180020f4a  lea     rcx, [rbp+0C70h+var_CE8]
0x180020f4e  mov     ebx, eax
0x180020f50  test    eax, eax
0x180020f52  jns     short loc_180020F7E
0x180020f54  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180020f5a  lea     rcx, [rbp+0C70h+var_CB0]
0x180020f5e  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180020f64  lea     rcx, [rbp+0C70h+var_C78]
0x180020f68  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180020f6e  lea     rcx, [rbp+0C70h+var_C40]; this
0x180020f72  call    ??1W3_URL_INFO_KEY@@QEAA@XZ; W3_URL_INFO_KEY::~W3_URL_INFO_KEY(void)
0x180020f77  mov     eax, ebx
0x180020f79  jmp     loc_180021266
0x180020f7e  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180020f84  lea     rcx, [rbp+0C70h+var_CE8]
0x180020f88  mov     r14, rax
0x180020f8b  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180020f91  mov     rbx, [rsp+0D70h+var_CF8]
0x180020f96  xor     ecx, ecx
0x180020f98  mov     esi, eax
0x180020f9a  jmp     short loc_180020FA6
0x180020f9c  inc     rsi
0x180020f9f  cmp     [r14+rsi*2], cx
0x180020fa4  jnz     short loc_180020F9C
0x180020fa6  test    r12, r12
0x180020fa9  jz      loc_18002123A
0x180020faf  test    r14, r14
0x180020fb2  jz      loc_18002123A
0x180020fb8  test    rbx, rbx
0x180020fbb  jz      loc_18002123A
0x180020fc1  cmp     [rbp+0C70h+var_CF0], rcx
0x180020fc5  jz      loc_18002123A
0x180020fcb  mov     rcx, rbx; char *
0x180020fce  call    ?GetIndex@METHOD_HASH@@SA?AW4_HTTP_VERB@@PEBD@Z; METHOD_HASH::GetIndex(char const *)
0x180020fd3  mov     r9, r12; unsigned __int16 *
0x180020fd6  mov     dword ptr [rsp+0D70h+var_D48], edi; unsigned int
0x180020fda  mov     r8d, esi; unsigned int
0x180020fdd  mov     [rsp+0D70h+var_D10], eax
0x180020fe1  mov     rdx, r14; unsigned __int16 *
0x180020fe4  mov     dword ptr [rsp+0D70h+var_D50], r15d; unsigned int
0x180020fe9  lea     rcx, [rbp+0C70h+var_C40]; this
0x180020fed  call    ?Initialize@W3_URL_INFO_KEY@@QEAAJPEBGK0KK@Z; W3_URL_INFO_KEY::Initialize(ushort const *,ulong,ushort const *,ulong,ulong)
0x180020ff2  xor     edx, edx
0x180020ff4  mov     ebx, eax
0x180020ff6  test    eax, eax
0x180020ff8  jns     short loc_180021003
0x180020ffa  lea     rcx, [rbp+0C70h+var_CE8]
0x180020ffe  jmp     loc_180020F54
0x180021003  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x18002100a  lea     r9, [rsp+0D70h+var_D18]
0x18002100f  lea     r8, [rbp+0C70h+var_C40]
0x180021013  mov     [rsp+0D70h+var_D50], rdx
0x180021018  mov     rax, [rcx]
0x18002101b  mov     rax, [rax+50h]
0x18002101f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021024  mov     edi, eax
0x180021026  test    eax, eax
0x180021028  js      short loc_180021050
0x18002102a  mov     rbx, [rsp+0D70h+var_D18]
0x18002102f  test    rbx, rbx
0x180021032  jz      short loc_180021050
0x180021034  mov     rsi, [rbx+248h]
0x18002103b  add     rbx, 0FFFFFFFFFFFFFFF8h
0x18002103f  xor     r15d, r15d
0x180021042  test    rsi, rsi
0x180021045  jz      loc_1800210CF
0x18002104b  jmp     loc_180021122
0x180021050  mov     ecx, 540h; Size
0x180021055  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002105a  test    rax, rax
0x18002105d  jz      loc_18002120A
0x180021063  mov     rcx, rax; this
0x180021066  call    ??0W3_URL_INFO@@QEAA@XZ; W3_URL_INFO::W3_URL_INFO(void)
0x18002106b  mov     rbx, rax
0x18002106e  test    rax, rax
0x180021071  jz      loc_18002120A
0x180021077  mov     r9d, [rsp+0D70h+var_D20]; unsigned int
0x18002107c  mov     r8d, esi; unsigned int
0x18002107f  mov     dword ptr [rsp+0D70h+var_D48], r15d; unsigned int
0x180021084  mov     rdx, r14; unsigned __int16 *
0x180021087  mov     rcx, rax; this
0x18002108a  mov     [rsp+0D70h+var_D50], r12; unsigned __int16 *
0x18002108f  call    ?Initialize@W3_URL_INFO@@QEAAJPEBGKK0KPEAPEAVINativeSectionException@@@Z; W3_URL_INFO::Initialize(ushort const *,ulong,ulong,ushort const *,ulong,INativeSectionException * *)
0x180021094  xor     r15d, r15d
0x180021097  mov     edi, eax
0x180021099  test    eax, eax
0x18002109b  js      loc_1800211F8
0x1800210a1  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x1800210a8  lea     rax, [rbx+8]
0x1800210ac  mov     [rsp+0D70h+var_D18], rax
0x1800210b1  lea     r9, [rsp+0D70h+var_D18]
0x1800210b6  lea     r8, [rbp+0C70h+var_C40]
0x1800210ba  mov     [rsp+0D70h+var_D50], r15
0x1800210bf  lea     edx, [r15+1]
0x1800210c3  mov     rax, [rcx]
0x1800210c6  mov     rax, [rax+50h]
0x1800210ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800210cf  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x1800210d6  lea     r9, [rsp+0D70h+var_D00]
0x1800210db  mov     r8, r14
0x1800210de  mov     rdx, r12
0x1800210e1  mov     rax, [rcx]
0x1800210e4  mov     rax, [rax+0E8h]
0x1800210eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800210f0  mov     edi, eax
0x1800210f2  test    eax, eax
0x1800210f4  js      loc_1800211F8
0x1800210fa  mov     rsi, [rsp+0D70h+var_D00]
0x1800210ff  xor     eax, eax
0x180021101  lock cmpxchg [rbx+250h], rsi
0x18002110a  jz      short loc_180021122
0x18002110c  mov     rax, [rsi]
0x18002110f  mov     rcx, rsi
0x180021112  mov     rax, [rax+28h]
0x180021116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002111b  mov     rsi, [rbx+250h]
0x180021122  cmp     [rbp+0C70h+arg_30], r15d
0x180021129  jnz     short loc_180021161
0x18002112b  mov     rcx, [r13+188h]
0x180021132  add     rcx, 2498h
0x180021139  mov     [rsp+0D70h+var_D20], r15d
0x18002113e  call    cs:__imp_?QueryStr@MULTISZ@@QEBAPEAGXZ; MULTISZ::QueryStr(void)
0x180021144  lea     rdx, [rsp+0D70h+var_D20]; unsigned int *
0x180021149  mov     rcx, rsi; this
0x18002114c  mov     r8, rax; unsigned __int16 *
0x18002114f  call    ?QueryStarScriptMap@W3_METADATA@@QEAAPEAVMETA_SCRIPT_MAP_ENTRY@@PEAKPEBG@Z; W3_METADATA::QueryStarScriptMap(ulong *,ushort const *)
0x180021154  mov     [rsp+0D70h+var_D08], rax
0x180021159  mov     r14, rax
0x18002115c  test    rax, rax
0x18002115f  jnz     short loc_1800211A2
0x180021161  mov     r9d, [rsp+0D70h+var_D10]; enum _HTTP_VERB
0x180021166  lea     rax, [rsp+0D70h+var_D08]
0x18002116b  mov     [rsp+0D70h+var_D30], r15; int *
0x180021170  xor     r8d, r8d; struct W3_APPLICATION *
0x180021173  mov     [rsp+0D70h+var_D38], r15; unsigned int *
0x180021178  mov     rdx, rsi; struct W3_METADATA *
0x18002117b  mov     [rsp+0D70h+var_D40], r15; struct MULTISZ *
0x180021180  mov     rcx, rbx; this
0x180021183  mov     [rsp+0D70h+var_D48], rax; struct IScriptMapInfo **
0x180021188  mov     rax, [rsp+0D70h+var_CF8]
0x18002118d  mov     [rsp+0D70h+var_D50], rax; char *
0x180021192  call    ?ProcessUrl@W3_URL_INFO@@QEAAJPEAVW3_METADATA@@PEAVW3_APPLICATION@@W4_HTTP_VERB@@PEBDPEAPEAVIScriptMapInfo@@PEAVMULTISZ@@PEAKPEAH@Z; W3_URL_INFO::ProcessUrl(W3_METADATA *,W3_APPLICATION *,_HTTP_VERB,char const *,IScriptMapInfo * *,MULTISZ *,ulong *,int *)
0x180021197  mov     edi, eax
0x180021199  test    eax, eax
0x18002119b  js      short loc_1800211F8
0x18002119d  mov     r14, [rsp+0D70h+var_D08]
0x1800211a2  test    r14, r14
0x1800211a5  jz      short loc_1800211EE
0x1800211a7  mov     rax, [r13+0]
0x1800211ab  mov     edx, 60h ; '`'
0x1800211b0  mov     rcx, r13
0x1800211b3  mov     rax, [rax+90h]
0x1800211ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800211bf  mov     rsi, rax
0x1800211c2  test    rax, rax
0x1800211c5  jz      short loc_1800211E7
0x1800211c7  lea     rax, ??_7CLONED_SCRIPT_MAP_ENTRY@@6B@; const CLONED_SCRIPT_MAP_ENTRY::`vftable'
0x1800211ce  mov     r8, r14; struct IScriptMapInfo *
0x1800211d1  mov     rdx, r13; struct IHttpContext *
0x1800211d4  mov     [rsi], rax
0x1800211d7  mov     rcx, rsi; this
0x1800211da  call    ?Initialize@CLONED_SCRIPT_MAP_ENTRY@@QEAAJPEAVIHttpContext@@PEAVIScriptMapInfo@@@Z; CLONED_SCRIPT_MAP_ENTRY::Initialize(IHttpContext *,IScriptMapInfo *)
0x1800211df  mov     edi, eax
0x1800211e1  test    eax, eax
0x1800211e3  js      short loc_1800211F8
0x1800211e5  jmp     short loc_1800211F1
0x1800211e7  mov     edi, 80070008h
0x1800211ec  jmp     short loc_1800211F8
0x1800211ee  mov     rsi, r15
0x1800211f1  mov     rax, [rbp+0C70h+var_CF0]
0x1800211f5  mov     [rax], rsi
0x1800211f8  lea     rcx, [rbx+8]
0x1800211fc  mov     rax, [rcx]
0x1800211ff  mov     rax, [rax+10h]
0x180021203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021208  jmp     short loc_18002120F
0x18002120a  mov     edi, 80070008h
0x18002120f  lea     rcx, [rbp+0C70h+var_CE8]
0x180021213  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180021219  lea     rcx, [rbp+0C70h+var_CB0]
0x18002121d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180021223  lea     rcx, [rbp+0C70h+var_C78]
0x180021227  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002122d  lea     rcx, [rbp+0C70h+var_C40]; this
0x180021231  call    ??1W3_URL_INFO_KEY@@QEAA@XZ; W3_URL_INFO_KEY::~W3_URL_INFO_KEY(void)
0x180021236  mov     eax, edi
0x180021238  jmp     short loc_180021266
0x18002123a  lea     rcx, [rbp+0C70h+var_CE8]
0x18002123e  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180021244  lea     rcx, [rbp+0C70h+var_CB0]
0x180021248  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002124e  lea     rcx, [rbp+0C70h+var_C78]
0x180021252  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180021258  lea     rcx, [rbp+0C70h+var_C40]; this
0x18002125c  call    ??1W3_URL_INFO_KEY@@QEAA@XZ; W3_URL_INFO_KEY::~W3_URL_INFO_KEY(void)
0x180021261  mov     eax, 80070057h
0x180021266  mov     rcx, [rbp+0C70h+var_50]
0x18002126d  xor     rcx, rsp; StackCookie
0x180021270  call    __security_check_cookie
0x180021275  add     rsp, 0D38h
0x18002127c  pop     r15
0x18002127e  pop     r14
0x180021280  pop     r13
0x180021282  pop     r12
0x180021284  pop     rdi
0x180021285  pop     rsi
0x180021286  pop     rbx
0x180021287  pop     rbp
0x180021288  retn
```
