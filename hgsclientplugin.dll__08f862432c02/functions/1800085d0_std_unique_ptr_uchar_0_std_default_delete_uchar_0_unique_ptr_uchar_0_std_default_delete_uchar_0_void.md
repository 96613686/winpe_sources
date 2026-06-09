# std::unique_ptr<uchar [0],std::default_delete<uchar [0]>>::~unique_ptr<uchar [0],std::default_delete<uchar [0]>>(void)

- ea: `0x1800085d0`
- end: `0x1800085e6`
- name: `??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(void **, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000b033`

## callees

- `0x1800018f0`
- `0x1800085d0`

## pseudocode

```c
void __fastcall std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(void **a1, unsigned __int64 a2)
{
  void *v2; // rcx

  v2 = *a1;
  if ( v2 )
    operator delete(v2, a2);
}

```

## disassembly

```asm
0x1800085d0  sub     rsp, 28h
0x1800085d4  mov     rcx, [rcx]; void *
0x1800085d7  test    rcx, rcx
0x1800085da  jz      short loc_1800085E1
0x1800085dc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800085e1  add     rsp, 28h
0x1800085e5  retn
```
