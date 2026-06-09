# LOCATOR::FLocateDbg(wchar_t const *)

- ea: `0x180085360`
- end: `0x1800859db`
- name: `?FLocateDbg@LOCATOR@@QEAA_NPEB_W@Z`
- size: `1659`
- prototype: `bool __fastcall(LOCATOR *__hidden this, const wchar_t *)`
- caller_count: `3`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x1800478a0`
- `0x1800479f0`
- `0x180047b60`

## callees

- `0x180026980`
- `0x1800269f8`
- `0x18003e270`
- `0x180085360`
- `0x1800859f0`
- `0x180085e80`
- `0x180087770`
- `0x1800877f0`
- `0x180087870`
- `0x1800878f0`
- `0x180087a30`
- `0x180087c50`
- `0x180088330`
- `0x1801d6350`
- `0x1801d63b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800856f9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180085717`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180085735`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180085805`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800856f9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180085717`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180085735`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180085805`
- `api-ms-win-crt-private-l1-1-0!_o__wmakepath_s` at `0x180085497`
- `api-ms-win-crt-private-l1-1-0!_o__wmakepath_s` at `0x180085497`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18008546b`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18008546b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180085974`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800859a9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180085974`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800859a9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800855e5`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18008561e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180085630`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800855e5`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18008561e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180085630`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18008558d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800855ac`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800855cf`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180085772`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180085799`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800857ce`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18008558d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800855ac`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800855cf`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180085772`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180085799`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800857ce`

## string_xrefs

- `0x18008572b`: `CACHE*`
- `0x1800857fb`: `CACHE*`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall LOCATOR::FLocateDbg(LOCATOR *this, const wchar_t *a2)
{
  __int64 (__fastcall *v4)(_QWORD, __int64); // rax
  __int64 v5; // rax
  unsigned int (__fastcall *v6)(_QWORD); // rax
  unsigned __int64 v8; // rax
  __int64 v9; // rbx
  _WORD *v10; // rsi
  __int64 v11; // r13
  __int64 v12; // r8
  __int64 v13; // rcx
  __int64 v14; // rax
  unsigned __int64 v15; // r14
  unsigned __int64 v16; // rax
  wchar_t *v17; // rbx
  char v18; // r15
  wchar_t *v19; // rdi
  wchar_t *v20; // rsi
  wchar_t v21; // ax
  __int16 v22; // ax
  unsigned __int64 v23; // r14
  void *Block; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v25; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v26; // [rsp+60h] [rbp-A0h]
  unsigned __int64 v27; // [rsp+68h] [rbp-98h]
  _WORD *v28; // [rsp+70h] [rbp-90h]
  unsigned __int64 v29; // [rsp+78h] [rbp-88h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  wchar_t *v31; // [rsp+88h] [rbp-78h]
  wchar_t Drive[2]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t Dir[8]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v34[1536]; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t v35[776]; // [rsp+6B0h] [rbp+5B0h] BYREF

  v30 = -2;
  if ( !*((_BYTE *)this + 2168) )
  {
    *((_BYTE *)this + 2168) = 1;
    v4 = (__int64 (__fastcall *)(_QWORD, __int64))*((_QWORD *)this + 258);
    if ( v4 )
      v5 = v4(*((_QWORD *)this + 257), 14);
    else
      v5 = 0;
    *((_QWORD *)this + 272) = v5;
  }
  v6 = (unsigned int (__fastcall *)(_QWORD))*((_QWORD *)this + 272);
  if ( v6 && v6(*((_QWORD *)this + 257)) )
    return *((_BYTE *)this + 3352);
  if ( *((_QWORD *)this + 417) )
    return 1;
  if ( !*((_BYTE *)this + 3312) )
    return *((_BYTE *)this + 3352);
  if ( LOCATOR::FRestrictReferencePath(this)
    || (_wsplitpath_s(*((const wchar_t **)this + 284), Drive, 3u, Dir, 0x100u, 0, 0, 0, 0),
        _o__wmakepath_s(v35, 776, Drive, Dir, (char *)this + 2280, L".dbg"),
        !LOCATOR::FLocateDbgValidate(this, v35)) )
  {
    if ( *((_BYTE *)this + 3448) )
    {
LABEL_70:
      *(_DWORD *)this = 18;
      *((_WORD *)this + 2) = 0;
      return 0;
    }
    if ( !LOCATOR::FLocateDbgPath(this, a2) )
    {
      if ( LOCATOR::FRestrictRegistry(this)
        || (LOCATOR::REGISTRY::Init((LOCATOR::REGISTRY *)LOCATOR::m_registryUser),
            !LOCATOR::FLocateDbgPath(this, qword_1802B2800))
        && (LOCATOR::REGISTRY::Init((LOCATOR::REGISTRY *)LOCATOR::m_registryMachine),
            !LOCATOR::FLocateDbgPath(this, qword_1802B2818)) )
      {
        v29 = !LOCATOR::FRestrictSystemRoot(this) + 2LL;
        v8 = 0;
        v27 = 0;
        v9 = -1;
        while ( 1 )
        {
          Block = 0;
          PDB_wdupenv_s((wchar_t **)&Block, 0, (const wchar_t *)(&LOCATOR::rgwszEnvName)[v8]);
          v10 = Block;
          v28 = Block;
          if ( Block )
            break;
LABEL_69:
          free(v10);
          v8 = v27 + 1;
          v27 = v8;
          if ( v8 >= v29 )
            goto LABEL_70;
        }
        _o_wcscpy_s(Dir, 776, L"symbols\\");
        v11 = *((_QWORD *)this + 416);
        if ( v11 )
        {
          _o_wcscpy_s(v34, 768, *((_QWORD *)this + 416));
          v25 = 0;
          goto LABEL_28;
        }
LABEL_22:
        v12 = *((_QWORD *)this + 413);
        if ( v12 )
        {
          _o_wcscpy_s(v34, 768, v12);
          _o_wcscat_s(v34, 768);
          do
            ++v9;
          while ( Dir[v9] );
          v25 = v9;
        }
        else
        {
          v25 = 0;
        }
        _o_wcscat_s(v34, 768);
        _o_wcscat_s(v34, 768);
LABEL_28:
        v13 = -1;
        do
          ++v13;
        while ( Dir[v13] );
        v14 = -1;
        do
          ++v14;
        while ( v10[v14] );
        v15 = v13 + v14 + 2;
        v26 = v15;
        v16 = 2 * v15;
        if ( !is_mul_ok(v15, 2u) )
          v16 = -1;
        v17 = (wchar_t *)operator new[](v16, (const struct std::nothrow_t *)&std::nothrow);
        v31 = v17;
        if ( !v17 )
        {
          *(_DWORD *)this = 2;
          *((_WORD *)this + 2) = 0;
          goto LABEL_66;
        }
        v18 = 0;
        v19 = v10;
        if ( !*v10 )
          goto LABEL_63;
        while ( 1 )
        {
          v20 = v17;
          v21 = *v19;
          do
          {
            ++v19;
            if ( v21 == 59 )
              break;
            *v20++ = v21;
            v21 = *v19;
          }
          while ( *v19 );
          if ( v20 != v17 )
          {
            v18 = 0;
            *v20 = 0;
            if ( (unsigned int)_o__wcsnicmp(v17, L"SRV*", 4) && (unsigned int)_o__wcsnicmp(v17, L"SYMSRV*", 7) )
            {
              if ( (unsigned int)_o__wcsnicmp(v17, L"CACHE*", 6) )
              {
                v22 = *(v20 - 1);
                if ( v22 != 92 && v22 != 47 )
                  *v20++ = 92;
                v23 = v15 - (v20 - v17);
                _o_wcscpy_s(v20, v23, Dir);
                v18 = LOCATOR::FLocateDbgValidate(this, v17);
                if ( v18 )
                  goto LABEL_64;
                _o_wcscpy_s(v20, v23, v34);
                v18 = LOCATOR::FLocateDbgValidate(this, v17);
                if ( v18 )
                  goto LABEL_64;
                if ( v25 )
                {
                  _o_wcscpy_s(v20, v23, &Dir[v25]);
                  v18 = LOCATOR::FLocateDbgValidate(this, v17);
                  if ( v18 )
                    goto LABEL_64;
                }
                v15 = v26;
                goto LABEL_63;
              }
            }
            else
            {
              _o__wcsnicmp(v17, L"CACHE*", 6);
            }
            if ( *((_QWORD *)this + 416) && !LOCATOR::FRestrictSymsrv(this) )
            {
              *(_DWORD *)Drive = 0;
              if ( LOCATOR::SYMSRV::SymbolServer(
                     (LOCATOR::SYMSRV *)&LOCATOR::m_symsrv,
                     this,
                     v17,
                     *((const wchar_t **)this + 416),
                     0,
                     *((_DWORD *)this + 830),
                     *((_DWORD *)this + 829),
                     0,
                     v35,
                     (unsigned int *)Drive)
                || LOCATOR::SYMSRV::SymbolServer(
                     (LOCATOR::SYMSRV *)&LOCATOR::m_symsrv,
                     this,
                     v17,
                     *((const wchar_t **)this + 416),
                     0,
                     *((_DWORD *)this + 831),
                     *((_DWORD *)this + 829),
                     0,
                     v35,
                     (unsigned int *)Drive) )
              {
                v18 = LOCATOR::FLocateDbgValidate(this, v35);
                if ( v18 )
                {
LABEL_64:
                  PSGSI1::EnumPubsByAddr::release((PSGSI1::EnumPubsByAddr *)v17);
                  if ( v18 )
                  {
                    free(Block);
                    return 1;
                  }
                  v10 = v28;
LABEL_66:
                  v9 = -1;
                  if ( !v11 )
                  {
                    v10 = Block;
                    goto LABEL_69;
                  }
                  v11 = 0;
                  goto LABEL_22;
                }
              }
              else if ( *(_DWORD *)Drive == 3 )
              {
                LOCATOR::NotifyOpenDBG(this, v17, 25, 0);
              }
              else if ( *(_DWORD *)Drive == 39 || *(_DWORD *)Drive == 112 )
              {
                LOCATOR::NotifyOpenDBG(this, v17, 26, 0);
              }
            }
          }
LABEL_63:
          if ( !*v19 )
            goto LABEL_64;
        }
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180085360  push    rbp
0x180085362  push    rsi
0x180085363  push    rdi
0x180085364  push    r12
0x180085366  push    r13
0x180085368  push    r14
0x18008536a  push    r15
0x18008536c  lea     rbp, [rsp-0BD0h]
0x180085374  sub     rsp, 0CD0h
0x18008537b  mov     [rbp+0C00h+var_C80], 0FFFFFFFFFFFFFFFEh
0x180085383  mov     [rsp+0D00h+arg_10], rbx
0x18008538b  mov     rax, cs:__security_cookie
0x180085392  xor     rax, rsp
0x180085395  mov     [rbp+0C00h+var_40], rax
0x18008539c  mov     rdi, rdx
0x18008539f  mov     r12, rcx
0x1800853a2  xor     r15d, r15d
0x1800853a5  cmp     [rcx+878h], r15b
0x1800853ac  jnz     short loc_1800853E0
0x1800853ae  mov     byte ptr [rcx+878h], 1
0x1800853b5  mov     rax, [rcx+810h]
0x1800853bc  test    rax, rax
0x1800853bf  jnz     short loc_1800853C6
0x1800853c1  mov     eax, r15d
0x1800853c4  jmp     short loc_1800853D8
0x1800853c6  mov     edx, 0Eh
0x1800853cb  mov     rcx, [rcx+808h]
0x1800853d2  call    cs:__guard_dispatch_icall_fptr
0x1800853d8  mov     [r12+880h], rax
0x1800853e0  mov     rax, [r12+880h]
0x1800853e8  test    rax, rax
0x1800853eb  jz      short loc_1800853FF
0x1800853ed  mov     rcx, [r12+808h]
0x1800853f5  call    cs:__guard_dispatch_icall_fptr
0x1800853fb  test    eax, eax
0x1800853fd  jnz     short loc_180085417
0x1800853ff  cmp     [r12+0D08h], r15
0x180085407  jnz     loc_1800859AF
0x18008540d  cmp     [r12+0CF0h], r15b
0x180085415  jnz     short loc_180085425
0x180085417  movzx   eax, byte ptr [r12+0D18h]
0x180085420  jmp     loc_1800859B1
0x180085425  mov     rcx, r12; this
0x180085428  call    ?FRestrictReferencePath@LOCATOR@@AEAA_NXZ; LOCATOR::FRestrictReferencePath(void)
0x18008542d  lea     r14, aDbg_0; ".dbg"
0x180085434  test    al, al
0x180085436  jnz     short loc_1800854B4
0x180085438  mov     [rsp+0D00h+ExtCount], r15; ExtCount
0x18008543d  mov     [rsp+0D00h+Ext], r15; Ext
0x180085442  mov     [rsp+0D00h+FilenameCount], r15; FilenameCount
0x180085447  mov     [rsp+0D00h+Filename], r15; Filename
0x18008544c  mov     [rsp+0D00h+DirCount], 100h; DirCount
0x180085455  lea     r9, [rbp+0C00h+Dir]; Dir
0x180085459  mov     r8d, 3; DriveCount
0x18008545f  lea     rdx, [rbp+0C00h+Drive]; Drive
0x180085463  mov     rcx, [r12+8E0h]; FullPath
0x18008546b  call    cs:__imp__wsplitpath_s
0x180085471  lea     rax, [r12+8E8h]
0x180085479  mov     [rsp+0D00h+Filename], r14
0x18008547e  mov     [rsp+0D00h+DirCount], rax
0x180085483  lea     r9, [rbp+0C00h+Dir]
0x180085487  lea     r8, [rbp+0C00h+Drive]
0x18008548b  mov     edx, 308h
0x180085490  lea     rcx, [rbp+0C00h+var_650]
0x180085497  call    cs:__imp__o__wmakepath_s
0x18008549d  lea     rdx, [rbp+0C00h+var_650]; wchar_t *
0x1800854a4  mov     rcx, r12; this
0x1800854a7  call    ?FLocateDbgValidate@LOCATOR@@AEAA_NPEB_W@Z; LOCATOR::FLocateDbgValidate(wchar_t const *)
0x1800854ac  test    al, al
0x1800854ae  jnz     loc_1800859AF
0x1800854b4  cmp     [r12+0D78h], r15b
0x1800854bc  jnz     loc_180085992
0x1800854c2  mov     rdx, rdi; wchar_t *
0x1800854c5  mov     rcx, r12; this
0x1800854c8  call    ?FLocateDbgPath@LOCATOR@@AEAA_NPEB_W@Z; LOCATOR::FLocateDbgPath(wchar_t const *)
0x1800854cd  test    al, al
0x1800854cf  jnz     loc_1800859AF
0x1800854d5  mov     rcx, r12; this
0x1800854d8  call    ?FRestrictRegistry@LOCATOR@@AEAA_NXZ; LOCATOR::FRestrictRegistry(void)
0x1800854dd  test    al, al
0x1800854df  jnz     short loc_180085527
0x1800854e1  lea     rcx, ?m_registryUser@LOCATOR@@0VREGISTRY@1@A; this
0x1800854e8  call    ?Init@REGISTRY@LOCATOR@@AEAAXXZ; LOCATOR::REGISTRY::Init(void)
0x1800854ed  mov     rdx, cs:qword_1802B2800; wchar_t *
0x1800854f4  mov     rcx, r12; this
0x1800854f7  call    ?FLocateDbgPath@LOCATOR@@AEAA_NPEB_W@Z; LOCATOR::FLocateDbgPath(wchar_t const *)
0x1800854fc  test    al, al
0x1800854fe  jnz     loc_1800859AF
0x180085504  lea     rcx, ?m_registryMachine@LOCATOR@@0VREGISTRY@1@A; this
0x18008550b  call    ?Init@REGISTRY@LOCATOR@@AEAAXXZ; LOCATOR::REGISTRY::Init(void)
0x180085510  mov     rdx, cs:qword_1802B2818; wchar_t *
0x180085517  mov     rcx, r12; this
0x18008551a  call    ?FLocateDbgPath@LOCATOR@@AEAA_NPEB_W@Z; LOCATOR::FLocateDbgPath(wchar_t const *)
0x18008551f  test    al, al
0x180085521  jnz     loc_1800859AF
0x180085527  mov     rcx, r12; this
0x18008552a  call    ?FRestrictSystemRoot@LOCATOR@@AEAA_NXZ; LOCATOR::FRestrictSystemRoot(void)
0x18008552f  movzx   eax, al
0x180085532  xor     rax, 1
0x180085536  add     rax, 2
0x18008553a  mov     [rsp+0D00h+var_C88], rax
0x18008553f  mov     rax, r15
0x180085542  mov     [rsp+0D00h+var_C98], rax
0x180085547  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18008554e  lea     rdx, ?rgwszEnvName@LOCATOR@@0QBQEB_WB; wchar_t const * const near * const LOCATOR::rgwszEnvName
0x180085555  mov     [rsp+0D00h+Block], r15
0x18008555a  mov     r8, [rdx+rax*8]; wchar_t *
0x18008555e  xor     edx, edx; unsigned __int64 *
0x180085560  lea     rcx, [rsp+0D00h+Block]; wchar_t **
0x180085565  call    ?PDB_wdupenv_s@@YAHPEAPEA_WPEA_KPEB_W@Z; PDB_wdupenv_s(wchar_t * *,unsigned __int64 *,wchar_t const *)
0x18008556a  mov     rsi, [rsp+0D00h+Block]
0x18008556f  mov     [rsp+0D00h+var_C90], rsi
0x180085574  test    rsi, rsi
0x180085577  jz      loc_180085971
0x18008557d  lea     r8, aSymbols_1; "symbols\\"
0x180085584  mov     edx, 308h
0x180085589  lea     rcx, [rbp+0C00h+Dir]
0x18008558d  call    cs:__imp__o_wcscpy_s
0x180085593  mov     r13, [r12+0D00h]
0x18008559b  test    r13, r13
0x18008559e  jz      short loc_1800855B9
0x1800855a0  mov     r8, r13
0x1800855a3  mov     edx, 300h
0x1800855a8  lea     rcx, [rbp+0C00h+var_C50]
0x1800855ac  call    cs:__imp__o_wcscpy_s
0x1800855b2  mov     [rsp+0D00h+var_CA8], r15
0x1800855b7  jmp     short loc_180085636
0x1800855b9  mov     r8, [r12+0CE8h]
0x1800855c1  test    r8, r8
0x1800855c4  jz      short loc_180085608
0x1800855c6  mov     edx, 300h
0x1800855cb  lea     rcx, [rbp+0C00h+var_C50]
0x1800855cf  call    cs:__imp__o_wcscpy_s
0x1800855d5  lea     r8, asc_180249970; "\\"
0x1800855dc  mov     edx, 300h
0x1800855e1  lea     rcx, [rbp+0C00h+var_C50]
0x1800855e5  call    cs:__imp__o_wcscat_s
0x1800855eb  lea     rax, [rbp+0C00h+Dir]
0x1800855ef  nop
0x1800855f0  inc     rbx
0x1800855f3  cmp     word ptr [rax+rbx*2], 0
0x1800855f8  jnz     short loc_1800855F0
0x1800855fa  mov     [rsp+0D00h+var_CA8], rbx
0x1800855ff  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180085606  jmp     short loc_18008560D
0x180085608  mov     [rsp+0D00h+var_CA8], r15
0x18008560d  lea     r8, [r12+8E8h]
0x180085615  mov     edx, 300h
0x18008561a  lea     rcx, [rbp+0C00h+var_C50]
0x18008561e  call    cs:__imp__o_wcscat_s
0x180085624  mov     r8, r14
0x180085627  mov     edx, 300h
0x18008562c  lea     rcx, [rbp+0C00h+var_C50]
0x180085630  call    cs:__imp__o_wcscat_s
0x180085636  lea     rax, [rbp+0C00h+Dir]
0x18008563a  mov     rcx, rbx
0x18008563d  nop     dword ptr [rax]
0x180085640  inc     rcx
0x180085643  cmp     word ptr [rax+rcx*2], 0
0x180085648  jnz     short loc_180085640
0x18008564a  mov     rax, rbx
0x18008564d  nop     dword ptr [rax]
0x180085650  lea     rax, [rax+1]
0x180085654  cmp     word ptr [rsi+rax*2], 0
0x180085659  jnz     short loc_180085650
0x18008565b  lea     r14, [rax+2]
0x18008565f  add     r14, rcx
0x180085662  mov     [rsp+0D00h+var_CA0], r14
0x180085667  mov     eax, 2
0x18008566c  mul     r14
0x18008566f  cmovb   rax, rbx
0x180085673  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008567a  mov     rcx, rax; unsigned __int64
0x18008567d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180085682  mov     rbx, rax
0x180085685  mov     [rbp+0C00h+var_C78], rax
0x180085689  test    rax, rax
0x18008568c  jnz     short loc_1800856A1
0x18008568e  mov     dword ptr [r12], 2
0x180085696  mov     [r12+4], r15w
0x18008569c  jmp     loc_180085951
0x1800856a1  xor     r15b, r15b
0x1800856a4  mov     rdi, rsi
0x1800856a7  movzx   eax, word ptr [rsi]
0x1800856aa  test    ax, ax
0x1800856ad  jz      loc_180085930
0x1800856b3  mov     rsi, rbx
0x1800856b6  movzx   eax, word ptr [rdi]
0x1800856b9  nop     dword ptr [rax+00000000h]
0x1800856c0  add     rdi, 2
0x1800856c4  cmp     ax, 3Bh ; ';'
0x1800856c8  jz      short loc_1800856D9
0x1800856ca  mov     [rsi], ax
0x1800856cd  add     rsi, 2
0x1800856d1  movzx   eax, word ptr [rdi]
0x1800856d4  test    ax, ax
0x1800856d7  jnz     short loc_1800856C0
0x1800856d9  cmp     rsi, rbx
0x1800856dc  jz      loc_180085930
0x1800856e2  xor     r15d, r15d
0x1800856e5  mov     [rsi], r15w
0x1800856e9  mov     r8d, 4
0x1800856ef  lea     rdx, aSrv_2; "SRV*"
0x1800856f6  mov     rcx, rbx
0x1800856f9  call    cs:__imp__o__wcsnicmp
0x1800856ff  test    eax, eax
0x180085701  jz      loc_1800857F5
0x180085707  mov     r8d, 7
0x18008570d  lea     rdx, aSymsrv_0; "SYMSRV*"
0x180085714  mov     rcx, rbx
0x180085717  call    cs:__imp__o__wcsnicmp
0x18008571d  test    eax, eax
0x18008571f  jz      loc_1800857F5
0x180085725  mov     r8d, 6
0x18008572b  lea     rdx, aCache; "CACHE*"
0x180085732  mov     rcx, rbx
0x180085735  call    cs:__imp__o__wcsnicmp
0x18008573b  test    eax, eax
0x18008573d  jz      loc_18008580B
0x180085743  movzx   eax, word ptr [rsi-2]
0x180085747  cmp     ax, 5Ch ; '\'
0x18008574b  jz      short loc_18008575C
0x18008574d  cmp     ax, 2Fh ; '/'
0x180085751  jz      short loc_18008575C
0x180085753  mov     word ptr [rsi], 5Ch ; '\'
0x180085758  add     rsi, 2
0x18008575c  mov     rax, rsi
0x18008575f  sub     rax, rbx
0x180085762  sar     rax, 1
0x180085765  sub     r14, rax
0x180085768  lea     r8, [rbp+0C00h+Dir]
0x18008576c  mov     rdx, r14
0x18008576f  mov     rcx, rsi
0x180085772  call    cs:__imp__o_wcscpy_s
0x180085778  mov     rdx, rbx; wchar_t *
0x18008577b  mov     rcx, r12; this
0x18008577e  call    ?FLocateDbgValidate@LOCATOR@@AEAA_NPEB_W@Z; LOCATOR::FLocateDbgValidate(wchar_t const *)
0x180085783  movzx   r15d, al
0x180085787  test    al, al
0x180085789  jnz     loc_18008593C
0x18008578f  lea     r8, [rbp+0C00h+var_C50]
0x180085793  mov     rdx, r14
0x180085796  mov     rcx, rsi
0x180085799  call    cs:__imp__o_wcscpy_s
0x18008579f  mov     rdx, rbx; wchar_t *
0x1800857a2  mov     rcx, r12; this
0x1800857a5  call    ?FLocateDbgValidate@LOCATOR@@AEAA_NPEB_W@Z; LOCATOR::FLocateDbgValidate(wchar_t const *)
0x1800857aa  movzx   r15d, al
0x1800857ae  test    al, al
0x1800857b0  jnz     loc_18008593C
0x1800857b6  mov     rax, [rsp+0D00h+var_CA8]
0x1800857bb  test    rax, rax
0x1800857be  jz      short loc_1800857EB
0x1800857c0  lea     r8, [rbp+0C00h+Dir]
0x1800857c4  lea     r8, [r8+rax*2]
0x1800857c8  mov     rdx, r14
0x1800857cb  mov     rcx, rsi
0x1800857ce  call    cs:__imp__o_wcscpy_s
0x1800857d4  mov     rdx, rbx; wchar_t *
0x1800857d7  mov     rcx, r12; this
0x1800857da  call    ?FLocateDbgValidate@LOCATOR@@AEAA_NPEB_W@Z; LOCATOR::FLocateDbgValidate(wchar_t const *)
0x1800857df  movzx   r15d, al
0x1800857e3  test    al, al
0x1800857e5  jnz     loc_18008593C
0x1800857eb  mov     r14, [rsp+0D00h+var_CA0]
0x1800857f0  jmp     loc_180085930
0x1800857f5  mov     r8d, 6
0x1800857fb  lea     rdx, aCache; "CACHE*"
0x180085802  mov     rcx, rbx
0x180085805  call    cs:__imp__o__wcsnicmp
0x18008580b  cmp     [r12+0D00h], r15
0x180085813  jz      loc_180085930
0x180085819  mov     rcx, r12; this
0x18008581c  call    ?FRestrictSymsrv@LOCATOR@@AEAA_NXZ; LOCATOR::FRestrictSymsrv(void)
0x180085821  test    al, al
0x180085823  jnz     loc_180085930
0x180085829  mov     dword ptr [rbp+0C00h+Drive], r15d
0x18008582d  lea     rax, [rbp+0C00h+Drive]
0x180085831  mov     [rsp+0D00h+var_CB8], rax; unsigned int *
0x180085836  lea     rax, [rbp+0C00h+var_650]
0x18008583d  mov     [rsp+0D00h+ExtCount], rax; wchar_t *
0x180085842  mov     dword ptr [rsp+0D00h+Ext], r15d; unsigned int
0x180085847  mov     eax, [r12+0CF4h]
0x18008584f  mov     dword ptr [rsp+0D00h+FilenameCount], eax; unsigned int
0x180085853  mov     eax, [r12+0CF8h]
0x18008585b  mov     dword ptr [rsp+0D00h+Filename], eax; unsigned int
0x18008585f  mov     [rsp+0D00h+DirCount], r15; struct _GUID *
0x180085864  mov     r9, [r12+0D00h]; wchar_t *
0x18008586c  mov     r8, rbx; wchar_t *
0x18008586f  mov     rdx, r12; struct LOCATOR *
0x180085872  lea     rcx, ?m_symsrv@LOCATOR@@0VSYMSRV@1@A; this
0x180085879  call    ?SymbolServer@SYMSRV@LOCATOR@@QEAA_NPEAV2@PEB_W1PEBU_GUID@@KKKPEA_WPEAK@Z; LOCATOR::SYMSRV::SymbolServer(LOCATOR *,wchar_t const *,wchar_t const *,_GUID const *,ulong,ulong,ulong,wchar_t *,ulong *)
0x18008587e  test    al, al
0x180085880  jnz     loc_180085919
0x180085886  lea     rax, [rbp+0C00h+Drive]
0x18008588a  mov     [rsp+0D00h+var_CB8], rax; unsigned int *
0x18008588f  lea     rax, [rbp+0C00h+var_650]
0x180085896  mov     [rsp+0D00h+ExtCount], rax; wchar_t *
0x18008589b  mov     dword ptr [rsp+0D00h+Ext], r15d; unsigned int
0x1800858a0  mov     eax, [r12+0CF4h]
  ... truncated ...
```
