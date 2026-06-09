# std::unique_ptr<ushort [0],std::default_delete<ushort [0]>>::~unique_ptr<ushort [0],std::default_delete<ushort [0]>>(void)

- ea: `0x18000bed8`
- end: `0x18000beee`
- name: `??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000cc7b`

## callees

- `0x180001d24`
- `0x18000bed8`

## pseudocode

```c
void __fastcall std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x18000bed8  sub     rsp, 28h
0x18000bedc  mov     rcx, [rcx]; Block
0x18000bedf  test    rcx, rcx
0x18000bee2  jz      short loc_18000BEE9
0x18000bee4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000bee9  add     rsp, 28h
0x18000beed  retn
```
