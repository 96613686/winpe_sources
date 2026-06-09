# CADMCOMW::BackupWithPasswd(ushort const *,ulong,ulong,ushort const *)

- ea: `0x180002e50`
- end: `0x180002e55`
- name: `?BackupWithPasswd@CADMCOMW@@UEAAJPEBGKK0@Z`
- size: `5`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this, const unsigned __int16 *, unsigned int, unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002cd0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall CADMCOMW::BackupWithPasswd(
        CADMCOMW *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        int a4,
        const unsigned __int16 *a5)
{
  return CADMCOMW::BackupHelper(this, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x180002e50  jmp     ?BackupHelper@CADMCOMW@@AEAAJPEBGKK0@Z; CADMCOMW::BackupHelper(ushort const *,ulong,ulong,ushort const *)
```
