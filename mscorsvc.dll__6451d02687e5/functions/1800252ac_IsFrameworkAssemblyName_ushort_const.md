# IsFrameworkAssemblyName(ushort const *)

- ea: `0x1800252ac`
- end: `0x18002587c`
- name: `?IsFrameworkAssemblyName@@YA_NPEBG@Z`
- size: `1488`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18002587c`
- `0x18002f454`

## callees

- `0x1800251bc`
- `0x1800252ac`
- `0x18002a174`
- `0x180030b1c`
- `0x180030d84`
- `0x180038d60`
- `0x18003dc30`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800257b9`
- `KERNEL32!HeapFree` at `0x180025802`
- `KERNEL32!HeapFree` at `0x18002583f`
- `KERNEL32!HeapFree` at `0x1800257b9`
- `KERNEL32!HeapFree` at `0x180025802`
- `KERNEL32!HeapFree` at `0x18002583f`
- `KERNEL32!GetProcessHeap` at `0x1800257a4`
- `KERNEL32!GetProcessHeap` at `0x1800257ed`
- `KERNEL32!GetProcessHeap` at `0x18002582a`
- `KERNEL32!GetProcessHeap` at `0x1800257a4`
- `KERNEL32!GetProcessHeap` at `0x1800257ed`
- `KERNEL32!GetProcessHeap` at `0x18002582a`
- `VCRUNTIME140_CLR0400!wcschr` at `0x1800252eb`
- `VCRUNTIME140_CLR0400!wcschr` at `0x180025398`
- `VCRUNTIME140_CLR0400!wcschr` at `0x1800253a8`
- `VCRUNTIME140_CLR0400!wcschr` at `0x1800253f5`
- `VCRUNTIME140_CLR0400!wcschr` at `0x1800252eb`
- `VCRUNTIME140_CLR0400!wcschr` at `0x180025398`
- `VCRUNTIME140_CLR0400!wcschr` at `0x1800253a8`
- `VCRUNTIME140_CLR0400!wcschr` at `0x1800253f5`
- `VCRUNTIME140_CLR0400!wcsstr` at `0x180025338`
- `VCRUNTIME140_CLR0400!wcsstr` at `0x18002534b`
- `VCRUNTIME140_CLR0400!wcsstr` at `0x18002535e`
- `VCRUNTIME140_CLR0400!wcsstr` at `0x180025338`
- `VCRUNTIME140_CLR0400!wcsstr` at `0x18002534b`
- `VCRUNTIME140_CLR0400!wcsstr` at `0x18002535e`
- `ucrtbase_clr0400!_wcsnicmp` at `0x18002531c`
- `ucrtbase_clr0400!_wcsnicmp` at `0x1800253e2`
- `ucrtbase_clr0400!_wcsnicmp` at `0x18002542e`
- `ucrtbase_clr0400!_wcsnicmp` at `0x180025636`
- `ucrtbase_clr0400!_wcsnicmp` at `0x18002568f`
- `ucrtbase_clr0400!_wcsnicmp` at `0x18002531c`
- `ucrtbase_clr0400!_wcsnicmp` at `0x1800253e2`
- `ucrtbase_clr0400!_wcsnicmp` at `0x18002542e`
- `ucrtbase_clr0400!_wcsnicmp` at `0x180025636`
- `ucrtbase_clr0400!_wcsnicmp` at `0x18002568f`

## string_xrefs

- `0x180025354`: `PublicKeyToken=`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
char __fastcall IsFrameworkAssemblyName(const unsigned __int16 *a1)
{
  wchar_t *v2; // rax
  const wchar_t *v3; // rdi
  __int64 v4; // rsi
  wchar_t *v6; // r12
  wchar_t *v7; // rbx
  wchar_t *v8; // rax
  const wchar_t *v9; // r12
  const wchar_t *v10; // rbx
  const wchar_t *v11; // r14
  wchar_t *v12; // rax
  __int64 v13; // rax
  wchar_t *v14; // rax
  size_t v15; // rbx
  unsigned __int16 *v16; // r8
  unsigned int i; // r9d
  unsigned __int16 v18; // cx
  unsigned __int16 v19; // dx
  unsigned __int16 *v20; // r9
  unsigned int v21; // r10d
  unsigned __int16 j; // r8
  unsigned __int16 v23; // dx
  int v24; // eax
  unsigned __int16 **v25; // r8
  char v26; // di
  int v27; // eax
  char *v28; // r15
  int v29; // eax
  __int64 v30; // rcx
  const unsigned __int16 *const near *v31; // rdx
  __int64 v32; // rax
  int v33; // eax
  __int64 v34; // rcx
  const wchar_t *v35; // rcx
  __int64 v36; // rax
  __int64 v37; // rcx
  int v38; // r8d
  int v39; // eax
  int v40; // r8d
  __int64 v41; // rcx
  const unsigned __int16 *const near *v42; // rdx
  void *v43; // r15
  HANDLE ProcessHeap; // rax
  void *v45; // rbx
  HANDLE v46; // rax
  void *v47; // rbx
  HANDLE v48; // rax
  int v49; // [rsp+28h] [rbp-E0h] BYREF
  __int64 v50; // [rsp+30h] [rbp-D8h] BYREF
  wchar_t *v51; // [rsp+38h] [rbp-D0h]
  unsigned __int16 **v52; // [rsp+40h] [rbp-C8h]
  _QWORD v53[2]; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v54[2]; // [rsp+58h] [rbp-B0h] BYREF
  int v55; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v56; // [rsp+6Ch] [rbp-9Ch]
  LPVOID v57; // [rsp+78h] [rbp-90h]
  __int16 v58; // [rsp+80h] [rbp-88h] BYREF
  int v59; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v60; // [rsp+ACh] [rbp-5Ch]
  LPVOID lpMem; // [rsp+B8h] [rbp-50h]
  __int16 v62; // [rsp+C0h] [rbp-48h] BYREF
  wchar_t String1[256]; // [rsp+2C8h] [rbp+1C0h] BYREF
  __int64 v64; // [rsp+4C8h] [rbp+3C0h]

  v2 = wcschr(a1, 0x2Cu);
  v3 = v2;
  if ( !v2 )
    return 0;
  v4 = v2 - a1;
  if ( v4 == 8 && !_wcsnicmp(a1, L"mscorlib", 8u) )
    return 1;
  v6 = wcsstr(v3, L"Version=");
  v7 = wcsstr(v3, L"Culture=");
  v8 = wcsstr(v3, L"PublicKeyToken=");
  if ( !v6 || !v7 || !v8 )
    return 0;
  v9 = v6 + 8;
  v10 = v7 + 8;
  v11 = v8 + 15;
  v51 = wcschr(v9, 0x2Cu);
  v12 = wcschr(v10, 0x2Cu);
  if ( v12 )
  {
    v13 = v12 - v10;
  }
  else
  {
    v13 = -1;
    do
      ++v13;
    while ( v10[v13] );
  }
  if ( v13 != 7 || _wcsnicmp(v10, L"neutral", 7u) )
    return 0;
  v14 = wcschr(v11, 0x2Cu);
  if ( v14 )
  {
    v15 = v14 - v11;
  }
  else
  {
    v15 = -1;
    do
      ++v15;
    while ( v11[v15] );
  }
  if ( v15 == 4 && !_wcsnicmp(v11, L"null", 4u) )
    return 0;
  v56 = 32;
  v57 = &v58;
  v55 = 2;
  v58 = 0;
  SString::Set((SString *)&v55, a1, v4);
  SString::ConvertToUnicode((SString *)&v55);
  v16 = (unsigned __int16 *)v57;
  for ( i = 0; ; i = v18 + 65599 * i )
  {
    v19 = *v16;
    if ( !*v16 )
      break;
    ++v16;
    v18 = v19 + 32;
    if ( (unsigned __int16)(v19 - 65) > 0x19u )
      v18 = v19;
  }
  v53[1] = &g_arFxPolicy47_HashCollision;
  v53[0] = (char *)&g_arFxPolicy47_Hash + 4 * (i % 0xEF);
  SString::ConvertToUnicode((SString *)&v55);
  v20 = (unsigned __int16 *)v57;
  v21 = 0;
  for ( j = *(_WORD *)v57; *v20; j = *v20 )
  {
    ++v20;
    v23 = j + 32;
    if ( (unsigned __int16)(j - 65) > 0x19u )
      v23 = j;
    v21 = v23 + 65599 * v21;
  }
  v54[1] = &g_arFxPolicy471_HashCollision;
  v54[0] = (char *)&g_arFxPolicy471_Hash + 4 * (v21 % 0xEF);
  v24 = IsRunningOn47OrBelow();
  v25 = (unsigned __int16 **)v53;
  if ( !v24 )
    v25 = (unsigned __int16 **)v54;
  v52 = v25;
  v26 = 1;
  while ( 1 )
  {
    v27 = **v25 - 1;
    *v25 = &v25[1][2 * (*v25)[1]];
    if ( v27 < 0 )
    {
      v26 = 0;
      goto LABEL_72;
    }
    v28 = (char *)g_arFxPolicy + 6 * v27;
    v29 = IsRunningOn47OrBelow();
    v30 = (unsigned __int8)v28[4];
    if ( v29 )
      v31 = (&FxPolicyHelper47::g_rgAssemblyKeyVersionStrings)[v30];
    else
      v31 = (&FxPolicyHelper::g_rgAssemblyKeyVersionStrings)[v30];
    v32 = -1;
    do
      ++v32;
    while ( *((_WORD *)v31 + v32) );
    if ( v32 != v15 )
      goto LABEL_64;
    v33 = IsRunningOn47OrBelow();
    v34 = (unsigned __int8)v28[4];
    v35 = (const wchar_t *)(v33
                          ? (&FxPolicyHelper47::g_rgAssemblyKeyVersionStrings)[v34]
                          : (&FxPolicyHelper::g_rgAssemblyKeyVersionStrings)[v34]);
    if ( _wcsnicmp(v35, v11, v15) )
      goto LABEL_64;
    String1[0] = 0;
    v64 = 0;
    FrameworkConfig::GetFxAssemblyName<unsigned short>((__int64)v28, (__int64)String1);
    v36 = -1;
    do
      ++v36;
    while ( String1[v36] );
    if ( v36 != v4 || _wcsnicmp(String1, a1, v4) )
      goto LABEL_64;
    if ( v51 )
    {
      v37 = v51 - v9;
    }
    else
    {
      v37 = -1;
      do
        ++v37;
      while ( v9[v37] );
    }
    v60 = 512;
    lpMem = &v62;
    v59 = 2;
    v62 = 0;
    SString::Set((SString *)&v59, v9, v37);
    LODWORD(v50) = 0;
    SString::ConvertToUnicode((SString *)&v59);
    if ( (int)AssemblyVersion::Init((AssemblyVersion *)&v50, (const unsigned __int16 *)lpMem, v38) < 0 )
      break;
    v49 = 0;
    v39 = IsRunningOn47OrBelow();
    v41 = v28[5] & 0x7F;
    if ( v39 )
      v42 = (&FxPolicyHelper47::g_rgAssemblyKeyVersionStrings)[v41];
    else
      v42 = (&FxPolicyHelper::g_rgAssemblyKeyVersionStrings)[v41];
    AssemblyVersion::Init((AssemblyVersion *)&v49, (const unsigned __int16 *)v42, v40);
    if ( (HIWORD(v49) | ((unsigned __int64)(unsigned __int16)v49 << 16)) << 32 >= (WORD1(v50)
                                                                                 | ((unsigned __int64)(unsigned __int16)v50 << 16)) << 32 )
      goto LABEL_66;
    if ( (v60 & 0x800000000LL) != 0 )
    {
      v43 = lpMem;
      if ( lpMem )
      {
        ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          ProcessHeap = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
        }
        HeapFree(ProcessHeap, 0, v43);
      }
    }
LABEL_64:
    v25 = v52;
  }
  v26 = 0;
LABEL_66:
  if ( (v60 & 0x800000000LL) != 0 )
  {
    v45 = lpMem;
    if ( lpMem )
    {
      v46 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        v46 = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = v46;
      }
      HeapFree(v46, 0, v45);
    }
  }
LABEL_72:
  if ( (v56 & 0x800000000LL) != 0 )
  {
    v47 = v57;
    if ( v57 )
    {
      v48 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        v48 = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = v48;
      }
      HeapFree(v48, 0, v47);
    }
  }
  return v26;
}

```

## disassembly

```asm
0x1800252ac  mov     rax, rsp
0x1800252af  mov     [rax+10h], rbx
0x1800252b3  mov     [rax+18h], rsi
0x1800252b7  mov     [rax+20h], rdi
0x1800252bb  push    rbp
0x1800252bc  push    r12
0x1800252be  push    r13
0x1800252c0  push    r14
0x1800252c2  push    r15
0x1800252c4  lea     rbp, [rax-408h]
0x1800252cb  sub     rsp, 4E0h
0x1800252d2  mov     rax, cs:__security_cookie
0x1800252d9  xor     rax, rsp
0x1800252dc  mov     [rbp+400h+var_30], rax
0x1800252e3  mov     r13, rcx
0x1800252e6  mov     edx, 2Ch ; ','; Ch
0x1800252eb  call    cs:__imp_wcschr
0x1800252f1  mov     rdi, rax
0x1800252f4  xor     r15d, r15d
0x1800252f7  test    rax, rax
0x1800252fa  jz      loc_18002584A
0x180025300  mov     rsi, rax
0x180025303  sub     rsi, r13
0x180025306  sar     rsi, 1
0x180025309  cmp     rsi, 8
0x18002530d  jnz     short loc_18002532E
0x18002530f  mov     r8, rsi; MaxCount
0x180025312  lea     rdx, aMscorlib_0; "mscorlib"
0x180025319  mov     rcx, r13; String1
0x18002531c  call    cs:__imp__wcsnicmp
0x180025322  test    eax, eax
0x180025324  jnz     short loc_18002532E
0x180025326  lea     eax, [rsi-7]
0x180025329  jmp     loc_18002584C
0x18002532e  lea     rdx, aVersion; "Version="
0x180025335  mov     rcx, rdi; Str
0x180025338  call    cs:__imp_wcsstr
0x18002533e  mov     r12, rax
0x180025341  lea     rdx, aCulture; "Culture="
0x180025348  mov     rcx, rdi; Str
0x18002534b  call    cs:__imp_wcsstr
0x180025351  mov     rbx, rax
0x180025354  lea     rdx, aPublickeytoken; "PublicKeyToken="
0x18002535b  mov     rcx, rdi; Str
0x18002535e  call    cs:__imp_wcsstr
0x180025364  mov     r14, rax
0x180025367  test    r12, r12
0x18002536a  jz      loc_18002584A
0x180025370  test    rbx, rbx
0x180025373  jz      loc_18002584A
0x180025379  test    rax, rax
0x18002537c  jz      loc_18002584A
0x180025382  add     r12, 10h
0x180025386  add     rbx, 10h
0x18002538a  add     r14, 1Eh
0x18002538e  mov     edi, 2Ch ; ','
0x180025393  mov     edx, edi; Ch
0x180025395  mov     rcx, r12; Str
0x180025398  call    cs:__imp_wcschr
0x18002539e  mov     [rsp+500h+var_4D0], rax
0x1800253a3  mov     edx, edi; Ch
0x1800253a5  mov     rcx, rbx; Str
0x1800253a8  call    cs:__imp_wcschr
0x1800253ae  test    rax, rax
0x1800253b1  jnz     short loc_1800253C3
0x1800253b3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800253b7  inc     rax
0x1800253ba  cmp     [rbx+rax*2], r15w
0x1800253bf  jnz     short loc_1800253B7
0x1800253c1  jmp     short loc_1800253C9
0x1800253c3  sub     rax, rbx
0x1800253c6  sar     rax, 1
0x1800253c9  mov     r8d, 7; MaxCount
0x1800253cf  cmp     rax, r8
0x1800253d2  jnz     loc_18002584A
0x1800253d8  lea     rdx, aNeutral; "neutral"
0x1800253df  mov     rcx, rbx; String1
0x1800253e2  call    cs:__imp__wcsnicmp
0x1800253e8  test    eax, eax
0x1800253ea  jnz     loc_18002584A
0x1800253f0  mov     edx, edi; Ch
0x1800253f2  mov     rcx, r14; Str
0x1800253f5  call    cs:__imp_wcschr
0x1800253fb  mov     rbx, rax
0x1800253fe  test    rax, rax
0x180025401  jnz     short loc_180025413
0x180025403  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180025407  inc     rbx
0x18002540a  cmp     [r14+rbx*2], r15w
0x18002540f  jnz     short loc_180025407
0x180025411  jmp     short loc_180025419
0x180025413  sub     rbx, r14
0x180025416  sar     rbx, 1
0x180025419  mov     r8d, 4; MaxCount
0x18002541f  cmp     rbx, r8
0x180025422  jnz     short loc_18002543C
0x180025424  lea     rdx, aNull; "null"
0x18002542b  mov     rcx, r14; String1
0x18002542e  call    cs:__imp__wcsnicmp
0x180025434  test    eax, eax
0x180025436  jz      loc_18002584A
0x18002543c  mov     qword ptr [rsp+500h+var_4A0], r15
0x180025441  mov     qword ptr [rsp+64h], 20h ; ' '
0x18002544a  mov     [rsp+500h+var_490], r15
0x18002544f  lea     rax, [rsp+500h+var_488]
0x180025454  mov     [rsp+500h+var_490], rax
0x180025459  mov     edi, 20h ; ' '
0x18002545e  mov     [rsp+500h+var_4A0], 2
0x180025466  mov     rax, [rsp+500h+var_490]
0x18002546b  mov     [rax], r15w
0x18002546f  mov     r8d, esi; unsigned int
0x180025472  mov     rdx, r13; unsigned __int16 *
0x180025475  lea     rcx, [rsp+500h+var_4A0]; this
0x18002547a  call    ?Set@SString@@QEAAXPEBGI@Z; SString::Set(ushort const *,uint)
0x18002547f  nop
0x180025480  lea     rcx, [rsp+500h+var_4A0]; this
0x180025485  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18002548a  mov     r8, [rsp+500h+var_490]
0x18002548f  mov     r9d, r15d
0x180025492  jmp     short loc_1800254B3
0x180025494  lea     r8, [r8+2]
0x180025498  lea     eax, [rdx-41h]
0x18002549b  lea     ecx, [rdi+rdx]
0x18002549e  cmp     ax, 19h
0x1800254a2  cmova   cx, dx
0x1800254a6  movzx   ecx, cx
0x1800254a9  imul    r9d, 1003Fh
0x1800254b0  add     r9d, ecx
0x1800254b3  movzx   edx, word ptr [r8]
0x1800254b7  test    dx, dx
0x1800254ba  jnz     short loc_180025494
0x1800254bc  mov     eax, 891AC73Bh
0x1800254c1  mul     r9d
0x1800254c4  shr     edx, 7
0x1800254c7  imul    eax, edx, 0EFh
0x1800254cd  sub     r9d, eax
0x1800254d0  lea     rax, ?g_arFxPolicy47_HashCollision@@3QBGB; ushort const near * const g_arFxPolicy47_HashCollision
0x1800254d7  mov     [rsp+500h+var_4B8], rax
0x1800254dc  lea     ecx, [r9+r9]
0x1800254e0  lea     rdi, __ImageBase
0x1800254e7  lea     rax, rva ?g_arFxPolicy47_Hash@@3QBGB[rdi]; ushort const near * const g_arFxPolicy47_Hash ...
0x1800254ee  lea     rax, [rax+rcx*2]
0x1800254f2  mov     [rsp+500h+var_4C0], rax
0x1800254f7  lea     rcx, [rsp+500h+var_4A0]; this
0x1800254fc  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180025501  mov     r9, [rsp+500h+var_490]
0x180025506  mov     r10d, r15d
0x180025509  movzx   r8d, word ptr [r9]
0x18002550d  test    r8w, r8w
0x180025511  jz      short loc_180025545
0x180025513  mov     r11d, 20h ; ' '
0x180025519  lea     r9, [r9+2]
0x18002551d  lea     ecx, [r8-41h]
0x180025521  lea     edx, [r11+r8]
0x180025525  cmp     cx, 19h
0x180025529  cmova   dx, r8w
0x18002552e  movzx   edx, dx
0x180025531  imul    r10d, 1003Fh
0x180025538  add     r10d, edx
0x18002553b  movzx   r8d, word ptr [r9]
0x18002553f  test    r8w, r8w
0x180025543  jnz     short loc_180025519
0x180025545  mov     eax, 891AC73Bh
0x18002554a  mul     r10d
0x18002554d  shr     edx, 7
0x180025550  imul    eax, edx, 0EFh
0x180025556  sub     r10d, eax
0x180025559  lea     rax, ?g_arFxPolicy471_HashCollision@@3QBGB; ushort const near * const g_arFxPolicy471_HashCollision
0x180025560  mov     [rsp+500h+var_4A8], rax
0x180025565  lea     ecx, [r10+r10]
0x180025569  lea     rax, rva ?g_arFxPolicy471_Hash@@3QBGB[rdi]; ushort const near * const g_arFxPolicy471_Hash ...
0x180025570  lea     rax, [rax+rcx*2]
0x180025574  mov     [rsp+500h+var_4B0], rax
0x180025579  call    ?IsRunningOn47OrBelow@@YAHXZ; IsRunningOn47OrBelow(void)
0x18002557e  lea     r8, [rsp+500h+var_4C0]
0x180025583  lea     rcx, [rsp+500h+var_4B0]
0x180025588  test    eax, eax
0x18002558a  cmovz   r8, rcx
0x18002558e  mov     [rsp+500h+var_4C8], r8
0x180025593  mov     edi, 1
0x180025598  mov     rax, [r8]
0x18002559b  movzx   edx, word ptr [rax]
0x18002559e  movzx   ecx, word ptr [rax+2]
0x1800255a2  mov     rax, [r8+8]
0x1800255a6  lea     rcx, [rax+rcx*4]
0x1800255aa  mov     eax, edx
0x1800255ac  sub     eax, edi
0x1800255ae  mov     [r8], rcx
0x1800255b1  js      loc_18002580A
0x1800255b7  cdqe
0x1800255b9  lea     rcx, [rax+rax*2]
0x1800255bd  mov     rax, cs:?g_arFxPolicy@@3PEAUFrameworkConfig@@EA; FrameworkConfig * g_arFxPolicy
0x1800255c4  lea     r15, [rax+rcx*2]
0x1800255c8  call    ?IsRunningOn47OrBelow@@YAHXZ; IsRunningOn47OrBelow(void)
0x1800255cd  movzx   ecx, byte ptr [r15+4]
0x1800255d2  xor     r8d, r8d
0x1800255d5  test    eax, eax
0x1800255d7  lea     rax, __ImageBase
0x1800255de  jz      short loc_1800255EA
0x1800255e0  mov     rdx, ds:rva ?g_rgAssemblyKeyVersionStrings@FxPolicyHelper47@@3QBQEBGB[rax+rcx*8]; ushort const * const near * const FxPolicyHelper47::g_rgAssemblyKeyVersionStrings ...
0x1800255e8  jmp     short loc_1800255F2
0x1800255ea  mov     rdx, ds:rva ?g_rgAssemblyKeyVersionStrings@FxPolicyHelper@@3QBQEBGB[rax+rcx*8]; ushort const * const near * const FxPolicyHelper::g_rgAssemblyKeyVersionStrings ...
0x1800255f2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800255f6  inc     rax
0x1800255f9  cmp     [rdx+rax*2], r8w
0x1800255fe  jnz     short loc_1800255F6
0x180025600  cmp     rax, rbx
0x180025603  jnz     loc_1800257BF
0x180025609  call    ?IsRunningOn47OrBelow@@YAHXZ; IsRunningOn47OrBelow(void)
0x18002560e  movzx   ecx, byte ptr [r15+4]
0x180025613  test    eax, eax
0x180025615  lea     rax, __ImageBase
0x18002561c  jz      short loc_180025628
0x18002561e  mov     rcx, ds:rva ?g_rgAssemblyKeyVersionStrings@FxPolicyHelper47@@3QBQEBGB[rax+rcx*8]; ushort const * const near * const FxPolicyHelper47::g_rgAssemblyKeyVersionStrings ...
0x180025626  jmp     short loc_180025630
0x180025628  mov     rcx, ds:rva ?g_rgAssemblyKeyVersionStrings@FxPolicyHelper@@3QBQEBGB[rax+rcx*8]; String1
0x180025630  mov     r8, rbx; MaxCount
0x180025633  mov     rdx, r14; String2
0x180025636  call    cs:__imp__wcsnicmp
0x18002563c  xor     ecx, ecx
0x18002563e  test    eax, eax
0x180025640  jnz     loc_1800257BF
0x180025646  mov     [rbp+400h+String1], cx
0x18002564d  mov     [rbp+400h+var_40], rcx
0x180025654  lea     rdx, [rbp+400h+String1]
0x18002565b  mov     rcx, r15
0x18002565e  call    ??$GetFxAssemblyName@G@FrameworkConfig@@QEBAXAEAV?$FixedSizeString@G@@@Z; FrameworkConfig::GetFxAssemblyName<ushort>(FixedSizeString<ushort> &)
0x180025663  lea     rcx, [rbp+400h+String1]
0x18002566a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002566e  xor     edx, edx
0x180025670  inc     rax
0x180025673  cmp     [rcx+rax*2], dx
0x180025677  jnz     short loc_180025670
0x180025679  cmp     rax, rsi
0x18002567c  jnz     loc_1800257BF
0x180025682  mov     r8, rsi; MaxCount
0x180025685  mov     rdx, r13; String2
0x180025688  lea     rcx, [rbp+400h+String1]; String1
0x18002568f  call    cs:__imp__wcsnicmp
0x180025695  xor     edx, edx
0x180025697  test    eax, eax
0x180025699  jnz     loc_1800257BF
0x18002569f  mov     rax, [rsp+500h+var_4D0]
0x1800256a4  test    rax, rax
0x1800256a7  jnz     short loc_1800256B9
0x1800256a9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800256ad  inc     rcx
0x1800256b0  cmp     [r12+rcx*2], dx
0x1800256b5  jnz     short loc_1800256AD
0x1800256b7  jmp     short loc_1800256C2
0x1800256b9  mov     rcx, rax
0x1800256bc  sub     rcx, r12
0x1800256bf  sar     rcx, 1
0x1800256c2  mov     [rbp+400h+var_460], rdx
0x1800256c6  mov     [rbp+400h+var_460+4], 200h
0x1800256ce  mov     [rbp+400h+lpMem], rdx
0x1800256d2  lea     rax, [rbp+400h+var_448]
0x1800256d6  mov     [rbp+400h+lpMem], rax
0x1800256da  mov     dword ptr [rbp+400h+var_460], 2
0x1800256e1  mov     rax, [rbp+400h+lpMem]
0x1800256e5  mov     [rax], dx
0x1800256e8  mov     r8d, ecx; unsigned int
0x1800256eb  mov     rdx, r12; unsigned __int16 *
0x1800256ee  lea     rcx, [rbp+400h+var_460]; this
0x1800256f2  call    ?Set@SString@@QEAAXPEBGI@Z; SString::Set(ushort const *,uint)
0x1800256f7  nop
0x1800256f8  xor     eax, eax
0x1800256fa  mov     dword ptr [rsp+500h+var_4D8], eax
0x1800256fe  lea     rcx, [rbp+400h+var_460]; this
0x180025702  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180025707  mov     rdx, [rbp+400h+lpMem]; unsigned __int16 *
0x18002570b  lea     rcx, [rsp+500h+var_4D8]; this
0x180025710  call    ?Init@AssemblyVersion@@QEAAJPEBGH@Z; AssemblyVersion::Init(ushort const *,int)
0x180025715  xor     ecx, ecx
0x180025717  test    eax, eax
0x180025719  js      loc_1800257CC
0x18002571f  mov     [rsp+500h+var_4E0], ecx
0x180025723  call    ?IsRunningOn47OrBelow@@YAHXZ; IsRunningOn47OrBelow(void)
0x180025728  movzx   ecx, byte ptr [r15+5]
0x18002572d  and     ecx, 7Fh
0x180025730  xor     r15d, r15d
0x180025733  test    eax, eax
0x180025735  lea     rax, __ImageBase
0x18002573c  jz      short loc_180025748
0x18002573e  mov     rdx, ds:rva ?g_rgAssemblyKeyVersionStrings@FxPolicyHelper47@@3QBQEBGB[rax+rcx*8]; ushort const * const near * const FxPolicyHelper47::g_rgAssemblyKeyVersionStrings ...
0x180025746  jmp     short loc_180025750
0x180025748  mov     rdx, ds:rva ?g_rgAssemblyKeyVersionStrings@FxPolicyHelper@@3QBQEBGB[rax+rcx*8]; unsigned __int16 *
0x180025750  lea     rcx, [rsp+500h+var_4E0]; this
0x180025755  call    ?Init@AssemblyVersion@@QEAAJPEBGH@Z; AssemblyVersion::Init(ushort const *,int)
0x18002575a  movzx   edx, word ptr [rsp+500h+var_4E0]
0x18002575f  shl     rdx, 10h
0x180025763  movzx   eax, word ptr [rsp+500h+var_4E0+2]
0x180025768  or      rdx, rax
0x18002576b  shl     rdx, 20h
0x18002576f  movzx   ecx, word ptr [rsp+500h+var_4D8]
0x180025774  shl     rcx, 10h
0x180025778  movzx   eax, word ptr [rsp+500h+var_4D8+2]
0x18002577d  or      rcx, rax
0x180025780  shl     rcx, 20h
0x180025784  cmp     rdx, rcx
  ... truncated ...
```
