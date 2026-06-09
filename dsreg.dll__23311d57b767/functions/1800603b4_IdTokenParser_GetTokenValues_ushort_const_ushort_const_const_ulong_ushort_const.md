# IdTokenParser::GetTokenValues(ushort const *,ushort const * * const,ulong,ushort * * const)

- ea: `0x1800603b4`
- end: `0x1800607c4`
- name: `?GetTokenValues@IdTokenParser@@CAJPEBGQEAPEBGKQEAPEAG@Z`
- size: `1040`
- prototype: `__int64 __fastcall(wchar_t *Str, const unsigned __int16 **const, unsigned int, unsigned __int16 **const)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x18005ffb0`

## callees

- `0x1800084f4`
- `0x180009780`
- `0x18000fba0`
- `0x1800307c4`
- `0x18003334c`
- `0x18003b2bc`
- `0x180043ef8`
- `0x180044cd0`
- `0x180044d30`
- `0x18004654c`
- `0x18006018c`
- `0x1800603b4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800604b8`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18006050c`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800604b8`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18006050c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800606d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800606d5`
- `CRYPT32!CryptStringToBinaryW` at `0x180060681`
- `CRYPT32!CryptStringToBinaryW` at `0x1800606cb`
- `CRYPT32!CryptStringToBinaryW` at `0x180060681`
- `CRYPT32!CryptStringToBinaryW` at `0x1800606cb`

## string_xrefs

- `0x180060442`: `pcszAuthToken`
- `0x180060455`: `pcszAuthToken`
- `0x1800603f8`: `IdTokenParser::GetTokenValues`
- `0x180060433`: `IdTokenParser::GetTokenValues`
- `0x180060463`: `IdTokenParser::GetTokenValues`
- `0x1800604cd`: `IdTokenParser::GetTokenValues`
- `0x180060573`: `IdTokenParser::GetTokenValues`
- `0x1800605cb`: `IdTokenParser::GetTokenValues`
- `0x1800606dd`: `IdTokenParser::GetTokenValues`
- `0x180060741`: `IdTokenParser::GetTokenValues`
- `0x180060786`: `IdTokenParser::GetTokenValues`
- `0x1800604c3`: `%s: Improperly formatted token (first delimiter): %s`
- `0x1800604f9`: `%s: Improperly formatted token (second delimiter can't exist): %s`
- `0x18006051a`: `%s: Improperly formatted token (second delimiter): %s`
- `0x180060532`: `%s: Improperly formatted token (third segment): %s`
- `0x180060543`: `%s: Improperly formatted token (empty payload): %s`
- `0x18006057a`: `%s: JwtToken in token is not a valid base64 encoded string. The number of padding is %zu, exceeding the allowable 2 chars. Token: %s`
- `0x18006077c`: `IdTokenParser::GetStringPropertiesFromJwtToken`

## pseudocode

```c
__int64 __fastcall IdTokenParser::GetTokenValues(
        wchar_t *Str,
        unsigned __int16 **a2,
        DWORD a3,
        unsigned __int16 **const a4)
{
  CHAR *v4; // r15
  unsigned __int16 *v5; // r12
  char *v6; // rsi
  DWORD LastError; // ebx
  const unsigned __int16 *v9; // rdx
  int StringPropertiesFromJwtToken; // eax
  const wchar_t *v11; // r8
  wchar_t *v12; // rax
  unsigned __int64 v13; // r14
  const wchar_t *v14; // r13
  wchar_t *v15; // rax
  __int64 v16; // rbx
  __int64 v17; // r14
  unsigned __int64 v18; // rdi
  unsigned __int64 v19; // rax
  char *v20; // rax
  rsize_t v21; // rbx
  unsigned __int64 i; // rax
  BYTE *v23; // rax
  unsigned int v24; // edx
  int v25; // eax
  unsigned int v26; // r9d
  unsigned int v28; // [rsp+40h] [rbp-28h] BYREF
  unsigned __int64 v29; // [rsp+48h] [rbp-20h] BYREF
  unsigned __int16 *v30; // [rsp+50h] [rbp-18h] BYREF
  DWORD pdwFlags; // [rsp+B0h] [rbp+48h] BYREF
  unsigned __int16 **v32; // [rsp+B8h] [rbp+50h]
  DWORD pcbBinary; // [rsp+C0h] [rbp+58h] BYREF
  unsigned __int16 **v34; // [rsp+C8h] [rbp+60h]

  v34 = a4;
  pcbBinary = a3;
  v32 = a2;
  v4 = 0;
  v28 = 0;
  v5 = 0;
  v29 = 0;
  v6 = 0;
  v30 = 0;
  if ( !a4 )
  {
    LastError = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"IdTokenParser::GetTokenValues", L"values");
    v9 = L"values";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"IdTokenParser::GetTokenValues", v9);
    goto LABEL_49;
  }
  if ( !Str )
  {
    LastError = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"IdTokenParser::GetTokenValues", L"pcszAuthToken");
    v9 = L"pcszAuthToken";
    goto LABEL_3;
  }
  if ( !a2 )
  {
    LastError = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"IdTokenParser::GetTokenValues", L"properties");
    v9 = L"properties";
    goto LABEL_3;
  }
  StringPropertiesFromJwtToken = StringCchLengthW(Str, 0x7FFFFFFFu, &v29);
  LastError = StringPropertiesFromJwtToken;
  if ( StringPropertiesFromJwtToken < 0 )
  {
    v11 = L"StringCchLengthW";
    goto LABEL_48;
  }
  v12 = wcsstr(Str, L".");
  if ( !v12 )
  {
    Logger::TraceError(L"%s: Improperly formatted token (first delimiter): %s", L"IdTokenParser::GetTokenValues", Str);
LABEL_12:
    LastError = -2147024809;
    goto LABEL_49;
  }
  v13 = v29;
  v14 = v12 + 1;
  if ( v12 + 1 - Str > v29 )
  {
    Logger::TraceError(
      L"%s: Improperly formatted token (second delimiter can't exist): %s",
      L"IdTokenParser::GetTokenValues",
      Str);
    goto LABEL_12;
  }
  v15 = wcsstr(v14, L".");
  if ( !v15 )
  {
    Logger::TraceError(L"%s: Improperly formatted token (second delimiter): %s", L"IdTokenParser::GetTokenValues", Str);
    goto LABEL_12;
  }
  if ( v13 - (v15 - Str) == 1 )
  {
    Logger::TraceError(L"%s: Improperly formatted token (third segment): %s", L"IdTokenParser::GetTokenValues", Str);
    goto LABEL_12;
  }
  v16 = v15 - v14;
  if ( !v16 )
  {
    Logger::TraceError(L"%s: Improperly formatted token (empty payload): %s", L"IdTokenParser::GetTokenValues", Str);
    goto LABEL_12;
  }
  v17 = 0;
  if ( (v16 & 3) != 0 )
  {
    if ( ((v15 - v14) & 3) == 2 )
    {
      v17 = 2;
    }
    else
    {
      if ( ((v15 - v14) & 3) != 3 )
      {
        LastError = -2147024809;
        Logger::TraceError(
          L"%s: JwtToken in token is not a valid base64 encoded string. The number of padding is %zu, exceeding the allowa"
           "ble 2 chars. Token: %s",
          L"IdTokenParser::GetTokenValues",
          (v15 - v14) & 3,
          Str);
        goto LABEL_49;
      }
      v17 = 1;
    }
  }
  v18 = v16 + v17;
  v19 = 2 * (v16 + v17 + 1);
  if ( !is_mul_ok(v16 + v17 + 1, 2u) )
    v19 = -1;
  v20 = (char *)operator new[](v19, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v20;
  if ( !v20 )
  {
LABEL_30:
    LastError = -2147024882;
    Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"IdTokenParser::GetTokenValues");
    goto LABEL_49;
  }
  memset_0(v20, 0, v18 + 1);
  v21 = 2 * v16;
  memcpy_s_1(v6, v21, v14, v21);
  memcpy_s_1(&v6[v21], 2 * v17 + 2, L"====", 2 * v17);
  *(_WORD *)&v6[2 * v18] = 0;
  for ( i = 0; i < v18; ++i )
  {
    if ( *(_WORD *)&v6[2 * i] == 45 )
    {
      *(_WORD *)&v6[2 * i] = 43;
    }
    else if ( *(_WORD *)&v6[2 * i] == 95 )
    {
      *(_WORD *)&v6[2 * i] = 47;
    }
  }
  pcbBinary = 0;
  pdwFlags = 0;
  if ( CryptStringToBinaryW((LPCWSTR)v6, 0, 1u, 0, &pcbBinary, 0, &pdwFlags) )
  {
    v23 = (BYTE *)operator new[](pcbBinary + 1, (const struct std::nothrow_t *)&std::nothrow);
    v4 = (CHAR *)v23;
    if ( !v23 )
      goto LABEL_30;
    if ( CryptStringToBinaryW((LPCWSTR)v6, 0, 1u, v23, &pcbBinary, 0, &pdwFlags) )
    {
      v4[pcbBinary] = 0;
      v25 = MBToUnicode(v4, v24, &v30, &v28);
      LastError = v25;
      if ( v25 < 0 )
      {
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"IdTokenParser::GetTokenValues",
          L"MBToUnicode",
          (unsigned int)v25);
        v5 = v30;
        goto LABEL_49;
      }
      v5 = v30;
      StringPropertiesFromJwtToken = IdTokenParser::GetStringPropertiesFromJwtToken(
                                       v30,
                                       v28,
                                       (const unsigned __int16 **const)v32,
                                       v26,
                                       v34);
      LastError = StringPropertiesFromJwtToken;
      if ( StringPropertiesFromJwtToken >= 0 )
        goto LABEL_49;
      v11 = L"IdTokenParser::GetStringPropertiesFromJwtToken";
LABEL_48:
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"IdTokenParser::GetTokenValues",
        v11,
        (unsigned int)StringPropertiesFromJwtToken);
      goto LABEL_49;
    }
  }
  LastError = GetLastError();
  if ( !LastError )
    LastError = 1359;
  Logger::TraceError(
    L"%s: %s failed with win32 error code: 0x%08x.",
    L"IdTokenParser::GetTokenValues",
    L"CryptStringToBinaryW",
    LastError);
  if ( (int)LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_49:
  operator delete(v6);
  operator delete(v4);
  SafeFree(v5);
  return LastError;
}

```

## disassembly

```asm
0x1800603b4  mov     [rsp-40h+arg_18], r9
0x1800603b9  mov     [rsp-40h+arg_10], r8d
0x1800603be  mov     [rsp-40h+arg_8], rdx
0x1800603c3  push    rbp
0x1800603c4  push    rbx
0x1800603c5  push    rsi
0x1800603c6  push    rdi
0x1800603c7  push    r12
0x1800603c9  push    r13
0x1800603cb  push    r14
0x1800603cd  push    r15
0x1800603cf  mov     rbp, rsp
0x1800603d2  sub     rsp, 68h
0x1800603d6  xor     r15d, r15d
0x1800603d9  mov     [rbp+var_28], 0
0x1800603e0  xor     r12d, r12d
0x1800603e3  mov     [rbp+var_20], r15
0x1800603e7  xor     esi, esi
0x1800603e9  mov     [rbp+var_18], r12
0x1800603ed  mov     rax, rdx
0x1800603f0  mov     rdi, rcx
0x1800603f3  test    r9, r9
0x1800603f6  jnz     short loc_18006042E
0x1800603f8  lea     rdi, aIdtokenparserG; "IdTokenParser::GetTokenValues"
0x1800603ff  mov     ebx, 80070057h
0x180060404  mov     rdx, rdi
0x180060407  lea     r8, aValues_0; "values"
0x18006040e  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180060415  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18006041a  lea     rdx, aValues_0; "values"
0x180060421  mov     rcx, rdi; unsigned __int16 *
0x180060424  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180060429  jmp     loc_180060799
0x18006042e  test    rdi, rdi
0x180060431  jnz     short loc_18006045E
0x180060433  lea     rdi, aIdtokenparserG; "IdTokenParser::GetTokenValues"
0x18006043a  mov     ebx, 80070057h
0x18006043f  mov     rdx, rdi
0x180060442  lea     r8, aPcszauthtoken; "pcszAuthToken"
0x180060449  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180060450  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180060455  lea     rdx, aPcszauthtoken; "pcszAuthToken"
0x18006045c  jmp     short loc_180060421
0x18006045e  test    rax, rax
0x180060461  jnz     short loc_18006048E
0x180060463  lea     rdi, aIdtokenparserG; "IdTokenParser::GetTokenValues"
0x18006046a  mov     ebx, 80070057h
0x18006046f  mov     rdx, rdi
0x180060472  lea     r8, aProperties; "properties"
0x180060479  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180060480  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180060485  lea     rdx, aProperties; "properties"
0x18006048c  jmp     short loc_180060421
0x18006048e  lea     r8, [rbp+var_20]; unsigned __int64 *
0x180060492  mov     edx, 7FFFFFFFh; unsigned __int64
0x180060497  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18006049c  mov     ebx, eax
0x18006049e  test    eax, eax
0x1800604a0  jns     short loc_1800604AE
0x1800604a2  lea     r8, aStringcchlengt; "StringCchLengthW"
0x1800604a9  jmp     loc_180060783
0x1800604ae  lea     rdx, Control; "."
0x1800604b5  mov     rcx, rdi; Str
0x1800604b8  call    cs:__imp_wcsstr
0x1800604be  test    rax, rax
0x1800604c1  jnz     short loc_1800604E3
0x1800604c3  lea     rcx, aSImproperlyFor_1; "%s: Improperly formatted token (first d"...
0x1800604ca  mov     r8, rdi
0x1800604cd  lea     rdx, aIdtokenparserG; "IdTokenParser::GetTokenValues"
0x1800604d4  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800604d9  mov     ebx, 80070057h
0x1800604de  jmp     loc_180060799
0x1800604e3  mov     r14, [rbp+var_20]
0x1800604e7  lea     r13, [rax+2]
0x1800604eb  mov     rax, r13
0x1800604ee  sub     rax, rdi
0x1800604f1  sar     rax, 1
0x1800604f4  cmp     rax, r14
0x1800604f7  jbe     short loc_180060502
0x1800604f9  lea     rcx, aSImproperlyFor_0; "%s: Improperly formatted token (second "...
0x180060500  jmp     short loc_1800604CA
0x180060502  lea     rdx, Control; "."
0x180060509  mov     rcx, r13; Str
0x18006050c  call    cs:__imp_wcsstr
0x180060512  mov     rbx, rax
0x180060515  test    rax, rax
0x180060518  jnz     short loc_180060523
0x18006051a  lea     rcx, aSImproperlyFor_2; "%s: Improperly formatted token (second "...
0x180060521  jmp     short loc_1800604CA
0x180060523  sub     rax, rdi
0x180060526  sar     rax, 1
0x180060529  sub     r14, rax
0x18006052c  cmp     r14, 1
0x180060530  jnz     short loc_18006053B
0x180060532  lea     rcx, aSImproperlyFor_3; "%s: Improperly formatted token (third s"...
0x180060539  jmp     short loc_1800604CA
0x18006053b  sub     rbx, r13
0x18006053e  sar     rbx, 1
0x180060541  jnz     short loc_18006054F
0x180060543  lea     rcx, aSImproperlyFor; "%s: Improperly formatted token (empty p"...
0x18006054a  jmp     loc_1800604CA
0x18006054f  mov     r8, rbx
0x180060552  xor     r14d, r14d
0x180060555  and     r8d, 3
0x180060559  mov     eax, r8d
0x18006055c  lea     edx, [r14+2]
0x180060560  test    r8, r8
0x180060563  jz      short loc_18006059B
0x180060565  sub     rax, rdx
0x180060568  jz      short loc_180060598
0x18006056a  cmp     rax, 1
0x18006056e  jz      short loc_180060590
0x180060570  mov     r9, rdi
0x180060573  lea     rdx, aIdtokenparserG; "IdTokenParser::GetTokenValues"
0x18006057a  lea     rcx, aSJwttokenInTok; "%s: JwtToken in token is not a valid ba"...
0x180060581  mov     ebx, 80070057h
0x180060586  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18006058b  jmp     loc_180060799
0x180060590  mov     r14d, 1
0x180060596  jmp     short loc_18006059B
0x180060598  mov     r14, rdx
0x18006059b  mov     rax, rdx
0x18006059e  lea     rdi, [rbx+r14]
0x1800605a2  lea     rcx, [rdi+1]
0x1800605a6  mul     rcx
0x1800605a9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800605b0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800605b7  cmovb   rax, rcx
0x1800605bb  mov     rcx, rax; unsigned __int64
0x1800605be  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800605c3  mov     rsi, rax
0x1800605c6  test    rax, rax
0x1800605c9  jnz     short loc_1800605E8
0x1800605cb  lea     rdx, aIdtokenparserG; "IdTokenParser::GetTokenValues"
0x1800605d2  mov     ebx, 8007000Eh
0x1800605d7  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x1800605de  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x1800605e3  jmp     loc_180060799
0x1800605e8  lea     r8, [rdi+1]; Size
0x1800605ec  xor     edx, edx; Val
0x1800605ee  mov     rcx, rsi; void *
0x1800605f1  call    memset_0
0x1800605f6  add     rbx, rbx
0x1800605f9  mov     r8, r13; Source
0x1800605fc  mov     r9, rbx; SourceSize
0x1800605ff  mov     rdx, rbx; DestinationSize
0x180060602  mov     rcx, rsi; Destination
0x180060605  call    memcpy_s_1
0x18006060a  lea     r9, [r14+r14]; SourceSize
0x18006060e  lea     rdx, [r9+2]; DestinationSize
0x180060612  lea     rcx, [rbx+rsi]; Destination
0x180060616  lea     r8, asc_1800E6F40; "===="
0x18006061d  call    memcpy_s_1
0x180060622  xor     r14d, r14d
0x180060625  mov     [rsi+rdi*2], r14w
0x18006062a  mov     eax, r14d
0x18006062d  test    rdi, rdi
0x180060630  jz      short loc_180060656
0x180060632  cmp     word ptr [rsi+rax*2], 2Dh ; '-'
0x180060637  jnz     short loc_180060641
0x180060639  mov     word ptr [rsi+rax*2], 2Bh ; '+'
0x18006063f  jmp     short loc_18006064E
0x180060641  cmp     word ptr [rsi+rax*2], 5Fh ; '_'
0x180060646  jnz     short loc_18006064E
0x180060648  mov     word ptr [rsi+rax*2], 2Fh ; '/'
0x18006064e  inc     rax
0x180060651  cmp     rax, rdi
0x180060654  jb      short loc_180060632
0x180060656  xor     r9d, r9d; pbBinary
0x180060659  mov     [rbp+arg_10], r14d
0x18006065d  lea     rax, [rbp+arg_0]
0x180060661  mov     [rbp+arg_0], r14d
0x180060665  mov     [rsp+68h+pdwFlags], rax; pdwFlags
0x18006066a  xor     edx, edx; cchString
0x18006066c  lea     rax, [rbp+arg_10]
0x180060670  mov     [rsp+68h+pdwSkip], r14; pdwSkip
0x180060675  lea     r8d, [r9+1]; dwFlags
0x180060679  mov     [rsp+68h+pcbBinary], rax; pcbBinary
0x18006067e  mov     rcx, rsi; pszString
0x180060681  call    cs:__imp_CryptStringToBinaryW
0x180060687  test    eax, eax
0x180060689  jz      short loc_1800606D5
0x18006068b  mov     ecx, [rbp+arg_10]
0x18006068e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180060695  inc     ecx; unsigned __int64
0x180060697  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18006069c  mov     r15, rax
0x18006069f  test    rax, rax
0x1800606a2  jz      loc_1800605CB
0x1800606a8  xor     edx, edx; cchString
0x1800606aa  lea     rax, [rbp+arg_0]
0x1800606ae  mov     [rsp+68h+pdwFlags], rax; pdwFlags
0x1800606b3  mov     r9, r15; pbBinary
0x1800606b6  lea     rax, [rbp+arg_10]
0x1800606ba  mov     [rsp+68h+pdwSkip], r14; pdwSkip
0x1800606bf  mov     rcx, rsi; pszString
0x1800606c2  mov     [rsp+68h+pcbBinary], rax; pcbBinary
0x1800606c7  lea     r8d, [rdx+1]; dwFlags
0x1800606cb  call    cs:__imp_CryptStringToBinaryW
0x1800606d1  test    eax, eax
0x1800606d3  jnz     short loc_18006071A
0x1800606d5  call    cs:__imp_GetLastError
0x1800606db  mov     ebx, eax
0x1800606dd  lea     rdi, aIdtokenparserG; "IdTokenParser::GetTokenValues"
0x1800606e4  test    eax, eax
0x1800606e6  lea     r8, aCryptstringtob_0; "CryptStringToBinaryW"
0x1800606ed  mov     eax, 54Fh
0x1800606f2  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x1800606f9  cmovz   ebx, eax
0x1800606fc  mov     rdx, rdi
0x1800606ff  mov     r9d, ebx
0x180060702  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180060707  test    ebx, ebx
0x180060709  jle     loc_180060799
0x18006070f  movzx   ebx, bx
0x180060712  or      ebx, 80070000h
0x180060718  jmp     short loc_180060799
0x18006071a  mov     eax, [rbp+arg_10]
0x18006071d  lea     r9, [rbp+var_28]; unsigned int *
0x180060721  lea     r8, [rbp+var_18]; unsigned __int16 **
0x180060725  mov     rcx, r15; lpMultiByteStr
0x180060728  mov     [rax+r15], r14b
0x18006072c  call    ?MBToUnicode@@YAJPEBDIPEAPEAGPEAK@Z; MBToUnicode(char const *,uint,ushort * *,ulong *)
0x180060731  mov     ebx, eax
0x180060733  test    eax, eax
0x180060735  jns     short loc_18006075A
0x180060737  mov     r9d, eax
0x18006073a  lea     r8, aMbtounicode; "MBToUnicode"
0x180060741  lea     rdx, aIdtokenparserG; "IdTokenParser::GetTokenValues"
0x180060748  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18006074f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180060754  mov     r12, [rbp+var_18]
0x180060758  jmp     short loc_180060799
0x18006075a  mov     rax, [rbp+arg_18]
0x18006075e  mov     r12, [rbp+var_18]
0x180060762  mov     r8, [rbp+arg_8]; unsigned __int16 **
0x180060766  mov     rcx, r12; unsigned __int16 *
0x180060769  mov     edx, [rbp+var_28]; unsigned int
0x18006076c  mov     [rsp+68h+pcbBinary], rax; unsigned __int16 **
0x180060771  call    ?GetStringPropertiesFromJwtToken@IdTokenParser@@CAJPEAGKQEAPEBGKQEAPEAG@Z; IdTokenParser::GetStringPropertiesFromJwtToken(ushort *,ulong,ushort const * * const,ulong,ushort * * const)
0x180060776  mov     ebx, eax
0x180060778  test    eax, eax
0x18006077a  jns     short loc_180060799
0x18006077c  lea     r8, aIdtokenparserG_0; "IdTokenParser::GetStringPropertiesFromJ"...
0x180060783  mov     r9d, eax
0x180060786  lea     rdx, aIdtokenparserG; "IdTokenParser::GetTokenValues"
0x18006078d  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180060794  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180060799  mov     rcx, rsi; Block
0x18006079c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800607a1  mov     rcx, r15; Block
0x1800607a4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800607a9  mov     rcx, r12; lpMem
0x1800607ac  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800607b1  mov     eax, ebx
0x1800607b3  add     rsp, 68h
0x1800607b7  pop     r15
0x1800607b9  pop     r14
0x1800607bb  pop     r13
0x1800607bd  pop     r12
0x1800607bf  pop     rdi
0x1800607c0  pop     rsi
0x1800607c1  pop     rbx
0x1800607c2  pop     rbp
0x1800607c3  retn
```
