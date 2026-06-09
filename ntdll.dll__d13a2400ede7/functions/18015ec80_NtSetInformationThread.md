# NtSetInformationThread

- ea: `0x18015ec80`
- end: `0x18015ec98`
- name: `NtSetInformationThread`
- size: `24`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `46`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180015d00`
- `0x180016560`
- `0x180016640`
- `0x180016fa0`
- `0x1800183a0`
- `0x180018bc0`
- `0x18001f4d0`
- `0x180025988`
- `0x18002b9f0`
- `0x18002c810`
- `0x18002d6a0`
- `0x18002e7c0`
- `0x18002ef00`
- `0x180044ee0`
- `0x18004f8e4`
- `0x18005a8b0`
- `0x18005de30`
- `0x180063a20`
- `0x180065ee0`
- `0x18006625c`
- `0x1800685a0`
- `0x18006904c`
- `0x18006a300`
- `0x18006b980`
- `0x18006c200`
- `0x18006d980`
- `0x18006e2e0`
- `0x18006fb30`
- `0x18006ffa0`
- `0x180070490`
- `0x18007cf60`
- `0x18007da70`
- `0x18007de60`
- `0x18008b5b0`
- `0x180091350`
- `0x1800a4970`
- `0x1800c5500`
- `0x1800c6660`
- `0x1800d98c0`
- `0x1800e03d8`
- `0x1800e9874`
- `0x1801098f0`
- `0x180138820`
- `0x180138ee0`
- `0x180138f50`
- `0x18013a8a0`

## callees

- `0x18015ec80`

## pseudocode

```c
__int64 NtSetInformationThread()
{
  __int64 result; // rax

  result = 13;
  if ( (MEMORY[0x7FFE0308] & 1) != 0 )
    __asm { int     2Eh; DOS 2+ internal - EXECUTE COMMAND }
  else
    __asm { syscall; Low latency system call }
  return result;
}

```

## disassembly

```asm
0x18015ec80  mov     r10, rcx; NtSetInformationThread
0x18015ec83  mov     eax, 0Dh
0x18015ec88  test    byte ptr ds:7FFE0308h, 1
0x18015ec90  jnz     short loc_18015EC95
0x18015ec92  syscall; Low latency system call
0x18015ec94  retn
0x18015ec95  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x18015ec97  retn
```
