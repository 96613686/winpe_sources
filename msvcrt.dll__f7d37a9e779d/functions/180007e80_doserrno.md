# __doserrno

- ea: `0x180007e80`
- end: `0x180007ea0`
- name: `__doserrno`
- size: `32`
- prototype: `unsigned int *__cdecl()`
- caller_count: `56`
- callee_count: `2`
- tags: ``

## callers

- `0x1800080a0`
- `0x180008140`
- `0x180008290`
- `0x180008410`
- `0x180008678`
- `0x180008960`
- `0x180008e90`
- `0x180008f30`
- `0x180009080`
- `0x180009318`
- `0x180009b10`
- `0x18000a0d8`
- `0x18000a768`
- `0x180018730`
- `0x18001b684`
- `0x18001bba4`
- `0x18001bf4c`
- `0x18001c4a0`
- `0x18001ced0`
- `0x18001cf40`
- `0x18001cf90`
- `0x18001db20`
- `0x18001dba0`
- `0x18001dcd0`
- `0x18001dd50`
- `0x18001df6c`
- `0x18001e0f0`
- `0x18001e200`
- `0x18001e3d0`
- `0x18001e4c0`
- `0x18001e560`
- `0x18001e710`
- `0x18001e7fc`
- `0x18001e9c0`
- `0x18001eb5c`
- `0x18001ecd0`
- `0x18001ee10`
- `0x18001ef40`
- `0x18001f5c0`
- `0x18001ff14`
- `0x18001ffd0`
- `0x1800200c0`
- `0x1800201cc`
- `0x180020580`
- `0x180020684`
- `0x180020750`
- `0x1800208f0`
- `0x180020ee8`
- `0x1800216f0`
- `0x180021ae0`

## callees

- `0x180007e80`
- `0x18003e074`

## pseudocode

```c
unsigned int *__cdecl _doserrno()
{
  _QWORD *v0; // rax

  v0 = getptd_noexit();
  if ( v0 )
    return (unsigned int *)v0 + 5;
  else
    return (unsigned int *)&dword_18009D284;
}

```

## disassembly

```asm
0x180007e80  sub     rsp, 28h
0x180007e84  call    _getptd_noexit
0x180007e89  test    rax, rax
0x180007e8c  jnz     short loc_180007E97
0x180007e8e  lea     rax, dword_18009D284
0x180007e95  jmp     short loc_180007E9B
0x180007e97  add     rax, 14h
0x180007e9b  add     rsp, 28h
0x180007e9f  retn
```
