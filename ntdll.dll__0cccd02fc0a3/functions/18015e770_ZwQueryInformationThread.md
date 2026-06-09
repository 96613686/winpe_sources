# ZwQueryInformationThread

- ea: `0x18015e770`
- end: `0x18015e788`
- name: `ZwQueryInformationThread`
- size: `24`
- prototype: ``
- caller_count: `26`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180025b30`
- `0x180035a70`
- `0x180042f68`
- `0x180043140`
- `0x180043348`
- `0x1800622a0`
- `0x18006d6bc`
- `0x18009b1f0`
- `0x1800b5f60`
- `0x1800b6368`
- `0x1800caf60`
- `0x1800e4580`
- `0x1800f84b8`
- `0x1800ffb90`
- `0x180101fb0`
- `0x180108b80`
- `0x18010aef0`
- `0x1801207c4`
- `0x180137b50`
- `0x180137b80`
- `0x180137e84`
- `0x180138068`
- `0x180138560`
- `0x1801394c0`
- `0x180148d40`
- `0x18015afd0`

## callees

- `0x18015e770`

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
0x18015e770  mov     r10, rcx; NtQueryInformationThread
0x18015e773  mov     eax, 25h ; '%'
0x18015e778  test    byte ptr ds:7FFE0308h, 1
0x18015e780  jnz     short loc_18015E785
0x18015e782  syscall; Low latency system call
0x18015e784  retn
0x18015e785  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x18015e787  retn
```
