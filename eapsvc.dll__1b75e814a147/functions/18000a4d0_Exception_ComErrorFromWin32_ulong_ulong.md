# Exception::ComErrorFromWin32<ulong>(ulong)

- ea: `0x18000a4d0`
- end: `0x18000a4e0`
- name: `??$ComErrorFromWin32@K@Exception@@SAJK@Z`
- size: `16`
- prototype: `__int64 __fastcall(int)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a5ac`
- `0x18000d338`
- `0x18000d4a8`
- `0x18000d4c8`
- `0x18000eadc`

## callees

- `0x18000a4d0`

## pseudocode

```c
__int64 __fastcall Exception::ComErrorFromWin32<unsigned long>(int a1)
{
  if ( a1 > 0 )
    return (unsigned __int16)a1 | 0x80070000;
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x18000a4d0  test    ecx, ecx
0x18000a4d2  jle     short loc_18000A4DD
0x18000a4d4  movzx   ecx, cx
0x18000a4d7  or      ecx, 80070000h
0x18000a4dd  mov     eax, ecx
0x18000a4df  retn
```
