# lldpReleaseInterLock

- ea: `0x140004320`
- end: `0x140004333`
- name: `lldpReleaseInterLock`
- size: `19`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1400041fc`
- `0x140006310`
- `0x1400063bc`
- `0x14000edc0`
- `0x140010998`
- `0x140011cac`

## callees

- `0x140004320`

## pseudocode

```c
__int64 __fastcall lldpReleaseInterLock(__int64 a1)
{
  __int64 result; // rax

  if ( !*(_DWORD *)a1 )
    return _InterlockedExchange64((volatile __int64 *)(a1 + 8), 0);
  result = (unsigned int)(*(_DWORD *)a1 - 1);
  *(_DWORD *)a1 = result;
  return result;
}

```

## disassembly

```asm
0x140004320  mov     eax, [rcx]
0x140004322  test    eax, eax
0x140004324  jz      short loc_14000432C
0x140004326  dec     eax
0x140004328  mov     [rcx], eax
0x14000432a  retn
0x14000432c  xor     eax, eax
0x14000432e  xchg    rax, [rcx+8]
0x140004332  retn
```
