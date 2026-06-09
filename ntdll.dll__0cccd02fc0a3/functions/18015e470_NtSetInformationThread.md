# NtSetInformationThread

- ea: `0x18015e470`
- end: `0x18015e488`
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
- `0x18001f4e0`
- `0x180025998`
- `0x18002c6f0`
- `0x18002d510`
- `0x18002e3a0`
- `0x18002f4c0`
- `0x18002fc00`
- `0x18003ed70`
- `0x180046e20`
- `0x1800492e0`
- `0x18004965c`
- `0x18004b9a0`
- `0x18004c44c`
- `0x18004d920`
- `0x18004efa0`
- `0x18004f820`
- `0x180050fa0`
- `0x180051900`
- `0x180053150`
- `0x1800535c0`
- `0x180053ab0`
- `0x180060580`
- `0x180061090`
- `0x180061480`
- `0x18006eb00`
- `0x18007af10`
- `0x18007e490`
- `0x180084ef0`
- `0x180098ba0`
- `0x1800c1220`
- `0x1800c2380`
- `0x1800d82f4`
- `0x1800d8e40`
- `0x1800e02b8`
- `0x1800e9214`
- `0x180108b80`
- `0x180137d30`
- `0x1801383f0`
- `0x180138460`
- `0x180139db0`

## callees

- `0x18015e470`

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
0x18015e470  mov     r10, rcx; NtSetInformationThread
0x18015e473  mov     eax, 0Dh
0x18015e478  test    byte ptr ds:7FFE0308h, 1
0x18015e480  jnz     short loc_18015E485
0x18015e482  syscall; Low latency system call
0x18015e484  retn
0x18015e485  int     2Eh; DOS 2+ internal - EXECUTE COMMAND
0x18015e487  retn
```
