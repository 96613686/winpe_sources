# _CapiKDF

- ea: `0x18007ea28`
- end: `0x18007ec7e`
- name: `_CapiKDF`
- size: `598`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18007dfb4`

## callees

- `0x180003f70`
- `0x180004320`
- `0x180006470`
- `0x18000743c`
- `0x18002b700`
- `0x180031d70`
- `0x18007ea28`
- `0x18009f650`
- `0x18009f780`
- `0x18009fa80`

## string_xrefs

- `0x18007eafe`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x18007ec4a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`

## pseudocode

```c
__int64 __fastcall CapiKDF(_DWORD *a1, void *a2, unsigned int a3, char a4)
{
  size_t v5; // r14
  unsigned int HashProperty; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  unsigned int v12; // ebx
  __int64 v13; // r9
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rax
  _BYTE *v17; // rdi
  unsigned int v18; // eax
  __int64 v19; // r9
  BOOL v20; // eax
  __int64 i; // rdx
  char v22; // al
  __int64 v23; // rcx
  _BYTE *v24; // rax
  _QWORD v26[2]; // [rsp+30h] [rbp-79h] BYREF
  _BYTE v27[64]; // [rsp+40h] [rbp-69h] BYREF
  _BYTE v28[64]; // [rsp+80h] [rbp-29h] BYREF

  v5 = a3;
  v26[0] = 0;
  HashProperty = MSCryptGetHashProperty(a1, L"HashDigestLength", v26, 4u, (unsigned int *)v26 + 1, 0);
  v12 = HashProperty;
  if ( HashProperty )
  {
    v13 = 1224;
    v14 = HashProperty;
LABEL_30:
    DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c", v13);
    return v12;
  }
  v15 = (unsigned int)(2 * LODWORD(v26[0]));
  if ( (unsigned int)v15 < (unsigned int)v5 || LODWORD(v26[0]) > 0x40 )
  {
    v12 = -1073741811;
    v13 = 1232;
    v14 = 3221225485LL;
    goto LABEL_30;
  }
  v16 = MSCryptAlloc(v15, v9, v10, v11);
  v17 = (_BYTE *)v16;
  if ( !v16 )
  {
    v12 = -1073741801;
    v13 = 1245;
    v14 = 3221225495LL;
    goto LABEL_30;
  }
  v18 = MSCryptFinishHash(a1, v16, LODWORD(v26[0]), 0);
  v12 = v18;
  if ( !v18 )
  {
    v20 = LODWORD(v26[0]) < (unsigned int)v5;
    if ( (a4 & 0x10) != 0 && (_DWORD)v5 == 16 && LODWORD(v26[0]) < 0x20 )
      v20 = 1;
    if ( v20 )
    {
      memset(v27, 54, sizeof(v27));
      memset(v28, 92, sizeof(v28));
      for ( i = 0; (unsigned int)i < LODWORD(v26[0]); i = (unsigned int)(i + 1) )
      {
        v22 = v17[i];
        v27[i] ^= v22;
        v28[i] ^= v22;
      }
      v18 = MSCryptHashData((__int64)a1, (__int64)v27, 64, 0);
      v12 = v18;
      if ( v18 )
      {
        v19 = 1319;
        goto LABEL_9;
      }
      v18 = MSCryptFinishHash(a1, v17, LODWORD(v26[0]), 0);
      v12 = v18;
      if ( v18 )
      {
        v19 = 1330;
        goto LABEL_9;
      }
      v18 = MSCryptHashData((__int64)a1, (__int64)v28, 64, 0);
      v12 = v18;
      if ( v18 )
      {
        v19 = 1342;
        goto LABEL_9;
      }
      v18 = MSCryptFinishHash(a1, &v17[LODWORD(v26[0])], LODWORD(v26[0]), 0);
      v12 = v18;
      if ( v18 )
      {
        v19 = 1353;
        goto LABEL_9;
      }
    }
    memmove(a2, v17, v5);
    v12 = 0;
    goto LABEL_26;
  }
  v19 = 1256;
LABEL_9:
  DebugTraceError(v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c", v19);
LABEL_26:
  v23 = (unsigned int)(2 * LODWORD(v26[0]));
  v24 = v17;
  if ( 2 * LODWORD(v26[0]) )
  {
    do
    {
      *v24++ = 0;
      --v23;
    }
    while ( v23 );
  }
  MSCryptFree(v17);
  return v12;
}

```

## disassembly

```asm
0x18007ea28  push    rbp
0x18007ea2a  push    rbx
0x18007ea2b  push    rsi
0x18007ea2c  push    rdi
0x18007ea2d  push    r12
0x18007ea2f  push    r14
0x18007ea31  push    r15
0x18007ea33  lea     rbp, [rsp-27h]
0x18007ea38  sub     rsp, 0D0h
0x18007ea3f  mov     rax, cs:__security_cookie
0x18007ea46  xor     rax, rsp
0x18007ea49  mov     [rbp+57h+var_40], rax
0x18007ea4d  mov     r15d, r9d
0x18007ea50  mov     r14d, r8d
0x18007ea53  mov     r12, rdx
0x18007ea56  mov     [rsp+100h+var_D8], 0
0x18007ea5e  lea     rax, [rbp+57h+var_CC]
0x18007ea62  mov     [rbp+57h+var_D0], 0
0x18007ea69  mov     r9d, 4
0x18007ea6f  mov     [rsp+100h+var_E0], rax
0x18007ea74  lea     r8, [rbp+57h+var_D0]
0x18007ea78  mov     [rbp+57h+var_CC], 0
0x18007ea7f  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18007ea86  mov     rsi, rcx
0x18007ea89  call    MSCryptGetHashProperty
0x18007ea8e  mov     ebx, eax
0x18007ea90  test    eax, eax
0x18007ea92  jz      short loc_18007EAA1
0x18007ea94  mov     r9d, 4C8h
0x18007ea9a  mov     ecx, eax
0x18007ea9c  jmp     loc_18007EC4A
0x18007eaa1  mov     eax, [rbp+57h+var_D0]
0x18007eaa4  lea     ecx, [rax+rax]
0x18007eaa7  cmp     ecx, r14d
0x18007eaaa  jb      loc_18007EC3A
0x18007eab0  cmp     eax, 40h ; '@'
0x18007eab3  ja      loc_18007EC3A
0x18007eab9  call    MSCryptAlloc
0x18007eabe  mov     rdi, rax
0x18007eac1  test    rax, rax
0x18007eac4  jnz     short loc_18007EADB
0x18007eac6  mov     ebx, 0C0000017h
0x18007eacb  mov     r9d, 4DDh
0x18007ead1  mov     ecx, 0C0000017h
0x18007ead6  jmp     loc_18007EC4A
0x18007eadb  mov     r8d, [rbp+57h+var_D0]
0x18007eadf  xor     r9d, r9d
0x18007eae2  mov     rdx, rdi
0x18007eae5  mov     rcx, rsi
0x18007eae8  call    MSCryptFinishHash
0x18007eaed  mov     ebx, eax
0x18007eaef  mov     ecx, 1
0x18007eaf4  test    eax, eax
0x18007eaf6  jz      short loc_18007EB18
0x18007eaf8  mov     r9d, 4E8h
0x18007eafe  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007eb05  mov     ecx, eax
0x18007eb07  lea     rdx, aStatus; "Status"
0x18007eb0e  call    DebugTraceError
0x18007eb13  jmp     loc_18007EC18
0x18007eb18  xor     eax, eax
0x18007eb1a  cmp     [rbp+57h+var_D0], r14d
0x18007eb1e  cmovb   eax, ecx
0x18007eb21  test    r15b, 10h
0x18007eb25  jz      short loc_18007EB34
0x18007eb27  cmp     r14d, 10h
0x18007eb2b  jnz     short loc_18007EB34
0x18007eb2d  cmp     [rbp+57h+var_D0], 20h ; ' '
0x18007eb31  cmovb   eax, ecx
0x18007eb34  cmp     eax, ecx
0x18007eb36  jnz     loc_18007EC08
0x18007eb3c  mov     r15d, 40h ; '@'
0x18007eb42  lea     rcx, [rbp+57h+var_C0]; void *
0x18007eb46  mov     r8d, r15d; Size
0x18007eb49  lea     edx, [r15-0Ah]; Val
0x18007eb4d  call    memset
0x18007eb52  mov     r8d, r15d; Size
0x18007eb55  lea     edx, [r15+1Ch]; Val
0x18007eb59  lea     rcx, [rbp+57h+var_80]; void *
0x18007eb5d  call    memset
0x18007eb62  xor     edx, edx
0x18007eb64  cmp     [rbp+57h+var_D0], edx
0x18007eb67  jbe     short loc_18007EB7B
0x18007eb69  mov     al, [rdx+rdi]
0x18007eb6c  xor     [rbp+rdx+57h+var_C0], al
0x18007eb70  xor     [rbp+rdx+57h+var_80], al
0x18007eb74  inc     edx
0x18007eb76  cmp     edx, [rbp+57h+var_D0]
0x18007eb79  jb      short loc_18007EB69
0x18007eb7b  xor     r9d, r9d
0x18007eb7e  lea     rdx, [rbp+57h+var_C0]
0x18007eb82  mov     r8d, r15d
0x18007eb85  mov     rcx, rsi
0x18007eb88  call    MSCryptHashData
0x18007eb8d  mov     ebx, eax
0x18007eb8f  test    eax, eax
0x18007eb91  jz      short loc_18007EB9E
0x18007eb93  mov     r9d, 527h
0x18007eb99  jmp     loc_18007EAFE
0x18007eb9e  mov     r8d, [rbp+57h+var_D0]
0x18007eba2  xor     r9d, r9d
0x18007eba5  mov     rdx, rdi
0x18007eba8  mov     rcx, rsi
0x18007ebab  call    MSCryptFinishHash
0x18007ebb0  mov     ebx, eax
0x18007ebb2  test    eax, eax
0x18007ebb4  jz      short loc_18007EBC1
0x18007ebb6  mov     r9d, 532h
0x18007ebbc  jmp     loc_18007EAFE
0x18007ebc1  xor     r9d, r9d
0x18007ebc4  lea     rdx, [rbp+57h+var_80]
0x18007ebc8  mov     r8d, r15d
0x18007ebcb  mov     rcx, rsi
0x18007ebce  call    MSCryptHashData
0x18007ebd3  mov     ebx, eax
0x18007ebd5  test    eax, eax
0x18007ebd7  jz      short loc_18007EBE4
0x18007ebd9  mov     r9d, 53Eh
0x18007ebdf  jmp     loc_18007EAFE
0x18007ebe4  mov     r8d, [rbp+57h+var_D0]
0x18007ebe8  xor     r9d, r9d
0x18007ebeb  mov     rcx, rsi
0x18007ebee  lea     rdx, [rdi+r8]
0x18007ebf2  call    MSCryptFinishHash
0x18007ebf7  mov     ebx, eax
0x18007ebf9  test    eax, eax
0x18007ebfb  jz      short loc_18007EC08
0x18007ebfd  mov     r9d, 549h
0x18007ec03  jmp     loc_18007EAFE
0x18007ec08  mov     r8, r14; Size
0x18007ec0b  mov     rdx, rdi; Src
0x18007ec0e  mov     rcx, r12; void *
0x18007ec11  call    memmove
0x18007ec16  xor     ebx, ebx
0x18007ec18  mov     eax, [rbp+57h+var_D0]
0x18007ec1b  add     eax, eax
0x18007ec1d  mov     ecx, eax
0x18007ec1f  mov     rax, rdi
0x18007ec22  jz      short loc_18007EC30
0x18007ec24  mov     byte ptr [rax], 0
0x18007ec27  inc     rax
0x18007ec2a  sub     rcx, 1
0x18007ec2e  jnz     short loc_18007EC24
0x18007ec30  mov     rcx, rdi; P
0x18007ec33  call    MSCryptFree
0x18007ec38  jmp     short loc_18007EC5D
0x18007ec3a  mov     ebx, 0C000000Dh
0x18007ec3f  mov     r9d, 4D0h
0x18007ec45  mov     ecx, 0C000000Dh
0x18007ec4a  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007ec51  lea     rdx, aStatus; "Status"
0x18007ec58  call    DebugTraceError
0x18007ec5d  mov     eax, ebx
0x18007ec5f  mov     rcx, [rbp+57h+var_40]
0x18007ec63  xor     rcx, rsp; StackCookie
0x18007ec66  call    __security_check_cookie
0x18007ec6b  add     rsp, 0D0h
0x18007ec72  pop     r15
0x18007ec74  pop     r14
0x18007ec76  pop     r12
0x18007ec78  pop     rdi
0x18007ec79  pop     rsi
0x18007ec7a  pop     rbx
0x18007ec7b  pop     rbp
0x18007ec7c  retn
```
