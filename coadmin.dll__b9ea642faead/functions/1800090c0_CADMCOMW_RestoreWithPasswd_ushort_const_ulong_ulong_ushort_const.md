# CADMCOMW::RestoreWithPasswd(ushort const *,ulong,ulong,ushort const *)

- ea: `0x1800090c0`
- end: `0x1800090e8`
- name: `?RestoreWithPasswd@CADMCOMW@@UEAAJPEBGKK0@Z`
- size: `40`
- prototype: `int(CADMCOMW *__hidden this, const unsigned __int16 *, unsigned int, unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008ae0`

## pseudocode

```c
__int64 __fastcall CADMCOMW::RestoreWithPasswd(
        CADMCOMW *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int16 *a5)
{
  return CADMCOMW::RestoreHelper(this, a2, a3, 0, a5, a4, 2u);
}

```

## disassembly

```asm
0x1800090c0  sub     rsp, 48h
0x1800090c4  mov     rax, [rsp+48h+arg_20]
0x1800090c9  mov     [rsp+48h+var_18], 2; unsigned int
0x1800090d1  mov     [rsp+48h+var_20], r9d; unsigned int
0x1800090d6  xor     r9d, r9d; unsigned int
0x1800090d9  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x1800090de  call    ?RestoreHelper@CADMCOMW@@AEAAJPEBGKK0KK@Z; CADMCOMW::RestoreHelper(ushort const *,ulong,ulong,ushort const *,ulong,ulong)
0x1800090e3  add     rsp, 48h
0x1800090e7  retn
```
