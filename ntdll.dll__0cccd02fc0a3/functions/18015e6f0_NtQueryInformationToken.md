# NtQueryInformationToken

- ea: `0x18015e6f0`
- end: `0x18015e708`
- name: `NtQueryInformationToken`
- size: `24`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `20`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010870`
- `0x180012eb0`
- `0x1800152b0`
- `0x18002a640`
- `0x18002b040`
- `0x1800866c0`
- `0x1800b0870`
- `0x1800b1420`
- `0x1800b2e90`
- `0x1800b32c0`
- `0x1800b36b0`
- `0x1800b3b70`
- `0x1800ccde8`
- `0x1800de100`
- `0x1801040e0`
- `0x180106330`
- `0x180109568`
- `0x18010e4e0`
- `0x18011158c`
- `0x180139380`

## callees

- `0x18015e6f0`

## pseudocode

```c
__int64 NtQueryInformationToken()
{
  __int64 result; // rax

  result = 33;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x18015e6f0  mov     r10, rcx; NtQueryInformationToken
0x18015e6f3  mov     eax, 21h ; '!'
0x18015e6f8  test    byte ptr ds:7FFE0308h, 1
0x18015e700  jnz     short loc_18015E705
0x18015e702  syscall; Low latency system call
0x18015e704  retn
0x18015e705  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x18015e707  retn
```
