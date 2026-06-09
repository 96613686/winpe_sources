# GetPopRegLocationForKeyMapping(_NGC_IDP_ACCOUNT_INFO *,ushort const *,ushort const *,ushort const *,ushort * *)

- ea: `0x1800177f4`
- end: `0x180017b43`
- name: `?GetPopRegLocationForKeyMapping@@YAJPEAU_NGC_IDP_ACCOUNT_INFO@@PEBG11PEAPEAG@Z`
- size: `847`
- prototype: `__int64 __fastcall(NgcUtils **, NgcUtils *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015644`
- `0x180015bf0`
- `0x180018eec`
- `0x180019424`

## callees

- `0x18000b0fc`
- `0x18000b898`
- `0x18000db5c`
- `0x180010730`
- `0x180014478`
- `0x180014e40`
- `0x1800177f4`
- `0x180017b4c`

## string_xrefs

- `0x180017863`: `onecore\ds\security\ngc\ngcpopkey\common\reg.cpp`
- `0x1800178cf`: `onecore\ds\security\ngc\ngcpopkey\common\reg.cpp`
- `0x18001793f`: `onecore\ds\security\ngc\ngcpopkey\common\reg.cpp`
- `0x1800179c7`: `onecore\ds\security\ngc\ngcpopkey\common\reg.cpp`
- `0x180017a4d`: `onecore\ds\security\ngc\ngcpopkey\common\reg.cpp`
- `0x180017ab7`: `onecore\ds\security\ngc\ngcpopkey\common\reg.cpp`

## pseudocode

```c
__int64 __fastcall GetPopRegLocationForKeyMapping(
        NgcUtils **a1,
        NgcUtils *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 **a5)
{
  const unsigned __int16 *v7; // rdi
  __int64 v8; // r14
  __int64 v9; // r13
  unsigned __int16 **v10; // r8
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v14; // rbx
  unsigned __int16 **v15; // r8
  int v16; // eax
  unsigned int v17; // esi
  __int64 v18; // rsi
  __int64 v19; // r15
  int TenantAndUserAccountSubKey; // eax
  unsigned int v21; // r12d
  __int64 v22; // r15
  unsigned __int16 *v23; // rbx
  unsigned __int64 v24; // r15
  unsigned __int16 *v25; // r14
  const unsigned __int16 *v26; // rax
  int v27; // eax
  int v28; // eax
  int v29; // [rsp+20h] [rbp-40h]
  int v30; // [rsp+20h] [rbp-40h]
  int v31; // [rsp+20h] [rbp-40h]
  unsigned __int16 v32[4]; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int16 v33[4]; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int16 *v34; // [rsp+50h] [rbp-10h] BYREF
  unsigned __int16 *v35; // [rsp+58h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  v7 = 0;
  *(_QWORD *)v32 = 0;
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( a3[v9] );
  if ( a2 )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      v32,
      0);
    v11 = NgcUtils::HashStringIntoHexString(a2, v32, v10);
    v12 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBC,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\reg.cpp",
        (const char *)(unsigned int)v11,
        v29);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v32);
      return v12;
    }
    v7 = *(const unsigned __int16 **)v32;
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)(*(_QWORD *)v32 + 2 * v14) );
  }
  else
  {
    v14 = -1;
    do
      ++v14;
    while ( a4[v14] );
  }
  *(_QWORD *)v33 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    v33,
    0);
  v16 = NgcUtils::HashStringIntoHexString(*a1, v33, v15);
  v17 = v16;
  if ( v16 >= 0 )
  {
    v18 = *(_QWORD *)v33;
    v19 = -1;
    do
      ++v19;
    while ( *(_WORD *)(*(_QWORD *)v33 + 2 * v19) );
    v34 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v34,
      0);
    TenantAndUserAccountSubKey = GetTenantAndUserAccountSubKey(a1[1], a1[2], &v34);
    v21 = TenantAndUserAccountSubKey;
    if ( TenantAndUserAccountSubKey >= 0 )
    {
      v22 = v14 + v9 + (unsigned int)v19;
      v23 = v34;
      if ( v34 )
      {
        do
          ++v8;
        while ( v34[v8] );
        v24 = v8 + v22 + 4;
      }
      else
      {
        v24 = v22 + 3;
      }
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &v35,
        0,
        v24);
      v25 = v35;
      if ( !v35 )
      {
        v12 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDE,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\reg.cpp",
          (const char *)0x8007000ELL,
          v29);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v34);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v33);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v32);
        return v12;
      }
      v26 = a4;
      if ( v23 )
      {
        if ( a2 )
          v26 = v7;
        v27 = StringCchPrintfW(v35, v24, L"%s\\%s\\%s\\%s", a3, v26, v18, v23);
        v12 = v27;
        if ( v27 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xE9,
            (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\reg.cpp",
            (const char *)(unsigned int)v27,
            v30);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v34);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v33);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v32);
          return v12;
        }
      }
      else
      {
        if ( a2 )
          v26 = v7;
        v28 = StringCchPrintfW(v35, v24, L"%s\\%s\\%s", a3, v26, v18);
        v12 = v28;
        if ( v28 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xF3,
            (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\reg.cpp",
            (const char *)(unsigned int)v28,
            v31);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v34);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v33);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v32);
          return v12;
        }
      }
      v35 = 0;
      *a5 = v25;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v34);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v33);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v32);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD1,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\reg.cpp",
        (const char *)(unsigned int)TenantAndUserAccountSubKey,
        v29);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v34);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v33);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v32);
      return v21;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC9,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\reg.cpp",
      (const char *)(unsigned int)v16,
      v29);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v33);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v32);
    return v17;
  }
}

```

## disassembly

```asm
0x1800177f4  mov     rax, rsp
0x1800177f7  mov     [rax+8], rbx
0x1800177fb  mov     [rax+20h], r9
0x1800177ff  mov     [rax+18h], r8
0x180017803  mov     [rax+10h], rdx
0x180017807  push    rbp
0x180017808  push    rsi
0x180017809  push    rdi
0x18001780a  push    r12
0x18001780c  push    r13
0x18001780e  push    r14
0x180017810  push    r15
0x180017812  mov     rbp, rsp
0x180017815  sub     rsp, 60h
0x180017819  mov     rbx, rdx
0x18001781c  mov     r12, rcx
0x18001781f  xor     r15d, r15d
0x180017822  mov     edi, r15d
0x180017825  mov     qword ptr [rbp+var_20], r15
0x180017829  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001782d  mov     r13, r14
0x180017830  inc     r13
0x180017833  cmp     [r8+r13*2], r15w
0x180017838  jnz     short loc_180017830
0x18001783a  test    rbx, rbx
0x18001783d  jz      short loc_180017899
0x18001783f  xor     edx, edx
0x180017841  lea     rcx, [rbp+var_20]
0x180017845  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001784a  lea     rdx, [rbp+var_20]; unsigned __int16 *
0x18001784e  mov     rcx, rbx; this
0x180017851  call    ?HashStringIntoHexString@NgcUtils@@YAJPEBGPEAPEAG@Z; NgcUtils::HashStringIntoHexString(ushort const *,ushort * *)
0x180017856  mov     ebx, eax
0x180017858  test    eax, eax
0x18001785a  jns     short loc_180017886
0x18001785c  mov     rcx, [rbp+38h]; this
0x180017860  mov     r9d, eax; char *
0x180017863  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001786a  mov     edx, 0BCh; void *
0x18001786f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017874  nop
0x180017875  lea     rcx, [rbp+var_20]
0x180017879  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001787e  nop
0x18001787f  mov     eax, ebx
0x180017881  jmp     loc_180017B2B
0x180017886  mov     rdi, qword ptr [rbp+var_20]
0x18001788a  mov     rbx, r14
0x18001788d  inc     rbx
0x180017890  cmp     [rdi+rbx*2], r15w
0x180017895  jnz     short loc_18001788D
0x180017897  jmp     short loc_1800178A6
0x180017899  mov     rbx, r14
0x18001789c  inc     rbx
0x18001789f  cmp     [r9+rbx*2], r15w
0x1800178a4  jnz     short loc_18001789C
0x1800178a6  mov     qword ptr [rbp+var_18], r15
0x1800178aa  xor     edx, edx
0x1800178ac  lea     rcx, [rbp+var_18]
0x1800178b0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800178b5  lea     rdx, [rbp+var_18]; unsigned __int16 *
0x1800178b9  mov     rcx, [r12]; this
0x1800178bd  call    ?HashStringIntoHexString@NgcUtils@@YAJPEBGPEAPEAG@Z; NgcUtils::HashStringIntoHexString(ushort const *,ushort * *)
0x1800178c2  mov     esi, eax
0x1800178c4  test    eax, eax
0x1800178c6  jns     short loc_1800178FC
0x1800178c8  mov     rcx, [rbp+38h]; this
0x1800178cc  mov     r9d, eax; char *
0x1800178cf  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x1800178d6  mov     edx, 0C9h; void *
0x1800178db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800178e0  nop
0x1800178e1  lea     rcx, [rbp+var_18]
0x1800178e5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800178ea  nop
0x1800178eb  lea     rcx, [rbp+var_20]
0x1800178ef  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800178f4  nop
0x1800178f5  mov     eax, esi
0x1800178f7  jmp     loc_180017B2B
0x1800178fc  mov     rsi, qword ptr [rbp+var_18]
0x180017900  mov     r15, r14
0x180017903  xor     eax, eax
0x180017905  inc     r15
0x180017908  cmp     [rsi+r15*2], ax
0x18001790d  jnz     short loc_180017905
0x18001790f  mov     [rbp+var_10], rax
0x180017913  xor     edx, edx
0x180017915  lea     rcx, [rbp+var_10]
0x180017919  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001791e  lea     r8, [rbp+var_10]; unsigned __int16 **
0x180017922  mov     rdx, [r12+10h]; NgcUtils *
0x180017927  mov     rcx, [r12+8]; this
0x18001792c  call    ?GetTenantAndUserAccountSubKey@@YAJPEBG0PEAPEAG@Z; GetTenantAndUserAccountSubKey(ushort const *,ushort const *,ushort * *)
0x180017931  mov     r12d, eax
0x180017934  test    eax, eax
0x180017936  jns     short loc_180017977
0x180017938  mov     rcx, [rbp+38h]; this
0x18001793c  mov     r9d, eax; char *
0x18001793f  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180017946  mov     edx, 0D1h; void *
0x18001794b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017950  nop
0x180017951  lea     rcx, [rbp+var_10]
0x180017955  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001795a  nop
0x18001795b  lea     rcx, [rbp+var_18]
0x18001795f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017964  nop
0x180017965  lea     rcx, [rbp+var_20]
0x180017969  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001796e  nop
0x18001796f  mov     eax, r12d
0x180017972  jmp     loc_180017B2B
0x180017977  mov     r15d, r15d
0x18001797a  add     r15, r13
0x18001797d  add     r15, rbx
0x180017980  mov     rbx, [rbp+var_10]
0x180017984  xor     r12d, r12d
0x180017987  test    rbx, rbx
0x18001798a  jz      short loc_18001799F
0x18001798c  inc     r14
0x18001798f  cmp     [rbx+r14*2], r12w
0x180017994  jnz     short loc_18001798C
0x180017996  add     r15, 4
0x18001799a  add     r15, r14
0x18001799d  jmp     short loc_1800179A3
0x18001799f  add     r15, 3
0x1800179a3  mov     r8, r15
0x1800179a6  xor     edx, edx
0x1800179a8  lea     rcx, [rbp+var_8]
0x1800179ac  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800179b1  nop
0x1800179b2  mov     r14, [rbp+var_8]
0x1800179b6  test    r14, r14
0x1800179b9  jnz     short loc_180017A06
0x1800179bb  mov     rcx, [rbp+38h]; this
0x1800179bf  mov     ebx, 8007000Eh
0x1800179c4  mov     r9d, ebx; char *
0x1800179c7  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x1800179ce  mov     edx, 0DEh; void *
0x1800179d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800179d8  nop
0x1800179d9  lea     rcx, [rbp+var_8]
0x1800179dd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800179e2  nop
0x1800179e3  lea     rcx, [rbp+var_10]
0x1800179e7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800179ec  nop
0x1800179ed  lea     rcx, [rbp+var_18]
0x1800179f1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800179f6  nop
0x1800179f7  lea     rcx, [rbp+var_20]
0x1800179fb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017a00  nop
0x180017a01  jmp     loc_18001787F
0x180017a06  mov     rax, [rbp+arg_18]
0x180017a0a  mov     r9, [rbp+arg_10]
0x180017a0e  mov     rdx, r15; unsigned __int64
0x180017a11  mov     rcx, r14; unsigned __int16 *
0x180017a14  test    rbx, rbx
0x180017a17  jz      short loc_180017A8C
0x180017a19  cmp     [rbp+arg_8], r12
0x180017a1d  cmovnz  rax, rdi
0x180017a21  mov     [rsp+60h+var_30], rbx
0x180017a26  mov     [rsp+60h+var_38], rsi
0x180017a2b  mov     qword ptr [rsp+60h+var_40], rax; int
0x180017a30  lea     r8, aSSSS; "%s\\%s\\%s\\%s"
0x180017a37  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017a3c  mov     ebx, eax
0x180017a3e  test    eax, eax
0x180017a40  jns     loc_180017AF6
0x180017a46  mov     rcx, [rbp+38h]; this
0x180017a4a  mov     r9d, eax; char *
0x180017a4d  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180017a54  mov     edx, 0E9h; void *
0x180017a59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017a5e  nop
0x180017a5f  lea     rcx, [rbp+var_8]
0x180017a63  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017a68  nop
0x180017a69  lea     rcx, [rbp+var_10]
0x180017a6d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017a72  nop
0x180017a73  lea     rcx, [rbp+var_18]
0x180017a77  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017a7c  nop
0x180017a7d  lea     rcx, [rbp+var_20]
0x180017a81  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017a86  nop
0x180017a87  jmp     loc_18001787F
0x180017a8c  cmp     [rbp+arg_8], r12
0x180017a90  cmovnz  rax, rdi
0x180017a94  mov     [rsp+60h+var_38], rsi
0x180017a99  mov     qword ptr [rsp+60h+var_40], rax; int
0x180017a9e  lea     r8, aSSS; "%s\\%s\\%s"
0x180017aa5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017aaa  mov     ebx, eax
0x180017aac  test    eax, eax
0x180017aae  jns     short loc_180017AF6
0x180017ab0  mov     rcx, [rbp+38h]; this
0x180017ab4  mov     r9d, eax; char *
0x180017ab7  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180017abe  mov     edx, 0F3h; void *
0x180017ac3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017ac8  nop
0x180017ac9  lea     rcx, [rbp+var_8]
0x180017acd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017ad2  nop
0x180017ad3  lea     rcx, [rbp+var_10]
0x180017ad7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017adc  nop
0x180017add  lea     rcx, [rbp+var_18]
0x180017ae1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017ae6  nop
0x180017ae7  lea     rcx, [rbp+var_20]
0x180017aeb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017af0  nop
0x180017af1  jmp     loc_18001787F
0x180017af6  mov     [rbp+var_8], r12
0x180017afa  mov     rax, [rbp+arg_20]
0x180017afe  mov     [rax], r14
0x180017b01  lea     rcx, [rbp+var_8]
0x180017b05  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017b0a  nop
0x180017b0b  lea     rcx, [rbp+var_10]
0x180017b0f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017b14  nop
0x180017b15  lea     rcx, [rbp+var_18]
0x180017b19  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017b1e  nop
0x180017b1f  lea     rcx, [rbp+var_20]
0x180017b23  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017b28  nop
0x180017b29  xor     eax, eax
0x180017b2b  mov     rbx, [rsp+60h+arg_0]
0x180017b33  add     rsp, 60h
0x180017b37  pop     r15
0x180017b39  pop     r14
0x180017b3b  pop     r13
0x180017b3d  pop     r12
0x180017b3f  pop     rdi
0x180017b40  pop     rsi
0x180017b41  pop     rbp
0x180017b42  retn
```
