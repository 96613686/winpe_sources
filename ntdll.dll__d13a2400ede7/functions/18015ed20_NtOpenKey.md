# NtOpenKey

- ea: `0x18015ed20`
- end: `0x18015ed38`
- name: `NtOpenKey`
- size: `24`
- prototype: ``
- caller_count: `52`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800012e0`
- `0x180010770`
- `0x180010870`
- `0x180010b80`
- `0x180010eb0`
- `0x180011d10`
- `0x180013820`
- `0x180016bc0`
- `0x18001d4b0`
- `0x18002a934`
- `0x180034bd0`
- `0x180036190`
- `0x1800362dc`
- `0x180036494`
- `0x1800382d0`
- `0x180038ed4`
- `0x1800533cc`
- `0x18005ee5c`
- `0x180071960`
- `0x180077ad0`
- `0x18007cd80`
- `0x1800bc688`
- `0x1800c3fe0`
- `0x1800c50c4`
- `0x1800cf5cc`
- `0x1800d0c40`
- `0x1800d1648`
- `0x1800d36e4`
- `0x1800d49a4`
- `0x1800d4a58`
- `0x1800d4d20`
- `0x1800d5174`
- `0x1800d5350`
- `0x1800d58f8`
- `0x1800d9560`
- `0x1800da250`
- `0x1800e1bb0`
- `0x1800e8d8c`
- `0x1800e9920`
- `0x1800eb2e0`
- `0x1800ec51c`
- `0x1800fc6f8`
- `0x18010308c`
- `0x180105d70`
- `0x18010c708`
- `0x180111434`
- `0x180112394`
- `0x180124284`
- `0x180124618`
- `0x18013a99c`

## callees

- `0x18015ed20`

## pseudocode

```c
__int64 NtOpenKey()
{
  __int64 result; // rax

  result = 18;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x18015ed20  mov     r10, rcx; NtOpenKey
0x18015ed23  mov     eax, 12h
0x18015ed28  test    byte ptr ds:7FFE0308h, 1
0x18015ed30  jnz     short loc_18015ED35
0x18015ed32  syscall; Low latency system call
0x18015ed34  retn
0x18015ed35  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x18015ed37  retn
```
