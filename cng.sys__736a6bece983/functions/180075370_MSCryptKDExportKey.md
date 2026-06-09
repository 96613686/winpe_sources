# MSCryptKDExportKey

- ea: `0x180075370`
- end: `0x180075534`
- name: `MSCryptKDExportKey`
- size: `452`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800751b0`

## callees

- `0x18000743c`
- `0x18003a5b0`
- `0x18003aa20`
- `0x180075370`
- `0x18009f616`
- `0x18009f780`

## string_xrefs

- `0x1800753b0`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18007541b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180075456`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`

## pseudocode

```c
__int64 __fastcall MSCryptKDExportKey(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        _DWORD *a4,
        unsigned int a5,
        unsigned int *a6,
        int a7)
{
  unsigned int v7; // r15d
  unsigned int v10; // esi
  __int64 v11; // r9
  __int64 v12; // rcx
  unsigned int *v13; // r14
  __int64 v15; // rbp
  __int64 v16; // r9
  __int64 v17; // rcx
  void *v18; // r9
  int v19; // ecx
  __int64 v20; // r9
  __int64 v21; // rbx
  __int64 v22[9]; // [rsp+20h] [rbp-48h] BYREF

  v7 = 0;
  v22[0] = 0;
  if ( a7 )
  {
    v10 = -1073741811;
    v11 = 1807;
    v12 = 3221225485LL;
LABEL_3:
    DebugTraceError(
      v12,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      v11);
    goto LABEL_4;
  }
  v10 = ValidateKeyDerivationKey(a1, v22);
  if ( (v10 & 0x80000000) == 0 )
  {
    v15 = v22[0];
    if ( v22[0] )
    {
      v13 = a6;
      if ( !a6 )
      {
        v10 = -1073741811;
        DebugTraceError(
          3221225485LL,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
          1830);
        return v10;
      }
      if ( a3 )
      {
        if ( !wcscmp_0(a3, L"KeyDataBlob") )
        {
          v7 = *(_DWORD *)(v15 + 16) + 12;
          if ( *(_QWORD *)(v15 + 72) )
            v7 += *(_DWORD *)(v15 + 64) + 4;
          if ( a4 )
          {
            if ( a5 >= v7 )
            {
              *a4 = 1296188491;
              v18 = a4 + 3;
              a4[1] = 1;
              v19 = *(_DWORD *)(v15 + 16);
              a4[2] = v19;
              if ( *(_QWORD *)(v15 + 72) )
              {
                a4[2] = *(_DWORD *)(v15 + 64) + v19 + 4;
                ReverseMemCopy(a4 + 3, v15 + 64, 4);
                v21 = v20 + 4;
                memmove((void *)(v20 + 4), *(const void **)(v15 + 56), *(unsigned int *)(v15 + 64));
                v18 = (void *)(v21 + *(unsigned int *)(v15 + 64));
              }
              memmove(v18, *(const void **)(v15 + 24), *(unsigned int *)(v15 + 16));
            }
            else
            {
              v10 = -1073741789;
            }
          }
          else
          {
            v10 = 0;
          }
          goto LABEL_5;
        }
        v10 = -1073741637;
        v16 = 1888;
        v17 = 3221225659LL;
      }
      else
      {
        v10 = -1073741811;
        v16 = 1837;
        v17 = 3221225485LL;
      }
      DebugTraceError(
        v17,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        v16);
LABEL_5:
      *v13 = v7;
      return v10;
    }
    v10 = -1073741816;
    v11 = 1823;
    v12 = 3221225480LL;
    goto LABEL_3;
  }
LABEL_4:
  v13 = a6;
  if ( a6 )
    goto LABEL_5;
  return v10;
}

```

## disassembly

```asm
0x180075370  push    rbx
0x180075372  push    rbp
0x180075373  push    rsi
0x180075374  push    rdi
0x180075375  push    r14
0x180075377  push    r15
0x180075379  sub     rsp, 38h
0x18007537d  xor     r15d, r15d
0x180075380  mov     [rsp+68h+var_48], 0
0x180075389  mov     rbx, r9
0x18007538c  mov     rdi, r8
0x18007538f  cmp     [rsp+68h+arg_30], r15d
0x180075397  jz      short loc_1800753DC
0x180075399  mov     esi, 0C000000Dh
0x18007539e  mov     r9d, 70Fh
0x1800753a4  mov     ecx, 0C000000Dh
0x1800753a9  lea     rdx, aStatus; "Status"
0x1800753b0  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800753b7  call    DebugTraceError
0x1800753bc  mov     r14, [rsp+68h+arg_28]
0x1800753c4  test    r14, r14
0x1800753c7  jz      short loc_1800753CC
0x1800753c9  mov     [r14], r15d
0x1800753cc  mov     eax, esi
0x1800753ce  add     rsp, 38h
0x1800753d2  pop     r15
0x1800753d4  pop     r14
0x1800753d6  pop     rdi
0x1800753d7  pop     rsi
0x1800753d8  pop     rbp
0x1800753d9  pop     rbx
0x1800753da  retn
0x1800753dc  lea     rdx, [rsp+68h+var_48]
0x1800753e1  call    ValidateKeyDerivationKey
0x1800753e6  mov     esi, eax
0x1800753e8  test    eax, eax
0x1800753ea  js      short loc_1800753BC
0x1800753ec  mov     rbp, [rsp+68h+var_48]
0x1800753f1  test    rbp, rbp
0x1800753f4  jnz     short loc_180075408
0x1800753f6  mov     esi, 0C0000008h
0x1800753fb  mov     r9d, 71Fh
0x180075401  mov     ecx, 0C0000008h
0x180075406  jmp     short loc_1800753A9
0x180075408  mov     r14, [rsp+68h+arg_28]
0x180075410  test    r14, r14
0x180075413  jnz     short loc_18007543A
0x180075415  mov     r9d, 726h
0x18007541b  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180075422  lea     rdx, aStatus; "Status"
0x180075429  mov     ecx, 0C000000Dh
0x18007542e  mov     esi, 0C000000Dh
0x180075433  call    DebugTraceError
0x180075438  jmp     short loc_1800753CC
0x18007543a  test    rdi, rdi
0x18007543d  jnz     short loc_180075467
0x18007543f  mov     esi, 0C000000Dh
0x180075444  mov     r9d, 72Dh
0x18007544a  mov     ecx, 0C000000Dh
0x18007544f  lea     rdx, aStatus; "Status"
0x180075456  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007545d  call    DebugTraceError
0x180075462  jmp     loc_1800753C9
0x180075467  lea     rdx, aKeydatablob; "KeyDataBlob"
0x18007546e  mov     rcx, rdi; Str1
0x180075471  call    wcscmp_0
0x180075476  test    eax, eax
0x180075478  jnz     loc_18007551F
0x18007547e  mov     r15d, [rbp+10h]
0x180075482  add     r15d, 0Ch
0x180075486  cmp     qword ptr [rbp+48h], 0
0x18007548b  jz      short loc_180075496
0x18007548d  mov     eax, [rbp+40h]
0x180075490  add     eax, 4
0x180075493  add     r15d, eax
0x180075496  test    rbx, rbx
0x180075499  jnz     short loc_1800754A2
0x18007549b  xor     esi, esi
0x18007549d  jmp     loc_1800753C9
0x1800754a2  cmp     [rsp+68h+arg_20], r15d
0x1800754aa  jnb     short loc_1800754B6
0x1800754ac  mov     esi, 0C0000023h
0x1800754b1  jmp     loc_1800753C9
0x1800754b6  mov     dword ptr [rbx], 4D42444Bh
0x1800754bc  lea     r9, [rbx+0Ch]
0x1800754c0  mov     dword ptr [rbx+4], 1
0x1800754c7  mov     ecx, [rbp+10h]
0x1800754ca  mov     [rbx+8], ecx
0x1800754cd  cmp     qword ptr [rbp+48h], 0
0x1800754d2  jz      short loc_18007550A
0x1800754d4  lea     rdi, [rbp+40h]
0x1800754d8  add     ecx, 4
0x1800754db  add     ecx, [rdi]
0x1800754dd  mov     r8d, 4
0x1800754e3  mov     [rbx+8], ecx
0x1800754e6  mov     rdx, rdi
0x1800754e9  mov     rcx, r9
0x1800754ec  call    ReverseMemCopy
0x1800754f1  mov     r8d, [rdi]; Size
0x1800754f4  lea     rbx, [r9+4]
0x1800754f8  mov     rdx, [rbp+38h]; Src
0x1800754fc  mov     rcx, rbx; void *
0x1800754ff  call    memmove
0x180075504  mov     r9d, [rdi]
0x180075507  add     r9, rbx
0x18007550a  mov     r8d, [rbp+10h]; Size
0x18007550e  mov     rcx, r9; void *
0x180075511  mov     rdx, [rbp+18h]; Src
0x180075515  call    memmove
0x18007551a  jmp     loc_1800753C9
0x18007551f  mov     esi, 0C00000BBh
0x180075524  mov     r9d, 760h
0x18007552a  mov     ecx, 0C00000BBh
0x18007552f  jmp     loc_18007544F
```
