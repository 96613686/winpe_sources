# W3_SERVER::GetFileInfo(ushort const *,void *,void *,ushort const *,void *,int,IHttpFileInfo * *,IHttpTraceContext *)

- ea: `0x1800115b0`
- end: `0x180011c3a`
- name: `?GetFileInfo@W3_SERVER@@UEAAJPEBGPEAX101HPEAPEAVIHttpFileInfo@@PEAVIHttpTraceContext@@@Z`
- size: `1674`
- prototype: `__int64 __fastcall(W3_SERVER *this, unsigned __int16 *, void *, void *, unsigned __int16 *, HANDLE Token, int, struct IHttpFileInfo **, struct IHttpTraceContext *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x1800115b0`
- `0x180011c40`
- `0x18001f09c`
- `0x18001f2c8`
- `0x18001f45c`
- `0x18003773a`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `msvcrt!_wcsupr` at `0x1800117b3`
- `msvcrt!_wcsupr` at `0x1800117b3`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800118b7`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800118c7`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18001190d`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18001191d`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800118b7`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800118c7`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18001190d`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18001191d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800118d7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001192d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800118d7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001192d`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180011691`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800116a9`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180011a5c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180011a6f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180011b5f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180011b72`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180011691`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800116a9`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180011a5c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180011a6f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180011b5f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180011b72`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800117a4`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800117a4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180011792`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180011792`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180011625`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180011625`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180011656`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180011681`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180011656`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180011681`
- `iisutil!LookupTokenAccountName` at `0x180011a1b`
- `iisutil!LookupTokenAccountName` at `0x180011a1b`

## pseudocode

```c
__int64 __fastcall W3_SERVER::GetFileInfo(
        W3_SERVER *this,
        unsigned __int16 *a2,
        void *a3,
        void *a4,
        unsigned __int16 *a5,
        HANDLE Token,
        int a7,
        struct IHttpFileInfo **a8,
        struct IHttpTraceContext *a9)
{
  struct IHttpTraceContext *v10; // rsi
  unsigned __int16 *v11; // rbx
  W3_SERVER *v12; // rdi
  int v13; // r12d
  int (__fastcall **v14)(struct IHttpTraceContext *, GUID **); // rcx
  int (__fastcall **v15)(struct IHttpTraceContext *, GUID **); // rax
  int (__fastcall **v16)(struct IHttpTraceContext *, GUID **); // rax
  int FileInfo; // ebx
  wchar_t *Str; // rax
  __int64 v19; // rax
  struct IHttpFileInfo *v20; // rdi
  unsigned __int16 *v21; // r15
  int (__fastcall **v22)(struct IHttpTraceContext *, GUID **); // rax
  int v23; // r12d
  int (__fastcall **v24)(struct IHttpTraceContext *, GUID **); // rax
  HANDLE v26; // rcx
  const unsigned __int16 *Ptr; // rdi
  const unsigned __int16 *v28; // rbx
  const struct _GUID *v29; // rax
  const unsigned __int16 *v30; // r9
  HANDLE v31; // rdx
  int v32; // eax
  __int64 v33; // rdx
  __int64 (__fastcall *v34)(struct IHttpFileInfo *, HANDLE, void *); // rax
  void *v35; // r8
  HANDLE v36; // rdx
  const unsigned __int16 *v37; // rdi
  const unsigned __int16 *v38; // rbx
  const struct _GUID *v39; // rax
  const char *v40; // r15
  const struct _GUID *v41; // rax
  int v42; // [rsp+28h] [rbp-D8h]
  const struct _GUID *v43; // [rsp+30h] [rbp-D0h]
  GUID *v44; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v45; // [rsp+58h] [rbp-A8h]
  int v46; // [rsp+68h] [rbp-98h]
  char v47[4]; // [rsp+6Ch] [rbp-94h]
  struct IHttpFileInfo *v48; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v49; // [rsp+78h] [rbp-88h]
  W3_SERVER *v50; // [rsp+80h] [rbp-80h]
  void *v51; // [rsp+88h] [rbp-78h]
  void *v52; // [rsp+90h] [rbp-70h]
  _BYTE v53[48]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v54[56]; // [rsp+C8h] [rbp-38h] BYREF
  void **v55; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v56[56]; // [rsp+108h] [rbp+8h] BYREF
  unsigned __int16 v57[256]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int8 v58[512]; // [rsp+340h] [rbp+240h] BYREF
  unsigned __int8 v59[512]; // [rsp+540h] [rbp+440h] BYREF

  v10 = a9;
  v11 = a2;
  v52 = a3;
  v12 = this;
  v49 = a2;
  v50 = this;
  v55 = &W3_FILE_KEY::`vftable';
  v51 = a4;
  STRU::STRU((STRU *)v56, v57, 0x100u);
  memset_0(v58, 0, sizeof(v58));
  BUFFER::BUFFER((BUFFER *)v54, v58, 0x200u);
  memset_0(v59, 0, sizeof(v59));
  BUFFER::BUFFER((BUFFER *)v53, v59, 0x200u);
  *(_WORD *)BUFFER::QueryPtr((BUFFER *)v54) = 0;
  *(_WORD *)BUFFER::QueryPtr((BUFFER *)v53) = 0;
  if ( !v11 || !a8 )
  {
    BUFFER::~BUFFER((BUFFER *)v53);
    BUFFER::~BUFFER((BUFFER *)v54);
    STRU::~STRU((STRU *)v56);
    return 2147942487LL;
  }
  v13 = 0;
  v46 = 0;
  *(_DWORD *)v47 = 0;
  *a8 = 0;
  if ( !a9 )
    v10 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(W3_SERVER *))(*(_QWORD *)v12 + 184LL))(v12);
  v14 = *(int (__fastcall ***)(struct IHttpTraceContext *, GUID **))v10;
  v44 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v45 = 0;
  if ( (*v14)(v10, &v44) >= 0 && DWORD1(v45) >= 4 && DWORD2(v45) && ((_DWORD)v45 == 128 || (v45 & 0x80u) != 0LL)
    || (v44 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid,
        v15 = *(int (__fastcall ***)(struct IHttpTraceContext *, GUID **))v10,
        v45 = 0,
        (*v15)(v10, &v44) >= 0)
    && DWORD1(v45) >= 4
    && DWORD2(v45)
    && ((_DWORD)v45 == 128 || (v45 & 0x80u) != 0LL) )
  {
    if ( Token )
    {
      v26 = Token;
    }
    else
    {
      if ( !a3 )
        goto LABEL_9;
      v26 = a3;
    }
    v13 = LookupTokenAccountName(v26, (struct BUFFER *)v54, (struct BUFFER *)v53);
  }
LABEL_9:
  v44 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v16 = *(int (__fastcall ***)(struct IHttpTraceContext *, GUID **))v10;
  v45 = 0;
  if ( (*v16)(v10, &v44) >= 0
    && DWORD1(v45) >= 4
    && DWORD2(v45)
    && ((_DWORD)v45 == 128 || (v45 & 0x80u) != 0LL)
    && v13 >= 0 )
  {
    Ptr = (const unsigned __int16 *)BUFFER::QueryPtr((BUFFER *)v53);
    v28 = (const unsigned __int16 *)BUFFER::QueryPtr((BUFFER *)v54);
    v29 = (const struct _GUID *)(*(__int64 (__fastcall **)(struct IHttpTraceContext *))(*(_QWORD *)v10 + 24LL))(v10);
    v30 = v28;
    v11 = v49;
    IISCacheEvents::FILE_CACHE_ACCESS_START::RaiseEvent(v10, v29, v49, v30, Ptr);
    v12 = v50;
  }
  FileInfo = STRU::Copy((STRU *)v56, v11);
  Str = STRU::QueryStr((STRU *)v56);
  _wcsupr(Str);
  if ( FileInfo >= 0 )
  {
    v19 = *(_QWORD *)v12;
    v48 = 0;
    if ( (*(unsigned int (__fastcall **)(W3_SERVER *, _QWORD, void ***, struct IHttpFileInfo **, struct IHttpTraceContext *))(v19 + 80))(
           v12,
           0,
           &v55,
           &v48,
           v10)
      || (v20 = v48) == 0 )
    {
LABEL_14:
      v21 = v49;
      FileInfo = W3_FILE_INFO::GetFileInfo(v49, a8, v52, a5, Token, a7, v43);
      if ( FileInfo >= 0 )
      {
        v44 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
        v22 = *(int (__fastcall ***)(struct IHttpTraceContext *, GUID **))v10;
        v45 = 0;
        if ( (*v22)(v10, &v44) >= 0
          && DWORD1(v45) >= 4
          && DWORD2(v45)
          && ((_DWORD)v45 == 128 || (v45 & 0x80u) != 0LL)
          && v13 >= 0 )
        {
          v37 = (const unsigned __int16 *)BUFFER::QueryPtr((BUFFER *)v53);
          v38 = (const unsigned __int16 *)BUFFER::QueryPtr((BUFFER *)v54);
          v39 = (const struct _GUID *)(*(__int64 (__fastcall **)(struct IHttpTraceContext *))(*(_QWORD *)v10 + 24LL))(v10);
          IISCacheEvents::FILE_CACHE_CREATE_FILE::RaiseEvent(v10, v39, v21, v38, v37);
        }
        if ( a7 && *a8 && ((*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a8 + 56LL))(*a8) & 0x4000) == 0 )
        {
          v48 = *a8;
          (*(void (__fastcall **)(W3_SERVER *, __int64, void ***, struct IHttpFileInfo **, struct IHttpTraceContext *))(*(_QWORD *)v50 + 80LL))(
            v50,
            1,
            &v55,
            &v48,
            v10);
          *a8 = v48;
          *(_DWORD *)v47 = 1;
        }
        FileInfo = 0;
        v23 = 0;
        goto LABEL_19;
      }
      goto LABEL_53;
    }
    v31 = Token;
    if ( !Token )
      v31 = a3;
    v32 = (*(__int64 (__fastcall **)(struct IHttpFileInfo *, HANDLE))(*(_QWORD *)v48 + 160LL))(v48, v31);
    v33 = *(_QWORD *)v20;
    if ( v32 )
    {
      (*(void (__fastcall **)(struct IHttpFileInfo *))(v33 + 16))(v20);
      goto LABEL_14;
    }
    v34 = *(__int64 (__fastcall **)(struct IHttpFileInfo *, HANDLE, void *))(v33 + 128);
    if ( Token )
    {
      v35 = 0;
      v36 = Token;
    }
    else
    {
      v35 = v51;
      v36 = a3;
    }
    FileInfo = v34(v20, v36, v35);
    if ( FileInfo >= 0 )
    {
      v23 = 1;
      *a8 = v20;
      goto LABEL_19;
    }
    (*(void (__fastcall **)(struct IHttpFileInfo *))(*(_QWORD *)v20 + 16LL))(v20);
  }
LABEL_53:
  v23 = v46;
LABEL_19:
  v44 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v24 = *(int (__fastcall ***)(struct IHttpTraceContext *, GUID **))v10;
  v45 = 0;
  if ( (*v24)(v10, &v44) >= 0 && DWORD1(v45) >= 4 && DWORD2(v45) && ((_DWORD)v45 == 128 || (v45 & 0x80u) != 0LL) )
  {
    v40 = dword_18003C5E4;
    if ( *a8 )
    {
      if ( (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a8 + 112LL))(*a8) )
        v40 = (const char *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a8 + 112LL))(*a8);
    }
    v41 = (const struct _GUID *)(*(__int64 (__fastcall **)(struct IHttpTraceContext *))(*(_QWORD *)v10 + 24LL))(v10);
    IISCacheEvents::FILE_CACHE_ACCESS_END::RaiseEvent(
      v10,
      v41,
      FileInfo >= 0,
      v23,
      v47[0],
      v42,
      (int)v43,
      FileInfo,
      v40);
  }
  BUFFER::~BUFFER((BUFFER *)v53);
  BUFFER::~BUFFER((BUFFER *)v54);
  STRU::~STRU((STRU *)v56);
  return (unsigned int)FileInfo;
}

```

## disassembly

```asm
0x1800115b0  push    rbp
0x1800115b2  push    rbx
0x1800115b3  push    rsi
0x1800115b4  push    rdi
0x1800115b5  push    r12
0x1800115b7  push    r13
0x1800115b9  push    r14
0x1800115bb  push    r15
0x1800115bd  lea     rbp, [rsp-658h]
0x1800115c5  sub     rsp, 758h
0x1800115cc  mov     rax, cs:__security_cookie
0x1800115d3  xor     rax, rsp
0x1800115d6  mov     [rbp+690h+var_50], rax
0x1800115dd  mov     r15, [rbp+690h+arg_28]
0x1800115e4  lea     rax, ??_7W3_FILE_KEY@@6B@; const W3_FILE_KEY::`vftable'
0x1800115eb  mov     r14, [rbp+690h+arg_38]
0x1800115f2  mov     r13, r8
0x1800115f5  mov     rsi, [rbp+690h+arg_40]
0x1800115fc  mov     rbx, rdx
0x1800115ff  mov     [rbp+690h+var_700], r8
0x180011603  mov     rdi, rcx
0x180011606  mov     [rsp+790h+var_718], rdx
0x18001160b  mov     r8d, 100h
0x180011611  mov     [rbp+690h+var_710], rcx
0x180011615  lea     rdx, [rbp+690h+var_650]
0x180011619  lea     rcx, [rbp+690h+var_688]
0x18001161d  mov     [rbp+690h+var_690], rax
0x180011621  mov     [rbp+690h+var_708], r9
0x180011625  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001162c  nop     dword ptr [rax+rax+00h]
0x180011631  mov     r12d, 200h
0x180011637  lea     rcx, [rbp+690h+var_450]; void *
0x18001163e  mov     r8d, r12d; Size
0x180011641  xor     edx, edx; Val
0x180011643  call    memset_0
0x180011648  mov     r8d, r12d
0x18001164b  lea     rdx, [rbp+690h+var_450]
0x180011652  lea     rcx, [rbp+690h+var_6C8]
0x180011656  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x18001165d  nop     dword ptr [rax+rax+00h]
0x180011662  mov     r8d, r12d; Size
0x180011665  lea     rcx, [rbp+690h+var_250]; void *
0x18001166c  xor     edx, edx; Val
0x18001166e  call    memset_0
0x180011673  mov     r8d, r12d
0x180011676  lea     rdx, [rbp+690h+var_250]
0x18001167d  lea     rcx, [rbp+690h+var_6F8]
0x180011681  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x180011688  nop     dword ptr [rax+rax+00h]
0x18001168d  lea     rcx, [rbp+690h+var_6C8]
0x180011691  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180011698  nop     dword ptr [rax+rax+00h]
0x18001169d  mov     rcx, rax
0x1800116a0  xor     eax, eax
0x1800116a2  mov     [rcx], ax
0x1800116a5  lea     rcx, [rbp+690h+var_6F8]
0x1800116a9  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800116b0  nop     dword ptr [rax+rax+00h]
0x1800116b5  mov     rcx, rax
0x1800116b8  xor     eax, eax
0x1800116ba  mov     [rcx], ax
0x1800116bd  test    rbx, rbx
0x1800116c0  jz      loc_180011909
0x1800116c6  test    r14, r14
0x1800116c9  jz      loc_180011909
0x1800116cf  xor     r12d, r12d
0x1800116d2  mov     [rsp+790h+var_728], eax
0x1800116d6  mov     dword ptr [rsp+790h+var_724], eax
0x1800116da  mov     [r14], rax
0x1800116dd  test    rsi, rsi
0x1800116e0  jz      loc_1800119A2
0x1800116e6  mov     rcx, [rsi]
0x1800116e9  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x1800116f0  mov     [rsp+790h+var_740], rax
0x1800116f5  lea     rdx, [rsp+790h+var_740]
0x1800116fa  xorps   xmm0, xmm0
0x1800116fd  movdqu  [rsp+790h+var_738], xmm0
0x180011703  mov     rax, [rcx]
0x180011706  mov     rcx, rsi
0x180011709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001170e  test    eax, eax
0x180011710  js      short loc_18001171D
0x180011712  cmp     dword ptr [rsp+790h+var_738+4], 4
0x180011717  jnb     loc_1800119BC
0x18001171d  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180011724  xorps   xmm0, xmm0
0x180011727  mov     [rsp+790h+var_740], rax
0x18001172c  lea     rdx, [rsp+790h+var_740]
0x180011731  mov     rax, [rsi]
0x180011734  mov     rcx, rsi
0x180011737  movdqu  [rsp+790h+var_738], xmm0
0x18001173d  mov     rax, [rax]
0x180011740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011745  test    eax, eax
0x180011747  js      short loc_180011754
0x180011749  cmp     dword ptr [rsp+790h+var_738+4], 4
0x18001174e  jnb     loc_1800119DD
0x180011754  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18001175b  xorps   xmm0, xmm0
0x18001175e  mov     [rsp+790h+var_740], rax
0x180011763  lea     rdx, [rsp+790h+var_740]
0x180011768  mov     rax, [rsi]
0x18001176b  mov     rcx, rsi
0x18001176e  movdqu  [rsp+790h+var_738], xmm0
0x180011774  mov     rax, [rax]
0x180011777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001177c  test    eax, eax
0x18001177e  js      short loc_18001178B
0x180011780  cmp     dword ptr [rsp+790h+var_738+4], 4
0x180011785  jnb     loc_180011A2F
0x18001178b  mov     rdx, rbx
0x18001178e  lea     rcx, [rbp+690h+var_688]
0x180011792  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180011799  nop     dword ptr [rax+rax+00h]
0x18001179e  lea     rcx, [rbp+690h+var_688]
0x1800117a2  mov     ebx, eax
0x1800117a4  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800117ab  nop     dword ptr [rax+rax+00h]
0x1800117b0  mov     rcx, rax; String
0x1800117b3  call    cs:__imp__wcsupr
0x1800117ba  nop     dword ptr [rax+rax+00h]
0x1800117bf  test    ebx, ebx
0x1800117c1  js      loc_180011B28
0x1800117c7  mov     rax, [rdi]
0x1800117ca  lea     r9, [rsp+790h+var_720]
0x1800117cf  lea     r8, [rbp+690h+var_690]
0x1800117d3  mov     [rsp+790h+var_720], 0
0x1800117dc  xor     edx, edx
0x1800117de  mov     [rsp+790h+Token], rsi
0x1800117e3  mov     rcx, rdi
0x1800117e6  mov     rax, [rax+50h]
0x1800117ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117ef  test    eax, eax
0x1800117f1  jnz     short loc_180011801
0x1800117f3  mov     rdi, [rsp+790h+var_720]
0x1800117f8  test    rdi, rdi
0x1800117fb  jnz     loc_180011AB1
0x180011801  mov     r13d, [rbp+690h+arg_30]
0x180011808  mov     rdx, r14; struct IHttpFileInfo **
0x18001180b  mov     r9, [rbp+690h+arg_20]; unsigned __int16 *
0x180011812  mov     r8, [rbp+690h+var_700]; void *
0x180011816  mov     [rsp+790h+var_768], r13d; int
0x18001181b  mov     [rsp+790h+Token], r15; Token
0x180011820  mov     r15, [rsp+790h+var_718]
0x180011825  mov     rcx, r15; unsigned __int16 *
0x180011828  call    ?GetFileInfo@W3_FILE_INFO@@SAJPEBGPEAPEAVIHttpFileInfo@@PEAX02HPEBU_GUID@@@Z; W3_FILE_INFO::GetFileInfo(ushort const *,IHttpFileInfo * *,void *,ushort const *,void *,int,_GUID const *)
0x18001182d  mov     ebx, eax
0x18001182f  test    eax, eax
0x180011831  js      loc_180011B28
0x180011837  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18001183e  xorps   xmm0, xmm0
0x180011841  mov     [rsp+790h+var_740], rax
0x180011846  lea     rdx, [rsp+790h+var_740]
0x18001184b  mov     rax, [rsi]
0x18001184e  mov     rcx, rsi
0x180011851  movdqu  [rsp+790h+var_738], xmm0
0x180011857  mov     rax, [rax]
0x18001185a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001185f  test    eax, eax
0x180011861  js      short loc_18001186E
0x180011863  cmp     dword ptr [rsp+790h+var_738+4], 4
0x180011868  jnb     loc_180011B32
0x18001186e  test    r13d, r13d
0x180011871  jnz     loc_180011940
0x180011877  xor     ebx, ebx
0x180011879  mov     r12d, ebx
0x18001187c  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180011883  xorps   xmm0, xmm0
0x180011886  mov     [rsp+790h+var_740], rax
0x18001188b  lea     rdx, [rsp+790h+var_740]
0x180011890  mov     rax, [rsi]
0x180011893  mov     rcx, rsi
0x180011896  movdqu  [rsp+790h+var_738], xmm0
0x18001189c  mov     rax, [rax]
0x18001189f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118a4  test    eax, eax
0x1800118a6  js      short loc_1800118B3
0x1800118a8  cmp     dword ptr [rsp+790h+var_738+4], 4
0x1800118ad  jnb     loc_180011BAB
0x1800118b3  lea     rcx, [rbp+690h+var_6F8]
0x1800118b7  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800118be  nop     dword ptr [rax+rax+00h]
0x1800118c3  lea     rcx, [rbp+690h+var_6C8]
0x1800118c7  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800118ce  nop     dword ptr [rax+rax+00h]
0x1800118d3  lea     rcx, [rbp+690h+var_688]
0x1800118d7  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800118de  nop     dword ptr [rax+rax+00h]
0x1800118e3  mov     eax, ebx
0x1800118e5  mov     rcx, [rbp+690h+var_50]
0x1800118ec  xor     rcx, rsp; StackCookie
0x1800118ef  call    __security_check_cookie
0x1800118f4  add     rsp, 758h
0x1800118fb  pop     r15
0x1800118fd  pop     r14
0x1800118ff  pop     r13
0x180011901  pop     r12
0x180011903  pop     rdi
0x180011904  pop     rsi
0x180011905  pop     rbx
0x180011906  pop     rbp
0x180011907  retn
0x180011909  lea     rcx, [rbp+690h+var_6F8]
0x18001190d  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180011914  nop     dword ptr [rax+rax+00h]
0x180011919  lea     rcx, [rbp+690h+var_6C8]
0x18001191d  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180011924  nop     dword ptr [rax+rax+00h]
0x180011929  lea     rcx, [rbp+690h+var_688]
0x18001192d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180011934  nop     dword ptr [rax+rax+00h]
0x180011939  mov     eax, 80070057h
0x18001193e  jmp     short loc_1800118E5
0x180011940  mov     rcx, [r14]
0x180011943  test    rcx, rcx
0x180011946  jz      loc_180011877
0x18001194c  mov     rax, [rcx]
0x18001194f  mov     rax, [rax+38h]
0x180011953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011958  bt      eax, 0Eh
0x18001195c  jb      loc_180011877
0x180011962  mov     rax, [r14]
0x180011965  lea     r9, [rsp+790h+var_720]
0x18001196a  mov     rcx, [rbp+690h+var_710]
0x18001196e  lea     r8, [rbp+690h+var_690]
0x180011972  mov     [rsp+790h+var_720], rax
0x180011977  mov     edx, 1
0x18001197c  mov     [rsp+790h+Token], rsi
0x180011981  mov     rax, [rcx]
0x180011984  mov     rax, [rax+50h]
0x180011988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001198d  mov     rax, [rsp+790h+var_720]
0x180011992  mov     [r14], rax
0x180011995  mov     dword ptr [rsp+790h+var_724], 1
0x18001199d  jmp     loc_180011877
0x1800119a2  mov     rax, [rdi]
0x1800119a5  mov     rcx, rdi
0x1800119a8  mov     rax, [rax+0B8h]
0x1800119af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119b4  mov     rsi, rax
0x1800119b7  jmp     loc_1800116E6
0x1800119bc  cmp     dword ptr [rsp+790h+var_738+8], r12d
0x1800119c1  jz      loc_18001171D
0x1800119c7  cmp     dword ptr [rsp+790h+var_738], 80h
0x1800119cf  jz      short loc_1800119FD
0x1800119d1  test    byte ptr [rsp+790h+var_738], 80h
0x1800119d6  jnz     short loc_1800119FD
0x1800119d8  jmp     loc_18001171D
0x1800119dd  cmp     dword ptr [rsp+790h+var_738+8], r12d
0x1800119e2  jz      loc_180011754
0x1800119e8  cmp     dword ptr [rsp+790h+var_738], 80h
0x1800119f0  jz      short loc_1800119FD
0x1800119f2  test    byte ptr [rsp+790h+var_738], 80h
0x1800119f7  jz      loc_180011754
0x1800119fd  test    r15, r15
0x180011a00  jz      short loc_180011A07
0x180011a02  mov     rcx, r15
0x180011a05  jmp     short loc_180011A13
0x180011a07  test    r13, r13
0x180011a0a  jz      loc_180011754
0x180011a10  mov     rcx, r13
0x180011a13  lea     r8, [rbp+690h+var_6F8]
0x180011a17  lea     rdx, [rbp+690h+var_6C8]
0x180011a1b  call    cs:__imp_?LookupTokenAccountName@@YAJPEAXPEAVBUFFER@@1@Z; LookupTokenAccountName(void *,BUFFER *,BUFFER *)
0x180011a22  nop     dword ptr [rax+rax+00h]
0x180011a27  mov     r12d, eax
0x180011a2a  jmp     loc_180011754
0x180011a2f  cmp     dword ptr [rsp+790h+var_738+8], 0
0x180011a34  jz      loc_18001178B
0x180011a3a  cmp     dword ptr [rsp+790h+var_738], 80h
0x180011a42  jz      short loc_180011A4F
0x180011a44  test    byte ptr [rsp+790h+var_738], 80h
0x180011a49  jz      loc_18001178B
0x180011a4f  test    r12d, r12d
0x180011a52  js      loc_18001178B
0x180011a58  lea     rcx, [rbp+690h+var_6F8]
0x180011a5c  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180011a63  nop     dword ptr [rax+rax+00h]
0x180011a68  lea     rcx, [rbp+690h+var_6C8]
0x180011a6c  mov     rdi, rax
0x180011a6f  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180011a76  nop     dword ptr [rax+rax+00h]
0x180011a7b  mov     rcx, [rsi]
0x180011a7e  mov     rbx, rax
0x180011a81  mov     rax, [rcx+18h]
0x180011a85  mov     rcx, rsi
0x180011a88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a8d  mov     r9, rbx; unsigned __int16 *
0x180011a90  mov     [rsp+790h+Token], rdi; unsigned __int16 *
0x180011a95  mov     rbx, [rsp+790h+var_718]
0x180011a9a  mov     rdx, rax; struct _GUID *
0x180011a9d  mov     r8, rbx; unsigned __int16 *
0x180011aa0  mov     rcx, rsi; struct IHttpTraceContext *
0x180011aa3  call    ?RaiseEvent@FILE_CACHE_ACCESS_START@IISCacheEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBG22@Z; IISCacheEvents::FILE_CACHE_ACCESS_START::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *,ushort const *,ushort const *)
0x180011aa8  mov     rdi, [rbp+690h+var_710]
0x180011aac  jmp     loc_18001178B
0x180011ab1  mov     rax, [rdi]
0x180011ab4  test    r15, r15
0x180011ab7  mov     rdx, r15
0x180011aba  mov     rcx, rdi
  ... truncated ...
```
