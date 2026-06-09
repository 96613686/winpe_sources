# BCryptResolveProvidersForBcoapCached

- ea: `0x18003a740`
- end: `0x18003a824`
- name: `BCryptResolveProvidersForBcoapCached`
- size: `228`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, LPCWSTR pszProvider, ULONG dwFlags, ULONG *pcbBuffer, PCRYPT_PROVIDER_REFS *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180045440`

## callees

- `0x18000743c`
- `0x180018e40`
- `0x180018f30`
- `0x180025c00`
- `0x180036d70`
- `0x18003a740`

## string_xrefs

- `0x1800a2f79`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800a2fac`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800a2fe5`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
__int64 __fastcall BCryptResolveProvidersForBcoapCached(
        STRSAFE_LPCWSTR pszSrc,
        LPCWSTR pszProvider,
        ULONG dwFlags,
        ULONG *pcbBuffer,
        PCRYPT_PROVIDER_REFS *ppBuffer,
        bool *a6)
{
  __int64 v8; // r10
  STRSAFE_LPCWSTR v9; // rax
  int v10; // ecx
  int v11; // edx
  unsigned int v12; // esi
  bool v13; // di
  NTSTATUS v15; // eax
  __int64 v16; // rax
  _QWORD *v17; // rbx
  signed __int64 v18; // rax
  signed __int64 v19; // rcx

  if ( pszProvider || dwFlags != 2 )
  {
    v12 = BCryptResolveProviders(0, 0, pszSrc, pszProvider, 2u, dwFlags, pcbBuffer, ppBuffer);
    v13 = *ppBuffer != 0;
  }
  else
  {
    v8 = g_pResolveProviderCache;
    if ( g_pResolveProviderCache )
    {
      while ( 1 )
      {
        v9 = pszSrc;
        do
        {
          v10 = *(STRSAFE_LPCWSTR)((char *)v9 + v8 + 20 - (_QWORD)pszSrc);
          v11 = *v9 - v10;
          if ( v11 )
            break;
          ++v9;
        }
        while ( v10 );
        if ( !v11 )
          break;
        v8 = *(_QWORD *)v8;
        if ( !v8 )
          goto LABEL_12;
      }
      v12 = 0;
      *pcbBuffer = *(_DWORD *)(v8 + 16);
      v13 = 0;
      *ppBuffer = *(PCRYPT_PROVIDER_REFS *)(v8 + 8);
    }
    else
    {
LABEL_12:
      v15 = BCryptResolveProviders(0, 0, pszSrc, 0, 2u, 2u, pcbBuffer, ppBuffer);
      v12 = v15;
      v13 = *ppBuffer != 0;
      if ( v15 >= 0 )
      {
        v16 = BCryptAlloc(64);
        v17 = (_QWORD *)v16;
        if ( v16 )
        {
          if ( StringCchCopyW((STRSAFE_LPWSTR)(v16 + 20), 0x14u, pszSrc) )
          {
            DebugTraceError(
              3221225507LL,
              "STATUS_BUFFER_TOO_SMALL",
              "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
              1546);
            BCryptFree(v17);
          }
          else
          {
            *((_DWORD *)v17 + 4) = *pcbBuffer;
            v17[1] = *ppBuffer;
            v18 = g_pResolveProviderCache;
            do
            {
              *v17 = v18;
              v19 = v18;
              v18 = _InterlockedCompareExchange64(&g_pResolveProviderCache, (signed __int64)v17, v18);
            }
            while ( v19 != v18 );
            v13 = 0;
          }
        }
        else
        {
          DebugTraceError(
            3221225495LL,
            "STATUS_NO_MEMORY",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
            1539);
        }
      }
      else
      {
        DebugTraceError((unsigned int)v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 1532);
      }
    }
  }
  *a6 = v13;
  return v12;
}

```

## disassembly

```asm
0x18003a740  push    rbx
0x18003a742  push    rbp
0x18003a743  push    rsi
0x18003a744  push    rdi
0x18003a745  push    r14
0x18003a747  push    r15
0x18003a749  sub     rsp, 48h
0x18003a74d  mov     r15, r9
0x18003a750  mov     rbp, rcx
0x18003a753  test    rdx, rdx
0x18003a756  jnz     short loc_18003A7CE
0x18003a758  cmp     r8d, 2
0x18003a75c  jnz     short loc_18003A7CE
0x18003a75e  mov     r10, cs:g_pResolveProviderCache
0x18003a765  test    r10, r10
0x18003a768  jz      loc_1800A2F34
0x18003a76e  lea     r8, [r10+14h]
0x18003a772  mov     rax, rbp
0x18003a775  sub     r8, rbp
0x18003a778  nop     dword ptr [rax+rax+00000000h]
0x18003a780  movzx   edx, word ptr [rax]
0x18003a783  movzx   ecx, word ptr [rax+r8]
0x18003a788  sub     edx, ecx
0x18003a78a  jnz     short loc_18003A794
0x18003a78c  add     rax, 2
0x18003a790  test    ecx, ecx
0x18003a792  jnz     short loc_18003A780
0x18003a794  test    edx, edx
0x18003a796  jnz     short loc_18003A813
0x18003a798  mov     eax, [r10+10h]
0x18003a79c  xor     esi, esi
0x18003a79e  mov     [r9], eax
0x18003a7a1  xor     dil, dil
0x18003a7a4  mov     rax, [rsp+78h+arg_20]
0x18003a7ac  mov     rcx, [r10+8]
0x18003a7b0  mov     [rax], rcx
0x18003a7b3  mov     rax, [rsp+78h+arg_28]
0x18003a7bb  mov     [rax], dil
0x18003a7be  mov     eax, esi
0x18003a7c0  add     rsp, 48h
0x18003a7c4  pop     r15
0x18003a7c6  pop     r14
0x18003a7c8  pop     rdi
0x18003a7c9  pop     rsi
0x18003a7ca  pop     rbp
0x18003a7cb  pop     rbx
0x18003a7cc  retn
0x18003a7ce  mov     rbx, [rsp+78h+arg_20]
0x18003a7d6  mov     r9, rdx; pszProvider
0x18003a7d9  mov     [rsp+78h+ppBuffer], rbx; ppBuffer
0x18003a7de  xor     edx, edx; dwInterface
0x18003a7e0  mov     [rsp+78h+pcbBuffer], r15; pcbBuffer
0x18003a7e5  xor     ecx, ecx; pszContext
0x18003a7e7  mov     [rsp+78h+dwFlags], r8d; dwFlags
0x18003a7ec  xor     dil, dil
0x18003a7ef  mov     r8, rbp; pszFunction
0x18003a7f2  mov     [rsp+78h+dwMode], 2; dwMode
0x18003a7fa  call    BCryptResolveProviders
0x18003a7ff  cmp     qword ptr [rbx], 0
0x18003a803  mov     esi, eax
0x18003a805  mov     eax, 1
0x18003a80a  movzx   edi, dil
0x18003a80e  cmovnz  edi, eax
0x18003a811  jmp     short loc_18003A7B3
0x18003a813  mov     r10, [r10]
0x18003a816  test    r10, r10
0x18003a819  jnz     loc_18003A76E
0x18003a81f  jmp     loc_1800A2F34
0x1800a2f34  mov     r14, [rsp+78h+arg_20]
0x1800a2f3c  xor     r9d, r9d; pszProvider
0x1800a2f3f  mov     [rsp+78h+ppBuffer], r14; ppBuffer
0x1800a2f44  mov     r8, rbp; pszFunction
0x1800a2f47  mov     [rsp+78h+pcbBuffer], r15; pcbBuffer
0x1800a2f4c  xor     edx, edx; dwInterface
0x1800a2f4e  mov     [rsp+78h+dwFlags], 2; dwFlags
0x1800a2f56  xor     ecx, ecx; pszContext
0x1800a2f58  mov     [rsp+78h+dwMode], 2; dwMode
0x1800a2f60  call    BCryptResolveProviders
0x1800a2f65  cmp     qword ptr [r14], 0
0x1800a2f69  mov     esi, eax
0x1800a2f6b  setnz   dil
0x1800a2f6f  test    eax, eax
0x1800a2f71  jns     short loc_1800A2F94
0x1800a2f73  mov     r9d, 5FCh
0x1800a2f79  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a2f80  lea     rdx, aStatus; "Status"
0x1800a2f87  mov     ecx, eax
0x1800a2f89  call    DebugTraceError
0x1800a2f8e  nop
0x1800a2f8f  jmp     loc_18003A7B3
0x1800a2f94  mov     ecx, 40h ; '@'
0x1800a2f99  call    BCryptAlloc
0x1800a2f9e  mov     rbx, rax
0x1800a2fa1  test    rax, rax
0x1800a2fa4  jnz     short loc_1800A2FCA
0x1800a2fa6  mov     r9d, 603h
0x1800a2fac  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a2fb3  lea     rdx, aStatusNoMemory; "STATUS_NO_MEMORY"
0x1800a2fba  mov     ecx, 0C0000017h
0x1800a2fbf  call    DebugTraceError
0x1800a2fc4  nop
0x1800a2fc5  jmp     loc_18003A7B3
0x1800a2fca  lea     rcx, [rax+14h]; pszDest
0x1800a2fce  mov     r8, rbp; pszSrc
0x1800a2fd1  mov     edx, 14h; cchDest
0x1800a2fd6  call    StringCchCopyW
0x1800a2fdb  test    eax, eax
0x1800a2fdd  jz      short loc_1800A300B
0x1800a2fdf  mov     r9d, 60Ah
0x1800a2fe5  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a2fec  lea     rdx, aStatusBufferTo; "STATUS_BUFFER_TOO_SMALL"
0x1800a2ff3  mov     ecx, 0C0000023h
0x1800a2ff8  call    DebugTraceError
0x1800a2ffd  mov     rcx, rbx; P
0x1800a3000  call    BCryptFree
0x1800a3005  nop
0x1800a3006  jmp     loc_18003A7B3
0x1800a300b  mov     eax, [r15]
0x1800a300e  mov     [rbx+10h], eax
0x1800a3011  mov     rax, [r14]
0x1800a3014  mov     [rbx+8], rax
0x1800a3018  mov     rax, cs:g_pResolveProviderCache
0x1800a301f  mov     [rbx], rax
0x1800a3022  mov     rcx, rax
0x1800a3025  lock cmpxchg cs:g_pResolveProviderCache, rbx
0x1800a302e  cmp     rcx, rax
0x1800a3031  jnz     short loc_1800A301F
0x1800a3033  xor     dil, dil
0x1800a3036  jmp     loc_18003A7B3
```
