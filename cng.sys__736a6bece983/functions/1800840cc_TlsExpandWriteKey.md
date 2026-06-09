# TlsExpandWriteKey

- ea: `0x1800840cc`
- end: `0x1800843ba`
- name: `TlsExpandWriteKey`
- size: `750`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180082a00`

## callees

- `0x1800020c0`
- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x180036040`
- `0x180038230`
- `0x180083ed4`
- `0x1800840cc`
- `0x18009fa80`

## string_xrefs

- `0x18008416e`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180084339`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

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
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rax
  int v27; // eax
  NTSTATUS SymmetricKey; // eax
  int v29; // eax
  __int64 v30; // rcx
  _BYTE *v31; // rax
  __int64 v32; // rcx
  UCHAR *v33; // rax
  ULONG cbSecret; // [rsp+28h] [rbp-60h]
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+40h] [rbp-48h]
  ULONG v37; // [rsp+90h] [rbp+8h]

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
    v37 = v15 + 112;
    v17 = (char *)MSCryptAlloc(v15 + 112, a2, a3, v9);
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
    v26 = MSCryptAlloc(v7, v23, v24, v25);
    pbSecret = (UCHAR *)v26;
    if ( !v26 )
    {
      v12 = -2146893810;
      v20 = 2148073486LL;
      v21 = 4285;
LABEL_17:
      v19 = v15 + 112;
      v3 = 0;
      goto LABEL_28;
    }
    v27 = TlsExpandLabel(v8, "key", 0, 0, v26, (_WORD)v7);
    v12 = v27;
    if ( v27 < 0 )
    {
      v20 = (unsigned int)v27;
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
    v29 = TlsExpandLabel(v8, "iv", 0, 0, v18 + 56, cbSecret);
    v12 = v29;
    if ( v29 >= 0 )
    {
      *a3 = v18;
LABEL_35:
      v32 = (unsigned int)v7;
      v33 = pbSecret;
      if ( (_DWORD)v7 )
      {
        do
        {
          *v33++ = 0;
          --v32;
        }
        while ( v32 );
      }
      MSCryptFree(pbSecret);
      return v12;
    }
    v19 = v37;
    v20 = (unsigned int)v29;
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
    v30 = v19;
    v31 = v18;
    if ( v19 )
    {
      do
      {
        *v31++ = 0;
        --v30;
      }
      while ( v30 );
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
0x1800840cc  mov     [rsp+arg_8], rbx
0x1800840d1  mov     [rsp+arg_10], r8
0x1800840d6  push    rbp
0x1800840d7  push    rsi
0x1800840d8  push    rdi
0x1800840d9  push    r12
0x1800840db  push    r13
0x1800840dd  push    r14
0x1800840df  push    r15
0x1800840e1  sub     rsp, 50h
0x1800840e5  xor     r13d, r13d
0x1800840e8  xor     ebp, ebp
0x1800840ea  mov     [rsp+88h+arg_18], r13
0x1800840f2  mov     rax, r8
0x1800840f5  mov     rsi, rdx
0x1800840f8  test    rcx, rcx
0x1800840fb  jz      loc_180084322
0x180084101  test    rdx, rdx
0x180084104  jz      loc_180084322
0x18008410a  mov     r14, [rdx+10h]
0x18008410e  test    r14, r14
0x180084111  jz      loc_180084322
0x180084117  test    rax, rax
0x18008411a  jz      loc_180084322
0x180084120  mov     r15d, [r14+20h]
0x180084124  cmp     r15d, 0FFFFh
0x18008412b  ja      loc_18008430D
0x180084131  mov     r12, [rdx+20h]
0x180084135  test    r12, r12
0x180084138  jz      loc_18008430D
0x18008413e  mov     r9d, [r14+28h]
0x180084142  lea     rdi, [r9+1]
0x180084146  shl     rdi, 4
0x18008414a  add     rdi, rcx
0x18008414d  cmp     [rdi+0Ch], ebp
0x180084150  jnz     short loc_180084186
0x180084152  mov     edx, [rcx+0Ch]
0x180084155  mov     r8, rdi
0x180084158  mov     ecx, r9d
0x18008415b  call    I_GetCipherEntry
0x180084160  mov     ebx, eax
0x180084162  test    eax, eax
0x180084164  jns     short loc_180084186
0x180084166  mov     r9d, 109Ah
0x18008416c  mov     ecx, eax
0x18008416e  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180084175  lea     rdx, aStatus; "Status"
0x18008417c  call    DebugTraceError
0x180084181  jmp     loc_18008439F
0x180084186  mov     r13d, [rdi+8]
0x18008418a  test    r13d, r13d
0x18008418d  jz      loc_1800842F8
0x180084193  mov     rax, [rdi]
0x180084196  mov     [rsp+88h+hAlgorithm], rax
0x18008419b  test    rax, rax
0x18008419e  jz      loc_1800842F8
0x1800841a4  lea     ebx, [r13+70h]
0x1800841a8  mov     ecx, ebx
0x1800841aa  mov     [rsp+88h+arg_0], ebx
0x1800841b1  call    MSCryptAlloc
0x1800841b6  mov     rdi, rax
0x1800841b9  test    rax, rax
0x1800841bc  jnz     short loc_1800841DD
0x1800841be  mov     esi, [rsp+88h+arg_0]
0x1800841c5  mov     ebx, 8009000Eh
0x1800841ca  mov     ecx, 8009000Eh
0x1800841cf  mov     r9d, 10ACh
0x1800841d5  mov     r13, rbp
0x1800841d8  jmp     loc_180084339
0x1800841dd  mov     r8d, ebx; Size
0x1800841e0  xor     edx, edx; Val
0x1800841e2  mov     rcx, rdi; void *
0x1800841e5  call    memset
0x1800841ea  mov     [rdi], ebx
0x1800841ec  mov     rcx, r15
0x1800841ef  mov     dword ptr [rdi+4], 73736C33h
0x1800841f6  mov     eax, [rsi+8]
0x1800841f9  mov     [rdi+10h], r14
0x1800841fd  mov     r14d, 0Ch
0x180084203  mov     [rdi+68h], r14d
0x180084207  mov     [rdi+8], eax
0x18008420a  mov     dword ptr [rdi+6Ch], 5
0x180084211  call    MSCryptAlloc
0x180084216  mov     rbp, rax
0x180084219  test    rax, rax
0x18008421c  jnz     short loc_180084242
0x18008421e  mov     ebx, 8009000Eh
0x180084223  mov     ecx, 8009000Eh
0x180084228  mov     r9d, 10BDh
0x18008422e  mov     esi, [rsp+88h+arg_0]
0x180084235  mov     r13, [rsp+88h+arg_18]
0x18008423d  jmp     loc_180084339
0x180084242  mov     word ptr [rsp+88h+cbSecret], r15w
0x180084248  lea     rdx, aKey; "key"
0x18008424f  xor     r9d, r9d
0x180084252  mov     [rsp+88h+pbSecret], rbp
0x180084257  xor     r8d, r8d
0x18008425a  mov     rcx, r12
0x18008425d  call    TlsExpandLabel
0x180084262  mov     ebx, eax
0x180084264  test    eax, eax
0x180084266  jns     short loc_180084272
0x180084268  mov     ecx, eax
0x18008426a  mov     r9d, 10C9h
0x180084270  jmp     short loc_18008422E
0x180084272  mov     rcx, [rsp+88h+hAlgorithm]; hAlgorithm
0x180084277  lea     r8, [rdi+70h]; pbKeyObject
0x18008427b  mov     [rsp+88h+dwFlags], 0; dwFlags
0x180084283  lea     rdx, [rdi+20h]; phKey
0x180084287  mov     [rsp+88h+cbSecret], r15d; cbSecret
0x18008428c  mov     r9d, r13d; cbKeyObject
0x18008428f  mov     [rsp+88h+pbSecret], rbp; pbSecret
0x180084294  call    BCryptGenerateSymmetricKey
0x180084299  mov     ebx, eax
0x18008429b  test    eax, eax
0x18008429d  jns     short loc_1800842A9
0x18008429f  mov     ecx, eax
0x1800842a1  mov     r9d, 10D8h
0x1800842a7  jmp     short loc_18008422E
0x1800842a9  mov     r13, [rdi+20h]
0x1800842ad  lea     rax, [rdi+38h]
0x1800842b1  mov     word ptr [rsp+88h+cbSecret], r14w
0x1800842b7  lea     rdx, aIv; "iv"
0x1800842be  xor     r9d, r9d
0x1800842c1  mov     [rsp+88h+pbSecret], rax
0x1800842c6  xor     r8d, r8d
0x1800842c9  mov     rcx, r12
0x1800842cc  call    TlsExpandLabel
0x1800842d1  mov     ebx, eax
0x1800842d3  test    eax, eax
0x1800842d5  jns     short loc_1800842E8
0x1800842d7  mov     esi, [rsp+88h+arg_0]
0x1800842de  mov     ecx, eax
0x1800842e0  mov     r9d, 10E7h
0x1800842e6  jmp     short loc_180084339
0x1800842e8  mov     rax, [rsp+88h+arg_10]
0x1800842f0  mov     [rax], rdi
0x1800842f3  jmp     loc_180084380
0x1800842f8  mov     ebx, 80090029h
0x1800842fd  mov     r9d, 10A2h
0x180084303  mov     ecx, 80090029h
0x180084308  jmp     loc_18008416E
0x18008430d  mov     ebx, 80090027h
0x180084312  mov     r9d, 108Dh
0x180084318  mov     ecx, 80090027h
0x18008431d  jmp     loc_18008416E
0x180084322  xor     edi, edi
0x180084324  xor     esi, esi
0x180084326  xor     r15d, r15d
0x180084329  mov     ebx, 80090027h
0x18008432e  mov     ecx, 80090027h
0x180084333  mov     r9d, 1084h
0x180084339  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180084340  lea     rdx, aStatus; "Status"
0x180084347  call    DebugTraceError
0x18008434c  test    rdi, rdi
0x18008434f  jz      short loc_18008437B
0x180084351  test    r13, r13
0x180084354  jz      short loc_18008435E
0x180084356  mov     rcx, r13; hKey
0x180084359  call    BCryptDestroyKey
0x18008435e  mov     ecx, esi
0x180084360  mov     rax, rdi
0x180084363  test    esi, esi
0x180084365  jz      short loc_180084373
0x180084367  mov     byte ptr [rax], 0
0x18008436a  inc     rax
0x18008436d  sub     rcx, 1
0x180084371  jnz     short loc_180084367
0x180084373  mov     rcx, rdi; P
0x180084376  call    MSCryptFree
0x18008437b  test    rbp, rbp
0x18008437e  jz      short loc_18008439F
0x180084380  mov     ecx, r15d
0x180084383  mov     rax, rbp
0x180084386  test    r15d, r15d
0x180084389  jz      short loc_180084397
0x18008438b  mov     byte ptr [rax], 0
0x18008438e  inc     rax
0x180084391  sub     rcx, 1
0x180084395  jnz     short loc_18008438B
0x180084397  mov     rcx, rbp; P
0x18008439a  call    MSCryptFree
0x18008439f  mov     eax, ebx
0x1800843a1  mov     rbx, [rsp+88h+arg_8]
0x1800843a9  add     rsp, 50h
0x1800843ad  pop     r15
0x1800843af  pop     r14
0x1800843b1  pop     r13
0x1800843b3  pop     r12
0x1800843b5  pop     rdi
0x1800843b6  pop     rsi
0x1800843b7  pop     rbp
0x1800843b8  retn
```
