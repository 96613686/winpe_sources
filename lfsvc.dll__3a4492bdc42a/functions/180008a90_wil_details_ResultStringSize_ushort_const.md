# wil::details::ResultStringSize(ushort const *)

- ea: `0x180008a90`
- end: `0x180008ab1`
- name: `?ResultStringSize@details@wil@@YA_KPEBG@Z`
- size: `33`
- prototype: `__int64 __fastcall(wil::details *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180005810`
- `0x180008ca0`
- `0x180008ec8`

## callees

- `0x180008a90`

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
0x180008a90  xor     edx, edx
0x180008a92  test    rcx, rcx
0x180008a95  jnz     short loc_180008A9B
0x180008a97  lea     eax, [rdx+2]
0x180008a9a  retn
0x180008a9b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008a9f  inc     rax
0x180008aa2  cmp     [rcx+rax*2], dx
0x180008aa6  jnz     short loc_180008A9F
0x180008aa8  lea     rax, ds:2[rax*2]
0x180008ab0  retn
```
