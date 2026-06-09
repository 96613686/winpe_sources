# DC_CheckAndUpdatePendingDocs(ushort *,PushRouterSubmitOrigin,OMADMALERTINFO const *,ulong)

- ea: `0x18000b67c`
- end: `0x18000bc3d`
- name: `?DC_CheckAndUpdatePendingDocs@@YAJPEAGW4PushRouterSubmitOrigin@@PEBUOMADMALERTINFO@@K@Z`
- size: `1473`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180019684`

## callees

- `0x1800031b0`
- `0x18000979c`
- `0x180009ec8`
- `0x18000a720`
- `0x18000b67c`
- `0x180011b98`
- `0x180013dac`
- `0x180014024`
- `0x1800140a0`
- `0x1800141ac`
- `0x180024010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000b734`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000b9a9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000b734`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000b9a9`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18000b7b7`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18000ba23`
- `DeclaredConfiguration!DMOrchestratorUpdateDocStatus` at `0x18000b92d`
- `DeclaredConfiguration!DMOrchestratorUpdateDocStatus` at `0x18000bbc6`
- `DeclaredConfiguration!DMOrchestratorUpdateDocStatus` at `0x18000b92d`
- `DeclaredConfiguration!DMOrchestratorUpdateDocStatus` at `0x18000bbc6`

## string_xrefs

- `0x18000bbba`: `DCAppInstallUniqueId`
- `0x18000b91a`: `DCUniversalPrinterInstallUniqueId`
- `0x18000b728`: `Reversed-Domain-Name:com.microsoft.mdm.UPPrinterInstallsAlert`
- `0x18000b7d0`: `uppprinterinstalls`
- `0x18000b99d`: `Reversed-Domain-Name:com.microsoft.mdm.EnterpriseStoreAppInstall.result`
- `0x18000ba3c`: `appinstallation`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=2
__int64 __fastcall DC_CheckAndUpdatePendingDocs(__int64 a1, int a2, __int64 a3, unsigned int a4)
{
  int v4; // r13d
  unsigned int v6; // r14d
  __m128i si128; // xmm6
  unsigned __int64 v8; // rcx
  __int64 v9; // rdi
  __int64 v10; // r8
  __int128 *v11; // rsi
  __int128 *v12; // rdx
  unsigned __int16 *v13; // r12
  unsigned __int16 *v14; // rdi
  __int64 v15; // rax
  __int64 v16; // rdx
  unsigned __int64 first_of; // rdi
  unsigned __int64 last_of; // rax
  unsigned __int64 v19; // rdx
  __int64 v20; // r8
  __int128 *v21; // rax
  __int128 *v22; // r9
  unsigned int v23; // r14d
  __m128i v24; // xmm6
  unsigned __int64 v25; // rcx
  __int64 v26; // rdi
  __int64 v27; // r8
  __int128 *v28; // rsi
  __int128 *v29; // rdx
  unsigned __int16 *v30; // r12
  unsigned __int16 *v31; // rdi
  __int64 v32; // rax
  __int64 v33; // rdx
  unsigned __int64 v34; // rdi
  unsigned __int64 v35; // rax
  unsigned __int64 v36; // rcx
  unsigned __int64 v37; // rdx
  __int64 v38; // r8
  __int128 *v39; // rax
  const wchar_t *v40; // rdx
  __int128 *v41; // r9
  int v42; // [rsp+20h] [rbp-E8h]
  unsigned int v43; // [rsp+30h] [rbp-D8h]
  __int64 v45; // [rsp+40h] [rbp-C8h]
  __int128 v46; // [rsp+50h] [rbp-B8h] BYREF
  __int128 v47; // [rsp+60h] [rbp-A8h]
  __int128 v48; // [rsp+70h] [rbp-98h] BYREF
  __int128 v49; // [rsp+80h] [rbp-88h]
  __int128 v50; // [rsp+90h] [rbp-78h] BYREF
  __m128i v51; // [rsp+A0h] [rbp-68h]
  __int128 v52; // [rsp+B0h] [rbp-58h] BYREF
  __int128 v53; // [rsp+C0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v43 = a4;
  v45 = a3;
  v4 = 0;
  if ( a4 && !a3 )
    return 2147942487LL;
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D8,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmapi\\src\\omadmapi.cpp",
      (const char *)0x80070057LL,
      v42);
    return 2147942487LL;
  }
  if ( a2 == 45 )
  {
    v6 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    while ( 1 )
    {
      if ( v6 >= a4 )
        return 0;
      v8 = (unsigned __int64)v6 << 6;
      v9 = *(_QWORD *)(v8 + a3 + 16);
      if ( !(unsigned int)_o__wcsicmp(
                            *(_QWORD *)(v8 + a3 + 8),
                            L"Reversed-Domain-Name:com.microsoft.mdm.UPPrinterInstallsAlert") )
      {
        v48 = 0;
        v49 = 0;
        v10 = -1;
        do
          ++v10;
        while ( *(_WORD *)(v9 + 2 * v10) );
        std::wstring::_Construct<1,unsigned short const *>(&v48, v9, v10);
        if ( *((_QWORD *)&v49 + 1) <= 7u )
        {
          v11 = &v48;
          v12 = &v48;
        }
        else
        {
          v11 = (__int128 *)v48;
          v12 = (__int128 *)v48;
        }
        v13 = (unsigned __int16 *)v12 + v49;
        v14 = (unsigned __int16 *)&v48;
        if ( *((_QWORD *)&v49 + 1) > 7u )
          v14 = (unsigned __int16 *)v48;
        while ( v14 != v13 )
        {
          *(_WORD *)v11 = _o_towlower(*v14++);
          v11 = (__int128 *)((char *)v11 + 2);
        }
        v15 = std::wstring::find(&v48, L"uppprinterinstalls");
        if ( v15 == -1
          || (first_of = std::wstring::find_first_of(&v48, v16, v15), first_of == -1)
          || (last_of = std::wstring::find_last_of(&v48), last_of == -1) )
        {
          std::wstring::~wstring(&v48);
          return 2147942402LL;
        }
        v50 = 0;
        v51 = si128;
        LOWORD(v50) = 0;
        if ( last_of > first_of )
        {
          v19 = first_of + 1;
          v52 = 0;
          v53 = 0;
          if ( (unsigned __int64)v49 < first_of + 1 )
          {
            std::_String_val<std::_Simple_types<unsigned short>>::_Xran(last_of);
            goto LABEL_71;
          }
          v20 = v49 - v19;
          if ( (unsigned __int64)v49 - v19 >= last_of - first_of - 1 )
            v20 = last_of - first_of - 1;
          v21 = &v48;
          if ( *((_QWORD *)&v49 + 1) > 7u )
            v21 = (__int128 *)v48;
          std::wstring::_Construct<1,unsigned short const *>(&v52, (char *)v21 + 2 * v19, v20);
          v4 |= 1u;
          std::wstring::operator=(&v50, &v52);
          std::wstring::~wstring(&v52);
        }
        v22 = &v50;
        if ( v51.m128i_i64[1] > 7uLL )
          v22 = (__int128 *)v50;
        DMOrchestratorUpdateDocStatus(a1, L"user", L"DCUniversalPrinterInstallUniqueId", v22, 1);
        std::wstring::~wstring(&v50);
        std::wstring::~wstring(&v48);
      }
      ++v6;
      a3 = v45;
      a4 = v43;
    }
  }
  if ( ((a2 - 31) & 0xFFFFFFF7) == 0 )
  {
    v23 = 0;
    v24 = _mm_load_si128((const __m128i *)&_xmm);
    while ( 1 )
    {
      if ( v23 >= a4 )
        return 0;
      v25 = (unsigned __int64)v23 << 6;
      v26 = *(_QWORD *)(v25 + a3 + 16);
      if ( !(unsigned int)_o__wcsicmp(
                            *(_QWORD *)(v25 + a3 + 8),
                            L"Reversed-Domain-Name:com.microsoft.mdm.EnterpriseStoreAppInstall.result") )
        break;
LABEL_68:
      ++v23;
      a3 = v45;
      a4 = v43;
    }
    v46 = 0;
    v47 = 0;
    v27 = -1;
    do
      ++v27;
    while ( *(_WORD *)(v26 + 2 * v27) );
    std::wstring::_Construct<1,unsigned short const *>(&v46, v26, v27);
    if ( *((_QWORD *)&v47 + 1) <= 7u )
    {
      v28 = &v46;
      v29 = &v46;
    }
    else
    {
      v28 = (__int128 *)v46;
      v29 = (__int128 *)v46;
    }
    v30 = (unsigned __int16 *)v29 + v47;
    v31 = (unsigned __int16 *)&v46;
    if ( *((_QWORD *)&v47 + 1) > 7u )
      v31 = (unsigned __int16 *)v46;
    while ( v31 != v30 )
    {
      *(_WORD *)v28 = _o_towlower(*v31++);
      v28 = (__int128 *)((char *)v28 + 2);
    }
    v32 = std::wstring::find(&v46, L"appinstallation");
    if ( v32 == -1
      || (v34 = std::wstring::find_first_of(&v46, v33, v32), v34 == -1)
      || (v35 = std::wstring::find_last_of(&v46), v36 = v35, v35 == -1) )
    {
      std::wstring::~wstring(&v46);
      return 2147942402LL;
    }
    v50 = 0;
    v51 = v24;
    LOWORD(v50) = 0;
    if ( v35 > v34 )
    {
      v37 = v34 + 1;
      v52 = 0;
      v53 = 0;
      if ( (unsigned __int64)v47 < v34 + 1 )
      {
LABEL_71:
        std::_String_val<std::_Simple_types<unsigned short>>::_Xran(v36);
        JUMPOUT(0x18000BC3BLL);
      }
      v38 = v47 - v37;
      if ( (unsigned __int64)v47 - v37 >= v35 - v34 - 1 )
        v38 = v35 - v34 - 1;
      v39 = &v46;
      if ( *((_QWORD *)&v47 + 1) > 7u )
        v39 = (__int128 *)v46;
      std::wstring::_Construct<1,unsigned short const *>(&v52, (char *)v39 + 2 * v37, v38);
      v4 |= 2u;
      std::wstring::operator=(&v50, &v52);
      std::wstring::~wstring(&v52);
    }
    if ( std::wstring::find(&v46, L"./user") == -1 )
    {
      if ( std::wstring::find(&v46, L"./device") == -1 )
      {
LABEL_67:
        std::wstring::~wstring(&v50);
        std::wstring::~wstring(&v46);
        goto LABEL_68;
      }
      v40 = L"device";
    }
    else
    {
      v40 = L"user";
    }
    v41 = &v50;
    if ( v51.m128i_i64[1] > 7uLL )
      v41 = (__int128 *)v50;
    DMOrchestratorUpdateDocStatus(a1, v40, L"DCAppInstallUniqueId", v41, 1);
    goto LABEL_67;
  }
  return 0;
}

```

## disassembly

```asm
0x18000b67c  mov     rax, rsp
0x18000b67f  mov     [rax+10h], rsi
0x18000b683  mov     [rax+20h], rdi
0x18000b687  push    r12
0x18000b689  push    r13
0x18000b68b  push    r14
0x18000b68d  sub     rsp, 0F0h
0x18000b694  movaps  xmmword ptr [rax-28h], xmm6
0x18000b698  mov     rax, cs:__security_cookie
0x18000b69f  xor     rax, rsp
0x18000b6a2  mov     [rsp+108h+var_38], rax
0x18000b6aa  mov     [rsp+108h+var_D8], r9d
0x18000b6af  mov     [rsp+108h+var_C8], r8
0x18000b6b4  mov     rax, rcx
0x18000b6b7  mov     [rsp+108h+var_D0], rcx
0x18000b6bc  xor     esi, esi
0x18000b6be  mov     r13d, esi
0x18000b6c1  mov     [rsp+108h+var_C0], esi
0x18000b6c5  test    r9d, r9d
0x18000b6c8  jz      short loc_18000B6D9
0x18000b6ca  test    r8, r8
0x18000b6cd  jnz     short loc_18000B6D9
0x18000b6cf  mov     eax, 80070057h
0x18000b6d4  jmp     loc_18000BC00
0x18000b6d9  test    rax, rax
0x18000b6dc  jnz     short loc_18000B6FF
0x18000b6de  mov     rcx, [rsp+108h]; this
0x18000b6e6  mov     r9d, 80070057h; char *
0x18000b6ec  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\dm\\omadm\\omadmapi"...
0x18000b6f3  mov     edx, 2D8h; void *
0x18000b6f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b6fd  jmp     short loc_18000B6CF
0x18000b6ff  cmp     edx, 2Dh ; '-'
0x18000b702  jnz     loc_18000B96F
0x18000b708  mov     r14d, esi
0x18000b70b  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18000b713  cmp     r14d, r9d
0x18000b716  jnb     loc_18000BBFE
0x18000b71c  mov     ecx, r14d
0x18000b71f  shl     rcx, 6
0x18000b723  mov     rdi, [rcx+r8+10h]
0x18000b728  lea     rdx, aReversedDomain_0; "Reversed-Domain-Name:com.microsoft.mdm."...
0x18000b72f  mov     rcx, [rcx+r8+8]
0x18000b734  call    cs:__imp__o__wcsicmp
0x18000b73b  nop     dword ptr [rax+rax+00h]
0x18000b740  test    eax, eax
0x18000b742  jnz     loc_18000B95D
0x18000b748  xorps   xmm0, xmm0
0x18000b74b  movups  [rsp+108h+var_98], xmm0
0x18000b750  xorps   xmm1, xmm1
0x18000b753  movdqu  [rsp+108h+var_88], xmm1
0x18000b75c  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000b760  inc     r8
0x18000b763  cmp     [rdi+r8*2], si
0x18000b768  jnz     short loc_18000B760
0x18000b76a  mov     rdx, rdi
0x18000b76d  lea     rcx, [rsp+108h+var_98]
0x18000b772  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000b777  nop
0x18000b778  mov     rcx, qword ptr [rsp+108h+var_98]
0x18000b77d  cmp     qword ptr [rsp+108h+var_88+8], 7
0x18000b786  jbe     short loc_18000B790
0x18000b788  mov     rsi, rcx
0x18000b78b  mov     rdx, rcx
0x18000b78e  jmp     short loc_18000B79A
0x18000b790  lea     rsi, [rsp+108h+var_98]
0x18000b795  lea     rdx, [rsp+108h+var_98]
0x18000b79a  mov     rax, qword ptr [rsp+108h+var_88]
0x18000b7a2  lea     r12, [rdx+rax*2]
0x18000b7a6  lea     rdi, [rsp+108h+var_98]
0x18000b7ab  cmova   rdi, rcx
0x18000b7af  cmp     rdi, r12
0x18000b7b2  jz      short loc_18000B7D0
0x18000b7b4  movzx   ecx, word ptr [rdi]
0x18000b7b7  mov     rax, cs:__imp__o_towlower
0x18000b7be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7c3  mov     [rsi], ax
0x18000b7c6  add     rdi, 2
0x18000b7ca  add     rsi, 2
0x18000b7ce  jmp     short loc_18000B7AF
0x18000b7d0  lea     rdx, aUppprinterinst; "uppprinterinstalls"
0x18000b7d7  lea     rcx, [rsp+108h+var_98]
0x18000b7dc  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x18000b7e1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000b7e5  jnz     short loc_18000B7FB
0x18000b7e7  lea     rcx, [rsp+108h+var_98]
0x18000b7ec  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000b7f1  mov     eax, 80070002h
0x18000b7f6  jmp     loc_18000BC00
0x18000b7fb  mov     r8, rax
0x18000b7fe  lea     rcx, [rsp+108h+var_98]
0x18000b803  call    ?find_first_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find_first_of(ushort const * const,unsigned __int64)
0x18000b808  mov     rdi, rax
0x18000b80b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000b80f  jnz     short loc_18000B825
0x18000b811  lea     rcx, [rsp+108h+var_98]
0x18000b816  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000b81b  mov     eax, 80070002h
0x18000b820  jmp     loc_18000BC00
0x18000b825  lea     rcx, [rsp+108h+var_98]
0x18000b82a  call    ?find_last_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find_last_of(ushort const * const,unsigned __int64)
0x18000b82f  mov     rcx, rax
0x18000b832  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000b836  jnz     short loc_18000B84C
0x18000b838  lea     rcx, [rsp+108h+var_98]
0x18000b83d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000b842  mov     eax, 80070002h
0x18000b847  jmp     loc_18000BC00
0x18000b84c  xorps   xmm0, xmm0
0x18000b84f  movups  [rsp+108h+var_78], xmm0
0x18000b857  movdqu  [rsp+108h+var_68], xmm6
0x18000b860  xor     esi, esi
0x18000b862  mov     word ptr [rsp+108h+var_78], si
0x18000b86a  cmp     rcx, rdi
0x18000b86d  jbe     loc_18000B8F8
0x18000b873  lea     rdx, [rdi+1]
0x18000b877  movups  [rsp+108h+var_58], xmm0
0x18000b87f  xorps   xmm1, xmm1
0x18000b882  movdqu  [rsp+108h+var_48], xmm1
0x18000b88b  mov     r8, qword ptr [rsp+108h+var_88]
0x18000b893  cmp     r8, rdx
0x18000b896  jb      loc_18000BC30
0x18000b89c  sub     rcx, rdi
0x18000b89f  lea     rax, [rcx-1]
0x18000b8a3  sub     r8, rdx
0x18000b8a6  cmp     r8, rax
0x18000b8a9  cmovnb  r8, rax
0x18000b8ad  lea     rax, [rsp+108h+var_98]
0x18000b8b2  cmp     qword ptr [rsp+108h+var_88+8], 7
0x18000b8bb  cmova   rax, qword ptr [rsp+108h+var_98]
0x18000b8c1  lea     rdx, [rax+rdx*2]
0x18000b8c5  lea     rcx, [rsp+108h+var_58]
0x18000b8cd  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000b8d2  or      r13d, 1
0x18000b8d6  lea     rdx, [rsp+108h+var_58]
0x18000b8de  lea     rcx, [rsp+108h+var_78]
0x18000b8e6  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000b8eb  lea     rcx, [rsp+108h+var_58]
0x18000b8f3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000b8f8  lea     r9, [rsp+108h+var_78]
0x18000b900  cmp     qword ptr [rsp+108h+var_68+8], 7
0x18000b909  cmova   r9, qword ptr [rsp+108h+var_78]
0x18000b912  mov     [rsp+108h+var_E8], 1
0x18000b91a  lea     r8, aDcuniversalpri; "DCUniversalPrinterInstallUniqueId"
0x18000b921  lea     rdx, aUser_0; "user"
0x18000b928  mov     rcx, [rsp+108h+var_D0]
0x18000b92d  call    cs:__imp_DMOrchestratorUpdateDocStatus
0x18000b934  nop     dword ptr [rax+rax+00h]
0x18000b939  nop
0x18000b93a  lea     rcx, [rsp+108h+var_78]
0x18000b942  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000b947  nop
0x18000b948  lea     rcx, [rsp+108h+var_98]
0x18000b94d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000b952  jmp     short loc_18000B95D
0x18000b954  mov     eax, [rsp+108h+var_D8]
0x18000b958  jmp     loc_18000BC00
0x18000b95d  inc     r14d
0x18000b960  mov     r8, [rsp+108h+var_C8]
0x18000b965  mov     r9d, [rsp+108h+var_D8]
0x18000b96a  jmp     loc_18000B713
0x18000b96f  lea     eax, [rdx-1Fh]
0x18000b972  test    eax, 0FFFFFFF7h
0x18000b977  jnz     loc_18000BBFE
0x18000b97d  mov     r14d, esi
0x18000b980  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18000b988  cmp     r14d, r9d
0x18000b98b  jnb     loc_18000BBFE
0x18000b991  mov     ecx, r14d
0x18000b994  shl     rcx, 6
0x18000b998  mov     rdi, [rcx+r8+10h]
0x18000b99d  lea     rdx, aReversedDomain; "Reversed-Domain-Name:com.microsoft.mdm."...
0x18000b9a4  mov     rcx, [rcx+r8+8]
0x18000b9a9  call    cs:__imp__o__wcsicmp
0x18000b9b0  nop     dword ptr [rax+rax+00h]
0x18000b9b5  test    eax, eax
0x18000b9b7  jnz     loc_18000BBEC
0x18000b9bd  xorps   xmm0, xmm0
0x18000b9c0  movups  [rsp+108h+var_B8], xmm0
0x18000b9c5  xorps   xmm1, xmm1
0x18000b9c8  movdqu  [rsp+108h+var_A8], xmm1
0x18000b9ce  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000b9d2  inc     r8
0x18000b9d5  cmp     [rdi+r8*2], si
0x18000b9da  jnz     short loc_18000B9D2
0x18000b9dc  mov     rdx, rdi
0x18000b9df  lea     rcx, [rsp+108h+var_B8]
0x18000b9e4  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000b9e9  nop
0x18000b9ea  mov     rcx, qword ptr [rsp+108h+var_B8]
0x18000b9ef  cmp     qword ptr [rsp+108h+var_A8+8], 7
0x18000b9f5  jbe     short loc_18000B9FF
0x18000b9f7  mov     rsi, rcx
0x18000b9fa  mov     rdx, rcx
0x18000b9fd  jmp     short loc_18000BA09
0x18000b9ff  lea     rsi, [rsp+108h+var_B8]
0x18000ba04  lea     rdx, [rsp+108h+var_B8]
0x18000ba09  mov     rax, qword ptr [rsp+108h+var_A8]
0x18000ba0e  lea     r12, [rdx+rax*2]
0x18000ba12  lea     rdi, [rsp+108h+var_B8]
0x18000ba17  cmova   rdi, rcx
0x18000ba1b  cmp     rdi, r12
0x18000ba1e  jz      short loc_18000BA3C
0x18000ba20  movzx   ecx, word ptr [rdi]
0x18000ba23  mov     rax, cs:__imp__o_towlower
0x18000ba2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba2f  mov     [rsi], ax
0x18000ba32  add     rdi, 2
0x18000ba36  add     rsi, 2
0x18000ba3a  jmp     short loc_18000BA1B
0x18000ba3c  lea     rdx, aAppinstallatio; "appinstallation"
0x18000ba43  lea     rcx, [rsp+108h+var_B8]
0x18000ba48  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x18000ba4d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ba51  jnz     short loc_18000BA67
0x18000ba53  lea     rcx, [rsp+108h+var_B8]
0x18000ba58  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ba5d  mov     eax, 80070002h
0x18000ba62  jmp     loc_18000BC00
0x18000ba67  mov     r8, rax
0x18000ba6a  lea     rcx, [rsp+108h+var_B8]
0x18000ba6f  call    ?find_first_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find_first_of(ushort const * const,unsigned __int64)
0x18000ba74  mov     rdi, rax
0x18000ba77  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ba7b  jnz     short loc_18000BA91
0x18000ba7d  lea     rcx, [rsp+108h+var_B8]
0x18000ba82  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ba87  mov     eax, 80070002h
0x18000ba8c  jmp     loc_18000BC00
0x18000ba91  lea     rcx, [rsp+108h+var_B8]
0x18000ba96  call    ?find_last_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find_last_of(ushort const * const,unsigned __int64)
0x18000ba9b  mov     rcx, rax
0x18000ba9e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000baa2  jnz     short loc_18000BAB8
0x18000baa4  lea     rcx, [rsp+108h+var_B8]
0x18000baa9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000baae  mov     eax, 80070002h
0x18000bab3  jmp     loc_18000BC00
0x18000bab8  xorps   xmm0, xmm0
0x18000babb  movups  [rsp+108h+var_78], xmm0
0x18000bac3  movdqu  [rsp+108h+var_68], xmm6
0x18000bacc  xor     esi, esi
0x18000bace  mov     word ptr [rsp+108h+var_78], si
0x18000bad6  cmp     rcx, rdi
0x18000bad9  jbe     short loc_18000BB5A
0x18000badb  lea     rdx, [rdi+1]
0x18000badf  movups  [rsp+108h+var_58], xmm0
0x18000bae7  xorps   xmm1, xmm1
0x18000baea  movdqu  [rsp+108h+var_48], xmm1
0x18000baf3  mov     r8, qword ptr [rsp+108h+var_A8]
0x18000baf8  cmp     r8, rdx
0x18000bafb  jb      loc_18000BC36
0x18000bb01  sub     rcx, rdi
0x18000bb04  lea     rax, [rcx-1]
0x18000bb08  sub     r8, rdx
0x18000bb0b  cmp     r8, rax
0x18000bb0e  cmovnb  r8, rax
0x18000bb12  lea     rax, [rsp+108h+var_B8]
0x18000bb17  cmp     qword ptr [rsp+108h+var_A8+8], 7
0x18000bb1d  cmova   rax, qword ptr [rsp+108h+var_B8]
0x18000bb23  lea     rdx, [rax+rdx*2]
0x18000bb27  lea     rcx, [rsp+108h+var_58]
0x18000bb2f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000bb34  or      r13d, 2
0x18000bb38  lea     rdx, [rsp+108h+var_58]
0x18000bb40  lea     rcx, [rsp+108h+var_78]
0x18000bb48  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000bb4d  lea     rcx, [rsp+108h+var_58]
0x18000bb55  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000bb5a  lea     rdx, aUser; "./user"
0x18000bb61  lea     rcx, [rsp+108h+var_B8]
0x18000bb66  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x18000bb6b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000bb6f  jz      short loc_18000BB7A
0x18000bb71  lea     rdx, aUser_0; "user"
0x18000bb78  jmp     short loc_18000BB98
0x18000bb7a  lea     rdx, aDevice; "./device"
0x18000bb81  lea     rcx, [rsp+108h+var_B8]
0x18000bb86  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x18000bb8b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000bb8f  jz      short loc_18000BBD3
0x18000bb91  lea     rdx, aDevice_0; "device"
0x18000bb98  lea     r9, [rsp+108h+var_78]
0x18000bba0  cmp     qword ptr [rsp+108h+var_68+8], 7
0x18000bba9  mov     [rsp+108h+var_E8], 1
0x18000bbb1  cmova   r9, qword ptr [rsp+108h+var_78]
0x18000bbba  lea     r8, aDcappinstallun; "DCAppInstallUniqueId"
0x18000bbc1  mov     rcx, [rsp+108h+var_D0]
0x18000bbc6  call    cs:__imp_DMOrchestratorUpdateDocStatus
0x18000bbcd  nop     dword ptr [rax+rax+00h]
0x18000bbd2  nop
0x18000bbd3  lea     rcx, [rsp+108h+var_78]
0x18000bbdb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000bbe0  nop
0x18000bbe1  lea     rcx, [rsp+108h+var_B8]
0x18000bbe6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000bbeb  nop
0x18000bbec  inc     r14d
0x18000bbef  mov     r8, [rsp+108h+var_C8]
0x18000bbf4  mov     r9d, [rsp+108h+var_D8]
  ... truncated ...
```
