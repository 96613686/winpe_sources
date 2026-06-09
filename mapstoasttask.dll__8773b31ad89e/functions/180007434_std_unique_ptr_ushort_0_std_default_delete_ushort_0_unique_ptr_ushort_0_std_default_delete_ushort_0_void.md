# std::unique_ptr<ushort [0],std::default_delete<ushort [0]>>::~unique_ptr<ushort [0],std::default_delete<ushort [0]>>(void)

- ea: `0x180007434`
- end: `0x18000744a`
- name: `??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180009c32`

## callees

- `0x180001624`
- `0x180007434`

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
0x180007434  sub     rsp, 28h
0x180007438  mov     rcx, [rcx]; Block
0x18000743b  test    rcx, rcx
0x18000743e  jz      short loc_180007445
0x180007440  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007445  add     rsp, 28h
0x180007449  retn
```
