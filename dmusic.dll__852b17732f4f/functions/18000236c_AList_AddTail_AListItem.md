# AList::AddTail(AListItem *)

- ea: `0x18000236c`
- end: `0x1800023a2`
- name: `?AddTail@AList@@QEAAXPEAVAListItem@@@Z`
- size: `54`
- prototype: `void __fastcall(AList *__hidden this, struct AListItem *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c330`
- `0x18000f6a4`
- `0x1800186a4`
- `0x180019df0`
- `0x18001a2fc`

## callees

- `0x18000236c`

## pseudocode

```c
void __fastcall AList::AddTail(AList *this, struct AListItem *a2)
{
  _QWORD **v2; // r8
  _QWORD *v3; // r9
  _QWORD *v4; // r10

  v2 = *(_QWORD ***)this;
  if ( *(_QWORD *)this )
  {
    v3 = *v2;
    if ( *v2 )
    {
      do
      {
        v4 = v3;
        v3 = (_QWORD *)*v3;
      }
      while ( v3 );
    }
    else
    {
      v4 = *(_QWORD **)this;
    }
    *v4 = a2;
    *(_QWORD *)this = v2;
  }
  else if ( a2 )
  {
    *(_QWORD *)a2 = 0;
    *(_QWORD *)this = a2;
  }
}

```

## disassembly

```asm
0x18000236c  mov     r8, [rcx]
0x18000236f  test    r8, r8
0x180002372  jnz     short loc_180002380
0x180002374  test    rdx, rdx
0x180002377  jz      short locret_1800023A1
0x180002379  mov     [rdx], r8
0x18000237c  mov     [rcx], rdx
0x18000237f  retn
0x180002380  mov     r9, [r8]
0x180002383  test    r9, r9
0x180002386  jz      short loc_180002398
0x180002388  mov     rax, [r9]
0x18000238b  mov     r10, r9
0x18000238e  mov     r9, rax
0x180002391  test    rax, rax
0x180002394  jnz     short loc_180002388
0x180002396  jmp     short loc_18000239B
0x180002398  mov     r10, r8
0x18000239b  mov     [r10], rdx
0x18000239e  mov     [rcx], r8
0x1800023a1  retn
```
