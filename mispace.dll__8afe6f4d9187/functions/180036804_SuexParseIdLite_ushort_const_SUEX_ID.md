# SuexParseIdLite(ushort const *,_SUEX_ID *)

- ea: `0x180036804`
- end: `0x180036a91`
- name: `?SuexParseIdLite@@YAKPEBGPEAU_SUEX_ID@@@Z`
- size: `653`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, struct _SUEX_ID *)`
- caller_count: `54`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001ab18`
- `0x18002d87c`
- `0x18002da3c`
- `0x18002df14`
- `0x18002eee4`
- `0x18002f550`
- `0x18002fe30`
- `0x180030444`
- `0x180030808`
- `0x180030b10`
- `0x180030fc8`
- `0x180031480`
- `0x180031914`
- `0x180031b2c`
- `0x180031eb8`
- `0x180032a54`
- `0x180033650`
- `0x18003487c`
- `0x180036710`
- `0x18003d050`
- `0x18003f72c`
- `0x180040bb8`
- `0x1800419c0`
- `0x1800421dc`
- `0x180042378`
- `0x180042968`
- `0x180042d84`
- `0x1800430b0`
- `0x1800433d4`
- `0x180052080`
- `0x180056660`
- `0x1800611b0`
- `0x180077f70`
- `0x1800792a8`
- `0x1800796e0`
- `0x180098dc4`
- `0x18009d8f8`
- `0x1800a3f58`
- `0x1800a6e90`
- `0x1800a7f50`
- `0x1800c3940`
- `0x1800c9d40`
- `0x1800cfcd4`
- `0x1800e7f64`
- `0x1800eb2f0`
- `0x1800fcf10`
- `0x18010928c`
- `0x180109608`
- `0x180109b9c`
- `0x180109e50`

## callees

- `0x18000cdc8`
- `0x180036804`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180036815`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800369ce`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800369dc`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180036a2b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180036a3a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180036a48`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180036a5b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180036a6e`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180036815`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800369ce`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800369dc`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180036a2b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180036a3a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180036a48`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180036a5b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180036a6e`

## pseudocode

```c
__int64 __fastcall SuexParseIdLite(const unsigned __int16 *a1, struct _SUEX_ID *a2)
{
  unsigned __int16 v4; // ax
  const unsigned __int16 *v5; // r14
  unsigned int v6; // ecx
  unsigned int v7; // esi
  const OLECHAR *v8; // r14
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  const OLECHAR *v15; // rcx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  __int128 v21; // xmm0

  CLSIDFromString(a1, (LPCLSID)a2);
  *((_DWORD *)a2 + 4) = 2;
  v4 = a1[39];
  switch ( v4 )
  {
    case 'C':
      v5 = a1 + 40;
      if ( *v5 == 72 )
      {
        v6 = 40;
LABEL_39:
        *((_DWORD *)a2 + 5) = v6;
        goto LABEL_43;
      }
      return 50;
    case 'I':
      v5 = a1 + 40;
      if ( *v5 == 73 )
      {
        v6 = 1;
        goto LABEL_39;
      }
      return 50;
    case 'M':
      v5 = a1 + 40;
      if ( *v5 == 83 )
      {
        *((_DWORD *)a2 + 5) = 2;
        v6 = 2;
        goto LABEL_43;
      }
      return 50;
    case 'P':
      v5 = a1 + 40;
      if ( *v5 == 68 )
      {
        v6 = 4;
        goto LABEL_39;
      }
      if ( *v5 == 82 )
      {
        v6 = 34;
        goto LABEL_39;
      }
      return 50;
    case 'R':
      v5 = a1 + 40;
      switch ( *v5 )
      {
        case 'A':
          v6 = 41;
          goto LABEL_39;
        case 'C':
          v6 = 6;
          goto LABEL_39;
        case 'S':
          v6 = 7;
          goto LABEL_39;
      }
      return 50;
    case 'S':
      v5 = a1 + 40;
      switch ( *v5 )
      {
        case 'E':
          v6 = 8;
          goto LABEL_39;
        case 'I':
          v6 = 42;
          goto LABEL_39;
        case 'J':
          v6 = 9;
          goto LABEL_39;
        case 'N':
          *((_DWORD *)a2 + 5) = 10;
          v6 = 10;
          goto LABEL_43;
        case 'P':
          *((_DWORD *)a2 + 5) = 11;
          v6 = 11;
          goto LABEL_43;
        case 'S':
          v6 = 13;
          goto LABEL_39;
        case 'T':
          v6 = 12;
          goto LABEL_39;
        case 'U':
          v6 = 39;
          goto LABEL_39;
      }
      return 50;
  }
  if ( v4 != 86 )
    return 50;
  v5 = a1 + 40;
  if ( *v5 != 68 )
    return 50;
  *((_DWORD *)a2 + 5) = 16;
  v6 = 16;
LABEL_43:
  v7 = 0;
  v8 = v5 + 2;
  if ( v6 > 0xA )
  {
    v16 = v6 - 11;
    if ( v16 )
    {
      v17 = v16 - 1;
      if ( !v17 )
        goto LABEL_63;
      v18 = v17 - 4;
      if ( v18 )
      {
        v19 = v18 - 23;
        if ( v19 )
        {
          v20 = v19 - 1;
          if ( v20 )
          {
            if ( v20 - 1 > 1 )
              return v7;
          }
        }
LABEL_60:
        v15 = v8;
        goto LABEL_61;
      }
      CLSIDFromString(v8, (LPCLSID)((char *)a2 + 40));
      CLSIDFromString(v8 + 38, (LPCLSID)((char *)a2 + 56));
      v21 = *(_OWORD *)((char *)a2 + 56);
    }
    else
    {
      CLSIDFromString(v8, (LPCLSID)((char *)a2 + 40));
      v21 = *(_OWORD *)((char *)a2 + 40);
    }
    *(_OWORD *)((char *)a2 + 24) = v21;
    return v7;
  }
  if ( v6 == 10 )
    return (unsigned int)StringCchCopyW((unsigned __int16 *)a2 + 12, 0x10u, v8);
  v9 = v6 - 1;
  if ( !v9 )
    return (unsigned int)StringCchCopyW((unsigned __int16 *)a2 + 12, 0x10u, v8);
  v10 = v9 - 1;
  if ( !v10 )
    return (unsigned int)StringCchCopyW((unsigned __int16 *)a2 + 12, 0x10u, v8);
  v11 = v10 - 2;
  if ( !v11 )
    goto LABEL_60;
  v12 = v11 - 2;
  if ( !v12 )
    goto LABEL_60;
  v13 = v12 - 1;
  if ( !v13 )
  {
LABEL_63:
    CLSIDFromString(v8, (LPCLSID)((char *)a2 + 40));
    v15 = v8 + 38;
    goto LABEL_61;
  }
  v14 = v13 - 1;
  if ( !v14 )
    goto LABEL_60;
  if ( v14 == 1 )
  {
    CLSIDFromString(v8, (LPCLSID)((char *)a2 + 40));
    CLSIDFromString(v8 + 38, (LPCLSID)((char *)a2 + 56));
    v15 = v8 + 76;
LABEL_61:
    CLSIDFromString(v15, (LPCLSID)((char *)a2 + 24));
  }
  return v7;
}

```

## disassembly

```asm
0x180036804  push    rbx
0x180036806  push    rbp
0x180036807  push    rsi
0x180036808  push    rdi
0x180036809  push    r14
0x18003680b  sub     rsp, 20h
0x18003680f  mov     rbp, rdx
0x180036812  mov     r14, rcx
0x180036815  call    cs:__imp_CLSIDFromString
0x18003681b  mov     edx, 2
0x180036820  mov     [rbp+10h], edx
0x180036823  movzx   eax, word ptr [r14+4Eh]
0x180036828  lea     r10d, [rdx+0Eh]
0x18003682c  lea     r9d, [rdx+9]
0x180036830  lea     r8d, [rdx+8]
0x180036834  cmp     ax, 43h ; 'C'
0x180036838  jnz     short loc_180036851
0x18003683a  add     r14, 50h ; 'P'
0x18003683e  cmp     word ptr [r14], 48h ; 'H'
0x180036843  jnz     loc_180036A7F
0x180036849  lea     ecx, [rdx+26h]
0x18003684c  jmp     loc_18003696C
0x180036851  cmp     ax, 49h ; 'I'
0x180036855  jnz     short loc_18003686F
0x180036857  add     r14, 50h ; 'P'
0x18003685b  cmp     [r14], ax
0x18003685f  jnz     loc_180036A7F
0x180036865  mov     ecx, 1
0x18003686a  jmp     loc_18003696C
0x18003686f  cmp     ax, 4Dh ; 'M'
0x180036873  jnz     short loc_18003688E
0x180036875  add     r14, 50h ; 'P'
0x180036879  cmp     word ptr [r14], 53h ; 'S'
0x18003687e  jnz     loc_180036A7F
0x180036884  mov     [rbp+14h], edx
0x180036887  mov     ecx, edx
0x180036889  jmp     loc_180036991
0x18003688e  cmp     ax, 50h ; 'P'
0x180036892  jnz     short loc_1800368BE
0x180036894  add     r14, 50h ; 'P'
0x180036898  cmp     word ptr [r14], 44h ; 'D'
0x18003689d  jz      short loc_1800368B4
0x18003689f  cmp     word ptr [r14], 52h ; 'R'
0x1800368a4  jnz     loc_180036A7F
0x1800368aa  mov     ecx, 22h ; '"'
0x1800368af  jmp     loc_18003696C
0x1800368b4  mov     ecx, 4
0x1800368b9  jmp     loc_18003696C
0x1800368be  cmp     ax, 52h ; 'R'
0x1800368c2  jnz     short loc_1800368F9
0x1800368c4  add     r14, 50h ; 'P'
0x1800368c8  cmp     word ptr [r14], 41h ; 'A'
0x1800368cd  jz      short loc_1800368F2
0x1800368cf  cmp     word ptr [r14], 43h ; 'C'
0x1800368d4  jz      short loc_1800368EB
0x1800368d6  cmp     word ptr [r14], 53h ; 'S'
0x1800368db  jnz     loc_180036A7F
0x1800368e1  mov     ecx, 7
0x1800368e6  jmp     loc_18003696C
0x1800368eb  mov     ecx, 6
0x1800368f0  jmp     short loc_18003696C
0x1800368f2  mov     ecx, 29h ; ')'
0x1800368f7  jmp     short loc_18003696C
0x1800368f9  cmp     ax, 53h ; 'S'
0x1800368fd  jnz     short loc_180036971
0x1800368ff  add     r14, 50h ; 'P'
0x180036903  movzx   ecx, word ptr [r14]
0x180036907  sub     ecx, 45h ; 'E'
0x18003690a  jz      short loc_180036967
0x18003690c  sub     ecx, 4
0x18003690f  jz      short loc_180036960
0x180036911  sub     ecx, 1
0x180036914  jz      short loc_180036959
0x180036916  sub     ecx, 4
0x180036919  jz      short loc_180036950
0x18003691b  sub     ecx, edx
0x18003691d  jz      short loc_180036947
0x18003691f  sub     ecx, 3
0x180036922  jz      short loc_180036940
0x180036924  sub     ecx, 1
0x180036927  jz      short loc_180036939
0x180036929  cmp     ecx, 1
0x18003692c  jnz     loc_180036A7F
0x180036932  mov     ecx, 27h ; '''
0x180036937  jmp     short loc_18003696C
0x180036939  mov     ecx, 0Ch
0x18003693e  jmp     short loc_18003696C
0x180036940  mov     ecx, 0Dh
0x180036945  jmp     short loc_18003696C
0x180036947  mov     [rbp+14h], r9d
0x18003694b  mov     ecx, r9d
0x18003694e  jmp     short loc_180036991
0x180036950  mov     [rbp+14h], r8d
0x180036954  mov     ecx, r8d
0x180036957  jmp     short loc_180036991
0x180036959  mov     ecx, 9
0x18003695e  jmp     short loc_18003696C
0x180036960  mov     ecx, 2Ah ; '*'
0x180036965  jmp     short loc_18003696C
0x180036967  mov     ecx, 8
0x18003696c  mov     [rbp+14h], ecx
0x18003696f  jmp     short loc_180036991
0x180036971  cmp     ax, 56h ; 'V'
0x180036975  jnz     loc_180036A7F
0x18003697b  add     r14, 50h ; 'P'
0x18003697f  cmp     word ptr [r14], 44h ; 'D'
0x180036984  jnz     loc_180036A7F
0x18003698a  mov     [rbp+14h], r10d
0x18003698e  mov     ecx, r10d
0x180036991  xor     esi, esi
0x180036993  add     r14, 4
0x180036997  cmp     ecx, r8d
0x18003699a  ja      short loc_180036A01
0x18003699c  jz      short loc_1800369EB
0x18003699e  sub     ecx, 1
0x1800369a1  jz      short loc_1800369EB
0x1800369a3  sub     ecx, 1
0x1800369a6  jz      short loc_1800369EB
0x1800369a8  sub     ecx, edx
0x1800369aa  jz      short loc_180036A24
0x1800369ac  sub     ecx, edx
0x1800369ae  jz      short loc_180036A24
0x1800369b0  sub     ecx, 1
0x1800369b3  jz      loc_180036A54
0x1800369b9  sub     ecx, 1
0x1800369bc  jz      short loc_180036A24
0x1800369be  cmp     ecx, 1
0x1800369c1  jnz     loc_180036A84
0x1800369c7  lea     rdx, [rbp+28h]; pclsid
0x1800369cb  mov     rcx, r14; lpsz
0x1800369ce  call    cs:__imp_CLSIDFromString
0x1800369d4  lea     rdx, [rbp+38h]; pclsid
0x1800369d8  lea     rcx, [r14+4Ch]; lpsz
0x1800369dc  call    cs:__imp_CLSIDFromString
0x1800369e2  lea     rcx, [r14+98h]
0x1800369e9  jmp     short loc_180036A27
0x1800369eb  lea     rcx, [rbp+18h]; unsigned __int16 *
0x1800369ef  mov     r8, r14; unsigned __int16 *
0x1800369f2  mov     rdx, r10; unsigned __int64
0x1800369f5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800369fa  mov     esi, eax
0x1800369fc  jmp     loc_180036A84
0x180036a01  sub     ecx, r9d
0x180036a04  jz      short loc_180036A67
0x180036a06  sub     ecx, 1
0x180036a09  jz      short loc_180036A54
0x180036a0b  sub     ecx, 4
0x180036a0e  jz      short loc_180036A33
0x180036a10  sub     ecx, 17h
0x180036a13  jz      short loc_180036A24
0x180036a15  sub     ecx, 1
0x180036a18  jz      short loc_180036A24
0x180036a1a  sub     ecx, 1
0x180036a1d  jz      short loc_180036A24
0x180036a1f  cmp     ecx, 1
0x180036a22  jnz     short loc_180036A84
0x180036a24  mov     rcx, r14; lpsz
0x180036a27  lea     rdx, [rbp+18h]; pclsid
0x180036a2b  call    cs:__imp_CLSIDFromString
0x180036a31  jmp     short loc_180036A84
0x180036a33  lea     rdx, [rbp+28h]; pclsid
0x180036a37  mov     rcx, r14; lpsz
0x180036a3a  call    cs:__imp_CLSIDFromString
0x180036a40  lea     rcx, [r14+4Ch]; lpsz
0x180036a44  lea     rdx, [rbp+38h]; pclsid
0x180036a48  call    cs:__imp_CLSIDFromString
0x180036a4e  movups  xmm0, xmmword ptr [rbp+38h]
0x180036a52  jmp     short loc_180036A78
0x180036a54  lea     rdx, [rbp+28h]; pclsid
0x180036a58  mov     rcx, r14; lpsz
0x180036a5b  call    cs:__imp_CLSIDFromString
0x180036a61  lea     rcx, [r14+4Ch]
0x180036a65  jmp     short loc_180036A27
0x180036a67  lea     rdx, [rbp+28h]; pclsid
0x180036a6b  mov     rcx, r14; lpsz
0x180036a6e  call    cs:__imp_CLSIDFromString
0x180036a74  movups  xmm0, xmmword ptr [rbp+28h]
0x180036a78  movdqu  xmmword ptr [rbp+18h], xmm0
0x180036a7d  jmp     short loc_180036A84
0x180036a7f  mov     esi, 32h ; '2'
0x180036a84  mov     eax, esi
0x180036a86  add     rsp, 20h
0x180036a8a  pop     r14
0x180036a8c  pop     rdi
0x180036a8d  pop     rsi
0x180036a8e  pop     rbp
0x180036a8f  pop     rbx
0x180036a90  retn
```
