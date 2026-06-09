# fsg_UpdateWorkSpaceElement(fsg_WorkSpaceOffsets *,fsg_WorkSpaceAddr *)

- ea: `0x140047308`
- end: `0x140047363`
- name: `?fsg_UpdateWorkSpaceElement@@YAXPEAUfsg_WorkSpaceOffsets@@PEAUfsg_WorkSpaceAddr@@@Z`
- size: `91`
- prototype: `void __fastcall(struct fsg_WorkSpaceOffsets *, struct fsg_WorkSpaceAddr *)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140011f54`
- `0x140013530`

## callees

- `0x140047308`

## pseudocode

```c
void __fastcall fsg_UpdateWorkSpaceElement(struct fsg_WorkSpaceOffsets *a1, struct fsg_WorkSpaceAddr *a2)
{
  __int64 v2; // r8
  _QWORD *v3; // r9
  __int64 i; // rdx

  v2 = *((_QWORD *)a2 + 1);
  v3 = (_QWORD *)*((_QWORD *)a2 + 2);
  for ( i = 0; i != 6; ++i )
    v3[i] = v2 + *((unsigned int *)a1 + i + 5);
  v3[7] = v2 + *((unsigned int *)a1 + 12);
  v3[8] = v2 + *((unsigned int *)a1 + 13);
  v3[6] = v2 + *((unsigned int *)a1 + 11);
  v3[9] = v2 + *((unsigned int *)a1 + 14);
  v3[11] = v2 + *((unsigned int *)a1 + 15);
  v3[13] = v2 + *((unsigned int *)a1 + 16);
}

```

## disassembly

```asm
0x140047308  mov     r8, [rdx+8]
0x14004730c  mov     r9, [rdx+10h]
0x140047310  xor     edx, edx
0x140047312  mov     eax, [rcx+rdx*4+14h]
0x140047316  add     rax, r8
0x140047319  mov     [r9+rdx*8], rax
0x14004731d  inc     rdx
0x140047320  cmp     rdx, 6
0x140047324  jnz     short loc_140047312
0x140047326  mov     eax, [rcx+30h]
0x140047329  add     rax, r8
0x14004732c  mov     [r9+38h], rax
0x140047330  mov     eax, [rcx+34h]
0x140047333  add     rax, r8
0x140047336  mov     [r9+40h], rax
0x14004733a  mov     eax, [rcx+2Ch]
0x14004733d  add     rax, r8
0x140047340  mov     [r9+30h], rax
0x140047344  mov     eax, [rcx+38h]
0x140047347  add     rax, r8
0x14004734a  mov     [r9+48h], rax
0x14004734e  mov     eax, [rcx+3Ch]
0x140047351  add     rax, r8
0x140047354  mov     [r9+58h], rax
0x140047358  mov     eax, [rcx+40h]
0x14004735b  add     rax, r8
0x14004735e  mov     [r9+68h], rax
0x140047362  retn
```
