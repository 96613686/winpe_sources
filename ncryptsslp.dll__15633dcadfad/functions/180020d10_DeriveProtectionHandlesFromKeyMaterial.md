# DeriveProtectionHandlesFromKeyMaterial

- ea: `0x180020d10`
- end: `0x1800210fb`
- name: `DeriveProtectionHandlesFromKeyMaterial`
- size: `1003`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001e8c0`

## callees

- `0x18000b654`
- `0x180020d10`
- `0x180021104`
- `0x180024ef0`

## import_xrefs

- `bcrypt!BCryptKeyDerivation` at `0x180020f30`
- `bcrypt!BCryptKeyDerivation` at `0x180020fb8`
- `bcrypt!BCryptKeyDerivation` at `0x180021037`
- `bcrypt!BCryptKeyDerivation` at `0x180020f30`
- `bcrypt!BCryptKeyDerivation` at `0x180020fb8`
- `bcrypt!BCryptKeyDerivation` at `0x180021037`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180020ef1`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180020f6c`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180020fef`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180020ef1`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180020f6c`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180020fef`
- `bcrypt!BCryptDestroyKey` at `0x180021068`
- `bcrypt!BCryptDestroyKey` at `0x180021081`
- `bcrypt!BCryptDestroyKey` at `0x1800210c4`
- `bcrypt!BCryptDestroyKey` at `0x180021068`
- `bcrypt!BCryptDestroyKey` at `0x180021081`
- `bcrypt!BCryptDestroyKey` at `0x1800210c4`

## string_xrefs

- `0x180020db1`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlssessionticket.c`
- `0x180020e21`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlssessionticket.c`
- `0x180020e51`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlssessionticket.c`
- `0x180021049`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlssessionticket.c`

## pseudocode

```c
__int64 __fastcall DeriveProtectionHandlesFromKeyMaterial(
        __int64 a1,
        int a2,
        UCHAR *a3,
        ULONG a4,
        BCRYPT_KEY_HANDLE *a5,
        UCHAR *pbKeyObject,
        ULONG cbKeyObject,
        _BYTE *a8,
        unsigned int a9)
{
  UCHAR *v9; // rdi
  _BYTE *v10; // r15
  int NcryptObjectSizes; // eax
  int v14; // ebx
  NTSTATUS SymmetricKey; // eax
  __int64 v16; // rsi
  __int64 v17; // r9
  __int64 v18; // rcx
  UCHAR *v19; // rax
  UCHAR *v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  int v23; // [rsp+40h] [rbp-C0h] BYREF
  UCHAR pbOutput[4]; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v25; // [rsp+48h] [rbp-B8h]
  BCRYPT_KEY_HANDLE hKey; // [rsp+50h] [rbp-B0h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+58h] [rbp-A8h] BYREF
  ULONG cbSecret; // [rsp+60h] [rbp-A0h]
  _DWORD v29[2]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+78h] [rbp-88h]
  _QWORD v32[2]; // [rsp+80h] [rbp-80h] BYREF
  int v33; // [rsp+90h] [rbp-70h]
  int v34; // [rsp+94h] [rbp-6Ch]
  const wchar_t *v35; // [rsp+98h] [rbp-68h]
  int v36; // [rsp+A0h] [rbp-60h]
  int v37; // [rsp+A4h] [rbp-5Ch]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  UCHAR v39[16]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v40; // [rsp+C0h] [rbp-40h]
  UCHAR v41[16]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v42; // [rsp+E0h] [rbp-20h]

  v9 = pbKeyObject;
  v10 = a8;
  v31 = a1;
  *(_DWORD *)pbOutput = 0;
  cbSecret = a4;
  v25 = 0;
  phKey = 0;
  hKey = 0;
  *(_OWORD *)v39 = 0;
  v40 = 0;
  *(_OWORD *)v41 = 0;
  v42 = 0;
  if ( !a1 || a2 != 16 || !a3 || !a4 || !a5 )
    goto LABEL_8;
  if ( pbKeyObject )
  {
    if ( !cbKeyObject )
    {
LABEL_8:
      DebugTraceError(
        2148073511LL,
        "status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlssessionticket.c",
        105);
      return 2148073511LL;
    }
  }
  else if ( cbKeyObject )
  {
    goto LABEL_8;
  }
  if ( !a8 || !a9 )
    goto LABEL_8;
  NcryptObjectSizes = GetNcryptObjectSizes(pbOutput);
  v14 = NcryptObjectSizes;
  if ( NcryptObjectSizes < 0 )
  {
    DebugTraceError(
      (unsigned int)NcryptObjectSizes,
      "status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlssessionticket.c",
      115);
    return (unsigned int)v14;
  }
  if ( (!pbKeyObject || cbKeyObject >= *(_DWORD *)pbOutput) && a9 >= v25 )
  {
    *a5 = 0;
    v32[0] = 14;
    v37 = 14;
    v38 = v31;
    v30 = v32;
    v35 = L"dpaping key file provider";
    v23 = 0;
    v32[1] = L"SHA256";
    v29[0] = 0;
    v34 = 13;
    v36 = 16;
    v29[1] = 3;
    v33 = 52;
    SymmetricKey = BCryptGenerateSymmetricKey((BCRYPT_ALG_HANDLE)0x341, &phKey, 0, 0, a3, cbSecret, 0);
    v14 = SymmetricKey;
    v16 = 32;
    if ( SymmetricKey >= 0 )
    {
      SymmetricKey = BCryptKeyDerivation(phKey, v29, v39, 32, &v23, 0);
      v14 = SymmetricKey;
      if ( SymmetricKey >= 0 )
      {
        SymmetricKey = BCryptGenerateSymmetricKey((BCRYPT_ALG_HANDLE)0x341, &hKey, 0, 0, v39, 0x20u, 0);
        v14 = SymmetricKey;
        if ( SymmetricKey >= 0 )
        {
          v35 = L"AES";
          v33 = 8;
          SymmetricKey = BCryptKeyDerivation(hKey, v29, v41, 32, &v23, 0);
          v14 = SymmetricKey;
          if ( SymmetricKey >= 0 )
          {
            SymmetricKey = BCryptGenerateSymmetricKey(
                             (BCRYPT_ALG_HANDLE)0x1A1,
                             a5,
                             pbKeyObject,
                             cbKeyObject,
                             v41,
                             0x20u,
                             0);
            v14 = SymmetricKey;
            if ( SymmetricKey >= 0 )
            {
              v35 = L"SHA256";
              v33 = 14;
              SymmetricKey = BCryptKeyDerivation(hKey, v29, a8, a9, &v23, 0);
              v14 = SymmetricKey;
              if ( SymmetricKey >= 0 )
              {
LABEL_32:
                if ( phKey )
                {
                  BCryptDestroyKey(phKey);
                  phKey = 0;
                }
                if ( hKey )
                {
                  BCryptDestroyKey(hKey);
                  hKey = 0;
                }
                v18 = 32;
                v19 = v39;
                do
                {
                  *v19++ = 0;
                  --v18;
                }
                while ( v18 );
                v20 = v41;
                do
                {
                  *v20++ = 0;
                  --v16;
                }
                while ( v16 );
                if ( v14 < 0 )
                {
                  if ( *a5 )
                  {
                    BCryptDestroyKey(*a5);
                    *a5 = 0;
                  }
                  if ( pbKeyObject )
                  {
                    v21 = cbKeyObject;
                    if ( cbKeyObject )
                    {
                      do
                      {
                        *v9++ = 0;
                        --v21;
                      }
                      while ( v21 );
                    }
                  }
                  v22 = a9;
                  do
                  {
                    *v10++ = 0;
                    --v22;
                  }
                  while ( v22 );
                }
                return (unsigned int)v14;
              }
              v17 = 251;
            }
            else
            {
              v17 = 232;
            }
          }
          else
          {
            v17 = 218;
          }
        }
        else
        {
          v17 = 199;
        }
      }
      else
      {
        v17 = 182;
      }
    }
    else
    {
      v17 = 170;
    }
    DebugTraceError(
      (unsigned int)SymmetricKey,
      "status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlssessionticket.c",
      v17);
    goto LABEL_32;
  }
  DebugTraceError(2148073512LL, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlssessionticket.c", 122);
  return 2148073512LL;
}

```

## disassembly

```asm
0x180020d10  push    rbp
0x180020d12  push    rbx
0x180020d13  push    rsi
0x180020d14  push    rdi
0x180020d15  push    r12
0x180020d17  push    r13
0x180020d19  push    r14
0x180020d1b  push    r15
0x180020d1d  lea     rbp, [rsp-8]
0x180020d22  sub     rsp, 108h
0x180020d29  mov     rax, cs:__security_cookie
0x180020d30  xor     rax, rsp
0x180020d33  mov     [rbp+40h+var_50], rax
0x180020d37  mov     r13, [rbp+40h+arg_20]
0x180020d3b  xorps   xmm0, xmm0
0x180020d3e  mov     rdi, [rbp+40h+pbKeyObject]
0x180020d42  xorps   xmm1, xmm1
0x180020d45  mov     r15, [rbp+40h+arg_38]
0x180020d4c  mov     rsi, r8
0x180020d4f  xor     r8d, r8d
0x180020d52  mov     [rsp+140h+var_C8], rcx
0x180020d57  mov     dword ptr [rsp+140h+pbOutput], r8d
0x180020d5c  mov     eax, r9d
0x180020d5f  mov     [rsp+140h+var_E0], eax
0x180020d63  mov     [rsp+140h+var_F8], r8d
0x180020d68  mov     [rsp+140h+phKey], r8
0x180020d6d  mov     [rsp+140h+hKey], r8
0x180020d72  movups  xmmword ptr [rbp+40h+var_90], xmm0
0x180020d76  movups  [rbp+40h+var_80], xmm0
0x180020d7a  movups  xmmword ptr [rbp+40h+var_70], xmm1
0x180020d7e  movups  [rbp+40h+var_60], xmm1
0x180020d82  test    rcx, rcx
0x180020d85  jz      short loc_180020DAB
0x180020d87  cmp     edx, 10h
0x180020d8a  jnz     short loc_180020DAB
0x180020d8c  test    rsi, rsi
0x180020d8f  jz      short loc_180020DAB
0x180020d91  test    eax, eax
0x180020d93  jz      short loc_180020DAB
0x180020d95  test    r13, r13
0x180020d98  jz      short loc_180020DAB
0x180020d9a  mov     r14d, [rbp+40h+cbKeyObject]
0x180020da1  test    rdi, rdi
0x180020da4  jz      short loc_180020DEE
0x180020da6  test    r14d, r14d
0x180020da9  jnz     short loc_180020DF3
0x180020dab  mov     r9d, 69h ; 'i'
0x180020db1  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180020db8  lea     rdx, aStatus_0; "status"
0x180020dbf  mov     ecx, 80090027h
0x180020dc4  call    DebugTraceError
0x180020dc9  mov     eax, 80090027h
0x180020dce  mov     rcx, [rbp+40h+var_50]
0x180020dd2  xor     rcx, rsp; StackCookie
0x180020dd5  call    __security_check_cookie
0x180020dda  add     rsp, 108h
0x180020de1  pop     r15
0x180020de3  pop     r14
0x180020de5  pop     r13
0x180020de7  pop     r12
0x180020de9  pop     rdi
0x180020dea  pop     rsi
0x180020deb  pop     rbx
0x180020dec  pop     rbp
0x180020ded  retn
0x180020dee  test    r14d, r14d
0x180020df1  jnz     short loc_180020DAB
0x180020df3  test    r15, r15
0x180020df6  jz      short loc_180020DAB
0x180020df8  mov     r12d, [rbp+40h+arg_40]
0x180020dff  test    r12d, r12d
0x180020e02  jz      short loc_180020DAB
0x180020e04  lea     rdx, [rsp+140h+var_F8]
0x180020e09  lea     rcx, [rsp+140h+pbOutput]; pbOutput
0x180020e0e  call    GetNcryptObjectSizes
0x180020e13  xor     ecx, ecx
0x180020e15  mov     ebx, eax
0x180020e17  test    eax, eax
0x180020e19  jns     short loc_180020E38
0x180020e1b  lea     r9d, [rcx+73h]
0x180020e1f  mov     ecx, eax
0x180020e21  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180020e28  lea     rdx, aStatus_0; "status"
0x180020e2f  call    DebugTraceError
0x180020e34  mov     eax, ebx
0x180020e36  jmp     short loc_180020DCE
0x180020e38  test    rdi, rdi
0x180020e3b  jz      short loc_180020E44
0x180020e3d  cmp     r14d, dword ptr [rsp+140h+pbOutput]
0x180020e42  jb      short loc_180020E4B
0x180020e44  cmp     r12d, [rsp+140h+var_F8]
0x180020e49  jnb     short loc_180020E73
0x180020e4b  mov     r9d, 7Ah ; 'z'
0x180020e51  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180020e58  lea     rdx, aStatus_0; "status"
0x180020e5f  mov     ecx, 80090028h
0x180020e64  call    DebugTraceError
0x180020e69  mov     eax, 80090028h
0x180020e6e  jmp     loc_180020DCE
0x180020e73  mov     [rsp+140h+dwFlags], ecx; dwFlags
0x180020e77  lea     rdx, aSha256; "SHA256"
0x180020e7e  mov     eax, 0Eh
0x180020e83  mov     [r13+0], rcx
0x180020e87  mov     [rbp+40h+var_C0], rax
0x180020e8b  xor     r9d, r9d; cbKeyObject
0x180020e8e  mov     [rbp+40h+var_9C], eax
0x180020e91  xor     r8d, r8d; pbKeyObject
0x180020e94  mov     rax, [rsp+140h+var_C8]
0x180020e99  mov     [rbp+40h+var_98], rax
0x180020e9d  lea     rax, [rbp+40h+var_C0]
0x180020ea1  mov     [rsp+140h+var_D0], rax
0x180020ea6  lea     rax, aDpapingKeyFile; "dpaping key file provider"
0x180020ead  mov     [rbp+40h+var_A8], rax
0x180020eb1  mov     eax, [rsp+140h+var_E0]
0x180020eb5  mov     [rsp+140h+var_100], ecx
0x180020eb9  mov     [rbp+40h+var_B8], rdx
0x180020ebd  lea     rdx, [rsp+140h+phKey]; phKey
0x180020ec2  mov     [rsp+140h+var_D8], ecx
0x180020ec6  mov     ecx, 341h; hAlgorithm
0x180020ecb  mov     [rsp+140h+cbSecret], eax; cbSecret
0x180020ecf  mov     [rsp+140h+pbSecret], rsi; pbSecret
0x180020ed4  mov     [rbp+40h+var_AC], 0Dh
0x180020edb  mov     [rbp+40h+var_A0], 10h
0x180020ee2  mov     [rsp+140h+var_D4], 3
0x180020eea  mov     [rbp+40h+var_B0], 34h ; '4'
0x180020ef1  call    cs:__imp_BCryptGenerateSymmetricKey
0x180020ef7  mov     ebx, eax
0x180020ef9  mov     esi, 20h ; ' '
0x180020efe  test    eax, eax
0x180020f00  jns     short loc_180020F0D
0x180020f02  mov     r9d, 0AAh
0x180020f08  jmp     loc_180021049
0x180020f0d  mov     rcx, [rsp+140h+phKey]
0x180020f12  lea     rax, [rsp+140h+var_100]
0x180020f17  mov     [rsp+140h+cbSecret], 0
0x180020f1f  lea     r8, [rbp+40h+var_90]
0x180020f23  mov     r9d, esi
0x180020f26  mov     [rsp+140h+pbSecret], rax
0x180020f2b  lea     rdx, [rsp+140h+var_D8]
0x180020f30  call    cs:__imp_BCryptKeyDerivation
0x180020f36  mov     ebx, eax
0x180020f38  test    eax, eax
0x180020f3a  jns     short loc_180020F47
0x180020f3c  mov     r9d, 0B6h
0x180020f42  jmp     loc_180021049
0x180020f47  mov     [rsp+140h+dwFlags], 0; dwFlags
0x180020f4f  lea     rax, [rbp+40h+var_90]
0x180020f53  mov     [rsp+140h+cbSecret], esi; cbSecret
0x180020f57  lea     rdx, [rsp+140h+hKey]; phKey
0x180020f5c  xor     r9d, r9d; cbKeyObject
0x180020f5f  mov     [rsp+140h+pbSecret], rax; pbSecret
0x180020f64  xor     r8d, r8d; pbKeyObject
0x180020f67  mov     ecx, 341h; hAlgorithm
0x180020f6c  call    cs:__imp_BCryptGenerateSymmetricKey
0x180020f72  mov     ebx, eax
0x180020f74  test    eax, eax
0x180020f76  jns     short loc_180020F83
0x180020f78  mov     r9d, 0C7h
0x180020f7e  jmp     loc_180021049
0x180020f83  mov     rcx, [rsp+140h+hKey]
0x180020f88  lea     rax, aAes; "AES"
0x180020f8f  mov     [rbp+40h+var_A8], rax
0x180020f93  lea     r8, [rbp+40h+var_70]
0x180020f97  lea     rax, [rsp+140h+var_100]
0x180020f9c  mov     [rsp+140h+cbSecret], 0
0x180020fa4  mov     r9d, esi
0x180020fa7  mov     [rsp+140h+pbSecret], rax
0x180020fac  lea     rdx, [rsp+140h+var_D8]
0x180020fb1  mov     [rbp+40h+var_B0], 8
0x180020fb8  call    cs:__imp_BCryptKeyDerivation
0x180020fbe  mov     ebx, eax
0x180020fc0  test    eax, eax
0x180020fc2  jns     short loc_180020FCC
0x180020fc4  mov     r9d, 0DAh
0x180020fca  jmp     short loc_180021049
0x180020fcc  mov     [rsp+140h+dwFlags], 0; dwFlags
0x180020fd4  lea     rax, [rbp+40h+var_70]
0x180020fd8  mov     [rsp+140h+cbSecret], esi; cbSecret
0x180020fdc  mov     r9d, r14d; cbKeyObject
0x180020fdf  mov     r8, rdi; pbKeyObject
0x180020fe2  mov     [rsp+140h+pbSecret], rax; pbSecret
0x180020fe7  mov     rdx, r13; phKey
0x180020fea  mov     ecx, 1A1h; hAlgorithm
0x180020fef  call    cs:__imp_BCryptGenerateSymmetricKey
0x180020ff5  mov     ebx, eax
0x180020ff7  test    eax, eax
0x180020ff9  jns     short loc_180021003
0x180020ffb  mov     r9d, 0E8h
0x180021001  jmp     short loc_180021049
0x180021003  mov     rcx, [rsp+140h+hKey]
0x180021008  lea     rax, aSha256; "SHA256"
0x18002100f  mov     [rbp+40h+var_A8], rax
0x180021013  lea     rdx, [rsp+140h+var_D8]
0x180021018  lea     rax, [rsp+140h+var_100]
0x18002101d  mov     [rsp+140h+cbSecret], 0
0x180021025  mov     r9d, r12d
0x180021028  mov     [rsp+140h+pbSecret], rax
0x18002102d  mov     r8, r15
0x180021030  mov     [rbp+40h+var_B0], 0Eh
0x180021037  call    cs:__imp_BCryptKeyDerivation
0x18002103d  mov     ebx, eax
0x18002103f  test    eax, eax
0x180021041  jns     short loc_18002105E
0x180021043  mov     r9d, 0FBh
0x180021049  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021050  mov     ecx, eax
0x180021052  lea     rdx, aStatus_0; "status"
0x180021059  call    DebugTraceError
0x18002105e  mov     rcx, [rsp+140h+phKey]; hKey
0x180021063  test    rcx, rcx
0x180021066  jz      short loc_180021077
0x180021068  call    cs:__imp_BCryptDestroyKey
0x18002106e  mov     [rsp+140h+phKey], 0
0x180021077  mov     rcx, [rsp+140h+hKey]; hKey
0x18002107c  test    rcx, rcx
0x18002107f  jz      short loc_180021090
0x180021081  call    cs:__imp_BCryptDestroyKey
0x180021087  mov     [rsp+140h+hKey], 0
0x180021090  mov     rcx, rsi
0x180021093  lea     rax, [rbp+40h+var_90]
0x180021097  mov     byte ptr [rax], 0
0x18002109a  inc     rax
0x18002109d  sub     rcx, 1
0x1800210a1  jnz     short loc_180021097
0x1800210a3  lea     rax, [rbp+40h+var_70]
0x1800210a7  mov     byte ptr [rax], 0
0x1800210aa  inc     rax
0x1800210ad  sub     rsi, 1
0x1800210b1  jnz     short loc_1800210A7
0x1800210b3  test    ebx, ebx
0x1800210b5  jns     loc_180020E34
0x1800210bb  mov     rcx, [r13+0]; hKey
0x1800210bf  test    rcx, rcx
0x1800210c2  jz      short loc_1800210CE
0x1800210c4  call    cs:__imp_BCryptDestroyKey
0x1800210ca  mov     [r13+0], rsi
0x1800210ce  test    rdi, rdi
0x1800210d1  jz      short loc_1800210E7
0x1800210d3  mov     eax, r14d
0x1800210d6  test    r14d, r14d
0x1800210d9  jz      short loc_1800210E7
0x1800210db  mov     [rdi], sil
0x1800210de  inc     rdi
0x1800210e1  sub     rax, 1
0x1800210e5  jnz     short loc_1800210DB
0x1800210e7  mov     rax, r12
0x1800210ea  mov     [r15], sil
0x1800210ed  inc     r15
0x1800210f0  sub     rax, 1
0x1800210f4  jnz     short loc_1800210EA
0x1800210f6  jmp     loc_180020E34
```
