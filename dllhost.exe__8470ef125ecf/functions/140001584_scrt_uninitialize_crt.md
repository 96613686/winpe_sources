# __scrt_uninitialize_crt

- ea: `0x140001584`
- end: `0x1400015ad`
- name: `__scrt_uninitialize_crt`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400011d0`

## callees

- `0x140001584`
- `0x140001708`

## pseudocode

```c
char __fastcall _scrt_uninitialize_crt(__int64 a1, char a2)
{
  if ( !byte_1400070D1 || !a2 )
  {
    _scrt_stub_for_acrt_uninitialize();
    _scrt_stub_for_acrt_uninitialize();
  }
  return 1;
}

```

## disassembly

```asm
0x140001584  push    rbx
0x140001586  sub     rsp, 20h
0x14000158a  cmp     cs:byte_1400070D1, 0
0x140001591  mov     bl, cl
0x140001593  jz      short loc_140001599
0x140001595  test    dl, dl
0x140001597  jnz     short loc_1400015A5
0x140001599  call    __scrt_stub_for_acrt_uninitialize
0x14000159e  mov     cl, bl
0x1400015a0  call    __scrt_stub_for_acrt_uninitialize
0x1400015a5  mov     al, 1
0x1400015a7  add     rsp, 20h
0x1400015ab  pop     rbx
0x1400015ac  retn
```
