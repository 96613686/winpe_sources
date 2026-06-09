# SmbCopySendBufferForSecuritySignatures

- ea: `0x14003f618`
- end: `0x14003f6f5`
- name: `SmbCopySendBufferForSecuritySignatures`
- size: `221`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14003f0c8`
- `0x14003f41c`
- `0x14004e5b0`

## callees

- `0x1400166c0`
- `0x14003f618`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14003f6a0`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14003f6a0`
- `ntoskrnl!ExAllocatePool2` at `0x14003f641`
- `ntoskrnl!ExAllocatePool2` at `0x14003f641`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003f68c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003f68c`
- `rdbss!RxAllocateMdl2` at `0x14003f673`
- `rdbss!RxAllocateMdl2` at `0x14003f673`

## pseudocode

```c
__int64 __fastcall SmbCopySendBufferForSecuritySignatures(__int64 *a1, unsigned int a2, struct _MDL **a3, _QWORD *a4)
{
  unsigned int v5; // esi
  __int64 Pool2; // rax
  char *v9; // rdi
  __int64 result; // rax
  struct _MDL *Mdl2; // rax
  struct _MDL *v12; // rbp
  char *v13; // r15
  unsigned int v14; // eax
  __int64 v15; // rbx

  v5 = a2;
  Pool2 = ExAllocatePool2(66, a2, 1397976403);
  v9 = (char *)Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  Mdl2 = (struct _MDL *)RxAllocateMdl2(Pool2, v5, 0, 0, 0);
  v12 = Mdl2;
  if ( !Mdl2 )
  {
    ExFreePoolWithTag(v9, 0);
    return 3221225626LL;
  }
  v13 = v9;
  MmBuildMdlForNonPagedPool(Mdl2);
  while ( a1 && v5 )
  {
    v14 = *((_DWORD *)a1 + 10);
    if ( v14 >= v5 )
      v14 = v5;
    v15 = v14;
    memmove(v9, (const void *)a1[3], v14);
    a1 = (__int64 *)*a1;
    v5 -= v15;
    v9 += v15;
  }
  *a3 = v12;
  result = 0;
  *a4 = v13;
  return result;
}

```

## disassembly

```asm
0x14003f618  push    rbx
0x14003f61a  push    rbp
0x14003f61b  push    rsi
0x14003f61c  push    rdi
0x14003f61d  push    r12
0x14003f61f  push    r13
0x14003f621  push    r14
0x14003f623  push    r15
0x14003f625  sub     rsp, 38h
0x14003f629  mov     r13, r8
0x14003f62c  mov     esi, edx
0x14003f62e  mov     r14, rcx
0x14003f631  mov     edx, edx
0x14003f633  mov     ecx, 42h ; 'B'
0x14003f638  mov     r8d, 53536D53h
0x14003f63e  mov     r12, r9
0x14003f641  call    cs:__imp_ExAllocatePool2
0x14003f648  nop     dword ptr [rax+rax+00h]
0x14003f64d  mov     rdi, rax
0x14003f650  test    rax, rax
0x14003f653  jnz     short loc_14003F65F
0x14003f655  mov     eax, 0C000009Ah
0x14003f65a  jmp     loc_14003F6E3
0x14003f65f  xor     r9d, r9d
0x14003f662  mov     [rsp+78h+var_58], 0
0x14003f66b  xor     r8d, r8d
0x14003f66e  mov     edx, esi
0x14003f670  mov     rcx, rdi
0x14003f673  call    cs:__imp_RxAllocateMdl2
0x14003f67a  nop     dword ptr [rax+rax+00h]
0x14003f67f  mov     rbp, rax
0x14003f682  test    rax, rax
0x14003f685  jnz     short loc_14003F69A
0x14003f687  xor     edx, edx; Tag
0x14003f689  mov     rcx, rdi; P
0x14003f68c  call    cs:__imp_ExFreePoolWithTag
0x14003f693  nop     dword ptr [rax+rax+00h]
0x14003f698  jmp     short loc_14003F655
0x14003f69a  mov     rcx, rbp; MemoryDescriptorList
0x14003f69d  mov     r15, rdi
0x14003f6a0  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14003f6a7  nop     dword ptr [rax+rax+00h]
0x14003f6ac  jmp     short loc_14003F6D4
0x14003f6ae  test    esi, esi
0x14003f6b0  jz      short loc_14003F6D9
0x14003f6b2  mov     eax, [r14+28h]
0x14003f6b6  mov     rcx, rdi; void *
0x14003f6b9  mov     rdx, [r14+18h]; Src
0x14003f6bd  cmp     eax, esi
0x14003f6bf  cmovnb  eax, esi
0x14003f6c2  mov     r8d, eax; Size
0x14003f6c5  mov     ebx, eax
0x14003f6c7  call    memmove
0x14003f6cc  mov     r14, [r14]
0x14003f6cf  sub     esi, ebx
0x14003f6d1  add     rdi, rbx
0x14003f6d4  test    r14, r14
0x14003f6d7  jnz     short loc_14003F6AE
0x14003f6d9  mov     [r13+0], rbp
0x14003f6dd  xor     eax, eax
0x14003f6df  mov     [r12], r15
0x14003f6e3  add     rsp, 38h
0x14003f6e7  pop     r15
0x14003f6e9  pop     r14
0x14003f6eb  pop     r13
0x14003f6ed  pop     r12
0x14003f6ef  pop     rdi
0x14003f6f0  pop     rsi
0x14003f6f1  pop     rbp
0x14003f6f2  pop     rbx
0x14003f6f3  retn
```
