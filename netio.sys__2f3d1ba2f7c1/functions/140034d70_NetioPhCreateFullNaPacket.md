# NetioPhCreateFullNaPacket

- ea: `0x140034d70`
- end: `0x140034f51`
- name: `NetioPhCreateFullNaPacket`
- size: `481`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140034d70`
- `0x140034f60`
- `0x140035450`
- `0x1400354c0`
- `0x140078100`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140034ee9`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140034f13`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140034ee9`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140034f13`

## pseudocode

```c
__int64 __fastcall NetioPhCreateFullNaPacket(
        __int64 a1,
        unsigned int a2,
        _OWORD *a3,
        const void *a4,
        _OWORD *a5,
        void *Src,
        char a7,
        char a8,
        char a9,
        char a10,
        __int64 *a11)
{
  size_t v13; // rbx
  ULONG v14; // r15d
  __int16 v15; // si
  __int64 result; // rax
  struct _NET_BUFFER_LIST *v17; // rcx
  __int64 v18; // rbx
  __int64 v19; // rcx
  char *v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rdi
  __int64 v23; // rcx
  char *v24; // rax
  char *v25; // rdi

  v13 = a2;
  v14 = a1;
  if ( !Src || (v15 = a2 + 26, !a2) )
    v15 = 24;
  if ( a10 && (!Src || !a4) )
    return 3221225485LL;
  result = NetioPhCreateNaPacket(a1, a2, a5, Src, a7, a8, a9, a3, a11);
  if ( (int)result >= 0 )
  {
    v17 = (struct _NET_BUFFER_LIST *)*a11;
    if ( a10 )
    {
      NetioRetreatNetBufferList(v17);
      v22 = *(_QWORD *)(*a11 + 8);
      v23 = *(_QWORD *)(v22 + 8);
      if ( (*(_BYTE *)(v23 + 10) & 5) != 0 )
        v24 = *(char **)(v23 + 24);
      else
        v24 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v23, 0, MmCached, 0, 0, 0x40000000u);
      v25 = &v24[*(unsigned int *)(v22 + 16)];
      memmove(v25, a4, v13);
      memmove(v25 + 6, Src, v13);
      *((_WORD *)v25 + 6) = -8826;
      NetioAdvanceNetBufferList(*a11, v14);
    }
    else
    {
      NetioRetreatNetBufferList(v17);
    }
    v18 = *(_QWORD *)(*a11 + 8);
    v19 = *(_QWORD *)(v18 + 8);
    if ( (*(_BYTE *)(v19 + 10) & 5) != 0 )
      v20 = *(char **)(v19 + 24);
    else
      v20 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v19, 0, MmCached, 0, 0, 0x40000000u);
    v21 = *(unsigned int *)(v18 + 16);
    *(_DWORD *)&v20[v21] = 96;
    *(_WORD *)&v20[v21 + 4] = __ROR2__(v15, 8);
    *(_WORD *)&v20[v21 + 6] = -198;
    *(_OWORD *)&v20[v21 + 8] = *a5;
    *(_OWORD *)&v20[v21 + 24] = *a3;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140034d70  push    rbx
0x140034d72  push    rsi
0x140034d73  push    rdi
0x140034d74  push    r12
0x140034d76  push    r13
0x140034d78  push    r14
0x140034d7a  push    r15
0x140034d7c  sub     rsp, 50h
0x140034d80  cmp     [rsp+88h+Src], 0
0x140034d89  mov     r12, r9
0x140034d8c  mov     r13, r8
0x140034d8f  mov     ebx, edx
0x140034d91  mov     r15d, ecx
0x140034d94  jnz     loc_140034F24
0x140034d9a  mov     esi, 18h
0x140034d9f  mov     dil, [rsp+88h+arg_48]
0x140034da7  test    dil, dil
0x140034daa  jnz     loc_140034F34
0x140034db0  mov     al, [rsp+88h+arg_40]
0x140034db7  mov     edx, ebx
0x140034db9  mov     r14, [rsp+88h+arg_50]
0x140034dc1  mov     r9, [rsp+88h+Src]
0x140034dc9  mov     r8, [rsp+88h+arg_20]
0x140034dd1  mov     [rsp+88h+var_48], r14
0x140034dd6  mov     [rsp+88h+var_50], r13
0x140034ddb  mov     [rsp+88h+var_58], al
0x140034ddf  mov     al, [rsp+88h+arg_38]
0x140034de6  mov     byte ptr [rsp+88h+Priority], al
0x140034dea  mov     al, [rsp+88h+arg_30]
0x140034df1  mov     byte ptr [rsp+88h+BugCheckOnFailure], al
0x140034df5  call    NetioPhCreateNaPacket
0x140034dfa  test    eax, eax
0x140034dfc  js      short loc_140034E63
0x140034dfe  mov     rcx, [r14]; NetBufferList
0x140034e01  xor     r8d, r8d
0x140034e04  test    dil, dil
0x140034e07  jnz     short loc_140034E74
0x140034e09  lea     edx, [r8+28h]
0x140034e0d  call    NetioRetreatNetBufferList
0x140034e12  mov     rax, [r14]
0x140034e15  mov     rbx, [rax+8]
0x140034e19  mov     rcx, [rbx+8]; MemoryDescriptorList
0x140034e1d  test    byte ptr [rcx+0Ah], 5
0x140034e21  jz      loc_140034ED0
0x140034e27  mov     rax, [rcx+18h]
0x140034e2b  mov     ecx, [rbx+10h]
0x140034e2e  mov     rdx, [rsp+88h+arg_20]
0x140034e36  ror     si, 8
0x140034e3a  mov     dword ptr [rcx+rax], 60h ; '`'
0x140034e41  mov     [rcx+rax+4], si
0x140034e46  mov     word ptr [rcx+rax+6], 0FF3Ah
0x140034e4d  movups  xmm0, xmmword ptr [rdx]
0x140034e50  movdqu  xmmword ptr [rcx+rax+8], xmm0
0x140034e56  movups  xmm1, xmmword ptr [r13+0]
0x140034e5b  movdqu  xmmword ptr [rcx+rax+18h], xmm1
0x140034e61  xor     eax, eax
0x140034e63  add     rsp, 50h
0x140034e67  pop     r15
0x140034e69  pop     r14
0x140034e6b  pop     r13
0x140034e6d  pop     r12
0x140034e6f  pop     rdi
0x140034e70  pop     rsi
0x140034e71  pop     rbx
0x140034e72  retn
0x140034e74  lea     edx, [r15+28h]
0x140034e78  call    NetioRetreatNetBufferList
0x140034e7d  mov     rax, [r14]
0x140034e80  mov     rdi, [rax+8]
0x140034e84  mov     rcx, [rdi+8]; MemoryDescriptorList
0x140034e88  test    byte ptr [rcx+0Ah], 5
0x140034e8c  jz      short loc_140034EFA
0x140034e8e  mov     rax, [rcx+18h]
0x140034e92  mov     edi, [rdi+10h]
0x140034e95  mov     r8, rbx; Size
0x140034e98  add     rdi, rax
0x140034e9b  mov     rdx, r12; Src
0x140034e9e  mov     rcx, rdi; void *
0x140034ea1  call    memmove
0x140034ea6  mov     rdx, [rsp+88h+Src]; Src
0x140034eae  lea     rcx, [rdi+6]; void *
0x140034eb2  mov     r8, rbx; Size
0x140034eb5  call    memmove
0x140034eba  mov     word ptr [rdi+0Ch], 0DD86h
0x140034ec0  mov     edx, r15d
0x140034ec3  mov     rcx, [r14]
0x140034ec6  call    NetioAdvanceNetBufferList
0x140034ecb  jmp     loc_140034E12
0x140034ed0  xor     r9d, r9d; RequestedAddress
0x140034ed3  mov     [rsp+88h+Priority], 40000000h; Priority
0x140034edb  xor     edx, edx; AccessMode
0x140034edd  mov     [rsp+88h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140034ee5  lea     r8d, [r9+1]; CacheType
0x140034ee9  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140034ef0  nop     dword ptr [rax+rax+00h]
0x140034ef5  jmp     loc_140034E2B
0x140034efa  xor     r9d, r9d; RequestedAddress
0x140034efd  mov     [rsp+88h+Priority], 40000000h; Priority
0x140034f05  xor     edx, edx; AccessMode
0x140034f07  mov     [rsp+88h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140034f0f  lea     r8d, [r9+1]; CacheType
0x140034f13  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140034f1a  nop     dword ptr [rax+rax+00h]
0x140034f1f  jmp     loc_140034E92
0x140034f24  lea     esi, [rbx+1Ah]
0x140034f27  test    edx, edx
0x140034f29  jnz     loc_140034D9F
0x140034f2f  jmp     loc_140034D9A
0x140034f34  cmp     [rsp+88h+Src], 0
0x140034f3d  jz      loc_14007C9FC
0x140034f43  test    r12, r12
0x140034f46  jnz     loc_140034DB0
0x140034f4c  jmp     loc_14007C9FC
0x14007c9fc  mov     eax, 0C000000Dh
0x14007ca01  jmp     loc_140034E63
```
