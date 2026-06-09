# MSCryptGetKeyData

- ea: `0x180014b8c`
- end: `0x180014d72`
- name: `MSCryptGetKeyData`
- size: `486`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180014450`

## callees

- `0x180003f70`
- `0x180006470`
- `0x1800082b0`
- `0x180013dc0`
- `0x180014b8c`
- `0x18009f650`
- `0x18009f780`

## string_xrefs

- `0x180014c77`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x180014cdc`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x180014d34`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`

## pseudocode

```c
__int64 __fastcall MSCryptGetKeyData(__int64 a1, void *a2, __int64 a3, __int64 a4)
{
  size_t v4; // r14
  unsigned int v7; // edi
  __int64 v8; // rbp
  _BYTE *v9; // rbx
  char *v10; // rsi
  int v11; // edx
  int v12; // edi
  int v13; // r8d
  __int64 v15; // rax
  int v16; // edx
  int v17; // r8d
  int v18; // edx
  _BYTE *i; // rax
  _DWORD v20[4]; // [rsp+40h] [rbp-A8h] BYREF
  char v21; // [rsp+50h] [rbp-98h] BYREF

  v4 = (unsigned int)a3;
  v20[0] = 0;
  v7 = a3 + 12;
  v8 = (unsigned int)(a3 + 12);
  if ( (unsigned int)(a3 + 12) <= 0x4C )
  {
    v9 = 0;
    v10 = &v21;
LABEL_3:
    v12 = MSCryptExportKey(a1, 0, L"KeyDataBlob", v10, v7, v20, 0);
    if ( v12 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        v18 = *((_DWORD *)WPP_GLOBAL_Control + 11);
        if ( (v18 & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v18,
            v13,
            (unsigned int)"Status",
            v12,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\AesKeyWrap.c",
            94);
      }
    }
    else if ( (_DWORD)v4 == *((_DWORD *)v10 + 2) )
    {
      memmove(a2, v10 + 12, v4);
      v12 = 0;
    }
    else
    {
      v12 = -1073741811;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v11,
          v13,
          (unsigned int)"Status",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\AesKeyWrap.c",
          103);
    }
    if ( v9 )
    {
      for ( i = v9; v8; --v8 )
        *i++ = 0;
      MSCryptFree(v9);
    }
    return (unsigned int)v12;
  }
  v15 = MSCryptAlloc(v7, a2, a3, a4);
  v9 = (_BYTE *)v15;
  if ( v15 )
  {
    v10 = (char *)v15;
    goto LABEL_3;
  }
  v12 = -1073741801;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v16,
      v17,
      (unsigned int)"Status",
      23,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\AesKeyWrap.c",
      77);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180014b8c  push    rbx
0x180014b8e  push    rbp
0x180014b8f  push    rsi
0x180014b90  push    rdi
0x180014b91  push    r12
0x180014b93  push    r14
0x180014b95  push    r15
0x180014b97  sub     rsp, 0B0h
0x180014b9e  mov     rax, cs:__security_cookie
0x180014ba5  xor     rax, rsp
0x180014ba8  mov     [rsp+0E8h+var_48], rax
0x180014bb0  mov     r14d, r8d
0x180014bb3  mov     r15, rdx
0x180014bb6  mov     r12, rcx
0x180014bb9  mov     [rsp+0E8h+var_A8], 0
0x180014bc1  lea     edi, [r14+0Ch]
0x180014bc5  mov     ebp, edi
0x180014bc7  cmp     edi, 4Ch ; 'L'
0x180014bca  ja      loc_180014C9D
0x180014bd0  xor     ebx, ebx
0x180014bd2  lea     rsi, [rsp+0E8h+var_98]
0x180014bd7  lea     rax, [rsp+0E8h+var_A8]
0x180014bdc  mov     [rsp+0E8h+var_B8], 0
0x180014be4  mov     [rsp+0E8h+var_C0], rax
0x180014be9  lea     r8, aKeydatablob; "KeyDataBlob"
0x180014bf0  mov     r9, rsi
0x180014bf3  mov     [rsp+0E8h+var_C8], edi
0x180014bf7  xor     edx, edx
0x180014bf9  mov     rcx, r12
0x180014bfc  call    MSCryptExportKey
0x180014c01  mov     edi, eax
0x180014c03  test    eax, eax
0x180014c05  js      loc_180014D09
0x180014c0b  cmp     r14d, [rsi+8]
0x180014c0f  jnz     short loc_180014C50
0x180014c11  mov     r8, r14; Size
0x180014c14  lea     rdx, [rsi+0Ch]; Src
0x180014c18  mov     rcx, r15; void *
0x180014c1b  call    memmove
0x180014c20  xor     edi, edi
0x180014c22  test    rbx, rbx
0x180014c25  jnz     loc_180014D49
0x180014c2b  mov     eax, edi
0x180014c2d  mov     rcx, [rsp+0E8h+var_48]
0x180014c35  xor     rcx, rsp; StackCookie
0x180014c38  call    __security_check_cookie
0x180014c3d  add     rsp, 0B0h
0x180014c44  pop     r15
0x180014c46  pop     r14
0x180014c48  pop     r12
0x180014c4a  pop     rdi
0x180014c4b  pop     rsi
0x180014c4c  pop     rbp
0x180014c4d  pop     rbx
0x180014c4e  retn
0x180014c50  mov     edi, 0C000000Dh
0x180014c55  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c5c  lea     rax, WPP_GLOBAL_Control
0x180014c63  cmp     rcx, rax
0x180014c66  jz      short loc_180014C22
0x180014c68  mov     eax, [rcx+2Ch]
0x180014c6b  test    al, 1
0x180014c6d  jz      short loc_180014C22
0x180014c6f  mov     [rsp+0E8h+var_B8], 67h ; 'g'
0x180014c77  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180014c7e  mov     [rsp+0E8h+var_C0], rax
0x180014c83  mov     [rsp+0E8h+var_C8], 0C000000Dh
0x180014c8b  mov     rcx, [rcx+18h]
0x180014c8f  lea     r9, aStatus; "Status"
0x180014c96  call    WPP_SF_sDsd
0x180014c9b  jmp     short loc_180014C22
0x180014c9d  mov     rcx, rbp
0x180014ca0  call    MSCryptAlloc
0x180014ca5  mov     rbx, rax
0x180014ca8  test    rax, rax
0x180014cab  jnz     loc_180014D6A
0x180014cb1  mov     edi, 0C0000017h
0x180014cb6  mov     rcx, cs:WPP_GLOBAL_Control
0x180014cbd  lea     rax, WPP_GLOBAL_Control
0x180014cc4  cmp     rcx, rax
0x180014cc7  jz      loc_180014C2B
0x180014ccd  mov     eax, [rcx+2Ch]
0x180014cd0  test    al, 1
0x180014cd2  jz      loc_180014C2B
0x180014cd8  mov     rcx, [rcx+18h]
0x180014cdc  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180014ce3  mov     [rsp+0E8h+var_B8], 4Dh ; 'M'
0x180014ceb  lea     r9, aStatus; "Status"
0x180014cf2  mov     [rsp+0E8h+var_C0], rax
0x180014cf7  mov     [rsp+0E8h+var_C8], 0C0000017h
0x180014cff  call    WPP_SF_sDsd
0x180014d04  jmp     loc_180014C2B
0x180014d09  mov     rcx, cs:WPP_GLOBAL_Control
0x180014d10  lea     rax, WPP_GLOBAL_Control
0x180014d17  cmp     rcx, rax
0x180014d1a  jz      loc_180014C22
0x180014d20  mov     edx, [rcx+2Ch]
0x180014d23  test    dl, 1
0x180014d26  jz      loc_180014C22
0x180014d2c  mov     [rsp+0E8h+var_B8], 5Eh ; '^'
0x180014d34  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180014d3b  mov     [rsp+0E8h+var_C0], rax
0x180014d40  mov     [rsp+0E8h+var_C8], edi
0x180014d44  jmp     loc_180014C8B
0x180014d49  mov     rax, rbx
0x180014d4c  test    rbp, rbp
0x180014d4f  jz      short loc_180014D5D
0x180014d51  mov     byte ptr [rax], 0
0x180014d54  inc     rax
0x180014d57  sub     rbp, 1
0x180014d5b  jnz     short loc_180014D51
0x180014d5d  mov     rcx, rbx; P
0x180014d60  call    MSCryptFree
0x180014d65  jmp     loc_180014C2B
0x180014d6a  mov     rsi, rax
0x180014d6d  jmp     loc_180014BD7
```
