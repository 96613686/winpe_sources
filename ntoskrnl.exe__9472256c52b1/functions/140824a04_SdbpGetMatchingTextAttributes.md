# SdbpGetMatchingTextAttributes

- ea: `0x140824a04`
- end: `0x140824cd6`
- name: `SdbpGetMatchingTextAttributes`
- size: `722`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140823f30`

## callees

- `0x1406ce1cc`
- `0x140824a04`
- `0x1408be86c`
- `0x1408bf658`
- `0x1408c14bc`
- `0x1408c2580`
- `0x1408c293c`
- `0x1408c2c64`
- `0x1408c2f88`
- `0x1408c3154`

## string_xrefs

- `0x140824c0a`: `Failed to read encoding type`
- `0x140824be7`: `Failed to read text encoding`
- `0x140824bc3`: `Failed to read matching text blob`
- `0x140824c7e`: `Failed to read MATCHING_TEXT file path`
- `0x140824b17`: `Failed to read text to match`
- `0x140824a74`: `Failed to get MATCHING_TEXT file path`

## pseudocode

```c
__int64 __fastcall SdbpGetMatchingTextAttributes(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 *a4,
        unsigned int *a5,
        _DWORD *a6,
        int *a7)
{
  int v7; // r13d
  unsigned int v8; // r12d
  __int64 v10; // rdi
  unsigned int v11; // ebp
  unsigned int FirstTag; // eax
  __int64 v13; // rcx
  __int128 v14; // kr00_16
  char *StringTagPtr; // rax
  unsigned int v16; // eax
  unsigned int v17; // r15d
  const char *v18; // r9
  int v19; // r8d
  unsigned int TagDataSize; // eax
  __int64 v21; // rcx
  unsigned int v22; // ebp
  const char *v23; // r9
  int v24; // r8d
  __int64 v25; // rax
  unsigned int v26; // eax
  int DWORDTag; // r15d
  unsigned int v28; // eax
  __int128 v30; // [rsp+28h] [rbp-50h] BYREF

  *a3 = 0;
  v7 = 0x2000;
  *a4 = 0;
  *a5 = 0;
  v8 = a2;
  v10 = 0;
  v11 = 0;
  v30 = 0;
  *a6 = 0;
  *a7 = 0x2000;
  FirstTag = SdbFindFirstTag(a1, a2, 24577);
  if ( !FirstTag )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbpGetMatchingTextAttributes",
      1850,
      (unsigned int)"Failed to get MATCHING_TEXT file path");
    v14 = v30;
    goto LABEL_28;
  }
  StringTagPtr = (char *)SdbGetStringTagPtr(a1, FirstTag);
  SdbpUmaInit_PCWSTR(StringTagPtr, (char **)&v30);
  v14 = v30;
  if ( !(_QWORD)v30 )
  {
    if ( *((_QWORD *)&v30 + 1) )
    {
      AslLogCallPrintf(v30 + 1, (unsigned int)"SdbpGetMatchingTextAttributes", 1856, (unsigned int)"Out of memory");
      return v11;
    }
    goto LABEL_26;
  }
  if ( !*(_WORD *)v30 )
  {
LABEL_26:
    v18 = "Failed to read MATCHING_TEXT file path";
    v19 = 1862;
    goto LABEL_27;
  }
  v16 = SdbFindFirstTag(a1, v8, 36883);
  v17 = v16;
  if ( !v16 )
  {
    v18 = "Failed to read text to match";
    v19 = 1871;
LABEL_27:
    AslLogCallPrintf(1, (unsigned int)"SdbpGetMatchingTextAttributes", v19, (_DWORD)v18);
    goto LABEL_28;
  }
  TagDataSize = SdbGetTagDataSize(a1, v16);
  v22 = TagDataSize;
  if ( TagDataSize )
  {
    if ( TagDataSize == 0x20000000 )
    {
      v23 = "Failed to get text size to match blob";
      v24 = 1881;
    }
    else
    {
      v25 = AslAlloc(v21, TagDataSize + 2LL);
      v10 = v25;
      if ( v25 )
      {
        if ( (unsigned int)SdbReadBinaryTag(a1, v17, v25, v22) )
        {
          v26 = SdbFindFirstTag(a1, v8, 16467);
          if ( v26 )
          {
            DWORDTag = SdbReadDWORDTag(a1, v26, 0);
            if ( DWORDTag )
            {
              v28 = SdbFindFirstTag(a1, v8, 16385);
              if ( v28 )
                v7 = SdbReadDWORDTag(a1, v28, 0x2000);
              *a3 = *((_QWORD *)&v14 + 1);
              *a4 = v10;
              v10 = 0;
              *a5 = v22;
              v11 = 1;
              *a6 = DWORDTag;
              *a7 = v7;
              goto LABEL_28;
            }
            v23 = "Failed to read encoding type";
            v24 = 1907;
          }
          else
          {
            v23 = "Failed to read text encoding";
            v24 = 1901;
          }
        }
        else
        {
          v23 = "Failed to read matching text blob";
          v24 = 1892;
        }
      }
      else
      {
        v23 = "Failed to allocate memory for text blob";
        v24 = 1887;
      }
    }
  }
  else
  {
    v23 = "Failed to get text to match blob";
    v24 = 1877;
  }
  AslLogCallPrintf(1, (unsigned int)"SdbpGetMatchingTextAttributes", v24, (_DWORD)v23);
  v11 = 0;
LABEL_28:
  if ( (_QWORD)v14 && (_QWORD)v14 != *((_QWORD *)&v14 + 1) )
    AslFree(v13, v14);
  if ( v10 )
    AslFree(v13, v10);
  return v11;
}

```

## disassembly

```asm
0x140824a04  mov     [rsp+arg_0], rbx
0x140824a09  mov     [rsp+arg_18], r9
0x140824a0e  mov     [rsp+arg_10], r8
0x140824a13  push    rbp
0x140824a14  push    rsi
0x140824a15  push    rdi
0x140824a16  push    r12
0x140824a18  push    r13
0x140824a1a  push    r14
0x140824a1c  push    r15
0x140824a1e  sub     rsp, 40h
0x140824a22  mov     rax, [rsp+78h+arg_20]
0x140824a2a  xor     ebx, ebx
0x140824a2c  mov     [r8], rbx
0x140824a2f  xorps   xmm0, xmm0
0x140824a32  mov     r13d, 2000h
0x140824a38  mov     [rsp+78h+var_58], ebx
0x140824a3c  mov     r8d, 6001h
0x140824a42  mov     [r9], rbx
0x140824a45  mov     [rax], ebx
0x140824a47  mov     r12d, edx
0x140824a4a  mov     rax, [rsp+78h+arg_28]
0x140824a52  mov     rsi, rcx
0x140824a55  mov     edi, ebx
0x140824a57  mov     ebp, ebx
0x140824a59  movups  [rsp+78h+var_50], xmm0
0x140824a5e  mov     [rax], ebx
0x140824a60  mov     rax, [rsp+78h+arg_30]
0x140824a68  mov     [rax], r13d
0x140824a6b  call    SdbFindFirstTag
0x140824a70  test    eax, eax
0x140824a72  jnz     short loc_140824A9F
0x140824a74  lea     r9, aFailedToGetMat; "Failed to get MATCHING_TEXT file path"
0x140824a7b  mov     r8d, 73Ah
0x140824a81  lea     rdx, aSdbpgetmatchin; "SdbpGetMatchingTextAttributes"
0x140824a88  lea     ecx, [rbx+1]
0x140824a8b  call    AslLogCallPrintf
0x140824a90  mov     r14, qword ptr [rsp+78h+var_50+8]
0x140824a95  mov     rbx, qword ptr [rsp+78h+var_50]
0x140824a9a  jmp     loc_140824C9C
0x140824a9f  mov     edx, eax
0x140824aa1  mov     rcx, rsi
0x140824aa4  call    SdbGetStringTagPtr
0x140824aa9  mov     rcx, rax; Src
0x140824aac  lea     rdx, [rsp+78h+var_50]
0x140824ab1  call    SdbpUmaInit_PCWSTR
0x140824ab6  mov     rbx, qword ptr [rsp+78h+var_50]
0x140824abb  xor     eax, eax
0x140824abd  mov     r14, qword ptr [rsp+78h+var_50+8]
0x140824ac2  test    rbx, rbx
0x140824ac5  jnz     short loc_140824AF6
0x140824ac7  test    r14, r14
0x140824aca  jz      short loc_140824AED
0x140824acc  lea     r9, aOutOfMemory_0; "Out of memory"
0x140824ad3  mov     r8d, 740h
0x140824ad9  lea     rdx, aSdbpgetmatchin; "SdbpGetMatchingTextAttributes"
0x140824ae0  lea     ecx, [rbx+1]
0x140824ae3  call    AslLogCallPrintf
0x140824ae8  jmp     loc_140824CBB
0x140824aed  test    rbx, rbx
0x140824af0  jz      loc_140824C7E
0x140824af6  cmp     [rbx], ax
0x140824af9  jz      loc_140824C7E
0x140824aff  mov     r8d, 9013h
0x140824b05  mov     edx, r12d
0x140824b08  mov     rcx, rsi
0x140824b0b  call    SdbFindFirstTag
0x140824b10  mov     r15d, eax
0x140824b13  test    eax, eax
0x140824b15  jnz     short loc_140824B29
0x140824b17  lea     r9, aFailedToReadTe_0; "Failed to read text to match"
0x140824b1e  mov     r8d, 74Fh
0x140824b24  jmp     loc_140824C8B
0x140824b29  mov     edx, r15d
0x140824b2c  mov     rcx, rsi
0x140824b2f  call    SdbGetTagDataSize
0x140824b34  mov     ebp, eax
0x140824b36  test    eax, eax
0x140824b38  jnz     short loc_140824B5F
0x140824b3a  lea     r9, aFailedToGetTex; "Failed to get text to match blob"
0x140824b41  mov     r8d, 755h
0x140824b47  lea     rdx, aSdbpgetmatchin; "SdbpGetMatchingTextAttributes"
0x140824b4e  mov     ecx, 1
0x140824b53  call    AslLogCallPrintf
0x140824b58  mov     ebp, edi
0x140824b5a  jmp     loc_140824C9C
0x140824b5f  cmp     ebp, 20000000h
0x140824b65  jnz     short loc_140824B76
0x140824b67  lea     r9, aFailedToGetTex_0; "Failed to get text size to match blob"
0x140824b6e  mov     r8d, 759h
0x140824b74  jmp     short loc_140824B47
0x140824b76  lea     rdx, [rbp+2]
0x140824b7a  call    AslAlloc
0x140824b7f  mov     rdi, rax
0x140824b82  test    rax, rax
0x140824b85  jnz     short loc_140824BAE
0x140824b87  lea     r9, aFailedToAlloca; "Failed to allocate memory for text blob"
0x140824b8e  mov     r8d, 75Fh
0x140824b94  lea     rdx, aSdbpgetmatchin; "SdbpGetMatchingTextAttributes"
0x140824b9b  mov     ecx, 1
0x140824ba0  call    AslLogCallPrintf
0x140824ba5  mov     ebp, [rsp+78h+var_58]
0x140824ba9  jmp     loc_140824C9C
0x140824bae  mov     r9d, ebp
0x140824bb1  mov     r8, rdi
0x140824bb4  mov     edx, r15d
0x140824bb7  mov     rcx, rsi
0x140824bba  call    SdbReadBinaryTag
0x140824bbf  test    eax, eax
0x140824bc1  jnz     short loc_140824BD2
0x140824bc3  lea     r9, aFailedToReadMa_0; "Failed to read matching text blob"
0x140824bca  mov     r8d, 764h
0x140824bd0  jmp     short loc_140824B94
0x140824bd2  mov     r8d, 4053h
0x140824bd8  mov     edx, r12d
0x140824bdb  mov     rcx, rsi
0x140824bde  call    SdbFindFirstTag
0x140824be3  test    eax, eax
0x140824be5  jnz     short loc_140824BF6
0x140824be7  lea     r9, aFailedToReadTe; "Failed to read text encoding"
0x140824bee  mov     r8d, 76Dh
0x140824bf4  jmp     short loc_140824B94
0x140824bf6  xor     r8d, r8d
0x140824bf9  mov     edx, eax
0x140824bfb  mov     rcx, rsi
0x140824bfe  call    SdbReadDWORDTag
0x140824c03  mov     r15d, eax
0x140824c06  test    eax, eax
0x140824c08  jnz     short loc_140824C1C
0x140824c0a  lea     r9, aFailedToReadEn; "Failed to read encoding type"
0x140824c11  mov     r8d, 773h
0x140824c17  jmp     loc_140824B94
0x140824c1c  mov     r8d, 4001h
0x140824c22  mov     edx, r12d
0x140824c25  mov     rcx, rsi
0x140824c28  call    SdbFindFirstTag
0x140824c2d  test    eax, eax
0x140824c2f  jz      short loc_140824C41
0x140824c31  mov     r8d, r13d
0x140824c34  mov     edx, eax
0x140824c36  mov     rcx, rsi
0x140824c39  call    SdbReadDWORDTag
0x140824c3e  mov     r13d, eax
0x140824c41  mov     rax, [rsp+78h+arg_10]
0x140824c49  mov     [rax], r14
0x140824c4c  mov     rax, [rsp+78h+arg_18]
0x140824c54  mov     [rax], rdi
0x140824c57  xor     edi, edi
0x140824c59  mov     rax, [rsp+78h+arg_20]
0x140824c61  mov     [rax], ebp
0x140824c63  lea     ebp, [rdi+1]
0x140824c66  mov     rax, [rsp+78h+arg_28]
0x140824c6e  mov     [rax], r15d
0x140824c71  mov     rax, [rsp+78h+arg_30]
0x140824c79  mov     [rax], r13d
0x140824c7c  jmp     short loc_140824C9C
0x140824c7e  lea     r9, aFailedToReadMa_3; "Failed to read MATCHING_TEXT file path"
0x140824c85  mov     r8d, 746h
0x140824c8b  lea     rdx, aSdbpgetmatchin; "SdbpGetMatchingTextAttributes"
0x140824c92  mov     ecx, 1
0x140824c97  call    AslLogCallPrintf
0x140824c9c  test    rbx, rbx
0x140824c9f  jz      short loc_140824CAE
0x140824ca1  cmp     rbx, r14
0x140824ca4  jz      short loc_140824CAE
0x140824ca6  mov     rdx, rbx
0x140824ca9  call    AslFree
0x140824cae  test    rdi, rdi
0x140824cb1  jz      short loc_140824CBB
0x140824cb3  mov     rdx, rdi
0x140824cb6  call    AslFree
0x140824cbb  mov     rbx, [rsp+78h+arg_0]
0x140824cc3  mov     eax, ebp
0x140824cc5  add     rsp, 40h
0x140824cc9  pop     r15
0x140824ccb  pop     r14
0x140824ccd  pop     r13
0x140824ccf  pop     r12
0x140824cd1  pop     rdi
0x140824cd2  pop     rsi
0x140824cd3  pop     rbp
0x140824cd4  retn
```
