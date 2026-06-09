# SystemManagedAccountUtil::GenerateComplexPassword(ushort * *)

- ea: `0x18001d29c`
- end: `0x18001d931`
- name: `?GenerateComplexPassword@SystemManagedAccountUtil@@YAJPEAPEAG@Z`
- size: `1685`
- prototype: `__int64 __fastcall(SystemManagedAccountUtil *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180020a54`

## callees

- `0x180002490`
- `0x1800067c4`
- `0x18001a8c8`
- `0x18001d29c`
- `0x18001d938`
- `0x18001f5cc`
- `0x18001f96c`
- `0x180021370`
- `0x1800215f8`
- `0x180021cbc`
- `0x18002cf04`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d36b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d45f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d4bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d578`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d5ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d604`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d654`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d66e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d6bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d6d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d738`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d799`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d7f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d851`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d8a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d901`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d36b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d45f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d4bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d578`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d5ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d604`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d654`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d66e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d6bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d6d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d738`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d799`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d7f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d851`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d8a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d901`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemManagedAccountUtil::GenerateComplexPassword(
        SystemManagedAccountUtil *this,
        unsigned __int16 **a2)
{
  int RandomChars; // eax
  unsigned int v4; // ebx
  __int64 v6; // rbx
  char *v7; // rbx
  int v8; // eax
  const unsigned __int16 *v9; // rdx
  unsigned int v10; // esi
  _BYTE *v11; // rax
  char v12; // r15
  unsigned int i; // r14d
  int ComplexSuffix; // eax
  unsigned int v15; // r14d
  int v16; // eax
  void *v17; // r14
  __int64 v18; // r8
  int v19; // eax
  unsigned int v20; // r15d
  _BYTE *jj; // rcx
  int v22; // eax
  __int64 v23; // r8
  int v24; // eax
  unsigned int v25; // eax
  unsigned __int16 **v26; // rdx
  LPVOID v27; // rax
  _BYTE *j; // rax
  _BYTE *i1; // rax
  _BYTE *nn; // rax
  _BYTE *mm; // rax
  _BYTE *i2; // rcx
  _BYTE *kk; // rax
  _BYTE *ii; // rax
  _BYTE *n; // rax
  _BYTE *m; // rax
  _BYTE *k; // rax
  LPVOID pv; // [rsp+20h] [rbp-49h] BYREF
  __int64 v39; // [rsp+28h] [rbp-41h]
  __int64 v40; // [rsp+30h] [rbp-39h]
  LPVOID *p_pv; // [rsp+38h] [rbp-31h] BYREF
  char v42; // [rsp+40h] [rbp-29h]
  _WORD v43[4]; // [rsp+48h] [rbp-21h] BYREF
  LPVOID v44[5]; // [rsp+50h] [rbp-19h] BYREF
  _WORD v45[16]; // [rsp+78h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  *(_QWORD *)this = 0;
  RandomChars = GenerateRandomChars(v45, 15);
  v4 = RandomChars;
  if ( RandomChars < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x50,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\SystemManagedAccountUtil.h",
      (const char *)(unsigned int)RandomChars,
      (int)pv);
    return v4;
  }
  v6 = -1;
  do
    ++v6;
  while ( v45[v6] );
  v7 = (char *)(2 * v6);
  v44[3] = v45;
  v44[4] = v7;
  pv = 0;
  v39 = 0;
  v40 = 0;
  v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(&pv, v45, -1);
  v10 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x54,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\SystemManagedAccountUtil.h",
      (const char *)(unsigned int)v8,
      (int)pv);
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v39 = 0;
    v40 = 0;
    if ( v7 )
    {
      v11 = v45;
      do
      {
        *v11++ = 0;
        --v7;
      }
      while ( v7 );
    }
    return v10;
  }
  p_pv = &pv;
  v42 = 1;
  v12 = 0;
  for ( i = 0; ; i = v10 )
  {
    v25 = SystemManagedAccountUtil::ValidatePassword((SystemManagedAccountUtil *)pv, v9);
    v10 = v25;
    if ( (v25 & 0x80000000) == 0 )
    {
      v27 = pv;
      pv = 0;
      v40 = 0;
      v39 = 0;
      *(_QWORD *)this = v27;
      wil::details::ScopeExitFn__lambda_44528485316ca652931629561a7ea420___::_ScopeExitFn__lambda_44528485316ca652931629561a7ea420___(&p_pv);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      v39 = 0;
      v40 = 0;
      for ( j = v45; v7; --v7 )
        *j++ = 0;
      return 0;
    }
    if ( v25 == -2147022651 )
    {
      if ( i == -2147022193 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x65,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\SystemManagedAccountUtil.h",
          (const char *)v25,
          (int)pv);
        wil::details::ScopeExitFn__lambda_44528485316ca652931629561a7ea420___::_ScopeExitFn__lambda_44528485316ca652931629561a7ea420___(&p_pv);
        if ( pv )
        {
          CoTaskMemFree(pv);
          pv = 0;
        }
        v39 = 0;
        v40 = 0;
        for ( k = v45; v7; --v7 )
          *k++ = 0;
        return v10;
      }
      v22 = GenerateRandomChars(v43, 2);
      v15 = v22;
      if ( v22 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x69,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\SystemManagedAccountUtil.h",
          (const char *)(unsigned int)v22,
          (int)pv);
        wil::details::ScopeExitFn__lambda_44528485316ca652931629561a7ea420___::_ScopeExitFn__lambda_44528485316ca652931629561a7ea420___(&p_pv);
        if ( pv )
        {
          CoTaskMemFree(pv);
          pv = 0;
        }
        v39 = 0;
        v40 = 0;
        for ( m = v45; v7; --v7 )
          *m++ = 0;
        return v15;
      }
      v23 = -1;
      do
        ++v23;
      while ( v43[v23] );
      v24 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(&pv, v43);
      v15 = v24;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6A,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\SystemManagedAccountUtil.h",
          (const char *)(unsigned int)v24,
          (int)pv);
        wil::details::ScopeExitFn__lambda_44528485316ca652931629561a7ea420___::_ScopeExitFn__lambda_44528485316ca652931629561a7ea420___(&p_pv);
        if ( pv )
        {
          CoTaskMemFree(pv);
          pv = 0;
        }
        v39 = 0;
        v40 = 0;
        for ( n = v45; v7; --v7 )
          *n++ = 0;
        return v15;
      }
      continue;
    }
    if ( v25 == -2147022193 )
    {
      if ( i == -2147022651 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x72,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\SystemManagedAccountUtil.h",
          (const char *)v25,
          (int)pv);
        wil::details::ScopeExitFn__lambda_44528485316ca652931629561a7ea420___::_ScopeExitFn__lambda_44528485316ca652931629561a7ea420___(&p_pv);
        if ( pv )
        {
          CoTaskMemFree(pv);
          pv = 0;
        }
        v39 = 0;
        v40 = 0;
        for ( ii = v45; v7; --v7 )
          *ii++ = 0;
        return v10;
      }
      if ( !(unsigned __int8)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::RemoveAt(
                               &pv,
                               0) )
      {
        v10 = -2147418113;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x75,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\SystemManagedAccountUtil.h",
          (const char *)0x8000FFFFLL,
          (int)pv);
        wil::details::ScopeExitFn__lambda_44528485316ca652931629561a7ea420___::_ScopeExitFn__lambda_44528485316ca652931629561a7ea420___(&p_pv);
        if ( pv )
        {
          CoTaskMemFree(pv);
          pv = 0;
        }
        v39 = 0;
        v40 = 0;
        for ( jj = v45; v7; --v7 )
          *jj++ = 0;
        return v10;
      }
      continue;
    }
    if ( v25 != -2147022192 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x88,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\SystemManagedAccountUtil.h",
        (const char *)v25,
        (int)pv);
      wil::details::ScopeExitFn__lambda_44528485316ca652931629561a7ea420___::_ScopeExitFn__lambda_44528485316ca652931629561a7ea420___(&p_pv);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      v39 = 0;
      v40 = 0;
      for ( kk = v45; v7; --v7 )
        *kk++ = 0;
      return v10;
    }
    if ( v12 )
      break;
    v44[0] = 0;
    v44[1] = (LPVOID)-1LL;
    v44[2] = (LPVOID)-1LL;
    ComplexSuffix = SystemManagedAccountUtil::GenerateComplexSuffix((SystemManagedAccountUtil *)v44, v26);
    v15 = ComplexSuffix;
    if ( ComplexSuffix < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7F,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\SystemManagedAccountUtil.h",
        (const char *)(unsigned int)ComplexSuffix,
        (int)pv);
      if ( v44[0] )
        CoTaskMemFree(v44[0]);
      wil::details::ScopeExitFn__lambda_44528485316ca652931629561a7ea420___::_ScopeExitFn__lambda_44528485316ca652931629561a7ea420___(&p_pv);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      v39 = 0;
      v40 = 0;
      for ( mm = v45; v7; --v7 )
        *mm++ = 0;
      return v15;
    }
    v16 = SystemManagedAccountUtil::ScrambleString(v44);
    v15 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x80,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\SystemManagedAccountUtil.h",
        (const char *)(unsigned int)v16,
        (int)pv);
      if ( v44[0] )
        CoTaskMemFree(v44[0]);
      wil::details::ScopeExitFn__lambda_44528485316ca652931629561a7ea420___::_ScopeExitFn__lambda_44528485316ca652931629561a7ea420___(&p_pv);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      v39 = 0;
      v40 = 0;
      for ( nn = v45; v7; --v7 )
        *nn++ = 0;
      return v15;
    }
    v17 = v44[0];
    if ( *(_OWORD *)v44 > __PAIR128__(-1, 0) )
    {
      v18 = -1;
      do
        ++v18;
      while ( *((_WORD *)v44[0] + v18) );
    }
    v19 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(&pv, v44[0]);
    v20 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x81,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\SystemManagedAccountUtil.h",
        (const char *)(unsigned int)v19,
        (int)pv);
      if ( v17 )
        CoTaskMemFree(v17);
      wil::details::ScopeExitFn__lambda_44528485316ca652931629561a7ea420___::_ScopeExitFn__lambda_44528485316ca652931629561a7ea420___(&p_pv);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      v39 = 0;
      v40 = 0;
      for ( i1 = v45; v7; --v7 )
        *i1++ = 0;
      return v20;
    }
    v12 = 1;
    if ( v17 )
      CoTaskMemFree(v17);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x7C,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\SystemManagedAccountUtil.h",
    (const char *)0x80070A90LL,
    (int)pv);
  wil::details::ScopeExitFn__lambda_44528485316ca652931629561a7ea420___::_ScopeExitFn__lambda_44528485316ca652931629561a7ea420___(&p_pv);
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  v39 = 0;
  v40 = 0;
  for ( i2 = v45; v7; --v7 )
    *i2++ = 0;
  return 2147945104LL;
}

```

## disassembly

```asm
0x18001d29c  mov     [rsp-8+arg_8], rbx
0x18001d2a1  mov     [rsp-8+arg_10], rsi
0x18001d2a6  push    rbp
0x18001d2a7  push    r12
0x18001d2a9  push    r13
0x18001d2ab  push    r14
0x18001d2ad  push    r15
0x18001d2af  lea     rbp, [rsp-37h]
0x18001d2b4  sub     rsp, 0A0h
0x18001d2bb  mov     rax, cs:__security_cookie
0x18001d2c2  xor     rax, rsp
0x18001d2c5  mov     [rbp+57h+var_28], rax
0x18001d2c9  mov     r12, rcx
0x18001d2cc  xor     r13d, r13d
0x18001d2cf  mov     [rcx], r13
0x18001d2d2  lea     edx, [r13+0Fh]
0x18001d2d6  lea     rcx, [rbp+57h+var_48]
0x18001d2da  call    GenerateRandomChars
0x18001d2df  mov     ebx, eax
0x18001d2e1  test    eax, eax
0x18001d2e3  jns     short loc_18001D303
0x18001d2e5  mov     rcx, [rbp+5Fh]; this
0x18001d2e9  mov     r9d, eax; char *
0x18001d2ec  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Syste"...
0x18001d2f3  lea     edx, [r13+50h]; void *
0x18001d2f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d2fc  mov     eax, ebx
0x18001d2fe  jmp     loc_18001D5A1
0x18001d303  lea     rax, [rbp+57h+var_48]
0x18001d307  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001d30b  mov     rbx, rcx
0x18001d30e  inc     rbx
0x18001d311  cmp     [rax+rbx*2], r13w
0x18001d316  jnz     short loc_18001D30E
0x18001d318  add     rbx, rbx
0x18001d31b  lea     rax, [rbp+57h+var_48]
0x18001d31f  mov     [rbp+57h+var_58], rax
0x18001d323  mov     [rbp+57h+var_50], rbx
0x18001d327  mov     [rbp+57h+pv], r13
0x18001d32b  mov     [rbp+57h+var_98], r13
0x18001d32f  mov     [rbp+57h+var_90], r13
0x18001d333  mov     r8, rcx
0x18001d336  lea     rdx, [rbp+57h+var_48]
0x18001d33a  lea     rcx, [rbp+57h+pv]
0x18001d33e  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18001d343  mov     esi, eax
0x18001d345  test    eax, eax
0x18001d347  jns     short loc_18001D399
0x18001d349  mov     rcx, [rbp+5Fh]; this
0x18001d34d  mov     r9d, eax; char *
0x18001d350  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Syste"...
0x18001d357  mov     edx, 54h ; 'T'; void *
0x18001d35c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d361  nop
0x18001d362  mov     rcx, [rbp+57h+pv]; pv
0x18001d366  test    rcx, rcx
0x18001d369  jz      short loc_18001D375
0x18001d36b  call    cs:__imp_CoTaskMemFree
0x18001d371  mov     [rbp+57h+pv], r13
0x18001d375  mov     [rbp+57h+var_98], r13
0x18001d379  mov     [rbp+57h+var_90], r13
0x18001d37d  test    rbx, rbx
0x18001d380  jz      short loc_18001D392
0x18001d382  lea     rax, [rbp+57h+var_48]
0x18001d386  mov     [rax], r13b
0x18001d389  inc     rax
0x18001d38c  sub     rbx, 1
0x18001d390  jnz     short loc_18001D386
0x18001d392  mov     eax, esi
0x18001d394  jmp     loc_18001D5A1
0x18001d399  lea     rax, [rbp+57h+pv]
0x18001d39d  mov     [rbp+57h+var_88], rax
0x18001d3a1  mov     [rbp+57h+var_80], 1
0x18001d3a5  mov     r15b, r13b
0x18001d3a8  mov     r14d, r13d
0x18001d3ab  jmp     loc_18001D53E
0x18001d3b0  cmp     esi, 800708C5h
0x18001d3b6  jz      loc_18001D4EB
0x18001d3bc  cmp     esi, 80070A8Fh
0x18001d3c2  jz      loc_18001D46A
0x18001d3c8  cmp     esi, 80070A90h
0x18001d3ce  jnz     loc_18001D769
0x18001d3d4  test    r15b, r15b
0x18001d3d7  jnz     loc_18001D709
0x18001d3dd  mov     [rbp+57h+var_70], r13
0x18001d3e1  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001d3e5  mov     [rbp+57h+var_68], r15
0x18001d3e9  mov     [rbp+57h+var_60], r15
0x18001d3ed  lea     rcx, [rbp+57h+var_70]; this
0x18001d3f1  call    ?GenerateComplexSuffix@SystemManagedAccountUtil@@YAJPEAPEAG@Z; SystemManagedAccountUtil::GenerateComplexSuffix(ushort * *)
0x18001d3f6  mov     r14d, eax
0x18001d3f9  test    eax, eax
0x18001d3fb  js      loc_18001D69E
0x18001d401  lea     rcx, [rbp+57h+var_70]
0x18001d405  call    ?ScrambleString@SystemManagedAccountUtil@@YAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; SystemManagedAccountUtil::ScrambleString(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x18001d40a  mov     r14d, eax
0x18001d40d  test    eax, eax
0x18001d40f  js      loc_18001D633
0x18001d415  mov     r8, [rbp+57h+var_68]
0x18001d419  mov     r14, [rbp+57h+var_70]
0x18001d41d  cmp     r8, r15
0x18001d420  jnz     short loc_18001D439
0x18001d422  test    r14, r14
0x18001d425  jz      short loc_18001D436
0x18001d427  mov     r8, r15
0x18001d42a  inc     r8
0x18001d42d  cmp     [r14+r8*2], r13w
0x18001d432  jnz     short loc_18001D42A
0x18001d434  jmp     short loc_18001D439
0x18001d436  mov     r8, r13
0x18001d439  mov     rdx, r14
0x18001d43c  lea     rcx, [rbp+57h+pv]
0x18001d440  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x18001d445  mov     r15d, eax
0x18001d448  test    eax, eax
0x18001d44a  js      loc_18001D5CA
0x18001d450  mov     r15b, 1
0x18001d453  test    r14, r14
0x18001d456  jz      loc_18001D53B
0x18001d45c  mov     rcx, r14; pv
0x18001d45f  call    cs:__imp_CoTaskMemFree
0x18001d465  jmp     loc_18001D53B
0x18001d46a  cmp     r14d, 800708C5h
0x18001d471  jz      loc_18001D7C9
0x18001d477  xor     edx, edx
0x18001d479  lea     rcx, [rbp+57h+pv]
0x18001d47d  call    ?RemoveAt@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA_N_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::RemoveAt(unsigned __int64)
0x18001d482  test    al, al
0x18001d484  jnz     loc_18001D53B
0x18001d48a  mov     rcx, [rbp+5Fh]; this
0x18001d48e  mov     esi, 8000FFFFh
0x18001d493  mov     r9d, esi; char *
0x18001d496  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Syste"...
0x18001d49d  mov     edx, 75h ; 'u'; void *
0x18001d4a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d4a7  nop
0x18001d4a8  lea     rcx, [rbp+57h+var_88]
0x18001d4ac  call    wil__details__ScopeExitFn__lambda_44528485316ca652931629561a7ea420______ScopeExitFn__lambda_44528485316ca652931629561a7ea420___
0x18001d4b1  nop
0x18001d4b2  mov     rcx, [rbp+57h+pv]; pv
0x18001d4b6  test    rcx, rcx
0x18001d4b9  jz      short loc_18001D4C5
0x18001d4bb  call    cs:__imp_CoTaskMemFree
0x18001d4c1  mov     [rbp+57h+pv], r13
0x18001d4c5  mov     [rbp+57h+var_98], r13
0x18001d4c9  mov     [rbp+57h+var_90], r13
0x18001d4cd  lea     rcx, [rbp+57h+var_48]
0x18001d4d1  test    rbx, rbx
0x18001d4d4  jz      loc_18001D392
0x18001d4da  mov     [rcx], r13b
0x18001d4dd  inc     rcx
0x18001d4e0  sub     rbx, 1
0x18001d4e4  jnz     short loc_18001D4DA
0x18001d4e6  jmp     loc_18001D392
0x18001d4eb  cmp     r14d, 80070A8Fh
0x18001d4f2  jz      loc_18001D8D5
0x18001d4f8  mov     edx, 2
0x18001d4fd  lea     rcx, [rbp+57h+var_78]
0x18001d501  call    GenerateRandomChars
0x18001d506  mov     r14d, eax
0x18001d509  test    eax, eax
0x18001d50b  js      loc_18001D87A
0x18001d511  lea     rax, [rbp+57h+var_78]
0x18001d515  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001d519  inc     r8
0x18001d51c  cmp     [rax+r8*2], r13w
0x18001d521  jnz     short loc_18001D519
0x18001d523  lea     rdx, [rbp+57h+var_78]
0x18001d527  lea     rcx, [rbp+57h+pv]
0x18001d52b  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x18001d530  mov     r14d, eax
0x18001d533  test    eax, eax
0x18001d535  js      loc_18001D825
0x18001d53b  mov     r14d, esi
0x18001d53e  mov     rcx, [rbp+57h+pv]; this
0x18001d542  call    ?ValidatePassword@SystemManagedAccountUtil@@YAJPEBG@Z; SystemManagedAccountUtil::ValidatePassword(ushort const *)
0x18001d547  test    eax, eax
0x18001d549  mov     esi, eax
0x18001d54b  js      loc_18001D3B0
0x18001d551  mov     rax, [rbp+57h+pv]
0x18001d555  mov     [rbp+57h+pv], r13
0x18001d559  mov     [rbp+57h+var_90], r13
0x18001d55d  mov     [rbp+57h+var_98], r13
0x18001d561  mov     [r12], rax
0x18001d565  lea     rcx, [rbp+57h+var_88]
0x18001d569  call    wil__details__ScopeExitFn__lambda_44528485316ca652931629561a7ea420______ScopeExitFn__lambda_44528485316ca652931629561a7ea420___
0x18001d56e  nop
0x18001d56f  mov     rcx, [rbp+57h+pv]; pv
0x18001d573  test    rcx, rcx
0x18001d576  jz      short loc_18001D582
0x18001d578  call    cs:__imp_CoTaskMemFree
0x18001d57e  mov     [rbp+57h+pv], r13
0x18001d582  mov     [rbp+57h+var_98], r13
0x18001d586  mov     [rbp+57h+var_90], r13
0x18001d58a  lea     rax, [rbp+57h+var_48]
0x18001d58e  test    rbx, rbx
0x18001d591  jz      short loc_18001D59F
0x18001d593  mov     [rax], r13b
0x18001d596  inc     rax
0x18001d599  sub     rbx, 1
0x18001d59d  jnz     short loc_18001D593
0x18001d59f  xor     eax, eax
0x18001d5a1  mov     rcx, [rbp+57h+var_28]
0x18001d5a5  xor     rcx, rsp; StackCookie
0x18001d5a8  call    __security_check_cookie
0x18001d5ad  lea     r11, [rsp+0C0h+var_20]
0x18001d5b5  mov     rbx, [r11+38h]
0x18001d5b9  mov     rsi, [r11+40h]
0x18001d5bd  mov     rsp, r11
0x18001d5c0  pop     r15
0x18001d5c2  pop     r14
0x18001d5c4  pop     r13
0x18001d5c6  pop     r12
0x18001d5c8  pop     rbp
0x18001d5c9  retn
0x18001d5ca  mov     rcx, [rbp+5Fh]; this
0x18001d5ce  mov     r9d, r15d; char *
0x18001d5d1  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Syste"...
0x18001d5d8  mov     edx, 81h; void *
0x18001d5dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d5e2  test    r14, r14
0x18001d5e5  jz      short loc_18001D5F1
0x18001d5e7  mov     rcx, r14; pv
0x18001d5ea  call    cs:__imp_CoTaskMemFree
0x18001d5f0  nop
0x18001d5f1  lea     rcx, [rbp+57h+var_88]
0x18001d5f5  call    wil__details__ScopeExitFn__lambda_44528485316ca652931629561a7ea420______ScopeExitFn__lambda_44528485316ca652931629561a7ea420___
0x18001d5fa  nop
0x18001d5fb  mov     rcx, [rbp+57h+pv]; pv
0x18001d5ff  test    rcx, rcx
0x18001d602  jz      short loc_18001D60E
0x18001d604  call    cs:__imp_CoTaskMemFree
0x18001d60a  mov     [rbp+57h+pv], r13
0x18001d60e  mov     [rbp+57h+var_98], r13
0x18001d612  mov     [rbp+57h+var_90], r13
0x18001d616  lea     rax, [rbp+57h+var_48]
0x18001d61a  test    rbx, rbx
0x18001d61d  jz      short loc_18001D62B
0x18001d61f  mov     [rax], r13b
0x18001d622  inc     rax
0x18001d625  sub     rbx, 1
0x18001d629  jnz     short loc_18001D61F
0x18001d62b  mov     eax, r15d
0x18001d62e  jmp     loc_18001D5A1
0x18001d633  mov     rcx, [rbp+5Fh]; this
0x18001d637  mov     r9d, r14d; char *
0x18001d63a  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Syste"...
0x18001d641  mov     edx, 80h; void *
0x18001d646  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d64b  mov     rcx, [rbp+57h+var_70]; pv
0x18001d64f  test    rcx, rcx
0x18001d652  jz      short loc_18001D65B
0x18001d654  call    cs:__imp_CoTaskMemFree
0x18001d65a  nop
0x18001d65b  lea     rcx, [rbp+57h+var_88]
0x18001d65f  call    wil__details__ScopeExitFn__lambda_44528485316ca652931629561a7ea420______ScopeExitFn__lambda_44528485316ca652931629561a7ea420___
0x18001d664  nop
0x18001d665  mov     rcx, [rbp+57h+pv]; pv
0x18001d669  test    rcx, rcx
0x18001d66c  jz      short loc_18001D678
0x18001d66e  call    cs:__imp_CoTaskMemFree
0x18001d674  mov     [rbp+57h+pv], r13
0x18001d678  mov     [rbp+57h+var_98], r13
0x18001d67c  mov     [rbp+57h+var_90], r13
0x18001d680  lea     rax, [rbp+57h+var_48]
0x18001d684  test    rbx, rbx
0x18001d687  jz      loc_18001D8CD
0x18001d68d  mov     [rax], r13b
0x18001d690  inc     rax
0x18001d693  sub     rbx, 1
0x18001d697  jnz     short loc_18001D68D
0x18001d699  jmp     loc_18001D8CD
0x18001d69e  mov     rcx, [rbp+5Fh]; this
0x18001d6a2  mov     r9d, r14d; char *
0x18001d6a5  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Syste"...
0x18001d6ac  mov     edx, 7Fh; void *
0x18001d6b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d6b6  mov     rcx, [rbp+57h+var_70]; pv
0x18001d6ba  test    rcx, rcx
0x18001d6bd  jz      short loc_18001D6C6
0x18001d6bf  call    cs:__imp_CoTaskMemFree
0x18001d6c5  nop
0x18001d6c6  lea     rcx, [rbp+57h+var_88]
0x18001d6ca  call    wil__details__ScopeExitFn__lambda_44528485316ca652931629561a7ea420______ScopeExitFn__lambda_44528485316ca652931629561a7ea420___
0x18001d6cf  nop
0x18001d6d0  mov     rcx, [rbp+57h+pv]; pv
0x18001d6d4  test    rcx, rcx
0x18001d6d7  jz      short loc_18001D6E3
0x18001d6d9  call    cs:__imp_CoTaskMemFree
0x18001d6df  mov     [rbp+57h+pv], r13
0x18001d6e3  mov     [rbp+57h+var_98], r13
0x18001d6e7  mov     [rbp+57h+var_90], r13
0x18001d6eb  lea     rax, [rbp+57h+var_48]
0x18001d6ef  test    rbx, rbx
0x18001d6f2  jz      loc_18001D8CD
0x18001d6f8  mov     [rax], r13b
0x18001d6fb  inc     rax
0x18001d6fe  sub     rbx, 1
0x18001d702  jnz     short loc_18001D6F8
0x18001d704  jmp     loc_18001D8CD
  ... truncated ...
```
