# GetMatchedKey(unsigned __int64,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,_NGC_USER_ID_KEY_INFO * *,bool *)

- ea: `0x180004970`
- end: `0x180004e2f`
- name: `?GetMatchedKey@@YAJ_KPEBG1111PEAPEAU_NGC_USER_ID_KEY_INFO@@PEA_N@Z`
- size: `1215`
- prototype: `__int64 __usercall@<rax>(NCRYPT_PROV_HANDLE hProvider@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *, const unsigned __int16 *, struct _NGC_USER_ID_KEY_INFO **, bool *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002e10`

## callees

- `0x180004970`
- `0x180005320`
- `0x180006538`
- `0x1800065c0`
- `0x18002e180`
- `0x18002e1f4`
- `0x18002f7db`
- `0x180032fcc`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004df5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004df5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004e0a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004e0a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004e02`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004e02`
- `ncrypt!NCryptFreeObject` at `0x180004c16`
- `ncrypt!NCryptFreeObject` at `0x180004c80`
- `ncrypt!NCryptFreeObject` at `0x180004d5c`
- `ncrypt!NCryptFreeObject` at `0x180004db7`
- `ncrypt!NCryptFreeObject` at `0x180004c16`
- `ncrypt!NCryptFreeObject` at `0x180004c80`
- `ncrypt!NCryptFreeObject` at `0x180004d5c`
- `ncrypt!NCryptFreeObject` at `0x180004db7`
- `ncrypt!NCryptOpenKey` at `0x180004a38`
- `ncrypt!NCryptOpenKey` at `0x180004a38`
- `ncrypt!NCryptGetProperty` at `0x180004beb`
- `ncrypt!NCryptGetProperty` at `0x180004beb`

## string_xrefs

- `0x180004c64`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x180004d40`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x180004d9b`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x180004e18`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x1800049d7`: `NgcUserSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetMatchedKey(
        NCRYPT_PROV_HANDLE hProvider,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *pszKeyName,
        struct _NGC_USER_ID_KEY_INFO **a7,
        bool *a8)
{
  SECURITY_STATUS v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // rdi
  __int64 v12; // rax
  unsigned int v13; // r13d
  int i; // r12d
  HLOCAL *v15; // r14
  int v16; // eax
  unsigned int v17; // ebx
  __int64 v18; // rax
  HLOCAL v19; // r14
  char *v20; // r15
  __int64 v21; // rax
  size_t v22; // rbx
  char *v23; // rsi
  char *v24; // r15
  char *v25; // r15
  char *v26; // r15
  SECURITY_STATUS Property; // eax
  NCRYPT_HANDLE v28; // rcx
  __int64 v30; // rax
  size_t v31; // rbx
  __int64 v32; // rax
  size_t v33; // rbx
  __int64 v34; // rax
  size_t v35; // rbx
  DWORD LastError; // ebx
  int dwFlags; // [rsp+20h] [rbp-B1h]
  int dwFlagsa; // [rsp+20h] [rbp-B1h]
  bool v39; // [rsp+30h] [rbp-A1h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+38h] [rbp-99h] BYREF
  DWORD pcbResult; // [rsp+40h] [rbp-91h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-89h] BYREF
  bool *v43; // [rsp+50h] [rbp-81h]
  struct _NGC_USER_ID_KEY_INFO **v44; // [rsp+58h] [rbp-79h]
  LPCWCH lpString1[4]; // [rsp+60h] [rbp-71h]
  LPCWSTR pszProperty[4]; // [rsp+80h] [rbp-51h]
  void *v47; // [rsp+A0h] [rbp-31h] BYREF
  void *v48; // [rsp+A8h] [rbp-29h]
  void *v49; // [rsp+B0h] [rbp-21h]
  void *Src; // [rsp+B8h] [rbp-19h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+47h]

  v44 = a7;
  v43 = a8;
  pszProperty[0] = L"NgcDomainName";
  pszProperty[1] = L"NgcTenantDomainName";
  pszProperty[2] = L"NgcAccountId";
  pszProperty[3] = L"NgcUserSid";
  lpString1[0] = a2;
  lpString1[1] = a3;
  lpString1[2] = a4;
  lpString1[3] = a5;
  `eh vector constructor iterator'(
    &v47,
    8u,
    4u,
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>);
  *a8 = 0;
  phKey = 0;
  v9 = NCryptOpenKey(hProvider, &phKey, pszKeyName, 0, 0);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D8,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
      (const char *)(unsigned int)v9,
      dwFlags);
    if ( phKey )
      NCryptFreeObject(phKey);
    `eh vector destructor iterator'(
      &v47,
      8u,
      4u,
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>);
    return v10;
  }
  else
  {
    v11 = -1;
    v12 = -1;
    do
      ++v12;
    while ( pszKeyName[v12] );
    v13 = 2 * v12 + 50;
    for ( i = 0; (unsigned __int64)i < 4; ++i )
    {
      v39 = 0;
      v15 = &v47 + i;
      hMem = *v15;
      if ( hMem )
      {
        LastError = GetLastError();
        LocalFree(hMem);
        SetLastError(LastError);
      }
      *v15 = 0;
      v16 = CheckIfMatchAndReturnValueOnKeyWhenMatch(
              phKey,
              pszProperty[i],
              lpString1[i],
              (const WCHAR **)&v47 + i,
              &v39);
      v17 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3E4,
          (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
          (const char *)(unsigned int)v16,
          dwFlags);
        if ( phKey )
          NCryptFreeObject(phKey);
        `eh vector destructor iterator'(
          &v47,
          8u,
          4u,
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>);
        return v17;
      }
      if ( !v39 )
      {
        v28 = phKey;
        if ( phKey )
          goto LABEL_32;
        goto LABEL_33;
      }
      if ( *v15 )
      {
        v18 = -1;
        do
          ++v18;
        while ( *((_WORD *)*v15 + v18) );
        v13 += 2 * v18 + 2;
      }
    }
    wil::make_unique_hlocal_nothrow<unsigned char [0]>(&hMem, v13);
    v19 = hMem;
    if ( hMem )
    {
      v20 = (char *)hMem + 48;
      if ( pszKeyName )
      {
        v21 = -1;
        do
          ++v21;
        while ( pszKeyName[v21] );
        v22 = (unsigned int)(2 * v21 + 2);
        memcpy_0((char *)hMem + 48, pszKeyName, v22);
        v23 = &v20[v22];
      }
      else
      {
        v23 = (char *)hMem + 48;
        v20 = 0;
      }
      *((_QWORD *)v19 + 4) = v20;
      if ( v47 )
      {
        v24 = v23;
        v30 = -1;
        do
          ++v30;
        while ( *((_WORD *)v47 + v30) );
        v31 = (unsigned int)(2 * v30 + 2);
        memcpy_0(v23, v47, v31);
        v23 += v31;
      }
      else
      {
        v24 = 0;
      }
      *(_QWORD *)v19 = v24;
      if ( v48 )
      {
        v25 = v23;
        v32 = -1;
        do
          ++v32;
        while ( *((_WORD *)v48 + v32) );
        v33 = (unsigned int)(2 * v32 + 2);
        memcpy_0(v23, v48, v33);
        v23 += v33;
      }
      else
      {
        v25 = 0;
      }
      *((_QWORD *)v19 + 1) = v25;
      if ( v49 )
      {
        v26 = v23;
        v34 = -1;
        do
          ++v34;
        while ( *((_WORD *)v49 + v34) );
        v35 = (unsigned int)(2 * v34 + 2);
        memcpy_0(v23, v49, v35);
        v23 += v35;
      }
      else
      {
        v26 = 0;
      }
      *((_QWORD *)v19 + 2) = v26;
      if ( Src )
      {
        do
          ++v11;
        while ( *((_WORD *)Src + v11) );
        memcpy_0(v23, Src, (unsigned int)(2 * v11 + 2));
      }
      else
      {
        v23 = 0;
      }
      *((_QWORD *)v19 + 3) = v23;
      pcbResult = 0;
      Property = NCryptGetProperty(phKey, L"NgcContainerStatus", (PBYTE)v19 + 40, 4u, &pcbResult, 0);
      if ( Property < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x407,
          (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
          (const char *)(unsigned int)Property,
          dwFlagsa);
      *v43 = 1;
      *v44 = (struct _NGC_USER_ID_KEY_INFO *)v19;
      v28 = phKey;
      if ( phKey )
LABEL_32:
        NCryptFreeObject(v28);
LABEL_33:
      `eh vector destructor iterator'(
        &v47,
        8u,
        4u,
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F2,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
      (const char *)0x8007000ELL,
      dwFlags);
    if ( phKey )
      NCryptFreeObject(phKey);
    `eh vector destructor iterator'(
      &v47,
      8u,
      4u,
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180004970  push    rbp
0x180004972  push    rbx
0x180004973  push    rsi
0x180004974  push    rdi
0x180004975  push    r12
0x180004977  push    r13
0x180004979  push    r14
0x18000497b  push    r15
0x18000497d  lea     rbp, [rsp-7]
0x180004982  sub     rsp, 0D8h
0x180004989  mov     rax, cs:__security_cookie
0x180004990  xor     rax, rsp
0x180004993  mov     [rbp+3Fh+var_50], rax
0x180004997  mov     rbx, rcx
0x18000499a  mov     rax, [rbp+3Fh+arg_20]
0x18000499e  mov     rsi, [rbp+3Fh+pszKeyName]
0x1800049a2  mov     rcx, [rbp+3Fh+arg_30]
0x1800049a6  mov     [rbp+3Fh+var_B8], rcx
0x1800049aa  mov     rdi, [rbp+3Fh+arg_38]
0x1800049b1  mov     [rsp+110h+var_C0], rdi
0x1800049b6  lea     rcx, aNgcdomainname; "NgcDomainName"
0x1800049bd  mov     [rbp+3Fh+pszProperty], rcx
0x1800049c1  lea     rcx, aNgctenantdomai; "NgcTenantDomainName"
0x1800049c8  mov     [rbp+3Fh+var_88], rcx
0x1800049cc  lea     rcx, aNgcaccountid; "NgcAccountId"
0x1800049d3  mov     [rbp+3Fh+var_80], rcx
0x1800049d7  lea     rcx, aNgcusersid; "NgcUserSid"
0x1800049de  mov     [rbp+3Fh+var_78], rcx
0x1800049e2  mov     [rbp+3Fh+lpString1], rdx
0x1800049e6  mov     [rbp+3Fh+var_A8], r8
0x1800049ea  mov     [rbp+3Fh+var_A0], r9
0x1800049ee  mov     [rbp+3Fh+var_98], rax
0x1800049f2  lea     r15, ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800049f9  mov     qword ptr [rsp+110h+dwFlags], r15; void (*)(void *)
0x1800049fe  lea     r9, ??0?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x180004a05  mov     edx, 8; unsigned __int64
0x180004a0a  mov     r8d, 4; unsigned __int64
0x180004a10  lea     rcx, [rbp+3Fh+var_70]; void *
0x180004a14  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180004a19  nop
0x180004a1a  mov     byte ptr [rdi], 0
0x180004a1d  xor     r14d, r14d
0x180004a20  mov     [rsp+110h+phKey], r14
0x180004a25  mov     [rsp+110h+dwFlags], r14d; int
0x180004a2a  xor     r9d, r9d; dwLegacyKeySpec
0x180004a2d  mov     r8, rsi; pszKeyName
0x180004a30  lea     rdx, [rsp+110h+phKey]; phKey
0x180004a35  mov     rcx, rbx; hProvider
0x180004a38  call    cs:__imp_NCryptOpenKey
0x180004a3e  mov     ebx, eax
0x180004a40  test    eax, eax
0x180004a42  js      loc_180004D39
0x180004a48  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180004a4f  mov     rax, rdi
0x180004a52  lea     rax, [rax+1]
0x180004a56  cmp     [rsi+rax*2], r14w
0x180004a5b  jnz     short loc_180004A52
0x180004a5d  lea     r13d, ds:32h[rax*2]
0x180004a65  mov     r12d, r14d
0x180004a68  movsxd  r15, r12d
0x180004a6b  cmp     r15, 4
0x180004a6f  jnb     loc_180004AFC
0x180004a75  mov     [rsp+110h+var_E0], 0
0x180004a7a  lea     r14, [rbp+3Fh+var_70]
0x180004a7e  lea     r14, [r14+r15*8]
0x180004a82  mov     rax, [r14]
0x180004a85  mov     [rsp+110h+hMem], rax
0x180004a8a  test    rax, rax
0x180004a8d  jnz     loc_180004DF5
0x180004a93  mov     qword ptr [r14], 0
0x180004a9a  lea     rax, [rsp+110h+var_E0]
0x180004a9f  mov     qword ptr [rsp+110h+dwFlags], rax; int
0x180004aa4  mov     r9, r14; unsigned __int16 **
0x180004aa7  mov     r8, [rbp+r15*8+3Fh+lpString1]; lpString1
0x180004aac  mov     rdx, [rbp+r15*8+3Fh+pszProperty]; pszProperty
0x180004ab1  mov     rcx, [rsp+110h+phKey]; hObject
0x180004ab6  call    ?CheckIfMatchAndReturnValueOnKeyWhenMatch@@YAJ_KPEBG1PEAPEAGPEA_N@Z; CheckIfMatchAndReturnValueOnKeyWhenMatch(unsigned __int64,ushort const *,ushort const *,ushort * *,bool *)
0x180004abb  mov     ebx, eax
0x180004abd  test    eax, eax
0x180004abf  js      loc_180004D94
0x180004ac5  cmp     [rsp+110h+var_E0], 0
0x180004aca  jz      loc_180004D81
0x180004ad0  mov     rcx, [r14]
0x180004ad3  test    rcx, rcx
0x180004ad6  jz      short loc_180004AF4
0x180004ad8  mov     rax, rdi
0x180004adb  nop     dword ptr [rax+rax+00h]
0x180004ae0  lea     rax, [rax+1]
0x180004ae4  cmp     word ptr [rcx+rax*2], 0
0x180004ae9  jnz     short loc_180004AE0
0x180004aeb  lea     r13d, [r13+rax*2+0]
0x180004af0  add     r13d, 2
0x180004af4  inc     r12d
0x180004af7  jmp     loc_180004A68
0x180004afc  mov     edx, r13d
0x180004aff  lea     rcx, [rsp+110h+hMem]
0x180004b04  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x180004b09  nop
0x180004b0a  mov     r14, [rsp+110h+hMem]
0x180004b0f  test    r14, r14
0x180004b12  jz      loc_180004C5A
0x180004b18  lea     r15, [r14+30h]
0x180004b1c  test    rsi, rsi
0x180004b1f  jz      loc_180004DE0
0x180004b25  mov     rax, rdi
0x180004b28  nop     dword ptr [rax+rax+00000000h]
0x180004b30  lea     rax, [rax+1]
0x180004b34  cmp     word ptr [rsi+rax*2], 0
0x180004b39  jnz     short loc_180004B30
0x180004b3b  lea     eax, ds:2[rax*2]
0x180004b42  mov     ebx, eax
0x180004b44  mov     r8d, eax; Size
0x180004b47  mov     rdx, rsi; Src
0x180004b4a  mov     rcx, r15; void *
0x180004b4d  call    memcpy_0
0x180004b52  lea     rsi, [rbx+r15]
0x180004b56  xor     ebx, ebx
0x180004b58  mov     [r14+20h], r15
0x180004b5c  mov     rdx, [rbp+3Fh+var_70]; Src
0x180004b60  test    rdx, rdx
0x180004b63  jnz     loc_180004CA9
0x180004b69  mov     r15, rbx
0x180004b6c  mov     [r14], r15
0x180004b6f  mov     rdx, [rbp+3Fh+var_68]; Src
0x180004b73  test    rdx, rdx
0x180004b76  jnz     loc_180004CD9
0x180004b7c  mov     r15, rbx
0x180004b7f  mov     [r14+8], r15
0x180004b83  mov     rdx, [rbp+3Fh+var_60]; Src
0x180004b87  test    rdx, rdx
0x180004b8a  jnz     loc_180004D09
0x180004b90  mov     r15, rbx
0x180004b93  mov     [r14+10h], r15
0x180004b97  mov     rdx, [rbp+3Fh+Src]; Src
0x180004b9b  test    rdx, rdx
0x180004b9e  jz      loc_180004DED
0x180004ba4  lea     rdi, [rdi+1]
0x180004ba8  cmp     word ptr [rdx+rdi*2], 0
0x180004bad  jnz     short loc_180004BA4
0x180004baf  lea     r8d, ds:2[rdi*2]; Size
0x180004bb7  mov     rcx, rsi; void *
0x180004bba  call    memcpy_0
0x180004bbf  mov     [r14+18h], rsi
0x180004bc3  mov     [rsp+110h+pcbResult], ebx
0x180004bc7  lea     r8, [r14+28h]; pbOutput
0x180004bcb  mov     [rsp+110h+var_E8], ebx; dwFlags
0x180004bcf  lea     rax, [rsp+110h+pcbResult]
0x180004bd4  mov     qword ptr [rsp+110h+dwFlags], rax; int
0x180004bd9  mov     r9d, 4; cbOutput
0x180004bdf  lea     rdx, pszProperty; "NgcContainerStatus"
0x180004be6  mov     rcx, [rsp+110h+phKey]; hObject
0x180004beb  call    cs:__imp_NCryptGetProperty
0x180004bf1  mov     rcx, [rbp+47h]; this
0x180004bf5  test    eax, eax
0x180004bf7  js      loc_180004E15
0x180004bfd  mov     rax, [rsp+110h+var_C0]
0x180004c02  mov     byte ptr [rax], 1
0x180004c05  mov     rax, [rbp+3Fh+var_B8]
0x180004c09  mov     [rax], r14
0x180004c0c  mov     rcx, [rsp+110h+phKey]; hObject
0x180004c11  test    rcx, rcx
0x180004c14  jz      short loc_180004C1D
0x180004c16  call    cs:__imp_NCryptFreeObject
0x180004c1c  nop
0x180004c1d  lea     r9, ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x180004c24  mov     edx, 8; unsigned __int64
0x180004c29  mov     r8d, 4; unsigned __int64
0x180004c2f  lea     rcx, [rbp+3Fh+var_70]; void *
0x180004c33  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180004c38  xor     eax, eax
0x180004c3a  mov     rcx, [rbp+3Fh+var_50]
0x180004c3e  xor     rcx, rsp; StackCookie
0x180004c41  call    __security_check_cookie
0x180004c46  add     rsp, 0D8h
0x180004c4d  pop     r15
0x180004c4f  pop     r14
0x180004c51  pop     r13
0x180004c53  pop     r12
0x180004c55  pop     rdi
0x180004c56  pop     rsi
0x180004c57  pop     rbx
0x180004c58  pop     rbp
0x180004c59  retn
0x180004c5a  mov     rcx, [rbp+47h]; this
0x180004c5e  mov     r9d, 8007000Eh; char *
0x180004c64  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180004c6b  mov     edx, 3F2h; void *
0x180004c70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004c75  nop
0x180004c76  mov     rcx, [rsp+110h+phKey]; hObject
0x180004c7b  test    rcx, rcx
0x180004c7e  jz      short loc_180004C87
0x180004c80  call    cs:__imp_NCryptFreeObject
0x180004c86  nop
0x180004c87  lea     r9, ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x180004c8e  mov     edx, 8; unsigned __int64
0x180004c93  mov     r8d, 4; unsigned __int64
0x180004c99  lea     rcx, [rbp+3Fh+var_70]; void *
0x180004c9d  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180004ca2  mov     eax, 8007000Eh
0x180004ca7  jmp     short loc_180004C3A
0x180004ca9  mov     r15, rsi
0x180004cac  mov     rax, rdi
0x180004caf  nop
0x180004cb0  lea     rax, [rax+1]
0x180004cb4  cmp     word ptr [rdx+rax*2], 0
0x180004cb9  jnz     short loc_180004CB0
0x180004cbb  lea     eax, ds:2[rax*2]
0x180004cc2  mov     ebx, eax
0x180004cc4  mov     r8d, eax; Size
0x180004cc7  mov     rcx, rsi; void *
0x180004cca  call    memcpy_0
0x180004ccf  add     rsi, rbx
0x180004cd2  xor     ebx, ebx
0x180004cd4  jmp     loc_180004B6C
0x180004cd9  mov     r15, rsi
0x180004cdc  mov     rax, rdi
0x180004cdf  nop
0x180004ce0  lea     rax, [rax+1]
0x180004ce4  cmp     word ptr [rdx+rax*2], 0
0x180004ce9  jnz     short loc_180004CE0
0x180004ceb  lea     eax, ds:2[rax*2]
0x180004cf2  mov     ebx, eax
0x180004cf4  mov     r8d, eax; Size
0x180004cf7  mov     rcx, rsi; void *
0x180004cfa  call    memcpy_0
0x180004cff  add     rsi, rbx
0x180004d02  xor     ebx, ebx
0x180004d04  jmp     loc_180004B7F
0x180004d09  mov     r15, rsi
0x180004d0c  mov     rax, rdi
0x180004d0f  nop
0x180004d10  lea     rax, [rax+1]
0x180004d14  cmp     word ptr [rdx+rax*2], 0
0x180004d19  jnz     short loc_180004D10
0x180004d1b  lea     eax, ds:2[rax*2]
0x180004d22  mov     ebx, eax
0x180004d24  mov     r8d, eax; Size
0x180004d27  mov     rcx, rsi; void *
0x180004d2a  call    memcpy_0
0x180004d2f  add     rsi, rbx
0x180004d32  xor     ebx, ebx
0x180004d34  jmp     loc_180004B93
0x180004d39  mov     rcx, [rbp+47h]; this
0x180004d3d  mov     r9d, ebx; char *
0x180004d40  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180004d47  mov     edx, 3D8h; void *
0x180004d4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004d51  nop
0x180004d52  mov     rcx, [rsp+110h+phKey]; hObject
0x180004d57  test    rcx, rcx
0x180004d5a  jz      short loc_180004D63
0x180004d5c  call    cs:__imp_NCryptFreeObject
0x180004d62  nop
0x180004d63  mov     r9, r15; void (*)(void *)
0x180004d66  mov     edx, 8; unsigned __int64
0x180004d6b  mov     r8d, 4; unsigned __int64
0x180004d71  lea     rcx, [rbp+3Fh+var_70]; void *
0x180004d75  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180004d7a  mov     eax, ebx
0x180004d7c  jmp     loc_180004C3A
0x180004d81  mov     rcx, [rsp+110h+phKey]
0x180004d86  test    rcx, rcx
0x180004d89  jz      loc_180004C1D
0x180004d8f  jmp     loc_180004C16
0x180004d94  mov     rcx, [rbp+47h]; this
0x180004d98  mov     r9d, ebx; char *
0x180004d9b  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180004da2  mov     edx, 3E4h; void *
0x180004da7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004dac  nop
0x180004dad  mov     rcx, [rsp+110h+phKey]; hObject
0x180004db2  test    rcx, rcx
0x180004db5  jz      short loc_180004DBE
0x180004db7  call    cs:__imp_NCryptFreeObject
0x180004dbd  nop
0x180004dbe  lea     r9, ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x180004dc5  mov     edx, 8; unsigned __int64
0x180004dca  mov     r8d, 4; unsigned __int64
0x180004dd0  lea     rcx, [rbp+3Fh+var_70]; void *
0x180004dd4  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180004dd9  mov     eax, ebx
0x180004ddb  jmp     loc_180004C3A
0x180004de0  mov     rsi, r15
0x180004de3  xor     ebx, ebx
0x180004de5  mov     r15d, ebx
0x180004de8  jmp     loc_180004B58
0x180004ded  mov     rsi, rbx
0x180004df0  jmp     loc_180004BBF
0x180004df5  call    cs:__imp_GetLastError
0x180004dfb  mov     ebx, eax
0x180004dfd  mov     rcx, [rsp+110h+hMem]; hMem
0x180004e02  call    cs:__imp_LocalFree
0x180004e08  mov     ecx, ebx; dwErrCode
0x180004e0a  call    cs:__imp_SetLastError
0x180004e10  jmp     loc_180004A93
0x180004e15  mov     r9d, eax; char *
0x180004e18  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180004e1f  mov     edx, 407h; void *
0x180004e24  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
  ... truncated ...
```
