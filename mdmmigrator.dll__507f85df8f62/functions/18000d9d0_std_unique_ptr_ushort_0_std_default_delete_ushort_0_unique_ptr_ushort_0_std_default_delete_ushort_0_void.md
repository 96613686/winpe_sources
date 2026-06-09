# std::unique_ptr<ushort [0],std::default_delete<ushort [0]>>::~unique_ptr<ushort [0],std::default_delete<ushort [0]>>(void)

- ea: `0x18000d9d0`
- end: `0x18000d9e6`
- name: `??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(void **, const struct std::nothrow_t *)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001f811`
- `0x18001f987`
- `0x18001fa05`
- `0x18001fa4d`

## callees

- `0x1800026b0`
- `0x18000d9d0`

## pseudocode

```c
void __fastcall std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(
        void **a1,
        const struct std::nothrow_t *a2)
{
  void *v2; // rcx

  v2 = *a1;
  if ( v2 )
    operator delete(v2, a2);
}

```

## disassembly

```asm
0x18000d9d0  sub     rsp, 28h
0x18000d9d4  mov     rcx, [rcx]; void *
0x18000d9d7  test    rcx, rcx
0x18000d9da  jz      short loc_18000D9E1
0x18000d9dc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d9e1  add     rsp, 28h
0x18000d9e5  retn
```
