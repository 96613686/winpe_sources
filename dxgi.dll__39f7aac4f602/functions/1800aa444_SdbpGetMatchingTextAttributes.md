# SdbpGetMatchingTextAttributes

- ea: `0x1800aa444`
- end: `0x1800aa699`
- name: `SdbpGetMatchingTextAttributes`
- size: `597`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800a9b30`

## callees

- `0x180040e44`
- `0x180041774`
- `0x1800423c0`
- `0x18004281c`
- `0x180042854`
- `0x1800428f4`
- `0x1800aa444`
- `0x1800ad3a4`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800aa55e`
- `ntdll!RtlAllocateHeap` at `0x1800aa55e`

## string_xrefs

- `0x1800aa4a7`: `Failed to get MATCHING_TEXT file path`
- `0x1800aa64f`: `Failed to read MATCHING_TEXT file path`
- `0x1800aa500`: `Failed to read text to match`
- `0x1800aa5bf`: `Failed to read text encoding`
- `0x1800aa598`: `Failed to read matching text blob`
- `0x1800aa5e4`: `Failed to read encoding type`

## pseudocode

```c
__int64 __fastcall SdbpGetMatchingTextAttributes(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        _QWORD *a4,
        unsigned int *a5,
        _DWORD *a6,
        int *a7)
{
  PVOID v7; // rbx
  int v8; // r12d
  unsigned int v9; // r15d
  unsigned int v11; // r13d
  unsigned int FirstTag; // eax
  _WORD *StringTagPtr; // rax
  _WORD *v14; // r14
  unsigned int v15; // eax
  unsigned int v16; // ebp
  unsigned int TagDataSize; // eax
  unsigned int v18; // esi
  PVOID Heap; // rax
  unsigned int v20; // eax
  int DWORDTag; // ebp
  unsigned int v22; // eax

  v7 = 0;
  *a3 = 0;
  v8 = 0x2000;
  *a4 = 0;
  v9 = a2;
  *a5 = 0;
  v11 = 0;
  *a6 = 0;
  *a7 = 0x2000;
  FirstTag = SdbFindFirstTag(a1, a2, 24577);
  if ( !FirstTag )
  {
    AslLogCallPrintf(1, "SdbpGetMatchingTextAttributes", 1850, "Failed to get MATCHING_TEXT file path");
    return v11;
  }
  StringTagPtr = (_WORD *)SdbGetStringTagPtr(a1, FirstTag);
  v14 = StringTagPtr;
  if ( !StringTagPtr || !*StringTagPtr )
  {
    AslLogCallPrintf(1, "SdbpGetMatchingTextAttributes", 1862, "Failed to read MATCHING_TEXT file path");
LABEL_24:
    if ( v7 )
      AslFree(NtCurrentPeb()->ProcessHeap, v7);
    return v11;
  }
  v15 = SdbFindFirstTag(a1, v9, 36883);
  v16 = v15;
  if ( !v15 )
  {
    AslLogCallPrintf(1, "SdbpGetMatchingTextAttributes", 1871, "Failed to read text to match");
    return v11;
  }
  TagDataSize = SdbGetTagDataSize(a1, v15);
  v18 = TagDataSize;
  if ( !TagDataSize )
  {
    AslLogCallPrintf(1, "SdbpGetMatchingTextAttributes", 1877, "Failed to get text to match blob");
    return v11;
  }
  if ( TagDataSize == 0x20000000 )
  {
    AslLogCallPrintf(1, "SdbpGetMatchingTextAttributes", 1881, "Failed to get text size to match blob");
    return v11;
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, TagDataSize + 2LL);
  v7 = Heap;
  if ( !Heap )
  {
    AslLogCallPrintf(1, "SdbpGetMatchingTextAttributes", 1887, "Failed to allocate memory for text blob");
    return v11;
  }
  if ( !(unsigned int)SdbReadBinaryTag(a1, v16, Heap, v18) )
  {
    AslLogCallPrintf(1, "SdbpGetMatchingTextAttributes", 1892, "Failed to read matching text blob");
    goto LABEL_24;
  }
  v20 = SdbFindFirstTag(a1, v9, 16467);
  if ( !v20 )
  {
    AslLogCallPrintf(1, "SdbpGetMatchingTextAttributes", 1901, "Failed to read text encoding");
    goto LABEL_24;
  }
  DWORDTag = SdbReadDWORDTag(a1, v20, 0);
  if ( !DWORDTag )
  {
    AslLogCallPrintf(1, "SdbpGetMatchingTextAttributes", 1907, "Failed to read encoding type");
    goto LABEL_24;
  }
  v22 = SdbFindFirstTag(a1, v9, 16385);
  if ( v22 )
    v8 = SdbReadDWORDTag(a1, v22, 0x2000);
  v11 = 1;
  *a3 = v14;
  *a4 = v7;
  *a5 = v18;
  *a6 = DWORDTag;
  *a7 = v8;
  return v11;
}

```

## disassembly

```asm
0x1800aa444  mov     [rsp+arg_0], rbx
0x1800aa449  mov     [rsp+arg_18], r9
0x1800aa44e  mov     [rsp+arg_10], r8
0x1800aa453  push    rbp
0x1800aa454  push    rsi
0x1800aa455  push    rdi
0x1800aa456  push    r12
0x1800aa458  push    r13
0x1800aa45a  push    r14
0x1800aa45c  push    r15
0x1800aa45e  sub     rsp, 20h
0x1800aa462  mov     rax, [rsp+58h+arg_20]
0x1800aa46a  xor     ebx, ebx
0x1800aa46c  mov     [r8], rbx
0x1800aa46f  mov     r12d, 2000h
0x1800aa475  mov     r8d, 6001h
0x1800aa47b  mov     [r9], rbx
0x1800aa47e  mov     r15d, edx
0x1800aa481  mov     rdi, rcx
0x1800aa484  mov     [rax], ebx
0x1800aa486  mov     r13d, ebx
0x1800aa489  mov     rax, [rsp+58h+arg_28]
0x1800aa491  mov     [rax], ebx
0x1800aa493  mov     rax, [rsp+58h+arg_30]
0x1800aa49b  mov     [rax], r12d
0x1800aa49e  call    SdbFindFirstTag
0x1800aa4a3  test    eax, eax
0x1800aa4a5  jnz     short loc_1800AA4CA
0x1800aa4a7  lea     r9, aFailedToGetMat; "Failed to get MATCHING_TEXT file path"
0x1800aa4ae  mov     r8d, 73Ah
0x1800aa4b4  lea     rdx, aSdbpgetmatchin; "SdbpGetMatchingTextAttributes"
0x1800aa4bb  mov     ecx, 1
0x1800aa4c0  call    AslLogCallPrintf
0x1800aa4c5  jmp     loc_1800AA681
0x1800aa4ca  mov     edx, eax
0x1800aa4cc  mov     rcx, rdi
0x1800aa4cf  call    SdbGetStringTagPtr
0x1800aa4d4  mov     r14, rax
0x1800aa4d7  test    rax, rax
0x1800aa4da  jz      loc_1800AA649
0x1800aa4e0  cmp     [rax], bx
0x1800aa4e3  jz      loc_1800AA649
0x1800aa4e9  mov     r8d, 9013h
0x1800aa4ef  mov     edx, r15d
0x1800aa4f2  mov     rcx, rdi
0x1800aa4f5  call    SdbFindFirstTag
0x1800aa4fa  mov     ebp, eax
0x1800aa4fc  test    eax, eax
0x1800aa4fe  jnz     short loc_1800AA50F
0x1800aa500  lea     r9, aFailedToReadTe_0; "Failed to read text to match"
0x1800aa507  mov     r8d, 74Fh
0x1800aa50d  jmp     short loc_1800AA4B4
0x1800aa50f  mov     edx, ebp
0x1800aa511  mov     rcx, rdi
0x1800aa514  call    SdbGetTagDataSize
0x1800aa519  mov     esi, eax
0x1800aa51b  test    eax, eax
0x1800aa51d  jnz     short loc_1800AA52E
0x1800aa51f  lea     r9, aFailedToGetTex; "Failed to get text to match blob"
0x1800aa526  mov     r8d, 755h
0x1800aa52c  jmp     short loc_1800AA4B4
0x1800aa52e  cmp     esi, 20000000h
0x1800aa534  jnz     short loc_1800AA548
0x1800aa536  lea     r9, aFailedToGetTex_0; "Failed to get text size to match blob"
0x1800aa53d  mov     r8d, 759h
0x1800aa543  jmp     loc_1800AA4B4
0x1800aa548  mov     rcx, gs:60h
0x1800aa551  lea     r8, [rsi+2]; Size
0x1800aa555  mov     edx, 8; Flags
0x1800aa55a  mov     rcx, [rcx+30h]; HeapHandle
0x1800aa55e  call    cs:__imp_RtlAllocateHeap
0x1800aa564  mov     rbx, rax
0x1800aa567  test    rax, rax
0x1800aa56a  jnz     short loc_1800AA57E
0x1800aa56c  lea     r9, aFailedToAlloca; "Failed to allocate memory for text blob"
0x1800aa573  mov     r8d, 75Fh
0x1800aa579  jmp     loc_1800AA4B4
0x1800aa57e  mov     r9d, esi
0x1800aa581  mov     r8, rbx
0x1800aa584  mov     edx, ebp
0x1800aa586  mov     rcx, rdi
0x1800aa589  call    SdbReadBinaryTag
0x1800aa58e  test    eax, eax
0x1800aa590  jnz     short loc_1800AA5A4
0x1800aa592  mov     r8d, 764h
0x1800aa598  lea     r9, aFailedToReadMa_0; "Failed to read matching text blob"
0x1800aa59f  jmp     loc_1800AA656
0x1800aa5a4  mov     r8d, 4053h
0x1800aa5aa  mov     edx, r15d
0x1800aa5ad  mov     rcx, rdi
0x1800aa5b0  call    SdbFindFirstTag
0x1800aa5b5  test    eax, eax
0x1800aa5b7  jnz     short loc_1800AA5CB
0x1800aa5b9  mov     r8d, 76Dh
0x1800aa5bf  lea     r9, aFailedToReadTe; "Failed to read text encoding"
0x1800aa5c6  jmp     loc_1800AA656
0x1800aa5cb  xor     r8d, r8d
0x1800aa5ce  mov     edx, eax
0x1800aa5d0  mov     rcx, rdi
0x1800aa5d3  call    SdbReadDWORDTag
0x1800aa5d8  mov     ebp, eax
0x1800aa5da  test    eax, eax
0x1800aa5dc  jnz     short loc_1800AA5ED
0x1800aa5de  mov     r8d, 773h
0x1800aa5e4  lea     r9, aFailedToReadEn; "Failed to read encoding type"
0x1800aa5eb  jmp     short loc_1800AA656
0x1800aa5ed  mov     r8d, 4001h
0x1800aa5f3  mov     edx, r15d
0x1800aa5f6  mov     rcx, rdi
0x1800aa5f9  call    SdbFindFirstTag
0x1800aa5fe  test    eax, eax
0x1800aa600  jz      short loc_1800AA612
0x1800aa602  mov     r8d, r12d
0x1800aa605  mov     edx, eax
0x1800aa607  mov     rcx, rdi
0x1800aa60a  call    SdbReadDWORDTag
0x1800aa60f  mov     r12d, eax
0x1800aa612  mov     rax, [rsp+58h+arg_10]
0x1800aa617  mov     r13d, 1
0x1800aa61d  mov     [rax], r14
0x1800aa620  mov     rax, [rsp+58h+arg_18]
0x1800aa625  mov     [rax], rbx
0x1800aa628  mov     rax, [rsp+58h+arg_20]
0x1800aa630  mov     [rax], esi
0x1800aa632  mov     rax, [rsp+58h+arg_28]
0x1800aa63a  mov     [rax], ebp
0x1800aa63c  mov     rax, [rsp+58h+arg_30]
0x1800aa644  mov     [rax], r12d
0x1800aa647  jmp     short loc_1800AA681
0x1800aa649  mov     r8d, 746h
0x1800aa64f  lea     r9, aFailedToReadMa_3; "Failed to read MATCHING_TEXT file path"
0x1800aa656  lea     rdx, aSdbpgetmatchin; "SdbpGetMatchingTextAttributes"
0x1800aa65d  mov     ecx, 1
0x1800aa662  call    AslLogCallPrintf
0x1800aa667  test    rbx, rbx
0x1800aa66a  jz      short loc_1800AA681
0x1800aa66c  mov     rcx, gs:60h
0x1800aa675  mov     rdx, rbx
0x1800aa678  mov     rcx, [rcx+30h]
0x1800aa67c  call    AslFree
0x1800aa681  mov     rbx, [rsp+58h+arg_0]
0x1800aa686  mov     eax, r13d
0x1800aa689  add     rsp, 20h
0x1800aa68d  pop     r15
0x1800aa68f  pop     r14
0x1800aa691  pop     r13
0x1800aa693  pop     r12
0x1800aa695  pop     rdi
0x1800aa696  pop     rsi
0x1800aa697  pop     rbp
0x1800aa698  retn
```
