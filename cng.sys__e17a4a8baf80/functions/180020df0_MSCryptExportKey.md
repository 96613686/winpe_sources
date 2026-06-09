# MSCryptExportKey

- ea: `0x180020df0`
- end: `0x18002106f`
- name: `MSCryptExportKey`
- size: `639`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180020c70`
- `0x180021c0c`

## callees

- `0x18001155c`
- `0x1800123d0`
- `0x180020718`
- `0x180020df0`
- `0x180021080`
- `0x180021480`
- `0x1800a4232`
- `0x1800a45c0`

## string_xrefs

- `0x180020eae`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180020fd3`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180021006`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18002102e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x1800a6834`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`

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
        18);
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
        DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c", 1314);
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
            41);
        goto LABEL_13;
      }
      if ( !wcscmp_0(a3, L"OpaqueKeyBlob") )
      {
        v17 = MSCryptExportKeyOpaque(v12, a4, a5, v20);
        v15 = v17;
        if ( v17 < 0 )
        {
          v18 = 1330;
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
          v18 = 1379;
          v19 = 3221225659LL;
          goto LABEL_30;
        }
        v17 = MSCryptAesKeyWrap(a1, a2, a4, a5, v20);
        v15 = v17;
        if ( v17 < 0 )
        {
          v18 = 1372;
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
    DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c", 1307);
  }
  v13 = a6;
  if ( a6 )
    goto LABEL_13;
  return v15;
}

```

## disassembly

```asm
0x180020df0  push    rbx
0x180020df2  push    rbp
0x180020df3  push    rsi
0x180020df4  push    rdi
0x180020df5  push    r14
0x180020df7  push    r15
0x180020df9  sub     rsp, 58h
0x180020dfd  cmp     [rsp+88h+arg_30], 0
0x180020e05  mov     r14, r9
0x180020e08  mov     rbx, r8
0x180020e0b  mov     [rsp+88h+var_48], 0
0x180020e13  mov     r15, rdx
0x180020e16  mov     rbp, rcx
0x180020e19  jnz     short loc_180020E8B
0x180020e1b  call    validateMSCryptSymmKey
0x180020e20  mov     rdi, rax
0x180020e23  test    rax, rax
0x180020e26  jz      loc_180021000
0x180020e2c  mov     rsi, [rsp+88h+arg_28]
0x180020e34  test    rsi, rsi
0x180020e37  jz      loc_180021028
0x180020e3d  test    rbx, rbx
0x180020e40  jz      loc_180020FA8
0x180020e46  lea     rdx, aOpaquekeyblob; "OpaqueKeyBlob"
0x180020e4d  mov     rcx, rbx; Str1
0x180020e50  call    wcscmp_0
0x180020e55  test    eax, eax
0x180020e57  jz      loc_180020F7E
0x180020e5d  lea     rdx, aKeydatablob; "KeyDataBlob"
0x180020e64  mov     rcx, rbx; Str1
0x180020e67  call    wcscmp_0
0x180020e6c  test    eax, eax
0x180020e6e  jnz     loc_180020EF9
0x180020e74  mov     eax, [rdi+38h]
0x180020e77  add     eax, 0Ch
0x180020e7a  mov     [rsp+88h+var_48], eax
0x180020e7e  test    r14, r14
0x180020e81  jnz     loc_180020F43
0x180020e87  xor     ebx, ebx
0x180020e89  jmp     short loc_180020EE3
0x180020e8b  mov     ebx, 0C000000Dh
0x180020e90  mov     rcx, cs:WPP_GLOBAL_Control
0x180020e97  lea     rax, WPP_GLOBAL_Control
0x180020e9e  cmp     rcx, rax
0x180020ea1  jz      short loc_180020ED6
0x180020ea3  mov     eax, [rcx+2Ch]
0x180020ea6  test    al, 1
0x180020ea8  jz      short loc_180020ED6
0x180020eaa  mov     rcx, [rcx+18h]
0x180020eae  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180020eb5  mov     [rsp+88h+var_58], 512h
0x180020ebd  lea     r9, aStatus; "Status"
0x180020ec4  mov     [rsp+88h+var_60], r8
0x180020ec9  mov     dword ptr [rsp+88h+var_68], 0C000000Dh
0x180020ed1  call    WPP_SF_sDsd
0x180020ed6  mov     rsi, [rsp+88h+arg_28]
0x180020ede  test    rsi, rsi
0x180020ee1  jz      short loc_180020EE9
0x180020ee3  mov     eax, [rsp+88h+var_48]
0x180020ee7  mov     [rsi], eax
0x180020ee9  mov     eax, ebx
0x180020eeb  add     rsp, 58h
0x180020eef  pop     r15
0x180020ef1  pop     r14
0x180020ef3  pop     rdi
0x180020ef4  pop     rsi
0x180020ef5  pop     rbp
0x180020ef6  pop     rbx
0x180020ef7  retn
0x180020ef9  lea     rdx, aRfc3565keywrap; "Rfc3565KeyWrapBlob"
0x180020f00  mov     rcx, rbx; Str1
0x180020f03  call    wcscmp_0
0x180020f08  test    eax, eax
0x180020f0a  jnz     loc_18002105A
0x180020f10  mov     r9d, [rsp+88h+arg_20]
0x180020f18  lea     rax, [rsp+88h+var_48]
0x180020f1d  mov     r8, r14
0x180020f20  mov     [rsp+88h+var_68], rax
0x180020f25  mov     rdx, r15
0x180020f28  mov     rcx, rbp
0x180020f2b  call    MSCryptAesKeyWrap
0x180020f30  mov     ebx, eax
0x180020f32  test    eax, eax
0x180020f34  jns     short loc_180020EE3
0x180020f36  mov     r9d, 55Ch
0x180020f3c  mov     ecx, eax
0x180020f3e  jmp     loc_1800A6834
0x180020f43  cmp     [rsp+88h+arg_20], eax
0x180020f4a  jb      loc_180021050
0x180020f50  mov     dword ptr [r14], 4D42444Bh
0x180020f57  lea     rdx, [rdi+3Ch]; Src
0x180020f5b  mov     dword ptr [r14+4], 1
0x180020f63  lea     rcx, [r14+0Ch]; void *
0x180020f67  mov     eax, [rdi+38h]
0x180020f6a  xor     ebx, ebx
0x180020f6c  mov     [r14+8], eax
0x180020f70  mov     r8d, [rdi+38h]; Size
0x180020f74  call    memmove
0x180020f79  jmp     loc_180020EE3
0x180020f7e  mov     r8d, [rsp+88h+arg_20]
0x180020f86  lea     r9, [rsp+88h+var_48]
0x180020f8b  mov     rdx, r14
0x180020f8e  mov     rcx, rdi
0x180020f91  call    MSCryptExportKeyOpaque
0x180020f96  mov     ebx, eax
0x180020f98  test    eax, eax
0x180020f9a  jns     loc_180020EE3
0x180020fa0  mov     r9d, 532h
0x180020fa6  jmp     short loc_180020F3C
0x180020fa8  mov     ebx, 0C000000Dh
0x180020fad  mov     rcx, cs:WPP_GLOBAL_Control
0x180020fb4  lea     rax, WPP_GLOBAL_Control
0x180020fbb  cmp     rcx, rax
0x180020fbe  jz      loc_180020EE3
0x180020fc4  mov     eax, [rcx+2Ch]
0x180020fc7  test    al, 1
0x180020fc9  jz      loc_180020EE3
0x180020fcf  mov     rcx, [rcx+18h]
0x180020fd3  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180020fda  mov     [rsp+88h+var_58], 529h
0x180020fe2  lea     r9, aStatus; "Status"
0x180020fe9  mov     [rsp+88h+var_60], r8
0x180020fee  mov     dword ptr [rsp+88h+var_68], 0C000000Dh
0x180020ff6  call    WPP_SF_sDsd
0x180020ffb  jmp     loc_180020EE3
0x180021000  mov     r9d, 51Bh
0x180021006  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002100d  lea     rdx, aStatus; "Status"
0x180021014  mov     ecx, 0C0000008h
0x180021019  mov     ebx, 0C0000008h
0x18002101e  call    DebugTraceError
0x180021023  jmp     loc_180020ED6
0x180021028  mov     r9d, 522h
0x18002102e  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021035  lea     rdx, aStatus; "Status"
0x18002103c  mov     ecx, 0C000000Dh
0x180021041  mov     ebx, 0C000000Dh
0x180021046  call    DebugTraceError
0x18002104b  jmp     loc_180020EE9
0x180021050  mov     ebx, 0C0000023h
0x180021055  jmp     loc_180020EE3
0x18002105a  mov     ebx, 0C00000BBh
0x18002105f  mov     r9d, 563h
0x180021065  mov     ecx, 0C00000BBh
0x18002106a  jmp     loc_1800A6834
0x1800a6834  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a683b  lea     rdx, aStatus; "Status"
0x1800a6842  call    DebugTraceError
0x1800a6847  nop
0x1800a6848  jmp     loc_180020EE3
```
