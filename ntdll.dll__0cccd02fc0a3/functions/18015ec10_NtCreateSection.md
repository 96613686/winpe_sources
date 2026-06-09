# NtCreateSection

- ea: `0x18015ec10`
- end: `0x18015ec28`
- name: `NtCreateSection`
- size: `24`
- prototype: ``
- caller_count: `24`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001cd30`
- `0x180028bd0`
- `0x18002b47c`
- `0x1800408d4`
- `0x1800427d0`
- `0x18005b4b0`
- `0x18009c6dc`
- `0x18009cdbc`
- `0x18009d488`
- `0x1800a6dcc`
- `0x1800b5f60`
- `0x1800e8430`
- `0x1800eb194`
- `0x1800fa8f8`
- `0x180101c3c`
- `0x1801097c0`
- `0x18010da00`
- `0x18010f078`
- `0x1801113ec`
- `0x18011ffa0`
- `0x180136ed4`
- `0x180138980`
- `0x18014eda8`
- `0x180159780`

## callees

- `0x18015ec10`

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
0x18015ec10  mov     r10, rcx; NtCreateSection
0x18015ec13  mov     eax, 4Ah ; 'J'
0x18015ec18  test    byte ptr ds:7FFE0308h, 1
0x18015ec20  jnz     short loc_18015EC25
0x18015ec22  syscall; Low latency system call
0x18015ec24  retn
0x18015ec25  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x18015ec27  retn
```
