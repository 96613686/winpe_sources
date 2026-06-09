# wil::details::ResultStringSize(ushort const *)

- ea: `0x1800079bc`
- end: `0x1800079dd`
- name: `?ResultStringSize@details@wil@@YA_KPEBG@Z`
- size: `33`
- prototype: `__int64 __fastcall(wil::details *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180006420`
- `0x180007a4c`
- `0x180007b88`

## callees

- `0x1800079bc`

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
0x1800079bc  xor     edx, edx
0x1800079be  test    rcx, rcx
0x1800079c1  jnz     short loc_1800079C7
0x1800079c3  lea     eax, [rdx+2]
0x1800079c6  retn
0x1800079c7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800079cb  inc     rax
0x1800079ce  cmp     [rcx+rax*2], dx
0x1800079d2  jnz     short loc_1800079CB
0x1800079d4  lea     rax, ds:2[rax*2]
0x1800079dc  retn
```
