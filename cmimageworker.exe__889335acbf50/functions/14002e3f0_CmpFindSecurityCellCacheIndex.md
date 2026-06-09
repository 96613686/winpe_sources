# CmpFindSecurityCellCacheIndex

- ea: `0x14002e3f0`
- end: `0x14002e493`
- name: `CmpFindSecurityCellCacheIndex`
- size: `163`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140031990`
- `0x140031cf8`
- `0x140031dfc`
- `0x140031f38`

## callees

- `0x14002e3f0`
- `0x1400323b0`

## pseudocode

```c
char __fastcall CmpFindSecurityCellCacheIndex(__int64 a1, int a2, _DWORD *a3)
{
  unsigned __int64 v5; // r9
  char result; // al
  _DWORD *LowerBoundInSortedArray; // rcx
  int v8; // [rsp+48h] [rbp+10h] BYREF

  v8 = a2;
  if ( *(_DWORD *)(a1 + 1888) )
  {
    LODWORD(v5) = *(_DWORD *)(a1 + 1896);
    if ( (v5 & 0x80000000) != 0LL
      || (unsigned int)v5 >= *(_DWORD *)(a1 + 1888)
      || *(_DWORD *)(*(_QWORD *)(a1 + 1904) + 16LL * (int)v5) != v8 )
    {
      LowerBoundInSortedArray = (_DWORD *)RtlFindLowerBoundInSortedArray(
                                            &v8,
                                            *(_QWORD *)(a1 + 1904),
                                            *(unsigned int *)(a1 + 1888));
      v5 = ((unsigned __int64)LowerBoundInSortedArray - *(_QWORD *)(a1 + 1904)) >> 4;
      if ( (unsigned int)v5 >= *(_DWORD *)(a1 + 1888) || *LowerBoundInSortedArray != v8 )
        goto LABEL_3;
      *(_DWORD *)(a1 + 1896) = v5;
    }
    result = 1;
    goto LABEL_4;
  }
  LODWORD(v5) = 0;
LABEL_3:
  result = 0;
LABEL_4:
  *a3 = v5;
  return result;
}

```

## disassembly

```asm
0x14002e3f0  mov     [rsp+arg_0], rbx
0x14002e3f5  mov     [rsp+arg_8], edx
0x14002e3f9  push    rdi
0x14002e3fa  sub     rsp, 30h
0x14002e3fe  cmp     dword ptr [rcx+760h], 0
0x14002e405  mov     rdi, r8
0x14002e408  mov     rbx, rcx
0x14002e40b  jnz     short loc_14002E421
0x14002e40d  xor     r9d, r9d
0x14002e410  xor     al, al
0x14002e412  mov     rbx, [rsp+38h+arg_0]
0x14002e417  mov     [rdi], r9d
0x14002e41a  add     rsp, 30h
0x14002e41e  pop     rdi
0x14002e41f  retn
0x14002e421  mov     r9d, [rcx+768h]
0x14002e428  test    r9d, r9d
0x14002e42b  js      short loc_14002E450
0x14002e42d  cmp     r9d, [rcx+760h]
0x14002e434  jnb     short loc_14002E450
0x14002e436  mov     rcx, [rcx+770h]
0x14002e43d  mov     eax, [rsp+38h+arg_8]
0x14002e441  movsxd  rdx, r9d
0x14002e444  add     rdx, rdx
0x14002e447  cmp     [rcx+rdx*8], eax
0x14002e44a  jnz     short loc_14002E450
0x14002e44c  mov     al, 1
0x14002e44e  jmp     short loc_14002E412
0x14002e450  mov     r8d, [rbx+760h]
0x14002e457  lea     rcx, [rsp+38h+arg_8]
0x14002e45c  mov     rdx, [rbx+770h]
0x14002e463  call    RtlFindLowerBoundInSortedArray
0x14002e468  mov     r9, rax
0x14002e46b  mov     rcx, rax
0x14002e46e  sub     r9, [rbx+770h]
0x14002e475  shr     r9, 4
0x14002e479  cmp     r9d, [rbx+760h]
0x14002e480  jnb     short loc_14002E410
0x14002e482  mov     eax, [rsp+38h+arg_8]
0x14002e486  cmp     [rcx], eax
0x14002e488  jnz     short loc_14002E410
0x14002e48a  mov     [rbx+768h], r9d
0x14002e491  jmp     short loc_14002E44C
```
