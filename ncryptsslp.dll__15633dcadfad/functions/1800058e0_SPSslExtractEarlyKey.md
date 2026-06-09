# SPSslExtractEarlyKey

- ea: `0x1800058e0`
- end: `0x180005ca9`
- name: `SPSslExtractEarlyKey`
- size: `969`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180003ef0`
- `0x180005860`
- `0x1800058e0`
- `0x180005e50`
- `0x1800068e0`
- `0x180007940`
- `0x18000b594`
- `0x18000b654`
- `0x18000cfb0`
- `0x180025660`

## string_xrefs

- `0x180005956`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180005ae3`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180005b4d`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180005ba8`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180005bef`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180005c68`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180005c7f`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslExtractEarlyKey(__int64 a1, _DWORD *a2, __int64 *a3, unsigned int a4, unsigned int a5)
{
  __int64 v9; // r13
  UCHAR *v10; // r14
  void *v11; // r12
  __int64 v12; // rdi
  __int64 v13; // rax
  int v14; // edx
  ULONG v15; // ebx
  unsigned int v16; // ebx
  __int64 v17; // rbp
  wchar_t *v19; // rcx
  __int64 HashInfoFromAlgorithmName; // rax
  size_t v21; // rbp
  UCHAR *v22; // rax
  int v23; // edx
  ULONG v24; // r15d
  void *v25; // rax
  int v26; // edx
  void *v27; // rax
  int v28; // eax
  _BYTE *v29; // rax
  __int64 v30; // r9
  __int64 v31; // rcx

  v9 = LookupCipherSuite(a4, a5);
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v13 = SslpValidateProvHandle(a1);
  v15 = 0;
  if ( !v13 )
  {
    v16 = -2146893786;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        92);
    goto LABEL_5;
  }
  if ( !a3 )
  {
    v16 = -2146893785;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        (unsigned int)"Status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        99);
    goto LABEL_5;
  }
  if ( a4 != 772 || !v9 )
  {
    v16 = -2146893783;
    DebugTraceError(2148073513LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", 5482);
LABEL_5:
    v17 = 112;
    goto LABEL_6;
  }
  v19 = *(wchar_t **)(v9 + 136);
  if ( !v19 || !*v19 )
    v19 = L"SHA256";
  HashInfoFromAlgorithmName = I_GetHashInfoFromAlgorithmName(v19);
  if ( HashInfoFromAlgorithmName )
    v15 = *(_DWORD *)(HashInfoFromAlgorithmName + 8);
  if ( a2 )
  {
    if ( *a2 >= 0x10u && a2[1] == 1936944186 )
    {
      v24 = *a2 - 12;
    }
    else
    {
      if ( *a2 < v15 + 12 || a2[1] != 1936944184 )
      {
        v16 = -2146893786;
        DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", 5510);
        return v16;
      }
      v24 = v15;
    }
    v21 = v15;
    v10 = (UCHAR *)(a2 + 3);
LABEL_21:
    v25 = (void *)SafeAllocaAllocateFromHeap(v21);
    v11 = v25;
    if ( !v25 )
    {
      v16 = -2146893810;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v26,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
          (unsigned int)"Status",
          14,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
          167);
      goto LABEL_5;
    }
    memset(v25, 0, v21);
    v17 = 112;
    v27 = (void *)SafeAllocaAllocateFromHeap(112);
    v12 = (__int64)v27;
    if ( v27 )
    {
      memset(v27, 0, 0x70u);
      *(_DWORD *)v12 = 112;
      *(_DWORD *)(v12 + 4) = 1936944179;
      *(_DWORD *)(v12 + 8) = 772;
      *(_QWORD *)(v12 + 16) = v9;
      *(_DWORD *)(v12 + 108) = 1;
      v28 = TlsHkdfExtract(v10, v24, v12);
      v16 = v28;
      if ( v28 >= 0 )
      {
        *a3 = v12;
        v12 = 0;
        goto LABEL_6;
      }
      v30 = 5578;
      v31 = (unsigned int)v28;
    }
    else
    {
      v16 = -2146893810;
      v30 = 5556;
      v31 = 2148073486LL;
    }
    DebugTraceError(v31, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v30);
LABEL_6:
    if ( !a2 && v10 )
      MSCryptFree(v10);
    if ( v11 )
      MSCryptFree(v11);
    if ( v12 )
    {
      v29 = (_BYTE *)v12;
      do
      {
        *v29++ = 0;
        --v17;
      }
      while ( v17 );
      MSCryptFree(v12);
    }
    return v16;
  }
  v21 = v15;
  v22 = (UCHAR *)SafeAllocaAllocateFromHeap(v15);
  v10 = v22;
  if ( v22 )
  {
    memset(v22, 0, v15);
    v24 = v15;
    goto LABEL_21;
  }
  v16 = -2146893810;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v23,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
      (unsigned int)"Status",
      14,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
      152);
  return v16;
}

```

## disassembly

```asm
0x1800058e0  mov     [rsp+arg_10], r8
0x1800058e5  push    rbx
0x1800058e6  push    rbp
0x1800058e7  push    rsi
0x1800058e8  push    rdi
0x1800058e9  push    r12
0x1800058eb  push    r13
0x1800058ed  push    r14
0x1800058ef  push    r15
0x1800058f1  sub     rsp, 48h
0x1800058f5  mov     rsi, rdx
0x1800058f8  mov     rbx, rcx
0x1800058fb  mov     edx, [rsp+88h+arg_20]
0x180005902  mov     ecx, r9d
0x180005905  mov     ebp, r9d
0x180005908  mov     r15, r8
0x18000590b  call    LookupCipherSuite
0x180005910  mov     r13, rax
0x180005913  mov     rcx, rbx
0x180005916  xor     eax, eax
0x180005918  mov     r14d, eax
0x18000591b  mov     r12d, eax
0x18000591e  mov     edi, eax
0x180005920  call    SslpValidateProvHandle
0x180005925  xor     ebx, ebx
0x180005927  test    rax, rax
0x18000592a  jnz     loc_1800059B1
0x180005930  mov     ebx, 80090026h
0x180005935  mov     rcx, cs:WPP_GLOBAL_Control
0x18000593c  lea     rax, WPP_GLOBAL_Control
0x180005943  cmp     rcx, rax
0x180005946  jz      short loc_18000597A
0x180005948  test    byte ptr [rcx+1Ch], 1
0x18000594c  jz      short loc_18000597A
0x18000594e  mov     [rsp+88h+var_58], 155Ch
0x180005956  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000595d  mov     [rsp+88h+var_60], r8
0x180005962  mov     dword ptr [rsp+88h+var_68], 80090026h
0x18000596a  mov     rcx, [rcx+10h]
0x18000596e  lea     r9, aStatus; "Status"
0x180005975  call    WPP_SF_sDsd
0x18000597a  mov     ebp, 70h ; 'p'
0x18000597f  test    rsi, rsi
0x180005982  jz      loc_180005B0D
0x180005988  test    r12, r12
0x18000598b  jz      short loc_180005995
0x18000598d  mov     rcx, r12
0x180005990  call    MSCryptFree
0x180005995  test    rdi, rdi
0x180005998  jnz     loc_180005CA1
0x18000599e  mov     eax, ebx
0x1800059a0  add     rsp, 48h
0x1800059a4  pop     r15
0x1800059a6  pop     r14
0x1800059a8  pop     r13
0x1800059aa  pop     r12
0x1800059ac  pop     rdi
0x1800059ad  pop     rsi
0x1800059ae  pop     rbp
0x1800059af  pop     rbx
0x1800059b0  retn
0x1800059b1  test    r15, r15
0x1800059b4  jz      loc_180005B7A
0x1800059ba  cmp     ebp, 304h
0x1800059c0  jnz     loc_180005C79
0x1800059c6  test    r13, r13
0x1800059c9  jz      loc_180005C79
0x1800059cf  mov     rcx, [r13+88h]; String1
0x1800059d6  test    rcx, rcx
0x1800059d9  jz      loc_180005C08
0x1800059df  cmp     [rcx], bx
0x1800059e2  jz      loc_180005C08
0x1800059e8  call    I_GetHashInfoFromAlgorithmName
0x1800059ed  test    rax, rax
0x1800059f0  jnz     loc_180005B05
0x1800059f6  test    rsi, rsi
0x1800059f9  jnz     loc_180005AB7
0x1800059ff  mov     ecx, ebx
0x180005a01  mov     ebp, ebx
0x180005a03  call    SafeAllocaAllocateFromHeap
0x180005a08  mov     r14, rax
0x180005a0b  test    rax, rax
0x180005a0e  jz      loc_180005B23
0x180005a14  mov     r8d, ebp; Size
0x180005a17  xor     edx, edx; Val
0x180005a19  mov     rcx, rax; void *
0x180005a1c  call    memset
0x180005a21  mov     r15d, ebx
0x180005a24  mov     rcx, rbp
0x180005a27  call    SafeAllocaAllocateFromHeap
0x180005a2c  mov     r12, rax
0x180005a2f  test    rax, rax
0x180005a32  jz      loc_180005BC1
0x180005a38  mov     r8, rbp; Size
0x180005a3b  xor     edx, edx; Val
0x180005a3d  mov     rcx, rax; void *
0x180005a40  call    memset
0x180005a45  mov     ebp, 70h ; 'p'
0x180005a4a  mov     ecx, ebp
0x180005a4c  call    SafeAllocaAllocateFromHeap
0x180005a51  mov     rdi, rax
0x180005a54  test    rax, rax
0x180005a57  jz      loc_180005C47
0x180005a5d  mov     r8d, ebp; Size
0x180005a60  xor     edx, edx; Val
0x180005a62  mov     rcx, rax; void *
0x180005a65  call    memset
0x180005a6a  mov     r9d, ebx
0x180005a6d  mov     [rdi], ebp
0x180005a6f  mov     r8, r12
0x180005a72  mov     dword ptr [rdi+4], 73736C33h
0x180005a79  mov     edx, r15d; cbSecret
0x180005a7c  mov     dword ptr [rdi+8], 304h
0x180005a83  mov     rcx, r14; pbSecret
0x180005a86  mov     [rdi+10h], r13
0x180005a8a  mov     dword ptr [rdi+6Ch], 1
0x180005a91  mov     [rsp+88h+var_68], rdi; __int64
0x180005a96  call    TlsHkdfExtract
0x180005a9b  mov     ebx, eax
0x180005a9d  test    eax, eax
0x180005a9f  js      loc_180005C59
0x180005aa5  mov     rax, [rsp+88h+arg_10]
0x180005aad  mov     [rax], rdi
0x180005ab0  xor     edi, edi
0x180005ab2  jmp     loc_18000597F
0x180005ab7  cmp     dword ptr [rsi], 10h
0x180005aba  jb      short loc_180005AC9
0x180005abc  cmp     dword ptr [rsi+4], 73736C3Ah
0x180005ac3  jz      loc_180005C2D
0x180005ac9  lea     eax, [rbx+0Ch]
0x180005acc  cmp     [rsi], eax
0x180005ace  jb      short loc_180005ADD
0x180005ad0  cmp     dword ptr [rsi+4], 73736C38h
0x180005ad7  jz      loc_180005C36
0x180005add  mov     r9d, 1586h
0x180005ae3  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005aea  lea     rdx, aStatus; "Status"
0x180005af1  mov     ecx, 80090026h
0x180005af6  mov     ebx, 80090026h
0x180005afb  call    DebugTraceError
0x180005b00  jmp     loc_18000599E
0x180005b05  mov     ebx, [rax+8]
0x180005b08  jmp     loc_1800059F6
0x180005b0d  test    r14, r14
0x180005b10  jz      loc_180005988
0x180005b16  mov     rcx, r14
0x180005b19  call    MSCryptFree
0x180005b1e  jmp     loc_180005988
0x180005b23  mov     ebx, 8009000Eh
0x180005b28  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b2f  lea     rax, WPP_GLOBAL_Control
0x180005b36  cmp     rcx, rax
0x180005b39  jz      loc_18000599E
0x180005b3f  test    byte ptr [rcx+1Ch], 1
0x180005b43  jz      loc_18000599E
0x180005b49  mov     rcx, [rcx+10h]
0x180005b4d  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005b54  mov     [rsp+88h+var_58], 1598h
0x180005b5c  lea     r9, aStatus; "Status"
0x180005b63  mov     [rsp+88h+var_60], r8
0x180005b68  mov     dword ptr [rsp+88h+var_68], 8009000Eh
0x180005b70  call    WPP_SF_sDsd
0x180005b75  jmp     loc_18000599E
0x180005b7a  mov     ebx, 80090027h
0x180005b7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b86  lea     rax, WPP_GLOBAL_Control
0x180005b8d  cmp     rcx, rax
0x180005b90  jz      loc_18000597A
0x180005b96  test    byte ptr [rcx+1Ch], 1
0x180005b9a  jz      loc_18000597A
0x180005ba0  mov     [rsp+88h+var_58], 1563h
0x180005ba8  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005baf  mov     [rsp+88h+var_60], r8
0x180005bb4  mov     dword ptr [rsp+88h+var_68], 80090027h
0x180005bbc  jmp     loc_18000596A
0x180005bc1  mov     ebx, 8009000Eh
0x180005bc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180005bcd  lea     rax, WPP_GLOBAL_Control
0x180005bd4  cmp     rcx, rax
0x180005bd7  jz      loc_18000597A
0x180005bdd  test    byte ptr [rcx+1Ch], 1
0x180005be1  jz      loc_18000597A
0x180005be7  mov     [rsp+88h+var_58], 15A7h
0x180005bef  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005bf6  mov     [rsp+88h+var_60], r8
0x180005bfb  mov     dword ptr [rsp+88h+var_68], 8009000Eh
0x180005c03  jmp     loc_18000596A
0x180005c08  lea     rcx, aSha256; "SHA256"
0x180005c0f  jmp     loc_1800059E8
0x180005c14  mov     byte ptr [rax], 0
0x180005c17  inc     rax
0x180005c1a  sub     rbp, 1
0x180005c1e  jnz     short loc_180005C14
0x180005c20  mov     rcx, rdi
0x180005c23  call    MSCryptFree
0x180005c28  jmp     loc_18000599E
0x180005c2d  mov     r15d, [rsi]
0x180005c30  sub     r15d, 0Ch
0x180005c34  jmp     short loc_180005C39
0x180005c36  mov     r15d, ebx
0x180005c39  mov     r14, rsi
0x180005c3c  mov     ebp, ebx
0x180005c3e  add     r14, 0Ch
0x180005c42  jmp     loc_180005A24
0x180005c47  mov     ebx, 8009000Eh
0x180005c4c  mov     r9d, 15B4h
0x180005c52  mov     ecx, 8009000Eh
0x180005c57  jmp     short loc_180005C61
0x180005c59  mov     r9d, 15CAh
0x180005c5f  mov     ecx, eax
0x180005c61  lea     rdx, aStatus; "Status"
0x180005c68  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005c6f  call    DebugTraceError
0x180005c74  jmp     loc_18000597F
0x180005c79  mov     r9d, 156Ah
0x180005c7f  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005c86  lea     rdx, aStatus; "Status"
0x180005c8d  mov     ecx, 80090029h
0x180005c92  mov     ebx, 80090029h
0x180005c97  call    DebugTraceError
0x180005c9c  jmp     loc_18000597A
0x180005ca1  mov     rax, rdi
0x180005ca4  jmp     loc_180005C14
```
