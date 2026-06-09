# FreeContextBuffer

- ea: `0x180027290`
- end: `0x1800272a1`
- name: `FreeContextBuffer`
- size: `17`
- prototype: `SECURITY_STATUS __stdcall(PVOID pvContextBuffer)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000ab20`

## callees

- `0x180002900`

## pseudocode

```c
SECURITY_STATUS __stdcall FreeContextBuffer(PVOID pvContextBuffer)
{
  SecFreeForKsecCaller(pvContextBuffer);
  return 0;
}

```

## disassembly

```asm
0x180027290  sub     rsp, 28h
0x180027294  call    SecFreeForKsecCaller
0x180027299  xor     eax, eax
0x18002729b  add     rsp, 28h
0x18002729f  retn
```
