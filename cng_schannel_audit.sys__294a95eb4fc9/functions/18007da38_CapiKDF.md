# _CapiKDF

- ea: `0x18007da38`
- end: `0x18007dc8e`
- name: `_CapiKDF`
- size: `598`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18007cfc4`

## callees

- `0x180003f70`
- `0x180004320`
- `0x180006470`
- `0x18000743c`
- `0x180011ac0`
- `0x180031270`
- `0x18007da38`
- `0x18009d820`
- `0x18009da40`
- `0x18009dd40`

## string_xrefs

- `0x18007db0e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x18007dc5a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`

## pseudocode

```c
__int64 __fastcall CapiKDF(_DWORD *a1, void *a2, unsigned int a3, char a4)
{
  size_t v5; // r14
  unsigned int HashProperty; // eax
  __int64 v9; // rdx
  unsigned int v10; // ebx
  __int64 v11; // r9
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rax
  _BYTE *v15; // rdi
  unsigned int v16; // eax
  __int64 v17; // r9
  BOOL v18; // eax
  __int64 i; // rdx
  char v20; // al
  __int64 v21; // rcx
  _BYTE *v22; // rax
  _QWORD v24[2]; // [rsp+30h] [rbp-79h] BYREF
  _BYTE v25[64]; // [rsp+40h] [rbp-69h] BYREF
  _BYTE v26[64]; // [rsp+80h] [rbp-29h] BYREF

  v5 = a3;
  v24[0] = 0;
  HashProperty = MSCryptGetHashProperty(a1, L"HashDigestLength", v24, 4u, (unsigned int *)v24 + 1, 0);
  v10 = HashProperty;
  if ( HashProperty )
  {
    v11 = 1224;
    v12 = HashProperty;
LABEL_30:
    DebugTraceError(v12, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c", v11);
    return v10;
  }
  v13 = (unsigned int)(2 * LODWORD(v24[0]));
  if ( (unsigned int)v13 < (unsigned int)v5 || LODWORD(v24[0]) > 0x40 )
  {
    v10 = -1073741811;
    v11 = 1232;
    v12 = 3221225485LL;
    goto LABEL_30;
  }
  v14 = MSCryptAlloc(v13, v9);
  v15 = (_BYTE *)v14;
  if ( !v14 )
  {
    v10 = -1073741801;
    v11 = 1245;
    v12 = 3221225495LL;
    goto LABEL_30;
  }
  v16 = MSCryptFinishHash(a1, v14, LODWORD(v24[0]), 0);
  v10 = v16;
  if ( !v16 )
  {
    v18 = LODWORD(v24[0]) < (unsigned int)v5;
    if ( (a4 & 0x10) != 0 && (_DWORD)v5 == 16 && LODWORD(v24[0]) < 0x20 )
      v18 = 1;
    if ( v18 )
    {
      memset(v25, 54, sizeof(v25));
      memset(v26, 92, sizeof(v26));
      for ( i = 0; (unsigned int)i < LODWORD(v24[0]); i = (unsigned int)(i + 1) )
      {
        v20 = v15[i];
        v25[i] ^= v20;
        v26[i] ^= v20;
      }
      v16 = MSCryptHashData((__int64)a1, (__int64)v25, 64, 0);
      v10 = v16;
      if ( v16 )
      {
        v17 = 1319;
        goto LABEL_9;
      }
      v16 = MSCryptFinishHash(a1, v15, LODWORD(v24[0]), 0);
      v10 = v16;
      if ( v16 )
      {
        v17 = 1330;
        goto LABEL_9;
      }
      v16 = MSCryptHashData((__int64)a1, (__int64)v26, 64, 0);
      v10 = v16;
      if ( v16 )
      {
        v17 = 1342;
        goto LABEL_9;
      }
      v16 = MSCryptFinishHash(a1, &v15[LODWORD(v24[0])], LODWORD(v24[0]), 0);
      v10 = v16;
      if ( v16 )
      {
        v17 = 1353;
        goto LABEL_9;
      }
    }
    memmove(a2, v15, v5);
    v10 = 0;
    goto LABEL_26;
  }
  v17 = 1256;
LABEL_9:
  DebugTraceError(v16, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c", v17);
LABEL_26:
  v21 = (unsigned int)(2 * LODWORD(v24[0]));
  v22 = v15;
  if ( 2 * LODWORD(v24[0]) )
  {
    do
    {
      *v22++ = 0;
      --v21;
    }
    while ( v21 );
  }
  MSCryptFree(v15);
  return v10;
}

```

## disassembly

```asm
0x18007da38  push    rbp
0x18007da3a  push    rbx
0x18007da3b  push    rsi
0x18007da3c  push    rdi
0x18007da3d  push    r12
0x18007da3f  push    r14
0x18007da41  push    r15
0x18007da43  lea     rbp, [rsp-27h]
0x18007da48  sub     rsp, 0D0h
0x18007da4f  mov     rax, cs:__security_cookie
0x18007da56  xor     rax, rsp
0x18007da59  mov     [rbp+57h+var_40], rax
0x18007da5d  mov     r15d, r9d
0x18007da60  mov     r14d, r8d
0x18007da63  mov     r12, rdx
0x18007da66  mov     [rsp+100h+var_D8], 0
0x18007da6e  lea     rax, [rbp+57h+var_CC]
0x18007da72  mov     [rbp+57h+var_D0], 0
0x18007da79  mov     r9d, 4
0x18007da7f  mov     [rsp+100h+var_E0], rax
0x18007da84  lea     r8, [rbp+57h+var_D0]
0x18007da88  mov     [rbp+57h+var_CC], 0
0x18007da8f  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18007da96  mov     rsi, rcx
0x18007da99  call    MSCryptGetHashProperty
0x18007da9e  mov     ebx, eax
0x18007daa0  test    eax, eax
0x18007daa2  jz      short loc_18007DAB1
0x18007daa4  mov     r9d, 4C8h
0x18007daaa  mov     ecx, eax
0x18007daac  jmp     loc_18007DC5A
0x18007dab1  mov     eax, [rbp+57h+var_D0]
0x18007dab4  lea     ecx, [rax+rax]
0x18007dab7  cmp     ecx, r14d
0x18007daba  jb      loc_18007DC4A
0x18007dac0  cmp     eax, 40h ; '@'
0x18007dac3  ja      loc_18007DC4A
0x18007dac9  call    MSCryptAlloc
0x18007dace  mov     rdi, rax
0x18007dad1  test    rax, rax
0x18007dad4  jnz     short loc_18007DAEB
0x18007dad6  mov     ebx, 0C0000017h
0x18007dadb  mov     r9d, 4DDh
0x18007dae1  mov     ecx, 0C0000017h
0x18007dae6  jmp     loc_18007DC5A
0x18007daeb  mov     r8d, [rbp+57h+var_D0]
0x18007daef  xor     r9d, r9d
0x18007daf2  mov     rdx, rdi
0x18007daf5  mov     rcx, rsi
0x18007daf8  call    MSCryptFinishHash
0x18007dafd  mov     ebx, eax
0x18007daff  mov     ecx, 1
0x18007db04  test    eax, eax
0x18007db06  jz      short loc_18007DB28
0x18007db08  mov     r9d, 4E8h
0x18007db0e  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007db15  mov     ecx, eax
0x18007db17  lea     rdx, aStatus; "Status"
0x18007db1e  call    DebugTraceError
0x18007db23  jmp     loc_18007DC28
0x18007db28  xor     eax, eax
0x18007db2a  cmp     [rbp+57h+var_D0], r14d
0x18007db2e  cmovb   eax, ecx
0x18007db31  test    r15b, 10h
0x18007db35  jz      short loc_18007DB44
0x18007db37  cmp     r14d, 10h
0x18007db3b  jnz     short loc_18007DB44
0x18007db3d  cmp     [rbp+57h+var_D0], 20h ; ' '
0x18007db41  cmovb   eax, ecx
0x18007db44  cmp     eax, ecx
0x18007db46  jnz     loc_18007DC18
0x18007db4c  mov     r15d, 40h ; '@'
0x18007db52  lea     rcx, [rbp+57h+var_C0]; void *
0x18007db56  mov     r8d, r15d; Size
0x18007db59  lea     edx, [r15-0Ah]; Val
0x18007db5d  call    memset
0x18007db62  mov     r8d, r15d; Size
0x18007db65  lea     edx, [r15+1Ch]; Val
0x18007db69  lea     rcx, [rbp+57h+var_80]; void *
0x18007db6d  call    memset
0x18007db72  xor     edx, edx
0x18007db74  cmp     [rbp+57h+var_D0], edx
0x18007db77  jbe     short loc_18007DB8B
0x18007db79  mov     al, [rdx+rdi]
0x18007db7c  xor     [rbp+rdx+57h+var_C0], al
0x18007db80  xor     [rbp+rdx+57h+var_80], al
0x18007db84  inc     edx
0x18007db86  cmp     edx, [rbp+57h+var_D0]
0x18007db89  jb      short loc_18007DB79
0x18007db8b  xor     r9d, r9d
0x18007db8e  lea     rdx, [rbp+57h+var_C0]
0x18007db92  mov     r8d, r15d
0x18007db95  mov     rcx, rsi
0x18007db98  call    MSCryptHashData
0x18007db9d  mov     ebx, eax
0x18007db9f  test    eax, eax
0x18007dba1  jz      short loc_18007DBAE
0x18007dba3  mov     r9d, 527h
0x18007dba9  jmp     loc_18007DB0E
0x18007dbae  mov     r8d, [rbp+57h+var_D0]
0x18007dbb2  xor     r9d, r9d
0x18007dbb5  mov     rdx, rdi
0x18007dbb8  mov     rcx, rsi
0x18007dbbb  call    MSCryptFinishHash
0x18007dbc0  mov     ebx, eax
0x18007dbc2  test    eax, eax
0x18007dbc4  jz      short loc_18007DBD1
0x18007dbc6  mov     r9d, 532h
0x18007dbcc  jmp     loc_18007DB0E
0x18007dbd1  xor     r9d, r9d
0x18007dbd4  lea     rdx, [rbp+57h+var_80]
0x18007dbd8  mov     r8d, r15d
0x18007dbdb  mov     rcx, rsi
0x18007dbde  call    MSCryptHashData
0x18007dbe3  mov     ebx, eax
0x18007dbe5  test    eax, eax
0x18007dbe7  jz      short loc_18007DBF4
0x18007dbe9  mov     r9d, 53Eh
0x18007dbef  jmp     loc_18007DB0E
0x18007dbf4  mov     r8d, [rbp+57h+var_D0]
0x18007dbf8  xor     r9d, r9d
0x18007dbfb  mov     rcx, rsi
0x18007dbfe  lea     rdx, [rdi+r8]
0x18007dc02  call    MSCryptFinishHash
0x18007dc07  mov     ebx, eax
0x18007dc09  test    eax, eax
0x18007dc0b  jz      short loc_18007DC18
0x18007dc0d  mov     r9d, 549h
0x18007dc13  jmp     loc_18007DB0E
0x18007dc18  mov     r8, r14; Size
0x18007dc1b  mov     rdx, rdi; Src
0x18007dc1e  mov     rcx, r12; void *
0x18007dc21  call    memmove
0x18007dc26  xor     ebx, ebx
0x18007dc28  mov     eax, [rbp+57h+var_D0]
0x18007dc2b  add     eax, eax
0x18007dc2d  mov     ecx, eax
0x18007dc2f  mov     rax, rdi
0x18007dc32  jz      short loc_18007DC40
0x18007dc34  mov     byte ptr [rax], 0
0x18007dc37  inc     rax
0x18007dc3a  sub     rcx, 1
0x18007dc3e  jnz     short loc_18007DC34
0x18007dc40  mov     rcx, rdi; P
0x18007dc43  call    MSCryptFree
0x18007dc48  jmp     short loc_18007DC6D
0x18007dc4a  mov     ebx, 0C000000Dh
0x18007dc4f  mov     r9d, 4D0h
0x18007dc55  mov     ecx, 0C000000Dh
0x18007dc5a  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007dc61  lea     rdx, aStatus; "Status"
0x18007dc68  call    DebugTraceError
0x18007dc6d  mov     eax, ebx
0x18007dc6f  mov     rcx, [rbp+57h+var_40]
0x18007dc73  xor     rcx, rsp; StackCookie
0x18007dc76  call    __security_check_cookie
0x18007dc7b  add     rsp, 0D0h
0x18007dc82  pop     r15
0x18007dc84  pop     r14
0x18007dc86  pop     r12
0x18007dc88  pop     rdi
0x18007dc89  pop     rsi
0x18007dc8a  pop     rbx
0x18007dc8b  pop     rbp
0x18007dc8c  retn
```
