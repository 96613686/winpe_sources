# MSCryptKDExportKey

- ea: `0x18007eb00`
- end: `0x18007ecc4`
- name: `MSCryptKDExportKey`
- size: `452`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18007e940`

## callees

- `0x18001155c`
- `0x180043b20`
- `0x180043fb0`
- `0x18007eb00`
- `0x1800a4232`
- `0x1800a45c0`

## string_xrefs

- `0x18007eb40`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18007ebab`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18007ebe6`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`

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
0x18007eb00  push    rbx
0x18007eb02  push    rbp
0x18007eb03  push    rsi
0x18007eb04  push    rdi
0x18007eb05  push    r14
0x18007eb07  push    r15
0x18007eb09  sub     rsp, 38h
0x18007eb0d  xor     r15d, r15d
0x18007eb10  mov     [rsp+68h+var_48], 0
0x18007eb19  mov     rbx, r9
0x18007eb1c  mov     rdi, r8
0x18007eb1f  cmp     [rsp+68h+arg_30], r15d
0x18007eb27  jz      short loc_18007EB6C
0x18007eb29  mov     esi, 0C000000Dh
0x18007eb2e  mov     r9d, 70Fh
0x18007eb34  mov     ecx, 0C000000Dh
0x18007eb39  lea     rdx, aStatus; "Status"
0x18007eb40  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007eb47  call    DebugTraceError
0x18007eb4c  mov     r14, [rsp+68h+arg_28]
0x18007eb54  test    r14, r14
0x18007eb57  jz      short loc_18007EB5C
0x18007eb59  mov     [r14], r15d
0x18007eb5c  mov     eax, esi
0x18007eb5e  add     rsp, 38h
0x18007eb62  pop     r15
0x18007eb64  pop     r14
0x18007eb66  pop     rdi
0x18007eb67  pop     rsi
0x18007eb68  pop     rbp
0x18007eb69  pop     rbx
0x18007eb6a  retn
0x18007eb6c  lea     rdx, [rsp+68h+var_48]
0x18007eb71  call    ValidateKeyDerivationKey
0x18007eb76  mov     esi, eax
0x18007eb78  test    eax, eax
0x18007eb7a  js      short loc_18007EB4C
0x18007eb7c  mov     rbp, [rsp+68h+var_48]
0x18007eb81  test    rbp, rbp
0x18007eb84  jnz     short loc_18007EB98
0x18007eb86  mov     esi, 0C0000008h
0x18007eb8b  mov     r9d, 71Fh
0x18007eb91  mov     ecx, 0C0000008h
0x18007eb96  jmp     short loc_18007EB39
0x18007eb98  mov     r14, [rsp+68h+arg_28]
0x18007eba0  test    r14, r14
0x18007eba3  jnz     short loc_18007EBCA
0x18007eba5  mov     r9d, 726h
0x18007ebab  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007ebb2  lea     rdx, aStatus; "Status"
0x18007ebb9  mov     ecx, 0C000000Dh
0x18007ebbe  mov     esi, 0C000000Dh
0x18007ebc3  call    DebugTraceError
0x18007ebc8  jmp     short loc_18007EB5C
0x18007ebca  test    rdi, rdi
0x18007ebcd  jnz     short loc_18007EBF7
0x18007ebcf  mov     esi, 0C000000Dh
0x18007ebd4  mov     r9d, 72Dh
0x18007ebda  mov     ecx, 0C000000Dh
0x18007ebdf  lea     rdx, aStatus; "Status"
0x18007ebe6  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007ebed  call    DebugTraceError
0x18007ebf2  jmp     loc_18007EB59
0x18007ebf7  lea     rdx, aKeydatablob; "KeyDataBlob"
0x18007ebfe  mov     rcx, rdi; Str1
0x18007ec01  call    wcscmp_0
0x18007ec06  test    eax, eax
0x18007ec08  jnz     loc_18007ECAF
0x18007ec0e  mov     r15d, [rbp+10h]
0x18007ec12  add     r15d, 0Ch
0x18007ec16  cmp     qword ptr [rbp+48h], 0
0x18007ec1b  jz      short loc_18007EC26
0x18007ec1d  mov     eax, [rbp+40h]
0x18007ec20  add     eax, 4
0x18007ec23  add     r15d, eax
0x18007ec26  test    rbx, rbx
0x18007ec29  jnz     short loc_18007EC32
0x18007ec2b  xor     esi, esi
0x18007ec2d  jmp     loc_18007EB59
0x18007ec32  cmp     [rsp+68h+arg_20], r15d
0x18007ec3a  jnb     short loc_18007EC46
0x18007ec3c  mov     esi, 0C0000023h
0x18007ec41  jmp     loc_18007EB59
0x18007ec46  mov     dword ptr [rbx], 4D42444Bh
0x18007ec4c  lea     r9, [rbx+0Ch]
0x18007ec50  mov     dword ptr [rbx+4], 1
0x18007ec57  mov     ecx, [rbp+10h]
0x18007ec5a  mov     [rbx+8], ecx
0x18007ec5d  cmp     qword ptr [rbp+48h], 0
0x18007ec62  jz      short loc_18007EC9A
0x18007ec64  lea     rdi, [rbp+40h]
0x18007ec68  add     ecx, 4
0x18007ec6b  add     ecx, [rdi]
0x18007ec6d  mov     r8d, 4
0x18007ec73  mov     [rbx+8], ecx
0x18007ec76  mov     rdx, rdi
0x18007ec79  mov     rcx, r9
0x18007ec7c  call    ReverseMemCopy
0x18007ec81  mov     r8d, [rdi]; Size
0x18007ec84  lea     rbx, [r9+4]
0x18007ec88  mov     rdx, [rbp+38h]; Src
0x18007ec8c  mov     rcx, rbx; void *
0x18007ec8f  call    memmove
0x18007ec94  mov     r9d, [rdi]
0x18007ec97  add     r9, rbx
0x18007ec9a  mov     r8d, [rbp+10h]; Size
0x18007ec9e  mov     rcx, r9; void *
0x18007eca1  mov     rdx, [rbp+18h]; Src
0x18007eca5  call    memmove
0x18007ecaa  jmp     loc_18007EB59
0x18007ecaf  mov     esi, 0C00000BBh
0x18007ecb4  mov     r9d, 760h
0x18007ecba  mov     ecx, 0C00000BBh
0x18007ecbf  jmp     loc_18007EBDF
```
