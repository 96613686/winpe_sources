# NtOpenKey

- ea: `0x18015e510`
- end: `0x18015e528`
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
- `0x18002b640`
- `0x1800353f0`
- `0x1800355d8`
- `0x180035790`
- `0x180035a70`
- `0x18004226c`
- `0x180054f80`
- `0x18005b0f0`
- `0x1800603a0`
- `0x18007248c`
- `0x180073744`
- `0x1800737f8`
- `0x180073ac0`
- `0x180073f14`
- `0x1800740f0`
- `0x180074698`
- `0x1800b88e8`
- `0x1800bfd00`
- `0x1800c0de4`
- `0x1800c9be0`
- `0x1800ca7e4`
- `0x1800cda3c`
- `0x1800cf510`
- `0x1800cff18`
- `0x1800d8850`
- `0x1800d97d0`
- `0x1800dcb7c`
- `0x1800e15a0`
- `0x1800e872c`
- `0x1800e92c0`
- `0x1800eac80`
- `0x1800eba3c`
- `0x1800fb9b8`
- `0x18010243c`
- `0x180104f40`
- `0x18010b168`
- `0x1801100d4`
- `0x180110fa8`
- `0x180123794`
- `0x180123b28`
- `0x180139eac`

## callees

- `0x18015e510`

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
0x18015e510  mov     r10, rcx; NtOpenKey
0x18015e513  mov     eax, 12h
0x18015e518  test    byte ptr ds:7FFE0308h, 1
0x18015e520  jnz     short loc_18015E525
0x18015e522  syscall; Low latency system call
0x18015e524  retn
0x18015e525  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x18015e527  retn
```
