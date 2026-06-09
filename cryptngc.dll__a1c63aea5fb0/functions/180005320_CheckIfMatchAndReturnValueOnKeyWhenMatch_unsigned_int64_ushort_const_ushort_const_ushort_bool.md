# CheckIfMatchAndReturnValueOnKeyWhenMatch(unsigned __int64,ushort const *,ushort const *,ushort * *,bool *)

- ea: `0x180005320`
- end: `0x180005677`
- name: `?CheckIfMatchAndReturnValueOnKeyWhenMatch@@YAJ_KPEBG1PEAPEAGPEA_N@Z`
- size: `855`
- prototype: `__int64 __usercall@<rax>(NCRYPT_HANDLE hObject@<rcx>, LPCWSTR pszProperty@<rdx>, LPCWCH lpString1@<r8>, unsigned __int16 **@<r9>, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180004970`

## callees

- `0x180005320`
- `0x180006538`
- `0x180006560`
- `0x180028360`
- `0x18002e7a6`
- `0x18002e850`
- `0x18002f7db`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005661`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005661`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000551d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000551d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800054a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800054b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005532`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000553b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005579`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005582`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800055fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800054a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800054b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005532`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000553b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005579`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005582`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800055fe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005395`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005459`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005395`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005459`
- `ncrypt!NCryptGetProperty` at `0x18000536c`
- `ncrypt!NCryptGetProperty` at `0x1800053d7`
- `ncrypt!NCryptGetProperty` at `0x18000536c`
- `ncrypt!NCryptGetProperty` at `0x1800053d7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000554d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000554d`

## string_xrefs

- `0x180005487`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x1800054be`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x18000555c`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x1800055e7`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x18000562d`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x1800053ec`: `NgcUserSid`

## pseudocode

```c
__int64 __fastcall CheckIfMatchAndReturnValueOnKeyWhenMatch(
        NCRYPT_HANDLE hObject,
        LPCWSTR pszProperty,
        LPCWCH lpString1,
        const WCHAR **a4,
        bool *uBytes)
{
  bool *v5; // r15
  SECURITY_STATUS Property; // eax
  unsigned int v11; // ebx
  __int64 v12; // rsi
  BYTE *v13; // rax
  BYTE *v14; // rbx
  BYTE *i; // rcx
  SECURITY_STATUS v16; // eax
  unsigned int v17; // esi
  __int64 v18; // rcx
  int v19; // edx
  __int64 v20; // rcx
  char *v21; // rax
  size_t v22; // rsi
  size_t v23; // rbp
  char *v24; // rax
  char *v25; // rdi
  const WCHAR *v26; // rdx
  const char *v28; // r9
  unsigned int LastError; // edi
  int pcbResult; // [rsp+20h] [rbp-38h]
  int pcbResulta; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HLOCAL hMem; // [rsp+78h] [rbp+20h] BYREF

  v5 = uBytes;
  LODWORD(uBytes) = 0;
  *v5 = 0;
  *a4 = 0;
  Property = NCryptGetProperty(hObject, pszProperty, 0, 0, (DWORD *)&uBytes, 0);
  v11 = Property;
  if ( Property < 0 )
  {
    if ( Property != -2146893807 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x37A,
        (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
        (const char *)(unsigned int)Property,
        pcbResult);
      return v11;
    }
    if ( !lpString1 || !*lpString1 )
      *v5 = 1;
    return 0;
  }
  if ( !lpString1 )
    return 0;
  v12 = (unsigned int)uBytes;
  v13 = (BYTE *)LocalAlloc(0, (unsigned int)uBytes);
  v14 = v13;
  if ( !v13 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x385,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
      (const char *)0x8007000ELL,
      pcbResult);
    return 2147942414LL;
  }
  for ( i = &v13[v12]; v13 != i; ++v13 )
    *v13 = 0;
  v16 = NCryptGetProperty(hObject, pszProperty, v14, (DWORD)uBytes, (DWORD *)&uBytes, 0);
  v17 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x38D,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
      (const char *)(unsigned int)v16,
      pcbResulta);
    LocalFree(v14);
    return v17;
  }
  hMem = 0;
  v18 = -1;
  do
  {
    v19 = pszProperty[v18 + 1] - aNgcusersid[v18 + 1];
    if ( v19 )
      break;
    v18 += 2;
    if ( v18 == 11 )
      break;
    v19 = pszProperty[v18] - aNgcusersid[v18];
  }
  while ( !v19 );
  if ( v19 )
  {
    v20 = 0x7FFFFFFF;
    v21 = (char *)v14;
    do
    {
      if ( !*(_WORD *)v21 )
        break;
      v21 += 2;
      --v20;
    }
    while ( v20 );
    v22 = 2 * ((v21 - (char *)v14) >> 1);
    v23 = v22 + 2;
    v24 = (char *)LocalAlloc(0, v22 + 2);
    v25 = v24;
    if ( !v24 )
    {
LABEL_15:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &hMem,
        v25);
      v26 = (const WCHAR *)hMem;
      if ( !hMem )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x39C,
          (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
          (const char *)0x8007000ELL,
          pcbResulta);
        if ( hMem )
          LocalFree(hMem);
        LocalFree(v14);
        return 2147942414LL;
      }
LABEL_23:
      if ( *lpString1 )
      {
        if ( CompareStringOrdinal(lpString1, -1, v26, -1, 1) != 2 )
        {
          if ( hMem )
            LocalFree(hMem);
          goto LABEL_27;
        }
        v26 = (const WCHAR *)hMem;
      }
      *v5 = 1;
      *a4 = v26;
      hMem = 0;
LABEL_27:
      LocalFree(v14);
      return 0;
    }
    if ( v22 )
    {
      if ( v23 >= v22 )
      {
        memcpy_0(v24, v14, v22);
        *(_WORD *)&v25[v22] = 0;
        goto LABEL_15;
      }
      memset_0(v24, 0, v23);
      *(_DWORD *)_o__errno() = 34;
      invalid_parameter_noinfo();
    }
    *(_WORD *)&v25[v22] = 0;
    goto LABEL_15;
  }
  if ( ConvertSidToStringSidW(v14, (LPWSTR *)&hMem) )
  {
    v26 = (const WCHAR *)hMem;
    goto LABEL_23;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x396,
                (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
                v28);
  if ( hMem )
    LocalFree(hMem);
  LocalFree(v14);
  return LastError;
}

```

## disassembly

```asm
0x180005320  mov     r11, rsp
0x180005323  mov     [r11+10h], rbx
0x180005327  mov     [r11+18h], rbp
0x18000532b  push    rdi
0x18000532c  push    r12
0x18000532e  push    r13
0x180005330  push    r14
0x180005332  push    r15
0x180005334  sub     rsp, 30h
0x180005338  mov     r15, [rsp+58h+uBytes]
0x180005340  lea     rax, [r11+28h]
0x180005344  xor     r13d, r13d
0x180005347  mov     r12, r9
0x18000534a  mov     r14, r8
0x18000534d  mov     [r11-30h], r13d
0x180005351  xor     r8d, r8d; pbOutput
0x180005354  mov     [r11+28h], r13d
0x180005358  mov     byte ptr [r15], 0
0x18000535c  mov     rdi, rdx
0x18000535f  mov     [r9], r13
0x180005362  mov     rbp, rcx
0x180005365  xor     r9d, r9d; cbOutput
0x180005368  mov     [r11-38h], rax
0x18000536c  call    cs:__imp_NCryptGetProperty
0x180005372  mov     ebx, eax
0x180005374  test    eax, eax
0x180005376  js      loc_1800055A3
0x18000537c  test    r14, r14
0x18000537f  jz      loc_1800055B8
0x180005385  mov     [rsp+58h+arg_0], rsi
0x18000538a  xor     ecx, ecx; uFlags
0x18000538c  mov     esi, dword ptr [rsp+58h+uBytes]
0x180005393  mov     edx, esi; uBytes
0x180005395  call    cs:__imp_LocalAlloc
0x18000539b  mov     rbx, rax
0x18000539e  test    rax, rax
0x1800053a1  jz      loc_1800054B9
0x1800053a7  lea     rcx, [rsi+rax]
0x1800053ab  cmp     rax, rcx
0x1800053ae  jnz     loc_1800055D0
0x1800053b4  mov     r9d, dword ptr [rsp+58h+uBytes]; cbOutput
0x1800053bc  lea     rax, [rsp+58h+uBytes]
0x1800053c4  mov     [rsp+58h+dwFlags], r13d; dwFlags
0x1800053c9  mov     r8, rbx; pbOutput
0x1800053cc  mov     rdx, rdi; pszProperty
0x1800053cf  mov     [rsp+58h+pcbResult], rax; int
0x1800053d4  mov     rcx, rbp; hObject
0x1800053d7  call    cs:__imp_NCryptGetProperty
0x1800053dd  mov     esi, eax
0x1800053df  test    eax, eax
0x1800053e1  js      loc_1800055E2
0x1800053e7  mov     [rsp+58h+hMem], r13
0x1800053ec  lea     r8, aNgcusersid; "NgcUserSid"
0x1800053f3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800053fa  nop     word ptr [rax+rax+00h]
0x180005400  movzx   edx, word ptr [rdi+rcx*2+2]
0x180005405  movzx   eax, word ptr [r8+rcx*2+2]
0x18000540b  sub     edx, eax
0x18000540d  jnz     short loc_180005426
0x18000540f  add     rcx, 2
0x180005413  cmp     rcx, 0Bh
0x180005417  jz      short loc_180005426
0x180005419  movzx   edx, word ptr [rdi+rcx*2]
0x18000541d  movzx   eax, word ptr [r8+rcx*2]
0x180005422  sub     edx, eax
0x180005424  jz      short loc_180005400
0x180005426  test    edx, edx
0x180005428  jz      loc_180005545
0x18000542e  mov     ecx, 7FFFFFFFh
0x180005433  mov     rax, rbx
0x180005436  cmp     [rax], r13w
0x18000543a  jz      short loc_180005446
0x18000543c  add     rax, 2
0x180005440  sub     rcx, 1
0x180005444  jnz     short loc_180005436
0x180005446  sub     rax, rbx
0x180005449  xor     ecx, ecx; uFlags
0x18000544b  sar     rax, 1
0x18000544e  lea     rsi, [rax+rax]
0x180005452  lea     rbp, [rsi+2]
0x180005456  mov     rdx, rbp; uBytes
0x180005459  call    cs:__imp_LocalAlloc
0x18000545f  mov     rdi, rax
0x180005462  test    rax, rax
0x180005465  jnz     loc_1800055BF
0x18000546b  mov     rdx, rdi
0x18000546e  lea     rcx, [rsp+58h+hMem]
0x180005473  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180005478  mov     rdx, [rsp+58h+hMem]
0x18000547d  test    rdx, rdx
0x180005480  jnz     short loc_1800054FC
0x180005482  mov     rcx, [rsp+58h]; this
0x180005487  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x18000548e  mov     r9d, 8007000Eh; char *
0x180005494  mov     edx, 39Ch; void *
0x180005499  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000549e  mov     rcx, [rsp+58h+hMem]; hMem
0x1800054a3  test    rcx, rcx
0x1800054a6  jz      short loc_1800054AE
0x1800054a8  call    cs:__imp_LocalFree
0x1800054ae  mov     rcx, rbx; hMem
0x1800054b1  call    cs:__imp_LocalFree
0x1800054b7  jmp     short loc_1800054D5
0x1800054b9  mov     rcx, [rsp+58h]; this
0x1800054be  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x1800054c5  mov     r9d, 8007000Eh; char *
0x1800054cb  mov     edx, 385h; void *
0x1800054d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800054d5  mov     eax, 8007000Eh
0x1800054da  mov     rsi, [rsp+58h+arg_0]
0x1800054df  mov     rbx, [rsp+58h+arg_8]
0x1800054e4  mov     rbp, [rsp+58h+arg_10]
0x1800054e9  add     rsp, 30h
0x1800054ed  pop     r15
0x1800054ef  pop     r14
0x1800054f1  pop     r13
0x1800054f3  pop     r12
0x1800054f5  pop     rdi
0x1800054f6  retn
0x1800054f7  mov     rdx, [rsp+58h+hMem]
0x1800054fc  cmp     [r14], r13w
0x180005500  jz      loc_180005594
0x180005506  mov     r9d, 0FFFFFFFFh; cchCount2
0x18000550c  mov     dword ptr [rsp+58h+pcbResult], 1; bIgnoreCase
0x180005514  mov     r8, rdx; lpString2
0x180005517  mov     rcx, r14; lpString1
0x18000551a  mov     edx, r9d; cchCount1
0x18000551d  call    cs:__imp_CompareStringOrdinal
0x180005523  cmp     eax, 2
0x180005526  jz      short loc_18000558F
0x180005528  mov     rcx, [rsp+58h+hMem]; hMem
0x18000552d  test    rcx, rcx
0x180005530  jz      short loc_180005538
0x180005532  call    cs:__imp_LocalFree
0x180005538  mov     rcx, rbx; hMem
0x18000553b  call    cs:__imp_LocalFree
0x180005541  xor     eax, eax
0x180005543  jmp     short loc_1800054DA
0x180005545  lea     rdx, [rsp+58h+hMem]; StringSid
0x18000554a  mov     rcx, rbx; Sid
0x18000554d  call    cs:__imp_ConvertSidToStringSidW
0x180005553  test    eax, eax
0x180005555  jnz     short loc_1800054F7
0x180005557  mov     rcx, [rsp+58h]; this
0x18000555c  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180005563  mov     edx, 396h; void *
0x180005568  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000556d  mov     rcx, [rsp+58h+hMem]; hMem
0x180005572  mov     edi, eax
0x180005574  test    rcx, rcx
0x180005577  jz      short loc_18000557F
0x180005579  call    cs:__imp_LocalFree
0x18000557f  mov     rcx, rbx; hMem
0x180005582  call    cs:__imp_LocalFree
0x180005588  mov     eax, edi
0x18000558a  jmp     loc_1800054DA
0x18000558f  mov     rdx, [rsp+58h+hMem]
0x180005594  mov     byte ptr [r15], 1
0x180005598  mov     [r12], rdx
0x18000559c  mov     [rsp+58h+hMem], r13
0x1800055a1  jmp     short loc_180005538
0x1800055a3  cmp     ebx, 80090011h
0x1800055a9  jnz     short loc_180005628
0x1800055ab  test    r14, r14
0x1800055ae  jnz     loc_180005648
0x1800055b4  mov     byte ptr [r15], 1
0x1800055b8  xor     eax, eax
0x1800055ba  jmp     loc_1800054DF
0x1800055bf  test    rsi, rsi
0x1800055c2  jnz     short loc_18000560B
0x1800055c4  mov     [rsi+rdi], r13w
0x1800055c9  jmp     loc_18000546B
0x1800055d0  xor     edx, edx
0x1800055d2  mov     [rax], dl
0x1800055d4  inc     rax
0x1800055d7  cmp     rax, rcx
0x1800055da  jz      loc_1800053B4
0x1800055e0  jmp     short loc_1800055D0
0x1800055e2  mov     rcx, [rsp+58h]; this
0x1800055e7  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x1800055ee  mov     r9d, esi; char *
0x1800055f1  mov     edx, 38Dh; void *
0x1800055f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800055fb  mov     rcx, rbx; hMem
0x1800055fe  call    cs:__imp_LocalFree
0x180005604  mov     eax, esi
0x180005606  jmp     loc_1800054DA
0x18000560b  mov     rcx, rdi; void *
0x18000560e  cmp     rbp, rsi
0x180005611  jb      short loc_180005657
0x180005613  mov     r8, rsi; Size
0x180005616  mov     rdx, rbx; Src
0x180005619  call    memcpy_0
0x18000561e  mov     [rsi+rdi], r13w
0x180005623  jmp     loc_18000546B
0x180005628  mov     rcx, [rsp+58h]; this
0x18000562d  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180005634  mov     r9d, ebx; char *
0x180005637  mov     edx, 37Ah; void *
0x18000563c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005641  mov     eax, ebx
0x180005643  jmp     loc_1800054DF
0x180005648  cmp     [r14], r13w
0x18000564c  jnz     loc_1800055B8
0x180005652  jmp     loc_1800055B4
0x180005657  mov     r8, rbp; Size
0x18000565a  xor     edx, edx; Val
0x18000565c  call    memset_0
0x180005661  call    cs:__imp__o__errno
0x180005667  mov     dword ptr [rax], 22h ; '"'
0x18000566d  call    _invalid_parameter_noinfo
0x180005672  jmp     loc_1800055C4
```
