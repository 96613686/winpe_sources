# CADMCOMW::GetServerGuid(void)

- ea: `0x1800062c0`
- end: `0x1800062c6`
- name: `?GetServerGuid@CADMCOMW@@UEAAJXZ`
- size: `6`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CADMCOMW::GetServerGuid(CADMCOMW *this)
{
  return 2147500037LL;
}

```

## disassembly

```asm
0x1800062c0  mov     eax, 80004005h
0x1800062c5  retn
```
