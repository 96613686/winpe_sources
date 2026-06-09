# BCryptResolveProvidersForBcoapCached

- ea: `0x180039c40`
- end: `0x180039d24`
- name: `BCryptResolveProvidersForBcoapCached`
- size: `228`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, LPCWSTR pszProvider, ULONG dwFlags, ULONG *pcbBuffer, PCRYPT_PROVIDER_REFS *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800449b0`

## callees

- `0x18000743c`
- `0x18001bd90`
- `0x18001be80`
- `0x180028b40`
- `0x180036270`
- `0x180039c40`

## string_xrefs

- `0x1800a1149`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800a117c`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800a11b5`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

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
0x180039c40  push    rbx
0x180039c42  push    rbp
0x180039c43  push    rsi
0x180039c44  push    rdi
0x180039c45  push    r14
0x180039c47  push    r15
0x180039c49  sub     rsp, 48h
0x180039c4d  mov     r15, r9
0x180039c50  mov     rbp, rcx
0x180039c53  test    rdx, rdx
0x180039c56  jnz     short loc_180039CCE
0x180039c58  cmp     r8d, 2
0x180039c5c  jnz     short loc_180039CCE
0x180039c5e  mov     r10, cs:g_pResolveProviderCache
0x180039c65  test    r10, r10
0x180039c68  jz      loc_1800A1104
0x180039c6e  lea     r8, [r10+14h]
0x180039c72  mov     rax, rbp
0x180039c75  sub     r8, rbp
0x180039c78  nop     dword ptr [rax+rax+00000000h]
0x180039c80  movzx   edx, word ptr [rax]
0x180039c83  movzx   ecx, word ptr [rax+r8]
0x180039c88  sub     edx, ecx
0x180039c8a  jnz     short loc_180039C94
0x180039c8c  add     rax, 2
0x180039c90  test    ecx, ecx
0x180039c92  jnz     short loc_180039C80
0x180039c94  test    edx, edx
0x180039c96  jnz     short loc_180039D13
0x180039c98  mov     eax, [r10+10h]
0x180039c9c  xor     esi, esi
0x180039c9e  mov     [r9], eax
0x180039ca1  xor     dil, dil
0x180039ca4  mov     rax, [rsp+78h+arg_20]
0x180039cac  mov     rcx, [r10+8]
0x180039cb0  mov     [rax], rcx
0x180039cb3  mov     rax, [rsp+78h+arg_28]
0x180039cbb  mov     [rax], dil
0x180039cbe  mov     eax, esi
0x180039cc0  add     rsp, 48h
0x180039cc4  pop     r15
0x180039cc6  pop     r14
0x180039cc8  pop     rdi
0x180039cc9  pop     rsi
0x180039cca  pop     rbp
0x180039ccb  pop     rbx
0x180039ccc  retn
0x180039cce  mov     rbx, [rsp+78h+arg_20]
0x180039cd6  mov     r9, rdx; pszProvider
0x180039cd9  mov     [rsp+78h+ppBuffer], rbx; ppBuffer
0x180039cde  xor     edx, edx; dwInterface
0x180039ce0  mov     [rsp+78h+pcbBuffer], r15; pcbBuffer
0x180039ce5  xor     ecx, ecx; pszContext
0x180039ce7  mov     [rsp+78h+dwFlags], r8d; dwFlags
0x180039cec  xor     dil, dil
0x180039cef  mov     r8, rbp; pszFunction
0x180039cf2  mov     [rsp+78h+dwMode], 2; dwMode
0x180039cfa  call    BCryptResolveProviders
0x180039cff  cmp     qword ptr [rbx], 0
0x180039d03  mov     esi, eax
0x180039d05  mov     eax, 1
0x180039d0a  movzx   edi, dil
0x180039d0e  cmovnz  edi, eax
0x180039d11  jmp     short loc_180039CB3
0x180039d13  mov     r10, [r10]
0x180039d16  test    r10, r10
0x180039d19  jnz     loc_180039C6E
0x180039d1f  jmp     loc_1800A1104
0x1800a1104  mov     r14, [rsp+78h+arg_20]
0x1800a110c  xor     r9d, r9d; pszProvider
0x1800a110f  mov     [rsp+78h+ppBuffer], r14; ppBuffer
0x1800a1114  mov     r8, rbp; pszFunction
0x1800a1117  mov     [rsp+78h+pcbBuffer], r15; pcbBuffer
0x1800a111c  xor     edx, edx; dwInterface
0x1800a111e  mov     [rsp+78h+dwFlags], 2; dwFlags
0x1800a1126  xor     ecx, ecx; pszContext
0x1800a1128  mov     [rsp+78h+dwMode], 2; dwMode
0x1800a1130  call    BCryptResolveProviders
0x1800a1135  cmp     qword ptr [r14], 0
0x1800a1139  mov     esi, eax
0x1800a113b  setnz   dil
0x1800a113f  test    eax, eax
0x1800a1141  jns     short loc_1800A1164
0x1800a1143  mov     r9d, 5FCh
0x1800a1149  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a1150  lea     rdx, aStatus; "Status"
0x1800a1157  mov     ecx, eax
0x1800a1159  call    DebugTraceError
0x1800a115e  nop
0x1800a115f  jmp     loc_180039CB3
0x1800a1164  mov     ecx, 40h ; '@'
0x1800a1169  call    BCryptAlloc
0x1800a116e  mov     rbx, rax
0x1800a1171  test    rax, rax
0x1800a1174  jnz     short loc_1800A119A
0x1800a1176  mov     r9d, 603h
0x1800a117c  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a1183  lea     rdx, aStatusNoMemory; "STATUS_NO_MEMORY"
0x1800a118a  mov     ecx, 0C0000017h
0x1800a118f  call    DebugTraceError
0x1800a1194  nop
0x1800a1195  jmp     loc_180039CB3
0x1800a119a  lea     rcx, [rax+14h]; pszDest
0x1800a119e  mov     r8, rbp; pszSrc
0x1800a11a1  mov     edx, 14h; cchDest
0x1800a11a6  call    StringCchCopyW
0x1800a11ab  test    eax, eax
0x1800a11ad  jz      short loc_1800A11DB
0x1800a11af  mov     r9d, 60Ah
0x1800a11b5  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a11bc  lea     rdx, aStatusBufferTo; "STATUS_BUFFER_TOO_SMALL"
0x1800a11c3  mov     ecx, 0C0000023h
0x1800a11c8  call    DebugTraceError
0x1800a11cd  mov     rcx, rbx; P
0x1800a11d0  call    BCryptFree
0x1800a11d5  nop
0x1800a11d6  jmp     loc_180039CB3
0x1800a11db  mov     eax, [r15]
0x1800a11de  mov     [rbx+10h], eax
0x1800a11e1  mov     rax, [r14]
0x1800a11e4  mov     [rbx+8], rax
0x1800a11e8  mov     rax, cs:g_pResolveProviderCache
0x1800a11ef  mov     [rbx], rax
0x1800a11f2  mov     rcx, rax
0x1800a11f5  lock cmpxchg cs:g_pResolveProviderCache, rbx
0x1800a11fe  cmp     rcx, rax
0x1800a1201  jnz     short loc_1800A11EF
0x1800a1203  xor     dil, dil
0x1800a1206  jmp     loc_180039CB3
```
