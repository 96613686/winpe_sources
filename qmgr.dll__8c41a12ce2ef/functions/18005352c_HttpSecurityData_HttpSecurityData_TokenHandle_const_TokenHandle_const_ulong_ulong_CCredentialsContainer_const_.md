# HttpSecurityData::HttpSecurityData(TokenHandle const &,TokenHandle const &,ulong,ulong,CCredentialsContainer const &,CClientCertificate const *)

- ea: `0x18005352c`
- end: `0x18005391d`
- name: `??0HttpSecurityData@@QEAA@AEBVTokenHandle@@0KKAEBVCCredentialsContainer@@PEBVCClientCertificate@@@Z`
- size: `1009`
- prototype: `HttpSecurityData *__fastcall(HttpSecurityData *__hidden this, const struct TokenHandle *, const struct TokenHandle *, unsigned int, unsigned int, const struct CCredentialsContainer *, const struct CClientCertificate *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180051ea0`

## callees

- `0x180006640`
- `0x180008b70`
- `0x18000db20`
- `0x18005352c`
- `0x180053924`
- `0x180057cac`
- `0x180065da0`
- `0x18009d024`
- `0x18009e9c8`
- `0x1800a3420`
- `0x1800c0a68`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800535a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800535b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800535bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053656`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053660`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005366a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005374c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800535a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800535b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800535bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053656`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053660`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005366a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005374c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180053742`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180053742`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005359d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005364c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005359d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005364c`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
HttpSecurityData *__fastcall HttpSecurityData::HttpSecurityData(
        HttpSecurityData *this,
        HANDLE **a2,
        HANDLE **a3,
        char a4,
        unsigned int a5,
        const struct CCredentialsContainer *a6,
        const struct CClientCertificate *a7)
{
  unsigned int LastError; // ecx
  unsigned int v12; // ecx
  struct _LUID v13; // rax
  _DWORD *v14; // rax
  signed int v15; // eax
  unsigned int v16; // ecx
  unsigned int v17; // r9d
  __int64 v18; // rax
  CEncryptedCredentials *v19; // rsi
  unsigned int updated; // eax
  __int64 v21; // rax
  EVENT_LOG *v22; // rcx
  __int64 v23; // rdx
  DWORD ReturnLength; // [rsp+30h] [rbp-91h] BYREF
  __int64 v26; // [rsp+38h] [rbp-89h] BYREF
  void **pExceptionObject; // [rsp+40h] [rbp-81h] BYREF
  __int128 v28; // [rsp+48h] [rbp-79h]
  int v29; // [rsp+58h] [rbp-69h]
  int v30; // [rsp+5Ch] [rbp-65h]
  int v31; // [rsp+60h] [rbp-61h]
  __int128 TokenInformation; // [rsp+A0h] [rbp-21h] BYREF
  __int128 v33; // [rsp+B0h] [rbp-11h]
  __int128 v34; // [rsp+C0h] [rbp-1h]
  void *v35; // [rsp+D0h] [rbp+Fh]

  ReturnLength = 0;
  TokenInformation = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  if ( !GetTokenInformation(**a2, TokenStatistics, &TokenInformation, 0x38u, &ReturnLength) )
  {
    if ( (int)GetLastError() > 0 )
      LastError = (unsigned __int16)GetLastError() | 0x80070000;
    else
      LastError = GetLastError();
    v28 = 0;
    pExceptionObject = &ComError::`vftable';
    v29 = LastError;
    v30 = 783;
    v31 = 1;
    throw (ComError *)&pExceptionObject;
  }
  *(_QWORD *)this = v35;
  if ( (a4 & 2) != 0 )
  {
    ReturnLength = 0;
    TokenInformation = 0;
    v33 = 0;
    v34 = 0;
    v35 = 0;
    if ( !GetTokenInformation(**a3, TokenStatistics, &TokenInformation, 0x38u, &ReturnLength) )
    {
      if ( (int)GetLastError() > 0 )
        v12 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v12 = GetLastError();
      v28 = 0;
      pExceptionObject = &ComError::`vftable';
      v29 = v12;
      v30 = 783;
      v31 = 1;
      throw (ComError *)&pExceptionObject;
    }
    v13 = (struct _LUID)v35;
  }
  else
  {
    v13 = g_nullLuid;
  }
  *((struct _LUID *)this + 1) = v13;
  *((_DWORD *)this + 4) = a5;
  *(_OWORD *)((char *)this + 24) = 0;
  *((_DWORD *)this + 10) = 0;
  *((_BYTE *)this + 44) = CCredentialsContainer::IsPassportAuthSet(a6);
  CSaveThreadToken::CSaveThreadToken((CSaveThreadToken *)&TokenInformation);
  BYTE8(TokenInformation) = 0;
  *(_QWORD *)&v33 = *a2;
  _InterlockedAdd((volatile signed __int32 *)(v33 + 8), 1u);
  *((_QWORD *)&v33 + 1) = 0;
  v14 = operator new(4u);
  if ( v14 )
    *v14 = 1;
  v34 = (unsigned __int64)v14;
  _InterlockedAdd(&dword_180145058, 1u);
  v35 = &GenericStringHandle<unsigned short>::s_EmptyString;
  if ( !BYTE8(TokenInformation) )
  {
    if ( !ImpersonateLoggedOnUser(*(HANDLE *)v33) )
    {
      v15 = GetLastError();
      v16 = v15;
      if ( v15 > 0 )
        v16 = (unsigned __int16)v15 | 0x80070000;
      v28 = 0;
      pExceptionObject = &ComError::`vftable';
      v29 = v16;
      v30 = 0;
      v31 = 1;
      throw (ComError *)&pExceptionObject;
    }
    BYTE8(TokenInformation) = 1;
  }
  v17 = -1;
  v18 = **(_QWORD **)a6;
  v26 = v18;
  while ( v18 != *(_QWORD *)a6 )
  {
    ReturnLength = *(_DWORD *)(v18 + 32);
    v19 = *(CEncryptedCredentials **)(v18 + 40);
    updated = UpdateCRC32((const unsigned __int8 *)&ReturnLength, 4, v17);
    if ( v19 )
      CEncryptedCredentials::UpdateCrc32(v19, updated);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,CEncryptedCredentials *>>>,std::_Iterator_base0>::operator++(&v26);
    v18 = v26;
  }
  *((_DWORD *)this + 5) = ~v17;
  CNestedImpersonation::~CNestedImpersonation((CNestedImpersonation *)&TokenInformation);
  if ( !a7 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
      return this;
    v23 = 12;
LABEL_41:
    WPP_SF_(*((_QWORD *)v22 + 2), v23, &WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids);
    return this;
  }
  if ( !*((_DWORD *)a7 + 10) )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
      return this;
    v23 = 10;
    goto LABEL_41;
  }
  if ( *((_DWORD *)a7 + 6) != 20 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids, 1359);
    v28 = 0;
    pExceptionObject = &ComError::`vftable';
    v29 = -2147023537;
    v30 = 132;
    v31 = 1;
    throw (ComError *)&pExceptionObject;
  }
  v21 = *((_QWORD *)a7 + 2);
  *(_OWORD *)((char *)this + 24) = *(_OWORD *)v21;
  *((_DWORD *)this + 10) = *(_DWORD *)(v21 + 16);
  return this;
}

```

## disassembly

```asm
0x18005352c  mov     [rsp-8+arg_18], rbx
0x180053531  push    rbp
0x180053532  push    rsi
0x180053533  push    rdi
0x180053534  push    r14
0x180053536  push    r15
0x180053538  lea     rbp, [rsp-1Fh]
0x18005353d  sub     rsp, 0E0h
0x180053544  mov     rax, cs:__security_cookie
0x18005354b  xor     rax, rsp
0x18005354e  mov     [rbp+3Fh+var_28], rax
0x180053552  mov     ebx, r9d
0x180053555  mov     rsi, r8
0x180053558  mov     r15, rdx
0x18005355b  mov     rdi, rcx
0x18005355e  mov     r14, [rbp+3Fh+arg_28]
0x180053562  mov     [rsp+100h+var_D0], 0
0x18005356a  xorps   xmm0, xmm0
0x18005356d  xor     eax, eax
0x18005356f  movups  [rbp+3Fh+TokenInformation], xmm0
0x180053573  movups  [rbp+3Fh+var_50], xmm0
0x180053577  movups  [rbp+3Fh+var_40], xmm0
0x18005357b  mov     [rbp+3Fh+var_30], rax
0x18005357f  mov     rcx, [rdx]
0x180053582  lea     rax, [rsp+100h+var_D0]
0x180053587  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x18005358c  mov     r9d, 38h ; '8'; TokenInformationLength
0x180053592  lea     r8, [rbp+3Fh+TokenInformation]; TokenInformation
0x180053596  lea     edx, [r9-2Eh]; TokenInformationClass
0x18005359a  mov     rcx, [rcx]; TokenHandle
0x18005359d  call    cs:__imp_GetTokenInformation
0x1800535a3  test    eax, eax
0x1800535a5  jnz     short loc_180053601
0x1800535a7  call    cs:__imp_GetLastError
0x1800535ad  test    eax, eax
0x1800535af  jg      short loc_1800535BB
0x1800535b1  call    cs:__imp_GetLastError
0x1800535b7  mov     ecx, eax
0x1800535b9  jmp     short loc_1800535CA
0x1800535bb  call    cs:__imp_GetLastError
0x1800535c1  movzx   ecx, ax
0x1800535c4  or      ecx, 80070000h
0x1800535ca  xorps   xmm0, xmm0
0x1800535cd  movups  [rbp+3Fh+var_B8], xmm0
0x1800535d1  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800535d8  mov     [rsp+100h+pExceptionObject], rax
0x1800535dd  mov     [rbp+3Fh+var_A8], ecx
0x1800535e0  mov     [rbp+3Fh+var_A4], 30Fh
0x1800535e7  mov     ebx, 1
0x1800535ec  mov     [rbp+3Fh+var_A0], ebx
0x1800535ef  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800535f6  lea     rcx, [rsp+100h+pExceptionObject]; pExceptionObject
0x1800535fb  call    _CxxThrowException_0
0x180053601  mov     rax, [rbp+3Fh+var_30]
0x180053605  mov     [rdi], rax
0x180053608  test    bl, 2
0x18005360b  jz      loc_1800536B6
0x180053611  mov     [rsp+100h+var_D0], 0
0x180053619  xorps   xmm0, xmm0
0x18005361c  xor     eax, eax
0x18005361e  movups  [rbp+3Fh+TokenInformation], xmm0
0x180053622  movups  [rbp+3Fh+var_50], xmm0
0x180053626  movups  [rbp+3Fh+var_40], xmm0
0x18005362a  mov     [rbp+3Fh+var_30], rax
0x18005362e  mov     rcx, [rsi]
0x180053631  lea     rax, [rsp+100h+var_D0]
0x180053636  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x18005363b  mov     r9d, 38h ; '8'; TokenInformationLength
0x180053641  lea     r8, [rbp+3Fh+TokenInformation]; TokenInformation
0x180053645  lea     edx, [r9-2Eh]; TokenInformationClass
0x180053649  mov     rcx, [rcx]; TokenHandle
0x18005364c  call    cs:__imp_GetTokenInformation
0x180053652  test    eax, eax
0x180053654  jnz     short loc_1800536B0
0x180053656  call    cs:__imp_GetLastError
0x18005365c  test    eax, eax
0x18005365e  jg      short loc_18005366A
0x180053660  call    cs:__imp_GetLastError
0x180053666  mov     ecx, eax
0x180053668  jmp     short loc_180053679
0x18005366a  call    cs:__imp_GetLastError
0x180053670  movzx   ecx, ax
0x180053673  or      ecx, 80070000h
0x180053679  xorps   xmm0, xmm0
0x18005367c  movups  [rbp+3Fh+var_B8], xmm0
0x180053680  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180053687  mov     [rsp+100h+pExceptionObject], rax
0x18005368c  mov     [rbp+3Fh+var_A8], ecx
0x18005368f  mov     [rbp+3Fh+var_A4], 30Fh
0x180053696  mov     ebx, 1
0x18005369b  mov     [rbp+3Fh+var_A0], ebx
0x18005369e  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800536a5  lea     rcx, [rsp+100h+pExceptionObject]; pExceptionObject
0x1800536aa  call    _CxxThrowException_0
0x1800536b0  mov     rax, [rbp+3Fh+var_30]
0x1800536b4  jmp     short loc_1800536BD
0x1800536b6  mov     rax, cs:?g_nullLuid@@3U_LUID@@B; _LUID const g_nullLuid
0x1800536bd  mov     [rdi+8], rax
0x1800536c1  mov     eax, [rbp+3Fh+arg_20]
0x1800536c4  mov     [rdi+10h], eax
0x1800536c7  xorps   xmm0, xmm0
0x1800536ca  xor     eax, eax
0x1800536cc  movups  xmmword ptr [rdi+18h], xmm0
0x1800536d0  mov     [rdi+28h], eax
0x1800536d3  mov     rcx, r14; this
0x1800536d6  call    ?IsPassportAuthSet@CCredentialsContainer@@QEBA_NXZ; CCredentialsContainer::IsPassportAuthSet(void)
0x1800536db  mov     [rdi+2Ch], al
0x1800536de  lea     rcx, [rbp+3Fh+TokenInformation]; this
0x1800536e2  call    ??0CSaveThreadToken@@QEAA@XZ; CSaveThreadToken::CSaveThreadToken(void)
0x1800536e7  nop
0x1800536e8  mov     byte ptr [rbp+3Fh+TokenInformation+8], 0
0x1800536ec  mov     rax, [r15]
0x1800536ef  mov     qword ptr [rbp+3Fh+var_50], rax
0x1800536f3  mov     ebx, 1
0x1800536f8  lock add [rax+8], ebx
0x1800536fc  mov     qword ptr [rbp+3Fh+var_50+8], 0
0x180053704  lea     r15d, [rbx+3]
0x180053708  mov     ecx, r15d; dwBytes
0x18005370b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180053710  test    rax, rax
0x180053713  jz      short loc_180053717
0x180053715  mov     [rax], ebx
0x180053717  mov     qword ptr [rbp+3Fh+var_40], rax
0x18005371b  mov     qword ptr [rbp+3Fh+var_40+8], 0
0x180053723  lock add cs:dword_180145058, ebx
0x18005372a  lea     rax, ?s_EmptyString@?$GenericStringHandle@G@@0UStringData@1@A; GenericStringHandle<ushort>::StringData GenericStringHandle<ushort>::s_EmptyString
0x180053731  mov     [rbp+3Fh+var_30], rax
0x180053735  cmp     byte ptr [rbp+3Fh+TokenInformation+8], 0
0x180053739  jnz     short loc_180053796
0x18005373b  mov     rcx, qword ptr [rbp+3Fh+var_50]
0x18005373f  mov     rcx, [rcx]; hToken
0x180053742  call    cs:__imp_ImpersonateLoggedOnUser
0x180053748  test    eax, eax
0x18005374a  jnz     short loc_180053793
0x18005374c  call    cs:__imp_GetLastError
0x180053752  mov     ecx, eax
0x180053754  test    eax, eax
0x180053756  jle     short loc_180053761
0x180053758  movzx   ecx, ax
0x18005375b  or      ecx, 80070000h
0x180053761  xorps   xmm0, xmm0
0x180053764  movups  [rbp+3Fh+var_B8], xmm0
0x180053768  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18005376f  mov     [rsp+100h+pExceptionObject], rax
0x180053774  mov     [rbp+3Fh+var_A8], ecx
0x180053777  mov     [rbp+3Fh+var_A4], 0
0x18005377e  mov     [rbp+3Fh+var_A0], ebx
0x180053781  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180053788  lea     rcx, [rsp+100h+pExceptionObject]; pExceptionObject
0x18005378d  call    _CxxThrowException_0
0x180053793  mov     byte ptr [rbp+3Fh+TokenInformation+8], bl
0x180053796  or      r9d, 0FFFFFFFFh
0x18005379a  mov     rax, [r14]
0x18005379d  mov     rax, [rax]
0x1800537a0  mov     [rsp+100h+var_C8], rax
0x1800537a5  cmp     rax, [r14]
0x1800537a8  jz      short loc_1800537EB
0x1800537aa  mov     ecx, [rax+20h]
0x1800537ad  mov     [rsp+100h+var_D0], ecx
0x1800537b1  mov     rsi, [rax+28h]
0x1800537b5  mov     r8d, r9d; unsigned int
0x1800537b8  mov     edx, r15d; int
0x1800537bb  lea     rcx, [rsp+100h+var_D0]; unsigned __int8 *
0x1800537c0  call    ?UpdateCRC32@@YAKPEBEHK@Z; UpdateCRC32(uchar const *,int,ulong)
0x1800537c5  mov     r9d, eax
0x1800537c8  test    rsi, rsi
0x1800537cb  jz      short loc_1800537DA
0x1800537cd  mov     edx, eax; unsigned int
0x1800537cf  mov     rcx, rsi; this
0x1800537d2  call    ?UpdateCrc32@CEncryptedCredentials@@QEBAKK@Z; CEncryptedCredentials::UpdateCrc32(ulong)
0x1800537d7  mov     r9d, eax
0x1800537da  lea     rcx, [rsp+100h+var_C8]
0x1800537df  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKPEAVCEncryptedCredentials@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,CEncryptedCredentials *>>>,std::_Iterator_base0>::operator++(void)
0x1800537e4  mov     rax, [rsp+100h+var_C8]
0x1800537e9  jmp     short loc_1800537A5
0x1800537eb  not     r9d
0x1800537ee  mov     [rdi+14h], r9d
0x1800537f2  lea     rcx, [rbp+3Fh+TokenInformation]; this
0x1800537f6  call    ??1CNestedImpersonation@@QEAA@XZ; CNestedImpersonation::~CNestedImpersonation(void)
0x1800537fb  mov     rax, [rbp+3Fh+arg_30]
0x1800537ff  test    rax, rax
0x180053802  jz      loc_1800538C6
0x180053808  cmp     dword ptr [rax+28h], 0
0x18005380c  jz      loc_1800538A3
0x180053812  cmp     dword ptr [rax+18h], 14h
0x180053816  jz      short loc_180053890
0x180053818  lea     rax, WPP_GLOBAL_Control
0x18005381f  mov     rcx, cs:WPP_GLOBAL_Control
0x180053826  cmp     rcx, rax
0x180053829  jz      short loc_18005384C
0x18005382b  test    [rcx+1Ch], r15b
0x18005382f  jz      short loc_18005384C
0x180053831  mov     edx, 0Bh
0x180053836  mov     r9d, 54Fh
0x18005383c  lea     r8, WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids
0x180053843  mov     rcx, [rcx+10h]
0x180053847  call    WPP_SF_d
0x18005384c  xorps   xmm0, xmm0
0x18005384f  movups  [rbp+3Fh+var_B8], xmm0
0x180053853  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18005385a  mov     [rsp+100h+pExceptionObject], rax
0x18005385f  xor     eax, eax
0x180053861  neg     al
0x180053863  sbb     ecx, ecx
0x180053865  and     ecx, 7FF90000h
0x18005386b  add     ecx, 8007054Fh
0x180053871  mov     [rbp+3Fh+var_A8], ecx
0x180053874  mov     [rbp+3Fh+var_A4], 84h
0x18005387b  mov     [rbp+3Fh+var_A0], ebx
0x18005387e  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180053885  lea     rcx, [rsp+100h+pExceptionObject]; pExceptionObject
0x18005388a  call    _CxxThrowException_0
0x180053890  mov     rax, [rax+10h]
0x180053894  movups  xmm0, xmmword ptr [rax]
0x180053897  movups  xmmword ptr [rdi+18h], xmm0
0x18005389b  mov     eax, [rax+10h]
0x18005389e  mov     [rdi+28h], eax
0x1800538a1  jmp     short loc_1800538F7
0x1800538a3  lea     rax, WPP_GLOBAL_Control
0x1800538aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800538b1  cmp     rcx, rax
0x1800538b4  jz      short loc_1800538F7
0x1800538b6  test    dword ptr [rcx+1Ch], 800h
0x1800538bd  jz      short loc_1800538F7
0x1800538bf  mov     edx, 0Ah
0x1800538c4  jmp     short loc_1800538E7
0x1800538c6  lea     rax, WPP_GLOBAL_Control
0x1800538cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800538d4  cmp     rcx, rax
0x1800538d7  jz      short loc_1800538F7
0x1800538d9  test    dword ptr [rcx+1Ch], 800h
0x1800538e0  jz      short loc_1800538F7
0x1800538e2  mov     edx, 0Ch
0x1800538e7  lea     r8, WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids
0x1800538ee  mov     rcx, [rcx+10h]
0x1800538f2  call    WPP_SF_
0x1800538f7  mov     rax, rdi
0x1800538fa  mov     rcx, [rbp+3Fh+var_28]
0x1800538fe  xor     rcx, rsp; StackCookie
0x180053901  call    __security_check_cookie
0x180053906  mov     rbx, [rsp+100h+arg_18]
0x18005390e  add     rsp, 0E0h
0x180053915  pop     r15
0x180053917  pop     r14
0x180053919  pop     rdi
0x18005391a  pop     rsi
0x18005391b  pop     rbp
0x18005391c  retn
```
