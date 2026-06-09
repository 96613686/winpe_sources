# ocslen(ushort const *)

- ea: `0x180003a20`
- end: `0x180003a38`
- name: `?ocslen@@YAHPEBG@Z`
- size: `24`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003924`
- `0x180008284`
- `0x180008efc`
- `0x18000bcdc`

## callees

- `0x180003a20`

## pseudocode

```c
__int64 __fastcall ocslen(const unsigned __int16 *a1)
{
  __int64 result; // rax

  if ( !a1 )
    return 0;
  result = -1;
  do
    ++result;
  while ( a1[result] );
  return result;
}

```

## disassembly

```asm
0x180003a20  xor     edx, edx
0x180003a22  test    rcx, rcx
0x180003a25  jnz     short loc_180003A2A
0x180003a27  xor     eax, eax
0x180003a29  retn
0x180003a2a  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003a2e  inc     rax
0x180003a31  cmp     [rcx+rax*2], dx
0x180003a35  jnz     short loc_180003A2E
0x180003a37  retn
```
