# KerbCredIsoIum::CreateApReqAuthenticator(_KERB_ENCRYPTION_KEY *,ulong,_KERB_INTERNAL_NAME *,_UNICODE_STRING *,KERB_ADJUSTED_TIME *,_KERB_ENCRYPTION_KEY *,PKERB_AUTHORIZATION_DATA_s *,KERB_CHECKSUM *,ulong,_LARGE_INTEGER *,long *,KERB_ENCRYPTED_DATA *)

- ea: `0x180052e50`
- end: `0x1800531e9`
- name: `?CreateApReqAuthenticator@KerbCredIsoIum@@UEAAJPEAU_KERB_ENCRYPTION_KEY@@KPEAU_KERB_INTERNAL_NAME@@PEAU_UNICODE_STRING@@PEAUKERB_ADJUSTED_TIME@@0PEAUPKERB_AUTHORIZATION_DATA_s@@PEAUKERB_CHECKSUM@@KPEAT_LARGE_INTEGER@@PEAJPEAUKERB_ENCRYPTED_DATA@@@Z`
- size: `921`
- prototype: `__int64 __fastcall(KerbCredIsoIum *__hidden this, struct _KERB_ENCRYPTION_KEY *, unsigned int, struct _KERB_INTERNAL_NAME *, struct _UNICODE_STRING *, struct KERB_ADJUSTED_TIME *, struct _KERB_ENCRYPTION_KEY *, struct PKERB_AUTHORIZATION_DATA_s *, struct KERB_CHECKSUM *, unsigned int, union _LARGE_INTEGER *, int *, struct KERB_ENCRYPTED_DATA *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x180024ed0`
- `0x18002ac60`
- `0x180052e50`
- `0x18007108c`
- `0x1800744cf`
- `0x18008b70c`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800530b8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800530b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053138`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053166`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053194`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053138`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053166`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053194`
- `KerbClientShared!KerbClientPackAsn1Buffer` at `0x180052ec9`
- `KerbClientShared!KerbClientPackAsn1Buffer` at `0x180052eef`
- `KerbClientShared!KerbClientPackAsn1Buffer` at `0x180052ec9`
- `KerbClientShared!KerbClientPackAsn1Buffer` at `0x180052eef`
- `KerbClientShared!KerbClientUnpackAsn1BufferVoid` at `0x18005305e`
- `KerbClientShared!KerbClientUnpackAsn1BufferVoid` at `0x18005305e`
- `RPCRT4!I_RpcMapWin32Status` at `0x180052fdd`
- `RPCRT4!I_RpcMapWin32Status` at `0x180052fdd`
- `RPCRT4!RpcExceptionFilter` at `0x1800f2cce`
- `RPCRT4!RpcExceptionFilter` at `0x1800f2cce`

## string_xrefs

- `0x180052efb`: `KerbCredIsoIum::CreateApReqAuthenticator`
- `0x180052f07`: `KerbCredIsoIum::CreateApReqAuthenticator`
- `0x180052fed`: `KerbCredIsoIum::CreateApReqAuthenticator`
- `0x180053017`: `KerbCredIsoIum::CreateApReqAuthenticator`
- `0x1800531b4`: `%hs: CreateApReqAuthenticatorFailed. %#x\n`

## pseudocode

```c
__int64 __fastcall KerbCredIsoIum::CreateApReqAuthenticator(
        KerbCredIsoIum *this,
        struct _KERB_ENCRYPTION_KEY *a2,
        int a3,
        struct _KERB_INTERNAL_NAME *a4,
        struct _UNICODE_STRING *a5,
        struct KERB_ADJUSTED_TIME *a6,
        struct _KERB_ENCRYPTION_KEY *a7,
        struct PKERB_AUTHORIZATION_DATA_s *a8,
        struct KERB_CHECKSUM *a9,
        unsigned int a10,
        union _LARGE_INTEGER *a11,
        int *a12,
        struct KERB_ENCRYPTED_DATA *a13)
{
  int v14; // r14d
  int ApReqAuthenticator; // edi
  __int128 *v17; // rdx
  __int128 *v18; // rcx
  struct KERB_ENCRYPTED_DATA *v19; // r14
  const void **v20; // rax
  void *v21; // rbx
  SIZE_T v22; // r15
  HLOCAL v23; // rax
  LONGLONG v25; // [rsp+78h] [rbp-60h] BYREF
  _WORD v26[2]; // [rsp+80h] [rbp-58h] BYREF
  int v27; // [rsp+84h] [rbp-54h]
  char *v28; // [rsp+88h] [rbp-50h]
  __int128 v29; // [rsp+90h] [rbp-48h] BYREF
  __int128 v30; // [rsp+A0h] [rbp-38h] BYREF
  __int128 v31; // [rsp+B0h] [rbp-28h] BYREF
  const void **v32; // [rsp+F8h] [rbp+20h] BYREF

  v14 = (int)a2;
  v27 = 0;
  v26[1] = *((_WORD *)a4 + 1);
  v26[0] = *(_WORD *)a4;
  v28 = (char *)a4 + 8;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v25 = 0;
  if ( !a8
    || (ApReqAuthenticator = KerbClientPackAsn1Buffer(&a8, 0, (struct _KERB_ASN1_DATA *)&v29), ApReqAuthenticator >= 0) )
  {
    if ( !a9
      || (ApReqAuthenticator = KerbClientPackAsn1Buffer(a9, 9u, (struct _KERB_ASN1_DATA *)&v30), ApReqAuthenticator >= 0) )
    {
      KerbTracerT::Log(
        3,
        "TraceRpcStart",
        39,
        "%hs - Start call to LsaIso\n",
        "KerbCredIsoIum::CreateApReqAuthenticator");
      v17 = &v30;
      if ( !DWORD1(v30) )
        v17 = 0;
      v18 = &v29;
      if ( !DWORD1(v29) )
        v18 = 0;
      ApReqAuthenticator = KerbIumCreateApReqAuthenticator(
                             *((_QWORD *)this + 1),
                             v14,
                             a3,
                             (unsigned int)v26,
                             (__int64)a5,
                             (__int64)a6,
                             (__int64)a7,
                             (__int64)v18,
                             (__int64)v17,
                             a10,
                             (__int64)&v25,
                             (__int64)&v31,
                             (__int64)a12);
      KerbTracerT::Log(3, "TraceRpcEnd", 44, "%hs - End call to LsaIso\n", "KerbCredIsoIum::CreateApReqAuthenticator");
      if ( ApReqAuthenticator >= 0 )
      {
        ApReqAuthenticator = KerbClientUnpackAsn1BufferVoid((const struct _KERB_ASN1_DATA *)&v31, 7u, (void **)&v32);
        if ( ApReqAuthenticator >= 0 )
        {
          v19 = a13;
          v20 = v32;
          *(_OWORD *)a13 = *(_OWORD *)v32;
          *((_OWORD *)v19 + 1) = *((_OWORD *)v20 + 1);
          if ( KerbGlobalPackageState == 1 )
          {
            v21 = (void *)((__int64 (__fastcall *)(_QWORD))LsaFunctions->AllocateLsaHeap)(*((unsigned int *)v19 + 4));
          }
          else
          {
            v22 = *((unsigned int *)v19 + 4);
            v23 = LocalAlloc(0, v22);
            v21 = v23;
            if ( v23 )
              memset_0(v23, 0, v22);
          }
          *((_QWORD *)v19 + 3) = v21;
          if ( v21 )
          {
            memcpy_0(v21, v32[3], *((unsigned int *)v19 + 4));
            if ( a11 )
              a11->QuadPart = v25;
          }
          else
          {
            ApReqAuthenticator = -1073741801;
          }
        }
      }
    }
  }
  if ( *((_QWORD *)&v29 + 1) )
  {
    if ( KerbGlobalPackageState == 1 )
      ((void (*)(void))LsaFunctions->FreeLsaHeap)();
    else
      LocalFree(*((HLOCAL *)&v29 + 1));
  }
  if ( *((_QWORD *)&v30 + 1) )
  {
    if ( KerbGlobalPackageState == 1 )
      ((void (*)(void))LsaFunctions->FreeLsaHeap)();
    else
      LocalFree(*((HLOCAL *)&v30 + 1));
  }
  if ( *((_QWORD *)&v31 + 1) )
  {
    if ( KerbGlobalPackageState == 1 )
      ((void (*)(void))LsaFunctions->FreeLsaHeap)();
    else
      LocalFree(*((HLOCAL *)&v31 + 1));
  }
  KerbClientFreeAsn1DecodedData<KERB_ENCRYPTED_DATA>((__int64)v32);
  if ( ApReqAuthenticator < 0 )
    KerbTracerT::Log(
      1,
      "KerbCredIsoIum::CreateApReqAuthenticator",
      397,
      "%hs: CreateApReqAuthenticatorFailed. %#x\n",
      "KerbCredIsoIum::CreateApReqAuthenticator",
      ApReqAuthenticator);
  return (unsigned int)ApReqAuthenticator;
}

```

## disassembly

```asm
0x180052e50  mov     r11, rsp
0x180052e53  mov     [r11+8], rbx
0x180052e57  mov     [r11+10h], rsi
0x180052e5b  push    rdi
0x180052e5c  push    r14
0x180052e5e  push    r15
0x180052e60  sub     rsp, 0C0h
0x180052e67  mov     ebx, r8d
0x180052e6a  mov     r14, rdx
0x180052e6d  mov     r15, rcx
0x180052e70  mov     dword ptr [r11-54h], 0
0x180052e78  movzx   eax, word ptr [r9+2]
0x180052e7d  mov     [r11-56h], ax
0x180052e82  movzx   eax, word ptr [r9]
0x180052e86  mov     [r11-58h], ax
0x180052e8b  lea     rax, [r9+8]
0x180052e8f  mov     [r11-50h], rax
0x180052e93  xorps   xmm0, xmm0
0x180052e96  movups  xmmword ptr [r11-48h], xmm0
0x180052e9b  xorps   xmm1, xmm1
0x180052e9e  movups  xmmword ptr [r11-38h], xmm1
0x180052ea3  movups  xmmword ptr [r11-28h], xmm0
0x180052ea8  mov     qword ptr [r11+20h], 0
0x180052eb0  mov     qword ptr [r11-60h], 0
0x180052eb8  cmp     qword ptr [r11+40h], 0
0x180052ebd  jz      short loc_180052ED5
0x180052ebf  lea     r8, [r11-48h]
0x180052ec3  xor     edx, edx
0x180052ec5  lea     rcx, [r11+40h]
0x180052ec9  call    cs:__imp_?KerbClientPackAsn1Buffer@@YAJPEAXKPEAU_KERB_ASN1_DATA@@@Z; KerbClientPackAsn1Buffer(void *,ulong,_KERB_ASN1_DATA *)
0x180052ecf  mov     edi, eax
0x180052ed1  test    eax, eax
0x180052ed3  js      short loc_180052EFB
0x180052ed5  mov     rcx, [rsp+0D8h+arg_40]
0x180052edd  test    rcx, rcx
0x180052ee0  jz      short loc_180052F07
0x180052ee2  lea     r8, [rsp+0D8h+var_38]
0x180052eea  mov     edx, 9
0x180052eef  call    cs:__imp_?KerbClientPackAsn1Buffer@@YAJPEAXKPEAU_KERB_ASN1_DATA@@@Z; KerbClientPackAsn1Buffer(void *,ulong,_KERB_ASN1_DATA *)
0x180052ef5  mov     edi, eax
0x180052ef7  test    eax, eax
0x180052ef9  jns     short loc_180052F07
0x180052efb  lea     rsi, aKerbcredisoium_7; "KerbCredIsoIum::CreateApReqAuthenticato"...
0x180052f02  jmp     loc_180053110
0x180052f07  lea     rsi, aKerbcredisoium_7; "KerbCredIsoIum::CreateApReqAuthenticato"...
0x180052f0e  mov     [rsp+0D8h+var_B8], rsi
0x180052f13  lea     r9, aHsStartCallToL; "%hs - Start call to LsaIso\n"
0x180052f1a  mov     r8d, 27h ; '''
0x180052f20  lea     rdx, aTracerpcstart; "TraceRpcStart"
0x180052f27  mov     ecx, 3
0x180052f2c  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180052f31  nop
0x180052f32  lea     rdx, [rsp+0D8h+var_38]
0x180052f3a  xor     eax, eax
0x180052f3c  cmp     [rsp+0D8h+var_34], eax
0x180052f43  cmovbe  rdx, rax
0x180052f47  lea     rcx, [rsp+0D8h+var_48]
0x180052f4f  cmp     [rsp+0D8h+var_44], eax
0x180052f56  cmovbe  rcx, rax
0x180052f5a  mov     rax, [rsp+0D8h+arg_58]
0x180052f62  mov     [rsp+0D8h+var_78], rax
0x180052f67  lea     rax, [rsp+0D8h+var_28]
0x180052f6f  mov     [rsp+0D8h+var_80], rax
0x180052f74  lea     rax, [rsp+0D8h+var_60]
0x180052f79  mov     [rsp+0D8h+var_88], rax
0x180052f7e  mov     eax, [rsp+0D8h+arg_48]
0x180052f85  mov     [rsp+0D8h+var_90], eax
0x180052f89  mov     [rsp+0D8h+var_98], rdx
0x180052f8e  mov     [rsp+0D8h+var_A0], rcx
0x180052f93  mov     rax, [rsp+0D8h+arg_30]
0x180052f9b  mov     [rsp+0D8h+var_A8], rax
0x180052fa0  mov     rax, [rsp+0D8h+arg_28]
0x180052fa8  mov     [rsp+0D8h+var_B0], rax
0x180052fad  mov     rax, [rsp+0D8h+arg_20]
0x180052fb5  mov     [rsp+0D8h+var_B8], rax
0x180052fba  lea     r9, [rsp+0D8h+var_58]
0x180052fc2  mov     r8d, ebx
0x180052fc5  mov     rdx, r14
0x180052fc8  mov     rcx, [r15+8]
0x180052fcc  call    KerbIumCreateApReqAuthenticator
0x180052fd1  mov     edi, eax
0x180052fd3  mov     [rsp+0D8h+var_68], eax
0x180052fd7  jmp     short loc_18005301E
0x180052fd9  mov     ebx, eax
0x180052fdb  mov     ecx, eax; Status
0x180052fdd  call    cs:__imp_I_RpcMapWin32Status
0x180052fe3  mov     edi, eax
0x180052fe5  mov     [rsp+0D8h+var_68], eax
0x180052fe9  mov     dword ptr [rsp+0D8h+var_B0], ebx
0x180052fed  lea     rax, aKerbcredisoium_7; "KerbCredIsoIum::CreateApReqAuthenticato"...
0x180052ff4  mov     [rsp+0D8h+var_B8], rax
0x180052ff9  lea     r9, aHsRpcErrorD; "%hs: RPC Error: %d"
0x180053000  mov     r8d, 22h ; '"'
0x180053006  lea     rdx, aLogrpcerror; "LogRpcError"
0x18005300d  mov     ecx, 1
0x180053012  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180053017  lea     rsi, aKerbcredisoium_7; "KerbCredIsoIum::CreateApReqAuthenticato"...
0x18005301e  mov     [rsp+0D8h+var_B8], rsi
0x180053023  lea     r9, aHsEndCallToLsa; "%hs - End call to LsaIso\n"
0x18005302a  mov     r8d, 2Ch ; ','
0x180053030  lea     rdx, aTracerpcend; "TraceRpcEnd"
0x180053037  mov     ecx, 3
0x18005303c  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180053041  test    edi, edi
0x180053043  js      loc_180053110
0x180053049  lea     r8, [rsp+0D8h+arg_18]
0x180053051  mov     edx, 7
0x180053056  lea     rcx, [rsp+0D8h+var_28]
0x18005305e  call    cs:__imp_?KerbClientUnpackAsn1BufferVoid@@YAJAEBU_KERB_ASN1_DATA@@KPEAPEAX@Z; KerbClientUnpackAsn1BufferVoid(_KERB_ASN1_DATA const &,ulong,void * *)
0x180053064  mov     edi, eax
0x180053066  test    eax, eax
0x180053068  js      loc_180053110
0x18005306e  mov     r14, [rsp+0D8h+arg_60]
0x180053076  mov     rax, [rsp+0D8h+arg_18]
0x18005307e  movups  xmm0, xmmword ptr [rax]
0x180053081  movups  xmmword ptr [r14], xmm0
0x180053085  movups  xmm1, xmmword ptr [rax+10h]
0x180053089  movups  xmmword ptr [r14+10h], xmm1
0x18005308e  mov     ecx, [r14+10h]
0x180053092  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1; KerberosState KerbGlobalPackageState
0x180053099  jnz     short loc_1800530B0
0x18005309b  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x1800530a2  mov     rax, [rax+28h]
0x1800530a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800530ab  mov     rbx, rax
0x1800530ae  jmp     short loc_1800530D3
0x1800530b0  mov     r15, rcx
0x1800530b3  mov     rdx, rcx; uBytes
0x1800530b6  xor     ecx, ecx; uFlags
0x1800530b8  call    cs:__imp_LocalAlloc
0x1800530be  mov     rbx, rax
0x1800530c1  test    rax, rax
0x1800530c4  jz      short loc_1800530D3
0x1800530c6  mov     r8, r15; Size
0x1800530c9  xor     edx, edx; Val
0x1800530cb  mov     rcx, rax; void *
0x1800530ce  call    memset_0
0x1800530d3  mov     [r14+18h], rbx
0x1800530d7  test    rbx, rbx
0x1800530da  jnz     short loc_1800530E3
0x1800530dc  mov     edi, 0C0000017h
0x1800530e1  jmp     short loc_180053110
0x1800530e3  mov     r8d, [r14+10h]; Size
0x1800530e7  mov     rdx, [rsp+0D8h+arg_18]
0x1800530ef  mov     rdx, [rdx+18h]; Src
0x1800530f3  mov     rcx, rbx; void *
0x1800530f6  call    memcpy_0
0x1800530fb  mov     rcx, [rsp+0D8h+arg_50]
0x180053103  test    rcx, rcx
0x180053106  jz      short loc_180053110
0x180053108  mov     rax, [rsp+0D8h+var_60]
0x18005310d  mov     [rcx], rax
0x180053110  mov     rcx, [rsp+0D8h+hMem]; hMem
0x180053118  test    rcx, rcx
0x18005311b  jz      short loc_18005313E
0x18005311d  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1; KerberosState KerbGlobalPackageState
0x180053124  jnz     short loc_180053138
0x180053126  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x18005312d  mov     rax, [rax+30h]
0x180053131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053136  jmp     short loc_18005313E
0x180053138  call    cs:__imp_LocalFree
0x18005313e  mov     rcx, [rsp+0D8h+var_30]; hMem
0x180053146  test    rcx, rcx
0x180053149  jz      short loc_18005316C
0x18005314b  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1; KerberosState KerbGlobalPackageState
0x180053152  jnz     short loc_180053166
0x180053154  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x18005315b  mov     rax, [rax+30h]
0x18005315f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053164  jmp     short loc_18005316C
0x180053166  call    cs:__imp_LocalFree
0x18005316c  mov     rcx, [rsp+0D8h+var_20]; hMem
0x180053174  test    rcx, rcx
0x180053177  jz      short loc_18005319A
0x180053179  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1; KerberosState KerbGlobalPackageState
0x180053180  jnz     short loc_180053194
0x180053182  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x180053189  mov     rax, [rax+30h]
0x18005318d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053192  jmp     short loc_18005319A
0x180053194  call    cs:__imp_LocalFree
0x18005319a  mov     rcx, [rsp+0D8h+arg_18]
0x1800531a2  call    ??$KerbClientFreeAsn1DecodedData@UKERB_ENCRYPTED_DATA@@@@YAXPEAUKERB_ENCRYPTED_DATA@@@Z; KerbClientFreeAsn1DecodedData<KERB_ENCRYPTED_DATA>(KERB_ENCRYPTED_DATA *)
0x1800531a7  test    edi, edi
0x1800531a9  jns     short loc_1800531CE
0x1800531ab  mov     dword ptr [rsp+0D8h+var_B0], edi
0x1800531af  mov     [rsp+0D8h+var_B8], rsi
0x1800531b4  lea     r9, aHsCreateapreqa; "%hs: CreateApReqAuthenticatorFailed. %#"...
0x1800531bb  mov     r8d, 18Dh
0x1800531c1  mov     rdx, rsi
0x1800531c4  mov     ecx, 1
0x1800531c9  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800531ce  mov     eax, edi
0x1800531d0  lea     r11, [rsp+0D8h+var_18]
0x1800531d8  mov     rbx, [r11+20h]
0x1800531dc  mov     rsi, [r11+28h]
0x1800531e0  mov     rsp, r11
0x1800531e3  pop     r15
0x1800531e5  pop     r14
0x1800531e7  pop     rdi
0x1800531e8  retn
0x1800f2cc0  push    rbp
0x1800f2cc2  sub     rsp, 70h
0x1800f2cc6  mov     rbp, rdx
0x1800f2cc9  mov     rcx, [rcx]
0x1800f2ccc  mov     ecx, [rcx]; ExceptionCode
0x1800f2cce  call    cs:__imp_RpcExceptionFilter
0x1800f2cd4  nop
0x1800f2cd5  add     rsp, 70h
0x1800f2cd9  pop     rbp
0x1800f2cda  retn
```
