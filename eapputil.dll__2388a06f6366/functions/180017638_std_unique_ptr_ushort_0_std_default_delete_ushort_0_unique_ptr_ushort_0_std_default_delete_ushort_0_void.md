# std::unique_ptr<ushort [0],std::default_delete<ushort [0]>>::~unique_ptr<ushort [0],std::default_delete<ushort [0]>>(void)

- ea: `0x180017638`
- end: `0x18001764e`
- name: `??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(void **, unsigned __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180031e6e`
- `0x180031f7f`
- `0x180031f91`
- `0x180032021`
- `0x180032405`
- `0x180032443`
- `0x180032467`

## callees

- `0x1800025a0`
- `0x180017638`

## pseudocode

```c
void __fastcall std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(void **a1, unsigned __int64 a2)
{
  void *v2; // rcx

  v2 = *a1;
  if ( v2 )
    operator delete(v2, a2);
}

```

## disassembly

```asm
0x180017638  sub     rsp, 28h
0x18001763c  mov     rcx, [rcx]; void *
0x18001763f  test    rcx, rcx
0x180017642  jz      short loc_180017649
0x180017644  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017649  add     rsp, 28h
0x18001764d  retn
```
