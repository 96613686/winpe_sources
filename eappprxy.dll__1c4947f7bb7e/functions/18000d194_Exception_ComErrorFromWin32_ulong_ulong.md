# Exception::ComErrorFromWin32<ulong>(ulong)

- ea: `0x18000d194`
- end: `0x18000d1a4`
- name: `??$ComErrorFromWin32@K@Exception@@SAJK@Z`
- size: `16`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000d214`

## callees

- `0x18000d194`

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
0x18000d194  test    ecx, ecx
0x18000d196  jle     short loc_18000D1A1
0x18000d198  movzx   ecx, cx
0x18000d19b  or      ecx, 80070000h
0x18000d1a1  mov     eax, ecx
0x18000d1a3  retn
```
