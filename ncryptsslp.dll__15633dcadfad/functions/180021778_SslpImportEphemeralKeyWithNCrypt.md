# SslpImportEphemeralKeyWithNCrypt

- ea: `0x180021778`
- end: `0x180021a6b`
- name: `SslpImportEphemeralKeyWithNCrypt`
- size: `755`
- prototype: `__int64 __fastcall(PBYTE pbData, DWORD cbData, LPCWSTR pszBlobType, _QWORD *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001010`
- `0x1800234b0`

## callees

- `0x18000b654`
- `0x180011db0`
- `0x180013b80`
- `0x180013e6c`
- `0x1800185e0`
- `0x180021778`
- `0x180024ef0`
- `0x180024fb0`

## import_xrefs

- `ncrypt!NCryptImportKey` at `0x1800219ef`
- `ncrypt!NCryptImportKey` at `0x1800219ef`
- `ntdll!RtlReleaseResource` at `0x18002187a`
- `ntdll!RtlReleaseResource` at `0x1800218d1`
- `ntdll!RtlReleaseResource` at `0x18002187a`
- `ntdll!RtlReleaseResource` at `0x1800218d1`
- `ntdll!RtlAcquireResourceShared` at `0x180021861`
- `ntdll!RtlAcquireResourceShared` at `0x180021861`

## string_xrefs

- `0x180021844`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlsephemeral.c`
- `0x180021a2d`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlsephemeral.c`

## pseudocode

```c
__int64 __fastcall SslpImportEphemeralKeyWithNCrypt(PBYTE pbData, DWORD cbData, LPCWSTR pszBlobType, _QWORD *a4)
{
  const wchar_t *v5; // rsi
  __int64 v8; // rdi
  unsigned __int16 v9; // bx
  __int64 v10; // rcx
  __int64 v11; // r8
  unsigned int v12; // ebx
  __int64 v13; // r9
  __int64 v14; // rcx
  _WORD *v15; // rdx
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // r9
  SECURITY_STATUS v20; // eax
  __int64 v22; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v23; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v24; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v25[512]; // [rsp+70h] [rbp-90h] BYREF

  v22 = 0;
  v5 = pszBlobType;
  v8 = 0;
  v24 = 0;
  v23 = 0;
  if ( pbData && cbData && pszBlobType && a4 )
  {
    v9 = 0;
    if ( !wcscmp(pszBlobType, L"ECCFULLPUBLICBLOB") )
    {
      v11 = 196618;
      goto LABEL_29;
    }
    if ( !wcscmp(v5, L"SSLECCPUBLICBLOB") )
    {
      if ( cbData < 8 )
      {
        v12 = -2146893819;
        v13 = 425;
        v14 = 2148073477LL;
LABEL_10:
        DebugTraceError(v14, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlsephemeral.c", v13);
        return v12;
      }
      RtlAcquireResourceShared(&g_EccCurvesRWLock, 1u);
      v15 = (_WORD *)LookupEccCurveByCurveType(*(unsigned int *)pbData);
      if ( !v15 )
      {
        RtlReleaseResource(&g_EccCurvesRWLock);
        v13 = 439;
LABEL_13:
        v12 = -2146893783;
        v14 = 2148073513LL;
        goto LABEL_10;
      }
      v9 = *(_WORD *)pbData;
      v16 = -1;
      DWORD1(v24) = 60;
      do
        ++v16;
      while ( v15[v16] );
      *((_QWORD *)&v24 + 1) = v25;
      LODWORD(v24) = 2 * v16 + 2;
      memmove(v25, v15, (unsigned int)v24);
      RtlReleaseResource(&g_EccCurvesRWLock);
      *((_QWORD *)&v23 + 1) = &v24;
      v5 = L"ECCPUBLICBLOB";
      *(_QWORD *)&v23 = 0x100000000LL;
      v11 = 196618;
      *(_DWORD *)pbData = 1347109701;
    }
    else if ( !wcscmp(v5, L"ECCPUBLICBLOB") )
    {
      switch ( *(_DWORD *)pbData )
      {
        case 0x314B4345:
          v9 = 23;
          v11 = 196615;
          break;
        case 0x334B4345:
          v9 = 24;
          v11 = 196616;
          break;
        case 0x354B4345:
          v9 = 25;
          v11 = 196617;
          break;
        default:
          v13 = 493;
          goto LABEL_13;
      }
    }
    else if ( !wcscmp(v5, L"DHPUBLICBLOB") )
    {
      v11 = 196610;
    }
    else
    {
      if ( wcscmp(v5, L"RSAPUBLICBLOB") )
      {
        v13 = 509;
        goto LABEL_13;
      }
      v11 = 196609;
    }
LABEL_29:
    v17 = SslpCreateBaseEphemeralKeyStruct(v10, v9, v11, &v22);
    v8 = v22;
    v12 = v17;
    if ( v17 >= 0 )
    {
      v20 = NCryptImportKey(
              *(_QWORD *)(v22 + 16),
              0,
              v5,
              (NCryptBufferDesc *)((unsigned __int64)&v23 & -(__int64)(DWORD1(v23) != 0)),
              (NCRYPT_KEY_HANDLE *)(v22 + 24),
              pbData,
              cbData,
              0);
      v12 = v20;
      if ( v20 >= 0 )
      {
        *a4 = v8;
        return v12;
      }
      v18 = (unsigned int)v20;
      v19 = 535;
    }
    else
    {
      v18 = (unsigned int)v17;
      v19 = 520;
    }
    goto LABEL_36;
  }
  v12 = -2146893785;
  v18 = 2148073511LL;
  v19 = 412;
LABEL_36:
  DebugTraceError(v18, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlsephemeral.c", v19);
  if ( v8 )
    SslpFreeEphemeralKey(v8);
  return v12;
}

```

## disassembly

```asm
0x180021778  push    rbp
0x18002177a  push    rbx
0x18002177b  push    rsi
0x18002177c  push    rdi
0x18002177d  push    r12
0x18002177f  push    r13
0x180021781  push    r14
0x180021783  push    r15
0x180021785  lea     rbp, [rsp-188h]
0x18002178d  sub     rsp, 288h
0x180021794  mov     rax, cs:__security_cookie
0x18002179b  xor     rax, rsp
0x18002179e  mov     [rbp+1C0h+var_50], rax
0x1800217a5  xor     r13d, r13d
0x1800217a8  xorps   xmm0, xmm0
0x1800217ab  mov     [rsp+2C0h+var_280], r13
0x1800217b0  xorps   xmm1, xmm1
0x1800217b3  mov     r12, r9
0x1800217b6  mov     rsi, r8
0x1800217b9  mov     r15d, edx
0x1800217bc  mov     r14, rcx
0x1800217bf  mov     edi, r13d
0x1800217c2  movups  [rsp+2C0h+var_268], xmm0
0x1800217c7  movups  [rsp+2C0h+var_278], xmm1
0x1800217cc  test    rcx, rcx
0x1800217cf  jz      loc_180021A16
0x1800217d5  test    edx, edx
0x1800217d7  jz      loc_180021A16
0x1800217dd  test    r8, r8
0x1800217e0  jz      loc_180021A16
0x1800217e6  test    r9, r9
0x1800217e9  jz      loc_180021A16
0x1800217ef  lea     rdx, aEccfullpublicb; "ECCFULLPUBLICBLOB"
0x1800217f6  mov     rcx, r8; String1
0x1800217f9  mov     ebx, r13d
0x1800217fc  call    wcscmp
0x180021801  test    eax, eax
0x180021803  jnz     short loc_180021810
0x180021805  mov     r8d, 3000Ah
0x18002180b  jmp     loc_18002199B
0x180021810  lea     rdx, aSsleccpublicbl; "SSLECCPUBLICBLOB"
0x180021817  mov     rcx, rsi; String1
0x18002181a  call    wcscmp
0x18002181f  test    eax, eax
0x180021821  jnz     loc_180021907
0x180021827  cmp     r15d, 8
0x18002182b  jnb     short loc_180021855
0x18002182d  mov     ebx, 80090005h
0x180021832  mov     r9d, 1A9h
0x180021838  mov     ecx, 80090005h
0x18002183d  lea     rdx, aStatus_0; "status"
0x180021844  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002184b  call    DebugTraceError
0x180021850  jmp     loc_180021A46
0x180021855  lea     rdi, g_EccCurvesRWLock
0x18002185c  mov     dl, 1; Wait
0x18002185e  mov     rcx, rdi; Resource
0x180021861  call    cs:__imp_RtlAcquireResourceShared
0x180021867  mov     ecx, [r14]
0x18002186a  call    LookupEccCurveByCurveType
0x18002186f  mov     rdx, rax; Src
0x180021872  test    rax, rax
0x180021875  jnz     short loc_180021892
0x180021877  mov     rcx, rdi; Resource
0x18002187a  call    cs:__imp_RtlReleaseResource
0x180021880  mov     r9d, 1B7h
0x180021886  mov     ebx, 80090029h
0x18002188b  mov     ecx, 80090029h
0x180021890  jmp     short loc_18002183D
0x180021892  movzx   ebx, word ptr [r14]
0x180021896  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002189a  mov     dword ptr [rsp+2C0h+var_268+4], 3Ch ; '<'
0x1800218a2  inc     rax
0x1800218a5  cmp     [rdx+rax*2], r13w
0x1800218aa  jnz     short loc_1800218A2
0x1800218ac  lea     eax, ds:2[rax*2]
0x1800218b3  lea     rcx, [rsp+2C0h+var_250]
0x1800218b8  mov     r8d, eax; Size
0x1800218bb  mov     qword ptr [rsp+2C0h+var_268+8], rcx
0x1800218c0  lea     rcx, [rsp+2C0h+var_250]; void *
0x1800218c5  mov     dword ptr [rsp+2C0h+var_268], eax
0x1800218c9  call    memmove
0x1800218ce  mov     rcx, rdi; Resource
0x1800218d1  call    cs:__imp_RtlReleaseResource
0x1800218d7  lea     rax, [rsp+2C0h+var_268]
0x1800218dc  mov     dword ptr [rsp+2C0h+var_278+4], 1
0x1800218e4  mov     qword ptr [rsp+2C0h+var_278+8], rax
0x1800218e9  lea     rsi, aEccpublicblob; "ECCPUBLICBLOB"
0x1800218f0  mov     dword ptr [rsp+2C0h+var_278], r13d
0x1800218f5  mov     r8d, 3000Ah
0x1800218fb  mov     dword ptr [r14], 504B4345h
0x180021902  jmp     loc_18002199B
0x180021907  lea     rdx, aEccpublicblob; "ECCPUBLICBLOB"
0x18002190e  mov     rcx, rsi; String1
0x180021911  call    wcscmp
0x180021916  test    eax, eax
0x180021918  jnz     short loc_180021967
0x18002191a  cmp     dword ptr [r14], 314B4345h
0x180021921  jz      short loc_18002195A
0x180021923  cmp     dword ptr [r14], 334B4345h
0x18002192a  jz      short loc_18002194D
0x18002192c  cmp     dword ptr [r14], 354B4345h
0x180021933  jz      short loc_180021940
0x180021935  mov     r9d, 1EDh
0x18002193b  jmp     loc_180021886
0x180021940  mov     ebx, 19h
0x180021945  mov     r8d, 30009h
0x18002194b  jmp     short loc_18002199B
0x18002194d  mov     ebx, 18h
0x180021952  mov     r8d, 30008h
0x180021958  jmp     short loc_18002199B
0x18002195a  mov     ebx, 17h
0x18002195f  mov     r8d, 30007h
0x180021965  jmp     short loc_18002199B
0x180021967  lea     rdx, aDhpublicblob; "DHPUBLICBLOB"
0x18002196e  mov     rcx, rsi; String1
0x180021971  call    wcscmp
0x180021976  test    eax, eax
0x180021978  jnz     short loc_180021982
0x18002197a  mov     r8d, 30002h
0x180021980  jmp     short loc_18002199B
0x180021982  lea     rdx, aRsapublicblob; "RSAPUBLICBLOB"
0x180021989  mov     rcx, rsi; String1
0x18002198c  call    wcscmp
0x180021991  test    eax, eax
0x180021993  jnz     short loc_180021A0B
0x180021995  mov     r8d, 30001h
0x18002199b  lea     r9, [rsp+2C0h+var_280]
0x1800219a0  movzx   edx, bx
0x1800219a3  call    SslpCreateBaseEphemeralKeyStruct
0x1800219a8  mov     rdi, [rsp+2C0h+var_280]
0x1800219ad  mov     ebx, eax
0x1800219af  test    eax, eax
0x1800219b1  jns     short loc_1800219BD
0x1800219b3  mov     ecx, eax
0x1800219b5  mov     r9d, 208h
0x1800219bb  jmp     short loc_180021A26
0x1800219bd  mov     eax, dword ptr [rsp+2C0h+var_278+4]
0x1800219c1  mov     r8, rsi; pszBlobType
0x1800219c4  mov     rcx, [rdi+10h]; hProvider
0x1800219c8  neg     eax
0x1800219ca  mov     [rsp+2C0h+dwFlags], r13d; dwFlags
0x1800219cf  lea     rax, [rsp+2C0h+var_278]
0x1800219d4  sbb     r9, r9
0x1800219d7  mov     [rsp+2C0h+cbData], r15d; cbData
0x1800219dc  and     r9, rax; pParameterList
0x1800219df  mov     [rsp+2C0h+pbData], r14; pbData
0x1800219e4  lea     rax, [rdi+18h]
0x1800219e8  xor     edx, edx; hImportKey
0x1800219ea  mov     [rsp+2C0h+phKey], rax; phKey
0x1800219ef  call    cs:__imp_NCryptImportKey
0x1800219f5  mov     ebx, eax
0x1800219f7  test    eax, eax
0x1800219f9  jns     short loc_180021A05
0x1800219fb  mov     ecx, eax
0x1800219fd  mov     r9d, 217h
0x180021a03  jmp     short loc_180021A26
0x180021a05  mov     [r12], rdi
0x180021a09  jmp     short loc_180021A46
0x180021a0b  mov     r9d, 1FDh
0x180021a11  jmp     loc_180021886
0x180021a16  mov     ebx, 80090027h
0x180021a1b  mov     ecx, 80090027h
0x180021a20  mov     r9d, 19Ch
0x180021a26  lea     rdx, aStatus_0; "status"
0x180021a2d  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021a34  call    DebugTraceError
0x180021a39  test    rdi, rdi
0x180021a3c  jz      short loc_180021A46
0x180021a3e  mov     rcx, rdi
0x180021a41  call    SslpFreeEphemeralKey
0x180021a46  mov     eax, ebx
0x180021a48  mov     rcx, [rbp+1C0h+var_50]
0x180021a4f  xor     rcx, rsp; StackCookie
0x180021a52  call    __security_check_cookie
0x180021a57  add     rsp, 288h
0x180021a5e  pop     r15
0x180021a60  pop     r14
0x180021a62  pop     r13
0x180021a64  pop     r12
0x180021a66  pop     rdi
0x180021a67  pop     rsi
0x180021a68  pop     rbx
0x180021a69  pop     rbp
0x180021a6a  retn
```
