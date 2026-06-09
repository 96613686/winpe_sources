# MSCryptGetKeyData

- ea: `0x180017adc`
- end: `0x180017cc2`
- name: `MSCryptGetKeyData`
- size: `486`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800173a0`

## callees

- `0x180003f70`
- `0x180006470`
- `0x1800082b0`
- `0x180016d10`
- `0x180017adc`
- `0x18009d820`
- `0x18009da40`

## string_xrefs

- `0x180017bc7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x180017c2c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x180017c84`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`

## pseudocode

```c
__int64 __fastcall MSCryptGetKeyData(__int64 a1, void *a2, unsigned int a3)
{
  size_t v3; // r14
  unsigned int v6; // edi
  __int64 v7; // rbp
  _BYTE *v8; // rbx
  char *v9; // rsi
  int v10; // edx
  int v11; // edi
  int v12; // r8d
  __int64 v14; // rax
  int v15; // edx
  int v16; // r8d
  int v17; // edx
  _BYTE *i; // rax
  _DWORD v19[4]; // [rsp+40h] [rbp-A8h] BYREF
  char v20; // [rsp+50h] [rbp-98h] BYREF

  v3 = a3;
  v19[0] = 0;
  v6 = a3 + 12;
  v7 = a3 + 12;
  if ( a3 + 12 <= 0x4C )
  {
    v8 = 0;
    v9 = &v20;
LABEL_3:
    v11 = MSCryptExportKey(a1, 0, L"KeyDataBlob", v9, v6, v19, 0);
    if ( v11 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        v17 = *((_DWORD *)WPP_GLOBAL_Control + 11);
        if ( (v17 & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v17,
            v12,
            (unsigned int)"Status",
            v11,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\AesKeyWrap.c",
            94);
      }
    }
    else if ( (_DWORD)v3 == *((_DWORD *)v9 + 2) )
    {
      memmove(a2, v9 + 12, v3);
      v11 = 0;
    }
    else
    {
      v11 = -1073741811;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v10,
          v12,
          (unsigned int)"Status",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\AesKeyWrap.c",
          103);
    }
    if ( v8 )
    {
      for ( i = v8; v7; --v7 )
        *i++ = 0;
      MSCryptFree(v8);
    }
    return (unsigned int)v11;
  }
  v14 = MSCryptAlloc(v6, a2);
  v8 = (_BYTE *)v14;
  if ( v14 )
  {
    v9 = (char *)v14;
    goto LABEL_3;
  }
  v11 = -1073741801;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v15,
      v16,
      (unsigned int)"Status",
      23,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\AesKeyWrap.c",
      77);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180017adc  push    rbx
0x180017ade  push    rbp
0x180017adf  push    rsi
0x180017ae0  push    rdi
0x180017ae1  push    r12
0x180017ae3  push    r14
0x180017ae5  push    r15
0x180017ae7  sub     rsp, 0B0h
0x180017aee  mov     rax, cs:__security_cookie
0x180017af5  xor     rax, rsp
0x180017af8  mov     [rsp+0E8h+var_48], rax
0x180017b00  mov     r14d, r8d
0x180017b03  mov     r15, rdx
0x180017b06  mov     r12, rcx
0x180017b09  mov     [rsp+0E8h+var_A8], 0
0x180017b11  lea     edi, [r14+0Ch]
0x180017b15  mov     ebp, edi
0x180017b17  cmp     edi, 4Ch ; 'L'
0x180017b1a  ja      loc_180017BED
0x180017b20  xor     ebx, ebx
0x180017b22  lea     rsi, [rsp+0E8h+var_98]
0x180017b27  lea     rax, [rsp+0E8h+var_A8]
0x180017b2c  mov     [rsp+0E8h+var_B8], 0
0x180017b34  mov     [rsp+0E8h+var_C0], rax
0x180017b39  lea     r8, aKeydatablob; "KeyDataBlob"
0x180017b40  mov     r9, rsi
0x180017b43  mov     [rsp+0E8h+var_C8], edi
0x180017b47  xor     edx, edx
0x180017b49  mov     rcx, r12
0x180017b4c  call    MSCryptExportKey
0x180017b51  mov     edi, eax
0x180017b53  test    eax, eax
0x180017b55  js      loc_180017C59
0x180017b5b  cmp     r14d, [rsi+8]
0x180017b5f  jnz     short loc_180017BA0
0x180017b61  mov     r8, r14; Size
0x180017b64  lea     rdx, [rsi+0Ch]; Src
0x180017b68  mov     rcx, r15; void *
0x180017b6b  call    memmove
0x180017b70  xor     edi, edi
0x180017b72  test    rbx, rbx
0x180017b75  jnz     loc_180017C99
0x180017b7b  mov     eax, edi
0x180017b7d  mov     rcx, [rsp+0E8h+var_48]
0x180017b85  xor     rcx, rsp; StackCookie
0x180017b88  call    __security_check_cookie
0x180017b8d  add     rsp, 0B0h
0x180017b94  pop     r15
0x180017b96  pop     r14
0x180017b98  pop     r12
0x180017b9a  pop     rdi
0x180017b9b  pop     rsi
0x180017b9c  pop     rbp
0x180017b9d  pop     rbx
0x180017b9e  retn
0x180017ba0  mov     edi, 0C000000Dh
0x180017ba5  mov     rcx, cs:WPP_GLOBAL_Control
0x180017bac  lea     rax, WPP_GLOBAL_Control
0x180017bb3  cmp     rcx, rax
0x180017bb6  jz      short loc_180017B72
0x180017bb8  mov     eax, [rcx+2Ch]
0x180017bbb  test    al, 1
0x180017bbd  jz      short loc_180017B72
0x180017bbf  mov     [rsp+0E8h+var_B8], 67h ; 'g'
0x180017bc7  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180017bce  mov     [rsp+0E8h+var_C0], rax
0x180017bd3  mov     [rsp+0E8h+var_C8], 0C000000Dh
0x180017bdb  mov     rcx, [rcx+18h]
0x180017bdf  lea     r9, aStatus; "Status"
0x180017be6  call    WPP_SF_sDsd
0x180017beb  jmp     short loc_180017B72
0x180017bed  mov     rcx, rbp
0x180017bf0  call    MSCryptAlloc
0x180017bf5  mov     rbx, rax
0x180017bf8  test    rax, rax
0x180017bfb  jnz     loc_180017CBA
0x180017c01  mov     edi, 0C0000017h
0x180017c06  mov     rcx, cs:WPP_GLOBAL_Control
0x180017c0d  lea     rax, WPP_GLOBAL_Control
0x180017c14  cmp     rcx, rax
0x180017c17  jz      loc_180017B7B
0x180017c1d  mov     eax, [rcx+2Ch]
0x180017c20  test    al, 1
0x180017c22  jz      loc_180017B7B
0x180017c28  mov     rcx, [rcx+18h]
0x180017c2c  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180017c33  mov     [rsp+0E8h+var_B8], 4Dh ; 'M'
0x180017c3b  lea     r9, aStatus; "Status"
0x180017c42  mov     [rsp+0E8h+var_C0], rax
0x180017c47  mov     [rsp+0E8h+var_C8], 0C0000017h
0x180017c4f  call    WPP_SF_sDsd
0x180017c54  jmp     loc_180017B7B
0x180017c59  mov     rcx, cs:WPP_GLOBAL_Control
0x180017c60  lea     rax, WPP_GLOBAL_Control
0x180017c67  cmp     rcx, rax
0x180017c6a  jz      loc_180017B72
0x180017c70  mov     edx, [rcx+2Ch]
0x180017c73  test    dl, 1
0x180017c76  jz      loc_180017B72
0x180017c7c  mov     [rsp+0E8h+var_B8], 5Eh ; '^'
0x180017c84  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180017c8b  mov     [rsp+0E8h+var_C0], rax
0x180017c90  mov     [rsp+0E8h+var_C8], edi
0x180017c94  jmp     loc_180017BDB
0x180017c99  mov     rax, rbx
0x180017c9c  test    rbp, rbp
0x180017c9f  jz      short loc_180017CAD
0x180017ca1  mov     byte ptr [rax], 0
0x180017ca4  inc     rax
0x180017ca7  sub     rbp, 1
0x180017cab  jnz     short loc_180017CA1
0x180017cad  mov     rcx, rbx; P
0x180017cb0  call    MSCryptFree
0x180017cb5  jmp     loc_180017B7B
0x180017cba  mov     rsi, rax
0x180017cbd  jmp     loc_180017B27
```
