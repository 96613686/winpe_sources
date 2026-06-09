# __scrt_uninitialize_crt

- ea: `0x1800018b8`
- end: `0x1800018e1`
- name: `__scrt_uninitialize_crt`
- size: `41`
- prototype: `char __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001258`

## callees

- `0x1800018b8`
- `0x1800020ec`

## pseudocode

```c
char __fastcall _scrt_uninitialize_crt(__int64 a1, char a2)
{
  if ( !byte_18002A0F1 || !a2 )
  {
    _scrt_stub_for_acrt_uninitialize_critical();
    _scrt_stub_for_acrt_uninitialize_critical();
  }
  return 1;
}

```

## disassembly

```asm
0x1800018b8  push    rbx
0x1800018ba  sub     rsp, 20h
0x1800018be  cmp     cs:byte_18002A0F1, 0
0x1800018c5  mov     bl, cl
0x1800018c7  jz      short loc_1800018CD
0x1800018c9  test    dl, dl
0x1800018cb  jnz     short loc_1800018D9
0x1800018cd  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800018d2  mov     cl, bl
0x1800018d4  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800018d9  mov     al, 1
0x1800018db  add     rsp, 20h
0x1800018df  pop     rbx
0x1800018e0  retn
```
