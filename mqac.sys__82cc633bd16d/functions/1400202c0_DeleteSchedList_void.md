# DeleteSchedList(void *)

- ea: `0x1400202c0`
- end: `0x1400202f8`
- name: `?DeleteSchedList@@YAXPEAX@Z`
- size: `56`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x1400010a4`
- `0x1400202c0`

## pseudocode

```c
void __fastcall DeleteSchedList(_QWORD *a1)
{
  _QWORD *v1; // rdi
  _QWORD *v2; // rbx

  v1 = (_QWORD *)a1[2];
  operator delete(a1);
  if ( v1 )
  {
    do
    {
      v2 = (_QWORD *)v1[1];
      operator delete(v1);
      v1 = v2;
    }
    while ( v2 );
  }
}

```

## disassembly

```asm
0x1400202c0  mov     [rsp+arg_0], rbx
0x1400202c5  push    rdi
0x1400202c6  sub     rsp, 20h
0x1400202ca  mov     rdi, [rcx+10h]
0x1400202ce  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400202d3  test    rdi, rdi
0x1400202d6  jz      short loc_1400202EC
0x1400202d8  mov     rbx, [rdi+8]
0x1400202dc  mov     rcx, rdi; void *
0x1400202df  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400202e4  mov     rdi, rbx
0x1400202e7  test    rbx, rbx
0x1400202ea  jnz     short loc_1400202D8
0x1400202ec  mov     rbx, [rsp+28h+arg_0]
0x1400202f1  add     rsp, 20h
0x1400202f5  pop     rdi
0x1400202f6  retn
```
