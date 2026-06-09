# NatShimAllocateBuffer

- ea: `0x140028c0c`
- end: `0x140028d2d`
- name: `NatShimAllocateBuffer`
- size: `289`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140028af8`
- `0x140028ea0`

## callees

- `0x140028c0c`
- `0x140028d34`
- `0x14002bfe0`
- `0x14002cbc0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140028cab`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140028cab`

## pseudocode

```c
_DWORD *__fastcall NatShimAllocateBuffer(__int64 a1)
{
  __int64 v1; // rsi
  unsigned int v2; // ebp
  __int64 *v3; // rdi
  _DWORD *v4; // rax
  _DWORD *v5; // rbx
  _QWORD *v6; // r14
  __int64 v7; // r15
  _DWORD *v8; // rbp
  __int64 v9; // r12
  char *v10; // rax
  _DWORD *v11; // rax

  if ( !NatShimPool )
    return 0;
  v1 = *(unsigned int *)(a1 + 24);
  v2 = *(_DWORD *)(a1 + 16);
  v3 = *(__int64 **)(a1 + 8);
  v4 = (_DWORD *)FsbAllocate();
  v5 = v4;
  if ( !v4 )
    return 0;
  v6 = 0;
  v7 = v2;
  memset(v4, 0, 0x40u);
  v8 = v5;
  if ( v1 )
  {
    while ( v3 )
    {
      v9 = v1;
      if ( v7 + v1 > (unsigned __int64)*((unsigned int *)v3 + 10) )
        v9 = *((unsigned int *)v3 + 10) - v7;
      v10 = (*((_BYTE *)v3 + 10) & 5) != 0
          ? (char *)v3[3]
          : (char *)MmMapLockedPagesSpecifyCache((PMDL)v3, 0, MmCached, 0, 0, 0x40000000u);
      if ( !v10 )
        break;
      v5[6] = v9;
      v1 -= v9;
      *((_QWORD *)v5 + 2) = &v10[v7];
      v5[15] = 2;
      *(_QWORD *)v5 = 0;
      if ( v6 )
        *v6 = v5;
      if ( !v1 )
        return v8;
      v6 = v5;
      v11 = (_DWORD *)FsbAllocate();
      v5 = v11;
      if ( !v11 )
        break;
      memset(v11, 0, 0x40u);
      v3 = (__int64 *)*v3;
      v7 = 0;
    }
    NatShimFreeBuffer(v8);
    return 0;
  }
  return v8;
}

```

## disassembly

```asm
0x140028c0c  push    rbx
0x140028c0e  push    rbp
0x140028c0f  push    rsi
0x140028c10  push    rdi
0x140028c11  push    r12
0x140028c13  push    r14
0x140028c15  push    r15
0x140028c17  sub     rsp, 30h
0x140028c1b  cmp     cs:NatShimPool, 0
0x140028c23  jz      loc_140028D16
0x140028c29  mov     esi, [rcx+18h]
0x140028c2c  mov     ebp, [rcx+10h]
0x140028c2f  mov     rdi, [rcx+8]
0x140028c33  call    FsbAllocate
0x140028c38  mov     rbx, rax
0x140028c3b  test    rax, rax
0x140028c3e  jz      loc_140028D16
0x140028c44  xor     r14d, r14d
0x140028c47  xor     edx, edx; Val
0x140028c49  mov     rcx, rax; void *
0x140028c4c  mov     r15d, ebp
0x140028c4f  lea     r8d, [r14+40h]; Size
0x140028c53  call    memset
0x140028c58  mov     rbp, rbx
0x140028c5b  test    rsi, rsi
0x140028c5e  jz      loc_140028D28
0x140028c64  test    rdi, rdi
0x140028c67  jz      loc_140028D0E
0x140028c6d  mov     edx, [rdi+28h]
0x140028c70  lea     rcx, [r15+rsi]
0x140028c74  mov     eax, edx
0x140028c76  mov     r12, rsi
0x140028c79  sub     rax, r15
0x140028c7c  cmp     rcx, rdx
0x140028c7f  cmova   r12, rax
0x140028c83  test    byte ptr [rdi+0Ah], 5
0x140028c87  jz      short loc_140028C8F
0x140028c89  mov     rax, [rdi+18h]
0x140028c8d  jmp     short loc_140028CB7
0x140028c8f  xor     r9d, r9d; RequestedAddress
0x140028c92  mov     [rsp+68h+Priority], 40000000h; Priority
0x140028c9a  xor     edx, edx; AccessMode
0x140028c9c  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140028ca4  mov     rcx, rdi; MemoryDescriptorList
0x140028ca7  lea     r8d, [r9+1]; CacheType
0x140028cab  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140028cb2  nop     dword ptr [rax+rax+00h]
0x140028cb7  test    rax, rax
0x140028cba  jz      short loc_140028D0E
0x140028cbc  add     rax, r15
0x140028cbf  mov     [rbx+18h], r12d
0x140028cc3  sub     rsi, r12
0x140028cc6  mov     [rbx+10h], rax
0x140028cca  mov     dword ptr [rbx+3Ch], 2
0x140028cd1  mov     qword ptr [rbx], 0
0x140028cd8  test    r14, r14
0x140028cdb  jz      short loc_140028CE0
0x140028cdd  mov     [r14], rbx
0x140028ce0  test    rsi, rsi
0x140028ce3  jz      short loc_140028D28
0x140028ce5  mov     r14, rbx
0x140028ce8  call    FsbAllocate
0x140028ced  mov     rbx, rax
0x140028cf0  test    rax, rax
0x140028cf3  jz      short loc_140028D0E
0x140028cf5  xor     edx, edx; Val
0x140028cf7  mov     rcx, rax; void *
0x140028cfa  lea     r8d, [rdx+40h]; Size
0x140028cfe  call    memset
0x140028d03  mov     rdi, [rdi]
0x140028d06  xor     r15d, r15d
0x140028d09  jmp     loc_140028C64
0x140028d0e  mov     rcx, rbp
0x140028d11  call    NatShimFreeBuffer
0x140028d16  xor     eax, eax
0x140028d18  add     rsp, 30h
0x140028d1c  pop     r15
0x140028d1e  pop     r14
0x140028d20  pop     r12
0x140028d22  pop     rdi
0x140028d23  pop     rsi
0x140028d24  pop     rbp
0x140028d25  pop     rbx
0x140028d26  retn
0x140028d28  mov     rax, rbp
0x140028d2b  jmp     short loc_140028D18
```
