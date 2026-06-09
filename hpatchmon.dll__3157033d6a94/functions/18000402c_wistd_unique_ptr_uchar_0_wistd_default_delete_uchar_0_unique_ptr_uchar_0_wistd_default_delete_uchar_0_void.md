# wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::~unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>(void)

- ea: `0x18000402c`
- end: `0x18000404c`
- name: `??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(void **, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180014219`

## callees

- `0x180002c8c`
- `0x18000402c`

## pseudocode

```c
void __fastcall wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::~unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>(
        void **a1,
        unsigned __int64 a2)
{
  void *v2; // rax

  v2 = *a1;
  *a1 = 0;
  if ( v2 )
    operator delete(v2, a2);
}

```

## disassembly

```asm
0x18000402c  sub     rsp, 28h
0x180004030  mov     rax, [rcx]
0x180004033  mov     qword ptr [rcx], 0
0x18000403a  test    rax, rax
0x18000403d  jz      short loc_180004047
0x18000403f  mov     rcx, rax; void *
0x180004042  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004047  add     rsp, 28h
0x18000404b  retn
```
