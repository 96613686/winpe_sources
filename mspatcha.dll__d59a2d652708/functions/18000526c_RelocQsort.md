# RelocQsort

- ea: `0x18000526c`
- end: `0x180005331`
- name: `RelocQsort`
- size: `197`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000526c`
- `0x1800061e4`

## callees

- `0x18000526c`

## pseudocode

```c
__int64 __fastcall RelocQsort(unsigned __int64 a1, unsigned __int64 a2)
{
  unsigned int *v4; // r9
  unsigned int *v5; // r8
  __int64 result; // rax
  unsigned int *v7; // rbx
  unsigned int v8; // edx
  bool v9; // cc
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx

  do
  {
    v4 = (unsigned int *)a1;
    v5 = (unsigned int *)a2;
    result = ((__int64)(a2 - a1) >> 3) / 2;
    v7 = (unsigned int *)(a1 + 8 * result);
    v8 = *v7;
    do
    {
      if ( v4 > v5 )
        break;
      do
      {
        if ( *v4 > v8 )
          break;
        v4 += 2;
      }
      while ( v4 <= v5 );
      while ( v5 >= v4 && *v5 >= v8 )
        v5 -= 2;
      v9 = v4 <= v5;
      if ( v4 < v5 )
      {
        result = *(_QWORD *)v5;
        v10 = *(_QWORD *)v4;
        *(_QWORD *)v4 = *(_QWORD *)v5;
        v4 += 2;
        *(_QWORD *)v5 = v10;
        v5 -= 2;
        v9 = v4 <= v5;
      }
    }
    while ( v9 );
    if ( v4 >= v7 )
    {
      if ( v5 > v7 )
      {
        result = *(_QWORD *)v7;
        v12 = *(_QWORD *)v5;
        *(_QWORD *)v5 = *(_QWORD *)v7;
        *(_QWORD *)v7 = v12;
        v7 = v5;
      }
    }
    else
    {
      result = *(_QWORD *)v7;
      v11 = *(_QWORD *)v4;
      *(_QWORD *)v4 = *(_QWORD *)v7;
      *(_QWORD *)v7 = v11;
      v7 = v4;
    }
    if ( a1 < (unsigned __int64)(v7 - 2) )
      result = RelocQsort(a1, v7 - 2);
    a1 = (unsigned __int64)(v7 + 2);
  }
  while ( (unsigned __int64)(v7 + 2) < a2 );
  return result;
}

```

## disassembly

```asm
0x18000526c  mov     [rsp+arg_0], rbx
0x180005271  push    rdi
0x180005272  sub     rsp, 20h
0x180005276  mov     rdi, rdx
0x180005279  mov     r10, rcx
0x18000527c  mov     rax, rdi
0x18000527f  mov     r9, r10
0x180005282  sub     rax, r10
0x180005285  mov     r8, rdi
0x180005288  sar     rax, 3
0x18000528c  test    rax, rax
0x18000528f  jns     short loc_180005294
0x180005291  inc     rax
0x180005294  sar     rax, 1
0x180005297  lea     rbx, [r10+rax*8]
0x18000529b  mov     edx, [rbx]
0x18000529d  cmp     r9, r8
0x1800052a0  ja      short loc_1800052DE
0x1800052a2  cmp     [r9], edx
0x1800052a5  ja      short loc_1800052BB
0x1800052a7  add     r9, 8
0x1800052ab  cmp     r9, r8
0x1800052ae  jbe     short loc_1800052A2
0x1800052b0  jmp     short loc_1800052BB
0x1800052b2  cmp     [r8], edx
0x1800052b5  jb      short loc_1800052C0
0x1800052b7  sub     r8, 8
0x1800052bb  cmp     r8, r9
0x1800052be  jnb     short loc_1800052B2
0x1800052c0  cmp     r9, r8
0x1800052c3  jnb     short loc_1800052DC
0x1800052c5  mov     rax, [r8]
0x1800052c8  mov     rcx, [r9]
0x1800052cb  mov     [r9], rax
0x1800052ce  add     r9, 8
0x1800052d2  mov     [r8], rcx
0x1800052d5  sub     r8, 8
0x1800052d9  cmp     r9, r8
0x1800052dc  jbe     short loc_18000529D
0x1800052de  cmp     r9, rbx
0x1800052e1  jnb     short loc_1800052F4
0x1800052e3  mov     rax, [rbx]
0x1800052e6  mov     rcx, [r9]
0x1800052e9  mov     [r9], rax
0x1800052ec  mov     [rbx], rcx
0x1800052ef  mov     rbx, r9
0x1800052f2  jmp     short loc_180005308
0x1800052f4  cmp     r8, rbx
0x1800052f7  jbe     short loc_180005308
0x1800052f9  mov     rax, [rbx]
0x1800052fc  mov     rcx, [r8]
0x1800052ff  mov     [r8], rax
0x180005302  mov     [rbx], rcx
0x180005305  mov     rbx, r8
0x180005308  lea     rdx, [rbx-8]
0x18000530c  cmp     r10, rdx
0x18000530f  jnb     short loc_180005319
0x180005311  mov     rcx, r10
0x180005314  call    RelocQsort
0x180005319  lea     r10, [rbx+8]
0x18000531d  cmp     r10, rdi
0x180005320  jb      loc_18000527C
0x180005326  mov     rbx, [rsp+28h+arg_0]
0x18000532b  add     rsp, 20h
0x18000532f  pop     rdi
0x180005330  retn
```
