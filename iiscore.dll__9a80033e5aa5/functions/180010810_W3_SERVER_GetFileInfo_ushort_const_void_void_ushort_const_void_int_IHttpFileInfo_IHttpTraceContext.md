# W3_SERVER::GetFileInfo(ushort const *,void *,void *,ushort const *,void *,int,IHttpFileInfo * *,IHttpTraceContext *)

- ea: `0x180010810`
- end: `0x180010e27`
- name: `?GetFileInfo@W3_SERVER@@UEAAJPEBGPEAX101HPEAPEAVIHttpFileInfo@@PEAVIHttpTraceContext@@@Z`
- size: `1559`
- prototype: `__int64 __fastcall(W3_SERVER *this, unsigned __int16 *, void *, void *, unsigned __int16 *, HANDLE Token, int, struct IHttpFileInfo **, struct IHttpTraceContext *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x180010810`
- `0x180010e30`
- `0x18001d66c`
- `0x18001d898`
- `0x18001da2c`
- `0x18003439a`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `msvcrt!_wcsupr` at `0x1800109e9`
- `msvcrt!_wcsupr` at `0x1800109e9`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180010ae7`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180010af1`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180010b2a`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180010b34`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180010ae7`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180010af1`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180010b2a`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180010b34`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180010afb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180010b3e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180010afb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180010b3e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800108df`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800108f1`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180010c61`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180010c6e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180010d58`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180010d65`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800108df`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800108f1`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180010c61`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180010c6e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180010d58`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180010d65`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800109e0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800109e0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800109d4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800109d4`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180010885`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180010885`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x1800108b0`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x1800108d5`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x1800108b0`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x1800108d5`
- `iisutil!LookupTokenAccountName` at `0x180010c26`
- `iisutil!LookupTokenAccountName` at `0x180010c26`

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
  int v43; // [rsp+30h] [rbp-D0h]
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
      FileInfo = W3_FILE_INFO::GetFileInfo(v49, a8, v52, a5, Token, a7);
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
    v40 = dword_1800395E4;
    if ( *a8 )
    {
      if ( (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a8 + 112LL))(*a8) )
        v40 = (const char *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a8 + 112LL))(*a8);
    }
    v41 = (const struct _GUID *)(*(__int64 (__fastcall **)(struct IHttpTraceContext *))(*(_QWORD *)v10 + 24LL))(v10);
    IISCacheEvents::FILE_CACHE_ACCESS_END::RaiseEvent(v10, v41, FileInfo >= 0, v23, v47[0], v42, v43, FileInfo, v40);
  }
  BUFFER::~BUFFER((BUFFER *)v53);
  BUFFER::~BUFFER((BUFFER *)v54);
  STRU::~STRU((STRU *)v56);
  return (unsigned int)FileInfo;
}

```

## disassembly

```asm
0x180010810  push    rbp
0x180010812  push    rbx
0x180010813  push    rsi
0x180010814  push    rdi
0x180010815  push    r12
0x180010817  push    r13
0x180010819  push    r14
0x18001081b  push    r15
0x18001081d  lea     rbp, [rsp-658h]
0x180010825  sub     rsp, 758h
0x18001082c  mov     rax, cs:__security_cookie
0x180010833  xor     rax, rsp
0x180010836  mov     [rbp+690h+var_50], rax
0x18001083d  mov     r15, [rbp+690h+arg_28]
0x180010844  lea     rax, ??_7W3_FILE_KEY@@6B@; const W3_FILE_KEY::`vftable'
0x18001084b  mov     r14, [rbp+690h+arg_38]
0x180010852  mov     r13, r8
0x180010855  mov     rsi, [rbp+690h+arg_40]
0x18001085c  mov     rbx, rdx
0x18001085f  mov     [rbp+690h+var_700], r8
0x180010863  mov     rdi, rcx
0x180010866  mov     [rsp+790h+var_718], rdx
0x18001086b  mov     r8d, 100h
0x180010871  mov     [rbp+690h+var_710], rcx
0x180010875  lea     rdx, [rbp+690h+var_650]
0x180010879  lea     rcx, [rbp+690h+var_688]
0x18001087d  mov     [rbp+690h+var_690], rax
0x180010881  mov     [rbp+690h+var_708], r9
0x180010885  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001088b  mov     r12d, 200h
0x180010891  lea     rcx, [rbp+690h+var_450]; void *
0x180010898  mov     r8d, r12d; Size
0x18001089b  xor     edx, edx; Val
0x18001089d  call    memset_0
0x1800108a2  mov     r8d, r12d
0x1800108a5  lea     rdx, [rbp+690h+var_450]
0x1800108ac  lea     rcx, [rbp+690h+var_6C8]
0x1800108b0  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x1800108b6  mov     r8d, r12d; Size
0x1800108b9  lea     rcx, [rbp+690h+var_250]; void *
0x1800108c0  xor     edx, edx; Val
0x1800108c2  call    memset_0
0x1800108c7  mov     r8d, r12d
0x1800108ca  lea     rdx, [rbp+690h+var_250]
0x1800108d1  lea     rcx, [rbp+690h+var_6F8]
0x1800108d5  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x1800108db  lea     rcx, [rbp+690h+var_6C8]
0x1800108df  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800108e5  mov     rcx, rax
0x1800108e8  xor     eax, eax
0x1800108ea  mov     [rcx], ax
0x1800108ed  lea     rcx, [rbp+690h+var_6F8]
0x1800108f1  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800108f7  mov     rcx, rax
0x1800108fa  xor     eax, eax
0x1800108fc  mov     [rcx], ax
0x1800108ff  test    rbx, rbx
0x180010902  jz      loc_180010B26
0x180010908  test    r14, r14
0x18001090b  jz      loc_180010B26
0x180010911  xor     r12d, r12d
0x180010914  mov     [rsp+790h+var_728], eax
0x180010918  mov     dword ptr [rsp+790h+var_724], eax
0x18001091c  mov     [r14], rax
0x18001091f  test    rsi, rsi
0x180010922  jz      loc_180010BAD
0x180010928  mov     rcx, [rsi]
0x18001092b  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180010932  mov     [rsp+790h+var_740], rax
0x180010937  lea     rdx, [rsp+790h+var_740]
0x18001093c  xorps   xmm0, xmm0
0x18001093f  movdqu  [rsp+790h+var_738], xmm0
0x180010945  mov     rax, [rcx]
0x180010948  mov     rcx, rsi
0x18001094b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010950  test    eax, eax
0x180010952  js      short loc_18001095F
0x180010954  cmp     dword ptr [rsp+790h+var_738+4], 4
0x180010959  jnb     loc_180010BC7
0x18001095f  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180010966  xorps   xmm0, xmm0
0x180010969  mov     [rsp+790h+var_740], rax
0x18001096e  lea     rdx, [rsp+790h+var_740]
0x180010973  mov     rax, [rsi]
0x180010976  mov     rcx, rsi
0x180010979  movdqu  [rsp+790h+var_738], xmm0
0x18001097f  mov     rax, [rax]
0x180010982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010987  test    eax, eax
0x180010989  js      short loc_180010996
0x18001098b  cmp     dword ptr [rsp+790h+var_738+4], 4
0x180010990  jnb     loc_180010BE8
0x180010996  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x18001099d  xorps   xmm0, xmm0
0x1800109a0  mov     [rsp+790h+var_740], rax
0x1800109a5  lea     rdx, [rsp+790h+var_740]
0x1800109aa  mov     rax, [rsi]
0x1800109ad  mov     rcx, rsi
0x1800109b0  movdqu  [rsp+790h+var_738], xmm0
0x1800109b6  mov     rax, [rax]
0x1800109b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109be  test    eax, eax
0x1800109c0  js      short loc_1800109CD
0x1800109c2  cmp     dword ptr [rsp+790h+var_738+4], 4
0x1800109c7  jnb     loc_180010C34
0x1800109cd  mov     rdx, rbx
0x1800109d0  lea     rcx, [rbp+690h+var_688]
0x1800109d4  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800109da  lea     rcx, [rbp+690h+var_688]
0x1800109de  mov     ebx, eax
0x1800109e0  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800109e6  mov     rcx, rax; String
0x1800109e9  call    cs:__imp__wcsupr
0x1800109ef  test    ebx, ebx
0x1800109f1  js      loc_180010D21
0x1800109f7  mov     rax, [rdi]
0x1800109fa  lea     r9, [rsp+790h+var_720]
0x1800109ff  lea     r8, [rbp+690h+var_690]
0x180010a03  mov     [rsp+790h+var_720], 0
0x180010a0c  xor     edx, edx
0x180010a0e  mov     [rsp+790h+Token], rsi
0x180010a13  mov     rcx, rdi
0x180010a16  mov     rax, [rax+50h]
0x180010a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a1f  test    eax, eax
0x180010a21  jnz     short loc_180010A31
0x180010a23  mov     rdi, [rsp+790h+var_720]
0x180010a28  test    rdi, rdi
0x180010a2b  jnz     loc_180010CAA
0x180010a31  mov     r13d, [rbp+690h+arg_30]
0x180010a38  mov     rdx, r14; struct IHttpFileInfo **
0x180010a3b  mov     r9, [rbp+690h+arg_20]; unsigned __int16 *
0x180010a42  mov     r8, [rbp+690h+var_700]; void *
0x180010a46  mov     [rsp+790h+var_768], r13d; int
0x180010a4b  mov     [rsp+790h+Token], r15; Token
0x180010a50  mov     r15, [rsp+790h+var_718]
0x180010a55  mov     rcx, r15; unsigned __int16 *
0x180010a58  call    ?GetFileInfo@W3_FILE_INFO@@SAJPEBGPEAPEAVIHttpFileInfo@@PEAX02HPEBU_GUID@@@Z; W3_FILE_INFO::GetFileInfo(ushort const *,IHttpFileInfo * *,void *,ushort const *,void *,int,_GUID const *)
0x180010a5d  mov     ebx, eax
0x180010a5f  test    eax, eax
0x180010a61  js      loc_180010D21
0x180010a67  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180010a6e  xorps   xmm0, xmm0
0x180010a71  mov     [rsp+790h+var_740], rax
0x180010a76  lea     rdx, [rsp+790h+var_740]
0x180010a7b  mov     rax, [rsi]
0x180010a7e  mov     rcx, rsi
0x180010a81  movdqu  [rsp+790h+var_738], xmm0
0x180010a87  mov     rax, [rax]
0x180010a8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a8f  test    eax, eax
0x180010a91  js      short loc_180010A9E
0x180010a93  cmp     dword ptr [rsp+790h+var_738+4], 4
0x180010a98  jnb     loc_180010D2B
0x180010a9e  test    r13d, r13d
0x180010aa1  jnz     loc_180010B4B
0x180010aa7  xor     ebx, ebx
0x180010aa9  mov     r12d, ebx
0x180010aac  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180010ab3  xorps   xmm0, xmm0
0x180010ab6  mov     [rsp+790h+var_740], rax
0x180010abb  lea     rdx, [rsp+790h+var_740]
0x180010ac0  mov     rax, [rsi]
0x180010ac3  mov     rcx, rsi
0x180010ac6  movdqu  [rsp+790h+var_738], xmm0
0x180010acc  mov     rax, [rax]
0x180010acf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ad4  test    eax, eax
0x180010ad6  js      short loc_180010AE3
0x180010ad8  cmp     dword ptr [rsp+790h+var_738+4], 4
0x180010add  jnb     loc_180010D98
0x180010ae3  lea     rcx, [rbp+690h+var_6F8]
0x180010ae7  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180010aed  lea     rcx, [rbp+690h+var_6C8]
0x180010af1  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180010af7  lea     rcx, [rbp+690h+var_688]
0x180010afb  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180010b01  mov     eax, ebx
0x180010b03  mov     rcx, [rbp+690h+var_50]
0x180010b0a  xor     rcx, rsp; StackCookie
0x180010b0d  call    __security_check_cookie
0x180010b12  add     rsp, 758h
0x180010b19  pop     r15
0x180010b1b  pop     r14
0x180010b1d  pop     r13
0x180010b1f  pop     r12
0x180010b21  pop     rdi
0x180010b22  pop     rsi
0x180010b23  pop     rbx
0x180010b24  pop     rbp
0x180010b25  retn
0x180010b26  lea     rcx, [rbp+690h+var_6F8]
0x180010b2a  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180010b30  lea     rcx, [rbp+690h+var_6C8]
0x180010b34  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180010b3a  lea     rcx, [rbp+690h+var_688]
0x180010b3e  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180010b44  mov     eax, 80070057h
0x180010b49  jmp     short loc_180010B03
0x180010b4b  mov     rcx, [r14]
0x180010b4e  test    rcx, rcx
0x180010b51  jz      loc_180010AA7
0x180010b57  mov     rax, [rcx]
0x180010b5a  mov     rax, [rax+38h]
0x180010b5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b63  bt      eax, 0Eh
0x180010b67  jb      loc_180010AA7
0x180010b6d  mov     rax, [r14]
0x180010b70  lea     r9, [rsp+790h+var_720]
0x180010b75  mov     rcx, [rbp+690h+var_710]
0x180010b79  lea     r8, [rbp+690h+var_690]
0x180010b7d  mov     [rsp+790h+var_720], rax
0x180010b82  mov     edx, 1
0x180010b87  mov     [rsp+790h+Token], rsi
0x180010b8c  mov     rax, [rcx]
0x180010b8f  mov     rax, [rax+50h]
0x180010b93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b98  mov     rax, [rsp+790h+var_720]
0x180010b9d  mov     [r14], rax
0x180010ba0  mov     dword ptr [rsp+790h+var_724], 1
0x180010ba8  jmp     loc_180010AA7
0x180010bad  mov     rax, [rdi]
0x180010bb0  mov     rcx, rdi
0x180010bb3  mov     rax, [rax+0B8h]
0x180010bba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010bbf  mov     rsi, rax
0x180010bc2  jmp     loc_180010928
0x180010bc7  cmp     dword ptr [rsp+790h+var_738+8], r12d
0x180010bcc  jz      loc_18001095F
0x180010bd2  cmp     dword ptr [rsp+790h+var_738], 80h
0x180010bda  jz      short loc_180010C08
0x180010bdc  test    byte ptr [rsp+790h+var_738], 80h
0x180010be1  jnz     short loc_180010C08
0x180010be3  jmp     loc_18001095F
0x180010be8  cmp     dword ptr [rsp+790h+var_738+8], r12d
0x180010bed  jz      loc_180010996
0x180010bf3  cmp     dword ptr [rsp+790h+var_738], 80h
0x180010bfb  jz      short loc_180010C08
0x180010bfd  test    byte ptr [rsp+790h+var_738], 80h
0x180010c02  jz      loc_180010996
0x180010c08  test    r15, r15
0x180010c0b  jz      short loc_180010C12
0x180010c0d  mov     rcx, r15
0x180010c10  jmp     short loc_180010C1E
0x180010c12  test    r13, r13
0x180010c15  jz      loc_180010996
0x180010c1b  mov     rcx, r13
0x180010c1e  lea     r8, [rbp+690h+var_6F8]
0x180010c22  lea     rdx, [rbp+690h+var_6C8]
0x180010c26  call    cs:__imp_?LookupTokenAccountName@@YAJPEAXPEAVBUFFER@@1@Z; LookupTokenAccountName(void *,BUFFER *,BUFFER *)
0x180010c2c  mov     r12d, eax
0x180010c2f  jmp     loc_180010996
0x180010c34  cmp     dword ptr [rsp+790h+var_738+8], 0
0x180010c39  jz      loc_1800109CD
0x180010c3f  cmp     dword ptr [rsp+790h+var_738], 80h
0x180010c47  jz      short loc_180010C54
0x180010c49  test    byte ptr [rsp+790h+var_738], 80h
0x180010c4e  jz      loc_1800109CD
0x180010c54  test    r12d, r12d
0x180010c57  js      loc_1800109CD
0x180010c5d  lea     rcx, [rbp+690h+var_6F8]
0x180010c61  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180010c67  lea     rcx, [rbp+690h+var_6C8]
0x180010c6b  mov     rdi, rax
0x180010c6e  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180010c74  mov     rcx, [rsi]
0x180010c77  mov     rbx, rax
0x180010c7a  mov     rax, [rcx+18h]
0x180010c7e  mov     rcx, rsi
0x180010c81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c86  mov     r9, rbx; unsigned __int16 *
0x180010c89  mov     [rsp+790h+Token], rdi; unsigned __int16 *
0x180010c8e  mov     rbx, [rsp+790h+var_718]
0x180010c93  mov     rdx, rax; struct _GUID *
0x180010c96  mov     r8, rbx; unsigned __int16 *
0x180010c99  mov     rcx, rsi; struct IHttpTraceContext *
0x180010c9c  call    ?RaiseEvent@FILE_CACHE_ACCESS_START@IISCacheEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBG22@Z; IISCacheEvents::FILE_CACHE_ACCESS_START::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *,ushort const *,ushort const *)
0x180010ca1  mov     rdi, [rbp+690h+var_710]
0x180010ca5  jmp     loc_1800109CD
0x180010caa  mov     rax, [rdi]
0x180010cad  test    r15, r15
0x180010cb0  mov     rdx, r15
0x180010cb3  mov     rcx, rdi
0x180010cb6  cmovz   rdx, r13
0x180010cba  mov     rax, [rax+0A0h]
0x180010cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cc6  mov     rdx, [rdi]
0x180010cc9  mov     rcx, rdi
0x180010ccc  test    eax, eax
0x180010cce  jz      short loc_180010CDE
0x180010cd0  mov     rax, [rdx+10h]
0x180010cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cd9  jmp     loc_180010A31
0x180010cde  mov     rax, [rdx+80h]
0x180010ce5  test    r15, r15
0x180010ce8  jnz     short loc_180010CF3
0x180010cea  mov     r8, [rbp+690h+var_708]
0x180010cee  mov     rdx, r13
0x180010cf1  jmp     short loc_180010CF9
0x180010cf3  xor     r8d, r8d
  ... truncated ...
```
