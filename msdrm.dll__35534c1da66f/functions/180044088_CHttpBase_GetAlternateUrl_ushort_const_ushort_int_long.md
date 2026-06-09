# CHttpBase::GetAlternateUrl(ushort const *,ushort * *,int *,long *)

- ea: `0x180044088`
- end: `0x18004481f`
- name: `?GetAlternateUrl@CHttpBase@@AEAAJPEBGPEAPEAGPEAHPEAJ@Z`
- size: `1943`
- prototype: `__int64 __fastcall(CHttpBase *__hidden this, const unsigned __int16 *, unsigned __int16 **, int *, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180043bc0`

## callees

- `0x180001284`
- `0x180001290`
- `0x180004654`
- `0x1800046c8`
- `0x180015438`
- `0x180017210`
- `0x180037d38`
- `0x180039970`
- `0x180044088`
- `0x180045980`
- `0x180046938`

## import_xrefs

- `msvcrt!_wcslwr` at `0x1800445e2`
- `msvcrt!_wcslwr` at `0x1800445e2`
- `msvcrt!wcsrchr` at `0x1800445a0`
- `msvcrt!wcsrchr` at `0x1800445a0`
- `msvcrt!_wcsicmp` at `0x180044252`
- `msvcrt!_wcsicmp` at `0x1800443e0`
- `msvcrt!_wcsicmp` at `0x180044252`
- `msvcrt!_wcsicmp` at `0x1800443e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800443b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800443b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004411a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004411a`

## string_xrefs

- `0x180044292`: `[msdrm]:Using Cache - Server From Url=%S To Url=%S`
- `0x180044409`: `[msdrm]:Using Cache - UrlResolvable Url=%S`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=2
__int64 __fastcall CHttpBase::GetAlternateUrl(
        CHttpBase *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        int *a4,
        int *a5)
{
  const wchar_t *v5; // r14
  signed int ServerAndObjectPath; // edi
  unsigned __int16 *v7; // r15
  unsigned __int16 *v8; // rsi
  HKEY v9; // rcx
  unsigned __int64 v10; // r12
  __int64 v11; // rax
  __int64 v12; // rax
  unsigned __int64 v13; // r14
  unsigned __int16 *v14; // rax
  HKEY v15; // rdx
  DRMOS *v16; // rcx
  const unsigned __int16 *v17; // r8
  const unsigned __int16 *v18; // r9
  unsigned int i; // edi
  unsigned __int64 v20; // rax
  const unsigned __int16 **v21; // r13
  const unsigned __int16 *v22; // rax
  __int64 v23; // rdx
  unsigned __int64 v24; // r8
  signed __int64 v25; // rsi
  unsigned __int64 v26; // rcx
  unsigned __int64 v27; // rax
  unsigned __int64 v28; // rcx
  unsigned __int16 *v29; // rax
  unsigned int j; // edi
  __int64 v31; // r13
  unsigned __int64 v32; // rax
  unsigned __int16 * near *v33; // rax
  __int64 v34; // rdx
  unsigned __int64 v35; // r8
  signed __int64 v36; // rsi
  unsigned __int64 v37; // rcx
  unsigned __int64 v38; // rax
  unsigned __int64 v39; // rcx
  unsigned __int16 *v40; // rax
  int v41; // eax
  CHttpBase *v42; // rcx
  wchar_t *v43; // rax
  __int64 v44; // rsi
  __int64 v45; // rdi
  wchar_t *v46; // r13
  unsigned __int64 v47; // rsi
  unsigned __int64 v48; // rax
  unsigned __int16 *v49; // rax
  unsigned __int64 v50; // rcx
  unsigned __int16 *v51; // rax
  unsigned __int64 v52; // rdx
  unsigned __int64 v53; // rax
  bool v54; // zf
  unsigned __int64 v55; // rcx
  unsigned __int16 *v56; // rdx
  wchar_t v57; // r8
  unsigned __int16 *v58; // rax
  __int64 v59; // rax
  __int64 v60; // rcx
  wchar_t *Str; // [rsp+30h] [rbp-78h] BYREF
  void *Block[2]; // [rsp+38h] [rbp-70h] BYREF
  unsigned __int16 *v64[3]; // [rsp+48h] [rbp-60h] BYREF
  int v65; // [rsp+64h] [rbp-44h] BYREF
  unsigned __int16 *v66; // [rsp+B0h] [rbp+8h]
  unsigned __int16 *v67; // [rsp+B0h] [rbp+8h]

  v64[2] = (unsigned __int16 *)-2LL;
  v5 = a2;
  ServerAndObjectPath = 0;
  v7 = 0;
  Block[1] = 0;
  Block[0] = 0;
  v64[0] = 0;
  Str = 0;
  v8 = 0;
  if ( !g_fGlobalOptionUseWinhttp && g_dwHomeRealmCheck )
  {
    if ( !a2 || !a3 || !a4 || !a5 )
    {
      ServerAndObjectPath = -2147024809;
      goto LABEL_115;
    }
    EnterCriticalSection(&g_csOptions);
    if ( g_wszHomeRealmQueryString )
    {
      v10 = -1;
    }
    else
    {
      g_dwHomeRealmCheck = 0;
      v10 = -1;
      if ( !(unsigned int)GetRegistryKey(
                            v9,
                            L"SOFTWARE\\Microsoft\\MSDRM\\Federation",
                            L"FederationHomeRealm",
                            (unsigned __int16 **)Block) )
      {
        v11 = -1;
        do
          ++v11;
        while ( *((_WORD *)Block[0] + v11) );
        if ( v11 )
        {
          v12 = -1;
          do
            ++v12;
          while ( *((_WORD *)Block[0] + v12) );
          v13 = (unsigned int)(v12 + 6);
          v14 = (unsigned __int16 *)operator new[](saturated_mul(v13, 2u));
          v8 = v14;
          if ( !v14 )
          {
            ServerAndObjectPath = -2147024882;
            goto LABEL_45;
          }
          ServerAndObjectPath = StringCchCopyW(v14, v13, L"?whr=");
          if ( ServerAndObjectPath < 0
            || (ServerAndObjectPath = StringCchCatW(v8, v13, (const unsigned __int16 *)Block[0]), ServerAndObjectPath < 0) )
          {
LABEL_45:
            LeaveCriticalSection(&g_csOptions);
            goto LABEL_115;
          }
          g_wszHomeRealmQueryString = v8;
          DRMOS::GetDWordRegValue(v16, v15, v17, v18);
          g_dwHomeRealmCheck = 1;
          v5 = a2;
LABEL_21:
          for ( i = 0; ; ++i )
          {
            if ( i >= g_cUrlMapping )
            {
              for ( j = 0; j < g_cUrlResolvable; ++j )
              {
                v31 = j;
                if ( !_wcsicmp(v5, (const wchar_t *)(&g_pwszUrlResolvable)[j]) )
                {
                  _mm_lfence();
                  v32 = -1;
                  do
                    ++v32;
                  while ( v5[v32] );
                  if ( v32 < 0x3E8 )
                    _RTLTRACE("[msdrm]:Using Cache - UrlResolvable Url=%S", v5);
                  v33 = (&g_pwszUrlResolvable)[j];
                  if ( v33 )
                  {
                    v34 = 0x7FFFFFFF;
                    do
                    {
                      if ( !*(_WORD *)v33 )
                        break;
                      v33 = (unsigned __int16 * near *)((char *)v33 + 2);
                      --v34;
                    }
                    while ( v34 );
                    ServerAndObjectPath = v34 == 0 ? 0x80070057 : 0;
                    v35 = (0x7FFFFFFF - v34) & -(__int64)(v34 != 0);
                    if ( v34 )
                    {
                      v36 = v35 + 1;
                      if ( v35 + 1 < v35 )
                        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(0x7FFFFFFF - v34);
                      v37 = HIDWORD(v36);
                      if ( v36 < 0 )
                        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v37);
                      v38 = 2LL * (unsigned int)v36;
                      v39 = v37 << 33;
                      if ( v39 + v38 < v38 )
                        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v39);
                      if ( v39 + v38 )
                      {
                        v40 = (unsigned __int16 *)operator new[](saturated_mul(v36, 2u));
                        *a3 = v40;
                        if ( !v40 )
                        {
                          ServerAndObjectPath = -2147024882;
                          v8 = 0;
                          goto LABEL_45;
                        }
                        ServerAndObjectPath = StringCchCopyW(
                                                v40,
                                                v36,
                                                (const unsigned __int16 *)(&g_pwszUrlResolvable)[v31]);
                        if ( ServerAndObjectPath < 0 )
                        {
                          v8 = 0;
                          goto LABEL_45;
                        }
                      }
                      *a4 = 0;
                      goto LABEL_44;
                    }
                  }
                  else
                  {
                    ServerAndObjectPath = -2147024809;
                  }
                  v8 = 0;
                  goto LABEL_45;
                }
              }
              v41 = CHttpBase::ResolveUrlWithGET(v5);
              ServerAndObjectPath = v41;
              if ( v41 >= 0 )
                goto LABEL_44;
              switch ( v41 )
              {
                case -2147024809:
                  goto LABEL_44;
                case -2147024882:
                  goto LABEL_44;
                case -2147168438:
                  goto LABEL_44;
              }
              *a5 = v41;
              ServerAndObjectPath = CHttpBase::GetServerAndObjectPath(v42, a2, v64, &Str, 0, 0);
              if ( ServerAndObjectPath < 0 )
                goto LABEL_44;
              v43 = wcsrchr(Str, 0x2Fu);
              v67 = v43;
              if ( v43 )
              {
                try
                {
                  v44 = -1;
                  do
                    ++v44;
                  while ( v64[0][v44] );
                  v45 = -1;
                  do
                    ++v45;
                  while ( Str[v45] );
                  v46 = _wcslwr(Str);
                  Str = v46;
                  v47 = (unsigned int)(v45 + v44 + 17);
                  v48 = 2 * v47;
                  if ( !is_mul_ok(v47, 2u) )
                    v48 = -1;
                }
                catch ( SafeIntException v65 )
                {
                  ServerAndObjectPath = -2147467259;
                  goto LABEL_43;
                }
                v49 = (unsigned __int16 *)operator new[](v48);
                v7 = v49;
                if ( !v49 )
                {
                  ServerAndObjectPath = -2147024882;
                  goto LABEL_44;
                }
                ServerAndObjectPath = StringCchCopyW(v49, v47, L"https://");
                if ( ServerAndObjectPath < 0
                  || (ServerAndObjectPath = StringCchCatW(v7, v47, v64[0]), ServerAndObjectPath < 0) )
                {
LABEL_44:
                  v8 = 0;
                  goto LABEL_45;
                }
                if ( v47 - 1 <= 0x7FFFFFFE )
                {
                  v50 = v47;
                  v51 = v7;
                  do
                  {
                    if ( !*v51 )
                      break;
                    ++v51;
                    --v50;
                  }
                  while ( v50 );
                  ServerAndObjectPath = v50 == 0 ? 0x80070057 : 0;
                  if ( v50 )
                    v52 = v47 - v50;
                  else
                    v52 = 0;
                  if ( !v50 )
                    goto LABEL_44;
                  v53 = v67 - v46;
                  if ( v53 <= 0x7FFFFFFE )
                  {
                    v55 = v47 - v52;
                    v54 = v47 == v52;
                    v56 = &v7[v52];
                    if ( !v54 )
                    {
                      do
                      {
                        if ( !v53 )
                          break;
                        v57 = *v46;
                        if ( !*v46 )
                          break;
                        ++v46;
                        *v56++ = v57;
                        --v53;
                        --v55;
                      }
                      while ( v55 );
                    }
                    ServerAndObjectPath = v55 == 0 ? 0x8007007A : 0;
                    v58 = v56 - 1;
                    if ( v55 )
                      v58 = v56;
                    *v58 = 0;
                    if ( v55 )
                    {
                      v59 = -1;
                      do
                        ++v59;
                      while ( v7[v59] );
                      if ( (unsigned int)v59 > 1 )
                      {
                        v60 = (unsigned int)(v59 - 1);
                        if ( v7[v60] == 47 )
                          v7[v60] = 0;
                      }
                      ServerAndObjectPath = StringCchCatW(v7, v47, L"external");
                      if ( ServerAndObjectPath >= 0 )
                      {
                        ServerAndObjectPath = StringCchCatW(v7, v47, v67);
                        if ( ServerAndObjectPath >= 0 )
                        {
                          do
                            ++v10;
                          while ( v7[v10] );
                          if ( v10 < 0x3E8 )
                            _RTLTRACE("[msdrm]:ADFS Url for the Url = %S is %S", a2, v7);
                          *a3 = v7;
                          *a4 = 1;
                          ServerAndObjectPath = 0;
LABEL_43:
                          v7 = 0;
                        }
                      }
                    }
                    goto LABEL_44;
                  }
                }
              }
              ServerAndObjectPath = -2147024809;
              goto LABEL_44;
            }
            v66 = (unsigned __int16 *)i;
            if ( !_wcsicmp(v5, (const wchar_t *)(&g_pwszUrlMappingFrom)[i]) )
              break;
          }
          _mm_lfence();
          v20 = -1;
          do
            ++v20;
          while ( v5[v20] );
          v21 = (const unsigned __int16 **)&(&g_pwszUrlMappingTo)[i];
          if ( v20 < 0x3E8 )
            _RTLTRACE("[msdrm]:Using Cache - Server From Url=%S To Url=%S", v5, *v21);
          v22 = *v21;
          if ( *v21 )
          {
            v23 = 0x7FFFFFFF;
            do
            {
              if ( !*v22 )
                break;
              ++v22;
              --v23;
            }
            while ( v23 );
            ServerAndObjectPath = v23 == 0 ? 0x80070057 : 0;
            v24 = (0x7FFFFFFF - v23) & -(__int64)(v23 != 0);
            if ( v23 )
            {
              v25 = v24 + 1;
              if ( v24 + 1 < v24 )
                SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(0x7FFFFFFF - v23);
              v26 = HIDWORD(v25);
              if ( v25 < 0 )
                SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v26);
              v27 = 2LL * (unsigned int)v25;
              v28 = v26 << 33;
              if ( v28 + v27 < v27 )
                SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v28);
              if ( !(v28 + v27) )
                goto LABEL_41;
              v29 = (unsigned __int16 *)operator new[](saturated_mul(v25, 2u));
              *a3 = v29;
              if ( !v29 )
              {
                ServerAndObjectPath = -2147024882;
                v8 = 0;
                goto LABEL_45;
              }
              ServerAndObjectPath = StringCchCopyW(v29, v25, *v21);
              if ( ServerAndObjectPath >= 0 )
              {
LABEL_41:
                *a4 = *((_DWORD *)&g_fUrlADFS + (_QWORD)v66);
                goto LABEL_44;
              }
              v8 = 0;
              goto LABEL_45;
            }
          }
          else
          {
            ServerAndObjectPath = -2147024809;
          }
          v8 = 0;
          goto LABEL_45;
        }
      }
    }
    if ( !g_dwHomeRealmCheck )
      goto LABEL_45;
    goto LABEL_21;
  }
LABEL_115:
  operator delete(Block[0]);
  operator delete(v7);
  operator delete(v64[0]);
  operator delete(Str);
  operator delete(v8);
  return (unsigned int)ServerAndObjectPath;
}

```

## disassembly

```asm
0x180044088  mov     r11, rsp
0x18004408b  mov     [r11+20h], r9
0x18004408f  mov     [r11+18h], r8
0x180044093  mov     [r11+10h], rdx
0x180044097  mov     [r11+8], rcx
0x18004409b  push    rbx
0x18004409c  push    rsi
0x18004409d  push    rdi
0x18004409e  push    r12
0x1800440a0  push    r13
0x1800440a2  push    r14
0x1800440a4  push    r15
0x1800440a6  sub     rsp, 70h
0x1800440aa  mov     qword ptr [r11-50h], 0FFFFFFFFFFFFFFFEh
0x1800440b2  mov     rax, r8
0x1800440b5  mov     r14, rdx
0x1800440b8  xor     ebx, ebx
0x1800440ba  mov     edi, ebx
0x1800440bc  mov     r15d, ebx
0x1800440bf  mov     [rsp+0A8h+var_68], rbx
0x1800440c4  mov     [r11-70h], rbx
0x1800440c8  mov     [r11-60h], rbx
0x1800440cc  mov     [r11-78h], rbx
0x1800440d0  mov     esi, ebx
0x1800440d2  cmp     cs:?g_fGlobalOptionUseWinhttp@@3HA, ebx; int g_fGlobalOptionUseWinhttp
0x1800440d8  jnz     loc_1800447BD
0x1800440de  cmp     cs:?g_dwHomeRealmCheck@@3KA, ebx; ulong g_dwHomeRealmCheck
0x1800440e4  jz      loc_1800447BD
0x1800440ea  test    rdx, rdx
0x1800440ed  jz      loc_1800447B8
0x1800440f3  test    rax, rax
0x1800440f6  jz      loc_1800447B8
0x1800440fc  test    r9, r9
0x1800440ff  jz      loc_1800447B8
0x180044105  cmp     [rsp+0A8h+arg_20], rbx
0x18004410d  jz      loc_1800447B8
0x180044113  lea     rcx, ?g_csOptions@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004411a  call    cs:__imp_EnterCriticalSection
0x180044120  cmp     cs:?g_wszHomeRealmQueryString@@3PEAGEA, rbx; ushort * g_wszHomeRealmQueryString
0x180044127  jnz     loc_180044218
0x18004412d  mov     cs:?g_dwHomeRealmCheck@@3KA, ebx; ulong g_dwHomeRealmCheck
0x180044133  lea     r9, [rsp+0A8h+Block]; unsigned __int16 **
0x180044138  lea     r8, ?g_wszFederationHomeRealmKey@@3QBGB; "FederationHomeRealm"
0x18004413f  lea     rdx, ?g_wszMSDRMFederationKey@@3QBGB; "SOFTWARE\\Microsoft\\MSDRM\\Federation"
0x180044146  call    ?GetRegistryKey@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; GetRegistryKey(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x18004414b  or      r12, 0FFFFFFFFFFFFFFFFh
0x18004414f  test    eax, eax
0x180044151  jnz     loc_18004421C
0x180044157  mov     rcx, [rsp+0A8h+Block]
0x18004415c  mov     rax, r12
0x18004415f  inc     rax
0x180044162  cmp     [rcx+rax*2], bx
0x180044166  jnz     short loc_18004415F
0x180044168  test    rax, rax
0x18004416b  jz      loc_18004421C
0x180044171  mov     rcx, [rsp+0A8h+Block]
0x180044176  mov     rax, r12
0x180044179  inc     rax
0x18004417c  cmp     [rcx+rax*2], bx
0x180044180  jnz     short loc_180044179
0x180044182  add     eax, 6
0x180044185  mov     r14d, eax
0x180044188  mov     eax, 2
0x18004418d  mul     r14
0x180044190  cmovb   rax, r12
0x180044194  mov     rcx, rax; unsigned __int64
0x180044197  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18004419c  mov     rsi, rax
0x18004419f  test    rax, rax
0x1800441a2  jnz     short loc_1800441AE
0x1800441a4  mov     edi, 8007000Eh
0x1800441a9  jmp     loc_1800443AB
0x1800441ae  lea     r8, aWhr; "?whr="
0x1800441b5  mov     rdx, r14; unsigned __int64
0x1800441b8  mov     rcx, rsi; unsigned __int16 *
0x1800441bb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800441c0  mov     edi, eax
0x1800441c2  test    eax, eax
0x1800441c4  js      loc_1800443AB
0x1800441ca  mov     r8, [rsp+0A8h+Block]; unsigned __int16 *
0x1800441cf  mov     rdx, r14; unsigned __int64
0x1800441d2  mov     rcx, rsi; unsigned __int16 *
0x1800441d5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800441da  mov     edi, eax
0x1800441dc  test    eax, eax
0x1800441de  js      loc_1800443AB
0x1800441e4  mov     cs:?g_wszHomeRealmQueryString@@3PEAGEA, rsi; ushort * g_wszHomeRealmQueryString
0x1800441eb  call    ?GetDWordRegValue@DRMOS@@YAJPEAUHKEY__@@PEBG1PEAK@Z; DRMOS::GetDWordRegValue(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800441f0  mov     cs:?g_dwHomeRealmCheck@@3KA, 1; ulong g_dwHomeRealmCheck
0x1800441fa  mov     r14, [rsp+0A8h+String1]
0x180044202  jmp     short loc_180044228
0x180044204  mov     edi, dword ptr [rsp+0A8h+arg_0]
0x18004420b  mov     r15, [rsp+0A8h+var_68]
0x180044210  mov     rsi, r15
0x180044213  jmp     loc_1800443AB
0x180044218  or      r12, 0FFFFFFFFFFFFFFFFh
0x18004421c  cmp     cs:?g_dwHomeRealmCheck@@3KA, ebx; ulong g_dwHomeRealmCheck
0x180044222  jz      loc_1800443AB
0x180044228  mov     edi, ebx
0x18004422a  lea     rax, __ImageBase
0x180044231  cmp     edi, cs:?g_cUrlMapping@@3IA; uint g_cUrlMapping
0x180044237  jnb     loc_1800443C4
0x18004423d  mov     esi, edi
0x18004423f  mov     [rsp+0A8h+arg_0], rsi
0x180044247  mov     rdx, rva ?g_pwszUrlMappingFrom@@3PAPEAGA[rax+rsi*8]; String2
0x18004424f  mov     rcx, r14; String1
0x180044252  call    cs:__imp__wcsicmp
0x180044258  test    eax, eax
0x18004425a  jnz     loc_1800443BD
0x180044260  lfence
0x180044263  mov     rax, r12
0x180044266  inc     rax
0x180044269  cmp     [r14+rax*2], bx
0x18004426e  jnz     short loc_180044266
0x180044270  lea     rcx, __ImageBase
0x180044277  lea     r13, rva ?g_pwszUrlMappingTo@@3PAPEAGA[rcx]; ushort * near * g_pwszUrlMappingTo ...
0x18004427e  lea     r13, [r13+rsi*8+0]
0x180044283  cmp     rax, 3E8h
0x180044289  jnb     short loc_18004429F
0x18004428b  mov     r8, [r13+0]
0x18004428f  mov     rdx, r14
0x180044292  lea     rcx, aMsdrmUsingCach_1; "[msdrm]:Using Cache - Server From Url=%"...
0x180044299  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18004429e  nop
0x18004429f  mov     rax, [r13+0]
0x1800442a3  test    rax, rax
0x1800442a6  jz      loc_180044392
0x1800442ac  mov     ecx, 7FFFFFFFh
0x1800442b1  mov     edx, ecx
0x1800442b3  cmp     [rax], bx
0x1800442b6  jz      short loc_1800442C2
0x1800442b8  add     rax, 2
0x1800442bc  sub     rdx, 1
0x1800442c0  jnz     short loc_1800442B3
0x1800442c2  mov     rax, rdx
0x1800442c5  neg     rax
0x1800442c8  sbb     edi, edi
0x1800442ca  not     edi
0x1800442cc  and     edi, 80070057h
0x1800442d2  mov     rax, rdx
0x1800442d5  sub     rcx, rdx
0x1800442d8  neg     rax
0x1800442db  sbb     r8, r8
0x1800442de  and     r8, rcx
0x1800442e1  test    rdx, rdx
0x1800442e4  jz      loc_180044397
0x1800442ea  lea     rsi, [r8+1]
0x1800442ee  cmp     rsi, r8
0x1800442f1  jb      loc_1800447FD
0x1800442f7  mov     rcx, rsi
0x1800442fa  shr     rcx, 20h
0x1800442fe  mov     rax, rcx
0x180044301  shr     rax, 1Fh
0x180044305  test    eax, eax
0x180044307  jnz     loc_180044803
0x18004430d  mov     eax, esi
0x18004430f  add     rax, rax
0x180044312  shl     rcx, 21h
0x180044316  lea     rdx, [rcx+rax]
0x18004431a  cmp     rdx, rax
0x18004431d  jb      loc_180044808
0x180044323  test    rdx, rdx
0x180044326  jz      short loc_180044370
0x180044328  mov     eax, 2
0x18004432d  mul     rsi
0x180044330  cmovb   rax, r12
0x180044334  mov     rcx, rax; unsigned __int64
0x180044337  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18004433c  mov     rcx, [rsp+0A8h+arg_10]
0x180044344  mov     [rcx], rax
0x180044347  test    rax, rax
0x18004434a  jnz     short loc_180044356
0x18004434c  mov     edi, 8007000Eh
0x180044351  mov     rsi, rbx
0x180044354  jmp     short loc_1800443AB
0x180044356  mov     r8, [r13+0]; unsigned __int16 *
0x18004435a  mov     rdx, rsi; unsigned __int64
0x18004435d  mov     rcx, rax; unsigned __int16 *
0x180044360  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180044365  mov     edi, eax
0x180044367  test    eax, eax
0x180044369  jns     short loc_180044370
0x18004436b  mov     rsi, rbx
0x18004436e  jmp     short loc_1800443AB
0x180044370  mov     rax, [rsp+0A8h+arg_0]
0x180044378  lea     rcx, __ImageBase
0x18004437f  mov     eax, rva ?g_fUrlADFS@@3PAHA[rcx+rax*4]; int near * g_fUrlADFS ...
0x180044386  mov     rcx, [rsp+0A8h+arg_18]
0x18004438e  mov     [rcx], eax
0x180044390  jmp     short loc_1800443A8
0x180044392  mov     edi, 80070057h
0x180044397  mov     rsi, rbx
0x18004439a  jmp     short loc_1800443AB
0x18004439c  xor     ebx, ebx
0x18004439e  mov     edi, dword ptr [rsp+0A8h+arg_0]
0x1800443a5  mov     r15, rbx
0x1800443a8  mov     rsi, rbx
0x1800443ab  lea     rcx, ?g_csOptions@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800443b2  call    cs:__imp_LeaveCriticalSection
0x1800443b8  jmp     loc_1800447BD
0x1800443bd  inc     edi
0x1800443bf  jmp     loc_18004422A
0x1800443c4  mov     edi, ebx
0x1800443c6  mov     rcx, r14; unsigned __int16 *
0x1800443c9  cmp     edi, cs:?g_cUrlResolvable@@3IA; uint g_cUrlResolvable
0x1800443cf  jnb     loc_18004452D
0x1800443d5  mov     r13d, edi
0x1800443d8  mov     rdx, rva ?g_pwszUrlResolvable@@3PAPEAGA[rax+r13*8]; String2
0x1800443e0  call    cs:__imp__wcsicmp
0x1800443e6  test    eax, eax
0x1800443e8  jnz     loc_18004451F
0x1800443ee  lfence
0x1800443f1  mov     rax, r12
0x1800443f4  inc     rax
0x1800443f7  cmp     [r14+rax*2], bx
0x1800443fc  jnz     short loc_1800443F4
0x1800443fe  cmp     rax, 3E8h
0x180044404  jnb     short loc_180044416
0x180044406  mov     rdx, r14
0x180044409  lea     rcx, aMsdrmUsingCach; "[msdrm]:Using Cache - UrlResolvable Url"...
0x180044410  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180044415  nop
0x180044416  lea     rax, __ImageBase
0x18004441d  mov     rax, rva ?g_pwszUrlResolvable@@3PAPEAGA[rax+r13*8]; ushort * near * g_pwszUrlResolvable ...
0x180044425  test    rax, rax
0x180044428  jz      loc_180044512
0x18004442e  mov     ecx, 7FFFFFFFh
0x180044433  mov     edx, ecx
0x180044435  cmp     [rax], bx
0x180044438  jz      short loc_180044444
0x18004443a  add     rax, 2
0x18004443e  sub     rdx, 1
0x180044442  jnz     short loc_180044435
0x180044444  mov     rax, rdx
0x180044447  neg     rax
0x18004444a  sbb     edi, edi
0x18004444c  not     edi
0x18004444e  and     edi, 80070057h
0x180044454  mov     rax, rdx
0x180044457  sub     rcx, rdx
0x18004445a  neg     rax
0x18004445d  sbb     r8, r8
0x180044460  and     r8, rcx
0x180044463  test    rdx, rdx
0x180044466  jz      loc_180044517
0x18004446c  lea     rsi, [r8+1]
0x180044470  cmp     rsi, r8
0x180044473  jb      loc_18004480E
0x180044479  mov     rcx, rsi
0x18004447c  shr     rcx, 20h
0x180044480  mov     rax, rcx
0x180044483  shr     rax, 1Fh
0x180044487  test    eax, eax
0x180044489  jnz     loc_180044813
0x18004448f  mov     eax, esi
0x180044491  add     rax, rax
0x180044494  shl     rcx, 21h
0x180044498  lea     rdx, [rcx+rax]
0x18004449c  cmp     rdx, rax
0x18004449f  jb      loc_180044818
0x1800444a5  test    rdx, rdx
0x1800444a8  jz      short loc_180044503
0x1800444aa  mov     eax, 2
0x1800444af  mul     rsi
0x1800444b2  cmovb   rax, r12
0x1800444b6  mov     rcx, rax; unsigned __int64
0x1800444b9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800444be  mov     rcx, [rsp+0A8h+arg_10]
0x1800444c6  mov     [rcx], rax
0x1800444c9  test    rax, rax
0x1800444cc  jnz     short loc_1800444DB
0x1800444ce  mov     edi, 8007000Eh
0x1800444d3  mov     rsi, rbx
0x1800444d6  jmp     loc_1800443AB
0x1800444db  lea     rcx, __ImageBase
0x1800444e2  mov     r8, rva ?g_pwszUrlResolvable@@3PAPEAGA[rcx+r13*8]; unsigned __int16 *
0x1800444ea  mov     rdx, rsi; unsigned __int64
0x1800444ed  mov     rcx, rax; unsigned __int16 *
0x1800444f0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800444f5  mov     edi, eax
0x1800444f7  test    eax, eax
0x1800444f9  jns     short loc_180044503
0x1800444fb  mov     rsi, rbx
0x1800444fe  jmp     loc_1800443AB
0x180044503  mov     rcx, [rsp+0A8h+arg_18]
0x18004450b  mov     [rcx], ebx
0x18004450d  jmp     loc_1800443A8
0x180044512  mov     edi, 80070057h
0x180044517  mov     rsi, rbx
0x18004451a  jmp     loc_1800443AB
0x18004451f  inc     edi
0x180044521  lea     rax, __ImageBase
0x180044528  jmp     loc_1800443C6
0x18004452d  call    ?ResolveUrlWithGET@CHttpBase@@SAJPEBG@Z; CHttpBase::ResolveUrlWithGET(ushort const *)
0x180044532  mov     edi, eax
0x180044534  test    eax, eax
0x180044536  jns     loc_1800443A8
0x18004453c  mov     r14d, 80070057h
0x180044542  cmp     eax, r14d
0x180044545  jz      loc_1800443A8
  ... truncated ...
```
