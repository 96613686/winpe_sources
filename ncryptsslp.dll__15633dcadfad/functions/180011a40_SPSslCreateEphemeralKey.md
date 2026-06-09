# SPSslCreateEphemeralKey

- ea: `0x180011a40`
- end: `0x180011da2`
- name: `SPSslCreateEphemeralKey`
- size: `866`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005e50`
- `0x1800068e0`
- `0x18000b654`
- `0x180011a40`
- `0x180011db0`
- `0x180013950`
- `0x180021b60`
- `0x180024ef0`
- `0x180025660`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180011bf1`
- `ntdll!RtlReleaseResource` at `0x180011cf7`
- `ntdll!RtlReleaseResource` at `0x180011bf1`
- `ntdll!RtlReleaseResource` at `0x180011cf7`
- `ntdll!RtlAcquireResourceShared` at `0x180011b3e`
- `ntdll!RtlAcquireResourceShared` at `0x180011b3e`

## string_xrefs

- `0x180011c83`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180011cb0`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180011d13`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180011d3d`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslCreateEphemeralKey(
        __int64 a1,
        _QWORD *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        BYTE a6,
        BYTE *a7,
        DWORD a8,
        int a9)
{
  wchar_t *v13; // rax
  __int64 v14; // rax
  int v15; // ecx
  int v16; // r8d
  int v17; // ecx
  int v18; // ecx
  _OWORD *v19; // rax
  const WCHAR *v20; // rdx
  int KemKey; // ebx
  __int64 v23; // r9
  __int64 v24; // r9
  __int64 v25; // r9
  __int64 v26[2]; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v27[32]; // [rsp+50h] [rbp-B0h] BYREF

  v26[0] = 0;
  memset(v27, 0, 0x1FEu);
  if ( !SslpValidateProvHandle(a1) )
  {
    DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", 1136);
    return 2148073510LL;
  }
  if ( !a2 )
  {
    v23 = 1143;
LABEL_21:
    DebugTraceError(2148073511LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v23);
    return 2148073511LL;
  }
  if ( (a9 & 0xFFFFFFFD) != 0 )
  {
    v23 = 1150;
    goto LABEL_21;
  }
  if ( a5 - 512 <= 2 )
  {
    switch ( a5 )
    {
      case 0x200u:
        v13 = (wchar_t *)L"512";
        break;
      case 0x201u:
        v13 = (wchar_t *)L"768";
        break;
      case 0x202u:
        v13 = (wchar_t *)L"1024";
        break;
      default:
        v24 = 1186;
        goto LABEL_31;
    }
    KemKey = SslpCreateKemKey(v26, L"ML-KEM", 458753, a5, (PBYTE)v13, a9);
    if ( KemKey < 0 )
    {
      v25 = 1272;
      goto LABEL_27;
    }
    goto LABEL_15;
  }
  v14 = LookupCipherSuite(a3, a4);
  if ( !v14 )
  {
    v24 = 1198;
    goto LABEL_31;
  }
  v15 = *(_DWORD *)(v14 + 88);
  if ( v15 )
  {
    v16 = 196609;
    v17 = v15 - 196609;
    if ( v17 )
    {
      v18 = v17 - 1;
      if ( v18 )
      {
        if ( v18 != 8 )
        {
          v24 = 1255;
          goto LABEL_31;
        }
        goto LABEL_12;
      }
      v16 = 196610;
      v20 = L"DH";
    }
    else
    {
      v20 = L"RSA";
    }
LABEL_14:
    KemKey = SslpCreateEphemeralKey(v26, v20, v16, a5, (PBYTE)v27, a6, a7, a8);
    if ( KemKey < 0 )
    {
      v25 = 1289;
LABEL_27:
      DebugTraceError(
        (unsigned int)KemKey,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        v25);
      return (unsigned int)KemKey;
    }
LABEL_15:
    *a2 = v26[0];
    return (unsigned int)KemKey;
  }
LABEL_12:
  RtlAcquireResourceShared(&g_EccCurvesRWLock, 1u);
  v19 = (_OWORD *)LookupEccCurveByCurveType(a5);
  if ( v19 )
  {
    v27[0] = *v19;
    v27[1] = v19[1];
    v27[2] = v19[2];
    v27[3] = v19[3];
    v27[4] = v19[4];
    v27[5] = v19[5];
    v27[6] = v19[6];
    v27[7] = v19[7];
    v27[8] = v19[8];
    v27[9] = v19[9];
    v27[10] = v19[10];
    v27[11] = v19[11];
    v27[12] = v19[12];
    v27[13] = v19[13];
    v27[14] = v19[14];
    *(_OWORD *)((char *)&v27[14] + 15) = *(_OWORD *)((char *)v19 + 239);
    RtlReleaseResource(&g_EccCurvesRWLock);
    v16 = 196618;
    v20 = L"ECDH";
    goto LABEL_14;
  }
  RtlReleaseResource(&g_EccCurvesRWLock);
  v24 = 1235;
LABEL_31:
  DebugTraceError(2148073513LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v24);
  return 2148073513LL;
}

```

## disassembly

```asm
0x180011a40  mov     [rsp-8+arg_0], rbx
0x180011a45  mov     [rsp-8+arg_10], rsi
0x180011a4a  push    rbp
0x180011a4b  push    rdi
0x180011a4c  push    r12
0x180011a4e  push    r14
0x180011a50  push    r15
0x180011a52  lea     rbp, [rsp-160h]
0x180011a5a  sub     rsp, 260h
0x180011a61  mov     rax, cs:__security_cookie
0x180011a68  xor     rax, rsp
0x180011a6b  mov     [rbp+180h+var_30], rax
0x180011a72  mov     edi, [rbp+180h+arg_20]
0x180011a78  mov     r15d, r8d
0x180011a7b  mov     r12, [rbp+180h+arg_30]
0x180011a82  mov     rsi, rdx
0x180011a85  mov     rbx, rcx
0x180011a88  mov     [rsp+280h+var_240], 0
0x180011a91  xor     edx, edx; Val
0x180011a93  lea     rcx, [rsp+280h+var_230]; void *
0x180011a98  mov     r8d, 1FEh; Size
0x180011a9e  mov     r14d, r9d
0x180011aa1  call    memset
0x180011aa6  mov     rcx, rbx
0x180011aa9  call    SslpValidateProvHandle
0x180011aae  test    rax, rax
0x180011ab1  jz      loc_180011C7D
0x180011ab7  test    rsi, rsi
0x180011aba  jz      loc_180011CA2
0x180011ac0  mov     ecx, [rbp+180h+arg_40]
0x180011ac6  test    ecx, 0FFFFFFFDh
0x180011acc  jnz     loc_180011CAA
0x180011ad2  lea     eax, [rdi-200h]
0x180011ad8  cmp     eax, 2
0x180011adb  ja      short loc_180011AF6
0x180011add  mov     eax, edi
0x180011adf  sub     eax, 200h
0x180011ae4  jnz     loc_180011D2D
0x180011aea  lea     rax, a512; "512"
0x180011af1  jmp     loc_180011D6F
0x180011af6  mov     edx, r14d
0x180011af9  mov     ecx, r15d
0x180011afc  call    LookupCipherSuite
0x180011b01  test    rax, rax
0x180011b04  jz      loc_180011CD2
0x180011b0a  mov     ecx, [rax+58h]
0x180011b0d  test    ecx, ecx
0x180011b0f  jz      short loc_180011B32
0x180011b11  mov     r8d, 30001h
0x180011b17  sub     ecx, r8d
0x180011b1a  jz      loc_180011C74
0x180011b20  sub     ecx, 1
0x180011b23  jz      loc_180011CE2
0x180011b29  cmp     ecx, 8
0x180011b2c  jnz     loc_180011CDA
0x180011b32  lea     rbx, g_EccCurvesRWLock
0x180011b39  mov     dl, 1; Wait
0x180011b3b  mov     rcx, rbx; Resource
0x180011b3e  call    cs:__imp_RtlAcquireResourceShared
0x180011b44  mov     ecx, edi
0x180011b46  call    LookupEccCurveByCurveType
0x180011b4b  test    rax, rax
0x180011b4e  jz      loc_180011CF4
0x180011b54  movups  xmm0, xmmword ptr [rax]
0x180011b57  mov     rcx, rbx; Resource
0x180011b5a  movups  [rsp+280h+var_230], xmm0
0x180011b5f  movups  xmm1, xmmword ptr [rax+10h]
0x180011b63  movups  [rsp+280h+var_220], xmm1
0x180011b68  movups  xmm0, xmmword ptr [rax+20h]
0x180011b6c  movups  [rsp+280h+var_210], xmm0
0x180011b71  movups  xmm1, xmmword ptr [rax+30h]
0x180011b75  movups  [rbp+180h+var_200], xmm1
0x180011b79  movups  xmm0, xmmword ptr [rax+40h]
0x180011b7d  movups  [rbp+180h+var_1F0], xmm0
0x180011b81  movups  xmm1, xmmword ptr [rax+50h]
0x180011b85  movups  [rbp+180h+var_1E0], xmm1
0x180011b89  movups  xmm0, xmmword ptr [rax+60h]
0x180011b8d  movups  [rbp+180h+var_1D0], xmm0
0x180011b91  movups  xmm1, xmmword ptr [rax+70h]
0x180011b95  movups  [rbp+180h+var_1C0], xmm1
0x180011b99  movups  xmm0, xmmword ptr [rax+80h]
0x180011ba0  movups  [rbp+180h+var_1B0], xmm0
0x180011ba4  movups  xmm1, xmmword ptr [rax+90h]
0x180011bab  movups  [rbp+180h+var_1A0], xmm1
0x180011baf  movups  xmm0, xmmword ptr [rax+0A0h]
0x180011bb6  movups  [rbp+180h+var_190], xmm0
0x180011bba  movups  xmm1, xmmword ptr [rax+0B0h]
0x180011bc1  movups  [rbp+180h+var_180], xmm1
0x180011bc5  movups  xmm0, xmmword ptr [rax+0C0h]
0x180011bcc  movups  [rbp+180h+var_170], xmm0
0x180011bd0  movups  xmm1, xmmword ptr [rax+0D0h]
0x180011bd7  movups  [rbp+180h+var_160], xmm1
0x180011bdb  movups  xmm0, xmmword ptr [rax+0E0h]
0x180011be2  movups  [rbp+180h+var_150], xmm0
0x180011be6  movups  xmm1, xmmword ptr [rax+0EFh]
0x180011bed  movups  [rbp+180h+var_150+0Fh], xmm1
0x180011bf1  call    cs:__imp_RtlReleaseResource
0x180011bf7  mov     r8d, 3000Ah
0x180011bfd  lea     rdx, aEcdh; "ECDH"
0x180011c04  mov     eax, [rbp+180h+arg_38]
0x180011c0a  lea     rcx, [rsp+280h+var_240]
0x180011c0f  mov     [rsp+280h+var_248], eax
0x180011c13  movzx   r9d, di
0x180011c17  mov     eax, dword ptr [rbp+180h+arg_28]
0x180011c1d  mov     [rsp+280h+var_250], r12
0x180011c22  mov     [rsp+280h+var_258], eax
0x180011c26  lea     rax, [rsp+280h+var_230]
0x180011c2b  mov     [rsp+280h+var_260], rax
0x180011c30  call    SslpCreateEphemeralKey
0x180011c35  mov     ebx, eax
0x180011c37  test    eax, eax
0x180011c39  js      loc_180011D05
0x180011c3f  mov     rax, [rsp+280h+var_240]
0x180011c44  mov     [rsi], rax
0x180011c47  mov     eax, ebx
0x180011c49  mov     rcx, [rbp+180h+var_30]
0x180011c50  xor     rcx, rsp; StackCookie
0x180011c53  call    __security_check_cookie
0x180011c58  lea     r11, [rsp+280h+var_20]
0x180011c60  mov     rbx, [r11+30h]
0x180011c64  mov     rsi, [r11+40h]
0x180011c68  mov     rsp, r11
0x180011c6b  pop     r15
0x180011c6d  pop     r14
0x180011c6f  pop     r12
0x180011c71  pop     rdi
0x180011c72  pop     rbp
0x180011c73  retn
0x180011c74  lea     rdx, aRsa; "RSA"
0x180011c7b  jmp     short loc_180011C04
0x180011c7d  mov     r9d, 470h
0x180011c83  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011c8a  lea     rdx, aStatus; "Status"
0x180011c91  mov     ecx, 80090026h
0x180011c96  call    DebugTraceError
0x180011c9b  mov     eax, 80090026h
0x180011ca0  jmp     short loc_180011C49
0x180011ca2  mov     r9d, 477h
0x180011ca8  jmp     short loc_180011CB0
0x180011caa  mov     r9d, 47Eh
0x180011cb0  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011cb7  mov     ecx, 80090027h
0x180011cbc  lea     rdx, aStatus; "Status"
0x180011cc3  call    DebugTraceError
0x180011cc8  mov     eax, 80090027h
0x180011ccd  jmp     loc_180011C49
0x180011cd2  mov     r9d, 4AEh
0x180011cd8  jmp     short loc_180011D3D
0x180011cda  mov     r9d, 4E7h
0x180011ce0  jmp     short loc_180011D3D
0x180011ce2  mov     r8d, 30002h
0x180011ce8  lea     rdx, aDh; "DH"
0x180011cef  jmp     loc_180011C04
0x180011cf4  mov     rcx, rbx; Resource
0x180011cf7  call    cs:__imp_RtlReleaseResource
0x180011cfd  mov     r9d, 4D3h
0x180011d03  jmp     short loc_180011D3D
0x180011d05  mov     r9d, 509h
0x180011d0b  jmp     short loc_180011D13
0x180011d0d  mov     r9d, 4F8h
0x180011d13  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011d1a  mov     ecx, ebx
0x180011d1c  lea     rdx, aStatus; "Status"
0x180011d23  call    DebugTraceError
0x180011d28  jmp     loc_180011C47
0x180011d2d  sub     eax, 1
0x180011d30  jz      short loc_180011D68
0x180011d32  cmp     eax, 1
0x180011d35  jz      short loc_180011D5F
0x180011d37  mov     r9d, 4A2h
0x180011d3d  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011d44  mov     ecx, 80090029h
0x180011d49  lea     rdx, aStatus; "Status"
0x180011d50  call    DebugTraceError
0x180011d55  mov     eax, 80090029h
0x180011d5a  jmp     loc_180011C49
0x180011d5f  lea     rax, a1024; "1024"
0x180011d66  jmp     short loc_180011D6F
0x180011d68  lea     rax, a768; "768"
0x180011d6f  mov     [rsp+280h+var_258], ecx
0x180011d73  lea     rdx, aMlKem; "ML-KEM"
0x180011d7a  lea     rcx, [rsp+280h+var_240]
0x180011d7f  mov     [rsp+280h+var_260], rax
0x180011d84  movzx   r9d, di
0x180011d88  mov     r8d, 70001h
0x180011d8e  call    SslpCreateKemKey
0x180011d93  mov     ebx, eax
0x180011d95  test    eax, eax
0x180011d97  jns     loc_180011C3F
0x180011d9d  jmp     loc_180011D0D
```
