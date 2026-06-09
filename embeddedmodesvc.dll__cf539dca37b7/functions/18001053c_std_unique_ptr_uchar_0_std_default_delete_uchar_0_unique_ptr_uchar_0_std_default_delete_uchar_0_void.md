# std::unique_ptr<uchar [0],std::default_delete<uchar [0]>>::~unique_ptr<uchar [0],std::default_delete<uchar [0]>>(void)

- ea: `0x18001053c`
- end: `0x180010552`
- name: `??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(void **, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180011e74`
- `0x180017e4c`
- `0x1800180a4`
- `0x18001839c`
- `0x1800184a4`
- `0x18001a050`

## callees

- `0x180002ee0`
- `0x18001053c`

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
0x18001053c  sub     rsp, 28h
0x180010540  mov     rcx, [rcx]; void *
0x180010543  test    rcx, rcx
0x180010546  jz      short loc_18001054D
0x180010548  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001054d  add     rsp, 28h
0x180010551  retn
```
