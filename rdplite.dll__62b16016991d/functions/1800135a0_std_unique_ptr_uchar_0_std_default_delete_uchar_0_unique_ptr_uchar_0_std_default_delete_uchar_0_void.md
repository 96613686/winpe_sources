# std::unique_ptr<uchar [0],std::default_delete<uchar [0]>>::~unique_ptr<uchar [0],std::default_delete<uchar [0]>>(void)

- ea: `0x1800135a0`
- end: `0x1800135b6`
- name: `??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `10`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180014570`
- `0x180015040`
- `0x1800161b8`
- `0x180016660`
- `0x180017290`
- `0x180017720`
- `0x1800293df`
- `0x180029442`
- `0x1800295af`
- `0x18002965e`

## callees

- `0x180003b10`
- `0x1800135a0`

## pseudocode

```c
void __fastcall std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x1800135a0  sub     rsp, 28h
0x1800135a4  mov     rcx, [rcx]; Block
0x1800135a7  test    rcx, rcx
0x1800135aa  jz      short loc_1800135B1
0x1800135ac  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800135b1  add     rsp, 28h
0x1800135b5  retn
```
