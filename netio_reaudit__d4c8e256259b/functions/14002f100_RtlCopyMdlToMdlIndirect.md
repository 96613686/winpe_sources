# RtlCopyMdlToMdlIndirect

- ea: `0x14002f100`
- end: `0x14002f45f`
- name: `RtlCopyMdlToMdlIndirect`
- size: `863`
- prototype: `__int64 __fastcall(int, int, int, int, size_t Size, char, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14002f100`
- `0x14002f468`
- `0x140078100`

## import_xrefs

- `ntoskrnl!RtlPrefetchMemoryNonTemporal` at `0x14002f430`
- `ntoskrnl!RtlPrefetchMemoryNonTemporal` at `0x14002f44e`
- `ntoskrnl!RtlPrefetchMemoryNonTemporal` at `0x14002f430`
- `ntoskrnl!RtlPrefetchMemoryNonTemporal` at `0x14002f44e`
- `ntoskrnl!KeLowerIrql` at `0x14002f2de`
- `ntoskrnl!KeLowerIrql` at `0x14002f2de`
- `ntoskrnl!KfRaiseIrql` at `0x14002f28e`
- `ntoskrnl!KfRaiseIrql` at `0x14002f28e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002f383`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002f3b2`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002f3e6`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002f40f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002f383`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002f3b2`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002f3e6`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002f40f`

## pseudocode

```c
_QWORD *__fastcall RtlCopyMdlToMdlIndirect(
        PMDL *a1,
        _DWORD *a2,
        struct _MDL **a3,
        _DWORD *a4,
        size_t Size,
        char a6,
        _QWORD *a7)
{
  PMDL v7; // rcx
  size_t v10; // rsi
  size_t ByteCount; // r12
  char *MappedSystemVa; // rax
  char *v13; // rdi
  struct _MDL *v14; // rcx
  unsigned int v15; // ebp
  char *v16; // r14
  size_t v17; // rbx
  __int64 v18; // r15
  struct _MDL *Next; // rcx
  struct _MDL **v20; // r15
  _QWORD *result; // rax
  KIRQL v22; // di
  struct _MDL *v23; // rcx
  SIZE_T v24; // rdx
  SIZE_T v25; // rdx
  _DWORD *v27; // [rsp+88h] [rbp+10h]
  char *v29; // [rsp+98h] [rbp+20h]

  v27 = a2;
  v7 = *a1;
  v10 = Size;
  LODWORD(ByteCount) = v7->ByteCount - *a2;
  if ( (v7->MdlFlags & 5) != 0 )
  {
    MappedSystemVa = (char *)v7->MappedSystemVa;
  }
  else
  {
    MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(v7, 0, MmCached, 0, 0, 0x40000000u);
    a2 = v27;
  }
  if ( MappedSystemVa )
  {
    v13 = &MappedSystemVa[*a2];
    v29 = v13;
    if ( a6 )
    {
      v25 = (unsigned int)ByteCount;
      if ( Size < (unsigned int)ByteCount )
        v25 = Size;
      RtlPrefetchMemoryNonTemporal(v13, v25);
    }
  }
  else
  {
    v13 = 0;
    v29 = 0;
  }
  v14 = *a3;
  v15 = (*a3)->ByteCount - *a4;
  if ( ((*a3)->MdlFlags & 5) != 0 )
    v16 = (char *)v14->MappedSystemVa;
  else
    v16 = (char *)MmMapLockedPagesSpecifyCache(v14, 0, MmCached, 0, 0, 0x40000000u);
  if ( v16 )
    v16 += (unsigned int)*a4;
  do
  {
    v17 = v15;
    if ( v15 >= (unsigned int)ByteCount )
      v17 = (unsigned int)ByteCount;
    if ( v17 > v10 )
      LODWORD(v17) = v10;
    if ( v13 && v16 )
    {
      v18 = (unsigned int)v17;
      memmove(v16, v13, (unsigned int)v17);
    }
    else
    {
      v22 = KfRaiseIrql(2u);
      v18 = (unsigned int)v17;
      RtlCopyMdlToMdlWithReservedMappingAtDpcLevel(*a1, (unsigned int)v17, a6);
      KeLowerIrql(v22);
      v13 = v29;
    }
    v10 -= v18;
    if ( (_DWORD)ByteCount == (_DWORD)v17 )
    {
      *v27 = 0;
      while ( 1 )
      {
        Next = (*a1)->Next;
        *a1 = Next;
        if ( !Next )
          break;
        ByteCount = Next->ByteCount;
        if ( (_DWORD)ByteCount )
        {
          if ( v10 )
          {
            v13 = (char *)((Next->MdlFlags & 5) != 0
                         ? Next->MappedSystemVa
                         : MmMapLockedPagesSpecifyCache(Next, 0, MmCached, 0, 0, 0x40000000u));
            v29 = v13;
            if ( v13 )
            {
              if ( a6 )
              {
                v24 = ByteCount;
                if ( v10 < ByteCount )
                  v24 = v10;
                RtlPrefetchMemoryNonTemporal(v13, v24);
              }
            }
          }
          break;
        }
      }
    }
    else
    {
      if ( v13 )
      {
        v13 += v18;
        v29 = v13;
      }
      *v27 += v17;
      LODWORD(ByteCount) = ByteCount - v17;
    }
    if ( v15 == (_DWORD)v17 )
    {
      v20 = a3;
      *a4 = 0;
      while ( 1 )
      {
        v23 = (*a3)->Next;
        *a3 = v23;
        if ( !v23 )
          break;
        v15 = v23->ByteCount;
        if ( v15 )
        {
          if ( !v10 )
            goto LABEL_33;
          if ( (v23->MdlFlags & 5) != 0 )
            v16 = (char *)v23->MappedSystemVa;
          else
            v16 = (char *)MmMapLockedPagesSpecifyCache(v23, 0, MmCached, 0, 0, 0x40000000u);
          goto LABEL_31;
        }
      }
    }
    else
    {
      if ( v16 )
        v16 += v18;
      *a4 += v17;
      v15 -= v17;
    }
    if ( !v10 )
      break;
    v20 = a3;
LABEL_31:
    ;
  }
  while ( *v20 && *a1 );
LABEL_33:
  result = a7;
  *a7 = Size - v10;
  return result;
}

```

## disassembly

```asm
0x14002f100  mov     [rsp+arg_10], r8
0x14002f105  mov     [rsp+arg_8], rdx
0x14002f10a  mov     [rsp+arg_0], rcx
0x14002f10f  push    rbx
0x14002f110  push    rbp
0x14002f111  push    rsi
0x14002f112  push    rdi
0x14002f113  push    r12
0x14002f115  push    r13
0x14002f117  push    r14
0x14002f119  push    r15
0x14002f11b  sub     rsp, 38h
0x14002f11f  mov     rcx, [rcx]; MemoryDescriptorList
0x14002f122  mov     r13, r9
0x14002f125  mov     rbx, [rsp+78h+Size]
0x14002f12d  mov     r15, r8
0x14002f130  mov     rsi, rbx
0x14002f133  mov     r12d, [rcx+28h]
0x14002f137  sub     r12d, [rdx]
0x14002f13a  test    byte ptr [rcx+0Ah], 5
0x14002f13e  jz      loc_14002F397
0x14002f144  mov     rax, [rcx+18h]
0x14002f148  test    rax, rax
0x14002f14b  jz      loc_14002F319
0x14002f151  mov     edi, [rdx]
0x14002f153  add     rdi, rax
0x14002f156  cmp     [rsp+78h+arg_28], 0
0x14002f15e  mov     [rsp+78h+arg_18], rdi
0x14002f166  jnz     loc_14002F441
0x14002f16c  mov     rcx, [r15]; MemoryDescriptorList
0x14002f16f  mov     ebp, [rcx+28h]
0x14002f172  sub     ebp, [r13+0]
0x14002f176  test    byte ptr [rcx+0Ah], 5
0x14002f17a  jz      loc_14002F3CB
0x14002f180  mov     r14, [rcx+18h]
0x14002f184  test    r14, r14
0x14002f187  jz      short loc_14002F190
0x14002f189  mov     ecx, [r13+0]
0x14002f18d  add     r14, rcx
0x14002f190  cmp     ebp, r12d
0x14002f193  mov     ebx, ebp
0x14002f195  cmovnb  ebx, r12d
0x14002f199  cmp     rbx, rsi
0x14002f19c  cmova   ebx, esi
0x14002f19f  test    rdi, rdi
0x14002f1a2  jz      loc_14002F28C
0x14002f1a8  test    r14, r14
0x14002f1ab  jz      loc_14002F28C
0x14002f1b1  mov     r8d, ebx; Size
0x14002f1b4  mov     rdx, rdi; Src
0x14002f1b7  mov     rcx, r14; void *
0x14002f1ba  mov     r15d, ebx
0x14002f1bd  call    memmove
0x14002f1c2  sub     rsi, r15
0x14002f1c5  cmp     r12d, ebx
0x14002f1c8  jnz     loc_14002F2F7
0x14002f1ce  mov     rax, [rsp+78h+arg_8]
0x14002f1d6  xor     r8d, r8d
0x14002f1d9  mov     rdx, [rsp+78h+arg_0]
0x14002f1e1  mov     [rax], r8d
0x14002f1e4  mov     rax, [rdx]
0x14002f1e7  mov     rcx, [rax]; MemoryDescriptorList
0x14002f1ea  mov     [rdx], rcx
0x14002f1ed  test    rcx, rcx
0x14002f1f0  jz      short loc_14002F229
0x14002f1f2  mov     r12d, [rcx+28h]
0x14002f1f6  test    r12d, r12d
0x14002f1f9  jz      short loc_14002F1E4
0x14002f1fb  test    rsi, rsi
0x14002f1fe  jz      short loc_14002F229
0x14002f200  test    byte ptr [rcx+0Ah], 5
0x14002f204  jz      loc_14002F36B
0x14002f20a  mov     rdi, [rcx+18h]
0x14002f20e  mov     [rsp+78h+arg_18], rdi
0x14002f216  test    rdi, rdi
0x14002f219  jz      short loc_14002F229
0x14002f21b  cmp     [rsp+78h+arg_28], 0
0x14002f223  jnz     loc_14002F423
0x14002f229  cmp     ebp, ebx
0x14002f22b  jz      loc_14002F328
0x14002f231  test    r14, r14
0x14002f234  jz      short loc_14002F239
0x14002f236  add     r14, r15
0x14002f239  add     [r13+0], ebx
0x14002f23d  sub     ebp, ebx
0x14002f23f  test    rsi, rsi
0x14002f242  jz      short loc_14002F264
0x14002f244  mov     r15, [rsp+78h+arg_10]
0x14002f24c  cmp     qword ptr [r15], 0
0x14002f250  jz      short loc_14002F264
0x14002f252  mov     rax, [rsp+78h+arg_0]
0x14002f25a  cmp     qword ptr [rax], 0
0x14002f25e  jnz     loc_14002F190
0x14002f264  mov     rax, [rsp+78h+arg_30]
0x14002f26c  mov     rcx, [rsp+78h+Size]
0x14002f274  sub     rcx, rsi
0x14002f277  mov     [rax], rcx
0x14002f27a  add     rsp, 38h
0x14002f27e  pop     r15
0x14002f280  pop     r14
0x14002f282  pop     r13
0x14002f284  pop     r12
0x14002f286  pop     rdi
0x14002f287  pop     rsi
0x14002f288  pop     rbp
0x14002f289  pop     rbx
0x14002f28a  retn
0x14002f28c  mov     cl, 2; NewIrql
0x14002f28e  call    cs:__imp_KfRaiseIrql
0x14002f295  nop     dword ptr [rax+rax+00h]
0x14002f29a  mov     r8, [rsp+78h+arg_10]
0x14002f2a2  movzx   edi, al
0x14002f2a5  mov     rax, [rsp+78h+arg_8]
0x14002f2ad  mov     rcx, [rsp+78h+arg_0]
0x14002f2b5  mov     r9d, [r13+0]
0x14002f2b9  mov     r8, [r8]
0x14002f2bc  mov     edx, [rax]
0x14002f2be  movzx   eax, [rsp+78h+arg_28]
0x14002f2c6  mov     rcx, [rcx]; SourceMdl
0x14002f2c9  mov     byte ptr [rsp+78h+Priority], al; char
0x14002f2cd  mov     r15d, ebx
0x14002f2d0  mov     qword ptr [rsp+78h+BugCheckOnFailure], r15; __int64
0x14002f2d5  call    RtlCopyMdlToMdlWithReservedMappingAtDpcLevel
0x14002f2da  movzx   ecx, dil; NewIrql
0x14002f2de  call    cs:__imp_KeLowerIrql
0x14002f2e5  nop     dword ptr [rax+rax+00h]
0x14002f2ea  mov     rdi, [rsp+78h+arg_18]
0x14002f2f2  jmp     loc_14002F1C2
0x14002f2f7  test    rdi, rdi
0x14002f2fa  jz      short loc_14002F307
0x14002f2fc  add     rdi, r15
0x14002f2ff  mov     [rsp+78h+arg_18], rdi
0x14002f307  mov     rax, [rsp+78h+arg_8]
0x14002f30f  add     [rax], ebx
0x14002f311  sub     r12d, ebx
0x14002f314  jmp     loc_14002F229
0x14002f319  xor     edi, edi
0x14002f31b  mov     [rsp+78h+arg_18], rdi
0x14002f323  jmp     loc_14002F16C
0x14002f328  mov     r15, [rsp+78h+arg_10]
0x14002f330  xor     edx, edx; AccessMode
0x14002f332  mov     [r13+0], edx
0x14002f336  mov     rax, [r15]
0x14002f339  mov     rcx, [rax]; MemoryDescriptorList
0x14002f33c  mov     [r15], rcx
0x14002f33f  test    rcx, rcx
0x14002f342  jz      loc_14002F23F
0x14002f348  mov     ebp, [rcx+28h]
0x14002f34b  test    ebp, ebp
0x14002f34d  jz      short loc_14002F336
0x14002f34f  test    rsi, rsi
0x14002f352  jz      loc_14002F264
0x14002f358  test    byte ptr [rcx+0Ah], 5
0x14002f35c  jz      loc_14002F3FA
0x14002f362  mov     r14, [rcx+18h]
0x14002f366  jmp     loc_14002F24C
0x14002f36b  mov     [rsp+78h+Priority], 40000000h; Priority
0x14002f373  xor     r9d, r9d; RequestedAddress
0x14002f376  mov     [rsp+78h+BugCheckOnFailure], r8d; BugCheckOnFailure
0x14002f37b  xor     edx, edx; AccessMode
0x14002f37d  mov     r8d, 1; CacheType
0x14002f383  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14002f38a  nop     dword ptr [rax+rax+00h]
0x14002f38f  mov     rdi, rax
0x14002f392  jmp     loc_14002F20E
0x14002f397  mov     [rsp+78h+Priority], 40000000h; Priority
0x14002f39f  xor     r9d, r9d; RequestedAddress
0x14002f3a2  xor     edx, edx; AccessMode
0x14002f3a4  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14002f3ac  mov     r8d, 1; CacheType
0x14002f3b2  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14002f3b9  nop     dword ptr [rax+rax+00h]
0x14002f3be  mov     rdx, [rsp+78h+arg_8]
0x14002f3c6  jmp     loc_14002F148
0x14002f3cb  mov     [rsp+78h+Priority], 40000000h; Priority
0x14002f3d3  xor     r9d, r9d; RequestedAddress
0x14002f3d6  xor     edx, edx; AccessMode
0x14002f3d8  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14002f3e0  mov     r8d, 1; CacheType
0x14002f3e6  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14002f3ed  nop     dword ptr [rax+rax+00h]
0x14002f3f2  mov     r14, rax
0x14002f3f5  jmp     loc_14002F184
0x14002f3fa  mov     [rsp+78h+Priority], 40000000h; Priority
0x14002f402  xor     r9d, r9d; RequestedAddress
0x14002f405  mov     r8d, 1; CacheType
0x14002f40b  mov     [rsp+78h+BugCheckOnFailure], edx; BugCheckOnFailure
0x14002f40f  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14002f416  nop     dword ptr [rax+rax+00h]
0x14002f41b  mov     r14, rax
0x14002f41e  jmp     loc_14002F24C
0x14002f423  cmp     rsi, r12
0x14002f426  mov     rdx, r12
0x14002f429  mov     rcx, rdi; Source
0x14002f42c  cmovb   rdx, rsi; Length
0x14002f430  call    cs:__imp_RtlPrefetchMemoryNonTemporal
0x14002f437  nop     dword ptr [rax+rax+00h]
0x14002f43c  jmp     loc_14002F229
0x14002f441  mov     edx, r12d
0x14002f444  mov     rcx, rdi; Source
0x14002f447  cmp     rbx, rdx
0x14002f44a  cmovb   rdx, rbx; Length
0x14002f44e  call    cs:__imp_RtlPrefetchMemoryNonTemporal
0x14002f455  nop     dword ptr [rax+rax+00h]
0x14002f45a  jmp     loc_14002F16C
```
