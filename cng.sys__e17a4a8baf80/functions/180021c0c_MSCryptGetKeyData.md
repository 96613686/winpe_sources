# MSCryptGetKeyData

- ea: `0x180021c0c`
- end: `0x180021df2`
- name: `MSCryptGetKeyData`
- size: `486`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180021480`

## callees

- `0x18000e090`
- `0x180010590`
- `0x1800123d0`
- `0x180020df0`
- `0x180021c0c`
- `0x1800a4260`
- `0x1800a45c0`

## string_xrefs

- `0x180021cf7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x180021d5c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x180021db4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`

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
0x180021c0c  push    rbx
0x180021c0e  push    rbp
0x180021c0f  push    rsi
0x180021c10  push    rdi
0x180021c11  push    r12
0x180021c13  push    r14
0x180021c15  push    r15
0x180021c17  sub     rsp, 0B0h
0x180021c1e  mov     rax, cs:__security_cookie
0x180021c25  xor     rax, rsp
0x180021c28  mov     [rsp+0E8h+var_48], rax
0x180021c30  mov     r14d, r8d
0x180021c33  mov     r15, rdx
0x180021c36  mov     r12, rcx
0x180021c39  mov     [rsp+0E8h+var_A8], 0
0x180021c41  lea     edi, [r14+0Ch]
0x180021c45  mov     ebp, edi
0x180021c47  cmp     edi, 4Ch ; 'L'
0x180021c4a  ja      loc_180021D1D
0x180021c50  xor     ebx, ebx
0x180021c52  lea     rsi, [rsp+0E8h+var_98]
0x180021c57  lea     rax, [rsp+0E8h+var_A8]
0x180021c5c  mov     [rsp+0E8h+var_B8], 0
0x180021c64  mov     [rsp+0E8h+var_C0], rax
0x180021c69  lea     r8, aKeydatablob; "KeyDataBlob"
0x180021c70  mov     r9, rsi
0x180021c73  mov     [rsp+0E8h+var_C8], edi
0x180021c77  xor     edx, edx
0x180021c79  mov     rcx, r12
0x180021c7c  call    MSCryptExportKey
0x180021c81  mov     edi, eax
0x180021c83  test    eax, eax
0x180021c85  js      loc_180021D89
0x180021c8b  cmp     r14d, [rsi+8]
0x180021c8f  jnz     short loc_180021CD0
0x180021c91  mov     r8, r14; Size
0x180021c94  lea     rdx, [rsi+0Ch]; Src
0x180021c98  mov     rcx, r15; void *
0x180021c9b  call    memmove
0x180021ca0  xor     edi, edi
0x180021ca2  test    rbx, rbx
0x180021ca5  jnz     loc_180021DC9
0x180021cab  mov     eax, edi
0x180021cad  mov     rcx, [rsp+0E8h+var_48]
0x180021cb5  xor     rcx, rsp; StackCookie
0x180021cb8  call    __security_check_cookie
0x180021cbd  add     rsp, 0B0h
0x180021cc4  pop     r15
0x180021cc6  pop     r14
0x180021cc8  pop     r12
0x180021cca  pop     rdi
0x180021ccb  pop     rsi
0x180021ccc  pop     rbp
0x180021ccd  pop     rbx
0x180021cce  retn
0x180021cd0  mov     edi, 0C000000Dh
0x180021cd5  mov     rcx, cs:WPP_GLOBAL_Control
0x180021cdc  lea     rax, WPP_GLOBAL_Control
0x180021ce3  cmp     rcx, rax
0x180021ce6  jz      short loc_180021CA2
0x180021ce8  mov     eax, [rcx+2Ch]
0x180021ceb  test    al, 1
0x180021ced  jz      short loc_180021CA2
0x180021cef  mov     [rsp+0E8h+var_B8], 67h ; 'g'
0x180021cf7  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021cfe  mov     [rsp+0E8h+var_C0], rax
0x180021d03  mov     [rsp+0E8h+var_C8], 0C000000Dh
0x180021d0b  mov     rcx, [rcx+18h]
0x180021d0f  lea     r9, aStatus; "Status"
0x180021d16  call    WPP_SF_sDsd
0x180021d1b  jmp     short loc_180021CA2
0x180021d1d  mov     rcx, rbp
0x180021d20  call    MSCryptAlloc
0x180021d25  mov     rbx, rax
0x180021d28  test    rax, rax
0x180021d2b  jnz     loc_180021DEA
0x180021d31  mov     edi, 0C0000017h
0x180021d36  mov     rcx, cs:WPP_GLOBAL_Control
0x180021d3d  lea     rax, WPP_GLOBAL_Control
0x180021d44  cmp     rcx, rax
0x180021d47  jz      loc_180021CAB
0x180021d4d  mov     eax, [rcx+2Ch]
0x180021d50  test    al, 1
0x180021d52  jz      loc_180021CAB
0x180021d58  mov     rcx, [rcx+18h]
0x180021d5c  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021d63  mov     [rsp+0E8h+var_B8], 4Dh ; 'M'
0x180021d6b  lea     r9, aStatus; "Status"
0x180021d72  mov     [rsp+0E8h+var_C0], rax
0x180021d77  mov     [rsp+0E8h+var_C8], 0C0000017h
0x180021d7f  call    WPP_SF_sDsd
0x180021d84  jmp     loc_180021CAB
0x180021d89  mov     rcx, cs:WPP_GLOBAL_Control
0x180021d90  lea     rax, WPP_GLOBAL_Control
0x180021d97  cmp     rcx, rax
0x180021d9a  jz      loc_180021CA2
0x180021da0  mov     edx, [rcx+2Ch]
0x180021da3  test    dl, 1
0x180021da6  jz      loc_180021CA2
0x180021dac  mov     [rsp+0E8h+var_B8], 5Eh ; '^'
0x180021db4  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021dbb  mov     [rsp+0E8h+var_C0], rax
0x180021dc0  mov     [rsp+0E8h+var_C8], edi
0x180021dc4  jmp     loc_180021D0B
0x180021dc9  mov     rax, rbx
0x180021dcc  test    rbp, rbp
0x180021dcf  jz      short loc_180021DDD
0x180021dd1  mov     byte ptr [rax], 0
0x180021dd4  inc     rax
0x180021dd7  sub     rbp, 1
0x180021ddb  jnz     short loc_180021DD1
0x180021ddd  mov     rcx, rbx; P
0x180021de0  call    MSCryptFree
0x180021de5  jmp     loc_180021CAB
0x180021dea  mov     rsi, rax
0x180021ded  jmp     loc_180021C57
```
