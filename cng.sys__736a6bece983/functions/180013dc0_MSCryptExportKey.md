# MSCryptExportKey

- ea: `0x180013dc0`
- end: `0x18001403f`
- name: `MSCryptExportKey`
- size: `639`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180013c40`
- `0x180014b8c`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x1800136f0`
- `0x180013dc0`
- `0x180014050`
- `0x180014450`
- `0x18009f616`
- `0x18009f780`

## string_xrefs

- `0x180013e7e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180013fa3`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180013fd6`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180013ffe`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x1800a164c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`

## pseudocode

```c
__int64 __fastcall MSCryptExportKey(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        _DWORD *a4,
        unsigned int a5,
        _DWORD *a6,
        int a7)
{
  int v11; // edx
  __int64 v12; // rdi
  _DWORD *v13; // rsi
  unsigned int v14; // eax
  unsigned int v15; // ebx
  int v17; // eax
  __int64 v18; // r9
  __int64 v19; // rcx
  unsigned int v20[18]; // [rsp+40h] [rbp-48h] BYREF

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
        v17 = MSCryptAesKeyWrap(a1, a2, a4, a5, v20);
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
0x180013dc0  push    rbx
0x180013dc2  push    rbp
0x180013dc3  push    rsi
0x180013dc4  push    rdi
0x180013dc5  push    r14
0x180013dc7  push    r15
0x180013dc9  sub     rsp, 58h
0x180013dcd  cmp     [rsp+88h+arg_30], 0
0x180013dd5  mov     r14, r9
0x180013dd8  mov     rbx, r8
0x180013ddb  mov     [rsp+88h+var_48], 0
0x180013de3  mov     r15, rdx
0x180013de6  mov     rbp, rcx
0x180013de9  jnz     short loc_180013E5B
0x180013deb  call    validateMSCryptSymmKey
0x180013df0  mov     rdi, rax
0x180013df3  test    rax, rax
0x180013df6  jz      loc_180013FD0
0x180013dfc  mov     rsi, [rsp+88h+arg_28]
0x180013e04  test    rsi, rsi
0x180013e07  jz      loc_180013FF8
0x180013e0d  test    rbx, rbx
0x180013e10  jz      loc_180013F78
0x180013e16  lea     rdx, aOpaquekeyblob; "OpaqueKeyBlob"
0x180013e1d  mov     rcx, rbx; Str1
0x180013e20  call    wcscmp_0
0x180013e25  test    eax, eax
0x180013e27  jz      loc_180013F4E
0x180013e2d  lea     rdx, aKeydatablob; "KeyDataBlob"
0x180013e34  mov     rcx, rbx; Str1
0x180013e37  call    wcscmp_0
0x180013e3c  test    eax, eax
0x180013e3e  jnz     loc_180013EC9
0x180013e44  mov     eax, [rdi+38h]
0x180013e47  add     eax, 0Ch
0x180013e4a  mov     [rsp+88h+var_48], eax
0x180013e4e  test    r14, r14
0x180013e51  jnz     loc_180013F13
0x180013e57  xor     ebx, ebx
0x180013e59  jmp     short loc_180013EB3
0x180013e5b  mov     ebx, 0C000000Dh
0x180013e60  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e67  lea     rax, WPP_GLOBAL_Control
0x180013e6e  cmp     rcx, rax
0x180013e71  jz      short loc_180013EA6
0x180013e73  mov     eax, [rcx+2Ch]
0x180013e76  test    al, 1
0x180013e78  jz      short loc_180013EA6
0x180013e7a  mov     rcx, [rcx+18h]
0x180013e7e  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180013e85  mov     [rsp+88h+var_58], 511h
0x180013e8d  lea     r9, aStatus; "Status"
0x180013e94  mov     [rsp+88h+var_60], r8
0x180013e99  mov     dword ptr [rsp+88h+var_68], 0C000000Dh
0x180013ea1  call    WPP_SF_sDsd
0x180013ea6  mov     rsi, [rsp+88h+arg_28]
0x180013eae  test    rsi, rsi
0x180013eb1  jz      short loc_180013EB9
0x180013eb3  mov     eax, [rsp+88h+var_48]
0x180013eb7  mov     [rsi], eax
0x180013eb9  mov     eax, ebx
0x180013ebb  add     rsp, 58h
0x180013ebf  pop     r15
0x180013ec1  pop     r14
0x180013ec3  pop     rdi
0x180013ec4  pop     rsi
0x180013ec5  pop     rbp
0x180013ec6  pop     rbx
0x180013ec7  retn
0x180013ec9  lea     rdx, aRfc3565keywrap; "Rfc3565KeyWrapBlob"
0x180013ed0  mov     rcx, rbx; Str1
0x180013ed3  call    wcscmp_0
0x180013ed8  test    eax, eax
0x180013eda  jnz     loc_18001402A
0x180013ee0  mov     r9d, [rsp+88h+arg_20]
0x180013ee8  lea     rax, [rsp+88h+var_48]
0x180013eed  mov     r8, r14
0x180013ef0  mov     [rsp+88h+var_68], rax
0x180013ef5  mov     rdx, r15
0x180013ef8  mov     rcx, rbp
0x180013efb  call    MSCryptAesKeyWrap
0x180013f00  mov     ebx, eax
0x180013f02  test    eax, eax
0x180013f04  jns     short loc_180013EB3
0x180013f06  mov     r9d, 55Bh
0x180013f0c  mov     ecx, eax
0x180013f0e  jmp     loc_1800A164C
0x180013f13  cmp     [rsp+88h+arg_20], eax
0x180013f1a  jb      loc_180014020
0x180013f20  mov     dword ptr [r14], 4D42444Bh
0x180013f27  lea     rdx, [rdi+3Ch]; Src
0x180013f2b  mov     dword ptr [r14+4], 1
0x180013f33  lea     rcx, [r14+0Ch]; void *
0x180013f37  mov     eax, [rdi+38h]
0x180013f3a  xor     ebx, ebx
0x180013f3c  mov     [r14+8], eax
0x180013f40  mov     r8d, [rdi+38h]; Size
0x180013f44  call    memmove
0x180013f49  jmp     loc_180013EB3
0x180013f4e  mov     r8d, [rsp+88h+arg_20]
0x180013f56  lea     r9, [rsp+88h+var_48]
0x180013f5b  mov     rdx, r14
0x180013f5e  mov     rcx, rdi
0x180013f61  call    MSCryptExportKeyOpaque
0x180013f66  mov     ebx, eax
0x180013f68  test    eax, eax
0x180013f6a  jns     loc_180013EB3
0x180013f70  mov     r9d, 531h
0x180013f76  jmp     short loc_180013F0C
0x180013f78  mov     ebx, 0C000000Dh
0x180013f7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f84  lea     rax, WPP_GLOBAL_Control
0x180013f8b  cmp     rcx, rax
0x180013f8e  jz      loc_180013EB3
0x180013f94  mov     eax, [rcx+2Ch]
0x180013f97  test    al, 1
0x180013f99  jz      loc_180013EB3
0x180013f9f  mov     rcx, [rcx+18h]
0x180013fa3  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180013faa  mov     [rsp+88h+var_58], 528h
0x180013fb2  lea     r9, aStatus; "Status"
0x180013fb9  mov     [rsp+88h+var_60], r8
0x180013fbe  mov     dword ptr [rsp+88h+var_68], 0C000000Dh
0x180013fc6  call    WPP_SF_sDsd
0x180013fcb  jmp     loc_180013EB3
0x180013fd0  mov     r9d, 51Ah
0x180013fd6  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180013fdd  lea     rdx, aStatus; "Status"
0x180013fe4  mov     ecx, 0C0000008h
0x180013fe9  mov     ebx, 0C0000008h
0x180013fee  call    DebugTraceError
0x180013ff3  jmp     loc_180013EA6
0x180013ff8  mov     r9d, 521h
0x180013ffe  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180014005  lea     rdx, aStatus; "Status"
0x18001400c  mov     ecx, 0C000000Dh
0x180014011  mov     ebx, 0C000000Dh
0x180014016  call    DebugTraceError
0x18001401b  jmp     loc_180013EB9
0x180014020  mov     ebx, 0C0000023h
0x180014025  jmp     loc_180013EB3
0x18001402a  mov     ebx, 0C00000BBh
0x18001402f  mov     r9d, 562h
0x180014035  mov     ecx, 0C00000BBh
0x18001403a  jmp     loc_1800A164C
0x1800a164c  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a1653  lea     rdx, aStatus; "Status"
0x1800a165a  call    DebugTraceError
0x1800a165f  nop
0x1800a1660  jmp     loc_180013EB3
```
