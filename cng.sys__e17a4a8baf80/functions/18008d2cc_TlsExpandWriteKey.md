# TlsExpandWriteKey

- ea: `0x18008d2cc`
- end: `0x18008d5ba`
- name: `TlsExpandWriteKey`
- size: `750`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18008bc00`

## callees

- `0x18000c1e0`
- `0x18000e090`
- `0x180010590`
- `0x18001155c`
- `0x18003f5b0`
- `0x1800417a0`
- `0x18008d0d4`
- `0x18008d2cc`
- `0x1800a4380`

## string_xrefs

- `0x18008d36e`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18008d539`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

## pseudocode

```c
__int64 __fastcall TlsExpandWriteKey(__int64 a1, __int64 a2, _QWORD *a3)
{
  void *v3; // r13
  UCHAR *pbSecret; // rbp
  __int64 v6; // r14
  __int64 v7; // r15
  __int64 v8; // r12
  __int64 v9; // r9
  __int64 v10; // rdi
  int CipherEntry; // eax
  unsigned int v12; // ebx
  __int64 v13; // r9
  __int64 v14; // rcx
  ULONG v15; // r13d
  ULONG v16; // ebx
  char *v17; // rax
  char *v18; // rdi
  ULONG v19; // esi
  __int64 v20; // rcx
  __int64 v21; // r9
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rax
  int v25; // eax
  NTSTATUS SymmetricKey; // eax
  int v27; // eax
  __int64 v28; // rcx
  _BYTE *v29; // rax
  __int64 v30; // rcx
  UCHAR *v31; // rax
  ULONG cbSecret; // [rsp+28h] [rbp-60h]
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+40h] [rbp-48h]
  ULONG v35; // [rsp+90h] [rbp+8h]

  v3 = 0;
  pbSecret = 0;
  if ( a1 && a2 && (v6 = *(_QWORD *)(a2 + 16)) != 0 && a3 )
  {
    v7 = *(unsigned int *)(v6 + 32);
    if ( (unsigned int)v7 > 0xFFFF || (v8 = *(_QWORD *)(a2 + 32)) == 0 )
    {
      v12 = -2146893785;
      v13 = 4237;
      v14 = 2148073511LL;
      goto LABEL_10;
    }
    v9 = *(unsigned int *)(v6 + 40);
    v10 = a1 + 16 * (v9 + 1);
    if ( !*(_DWORD *)(v10 + 12) )
    {
      CipherEntry = I_GetCipherEntry(v9, *(_DWORD *)(a1 + 12), a1 + 16 * (v9 + 1));
      v12 = CipherEntry;
      if ( CipherEntry < 0 )
      {
        v13 = 4250;
        v14 = (unsigned int)CipherEntry;
LABEL_10:
        DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", v13);
        return v12;
      }
    }
    v15 = *(_DWORD *)(v10 + 8);
    if ( !v15 || (hAlgorithm = *(BCRYPT_ALG_HANDLE *)v10) == 0 )
    {
      v12 = -2146893783;
      v13 = 4258;
      v14 = 2148073513LL;
      goto LABEL_10;
    }
    v16 = v15 + 112;
    v35 = v15 + 112;
    v17 = (char *)MSCryptAlloc(v15 + 112, a2);
    v18 = v17;
    if ( !v17 )
    {
      v19 = v15 + 112;
      v12 = -2146893810;
      v20 = 2148073486LL;
      v21 = 4268;
      v3 = 0;
      goto LABEL_28;
    }
    memset(v17, 0, v16);
    *(_DWORD *)v18 = v16;
    *((_DWORD *)v18 + 1) = 1936944179;
    v22 = *(_DWORD *)(a2 + 8);
    *((_QWORD *)v18 + 2) = v6;
    *((_DWORD *)v18 + 26) = 12;
    *((_DWORD *)v18 + 2) = v22;
    *((_DWORD *)v18 + 27) = 5;
    v24 = MSCryptAlloc(v7, v23);
    pbSecret = (UCHAR *)v24;
    if ( !v24 )
    {
      v12 = -2146893810;
      v20 = 2148073486LL;
      v21 = 4285;
LABEL_17:
      v19 = v15 + 112;
      v3 = 0;
      goto LABEL_28;
    }
    v25 = TlsExpandLabel(v8, "key", 0, 0, v24, (_WORD)v7);
    v12 = v25;
    if ( v25 < 0 )
    {
      v20 = (unsigned int)v25;
      v21 = 4297;
      goto LABEL_17;
    }
    SymmetricKey = BCryptGenerateSymmetricKey(
                     hAlgorithm,
                     (BCRYPT_KEY_HANDLE *)v18 + 4,
                     (PUCHAR)v18 + 112,
                     v15,
                     pbSecret,
                     v7,
                     0);
    v12 = SymmetricKey;
    if ( SymmetricKey < 0 )
    {
      v20 = (unsigned int)SymmetricKey;
      v21 = 4312;
      goto LABEL_17;
    }
    v3 = (void *)*((_QWORD *)v18 + 4);
    LOWORD(cbSecret) = 12;
    v27 = TlsExpandLabel(v8, "iv", 0, 0, v18 + 56, cbSecret);
    v12 = v27;
    if ( v27 >= 0 )
    {
      *a3 = v18;
LABEL_35:
      v30 = (unsigned int)v7;
      v31 = pbSecret;
      if ( (_DWORD)v7 )
      {
        do
        {
          *v31++ = 0;
          --v30;
        }
        while ( v30 );
      }
      MSCryptFree(pbSecret);
      return v12;
    }
    v19 = v35;
    v20 = (unsigned int)v27;
    v21 = 4327;
  }
  else
  {
    v18 = 0;
    v19 = 0;
    LODWORD(v7) = 0;
    v12 = -2146893785;
    v20 = 2148073511LL;
    v21 = 4228;
  }
LABEL_28:
  DebugTraceError(v20, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", v21);
  if ( v18 )
  {
    if ( v3 )
      BCryptDestroyKey(v3);
    v28 = v19;
    v29 = v18;
    if ( v19 )
    {
      do
      {
        *v29++ = 0;
        --v28;
      }
      while ( v28 );
    }
    MSCryptFree(v18);
  }
  if ( pbSecret )
    goto LABEL_35;
  return v12;
}

```

## disassembly

```asm
0x18008d2cc  mov     [rsp+arg_8], rbx
0x18008d2d1  mov     [rsp+arg_10], r8
0x18008d2d6  push    rbp
0x18008d2d7  push    rsi
0x18008d2d8  push    rdi
0x18008d2d9  push    r12
0x18008d2db  push    r13
0x18008d2dd  push    r14
0x18008d2df  push    r15
0x18008d2e1  sub     rsp, 50h
0x18008d2e5  xor     r13d, r13d
0x18008d2e8  xor     ebp, ebp
0x18008d2ea  mov     [rsp+88h+arg_18], r13
0x18008d2f2  mov     rax, r8
0x18008d2f5  mov     rsi, rdx
0x18008d2f8  test    rcx, rcx
0x18008d2fb  jz      loc_18008D522
0x18008d301  test    rdx, rdx
0x18008d304  jz      loc_18008D522
0x18008d30a  mov     r14, [rdx+10h]
0x18008d30e  test    r14, r14
0x18008d311  jz      loc_18008D522
0x18008d317  test    rax, rax
0x18008d31a  jz      loc_18008D522
0x18008d320  mov     r15d, [r14+20h]
0x18008d324  cmp     r15d, 0FFFFh
0x18008d32b  ja      loc_18008D50D
0x18008d331  mov     r12, [rdx+20h]
0x18008d335  test    r12, r12
0x18008d338  jz      loc_18008D50D
0x18008d33e  mov     r9d, [r14+28h]
0x18008d342  lea     rdi, [r9+1]
0x18008d346  shl     rdi, 4
0x18008d34a  add     rdi, rcx
0x18008d34d  cmp     [rdi+0Ch], ebp
0x18008d350  jnz     short loc_18008D386
0x18008d352  mov     edx, [rcx+0Ch]
0x18008d355  mov     r8, rdi
0x18008d358  mov     ecx, r9d
0x18008d35b  call    I_GetCipherEntry
0x18008d360  mov     ebx, eax
0x18008d362  test    eax, eax
0x18008d364  jns     short loc_18008D386
0x18008d366  mov     r9d, 109Ah
0x18008d36c  mov     ecx, eax
0x18008d36e  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18008d375  lea     rdx, aStatus; "Status"
0x18008d37c  call    DebugTraceError
0x18008d381  jmp     loc_18008D59F
0x18008d386  mov     r13d, [rdi+8]
0x18008d38a  test    r13d, r13d
0x18008d38d  jz      loc_18008D4F8
0x18008d393  mov     rax, [rdi]
0x18008d396  mov     [rsp+88h+hAlgorithm], rax
0x18008d39b  test    rax, rax
0x18008d39e  jz      loc_18008D4F8
0x18008d3a4  lea     ebx, [r13+70h]
0x18008d3a8  mov     ecx, ebx
0x18008d3aa  mov     [rsp+88h+arg_0], ebx
0x18008d3b1  call    MSCryptAlloc
0x18008d3b6  mov     rdi, rax
0x18008d3b9  test    rax, rax
0x18008d3bc  jnz     short loc_18008D3DD
0x18008d3be  mov     esi, [rsp+88h+arg_0]
0x18008d3c5  mov     ebx, 8009000Eh
0x18008d3ca  mov     ecx, 8009000Eh
0x18008d3cf  mov     r9d, 10ACh
0x18008d3d5  mov     r13, rbp
0x18008d3d8  jmp     loc_18008D539
0x18008d3dd  mov     r8d, ebx; Size
0x18008d3e0  xor     edx, edx; Val
0x18008d3e2  mov     rcx, rdi; void *
0x18008d3e5  call    memset
0x18008d3ea  mov     [rdi], ebx
0x18008d3ec  mov     rcx, r15
0x18008d3ef  mov     dword ptr [rdi+4], 73736C33h
0x18008d3f6  mov     eax, [rsi+8]
0x18008d3f9  mov     [rdi+10h], r14
0x18008d3fd  mov     r14d, 0Ch
0x18008d403  mov     [rdi+68h], r14d
0x18008d407  mov     [rdi+8], eax
0x18008d40a  mov     dword ptr [rdi+6Ch], 5
0x18008d411  call    MSCryptAlloc
0x18008d416  mov     rbp, rax
0x18008d419  test    rax, rax
0x18008d41c  jnz     short loc_18008D442
0x18008d41e  mov     ebx, 8009000Eh
0x18008d423  mov     ecx, 8009000Eh
0x18008d428  mov     r9d, 10BDh
0x18008d42e  mov     esi, [rsp+88h+arg_0]
0x18008d435  mov     r13, [rsp+88h+arg_18]
0x18008d43d  jmp     loc_18008D539
0x18008d442  mov     word ptr [rsp+88h+cbSecret], r15w
0x18008d448  lea     rdx, aKey; "key"
0x18008d44f  xor     r9d, r9d
0x18008d452  mov     [rsp+88h+pbSecret], rbp
0x18008d457  xor     r8d, r8d
0x18008d45a  mov     rcx, r12
0x18008d45d  call    TlsExpandLabel
0x18008d462  mov     ebx, eax
0x18008d464  test    eax, eax
0x18008d466  jns     short loc_18008D472
0x18008d468  mov     ecx, eax
0x18008d46a  mov     r9d, 10C9h
0x18008d470  jmp     short loc_18008D42E
0x18008d472  mov     rcx, [rsp+88h+hAlgorithm]; hAlgorithm
0x18008d477  lea     r8, [rdi+70h]; pbKeyObject
0x18008d47b  mov     [rsp+88h+dwFlags], 0; dwFlags
0x18008d483  lea     rdx, [rdi+20h]; phKey
0x18008d487  mov     [rsp+88h+cbSecret], r15d; cbSecret
0x18008d48c  mov     r9d, r13d; cbKeyObject
0x18008d48f  mov     [rsp+88h+pbSecret], rbp; pbSecret
0x18008d494  call    BCryptGenerateSymmetricKey
0x18008d499  mov     ebx, eax
0x18008d49b  test    eax, eax
0x18008d49d  jns     short loc_18008D4A9
0x18008d49f  mov     ecx, eax
0x18008d4a1  mov     r9d, 10D8h
0x18008d4a7  jmp     short loc_18008D42E
0x18008d4a9  mov     r13, [rdi+20h]
0x18008d4ad  lea     rax, [rdi+38h]
0x18008d4b1  mov     word ptr [rsp+88h+cbSecret], r14w
0x18008d4b7  lea     rdx, aIv; "iv"
0x18008d4be  xor     r9d, r9d
0x18008d4c1  mov     [rsp+88h+pbSecret], rax
0x18008d4c6  xor     r8d, r8d
0x18008d4c9  mov     rcx, r12
0x18008d4cc  call    TlsExpandLabel
0x18008d4d1  mov     ebx, eax
0x18008d4d3  test    eax, eax
0x18008d4d5  jns     short loc_18008D4E8
0x18008d4d7  mov     esi, [rsp+88h+arg_0]
0x18008d4de  mov     ecx, eax
0x18008d4e0  mov     r9d, 10E7h
0x18008d4e6  jmp     short loc_18008D539
0x18008d4e8  mov     rax, [rsp+88h+arg_10]
0x18008d4f0  mov     [rax], rdi
0x18008d4f3  jmp     loc_18008D580
0x18008d4f8  mov     ebx, 80090029h
0x18008d4fd  mov     r9d, 10A2h
0x18008d503  mov     ecx, 80090029h
0x18008d508  jmp     loc_18008D36E
0x18008d50d  mov     ebx, 80090027h
0x18008d512  mov     r9d, 108Dh
0x18008d518  mov     ecx, 80090027h
0x18008d51d  jmp     loc_18008D36E
0x18008d522  xor     edi, edi
0x18008d524  xor     esi, esi
0x18008d526  xor     r15d, r15d
0x18008d529  mov     ebx, 80090027h
0x18008d52e  mov     ecx, 80090027h
0x18008d533  mov     r9d, 1084h
0x18008d539  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18008d540  lea     rdx, aStatus; "Status"
0x18008d547  call    DebugTraceError
0x18008d54c  test    rdi, rdi
0x18008d54f  jz      short loc_18008D57B
0x18008d551  test    r13, r13
0x18008d554  jz      short loc_18008D55E
0x18008d556  mov     rcx, r13; hKey
0x18008d559  call    BCryptDestroyKey
0x18008d55e  mov     ecx, esi
0x18008d560  mov     rax, rdi
0x18008d563  test    esi, esi
0x18008d565  jz      short loc_18008D573
0x18008d567  mov     byte ptr [rax], 0
0x18008d56a  inc     rax
0x18008d56d  sub     rcx, 1
0x18008d571  jnz     short loc_18008D567
0x18008d573  mov     rcx, rdi; P
0x18008d576  call    MSCryptFree
0x18008d57b  test    rbp, rbp
0x18008d57e  jz      short loc_18008D59F
0x18008d580  mov     ecx, r15d
0x18008d583  mov     rax, rbp
0x18008d586  test    r15d, r15d
0x18008d589  jz      short loc_18008D597
0x18008d58b  mov     byte ptr [rax], 0
0x18008d58e  inc     rax
0x18008d591  sub     rcx, 1
0x18008d595  jnz     short loc_18008D58B
0x18008d597  mov     rcx, rbp; P
0x18008d59a  call    MSCryptFree
0x18008d59f  mov     eax, ebx
0x18008d5a1  mov     rbx, [rsp+88h+arg_8]
0x18008d5a9  add     rsp, 50h
0x18008d5ad  pop     r15
0x18008d5af  pop     r14
0x18008d5b1  pop     r13
0x18008d5b3  pop     r12
0x18008d5b5  pop     rdi
0x18008d5b6  pop     rsi
0x18008d5b7  pop     rbp
0x18008d5b8  retn
```
