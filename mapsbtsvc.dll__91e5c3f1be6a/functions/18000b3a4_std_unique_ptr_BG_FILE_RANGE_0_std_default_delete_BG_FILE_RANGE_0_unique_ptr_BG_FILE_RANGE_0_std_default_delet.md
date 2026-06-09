# std::unique_ptr<_BG_FILE_RANGE [0],std::default_delete<_BG_FILE_RANGE [0]>>::~unique_ptr<_BG_FILE_RANGE [0],std::default_delete<_BG_FILE_RANGE [0]>>(void)

- ea: `0x18000b3a4`
- end: `0x18000b3ba`
- name: `??1?$unique_ptr@$$BY0A@U_BG_FILE_RANGE@@U?$default_delete@$$BY0A@U_BG_FILE_RANGE@@@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(void **)`
- caller_count: `10`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000bb70`
- `0x18000c99c`
- `0x18000dd10`
- `0x18001240c`
- `0x180014334`
- `0x18001438e`
- `0x180014467`
- `0x18001451b`
- `0x180014563`
- `0x18001480f`

## callees

- `0x180001e94`
- `0x18000b3a4`

## pseudocode

```c
void __fastcall std::unique_ptr<_BG_FILE_RANGE [0]>::~unique_ptr<_BG_FILE_RANGE [0]>(void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x18000b3a4  sub     rsp, 28h
0x18000b3a8  mov     rcx, [rcx]; Block
0x18000b3ab  test    rcx, rcx
0x18000b3ae  jz      short loc_18000B3B5
0x18000b3b0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000b3b5  add     rsp, 28h
0x18000b3b9  retn
```
