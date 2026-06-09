# VsmOpenAlgorithmProvider

- ea: `0x18005b598`
- end: `0x18005b959`
- name: `VsmOpenAlgorithmProvider`
- size: `961`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180045440`

## callees

- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x18005b1ec`
- `0x18005b598`
- `0x180069e8c`
- `0x18009f6d0`
- `0x18009fa80`
- `0x18009ffa0`

## import_xrefs

- `ntoskrnl!wcsncpy_s` at `0x18005b6d2`
- `ntoskrnl!wcsncpy_s` at `0x18005b6d2`

## string_xrefs

- `0x18005b8bd`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18005b928`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
__int64 __fastcall VsmOpenAlgorithmProvider(_QWORD *a1, const wchar_t *a2, const void *a3, unsigned int a4)
{
  unsigned int v6; // ebx
  __int64 v7; // r9
  __int64 v8; // rcx
  unsigned int i; // ecx
  __int64 v10; // r15
  wchar_t *v11; // rax
  signed __int64 v12; // r9
  __int64 v13; // r8
  __int64 v14; // rdx
  int v15; // esi
  char *v16; // rax
  char *v17; // rdi
  _OWORD *v18; // r14
  int Interface; // eax
  __int64 v20; // r9
  __int64 v21; // rax
  _OWORD *v22; // rcx
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  _QWORD *v30; // r14
  __int64 v31; // rcx
  wchar_t *v32; // rdx
  __int64 (__fastcall *v34)(char *, const wchar_t *, _QWORD); // [rsp+40h] [rbp-C0h] BYREF
  int v35; // [rsp+48h] [rbp-B8h] BYREF
  __int64 (__fastcall *v36)(_QWORD, const wchar_t *, char *, __int64, int *, _DWORD); // [rsp+50h] [rbp-B0h] BYREF
  void (__fastcall *v37)(_QWORD, wchar_t *, __int64 *, _QWORD, _DWORD); // [rsp+58h] [rbp-A8h] BYREF
  __int64 v38; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v39[448]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v41; // [rsp+250h] [rbp+150h] BYREF

  v41 = 4;
  v34 = 0;
  v38 = 0;
  v37 = 0;
  v36 = 0;
  v35 = 0;
  if ( !a3 || !memcmp(a3, L"Microsoft Primitive Provider", 0x3Au) )
  {
    for ( i = 0; i < 0x35; ++i )
    {
      v10 = 4LL * i;
      v11 = (&AlgorithmClassPropertyTable)[v10];
      v12 = (char *)a2 - (char *)v11;
      do
      {
        v13 = *(wchar_t *)((char *)v11 + v12);
        v14 = *v11 - (unsigned int)v13;
        if ( (_DWORD)v14 )
          break;
        ++v11;
      }
      while ( (_DWORD)v13 );
      if ( !(_DWORD)v14 )
      {
        v15 = *((_DWORD *)&AlgorithmClassPropertyTable + 2 * v10 + 2);
        if ( (unsigned int)(v15 - 1) > 7 )
        {
          v7 = 1677;
          goto LABEL_41;
        }
        v16 = (char *)MSCryptAlloc(968, v14, v13, v12);
        v17 = v16;
        if ( !v16 )
        {
          v6 = -1073741801;
          v7 = 1691;
          v8 = 3221225495LL;
          goto LABEL_42;
        }
        memset(v16, 0, 0x3C8u);
        *(_DWORD *)v17 = 968;
        *((_DWORD *)v17 + 1) = 1431655761;
        *((_DWORD *)v17 + 4) = 1;
        *((_DWORD *)v17 + 9) = v15;
        wcsncpy_s((wchar_t *)v17 + 222, 0x104u, a2, 0xFFFFFFFFFFFFFFFFuLL);
        v18 = v17 + 48;
        *((_DWORD *)v17 + 8) = a4 & 1;
        Interface = VsmLoadInterface(*((unsigned int *)v17 + 9), a2, a4, v17 + 48);
        v6 = Interface;
        if ( Interface < 0 )
        {
          v20 = 1722;
          goto LABEL_35;
        }
        v21 = 3;
        v22 = v39;
        do
        {
          v23 = v18[1];
          *v22 = *v18;
          v24 = v18[2];
          v22[1] = v23;
          v25 = v18[3];
          v22[2] = v24;
          v26 = v18[4];
          v22[3] = v25;
          v27 = v18[5];
          v22[4] = v26;
          v28 = v18[6];
          v22[5] = v27;
          v29 = v18[7];
          v18 += 8;
          v22[6] = v28;
          v22[7] = v29;
          v22 += 8;
          --v21;
        }
        while ( v21 );
        *(_QWORD *)v22 = *(_QWORD *)v18;
        Interface = ValidateFunctionTable(
                      v15,
                      (unsigned int)v39,
                      (unsigned int)&v34,
                      (unsigned int)&v38,
                      (__int64)&v37,
                      (__int64)&v36);
        v6 = Interface;
        if ( Interface < 0 )
        {
          v20 = 1731;
          goto LABEL_35;
        }
        v30 = v17 + 24;
        v6 = v34(v17 + 24, a2, a4);
        if ( v6 == -1073700863 )
        {
          if ( v15 == 2 )
          {
            if ( (a4 & 0x28) == 8 )
            {
              v34(v17 + 24, a2, a4 & 0xFFFFFFF7);
              *((_DWORD *)v17 + 2) |= 8u;
            }
LABEL_26:
            if ( !v36 )
            {
              v6 = -1073741595;
              v31 = 3221225701LL;
              v20 = 1769;
LABEL_36:
              DebugTraceError(v31, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v20);
              MSCryptFree(v17);
              return v6;
            }
            Interface = v36(*v30, L"HashBlockLength", v17 + 12, 4, &v35, 0);
            v6 = Interface;
            if ( Interface < 0 )
            {
              v20 = 1781;
LABEL_35:
              v31 = (unsigned int)Interface;
              goto LABEL_36;
            }
LABEL_37:
            v32 = (&AlgorithmClassPropertyTable)[v10 + 1];
            if ( v32 )
              v37(*v30, v32, &qword_1800A99C8[v10], *((unsigned int *)&AlgorithmClassPropertyTable + 2 * v10 + 7), 0);
            *a1 = v17;
            return v6;
          }
        }
        else if ( v15 == 2 )
        {
          goto LABEL_26;
        }
        if ( v15 == 3 )
        {
          if ( !v36 )
          {
            v6 = -1073741595;
            v31 = 3221225701LL;
            v20 = 1790;
            goto LABEL_36;
          }
          Interface = v36(*v30, L"PaddingSchemes", v17 + 440, v41, (int *)&v41, 0);
          v6 = Interface;
          if ( Interface < 0 )
          {
            v20 = 1802;
            goto LABEL_35;
          }
        }
        goto LABEL_37;
      }
    }
    v7 = 1668;
LABEL_41:
    v8 = 3221225480LL;
    v6 = -1073741816;
  }
  else
  {
    v6 = -1073741811;
    v7 = 1660;
    v8 = 3221225485LL;
  }
LABEL_42:
  DebugTraceError(v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v7);
  return v6;
}

```

## disassembly

```asm
0x18005b598  mov     [rsp-8+arg_8], rbx
0x18005b59d  mov     [rsp-8+arg_0], rcx
0x18005b5a2  push    rbp
0x18005b5a3  push    rsi
0x18005b5a4  push    rdi
0x18005b5a5  push    r12
0x18005b5a7  push    r13
0x18005b5a9  push    r14
0x18005b5ab  push    r15
0x18005b5ad  lea     rbp, [rsp-100h]
0x18005b5b5  sub     rsp, 200h
0x18005b5bc  xor     ebx, ebx
0x18005b5be  mov     [rbp+130h+arg_10], 4
0x18005b5c8  mov     [rsp+230h+var_1F0], rbx
0x18005b5cd  mov     r12d, r9d
0x18005b5d0  mov     [rsp+230h+var_1D0], rbx
0x18005b5d5  mov     rax, r8
0x18005b5d8  mov     [rsp+230h+var_1D8], rbx
0x18005b5dd  mov     r13, rdx
0x18005b5e0  mov     [rsp+230h+var_1E0], rbx
0x18005b5e5  mov     [rsp+230h+var_1E8], ebx
0x18005b5e9  test    r8, r8
0x18005b5ec  jz      short loc_18005B61A
0x18005b5ee  lea     r8d, [rbx+3Ah]; Size
0x18005b5f2  mov     rcx, rax; Buf1
0x18005b5f5  lea     rdx, pszProvider; "Microsoft Primitive Provider"
0x18005b5fc  call    memcmp
0x18005b601  test    eax, eax
0x18005b603  jz      short loc_18005B61A
0x18005b605  mov     ebx, 0C000000Dh
0x18005b60a  mov     r9d, 67Ch
0x18005b610  mov     ecx, 0C000000Dh
0x18005b615  jmp     loc_18005B928
0x18005b61a  mov     ecx, ebx
0x18005b61c  lea     r10, AlgorithmClassPropertyTable
0x18005b623  cmp     ecx, 35h ; '5'
0x18005b626  jnb     loc_18005B918
0x18005b62c  mov     r15d, ecx
0x18005b62f  mov     r9, r13
0x18005b632  shl     r15, 5
0x18005b636  mov     rax, [r15+r10]
0x18005b63a  sub     r9, rax
0x18005b63d  movzx   edx, word ptr [rax]
0x18005b640  movzx   r8d, word ptr [rax+r9]
0x18005b645  sub     edx, r8d
0x18005b648  jnz     short loc_18005B653
0x18005b64a  add     rax, 2
0x18005b64e  test    r8d, r8d
0x18005b651  jnz     short loc_18005B63D
0x18005b653  test    edx, edx
0x18005b655  jz      short loc_18005B65B
0x18005b657  inc     ecx
0x18005b659  jmp     short loc_18005B623
0x18005b65b  mov     esi, [r15+r10+8]
0x18005b660  lea     eax, [rsi-1]
0x18005b663  cmp     eax, 7
0x18005b666  jbe     short loc_18005B673
0x18005b668  mov     r9d, 68Dh
0x18005b66e  jmp     loc_18005B91E
0x18005b673  mov     r14d, 3C8h
0x18005b679  mov     ecx, r14d
0x18005b67c  call    MSCryptAlloc
0x18005b681  mov     rdi, rax
0x18005b684  test    rax, rax
0x18005b687  jnz     short loc_18005B69E
0x18005b689  mov     ebx, 0C0000017h
0x18005b68e  mov     r9d, 69Bh
0x18005b694  mov     ecx, 0C0000017h
0x18005b699  jmp     loc_18005B928
0x18005b69e  mov     r8, r14; Size
0x18005b6a1  xor     edx, edx; Val
0x18005b6a3  mov     rcx, rdi; void *
0x18005b6a6  call    memset
0x18005b6ab  lea     rcx, [rdi+1BCh]; Dst
0x18005b6b2  mov     [rdi], r14d
0x18005b6b5  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18005b6b9  mov     dword ptr [rdi+4], 55555551h
0x18005b6c0  mov     r8, r13; Src
0x18005b6c3  mov     dword ptr [rdi+10h], 1
0x18005b6ca  mov     edx, 104h; SizeInWords
0x18005b6cf  mov     [rdi+24h], esi
0x18005b6d2  call    cs:__imp_wcsncpy_s
0x18005b6d9  nop     dword ptr [rax+rax+00h]
0x18005b6de  mov     eax, r12d
0x18005b6e1  lea     r14, [rdi+30h]
0x18005b6e5  and     eax, 1
0x18005b6e8  mov     r9, r14
0x18005b6eb  mov     [rdi+20h], eax
0x18005b6ee  mov     r8d, r12d
0x18005b6f1  mov     ecx, [rdi+24h]
0x18005b6f4  mov     rdx, r13
0x18005b6f7  call    VsmLoadInterface
0x18005b6fc  mov     ebx, eax
0x18005b6fe  test    eax, eax
0x18005b700  jns     short loc_18005B70D
0x18005b702  mov     r9d, 6BAh
0x18005b708  jmp     loc_18005B8BB
0x18005b70d  mov     eax, 3
0x18005b712  lea     rcx, [rsp+230h+var_1C0]
0x18005b717  lea     edx, [rax+7Dh]
0x18005b71a  movups  xmm0, xmmword ptr [r14]
0x18005b71e  movups  xmm1, xmmword ptr [r14+10h]
0x18005b723  movups  xmmword ptr [rcx], xmm0
0x18005b726  movups  xmm0, xmmword ptr [r14+20h]
0x18005b72b  movups  xmmword ptr [rcx+10h], xmm1
0x18005b72f  movups  xmm1, xmmword ptr [r14+30h]
0x18005b734  movups  xmmword ptr [rcx+20h], xmm0
0x18005b738  movups  xmm0, xmmword ptr [r14+40h]
0x18005b73d  movups  xmmword ptr [rcx+30h], xmm1
0x18005b741  movups  xmm1, xmmword ptr [r14+50h]
0x18005b746  movups  xmmword ptr [rcx+40h], xmm0
0x18005b74a  movups  xmm0, xmmword ptr [r14+60h]
0x18005b74f  movups  xmmword ptr [rcx+50h], xmm1
0x18005b753  movups  xmm1, xmmword ptr [r14+70h]
0x18005b758  add     r14, rdx
0x18005b75b  movups  xmmword ptr [rcx+60h], xmm0
0x18005b75f  movups  xmmword ptr [rcx+70h], xmm1
0x18005b763  add     rcx, rdx
0x18005b766  sub     rax, 1
0x18005b76a  jnz     short loc_18005B71A
0x18005b76c  mov     rax, [r14]
0x18005b76f  lea     r9, [rsp+230h+var_1D0]
0x18005b774  mov     [rcx], rax
0x18005b777  lea     r8, [rsp+230h+var_1F0]
0x18005b77c  lea     rax, [rsp+230h+var_1E0]
0x18005b781  mov     ecx, esi
0x18005b783  mov     [rsp+230h+var_208], rax
0x18005b788  lea     rdx, [rsp+230h+var_1C0]
0x18005b78d  lea     rax, [rsp+230h+var_1D8]
0x18005b792  mov     [rsp+230h+var_210], rax
0x18005b797  call    ValidateFunctionTable
0x18005b79c  mov     ebx, eax
0x18005b79e  test    eax, eax
0x18005b7a0  jns     short loc_18005B7AD
0x18005b7a2  mov     r9d, 6C3h
0x18005b7a8  jmp     loc_18005B8BB
0x18005b7ad  mov     rax, [rsp+230h+var_1F0]
0x18005b7b2  lea     r14, [rdi+18h]
0x18005b7b6  mov     rcx, r14
0x18005b7b9  mov     r8d, r12d
0x18005b7bc  mov     rdx, r13
0x18005b7bf  call    _guard_dispatch_icall
0x18005b7c4  mov     ebx, eax
0x18005b7c6  cmp     eax, 0C000A001h
0x18005b7cb  jnz     short loc_18005B7FC
0x18005b7cd  cmp     esi, 2
0x18005b7d0  jnz     loc_18005B85D
0x18005b7d6  mov     eax, r12d
0x18005b7d9  and     al, 28h
0x18005b7db  cmp     al, 8
0x18005b7dd  jnz     short loc_18005B801
0x18005b7df  mov     rax, [rsp+230h+var_1F0]
0x18005b7e4  and     r12d, 0FFFFFFF7h
0x18005b7e8  mov     r8d, r12d
0x18005b7eb  mov     rdx, r13
0x18005b7ee  mov     rcx, r14
0x18005b7f1  call    _guard_dispatch_icall
0x18005b7f6  or      dword ptr [rdi+8], 8
0x18005b7fa  jmp     short loc_18005B801
0x18005b7fc  cmp     esi, 2
0x18005b7ff  jnz     short loc_18005B85D
0x18005b801  mov     rax, [rsp+230h+var_1E0]
0x18005b806  test    rax, rax
0x18005b809  jnz     short loc_18005B820
0x18005b80b  mov     ebx, 0C00000E5h
0x18005b810  mov     ecx, 0C00000E5h
0x18005b815  mov     r9d, 6E9h
0x18005b81b  jmp     loc_18005B8BD
0x18005b820  lea     rcx, [rsp+230h+var_1E8]
0x18005b825  mov     dword ptr [rsp+230h+var_208], 0
0x18005b82d  mov     [rsp+230h+var_210], rcx
0x18005b832  lea     r8, [rdi+0Ch]
0x18005b836  mov     rcx, [r14]
0x18005b839  lea     rdx, aHashblocklengt; "HashBlockLength"
0x18005b840  mov     r9d, 4
0x18005b846  call    _guard_dispatch_icall
0x18005b84b  mov     ebx, eax
0x18005b84d  test    eax, eax
0x18005b84f  jns     loc_18005B8DA
0x18005b855  mov     r9d, 6F5h
0x18005b85b  jmp     short loc_18005B8BB
0x18005b85d  cmp     esi, 3
0x18005b860  jnz     short loc_18005B8DA
0x18005b862  mov     rax, [rsp+230h+var_1E0]
0x18005b867  test    rax, rax
0x18005b86a  jnz     short loc_18005B87E
0x18005b86c  mov     ebx, 0C00000E5h
0x18005b871  mov     ecx, 0C00000E5h
0x18005b876  mov     r9d, 6FEh
0x18005b87c  jmp     short loc_18005B8BD
0x18005b87e  mov     r9d, [rbp+130h+arg_10]
0x18005b885  lea     rcx, [rbp+130h+arg_10]
0x18005b88c  mov     dword ptr [rsp+230h+var_208], 0
0x18005b894  lea     r8, [rdi+1B8h]
0x18005b89b  mov     [rsp+230h+var_210], rcx
0x18005b8a0  lea     rdx, aPaddingschemes; "PaddingSchemes"
0x18005b8a7  mov     rcx, [r14]
0x18005b8aa  call    _guard_dispatch_icall
0x18005b8af  mov     ebx, eax
0x18005b8b1  test    eax, eax
0x18005b8b3  jns     short loc_18005B8DA
0x18005b8b5  mov     r9d, 70Ah
0x18005b8bb  mov     ecx, eax
0x18005b8bd  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005b8c4  lea     rdx, aStatus; "Status"
0x18005b8cb  call    DebugTraceError
0x18005b8d0  mov     rcx, rdi; P
0x18005b8d3  call    MSCryptFree
0x18005b8d8  jmp     short loc_18005B93B
0x18005b8da  lea     r9, AlgorithmClassPropertyTable
0x18005b8e1  mov     rdx, [r15+r9+10h]
0x18005b8e6  test    rdx, rdx
0x18005b8e9  jz      short loc_18005B90C
0x18005b8eb  mov     rcx, [r14]
0x18005b8ee  lea     r8, [r9+18h]
0x18005b8f2  mov     r9d, [r15+r9+1Ch]
0x18005b8f7  add     r8, r15
0x18005b8fa  mov     rax, [rsp+230h+var_1D8]
0x18005b8ff  mov     dword ptr [rsp+230h+var_210], 0
0x18005b907  call    _guard_dispatch_icall
0x18005b90c  mov     rax, [rbp+130h+arg_0]
0x18005b913  mov     [rax], rdi
0x18005b916  jmp     short loc_18005B93B
0x18005b918  mov     r9d, 684h
0x18005b91e  mov     ecx, 0C0000008h
0x18005b923  mov     ebx, 0C0000008h
0x18005b928  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005b92f  lea     rdx, aStatus; "Status"
0x18005b936  call    DebugTraceError
0x18005b93b  mov     eax, ebx
0x18005b93d  mov     rbx, [rsp+230h+arg_8]
0x18005b945  add     rsp, 200h
0x18005b94c  pop     r15
0x18005b94e  pop     r14
0x18005b950  pop     r13
0x18005b952  pop     r12
0x18005b954  pop     rdi
0x18005b955  pop     rsi
0x18005b956  pop     rbp
0x18005b957  retn
```
