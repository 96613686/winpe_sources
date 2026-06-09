# SdbpGetMatchingTextAttributes

- ea: `0x140822a94`
- end: `0x140822d66`
- name: `SdbpGetMatchingTextAttributes`
- size: `722`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140821fc0`

## callees

- `0x1406cb56c`
- `0x140822a94`
- `0x140978aa4`
- `0x140979890`
- `0x14097b68c`
- `0x14097c750`
- `0x14097cb0c`
- `0x14097ce34`
- `0x14097d158`
- `0x14097d324`

## string_xrefs

- `0x140822c9a`: `Failed to read encoding type`
- `0x140822c77`: `Failed to read text encoding`
- `0x140822c53`: `Failed to read matching text blob`
- `0x140822ba7`: `Failed to read text to match`
- `0x140822d0e`: `Failed to read MATCHING_TEXT file path`
- `0x140822b04`: `Failed to get MATCHING_TEXT file path`

## pseudocode

```c
__int64 __fastcall SdbpGetMatchingTextAttributes(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        _QWORD *a4,
        _DWORD *a5,
        _DWORD *a6,
        _DWORD *a7)
{
  unsigned int FirstTag; // eax
  __int64 v9; // rcx
  __int128 v10; // kr00_16
  void *StringTagPtr; // rax

  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  *a6 = 0;
  *a7 = 0x2000;
  FirstTag = SdbFindFirstTag(a1, a2, 24577);
  if ( FirstTag )
  {
    StringTagPtr = (void *)SdbGetStringTagPtr(a1, FirstTag);
    SdbpUmaInit_PCWSTR(StringTagPtr);
    v10 = 0;
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbpGetMatchingTextAttributes",
      1862,
      (unsigned int)"Failed to read MATCHING_TEXT file path",
      0);
  }
  else
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbpGetMatchingTextAttributes",
      1850,
      (unsigned int)"Failed to get MATCHING_TEXT file path",
      0);
    v10 = 0u;
  }
  if ( (_QWORD)v10 && (_QWORD)v10 != *((_QWORD *)&v10 + 1) )
    AslFree(v9, v10);
  return 0;
}

```

## disassembly

```asm
0x140822a94  mov     [rsp+arg_0], rbx
0x140822a99  mov     [rsp+arg_18], r9
0x140822a9e  mov     [rsp+arg_10], r8
0x140822aa3  push    rbp
0x140822aa4  push    rsi
0x140822aa5  push    rdi
0x140822aa6  push    r12
0x140822aa8  push    r13
0x140822aaa  push    r14
0x140822aac  push    r15
0x140822aae  sub     rsp, 40h
0x140822ab2  mov     rax, [rsp+78h+arg_20]
0x140822aba  xor     ebx, ebx
0x140822abc  mov     [r8], rbx
0x140822abf  xorps   xmm0, xmm0
0x140822ac2  mov     r13d, 2000h
0x140822ac8  mov     [rsp+78h+var_58], ebx
0x140822acc  mov     r8d, 6001h
0x140822ad2  mov     [r9], rbx
0x140822ad5  mov     [rax], ebx
0x140822ad7  mov     r12d, edx
0x140822ada  mov     rax, [rsp+78h+arg_28]
0x140822ae2  mov     rsi, rcx
0x140822ae5  mov     edi, ebx
0x140822ae7  mov     ebp, ebx
0x140822ae9  movups  [rsp+78h+var_50], xmm0
0x140822aee  mov     [rax], ebx
0x140822af0  mov     rax, [rsp+78h+arg_30]
0x140822af8  mov     [rax], r13d
0x140822afb  call    SdbFindFirstTag
0x140822b00  test    eax, eax
0x140822b02  jnz     short loc_140822B2F
0x140822b04  lea     r9, aFailedToGetMat; "Failed to get MATCHING_TEXT file path"
0x140822b0b  mov     r8d, 73Ah
0x140822b11  lea     rdx, aSdbpgetmatchin; "SdbpGetMatchingTextAttributes"
0x140822b18  lea     ecx, [rbx+1]
0x140822b1b  call    AslLogCallPrintf
0x140822b20  mov     r14, qword ptr [rsp+78h+var_50+8]
0x140822b25  mov     rbx, qword ptr [rsp+78h+var_50]
0x140822b2a  jmp     loc_140822D2C
0x140822b2f  mov     edx, eax
0x140822b31  mov     rcx, rsi
0x140822b34  call    SdbGetStringTagPtr
0x140822b39  mov     rcx, rax; Src
0x140822b3c  lea     rdx, [rsp+78h+var_50]
0x140822b41  call    SdbpUmaInit_PCWSTR
0x140822b46  mov     rbx, qword ptr [rsp+78h+var_50]
0x140822b4b  xor     eax, eax
0x140822b4d  mov     r14, qword ptr [rsp+78h+var_50+8]
0x140822b52  test    rbx, rbx
0x140822b55  jnz     short loc_140822B86
0x140822b57  test    r14, r14
0x140822b5a  jz      short loc_140822B7D
0x140822b5c  lea     r9, aOutOfMemory_0; "Out of memory"
0x140822b63  mov     r8d, 740h
0x140822b69  lea     rdx, aSdbpgetmatchin; "SdbpGetMatchingTextAttributes"
0x140822b70  lea     ecx, [rbx+1]
0x140822b73  call    AslLogCallPrintf
0x140822b78  jmp     loc_140822D4B
0x140822b7d  test    rbx, rbx
0x140822b80  jz      loc_140822D0E
0x140822b86  cmp     [rbx], ax
0x140822b89  jz      loc_140822D0E
0x140822b8f  mov     r8d, 9013h
0x140822b95  mov     edx, r12d
0x140822b98  mov     rcx, rsi
0x140822b9b  call    SdbFindFirstTag
0x140822ba0  mov     r15d, eax
0x140822ba3  test    eax, eax
0x140822ba5  jnz     short loc_140822BB9
0x140822ba7  lea     r9, aFailedToReadTe_0; "Failed to read text to match"
0x140822bae  mov     r8d, 74Fh
0x140822bb4  jmp     loc_140822D1B
0x140822bb9  mov     edx, r15d
0x140822bbc  mov     rcx, rsi
0x140822bbf  call    SdbGetTagDataSize
0x140822bc4  mov     ebp, eax
0x140822bc6  test    eax, eax
0x140822bc8  jnz     short loc_140822BEF
0x140822bca  lea     r9, aFailedToGetTex; "Failed to get text to match blob"
0x140822bd1  mov     r8d, 755h
0x140822bd7  lea     rdx, aSdbpgetmatchin; "SdbpGetMatchingTextAttributes"
0x140822bde  mov     ecx, 1
0x140822be3  call    AslLogCallPrintf
0x140822be8  mov     ebp, edi
0x140822bea  jmp     loc_140822D2C
0x140822bef  cmp     ebp, 20000000h
0x140822bf5  jnz     short loc_140822C06
0x140822bf7  lea     r9, aFailedToGetTex_0; "Failed to get text size to match blob"
0x140822bfe  mov     r8d, 759h
0x140822c04  jmp     short loc_140822BD7
0x140822c06  lea     rdx, [rbp+2]
0x140822c0a  call    AslAlloc
0x140822c0f  mov     rdi, rax
0x140822c12  test    rax, rax
0x140822c15  jnz     short loc_140822C3E
0x140822c17  lea     r9, aFailedToAlloca; "Failed to allocate memory for text blob"
0x140822c1e  mov     r8d, 75Fh
0x140822c24  lea     rdx, aSdbpgetmatchin; "SdbpGetMatchingTextAttributes"
0x140822c2b  mov     ecx, 1
0x140822c30  call    AslLogCallPrintf
0x140822c35  mov     ebp, [rsp+78h+var_58]
0x140822c39  jmp     loc_140822D2C
0x140822c3e  mov     r9d, ebp
0x140822c41  mov     r8, rdi
0x140822c44  mov     edx, r15d
0x140822c47  mov     rcx, rsi
0x140822c4a  call    SdbReadBinaryTag
0x140822c4f  test    eax, eax
0x140822c51  jnz     short loc_140822C62
0x140822c53  lea     r9, aFailedToReadMa_0; "Failed to read matching text blob"
0x140822c5a  mov     r8d, 764h
0x140822c60  jmp     short loc_140822C24
0x140822c62  mov     r8d, 4053h
0x140822c68  mov     edx, r12d
0x140822c6b  mov     rcx, rsi
0x140822c6e  call    SdbFindFirstTag
0x140822c73  test    eax, eax
0x140822c75  jnz     short loc_140822C86
0x140822c77  lea     r9, aFailedToReadTe; "Failed to read text encoding"
0x140822c7e  mov     r8d, 76Dh
0x140822c84  jmp     short loc_140822C24
0x140822c86  xor     r8d, r8d
0x140822c89  mov     edx, eax
0x140822c8b  mov     rcx, rsi
0x140822c8e  call    SdbReadDWORDTag
0x140822c93  mov     r15d, eax
0x140822c96  test    eax, eax
0x140822c98  jnz     short loc_140822CAC
0x140822c9a  lea     r9, aFailedToReadEn; "Failed to read encoding type"
0x140822ca1  mov     r8d, 773h
0x140822ca7  jmp     loc_140822C24
0x140822cac  mov     r8d, 4001h
0x140822cb2  mov     edx, r12d
0x140822cb5  mov     rcx, rsi
0x140822cb8  call    SdbFindFirstTag
0x140822cbd  test    eax, eax
0x140822cbf  jz      short loc_140822CD1
0x140822cc1  mov     r8d, r13d
0x140822cc4  mov     edx, eax
0x140822cc6  mov     rcx, rsi
0x140822cc9  call    SdbReadDWORDTag
0x140822cce  mov     r13d, eax
0x140822cd1  mov     rax, [rsp+78h+arg_10]
0x140822cd9  mov     [rax], r14
0x140822cdc  mov     rax, [rsp+78h+arg_18]
0x140822ce4  mov     [rax], rdi
0x140822ce7  xor     edi, edi
0x140822ce9  mov     rax, [rsp+78h+arg_20]
0x140822cf1  mov     [rax], ebp
0x140822cf3  lea     ebp, [rdi+1]
0x140822cf6  mov     rax, [rsp+78h+arg_28]
0x140822cfe  mov     [rax], r15d
0x140822d01  mov     rax, [rsp+78h+arg_30]
0x140822d09  mov     [rax], r13d
0x140822d0c  jmp     short loc_140822D2C
0x140822d0e  lea     r9, aFailedToReadMa_3; "Failed to read MATCHING_TEXT file path"
0x140822d15  mov     r8d, 746h
0x140822d1b  lea     rdx, aSdbpgetmatchin; "SdbpGetMatchingTextAttributes"
0x140822d22  mov     ecx, 1
0x140822d27  call    AslLogCallPrintf
0x140822d2c  test    rbx, rbx
0x140822d2f  jz      short loc_140822D3E
0x140822d31  cmp     rbx, r14
0x140822d34  jz      short loc_140822D3E
0x140822d36  mov     rdx, rbx
0x140822d39  call    AslFree
0x140822d3e  test    rdi, rdi
0x140822d41  jz      short loc_140822D4B
0x140822d43  mov     rdx, rdi
0x140822d46  call    AslFree
0x140822d4b  mov     rbx, [rsp+78h+arg_0]
0x140822d53  mov     eax, ebp
0x140822d55  add     rsp, 40h
0x140822d59  pop     r15
0x140822d5b  pop     r14
0x140822d5d  pop     r13
0x140822d5f  pop     r12
0x140822d61  pop     rdi
0x140822d62  pop     rsi
0x140822d63  pop     rbp
0x140822d64  retn
```
