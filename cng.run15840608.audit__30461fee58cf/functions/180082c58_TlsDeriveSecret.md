# TlsDeriveSecret

- ea: `0x180082c58`
- end: `0x180082edb`
- name: `TlsDeriveSecret`
- size: `643`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180081950`

## callees

- `0x1800020c0`
- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x180035540`
- `0x180059be0`
- `0x180082810`
- `0x180082c58`
- `0x180082ee4`
- `0x18009dd40`

## string_xrefs

- `0x180082cd7`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180082e76`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

## pseudocode

```c
__int64 __fastcall TlsDeriveSecret(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, __int64 *a6)
{
  __int64 v6; // rdi
  ULONG cbSecret; // r14d
  UCHAR *pbSecret; // rsi
  void *v10; // r12
  __int64 v11; // r13
  __int64 v12; // r15
  int PrfHashInfo; // eax
  unsigned int v14; // ebx
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // r9
  __int64 v18; // rax
  int v19; // eax
  unsigned int SymmetricKey; // eax
  __int64 v21; // r9
  unsigned int v22; // eax
  unsigned int v23; // eax
  __int64 v24; // rax
  UCHAR *v25; // rcx
  PUCHAR pbInput; // [rsp+90h] [rbp+18h] BYREF
  ULONG v28; // [rsp+98h] [rbp+20h] BYREF

  v6 = 0;
  v28 = 0;
  cbSecret = 0;
  pbInput = 0;
  pbSecret = 0;
  v10 = 0;
  if ( a1 && (v11 = *(_QWORD *)(a1 + 32)) != 0 && (v12 = *(_QWORD *)(a1 + 16)) != 0 && a6 )
  {
    PrfHashInfo = GetPrfHashInfo(*(_QWORD *)(a1 + 16), &pbInput, &v28);
    v14 = PrfHashInfo;
    if ( PrfHashInfo < 0 )
    {
      DebugTraceError(
        (unsigned int)PrfHashInfo,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        4087);
      return v14;
    }
    v15 = MSCryptAlloc(112);
    v6 = v15;
    if ( v15 )
    {
      memset((void *)(v15 + 8), 0, 0x68u);
      cbSecret = v28;
      *(_DWORD *)v6 = 112;
      *(_DWORD *)(v6 + 4) = 1936944179;
      *(_DWORD *)(v6 + 8) = *(_DWORD *)(a1 + 8);
      *(_QWORD *)(v6 + 16) = v12;
      *(_DWORD *)(v6 + 108) = 4;
      v18 = MSCryptAlloc(cbSecret);
      pbSecret = (UCHAR *)v18;
      if ( v18 )
      {
        v19 = TlsExpandLabel(v11, "traffic upd", 0, 0, v18, (_WORD)cbSecret);
        v14 = v19;
        if ( v19 >= 0 )
        {
          SymmetricKey = BCryptGenerateSymmetricKey(
                           (BCRYPT_ALG_HANDLE)0x391,
                           (BCRYPT_KEY_HANDLE *)(v6 + 32),
                           0,
                           0,
                           pbSecret,
                           cbSecret,
                           0);
          v14 = SymmetricKey;
          if ( SymmetricKey )
          {
            v16 = SymmetricKey;
            v17 = 4146;
          }
          else
          {
            v10 = *(void **)(v6 + 32);
            v21 = -1;
            do
              ++v21;
            while ( *(_WORD *)&pbInput[2 * v21] );
            v22 = BCryptSetProperty(v10, L"HkdfHashAlgorithm", pbInput, 2 * v21 + 2, 0);
            v14 = v22;
            if ( v22 )
            {
              v16 = v22;
              v17 = 4160;
            }
            else
            {
              v23 = BCryptSetProperty(v10, L"HkdfPrkAndFinalize", 0, 0, 0);
              v14 = v23;
              if ( !v23 )
              {
                *a6 = v6;
LABEL_28:
                v24 = cbSecret;
                v25 = pbSecret;
                if ( cbSecret )
                {
                  do
                  {
                    *v25++ = 0;
                    --v24;
                  }
                  while ( v24 );
                }
                MSCryptFree(pbSecret);
                return v14;
              }
              v16 = v23;
              v17 = 4171;
            }
          }
        }
        else
        {
          v16 = (unsigned int)v19;
          v17 = 4131;
        }
      }
      else
      {
        v14 = -2146893810;
        v16 = 2148073486LL;
        v17 = 4119;
      }
    }
    else
    {
      cbSecret = v28;
      v14 = -2146893810;
      v16 = 2148073486LL;
      v17 = 4104;
    }
  }
  else
  {
    v14 = -2146893785;
    v16 = 2148073511LL;
    v17 = 4080;
  }
  DebugTraceError(v16, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", v17);
  if ( v6 )
  {
    if ( v10 )
      BCryptDestroyKey(v10);
    MSCryptFree((PVOID)v6);
  }
  if ( pbSecret )
    goto LABEL_28;
  return v14;
}

```

## disassembly

```asm
0x180082c58  mov     rax, rsp
0x180082c5b  mov     [rax+8], rbx
0x180082c5f  mov     [rax+20h], r9b
0x180082c63  mov     [rax+18h], r8
0x180082c67  push    rbp
0x180082c68  push    rsi
0x180082c69  push    rdi
0x180082c6a  push    r12
0x180082c6c  push    r13
0x180082c6e  push    r14
0x180082c70  push    r15
0x180082c72  sub     rsp, 40h
0x180082c76  xor     edi, edi
0x180082c78  mov     rbp, rcx
0x180082c7b  mov     [rax+20h], edi
0x180082c7e  mov     r14d, edi
0x180082c81  mov     [rax+18h], rdi
0x180082c85  mov     esi, edi
0x180082c87  mov     r12d, edi
0x180082c8a  test    rcx, rcx
0x180082c8d  jz      loc_180082E5D
0x180082c93  mov     r13, [rcx+20h]
0x180082c97  test    r13, r13
0x180082c9a  jz      loc_180082E5D
0x180082ca0  mov     r15, [rcx+10h]
0x180082ca4  test    r15, r15
0x180082ca7  jz      loc_180082E5D
0x180082cad  cmp     [rsp+78h+arg_28], rdi
0x180082cb5  jz      loc_180082E5D
0x180082cbb  lea     r8, [rax+20h]
0x180082cbf  mov     rcx, r15
0x180082cc2  lea     rdx, [rax+18h]
0x180082cc6  call    GetPrfHashInfo
0x180082ccb  mov     ebx, eax
0x180082ccd  test    eax, eax
0x180082ccf  jns     short loc_180082CF1
0x180082cd1  mov     r9d, 0FF7h
0x180082cd7  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180082cde  lea     rdx, aStatus; "Status"
0x180082ce5  mov     ecx, eax
0x180082ce7  call    DebugTraceError
0x180082cec  jmp     loc_180082EC0
0x180082cf1  mov     ebx, 70h ; 'p'
0x180082cf6  mov     ecx, ebx
0x180082cf8  call    MSCryptAlloc
0x180082cfd  mov     rdi, rax
0x180082d00  test    rax, rax
0x180082d03  jnz     short loc_180082D22
0x180082d05  mov     r14d, [rsp+78h+arg_18]
0x180082d0d  mov     ebx, 8009000Eh
0x180082d12  mov     ecx, 8009000Eh
0x180082d17  mov     r9d, 1008h
0x180082d1d  jmp     loc_180082E6D
0x180082d22  xor     edx, edx; Val
0x180082d24  lea     rcx, [rax+8]; void *
0x180082d28  lea     r8d, [rdx+68h]; Size
0x180082d2c  call    memset
0x180082d31  mov     r14d, [rsp+78h+arg_18]
0x180082d39  mov     [rdi], ebx
0x180082d3b  mov     ecx, r14d
0x180082d3e  mov     dword ptr [rdi+4], 73736C33h
0x180082d45  mov     eax, [rbp+8]
0x180082d48  mov     [rdi+8], eax
0x180082d4b  mov     [rdi+10h], r15
0x180082d4f  mov     dword ptr [rdi+6Ch], 4
0x180082d56  call    MSCryptAlloc
0x180082d5b  xor     ebp, ebp
0x180082d5d  mov     rsi, rax
0x180082d60  test    rax, rax
0x180082d63  jnz     short loc_180082D7A
0x180082d65  mov     ebx, 8009000Eh
0x180082d6a  mov     ecx, 8009000Eh
0x180082d6f  mov     r9d, 1017h
0x180082d75  jmp     loc_180082E6F
0x180082d7a  mov     word ptr [rsp+78h+cbSecret], r14w
0x180082d80  lea     rdx, aTrafficUpd; "traffic upd"
0x180082d87  xor     r9d, r9d
0x180082d8a  mov     [rsp+78h+pbSecret], rsi
0x180082d8f  xor     r8d, r8d
0x180082d92  mov     rcx, r13
0x180082d95  call    TlsExpandLabel
0x180082d9a  mov     ebx, eax
0x180082d9c  test    eax, eax
0x180082d9e  jns     short loc_180082DAD
0x180082da0  mov     ecx, eax
0x180082da2  mov     r9d, 1023h
0x180082da8  jmp     loc_180082E6F
0x180082dad  mov     [rsp+78h+dwFlags], ebp; dwFlags
0x180082db1  lea     rdx, [rdi+20h]; phKey
0x180082db5  mov     [rsp+78h+cbSecret], r14d; cbSecret
0x180082dba  xor     r9d, r9d; cbKeyObject
0x180082dbd  xor     r8d, r8d; pbKeyObject
0x180082dc0  mov     [rsp+78h+pbSecret], rsi; pbSecret
0x180082dc5  mov     ecx, 391h; hAlgorithm
0x180082dca  call    BCryptGenerateSymmetricKey
0x180082dcf  mov     ebx, eax
0x180082dd1  test    eax, eax
0x180082dd3  jz      short loc_180082DE2
0x180082dd5  mov     ecx, eax
0x180082dd7  mov     r9d, 1032h
0x180082ddd  jmp     loc_180082E6F
0x180082de2  mov     r12, [rdi+20h]
0x180082de6  or      r9, 0FFFFFFFFFFFFFFFFh
0x180082dea  mov     r8, [rsp+78h+pbInput]; pbInput
0x180082df2  inc     r9
0x180082df5  cmp     [r8+r9*2], bp
0x180082dfa  jnz     short loc_180082DF2
0x180082dfc  lea     r9d, ds:2[r9*2]; cbInput
0x180082e04  mov     dword ptr [rsp+78h+pbSecret], ebp; dwFlags
0x180082e08  lea     rdx, aHkdfhashalgori; "HkdfHashAlgorithm"
0x180082e0f  mov     rcx, r12; hObject
0x180082e12  call    BCryptSetProperty
0x180082e17  mov     ebx, eax
0x180082e19  test    eax, eax
0x180082e1b  jz      short loc_180082E27
0x180082e1d  mov     ecx, eax
0x180082e1f  mov     r9d, 1040h
0x180082e25  jmp     short loc_180082E6F
0x180082e27  xor     r9d, r9d; cbInput
0x180082e2a  mov     dword ptr [rsp+78h+pbSecret], ebp; dwFlags
0x180082e2e  xor     r8d, r8d; pbInput
0x180082e31  lea     rdx, aHkdfprkandfina; "HkdfPrkAndFinalize"
0x180082e38  mov     rcx, r12; hObject
0x180082e3b  call    BCryptSetProperty
0x180082e40  mov     ebx, eax
0x180082e42  test    eax, eax
0x180082e44  jz      short loc_180082E50
0x180082e46  mov     ecx, eax
0x180082e48  mov     r9d, 104Bh
0x180082e4e  jmp     short loc_180082E6F
0x180082e50  mov     rax, [rsp+78h+arg_28]
0x180082e58  mov     [rax], rdi
0x180082e5b  jmp     short loc_180082EA1
0x180082e5d  mov     ebx, 80090027h
0x180082e62  mov     ecx, 80090027h
0x180082e67  mov     r9d, 0FF0h
0x180082e6d  xor     ebp, ebp
0x180082e6f  lea     rdx, aStatus; "Status"
0x180082e76  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180082e7d  call    DebugTraceError
0x180082e82  test    rdi, rdi
0x180082e85  jz      short loc_180082E9C
0x180082e87  test    r12, r12
0x180082e8a  jz      short loc_180082E94
0x180082e8c  mov     rcx, r12; hKey
0x180082e8f  call    BCryptDestroyKey
0x180082e94  mov     rcx, rdi; P
0x180082e97  call    MSCryptFree
0x180082e9c  test    rsi, rsi
0x180082e9f  jz      short loc_180082EC0
0x180082ea1  mov     eax, r14d
0x180082ea4  mov     rcx, rsi
0x180082ea7  test    r14d, r14d
0x180082eaa  jz      short loc_180082EB8
0x180082eac  mov     [rcx], bpl
0x180082eaf  inc     rcx
0x180082eb2  sub     rax, 1
0x180082eb6  jnz     short loc_180082EAC
0x180082eb8  mov     rcx, rsi; P
0x180082ebb  call    MSCryptFree
0x180082ec0  mov     eax, ebx
0x180082ec2  mov     rbx, [rsp+78h+arg_0]
0x180082eca  add     rsp, 40h
0x180082ece  pop     r15
0x180082ed0  pop     r14
0x180082ed2  pop     r13
0x180082ed4  pop     r12
0x180082ed6  pop     rdi
0x180082ed7  pop     rsi
0x180082ed8  pop     rbp
0x180082ed9  retn
```
