# std::unique_ptr<ushort [0],std::default_delete<ushort [0]>>::~unique_ptr<ushort [0],std::default_delete<ushort [0]>>(void)

- ea: `0x140004f24`
- end: `0x140004f3a`
- name: `??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1400132a0`
- `0x14001381c`

## callees

- `0x140002624`
- `0x140004f24`

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
0x140004f24  sub     rsp, 28h
0x140004f28  mov     rcx, [rcx]; void *
0x140004f2b  test    rcx, rcx
0x140004f2e  jz      short loc_140004F35
0x140004f30  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140004f35  add     rsp, 28h
0x140004f39  retn
```
