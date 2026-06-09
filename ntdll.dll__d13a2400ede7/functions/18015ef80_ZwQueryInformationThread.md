# ZwQueryInformationThread

- ea: `0x18015ef80`
- end: `0x18015ef98`
- name: `ZwQueryInformationThread`
- size: `24`
- prototype: ``
- caller_count: `26`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180025b20`
- `0x180034bd0`
- `0x18005fb58`
- `0x18005fd30`
- `0x18005ff38`
- `0x18007ec80`
- `0x18008a16c`
- `0x1800a7640`
- `0x1800b9d30`
- `0x1800ba138`
- `0x1800ccaf0`
- `0x1800e4900`
- `0x1800f8f98`
- `0x1801001b0`
- `0x1801025b0`
- `0x1801098f0`
- `0x18010c490`
- `0x1801212b4`
- `0x180138640`
- `0x180138670`
- `0x180138974`
- `0x180138b58`
- `0x180139050`
- `0x180139fb0`
- `0x1801496a0`
- `0x18015b960`

## callees

- `0x18015ef80`

## pseudocode

```c
__int64 ZwQueryInformationThread()
{
  __int64 result; // rax

  result = 37;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x18015ef80  mov     r10, rcx; NtQueryInformationThread
0x18015ef83  mov     eax, 25h ; '%'
0x18015ef88  test    byte ptr ds:7FFE0308h, 1
0x18015ef90  jnz     short loc_18015EF95
0x18015ef92  syscall; Low latency system call
0x18015ef94  retn
0x18015ef95  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x18015ef97  retn
```
