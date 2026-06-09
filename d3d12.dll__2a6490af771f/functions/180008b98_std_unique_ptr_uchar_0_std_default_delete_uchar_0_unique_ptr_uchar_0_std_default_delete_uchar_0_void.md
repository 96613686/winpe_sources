# std::unique_ptr<uchar [0],std::default_delete<uchar [0]>>::~unique_ptr<uchar [0],std::default_delete<uchar [0]>>(void)

- ea: `0x180008b98`
- end: `0x180008bae`
- name: `??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000195c`
- `0x180001a60`
- `0x180013b10`
- `0x180013b30`
- `0x180013b50`
- `0x180013c2f`
- `0x180013c65`
- `0x180013c77`

## callees

- `0x180008b98`
- `0x18000b7e0`

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
0x180008b98  sub     rsp, 28h
0x180008b9c  mov     rcx, [rcx]; Block
0x180008b9f  test    rcx, rcx
0x180008ba2  jz      short loc_180008BA9
0x180008ba4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008ba9  add     rsp, 28h
0x180008bad  retn
```
