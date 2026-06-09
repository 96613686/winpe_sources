# LOCATOR::FLocateDbgPath(wchar_t const *)

- ea: `0x1800859f0`
- end: `0x180085e73`
- name: `?FLocateDbgPath@LOCATOR@@AEAA_NPEB_W@Z`
- size: `1155`
- prototype: `bool __fastcall(LOCATOR *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180085360`

## callees

- `0x180026980`
- `0x1800269f8`
- `0x1800859f0`
- `0x180085e80`
- `0x180087870`
- `0x180087c50`
- `0x180088330`
- `0x1801d6350`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180085bd7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180085bf5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180085c13`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180085ce7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180085bd7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180085bf5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180085c13`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180085ce7`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180085aba`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180085af4`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180085b0e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180085aba`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180085af4`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180085b0e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180085a4e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180085a79`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180085aa0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180085c54`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180085c7e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180085cb1`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180085a4e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180085a79`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180085aa0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180085c54`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180085c7e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180085cb1`

## string_xrefs

- `0x180085c09`: `CACHE*`
- `0x180085cdd`: `CACHE*`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall LOCATOR::FLocateDbgPath(LOCATOR *this, const wchar_t *a2)
{
  const wchar_t *v2; // rsi
  __int64 v4; // r12
  __int64 v5; // r13
  __int64 v6; // r8
  __int64 v7; // rcx
  __int64 v8; // rax
  unsigned __int64 v9; // r14
  unsigned __int64 v10; // rax
  wchar_t *v11; // rbx
  char v12; // bp
  const wchar_t *v13; // rdi
  wchar_t *v14; // rsi
  wchar_t v15; // ax
  __int16 v16; // ax
  unsigned __int64 v17; // r14
  unsigned int v19; // [rsp+50h] [rbp-C98h] BYREF
  unsigned __int64 v20; // [rsp+58h] [rbp-C90h]
  const wchar_t *v21; // [rsp+60h] [rbp-C88h]
  __int64 v22; // [rsp+68h] [rbp-C80h]
  wchar_t *v23; // [rsp+70h] [rbp-C78h]
  _WORD v24[8]; // [rsp+80h] [rbp-C68h] BYREF
  _BYTE v25[1536]; // [rsp+90h] [rbp-C58h] BYREF
  wchar_t v26[776]; // [rsp+690h] [rbp-658h] BYREF

  v22 = -2;
  v2 = a2;
  v21 = a2;
  if ( a2 )
  {
    _o_wcscpy_s(v24, 776, L"symbols\\");
    v4 = *((_QWORD *)this + 416);
    if ( v4 )
    {
      _o_wcscpy_s(v25, 768, *((_QWORD *)this + 416));
      v5 = 0;
      goto LABEL_10;
    }
LABEL_4:
    v6 = *((_QWORD *)this + 413);
    if ( v6 )
    {
      _o_wcscpy_s(v25, 768, v6);
      _o_wcscat_s(v25, 768);
      v5 = -1;
      do
        ++v5;
      while ( v24[v5] );
    }
    else
    {
      v5 = 0;
    }
    _o_wcscat_s(v25, 768);
    _o_wcscat_s(v25, 768);
LABEL_10:
    v7 = -1;
    do
      ++v7;
    while ( v24[v7] );
    v8 = -1;
    do
      ++v8;
    while ( v2[v8] );
    v9 = v7 + v8 + 2;
    v20 = v9;
    v10 = 2 * v9;
    if ( !is_mul_ok(v9, 2u) )
      v10 = -1;
    v11 = (wchar_t *)operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
    v23 = v11;
    if ( !v11 )
    {
      *(_DWORD *)this = 2;
      *((_WORD *)this + 2) = 0;
      goto LABEL_48;
    }
    v12 = 0;
    v13 = v2;
    if ( !*v2 )
      goto LABEL_45;
    while ( 1 )
    {
      v14 = v11;
      v15 = *v13;
      do
      {
        ++v13;
        if ( v15 == 59 )
          break;
        *v14++ = v15;
        v15 = *v13;
      }
      while ( *v13 );
      if ( v14 != v11 )
      {
        v12 = 0;
        *v14 = 0;
        if ( (unsigned int)_o__wcsnicmp(v11, L"SRV*", 4) && (unsigned int)_o__wcsnicmp(v11, L"SYMSRV*", 7) )
        {
          if ( (unsigned int)_o__wcsnicmp(v11, L"CACHE*", 6) )
          {
            v16 = *(v14 - 1);
            if ( v16 != 92 && v16 != 47 )
              *v14++ = 92;
            v17 = v9 - (v14 - v11);
            _o_wcscpy_s(v14, v17, v24);
            v12 = LOCATOR::FLocateDbgValidate(this, v11);
            if ( v12 )
              goto LABEL_46;
            _o_wcscpy_s(v14, v17, v25);
            v12 = LOCATOR::FLocateDbgValidate(this, v11);
            if ( v12 )
              goto LABEL_46;
            if ( v5 )
            {
              _o_wcscpy_s(v14, v17, &v24[v5]);
              v12 = LOCATOR::FLocateDbgValidate(this, v11);
              if ( v12 )
                goto LABEL_46;
            }
            v9 = v20;
            goto LABEL_45;
          }
        }
        else
        {
          _o__wcsnicmp(v11, L"CACHE*", 6);
        }
        if ( *((_QWORD *)this + 416) && !LOCATOR::FRestrictSymsrv(this) )
        {
          v19 = 0;
          if ( LOCATOR::SYMSRV::SymbolServer(
                 (LOCATOR::SYMSRV *)&LOCATOR::m_symsrv,
                 this,
                 v11,
                 *((const wchar_t **)this + 416),
                 0,
                 *((_DWORD *)this + 830),
                 *((_DWORD *)this + 829),
                 0,
                 v26,
                 &v19)
            || LOCATOR::SYMSRV::SymbolServer(
                 (LOCATOR::SYMSRV *)&LOCATOR::m_symsrv,
                 this,
                 v11,
                 *((const wchar_t **)this + 416),
                 0,
                 *((_DWORD *)this + 831),
                 *((_DWORD *)this + 829),
                 0,
                 v26,
                 &v19) )
          {
            v12 = LOCATOR::FLocateDbgValidate(this, v26);
            if ( v12 )
            {
LABEL_46:
              PSGSI1::EnumPubsByAddr::release((PSGSI1::EnumPubsByAddr *)v11);
              if ( v12 )
                return 1;
              v2 = v21;
LABEL_48:
              if ( !v4 )
                return 0;
              v4 = 0;
              goto LABEL_4;
            }
          }
          else if ( v19 == 3 )
          {
            LOCATOR::NotifyOpenDBG(this, v11, 25, 0);
          }
          else if ( v19 == 39 || v19 == 112 )
          {
            LOCATOR::NotifyOpenDBG(this, v11, 26, 0);
          }
        }
      }
LABEL_45:
      if ( !*v13 )
        goto LABEL_46;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800859f0  push    rbp
0x1800859f2  push    rsi
0x1800859f3  push    rdi
0x1800859f4  push    r12
0x1800859f6  push    r13
0x1800859f8  push    r14
0x1800859fa  push    r15
0x1800859fc  sub     rsp, 0CB0h
0x180085a03  mov     [rsp+0CE8h+var_C80], 0FFFFFFFFFFFFFFFEh
0x180085a0c  mov     [rsp+0CE8h+arg_10], rbx
0x180085a14  mov     rax, cs:__security_cookie
0x180085a1b  xor     rax, rsp
0x180085a1e  mov     [rsp+0CE8h+var_48], rax
0x180085a26  mov     rsi, rdx
0x180085a29  mov     [rsp+0CE8h+var_C88], rdx
0x180085a2e  mov     r15, rcx
0x180085a31  test    rdx, rdx
0x180085a34  jz      loc_180085E46
0x180085a3a  lea     r8, aSymbols_1; "symbols\\"
0x180085a41  mov     edx, 308h
0x180085a46  lea     rcx, [rsp+0CE8h+var_C68]
0x180085a4e  call    cs:__imp__o_wcscpy_s
0x180085a54  mov     r12, [r15+0D00h]
0x180085a5b  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180085a62  xor     edi, edi
0x180085a64  test    r12, r12
0x180085a67  jz      short loc_180085A87
0x180085a69  mov     r8, r12
0x180085a6c  mov     edx, 300h
0x180085a71  lea     rcx, [rsp+0CE8h+var_C58]
0x180085a79  call    cs:__imp__o_wcscpy_s
0x180085a7f  mov     r13d, edi
0x180085a82  jmp     loc_180085B14
0x180085a87  mov     r8, [r15+0CE8h]
0x180085a8e  test    r8, r8
0x180085a91  jz      short loc_180085ADD
0x180085a93  mov     edx, 300h
0x180085a98  lea     rcx, [rsp+0CE8h+var_C58]
0x180085aa0  call    cs:__imp__o_wcscpy_s
0x180085aa6  lea     r8, asc_180249970; "\\"
0x180085aad  mov     edx, 300h
0x180085ab2  lea     rcx, [rsp+0CE8h+var_C58]
0x180085aba  call    cs:__imp__o_wcscat_s
0x180085ac0  lea     rax, [rsp+0CE8h+var_C68]
0x180085ac8  mov     r13, rbx
0x180085acb  nop     dword ptr [rax+rax+00h]
0x180085ad0  inc     r13
0x180085ad3  cmp     word ptr [rax+r13*2], 0
0x180085ad9  jnz     short loc_180085AD0
0x180085adb  jmp     short loc_180085AE0
0x180085add  mov     r13, rdi
0x180085ae0  lea     r8, [r15+8E8h]
0x180085ae7  mov     edx, 300h
0x180085aec  lea     rcx, [rsp+0CE8h+var_C58]
0x180085af4  call    cs:__imp__o_wcscat_s
0x180085afa  lea     r8, aDbg_0; ".dbg"
0x180085b01  mov     edx, 300h
0x180085b06  lea     rcx, [rsp+0CE8h+var_C58]
0x180085b0e  call    cs:__imp__o_wcscat_s
0x180085b14  lea     rax, [rsp+0CE8h+var_C68]
0x180085b1c  mov     rcx, rbx
0x180085b1f  nop
0x180085b20  inc     rcx
0x180085b23  cmp     word ptr [rax+rcx*2], 0
0x180085b28  jnz     short loc_180085B20
0x180085b2a  mov     rax, rbx
0x180085b2d  nop     dword ptr [rax]
0x180085b30  lea     rax, [rax+1]
0x180085b34  cmp     word ptr [rsi+rax*2], 0
0x180085b39  jnz     short loc_180085B30
0x180085b3b  lea     r14, [rax+2]
0x180085b3f  add     r14, rcx
0x180085b42  mov     [rsp+0CE8h+var_C90], r14
0x180085b47  mov     eax, 2
0x180085b4c  mul     r14
0x180085b4f  cmovb   rax, rbx
0x180085b53  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180085b5a  mov     rcx, rax; unsigned __int64
0x180085b5d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180085b62  mov     rbx, rax
0x180085b65  mov     [rsp+0CE8h+var_C78], rax
0x180085b6a  test    rax, rax
0x180085b6d  jnz     short loc_180085B80
0x180085b6f  mov     dword ptr [r15], 2
0x180085b76  mov     [r15+4], di
0x180085b7b  jmp     loc_180085E2E
0x180085b80  xor     bpl, bpl
0x180085b83  mov     rdi, rsi
0x180085b86  movzx   eax, word ptr [rsi]
0x180085b89  test    ax, ax
0x180085b8c  jz      loc_180085E0E
0x180085b92  mov     rsi, rbx
0x180085b95  movzx   eax, word ptr [rdi]
0x180085b98  nop     dword ptr [rax+rax+00000000h]
0x180085ba0  add     rdi, 2
0x180085ba4  cmp     ax, 3Bh ; ';'
0x180085ba8  jz      short loc_180085BB9
0x180085baa  mov     [rsi], ax
0x180085bad  add     rsi, 2
0x180085bb1  movzx   eax, word ptr [rdi]
0x180085bb4  test    ax, ax
0x180085bb7  jnz     short loc_180085BA0
0x180085bb9  cmp     rsi, rbx
0x180085bbc  jz      loc_180085E0E
0x180085bc2  xor     ebp, ebp
0x180085bc4  mov     [rsi], bp
0x180085bc7  mov     r8d, 4
0x180085bcd  lea     rdx, aSrv_2; "SRV*"
0x180085bd4  mov     rcx, rbx
0x180085bd7  call    cs:__imp__o__wcsnicmp
0x180085bdd  test    eax, eax
0x180085bdf  jz      loc_180085CD7
0x180085be5  mov     r8d, 7
0x180085beb  lea     rdx, aSymsrv_0; "SYMSRV*"
0x180085bf2  mov     rcx, rbx
0x180085bf5  call    cs:__imp__o__wcsnicmp
0x180085bfb  test    eax, eax
0x180085bfd  jz      loc_180085CD7
0x180085c03  mov     r8d, 6
0x180085c09  lea     rdx, aCache; "CACHE*"
0x180085c10  mov     rcx, rbx
0x180085c13  call    cs:__imp__o__wcsnicmp
0x180085c19  test    eax, eax
0x180085c1b  jz      loc_180085CED
0x180085c21  movzx   eax, word ptr [rsi-2]
0x180085c25  cmp     ax, 5Ch ; '\'
0x180085c29  jz      short loc_180085C3A
0x180085c2b  cmp     ax, 2Fh ; '/'
0x180085c2f  jz      short loc_180085C3A
0x180085c31  mov     word ptr [rsi], 5Ch ; '\'
0x180085c36  add     rsi, 2
0x180085c3a  mov     rax, rsi
0x180085c3d  sub     rax, rbx
0x180085c40  sar     rax, 1
0x180085c43  sub     r14, rax
0x180085c46  lea     r8, [rsp+0CE8h+var_C68]
0x180085c4e  mov     rdx, r14
0x180085c51  mov     rcx, rsi
0x180085c54  call    cs:__imp__o_wcscpy_s
0x180085c5a  mov     rdx, rbx; wchar_t *
0x180085c5d  mov     rcx, r15; this
0x180085c60  call    ?FLocateDbgValidate@LOCATOR@@AEAA_NPEB_W@Z; LOCATOR::FLocateDbgValidate(wchar_t const *)
0x180085c65  movzx   ebp, al
0x180085c68  test    al, al
0x180085c6a  jnz     loc_180085E1A
0x180085c70  lea     r8, [rsp+0CE8h+var_C58]
0x180085c78  mov     rdx, r14
0x180085c7b  mov     rcx, rsi
0x180085c7e  call    cs:__imp__o_wcscpy_s
0x180085c84  mov     rdx, rbx; wchar_t *
0x180085c87  mov     rcx, r15; this
0x180085c8a  call    ?FLocateDbgValidate@LOCATOR@@AEAA_NPEB_W@Z; LOCATOR::FLocateDbgValidate(wchar_t const *)
0x180085c8f  movzx   ebp, al
0x180085c92  test    al, al
0x180085c94  jnz     loc_180085E1A
0x180085c9a  test    r13, r13
0x180085c9d  jz      short loc_180085CCD
0x180085c9f  lea     r8, [rsp+0CE8h+var_C68]
0x180085ca7  lea     r8, [r8+r13*2]
0x180085cab  mov     rdx, r14
0x180085cae  mov     rcx, rsi
0x180085cb1  call    cs:__imp__o_wcscpy_s
0x180085cb7  mov     rdx, rbx; wchar_t *
0x180085cba  mov     rcx, r15; this
0x180085cbd  call    ?FLocateDbgValidate@LOCATOR@@AEAA_NPEB_W@Z; LOCATOR::FLocateDbgValidate(wchar_t const *)
0x180085cc2  movzx   ebp, al
0x180085cc5  test    al, al
0x180085cc7  jnz     loc_180085E1A
0x180085ccd  mov     r14, [rsp+0CE8h+var_C90]
0x180085cd2  jmp     loc_180085E0E
0x180085cd7  mov     r8d, 6
0x180085cdd  lea     rdx, aCache; "CACHE*"
0x180085ce4  mov     rcx, rbx
0x180085ce7  call    cs:__imp__o__wcsnicmp
0x180085ced  cmp     [r15+0D00h], rbp
0x180085cf4  jz      loc_180085E0E
0x180085cfa  mov     rcx, r15; this
0x180085cfd  call    ?FRestrictSymsrv@LOCATOR@@AEAA_NXZ; LOCATOR::FRestrictSymsrv(void)
0x180085d02  test    al, al
0x180085d04  jnz     loc_180085E0E
0x180085d0a  mov     [rsp+0CE8h+var_C98], ebp
0x180085d0e  lea     rax, [rsp+0CE8h+var_C98]
0x180085d13  mov     [rsp+0CE8h+var_CA0], rax; unsigned int *
0x180085d18  lea     rax, [rsp+0CE8h+var_658]
0x180085d20  mov     [rsp+0CE8h+var_CA8], rax; wchar_t *
0x180085d25  mov     [rsp+0CE8h+var_CB0], ebp; unsigned int
0x180085d29  mov     eax, [r15+0CF4h]
0x180085d30  mov     [rsp+0CE8h+var_CB8], eax; unsigned int
0x180085d34  mov     eax, [r15+0CF8h]
0x180085d3b  mov     [rsp+0CE8h+var_CC0], eax; unsigned int
0x180085d3f  mov     [rsp+0CE8h+var_CC8], rbp; struct _GUID *
0x180085d44  mov     r9, [r15+0D00h]; wchar_t *
0x180085d4b  mov     r8, rbx; wchar_t *
0x180085d4e  mov     rdx, r15; struct LOCATOR *
0x180085d51  lea     rcx, ?m_symsrv@LOCATOR@@0VSYMSRV@1@A; this
0x180085d58  call    ?SymbolServer@SYMSRV@LOCATOR@@QEAA_NPEAV2@PEB_W1PEBU_GUID@@KKKPEA_WPEAK@Z; LOCATOR::SYMSRV::SymbolServer(LOCATOR *,wchar_t const *,wchar_t const *,_GUID const *,ulong,ulong,ulong,wchar_t *,ulong *)
0x180085d5d  test    al, al
0x180085d5f  jnz     loc_180085DF7
0x180085d65  lea     rax, [rsp+0CE8h+var_C98]
0x180085d6a  mov     [rsp+0CE8h+var_CA0], rax; unsigned int *
0x180085d6f  lea     rax, [rsp+0CE8h+var_658]
0x180085d77  mov     [rsp+0CE8h+var_CA8], rax; wchar_t *
0x180085d7c  mov     [rsp+0CE8h+var_CB0], ebp; unsigned int
0x180085d80  mov     eax, [r15+0CF4h]
0x180085d87  mov     [rsp+0CE8h+var_CB8], eax; unsigned int
0x180085d8b  mov     eax, [r15+0CFCh]
0x180085d92  mov     [rsp+0CE8h+var_CC0], eax; unsigned int
0x180085d96  mov     [rsp+0CE8h+var_CC8], rbp; struct _GUID *
0x180085d9b  mov     r9, [r15+0D00h]; wchar_t *
0x180085da2  mov     r8, rbx; wchar_t *
0x180085da5  mov     rdx, r15; struct LOCATOR *
0x180085da8  lea     rcx, ?m_symsrv@LOCATOR@@0VSYMSRV@1@A; this
0x180085daf  call    ?SymbolServer@SYMSRV@LOCATOR@@QEAA_NPEAV2@PEB_W1PEBU_GUID@@KKKPEA_WPEAK@Z; LOCATOR::SYMSRV::SymbolServer(LOCATOR *,wchar_t const *,wchar_t const *,_GUID const *,ulong,ulong,ulong,wchar_t *,ulong *)
0x180085db4  test    al, al
0x180085db6  jnz     short loc_180085DF7
0x180085db8  mov     eax, [rsp+0CE8h+var_C98]
0x180085dbc  cmp     eax, 3
0x180085dbf  jnz     short loc_180085DD7
0x180085dc1  mov     r8d, 19h
0x180085dc7  xor     r9d, r9d
0x180085dca  mov     rdx, rbx
0x180085dcd  mov     rcx, r15
0x180085dd0  call    ?NotifyOpenDBG@LOCATOR@@AEAAXPEB_WW4PDBErrors@@0@Z; LOCATOR::NotifyOpenDBG(wchar_t const *,PDBErrors,wchar_t const *)
0x180085dd5  jmp     short loc_180085E0E
0x180085dd7  cmp     eax, 27h ; '''
0x180085dda  jz      short loc_180085DE1
0x180085ddc  cmp     eax, 70h ; 'p'
0x180085ddf  jnz     short loc_180085E0E
0x180085de1  mov     r8d, 1Ah
0x180085de7  xor     r9d, r9d
0x180085dea  mov     rdx, rbx
0x180085ded  mov     rcx, r15
0x180085df0  call    ?NotifyOpenDBG@LOCATOR@@AEAAXPEB_WW4PDBErrors@@0@Z; LOCATOR::NotifyOpenDBG(wchar_t const *,PDBErrors,wchar_t const *)
0x180085df5  jmp     short loc_180085E0E
0x180085df7  lea     rdx, [rsp+0CE8h+var_658]; wchar_t *
0x180085dff  mov     rcx, r15; this
0x180085e02  call    ?FLocateDbgValidate@LOCATOR@@AEAA_NPEB_W@Z; LOCATOR::FLocateDbgValidate(wchar_t const *)
0x180085e07  movzx   ebp, al
0x180085e0a  test    al, al
0x180085e0c  jnz     short loc_180085E1A
0x180085e0e  movzx   eax, word ptr [rdi]
0x180085e11  test    ax, ax
0x180085e14  jnz     loc_180085B92
0x180085e1a  mov     rcx, rbx; this
0x180085e1d  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x180085e22  test    bpl, bpl
0x180085e25  jnz     short loc_180085E42
0x180085e27  mov     rsi, [rsp+0CE8h+var_C88]
0x180085e2c  xor     edi, edi
0x180085e2e  test    r12, r12
0x180085e31  jz      short loc_180085E46
0x180085e33  mov     r12, rdi
0x180085e36  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180085e3d  jmp     loc_180085A87
0x180085e42  mov     al, 1
0x180085e44  jmp     short loc_180085E48
0x180085e46  xor     al, al
0x180085e48  mov     rcx, [rsp+0CE8h+var_48]
0x180085e50  xor     rcx, rsp; StackCookie
0x180085e53  call    __security_check_cookie
0x180085e58  mov     rbx, [rsp+0CE8h+arg_10]
0x180085e60  add     rsp, 0CB0h
0x180085e67  pop     r15
0x180085e69  pop     r14
0x180085e6b  pop     r13
0x180085e6d  pop     r12
0x180085e6f  pop     rdi
0x180085e70  pop     rsi
0x180085e71  pop     rbp
0x180085e72  retn
```
