# TlsDeriveSecret

- ea: `0x180083c48`
- end: `0x180083ecb`
- name: `TlsDeriveSecret`
- size: `643`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180082940`

## callees

- `0x1800020c0`
- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x180036040`
- `0x18005a4d0`
- `0x180083800`
- `0x180083c48`
- `0x180083ed4`
- `0x18009fa80`

## string_xrefs

- `0x180083cc7`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180083e66`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

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
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  unsigned int v17; // ebx
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // r9
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // rax
  int v25; // eax
  unsigned int SymmetricKey; // eax
  __int64 v27; // r9
  unsigned int v28; // eax
  unsigned int v29; // eax
  __int64 v30; // rax
  UCHAR *v31; // rcx
  PUCHAR pbInput; // [rsp+90h] [rbp+18h] BYREF
  ULONG v34; // [rsp+98h] [rbp+20h] BYREF

  v6 = 0;
  v34 = 0;
  cbSecret = 0;
  pbInput = 0;
  pbSecret = 0;
  v10 = 0;
  if ( a1 && (v11 = *(_QWORD *)(a1 + 32)) != 0 && (v12 = *(_QWORD *)(a1 + 16)) != 0 && a6 )
  {
    PrfHashInfo = GetPrfHashInfo(*(_QWORD *)(a1 + 16), &pbInput, &v34);
    v17 = PrfHashInfo;
    if ( PrfHashInfo < 0 )
    {
      DebugTraceError(
        (unsigned int)PrfHashInfo,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        4087);
      return v17;
    }
    v18 = MSCryptAlloc(112, v14, v15, v16);
    v6 = v18;
    if ( v18 )
    {
      memset((void *)(v18 + 8), 0, 0x68u);
      cbSecret = v34;
      *(_DWORD *)v6 = 112;
      *(_DWORD *)(v6 + 4) = 1936944179;
      *(_DWORD *)(v6 + 8) = *(_DWORD *)(a1 + 8);
      *(_QWORD *)(v6 + 16) = v12;
      *(_DWORD *)(v6 + 108) = 4;
      v24 = MSCryptAlloc(cbSecret, v21, v22, v23);
      pbSecret = (UCHAR *)v24;
      if ( v24 )
      {
        v25 = TlsExpandLabel(v11, "traffic upd", 0, 0, v24, (_WORD)cbSecret);
        v17 = v25;
        if ( v25 >= 0 )
        {
          SymmetricKey = BCryptGenerateSymmetricKey(
                           (BCRYPT_ALG_HANDLE)0x391,
                           (BCRYPT_KEY_HANDLE *)(v6 + 32),
                           0,
                           0,
                           pbSecret,
                           cbSecret,
                           0);
          v17 = SymmetricKey;
          if ( SymmetricKey )
          {
            v19 = SymmetricKey;
            v20 = 4146;
          }
          else
          {
            v10 = *(void **)(v6 + 32);
            v27 = -1;
            do
              ++v27;
            while ( *(_WORD *)&pbInput[2 * v27] );
            v28 = BCryptSetProperty(v10, L"HkdfHashAlgorithm", pbInput, 2 * v27 + 2, 0);
            v17 = v28;
            if ( v28 )
            {
              v19 = v28;
              v20 = 4160;
            }
            else
            {
              v29 = BCryptSetProperty(v10, L"HkdfPrkAndFinalize", 0, 0, 0);
              v17 = v29;
              if ( !v29 )
              {
                *a6 = v6;
LABEL_28:
                v30 = cbSecret;
                v31 = pbSecret;
                if ( cbSecret )
                {
                  do
                  {
                    *v31++ = 0;
                    --v30;
                  }
                  while ( v30 );
                }
                MSCryptFree(pbSecret);
                return v17;
              }
              v19 = v29;
              v20 = 4171;
            }
          }
        }
        else
        {
          v19 = (unsigned int)v25;
          v20 = 4131;
        }
      }
      else
      {
        v17 = -2146893810;
        v19 = 2148073486LL;
        v20 = 4119;
      }
    }
    else
    {
      cbSecret = v34;
      v17 = -2146893810;
      v19 = 2148073486LL;
      v20 = 4104;
    }
  }
  else
  {
    v17 = -2146893785;
    v19 = 2148073511LL;
    v20 = 4080;
  }
  DebugTraceError(v19, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", v20);
  if ( v6 )
  {
    if ( v10 )
      BCryptDestroyKey(v10);
    MSCryptFree((PVOID)v6);
  }
  if ( pbSecret )
    goto LABEL_28;
  return v17;
}

```

## disassembly

```asm
0x180083c48  mov     rax, rsp
0x180083c4b  mov     [rax+8], rbx
0x180083c4f  mov     [rax+20h], r9b
0x180083c53  mov     [rax+18h], r8
0x180083c57  push    rbp
0x180083c58  push    rsi
0x180083c59  push    rdi
0x180083c5a  push    r12
0x180083c5c  push    r13
0x180083c5e  push    r14
0x180083c60  push    r15
0x180083c62  sub     rsp, 40h
0x180083c66  xor     edi, edi
0x180083c68  mov     rbp, rcx
0x180083c6b  mov     [rax+20h], edi
0x180083c6e  mov     r14d, edi
0x180083c71  mov     [rax+18h], rdi
0x180083c75  mov     esi, edi
0x180083c77  mov     r12d, edi
0x180083c7a  test    rcx, rcx
0x180083c7d  jz      loc_180083E4D
0x180083c83  mov     r13, [rcx+20h]
0x180083c87  test    r13, r13
0x180083c8a  jz      loc_180083E4D
0x180083c90  mov     r15, [rcx+10h]
0x180083c94  test    r15, r15
0x180083c97  jz      loc_180083E4D
0x180083c9d  cmp     [rsp+78h+arg_28], rdi
0x180083ca5  jz      loc_180083E4D
0x180083cab  lea     r8, [rax+20h]
0x180083caf  mov     rcx, r15
0x180083cb2  lea     rdx, [rax+18h]
0x180083cb6  call    GetPrfHashInfo
0x180083cbb  mov     ebx, eax
0x180083cbd  test    eax, eax
0x180083cbf  jns     short loc_180083CE1
0x180083cc1  mov     r9d, 0FF7h
0x180083cc7  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180083cce  lea     rdx, aStatus; "Status"
0x180083cd5  mov     ecx, eax
0x180083cd7  call    DebugTraceError
0x180083cdc  jmp     loc_180083EB0
0x180083ce1  mov     ebx, 70h ; 'p'
0x180083ce6  mov     ecx, ebx
0x180083ce8  call    MSCryptAlloc
0x180083ced  mov     rdi, rax
0x180083cf0  test    rax, rax
0x180083cf3  jnz     short loc_180083D12
0x180083cf5  mov     r14d, [rsp+78h+arg_18]
0x180083cfd  mov     ebx, 8009000Eh
0x180083d02  mov     ecx, 8009000Eh
0x180083d07  mov     r9d, 1008h
0x180083d0d  jmp     loc_180083E5D
0x180083d12  xor     edx, edx; Val
0x180083d14  lea     rcx, [rax+8]; void *
0x180083d18  lea     r8d, [rdx+68h]; Size
0x180083d1c  call    memset
0x180083d21  mov     r14d, [rsp+78h+arg_18]
0x180083d29  mov     [rdi], ebx
0x180083d2b  mov     ecx, r14d
0x180083d2e  mov     dword ptr [rdi+4], 73736C33h
0x180083d35  mov     eax, [rbp+8]
0x180083d38  mov     [rdi+8], eax
0x180083d3b  mov     [rdi+10h], r15
0x180083d3f  mov     dword ptr [rdi+6Ch], 4
0x180083d46  call    MSCryptAlloc
0x180083d4b  xor     ebp, ebp
0x180083d4d  mov     rsi, rax
0x180083d50  test    rax, rax
0x180083d53  jnz     short loc_180083D6A
0x180083d55  mov     ebx, 8009000Eh
0x180083d5a  mov     ecx, 8009000Eh
0x180083d5f  mov     r9d, 1017h
0x180083d65  jmp     loc_180083E5F
0x180083d6a  mov     word ptr [rsp+78h+cbSecret], r14w
0x180083d70  lea     rdx, aTrafficUpd; "traffic upd"
0x180083d77  xor     r9d, r9d
0x180083d7a  mov     [rsp+78h+pbSecret], rsi
0x180083d7f  xor     r8d, r8d
0x180083d82  mov     rcx, r13
0x180083d85  call    TlsExpandLabel
0x180083d8a  mov     ebx, eax
0x180083d8c  test    eax, eax
0x180083d8e  jns     short loc_180083D9D
0x180083d90  mov     ecx, eax
0x180083d92  mov     r9d, 1023h
0x180083d98  jmp     loc_180083E5F
0x180083d9d  mov     [rsp+78h+dwFlags], ebp; dwFlags
0x180083da1  lea     rdx, [rdi+20h]; phKey
0x180083da5  mov     [rsp+78h+cbSecret], r14d; cbSecret
0x180083daa  xor     r9d, r9d; cbKeyObject
0x180083dad  xor     r8d, r8d; pbKeyObject
0x180083db0  mov     [rsp+78h+pbSecret], rsi; pbSecret
0x180083db5  mov     ecx, 391h; hAlgorithm
0x180083dba  call    BCryptGenerateSymmetricKey
0x180083dbf  mov     ebx, eax
0x180083dc1  test    eax, eax
0x180083dc3  jz      short loc_180083DD2
0x180083dc5  mov     ecx, eax
0x180083dc7  mov     r9d, 1032h
0x180083dcd  jmp     loc_180083E5F
0x180083dd2  mov     r12, [rdi+20h]
0x180083dd6  or      r9, 0FFFFFFFFFFFFFFFFh
0x180083dda  mov     r8, [rsp+78h+pbInput]; pbInput
0x180083de2  inc     r9
0x180083de5  cmp     [r8+r9*2], bp
0x180083dea  jnz     short loc_180083DE2
0x180083dec  lea     r9d, ds:2[r9*2]; cbInput
0x180083df4  mov     dword ptr [rsp+78h+pbSecret], ebp; dwFlags
0x180083df8  lea     rdx, aHkdfhashalgori; "HkdfHashAlgorithm"
0x180083dff  mov     rcx, r12; hObject
0x180083e02  call    BCryptSetProperty
0x180083e07  mov     ebx, eax
0x180083e09  test    eax, eax
0x180083e0b  jz      short loc_180083E17
0x180083e0d  mov     ecx, eax
0x180083e0f  mov     r9d, 1040h
0x180083e15  jmp     short loc_180083E5F
0x180083e17  xor     r9d, r9d; cbInput
0x180083e1a  mov     dword ptr [rsp+78h+pbSecret], ebp; dwFlags
0x180083e1e  xor     r8d, r8d; pbInput
0x180083e21  lea     rdx, aHkdfprkandfina; "HkdfPrkAndFinalize"
0x180083e28  mov     rcx, r12; hObject
0x180083e2b  call    BCryptSetProperty
0x180083e30  mov     ebx, eax
0x180083e32  test    eax, eax
0x180083e34  jz      short loc_180083E40
0x180083e36  mov     ecx, eax
0x180083e38  mov     r9d, 104Bh
0x180083e3e  jmp     short loc_180083E5F
0x180083e40  mov     rax, [rsp+78h+arg_28]
0x180083e48  mov     [rax], rdi
0x180083e4b  jmp     short loc_180083E91
0x180083e4d  mov     ebx, 80090027h
0x180083e52  mov     ecx, 80090027h
0x180083e57  mov     r9d, 0FF0h
0x180083e5d  xor     ebp, ebp
0x180083e5f  lea     rdx, aStatus; "Status"
0x180083e66  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180083e6d  call    DebugTraceError
0x180083e72  test    rdi, rdi
0x180083e75  jz      short loc_180083E8C
0x180083e77  test    r12, r12
0x180083e7a  jz      short loc_180083E84
0x180083e7c  mov     rcx, r12; hKey
0x180083e7f  call    BCryptDestroyKey
0x180083e84  mov     rcx, rdi; P
0x180083e87  call    MSCryptFree
0x180083e8c  test    rsi, rsi
0x180083e8f  jz      short loc_180083EB0
0x180083e91  mov     eax, r14d
0x180083e94  mov     rcx, rsi
0x180083e97  test    r14d, r14d
0x180083e9a  jz      short loc_180083EA8
0x180083e9c  mov     [rcx], bpl
0x180083e9f  inc     rcx
0x180083ea2  sub     rax, 1
0x180083ea6  jnz     short loc_180083E9C
0x180083ea8  mov     rcx, rsi; P
0x180083eab  call    MSCryptFree
0x180083eb0  mov     eax, ebx
0x180083eb2  mov     rbx, [rsp+78h+arg_0]
0x180083eba  add     rsp, 40h
0x180083ebe  pop     r15
0x180083ec0  pop     r14
0x180083ec2  pop     r13
0x180083ec4  pop     r12
0x180083ec6  pop     rdi
0x180083ec7  pop     rsi
0x180083ec8  pop     rbp
0x180083ec9  retn
```
