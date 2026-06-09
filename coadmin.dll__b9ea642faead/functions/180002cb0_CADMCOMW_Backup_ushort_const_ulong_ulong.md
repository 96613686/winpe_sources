# CADMCOMW::Backup(ushort const *,ulong,ulong)

- ea: `0x180002cb0`
- end: `0x180002cc7`
- name: `?Backup@CADMCOMW@@UEAAJPEBGKK@Z`
- size: `23`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002cd0`

## pseudocode

```c
__int64 __fastcall CADMCOMW::Backup(CADMCOMW *this, const unsigned __int16 *a2, unsigned int a3, unsigned int a4)
{
  return CADMCOMW::BackupHelper(this, a2, a3, a4, 0);
}

```

## disassembly

```asm
0x180002cb0  sub     rsp, 38h
0x180002cb4  mov     [rsp+38h+var_18], 0; unsigned __int16 *
0x180002cbd  call    ?BackupHelper@CADMCOMW@@AEAAJPEBGKK0@Z; CADMCOMW::BackupHelper(ushort const *,ulong,ulong,ushort const *)
0x180002cc2  add     rsp, 38h
0x180002cc6  retn
```
