# sqlencrypt::AzureKeyVault::VerifyCMKMetadata(CEKeystoreContext *,void (*)(CEKeystoreContext *,ushort const *,...),ushort const *,uchar *,ushort)

- ea: `0x10046edf0`
- end: `0x10046f445`
- name: `?VerifyCMKMetadata@AzureKeyVault@sqlencrypt@@SAHPEAUCEKeystoreContext@@P6AX0PEBGZZ1PEAEG@Z`
- size: `1621`
- prototype: `__int64 __usercall@<rax>(struct CEKeystoreContext *@<rcx>, void (*)(struct CEKeystoreContext *, const unsigned __int16 *, ...)@<rdx>, const unsigned __int16 *@<r8>, unsigned __int8 *@<r9>, unsigned __int16)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1004245f0`
- `0x100430674`
- `0x1004306f0`
- `0x1004307a0`
- `0x100430824`
- `0x100431464`
- `0x1004385b0`
- `0x10046edf0`
- `0x1004700b4`
- `0x100470b78`
- `0x100471184`
- `0x100471648`
- `0x1004717c4`
- `0x10047dd74`
- `0x100483714`
- `0x100486308`
- `0x1005480f8`
- `0x100548170`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10046f020`
- `KERNEL32!GetLastError` at `0x10046f0b0`
- `KERNEL32!GetLastError` at `0x10046f020`
- `KERNEL32!GetLastError` at `0x10046f0b0`
- `ADVAPI32!CryptDestroyHash` at `0x10046f0cf`
- `ADVAPI32!CryptDestroyHash` at `0x10046f0ff`
- `ADVAPI32!CryptDestroyHash` at `0x10046f0cf`
- `ADVAPI32!CryptDestroyHash` at `0x10046f0ff`
- `ADVAPI32!CryptHashData` at `0x10046f05f`
- `ADVAPI32!CryptHashData` at `0x10046f05f`
- `ADVAPI32!CryptCreateHash` at `0x10046efcf`
- `ADVAPI32!CryptCreateHash` at `0x10046efcf`
- `ADVAPI32!CryptGetHashParam` at `0x10046f0f4`
- `ADVAPI32!CryptGetHashParam` at `0x10046f0f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall sqlencrypt::AzureKeyVault::VerifyCMKMetadata(
        struct CEKeystoreContext *a1,
        void (*a2)(struct CEKeystoreContext *, const unsigned __int16 *, ...),
        const unsigned __int16 *a3,
        unsigned __int8 *a4,
        unsigned __int16 a5)
{
  unsigned int v9; // edi
  const unsigned __int16 *v10; // rax
  __int64 i; // r8
  __int64 v12; // r8
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // r9
  unsigned __int64 v15; // rdx
  BYTE *v16; // r8
  BYTE **v17; // rax
  BYTE **v18; // rax
  BYTE **v19; // rax
  HCRYPTPROV WinCryptProvider; // rax
  wchar_t *v21; // r9
  __int64 v22; // r8
  DWORD LastError; // eax
  const BYTE *v24; // rdx
  DWORD v25; // eax
  unsigned int *Config; // rax
  __int64 v27; // r8
  __int64 v28; // rax
  int *v29; // r9
  int v30; // ebx
  _QWORD *v31; // rsi
  char *v32; // r12
  size_t v33; // r8
  const void *j; // rcx
  const void *v35; // rbx
  char *v36; // rax
  char *v37; // rbx
  _QWORD *v38; // r8
  unsigned int v39; // edx
  DWORD pdwDataLen; // [rsp+44h] [rbp-BCh] BYREF
  HCRYPTHASH hHash; // [rsp+48h] [rbp-B8h] BYREF
  int v43[4]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v44; // [rsp+60h] [rbp-A0h]
  BYTE *pbData[2]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v46; // [rsp+78h] [rbp-88h]
  unsigned __int64 v47; // [rsp+80h] [rbp-80h]
  _QWORD v48[3]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 v49; // [rsp+A0h] [rbp-60h]
  _BYTE v50[16]; // [rsp+A8h] [rbp-58h] BYREF
  __m128i v51; // [rsp+B8h] [rbp-48h]
  _QWORD v52[2]; // [rsp+C8h] [rbp-38h] BYREF
  __m128i v53; // [rsp+D8h] [rbp-28h]
  int v54[4]; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v55; // [rsp+F8h] [rbp-8h]
  _BYTE Src[16]; // [rsp+108h] [rbp+8h] BYREF
  __m128i si128; // [rsp+118h] [rbp+18h]
  _BYTE v58[16]; // [rsp+128h] [rbp+28h] BYREF
  __int128 v59; // [rsp+138h] [rbp+38h]
  _BYTE v60[32]; // [rsp+148h] [rbp+48h] BYREF
  BYTE v61[32]; // [rsp+168h] [rbp+68h] BYREF
  BYTE v62[32]; // [rsp+188h] [rbp+88h] BYREF

  v44 = -2;
  v9 = 0;
  v48[2] = 0;
  v49 = 7;
  LOWORD(v48[0]) = 0;
  v10 = a3;
  for ( i = 0; *v10; ++v10 )
    ++i;
  std::basic_string<char16_t>::assign(v48, a3, i);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  Src[0] = 0;
  std::string::_Construct<char16_t const *>(Src);
  v46 = 0;
  v47 = 7;
  LOWORD(pbData[0]) = 0;
  std::wstring::assign(pbData);
  v12 = -1;
  do
    ++v12;
  while ( a3[v12] );
  std::wstring::append(pbData);
  std::wstring::append(pbData);
  v13 = 0;
  v14 = v46;
  if ( v46 )
  {
    v15 = v47;
    v16 = pbData[0];
    do
    {
      v17 = pbData;
      if ( v15 >= 8 )
        v17 = (BYTE **)v16;
      if ( *((_WORD *)v17 + v13) >= 0x41u )
      {
        v18 = pbData;
        if ( v15 >= 8 )
          v18 = (BYTE **)v16;
        if ( *((_WORD *)v18 + v13) <= 0x5Au )
        {
          v19 = pbData;
          if ( v15 >= 8 )
            v19 = (BYTE **)v16;
          *((_WORD *)v19 + v13) |= 0x20u;
          v15 = v47;
          v14 = v46;
          v16 = pbData[0];
        }
      }
      ++v13;
    }
    while ( v13 < v14 );
  }
  WinCryptProvider = sqlencrypt::SqlSecurityUtility::GetWinCryptProvider();
  if ( !WinCryptProvider )
  {
    if ( (bidGblFlags & 2) == 0 || !off_1005E6D20[0] || bidID == -1 )
      goto LABEL_28;
    v21 = off_1005E6D20[0];
    v22 = 530432;
LABEL_27:
    ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0[0])(bidID, 0, v22, v21, 0);
LABEL_28:
    LastError = GetLastError();
    a2(a1, (const unsigned __int16 *)41328, LastError);
    goto LABEL_60;
  }
  pdwDataLen = 32;
  if ( !CryptCreateHash(WinCryptProvider, 0x800Cu, 0, 0, &hHash) )
  {
    if ( (bidGblFlags & 2) == 0 || !off_1005E6D28[0] || bidID == -1 )
      goto LABEL_28;
    v21 = off_1005E6D28[0];
    v22 = 538624;
    goto LABEL_27;
  }
  v24 = (const BYTE *)pbData;
  if ( v47 >= 8 )
    v24 = pbData[0];
  if ( CryptHashData(hHash, v24, 2 * v46, 0) )
  {
    CryptGetHashParam(hHash, 2u, v62, &pdwDataLen, 0);
    CryptDestroyHash(hHash);
    Config = (unsigned int *)sqlencrypt::AzureKeyVault::GetConfig(a1);
    aadauth::AzureADAuth::AzureADAuth((aadauth::AzureADAuth *)v43, Config[34], Config[35], Config[36]);
    v51 = _mm_load_si128((const __m128i *)&_xmm);
    v50[0] = 0;
    _mm_lfence();
    LOBYTE(v27) = 0;
    std::string::_Reallocate_for<_lambda_66f57f934f28d61049862f64df852ff0_,char const *>(
      v50,
      25,
      v27,
      "{\"alg\":\"RS256\",\"digest\":\"");
    sqlencrypt::utils::Base64URLencode(v60, v62, 32);
    std::string::append(v50);
    std::string::_Tidy_deallocate(v60);
    std::string::append(v50);
    sqlencrypt::utils::Base64URLencode(v61, a4, a5);
    std::string::append(v50);
    std::string::_Tidy_deallocate(v61);
    std::string::append(v50);
    v53 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v52[0]) = 0;
    v59 = 0;
    std::string::_Construct_lv_contents(v58, Src);
    v28 = std::string::append(v58);
    v55 = 0;
    *(_OWORD *)v54 = *(_OWORD *)v28;
    v55 = *(_OWORD *)(v28 + 16);
    *(_QWORD *)(v28 + 16) = 0;
    *(_QWORD *)(v28 + 24) = 15;
    *(_BYTE *)v28 = 0;
    v29 = v54;
    if ( *((_QWORD *)&v55 + 1) >= 0x10u )
      LODWORD(v29) = v54[0];
    v30 = sqlencrypt::AzureKeyVault::AKVRequest((int)v43, (int)a1, (int)a2, (int)v29, v52, (__int64)v50, 0);
    std::string::_Tidy_deallocate(v54);
    std::string::_Tidy_deallocate(v58);
    if ( v30 == 200 )
    {
      v31 = v52;
      if ( v53.m128i_i64[1] >= 0x10uLL )
        v31 = (_QWORD *)v52[0];
      if ( v53.m128i_i64[0] >= 0xCuLL )
      {
        v32 = (char *)v31 + v53.m128i_i64[0];
        v33 = v53.m128i_i64[0] - 11;
        for ( j = v31; ; j = v35 )
        {
          v36 = (char *)memchr_0(j, 34, v33);
          v37 = v36;
          if ( !v36 )
            break;
          if ( !memcmp_0(v36, "\"value\":true", 0xCu) )
          {
            if ( v37 - (char *)v31 == -1 )
              break;
            v9 = 1;
            goto LABEL_59;
          }
          v35 = v37 + 1;
          v33 = v32 - 11 - (_BYTE *)v35;
        }
      }
      if ( (bidGblFlags & 2) != 0 && off_1005E6D40[0] && bidID != -1 )
        ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0[0])(
          bidID,
          0,
          571392,
          off_1005E6D40[0],
          0);
      v38 = v48;
      if ( v49 >= 8 )
        v38 = (_QWORD *)v48[0];
      a2(a1, (const unsigned __int16 *)41318, v38);
    }
    else
    {
      if ( (bidGblFlags & 2) != 0 && off_1005E6D38[0] && bidID != -1 )
        ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0[0])(
          bidID,
          0,
          565248,
          off_1005E6D38[0],
          0);
      a2(a1, (const unsigned __int16 *)41348);
    }
LABEL_59:
    std::string::_Tidy_deallocate(v52);
    std::string::_Tidy_deallocate(v50);
    SNI_IOCPIOQueue::Poll((SNI_IOCPIOQueue *)v43, v39);
  }
  else
  {
    if ( (bidGblFlags & 2) != 0 && off_1005E6D30[0] && bidID != -1 )
      ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0[0])(
        bidID,
        0,
        544768,
        off_1005E6D30[0],
        0);
    v25 = GetLastError();
    a2(a1, (const unsigned __int16 *)41328, v25);
    CryptDestroyHash(hHash);
  }
LABEL_60:
  std::basic_string<char16_t>::_Tidy_deallocate(pbData);
  std::string::_Tidy_deallocate(Src);
  std::basic_string<char16_t>::_Tidy_deallocate(v48);
  return v9;
}

```

## disassembly

```asm
0x10046edf0  push    rbp
0x10046edf2  push    rbx
0x10046edf3  push    rsi
0x10046edf4  push    rdi
0x10046edf5  push    r12
0x10046edf7  push    r14
0x10046edf9  push    r15
0x10046edfb  lea     rbp, [rsp-0B0h]
0x10046ee03  sub     rsp, 1B0h
0x10046ee0a  mov     [rsp+1E0h+var_180], 0FFFFFFFFFFFFFFFEh
0x10046ee13  mov     rax, cs:__security_cookie
0x10046ee1a  xor     rax, rsp
0x10046ee1d  mov     [rbp+0E0h+var_38], rax
0x10046ee24  mov     rsi, r9
0x10046ee27  mov     rbx, r8
0x10046ee2a  mov     r15, rdx
0x10046ee2d  mov     r14, rcx
0x10046ee30  movzx   r12d, [rbp+0E0h+arg_20]
0x10046ee38  xor     edi, edi
0x10046ee3a  mov     [rbp+0E0h+var_148], rdi
0x10046ee3e  mov     [rbp+0E0h+var_140], 7
0x10046ee46  mov     word ptr [rbp+0E0h+var_158], di
0x10046ee4a  mov     rax, r8
0x10046ee4d  mov     r8d, edi
0x10046ee50  cmp     [rax], di
0x10046ee53  jz      short loc_10046EE61
0x10046ee55  inc     r8
0x10046ee58  lea     rax, [rax+2]
0x10046ee5c  cmp     [rax], di
0x10046ee5f  jnz     short loc_10046EE55
0x10046ee61  mov     rdx, rbx
0x10046ee64  lea     rcx, [rbp+0E0h+var_158]
0x10046ee68  call    ?assign@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAAAEAV12@QEB_S_K@Z; std::basic_string<char16_t>::assign(char16_t const * const,unsigned __int64)
0x10046ee6d  nop
0x10046ee6e  lea     rcx, [rbp+0E0h+var_158]
0x10046ee72  cmp     [rbp+0E0h+var_140], 8
0x10046ee77  cmovnb  rcx, [rbp+0E0h+var_158]
0x10046ee7c  mov     rax, [rbp+0E0h+var_148]
0x10046ee80  lea     r8, [rcx+rax*2]
0x10046ee84  lea     rdx, [rbp+0E0h+var_158]
0x10046ee88  cmovnb  rdx, [rbp+0E0h+var_158]
0x10046ee8d  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x10046ee95  movdqu  [rbp+0E0h+var_C8], xmm0
0x10046ee9a  mov     [rbp+0E0h+Src], dil
0x10046ee9e  mov     r9b, [rsp+1E0h+var_1A0]
0x10046eea3  lea     rcx, [rbp+0E0h+Src]; Src
0x10046eea7  call    ??$_Construct@PEB_S@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXQEB_S0Uforward_iterator_tag@1@@Z; std::string::_Construct<char16_t const *>(char16_t const * const,char16_t const * const,std::forward_iterator_tag)
0x10046eeac  nop
0x10046eead  mov     [rsp+1E0h+var_168], rdi
0x10046eeb2  mov     [rbp+0E0h+var_160], 7
0x10046eeba  mov     word ptr [rsp+1E0h+pbData], di
0x10046eebf  mov     r8d, 0Fh
0x10046eec5  lea     rdx, aAzureKeyVault; "azure_key_vault"
0x10046eecc  lea     rcx, [rsp+1E0h+pbData]; void *
0x10046eed1  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x10046eed6  nop
0x10046eed7  or      r8, 0FFFFFFFFFFFFFFFFh
0x10046eedb  inc     r8
0x10046eede  cmp     [rbx+r8*2], di
0x10046eee3  jnz     short loc_10046EEDB
0x10046eee5  mov     rdx, rbx
0x10046eee8  lea     rcx, [rsp+1E0h+pbData]; Src
0x10046eeed  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::append(ushort const * const,unsigned __int64)
0x10046eef2  mov     r8d, 4
0x10046eef8  lea     rdx, aTrue; "true"
0x10046eeff  lea     rcx, [rsp+1E0h+pbData]; Src
0x10046ef04  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::append(ushort const * const,unsigned __int64)
0x10046ef09  mov     rcx, rdi
0x10046ef0c  mov     ebx, 20h ; ' '
0x10046ef11  mov     r9, [rsp+1E0h+var_168]
0x10046ef16  test    r9, r9
0x10046ef19  jz      short loc_10046EF73
0x10046ef1b  mov     rdx, [rbp+0E0h+var_160]
0x10046ef1f  mov     r8, [rsp+1E0h+pbData]
0x10046ef24  lea     rax, [rsp+1E0h+pbData]
0x10046ef29  cmp     rdx, 8
0x10046ef2d  cmovnb  rax, r8
0x10046ef31  cmp     word ptr [rax+rcx*2], 41h ; 'A'
0x10046ef36  jb      short loc_10046EF6B
0x10046ef38  lea     rax, [rsp+1E0h+pbData]
0x10046ef3d  cmp     rdx, 8
0x10046ef41  cmovnb  rax, r8
0x10046ef45  cmp     word ptr [rax+rcx*2], 5Ah ; 'Z'
0x10046ef4a  ja      short loc_10046EF6B
0x10046ef4c  lea     rax, [rsp+1E0h+pbData]
0x10046ef51  cmp     rdx, 8
0x10046ef55  cmovnb  rax, r8
0x10046ef59  or      [rax+rcx*2], bx
0x10046ef5d  mov     rdx, [rbp+0E0h+var_160]
0x10046ef61  mov     r9, [rsp+1E0h+var_168]
0x10046ef66  mov     r8, [rsp+1E0h+pbData]
0x10046ef6b  inc     rcx
0x10046ef6e  cmp     rcx, r9
0x10046ef71  jb      short loc_10046EF24
0x10046ef73  call    ?GetWinCryptProvider@SqlSecurityUtility@sqlencrypt@@SA_KXZ; sqlencrypt::SqlSecurityUtility::GetWinCryptProvider(void)
0x10046ef78  test    rax, rax
0x10046ef7b  jnz     short loc_10046EFB3
0x10046ef7d  test    byte ptr cs:_bidGblFlags, 2
0x10046ef84  jz      loc_10046F020
0x10046ef8a  mov     rax, cs:off_1005E6D20; "<sqlencrypt::AzureKeyVault::VerifyCMKMe"...
0x10046ef91  test    rax, rax
0x10046ef94  jz      loc_10046F020
0x10046ef9a  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x10046efa2  jz      short loc_10046F020
0x10046efa4  mov     r9, cs:off_1005E6D20; "<sqlencrypt::AzureKeyVault::VerifyCMKMe"...
0x10046efab  mov     r8d, 81800h
0x10046efb1  jmp     short loc_10046F005
0x10046efb3  mov     [rsp+1E0h+pdwDataLen], ebx
0x10046efb7  lea     rcx, [rsp+1E0h+hHash]
0x10046efbc  mov     [rsp+1E0h+phHash], rcx; phHash
0x10046efc1  xor     r9d, r9d; dwFlags
0x10046efc4  xor     r8d, r8d; hKey
0x10046efc7  mov     edx, 800Ch; Algid
0x10046efcc  mov     rcx, rax; hProv
0x10046efcf  call    cs:__imp_CryptCreateHash
0x10046efd5  test    eax, eax
0x10046efd7  jnz     short loc_10046F03F
0x10046efd9  test    byte ptr cs:_bidGblFlags, 2
0x10046efe0  jz      short loc_10046F020
0x10046efe2  mov     rax, cs:off_1005E6D28; "<sqlencrypt::AzureKeyVault::VerifyCMKMe"...
0x10046efe9  test    rax, rax
0x10046efec  jz      short loc_10046F020
0x10046efee  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x10046eff6  jz      short loc_10046F020
0x10046eff8  mov     r9, cs:off_1005E6D28; "<sqlencrypt::AzureKeyVault::VerifyCMKMe"...
0x10046efff  mov     r8d, 83800h
0x10046f005  xor     edx, edx
0x10046f007  mov     [rsp+1E0h+phHash], rdi
0x10046f00c  mov     rax, cs:off_1005D39E0
0x10046f013  mov     rcx, cs:_bidID
0x10046f01a  call    cs:__guard_dispatch_icall_fptr
0x10046f020  call    cs:__imp_GetLastError
0x10046f026  mov     r8d, eax
0x10046f029  mov     edx, 0A170h
0x10046f02e  mov     rcx, r14
0x10046f031  mov     rax, r15
0x10046f034  call    cs:__guard_dispatch_icall_fptr
0x10046f03a  jmp     loc_10046F3EF
0x10046f03f  lea     rdx, [rsp+1E0h+pbData]
0x10046f044  cmp     [rbp+0E0h+var_160], 8
0x10046f049  cmovnb  rdx, [rsp+1E0h+pbData]; pbData
0x10046f04f  mov     r8d, dword ptr [rsp+1E0h+var_168]
0x10046f054  add     r8d, r8d; dwDataLen
0x10046f057  xor     r9d, r9d; dwFlags
0x10046f05a  mov     rcx, [rsp+1E0h+hHash]; hHash
0x10046f05f  call    cs:__imp_CryptHashData
0x10046f065  test    eax, eax
0x10046f067  jnz     short loc_10046F0DA
0x10046f069  test    byte ptr cs:_bidGblFlags, 2
0x10046f070  jz      short loc_10046F0B0
0x10046f072  mov     rax, cs:off_1005E6D30; "<sqlencrypt::AzureKeyVault::VerifyCMKMe"...
0x10046f079  test    rax, rax
0x10046f07c  jz      short loc_10046F0B0
0x10046f07e  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x10046f086  jz      short loc_10046F0B0
0x10046f088  mov     rax, cs:off_1005D39E0
0x10046f08f  mov     [rsp+1E0h+phHash], rdi
0x10046f094  mov     r9, cs:off_1005E6D30; "<sqlencrypt::AzureKeyVault::VerifyCMKMe"...
0x10046f09b  xor     edx, edx
0x10046f09d  mov     r8d, 85000h
0x10046f0a3  mov     rcx, cs:_bidID
0x10046f0aa  call    cs:__guard_dispatch_icall_fptr
0x10046f0b0  call    cs:__imp_GetLastError
0x10046f0b6  mov     r8d, eax
0x10046f0b9  mov     edx, 0A170h
0x10046f0be  mov     rcx, r14
0x10046f0c1  mov     rax, r15
0x10046f0c4  call    cs:__guard_dispatch_icall_fptr
0x10046f0ca  mov     rcx, [rsp+1E0h+hHash]; hHash
0x10046f0cf  call    cs:__imp_CryptDestroyHash
0x10046f0d5  jmp     loc_10046F3EF
0x10046f0da  mov     dword ptr [rsp+1E0h+phHash], edi; dwFlags
0x10046f0de  lea     r9, [rsp+1E0h+pdwDataLen]; pdwDataLen
0x10046f0e3  lea     r8, [rbp+0E0h+var_58]; pbData
0x10046f0ea  mov     edx, 2; dwParam
0x10046f0ef  mov     rcx, [rsp+1E0h+hHash]; hHash
0x10046f0f4  call    cs:__imp_CryptGetHashParam
0x10046f0fa  mov     rcx, [rsp+1E0h+hHash]; hHash
0x10046f0ff  call    cs:__imp_CryptDestroyHash
0x10046f105  mov     rcx, r14; struct CEKeystoreContext *
0x10046f108  call    ?GetConfig@AzureKeyVault@sqlencrypt@@CAAEAUConfigData@12@PEAUCEKeystoreContext@@@Z; sqlencrypt::AzureKeyVault::GetConfig(CEKeystoreContext *)
0x10046f10d  mov     r9d, [rax+90h]; unsigned int
0x10046f114  mov     r8d, [rax+8Ch]; unsigned int
0x10046f11b  mov     edx, [rax+88h]; unsigned int
0x10046f121  lea     rcx, [rsp+1E0h+var_190]; this
0x10046f126  call    ??0AzureADAuth@aadauth@@QEAA@KKK@Z; aadauth::AzureADAuth::AzureADAuth(ulong,ulong,ulong)
0x10046f12b  nop
0x10046f12c  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x10046f134  movdqu  [rbp+0E0h+var_128], xmm0
0x10046f139  mov     [rbp+0E0h+var_138], dil
0x10046f13d  lfence
0x10046f140  lea     r9, aAlgRs256Digest; "{\"alg\":\"RS256\",\"digest\":\""
0x10046f147  mov     r8b, dil
0x10046f14a  mov     edx, 19h
0x10046f14f  lea     rcx, [rbp+0E0h+var_138]
0x10046f153  call    ??$_Reallocate_for@V_lambda_66f57f934f28d61049862f64df852ff0_@@PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@_KV_lambda_66f57f934f28d61049862f64df852ff0_@@PEBD@Z; std::string::_Reallocate_for<_lambda_66f57f934f28d61049862f64df852ff0_,char const *>(unsigned __int64,_lambda_66f57f934f28d61049862f64df852ff0_,char const *)
0x10046f158  nop
0x10046f159  mov     r8, rbx
0x10046f15c  lea     rdx, [rbp+0E0h+var_58]
0x10046f163  lea     rcx, [rbp+0E0h+var_98]
0x10046f167  call    ?Base64URLencode@utils@sqlencrypt@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBE_K@Z; sqlencrypt::utils::Base64URLencode(uchar const *,unsigned __int64)
0x10046f16c  nop
0x10046f16d  mov     rdx, rax
0x10046f170  cmp     qword ptr [rax+18h], 10h
0x10046f175  jb      short loc_10046F17A
0x10046f177  mov     rdx, [rax]
0x10046f17a  mov     r8, [rax+10h]
0x10046f17e  lea     rcx, [rbp+0E0h+var_138]; Src
0x10046f182  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x10046f187  nop
0x10046f188  lea     rcx, [rbp+0E0h+var_98]
0x10046f18c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXXZ; std::string::_Tidy_deallocate(void)
0x10046f191  mov     r8d, 0Bh
0x10046f197  lea     rdx, aValue; "\",\"value\":\""
0x10046f19e  lea     rcx, [rbp+0E0h+var_138]; Src
0x10046f1a2  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x10046f1a7  mov     r8, r12
0x10046f1aa  mov     rdx, rsi
0x10046f1ad  lea     rcx, [rbp+0E0h+var_78]
0x10046f1b1  call    ?Base64URLencode@utils@sqlencrypt@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBE_K@Z; sqlencrypt::utils::Base64URLencode(uchar const *,unsigned __int64)
0x10046f1b6  nop
0x10046f1b7  mov     rdx, rax
0x10046f1ba  cmp     qword ptr [rax+18h], 10h
0x10046f1bf  jb      short loc_10046F1C4
0x10046f1c1  mov     rdx, [rax]
0x10046f1c4  mov     r8, [rax+10h]
0x10046f1c8  lea     rcx, [rbp+0E0h+var_138]; Src
0x10046f1cc  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x10046f1d1  nop
0x10046f1d2  lea     rcx, [rbp+0E0h+var_78]
0x10046f1d6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXXZ; std::string::_Tidy_deallocate(void)
0x10046f1db  mov     r8d, 2
0x10046f1e1  lea     rdx, asc_100593C5C; "\"}"
0x10046f1e8  lea     rcx, [rbp+0E0h+var_138]; Src
0x10046f1ec  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x10046f1f1  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x10046f1f9  movdqu  [rbp+0E0h+var_108], xmm0
0x10046f1fe  mov     byte ptr [rbp+0E0h+var_118], dil
0x10046f202  xorps   xmm0, xmm0
0x10046f205  movdqu  [rbp+0E0h+var_A8], xmm0
0x10046f20a  lea     rdx, [rbp+0E0h+Src]
0x10046f20e  lea     rcx, [rbp+0E0h+var_B8]
0x10046f212  call    ?_Construct_lv_contents@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXAEBV12@@Z; std::string::_Construct_lv_contents(std::string const &)
0x10046f217  nop
0x10046f218  mov     r8d, 7
0x10046f21e  lea     rdx, aVerify; "/verify"
0x10046f225  lea     rcx, [rbp+0E0h+var_B8]; Src
0x10046f229  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x10046f22e  xorps   xmm0, xmm0
0x10046f231  movdqu  [rbp+0E0h+var_E8], xmm0
0x10046f236  movups  xmm0, xmmword ptr [rax]
0x10046f239  movups  xmmword ptr [rbp+0E0h+var_F8], xmm0
0x10046f23d  movups  xmm1, xmmword ptr [rax+10h]
0x10046f241  movups  [rbp+0E0h+var_E8], xmm1
0x10046f245  mov     [rax+10h], rdi
0x10046f249  mov     qword ptr [rax+18h], 0Fh
0x10046f251  mov     [rax], dil
0x10046f254  lea     r9, [rbp+0E0h+var_F8]
0x10046f258  cmp     qword ptr [rbp+0E0h+var_E8+8], 10h
0x10046f25d  cmovnb  r9, qword ptr [rbp+0E0h+var_F8]; int
0x10046f262  mov     [rsp+1E0h+var_1B0], dil; char
0x10046f267  lea     rax, [rbp+0E0h+var_138]
0x10046f26b  mov     [rsp+1E0h+var_1B8], rax; __int64
0x10046f270  lea     rax, [rbp+0E0h+var_118]
0x10046f274  mov     [rsp+1E0h+phHash], rax; void *
0x10046f279  mov     r8, r15; int
0x10046f27c  mov     rdx, r14; int
0x10046f27f  lea     rcx, [rsp+1E0h+var_190]; int
0x10046f284  call    ?AKVRequest@AzureKeyVault@sqlencrypt@@CAJAEBVAzureADAuth@aadauth@@PEAUCEKeystoreContext@@P6AX1PEBGZZPEBDAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAV67@_N@Z; sqlencrypt::AzureKeyVault::AKVRequest(aadauth::AzureADAuth const &,CEKeystoreContext *,void (*)(CEKeystoreContext *,ushort const *,...),char const *,std::string &,std::string *,bool)
0x10046f289  mov     ebx, eax
0x10046f28b  lea     rcx, [rbp+0E0h+var_F8]
0x10046f28f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXXZ; std::string::_Tidy_deallocate(void)
0x10046f294  nop
0x10046f295  lea     rcx, [rbp+0E0h+var_B8]
0x10046f299  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXXZ; std::string::_Tidy_deallocate(void)
0x10046f29e  cmp     ebx, 0C8h
0x10046f2a4  jz      short loc_10046F303
0x10046f2a6  test    byte ptr cs:_bidGblFlags, 2
0x10046f2ad  jz      short loc_10046F2ED
0x10046f2af  mov     rax, cs:off_1005E6D38; "<sqlencrypt::AzureKeyVault::VerifyCMKMe"...
0x10046f2b6  test    rax, rax
0x10046f2b9  jz      short loc_10046F2ED
0x10046f2bb  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x10046f2c3  jz      short loc_10046F2ED
0x10046f2c5  mov     rax, cs:off_1005D39E0
0x10046f2cc  mov     [rsp+1E0h+phHash], rdi
0x10046f2d1  mov     r9, cs:off_1005E6D38; "<sqlencrypt::AzureKeyVault::VerifyCMKMe"...
0x10046f2d8  xor     edx, edx
0x10046f2da  mov     r8d, 8A000h
0x10046f2e0  mov     rcx, cs:_bidID
0x10046f2e7  call    cs:__guard_dispatch_icall_fptr
0x10046f2ed  mov     edx, 0A184h
0x10046f2f2  mov     rcx, r14
0x10046f2f5  mov     rax, r15
0x10046f2f8  call    cs:__guard_dispatch_icall_fptr
0x10046f2fe  jmp     loc_10046F3D0
0x10046f303  lea     rsi, [rbp+0E0h+var_118]
0x10046f307  cmp     qword ptr [rbp+0E0h+var_108+8], 10h
0x10046f30c  cmovnb  rsi, [rbp+0E0h+var_118]
0x10046f311  mov     rax, qword ptr [rbp+0E0h+var_108]
  ... truncated ...
```
