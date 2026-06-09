# __scrt_uninitialize_crt

- ea: `0x140001544`
- end: `0x14000156d`
- name: `__scrt_uninitialize_crt`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140001180`

## callees

- `0x140001544`
- `0x1400016c8`

## pseudocode

```c
char __fastcall _scrt_uninitialize_crt(__int64 a1, char a2)
{
  if ( !byte_1400040D1 || !a2 )
  {
    _scrt_stub_for_acrt_uninitialize();
    _scrt_stub_for_acrt_uninitialize();
  }
  return 1;
}

```

## disassembly

```asm
0x140001544  push    rbx
0x140001546  sub     rsp, 20h
0x14000154a  cmp     cs:byte_1400040D1, 0
0x140001551  mov     bl, cl
0x140001553  jz      short loc_140001559
0x140001555  test    dl, dl
0x140001557  jnz     short loc_140001565
0x140001559  call    __scrt_stub_for_acrt_uninitialize
0x14000155e  mov     cl, bl
0x140001560  call    __scrt_stub_for_acrt_uninitialize
0x140001565  mov     al, 1
0x140001567  add     rsp, 20h
0x14000156b  pop     rbx
0x14000156c  retn
```
