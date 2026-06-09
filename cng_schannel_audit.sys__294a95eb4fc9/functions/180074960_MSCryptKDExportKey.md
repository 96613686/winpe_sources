# MSCryptKDExportKey

- ea: `0x180074960`
- end: `0x180074b24`
- name: `MSCryptKDExportKey`
- size: `452`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800747a0`

## callees

- `0x18000743c`
- `0x180039ab0`
- `0x180039f20`
- `0x180074960`
- `0x18009d746`
- `0x18009da40`

## string_xrefs

- `0x1800749a0`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180074a0b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180074a46`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`

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
0x180074960  push    rbx
0x180074962  push    rbp
0x180074963  push    rsi
0x180074964  push    rdi
0x180074965  push    r14
0x180074967  push    r15
0x180074969  sub     rsp, 38h
0x18007496d  xor     r15d, r15d
0x180074970  mov     [rsp+68h+var_48], 0
0x180074979  mov     rbx, r9
0x18007497c  mov     rdi, r8
0x18007497f  cmp     [rsp+68h+arg_30], r15d
0x180074987  jz      short loc_1800749CC
0x180074989  mov     esi, 0C000000Dh
0x18007498e  mov     r9d, 70Fh
0x180074994  mov     ecx, 0C000000Dh
0x180074999  lea     rdx, aStatus; "Status"
0x1800749a0  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800749a7  call    DebugTraceError
0x1800749ac  mov     r14, [rsp+68h+arg_28]
0x1800749b4  test    r14, r14
0x1800749b7  jz      short loc_1800749BC
0x1800749b9  mov     [r14], r15d
0x1800749bc  mov     eax, esi
0x1800749be  add     rsp, 38h
0x1800749c2  pop     r15
0x1800749c4  pop     r14
0x1800749c6  pop     rdi
0x1800749c7  pop     rsi
0x1800749c8  pop     rbp
0x1800749c9  pop     rbx
0x1800749ca  retn
0x1800749cc  lea     rdx, [rsp+68h+var_48]
0x1800749d1  call    ValidateKeyDerivationKey
0x1800749d6  mov     esi, eax
0x1800749d8  test    eax, eax
0x1800749da  js      short loc_1800749AC
0x1800749dc  mov     rbp, [rsp+68h+var_48]
0x1800749e1  test    rbp, rbp
0x1800749e4  jnz     short loc_1800749F8
0x1800749e6  mov     esi, 0C0000008h
0x1800749eb  mov     r9d, 71Fh
0x1800749f1  mov     ecx, 0C0000008h
0x1800749f6  jmp     short loc_180074999
0x1800749f8  mov     r14, [rsp+68h+arg_28]
0x180074a00  test    r14, r14
0x180074a03  jnz     short loc_180074A2A
0x180074a05  mov     r9d, 726h
0x180074a0b  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180074a12  lea     rdx, aStatus; "Status"
0x180074a19  mov     ecx, 0C000000Dh
0x180074a1e  mov     esi, 0C000000Dh
0x180074a23  call    DebugTraceError
0x180074a28  jmp     short loc_1800749BC
0x180074a2a  test    rdi, rdi
0x180074a2d  jnz     short loc_180074A57
0x180074a2f  mov     esi, 0C000000Dh
0x180074a34  mov     r9d, 72Dh
0x180074a3a  mov     ecx, 0C000000Dh
0x180074a3f  lea     rdx, aStatus; "Status"
0x180074a46  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180074a4d  call    DebugTraceError
0x180074a52  jmp     loc_1800749B9
0x180074a57  lea     rdx, aKeydatablob; "KeyDataBlob"
0x180074a5e  mov     rcx, rdi; Str1
0x180074a61  call    wcscmp_0
0x180074a66  test    eax, eax
0x180074a68  jnz     loc_180074B0F
0x180074a6e  mov     r15d, [rbp+10h]
0x180074a72  add     r15d, 0Ch
0x180074a76  cmp     qword ptr [rbp+48h], 0
0x180074a7b  jz      short loc_180074A86
0x180074a7d  mov     eax, [rbp+40h]
0x180074a80  add     eax, 4
0x180074a83  add     r15d, eax
0x180074a86  test    rbx, rbx
0x180074a89  jnz     short loc_180074A92
0x180074a8b  xor     esi, esi
0x180074a8d  jmp     loc_1800749B9
0x180074a92  cmp     [rsp+68h+arg_20], r15d
0x180074a9a  jnb     short loc_180074AA6
0x180074a9c  mov     esi, 0C0000023h
0x180074aa1  jmp     loc_1800749B9
0x180074aa6  mov     dword ptr [rbx], 4D42444Bh
0x180074aac  lea     r9, [rbx+0Ch]
0x180074ab0  mov     dword ptr [rbx+4], 1
0x180074ab7  mov     ecx, [rbp+10h]
0x180074aba  mov     [rbx+8], ecx
0x180074abd  cmp     qword ptr [rbp+48h], 0
0x180074ac2  jz      short loc_180074AFA
0x180074ac4  lea     rdi, [rbp+40h]
0x180074ac8  add     ecx, 4
0x180074acb  add     ecx, [rdi]
0x180074acd  mov     r8d, 4
0x180074ad3  mov     [rbx+8], ecx
0x180074ad6  mov     rdx, rdi
0x180074ad9  mov     rcx, r9
0x180074adc  call    ReverseMemCopy
0x180074ae1  mov     r8d, [rdi]; Size
0x180074ae4  lea     rbx, [r9+4]
0x180074ae8  mov     rdx, [rbp+38h]; Src
0x180074aec  mov     rcx, rbx; void *
0x180074aef  call    memmove
0x180074af4  mov     r9d, [rdi]
0x180074af7  add     r9, rbx
0x180074afa  mov     r8d, [rbp+10h]; Size
0x180074afe  mov     rcx, r9; void *
0x180074b01  mov     rdx, [rbp+18h]; Src
0x180074b05  call    memmove
0x180074b0a  jmp     loc_1800749B9
0x180074b0f  mov     esi, 0C00000BBh
0x180074b14  mov     r9d, 760h
0x180074b1a  mov     ecx, 0C00000BBh
0x180074b1f  jmp     loc_180074A3F
```
