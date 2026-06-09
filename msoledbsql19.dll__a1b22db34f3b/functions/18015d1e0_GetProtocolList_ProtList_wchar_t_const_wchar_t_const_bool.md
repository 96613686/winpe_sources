# GetProtocolList(ProtList *,wchar_t const *,wchar_t const *,bool *)

- ea: `0x18015d1e0`
- end: `0x18015d684`
- name: `?GetProtocolList@@YAKPEAVProtList@@PEB_W1PEA_N@Z`
- size: `1188`
- prototype: `unsigned int(struct ProtList *, const wchar_t *, const wchar_t *, bool *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1801a93d0`

## callees

- `0x1800013e0`
- `0x180001f70`
- `0x180002ef0`
- `0x1800030c0`
- `0x180003824`
- `0x180003d80`
- `0x18015ccd0`
- `0x18015d1e0`
- `0x1801a65e1`
- `0x1801a7780`
- `0x1801ad6a0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp_l` at `0x18015d32b`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp_l` at `0x18015d347`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp_l` at `0x18015d32b`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp_l` at `0x18015d347`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18015d2fa`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18015d2fa`
- `KERNEL32!CompareStringW` at `0x18015d375`
- `KERNEL32!CompareStringW` at `0x18015d375`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetProtocolList(struct ProtList *a1, const wchar_t *a2, const wchar_t *a3, bool *a4)
{
  wchar_t *v8; // r14
  unsigned int ProtocolDefaults; // ebx
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rax
  const wchar_t *v14; // rsi
  __int64 v15; // rcx
  struct localeinfo_struct *v16; // rax
  __int64 v17; // rcx
  struct localeinfo_struct *v18; // rax
  __int64 v19; // rax
  __int64 v20; // rdi
  _WORD *v21; // rcx
  __int64 v22; // rdx
  __int16 v23; // ax
  _WORD *v24; // rax
  unsigned int v25; // ebx
  _WORD *v26; // rcx
  __int64 v27; // rdx
  __int16 v28; // ax
  _WORD *v29; // rax
  __int64 v30; // r9
  struct ProtList *v31; // rcx
  __int64 i; // rax
  __int64 v33; // rax
  unsigned int v35; // [rsp+38h] [rbp-70h] BYREF
  __int64 v36; // [rsp+40h] [rbp-68h] BYREF
  __int64 v37; // [rsp+48h] [rbp-60h] BYREF
  __int64 v38; // [rsp+50h] [rbp-58h] BYREF

  v38 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1802668B8[0] )
    bidScopeEnterW(&v38, off_1802668B8[0], a1, a2);
  v35 = 0;
  v8 = 0;
  ProtocolDefaults = 0;
  *a4 = 0;
  if ( (unsigned int)CSgetProtocolOrder(0, (int *)&v35) || v35 < 6 )
    goto LABEL_14;
  v10 = v35 + 1;
  if ( (unsigned int)v10 < v35 )
  {
    ProtocolDefaults = -1;
    goto LABEL_61;
  }
  v11 = v10 >> 1;
  v12 = 2 * v11;
  if ( !is_mul_ok(v11, 2u) )
    v12 = -1;
  v13 = (*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 112LL))(g_pMO, v12);
  v8 = (wchar_t *)v13;
  if ( !v13 || (unsigned int)CSgetProtocolOrder(v13, (int *)&v35) )
  {
LABEL_14:
    v14 = L"sm";
    v35 = 22;
    goto LABEL_15;
  }
  v14 = v8;
  if ( !*v8 )
    goto LABEL_60;
  while ( 1 )
  {
LABEL_15:
    if ( !_wcsicmp(v14, L"sm") && (*a2 != 46 || a2[1]) )
    {
      v16 = (struct localeinfo_struct *)ImplBidTouch(v15);
      if ( _wcsicmp_l(L"(local)", a2, v16) )
      {
        v18 = (struct localeinfo_struct *)ImplBidTouch(v17);
        if ( _wcsicmp_l(L"localhost", a2, v18) )
        {
          if ( CompareStringW(0x800u, 0x20001u, &gwszComputerName, -1, a2, -1) != 2 )
          {
            *a4 = 1;
            goto LABEL_52;
          }
        }
      }
    }
    v19 = (*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)gpmo + 88LL))(gpmo, 2576);
    v20 = v19;
    if ( !v19 )
      goto LABEL_58;
    memset_0((void *)(v19 + 1544), 0, 0x400u);
    *(_DWORD *)v20 = 8;
    *(_DWORD *)(v20 + 4) = 8;
    *(_WORD *)(v20 + 8) = 0;
    *(_WORD *)(v20 + 520) = 0;
    *(_WORD *)(v20 + 1032) = 0;
    *(_QWORD *)(v20 + 2568) = 0;
    v36 = -1;
    if ( (bidGblFlags & 0x20004) == 0x20004 && `ProtElem::Init'::`7'::_bidPtrSA_040_694[0] )
      bidScopeEnterW(&v36, `ProtElem::Init'::`7'::_bidPtrSA_040_694[0], a2, a3);
    v21 = (_WORD *)(v20 + 8);
    v22 = 256;
    do
    {
      if ( v22 == -2147483390 )
        break;
      v23 = *(_WORD *)((char *)v21 + (_QWORD)((char *)a2 - v20 - 8));
      if ( !v23 )
        break;
      *v21++ = v23;
      --v22;
    }
    while ( v22 );
    v24 = v21 - 1;
    if ( v22 )
      v24 = v21;
    *v24 = 0;
    v25 = -2147024774;
    if ( v22 )
    {
      v26 = (_WORD *)(v20 + 520);
      v27 = 256;
      do
      {
        if ( v27 == -2147483390 )
          break;
        v28 = *(_WORD *)((char *)v26 + (_QWORD)((char *)a3 - v20 - 520));
        if ( !v28 )
          break;
        *v26++ = v28;
        --v27;
      }
      while ( v27 );
      v29 = v26 - 1;
      if ( v27 )
        v29 = v26;
      *v29 = 0;
      v25 = -2147024774;
      if ( v27 )
        v25 = 0;
    }
    if ( (bidGblFlags & 0x20002) == 0x20002 && `ProtElem::Init'::`19'::_bidPtrSA_030_709[0] )
      bidTraceW(`ProtElem::Init'::`19'::_bidSrcFileA[0], 726016, `ProtElem::Init'::`19'::_bidPtrSA_030_709[0], v25);
    _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v36);
    if ( v25 )
      break;
    ProtocolDefaults = GetProtocolDefaults((struct ProtElem *)v20, v14, a2);
    if ( ProtocolDefaults == -1 )
    {
      operator delete((void *)v20, 0xA10u);
      goto LABEL_59;
    }
    v37 = -1;
    if ( (bidGblFlags & 0x20004) == 0x20004 && `ProtList::AddTail'::`7'::_bidPtrSA_040_910[0] )
      bidScopeEnterW(&v37, `ProtList::AddTail'::`7'::_bidPtrSA_040_910[0], v20, v30);
    v31 = a1;
    for ( i = *(_QWORD *)a1; i; i = *(_QWORD *)(i + 2568) )
      v31 = (struct ProtList *)(i + 2568);
    *(_QWORD *)v31 = v20;
    *(_QWORD *)(v20 + 2568) = 0;
    _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v37);
LABEL_52:
    v33 = -1;
    do
      ++v33;
    while ( v14[v33] );
    v14 += (unsigned int)v33 + 1;
    if ( !*v14 )
      goto LABEL_59;
  }
  operator delete((void *)v20, 0xA10u);
LABEL_58:
  ProtocolDefaults = -1;
LABEL_59:
  if ( v8 )
LABEL_60:
    (*(void (__fastcall **)(struct ISOSHost_MemObj *, wchar_t *))(*(_QWORD *)g_pMO + 128LL))(g_pMO, v8);
LABEL_61:
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_180264128[0] )
    bidTraceW(off_180260DE0[0], 811008, off_180264128[0], ProtocolDefaults);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v38);
  return ProtocolDefaults;
}

```

## disassembly

```asm
0x18015d1e0  push    rbx
0x18015d1e2  push    rbp
0x18015d1e3  push    rsi
0x18015d1e4  push    rdi
0x18015d1e5  push    r12
0x18015d1e7  push    r13
0x18015d1e9  push    r14
0x18015d1eb  push    r15
0x18015d1ed  sub     rsp, 68h
0x18015d1f1  mov     rax, cs:__security_cookie
0x18015d1f8  xor     rax, rsp
0x18015d1fb  mov     [rsp+0A8h+var_50], rax
0x18015d200  mov     r13, r9
0x18015d203  mov     r15, r8
0x18015d206  mov     rbp, rdx
0x18015d209  mov     r12, rcx
0x18015d20c  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18015d213  mov     [rsp+0A8h+var_58], rsi
0x18015d218  mov     eax, cs:_bidGblFlags
0x18015d21e  and     eax, 20004h
0x18015d223  cmp     eax, 20004h
0x18015d228  jnz     short loc_18015D252
0x18015d22a  mov     rax, cs:off_1802668B8; "<GetProtocolList|API|SNI> pProtList: %p"...
0x18015d231  test    rax, rax
0x18015d234  jz      short loc_18015D252
0x18015d236  mov     [rsp+0A8h+lpString2], r8
0x18015d23b  mov     r9, rdx
0x18015d23e  mov     r8, rcx
0x18015d241  mov     rdx, cs:off_1802668B8; "<GetProtocolList|API|SNI> pProtList: %p"...
0x18015d248  lea     rcx, [rsp+0A8h+var_58]
0x18015d24d  call    _bidScopeEnterW
0x18015d252  xor     edi, edi
0x18015d254  mov     [rsp+0A8h+var_70], edi
0x18015d258  mov     r14d, edi
0x18015d25b  mov     ebx, edi
0x18015d25d  mov     [r13+0], bl
0x18015d261  lea     rdx, [rsp+0A8h+var_70]
0x18015d266  xor     ecx, ecx
0x18015d268  call    CSgetProtocolOrder
0x18015d26d  test    eax, eax
0x18015d26f  jnz     short loc_18015D2D9
0x18015d271  mov     eax, [rsp+0A8h+var_70]
0x18015d275  cmp     eax, 6
0x18015d278  jb      short loc_18015D2D9
0x18015d27a  lea     ecx, [rax+1]
0x18015d27d  cmp     ecx, eax
0x18015d27f  jb      short loc_18015D2CF
0x18015d281  shr     rcx, 1
0x18015d284  mov     eax, 2
0x18015d289  mul     rcx
0x18015d28c  mov     rdx, rax
0x18015d28f  cmovb   rdx, rsi
0x18015d293  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x18015d29a  mov     rax, [rcx]
0x18015d29d  mov     rax, [rax+70h]
0x18015d2a1  call    cs:__guard_dispatch_icall_fptr
0x18015d2a7  mov     r14, rax
0x18015d2aa  test    rax, rax
0x18015d2ad  jz      short loc_18015D2D9
0x18015d2af  lea     rdx, [rsp+0A8h+var_70]
0x18015d2b4  mov     rcx, rax
0x18015d2b7  call    CSgetProtocolOrder
0x18015d2bc  test    eax, eax
0x18015d2be  jnz     short loc_18015D2D9
0x18015d2c0  mov     rsi, r14
0x18015d2c3  cmp     [r14], ax
0x18015d2c7  jz      loc_18015D604
0x18015d2cd  jmp     short loc_18015D2F0
0x18015d2cf  mov     ebx, 0FFFFFFFFh
0x18015d2d4  jmp     loc_18015D61F
0x18015d2d9  lea     rsi, aSm; "sm"
0x18015d2e0  mov     [rsp+0A8h+var_70], 16h
0x18015d2e8  nop     dword ptr [rax+rax+00000000h]
0x18015d2f0  lea     rdx, aSm_0; "sm"
0x18015d2f7  mov     rcx, rsi; String1
0x18015d2fa  call    cs:__imp__wcsicmp
0x18015d300  test    eax, eax
0x18015d302  jnz     loc_18015D38A
0x18015d308  mov     eax, 2Eh ; '.'
0x18015d30d  cmp     ax, [rbp+0]
0x18015d311  jnz     short loc_18015D319
0x18015d313  cmp     di, [rbp+2]
0x18015d317  jz      short loc_18015D38A
0x18015d319  call    ImplBidTouch
0x18015d31e  mov     r8, rax; Locale
0x18015d321  mov     rdx, rbp; String2
0x18015d324  lea     rcx, aLocal; "(local)"
0x18015d32b  call    cs:__imp__wcsicmp_l
0x18015d331  test    eax, eax
0x18015d333  jz      short loc_18015D38A
0x18015d335  call    ImplBidTouch
0x18015d33a  mov     r8, rax; Locale
0x18015d33d  mov     rdx, rbp; String2
0x18015d340  lea     rcx, aLocalhost; "localhost"
0x18015d347  call    cs:__imp__wcsicmp_l
0x18015d34d  test    eax, eax
0x18015d34f  jz      short loc_18015D38A
0x18015d351  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18015d358  mov     [rsp+0A8h+cchCount2], eax; cchCount2
0x18015d35c  mov     [rsp+0A8h+lpString2], rbp; lpString2
0x18015d361  mov     r9d, eax; cchCount1
0x18015d364  lea     r8, ?gwszComputerName@@3PA_WA; lpString1
0x18015d36b  mov     edx, 20001h; dwCmpFlags
0x18015d370  mov     ecx, 800h; Locale
0x18015d375  call    cs:__imp_CompareStringW
0x18015d37b  cmp     eax, 2
0x18015d37e  jz      short loc_18015D38A
0x18015d380  mov     byte ptr [r13+0], 1
0x18015d385  jmp     loc_18015D5BA
0x18015d38a  mov     rcx, cs:?gpmo@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * gpmo
0x18015d391  mov     rax, [rcx]
0x18015d394  mov     edx, 0A10h
0x18015d399  mov     rax, [rax+58h]
0x18015d39d  call    cs:__guard_dispatch_icall_fptr
0x18015d3a3  mov     rdi, rax
0x18015d3a6  mov     [rsp+0A8h+var_78], rax
0x18015d3ab  test    rax, rax
0x18015d3ae  jz      loc_18015D5FA
0x18015d3b4  lea     rcx, [rax+608h]; void *
0x18015d3bb  xor     edx, edx; Val
0x18015d3bd  mov     r8d, 400h; Size
0x18015d3c3  call    memset_0
0x18015d3c8  mov     dword ptr [rdi], 8
0x18015d3ce  mov     dword ptr [rdi+4], 8
0x18015d3d5  xor     r9d, r9d
0x18015d3d8  mov     [rdi+8], r9w
0x18015d3dd  mov     [rdi+208h], r9w
0x18015d3e5  mov     [rdi+408h], r9w
0x18015d3ed  mov     [rdi+0A08h], r9
0x18015d3f4  test    rdi, rdi
0x18015d3f7  jz      loc_18015D5FA
0x18015d3fd  mov     [rsp+0A8h+var_68], 0FFFFFFFFFFFFFFFFh
0x18015d406  mov     eax, cs:_bidGblFlags
0x18015d40c  and     eax, 20004h
0x18015d411  cmp     eax, 20004h
0x18015d416  jnz     short loc_18015D43E
0x18015d418  mov     rax, cs:?_bidPtrSA_040_694@?6??Init@ProtElem@@QEAAKQEB_W0@Z@4REB_WEB; wchar_t const * const `ProtElem::Init(wchar_t const * const,wchar_t const * const)'::`7'::_bidPtrSA_040_694
0x18015d41f  test    rax, rax
0x18015d422  jz      short loc_18015D43E
0x18015d424  mov     r9, r15
0x18015d427  mov     r8, rbp
0x18015d42a  mov     rdx, cs:?_bidPtrSA_040_694@?6??Init@ProtElem@@QEAAKQEB_W0@Z@4REB_WEB; wchar_t const * const `ProtElem::Init(wchar_t const * const,wchar_t const * const)'::`7'::_bidPtrSA_040_694
0x18015d431  lea     rcx, [rsp+0A8h+var_68]
0x18015d436  call    _bidScopeEnterW
0x18015d43b  xor     r9d, r9d
0x18015d43e  lea     rcx, [rdi+8]
0x18015d442  mov     edx, 100h
0x18015d447  mov     r8, rbp
0x18015d44a  sub     r8, rcx
0x18015d44d  nop     dword ptr [rax]
0x18015d450  lea     rax, [rdx+7FFFFEFEh]
0x18015d457  test    rax, rax
0x18015d45a  jz      short loc_18015D473
0x18015d45c  movzx   eax, word ptr [r8+rcx]
0x18015d461  test    ax, ax
0x18015d464  jz      short loc_18015D473
0x18015d466  mov     [rcx], ax
0x18015d469  add     rcx, 2
0x18015d46d  sub     rdx, 1
0x18015d471  jnz     short loc_18015D450
0x18015d473  lea     rax, [rcx-2]
0x18015d477  test    rdx, rdx
0x18015d47a  cmovnz  rax, rcx
0x18015d47e  mov     [rax], r9w
0x18015d482  mov     ebx, 8007007Ah
0x18015d487  cmovnz  ebx, r9d
0x18015d48b  jz      short loc_18015D4DB
0x18015d48d  lea     rcx, [rdi+208h]
0x18015d494  mov     edx, 100h
0x18015d499  mov     r8, r15
0x18015d49c  sub     r8, rcx
0x18015d49f  nop
0x18015d4a0  lea     rax, [rdx+7FFFFEFEh]
0x18015d4a7  test    rax, rax
0x18015d4aa  jz      short loc_18015D4C3
0x18015d4ac  movzx   eax, word ptr [r8+rcx]
0x18015d4b1  test    ax, ax
0x18015d4b4  jz      short loc_18015D4C3
0x18015d4b6  mov     [rcx], ax
0x18015d4b9  add     rcx, 2
0x18015d4bd  sub     rdx, 1
0x18015d4c1  jnz     short loc_18015D4A0
0x18015d4c3  lea     rax, [rcx-2]
0x18015d4c7  test    rdx, rdx
0x18015d4ca  cmovnz  rax, rcx
0x18015d4ce  mov     [rax], r9w
0x18015d4d2  mov     ebx, 8007007Ah
0x18015d4d7  cmovnz  ebx, r9d
0x18015d4db  mov     eax, cs:_bidGblFlags
0x18015d4e1  and     eax, 20002h
0x18015d4e6  cmp     eax, 20002h
0x18015d4eb  jnz     short loc_18015D515
0x18015d4ed  mov     rax, cs:?_bidPtrSA_030_709@?BD@??Init@ProtElem@@QEAAKQEB_W0@Z@4REB_WEB; wchar_t const * const `ProtElem::Init(wchar_t const * const,wchar_t const * const)'::`19'::_bidPtrSA_030_709
0x18015d4f4  test    rax, rax
0x18015d4f7  jz      short loc_18015D515
0x18015d4f9  mov     r9d, ebx
0x18015d4fc  mov     r8, cs:?_bidPtrSA_030_709@?BD@??Init@ProtElem@@QEAAKQEB_W0@Z@4REB_WEB; wchar_t const * const `ProtElem::Init(wchar_t const * const,wchar_t const * const)'::`19'::_bidPtrSA_030_709
0x18015d503  mov     edx, 0B1400h
0x18015d508  mov     rcx, cs:?_bidSrcFileA@?BD@??Init@ProtElem@@QEAAKQEB_W0@Z@4REBDEB; char const * const `ProtElem::Init(wchar_t const * const,wchar_t const * const)'::`19'::_bidSrcFileA
0x18015d50f  call    _bidTraceW
0x18015d514  nop
0x18015d515  lea     rcx, [rsp+0A8h+var_68]; this
0x18015d51a  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x18015d51f  nop
0x18015d520  mov     rcx, rdi; void *
0x18015d523  test    ebx, ebx
0x18015d525  jnz     loc_18015D5F0
0x18015d52b  mov     r8, rbp; wchar_t *
0x18015d52e  mov     rdx, rsi; wchar_t *
0x18015d531  call    ?GetProtocolDefaults@@YAKPEAVProtElem@@PEB_W1@Z; GetProtocolDefaults(ProtElem *,wchar_t const *,wchar_t const *)
0x18015d536  mov     ebx, eax
0x18015d538  cmp     eax, 0FFFFFFFFh
0x18015d53b  jz      loc_18015D5E1
0x18015d541  mov     [rsp+0A8h+var_60], 0FFFFFFFFFFFFFFFFh
0x18015d54a  mov     ecx, cs:_bidGblFlags
0x18015d550  and     ecx, 20004h
0x18015d556  cmp     ecx, 20004h
0x18015d55c  jnz     short loc_18015D57E
0x18015d55e  mov     rcx, cs:?_bidPtrSA_040_910@?6??AddTail@ProtList@@QEAAXPEAVProtElem@@@Z@4REB_WEB; wchar_t const * const `ProtList::AddTail(ProtElem *)'::`7'::_bidPtrSA_040_910
0x18015d565  test    rcx, rcx
0x18015d568  jz      short loc_18015D57E
0x18015d56a  mov     r8, rdi
0x18015d56d  mov     rdx, cs:?_bidPtrSA_040_910@?6??AddTail@ProtList@@QEAAXPEAVProtElem@@@Z@4REB_WEB; wchar_t const * const `ProtList::AddTail(ProtElem *)'::`7'::_bidPtrSA_040_910
0x18015d574  lea     rcx, [rsp+0A8h+var_60]
0x18015d579  call    _bidScopeEnterW
0x18015d57e  mov     rcx, r12
0x18015d581  mov     rax, [r12]
0x18015d585  test    rax, rax
0x18015d588  jz      short loc_18015D59F
0x18015d58a  nop     word ptr [rax+rax+00h]
0x18015d590  lea     rcx, [rax+0A08h]
0x18015d597  mov     rax, [rcx]
0x18015d59a  test    rax, rax
0x18015d59d  jnz     short loc_18015D590
0x18015d59f  mov     [rcx], rdi
0x18015d5a2  mov     qword ptr [rdi+0A08h], 0
0x18015d5ad  lea     rcx, [rsp+0A8h+var_60]; this
0x18015d5b2  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x18015d5b7  nop
0x18015d5b8  xor     edi, edi
0x18015d5ba  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18015d5c1  inc     rax
0x18015d5c4  cmp     word ptr [rsi+rax*2], 0
0x18015d5c9  jnz     short loc_18015D5C1
0x18015d5cb  mov     eax, eax
0x18015d5cd  lea     rsi, [rsi+rax*2]
0x18015d5d1  add     rsi, 2
0x18015d5d5  cmp     word ptr [rsi], 0
0x18015d5d9  jnz     loc_18015D2F0
0x18015d5df  jmp     short loc_18015D5FF
0x18015d5e1  mov     edx, 0A10h; unsigned __int64
0x18015d5e6  mov     rcx, rdi; void *
0x18015d5e9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18015d5ee  jmp     short loc_18015D5FF
0x18015d5f0  mov     edx, 0A10h; unsigned __int64
0x18015d5f5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18015d5fa  mov     ebx, 0FFFFFFFFh
0x18015d5ff  test    r14, r14
0x18015d602  jz      short loc_18015D61F
0x18015d604  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x18015d60b  mov     rax, [rcx]
0x18015d60e  mov     rdx, r14
0x18015d611  mov     rax, [rax+80h]
0x18015d618  call    cs:__guard_dispatch_icall_fptr
0x18015d61e  nop
0x18015d61f  mov     eax, cs:_bidGblFlags
0x18015d625  and     eax, 20002h
0x18015d62a  cmp     eax, 20002h
0x18015d62f  jnz     short loc_18015D659
0x18015d631  mov     rax, cs:off_180264128; "<GetProtocolList|RET|SNI> %d{WINERR}\n"
0x18015d638  test    rax, rax
0x18015d63b  jz      short loc_18015D659
0x18015d63d  mov     r9d, ebx
0x18015d640  mov     r8, cs:off_180264128; "<GetProtocolList|RET|SNI> %d{WINERR}\n"
0x18015d647  mov     edx, 0C6000h
0x18015d64c  mov     rcx, cs:off_180260DE0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015d653  call    _bidTraceW
0x18015d658  nop
0x18015d659  lea     rcx, [rsp+0A8h+var_58]; this
0x18015d65e  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x18015d663  nop
0x18015d664  mov     eax, ebx
0x18015d666  mov     rcx, [rsp+0A8h+var_50]
0x18015d66b  xor     rcx, rsp; StackCookie
0x18015d66e  call    __security_check_cookie
0x18015d673  add     rsp, 68h
0x18015d677  pop     r15
0x18015d679  pop     r14
0x18015d67b  pop     r13
0x18015d67d  pop     r12
0x18015d67f  pop     rdi
0x18015d680  pop     rsi
0x18015d681  pop     rbp
0x18015d682  pop     rbx
0x18015d683  retn
```
