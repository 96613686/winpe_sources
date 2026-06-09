# wil::details::ResultStringSize(ushort const *)

- ea: `0x180008730`
- end: `0x180008751`
- name: `?ResultStringSize@details@wil@@YA_KPEBG@Z`
- size: `33`
- prototype: `__int64 __fastcall(wil::details *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180005604`
- `0x1800088a0`
- `0x180008ac8`

## callees

- `0x180008730`

## pseudocode

```c
__int64 __fastcall wil::details::ResultStringSize(wil::details *this, const unsigned __int16 *a2)
{
  __int64 v3; // rax

  if ( !this )
    return 2;
  v3 = -1;
  do
    ++v3;
  while ( *((_WORD *)this + v3) );
  return 2 * v3 + 2;
}

```

## disassembly

```asm
0x180008730  xor     edx, edx
0x180008732  test    rcx, rcx
0x180008735  jnz     short loc_18000873B
0x180008737  lea     eax, [rdx+2]
0x18000873a  retn
0x18000873b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000873f  inc     rax
0x180008742  cmp     [rcx+rax*2], dx
0x180008746  jnz     short loc_18000873F
0x180008748  lea     rax, ds:2[rax*2]
0x180008750  retn
```
