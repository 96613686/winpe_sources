# wil::details::ResultStringSize(char const *)

- ea: `0x18000799c`
- end: `0x1800079b6`
- name: `?ResultStringSize@details@wil@@YA_KPEBD@Z`
- size: `26`
- prototype: `__int64 __fastcall(wil::details *this, const char *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800063a8`
- `0x180007a4c`
- `0x180007b88`

## callees

- `0x18000799c`

## pseudocode

```c
__int64 __fastcall wil::details::ResultStringSize(wil::details *this, const char *a2)
{
  __int64 v3; // rax

  if ( !this )
    return 1;
  v3 = -1;
  do
    ++v3;
  while ( *((_BYTE *)this + v3) );
  return v3 + 1;
}

```

## disassembly

```asm
0x18000799c  test    rcx, rcx
0x18000799f  jnz     short loc_1800079A5
0x1800079a1  lea     eax, [rcx+1]
0x1800079a4  retn
0x1800079a5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800079a9  inc     rax
0x1800079ac  cmp     byte ptr [rcx+rax], 0
0x1800079b0  jnz     short loc_1800079A9
0x1800079b2  inc     rax
0x1800079b5  retn
```
