# LOCATOR::FLocatePdb(wchar_t const *)

- ea: `0x180086180`
- end: `0x180086807`
- name: `?FLocatePdb@LOCATOR@@QEAA_NPEB_W@Z`
- size: `1671`
- prototype: `bool __fastcall(LOCATOR *__hidden this, const wchar_t *)`
- caller_count: `3`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x1800478a0`
- `0x1800479f0`
- `0x180047b60`

## callees

- `0x180026980`
- `0x1800269f8`
- `0x18003e270`
- `0x180086180`
- `0x180086810`
- `0x180086bc0`
- `0x180086cd0`
- `0x180087080`
- `0x180087230`
- `0x180087770`
- `0x1800877f0`
- `0x1800878f0`
- `0x180087a30`
- `0x180168f90`
- `0x1801d6350`
- `0x1801d63b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x180086718`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x180086718`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18008659a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800865b4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800865d6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18008659a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800865b4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800865d6`
- `api-ms-win-crt-private-l1-1-0!_o__wmakepath_s` at `0x1800862bd`
- `api-ms-win-crt-private-l1-1-0!_o__wmakepath_s` at `0x1800862bd`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180086239`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18008628b`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800864b5`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180086239`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18008628b`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800864b5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800865ef`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008674f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800867a4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800865ef`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008674f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800867a4`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18008643d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180086453`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800864cb`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800864e1`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18008643d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180086453`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800864cb`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800864e1`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180086422`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180086646`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18008666d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800866a6`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180086422`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180086646`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18008666d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800866a6`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800867b6`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800867b6`

## string_xrefs

- `0x1800865cc`: `CACHE*`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall LOCATOR::FLocatePdb(const wchar_t **this, const wchar_t *a2)
{
  __int64 v4; // rax
  const wchar_t *v5; // rbx
  const wchar_t *v6; // rax
  __int64 v7; // rax
  const wchar_t *v8; // rax
  unsigned __int64 v9; // rax
  wchar_t *v10; // rdi
  __int64 v11; // r12
  __int64 v12; // rcx
  __int64 v13; // rax
  unsigned __int64 v14; // rax
  wchar_t *v15; // rbx
  bool v16; // r13
  wchar_t *v17; // rsi
  wchar_t v18; // ax
  bool v19; // r15
  int v20; // r12d
  wchar_t *v21; // rcx
  __int16 v22; // ax
  unsigned __int64 v23; // r15
  int v24; // esi
  const wchar_t *v25; // r8
  _WORD *v26; // rcx
  __int64 v28; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v29; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v30; // [rsp+60h] [rbp-A0h]
  unsigned __int64 v31; // [rsp+68h] [rbp-98h]
  wchar_t Drive[4]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t Dir[8]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v34[1536]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t Ext[256]; // [rsp+6A0h] [rbp+5A0h] BYREF
  wchar_t Filename[256]; // [rsp+8A0h] [rbp+7A0h] BYREF
  wchar_t v37[776]; // [rsp+AA0h] [rbp+9A0h] BYREF

  if ( !LOCATOR::FReadDebugDirInfo((LOCATOR *)this) )
    return 0;
  v4 = 284;
  if ( !*((_BYTE *)this + 3352) )
    v4 = 418;
  v5 = this[v4];
  if ( v5 && !LOCATOR::FRestrictReferencePath((LOCATOR *)this) )
  {
    _wsplitpath_s(v5, Drive, 3u, Dir, 0x100u, 0, 0, 0, 0);
    if ( !Dir[0] )
      wcscpy(Dir, L".");
    _wsplitpath_s(this[425], 0, 0, 0, 0, Filename, 0x100u, Ext, 0x100u);
    _o__wmakepath_s(v37, 776, Drive, Dir, Filename, Ext);
    if ( LOCATOR::FOpenValidate4((LOCATOR *)this, v37) )
      return 1;
  }
  if ( !*((_BYTE *)this + 3448) )
  {
    if ( !*((_BYTE *)this + 2184) )
    {
      *((_BYTE *)this + 2184) = 1;
      v6 = this[258];
      if ( v6 )
        v7 = ((__int64 (__fastcall *)(const wchar_t *, __int64))v6)(this[257], 12);
      else
        v7 = 0;
      this[274] = (const wchar_t *)v7;
    }
    v8 = this[274];
    if ( (!v8 || !((unsigned int (__fastcall *)(const wchar_t *))v8)(this[257]))
      && LOCATOR::FOpenValidate4((LOCATOR *)this, this[425]) )
    {
      return 1;
    }
  }
  if ( *((_BYTE *)this + 3448) )
    goto LABEL_71;
  if ( LOCATOR::FLocatePdbPath((LOCATOR *)this, a2) )
    return 1;
  if ( !LOCATOR::FRestrictRegistry((LOCATOR *)this) )
  {
    LOCATOR::REGISTRY::Init((LOCATOR::REGISTRY *)LOCATOR::m_registryUser);
    if ( LOCATOR::FLocatePdbPath((LOCATOR *)this, qword_1802B2800) )
      return 1;
    LOCATOR::REGISTRY::Init((LOCATOR::REGISTRY *)LOCATOR::m_registryMachine);
    if ( LOCATOR::FLocatePdbPath((LOCATOR *)this, qword_1802B2818) )
      return 1;
  }
  v31 = !LOCATOR::FRestrictSystemRoot((LOCATOR *)this) + 2LL;
  v9 = 0;
  v29 = 0;
  do
  {
    *(_QWORD *)Drive = 0;
    PDB_wdupenv_s((wchar_t **)Drive, 0, (const wchar_t *)(&LOCATOR::rgwszEnvName)[v9]);
    v10 = *(wchar_t **)Drive;
    if ( !*(_QWORD *)Drive )
      goto LABEL_68;
    _o_wcscpy_s(Dir, 776, L"symbols\\");
    if ( this[413] )
    {
      _o_wcscat_s(v34, 768);
      _o_wcscat_s(v34, 768);
      v11 = -1;
      do
        ++v11;
      while ( Dir[v11] );
      v28 = v11;
    }
    else
    {
      v28 = 0;
    }
    _wsplitpath_s(this[425], 0, 0, 0, 0, Filename, 0x100u, Ext, 0x100u);
    _o_wcscat_s(Dir, 776);
    _o_wcscat_s(Dir, 776);
    v12 = -1;
    do
      ++v12;
    while ( Dir[v12] );
    v13 = -1;
    do
      ++v13;
    while ( v10[v13] );
    v30 = v13 + 2 + v12;
    v14 = 2 * v30;
    if ( !is_mul_ok(v30, 2u) )
      v14 = -1;
    v15 = (wchar_t *)operator new[](v14, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v15 )
    {
      *(_DWORD *)this = 2;
      *((_WORD *)this + 2) = 0;
      goto LABEL_68;
    }
    v16 = 0;
    if ( !*v10 )
      goto LABEL_66;
    do
    {
      v17 = v15;
      v18 = *v10;
      do
      {
        ++v10;
        if ( v18 == 59 )
          break;
        *v17++ = v18;
        v18 = *v10;
      }
      while ( *v10 );
      if ( v17 != v15 )
      {
        *v17 = 0;
        v19 = !(unsigned int)_o__wcsnicmp(v15, L"SRV*", 4) || !(unsigned int)_o__wcsnicmp(v15, L"SYMSRV*", 7);
        v20 = _o__wcsnicmp(v15, L"CACHE*", 6);
        if ( !v20 )
        {
          v21 = (wchar_t *)this[429];
          if ( v21 )
          {
            free(v21);
            this[429] = 0;
          }
        }
        if ( v19 || !v20 )
        {
          v16 = LOCATOR::FLocatePdbSymsrv((LOCATOR *)this, v15);
          if ( v16 )
            break;
          if ( *((_WORD *)this + 1684) == 20557 )
          {
            v24 = *((_DWORD *)this + 848);
            *((_DWORD *)this + 848) = -1;
            v16 = LOCATOR::FLocatePdbSymsrv((LOCATOR *)this, v15);
            if ( v16 )
              break;
            *((_DWORD *)this + 848) = v24;
          }
          if ( !v20 )
            this[429] = (const wchar_t *)_o__wcsdup(v15 + 6);
          continue;
        }
        v22 = *(v17 - 1);
        if ( v22 != 92 && v22 != 47 )
          *v17++ = 92;
        v23 = v30 - (v17 - v15);
        _o_wcscpy_s(v17, v23, Dir);
        v16 = LOCATOR::FOpenValidate4((LOCATOR *)this, v15);
        if ( v16 )
          break;
        _o_wcscpy_s(v17, v23, v34);
        v16 = LOCATOR::FOpenValidate4((LOCATOR *)this, v15);
        if ( v16 )
          break;
        if ( v28 )
        {
          _o_wcscpy_s(v17, v23, &Dir[v28]);
          v16 = LOCATOR::FOpenValidate4((LOCATOR *)this, v15);
          if ( v16 )
            break;
        }
      }
LABEL_66:
      ;
    }
    while ( *v10 );
    PSGSI1::EnumPubsByAddr::release((PSGSI1::EnumPubsByAddr *)v15);
    if ( v16 )
    {
      free(*(void **)Drive);
      return 1;
    }
LABEL_68:
    free(*(void **)Drive);
    v9 = v29 + 1;
    v29 = v9;
  }
  while ( v9 < v31 );
  if ( !*((_BYTE *)this + 3408) || !LOCATOR::FOpenEmbeddedPortablePDB((LOCATOR *)this) )
  {
LABEL_71:
    v25 = this[425];
    *(_DWORD *)this = 4;
    v26 = (_WORD *)this + 2;
    if ( v25 )
    {
      _o_wcsncpy_s(v26, 1024, v25, -1);
      if ( (unsigned __int16)(*((_WORD *)this + 1024) + 10240) <= 0x3FFu )
        *((_WORD *)this + 1024) = 0;
    }
    else
    {
      *v26 = 0;
    }
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180086180  push    rbp
0x180086182  push    rsi
0x180086183  push    rdi
0x180086184  push    r12
0x180086186  push    r13
0x180086188  push    r14
0x18008618a  push    r15
0x18008618c  lea     rbp, [rsp-0FC0h]
0x180086194  mov     eax, 10C0h
0x180086199  call    _alloca_probe
0x18008619e  sub     rsp, rax
0x1800861a1  mov     [rsp+10F0h+var_1080], 0FFFFFFFFFFFFFFFEh
0x1800861aa  mov     [rsp+10F0h+arg_10], rbx
0x1800861b2  mov     rax, cs:__security_cookie
0x1800861b9  xor     rax, rsp
0x1800861bc  mov     [rbp+0FF0h+var_40], rax
0x1800861c3  mov     rdi, rdx
0x1800861c6  mov     r14, rcx
0x1800861c9  call    ?FReadDebugDirInfo@LOCATOR@@AEAA_NXZ; LOCATOR::FReadDebugDirInfo(void)
0x1800861ce  test    al, al
0x1800861d0  jz      loc_1800867DB
0x1800861d6  mov     eax, 8E0h
0x1800861db  mov     ecx, 0D10h
0x1800861e0  cmp     byte ptr [r14+0D18h], 0
0x1800861e8  cmovz   eax, ecx
0x1800861eb  mov     rbx, [rax+r14]
0x1800861ef  xor     r15d, r15d
0x1800861f2  test    rbx, rbx
0x1800861f5  jz      loc_1800862DA
0x1800861fb  mov     rcx, r14; this
0x1800861fe  call    ?FRestrictReferencePath@LOCATOR@@AEAA_NXZ; LOCATOR::FRestrictReferencePath(void)
0x180086203  test    al, al
0x180086205  jnz     loc_1800862DA
0x18008620b  mov     [rsp+10F0h+ExtCount], r15; ExtCount
0x180086210  mov     [rsp+10F0h+Ext], r15; Ext
0x180086215  mov     [rsp+10F0h+FilenameCount], r15; FilenameCount
0x18008621a  mov     [rsp+10F0h+Filename], r15; Filename
0x18008621f  mov     [rsp+10F0h+DirCount], 100h; DirCount
0x180086228  lea     r9, [rbp+0FF0h+Dir]; Dir
0x18008622c  mov     r8d, 3; DriveCount
0x180086232  lea     rdx, [rbp+0FF0h+Drive]; Drive
0x180086236  mov     rcx, rbx; FullPath
0x180086239  call    cs:__imp__wsplitpath_s
0x18008623f  cmp     [rbp+0FF0h+Dir], r15w
0x180086244  jnz     short loc_18008624D
0x180086246  mov     dword ptr [rbp+0FF0h+Dir], 2Eh ; '.'
0x18008624d  mov     [rsp+10F0h+ExtCount], 100h; ExtCount
0x180086256  lea     rax, [rbp+0FF0h+var_A50]
0x18008625d  mov     [rsp+10F0h+Ext], rax; Ext
0x180086262  mov     [rsp+10F0h+FilenameCount], 100h; FilenameCount
0x18008626b  lea     rax, [rbp+0FF0h+var_850]
0x180086272  mov     [rsp+10F0h+Filename], rax; Filename
0x180086277  mov     [rsp+10F0h+DirCount], r15; DirCount
0x18008627c  xor     r9d, r9d; Dir
0x18008627f  xor     r8d, r8d; DriveCount
0x180086282  xor     edx, edx; Drive
0x180086284  mov     rcx, [r14+0D48h]; FullPath
0x18008628b  call    cs:__imp__wsplitpath_s
0x180086291  lea     rax, [rbp+0FF0h+var_A50]
0x180086298  mov     [rsp+10F0h+Filename], rax
0x18008629d  lea     rax, [rbp+0FF0h+var_850]
0x1800862a4  mov     [rsp+10F0h+DirCount], rax
0x1800862a9  lea     r9, [rbp+0FF0h+Dir]
0x1800862ad  lea     r8, [rbp+0FF0h+Drive]
0x1800862b1  mov     edx, 308h
0x1800862b6  lea     rcx, [rbp+0FF0h+var_650]
0x1800862bd  call    cs:__imp__o__wmakepath_s
0x1800862c3  lea     rdx, [rbp+0FF0h+var_650]; wchar_t *
0x1800862ca  mov     rcx, r14; this
0x1800862cd  call    ?FOpenValidate4@LOCATOR@@AEAA_NPEB_W@Z; LOCATOR::FOpenValidate4(wchar_t const *)
0x1800862d2  test    al, al
0x1800862d4  jnz     loc_1800867AA
0x1800862da  cmp     [r14+0D78h], r15b
0x1800862e1  jnz     short loc_180086352
0x1800862e3  cmp     [r14+888h], r15b
0x1800862ea  jnz     short loc_18008631E
0x1800862ec  mov     byte ptr [r14+888h], 1
0x1800862f4  mov     rax, [r14+810h]
0x1800862fb  test    rax, rax
0x1800862fe  jnz     short loc_180086305
0x180086300  mov     rax, r15
0x180086303  jmp     short loc_180086317
0x180086305  mov     edx, 0Ch
0x18008630a  mov     rcx, [r14+808h]
0x180086311  call    cs:__guard_dispatch_icall_fptr
0x180086317  mov     [r14+890h], rax
0x18008631e  mov     rax, [r14+890h]
0x180086325  test    rax, rax
0x180086328  jz      short loc_18008633B
0x18008632a  mov     rcx, [r14+808h]
0x180086331  call    cs:__guard_dispatch_icall_fptr
0x180086337  test    eax, eax
0x180086339  jnz     short loc_180086352
0x18008633b  mov     rdx, [r14+0D48h]; wchar_t *
0x180086342  mov     rcx, r14; this
0x180086345  call    ?FOpenValidate4@LOCATOR@@AEAA_NPEB_W@Z; LOCATOR::FOpenValidate4(wchar_t const *)
0x18008634a  test    al, al
0x18008634c  jnz     loc_1800867AA
0x180086352  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180086359  cmp     [r14+0D78h], r15b
0x180086360  jnz     loc_180086783
0x180086366  mov     rdx, rdi; wchar_t *
0x180086369  mov     rcx, r14; this
0x18008636c  call    ?FLocatePdbPath@LOCATOR@@AEAA_NPEB_W@Z; LOCATOR::FLocatePdbPath(wchar_t const *)
0x180086371  test    al, al
0x180086373  jnz     loc_1800867AA
0x180086379  mov     rcx, r14; this
0x18008637c  call    ?FRestrictRegistry@LOCATOR@@AEAA_NXZ; LOCATOR::FRestrictRegistry(void)
0x180086381  test    al, al
0x180086383  jnz     short loc_1800863CB
0x180086385  lea     rcx, ?m_registryUser@LOCATOR@@0VREGISTRY@1@A; this
0x18008638c  call    ?Init@REGISTRY@LOCATOR@@AEAAXXZ; LOCATOR::REGISTRY::Init(void)
0x180086391  mov     rdx, cs:qword_1802B2800; wchar_t *
0x180086398  mov     rcx, r14; this
0x18008639b  call    ?FLocatePdbPath@LOCATOR@@AEAA_NPEB_W@Z; LOCATOR::FLocatePdbPath(wchar_t const *)
0x1800863a0  test    al, al
0x1800863a2  jnz     loc_1800867AA
0x1800863a8  lea     rcx, ?m_registryMachine@LOCATOR@@0VREGISTRY@1@A; this
0x1800863af  call    ?Init@REGISTRY@LOCATOR@@AEAAXXZ; LOCATOR::REGISTRY::Init(void)
0x1800863b4  mov     rdx, cs:qword_1802B2818; wchar_t *
0x1800863bb  mov     rcx, r14; this
0x1800863be  call    ?FLocatePdbPath@LOCATOR@@AEAA_NPEB_W@Z; LOCATOR::FLocatePdbPath(wchar_t const *)
0x1800863c3  test    al, al
0x1800863c5  jnz     loc_1800867AA
0x1800863cb  mov     rcx, r14; this
0x1800863ce  call    ?FRestrictSystemRoot@LOCATOR@@AEAA_NXZ; LOCATOR::FRestrictSystemRoot(void)
0x1800863d3  movzx   eax, al
0x1800863d6  xor     rax, 1
0x1800863da  add     rax, 2
0x1800863de  mov     [rsp+10F0h+var_1088], rax
0x1800863e3  mov     rax, r15
0x1800863e6  mov     [rsp+10F0h+var_1098], rax
0x1800863eb  lea     rdx, ?rgwszEnvName@LOCATOR@@0QBQEB_WB; wchar_t const * const near * const LOCATOR::rgwszEnvName
0x1800863f2  mov     qword ptr [rbp+0FF0h+Drive], r15
0x1800863f6  mov     r8, [rdx+rax*8]; wchar_t *
0x1800863fa  xor     edx, edx; unsigned __int64 *
0x1800863fc  lea     rcx, [rbp+0FF0h+Drive]; wchar_t **
0x180086400  call    ?PDB_wdupenv_s@@YAHPEAPEA_WPEA_KPEB_W@Z; PDB_wdupenv_s(wchar_t * *,unsigned __int64 *,wchar_t const *)
0x180086405  mov     rdi, qword ptr [rbp+0FF0h+Drive]
0x180086409  test    rdi, rdi
0x18008640c  jz      loc_18008674B
0x180086412  lea     r8, aSymbols_1; "symbols\\"
0x180086419  mov     edx, 308h
0x18008641e  lea     rcx, [rbp+0FF0h+Dir]
0x180086422  call    cs:__imp__o_wcscpy_s
0x180086428  mov     r8, [r14+0CE8h]
0x18008642f  test    r8, r8
0x180086432  jz      short loc_180086472
0x180086434  mov     edx, 300h
0x180086439  lea     rcx, [rbp+0FF0h+var_1050]
0x18008643d  call    cs:__imp__o_wcscat_s
0x180086443  lea     r8, asc_180249970; "\\"
0x18008644a  mov     edx, 300h
0x18008644f  lea     rcx, [rbp+0FF0h+var_1050]
0x180086453  call    cs:__imp__o_wcscat_s
0x180086459  lea     rax, [rbp+0FF0h+Dir]
0x18008645d  mov     r12, rbx
0x180086460  inc     r12
0x180086463  cmp     word ptr [rax+r12*2], 0
0x180086469  jnz     short loc_180086460
0x18008646b  mov     [rsp+10F0h+var_10A0], r12
0x180086470  jmp     short loc_180086477
0x180086472  mov     [rsp+10F0h+var_10A0], r15
0x180086477  mov     [rsp+10F0h+ExtCount], 100h; ExtCount
0x180086480  lea     rax, [rbp+0FF0h+var_A50]
0x180086487  mov     [rsp+10F0h+Ext], rax; Ext
0x18008648c  mov     [rsp+10F0h+FilenameCount], 100h; FilenameCount
0x180086495  lea     rax, [rbp+0FF0h+var_850]
0x18008649c  mov     [rsp+10F0h+Filename], rax; Filename
0x1800864a1  mov     [rsp+10F0h+DirCount], r15; DirCount
0x1800864a6  xor     r9d, r9d; Dir
0x1800864a9  xor     r8d, r8d; DriveCount
0x1800864ac  xor     edx, edx; Drive
0x1800864ae  mov     rcx, [r14+0D48h]; FullPath
0x1800864b5  call    cs:__imp__wsplitpath_s
0x1800864bb  lea     r8, [rbp+0FF0h+var_850]
0x1800864c2  mov     edx, 308h
0x1800864c7  lea     rcx, [rbp+0FF0h+Dir]
0x1800864cb  call    cs:__imp__o_wcscat_s
0x1800864d1  lea     r8, [rbp+0FF0h+var_A50]
0x1800864d8  mov     edx, 308h
0x1800864dd  lea     rcx, [rbp+0FF0h+Dir]
0x1800864e1  call    cs:__imp__o_wcscat_s
0x1800864e7  lea     rax, [rbp+0FF0h+Dir]
0x1800864eb  mov     rcx, rbx
0x1800864ee  xchg    ax, ax
0x1800864f0  inc     rcx
0x1800864f3  cmp     word ptr [rax+rcx*2], 0
0x1800864f8  jnz     short loc_1800864F0
0x1800864fa  mov     rax, rbx
0x1800864fd  nop     dword ptr [rax]
0x180086500  inc     rax
0x180086503  cmp     word ptr [rdi+rax*2], 0
0x180086508  jnz     short loc_180086500
0x18008650a  add     rax, 2
0x18008650e  add     rcx, rax
0x180086511  mov     [rsp+10F0h+var_1090], rcx
0x180086516  mov     eax, 2
0x18008651b  mul     rcx
0x18008651e  cmovb   rax, rbx
0x180086522  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180086529  mov     rcx, rax; unsigned __int64
0x18008652c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180086531  mov     rbx, rax
0x180086534  mov     [rsp+10F0h+var_1078], rax
0x180086539  test    rax, rax
0x18008653c  jnz     short loc_18008654F
0x18008653e  mov     dword ptr [r14], 2
0x180086545  mov     [r14+4], r15w
0x18008654a  jmp     loc_180086744
0x18008654f  xor     r13b, r13b
0x180086552  movzx   eax, word ptr [rdi]
0x180086555  test    ax, ax
0x180086558  jz      loc_180086728
0x18008655e  mov     rsi, rbx
0x180086561  movzx   eax, word ptr [rdi]
0x180086564  add     rdi, 2
0x180086568  cmp     ax, 3Bh ; ';'
0x18008656c  jz      short loc_18008657D
0x18008656e  mov     [rsi], ax
0x180086571  add     rsi, 2
0x180086575  movzx   eax, word ptr [rdi]
0x180086578  test    ax, ax
0x18008657b  jnz     short loc_180086564
0x18008657d  cmp     rsi, rbx
0x180086580  jz      loc_180086728
0x180086586  mov     [rsi], r15w
0x18008658a  mov     r8d, 4
0x180086590  lea     rdx, aSrv_2; "SRV*"
0x180086597  mov     rcx, rbx
0x18008659a  call    cs:__imp__o__wcsnicmp
0x1800865a0  test    eax, eax
0x1800865a2  jz      short loc_1800865C3
0x1800865a4  mov     r8d, 7
0x1800865aa  lea     rdx, aSymsrv_0; "SYMSRV*"
0x1800865b1  mov     rcx, rbx
0x1800865b4  call    cs:__imp__o__wcsnicmp
0x1800865ba  test    eax, eax
0x1800865bc  jz      short loc_1800865C3
0x1800865be  xor     r15b, r15b
0x1800865c1  jmp     short loc_1800865C6
0x1800865c3  mov     r15b, 1
0x1800865c6  mov     r8d, 6
0x1800865cc  lea     rdx, aCache; "CACHE*"
0x1800865d3  mov     rcx, rbx
0x1800865d6  call    cs:__imp__o__wcsnicmp
0x1800865dc  mov     r12d, eax
0x1800865df  test    eax, eax
0x1800865e1  jnz     short loc_180086600
0x1800865e3  mov     rcx, [r14+0D68h]; Block
0x1800865ea  test    rcx, rcx
0x1800865ed  jz      short loc_180086600
0x1800865ef  call    cs:__imp_free
0x1800865f5  mov     qword ptr [r14+0D68h], 0
0x180086600  test    r15b, r15b
0x180086603  jnz     loc_1800866C1
0x180086609  test    r12d, r12d
0x18008660c  jz      loc_1800866C1
0x180086612  movzx   eax, word ptr [rsi-2]
0x180086616  cmp     ax, 5Ch ; '\'
0x18008661a  jz      short loc_18008662B
0x18008661c  cmp     ax, 2Fh ; '/'
0x180086620  jz      short loc_18008662B
0x180086622  mov     word ptr [rsi], 5Ch ; '\'
0x180086627  add     rsi, 2
0x18008662b  mov     rax, rsi
0x18008662e  sub     rax, rbx
0x180086631  sar     rax, 1
0x180086634  mov     r15, [rsp+10F0h+var_1090]
0x180086639  sub     r15, rax
0x18008663c  lea     r8, [rbp+0FF0h+Dir]
0x180086640  mov     rdx, r15
0x180086643  mov     rcx, rsi
0x180086646  call    cs:__imp__o_wcscpy_s
0x18008664c  mov     rdx, rbx; wchar_t *
0x18008664f  mov     rcx, r14; this
0x180086652  call    ?FOpenValidate4@LOCATOR@@AEAA_NPEB_W@Z; LOCATOR::FOpenValidate4(wchar_t const *)
0x180086657  movzx   r13d, al
0x18008665b  test    al, al
0x18008665d  jnz     loc_180086734
0x180086663  lea     r8, [rbp+0FF0h+var_1050]
0x180086667  mov     rdx, r15
0x18008666a  mov     rcx, rsi
0x18008666d  call    cs:__imp__o_wcscpy_s
0x180086673  mov     rdx, rbx; wchar_t *
0x180086676  mov     rcx, r14; this
0x180086679  call    ?FOpenValidate4@LOCATOR@@AEAA_NPEB_W@Z; LOCATOR::FOpenValidate4(wchar_t const *)
0x18008667e  movzx   r13d, al
0x180086682  test    al, al
0x180086684  jnz     loc_180086734
0x18008668a  mov     r12, [rsp+10F0h+var_10A0]
0x18008668f  test    r12, r12
0x180086692  jz      loc_180086725
0x180086698  lea     r8, [rbp+0FF0h+Dir]
0x18008669c  lea     r8, [r8+r12*2]
0x1800866a0  mov     rdx, r15
0x1800866a3  mov     rcx, rsi
0x1800866a6  call    cs:__imp__o_wcscpy_s
0x1800866ac  mov     rdx, rbx; wchar_t *
0x1800866af  mov     rcx, r14; this
  ... truncated ...
```
