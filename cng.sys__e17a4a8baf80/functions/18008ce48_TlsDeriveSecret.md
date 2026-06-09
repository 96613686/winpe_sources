# TlsDeriveSecret

- ea: `0x18008ce48`
- end: `0x18008d0cb`
- name: `TlsDeriveSecret`
- size: `643`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18008bb40`

## callees

- `0x18000c1e0`
- `0x18000e090`
- `0x180010590`
- `0x18001155c`
- `0x18003f5b0`
- `0x180063db0`
- `0x18008ca00`
- `0x18008ce48`
- `0x18008d0d4`
- `0x1800a4380`

## string_xrefs

- `0x18008cec7`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18008d066`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

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
  unsigned int v15; // ebx
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // r9
  __int64 v19; // rdx
  __int64 v20; // rax
  int v21; // eax
  unsigned int SymmetricKey; // eax
  __int64 v23; // r9
  unsigned int v24; // eax
  unsigned int v25; // eax
  __int64 v26; // rax
  UCHAR *v27; // rcx
  PUCHAR pbInput; // [rsp+90h] [rbp+18h] BYREF
  ULONG v30; // [rsp+98h] [rbp+20h] BYREF

  v6 = 0;
  v30 = 0;
  cbSecret = 0;
  pbInput = 0;
  pbSecret = 0;
  v10 = 0;
  if ( a1 && (v11 = *(_QWORD *)(a1 + 32)) != 0 && (v12 = *(_QWORD *)(a1 + 16)) != 0 && a6 )
  {
    PrfHashInfo = GetPrfHashInfo(*(_QWORD *)(a1 + 16), &pbInput, &v30);
    v15 = PrfHashInfo;
    if ( PrfHashInfo < 0 )
    {
      DebugTraceError(
        (unsigned int)PrfHashInfo,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        4087);
      return v15;
    }
    v16 = MSCryptAlloc(112, v14);
    v6 = v16;
    if ( v16 )
    {
      memset((void *)(v16 + 8), 0, 0x68u);
      cbSecret = v30;
      *(_DWORD *)v6 = 112;
      *(_DWORD *)(v6 + 4) = 1936944179;
      *(_DWORD *)(v6 + 8) = *(_DWORD *)(a1 + 8);
      *(_QWORD *)(v6 + 16) = v12;
      *(_DWORD *)(v6 + 108) = 4;
      v20 = MSCryptAlloc(cbSecret, v19);
      pbSecret = (UCHAR *)v20;
      if ( v20 )
      {
        v21 = TlsExpandLabel(v11, "traffic upd", 0, 0, v20, (_WORD)cbSecret);
        v15 = v21;
        if ( v21 >= 0 )
        {
          SymmetricKey = BCryptGenerateSymmetricKey(
                           (BCRYPT_ALG_HANDLE)0x391,
                           (BCRYPT_KEY_HANDLE *)(v6 + 32),
                           0,
                           0,
                           pbSecret,
                           cbSecret,
                           0);
          v15 = SymmetricKey;
          if ( SymmetricKey )
          {
            v17 = SymmetricKey;
            v18 = 4146;
          }
          else
          {
            v10 = *(void **)(v6 + 32);
            v23 = -1;
            do
              ++v23;
            while ( *(_WORD *)&pbInput[2 * v23] );
            v24 = BCryptSetProperty(v10, L"HkdfHashAlgorithm", pbInput, 2 * v23 + 2, 0);
            v15 = v24;
            if ( v24 )
            {
              v17 = v24;
              v18 = 4160;
            }
            else
            {
              v25 = BCryptSetProperty(v10, L"HkdfPrkAndFinalize", 0, 0, 0);
              v15 = v25;
              if ( !v25 )
              {
                *a6 = v6;
LABEL_28:
                v26 = cbSecret;
                v27 = pbSecret;
                if ( cbSecret )
                {
                  do
                  {
                    *v27++ = 0;
                    --v26;
                  }
                  while ( v26 );
                }
                MSCryptFree(pbSecret);
                return v15;
              }
              v17 = v25;
              v18 = 4171;
            }
          }
        }
        else
        {
          v17 = (unsigned int)v21;
          v18 = 4131;
        }
      }
      else
      {
        v15 = -2146893810;
        v17 = 2148073486LL;
        v18 = 4119;
      }
    }
    else
    {
      cbSecret = v30;
      v15 = -2146893810;
      v17 = 2148073486LL;
      v18 = 4104;
    }
  }
  else
  {
    v15 = -2146893785;
    v17 = 2148073511LL;
    v18 = 4080;
  }
  DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", v18);
  if ( v6 )
  {
    if ( v10 )
      BCryptDestroyKey(v10);
    MSCryptFree((PVOID)v6);
  }
  if ( pbSecret )
    goto LABEL_28;
  return v15;
}

```

## disassembly

```asm
0x18008ce48  mov     rax, rsp
0x18008ce4b  mov     [rax+8], rbx
0x18008ce4f  mov     [rax+20h], r9b
0x18008ce53  mov     [rax+18h], r8
0x18008ce57  push    rbp
0x18008ce58  push    rsi
0x18008ce59  push    rdi
0x18008ce5a  push    r12
0x18008ce5c  push    r13
0x18008ce5e  push    r14
0x18008ce60  push    r15
0x18008ce62  sub     rsp, 40h
0x18008ce66  xor     edi, edi
0x18008ce68  mov     rbp, rcx
0x18008ce6b  mov     [rax+20h], edi
0x18008ce6e  mov     r14d, edi
0x18008ce71  mov     [rax+18h], rdi
0x18008ce75  mov     esi, edi
0x18008ce77  mov     r12d, edi
0x18008ce7a  test    rcx, rcx
0x18008ce7d  jz      loc_18008D04D
0x18008ce83  mov     r13, [rcx+20h]
0x18008ce87  test    r13, r13
0x18008ce8a  jz      loc_18008D04D
0x18008ce90  mov     r15, [rcx+10h]
0x18008ce94  test    r15, r15
0x18008ce97  jz      loc_18008D04D
0x18008ce9d  cmp     [rsp+78h+arg_28], rdi
0x18008cea5  jz      loc_18008D04D
0x18008ceab  lea     r8, [rax+20h]
0x18008ceaf  mov     rcx, r15
0x18008ceb2  lea     rdx, [rax+18h]
0x18008ceb6  call    GetPrfHashInfo
0x18008cebb  mov     ebx, eax
0x18008cebd  test    eax, eax
0x18008cebf  jns     short loc_18008CEE1
0x18008cec1  mov     r9d, 0FF7h
0x18008cec7  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18008cece  lea     rdx, aStatus; "Status"
0x18008ced5  mov     ecx, eax
0x18008ced7  call    DebugTraceError
0x18008cedc  jmp     loc_18008D0B0
0x18008cee1  mov     ebx, 70h ; 'p'
0x18008cee6  mov     ecx, ebx
0x18008cee8  call    MSCryptAlloc
0x18008ceed  mov     rdi, rax
0x18008cef0  test    rax, rax
0x18008cef3  jnz     short loc_18008CF12
0x18008cef5  mov     r14d, [rsp+78h+arg_18]
0x18008cefd  mov     ebx, 8009000Eh
0x18008cf02  mov     ecx, 8009000Eh
0x18008cf07  mov     r9d, 1008h
0x18008cf0d  jmp     loc_18008D05D
0x18008cf12  xor     edx, edx; Val
0x18008cf14  lea     rcx, [rax+8]; void *
0x18008cf18  lea     r8d, [rdx+68h]; Size
0x18008cf1c  call    memset
0x18008cf21  mov     r14d, [rsp+78h+arg_18]
0x18008cf29  mov     [rdi], ebx
0x18008cf2b  mov     ecx, r14d
0x18008cf2e  mov     dword ptr [rdi+4], 73736C33h
0x18008cf35  mov     eax, [rbp+8]
0x18008cf38  mov     [rdi+8], eax
0x18008cf3b  mov     [rdi+10h], r15
0x18008cf3f  mov     dword ptr [rdi+6Ch], 4
0x18008cf46  call    MSCryptAlloc
0x18008cf4b  xor     ebp, ebp
0x18008cf4d  mov     rsi, rax
0x18008cf50  test    rax, rax
0x18008cf53  jnz     short loc_18008CF6A
0x18008cf55  mov     ebx, 8009000Eh
0x18008cf5a  mov     ecx, 8009000Eh
0x18008cf5f  mov     r9d, 1017h
0x18008cf65  jmp     loc_18008D05F
0x18008cf6a  mov     word ptr [rsp+78h+cbSecret], r14w
0x18008cf70  lea     rdx, aTrafficUpd; "traffic upd"
0x18008cf77  xor     r9d, r9d
0x18008cf7a  mov     [rsp+78h+pbSecret], rsi
0x18008cf7f  xor     r8d, r8d
0x18008cf82  mov     rcx, r13
0x18008cf85  call    TlsExpandLabel
0x18008cf8a  mov     ebx, eax
0x18008cf8c  test    eax, eax
0x18008cf8e  jns     short loc_18008CF9D
0x18008cf90  mov     ecx, eax
0x18008cf92  mov     r9d, 1023h
0x18008cf98  jmp     loc_18008D05F
0x18008cf9d  mov     [rsp+78h+dwFlags], ebp; dwFlags
0x18008cfa1  lea     rdx, [rdi+20h]; phKey
0x18008cfa5  mov     [rsp+78h+cbSecret], r14d; cbSecret
0x18008cfaa  xor     r9d, r9d; cbKeyObject
0x18008cfad  xor     r8d, r8d; pbKeyObject
0x18008cfb0  mov     [rsp+78h+pbSecret], rsi; pbSecret
0x18008cfb5  mov     ecx, 391h; hAlgorithm
0x18008cfba  call    BCryptGenerateSymmetricKey
0x18008cfbf  mov     ebx, eax
0x18008cfc1  test    eax, eax
0x18008cfc3  jz      short loc_18008CFD2
0x18008cfc5  mov     ecx, eax
0x18008cfc7  mov     r9d, 1032h
0x18008cfcd  jmp     loc_18008D05F
0x18008cfd2  mov     r12, [rdi+20h]
0x18008cfd6  or      r9, 0FFFFFFFFFFFFFFFFh
0x18008cfda  mov     r8, [rsp+78h+pbInput]; pbInput
0x18008cfe2  inc     r9
0x18008cfe5  cmp     [r8+r9*2], bp
0x18008cfea  jnz     short loc_18008CFE2
0x18008cfec  lea     r9d, ds:2[r9*2]; cbInput
0x18008cff4  mov     dword ptr [rsp+78h+pbSecret], ebp; dwFlags
0x18008cff8  lea     rdx, aHkdfhashalgori; "HkdfHashAlgorithm"
0x18008cfff  mov     rcx, r12; hObject
0x18008d002  call    BCryptSetProperty
0x18008d007  mov     ebx, eax
0x18008d009  test    eax, eax
0x18008d00b  jz      short loc_18008D017
0x18008d00d  mov     ecx, eax
0x18008d00f  mov     r9d, 1040h
0x18008d015  jmp     short loc_18008D05F
0x18008d017  xor     r9d, r9d; cbInput
0x18008d01a  mov     dword ptr [rsp+78h+pbSecret], ebp; dwFlags
0x18008d01e  xor     r8d, r8d; pbInput
0x18008d021  lea     rdx, aHkdfprkandfina; "HkdfPrkAndFinalize"
0x18008d028  mov     rcx, r12; hObject
0x18008d02b  call    BCryptSetProperty
0x18008d030  mov     ebx, eax
0x18008d032  test    eax, eax
0x18008d034  jz      short loc_18008D040
0x18008d036  mov     ecx, eax
0x18008d038  mov     r9d, 104Bh
0x18008d03e  jmp     short loc_18008D05F
0x18008d040  mov     rax, [rsp+78h+arg_28]
0x18008d048  mov     [rax], rdi
0x18008d04b  jmp     short loc_18008D091
0x18008d04d  mov     ebx, 80090027h
0x18008d052  mov     ecx, 80090027h
0x18008d057  mov     r9d, 0FF0h
0x18008d05d  xor     ebp, ebp
0x18008d05f  lea     rdx, aStatus; "Status"
0x18008d066  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18008d06d  call    DebugTraceError
0x18008d072  test    rdi, rdi
0x18008d075  jz      short loc_18008D08C
0x18008d077  test    r12, r12
0x18008d07a  jz      short loc_18008D084
0x18008d07c  mov     rcx, r12; hKey
0x18008d07f  call    BCryptDestroyKey
0x18008d084  mov     rcx, rdi; P
0x18008d087  call    MSCryptFree
0x18008d08c  test    rsi, rsi
0x18008d08f  jz      short loc_18008D0B0
0x18008d091  mov     eax, r14d
0x18008d094  mov     rcx, rsi
0x18008d097  test    r14d, r14d
0x18008d09a  jz      short loc_18008D0A8
0x18008d09c  mov     [rcx], bpl
0x18008d09f  inc     rcx
0x18008d0a2  sub     rax, 1
0x18008d0a6  jnz     short loc_18008D09C
0x18008d0a8  mov     rcx, rsi; P
0x18008d0ab  call    MSCryptFree
0x18008d0b0  mov     eax, ebx
0x18008d0b2  mov     rbx, [rsp+78h+arg_0]
0x18008d0ba  add     rsp, 40h
0x18008d0be  pop     r15
0x18008d0c0  pop     r14
0x18008d0c2  pop     r13
0x18008d0c4  pop     r12
0x18008d0c6  pop     rdi
0x18008d0c7  pop     rsi
0x18008d0c8  pop     rbp
0x18008d0c9  retn
```
