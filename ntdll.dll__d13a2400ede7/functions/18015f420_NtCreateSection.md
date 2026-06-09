# NtCreateSection

- ea: `0x18015f420`
- end: `0x18015f438`
- name: `NtCreateSection`
- size: `24`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD)`
- caller_count: `24`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001cd30`
- `0x180028ac0`
- `0x18002a770`
- `0x18004e1b4`
- `0x18005f3c0`
- `0x180077e90`
- `0x1800a8b2c`
- `0x1800a920c`
- `0x1800a98d8`
- `0x1800af79c`
- `0x1800b9d30`
- `0x1800e8a90`
- `0x1800eb504`
- `0x1800fb630`
- `0x18010223c`
- `0x18010a750`
- `0x18010ed50`
- `0x1801103d8`
- `0x1801127dc`
- `0x180120a90`
- `0x1801379c4`
- `0x180139470`
- `0x18014f708`
- `0x18015a110`

## callees

- `0x18015f420`

## pseudocode

```c
__int64 NtCreateSection()
{
  __int64 result; // rax

  result = 74;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x18015f420  mov     r10, rcx; NtCreateSection
0x18015f423  mov     eax, 4Ah ; 'J'
0x18015f428  test    byte ptr ds:7FFE0308h, 1
0x18015f430  jnz     short loc_18015F435
0x18015f432  syscall; Low latency system call
0x18015f434  retn
0x18015f435  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x18015f437  retn
```
