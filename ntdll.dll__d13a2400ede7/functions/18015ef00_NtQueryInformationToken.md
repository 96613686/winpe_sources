# NtQueryInformationToken

- ea: `0x18015ef00`
- end: `0x18015ef18`
- name: `NtQueryInformationToken`
- size: `24`
- prototype: ``
- caller_count: `20`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010870`
- `0x180012eb0`
- `0x1800152b0`
- `0x180036690`
- `0x1800371d0`
- `0x18003bb70`
- `0x18003c720`
- `0x18003e190`
- `0x18003e5c0`
- `0x18003e9b0`
- `0x18003ee70`
- `0x180092b20`
- `0x1800ce978`
- `0x1800de220`
- `0x180104f10`
- `0x180107160`
- `0x18010a4f8`
- `0x18010f840`
- `0x18011297c`
- `0x180139e70`

## callees

- `0x18015ef00`

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
0x18015ef00  mov     r10, rcx; NtQueryInformationToken
0x18015ef03  mov     eax, 21h ; '!'
0x18015ef08  test    byte ptr ds:7FFE0308h, 1
0x18015ef10  jnz     short loc_18015EF15
0x18015ef12  syscall; Low latency system call
0x18015ef14  retn
0x18015ef15  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x18015ef17  retn
```
