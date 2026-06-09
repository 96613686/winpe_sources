# MSCryptExportKey

- ea: `0x180016d10`
- end: `0x180016f8f`
- name: `MSCryptExportKey`
- size: `639`
- prototype: `__int64 __fastcall(int, int, const wchar_t *, _DWORD *, unsigned int, _DWORD *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180016b90`
- `0x180017adc`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x180016638`
- `0x180016d10`
- `0x180016fa0`
- `0x1800173a0`
- `0x18009d746`
- `0x18009da40`

## string_xrefs

- `0x180016dce`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180016ef3`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180016f26`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180016f4e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18009fa96`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`

## pseudocode

```c
__int64 __fastcall MSCryptExportKey(int a1, int a2, const wchar_t *a3, _DWORD *a4, unsigned int a5, _DWORD *a6, int a7)
{
  int v11; // edx
  __int64 v12; // rdi
  _DWORD *v13; // rsi
  unsigned int v14; // eax
  unsigned int v15; // ebx
  int v17; // eax
  __int64 v18; // r9
  __int64 v19; // rcx
  _DWORD v20[18]; // [rsp+40h] [rbp-48h] BYREF

  v20[0] = 0;
  if ( a7 )
  {
    v15 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
        17);
  }
  else
  {
    v12 = validateMSCryptSymmKey();
    if ( v12 )
    {
      v13 = a6;
      if ( !a6 )
      {
        v15 = -1073741811;
        DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c", 1313);
        return v15;
      }
      if ( !a3 )
      {
        v15 = -1073741811;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v11,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
            (unsigned int)"Status",
            13,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
            40);
        goto LABEL_13;
      }
      if ( !wcscmp_0(a3, L"OpaqueKeyBlob") )
      {
        v17 = MSCryptExportKeyOpaque(v12, a4, a5, v20);
        v15 = v17;
        if ( v17 < 0 )
        {
          v18 = 1329;
          goto LABEL_18;
        }
      }
      else
      {
        if ( !wcscmp_0(a3, L"KeyDataBlob") )
        {
          v14 = *(_DWORD *)(v12 + 56) + 12;
          v20[0] = v14;
          if ( a4 )
          {
            if ( a5 < v14 )
            {
              v15 = -1073741789;
            }
            else
            {
              *a4 = 1296188491;
              a4[1] = 1;
              v15 = 0;
              a4[2] = *(_DWORD *)(v12 + 56);
              memmove(a4 + 3, (const void *)(v12 + 60), *(unsigned int *)(v12 + 56));
            }
          }
          else
          {
            v15 = 0;
          }
          goto LABEL_13;
        }
        if ( wcscmp_0(a3, L"Rfc3565KeyWrapBlob") )
        {
          v15 = -1073741637;
          v18 = 1378;
          v19 = 3221225659LL;
          goto LABEL_30;
        }
        v17 = MSCryptAesKeyWrap(a1, a2, (_DWORD)a4, a5, (__int64)v20);
        v15 = v17;
        if ( v17 < 0 )
        {
          v18 = 1371;
LABEL_18:
          v19 = (unsigned int)v17;
LABEL_30:
          DebugTraceError(v19, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c", v18);
        }
      }
LABEL_13:
      *v13 = v20[0];
      return v15;
    }
    v15 = -1073741816;
    DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c", 1306);
  }
  v13 = a6;
  if ( a6 )
    goto LABEL_13;
  return v15;
}

```

## disassembly

```asm
0x180016d10  push    rbx
0x180016d12  push    rbp
0x180016d13  push    rsi
0x180016d14  push    rdi
0x180016d15  push    r14
0x180016d17  push    r15
0x180016d19  sub     rsp, 58h
0x180016d1d  cmp     [rsp+88h+arg_30], 0
0x180016d25  mov     r14, r9
0x180016d28  mov     rbx, r8
0x180016d2b  mov     [rsp+88h+var_48], 0
0x180016d33  mov     r15, rdx
0x180016d36  mov     rbp, rcx
0x180016d39  jnz     short loc_180016DAB
0x180016d3b  call    validateMSCryptSymmKey
0x180016d40  mov     rdi, rax
0x180016d43  test    rax, rax
0x180016d46  jz      loc_180016F20
0x180016d4c  mov     rsi, [rsp+88h+arg_28]
0x180016d54  test    rsi, rsi
0x180016d57  jz      loc_180016F48
0x180016d5d  test    rbx, rbx
0x180016d60  jz      loc_180016EC8
0x180016d66  lea     rdx, aOpaquekeyblob; "OpaqueKeyBlob"
0x180016d6d  mov     rcx, rbx; Str1
0x180016d70  call    wcscmp_0
0x180016d75  test    eax, eax
0x180016d77  jz      loc_180016E9E
0x180016d7d  lea     rdx, aKeydatablob; "KeyDataBlob"
0x180016d84  mov     rcx, rbx; Str1
0x180016d87  call    wcscmp_0
0x180016d8c  test    eax, eax
0x180016d8e  jnz     loc_180016E19
0x180016d94  mov     eax, [rdi+38h]
0x180016d97  add     eax, 0Ch
0x180016d9a  mov     [rsp+88h+var_48], eax
0x180016d9e  test    r14, r14
0x180016da1  jnz     loc_180016E63
0x180016da7  xor     ebx, ebx
0x180016da9  jmp     short loc_180016E03
0x180016dab  mov     ebx, 0C000000Dh
0x180016db0  mov     rcx, cs:WPP_GLOBAL_Control
0x180016db7  lea     rax, WPP_GLOBAL_Control
0x180016dbe  cmp     rcx, rax
0x180016dc1  jz      short loc_180016DF6
0x180016dc3  mov     eax, [rcx+2Ch]
0x180016dc6  test    al, 1
0x180016dc8  jz      short loc_180016DF6
0x180016dca  mov     rcx, [rcx+18h]
0x180016dce  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180016dd5  mov     [rsp+88h+var_58], 511h
0x180016ddd  lea     r9, aStatus; "Status"
0x180016de4  mov     [rsp+88h+var_60], r8
0x180016de9  mov     dword ptr [rsp+88h+var_68], 0C000000Dh
0x180016df1  call    WPP_SF_sDsd
0x180016df6  mov     rsi, [rsp+88h+arg_28]
0x180016dfe  test    rsi, rsi
0x180016e01  jz      short loc_180016E09
0x180016e03  mov     eax, [rsp+88h+var_48]
0x180016e07  mov     [rsi], eax
0x180016e09  mov     eax, ebx
0x180016e0b  add     rsp, 58h
0x180016e0f  pop     r15
0x180016e11  pop     r14
0x180016e13  pop     rdi
0x180016e14  pop     rsi
0x180016e15  pop     rbp
0x180016e16  pop     rbx
0x180016e17  retn
0x180016e19  lea     rdx, aRfc3565keywrap; "Rfc3565KeyWrapBlob"
0x180016e20  mov     rcx, rbx; Str1
0x180016e23  call    wcscmp_0
0x180016e28  test    eax, eax
0x180016e2a  jnz     loc_180016F7A
0x180016e30  mov     r9d, [rsp+88h+arg_20]
0x180016e38  lea     rax, [rsp+88h+var_48]
0x180016e3d  mov     r8, r14
0x180016e40  mov     [rsp+88h+var_68], rax
0x180016e45  mov     rdx, r15
0x180016e48  mov     rcx, rbp
0x180016e4b  call    MSCryptAesKeyWrap
0x180016e50  mov     ebx, eax
0x180016e52  test    eax, eax
0x180016e54  jns     short loc_180016E03
0x180016e56  mov     r9d, 55Bh
0x180016e5c  mov     ecx, eax
0x180016e5e  jmp     loc_18009FA96
0x180016e63  cmp     [rsp+88h+arg_20], eax
0x180016e6a  jb      loc_180016F70
0x180016e70  mov     dword ptr [r14], 4D42444Bh
0x180016e77  lea     rdx, [rdi+3Ch]; Src
0x180016e7b  mov     dword ptr [r14+4], 1
0x180016e83  lea     rcx, [r14+0Ch]; void *
0x180016e87  mov     eax, [rdi+38h]
0x180016e8a  xor     ebx, ebx
0x180016e8c  mov     [r14+8], eax
0x180016e90  mov     r8d, [rdi+38h]; Size
0x180016e94  call    memmove
0x180016e99  jmp     loc_180016E03
0x180016e9e  mov     r8d, [rsp+88h+arg_20]
0x180016ea6  lea     r9, [rsp+88h+var_48]
0x180016eab  mov     rdx, r14
0x180016eae  mov     rcx, rdi
0x180016eb1  call    MSCryptExportKeyOpaque
0x180016eb6  mov     ebx, eax
0x180016eb8  test    eax, eax
0x180016eba  jns     loc_180016E03
0x180016ec0  mov     r9d, 531h
0x180016ec6  jmp     short loc_180016E5C
0x180016ec8  mov     ebx, 0C000000Dh
0x180016ecd  mov     rcx, cs:WPP_GLOBAL_Control
0x180016ed4  lea     rax, WPP_GLOBAL_Control
0x180016edb  cmp     rcx, rax
0x180016ede  jz      loc_180016E03
0x180016ee4  mov     eax, [rcx+2Ch]
0x180016ee7  test    al, 1
0x180016ee9  jz      loc_180016E03
0x180016eef  mov     rcx, [rcx+18h]
0x180016ef3  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180016efa  mov     [rsp+88h+var_58], 528h
0x180016f02  lea     r9, aStatus; "Status"
0x180016f09  mov     [rsp+88h+var_60], r8
0x180016f0e  mov     dword ptr [rsp+88h+var_68], 0C000000Dh
0x180016f16  call    WPP_SF_sDsd
0x180016f1b  jmp     loc_180016E03
0x180016f20  mov     r9d, 51Ah
0x180016f26  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180016f2d  lea     rdx, aStatus; "Status"
0x180016f34  mov     ecx, 0C0000008h
0x180016f39  mov     ebx, 0C0000008h
0x180016f3e  call    DebugTraceError
0x180016f43  jmp     loc_180016DF6
0x180016f48  mov     r9d, 521h
0x180016f4e  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180016f55  lea     rdx, aStatus; "Status"
0x180016f5c  mov     ecx, 0C000000Dh
0x180016f61  mov     ebx, 0C000000Dh
0x180016f66  call    DebugTraceError
0x180016f6b  jmp     loc_180016E09
0x180016f70  mov     ebx, 0C0000023h
0x180016f75  jmp     loc_180016E03
0x180016f7a  mov     ebx, 0C00000BBh
0x180016f7f  mov     r9d, 562h
0x180016f85  mov     ecx, 0C00000BBh
0x180016f8a  jmp     loc_18009FA96
0x18009fa96  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18009fa9d  lea     rdx, aStatus; "Status"
0x18009faa4  call    DebugTraceError
0x18009faa9  nop
0x18009faaa  jmp     loc_180016E03
```
