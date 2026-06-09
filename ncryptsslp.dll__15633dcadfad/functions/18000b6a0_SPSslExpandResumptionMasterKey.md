# SPSslExpandResumptionMasterKey

- ea: `0x18000b6a0`
- end: `0x18000bb7c`
- name: `SPSslExpandResumptionMasterKey`
- size: `1244`
- prototype: `__int64 __fastcall(_DWORD *, __int64, BCRYPT_HASH_HANDLE *, __int64, int, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800037a0`
- `0x18000b594`
- `0x18000b654`
- `0x18000b6a0`
- `0x1800183d0`

## import_xrefs

- `bcrypt!BCryptDuplicateHash` at `0x18000b8eb`
- `bcrypt!BCryptDuplicateHash` at `0x18000b8eb`
- `bcrypt!BCryptFinishHash` at `0x18000b930`
- `bcrypt!BCryptFinishHash` at `0x18000b930`
- `bcrypt!BCryptDestroyHash` at `0x18000b771`
- `bcrypt!BCryptDestroyHash` at `0x18000b771`
- `ntdll!RtlFreeHeap` at `0x18000b7af`
- `ntdll!RtlFreeHeap` at `0x18000b7e2`
- `ntdll!RtlFreeHeap` at `0x18000b7af`
- `ntdll!RtlFreeHeap` at `0x18000b7e2`
- `ntdll!RtlAllocateHeap` at `0x18000b8bf`
- `ntdll!RtlAllocateHeap` at `0x18000b90d`
- `ntdll!RtlAllocateHeap` at `0x18000b8bf`
- `ntdll!RtlAllocateHeap` at `0x18000b90d`

## string_xrefs

- `0x18000b747`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000b973`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000b9ca`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000ba00`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000ba4e`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000bab2`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000bb03`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000bb32`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000bb5a`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslExpandResumptionMasterKey(
        _DWORD *a1,
        __int64 a2,
        BCRYPT_HASH_HANDLE *a3,
        __int64 a4,
        int a5,
        int a6)
{
  BCRYPT_HASH_HANDLE *v7; // rsi
  __int64 v8; // rdi
  __int64 v9; // rbx
  UCHAR *v10; // rbp
  UCHAR *v11; // r13
  ULONG v12; // r15d
  __int64 v13; // rax
  NTSTATUS v14; // esi
  __int64 v15; // rcx
  UCHAR *v16; // rax
  __int64 v17; // rcx
  UCHAR *v18; // rax
  const wchar_t *v20; // rbp
  __int64 *v21; // rax
  __int64 *v22; // r14
  UCHAR *Heap; // rax
  int v24; // edx
  UCHAR *v25; // rax
  int v26; // edx
  int v27; // eax
  BCRYPT_HASH_HANDLE hHash; // [rsp+90h] [rbp+18h] BYREF

  v7 = a3;
  v8 = a2;
  if ( !a1 || *a1 < 0x310u || a1[1] != 1936944177 )
    a1 = 0;
  if ( !a2 || *(_DWORD *)a2 < 0x70u || *(_DWORD *)(a2 + 4) != 1936944179 )
    v8 = 0;
  if ( !a3 || *(_DWORD *)a3 < 0x30u || *((_DWORD *)a3 + 1) != 1936944178 )
    v7 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  hHash = 0;
  v12 = 0;
  if ( !a1 || !v8 || (v13 = *(_QWORD *)(v8 + 16)) == 0 || !v7 )
  {
    v14 = -2146893786;
    DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", 6544);
LABEL_18:
    if ( hHash )
      BCryptDestroyHash(hHash);
    if ( v11 )
    {
      v15 = v12;
      v16 = v11;
      if ( v12 )
      {
        do
        {
          *v16++ = 0;
          --v15;
        }
        while ( v15 );
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
    }
    if ( v10 )
    {
      v17 = (unsigned int)v9;
      v18 = v10;
      if ( (_DWORD)v9 )
      {
        do
        {
          *v18++ = 0;
          --v17;
        }
        while ( v17 );
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
    }
    return (unsigned int)v14;
  }
  v20 = *(const wchar_t **)(v13 + 136);
  if ( !v20 || !*v20 )
    v20 = L"SHA256";
  while ( 1 )
  {
    if ( (unsigned int)v9 >= g_dwHashInfoTotalCount )
      goto LABEL_37;
    v21 = (__int64 *)g_pHashInfo[v9];
    v22 = &g_pHashInfo[v9];
    if ( v21 )
    {
      a2 = *v21;
      if ( *v21 )
      {
        if ( !wcsnicmp(v20, (const wchar_t *)a2, 0x40u) )
          break;
      }
    }
    v9 = (unsigned int)(v9 + 1);
  }
  _mm_lfence();
  if ( *v22 )
  {
    LODWORD(v9) = *(_DWORD *)(*v22 + 8);
    if ( (unsigned int)v9 > 0xFF )
      goto LABEL_50;
  }
  else
  {
LABEL_37:
    LODWORD(v9) = 0;
  }
  if ( (_DWORD)v9 != *((_DWORD *)v7 + 7) || !a4 )
  {
LABEL_50:
    v14 = -2146893785;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        (unsigned int)"Status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        157);
    goto LABEL_65;
  }
  if ( *(_DWORD *)(v8 + 8) != 772 || *(_DWORD *)(v8 + 108) != 3 )
  {
    v14 = -2146893783;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        (unsigned int)"Status",
        41,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        164);
LABEL_65:
    v10 = 0;
    goto LABEL_18;
  }
  if ( !a6 )
  {
    v12 = *((_DWORD *)v7 + 6);
    Heap = (UCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
    v11 = Heap;
    if ( Heap )
    {
      v14 = BCryptDuplicateHash(v7[2], &hHash, Heap, v12, 0);
      if ( v14 >= 0 )
      {
        v25 = (UCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)v9);
        v10 = v25;
        if ( v25 )
        {
          v14 = BCryptFinishHash(hHash, v25, v9, 0);
          if ( v14 < 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v26,
                (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
                (unsigned int)"Status",
                v14,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
                211);
          }
          else
          {
            v27 = TlsDeriveSecret(v8, "res master", v10, (unsigned __int8)v9, 7, a4);
            v14 = v27;
            if ( v27 < 0 )
              DebugTraceError(
                (unsigned int)v27,
                "Status",
                "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
                6628);
          }
        }
        else
        {
          v14 = -1073741801;
          DebugTraceError(
            3221225495LL,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
            6601);
        }
        goto LABEL_18;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v24,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
          (unsigned int)"Status",
          v14,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
          194);
    }
    else
    {
      v14 = -1073741801;
      DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", 6583);
    }
    v10 = 0;
    goto LABEL_18;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
      (unsigned int)"NTE_BAD_FLAGS",
      9,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
      170);
  return 2148073481LL;
}

```

## disassembly

```asm
0x18000b6a0  push    rbx
0x18000b6a2  push    rbp
0x18000b6a3  push    rsi
0x18000b6a4  push    rdi
0x18000b6a5  push    r12
0x18000b6a7  push    r13
0x18000b6a9  push    r15
0x18000b6ab  sub     rsp, 40h
0x18000b6af  mov     r12, r9
0x18000b6b2  mov     rsi, r8
0x18000b6b5  mov     rdi, rdx
0x18000b6b8  test    rcx, rcx
0x18000b6bb  jz      short loc_18000B6CE
0x18000b6bd  cmp     dword ptr [rcx], 310h
0x18000b6c3  jb      short loc_18000B6CE
0x18000b6c5  cmp     dword ptr [rcx+4], 73736C31h
0x18000b6cc  jz      short loc_18000B6D0
0x18000b6ce  xor     ecx, ecx
0x18000b6d0  test    rdx, rdx
0x18000b6d3  jz      short loc_18000B6E3
0x18000b6d5  cmp     dword ptr [rdx], 70h ; 'p'
0x18000b6d8  jb      short loc_18000B6E3
0x18000b6da  cmp     dword ptr [rdx+4], 73736C33h
0x18000b6e1  jz      short loc_18000B6E5
0x18000b6e3  xor     edi, edi
0x18000b6e5  test    r8, r8
0x18000b6e8  jz      short loc_18000B6FA
0x18000b6ea  cmp     dword ptr [r8], 30h ; '0'
0x18000b6ee  jb      short loc_18000B6FA
0x18000b6f0  cmp     dword ptr [r8+4], 73736C32h
0x18000b6f8  jz      short loc_18000B6FC
0x18000b6fa  xor     esi, esi
0x18000b6fc  xor     ebx, ebx
0x18000b6fe  mov     [rsp+78h+arg_18], r14
0x18000b706  xor     ebp, ebp
0x18000b708  mov     dword ptr [rsp+78h+Size], ebx
0x18000b70f  xor     r13d, r13d
0x18000b712  mov     [rsp+78h+hHash], rbx
0x18000b71a  xor     r15d, r15d
0x18000b71d  mov     [rsp+78h+arg_8], rbp
0x18000b725  test    rcx, rcx
0x18000b728  jz      short loc_18000B741
0x18000b72a  test    rdi, rdi
0x18000b72d  jz      short loc_18000B741
0x18000b72f  mov     rax, [rdi+10h]
0x18000b733  test    rax, rax
0x18000b736  jz      short loc_18000B741
0x18000b738  test    rsi, rsi
0x18000b73b  jnz     loc_18000B801
0x18000b741  mov     r9d, 1990h
0x18000b747  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b74e  lea     rdx, aStatus; "Status"
0x18000b755  mov     ecx, 80090026h
0x18000b75a  mov     esi, 80090026h
0x18000b75f  call    DebugTraceError
0x18000b764  mov     rcx, [rsp+78h+hHash]; hHash
0x18000b76c  test    rcx, rcx
0x18000b76f  jz      short loc_18000B777
0x18000b771  call    cs:__imp_BCryptDestroyHash
0x18000b777  test    r13, r13
0x18000b77a  jz      short loc_18000B7B5
0x18000b77c  mov     ecx, r15d
0x18000b77f  mov     rax, r13
0x18000b782  test    r15d, r15d
0x18000b785  jz      short loc_18000B79D
0x18000b787  nop     word ptr [rax+rax+00000000h]
0x18000b790  mov     byte ptr [rax], 0
0x18000b793  lea     rax, [rax+1]
0x18000b797  sub     rcx, 1
0x18000b79b  jnz     short loc_18000B790
0x18000b79d  mov     rcx, gs:60h
0x18000b7a6  mov     r8, r13; P
0x18000b7a9  xor     edx, edx; Flags
0x18000b7ab  mov     rcx, [rcx+30h]; HeapHandle
0x18000b7af  call    cs:__imp_RtlFreeHeap
0x18000b7b5  test    rbp, rbp
0x18000b7b8  jz      short loc_18000B7E8
0x18000b7ba  mov     ecx, ebx
0x18000b7bc  mov     rax, rbp
0x18000b7bf  test    ebx, ebx
0x18000b7c1  jz      short loc_18000B7D0
0x18000b7c3  mov     byte ptr [rax], 0
0x18000b7c6  lea     rax, [rax+1]
0x18000b7ca  sub     rcx, 1
0x18000b7ce  jnz     short loc_18000B7C3
0x18000b7d0  mov     rcx, gs:60h
0x18000b7d9  mov     r8, rbp; P
0x18000b7dc  xor     edx, edx; Flags
0x18000b7de  mov     rcx, [rcx+30h]; HeapHandle
0x18000b7e2  call    cs:__imp_RtlFreeHeap
0x18000b7e8  mov     eax, esi
0x18000b7ea  mov     r14, [rsp+78h+arg_18]
0x18000b7f2  add     rsp, 40h
0x18000b7f6  pop     r15
0x18000b7f8  pop     r13
0x18000b7fa  pop     r12
0x18000b7fc  pop     rdi
0x18000b7fd  pop     rsi
0x18000b7fe  pop     rbp
0x18000b7ff  pop     rbx
0x18000b800  retn
0x18000b801  mov     rbp, [rax+88h]
0x18000b808  test    rbp, rbp
0x18000b80b  jz      loc_18000BA80
0x18000b811  cmp     [rbp+0], bx
0x18000b815  jz      loc_18000BA80
0x18000b81b  lea     rcx, g_pHashInfo
0x18000b822  cmp     ebx, cs:g_dwHashInfoTotalCount
0x18000b828  jnb     short loc_18000B86B
0x18000b82a  mov     rax, [rcx+rbx*8]
0x18000b82e  lea     r14, [rcx+rbx*8]
0x18000b832  test    rax, rax
0x18000b835  jz      short loc_18000B858
0x18000b837  mov     rdx, [rax]; String2
0x18000b83a  test    rdx, rdx
0x18000b83d  jz      short loc_18000B858
0x18000b83f  mov     r8d, 40h ; '@'; MaxCount
0x18000b845  mov     rcx, rbp; String1
0x18000b848  call    _wcsnicmp
0x18000b84d  test    eax, eax
0x18000b84f  jz      short loc_18000B85C
0x18000b851  lea     rcx, g_pHashInfo
0x18000b858  inc     ebx
0x18000b85a  jmp     short loc_18000B822
0x18000b85c  lfence
0x18000b85f  mov     rax, [r14]
0x18000b862  test    rax, rax
0x18000b865  jnz     loc_18000B98D
0x18000b86b  mov     ebx, dword ptr [rsp+78h+Size]
0x18000b872  cmp     ebx, [rsi+1Ch]
0x18000b875  jnz     loc_18000B99C
0x18000b87b  test    r12, r12
0x18000b87e  jz      loc_18000B99C
0x18000b884  cmp     dword ptr [rdi+8], 304h
0x18000b88b  jnz     loc_18000BA8C
0x18000b891  cmp     dword ptr [rdi+6Ch], 3
0x18000b895  jnz     loc_18000BA8C
0x18000b89b  cmp     [rsp+78h+arg_28], r13d
0x18000b8a3  jnz     loc_18000BA31
0x18000b8a9  mov     rcx, gs:60h
0x18000b8b2  xor     edx, edx; Flags
0x18000b8b4  mov     r15d, [rsi+18h]
0x18000b8b8  mov     r8d, r15d; Size
0x18000b8bb  mov     rcx, [rcx+30h]; HeapHandle
0x18000b8bf  call    cs:__imp_RtlAllocateHeap
0x18000b8c5  mov     r13, rax
0x18000b8c8  test    rax, rax
0x18000b8cb  jz      loc_18000BB2C
0x18000b8d1  mov     rcx, [rsi+10h]; hHash
0x18000b8d5  lea     rdx, [rsp+78h+hHash]; phNewHash
0x18000b8dd  mov     r9d, r15d; cbHashObject
0x18000b8e0  mov     [rsp+78h+dwFlags], 0; dwFlags
0x18000b8e8  mov     r8, rax; pbHashObject
0x18000b8eb  call    cs:__imp_BCryptDuplicateHash
0x18000b8f1  mov     esi, eax
0x18000b8f3  test    eax, eax
0x18000b8f5  js      loc_18000B9E3
0x18000b8fb  mov     rcx, gs:60h
0x18000b904  xor     edx, edx; Flags
0x18000b906  mov     r8d, ebx; Size
0x18000b909  mov     rcx, [rcx+30h]; HeapHandle
0x18000b90d  call    cs:__imp_RtlAllocateHeap
0x18000b913  mov     rbp, rax
0x18000b916  test    rax, rax
0x18000b919  jz      loc_18000BB54
0x18000b91f  mov     rcx, [rsp+78h+hHash]; hHash
0x18000b927  xor     r9d, r9d; dwFlags
0x18000b92a  mov     r8d, ebx; cbOutput
0x18000b92d  mov     rdx, rax; pbOutput
0x18000b930  call    cs:__imp_BCryptFinishHash
0x18000b936  mov     esi, eax
0x18000b938  test    eax, eax
0x18000b93a  js      loc_18000BADE
0x18000b940  movzx   r9d, bl
0x18000b944  mov     [rsp+78h+var_50], r12
0x18000b949  mov     r8, rbp
0x18000b94c  mov     [rsp+78h+dwFlags], 7
0x18000b954  lea     rdx, aResMaster; "res master"
0x18000b95b  mov     rcx, rdi
0x18000b95e  call    TlsDeriveSecret
0x18000b963  mov     esi, eax
0x18000b965  test    eax, eax
0x18000b967  jns     loc_18000B764
0x18000b96d  mov     r9d, 19E4h
0x18000b973  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b97a  lea     rdx, aStatus; "Status"
0x18000b981  mov     ecx, eax
0x18000b983  call    DebugTraceError
0x18000b988  jmp     loc_18000B764
0x18000b98d  mov     ebx, [rax+8]
0x18000b990  cmp     ebx, 0FFh
0x18000b996  jbe     loc_18000B872
0x18000b99c  mov     esi, 80090027h
0x18000b9a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b9a8  lea     rax, WPP_GLOBAL_Control
0x18000b9af  cmp     rcx, rax
0x18000b9b2  jz      loc_18000BAD6
0x18000b9b8  test    byte ptr [rcx+1Ch], 1
0x18000b9bc  jz      loc_18000BAD6
0x18000b9c2  mov     [rsp+78h+var_48], 199Dh
0x18000b9ca  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b9d1  mov     [rsp+78h+var_50], r8
0x18000b9d6  mov     [rsp+78h+dwFlags], 80090027h
0x18000b9de  jmp     loc_18000BAC6
0x18000b9e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b9ea  lea     rax, WPP_GLOBAL_Control
0x18000b9f1  cmp     rcx, rax
0x18000b9f4  jz      short loc_18000BA24
0x18000b9f6  test    byte ptr [rcx+1Ch], 1
0x18000b9fa  jz      short loc_18000BA24
0x18000b9fc  mov     rcx, [rcx+10h]
0x18000ba00  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ba07  mov     [rsp+78h+var_48], 19C2h
0x18000ba0f  lea     r9, aStatus; "Status"
0x18000ba16  mov     [rsp+78h+var_50], r8
0x18000ba1b  mov     [rsp+78h+dwFlags], esi
0x18000ba1f  call    WPP_SF_sDsd
0x18000ba24  mov     rbp, [rsp+78h+arg_8]
0x18000ba2c  jmp     loc_18000B764
0x18000ba31  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ba38  lea     rax, WPP_GLOBAL_Control
0x18000ba3f  cmp     rcx, rax
0x18000ba42  jz      short loc_18000BA76
0x18000ba44  test    byte ptr [rcx+1Ch], 1
0x18000ba48  jz      short loc_18000BA76
0x18000ba4a  mov     rcx, [rcx+10h]
0x18000ba4e  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ba55  mov     [rsp+78h+var_48], 19AAh
0x18000ba5d  lea     r9, aNteBadFlags; "NTE_BAD_FLAGS"
0x18000ba64  mov     [rsp+78h+var_50], r8
0x18000ba69  mov     [rsp+78h+dwFlags], 80090009h
0x18000ba71  call    WPP_SF_sDsd
0x18000ba76  mov     eax, 80090009h
0x18000ba7b  jmp     loc_18000B7EA
0x18000ba80  lea     rbp, aSha256; "SHA256"
0x18000ba87  jmp     loc_18000B81B
0x18000ba8c  mov     esi, 80090029h
0x18000ba91  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ba98  lea     rax, WPP_GLOBAL_Control
0x18000ba9f  cmp     rcx, rax
0x18000baa2  jz      short loc_18000BAD6
0x18000baa4  test    byte ptr [rcx+1Ch], 1
0x18000baa8  jz      short loc_18000BAD6
0x18000baaa  mov     [rsp+78h+var_48], 19A4h
0x18000bab2  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000bab9  mov     [rsp+78h+var_50], r8
0x18000babe  mov     [rsp+78h+dwFlags], 80090029h
0x18000bac6  mov     rcx, [rcx+10h]
0x18000baca  lea     r9, aStatus; "Status"
0x18000bad1  call    WPP_SF_sDsd
0x18000bad6  mov     rbp, r13
0x18000bad9  jmp     loc_18000B764
0x18000bade  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bae5  lea     rax, WPP_GLOBAL_Control
0x18000baec  cmp     rcx, rax
0x18000baef  jz      loc_18000B764
0x18000baf5  test    byte ptr [rcx+1Ch], 1
0x18000baf9  jz      loc_18000B764
0x18000baff  mov     rcx, [rcx+10h]
0x18000bb03  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000bb0a  mov     [rsp+78h+var_48], 19D3h
0x18000bb12  lea     r9, aStatus; "Status"
0x18000bb19  mov     [rsp+78h+var_50], r8
0x18000bb1e  mov     [rsp+78h+dwFlags], esi
0x18000bb22  call    WPP_SF_sDsd
0x18000bb27  jmp     loc_18000B764
0x18000bb2c  mov     r9d, 19B7h
0x18000bb32  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000bb39  lea     rdx, aStatus; "Status"
0x18000bb40  mov     ecx, 0C0000017h
0x18000bb45  mov     esi, 0C0000017h
0x18000bb4a  call    DebugTraceError
0x18000bb4f  jmp     loc_18000BA24
0x18000bb54  mov     r9d, 19C9h
0x18000bb5a  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000bb61  lea     rdx, aStatus; "Status"
0x18000bb68  mov     ecx, 0C0000017h
0x18000bb6d  mov     esi, 0C0000017h
0x18000bb72  call    DebugTraceError
0x18000bb77  jmp     loc_18000B764
```
