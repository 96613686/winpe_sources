# __scrt_uninitialize_crt

- ea: `0x180001874`
- end: `0x18000189d`
- name: `__scrt_uninitialize_crt`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800011e8`

## callees

- `0x180001874`
- `0x180001cac`

## pseudocode

```c
char __fastcall _scrt_uninitialize_crt(__int64 a1, char a2)
{
  if ( !byte_1800080F1 || !a2 )
  {
    _scrt_stub_for_acrt_uninitialize_critical();
    _scrt_stub_for_acrt_uninitialize_critical();
  }
  return 1;
}

```

## disassembly

```asm
0x180001874  push    rbx
0x180001876  sub     rsp, 20h
0x18000187a  cmp     cs:byte_1800080F1, 0
0x180001881  mov     bl, cl
0x180001883  jz      short loc_180001889
0x180001885  test    dl, dl
0x180001887  jnz     short loc_180001895
0x180001889  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000188e  mov     cl, bl
0x180001890  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001895  mov     al, 1
0x180001897  add     rsp, 20h
0x18000189b  pop     rbx
0x18000189c  retn
```
