# CNG_DescriptorInfoToString

- ea: `0x18001d538`
- end: `0x18001d7af`
- name: `CNG_DescriptorInfoToString`
- size: `631`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001d040`

## callees

- `0x18000e120`
- `0x180015a40`
- `0x18001d538`
- `0x18001f175`
- `0x180020010`

## string_xrefs

- `0x18001d60c`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\descriptor.c`
- `0x18001d770`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\descriptor.c`

## pseudocode

```c
__int64 __fastcall CNG_DescriptorInfoToString(__int64 a1, __int64 a2, wchar_t **a3)
{
  unsigned int v3; // r15d
  size_t v4; // rbx
  wchar_t **v5; // r13
  __int64 v6; // rsi
  __int64 v8; // r9
  __int64 v9; // r10
  __int64 v10; // rax
  __int64 v11; // rdi
  unsigned int v12; // ecx
  __int64 v13; // rax
  __int64 v14; // r11
  __int64 v15; // rax
  wchar_t *v16; // rax
  wchar_t *v17; // rsi
  HRESULT v18; // ebx
  wchar_t *v19; // rcx
  unsigned int v20; // edi
  __int64 v21; // r12
  __int64 v22; // r8
  __int64 v23; // r9
  size_t pcchRemaining; // [rsp+80h] [rbp+40h] BYREF
  __int64 v26; // [rsp+88h] [rbp+48h]
  STRSAFE_LPWSTR ppszDestEnd; // [rsp+90h] [rbp+50h] BYREF

  v26 = a2;
  v3 = 0;
  v4 = 1;
  *a3 = 0;
  v5 = a3;
  v6 = a2;
  v8 = 0;
  pcchRemaining = 1;
  if ( *(_DWORD *)a1 )
  {
    v9 = *(_QWORD *)(a1 + 8);
    do
    {
      if ( (_DWORD)v8 )
      {
        v4 += 2LL;
        pcchRemaining = v4;
      }
      v10 = 32LL * (unsigned int)v8;
      a3 = (wchar_t **)*(unsigned int *)(v10 + v9);
      if ( (_DWORD)a3 )
      {
        v11 = *(_QWORD *)(v10 + v9 + 8);
        v12 = 0;
        do
        {
          if ( v12 )
            v4 += 3LL;
          a2 = -1;
          v13 = 32LL * v12;
          do
            ++a2;
          while ( *(_WORD *)(*(_QWORD *)(v13 + v11) + 2 * a2) );
          v14 = *(_QWORD *)(v13 + v11 + 8);
          v15 = -1;
          do
            ++v15;
          while ( *(_WORD *)(v14 + 2 * v15) );
          v4 += a2 + v15 + 1;
          ++v12;
        }
        while ( v12 < (unsigned int)a3 );
        pcchRemaining = v4;
      }
      v8 = (unsigned int)(v8 + 1);
    }
    while ( (unsigned int)v8 < *(_DWORD *)a1 );
  }
  v16 = (wchar_t *)(*(__int64 (__fastcall **)(size_t, __int64, wchar_t **, __int64))(v6 + 8))(2 * v4, a2, a3, v8);
  v17 = v16;
  if ( v16 )
  {
    memset_0(v16, 0, 2 * v4);
    v19 = v17;
    v20 = 0;
    ppszDestEnd = v17;
    while ( 2 )
    {
      if ( v20 >= *(_DWORD *)a1 )
      {
LABEL_33:
        *v5 = v17;
        return 0;
      }
      else
      {
        v21 = 32LL * v20;
        while ( 1 )
        {
          v22 = *(_QWORD *)(a1 + 8);
          if ( v3 >= *(_DWORD *)(v22 + 32LL * v20) )
            break;
          v18 = StringCchPrintfExW(
                  v19,
                  v4,
                  &ppszDestEnd,
                  &pcchRemaining,
                  0,
                  L"%ls=%ls",
                  *(_QWORD *)(32LL * v3 + *(_QWORD *)(v22 + v21 + 8)),
                  *(_QWORD *)(32LL * v3 + *(_QWORD *)(v22 + v21 + 8) + 8));
          if ( v18 < 0 )
          {
            v23 = 1035;
            goto LABEL_32;
          }
          if ( ++v3 < *(_DWORD *)(v21 + *(_QWORD *)(a1 + 8)) )
          {
            v18 = StringCchPrintfExW(ppszDestEnd, pcchRemaining, &ppszDestEnd, &pcchRemaining, 0, L"%ls", L"AND");
            if ( v18 < 0 )
            {
              v23 = 1052;
              goto LABEL_32;
            }
          }
          v4 = pcchRemaining;
          v19 = ppszDestEnd;
        }
        ++v20;
        v3 = 0;
        if ( v20 >= *(_DWORD *)a1 )
          goto LABEL_33;
        v18 = StringCchPrintfExW(v19, v4, &ppszDestEnd, &pcchRemaining, 0, L"%ls", L"OR");
        if ( v18 >= 0 )
        {
          v4 = pcchRemaining;
          v19 = ppszDestEnd;
          continue;
        }
        v23 = 1071;
LABEL_32:
        DebugTraceError(
          (unsigned int)v18,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c",
          v23);
        (*(void (__fastcall **)(wchar_t *))(v26 + 16))(v17);
      }
      break;
    }
  }
  else
  {
    v18 = -2146893810;
    DebugTraceError(
      2148073486LL,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c",
      1007);
  }
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x18001d538  mov     [rsp-38h+arg_18], rbx
0x18001d53d  mov     [rsp-38h+arg_8], rdx
0x18001d542  push    rbp
0x18001d543  push    rsi
0x18001d544  push    rdi
0x18001d545  push    r12
0x18001d547  push    r13
0x18001d549  push    r14
0x18001d54b  push    r15
0x18001d54d  mov     rbp, rsp
0x18001d550  sub     rsp, 40h
0x18001d554  xor     r15d, r15d
0x18001d557  mov     ebx, 1
0x18001d55c  mov     [r8], r15
0x18001d55f  mov     r13, r8
0x18001d562  mov     rsi, rdx
0x18001d565  mov     r14, rcx
0x18001d568  mov     r9d, r15d
0x18001d56b  mov     [rbp+pcchRemaining], rbx
0x18001d56f  cmp     [rcx], r15d
0x18001d572  jbe     short loc_18001D5EE
0x18001d574  mov     r10, [rcx+8]
0x18001d578  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001d57c  test    r9d, r9d
0x18001d57f  jz      short loc_18001D589
0x18001d581  add     rbx, 2
0x18001d585  mov     [rbp+pcchRemaining], rbx
0x18001d589  mov     eax, r9d
0x18001d58c  shl     rax, 5
0x18001d590  mov     r8d, [rax+r10]
0x18001d594  test    r8d, r8d
0x18001d597  jz      short loc_18001D5E6
0x18001d599  mov     rdi, [rax+r10+8]
0x18001d59e  mov     ecx, r15d
0x18001d5a1  test    ecx, ecx
0x18001d5a3  jz      short loc_18001D5A9
0x18001d5a5  add     rbx, 3
0x18001d5a9  mov     eax, ecx
0x18001d5ab  mov     rdx, r12
0x18001d5ae  shl     rax, 5
0x18001d5b2  mov     r11, [rax+rdi]
0x18001d5b6  inc     rdx
0x18001d5b9  cmp     [r11+rdx*2], r15w
0x18001d5be  jnz     short loc_18001D5B6
0x18001d5c0  mov     r11, [rax+rdi+8]
0x18001d5c5  mov     rax, r12
0x18001d5c8  inc     rax
0x18001d5cb  cmp     [r11+rax*2], r15w
0x18001d5d0  jnz     short loc_18001D5C8
0x18001d5d2  add     rax, rdx
0x18001d5d5  inc     rbx
0x18001d5d8  add     rbx, rax
0x18001d5db  inc     ecx
0x18001d5dd  cmp     ecx, r8d
0x18001d5e0  jb      short loc_18001D5A1
0x18001d5e2  mov     [rbp+pcchRemaining], rbx
0x18001d5e6  inc     r9d
0x18001d5e9  cmp     r9d, [r14]
0x18001d5ec  jb      short loc_18001D57C
0x18001d5ee  mov     rax, [rsi+8]
0x18001d5f2  lea     rdi, [rbx+rbx]
0x18001d5f6  mov     rcx, rdi
0x18001d5f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5fe  mov     rsi, rax
0x18001d601  test    rax, rax
0x18001d604  jnz     short loc_18001D62E
0x18001d606  mov     r9d, 3EFh
0x18001d60c  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001d613  lea     rdx, aStatus; "Status"
0x18001d61a  mov     ecx, 8009000Eh
0x18001d61f  mov     ebx, 8009000Eh
0x18001d624  call    DebugTraceError
0x18001d629  jmp     loc_18001D795
0x18001d62e  mov     r8, rdi; Size
0x18001d631  xor     edx, edx; Val
0x18001d633  mov     rcx, rsi; void *
0x18001d636  call    memset_0
0x18001d63b  mov     rcx, rsi; pszDest
0x18001d63e  mov     edi, r15d
0x18001d641  mov     [rbp+ppszDestEnd], rcx
0x18001d645  cmp     edi, [r14]
0x18001d648  jnb     loc_18001D78E
0x18001d64e  mov     r12d, edi
0x18001d651  shl     r12, 5
0x18001d655  mov     r8, [r14+8]
0x18001d659  cmp     r15d, [r8+r12]
0x18001d65d  jnb     loc_18001D707
0x18001d663  mov     r8, [r8+r12+8]
0x18001d668  mov     rdx, rbx; cchDest
0x18001d66b  mov     r9d, r15d
0x18001d66e  shl     r9, 5
0x18001d672  mov     rax, [r9+r8+8]
0x18001d677  mov     [rsp+40h+var_8], rax
0x18001d67c  mov     rax, [r9+r8]
0x18001d680  lea     r9, [rbp+pcchRemaining]; pcchRemaining
0x18001d684  mov     [rsp+40h+var_10], rax
0x18001d689  lea     r8, [rbp+ppszDestEnd]; ppszDestEnd
0x18001d68d  lea     rax, aLsLs; "%ls=%ls"
0x18001d694  mov     [rsp+40h+pszFormat], rax; pszFormat
0x18001d699  mov     qword ptr [rsp+40h+dwFlags], 0; dwFlags
0x18001d6a2  call    StringCchPrintfExW
0x18001d6a7  mov     ebx, eax
0x18001d6a9  test    eax, eax
0x18001d6ab  js      loc_18001D759
0x18001d6b1  mov     rax, [r14+8]
0x18001d6b5  inc     r15d
0x18001d6b8  cmp     r15d, [r12+rax]
0x18001d6bc  jnb     short loc_18001D6FA
0x18001d6be  mov     rdx, [rbp+pcchRemaining]; cchDest
0x18001d6c2  lea     rax, aAnd; "AND"
0x18001d6c9  mov     rcx, [rbp+ppszDestEnd]; pszDest
0x18001d6cd  lea     r9, [rbp+pcchRemaining]; pcchRemaining
0x18001d6d1  mov     [rsp+40h+var_10], rax
0x18001d6d6  lea     r8, [rbp+ppszDestEnd]; ppszDestEnd
0x18001d6da  lea     rax, aLs; "%ls"
0x18001d6e1  mov     [rsp+40h+pszFormat], rax; pszFormat
0x18001d6e6  mov     qword ptr [rsp+40h+dwFlags], 0; dwFlags
0x18001d6ef  call    StringCchPrintfExW
0x18001d6f4  mov     ebx, eax
0x18001d6f6  test    eax, eax
0x18001d6f8  js      short loc_18001D751
0x18001d6fa  mov     rbx, [rbp+pcchRemaining]
0x18001d6fe  mov     rcx, [rbp+ppszDestEnd]
0x18001d702  jmp     loc_18001D655
0x18001d707  inc     edi
0x18001d709  xor     r15d, r15d
0x18001d70c  cmp     edi, [r14]
0x18001d70f  jnb     short loc_18001D78E
0x18001d711  lea     rax, aOr; "OR"
0x18001d718  mov     rdx, rbx; cchDest
0x18001d71b  mov     [rsp+40h+var_10], rax
0x18001d720  lea     r9, [rbp+pcchRemaining]; pcchRemaining
0x18001d724  lea     rax, aLs; "%ls"
0x18001d72b  mov     [rsp+40h+pszFormat], rax; pszFormat
0x18001d730  lea     r8, [rbp+ppszDestEnd]; ppszDestEnd
0x18001d734  mov     qword ptr [rsp+40h+dwFlags], r15; dwFlags
0x18001d739  call    StringCchPrintfExW
0x18001d73e  mov     ebx, eax
0x18001d740  test    eax, eax
0x18001d742  js      short loc_18001D761
0x18001d744  mov     rbx, [rbp+pcchRemaining]
0x18001d748  mov     rcx, [rbp+ppszDestEnd]
0x18001d74c  jmp     loc_18001D645
0x18001d751  mov     r9d, 41Ch
0x18001d757  jmp     short loc_18001D767
0x18001d759  mov     r9d, 40Bh
0x18001d75f  jmp     short loc_18001D767
0x18001d761  mov     r9d, 42Fh
0x18001d767  mov     ecx, ebx
0x18001d769  lea     rdx, aStatus; "Status"
0x18001d770  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001d777  call    DebugTraceError
0x18001d77c  mov     rax, [rbp+arg_8]
0x18001d780  mov     rcx, rsi
0x18001d783  mov     rax, [rax+10h]
0x18001d787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d78c  jmp     short loc_18001D795
0x18001d78e  mov     [r13+0], rsi
0x18001d792  mov     ebx, r15d
0x18001d795  mov     eax, ebx
0x18001d797  mov     rbx, [rsp+40h+arg_18]
0x18001d79f  add     rsp, 40h
0x18001d7a3  pop     r15
0x18001d7a5  pop     r14
0x18001d7a7  pop     r13
0x18001d7a9  pop     r12
0x18001d7ab  pop     rdi
0x18001d7ac  pop     rsi
0x18001d7ad  pop     rbp
0x18001d7ae  retn
```
