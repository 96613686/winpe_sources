# CInputProcessorProfiles::GetLanguageProfileDescription(_GUID const &,ushort,_GUID const &,ushort * *)

- ea: `0x180025490`
- end: `0x180025b94`
- name: `?GetLanguageProfileDescription@CInputProcessorProfiles@@UEAAJAEBU_GUID@@G0PEAPEAG@Z`
- size: `1796`
- prototype: `__int64 __fastcall(CInputProcessorProfiles *__hidden this, const struct _GUID *, unsigned __int16, const struct _GUID *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000fac0`
- `0x1800139a4`
- `0x180025490`
- `0x1800267c0`
- `0x1800539d8`
- `0x18005d0f0`
- `0x18009eaea`
- `0x180106a60`

## import_xrefs

- `msvcrt!wcsnlen` at `0x18002575c`
- `msvcrt!wcsnlen` at `0x18002575c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025940`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800259f5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025b6b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025940`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800259f5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025b6b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800257ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025878`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800257ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025878`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025893`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800258ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800258ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800259a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800259af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025893`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800258ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800258ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800259a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800259af`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180025a2b`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180025a2b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025b3e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025b3e`
- `OLEAUT32!__imp_SysAllocString` at `0x180025982`
- `OLEAUT32!__imp_SysAllocString` at `0x180025982`

## pseudocode

```c
__int64 __fastcall CInputProcessorProfiles::GetLanguageProfileDescription(
        CInputProcessorProfiles *this,
        const struct _GUID *a2,
        unsigned __int16 a3,
        struct _GUID *a4,
        unsigned __int16 **a5)
{
  unsigned int v5; // r12d
  HKEY v7; // rsi
  __int64 v8; // r14
  const WCHAR *v9; // r8
  wchar_t *v10; // rax
  __int64 v11; // rcx
  int v12; // edi
  __int64 v13; // rdx
  wchar_t *v14; // rcx
  int v15; // r8d
  unsigned int i; // r9d
  __int64 v17; // rcx
  __int64 v18; // rdx
  unsigned int v19; // edx
  HKEY v20; // r13
  wchar_t *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  wchar_t *v24; // r9
  __int64 v25; // rcx
  wchar_t *v26; // rdx
  __int64 v27; // rax
  wchar_t *v28; // rcx
  __int64 v29; // rdx
  wchar_t *v30; // rax
  __int64 v31; // r8
  const WCHAR *v32; // r9
  __int64 v33; // rcx
  wchar_t *v34; // rdx
  __int64 v35; // rax
  wchar_t *v36; // rcx
  __int64 v37; // rdx
  wchar_t *v38; // rax
  __int64 v39; // r8
  const unsigned __int16 *v40; // rcx
  wchar_t *v41; // rdx
  __int64 v42; // rax
  wchar_t *v43; // rcx
  unsigned int v44; // eax
  unsigned __int64 v45; // rbx
  unsigned __int16 *v46; // r15
  HKEY v47; // rbx
  HKEY v48; // r10
  int v49; // edx
  unsigned int j; // r8d
  __int64 v51; // r9
  __int64 v52; // rcx
  HKEY v53; // r14
  LSTATUS v54; // r14d
  unsigned int v55; // r15d
  LSTATUS Value; // eax
  void **v58; // r9
  int IndirectString; // r14d
  BYTE *v60; // r12
  BSTR v61; // rax
  unsigned int v62; // edi
  LSTATUS v63; // eax
  unsigned __int64 v64; // rax
  HKEY phkResult; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  void **v67; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v68; // [rsp+48h] [rbp-B8h]
  _QWORD v69[2]; // [rsp+50h] [rbp-B0h] BYREF
  _WORD v70[40]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Source[256]; // [rsp+B0h] [rbp-50h] BYREF
  BYTE Data[2]; // [rsp+2B0h] [rbp+1B0h] BYREF

  phkResult = (HKEY)a4;
  v5 = a3;
  hKey = (HKEY)a5;
  v67 = &CPreloadRegKey::`vftable';
  v7 = 0;
  v68 = 0;
  v69[1] = 0;
  v69[0] = &CRegKeyMUI::`vftable';
  if ( !a5 )
  {
    v69[0] = &CPreloadRegKey::`vftable';
    CInputDllRegKey::Close((CInputDllRegKey *)v69);
    v55 = -2147024809;
    goto LABEL_89;
  }
  v8 = 2147483646;
  v9 = L"SOFTWARE\\Microsoft\\CTF\\TIP\\";
  v10 = Source;
  v11 = 2147483646;
  v12 = 1;
  v13 = 256;
  do
  {
    if ( !v11 )
      break;
    if ( !*v9 )
      break;
    *v10++ = *v9++;
    --v11;
    --v13;
  }
  while ( v13 );
  v14 = v10 - 1;
  if ( v13 )
    v14 = v10;
  *v14 = 0;
  memset_0(v70, 0, 0x4Eu);
  v70[0] = 123;
  v15 = 1;
  for ( i = 0; i < 0x14; ++i )
  {
    if ( v15 >= 36 )
      break;
    v17 = v15;
    v18 = *((unsigned __int8 *)qword_18011F820 + (int)i);
    if ( (_BYTE)v18 == 45 )
    {
      v70[v15] = 45;
    }
    else
    {
      v19 = *((unsigned __int8 *)&a2->Data1 + v18);
      ++v15;
      v70[v17] = word_18011F7F0[(unsigned __int64)v19 >> 4];
      v70[v15] = word_18011F7F0[v19 & 0xF];
    }
    ++v15;
  }
  v20 = hKey;
  v21 = Source;
  v22 = 256;
  *(_DWORD *)&v70[v15] = 125;
  do
  {
    if ( !*v21 )
      break;
    ++v21;
    --v22;
  }
  while ( v22 );
  v23 = (256 - v22) & -(__int64)(v22 != 0);
  if ( v22 )
  {
    v24 = v70;
    v25 = 2147483646;
    v26 = &Source[v23];
    v27 = 256 - v23;
    if ( v23 != 256 )
    {
      do
      {
        if ( !v25 )
          break;
        if ( !*v24 )
          break;
        *v26++ = *v24++;
        --v25;
        --v27;
      }
      while ( v27 );
    }
    v28 = v26 - 1;
    if ( v27 )
      v28 = v26;
    *v28 = 0;
  }
  v29 = 256;
  v30 = Source;
  do
  {
    if ( !*v30 )
      break;
    ++v30;
    --v29;
  }
  while ( v29 );
  v31 = (256 - v29) & -(__int64)(v29 != 0);
  if ( v29 )
  {
    v32 = L"\\";
    v33 = 2147483646;
    v34 = &Source[v31];
    v35 = 256 - v31;
    if ( v31 != 256 )
    {
      do
      {
        if ( !v33 )
          break;
        if ( !*v32 )
          break;
        *v34++ = *v32++;
        --v33;
        --v35;
      }
      while ( v35 );
    }
    v36 = v34 - 1;
    if ( v35 )
      v36 = v34;
    *v36 = 0;
  }
  v37 = 256;
  v38 = Source;
  do
  {
    if ( !*v38 )
      break;
    ++v38;
    --v37;
  }
  while ( v37 );
  v39 = (256 - v37) & -(__int64)(v37 != 0);
  if ( v37 )
  {
    v40 = L"LanguageProfile\\";
    v41 = &Source[v39];
    v42 = 256 - v39;
    if ( v39 != 256 )
    {
      do
      {
        if ( !v8 )
          break;
        if ( !*v40 )
          break;
        *v41++ = *v40++;
        --v8;
        --v42;
      }
      while ( v42 );
    }
    v43 = v41 - 1;
    if ( v42 )
      v43 = v41;
    *v43 = 0;
  }
  v44 = wcsnlen(Source, 0x100u);
  v45 = 256LL - v44;
  v46 = &Source[v44];
  StringCchPrintfW(v46, v45, L"0x%08x", v5);
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, Source, 0, 0x20019u, &hKey) )
  {
    StringCchPrintfW(v46, v45, L"0x%08x", v5 & 0x3FF);
    if ( !CMyRegKey::Open((CMyRegKey *)&v67, HKEY_LOCAL_MACHINE, Source, 0x20019u)
      || (StringCchPrintfW(v46, v45, L"0x0000ffff"),
          !CMyRegKey::Open((CMyRegKey *)&v67, HKEY_LOCAL_MACHINE, Source, 0x20019u)) )
    {
      v47 = v68;
      goto LABEL_48;
    }
    v69[0] = &CPreloadRegKey::`vftable';
    CInputDllRegKey::Close((CInputDllRegKey *)v69);
    v67 = &CPreloadRegKey::`vftable';
    v55 = -2147467259;
LABEL_89:
    CInputDllRegKey::Close((CInputDllRegKey *)&v67);
    return v55;
  }
  v47 = hKey;
LABEL_48:
  v48 = phkResult;
  v49 = 1;
  Source[0] = 123;
  for ( j = 0; j < 0x14; ++j )
  {
    if ( v49 >= 36 )
      break;
    v51 = v49;
    v52 = *((unsigned __int8 *)qword_18011F820 + (int)j);
    if ( (_BYTE)v52 == 45 )
    {
      Source[v49] = 45;
    }
    else
    {
      ++v49;
      Source[v51] = word_18011F7F0[(unsigned __int64)*((unsigned __int8 *)v48 + v52) >> 4];
      Source[v49] = word_18011F7F0[*((_BYTE *)v48 + v52) & 0xF];
    }
    ++v49;
  }
  v53 = v47;
  phkResult = 0;
  hKey = 0;
  *(_DWORD *)&Source[v49] = 125;
  if ( v47 == HKEY_CURRENT_USER && !RegOpenCurrentUser(0x20019u, &hKey) )
    v53 = hKey;
  v54 = RegOpenKeyExW(v53, Source, 0, 0x20019u, &phkResult);
  if ( !v54 )
    v7 = phkResult;
  if ( hKey )
    RegCloseKey(hKey);
  v55 = -2147467259;
  if ( v54 )
    goto LABEL_59;
  *(_WORD *)Data = 0;
  if ( (unsigned __int64)v7 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    goto LABEL_80;
  LODWORD(phkResult) = 520;
  Value = RegQueryValueExW(v7, L"Display Description", 0, 0, Data, (LPDWORD)&phkResult);
  if ( Value )
  {
    if ( Value != 234 )
      goto LABEL_80;
  }
  IndirectString = -2147467259;
  if ( Value != 234 )
  {
    v60 = Data;
    v12 = 0;
    goto LABEL_70;
  }
  v64 = 2 * ((unsigned __int64)(unsigned int)((_DWORD)phkResult + 1) >> 1);
  if ( !is_mul_ok((unsigned __int64)(unsigned int)((_DWORD)phkResult + 1) >> 1, 2u) )
    LODWORD(v64) = -1;
  v60 = (BYTE *)LocalAlloc(0x40u, (unsigned int)v64);
  if ( v60 )
  {
    Value = RegQueryValueExW(v7, L"Display Description", 0, 0, v60, (LPDWORD)&phkResult);
LABEL_70:
    if ( !Value )
      IndirectString = LoadIndirectString((const unsigned __int16 *)v60, (unsigned __int16 *)Data, 0x104u, v58);
    if ( v12 && v60 )
      cicMemFree(v60);
    if ( !IndirectString )
      goto LABEL_74;
  }
LABEL_80:
  LODWORD(phkResult) = 520;
  LODWORD(hKey) = 0;
  v63 = RegQueryValueExW(v7, L"Description", 0, (LPDWORD)&hKey, Data, (LPDWORD)&phkResult);
  *(_WORD *)&Data[v63 == 0 ? 0x206 : 0] = 0;
  if ( v63 )
  {
LABEL_59:
    if ( v7 )
      RegCloseKey(v7);
    if ( v47 )
      RegCloseKey(v47);
    return v55;
  }
LABEL_74:
  v61 = SysAllocString((const OLECHAR *)Data);
  *(_QWORD *)v20 = v61;
  v62 = v61 == 0 ? 0x8007000E : 0;
  if ( v7 )
    RegCloseKey(v7);
  if ( v47 )
    RegCloseKey(v47);
  return v62;
}

```

## disassembly

```asm
0x180025490  push    rbp
0x180025492  push    rbx
0x180025493  push    rsi
0x180025494  push    rdi
0x180025495  push    r12
0x180025497  push    r13
0x180025499  push    r14
0x18002549b  push    r15
0x18002549d  lea     rbp, [rsp-3D8h]
0x1800254a5  sub     rsp, 4D8h
0x1800254ac  mov     rax, cs:__security_cookie
0x1800254b3  xor     rax, rsp
0x1800254b6  mov     [rbp+410h+var_50], rax
0x1800254bd  mov     r13, [rbp+410h+arg_20]
0x1800254c4  lea     rcx, ??_7CPreloadRegKey@@6B@; const CPreloadRegKey::`vftable'
0x1800254cb  xor     r10d, r10d
0x1800254ce  mov     [rsp+510h+var_4E0], r9
0x1800254d3  movzx   r12d, r8w
0x1800254d7  lea     rax, ??_7CRegKeyMUI@@6B@; const CRegKeyMUI::`vftable'
0x1800254de  mov     [rsp+510h+hKey], r13
0x1800254e3  mov     r15, rdx
0x1800254e6  mov     [rsp+510h+var_4D0], rcx
0x1800254eb  mov     esi, r10d
0x1800254ee  mov     [rsp+510h+var_4C8], r10
0x1800254f3  mov     [rsp+510h+var_4B8], r10
0x1800254f8  mov     [rsp+510h+var_4C0], rax
0x1800254fd  test    r13, r13
0x180025500  jz      loc_180025A5B
0x180025506  mov     r14d, 7FFFFFFEh
0x18002550c  lea     r8, ?c_szCTFTIPKey@@3QBGB; "SOFTWARE\\Microsoft\\CTF\\TIP\\"
0x180025513  mov     ebx, 100h
0x180025518  lea     rax, [rbp+410h+Source]
0x18002551c  mov     ecx, r14d
0x18002551f  lea     edi, [r10+1]
0x180025523  mov     edx, ebx
0x180025525  test    rcx, rcx
0x180025528  jz      short loc_180025548
0x18002552a  movzx   r9d, word ptr [r8]
0x18002552e  test    r9w, r9w
0x180025532  jz      short loc_180025548
0x180025534  mov     [rax], r9w
0x180025538  add     r8, 2
0x18002553c  add     rax, 2
0x180025540  sub     rcx, rdi
0x180025543  sub     rdx, rdi
0x180025546  jnz     short loc_180025525
0x180025548  test    rdx, rdx
0x18002554b  lea     rcx, [rax-2]
0x18002554f  cmovnz  rcx, rax
0x180025553  xor     edx, edx; Val
0x180025555  mov     [rcx], r10w
0x180025559  lea     r8d, [rdx+4Eh]; Size
0x18002555d  lea     rcx, [rsp+510h+var_4B0]; void *
0x180025562  call    memset_0
0x180025567  mov     eax, 7Bh ; '{'
0x18002556c  lea     r13, __ImageBase
0x180025573  xor     r10d, r10d
0x180025576  mov     [rsp+510h+var_4B0], ax
0x18002557b  mov     r8d, edi
0x18002557e  mov     r9d, r10d
0x180025581  lea     r11d, [rax-4Eh]
0x180025585  cmp     r8d, 24h ; '$'
0x180025589  jge     short loc_1800255DF
0x18002558b  movsxd  rax, r9d
0x18002558e  movsxd  rcx, r8d
0x180025591  movzx   edx, byte ptr [rax+r13+11F820h]
0x18002559a  cmp     dl, r11b
0x18002559d  jz      loc_1800258E6
0x1800255a3  movzx   edx, byte ptr [rdx+r15]
0x1800255a8  inc     r8d
0x1800255ab  mov     eax, edx
0x1800255ad  shr     rax, 4
0x1800255b1  and     edx, 0Fh
0x1800255b4  movzx   eax, ds:rva word_18011F7F0[r13+rax*2]
0x1800255bd  mov     [rsp+rcx*2+510h+var_4B0], ax
0x1800255c2  movzx   eax, ds:rva word_18011F7F0[r13+rdx*2]
0x1800255cb  movsxd  rcx, r8d
0x1800255ce  mov     [rsp+rcx*2+510h+var_4B0], ax
0x1800255d3  add     r9d, edi
0x1800255d6  inc     r8d
0x1800255d9  cmp     r9d, 14h
0x1800255dd  jb      short loc_180025585
0x1800255df  mov     r13, [rsp+510h+hKey]
0x1800255e4  lea     rax, [rbp+410h+Source]
0x1800255e8  movsxd  rcx, r8d
0x1800255eb  mov     rdx, rbx
0x1800255ee  mov     dword ptr [rsp+rcx*2+510h+var_4B0], 7Dh ; '}'
0x1800255f6  cmp     [rax], r10w
0x1800255fa  jz      short loc_180025605
0x1800255fc  add     rax, 2
0x180025600  sub     rdx, rdi
0x180025603  jnz     short loc_1800255F6
0x180025605  mov     rcx, rbx
0x180025608  mov     rax, rdx
0x18002560b  sub     rcx, rdx
0x18002560e  neg     rax
0x180025611  sbb     r8, r8
0x180025614  and     r8, rcx
0x180025617  test    rdx, rdx
0x18002561a  jz      short loc_180025666
0x18002561c  mov     rax, rbx
0x18002561f  lea     rdx, [rbp+410h+Source]
0x180025623  lea     r9, [rsp+510h+var_4B0]
0x180025628  mov     rcx, r14
0x18002562b  lea     rdx, [rdx+r8*2]
0x18002562f  sub     rax, r8
0x180025632  jz      short loc_180025657
0x180025634  test    rcx, rcx
0x180025637  jz      short loc_180025657
0x180025639  movzx   r8d, word ptr [r9]
0x18002563d  test    r8w, r8w
0x180025641  jz      short loc_180025657
0x180025643  mov     [rdx], r8w
0x180025647  add     r9, 2
0x18002564b  add     rdx, 2
0x18002564f  sub     rcx, rdi
0x180025652  sub     rax, rdi
0x180025655  jnz     short loc_180025634
0x180025657  test    rax, rax
0x18002565a  lea     rcx, [rdx-2]
0x18002565e  cmovnz  rcx, rdx
0x180025662  mov     [rcx], r10w
0x180025666  mov     rdx, rbx
0x180025669  lea     rax, [rbp+410h+Source]
0x18002566d  cmp     [rax], r10w
0x180025671  jz      short loc_18002567C
0x180025673  add     rax, 2
0x180025677  sub     rdx, rdi
0x18002567a  jnz     short loc_18002566D
0x18002567c  mov     rcx, rbx
0x18002567f  mov     rax, rdx
0x180025682  sub     rcx, rdx
0x180025685  neg     rax
0x180025688  sbb     r8, r8
0x18002568b  and     r8, rcx
0x18002568e  test    rdx, rdx
0x180025691  jz      short loc_1800256DF
0x180025693  mov     rax, rbx
0x180025696  lea     rdx, [rbp+410h+Source]
0x18002569a  lea     r9, SubBlock; "\\"
0x1800256a1  mov     rcx, r14
0x1800256a4  lea     rdx, [rdx+r8*2]
0x1800256a8  sub     rax, r8
0x1800256ab  jz      short loc_1800256D0
0x1800256ad  test    rcx, rcx
0x1800256b0  jz      short loc_1800256D0
0x1800256b2  movzx   r8d, word ptr [r9]
0x1800256b6  test    r8w, r8w
0x1800256ba  jz      short loc_1800256D0
0x1800256bc  mov     [rdx], r8w
0x1800256c0  add     r9, 2
0x1800256c4  add     rdx, 2
0x1800256c8  sub     rcx, rdi
0x1800256cb  sub     rax, rdi
0x1800256ce  jnz     short loc_1800256AD
0x1800256d0  test    rax, rax
0x1800256d3  lea     rcx, [rdx-2]
0x1800256d7  cmovnz  rcx, rdx
0x1800256db  mov     [rcx], r10w
0x1800256df  mov     rdx, rbx
0x1800256e2  lea     rax, [rbp+410h+Source]
0x1800256e6  cmp     [rax], r10w
0x1800256ea  jz      short loc_1800256F5
0x1800256ec  add     rax, 2
0x1800256f0  sub     rdx, rdi
0x1800256f3  jnz     short loc_1800256E6
0x1800256f5  mov     rcx, rbx
0x1800256f8  mov     rax, rdx
0x1800256fb  sub     rcx, rdx
0x1800256fe  neg     rax
0x180025701  sbb     r8, r8
0x180025704  and     r8, rcx
0x180025707  test    rdx, rdx
0x18002570a  jz      short loc_180025755
0x18002570c  mov     rax, rbx
0x18002570f  lea     rdx, [rbp+410h+Source]
0x180025713  lea     rcx, ?c_szLanguageProfileKey@@3QBGB; "LanguageProfile\\"
0x18002571a  lea     rdx, [rdx+r8*2]
0x18002571e  sub     rax, r8
0x180025721  jz      short loc_180025746
0x180025723  test    r14, r14
0x180025726  jz      short loc_180025746
0x180025728  movzx   r8d, word ptr [rcx]
0x18002572c  test    r8w, r8w
0x180025730  jz      short loc_180025746
0x180025732  mov     [rdx], r8w
0x180025736  add     rcx, 2
0x18002573a  add     rdx, 2
0x18002573e  sub     r14, rdi
0x180025741  sub     rax, rdi
0x180025744  jnz     short loc_180025723
0x180025746  test    rax, rax
0x180025749  lea     rcx, [rdx-2]
0x18002574d  cmovnz  rcx, rdx
0x180025751  mov     [rcx], r10w
0x180025755  mov     rdx, rbx; MaxCount
0x180025758  lea     rcx, [rbp+410h+Source]; Source
0x18002575c  call    cs:__imp_wcsnlen
0x180025762  mov     ecx, eax
0x180025764  lea     r15, [rbp+410h+Source]
0x180025768  mov     r9d, r12d
0x18002576b  lea     r8, a0x08x; "0x%08x"
0x180025772  sub     rbx, rcx
0x180025775  mov     r14d, r12d
0x180025778  mov     rdx, rbx; unsigned __int64
0x18002577b  lea     r15, [r15+rcx*2]
0x18002577f  mov     rcx, r15; unsigned __int16 *
0x180025782  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180025787  lea     rax, [rsp+510h+hKey]
0x18002578c  xor     r12d, r12d
0x18002578f  mov     r9d, 20019h; samDesired
0x180025795  mov     [rsp+510h+phkResult], rax; phkResult
0x18002579a  xor     r8d, r8d; ulOptions
0x18002579d  mov     [rsp+510h+hKey], r12
0x1800257a2  lea     rdx, [rbp+410h+Source]; lpSubKey
0x1800257a6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800257ad  call    cs:__imp_RegOpenKeyExW
0x1800257b3  test    eax, eax
0x1800257b5  jnz     loc_180025A75
0x1800257bb  mov     rbx, [rsp+510h+hKey]
0x1800257c0  mov     r10, [rsp+510h+var_4E0]
0x1800257c5  lea     r14, __ImageBase
0x1800257cc  mov     eax, 7Bh ; '{'
0x1800257d1  mov     edx, edi
0x1800257d3  mov     [rbp+410h+Source], ax
0x1800257d7  mov     r8d, r12d
0x1800257da  lea     r11d, [rax-4Eh]
0x1800257de  cmp     edx, 24h ; '$'
0x1800257e1  jge     short loc_180025839
0x1800257e3  movsxd  rax, r8d
0x1800257e6  movsxd  r9, edx
0x1800257e9  movzx   ecx, byte ptr [rax+r14+11F820h]
0x1800257f2  cmp     cl, r11b
0x1800257f5  jz      loc_1800258F1
0x1800257fb  movzx   eax, byte ptr [rcx+r10]
0x180025800  inc     edx
0x180025802  shr     rax, 4
0x180025806  movzx   eax, ds:rva word_18011F7F0[r14+rax*2]
0x18002580f  mov     [rbp+r9*2+410h+Source], ax
0x180025815  movzx   eax, byte ptr [rcx+r10]
0x18002581a  and     eax, 0Fh
0x18002581d  movsxd  rcx, edx
0x180025820  movzx   eax, ds:rva word_18011F7F0[r14+rax*2]
0x180025829  mov     [rbp+rcx*2+410h+Source], ax
0x18002582e  add     r8d, edi
0x180025831  inc     edx
0x180025833  cmp     r8d, 14h
0x180025837  jb      short loc_1800257DE
0x180025839  movsxd  rcx, edx
0x18002583c  mov     r14, rbx
0x18002583f  mov     [rsp+510h+var_4E0], r12
0x180025844  mov     [rsp+510h+hKey], r12
0x180025849  mov     dword ptr [rbp+rcx*2+410h+Source], 7Dh ; '}'
0x180025851  cmp     rbx, 0FFFFFFFF80000001h
0x180025858  jz      loc_180025A21
0x18002585e  lea     rax, [rsp+510h+var_4E0]
0x180025863  mov     r9d, 20019h; samDesired
0x180025869  xor     r8d, r8d; ulOptions
0x18002586c  mov     [rsp+510h+phkResult], rax; phkResult
0x180025871  lea     rdx, [rbp+410h+Source]; lpSubKey
0x180025875  mov     rcx, r14; hKey
0x180025878  call    cs:__imp_RegOpenKeyExW
0x18002587e  mov     rcx, [rsp+510h+hKey]; hKey
0x180025883  test    eax, eax
0x180025885  mov     r14d, eax
0x180025888  cmovz   rsi, [rsp+510h+var_4E0]
0x18002588e  test    rcx, rcx
0x180025891  jz      short loc_180025899
0x180025893  call    cs:__imp_RegCloseKey
0x180025899  mov     r15d, 80004005h
0x18002589f  test    r14d, r14d
0x1800258a2  jz      short loc_1800258FC
0x1800258a4  test    rsi, rsi
0x1800258a7  jz      short loc_1800258B2
0x1800258a9  mov     rcx, rsi; hKey
0x1800258ac  call    cs:__imp_RegCloseKey
0x1800258b2  test    rbx, rbx
0x1800258b5  jz      short loc_1800258C0
0x1800258b7  mov     rcx, rbx; hKey
0x1800258ba  call    cs:__imp_RegCloseKey
0x1800258c0  mov     eax, r15d
0x1800258c3  mov     rcx, [rbp+410h+var_50]
0x1800258ca  xor     rcx, rsp; StackCookie
0x1800258cd  call    __security_check_cookie
0x1800258d2  add     rsp, 4D8h
0x1800258d9  pop     r15
0x1800258db  pop     r14
0x1800258dd  pop     r13
0x1800258df  pop     r12
0x1800258e1  pop     rdi
0x1800258e2  pop     rsi
0x1800258e3  pop     rbx
0x1800258e4  pop     rbp
0x1800258e5  retn
0x1800258e6  mov     [rsp+rcx*2+510h+var_4B0], r11w
0x1800258ec  jmp     loc_1800255D3
0x1800258f1  mov     [rbp+r9*2+410h+Source], r11w
0x1800258f7  jmp     loc_18002582E
0x1800258fc  lea     rax, [rsi-1]
0x180025900  mov     word ptr [rbp+410h+Data], r12w
  ... truncated ...
```
