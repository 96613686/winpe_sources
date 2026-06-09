# CADMCOMW::Restore(ushort const *,ulong,ulong)

- ea: `0x180008ab0`
- end: `0x180008ad7`
- name: `?Restore@CADMCOMW@@UEAAJPEBGKK@Z`
- size: `39`
- prototype: `int(CADMCOMW *__hidden this, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008ae0`

## pseudocode

```c
__int64 __fastcall CADMCOMW::Restore(CADMCOMW *this, const unsigned __int16 *a2, unsigned int a3, unsigned int a4)
{
  return CADMCOMW::RestoreHelper(this, a2, a3, 0, 0, a4, 2u);
}

```

## disassembly

```asm
0x180008ab0  sub     rsp, 48h
0x180008ab4  mov     [rsp+48h+var_18], 2; unsigned int
0x180008abc  mov     [rsp+48h+var_20], r9d; unsigned int
0x180008ac1  xor     r9d, r9d; unsigned int
0x180008ac4  mov     [rsp+48h+var_28], 0; unsigned __int16 *
0x180008acd  call    ?RestoreHelper@CADMCOMW@@AEAAJPEBGKK0KK@Z; CADMCOMW::RestoreHelper(ushort const *,ulong,ulong,ushort const *,ulong,ulong)
0x180008ad2  add     rsp, 48h
0x180008ad6  retn
```
