# BCryptResolveProvidersForBcoapCached

- ea: `0x180043cd0`
- end: `0x180043db4`
- name: `BCryptResolveProvidersForBcoapCached`
- size: `228`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, LPCWSTR pszProvider, ULONG dwFlags, ULONG *pcbBuffer, PCRYPT_PROVIDER_REFS *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18004eaa0`

## callees

- `0x18001155c`
- `0x180025ec0`
- `0x180025fb0`
- `0x180032c70`
- `0x1800402e0`
- `0x180043cd0`

## string_xrefs

- `0x1800a7ee7`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800a7f1a`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800a7f53`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

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
0x180043cd0  push    rbx
0x180043cd2  push    rbp
0x180043cd3  push    rsi
0x180043cd4  push    rdi
0x180043cd5  push    r14
0x180043cd7  push    r15
0x180043cd9  sub     rsp, 48h
0x180043cdd  mov     r15, r9
0x180043ce0  mov     rbp, rcx
0x180043ce3  test    rdx, rdx
0x180043ce6  jnz     short loc_180043D5E
0x180043ce8  cmp     r8d, 2
0x180043cec  jnz     short loc_180043D5E
0x180043cee  mov     r10, cs:g_pResolveProviderCache
0x180043cf5  test    r10, r10
0x180043cf8  jz      loc_1800A7EA2
0x180043cfe  lea     r8, [r10+14h]
0x180043d02  mov     rax, rbp
0x180043d05  sub     r8, rbp
0x180043d08  nop     dword ptr [rax+rax+00000000h]
0x180043d10  movzx   edx, word ptr [rax]
0x180043d13  movzx   ecx, word ptr [rax+r8]
0x180043d18  sub     edx, ecx
0x180043d1a  jnz     short loc_180043D24
0x180043d1c  add     rax, 2
0x180043d20  test    ecx, ecx
0x180043d22  jnz     short loc_180043D10
0x180043d24  test    edx, edx
0x180043d26  jnz     short loc_180043DA3
0x180043d28  mov     eax, [r10+10h]
0x180043d2c  xor     esi, esi
0x180043d2e  mov     [r9], eax
0x180043d31  xor     dil, dil
0x180043d34  mov     rax, [rsp+78h+arg_20]
0x180043d3c  mov     rcx, [r10+8]
0x180043d40  mov     [rax], rcx
0x180043d43  mov     rax, [rsp+78h+arg_28]
0x180043d4b  mov     [rax], dil
0x180043d4e  mov     eax, esi
0x180043d50  add     rsp, 48h
0x180043d54  pop     r15
0x180043d56  pop     r14
0x180043d58  pop     rdi
0x180043d59  pop     rsi
0x180043d5a  pop     rbp
0x180043d5b  pop     rbx
0x180043d5c  retn
0x180043d5e  mov     rbx, [rsp+78h+arg_20]
0x180043d66  mov     r9, rdx; pszProvider
0x180043d69  mov     [rsp+78h+ppBuffer], rbx; ppBuffer
0x180043d6e  xor     edx, edx; dwInterface
0x180043d70  mov     [rsp+78h+pcbBuffer], r15; pcbBuffer
0x180043d75  xor     ecx, ecx; pszContext
0x180043d77  mov     [rsp+78h+dwFlags], r8d; dwFlags
0x180043d7c  xor     dil, dil
0x180043d7f  mov     r8, rbp; pszFunction
0x180043d82  mov     [rsp+78h+dwMode], 2; dwMode
0x180043d8a  call    BCryptResolveProviders
0x180043d8f  cmp     qword ptr [rbx], 0
0x180043d93  mov     esi, eax
0x180043d95  mov     eax, 1
0x180043d9a  movzx   edi, dil
0x180043d9e  cmovnz  edi, eax
0x180043da1  jmp     short loc_180043D43
0x180043da3  mov     r10, [r10]
0x180043da6  test    r10, r10
0x180043da9  jnz     loc_180043CFE
0x180043daf  jmp     loc_1800A7EA2
0x1800a7ea2  mov     r14, [rsp+78h+arg_20]
0x1800a7eaa  xor     r9d, r9d; pszProvider
0x1800a7ead  mov     [rsp+78h+ppBuffer], r14; ppBuffer
0x1800a7eb2  mov     r8, rbp; pszFunction
0x1800a7eb5  mov     [rsp+78h+pcbBuffer], r15; pcbBuffer
0x1800a7eba  xor     edx, edx; dwInterface
0x1800a7ebc  mov     [rsp+78h+dwFlags], 2; dwFlags
0x1800a7ec4  xor     ecx, ecx; pszContext
0x1800a7ec6  mov     [rsp+78h+dwMode], 2; dwMode
0x1800a7ece  call    BCryptResolveProviders
0x1800a7ed3  cmp     qword ptr [r14], 0
0x1800a7ed7  mov     esi, eax
0x1800a7ed9  setnz   dil
0x1800a7edd  test    eax, eax
0x1800a7edf  jns     short loc_1800A7F02
0x1800a7ee1  mov     r9d, 5FCh
0x1800a7ee7  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a7eee  lea     rdx, aStatus; "Status"
0x1800a7ef5  mov     ecx, eax
0x1800a7ef7  call    DebugTraceError
0x1800a7efc  nop
0x1800a7efd  jmp     loc_180043D43
0x1800a7f02  mov     ecx, 40h ; '@'
0x1800a7f07  call    BCryptAlloc
0x1800a7f0c  mov     rbx, rax
0x1800a7f0f  test    rax, rax
0x1800a7f12  jnz     short loc_1800A7F38
0x1800a7f14  mov     r9d, 603h
0x1800a7f1a  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a7f21  lea     rdx, aStatusNoMemory; "STATUS_NO_MEMORY"
0x1800a7f28  mov     ecx, 0C0000017h
0x1800a7f2d  call    DebugTraceError
0x1800a7f32  nop
0x1800a7f33  jmp     loc_180043D43
0x1800a7f38  lea     rcx, [rax+14h]; pszDest
0x1800a7f3c  mov     r8, rbp; pszSrc
0x1800a7f3f  mov     edx, 14h; cchDest
0x1800a7f44  call    StringCchCopyW
0x1800a7f49  test    eax, eax
0x1800a7f4b  jz      short loc_1800A7F79
0x1800a7f4d  mov     r9d, 60Ah
0x1800a7f53  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a7f5a  lea     rdx, aStatusBufferTo; "STATUS_BUFFER_TOO_SMALL"
0x1800a7f61  mov     ecx, 0C0000023h
0x1800a7f66  call    DebugTraceError
0x1800a7f6b  mov     rcx, rbx; P
0x1800a7f6e  call    BCryptFree
0x1800a7f73  nop
0x1800a7f74  jmp     loc_180043D43
0x1800a7f79  mov     eax, [r15]
0x1800a7f7c  mov     [rbx+10h], eax
0x1800a7f7f  mov     rax, [r14]
0x1800a7f82  mov     [rbx+8], rax
0x1800a7f86  mov     rax, cs:g_pResolveProviderCache
0x1800a7f8d  mov     [rbx], rax
0x1800a7f90  mov     rcx, rax
0x1800a7f93  lock cmpxchg cs:g_pResolveProviderCache, rbx
0x1800a7f9c  cmp     rcx, rax
0x1800a7f9f  jnz     short loc_1800A7F8D
0x1800a7fa1  xor     dil, dil
0x1800a7fa4  jmp     loc_180043D43
```
