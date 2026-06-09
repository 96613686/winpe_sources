# RtlCopyMdlToMdl

- ea: `0x140047a60`
- end: `0x140047db4`
- name: `RtlCopyMdlToMdl`
- size: `852`
- prototype: `__int64 __usercall@<rax>(PMDL SourceMdl@<rcx>, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14002f468`
- `0x140047a60`
- `0x140077fd0`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x140047bf9`
- `ntoskrnl!KeLowerIrql` at `0x140047bf9`
- `ntoskrnl!KfRaiseIrql` at `0x140047bc8`
- `ntoskrnl!KfRaiseIrql` at `0x140047bc8`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140047b29`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140047b75`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140047c85`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140047d0f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140047b29`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140047b75`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140047c85`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140047d0f`

## pseudocode

```c
unsigned __int64 *__fastcall RtlCopyMdlToMdl(
        PMDL SourceMdl,
        unsigned __int64 a2,
        struct _MDL *a3,
        unsigned __int64 a4,
        unsigned __int64 a5,
        unsigned __int64 *a6)
{
  struct _MDL *v7; // rbx
  PMDL i; // rsi
  unsigned __int64 ByteCount; // rax
  unsigned __int64 v11; // rax
  ULONG v12; // eax
  char *MappedSystemVa; // rax
  char *v14; // rcx
  ULONG v15; // ebp
  char *v16; // rax
  char *v17; // rdi
  ULONG v18; // edx
  ULONG v19; // r15d
  __int64 v20; // r13
  KIRQL v21; // di
  unsigned __int64 v22; // r8
  unsigned __int64 v23; // rcx
  char *v24; // rax
  char *v25; // rax
  char *v26; // rax
  unsigned __int64 *result; // rax
  unsigned __int64 v28; // rcx
  char *v29; // [rsp+30h] [rbp-48h]
  unsigned __int64 v30; // [rsp+38h] [rbp-40h]
  ULONG Size; // [rsp+80h] [rbp+8h]
  char *v32; // [rsp+90h] [rbp+18h]

  v7 = a3;
  for ( i = SourceMdl; i; a2 -= ByteCount )
  {
    ByteCount = i->ByteCount;
    if ( a2 < ByteCount )
      break;
    i = i->Next;
  }
  if ( a3 )
  {
    do
    {
      v11 = v7->ByteCount;
      if ( a4 < v11 )
        break;
      v7 = v7->Next;
      a4 -= v11;
    }
    while ( v7 );
  }
  if ( a5 && i && v7 )
  {
    v12 = a5;
    if ( (unsigned int)(i->ByteCount - a2) <= a5 )
      v12 = i->ByteCount - a2;
    v30 = a5;
    Size = v12;
    if ( (i->MdlFlags & 5) != 0 )
      MappedSystemVa = (char *)i->MappedSystemVa;
    else
      MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(i, 0, MmCached, 0, 0, 0x40000000u);
    v14 = &MappedSystemVa[a2];
    if ( !MappedSystemVa )
      v14 = 0;
    v15 = v7->ByteCount - a4;
    v32 = v14;
    if ( (v7->MdlFlags & 5) != 0 )
    {
      v16 = (char *)v7->MappedSystemVa;
    }
    else
    {
      v16 = (char *)MmMapLockedPagesSpecifyCache(v7, 0, MmCached, 0, 0, 0x40000000u);
      v14 = v32;
    }
    v17 = &v16[a4];
    if ( !v16 )
      v17 = 0;
LABEL_22:
    v29 = v17;
LABEL_23:
    v18 = Size;
    while ( 1 )
    {
      v19 = v15;
      if ( v15 >= v18 )
        v19 = v18;
      if ( v14 && v17 )
      {
        v20 = v19;
        RtlCopyVolatileMemory(v17, v14, v19);
      }
      else
      {
        v20 = v19;
        v21 = KfRaiseIrql(2u);
        RtlCopyMdlToMdlWithReservedMappingAtDpcLevel(i, v19, 0);
        KeLowerIrql(v21);
        v17 = v29;
      }
      if ( v30 == v20 )
        break;
      v22 = v30 - v20;
      v30 -= v20;
      if ( Size == v19 )
      {
        while ( 1 )
        {
          i = i->Next;
          if ( !i )
            goto LABEL_51;
          v23 = i->ByteCount;
          if ( (_DWORD)v23 )
          {
            a2 = 0;
            v18 = v22;
            if ( v23 <= v22 )
              v18 = i->ByteCount;
            Size = v18;
            if ( (i->MdlFlags & 5) != 0 )
            {
              v14 = (char *)i->MappedSystemVa;
              v32 = v14;
              goto LABEL_42;
            }
            v24 = (char *)MmMapLockedPagesSpecifyCache(i, 0, MmCached, 0, 0, 0x40000000u);
            v18 = Size;
            v22 = v30;
            goto LABEL_41;
          }
        }
      }
      v18 = Size - v19;
      a2 += v20;
      Size -= v19;
      v24 = &v32[v20];
      if ( !v32 )
        v24 = 0;
LABEL_41:
      v32 = v24;
      v14 = v24;
LABEL_42:
      if ( v15 == v19 )
      {
        while ( 1 )
        {
          v7 = v7->Next;
          if ( !v7 )
            break;
          v15 = v7->ByteCount;
          if ( v15 )
          {
            a4 = 0;
            if ( (v7->MdlFlags & 5) != 0 )
            {
              v17 = (char *)v7->MappedSystemVa;
              goto LABEL_22;
            }
            v25 = (char *)MmMapLockedPagesSpecifyCache(v7, 0, MmCached, 0, 0, 0x40000000u);
            v14 = v32;
            v17 = v25;
            v29 = v25;
            goto LABEL_23;
          }
        }
LABEL_51:
        result = a6;
        v28 = a5 - v22;
        goto LABEL_52;
      }
      v26 = &v17[v20];
      a4 += v20;
      v15 -= v19;
      if ( !v17 )
        v26 = 0;
      v17 = v26;
      v29 = v26;
    }
    result = a6;
    v28 = a5;
LABEL_52:
    *result = v28;
  }
  else
  {
    result = a6;
    *a6 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140047a60  push    rbx
0x140047a62  push    rsi
0x140047a63  push    r12
0x140047a65  push    r14
0x140047a67  sub     rsp, 58h
0x140047a6b  mov     r14, r9
0x140047a6e  mov     rbx, r8
0x140047a71  mov     r12, rdx
0x140047a74  mov     rsi, rcx
0x140047a77  test    rcx, rcx
0x140047a7a  jz      short loc_140047A93
0x140047a7c  nop     dword ptr [rax+00h]
0x140047a80  mov     eax, [rsi+28h]
0x140047a83  cmp     r12, rax
0x140047a86  jb      short loc_140047A93
0x140047a88  mov     rsi, [rsi]
0x140047a8b  sub     r12, rax
0x140047a8e  test    rsi, rsi
0x140047a91  jnz     short loc_140047A80
0x140047a93  test    rbx, rbx
0x140047a96  jz      short loc_140047AAB
0x140047a98  mov     eax, [rbx+28h]
0x140047a9b  cmp     r14, rax
0x140047a9e  jb      short loc_140047AAB
0x140047aa0  mov     rbx, [rbx]
0x140047aa3  sub     r14, rax
0x140047aa6  test    rbx, rbx
0x140047aa9  jnz     short loc_140047A98
0x140047aab  mov     rdx, [rsp+78h+arg_20]
0x140047ab3  test    rdx, rdx
0x140047ab6  jz      loc_140047D99
0x140047abc  test    rsi, rsi
0x140047abf  jz      loc_140047D99
0x140047ac5  test    rbx, rbx
0x140047ac8  jz      loc_140047D99
0x140047ace  mov     ecx, [rsi+28h]
0x140047ad1  mov     eax, edx
0x140047ad3  sub     ecx, r12d
0x140047ad6  mov     [rsp+78h+arg_8], rbp
0x140047ade  cmp     rcx, rdx
0x140047ae1  mov     [rsp+78h+var_28], rdi
0x140047ae6  mov     [rsp+78h+var_30], r13
0x140047aeb  cmovbe  eax, ecx
0x140047aee  mov     [rsp+78h+var_38], r15
0x140047af3  xor     r13d, r13d
0x140047af6  mov     [rsp+78h+var_40], rdx
0x140047afb  test    byte ptr [rsi+0Ah], 5
0x140047aff  mov     dword ptr [rsp+78h+Size], eax
0x140047b06  jz      short loc_140047B0E
0x140047b08  mov     rax, [rsi+18h]
0x140047b0c  jmp     short loc_140047B35
0x140047b0e  mov     [rsp+78h+Priority], 40000000h; Priority
0x140047b16  xor     r9d, r9d; RequestedAddress
0x140047b19  xor     edx, edx; AccessMode
0x140047b1b  mov     [rsp+78h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x140047b20  mov     r8d, 1; CacheType
0x140047b26  mov     rcx, rsi; MemoryDescriptorList
0x140047b29  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140047b30  nop     dword ptr [rax+rax+00h]
0x140047b35  mov     ebp, [rbx+28h]
0x140047b38  lea     rcx, [rax+r12]
0x140047b3c  test    rax, rax
0x140047b3f  cmovz   rcx, rax
0x140047b43  sub     ebp, r14d
0x140047b46  test    byte ptr [rbx+0Ah], 5
0x140047b4a  mov     [rsp+78h+arg_10], rcx
0x140047b52  jz      short loc_140047B5A
0x140047b54  mov     rax, [rbx+18h]
0x140047b58  jmp     short loc_140047B89
0x140047b5a  mov     [rsp+78h+Priority], 40000000h; Priority
0x140047b62  xor     r9d, r9d; RequestedAddress
0x140047b65  xor     edx, edx; AccessMode
0x140047b67  mov     [rsp+78h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x140047b6c  mov     r8d, 1; CacheType
0x140047b72  mov     rcx, rbx; MemoryDescriptorList
0x140047b75  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140047b7c  nop     dword ptr [rax+rax+00h]
0x140047b81  mov     rcx, [rsp+78h+arg_10]
0x140047b89  test    rax, rax
0x140047b8c  lea     rdi, [rax+r14]
0x140047b90  cmovz   rdi, rax
0x140047b94  mov     [rsp+78h+var_48], rdi
0x140047b99  mov     edx, dword ptr [rsp+78h+Size]
0x140047ba0  cmp     ebp, edx
0x140047ba2  mov     r15d, ebp
0x140047ba5  cmovnb  r15d, edx
0x140047ba9  test    rcx, rcx
0x140047bac  jz      short loc_140047BC6
0x140047bae  test    rdi, rdi
0x140047bb1  jz      short loc_140047BC6
0x140047bb3  mov     rdx, rcx; Src
0x140047bb6  mov     r8d, r15d; Size
0x140047bb9  mov     rcx, rdi; void *
0x140047bbc  mov     r13d, r15d
0x140047bbf  call    RtlCopyVolatileMemory
0x140047bc4  jmp     short loc_140047C0A
0x140047bc6  mov     cl, 2; NewIrql
0x140047bc8  call    cs:__imp_KfRaiseIrql
0x140047bcf  nop     dword ptr [rax+rax+00h]
0x140047bd4  mov     r13d, r15d
0x140047bd7  mov     r9, r14
0x140047bda  mov     r8, rbx
0x140047bdd  mov     byte ptr [rsp+78h+Priority], 0; char
0x140047be2  mov     rdx, r12
0x140047be5  mov     qword ptr [rsp+78h+BugCheckOnFailure], r13; __int64
0x140047bea  mov     rcx, rsi; SourceMdl
0x140047bed  movzx   edi, al
0x140047bf0  call    RtlCopyMdlToMdlWithReservedMappingAtDpcLevel
0x140047bf5  movzx   ecx, dil; NewIrql
0x140047bf9  call    cs:__imp_KeLowerIrql
0x140047c00  nop     dword ptr [rax+rax+00h]
0x140047c05  mov     rdi, [rsp+78h+var_48]
0x140047c0a  mov     r8, [rsp+78h+var_40]
0x140047c0f  cmp     r8, r13
0x140047c12  jz      loc_140047D87
0x140047c18  mov     edx, dword ptr [rsp+78h+Size]
0x140047c1f  sub     r8, r13
0x140047c22  mov     [rsp+78h+var_40], r8
0x140047c27  cmp     edx, r15d
0x140047c2a  jnz     short loc_140047C9F
0x140047c2c  nop     dword ptr [rax+00h]
0x140047c30  mov     rsi, [rsi]
0x140047c33  test    rsi, rsi
0x140047c36  jz      loc_140047D4E
0x140047c3c  mov     ecx, [rsi+28h]
0x140047c3f  test    ecx, ecx
0x140047c41  jz      short loc_140047C30
0x140047c43  xor     r12d, r12d
0x140047c46  mov     edx, r8d
0x140047c49  cmp     rcx, r8
0x140047c4c  cmovbe  edx, ecx
0x140047c4f  test    byte ptr [rsi+0Ah], 5
0x140047c53  mov     dword ptr [rsp+78h+Size], edx
0x140047c5a  jz      short loc_140047C6A
0x140047c5c  mov     rcx, [rsi+18h]
0x140047c60  mov     [rsp+78h+arg_10], rcx
0x140047c68  jmp     short loc_140047CCA
0x140047c6a  mov     [rsp+78h+Priority], 40000000h; Priority
0x140047c72  xor     r9d, r9d; RequestedAddress
0x140047c75  xor     edx, edx; AccessMode
0x140047c77  mov     [rsp+78h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x140047c7c  mov     r8d, 1; CacheType
0x140047c82  mov     rcx, rsi; MemoryDescriptorList
0x140047c85  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140047c8c  nop     dword ptr [rax+rax+00h]
0x140047c91  mov     edx, dword ptr [rsp+78h+Size]
0x140047c98  mov     r8, [rsp+78h+var_40]
0x140047c9d  jmp     short loc_140047CBF
0x140047c9f  mov     rcx, [rsp+78h+arg_10]
0x140047ca7  sub     edx, r15d
0x140047caa  add     r12, r13
0x140047cad  mov     dword ptr [rsp+78h+Size], edx
0x140047cb4  test    rcx, rcx
0x140047cb7  lea     rax, [rcx+r13]
0x140047cbb  cmovz   rax, rcx
0x140047cbf  mov     [rsp+78h+arg_10], rax
0x140047cc7  mov     rcx, rax
0x140047cca  cmp     ebp, r15d
0x140047ccd  jnz     short loc_140047D30
0x140047ccf  nop
0x140047cd0  mov     rbx, [rbx]
0x140047cd3  test    rbx, rbx
0x140047cd6  jz      short loc_140047D4E
0x140047cd8  mov     ebp, [rbx+28h]
0x140047cdb  test    ebp, ebp
0x140047cdd  jz      short loc_140047CD0
0x140047cdf  xor     r13d, r13d
0x140047ce2  test    byte ptr [rbx+0Ah], 5
0x140047ce6  mov     r14d, r13d
0x140047ce9  jz      short loc_140047CF4
0x140047ceb  mov     rdi, [rbx+18h]
0x140047cef  jmp     loc_140047B94
0x140047cf4  mov     [rsp+78h+Priority], 40000000h; Priority
0x140047cfc  xor     r9d, r9d; RequestedAddress
0x140047cff  xor     edx, edx; AccessMode
0x140047d01  mov     [rsp+78h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x140047d06  mov     r8d, 1; CacheType
0x140047d0c  mov     rcx, rbx; MemoryDescriptorList
0x140047d0f  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140047d16  nop     dword ptr [rax+rax+00h]
0x140047d1b  mov     rcx, [rsp+78h+arg_10]
0x140047d23  mov     rdi, rax
0x140047d26  mov     [rsp+78h+var_48], rax
0x140047d2b  jmp     loc_140047B99
0x140047d30  lea     rax, [rdi+r13]
0x140047d34  add     r14, r13
0x140047d37  sub     ebp, r15d
0x140047d3a  test    rdi, rdi
0x140047d3d  cmovz   rax, rdi
0x140047d41  mov     rdi, rax
0x140047d44  mov     [rsp+78h+var_48], rax
0x140047d49  jmp     loc_140047BA0
0x140047d4e  mov     rcx, [rsp+78h+arg_20]
0x140047d56  mov     rax, [rsp+78h+arg_28]
0x140047d5e  sub     rcx, r8
0x140047d61  mov     [rax], rcx
0x140047d64  mov     r13, [rsp+78h+var_30]
0x140047d69  mov     rdi, [rsp+78h+var_28]
0x140047d6e  mov     rbp, [rsp+78h+arg_8]
0x140047d76  mov     r15, [rsp+78h+var_38]
0x140047d7b  add     rsp, 58h
0x140047d7f  pop     r14
0x140047d81  pop     r12
0x140047d83  pop     rsi
0x140047d84  pop     rbx
0x140047d85  retn
0x140047d87  mov     rax, [rsp+78h+arg_28]
0x140047d8f  mov     rcx, [rsp+78h+arg_20]
0x140047d97  jmp     short loc_140047D61
0x140047d99  mov     rax, [rsp+78h+arg_28]
0x140047da1  mov     qword ptr [rax], 0
0x140047da8  add     rsp, 58h
0x140047dac  pop     r14
0x140047dae  pop     r12
0x140047db0  pop     rsi
0x140047db1  pop     rbx
0x140047db2  retn
```
