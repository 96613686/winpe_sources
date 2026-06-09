# CUSTOM_ERROR_HANDLER::SetupCustomErrorFileResponse(IHttpContext *,STRU *,STRU *,STRA *)

- ea: `0x180004968`
- end: `0x180004d94`
- name: `?SetupCustomErrorFileResponse@CUSTOM_ERROR_HANDLER@@QEAAJPEAVIHttpContext@@PEAVSTRU@@1PEAVSTRA@@@Z`
- size: `1068`
- prototype: `__int64 __fastcall(const char **this, struct IHttpContext *, struct STRU *, struct STRU *, struct STRA *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x1800012c0`

## callees

- `0x1800038d0`
- `0x180004968`
- `0x180007836`
- `0x180007870`
- `0x180008010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180004ac2`
- `msvcrt!wcsrchr` at `0x180004ac2`
- `iisutil!?GetFallbackLanguage@LANG_STRING@@QEAAJPEAPEBD@Z` at `0x180004be8`
- `iisutil!?GetFallbackLanguage@LANG_STRING@@QEAAJPEAPEBD@Z` at `0x180004be8`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180004c75`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180004c75`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004d69`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004d69`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004ab6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004ad7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004ae9`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004af8`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004b3f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004b4b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004ab6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004ad7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004ae9`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004af8`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004b3f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004b4b`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180004c81`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180004c81`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180004aa0`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180004aa0`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180004b08`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180004b08`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800049f3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800049f3`

## pseudocode

```c
__int64 __fastcall CUSTOM_ERROR_HANDLER::SetupCustomErrorFileResponse(
        const char **this,
        struct IHttpContext *a2,
        struct STRU *a3,
        struct STRU *a4,
        struct STRA *a5)
{
  __int64 v9; // rax
  __int64 v10; // rbx
  void *v11; // r13
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // r12
  __int64 (__fastcall *v16)(struct IHttpContext *); // rax
  __int64 v17; // rax
  __int64 v18; // rax
  CUSTOM_ERROR_HANDLER *v19; // rbx
  const wchar_t *v20; // rax
  unsigned __int16 *v21; // rbx
  __int64 v22; // rbx
  const unsigned __int16 *v23; // rax
  int FallbackLanguage; // ebx
  __int64 (__fastcall *v25)(struct IHttpServer *, unsigned __int16 *, void *, _QWORD, unsigned __int16 *, CUSTOM_ERROR_HANDLER *, int, struct IHttpFileInfo **, __int64); // rsi
  __int64 v26; // rbx
  unsigned __int16 *v27; // rdi
  unsigned __int16 *v28; // rax
  int FileInfo; // eax
  struct IHttpTraceContext *v30; // rax
  CUSTOM_ERROR_HANDLER *v31; // rcx
  struct IHttpTraceContext *v32; // rax
  const char *v33; // rcx
  STRA *v34; // rcx
  __int64 (__fastcall *v35)(__int64, __int64, char *, _QWORD, int); // rdi
  unsigned __int16 CCH; // bx
  char *Str; // rax
  const char *v38; // rcx
  const char *v39; // rcx
  const char *v40; // rcx
  __int64 v42; // [rsp+50h] [rbp-B0h] BYREF
  struct IHttpFileInfo *v43; // [rsp+58h] [rbp-A8h] BYREF
  CUSTOM_ERROR_HANDLER *v44; // [rsp+60h] [rbp-A0h]
  char *v45; // [rsp+68h] [rbp-98h] BYREF
  __int128 v46; // [rsp+70h] [rbp-90h] BYREF
  __int128 v47; // [rsp+80h] [rbp-80h]
  STRA *v48; // [rsp+90h] [rbp-70h]
  _BYTE v49[56]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 v50[128]; // [rsp+D0h] [rbp-30h] BYREF

  v48 = a5;
  v9 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 160LL))(a2);
  v43 = 0;
  v44 = 0;
  v10 = v9;
  v11 = 0;
  memset_0(v50, 0, sizeof(v50));
  STRU::STRU((STRU *)v49, v50, 0x80u);
  v12 = *(_QWORD *)a2;
  v45 = 0;
  v13 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v12 + 32))(a2);
  v14 = *(_QWORD *)a2;
  v15 = v13;
  v42 = 0;
  v46 = 0;
  v16 = *(__int64 (__fastcall **)(struct IHttpContext *))(v14 + 48);
  v47 = 0;
  if ( v16(a2) )
  {
    v17 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 48LL))(a2);
    v11 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 32LL))(v17);
  }
  if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10) )
  {
    v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    v19 = (CUSTOM_ERROR_HANDLER *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 56LL))(v18);
    v44 = v19;
  }
  else
  {
    v19 = v44;
  }
  if ( !STRU::IsEmpty(a3) )
  {
    v30 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
    if ( (int)CUSTOM_ERROR_HANDLER::LocalizedGetFileInfo(v31, a3, this[4], a4, v11, v19, &v43, v30) >= 0 )
      goto LABEL_16;
    FallbackLanguage = LANG_STRING::GetFallbackLanguage(
                         (LANG_STRING *)CUSTOM_ERROR_HANDLER::sm_pLangString,
                         (const char **)&v45);
    if ( FallbackLanguage < 0 )
      goto LABEL_25;
    v32 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
    FileInfo = CUSTOM_ERROR_HANDLER::LocalizedGetFileInfo(v44, a3, v45, a4, v11, v44, &v43, v32);
LABEL_15:
    FallbackLanguage = FileInfo;
    if ( FileInfo < 0 )
      goto LABEL_25;
LABEL_16:
    v33 = this[1];
    if ( v33 )
      (*(void (__fastcall **)(const char *))(*(_QWORD *)v33 + 16LL))(v33);
    v34 = v48;
    this[1] = (const char *)v43;
    v43 = 0;
    v35 = *(__int64 (__fastcall **)(__int64, __int64, char *, _QWORD, int))(*(_QWORD *)v15 + 32LL);
    CCH = STRA::QueryCCH(v34);
    Str = STRA::QueryStr(v48);
    FallbackLanguage = v35(v15, 12, Str, CCH, 1);
    if ( FallbackLanguage >= 0 )
    {
      v38 = this[1];
      if ( v38 )
      {
        (*(void (__fastcall **)(const char *, __int64 *))(*(_QWORD *)v38 + 64LL))(v38, &v42);
        if ( !(*(__int64 (__fastcall **)(const char *))(*(_QWORD *)this[1] + 72LL))(this[1]) )
        {
          v40 = this[1];
          LODWORD(v46) = 1;
          *((_QWORD *)&v47 + 1) = (*(__int64 (__fastcall **)(const char *))(*(_QWORD *)v40 + 80LL))(v40);
          *(_QWORD *)&v47 = v42;
          *((_QWORD *)&v46 + 1) = 0;
          goto LABEL_24;
        }
        if ( !HIDWORD(v42) )
        {
          v39 = this[1];
          LODWORD(v46) = 0;
          *((_QWORD *)&v46 + 1) = (*(__int64 (__fastcall **)(const char *))(*(_QWORD *)v39 + 72LL))(v39);
          LODWORD(v47) = v42;
LABEL_24:
          FallbackLanguage = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64))(*(_QWORD *)v15 + 160LL))(
                               v15,
                               &v46,
                               0xFFFFFFFFLL);
          goto LABEL_25;
        }
      }
      goto LABEL_11;
    }
    goto LABEL_25;
  }
  v20 = STRU::QueryStr(a4);
  v21 = wcsrchr(v20, 0x5Cu);
  if ( !v21 || v21 == STRU::QueryStr(a4) )
  {
LABEL_11:
    FallbackLanguage = -2147024883;
    goto LABEL_25;
  }
  v22 = v21 - STRU::QueryStr(a4);
  v23 = STRU::QueryStr(a4);
  FallbackLanguage = STRU::Copy((STRU *)v49, v23, v22);
  if ( FallbackLanguage >= 0 )
  {
    v25 = *(__int64 (__fastcall **)(struct IHttpServer *, unsigned __int16 *, void *, _QWORD, unsigned __int16 *, CUSTOM_ERROR_HANDLER *, int, struct IHttpFileInfo **, __int64))(*(_QWORD *)s_pGlobalInfo + 64LL);
    v26 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 272LL))(a2);
    v27 = STRU::QueryStr((STRU *)v49);
    v28 = STRU::QueryStr(a4);
    FileInfo = v25(s_pGlobalInfo, v28, v11, 0, v27, v44, 1, &v43, v26);
    goto LABEL_15;
  }
LABEL_25:
  STRU::~STRU((STRU *)v49);
  return (unsigned int)FallbackLanguage;
}

```

## disassembly

```asm
0x180004968  push    rbp
0x18000496a  push    rbx
0x18000496b  push    rsi
0x18000496c  push    rdi
0x18000496d  push    r12
0x18000496f  push    r13
0x180004971  push    r14
0x180004973  push    r15
0x180004975  lea     rbp, [rsp-0E8h]
0x18000497d  sub     rsp, 1E8h
0x180004984  mov     rax, cs:__security_cookie
0x18000498b  xor     rax, rsp
0x18000498e  mov     [rbp+120h+var_50], rax
0x180004995  mov     rax, [rbp+120h+arg_20]
0x18000499c  mov     r14, rcx
0x18000499f  mov     [rbp+120h+var_190], rax
0x1800049a3  mov     rcx, rdx
0x1800049a6  mov     rax, [rdx]
0x1800049a9  mov     r15, r9
0x1800049ac  mov     rsi, r8
0x1800049af  mov     rdi, rdx
0x1800049b2  mov     rax, [rax+0A0h]
0x1800049b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049be  xor     ecx, ecx
0x1800049c0  mov     [rsp+220h+var_1C8], 0
0x1800049c9  mov     [rsp+220h+var_1C0], rcx
0x1800049ce  xor     edx, edx; Val
0x1800049d0  lea     rcx, [rbp+120h+var_150]; void *
0x1800049d4  mov     r8d, 100h; Size
0x1800049da  mov     rbx, rax
0x1800049dd  xor     r13d, r13d
0x1800049e0  call    memset_0
0x1800049e5  mov     r8d, 80h
0x1800049eb  lea     rdx, [rbp+120h+var_150]
0x1800049ef  lea     rcx, [rbp+120h+var_188]
0x1800049f3  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800049f9  mov     rcx, [rdi]
0x1800049fc  mov     [rsp+220h+var_1B8], r13
0x180004a01  mov     rax, [rcx+20h]
0x180004a05  mov     rcx, rdi
0x180004a08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a0d  mov     rcx, [rdi]
0x180004a10  xorps   xmm0, xmm0
0x180004a13  mov     r12, rax
0x180004a16  mov     [rsp+220h+var_1D0], r13
0x180004a1b  movups  [rsp+220h+var_1B0], xmm0
0x180004a20  mov     rax, [rcx+30h]
0x180004a24  mov     rcx, rdi
0x180004a27  movups  [rbp+120h+var_1A0], xmm0
0x180004a2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a30  test    rax, rax
0x180004a33  jz      short loc_180004A59
0x180004a35  mov     rax, [rdi]
0x180004a38  mov     rcx, rdi
0x180004a3b  mov     rax, [rax+30h]
0x180004a3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a44  mov     rdx, rax
0x180004a47  mov     rcx, [rax]
0x180004a4a  mov     rax, [rcx+20h]
0x180004a4e  mov     rcx, rdx
0x180004a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a56  mov     r13, rax
0x180004a59  mov     rcx, [rbx]
0x180004a5c  mov     rax, [rcx+10h]
0x180004a60  mov     rcx, rbx
0x180004a63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a68  test    rax, rax
0x180004a6b  jz      short loc_180004A98
0x180004a6d  mov     rcx, [rbx]
0x180004a70  mov     rax, [rcx+10h]
0x180004a74  mov     rcx, rbx
0x180004a77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a7c  mov     rdx, rax
0x180004a7f  mov     rcx, [rax]
0x180004a82  mov     rax, [rcx+38h]
0x180004a86  mov     rcx, rdx
0x180004a89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a8e  mov     rbx, rax
0x180004a91  mov     [rsp+220h+var_1C0], rax
0x180004a96  jmp     short loc_180004A9D
0x180004a98  mov     rbx, [rsp+220h+var_1C0]
0x180004a9d  mov     rcx, rsi
0x180004aa0  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x180004aa6  test    al, al
0x180004aa8  jz      loc_180004B9E
0x180004aae  mov     rcx, r15
0x180004ab1  mov     ebx, 5Ch ; '\'
0x180004ab6  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180004abc  mov     rcx, rax; Str
0x180004abf  movzx   edx, bx; Ch
0x180004ac2  call    cs:__imp_wcsrchr
0x180004ac8  mov     rbx, rax
0x180004acb  test    rax, rax
0x180004ace  jz      loc_180004B94
0x180004ad4  mov     rcx, r15
0x180004ad7  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180004add  cmp     rbx, rax
0x180004ae0  jz      loc_180004B94
0x180004ae6  mov     rcx, r15
0x180004ae9  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180004aef  sub     rbx, rax
0x180004af2  mov     rcx, r15
0x180004af5  sar     rbx, 1
0x180004af8  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180004afe  mov     r8d, ebx
0x180004b01  lea     rcx, [rbp+120h+var_188]
0x180004b05  mov     rdx, rax
0x180004b08  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180004b0e  mov     ebx, eax
0x180004b10  test    eax, eax
0x180004b12  js      loc_180004D65
0x180004b18  mov     rax, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x180004b1f  mov     rcx, rdi
0x180004b22  mov     rdx, [rax]
0x180004b25  mov     rax, [rdi]
0x180004b28  mov     rsi, [rdx+40h]
0x180004b2c  mov     rax, [rax+110h]
0x180004b33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b38  lea     rcx, [rbp+120h+var_188]
0x180004b3c  mov     rbx, rax
0x180004b3f  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180004b45  mov     rcx, r15
0x180004b48  mov     rdi, rax
0x180004b4b  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180004b51  mov     [rsp+220h+var_1E0], rbx
0x180004b56  lea     rcx, [rsp+220h+var_1C8]
0x180004b5b  mov     [rsp+220h+var_1E8], rcx
0x180004b60  mov     rdx, rax
0x180004b63  mov     rcx, [rsp+220h+var_1C0]
0x180004b68  xor     r9d, r9d
0x180004b6b  mov     dword ptr [rsp+220h+var_1F0], 1
0x180004b73  mov     r8, r13
0x180004b76  mov     [rsp+220h+var_1F8], rcx
0x180004b7b  mov     rax, rsi
0x180004b7e  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x180004b85  mov     [rsp+220h+var_200], rdi
0x180004b8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b8f  jmp     loc_180004C38
0x180004b94  mov     ebx, 8007000Dh
0x180004b99  jmp     loc_180004D65
0x180004b9e  mov     rax, [rdi]
0x180004ba1  mov     rcx, rdi
0x180004ba4  mov     rax, [rax+110h]
0x180004bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bb0  mov     r8, [r14+20h]; char *
0x180004bb4  mov     r9, r15; struct STRU *
0x180004bb7  mov     [rsp+220h+var_1E8], rax; struct IHttpTraceContext *
0x180004bbc  mov     rdx, rsi; struct STRU *
0x180004bbf  lea     rax, [rsp+220h+var_1C8]
0x180004bc4  mov     [rsp+220h+var_1F0], rax; struct IHttpFileInfo **
0x180004bc9  mov     [rsp+220h+var_1F8], rbx; void *
0x180004bce  mov     [rsp+220h+var_200], r13; void *
0x180004bd3  call    ?LocalizedGetFileInfo@CUSTOM_ERROR_HANDLER@@AEAAJPEAVSTRU@@PEBD0PEAX2PEAPEAVIHttpFileInfo@@PEAVIHttpTraceContext@@@Z; CUSTOM_ERROR_HANDLER::LocalizedGetFileInfo(STRU *,char const *,STRU *,void *,void *,IHttpFileInfo * *,IHttpTraceContext *)
0x180004bd8  test    eax, eax
0x180004bda  jns     short loc_180004C42
0x180004bdc  mov     rcx, cs:?sm_pLangString@CUSTOM_ERROR_HANDLER@@2PEAVLANG_STRING@@EA; LANG_STRING * CUSTOM_ERROR_HANDLER::sm_pLangString
0x180004be3  lea     rdx, [rsp+220h+var_1B8]
0x180004be8  call    cs:__imp_?GetFallbackLanguage@LANG_STRING@@QEAAJPEAPEBD@Z; LANG_STRING::GetFallbackLanguage(char const * *)
0x180004bee  mov     ebx, eax
0x180004bf0  test    eax, eax
0x180004bf2  js      loc_180004D65
0x180004bf8  mov     rax, [rdi]
0x180004bfb  mov     rcx, rdi
0x180004bfe  mov     rax, [rax+110h]
0x180004c05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c0a  mov     rcx, [rsp+220h+var_1C0]; this
0x180004c0f  mov     r9, r15; struct STRU *
0x180004c12  mov     r8, [rsp+220h+var_1B8]; char *
0x180004c17  mov     rdx, rsi; struct STRU *
0x180004c1a  mov     [rsp+220h+var_1E8], rax; struct IHttpTraceContext *
0x180004c1f  lea     rax, [rsp+220h+var_1C8]
0x180004c24  mov     [rsp+220h+var_1F0], rax; struct IHttpFileInfo **
0x180004c29  mov     [rsp+220h+var_1F8], rcx; void *
0x180004c2e  mov     [rsp+220h+var_200], r13; void *
0x180004c33  call    ?LocalizedGetFileInfo@CUSTOM_ERROR_HANDLER@@AEAAJPEAVSTRU@@PEBD0PEAX2PEAPEAVIHttpFileInfo@@PEAVIHttpTraceContext@@@Z; CUSTOM_ERROR_HANDLER::LocalizedGetFileInfo(STRU *,char const *,STRU *,void *,void *,IHttpFileInfo * *,IHttpTraceContext *)
0x180004c38  mov     ebx, eax
0x180004c3a  test    eax, eax
0x180004c3c  js      loc_180004D65
0x180004c42  mov     rcx, [r14+8]
0x180004c46  test    rcx, rcx
0x180004c49  jz      short loc_180004C57
0x180004c4b  mov     rax, [rcx]
0x180004c4e  mov     rax, [rax+10h]
0x180004c52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c57  mov     rax, [rsp+220h+var_1C8]
0x180004c5c  mov     rcx, [rbp+120h+var_190]
0x180004c60  mov     [r14+8], rax
0x180004c64  mov     [rsp+220h+var_1C8], 0
0x180004c6d  mov     rax, [r12]
0x180004c71  mov     rdi, [rax+20h]
0x180004c75  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180004c7b  mov     rcx, [rbp+120h+var_190]
0x180004c7f  mov     ebx, eax
0x180004c81  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180004c87  movzx   r9d, bx
0x180004c8b  mov     dword ptr [rsp+220h+var_200], 1
0x180004c93  mov     r8, rax
0x180004c96  mov     edx, 0Ch
0x180004c9b  mov     rax, rdi
0x180004c9e  mov     rcx, r12
0x180004ca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ca6  mov     ebx, eax
0x180004ca8  test    eax, eax
0x180004caa  js      loc_180004D65
0x180004cb0  mov     rcx, [r14+8]
0x180004cb4  test    rcx, rcx
0x180004cb7  jz      loc_180004B94
0x180004cbd  mov     rax, [rcx]
0x180004cc0  lea     rdx, [rsp+220h+var_1D0]
0x180004cc5  mov     rax, [rax+40h]
0x180004cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cce  mov     rcx, [r14+8]
0x180004cd2  mov     rax, [rcx]
0x180004cd5  mov     rax, [rax+48h]
0x180004cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cde  test    rax, rax
0x180004ce1  jz      short loc_180004D14
0x180004ce3  cmp     dword ptr [rsp+220h+var_1D0+4], 0
0x180004ce8  jnz     loc_180004B94
0x180004cee  mov     rcx, [r14+8]
0x180004cf2  mov     dword ptr [rsp+220h+var_1B0], 0
0x180004cfa  mov     rax, [rcx]
0x180004cfd  mov     rax, [rax+48h]
0x180004d01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d06  mov     qword ptr [rsp+220h+var_1B0+8], rax
0x180004d0b  mov     eax, dword ptr [rsp+220h+var_1D0]
0x180004d0f  mov     dword ptr [rbp+120h+var_1A0], eax
0x180004d12  jmp     short loc_180004D47
0x180004d14  mov     rcx, [r14+8]
0x180004d18  mov     dword ptr [rsp+220h+var_1B0], 1
0x180004d20  mov     rax, [rcx]
0x180004d23  mov     rax, [rax+50h]
0x180004d27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d2c  mov     qword ptr [rbp+120h+var_1A0+8], rax
0x180004d30  mov     eax, dword ptr [rsp+220h+var_1D0]
0x180004d34  mov     dword ptr [rbp+120h+var_1A0], eax
0x180004d37  mov     eax, dword ptr [rsp+220h+var_1D0+4]
0x180004d3b  mov     dword ptr [rbp+120h+var_1A0+4], eax
0x180004d3e  mov     qword ptr [rsp+220h+var_1B0+8], 0
0x180004d47  mov     rax, [r12]
0x180004d4b  lea     rdx, [rsp+220h+var_1B0]
0x180004d50  or      r8d, 0FFFFFFFFh
0x180004d54  mov     rcx, r12
0x180004d57  mov     rax, [rax+0A0h]
0x180004d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d63  mov     ebx, eax
0x180004d65  lea     rcx, [rbp+120h+var_188]
0x180004d69  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004d6f  mov     eax, ebx
0x180004d71  mov     rcx, [rbp+120h+var_50]
0x180004d78  xor     rcx, rsp; StackCookie
0x180004d7b  call    __security_check_cookie
0x180004d80  add     rsp, 1E8h
0x180004d87  pop     r15
0x180004d89  pop     r14
0x180004d8b  pop     r13
0x180004d8d  pop     r12
0x180004d8f  pop     rdi
0x180004d90  pop     rsi
0x180004d91  pop     rbx
0x180004d92  pop     rbp
0x180004d93  retn
```
