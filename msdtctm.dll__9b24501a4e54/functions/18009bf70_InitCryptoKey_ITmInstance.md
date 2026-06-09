# InitCryptoKey(ITmInstance *)

- ea: `0x18009bf70`
- end: `0x18009c4e8`
- name: `?InitCryptoKey@@YAJPEAUITmInstance@@@Z`
- size: `1400`
- prototype: `__int64 __fastcall(struct ITmInstance *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000ae50`

## callees

- `0x1800063b0`
- `0x1800240f0`
- `0x1800240fc`
- `0x1800846c0`
- `0x18009bf70`
- `0x1800ad808`
- `0x1800b8420`
- `0x1800bd010`

## import_xrefs

- `RPCRT4!UuidToStringW` at `0x18009bfc1`
- `RPCRT4!UuidToStringW` at `0x18009bfc1`
- `RPCRT4!RpcStringFreeW` at `0x18009c489`
- `RPCRT4!RpcStringFreeW` at `0x18009c489`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18009c0f0`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18009c0f0`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18009c4b0`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18009c4b0`
- `bcrypt!BCryptImportKey` at `0x18009c438`
- `bcrypt!BCryptImportKey` at `0x18009c438`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18009c29f`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18009c33a`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18009c29f`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18009c33a`
- `bcrypt!BCryptGetProperty` at `0x18009c3bc`
- `bcrypt!BCryptGetProperty` at `0x18009c3bc`
- `bcrypt!BCryptSetProperty` at `0x18009c36f`
- `bcrypt!BCryptSetProperty` at `0x18009c36f`
- `bcrypt!BCryptGenRandom` at `0x18009c301`
- `bcrypt!BCryptGenRandom` at `0x18009c301`

## string_xrefs

- `0x18009c2c6`: `com\complus\dtc\dtc\xatm\src\xatmcrypt.cpp`
- `0x18009c46c`: `com\complus\dtc\dtc\xatm\src\xatmcrypt.cpp`
- `0x18009c10e`: `Error from GetXATmSecurityKeyCNGSize`
- `0x18009c0af`: `Error from GetXATmSecurityKey`
- `0x18009c274`: `Error from GetXATmSecurityKeyCNG`
- `0x18009c133`: `Unable to allocate memory for XATM Security Key`
- `0x18009c2b6`: `Error from BCryptOpenAlgorithmProvider(%s)`
- `0x18009c497`: `InitCryptoKey (com\complus\dtc\dtc\xatm\src\xatmcrypt.cpp@233): Deallocation of string Uuid failed.`
- `0x18009c07a`: `com\complus\dtc\shared\util\xasecurity.cpp`
- `0x18009c17a`: `com\complus\dtc\shared\util\xasecurity.cpp`
- `0x18009c200`: `com\complus\dtc\shared\util\xasecurity.cpp`
- `0x18009c243`: `com\complus\dtc\shared\util\xasecurity.cpp`
- `0x18009c1c5`: `Security\XAKeyCNGKeyDataBlob`
- `0x18009c1f4`: `Security\XAKeyCNGKeyDataBlob`
- `0x18009c033`: `Security\XAKey`
- `0x18009c06e`: `Security\XAKey`
- `0x18009c095`: `GetXATmSecurityKey`
- `0x18009c081`: `Error from ITmInstance::GetRegistryValue : KeyName - %s, ValueName - %s`
- `0x18009c207`: `Error from ITmInstance::GetRegistryValue : KeyName - %s, ValueName - `
- `0x18009c181`: `GetXATmSecurityKeyCNG`
- `0x18009c21b`: `GetXATmSecurityKeyCNG`
- `0x18009c24d`: `GetXATmSecurityKeyCNG`

## pseudocode

```c
__int64 __fastcall InitCryptoKey(struct ITmInstance *a1)
{
  UCHAR *v2; // rsi
  RPC_STATUS v3; // eax
  RPC_STATUS v4; // r14d
  int XATmSecurityKeyCNGSize; // ebx
  RPC_WSTR v6; // r12
  __int64 v7; // rax
  __int64 (__fastcall *v8)(struct ITmInstance *, const wchar_t *, RPC_WSTR, int *, WCHAR *, unsigned int *); // rax
  ULONG v9; // ebx
  const wchar_t *v10; // rax
  __int64 v11; // r9
  RPC_WSTR v12; // r13
  __int64 v13; // rax
  int v14; // eax
  ULONG v15; // r15d
  const WCHAR *v16; // r12
  NTSTATUS v17; // eax
  __int64 v18; // r9
  NTSTATUS v19; // eax
  NTSTATUS v20; // ebx
  __int64 v21; // r9
  const wchar_t *v22; // rax
  NTSTATUS v23; // eax
  NTSTATUS Property; // eax
  NTSTATUS v25; // eax
  LPBOOL lpUsedDefaultChar; // [rsp+38h] [rbp-C8h]
  ULONG cbInput; // [rsp+50h] [rbp-B0h] BYREF
  int v29; // [rsp+54h] [rbp-ACh] BYREF
  RPC_WSTR StringUuid; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v31; // [rsp+60h] [rbp-A0h] BYREF
  ULONG pcbResult; // [rsp+64h] [rbp-9Ch] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+68h] [rbp-98h] BYREF
  WCHAR WideCharStr[256]; // [rsp+70h] [rbp-90h] BYREF

  StringUuid = 0;
  phAlgorithm = 0;
  v2 = 0;
  cbInput = 0;
  v3 = UuidToStringW(&g_guidXATM, &StringUuid);
  v4 = v3;
  if ( v3 > 0 )
    XATmSecurityKeyCNGSize = (unsigned __int16)v3 | 0x80070000;
  else
    XATmSecurityKeyCNGSize = v3;
  if ( XATmSecurityKeyCNGSize < 0 )
  {
    TraceStringInline(
      11,
      1,
      L"com\\complus\\dtc\\dtc\\xatm\\src\\xatmcrypt.cpp",
      78,
      L"InitCryptoKey",
      XATmSecurityKeyCNGSize,
      L"Error from UuidToStringW");
    goto LABEL_41;
  }
  if ( !a1 || (v6 = StringUuid) == 0 )
  {
    XATmSecurityKeyCNGSize = -2147024809;
LABEL_12:
    TraceStringInline(
      11,
      1,
      L"com\\complus\\dtc\\dtc\\xatm\\src\\xatmcrypt.cpp",
      90,
      L"InitCryptoKey",
      XATmSecurityKeyCNGSize,
      L"Error from GetXATmSecurityKey");
    goto LABEL_41;
  }
  v7 = *(_QWORD *)a1;
  v29 = 1;
  v8 = *(__int64 (__fastcall **)(struct ITmInstance *, const wchar_t *, RPC_WSTR, int *, WCHAR *, unsigned int *))(v7 + 400);
  v31 = 512;
  XATmSecurityKeyCNGSize = v8(a1, L"Security\\XAKey", StringUuid, &v29, WideCharStr, &v31);
  if ( (int)(XATmSecurityKeyCNGSize + 0x80000000) >= 0 && XATmSecurityKeyCNGSize != -2147024894 )
  {
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\xasecurity.cpp",
      357,
      L"GetXATmSecurityKey",
      XATmSecurityKeyCNGSize,
      L"Error from ITmInstance::GetRegistryValue : KeyName - %s, ValueName - %s",
      L"Security\\XAKey",
      v6);
    goto LABEL_12;
  }
  WideCharToMultiByte(0, 0, WideCharStr, v31 >> 1, MultiByteStr, 256, 0, 0);
  XATmSecurityKeyCNGSize = GetXATmSecurityKeyCNGSize(a1, StringUuid, &cbInput);
  if ( XATmSecurityKeyCNGSize < 0 )
  {
    TraceStringInline(
      11,
      1,
      L"com\\complus\\dtc\\dtc\\xatm\\src\\xatmcrypt.cpp",
      111,
      L"InitCryptoKey",
      XATmSecurityKeyCNGSize,
      L"Error from GetXATmSecurityKeyCNGSize");
    goto LABEL_41;
  }
  v9 = cbInput;
  v2 = (UCHAR *)operator new[](cbInput);
  if ( !v2 )
  {
    v10 = L"Unable to allocate memory for XATM Security Key";
    v11 = 120;
LABEL_17:
    XATmSecurityKeyCNGSize = -2147024882;
    TraceStringInline(
      11,
      1,
      L"com\\complus\\dtc\\dtc\\xatm\\src\\xatmcrypt.cpp",
      v11,
      L"InitCryptoKey",
      -2147024882,
      v10);
    goto LABEL_41;
  }
  v12 = StringUuid;
  if ( !StringUuid )
  {
    XATmSecurityKeyCNGSize = -2147024809;
LABEL_23:
    TraceStringInline(
      11,
      1,
      L"com\\complus\\dtc\\dtc\\xatm\\src\\xatmcrypt.cpp",
      127,
      L"InitCryptoKey",
      XATmSecurityKeyCNGSize,
      L"Error from GetXATmSecurityKeyCNG");
    goto LABEL_41;
  }
  TraceStringInline(
    7,
    5,
    L"com\\complus\\dtc\\shared\\util\\xasecurity.cpp",
    524,
    L"GetXATmSecurityKeyCNG",
    0,
    L"Entering method");
  v13 = *(_QWORD *)a1;
  v29 = 3;
  cbInput = v9;
  v14 = (*(__int64 (__fastcall **)(struct ITmInstance *, const wchar_t *, RPC_WSTR, int *, UCHAR *, ULONG *))(v13 + 400))(
          a1,
          L"Security\\XAKeyCNGKeyDataBlob",
          v12,
          &v29,
          v2,
          &cbInput);
  v15 = cbInput;
  XATmSecurityKeyCNGSize = v14;
  if ( v14 < 0 )
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\xasecurity.cpp",
      540,
      L"GetXATmSecurityKeyCNG",
      v14,
      L"Error from ITmInstance::GetRegistryValue : KeyName - %s, ValueName - ",
      L"Security\\XAKeyCNGKeyDataBlob",
      v12);
  LODWORD(lpUsedDefaultChar) = XATmSecurityKeyCNGSize;
  TraceStringInline(
    7,
    5,
    L"com\\complus\\dtc\\shared\\util\\xasecurity.cpp",
    554,
    L"GetXATmSecurityKeyCNG",
    0,
    L"Exiting method, hr = 0x%x",
    lpUsedDefaultChar);
  if ( XATmSecurityKeyCNGSize < 0 )
    goto LABEL_23;
  v16 = L"RNG";
  v17 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"RNG", L"Microsoft Primitive Provider", 0);
  if ( v17 )
  {
    v18 = 141;
LABEL_26:
    XATmSecurityKeyCNGSize = v17 | 0x10000000;
    TraceStringInline(
      11,
      1,
      L"com\\complus\\dtc\\dtc\\xatm\\src\\xatmcrypt.cpp",
      v18,
      L"InitCryptoKey",
      v17 | 0x10000000,
      L"Error from BCryptOpenAlgorithmProvider(%s)",
      v16);
    goto LABEL_41;
  }
  v19 = BCryptGenRandom(phAlgorithm, &g_bInitVectorCNG, 0x10u, 0);
  if ( v19 )
  {
    v20 = v19;
    v21 = 153;
    v22 = L"Error from BCryptGenRandom";
    goto LABEL_39;
  }
  v16 = L"AES";
  v17 = BCryptOpenAlgorithmProvider(&g_hAesProv, L"AES", L"Microsoft Primitive Provider", 0);
  if ( v17 )
  {
    v18 = 165;
    goto LABEL_26;
  }
  v23 = BCryptSetProperty(g_hAesProv, L"ChainingMode", (PUCHAR)L"ChainingModeCBC", 0x20u, 0);
  if ( v23 )
  {
    v20 = v23;
    v21 = 179;
    v22 = L"Error from BCryptSetProperty(BCRYPT_CHAINING_MODE)";
    goto LABEL_39;
  }
  pcbResult = 4;
  Property = BCryptGetProperty(g_hAesProv, L"ObjectLength", &g_cbCryptoKeyCNG, 4u, &pcbResult, 0);
  if ( Property )
  {
    v20 = Property;
    v21 = 195;
    v22 = L"Error from BCryptGetProperty(BCRYPT_OBJECT_LENGTH)";
    goto LABEL_39;
  }
  g_pbCryptoKeyCNG = (unsigned __int8 *)operator new[](*(unsigned int *)&g_cbCryptoKeyCNG);
  if ( !g_pbCryptoKeyCNG )
  {
    v10 = L"Couldn't allocate memory for CNG Key object";
    v11 = 204;
    goto LABEL_17;
  }
  v25 = BCryptImportKey(
          g_hAesProv,
          0,
          L"KeyDataBlob",
          &g_hKeyCNG,
          g_pbCryptoKeyCNG,
          *(ULONG *)&g_cbCryptoKeyCNG,
          v2,
          v15,
          0);
  if ( v25 )
  {
    v20 = v25;
    v21 = 222;
    v22 = L"Error from BCryptImportKey";
LABEL_39:
    XATmSecurityKeyCNGSize = v20 | 0x10000000;
    TraceStringInline(
      11,
      1,
      L"com\\complus\\dtc\\dtc\\xatm\\src\\xatmcrypt.cpp",
      v21,
      L"InitCryptoKey",
      XATmSecurityKeyCNGSize,
      v22);
  }
LABEL_41:
  if ( StringUuid )
    v4 = RpcStringFreeW(&StringUuid);
  if ( v4 )
    DtcInternalErrorW(L"InitCryptoKey (com\\complus\\dtc\\dtc\\xatm\\src\\xatmcrypt.cpp@233): Deallocation of string Uuid failed.");
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( v2 )
    operator delete(v2);
  return (unsigned int)XATmSecurityKeyCNGSize;
}

```

## disassembly

```asm
0x18009bf70  push    rbp
0x18009bf72  push    rbx
0x18009bf73  push    rsi
0x18009bf74  push    rdi
0x18009bf75  push    r12
0x18009bf77  push    r13
0x18009bf79  push    r14
0x18009bf7b  push    r15
0x18009bf7d  lea     rbp, [rsp-188h]
0x18009bf85  sub     rsp, 288h
0x18009bf8c  mov     rax, cs:__security_cookie
0x18009bf93  xor     rax, rsp
0x18009bf96  mov     [rbp+1C0h+var_50], rax
0x18009bf9d  xor     r13d, r13d
0x18009bfa0  lea     rdx, [rsp+2C0h+StringUuid]; StringUuid
0x18009bfa5  mov     r15, rcx
0x18009bfa8  mov     [rsp+2C0h+StringUuid], r13
0x18009bfad  lea     rcx, ?g_guidXATM@@3U_GUID@@A; Uuid
0x18009bfb4  mov     [rsp+2C0h+phAlgorithm], r13
0x18009bfb9  mov     esi, r13d
0x18009bfbc  mov     [rsp+2C0h+cbInput], r13d
0x18009bfc1  call    cs:__imp_UuidToStringW
0x18009bfc7  mov     r14d, eax
0x18009bfca  test    eax, eax
0x18009bfcc  jg      short loc_18009BFD2
0x18009bfce  mov     ebx, eax
0x18009bfd0  jmp     short loc_18009BFDB
0x18009bfd2  movzx   ebx, ax
0x18009bfd5  or      ebx, 80070000h
0x18009bfdb  test    ebx, ebx
0x18009bfdd  jns     short loc_18009BFF5
0x18009bfdf  mov     r9d, 4Eh ; 'N'
0x18009bfe5  lea     rax, aErrorFromUuidt; "Error from UuidToStringW"
0x18009bfec  lea     edx, [r9-4Dh]
0x18009bff0  jmp     loc_18009C457
0x18009bff5  mov     edi, 1
0x18009bffa  test    r15, r15
0x18009bffd  jnz     short loc_18009C009
0x18009bfff  mov     ebx, 80070057h
0x18009c004  jmp     loc_18009C0AF
0x18009c009  mov     r12, [rsp+2C0h+StringUuid]
0x18009c00e  test    r12, r12
0x18009c011  jz      short loc_18009BFFF
0x18009c013  mov     rax, [r15]
0x18009c016  lea     rcx, [rsp+2C0h+var_260]
0x18009c01b  mov     qword ptr [rsp+2C0h+cbMultiByte], rcx
0x18009c020  lea     r9, [rsp+2C0h+var_26C]
0x18009c025  lea     rcx, [rsp+2C0h+WideCharStr]
0x18009c02a  mov     [rsp+2C0h+var_26C], edi
0x18009c02e  mov     [rsp+2C0h+lpMultiByteStr], rcx
0x18009c033  lea     rdx, aSecurityXakey; "Security\\XAKey"
0x18009c03a  mov     rax, [rax+190h]
0x18009c041  mov     rcx, r15
0x18009c044  mov     r8, r12
0x18009c047  mov     [rsp+2C0h+var_260], 200h
0x18009c04f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c054  mov     ecx, 80000000h
0x18009c059  mov     ebx, eax
0x18009c05b  add     eax, ecx
0x18009c05d  test    ecx, eax
0x18009c05f  jnz     short loc_18009C0C1
0x18009c061  cmp     ebx, 80070002h
0x18009c067  jz      short loc_18009C0C1
0x18009c069  mov     qword ptr [rsp+2C0h+dwFlags], r12
0x18009c06e  lea     rax, aSecurityXakey; "Security\\XAKey"
0x18009c075  mov     [rsp+2C0h+lpUsedDefaultChar], rax
0x18009c07a  lea     r8, aComComplusDtcS; "com\\complus\\dtc\\shared\\util\\xasecu"...
0x18009c081  lea     rax, aErrorFromItmin_0; "Error from ITmInstance::GetRegistryValu"...
0x18009c088  mov     r9d, 165h
0x18009c08e  mov     [rsp+2C0h+lpDefaultChar], rax
0x18009c093  mov     edx, edi
0x18009c095  lea     rax, aGetxatmsecurit_1; "GetXATmSecurityKey"
0x18009c09c  mov     [rsp+2C0h+cbMultiByte], ebx
0x18009c0a0  mov     ecx, 7
0x18009c0a5  mov     [rsp+2C0h+lpMultiByteStr], rax
0x18009c0aa  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18009c0af  lea     rax, aErrorFromGetxa_1; "Error from GetXATmSecurityKey"
0x18009c0b6  mov     r9d, 5Ah ; 'Z'
0x18009c0bc  jmp     loc_18009C455
0x18009c0c1  mov     r9d, [rsp+2C0h+var_260]
0x18009c0c6  lea     rax, MultiByteStr
0x18009c0cd  mov     [rsp+2C0h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x18009c0d2  lea     r8, [rsp+2C0h+WideCharStr]; lpWideCharStr
0x18009c0d7  mov     [rsp+2C0h+lpDefaultChar], r13; lpDefaultChar
0x18009c0dc  xor     edx, edx; dwFlags
0x18009c0de  shr     r9d, 1; cchWideChar
0x18009c0e1  xor     ecx, ecx; CodePage
0x18009c0e3  mov     [rsp+2C0h+cbMultiByte], 100h; cbMultiByte
0x18009c0eb  mov     [rsp+2C0h+lpMultiByteStr], rax; lpMultiByteStr
0x18009c0f0  call    cs:__imp_WideCharToMultiByte
0x18009c0f6  mov     rdx, [rsp+2C0h+StringUuid]; unsigned __int16 *
0x18009c0fb  lea     r8, [rsp+2C0h+cbInput]; unsigned int *
0x18009c100  mov     rcx, r15; struct ITmInstance *
0x18009c103  call    ?GetXATmSecurityKeyCNGSize@@YAJPEAUITmInstance@@PEAGPEAK@Z; GetXATmSecurityKeyCNGSize(ITmInstance *,ushort *,ulong *)
0x18009c108  mov     ebx, eax
0x18009c10a  test    eax, eax
0x18009c10c  jns     short loc_18009C120
0x18009c10e  lea     rax, aErrorFromGetxa_0; "Error from GetXATmSecurityKeyCNGSize"
0x18009c115  mov     r9d, 6Fh ; 'o'
0x18009c11b  jmp     loc_18009C455
0x18009c120  mov     ebx, [rsp+2C0h+cbInput]
0x18009c124  mov     ecx, ebx; unsigned __int64
0x18009c126  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18009c12b  mov     rsi, rax
0x18009c12e  test    rax, rax
0x18009c131  jnz     short loc_18009C155
0x18009c133  lea     rax, aUnableToAlloca; "Unable to allocate memory for XATM Secu"...
0x18009c13a  lea     r9d, [rsi+78h]
0x18009c13e  mov     ecx, 8007000Eh
0x18009c143  mov     [rsp+2C0h+lpDefaultChar], rax
0x18009c148  mov     [rsp+2C0h+cbMultiByte], ecx
0x18009c14c  mov     ebx, ecx
0x18009c14e  mov     edx, edi
0x18009c150  jmp     loc_18009C460
0x18009c155  mov     r13, [rsp+2C0h+StringUuid]
0x18009c15a  test    r13, r13
0x18009c15d  jnz     short loc_18009C169
0x18009c15f  mov     ebx, 80070057h
0x18009c164  jmp     loc_18009C274
0x18009c169  mov     edx, 5
0x18009c16e  lea     rax, aEnteringMethod; "Entering method"
0x18009c175  mov     [rsp+2C0h+lpDefaultChar], rax
0x18009c17a  lea     r8, aComComplusDtcS; "com\\complus\\dtc\\shared\\util\\xasecu"...
0x18009c181  lea     rax, aGetxatmsecurit_0; "GetXATmSecurityKeyCNG"
0x18009c188  mov     qword ptr [rsp+2C0h+cbMultiByte], 0
0x18009c191  mov     r9d, 20Ch
0x18009c197  mov     [rsp+2C0h+lpMultiByteStr], rax
0x18009c19c  lea     r12d, [rdx+2]
0x18009c1a0  mov     ecx, r12d
0x18009c1a3  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18009c1a8  mov     rax, [r15]
0x18009c1ab  lea     rcx, [rsp+2C0h+cbInput]
0x18009c1b0  mov     qword ptr [rsp+2C0h+cbMultiByte], rcx
0x18009c1b5  lea     r9, [rsp+2C0h+var_26C]
0x18009c1ba  mov     r8, r13
0x18009c1bd  mov     [rsp+2C0h+var_26C], 3
0x18009c1c5  lea     rdx, aSecurityXakeyc; "Security\\XAKeyCNGKeyDataBlob"
0x18009c1cc  mov     [rsp+2C0h+cbInput], ebx
0x18009c1d0  mov     rax, [rax+190h]
0x18009c1d7  mov     rcx, r15
0x18009c1da  mov     [rsp+2C0h+lpMultiByteStr], rsi
0x18009c1df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c1e4  mov     r15d, [rsp+2C0h+cbInput]
0x18009c1e9  mov     ebx, eax
0x18009c1eb  test    eax, eax
0x18009c1ed  jns     short loc_18009C233
0x18009c1ef  mov     qword ptr [rsp+2C0h+dwFlags], r13
0x18009c1f4  lea     rax, aSecurityXakeyc; "Security\\XAKeyCNGKeyDataBlob"
0x18009c1fb  mov     [rsp+2C0h+lpUsedDefaultChar], rax
0x18009c200  lea     r8, aComComplusDtcS; "com\\complus\\dtc\\shared\\util\\xasecu"...
0x18009c207  lea     rax, aErrorFromItmin; "Error from ITmInstance::GetRegistryValu"...
0x18009c20e  mov     r9d, 21Ch
0x18009c214  mov     [rsp+2C0h+lpDefaultChar], rax
0x18009c219  mov     edx, edi
0x18009c21b  lea     rax, aGetxatmsecurit_0; "GetXATmSecurityKeyCNG"
0x18009c222  mov     [rsp+2C0h+cbMultiByte], ebx
0x18009c226  mov     ecx, r12d
0x18009c229  mov     [rsp+2C0h+lpMultiByteStr], rax
0x18009c22e  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18009c233  mov     dword ptr [rsp+2C0h+lpUsedDefaultChar], ebx
0x18009c237  lea     rax, aExitingMethodH; "Exiting method, hr = 0x%x"
0x18009c23e  mov     [rsp+2C0h+lpDefaultChar], rax
0x18009c243  lea     r8, aComComplusDtcS; "com\\complus\\dtc\\shared\\util\\xasecu"...
0x18009c24a  xor     r13d, r13d
0x18009c24d  lea     rax, aGetxatmsecurit_0; "GetXATmSecurityKeyCNG"
0x18009c254  mov     qword ptr [rsp+2C0h+cbMultiByte], r13
0x18009c259  mov     r9d, 22Ah
0x18009c25f  mov     ecx, r12d
0x18009c262  mov     [rsp+2C0h+lpMultiByteStr], rax
0x18009c267  lea     edx, [r13+5]
0x18009c26b  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18009c270  test    ebx, ebx
0x18009c272  jns     short loc_18009C286
0x18009c274  lea     rax, aErrorFromGetxa; "Error from GetXATmSecurityKeyCNG"
0x18009c27b  mov     r9d, 7Fh
0x18009c281  jmp     loc_18009C455
0x18009c286  lea     r12, pszAlgId; "RNG"
0x18009c28d  xor     r9d, r9d; dwFlags
0x18009c290  mov     rdx, r12; pszAlgId
0x18009c293  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18009c29a  lea     rcx, [rsp+2C0h+phAlgorithm]; phAlgorithm
0x18009c29f  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18009c2a5  test    eax, eax
0x18009c2a7  jz      short loc_18009C2EE
0x18009c2a9  mov     r9d, 8Dh
0x18009c2af  mov     ebx, eax
0x18009c2b1  mov     [rsp+2C0h+lpUsedDefaultChar], r12
0x18009c2b6  lea     rax, aErrorFromBcryp; "Error from BCryptOpenAlgorithmProvider("...
0x18009c2bd  bts     ebx, 1Ch
0x18009c2c1  mov     [rsp+2C0h+lpDefaultChar], rax
0x18009c2c6  lea     r8, aComComplusDtcD_9; "com\\complus\\dtc\\dtc\\xatm\\src\\xatm"...
0x18009c2cd  lea     rax, aInitcryptokey; "InitCryptoKey"
0x18009c2d4  mov     [rsp+2C0h+cbMultiByte], ebx
0x18009c2d8  mov     edx, edi
0x18009c2da  mov     [rsp+2C0h+lpMultiByteStr], rax
0x18009c2df  mov     ecx, 0Bh
0x18009c2e4  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18009c2e9  jmp     loc_18009C47D
0x18009c2ee  mov     rcx, [rsp+2C0h+phAlgorithm]; hAlgorithm
0x18009c2f3  lea     rdx, ?g_bInitVectorCNG@@3PAEA; pbBuffer
0x18009c2fa  xor     r9d, r9d; dwFlags
0x18009c2fd  lea     r8d, [r9+10h]; cbBuffer
0x18009c301  call    cs:__imp_BCryptGenRandom
0x18009c307  test    eax, eax
0x18009c309  jz      short loc_18009C31F
0x18009c30b  mov     ebx, eax
0x18009c30d  mov     r9d, 99h
0x18009c313  lea     rax, aErrorFromBcryp_4; "Error from BCryptGenRandom"
0x18009c31a  jmp     loc_18009C451
0x18009c31f  lea     r12, aAes; "AES"
0x18009c326  xor     r9d, r9d; dwFlags
0x18009c329  mov     rdx, r12; pszAlgId
0x18009c32c  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18009c333  lea     rcx, ?g_hAesProv@@3PEAXEA; phAlgorithm
0x18009c33a  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18009c340  test    eax, eax
0x18009c342  jz      short loc_18009C34F
0x18009c344  mov     r9d, 0A5h
0x18009c34a  jmp     loc_18009C2AF
0x18009c34f  mov     rcx, cs:?g_hAesProv@@3PEAXEA; hObject
0x18009c356  lea     r8, pbInput; "ChainingModeCBC"
0x18009c35d  mov     r9d, 20h ; ' '; cbInput
0x18009c363  mov     dword ptr [rsp+2C0h+lpMultiByteStr], r13d; dwFlags
0x18009c368  lea     rdx, pszProperty; "ChainingMode"
0x18009c36f  call    cs:__imp_BCryptSetProperty
0x18009c375  test    eax, eax
0x18009c377  jz      short loc_18009C38D
0x18009c379  mov     ebx, eax
0x18009c37b  mov     r9d, 0B3h
0x18009c381  lea     rax, aErrorFromBcryp_2; "Error from BCryptSetProperty(BCRYPT_CHA"...
0x18009c388  jmp     loc_18009C451
0x18009c38d  mov     rcx, cs:?g_hAesProv@@3PEAXEA; hObject
0x18009c394  lea     rax, [rsp+2C0h+pcbResult]
0x18009c399  mov     r9d, 4; cbOutput
0x18009c39f  mov     [rsp+2C0h+cbMultiByte], r13d; dwFlags
0x18009c3a4  lea     r8, ?g_cbCryptoKeyCNG@@3KA; pbOutput
0x18009c3ab  mov     [rsp+2C0h+pcbResult], r9d
0x18009c3b0  lea     rdx, aObjectlength; "ObjectLength"
0x18009c3b7  mov     [rsp+2C0h+lpMultiByteStr], rax; pcbResult
0x18009c3bc  call    cs:__imp_BCryptGetProperty
0x18009c3c2  test    eax, eax
0x18009c3c4  jz      short loc_18009C3D7
0x18009c3c6  mov     ebx, eax
0x18009c3c8  mov     r9d, 0C3h
0x18009c3ce  lea     rax, aErrorFromBcryp_1; "Error from BCryptGetProperty(BCRYPT_OBJ"...
0x18009c3d5  jmp     short loc_18009C451
0x18009c3d7  mov     ecx, cs:?g_cbCryptoKeyCNG@@3KA; unsigned __int64
0x18009c3dd  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18009c3e2  mov     cs:?g_pbCryptoKeyCNG@@3PEAEEA, rax; uchar * g_pbCryptoKeyCNG
0x18009c3e9  mov     rcx, rax
0x18009c3ec  test    rax, rax
0x18009c3ef  jnz     short loc_18009C403
0x18009c3f1  lea     rax, aCouldnTAllocat; "Couldn't allocate memory for CNG Key ob"...
0x18009c3f8  mov     r9d, 0CCh
0x18009c3fe  jmp     loc_18009C13E
0x18009c403  mov     eax, cs:?g_cbCryptoKeyCNG@@3KA; ulong g_cbCryptoKeyCNG
0x18009c409  lea     r9, ?g_hKeyCNG@@3PEAXEA; phKey
0x18009c410  mov     [rsp+2C0h+dwFlags], r13d; dwFlags
0x18009c415  lea     r8, pszBlobType; "KeyDataBlob"
0x18009c41c  mov     dword ptr [rsp+2C0h+lpUsedDefaultChar], r15d; cbInput
0x18009c421  xor     edx, edx; hImportKey
0x18009c423  mov     [rsp+2C0h+lpDefaultChar], rsi; pbInput
0x18009c428  mov     [rsp+2C0h+cbMultiByte], eax; cbKeyObject
0x18009c42c  mov     [rsp+2C0h+lpMultiByteStr], rcx; pbKeyObject
0x18009c431  mov     rcx, cs:?g_hAesProv@@3PEAXEA; hAlgorithm
0x18009c438  call    cs:__imp_BCryptImportKey
0x18009c43e  test    eax, eax
0x18009c440  jz      short loc_18009C47D
0x18009c442  mov     ebx, eax
0x18009c444  mov     r9d, 0DEh
0x18009c44a  lea     rax, aErrorFromBcryp_3; "Error from BCryptImportKey"
0x18009c451  bts     ebx, 1Ch
0x18009c455  mov     edx, edi
0x18009c457  mov     [rsp+2C0h+lpDefaultChar], rax
0x18009c45c  mov     [rsp+2C0h+cbMultiByte], ebx
0x18009c460  lea     rax, aInitcryptokey; "InitCryptoKey"
0x18009c467  mov     ecx, 0Bh
0x18009c46c  lea     r8, aComComplusDtcD_9; "com\\complus\\dtc\\dtc\\xatm\\src\\xatm"...
0x18009c473  mov     [rsp+2C0h+lpMultiByteStr], rax
0x18009c478  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18009c47d  cmp     [rsp+2C0h+StringUuid], r13
0x18009c482  jz      short loc_18009C492
0x18009c484  lea     rcx, [rsp+2C0h+StringUuid]; String
0x18009c489  call    cs:__imp_RpcStringFreeW
0x18009c48f  mov     r14d, eax
0x18009c492  test    r14d, r14d
0x18009c495  jz      short loc_18009C4A4
0x18009c497  lea     rcx, aInitcryptokeyC; "InitCryptoKey (com\\complus\\dtc\\dtc\\"...
0x18009c49e  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18009c4a4  mov     rcx, [rsp+2C0h+phAlgorithm]; hAlgorithm
0x18009c4a9  test    rcx, rcx
0x18009c4ac  jz      short loc_18009C4B6
0x18009c4ae  xor     edx, edx; dwFlags
0x18009c4b0  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18009c4b6  test    rsi, rsi
0x18009c4b9  jz      short loc_18009C4C3
0x18009c4bb  mov     rcx, rsi; Block
0x18009c4be  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18009c4c3  mov     eax, ebx
0x18009c4c5  mov     rcx, [rbp+1C0h+var_50]
  ... truncated ...
```
